# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_BACKTRACE>::GetCachedFeatureEnabledState(void)

- ea: `0x140008a54`
- end: `0x140008be4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_BACKTRACE@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005910`
- `0x140008bec`

## callees

- `0x140004168`
- `0x14000422c`
- `0x140008a54`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_BACKTRACE>::GetCachedFeatureEnabledState(
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
    v7 = v6(52799658, 0, &v19);
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
0x140008a54  mov     [rsp+arg_10], rbx
0x140008a59  mov     [rsp+arg_18], rbp
0x140008a5e  push    rsi
0x140008a5f  push    rdi
0x140008a60  push    r15
0x140008a62  sub     rsp, 30h
0x140008a66  mov     rax, cs:__security_cookie
0x140008a6d  xor     rax, rsp
0x140008a70  mov     [rsp+48h+var_20], rax
0x140008a75  mov     qword ptr [rdx], 0
0x140008a7c  mov     rdi, rdx
0x140008a7f  mov     eax, [rcx]
0x140008a81  mov     rsi, rcx
0x140008a84  mov     [rdx], eax
0x140008a86  and     eax, 6
0x140008a89  cmp     al, 6
0x140008a8b  jz      loc_140008BC1
0x140008a91  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008a96  mov     ebp, eax
0x140008a98  mov     [rsp+48h+var_28], 0
0x140008aa0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140008aa7  mov     r15d, 40h ; '@'
0x140008aad  test    rax, rax
0x140008ab0  jnz     short loc_140008ABE
0x140008ab2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140008ab9  test    rax, rax
0x140008abc  jz      short loc_140008B0A
0x140008abe  lea     r8, [rsp+48h+var_28]
0x140008ac3  xor     edx, edx
0x140008ac5  mov     ecx, 325A8AAh
0x140008aca  call    _guard_dispatch_icall
0x140008acf  mov     r8d, eax
0x140008ad2  mov     edx, eax
0x140008ad4  and     r8d, 0FFFFFF3Fh
0x140008adb  and     eax, r15d
0x140008ade  and     edx, 80h
0x140008ae4  mov     ecx, r8d
0x140008ae7  and     ecx, 3
0x140008aea  shl     ecx, 2
0x140008aed  or      ecx, eax
0x140008aef  shl     ecx, 2
0x140008af2  or      ecx, edx
0x140008af4  shl     ecx, 3
0x140008af7  test    r8d, r8d
0x140008afa  jz      short loc_140008B0C
0x140008afc  xor     eax, eax
0x140008afe  cmp     r8d, 2
0x140008b02  cmovz   eax, r15d
0x140008b06  or      eax, ecx
0x140008b08  jmp     short loc_140008B0E
0x140008b0a  xor     ecx, ecx
0x140008b0c  mov     eax, ecx
0x140008b0e  mov     ebx, eax
0x140008b10  shr     ebx, 6
0x140008b13  and     ebx, 1
0x140008b16  or      ebx, eax
0x140008b18  test    ebp, ebp
0x140008b1a  jnz     short loc_140008B20
0x140008b1c  mov     [rsp+48h+var_28], ebp
0x140008b20  mov     eax, [rdi]
0x140008b22  cmp     [rsp+48h+var_28], 0
0x140008b27  mov     edx, eax
0x140008b29  mov     [rdi], eax
0x140008b2b  mov     ecx, eax
0x140008b2d  jz      short loc_140008B62
0x140008b2f  test    dl, 2
0x140008b32  jnz     short loc_140008B62
0x140008b34  mov     eax, ebx
0x140008b36  xor     eax, ecx
0x140008b38  and     eax, 180h
0x140008b3d  xor     eax, ecx
0x140008b3f  mov     ecx, eax
0x140008b41  xor     ecx, ebx
0x140008b43  and     ecx, r15d
0x140008b46  xor     ecx, eax
0x140008b48  mov     eax, ecx
0x140008b4a  xor     eax, ebx
0x140008b4c  and     eax, 1
0x140008b4f  xor     eax, ecx
0x140008b51  mov     ecx, eax
0x140008b53  xor     ecx, ebx
0x140008b55  and     ecx, 800h
0x140008b5b  xor     ecx, eax
0x140008b5d  or      ecx, 2
0x140008b60  mov     [rdi], ecx
0x140008b62  test    dl, 4
0x140008b65  jnz     short loc_140008B77
0x140008b67  mov     eax, ebx
0x140008b69  xor     eax, ecx
0x140008b6b  and     eax, 400h
0x140008b70  xor     ecx, eax
0x140008b72  or      ecx, 4
0x140008b75  mov     [rdi], ecx
0x140008b77  mov     eax, edx
0x140008b79  lock cmpxchg [rsi], ecx
0x140008b7d  jnz     short loc_140008B22
0x140008b7f  test    dl, 4
0x140008b82  jnz     short loc_140008B91
0x140008b84  mov     r8d, ebp
0x140008b87  xor     edx, edx
0x140008b89  mov     rcx, rsi
0x140008b8c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140008b91  test    byte ptr [rdi], 2
0x140008b94  jnz     short loc_140008BC1
0x140008b96  mov     eax, ebx
0x140008b98  xor     eax, [rdi]
0x140008b9a  and     eax, 180h
0x140008b9f  xor     eax, [rdi]
0x140008ba1  mov     ecx, eax
0x140008ba3  xor     ecx, ebx
0x140008ba5  and     ecx, r15d
0x140008ba8  xor     ecx, eax
0x140008baa  mov     edx, ecx
0x140008bac  xor     edx, ebx
0x140008bae  and     edx, 1
0x140008bb1  xor     edx, ecx
0x140008bb3  mov     ecx, edx
0x140008bb5  xor     ecx, ebx
0x140008bb7  and     ecx, 800h
0x140008bbd  xor     ecx, edx
0x140008bbf  mov     [rdi], ecx
0x140008bc1  mov     rax, rdi
0x140008bc4  mov     rcx, [rsp+48h+var_20]
0x140008bc9  xor     rcx, rsp; StackCookie
0x140008bcc  call    __security_check_cookie
0x140008bd1  mov     rbx, [rsp+48h+arg_10]
0x140008bd6  mov     rbp, [rsp+48h+arg_18]
0x140008bdb  add     rsp, 30h
0x140008bdf  pop     r15
0x140008be1  pop     rdi
0x140008be2  pop     rsi
0x140008be3  retn
```
