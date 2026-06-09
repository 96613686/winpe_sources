# Microsoft.SharePoint.Client.Rest.FilteredEdmModelForMetadataDocument::IsEdmComplexTypeExcluded

- ea: `0x1d040`
- end: `0x1d083`
- name: `Microsoft.SharePoint.Client.Rest.FilteredEdmModelForMetadataDocument::IsEdmComplexTypeExcluded`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1d250`

## callees

- `0xe010`
- `0x152f0`
- `0x1d040`

## string_xrefs

- `0x1d064`: `ComplexType {0} is excluded`

## pseudocode

```c

```

## disassembly

```asm
0x1d040  ldarg.0
0x1d041  ldfld    class [System]System.Collections.Generic.ISet`1<string> Microsoft.SharePoint.Client.Rest.FilteredEdmModelForMetadataDocument::m_excludedTypeFullNames
0x1d046  ldarg.1
0x1d047  call     string [Microsoft.Data.Edm]Microsoft.Data.Edm.ExtensionMethods::FullName(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmSchemaElement)
0x1d04c  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x1d051  brfalse.s loc_1D081
0x1d053  ldarg.0
0x1d054  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.Rest.FilteredEdmModelForMetadataDocument::m_proxyContext
0x1d059  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1d05e  ldc.i4   0x65185F
0x1d063  ldc.i4.4
0x1d064  ldstr    aComplextype0Is// "ComplexType {0} is excluded"
0x1d069  ldc.i4.1
0x1d06a  newarr   [mscorlib]System.Object
0x1d06f  stloc.0
0x1d070  ldloc.0
0x1d071  ldc.i4.0
0x1d072  ldarg.1
0x1d073  call     string [Microsoft.Data.Edm]Microsoft.Data.Edm.ExtensionMethods::FullName(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmSchemaElement)
0x1d078  stelem.ref
0x1d079  ldloc.0
0x1d07a  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1d07f  ldc.i4.1
0x1d080  ret
0x1d081  ldc.i4.0
0x1d082  ret
```
