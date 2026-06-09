# System.Web.Http.Properties.CommonWebApiResources::get_ArgumentInvalidAbsoluteUri

- ea: `0xb8b0`
- end: `0xb8c5`
- name: `System.Web.Http.Properties.CommonWebApiResources::get_ArgumentInvalidAbsoluteUri`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb370`

## callees

- `0xb820`

## string_xrefs

- `0xb8b5`: `ArgumentInvalidAbsoluteUri`

## pseudocode

```c

```

## disassembly

```asm
0xb8b0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Http.Properties.CommonWebApiResources::get_ResourceManager()
0xb8b5  ldstr    aArgumentinvali// "ArgumentInvalidAbsoluteUri"
0xb8ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Http.Properties.CommonWebApiResources::resourceCulture
0xb8bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xb8c4  ret
```
