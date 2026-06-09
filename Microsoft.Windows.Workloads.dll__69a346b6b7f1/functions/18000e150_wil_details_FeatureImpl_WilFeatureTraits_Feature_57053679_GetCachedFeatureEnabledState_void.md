# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57053679>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e150`
- end: `0x18000e32d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57053679@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `477`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9a0`

## callees

- `0x18000e150`
- `0x18000fdc0`
- `0x1800100b0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e2cd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000e2cd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e28c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000e28c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57053679>::GetCachedFeatureEnabledState(
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
    v7 = v6(57053679, 0, &v22);
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
0x18000e150  push    rbx
0x18000e152  push    rsi
0x18000e153  push    r14
0x18000e155  sub     rsp, 40h
0x18000e159  mov     rax, cs:__security_cookie
0x18000e160  xor     rax, rsp
0x18000e163  mov     [rsp+58h+var_20], rax
0x18000e168  xor     r14d, r14d
0x18000e16b  mov     rbx, rdx
0x18000e16e  mov     [rdx], r14
0x18000e171  mov     rsi, rcx
0x18000e174  mov     eax, [rcx]
0x18000e176  mov     [rdx], eax
0x18000e178  and     eax, 6
0x18000e17b  cmp     al, 6
0x18000e17d  jz      loc_18000E328
0x18000e183  mov     [rsp+58h+arg_10], rbp
0x18000e188  mov     [rsp+58h+arg_18], rdi
0x18000e18d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e192  mov     ebp, eax
0x18000e194  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e19b  test    rax, rax
0x18000e19e  jnz     short loc_18000E1AC
0x18000e1a0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e1a7  test    rax, rax
0x18000e1aa  jz      short loc_18000E1FE
0x18000e1ac  lea     r8, [rsp+58h+var_28]
0x18000e1b1  xor     edx, edx
0x18000e1b3  mov     ecx, 36691EFh
0x18000e1b8  call    cs:__guard_dispatch_icall_fptr
0x18000e1be  mov     r8d, eax
0x18000e1c1  mov     edx, eax
0x18000e1c3  and     r8d, 0FFFFFF3Fh
0x18000e1ca  and     eax, 40h
0x18000e1cd  and     edx, 80h
0x18000e1d3  mov     ecx, r8d
0x18000e1d6  and     ecx, 3
0x18000e1d9  shl     ecx, 2
0x18000e1dc  or      ecx, eax
0x18000e1de  shl     ecx, 2
0x18000e1e1  or      ecx, edx
0x18000e1e3  shl     ecx, 3
0x18000e1e6  test    r8d, r8d
0x18000e1e9  jz      short loc_18000E201
0x18000e1eb  cmp     r8d, 2
0x18000e1ef  mov     eax, r14d
0x18000e1f2  mov     edx, 40h ; '@'
0x18000e1f7  cmovz   eax, edx
0x18000e1fa  or      eax, ecx
0x18000e1fc  jmp     short loc_18000E203
0x18000e1fe  mov     ecx, r14d
0x18000e201  mov     eax, ecx
0x18000e203  mov     edi, eax
0x18000e205  shr     edi, 6
0x18000e208  and     edi, 1
0x18000e20b  or      edi, eax
0x18000e20d  test    ebp, ebp
0x18000e20f  jnz     short loc_18000E216
0x18000e211  mov     [rsp+58h+var_28], r14d
0x18000e216  mov     eax, [rbx]
0x18000e218  mov     edx, eax
0x18000e21a  mov     [rbx], eax
0x18000e21c  mov     ecx, eax
0x18000e21e  cmp     [rsp+58h+var_28], r14d
0x18000e223  jz      short loc_18000E256
0x18000e225  test    dl, 2
0x18000e228  jnz     short loc_18000E256
0x18000e22a  xor     eax, edi
0x18000e22c  and     eax, 180h
0x18000e231  xor     eax, ecx
0x18000e233  mov     ecx, eax
0x18000e235  xor     ecx, edi
0x18000e237  and     ecx, 40h
0x18000e23a  xor     ecx, eax
0x18000e23c  mov     eax, ecx
0x18000e23e  xor     eax, edi
0x18000e240  and     eax, 1
0x18000e243  xor     eax, ecx
0x18000e245  mov     ecx, eax
0x18000e247  xor     ecx, edi
0x18000e249  and     ecx, 800h
0x18000e24f  xor     ecx, eax
0x18000e251  or      ecx, 2
0x18000e254  mov     [rbx], ecx
0x18000e256  mov     r8d, edx
0x18000e259  and     r8d, 4
0x18000e25d  jnz     short loc_18000E26F
0x18000e25f  mov     eax, ecx
0x18000e261  xor     eax, edi
0x18000e263  and     eax, 400h
0x18000e268  xor     ecx, eax
0x18000e26a  or      ecx, 4
0x18000e26d  mov     [rbx], ecx
0x18000e26f  mov     eax, edx
0x18000e271  lock cmpxchg [rsi], ecx
0x18000e275  jnz     short loc_18000E218
0x18000e277  test    r8d, r8d
0x18000e27a  jnz     short loc_18000E2D3
0x18000e27c  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000e283  jz      short loc_18000E2D3
0x18000e285  lea     rcx, SRWLock; SRWLock
0x18000e28c  call    cs:__imp_AcquireSRWLockExclusive
0x18000e292  mov     eax, cs:dword_1800583FC
0x18000e298  test    ebp, ebp
0x18000e29a  jz      short loc_18000E2BF
0x18000e29c  cmp     ebp, eax
0x18000e29e  jnz     short loc_18000E2BF
0x18000e2a0  lea     rdx, [rsp+58h+var_38]; void *
0x18000e2a5  mov     [rsp+58h+var_38], r14
0x18000e2aa  lea     rcx, qword_180058430; this
0x18000e2b1  mov     [rsp+58h+var_30], rsi
0x18000e2b6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000e2bb  test    al, al
0x18000e2bd  jnz     short loc_18000E2C6
0x18000e2bf  lock and dword ptr [rsi], 0FFFFF7C1h
0x18000e2c6  lea     rcx, SRWLock; SRWLock
0x18000e2cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e2d3  mov     ecx, [rbx]
0x18000e2d5  mov     rbp, [rsp+58h+arg_10]
0x18000e2da  test    cl, 2
0x18000e2dd  jnz     short loc_18000E30A
0x18000e2df  mov     eax, ecx
0x18000e2e1  xor     eax, edi
0x18000e2e3  and     eax, 180h
0x18000e2e8  xor     eax, ecx
0x18000e2ea  mov     ecx, eax
0x18000e2ec  xor     ecx, edi
0x18000e2ee  and     ecx, 40h
0x18000e2f1  xor     ecx, eax
0x18000e2f3  mov     edx, ecx
0x18000e2f5  xor     edx, edi
0x18000e2f7  and     edx, 1
0x18000e2fa  xor     edx, ecx
0x18000e2fc  mov     ecx, edx
0x18000e2fe  xor     ecx, edi
0x18000e300  and     ecx, 800h
0x18000e306  xor     ecx, edx
0x18000e308  mov     [rbx], ecx
0x18000e30a  mov     rdi, [rsp+58h+arg_18]
0x18000e30f  mov     rax, rbx
0x18000e312  mov     rcx, [rsp+58h+var_20]
0x18000e317  xor     rcx, rsp; StackCookie
0x18000e31a  call    __security_check_cookie
0x18000e31f  add     rsp, 40h
0x18000e323  pop     r14
0x18000e325  pop     rsi
0x18000e326  pop     rbx
0x18000e327  retn
0x18000e328  mov     rax, rbx
0x18000e32b  jmp     short loc_18000E312
```
