# ServiceManager::OnMigrationComplete(long,std::vector<uint,std::allocator<uint>> const &)

- ea: `0x18001ac90`
- end: `0x18001ae9e`
- name: `?OnMigrationComplete@ServiceManager@@UEAAXJAEBV?$vector@IV?$allocator@I@std@@@std@@@Z`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009c04`
- `0x18000ea5c`
- `0x18000ec18`
- `0x180014c00`
- `0x180015898`
- `0x180015ed0`
- `0x18001ac90`
- `0x18001b068`
- `0x18001ba6c`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001ae7e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001ae7e`
- `MosStorage!MosStorageSetMigrationState` at `0x18001acfc`
- `MosStorage!MosStorageSetMigrationState` at `0x18001acfc`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ad18`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ad45`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ada2`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001addf`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ae07`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ae48`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ad18`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ad45`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ada2`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001addf`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ae07`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ae48`

## string_xrefs

- `0x18001ad0f`: `ServiceManager::OnMigrationComplete`
- `0x18001ad3c`: `ServiceManager::OnMigrationComplete`
- `0x18001ad99`: `ServiceManager::OnMigrationComplete`
- `0x18001add6`: `ServiceManager::OnMigrationComplete`
- `0x18001adfe`: `ServiceManager::OnMigrationComplete`
- `0x18001ae3f`: `ServiceManager::OnMigrationComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceManager::OnMigrationComplete(__int64 a1, int a2, __int64 *a3)
{
  __int64 v6; // rbx
  bool v7; // r15
  __int64 v8; // r8
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int updated; // eax
  int v14; // eax
  _BYTE v15[72]; // [rsp+20h] [rbp-48h] BYREF

  CriticalSectionWithConditionVariable::Lock((struct _RTL_CRITICAL_SECTION *)(a1 + 3392), (__int64)v15);
  v6 = a1 - 8;
  *(_DWORD *)(a1 - 8 + 3520) = 0;
  *(_DWORD *)(a1 + 3516) = 0;
  v7 = a2 >= 0 && *a3 != a3[1];
  LOBYTE(v8) = PackageManager::AreMapsRegistered((PackageManager *)(a1 + 3560));
  v9 = MosStorageSetMigrationState(0, (unsigned int)a2, v8);
  if ( v9 < 0 )
    ZTraceReportIgnore(v9, "ServiceManager::OnMigrationComplete", 3719, (const void *)(a1 - 8));
  if ( *(_DWORD *)(a1 + 3524) != 2 )
  {
    v10 = ServiceManager::SerializeOperationState((ServiceManager *)(a1 - 8));
    if ( v10 < 0 )
      ZTraceReportIgnore(v10, "ServiceManager::OnMigrationComplete", 3723, (const void *)(a1 - 8));
  }
  if ( a2 < 0 )
  {
    *(_DWORD *)(v6 + 3536) = 1;
    *(_DWORD *)(v6 + 3540) = a2;
    ServiceManager::FireOdmlStateChange((ServiceManager *)(a1 - 8));
  }
  if ( ClientsTracker::HasClientsOf(a1 + 3808, 1) )
  {
    v11 = ServiceManager::EnsureServiceInitialized(a1 - 8, 1u);
    if ( v11 < 0 )
      ZTraceReportIgnore(v11, "ServiceManager::OnMigrationComplete", 3734, (const void *)(a1 - 8));
  }
  if ( v7 )
  {
    v12 = PackageManager::AddPackagesToInstall(a1 + 3560, (a3[1] - *a3) >> 2, *a3, 8);
    if ( v12 < 0 )
      ZTraceReportIgnore(v12, "ServiceManager::OnMigrationComplete", 3740, (const void *)(a1 - 8));
    updated = ServiceManager::ProcessPackageOrUpdateOperation((ServiceManager *)(a1 - 8));
    if ( updated < 0 )
      ZTraceReportIgnore(updated, "ServiceManager::OnMigrationComplete", 3741, (const void *)(a1 - 8));
  }
  else
  {
    if ( ClientsTracker::HasClientsOf(a1 + 3808, 2) )
    {
      v14 = ServiceManager::DetachClient(a1 - 8, 2u, 0);
      if ( v14 < 0 )
        ZTraceReportIgnore(v14, "ServiceManager::OnMigrationComplete", 3748, (const void *)(a1 - 8));
    }
    if ( !ClientsTracker::HasClientsOf(a1 + 3808, 1) )
    {
      *(_DWORD *)(v6 + 3536) = 0;
      *(_DWORD *)(v6 + 3540) = a2;
      ServiceManager::FireOdmlStateChange((ServiceManager *)(a1 - 8));
    }
  }
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 3432));
  RelockableGate::~RelockableGate((RelockableGate *)v15);
}

```

