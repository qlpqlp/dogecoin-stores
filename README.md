# Dogecoin Stores Map

A comprehensive mapping of stores, organizations, and businesses that accept Dogecoin as payment. This JSON dataset is designed to be used with the Dogecoin Wallet Map Source to help users discover places where they can spend their DOGE.

## 📍 Purpose

This repository maintains a curated list of all physical and online stores, restaurants, organizations, and businesses worldwide that accept Dogecoin. The goal is to create a global directory that makes it easy for Dogecoin users to find places to spend their cryptocurrency.

## 📊 JSON Structure

The `doge-stores.json` file contains an array of store objects, each with the following structure:

```json
{
  "lat": 38.250297,
  "lon": -85.735915,
  "category": "Food",
  "name": "Dogebeans Coffee",
  "description": "Coffee shop accepting Dogecoin",
  "address": null,
  "postal": "40204",
  "location": "Louisville",
  "country": "USA",
  "email": "dogebeanscoffee@gmail.com",
  "phone": null,
  "website": "https://dogebeans.com/",
  "social": []
}
```

### Field Descriptions

- **`lat`** (number, required): Latitude coordinate for mapping
- **`lon`** (number, required): Longitude coordinate for mapping
- **`category`** (string, required): Business category (e.g., "Food", "Clothing", "Electronics", "Restaurant", "Hotel", etc.)
- **`name`** (string, required): Business/store name
- **`description`** (string, optional): Brief description of the business
- **`address`** (string, optional): Street address (can be null)
- **`postal`** (string, required): Postal/ZIP code
- **`location`** (string, required): City or location name
- **`country`** (string, required): Country name
- **`email`** (string, optional): Contact email (can be null)
- **`phone`** (string, optional): Contact phone number (can be null)
- **`website`** (string, optional): Business website URL (can be null)
- **`social`** (array, optional): Array of social media profile URLs (can be empty array)

### Supported Categories

- Food
- Clothing
- Electronics
- Vehicles
- Health
- Beauty
- Sports
- Toys
- Business
- Pets
- Hotel
- Restaurant
- Photography
- BarberShop
- Icecream
- Other

## 🍴 Forking and Creating Your Own

You can fork this repository to create your own version or regional variant:

1. **Fork the Repository**
   - Click the "Fork" button on GitHub
   - Clone your fork: `git clone https://github.com/YOUR_USERNAME/dogecoin-stores.git`

2. **Customize for Your Needs**
   - Modify `doge-stores.json` to include stores in your region
   - Add custom categories if needed
   - Update the README to reflect your project's purpose

3. **Use in Your Application**
   - Load the JSON file in your application
   - Parse and display stores on a map
   - Filter by category, location, or country

## 🗺️ Adding to Dogecoin Wallet Map Source

To integrate this JSON file with the Dogecoin Wallet Map Source:

1. **Point to the Raw JSON URL**
   - Use the raw GitHub URL: `https://raw.githubusercontent.com/YOUR_USERNAME/dogecoin-stores/main/doge-stores.json`
   - Or use the CDN URL if available

2. **Configure the Map Source**
   - In your Dogecoin Wallet Map configuration, set the data source to this JSON file
   - Ensure your map application can parse the JSON structure
   - Map the fields to your display format

3. **Example Integration**
   ```javascript
   fetch('https://raw.githubusercontent.com/YOUR_USERNAME/dogecoin-stores/main/doge-stores.json')
     .then(response => response.json())
     .then(stores => {
       // Display stores on map
       stores.forEach(store => {
         addMarker(store.lat, store.lon, store.name);
       });
     });
   ```

## 🤝 Contributing to This Repository

We welcome contributions! Here's how you can help:

### Adding a New Store

1. **Fork the Repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/dogecoin-stores.git
   cd dogecoin-stores
   ```

2. **Add Your Store Entry**
   - Open `doge-stores.json`
   - Add a new object to the array following the structure above
   - Ensure all required fields are filled
   - Use `null` for optional fields that don't apply
   - Use an empty array `[]` for social if there are no social links

3. **Validate JSON**
   - Ensure the JSON is valid (no trailing commas, proper syntax)
   - You can use online JSON validators or:
     ```bash
     python -m json.tool doge-stores.json > /dev/null
     ```

4. **Submit a Pull Request**
   ```bash
   git checkout -b add-store-name
   git add doge-stores.json
   git commit -m "Add [Store Name] accepting Dogecoin"
   git push origin add-store-name
   ```
   Then create a Pull Request on GitHub.

### Updating Existing Stores

- Follow the same process as adding a new store
- Find the existing entry and update the relevant fields
- Commit with a message like: "Update [Store Name] information"

### Guidelines for Contributions

- ✅ Verify the store actually accepts Dogecoin before adding
- ✅ Use accurate coordinates (lat/lon)
- ✅ Include as much information as possible
- ✅ Use consistent category names
- ✅ Keep descriptions concise
- ✅ Ensure all URLs are valid and accessible
- ❌ Don't add stores that don't accept Dogecoin
- ❌ Don't add duplicate entries
- ❌ Don't modify entries for stores you don't own without permission

## 📝 JSON Validation

Before submitting, ensure your JSON is valid:

```bash
# Using Python
python -m json.tool doge-stores.json

# Using Node.js
node -e "JSON.parse(require('fs').readFileSync('doge-stores.json'))"

# Using jq (if installed)
jq . doge-stores.json
```

## 🌍 Current Coverage

This dataset currently includes stores from:
- United States
- France
- Portugal
- United Kingdom
- Germany
- Netherlands
- India
- Brazil
- Canada
- Italy
- Panama
- And more...

## 📄 License

This project is open source. Please check the LICENSE file for details.

## 🔗 Related Projects

- [Dogecoin Wallet](https://github.com/dogecoin/dogecoin) - The official Dogecoin wallet
- [Dogecoin Foundation](https://foundation.dogecoin.com/) - Official Dogecoin Foundation

## 💬 Questions or Issues?

If you have questions, find errors, or want to suggest improvements:
- Open an Issue on GitHub
- Submit a Pull Request
- Contact the maintainers

---

**Much Wow!** 🐕 Let's make it easy for everyone to spend their Dogecoin! 🚀

