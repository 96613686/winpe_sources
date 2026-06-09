# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000d09c`
- end: `0x18000d1ab`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000e610`

## callees

- `0x18000a498`
- `0x18000a54c`
- `0x18000d09c`
- `0x18000d1b4`
- `0x18000d1e8`
- `0x18000d220`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d148`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d197`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d148`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d197`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d0fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d181`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d0fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d181`

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
0x18000d09c  push    rbx
0x18000d09e  push    rbp
0x18000d09f  push    rsi
0x18000d0a0  push    rdi
0x18000d0a1  push    r14
0x18000d0a3  push    r15
0x18000d0a5  sub     rsp, 28h
0x18000d0a9  mov     r15, r9
0x18000d0ac  mov     ebx, r8d
0x18000d0af  mov     r14d, edx
0x18000d0b2  mov     rsi, rcx
0x18000d0b5  cmp     byte ptr [rcx], 0
0x18000d0b8  jz      loc_18000D19E
0x18000d0be  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000d0c3  test    al, al
0x18000d0c5  jz      loc_18000D19E
0x18000d0cb  mov     rdi, [rsi+18h]
0x18000d0cf  cmp     ebx, 0FEh
0x18000d0d5  jz      short loc_18000D154
0x18000d0d7  cmp     ebx, 0C8h
0x18000d0dd  jb      short loc_18000D0F7
0x18000d0df  cmp     ebx, 100h
0x18000d0e5  jl      loc_18000D19E
0x18000d0eb  cmp     ebx, 200h
0x18000d0f1  jnb     loc_18000D19E
0x18000d0f7  mov     rcx, rdi; SRWLock
0x18000d0fa  call    cs:__imp_AcquireSRWLockExclusive
0x18000d100  cmp     ebx, 7
0x18000d103  ja      short loc_18000D10F
0x18000d105  mov     eax, 0CCh
0x18000d10a  bt      eax, ebx
0x18000d10d  jb      short loc_18000D12F
0x18000d10f  lea     eax, [rbx-100h]
0x18000d115  cmp     eax, 7Fh
0x18000d118  jbe     short loc_18000D12F
0x18000d11a  mov     r9d, r15d
0x18000d11d  lea     rcx, [rdi+48h]
0x18000d121  mov     r8d, r14d
0x18000d124  mov     edx, ebx
0x18000d126  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d12b  mov     bl, al
0x18000d12d  jmp     short loc_18000D140
0x18000d12f  mov     r8d, r14d
0x18000d132  mov     edx, ebx
0x18000d134  lea     rcx, [rdi+8]
0x18000d138  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d13d  mov     bl, [rdi+40h]
0x18000d140  test    rdi, rdi
0x18000d143  jz      short loc_18000D14E
0x18000d145  mov     rcx, rdi; SRWLock
0x18000d148  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d14e  test    bl, bl
0x18000d150  jz      short loc_18000D19E
0x18000d152  jmp     short loc_18000D15C
0x18000d154  mov     rcx, rdi; SRWLock
0x18000d157  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000d15c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d163  jnz     short loc_18000D19E
0x18000d165  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d16c  test    rax, rax
0x18000d16f  jz      short loc_18000D17A
0x18000d171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d176  test    al, al
0x18000d178  jnz     short loc_18000D19E
0x18000d17a  lea     rbx, [rsi+20h]
0x18000d17e  mov     rcx, rbx; SRWLock
0x18000d181  call    cs:__imp_AcquireSRWLockExclusive
0x18000d187  mov     rcx, rsi; pv
0x18000d18a  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000d18f  test    rbx, rbx
0x18000d192  jz      short loc_18000D19E
0x18000d194  mov     rcx, rbx; SRWLock
0x18000d197  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d19d  nop
0x18000d19e  add     rsp, 28h
0x18000d1a2  pop     r15
0x18000d1a4  pop     r14
0x18000d1a6  pop     rdi
0x18000d1a7  pop     rsi
0x18000d1a8  pop     rbp
0x18000d1a9  pop     rbx
0x18000d1aa  retn
```
