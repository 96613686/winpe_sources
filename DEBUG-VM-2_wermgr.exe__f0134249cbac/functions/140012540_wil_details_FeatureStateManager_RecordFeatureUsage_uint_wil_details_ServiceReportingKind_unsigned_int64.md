# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140012540`
- end: `0x14001264f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400144d0`

## callees

- `0x1400112c0`
- `0x140011374`
- `0x140012540`
- `0x140012694`
- `0x1400126c8`
- `0x140012700`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400125ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001263b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400125ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001263b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001259e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012625`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001259e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012625`

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
0x140012540  push    rbx
0x140012542  push    rbp
0x140012543  push    rsi
0x140012544  push    rdi
0x140012545  push    r14
0x140012547  push    r15
0x140012549  sub     rsp, 28h
0x14001254d  mov     r15, r9
0x140012550  mov     ebx, r8d
0x140012553  mov     r14d, edx
0x140012556  mov     rsi, rcx
0x140012559  cmp     byte ptr [rcx], 0
0x14001255c  jz      loc_140012642
0x140012562  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140012567  test    al, al
0x140012569  jz      loc_140012642
0x14001256f  mov     rdi, [rsi+18h]
0x140012573  cmp     ebx, 0FEh
0x140012579  jz      short loc_1400125F8
0x14001257b  cmp     ebx, 0C8h
0x140012581  jb      short loc_14001259B
0x140012583  cmp     ebx, 100h
0x140012589  jl      loc_140012642
0x14001258f  cmp     ebx, 200h
0x140012595  jnb     loc_140012642
0x14001259b  mov     rcx, rdi; SRWLock
0x14001259e  call    cs:__imp_AcquireSRWLockExclusive
0x1400125a4  cmp     ebx, 7
0x1400125a7  ja      short loc_1400125B3
0x1400125a9  mov     eax, 0CCh
0x1400125ae  bt      eax, ebx
0x1400125b1  jb      short loc_1400125D3
0x1400125b3  lea     eax, [rbx-100h]
0x1400125b9  cmp     eax, 7Fh
0x1400125bc  jbe     short loc_1400125D3
0x1400125be  mov     r9d, r15d
0x1400125c1  lea     rcx, [rdi+48h]
0x1400125c5  mov     r8d, r14d
0x1400125c8  mov     edx, ebx
0x1400125ca  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400125cf  mov     bl, al
0x1400125d1  jmp     short loc_1400125E4
0x1400125d3  mov     r8d, r14d
0x1400125d6  mov     edx, ebx
0x1400125d8  lea     rcx, [rdi+8]
0x1400125dc  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400125e1  mov     bl, [rdi+40h]
0x1400125e4  test    rdi, rdi
0x1400125e7  jz      short loc_1400125F2
0x1400125e9  mov     rcx, rdi; SRWLock
0x1400125ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1400125f2  test    bl, bl
0x1400125f4  jz      short loc_140012642
0x1400125f6  jmp     short loc_140012600
0x1400125f8  mov     rcx, rdi; SRWLock
0x1400125fb  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140012600  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140012607  jnz     short loc_140012642
0x140012609  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140012610  test    rax, rax
0x140012613  jz      short loc_14001261E
0x140012615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001261a  test    al, al
0x14001261c  jnz     short loc_140012642
0x14001261e  lea     rbx, [rsi+20h]
0x140012622  mov     rcx, rbx; SRWLock
0x140012625  call    cs:__imp_AcquireSRWLockExclusive
0x14001262b  mov     rcx, rsi; pv
0x14001262e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140012633  test    rbx, rbx
0x140012636  jz      short loc_140012642
0x140012638  mov     rcx, rbx; SRWLock
0x14001263b  call    cs:__imp_ReleaseSRWLockExclusive
0x140012641  nop
0x140012642  add     rsp, 28h
0x140012646  pop     r15
0x140012648  pop     r14
0x14001264a  pop     rdi
0x14001264b  pop     rsi
0x14001264c  pop     rbp
0x14001264d  pop     rbx
0x14001264e  retn
```
