# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006164`
- end: `0x180006273`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008150`

## callees

- `0x180004634`
- `0x1800046e8`
- `0x180006164`
- `0x1800062b4`
- `0x1800062e8`
- `0x180006320`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006249`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006249`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006210`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000625f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006210`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000625f`

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
0x180006164  push    rbx
0x180006166  push    rbp
0x180006167  push    rsi
0x180006168  push    rdi
0x180006169  push    r14
0x18000616b  push    r15
0x18000616d  sub     rsp, 28h
0x180006171  mov     r15, r9
0x180006174  mov     ebx, r8d
0x180006177  mov     r14d, edx
0x18000617a  mov     rsi, rcx
0x18000617d  cmp     byte ptr [rcx], 0
0x180006180  jz      loc_180006266
0x180006186  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000618b  test    al, al
0x18000618d  jz      loc_180006266
0x180006193  mov     rdi, [rsi+18h]
0x180006197  cmp     ebx, 0FEh
0x18000619d  jz      short loc_18000621C
0x18000619f  cmp     ebx, 0C8h
0x1800061a5  jb      short loc_1800061BF
0x1800061a7  cmp     ebx, 100h
0x1800061ad  jl      loc_180006266
0x1800061b3  cmp     ebx, 200h
0x1800061b9  jnb     loc_180006266
0x1800061bf  mov     rcx, rdi; SRWLock
0x1800061c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800061c8  cmp     ebx, 7
0x1800061cb  ja      short loc_1800061D7
0x1800061cd  mov     eax, 0CCh
0x1800061d2  bt      eax, ebx
0x1800061d5  jb      short loc_1800061F7
0x1800061d7  lea     eax, [rbx-100h]
0x1800061dd  cmp     eax, 7Fh
0x1800061e0  jbe     short loc_1800061F7
0x1800061e2  mov     r9d, r15d
0x1800061e5  lea     rcx, [rdi+48h]
0x1800061e9  mov     r8d, r14d
0x1800061ec  mov     edx, ebx
0x1800061ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800061f3  mov     bl, al
0x1800061f5  jmp     short loc_180006208
0x1800061f7  mov     r8d, r14d
0x1800061fa  mov     edx, ebx
0x1800061fc  lea     rcx, [rdi+8]
0x180006200  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006205  mov     bl, [rdi+40h]
0x180006208  test    rdi, rdi
0x18000620b  jz      short loc_180006216
0x18000620d  mov     rcx, rdi; SRWLock
0x180006210  call    cs:__imp_ReleaseSRWLockExclusive
0x180006216  test    bl, bl
0x180006218  jz      short loc_180006266
0x18000621a  jmp     short loc_180006224
0x18000621c  mov     rcx, rdi; SRWLock
0x18000621f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006224  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000622b  jnz     short loc_180006266
0x18000622d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006234  test    rax, rax
0x180006237  jz      short loc_180006242
0x180006239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623e  test    al, al
0x180006240  jnz     short loc_180006266
0x180006242  lea     rbx, [rsi+20h]
0x180006246  mov     rcx, rbx; SRWLock
0x180006249  call    cs:__imp_AcquireSRWLockExclusive
0x18000624f  mov     rcx, rsi; pv
0x180006252  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006257  test    rbx, rbx
0x18000625a  jz      short loc_180006266
0x18000625c  mov     rcx, rbx; SRWLock
0x18000625f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006265  nop
0x180006266  add     rsp, 28h
0x18000626a  pop     r15
0x18000626c  pop     r14
0x18000626e  pop     rdi
0x18000626f  pop     rsi
0x180006270  pop     rbp
0x180006271  pop     rbx
0x180006272  retn
```
