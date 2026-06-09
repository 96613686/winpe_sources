# System.Web.Resources.AtlasWeb::get_RoleService_RoleProviderNotFound

- ea: `0x2a7f0`
- end: `0x2a805`
- name: `System.Web.Resources.AtlasWeb::get_RoleService_RoleProviderNotFound`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x38f00`

## callees

- `0x28080`

## string_xrefs

- `0x2a7f5`: `RoleService_RoleProviderNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x2a7f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2a7f5  ldstr    aRoleserviceRol// "RoleService_RoleProviderNotFound"
0x2a7fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2a7ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2a804  ret
```
