# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008540`
- end: `0x18000861e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008540`
- `0x18000971c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800085d4`
- `msvcrt!memcpy_s` at `0x1800085d4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008601`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008601`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000856c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000856c`

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
      && a3 == dword_180050E44
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180050E78, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180050E88 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180050E88),
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
0x180008540  mov     [rsp+arg_0], rbx
0x180008545  mov     [rsp+arg_8], rsi
0x18000854a  push    rdi
0x18000854b  sub     rsp, 30h
0x18000854f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008555  mov     esi, r8d
0x180008558  mov     ebx, edx
0x18000855a  mov     rdi, rcx
0x18000855d  test    eax, eax
0x18000855f  jz      loc_18000860D
0x180008565  lea     rcx, SRWLock; SRWLock
0x18000856c  call    cs:__imp_AcquireSRWLockExclusive
0x180008573  nop     dword ptr [rax+rax+00h]
0x180008578  mov     eax, cs:dword_180050E44
0x18000857e  test    esi, esi
0x180008580  jz      short loc_1800085E9
0x180008582  cmp     esi, eax
0x180008584  jnz     short loc_1800085E9
0x180008586  mov     esi, 10h
0x18000858b  mov     [rsp+38h+var_14], 0
0x180008593  mov     edx, esi; unsigned __int64
0x180008595  mov     [rsp+38h+Source], ebx
0x180008599  lea     rcx, qword_180050E78; this
0x1800085a0  mov     [rsp+38h+var_10], rdi
0x1800085a5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800085aa  test    al, al
0x1800085ac  jz      short loc_1800085E9
0x1800085ae  mov     rcx, cs:Destination; Destination
0x1800085b5  lea     r8, [rsp+38h+Source]; Source
0x1800085ba  mov     rax, cs:qword_180050E88
0x1800085c1  mov     r9d, esi; SourceSize
0x1800085c4  sub     rax, rcx
0x1800085c7  cmp     rcx, cs:qword_180050E88
0x1800085ce  sbb     rdx, rdx
0x1800085d1  and     rdx, rax; DestinationSize
0x1800085d4  call    cs:__imp_memcpy_s
0x1800085db  nop     dword ptr [rax+rax+00h]
0x1800085e0  add     cs:Destination, rsi
0x1800085e7  jmp     short loc_1800085FA
0x1800085e9  neg     ebx
0x1800085eb  sbb     eax, eax
0x1800085ed  and     eax, 83Ah
0x1800085f2  add     eax, 0FFFFF7C1h
0x1800085f7  lock and [rdi], eax
0x1800085fa  lea     rcx, SRWLock; SRWLock
0x180008601  call    cs:__imp_ReleaseSRWLockExclusive
0x180008608  nop     dword ptr [rax+rax+00h]
0x18000860d  mov     rbx, [rsp+38h+arg_0]
0x180008612  mov     rsi, [rsp+38h+arg_8]
0x180008617  add     rsp, 30h
0x18000861b  pop     rdi
0x18000861c  retn
```