## disassembly

```asm
0x18001ac90  push    rbx
0x18001ac92  push    rbp
0x18001ac93  push    rsi
0x18001ac94  push    rdi
0x18001ac95  push    r12
0x18001ac97  push    r14
0x18001ac99  push    r15
0x18001ac9b  sub     rsp, 30h
0x18001ac9f  mov     r14, r8
0x18001aca2  mov     esi, edx
0x18001aca4  mov     rdi, rcx
0x18001aca7  add     rcx, 0D40h
0x18001acae  lea     rdx, [rsp+68h+var_48]
0x18001acb3  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001acb8  nop
0x18001acb9  lea     rbx, [rdi-8]
0x18001acbd  mov     dword ptr [rbx+0DC0h], 0
0x18001acc7  mov     dword ptr [rdi+0DBCh], 0
0x18001acd1  test    esi, esi
0x18001acd3  js      short loc_18001ACE3
0x18001acd5  mov     rax, [r14+8]
0x18001acd9  cmp     [r14], rax
0x18001acdc  jz      short loc_18001ACE3
0x18001acde  mov     r15b, 1
0x18001ace1  jmp     short loc_18001ACE6
0x18001ace3  xor     r15b, r15b
0x18001ace6  lea     r12, [rdi+0DE8h]
0x18001aced  mov     rcx, r12; this
0x18001acf0  call    ?AreMapsRegistered@PackageManager@@QEAA_NXZ; PackageManager::AreMapsRegistered(void)
0x18001acf5  mov     r8b, al
0x18001acf8  mov     edx, esi
0x18001acfa  xor     ecx, ecx
0x18001acfc  call    cs:__imp_?MosStorageSetMigrationState@@YAJW4__MIDL_mapsstorageapi_0002@@J_N@Z; MosStorageSetMigrationState(__MIDL_mapsstorageapi_0002,long,bool)
0x18001ad02  test    eax, eax
0x18001ad04  jns     short loc_18001AD1E
0x18001ad06  mov     r9, rbx
0x18001ad09  mov     r8d, 0E87h
0x18001ad0f  lea     rdx, aServicemanager_41; "ServiceManager::OnMigrationComplete"
0x18001ad16  mov     ecx, eax
0x18001ad18  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ad1e  cmp     dword ptr [rdi+0DC4h], 2
0x18001ad25  jz      short loc_18001AD4B
0x18001ad27  mov     rcx, rbx; this
0x18001ad2a  call    ?SerializeOperationState@ServiceManager@@AEAAJXZ; ServiceManager::SerializeOperationState(void)
0x18001ad2f  test    eax, eax
0x18001ad31  jns     short loc_18001AD4B
0x18001ad33  mov     r9, rbx
0x18001ad36  mov     r8d, 0E8Bh
0x18001ad3c  lea     rdx, aServicemanager_41; "ServiceManager::OnMigrationComplete"
0x18001ad43  mov     ecx, eax
0x18001ad45  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ad4b  test    esi, esi
0x18001ad4d  jns     short loc_18001AD67
0x18001ad4f  mov     dword ptr [rbx+0DD0h], 1
0x18001ad59  mov     [rbx+0DD4h], esi
0x18001ad5f  mov     rcx, rbx; this
0x18001ad62  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001ad67  lea     rbp, [rdi+0EE0h]
0x18001ad6e  mov     edx, 1
0x18001ad73  mov     rcx, rbp
0x18001ad76  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001ad7b  test    al, al
0x18001ad7d  jz      short loc_18001ADA8
0x18001ad7f  mov     edx, 1
0x18001ad84  mov     rcx, rbx
0x18001ad87  call    ?EnsureServiceInitialized@ServiceManager@@AEAAJW4MapsClientType@@@Z; ServiceManager::EnsureServiceInitialized(MapsClientType)
0x18001ad8c  test    eax, eax
0x18001ad8e  jns     short loc_18001ADA8
0x18001ad90  mov     r9, rbx
0x18001ad93  mov     r8d, 0E96h
0x18001ad99  lea     rdx, aServicemanager_41; "ServiceManager::OnMigrationComplete"
0x18001ada0  mov     ecx, eax
0x18001ada2  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ada8  test    r15b, r15b
0x18001adab  jz      short loc_18001AE0F
0x18001adad  mov     rdx, [r14+8]
0x18001adb1  sub     rdx, [r14]
0x18001adb4  sar     rdx, 2
0x18001adb8  mov     r9d, 8
0x18001adbe  mov     r8, [r14]
0x18001adc1  mov     rcx, r12
0x18001adc4  call    ?AddPackagesToInstall@PackageManager@@QEAAJKPEBIW4MapsOperationTrigger@@@Z; PackageManager::AddPackagesToInstall(ulong,uint const *,MapsOperationTrigger)
0x18001adc9  test    eax, eax
0x18001adcb  jns     short loc_18001ADE5
0x18001adcd  mov     r9, rbx
0x18001add0  mov     r8d, 0E9Ch
0x18001add6  lea     rdx, aServicemanager_41; "ServiceManager::OnMigrationComplete"
0x18001addd  mov     ecx, eax
0x18001addf  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ade5  mov     rcx, rbx; this
0x18001ade8  call    ?ProcessPackageOrUpdateOperation@ServiceManager@@AEAAJXZ; ServiceManager::ProcessPackageOrUpdateOperation(void)
0x18001aded  test    eax, eax
0x18001adef  jns     loc_18001AE77
0x18001adf5  mov     r9, rbx
0x18001adf8  mov     r8d, 0E9Dh
0x18001adfe  lea     rdx, aServicemanager_41; "ServiceManager::OnMigrationComplete"
0x18001ae05  mov     ecx, eax
0x18001ae07  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ae0d  jmp     short loc_18001AE77
0x18001ae0f  mov     r14d, 2
0x18001ae15  mov     edx, r14d
0x18001ae18  mov     rcx, rbp
0x18001ae1b  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001ae20  test    al, al
0x18001ae22  jz      short loc_18001AE4E
0x18001ae24  xor     r8d, r8d
0x18001ae27  mov     edx, r14d
0x18001ae2a  mov     rcx, rbx
0x18001ae2d  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x18001ae32  test    eax, eax
0x18001ae34  jns     short loc_18001AE4E
0x18001ae36  mov     r9, rbx
0x18001ae39  mov     r8d, 0EA4h
0x18001ae3f  lea     rdx, aServicemanager_41; "ServiceManager::OnMigrationComplete"
0x18001ae46  mov     ecx, eax
0x18001ae48  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ae4e  mov     edx, 1
0x18001ae53  mov     rcx, rbp
0x18001ae56  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x18001ae5b  test    al, al
0x18001ae5d  jnz     short loc_18001AE77
0x18001ae5f  mov     dword ptr [rbx+0DD0h], 0
0x18001ae69  mov     [rbx+0DD4h], esi
0x18001ae6f  mov     rcx, rbx; this
0x18001ae72  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001ae77  lea     rcx, [rdi+0D68h]; ConditionVariable
0x18001ae7e  call    cs:__imp_WakeAllConditionVariable
0x18001ae84  nop
0x18001ae85  lea     rcx, [rsp+68h+var_48]; this
0x18001ae8a  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001ae8f  add     rsp, 30h
0x18001ae93  pop     r15
0x18001ae95  pop     r14
0x18001ae97  pop     r12
0x18001ae99  pop     rdi
0x18001ae9a  pop     rsi
0x18001ae9b  pop     rbp
0x18001ae9c  pop     rbx
0x18001ae9d  retn
```
