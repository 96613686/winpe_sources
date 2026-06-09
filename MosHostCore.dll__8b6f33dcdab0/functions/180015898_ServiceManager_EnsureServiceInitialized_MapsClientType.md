# ServiceManager::EnsureServiceInitialized(MapsClientType)

- ea: `0x180015898`
- end: `0x180015ac9`
- name: `?EnsureServiceInitialized@ServiceManager@@AEAAJW4MapsClientType@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012cf0`
- `0x180014c00`
- `0x180015ad0`
- `0x18001ac90`

## callees

- `0x180003410`
- `0x180009d0c`
- `0x180009d90`
- `0x180009db4`
- `0x18001189c`
- `0x180013174`
- `0x18001546c`
- `0x1800155ec`
- `0x180015898`
- `0x180015ed0`
- `0x180016d3c`
- `0x180018094`
- `0x18001db8c`
- `0x18001e454`
- `0x18001e5e0`

## import_xrefs

- `MosStorage!MosStorageDumpConfiguration` at `0x1800158ef`
- `MosStorage!MosStorageDumpConfiguration` at `0x1800158ef`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015967`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015967`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015a89`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015a89`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015a19`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015a19`

## string_xrefs

- `0x180015958`: `ServiceManager::EnsureServiceInitialized`
- `0x180015a0a`: `ServiceManager::EnsureServiceInitialized`
- `0x180015a80`: `ServiceManager::EnsureServiceInitialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::EnsureServiceInitialized(__int64 a1, unsigned int a2)
{
  char v4; // si
  int v5; // eax
  int v6; // r8d
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  OfflineMapsTelemetry *v9; // rax
  int updated; // eax
  struct _TP_CALLBACK_ENVIRON_V3 *v11; // rcx
  __int64 v12; // rcx
  int inited; // eax
  unsigned int v14; // eax
  unsigned int v15; // edi
  __m128i *p_si128; // [rsp+20h] [rbp-38h] BYREF
  __int8 *v18; // [rsp+28h] [rbp-30h]
  __m128i si128; // [rsp+30h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-18h] BYREF

  if ( a2 == 3 || *(_DWORD *)(a1 + 3528) )
  {
    v4 = 0;
    if ( a2 == 3 )
      goto LABEL_7;
  }
  else
  {
    v4 = 1;
  }
  v5 = ServiceManager::WaitForStoresRepairing((ServiceManager *)a1);
  if ( v5 < 0 )
  {
    v6 = 2603;
LABEL_32:
    v14 = ZTraceReportPropagation(v5, "ServiceManager::EnsureServiceInitialized", v6, (const void *)a1);
    goto LABEL_33;
  }
LABEL_7:
  if ( !*(_DWORD *)(a1 + 4320) )
  {
    v5 = MosStorageDumpConfiguration();
    if ( v5 < 0 )
    {
      v6 = 2609;
      goto LABEL_32;
    }
    *(_DWORD *)(a1 + 4320) = 3;
    if ( OfflineMapsTelemetry::IsEnabled(v8, v7) )
    {
      v9 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::MapsBrokerServiceInitialized_(v9, 3);
    }
    v5 = ServiceManager::DoUpgradeCheck((ServiceManager *)a1);
    if ( v5 < 0 )
    {
      v6 = 2614;
      goto LABEL_32;
    }
  }
  if ( !*(_BYTE *)(a1 + 4316) )
  {
    updated = ServiceManager::EnableMapsUpdateTask((ServiceManager *)a1);
    if ( updated < 0 )
      ZTraceReportIgnore(updated, "ServiceManager::EnsureServiceInitialized", 2619, (const void *)a1);
  }
  if ( !*(_DWORD *)(a1 + 3528) )
  {
    v11 = *(struct _TP_CALLBACK_ENVIRON_V3 **)(a1 + 3392);
    si128.m128i_i64[0] = (__int64)ServiceManager::InitMOSAndBing;
    si128.m128i_i32[3] = HIDWORD(v18);
    *(_DWORD *)(a1 + 3528) = 1;
    si128.m128i_i32[2] = 0;
    Threadpool::QueueThis<ServiceManager>(v11, a1, &si128);
  }
  if ( a2 )
  {
    v5 = ServiceManager::WaitForMOSAndBingInit((ServiceManager *)a1);
    if ( v5 < 0 )
    {
      v6 = 2633;
      goto LABEL_32;
    }
  }
  p_si128 = &si128;
  v18 = (__int8 *)&v20;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( !(unsigned __int8)ClientsTracker::IsClientOneOf(a2, &p_si128) || *(_DWORD *)(a1 + 3528) != 2 )
  {
    si128.m128i_i64[0] = 0x500000001LL;
    p_si128 = &si128;
    v18 = &si128.m128i_i8[8];
    if ( (unsigned __int8)ClientsTracker::IsClientOneOf(v12, &p_si128) && *(_DWORD *)(a1 + 3528) == 5 )
      ServiceManager::FireOdmlStateChange((ServiceManager *)a1);
    goto LABEL_29;
  }
  inited = ServiceManager::InitODML((ServiceManager *)a1);
  if ( inited >= 0 )
  {
LABEL_29:
    if ( (unsigned int)(*(_DWORD *)(a1 + 3528) - 3) > 2 )
      return 0;
    v5 = ServiceManager::UpdateTransferPolicies((ServiceManager *)a1);
    if ( v5 >= 0 )
      return 0;
    v6 = 2654;
    goto LABEL_32;
  }
  v14 = ZTraceReportOrigination(inited, "ServiceManager::EnsureServiceInitialized", 2642, (const void *)a1);
LABEL_33:
  v15 = v14;
  if ( v14 == -2147023504 && v4 && !*(_BYTE *)(a1 + 4312) )
    ServiceManager::AttemptRepairMapDataAsync((ServiceManager *)a1);
  return v15;
}

```

