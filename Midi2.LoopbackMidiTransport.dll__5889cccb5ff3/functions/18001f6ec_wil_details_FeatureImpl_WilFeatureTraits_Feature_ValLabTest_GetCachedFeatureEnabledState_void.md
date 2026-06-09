# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f6ec`
- end: `0x18001f863`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff9c`

## callees

- `0x18001e65c`
- `0x18001f6ec`
- `0x180020fe4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x18001f6ec  mov     [rsp+arg_8], rbx
0x18001f6f1  mov     [rsp+arg_10], rbp
0x18001f6f6  mov     [rsp+arg_0], rcx
0x18001f6fb  push    rsi
0x18001f6fc  push    rdi
0x18001f6fd  push    r15
0x18001f6ff  sub     rsp, 20h
0x18001f703  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18001f70a  mov     rbx, rdx
0x18001f70d  mov     qword ptr [rdx], 0
0x18001f714  mov     eax, [rsi]
0x18001f716  mov     [rdx], eax
0x18001f718  and     eax, 6
0x18001f71b  cmp     al, 6
0x18001f71d  jz      loc_18001F84D
0x18001f723  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f728  mov     ebp, eax
0x18001f72a  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f732  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f739  test    rax, rax
0x18001f73c  jz      short loc_18001F756
0x18001f73e  lea     r8, [rsp+38h+arg_0]
0x18001f743  mov     edx, 3
0x18001f748  mov     ecx, 3667CA2h
0x18001f74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f752  mov     edx, eax
0x18001f754  jmp     short loc_18001F764
0x18001f756  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f75d  test    rax, rax
0x18001f760  jnz     short loc_18001F73E
0x18001f762  xor     edx, edx
0x18001f764  mov     r8d, edx
0x18001f767  mov     eax, edx
0x18001f769  and     r8d, 0FFFFFF3Fh
0x18001f770  and     edx, 80h
0x18001f776  mov     ecx, r8d
0x18001f779  mov     r15d, 40h ; '@'
0x18001f77f  and     ecx, 3
0x18001f782  and     eax, r15d
0x18001f785  shl     ecx, 2
0x18001f788  or      ecx, eax
0x18001f78a  shl     ecx, 2
0x18001f78d  or      ecx, edx
0x18001f78f  lea     edi, ds:0[rcx*8]
0x18001f796  test    r8d, r8d
0x18001f799  jnz     short loc_18001F7A0
0x18001f79b  mov     eax, r15d
0x18001f79e  jmp     short loc_18001F7AA
0x18001f7a0  xor     eax, eax
0x18001f7a2  cmp     r8d, 2
0x18001f7a6  cmovz   eax, r15d
0x18001f7aa  or      edi, eax
0x18001f7ac  mov     eax, [rbx]
0x18001f7ae  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f7b3  mov     edx, eax
0x18001f7b5  mov     [rbx], eax
0x18001f7b7  jz      short loc_18001F7E7
0x18001f7b9  test    dl, 2
0x18001f7bc  jnz     short loc_18001F7E7
0x18001f7be  mov     eax, edi
0x18001f7c0  xor     eax, edx
0x18001f7c2  and     eax, 180h
0x18001f7c7  xor     eax, edx
0x18001f7c9  mov     ecx, eax
0x18001f7cb  xor     ecx, edi
0x18001f7cd  and     ecx, r15d
0x18001f7d0  xor     ecx, eax
0x18001f7d2  or      ecx, 1
0x18001f7d5  mov     eax, ecx
0x18001f7d7  xor     eax, edi
0x18001f7d9  and     eax, 800h
0x18001f7de  xor     eax, ecx
0x18001f7e0  or      eax, 2
0x18001f7e3  mov     [rbx], eax
0x18001f7e5  jmp     short loc_18001F7E9
0x18001f7e7  mov     eax, edx
0x18001f7e9  mov     r8d, edx
0x18001f7ec  and     r8d, 4
0x18001f7f0  jnz     short loc_18001F805
0x18001f7f2  mov     ecx, edi
0x18001f7f4  xor     ecx, eax
0x18001f7f6  and     ecx, 400h
0x18001f7fc  xor     ecx, eax
0x18001f7fe  or      ecx, 4
0x18001f801  mov     [rbx], ecx
0x18001f803  jmp     short loc_18001F807
0x18001f805  mov     ecx, eax
0x18001f807  mov     eax, edx
0x18001f809  lock cmpxchg [rsi], ecx
0x18001f80d  jnz     short loc_18001F7AE
0x18001f80f  test    r8d, r8d
0x18001f812  jnz     short loc_18001F824
0x18001f814  mov     r8d, ebp
0x18001f817  mov     edx, 3
0x18001f81c  mov     rcx, rsi
0x18001f81f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f824  test    byte ptr [rbx], 2
0x18001f827  jnz     short loc_18001F84D
0x18001f829  mov     eax, [rbx]
0x18001f82b  xor     eax, edi
0x18001f82d  and     eax, 180h
0x18001f832  xor     eax, [rbx]
0x18001f834  mov     ecx, eax
0x18001f836  xor     ecx, edi
0x18001f838  and     ecx, r15d
0x18001f83b  xor     ecx, eax
0x18001f83d  or      ecx, 1
0x18001f840  mov     eax, ecx
0x18001f842  xor     eax, edi
0x18001f844  and     eax, 800h
0x18001f849  xor     eax, ecx
0x18001f84b  mov     [rbx], eax
0x18001f84d  mov     rbp, [rsp+38h+arg_10]
0x18001f852  mov     rax, rbx
0x18001f855  mov     rbx, [rsp+38h+arg_8]
0x18001f85a  add     rsp, 20h
0x18001f85e  pop     r15
0x18001f860  pop     rdi
0x18001f861  pop     rsi
0x18001f862  retn
```
