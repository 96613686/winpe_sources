# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002c7b4`
- end: `0x18002c8c3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18002f590`

## callees

- `0x180029980`
- `0x180029af8`
- `0x18002c7b4`
- `0x18002c944`
- `0x18002c978`
- `0x18002c9b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c860`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c8af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c860`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c8af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c812`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c899`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c812`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c899`

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
0x18002c7b4  push    rbx
0x18002c7b6  push    rbp
0x18002c7b7  push    rsi
0x18002c7b8  push    rdi
0x18002c7b9  push    r14
0x18002c7bb  push    r15
0x18002c7bd  sub     rsp, 28h
0x18002c7c1  mov     r15, r9
0x18002c7c4  mov     ebx, r8d
0x18002c7c7  mov     r14d, edx
0x18002c7ca  mov     rsi, rcx
0x18002c7cd  cmp     byte ptr [rcx], 0
0x18002c7d0  jz      loc_18002C8B6
0x18002c7d6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002c7db  test    al, al
0x18002c7dd  jz      loc_18002C8B6
0x18002c7e3  mov     rdi, [rsi+18h]
0x18002c7e7  cmp     ebx, 0FEh
0x18002c7ed  jz      short loc_18002C86C
0x18002c7ef  cmp     ebx, 0C8h
0x18002c7f5  jb      short loc_18002C80F
0x18002c7f7  cmp     ebx, 100h
0x18002c7fd  jl      loc_18002C8B6
0x18002c803  cmp     ebx, 200h
0x18002c809  jnb     loc_18002C8B6
0x18002c80f  mov     rcx, rdi; SRWLock
0x18002c812  call    cs:__imp_AcquireSRWLockExclusive
0x18002c818  cmp     ebx, 7
0x18002c81b  ja      short loc_18002C827
0x18002c81d  mov     eax, 0CCh
0x18002c822  bt      eax, ebx
0x18002c825  jb      short loc_18002C847
0x18002c827  lea     eax, [rbx-100h]
0x18002c82d  cmp     eax, 7Fh
0x18002c830  jbe     short loc_18002C847
0x18002c832  mov     r9d, r15d
0x18002c835  lea     rcx, [rdi+48h]
0x18002c839  mov     r8d, r14d
0x18002c83c  mov     edx, ebx
0x18002c83e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002c843  mov     bl, al
0x18002c845  jmp     short loc_18002C858
0x18002c847  mov     r8d, r14d
0x18002c84a  mov     edx, ebx
0x18002c84c  lea     rcx, [rdi+8]
0x18002c850  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002c855  mov     bl, [rdi+40h]
0x18002c858  test    rdi, rdi
0x18002c85b  jz      short loc_18002C866
0x18002c85d  mov     rcx, rdi; SRWLock
0x18002c860  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c866  test    bl, bl
0x18002c868  jz      short loc_18002C8B6
0x18002c86a  jmp     short loc_18002C874
0x18002c86c  mov     rcx, rdi; SRWLock
0x18002c86f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002c874  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002c87b  jnz     short loc_18002C8B6
0x18002c87d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002c884  test    rax, rax
0x18002c887  jz      short loc_18002C892
0x18002c889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c88e  test    al, al
0x18002c890  jnz     short loc_18002C8B6
0x18002c892  lea     rbx, [rsi+20h]
0x18002c896  mov     rcx, rbx; SRWLock
0x18002c899  call    cs:__imp_AcquireSRWLockExclusive
0x18002c89f  mov     rcx, rsi; pv
0x18002c8a2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18002c8a7  test    rbx, rbx
0x18002c8aa  jz      short loc_18002C8B6
0x18002c8ac  mov     rcx, rbx; SRWLock
0x18002c8af  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c8b5  nop
0x18002c8b6  add     rsp, 28h
0x18002c8ba  pop     r15
0x18002c8bc  pop     r14
0x18002c8be  pop     rdi
0x18002c8bf  pop     rsi
0x18002c8c0  pop     rbp
0x18002c8c1  pop     rbx
0x18002c8c2  retn
```
