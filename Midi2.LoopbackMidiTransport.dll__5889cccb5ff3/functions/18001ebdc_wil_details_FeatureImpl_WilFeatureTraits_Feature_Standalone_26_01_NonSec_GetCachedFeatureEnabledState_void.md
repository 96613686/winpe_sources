# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ebdc`
- end: `0x18001ed49`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fb4c`

## callees

- `0x18001e65c`
- `0x18001ebdc`
- `0x180020fe4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18001ebdc  mov     [rsp+arg_8], rbx
0x18001ebe1  mov     [rsp+arg_10], rbp
0x18001ebe6  mov     [rsp+arg_0], rcx
0x18001ebeb  push    rsi
0x18001ebec  push    rdi
0x18001ebed  push    r15
0x18001ebef  sub     rsp, 20h
0x18001ebf3  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18001ebfa  mov     rbx, rdx
0x18001ebfd  mov     qword ptr [rdx], 0
0x18001ec04  mov     eax, [rsi]
0x18001ec06  mov     [rdx], eax
0x18001ec08  and     eax, 6
0x18001ec0b  cmp     al, 6
0x18001ec0d  jz      loc_18001ED33
0x18001ec13  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001ec18  mov     ebp, eax
0x18001ec1a  mov     dword ptr [rsp+38h+arg_0], 0
0x18001ec22  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001ec29  test    rax, rax
0x18001ec2c  jz      short loc_18001EC46
0x18001ec2e  lea     r8, [rsp+38h+arg_0]
0x18001ec33  mov     edx, 3
0x18001ec38  mov     ecx, 37E286Ch
0x18001ec3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec42  mov     edx, eax
0x18001ec44  jmp     short loc_18001EC54
0x18001ec46  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001ec4d  test    rax, rax
0x18001ec50  jnz     short loc_18001EC2E
0x18001ec52  xor     edx, edx
0x18001ec54  mov     r8d, edx
0x18001ec57  mov     eax, edx
0x18001ec59  and     r8d, 0FFFFFF3Fh
0x18001ec60  and     edx, 80h
0x18001ec66  mov     ecx, r8d
0x18001ec69  mov     r15d, 40h ; '@'
0x18001ec6f  and     ecx, 3
0x18001ec72  and     eax, r15d
0x18001ec75  shl     ecx, 2
0x18001ec78  or      ecx, eax
0x18001ec7a  shl     ecx, 2
0x18001ec7d  or      ecx, edx
0x18001ec7f  lea     edi, ds:0[rcx*8]
0x18001ec86  test    r8d, r8d
0x18001ec89  jnz     short loc_18001EC90
0x18001ec8b  mov     eax, r15d
0x18001ec8e  jmp     short loc_18001EC9A
0x18001ec90  xor     eax, eax
0x18001ec92  cmp     r8d, 2
0x18001ec96  cmovz   eax, r15d
0x18001ec9a  or      edi, eax
0x18001ec9c  mov     eax, [rbx]
0x18001ec9e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001eca3  mov     edx, eax
0x18001eca5  mov     [rbx], eax
0x18001eca7  jz      short loc_18001ECD3
0x18001eca9  test    dl, 2
0x18001ecac  jnz     short loc_18001ECD3
0x18001ecae  xor     eax, edi
0x18001ecb0  and     eax, 180h
0x18001ecb5  xor     eax, edx
0x18001ecb7  mov     ecx, eax
0x18001ecb9  xor     ecx, edi
0x18001ecbb  and     ecx, r15d
0x18001ecbe  xor     ecx, eax
0x18001ecc0  or      ecx, 1
0x18001ecc3  mov     eax, ecx
0x18001ecc5  xor     eax, edi
0x18001ecc7  and     eax, 800h
0x18001eccc  xor     eax, ecx
0x18001ecce  or      eax, 2
0x18001ecd1  mov     [rbx], eax
0x18001ecd3  mov     r8d, edx
0x18001ecd6  mov     ecx, eax
0x18001ecd8  and     r8d, 4
0x18001ecdc  jnz     short loc_18001ECED
0x18001ecde  xor     ecx, edi
0x18001ece0  and     ecx, 400h
0x18001ece6  xor     ecx, eax
0x18001ece8  or      ecx, 4
0x18001eceb  mov     [rbx], ecx
0x18001eced  mov     eax, edx
0x18001ecef  lock cmpxchg [rsi], ecx
0x18001ecf3  jnz     short loc_18001EC9E
0x18001ecf5  test    r8d, r8d
0x18001ecf8  jnz     short loc_18001ED0A
0x18001ecfa  mov     r8d, ebp
0x18001ecfd  mov     edx, 3
0x18001ed02  mov     rcx, rsi
0x18001ed05  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ed0a  test    byte ptr [rbx], 2
0x18001ed0d  jnz     short loc_18001ED33
0x18001ed0f  mov     eax, [rbx]
0x18001ed11  xor     eax, edi
0x18001ed13  and     eax, 180h
0x18001ed18  xor     eax, [rbx]
0x18001ed1a  mov     ecx, eax
0x18001ed1c  xor     ecx, edi
0x18001ed1e  and     ecx, r15d
0x18001ed21  xor     ecx, eax
0x18001ed23  or      ecx, 1
0x18001ed26  mov     eax, ecx
0x18001ed28  xor     eax, edi
0x18001ed2a  and     eax, 800h
0x18001ed2f  xor     eax, ecx
0x18001ed31  mov     [rbx], eax
0x18001ed33  mov     rbp, [rsp+38h+arg_10]
0x18001ed38  mov     rax, rbx
0x18001ed3b  mov     rbx, [rsp+38h+arg_8]
0x18001ed40  add     rsp, 20h
0x18001ed44  pop     r15
0x18001ed46  pop     rdi
0x18001ed47  pop     rsi
0x18001ed48  retn
```
