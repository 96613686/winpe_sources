# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180011398`
- end: `0x1800114a7`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180013f20`

## callees

- `0x180010024`
- `0x1800100d8`
- `0x180011398`
- `0x1800114b0`
- `0x1800114e4`
- `0x18001151c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011444`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011493`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011444`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011493`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001147d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001147d`

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
0x180011398  push    rbx
0x18001139a  push    rbp
0x18001139b  push    rsi
0x18001139c  push    rdi
0x18001139d  push    r14
0x18001139f  push    r15
0x1800113a1  sub     rsp, 28h
0x1800113a5  mov     r15, r9
0x1800113a8  mov     ebx, r8d
0x1800113ab  mov     r14d, edx
0x1800113ae  mov     rsi, rcx
0x1800113b1  cmp     byte ptr [rcx], 0
0x1800113b4  jz      loc_18001149A
0x1800113ba  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800113bf  test    al, al
0x1800113c1  jz      loc_18001149A
0x1800113c7  mov     rdi, [rsi+18h]
0x1800113cb  cmp     ebx, 0FEh
0x1800113d1  jz      short loc_180011450
0x1800113d3  cmp     ebx, 0C8h
0x1800113d9  jb      short loc_1800113F3
0x1800113db  cmp     ebx, 100h
0x1800113e1  jl      loc_18001149A
0x1800113e7  cmp     ebx, 200h
0x1800113ed  jnb     loc_18001149A
0x1800113f3  mov     rcx, rdi; SRWLock
0x1800113f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800113fc  cmp     ebx, 7
0x1800113ff  ja      short loc_18001140B
0x180011401  mov     eax, 0CCh
0x180011406  bt      eax, ebx
0x180011409  jb      short loc_18001142B
0x18001140b  lea     eax, [rbx-100h]
0x180011411  cmp     eax, 7Fh
0x180011414  jbe     short loc_18001142B
0x180011416  mov     r9d, r15d
0x180011419  lea     rcx, [rdi+48h]
0x18001141d  mov     r8d, r14d
0x180011420  mov     edx, ebx
0x180011422  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180011427  mov     bl, al
0x180011429  jmp     short loc_18001143C
0x18001142b  mov     r8d, r14d
0x18001142e  mov     edx, ebx
0x180011430  lea     rcx, [rdi+8]
0x180011434  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180011439  mov     bl, [rdi+40h]
0x18001143c  test    rdi, rdi
0x18001143f  jz      short loc_18001144A
0x180011441  mov     rcx, rdi; SRWLock
0x180011444  call    cs:__imp_ReleaseSRWLockExclusive
0x18001144a  test    bl, bl
0x18001144c  jz      short loc_18001149A
0x18001144e  jmp     short loc_180011458
0x180011450  mov     rcx, rdi; SRWLock
0x180011453  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011458  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001145f  jnz     short loc_18001149A
0x180011461  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011468  test    rax, rax
0x18001146b  jz      short loc_180011476
0x18001146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011472  test    al, al
0x180011474  jnz     short loc_18001149A
0x180011476  lea     rbx, [rsi+20h]
0x18001147a  mov     rcx, rbx; SRWLock
0x18001147d  call    cs:__imp_AcquireSRWLockExclusive
0x180011483  mov     rcx, rsi; pv
0x180011486  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18001148b  test    rbx, rbx
0x18001148e  jz      short loc_18001149A
0x180011490  mov     rcx, rbx; SRWLock
0x180011493  call    cs:__imp_ReleaseSRWLockExclusive
0x180011499  nop
0x18001149a  add     rsp, 28h
0x18001149e  pop     r15
0x1800114a0  pop     r14
0x1800114a2  pop     rdi
0x1800114a3  pop     rsi
0x1800114a4  pop     rbp
0x1800114a5  pop     rbx
0x1800114a6  retn
```
