# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800112b0`
- end: `0x1800113b4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000de7c`
- `0x18001a0bc`

## callees

- `0x180005306`
- `0x180005374`
- `0x1800112b0`
- `0x1800122d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011341`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001136b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011341`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001136b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001139e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001139e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800112dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800112dc`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int128 v12; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180042914
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180042938, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180042948 - (_QWORD)qword_180042940) & -(__int64)((unsigned __int64)qword_180042940 < qword_180042948);
    if ( qword_180042940 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180042940 = v12;
LABEL_11:
        qword_180042940 = (char *)qword_180042940 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180042940, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x1800112b0  mov     [rsp+arg_0], rbx
0x1800112b5  mov     [rsp+arg_8], rsi
0x1800112ba  push    rdi
0x1800112bb  sub     rsp, 30h
0x1800112bf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800112c5  mov     esi, r8d
0x1800112c8  mov     ebx, edx
0x1800112ca  mov     rdi, rcx
0x1800112cd  test    eax, eax
0x1800112cf  jz      loc_1800113A4
0x1800112d5  lea     rcx, SRWLock; SRWLock
0x1800112dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800112e2  mov     eax, cs:dword_180042914
0x1800112e8  test    esi, esi
0x1800112ea  jz      loc_180011386
0x1800112f0  cmp     esi, eax
0x1800112f2  jnz     loc_180011386
0x1800112f8  mov     edx, 10h; unsigned __int64
0x1800112fd  mov     dword ptr [rsp+38h+var_18+4], 0
0x180011305  lea     rcx, qword_180042938; this
0x18001130c  mov     dword ptr [rsp+38h+var_18], ebx
0x180011310  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180011315  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001131a  test    al, al
0x18001131c  jz      short loc_180011386
0x18001131e  mov     r9, cs:qword_180042940
0x180011325  mov     rax, cs:qword_180042948
0x18001132c  sub     rax, r9
0x18001132f  cmp     r9, cs:qword_180042948
0x180011336  sbb     r8, r8
0x180011339  and     r8, rax; Size
0x18001133c  test    r9, r9
0x18001133f  jnz     short loc_18001134F
0x180011341  call    cs:__imp__o__errno
0x180011347  mov     dword ptr [rax], 16h
0x18001134d  jmp     short loc_180011377
0x18001134f  cmp     r8, 10h
0x180011353  jb      short loc_180011361
0x180011355  movups  xmm0, [rsp+38h+var_18]
0x18001135a  movdqu  xmmword ptr [r9], xmm0
0x18001135f  jmp     short loc_18001137C
0x180011361  xor     edx, edx; Val
0x180011363  mov     rcx, r9; void *
0x180011366  call    memset_0
0x18001136b  call    cs:__imp__o__errno
0x180011371  mov     dword ptr [rax], 22h ; '"'
0x180011377  call    _invalid_parameter_noinfo
0x18001137c  add     cs:qword_180042940, 10h
0x180011384  jmp     short loc_180011397
0x180011386  neg     ebx
0x180011388  sbb     eax, eax
0x18001138a  and     eax, 83Ah
0x18001138f  add     eax, 0FFFFF7C1h
0x180011394  lock and [rdi], eax
0x180011397  lea     rcx, SRWLock; SRWLock
0x18001139e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800113a4  mov     rbx, [rsp+38h+arg_0]
0x1800113a9  mov     rsi, [rsp+38h+arg_8]
0x1800113ae  add     rsp, 30h
0x1800113b2  pop     rdi
0x1800113b3  retn
```
