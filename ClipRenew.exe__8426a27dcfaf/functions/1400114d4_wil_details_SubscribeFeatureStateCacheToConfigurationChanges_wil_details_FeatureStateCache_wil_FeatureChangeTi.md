# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1400114d4`
- end: `0x14001159f`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007140`
- `0x140007304`
- `0x1400074c0`
- `0x140007684`
- `0x140007ce4`

## callees

- `0x1400114d4`
- `0x140011fcc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140011562`
- `msvcrt!memcpy_s` at `0x140011562`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011589`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140011589`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011500`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011500`

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
      && a3 == dword_1400193FC
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140019420, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_140019430 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_140019430),
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
0x1400114d4  mov     [rsp+arg_0], rbx
0x1400114d9  mov     [rsp+arg_8], rsi
0x1400114de  push    rdi
0x1400114df  sub     rsp, 30h
0x1400114e3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400114e9  mov     esi, r8d
0x1400114ec  mov     ebx, edx
0x1400114ee  mov     rdi, rcx
0x1400114f1  test    eax, eax
0x1400114f3  jz      loc_14001158F
0x1400114f9  lea     rcx, SRWLock; SRWLock
0x140011500  call    cs:__imp_AcquireSRWLockExclusive
0x140011506  mov     eax, cs:dword_1400193FC
0x14001150c  test    esi, esi
0x14001150e  jz      short loc_140011571
0x140011510  cmp     esi, eax
0x140011512  jnz     short loc_140011571
0x140011514  mov     esi, 10h
0x140011519  mov     [rsp+38h+var_14], 0
0x140011521  mov     edx, esi; unsigned __int64
0x140011523  mov     [rsp+38h+Source], ebx
0x140011527  lea     rcx, qword_140019420; this
0x14001152e  mov     [rsp+38h+var_10], rdi
0x140011533  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140011538  test    al, al
0x14001153a  jz      short loc_140011571
0x14001153c  mov     rcx, cs:Destination; Destination
0x140011543  lea     r8, [rsp+38h+Source]; Source
0x140011548  mov     rax, cs:qword_140019430
0x14001154f  mov     r9d, esi; SourceSize
0x140011552  sub     rax, rcx
0x140011555  cmp     rcx, cs:qword_140019430
0x14001155c  sbb     rdx, rdx
0x14001155f  and     rdx, rax; DestinationSize
0x140011562  call    cs:__imp_memcpy_s
0x140011568  add     cs:Destination, rsi
0x14001156f  jmp     short loc_140011582
0x140011571  neg     ebx
0x140011573  sbb     eax, eax
0x140011575  and     eax, 83Ah
0x14001157a  add     eax, 0FFFFF7C1h
0x14001157f  lock and [rdi], eax
0x140011582  lea     rcx, SRWLock; SRWLock
0x140011589  call    cs:__imp_ReleaseSRWLockExclusive
0x14001158f  mov     rbx, [rsp+38h+arg_0]
0x140011594  mov     rsi, [rsp+38h+arg_8]
0x140011599  add     rsp, 30h
0x14001159d  pop     rdi
0x14001159e  retn
```
