# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800134f4`
- end: `0x180013661`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014abc`

## callees

- `0x180004a48`
- `0x180008344`
- `0x1800134f4`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x1800134f4  mov     [rsp+arg_8], rbx
0x1800134f9  mov     [rsp+arg_10], rbp
0x1800134fe  mov     [rsp+arg_0], rcx
0x180013503  push    rsi
0x180013504  push    rdi
0x180013505  push    r15
0x180013507  sub     rsp, 20h
0x18001350b  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180013512  mov     rbx, rdx
0x180013515  mov     qword ptr [rdx], 0
0x18001351c  mov     eax, [rsi]
0x18001351e  mov     [rdx], eax
0x180013520  and     eax, 6
0x180013523  cmp     al, 6
0x180013525  jz      loc_18001364B
0x18001352b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013530  mov     ebp, eax
0x180013532  mov     dword ptr [rsp+38h+arg_0], 0
0x18001353a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013541  test    rax, rax
0x180013544  jz      short loc_18001355E
0x180013546  lea     r8, [rsp+38h+arg_0]
0x18001354b  mov     edx, 3
0x180013550  mov     ecx, 2AF34FDh
0x180013555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001355a  mov     edx, eax
0x18001355c  jmp     short loc_18001356C
0x18001355e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013565  test    rax, rax
0x180013568  jnz     short loc_180013546
0x18001356a  xor     edx, edx
0x18001356c  mov     r8d, edx
0x18001356f  mov     eax, edx
0x180013571  and     r8d, 0FFFFFF3Fh
0x180013578  and     edx, 80h
0x18001357e  mov     ecx, r8d
0x180013581  mov     r15d, 40h ; '@'
0x180013587  and     ecx, 3
0x18001358a  and     eax, r15d
0x18001358d  shl     ecx, 2
0x180013590  or      ecx, eax
0x180013592  shl     ecx, 2
0x180013595  or      ecx, edx
0x180013597  lea     edi, ds:0[rcx*8]
0x18001359e  test    r8d, r8d
0x1800135a1  jnz     short loc_1800135A8
0x1800135a3  mov     eax, r15d
0x1800135a6  jmp     short loc_1800135B2
0x1800135a8  xor     eax, eax
0x1800135aa  cmp     r8d, 2
0x1800135ae  cmovz   eax, r15d
0x1800135b2  or      edi, eax
0x1800135b4  mov     eax, [rbx]
0x1800135b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800135bb  mov     edx, eax
0x1800135bd  mov     [rbx], eax
0x1800135bf  jz      short loc_1800135EB
0x1800135c1  test    dl, 2
0x1800135c4  jnz     short loc_1800135EB
0x1800135c6  xor     eax, edi
0x1800135c8  and     eax, 180h
0x1800135cd  xor     eax, edx
0x1800135cf  mov     ecx, eax
0x1800135d1  xor     ecx, edi
0x1800135d3  and     ecx, r15d
0x1800135d6  xor     ecx, eax
0x1800135d8  or      ecx, 1
0x1800135db  mov     eax, ecx
0x1800135dd  xor     eax, edi
0x1800135df  and     eax, 800h
0x1800135e4  xor     eax, ecx
0x1800135e6  or      eax, 2
0x1800135e9  mov     [rbx], eax
0x1800135eb  mov     r8d, edx
0x1800135ee  mov     ecx, eax
0x1800135f0  and     r8d, 4
0x1800135f4  jnz     short loc_180013605
0x1800135f6  xor     ecx, edi
0x1800135f8  and     ecx, 400h
0x1800135fe  xor     ecx, eax
0x180013600  or      ecx, 4
0x180013603  mov     [rbx], ecx
0x180013605  mov     eax, edx
0x180013607  lock cmpxchg [rsi], ecx
0x18001360b  jnz     short loc_1800135B6
0x18001360d  test    r8d, r8d
0x180013610  jnz     short loc_180013622
0x180013612  mov     r8d, ebp
0x180013615  mov     edx, 3
0x18001361a  mov     rcx, rsi
0x18001361d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013622  test    byte ptr [rbx], 2
0x180013625  jnz     short loc_18001364B
0x180013627  mov     eax, [rbx]
0x180013629  xor     eax, edi
0x18001362b  and     eax, 180h
0x180013630  xor     eax, [rbx]
0x180013632  mov     ecx, eax
0x180013634  xor     ecx, edi
0x180013636  and     ecx, r15d
0x180013639  xor     ecx, eax
0x18001363b  or      ecx, 1
0x18001363e  mov     eax, ecx
0x180013640  xor     eax, edi
0x180013642  and     eax, 800h
0x180013647  xor     eax, ecx
0x180013649  mov     [rbx], eax
0x18001364b  mov     rbp, [rsp+38h+arg_10]
0x180013650  mov     rax, rbx
0x180013653  mov     rbx, [rsp+38h+arg_8]
0x180013658  add     rsp, 20h
0x18001365c  pop     r15
0x18001365e  pop     rdi
0x18001365f  pop     rsi
0x180013660  retn
```
