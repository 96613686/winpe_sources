# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800151bc`
- end: `0x18001530f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `339`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f1c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000cfc0`
- `0x1800151bc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E2881,
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
              (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_03_NonSec__descriptor, 3, v5);
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
0x1800151bc  mov     [rsp+arg_8], rbx
0x1800151c1  mov     [rsp+arg_10], rbp
0x1800151c6  mov     [rsp+arg_0], rcx
0x1800151cb  push    rsi
0x1800151cc  push    rdi
0x1800151cd  push    r15
0x1800151cf  sub     rsp, 20h
0x1800151d3  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x1800151da  mov     rbx, rdx
0x1800151dd  mov     qword ptr [rdx], 0
0x1800151e4  mov     eax, [rsi]
0x1800151e6  mov     [rdx], eax
0x1800151e8  and     eax, 6
0x1800151eb  cmp     al, 6
0x1800151ed  jz      loc_1800152F9
0x1800151f3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800151f8  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800151fd  mov     dword ptr [rsp+38h+arg_0], 0
0x180015205  mov     ecx, 37E2881h; this
0x18001520a  mov     ebp, eax
0x18001520c  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015211  mov     r8d, eax
0x180015214  mov     ecx, eax
0x180015216  and     r8d, 0FFFFFF3Fh
0x18001521d  and     eax, 80h
0x180015222  mov     edx, r8d
0x180015225  mov     r15d, 40h ; '@'
0x18001522b  and     edx, 3
0x18001522e  and     ecx, r15d
0x180015231  shl     edx, 2
0x180015234  or      edx, ecx
0x180015236  shl     edx, 2
0x180015239  or      edx, eax
0x18001523b  lea     edi, ds:0[rdx*8]
0x180015242  test    r8d, r8d
0x180015245  jnz     short loc_18001524C
0x180015247  mov     eax, r15d
0x18001524a  jmp     short loc_180015256
0x18001524c  xor     eax, eax
0x18001524e  cmp     r8d, 2
0x180015252  cmovz   eax, r15d
0x180015256  or      edi, eax
0x180015258  mov     eax, [rbx]
0x18001525a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001525f  mov     edx, eax
0x180015261  mov     [rbx], eax
0x180015263  jz      short loc_180015293
0x180015265  test    dl, 2
0x180015268  jnz     short loc_180015293
0x18001526a  mov     eax, edi
0x18001526c  xor     eax, edx
0x18001526e  and     eax, 180h
0x180015273  xor     eax, edx
0x180015275  mov     ecx, eax
0x180015277  xor     ecx, edi
0x180015279  and     ecx, r15d
0x18001527c  xor     ecx, eax
0x18001527e  or      ecx, 1
0x180015281  mov     eax, ecx
0x180015283  xor     eax, edi
0x180015285  and     eax, 800h
0x18001528a  xor     eax, ecx
0x18001528c  or      eax, 2
0x18001528f  mov     [rbx], eax
0x180015291  jmp     short loc_180015295
0x180015293  mov     eax, edx
0x180015295  mov     r8d, edx
0x180015298  and     r8d, 4
0x18001529c  jnz     short loc_1800152B1
0x18001529e  mov     ecx, edi
0x1800152a0  xor     ecx, eax
0x1800152a2  and     ecx, 400h
0x1800152a8  xor     ecx, eax
0x1800152aa  or      ecx, 4
0x1800152ad  mov     [rbx], ecx
0x1800152af  jmp     short loc_1800152B3
0x1800152b1  mov     ecx, eax
0x1800152b3  mov     eax, edx
0x1800152b5  lock cmpxchg [rsi], ecx
0x1800152b9  jnz     short loc_18001525A
0x1800152bb  test    r8d, r8d
0x1800152be  jnz     short loc_1800152D0
0x1800152c0  mov     r8d, ebp
0x1800152c3  mov     edx, 3
0x1800152c8  mov     rcx, rsi
0x1800152cb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800152d0  test    byte ptr [rbx], 2
0x1800152d3  jnz     short loc_1800152F9
0x1800152d5  mov     eax, [rbx]
0x1800152d7  xor     eax, edi
0x1800152d9  and     eax, 180h
0x1800152de  xor     eax, [rbx]
0x1800152e0  mov     ecx, eax
0x1800152e2  xor     ecx, edi
0x1800152e4  and     ecx, r15d
0x1800152e7  xor     ecx, eax
0x1800152e9  or      ecx, 1
0x1800152ec  mov     eax, ecx
0x1800152ee  xor     eax, edi
0x1800152f0  and     eax, 800h
0x1800152f5  xor     eax, ecx
0x1800152f7  mov     [rbx], eax
0x1800152f9  mov     rbp, [rsp+38h+arg_10]
0x1800152fe  mov     rax, rbx
0x180015301  mov     rbx, [rsp+38h+arg_8]
0x180015306  add     rsp, 20h
0x18001530a  pop     r15
0x18001530c  pop     rdi
0x18001530d  pop     rsi
0x18001530e  retn
```
