# ServiceManager::CollectChinaVariantTelemetry(void)

- ea: `0x180013e7c`
- end: `0x180013f11`
- name: `?CollectChinaVariantTelemetry@ServiceManager@@AEAAXXZ`
- size: `149`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180016e80`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x180013e7c`
- `0x18001d678`
- `0x180020720`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013eb4`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013ee9`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013eb4`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013ee9`

## string_xrefs

- `0x180013ea5`: `ServiceManager::CollectChinaVariantTelemetry`
- `0x180013eda`: `ServiceManager::CollectChinaVariantTelemetry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceManager::CollectChinaVariantTelemetry(ServiceManager *this)
{
  int MapsPersistedRegBoolean; // eax
  __int64 v3; // rcx
  int v4; // eax
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  OfflineMapsTelemetry *v7; // rcx
  bool v8; // [rsp+38h] [rbp+10h] BYREF
  bool v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(this, L"ChinaVariant", 0, &v9);
  if ( MapsPersistedRegBoolean < 0 )
    ZTraceReportIgnore(MapsPersistedRegBoolean, "ServiceManager::CollectChinaVariantTelemetry", 617, this);
  v8 = 0;
  v4 = RegUtils::GetMapsPersistedRegBoolean(v3, L"OEMChinaVariantWin10", 0, &v8);
  if ( v4 < 0 )
    ZTraceReportIgnore(v4, "ServiceManager::CollectChinaVariantTelemetry", 621, this);
  if ( OfflineMapsTelemetry::IsEnabled(v6, v5) )
  {
    OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::TraceChinaVariantKey_(v7, v9, v8);
  }
}

```

## disassembly

```asm
0x180013e7c  push    rbx
0x180013e7e  sub     rsp, 20h
0x180013e82  lea     r9, [rsp+28h+arg_10]
0x180013e87  mov     [rsp+28h+arg_10], 0
0x180013e8c  xor     r8d, r8d
0x180013e8f  lea     rdx, aChinavariant; "ChinaVariant"
0x180013e96  mov     rbx, rcx
0x180013e99  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180013e9e  test    eax, eax
0x180013ea0  jns     short loc_180013EBA
0x180013ea2  mov     r9, rbx
0x180013ea5  lea     rdx, aServicemanager_50; "ServiceManager::CollectChinaVariantTele"...
0x180013eac  mov     r8d, 269h
0x180013eb2  mov     ecx, eax
0x180013eb4  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180013eba  lea     r9, [rsp+28h+arg_8]
0x180013ebf  mov     [rsp+28h+arg_8], 0
0x180013ec4  xor     r8d, r8d
0x180013ec7  lea     rdx, aOemchinavarian; "OEMChinaVariantWin10"
0x180013ece  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180013ed3  test    eax, eax
0x180013ed5  jns     short loc_180013EEF
0x180013ed7  mov     r9, rbx
0x180013eda  lea     rdx, aServicemanager_50; "ServiceManager::CollectChinaVariantTele"...
0x180013ee1  mov     r8d, 26Dh
0x180013ee7  mov     ecx, eax
0x180013ee9  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180013eef  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180013ef4  test    al, al
0x180013ef6  jz      short loc_180013F0B
0x180013ef8  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180013efd  mov     r8b, [rsp+28h+arg_8]; bool
0x180013f02  mov     dl, [rsp+28h+arg_10]; bool
0x180013f06  call    ?TraceChinaVariantKey_@OfflineMapsTelemetry@@QEAAX_N0@Z; OfflineMapsTelemetry::TraceChinaVariantKey_(bool,bool)
0x180013f0b  add     rsp, 20h
0x180013f0f  pop     rbx
0x180013f10  retn
```
