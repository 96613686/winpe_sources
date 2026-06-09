# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000a334`
- end: `0x14000a443`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000c220`

## callees

- `0x1400091c4`
- `0x140009278`
- `0x14000a334`
- `0x14000a44c`
- `0x14000a480`
- `0x14000a4b8`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a392`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a419`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a392`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a419`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a3e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a42f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a3e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a42f`

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
0x14000a334  push    rbx
0x14000a336  push    rbp
0x14000a337  push    rsi
0x14000a338  push    rdi
0x14000a339  push    r14
0x14000a33b  push    r15
0x14000a33d  sub     rsp, 28h
0x14000a341  mov     r15, r9
0x14000a344  mov     ebx, r8d
0x14000a347  mov     r14d, edx
0x14000a34a  mov     rsi, rcx
0x14000a34d  cmp     byte ptr [rcx], 0
0x14000a350  jz      loc_14000A436
0x14000a356  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000a35b  test    al, al
0x14000a35d  jz      loc_14000A436
0x14000a363  mov     rdi, [rsi+18h]
0x14000a367  cmp     ebx, 0FEh
0x14000a36d  jz      short loc_14000A3EC
0x14000a36f  cmp     ebx, 0C8h
0x14000a375  jb      short loc_14000A38F
0x14000a377  cmp     ebx, 100h
0x14000a37d  jl      loc_14000A436
0x14000a383  cmp     ebx, 200h
0x14000a389  jnb     loc_14000A436
0x14000a38f  mov     rcx, rdi; SRWLock
0x14000a392  call    cs:__imp_AcquireSRWLockExclusive
0x14000a398  cmp     ebx, 7
0x14000a39b  ja      short loc_14000A3A7
0x14000a39d  mov     eax, 0CCh
0x14000a3a2  bt      eax, ebx
0x14000a3a5  jb      short loc_14000A3C7
0x14000a3a7  lea     eax, [rbx-100h]
0x14000a3ad  cmp     eax, 7Fh
0x14000a3b0  jbe     short loc_14000A3C7
0x14000a3b2  mov     r9d, r15d
0x14000a3b5  lea     rcx, [rdi+48h]
0x14000a3b9  mov     r8d, r14d
0x14000a3bc  mov     edx, ebx
0x14000a3be  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000a3c3  mov     bl, al
0x14000a3c5  jmp     short loc_14000A3D8
0x14000a3c7  mov     r8d, r14d
0x14000a3ca  mov     edx, ebx
0x14000a3cc  lea     rcx, [rdi+8]
0x14000a3d0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000a3d5  mov     bl, [rdi+40h]
0x14000a3d8  test    rdi, rdi
0x14000a3db  jz      short loc_14000A3E6
0x14000a3dd  mov     rcx, rdi; SRWLock
0x14000a3e0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a3e6  test    bl, bl
0x14000a3e8  jz      short loc_14000A436
0x14000a3ea  jmp     short loc_14000A3F4
0x14000a3ec  mov     rcx, rdi; SRWLock
0x14000a3ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000a3f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a3fb  jnz     short loc_14000A436
0x14000a3fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a404  test    rax, rax
0x14000a407  jz      short loc_14000A412
0x14000a409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a40e  test    al, al
0x14000a410  jnz     short loc_14000A436
0x14000a412  lea     rbx, [rsi+20h]
0x14000a416  mov     rcx, rbx; SRWLock
0x14000a419  call    cs:__imp_AcquireSRWLockExclusive
0x14000a41f  mov     rcx, rsi; pv
0x14000a422  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000a427  test    rbx, rbx
0x14000a42a  jz      short loc_14000A436
0x14000a42c  mov     rcx, rbx; SRWLock
0x14000a42f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a435  nop
0x14000a436  add     rsp, 28h
0x14000a43a  pop     r15
0x14000a43c  pop     r14
0x14000a43e  pop     rdi
0x14000a43f  pop     rsi
0x14000a440  pop     rbp
0x14000a441  pop     rbx
0x14000a442  retn
```
