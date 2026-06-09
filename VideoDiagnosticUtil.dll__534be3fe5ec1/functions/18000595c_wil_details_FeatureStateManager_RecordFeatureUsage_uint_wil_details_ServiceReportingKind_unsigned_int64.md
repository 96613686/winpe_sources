# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000595c`
- end: `0x180005a87`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800074b0`

## callees

- `0x180003ce4`
- `0x180003db0`
- `0x18000595c`
- `0x180005ad0`
- `0x180005b08`
- `0x180005b40`
- `0x18000a010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800059be`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005a51`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800059be`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005a51`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005a12`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005a6d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005a12`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005a6d`

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
0x18000595c  push    rbx
0x18000595e  push    rbp
0x18000595f  push    rsi
0x180005960  push    rdi
0x180005961  push    r14
0x180005963  push    r15
0x180005965  sub     rsp, 28h
0x180005969  cmp     byte ptr [rcx], 0
0x18000596c  mov     r15, r9
0x18000596f  mov     ebx, r8d
0x180005972  mov     r14d, edx
0x180005975  mov     rsi, rcx
0x180005978  jz      loc_180005A79
0x18000597e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005983  test    al, al
0x180005985  jz      loc_180005A79
0x18000598b  mov     rdi, [rsi+18h]
0x18000598f  cmp     ebx, 0FEh
0x180005995  jz      loc_180005A24
0x18000599b  cmp     ebx, 0C8h
0x1800059a1  jb      short loc_1800059BB
0x1800059a3  cmp     ebx, 100h
0x1800059a9  jl      loc_180005A79
0x1800059af  cmp     ebx, 200h
0x1800059b5  jnb     loc_180005A79
0x1800059bb  mov     rcx, rdi; SRWLock
0x1800059be  call    cs:__imp_AcquireSRWLockExclusive
0x1800059c5  nop     dword ptr [rax+rax+00h]
0x1800059ca  cmp     ebx, 7
0x1800059cd  ja      short loc_1800059D9
0x1800059cf  mov     eax, 0CCh
0x1800059d4  bt      eax, ebx
0x1800059d7  jb      short loc_1800059F9
0x1800059d9  lea     eax, [rbx-100h]
0x1800059df  cmp     eax, 7Fh
0x1800059e2  jbe     short loc_1800059F9
0x1800059e4  mov     r9d, r15d
0x1800059e7  lea     rcx, [rdi+48h]
0x1800059eb  mov     r8d, r14d
0x1800059ee  mov     edx, ebx
0x1800059f0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800059f5  mov     bl, al
0x1800059f7  jmp     short loc_180005A0A
0x1800059f9  mov     r8d, r14d
0x1800059fc  lea     rcx, [rdi+8]
0x180005a00  mov     edx, ebx
0x180005a02  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005a07  mov     bl, [rdi+40h]
0x180005a0a  test    rdi, rdi
0x180005a0d  jz      short loc_180005A1E
0x180005a0f  mov     rcx, rdi; SRWLock
0x180005a12  call    cs:__imp_ReleaseSRWLockExclusive
0x180005a19  nop     dword ptr [rax+rax+00h]
0x180005a1e  test    bl, bl
0x180005a20  jz      short loc_180005A79
0x180005a22  jmp     short loc_180005A2C
0x180005a24  mov     rcx, rdi; SRWLock
0x180005a27  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005a2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005a33  jnz     short loc_180005A79
0x180005a35  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005a3c  test    rax, rax
0x180005a3f  jz      short loc_180005A4A
0x180005a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a46  test    al, al
0x180005a48  jnz     short loc_180005A79
0x180005a4a  lea     rbx, [rsi+20h]
0x180005a4e  mov     rcx, rbx; SRWLock
0x180005a51  call    cs:__imp_AcquireSRWLockExclusive
0x180005a58  nop     dword ptr [rax+rax+00h]
0x180005a5d  mov     rcx, rsi; pv
0x180005a60  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180005a65  test    rbx, rbx
0x180005a68  jz      short loc_180005A79
0x180005a6a  mov     rcx, rbx; SRWLock
0x180005a6d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005a74  nop     dword ptr [rax+rax+00h]
0x180005a79  add     rsp, 28h
0x180005a7d  pop     r15
0x180005a7f  pop     r14
0x180005a81  pop     rdi
0x180005a82  pop     rsi
0x180005a83  pop     rbp
0x180005a84  pop     rbx
0x180005a85  retn
```
