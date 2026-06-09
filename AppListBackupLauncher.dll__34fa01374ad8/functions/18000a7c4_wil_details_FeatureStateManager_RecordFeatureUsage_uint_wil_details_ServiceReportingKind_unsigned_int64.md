# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a7c4`
- end: `0x18000a8d3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000dae0`

## callees

- `0x1800077a0`
- `0x180007918`
- `0x18000a7c4`
- `0x18000a954`
- `0x18000a988`
- `0x18000a9c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a822`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a8a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a822`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a8a9`

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
0x18000a7c4  push    rbx
0x18000a7c6  push    rbp
0x18000a7c7  push    rsi
0x18000a7c8  push    rdi
0x18000a7c9  push    r14
0x18000a7cb  push    r15
0x18000a7cd  sub     rsp, 28h
0x18000a7d1  mov     r15, r9
0x18000a7d4  mov     ebx, r8d
0x18000a7d7  mov     r14d, edx
0x18000a7da  mov     rsi, rcx
0x18000a7dd  cmp     byte ptr [rcx], 0
0x18000a7e0  jz      loc_18000A8C6
0x18000a7e6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a7eb  test    al, al
0x18000a7ed  jz      loc_18000A8C6
0x18000a7f3  mov     rdi, [rsi+18h]
0x18000a7f7  cmp     ebx, 0FEh
0x18000a7fd  jz      short loc_18000A87C
0x18000a7ff  cmp     ebx, 0C8h
0x18000a805  jb      short loc_18000A81F
0x18000a807  cmp     ebx, 100h
0x18000a80d  jl      loc_18000A8C6
0x18000a813  cmp     ebx, 200h
0x18000a819  jnb     loc_18000A8C6
0x18000a81f  mov     rcx, rdi; SRWLock
0x18000a822  call    cs:__imp_AcquireSRWLockExclusive
0x18000a828  cmp     ebx, 7
0x18000a82b  ja      short loc_18000A837
0x18000a82d  mov     eax, 0CCh
0x18000a832  bt      eax, ebx
0x18000a835  jb      short loc_18000A857
0x18000a837  lea     eax, [rbx-100h]
0x18000a83d  cmp     eax, 7Fh
0x18000a840  jbe     short loc_18000A857
0x18000a842  mov     r9d, r15d
0x18000a845  lea     rcx, [rdi+48h]
0x18000a849  mov     r8d, r14d
0x18000a84c  mov     edx, ebx
0x18000a84e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a853  mov     bl, al
0x18000a855  jmp     short loc_18000A868
0x18000a857  mov     r8d, r14d
0x18000a85a  mov     edx, ebx
0x18000a85c  lea     rcx, [rdi+8]
0x18000a860  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a865  mov     bl, [rdi+40h]
0x18000a868  test    rdi, rdi
0x18000a86b  jz      short loc_18000A876
0x18000a86d  mov     rcx, rdi; SRWLock
0x18000a870  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a876  test    bl, bl
0x18000a878  jz      short loc_18000A8C6
0x18000a87a  jmp     short loc_18000A884
0x18000a87c  mov     rcx, rdi; SRWLock
0x18000a87f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a884  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a88b  jnz     short loc_18000A8C6
0x18000a88d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a894  test    rax, rax
0x18000a897  jz      short loc_18000A8A2
0x18000a899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89e  test    al, al
0x18000a8a0  jnz     short loc_18000A8C6
0x18000a8a2  lea     rbx, [rsi+20h]
0x18000a8a6  mov     rcx, rbx; SRWLock
0x18000a8a9  call    cs:__imp_AcquireSRWLockExclusive
0x18000a8af  mov     rcx, rsi; pv
0x18000a8b2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000a8b7  test    rbx, rbx
0x18000a8ba  jz      short loc_18000A8C6
0x18000a8bc  mov     rcx, rbx; SRWLock
0x18000a8bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a8c5  nop
0x18000a8c6  add     rsp, 28h
0x18000a8ca  pop     r15
0x18000a8cc  pop     r14
0x18000a8ce  pop     rdi
0x18000a8cf  pop     rsi
0x18000a8d0  pop     rbp
0x18000a8d1  pop     rbx
0x18000a8d2  retn
```
