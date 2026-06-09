# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::DetermineTechCenterHelpSource

- ea: `0x34630`
- end: `0x34745`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::DetermineTechCenterHelpSource`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x34750`

## callees

- `0x345d0`
- `0x34630`

## string_xrefs

- `0x34648`: `MicrosoftRedirectionProgramCommandLineParameters`
- `0x3471d`: `http://go.microsoft.com/fwlink/events.asp`
- `0x34733`: `http://go.microsoft.com/fwlink/events.asp`

## pseudocode

```c

```

## disassembly

```asm
0x34630  ldarg.0
0x34631  ldnull
0x34632  stind.ref
0x34633  ldarg.1
0x34634  ldnull
0x34635  stind.ref
0x34636  ldstr    aSoftwareMicros_2// "Software\\Microsoft\\Windows NT\\Curren"...
0x3463b  stloc.0
0x3463c  ldstr    aSoftwarePolici// "Software\\Policies\\Microsoft\\EventVie"...
0x34641  stloc.1
0x34642  ldstr    aMicrosoftredir// "MicrosoftRedirectionProgram"
0x34647  stloc.2
0x34648  ldstr    aMicrosoftredir_0// "MicrosoftRedirectionProgramCommandLineP"...
0x3464d  stloc.3
0x3464e  ldstr    aMicrosoftredir_1// "MicrosoftRedirectionURL"
0x34653  stloc.s  4
0x34655  ldarg.0
0x34656  ldc.i4   0x80000002
0x3465b  ldloc.1
0x3465c  ldloc.2
0x3465d  ldstr    asc_AA3F4// ""
0x34662  ldsfld   string [mscorlib]System.String::Empty
0x34667  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x3466c  stind.ref
0x3466d  ldarg.0
0x3466e  ldind.ref
0x3466f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34674  brfalse.s loc_3468E
0x34676  ldarg.0
0x34677  ldc.i4   0x80000002
0x3467c  ldloc.0
0x3467d  ldloc.2
0x3467e  ldstr    asc_AA3F4// ""
0x34683  ldsfld   string [mscorlib]System.String::Empty
0x34688  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x3468d  stind.ref
0x3468e  ldarg.0
0x3468f  ldind.ref
0x34690  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34695  brtrue.s loc_346D0
0x34697  ldarg.1
0x34698  ldc.i4   0x80000002
0x3469d  ldloc.1
0x3469e  ldloc.3
0x3469f  ldstr    asc_AA3F4// ""
0x346a4  ldsfld   string [mscorlib]System.String::Empty
0x346a9  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x346ae  stind.ref
0x346af  ldarg.1
0x346b0  ldind.ref
0x346b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x346b6  brfalse.s loc_346D0
0x346b8  ldarg.1
0x346b9  ldc.i4   0x80000002
0x346be  ldloc.0
0x346bf  ldloc.3
0x346c0  ldstr    asc_AA3F4// ""
0x346c5  ldsfld   string [mscorlib]System.String::Empty
0x346ca  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x346cf  stind.ref
0x346d0  ldsfld   string [mscorlib]System.String::Empty
0x346d5  stloc.s  5
0x346d7  ldc.i4   0x80000002
0x346dc  ldloc.1
0x346dd  ldloc.s  4
0x346df  ldsfld   string [mscorlib]System.String::Empty
0x346e4  ldsfld   string [mscorlib]System.String::Empty
0x346e9  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x346ee  stloc.s  5
0x346f0  ldloc.s  5
0x346f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x346f7  brfalse.s loc_34712
0x346f9  ldc.i4   0x80000002
0x346fe  ldloc.0
0x346ff  ldloc.s  4
0x34701  ldsfld   string [mscorlib]System.String::Empty
0x34706  ldsfld   string [mscorlib]System.String::Empty
0x3470b  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetStringRegistryValue(valuetype [mscorlib]Microsoft.Win32.RegistryHive regHive, string keyName, string valueName, string defaultValue, string remoteMachineName)
0x34710  stloc.s  5
0x34712  ldloc.s  5
0x34714  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34719  brtrue.s loc_3472A
0x3471b  ldloc.s  5
0x3471d  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/events.a"...
0x34722  ldc.i4.5
0x34723  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x34728  brtrue.s loc_34740
0x3472a  ldarg.2
0x3472b  ldind.ref
0x3472c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34731  brfalse.s loc_3473C
0x34733  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/events.a"...
0x34738  stloc.s  5
0x3473a  br.s     loc_34740
0x3473c  ldarg.2
0x3473d  ldind.ref
0x3473e  stloc.s  5
0x34740  ldarg.2
0x34741  ldloc.s  5
0x34743  stind.ref
0x34744  ret
```
