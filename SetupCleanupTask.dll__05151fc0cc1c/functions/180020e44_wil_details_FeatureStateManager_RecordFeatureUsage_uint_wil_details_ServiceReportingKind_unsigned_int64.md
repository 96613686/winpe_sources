# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180020e44`
- end: `0x180020f52`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180024040`

## callees

- `0x18001b0a0`
- `0x18001b154`
- `0x180020e44`
- `0x180020f90`
- `0x180020fc4`
- `0x180020ffc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ef0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020f3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ef0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020f3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020ea2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020f29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020ea2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020f29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180020e44  push    rbx
0x180020e46  push    rbp
0x180020e47  push    rsi
0x180020e48  push    rdi
0x180020e49  push    r14
0x180020e4b  push    r15
0x180020e4d  sub     rsp, 28h
0x180020e51  cmp     byte ptr [rcx], 0
0x180020e54  mov     r15, r9
0x180020e57  mov     ebx, r8d
0x180020e5a  mov     r14d, edx
0x180020e5d  mov     rsi, rcx
0x180020e60  jz      loc_180020F45
0x180020e66  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180020e6b  test    al, al
0x180020e6d  jz      loc_180020F45
0x180020e73  mov     rdi, [rsi+18h]
0x180020e77  cmp     ebx, 0FEh
0x180020e7d  jz      short loc_180020EFC
0x180020e7f  cmp     ebx, 0C8h
0x180020e85  jb      short loc_180020E9F
0x180020e87  cmp     ebx, 100h
0x180020e8d  jl      loc_180020F45
0x180020e93  cmp     ebx, 200h
0x180020e99  jnb     loc_180020F45
0x180020e9f  mov     rcx, rdi; SRWLock
0x180020ea2  call    cs:__imp_AcquireSRWLockExclusive
0x180020ea8  cmp     ebx, 7
0x180020eab  ja      short loc_180020EB7
0x180020ead  mov     eax, 0CCh
0x180020eb2  bt      eax, ebx
0x180020eb5  jb      short loc_180020ED7
0x180020eb7  lea     eax, [rbx-100h]
0x180020ebd  cmp     eax, 7Fh
0x180020ec0  jbe     short loc_180020ED7
0x180020ec2  mov     r9d, r15d
0x180020ec5  lea     rcx, [rdi+48h]
0x180020ec9  mov     r8d, r14d
0x180020ecc  mov     edx, ebx
0x180020ece  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020ed3  mov     bl, al
0x180020ed5  jmp     short loc_180020EE8
0x180020ed7  mov     r8d, r14d
0x180020eda  lea     rcx, [rdi+8]
0x180020ede  mov     edx, ebx
0x180020ee0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020ee5  mov     bl, [rdi+40h]
0x180020ee8  test    rdi, rdi
0x180020eeb  jz      short loc_180020EF6
0x180020eed  mov     rcx, rdi; SRWLock
0x180020ef0  call    cs:__imp_ReleaseSRWLockExclusive
0x180020ef6  test    bl, bl
0x180020ef8  jz      short loc_180020F45
0x180020efa  jmp     short loc_180020F04
0x180020efc  mov     rcx, rdi; SRWLock
0x180020eff  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180020f04  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180020f0b  jnz     short loc_180020F45
0x180020f0d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180020f14  test    rax, rax
0x180020f17  jz      short loc_180020F22
0x180020f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f1e  test    al, al
0x180020f20  jnz     short loc_180020F45
0x180020f22  lea     rbx, [rsi+20h]
0x180020f26  mov     rcx, rbx; SRWLock
0x180020f29  call    cs:__imp_AcquireSRWLockExclusive
0x180020f2f  mov     rcx, rsi; pv
0x180020f32  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180020f37  test    rbx, rbx
0x180020f3a  jz      short loc_180020F45
0x180020f3c  mov     rcx, rbx; SRWLock
0x180020f3f  call    cs:__imp_ReleaseSRWLockExclusive
0x180020f45  add     rsp, 28h
0x180020f49  pop     r15
0x180020f4b  pop     r14
0x180020f4d  pop     rdi
0x180020f4e  pop     rsi
0x180020f4f  pop     rbp
0x180020f50  pop     rbx
0x180020f51  retn
```
