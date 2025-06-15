# FASTA Validation Tool

A web application for validating and analyzing FASTA sequence files, built with Svelte and HyPhy.

## Installation and Setup

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn

### Installation

1. Clone the repository

```bash
git clone https://github.com/stevenweaver/fasta-validation.git
cd fasta-validation
```

2. Install dependencies

```bash
npm install
# or
yarn install
```

3. Start the development server

```bash
npm run dev
# or
yarn dev
```

4. Open your browser and navigate to `http://localhost:5173`

## Usage

The application allows you to:
- Upload and validate FASTA sequence files
- Run various analyses on sequence data
- Visualize analysis results
- Export results in multiple formats

All data is stored locally in your browser using IndexedDB.

## Building for Production

To create a production build:

```bash
npm run build
# or
yarn build
```

You can preview the production build with:

```bash
npm run preview
# or
yarn preview
```

## Environment Configuration

This application uses environment variables for configuration:

- `VITE_PAGES_URL`: URL for visualization iframes (defaults to `//localhost:3000/pages` in development)
- `VITE_HYPHY_EYE_URL`: URL for the HyPhy Eye visualization server (defaults to `http://localhost:3000` in development)

You can create a `.env` file in the project root to set these variables:

```
VITE_PAGES_URL=//your-visualization-server.com/pages
VITE_HYPHY_EYE_URL=https://your-hyphy-eye-server.com
```

## Storage

The application uses browser-based IndexedDB storage for persisting files and analysis results.
This means data is stored locally in the user's browser and is not sent to any server.

## Testing

Run the test suite with:

```bash
npm run test
# or
yarn test
```

## Development

### Adding New Visualization Methods

To add new visualization methods:

1. Update the method list in `src/lib/AnalysisResultViewer.svelte`
2. Add a method configuration in `src/lib/config/methodOptions.toml`
3. Ensure the visualization is available in HyPhy Eye

### Project Structure

- `src/lib` - Svelte components and utilities
- `src/routes` - SvelteKit routes
- `src/stores` - Svelte stores for state management
- `src/lib/utils` - Utility functions including IndexedDB storage
- `static` - Static assets and test data
