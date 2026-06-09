# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800112ac`
- end: `0x180011383`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `215`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000def4`
- `0x18001a6f0`

## callees

- `0x1800112ac`
- `0x1800124c0`
- `0x180013758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011366`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011366`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800112d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800112d8`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( a3
      && a3 == dword_180043914
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180043948, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180043958 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180043958),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800112ac  mov     [rsp+arg_0], rbx
0x1800112b1  mov     [rsp+arg_8], rsi
0x1800112b6  push    rdi
0x1800112b7  sub     rsp, 30h
0x1800112bb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800112c1  mov     esi, r8d
0x1800112c4  mov     ebx, edx
0x1800112c6  mov     rdi, rcx
0x1800112c9  test    eax, eax
0x1800112cb  jz      loc_180011372
0x1800112d1  lea     rcx, SRWLock; SRWLock
0x1800112d8  call    cs:__imp_AcquireSRWLockExclusive
0x1800112df  nop     dword ptr [rax+rax+00h]
0x1800112e4  mov     eax, cs:dword_180043914
0x1800112ea  test    esi, esi
0x1800112ec  jz      short loc_18001134E
0x1800112ee  cmp     esi, eax
0x1800112f0  jnz     short loc_18001134E
0x1800112f2  mov     esi, 10h
0x1800112f7  mov     [rsp+38h+var_14], 0
0x1800112ff  mov     edx, esi; unsigned __int64
0x180011301  mov     [rsp+38h+Source], ebx
0x180011305  lea     rcx, qword_180043948; this
0x18001130c  mov     [rsp+38h+var_10], rdi
0x180011311  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180011316  test    al, al
0x180011318  jz      short loc_18001134E
0x18001131a  mov     rcx, cs:Destination; Destination
0x180011321  lea     r8, [rsp+38h+Source]; Source
0x180011326  mov     rax, cs:qword_180043958
0x18001132d  mov     r9d, esi; SourceSize
0x180011330  sub     rax, rcx
0x180011333  cmp     rcx, cs:qword_180043958
0x18001133a  sbb     rdx, rdx
0x18001133d  and     rdx, rax; DestinationSize
0x180011340  call    memcpy_s
0x180011345  add     cs:Destination, rsi
0x18001134c  jmp     short loc_18001135F
0x18001134e  neg     ebx
0x180011350  sbb     eax, eax
0x180011352  and     eax, 83Ah
0x180011357  add     eax, 0FFFFF7C1h
0x18001135c  lock and [rdi], eax
0x18001135f  lea     rcx, SRWLock; SRWLock
0x180011366  call    cs:__imp_ReleaseSRWLockExclusive
0x18001136d  nop     dword ptr [rax+rax+00h]
0x180011372  mov     rbx, [rsp+38h+arg_0]
0x180011377  mov     rsi, [rsp+38h+arg_8]
0x18001137c  add     rsp, 30h
0x180011380  pop     rdi
0x180011381  retn
```
