# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180015060`
- end: `0x1800151b3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `339`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015b2c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000cfc0`
- `0x180015060`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  unsigned int v6; // edx
  int *v7; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v9; // r8d
  int v10; // edi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  wil::details *v18; // [rsp+40h] [rbp+8h] BYREF

  v18 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E287E,
                            v6,
                            (enum FEATURE_CHANGE_TIME)&v18,
                            v7);
    v9 = FeatureEnabledState & 0xFFFFFF3F;
    v10 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v11 = 0;
      if ( v9 == 2 )
        v11 = 64;
    }
    else
    {
      v11 = 64;
    }
    v12 = v11 | v10;
    v13 = *(_DWORD *)a2;
    do
    {
      v14 = (_DWORD)v18 == 0;
      v15 = v13;
      *(_DWORD *)a2 = v13;
      if ( !v14 && (v13 & 2) == 0 )
      {
        v13 = (v13
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v13 ^ v12) & 0x180 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v13;
      }
      if ( (v15 & 4) != 0 )
      {
        v16 = v13;
      }
      else
      {
        v16 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v12) & 0x400 | 4;
        *(_DWORD *)a2 = v16;
      }
      v13 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v12
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v12
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v12
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v12
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
0x180015060  mov     [rsp+arg_8], rbx
0x180015065  mov     [rsp+arg_10], rbp
0x18001506a  mov     [rsp+arg_0], rcx
0x18001506f  push    rsi
0x180015070  push    rdi
0x180015071  push    r15
0x180015073  sub     rsp, 20h
0x180015077  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18001507e  mov     rbx, rdx
0x180015081  mov     qword ptr [rdx], 0
0x180015088  mov     eax, [rsi]
0x18001508a  mov     [rdx], eax
0x18001508c  and     eax, 6
0x18001508f  cmp     al, 6
0x180015091  jz      loc_18001519D
0x180015097  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001509c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800150a1  mov     dword ptr [rsp+38h+arg_0], 0
0x1800150a9  mov     ecx, 37E287Eh; this
0x1800150ae  mov     ebp, eax
0x1800150b0  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800150b5  mov     r8d, eax
0x1800150b8  mov     ecx, eax
0x1800150ba  and     r8d, 0FFFFFF3Fh
0x1800150c1  and     eax, 80h
0x1800150c6  mov     edx, r8d
0x1800150c9  mov     r15d, 40h ; '@'
0x1800150cf  and     edx, 3
0x1800150d2  and     ecx, r15d
0x1800150d5  shl     edx, 2
0x1800150d8  or      edx, ecx
0x1800150da  shl     edx, 2
0x1800150dd  or      edx, eax
0x1800150df  lea     edi, ds:0[rdx*8]
0x1800150e6  test    r8d, r8d
0x1800150e9  jnz     short loc_1800150F0
0x1800150eb  mov     eax, r15d
0x1800150ee  jmp     short loc_1800150FA
0x1800150f0  xor     eax, eax
0x1800150f2  cmp     r8d, 2
0x1800150f6  cmovz   eax, r15d
0x1800150fa  or      edi, eax
0x1800150fc  mov     eax, [rbx]
0x1800150fe  cmp     dword ptr [rsp+38h+arg_0], 0
0x180015103  mov     edx, eax
0x180015105  mov     [rbx], eax
0x180015107  jz      short loc_180015137
0x180015109  test    dl, 2
0x18001510c  jnz     short loc_180015137
0x18001510e  mov     eax, edi
0x180015110  xor     eax, edx
0x180015112  and     eax, 180h
0x180015117  xor     eax, edx
0x180015119  mov     ecx, eax
0x18001511b  xor     ecx, edi
0x18001511d  and     ecx, r15d
0x180015120  xor     ecx, eax
0x180015122  or      ecx, 1
0x180015125  mov     eax, ecx
0x180015127  xor     eax, edi
0x180015129  and     eax, 800h
0x18001512e  xor     eax, ecx
0x180015130  or      eax, 2
0x180015133  mov     [rbx], eax
0x180015135  jmp     short loc_180015139
0x180015137  mov     eax, edx
0x180015139  mov     r8d, edx
0x18001513c  and     r8d, 4
0x180015140  jnz     short loc_180015155
0x180015142  mov     ecx, edi
0x180015144  xor     ecx, eax
0x180015146  and     ecx, 400h
0x18001514c  xor     ecx, eax
0x18001514e  or      ecx, 4
0x180015151  mov     [rbx], ecx
0x180015153  jmp     short loc_180015157
0x180015155  mov     ecx, eax
0x180015157  mov     eax, edx
0x180015159  lock cmpxchg [rsi], ecx
0x18001515d  jnz     short loc_1800150FE
0x18001515f  test    r8d, r8d
0x180015162  jnz     short loc_180015174
0x180015164  mov     r8d, ebp
0x180015167  mov     edx, 3
0x18001516c  mov     rcx, rsi
0x18001516f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015174  test    byte ptr [rbx], 2
0x180015177  jnz     short loc_18001519D
0x180015179  mov     eax, [rbx]
0x18001517b  xor     eax, edi
0x18001517d  and     eax, 180h
0x180015182  xor     eax, [rbx]
0x180015184  mov     ecx, eax
0x180015186  xor     ecx, edi
0x180015188  and     ecx, r15d
0x18001518b  xor     ecx, eax
0x18001518d  or      ecx, 1
0x180015190  mov     eax, ecx
0x180015192  xor     eax, edi
0x180015194  and     eax, 800h
0x180015199  xor     eax, ecx
0x18001519b  mov     [rbx], eax
0x18001519d  mov     rbp, [rsp+38h+arg_10]
0x1800151a2  mov     rax, rbx
0x1800151a5  mov     rbx, [rsp+38h+arg_8]
0x1800151aa  add     rsp, 20h
0x1800151ae  pop     r15
0x1800151b0  pop     rdi
0x1800151b1  pop     rsi
0x1800151b2  retn
```
