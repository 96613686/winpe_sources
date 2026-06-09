# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetCachedFeatureEnabledState(void)

- ea: `0x18002caec`
- end: `0x18002cc84`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `408`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018a50`
- `0x18001a724`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x18002caec`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edx
  int v10; // eax
  int v11; // edi
  char v12; // al
  int v13; // eax
  int v14; // edi
  signed __int32 v15; // eax
  bool v16; // zf
  signed __int32 v17; // edx
  int v18; // r8d
  int v19; // r9d
  signed __int32 v20; // ecx
  wil::details *v22; // [rsp+40h] [rbp+8h] BYREF

  v22 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Bugfix_TextInputManagementServiceLeak__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Bugfix_TextInputManagementServiceLeak__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v22) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x3888D7F,
                          3u,
                          (enum FEATURE_CHANGE_TIME)&v22,
                          v6);
  v8 = FeatureEnabledState & 0xFFFFFF3F;
  v9 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v10 = 0;
  if ( v8 == 2 )
    v10 = 64;
  v11 = v10 | (8 * v9);
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v12 = 1;
  }
  else
  {
    if ( (v11 & 0x40) != 0 )
      goto LABEL_11;
    v12 = 0;
  }
  if ( (v11 & 0x40) == 0 || !v12 )
  {
    v13 = 0;
    goto LABEL_12;
  }
LABEL_11:
  v13 = 1;
