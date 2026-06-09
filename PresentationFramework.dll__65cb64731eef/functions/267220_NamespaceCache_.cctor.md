# NamespaceCache::.cctor

- ea: `0x267220`
- end: `0x26725d`
- name: `NamespaceCache::.cctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x26723e`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x267248`: `http://www.w3.org/XML/1998/namespace`
- `0x267252`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0x267220  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::.ctor()
0x267225  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>> NamespaceCache::XmlnsDefinitions
0x26722a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x26722f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> NamespaceCache::DefaultPrefixes
0x267234  newobj   instance void [mscorlib]System.Object::.ctor()
0x267239  stsfld   object NamespaceCache::SyncObject
0x26723e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x267243  stsfld   string NamespaceCache::XamlNamespace
0x267248  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x26724d  stsfld   string NamespaceCache::XmlNamespace
0x267252  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x267257  stsfld   string NamespaceCache::XmlnsNamespace
0x26725c  ret
```
