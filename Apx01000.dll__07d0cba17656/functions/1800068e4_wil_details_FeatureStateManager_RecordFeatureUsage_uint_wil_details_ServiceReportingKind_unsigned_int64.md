# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800068e4`
- end: `0x1800069f3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008a90`

## callees

- `0x180004994`
- `0x180004b0c`
- `0x1800068e4`
- `0x180006a74`
- `0x180006aa8`
- `0x180006ae0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800069df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800069df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800069c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800069c9`

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
0x1800068e4  push    rbx
0x1800068e6  push    rbp
0x1800068e7  push    rsi
0x1800068e8  push    rdi
0x1800068e9  push    r14
0x1800068eb  push    r15
0x1800068ed  sub     rsp, 28h
0x1800068f1  mov     r15, r9
0x1800068f4  mov     ebx, r8d
0x1800068f7  mov     r14d, edx
0x1800068fa  mov     rsi, rcx
0x1800068fd  cmp     byte ptr [rcx], 0
0x180006900  jz      loc_1800069E6
0x180006906  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000690b  test    al, al
0x18000690d  jz      loc_1800069E6
0x180006913  mov     rdi, [rsi+18h]
0x180006917  cmp     ebx, 0FEh
0x18000691d  jz      short loc_18000699C
0x18000691f  cmp     ebx, 0C8h
0x180006925  jb      short loc_18000693F
0x180006927  cmp     ebx, 100h
0x18000692d  jl      loc_1800069E6
0x180006933  cmp     ebx, 200h
0x180006939  jnb     loc_1800069E6
0x18000693f  mov     rcx, rdi; SRWLock
0x180006942  call    cs:__imp_AcquireSRWLockExclusive
0x180006948  cmp     ebx, 7
0x18000694b  ja      short loc_180006957
0x18000694d  mov     eax, 0CCh
0x180006952  bt      eax, ebx
0x180006955  jb      short loc_180006977
0x180006957  lea     eax, [rbx-100h]
0x18000695d  cmp     eax, 7Fh
0x180006960  jbe     short loc_180006977
0x180006962  mov     r9d, r15d
0x180006965  lea     rcx, [rdi+48h]
0x180006969  mov     r8d, r14d
0x18000696c  mov     edx, ebx
0x18000696e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006973  mov     bl, al
0x180006975  jmp     short loc_180006988
0x180006977  mov     r8d, r14d
0x18000697a  mov     edx, ebx
0x18000697c  lea     rcx, [rdi+8]
0x180006980  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006985  mov     bl, [rdi+40h]
0x180006988  test    rdi, rdi
0x18000698b  jz      short loc_180006996
0x18000698d  mov     rcx, rdi; SRWLock
0x180006990  call    cs:__imp_ReleaseSRWLockExclusive
0x180006996  test    bl, bl
0x180006998  jz      short loc_1800069E6
0x18000699a  jmp     short loc_1800069A4
0x18000699c  mov     rcx, rdi; SRWLock
0x18000699f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800069a4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800069ab  jnz     short loc_1800069E6
0x1800069ad  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800069b4  test    rax, rax
0x1800069b7  jz      short loc_1800069C2
0x1800069b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069be  test    al, al
0x1800069c0  jnz     short loc_1800069E6
0x1800069c2  lea     rbx, [rsi+20h]
0x1800069c6  mov     rcx, rbx; SRWLock
0x1800069c9  call    cs:__imp_AcquireSRWLockExclusive
0x1800069cf  mov     rcx, rsi; pv
0x1800069d2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800069d7  test    rbx, rbx
0x1800069da  jz      short loc_1800069E6
0x1800069dc  mov     rcx, rbx; SRWLock
0x1800069df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800069e5  nop
0x1800069e6  add     rsp, 28h
0x1800069ea  pop     r15
0x1800069ec  pop     r14
0x1800069ee  pop     rdi
0x1800069ef  pop     rsi
0x1800069f0  pop     rbp
0x1800069f1  pop     rbx
0x1800069f2  retn
```
