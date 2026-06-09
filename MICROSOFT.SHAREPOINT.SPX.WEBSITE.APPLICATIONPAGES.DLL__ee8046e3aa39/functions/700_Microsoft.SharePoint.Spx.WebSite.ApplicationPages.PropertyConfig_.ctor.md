# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::.ctor

- ea: `0x700`
- end: `0x761`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::.ctor`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7b0`

## callees

- `0x700`

## string_xrefs

- `0x725`: `/WH/Editor/XML/PropertySizes.xml`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldarg.0
0x701  call     instance void [mscorlib]System.Object::.ctor()
0x706  ldarg.0
0x707  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x70c  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::propertyValues
0x711  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x716  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x71b  ldstr    asc_20240// "/"
0x720  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0x725  ldstr    aWhEditorXmlPro// "/WH/Editor/XML/PropertySizes.xml"
0x72a  call     string [mscorlib]System.String::Concat(string, string, string)
0x72f  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x734  stloc.0
0x735  ldloc.0
0x736  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(string)
0x73b  stloc.1
0x73c  ldloc.1
0x73d  ldc.i4.0
0x73e  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x743  ldarg.0
0x744  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PropertyConfig::propertyValues
0x749  ldloc.1
0x74a  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x74f  leave.s  loc_75B
0x751  ldloc.1
0x752  brfalse.s loc_75A
0x754  ldloc.1
0x755  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x75a  endfinally
0x75b  leave.s  loc_760
0x75d  pop
0x75e  leave.s  loc_760
0x760  ret
```
