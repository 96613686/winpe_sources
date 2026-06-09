# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800076d4`
- end: `0x1800077ea`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `278`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009c50`

## callees

- `0x180004930`
- `0x180004ba0`
- `0x1800076d4`
- `0x180007864`
- `0x1800078b8`
- `0x180007910`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007735`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800077bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007735`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800077bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007783`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800077d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007783`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800077d2`

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
0x1800076d4  mov     [rsp+arg_18], rbx
0x1800076d9  push    rbp
0x1800076da  push    rsi
0x1800076db  push    rdi
0x1800076dc  push    r14
0x1800076de  push    r15
0x1800076e0  sub     rsp, 20h
0x1800076e4  mov     r15, r9
0x1800076e7  mov     ebx, r8d
0x1800076ea  mov     r14d, edx
0x1800076ed  mov     rsi, rcx
0x1800076f0  cmp     byte ptr [rcx], 0
0x1800076f3  jz      loc_1800077D9
0x1800076f9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800076fe  test    al, al
0x180007700  jz      loc_1800077D9
0x180007706  mov     rdi, [rsi+18h]
0x18000770a  cmp     ebx, 0FEh
0x180007710  jz      short loc_18000778F
0x180007712  cmp     ebx, 0C8h
0x180007718  jb      short loc_180007732
0x18000771a  cmp     ebx, 100h
0x180007720  jl      loc_1800077D9
0x180007726  cmp     ebx, 200h
0x18000772c  jnb     loc_1800077D9
0x180007732  mov     rcx, rdi; SRWLock
0x180007735  call    cs:__imp_AcquireSRWLockExclusive
0x18000773b  cmp     ebx, 7
0x18000773e  ja      short loc_18000774A
0x180007740  mov     eax, 0CCh
0x180007745  bt      eax, ebx
0x180007748  jb      short loc_18000776A
0x18000774a  lea     eax, [rbx-100h]
0x180007750  cmp     eax, 7Fh
0x180007753  jbe     short loc_18000776A
0x180007755  mov     r9d, r15d
0x180007758  lea     rcx, [rdi+48h]
0x18000775c  mov     r8d, r14d
0x18000775f  mov     edx, ebx
0x180007761  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007766  mov     bl, al
0x180007768  jmp     short loc_18000777B
0x18000776a  mov     r8d, r14d
0x18000776d  mov     edx, ebx
0x18000776f  lea     rcx, [rdi+8]
0x180007773  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007778  mov     bl, [rdi+40h]
0x18000777b  test    rdi, rdi
0x18000777e  jz      short loc_180007789
0x180007780  mov     rcx, rdi; SRWLock
0x180007783  call    cs:__imp_ReleaseSRWLockExclusive
0x180007789  test    bl, bl
0x18000778b  jz      short loc_1800077D9
0x18000778d  jmp     short loc_180007797
0x18000778f  mov     rcx, rdi; SRWLock
0x180007792  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007797  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000779e  jnz     short loc_1800077D9
0x1800077a0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800077a7  test    rax, rax
0x1800077aa  jz      short loc_1800077B5
0x1800077ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b1  test    al, al
0x1800077b3  jnz     short loc_1800077D9
0x1800077b5  lea     rbx, [rsi+20h]
0x1800077b9  mov     rcx, rbx; SRWLock
0x1800077bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800077c2  mov     rcx, rsi; pv
0x1800077c5  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800077ca  test    rbx, rbx
0x1800077cd  jz      short loc_1800077D9
0x1800077cf  mov     rcx, rbx; SRWLock
0x1800077d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800077d8  nop
0x1800077d9  mov     rbx, [rsp+48h+arg_18]
0x1800077de  add     rsp, 20h
0x1800077e2  pop     r15
0x1800077e4  pop     r14
0x1800077e6  pop     rdi
0x1800077e7  pop     rsi
0x1800077e8  pop     rbp
0x1800077e9  retn
```
