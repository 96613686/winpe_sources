# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Audio_Drivers_Apx_Streaming>::GetCachedFeatureEnabledState(void)

- ea: `0x180023fdc`
- end: `0x180024153`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Audio_Drivers_Apx_Streaming@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800246d0`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180023fdc`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Audio_Drivers_Apx_Streaming>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Audio_Drivers_Apx_Streaming__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Audio_Drivers_Apx_Streaming__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45307425, 3, &v14);
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
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
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
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Audio_Drivers_Apx_Streaming__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Audio_Drivers_Apx_Streaming__descriptor,
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
0x180023fdc  mov     [rsp+arg_8], rbx
0x180023fe1  mov     [rsp+arg_10], rbp
0x180023fe6  mov     [rsp+arg_0], rcx
0x180023feb  push    rsi
0x180023fec  push    rdi
0x180023fed  push    r15
0x180023fef  sub     rsp, 20h
0x180023ff3  mov     rsi, cs:Feature_Audio_Drivers_Apx_Streaming__descriptor
0x180023ffa  mov     rbx, rdx
0x180023ffd  mov     qword ptr [rdx], 0
0x180024004  mov     eax, [rsi]
0x180024006  mov     [rdx], eax
0x180024008  and     eax, 6
0x18002400b  cmp     al, 6
0x18002400d  jz      loc_18002413D
0x180024013  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180024018  mov     ebp, eax
0x18002401a  mov     dword ptr [rsp+38h+arg_0], 0
0x180024022  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180024029  test    rax, rax
0x18002402c  jz      short loc_180024046
0x18002402e  lea     r8, [rsp+38h+arg_0]
0x180024033  mov     edx, 3
0x180024038  mov     ecx, 2B35621h
0x18002403d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024042  mov     edx, eax
0x180024044  jmp     short loc_180024054
0x180024046  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002404d  test    rax, rax
0x180024050  jnz     short loc_18002402E
0x180024052  xor     edx, edx
0x180024054  mov     r8d, edx
0x180024057  mov     eax, edx
0x180024059  and     r8d, 0FFFFFF3Fh
0x180024060  and     edx, 80h
0x180024066  mov     ecx, r8d
0x180024069  mov     r15d, 40h ; '@'
0x18002406f  and     ecx, 3
0x180024072  and     eax, r15d
0x180024075  shl     ecx, 2
0x180024078  or      ecx, eax
0x18002407a  shl     ecx, 2
0x18002407d  or      ecx, edx
0x18002407f  lea     edi, ds:0[rcx*8]
0x180024086  test    r8d, r8d
0x180024089  jnz     short loc_180024090
0x18002408b  mov     eax, r15d
0x18002408e  jmp     short loc_18002409A
0x180024090  xor     eax, eax
0x180024092  cmp     r8d, 2
0x180024096  cmovz   eax, r15d
0x18002409a  or      edi, eax
0x18002409c  mov     eax, [rbx]
0x18002409e  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800240a3  mov     edx, eax
0x1800240a5  mov     [rbx], eax
0x1800240a7  jz      short loc_1800240D7
0x1800240a9  test    dl, 2
0x1800240ac  jnz     short loc_1800240D7
0x1800240ae  mov     eax, edi
0x1800240b0  xor     eax, edx
0x1800240b2  and     eax, 180h
0x1800240b7  xor     eax, edx
0x1800240b9  mov     ecx, eax
0x1800240bb  xor     ecx, edi
0x1800240bd  and     ecx, r15d
0x1800240c0  xor     ecx, eax
0x1800240c2  or      ecx, 1
0x1800240c5  mov     eax, ecx
0x1800240c7  xor     eax, edi
0x1800240c9  and     eax, 800h
0x1800240ce  xor     eax, ecx
0x1800240d0  or      eax, 2
0x1800240d3  mov     [rbx], eax
0x1800240d5  jmp     short loc_1800240D9
0x1800240d7  mov     eax, edx
0x1800240d9  mov     r8d, edx
0x1800240dc  and     r8d, 4
0x1800240e0  jnz     short loc_1800240F5
0x1800240e2  mov     ecx, edi
0x1800240e4  xor     ecx, eax
0x1800240e6  and     ecx, 400h
0x1800240ec  xor     ecx, eax
0x1800240ee  or      ecx, 4
0x1800240f1  mov     [rbx], ecx
0x1800240f3  jmp     short loc_1800240F7
0x1800240f5  mov     ecx, eax
0x1800240f7  mov     eax, edx
0x1800240f9  lock cmpxchg [rsi], ecx
0x1800240fd  jnz     short loc_18002409E
0x1800240ff  test    r8d, r8d
0x180024102  jnz     short loc_180024114
0x180024104  mov     r8d, ebp
0x180024107  mov     edx, 3
0x18002410c  mov     rcx, rsi
0x18002410f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180024114  test    byte ptr [rbx], 2
0x180024117  jnz     short loc_18002413D
0x180024119  mov     eax, [rbx]
0x18002411b  xor     eax, edi
0x18002411d  and     eax, 180h
0x180024122  xor     eax, [rbx]
0x180024124  mov     ecx, eax
0x180024126  xor     ecx, edi
0x180024128  and     ecx, r15d
0x18002412b  xor     ecx, eax
0x18002412d  or      ecx, 1
0x180024130  mov     eax, ecx
0x180024132  xor     eax, edi
0x180024134  and     eax, 800h
0x180024139  xor     eax, ecx
0x18002413b  mov     [rbx], eax
0x18002413d  mov     rbp, [rsp+38h+arg_10]
0x180024142  mov     rax, rbx
0x180024145  mov     rbx, [rsp+38h+arg_8]
0x18002414a  add     rsp, 20h
0x18002414e  pop     r15
0x180024150  pop     rdi
0x180024151  pop     rsi
0x180024152  retn
```
