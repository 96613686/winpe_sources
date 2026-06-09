# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005c64`
- end: `0x180005d72`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007640`

## callees

- `0x180004134`
- `0x1800041e8`
- `0x180005c64`
- `0x180005db0`
- `0x180005de4`
- `0x180005e1c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005cc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005cc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d5f`

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
0x180005c64  push    rbx
0x180005c66  push    rbp
0x180005c67  push    rsi
0x180005c68  push    rdi
0x180005c69  push    r14
0x180005c6b  push    r15
0x180005c6d  sub     rsp, 28h
0x180005c71  cmp     byte ptr [rcx], 0
0x180005c74  mov     r15, r9
0x180005c77  mov     ebx, r8d
0x180005c7a  mov     r14d, edx
0x180005c7d  mov     rsi, rcx
0x180005c80  jz      loc_180005D65
0x180005c86  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005c8b  test    al, al
0x180005c8d  jz      loc_180005D65
0x180005c93  mov     rdi, [rsi+18h]
0x180005c97  cmp     ebx, 0FEh
0x180005c9d  jz      short loc_180005D1C
0x180005c9f  cmp     ebx, 0C8h
0x180005ca5  jb      short loc_180005CBF
0x180005ca7  cmp     ebx, 100h
0x180005cad  jl      loc_180005D65
0x180005cb3  cmp     ebx, 200h
0x180005cb9  jnb     loc_180005D65
0x180005cbf  mov     rcx, rdi; SRWLock
0x180005cc2  call    cs:__imp_AcquireSRWLockExclusive
0x180005cc8  cmp     ebx, 7
0x180005ccb  ja      short loc_180005CD7
0x180005ccd  mov     eax, 0CCh
0x180005cd2  bt      eax, ebx
0x180005cd5  jb      short loc_180005CF7
0x180005cd7  lea     eax, [rbx-100h]
0x180005cdd  cmp     eax, 7Fh
0x180005ce0  jbe     short loc_180005CF7
0x180005ce2  mov     r9d, r15d
0x180005ce5  lea     rcx, [rdi+48h]
0x180005ce9  mov     r8d, r14d
0x180005cec  mov     edx, ebx
0x180005cee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005cf3  mov     bl, al
0x180005cf5  jmp     short loc_180005D08
0x180005cf7  mov     r8d, r14d
0x180005cfa  lea     rcx, [rdi+8]
0x180005cfe  mov     edx, ebx
0x180005d00  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005d05  mov     bl, [rdi+40h]
0x180005d08  test    rdi, rdi
0x180005d0b  jz      short loc_180005D16
0x180005d0d  mov     rcx, rdi; SRWLock
0x180005d10  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d16  test    bl, bl
0x180005d18  jz      short loc_180005D65
0x180005d1a  jmp     short loc_180005D24
0x180005d1c  mov     rcx, rdi; SRWLock
0x180005d1f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005d24  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005d2b  jnz     short loc_180005D65
0x180005d2d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005d34  test    rax, rax
0x180005d37  jz      short loc_180005D42
0x180005d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3e  test    al, al
0x180005d40  jnz     short loc_180005D65
0x180005d42  lea     rbx, [rsi+20h]
0x180005d46  mov     rcx, rbx; SRWLock
0x180005d49  call    cs:__imp_AcquireSRWLockExclusive
0x180005d4f  mov     rcx, rsi; pv
0x180005d52  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180005d57  test    rbx, rbx
0x180005d5a  jz      short loc_180005D65
0x180005d5c  mov     rcx, rbx; SRWLock
0x180005d5f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d65  add     rsp, 28h
0x180005d69  pop     r15
0x180005d6b  pop     r14
0x180005d6d  pop     rdi
0x180005d6e  pop     rsi
0x180005d6f  pop     rbp
0x180005d70  pop     rbx
0x180005d71  retn
```
