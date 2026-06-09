# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140009b34`
- end: `0x140009bff`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005824`
- `0x1400068c8`
- `0x14000c50c`
- `0x140013254`

## callees

- `0x140009b34`
- `0x14000a87c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009be9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009be9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009b60`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009b60`
- `msvcrt!memcpy_s` at `0x140009bc2`
- `msvcrt!memcpy_s` at `0x140009bc2`

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
      && a3 == dword_140020A44
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140020A68, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_140020A78 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_140020A78),
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
0x140009b34  mov     [rsp+arg_0], rbx
0x140009b39  mov     [rsp+arg_8], rsi
0x140009b3e  push    rdi
0x140009b3f  sub     rsp, 30h
0x140009b43  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009b49  mov     esi, r8d
0x140009b4c  mov     ebx, edx
0x140009b4e  mov     rdi, rcx
0x140009b51  test    eax, eax
0x140009b53  jz      loc_140009BEF
0x140009b59  lea     rcx, SRWLock; SRWLock
0x140009b60  call    cs:__imp_AcquireSRWLockExclusive
0x140009b66  mov     eax, cs:dword_140020A44
0x140009b6c  test    esi, esi
0x140009b6e  jz      short loc_140009BD1
0x140009b70  cmp     esi, eax
0x140009b72  jnz     short loc_140009BD1
0x140009b74  mov     esi, 10h
0x140009b79  mov     [rsp+38h+var_14], 0
0x140009b81  mov     edx, esi; unsigned __int64
0x140009b83  mov     [rsp+38h+Source], ebx
0x140009b87  lea     rcx, qword_140020A68; this
0x140009b8e  mov     [rsp+38h+var_10], rdi
0x140009b93  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009b98  test    al, al
0x140009b9a  jz      short loc_140009BD1
0x140009b9c  mov     rcx, cs:Destination; Destination
0x140009ba3  lea     r8, [rsp+38h+Source]; Source
0x140009ba8  mov     rax, cs:qword_140020A78
0x140009baf  mov     r9d, esi; SourceSize
0x140009bb2  sub     rax, rcx
0x140009bb5  cmp     rcx, cs:qword_140020A78
0x140009bbc  sbb     rdx, rdx
0x140009bbf  and     rdx, rax; DestinationSize
0x140009bc2  call    cs:__imp_memcpy_s
0x140009bc8  add     cs:Destination, rsi
0x140009bcf  jmp     short loc_140009BE2
0x140009bd1  neg     ebx
0x140009bd3  sbb     eax, eax
0x140009bd5  and     eax, 83Ah
0x140009bda  add     eax, 0FFFFF7C1h
0x140009bdf  lock and [rdi], eax
0x140009be2  lea     rcx, SRWLock; SRWLock
0x140009be9  call    cs:__imp_ReleaseSRWLockExclusive
0x140009bef  mov     rbx, [rsp+38h+arg_0]
0x140009bf4  mov     rsi, [rsp+38h+arg_8]
0x140009bf9  add     rsp, 30h
0x140009bfd  pop     rdi
0x140009bfe  retn
```