LABEL_12:
  v14 = v13 | v11;
  v15 = *(_DWORD *)a2;
  do
  {
    v16 = (_DWORD)v22 == 0;
    v17 = v15;
    *(_DWORD *)a2 = v15;
    if ( v16 || (v15 & 2) != 0 )
    {
      v18 = v15;
    }
    else
    {
      v18 = v15
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)v14)
          & 0x180
          ^ (v14
           ^ v15
           ^ ((unsigned __int16)v15
            ^ (unsigned __int16)v14)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v14
           ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v14
           ^ (unsigned __int16)(v15
                              ^ (v15
                               ^ v14)
                              & 0x180
                              ^ (v14
                               ^ v15
                               ^ (v15
                                ^ v14)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v14
                               ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v18;
    }
    v19 = v15 & 4;
    if ( (v15 & 4) != 0 )
    {
      v20 = v18;
    }
    else
    {
      v20 = v18 ^ ((unsigned __int16)v18 ^ (unsigned __int16)v14) & 0x400 | 4;
      *(_DWORD *)a2 = v20;
    }
    v15 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_Bugfix_TextInputManagementServiceLeak__descriptor,
            v20,
            v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_Bugfix_TextInputManagementServiceLeak__descriptor,
      3,
      v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v14
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v14
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v14
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v14
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v14
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v14
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v14
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v14
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v14
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v14
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v14
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v14
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v14
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v14
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v14
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x18002caec  mov     [rsp+arg_8], rbx
0x18002caf1  mov     [rsp+arg_10], rbp
0x18002caf6  mov     [rsp+arg_0], rcx
0x18002cafb  push    rsi
0x18002cafc  push    rdi
0x18002cafd  push    r15
0x18002caff  sub     rsp, 20h
0x18002cb03  mov     rsi, cs:Feature_Bugfix_TextInputManagementServiceLeak__descriptor
0x18002cb0a  mov     rbx, rdx
0x18002cb0d  mov     qword ptr [rdx], 0
0x18002cb14  mov     eax, [rsi]
0x18002cb16  mov     [rdx], eax
0x18002cb18  and     eax, 6
0x18002cb1b  cmp     al, 6
0x18002cb1d  jz      loc_18002CC6E
0x18002cb23  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002cb28  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18002cb2d  mov     dword ptr [rsp+38h+arg_0], 0
0x18002cb35  mov     edx, 3; unsigned int
0x18002cb3a  mov     ecx, 3888D7Fh; this
0x18002cb3f  mov     ebp, eax
0x18002cb41  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18002cb46  mov     r8d, eax
0x18002cb49  mov     ecx, eax
0x18002cb4b  and     eax, 80h
0x18002cb50  and     r8d, 0FFFFFF3Fh
0x18002cb57  mov     edx, r8d
0x18002cb5a  mov     r15d, 40h ; '@'
0x18002cb60  and     edx, 3
0x18002cb63  and     ecx, r15d
0x18002cb66  shl     edx, 2
0x18002cb69  or      edx, ecx
0x18002cb6b  shl     edx, 2
0x18002cb6e  or      edx, eax
0x18002cb70  xor     eax, eax
0x18002cb72  lea     edi, ds:0[rdx*8]
0x18002cb79  test    r8d, r8d
0x18002cb7c  jz      short loc_18002CB86
0x18002cb7e  cmp     r8d, 2
0x18002cb82  cmovz   eax, r15d
0x18002cb86  or      edi, eax
0x18002cb88  mov     edx, 0C00h
0x18002cb8d  mov     ecx, edi
0x18002cb8f  mov     eax, edi
0x18002cb91  and     ecx, r15d
0x18002cb94  and     eax, edx
0x18002cb96  cmp     eax, edx
0x18002cb98  jnz     short loc_18002CB9E
0x18002cb9a  mov     al, 1
0x18002cb9c  jmp     short loc_18002CBA4
0x18002cb9e  test    ecx, ecx
0x18002cba0  jnz     short loc_18002CBB0
0x18002cba2  xor     al, al
0x18002cba4  test    ecx, ecx
0x18002cba6  jz      short loc_18002CBAC
0x18002cba8  test    al, al
0x18002cbaa  jnz     short loc_18002CBB0
0x18002cbac  xor     eax, eax
0x18002cbae  jmp     short loc_18002CBB5
0x18002cbb0  mov     eax, 1
0x18002cbb5  or      edi, eax
0x18002cbb7  mov     eax, [rbx]
0x18002cbb9  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002cbbe  mov     edx, eax
0x18002cbc0  mov     [rbx], eax
0x18002cbc2  jz      short loc_18002CBFF
0x18002cbc4  test    dl, 2
0x18002cbc7  jnz     short loc_18002CBFF
0x18002cbc9  mov     eax, edi
0x18002cbcb  xor     eax, edx
0x18002cbcd  and     eax, 180h
0x18002cbd2  xor     eax, edx
0x18002cbd4  mov     ecx, eax
0x18002cbd6  xor     ecx, edi
0x18002cbd8  and     ecx, r15d
0x18002cbdb  xor     ecx, eax
0x18002cbdd  mov     eax, ecx
0x18002cbdf  xor     eax, edi
0x18002cbe1  and     eax, 1
0x18002cbe4  xor     eax, ecx
0x18002cbe6  mov     r8d, eax
0x18002cbe9  xor     r8d, edi
0x18002cbec  and     r8d, 800h
0x18002cbf3  xor     r8d, eax
0x18002cbf6  or      r8d, 2
0x18002cbfa  mov     [rbx], r8d
0x18002cbfd  jmp     short loc_18002CC02
0x18002cbff  mov     r8d, edx
0x18002cc02  mov     r9d, edx
0x18002cc05  and     r9d, 4
0x18002cc09  jnz     short loc_18002CC20
0x18002cc0b  mov     ecx, edi
0x18002cc0d  xor     ecx, r8d
0x18002cc10  and     ecx, 400h
0x18002cc16  xor     ecx, r8d
0x18002cc19  or      ecx, 4
0x18002cc1c  mov     [rbx], ecx
0x18002cc1e  jmp     short loc_18002CC23
0x18002cc20  mov     ecx, r8d
0x18002cc23  mov     eax, edx
0x18002cc25  lock cmpxchg [rsi], ecx
0x18002cc29  jnz     short loc_18002CBB9
0x18002cc2b  test    r9d, r9d
0x18002cc2e  jnz     short loc_18002CC3F
0x18002cc30  mov     r8d, ebp
0x18002cc33  lea     edx, [r9+3]
0x18002cc37  mov     rcx, rsi
0x18002cc3a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002cc3f  test    byte ptr [rbx], 2
0x18002cc42  jnz     short loc_18002CC6E
0x18002cc44  mov     eax, [rbx]
0x18002cc46  xor     eax, edi
0x18002cc48  and     eax, 180h
0x18002cc4d  xor     eax, [rbx]
0x18002cc4f  mov     ecx, eax
0x18002cc51  xor     ecx, edi
0x18002cc53  and     ecx, r15d
0x18002cc56  xor     ecx, eax
0x18002cc58  mov     edx, ecx
0x18002cc5a  xor     edx, edi
0x18002cc5c  and     edx, 1
0x18002cc5f  xor     edx, ecx
0x18002cc61  mov     eax, edx
0x18002cc63  xor     eax, edi
0x18002cc65  and     eax, 800h
0x18002cc6a  xor     eax, edx
0x18002cc6c  mov     [rbx], eax
0x18002cc6e  mov     rbp, [rsp+38h+arg_10]
0x18002cc73  mov     rax, rbx
0x18002cc76  mov     rbx, [rsp+38h+arg_8]
0x18002cc7b  add     rsp, 20h
0x18002cc7f  pop     r15
0x18002cc81  pop     rdi
0x18002cc82  pop     rsi
0x18002cc83  retn
```
