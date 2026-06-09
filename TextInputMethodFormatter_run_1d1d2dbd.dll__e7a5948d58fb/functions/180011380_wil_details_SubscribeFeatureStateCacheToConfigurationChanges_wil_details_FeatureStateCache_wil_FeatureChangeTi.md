# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180011380`
- end: `0x180011485`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `261`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b49c`
- `0x18000b65c`
- `0x18000b81c`
- `0x18000b990`
- `0x18000bb04`
- `0x18000bc78`
- `0x18000bdec`
- `0x18000bf60`
- `0x18000c0d4`
- `0x18000c1b4`
- `0x18000c294`
- `0x18000c374`
- `0x18000c454`
- `0x18000c5c8`
- `0x18000c79c`
- `0x18000c87c`
- `0x18000c95c`
- `0x18000dc08`
- `0x1800160cc`
- `0x180031638`

## callees

- `0x180002db8`
- `0x180011380`
- `0x18001268c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180011447`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180011447`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011411`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001143b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011411`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001143b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001146f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001146f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800113ac`

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
      || a3 != dword_180082434
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&unk_180082458, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180082468 - (_QWORD)qword_180082460) & -(__int64)((unsigned __int64)qword_180082460 < qword_180082468);
    if ( qword_180082460 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180082460 = v12;
LABEL_11:
        qword_180082460 = (char *)qword_180082460 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180082460, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6, v8) = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x180011380  mov     [rsp+arg_0], rbx
0x180011385  mov     [rsp+arg_8], rsi
0x18001138a  push    rdi
0x18001138b  sub     rsp, 30h
0x18001138f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011395  mov     esi, r8d
0x180011398  mov     ebx, edx
0x18001139a  mov     rdi, rcx
0x18001139d  test    eax, eax
0x18001139f  jz      loc_180011475
0x1800113a5  lea     rcx, SRWLock; SRWLock
0x1800113ac  call    cs:__imp_AcquireSRWLockExclusive
0x1800113b2  mov     eax, cs:dword_180082434
0x1800113b8  test    esi, esi
0x1800113ba  jz      loc_180011457
0x1800113c0  cmp     esi, eax
0x1800113c2  jnz     loc_180011457
0x1800113c8  mov     edx, 10h; unsigned __int64
0x1800113cd  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800113d5  lea     rcx, unk_180082458; this
0x1800113dc  mov     dword ptr [rsp+38h+var_18], ebx
0x1800113e0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800113e5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800113ea  test    al, al
0x1800113ec  jz      short loc_180011457
0x1800113ee  mov     r9, cs:qword_180082460
0x1800113f5  mov     rax, cs:qword_180082468
0x1800113fc  sub     rax, r9
0x1800113ff  cmp     r9, cs:qword_180082468
0x180011406  sbb     r8, r8
0x180011409  and     r8, rax; Size
0x18001140c  test    r9, r9
0x18001140f  jnz     short loc_18001141F
0x180011411  call    cs:__imp__o__errno
0x180011417  mov     dword ptr [rax], 16h
0x18001141d  jmp     short loc_180011447
0x18001141f  cmp     r8, 10h
0x180011423  jb      short loc_180011431
0x180011425  movups  xmm0, [rsp+38h+var_18]
0x18001142a  movdqu  xmmword ptr [r9], xmm0
0x18001142f  jmp     short loc_18001144D
0x180011431  xor     edx, edx; Val
0x180011433  mov     rcx, r9; void *
0x180011436  call    memset_0
0x18001143b  call    cs:__imp__o__errno
0x180011441  mov     dword ptr [rax], 22h ; '"'
0x180011447  call    cs:__imp__invalid_parameter_noinfo
0x18001144d  add     cs:qword_180082460, 10h
0x180011455  jmp     short loc_180011468
0x180011457  neg     ebx
0x180011459  sbb     eax, eax
0x18001145b  and     eax, 83Ah
0x180011460  add     eax, 0FFFFF7C1h
0x180011465  lock and [rdi], eax
0x180011468  lea     rcx, SRWLock; SRWLock
0x18001146f  call    cs:__imp_ReleaseSRWLockExclusive
0x180011475  mov     rbx, [rsp+38h+arg_0]
0x18001147a  mov     rsi, [rsp+38h+arg_8]
0x18001147f  add     rsp, 30h
0x180011483  pop     rdi
0x180011484  retn
```
