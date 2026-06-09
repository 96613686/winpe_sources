# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18001c760`
- end: `0x18001c864`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016eb4`
- `0x18001709c`
- `0x180017234`
- `0x1800187bc`

## callees

- `0x180004086`
- `0x180004118`
- `0x18001c760`
- `0x180021e9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c7f1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c81b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c7f1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c81b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c84e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c84e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c78c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c78c`

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
      || a3 != dword_180037494
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800374B8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800374C8 - (_QWORD)qword_1800374C0) & -(__int64)((unsigned __int64)qword_1800374C0 < qword_1800374C8);
    if ( qword_1800374C0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800374C0 = v12;
LABEL_11:
        qword_1800374C0 = (char *)qword_1800374C0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800374C0, 0, v8);
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
0x18001c760  mov     [rsp+arg_10], rbx
0x18001c765  mov     [rsp+arg_18], rsi
0x18001c76a  push    rdi
0x18001c76b  sub     rsp, 30h
0x18001c76f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001c775  mov     esi, r8d
0x18001c778  mov     edi, edx
0x18001c77a  mov     rbx, rcx
0x18001c77d  test    eax, eax
0x18001c77f  jz      loc_18001C854
0x18001c785  lea     rcx, SRWLock; SRWLock
0x18001c78c  call    cs:__imp_AcquireSRWLockExclusive
0x18001c792  mov     eax, cs:dword_180037494
0x18001c798  test    esi, esi
0x18001c79a  jz      loc_18001C836
0x18001c7a0  cmp     esi, eax
0x18001c7a2  jnz     loc_18001C836
0x18001c7a8  mov     edx, 10h; unsigned __int64
0x18001c7ad  mov     dword ptr [rsp+38h+var_18+4], 0
0x18001c7b5  lea     rcx, qword_1800374B8; this
0x18001c7bc  mov     dword ptr [rsp+38h+var_18], edi
0x18001c7c0  mov     qword ptr [rsp+38h+var_18+8], rbx
0x18001c7c5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001c7ca  test    al, al
0x18001c7cc  jz      short loc_18001C836
0x18001c7ce  mov     r9, cs:qword_1800374C0
0x18001c7d5  mov     rax, cs:qword_1800374C8
0x18001c7dc  sub     rax, r9
0x18001c7df  cmp     r9, cs:qword_1800374C8
0x18001c7e6  sbb     r8, r8
0x18001c7e9  and     r8, rax; Size
0x18001c7ec  test    r9, r9
0x18001c7ef  jnz     short loc_18001C7FF
0x18001c7f1  call    cs:__imp__o__errno
0x18001c7f7  mov     dword ptr [rax], 16h
0x18001c7fd  jmp     short loc_18001C827
0x18001c7ff  cmp     r8, 10h
0x18001c803  jb      short loc_18001C811
0x18001c805  movups  xmm0, [rsp+38h+var_18]
0x18001c80a  movdqu  xmmword ptr [r9], xmm0
0x18001c80f  jmp     short loc_18001C82C
0x18001c811  xor     edx, edx; Val
0x18001c813  mov     rcx, r9; void *
0x18001c816  call    memset_0
0x18001c81b  call    cs:__imp__o__errno
0x18001c821  mov     dword ptr [rax], 22h ; '"'
0x18001c827  call    _invalid_parameter_noinfo
0x18001c82c  add     cs:qword_1800374C0, 10h
0x18001c834  jmp     short loc_18001C847
0x18001c836  neg     edi
0x18001c838  sbb     eax, eax
0x18001c83a  and     eax, 83Ah
0x18001c83f  add     eax, 0FFFFF7C1h
0x18001c844  lock and [rbx], eax
0x18001c847  lea     rcx, SRWLock; SRWLock
0x18001c84e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c854  mov     rbx, [rsp+38h+arg_10]
0x18001c859  mov     rsi, [rsp+38h+arg_18]
0x18001c85e  add     rsp, 30h
0x18001c862  pop     rdi
0x18001c863  retn
```
