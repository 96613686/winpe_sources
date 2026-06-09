# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140011334`
- end: `0x14001144a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `278`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140012760`

## callees

- `0x1400104d0`
- `0x140010584`
- `0x140011334`
- `0x140011450`
- `0x1400114a4`
- `0x1400114fc`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011395`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001141c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011395`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001141c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400113e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011432`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400113e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011432`

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
0x140011334  mov     [rsp+arg_18], rbx
0x140011339  push    rbp
0x14001133a  push    rsi
0x14001133b  push    rdi
0x14001133c  push    r14
0x14001133e  push    r15
0x140011340  sub     rsp, 20h
0x140011344  mov     r15, r9
0x140011347  mov     ebx, r8d
0x14001134a  mov     r14d, edx
0x14001134d  mov     rsi, rcx
0x140011350  cmp     byte ptr [rcx], 0
0x140011353  jz      loc_140011439
0x140011359  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001135e  test    al, al
0x140011360  jz      loc_140011439
0x140011366  mov     rdi, [rsi+18h]
0x14001136a  cmp     ebx, 0FEh
0x140011370  jz      short loc_1400113EF
0x140011372  cmp     ebx, 0C8h
0x140011378  jb      short loc_140011392
0x14001137a  cmp     ebx, 100h
0x140011380  jl      loc_140011439
0x140011386  cmp     ebx, 200h
0x14001138c  jnb     loc_140011439
0x140011392  mov     rcx, rdi; SRWLock
0x140011395  call    cs:__imp_AcquireSRWLockExclusive
0x14001139b  cmp     ebx, 7
0x14001139e  ja      short loc_1400113AA
0x1400113a0  mov     eax, 0CCh
0x1400113a5  bt      eax, ebx
0x1400113a8  jb      short loc_1400113CA
0x1400113aa  lea     eax, [rbx-100h]
0x1400113b0  cmp     eax, 7Fh
0x1400113b3  jbe     short loc_1400113CA
0x1400113b5  mov     r9d, r15d
0x1400113b8  lea     rcx, [rdi+48h]
0x1400113bc  mov     r8d, r14d
0x1400113bf  mov     edx, ebx
0x1400113c1  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400113c6  mov     bl, al
0x1400113c8  jmp     short loc_1400113DB
0x1400113ca  mov     r8d, r14d
0x1400113cd  mov     edx, ebx
0x1400113cf  lea     rcx, [rdi+8]
0x1400113d3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400113d8  mov     bl, [rdi+40h]
0x1400113db  test    rdi, rdi
0x1400113de  jz      short loc_1400113E9
0x1400113e0  mov     rcx, rdi; SRWLock
0x1400113e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400113e9  test    bl, bl
0x1400113eb  jz      short loc_140011439
0x1400113ed  jmp     short loc_1400113F7
0x1400113ef  mov     rcx, rdi; SRWLock
0x1400113f2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400113f7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400113fe  jnz     short loc_140011439
0x140011400  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140011407  test    rax, rax
0x14001140a  jz      short loc_140011415
0x14001140c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011411  test    al, al
0x140011413  jnz     short loc_140011439
0x140011415  lea     rbx, [rsi+20h]
0x140011419  mov     rcx, rbx; SRWLock
0x14001141c  call    cs:__imp_AcquireSRWLockExclusive
0x140011422  mov     rcx, rsi; pv
0x140011425  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14001142a  test    rbx, rbx
0x14001142d  jz      short loc_140011439
0x14001142f  mov     rcx, rbx; SRWLock
0x140011432  call    cs:__imp_ReleaseSRWLockExclusive
0x140011438  nop
0x140011439  mov     rbx, [rsp+48h+arg_18]
0x14001143e  add     rsp, 20h
0x140011442  pop     r15
0x140011444  pop     r14
0x140011446  pop     rdi
0x140011447  pop     rsi
0x140011448  pop     rbp
0x140011449  retn
```
