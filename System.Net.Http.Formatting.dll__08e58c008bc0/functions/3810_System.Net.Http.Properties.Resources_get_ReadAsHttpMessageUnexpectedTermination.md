# System.Net.Http.Properties.Resources::get_ReadAsHttpMessageUnexpectedTermination

- ea: `0x3810`
- end: `0x3825`
- name: `System.Net.Http.Properties.Resources::get_ReadAsHttpMessageUnexpectedTermination`
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

- `0x3815`: `ReadAsHttpMessageUnexpectedTermination`

## pseudocode

```c

```

## disassembly

```asm
0x3810  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3815  ldstr    aReadashttpmess// "ReadAsHttpMessageUnexpectedTermination"
0x381a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x381f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3824  ret
```
