## Checklist: 

1. Have a Dev/Personal Mac with the latest OS.
2. Have VSCode installed.
3. Have Developer Tools installed.

## Setup Instructions:

1. Install Go from the official website.
    - Link: [Go](https://go.dev/doc/install)

PERSONAL MAC:

2. Install Brew
    - Link: [Brew](https://brew.sh/)

3. Install Terraform with Brew
    - Link: [Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

DEV MAC:

3. Install Terraform with SelfService

4. In VSCode: Clone Provider and add to workspace (command + shift + p, type clone, hit enter)
    - Link: https://github.com/deploymenttheory/terraform-provider-jamfpro
    - reccomend placing at /Users/YOU/github/

5. Create the following folder:
    - `/Users/YOU/.terraform.d/plugins/terraform.local/local/jamfpro/0.1.0/darwin_arm64`

    Terminal: 
    ```
    mkdir -p /Users/YOU/.terraform.d/plugins/terraform.local/local/jamfpro/0.1.0/darwin_arm64
    ```

6. Open VSCode Terminal

7. Navigate to the provider folder in the terminal (if not there already) using `cd /path-to-provider-folder-that-you-cloned-in-step-4`

8. Build Provider Binary - this will make a new binary file in the provider folder
    - `go build`

9. Move the new Go Binary to the `.terraform.d////darwin_arm64` folder (manually or using `mv current_dir new_dir`)

10. Clone the workshop if you have not already. (Where you're reading this readme.)
    - Link github.com/thejoeker12/terraform-workshop

10. a. Navigate in the Terminal back to the workshop folder `cd /path-to-workshop-folder-you-cloned-in-step-10`


12. Make a new file & name it something.tf (I use infra.tf)

13. Make a new file & name it `clientauth.json`

14. Login to lbgsandbox & navigate to > Settings > API Roles & Clients > API Clients > workshop

15. Get credentials from teams chat.

16. Fill `clientauth.json` accordingly: 

    ```json
    {
        "instanceName": "lbgsandbox",
        "clientId": "ID HERE",
        "clientSecret": "SECRET HERE"
    }
    ```

17. Init Terraform in VSCode terminal
    - `terraform init`

17. Done.