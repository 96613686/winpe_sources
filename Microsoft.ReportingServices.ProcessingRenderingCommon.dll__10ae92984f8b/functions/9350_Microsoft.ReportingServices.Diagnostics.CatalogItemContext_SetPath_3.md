# Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath_3

- ea: `0x9350`
- end: `0x9432`
- name: `Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath_3`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x9310`
- `0x9340`

## callees

- `0x3a20`
- `0x7810`
- `0x8270`
- `0x8310`
- `0x8350`
- `0x83a0`
- `0x8cd0`
- `0x8e00`
- `0x8e10`
- `0x8e80`
- `0x8ea0`
- `0x9350`

## pseudocode

```c

```

## disassembly

```asm
0x9350  ldarg.1
0x9351  stloc.0
0x9352  ldarg.1
0x9353  stloc.1
0x9354  ldnull
0x9355  stloc.2
0x9356  ldarg.3
0x9357  ldc.i4.8
0x9358  and
0x9359  ldc.i4.8
0x935a  bne.un.s loc_93AE
0x935c  ldnull
0x935d  stloc.s  5
0x935f  ldnull
0x9360  stloc.s  6
0x9362  ldloc.1
0x9363  ldloca.s 2
0x9365  ldloca.s 4
0x9367  call     bool Microsoft.ReportingServices.Diagnostics.ItemPathBase::ParseInternalItemPathParts(string path, [out] string& editSessionID, [out] string& itemPath)
0x936c  brfalse.s loc_93AE
0x936e  ldloc.s  4
0x9370  stloc.1
0x9371  ldloc.2
0x9372  starg.s  2
0x9374  ldloc.1
0x9375  ldloca.s 5
0x9377  ldloca.s 6
0x9379  call     void Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::SplitPath(string itemPath, [out] string& itemName, [out] string& parentPath)
0x937e  ldloc.s  6
0x9380  ldsfld   string Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::PathSeparatorString
0x9385  call     int32 Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare(string a, string b)
0x938a  brfalse.s loc_9395
0x938c  ldloc.s  6
0x938e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9393  brfalse.s loc_93AE
0x9395  ldarg.3
0x9396  ldc.i4.1
0x9397  and
0x9398  ldc.i4.1
0x9399  bne.un.s loc_93A8
0x939b  ldloc.s  5
0x939d  ldstr    aName// "name"
0x93a2  call     string Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateAndTrimItemName(string name, string parameterName)
0x93a7  pop
0x93a8  ldarg.3
0x93a9  ldc.i4.s 0xFE
0x93ab  and
0x93ac  starg.s  3
0x93ae  ldarg.3
0x93af  ldc.i4.2
0x93b0  and
0x93b1  ldc.i4.2
0x93b2  ceq
0x93b4  stloc.3
0x93b5  ldarg.3
0x93b6  ldc.i4.1
0x93b7  and
0x93b8  ldc.i4.1
0x93b9  bne.un.s loc_93CD
0x93bb  ldloc.3
0x93bc  ldc.i4.0
0x93bd  ceq
0x93bf  stloc.s  7
0x93c1  ldloc.1
0x93c2  ldloc.s  7
0x93c4  call     bool Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ValidateItemPath(string path, bool isInternal)
0x93c9  brtrue.s loc_93CD
0x93cb  ldc.i4.0
0x93cc  ret
0x93cd  ldloc.3
0x93ce  brfalse.s loc_93D7
0x93d0  ldloc.1
0x93d1  call     string Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::ConvertPathToInternal(string externalPath)
0x93d6  stloc.1
0x93d7  ldarg.3
0x93d8  ldc.i4.4
0x93d9  and
0x93da  ldc.i4.4
0x93db  bne.un.s loc_93F2
0x93dd  ldarg.0
0x93de  ldfld    class Microsoft.ReportingServices.Diagnostics.IPathTranslator class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_PathTranslator
0x93e3  brfalse.s loc_93F2
0x93e5  ldarg.0
0x93e6  ldfld    class Microsoft.ReportingServices.Diagnostics.IPathTranslator class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_PathTranslator
0x93eb  ldloc.1
0x93ec  callvirt instance string Microsoft.ReportingServices.Diagnostics.IPathTranslator::PathToInternal(string source)
0x93f1  stloc.1
0x93f2  ldarg.3
0x93f3  ldc.i4.s 0x10
0x93f5  and
0x93f6  ldc.i4.s 0x10
0x93f8  bne.un.s loc_9416
0x93fa  ldarg.0
0x93fb  ldloc.1
0x93fc  ldarg.2
0x93fd  call     class Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Diagnostics.ExternalItemPath::CreateWithoutChecks(string value, string editSessionID)
0x9402  stfld    var<u1> class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_ItemPath
0x9407  ldarg.0
0x9408  ldloc.0
0x9409  ldarg.2
0x940a  call     class Microsoft.ReportingServices.Diagnostics.ExternalOriginalItemPath Microsoft.ReportingServices.Diagnostics.ExternalOriginalItemPath::CreateWithoutChecks(string value, string editSessionID)
0x940f  stfld    var<u1> class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_OriginalItemPath
0x9414  br.s     loc_9430
0x9416  ldarg.0
0x9417  ldloc.1
0x9418  ldarg.2
0x9419  newobj   instance void Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string value, string editSessionID)
0x941e  stfld    var<u1> class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_ItemPath
0x9423  ldarg.0
0x9424  ldloc.0
0x9425  ldarg.2
0x9426  newobj   instance void Microsoft.ReportingServices.Diagnostics.ExternalOriginalItemPath::.ctor(string value, string editSessionID)
0x942b  stfld    var<u1> class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_OriginalItemPath
0x9430  ldc.i4.1
0x9431  ret
```
