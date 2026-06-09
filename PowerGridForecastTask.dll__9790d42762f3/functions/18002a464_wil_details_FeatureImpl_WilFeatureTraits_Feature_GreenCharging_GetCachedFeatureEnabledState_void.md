# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GreenCharging>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a464`
- end: `0x18002a5db`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GreenCharging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002da2c`

## callees

- `0x180029a34`
- `0x18002a464`
- `0x18002ee7c`
- `0x180037010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GreenCharging>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GreenCharging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GreenCharging__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45690917, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GreenCharging__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_GreenCharging__descriptor, 3, v4);
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
0x18002a464  mov     [rsp+arg_8], rbx
0x18002a469  mov     [rsp+arg_10], rbp
0x18002a46e  mov     [rsp+arg_0], rcx
0x18002a473  push    rsi
0x18002a474  push    rdi
0x18002a475  push    r15
0x18002a477  sub     rsp, 20h
0x18002a47b  mov     rsi, cs:Feature_GreenCharging__descriptor
0x18002a482  mov     rbx, rdx
0x18002a485  mov     qword ptr [rdx], 0
0x18002a48c  mov     eax, [rsi]
0x18002a48e  mov     [rdx], eax
0x18002a490  and     eax, 6
0x18002a493  cmp     al, 6
0x18002a495  jz      loc_18002A5C5
0x18002a49b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002a4a0  mov     ebp, eax
0x18002a4a2  mov     dword ptr [rsp+38h+arg_0], 0
0x18002a4aa  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002a4b1  test    rax, rax
0x18002a4b4  jz      short loc_18002A4CE
0x18002a4b6  lea     r8, [rsp+38h+arg_0]
0x18002a4bb  mov     edx, 3
0x18002a4c0  mov     ecx, 2B93025h
0x18002a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4ca  mov     edx, eax
0x18002a4cc  jmp     short loc_18002A4DC
0x18002a4ce  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002a4d5  test    rax, rax
0x18002a4d8  jnz     short loc_18002A4B6
0x18002a4da  xor     edx, edx
0x18002a4dc  mov     r8d, edx
0x18002a4df  mov     eax, edx
0x18002a4e1  and     r8d, 0FFFFFF3Fh
0x18002a4e8  and     edx, 80h
0x18002a4ee  mov     ecx, r8d
0x18002a4f1  mov     r15d, 40h ; '@'
0x18002a4f7  and     ecx, 3
0x18002a4fa  and     eax, r15d
0x18002a4fd  shl     ecx, 2
0x18002a500  or      ecx, eax
0x18002a502  shl     ecx, 2
0x18002a505  or      ecx, edx
0x18002a507  lea     edi, ds:0[rcx*8]
0x18002a50e  test    r8d, r8d
0x18002a511  jnz     short loc_18002A518
0x18002a513  mov     eax, r15d
0x18002a516  jmp     short loc_18002A522
0x18002a518  xor     eax, eax
0x18002a51a  cmp     r8d, 2
0x18002a51e  cmovz   eax, r15d
0x18002a522  or      edi, eax
0x18002a524  mov     eax, [rbx]
0x18002a526  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002a52b  mov     edx, eax
0x18002a52d  mov     [rbx], eax
0x18002a52f  jz      short loc_18002A55F
0x18002a531  test    dl, 2
0x18002a534  jnz     short loc_18002A55F
0x18002a536  mov     eax, edi
0x18002a538  xor     eax, edx
0x18002a53a  and     eax, 180h
0x18002a53f  xor     eax, edx
0x18002a541  mov     ecx, eax
0x18002a543  xor     ecx, edi
0x18002a545  and     ecx, r15d
0x18002a548  xor     ecx, eax
0x18002a54a  or      ecx, 1
0x18002a54d  mov     eax, ecx
0x18002a54f  xor     eax, edi
0x18002a551  and     eax, 800h
0x18002a556  xor     eax, ecx
0x18002a558  or      eax, 2
0x18002a55b  mov     [rbx], eax
0x18002a55d  jmp     short loc_18002A561
0x18002a55f  mov     eax, edx
0x18002a561  mov     r8d, edx
0x18002a564  and     r8d, 4
0x18002a568  jnz     short loc_18002A57D
0x18002a56a  mov     ecx, edi
0x18002a56c  xor     ecx, eax
0x18002a56e  and     ecx, 400h
0x18002a574  xor     ecx, eax
0x18002a576  or      ecx, 4
0x18002a579  mov     [rbx], ecx
0x18002a57b  jmp     short loc_18002A57F
0x18002a57d  mov     ecx, eax
0x18002a57f  mov     eax, edx
0x18002a581  lock cmpxchg [rsi], ecx
0x18002a585  jnz     short loc_18002A526
0x18002a587  test    r8d, r8d
0x18002a58a  jnz     short loc_18002A59C
0x18002a58c  mov     r8d, ebp
0x18002a58f  mov     edx, 3
0x18002a594  mov     rcx, rsi
0x18002a597  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002a59c  test    byte ptr [rbx], 2
0x18002a59f  jnz     short loc_18002A5C5
0x18002a5a1  mov     eax, [rbx]
0x18002a5a3  xor     eax, edi
0x18002a5a5  and     eax, 180h
0x18002a5aa  xor     eax, [rbx]
0x18002a5ac  mov     ecx, eax
0x18002a5ae  xor     ecx, edi
0x18002a5b0  and     ecx, r15d
0x18002a5b3  xor     ecx, eax
0x18002a5b5  or      ecx, 1
0x18002a5b8  mov     eax, ecx
0x18002a5ba  xor     eax, edi
0x18002a5bc  and     eax, 800h
0x18002a5c1  xor     eax, ecx
0x18002a5c3  mov     [rbx], eax
0x18002a5c5  mov     rbp, [rsp+38h+arg_10]
0x18002a5ca  mov     rax, rbx
0x18002a5cd  mov     rbx, [rsp+38h+arg_8]
0x18002a5d2  add     rsp, 20h
0x18002a5d6  pop     r15
0x18002a5d8  pop     rdi
0x18002a5d9  pop     rsi
0x18002a5da  retn
```
