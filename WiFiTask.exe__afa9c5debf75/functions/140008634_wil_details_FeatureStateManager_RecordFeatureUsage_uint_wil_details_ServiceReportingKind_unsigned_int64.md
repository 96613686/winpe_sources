# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140008634`
- end: `0x140008743`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000afe0`

## callees

- `0x14000492c`
- `0x140004aa4`
- `0x140008634`
- `0x1400087c4`
- `0x1400087f8`
- `0x140008830`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008692`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008719`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008692`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008719`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400086e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000872f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400086e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000872f`

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
0x140008634  push    rbx
0x140008636  push    rbp
0x140008637  push    rsi
0x140008638  push    rdi
0x140008639  push    r14
0x14000863b  push    r15
0x14000863d  sub     rsp, 28h
0x140008641  mov     r15, r9
0x140008644  mov     ebx, r8d
0x140008647  mov     r14d, edx
0x14000864a  mov     rsi, rcx
0x14000864d  cmp     byte ptr [rcx], 0
0x140008650  jz      loc_140008736
0x140008656  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000865b  test    al, al
0x14000865d  jz      loc_140008736
0x140008663  mov     rdi, [rsi+18h]
0x140008667  cmp     ebx, 0FEh
0x14000866d  jz      short loc_1400086EC
0x14000866f  cmp     ebx, 0C8h
0x140008675  jb      short loc_14000868F
0x140008677  cmp     ebx, 100h
0x14000867d  jl      loc_140008736
0x140008683  cmp     ebx, 200h
0x140008689  jnb     loc_140008736
0x14000868f  mov     rcx, rdi; SRWLock
0x140008692  call    cs:__imp_AcquireSRWLockExclusive
0x140008698  cmp     ebx, 7
0x14000869b  ja      short loc_1400086A7
0x14000869d  mov     eax, 0CCh
0x1400086a2  bt      eax, ebx
0x1400086a5  jb      short loc_1400086C7
0x1400086a7  lea     eax, [rbx-100h]
0x1400086ad  cmp     eax, 7Fh
0x1400086b0  jbe     short loc_1400086C7
0x1400086b2  mov     r9d, r15d
0x1400086b5  lea     rcx, [rdi+48h]
0x1400086b9  mov     r8d, r14d
0x1400086bc  mov     edx, ebx
0x1400086be  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400086c3  mov     bl, al
0x1400086c5  jmp     short loc_1400086D8
0x1400086c7  mov     r8d, r14d
0x1400086ca  mov     edx, ebx
0x1400086cc  lea     rcx, [rdi+8]
0x1400086d0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400086d5  mov     bl, [rdi+40h]
0x1400086d8  test    rdi, rdi
0x1400086db  jz      short loc_1400086E6
0x1400086dd  mov     rcx, rdi; SRWLock
0x1400086e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400086e6  test    bl, bl
0x1400086e8  jz      short loc_140008736
0x1400086ea  jmp     short loc_1400086F4
0x1400086ec  mov     rcx, rdi; SRWLock
0x1400086ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400086f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400086fb  jnz     short loc_140008736
0x1400086fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008704  test    rax, rax
0x140008707  jz      short loc_140008712
0x140008709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000870e  test    al, al
0x140008710  jnz     short loc_140008736
0x140008712  lea     rbx, [rsi+20h]
0x140008716  mov     rcx, rbx; SRWLock
0x140008719  call    cs:__imp_AcquireSRWLockExclusive
0x14000871f  mov     rcx, rsi; pv
0x140008722  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140008727  test    rbx, rbx
0x14000872a  jz      short loc_140008736
0x14000872c  mov     rcx, rbx; SRWLock
0x14000872f  call    cs:__imp_ReleaseSRWLockExclusive
0x140008735  nop
0x140008736  add     rsp, 28h
0x14000873a  pop     r15
0x14000873c  pop     r14
0x14000873e  pop     rdi
0x14000873f  pop     rsi
0x140008740  pop     rbp
0x140008741  pop     rbx
0x140008742  retn
```
