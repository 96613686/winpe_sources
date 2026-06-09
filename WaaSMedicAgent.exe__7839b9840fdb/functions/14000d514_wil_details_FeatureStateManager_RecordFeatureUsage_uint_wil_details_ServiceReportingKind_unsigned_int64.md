# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000d514`
- end: `0x14000d62c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `280`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000e600`

## callees

- `0x14000c55c`
- `0x14000c610`
- `0x14000d514`
- `0x14000d634`
- `0x14000d668`
- `0x14000d6a0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d5c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d5c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d618`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d57b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d602`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d57b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d602`

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
  __int64 v10; // rcx
  char v11; // bl

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v10)) )
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
      v11 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v11 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4,
              -2);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v11 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x14000d514  push    rbx
0x14000d516  push    rbp
0x14000d517  push    rsi
0x14000d518  push    rdi
0x14000d519  push    r14
0x14000d51b  push    r15
0x14000d51d  sub     rsp, 38h
0x14000d521  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x14000d52a  mov     r15, r9
0x14000d52d  mov     ebx, r8d
0x14000d530  mov     r14d, edx
0x14000d533  mov     rsi, rcx
0x14000d536  cmp     byte ptr [rcx], 0
0x14000d539  jz      loc_14000D61F
0x14000d53f  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000d544  test    al, al
0x14000d546  jz      loc_14000D61F
0x14000d54c  mov     rdi, [rsi+18h]
0x14000d550  cmp     ebx, 0FEh
0x14000d556  jz      short loc_14000D5D5
0x14000d558  cmp     ebx, 0C8h
0x14000d55e  jb      short loc_14000D578
0x14000d560  cmp     ebx, 100h
0x14000d566  jl      loc_14000D61F
0x14000d56c  cmp     ebx, 200h
0x14000d572  jnb     loc_14000D61F
0x14000d578  mov     rcx, rdi; SRWLock
0x14000d57b  call    cs:__imp_AcquireSRWLockExclusive
0x14000d581  cmp     ebx, 7
0x14000d584  ja      short loc_14000D590
0x14000d586  mov     eax, 0CCh
0x14000d58b  bt      eax, ebx
0x14000d58e  jb      short loc_14000D5B0
0x14000d590  lea     eax, [rbx-100h]
0x14000d596  cmp     eax, 7Fh
0x14000d599  jbe     short loc_14000D5B0
0x14000d59b  mov     r9d, r15d
0x14000d59e  lea     rcx, [rdi+48h]
0x14000d5a2  mov     r8d, r14d
0x14000d5a5  mov     edx, ebx
0x14000d5a7  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000d5ac  mov     bl, al
0x14000d5ae  jmp     short loc_14000D5C1
0x14000d5b0  mov     r8d, r14d
0x14000d5b3  mov     edx, ebx
0x14000d5b5  lea     rcx, [rdi+8]
0x14000d5b9  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000d5be  mov     bl, [rdi+40h]
0x14000d5c1  test    rdi, rdi
0x14000d5c4  jz      short loc_14000D5CF
0x14000d5c6  mov     rcx, rdi; SRWLock
0x14000d5c9  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d5cf  test    bl, bl
0x14000d5d1  jz      short loc_14000D61F
0x14000d5d3  jmp     short loc_14000D5DD
0x14000d5d5  mov     rcx, rdi; SRWLock
0x14000d5d8  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000d5dd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000d5e4  jnz     short loc_14000D61F
0x14000d5e6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000d5ed  test    rax, rax
0x14000d5f0  jz      short loc_14000D5FB
0x14000d5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5f7  test    al, al
0x14000d5f9  jnz     short loc_14000D61F
0x14000d5fb  lea     rbx, [rsi+20h]
0x14000d5ff  mov     rcx, rbx; SRWLock
0x14000d602  call    cs:__imp_AcquireSRWLockExclusive
0x14000d608  mov     rcx, rsi; pv
0x14000d60b  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000d610  test    rbx, rbx
0x14000d613  jz      short loc_14000D61F
0x14000d615  mov     rcx, rbx; SRWLock
0x14000d618  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d61e  nop
0x14000d61f  add     rsp, 38h
0x14000d623  pop     r15
0x14000d625  pop     r14
0x14000d627  pop     rdi
0x14000d628  pop     rsi
0x14000d629  pop     rbp
0x14000d62a  pop     rbx
0x14000d62b  retn
```
