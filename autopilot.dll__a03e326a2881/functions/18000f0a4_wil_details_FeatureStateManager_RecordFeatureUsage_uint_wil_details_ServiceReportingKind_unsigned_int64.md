# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f0a4`
- end: `0x18000f1b3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180011aa0`

## callees

- `0x18000c7e0`
- `0x18000c958`
- `0x18000f0a4`
- `0x18000f234`
- `0x18000f268`
- `0x18000f2a0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f150`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f19f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f150`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f19f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f102`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f189`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f102`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f189`

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
0x18000f0a4  push    rbx
0x18000f0a6  push    rbp
0x18000f0a7  push    rsi
0x18000f0a8  push    rdi
0x18000f0a9  push    r14
0x18000f0ab  push    r15
0x18000f0ad  sub     rsp, 28h
0x18000f0b1  mov     r15, r9
0x18000f0b4  mov     ebx, r8d
0x18000f0b7  mov     r14d, edx
0x18000f0ba  mov     rsi, rcx
0x18000f0bd  cmp     byte ptr [rcx], 0
0x18000f0c0  jz      loc_18000F1A6
0x18000f0c6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f0cb  test    al, al
0x18000f0cd  jz      loc_18000F1A6
0x18000f0d3  mov     rdi, [rsi+18h]
0x18000f0d7  cmp     ebx, 0FEh
0x18000f0dd  jz      short loc_18000F15C
0x18000f0df  cmp     ebx, 0C8h
0x18000f0e5  jb      short loc_18000F0FF
0x18000f0e7  cmp     ebx, 100h
0x18000f0ed  jl      loc_18000F1A6
0x18000f0f3  cmp     ebx, 200h
0x18000f0f9  jnb     loc_18000F1A6
0x18000f0ff  mov     rcx, rdi; SRWLock
0x18000f102  call    cs:__imp_AcquireSRWLockExclusive
0x18000f108  cmp     ebx, 7
0x18000f10b  ja      short loc_18000F117
0x18000f10d  mov     eax, 0CCh
0x18000f112  bt      eax, ebx
0x18000f115  jb      short loc_18000F137
0x18000f117  lea     eax, [rbx-100h]
0x18000f11d  cmp     eax, 7Fh
0x18000f120  jbe     short loc_18000F137
0x18000f122  mov     r9d, r15d
0x18000f125  lea     rcx, [rdi+48h]
0x18000f129  mov     r8d, r14d
0x18000f12c  mov     edx, ebx
0x18000f12e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f133  mov     bl, al
0x18000f135  jmp     short loc_18000F148
0x18000f137  mov     r8d, r14d
0x18000f13a  mov     edx, ebx
0x18000f13c  lea     rcx, [rdi+8]
0x18000f140  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f145  mov     bl, [rdi+40h]
0x18000f148  test    rdi, rdi
0x18000f14b  jz      short loc_18000F156
0x18000f14d  mov     rcx, rdi; SRWLock
0x18000f150  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f156  test    bl, bl
0x18000f158  jz      short loc_18000F1A6
0x18000f15a  jmp     short loc_18000F164
0x18000f15c  mov     rcx, rdi; SRWLock
0x18000f15f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f164  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f16b  jnz     short loc_18000F1A6
0x18000f16d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f174  test    rax, rax
0x18000f177  jz      short loc_18000F182
0x18000f179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f17e  test    al, al
0x18000f180  jnz     short loc_18000F1A6
0x18000f182  lea     rbx, [rsi+20h]
0x18000f186  mov     rcx, rbx; SRWLock
0x18000f189  call    cs:__imp_AcquireSRWLockExclusive
0x18000f18f  mov     rcx, rsi; pv
0x18000f192  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000f197  test    rbx, rbx
0x18000f19a  jz      short loc_18000F1A6
0x18000f19c  mov     rcx, rbx; SRWLock
0x18000f19f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f1a5  nop
0x18000f1a6  add     rsp, 28h
0x18000f1aa  pop     r15
0x18000f1ac  pop     r14
0x18000f1ae  pop     rdi
0x18000f1af  pop     rsi
0x18000f1b0  pop     rbp
0x18000f1b1  pop     rbx
0x18000f1b2  retn
```
