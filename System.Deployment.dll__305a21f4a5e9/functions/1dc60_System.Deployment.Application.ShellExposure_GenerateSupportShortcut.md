# System.Deployment.Application.ShellExposure::GenerateSupportShortcut

- ea: `0x1dc60`
- end: `0x1dd37`
- name: `System.Deployment.Application.ShellExposure::GenerateSupportShortcut`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1d970`

## callees

- `0x17d40`
- `0x1dc60`
- `0x1efa0`
- `0x22cd0`
- `0x23c40`
- `0x2c530`

## string_xrefs

- `0x1dd21`: `Support shortcut file created: `

## pseudocode

```c

```

## disassembly

```asm
0x1dc60  ldarg.0
0x1dc61  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.SubscriptionState::get_EffectiveDescription()
0x1dc66  stloc.0
0x1dc67  ldloc.0
0x1dc68  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x1dc6d  ldnull
0x1dc6e  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1dc73  brfalse  loc_1DD36
0x1dc78  ldarg.1
0x1dc79  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1dc7e  ldc.i4.0
0x1dc7f  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x1dc84  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(string, bool, class [mscorlib]System.Text.Encoding)
0x1dc89  stloc.1
0x1dc8a  ldloc.1
0x1dc8b  ldstr    aDefault// "[Default]"
0x1dc90  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1dc95  ldloc.1
0x1dc96  ldstr    aBaseurl// "BASEURL="
0x1dc9b  ldloc.0
0x1dc9c  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x1dca1  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1dca6  call     string [mscorlib]System.String::Concat(string, string)
0x1dcab  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1dcb0  ldloc.1
0x1dcb1  ldstr    aInternetshortc// "[InternetShortcut]"
0x1dcb6  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1dcbb  ldloc.1
0x1dcbc  ldstr    aUrl_0// "URL="
0x1dcc1  ldloc.0
0x1dcc2  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x1dcc7  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1dccc  call     string [mscorlib]System.String::Concat(string, string)
0x1dcd1  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1dcd6  ldloc.1
0x1dcd7  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine()
0x1dcdc  ldloc.1
0x1dcdd  ldstr    aIconfile// "IconFile="
0x1dce2  call     string System.Deployment.Application.PathHelper::get_ShortShimDllPath()
0x1dce7  call     string [mscorlib]System.String::Concat(string, string)
0x1dcec  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1dcf1  ldloc.1
0x1dcf2  ldstr    aIconindex// "IconIndex="
0x1dcf7  ldc.i4.0
0x1dcf8  stloc.2
0x1dcf9  ldloca.s 2
0x1dcfb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1dd00  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1dd05  call     string [mscorlib]System.String::Concat(string, string)
0x1dd0a  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1dd0f  ldloc.1
0x1dd10  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine()
0x1dd15  leave.s  loc_1DD21
0x1dd17  ldloc.1
0x1dd18  brfalse.s loc_1DD20
0x1dd1a  ldloc.1
0x1dd1b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dd20  endfinally
0x1dd21  ldstr    aSupportShortcu// "Support shortcut file created: "
0x1dd26  ldarg.1
0x1dd27  callvirt instance string ShellExposureInformation::get_SupportShortcutPath()
0x1dd2c  call     string [mscorlib]System.String::Concat(string, string)
0x1dd31  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1dd36  ret
```
