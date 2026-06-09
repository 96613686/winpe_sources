# Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationPath

- ea: `0x1a680`
- end: `0x1a6b6`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_InstallationPath`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xd1a0`
- `0x1a680`

## string_xrefs

- `0x1a696`: `InstallationPath`
- `0x1a6aa`: `InstallationPath`

## pseudocode

```c

```

## disassembly

```asm
0x1a680  ldarg.1
0x1a681  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a686  brtrue.s loc_1A6A2
0x1a688  ldarg.0
0x1a689  ldarg.0
0x1a68a  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::installationPath
0x1a68f  ldarg.1
0x1a690  ldc.i4.0
0x1a691  call     string Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string path, [opt] bool addBackslash)
0x1a696  ldstr    aInstallationpa// "InstallationPath"
0x1a69b  ldnull
0x1a69c  call     T0x2B0000C9
0x1a6a1  ret
0x1a6a2  ldarg.0
0x1a6a3  ldarg.0
0x1a6a4  ldflda   string Microsoft.VisualStudio.Setup.Cache.Instance::installationPath
0x1a6a9  ldarg.1
0x1a6aa  ldstr    aInstallationpa// "InstallationPath"
0x1a6af  ldnull
0x1a6b0  call     T0x2B0000C9
0x1a6b5  ret
```
