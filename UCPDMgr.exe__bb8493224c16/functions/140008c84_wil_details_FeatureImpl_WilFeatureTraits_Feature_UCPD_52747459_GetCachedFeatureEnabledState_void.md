# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_52747459>::GetCachedFeatureEnabledState(void)

- ea: `0x140008c84`
- end: `0x140008e14`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_52747459@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000594c`
- `0x140008e1c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140008c84`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_52747459>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // ebx
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  int v17; // ecx
  int v19; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v19 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(52747459, 0, &v19);
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
    v19 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v19 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    v16 = v13;
    if ( !v14 && (v13 & 2) == 0 )
    {
      v17 = v13
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ ((unsigned __int16)v13
            ^ (unsigned __int16)v12)
           & 0x180)
          & 0x40;
      v16 = v17
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v17)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v17 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v17) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    if ( (v13 & 4) == 0 )
    {
      v16 = ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 ^ v16 | 4;
      *(_DWORD *)a2 = v16;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v16, v13);
  }
  while ( v15 != v13 );
  if ( (v15 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v12)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v12)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v12)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v12)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v12)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v12)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140008c84  mov     [rsp+arg_10], rbx
0x140008c89  mov     [rsp+arg_18], rbp
0x140008c8e  push    rsi
0x140008c8f  push    rdi
0x140008c90  push    r15
0x140008c92  sub     rsp, 30h
0x140008c96  mov     rax, cs:__security_cookie
0x140008c9d  xor     rax, rsp
0x140008ca0  mov     [rsp+48h+var_20], rax
0x140008ca5  mov     qword ptr [rdx], 0
0x140008cac  mov     rdi, rdx
0x140008caf  mov     eax, [rcx]
0x140008cb1  mov     rsi, rcx
0x140008cb4  mov     [rdx], eax
0x140008cb6  and     eax, 6
0x140008cb9  cmp     al, 6
0x140008cbb  jz      loc_140008DF1
0x140008cc1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008cc6  mov     ebp, eax
0x140008cc8  mov     [rsp+48h+var_28], 0
0x140008cd0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140008cd7  mov     r15d, 40h ; '@'
0x140008cdd  test    rax, rax
0x140008ce0  jnz     short loc_140008CEE
0x140008ce2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140008ce9  test    rax, rax
0x140008cec  jz      short loc_140008D3A
0x140008cee  lea     r8, [rsp+48h+var_28]
0x140008cf3  xor     edx, edx
0x140008cf5  mov     ecx, 324DCC3h
0x140008cfa  call    _guard_dispatch_icall
0x140008cff  mov     r8d, eax
0x140008d02  mov     edx, eax
0x140008d04  and     r8d, 0FFFFFF3Fh
0x140008d0b  and     eax, r15d
0x140008d0e  and     edx, 80h
0x140008d14  mov     ecx, r8d
0x140008d17  and     ecx, 3
0x140008d1a  shl     ecx, 2
0x140008d1d  or      ecx, eax
0x140008d1f  shl     ecx, 2
0x140008d22  or      ecx, edx
0x140008d24  shl     ecx, 3
0x140008d27  test    r8d, r8d
0x140008d2a  jz      short loc_140008D3C
0x140008d2c  xor     eax, eax
0x140008d2e  cmp     r8d, 2
0x140008d32  cmovz   eax, r15d
0x140008d36  or      eax, ecx
0x140008d38  jmp     short loc_140008D3E
0x140008d3a  xor     ecx, ecx
0x140008d3c  mov     eax, ecx
0x140008d3e  mov     ebx, eax
0x140008d40  shr     ebx, 6
0x140008d43  and     ebx, 1
0x140008d46  or      ebx, eax
0x140008d48  test    ebp, ebp
0x140008d4a  jnz     short loc_140008D50
0x140008d4c  mov     [rsp+48h+var_28], ebp
0x140008d50  mov     eax, [rdi]
0x140008d52  cmp     [rsp+48h+var_28], 0
0x140008d57  mov     edx, eax
0x140008d59  mov     [rdi], eax
0x140008d5b  mov     ecx, eax
0x140008d5d  jz      short loc_140008D92
0x140008d5f  test    dl, 2
0x140008d62  jnz     short loc_140008D92
0x140008d64  mov     eax, ebx
0x140008d66  xor     eax, ecx
0x140008d68  and     eax, 180h
0x140008d6d  xor     eax, ecx
0x140008d6f  mov     ecx, eax
0x140008d71  xor     ecx, ebx
0x140008d73  and     ecx, r15d
0x140008d76  xor     ecx, eax
0x140008d78  mov     eax, ecx
0x140008d7a  xor     eax, ebx
0x140008d7c  and     eax, 1
0x140008d7f  xor     eax, ecx
0x140008d81  mov     ecx, eax
0x140008d83  xor     ecx, ebx
0x140008d85  and     ecx, 800h
0x140008d8b  xor     ecx, eax
0x140008d8d  or      ecx, 2
0x140008d90  mov     [rdi], ecx
0x140008d92  test    dl, 4
0x140008d95  jnz     short loc_140008DA7
0x140008d97  mov     eax, ebx
0x140008d99  xor     eax, ecx
0x140008d9b  and     eax, 400h
0x140008da0  xor     ecx, eax
0x140008da2  or      ecx, 4
0x140008da5  mov     [rdi], ecx
0x140008da7  mov     eax, edx
0x140008da9  lock cmpxchg [rsi], ecx
0x140008dad  jnz     short loc_140008D52
0x140008daf  test    dl, 4
0x140008db2  jnz     short loc_140008DC1
0x140008db4  mov     r8d, ebp
0x140008db7  xor     edx, edx
0x140008db9  mov     rcx, rsi
0x140008dbc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140008dc1  test    byte ptr [rdi], 2
0x140008dc4  jnz     short loc_140008DF1
0x140008dc6  mov     eax, ebx
0x140008dc8  xor     eax, [rdi]
0x140008dca  and     eax, 180h
0x140008dcf  xor     eax, [rdi]
0x140008dd1  mov     ecx, eax
0x140008dd3  xor     ecx, ebx
0x140008dd5  and     ecx, r15d
0x140008dd8  xor     ecx, eax
0x140008dda  mov     edx, ecx
0x140008ddc  xor     edx, ebx
0x140008dde  and     edx, 1
0x140008de1  xor     edx, ecx
0x140008de3  mov     ecx, edx
0x140008de5  xor     ecx, ebx
0x140008de7  and     ecx, 800h
0x140008ded  xor     ecx, edx
0x140008def  mov     [rdi], ecx
0x140008df1  mov     rax, rdi
0x140008df4  mov     rcx, [rsp+48h+var_20]
0x140008df9  xor     rcx, rsp; StackCookie
0x140008dfc  call    __security_check_cookie
0x140008e01  mov     rbx, [rsp+48h+arg_10]
0x140008e06  mov     rbp, [rsp+48h+arg_18]
0x140008e0b  add     rsp, 30h
0x140008e0f  pop     r15
0x140008e11  pop     rdi
0x140008e12  pop     rsi
0x140008e13  retn
```
