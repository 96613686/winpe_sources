# MS.Internal.ReachFramework.WpfLibraryLoader::GetWPFInstallPath

- ea: `0x1ab80`
- end: `0x1ac04`
- name: `MS.Internal.ReachFramework.WpfLibraryLoader::GetWPFInstallPath`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ac40`

## callees

- `0x1ab80`
- `0x1ac10`

## string_xrefs

- `0x1ab82`: `COMPLUS_Version`
- `0x1ab95`: `COMPLUS_InstallRoot`
- `0x1abad`: `InstallRoot`
- `0x1abeb`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x1ab80  ldnull
0x1ab81  stloc.0
0x1ab82  ldstr    aComplusVersion// "COMPLUS_Version"
0x1ab87  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x1ab8c  stloc.1
0x1ab8d  ldloc.1
0x1ab8e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ab93  brtrue.s loc_1ABC8
0x1ab95  ldstr    aComplusInstall// "COMPLUS_InstallRoot"
0x1ab9a  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x1ab9f  stloc.0
0x1aba0  ldloc.0
0x1aba1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1aba6  brfalse.s loc_1ABB8
0x1aba8  ldstr    aSoftwareMicros// "Software\\Microsoft\\.NETFramework"
0x1abad  ldstr    aInstallroot// "InstallRoot"
0x1abb2  call     string MS.Internal.ReachFramework.WpfLibraryLoader::ReadLocalMachineString(string key, string valueName)
0x1abb7  stloc.0
0x1abb8  ldloc.0
0x1abb9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1abbe  brtrue.s loc_1ABC8
0x1abc0  ldloc.0
0x1abc1  ldloc.1
0x1abc2  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1abc7  stloc.0
0x1abc8  ldloc.0
0x1abc9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1abce  brfalse.s loc_1ABF6
0x1abd0  call     valuetype [mscorlib]System.Runtime.InteropServices.Architecture [mscorlib]System.Runtime.InteropServices.RuntimeInformation::get_ProcessArchitecture()
0x1abd5  ldc.i4.3
0x1abd6  bne.un.s loc_1ABDE
0x1abd8  call     string [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeDirectory()
0x1abdd  stloc.0
0x1abde  ldloc.0
0x1abdf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1abe4  brfalse.s loc_1ABF6
0x1abe6  ldstr    aSoftwareMicros_0// "Software\\Microsoft\\Net Framework Setu"...
0x1abeb  ldstr    aInstallpath// "InstallPath"
0x1abf0  call     string MS.Internal.ReachFramework.WpfLibraryLoader::ReadLocalMachineString(string key, string valueName)
0x1abf5  stloc.0
0x1abf6  ldloc.0
0x1abf7  ldstr    aWpf// "WPF"
0x1abfc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ac01  stloc.0
0x1ac02  ldloc.0
0x1ac03  ret
```
