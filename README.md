# RepeaterBook Config Generator

This tool generates RTLSDR-Airband configuration files from RepeaterBook CSV exports. It runs entirely in the browser, hosted on GitHub Pages, allowing users to upload a CSV, customize settings, and download a config file without any server-side processing.

## Features
- **Input:** Upload a RepeaterBook CSV file with a "Freq" column (e.g., `146.88000` MHz).
- **Modes:**
  - **Scan Mode:** Monitors frequencies sequentially with a single channel block.
  - **Multichannel Mode:** Assigns each frequency its own channel, with an optimal or user-specified center frequency.
- **Customization:**
  - Sample rate (default: 2.4 Msps) for multichannel bandwidth.
  - Optional center frequency override in multichannel mode (pre-populated with calculated ideal value).
- **Output:** Downloads a `rtlsdr_airband.conf` file with sorted frequencies and CSV metadata as comments.
- **Warnings:** Alerts in the browser and config file if frequencies exceed the bandwidth in multichannel mode.

## Usage
1. Visit the live site at [https://seanauff.github.io/repeaterbook-config-generator/](https://seanauff.github.io/repeaterbook-config-generator/).
2. Upload a RepeaterBook CSV file.
3. Select "Scan" or "Multichannel" mode.
4. Adjust sample rate or center frequency (multichannel only) if desired.
5. Click "Generate Config" and download the resulting `rtlsdr_airband.conf`.

## Example CSV Format
```text
Freq,Input,Offset,Tone,Location,ST/PR,County,Call,Use,Miles,Bearing,Degrees
146.88000,146.28,-0.60000,100.00,"Centennial Warren Mtn",CO,Jefferson,KE0NCQ,OPEN,9.1,W,262.8
```

## Deployment
- Hosted on GitHub Pages from the `main` branch.
- Edit `index.html` to modify the tool; push changes to update the live site.

## Dependencies
- [Papa Parse](https://www.papaparse.com/) (v5.3.0) for CSV parsing, loaded via CDN.

## License
This project is open-source under the [MIT License](LICENSE).