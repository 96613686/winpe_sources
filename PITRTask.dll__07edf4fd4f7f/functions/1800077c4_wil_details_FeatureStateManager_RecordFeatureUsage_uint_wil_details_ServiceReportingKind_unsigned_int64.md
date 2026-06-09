# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800077c4`
- end: `0x1800078da`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `278`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009f30`

## callees

- `0x180004eb0`
- `0x180005120`
- `0x1800077c4`
- `0x180007954`
- `0x1800079a8`
- `0x180007a00`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007873`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007873`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007825`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800078ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007825`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800078ac`

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
0x1800077c4  mov     [rsp+arg_18], rbx
0x1800077c9  push    rbp
0x1800077ca  push    rsi
0x1800077cb  push    rdi
0x1800077cc  push    r14
0x1800077ce  push    r15
0x1800077d0  sub     rsp, 20h
0x1800077d4  mov     r15, r9
0x1800077d7  mov     ebx, r8d
0x1800077da  mov     r14d, edx
0x1800077dd  mov     rsi, rcx
0x1800077e0  cmp     byte ptr [rcx], 0
0x1800077e3  jz      loc_1800078C9
0x1800077e9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800077ee  test    al, al
0x1800077f0  jz      loc_1800078C9
0x1800077f6  mov     rdi, [rsi+18h]
0x1800077fa  cmp     ebx, 0FEh
0x180007800  jz      short loc_18000787F
0x180007802  cmp     ebx, 0C8h
0x180007808  jb      short loc_180007822
0x18000780a  cmp     ebx, 100h
0x180007810  jl      loc_1800078C9
0x180007816  cmp     ebx, 200h
0x18000781c  jnb     loc_1800078C9
0x180007822  mov     rcx, rdi; SRWLock
0x180007825  call    cs:__imp_AcquireSRWLockExclusive
0x18000782b  cmp     ebx, 7
0x18000782e  ja      short loc_18000783A
0x180007830  mov     eax, 0CCh
0x180007835  bt      eax, ebx
0x180007838  jb      short loc_18000785A
0x18000783a  lea     eax, [rbx-100h]
0x180007840  cmp     eax, 7Fh
0x180007843  jbe     short loc_18000785A
0x180007845  mov     r9d, r15d
0x180007848  lea     rcx, [rdi+48h]
0x18000784c  mov     r8d, r14d
0x18000784f  mov     edx, ebx
0x180007851  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007856  mov     bl, al
0x180007858  jmp     short loc_18000786B
0x18000785a  mov     r8d, r14d
0x18000785d  mov     edx, ebx
0x18000785f  lea     rcx, [rdi+8]
0x180007863  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007868  mov     bl, [rdi+40h]
0x18000786b  test    rdi, rdi
0x18000786e  jz      short loc_180007879
0x180007870  mov     rcx, rdi; SRWLock
0x180007873  call    cs:__imp_ReleaseSRWLockExclusive
0x180007879  test    bl, bl
0x18000787b  jz      short loc_1800078C9
0x18000787d  jmp     short loc_180007887
0x18000787f  mov     rcx, rdi; SRWLock
0x180007882  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007887  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000788e  jnz     short loc_1800078C9
0x180007890  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007897  test    rax, rax
0x18000789a  jz      short loc_1800078A5
0x18000789c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a1  test    al, al
0x1800078a3  jnz     short loc_1800078C9
0x1800078a5  lea     rbx, [rsi+20h]
0x1800078a9  mov     rcx, rbx; SRWLock
0x1800078ac  call    cs:__imp_AcquireSRWLockExclusive
0x1800078b2  mov     rcx, rsi; pv
0x1800078b5  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800078ba  test    rbx, rbx
0x1800078bd  jz      short loc_1800078C9
0x1800078bf  mov     rcx, rbx; SRWLock
0x1800078c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800078c8  nop
0x1800078c9  mov     rbx, [rsp+48h+arg_18]
0x1800078ce  add     rsp, 20h
0x1800078d2  pop     r15
0x1800078d4  pop     r14
0x1800078d6  pop     rdi
0x1800078d7  pop     rsi
0x1800078d8  pop     rbp
0x1800078d9  retn
```
