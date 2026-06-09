# System.Net.Http.Properties.Resources::get_HttpMessageErrorReading

- ea: `0x3450`
- end: `0x3465`
- name: `System.Net.Http.Properties.Resources::get_HttpMessageErrorReading`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0xc370`
- `0xc5a0`

## callees

- `0x30a0`

## string_xrefs

- `0x3455`: `HttpMessageErrorReading`

## pseudocode

```c

```

## disassembly

```asm
0x3450  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3455  ldstr    aHttpmessageerr// "HttpMessageErrorReading"
0x345a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x345f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3464  ret
```
