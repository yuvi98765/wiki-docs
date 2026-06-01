Cd LLM Documentation 

(Windows) 

Create Cloudflare account 

Go to the Cloudflare website: https://dash.cloudflare.com 

Sign up 

Verify your email with the account 

Choose a plan to use (optional) 

Go to the workers & page on the left hand side of the screen 

Install Node.js 

Go to the official website: https://nodejs.org 

Download Node.js with the LTS option 

Open the .msi file (on windows) 

Click next and accept the license agreement 

Keep all default settings 

wranglkwrMake sure Npm is included 

Click install 

Verify installation 

Open command prompt in administrator mode  

Type node -v then npm -v 

You should see something like v20.x.x and 9.x.x 

Install Wrangler (Cloudflares CLI tool) 

In CMD (Administrator) run npm install -g wrangler 

Verify installation 

Wrangler -v 

You should see a version number like wrangler 3.x.x 

In CMD, Run wrangler login then login to the website that should open after doing the command 

Test it 

Wrangler whoami 

Create a worker project 

Run npm create cloudflare@latest, this creates the project 

When prompted, name your project 

For category, choose Hello World example 

For template, choose worker only 

For language choose JavaScript 

When asked to add AGENTS.md file, choose yes 

Deploy the application, if it opens a browser page with text saying "Hello World!”, everything is working. 

Set-up your application 

Use cd your-project-name to enter project directory 

Use cd src to enter src directory to find index.js 

Use notepad or any other IDE to edit index.js 

Add the following JavaScript 

export default { 

  async fetch(request, env) { 

    const response = await env.AI.run( 

      "@chosen/ai/model", 

      { 

        messages: [ 

          { role: "user", content: "Your question" } 

        ] 

      } 

    ); 

    return Response.json(response); 

  } 

}; 

Choose an AI model from https://developers.cloudflare.com/workers-ai/models/  

Go back to main project directory, this time we will edit wrangler.jsonc 

 

 

 

 

 

 

Add the following lines to the end of the code 

{ 

"$schema": "node_modules/wrangler/config-schema.json", 

"name": "worker-ai", 

"main": "src/index.js", 

"compatibility_date": "2026-04-06", 

"observability": { 

"enabled": true 

}, 

"upload_source_maps": true, 

"compatibility_flags": [ 

"nodejs_compat" 

], 

 

"ai": { 

"binding": "AI" 

} 

} 

The only thing added here is the AI section, this allows our application to use Workers AI. 

Use npm run dev, press b to open up a browser. This should open a webpage in your browser and instead of Hello World, you should see the answer to the question we made in the JavaScript. 

 

 

 

 

 

 

 

KIMI 2.5 

Kimi 2.5 is a developed AI model which gives you fast and stable answers (@cf/moonshotai/kimi-k2.5) 
