# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180009044`
- end: `0x180009164`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `288`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b910`

## callees

- `0x180006d64`
- `0x180006ee4`
- `0x180009044`
- `0x1800091e4`
- `0x180009238`
- `0x180009290`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009136`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009136`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000914c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800090fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000914c`

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
  __int64 v10; // rcx
  char v11; // bl

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v10)) )
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
      v11 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v11 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4,
              -2);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v11 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x180009044  push    rbp
0x180009046  push    rsi
0x180009047  push    rdi
0x180009048  push    r14
0x18000904a  push    r15
0x18000904c  sub     rsp, 30h
0x180009050  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180009059  mov     [rsp+58h+arg_18], rbx
0x18000905e  mov     r15, r9
0x180009061  mov     ebx, r8d
0x180009064  mov     r14d, edx
0x180009067  mov     rsi, rcx
0x18000906a  cmp     byte ptr [rcx], 0
0x18000906d  jz      loc_180009153
0x180009073  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009078  test    al, al
0x18000907a  jz      loc_180009153
0x180009080  mov     rdi, [rsi+18h]
0x180009084  cmp     ebx, 0FEh
0x18000908a  jz      short loc_180009109
0x18000908c  cmp     ebx, 0C8h
0x180009092  jb      short loc_1800090AC
0x180009094  cmp     ebx, 100h
0x18000909a  jl      loc_180009153
0x1800090a0  cmp     ebx, 200h
0x1800090a6  jnb     loc_180009153
0x1800090ac  mov     rcx, rdi; SRWLock
0x1800090af  call    cs:__imp_AcquireSRWLockExclusive
0x1800090b5  cmp     ebx, 7
0x1800090b8  ja      short loc_1800090C4
0x1800090ba  mov     eax, 0CCh
0x1800090bf  bt      eax, ebx
0x1800090c2  jb      short loc_1800090E4
0x1800090c4  lea     eax, [rbx-100h]
0x1800090ca  cmp     eax, 7Fh
0x1800090cd  jbe     short loc_1800090E4
0x1800090cf  mov     r9d, r15d
0x1800090d2  lea     rcx, [rdi+48h]
0x1800090d6  mov     r8d, r14d
0x1800090d9  mov     edx, ebx
0x1800090db  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800090e0  mov     bl, al
0x1800090e2  jmp     short loc_1800090F5
0x1800090e4  mov     r8d, r14d
0x1800090e7  mov     edx, ebx
0x1800090e9  lea     rcx, [rdi+8]
0x1800090ed  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800090f2  mov     bl, [rdi+40h]
0x1800090f5  test    rdi, rdi
0x1800090f8  jz      short loc_180009103
0x1800090fa  mov     rcx, rdi; SRWLock
0x1800090fd  call    cs:__imp_ReleaseSRWLockExclusive
0x180009103  test    bl, bl
0x180009105  jz      short loc_180009153
0x180009107  jmp     short loc_180009111
0x180009109  mov     rcx, rdi; SRWLock
0x18000910c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009111  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009118  jnz     short loc_180009153
0x18000911a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009121  test    rax, rax
0x180009124  jz      short loc_18000912F
0x180009126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912b  test    al, al
0x18000912d  jnz     short loc_180009153
0x18000912f  lea     rbx, [rsi+20h]
0x180009133  mov     rcx, rbx; SRWLock
0x180009136  call    cs:__imp_AcquireSRWLockExclusive
0x18000913c  mov     rcx, rsi; pv
0x18000913f  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180009144  test    rbx, rbx
0x180009147  jz      short loc_180009153
0x180009149  mov     rcx, rbx; SRWLock
0x18000914c  call    cs:__imp_ReleaseSRWLockExclusive
0x180009152  nop
0x180009153  mov     rbx, [rsp+58h+arg_18]
0x180009158  add     rsp, 30h
0x18000915c  pop     r15
0x18000915e  pop     r14
0x180009160  pop     rdi
0x180009161  pop     rsi
0x180009162  pop     rbp
0x180009163  retn
```