## disassembly

```asm
0x180015898  push    rbp
0x18001589a  push    rbx
0x18001589b  push    rsi
0x18001589c  push    rdi
0x18001589d  mov     rbp, rsp
0x1800158a0  sub     rsp, 58h
0x1800158a4  mov     rax, cs:__security_cookie
0x1800158ab  xor     rax, rsp
0x1800158ae  mov     [rbp+var_18], rax
0x1800158b2  mov     edi, edx
0x1800158b4  mov     rbx, rcx
0x1800158b7  cmp     edx, 3
0x1800158ba  jz      short loc_1800158CA
0x1800158bc  cmp     dword ptr [rcx+0DC8h], 0
0x1800158c3  jnz     short loc_1800158CA
0x1800158c5  mov     sil, 1
0x1800158c8  jmp     short loc_1800158D2
0x1800158ca  xor     sil, sil
0x1800158cd  cmp     edi, 3
0x1800158d0  jz      short loc_1800158E6
0x1800158d2  call    ?WaitForStoresRepairing@ServiceManager@@AEAAJXZ; ServiceManager::WaitForStoresRepairing(void)
0x1800158d7  test    eax, eax
0x1800158d9  jns     short loc_1800158E6
0x1800158db  mov     r8d, 0A2Bh
0x1800158e1  jmp     loc_180015A7D
0x1800158e6  cmp     dword ptr [rbx+10E0h], 0
0x1800158ed  jnz     short loc_180015940
0x1800158ef  call    cs:__imp_?MosStorageDumpConfiguration@@YAJXZ; MosStorageDumpConfiguration(void)
0x1800158f5  test    eax, eax
0x1800158f7  jns     short loc_180015904
0x1800158f9  mov     r8d, 0A31h
0x1800158ff  jmp     loc_180015A7D
0x180015904  mov     dword ptr [rbx+10E0h], 3
0x18001590e  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180015913  test    al, al
0x180015915  jz      short loc_180015929
0x180015917  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001591c  mov     edx, 3; int
0x180015921  mov     rcx, rax; this
0x180015924  call    ?MapsBrokerServiceInitialized_@OfflineMapsTelemetry@@QEAAXH@Z; OfflineMapsTelemetry::MapsBrokerServiceInitialized_(int)
0x180015929  mov     rcx, rbx; this
0x18001592c  call    ?DoUpgradeCheck@ServiceManager@@AEAAJXZ; ServiceManager::DoUpgradeCheck(void)
0x180015931  test    eax, eax
0x180015933  jns     short loc_180015940
0x180015935  mov     r8d, 0A36h
0x18001593b  jmp     loc_180015A7D
0x180015940  cmp     byte ptr [rbx+10DCh], 0
0x180015947  jnz     short loc_18001596D
0x180015949  mov     rcx, rbx; this
0x18001594c  call    ?EnableMapsUpdateTask@ServiceManager@@AEAAJXZ; ServiceManager::EnableMapsUpdateTask(void)
0x180015951  test    eax, eax
0x180015953  jns     short loc_18001596D
0x180015955  mov     r9, rbx
0x180015958  lea     rdx, aServicemanager_57; "ServiceManager::EnsureServiceInitialize"...
0x18001595f  mov     r8d, 0A3Bh
0x180015965  mov     ecx, eax
0x180015967  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001596d  cmp     dword ptr [rbx+0DC8h], 0
0x180015974  jnz     short loc_1800159AB
0x180015976  mov     rcx, [rbx+0D40h]; pcbe
0x18001597d  lea     rax, ?InitMOSAndBing@ServiceManager@@AEAAJXZ; ServiceManager::InitMOSAndBing(void)
0x180015984  mov     qword ptr [rbp+var_28], rax
0x180015988  lea     r8, [rbp+var_28]
0x18001598c  mov     eax, [rbp+var_2C]
0x18001598f  mov     rdx, rbx
0x180015992  mov     dword ptr [rbp+var_28+0Ch], eax
0x180015995  mov     dword ptr [rbx+0DC8h], 1
0x18001599f  mov     dword ptr [rbp+var_28+8], 0
0x1800159a6  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x1800159ab  test    edi, edi
0x1800159ad  jz      short loc_1800159C6
0x1800159af  mov     rcx, rbx; this
0x1800159b2  call    ?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForMOSAndBingInit(void)
0x1800159b7  test    eax, eax
0x1800159b9  jns     short loc_1800159C6
0x1800159bb  mov     r8d, 0A49h
0x1800159c1  jmp     loc_180015A7D
0x1800159c6  movdqa  xmm0, cs:__xmm@00000003000000050000000100000002
0x1800159ce  lea     rax, [rbp+var_28]
0x1800159d2  mov     [rbp+var_38], rax
0x1800159d6  lea     rdx, [rbp+var_38]
0x1800159da  lea     rax, [rbp+var_18]
0x1800159de  mov     ecx, edi
0x1800159e0  mov     [rbp-30h], rax
0x1800159e4  movdqu  [rbp+var_28], xmm0
0x1800159e9  call    ?IsClientOneOf@ClientsTracker@@SA_NW4MapsClientType@@AEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::IsClientOneOf(MapsClientType,std::initializer_list<MapsClientType> const &)
0x1800159ee  test    al, al
0x1800159f0  jz      short loc_180015A21
0x1800159f2  cmp     dword ptr [rbx+0DC8h], 2
0x1800159f9  jnz     short loc_180015A21
0x1800159fb  mov     rcx, rbx; this
0x1800159fe  call    ?InitODML@ServiceManager@@AEAAJXZ; ServiceManager::InitODML(void)
0x180015a03  test    eax, eax
0x180015a05  jns     short loc_180015A5D
0x180015a07  mov     r9, rbx
0x180015a0a  lea     rdx, aServicemanager_57; "ServiceManager::EnsureServiceInitialize"...
0x180015a11  mov     r8d, 0A52h
0x180015a17  mov     ecx, eax
0x180015a19  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180015a1f  jmp     short loc_180015A8F
0x180015a21  lea     rax, [rbp+var_28]
0x180015a25  mov     dword ptr [rbp+var_28], 1
0x180015a2c  mov     [rbp+var_38], rax
0x180015a30  lea     rdx, [rbp+var_38]
0x180015a34  lea     rax, [rbp+var_28+8]
0x180015a38  mov     dword ptr [rbp+var_28+4], 5
0x180015a3f  mov     [rbp-30h], rax
0x180015a43  call    ?IsClientOneOf@ClientsTracker@@SA_NW4MapsClientType@@AEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::IsClientOneOf(MapsClientType,std::initializer_list<MapsClientType> const &)
0x180015a48  test    al, al
0x180015a4a  jz      short loc_180015A5D
0x180015a4c  cmp     dword ptr [rbx+0DC8h], 5
0x180015a53  jnz     short loc_180015A5D
0x180015a55  mov     rcx, rbx; this
0x180015a58  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180015a5d  mov     eax, [rbx+0DC8h]
0x180015a63  sub     eax, 3
0x180015a66  cmp     eax, 2
0x180015a69  ja      short loc_180015AB0
0x180015a6b  mov     rcx, rbx; this
0x180015a6e  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x180015a73  test    eax, eax
0x180015a75  jns     short loc_180015AB0
0x180015a77  mov     r8d, 0A5Eh
0x180015a7d  mov     r9, rbx
0x180015a80  lea     rdx, aServicemanager_57; "ServiceManager::EnsureServiceInitialize"...
0x180015a87  mov     ecx, eax
0x180015a89  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015a8f  mov     edi, eax
0x180015a91  cmp     eax, 80070570h
0x180015a96  jnz     short loc_180015AB2
0x180015a98  test    sil, sil
0x180015a9b  jz      short loc_180015AB2
0x180015a9d  cmp     byte ptr [rbx+10D8h], 0
0x180015aa4  jnz     short loc_180015AB2
0x180015aa6  mov     rcx, rbx; this
0x180015aa9  call    ?AttemptRepairMapDataAsync@ServiceManager@@AEAAXXZ; ServiceManager::AttemptRepairMapDataAsync(void)
0x180015aae  jmp     short loc_180015AB2
0x180015ab0  xor     edi, edi
0x180015ab2  mov     eax, edi
0x180015ab4  mov     rcx, [rbp+var_18]
0x180015ab8  xor     rcx, rsp; StackCookie
0x180015abb  call    __security_check_cookie
0x180015ac0  add     rsp, 58h
0x180015ac4  pop     rdi
0x180015ac5  pop     rsi
0x180015ac6  pop     rbx
0x180015ac7  pop     rbp
0x180015ac8  retn
```
