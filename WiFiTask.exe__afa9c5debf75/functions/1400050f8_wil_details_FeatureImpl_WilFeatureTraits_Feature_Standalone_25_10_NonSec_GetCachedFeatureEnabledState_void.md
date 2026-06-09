# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1400050f8`
- end: `0x140005265`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005e70`

## callees

- `0x1400049e0`
- `0x1400050f8`
- `0x14000a88c`
- `0x140012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x1400050f8  mov     [rsp+arg_8], rbx
0x1400050fd  mov     [rsp+arg_10], rbp
0x140005102  mov     [rsp+arg_0], rcx
0x140005107  push    rsi
0x140005108  push    rdi
0x140005109  push    r15
0x14000510b  sub     rsp, 20h
0x14000510f  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x140005116  mov     rbx, rdx
0x140005119  mov     qword ptr [rdx], 0
0x140005120  mov     eax, [rsi]
0x140005122  mov     [rdx], eax
0x140005124  and     eax, 6
0x140005127  cmp     al, 6
0x140005129  jz      loc_14000524F
0x14000512f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140005134  mov     ebp, eax
0x140005136  mov     dword ptr [rsp+38h+arg_0], 0
0x14000513e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005145  test    rax, rax
0x140005148  jz      short loc_140005162
0x14000514a  lea     r8, [rsp+38h+arg_0]
0x14000514f  mov     edx, 3
0x140005154  mov     ecx, 2AF34F8h
0x140005159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000515e  mov     edx, eax
0x140005160  jmp     short loc_140005170
0x140005162  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005169  test    rax, rax
0x14000516c  jnz     short loc_14000514A
0x14000516e  xor     edx, edx
0x140005170  mov     r8d, edx
0x140005173  mov     eax, edx
0x140005175  and     r8d, 0FFFFFF3Fh
0x14000517c  and     edx, 80h
0x140005182  mov     ecx, r8d
0x140005185  mov     r15d, 40h ; '@'
0x14000518b  and     ecx, 3
0x14000518e  and     eax, r15d
0x140005191  shl     ecx, 2
0x140005194  or      ecx, eax
0x140005196  shl     ecx, 2
0x140005199  or      ecx, edx
0x14000519b  lea     edi, ds:0[rcx*8]
0x1400051a2  test    r8d, r8d
0x1400051a5  jnz     short loc_1400051AC
0x1400051a7  mov     eax, r15d
0x1400051aa  jmp     short loc_1400051B6
0x1400051ac  xor     eax, eax
0x1400051ae  cmp     r8d, 2
0x1400051b2  cmovz   eax, r15d
0x1400051b6  or      edi, eax
0x1400051b8  mov     eax, [rbx]
0x1400051ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400051bf  mov     edx, eax
0x1400051c1  mov     [rbx], eax
0x1400051c3  jz      short loc_1400051EF
0x1400051c5  test    dl, 2
0x1400051c8  jnz     short loc_1400051EF
0x1400051ca  xor     eax, edi
0x1400051cc  and     eax, 180h
0x1400051d1  xor     eax, edx
0x1400051d3  mov     ecx, eax
0x1400051d5  xor     ecx, edi
0x1400051d7  and     ecx, r15d
0x1400051da  xor     ecx, eax
0x1400051dc  or      ecx, 1
0x1400051df  mov     eax, ecx
0x1400051e1  xor     eax, edi
0x1400051e3  and     eax, 800h
0x1400051e8  xor     eax, ecx
0x1400051ea  or      eax, 2
0x1400051ed  mov     [rbx], eax
0x1400051ef  mov     r8d, edx
0x1400051f2  mov     ecx, eax
0x1400051f4  and     r8d, 4
0x1400051f8  jnz     short loc_140005209
0x1400051fa  xor     ecx, edi
0x1400051fc  and     ecx, 400h
0x140005202  xor     ecx, eax
0x140005204  or      ecx, 4
0x140005207  mov     [rbx], ecx
0x140005209  mov     eax, edx
0x14000520b  lock cmpxchg [rsi], ecx
0x14000520f  jnz     short loc_1400051BA
0x140005211  test    r8d, r8d
0x140005214  jnz     short loc_140005226
0x140005216  mov     r8d, ebp
0x140005219  mov     edx, 3
0x14000521e  mov     rcx, rsi
0x140005221  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140005226  test    byte ptr [rbx], 2
0x140005229  jnz     short loc_14000524F
0x14000522b  mov     eax, [rbx]
0x14000522d  xor     eax, edi
0x14000522f  and     eax, 180h
0x140005234  xor     eax, [rbx]
0x140005236  mov     ecx, eax
0x140005238  xor     ecx, edi
0x14000523a  and     ecx, r15d
0x14000523d  xor     ecx, eax
0x14000523f  or      ecx, 1
0x140005242  mov     eax, ecx
0x140005244  xor     eax, edi
0x140005246  and     eax, 800h
0x14000524b  xor     eax, ecx
0x14000524d  mov     [rbx], eax
0x14000524f  mov     rbp, [rsp+38h+arg_10]
0x140005254  mov     rax, rbx
0x140005257  mov     rbx, [rsp+38h+arg_8]
0x14000525c  add     rsp, 20h
0x140005260  pop     r15
0x140005262  pop     rdi
0x140005263  pop     rsi
0x140005264  retn
```
