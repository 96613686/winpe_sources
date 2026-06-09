# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180026004`
- end: `0x180026112`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800278c0`

## callees

- `0x180024394`
- `0x180024448`
- `0x180026004`
- `0x180026150`
- `0x180026184`
- `0x1800261bc`
- `0x18005d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180026062`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800260e9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026062`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800260e9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800260b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800260ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800260b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800260ff`

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
0x180026004  push    rbx
0x180026006  push    rbp
0x180026007  push    rsi
0x180026008  push    rdi
0x180026009  push    r14
0x18002600b  push    r15
0x18002600d  sub     rsp, 28h
0x180026011  cmp     byte ptr [rcx], 0
0x180026014  mov     r15, r9
0x180026017  mov     ebx, r8d
0x18002601a  mov     r14d, edx
0x18002601d  mov     rsi, rcx
0x180026020  jz      loc_180026105
0x180026026  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002602b  test    al, al
0x18002602d  jz      loc_180026105
0x180026033  mov     rdi, [rsi+18h]
0x180026037  cmp     ebx, 0FEh
0x18002603d  jz      short loc_1800260BC
0x18002603f  cmp     ebx, 0C8h
0x180026045  jb      short loc_18002605F
0x180026047  cmp     ebx, 100h
0x18002604d  jl      loc_180026105
0x180026053  cmp     ebx, 200h
0x180026059  jnb     loc_180026105
0x18002605f  mov     rcx, rdi; SRWLock
0x180026062  call    cs:__imp_AcquireSRWLockExclusive
0x180026068  cmp     ebx, 7
0x18002606b  ja      short loc_180026077
0x18002606d  mov     eax, 0CCh
0x180026072  bt      eax, ebx
0x180026075  jb      short loc_180026097
0x180026077  lea     eax, [rbx-100h]
0x18002607d  cmp     eax, 7Fh
0x180026080  jbe     short loc_180026097
0x180026082  mov     r9d, r15d
0x180026085  lea     rcx, [rdi+48h]
0x180026089  mov     r8d, r14d
0x18002608c  mov     edx, ebx
0x18002608e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180026093  mov     bl, al
0x180026095  jmp     short loc_1800260A8
0x180026097  mov     r8d, r14d
0x18002609a  lea     rcx, [rdi+8]
0x18002609e  mov     edx, ebx
0x1800260a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800260a5  mov     bl, [rdi+40h]
0x1800260a8  test    rdi, rdi
0x1800260ab  jz      short loc_1800260B6
0x1800260ad  mov     rcx, rdi; SRWLock
0x1800260b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800260b6  test    bl, bl
0x1800260b8  jz      short loc_180026105
0x1800260ba  jmp     short loc_1800260C4
0x1800260bc  mov     rcx, rdi; SRWLock
0x1800260bf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800260c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800260cb  jnz     short loc_180026105
0x1800260cd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800260d4  test    rax, rax
0x1800260d7  jz      short loc_1800260E2
0x1800260d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260de  test    al, al
0x1800260e0  jnz     short loc_180026105
0x1800260e2  lea     rbx, [rsi+20h]
0x1800260e6  mov     rcx, rbx; SRWLock
0x1800260e9  call    cs:__imp_AcquireSRWLockExclusive
0x1800260ef  mov     rcx, rsi; pv
0x1800260f2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800260f7  test    rbx, rbx
0x1800260fa  jz      short loc_180026105
0x1800260fc  mov     rcx, rbx; SRWLock
0x1800260ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180026105  add     rsp, 28h
0x180026109  pop     r15
0x18002610b  pop     r14
0x18002610d  pop     rdi
0x18002610e  pop     rsi
0x18002610f  pop     rbp
0x180026110  pop     rbx
0x180026111  retn
```
