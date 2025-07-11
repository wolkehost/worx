

# Getting Started

Worx is a framework for building APIs in Go with support for TMF (Telecom Management Forum) standards. Follow these steps to get started:

### 1. Install Worx:

```bash
go get -u github.com/wolkehost/worx
```

### 2. Initialize Your Application:

Create a new Worx application:

```go
package main

import (
	"github.com/wolkehost/worx"
	"github.com/wolkehost/worx"
)

func main() {
	app := worx.New("/api", "Product Catalog API")
}
```

### 3. Define Your API Endpoint:

Create a new API endpoint using the `Router` function:

```go
product := worx.Router[Product, ProductResponse](app, "/products")
```



### 4. Handle Requests:

Define your request handling logic using the `HandleCreate`, `HandleRead`, `HandleUpdate`, and `HandleList` methods:

```go
product.HandleCreate("", func(product Product, params *router.RequestParams) (*router.ProcessorError, *ProductResponse) {
	return nil, &ProductResponse{
		Product:  product,
		BaseType: nil,
		Url:      nil,
	}
})
```

### 5. Run Your Application:

Start your Worx application and listen on 8000 default port:

```go
  app.Run()

```

Now, your Worx application is ready to handle TMF API requests.

--- 

Make sure to include the route before defining the handlers to ensure that the routes are properly registered in your application. Happy coding