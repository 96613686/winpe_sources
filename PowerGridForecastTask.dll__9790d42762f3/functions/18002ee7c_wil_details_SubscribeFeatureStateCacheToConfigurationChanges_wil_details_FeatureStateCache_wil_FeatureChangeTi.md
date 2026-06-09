# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18002ee7c`
- end: `0x18002ef47`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002a464`
- `0x18002b258`

## callees

- `0x18002ee7c`
- `0x1800302f4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002ef0a`
- `msvcrt!memcpy_s` at `0x18002ef0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ef31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ef31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002eea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002eea8`

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
      && a3 == dword_180046454
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180046478, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180046488 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180046488),
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
0x18002ee7c  mov     [rsp+arg_0], rbx
0x18002ee81  mov     [rsp+arg_8], rsi
0x18002ee86  push    rdi
0x18002ee87  sub     rsp, 30h
0x18002ee8b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ee91  mov     esi, r8d
0x18002ee94  mov     ebx, edx
0x18002ee96  mov     rdi, rcx
0x18002ee99  test    eax, eax
0x18002ee9b  jz      loc_18002EF37
0x18002eea1  lea     rcx, SRWLock; SRWLock
0x18002eea8  call    cs:__imp_AcquireSRWLockExclusive
0x18002eeae  mov     eax, cs:dword_180046454
0x18002eeb4  test    esi, esi
0x18002eeb6  jz      short loc_18002EF19
0x18002eeb8  cmp     esi, eax
0x18002eeba  jnz     short loc_18002EF19
0x18002eebc  mov     esi, 10h
0x18002eec1  mov     [rsp+38h+var_14], 0
0x18002eec9  mov     edx, esi; unsigned __int64
0x18002eecb  mov     [rsp+38h+Source], ebx
0x18002eecf  lea     rcx, qword_180046478; this
0x18002eed6  mov     [rsp+38h+var_10], rdi
0x18002eedb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002eee0  test    al, al
0x18002eee2  jz      short loc_18002EF19
0x18002eee4  mov     rcx, cs:Destination; Destination
0x18002eeeb  lea     r8, [rsp+38h+Source]; Source
0x18002eef0  mov     rax, cs:qword_180046488
0x18002eef7  mov     r9d, esi; SourceSize
0x18002eefa  sub     rax, rcx
0x18002eefd  cmp     rcx, cs:qword_180046488
0x18002ef04  sbb     rdx, rdx
0x18002ef07  and     rdx, rax; DestinationSize
0x18002ef0a  call    cs:__imp_memcpy_s
0x18002ef10  add     cs:Destination, rsi
0x18002ef17  jmp     short loc_18002EF2A
0x18002ef19  neg     ebx
0x18002ef1b  sbb     eax, eax
0x18002ef1d  and     eax, 83Ah
0x18002ef22  add     eax, 0FFFFF7C1h
0x18002ef27  lock and [rdi], eax
0x18002ef2a  lea     rcx, SRWLock; SRWLock
0x18002ef31  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ef37  mov     rbx, [rsp+38h+arg_0]
0x18002ef3c  mov     rsi, [rsp+38h+arg_8]
0x18002ef41  add     rsp, 30h
0x18002ef45  pop     rdi
0x18002ef46  retn
```
