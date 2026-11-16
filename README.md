# Shawarma Bite: setup (about 20 minutes)

1. **Supabase:** create a free project at supabase.com.
2. **Database:** SQL Editor > run `schema.sql`, then `seed.sql`.
3. **Lock sign-ups:** Authentication > Sign In / Providers > turn OFF "Allow new users to sign up". Only people you add can log in.
4. **Owner account:** Authentication > Users > Add user (email + strong password, tick auto-confirm). Then in SQL Editor run:
   `update profiles set role='owner' where email='YOUR-EMAIL';`
5. **Staff accounts:** add them the same way in Users. They are staff automatically. The owner can change roles in the admin page.
6. **Connect the site:** put your Project URL and anon key in `config.js`.
7. **Vercel:** upload this folder to a GitHub repo, then Vercel > Add New Project > import it. Framework: Other. No build command.
8. **Supabase URL settings:** Authentication > URL Configuration > set Site URL to your Vercel address.

Pages: `/` is the customer site, `/admin.html` is the login.
Owner: everything, including deleting items and managing staff. Staff: edit and add items, prices, sold-out, photos.
These limits are enforced by the database, not just hidden in the page.
