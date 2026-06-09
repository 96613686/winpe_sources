# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800210b8`
- end: `0x18002120a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `338`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022288`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x1800210b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2F29A04,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v11
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v11
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v11 ^ v12) & 0x180 ^ (v11 ^ v12 ^ (v11 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x1800210b8  mov     [rsp+arg_8], rbx
0x1800210bd  mov     [rsp+arg_10], rbp
0x1800210c2  mov     [rsp+arg_0], rcx
0x1800210c7  push    rsi
0x1800210c8  push    rdi
0x1800210c9  push    r15
0x1800210cb  sub     rsp, 20h
0x1800210cf  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800210d6  mov     rbx, rdx
0x1800210d9  mov     qword ptr [rdx], 0
0x1800210e0  mov     eax, [rsi]
0x1800210e2  mov     [rdx], eax
0x1800210e4  and     eax, 6
0x1800210e7  cmp     al, 6
0x1800210e9  jz      loc_1800211F4
0x1800210ef  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800210f4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800210f9  mov     dword ptr [rsp+38h+arg_0], 0
0x180021101  mov     edx, 3; unsigned int
0x180021106  mov     ecx, 2F29A04h; this
0x18002110b  mov     ebp, eax
0x18002110d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180021112  mov     r8d, eax
0x180021115  mov     ecx, eax
0x180021117  and     r8d, 0FFFFFF3Fh
0x18002111e  and     eax, 80h
0x180021123  mov     edx, r8d
0x180021126  mov     r15d, 40h ; '@'
0x18002112c  and     edx, 3
0x18002112f  and     ecx, r15d
0x180021132  shl     edx, 2
0x180021135  or      edx, ecx
0x180021137  shl     edx, 2
0x18002113a  or      edx, eax
0x18002113c  lea     edi, ds:0[rdx*8]
0x180021143  test    r8d, r8d
0x180021146  jnz     short loc_18002114D
0x180021148  mov     eax, r15d
0x18002114b  jmp     short loc_180021157
0x18002114d  xor     eax, eax
0x18002114f  cmp     r8d, 2
0x180021153  cmovz   eax, r15d
0x180021157  or      edi, eax
0x180021159  mov     eax, [rbx]
0x18002115b  cmp     dword ptr [rsp+38h+arg_0], 0
0x180021160  mov     edx, eax
0x180021162  mov     [rbx], eax
0x180021164  jz      short loc_180021190
0x180021166  test    dl, 2
0x180021169  jnz     short loc_180021190
0x18002116b  xor     eax, edi
0x18002116d  and     eax, 180h
0x180021172  xor     eax, edx
0x180021174  mov     ecx, eax
0x180021176  xor     ecx, edi
0x180021178  and     ecx, r15d
0x18002117b  xor     ecx, eax
0x18002117d  or      ecx, 1
0x180021180  mov     eax, ecx
0x180021182  xor     eax, edi
0x180021184  and     eax, 800h
0x180021189  xor     eax, ecx
0x18002118b  or      eax, 2
0x18002118e  mov     [rbx], eax
0x180021190  mov     r8d, edx
0x180021193  and     r8d, 4
0x180021197  jnz     short loc_1800211AC
0x180021199  mov     ecx, edi
0x18002119b  xor     ecx, eax
0x18002119d  and     ecx, 400h
0x1800211a3  xor     ecx, eax
0x1800211a5  or      ecx, 4
0x1800211a8  mov     [rbx], ecx
0x1800211aa  jmp     short loc_1800211AE
0x1800211ac  mov     ecx, eax
0x1800211ae  mov     eax, edx
0x1800211b0  lock cmpxchg [rsi], ecx
0x1800211b4  jnz     short loc_18002115B
0x1800211b6  test    r8d, r8d
0x1800211b9  jnz     short loc_1800211CB
0x1800211bb  mov     r8d, ebp
0x1800211be  mov     edx, 3
0x1800211c3  mov     rcx, rsi
0x1800211c6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800211cb  test    byte ptr [rbx], 2
0x1800211ce  jnz     short loc_1800211F4
0x1800211d0  mov     eax, [rbx]
0x1800211d2  xor     eax, edi
0x1800211d4  and     eax, 180h
0x1800211d9  xor     eax, [rbx]
0x1800211db  mov     ecx, eax
0x1800211dd  xor     ecx, edi
0x1800211df  and     ecx, r15d
0x1800211e2  xor     ecx, eax
0x1800211e4  or      ecx, 1
0x1800211e7  mov     eax, ecx
0x1800211e9  xor     eax, edi
0x1800211eb  and     eax, 800h
0x1800211f0  xor     eax, ecx
0x1800211f2  mov     [rbx], eax
0x1800211f4  mov     rbp, [rsp+38h+arg_10]
0x1800211f9  mov     rax, rbx
0x1800211fc  mov     rbx, [rsp+38h+arg_8]
0x180021201  add     rsp, 20h
0x180021205  pop     r15
0x180021207  pop     rdi
0x180021208  pop     rsi
0x180021209  retn
```
