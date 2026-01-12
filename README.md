# Nike_scraper_challenge
NIKE PRODUCT DATA EXTRACTION – TECHNICAL DOCUMENTATION
Author: Ishan Wade

--------------------------------------------------
1. INTRODUCTION
--------------------------------------------------

This project was developed as part of the Relu Consultancy Hiring Challenge for the role of Data Extraction Engineer (FTE). The objective of the task is to scrape product data from the Nike Philippines website (https://www.nike.com/ph/w), clean and filter the data based on defined business rules, perform analytical operations, and store the results in CSV format.

The solution is implemented using Python and Selenium to handle dynamic web content, pagination, and real-time user interactions such as cookie consent handling.

--------------------------------------------------
2. TECHNOLOGY STACK
--------------------------------------------------

Programming Language:
- Python 3

Libraries Used:
- Selenium
- Pandas
- Time
- Regular Expressions (re)

Browser & Driver:
- Google Chrome
- Chrome WebDriver

--------------------------------------------------
3. HIGH-LEVEL ARCHITECTURE
--------------------------------------------------

The scraper follows a modular, class-based design using a single main class called NikeScraper.

Main components:
- Browser setup and configuration
- Pagination-aware product link extraction
- Individual product detail scraping
- Data validation and filtering
- Analytical processing
- CSV file generation
- Console output reporting

--------------------------------------------------
4. WORKFLOW AND EXECUTION STEPS
--------------------------------------------------

Step 1: Browser Initialization
- Chrome browser is initialized with automation-detection disabled.
- Explicit waits are used to ensure elements load correctly.
- Cookie consent pop-up is handled if it appears.

Step 2: Product Listing Extraction
- The scraper opens the Nike Philippines product listing page.
- All product cards are detected using stable data-testid attributes.
- Pagination is handled automatically until no more pages are available.
- Product URLs are collected uniquely to avoid duplicates.

Step 3: Individual Product Scraping
The following fields are extracted for each product:
Product_URL, Product_Image_URL, Product_Tagging, Product_Name,
Product_Description, Original_Price, Discount_Price,
Sizes_Available, Vouchers, Available_Colors, Color_Shown,
Style_Code, Rating_Score, Review_Count.

Step 4: Tagging Rule Enforcement
- Products with empty Product Tagging are excluded.
- Total empty tagging count is printed to the console.

Step 5: Data Filtering and Storage
- Only products with non-empty tagging and discount price are saved.
- Output file: nike_products_valid.csv

--------------------------------------------------
5. ANALYTICAL REQUIREMENTS
--------------------------------------------------

A. Top 10 Most Expensive Products
- Sorted using discount price
- Printed to console only

B. Ranking Based on Rating & Review Count
- Review Count > 150
- Ranking based on rating, then review count
- Output file: top_20_rating_review.csv

--------------------------------------------------
6. ROBUSTNESS AND ERROR HANDLING
--------------------------------------------------

- Explicit waits prevent page load issues
- Try-except blocks handle missing data
- Controlled delays prevent aggressive scraping
- Duplicate records are avoided

--------------------------------------------------
7. FINAL OUTPUTS
--------------------------------------------------

Generated Files:
1. nike_products_valid.csv
2. top_20_rating_review.csv

Console Output:
- Total products with empty tagging
- Top 10 most expensive products

--------------------------------------------------
8. CONCLUSION
--------------------------------------------------

This project demonstrates a complete data extraction pipeline including scraping, validation, analysis, and structured storage using Python and Selenium.

--------------------------------------------------
END OF DOCUMENT
--------------------------------------------------
