# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000a88c`
- end: `0x14000a990`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004f24`
- `0x1400050f8`
- `0x14000526c`
- `0x1400053e0`
- `0x140005554`
- `0x140005634`
- `0x140005714`
- `0x1400057f4`
- `0x1400075d0`

## callees

- `0x1400020b2`
- `0x140002168`
- `0x14000a88c`
- `0x14000b92c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a91d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a947`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a91d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a947`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a97a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a97a`

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
      || a3 != dword_14001937C
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1400193A0, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1400193B0 - (_QWORD)qword_1400193A8) & -(__int64)((unsigned __int64)qword_1400193A8 < qword_1400193B0);
    if ( qword_1400193A8 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1400193A8 = v12;
LABEL_11:
        qword_1400193A8 = (char *)qword_1400193A8 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1400193A8, 0, v8);
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
0x14000a88c  mov     [rsp+arg_0], rbx
0x14000a891  mov     [rsp+arg_8], rsi
0x14000a896  push    rdi
0x14000a897  sub     rsp, 30h
0x14000a89b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000a8a1  mov     esi, r8d
0x14000a8a4  mov     ebx, edx
0x14000a8a6  mov     rdi, rcx
0x14000a8a9  test    eax, eax
0x14000a8ab  jz      loc_14000A980
0x14000a8b1  lea     rcx, SRWLock; SRWLock
0x14000a8b8  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8be  mov     eax, cs:dword_14001937C
0x14000a8c4  test    esi, esi
0x14000a8c6  jz      loc_14000A962
0x14000a8cc  cmp     esi, eax
0x14000a8ce  jnz     loc_14000A962
0x14000a8d4  mov     edx, 10h; unsigned __int64
0x14000a8d9  mov     dword ptr [rsp+38h+var_18+4], 0
0x14000a8e1  lea     rcx, qword_1400193A0; this
0x14000a8e8  mov     dword ptr [rsp+38h+var_18], ebx
0x14000a8ec  mov     qword ptr [rsp+38h+var_18+8], rdi
0x14000a8f1  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000a8f6  test    al, al
0x14000a8f8  jz      short loc_14000A962
0x14000a8fa  mov     r9, cs:qword_1400193A8
0x14000a901  mov     rax, cs:qword_1400193B0
0x14000a908  sub     rax, r9
0x14000a90b  cmp     r9, cs:qword_1400193B0
0x14000a912  sbb     r8, r8
0x14000a915  and     r8, rax; Size
0x14000a918  test    r9, r9
0x14000a91b  jnz     short loc_14000A92B
0x14000a91d  call    cs:__imp__o__errno
0x14000a923  mov     dword ptr [rax], 16h
0x14000a929  jmp     short loc_14000A953
0x14000a92b  cmp     r8, 10h
0x14000a92f  jb      short loc_14000A93D
0x14000a931  movups  xmm0, [rsp+38h+var_18]
0x14000a936  movdqu  xmmword ptr [r9], xmm0
0x14000a93b  jmp     short loc_14000A958
0x14000a93d  xor     edx, edx; Val
0x14000a93f  mov     rcx, r9; void *
0x14000a942  call    memset_0
0x14000a947  call    cs:__imp__o__errno
0x14000a94d  mov     dword ptr [rax], 22h ; '"'
0x14000a953  call    _invalid_parameter_noinfo
0x14000a958  add     cs:qword_1400193A8, 10h
0x14000a960  jmp     short loc_14000A973
0x14000a962  neg     ebx
0x14000a964  sbb     eax, eax
0x14000a966  and     eax, 83Ah
0x14000a96b  add     eax, 0FFFFF7C1h
0x14000a970  lock and [rdi], eax
0x14000a973  lea     rcx, SRWLock; SRWLock
0x14000a97a  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a980  mov     rbx, [rsp+38h+arg_0]
0x14000a985  mov     rsi, [rsp+38h+arg_8]
0x14000a98a  add     rsp, 30h
0x14000a98e  pop     rdi
0x14000a98f  retn
```
