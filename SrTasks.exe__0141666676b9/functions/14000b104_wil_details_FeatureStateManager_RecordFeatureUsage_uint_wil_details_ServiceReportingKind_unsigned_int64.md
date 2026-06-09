# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000b104`
- end: `0x14000b212`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000c8d0`

## callees

- `0x1400096a4`
- `0x140009758`
- `0x14000b104`
- `0x14000b250`
- `0x14000b284`
- `0x14000b2bc`
- `0x140011010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b162`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b1e9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b162`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b1e9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b1b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b1ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b1b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b1ff`

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
0x14000b104  push    rbx
0x14000b106  push    rbp
0x14000b107  push    rsi
0x14000b108  push    rdi
0x14000b109  push    r14
0x14000b10b  push    r15
0x14000b10d  sub     rsp, 28h
0x14000b111  cmp     byte ptr [rcx], 0
0x14000b114  mov     r15, r9
0x14000b117  mov     ebx, r8d
0x14000b11a  mov     r14d, edx
0x14000b11d  mov     rsi, rcx
0x14000b120  jz      loc_14000B205
0x14000b126  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000b12b  test    al, al
0x14000b12d  jz      loc_14000B205
0x14000b133  mov     rdi, [rsi+18h]
0x14000b137  cmp     ebx, 0FEh
0x14000b13d  jz      short loc_14000B1BC
0x14000b13f  cmp     ebx, 0C8h
0x14000b145  jb      short loc_14000B15F
0x14000b147  cmp     ebx, 100h
0x14000b14d  jl      loc_14000B205
0x14000b153  cmp     ebx, 200h
0x14000b159  jnb     loc_14000B205
0x14000b15f  mov     rcx, rdi; SRWLock
0x14000b162  call    cs:__imp_AcquireSRWLockExclusive
0x14000b168  cmp     ebx, 7
0x14000b16b  ja      short loc_14000B177
0x14000b16d  mov     eax, 0CCh
0x14000b172  bt      eax, ebx
0x14000b175  jb      short loc_14000B197
0x14000b177  lea     eax, [rbx-100h]
0x14000b17d  cmp     eax, 7Fh
0x14000b180  jbe     short loc_14000B197
0x14000b182  mov     r9d, r15d
0x14000b185  lea     rcx, [rdi+48h]
0x14000b189  mov     r8d, r14d
0x14000b18c  mov     edx, ebx
0x14000b18e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b193  mov     bl, al
0x14000b195  jmp     short loc_14000B1A8
0x14000b197  mov     r8d, r14d
0x14000b19a  lea     rcx, [rdi+8]
0x14000b19e  mov     edx, ebx
0x14000b1a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b1a5  mov     bl, [rdi+40h]
0x14000b1a8  test    rdi, rdi
0x14000b1ab  jz      short loc_14000B1B6
0x14000b1ad  mov     rcx, rdi; SRWLock
0x14000b1b0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b1b6  test    bl, bl
0x14000b1b8  jz      short loc_14000B205
0x14000b1ba  jmp     short loc_14000B1C4
0x14000b1bc  mov     rcx, rdi; SRWLock
0x14000b1bf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b1c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000b1cb  jnz     short loc_14000B205
0x14000b1cd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000b1d4  test    rax, rax
0x14000b1d7  jz      short loc_14000B1E2
0x14000b1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b1de  test    al, al
0x14000b1e0  jnz     short loc_14000B205
0x14000b1e2  lea     rbx, [rsi+20h]
0x14000b1e6  mov     rcx, rbx; SRWLock
0x14000b1e9  call    cs:__imp_AcquireSRWLockExclusive
0x14000b1ef  mov     rcx, rsi; pv
0x14000b1f2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000b1f7  test    rbx, rbx
0x14000b1fa  jz      short loc_14000B205
0x14000b1fc  mov     rcx, rbx; SRWLock
0x14000b1ff  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b205  add     rsp, 28h
0x14000b209  pop     r15
0x14000b20b  pop     r14
0x14000b20d  pop     rdi
0x14000b20e  pop     rsi
0x14000b20f  pop     rbp
0x14000b210  pop     rbx
0x14000b211  retn
```
