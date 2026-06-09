# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800257a0`
- end: `0x180025917`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025990`
- `0x180025ad8`

## callees

- `0x180005b50`
- `0x1800097b0`
- `0x1800257a0`
- `0x18002b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3u,
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
0x1800257a0  mov     [rsp+arg_8], rbx
0x1800257a5  mov     [rsp+arg_10], rbp
0x1800257aa  mov     [rsp+arg_0], rcx
0x1800257af  push    rsi
0x1800257b0  push    rdi
0x1800257b1  push    r15
0x1800257b3  sub     rsp, 20h
0x1800257b7  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800257be  mov     rbx, rdx
0x1800257c1  mov     qword ptr [rdx], 0
0x1800257c8  mov     eax, [rsi]
0x1800257ca  mov     [rdx], eax
0x1800257cc  and     eax, 6
0x1800257cf  cmp     al, 6
0x1800257d1  jz      loc_180025901
0x1800257d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800257dc  mov     ebp, eax
0x1800257de  mov     dword ptr [rsp+38h+arg_0], 0
0x1800257e6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800257ed  test    rax, rax
0x1800257f0  jz      short loc_18002580A
0x1800257f2  lea     r8, [rsp+38h+arg_0]
0x1800257f7  mov     edx, 3
0x1800257fc  mov     ecx, 2F29A04h
0x180025801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025806  mov     edx, eax
0x180025808  jmp     short loc_180025818
0x18002580a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180025811  test    rax, rax
0x180025814  jnz     short loc_1800257F2
0x180025816  xor     edx, edx
0x180025818  mov     r8d, edx
0x18002581b  mov     eax, edx
0x18002581d  and     r8d, 0FFFFFF3Fh
0x180025824  and     edx, 80h
0x18002582a  mov     ecx, r8d
0x18002582d  mov     r15d, 40h ; '@'
0x180025833  and     ecx, 3
0x180025836  and     eax, r15d
0x180025839  shl     ecx, 2
0x18002583c  or      ecx, eax
0x18002583e  shl     ecx, 2
0x180025841  or      ecx, edx
0x180025843  lea     edi, ds:0[rcx*8]
0x18002584a  test    r8d, r8d
0x18002584d  jnz     short loc_180025854
0x18002584f  mov     eax, r15d
0x180025852  jmp     short loc_18002585E
0x180025854  xor     eax, eax
0x180025856  cmp     r8d, 2
0x18002585a  cmovz   eax, r15d
0x18002585e  or      edi, eax
0x180025860  mov     eax, [rbx]
0x180025862  cmp     dword ptr [rsp+38h+arg_0], 0
0x180025867  mov     edx, eax
0x180025869  mov     [rbx], eax
0x18002586b  jz      short loc_18002589B
0x18002586d  test    dl, 2
0x180025870  jnz     short loc_18002589B
0x180025872  mov     eax, edi
0x180025874  xor     eax, edx
0x180025876  and     eax, 180h
0x18002587b  xor     eax, edx
0x18002587d  mov     ecx, eax
0x18002587f  xor     ecx, edi
0x180025881  and     ecx, r15d
0x180025884  xor     ecx, eax
0x180025886  or      ecx, 1
0x180025889  mov     eax, ecx
0x18002588b  xor     eax, edi
0x18002588d  and     eax, 800h
0x180025892  xor     eax, ecx
0x180025894  or      eax, 2
0x180025897  mov     [rbx], eax
0x180025899  jmp     short loc_18002589D
0x18002589b  mov     eax, edx
0x18002589d  mov     r8d, edx
0x1800258a0  and     r8d, 4
0x1800258a4  jnz     short loc_1800258B9
0x1800258a6  mov     ecx, edi
0x1800258a8  xor     ecx, eax
0x1800258aa  and     ecx, 400h
0x1800258b0  xor     ecx, eax
0x1800258b2  or      ecx, 4
0x1800258b5  mov     [rbx], ecx
0x1800258b7  jmp     short loc_1800258BB
0x1800258b9  mov     ecx, eax
0x1800258bb  mov     eax, edx
0x1800258bd  lock cmpxchg [rsi], ecx
0x1800258c1  jnz     short loc_180025862
0x1800258c3  test    r8d, r8d
0x1800258c6  jnz     short loc_1800258D8
0x1800258c8  mov     r8d, ebp
0x1800258cb  mov     edx, 3
0x1800258d0  mov     rcx, rsi
0x1800258d3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800258d8  test    byte ptr [rbx], 2
0x1800258db  jnz     short loc_180025901
0x1800258dd  mov     eax, [rbx]
0x1800258df  xor     eax, edi
0x1800258e1  and     eax, 180h
0x1800258e6  xor     eax, [rbx]
0x1800258e8  mov     ecx, eax
0x1800258ea  xor     ecx, edi
0x1800258ec  and     ecx, r15d
0x1800258ef  xor     ecx, eax
0x1800258f1  or      ecx, 1
0x1800258f4  mov     eax, ecx
0x1800258f6  xor     eax, edi
0x1800258f8  and     eax, 800h
0x1800258fd  xor     eax, ecx
0x1800258ff  mov     [rbx], eax
0x180025901  mov     rbp, [rsp+38h+arg_10]
0x180025906  mov     rax, rbx
0x180025909  mov     rbx, [rsp+38h+arg_8]
0x18002590e  add     rsp, 20h
0x180025912  pop     r15
0x180025914  pop     rdi
0x180025915  pop     rsi
0x180025916  retn
```
