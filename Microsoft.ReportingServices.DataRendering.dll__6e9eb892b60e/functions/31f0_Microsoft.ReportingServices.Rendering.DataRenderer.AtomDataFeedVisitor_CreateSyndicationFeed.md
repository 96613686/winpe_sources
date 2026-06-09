# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateSyndicationFeed

- ea: `0x31f0`
- end: `0x3248`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateSyndicationFeed`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x1e90`
- `0x2030`

## string_xrefs

- `0x3200`: `http://www.w3.org/2000/xmlns/`
- `0x3226`: `http://www.w3.org/2000/xmlns/`
- `0x3217`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x323d`: `http://schemas.microsoft.com/ado/2007/08/dataservices/metadata`

## pseudocode

```c

```

## disassembly

```asm
0x31f0  ldarg.0
0x31f1  newobj   instance void [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed::.ctor()
0x31f6  stfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationFeed
0x31fb  ldstr    aD// "d"
0x3200  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x3205  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x320a  stloc.0
0x320b  ldarg.0
0x320c  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationFeed
0x3211  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, string> [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed::get_AttributeExtensions()
0x3216  ldloc.0
0x3217  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/ado/2007/0"...
0x321c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, string>::Add(var<u1>, !!T0)
0x3221  ldstr    aM// "m"
0x3226  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x322b  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x3230  stloc.0
0x3231  ldarg.0
0x3232  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationFeed
0x3237  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, string> [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed::get_AttributeExtensions()
0x323c  ldloc.0
0x323d  ldstr    aHttpSchemasMic_5// "http://schemas.microsoft.com/ado/2007/0"...
0x3242  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, string>::Add(var<u1>, !!T0)
0x3247  ret
```
