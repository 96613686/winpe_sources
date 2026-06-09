# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e770`
- end: `0x18000e8e7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f020`

## callees

- `0x18000d6e0`
- `0x18000e770`
- `0x18000ff38`
- `0x180013010`

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
0x18000e770  mov     [rsp+arg_8], rbx
0x18000e775  mov     [rsp+arg_10], rbp
0x18000e77a  mov     [rsp+arg_0], rcx
0x18000e77f  push    rsi
0x18000e780  push    rdi
0x18000e781  push    r15
0x18000e783  sub     rsp, 20h
0x18000e787  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000e78e  mov     rbx, rdx
0x18000e791  mov     qword ptr [rdx], 0
0x18000e798  mov     eax, [rsi]
0x18000e79a  mov     [rdx], eax
0x18000e79c  and     eax, 6
0x18000e79f  cmp     al, 6
0x18000e7a1  jz      loc_18000E8D1
0x18000e7a7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e7ac  mov     ebp, eax
0x18000e7ae  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e7b6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e7bd  test    rax, rax
0x18000e7c0  jz      short loc_18000E7DA
0x18000e7c2  lea     r8, [rsp+38h+arg_0]
0x18000e7c7  mov     edx, 3
0x18000e7cc  mov     ecx, 3667CA2h
0x18000e7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d6  mov     edx, eax
0x18000e7d8  jmp     short loc_18000E7E8
0x18000e7da  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e7e1  test    rax, rax
0x18000e7e4  jnz     short loc_18000E7C2
0x18000e7e6  xor     edx, edx
0x18000e7e8  mov     r8d, edx
0x18000e7eb  mov     eax, edx
0x18000e7ed  and     r8d, 0FFFFFF3Fh
0x18000e7f4  and     edx, 80h
0x18000e7fa  mov     ecx, r8d
0x18000e7fd  mov     r15d, 40h ; '@'
0x18000e803  and     ecx, 3
0x18000e806  and     eax, r15d
0x18000e809  shl     ecx, 2
0x18000e80c  or      ecx, eax
0x18000e80e  shl     ecx, 2
0x18000e811  or      ecx, edx
0x18000e813  lea     edi, ds:0[rcx*8]
0x18000e81a  test    r8d, r8d
0x18000e81d  jnz     short loc_18000E824
0x18000e81f  mov     eax, r15d
0x18000e822  jmp     short loc_18000E82E
0x18000e824  xor     eax, eax
0x18000e826  cmp     r8d, 2
0x18000e82a  cmovz   eax, r15d
0x18000e82e  or      edi, eax
0x18000e830  mov     eax, [rbx]
0x18000e832  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e837  mov     edx, eax
0x18000e839  mov     [rbx], eax
0x18000e83b  jz      short loc_18000E86B
0x18000e83d  test    dl, 2
0x18000e840  jnz     short loc_18000E86B
0x18000e842  mov     eax, edi
0x18000e844  xor     eax, edx
0x18000e846  and     eax, 180h
0x18000e84b  xor     eax, edx
0x18000e84d  mov     ecx, eax
0x18000e84f  xor     ecx, edi
0x18000e851  and     ecx, r15d
0x18000e854  xor     ecx, eax
0x18000e856  or      ecx, 1
0x18000e859  mov     eax, ecx
0x18000e85b  xor     eax, edi
0x18000e85d  and     eax, 800h
0x18000e862  xor     eax, ecx
0x18000e864  or      eax, 2
0x18000e867  mov     [rbx], eax
0x18000e869  jmp     short loc_18000E86D
0x18000e86b  mov     eax, edx
0x18000e86d  mov     r8d, edx
0x18000e870  and     r8d, 4
0x18000e874  jnz     short loc_18000E889
0x18000e876  mov     ecx, edi
0x18000e878  xor     ecx, eax
0x18000e87a  and     ecx, 400h
0x18000e880  xor     ecx, eax
0x18000e882  or      ecx, 4
0x18000e885  mov     [rbx], ecx
0x18000e887  jmp     short loc_18000E88B
0x18000e889  mov     ecx, eax
0x18000e88b  mov     eax, edx
0x18000e88d  lock cmpxchg [rsi], ecx
0x18000e891  jnz     short loc_18000E832
0x18000e893  test    r8d, r8d
0x18000e896  jnz     short loc_18000E8A8
0x18000e898  mov     r8d, ebp
0x18000e89b  mov     edx, 3
0x18000e8a0  mov     rcx, rsi
0x18000e8a3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e8a8  test    byte ptr [rbx], 2
0x18000e8ab  jnz     short loc_18000E8D1
0x18000e8ad  mov     eax, [rbx]
0x18000e8af  xor     eax, edi
0x18000e8b1  and     eax, 180h
0x18000e8b6  xor     eax, [rbx]
0x18000e8b8  mov     ecx, eax
0x18000e8ba  xor     ecx, edi
0x18000e8bc  and     ecx, r15d
0x18000e8bf  xor     ecx, eax
0x18000e8c1  or      ecx, 1
0x18000e8c4  mov     eax, ecx
0x18000e8c6  xor     eax, edi
0x18000e8c8  and     eax, 800h
0x18000e8cd  xor     eax, ecx
0x18000e8cf  mov     [rbx], eax
0x18000e8d1  mov     rbp, [rsp+38h+arg_10]
0x18000e8d6  mov     rax, rbx
0x18000e8d9  mov     rbx, [rsp+38h+arg_8]
0x18000e8de  add     rsp, 20h
0x18000e8e2  pop     r15
0x18000e8e4  pop     rdi
0x18000e8e5  pop     rsi
0x18000e8e6  retn
```
