# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000a048`
- end: `0x18000a115`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800074dc`

## callees

- `0x18000a048`
- `0x18000c40c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a0d7`
- `msvcrt!memcpy_s` at `0x18000a0d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a0fe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000a0fe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a074`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a074`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      && a3 == dword_1800173AC
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800173D0, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800173E0 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800173E0),
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
0x18000a048  mov     [rsp+arg_0], rbx
0x18000a04d  mov     [rsp+arg_8], rsi
0x18000a052  push    rdi
0x18000a053  sub     rsp, 30h
0x18000a057  mov     esi, r8d
0x18000a05a  mov     ebx, edx
0x18000a05c  mov     rdi, rcx
0x18000a05f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a065  test    eax, eax
0x18000a067  jz      loc_18000A105
0x18000a06d  lea     rcx, SRWLock; SRWLock
0x18000a074  call    cs:__imp_AcquireSRWLockExclusive
0x18000a07a  nop
0x18000a07b  mov     eax, cs:dword_1800173AC
0x18000a081  test    esi, esi
0x18000a083  jz      short loc_18000A0E6
0x18000a085  cmp     esi, eax
0x18000a087  jnz     short loc_18000A0E6
0x18000a089  mov     [rsp+38h+var_14], 0
0x18000a091  mov     [rsp+38h+Source], ebx
0x18000a095  mov     [rsp+38h+var_10], rdi
0x18000a09a  mov     esi, 10h
0x18000a09f  mov     edx, esi; unsigned __int64
0x18000a0a1  lea     rcx, qword_1800173D0; this
0x18000a0a8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a0ad  test    al, al
0x18000a0af  jz      short loc_18000A0E6
0x18000a0b1  mov     rcx, cs:Destination; Destination
0x18000a0b8  mov     rax, cs:qword_1800173E0
0x18000a0bf  sub     rax, rcx
0x18000a0c2  cmp     rcx, cs:qword_1800173E0
0x18000a0c9  sbb     rdx, rdx
0x18000a0cc  and     rdx, rax; DestinationSize
0x18000a0cf  mov     r9d, esi; SourceSize
0x18000a0d2  lea     r8, [rsp+38h+Source]; Source
0x18000a0d7  call    cs:__imp_memcpy_s
0x18000a0dd  add     cs:Destination, rsi
0x18000a0e4  jmp     short loc_18000A0F7
0x18000a0e6  neg     ebx
0x18000a0e8  sbb     eax, eax
0x18000a0ea  and     eax, 83Ah
0x18000a0ef  add     eax, 0FFFFF7C1h
0x18000a0f4  lock and [rdi], eax
0x18000a0f7  lea     rcx, SRWLock; SRWLock
0x18000a0fe  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a104  nop
0x18000a105  mov     rbx, [rsp+38h+arg_0]
0x18000a10a  mov     rsi, [rsp+38h+arg_8]
0x18000a10f  add     rsp, 30h
0x18000a113  pop     rdi
0x18000a114  retn
```
