# Solsta Create, Update or Delete (CRUD) Action for GitHub

This project is a GitHub Action that uses Solid State Networks tools and services to create, delete, or modify Solsta products, environments, repositories, or releases.

The action is compatible with Windows, Linux, and OSX runners.  Windows self-hosted runners require git-bash (https://git-scm.com/) in the %PATH%.

## Variables

* **solsta_client_id:** Client ID to authenticate usage of Solid State Networks console tools
* **solsta_client_secret:** Secret Key to authenticate usage of Solid State Networks console tools
* **console_version:** Version of Solsta Console Tools to use
* **scripts_version:** Version of Solsta Deploy Scripts to use
* **action_type:**  Either create, delete, or update
* **object_type:**  Either product, repository, environment, or release to create/update/delete 
* **target_product:**  Target product to create/update/delete (case-sensitive)
* **target_environment:**  Target environment to create/update/delete (case-sensitive)
* **target_repository:**  Target repository to create/update/delete (case-sensitive)
* **target_release:**  Target release to create/update/delete (case-sensitive)
* **description**  Friendly description of the modified object
* **publish_location:**  Environment publish location URI
* **source_location:**  Environment source location URI
* **update_path_count:**  Environment update path count number
* **optional:**  Whether the target repository is optional (true/false)
* **notes_location:**  Release release notes location URL

## Using

Here is an example YAML Fragment in the steps section of a build:

```yaml
    steps:
    - name: Create Object Configuration
      uses: snxd/deploy-github-create-action@v5
      with:
        console_version: '7.2.49'
        scripts_version: '3.11.0'
        solsta_client_id:  ${{ secrets.SOLSTA_CLIENT_ID }}
        solsta_client_secret:  ${{ secrets.SOLSTA_CLIENT_SECRET }}
        action_type: create
        object_type: product 
        target_product: My Product Name
        description:  Friendly description of My Product
```

## License
(C) 2022 Solid State Networks, LLC.  All Rights Reserved.
