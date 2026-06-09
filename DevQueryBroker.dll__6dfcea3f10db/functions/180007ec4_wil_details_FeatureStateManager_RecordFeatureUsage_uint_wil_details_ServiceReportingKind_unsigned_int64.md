# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007ec4`
- end: `0x180007fd2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800097c0`

## callees

- `0x1800063b4`
- `0x180006468`
- `0x180007ec4`
- `0x180008010`
- `0x180008044`
- `0x18000807c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f70`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007fa9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007fa9`

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
0x180007ec4  push    rbx
0x180007ec6  push    rbp
0x180007ec7  push    rsi
0x180007ec8  push    rdi
0x180007ec9  push    r14
0x180007ecb  push    r15
0x180007ecd  sub     rsp, 28h
0x180007ed1  cmp     byte ptr [rcx], 0
0x180007ed4  mov     r15, r9
0x180007ed7  mov     ebx, r8d
0x180007eda  mov     r14d, edx
0x180007edd  mov     rsi, rcx
0x180007ee0  jz      loc_180007FC5
0x180007ee6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007eeb  test    al, al
0x180007eed  jz      loc_180007FC5
0x180007ef3  mov     rdi, [rsi+18h]
0x180007ef7  cmp     ebx, 0FEh
0x180007efd  jz      short loc_180007F7C
0x180007eff  cmp     ebx, 0C8h
0x180007f05  jb      short loc_180007F1F
0x180007f07  cmp     ebx, 100h
0x180007f0d  jl      loc_180007FC5
0x180007f13  cmp     ebx, 200h
0x180007f19  jnb     loc_180007FC5
0x180007f1f  mov     rcx, rdi; SRWLock
0x180007f22  call    cs:__imp_AcquireSRWLockExclusive
0x180007f28  cmp     ebx, 7
0x180007f2b  ja      short loc_180007F37
0x180007f2d  mov     eax, 0CCh
0x180007f32  bt      eax, ebx
0x180007f35  jb      short loc_180007F57
0x180007f37  lea     eax, [rbx-100h]
0x180007f3d  cmp     eax, 7Fh
0x180007f40  jbe     short loc_180007F57
0x180007f42  mov     r9d, r15d
0x180007f45  lea     rcx, [rdi+48h]
0x180007f49  mov     r8d, r14d
0x180007f4c  mov     edx, ebx
0x180007f4e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007f53  mov     bl, al
0x180007f55  jmp     short loc_180007F68
0x180007f57  mov     r8d, r14d
0x180007f5a  lea     rcx, [rdi+8]
0x180007f5e  mov     edx, ebx
0x180007f60  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007f65  mov     bl, [rdi+40h]
0x180007f68  test    rdi, rdi
0x180007f6b  jz      short loc_180007F76
0x180007f6d  mov     rcx, rdi; SRWLock
0x180007f70  call    cs:__imp_ReleaseSRWLockExclusive
0x180007f76  test    bl, bl
0x180007f78  jz      short loc_180007FC5
0x180007f7a  jmp     short loc_180007F84
0x180007f7c  mov     rcx, rdi; SRWLock
0x180007f7f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007f84  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007f8b  jnz     short loc_180007FC5
0x180007f8d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007f94  test    rax, rax
0x180007f97  jz      short loc_180007FA2
0x180007f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9e  test    al, al
0x180007fa0  jnz     short loc_180007FC5
0x180007fa2  lea     rbx, [rsi+20h]
0x180007fa6  mov     rcx, rbx; SRWLock
0x180007fa9  call    cs:__imp_AcquireSRWLockExclusive
0x180007faf  mov     rcx, rsi; pv
0x180007fb2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007fb7  test    rbx, rbx
0x180007fba  jz      short loc_180007FC5
0x180007fbc  mov     rcx, rbx; SRWLock
0x180007fbf  call    cs:__imp_ReleaseSRWLockExclusive
0x180007fc5  add     rsp, 28h
0x180007fc9  pop     r15
0x180007fcb  pop     r14
0x180007fcd  pop     rdi
0x180007fce  pop     rsi
0x180007fcf  pop     rbp
0x180007fd0  pop     rbx
0x180007fd1  retn
```
