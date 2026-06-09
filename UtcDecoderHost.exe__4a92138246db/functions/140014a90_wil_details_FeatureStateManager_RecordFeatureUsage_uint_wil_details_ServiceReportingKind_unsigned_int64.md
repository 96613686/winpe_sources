# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140014a90`
- end: `0x140014b9f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140015eb0`

## callees

- `0x140013b40`
- `0x140013bf4`
- `0x140014a90`
- `0x140014ba8`
- `0x140014bdc`
- `0x140014c14`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014aee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014b75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014aee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014b75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014b3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014b8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014b3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014b8b`

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
0x140014a90  push    rbx
0x140014a92  push    rbp
0x140014a93  push    rsi
0x140014a94  push    rdi
0x140014a95  push    r14
0x140014a97  push    r15
0x140014a99  sub     rsp, 28h
0x140014a9d  mov     r15, r9
0x140014aa0  mov     ebx, r8d
0x140014aa3  mov     r14d, edx
0x140014aa6  mov     rsi, rcx
0x140014aa9  cmp     byte ptr [rcx], 0
0x140014aac  jz      loc_140014B92
0x140014ab2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140014ab7  test    al, al
0x140014ab9  jz      loc_140014B92
0x140014abf  mov     rdi, [rsi+18h]
0x140014ac3  cmp     ebx, 0FEh
0x140014ac9  jz      short loc_140014B48
0x140014acb  cmp     ebx, 0C8h
0x140014ad1  jb      short loc_140014AEB
0x140014ad3  cmp     ebx, 100h
0x140014ad9  jl      loc_140014B92
0x140014adf  cmp     ebx, 200h
0x140014ae5  jnb     loc_140014B92
0x140014aeb  mov     rcx, rdi; SRWLock
0x140014aee  call    cs:__imp_AcquireSRWLockExclusive
0x140014af4  cmp     ebx, 7
0x140014af7  ja      short loc_140014B03
0x140014af9  mov     eax, 0CCh
0x140014afe  bt      eax, ebx
0x140014b01  jb      short loc_140014B23
0x140014b03  lea     eax, [rbx-100h]
0x140014b09  cmp     eax, 7Fh
0x140014b0c  jbe     short loc_140014B23
0x140014b0e  mov     r9d, r15d
0x140014b11  lea     rcx, [rdi+48h]
0x140014b15  mov     r8d, r14d
0x140014b18  mov     edx, ebx
0x140014b1a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140014b1f  mov     bl, al
0x140014b21  jmp     short loc_140014B34
0x140014b23  mov     r8d, r14d
0x140014b26  mov     edx, ebx
0x140014b28  lea     rcx, [rdi+8]
0x140014b2c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140014b31  mov     bl, [rdi+40h]
0x140014b34  test    rdi, rdi
0x140014b37  jz      short loc_140014B42
0x140014b39  mov     rcx, rdi; SRWLock
0x140014b3c  call    cs:__imp_ReleaseSRWLockExclusive
0x140014b42  test    bl, bl
0x140014b44  jz      short loc_140014B92
0x140014b46  jmp     short loc_140014B50
0x140014b48  mov     rcx, rdi; SRWLock
0x140014b4b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140014b50  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014b57  jnz     short loc_140014B92
0x140014b59  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014b60  test    rax, rax
0x140014b63  jz      short loc_140014B6E
0x140014b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b6a  test    al, al
0x140014b6c  jnz     short loc_140014B92
0x140014b6e  lea     rbx, [rsi+20h]
0x140014b72  mov     rcx, rbx; SRWLock
0x140014b75  call    cs:__imp_AcquireSRWLockExclusive
0x140014b7b  mov     rcx, rsi; pv
0x140014b7e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140014b83  test    rbx, rbx
0x140014b86  jz      short loc_140014B92
0x140014b88  mov     rcx, rbx; SRWLock
0x140014b8b  call    cs:__imp_ReleaseSRWLockExclusive
0x140014b91  nop
0x140014b92  add     rsp, 28h
0x140014b96  pop     r15
0x140014b98  pop     r14
0x140014b9a  pop     rdi
0x140014b9b  pop     rsi
0x140014b9c  pop     rbp
0x140014b9d  pop     rbx
0x140014b9e  retn
```
