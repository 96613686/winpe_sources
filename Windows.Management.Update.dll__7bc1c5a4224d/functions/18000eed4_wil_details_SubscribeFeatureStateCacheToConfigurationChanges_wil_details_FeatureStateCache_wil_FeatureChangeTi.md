# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000eed4`
- end: `0x18000efd8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c3a0`
- `0x18001b984`
- `0x18001bb04`
- `0x18001bcd8`

## callees

- `0x180003392`
- `0x1800033e8`
- `0x18000eed4`
- `0x18000fcc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ef65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ef8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ef65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ef8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000efc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000efc2`

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
      || a3 != dword_18003AA74
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18003AA98, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18003AAA8 - (_QWORD)qword_18003AAA0) & -(__int64)((unsigned __int64)qword_18003AAA0 < qword_18003AAA8);
    if ( qword_18003AAA0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18003AAA0 = v12;
LABEL_11:
        qword_18003AAA0 = (char *)qword_18003AAA0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18003AAA0, 0, v8);
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
0x18000eed4  mov     [rsp+arg_0], rbx
0x18000eed9  mov     [rsp+arg_8], rsi
0x18000eede  push    rdi
0x18000eedf  sub     rsp, 30h
0x18000eee3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000eee9  mov     esi, r8d
0x18000eeec  mov     ebx, edx
0x18000eeee  mov     rdi, rcx
0x18000eef1  test    eax, eax
0x18000eef3  jz      loc_18000EFC8
0x18000eef9  lea     rcx, SRWLock; SRWLock
0x18000ef00  call    cs:__imp_AcquireSRWLockExclusive
0x18000ef06  mov     eax, cs:dword_18003AA74
0x18000ef0c  test    esi, esi
0x18000ef0e  jz      loc_18000EFAA
0x18000ef14  cmp     esi, eax
0x18000ef16  jnz     loc_18000EFAA
0x18000ef1c  mov     edx, 10h; unsigned __int64
0x18000ef21  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000ef29  lea     rcx, qword_18003AA98; this
0x18000ef30  mov     dword ptr [rsp+38h+var_18], ebx
0x18000ef34  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000ef39  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ef3e  test    al, al
0x18000ef40  jz      short loc_18000EFAA
0x18000ef42  mov     r9, cs:qword_18003AAA0
0x18000ef49  mov     rax, cs:qword_18003AAA8
0x18000ef50  sub     rax, r9
0x18000ef53  cmp     r9, cs:qword_18003AAA8
0x18000ef5a  sbb     r8, r8
0x18000ef5d  and     r8, rax; Size
0x18000ef60  test    r9, r9
0x18000ef63  jnz     short loc_18000EF73
0x18000ef65  call    cs:__imp__o__errno
0x18000ef6b  mov     dword ptr [rax], 16h
0x18000ef71  jmp     short loc_18000EF9B
0x18000ef73  cmp     r8, 10h
0x18000ef77  jb      short loc_18000EF85
0x18000ef79  movups  xmm0, [rsp+38h+var_18]
0x18000ef7e  movdqu  xmmword ptr [r9], xmm0
0x18000ef83  jmp     short loc_18000EFA0
0x18000ef85  xor     edx, edx; Val
0x18000ef87  mov     rcx, r9; void *
0x18000ef8a  call    memset_0
0x18000ef8f  call    cs:__imp__o__errno
0x18000ef95  mov     dword ptr [rax], 22h ; '"'
0x18000ef9b  call    _invalid_parameter_noinfo
0x18000efa0  add     cs:qword_18003AAA0, 10h
0x18000efa8  jmp     short loc_18000EFBB
0x18000efaa  neg     ebx
0x18000efac  sbb     eax, eax
0x18000efae  and     eax, 83Ah
0x18000efb3  add     eax, 0FFFFF7C1h
0x18000efb8  lock and [rdi], eax
0x18000efbb  lea     rcx, SRWLock; SRWLock
0x18000efc2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000efc8  mov     rbx, [rsp+38h+arg_0]
0x18000efcd  mov     rsi, [rsp+38h+arg_8]
0x18000efd2  add     rsp, 30h
0x18000efd6  pop     rdi
0x18000efd7  retn
```
