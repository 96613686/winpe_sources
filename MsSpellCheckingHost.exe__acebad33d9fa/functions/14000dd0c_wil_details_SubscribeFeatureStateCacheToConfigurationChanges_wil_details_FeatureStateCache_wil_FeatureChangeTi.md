# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000dd0c`
- end: `0x14000ddd7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b4cc`

## callees

- `0x14000dd0c`
- `0x14000f454`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000dd9a`
- `msvcrt!memcpy_s` at `0x14000dd9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000dd38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000dd38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ddc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ddc1`

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
      && a3 == dword_14001B714
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_14001B738, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_14001B748 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_14001B748),
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
0x14000dd0c  mov     [rsp+arg_0], rbx
0x14000dd11  mov     [rsp+arg_8], rsi
0x14000dd16  push    rdi
0x14000dd17  sub     rsp, 30h
0x14000dd1b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000dd21  mov     esi, r8d
0x14000dd24  mov     ebx, edx
0x14000dd26  mov     rdi, rcx
0x14000dd29  test    eax, eax
0x14000dd2b  jz      loc_14000DDC7
0x14000dd31  lea     rcx, SRWLock; SRWLock
0x14000dd38  call    cs:__imp_AcquireSRWLockExclusive
0x14000dd3e  mov     eax, cs:dword_14001B714
0x14000dd44  test    esi, esi
0x14000dd46  jz      short loc_14000DDA9
0x14000dd48  cmp     esi, eax
0x14000dd4a  jnz     short loc_14000DDA9
0x14000dd4c  mov     esi, 10h
0x14000dd51  mov     [rsp+38h+var_14], 0
0x14000dd59  mov     edx, esi; unsigned __int64
0x14000dd5b  mov     [rsp+38h+Source], ebx
0x14000dd5f  lea     rcx, qword_14001B738; this
0x14000dd66  mov     [rsp+38h+var_10], rdi
0x14000dd6b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000dd70  test    al, al
0x14000dd72  jz      short loc_14000DDA9
0x14000dd74  mov     rcx, cs:Destination; Destination
0x14000dd7b  lea     r8, [rsp+38h+Source]; Source
0x14000dd80  mov     rax, cs:qword_14001B748
0x14000dd87  mov     r9d, esi; SourceSize
0x14000dd8a  sub     rax, rcx
0x14000dd8d  cmp     rcx, cs:qword_14001B748
0x14000dd94  sbb     rdx, rdx
0x14000dd97  and     rdx, rax; DestinationSize
0x14000dd9a  call    cs:__imp_memcpy_s
0x14000dda0  add     cs:Destination, rsi
0x14000dda7  jmp     short loc_14000DDBA
0x14000dda9  neg     ebx
0x14000ddab  sbb     eax, eax
0x14000ddad  and     eax, 83Ah
0x14000ddb2  add     eax, 0FFFFF7C1h
0x14000ddb7  lock and [rdi], eax
0x14000ddba  lea     rcx, SRWLock; SRWLock
0x14000ddc1  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ddc7  mov     rbx, [rsp+38h+arg_0]
0x14000ddcc  mov     rsi, [rsp+38h+arg_8]
0x14000ddd1  add     rsp, 30h
0x14000ddd5  pop     rdi
0x14000ddd6  retn
```
