# <>c::<DownloadUpdatesForInstance>b__23_1

- ea: `0x3a60`
- end: `0x3a77`
- name: `<>c::<DownloadUpdatesForInstance>b__23_1`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x3a60`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldarg.1
0x3a61  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x3a66  ldarg.2
0x3a67  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Version()
0x3a6c  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x3a71  brtrue.s loc_3A75
0x3a73  ldarg.2
0x3a74  ret
0x3a75  ldarg.1
0x3a76  ret
```
