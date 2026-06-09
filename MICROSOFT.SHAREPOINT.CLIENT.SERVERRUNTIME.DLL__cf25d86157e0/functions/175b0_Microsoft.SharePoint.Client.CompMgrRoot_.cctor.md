# Microsoft.SharePoint.Client.CompMgrRoot::.cctor

- ea: `0x175b0`
- end: `0x175ef`
- name: `Microsoft.SharePoint.Client.CompMgrRoot::.cctor`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x175b0`: `SPComponent.ExpMgr`
- `0x175ba`: `SPComponent.CompMgr`

## pseudocode

```c

```

## disassembly

```asm
0x175b0  ldstr    aSpcomponentExp// "SPComponent.ExpMgr"
0x175b5  stsfld   string Microsoft.SharePoint.Client.CompMgrRoot::typeNameExpMgr
0x175ba  ldstr    aSpcomponentCom// "SPComponent.CompMgr"
0x175bf  stsfld   string Microsoft.SharePoint.Client.CompMgrRoot::typeNameCompMgr
0x175c4  ldstr    aProduction// "production"
0x175c9  stsfld   string Microsoft.SharePoint.Client.CompMgrRoot::defaultSetName
0x175ce  ldstr    aSharepoint// "SharePoint"
0x175d3  stsfld   string Microsoft.SharePoint.Client.CompMgrRoot::appName
0x175d8  ldnull
0x175d9  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x175de  ldnull
0x175df  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.IExpMgr Microsoft.SharePoint.Client.CompMgrRoot::expMgr
0x175e4  newobj   instance void [mscorlib]System.Object::.ctor()
0x175e9  stsfld   object Microsoft.SharePoint.Client.CompMgrRoot::lockObject
0x175ee  ret
```
