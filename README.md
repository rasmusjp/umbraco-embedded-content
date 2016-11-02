# Embedded Content for Umbraco

TODO: Add description and awesome gif

## Installation

### Option 1: NuGet

Run the following command in the [Package Manager Console](https://docs.nuget.org/docs/start-here/using-the-package-manager-console)

```powershell
PM> Install-Package DisPlay.Umbraco.EmbeddedContent
```

### Option 2: Our Umbraco

### Option 3: From source

```bat
> npm i
> npm run build
```

The output will be located in `dist/`

## Usage

TODO: Add code example

```csharp
```

## Creating a custom label resolver
```javascript
angular.module('umbraco')
.run(['DisPlay.Umbraco.EmbeddedContent.LabelResolvers', 'formResource', (labelResolvers, formResource) => {
  labelResolvers['UmbracoForms.FormPicker'] = (property, cacheService) => {
    const fromCache = cacheService.getOrAdd('UmbracoForms.FormPicker', property.value, () => {
      return formResource.getByGuid(property.value);
    });

    return fromCache ? fromCache.data.name : null;
  }
}]);
```

## Contributing

Anyone can help make this project better - check out our [Contributing guide](CONTRIBUTING.md)

## Authors

 * [Rasmus John Pedersen](https://www.github.com/rasmusjp)

## License

Copyright © 2016 DIS/PLAY A/S

Embedded Content is released under the [MIT License](LICENSE)
