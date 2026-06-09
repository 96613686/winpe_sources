# Microsoft.SharePoint.Utilities.Mime.MtomGlobals::.cctor

- ea: `0x2c360`
- end: `0x2c429`
- name: `Microsoft.SharePoint.Utilities.Mime.MtomGlobals::.cctor`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x2c3c4`: `xop+xml`
- `0x2c3ce`: `application/xop+xml`
- `0x2c40a`: `http://www.w3.org/2004/06/xmlmime`
- `0x2c414`: `http://www.w3.org/2005/05/xmlmime`

## pseudocode

```c

```

## disassembly

```asm
0x2c360  ldstr    aInclude// "Include"
0x2c365  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopIncludeLocalName
0x2c36a  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2004/08/xop/include"
0x2c36f  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopIncludeNamespace
0x2c374  ldstr    aXop// "xop"
0x2c379  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopIncludePrefix
0x2c37e  ldstr    aHref// "href"
0x2c383  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopIncludeHrefLocalName
0x2c388  ldsfld   string [mscorlib]System.String::Empty
0x2c38d  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopIncludeHrefNamespace
0x2c392  ldstr    aMultipart// "multipart"
0x2c397  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::MediaType
0x2c39c  ldstr    aRelated// "related"
0x2c3a1  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::MediaSubtype
0x2c3a6  ldstr    aBoundary// "boundary"
0x2c3ab  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::BoundaryParam
0x2c3b0  ldstr    aType// "type"
0x2c3b5  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::TypeParam
0x2c3ba  ldstr    aApplication// "application"
0x2c3bf  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopMediaType
0x2c3c4  ldstr    aXopXml// "xop+xml"
0x2c3c9  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopMediaSubtype
0x2c3ce  ldstr    aApplicationXop// "application/xop+xml"
0x2c3d3  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::XopType
0x2c3d8  ldstr    aStart// "start"
0x2c3dd  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::StartParam
0x2c3e2  ldstr    aStartInfo// "start-info"
0x2c3e7  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::StartInfoParam
0x2c3ec  ldstr    aAction// "action"
0x2c3f1  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::ActionParam
0x2c3f6  ldstr    aCharset// "charset"
0x2c3fb  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::CharsetParam
0x2c400  ldstr    aContenttype// "contentType"
0x2c405  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::MimeContentTypeLocalName
0x2c40a  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2004/06/xmlmime"
0x2c40f  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::MimeContentTypeNamespace200406
0x2c414  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2005/05/xmlmime"
0x2c419  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::MimeContentTypeNamespace200505
0x2c41e  ldstr    aApplicationOct// "application/octet-stream"
0x2c423  stsfld   string Microsoft.SharePoint.Utilities.Mime.MtomGlobals::DefaultContentTypeForBinary
0x2c428  ret
```
