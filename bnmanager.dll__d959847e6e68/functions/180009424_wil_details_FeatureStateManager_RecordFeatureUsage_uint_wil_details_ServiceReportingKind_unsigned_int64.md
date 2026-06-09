# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180009424`
- end: `0x180009533`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b6a0`

## callees

- `0x1800076c4`
- `0x180007778`
- `0x180009424`
- `0x180009574`
- `0x1800095a8`
- `0x1800095e0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009482`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009509`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009482`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800094d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000951f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800094d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000951f`

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
0x180009424  push    rbx
0x180009426  push    rbp
0x180009427  push    rsi
0x180009428  push    rdi
0x180009429  push    r14
0x18000942b  push    r15
0x18000942d  sub     rsp, 28h
0x180009431  mov     r15, r9
0x180009434  mov     ebx, r8d
0x180009437  mov     r14d, edx
0x18000943a  mov     rsi, rcx
0x18000943d  cmp     byte ptr [rcx], 0
0x180009440  jz      loc_180009526
0x180009446  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000944b  test    al, al
0x18000944d  jz      loc_180009526
0x180009453  mov     rdi, [rsi+18h]
0x180009457  cmp     ebx, 0FEh
0x18000945d  jz      short loc_1800094DC
0x18000945f  cmp     ebx, 0C8h
0x180009465  jb      short loc_18000947F
0x180009467  cmp     ebx, 100h
0x18000946d  jl      loc_180009526
0x180009473  cmp     ebx, 200h
0x180009479  jnb     loc_180009526
0x18000947f  mov     rcx, rdi; SRWLock
0x180009482  call    cs:__imp_AcquireSRWLockExclusive
0x180009488  cmp     ebx, 7
0x18000948b  ja      short loc_180009497
0x18000948d  mov     eax, 0CCh
0x180009492  bt      eax, ebx
0x180009495  jb      short loc_1800094B7
0x180009497  lea     eax, [rbx-100h]
0x18000949d  cmp     eax, 7Fh
0x1800094a0  jbe     short loc_1800094B7
0x1800094a2  mov     r9d, r15d
0x1800094a5  lea     rcx, [rdi+48h]
0x1800094a9  mov     r8d, r14d
0x1800094ac  mov     edx, ebx
0x1800094ae  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800094b3  mov     bl, al
0x1800094b5  jmp     short loc_1800094C8
0x1800094b7  mov     r8d, r14d
0x1800094ba  mov     edx, ebx
0x1800094bc  lea     rcx, [rdi+8]
0x1800094c0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800094c5  mov     bl, [rdi+40h]
0x1800094c8  test    rdi, rdi
0x1800094cb  jz      short loc_1800094D6
0x1800094cd  mov     rcx, rdi; SRWLock
0x1800094d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800094d6  test    bl, bl
0x1800094d8  jz      short loc_180009526
0x1800094da  jmp     short loc_1800094E4
0x1800094dc  mov     rcx, rdi; SRWLock
0x1800094df  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800094e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800094eb  jnz     short loc_180009526
0x1800094ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800094f4  test    rax, rax
0x1800094f7  jz      short loc_180009502
0x1800094f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094fe  test    al, al
0x180009500  jnz     short loc_180009526
0x180009502  lea     rbx, [rsi+20h]
0x180009506  mov     rcx, rbx; SRWLock
0x180009509  call    cs:__imp_AcquireSRWLockExclusive
0x18000950f  mov     rcx, rsi; pv
0x180009512  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180009517  test    rbx, rbx
0x18000951a  jz      short loc_180009526
0x18000951c  mov     rcx, rbx; SRWLock
0x18000951f  call    cs:__imp_ReleaseSRWLockExclusive
0x180009525  nop
0x180009526  add     rsp, 28h
0x18000952a  pop     r15
0x18000952c  pop     r14
0x18000952e  pop     rdi
0x18000952f  pop     rsi
0x180009530  pop     rbp
0x180009531  pop     rbx
0x180009532  retn
```
