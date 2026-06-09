# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180015900`
- end: `0x1800159de`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180015900`
- `0x18001685c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015994`
- `msvcrt!memcpy_s` at `0x180015994`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800159c1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800159c1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001592c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001592c`

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
      && a3 == dword_1800712A4
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800712D8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800712E8 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800712E8),
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
0x180015900  mov     [rsp+arg_0], rbx
0x180015905  mov     [rsp+arg_8], rsi
0x18001590a  push    rdi
0x18001590b  sub     rsp, 30h
0x18001590f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015915  mov     esi, r8d
0x180015918  mov     ebx, edx
0x18001591a  mov     rdi, rcx
0x18001591d  test    eax, eax
0x18001591f  jz      loc_1800159CD
0x180015925  lea     rcx, SRWLock; SRWLock
0x18001592c  call    cs:__imp_AcquireSRWLockExclusive
0x180015933  nop     dword ptr [rax+rax+00h]
0x180015938  mov     eax, cs:dword_1800712A4
0x18001593e  test    esi, esi
0x180015940  jz      short loc_1800159A9
0x180015942  cmp     esi, eax
0x180015944  jnz     short loc_1800159A9
0x180015946  mov     esi, 10h
0x18001594b  mov     [rsp+38h+var_14], 0
0x180015953  mov     edx, esi; unsigned __int64
0x180015955  mov     [rsp+38h+Source], ebx
0x180015959  lea     rcx, qword_1800712D8; this
0x180015960  mov     [rsp+38h+var_10], rdi
0x180015965  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001596a  test    al, al
0x18001596c  jz      short loc_1800159A9
0x18001596e  mov     rcx, cs:Destination; Destination
0x180015975  lea     r8, [rsp+38h+Source]; Source
0x18001597a  mov     rax, cs:qword_1800712E8
0x180015981  mov     r9d, esi; SourceSize
0x180015984  sub     rax, rcx
0x180015987  cmp     rcx, cs:qword_1800712E8
0x18001598e  sbb     rdx, rdx
0x180015991  and     rdx, rax; DestinationSize
0x180015994  call    cs:__imp_memcpy_s
0x18001599b  nop     dword ptr [rax+rax+00h]
0x1800159a0  add     cs:Destination, rsi
0x1800159a7  jmp     short loc_1800159BA
0x1800159a9  neg     ebx
0x1800159ab  sbb     eax, eax
0x1800159ad  and     eax, 83Ah
0x1800159b2  add     eax, 0FFFFF7C1h
0x1800159b7  lock and [rdi], eax
0x1800159ba  lea     rcx, SRWLock; SRWLock
0x1800159c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800159c8  nop     dword ptr [rax+rax+00h]
0x1800159cd  mov     rbx, [rsp+38h+arg_0]
0x1800159d2  mov     rsi, [rsp+38h+arg_8]
0x1800159d7  add     rsp, 30h
0x1800159db  pop     rdi
0x1800159dc  retn
```
