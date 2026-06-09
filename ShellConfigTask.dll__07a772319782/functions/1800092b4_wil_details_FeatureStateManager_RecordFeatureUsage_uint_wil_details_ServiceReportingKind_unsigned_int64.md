# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800092b4`
- end: `0x1800093c3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c010`

## callees

- `0x180006a64`
- `0x180006bdc`
- `0x1800092b4`
- `0x180009444`
- `0x180009478`
- `0x1800094b0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009312`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009399`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009312`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009399`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009360`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800093af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009360`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800093af`

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
0x1800092b4  push    rbx
0x1800092b6  push    rbp
0x1800092b7  push    rsi
0x1800092b8  push    rdi
0x1800092b9  push    r14
0x1800092bb  push    r15
0x1800092bd  sub     rsp, 28h
0x1800092c1  mov     r15, r9
0x1800092c4  mov     ebx, r8d
0x1800092c7  mov     r14d, edx
0x1800092ca  mov     rsi, rcx
0x1800092cd  cmp     byte ptr [rcx], 0
0x1800092d0  jz      loc_1800093B6
0x1800092d6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800092db  test    al, al
0x1800092dd  jz      loc_1800093B6
0x1800092e3  mov     rdi, [rsi+18h]
0x1800092e7  cmp     ebx, 0FEh
0x1800092ed  jz      short loc_18000936C
0x1800092ef  cmp     ebx, 0C8h
0x1800092f5  jb      short loc_18000930F
0x1800092f7  cmp     ebx, 100h
0x1800092fd  jl      loc_1800093B6
0x180009303  cmp     ebx, 200h
0x180009309  jnb     loc_1800093B6
0x18000930f  mov     rcx, rdi; SRWLock
0x180009312  call    cs:__imp_AcquireSRWLockExclusive
0x180009318  cmp     ebx, 7
0x18000931b  ja      short loc_180009327
0x18000931d  mov     eax, 0CCh
0x180009322  bt      eax, ebx
0x180009325  jb      short loc_180009347
0x180009327  lea     eax, [rbx-100h]
0x18000932d  cmp     eax, 7Fh
0x180009330  jbe     short loc_180009347
0x180009332  mov     r9d, r15d
0x180009335  lea     rcx, [rdi+48h]
0x180009339  mov     r8d, r14d
0x18000933c  mov     edx, ebx
0x18000933e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009343  mov     bl, al
0x180009345  jmp     short loc_180009358
0x180009347  mov     r8d, r14d
0x18000934a  mov     edx, ebx
0x18000934c  lea     rcx, [rdi+8]
0x180009350  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009355  mov     bl, [rdi+40h]
0x180009358  test    rdi, rdi
0x18000935b  jz      short loc_180009366
0x18000935d  mov     rcx, rdi; SRWLock
0x180009360  call    cs:__imp_ReleaseSRWLockExclusive
0x180009366  test    bl, bl
0x180009368  jz      short loc_1800093B6
0x18000936a  jmp     short loc_180009374
0x18000936c  mov     rcx, rdi; SRWLock
0x18000936f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009374  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000937b  jnz     short loc_1800093B6
0x18000937d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009384  test    rax, rax
0x180009387  jz      short loc_180009392
0x180009389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000938e  test    al, al
0x180009390  jnz     short loc_1800093B6
0x180009392  lea     rbx, [rsi+20h]
0x180009396  mov     rcx, rbx; SRWLock
0x180009399  call    cs:__imp_AcquireSRWLockExclusive
0x18000939f  mov     rcx, rsi; pv
0x1800093a2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800093a7  test    rbx, rbx
0x1800093aa  jz      short loc_1800093B6
0x1800093ac  mov     rcx, rbx; SRWLock
0x1800093af  call    cs:__imp_ReleaseSRWLockExclusive
0x1800093b5  nop
0x1800093b6  add     rsp, 28h
0x1800093ba  pop     r15
0x1800093bc  pop     r14
0x1800093be  pop     rdi
0x1800093bf  pop     rsi
0x1800093c0  pop     rbp
0x1800093c1  pop     rbx
0x1800093c2  retn
```
