# System.Net.Http.Properties.Resources::get_HttpMessageParserEmptyUri

- ea: `0x3490`
- end: `0x34a5`
- name: `System.Net.Http.Properties.Resources::get_HttpMessageParserEmptyUri`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9b70`

## callees

- `0x30a0`

## string_xrefs

- `0x3495`: `HttpMessageParserEmptyUri`

## pseudocode

```c

```

## disassembly

```asm
0x3490  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3495  ldstr    aHttpmessagepar// "HttpMessageParserEmptyUri"
0x349a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x349f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x34a4  ret
```
