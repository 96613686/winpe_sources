# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession>::GetCachedFeatureEnabledState(void)

- ea: `0x1800208ac`
- end: `0x180020a4f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `419`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019c3c`
- `0x180019c78`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x1800208ac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreventLaunchingTabTipInMultiSession>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  char v12; // cl
  int v13; // eax
  int v14; // eax
  int v15; // ebx
  signed __int32 v16; // eax
  bool v17; // zf
  signed __int32 v18; // edx
  int v19; // r8d
  int v20; // r9d
  signed __int32 v21; // ecx
  wil::details *v23; // [rsp+40h] [rbp+8h] BYREF

  v23 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_PreventLaunchingTabTipInMultiSession__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PreventLaunchingTabTipInMultiSession__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v23) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x2CFF0EB,
                          1u,
                          (enum FEATURE_CHANGE_TIME)&v23,
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
    v13 = v11 & 0x40;
  }
  else
  {
    v13 = v11 & 0x40;
    if ( (v11 & 0x40) != 0 )
      goto LABEL_14;
    v12 = 0;
  }
  if ( !v13 || !v12 )
  {
    v14 = 0;
    goto LABEL_15;
  }
LABEL_14:
  v14 = 1;
LABEL_15:
  v15 = v14 | v11;
  v16 = *(_DWORD *)a2;
  do
  {
    v17 = (_DWORD)v23 == 0;
    v18 = v16;
    *(_DWORD *)a2 = v16;
    if ( v17 || (v16 & 2) != 0 )
    {
      v19 = v16;
    }
    else
    {
      v19 = v16
          ^ ((unsigned __int16)v16
           ^ (unsigned __int16)v15)
          & 0x180
          ^ (v15
           ^ v16
           ^ ((unsigned __int16)v16
            ^ (unsigned __int16)v15)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v16 ^ (v16 ^ v15) & 0x80 ^ (v15 ^ v16 ^ (v16 ^ v15) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)(v16
                              ^ (v16
                               ^ v15)
                              & 0x180
                              ^ (v15
                               ^ v16
                               ^ (v16
                                ^ v15)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v15
                               ^ (unsigned __int8)(v16 ^ (v16 ^ v15) & 0x80 ^ (v15 ^ v16 ^ (v16 ^ v15) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v19;
    }
    v20 = v16 & 4;
    if ( (v16 & 4) != 0 )
    {
      v21 = v19;
    }
    else
    {
      v21 = v19 ^ (v19 ^ v15) & 0x400 | 4;
      *(_DWORD *)a2 = v21;
    }
    v16 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_PreventLaunchingTabTipInMultiSession__descriptor,
            v21,
            v16);
  }
  while ( v18 != v16 );
  if ( !v20 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_PreventLaunchingTabTipInMultiSession__descriptor,
      1,
      v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v15
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v15
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v15
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v15
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v15
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v15
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v15
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v15
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v15
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v15
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v15
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v15
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v15
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v15
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v15
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
0x1800208ac  mov     [rsp+arg_8], rbx
0x1800208b1  mov     [rsp+arg_10], rbp
0x1800208b6  mov     [rsp+arg_0], rcx
0x1800208bb  push    rsi
0x1800208bc  push    rdi
0x1800208bd  push    r15
0x1800208bf  sub     rsp, 20h
0x1800208c3  mov     rsi, cs:Feature_PreventLaunchingTabTipInMultiSession__descriptor
0x1800208ca  mov     rdi, rdx
0x1800208cd  mov     qword ptr [rdx], 0
0x1800208d4  mov     eax, [rsi]
0x1800208d6  mov     [rdx], eax
0x1800208d8  and     eax, 6
0x1800208db  cmp     al, 6
0x1800208dd  jz      loc_180020A39
0x1800208e3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800208e8  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800208ed  mov     dword ptr [rsp+38h+arg_0], 0
0x1800208f5  mov     edx, 1; unsigned int
0x1800208fa  mov     ecx, 2CFF0EBh; this
0x1800208ff  mov     ebp, eax
0x180020901  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180020906  mov     r8d, eax
0x180020909  mov     ecx, eax
0x18002090b  and     r8d, 0FFFFFF3Fh
0x180020912  and     eax, 80h
0x180020917  mov     edx, r8d
0x18002091a  mov     r15d, 40h ; '@'
0x180020920  and     edx, 3
0x180020923  and     ecx, r15d
0x180020926  shl     edx, 2
0x180020929  or      edx, ecx
0x18002092b  shl     edx, 2
0x18002092e  or      edx, eax
0x180020930  lea     ebx, ds:0[rdx*8]
0x180020937  test    r8d, r8d
0x18002093a  jnz     short loc_180020941
0x18002093c  mov     eax, r15d
0x18002093f  jmp     short loc_18002094B
0x180020941  xor     eax, eax
0x180020943  cmp     r8d, 2
0x180020947  cmovz   eax, r15d
0x18002094b  or      ebx, eax
0x18002094d  mov     r10d, 400h
0x180020953  test    r10d, ebx
0x180020956  jz      short loc_180020969
0x180020958  cmp     ebx, 800h
0x18002095e  jb      short loc_180020969
0x180020960  mov     eax, ebx
0x180020962  mov     cl, 1
0x180020964  and     eax, r15d
0x180020967  jmp     short loc_180020972
0x180020969  mov     eax, ebx
0x18002096b  and     eax, r15d
0x18002096e  jnz     short loc_18002097E
0x180020970  xor     cl, cl
0x180020972  test    eax, eax
0x180020974  jz      short loc_18002097A
0x180020976  test    cl, cl
0x180020978  jnz     short loc_18002097E
0x18002097a  xor     eax, eax
0x18002097c  jmp     short loc_180020983
0x18002097e  mov     eax, 1
0x180020983  or      ebx, eax
0x180020985  mov     eax, [rdi]
0x180020987  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002098c  mov     edx, eax
0x18002098e  mov     [rdi], eax
0x180020990  jz      short loc_1800209CD
0x180020992  test    dl, 2
0x180020995  jnz     short loc_1800209CD
0x180020997  mov     eax, ebx
0x180020999  xor     eax, edx
0x18002099b  and     eax, 180h
0x1800209a0  xor     eax, edx
0x1800209a2  mov     ecx, eax
0x1800209a4  xor     ecx, ebx
0x1800209a6  and     ecx, r15d
0x1800209a9  xor     ecx, eax
0x1800209ab  mov     eax, ecx
0x1800209ad  xor     eax, ebx
0x1800209af  and     eax, 1
0x1800209b2  xor     eax, ecx
0x1800209b4  mov     r8d, eax
0x1800209b7  xor     r8d, ebx
0x1800209ba  and     r8d, 800h
0x1800209c1  xor     r8d, eax
0x1800209c4  or      r8d, 2
0x1800209c8  mov     [rdi], r8d
0x1800209cb  jmp     short loc_1800209D0
0x1800209cd  mov     r8d, edx
0x1800209d0  mov     r9d, edx
0x1800209d3  and     r9d, 4
0x1800209d7  jnz     short loc_1800209EB
0x1800209d9  mov     ecx, ebx
0x1800209db  xor     ecx, r8d
0x1800209de  and     ecx, r10d
0x1800209e1  xor     ecx, r8d
0x1800209e4  or      ecx, 4
0x1800209e7  mov     [rdi], ecx
0x1800209e9  jmp     short loc_1800209EE
0x1800209eb  mov     ecx, r8d
0x1800209ee  mov     eax, edx
0x1800209f0  lock cmpxchg [rsi], ecx
0x1800209f4  jnz     short loc_180020987
0x1800209f6  test    r9d, r9d
0x1800209f9  jnz     short loc_180020A0A
0x1800209fb  mov     r8d, ebp
0x1800209fe  lea     edx, [r9+1]
0x180020a02  mov     rcx, rsi
0x180020a05  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180020a0a  test    byte ptr [rdi], 2
0x180020a0d  jnz     short loc_180020A39
0x180020a0f  mov     eax, [rdi]
0x180020a11  xor     eax, ebx
0x180020a13  and     eax, 180h
0x180020a18  xor     eax, [rdi]
0x180020a1a  mov     ecx, eax
0x180020a1c  xor     ecx, ebx
0x180020a1e  and     ecx, r15d
0x180020a21  xor     ecx, eax
0x180020a23  mov     edx, ecx
0x180020a25  xor     edx, ebx
0x180020a27  and     edx, 1
0x180020a2a  xor     edx, ecx
0x180020a2c  mov     eax, edx
0x180020a2e  xor     eax, ebx
0x180020a30  and     eax, 800h
0x180020a35  xor     eax, edx
0x180020a37  mov     [rdi], eax
0x180020a39  mov     rbx, [rsp+38h+arg_8]
0x180020a3e  mov     rax, rdi
0x180020a41  mov     rbp, [rsp+38h+arg_10]
0x180020a46  add     rsp, 20h
0x180020a4a  pop     r15
0x180020a4c  pop     rdi
0x180020a4d  pop     rsi
0x180020a4e  retn
```
