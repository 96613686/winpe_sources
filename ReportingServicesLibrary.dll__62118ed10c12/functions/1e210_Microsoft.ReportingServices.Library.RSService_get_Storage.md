# Microsoft.ReportingServices.Library.RSService::get_Storage

- ea: `0x1e210`
- end: `0x1e24f`
- name: `Microsoft.ReportingServices.Library.RSService::get_Storage`
- size: `63`
- prototype: ``
- caller_count: `192`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x2d50`
- `0x2dc0`
- `0x2ff0`
- `0x32e0`
- `0x3440`
- `0x35f0`
- `0xb870`
- `0xbb60`
- `0xe590`
- `0xe730`
- `0xea90`
- `0xed90`
- `0xfac0`
- `0x10400`
- `0x105e0`
- `0x116e0`
- `0x11f60`
- `0x16fe0`
- `0x17130`
- `0x17210`
- `0x17680`
- `0x17760`
- `0x18480`
- `0x190b0`
- `0x19150`
- `0x19880`
- `0x19890`
- `0x1a3a0`
- `0x1a580`
- `0x1bc40`
- `0x1bd80`
- `0x1bdf0`
- `0x1c310`
- `0x1c5e0`
- `0x1c8f0`
- `0x1d290`
- `0x1d360`
- `0x1d420`
- `0x1daf0`
- `0x1dd70`
- `0x1e1f0`
- `0x1f340`
- `0x1fa40`
- `0x20000`
- `0x20060`
- `0x20330`
- `0x203b0`
- `0x20810`
- `0x20ac0`
- `0x20db0`

## callees

- `0x1e210`
- `0x1e290`
- `0x1e3c0`
- `0x1e940`

## string_xrefs

- `0x1e218`: `Storage access outside guarded area.`

## pseudocode

```c

```

## disassembly

```asm
0x1e210  ldarg.0
0x1e211  ldfld    bool Microsoft.ReportingServices.Library.RSService::m_willDisconnectStorage
0x1e216  brtrue.s loc_1E223
0x1e218  ldstr    aStorageAccessO// "Storage access outside guarded area."
0x1e21d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x1e222  throw
0x1e223  ldarg.0
0x1e224  ldfld    class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSService::m_Storage
0x1e229  brtrue.s loc_1E248
0x1e22b  ldarg.0
0x1e22c  ldarg.0
0x1e22d  call     instance class Microsoft.ReportingServices.Library.RSServiceHelper Microsoft.ReportingServices.Library.RSService::get_ServiceHelper()
0x1e232  callvirt instance class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSServiceHelper::GetStorageInternal()
0x1e237  stfld    class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSService::m_Storage
0x1e23c  ldarg.0
0x1e23d  ldarg.0
0x1e23e  ldfld    class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSService::m_Storage
0x1e243  call     instance void Microsoft.ReportingServices.Library.RSService::ConnectStorage(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage storage)
0x1e248  ldarg.0
0x1e249  ldfld    class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSService::m_Storage
0x1e24e  ret
```
