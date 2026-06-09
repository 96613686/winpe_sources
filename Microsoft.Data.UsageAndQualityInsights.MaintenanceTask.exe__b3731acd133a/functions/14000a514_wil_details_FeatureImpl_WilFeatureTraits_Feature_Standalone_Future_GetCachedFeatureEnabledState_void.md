# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x14000a514`
- end: `0x14000a68b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a944`

## callees

- `0x140004568`
- `0x140007e64`
- `0x14000a514`
- `0x14000c010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v4);
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
0x14000a514  mov     [rsp+arg_8], rbx
0x14000a519  mov     [rsp+arg_10], rbp
0x14000a51e  mov     [rsp+arg_0], rcx
0x14000a523  push    rsi
0x14000a524  push    rdi
0x14000a525  push    r15
0x14000a527  sub     rsp, 20h
0x14000a52b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x14000a532  mov     rbx, rdx
0x14000a535  mov     qword ptr [rdx], 0
0x14000a53c  mov     eax, [rsi]
0x14000a53e  mov     [rdx], eax
0x14000a540  and     eax, 6
0x14000a543  cmp     al, 6
0x14000a545  jz      loc_14000A675
0x14000a54b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a550  mov     ebp, eax
0x14000a552  mov     dword ptr [rsp+38h+arg_0], 0
0x14000a55a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000a561  test    rax, rax
0x14000a564  jz      short loc_14000A57E
0x14000a566  lea     r8, [rsp+38h+arg_0]
0x14000a56b  mov     edx, 3
0x14000a570  mov     ecx, 2F29A04h
0x14000a575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a57a  mov     edx, eax
0x14000a57c  jmp     short loc_14000A58C
0x14000a57e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000a585  test    rax, rax
0x14000a588  jnz     short loc_14000A566
0x14000a58a  xor     edx, edx
0x14000a58c  mov     r8d, edx
0x14000a58f  mov     eax, edx
0x14000a591  and     r8d, 0FFFFFF3Fh
0x14000a598  and     edx, 80h
0x14000a59e  mov     ecx, r8d
0x14000a5a1  mov     r15d, 40h ; '@'
0x14000a5a7  and     ecx, 3
0x14000a5aa  and     eax, r15d
0x14000a5ad  shl     ecx, 2
0x14000a5b0  or      ecx, eax
0x14000a5b2  shl     ecx, 2
0x14000a5b5  or      ecx, edx
0x14000a5b7  lea     edi, ds:0[rcx*8]
0x14000a5be  test    r8d, r8d
0x14000a5c1  jnz     short loc_14000A5C8
0x14000a5c3  mov     eax, r15d
0x14000a5c6  jmp     short loc_14000A5D2
0x14000a5c8  xor     eax, eax
0x14000a5ca  cmp     r8d, 2
0x14000a5ce  cmovz   eax, r15d
0x14000a5d2  or      edi, eax
0x14000a5d4  mov     eax, [rbx]
0x14000a5d6  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000a5db  mov     edx, eax
0x14000a5dd  mov     [rbx], eax
0x14000a5df  jz      short loc_14000A60F
0x14000a5e1  test    dl, 2
0x14000a5e4  jnz     short loc_14000A60F
0x14000a5e6  mov     eax, edi
0x14000a5e8  xor     eax, edx
0x14000a5ea  and     eax, 180h
0x14000a5ef  xor     eax, edx
0x14000a5f1  mov     ecx, eax
0x14000a5f3  xor     ecx, edi
0x14000a5f5  and     ecx, r15d
0x14000a5f8  xor     ecx, eax
0x14000a5fa  or      ecx, 1
0x14000a5fd  mov     eax, ecx
0x14000a5ff  xor     eax, edi
0x14000a601  and     eax, 800h
0x14000a606  xor     eax, ecx
0x14000a608  or      eax, 2
0x14000a60b  mov     [rbx], eax
0x14000a60d  jmp     short loc_14000A611
0x14000a60f  mov     eax, edx
0x14000a611  mov     r8d, edx
0x14000a614  and     r8d, 4
0x14000a618  jnz     short loc_14000A62D
0x14000a61a  mov     ecx, edi
0x14000a61c  xor     ecx, eax
0x14000a61e  and     ecx, 400h
0x14000a624  xor     ecx, eax
0x14000a626  or      ecx, 4
0x14000a629  mov     [rbx], ecx
0x14000a62b  jmp     short loc_14000A62F
0x14000a62d  mov     ecx, eax
0x14000a62f  mov     eax, edx
0x14000a631  lock cmpxchg [rsi], ecx
0x14000a635  jnz     short loc_14000A5D6
0x14000a637  test    r8d, r8d
0x14000a63a  jnz     short loc_14000A64C
0x14000a63c  mov     r8d, ebp
0x14000a63f  mov     edx, 3
0x14000a644  mov     rcx, rsi
0x14000a647  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a64c  test    byte ptr [rbx], 2
0x14000a64f  jnz     short loc_14000A675
0x14000a651  mov     eax, [rbx]
0x14000a653  xor     eax, edi
0x14000a655  and     eax, 180h
0x14000a65a  xor     eax, [rbx]
0x14000a65c  mov     ecx, eax
0x14000a65e  xor     ecx, edi
0x14000a660  and     ecx, r15d
0x14000a663  xor     ecx, eax
0x14000a665  or      ecx, 1
0x14000a668  mov     eax, ecx
0x14000a66a  xor     eax, edi
0x14000a66c  and     eax, 800h
0x14000a671  xor     eax, ecx
0x14000a673  mov     [rbx], eax
0x14000a675  mov     rbp, [rsp+38h+arg_10]
0x14000a67a  mov     rax, rbx
0x14000a67d  mov     rbx, [rsp+38h+arg_8]
0x14000a682  add     rsp, 20h
0x14000a686  pop     r15
0x14000a688  pop     rdi
0x14000a689  pop     rsi
0x14000a68a  retn
```
