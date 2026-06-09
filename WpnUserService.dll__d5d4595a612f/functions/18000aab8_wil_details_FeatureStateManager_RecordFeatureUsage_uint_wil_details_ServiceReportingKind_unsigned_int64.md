# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000aab8`
- end: `0x18000abc7`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c740`

## callees

- `0x180008d84`
- `0x180008e38`
- `0x18000aab8`
- `0x18000abd0`
- `0x18000ac04`
- `0x18000ac3c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000abb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000abb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab9d`

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
0x18000aab8  push    rbx
0x18000aaba  push    rbp
0x18000aabb  push    rsi
0x18000aabc  push    rdi
0x18000aabd  push    r14
0x18000aabf  push    r15
0x18000aac1  sub     rsp, 28h
0x18000aac5  mov     r15, r9
0x18000aac8  mov     ebx, r8d
0x18000aacb  mov     r14d, edx
0x18000aace  mov     rsi, rcx
0x18000aad1  cmp     byte ptr [rcx], 0
0x18000aad4  jz      loc_18000ABBA
0x18000aada  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aadf  test    al, al
0x18000aae1  jz      loc_18000ABBA
0x18000aae7  mov     rdi, [rsi+18h]
0x18000aaeb  cmp     ebx, 0FEh
0x18000aaf1  jz      short loc_18000AB70
0x18000aaf3  cmp     ebx, 0C8h
0x18000aaf9  jb      short loc_18000AB13
0x18000aafb  cmp     ebx, 100h
0x18000ab01  jl      loc_18000ABBA
0x18000ab07  cmp     ebx, 200h
0x18000ab0d  jnb     loc_18000ABBA
0x18000ab13  mov     rcx, rdi; SRWLock
0x18000ab16  call    cs:__imp_AcquireSRWLockExclusive
0x18000ab1c  cmp     ebx, 7
0x18000ab1f  ja      short loc_18000AB2B
0x18000ab21  mov     eax, 0CCh
0x18000ab26  bt      eax, ebx
0x18000ab29  jb      short loc_18000AB4B
0x18000ab2b  lea     eax, [rbx-100h]
0x18000ab31  cmp     eax, 7Fh
0x18000ab34  jbe     short loc_18000AB4B
0x18000ab36  mov     r9d, r15d
0x18000ab39  lea     rcx, [rdi+48h]
0x18000ab3d  mov     r8d, r14d
0x18000ab40  mov     edx, ebx
0x18000ab42  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ab47  mov     bl, al
0x18000ab49  jmp     short loc_18000AB5C
0x18000ab4b  mov     r8d, r14d
0x18000ab4e  mov     edx, ebx
0x18000ab50  lea     rcx, [rdi+8]
0x18000ab54  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ab59  mov     bl, [rdi+40h]
0x18000ab5c  test    rdi, rdi
0x18000ab5f  jz      short loc_18000AB6A
0x18000ab61  mov     rcx, rdi; SRWLock
0x18000ab64  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab6a  test    bl, bl
0x18000ab6c  jz      short loc_18000ABBA
0x18000ab6e  jmp     short loc_18000AB78
0x18000ab70  mov     rcx, rdi; SRWLock
0x18000ab73  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ab78  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ab7f  jnz     short loc_18000ABBA
0x18000ab81  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ab88  test    rax, rax
0x18000ab8b  jz      short loc_18000AB96
0x18000ab8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab92  test    al, al
0x18000ab94  jnz     short loc_18000ABBA
0x18000ab96  lea     rbx, [rsi+20h]
0x18000ab9a  mov     rcx, rbx; SRWLock
0x18000ab9d  call    cs:__imp_AcquireSRWLockExclusive
0x18000aba3  mov     rcx, rsi; pv
0x18000aba6  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000abab  test    rbx, rbx
0x18000abae  jz      short loc_18000ABBA
0x18000abb0  mov     rcx, rbx; SRWLock
0x18000abb3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000abb9  nop
0x18000abba  add     rsp, 28h
0x18000abbe  pop     r15
0x18000abc0  pop     r14
0x18000abc2  pop     rdi
0x18000abc3  pop     rsi
0x18000abc4  pop     rbp
0x18000abc5  pop     rbx
0x18000abc6  retn
```
