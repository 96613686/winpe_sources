# System.Deployment.Application.ShellExposure::CanAddFileAssociation

- ea: `0x1dff0`
- end: `0x1e0c6`
- name: `System.Deployment.Application.ShellExposure::CanAddFileAssociation`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1e0d0`

## callees

- `0x17cb0`
- `0x17d40`
- `0x1dff0`
- `0x23020`
- `0x24490`
- `0x244b0`

## string_xrefs

- `0x1e08e`: `Exception reading registry key : `

## pseudocode

```c

```

## disassembly

```asm
0x1dff0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::CurrentUser
0x1dff5  ldstr    aSoftwareClasse_0// "Software\\Classes"
0x1dffa  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1dfff  stloc.0
0x1e000  ldloc.0
0x1e001  ldarg.0
0x1e002  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e007  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1e00c  stloc.1
0x1e00d  ldloc.0
0x1e00e  ldarg.0
0x1e00f  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_ProgID()
0x1e014  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1e019  stloc.2
0x1e01a  ldloc.1
0x1e01b  brtrue.s loc_1E020
0x1e01d  ldloc.2
0x1e01e  brfalse.s loc_1E066
0x1e020  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1e025  ldstr    aSkippedfileass// "SkippedFileAssoc"
0x1e02a  call     string System.Deployment.Application.Resources::GetString(string s)
0x1e02f  ldc.i4.1
0x1e030  newarr   [mscorlib]System.Object
0x1e035  dup
0x1e036  ldc.i4.0
0x1e037  ldarg.0
0x1e038  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e03d  stelem.ref
0x1e03e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e043  call     void System.Deployment.Application.Logger::AddWarningInformation(string message)
0x1e048  ldstr    aFileAssociatio// "File association for "
0x1e04d  ldarg.0
0x1e04e  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e053  ldstr    aSkippedSinceAn// " skipped, since another application is "...
0x1e058  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e05d  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1e062  ldc.i4.0
0x1e063  stloc.3
0x1e064  leave.s  loc_1E0C4
0x1e066  leave.s  loc_1E072
0x1e068  ldloc.2
0x1e069  brfalse.s loc_1E071
0x1e06b  ldloc.2
0x1e06c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e071  endfinally
0x1e072  leave.s  loc_1E07E
0x1e074  ldloc.1
0x1e075  brfalse.s loc_1E07D
0x1e077  ldloc.1
0x1e078  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e07d  endfinally
0x1e07e  leave.s  loc_1E08A
0x1e080  ldloc.0
0x1e081  brfalse.s loc_1E089
0x1e083  ldloc.0
0x1e084  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e089  endfinally
0x1e08a  leave.s  loc_1E0C2
0x1e08c  stloc.s  4
0x1e08e  ldstr    aExceptionReadi// "Exception reading registry key : "
0x1e093  ldloc.s  4
0x1e095  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1e09a  call     string [mscorlib]System.String::Concat(string, string)
0x1e09f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1e0a4  ldstr    aFileAssociatio// "File association for "
0x1e0a9  ldarg.0
0x1e0aa  callvirt instance string System.Deployment.Application.Manifest.FileAssociation::get_Extension()
0x1e0af  ldstr    aSkipped// " skipped"
0x1e0b4  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e0b9  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1e0be  ldc.i4.0
0x1e0bf  stloc.3
0x1e0c0  leave.s  loc_1E0C4
0x1e0c2  ldc.i4.1
0x1e0c3  ret
0x1e0c4  ldloc.3
0x1e0c5  ret
```
