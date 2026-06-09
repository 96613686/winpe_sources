# System.Net.Http.Properties.Resources::get_HttpMessageParserInvalidUriScheme

- ea: `0x34f0`
- end: `0x3505`
- name: `System.Net.Http.Properties.Resources::get_HttpMessageParserInvalidUriScheme`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18e0`

## callees

- `0x30a0`

## string_xrefs

- `0x34f5`: `HttpMessageParserInvalidUriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x34f0  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x34f5  ldstr    aHttpmessagepar_2// "HttpMessageParserInvalidUriScheme"
0x34fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x34ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3504  ret
```
