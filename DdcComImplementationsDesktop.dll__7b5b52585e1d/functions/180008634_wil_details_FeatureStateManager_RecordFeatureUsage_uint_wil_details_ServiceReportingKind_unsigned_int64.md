# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008634`
- end: `0x180008743`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000a620`

## callees

- `0x180006b04`
- `0x180006bb8`
- `0x180008634`
- `0x180008784`
- `0x1800087b8`
- `0x1800087f0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000872f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000872f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008692`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008719`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008692`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008719`

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
0x180008634  push    rbx
0x180008636  push    rbp
0x180008637  push    rsi
0x180008638  push    rdi
0x180008639  push    r14
0x18000863b  push    r15
0x18000863d  sub     rsp, 28h
0x180008641  mov     r15, r9
0x180008644  mov     ebx, r8d
0x180008647  mov     r14d, edx
0x18000864a  mov     rsi, rcx
0x18000864d  cmp     byte ptr [rcx], 0
0x180008650  jz      loc_180008736
0x180008656  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000865b  test    al, al
0x18000865d  jz      loc_180008736
0x180008663  mov     rdi, [rsi+18h]
0x180008667  cmp     ebx, 0FEh
0x18000866d  jz      short loc_1800086EC
0x18000866f  cmp     ebx, 0C8h
0x180008675  jb      short loc_18000868F
0x180008677  cmp     ebx, 100h
0x18000867d  jl      loc_180008736
0x180008683  cmp     ebx, 200h
0x180008689  jnb     loc_180008736
0x18000868f  mov     rcx, rdi; SRWLock
0x180008692  call    cs:__imp_AcquireSRWLockExclusive
0x180008698  cmp     ebx, 7
0x18000869b  ja      short loc_1800086A7
0x18000869d  mov     eax, 0CCh
0x1800086a2  bt      eax, ebx
0x1800086a5  jb      short loc_1800086C7
0x1800086a7  lea     eax, [rbx-100h]
0x1800086ad  cmp     eax, 7Fh
0x1800086b0  jbe     short loc_1800086C7
0x1800086b2  mov     r9d, r15d
0x1800086b5  lea     rcx, [rdi+48h]
0x1800086b9  mov     r8d, r14d
0x1800086bc  mov     edx, ebx
0x1800086be  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800086c3  mov     bl, al
0x1800086c5  jmp     short loc_1800086D8
0x1800086c7  mov     r8d, r14d
0x1800086ca  mov     edx, ebx
0x1800086cc  lea     rcx, [rdi+8]
0x1800086d0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800086d5  mov     bl, [rdi+40h]
0x1800086d8  test    rdi, rdi
0x1800086db  jz      short loc_1800086E6
0x1800086dd  mov     rcx, rdi; SRWLock
0x1800086e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800086e6  test    bl, bl
0x1800086e8  jz      short loc_180008736
0x1800086ea  jmp     short loc_1800086F4
0x1800086ec  mov     rcx, rdi; SRWLock
0x1800086ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800086f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800086fb  jnz     short loc_180008736
0x1800086fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008704  test    rax, rax
0x180008707  jz      short loc_180008712
0x180008709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870e  test    al, al
0x180008710  jnz     short loc_180008736
0x180008712  lea     rbx, [rsi+20h]
0x180008716  mov     rcx, rbx; SRWLock
0x180008719  call    cs:__imp_AcquireSRWLockExclusive
0x18000871f  mov     rcx, rsi; pv
0x180008722  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180008727  test    rbx, rbx
0x18000872a  jz      short loc_180008736
0x18000872c  mov     rcx, rbx; SRWLock
0x18000872f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008735  nop
0x180008736  add     rsp, 28h
0x18000873a  pop     r15
0x18000873c  pop     r14
0x18000873e  pop     rdi
0x18000873f  pop     rsi
0x180008740  pop     rbp
0x180008741  pop     rbx
0x180008742  retn
```
