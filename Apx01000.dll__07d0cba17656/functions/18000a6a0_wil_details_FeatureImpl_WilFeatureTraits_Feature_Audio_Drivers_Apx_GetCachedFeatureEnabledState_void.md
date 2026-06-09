# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Audio_Drivers_Apx>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a6a0`
- end: `0x18000a817`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Audio_Drivers_Apx@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a820`

## callees

- `0x180004a48`
- `0x180008344`
- `0x18000a6a0`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Audio_Drivers_Apx>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Audio_Drivers_Apx__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Audio_Drivers_Apx__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(30813804, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Audio_Drivers_Apx__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Audio_Drivers_Apx__descriptor, 3, v4);
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
0x18000a6a0  mov     [rsp+arg_8], rbx
0x18000a6a5  mov     [rsp+arg_10], rbp
0x18000a6aa  mov     [rsp+arg_0], rcx
0x18000a6af  push    rsi
0x18000a6b0  push    rdi
0x18000a6b1  push    r15
0x18000a6b3  sub     rsp, 20h
0x18000a6b7  mov     rsi, cs:Feature_Audio_Drivers_Apx__descriptor
0x18000a6be  mov     rbx, rdx
0x18000a6c1  mov     qword ptr [rdx], 0
0x18000a6c8  mov     eax, [rsi]
0x18000a6ca  mov     [rdx], eax
0x18000a6cc  and     eax, 6
0x18000a6cf  cmp     al, 6
0x18000a6d1  jz      loc_18000A801
0x18000a6d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a6dc  mov     ebp, eax
0x18000a6de  mov     dword ptr [rsp+38h+arg_0], 0
0x18000a6e6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000a6ed  test    rax, rax
0x18000a6f0  jz      short loc_18000A70A
0x18000a6f2  lea     r8, [rsp+38h+arg_0]
0x18000a6f7  mov     edx, 3
0x18000a6fc  mov     ecx, 1D62E6Ch
0x18000a701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a706  mov     edx, eax
0x18000a708  jmp     short loc_18000A718
0x18000a70a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000a711  test    rax, rax
0x18000a714  jnz     short loc_18000A6F2
0x18000a716  xor     edx, edx
0x18000a718  mov     r8d, edx
0x18000a71b  mov     eax, edx
0x18000a71d  and     r8d, 0FFFFFF3Fh
0x18000a724  and     edx, 80h
0x18000a72a  mov     ecx, r8d
0x18000a72d  mov     r15d, 40h ; '@'
0x18000a733  and     ecx, 3
0x18000a736  and     eax, r15d
0x18000a739  shl     ecx, 2
0x18000a73c  or      ecx, eax
0x18000a73e  shl     ecx, 2
0x18000a741  or      ecx, edx
0x18000a743  lea     edi, ds:0[rcx*8]
0x18000a74a  test    r8d, r8d
0x18000a74d  jnz     short loc_18000A754
0x18000a74f  mov     eax, r15d
0x18000a752  jmp     short loc_18000A75E
0x18000a754  xor     eax, eax
0x18000a756  cmp     r8d, 2
0x18000a75a  cmovz   eax, r15d
0x18000a75e  or      edi, eax
0x18000a760  mov     eax, [rbx]
0x18000a762  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000a767  mov     edx, eax
0x18000a769  mov     [rbx], eax
0x18000a76b  jz      short loc_18000A79B
0x18000a76d  test    dl, 2
0x18000a770  jnz     short loc_18000A79B
0x18000a772  mov     eax, edi
0x18000a774  xor     eax, edx
0x18000a776  and     eax, 180h
0x18000a77b  xor     eax, edx
0x18000a77d  mov     ecx, eax
0x18000a77f  xor     ecx, edi
0x18000a781  and     ecx, r15d
0x18000a784  xor     ecx, eax
0x18000a786  or      ecx, 1
0x18000a789  mov     eax, ecx
0x18000a78b  xor     eax, edi
0x18000a78d  and     eax, 800h
0x18000a792  xor     eax, ecx
0x18000a794  or      eax, 2
0x18000a797  mov     [rbx], eax
0x18000a799  jmp     short loc_18000A79D
0x18000a79b  mov     eax, edx
0x18000a79d  mov     r8d, edx
0x18000a7a0  and     r8d, 4
0x18000a7a4  jnz     short loc_18000A7B9
0x18000a7a6  mov     ecx, edi
0x18000a7a8  xor     ecx, eax
0x18000a7aa  and     ecx, 400h
0x18000a7b0  xor     ecx, eax
0x18000a7b2  or      ecx, 4
0x18000a7b5  mov     [rbx], ecx
0x18000a7b7  jmp     short loc_18000A7BB
0x18000a7b9  mov     ecx, eax
0x18000a7bb  mov     eax, edx
0x18000a7bd  lock cmpxchg [rsi], ecx
0x18000a7c1  jnz     short loc_18000A762
0x18000a7c3  test    r8d, r8d
0x18000a7c6  jnz     short loc_18000A7D8
0x18000a7c8  mov     r8d, ebp
0x18000a7cb  mov     edx, 3
0x18000a7d0  mov     rcx, rsi
0x18000a7d3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a7d8  test    byte ptr [rbx], 2
0x18000a7db  jnz     short loc_18000A801
0x18000a7dd  mov     eax, [rbx]
0x18000a7df  xor     eax, edi
0x18000a7e1  and     eax, 180h
0x18000a7e6  xor     eax, [rbx]
0x18000a7e8  mov     ecx, eax
0x18000a7ea  xor     ecx, edi
0x18000a7ec  and     ecx, r15d
0x18000a7ef  xor     ecx, eax
0x18000a7f1  or      ecx, 1
0x18000a7f4  mov     eax, ecx
0x18000a7f6  xor     eax, edi
0x18000a7f8  and     eax, 800h
0x18000a7fd  xor     eax, ecx
0x18000a7ff  mov     [rbx], eax
0x18000a801  mov     rbp, [rsp+38h+arg_10]
0x18000a806  mov     rax, rbx
0x18000a809  mov     rbx, [rsp+38h+arg_8]
0x18000a80e  add     rsp, 20h
0x18000a812  pop     r15
0x18000a814  pop     rdi
0x18000a815  pop     rsi
0x18000a816  retn
```
