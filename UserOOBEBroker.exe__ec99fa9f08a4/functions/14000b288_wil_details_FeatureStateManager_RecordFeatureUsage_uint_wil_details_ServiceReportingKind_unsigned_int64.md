# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000b288`
- end: `0x14000b397`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000d080`

## callees

- `0x140008f64`
- `0x1400090dc`
- `0x14000b288`
- `0x14000b3d4`
- `0x14000b408`
- `0x14000b440`
- `0x14000f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b2e6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b36d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b2e6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b36d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b334`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b383`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b334`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b383`

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
0x14000b288  push    rbx
0x14000b28a  push    rbp
0x14000b28b  push    rsi
0x14000b28c  push    rdi
0x14000b28d  push    r14
0x14000b28f  push    r15
0x14000b291  sub     rsp, 28h
0x14000b295  mov     r15, r9
0x14000b298  mov     ebx, r8d
0x14000b29b  mov     r14d, edx
0x14000b29e  mov     rsi, rcx
0x14000b2a1  cmp     byte ptr [rcx], 0
0x14000b2a4  jz      loc_14000B38A
0x14000b2aa  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000b2af  test    al, al
0x14000b2b1  jz      loc_14000B38A
0x14000b2b7  mov     rdi, [rsi+18h]
0x14000b2bb  cmp     ebx, 0FEh
0x14000b2c1  jz      short loc_14000B340
0x14000b2c3  cmp     ebx, 0C8h
0x14000b2c9  jb      short loc_14000B2E3
0x14000b2cb  cmp     ebx, 100h
0x14000b2d1  jl      loc_14000B38A
0x14000b2d7  cmp     ebx, 200h
0x14000b2dd  jnb     loc_14000B38A
0x14000b2e3  mov     rcx, rdi; SRWLock
0x14000b2e6  call    cs:__imp_AcquireSRWLockExclusive
0x14000b2ec  cmp     ebx, 7
0x14000b2ef  ja      short loc_14000B2FB
0x14000b2f1  mov     eax, 0CCh
0x14000b2f6  bt      eax, ebx
0x14000b2f9  jb      short loc_14000B31B
0x14000b2fb  lea     eax, [rbx-100h]
0x14000b301  cmp     eax, 7Fh
0x14000b304  jbe     short loc_14000B31B
0x14000b306  mov     r9d, r15d
0x14000b309  lea     rcx, [rdi+48h]
0x14000b30d  mov     r8d, r14d
0x14000b310  mov     edx, ebx
0x14000b312  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b317  mov     bl, al
0x14000b319  jmp     short loc_14000B32C
0x14000b31b  mov     r8d, r14d
0x14000b31e  mov     edx, ebx
0x14000b320  lea     rcx, [rdi+8]
0x14000b324  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b329  mov     bl, [rdi+40h]
0x14000b32c  test    rdi, rdi
0x14000b32f  jz      short loc_14000B33A
0x14000b331  mov     rcx, rdi; SRWLock
0x14000b334  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b33a  test    bl, bl
0x14000b33c  jz      short loc_14000B38A
0x14000b33e  jmp     short loc_14000B348
0x14000b340  mov     rcx, rdi; SRWLock
0x14000b343  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b348  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000b34f  jnz     short loc_14000B38A
0x14000b351  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000b358  test    rax, rax
0x14000b35b  jz      short loc_14000B366
0x14000b35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b362  test    al, al
0x14000b364  jnz     short loc_14000B38A
0x14000b366  lea     rbx, [rsi+20h]
0x14000b36a  mov     rcx, rbx; SRWLock
0x14000b36d  call    cs:__imp_AcquireSRWLockExclusive
0x14000b373  mov     rcx, rsi; pv
0x14000b376  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000b37b  test    rbx, rbx
0x14000b37e  jz      short loc_14000B38A
0x14000b380  mov     rcx, rbx; SRWLock
0x14000b383  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b389  nop
0x14000b38a  add     rsp, 28h
0x14000b38e  pop     r15
0x14000b390  pop     r14
0x14000b392  pop     rdi
0x14000b393  pop     rsi
0x14000b394  pop     rbp
0x14000b395  pop     rbx
0x14000b396  retn
```
