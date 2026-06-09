# System.Web.Resources.AtlasWeb::get_RoleServiceManager_LoadRolesWithNonDefaultPath

- ea: `0x2a850`
- end: `0x2a865`
- name: `System.Web.Resources.AtlasWeb::get_RoleServiceManager_LoadRolesWithNonDefaultPath`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x12a30`

## callees

- `0x28080`

## string_xrefs

- `0x2a855`: `RoleServiceManager_LoadRolesWithNonDefaultPath`

## pseudocode

```c

```

## disassembly

```asm
0x2a850  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2a855  ldstr    aRoleserviceman_0// "RoleServiceManager_LoadRolesWithNonDefa"...
0x2a85a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2a85f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2a864  ret
```
