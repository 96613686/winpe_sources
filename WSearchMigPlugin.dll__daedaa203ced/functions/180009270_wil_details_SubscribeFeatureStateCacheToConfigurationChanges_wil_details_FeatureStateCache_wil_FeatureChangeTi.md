# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009270`
- end: `0x180009374`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006a34`
- `0x18000e1cc`
- `0x18000e3a0`
- `0x18000e514`
- `0x18000e688`
- `0x18000e7fc`
- `0x18000e970`
- `0x18000eae4`
- `0x18000ebc4`
- `0x18000eca4`
- `0x18000ed84`
- `0x18000ee64`
- `0x18000ef44`

## callees

- `0x18000321a`
- `0x18000329c`
- `0x180009270`
- `0x18000a05c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009301`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000932b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009301`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000932b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000929c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000929c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000935e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000935e`

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
      || a3 != dword_180025B54
      || (*(_QWORD *)&v9 = a2,
          *((_QWORD *)&v9 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180025B78, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v7 = (qword_180025B88 - (_QWORD)qword_180025B80) & -(__int64)((unsigned __int64)qword_180025B80 < qword_180025B88);
    if ( qword_180025B80 )
    {
      if ( v7 >= 0x10 )
      {
        *(_OWORD *)qword_180025B80 = v9;
LABEL_11:
        qword_180025B80 = (char *)qword_180025B80 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180025B80, 0, v7);
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
0x180009270  mov     [rsp+arg_0], rbx
0x180009275  mov     [rsp+arg_8], rsi
0x18000927a  push    rdi
0x18000927b  sub     rsp, 30h
0x18000927f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009285  mov     esi, r8d
0x180009288  mov     ebx, edx
0x18000928a  mov     rdi, rcx
0x18000928d  test    eax, eax
0x18000928f  jz      loc_180009364
0x180009295  lea     rcx, SRWLock; SRWLock
0x18000929c  call    cs:__imp_AcquireSRWLockExclusive
0x1800092a2  mov     eax, cs:dword_180025B54
0x1800092a8  test    esi, esi
0x1800092aa  jz      loc_180009346
0x1800092b0  cmp     esi, eax
0x1800092b2  jnz     loc_180009346
0x1800092b8  mov     edx, 10h; unsigned __int64
0x1800092bd  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800092c5  lea     rcx, qword_180025B78; this
0x1800092cc  mov     dword ptr [rsp+38h+var_18], ebx
0x1800092d0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800092d5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800092da  test    al, al
0x1800092dc  jz      short loc_180009346
0x1800092de  mov     r9, cs:qword_180025B80
0x1800092e5  mov     rax, cs:qword_180025B88
0x1800092ec  sub     rax, r9
0x1800092ef  cmp     r9, cs:qword_180025B88
0x1800092f6  sbb     r8, r8
0x1800092f9  and     r8, rax; Size
0x1800092fc  test    r9, r9
0x1800092ff  jnz     short loc_18000930F
0x180009301  call    cs:__imp__o__errno
0x180009307  mov     dword ptr [rax], 16h
0x18000930d  jmp     short loc_180009337
0x18000930f  cmp     r8, 10h
0x180009313  jb      short loc_180009321
0x180009315  movups  xmm0, [rsp+38h+var_18]
0x18000931a  movdqu  xmmword ptr [r9], xmm0
0x18000931f  jmp     short loc_18000933C
0x180009321  xor     edx, edx; Val
0x180009323  mov     rcx, r9; void *
0x180009326  call    memset_0
0x18000932b  call    cs:__imp__o__errno
0x180009331  mov     dword ptr [rax], 22h ; '"'
0x180009337  call    _invalid_parameter_noinfo
0x18000933c  add     cs:qword_180025B80, 10h
0x180009344  jmp     short loc_180009357
0x180009346  neg     ebx
0x180009348  sbb     eax, eax
0x18000934a  and     eax, 83Ah
0x18000934f  add     eax, 0FFFFF7C1h
0x180009354  lock and [rdi], eax
0x180009357  lea     rcx, SRWLock; SRWLock
0x18000935e  call    cs:__imp_ReleaseSRWLockExclusive
0x180009364  mov     rbx, [rsp+38h+arg_0]
0x180009369  mov     rsi, [rsp+38h+arg_8]
0x18000936e  add     rsp, 30h
0x180009372  pop     rdi
0x180009373  retn
```
