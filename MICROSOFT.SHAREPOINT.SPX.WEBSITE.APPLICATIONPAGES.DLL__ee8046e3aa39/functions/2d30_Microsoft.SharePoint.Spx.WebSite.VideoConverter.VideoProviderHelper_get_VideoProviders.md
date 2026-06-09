# Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::get_VideoProviders

- ea: `0x2d30`
- end: `0x2d91`
- name: `Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::get_VideoProviders`
- size: `97`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3240`
- `0x3280`
- `0x32b0`
- `0x3320`

## callees

- `0x2d30`
- `0x3120`

## string_xrefs

- `0x2d51`: `/wh/Editor/VideoProvidersB2.xml`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldsfld   class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider[] Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::videoProviders
0x2d35  brtrue.s loc_2D8B
0x2d37  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x2d3c  stloc.0
0x2d3d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d42  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x2d47  ldstr    asc_20240// "/"
0x2d4c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0x2d51  ldstr    aWhEditorVideop// "/wh/Editor/VideoProvidersB2.xml"
0x2d56  call     string [mscorlib]System.String::Concat(string, string, string)
0x2d5b  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x2d60  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(string)
0x2d65  stloc.1
0x2d66  ldloc.1
0x2d67  ldc.i4.0
0x2d68  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x2d6d  ldloc.0
0x2d6e  ldloc.1
0x2d6f  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x2d74  leave.s  loc_2D80
0x2d76  ldloc.1
0x2d77  brfalse.s loc_2D7F
0x2d79  ldloc.1
0x2d7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d7f  endfinally
0x2d80  ldloc.0
0x2d81  call     class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider[] Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::ReadXmlVideoProviders(class [System.Xml]System.Xml.XmlDocument providersDocument)
0x2d86  stsfld   class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider[] Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::videoProviders
0x2d8b  ldsfld   class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider[] Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::videoProviders
0x2d90  ret
```
