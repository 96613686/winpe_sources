# Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::PrintMembers

- ea: `0x4f600`
- end: `0x4f6e0`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::PrintMembers`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4f5c0`

## callees

- `0x4f4a0`
- `0x4f4c0`
- `0x4f4d0`
- `0x4f4f0`
- `0x4f500`
- `0x4f510`
- `0x4f520`

## string_xrefs

- `0x4f61f`: `, InstallationPath = `
- `0x4f69f`: `, InstallSessionId = `

## pseudocode

```c

```

## disassembly

```asm
0x4f600  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x4f605  ldarg.1
0x4f606  ldstr    aActivityid// "ActivityId = "
0x4f60b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f610  pop
0x4f611  ldarg.1
0x4f612  ldarg.0
0x4f613  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_ActivityId()
0x4f618  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4f61d  pop
0x4f61e  ldarg.1
0x4f61f  ldstr    aInstallationpa_2// ", InstallationPath = "
0x4f624  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f629  pop
0x4f62a  ldarg.1
0x4f62b  ldarg.0
0x4f62c  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_InstallationPath()
0x4f631  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4f636  pop
0x4f637  ldarg.1
0x4f638  ldstr    aProductkey_0// ", ProductKey = "
0x4f63d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f642  pop
0x4f643  ldarg.1
0x4f644  ldarg.0
0x4f645  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_ProductKey()
0x4f64a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4f64f  pop
0x4f650  ldarg.1
0x4f651  ldstr    aIsquiet// ", IsQuiet = "
0x4f656  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f65b  pop
0x4f65c  ldarg.1
0x4f65d  ldarg.0
0x4f65e  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_IsQuiet()
0x4f663  stloc.0
0x4f664  ldloca.s 0
0x4f666  constrained. [mscorlib]System.Boolean
0x4f66c  callvirt instance string [mscorlib]System.Object::ToString()
0x4f671  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f676  pop
0x4f677  ldarg.1
0x4f678  ldstr    aIspassive// ", IsPassive = "
0x4f67d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f682  pop
0x4f683  ldarg.1
0x4f684  ldarg.0
0x4f685  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_IsPassive()
0x4f68a  stloc.0
0x4f68b  ldloca.s 0
0x4f68d  constrained. [mscorlib]System.Boolean
0x4f693  callvirt instance string [mscorlib]System.Object::ToString()
0x4f698  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f69d  pop
0x4f69e  ldarg.1
0x4f69f  ldstr    aInstallsession_0// ", InstallSessionId = "
0x4f6a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f6a9  pop
0x4f6aa  ldarg.1
0x4f6ab  ldarg.0
0x4f6ac  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_InstallSessionId()
0x4f6b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4f6b6  pop
0x4f6b7  ldarg.1
0x4f6b8  ldstr    aHasvalue// ", HasValue = "
0x4f6bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f6c2  pop
0x4f6c3  ldarg.1
0x4f6c4  ldarg.0
0x4f6c5  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments::get_HasValue()
0x4f6ca  stloc.0
0x4f6cb  ldloca.s 0
0x4f6cd  constrained. [mscorlib]System.Boolean
0x4f6d3  callvirt instance string [mscorlib]System.Object::ToString()
0x4f6d8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f6dd  pop
0x4f6de  ldc.i4.1
0x4f6df  ret
```
