# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CxhWamLauncher>::GetCachedFeatureEnabledState(void)

- ea: `0x14000a244`
- end: `0x14000a3b3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CxhWamLauncher@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c6a0`

## callees

- `0x140009018`
- `0x14000a244`
- `0x14000ca88`
- `0x14000f010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CxhWamLauncher>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_CxhWamLauncher__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CxhWamLauncher__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(43788167, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
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
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CxhWamLauncher__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CxhWamLauncher__descriptor, 0, v4);
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
0x14000a244  mov     [rsp+arg_8], rbx
0x14000a249  mov     [rsp+arg_10], rbp
0x14000a24e  mov     [rsp+arg_0], rcx
0x14000a253  push    rsi
0x14000a254  push    rdi
0x14000a255  push    r15
0x14000a257  sub     rsp, 20h
0x14000a25b  mov     rsi, cs:Feature_CxhWamLauncher__descriptor
0x14000a262  mov     rbx, rdx
0x14000a265  mov     qword ptr [rdx], 0
0x14000a26c  mov     eax, [rsi]
0x14000a26e  mov     [rdx], eax
0x14000a270  and     eax, 6
0x14000a273  cmp     al, 6
0x14000a275  jz      loc_14000A39D
0x14000a27b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a280  mov     ebp, eax
0x14000a282  mov     dword ptr [rsp+38h+arg_0], 0
0x14000a28a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000a291  xor     edx, edx
0x14000a293  test    rax, rax
0x14000a296  jnz     short loc_14000A2A4
0x14000a298  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000a29f  test    rax, rax
0x14000a2a2  jz      short loc_14000A2B5
0x14000a2a4  lea     r8, [rsp+38h+arg_0]
0x14000a2a9  mov     ecx, 29C2787h
0x14000a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2b3  mov     edx, eax
0x14000a2b5  mov     r8d, edx
0x14000a2b8  mov     eax, edx
0x14000a2ba  and     r8d, 0FFFFFF3Fh
0x14000a2c1  and     edx, 80h
0x14000a2c7  mov     ecx, r8d
0x14000a2ca  mov     r15d, 40h ; '@'
0x14000a2d0  and     ecx, 3
0x14000a2d3  and     eax, r15d
0x14000a2d6  shl     ecx, 2
0x14000a2d9  or      ecx, eax
0x14000a2db  shl     ecx, 2
0x14000a2de  or      ecx, edx
0x14000a2e0  lea     edi, ds:0[rcx*8]
0x14000a2e7  test    r8d, r8d
0x14000a2ea  jnz     short loc_14000A2F1
0x14000a2ec  mov     eax, r15d
0x14000a2ef  jmp     short loc_14000A2FB
0x14000a2f1  xor     eax, eax
0x14000a2f3  cmp     r8d, 2
0x14000a2f7  cmovz   eax, r15d
0x14000a2fb  or      edi, eax
0x14000a2fd  test    ebp, ebp
0x14000a2ff  jnz     short loc_14000A305
0x14000a301  mov     dword ptr [rsp+38h+arg_0], ebp
0x14000a305  mov     eax, [rbx]
0x14000a307  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000a30c  mov     edx, eax
0x14000a30e  mov     [rbx], eax
0x14000a310  jz      short loc_14000A33C
0x14000a312  test    dl, 2
0x14000a315  jnz     short loc_14000A33C
0x14000a317  xor     eax, edi
0x14000a319  and     eax, 180h
0x14000a31e  xor     eax, edx
0x14000a320  mov     ecx, eax
0x14000a322  xor     ecx, edi
0x14000a324  and     ecx, r15d
0x14000a327  xor     ecx, eax
0x14000a329  or      ecx, 1
0x14000a32c  mov     eax, ecx
0x14000a32e  xor     eax, edi
0x14000a330  and     eax, 800h
0x14000a335  xor     eax, ecx
0x14000a337  or      eax, 2
0x14000a33a  mov     [rbx], eax
0x14000a33c  mov     r8d, edx
0x14000a33f  and     r8d, 4
0x14000a343  jnz     short loc_14000A358
0x14000a345  mov     ecx, edi
0x14000a347  xor     ecx, eax
0x14000a349  and     ecx, 400h
0x14000a34f  xor     ecx, eax
0x14000a351  or      ecx, 4
0x14000a354  mov     [rbx], ecx
0x14000a356  jmp     short loc_14000A35A
0x14000a358  mov     ecx, eax
0x14000a35a  mov     eax, edx
0x14000a35c  lock cmpxchg [rsi], ecx
0x14000a360  jnz     short loc_14000A307
0x14000a362  test    r8d, r8d
0x14000a365  jnz     short loc_14000A374
0x14000a367  mov     r8d, ebp
0x14000a36a  xor     edx, edx
0x14000a36c  mov     rcx, rsi
0x14000a36f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a374  test    byte ptr [rbx], 2
0x14000a377  jnz     short loc_14000A39D
0x14000a379  mov     eax, [rbx]
0x14000a37b  xor     eax, edi
0x14000a37d  and     eax, 180h
0x14000a382  xor     eax, [rbx]
0x14000a384  mov     ecx, eax
0x14000a386  xor     ecx, edi
0x14000a388  and     ecx, r15d
0x14000a38b  xor     ecx, eax
0x14000a38d  or      ecx, 1
0x14000a390  mov     eax, ecx
0x14000a392  xor     eax, edi
0x14000a394  and     eax, 800h
0x14000a399  xor     eax, ecx
0x14000a39b  mov     [rbx], eax
0x14000a39d  mov     rbp, [rsp+38h+arg_10]
0x14000a3a2  mov     rax, rbx
0x14000a3a5  mov     rbx, [rsp+38h+arg_8]
0x14000a3aa  add     rsp, 20h
0x14000a3ae  pop     r15
0x14000a3b0  pop     rdi
0x14000a3b1  pop     rsi
0x14000a3b2  retn
```
