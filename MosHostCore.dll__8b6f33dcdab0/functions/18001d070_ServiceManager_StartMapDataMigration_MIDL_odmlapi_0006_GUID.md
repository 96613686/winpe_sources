# ServiceManager::StartMapDataMigration(__MIDL_odmlapi_0006,_GUID)

- ea: `0x18001d070`
- end: `0x18001d21c`
- name: `?StartMapDataMigration@ServiceManager@@UEAAJW4__MIDL_odmlapi_0006@@U_GUID@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(__int64, int, GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x18001b848`

## callees

- `0x180009bb4`
- `0x18000c668`
- `0x18000ec18`
- `0x18001189c`
- `0x180015ed0`
- `0x18001d070`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MosStorage!MosStorageSetMigrationState` at `0x18001d11d`
- `MosStorage!MosStorageSetMigrationState` at `0x18001d1df`
- `MosStorage!MosStorageSetMigrationState` at `0x18001d11d`
- `MosStorage!MosStorageSetMigrationState` at `0x18001d1df`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001d154`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001d154`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d1b0`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d1b0`

## string_xrefs

- `0x18001d14b`: `ServiceManager::StartMapDataMigration`
- `0x18001d1a9`: `ServiceManager::StartMapDataMigration`

## pseudocode

```c
__int64 __fastcall ServiceManager::StartMapDataMigration(__int64 a1, int a2, GUID *a3)
{
  char v6; // si
  int v7; // r8d
  int v8; // ecx
  __int64 v9; // r8
  int v10; // eax
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // r8
  GUID v15; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v16[12]; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+3Ch] [rbp-4h]
  int v18; // [rsp+60h] [rbp+20h] BYREF
  int v19; // [rsp+64h] [rbp+24h]
  __int64 v20; // [rsp+68h] [rbp+28h] BYREF

  v6 = 0;
  CriticalSectionWithConditionVariable::Lock(a1 + 3400, v16);
  v18 = 1;
  v19 = 2;
  *(_QWORD *)&v15.Data1 = &v18;
  *(_QWORD *)v15.Data4 = &v20;
  if ( !(unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, &v15) )
    __int2c();
  if ( *(_DWORD *)(a1 + 3528) != 5 )
  {
    v7 = 3579;
    v8 = -2147024875;
LABEL_11:
    v11 = ZTraceReportOrigination(v8, "ServiceManager::StartMapDataMigration", v7, (const void *)a1);
    goto LABEL_12;
  }
  if ( *(_DWORD *)(a1 + 3520) || *(_DWORD *)(a1 + 3524) )
  {
    v7 = 3580;
    v8 = -2147024567;
    goto LABEL_11;
  }
  LOBYTE(v9) = PackageManager::AreMapsRegistered((PackageManager *)(a1 + 3568));
  MosStorageSetMigrationState(3, 0, v9);
  v15 = *a3;
  v10 = MigrationEngine::SetupMigration(a1 + 8, a2, &v15);
  if ( v10 >= 0 )
  {
    v12 = 0;
    *(_DWORD *)(a1 + 3524) = 10;
    *(_DWORD *)(a1 + 3520) = 6;
    *(_QWORD *)&v15.Data1 = ServiceManager::DoMigration;
    *(_DWORD *)v15.Data4 = 0;
    *(_DWORD *)&v15.Data4[4] = v17;
    Threadpool::QueueThis<ServiceManager>(*(PTP_CALLBACK_ENVIRON *)(a1 + 3392));
    goto LABEL_15;
  }
  v6 = 1;
  v11 = ZTraceReportPropagation(v10, "ServiceManager::StartMapDataMigration", 3585, (const void *)a1);
LABEL_12:
  v12 = v11;
  if ( v11 < 0 && v6 )
  {
    *(_QWORD *)(a1 + 3520) = 0;
    LOBYTE(v13) = PackageManager::AreMapsRegistered((PackageManager *)(a1 + 3568));
    MosStorageSetMigrationState(0, v12, v13);
    *(_DWORD *)(a1 + 3536) = 1;
    *(_DWORD *)(a1 + 3540) = v12;
    ServiceManager::FireOdmlStateChange((ServiceManager *)a1);
  }
LABEL_15:
  RelockableGate::~RelockableGate((RelockableGate *)v16);
  return v12;
}

