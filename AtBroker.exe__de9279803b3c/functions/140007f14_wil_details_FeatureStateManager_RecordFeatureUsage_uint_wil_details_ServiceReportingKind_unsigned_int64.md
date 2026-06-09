# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007f14`
- end: `0x140008022`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000a210`

## callees

- `0x140004c64`
- `0x140004ddc`
- `0x140007f14`
- `0x140008094`
- `0x1400080c8`
- `0x140008100`
- `0x140017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007fc0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000800f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007fc0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000800f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007f72`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007ff9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007f72`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007ff9`

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
0x140007f14  push    rbx
0x140007f16  push    rbp
0x140007f17  push    rsi
0x140007f18  push    rdi
0x140007f19  push    r14
0x140007f1b  push    r15
0x140007f1d  sub     rsp, 28h
0x140007f21  cmp     byte ptr [rcx], 0
0x140007f24  mov     r15, r9
0x140007f27  mov     ebx, r8d
0x140007f2a  mov     r14d, edx
0x140007f2d  mov     rsi, rcx
0x140007f30  jz      loc_140008015
0x140007f36  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140007f3b  test    al, al
0x140007f3d  jz      loc_140008015
0x140007f43  mov     rdi, [rsi+18h]
0x140007f47  cmp     ebx, 0FEh
0x140007f4d  jz      short loc_140007FCC
0x140007f4f  cmp     ebx, 0C8h
0x140007f55  jb      short loc_140007F6F
0x140007f57  cmp     ebx, 100h
0x140007f5d  jl      loc_140008015
0x140007f63  cmp     ebx, 200h
0x140007f69  jnb     loc_140008015
0x140007f6f  mov     rcx, rdi; SRWLock
0x140007f72  call    cs:__imp_AcquireSRWLockExclusive
0x140007f78  cmp     ebx, 7
0x140007f7b  ja      short loc_140007F87
0x140007f7d  mov     eax, 0CCh
0x140007f82  bt      eax, ebx
0x140007f85  jb      short loc_140007FA7
0x140007f87  lea     eax, [rbx-100h]
0x140007f8d  cmp     eax, 7Fh
0x140007f90  jbe     short loc_140007FA7
0x140007f92  mov     r9d, r15d
0x140007f95  lea     rcx, [rdi+48h]
0x140007f99  mov     r8d, r14d
0x140007f9c  mov     edx, ebx
0x140007f9e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140007fa3  mov     bl, al
0x140007fa5  jmp     short loc_140007FB8
0x140007fa7  mov     r8d, r14d
0x140007faa  lea     rcx, [rdi+8]
0x140007fae  mov     edx, ebx
0x140007fb0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140007fb5  mov     bl, [rdi+40h]
0x140007fb8  test    rdi, rdi
0x140007fbb  jz      short loc_140007FC6
0x140007fbd  mov     rcx, rdi; SRWLock
0x140007fc0  call    cs:__imp_ReleaseSRWLockExclusive
0x140007fc6  test    bl, bl
0x140007fc8  jz      short loc_140008015
0x140007fca  jmp     short loc_140007FD4
0x140007fcc  mov     rcx, rdi; SRWLock
0x140007fcf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140007fd4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007fdb  jnz     short loc_140008015
0x140007fdd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007fe4  test    rax, rax
0x140007fe7  jz      short loc_140007FF2
0x140007fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fee  test    al, al
0x140007ff0  jnz     short loc_140008015
0x140007ff2  lea     rbx, [rsi+20h]
0x140007ff6  mov     rcx, rbx; SRWLock
0x140007ff9  call    cs:__imp_AcquireSRWLockExclusive
0x140007fff  mov     rcx, rsi; pv
0x140008002  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140008007  test    rbx, rbx
0x14000800a  jz      short loc_140008015
0x14000800c  mov     rcx, rbx; SRWLock
0x14000800f  call    cs:__imp_ReleaseSRWLockExclusive
0x140008015  add     rsp, 28h
0x140008019  pop     r15
0x14000801b  pop     r14
0x14000801d  pop     rdi
0x14000801e  pop     rsi
0x14000801f  pop     rbp
0x140008020  pop     rbx
0x140008021  retn
```
