# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f1c4`
- end: `0x18000f2f0`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180011c40`

## callees

- `0x18000c870`
- `0x18000ca18`
- `0x18000f1c4`
- `0x18000f374`
- `0x18000f3ac`
- `0x18000f3e4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f27a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f2d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f27a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f2d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f226`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f226`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2b9`

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
0x18000f1c4  push    rbx
0x18000f1c6  push    rbp
0x18000f1c7  push    rsi
0x18000f1c8  push    rdi
0x18000f1c9  push    r14
0x18000f1cb  push    r15
0x18000f1cd  sub     rsp, 28h
0x18000f1d1  mov     r15, r9
0x18000f1d4  mov     ebx, r8d
0x18000f1d7  mov     r14d, edx
0x18000f1da  mov     rsi, rcx
0x18000f1dd  cmp     byte ptr [rcx], 0
0x18000f1e0  jz      loc_18000F2E2
0x18000f1e6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f1eb  test    al, al
0x18000f1ed  jz      loc_18000F2E2
0x18000f1f3  mov     rdi, [rsi+18h]
0x18000f1f7  cmp     ebx, 0FEh
0x18000f1fd  jz      loc_18000F28C
0x18000f203  cmp     ebx, 0C8h
0x18000f209  jb      short loc_18000F223
0x18000f20b  cmp     ebx, 100h
0x18000f211  jl      loc_18000F2E2
0x18000f217  cmp     ebx, 200h
0x18000f21d  jnb     loc_18000F2E2
0x18000f223  mov     rcx, rdi; SRWLock
0x18000f226  call    cs:__imp_AcquireSRWLockExclusive
0x18000f22d  nop     dword ptr [rax+rax+00h]
0x18000f232  cmp     ebx, 7
0x18000f235  ja      short loc_18000F241
0x18000f237  mov     eax, 0CCh
0x18000f23c  bt      eax, ebx
0x18000f23f  jb      short loc_18000F261
0x18000f241  lea     eax, [rbx-100h]
0x18000f247  cmp     eax, 7Fh
0x18000f24a  jbe     short loc_18000F261
0x18000f24c  mov     r9d, r15d
0x18000f24f  lea     rcx, [rdi+48h]
0x18000f253  mov     r8d, r14d
0x18000f256  mov     edx, ebx
0x18000f258  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f25d  mov     bl, al
0x18000f25f  jmp     short loc_18000F272
0x18000f261  mov     r8d, r14d
0x18000f264  mov     edx, ebx
0x18000f266  lea     rcx, [rdi+8]
0x18000f26a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f26f  mov     bl, [rdi+40h]
0x18000f272  test    rdi, rdi
0x18000f275  jz      short loc_18000F286
0x18000f277  mov     rcx, rdi; SRWLock
0x18000f27a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f281  nop     dword ptr [rax+rax+00h]
0x18000f286  test    bl, bl
0x18000f288  jz      short loc_18000F2E2
0x18000f28a  jmp     short loc_18000F294
0x18000f28c  mov     rcx, rdi; SRWLock
0x18000f28f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f294  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f29b  jnz     short loc_18000F2E2
0x18000f29d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f2a4  test    rax, rax
0x18000f2a7  jz      short loc_18000F2B2
0x18000f2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2ae  test    al, al
0x18000f2b0  jnz     short loc_18000F2E2
0x18000f2b2  lea     rbx, [rsi+20h]
0x18000f2b6  mov     rcx, rbx; SRWLock
0x18000f2b9  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2c0  nop     dword ptr [rax+rax+00h]
0x18000f2c5  mov     rcx, rsi; pv
0x18000f2c8  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000f2cd  test    rbx, rbx
0x18000f2d0  jz      short loc_18000F2E2
0x18000f2d2  mov     rcx, rbx; SRWLock
0x18000f2d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f2dc  nop     dword ptr [rax+rax+00h]
0x18000f2e1  nop
0x18000f2e2  add     rsp, 28h
0x18000f2e6  pop     r15
0x18000f2e8  pop     r14
0x18000f2ea  pop     rdi
0x18000f2eb  pop     rsi
0x18000f2ec  pop     rbp
0x18000f2ed  pop     rbx
0x18000f2ee  retn
```
