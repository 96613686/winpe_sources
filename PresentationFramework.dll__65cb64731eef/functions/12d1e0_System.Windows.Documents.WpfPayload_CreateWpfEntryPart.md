# System.Windows.Documents.WpfPayload::CreateWpfEntryPart

- ea: `0x12d1e0`
- end: `0x12d214`
- name: `System.Windows.Documents.WpfPayload::CreateWpfEntryPart`
- size: `52`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x12c900`
- `0x12c9d0`
- `0x12d100`

## string_xrefs

- `0x12d1f3`: `application/vnd.ms-wpf.xaml+xml`
- `0x12d207`: `http://schemas.microsoft.com/wpf/2005/10/xaml/entry`

## pseudocode

```c

```

## disassembly

```asm
0x12d1e0  ldstr    aXamlDocumentXa// "/Xaml/Document.xaml"
0x12d1e5  ldc.i4.2
0x12d1e6  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x12d1eb  stloc.0
0x12d1ec  ldarg.0
0x12d1ed  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Documents.WpfPayload::_package
0x12d1f2  ldloc.0
0x12d1f3  ldstr    aApplicationVnd_10// "application/vnd.ms-wpf.xaml+xml"
0x12d1f8  ldc.i4.0
0x12d1f9  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::CreatePart(class [System]System.Uri, string, valuetype [WindowsBase]System.IO.Packaging.CompressionOption)
0x12d1fe  stloc.1
0x12d1ff  ldarg.0
0x12d200  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Documents.WpfPayload::_package
0x12d205  ldloc.0
0x12d206  ldc.i4.0
0x12d207  ldstr    aHttpSchemasMic_10// "http://schemas.microsoft.com/wpf/2005/1"...
0x12d20c  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.Package::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x12d211  stloc.2
0x12d212  ldloc.1
0x12d213  ret
```
