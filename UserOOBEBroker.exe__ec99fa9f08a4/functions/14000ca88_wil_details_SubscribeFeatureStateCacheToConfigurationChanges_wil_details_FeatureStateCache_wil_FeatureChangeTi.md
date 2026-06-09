# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000ca88`
- end: `0x14000cb53`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000a244`
- `0x14000a660`

## callees

- `0x14000ca88`
- `0x14000d7d4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000cab4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000cab4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000cb3d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000cb3d`
- `msvcrt!memcpy_s` at `0x14000cb16`
- `msvcrt!memcpy_s` at `0x14000cb16`

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
      && a3 == dword_1400173D4
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1400173F8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_140017408 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_140017408),
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
0x14000ca88  mov     [rsp+arg_0], rbx
0x14000ca8d  mov     [rsp+arg_8], rsi
0x14000ca92  push    rdi
0x14000ca93  sub     rsp, 30h
0x14000ca97  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ca9d  mov     esi, r8d
0x14000caa0  mov     ebx, edx
0x14000caa2  mov     rdi, rcx
0x14000caa5  test    eax, eax
0x14000caa7  jz      loc_14000CB43
0x14000caad  lea     rcx, SRWLock; SRWLock
0x14000cab4  call    cs:__imp_AcquireSRWLockExclusive
0x14000caba  mov     eax, cs:dword_1400173D4
0x14000cac0  test    esi, esi
0x14000cac2  jz      short loc_14000CB25
0x14000cac4  cmp     esi, eax
0x14000cac6  jnz     short loc_14000CB25
0x14000cac8  mov     esi, 10h
0x14000cacd  mov     [rsp+38h+var_14], 0
0x14000cad5  mov     edx, esi; unsigned __int64
0x14000cad7  mov     [rsp+38h+Source], ebx
0x14000cadb  lea     rcx, qword_1400173F8; this
0x14000cae2  mov     [rsp+38h+var_10], rdi
0x14000cae7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000caec  test    al, al
0x14000caee  jz      short loc_14000CB25
0x14000caf0  mov     rcx, cs:Destination; Destination
0x14000caf7  lea     r8, [rsp+38h+Source]; Source
0x14000cafc  mov     rax, cs:qword_140017408
0x14000cb03  mov     r9d, esi; SourceSize
0x14000cb06  sub     rax, rcx
0x14000cb09  cmp     rcx, cs:qword_140017408
0x14000cb10  sbb     rdx, rdx
0x14000cb13  and     rdx, rax; DestinationSize
0x14000cb16  call    cs:__imp_memcpy_s
0x14000cb1c  add     cs:Destination, rsi
0x14000cb23  jmp     short loc_14000CB36
0x14000cb25  neg     ebx
0x14000cb27  sbb     eax, eax
0x14000cb29  and     eax, 83Ah
0x14000cb2e  add     eax, 0FFFFF7C1h
0x14000cb33  lock and [rdi], eax
0x14000cb36  lea     rcx, SRWLock; SRWLock
0x14000cb3d  call    cs:__imp_ReleaseSRWLockExclusive
0x14000cb43  mov     rbx, [rsp+38h+arg_0]
0x14000cb48  mov     rsi, [rsp+38h+arg_8]
0x14000cb4d  add     rsp, 30h
0x14000cb51  pop     rdi
0x14000cb52  retn
```
