# System.Net.Http.Properties.Resources::get_ErrorReadingFormUrlEncodedStream

- ea: `0x3370`
- end: `0x3385`
- name: `System.Net.Http.Properties.Resources::get_ErrorReadingFormUrlEncodedStream`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7690`

## callees

- `0x30a0`

## string_xrefs

- `0x3375`: `ErrorReadingFormUrlEncodedStream`

## pseudocode

```c

```

## disassembly

```asm
0x3370  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3375  ldstr    aErrorreadingfo// "ErrorReadingFormUrlEncodedStream"
0x337a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x337f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3384  ret
```
