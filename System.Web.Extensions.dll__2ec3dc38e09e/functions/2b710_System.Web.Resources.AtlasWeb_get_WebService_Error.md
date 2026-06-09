# System.Web.Resources.AtlasWeb::get_WebService_Error

- ea: `0x2b710`
- end: `0x2b725`
- name: `System.Web.Resources.AtlasWeb::get_WebService_Error`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2dc90`

## callees

- `0x28080`

## string_xrefs

- `0x2b715`: `WebService_Error`

## pseudocode

```c

```

## disassembly

```asm
0x2b710  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b715  ldstr    aWebserviceErro// "WebService_Error"
0x2b71a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b71f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b724  ret
```
