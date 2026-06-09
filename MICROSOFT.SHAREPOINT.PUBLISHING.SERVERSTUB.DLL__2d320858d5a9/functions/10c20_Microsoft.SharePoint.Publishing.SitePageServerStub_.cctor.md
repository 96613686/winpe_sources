# Microsoft.SharePoint.Publishing.SitePageServerStub::.cctor

- ea: `0x10c20`
- end: `0x10c7d`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::.cctor`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x10c39`: `CanvasJson1`
- `0x10c61`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x10c20  ldc.i4.4
0x10c21  newarr   [mscorlib]System.String
0x10c26  stloc.0
0x10c27  ldloc.0
0x10c28  ldc.i4.0
0x10c29  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x10c2e  stelem.ref
0x10c2f  ldloc.0
0x10c30  ldc.i4.1
0x10c31  ldstr    aCanvascontent1// "CanvasContent1"
0x10c36  stelem.ref
0x10c37  ldloc.0
0x10c38  ldc.i4.2
0x10c39  ldstr    aCanvasjson1// "CanvasJson1"
0x10c3e  stelem.ref
0x10c3f  ldloc.0
0x10c40  ldc.i4.3
0x10c41  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x10c46  stelem.ref
0x10c47  ldloc.0
0x10c48  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageServerStub::s_valueProperties
0x10c4d  ldc.i4.0
0x10c4e  newarr   [mscorlib]System.String
0x10c53  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageServerStub::s_refProperties
0x10c58  ldc.i4.1
0x10c59  newarr   [mscorlib]System.String
0x10c5e  stloc.1
0x10c5f  ldloc.1
0x10c60  ldc.i4.0
0x10c61  ldstr    aCanvasjson1// "CanvasJson1"
0x10c66  stelem.ref
0x10c67  ldloc.1
0x10c68  stsfld   string[] Microsoft.SharePoint.Publishing.SitePageServerStub::s_excludeFromDefaultRetrieveProperties
0x10c6d  ldstr    aF03ba8fbD55e47// "{f03ba8fb-d55e-4745-8eb1-d6ade479311b}"
0x10c72  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x10c77  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.SitePageServerStub::s_targetTypeId
0x10c7c  ret
```
