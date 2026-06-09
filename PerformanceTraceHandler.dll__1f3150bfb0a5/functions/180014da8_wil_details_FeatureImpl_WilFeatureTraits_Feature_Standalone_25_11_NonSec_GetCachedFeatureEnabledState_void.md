# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180014da8`
- end: `0x180014efb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `339`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015c7c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000cfc0`
- `0x180014da8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34FD,
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
              (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v5);
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
0x180014da8  mov     [rsp+arg_8], rbx
0x180014dad  mov     [rsp+arg_10], rbp
0x180014db2  mov     [rsp+arg_0], rcx
0x180014db7  push    rsi
0x180014db8  push    rdi
0x180014db9  push    r15
0x180014dbb  sub     rsp, 20h
0x180014dbf  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180014dc6  mov     rbx, rdx
0x180014dc9  mov     qword ptr [rdx], 0
0x180014dd0  mov     eax, [rsi]
0x180014dd2  mov     [rdx], eax
0x180014dd4  and     eax, 6
0x180014dd7  cmp     al, 6
0x180014dd9  jz      loc_180014EE5
0x180014ddf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014de4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180014de9  mov     dword ptr [rsp+38h+arg_0], 0
0x180014df1  mov     ecx, 2AF34FDh; this
0x180014df6  mov     ebp, eax
0x180014df8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014dfd  mov     r8d, eax
0x180014e00  mov     ecx, eax
0x180014e02  and     r8d, 0FFFFFF3Fh
0x180014e09  and     eax, 80h
0x180014e0e  mov     edx, r8d
0x180014e11  mov     r15d, 40h ; '@'
0x180014e17  and     edx, 3
0x180014e1a  and     ecx, r15d
0x180014e1d  shl     edx, 2
0x180014e20  or      edx, ecx
0x180014e22  shl     edx, 2
0x180014e25  or      edx, eax
0x180014e27  lea     edi, ds:0[rdx*8]
0x180014e2e  test    r8d, r8d
0x180014e31  jnz     short loc_180014E38
0x180014e33  mov     eax, r15d
0x180014e36  jmp     short loc_180014E42
0x180014e38  xor     eax, eax
0x180014e3a  cmp     r8d, 2
0x180014e3e  cmovz   eax, r15d
0x180014e42  or      edi, eax
0x180014e44  mov     eax, [rbx]
0x180014e46  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014e4b  mov     edx, eax
0x180014e4d  mov     [rbx], eax
0x180014e4f  jz      short loc_180014E7F
0x180014e51  test    dl, 2
0x180014e54  jnz     short loc_180014E7F
0x180014e56  mov     eax, edi
0x180014e58  xor     eax, edx
0x180014e5a  and     eax, 180h
0x180014e5f  xor     eax, edx
0x180014e61  mov     ecx, eax
0x180014e63  xor     ecx, edi
0x180014e65  and     ecx, r15d
0x180014e68  xor     ecx, eax
0x180014e6a  or      ecx, 1
0x180014e6d  mov     eax, ecx
0x180014e6f  xor     eax, edi
0x180014e71  and     eax, 800h
0x180014e76  xor     eax, ecx
0x180014e78  or      eax, 2
0x180014e7b  mov     [rbx], eax
0x180014e7d  jmp     short loc_180014E81
0x180014e7f  mov     eax, edx
0x180014e81  mov     r8d, edx
0x180014e84  and     r8d, 4
0x180014e88  jnz     short loc_180014E9D
0x180014e8a  mov     ecx, edi
0x180014e8c  xor     ecx, eax
0x180014e8e  and     ecx, 400h
0x180014e94  xor     ecx, eax
0x180014e96  or      ecx, 4
0x180014e99  mov     [rbx], ecx
0x180014e9b  jmp     short loc_180014E9F
0x180014e9d  mov     ecx, eax
0x180014e9f  mov     eax, edx
0x180014ea1  lock cmpxchg [rsi], ecx
0x180014ea5  jnz     short loc_180014E46
0x180014ea7  test    r8d, r8d
0x180014eaa  jnz     short loc_180014EBC
0x180014eac  mov     r8d, ebp
0x180014eaf  mov     edx, 3
0x180014eb4  mov     rcx, rsi
0x180014eb7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014ebc  test    byte ptr [rbx], 2
0x180014ebf  jnz     short loc_180014EE5
0x180014ec1  mov     eax, [rbx]
0x180014ec3  xor     eax, edi
0x180014ec5  and     eax, 180h
0x180014eca  xor     eax, [rbx]
0x180014ecc  mov     ecx, eax
0x180014ece  xor     ecx, edi
0x180014ed0  and     ecx, r15d
0x180014ed3  xor     ecx, eax
0x180014ed5  or      ecx, 1
0x180014ed8  mov     eax, ecx
0x180014eda  xor     eax, edi
0x180014edc  and     eax, 800h
0x180014ee1  xor     eax, ecx
0x180014ee3  mov     [rbx], eax
0x180014ee5  mov     rbp, [rsp+38h+arg_10]
0x180014eea  mov     rax, rbx
0x180014eed  mov     rbx, [rsp+38h+arg_8]
0x180014ef2  add     rsp, 20h
0x180014ef6  pop     r15
0x180014ef8  pop     rdi
0x180014ef9  pop     rsi
0x180014efa  retn
```
