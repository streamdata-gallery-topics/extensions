---
swagger: "2.0"
x-collection-name: Watchful
x-complete: 0
info:
  title: Watchful Install Extension
  description: ""
  version: 1.0.0
host: watchful.li
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /extensions:
    get:
      summary: Get A List Extensions
      description: Returns a list Extensions
      operationId: getExtensions
      x-api-path-slug: extensions-get
      parameters:
      - in: query
        name: ext_name
        description: Do a LIKE search, you can also use %
      - in: query
        name: ext_prefix
        description: Do a LIKE search, you can also use %
      - in: query
        name: fields
        description: 'Fields to return separate by comas: name,id'
      - in: query
        name: limit
        description: Number of object to return (max 100, default 25)
      - in: query
        name: limitstart
        description: Start of the return (default 0)
      - in: query
        name: order
        description: ORDER by this field separete by comas
      - in: query
        name: siteids
        description: List of sites id separated by comma
      - in: query
        name: version
        description: Do a LIKE search, you can also use %
      - in: query
        name: vUpdate
        description: update available for this extension
      responses:
        200:
          description: OK
      tags:
      - Extensions
  /extensions/metadata:
    get:
      summary: Get The List Of Fields
      description: Returns a list of fields
      operationId: getFieldsExtensions
      x-api-path-slug: extensionsmetadata-get
      responses:
        200:
          description: OK
      tags:
      - Extensions
      - Metadata
  /extensions/{id}/ignore:
    post:
      summary: Set 'ignore Updates' For A Given Extension / Site_id
      description: Set 'ignore updates' for a given extension / site_id
      operationId: ignoreExtensionUpdate
      x-api-path-slug: extensionsidignore-post
      parameters:
      - in: path
        name: id
        description: ID of the extension
      responses:
        200:
          description: OK
      tags:
      - Extensions
      - Id
      - Ignore
  /extensions/{id}/unignore:
    post:
      summary: Remove 'ignore Updates' For A Given Extension
      description: Remove 'ignore updates' for a given extension
      operationId: unignoreExtensionUpdate
      x-api-path-slug: extensionsidunignore-post
      parameters:
      - in: path
        name: id
        description: ID of the extension
      responses:
        200:
          description: OK
      tags:
      - Extensions
      - Id
      - Unignore
  /extensions/{id}/update:
    post:
      summary: Update The Extension On The Remote Site
      description: Update the extension on the remote site
      operationId: updateExtension
      x-api-path-slug: extensionsidupdate-post
      parameters:
      - in: path
        name: id
        description: ID of the extension
      responses:
        200:
          description: OK
      tags:
      - Extensions
      - Id
      - Update
  /sites/{id}/extensions:
    get:
      summary: Get Extensions For A Site
      description: Get extensions for a site
      operationId: sites.id.extensions.get
      x-api-path-slug: sitesidextensions-get
      parameters:
      - in: query
        name: fields
        description: 'Fields to return separate by comas: name,id'
      - in: path
        name: id
        description: ID of the website
      - in: query
        name: limit
        description: Number of object to return (max 100, default 25)
      - in: query
        name: limitstart
        description: Start of the return (default 0)
      - in: query
        name: order
        description: ORDER by this field
      responses:
        200:
          description: OK
      tags:
      - Sites
      - Id
      - Extensions
    post:
      summary: Install Extension
      description: ""
      operationId: installExtension
      x-api-path-slug: sitesidextensions-post
      parameters:
      - in: path
        name: id
        description: ID of the website
      - in: query
        name: url
        description: URL to install the extension from
      responses:
        200:
          description: OK
      tags:
      - Sites
      - Id
      - Extensions
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---