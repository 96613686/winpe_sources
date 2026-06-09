# Microsoft.SharePoint.Client.CompMgr::Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit.FindProductionCompSetPath

- ea: `0x17640`
- end: `0x176bd`
- name: `Microsoft.SharePoint.Client.CompMgr::Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit.FindProductionCompSetPath`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x17610`
- `0x17640`
- `0x17730`
- `0x17750`

## string_xrefs

- `0x176aa`: `FindProductionCompSetPath = `

## pseudocode

```c

```

## disassembly

```asm
0x17640  ldarg.0
0x17641  call     instance string Microsoft.SharePoint.Client.CompMgr::InstallPathWrapper()
0x17646  ldarg.0
0x17647  ldfld    string Microsoft.SharePoint.Client.CompMgr::appName
0x1764c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x17651  stloc.0
0x17652  ldloc.0
0x17653  ldstr    aProduction_0// "\\production"
0x17658  call     string [mscorlib]System.String::Concat(string, string)
0x1765d  stloc.0
0x1765e  ldloc.0
0x1765f  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [mscorlib]System.IO.Directory::EnumerateDirectories(string)
0x17664  stloc.1
0x17665  ldstr    asc_3EE4E// ""
0x1766a  stloc.2
0x1766b  ldloc.1
0x1766c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x17671  stloc.s  4
0x17673  br.s     loc_17692
0x17675  ldloc.s  4
0x17677  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1767c  stloc.3
0x1767d  ldloc.3
0x1767e  ldloc.2
0x1767f  call     int32 [mscorlib]System.String::Compare(string, string)
0x17684  ldc.i4.0
0x17685  ble.s    loc_17692
0x17687  ldarg.0
0x17688  ldloc.3
0x17689  call     instance bool Microsoft.SharePoint.Client.CompMgr::CheckFolderHasCompMgr(string folder)
0x1768e  brfalse.s loc_17692
0x17690  ldloc.3
0x17691  stloc.2
0x17692  ldloc.s  4
0x17694  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17699  brtrue.s loc_17675
0x1769b  leave.s  loc_176A9
0x1769d  ldloc.s  4
0x1769f  brfalse.s loc_176A8
0x176a1  ldloc.s  4
0x176a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x176a8  endfinally
0x176a9  ldarg.0
0x176aa  ldstr    aFindproduction// "FindProductionCompSetPath = "
0x176af  ldloc.2
0x176b0  call     string [mscorlib]System.String::Concat(string, string)
0x176b5  ldc.i4.3
0x176b6  call     instance void Microsoft.SharePoint.Client.CompMgr::LogWrapper(string s, valuetype [System]System.Diagnostics.TraceLevel level)
0x176bb  ldloc.2
0x176bc  ret
```
