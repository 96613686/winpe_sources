# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180010684`
- end: `0x18001074f`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007df0`
- `0x180007ed0`
- `0x180007fb0`
- `0x180008090`
- `0x180008170`
- `0x180008250`
- `0x180008330`
- `0x180008410`
- `0x180008584`
- `0x1800086f8`
- `0x18000886c`
- `0x18000ba78`

## callees

- `0x180010684`
- `0x180011eec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010712`
- `msvcrt!memcpy_s` at `0x180010712`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800106b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800106b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180010739`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180010739`

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
      && a3 == dword_180023724
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&unk_180023748, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180023758 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180023758),
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
0x180010684  mov     [rsp+arg_0], rbx
0x180010689  mov     [rsp+arg_8], rsi
0x18001068e  push    rdi
0x18001068f  sub     rsp, 30h
0x180010693  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010699  mov     esi, r8d
0x18001069c  mov     ebx, edx
0x18001069e  mov     rdi, rcx
0x1800106a1  test    eax, eax
0x1800106a3  jz      loc_18001073F
0x1800106a9  lea     rcx, SRWLock; SRWLock
0x1800106b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800106b6  mov     eax, cs:dword_180023724
0x1800106bc  test    esi, esi
0x1800106be  jz      short loc_180010721
0x1800106c0  cmp     esi, eax
0x1800106c2  jnz     short loc_180010721
0x1800106c4  mov     esi, 10h
0x1800106c9  mov     [rsp+38h+var_14], 0
0x1800106d1  mov     edx, esi; unsigned __int64
0x1800106d3  mov     [rsp+38h+Source], ebx
0x1800106d7  lea     rcx, unk_180023748; this
0x1800106de  mov     [rsp+38h+var_10], rdi
0x1800106e3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800106e8  test    al, al
0x1800106ea  jz      short loc_180010721
0x1800106ec  mov     rcx, cs:Destination; Destination
0x1800106f3  lea     r8, [rsp+38h+Source]; Source
0x1800106f8  mov     rax, cs:qword_180023758
0x1800106ff  mov     r9d, esi; SourceSize
0x180010702  sub     rax, rcx
0x180010705  cmp     rcx, cs:qword_180023758
0x18001070c  sbb     rdx, rdx
0x18001070f  and     rdx, rax; DestinationSize
0x180010712  call    cs:__imp_memcpy_s
0x180010718  add     cs:Destination, rsi
0x18001071f  jmp     short loc_180010732
0x180010721  neg     ebx
0x180010723  sbb     eax, eax
0x180010725  and     eax, 83Ah
0x18001072a  add     eax, 0FFFFF7C1h
0x18001072f  lock and [rdi], eax
0x180010732  lea     rcx, SRWLock; SRWLock
0x180010739  call    cs:__imp_ReleaseSRWLockExclusive
0x18001073f  mov     rbx, [rsp+38h+arg_0]
0x180010744  mov     rsi, [rsp+38h+arg_8]
0x180010749  add     rsp, 30h
0x18001074d  pop     rdi
0x18001074e  retn
```
