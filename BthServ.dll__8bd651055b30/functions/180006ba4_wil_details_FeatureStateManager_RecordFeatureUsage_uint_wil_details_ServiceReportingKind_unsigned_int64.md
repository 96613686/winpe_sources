# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006ba4`
- end: `0x180006cb3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008f00`

## callees

- `0x180004c04`
- `0x180004d84`
- `0x180006ba4`
- `0x180006d34`
- `0x180006d68`
- `0x180006da0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c89`

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
0x180006ba4  push    rbx
0x180006ba6  push    rbp
0x180006ba7  push    rsi
0x180006ba8  push    rdi
0x180006ba9  push    r14
0x180006bab  push    r15
0x180006bad  sub     rsp, 28h
0x180006bb1  mov     r15, r9
0x180006bb4  mov     ebx, r8d
0x180006bb7  mov     r14d, edx
0x180006bba  mov     rsi, rcx
0x180006bbd  cmp     byte ptr [rcx], 0
0x180006bc0  jz      loc_180006CA6
0x180006bc6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006bcb  test    al, al
0x180006bcd  jz      loc_180006CA6
0x180006bd3  mov     rdi, [rsi+18h]
0x180006bd7  cmp     ebx, 0FEh
0x180006bdd  jz      short loc_180006C5C
0x180006bdf  cmp     ebx, 0C8h
0x180006be5  jb      short loc_180006BFF
0x180006be7  cmp     ebx, 100h
0x180006bed  jl      loc_180006CA6
0x180006bf3  cmp     ebx, 200h
0x180006bf9  jnb     loc_180006CA6
0x180006bff  mov     rcx, rdi; SRWLock
0x180006c02  call    cs:__imp_AcquireSRWLockExclusive
0x180006c08  cmp     ebx, 7
0x180006c0b  ja      short loc_180006C17
0x180006c0d  mov     eax, 0CCh
0x180006c12  bt      eax, ebx
0x180006c15  jb      short loc_180006C37
0x180006c17  lea     eax, [rbx-100h]
0x180006c1d  cmp     eax, 7Fh
0x180006c20  jbe     short loc_180006C37
0x180006c22  mov     r9d, r15d
0x180006c25  lea     rcx, [rdi+48h]
0x180006c29  mov     r8d, r14d
0x180006c2c  mov     edx, ebx
0x180006c2e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006c33  mov     bl, al
0x180006c35  jmp     short loc_180006C48
0x180006c37  mov     r8d, r14d
0x180006c3a  mov     edx, ebx
0x180006c3c  lea     rcx, [rdi+8]
0x180006c40  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006c45  mov     bl, [rdi+40h]
0x180006c48  test    rdi, rdi
0x180006c4b  jz      short loc_180006C56
0x180006c4d  mov     rcx, rdi; SRWLock
0x180006c50  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c56  test    bl, bl
0x180006c58  jz      short loc_180006CA6
0x180006c5a  jmp     short loc_180006C64
0x180006c5c  mov     rcx, rdi; SRWLock
0x180006c5f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006c64  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006c6b  jnz     short loc_180006CA6
0x180006c6d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006c74  test    rax, rax
0x180006c77  jz      short loc_180006C82
0x180006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7e  test    al, al
0x180006c80  jnz     short loc_180006CA6
0x180006c82  lea     rbx, [rsi+20h]
0x180006c86  mov     rcx, rbx; SRWLock
0x180006c89  call    cs:__imp_AcquireSRWLockExclusive
0x180006c8f  mov     rcx, rsi; pv
0x180006c92  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006c97  test    rbx, rbx
0x180006c9a  jz      short loc_180006CA6
0x180006c9c  mov     rcx, rbx; SRWLock
0x180006c9f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006ca5  nop
0x180006ca6  add     rsp, 28h
0x180006caa  pop     r15
0x180006cac  pop     r14
0x180006cae  pop     rdi
0x180006caf  pop     rsi
0x180006cb0  pop     rbp
0x180006cb1  pop     rbx
0x180006cb2  retn
```
