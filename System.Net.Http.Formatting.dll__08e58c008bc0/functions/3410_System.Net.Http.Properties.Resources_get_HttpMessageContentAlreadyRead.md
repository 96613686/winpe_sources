# System.Net.Http.Properties.Resources::get_HttpMessageContentAlreadyRead

- ea: `0x3410`
- end: `0x3425`
- name: `System.Net.Http.Properties.Resources::get_HttpMessageContentAlreadyRead`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x2560`

## callees

- `0x30a0`

## string_xrefs

- `0x3415`: `HttpMessageContentAlreadyRead`

## pseudocode

```c

```

## disassembly

```asm
0x3410  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3415  ldstr    aHttpmessagecon// "HttpMessageContentAlreadyRead"
0x341a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x341f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3424  ret
```
