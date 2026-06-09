# wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a1b0`
- end: `0x18002a38d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60663426@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `477`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029ac0`

## callees

- `0x18000fdc0`
- `0x1800100b0`
- `0x18002a1b0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a32d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a32d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a2ec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a2ec`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_60663426>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v4; // eax
  int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // edi
  signed __int32 v13; // eax
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  int v16; // ecx
  int v17; // r8d
  unsigned __int64 v18; // r8
  int v19; // ecx
  _QWORD v21[2]; // [rsp+20h] [rbp-38h] BYREF
  int v22; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v4 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v4 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(60663426, 0, &v22);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      v11 = v9 | v10;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = v9;
LABEL_10:
  v12 = v11 | (v11 >> 6) & 1;
  if ( !v5 )
    v22 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v13;
    *(_DWORD *)a2 = v13;
    v15 = v13;
    if ( v22 && (v13 & 2) == 0 )
    {
      v16 = v13
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v13)
          & 0x180
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)(v13 ^ (v12 ^ v13) & 0x80))
          & 0x40;
      v15 = v16
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v16)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v16 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v16) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v17 = v13 & 4;
    if ( (v13 & 4) == 0 )
    {
      v15 = ((unsigned __int16)v12 ^ (unsigned __int16)v15) & 0x400 ^ v15 | 4;
      *(_DWORD *)a2 = v15;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v15, v13);
  }
  while ( v14 != v13 );
  if ( !v17 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !v5
      || v5 != dword_1800583FC
      || (v21[0] = 0,
          v21[1] = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180058430, v21, v18)) )
    {
      _InterlockedAnd((volatile signed __int32 *)a1, 0xFFFFF7C1);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v19 = *(_DWORD *)a2
        ^ ((unsigned __int16)v12
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v12
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v12 ^ *(_DWORD *)a2) & 0x80))
        & 0x40;
    *(_DWORD *)a2 = v19
                  ^ ((unsigned __int8)v12
                   ^ (unsigned __int8)v19)
                  & 1
                  ^ ((unsigned __int16)v12
                   ^ (unsigned __int16)(v19 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v19) & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18002a1b0  push    rbx
0x18002a1b2  push    rsi
0x18002a1b3  push    r14
0x18002a1b5  sub     rsp, 40h
0x18002a1b9  mov     rax, cs:__security_cookie
0x18002a1c0  xor     rax, rsp
0x18002a1c3  mov     [rsp+58h+var_20], rax
0x18002a1c8  xor     r14d, r14d
0x18002a1cb  mov     rbx, rdx
0x18002a1ce  mov     [rdx], r14
0x18002a1d1  mov     rsi, rcx
0x18002a1d4  mov     eax, [rcx]
0x18002a1d6  mov     [rdx], eax
0x18002a1d8  and     eax, 6
0x18002a1db  cmp     al, 6
0x18002a1dd  jz      loc_18002A388
0x18002a1e3  mov     [rsp+58h+arg_10], rbp
0x18002a1e8  mov     [rsp+58h+arg_18], rdi
0x18002a1ed  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002a1f2  mov     ebp, eax
0x18002a1f4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002a1fb  test    rax, rax
0x18002a1fe  jnz     short loc_18002A20C
0x18002a200  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002a207  test    rax, rax
0x18002a20a  jz      short loc_18002A25E
0x18002a20c  lea     r8, [rsp+58h+var_28]
0x18002a211  xor     edx, edx
0x18002a213  mov     ecx, 39DA682h
0x18002a218  call    cs:__guard_dispatch_icall_fptr
0x18002a21e  mov     r8d, eax
0x18002a221  mov     edx, eax
0x18002a223  and     r8d, 0FFFFFF3Fh
0x18002a22a  and     eax, 40h
0x18002a22d  and     edx, 80h
0x18002a233  mov     ecx, r8d
0x18002a236  and     ecx, 3
0x18002a239  shl     ecx, 2
0x18002a23c  or      ecx, eax
0x18002a23e  shl     ecx, 2
0x18002a241  or      ecx, edx
0x18002a243  shl     ecx, 3
0x18002a246  test    r8d, r8d
0x18002a249  jz      short loc_18002A261
0x18002a24b  cmp     r8d, 2
0x18002a24f  mov     eax, r14d
0x18002a252  mov     edx, 40h ; '@'
0x18002a257  cmovz   eax, edx
0x18002a25a  or      eax, ecx
0x18002a25c  jmp     short loc_18002A263
0x18002a25e  mov     ecx, r14d
0x18002a261  mov     eax, ecx
0x18002a263  mov     edi, eax
0x18002a265  shr     edi, 6
0x18002a268  and     edi, 1
0x18002a26b  or      edi, eax
0x18002a26d  test    ebp, ebp
0x18002a26f  jnz     short loc_18002A276
0x18002a271  mov     [rsp+58h+var_28], r14d
0x18002a276  mov     eax, [rbx]
0x18002a278  mov     edx, eax
0x18002a27a  mov     [rbx], eax
0x18002a27c  mov     ecx, eax
0x18002a27e  cmp     [rsp+58h+var_28], r14d
0x18002a283  jz      short loc_18002A2B6
0x18002a285  test    dl, 2
0x18002a288  jnz     short loc_18002A2B6
0x18002a28a  xor     eax, edi
0x18002a28c  and     eax, 180h
0x18002a291  xor     eax, ecx
0x18002a293  mov     ecx, eax
0x18002a295  xor     ecx, edi
0x18002a297  and     ecx, 40h
0x18002a29a  xor     ecx, eax
0x18002a29c  mov     eax, ecx
0x18002a29e  xor     eax, edi
0x18002a2a0  and     eax, 1
0x18002a2a3  xor     eax, ecx
0x18002a2a5  mov     ecx, eax
0x18002a2a7  xor     ecx, edi
0x18002a2a9  and     ecx, 800h
0x18002a2af  xor     ecx, eax
0x18002a2b1  or      ecx, 2
0x18002a2b4  mov     [rbx], ecx
0x18002a2b6  mov     r8d, edx
0x18002a2b9  and     r8d, 4
0x18002a2bd  jnz     short loc_18002A2CF
0x18002a2bf  mov     eax, ecx
0x18002a2c1  xor     eax, edi
0x18002a2c3  and     eax, 400h
0x18002a2c8  xor     ecx, eax
0x18002a2ca  or      ecx, 4
0x18002a2cd  mov     [rbx], ecx
0x18002a2cf  mov     eax, edx
0x18002a2d1  lock cmpxchg [rsi], ecx
0x18002a2d5  jnz     short loc_18002A278
0x18002a2d7  test    r8d, r8d
0x18002a2da  jnz     short loc_18002A333
0x18002a2dc  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002a2e3  jz      short loc_18002A333
0x18002a2e5  lea     rcx, SRWLock; SRWLock
0x18002a2ec  call    cs:__imp_AcquireSRWLockExclusive
0x18002a2f2  mov     eax, cs:dword_1800583FC
0x18002a2f8  test    ebp, ebp
0x18002a2fa  jz      short loc_18002A31F
0x18002a2fc  cmp     ebp, eax
0x18002a2fe  jnz     short loc_18002A31F
0x18002a300  lea     rdx, [rsp+58h+var_38]; void *
0x18002a305  mov     [rsp+58h+var_38], r14
0x18002a30a  lea     rcx, qword_180058430; this
0x18002a311  mov     [rsp+58h+var_30], rsi
0x18002a316  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002a31b  test    al, al
0x18002a31d  jnz     short loc_18002A326
0x18002a31f  lock and dword ptr [rsi], 0FFFFF7C1h
0x18002a326  lea     rcx, SRWLock; SRWLock
0x18002a32d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a333  mov     ecx, [rbx]
0x18002a335  mov     rbp, [rsp+58h+arg_10]
0x18002a33a  test    cl, 2
0x18002a33d  jnz     short loc_18002A36A
0x18002a33f  mov     eax, ecx
0x18002a341  xor     eax, edi
0x18002a343  and     eax, 180h
0x18002a348  xor     eax, ecx
0x18002a34a  mov     ecx, eax
0x18002a34c  xor     ecx, edi
0x18002a34e  and     ecx, 40h
0x18002a351  xor     ecx, eax
0x18002a353  mov     edx, ecx
0x18002a355  xor     edx, edi
0x18002a357  and     edx, 1
0x18002a35a  xor     edx, ecx
0x18002a35c  mov     ecx, edx
0x18002a35e  xor     ecx, edi
0x18002a360  and     ecx, 800h
0x18002a366  xor     ecx, edx
0x18002a368  mov     [rbx], ecx
0x18002a36a  mov     rdi, [rsp+58h+arg_18]
0x18002a36f  mov     rax, rbx
0x18002a372  mov     rcx, [rsp+58h+var_20]
0x18002a377  xor     rcx, rsp; StackCookie
0x18002a37a  call    __security_check_cookie
0x18002a37f  add     rsp, 40h
0x18002a383  pop     r14
0x18002a385  pop     rsi
0x18002a386  pop     rbx
0x18002a387  retn
0x18002a388  mov     rax, rbx
0x18002a38b  jmp     short loc_18002A372
```
