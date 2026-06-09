# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140007e64`
- end: `0x140007f68`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005674`
- `0x14000a514`
- `0x14000a694`
- `0x14000a864`

## callees

- `0x14000216a`
- `0x14000221c`
- `0x140007e64`
- `0x140008c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007ef5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f1f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007ef5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007e90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007e90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007f52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007f52`

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
      || a3 != dword_14001169C
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1400116C0, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1400116D0 - (_QWORD)qword_1400116C8) & -(__int64)((unsigned __int64)qword_1400116C8 < qword_1400116D0);
    if ( qword_1400116C8 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1400116C8 = v12;
LABEL_11:
        qword_1400116C8 = (char *)qword_1400116C8 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1400116C8, 0, v8);
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
0x140007e64  mov     [rsp+arg_0], rbx
0x140007e69  mov     [rsp+arg_8], rsi
0x140007e6e  push    rdi
0x140007e6f  sub     rsp, 30h
0x140007e73  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140007e79  mov     esi, r8d
0x140007e7c  mov     ebx, edx
0x140007e7e  mov     rdi, rcx
0x140007e81  test    eax, eax
0x140007e83  jz      loc_140007F58
0x140007e89  lea     rcx, SRWLock; SRWLock
0x140007e90  call    cs:__imp_AcquireSRWLockExclusive
0x140007e96  mov     eax, cs:dword_14001169C
0x140007e9c  test    esi, esi
0x140007e9e  jz      loc_140007F3A
0x140007ea4  cmp     esi, eax
0x140007ea6  jnz     loc_140007F3A
0x140007eac  mov     edx, 10h; unsigned __int64
0x140007eb1  mov     dword ptr [rsp+38h+var_18+4], 0
0x140007eb9  lea     rcx, qword_1400116C0; this
0x140007ec0  mov     dword ptr [rsp+38h+var_18], ebx
0x140007ec4  mov     qword ptr [rsp+38h+var_18+8], rdi
0x140007ec9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007ece  test    al, al
0x140007ed0  jz      short loc_140007F3A
0x140007ed2  mov     r9, cs:qword_1400116C8
0x140007ed9  mov     rax, cs:qword_1400116D0
0x140007ee0  sub     rax, r9
0x140007ee3  cmp     r9, cs:qword_1400116D0
0x140007eea  sbb     r8, r8
0x140007eed  and     r8, rax; Size
0x140007ef0  test    r9, r9
0x140007ef3  jnz     short loc_140007F03
0x140007ef5  call    cs:__imp__o__errno
0x140007efb  mov     dword ptr [rax], 16h
0x140007f01  jmp     short loc_140007F2B
0x140007f03  cmp     r8, 10h
0x140007f07  jb      short loc_140007F15
0x140007f09  movups  xmm0, [rsp+38h+var_18]
0x140007f0e  movdqu  xmmword ptr [r9], xmm0
0x140007f13  jmp     short loc_140007F30
0x140007f15  xor     edx, edx; Val
0x140007f17  mov     rcx, r9; void *
0x140007f1a  call    memset_0
0x140007f1f  call    cs:__imp__o__errno
0x140007f25  mov     dword ptr [rax], 22h ; '"'
0x140007f2b  call    _invalid_parameter_noinfo
0x140007f30  add     cs:qword_1400116C8, 10h
0x140007f38  jmp     short loc_140007F4B
0x140007f3a  neg     ebx
0x140007f3c  sbb     eax, eax
0x140007f3e  and     eax, 83Ah
0x140007f43  add     eax, 0FFFFF7C1h
0x140007f48  lock and [rdi], eax
0x140007f4b  lea     rcx, SRWLock; SRWLock
0x140007f52  call    cs:__imp_ReleaseSRWLockExclusive
0x140007f58  mov     rbx, [rsp+38h+arg_0]
0x140007f5d  mov     rsi, [rsp+38h+arg_8]
0x140007f62  add     rsp, 30h
0x140007f66  pop     rdi
0x140007f67  retn
```
