# System.Web.Http.Properties.CommonWebApiResources::get_ArgumentUriHasQueryOrFragment

- ea: `0xb950`
- end: `0xb965`
- name: `System.Web.Http.Properties.CommonWebApiResources::get_ArgumentUriHasQueryOrFragment`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb390`

## callees

- `0xb820`

## string_xrefs

- `0xb955`: `ArgumentUriHasQueryOrFragment`

## pseudocode

```c

```

## disassembly

```asm
0xb950  call     class [mscorlib]System.Resources.ResourceManager System.Web.Http.Properties.CommonWebApiResources::get_ResourceManager()
0xb955  ldstr    aArgumenturihas// "ArgumentUriHasQueryOrFragment"
0xb95a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Http.Properties.CommonWebApiResources::resourceCulture
0xb95f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xb964  ret
```
