# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000b064`
- end: `0x14000b173`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000d7a0`

## callees

- `0x140009a38`
- `0x140009aec`
- `0x14000b064`
- `0x14000b17c`
- `0x14000b1b0`
- `0x14000b1e8`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b0c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b149`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b0c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b149`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b15f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b15f`

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
0x14000b064  push    rbx
0x14000b066  push    rbp
0x14000b067  push    rsi
0x14000b068  push    rdi
0x14000b069  push    r14
0x14000b06b  push    r15
0x14000b06d  sub     rsp, 28h
0x14000b071  mov     r15, r9
0x14000b074  mov     ebx, r8d
0x14000b077  mov     r14d, edx
0x14000b07a  mov     rsi, rcx
0x14000b07d  cmp     byte ptr [rcx], 0
0x14000b080  jz      loc_14000B166
0x14000b086  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000b08b  test    al, al
0x14000b08d  jz      loc_14000B166
0x14000b093  mov     rdi, [rsi+18h]
0x14000b097  cmp     ebx, 0FEh
0x14000b09d  jz      short loc_14000B11C
0x14000b09f  cmp     ebx, 0C8h
0x14000b0a5  jb      short loc_14000B0BF
0x14000b0a7  cmp     ebx, 100h
0x14000b0ad  jl      loc_14000B166
0x14000b0b3  cmp     ebx, 200h
0x14000b0b9  jnb     loc_14000B166
0x14000b0bf  mov     rcx, rdi; SRWLock
0x14000b0c2  call    cs:__imp_AcquireSRWLockExclusive
0x14000b0c8  cmp     ebx, 7
0x14000b0cb  ja      short loc_14000B0D7
0x14000b0cd  mov     eax, 0CCh
0x14000b0d2  bt      eax, ebx
0x14000b0d5  jb      short loc_14000B0F7
0x14000b0d7  lea     eax, [rbx-100h]
0x14000b0dd  cmp     eax, 7Fh
0x14000b0e0  jbe     short loc_14000B0F7
0x14000b0e2  mov     r9d, r15d
0x14000b0e5  lea     rcx, [rdi+48h]
0x14000b0e9  mov     r8d, r14d
0x14000b0ec  mov     edx, ebx
0x14000b0ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b0f3  mov     bl, al
0x14000b0f5  jmp     short loc_14000B108
0x14000b0f7  mov     r8d, r14d
0x14000b0fa  mov     edx, ebx
0x14000b0fc  lea     rcx, [rdi+8]
0x14000b100  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b105  mov     bl, [rdi+40h]
0x14000b108  test    rdi, rdi
0x14000b10b  jz      short loc_14000B116
0x14000b10d  mov     rcx, rdi; SRWLock
0x14000b110  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b116  test    bl, bl
0x14000b118  jz      short loc_14000B166
0x14000b11a  jmp     short loc_14000B124
0x14000b11c  mov     rcx, rdi; SRWLock
0x14000b11f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b124  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000b12b  jnz     short loc_14000B166
0x14000b12d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000b134  test    rax, rax
0x14000b137  jz      short loc_14000B142
0x14000b139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b13e  test    al, al
0x14000b140  jnz     short loc_14000B166
0x14000b142  lea     rbx, [rsi+20h]
0x14000b146  mov     rcx, rbx; SRWLock
0x14000b149  call    cs:__imp_AcquireSRWLockExclusive
0x14000b14f  mov     rcx, rsi; pv
0x14000b152  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000b157  test    rbx, rbx
0x14000b15a  jz      short loc_14000B166
0x14000b15c  mov     rcx, rbx; SRWLock
0x14000b15f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b165  nop
0x14000b166  add     rsp, 28h
0x14000b16a  pop     r15
0x14000b16c  pop     r14
0x14000b16e  pop     rdi
0x14000b16f  pop     rsi
0x14000b170  pop     rbp
0x14000b171  pop     rbx
0x14000b172  retn
```
