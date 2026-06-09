# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008534`
- end: `0x180008643`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800096a0`

## callees

- `0x180007c00`
- `0x180007cb4`
- `0x180008534`
- `0x18000864c`
- `0x180008680`
- `0x1800086b8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000862f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000862f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008592`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008619`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008592`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008619`

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
0x180008534  push    rbx
0x180008536  push    rbp
0x180008537  push    rsi
0x180008538  push    rdi
0x180008539  push    r14
0x18000853b  push    r15
0x18000853d  sub     rsp, 28h
0x180008541  mov     r15, r9
0x180008544  mov     ebx, r8d
0x180008547  mov     r14d, edx
0x18000854a  mov     rsi, rcx
0x18000854d  cmp     byte ptr [rcx], 0
0x180008550  jz      loc_180008636
0x180008556  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000855b  test    al, al
0x18000855d  jz      loc_180008636
0x180008563  mov     rdi, [rsi+18h]
0x180008567  cmp     ebx, 0FEh
0x18000856d  jz      short loc_1800085EC
0x18000856f  cmp     ebx, 0C8h
0x180008575  jb      short loc_18000858F
0x180008577  cmp     ebx, 100h
0x18000857d  jl      loc_180008636
0x180008583  cmp     ebx, 200h
0x180008589  jnb     loc_180008636
0x18000858f  mov     rcx, rdi; SRWLock
0x180008592  call    cs:__imp_AcquireSRWLockExclusive
0x180008598  cmp     ebx, 7
0x18000859b  ja      short loc_1800085A7
0x18000859d  mov     eax, 0CCh
0x1800085a2  bt      eax, ebx
0x1800085a5  jb      short loc_1800085C7
0x1800085a7  lea     eax, [rbx-100h]
0x1800085ad  cmp     eax, 7Fh
0x1800085b0  jbe     short loc_1800085C7
0x1800085b2  mov     r9d, r15d
0x1800085b5  lea     rcx, [rdi+48h]
0x1800085b9  mov     r8d, r14d
0x1800085bc  mov     edx, ebx
0x1800085be  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800085c3  mov     bl, al
0x1800085c5  jmp     short loc_1800085D8
0x1800085c7  mov     r8d, r14d
0x1800085ca  mov     edx, ebx
0x1800085cc  lea     rcx, [rdi+8]
0x1800085d0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800085d5  mov     bl, [rdi+40h]
0x1800085d8  test    rdi, rdi
0x1800085db  jz      short loc_1800085E6
0x1800085dd  mov     rcx, rdi; SRWLock
0x1800085e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800085e6  test    bl, bl
0x1800085e8  jz      short loc_180008636
0x1800085ea  jmp     short loc_1800085F4
0x1800085ec  mov     rcx, rdi; SRWLock
0x1800085ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800085f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800085fb  jnz     short loc_180008636
0x1800085fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008604  test    rax, rax
0x180008607  jz      short loc_180008612
0x180008609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000860e  test    al, al
0x180008610  jnz     short loc_180008636
0x180008612  lea     rbx, [rsi+20h]
0x180008616  mov     rcx, rbx; SRWLock
0x180008619  call    cs:__imp_AcquireSRWLockExclusive
0x18000861f  mov     rcx, rsi; pv
0x180008622  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180008627  test    rbx, rbx
0x18000862a  jz      short loc_180008636
0x18000862c  mov     rcx, rbx; SRWLock
0x18000862f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008635  nop
0x180008636  add     rsp, 28h
0x18000863a  pop     r15
0x18000863c  pop     r14
0x18000863e  pop     rdi
0x18000863f  pop     rsi
0x180008640  pop     rbp
0x180008641  pop     rbx
0x180008642  retn
```
