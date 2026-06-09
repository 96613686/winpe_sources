# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007884`
- end: `0x18000799c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `280`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800099c0`

## callees

- `0x180005834`
- `0x1800059b4`
- `0x180007884`
- `0x1800079dc`
- `0x180007a10`
- `0x180007a48`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800078eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007972`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800078eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007972`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007988`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007988`

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

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)a1) )
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
0x180007884  push    rbx
0x180007886  push    rbp
0x180007887  push    rsi
0x180007888  push    rdi
0x180007889  push    r14
0x18000788b  push    r15
0x18000788d  sub     rsp, 38h
0x180007891  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18000789a  mov     r15, r9
0x18000789d  mov     ebx, r8d
0x1800078a0  mov     r14d, edx
0x1800078a3  mov     rsi, rcx
0x1800078a6  cmp     byte ptr [rcx], 0
0x1800078a9  jz      loc_18000798F
0x1800078af  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800078b4  test    al, al
0x1800078b6  jz      loc_18000798F
0x1800078bc  mov     rdi, [rsi+18h]
0x1800078c0  cmp     ebx, 0FEh
0x1800078c6  jz      short loc_180007945
0x1800078c8  cmp     ebx, 0C8h
0x1800078ce  jb      short loc_1800078E8
0x1800078d0  cmp     ebx, 100h
0x1800078d6  jl      loc_18000798F
0x1800078dc  cmp     ebx, 200h
0x1800078e2  jnb     loc_18000798F
0x1800078e8  mov     rcx, rdi; SRWLock
0x1800078eb  call    cs:__imp_AcquireSRWLockExclusive
0x1800078f1  cmp     ebx, 7
0x1800078f4  ja      short loc_180007900
0x1800078f6  mov     eax, 0CCh
0x1800078fb  bt      eax, ebx
0x1800078fe  jb      short loc_180007920
0x180007900  lea     eax, [rbx-100h]
0x180007906  cmp     eax, 7Fh
0x180007909  jbe     short loc_180007920
0x18000790b  mov     r9d, r15d
0x18000790e  lea     rcx, [rdi+48h]
0x180007912  mov     r8d, r14d
0x180007915  mov     edx, ebx
0x180007917  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000791c  mov     bl, al
0x18000791e  jmp     short loc_180007931
0x180007920  mov     r8d, r14d
0x180007923  mov     edx, ebx
0x180007925  lea     rcx, [rdi+8]
0x180007929  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000792e  mov     bl, [rdi+40h]
0x180007931  test    rdi, rdi
0x180007934  jz      short loc_18000793F
0x180007936  mov     rcx, rdi; SRWLock
0x180007939  call    cs:__imp_ReleaseSRWLockExclusive
0x18000793f  test    bl, bl
0x180007941  jz      short loc_18000798F
0x180007943  jmp     short loc_18000794D
0x180007945  mov     rcx, rdi; SRWLock
0x180007948  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000794d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007954  jnz     short loc_18000798F
0x180007956  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000795d  test    rax, rax
0x180007960  jz      short loc_18000796B
0x180007962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007967  test    al, al
0x180007969  jnz     short loc_18000798F
0x18000796b  lea     rbx, [rsi+20h]
0x18000796f  mov     rcx, rbx; SRWLock
0x180007972  call    cs:__imp_AcquireSRWLockExclusive
0x180007978  mov     rcx, rsi; pv
0x18000797b  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007980  test    rbx, rbx
0x180007983  jz      short loc_18000798F
0x180007985  mov     rcx, rbx; SRWLock
0x180007988  call    cs:__imp_ReleaseSRWLockExclusive
0x18000798e  nop
0x18000798f  add     rsp, 38h
0x180007993  pop     r15
0x180007995  pop     r14
0x180007997  pop     rdi
0x180007998  pop     rsi
0x180007999  pop     rbp
0x18000799a  pop     rbx
0x18000799b  retn
```
