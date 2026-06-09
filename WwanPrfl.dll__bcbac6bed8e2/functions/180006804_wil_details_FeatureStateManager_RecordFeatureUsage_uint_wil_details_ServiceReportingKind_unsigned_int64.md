# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006804`
- end: `0x180006913`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008c30`

## callees

- `0x180004544`
- `0x1800046bc`
- `0x180006804`
- `0x180006994`
- `0x1800069c8`
- `0x180006a00`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006862`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800068e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006862`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800068e9`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rdi
  int v9; // eax
  char v10; // bl

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      wil::details::FeatureStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)a1);
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    if ( (AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24)), a3 <= 7) && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v10 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x180006804  push    rbx
0x180006806  push    rbp
0x180006807  push    rsi
0x180006808  push    rdi
0x180006809  push    r14
0x18000680b  push    r15
0x18000680d  sub     rsp, 28h
0x180006811  mov     r15, r9
0x180006814  mov     ebx, r8d
0x180006817  mov     r14d, edx
0x18000681a  mov     rsi, rcx
0x18000681d  cmp     byte ptr [rcx], 0
0x180006820  jz      loc_180006906
0x180006826  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000682b  test    al, al
0x18000682d  jz      loc_180006906
0x180006833  mov     rdi, [rsi+18h]
0x180006837  cmp     ebx, 0FEh
0x18000683d  jz      short loc_1800068BC
0x18000683f  cmp     ebx, 0C8h
0x180006845  jb      short loc_18000685F
0x180006847  cmp     ebx, 100h
0x18000684d  jl      loc_180006906
0x180006853  cmp     ebx, 200h
0x180006859  jnb     loc_180006906
0x18000685f  mov     rcx, rdi; SRWLock
0x180006862  call    cs:__imp_AcquireSRWLockExclusive
0x180006868  cmp     ebx, 7
0x18000686b  ja      short loc_180006877
0x18000686d  mov     eax, 0CCh
0x180006872  bt      eax, ebx
0x180006875  jb      short loc_180006897
0x180006877  lea     eax, [rbx-100h]
0x18000687d  cmp     eax, 7Fh
0x180006880  jbe     short loc_180006897
0x180006882  mov     r9d, r15d
0x180006885  lea     rcx, [rdi+48h]
0x180006889  mov     r8d, r14d
0x18000688c  mov     edx, ebx
0x18000688e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006893  mov     bl, al
0x180006895  jmp     short loc_1800068A8
0x180006897  mov     r8d, r14d
0x18000689a  mov     edx, ebx
0x18000689c  lea     rcx, [rdi+8]
0x1800068a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800068a5  mov     bl, [rdi+40h]
0x1800068a8  test    rdi, rdi
0x1800068ab  jz      short loc_1800068B6
0x1800068ad  mov     rcx, rdi; SRWLock
0x1800068b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800068b6  test    bl, bl
0x1800068b8  jz      short loc_180006906
0x1800068ba  jmp     short loc_1800068C4
0x1800068bc  mov     rcx, rdi; SRWLock
0x1800068bf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800068c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800068cb  jnz     short loc_180006906
0x1800068cd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800068d4  test    rax, rax
0x1800068d7  jz      short loc_1800068E2
0x1800068d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068de  test    al, al
0x1800068e0  jnz     short loc_180006906
0x1800068e2  lea     rbx, [rsi+20h]
0x1800068e6  mov     rcx, rbx; SRWLock
0x1800068e9  call    cs:__imp_AcquireSRWLockExclusive
0x1800068ef  mov     rcx, rsi; pv
0x1800068f2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800068f7  test    rbx, rbx
0x1800068fa  jz      short loc_180006906
0x1800068fc  mov     rcx, rbx; SRWLock
0x1800068ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180006905  nop
0x180006906  add     rsp, 28h
0x18000690a  pop     r15
0x18000690c  pop     r14
0x18000690e  pop     rdi
0x18000690f  pop     rsi
0x180006910  pop     rbp
0x180006911  pop     rbx
0x180006912  retn
```
