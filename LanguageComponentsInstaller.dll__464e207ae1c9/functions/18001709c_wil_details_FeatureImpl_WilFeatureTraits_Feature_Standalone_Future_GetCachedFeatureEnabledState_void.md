# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001709c`
- end: `0x18001722c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001777c`

## callees

- `0x180003520`
- `0x180016060`
- `0x18001709c`
- `0x18001c760`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  int v14; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v14 = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
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
      v10 = v14 == 0;
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
0x18001709c  mov     [rsp+arg_0], rbx
0x1800170a1  mov     [rsp+arg_10], rbp
0x1800170a6  push    rsi
0x1800170a7  push    rdi
0x1800170a8  push    r15
0x1800170aa  sub     rsp, 30h
0x1800170ae  mov     rax, cs:__security_cookie
0x1800170b5  xor     rax, rsp
0x1800170b8  mov     [rsp+48h+var_20], rax
0x1800170bd  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800170c4  mov     rbx, rdx
0x1800170c7  mov     qword ptr [rdx], 0
0x1800170ce  mov     eax, [rsi]
0x1800170d0  mov     [rdx], eax
0x1800170d2  and     eax, 6
0x1800170d5  cmp     al, 6
0x1800170d7  jz      loc_180017209
0x1800170dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800170e2  mov     ebp, eax
0x1800170e4  mov     [rsp+48h+var_28], 0
0x1800170ec  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800170f3  test    rax, rax
0x1800170f6  jz      short loc_180017110
0x1800170f8  lea     r8, [rsp+48h+var_28]
0x1800170fd  mov     edx, 3
0x180017102  mov     ecx, 2F29A04h
0x180017107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001710c  mov     edx, eax
0x18001710e  jmp     short loc_18001711E
0x180017110  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180017117  test    rax, rax
0x18001711a  jnz     short loc_1800170F8
0x18001711c  xor     edx, edx
0x18001711e  mov     r8d, edx
0x180017121  mov     eax, edx
0x180017123  and     r8d, 0FFFFFF3Fh
0x18001712a  and     edx, 80h
0x180017130  mov     ecx, r8d
0x180017133  mov     r15d, 40h ; '@'
0x180017139  and     ecx, 3
0x18001713c  and     eax, r15d
0x18001713f  shl     ecx, 2
0x180017142  or      ecx, eax
0x180017144  shl     ecx, 2
0x180017147  or      ecx, edx
0x180017149  lea     edi, ds:0[rcx*8]
0x180017150  test    r8d, r8d
0x180017153  jnz     short loc_18001715A
0x180017155  mov     eax, r15d
0x180017158  jmp     short loc_180017164
0x18001715a  xor     eax, eax
0x18001715c  cmp     r8d, 2
0x180017160  cmovz   eax, r15d
0x180017164  or      edi, eax
0x180017166  mov     eax, [rbx]
0x180017168  cmp     [rsp+48h+var_28], 0
0x18001716d  mov     edx, eax
0x18001716f  mov     [rbx], eax
0x180017171  jz      short loc_1800171A1
0x180017173  test    dl, 2
0x180017176  jnz     short loc_1800171A1
0x180017178  mov     eax, edi
0x18001717a  xor     eax, edx
0x18001717c  and     eax, 180h
0x180017181  xor     eax, edx
0x180017183  mov     ecx, eax
0x180017185  xor     ecx, edi
0x180017187  and     ecx, r15d
0x18001718a  xor     ecx, eax
0x18001718c  or      ecx, 1
0x18001718f  mov     eax, ecx
0x180017191  xor     eax, edi
0x180017193  and     eax, 800h
0x180017198  xor     eax, ecx
0x18001719a  or      eax, 2
0x18001719d  mov     [rbx], eax
0x18001719f  jmp     short loc_1800171A3
0x1800171a1  mov     eax, edx
0x1800171a3  mov     r8d, edx
0x1800171a6  and     r8d, 4
0x1800171aa  jnz     short loc_1800171BF
0x1800171ac  mov     ecx, edi
0x1800171ae  xor     ecx, eax
0x1800171b0  and     ecx, 400h
0x1800171b6  xor     ecx, eax
0x1800171b8  or      ecx, 4
0x1800171bb  mov     [rbx], ecx
0x1800171bd  jmp     short loc_1800171C1
0x1800171bf  mov     ecx, eax
0x1800171c1  mov     eax, edx
0x1800171c3  lock cmpxchg [rsi], ecx
0x1800171c7  jnz     short loc_180017168
0x1800171c9  test    r8d, r8d
0x1800171cc  jnz     short loc_1800171DE
0x1800171ce  mov     r8d, ebp
0x1800171d1  mov     edx, 3
0x1800171d6  mov     rcx, rsi
0x1800171d9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800171de  test    byte ptr [rbx], 2
0x1800171e1  jnz     short loc_180017209
0x1800171e3  mov     ecx, [rbx]
0x1800171e5  xor     ecx, edi
0x1800171e7  and     ecx, 180h
0x1800171ed  xor     ecx, [rbx]
0x1800171ef  mov     edx, ecx
0x1800171f1  xor     edx, edi
0x1800171f3  and     edx, r15d
0x1800171f6  xor     edx, ecx
0x1800171f8  or      edx, 1
0x1800171fb  mov     ecx, edx
0x1800171fd  xor     ecx, edi
0x1800171ff  and     ecx, 800h
0x180017205  xor     ecx, edx
0x180017207  mov     [rbx], ecx
0x180017209  mov     rax, rbx
0x18001720c  mov     rcx, [rsp+48h+var_20]
0x180017211  xor     rcx, rsp; StackCookie
0x180017214  call    __security_check_cookie
0x180017219  mov     rbx, [rsp+48h+arg_0]
0x18001721e  mov     rbp, [rsp+48h+arg_10]
0x180017223  add     rsp, 30h
0x180017227  pop     r15
0x180017229  pop     rdi
0x18001722a  pop     rsi
0x18001722b  retn
```
