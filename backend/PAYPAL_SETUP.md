# PayPal Payment Integration Setup

## 1. Install Dependencies

Run the following command to install the PayPal payment package:

```bash
pnpm install @medusajs/payment-paypal
```

Or if using npm:
```bash
npm install @medusajs/payment-paypal
```

## 2. Environment Variables

Add the following environment variables to your `.env` file or Railway environment settings:

```env
# PayPal Configuration
PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_CLIENT_SECRET=your_paypal_client_secret
PAYPAL_SANDBOX=true  # Set to false for production
PAYPAL_AUTH_WEBHOOK_ID=your_paypal_webhook_id  # Optional
```

## 3. PayPal Developer Account Setup

1. Go to [PayPal Developer](https://developer.paypal.com/)
2. Log in with your PayPal account
3. Create a new application
4. Get your Client ID and Client Secret from the app details
5. For sandbox testing, use the sandbox credentials
6. For production, switch to live credentials and set `PAYPAL_SANDBOX=false`

## 4. Webhook Configuration (Optional)

If you want to handle PayPal webhooks:

1. In your PayPal app settings, configure webhooks
2. Set the webhook URL to: `https://your-backend-domain/webhooks/paypal`
3. Add the webhook ID to your `PAYPAL_AUTH_WEBHOOK_ID` environment variable

## 5. Restart Your Application

After setting up the environment variables, restart your Medusa backend:

```bash
pnpm run dev
```

## 6. Test Payment

1. Go to your storefront
2. Add items to cart and proceed to checkout
3. You should see PayPal as a payment option
4. Use PayPal sandbox accounts for testing

## Troubleshooting

- Ensure all environment variables are properly set
- Check that the PayPal package is installed correctly
- Verify your PayPal app is configured for the correct environment (sandbox vs live)
- Check the Medusa logs for any PayPal-related errors 