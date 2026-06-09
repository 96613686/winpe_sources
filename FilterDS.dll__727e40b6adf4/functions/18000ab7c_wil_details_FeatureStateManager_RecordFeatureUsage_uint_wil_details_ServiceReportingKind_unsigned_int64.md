# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000ab7c`
- end: `0x18000ac8b`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c080`

## callees

- `0x180009700`
- `0x1800097b4`
- `0x18000ab7c`
- `0x18000ac94`
- `0x18000acc8`
- `0x18000ad00`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000abda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ac61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000abda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ac61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac77`

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
0x18000ab7c  push    rbx
0x18000ab7e  push    rbp
0x18000ab7f  push    rsi
0x18000ab80  push    rdi
0x18000ab81  push    r14
0x18000ab83  push    r15
0x18000ab85  sub     rsp, 28h
0x18000ab89  mov     r15, r9
0x18000ab8c  mov     ebx, r8d
0x18000ab8f  mov     r14d, edx
0x18000ab92  mov     rsi, rcx
0x18000ab95  cmp     byte ptr [rcx], 0
0x18000ab98  jz      loc_18000AC7E
0x18000ab9e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aba3  test    al, al
0x18000aba5  jz      loc_18000AC7E
0x18000abab  mov     rdi, [rsi+18h]
0x18000abaf  cmp     ebx, 0FEh
0x18000abb5  jz      short loc_18000AC34
0x18000abb7  cmp     ebx, 0C8h
0x18000abbd  jb      short loc_18000ABD7
0x18000abbf  cmp     ebx, 100h
0x18000abc5  jl      loc_18000AC7E
0x18000abcb  cmp     ebx, 200h
0x18000abd1  jnb     loc_18000AC7E
0x18000abd7  mov     rcx, rdi; SRWLock
0x18000abda  call    cs:__imp_AcquireSRWLockExclusive
0x18000abe0  cmp     ebx, 7
0x18000abe3  ja      short loc_18000ABEF
0x18000abe5  mov     eax, 0CCh
0x18000abea  bt      eax, ebx
0x18000abed  jb      short loc_18000AC0F
0x18000abef  lea     eax, [rbx-100h]
0x18000abf5  cmp     eax, 7Fh
0x18000abf8  jbe     short loc_18000AC0F
0x18000abfa  mov     r9d, r15d
0x18000abfd  lea     rcx, [rdi+48h]
0x18000ac01  mov     r8d, r14d
0x18000ac04  mov     edx, ebx
0x18000ac06  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ac0b  mov     bl, al
0x18000ac0d  jmp     short loc_18000AC20
0x18000ac0f  mov     r8d, r14d
0x18000ac12  mov     edx, ebx
0x18000ac14  lea     rcx, [rdi+8]
0x18000ac18  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ac1d  mov     bl, [rdi+40h]
0x18000ac20  test    rdi, rdi
0x18000ac23  jz      short loc_18000AC2E
0x18000ac25  mov     rcx, rdi; SRWLock
0x18000ac28  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ac2e  test    bl, bl
0x18000ac30  jz      short loc_18000AC7E
0x18000ac32  jmp     short loc_18000AC3C
0x18000ac34  mov     rcx, rdi; SRWLock
0x18000ac37  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ac3c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ac43  jnz     short loc_18000AC7E
0x18000ac45  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ac4c  test    rax, rax
0x18000ac4f  jz      short loc_18000AC5A
0x18000ac51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac56  test    al, al
0x18000ac58  jnz     short loc_18000AC7E
0x18000ac5a  lea     rbx, [rsi+20h]
0x18000ac5e  mov     rcx, rbx; SRWLock
0x18000ac61  call    cs:__imp_AcquireSRWLockExclusive
0x18000ac67  mov     rcx, rsi; pv
0x18000ac6a  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000ac6f  test    rbx, rbx
0x18000ac72  jz      short loc_18000AC7E
0x18000ac74  mov     rcx, rbx; SRWLock
0x18000ac77  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ac7d  nop
0x18000ac7e  add     rsp, 28h
0x18000ac82  pop     r15
0x18000ac84  pop     r14
0x18000ac86  pop     rdi
0x18000ac87  pop     rsi
0x18000ac88  pop     rbp
0x18000ac89  pop     rbx
0x18000ac8a  retn
```
