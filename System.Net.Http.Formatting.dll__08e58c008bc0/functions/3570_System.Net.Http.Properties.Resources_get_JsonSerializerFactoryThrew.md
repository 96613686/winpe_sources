# System.Net.Http.Properties.Resources::get_JsonSerializerFactoryThrew

- ea: `0x3570`
- end: `0x3585`
- name: `System.Net.Http.Properties.Resources::get_JsonSerializerFactoryThrew`
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

- `0x3575`: `JsonSerializerFactoryThrew`

## pseudocode

```c

```

## disassembly

```asm
0x3570  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3575  ldstr    aJsonserializer_0// "JsonSerializerFactoryThrew"
0x357a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x357f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3584  ret
```
