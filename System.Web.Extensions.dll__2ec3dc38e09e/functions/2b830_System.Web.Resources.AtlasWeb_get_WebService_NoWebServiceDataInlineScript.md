# System.Web.Resources.AtlasWeb::get_WebService_NoWebServiceDataInlineScript

- ea: `0x2b830`
- end: `0x2b845`
- name: `System.Web.Resources.AtlasWeb::get_WebService_NoWebServiceDataInlineScript`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2e4b0`

## callees

- `0x28080`

## string_xrefs

- `0x2b835`: `WebService_NoWebServiceDataInlineScript`

## pseudocode

```c

```

## disassembly

```asm
0x2b830  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b835  ldstr    aWebserviceNowe_0// "WebService_NoWebServiceDataInlineScript"
0x2b83a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b83f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b844  ret
```
