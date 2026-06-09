# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180020d18`
- end: `0x180020e70`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022048`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x180020d18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E286C,
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
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v5);
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
0x180020d18  mov     [rsp+arg_8], rbx
0x180020d1d  mov     [rsp+arg_10], rbp
0x180020d22  mov     [rsp+arg_0], rcx
0x180020d27  push    rsi
0x180020d28  push    rdi
0x180020d29  push    r15
0x180020d2b  sub     rsp, 20h
0x180020d2f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180020d36  mov     rbx, rdx
0x180020d39  mov     qword ptr [rdx], 0
0x180020d40  mov     eax, [rsi]
0x180020d42  mov     [rdx], eax
0x180020d44  and     eax, 6
0x180020d47  cmp     al, 6
0x180020d49  jz      loc_180020E5A
0x180020d4f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180020d54  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180020d59  mov     dword ptr [rsp+38h+arg_0], 0
0x180020d61  mov     edx, 3; unsigned int
0x180020d66  mov     ecx, 37E286Ch; this
0x180020d6b  mov     ebp, eax
0x180020d6d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180020d72  mov     r8d, eax
0x180020d75  mov     ecx, eax
0x180020d77  and     r8d, 0FFFFFF3Fh
0x180020d7e  and     eax, 80h
0x180020d83  mov     edx, r8d
0x180020d86  mov     r15d, 40h ; '@'
0x180020d8c  and     edx, 3
0x180020d8f  and     ecx, r15d
0x180020d92  shl     edx, 2
0x180020d95  or      edx, ecx
0x180020d97  shl     edx, 2
0x180020d9a  or      edx, eax
0x180020d9c  lea     edi, ds:0[rdx*8]
0x180020da3  test    r8d, r8d
0x180020da6  jnz     short loc_180020DAD
0x180020da8  mov     eax, r15d
0x180020dab  jmp     short loc_180020DB7
0x180020dad  xor     eax, eax
0x180020daf  cmp     r8d, 2
0x180020db3  cmovz   eax, r15d
0x180020db7  or      edi, eax
0x180020db9  mov     eax, [rbx]
0x180020dbb  cmp     dword ptr [rsp+38h+arg_0], 0
0x180020dc0  mov     edx, eax
0x180020dc2  mov     [rbx], eax
0x180020dc4  jz      short loc_180020DF4
0x180020dc6  test    dl, 2
0x180020dc9  jnz     short loc_180020DF4
0x180020dcb  mov     eax, edi
0x180020dcd  xor     eax, edx
0x180020dcf  and     eax, 180h
0x180020dd4  xor     eax, edx
0x180020dd6  mov     ecx, eax
0x180020dd8  xor     ecx, edi
0x180020dda  and     ecx, r15d
0x180020ddd  xor     ecx, eax
0x180020ddf  or      ecx, 1
0x180020de2  mov     eax, ecx
0x180020de4  xor     eax, edi
0x180020de6  and     eax, 800h
0x180020deb  xor     eax, ecx
0x180020ded  or      eax, 2
0x180020df0  mov     [rbx], eax
0x180020df2  jmp     short loc_180020DF6
0x180020df4  mov     eax, edx
0x180020df6  mov     r8d, edx
0x180020df9  and     r8d, 4
0x180020dfd  jnz     short loc_180020E12
0x180020dff  mov     ecx, edi
0x180020e01  xor     ecx, eax
0x180020e03  and     ecx, 400h
0x180020e09  xor     ecx, eax
0x180020e0b  or      ecx, 4
0x180020e0e  mov     [rbx], ecx
0x180020e10  jmp     short loc_180020E14
0x180020e12  mov     ecx, eax
0x180020e14  mov     eax, edx
0x180020e16  lock cmpxchg [rsi], ecx
0x180020e1a  jnz     short loc_180020DBB
0x180020e1c  test    r8d, r8d
0x180020e1f  jnz     short loc_180020E31
0x180020e21  mov     r8d, ebp
0x180020e24  mov     edx, 3
0x180020e29  mov     rcx, rsi
0x180020e2c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180020e31  test    byte ptr [rbx], 2
0x180020e34  jnz     short loc_180020E5A
0x180020e36  mov     eax, [rbx]
0x180020e38  xor     eax, edi
0x180020e3a  and     eax, 180h
0x180020e3f  xor     eax, [rbx]
0x180020e41  mov     ecx, eax
0x180020e43  xor     ecx, edi
0x180020e45  and     ecx, r15d
0x180020e48  xor     ecx, eax
0x180020e4a  or      ecx, 1
0x180020e4d  mov     eax, ecx
0x180020e4f  xor     eax, edi
0x180020e51  and     eax, 800h
0x180020e56  xor     eax, ecx
0x180020e58  mov     [rbx], eax
0x180020e5a  mov     rbp, [rsp+38h+arg_10]
0x180020e5f  mov     rax, rbx
0x180020e62  mov     rbx, [rsp+38h+arg_8]
0x180020e67  add     rsp, 20h
0x180020e6b  pop     r15
0x180020e6d  pop     rdi
0x180020e6e  pop     rsi
0x180020e6f  retn
```
