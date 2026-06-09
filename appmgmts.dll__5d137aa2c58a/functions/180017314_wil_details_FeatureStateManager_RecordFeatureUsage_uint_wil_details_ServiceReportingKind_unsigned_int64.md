# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180017314`
- end: `0x180017423`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800191d0`

## callees

- `0x1800157d4`
- `0x180015888`
- `0x180017314`
- `0x180017464`
- `0x180017498`
- `0x1800174d0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800173c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001740f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800173c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001740f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017372`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800173f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017372`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800173f9`

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
0x180017314  push    rbx
0x180017316  push    rbp
0x180017317  push    rsi
0x180017318  push    rdi
0x180017319  push    r14
0x18001731b  push    r15
0x18001731d  sub     rsp, 28h
0x180017321  mov     r15, r9
0x180017324  mov     ebx, r8d
0x180017327  mov     r14d, edx
0x18001732a  mov     rsi, rcx
0x18001732d  cmp     byte ptr [rcx], 0
0x180017330  jz      loc_180017416
0x180017336  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001733b  test    al, al
0x18001733d  jz      loc_180017416
0x180017343  mov     rdi, [rsi+18h]
0x180017347  cmp     ebx, 0FEh
0x18001734d  jz      short loc_1800173CC
0x18001734f  cmp     ebx, 0C8h
0x180017355  jb      short loc_18001736F
0x180017357  cmp     ebx, 100h
0x18001735d  jl      loc_180017416
0x180017363  cmp     ebx, 200h
0x180017369  jnb     loc_180017416
0x18001736f  mov     rcx, rdi; SRWLock
0x180017372  call    cs:__imp_AcquireSRWLockExclusive
0x180017378  cmp     ebx, 7
0x18001737b  ja      short loc_180017387
0x18001737d  mov     eax, 0CCh
0x180017382  bt      eax, ebx
0x180017385  jb      short loc_1800173A7
0x180017387  lea     eax, [rbx-100h]
0x18001738d  cmp     eax, 7Fh
0x180017390  jbe     short loc_1800173A7
0x180017392  mov     r9d, r15d
0x180017395  lea     rcx, [rdi+48h]
0x180017399  mov     r8d, r14d
0x18001739c  mov     edx, ebx
0x18001739e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800173a3  mov     bl, al
0x1800173a5  jmp     short loc_1800173B8
0x1800173a7  mov     r8d, r14d
0x1800173aa  mov     edx, ebx
0x1800173ac  lea     rcx, [rdi+8]
0x1800173b0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800173b5  mov     bl, [rdi+40h]
0x1800173b8  test    rdi, rdi
0x1800173bb  jz      short loc_1800173C6
0x1800173bd  mov     rcx, rdi; SRWLock
0x1800173c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800173c6  test    bl, bl
0x1800173c8  jz      short loc_180017416
0x1800173ca  jmp     short loc_1800173D4
0x1800173cc  mov     rcx, rdi; SRWLock
0x1800173cf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800173d4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800173db  jnz     short loc_180017416
0x1800173dd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800173e4  test    rax, rax
0x1800173e7  jz      short loc_1800173F2
0x1800173e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173ee  test    al, al
0x1800173f0  jnz     short loc_180017416
0x1800173f2  lea     rbx, [rsi+20h]
0x1800173f6  mov     rcx, rbx; SRWLock
0x1800173f9  call    cs:__imp_AcquireSRWLockExclusive
0x1800173ff  mov     rcx, rsi; pv
0x180017402  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180017407  test    rbx, rbx
0x18001740a  jz      short loc_180017416
0x18001740c  mov     rcx, rbx; SRWLock
0x18001740f  call    cs:__imp_ReleaseSRWLockExclusive
0x180017415  nop
0x180017416  add     rsp, 28h
0x18001741a  pop     r15
0x18001741c  pop     r14
0x18001741e  pop     rdi
0x18001741f  pop     rsi
0x180017420  pop     rbp
0x180017421  pop     rbx
0x180017422  retn
```
