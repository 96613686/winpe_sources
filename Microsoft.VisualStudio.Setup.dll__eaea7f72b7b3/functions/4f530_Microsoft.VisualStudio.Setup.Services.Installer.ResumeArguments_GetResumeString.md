# Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::GetResumeString

- ea: `0x4f530`
- end: `0x4f5be`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::GetResumeString`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7dfd0`

## callees

- `0x4f4c0`
- `0x4f4d0`
- `0x4f4f0`
- `0x4f500`
- `0x4f510`
- `0x4f530`

## string_xrefs

- `0x4f530`: `resume --installPath `
- `0x4f55f`: ` --installSessionId {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4f530  ldstr    aResumeInstallp// "resume --installPath "
0x4f535  ldarg.0
0x4f536  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_InstallationPath()
0x4f53b  ldc.i4.0
0x4f53c  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::QuotePath(string, bool)
0x4f541  ldstr    aRunonce// " --runOnce"
0x4f546  call     string [mscorlib]System.String::Concat(string, string, string)
0x4f54b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x4f550  stloc.0
0x4f551  ldarg.0
0x4f552  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_InstallSessionId()
0x4f557  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f55c  brtrue.s loc_4F570
0x4f55e  ldloc.0
0x4f55f  ldstr    aInstallsession// " --installSessionId {0}"
0x4f564  ldarg.0
0x4f565  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_InstallSessionId()
0x4f56a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x4f56f  pop
0x4f570  ldarg.0
0x4f571  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_IsQuiet()
0x4f576  brfalse.s loc_4F584
0x4f578  ldloc.0
0x4f579  ldstr    aQuiet// " --quiet"
0x4f57e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f583  pop
0x4f584  ldarg.0
0x4f585  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_IsPassive()
0x4f58a  brfalse.s loc_4F598
0x4f58c  ldloc.0
0x4f58d  ldstr    aPassive// " --passive"
0x4f592  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f597  pop
0x4f598  ldarg.0
0x4f599  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_ProductKey()
0x4f59e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4f5a3  brtrue.s loc_4F5B7
0x4f5a5  ldloc.0
0x4f5a6  ldstr    aProductkey0// " --productKey {0}"
0x4f5ab  ldarg.0
0x4f5ac  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_ProductKey()
0x4f5b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x4f5b6  pop
0x4f5b7  ldloc.0
0x4f5b8  callvirt instance string [mscorlib]System.Object::ToString()
0x4f5bd  ret
```
