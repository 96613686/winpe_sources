# <>c__DisplayClass13_0::<Create>b__4

- ea: `0x219e0`
- end: `0x21a02`
- name: `<>c__DisplayClass13_0::<Create>b__4`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x219f1`: `metadata.xml`

## pseudocode

```c

```

## disassembly

```asm
0x219e0  ldarg.1
0x219e1  ldstr    a012// "{0}.{1}.{2}"
0x219e6  ldsfld   string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::ResourceRoot
0x219eb  ldarg.0
0x219ec  ldfld    string <>c__DisplayClass13_0::typeName
0x219f1  ldstr    aMetadataXml// "metadata.xml"
0x219f6  call     string [mscorlib]System.String::Format(string, object, object, object)
0x219fb  ldc.i4.5
0x219fc  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x21a01  ret
```
