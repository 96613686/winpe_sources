# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fee0`
- end: `0x180010057`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010790`

## callees

- `0x18000ee50`
- `0x18000fee0`
- `0x180011648`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
        3,
        v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000fee0  mov     [rsp+arg_8], rbx
0x18000fee5  mov     [rsp+arg_10], rbp
0x18000feea  mov     [rsp+arg_0], rcx
0x18000feef  push    rsi
0x18000fef0  push    rdi
0x18000fef1  push    r15
0x18000fef3  sub     rsp, 20h
0x18000fef7  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000fefe  mov     rbx, rdx
0x18000ff01  mov     qword ptr [rdx], 0
0x18000ff08  mov     eax, [rsi]
0x18000ff0a  mov     [rdx], eax
0x18000ff0c  and     eax, 6
0x18000ff0f  cmp     al, 6
0x18000ff11  jz      loc_180010041
0x18000ff17  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ff1c  mov     ebp, eax
0x18000ff1e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ff26  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ff2d  test    rax, rax
0x18000ff30  jz      short loc_18000FF4A
0x18000ff32  lea     r8, [rsp+38h+arg_0]
0x18000ff37  mov     edx, 3
0x18000ff3c  mov     ecx, 3667CA2h
0x18000ff41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff46  mov     edx, eax
0x18000ff48  jmp     short loc_18000FF58
0x18000ff4a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ff51  test    rax, rax
0x18000ff54  jnz     short loc_18000FF32
0x18000ff56  xor     edx, edx
0x18000ff58  mov     r8d, edx
0x18000ff5b  mov     eax, edx
0x18000ff5d  and     r8d, 0FFFFFF3Fh
0x18000ff64  and     edx, 80h
0x18000ff6a  mov     ecx, r8d
0x18000ff6d  mov     r15d, 40h ; '@'
0x18000ff73  and     ecx, 3
0x18000ff76  and     eax, r15d
0x18000ff79  shl     ecx, 2
0x18000ff7c  or      ecx, eax
0x18000ff7e  shl     ecx, 2
0x18000ff81  or      ecx, edx
0x18000ff83  lea     edi, ds:0[rcx*8]
0x18000ff8a  test    r8d, r8d
0x18000ff8d  jnz     short loc_18000FF94
0x18000ff8f  mov     eax, r15d
0x18000ff92  jmp     short loc_18000FF9E
0x18000ff94  xor     eax, eax
0x18000ff96  cmp     r8d, 2
0x18000ff9a  cmovz   eax, r15d
0x18000ff9e  or      edi, eax
0x18000ffa0  mov     eax, [rbx]
0x18000ffa2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ffa7  mov     edx, eax
0x18000ffa9  mov     [rbx], eax
0x18000ffab  jz      short loc_18000FFDB
0x18000ffad  test    dl, 2
0x18000ffb0  jnz     short loc_18000FFDB
0x18000ffb2  mov     eax, edi
0x18000ffb4  xor     eax, edx
0x18000ffb6  and     eax, 180h
0x18000ffbb  xor     eax, edx
0x18000ffbd  mov     ecx, eax
0x18000ffbf  xor     ecx, edi
0x18000ffc1  and     ecx, r15d
0x18000ffc4  xor     ecx, eax
0x18000ffc6  or      ecx, 1
0x18000ffc9  mov     eax, ecx
0x18000ffcb  xor     eax, edi
0x18000ffcd  and     eax, 800h
0x18000ffd2  xor     eax, ecx
0x18000ffd4  or      eax, 2
0x18000ffd7  mov     [rbx], eax
0x18000ffd9  jmp     short loc_18000FFDD
0x18000ffdb  mov     eax, edx
0x18000ffdd  mov     r8d, edx
0x18000ffe0  and     r8d, 4
0x18000ffe4  jnz     short loc_18000FFF9
0x18000ffe6  mov     ecx, edi
0x18000ffe8  xor     ecx, eax
0x18000ffea  and     ecx, 400h
0x18000fff0  xor     ecx, eax
0x18000fff2  or      ecx, 4
0x18000fff5  mov     [rbx], ecx
0x18000fff7  jmp     short loc_18000FFFB
0x18000fff9  mov     ecx, eax
0x18000fffb  mov     eax, edx
0x18000fffd  lock cmpxchg [rsi], ecx
0x180010001  jnz     short loc_18000FFA2
0x180010003  test    r8d, r8d
0x180010006  jnz     short loc_180010018
0x180010008  mov     r8d, ebp
0x18001000b  mov     edx, 3
0x180010010  mov     rcx, rsi
0x180010013  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180010018  test    byte ptr [rbx], 2
0x18001001b  jnz     short loc_180010041
0x18001001d  mov     eax, [rbx]
0x18001001f  xor     eax, edi
0x180010021  and     eax, 180h
0x180010026  xor     eax, [rbx]
0x180010028  mov     ecx, eax
0x18001002a  xor     ecx, edi
0x18001002c  and     ecx, r15d
0x18001002f  xor     ecx, eax
0x180010031  or      ecx, 1
0x180010034  mov     eax, ecx
0x180010036  xor     eax, edi
0x180010038  and     eax, 800h
0x18001003d  xor     eax, ecx
0x18001003f  mov     [rbx], eax
0x180010041  mov     rbp, [rsp+38h+arg_10]
0x180010046  mov     rax, rbx
0x180010049  mov     rbx, [rsp+38h+arg_8]
0x18001004e  add     rsp, 20h
0x180010052  pop     r15
0x180010054  pop     rdi
0x180010055  pop     rsi
0x180010056  retn
```
