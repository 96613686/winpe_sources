# Microsoft.Windows.ManagementUI.CombinedControls.Settings::GetXmlPath

- ea: `0x14880`
- end: `0x148be`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.Settings::GetXmlPath`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x147e0`

## callees

- `0x13430`
- `0x14730`
- `0x14880`

## string_xrefs

- `0x14880`: `//XmlPath`
- `0x14893`: `Error 31006.10 Cannot get to XmlPath`

## pseudocode

```c

```

## disassembly

```asm
0x14880  ldstr    aXmlpath// "//XmlPath"
0x14885  call     string Microsoft.Windows.ManagementUI.CombinedControls.Settings::Get(string path)
0x1488a  stloc.0
0x1488b  ldloc.0
0x1488c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14891  brfalse.s loc_1489F
0x14893  ldstr    aError3100610Ca// "Error 31006.10 Cannot get to XmlPath"
0x14898  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x1489d  ldc.i4.0
0x1489e  ret
0x1489f  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.Settings::RootFolder
0x148a4  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x148a9  stloc.1
0x148aa  ldloca.s 1
0x148ac  call     instance string [mscorlib]System.Char::ToString()
0x148b1  ldloc.0
0x148b2  call     string [mscorlib]System.String::Concat(string, string, string)
0x148b7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.Settings::XmlPath
0x148bc  ldc.i4.1
0x148bd  ret
```
