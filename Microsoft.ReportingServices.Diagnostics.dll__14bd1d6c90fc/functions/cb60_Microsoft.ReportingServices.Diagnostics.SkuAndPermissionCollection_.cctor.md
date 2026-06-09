# Microsoft.ReportingServices.Diagnostics.SkuAndPermissionCollection::.cctor

- ea: `0xcb60`
- end: `0xcd84`
- name: `Microsoft.ReportingServices.Diagnostics.SkuAndPermissionCollection::.cctor`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xb530`

## string_xrefs

- `0xcb7e`: `Create Roles`
- `0xcb8e`: `Delete Roles`
- `0xcb9e`: `Create Schedules`
- `0xcbae`: `Read Schedules`
- `0xcbbe`: `Delete Schedules`
- `0xcbce`: `Update Schedules`
- `0xcbee`: `Update Role Properties`
- `0xcc1e`: `Create Any Subscription`
- `0xcc2e`: `Create Report History`
- `0xcc3e`: `Create Subscription`
- `0xcc4e`: `Delete Any Subscription`
- `0xcc5e`: `Delete Report History`
- `0xcc6e`: `Delete Subscription`
- `0xcc8e`: `Read Policy`
- `0xcd5e`: `Read Policy`
- `0xcc9e`: `Update Policy`
- `0xcd6e`: `Update Policy`
- `0xccae`: `Read Any Subscription`
- `0xccbe`: `Create Model`
- `0xccce`: `Read Subscription`
- `0xccde`: `Update Any Subscription`
- `0xccee`: `Read Model Item Security Policies`
- `0xccfe`: `Update Model Item Security Policies`
- `0xcd0e`: `Update Subscription`
- `0xcd1e`: `Read Content`
- `0xcd2e`: `Read Properties`
- `0xcd3e`: `Update Content`
- `0xcd4e`: `Update Properties`

## pseudocode

```c

```

## disassembly

```asm
0xcb60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku>::.ctor()
0xcb65  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku> Microsoft.ReportingServices.Diagnostics.SkuAndPermissionCollection::m_skuAndPermissions
0xcb6a  newobj   instance void Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::.ctor()
0xcb6f  stloc.0
0xcb70  ldloc.0
0xcb71  ldc.i4.s 0x16
0xcb73  stfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::Sku
0xcb78  ldloc.0
0xcb79  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcb7e  ldstr    aCreateRoles// "Create Roles"
0xcb83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcb88  ldloc.0
0xcb89  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcb8e  ldstr    aDeleteRoles// "Delete Roles"
0xcb93  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcb98  ldloc.0
0xcb99  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcb9e  ldstr    aCreateSchedule// "Create Schedules"
0xcba3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcba8  ldloc.0
0xcba9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcbae  ldstr    aReadSchedules// "Read Schedules"
0xcbb3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcbb8  ldloc.0
0xcbb9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcbbe  ldstr    aDeleteSchedule// "Delete Schedules"
0xcbc3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcbc8  ldloc.0
0xcbc9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcbce  ldstr    aUpdateSchedule// "Update Schedules"
0xcbd3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcbd8  ldloc.0
0xcbd9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcbde  ldstr    aExecuteReportD// "Execute Report Definition"
0xcbe3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcbe8  ldloc.0
0xcbe9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcbee  ldstr    aUpdateRoleProp// "Update Role Properties"
0xcbf3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcbf8  ldloc.0
0xcbf9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcbfe  ldstr    aManageSharedSc// "Manage Shared Schedules"
0xcc03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc08  ldloc.0
0xcc09  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedSystemPermissions
0xcc0e  ldstr    aGenerateEvents// "Generate Events"
0xcc13  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc18  ldloc.0
0xcc19  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc1e  ldstr    aCreateAnySubsc// "Create Any Subscription"
0xcc23  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc28  ldloc.0
0xcc29  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc2e  ldstr    aCreateReportHi// "Create Report History"
0xcc33  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc38  ldloc.0
0xcc39  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc3e  ldstr    aCreateSubscrip// "Create Subscription"
0xcc43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc48  ldloc.0
0xcc49  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc4e  ldstr    aDeleteAnySubsc// "Delete Any Subscription"
0xcc53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc58  ldloc.0
0xcc59  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc5e  ldstr    aDeleteReportHi// "Delete Report History"
0xcc63  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc68  ldloc.0
0xcc69  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc6e  ldstr    aDeleteSubscrip// "Delete Subscription"
0xcc73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc78  ldloc.0
0xcc79  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc7e  ldstr    aListReportHist// "List Report History"
0xcc83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc88  ldloc.0
0xcc89  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc8e  ldstr    aReadPolicy// "Read Policy"
0xcc93  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcc98  ldloc.0
0xcc99  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcc9e  ldstr    aUpdatePolicy// "Update Policy"
0xcca3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcca8  ldloc.0
0xcca9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xccae  ldstr    aReadAnySubscri// "Read Any Subscription"
0xccb3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xccb8  ldloc.0
0xccb9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xccbe  ldstr    aCreateModel// "Create Model"
0xccc3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xccc8  ldloc.0
0xccc9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xccce  ldstr    aReadSubscripti// "Read Subscription"
0xccd3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xccd8  ldloc.0
0xccd9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xccde  ldstr    aUpdateAnySubsc// "Update Any Subscription"
0xcce3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcce8  ldloc.0
0xcce9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xccee  ldstr    aReadModelItemS// "Read Model Item Security Policies"
0xccf3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xccf8  ldloc.0
0xccf9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xccfe  ldstr    aUpdateModelIte// "Update Model Item Security Policies"
0xcd03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd08  ldloc.0
0xcd09  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedGeneralPermissions
0xcd0e  ldstr    aUpdateSubscrip// "Update Subscription"
0xcd13  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd18  ldloc.0
0xcd19  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedModelPermissions
0xcd1e  ldstr    aReadContent// "Read Content"
0xcd23  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd28  ldloc.0
0xcd29  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedModelPermissions
0xcd2e  ldstr    aReadProperties// "Read Properties"
0xcd33  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd38  ldloc.0
0xcd39  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedModelPermissions
0xcd3e  ldstr    aUpdateContent// "Update Content"
0xcd43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd48  ldloc.0
0xcd49  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedModelPermissions
0xcd4e  ldstr    aUpdateProperti// "Update Properties"
0xcd53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd58  ldloc.0
0xcd59  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedModelPermissions
0xcd5e  ldstr    aReadPolicy// "Read Policy"
0xcd63  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd68  ldloc.0
0xcd69  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku::RevokedModelPermissions
0xcd6e  ldstr    aUpdatePolicy// "Update Policy"
0xcd73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xcd78  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku> Microsoft.ReportingServices.Diagnostics.SkuAndPermissionCollection::m_skuAndPermissions
0xcd7d  ldloc.0
0xcd7e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RevokedPermissionsForSku>::Add(var<u1>)
0xcd83  ret
```
