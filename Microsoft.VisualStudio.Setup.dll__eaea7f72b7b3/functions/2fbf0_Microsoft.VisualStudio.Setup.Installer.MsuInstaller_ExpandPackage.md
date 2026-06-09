# Microsoft.VisualStudio.Setup.Installer.MsuInstaller::ExpandPackage

- ea: `0x2fbf0`
- end: `0x2fd5b`
- name: `Microsoft.VisualStudio.Setup.Installer.MsuInstaller::ExpandPackage`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2f850`

## callees

- `0x27f20`
- `0x2b920`
- `0x2b940`
- `0x2fbf0`
- `0x386e0`
- `0x388e0`
- `0x39850`
- `0x398d0`

## string_xrefs

- `0x2fd34`: `Temporary directory '`
- `0x2fd3a`: `' used for MSU package expansion could not be deleted. Error: `

## pseudocode

```c

```

## disassembly

```asm
0x2fbf0  ldnull
0x2fbf1  stloc.0
0x2fbf2  ldnull
0x2fbf3  stloc.1
0x2fbf4  call     string [mscorlib]System.IO.Path::GetTempPath()
0x2fbf9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2fbfe  stloc.2
0x2fbff  ldloca.s 2
0x2fc01  constrained. [mscorlib]System.Guid
0x2fc07  callvirt instance string [mscorlib]System.Object::ToString()
0x2fc0c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2fc11  stloc.0
0x2fc12  ldarg.0
0x2fc13  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2fc18  dup
0x2fc19  brtrue.s loc_2FC1F
0x2fc1b  pop
0x2fc1c  ldnull
0x2fc1d  br.s     loc_2FC25
0x2fc1f  ldc.i4.1
0x2fc20  call     T0x2B00000C
0x2fc25  stloc.1
0x2fc26  ldloc.1
0x2fc27  ldloc.0
0x2fc28  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x2fc2d  newobj   instance void Microsoft.VisualStudio.Setup.Compression.CabEngine::.ctor()
0x2fc32  stloc.3
0x2fc33  ldnull
0x2fc34  stloc.s  4
0x2fc36  ldarg.1
0x2fc37  ldc.i4.3
0x2fc38  ldc.i4.1
0x2fc39  ldc.i4.1
0x2fc3a  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x2fc3f  stloc.s  5
0x2fc41  ldloc.3
0x2fc42  ldloc.s  5
0x2fc44  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Compression.ArchiveFileInfo> Microsoft.VisualStudio.Setup.Compression.CompressionEngine::GetFileInfo(class [mscorlib]System.IO.Stream stream)
0x2fc49  stloc.s  4
0x2fc4b  leave.s  loc_2FC59
0x2fc4d  ldloc.s  5
0x2fc4f  brfalse.s loc_2FC58
0x2fc51  ldloc.s  5
0x2fc53  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fc58  endfinally
0x2fc59  ldarg.1
0x2fc5a  ldc.i4.3
0x2fc5b  ldc.i4.1
0x2fc5c  ldc.i4.1
0x2fc5d  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x2fc62  stloc.s  6
0x2fc64  ldloc.s  4
0x2fc66  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Compression.ArchiveFileInfo>::GetEnumerator()
0x2fc6b  stloc.s  7
0x2fc6d  br.s     loc_2FCD4
0x2fc6f  ldloc.s  7
0x2fc71  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Compression.ArchiveFileInfo>::get_Current()
0x2fc76  stloc.s  8
0x2fc78  ldloc.s  8
0x2fc7a  callvirt instance string Microsoft.VisualStudio.Setup.Compression.ArchiveFileInfo::get_Path()
0x2fc7f  ldloc.s  8
0x2fc81  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x2fc86  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2fc8b  stloc.s  9
0x2fc8d  ldloc.0
0x2fc8e  ldloc.s  9
0x2fc90  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2fc95  stloc.s  0xA
0x2fc97  ldloc.3
0x2fc98  ldloc.s  6
0x2fc9a  ldloc.s  9
0x2fc9c  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Compression.CompressionEngine::Unpack(class [mscorlib]System.IO.Stream, string stream)
0x2fca1  stloc.s  0xB
0x2fca3  ldloc.s  0xA
0x2fca5  ldc.i4.2
0x2fca6  ldc.i4.2
0x2fca7  ldc.i4.2
0x2fca8  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x2fcad  stloc.s  0xC
0x2fcaf  ldloc.s  0xB
0x2fcb1  ldloc.s  0xC
0x2fcb3  call     void Microsoft.VisualStudio.Setup.Utility.IOUtil::CopyStream(class [mscorlib]System.IO.Stream input, class [mscorlib]System.IO.Stream output)
0x2fcb8  leave.s  loc_2FCC6
0x2fcba  ldloc.s  0xC
0x2fcbc  brfalse.s loc_2FCC5
0x2fcbe  ldloc.s  0xC
0x2fcc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fcc5  endfinally
0x2fcc6  leave.s  loc_2FCD4
0x2fcc8  ldloc.s  0xB
0x2fcca  brfalse.s loc_2FCD3
0x2fccc  ldloc.s  0xB
0x2fcce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fcd3  endfinally
0x2fcd4  ldloc.s  7
0x2fcd6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2fcdb  brtrue.s loc_2FC6F
0x2fcdd  leave.s  loc_2FCEB
0x2fcdf  ldloc.s  7
0x2fce1  brfalse.s loc_2FCEA
0x2fce3  ldloc.s  7
0x2fce5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fcea  endfinally
0x2fceb  leave.s  loc_2FCF9
0x2fced  ldloc.s  6
0x2fcef  brfalse.s loc_2FCF8
0x2fcf1  ldloc.s  6
0x2fcf3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fcf8  endfinally
0x2fcf9  leave.s  loc_2FD05
0x2fcfb  ldloc.3
0x2fcfc  brfalse.s loc_2FD04
0x2fcfe  ldloc.3
0x2fcff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fd04  endfinally
0x2fd05  leave.s  loc_2FD59
0x2fd07  pop
0x2fd08  ldloc.0
0x2fd09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fd0e  brtrue.s loc_2FD57
0x2fd10  ldloc.1
0x2fd11  brfalse.s loc_2FD57
0x2fd13  ldloc.1
0x2fd14  ldloc.0
0x2fd15  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x2fd1a  brfalse.s loc_2FD57
0x2fd1c  ldloc.1
0x2fd1d  ldloc.0
0x2fd1e  ldc.i4.1
0x2fd1f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DeleteDirectory(string, bool)
0x2fd24  leave.s  loc_2FD57
0x2fd26  stloc.s  0xD
0x2fd28  ldarg.0
0x2fd29  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2fd2e  dup
0x2fd2f  brtrue.s loc_2FD34
0x2fd31  pop
0x2fd32  br.s     loc_2FD55
0x2fd34  ldstr    aTemporaryDirec// "Temporary directory '"
0x2fd39  ldloc.0
0x2fd3a  ldstr    aUsedForMsuPack// "' used for MSU package expansion could "...
0x2fd3f  ldloc.s  0xD
0x2fd41  callvirt instance string [mscorlib]System.Object::ToString()
0x2fd46  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2fd4b  call     T0x2B000003
0x2fd50  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2fd55  leave.s  loc_2FD57
0x2fd57  rethrow
0x2fd59  ldloc.0
0x2fd5a  ret
```
