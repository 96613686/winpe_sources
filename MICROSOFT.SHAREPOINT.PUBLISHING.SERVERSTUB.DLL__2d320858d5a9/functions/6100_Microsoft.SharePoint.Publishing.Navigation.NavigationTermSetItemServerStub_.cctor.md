# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::.cctor

- ea: `0x6100`
- end: `0x6172`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::.cctor`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x6111`: `IsReadOnly`
- `0x6119`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x6100  ldc.i4.4
0x6101  newarr   [mscorlib]System.String
0x6106  stloc.0
0x6107  ldloc.0
0x6108  ldc.i4.0
0x6109  ldstr    aId// "Id"
0x610e  stelem.ref
0x610f  ldloc.0
0x6110  ldc.i4.1
0x6111  ldstr    aIsreadonly// "IsReadOnly"
0x6116  stelem.ref
0x6117  ldloc.0
0x6118  ldc.i4.2
0x6119  ldstr    aLinktype// "LinkType"
0x611e  stelem.ref
0x611f  ldloc.0
0x6120  ldc.i4.3
0x6121  ldstr    aTaxonomyname// "TaxonomyName"
0x6126  stelem.ref
0x6127  ldloc.0
0x6128  stsfld   string[] Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::s_valueProperties
0x612d  ldc.i4.5
0x612e  newarr   [mscorlib]System.String
0x6133  stloc.1
0x6134  ldloc.1
0x6135  ldc.i4.0
0x6136  ldstr    aCatalogtargetu// "CatalogTargetUrlForChildTerms"
0x613b  stelem.ref
0x613c  ldloc.1
0x613d  ldc.i4.1
0x613e  ldstr    aTargeturlforch// "TargetUrlForChildTerms"
0x6143  stelem.ref
0x6144  ldloc.1
0x6145  ldc.i4.2
0x6146  ldstr    aTerms// "Terms"
0x614b  stelem.ref
0x614c  ldloc.1
0x614d  ldc.i4.3
0x614e  ldstr    aTitle// "Title"
0x6153  stelem.ref
0x6154  ldloc.1
0x6155  ldc.i4.4
0x6156  ldstr    aView// "View"
0x615b  stelem.ref
0x615c  ldloc.1
0x615d  stsfld   string[] Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::s_refProperties
0x6162  ldstr    aF99351d7E3f341// "{f99351d7-e3f3-4185-a0ca-d0426ff83fde}"
0x6167  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x616c  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::s_targetTypeId
0x6171  ret
```
