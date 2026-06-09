# System.Web.Resources.AtlasWeb::get_AppService_RequiredSSL

- ea: `0x28130`
- end: `0x28145`
- name: `System.Web.Resources.AtlasWeb::get_AppService_RequiredSSL`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x39200`

## callees

- `0x28080`

## string_xrefs

- `0x28135`: `AppService_RequiredSSL`

## pseudocode

```c

```

## disassembly

```asm
0x28130  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28135  ldstr    aAppserviceRequ// "AppService_RequiredSSL"
0x2813a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2813f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28144  ret
```
