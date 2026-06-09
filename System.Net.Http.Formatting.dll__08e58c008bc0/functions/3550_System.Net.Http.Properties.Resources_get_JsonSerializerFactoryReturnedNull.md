# System.Net.Http.Properties.Resources::get_JsonSerializerFactoryReturnedNull

- ea: `0x3550`
- end: `0x3565`
- name: `System.Net.Http.Properties.Resources::get_JsonSerializerFactoryReturnedNull`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x5770`

## callees

- `0x30a0`

## string_xrefs

- `0x3555`: `JsonSerializerFactoryReturnedNull`

## pseudocode

```c

```

## disassembly

```asm
0x3550  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3555  ldstr    aJsonserializer// "JsonSerializerFactoryReturnedNull"
0x355a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x355f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3564  ret
```
