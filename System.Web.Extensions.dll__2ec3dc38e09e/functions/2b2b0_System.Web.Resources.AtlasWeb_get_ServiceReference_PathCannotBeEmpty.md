# System.Web.Resources.AtlasWeb::get_ServiceReference_PathCannotBeEmpty

- ea: `0x2b2b0`
- end: `0x2b2c5`
- name: `System.Web.Resources.AtlasWeb::get_ServiceReference_PathCannotBeEmpty`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x19130`

## callees

- `0x28080`

## string_xrefs

- `0x2b2b5`: `ServiceReference_PathCannotBeEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x2b2b0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b2b5  ldstr    aServicereferen_1// "ServiceReference_PathCannotBeEmpty"
0x2b2ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b2bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b2c4  ret
```
