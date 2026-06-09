# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140010314`
- end: `0x140010422`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140011920`

## callees

- `0x140006bf8`
- `0x140006d70`
- `0x140010314`
- `0x140010464`
- `0x140010498`
- `0x1400104d0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400103c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001040f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400103c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001040f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010372`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400103f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010372`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400103f9`

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
0x140010314  push    rbx
0x140010316  push    rbp
0x140010317  push    rsi
0x140010318  push    rdi
0x140010319  push    r14
0x14001031b  push    r15
0x14001031d  sub     rsp, 28h
0x140010321  cmp     byte ptr [rcx], 0
0x140010324  mov     r15, r9
0x140010327  mov     ebx, r8d
0x14001032a  mov     r14d, edx
0x14001032d  mov     rsi, rcx
0x140010330  jz      loc_140010415
0x140010336  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001033b  test    al, al
0x14001033d  jz      loc_140010415
0x140010343  mov     rdi, [rsi+18h]
0x140010347  cmp     ebx, 0FEh
0x14001034d  jz      short loc_1400103CC
0x14001034f  cmp     ebx, 0C8h
0x140010355  jb      short loc_14001036F
0x140010357  cmp     ebx, 100h
0x14001035d  jl      loc_140010415
0x140010363  cmp     ebx, 200h
0x140010369  jnb     loc_140010415
0x14001036f  mov     rcx, rdi; SRWLock
0x140010372  call    cs:__imp_AcquireSRWLockExclusive
0x140010378  cmp     ebx, 7
0x14001037b  ja      short loc_140010387
0x14001037d  mov     eax, 0CCh
0x140010382  bt      eax, ebx
0x140010385  jb      short loc_1400103A7
0x140010387  lea     eax, [rbx-100h]
0x14001038d  cmp     eax, 7Fh
0x140010390  jbe     short loc_1400103A7
0x140010392  mov     r9d, r15d
0x140010395  lea     rcx, [rdi+48h]
0x140010399  mov     r8d, r14d
0x14001039c  mov     edx, ebx
0x14001039e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400103a3  mov     bl, al
0x1400103a5  jmp     short loc_1400103B8
0x1400103a7  mov     r8d, r14d
0x1400103aa  lea     rcx, [rdi+8]
0x1400103ae  mov     edx, ebx
0x1400103b0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400103b5  mov     bl, [rdi+40h]
0x1400103b8  test    rdi, rdi
0x1400103bb  jz      short loc_1400103C6
0x1400103bd  mov     rcx, rdi; SRWLock
0x1400103c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400103c6  test    bl, bl
0x1400103c8  jz      short loc_140010415
0x1400103ca  jmp     short loc_1400103D4
0x1400103cc  mov     rcx, rdi; SRWLock
0x1400103cf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400103d4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400103db  jnz     short loc_140010415
0x1400103dd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400103e4  test    rax, rax
0x1400103e7  jz      short loc_1400103F2
0x1400103e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103ee  test    al, al
0x1400103f0  jnz     short loc_140010415
0x1400103f2  lea     rbx, [rsi+20h]
0x1400103f6  mov     rcx, rbx; SRWLock
0x1400103f9  call    cs:__imp_AcquireSRWLockExclusive
0x1400103ff  mov     rcx, rsi; pv
0x140010402  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140010407  test    rbx, rbx
0x14001040a  jz      short loc_140010415
0x14001040c  mov     rcx, rbx; SRWLock
0x14001040f  call    cs:__imp_ReleaseSRWLockExclusive
0x140010415  add     rsp, 28h
0x140010419  pop     r15
0x14001041b  pop     r14
0x14001041d  pop     rdi
0x14001041e  pop     rsi
0x14001041f  pop     rbp
0x140010420  pop     rbx
0x140010421  retn
```
