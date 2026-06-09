# System.Web.Http.Properties.CommonWebApiResources::get_ArgumentInvalidHttpUriScheme

- ea: `0xb8d0`
- end: `0xb8e5`
- name: `System.Web.Http.Properties.CommonWebApiResources::get_ArgumentInvalidHttpUriScheme`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb340`

## callees

- `0xb820`

## string_xrefs

- `0xb8d5`: `ArgumentInvalidHttpUriScheme`

## pseudocode

```c

```

## disassembly

```asm
0xb8d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Http.Properties.CommonWebApiResources::get_ResourceManager()
0xb8d5  ldstr    aArgumentinvali_0// "ArgumentInvalidHttpUriScheme"
0xb8da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Http.Properties.CommonWebApiResources::resourceCulture
0xb8df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xb8e4  ret
```
