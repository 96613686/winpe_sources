# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180021830`
- end: `0x180021988`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800223b4`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x180021830`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667CA2,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x180021830  mov     [rsp+arg_8], rbx
0x180021835  mov     [rsp+arg_10], rbp
0x18002183a  mov     [rsp+arg_0], rcx
0x18002183f  push    rsi
0x180021840  push    rdi
0x180021841  push    r15
0x180021843  sub     rsp, 20h
0x180021847  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18002184e  mov     rbx, rdx
0x180021851  mov     qword ptr [rdx], 0
0x180021858  mov     eax, [rsi]
0x18002185a  mov     [rdx], eax
0x18002185c  and     eax, 6
0x18002185f  cmp     al, 6
0x180021861  jz      loc_180021972
0x180021867  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002186c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180021871  mov     dword ptr [rsp+38h+arg_0], 0
0x180021879  mov     edx, 3; unsigned int
0x18002187e  mov     ecx, 3667CA2h; this
0x180021883  mov     ebp, eax
0x180021885  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18002188a  mov     r8d, eax
0x18002188d  mov     ecx, eax
0x18002188f  and     r8d, 0FFFFFF3Fh
0x180021896  and     eax, 80h
0x18002189b  mov     edx, r8d
0x18002189e  mov     r15d, 40h ; '@'
0x1800218a4  and     edx, 3
0x1800218a7  and     ecx, r15d
0x1800218aa  shl     edx, 2
0x1800218ad  or      edx, ecx
0x1800218af  shl     edx, 2
0x1800218b2  or      edx, eax
0x1800218b4  lea     edi, ds:0[rdx*8]
0x1800218bb  test    r8d, r8d
0x1800218be  jnz     short loc_1800218C5
0x1800218c0  mov     eax, r15d
0x1800218c3  jmp     short loc_1800218CF
0x1800218c5  xor     eax, eax
0x1800218c7  cmp     r8d, 2
0x1800218cb  cmovz   eax, r15d
0x1800218cf  or      edi, eax
0x1800218d1  mov     eax, [rbx]
0x1800218d3  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800218d8  mov     edx, eax
0x1800218da  mov     [rbx], eax
0x1800218dc  jz      short loc_18002190C
0x1800218de  test    dl, 2
0x1800218e1  jnz     short loc_18002190C
0x1800218e3  mov     eax, edi
0x1800218e5  xor     eax, edx
0x1800218e7  and     eax, 180h
0x1800218ec  xor     eax, edx
0x1800218ee  mov     ecx, eax
0x1800218f0  xor     ecx, edi
0x1800218f2  and     ecx, r15d
0x1800218f5  xor     ecx, eax
0x1800218f7  or      ecx, 1
0x1800218fa  mov     eax, ecx
0x1800218fc  xor     eax, edi
0x1800218fe  and     eax, 800h
0x180021903  xor     eax, ecx
0x180021905  or      eax, 2
0x180021908  mov     [rbx], eax
0x18002190a  jmp     short loc_18002190E
0x18002190c  mov     eax, edx
0x18002190e  mov     r8d, edx
0x180021911  and     r8d, 4
0x180021915  jnz     short loc_18002192A
0x180021917  mov     ecx, edi
0x180021919  xor     ecx, eax
0x18002191b  and     ecx, 400h
0x180021921  xor     ecx, eax
0x180021923  or      ecx, 4
0x180021926  mov     [rbx], ecx
0x180021928  jmp     short loc_18002192C
0x18002192a  mov     ecx, eax
0x18002192c  mov     eax, edx
0x18002192e  lock cmpxchg [rsi], ecx
0x180021932  jnz     short loc_1800218D3
0x180021934  test    r8d, r8d
0x180021937  jnz     short loc_180021949
0x180021939  mov     r8d, ebp
0x18002193c  mov     edx, 3
0x180021941  mov     rcx, rsi
0x180021944  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180021949  test    byte ptr [rbx], 2
0x18002194c  jnz     short loc_180021972
0x18002194e  mov     eax, [rbx]
0x180021950  xor     eax, edi
0x180021952  and     eax, 180h
0x180021957  xor     eax, [rbx]
0x180021959  mov     ecx, eax
0x18002195b  xor     ecx, edi
0x18002195d  and     ecx, r15d
0x180021960  xor     ecx, eax
0x180021962  or      ecx, 1
0x180021965  mov     eax, ecx
0x180021967  xor     eax, edi
0x180021969  and     eax, 800h
0x18002196e  xor     eax, ecx
0x180021970  mov     [rbx], eax
0x180021972  mov     rbp, [rsp+38h+arg_10]
0x180021977  mov     rax, rbx
0x18002197a  mov     rbx, [rsp+38h+arg_8]
0x18002197f  add     rsp, 20h
0x180021983  pop     r15
0x180021985  pop     rdi
0x180021986  pop     rsi
0x180021987  retn
```
