# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140006d90`
- end: `0x140006e9f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140007ee0`

## callees

- `0x14000645c`
- `0x140006510`
- `0x140006d90`
- `0x140006ea8`
- `0x140006edc`
- `0x140006f14`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006e8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006dee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006e75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006dee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006e75`

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
0x140006d90  push    rbx
0x140006d92  push    rbp
0x140006d93  push    rsi
0x140006d94  push    rdi
0x140006d95  push    r14
0x140006d97  push    r15
0x140006d99  sub     rsp, 28h
0x140006d9d  mov     r15, r9
0x140006da0  mov     ebx, r8d
0x140006da3  mov     r14d, edx
0x140006da6  mov     rsi, rcx
0x140006da9  cmp     byte ptr [rcx], 0
0x140006dac  jz      loc_140006E92
0x140006db2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140006db7  test    al, al
0x140006db9  jz      loc_140006E92
0x140006dbf  mov     rdi, [rsi+18h]
0x140006dc3  cmp     ebx, 0FEh
0x140006dc9  jz      short loc_140006E48
0x140006dcb  cmp     ebx, 0C8h
0x140006dd1  jb      short loc_140006DEB
0x140006dd3  cmp     ebx, 100h
0x140006dd9  jl      loc_140006E92
0x140006ddf  cmp     ebx, 200h
0x140006de5  jnb     loc_140006E92
0x140006deb  mov     rcx, rdi; SRWLock
0x140006dee  call    cs:__imp_AcquireSRWLockExclusive
0x140006df4  cmp     ebx, 7
0x140006df7  ja      short loc_140006E03
0x140006df9  mov     eax, 0CCh
0x140006dfe  bt      eax, ebx
0x140006e01  jb      short loc_140006E23
0x140006e03  lea     eax, [rbx-100h]
0x140006e09  cmp     eax, 7Fh
0x140006e0c  jbe     short loc_140006E23
0x140006e0e  mov     r9d, r15d
0x140006e11  lea     rcx, [rdi+48h]
0x140006e15  mov     r8d, r14d
0x140006e18  mov     edx, ebx
0x140006e1a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140006e1f  mov     bl, al
0x140006e21  jmp     short loc_140006E34
0x140006e23  mov     r8d, r14d
0x140006e26  mov     edx, ebx
0x140006e28  lea     rcx, [rdi+8]
0x140006e2c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140006e31  mov     bl, [rdi+40h]
0x140006e34  test    rdi, rdi
0x140006e37  jz      short loc_140006E42
0x140006e39  mov     rcx, rdi; SRWLock
0x140006e3c  call    cs:__imp_ReleaseSRWLockExclusive
0x140006e42  test    bl, bl
0x140006e44  jz      short loc_140006E92
0x140006e46  jmp     short loc_140006E50
0x140006e48  mov     rcx, rdi; SRWLock
0x140006e4b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140006e50  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140006e57  jnz     short loc_140006E92
0x140006e59  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140006e60  test    rax, rax
0x140006e63  jz      short loc_140006E6E
0x140006e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e6a  test    al, al
0x140006e6c  jnz     short loc_140006E92
0x140006e6e  lea     rbx, [rsi+20h]
0x140006e72  mov     rcx, rbx; SRWLock
0x140006e75  call    cs:__imp_AcquireSRWLockExclusive
0x140006e7b  mov     rcx, rsi; pv
0x140006e7e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140006e83  test    rbx, rbx
0x140006e86  jz      short loc_140006E92
0x140006e88  mov     rcx, rbx; SRWLock
0x140006e8b  call    cs:__imp_ReleaseSRWLockExclusive
0x140006e91  nop
0x140006e92  add     rsp, 28h
0x140006e96  pop     r15
0x140006e98  pop     r14
0x140006e9a  pop     rdi
0x140006e9b  pop     rsi
0x140006e9c  pop     rbp
0x140006e9d  pop     rbx
0x140006e9e  retn
```
