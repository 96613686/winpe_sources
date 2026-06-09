# Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::InitializeAccess

- ea: `0x15330`
- end: `0x15c6a`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::InitializeAccess`
- size: `2362`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x15ed0`

## callees

- `0x12ed0`
- `0x15330`
- `0x15c70`
- `0x35250`

## string_xrefs

- `0x15451`: `GeneralRead`
- `0x15517`: `GenericRead`
- `0x1557e`: `GenericWrite`
- `0x1563b`: `FileReadData`
- `0x15699`: `FileReadAttr`
- `0x156f6`: `FileReadEA`
- `0x15754`: `FileWriteData`
- `0x15814`: `FileWriteAttr`
- `0x15873`: `FileWriteEA`
- `0x158d2`: `FileDeleteChild`
- `0x15934`: `StandardDelete`
- `0x15996`: `StandardReadControl`
- `0x159f8`: `StandardWriteDac`
- `0x15a5a`: `StandardWriteOwner`

## pseudocode

```c

```

## disassembly

```asm
0x15330  ldarg.0
0x15331  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15336  brtrue   loc_15C69
0x1533b  ldarg.0
0x1533c  ldc.i4.s 0x17
0x1533e  newarr   Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15343  stfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15348  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1534d  stloc.0
0x1534e  ldarg.0
0x1534f  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15354  ldc.i4.0
0x15355  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1535a  ldloc.0
0x1535b  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x15360  ldarg.0
0x15361  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15366  ldc.i4.0
0x15367  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1536c  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.StandardAccessMasksEx_::FILE_GENERIC_ALL
0x15371  conv.u4
0x15372  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x15377  ldarg.0
0x15378  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1537d  ldc.i4.0
0x1537e  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15383  ldstr    aGenericall// "GenericAll"
0x15388  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x1538d  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x15392  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x15397  ldarg.0
0x15398  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1539d  ldc.i4.0
0x1539e  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x153a3  ldc.i4   0x30000
0x153a8  conv.i8
0x153a9  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::INHERIT_FULL
0x153ae  or
0x153af  conv.u4
0x153b0  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x153b5  ldarg.0
0x153b6  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x153bb  ldc.i4.1
0x153bc  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x153c1  ldloc.0
0x153c2  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x153c7  ldarg.0
0x153c8  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x153cd  ldc.i4.1
0x153ce  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x153d3  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.StandardAccessMasksEx_::FILE_GENERAL_MODIFY
0x153d8  conv.u4
0x153d9  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x153de  ldarg.0
0x153df  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x153e4  ldc.i4.1
0x153e5  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x153ea  ldstr    aGeneralmodify// "GeneralModify"
0x153ef  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x153f4  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x153f9  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x153fe  ldarg.0
0x153ff  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15404  ldc.i4.1
0x15405  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1540a  ldc.i4   0x20000
0x1540f  conv.i8
0x15410  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::INHERIT_FULL
0x15415  or
0x15416  conv.u4
0x15417  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x1541c  ldarg.0
0x1541d  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15422  ldc.i4.2
0x15423  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15428  ldloc.0
0x15429  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x1542e  ldarg.0
0x1542f  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15434  ldc.i4.2
0x15435  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1543a  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.StandardAccessMasksEx_::FILE_GENERAL_READ_EX
0x1543f  conv.u4
0x15440  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x15445  ldarg.0
0x15446  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1544b  ldc.i4.2
0x1544c  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15451  ldstr    aGeneralread// "GeneralRead"
0x15456  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x1545b  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x15460  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x15465  ldarg.0
0x15466  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1546b  ldc.i4.2
0x1546c  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15471  ldc.i4   0x20000
0x15476  conv.i8
0x15477  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::INHERIT_FULL
0x1547c  or
0x1547d  conv.u4
0x1547e  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x15483  ldarg.0
0x15484  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15489  ldc.i4.3
0x1548a  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1548f  ldloc.0
0x15490  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x15495  ldarg.0
0x15496  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1549b  ldc.i4.3
0x1549c  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x154a1  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.StandardAccessMasksEx_::FILE_GENERAL_READ_EX
0x154a6  conv.u4
0x154a7  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x154ac  ldarg.0
0x154ad  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x154b2  ldc.i4.3
0x154b3  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x154b8  ldstr    aGenerallist// "GeneralList"
0x154bd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x154c2  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x154c7  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x154cc  ldarg.0
0x154cd  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x154d2  ldc.i4.3
0x154d3  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x154d8  ldc.i4   0x40002
0x154dd  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x154e2  ldarg.0
0x154e3  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x154e8  ldc.i4.4
0x154e9  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x154ee  ldloc.0
0x154ef  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x154f4  ldarg.0
0x154f5  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x154fa  ldc.i4.4
0x154fb  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15500  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.StandardAccessMasksEx_::FILE_GENERIC_READ
0x15505  conv.u4
0x15506  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x1550b  ldarg.0
0x1550c  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15511  ldc.i4.4
0x15512  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15517  ldstr    aGenericread// "GenericRead"
0x1551c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x15521  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x15526  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x1552b  ldarg.0
0x1552c  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15531  ldc.i4.4
0x15532  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15537  ldc.i4   0x20000
0x1553c  conv.i8
0x1553d  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::INHERIT_FULL
0x15542  or
0x15543  conv.u4
0x15544  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x15549  ldarg.0
0x1554a  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1554f  ldc.i4.5
0x15550  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15555  ldloc.0
0x15556  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x1555b  ldarg.0
0x1555c  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15561  ldc.i4.5
0x15562  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15567  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.StandardAccessMasksEx_::FILE_GENERIC_WRITE
0x1556c  conv.u4
0x1556d  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x15572  ldarg.0
0x15573  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15578  ldc.i4.5
0x15579  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1557e  ldstr    aGenericwrite// "GenericWrite"
0x15583  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x15588  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x1558d  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x15592  ldarg.0
0x15593  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15598  ldc.i4.5
0x15599  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1559e  ldc.i4   0x20000
0x155a3  conv.i8
0x155a4  ldsfld   int64 Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::INHERIT_FULL
0x155a9  or
0x155aa  conv.u4
0x155ab  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x155b0  ldarg.0
0x155b1  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x155b6  ldc.i4.6
0x155b7  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x155bc  ldloc.0
0x155bd  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x155c2  ldarg.0
0x155c3  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x155c8  ldc.i4.6
0x155c9  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x155ce  ldc.i4.s 0x20
0x155d0  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x155d5  ldarg.0
0x155d6  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x155db  ldc.i4.6
0x155dc  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x155e1  ldstr    aFileexecute// "FileExecute"
0x155e6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x155eb  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x155f0  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x155f5  ldarg.0
0x155f6  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x155fb  ldc.i4.6
0x155fc  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15601  ldc.i4   0x10000
0x15606  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x1560b  ldarg.0
0x1560c  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15611  ldc.i4.7
0x15612  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15617  ldloc.0
0x15618  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x1561d  ldarg.0
0x1561e  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15623  ldc.i4.7
0x15624  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15629  ldc.i4.1
0x1562a  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x1562f  ldarg.0
0x15630  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15635  ldc.i4.7
0x15636  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1563b  ldstr    aFilereaddata// "FileReadData"
0x15640  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x15645  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x1564a  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x1564f  ldarg.0
0x15650  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15655  ldc.i4.7
0x15656  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1565b  ldc.i4   0x10000
0x15660  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x15665  ldarg.0
0x15666  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1566b  ldc.i4.8
0x1566c  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15671  ldloc.0
0x15672  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x15677  ldarg.0
0x15678  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x1567d  ldc.i4.8
0x1567e  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15683  ldc.i4   0x80
0x15688  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x1568d  ldarg.0
0x1568e  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15693  ldc.i4.8
0x15694  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15699  ldstr    aFilereadattr// "FileReadAttr"
0x1569e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x156a3  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x156a8  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x156ad  ldarg.0
0x156ae  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x156b3  ldc.i4.8
0x156b4  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x156b9  ldc.i4   0x10000
0x156be  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x156c3  ldarg.0
0x156c4  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x156c9  ldc.i4.s 9
0x156cb  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x156d0  ldloc.0
0x156d1  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pguid
0x156d6  ldarg.0
0x156d7  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x156dc  ldc.i4.s 9
0x156de  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x156e3  ldc.i4.8
0x156e4  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::mask
0x156e9  ldarg.0
0x156ea  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x156ef  ldc.i4.s 9
0x156f1  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x156f6  ldstr    aFilereadea// "FileReadEA"
0x156fb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x15700  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x15705  stfld    native int Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::pszName
0x1570a  ldarg.0
0x1570b  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15710  ldc.i4.s 9
0x15712  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x15717  ldc.i4   0x10000
0x1571c  stfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS::dwFlags
0x15721  ldarg.0
0x15722  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS[] Microsoft.Windows.ManagementUI.CombinedControls.NtfsSecurityHelper::access
0x15727  ldc.i4.s 0xA
0x15729  ldelema  Microsoft.Windows.ManagementUI.CombinedControls.SI_ACCESS
0x1572e  ldloc.0
  ... truncated ...
```
