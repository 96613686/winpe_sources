# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800159a4`
- end: `0x180015a6f`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012a60`
- `0x180012b40`
- `0x18001364c`

## callees

- `0x1800159a4`
- `0x1800162c4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015a32`
- `msvcrt!memcpy_s` at `0x180015a32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800159d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800159d0`

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
      && a3 == dword_1800274A4
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800274C8, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800274D8 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800274D8),
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
0x1800159a4  mov     [rsp+arg_0], rbx
0x1800159a9  mov     [rsp+arg_8], rsi
0x1800159ae  push    rdi
0x1800159af  sub     rsp, 30h
0x1800159b3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800159b9  mov     esi, r8d
0x1800159bc  mov     ebx, edx
0x1800159be  mov     rdi, rcx
0x1800159c1  test    eax, eax
0x1800159c3  jz      loc_180015A5F
0x1800159c9  lea     rcx, SRWLock; SRWLock
0x1800159d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800159d6  mov     eax, cs:dword_1800274A4
0x1800159dc  test    esi, esi
0x1800159de  jz      short loc_180015A41
0x1800159e0  cmp     esi, eax
0x1800159e2  jnz     short loc_180015A41
0x1800159e4  mov     esi, 10h
0x1800159e9  mov     [rsp+38h+var_14], 0
0x1800159f1  mov     edx, esi; unsigned __int64
0x1800159f3  mov     [rsp+38h+Source], ebx
0x1800159f7  lea     rcx, qword_1800274C8; this
0x1800159fe  mov     [rsp+38h+var_10], rdi
0x180015a03  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180015a08  test    al, al
0x180015a0a  jz      short loc_180015A41
0x180015a0c  mov     rcx, cs:Destination; Destination
0x180015a13  lea     r8, [rsp+38h+Source]; Source
0x180015a18  mov     rax, cs:qword_1800274D8
0x180015a1f  mov     r9d, esi; SourceSize
0x180015a22  sub     rax, rcx
0x180015a25  cmp     rcx, cs:qword_1800274D8
0x180015a2c  sbb     rdx, rdx
0x180015a2f  and     rdx, rax; DestinationSize
0x180015a32  call    cs:__imp_memcpy_s
0x180015a38  add     cs:Destination, rsi
0x180015a3f  jmp     short loc_180015A52
0x180015a41  neg     ebx
0x180015a43  sbb     eax, eax
0x180015a45  and     eax, 83Ah
0x180015a4a  add     eax, 0FFFFF7C1h
0x180015a4f  lock and [rdi], eax
0x180015a52  lea     rcx, SRWLock; SRWLock
0x180015a59  call    cs:__imp_ReleaseSRWLockExclusive
0x180015a5f  mov     rbx, [rsp+38h+arg_0]
0x180015a64  mov     rsi, [rsp+38h+arg_8]
0x180015a69  add     rsp, 30h
0x180015a6d  pop     rdi
0x180015a6e  retn
```
