# Microsoft.SharePoint.Client.CompMgr::Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit.Reload

- ea: `0x176e0`
- end: `0x17709`
- name: `Microsoft.SharePoint.Client.CompMgr::Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit.Reload`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x17750`

## string_xrefs

- `0x176fc`: `Loaded real CompMgr`

## pseudocode

```c

```

## disassembly

```asm
0x176e0  ldarg.0
0x176e1  ldflda   valuetype CompSet Microsoft.SharePoint.Client.CompMgr::csProduction
0x176e6  ldfld    class [mscorlib]System.Reflection.Assembly CompSet::compMgrAsm
0x176eb  ldsfld   string Microsoft.SharePoint.Client.CompMgrRoot::typeNameCompMgr
0x176f0  callvirt instance object [mscorlib]System.Reflection.Assembly::CreateInstance(string)
0x176f5  isinst   [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr
0x176fa  stloc.0
0x176fb  ldarg.0
0x176fc  ldstr    aLoadedRealComp// "Loaded real CompMgr"
0x17701  ldc.i4.3
0x17702  call     instance void Microsoft.SharePoint.Client.CompMgr::LogWrapper(string s, valuetype [System]System.Diagnostics.TraceLevel level)
0x17707  ldloc.0
0x17708  ret
```
