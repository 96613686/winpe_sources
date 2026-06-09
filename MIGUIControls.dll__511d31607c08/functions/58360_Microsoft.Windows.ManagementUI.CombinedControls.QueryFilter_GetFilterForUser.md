# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForUser

- ea: `0x58360`
- end: `0x584b2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForUser`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x58700`

## callees

- `0x12ed0`
- `0x1cdb0`
- `0x1cef0`
- `0x33b40`
- `0x38840`
- `0x53f00`
- `0x58360`
- `0x9ff20`

## string_xrefs

- `0x583ef`: `SidFromUserName`
- `0x58413`: `SidFromUserName`
- `0x58475`: `Security[@UserID='`

## pseudocode

```c

```

## disassembly

```asm
0x58360  ldc.i4.1
0x58361  stloc.0
0x58362  ldstr    aEmptyuser// "EMPTYUSER"
0x58367  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5836c  stloc.1
0x5836d  ldarg.0
0x5836e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtUser
0x58373  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x58378  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5837d  brtrue   loc_584B0
0x58382  ldarg.0
0x58383  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtUser
0x58388  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x5838d  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::AllUserText
0x58392  ldc.i4.5
0x58393  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x58398  brfalse  loc_584B0
0x5839d  ldarg.0
0x5839e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtUser
0x583a3  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x583a8  callvirt instance string [mscorlib]System.String::Trim()
0x583ad  stloc.2
0x583ae  ldc.i4.0
0x583af  stloc.3
0x583b0  ldarg.0
0x583b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x583b6  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x583bb  stloc.s  4
0x583bd  ldloc.s  4
0x583bf  callvirt instance string [mscorlib]System.String::Trim()
0x583c4  stloc.s  4
0x583c6  ldloc.s  4
0x583c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x583cd  brtrue.s loc_583DD
0x583cf  ldloc.s  4
0x583d1  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::AllComputerText
0x583d6  call     bool [mscorlib]System.String::Equals(string, string)
0x583db  brfalse.s loc_583EA
0x583dd  ldarg.0
0x583de  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x583e3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x583e8  stloc.s  4
0x583ea  ldstr    aQueryfilter// "QueryFilter"
0x583ef  ldstr    aSidfromusernam// "SidFromUserName"
0x583f4  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(string className, string methodName)
0x583f9  ldarg.0
0x583fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtUser
0x583ff  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x58404  ldloc.s  4
0x58406  ldloca.s 3
0x58408  call     string SIDLookup::SidFromUserName(string inName, string computerName, bool& flagIsUser)
0x5840d  stloc.2
0x5840e  ldstr    aQueryfilter// "QueryFilter"
0x58413  ldstr    aSidfromusernam// "SidFromUserName"
0x58418  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(string className, string methodName)
0x5841d  ldloc.2
0x5841e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58423  brfalse.s loc_5843E
0x58425  ldc.i4.0
0x58426  stloc.0
0x58427  ldc.i4.1
0x58428  ldarg.0
0x58429  ldstr    aInvaliduserid// "InvalidUserId"
0x5842e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58433  ldc.i4.0
0x58434  ldc.i4.s 0x10
0x58436  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5843b  pop
0x5843c  br.s     loc_58458
0x5843e  ldloc.3
0x5843f  brtrue.s loc_58458
0x58441  ldc.i4.0
0x58442  stloc.0
0x58443  ldc.i4.1
0x58444  ldarg.0
0x58445  ldstr    aInvalidgroupid// "InvalidGroupId"
0x5844a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5844f  ldc.i4.0
0x58450  ldc.i4.s 0x10
0x58452  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x58457  pop
0x58458  ldloc.0
0x58459  brfalse.s loc_584B0
0x5845b  ldarg.1
0x5845c  ldind.ref
0x5845d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58462  brtrue.s loc_58472
0x58464  ldarg.1
0x58465  ldarg.1
0x58466  ldind.ref
0x58467  ldstr    aAnd// " and "
0x5846c  call     string [mscorlib]System.String::Concat(string, string)
0x58471  stind.ref
0x58472  ldarg.1
0x58473  ldarg.1
0x58474  ldind.ref
0x58475  ldstr    aSecurityUserid// "Security[@UserID='"
0x5847a  call     string [mscorlib]System.String::Concat(string, string)
0x5847f  stind.ref
0x58480  ldarg.1
0x58481  ldarg.1
0x58482  ldind.ref
0x58483  ldloc.2
0x58484  ldstr    asc_AD7C6// "']"
0x58489  call     string [mscorlib]System.String::Concat(string, string, string)
0x5848e  stind.ref
0x5848f  ldarg.0
0x58490  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x58495  brtrue.s loc_584B0
0x58497  ldarg.2
0x58498  ldind.ref
0x58499  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::User
0x5849e  ldloc.2
0x5849f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x584a4  brtrue.s loc_584A9
0x584a6  ldloc.2
0x584a7  br.s     loc_584AA
0x584a9  ldloc.1
0x584aa  ldc.i4.1
0x584ab  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::SetProperty(string propertyName, string value, bool simple)
0x584b0  ldloc.0
0x584b1  ret
```
