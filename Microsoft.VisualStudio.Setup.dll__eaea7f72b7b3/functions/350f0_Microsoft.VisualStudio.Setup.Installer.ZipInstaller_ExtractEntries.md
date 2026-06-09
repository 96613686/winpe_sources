# Microsoft.VisualStudio.Setup.Installer.ZipInstaller::ExtractEntries

- ea: `0x350f0`
- end: `0x351f7`
- name: `Microsoft.VisualStudio.Setup.Installer.ZipInstaller::ExtractEntries`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x34db0`

## callees

- `0x1a0b0`
- `0x1a0d0`
- `0x350f0`
- `0x35200`
- `0x6d3a0`

## string_xrefs

- `0x3514d`: `The installation path: `
- `0x35153`: ` is outside of allowed directory: `

## pseudocode

```c

```

## disassembly

```asm
0x350f0  ldc.i4.0
0x350f1  stloc.0
0x350f2  ldarg.2
0x350f3  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::AddBackslashIfNotPresent(string)
0x350f8  starg.s  2
0x350fa  ldarg.1
0x350fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry>::GetEnumerator()
0x35100  stloc.1
0x35101  br       loc_351CE
0x35106  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x3510b  stloc.2
0x3510c  ldloc.2
0x3510d  ldloc.1
0x3510e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry>::get_Current()
0x35113  stfld    class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry <>c__DisplayClass7_0::entry
0x35118  ldarg.3
0x35119  ldloc.2
0x3511a  ldftn    instance bool <>c__DisplayClass7_0::<ExtractEntries>b__0(class [System]System.Text.RegularExpressions.Regex r)
0x35120  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Text.RegularExpressions.Regex, bool>::.ctor(object, native int)
0x35125  call     T0x2B000190
0x3512a  brtrue   loc_351CE
0x3512f  ldarg.2
0x35130  ldloc.2
0x35131  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry <>c__DisplayClass7_0::entry
0x35136  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x3513b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x35140  stloc.3
0x35141  ldloc.3
0x35142  ldarg.2
0x35143  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x35148  brtrue.s loc_35188
0x3514a  ldarg.s  5
0x3514c  ldnull
0x3514d  ldstr    aTheInstallatio_0// "The installation path: "
0x35152  ldloc.3
0x35153  ldstr    aIsOutsideOfAll// " is outside of allowed directory: "
0x35158  ldarg.2
0x35159  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x3515e  call     T0x2B000003
0x35163  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x35168  ldc.i4.4
0x35169  ldc.i4.0
0x3516a  call     string Microsoft.VisualStudio.Setup.Resources::get_FileInstallationPathInvalid_Args1()
0x3516f  ldloc.2
0x35170  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry <>c__DisplayClass7_0::entry
0x35175  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_Name()
0x3517a  call     string [mscorlib]System.String::Format(string, object)
0x3517f  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x35184  stloc.s  5
0x35186  leave.s  loc_351F4
0x35188  ldarg.0
0x35189  ldloc.2
0x3518a  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry <>c__DisplayClass7_0::entry
0x3518f  ldloc.3
0x35190  ldarg.s  4
0x35192  ldloca.s 4
0x35194  ldarg.s  5
0x35196  call     instance bool Microsoft.VisualStudio.Setup.Installer.ZipInstaller::ExtractEntry(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry entry, string fullPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ZipPackage package, [out] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType& rebootRequired, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x3519b  ldloc.0
0x3519c  ldloc.s  4
0x3519e  bge.s    loc_351A3
0x351a0  ldloc.s  4
0x351a2  stloc.0
0x351a3  brtrue.s loc_351CE
0x351a5  ldloc.s  4
0x351a7  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsRebootRequired(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType)
0x351ac  brtrue.s loc_351CE
0x351ae  ldc.i4.4
0x351af  ldc.i4.0
0x351b0  call     string Microsoft.VisualStudio.Setup.Resources::get_FileInstallationFailed_Args1()
0x351b5  ldloc.2
0x351b6  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry <>c__DisplayClass7_0::entry
0x351bb  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x351c0  call     string [mscorlib]System.String::Format(string, object)
0x351c5  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x351ca  stloc.s  5
0x351cc  leave.s  loc_351F4
0x351ce  ldloc.1
0x351cf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x351d4  brtrue   loc_35106
0x351d9  leave.s  loc_351E5
0x351db  ldloc.1
0x351dc  brfalse.s loc_351E4
0x351de  ldloc.1
0x351df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x351e4  endfinally
0x351e5  ldloc.0
0x351e6  brtrue.s loc_351EB
0x351e8  ldc.i4.1
0x351e9  br.s     loc_351EC
0x351eb  ldc.i4.3
0x351ec  ldc.i4.0
0x351ed  ldnull
0x351ee  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x351f3  ret
0x351f4  ldloc.s  5
0x351f6  ret
```
