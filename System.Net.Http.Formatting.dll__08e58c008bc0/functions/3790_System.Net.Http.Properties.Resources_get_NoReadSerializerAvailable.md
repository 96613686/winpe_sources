# System.Net.Http.Properties.Resources::get_NoReadSerializerAvailable

- ea: `0x3790`
- end: `0x37a5`
- name: `System.Net.Http.Properties.Resources::get_NoReadSerializerAvailable`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1670`

## callees

- `0x30a0`

## string_xrefs

- `0x3795`: `NoReadSerializerAvailable`

## pseudocode

```c

```

## disassembly

```asm
0x3790  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3795  ldstr    aNoreadserializ// "NoReadSerializerAvailable"
0x379a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x379f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x37a4  ret
```
