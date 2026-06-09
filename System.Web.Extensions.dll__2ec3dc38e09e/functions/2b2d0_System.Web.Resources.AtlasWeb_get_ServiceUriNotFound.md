# System.Web.Resources.AtlasWeb::get_ServiceUriNotFound

- ea: `0x2b2d0`
- end: `0x2b2e5`
- name: `System.Web.Resources.AtlasWeb::get_ServiceUriNotFound`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33d70`
- `0x350a0`
- `0x35810`

## callees

- `0x28080`

## string_xrefs

- `0x2b2d5`: `ServiceUriNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x2b2d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b2d5  ldstr    aServiceurinotf// "ServiceUriNotFound"
0x2b2da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b2df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b2e4  ret
```
