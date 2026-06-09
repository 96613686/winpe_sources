# MS.Internal.WindowsBase.WpfLibraryLoader::GetWPFInstallPath

- ea: `0x2bdd0`
- end: `0x2be54`
- name: `MS.Internal.WindowsBase.WpfLibraryLoader::GetWPFInstallPath`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2be90`

## callees

- `0x2bdd0`
- `0x2be60`

## string_xrefs

- `0x2bdd2`: `COMPLUS_Version`
- `0x2bde5`: `COMPLUS_InstallRoot`
- `0x2bdfd`: `InstallRoot`
- `0x2be3b`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x2bdd0  ldnull
0x2bdd1  stloc.0
0x2bdd2  ldstr    aComplusVersion// "COMPLUS_Version"
0x2bdd7  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x2bddc  stloc.1
0x2bddd  ldloc.1
0x2bdde  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2bde3  brtrue.s loc_2BE18
0x2bde5  ldstr    aComplusInstall// "COMPLUS_InstallRoot"
0x2bdea  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x2bdef  stloc.0
0x2bdf0  ldloc.0
0x2bdf1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2bdf6  brfalse.s loc_2BE08
0x2bdf8  ldstr    aSoftwareMicros// "Software\\Microsoft\\.NETFramework"
0x2bdfd  ldstr    aInstallroot// "InstallRoot"
0x2be02  call     string MS.Internal.WindowsBase.WpfLibraryLoader::ReadLocalMachineString(string key, string valueName)
0x2be07  stloc.0
0x2be08  ldloc.0
0x2be09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2be0e  brtrue.s loc_2BE18
0x2be10  ldloc.0
0x2be11  ldloc.1
0x2be12  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2be17  stloc.0
0x2be18  ldloc.0
0x2be19  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2be1e  brfalse.s loc_2BE46
0x2be20  call     valuetype [mscorlib]System.Runtime.InteropServices.Architecture [mscorlib]System.Runtime.InteropServices.RuntimeInformation::get_ProcessArchitecture()
0x2be25  ldc.i4.3
0x2be26  bne.un.s loc_2BE2E
0x2be28  call     string [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeDirectory()
0x2be2d  stloc.0
0x2be2e  ldloc.0
0x2be2f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2be34  brfalse.s loc_2BE46
0x2be36  ldstr    aSoftwareMicros_7// "Software\\Microsoft\\Net Framework Setu"...
0x2be3b  ldstr    aInstallpath// "InstallPath"
0x2be40  call     string MS.Internal.WindowsBase.WpfLibraryLoader::ReadLocalMachineString(string key, string valueName)
0x2be45  stloc.0
0x2be46  ldloc.0
0x2be47  ldstr    aWpf// "WPF"
0x2be4c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2be51  stloc.0
0x2be52  ldloc.0
0x2be53  ret
```
