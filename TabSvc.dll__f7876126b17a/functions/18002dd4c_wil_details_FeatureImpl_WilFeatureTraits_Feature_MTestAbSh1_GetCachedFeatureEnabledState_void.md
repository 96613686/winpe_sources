# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbSh1>::GetCachedFeatureEnabledState(void)

- ea: `0x18002dd4c`
- end: `0x18002dea4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MTestAbSh1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dec8`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x18002dd4c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbSh1>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MTestAbSh1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MTestAbSh1__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x27DCEF7,
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
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
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
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MTestAbSh1__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_MTestAbSh1__descriptor, 3, v5);
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
0x18002dd4c  mov     [rsp+arg_8], rbx
0x18002dd51  mov     [rsp+arg_10], rbp
0x18002dd56  mov     [rsp+arg_0], rcx
0x18002dd5b  push    rsi
0x18002dd5c  push    rdi
0x18002dd5d  push    r15
0x18002dd5f  sub     rsp, 20h
0x18002dd63  mov     rsi, cs:Feature_MTestAbSh1__descriptor
0x18002dd6a  mov     rbx, rdx
0x18002dd6d  mov     qword ptr [rdx], 0
0x18002dd74  mov     eax, [rsi]
0x18002dd76  mov     [rdx], eax
0x18002dd78  and     eax, 6
0x18002dd7b  cmp     al, 6
0x18002dd7d  jz      loc_18002DE8E
0x18002dd83  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002dd88  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18002dd8d  mov     dword ptr [rsp+38h+arg_0], 0
0x18002dd95  mov     edx, 3; unsigned int
0x18002dd9a  mov     ecx, 27DCEF7h; this
0x18002dd9f  mov     ebp, eax
0x18002dda1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18002dda6  mov     r8d, eax
0x18002dda9  mov     ecx, eax
0x18002ddab  and     r8d, 0FFFFFF3Fh
0x18002ddb2  and     eax, 80h
0x18002ddb7  mov     edx, r8d
0x18002ddba  mov     r15d, 40h ; '@'
0x18002ddc0  and     edx, 3
0x18002ddc3  and     ecx, r15d
0x18002ddc6  shl     edx, 2
0x18002ddc9  or      edx, ecx
0x18002ddcb  shl     edx, 2
0x18002ddce  or      edx, eax
0x18002ddd0  lea     edi, ds:0[rdx*8]
0x18002ddd7  test    r8d, r8d
0x18002ddda  jnz     short loc_18002DDE1
0x18002dddc  mov     eax, r15d
0x18002dddf  jmp     short loc_18002DDEB
0x18002dde1  xor     eax, eax
0x18002dde3  cmp     r8d, 2
0x18002dde7  cmovz   eax, r15d
0x18002ddeb  or      edi, eax
0x18002dded  mov     eax, [rbx]
0x18002ddef  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002ddf4  mov     edx, eax
0x18002ddf6  mov     [rbx], eax
0x18002ddf8  jz      short loc_18002DE28
0x18002ddfa  test    dl, 2
0x18002ddfd  jnz     short loc_18002DE28
0x18002ddff  mov     eax, edi
0x18002de01  xor     eax, edx
0x18002de03  and     eax, 180h
0x18002de08  xor     eax, edx
0x18002de0a  mov     ecx, eax
0x18002de0c  xor     ecx, edi
0x18002de0e  and     ecx, r15d
0x18002de11  xor     ecx, eax
0x18002de13  or      ecx, 1
0x18002de16  mov     eax, ecx
0x18002de18  xor     eax, edi
0x18002de1a  and     eax, 800h
0x18002de1f  xor     eax, ecx
0x18002de21  or      eax, 2
0x18002de24  mov     [rbx], eax
0x18002de26  jmp     short loc_18002DE2A
0x18002de28  mov     eax, edx
0x18002de2a  mov     r8d, edx
0x18002de2d  and     r8d, 4
0x18002de31  jnz     short loc_18002DE46
0x18002de33  mov     ecx, edi
0x18002de35  xor     ecx, eax
0x18002de37  and     ecx, 400h
0x18002de3d  xor     ecx, eax
0x18002de3f  or      ecx, 4
0x18002de42  mov     [rbx], ecx
0x18002de44  jmp     short loc_18002DE48
0x18002de46  mov     ecx, eax
0x18002de48  mov     eax, edx
0x18002de4a  lock cmpxchg [rsi], ecx
0x18002de4e  jnz     short loc_18002DDEF
0x18002de50  test    r8d, r8d
0x18002de53  jnz     short loc_18002DE65
0x18002de55  mov     r8d, ebp
0x18002de58  mov     edx, 3
0x18002de5d  mov     rcx, rsi
0x18002de60  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002de65  test    byte ptr [rbx], 2
0x18002de68  jnz     short loc_18002DE8E
0x18002de6a  mov     eax, [rbx]
0x18002de6c  xor     eax, edi
0x18002de6e  and     eax, 180h
0x18002de73  xor     eax, [rbx]
0x18002de75  mov     ecx, eax
0x18002de77  xor     ecx, edi
0x18002de79  and     ecx, r15d
0x18002de7c  xor     ecx, eax
0x18002de7e  or      ecx, 1
0x18002de81  mov     eax, ecx
0x18002de83  xor     eax, edi
0x18002de85  and     eax, 800h
0x18002de8a  xor     eax, ecx
0x18002de8c  mov     [rbx], eax
0x18002de8e  mov     rbp, [rsp+38h+arg_10]
0x18002de93  mov     rax, rbx
0x18002de96  mov     rbx, [rsp+38h+arg_8]
0x18002de9b  add     rsp, 20h
0x18002de9f  pop     r15
0x18002dea1  pop     rdi
0x18002dea2  pop     rsi
0x18002dea3  retn
```
