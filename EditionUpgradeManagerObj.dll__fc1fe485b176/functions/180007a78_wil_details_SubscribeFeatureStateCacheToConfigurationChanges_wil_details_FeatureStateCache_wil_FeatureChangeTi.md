# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180007a78`
- end: `0x180007b7c`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005834`
- `0x1800090fc`
- `0x180013a10`

## callees

- `0x180002652`
- `0x1800026b4`
- `0x180007a78`
- `0x18000877c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b09`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b09`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007b66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007b66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007aa4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007aa4`

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
      || a3 != dword_18002F71C
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18002F740, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18002F750 - (_QWORD)qword_18002F748) & -(__int64)((unsigned __int64)qword_18002F748 < qword_18002F750);
    if ( qword_18002F748 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18002F748 = v12;
LABEL_11:
        qword_18002F748 = (char *)qword_18002F748 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18002F748, 0, v8);
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
0x180007a78  mov     [rsp+arg_0], rbx
0x180007a7d  mov     [rsp+arg_8], rsi
0x180007a82  push    rdi
0x180007a83  sub     rsp, 30h
0x180007a87  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007a8d  mov     esi, r8d
0x180007a90  mov     ebx, edx
0x180007a92  mov     rdi, rcx
0x180007a95  test    eax, eax
0x180007a97  jz      loc_180007B6C
0x180007a9d  lea     rcx, SRWLock; SRWLock
0x180007aa4  call    cs:__imp_AcquireSRWLockExclusive
0x180007aaa  mov     eax, cs:dword_18002F71C
0x180007ab0  test    esi, esi
0x180007ab2  jz      loc_180007B4E
0x180007ab8  cmp     esi, eax
0x180007aba  jnz     loc_180007B4E
0x180007ac0  mov     edx, 10h; unsigned __int64
0x180007ac5  mov     dword ptr [rsp+38h+var_18+4], 0
0x180007acd  lea     rcx, qword_18002F740; this
0x180007ad4  mov     dword ptr [rsp+38h+var_18], ebx
0x180007ad8  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180007add  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007ae2  test    al, al
0x180007ae4  jz      short loc_180007B4E
0x180007ae6  mov     r9, cs:qword_18002F748
0x180007aed  mov     rax, cs:qword_18002F750
0x180007af4  sub     rax, r9
0x180007af7  cmp     r9, cs:qword_18002F750
0x180007afe  sbb     r8, r8
0x180007b01  and     r8, rax; Size
0x180007b04  test    r9, r9
0x180007b07  jnz     short loc_180007B17
0x180007b09  call    cs:__imp__o__errno
0x180007b0f  mov     dword ptr [rax], 16h
0x180007b15  jmp     short loc_180007B3F
0x180007b17  cmp     r8, 10h
0x180007b1b  jb      short loc_180007B29
0x180007b1d  movups  xmm0, [rsp+38h+var_18]
0x180007b22  movdqu  xmmword ptr [r9], xmm0
0x180007b27  jmp     short loc_180007B44
0x180007b29  xor     edx, edx; Val
0x180007b2b  mov     rcx, r9; void *
0x180007b2e  call    memset_0
0x180007b33  call    cs:__imp__o__errno
0x180007b39  mov     dword ptr [rax], 22h ; '"'
0x180007b3f  call    _invalid_parameter_noinfo
0x180007b44  add     cs:qword_18002F748, 10h
0x180007b4c  jmp     short loc_180007B5F
0x180007b4e  neg     ebx
0x180007b50  sbb     eax, eax
0x180007b52  and     eax, 83Ah
0x180007b57  add     eax, 0FFFFF7C1h
0x180007b5c  lock and [rdi], eax
0x180007b5f  lea     rcx, SRWLock; SRWLock
0x180007b66  call    cs:__imp_ReleaseSRWLockExclusive
0x180007b6c  mov     rbx, [rsp+38h+arg_0]
0x180007b71  mov     rsi, [rsp+38h+arg_8]
0x180007b76  add     rsp, 30h
0x180007b7a  pop     rdi
0x180007b7b  retn
```
