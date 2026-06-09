# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180024ab4`
- end: `0x180024bc3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180025c10`

## callees

- `0x1800241dc`
- `0x180024290`
- `0x180024ab4`
- `0x180024bcc`
- `0x180024c00`
- `0x180024c38`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024b12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024b99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024b12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024b99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024baf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024b60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024baf`

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
0x180024ab4  push    rbx
0x180024ab6  push    rbp
0x180024ab7  push    rsi
0x180024ab8  push    rdi
0x180024ab9  push    r14
0x180024abb  push    r15
0x180024abd  sub     rsp, 28h
0x180024ac1  mov     r15, r9
0x180024ac4  mov     ebx, r8d
0x180024ac7  mov     r14d, edx
0x180024aca  mov     rsi, rcx
0x180024acd  cmp     byte ptr [rcx], 0
0x180024ad0  jz      loc_180024BB6
0x180024ad6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180024adb  test    al, al
0x180024add  jz      loc_180024BB6
0x180024ae3  mov     rdi, [rsi+18h]
0x180024ae7  cmp     ebx, 0FEh
0x180024aed  jz      short loc_180024B6C
0x180024aef  cmp     ebx, 0C8h
0x180024af5  jb      short loc_180024B0F
0x180024af7  cmp     ebx, 100h
0x180024afd  jl      loc_180024BB6
0x180024b03  cmp     ebx, 200h
0x180024b09  jnb     loc_180024BB6
0x180024b0f  mov     rcx, rdi; SRWLock
0x180024b12  call    cs:__imp_AcquireSRWLockExclusive
0x180024b18  cmp     ebx, 7
0x180024b1b  ja      short loc_180024B27
0x180024b1d  mov     eax, 0CCh
0x180024b22  bt      eax, ebx
0x180024b25  jb      short loc_180024B47
0x180024b27  lea     eax, [rbx-100h]
0x180024b2d  cmp     eax, 7Fh
0x180024b30  jbe     short loc_180024B47
0x180024b32  mov     r9d, r15d
0x180024b35  lea     rcx, [rdi+48h]
0x180024b39  mov     r8d, r14d
0x180024b3c  mov     edx, ebx
0x180024b3e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180024b43  mov     bl, al
0x180024b45  jmp     short loc_180024B58
0x180024b47  mov     r8d, r14d
0x180024b4a  mov     edx, ebx
0x180024b4c  lea     rcx, [rdi+8]
0x180024b50  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180024b55  mov     bl, [rdi+40h]
0x180024b58  test    rdi, rdi
0x180024b5b  jz      short loc_180024B66
0x180024b5d  mov     rcx, rdi; SRWLock
0x180024b60  call    cs:__imp_ReleaseSRWLockExclusive
0x180024b66  test    bl, bl
0x180024b68  jz      short loc_180024BB6
0x180024b6a  jmp     short loc_180024B74
0x180024b6c  mov     rcx, rdi; SRWLock
0x180024b6f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180024b74  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180024b7b  jnz     short loc_180024BB6
0x180024b7d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180024b84  test    rax, rax
0x180024b87  jz      short loc_180024B92
0x180024b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b8e  test    al, al
0x180024b90  jnz     short loc_180024BB6
0x180024b92  lea     rbx, [rsi+20h]
0x180024b96  mov     rcx, rbx; SRWLock
0x180024b99  call    cs:__imp_AcquireSRWLockExclusive
0x180024b9f  mov     rcx, rsi; pv
0x180024ba2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180024ba7  test    rbx, rbx
0x180024baa  jz      short loc_180024BB6
0x180024bac  mov     rcx, rbx; SRWLock
0x180024baf  call    cs:__imp_ReleaseSRWLockExclusive
0x180024bb5  nop
0x180024bb6  add     rsp, 28h
0x180024bba  pop     r15
0x180024bbc  pop     r14
0x180024bbe  pop     rdi
0x180024bbf  pop     rsi
0x180024bc0  pop     rbp
0x180024bc1  pop     rbx
0x180024bc2  retn
```
