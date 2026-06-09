# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59940760>::GetCachedFeatureEnabledState(void)

- ea: `0x140005e94`
- end: `0x140006024`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_59940760@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005460`
- `0x14000602c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140005e94`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_59940760>::GetCachedFeatureEnabledState(
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
    v7 = v6(59940760, 0, &v19);
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
0x140005e94  mov     [rsp+arg_10], rbx
0x140005e99  mov     [rsp+arg_18], rbp
0x140005e9e  push    rsi
0x140005e9f  push    rdi
0x140005ea0  push    r15
0x140005ea2  sub     rsp, 30h
0x140005ea6  mov     rax, cs:__security_cookie
0x140005ead  xor     rax, rsp
0x140005eb0  mov     [rsp+48h+var_20], rax
0x140005eb5  mov     qword ptr [rdx], 0
0x140005ebc  mov     rdi, rdx
0x140005ebf  mov     eax, [rcx]
0x140005ec1  mov     rsi, rcx
0x140005ec4  mov     [rdx], eax
0x140005ec6  and     eax, 6
0x140005ec9  cmp     al, 6
0x140005ecb  jz      loc_140006001
0x140005ed1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140005ed6  mov     ebp, eax
0x140005ed8  mov     [rsp+48h+var_28], 0
0x140005ee0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005ee7  mov     r15d, 40h ; '@'
0x140005eed  test    rax, rax
0x140005ef0  jnz     short loc_140005EFE
0x140005ef2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005ef9  test    rax, rax
0x140005efc  jz      short loc_140005F4A
0x140005efe  lea     r8, [rsp+48h+var_28]
0x140005f03  xor     edx, edx
0x140005f05  mov     ecx, 3929F98h
0x140005f0a  call    _guard_dispatch_icall
0x140005f0f  mov     r8d, eax
0x140005f12  mov     edx, eax
0x140005f14  and     r8d, 0FFFFFF3Fh
0x140005f1b  and     eax, r15d
0x140005f1e  and     edx, 80h
0x140005f24  mov     ecx, r8d
0x140005f27  and     ecx, 3
0x140005f2a  shl     ecx, 2
0x140005f2d  or      ecx, eax
0x140005f2f  shl     ecx, 2
0x140005f32  or      ecx, edx
0x140005f34  shl     ecx, 3
0x140005f37  test    r8d, r8d
0x140005f3a  jz      short loc_140005F4C
0x140005f3c  xor     eax, eax
0x140005f3e  cmp     r8d, 2
0x140005f42  cmovz   eax, r15d
0x140005f46  or      eax, ecx
0x140005f48  jmp     short loc_140005F4E
0x140005f4a  xor     ecx, ecx
0x140005f4c  mov     eax, ecx
0x140005f4e  mov     ebx, eax
0x140005f50  shr     ebx, 6
0x140005f53  and     ebx, 1
0x140005f56  or      ebx, eax
0x140005f58  test    ebp, ebp
0x140005f5a  jnz     short loc_140005F60
0x140005f5c  mov     [rsp+48h+var_28], ebp
0x140005f60  mov     eax, [rdi]
0x140005f62  cmp     [rsp+48h+var_28], 0
0x140005f67  mov     edx, eax
0x140005f69  mov     [rdi], eax
0x140005f6b  mov     ecx, eax
0x140005f6d  jz      short loc_140005FA2
0x140005f6f  test    dl, 2
0x140005f72  jnz     short loc_140005FA2
0x140005f74  mov     eax, ebx
0x140005f76  xor     eax, ecx
0x140005f78  and     eax, 180h
0x140005f7d  xor     eax, ecx
0x140005f7f  mov     ecx, eax
0x140005f81  xor     ecx, ebx
0x140005f83  and     ecx, r15d
0x140005f86  xor     ecx, eax
0x140005f88  mov     eax, ecx
0x140005f8a  xor     eax, ebx
0x140005f8c  and     eax, 1
0x140005f8f  xor     eax, ecx
0x140005f91  mov     ecx, eax
0x140005f93  xor     ecx, ebx
0x140005f95  and     ecx, 800h
0x140005f9b  xor     ecx, eax
0x140005f9d  or      ecx, 2
0x140005fa0  mov     [rdi], ecx
0x140005fa2  test    dl, 4
0x140005fa5  jnz     short loc_140005FB7
0x140005fa7  mov     eax, ebx
0x140005fa9  xor     eax, ecx
0x140005fab  and     eax, 400h
0x140005fb0  xor     ecx, eax
0x140005fb2  or      ecx, 4
0x140005fb5  mov     [rdi], ecx
0x140005fb7  mov     eax, edx
0x140005fb9  lock cmpxchg [rsi], ecx
0x140005fbd  jnz     short loc_140005F62
0x140005fbf  test    dl, 4
0x140005fc2  jnz     short loc_140005FD1
0x140005fc4  mov     r8d, ebp
0x140005fc7  xor     edx, edx
0x140005fc9  mov     rcx, rsi
0x140005fcc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140005fd1  test    byte ptr [rdi], 2
0x140005fd4  jnz     short loc_140006001
0x140005fd6  mov     eax, ebx
0x140005fd8  xor     eax, [rdi]
0x140005fda  and     eax, 180h
0x140005fdf  xor     eax, [rdi]
0x140005fe1  mov     ecx, eax
0x140005fe3  xor     ecx, ebx
0x140005fe5  and     ecx, r15d
0x140005fe8  xor     ecx, eax
0x140005fea  mov     edx, ecx
0x140005fec  xor     edx, ebx
0x140005fee  and     edx, 1
0x140005ff1  xor     edx, ecx
0x140005ff3  mov     ecx, edx
0x140005ff5  xor     ecx, ebx
0x140005ff7  and     ecx, 800h
0x140005ffd  xor     ecx, edx
0x140005fff  mov     [rdi], ecx
0x140006001  mov     rax, rdi
0x140006004  mov     rcx, [rsp+48h+var_20]
0x140006009  xor     rcx, rsp; StackCookie
0x14000600c  call    __security_check_cookie
0x140006011  mov     rbx, [rsp+48h+arg_10]
0x140006016  mov     rbp, [rsp+48h+arg_18]
0x14000601b  add     rsp, 30h
0x14000601f  pop     r15
0x140006021  pop     rdi
0x140006022  pop     rsi
0x140006023  retn
```
