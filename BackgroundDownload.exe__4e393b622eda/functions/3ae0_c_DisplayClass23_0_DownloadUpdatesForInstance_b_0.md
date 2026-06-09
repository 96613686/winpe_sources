# <>c__DisplayClass23_0::<DownloadUpdatesForInstance>b__0

- ea: `0x3ae0`
- end: `0x3afc`
- name: `<>c__DisplayClass23_0::<DownloadUpdatesForInstance>b__0`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c

```

## disassembly

```asm
0x3ae0  ldarg.1
0x3ae1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x3ae6  ldarg.0
0x3ae7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass23_0::instance
0x3aec  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_Product()
0x3af1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x3af6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3afb  ret
```
