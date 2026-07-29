# Analyze My Resume

> See your resume through ATS eyes. Validate against the 3 universal parsing methods used by applicant tracking systems.

**Live Demo:** [Coming Soon]

## What This Tool Does

90% of large companies use Applicant Tracking Systems (ATS) to filter resumes before human recruiters see them. If your resume isn't formatted for ATS compatibility, you may be automatically rejected—no matter how qualified you are.

**Analyze My Resume** helps you:
- **Parse your resume** using the same methods ATS systems use
- **Identify formatting issues** that cause parsing failures
- **Validate compatibility** against 3 universal ATS parsing methods
- **Edit and optimize** your resume in real-time with AI assistance

## The 3 Universal ATS Parsing Methods

Our tool validates your resume against all three core parsing methods to ensure maximum compatibility:

### 1. Plain Text Extraction
The most universal method. ATS converts your document to plain text and reads it sequentially, top to bottom.

**What we check:**
- Text extracts cleanly from your PDF
- Content is in logical sequential order
- Name and contact info are clearly identifiable
- Sufficient text content (not a scan or image)

### 2. Pattern & Keyword Matching
ATS looks for specific patterns using rules-based logic to identify sections, dates, and contact information.

**What we check:**
- Email and phone number formats are recognizable
- Section headers follow standard patterns (Experience, Education, Skills, etc.)
- Date formats are consistent and parseable
- Degrees and certifications use standard terminology

### 3. NLP & AI Parsing
Modern ATS systems use Natural Language Processing to understand context and extract meaning.

**What we check:**
- Document structure supports semantic analysis
- No multi-column layouts that confuse parsing
- No images or graphics obscuring text
- Rich descriptive content (bullet points, achievements)
- Skills section present for keyword extraction

## Features

### 🔍 ATS X-Ray Mode
Upload your resume and see exactly what ATS systems extract:
- Contact information parsing
- Section detection and classification
- Entry-level field extraction (company, role, dates, location)
- Confidence scores for each extracted field
- Real-time format hazard warnings

### ✅ 3-Method Validation
Get scored validation results for all three ATS parsing methods:
- **Pass/Warn/Fail** status for each method
- Detailed scoring breakdown (0-100)
- Specific issues identified with actionable feedback
- Overall compatibility assessment

### 🎯 Format Hazard Detection
Automatically flags common issues:
- Multi-column layouts
- Text in headers/footers
- Embedded images
- Excessive font variations
- Unusual bullet characters
- Scanned documents

### ✏️ Built-in Resume Builder
Edit and optimize your resume directly in the app:
- Real-time visual preview
- Structured editor for profile, experience, education, skills
- Export to ATS-optimized PDF
- Multiple design templates (all ATS-friendly)

### 🤖 AI-Powered (Coming Soon)
- Intelligent content suggestions
- Keyword optimization
- Achievement rewriting
- Industry-specific recommendations

## How It Works

### For Users

1. **Upload Your Resume** — Drop your PDF into the analyzer
2. **Review X-Ray Results** — See what ATS systems extract from your resume
3. **Check 3-Method Validation** — Get compatibility scores for all parsing methods
4. **Fix Issues** — Load parsed content into the editor and make corrections
5. **Export & Apply** — Download your optimized resume

### Technical Architecture

```
User PDF → PDF.js Parser → Text Extraction → Multi-Stage Analysis
                                                      ↓
                                    ┌─────────────────┴─────────────────┐
                                    ↓                 ↓                 ↓
                            Plain Text Score   Pattern Match Score   NLP Score
                                    ↓                 ↓                 ↓
                                    └─────────────────┬─────────────────┘
                                                      ↓
                                          Final ATS Compatibility Report
```

#### Parsing Pipeline

1. **PDF Text Extraction** (via PDF.js)
   - Extract text items with positioning data
   - Detect font styles (bold, size, family)
   - Identify embedded images

2. **Line Grouping**
   - Merge text items into logical lines
   - Detect multi-column layouts
   - Calculate line spacing and gaps

