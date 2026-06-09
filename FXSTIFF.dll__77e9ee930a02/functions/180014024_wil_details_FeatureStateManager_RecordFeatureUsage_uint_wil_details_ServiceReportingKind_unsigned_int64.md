# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180014024`
- end: `0x180014150`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800161a0`

## callees

- `0x180012020`
- `0x1800121cc`
- `0x180014024`
- `0x180014198`
- `0x1800141d0`
- `0x180014208`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800140da`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180014135`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800140da`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180014135`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014086`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014119`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014086`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014119`

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
0x180014024  push    rbx
0x180014026  push    rbp
0x180014027  push    rsi
0x180014028  push    rdi
0x180014029  push    r14
0x18001402b  push    r15
0x18001402d  sub     rsp, 28h
0x180014031  mov     r15, r9
0x180014034  mov     ebx, r8d
0x180014037  mov     r14d, edx
0x18001403a  mov     rsi, rcx
0x18001403d  cmp     byte ptr [rcx], 0
0x180014040  jz      loc_180014142
0x180014046  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001404b  test    al, al
0x18001404d  jz      loc_180014142
0x180014053  mov     rdi, [rsi+18h]
0x180014057  cmp     ebx, 0FEh
0x18001405d  jz      loc_1800140EC
0x180014063  cmp     ebx, 0C8h
0x180014069  jb      short loc_180014083
0x18001406b  cmp     ebx, 100h
0x180014071  jl      loc_180014142
0x180014077  cmp     ebx, 200h
0x18001407d  jnb     loc_180014142
0x180014083  mov     rcx, rdi; SRWLock
0x180014086  call    cs:__imp_AcquireSRWLockExclusive
0x18001408d  nop     dword ptr [rax+rax+00h]
0x180014092  cmp     ebx, 7
0x180014095  ja      short loc_1800140A1
0x180014097  mov     eax, 0CCh
0x18001409c  bt      eax, ebx
0x18001409f  jb      short loc_1800140C1
0x1800140a1  lea     eax, [rbx-100h]
0x1800140a7  cmp     eax, 7Fh
0x1800140aa  jbe     short loc_1800140C1
0x1800140ac  mov     r9d, r15d
0x1800140af  lea     rcx, [rdi+48h]
0x1800140b3  mov     r8d, r14d
0x1800140b6  mov     edx, ebx
0x1800140b8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800140bd  mov     bl, al
0x1800140bf  jmp     short loc_1800140D2
0x1800140c1  mov     r8d, r14d
0x1800140c4  mov     edx, ebx
0x1800140c6  lea     rcx, [rdi+8]
0x1800140ca  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800140cf  mov     bl, [rdi+40h]
0x1800140d2  test    rdi, rdi
0x1800140d5  jz      short loc_1800140E6
0x1800140d7  mov     rcx, rdi; SRWLock
0x1800140da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800140e1  nop     dword ptr [rax+rax+00h]
0x1800140e6  test    bl, bl
0x1800140e8  jz      short loc_180014142
0x1800140ea  jmp     short loc_1800140F4
0x1800140ec  mov     rcx, rdi; SRWLock
0x1800140ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800140f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800140fb  jnz     short loc_180014142
0x1800140fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014104  test    rax, rax
0x180014107  jz      short loc_180014112
0x180014109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001410e  test    al, al
0x180014110  jnz     short loc_180014142
0x180014112  lea     rbx, [rsi+20h]
0x180014116  mov     rcx, rbx; SRWLock
0x180014119  call    cs:__imp_AcquireSRWLockExclusive
0x180014120  nop     dword ptr [rax+rax+00h]
0x180014125  mov     rcx, rsi; pv
0x180014128  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18001412d  test    rbx, rbx
0x180014130  jz      short loc_180014142
0x180014132  mov     rcx, rbx; SRWLock
0x180014135  call    cs:__imp_ReleaseSRWLockExclusive
0x18001413c  nop     dword ptr [rax+rax+00h]
0x180014141  nop
0x180014142  add     rsp, 28h
0x180014146  pop     r15
0x180014148  pop     r14
0x18001414a  pop     rdi
0x18001414b  pop     rsi
0x18001414c  pop     rbp
0x18001414d  pop     rbx
0x18001414e  retn
```
