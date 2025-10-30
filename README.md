## Browser-Extension-Threat-Analysis

Author: Rajeev More  
Date: October 30, 2025  

## Objective
To perform a comprehensive security analysis of all installed Chrome extensions, evaluate their permissions, detect potential threats or privacy risks, and mitigate them by disabling or removing untrusted extensions.

## Tools Used
- Browser: Google Chrome

## Steps Performed

### 1. Extension Enumeration
- Opened `chrome://extensions/` and listed all installed extensions.  
- Captured screenshots of each extension’s info page (name, version, permissions, and site access).  
- Saved all screenshots in the `evidence/` folder.

### 2. Extension Permission Review
- Reviewed each extension’s declared permissions and site access.  
- Checked if the extension requested high-risk permissions like:
  - “Read and change all your data on websites”
  - “Access browsing history”
  - “Change search settings”
- Cross-verified legitimacy using the Chrome Web Store listing and online reviews.

### 3. Risk Assessment
- Extensions from trusted publishers (Google, Norton, AdBlock Inc.) were marked safe.  
- Third-party or niche tools were flagged for monitoring.  
- Any extension with potential to modify search or access browsing data unnecessarily was disabled.

### 4. Mitigation & Verification
- Disabled unnecessary or high-permission extensions.  
- Restarted Chrome to verify safe functionality and normal browsing.  
- Captured “before” and “after” screenshots for documentation.

## Findings Summary

| Name                               | Version  | Enabled | Permissions                                                  | Source               | Risk Level | Notes / Action Taken                                     |
|------------------------------------|----------|---------|--------------------------------------------------------------|----------------------|------------|----------------------------------------------------------|
| Chrome Remote Desktop              | 2.1      |  Yes    | Manage downloads; Communicate with native apps               | Chrome Web Store     | Low        | Legit Google extension — *Disabled*                      |
| AI Google Form Builder             | 1.4      |  Yes    | No special permissions                                       | Chrome Web Store     | Medium     | Third-party AI tool; safe but *Removed*                  |
| Google Docs Offline                | 1.97.1   |  Yes    | Read/change data on docs.google.com & drive.google.com       | Installed by default | Low        | Official Google extension — *Kept*                       |
| Google Meet Enhanced Experience    | 4.0.0    |  Yes    | Read/change data on meet.google.com                          | Chrome Web Store     | Low        | Verified safe — *Disabled*                               |
| Google Translate                   | 2.0.16   |  Yes    | Read/change all data on websites                             | Chrome Web Store     | Low        | Trusted Google extension — *Kept*                        |
| Norton Safe Search                 | 3.24.0.5 |  No     | Read browsing history; Block content; Change search settings | Chrome Web Store     | Medium     | Legit Norton tool, but not required daily — *Removed*    |
| Swiggy Zomato Spendings Calculator | 1.0.4    |  Yes    | Read browsing history (swiggy.com, zomato.com)               | Chrome Web Store     | Medium     | Third-party; narrow scope but *Removed*                  |
| AdBlock — block ads across the web | 6.30.1   |  Yes    | Read/change all data; Display notifications                  | Chrome Web Store     | Low        | Verified publisher (AdBlock Inc.) — *Kept*               |
| ChatGPT Search                     | 1.11     |  No     | Change search settings to chatgpt.com                        | Chrome Web Store     | Medium     | Modified search engine; *Removed*                        |

## Observations
- Most extensions are verified and safe, originating from official or reputable sources.  
- Two third-party extensions (`AI Google Form Builder`, `Swiggy Zomato Spendings Calculator`) need ongoing monitoring.  
- Potential risk found: “ChatGPT Search” — disabled due to search redirection.  
- No evidence of adware, credential theft, or network interception detected.

## Security Recommendations
1. Only install extensions from official sources and reputable developers.  
2. Avoid extensions requiring broad permissions unless absolutely necessary.  
3. Review extension permissions monthly.  
4. Disable unused extensions to minimize attack surface.  
5. Keep Chrome updated and enable “Enhanced Safe Browsing.”  
6. Avoid enabling extensions in Incognito mode unless trusted.

## Repository Structure
Browser-Extension-Threat-Analysis
├── README.md
├── Extension_Summary.csv
└── Screenshots
