# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180013804`
- end: `0x180013913`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180015630`

## callees

- `0x1800119d4`
- `0x180011b54`
- `0x180013804`
- `0x180013954`
- `0x180013988`
- `0x1800139c0`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800138b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800138ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800138b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800138ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013862`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800138e9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013862`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800138e9`

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
      wil::details::FeatureStateManager::EnsureTimerUnderLock((_QWORD *)a1);
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
0x180013804  push    rbx
0x180013806  push    rbp
0x180013807  push    rsi
0x180013808  push    rdi
0x180013809  push    r14
0x18001380b  push    r15
0x18001380d  sub     rsp, 28h
0x180013811  mov     r15, r9
0x180013814  mov     ebx, r8d
0x180013817  mov     r14d, edx
0x18001381a  mov     rsi, rcx
0x18001381d  cmp     byte ptr [rcx], 0
0x180013820  jz      loc_180013906
0x180013826  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001382b  test    al, al
0x18001382d  jz      loc_180013906
0x180013833  mov     rdi, [rsi+18h]
0x180013837  cmp     ebx, 0FEh
0x18001383d  jz      short loc_1800138BC
0x18001383f  cmp     ebx, 0C8h
0x180013845  jb      short loc_18001385F
0x180013847  cmp     ebx, 100h
0x18001384d  jl      loc_180013906
0x180013853  cmp     ebx, 200h
0x180013859  jnb     loc_180013906
0x18001385f  mov     rcx, rdi; SRWLock
0x180013862  call    cs:__imp_AcquireSRWLockExclusive
0x180013868  cmp     ebx, 7
0x18001386b  ja      short loc_180013877
0x18001386d  mov     eax, 0CCh
0x180013872  bt      eax, ebx
0x180013875  jb      short loc_180013897
0x180013877  lea     eax, [rbx-100h]
0x18001387d  cmp     eax, 7Fh
0x180013880  jbe     short loc_180013897
0x180013882  mov     r9d, r15d
0x180013885  lea     rcx, [rdi+48h]
0x180013889  mov     r8d, r14d
0x18001388c  mov     edx, ebx
0x18001388e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180013893  mov     bl, al
0x180013895  jmp     short loc_1800138A8
0x180013897  mov     r8d, r14d
0x18001389a  mov     edx, ebx
0x18001389c  lea     rcx, [rdi+8]
0x1800138a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800138a5  mov     bl, [rdi+40h]
0x1800138a8  test    rdi, rdi
0x1800138ab  jz      short loc_1800138B6
0x1800138ad  mov     rcx, rdi; SRWLock
0x1800138b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800138b6  test    bl, bl
0x1800138b8  jz      short loc_180013906
0x1800138ba  jmp     short loc_1800138C4
0x1800138bc  mov     rcx, rdi; SRWLock
0x1800138bf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800138c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800138cb  jnz     short loc_180013906
0x1800138cd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800138d4  test    rax, rax
0x1800138d7  jz      short loc_1800138E2
0x1800138d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138de  test    al, al
0x1800138e0  jnz     short loc_180013906
0x1800138e2  lea     rbx, [rsi+20h]
0x1800138e6  mov     rcx, rbx; SRWLock
0x1800138e9  call    cs:__imp_AcquireSRWLockExclusive
0x1800138ef  mov     rcx, rsi; pv
0x1800138f2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800138f7  test    rbx, rbx
0x1800138fa  jz      short loc_180013906
0x1800138fc  mov     rcx, rbx; SRWLock
0x1800138ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180013905  nop
0x180013906  add     rsp, 28h
0x18001390a  pop     r15
0x18001390c  pop     r14
0x18001390e  pop     rdi
0x18001390f  pop     rsi
0x180013910  pop     rbp
0x180013911  pop     rbx
0x180013912  retn
```
