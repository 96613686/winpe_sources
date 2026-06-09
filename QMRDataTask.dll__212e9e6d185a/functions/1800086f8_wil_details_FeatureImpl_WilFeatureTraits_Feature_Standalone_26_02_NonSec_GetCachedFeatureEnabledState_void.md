# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800086f8`
- end: `0x180008865`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c88`

## callees

- `0x18000787c`
- `0x1800086f8`
- `0x180010684`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x1800086f8  mov     [rsp+arg_8], rbx
0x1800086fd  mov     [rsp+arg_10], rbp
0x180008702  mov     [rsp+arg_0], rcx
0x180008707  push    rsi
0x180008708  push    rdi
0x180008709  push    r15
0x18000870b  sub     rsp, 20h
0x18000870f  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180008716  mov     rbx, rdx
0x180008719  mov     qword ptr [rdx], 0
0x180008720  mov     eax, [rsi]
0x180008722  mov     [rdx], eax
0x180008724  and     eax, 6
0x180008727  cmp     al, 6
0x180008729  jz      loc_18000884F
0x18000872f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008734  mov     ebp, eax
0x180008736  mov     dword ptr [rsp+38h+arg_0], 0
0x18000873e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008745  test    rax, rax
0x180008748  jz      short loc_180008762
0x18000874a  lea     r8, [rsp+38h+arg_0]
0x18000874f  mov     edx, 3
0x180008754  mov     ecx, 37E287Eh
0x180008759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000875e  mov     edx, eax
0x180008760  jmp     short loc_180008770
0x180008762  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008769  test    rax, rax
0x18000876c  jnz     short loc_18000874A
0x18000876e  xor     edx, edx
0x180008770  mov     r8d, edx
0x180008773  mov     eax, edx
0x180008775  and     r8d, 0FFFFFF3Fh
0x18000877c  and     edx, 80h
0x180008782  mov     ecx, r8d
0x180008785  mov     r15d, 40h ; '@'
0x18000878b  and     ecx, 3
0x18000878e  and     eax, r15d
0x180008791  shl     ecx, 2
0x180008794  or      ecx, eax
0x180008796  shl     ecx, 2
0x180008799  or      ecx, edx
0x18000879b  lea     edi, ds:0[rcx*8]
0x1800087a2  test    r8d, r8d
0x1800087a5  jnz     short loc_1800087AC
0x1800087a7  mov     eax, r15d
0x1800087aa  jmp     short loc_1800087B6
0x1800087ac  xor     eax, eax
0x1800087ae  cmp     r8d, 2
0x1800087b2  cmovz   eax, r15d
0x1800087b6  or      edi, eax
0x1800087b8  mov     eax, [rbx]
0x1800087ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800087bf  mov     edx, eax
0x1800087c1  mov     [rbx], eax
0x1800087c3  jz      short loc_1800087EF
0x1800087c5  test    dl, 2
0x1800087c8  jnz     short loc_1800087EF
0x1800087ca  xor     eax, edi
0x1800087cc  and     eax, 180h
0x1800087d1  xor     eax, edx
0x1800087d3  mov     ecx, eax
0x1800087d5  xor     ecx, edi
0x1800087d7  and     ecx, r15d
0x1800087da  xor     ecx, eax
0x1800087dc  or      ecx, 1
0x1800087df  mov     eax, ecx
0x1800087e1  xor     eax, edi
0x1800087e3  and     eax, 800h
0x1800087e8  xor     eax, ecx
0x1800087ea  or      eax, 2
0x1800087ed  mov     [rbx], eax
0x1800087ef  mov     r8d, edx
0x1800087f2  mov     ecx, eax
0x1800087f4  and     r8d, 4
0x1800087f8  jnz     short loc_180008809
0x1800087fa  xor     ecx, edi
0x1800087fc  and     ecx, 400h
0x180008802  xor     ecx, eax
0x180008804  or      ecx, 4
0x180008807  mov     [rbx], ecx
0x180008809  mov     eax, edx
0x18000880b  lock cmpxchg [rsi], ecx
0x18000880f  jnz     short loc_1800087BA
0x180008811  test    r8d, r8d
0x180008814  jnz     short loc_180008826
0x180008816  mov     r8d, ebp
0x180008819  mov     edx, 3
0x18000881e  mov     rcx, rsi
0x180008821  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008826  test    byte ptr [rbx], 2
0x180008829  jnz     short loc_18000884F
0x18000882b  mov     eax, [rbx]
0x18000882d  xor     eax, edi
0x18000882f  and     eax, 180h
0x180008834  xor     eax, [rbx]
0x180008836  mov     ecx, eax
0x180008838  xor     ecx, edi
0x18000883a  and     ecx, r15d
0x18000883d  xor     ecx, eax
0x18000883f  or      ecx, 1
0x180008842  mov     eax, ecx
0x180008844  xor     eax, edi
0x180008846  and     eax, 800h
0x18000884b  xor     eax, ecx
0x18000884d  mov     [rbx], eax
0x18000884f  mov     rbp, [rsp+38h+arg_10]
0x180008854  mov     rax, rbx
0x180008857  mov     rbx, [rsp+38h+arg_8]
0x18000885c  add     rsp, 20h
0x180008860  pop     r15
0x180008862  pop     rdi
0x180008863  pop     rsi
0x180008864  retn
```
