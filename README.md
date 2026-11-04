# StudyBuddy AHS (PWA)

Installable Android web app: an AI study tutor tailored to the Austrian AHS curriculum.
Onboarding builds a "Master Prompt" from grade, branch, focus, subjects, tone, depth and format.

## Try it locally
    cd studybuddy-pwa && python3 -m http.server 8080
Open http://localhost:8080 (service workers work on localhost).

## Put it on a phone
PWAs need HTTPS. Upload this folder to any static host (GitHub Pages, Netlify, Cloudflare Pages).
On Android Chrome: open the URL -> menu -> "App installieren" / "Zum Startbildschirm hinzufügen".

## API key / going beyond personal use
This version stores the student's own Anthropic API key in the browser and calls the API directly.
That is fine for you or a few testers. For distributing to many students, put a tiny server
(e.g. a Cloudflare Worker) between app and API that holds your key, rate-limits, and applies the
system prompt — then change the fetch URL in index.html. Also consider data-protection rules (DSGVO)
for minors before collecting any student data.

## Next steps
Flashcard/quiz screens, Schularbeiten calendar with reminders, photo upload for homework, a Play Store
wrapper (Trusted Web Activity via Bubblewrap/PWABuilder).
