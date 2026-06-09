# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b1bc`
- end: `0x18000b2cb`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c820`

## callees

- `0x18000a2b0`
- `0x18000a364`
- `0x18000b1bc`
- `0x18000b2d4`
- `0x18000b308`
- `0x18000b340`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b21a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b21a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b268`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b268`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2b7`

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
0x18000b1bc  push    rbx
0x18000b1be  push    rbp
0x18000b1bf  push    rsi
0x18000b1c0  push    rdi
0x18000b1c1  push    r14
0x18000b1c3  push    r15
0x18000b1c5  sub     rsp, 28h
0x18000b1c9  mov     r15, r9
0x18000b1cc  mov     ebx, r8d
0x18000b1cf  mov     r14d, edx
0x18000b1d2  mov     rsi, rcx
0x18000b1d5  cmp     byte ptr [rcx], 0
0x18000b1d8  jz      loc_18000B2BE
0x18000b1de  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b1e3  test    al, al
0x18000b1e5  jz      loc_18000B2BE
0x18000b1eb  mov     rdi, [rsi+18h]
0x18000b1ef  cmp     ebx, 0FEh
0x18000b1f5  jz      short loc_18000B274
0x18000b1f7  cmp     ebx, 0C8h
0x18000b1fd  jb      short loc_18000B217
0x18000b1ff  cmp     ebx, 100h
0x18000b205  jl      loc_18000B2BE
0x18000b20b  cmp     ebx, 200h
0x18000b211  jnb     loc_18000B2BE
0x18000b217  mov     rcx, rdi; SRWLock
0x18000b21a  call    cs:__imp_AcquireSRWLockExclusive
0x18000b220  cmp     ebx, 7
0x18000b223  ja      short loc_18000B22F
0x18000b225  mov     eax, 0CCh
0x18000b22a  bt      eax, ebx
0x18000b22d  jb      short loc_18000B24F
0x18000b22f  lea     eax, [rbx-100h]
0x18000b235  cmp     eax, 7Fh
0x18000b238  jbe     short loc_18000B24F
0x18000b23a  mov     r9d, r15d
0x18000b23d  lea     rcx, [rdi+48h]
0x18000b241  mov     r8d, r14d
0x18000b244  mov     edx, ebx
0x18000b246  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b24b  mov     bl, al
0x18000b24d  jmp     short loc_18000B260
0x18000b24f  mov     r8d, r14d
0x18000b252  mov     edx, ebx
0x18000b254  lea     rcx, [rdi+8]
0x18000b258  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b25d  mov     bl, [rdi+40h]
0x18000b260  test    rdi, rdi
0x18000b263  jz      short loc_18000B26E
0x18000b265  mov     rcx, rdi; SRWLock
0x18000b268  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b26e  test    bl, bl
0x18000b270  jz      short loc_18000B2BE
0x18000b272  jmp     short loc_18000B27C
0x18000b274  mov     rcx, rdi; SRWLock
0x18000b277  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b27c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b283  jnz     short loc_18000B2BE
0x18000b285  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b28c  test    rax, rax
0x18000b28f  jz      short loc_18000B29A
0x18000b291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b296  test    al, al
0x18000b298  jnz     short loc_18000B2BE
0x18000b29a  lea     rbx, [rsi+20h]
0x18000b29e  mov     rcx, rbx; SRWLock
0x18000b2a1  call    cs:__imp_AcquireSRWLockExclusive
0x18000b2a7  mov     rcx, rsi; pv
0x18000b2aa  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000b2af  test    rbx, rbx
0x18000b2b2  jz      short loc_18000B2BE
0x18000b2b4  mov     rcx, rbx; SRWLock
0x18000b2b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2bd  nop
0x18000b2be  add     rsp, 28h
0x18000b2c2  pop     r15
0x18000b2c4  pop     r14
0x18000b2c6  pop     rdi
0x18000b2c7  pop     rsi
0x18000b2c8  pop     rbp
0x18000b2c9  pop     rbx
0x18000b2ca  retn
```
