# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180026d04`
- end: `0x180026e2f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `299`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800288c0`

## callees

- `0x180024f9c`
- `0x180025068`
- `0x180026d04`
- `0x180026e78`
- `0x180026eb0`
- `0x180026ee8`
- `0x18005f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180026d66`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026df9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026d66`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026df9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026dba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026e15`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026dba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026e15`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        int a2,
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
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        (wil::details_abi::RawUsageIndex *)(v8 + 8),
        a3,
        a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              (wil::details_abi::RawUsageIndex *)(v8 + 72),
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
0x180026d04  push    rbx
0x180026d06  push    rbp
0x180026d07  push    rsi
0x180026d08  push    rdi
0x180026d09  push    r14
0x180026d0b  push    r15
0x180026d0d  sub     rsp, 28h
0x180026d11  cmp     byte ptr [rcx], 0
0x180026d14  mov     r15, r9
0x180026d17  mov     ebx, r8d
0x180026d1a  mov     r14d, edx
0x180026d1d  mov     rsi, rcx
0x180026d20  jz      loc_180026E21
0x180026d26  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180026d2b  test    al, al
0x180026d2d  jz      loc_180026E21
0x180026d33  mov     rdi, [rsi+18h]
0x180026d37  cmp     ebx, 0FEh
0x180026d3d  jz      loc_180026DCC
0x180026d43  cmp     ebx, 0C8h
0x180026d49  jb      short loc_180026D63
0x180026d4b  cmp     ebx, 100h
0x180026d51  jl      loc_180026E21
0x180026d57  cmp     ebx, 200h
0x180026d5d  jnb     loc_180026E21
0x180026d63  mov     rcx, rdi; SRWLock
0x180026d66  call    cs:__imp_AcquireSRWLockExclusive
0x180026d6d  nop     dword ptr [rax+rax+00h]
0x180026d72  cmp     ebx, 7
0x180026d75  ja      short loc_180026D81
0x180026d77  mov     eax, 0CCh
0x180026d7c  bt      eax, ebx
0x180026d7f  jb      short loc_180026DA1
0x180026d81  lea     eax, [rbx-100h]
0x180026d87  cmp     eax, 7Fh
0x180026d8a  jbe     short loc_180026DA1
0x180026d8c  mov     r9d, r15d
0x180026d8f  lea     rcx, [rdi+48h]
0x180026d93  mov     r8d, r14d
0x180026d96  mov     edx, ebx
0x180026d98  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180026d9d  mov     bl, al
0x180026d9f  jmp     short loc_180026DB2
0x180026da1  mov     r8d, r14d
0x180026da4  lea     rcx, [rdi+8]
0x180026da8  mov     edx, ebx
0x180026daa  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180026daf  mov     bl, [rdi+40h]
0x180026db2  test    rdi, rdi
0x180026db5  jz      short loc_180026DC6
0x180026db7  mov     rcx, rdi; SRWLock
0x180026dba  call    cs:__imp_ReleaseSRWLockExclusive
0x180026dc1  nop     dword ptr [rax+rax+00h]
0x180026dc6  test    bl, bl
0x180026dc8  jz      short loc_180026E21
0x180026dca  jmp     short loc_180026DD4
0x180026dcc  mov     rcx, rdi; SRWLock
0x180026dcf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180026dd4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180026ddb  jnz     short loc_180026E21
0x180026ddd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180026de4  test    rax, rax
0x180026de7  jz      short loc_180026DF2
0x180026de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dee  test    al, al
0x180026df0  jnz     short loc_180026E21
0x180026df2  lea     rbx, [rsi+20h]
0x180026df6  mov     rcx, rbx; SRWLock
0x180026df9  call    cs:__imp_AcquireSRWLockExclusive
0x180026e00  nop     dword ptr [rax+rax+00h]
0x180026e05  mov     rcx, rsi; pv
0x180026e08  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180026e0d  test    rbx, rbx
0x180026e10  jz      short loc_180026E21
0x180026e12  mov     rcx, rbx; SRWLock
0x180026e15  call    cs:__imp_ReleaseSRWLockExclusive
0x180026e1c  nop     dword ptr [rax+rax+00h]
0x180026e21  add     rsp, 28h
0x180026e25  pop     r15
0x180026e27  pop     r14
0x180026e29  pop     rdi
0x180026e2a  pop     rsi
0x180026e2b  pop     rbp
0x180026e2c  pop     rbx
0x180026e2d  retn
```
