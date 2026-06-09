# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000cdd4`
- end: `0x18000cee3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180010e60`

## callees

- `0x1800077c8`
- `0x180007940`
- `0x18000cdd4`
- `0x18000cf64`
- `0x18000cf98`
- `0x18000cfd0`
- `0x180015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ce32`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ceb9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ce32`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ceb9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ce80`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cecf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ce80`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cecf`

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
0x18000cdd4  push    rbx
0x18000cdd6  push    rbp
0x18000cdd7  push    rsi
0x18000cdd8  push    rdi
0x18000cdd9  push    r14
0x18000cddb  push    r15
0x18000cddd  sub     rsp, 28h
0x18000cde1  mov     r15, r9
0x18000cde4  mov     ebx, r8d
0x18000cde7  mov     r14d, edx
0x18000cdea  mov     rsi, rcx
0x18000cded  cmp     byte ptr [rcx], 0
0x18000cdf0  jz      loc_18000CED6
0x18000cdf6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000cdfb  test    al, al
0x18000cdfd  jz      loc_18000CED6
0x18000ce03  mov     rdi, [rsi+18h]
0x18000ce07  cmp     ebx, 0FEh
0x18000ce0d  jz      short loc_18000CE8C
0x18000ce0f  cmp     ebx, 0C8h
0x18000ce15  jb      short loc_18000CE2F
0x18000ce17  cmp     ebx, 100h
0x18000ce1d  jl      loc_18000CED6
0x18000ce23  cmp     ebx, 200h
0x18000ce29  jnb     loc_18000CED6
0x18000ce2f  mov     rcx, rdi; SRWLock
0x18000ce32  call    cs:__imp_AcquireSRWLockExclusive
0x18000ce38  cmp     ebx, 7
0x18000ce3b  ja      short loc_18000CE47
0x18000ce3d  mov     eax, 0CCh
0x18000ce42  bt      eax, ebx
0x18000ce45  jb      short loc_18000CE67
0x18000ce47  lea     eax, [rbx-100h]
0x18000ce4d  cmp     eax, 7Fh
0x18000ce50  jbe     short loc_18000CE67
0x18000ce52  mov     r9d, r15d
0x18000ce55  lea     rcx, [rdi+48h]
0x18000ce59  mov     r8d, r14d
0x18000ce5c  mov     edx, ebx
0x18000ce5e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ce63  mov     bl, al
0x18000ce65  jmp     short loc_18000CE78
0x18000ce67  mov     r8d, r14d
0x18000ce6a  mov     edx, ebx
0x18000ce6c  lea     rcx, [rdi+8]
0x18000ce70  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ce75  mov     bl, [rdi+40h]
0x18000ce78  test    rdi, rdi
0x18000ce7b  jz      short loc_18000CE86
0x18000ce7d  mov     rcx, rdi; SRWLock
0x18000ce80  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ce86  test    bl, bl
0x18000ce88  jz      short loc_18000CED6
0x18000ce8a  jmp     short loc_18000CE94
0x18000ce8c  mov     rcx, rdi; SRWLock
0x18000ce8f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ce94  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ce9b  jnz     short loc_18000CED6
0x18000ce9d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000cea4  test    rax, rax
0x18000cea7  jz      short loc_18000CEB2
0x18000cea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceae  test    al, al
0x18000ceb0  jnz     short loc_18000CED6
0x18000ceb2  lea     rbx, [rsi+20h]
0x18000ceb6  mov     rcx, rbx; SRWLock
0x18000ceb9  call    cs:__imp_AcquireSRWLockExclusive
0x18000cebf  mov     rcx, rsi; pv
0x18000cec2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000cec7  test    rbx, rbx
0x18000ceca  jz      short loc_18000CED6
0x18000cecc  mov     rcx, rbx; SRWLock
0x18000cecf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ced5  nop
0x18000ced6  add     rsp, 28h
0x18000ceda  pop     r15
0x18000cedc  pop     r14
0x18000cede  pop     rdi
0x18000cedf  pop     rsi
0x18000cee0  pop     rbp
0x18000cee1  pop     rbx
0x18000cee2  retn
```
