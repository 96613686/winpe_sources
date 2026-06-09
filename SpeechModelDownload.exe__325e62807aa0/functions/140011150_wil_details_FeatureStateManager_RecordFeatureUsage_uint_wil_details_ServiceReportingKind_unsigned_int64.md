# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140011150`
- end: `0x14001125f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140012d90`

## callees

- `0x14000e684`
- `0x14000e7fc`
- `0x140011150`
- `0x1400112a4`
- `0x1400112d8`
- `0x140011310`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400111fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001124b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400111fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001124b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400111ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011235`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400111ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011235`

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
0x140011150  push    rbx
0x140011152  push    rbp
0x140011153  push    rsi
0x140011154  push    rdi
0x140011155  push    r14
0x140011157  push    r15
0x140011159  sub     rsp, 28h
0x14001115d  mov     r15, r9
0x140011160  mov     ebx, r8d
0x140011163  mov     r14d, edx
0x140011166  mov     rsi, rcx
0x140011169  cmp     byte ptr [rcx], 0
0x14001116c  jz      loc_140011252
0x140011172  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140011177  test    al, al
0x140011179  jz      loc_140011252
0x14001117f  mov     rdi, [rsi+18h]
0x140011183  cmp     ebx, 0FEh
0x140011189  jz      short loc_140011208
0x14001118b  cmp     ebx, 0C8h
0x140011191  jb      short loc_1400111AB
0x140011193  cmp     ebx, 100h
0x140011199  jl      loc_140011252
0x14001119f  cmp     ebx, 200h
0x1400111a5  jnb     loc_140011252
0x1400111ab  mov     rcx, rdi; SRWLock
0x1400111ae  call    cs:__imp_AcquireSRWLockExclusive
0x1400111b4  cmp     ebx, 7
0x1400111b7  ja      short loc_1400111C3
0x1400111b9  mov     eax, 0CCh
0x1400111be  bt      eax, ebx
0x1400111c1  jb      short loc_1400111E3
0x1400111c3  lea     eax, [rbx-100h]
0x1400111c9  cmp     eax, 7Fh
0x1400111cc  jbe     short loc_1400111E3
0x1400111ce  mov     r9d, r15d
0x1400111d1  lea     rcx, [rdi+48h]
0x1400111d5  mov     r8d, r14d
0x1400111d8  mov     edx, ebx
0x1400111da  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400111df  mov     bl, al
0x1400111e1  jmp     short loc_1400111F4
0x1400111e3  mov     r8d, r14d
0x1400111e6  mov     edx, ebx
0x1400111e8  lea     rcx, [rdi+8]
0x1400111ec  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400111f1  mov     bl, [rdi+40h]
0x1400111f4  test    rdi, rdi
0x1400111f7  jz      short loc_140011202
0x1400111f9  mov     rcx, rdi; SRWLock
0x1400111fc  call    cs:__imp_ReleaseSRWLockExclusive
0x140011202  test    bl, bl
0x140011204  jz      short loc_140011252
0x140011206  jmp     short loc_140011210
0x140011208  mov     rcx, rdi; SRWLock
0x14001120b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140011210  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140011217  jnz     short loc_140011252
0x140011219  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140011220  test    rax, rax
0x140011223  jz      short loc_14001122E
0x140011225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001122a  test    al, al
0x14001122c  jnz     short loc_140011252
0x14001122e  lea     rbx, [rsi+20h]
0x140011232  mov     rcx, rbx; SRWLock
0x140011235  call    cs:__imp_AcquireSRWLockExclusive
0x14001123b  mov     rcx, rsi; pv
0x14001123e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140011243  test    rbx, rbx
0x140011246  jz      short loc_140011252
0x140011248  mov     rcx, rbx; SRWLock
0x14001124b  call    cs:__imp_ReleaseSRWLockExclusive
0x140011251  nop
0x140011252  add     rsp, 28h
0x140011256  pop     r15
0x140011258  pop     r14
0x14001125a  pop     rdi
0x14001125b  pop     rsi
0x14001125c  pop     rbp
0x14001125d  pop     rbx
0x14001125e  retn
```
