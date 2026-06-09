# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c088`
- end: `0x18000c1d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `333`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c39c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000c088`
- `0x18000cfc0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2F29A04,
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
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v13)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v13)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v12 ^ v13) & 0x180 ^ (v12 ^ v13 ^ (v12 ^ v13) & 0x180) & 0x40) | 1))
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
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v5);
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
0x18000c088  mov     [rsp+arg_8], rbx
0x18000c08d  mov     [rsp+arg_10], rbp
0x18000c092  mov     [rsp+arg_0], rcx
0x18000c097  push    rsi
0x18000c098  push    rdi
0x18000c099  push    r15
0x18000c09b  sub     rsp, 20h
0x18000c09f  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000c0a6  mov     rbx, rdx
0x18000c0a9  mov     qword ptr [rdx], 0
0x18000c0b0  mov     eax, [rsi]
0x18000c0b2  mov     [rdx], eax
0x18000c0b4  and     eax, 6
0x18000c0b7  cmp     al, 6
0x18000c0b9  jz      loc_18000C1BF
0x18000c0bf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c0c4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18000c0c9  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c0d1  mov     ecx, 2F29A04h; this
0x18000c0d6  mov     ebp, eax
0x18000c0d8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000c0dd  mov     r8d, eax
0x18000c0e0  mov     ecx, eax
0x18000c0e2  and     r8d, 0FFFFFF3Fh
0x18000c0e9  and     eax, 80h
0x18000c0ee  mov     edx, r8d
0x18000c0f1  mov     r15d, 40h ; '@'
0x18000c0f7  and     edx, 3
0x18000c0fa  and     ecx, r15d
0x18000c0fd  shl     edx, 2
0x18000c100  or      edx, ecx
0x18000c102  shl     edx, 2
0x18000c105  or      edx, eax
0x18000c107  lea     edi, ds:0[rdx*8]
0x18000c10e  test    r8d, r8d
0x18000c111  jnz     short loc_18000C118
0x18000c113  mov     eax, r15d
0x18000c116  jmp     short loc_18000C122
0x18000c118  xor     eax, eax
0x18000c11a  cmp     r8d, 2
0x18000c11e  cmovz   eax, r15d
0x18000c122  or      edi, eax
0x18000c124  mov     eax, [rbx]
0x18000c126  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c12b  mov     edx, eax
0x18000c12d  mov     [rbx], eax
0x18000c12f  jz      short loc_18000C15B
0x18000c131  test    dl, 2
0x18000c134  jnz     short loc_18000C15B
0x18000c136  xor     eax, edi
0x18000c138  and     eax, 180h
0x18000c13d  xor     eax, edx
0x18000c13f  mov     ecx, eax
0x18000c141  xor     ecx, edi
0x18000c143  and     ecx, r15d
0x18000c146  xor     ecx, eax
0x18000c148  or      ecx, 1
0x18000c14b  mov     eax, ecx
0x18000c14d  xor     eax, edi
0x18000c14f  and     eax, 800h
0x18000c154  xor     eax, ecx
0x18000c156  or      eax, 2
0x18000c159  mov     [rbx], eax
0x18000c15b  mov     r8d, edx
0x18000c15e  and     r8d, 4
0x18000c162  jnz     short loc_18000C177
0x18000c164  mov     ecx, edi
0x18000c166  xor     ecx, eax
0x18000c168  and     ecx, 400h
0x18000c16e  xor     ecx, eax
0x18000c170  or      ecx, 4
0x18000c173  mov     [rbx], ecx
0x18000c175  jmp     short loc_18000C179
0x18000c177  mov     ecx, eax
0x18000c179  mov     eax, edx
0x18000c17b  lock cmpxchg [rsi], ecx
0x18000c17f  jnz     short loc_18000C126
0x18000c181  test    r8d, r8d
0x18000c184  jnz     short loc_18000C196
0x18000c186  mov     r8d, ebp
0x18000c189  mov     edx, 3
0x18000c18e  mov     rcx, rsi
0x18000c191  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c196  test    byte ptr [rbx], 2
0x18000c199  jnz     short loc_18000C1BF
0x18000c19b  mov     eax, [rbx]
0x18000c19d  xor     eax, edi
0x18000c19f  and     eax, 180h
0x18000c1a4  xor     eax, [rbx]
0x18000c1a6  mov     ecx, eax
0x18000c1a8  xor     ecx, edi
0x18000c1aa  and     ecx, r15d
0x18000c1ad  xor     ecx, eax
0x18000c1af  or      ecx, 1
0x18000c1b2  mov     eax, ecx
0x18000c1b4  xor     eax, edi
0x18000c1b6  and     eax, 800h
0x18000c1bb  xor     eax, ecx
0x18000c1bd  mov     [rbx], eax
0x18000c1bf  mov     rbp, [rsp+38h+arg_10]
0x18000c1c4  mov     rax, rbx
0x18000c1c7  mov     rbx, [rsp+38h+arg_8]
0x18000c1cc  add     rsp, 20h
0x18000c1d0  pop     r15
0x18000c1d2  pop     rdi
0x18000c1d3  pop     rsi
0x18000c1d4  retn
```
