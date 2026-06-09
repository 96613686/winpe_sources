# Microsoft.VisualStudio.Setup.Utility.Io::GetExistingAncestor

- ea: `0xd150`
- end: `0xd174`
- name: `Microsoft.VisualStudio.Setup.Utility.Io::GetExistingAncestor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xc1d0`
- `0xd310`

## string_xrefs

- `0xd151`: `services`

## pseudocode

```c

```

## disassembly

```asm
0xd150  ldarg.0
0xd151  ldstr    aServices// "services"
0xd156  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xd15b  ldarg.1
0xd15c  ldstr    aPath_0// "path"
0xd161  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0xd166  ldarg.0
0xd167  ldc.i4.1
0xd168  call     T0x2B00003E
0xd16d  ldarg.1
0xd16e  call     string Microsoft.VisualStudio.Setup.Utility.Io::GetExistingAncestorInternal(class Microsoft.VisualStudio.Setup.Services.IFileSystem, string fileSystem)
0xd173  ret
```
