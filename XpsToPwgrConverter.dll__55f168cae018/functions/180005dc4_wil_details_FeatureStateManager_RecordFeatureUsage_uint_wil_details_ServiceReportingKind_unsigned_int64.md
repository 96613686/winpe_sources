# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005dc4`
- end: `0x180005ed3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007f20`

## callees

- `0x180004254`
- `0x180004308`
- `0x180005dc4`
- `0x180005f14`
- `0x180005f48`
- `0x180005f80`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ea9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ebf`

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
0x180005dc4  push    rbx
0x180005dc6  push    rbp
0x180005dc7  push    rsi
0x180005dc8  push    rdi
0x180005dc9  push    r14
0x180005dcb  push    r15
0x180005dcd  sub     rsp, 28h
0x180005dd1  mov     r15, r9
0x180005dd4  mov     ebx, r8d
0x180005dd7  mov     r14d, edx
0x180005dda  mov     rsi, rcx
0x180005ddd  cmp     byte ptr [rcx], 0
0x180005de0  jz      loc_180005EC6
0x180005de6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005deb  test    al, al
0x180005ded  jz      loc_180005EC6
0x180005df3  mov     rdi, [rsi+18h]
0x180005df7  cmp     ebx, 0FEh
0x180005dfd  jz      short loc_180005E7C
0x180005dff  cmp     ebx, 0C8h
0x180005e05  jb      short loc_180005E1F
0x180005e07  cmp     ebx, 100h
0x180005e0d  jl      loc_180005EC6
0x180005e13  cmp     ebx, 200h
0x180005e19  jnb     loc_180005EC6
0x180005e1f  mov     rcx, rdi; SRWLock
0x180005e22  call    cs:__imp_AcquireSRWLockExclusive
0x180005e28  cmp     ebx, 7
0x180005e2b  ja      short loc_180005E37
0x180005e2d  mov     eax, 0CCh
0x180005e32  bt      eax, ebx
0x180005e35  jb      short loc_180005E57
0x180005e37  lea     eax, [rbx-100h]
0x180005e3d  cmp     eax, 7Fh
0x180005e40  jbe     short loc_180005E57
0x180005e42  mov     r9d, r15d
0x180005e45  lea     rcx, [rdi+48h]
0x180005e49  mov     r8d, r14d
0x180005e4c  mov     edx, ebx
0x180005e4e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005e53  mov     bl, al
0x180005e55  jmp     short loc_180005E68
0x180005e57  mov     r8d, r14d
0x180005e5a  mov     edx, ebx
0x180005e5c  lea     rcx, [rdi+8]
0x180005e60  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005e65  mov     bl, [rdi+40h]
0x180005e68  test    rdi, rdi
0x180005e6b  jz      short loc_180005E76
0x180005e6d  mov     rcx, rdi; SRWLock
0x180005e70  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e76  test    bl, bl
0x180005e78  jz      short loc_180005EC6
0x180005e7a  jmp     short loc_180005E84
0x180005e7c  mov     rcx, rdi; SRWLock
0x180005e7f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005e84  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005e8b  jnz     short loc_180005EC6
0x180005e8d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005e94  test    rax, rax
0x180005e97  jz      short loc_180005EA2
0x180005e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e9e  test    al, al
0x180005ea0  jnz     short loc_180005EC6
0x180005ea2  lea     rbx, [rsi+20h]
0x180005ea6  mov     rcx, rbx; SRWLock
0x180005ea9  call    cs:__imp_AcquireSRWLockExclusive
0x180005eaf  mov     rcx, rsi; pv
0x180005eb2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180005eb7  test    rbx, rbx
0x180005eba  jz      short loc_180005EC6
0x180005ebc  mov     rcx, rbx; SRWLock
0x180005ebf  call    cs:__imp_ReleaseSRWLockExclusive
0x180005ec5  nop
0x180005ec6  add     rsp, 28h
0x180005eca  pop     r15
0x180005ecc  pop     r14
0x180005ece  pop     rdi
0x180005ecf  pop     rsi
0x180005ed0  pop     rbp
0x180005ed1  pop     rbx
0x180005ed2  retn
```
