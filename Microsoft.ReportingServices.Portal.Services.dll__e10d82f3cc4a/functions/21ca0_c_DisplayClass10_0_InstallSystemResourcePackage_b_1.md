# <>c__DisplayClass10_0::<InstallSystemResourcePackage>b__1

- ea: `0x21ca0`
- end: `0x21cbf`
- name: `<>c__DisplayClass10_0::<InstallSystemResourcePackage>b__1`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x21ca0`

## string_xrefs

- `0x21ca6`: `metadata.xml`

## pseudocode

```c

```

## disassembly

```asm
0x21ca0  ldarg.0
0x21ca1  ldfld    class [System.IO.Compression]System.IO.Compression.ZipArchive <>c__DisplayClass10_0::archive
0x21ca6  ldstr    aMetadataXml// "metadata.xml"
0x21cab  callvirt instance class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry [System.IO.Compression]System.IO.Compression.ZipArchive::GetEntry(string)
0x21cb0  dup
0x21cb1  brtrue.s loc_21CB9
0x21cb3  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageMetadataNotFoundException::.ctor()
0x21cb8  throw
0x21cb9  callvirt instance class [mscorlib]System.IO.Stream [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::Open()
0x21cbe  ret
```
