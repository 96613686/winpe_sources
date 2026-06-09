# System.Web.UI.RoleServiceManager::GenerateInitializationScript

- ea: `0x12a30`
- end: `0x12b62`
- name: `System.Web.UI.RoleServiceManager::GenerateInitializationScript`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x12990`

## callees

- `0x12a30`
- `0x2a850`
- `0x31d00`
- `0x31f10`
- `0x39150`

## string_xrefs

- `0x12a4c`: `~/Role_JSON_AppService.axd`
- `0x12a90`: `~/Role_JSON_AppService.axd`
- `0x12a59`: `Sys.Services._RoleService.DefaultWebServicePath = '`
- `0x12ac6`: `Sys.Services.RoleService.set_path('`
- `0x12b35`: `Sys.Services.RoleService._roles = `

## pseudocode

```c

```

## disassembly

```asm
0x12a30  call     bool System.Web.ApplicationServices.ApplicationServiceHelper::get_RoleServiceEnabled()
0x12a35  stloc.0
0x12a36  ldnull
0x12a37  stloc.1
0x12a38  ldloc.0
0x12a39  brfalse.s loc_12A7F
0x12a3b  ldarg.0
0x12a3c  ldind.ref
0x12a3d  brtrue.s loc_12A4B
0x12a3f  ldarg.0
0x12a40  ldc.i4   0x80
0x12a45  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x12a4a  stind.ref
0x12a4b  ldarg.2
0x12a4c  ldstr    aRoleJsonAppser// "~/Role_JSON_AppService.axd"
0x12a51  callvirt instance string [System.Web]System.Web.UI.Control::ResolveClientUrl(string)
0x12a56  stloc.1
0x12a57  ldarg.0
0x12a58  ldind.ref
0x12a59  ldstr    aSysServicesRol// "Sys.Services._RoleService.DefaultWebSer"...
0x12a5e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a63  pop
0x12a64  ldarg.0
0x12a65  ldind.ref
0x12a66  ldloc.1
0x12a67  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0x12a6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a71  pop
0x12a72  ldarg.0
0x12a73  ldind.ref
0x12a74  ldstr    asc_3FB16// "';\n"
0x12a79  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a7e  pop
0x12a7f  ldarg.3
0x12a80  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12a85  ldc.i4.0
0x12a86  ceq
0x12a88  stloc.2
0x12a89  ldloc.2
0x12a8a  brfalse.s loc_12AEC
0x12a8c  ldloc.1
0x12a8d  brtrue.s loc_12A9B
0x12a8f  ldarg.2
0x12a90  ldstr    aRoleJsonAppser// "~/Role_JSON_AppService.axd"
0x12a95  callvirt instance string [System.Web]System.Web.UI.Control::ResolveClientUrl(string)
0x12a9a  stloc.1
0x12a9b  ldarg.s  4
0x12a9d  brfalse.s loc_12AB4
0x12a9f  ldarg.3
0x12aa0  ldloc.1
0x12aa1  ldc.i4.5
0x12aa2  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x12aa7  brtrue.s loc_12AB4
0x12aa9  call     string System.Web.Resources.AtlasWeb::get_RoleServiceManager_LoadRolesWithNonDefaultPath()
0x12aae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x12ab3  throw
0x12ab4  ldarg.0
0x12ab5  ldind.ref
0x12ab6  brtrue.s loc_12AC4
0x12ab8  ldarg.0
0x12ab9  ldc.i4   0x80
0x12abe  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x12ac3  stind.ref
0x12ac4  ldarg.0
0x12ac5  ldind.ref
0x12ac6  ldstr    aSysServicesRol_0// "Sys.Services.RoleService.set_path('"
0x12acb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12ad0  pop
0x12ad1  ldarg.0
0x12ad2  ldind.ref
0x12ad3  ldarg.3
0x12ad4  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0x12ad9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12ade  pop
0x12adf  ldarg.0
0x12ae0  ldind.ref
0x12ae1  ldstr    asc_3FB7A// "');\n"
0x12ae6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12aeb  pop
0x12aec  ldarg.s  4
0x12aee  brfalse.s loc_12B61
0x12af0  ldarg.2
0x12af1  callvirt instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x12af6  brfalse.s loc_12B16
0x12af8  ldarg.0
0x12af9  ldind.ref
0x12afa  brtrue.s loc_12B08
0x12afc  ldarg.0
0x12afd  ldc.i4   0x80
0x12b02  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x12b07  stind.ref
0x12b08  ldarg.0
0x12b09  ldind.ref
0x12b0a  ldstr    aLoadroles// "// loadRoles\n"
0x12b0f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12b14  pop
0x12b15  ret
0x12b16  call     string[] [System.Web]System.Web.Security.Roles::GetRolesForUser()
0x12b1b  stloc.3
0x12b1c  ldloc.3
0x12b1d  brfalse.s loc_12B61
0x12b1f  ldloc.3
0x12b20  ldlen
0x12b21  brfalse.s loc_12B61
0x12b23  ldarg.0
0x12b24  ldind.ref
0x12b25  brtrue.s loc_12B33
0x12b27  ldarg.0
0x12b28  ldc.i4   0x80
0x12b2d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x12b32  stind.ref
0x12b33  ldarg.0
0x12b34  ldind.ref
0x12b35  ldstr    aSysServicesRol_1// "Sys.Services.RoleService._roles = "
0x12b3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12b3f  pop
0x12b40  ldarg.0
0x12b41  ldind.ref
0x12b42  newobj   instance void System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x12b47  ldloc.3
0x12b48  ldc.i4.1
0x12b49  call     instance string System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object obj, valuetype SerializationFormat serializationFormat)
0x12b4e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12b53  pop
0x12b54  ldarg.0
0x12b55  ldind.ref
0x12b56  ldstr    asc_40496// ";\n"
0x12b5b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12b60  pop
0x12b61  ret
```
