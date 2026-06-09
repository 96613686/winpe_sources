# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000d1a4`
- end: `0x18000d2b3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000f640`

## callees

- `0x18000ac34`
- `0x18000adac`
- `0x18000d1a4`
- `0x18000d334`
- `0x18000d368`
- `0x18000d3a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d202`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d289`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d202`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d289`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d250`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d29f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d250`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d29f`

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
0x18000d1a4  push    rbx
0x18000d1a6  push    rbp
0x18000d1a7  push    rsi
0x18000d1a8  push    rdi
0x18000d1a9  push    r14
0x18000d1ab  push    r15
0x18000d1ad  sub     rsp, 28h
0x18000d1b1  mov     r15, r9
0x18000d1b4  mov     ebx, r8d
0x18000d1b7  mov     r14d, edx
0x18000d1ba  mov     rsi, rcx
0x18000d1bd  cmp     byte ptr [rcx], 0
0x18000d1c0  jz      loc_18000D2A6
0x18000d1c6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000d1cb  test    al, al
0x18000d1cd  jz      loc_18000D2A6
0x18000d1d3  mov     rdi, [rsi+18h]
0x18000d1d7  cmp     ebx, 0FEh
0x18000d1dd  jz      short loc_18000D25C
0x18000d1df  cmp     ebx, 0C8h
0x18000d1e5  jb      short loc_18000D1FF
0x18000d1e7  cmp     ebx, 100h
0x18000d1ed  jl      loc_18000D2A6
0x18000d1f3  cmp     ebx, 200h
0x18000d1f9  jnb     loc_18000D2A6
0x18000d1ff  mov     rcx, rdi; SRWLock
0x18000d202  call    cs:__imp_AcquireSRWLockExclusive
0x18000d208  cmp     ebx, 7
0x18000d20b  ja      short loc_18000D217
0x18000d20d  mov     eax, 0CCh
0x18000d212  bt      eax, ebx
0x18000d215  jb      short loc_18000D237
0x18000d217  lea     eax, [rbx-100h]
0x18000d21d  cmp     eax, 7Fh
0x18000d220  jbe     short loc_18000D237
0x18000d222  mov     r9d, r15d
0x18000d225  lea     rcx, [rdi+48h]
0x18000d229  mov     r8d, r14d
0x18000d22c  mov     edx, ebx
0x18000d22e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d233  mov     bl, al
0x18000d235  jmp     short loc_18000D248
0x18000d237  mov     r8d, r14d
0x18000d23a  mov     edx, ebx
0x18000d23c  lea     rcx, [rdi+8]
0x18000d240  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d245  mov     bl, [rdi+40h]
0x18000d248  test    rdi, rdi
0x18000d24b  jz      short loc_18000D256
0x18000d24d  mov     rcx, rdi; SRWLock
0x18000d250  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d256  test    bl, bl
0x18000d258  jz      short loc_18000D2A6
0x18000d25a  jmp     short loc_18000D264
0x18000d25c  mov     rcx, rdi; SRWLock
0x18000d25f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000d264  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d26b  jnz     short loc_18000D2A6
0x18000d26d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d274  test    rax, rax
0x18000d277  jz      short loc_18000D282
0x18000d279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d27e  test    al, al
0x18000d280  jnz     short loc_18000D2A6
0x18000d282  lea     rbx, [rsi+20h]
0x18000d286  mov     rcx, rbx; SRWLock
0x18000d289  call    cs:__imp_AcquireSRWLockExclusive
0x18000d28f  mov     rcx, rsi; pv
0x18000d292  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000d297  test    rbx, rbx
0x18000d29a  jz      short loc_18000D2A6
0x18000d29c  mov     rcx, rbx; SRWLock
0x18000d29f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d2a5  nop
0x18000d2a6  add     rsp, 28h
0x18000d2aa  pop     r15
0x18000d2ac  pop     r14
0x18000d2ae  pop     rdi
0x18000d2af  pop     rsi
0x18000d2b0  pop     rbp
0x18000d2b1  pop     rbx
0x18000d2b2  retn
```
