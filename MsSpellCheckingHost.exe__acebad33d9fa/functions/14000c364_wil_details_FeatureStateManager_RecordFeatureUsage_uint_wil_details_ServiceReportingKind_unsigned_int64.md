# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000c364`
- end: `0x14000c473`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000e420`

## callees

- `0x140009d14`
- `0x140009e8c`
- `0x14000c364`
- `0x14000c4f4`
- `0x14000c528`
- `0x14000c560`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c3c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c449`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c3c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c449`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c410`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c45f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c410`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c45f`

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
0x14000c364  push    rbx
0x14000c366  push    rbp
0x14000c367  push    rsi
0x14000c368  push    rdi
0x14000c369  push    r14
0x14000c36b  push    r15
0x14000c36d  sub     rsp, 28h
0x14000c371  mov     r15, r9
0x14000c374  mov     ebx, r8d
0x14000c377  mov     r14d, edx
0x14000c37a  mov     rsi, rcx
0x14000c37d  cmp     byte ptr [rcx], 0
0x14000c380  jz      loc_14000C466
0x14000c386  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c38b  test    al, al
0x14000c38d  jz      loc_14000C466
0x14000c393  mov     rdi, [rsi+18h]
0x14000c397  cmp     ebx, 0FEh
0x14000c39d  jz      short loc_14000C41C
0x14000c39f  cmp     ebx, 0C8h
0x14000c3a5  jb      short loc_14000C3BF
0x14000c3a7  cmp     ebx, 100h
0x14000c3ad  jl      loc_14000C466
0x14000c3b3  cmp     ebx, 200h
0x14000c3b9  jnb     loc_14000C466
0x14000c3bf  mov     rcx, rdi; SRWLock
0x14000c3c2  call    cs:__imp_AcquireSRWLockExclusive
0x14000c3c8  cmp     ebx, 7
0x14000c3cb  ja      short loc_14000C3D7
0x14000c3cd  mov     eax, 0CCh
0x14000c3d2  bt      eax, ebx
0x14000c3d5  jb      short loc_14000C3F7
0x14000c3d7  lea     eax, [rbx-100h]
0x14000c3dd  cmp     eax, 7Fh
0x14000c3e0  jbe     short loc_14000C3F7
0x14000c3e2  mov     r9d, r15d
0x14000c3e5  lea     rcx, [rdi+48h]
0x14000c3e9  mov     r8d, r14d
0x14000c3ec  mov     edx, ebx
0x14000c3ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000c3f3  mov     bl, al
0x14000c3f5  jmp     short loc_14000C408
0x14000c3f7  mov     r8d, r14d
0x14000c3fa  mov     edx, ebx
0x14000c3fc  lea     rcx, [rdi+8]
0x14000c400  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000c405  mov     bl, [rdi+40h]
0x14000c408  test    rdi, rdi
0x14000c40b  jz      short loc_14000C416
0x14000c40d  mov     rcx, rdi; SRWLock
0x14000c410  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c416  test    bl, bl
0x14000c418  jz      short loc_14000C466
0x14000c41a  jmp     short loc_14000C424
0x14000c41c  mov     rcx, rdi; SRWLock
0x14000c41f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000c424  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000c42b  jnz     short loc_14000C466
0x14000c42d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c434  test    rax, rax
0x14000c437  jz      short loc_14000C442
0x14000c439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c43e  test    al, al
0x14000c440  jnz     short loc_14000C466
0x14000c442  lea     rbx, [rsi+20h]
0x14000c446  mov     rcx, rbx; SRWLock
0x14000c449  call    cs:__imp_AcquireSRWLockExclusive
0x14000c44f  mov     rcx, rsi; pv
0x14000c452  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000c457  test    rbx, rbx
0x14000c45a  jz      short loc_14000C466
0x14000c45c  mov     rcx, rbx; SRWLock
0x14000c45f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c465  nop
0x14000c466  add     rsp, 28h
0x14000c46a  pop     r15
0x14000c46c  pop     r14
0x14000c46e  pop     rdi
0x14000c46f  pop     rsi
0x14000c470  pop     rbp
0x14000c471  pop     rbx
0x14000c472  retn
```
