# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180014c4c`
- end: `0x180014d9f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `339`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001606c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000cfc0`
- `0x180014c4c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
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
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v5);
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
0x180014c4c  mov     [rsp+arg_8], rbx
0x180014c51  mov     [rsp+arg_10], rbp
0x180014c56  mov     [rsp+arg_0], rcx
0x180014c5b  push    rsi
0x180014c5c  push    rdi
0x180014c5d  push    r15
0x180014c5f  sub     rsp, 20h
0x180014c63  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180014c6a  mov     rbx, rdx
0x180014c6d  mov     qword ptr [rdx], 0
0x180014c74  mov     eax, [rsi]
0x180014c76  mov     [rdx], eax
0x180014c78  and     eax, 6
0x180014c7b  cmp     al, 6
0x180014c7d  jz      loc_180014D89
0x180014c83  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014c88  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180014c8d  mov     dword ptr [rsp+38h+arg_0], 0
0x180014c95  mov     ecx, 2AF34F8h; this
0x180014c9a  mov     ebp, eax
0x180014c9c  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014ca1  mov     r8d, eax
0x180014ca4  mov     ecx, eax
0x180014ca6  and     r8d, 0FFFFFF3Fh
0x180014cad  and     eax, 80h
0x180014cb2  mov     edx, r8d
0x180014cb5  mov     r15d, 40h ; '@'
0x180014cbb  and     edx, 3
0x180014cbe  and     ecx, r15d
0x180014cc1  shl     edx, 2
0x180014cc4  or      edx, ecx
0x180014cc6  shl     edx, 2
0x180014cc9  or      edx, eax
0x180014ccb  lea     edi, ds:0[rdx*8]
0x180014cd2  test    r8d, r8d
0x180014cd5  jnz     short loc_180014CDC
0x180014cd7  mov     eax, r15d
0x180014cda  jmp     short loc_180014CE6
0x180014cdc  xor     eax, eax
0x180014cde  cmp     r8d, 2
0x180014ce2  cmovz   eax, r15d
0x180014ce6  or      edi, eax
0x180014ce8  mov     eax, [rbx]
0x180014cea  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014cef  mov     edx, eax
0x180014cf1  mov     [rbx], eax
0x180014cf3  jz      short loc_180014D23
0x180014cf5  test    dl, 2
0x180014cf8  jnz     short loc_180014D23
0x180014cfa  mov     eax, edi
0x180014cfc  xor     eax, edx
0x180014cfe  and     eax, 180h
0x180014d03  xor     eax, edx
0x180014d05  mov     ecx, eax
0x180014d07  xor     ecx, edi
0x180014d09  and     ecx, r15d
0x180014d0c  xor     ecx, eax
0x180014d0e  or      ecx, 1
0x180014d11  mov     eax, ecx
0x180014d13  xor     eax, edi
0x180014d15  and     eax, 800h
0x180014d1a  xor     eax, ecx
0x180014d1c  or      eax, 2
0x180014d1f  mov     [rbx], eax
0x180014d21  jmp     short loc_180014D25
0x180014d23  mov     eax, edx
0x180014d25  mov     r8d, edx
0x180014d28  and     r8d, 4
0x180014d2c  jnz     short loc_180014D41
0x180014d2e  mov     ecx, edi
0x180014d30  xor     ecx, eax
0x180014d32  and     ecx, 400h
0x180014d38  xor     ecx, eax
0x180014d3a  or      ecx, 4
0x180014d3d  mov     [rbx], ecx
0x180014d3f  jmp     short loc_180014D43
0x180014d41  mov     ecx, eax
0x180014d43  mov     eax, edx
0x180014d45  lock cmpxchg [rsi], ecx
0x180014d49  jnz     short loc_180014CEA
0x180014d4b  test    r8d, r8d
0x180014d4e  jnz     short loc_180014D60
0x180014d50  mov     r8d, ebp
0x180014d53  mov     edx, 3
0x180014d58  mov     rcx, rsi
0x180014d5b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014d60  test    byte ptr [rbx], 2
0x180014d63  jnz     short loc_180014D89
0x180014d65  mov     eax, [rbx]
0x180014d67  xor     eax, edi
0x180014d69  and     eax, 180h
0x180014d6e  xor     eax, [rbx]
0x180014d70  mov     ecx, eax
0x180014d72  xor     ecx, edi
0x180014d74  and     ecx, r15d
0x180014d77  xor     ecx, eax
0x180014d79  or      ecx, 1
0x180014d7c  mov     eax, ecx
0x180014d7e  xor     eax, edi
0x180014d80  and     eax, 800h
0x180014d85  xor     eax, ecx
0x180014d87  mov     [rbx], eax
0x180014d89  mov     rbp, [rsp+38h+arg_10]
0x180014d8e  mov     rax, rbx
0x180014d91  mov     rbx, [rsp+38h+arg_8]
0x180014d96  add     rsp, 20h
0x180014d9a  pop     r15
0x180014d9c  pop     rdi
0x180014d9d  pop     rsi
0x180014d9e  retn
```
