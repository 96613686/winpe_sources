# ServiceManager::CleanupRegistryState(void)

- ea: `0x180013684`
- end: `0x180013867`
- name: `?CleanupRegistryState@ServiceManager@@AEAAJXZ`
- size: `483`
- prototype: `int __fastcall(ServiceManager *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180013870`
- `0x180018508`

## callees

- `0x180013684`
- `0x1800203f0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800136b4`

## string_xrefs

- `0x18001380e`: `LastMapUpdateNotification`
- `0x18001368a`: `MigrationUpdateCheck`
- `0x1800137bd`: `IsAutoUpdate`
- `0x1800137a2`: `AutoUpdateInProgress`
- `0x180013844`: `LastMapUpdateDate`
- `0x180013829`: `LastMapUpdateCheck`
- `0x180013751`: `MapUpdate`
- `0x1800136a6`: `ServiceManager::CleanupRegistryState`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ServiceManager::CleanupRegistryState(ServiceManager *this)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // r8d
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx

  v2 = RegUtils::DeleteMapsPersistedRegValue((__int64)this, L"MigrationUpdateCheck");
  if ( v2 < 0 )
  {
    v4 = 3995;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v3, L"DataProviderSetChanged");
  if ( v2 < 0 )
  {
    v4 = 3996;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v6, L"UseMOSStack");
  if ( v2 < 0 )
  {
    v4 = 3997;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v7, L"CurrentOperation");
  if ( v2 < 0 )
  {
    v4 = 4000;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v8, L"QueuedPackageIds");
  if ( v2 < 0 )
  {
    v4 = 4001;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v9, L"QueuedPackageOpInfos");
  if ( v2 < 0 )
  {
    v4 = 4002;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v10, L"QueuedPackageOpTriggers");
  if ( v2 < 0 )
  {
    v4 = 4003;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v11, L"MapUpdate");
  if ( v2 < 0 )
  {
    v4 = 4004;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v12, L"MigrationTargetDeviceGuid");
  if ( v2 < 0 )
  {
    v4 = 4005;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v13, L"MigrationFlags");
  if ( v2 < 0 )
  {
    v4 = 4006;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v14, L"AutoUpdateInProgress");
  if ( v2 < 0 )
  {
    v4 = 4008;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v15, L"IsAutoUpdate");
  if ( v2 < 0 )
  {
    v4 = 4009;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v16, L"CurrentOperationStartTime");
  if ( v2 < 0 )
  {
    v4 = 4010;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v17, L"CurrentOperationActiveTime");
  if ( v2 < 0 )
  {
    v4 = 4011;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v18, L"LastMapUpdateNotification");
  if ( v2 < 0 )
  {
    v4 = 4013;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v19, L"LastMapUpdateCheck");
  if ( v2 < 0 )
  {
    v4 = 4014;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  v2 = RegUtils::DeleteMapsPersistedRegValue(v20, L"LastMapUpdateDate");
  if ( v2 < 0 )
  {
    v4 = 4015;
    return ZTraceReportPropagation(v2, "ServiceManager::CleanupRegistryState", v4, this);
  }
  return 0;
}

