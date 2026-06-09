# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180020e78`
- end: `0x180020fd0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021da0`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x180020e78`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E287E,
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
              (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v5);
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
0x180020e78  mov     [rsp+arg_8], rbx
0x180020e7d  mov     [rsp+arg_10], rbp
0x180020e82  mov     [rsp+arg_0], rcx
0x180020e87  push    rsi
0x180020e88  push    rdi
0x180020e89  push    r15
0x180020e8b  sub     rsp, 20h
0x180020e8f  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180020e96  mov     rbx, rdx
0x180020e99  mov     qword ptr [rdx], 0
0x180020ea0  mov     eax, [rsi]
0x180020ea2  mov     [rdx], eax
0x180020ea4  and     eax, 6
0x180020ea7  cmp     al, 6
0x180020ea9  jz      loc_180020FBA
0x180020eaf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180020eb4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180020eb9  mov     dword ptr [rsp+38h+arg_0], 0
0x180020ec1  mov     edx, 3; unsigned int
0x180020ec6  mov     ecx, 37E287Eh; this
0x180020ecb  mov     ebp, eax
0x180020ecd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180020ed2  mov     r8d, eax
0x180020ed5  mov     ecx, eax
0x180020ed7  and     r8d, 0FFFFFF3Fh
0x180020ede  and     eax, 80h
0x180020ee3  mov     edx, r8d
0x180020ee6  mov     r15d, 40h ; '@'
0x180020eec  and     edx, 3
0x180020eef  and     ecx, r15d
0x180020ef2  shl     edx, 2
0x180020ef5  or      edx, ecx
0x180020ef7  shl     edx, 2
0x180020efa  or      edx, eax
0x180020efc  lea     edi, ds:0[rdx*8]
0x180020f03  test    r8d, r8d
0x180020f06  jnz     short loc_180020F0D
0x180020f08  mov     eax, r15d
0x180020f0b  jmp     short loc_180020F17
0x180020f0d  xor     eax, eax
0x180020f0f  cmp     r8d, 2
0x180020f13  cmovz   eax, r15d
0x180020f17  or      edi, eax
0x180020f19  mov     eax, [rbx]
0x180020f1b  cmp     dword ptr [rsp+38h+arg_0], 0
0x180020f20  mov     edx, eax
0x180020f22  mov     [rbx], eax
0x180020f24  jz      short loc_180020F54
0x180020f26  test    dl, 2
0x180020f29  jnz     short loc_180020F54
0x180020f2b  mov     eax, edi
0x180020f2d  xor     eax, edx
0x180020f2f  and     eax, 180h
0x180020f34  xor     eax, edx
0x180020f36  mov     ecx, eax
0x180020f38  xor     ecx, edi
0x180020f3a  and     ecx, r15d
0x180020f3d  xor     ecx, eax
0x180020f3f  or      ecx, 1
0x180020f42  mov     eax, ecx
0x180020f44  xor     eax, edi
0x180020f46  and     eax, 800h
0x180020f4b  xor     eax, ecx
0x180020f4d  or      eax, 2
0x180020f50  mov     [rbx], eax
0x180020f52  jmp     short loc_180020F56
0x180020f54  mov     eax, edx
0x180020f56  mov     r8d, edx
0x180020f59  and     r8d, 4
0x180020f5d  jnz     short loc_180020F72
0x180020f5f  mov     ecx, edi
0x180020f61  xor     ecx, eax
0x180020f63  and     ecx, 400h
0x180020f69  xor     ecx, eax
0x180020f6b  or      ecx, 4
0x180020f6e  mov     [rbx], ecx
0x180020f70  jmp     short loc_180020F74
0x180020f72  mov     ecx, eax
0x180020f74  mov     eax, edx
0x180020f76  lock cmpxchg [rsi], ecx
0x180020f7a  jnz     short loc_180020F1B
0x180020f7c  test    r8d, r8d
0x180020f7f  jnz     short loc_180020F91
0x180020f81  mov     r8d, ebp
0x180020f84  mov     edx, 3
0x180020f89  mov     rcx, rsi
0x180020f8c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180020f91  test    byte ptr [rbx], 2
0x180020f94  jnz     short loc_180020FBA
0x180020f96  mov     eax, [rbx]
0x180020f98  xor     eax, edi
0x180020f9a  and     eax, 180h
0x180020f9f  xor     eax, [rbx]
0x180020fa1  mov     ecx, eax
0x180020fa3  xor     ecx, edi
0x180020fa5  and     ecx, r15d
0x180020fa8  xor     ecx, eax
0x180020faa  or      ecx, 1
0x180020fad  mov     eax, ecx
0x180020faf  xor     eax, edi
0x180020fb1  and     eax, 800h
0x180020fb6  xor     eax, ecx
0x180020fb8  mov     [rbx], eax
0x180020fba  mov     rbp, [rsp+38h+arg_10]
0x180020fbf  mov     rax, rbx
0x180020fc2  mov     rbx, [rsp+38h+arg_8]
0x180020fc7  add     rsp, 20h
0x180020fcb  pop     r15
0x180020fcd  pop     rdi
0x180020fce  pop     rsi
0x180020fcf  retn
```
