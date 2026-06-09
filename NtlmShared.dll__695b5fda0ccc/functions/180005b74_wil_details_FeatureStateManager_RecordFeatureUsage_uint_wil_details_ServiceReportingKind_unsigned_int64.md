# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005b74`
- end: `0x180005c82`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007710`

## callees

- `0x180003c64`
- `0x180003ddc`
- `0x180005b74`
- `0x180005cf4`
- `0x180005d28`
- `0x180005d60`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c6f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c59`

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
0x180005b74  push    rbx
0x180005b76  push    rbp
0x180005b77  push    rsi
0x180005b78  push    rdi
0x180005b79  push    r14
0x180005b7b  push    r15
0x180005b7d  sub     rsp, 28h
0x180005b81  cmp     byte ptr [rcx], 0
0x180005b84  mov     r15, r9
0x180005b87  mov     ebx, r8d
0x180005b8a  mov     r14d, edx
0x180005b8d  mov     rsi, rcx
0x180005b90  jz      loc_180005C75
0x180005b96  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005b9b  test    al, al
0x180005b9d  jz      loc_180005C75
0x180005ba3  mov     rdi, [rsi+18h]
0x180005ba7  cmp     ebx, 0FEh
0x180005bad  jz      short loc_180005C2C
0x180005baf  cmp     ebx, 0C8h
0x180005bb5  jb      short loc_180005BCF
0x180005bb7  cmp     ebx, 100h
0x180005bbd  jl      loc_180005C75
0x180005bc3  cmp     ebx, 200h
0x180005bc9  jnb     loc_180005C75
0x180005bcf  mov     rcx, rdi; SRWLock
0x180005bd2  call    cs:__imp_AcquireSRWLockExclusive
0x180005bd8  cmp     ebx, 7
0x180005bdb  ja      short loc_180005BE7
0x180005bdd  mov     eax, 0CCh
0x180005be2  bt      eax, ebx
0x180005be5  jb      short loc_180005C07
0x180005be7  lea     eax, [rbx-100h]
0x180005bed  cmp     eax, 7Fh
0x180005bf0  jbe     short loc_180005C07
0x180005bf2  mov     r9d, r15d
0x180005bf5  lea     rcx, [rdi+48h]
0x180005bf9  mov     r8d, r14d
0x180005bfc  mov     edx, ebx
0x180005bfe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005c03  mov     bl, al
0x180005c05  jmp     short loc_180005C18
0x180005c07  mov     r8d, r14d
0x180005c0a  lea     rcx, [rdi+8]
0x180005c0e  mov     edx, ebx
0x180005c10  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005c15  mov     bl, [rdi+40h]
0x180005c18  test    rdi, rdi
0x180005c1b  jz      short loc_180005C26
0x180005c1d  mov     rcx, rdi; SRWLock
0x180005c20  call    cs:__imp_ReleaseSRWLockExclusive
0x180005c26  test    bl, bl
0x180005c28  jz      short loc_180005C75
0x180005c2a  jmp     short loc_180005C34
0x180005c2c  mov     rcx, rdi; SRWLock
0x180005c2f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005c34  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005c3b  jnz     short loc_180005C75
0x180005c3d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005c44  test    rax, rax
0x180005c47  jz      short loc_180005C52
0x180005c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4e  test    al, al
0x180005c50  jnz     short loc_180005C75
0x180005c52  lea     rbx, [rsi+20h]
0x180005c56  mov     rcx, rbx; SRWLock
0x180005c59  call    cs:__imp_AcquireSRWLockExclusive
0x180005c5f  mov     rcx, rsi; pv
0x180005c62  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180005c67  test    rbx, rbx
0x180005c6a  jz      short loc_180005C75
0x180005c6c  mov     rcx, rbx; SRWLock
0x180005c6f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005c75  add     rsp, 28h
0x180005c79  pop     r15
0x180005c7b  pop     r14
0x180005c7d  pop     rdi
0x180005c7e  pop     rsi
0x180005c7f  pop     rbp
0x180005c80  pop     rbx
0x180005c81  retn
```