3. **Section Detection**
   - Identify section headers using pattern matching
   - Map to canonical section types (work, education, skills, etc.)
   - Handle custom section headers

4. **Field Extraction**
   - Parse contact information (email, phone, location, links)
   - Extract structured entries (company, role, dates, location)
   - Identify bullet points and descriptions
   - Assign confidence scores to each field

5. **Hazard Analysis**
   - Flag multi-column layouts
   - Detect text in header/footer zones
   - Count embedded images
   - Check for scanned documents

6. **3-Method Validation**
   - **Method 1:** Validate plain text extraction quality
   - **Method 2:** Validate pattern/keyword recognition
   - **Method 3:** Validate NLP-friendly structure

## Technology Stack

- **Frontend:** Pure HTML/CSS/JavaScript (no build step required)
- **PDF Parsing:** [PDF.js](https://github.com/mozilla/pdf.js) (Mozilla)
- **Architecture:** Single-page application, runs entirely in browser
- **Privacy:** All processing happens client-side, no data sent to servers

## Based on Open Resume

This tool is built on the foundation of [Open Resume](https://github.com/xitanggg/open-resume), an open-source resume parser and builder. We've enhanced it with:
- 3-Method ATS validation scoring
- Enhanced hazard detection
- Detailed compatibility reporting
- AI-powered suggestions (coming soon)

## Installation & Development

### Quick Start

1. Clone the repository:
```bash
git clone https://github.com/yourusername/analyze-my-resume.git
cd analyze-my-resume
```

2. Serve the `public` directory with any static file server:
```bash
# Using Python
python -m http.server 8000 --directory public

# Using Node.js
npx serve public

# Using PHP
php -S localhost:8000 -t public
```

3. Open `http://localhost:8000` in your browser

### Deployment

#### Cloudflare Pages (Recommended)

1. Create `wrangler.toml`:
```toml
name = "analyze-my-resume"
compatibility_date = "2025-01-01"

[assets]
directory = "public"
not_found_handling = "single-page-application"
```

2. Deploy:
```bash
npx wrangler deploy
```

#### GitHub Pages

```bash
# Build and push
git add .
git commit -m "Deploy to GitHub Pages"
git push origin main

# Enable GitHub Pages in repository settings
# Source: main branch, /public folder (or configure as root)
```

#### Vercel / Netlify

Simply connect your repository and set the build directory to `public`.

## File Structure

```
analyze-my-resume/
├── public/
│   ├── index.html          # Main resume builder/analyzer app
│   ├── landing.html         # Marketing landing page
│   └── (no other files needed - all-in-one HTML)
├── wrangler.toml            # Cloudflare Pages config
└── README.md                # This file
```

## Privacy & Security

- **No data collection:** Your resume never leaves your browser
- **No tracking:** No analytics or third-party scripts
- **No uploads:** All parsing happens client-side using PDF.js
- **Open source:** Inspect the code yourself

## Roadmap

- [x] PDF parsing and text extraction
- [x] 3-Method ATS validation
- [x] Format hazard detection
- [x] Resume builder with live preview
- [ ] AI-powered content suggestions
- [ ] Keyword optimization scoring
- [ ] Industry-specific ATS templates
- [ ] Multi-language support
- [ ] Browser extension
- [ ] LinkedIn import

## Contributing

Contributions welcome! This project is based on open-source technology and we'd love to improve it together.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

MIT License - see LICENSE file for details

Built with Open Resume technology. Enhanced with AI capabilities.

## Credits

- **Open Resume** by [@xitanggg](https://github.com/xitanggg) - Original resume parser and builder
- **PDF.js** by Mozilla - PDF rendering and text extraction
- **ATS Research** - Based on analysis of Workday, Taleo, Greenhouse, Lever, and other major ATS platforms

## Support

Having issues? Found a bug?
- Open an issue on GitHub
- Check existing issues for solutions
- Review the FAQ in the app

---

**Built for job seekers. Free forever.**

Stop wondering if your resume will make it through ATS. Start knowing.
