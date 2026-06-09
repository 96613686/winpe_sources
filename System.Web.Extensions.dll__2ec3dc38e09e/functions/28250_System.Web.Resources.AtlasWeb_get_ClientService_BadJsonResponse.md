# System.Web.Resources.AtlasWeb::get_ClientService_BadJsonResponse

- ea: `0x28250`
- end: `0x28265`
- name: `System.Web.Resources.AtlasWeb::get_ClientService_BadJsonResponse`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x36b00`

## callees

- `0x28080`

## string_xrefs

- `0x28255`: `ClientService_BadJsonResponse`

## pseudocode

```c

```

## disassembly

```asm
0x28250  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28255  ldstr    aClientserviceB// "ClientService_BadJsonResponse"
0x2825a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2825f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28264  ret
```
