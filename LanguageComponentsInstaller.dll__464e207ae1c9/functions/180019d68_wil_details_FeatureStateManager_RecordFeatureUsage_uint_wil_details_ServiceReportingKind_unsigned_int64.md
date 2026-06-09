# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180019d68`
- end: `0x180019e7e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `278`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18001cda0`

## callees

- `0x180015fac`
- `0x18001621c`
- `0x180019d68`
- `0x180019ec4`
- `0x180019f18`
- `0x180019f70`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019dc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019e50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019dc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019e50`

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
0x180019d68  mov     [rsp+arg_18], rbx
0x180019d6d  push    rbp
0x180019d6e  push    rsi
0x180019d6f  push    rdi
0x180019d70  push    r14
0x180019d72  push    r15
0x180019d74  sub     rsp, 20h
0x180019d78  mov     r15, r9
0x180019d7b  mov     ebx, r8d
0x180019d7e  mov     r14d, edx
0x180019d81  mov     rsi, rcx
0x180019d84  cmp     byte ptr [rcx], 0
0x180019d87  jz      loc_180019E6D
0x180019d8d  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180019d92  test    al, al
0x180019d94  jz      loc_180019E6D
0x180019d9a  mov     rdi, [rsi+18h]
0x180019d9e  cmp     ebx, 0FEh
0x180019da4  jz      short loc_180019E23
0x180019da6  cmp     ebx, 0C8h
0x180019dac  jb      short loc_180019DC6
0x180019dae  cmp     ebx, 100h
0x180019db4  jl      loc_180019E6D
0x180019dba  cmp     ebx, 200h
0x180019dc0  jnb     loc_180019E6D
0x180019dc6  mov     rcx, rdi; SRWLock
0x180019dc9  call    cs:__imp_AcquireSRWLockExclusive
0x180019dcf  cmp     ebx, 7
0x180019dd2  ja      short loc_180019DDE
0x180019dd4  mov     eax, 0CCh
0x180019dd9  bt      eax, ebx
0x180019ddc  jb      short loc_180019DFE
0x180019dde  lea     eax, [rbx-100h]
0x180019de4  cmp     eax, 7Fh
0x180019de7  jbe     short loc_180019DFE
0x180019de9  mov     r9d, r15d
0x180019dec  lea     rcx, [rdi+48h]
0x180019df0  mov     r8d, r14d
0x180019df3  mov     edx, ebx
0x180019df5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180019dfa  mov     bl, al
0x180019dfc  jmp     short loc_180019E0F
0x180019dfe  mov     r8d, r14d
0x180019e01  mov     edx, ebx
0x180019e03  lea     rcx, [rdi+8]
0x180019e07  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180019e0c  mov     bl, [rdi+40h]
0x180019e0f  test    rdi, rdi
0x180019e12  jz      short loc_180019E1D
0x180019e14  mov     rcx, rdi; SRWLock
0x180019e17  call    cs:__imp_ReleaseSRWLockExclusive
0x180019e1d  test    bl, bl
0x180019e1f  jz      short loc_180019E6D
0x180019e21  jmp     short loc_180019E2B
0x180019e23  mov     rcx, rdi; SRWLock
0x180019e26  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180019e2b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180019e32  jnz     short loc_180019E6D
0x180019e34  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180019e3b  test    rax, rax
0x180019e3e  jz      short loc_180019E49
0x180019e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e45  test    al, al
0x180019e47  jnz     short loc_180019E6D
0x180019e49  lea     rbx, [rsi+20h]
0x180019e4d  mov     rcx, rbx; SRWLock
0x180019e50  call    cs:__imp_AcquireSRWLockExclusive
0x180019e56  mov     rcx, rsi; pv
0x180019e59  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180019e5e  test    rbx, rbx
0x180019e61  jz      short loc_180019E6D
0x180019e63  mov     rcx, rbx; SRWLock
0x180019e66  call    cs:__imp_ReleaseSRWLockExclusive
0x180019e6c  nop
0x180019e6d  mov     rbx, [rsp+48h+arg_18]
0x180019e72  add     rsp, 20h
0x180019e76  pop     r15
0x180019e78  pop     r14
0x180019e7a  pop     rdi
0x180019e7b  pop     rsi
0x180019e7c  pop     rbp
0x180019e7d  retn
```
