# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006584`
- end: `0x180006692`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800081a0`

## callees

- `0x180004674`
- `0x1800047ec`
- `0x180006584`
- `0x180006704`
- `0x180006738`
- `0x180006770`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006630`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000667f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006630`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000667f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800065e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006669`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800065e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006669`

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
0x180006584  push    rbx
0x180006586  push    rbp
0x180006587  push    rsi
0x180006588  push    rdi
0x180006589  push    r14
0x18000658b  push    r15
0x18000658d  sub     rsp, 28h
0x180006591  cmp     byte ptr [rcx], 0
0x180006594  mov     r15, r9
0x180006597  mov     ebx, r8d
0x18000659a  mov     r14d, edx
0x18000659d  mov     rsi, rcx
0x1800065a0  jz      loc_180006685
0x1800065a6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800065ab  test    al, al
0x1800065ad  jz      loc_180006685
0x1800065b3  mov     rdi, [rsi+18h]
0x1800065b7  cmp     ebx, 0FEh
0x1800065bd  jz      short loc_18000663C
0x1800065bf  cmp     ebx, 0C8h
0x1800065c5  jb      short loc_1800065DF
0x1800065c7  cmp     ebx, 100h
0x1800065cd  jl      loc_180006685
0x1800065d3  cmp     ebx, 200h
0x1800065d9  jnb     loc_180006685
0x1800065df  mov     rcx, rdi; SRWLock
0x1800065e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800065e8  cmp     ebx, 7
0x1800065eb  ja      short loc_1800065F7
0x1800065ed  mov     eax, 0CCh
0x1800065f2  bt      eax, ebx
0x1800065f5  jb      short loc_180006617
0x1800065f7  lea     eax, [rbx-100h]
0x1800065fd  cmp     eax, 7Fh
0x180006600  jbe     short loc_180006617
0x180006602  mov     r9d, r15d
0x180006605  lea     rcx, [rdi+48h]
0x180006609  mov     r8d, r14d
0x18000660c  mov     edx, ebx
0x18000660e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006613  mov     bl, al
0x180006615  jmp     short loc_180006628
0x180006617  mov     r8d, r14d
0x18000661a  lea     rcx, [rdi+8]
0x18000661e  mov     edx, ebx
0x180006620  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006625  mov     bl, [rdi+40h]
0x180006628  test    rdi, rdi
0x18000662b  jz      short loc_180006636
0x18000662d  mov     rcx, rdi; SRWLock
0x180006630  call    cs:__imp_ReleaseSRWLockExclusive
0x180006636  test    bl, bl
0x180006638  jz      short loc_180006685
0x18000663a  jmp     short loc_180006644
0x18000663c  mov     rcx, rdi; SRWLock
0x18000663f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006644  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000664b  jnz     short loc_180006685
0x18000664d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006654  test    rax, rax
0x180006657  jz      short loc_180006662
0x180006659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665e  test    al, al
0x180006660  jnz     short loc_180006685
0x180006662  lea     rbx, [rsi+20h]
0x180006666  mov     rcx, rbx; SRWLock
0x180006669  call    cs:__imp_AcquireSRWLockExclusive
0x18000666f  mov     rcx, rsi; pv
0x180006672  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006677  test    rbx, rbx
0x18000667a  jz      short loc_180006685
0x18000667c  mov     rcx, rbx; SRWLock
0x18000667f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006685  add     rsp, 28h
0x180006689  pop     r15
0x18000668b  pop     r14
0x18000668d  pop     rdi
0x18000668e  pop     rsi
0x18000668f  pop     rbp
0x180006690  pop     rbx
0x180006691  retn
```
