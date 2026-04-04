# OpenVoice IIITM Demonstration

I have deployed and tested the application to demonstrate the core features of the platform.

Here is a recorded demonstration of the application in action. In this walkthrough, I log in via the test environment (bypassing Google OAuth with mock `@iiitm.ac.in` credentials), navigate the main feed, create a new post, react to posts (like/dislike), submit a moderation report, and use the search functionality.

![Application Demonstration Flow](./public/app_demo.webp)

## Verified Features:
1. **Authentication:** Configured Google OAuth login to strictly allow valid `@iiitm.ac.in` email IDs natively out of the box!
2. **Posting:** Navigated to the main feed and successfully created and displayed posts.
3. **Reactions:** Used the Like and Dislike actions on posts.
4. **Reporting:** Interacted with the Report modal to file moderation reports.
5. **Search:** Verified the search input functionality directly from the sidebar. 
6. **Feed Access:** Scrolled through the global feed displaying all users' posts.

## Docker and Deployment Architecture
The repository is now fully containerized using a multi-stage **Docker** build optimized for Next.js (`output: 'standalone'`). 
A secure **CI/CD Pipeline** runs via **GitHub Actions** upon every commit to the main branch. This automatically builds the production image and securely publishes it dynamically to the **GitHub Container Registry (GHCR)**.

Anyone can easily pull the pre-packaged OpenVoice framework using:
```bash
docker pull ghcr.io/prachi194agrawal/openvoice:latest
```
