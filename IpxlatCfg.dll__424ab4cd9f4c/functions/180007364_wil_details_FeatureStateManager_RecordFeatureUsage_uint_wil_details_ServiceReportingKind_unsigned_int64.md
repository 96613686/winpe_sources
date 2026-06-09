# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007364`
- end: `0x180007473`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009680`

## callees

- `0x1800053e4`
- `0x18000555c`
- `0x180007364`
- `0x1800074f4`
- `0x180007528`
- `0x180007560`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800073c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007449`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800073c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007449`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007410`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000745f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007410`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000745f`

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
0x180007364  push    rbx
0x180007366  push    rbp
0x180007367  push    rsi
0x180007368  push    rdi
0x180007369  push    r14
0x18000736b  push    r15
0x18000736d  sub     rsp, 28h
0x180007371  mov     r15, r9
0x180007374  mov     ebx, r8d
0x180007377  mov     r14d, edx
0x18000737a  mov     rsi, rcx
0x18000737d  cmp     byte ptr [rcx], 0
0x180007380  jz      loc_180007466
0x180007386  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000738b  test    al, al
0x18000738d  jz      loc_180007466
0x180007393  mov     rdi, [rsi+18h]
0x180007397  cmp     ebx, 0FEh
0x18000739d  jz      short loc_18000741C
0x18000739f  cmp     ebx, 0C8h
0x1800073a5  jb      short loc_1800073BF
0x1800073a7  cmp     ebx, 100h
0x1800073ad  jl      loc_180007466
0x1800073b3  cmp     ebx, 200h
0x1800073b9  jnb     loc_180007466
0x1800073bf  mov     rcx, rdi; SRWLock
0x1800073c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800073c8  cmp     ebx, 7
0x1800073cb  ja      short loc_1800073D7
0x1800073cd  mov     eax, 0CCh
0x1800073d2  bt      eax, ebx
0x1800073d5  jb      short loc_1800073F7
0x1800073d7  lea     eax, [rbx-100h]
0x1800073dd  cmp     eax, 7Fh
0x1800073e0  jbe     short loc_1800073F7
0x1800073e2  mov     r9d, r15d
0x1800073e5  lea     rcx, [rdi+48h]
0x1800073e9  mov     r8d, r14d
0x1800073ec  mov     edx, ebx
0x1800073ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800073f3  mov     bl, al
0x1800073f5  jmp     short loc_180007408
0x1800073f7  mov     r8d, r14d
0x1800073fa  mov     edx, ebx
0x1800073fc  lea     rcx, [rdi+8]
0x180007400  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007405  mov     bl, [rdi+40h]
0x180007408  test    rdi, rdi
0x18000740b  jz      short loc_180007416
0x18000740d  mov     rcx, rdi; SRWLock
0x180007410  call    cs:__imp_ReleaseSRWLockExclusive
0x180007416  test    bl, bl
0x180007418  jz      short loc_180007466
0x18000741a  jmp     short loc_180007424
0x18000741c  mov     rcx, rdi; SRWLock
0x18000741f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007424  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000742b  jnz     short loc_180007466
0x18000742d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007434  test    rax, rax
0x180007437  jz      short loc_180007442
0x180007439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743e  test    al, al
0x180007440  jnz     short loc_180007466
0x180007442  lea     rbx, [rsi+20h]
0x180007446  mov     rcx, rbx; SRWLock
0x180007449  call    cs:__imp_AcquireSRWLockExclusive
0x18000744f  mov     rcx, rsi; pv
0x180007452  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007457  test    rbx, rbx
0x18000745a  jz      short loc_180007466
0x18000745c  mov     rcx, rbx; SRWLock
0x18000745f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007465  nop
0x180007466  add     rsp, 28h
0x18000746a  pop     r15
0x18000746c  pop     r14
0x18000746e  pop     rdi
0x18000746f  pop     rsi
0x180007470  pop     rbp
0x180007471  pop     rbx
0x180007472  retn
```
