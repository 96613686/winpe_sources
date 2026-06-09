# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800147d4`
- end: `0x1800148e2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800160e0`

## callees

- `0x180012c84`
- `0x180012d38`
- `0x1800147d4`
- `0x180014954`
- `0x180014988`
- `0x1800149c0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014832`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800148b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014832`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800148b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014880`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800148cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014880`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800148cf`

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
0x1800147d4  push    rbx
0x1800147d6  push    rbp
0x1800147d7  push    rsi
0x1800147d8  push    rdi
0x1800147d9  push    r14
0x1800147db  push    r15
0x1800147dd  sub     rsp, 28h
0x1800147e1  cmp     byte ptr [rcx], 0
0x1800147e4  mov     r15, r9
0x1800147e7  mov     ebx, r8d
0x1800147ea  mov     r14d, edx
0x1800147ed  mov     rsi, rcx
0x1800147f0  jz      loc_1800148D5
0x1800147f6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800147fb  test    al, al
0x1800147fd  jz      loc_1800148D5
0x180014803  mov     rdi, [rsi+18h]
0x180014807  cmp     ebx, 0FEh
0x18001480d  jz      short loc_18001488C
0x18001480f  cmp     ebx, 0C8h
0x180014815  jb      short loc_18001482F
0x180014817  cmp     ebx, 100h
0x18001481d  jl      loc_1800148D5
0x180014823  cmp     ebx, 200h
0x180014829  jnb     loc_1800148D5
0x18001482f  mov     rcx, rdi; SRWLock
0x180014832  call    cs:__imp_AcquireSRWLockExclusive
0x180014838  cmp     ebx, 7
0x18001483b  ja      short loc_180014847
0x18001483d  mov     eax, 0CCh
0x180014842  bt      eax, ebx
0x180014845  jb      short loc_180014867
0x180014847  lea     eax, [rbx-100h]
0x18001484d  cmp     eax, 7Fh
0x180014850  jbe     short loc_180014867
0x180014852  mov     r9d, r15d
0x180014855  lea     rcx, [rdi+48h]
0x180014859  mov     r8d, r14d
0x18001485c  mov     edx, ebx
0x18001485e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014863  mov     bl, al
0x180014865  jmp     short loc_180014878
0x180014867  mov     r8d, r14d
0x18001486a  lea     rcx, [rdi+8]
0x18001486e  mov     edx, ebx
0x180014870  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014875  mov     bl, [rdi+40h]
0x180014878  test    rdi, rdi
0x18001487b  jz      short loc_180014886
0x18001487d  mov     rcx, rdi; SRWLock
0x180014880  call    cs:__imp_ReleaseSRWLockExclusive
0x180014886  test    bl, bl
0x180014888  jz      short loc_1800148D5
0x18001488a  jmp     short loc_180014894
0x18001488c  mov     rcx, rdi; SRWLock
0x18001488f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014894  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001489b  jnz     short loc_1800148D5
0x18001489d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800148a4  test    rax, rax
0x1800148a7  jz      short loc_1800148B2
0x1800148a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ae  test    al, al
0x1800148b0  jnz     short loc_1800148D5
0x1800148b2  lea     rbx, [rsi+20h]
0x1800148b6  mov     rcx, rbx; SRWLock
0x1800148b9  call    cs:__imp_AcquireSRWLockExclusive
0x1800148bf  mov     rcx, rsi; pv
0x1800148c2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800148c7  test    rbx, rbx
0x1800148ca  jz      short loc_1800148D5
0x1800148cc  mov     rcx, rbx; SRWLock
0x1800148cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800148d5  add     rsp, 28h
0x1800148d9  pop     r15
0x1800148db  pop     r14
0x1800148dd  pop     rdi
0x1800148de  pop     rsi
0x1800148df  pop     rbp
0x1800148e0  pop     rbx
0x1800148e1  retn
```