```

## disassembly

```asm
0x180013684  push    rbx
0x180013686  sub     rsp, 20h
0x18001368a  lea     rdx, aMigrationupdat; "MigrationUpdateCheck"
0x180013691  mov     rbx, rcx
0x180013694  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013699  test    eax, eax
0x18001369b  jns     short loc_1800136BB
0x18001369d  mov     r8d, 0F9Bh
0x1800136a3  mov     r9, rbx
0x1800136a6  lea     rdx, aServicemanager_15; "ServiceManager::CleanupRegistryState"
0x1800136ad  mov     ecx, eax
0x1800136af  add     rsp, 20h
0x1800136b3  pop     rbx
0x1800136b4  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800136bb  lea     rdx, aDataproviderse; "DataProviderSetChanged"
0x1800136c2  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800136c7  test    eax, eax
0x1800136c9  jns     short loc_1800136D3
0x1800136cb  mov     r8d, 0F9Ch
0x1800136d1  jmp     short loc_1800136A3
0x1800136d3  lea     rdx, aUsemosstack; "UseMOSStack"
0x1800136da  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800136df  test    eax, eax
0x1800136e1  jns     short loc_1800136EB
0x1800136e3  mov     r8d, 0F9Dh
0x1800136e9  jmp     short loc_1800136A3
0x1800136eb  lea     rdx, aCurrentoperati_0; "CurrentOperation"
0x1800136f2  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800136f7  test    eax, eax
0x1800136f9  jns     short loc_180013703
0x1800136fb  mov     r8d, 0FA0h
0x180013701  jmp     short loc_1800136A3
0x180013703  lea     rdx, aQueuedpackagei_0; "QueuedPackageIds"
0x18001370a  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001370f  test    eax, eax
0x180013711  jns     short loc_18001371B
0x180013713  mov     r8d, 0FA1h
0x180013719  jmp     short loc_1800136A3
0x18001371b  lea     rdx, aQueuedpackageo_2; "QueuedPackageOpInfos"
0x180013722  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013727  test    eax, eax
0x180013729  jns     short loc_180013736
0x18001372b  mov     r8d, 0FA2h
0x180013731  jmp     loc_1800136A3
0x180013736  lea     rdx, aQueuedpackageo_3; "QueuedPackageOpTriggers"
0x18001373d  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013742  test    eax, eax
0x180013744  jns     short loc_180013751
0x180013746  mov     r8d, 0FA3h
0x18001374c  jmp     loc_1800136A3
0x180013751  lea     rdx, aMapupdate; "MapUpdate"
0x180013758  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001375d  test    eax, eax
0x18001375f  jns     short loc_18001376C
0x180013761  mov     r8d, 0FA4h
0x180013767  jmp     loc_1800136A3
0x18001376c  lea     rdx, aMigrationtarge_0; "MigrationTargetDeviceGuid"
0x180013773  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013778  test    eax, eax
0x18001377a  jns     short loc_180013787
0x18001377c  mov     r8d, 0FA5h
0x180013782  jmp     loc_1800136A3
0x180013787  lea     rdx, aMigrationflags_0; "MigrationFlags"
0x18001378e  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013793  test    eax, eax
0x180013795  jns     short loc_1800137A2
0x180013797  mov     r8d, 0FA6h
0x18001379d  jmp     loc_1800136A3
0x1800137a2  lea     rdx, aAutoupdateinpr; "AutoUpdateInProgress"
0x1800137a9  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800137ae  test    eax, eax
0x1800137b0  jns     short loc_1800137BD
0x1800137b2  mov     r8d, 0FA8h
0x1800137b8  jmp     loc_1800136A3
0x1800137bd  lea     rdx, aIsautoupdate; "IsAutoUpdate"
0x1800137c4  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800137c9  test    eax, eax
0x1800137cb  jns     short loc_1800137D8
0x1800137cd  mov     r8d, 0FA9h
0x1800137d3  jmp     loc_1800136A3
0x1800137d8  lea     rdx, ValueName; "CurrentOperationStartTime"
0x1800137df  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800137e4  test    eax, eax
0x1800137e6  jns     short loc_1800137F3
0x1800137e8  mov     r8d, 0FAAh
0x1800137ee  jmp     loc_1800136A3
0x1800137f3  lea     rdx, aCurrentoperati; "CurrentOperationActiveTime"
0x1800137fa  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800137ff  test    eax, eax
0x180013801  jns     short loc_18001380E
0x180013803  mov     r8d, 0FABh
0x180013809  jmp     loc_1800136A3
0x18001380e  lea     rdx, aLastmapupdaten; "LastMapUpdateNotification"
0x180013815  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001381a  test    eax, eax
0x18001381c  jns     short loc_180013829
0x18001381e  mov     r8d, 0FADh
0x180013824  jmp     loc_1800136A3
0x180013829  lea     rdx, aLastmapupdatec; "LastMapUpdateCheck"
0x180013830  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013835  test    eax, eax
0x180013837  jns     short loc_180013844
0x180013839  mov     r8d, 0FAEh
0x18001383f  jmp     loc_1800136A3
0x180013844  lea     rdx, aLastmapupdated; "LastMapUpdateDate"
0x18001384b  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180013850  test    eax, eax
0x180013852  jns     short loc_18001385F
0x180013854  mov     r8d, 0FAFh
0x18001385a  jmp     loc_1800136A3
0x18001385f  xor     eax, eax
0x180013861  add     rsp, 20h
0x180013865  pop     rbx
0x180013866  retn
```
