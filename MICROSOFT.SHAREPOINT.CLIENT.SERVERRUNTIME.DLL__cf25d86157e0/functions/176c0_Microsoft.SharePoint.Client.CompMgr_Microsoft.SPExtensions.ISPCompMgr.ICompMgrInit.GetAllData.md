# Microsoft.SharePoint.Client.CompMgr::Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit.GetAllData

- ea: `0x176c0`
- end: `0x176e0`
- name: `Microsoft.SharePoint.Client.CompMgr::Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit.GetAllData`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x17750`
- `0x17780`

## string_xrefs

- `0x176d3`: `Built initial compset`

## pseudocode

```c

```

## disassembly

```asm
0x176c0  ldarg.0
0x176c1  ldarg.0
0x176c2  ldsfld   string Microsoft.SharePoint.Client.CompMgrRoot::defaultSetName
0x176c7  ldarg.1
0x176c8  call     instance valuetype CompSet Microsoft.SharePoint.Client.CompMgr::BuildCompSet(string name, string folder)
0x176cd  stfld    valuetype CompSet Microsoft.SharePoint.Client.CompMgr::csProduction
0x176d2  ldarg.0
0x176d3  ldstr    aBuiltInitialCo// "Built initial compset"
0x176d8  ldc.i4.3
0x176d9  call     instance void Microsoft.SharePoint.Client.CompMgr::LogWrapper(string s, valuetype [System]System.Diagnostics.TraceLevel level)
0x176de  ldc.i4.1
0x176df  ret
```
