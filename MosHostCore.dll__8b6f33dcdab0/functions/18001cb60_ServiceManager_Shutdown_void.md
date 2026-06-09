# ServiceManager::Shutdown(void)

- ea: `0x18001cb60`
- end: `0x18001cc42`
- name: `?Shutdown@ServiceManager@@UEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x1800125f8`
- `0x1800134b8`
- `0x1800181d0`
- `0x18001cb60`
- `0x18001d870`
- `0x1800228ec`
- `0x1800229b8`
- `0x1800229d4`
- `0x180022a00`

## import_xrefs

- `BingOnlineServices!?Teardown@ServiceRequestHelper@BingOnlineServices@@SAXXZ` at `0x18001cb82`
- `BingOnlineServices!?Teardown@ServiceRequestHelper@BingOnlineServices@@SAXXZ` at `0x18001cb82`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001cbab`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001cbab`
- `ZTrace_Maps!ZTraceHelper` at `0x18001cc0b`
- `ZTrace_Maps!ZTraceHelper` at `0x18001cc0b`

## string_xrefs

- `0x18001cba2`: `ServiceManager::Shutdown`
- `0x18001cbff`: `ServiceManager::Shutdown`
- `0x18001cbea`: `[MosHost] Service - Shutting down the service with service in the initialized state`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::Shutdown(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // eax
  __int64 v3; // rcx
  struct _TP_POOL **SpinCount; // rdx
  OfflineMapsTelemetry *v5; // rax
  _BYTE v7[24]; // [rsp+30h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock(this + 85, (__int64)v7);
  BYTE3(this[107].SpinCount) = 1;
  BingOnlineServices::ServiceRequestHelper::Teardown();
  v2 = ServiceManager::CancelOperationAndWait(this, 2);
  if ( v2 < 0 )
    ZTraceReportIgnore(v2, "ServiceManager::Shutdown", 198, this);
  RelockableGate::Unlock((RelockableGate *)v7);
  SpinCount = (struct _TP_POOL **)this[84].SpinCount;
  this[84].SpinCount = 0;
  if ( SpinCount )
    std::default_delete<Threadpool>::operator()(v3, SpinCount);
  RelockableGate::Relock((RelockableGate *)v7);
  if ( this[88].LockCount )
  {
    ZTraceHelper(
      2,
      "ServiceManager::Shutdown",
      212,
      this,
      "[MosHost] Service - Shutting down the service with service in the initialized state");
    ServiceManager::UninitializeService((ServiceManager *)this);
  }
  if ( OfflineMapsTelemetry::IsEnabled() )
  {
    v5 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::MapsBrokerServiceShutdown_(v5);
  }
  RelockableGate::~RelockableGate((RelockableGate *)v7);
  return 0;
}

```

## disassembly

```asm
0x18001cb60  push    rbx
0x18001cb62  sub     rsp, 40h
0x18001cb66  mov     rbx, rcx
0x18001cb69  add     rcx, 0D48h
0x18001cb70  lea     rdx, [rsp+48h+var_18]
0x18001cb75  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001cb7a  nop
0x18001cb7b  mov     byte ptr [rbx+10DBh], 1
0x18001cb82  call    cs:__imp_?Teardown@ServiceRequestHelper@BingOnlineServices@@SAXXZ; BingOnlineServices::ServiceRequestHelper::Teardown(void)
0x18001cb88  mov     edx, 2
0x18001cb8d  mov     rcx, rbx
0x18001cb90  call    ?CancelOperationAndWait@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperationAndWait(ServiceManager::CANCELLATION_TYPE)
0x18001cb95  test    eax, eax
0x18001cb97  jns     short loc_18001CBB1
0x18001cb99  mov     r9, rbx
0x18001cb9c  mov     r8d, 0C6h
0x18001cba2  lea     rdx, aServicemanager_14; "ServiceManager::Shutdown"
0x18001cba9  mov     ecx, eax
0x18001cbab  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001cbb1  lea     rcx, [rsp+48h+var_18]; this
0x18001cbb6  call    ?Unlock@RelockableGate@@QEAAXXZ; RelockableGate::Unlock(void)
0x18001cbbb  mov     rdx, [rbx+0D40h]
0x18001cbc2  mov     qword ptr [rbx+0D40h], 0
0x18001cbcd  test    rdx, rdx
0x18001cbd0  jz      short loc_18001CBD7
0x18001cbd2  call    ??R?$default_delete@VThreadpool@@@std@@QEBAXPEAVThreadpool@@@Z; std::default_delete<Threadpool>::operator()(Threadpool *)
0x18001cbd7  lea     rcx, [rsp+48h+var_18]; this
0x18001cbdc  call    ?Relock@RelockableGate@@QEAAXXZ; RelockableGate::Relock(void)
0x18001cbe1  cmp     dword ptr [rbx+0DC8h], 0
0x18001cbe8  jz      short loc_18001CC19
0x18001cbea  lea     rax, aMoshostService_4; "[MosHost] Service - Shutting down the s"...
0x18001cbf1  mov     [rsp+48h+var_28], rax
0x18001cbf6  mov     r9, rbx
0x18001cbf9  mov     r8d, 0D4h
0x18001cbff  lea     rdx, aServicemanager_14; "ServiceManager::Shutdown"
0x18001cc06  mov     ecx, 2
0x18001cc0b  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001cc11  mov     rcx, rbx; this
0x18001cc14  call    ?UninitializeService@ServiceManager@@AEAAXXZ; ServiceManager::UninitializeService(void)
0x18001cc19  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001cc1e  test    al, al
0x18001cc20  jz      short loc_18001CC30
0x18001cc22  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001cc27  mov     rcx, rax; this
0x18001cc2a  call    ?MapsBrokerServiceShutdown_@OfflineMapsTelemetry@@QEAAXXZ; OfflineMapsTelemetry::MapsBrokerServiceShutdown_(void)
0x18001cc2f  nop
0x18001cc30  lea     rcx, [rsp+48h+var_18]; this
0x18001cc35  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001cc3a  xor     eax, eax
0x18001cc3c  add     rsp, 40h
0x18001cc40  pop     rbx
0x18001cc41  retn
```
