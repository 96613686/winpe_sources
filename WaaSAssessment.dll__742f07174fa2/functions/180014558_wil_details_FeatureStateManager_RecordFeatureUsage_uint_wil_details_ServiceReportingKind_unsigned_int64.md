# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180014558`
- end: `0x180014667`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180015df0`

## callees

- `0x1800118f4`
- `0x180011a6c`
- `0x180014558`
- `0x1800146a4`
- `0x1800146d8`
- `0x180014710`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014604`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014653`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014604`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014653`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800145b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001463d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800145b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001463d`

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

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
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
0x180014558  push    rbx
0x18001455a  push    rbp
0x18001455b  push    rsi
0x18001455c  push    rdi
0x18001455d  push    r14
0x18001455f  push    r15
0x180014561  sub     rsp, 28h
0x180014565  mov     r15, r9
0x180014568  mov     ebx, r8d
0x18001456b  mov     r14d, edx
0x18001456e  mov     rsi, rcx
0x180014571  cmp     byte ptr [rcx], 0
0x180014574  jz      loc_18001465A
0x18001457a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001457f  test    al, al
0x180014581  jz      loc_18001465A
0x180014587  mov     rdi, [rsi+18h]
0x18001458b  cmp     ebx, 0FEh
0x180014591  jz      short loc_180014610
0x180014593  cmp     ebx, 0C8h
0x180014599  jb      short loc_1800145B3
0x18001459b  cmp     ebx, 100h
0x1800145a1  jl      loc_18001465A
0x1800145a7  cmp     ebx, 200h
0x1800145ad  jnb     loc_18001465A
0x1800145b3  mov     rcx, rdi; SRWLock
0x1800145b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800145bc  cmp     ebx, 7
0x1800145bf  ja      short loc_1800145CB
0x1800145c1  mov     eax, 0CCh
0x1800145c6  bt      eax, ebx
0x1800145c9  jb      short loc_1800145EB
0x1800145cb  lea     eax, [rbx-100h]
0x1800145d1  cmp     eax, 7Fh
0x1800145d4  jbe     short loc_1800145EB
0x1800145d6  mov     r9d, r15d
0x1800145d9  lea     rcx, [rdi+48h]
0x1800145dd  mov     r8d, r14d
0x1800145e0  mov     edx, ebx
0x1800145e2  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800145e7  mov     bl, al
0x1800145e9  jmp     short loc_1800145FC
0x1800145eb  mov     r8d, r14d
0x1800145ee  mov     edx, ebx
0x1800145f0  lea     rcx, [rdi+8]
0x1800145f4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800145f9  mov     bl, [rdi+40h]
0x1800145fc  test    rdi, rdi
0x1800145ff  jz      short loc_18001460A
0x180014601  mov     rcx, rdi; SRWLock
0x180014604  call    cs:__imp_ReleaseSRWLockExclusive
0x18001460a  test    bl, bl
0x18001460c  jz      short loc_18001465A
0x18001460e  jmp     short loc_180014618
0x180014610  mov     rcx, rdi; SRWLock
0x180014613  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014618  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001461f  jnz     short loc_18001465A
0x180014621  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014628  test    rax, rax
0x18001462b  jz      short loc_180014636
0x18001462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014632  test    al, al
0x180014634  jnz     short loc_18001465A
0x180014636  lea     rbx, [rsi+20h]
0x18001463a  mov     rcx, rbx; SRWLock
0x18001463d  call    cs:__imp_AcquireSRWLockExclusive
0x180014643  mov     rcx, rsi; pv
0x180014646  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18001464b  test    rbx, rbx
0x18001464e  jz      short loc_18001465A
0x180014650  mov     rcx, rbx; SRWLock
0x180014653  call    cs:__imp_ReleaseSRWLockExclusive
0x180014659  nop
0x18001465a  add     rsp, 28h
0x18001465e  pop     r15
0x180014660  pop     r14
0x180014662  pop     rdi
0x180014663  pop     rsi
0x180014664  pop     rbp
0x180014665  pop     rbx
0x180014666  retn
```
