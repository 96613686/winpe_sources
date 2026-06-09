# System.Web.Resources.AtlasWeb::get_RoleService_RolesFeatureNotEnabled

- ea: `0x2a810`
- end: `0x2a825`
- name: `System.Web.Resources.AtlasWeb::get_RoleService_RolesFeatureNotEnabled`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x38ee0`

## callees

- `0x28080`

## string_xrefs

- `0x2a815`: `RoleService_RolesFeatureNotEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x2a810  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2a815  ldstr    aRoleserviceRol_0// "RoleService_RolesFeatureNotEnabled"
0x2a81a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2a81f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2a824  ret
```
