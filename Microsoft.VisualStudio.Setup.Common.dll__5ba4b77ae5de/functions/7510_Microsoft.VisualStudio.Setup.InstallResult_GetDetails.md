# Microsoft.VisualStudio.Setup.InstallResult::GetDetails

- ea: `0x7510`
- end: `0x755b`
- name: `Microsoft.VisualStudio.Setup.InstallResult::GetDetails`
- size: `75`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7430`
- `0x74f0`
- `0x7600`

## callees

- `0x3380`
- `0x73f0`
- `0x74d0`
- `0x7510`
- `0xd400`

## pseudocode

```c

```

## disassembly

```asm
0x7510  ldarg.0
0x7511  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_ResourceId()
0x7516  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x751b  brtrue.s loc_752F
0x751d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x7522  ldarg.0
0x7523  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_ResourceId()
0x7528  ldarg.1
0x7529  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x752e  ret
0x752f  ldarg.0
0x7530  ldfld    string Microsoft.VisualStudio.Setup.InstallResult::details
0x7535  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x753a  brtrue.s loc_7543
0x753c  ldarg.0
0x753d  ldfld    string Microsoft.VisualStudio.Setup.InstallResult::details
0x7542  ret
0x7543  ldarg.0
0x7544  call     instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x7549  ldarg.1
0x754a  brtrue.s loc_754F
0x754c  ldc.i4.0
0x754d  br.s     loc_7555
0x754f  ldarg.1
0x7550  callvirt instance bool [mscorlib]System.Globalization.CultureInfo::get_IsNeutralCulture()
0x7555  call     string Microsoft.VisualStudio.Setup.Utility.Windows::GetMessage(int32 error, [opt] bool englishOnly)
0x755a  ret
```
