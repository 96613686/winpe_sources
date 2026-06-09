# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009528`
- end: `0x18000960f`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `231`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005054`
- `0x180005148`
- `0x1800068e4`

## callees

- `0x180009528`
- `0x18000af9c`
- `0x18000c610`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800095c5`
- `msvcrt!memcpy_s` at `0x1800095c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009563`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009563`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800095ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800095ec`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-20h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( a3
      && a3 == dword_180015714
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180015738, 0x10u)) )
    {
      memcpy_s(
        qword_180015740,
        (qword_180015748 - (_QWORD)qword_180015740) & -(__int64)((unsigned __int64)qword_180015740 < qword_180015748),
        Source,
        0x10u);
      qword_180015740 = (char *)qword_180015740 + 16;
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
0x180009528  mov     [rsp+arg_10], rbx
0x18000952d  mov     [rsp+arg_18], rsi
0x180009532  push    rdi
0x180009533  sub     rsp, 40h
0x180009537  mov     rax, cs:__security_cookie
0x18000953e  xor     rax, rsp
0x180009541  mov     [rsp+48h+var_18], rax
0x180009546  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000954c  mov     esi, r8d
0x18000954f  mov     edi, edx
0x180009551  mov     rbx, rcx
0x180009554  test    eax, eax
0x180009556  jz      loc_1800095F2
0x18000955c  lea     rcx, SRWLock; SRWLock
0x180009563  call    cs:__imp_AcquireSRWLockExclusive
0x180009569  mov     eax, cs:dword_180015714
0x18000956f  test    esi, esi
0x180009571  jz      short loc_1800095D4
0x180009573  cmp     esi, eax
0x180009575  jnz     short loc_1800095D4
0x180009577  mov     esi, 10h
0x18000957c  mov     [rsp+48h+var_24], 0
0x180009584  mov     edx, esi; unsigned __int64
0x180009586  mov     [rsp+48h+Source], edi
0x18000958a  lea     rcx, qword_180015738; this
0x180009591  mov     [rsp+48h+var_20], rbx
0x180009596  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000959b  test    al, al
0x18000959d  jz      short loc_1800095D4
0x18000959f  mov     rcx, cs:qword_180015740; Destination
0x1800095a6  lea     r8, [rsp+48h+Source]; Source
0x1800095ab  mov     rax, cs:qword_180015748
0x1800095b2  mov     r9d, esi; SourceSize
0x1800095b5  sub     rax, rcx
0x1800095b8  cmp     rcx, cs:qword_180015748
0x1800095bf  sbb     rdx, rdx
0x1800095c2  and     rdx, rax; DestinationSize
0x1800095c5  call    cs:__imp_memcpy_s
0x1800095cb  add     cs:qword_180015740, rsi
0x1800095d2  jmp     short loc_1800095E5
0x1800095d4  neg     edi
0x1800095d6  sbb     eax, eax
0x1800095d8  and     eax, 83Ah
0x1800095dd  add     eax, 0FFFFF7C1h
0x1800095e2  lock and [rbx], eax
0x1800095e5  lea     rcx, SRWLock; SRWLock
0x1800095ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800095f2  mov     rcx, [rsp+48h+var_18]
0x1800095f7  xor     rcx, rsp; StackCookie
0x1800095fa  call    __security_check_cookie
0x1800095ff  mov     rbx, [rsp+48h+arg_10]
0x180009604  mov     rsi, [rsp+48h+arg_18]
0x180009609  add     rsp, 40h
0x18000960d  pop     rdi
0x18000960e  retn
```
