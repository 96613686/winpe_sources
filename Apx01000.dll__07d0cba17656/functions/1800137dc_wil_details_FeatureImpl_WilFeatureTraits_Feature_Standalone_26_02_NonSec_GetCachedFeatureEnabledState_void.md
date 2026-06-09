# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800137dc`
- end: `0x180013949`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001494c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x1800137dc`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v4);
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
0x1800137dc  mov     [rsp+arg_8], rbx
0x1800137e1  mov     [rsp+arg_10], rbp
0x1800137e6  mov     [rsp+arg_0], rcx
0x1800137eb  push    rsi
0x1800137ec  push    rdi
0x1800137ed  push    r15
0x1800137ef  sub     rsp, 20h
0x1800137f3  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800137fa  mov     rbx, rdx
0x1800137fd  mov     qword ptr [rdx], 0
0x180013804  mov     eax, [rsi]
0x180013806  mov     [rdx], eax
0x180013808  and     eax, 6
0x18001380b  cmp     al, 6
0x18001380d  jz      loc_180013933
0x180013813  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013818  mov     ebp, eax
0x18001381a  mov     dword ptr [rsp+38h+arg_0], 0
0x180013822  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013829  test    rax, rax
0x18001382c  jz      short loc_180013846
0x18001382e  lea     r8, [rsp+38h+arg_0]
0x180013833  mov     edx, 3
0x180013838  mov     ecx, 37E287Eh
0x18001383d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013842  mov     edx, eax
0x180013844  jmp     short loc_180013854
0x180013846  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001384d  test    rax, rax
0x180013850  jnz     short loc_18001382E
0x180013852  xor     edx, edx
0x180013854  mov     r8d, edx
0x180013857  mov     eax, edx
0x180013859  and     r8d, 0FFFFFF3Fh
0x180013860  and     edx, 80h
0x180013866  mov     ecx, r8d
0x180013869  mov     r15d, 40h ; '@'
0x18001386f  and     ecx, 3
0x180013872  and     eax, r15d
0x180013875  shl     ecx, 2
0x180013878  or      ecx, eax
0x18001387a  shl     ecx, 2
0x18001387d  or      ecx, edx
0x18001387f  lea     edi, ds:0[rcx*8]
0x180013886  test    r8d, r8d
0x180013889  jnz     short loc_180013890
0x18001388b  mov     eax, r15d
0x18001388e  jmp     short loc_18001389A
0x180013890  xor     eax, eax
0x180013892  cmp     r8d, 2
0x180013896  cmovz   eax, r15d
0x18001389a  or      edi, eax
0x18001389c  mov     eax, [rbx]
0x18001389e  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800138a3  mov     edx, eax
0x1800138a5  mov     [rbx], eax
0x1800138a7  jz      short loc_1800138D3
0x1800138a9  test    dl, 2
0x1800138ac  jnz     short loc_1800138D3
0x1800138ae  xor     eax, edi
0x1800138b0  and     eax, 180h
0x1800138b5  xor     eax, edx
0x1800138b7  mov     ecx, eax
0x1800138b9  xor     ecx, edi
0x1800138bb  and     ecx, r15d
0x1800138be  xor     ecx, eax
0x1800138c0  or      ecx, 1
0x1800138c3  mov     eax, ecx
0x1800138c5  xor     eax, edi
0x1800138c7  and     eax, 800h
0x1800138cc  xor     eax, ecx
0x1800138ce  or      eax, 2
0x1800138d1  mov     [rbx], eax
0x1800138d3  mov     r8d, edx
0x1800138d6  mov     ecx, eax
0x1800138d8  and     r8d, 4
0x1800138dc  jnz     short loc_1800138ED
0x1800138de  xor     ecx, edi
0x1800138e0  and     ecx, 400h
0x1800138e6  xor     ecx, eax
0x1800138e8  or      ecx, 4
0x1800138eb  mov     [rbx], ecx
0x1800138ed  mov     eax, edx
0x1800138ef  lock cmpxchg [rsi], ecx
0x1800138f3  jnz     short loc_18001389E
0x1800138f5  test    r8d, r8d
0x1800138f8  jnz     short loc_18001390A
0x1800138fa  mov     r8d, ebp
0x1800138fd  mov     edx, 3
0x180013902  mov     rcx, rsi
0x180013905  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001390a  test    byte ptr [rbx], 2
0x18001390d  jnz     short loc_180013933
0x18001390f  mov     eax, [rbx]
0x180013911  xor     eax, edi
0x180013913  and     eax, 180h
0x180013918  xor     eax, [rbx]
0x18001391a  mov     ecx, eax
0x18001391c  xor     ecx, edi
0x18001391e  and     ecx, r15d
0x180013921  xor     ecx, eax
0x180013923  or      ecx, 1
0x180013926  mov     eax, ecx
0x180013928  xor     eax, edi
0x18001392a  and     eax, 800h
0x18001392f  xor     eax, ecx
0x180013931  mov     [rbx], eax
0x180013933  mov     rbp, [rsp+38h+arg_10]
0x180013938  mov     rax, rbx
0x18001393b  mov     rbx, [rsp+38h+arg_8]
0x180013940  add     rsp, 20h
0x180013944  pop     r15
0x180013946  pop     rdi
0x180013947  pop     rsi
0x180013948  retn
```
