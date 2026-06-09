# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008704`
- end: `0x180008816`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ab20`

## callees

- `0x1800059dc`
- `0x180005b68`
- `0x180008704`
- `0x180008894`
- `0x1800088c8`
- `0x180008900`
- `0x180011010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800087b1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008802`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800087b1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008802`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008762`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800087eb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008762`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800087eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      wil::details::FeatureStateManager::EnsureTimerUnderLock((_QWORD *)a1);
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
0x180008704  push    rbx
0x180008706  push    rbp
0x180008707  push    rsi
0x180008708  push    rdi
0x180008709  push    r14
0x18000870b  push    r15
0x18000870d  sub     rsp, 28h
0x180008711  mov     r15, r9
0x180008714  mov     ebx, r8d
0x180008717  mov     r14d, edx
0x18000871a  mov     rsi, rcx
0x18000871d  cmp     byte ptr [rcx], 0
0x180008720  jz      loc_180008809
0x180008726  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000872b  test    al, al
0x18000872d  jz      loc_180008809
0x180008733  mov     rdi, [rsi+18h]
0x180008737  cmp     ebx, 0FEh
0x18000873d  jz      short loc_1800087BE
0x18000873f  cmp     ebx, 0C8h
0x180008745  jb      short loc_18000875F
0x180008747  cmp     ebx, 100h
0x18000874d  jl      loc_180008809
0x180008753  cmp     ebx, 200h
0x180008759  jnb     loc_180008809
0x18000875f  mov     rcx, rdi; SRWLock
0x180008762  call    cs:__imp_AcquireSRWLockExclusive
0x180008768  nop
0x180008769  cmp     ebx, 7
0x18000876c  ja      short loc_180008778
0x18000876e  mov     eax, 0CCh
0x180008773  bt      eax, ebx
0x180008776  jb      short loc_180008798
0x180008778  lea     eax, [rbx-100h]
0x18000877e  cmp     eax, 7Fh
0x180008781  jbe     short loc_180008798
0x180008783  mov     r9d, r15d
0x180008786  lea     rcx, [rdi+48h]
0x18000878a  mov     r8d, r14d
0x18000878d  mov     edx, ebx
0x18000878f  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008794  mov     bl, al
0x180008796  jmp     short loc_1800087A9
0x180008798  mov     r8d, r14d
0x18000879b  mov     edx, ebx
0x18000879d  lea     rcx, [rdi+8]
0x1800087a1  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800087a6  mov     bl, [rdi+40h]
0x1800087a9  test    rdi, rdi
0x1800087ac  jz      short loc_1800087B8
0x1800087ae  mov     rcx, rdi; SRWLock
0x1800087b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087b7  nop
0x1800087b8  test    bl, bl
0x1800087ba  jz      short loc_180008809
0x1800087bc  jmp     short loc_1800087C6
0x1800087be  mov     rcx, rdi; SRWLock
0x1800087c1  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800087c6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800087cd  jnz     short loc_180008809
0x1800087cf  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800087d6  test    rax, rax
0x1800087d9  jz      short loc_1800087E4
0x1800087db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087e0  test    al, al
0x1800087e2  jnz     short loc_180008809
0x1800087e4  lea     rbx, [rsi+20h]
0x1800087e8  mov     rcx, rbx; SRWLock
0x1800087eb  call    cs:__imp_AcquireSRWLockExclusive
0x1800087f1  nop
0x1800087f2  mov     rcx, rsi; pv
0x1800087f5  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800087fa  test    rbx, rbx
0x1800087fd  jz      short loc_180008809
0x1800087ff  mov     rcx, rbx; SRWLock
0x180008802  call    cs:__imp_ReleaseSRWLockExclusive
0x180008808  nop
0x180008809  add     rsp, 28h
0x18000880d  pop     r15
0x18000880f  pop     r14
0x180008811  pop     rdi
0x180008812  pop     rsi
0x180008813  pop     rbp
0x180008814  pop     rbx
0x180008815  retn
```
