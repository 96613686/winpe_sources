# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008ff0`
- end: `0x1800090ff`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000a680`

## callees

- `0x180008084`
- `0x180008138`
- `0x180008ff0`
- `0x180009108`
- `0x18000913c`
- `0x180009174`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000909c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000909c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000904e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000904e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090d5`

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
0x180008ff0  push    rbx
0x180008ff2  push    rbp
0x180008ff3  push    rsi
0x180008ff4  push    rdi
0x180008ff5  push    r14
0x180008ff7  push    r15
0x180008ff9  sub     rsp, 28h
0x180008ffd  mov     r15, r9
0x180009000  mov     ebx, r8d
0x180009003  mov     r14d, edx
0x180009006  mov     rsi, rcx
0x180009009  cmp     byte ptr [rcx], 0
0x18000900c  jz      loc_1800090F2
0x180009012  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009017  test    al, al
0x180009019  jz      loc_1800090F2
0x18000901f  mov     rdi, [rsi+18h]
0x180009023  cmp     ebx, 0FEh
0x180009029  jz      short loc_1800090A8
0x18000902b  cmp     ebx, 0C8h
0x180009031  jb      short loc_18000904B
0x180009033  cmp     ebx, 100h
0x180009039  jl      loc_1800090F2
0x18000903f  cmp     ebx, 200h
0x180009045  jnb     loc_1800090F2
0x18000904b  mov     rcx, rdi; SRWLock
0x18000904e  call    cs:__imp_AcquireSRWLockExclusive
0x180009054  cmp     ebx, 7
0x180009057  ja      short loc_180009063
0x180009059  mov     eax, 0CCh
0x18000905e  bt      eax, ebx
0x180009061  jb      short loc_180009083
0x180009063  lea     eax, [rbx-100h]
0x180009069  cmp     eax, 7Fh
0x18000906c  jbe     short loc_180009083
0x18000906e  mov     r9d, r15d
0x180009071  lea     rcx, [rdi+48h]
0x180009075  mov     r8d, r14d
0x180009078  mov     edx, ebx
0x18000907a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000907f  mov     bl, al
0x180009081  jmp     short loc_180009094
0x180009083  mov     r8d, r14d
0x180009086  mov     edx, ebx
0x180009088  lea     rcx, [rdi+8]
0x18000908c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009091  mov     bl, [rdi+40h]
0x180009094  test    rdi, rdi
0x180009097  jz      short loc_1800090A2
0x180009099  mov     rcx, rdi; SRWLock
0x18000909c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800090a2  test    bl, bl
0x1800090a4  jz      short loc_1800090F2
0x1800090a6  jmp     short loc_1800090B0
0x1800090a8  mov     rcx, rdi; SRWLock
0x1800090ab  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800090b0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800090b7  jnz     short loc_1800090F2
0x1800090b9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800090c0  test    rax, rax
0x1800090c3  jz      short loc_1800090CE
0x1800090c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ca  test    al, al
0x1800090cc  jnz     short loc_1800090F2
0x1800090ce  lea     rbx, [rsi+20h]
0x1800090d2  mov     rcx, rbx; SRWLock
0x1800090d5  call    cs:__imp_AcquireSRWLockExclusive
0x1800090db  mov     rcx, rsi; pv
0x1800090de  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800090e3  test    rbx, rbx
0x1800090e6  jz      short loc_1800090F2
0x1800090e8  mov     rcx, rbx; SRWLock
0x1800090eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800090f1  nop
0x1800090f2  add     rsp, 28h
0x1800090f6  pop     r15
0x1800090f8  pop     r14
0x1800090fa  pop     rdi
0x1800090fb  pop     rsi
0x1800090fc  pop     rbp
0x1800090fd  pop     rbx
0x1800090fe  retn
```
