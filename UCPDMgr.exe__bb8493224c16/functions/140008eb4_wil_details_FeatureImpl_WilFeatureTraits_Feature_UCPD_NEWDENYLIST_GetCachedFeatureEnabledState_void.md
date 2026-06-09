# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_NEWDENYLIST>::GetCachedFeatureEnabledState(void)

- ea: `0x140008eb4`
- end: `0x140009045`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_NEWDENYLIST@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `401`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005988`
- `0x14000904c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140008eb4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_NEWDENYLIST>::GetCachedFeatureEnabledState(
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
  unsigned int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  int v16; // ecx
  int v18; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v18 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(50910371, 0, &v18);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v10 = 64;
LABEL_10:
  v11 = v10 | v9 | ((v10 | (unsigned int)v9) >> 6) & 1;
  if ( !v5 )
    v18 = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = v18 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    v15 = v12;
    if ( !v13 && (v12 & 2) == 0 )
    {
      v16 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40;
      v15 = v16
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)v16)
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v16 ^ ((unsigned __int8)v11 ^ (unsigned __int8)v16) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    if ( (v12 & 4) == 0 )
    {
      v15 = ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 ^ v15 | 4;
      *(_DWORD *)a2 = v15;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v15, v12);
  }
  while ( v14 != v12 );
  if ( (v14 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v11)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v11)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v11)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v11)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v11)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v11)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v11)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v11)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140008eb4  mov     [rsp+arg_10], rbx
0x140008eb9  mov     [rsp+arg_18], rbp
0x140008ebe  push    rsi
0x140008ebf  push    rdi
0x140008ec0  push    r15
0x140008ec2  sub     rsp, 30h
0x140008ec6  mov     rax, cs:__security_cookie
0x140008ecd  xor     rax, rsp
0x140008ed0  mov     [rsp+48h+var_20], rax
0x140008ed5  mov     qword ptr [rdx], 0
0x140008edc  mov     rdi, rdx
0x140008edf  mov     eax, [rcx]
0x140008ee1  mov     rsi, rcx
0x140008ee4  mov     [rdx], eax
0x140008ee6  and     eax, 6
0x140008ee9  cmp     al, 6
0x140008eeb  jz      loc_140009022
0x140008ef1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008ef6  mov     ebp, eax
0x140008ef8  mov     [rsp+48h+var_28], 0
0x140008f00  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140008f07  mov     r15d, 40h ; '@'
0x140008f0d  test    rax, rax
0x140008f10  jnz     short loc_140008F1E
0x140008f12  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140008f19  test    rax, rax
0x140008f1c  jz      short loc_140008F68
0x140008f1e  lea     r8, [rsp+48h+var_28]
0x140008f23  xor     edx, edx
0x140008f25  mov     ecx, 308D4A3h
0x140008f2a  call    _guard_dispatch_icall
0x140008f2f  mov     r8d, eax
0x140008f32  mov     edx, eax
0x140008f34  and     r8d, 0FFFFFF3Fh
0x140008f3b  and     eax, r15d
0x140008f3e  and     edx, 80h
0x140008f44  mov     ecx, r8d
0x140008f47  and     ecx, 3
0x140008f4a  shl     ecx, 2
0x140008f4d  or      ecx, eax
0x140008f4f  shl     ecx, 2
0x140008f52  or      ecx, edx
0x140008f54  shl     ecx, 3
0x140008f57  test    r8d, r8d
0x140008f5a  jz      short loc_140008F6A
0x140008f5c  xor     eax, eax
0x140008f5e  cmp     r8d, 2
0x140008f62  cmovz   eax, r15d
0x140008f66  jmp     short loc_140008F6D
0x140008f68  xor     ecx, ecx
0x140008f6a  mov     eax, r15d
0x140008f6d  or      ecx, eax
0x140008f6f  mov     ebx, ecx
0x140008f71  shr     ebx, 6
0x140008f74  and     ebx, 1
0x140008f77  or      ebx, ecx
0x140008f79  test    ebp, ebp
0x140008f7b  jnz     short loc_140008F81
0x140008f7d  mov     [rsp+48h+var_28], ebp
0x140008f81  mov     eax, [rdi]
0x140008f83  cmp     [rsp+48h+var_28], 0
0x140008f88  mov     edx, eax
0x140008f8a  mov     [rdi], eax
0x140008f8c  mov     ecx, eax
0x140008f8e  jz      short loc_140008FC3
0x140008f90  test    dl, 2
0x140008f93  jnz     short loc_140008FC3
0x140008f95  mov     eax, ebx
0x140008f97  xor     eax, ecx
0x140008f99  and     eax, 180h
0x140008f9e  xor     eax, ecx
0x140008fa0  mov     ecx, eax
0x140008fa2  xor     ecx, ebx
0x140008fa4  and     ecx, r15d
0x140008fa7  xor     ecx, eax
0x140008fa9  mov     eax, ecx
0x140008fab  xor     eax, ebx
0x140008fad  and     eax, 1
0x140008fb0  xor     eax, ecx
0x140008fb2  mov     ecx, eax
0x140008fb4  xor     ecx, ebx
0x140008fb6  and     ecx, 800h
0x140008fbc  xor     ecx, eax
0x140008fbe  or      ecx, 2
0x140008fc1  mov     [rdi], ecx
0x140008fc3  test    dl, 4
0x140008fc6  jnz     short loc_140008FD8
0x140008fc8  mov     eax, ebx
0x140008fca  xor     eax, ecx
0x140008fcc  and     eax, 400h
0x140008fd1  xor     ecx, eax
0x140008fd3  or      ecx, 4
0x140008fd6  mov     [rdi], ecx
0x140008fd8  mov     eax, edx
0x140008fda  lock cmpxchg [rsi], ecx
0x140008fde  jnz     short loc_140008F83
0x140008fe0  test    dl, 4
0x140008fe3  jnz     short loc_140008FF2
0x140008fe5  mov     r8d, ebp
0x140008fe8  xor     edx, edx
0x140008fea  mov     rcx, rsi
0x140008fed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140008ff2  test    byte ptr [rdi], 2
0x140008ff5  jnz     short loc_140009022
0x140008ff7  mov     eax, ebx
0x140008ff9  xor     eax, [rdi]
0x140008ffb  and     eax, 180h
0x140009000  xor     eax, [rdi]
0x140009002  mov     ecx, eax
0x140009004  xor     ecx, ebx
0x140009006  and     ecx, r15d
0x140009009  xor     ecx, eax
0x14000900b  mov     edx, ecx
0x14000900d  xor     edx, ebx
0x14000900f  and     edx, 1
0x140009012  xor     edx, ecx
0x140009014  mov     ecx, edx
0x140009016  xor     ecx, ebx
0x140009018  and     ecx, 800h
0x14000901e  xor     ecx, edx
0x140009020  mov     [rdi], ecx
0x140009022  mov     rax, rdi
0x140009025  mov     rcx, [rsp+48h+var_20]
0x14000902a  xor     rcx, rsp; StackCookie
0x14000902d  call    __security_check_cookie
0x140009032  mov     rbx, [rsp+48h+arg_10]
0x140009037  mov     rbp, [rsp+48h+arg_18]
0x14000903c  add     rsp, 30h
0x140009040  pop     r15
0x140009042  pop     rdi
0x140009043  pop     rsi
0x140009044  retn
```
