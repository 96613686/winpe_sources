# System.Web.Resources.AtlasWeb::get_WebService_RedirectError

- ea: `0x2b850`
- end: `0x2b865`
- name: `System.Web.Resources.AtlasWeb::get_WebService_RedirectError`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2be30`

## callees

- `0x28080`

## string_xrefs

- `0x2b855`: `WebService_RedirectError`

## pseudocode

```c

```

## disassembly

```asm
0x2b850  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b855  ldstr    aWebserviceRedi// "WebService_RedirectError"
0x2b85a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b85f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b864  ret
```
