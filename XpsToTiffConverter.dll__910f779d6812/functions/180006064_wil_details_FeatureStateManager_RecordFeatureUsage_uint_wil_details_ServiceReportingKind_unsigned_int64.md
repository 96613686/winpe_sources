# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006064`
- end: `0x180006173`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008230`

## callees

- `0x1800044f4`
- `0x1800045a8`
- `0x180006064`
- `0x1800061b4`
- `0x1800061e8`
- `0x180006220`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006149`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006149`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000615f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006110`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000615f`

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
0x180006064  push    rbx
0x180006066  push    rbp
0x180006067  push    rsi
0x180006068  push    rdi
0x180006069  push    r14
0x18000606b  push    r15
0x18000606d  sub     rsp, 28h
0x180006071  mov     r15, r9
0x180006074  mov     ebx, r8d
0x180006077  mov     r14d, edx
0x18000607a  mov     rsi, rcx
0x18000607d  cmp     byte ptr [rcx], 0
0x180006080  jz      loc_180006166
0x180006086  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000608b  test    al, al
0x18000608d  jz      loc_180006166
0x180006093  mov     rdi, [rsi+18h]
0x180006097  cmp     ebx, 0FEh
0x18000609d  jz      short loc_18000611C
0x18000609f  cmp     ebx, 0C8h
0x1800060a5  jb      short loc_1800060BF
0x1800060a7  cmp     ebx, 100h
0x1800060ad  jl      loc_180006166
0x1800060b3  cmp     ebx, 200h
0x1800060b9  jnb     loc_180006166
0x1800060bf  mov     rcx, rdi; SRWLock
0x1800060c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800060c8  cmp     ebx, 7
0x1800060cb  ja      short loc_1800060D7
0x1800060cd  mov     eax, 0CCh
0x1800060d2  bt      eax, ebx
0x1800060d5  jb      short loc_1800060F7
0x1800060d7  lea     eax, [rbx-100h]
0x1800060dd  cmp     eax, 7Fh
0x1800060e0  jbe     short loc_1800060F7
0x1800060e2  mov     r9d, r15d
0x1800060e5  lea     rcx, [rdi+48h]
0x1800060e9  mov     r8d, r14d
0x1800060ec  mov     edx, ebx
0x1800060ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800060f3  mov     bl, al
0x1800060f5  jmp     short loc_180006108
0x1800060f7  mov     r8d, r14d
0x1800060fa  mov     edx, ebx
0x1800060fc  lea     rcx, [rdi+8]
0x180006100  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006105  mov     bl, [rdi+40h]
0x180006108  test    rdi, rdi
0x18000610b  jz      short loc_180006116
0x18000610d  mov     rcx, rdi; SRWLock
0x180006110  call    cs:__imp_ReleaseSRWLockExclusive
0x180006116  test    bl, bl
0x180006118  jz      short loc_180006166
0x18000611a  jmp     short loc_180006124
0x18000611c  mov     rcx, rdi; SRWLock
0x18000611f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006124  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000612b  jnz     short loc_180006166
0x18000612d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006134  test    rax, rax
0x180006137  jz      short loc_180006142
0x180006139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613e  test    al, al
0x180006140  jnz     short loc_180006166
0x180006142  lea     rbx, [rsi+20h]
0x180006146  mov     rcx, rbx; SRWLock
0x180006149  call    cs:__imp_AcquireSRWLockExclusive
0x18000614f  mov     rcx, rsi; pv
0x180006152  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006157  test    rbx, rbx
0x18000615a  jz      short loc_180006166
0x18000615c  mov     rcx, rbx; SRWLock
0x18000615f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006165  nop
0x180006166  add     rsp, 28h
0x18000616a  pop     r15
0x18000616c  pop     r14
0x18000616e  pop     rdi
0x18000616f  pop     rsi
0x180006170  pop     rbp
0x180006171  pop     rbx
0x180006172  retn
```
