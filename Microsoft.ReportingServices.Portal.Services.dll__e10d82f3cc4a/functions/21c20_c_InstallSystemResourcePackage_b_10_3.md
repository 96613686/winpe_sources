# <>c::<InstallSystemResourcePackage>b__10_3

- ea: `0x21c20`
- end: `0x21c31`
- name: `<>c::<InstallSystemResourcePackage>b__10_3`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## string_xrefs

- `0x21c26`: `metadata.xml`

## pseudocode

```c

```

## disassembly

```asm
0x21c20  ldarg.1
0x21c21  callvirt instance string [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::get_FullName()
0x21c26  ldstr    aMetadataXml// "metadata.xml"
0x21c2b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21c30  ret
```
