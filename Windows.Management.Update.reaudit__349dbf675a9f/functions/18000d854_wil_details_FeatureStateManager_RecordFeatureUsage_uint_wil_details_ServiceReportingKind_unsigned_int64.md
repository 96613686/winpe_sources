# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000d854`
- end: `0x18000d997`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ffd0`

## callees

- `0x18000b1a4`
- `0x18000b358`
- `0x18000d854`
- `0x18000da14`
- `0x18000da4c`
- `0x18000da84`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d915`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d970`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d915`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d970`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d8c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d954`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d8c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d954`

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
0x18000d854  mov     [rsp+arg_0], rbx
0x18000d859  mov     [rsp+arg_8], rbp
0x18000d85e  mov     [rsp+arg_10], rsi
0x18000d863  push    rdi
0x18000d864  push    r14
0x18000d866  push    r15
0x18000d868  sub     rsp, 20h
0x18000d86c  mov     r15, r9
0x18000d86f  mov     ebx, r8d
0x18000d872  mov     r14d, edx
0x18000d875  mov     rsi, rcx
0x18000d878  cmp     byte ptr [rcx], 0
0x18000d87b  jz      loc_18000D97D
0x18000d881  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000d886  test    al, al
0x18000d888  jz      loc_18000D97D
0x18000d88e  mov     rdi, [rsi+18h]
0x18000d892  cmp     ebx, 0FEh
0x18000d898  jz      loc_18000D927
0x18000d89e  cmp     ebx, 0C8h
0x18000d8a4  jb      short loc_18000D8BE
0x18000d8a6  cmp     ebx, 100h
0x18000d8ac  jl      loc_18000D97D
0x18000d8b2  cmp     ebx, 200h
0x18000d8b8  jnb     loc_18000D97D
0x18000d8be  mov     rcx, rdi; SRWLock
0x18000d8c1  call    cs:__imp_AcquireSRWLockExclusive
0x18000d8c8  nop     dword ptr [rax+rax+00h]
0x18000d8cd  cmp     ebx, 7
0x18000d8d0  ja      short loc_18000D8DC
0x18000d8d2  mov     eax, 0CCh
0x18000d8d7  bt      eax, ebx
0x18000d8da  jb      short loc_18000D8FC
0x18000d8dc  lea     eax, [rbx-100h]
0x18000d8e2  cmp     eax, 7Fh
0x18000d8e5  jbe     short loc_18000D8FC
0x18000d8e7  lea     rcx, [rdi+48h]
0x18000d8eb  mov     r9d, r15d
0x18000d8ee  mov     r8d, r14d
0x18000d8f1  mov     edx, ebx
0x18000d8f3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d8f8  mov     bl, al
0x18000d8fa  jmp     short loc_18000D90D
0x18000d8fc  mov     r8d, r14d
0x18000d8ff  mov     edx, ebx
0x18000d901  lea     rcx, [rdi+8]
0x18000d905  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d90a  mov     bl, [rdi+40h]
0x18000d90d  test    rdi, rdi
0x18000d910  jz      short loc_18000D921
0x18000d912  mov     rcx, rdi; SRWLock
0x18000d915  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d91c  nop     dword ptr [rax+rax+00h]
0x18000d921  test    bl, bl
0x18000d923  jz      short loc_18000D97D
0x18000d925  jmp     short loc_18000D92F
0x18000d927  mov     rcx, rdi; SRWLock
0x18000d92a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000d92f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d936  jnz     short loc_18000D97D
0x18000d938  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d93f  test    rax, rax
0x18000d942  jz      short loc_18000D94D
0x18000d944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d949  test    al, al
0x18000d94b  jnz     short loc_18000D97D
0x18000d94d  lea     rbx, [rsi+20h]
0x18000d951  mov     rcx, rbx; SRWLock
0x18000d954  call    cs:__imp_AcquireSRWLockExclusive
0x18000d95b  nop     dword ptr [rax+rax+00h]
0x18000d960  mov     rcx, rsi; pv
0x18000d963  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000d968  test    rbx, rbx
0x18000d96b  jz      short loc_18000D97D
0x18000d96d  mov     rcx, rbx; SRWLock
0x18000d970  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d977  nop     dword ptr [rax+rax+00h]
0x18000d97c  nop
0x18000d97d  mov     rbx, [rsp+38h+arg_0]
0x18000d982  mov     rbp, [rsp+38h+arg_8]
0x18000d987  mov     rsi, [rsp+38h+arg_10]
0x18000d98c  add     rsp, 20h
0x18000d990  pop     r15
0x18000d992  pop     r14
0x18000d994  pop     rdi
0x18000d995  retn
```