```

## disassembly

```asm
0x18001d070  mov     [rsp-18h+arg_8], rbx
0x18001d075  mov     [rsp-18h+arg_10], rsi
0x18001d07a  push    rbp
0x18001d07b  push    rdi
0x18001d07c  push    r14
0x18001d07e  mov     rbp, rsp
0x18001d081  sub     rsp, 40h
0x18001d085  mov     rdi, r8
0x18001d088  mov     r14d, edx
0x18001d08b  mov     rbx, rcx
0x18001d08e  xor     sil, sil
0x18001d091  add     rcx, 0D48h
0x18001d098  lea     rdx, [rbp+var_10]
0x18001d09c  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x18001d0a1  nop
0x18001d0a2  mov     [rbp+arg_0], 1
0x18001d0a9  mov     [rbp+arg_4], 2
0x18001d0b0  lea     rax, [rbp+arg_0]
0x18001d0b4  mov     qword ptr [rbp+var_20], rax
0x18001d0b8  lea     rax, [rbp+arg_8]
0x18001d0bc  mov     qword ptr [rbp+var_20+8], rax
0x18001d0c0  lea     rcx, [rbx+0EE8h]
0x18001d0c7  lea     rdx, [rbp+var_20]
0x18001d0cb  call    ?HasClientsOf@ClientsTracker@@QEAA_NAEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::HasClientsOf(std::initializer_list<MapsClientType> const &)
0x18001d0d0  test    al, al
0x18001d0d2  jnz     short loc_18001D0D6
0x18001d0d4  int     2Ch; Windows NT - assertion failure
0x18001d0d6  cmp     dword ptr [rbx+0DC8h], 5
0x18001d0dd  jz      short loc_18001D0EF
0x18001d0df  mov     r8d, 0DFBh
0x18001d0e5  mov     ecx, 80070015h
0x18001d0ea  jmp     loc_18001D1A6
0x18001d0ef  cmp     dword ptr [rbx+0DC0h], 0
0x18001d0f6  jnz     loc_18001D19B
0x18001d0fc  cmp     dword ptr [rbx+0DC4h], 0
0x18001d103  jnz     loc_18001D19B
0x18001d109  lea     rcx, [rbx+0DF0h]; this
0x18001d110  call    ?AreMapsRegistered@PackageManager@@QEAA_NXZ; PackageManager::AreMapsRegistered(void)
0x18001d115  mov     r8b, al
0x18001d118  xor     edx, edx
0x18001d11a  lea     ecx, [rdx+3]
0x18001d11d  call    cs:__imp_?MosStorageSetMigrationState@@YAJW4__MIDL_mapsstorageapi_0002@@J_N@Z; MosStorageSetMigrationState(__MIDL_mapsstorageapi_0002,long,bool)
0x18001d123  movups  xmm0, xmmword ptr [rdi]
0x18001d126  movdqu  [rbp+var_20], xmm0
0x18001d12b  lea     rcx, [rbx+8]
0x18001d12f  lea     r8, [rbp+var_20]
0x18001d133  mov     edx, r14d
0x18001d136  call    ?SetupMigration@MigrationEngine@@IEAAJW4__MIDL_odmlapi_0006@@U_GUID@@@Z; MigrationEngine::SetupMigration(__MIDL_odmlapi_0006,_GUID)
0x18001d13b  test    eax, eax
0x18001d13d  jns     short loc_18001D15C
0x18001d13f  mov     sil, 1
0x18001d142  mov     r9, rbx
0x18001d145  mov     r8d, 0E01h
0x18001d14b  lea     rdx, aServicemanager_59; "ServiceManager::StartMapDataMigration"
0x18001d152  mov     ecx, eax
0x18001d154  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001d15a  jmp     short loc_18001D1B6
0x18001d15c  xor     edi, edi
0x18001d15e  mov     dword ptr [rbx+0DC4h], 0Ah
0x18001d168  mov     dword ptr [rbx+0DC0h], 6
0x18001d172  lea     rax, ?DoMigration@ServiceManager@@AEAAJXZ; ServiceManager::DoMigration(void)
0x18001d179  mov     qword ptr [rbp+var_20], rax
0x18001d17d  mov     dword ptr [rbp+var_20+8], edi
0x18001d180  mov     eax, [rbp+var_4]
0x18001d183  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001d186  lea     r8, [rbp+var_20]
0x18001d18a  mov     rdx, rbx
0x18001d18d  mov     rcx, [rbx+0D40h]; pcbe
0x18001d194  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x18001d199  jmp     short loc_18001D1FE
0x18001d19b  mov     r8d, 0DFCh
0x18001d1a1  mov     ecx, 80070149h
0x18001d1a6  mov     r9, rbx
0x18001d1a9  lea     rdx, aServicemanager_59; "ServiceManager::StartMapDataMigration"
0x18001d1b0  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001d1b6  mov     edi, eax
0x18001d1b8  test    eax, eax
0x18001d1ba  jns     short loc_18001D1FE
0x18001d1bc  test    sil, sil
0x18001d1bf  jz      short loc_18001D1FE
0x18001d1c1  mov     qword ptr [rbx+0DC0h], 0
0x18001d1cc  lea     rcx, [rbx+0DF0h]; this
0x18001d1d3  call    ?AreMapsRegistered@PackageManager@@QEAA_NXZ; PackageManager::AreMapsRegistered(void)
0x18001d1d8  mov     r8b, al
0x18001d1db  mov     edx, edi
0x18001d1dd  xor     ecx, ecx
0x18001d1df  call    cs:__imp_?MosStorageSetMigrationState@@YAJW4__MIDL_mapsstorageapi_0002@@J_N@Z; MosStorageSetMigrationState(__MIDL_mapsstorageapi_0002,long,bool)
0x18001d1e5  mov     dword ptr [rbx+0DD0h], 1
0x18001d1ef  mov     [rbx+0DD4h], edi
0x18001d1f5  mov     rcx, rbx; this
0x18001d1f8  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001d1fd  nop
0x18001d1fe  lea     rcx, [rbp+var_10]; this
0x18001d202  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001d207  mov     eax, edi
0x18001d209  mov     rbx, [rsp+40h+arg_8]
0x18001d20e  mov     rsi, [rsp+40h+arg_10]
0x18001d213  add     rsp, 40h
0x18001d217  pop     r14
0x18001d219  pop     rdi
0x18001d21a  pop     rbp
0x18001d21b  retn
```
