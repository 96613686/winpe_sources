# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140009680`
- end: `0x14000978f`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000b650`

## callees

- `0x1400083a4`
- `0x140008458`
- `0x140009680`
- `0x140009798`
- `0x1400097cc`
- `0x140009804`
- `0x140011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000972c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000977b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000972c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000977b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400096de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009765`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400096de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009765`

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
0x140009680  push    rbx
0x140009682  push    rbp
0x140009683  push    rsi
0x140009684  push    rdi
0x140009685  push    r14
0x140009687  push    r15
0x140009689  sub     rsp, 28h
0x14000968d  mov     r15, r9
0x140009690  mov     ebx, r8d
0x140009693  mov     r14d, edx
0x140009696  mov     rsi, rcx
0x140009699  cmp     byte ptr [rcx], 0
0x14000969c  jz      loc_140009782
0x1400096a2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400096a7  test    al, al
0x1400096a9  jz      loc_140009782
0x1400096af  mov     rdi, [rsi+18h]
0x1400096b3  cmp     ebx, 0FEh
0x1400096b9  jz      short loc_140009738
0x1400096bb  cmp     ebx, 0C8h
0x1400096c1  jb      short loc_1400096DB
0x1400096c3  cmp     ebx, 100h
0x1400096c9  jl      loc_140009782
0x1400096cf  cmp     ebx, 200h
0x1400096d5  jnb     loc_140009782
0x1400096db  mov     rcx, rdi; SRWLock
0x1400096de  call    cs:__imp_AcquireSRWLockExclusive
0x1400096e4  cmp     ebx, 7
0x1400096e7  ja      short loc_1400096F3
0x1400096e9  mov     eax, 0CCh
0x1400096ee  bt      eax, ebx
0x1400096f1  jb      short loc_140009713
0x1400096f3  lea     eax, [rbx-100h]
0x1400096f9  cmp     eax, 7Fh
0x1400096fc  jbe     short loc_140009713
0x1400096fe  mov     r9d, r15d
0x140009701  lea     rcx, [rdi+48h]
0x140009705  mov     r8d, r14d
0x140009708  mov     edx, ebx
0x14000970a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000970f  mov     bl, al
0x140009711  jmp     short loc_140009724
0x140009713  mov     r8d, r14d
0x140009716  mov     edx, ebx
0x140009718  lea     rcx, [rdi+8]
0x14000971c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140009721  mov     bl, [rdi+40h]
0x140009724  test    rdi, rdi
0x140009727  jz      short loc_140009732
0x140009729  mov     rcx, rdi; SRWLock
0x14000972c  call    cs:__imp_ReleaseSRWLockExclusive
0x140009732  test    bl, bl
0x140009734  jz      short loc_140009782
0x140009736  jmp     short loc_140009740
0x140009738  mov     rcx, rdi; SRWLock
0x14000973b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140009740  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140009747  jnz     short loc_140009782
0x140009749  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009750  test    rax, rax
0x140009753  jz      short loc_14000975E
0x140009755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000975a  test    al, al
0x14000975c  jnz     short loc_140009782
0x14000975e  lea     rbx, [rsi+20h]
0x140009762  mov     rcx, rbx; SRWLock
0x140009765  call    cs:__imp_AcquireSRWLockExclusive
0x14000976b  mov     rcx, rsi; pv
0x14000976e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140009773  test    rbx, rbx
0x140009776  jz      short loc_140009782
0x140009778  mov     rcx, rbx; SRWLock
0x14000977b  call    cs:__imp_ReleaseSRWLockExclusive
0x140009781  nop
0x140009782  add     rsp, 28h
0x140009786  pop     r15
0x140009788  pop     r14
0x14000978a  pop     rdi
0x14000978b  pop     rsi
0x14000978c  pop     rbp
0x14000978d  pop     rbx
0x14000978e  retn
```
