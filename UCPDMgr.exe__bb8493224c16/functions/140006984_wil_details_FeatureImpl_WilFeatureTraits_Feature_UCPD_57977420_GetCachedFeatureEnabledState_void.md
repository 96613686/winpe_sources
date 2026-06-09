# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57977420>::GetCachedFeatureEnabledState(void)

- ea: `0x140006984`
- end: `0x140006b14`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_57977420@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000558c`
- `0x140006b1c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140006984`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_57977420>::GetCachedFeatureEnabledState(
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
    v7 = v6(57977420, 0, &v19);
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
0x140006984  mov     [rsp+arg_10], rbx
0x140006989  mov     [rsp+arg_18], rbp
0x14000698e  push    rsi
0x14000698f  push    rdi
0x140006990  push    r15
0x140006992  sub     rsp, 30h
0x140006996  mov     rax, cs:__security_cookie
0x14000699d  xor     rax, rsp
0x1400069a0  mov     [rsp+48h+var_20], rax
0x1400069a5  mov     qword ptr [rdx], 0
0x1400069ac  mov     rdi, rdx
0x1400069af  mov     eax, [rcx]
0x1400069b1  mov     rsi, rcx
0x1400069b4  mov     [rdx], eax
0x1400069b6  and     eax, 6
0x1400069b9  cmp     al, 6
0x1400069bb  jz      loc_140006AF1
0x1400069c1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400069c6  mov     ebp, eax
0x1400069c8  mov     [rsp+48h+var_28], 0
0x1400069d0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400069d7  mov     r15d, 40h ; '@'
0x1400069dd  test    rax, rax
0x1400069e0  jnz     short loc_1400069EE
0x1400069e2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400069e9  test    rax, rax
0x1400069ec  jz      short loc_140006A3A
0x1400069ee  lea     r8, [rsp+48h+var_28]
0x1400069f3  xor     edx, edx
0x1400069f5  mov     ecx, 374AA4Ch
0x1400069fa  call    _guard_dispatch_icall
0x1400069ff  mov     r8d, eax
0x140006a02  mov     edx, eax
0x140006a04  and     r8d, 0FFFFFF3Fh
0x140006a0b  and     eax, r15d
0x140006a0e  and     edx, 80h
0x140006a14  mov     ecx, r8d
0x140006a17  and     ecx, 3
0x140006a1a  shl     ecx, 2
0x140006a1d  or      ecx, eax
0x140006a1f  shl     ecx, 2
0x140006a22  or      ecx, edx
0x140006a24  shl     ecx, 3
0x140006a27  test    r8d, r8d
0x140006a2a  jz      short loc_140006A3C
0x140006a2c  xor     eax, eax
0x140006a2e  cmp     r8d, 2
0x140006a32  cmovz   eax, r15d
0x140006a36  or      eax, ecx
0x140006a38  jmp     short loc_140006A3E
0x140006a3a  xor     ecx, ecx
0x140006a3c  mov     eax, ecx
0x140006a3e  mov     ebx, eax
0x140006a40  shr     ebx, 6
0x140006a43  and     ebx, 1
0x140006a46  or      ebx, eax
0x140006a48  test    ebp, ebp
0x140006a4a  jnz     short loc_140006A50
0x140006a4c  mov     [rsp+48h+var_28], ebp
0x140006a50  mov     eax, [rdi]
0x140006a52  cmp     [rsp+48h+var_28], 0
0x140006a57  mov     edx, eax
0x140006a59  mov     [rdi], eax
0x140006a5b  mov     ecx, eax
0x140006a5d  jz      short loc_140006A92
0x140006a5f  test    dl, 2
0x140006a62  jnz     short loc_140006A92
0x140006a64  mov     eax, ebx
0x140006a66  xor     eax, ecx
0x140006a68  and     eax, 180h
0x140006a6d  xor     eax, ecx
0x140006a6f  mov     ecx, eax
0x140006a71  xor     ecx, ebx
0x140006a73  and     ecx, r15d
0x140006a76  xor     ecx, eax
0x140006a78  mov     eax, ecx
0x140006a7a  xor     eax, ebx
0x140006a7c  and     eax, 1
0x140006a7f  xor     eax, ecx
0x140006a81  mov     ecx, eax
0x140006a83  xor     ecx, ebx
0x140006a85  and     ecx, 800h
0x140006a8b  xor     ecx, eax
0x140006a8d  or      ecx, 2
0x140006a90  mov     [rdi], ecx
0x140006a92  test    dl, 4
0x140006a95  jnz     short loc_140006AA7
0x140006a97  mov     eax, ebx
0x140006a99  xor     eax, ecx
0x140006a9b  and     eax, 400h
0x140006aa0  xor     ecx, eax
0x140006aa2  or      ecx, 4
0x140006aa5  mov     [rdi], ecx
0x140006aa7  mov     eax, edx
0x140006aa9  lock cmpxchg [rsi], ecx
0x140006aad  jnz     short loc_140006A52
0x140006aaf  test    dl, 4
0x140006ab2  jnz     short loc_140006AC1
0x140006ab4  mov     r8d, ebp
0x140006ab7  xor     edx, edx
0x140006ab9  mov     rcx, rsi
0x140006abc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006ac1  test    byte ptr [rdi], 2
0x140006ac4  jnz     short loc_140006AF1
0x140006ac6  mov     eax, ebx
0x140006ac8  xor     eax, [rdi]
0x140006aca  and     eax, 180h
0x140006acf  xor     eax, [rdi]
0x140006ad1  mov     ecx, eax
0x140006ad3  xor     ecx, ebx
0x140006ad5  and     ecx, r15d
0x140006ad8  xor     ecx, eax
0x140006ada  mov     edx, ecx
0x140006adc  xor     edx, ebx
0x140006ade  and     edx, 1
0x140006ae1  xor     edx, ecx
0x140006ae3  mov     ecx, edx
0x140006ae5  xor     ecx, ebx
0x140006ae7  and     ecx, 800h
0x140006aed  xor     ecx, edx
0x140006aef  mov     [rdi], ecx
0x140006af1  mov     rax, rdi
0x140006af4  mov     rcx, [rsp+48h+var_20]
0x140006af9  xor     rcx, rsp; StackCookie
0x140006afc  call    __security_check_cookie
0x140006b01  mov     rbx, [rsp+48h+arg_10]
0x140006b06  mov     rbp, [rsp+48h+arg_18]
0x140006b0b  add     rsp, 30h
0x140006b0f  pop     r15
0x140006b11  pop     rdi
0x140006b12  pop     rsi
0x140006b13  retn
```
