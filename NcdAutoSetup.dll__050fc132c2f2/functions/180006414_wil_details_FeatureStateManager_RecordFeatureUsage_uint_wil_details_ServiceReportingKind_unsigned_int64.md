# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006414`
- end: `0x180006522`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008780`

## callees

- `0x180004624`
- `0x1800046d8`
- `0x180006414`
- `0x180006560`
- `0x180006594`
- `0x1800065cc`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000650f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000650f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006472`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006472`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064f9`

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
0x180006414  push    rbx
0x180006416  push    rbp
0x180006417  push    rsi
0x180006418  push    rdi
0x180006419  push    r14
0x18000641b  push    r15
0x18000641d  sub     rsp, 28h
0x180006421  cmp     byte ptr [rcx], 0
0x180006424  mov     r15, r9
0x180006427  mov     ebx, r8d
0x18000642a  mov     r14d, edx
0x18000642d  mov     rsi, rcx
0x180006430  jz      loc_180006515
0x180006436  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000643b  test    al, al
0x18000643d  jz      loc_180006515
0x180006443  mov     rdi, [rsi+18h]
0x180006447  cmp     ebx, 0FEh
0x18000644d  jz      short loc_1800064CC
0x18000644f  cmp     ebx, 0C8h
0x180006455  jb      short loc_18000646F
0x180006457  cmp     ebx, 100h
0x18000645d  jl      loc_180006515
0x180006463  cmp     ebx, 200h
0x180006469  jnb     loc_180006515
0x18000646f  mov     rcx, rdi; SRWLock
0x180006472  call    cs:__imp_AcquireSRWLockExclusive
0x180006478  cmp     ebx, 7
0x18000647b  ja      short loc_180006487
0x18000647d  mov     eax, 0CCh
0x180006482  bt      eax, ebx
0x180006485  jb      short loc_1800064A7
0x180006487  lea     eax, [rbx-100h]
0x18000648d  cmp     eax, 7Fh
0x180006490  jbe     short loc_1800064A7
0x180006492  mov     r9d, r15d
0x180006495  lea     rcx, [rdi+48h]
0x180006499  mov     r8d, r14d
0x18000649c  mov     edx, ebx
0x18000649e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800064a3  mov     bl, al
0x1800064a5  jmp     short loc_1800064B8
0x1800064a7  mov     r8d, r14d
0x1800064aa  lea     rcx, [rdi+8]
0x1800064ae  mov     edx, ebx
0x1800064b0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800064b5  mov     bl, [rdi+40h]
0x1800064b8  test    rdi, rdi
0x1800064bb  jz      short loc_1800064C6
0x1800064bd  mov     rcx, rdi; SRWLock
0x1800064c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800064c6  test    bl, bl
0x1800064c8  jz      short loc_180006515
0x1800064ca  jmp     short loc_1800064D4
0x1800064cc  mov     rcx, rdi; SRWLock
0x1800064cf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800064d4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800064db  jnz     short loc_180006515
0x1800064dd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800064e4  test    rax, rax
0x1800064e7  jz      short loc_1800064F2
0x1800064e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ee  test    al, al
0x1800064f0  jnz     short loc_180006515
0x1800064f2  lea     rbx, [rsi+20h]
0x1800064f6  mov     rcx, rbx; SRWLock
0x1800064f9  call    cs:__imp_AcquireSRWLockExclusive
0x1800064ff  mov     rcx, rsi; pv
0x180006502  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006507  test    rbx, rbx
0x18000650a  jz      short loc_180006515
0x18000650c  mov     rcx, rbx; SRWLock
0x18000650f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006515  add     rsp, 28h
0x180006519  pop     r15
0x18000651b  pop     r14
0x18000651d  pop     rdi
0x18000651e  pop     rsi
0x18000651f  pop     rbp
0x180006520  pop     rbx
0x180006521  retn
```
