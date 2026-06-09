# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180007058`
- end: `0x180007123`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004e10`

## callees

- `0x180007058`
- `0x180007cdc`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800070e6`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800070e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000710d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000710d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007084`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007084`

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
      && a3 == dword_18001225C
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180012280, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180012290 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180012290),
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
0x180007058  mov     [rsp+arg_0], rbx
0x18000705d  mov     [rsp+arg_8], rsi
0x180007062  push    rdi
0x180007063  sub     rsp, 30h
0x180007067  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000706d  mov     esi, r8d
0x180007070  mov     ebx, edx
0x180007072  mov     rdi, rcx
0x180007075  test    eax, eax
0x180007077  jz      loc_180007113
0x18000707d  lea     rcx, SRWLock; SRWLock
0x180007084  call    cs:__imp_AcquireSRWLockExclusive
0x18000708a  mov     eax, cs:dword_18001225C
0x180007090  test    esi, esi
0x180007092  jz      short loc_1800070F5
0x180007094  cmp     esi, eax
0x180007096  jnz     short loc_1800070F5
0x180007098  mov     esi, 10h
0x18000709d  mov     [rsp+38h+var_14], 0
0x1800070a5  mov     edx, esi; unsigned __int64
0x1800070a7  mov     [rsp+38h+Source], ebx
0x1800070ab  lea     rcx, qword_180012280; this
0x1800070b2  mov     [rsp+38h+var_10], rdi
0x1800070b7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800070bc  test    al, al
0x1800070be  jz      short loc_1800070F5
0x1800070c0  mov     rcx, cs:Destination; Destination
0x1800070c7  lea     r8, [rsp+38h+Source]; Source
0x1800070cc  mov     rax, cs:qword_180012290
0x1800070d3  mov     r9d, esi; SourceSize
0x1800070d6  sub     rax, rcx
0x1800070d9  cmp     rcx, cs:qword_180012290
0x1800070e0  sbb     rdx, rdx
0x1800070e3  and     rdx, rax; DestinationSize
0x1800070e6  call    cs:__imp_memcpy_s
0x1800070ec  add     cs:Destination, rsi
0x1800070f3  jmp     short loc_180007106
0x1800070f5  neg     ebx
0x1800070f7  sbb     eax, eax
0x1800070f9  and     eax, 83Ah
0x1800070fe  add     eax, 0FFFFF7C1h
0x180007103  lock and [rdi], eax
0x180007106  lea     rcx, SRWLock; SRWLock
0x18000710d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007113  mov     rbx, [rsp+38h+arg_0]
0x180007118  mov     rsi, [rsp+38h+arg_8]
0x18000711d  add     rsp, 30h
0x180007121  pop     rdi
0x180007122  retn
```
