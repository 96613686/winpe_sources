# Microsoft.VisualStudio.Setup.InstallResult::GetOperationContext

- ea: `0x7560`
- end: `0x759b`
- name: `Microsoft.VisualStudio.Setup.InstallResult::GetOperationContext`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x75e0`
- `0x75f0`

## callees

- `0x3380`
- `0x7560`
- `0x75a0`
- `0x75c0`

## pseudocode

```c

```

## disassembly

```asm
0x7560  ldarg.0
0x7561  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_OperationContextResourceId()
0x7566  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x756b  brtrue.s loc_7599
0x756d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x7572  ldarg.0
0x7573  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_OperationContextResourceId()
0x7578  ldarg.1
0x7579  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x757e  stloc.0
0x757f  ldloc.0
0x7580  brfalse.s loc_7599
0x7582  ldarg.0
0x7583  call     instance object[] Microsoft.VisualStudio.Setup.InstallResult::get_OperationContextArgs()
0x7588  brtrue.s loc_758C
0x758a  ldloc.0
0x758b  ret
0x758c  ldloc.0
0x758d  ldarg.0
0x758e  call     instance object[] Microsoft.VisualStudio.Setup.InstallResult::get_OperationContextArgs()
0x7593  call     string [mscorlib]System.String::Format(string, object[])
0x7598  ret
0x7599  ldnull
0x759a  ret
```
