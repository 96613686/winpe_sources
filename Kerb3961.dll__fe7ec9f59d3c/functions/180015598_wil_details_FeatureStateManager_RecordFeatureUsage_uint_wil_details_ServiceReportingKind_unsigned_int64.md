# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180015598`
- end: `0x1800156a6`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180017a90`

## callees

- `0x1800134d0`
- `0x180013648`
- `0x180015598`
- `0x1800156e4`
- `0x180015718`
- `0x180015750`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800155f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001567d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800155f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001567d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015644`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015693`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015644`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015693`

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
0x180015598  push    rbx
0x18001559a  push    rbp
0x18001559b  push    rsi
0x18001559c  push    rdi
0x18001559d  push    r14
0x18001559f  push    r15
0x1800155a1  sub     rsp, 28h
0x1800155a5  cmp     byte ptr [rcx], 0
0x1800155a8  mov     r15, r9
0x1800155ab  mov     ebx, r8d
0x1800155ae  mov     r14d, edx
0x1800155b1  mov     rsi, rcx
0x1800155b4  jz      loc_180015699
0x1800155ba  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800155bf  test    al, al
0x1800155c1  jz      loc_180015699
0x1800155c7  mov     rdi, [rsi+18h]
0x1800155cb  cmp     ebx, 0FEh
0x1800155d1  jz      short loc_180015650
0x1800155d3  cmp     ebx, 0C8h
0x1800155d9  jb      short loc_1800155F3
0x1800155db  cmp     ebx, 100h
0x1800155e1  jl      loc_180015699
0x1800155e7  cmp     ebx, 200h
0x1800155ed  jnb     loc_180015699
0x1800155f3  mov     rcx, rdi; SRWLock
0x1800155f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800155fc  cmp     ebx, 7
0x1800155ff  ja      short loc_18001560B
0x180015601  mov     eax, 0CCh
0x180015606  bt      eax, ebx
0x180015609  jb      short loc_18001562B
0x18001560b  lea     eax, [rbx-100h]
0x180015611  cmp     eax, 7Fh
0x180015614  jbe     short loc_18001562B
0x180015616  mov     r9d, r15d
0x180015619  lea     rcx, [rdi+48h]
0x18001561d  mov     r8d, r14d
0x180015620  mov     edx, ebx
0x180015622  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015627  mov     bl, al
0x180015629  jmp     short loc_18001563C
0x18001562b  mov     r8d, r14d
0x18001562e  lea     rcx, [rdi+8]
0x180015632  mov     edx, ebx
0x180015634  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015639  mov     bl, [rdi+40h]
0x18001563c  test    rdi, rdi
0x18001563f  jz      short loc_18001564A
0x180015641  mov     rcx, rdi; SRWLock
0x180015644  call    cs:__imp_ReleaseSRWLockExclusive
0x18001564a  test    bl, bl
0x18001564c  jz      short loc_180015699
0x18001564e  jmp     short loc_180015658
0x180015650  mov     rcx, rdi; SRWLock
0x180015653  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180015658  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001565f  jnz     short loc_180015699
0x180015661  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180015668  test    rax, rax
0x18001566b  jz      short loc_180015676
0x18001566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015672  test    al, al
0x180015674  jnz     short loc_180015699
0x180015676  lea     rbx, [rsi+20h]
0x18001567a  mov     rcx, rbx; SRWLock
0x18001567d  call    cs:__imp_AcquireSRWLockExclusive
0x180015683  mov     rcx, rsi; pv
0x180015686  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18001568b  test    rbx, rbx
0x18001568e  jz      short loc_180015699
0x180015690  mov     rcx, rbx; SRWLock
0x180015693  call    cs:__imp_ReleaseSRWLockExclusive
0x180015699  add     rsp, 28h
0x18001569d  pop     r15
0x18001569f  pop     r14
0x1800156a1  pop     rdi
0x1800156a2  pop     rsi
0x1800156a3  pop     rbp
0x1800156a4  pop     rbx
0x1800156a5  retn
```
