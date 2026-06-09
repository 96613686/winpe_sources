# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1400121c4`
- end: `0x1400122c8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010084`

## callees

- `0x140003026`
- `0x1400030dc`
- `0x1400121c4`
- `0x140013290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012255`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001227f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012255`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001227f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400122b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400122b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400121f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400121f0`

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
      || a3 != dword_140030444
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140030468, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_140030478 - (_QWORD)qword_140030470) & -(__int64)((unsigned __int64)qword_140030470 < qword_140030478);
    if ( qword_140030470 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_140030470 = v12;
LABEL_11:
        qword_140030470 = (char *)qword_140030470 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_140030470, 0, v8);
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
0x1400121c4  mov     [rsp+arg_0], rbx
0x1400121c9  mov     [rsp+arg_8], rsi
0x1400121ce  push    rdi
0x1400121cf  sub     rsp, 30h
0x1400121d3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400121d9  mov     esi, r8d
0x1400121dc  mov     ebx, edx
0x1400121de  mov     rdi, rcx
0x1400121e1  test    eax, eax
0x1400121e3  jz      loc_1400122B8
0x1400121e9  lea     rcx, SRWLock; SRWLock
0x1400121f0  call    cs:__imp_AcquireSRWLockExclusive
0x1400121f6  mov     eax, cs:dword_140030444
0x1400121fc  test    esi, esi
0x1400121fe  jz      loc_14001229A
0x140012204  cmp     esi, eax
0x140012206  jnz     loc_14001229A
0x14001220c  mov     edx, 10h; unsigned __int64
0x140012211  mov     dword ptr [rsp+38h+var_18+4], 0
0x140012219  lea     rcx, qword_140030468; this
0x140012220  mov     dword ptr [rsp+38h+var_18], ebx
0x140012224  mov     qword ptr [rsp+38h+var_18+8], rdi
0x140012229  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14001222e  test    al, al
0x140012230  jz      short loc_14001229A
0x140012232  mov     r9, cs:qword_140030470
0x140012239  mov     rax, cs:qword_140030478
0x140012240  sub     rax, r9
0x140012243  cmp     r9, cs:qword_140030478
0x14001224a  sbb     r8, r8
0x14001224d  and     r8, rax; Size
0x140012250  test    r9, r9
0x140012253  jnz     short loc_140012263
0x140012255  call    cs:__imp__o__errno
0x14001225b  mov     dword ptr [rax], 16h
0x140012261  jmp     short loc_14001228B
0x140012263  cmp     r8, 10h
0x140012267  jb      short loc_140012275
0x140012269  movups  xmm0, [rsp+38h+var_18]
0x14001226e  movdqu  xmmword ptr [r9], xmm0
0x140012273  jmp     short loc_140012290
0x140012275  xor     edx, edx; Val
0x140012277  mov     rcx, r9; void *
0x14001227a  call    memset_0
0x14001227f  call    cs:__imp__o__errno
0x140012285  mov     dword ptr [rax], 22h ; '"'
0x14001228b  call    _invalid_parameter_noinfo
0x140012290  add     cs:qword_140030470, 10h
0x140012298  jmp     short loc_1400122AB
0x14001229a  neg     ebx
0x14001229c  sbb     eax, eax
0x14001229e  and     eax, 83Ah
0x1400122a3  add     eax, 0FFFFF7C1h
0x1400122a8  lock and [rdi], eax
0x1400122ab  lea     rcx, SRWLock; SRWLock
0x1400122b2  call    cs:__imp_ReleaseSRWLockExclusive
0x1400122b8  mov     rbx, [rsp+38h+arg_0]
0x1400122bd  mov     rsi, [rsp+38h+arg_8]
0x1400122c2  add     rsp, 30h
0x1400122c6  pop     rdi
0x1400122c7  retn
```
