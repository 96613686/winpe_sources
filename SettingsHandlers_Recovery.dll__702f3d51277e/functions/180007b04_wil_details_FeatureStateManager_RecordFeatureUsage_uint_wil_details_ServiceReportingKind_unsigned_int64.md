# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007b04`
- end: `0x180007c13`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009f50`

## callees

- `0x180005a90`
- `0x180005c14`
- `0x180007b04`
- `0x180007c94`
- `0x180007cc8`
- `0x180007d00`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007be9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007be9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bff`

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
0x180007b04  push    rbx
0x180007b06  push    rbp
0x180007b07  push    rsi
0x180007b08  push    rdi
0x180007b09  push    r14
0x180007b0b  push    r15
0x180007b0d  sub     rsp, 28h
0x180007b11  mov     r15, r9
0x180007b14  mov     ebx, r8d
0x180007b17  mov     r14d, edx
0x180007b1a  mov     rsi, rcx
0x180007b1d  cmp     byte ptr [rcx], 0
0x180007b20  jz      loc_180007C06
0x180007b26  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007b2b  test    al, al
0x180007b2d  jz      loc_180007C06
0x180007b33  mov     rdi, [rsi+18h]
0x180007b37  cmp     ebx, 0FEh
0x180007b3d  jz      short loc_180007BBC
0x180007b3f  cmp     ebx, 0C8h
0x180007b45  jb      short loc_180007B5F
0x180007b47  cmp     ebx, 100h
0x180007b4d  jl      loc_180007C06
0x180007b53  cmp     ebx, 200h
0x180007b59  jnb     loc_180007C06
0x180007b5f  mov     rcx, rdi; SRWLock
0x180007b62  call    cs:__imp_AcquireSRWLockExclusive
0x180007b68  cmp     ebx, 7
0x180007b6b  ja      short loc_180007B77
0x180007b6d  mov     eax, 0CCh
0x180007b72  bt      eax, ebx
0x180007b75  jb      short loc_180007B97
0x180007b77  lea     eax, [rbx-100h]
0x180007b7d  cmp     eax, 7Fh
0x180007b80  jbe     short loc_180007B97
0x180007b82  mov     r9d, r15d
0x180007b85  lea     rcx, [rdi+48h]
0x180007b89  mov     r8d, r14d
0x180007b8c  mov     edx, ebx
0x180007b8e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b93  mov     bl, al
0x180007b95  jmp     short loc_180007BA8
0x180007b97  mov     r8d, r14d
0x180007b9a  mov     edx, ebx
0x180007b9c  lea     rcx, [rdi+8]
0x180007ba0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007ba5  mov     bl, [rdi+40h]
0x180007ba8  test    rdi, rdi
0x180007bab  jz      short loc_180007BB6
0x180007bad  mov     rcx, rdi; SRWLock
0x180007bb0  call    cs:__imp_ReleaseSRWLockExclusive
0x180007bb6  test    bl, bl
0x180007bb8  jz      short loc_180007C06
0x180007bba  jmp     short loc_180007BC4
0x180007bbc  mov     rcx, rdi; SRWLock
0x180007bbf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007bc4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007bcb  jnz     short loc_180007C06
0x180007bcd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007bd4  test    rax, rax
0x180007bd7  jz      short loc_180007BE2
0x180007bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bde  test    al, al
0x180007be0  jnz     short loc_180007C06
0x180007be2  lea     rbx, [rsi+20h]
0x180007be6  mov     rcx, rbx; SRWLock
0x180007be9  call    cs:__imp_AcquireSRWLockExclusive
0x180007bef  mov     rcx, rsi; pv
0x180007bf2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007bf7  test    rbx, rbx
0x180007bfa  jz      short loc_180007C06
0x180007bfc  mov     rcx, rbx; SRWLock
0x180007bff  call    cs:__imp_ReleaseSRWLockExclusive
0x180007c05  nop
0x180007c06  add     rsp, 28h
0x180007c0a  pop     r15
0x180007c0c  pop     r14
0x180007c0e  pop     rdi
0x180007c0f  pop     rsi
0x180007c10  pop     rbp
0x180007c11  pop     rbx
0x180007c12  retn
```
