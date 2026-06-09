# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006b54`
- end: `0x180006c80`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009060`

## callees

- `0x18000410c`
- `0x1800042bc`
- `0x180006b54`
- `0x180006cc8`
- `0x180006d00`
- `0x180006d38`
- `0x18003e010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006c0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006c65`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006c0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006c65`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006bb6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006c49`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006bb6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006c49`

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
0x180006b54  push    rbx
0x180006b56  push    rbp
0x180006b57  push    rsi
0x180006b58  push    rdi
0x180006b59  push    r14
0x180006b5b  push    r15
0x180006b5d  sub     rsp, 28h
0x180006b61  mov     r15, r9
0x180006b64  mov     ebx, r8d
0x180006b67  mov     r14d, edx
0x180006b6a  mov     rsi, rcx
0x180006b6d  cmp     byte ptr [rcx], 0
0x180006b70  jz      loc_180006C72
0x180006b76  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006b7b  test    al, al
0x180006b7d  jz      loc_180006C72
0x180006b83  mov     rdi, [rsi+18h]
0x180006b87  cmp     ebx, 0FEh
0x180006b8d  jz      loc_180006C1C
0x180006b93  cmp     ebx, 0C8h
0x180006b99  jb      short loc_180006BB3
0x180006b9b  cmp     ebx, 100h
0x180006ba1  jl      loc_180006C72
0x180006ba7  cmp     ebx, 200h
0x180006bad  jnb     loc_180006C72
0x180006bb3  mov     rcx, rdi; SRWLock
0x180006bb6  call    cs:__imp_AcquireSRWLockExclusive
0x180006bbd  nop     dword ptr [rax+rax+00h]
0x180006bc2  cmp     ebx, 7
0x180006bc5  ja      short loc_180006BD1
0x180006bc7  mov     eax, 0CCh
0x180006bcc  bt      eax, ebx
0x180006bcf  jb      short loc_180006BF1
0x180006bd1  lea     eax, [rbx-100h]
0x180006bd7  cmp     eax, 7Fh
0x180006bda  jbe     short loc_180006BF1
0x180006bdc  mov     r9d, r15d
0x180006bdf  lea     rcx, [rdi+48h]
0x180006be3  mov     r8d, r14d
0x180006be6  mov     edx, ebx
0x180006be8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006bed  mov     bl, al
0x180006bef  jmp     short loc_180006C02
0x180006bf1  mov     r8d, r14d
0x180006bf4  mov     edx, ebx
0x180006bf6  lea     rcx, [rdi+8]
0x180006bfa  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006bff  mov     bl, [rdi+40h]
0x180006c02  test    rdi, rdi
0x180006c05  jz      short loc_180006C16
0x180006c07  mov     rcx, rdi; SRWLock
0x180006c0a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c11  nop     dword ptr [rax+rax+00h]
0x180006c16  test    bl, bl
0x180006c18  jz      short loc_180006C72
0x180006c1a  jmp     short loc_180006C24
0x180006c1c  mov     rcx, rdi; SRWLock
0x180006c1f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006c24  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006c2b  jnz     short loc_180006C72
0x180006c2d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006c34  test    rax, rax
0x180006c37  jz      short loc_180006C42
0x180006c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c3e  test    al, al
0x180006c40  jnz     short loc_180006C72
0x180006c42  lea     rbx, [rsi+20h]
0x180006c46  mov     rcx, rbx; SRWLock
0x180006c49  call    cs:__imp_AcquireSRWLockExclusive
0x180006c50  nop     dword ptr [rax+rax+00h]
0x180006c55  mov     rcx, rsi; pv
0x180006c58  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006c5d  test    rbx, rbx
0x180006c60  jz      short loc_180006C72
0x180006c62  mov     rcx, rbx; SRWLock
0x180006c65  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c6c  nop     dword ptr [rax+rax+00h]
0x180006c71  nop
0x180006c72  add     rsp, 28h
0x180006c76  pop     r15
0x180006c78  pop     r14
0x180006c7a  pop     rdi
0x180006c7b  pop     rsi
0x180006c7c  pop     rbp
0x180006c7d  pop     rbx
0x180006c7e  retn
```
