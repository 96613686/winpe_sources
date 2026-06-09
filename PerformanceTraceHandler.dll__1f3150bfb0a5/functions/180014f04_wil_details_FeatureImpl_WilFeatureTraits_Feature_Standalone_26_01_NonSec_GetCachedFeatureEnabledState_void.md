# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180014f04`
- end: `0x180015057`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `339`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015dcc`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000cfc0`
- `0x180014f04`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E286C,
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
              (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v5);
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
0x180014f04  mov     [rsp+arg_8], rbx
0x180014f09  mov     [rsp+arg_10], rbp
0x180014f0e  mov     [rsp+arg_0], rcx
0x180014f13  push    rsi
0x180014f14  push    rdi
0x180014f15  push    r15
0x180014f17  sub     rsp, 20h
0x180014f1b  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180014f22  mov     rbx, rdx
0x180014f25  mov     qword ptr [rdx], 0
0x180014f2c  mov     eax, [rsi]
0x180014f2e  mov     [rdx], eax
0x180014f30  and     eax, 6
0x180014f33  cmp     al, 6
0x180014f35  jz      loc_180015041
0x180014f3b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014f40  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180014f45  mov     dword ptr [rsp+38h+arg_0], 0
0x180014f4d  mov     ecx, 37E286Ch; this
0x180014f52  mov     ebp, eax
0x180014f54  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014f59  mov     r8d, eax
0x180014f5c  mov     ecx, eax
0x180014f5e  and     r8d, 0FFFFFF3Fh
0x180014f65  and     eax, 80h
0x180014f6a  mov     edx, r8d
0x180014f6d  mov     r15d, 40h ; '@'
0x180014f73  and     edx, 3
0x180014f76  and     ecx, r15d
0x180014f79  shl     edx, 2
0x180014f7c  or      edx, ecx
0x180014f7e  shl     edx, 2
0x180014f81  or      edx, eax
0x180014f83  lea     edi, ds:0[rdx*8]
0x180014f8a  test    r8d, r8d
0x180014f8d  jnz     short loc_180014F94
0x180014f8f  mov     eax, r15d
0x180014f92  jmp     short loc_180014F9E
0x180014f94  xor     eax, eax
0x180014f96  cmp     r8d, 2
0x180014f9a  cmovz   eax, r15d
0x180014f9e  or      edi, eax
0x180014fa0  mov     eax, [rbx]
0x180014fa2  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014fa7  mov     edx, eax
0x180014fa9  mov     [rbx], eax
0x180014fab  jz      short loc_180014FDB
0x180014fad  test    dl, 2
0x180014fb0  jnz     short loc_180014FDB
0x180014fb2  mov     eax, edi
0x180014fb4  xor     eax, edx
0x180014fb6  and     eax, 180h
0x180014fbb  xor     eax, edx
0x180014fbd  mov     ecx, eax
0x180014fbf  xor     ecx, edi
0x180014fc1  and     ecx, r15d
0x180014fc4  xor     ecx, eax
0x180014fc6  or      ecx, 1
0x180014fc9  mov     eax, ecx
0x180014fcb  xor     eax, edi
0x180014fcd  and     eax, 800h
0x180014fd2  xor     eax, ecx
0x180014fd4  or      eax, 2
0x180014fd7  mov     [rbx], eax
0x180014fd9  jmp     short loc_180014FDD
0x180014fdb  mov     eax, edx
0x180014fdd  mov     r8d, edx
0x180014fe0  and     r8d, 4
0x180014fe4  jnz     short loc_180014FF9
0x180014fe6  mov     ecx, edi
0x180014fe8  xor     ecx, eax
0x180014fea  and     ecx, 400h
0x180014ff0  xor     ecx, eax
0x180014ff2  or      ecx, 4
0x180014ff5  mov     [rbx], ecx
0x180014ff7  jmp     short loc_180014FFB
0x180014ff9  mov     ecx, eax
0x180014ffb  mov     eax, edx
0x180014ffd  lock cmpxchg [rsi], ecx
0x180015001  jnz     short loc_180014FA2
0x180015003  test    r8d, r8d
0x180015006  jnz     short loc_180015018
0x180015008  mov     r8d, ebp
0x18001500b  mov     edx, 3
0x180015010  mov     rcx, rsi
0x180015013  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015018  test    byte ptr [rbx], 2
0x18001501b  jnz     short loc_180015041
0x18001501d  mov     eax, [rbx]
0x18001501f  xor     eax, edi
0x180015021  and     eax, 180h
0x180015026  xor     eax, [rbx]
0x180015028  mov     ecx, eax
0x18001502a  xor     ecx, edi
0x18001502c  and     ecx, r15d
0x18001502f  xor     ecx, eax
0x180015031  or      ecx, 1
0x180015034  mov     eax, ecx
0x180015036  xor     eax, edi
0x180015038  and     eax, 800h
0x18001503d  xor     eax, ecx
0x18001503f  mov     [rbx], eax
0x180015041  mov     rbp, [rsp+38h+arg_10]
0x180015046  mov     rax, rbx
0x180015049  mov     rbx, [rsp+38h+arg_8]
0x18001504e  add     rsp, 20h
0x180015052  pop     r15
0x180015054  pop     rdi
0x180015055  pop     rsi
0x180015056  retn
```
