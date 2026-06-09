# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b7bc`
- end: `0x18000b8c0`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `46`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007240`
- `0x1800073bc`
- `0x180007538`
- `0x1800083e4`
- `0x180015330`
- `0x180015410`
- `0x1800155e4`
- `0x1800156c4`
- `0x1800157a4`
- `0x180015924`
- `0x180015aec`
- `0x180015cb4`
- `0x180015e7c`
- `0x180016044`
- `0x18001620c`
- `0x1800162f0`
- `0x1800164b8`
- `0x18001659c`
- `0x18001667c`
- `0x180016844`
- `0x180016928`
- `0x180016a0c`
- `0x180016aec`
- `0x180016bd0`
- `0x180016cb4`
- `0x180016d94`
- `0x180016e74`
- `0x180016f54`
- `0x1800170d4`
- `0x180017248`
- `0x1800173bc`
- `0x180017530`
- `0x1800176a4`
- `0x180017818`
- `0x18001798c`
- `0x180017b00`
- `0x180017c74`
- `0x180017d54`
- `0x180017e34`
- `0x180017f14`
- `0x1800180e8`
- `0x180018268`
- `0x1800183e8`
- `0x1800184c8`
- `0x180018648`
- `0x180029fd0`

## callees

- `0x180002f3a`
- `0x180002f98`
- `0x18000b7bc`
- `0x18000c6e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b84d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b877`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b84d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b877`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8aa`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rcx
  size_t v7; // r8
  __int64 v8; // rcx
  __int128 v9; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180041804
      || (*(_QWORD *)&v9 = a2,
          *((_QWORD *)&v9 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180041828, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v7 = (qword_180041838 - (_QWORD)qword_180041830) & -(__int64)((unsigned __int64)qword_180041830 < qword_180041838);
    if ( qword_180041830 )
    {
      if ( v7 >= 0x10 )
      {
        *(_OWORD *)qword_180041830 = v9;
LABEL_11:
        qword_180041830 = (char *)qword_180041830 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180041830, 0, v7);
      *(_DWORD *)_o__errno(v8) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v6) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x18000b7bc  mov     [rsp+arg_0], rbx
0x18000b7c1  mov     [rsp+arg_8], rsi
0x18000b7c6  push    rdi
0x18000b7c7  sub     rsp, 30h
0x18000b7cb  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b7d1  mov     esi, r8d
0x18000b7d4  mov     ebx, edx
0x18000b7d6  mov     rdi, rcx
0x18000b7d9  test    eax, eax
0x18000b7db  jz      loc_18000B8B0
0x18000b7e1  lea     rcx, SRWLock; SRWLock
0x18000b7e8  call    cs:__imp_AcquireSRWLockExclusive
0x18000b7ee  mov     eax, cs:dword_180041804
0x18000b7f4  test    esi, esi
0x18000b7f6  jz      loc_18000B892
0x18000b7fc  cmp     esi, eax
0x18000b7fe  jnz     loc_18000B892
0x18000b804  mov     edx, 10h; unsigned __int64
0x18000b809  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000b811  lea     rcx, qword_180041828; this
0x18000b818  mov     dword ptr [rsp+38h+var_18], ebx
0x18000b81c  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000b821  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b826  test    al, al
0x18000b828  jz      short loc_18000B892
0x18000b82a  mov     r9, cs:qword_180041830
0x18000b831  mov     rax, cs:qword_180041838
0x18000b838  sub     rax, r9
0x18000b83b  cmp     r9, cs:qword_180041838
0x18000b842  sbb     r8, r8
0x18000b845  and     r8, rax; Size
0x18000b848  test    r9, r9
0x18000b84b  jnz     short loc_18000B85B
0x18000b84d  call    cs:__imp__o__errno
0x18000b853  mov     dword ptr [rax], 16h
0x18000b859  jmp     short loc_18000B883
0x18000b85b  cmp     r8, 10h
0x18000b85f  jb      short loc_18000B86D
0x18000b861  movups  xmm0, [rsp+38h+var_18]
0x18000b866  movdqu  xmmword ptr [r9], xmm0
0x18000b86b  jmp     short loc_18000B888
0x18000b86d  xor     edx, edx; Val
0x18000b86f  mov     rcx, r9; void *
0x18000b872  call    memset_0
0x18000b877  call    cs:__imp__o__errno
0x18000b87d  mov     dword ptr [rax], 22h ; '"'
0x18000b883  call    _invalid_parameter_noinfo
0x18000b888  add     cs:qword_180041830, 10h
0x18000b890  jmp     short loc_18000B8A3
0x18000b892  neg     ebx
0x18000b894  sbb     eax, eax
0x18000b896  and     eax, 83Ah
0x18000b89b  add     eax, 0FFFFF7C1h
0x18000b8a0  lock and [rdi], eax
0x18000b8a3  lea     rcx, SRWLock; SRWLock
0x18000b8aa  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8b0  mov     rbx, [rsp+38h+arg_0]
0x18000b8b5  mov     rsi, [rsp+38h+arg_8]
0x18000b8ba  add     rsp, 30h
0x18000b8be  pop     rdi
0x18000b8bf  retn
```
