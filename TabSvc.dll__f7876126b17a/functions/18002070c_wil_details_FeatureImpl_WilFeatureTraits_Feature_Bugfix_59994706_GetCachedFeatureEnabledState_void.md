# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::GetCachedFeatureEnabledState(void)

- ea: `0x18002070c`
- end: `0x1800208a4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `408`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025350`
- `0x180028a24`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x18002070c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Bugfix_59994706__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Bugfix_59994706__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v22) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x3937252,
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
    v15 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Bugfix_59994706__descriptor, v20, v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Bugfix_59994706__descriptor, 3, v5);
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
0x18002070c  mov     [rsp+arg_8], rbx
0x180020711  mov     [rsp+arg_10], rbp
0x180020716  mov     [rsp+arg_0], rcx
0x18002071b  push    rsi
0x18002071c  push    rdi
0x18002071d  push    r15
0x18002071f  sub     rsp, 20h
0x180020723  mov     rsi, cs:Feature_Bugfix_59994706__descriptor
0x18002072a  mov     rbx, rdx
0x18002072d  mov     qword ptr [rdx], 0
0x180020734  mov     eax, [rsi]
0x180020736  mov     [rdx], eax
0x180020738  and     eax, 6
0x18002073b  cmp     al, 6
0x18002073d  jz      loc_18002088E
0x180020743  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180020748  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18002074d  mov     dword ptr [rsp+38h+arg_0], 0
0x180020755  mov     edx, 3; unsigned int
0x18002075a  mov     ecx, 3937252h; this
0x18002075f  mov     ebp, eax
0x180020761  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180020766  mov     r8d, eax
0x180020769  mov     ecx, eax
0x18002076b  and     eax, 80h
0x180020770  and     r8d, 0FFFFFF3Fh
0x180020777  mov     edx, r8d
0x18002077a  mov     r15d, 40h ; '@'
0x180020780  and     edx, 3
0x180020783  and     ecx, r15d
0x180020786  shl     edx, 2
0x180020789  or      edx, ecx
0x18002078b  shl     edx, 2
0x18002078e  or      edx, eax
0x180020790  xor     eax, eax
0x180020792  lea     edi, ds:0[rdx*8]
0x180020799  test    r8d, r8d
0x18002079c  jz      short loc_1800207A6
0x18002079e  cmp     r8d, 2
0x1800207a2  cmovz   eax, r15d
0x1800207a6  or      edi, eax
0x1800207a8  mov     edx, 0C00h
0x1800207ad  mov     ecx, edi
0x1800207af  mov     eax, edi
0x1800207b1  and     ecx, r15d
0x1800207b4  and     eax, edx
0x1800207b6  cmp     eax, edx
0x1800207b8  jnz     short loc_1800207BE
0x1800207ba  mov     al, 1
0x1800207bc  jmp     short loc_1800207C4
0x1800207be  test    ecx, ecx
0x1800207c0  jnz     short loc_1800207D0
0x1800207c2  xor     al, al
0x1800207c4  test    ecx, ecx
0x1800207c6  jz      short loc_1800207CC
0x1800207c8  test    al, al
0x1800207ca  jnz     short loc_1800207D0
0x1800207cc  xor     eax, eax
0x1800207ce  jmp     short loc_1800207D5
0x1800207d0  mov     eax, 1
0x1800207d5  or      edi, eax
0x1800207d7  mov     eax, [rbx]
0x1800207d9  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800207de  mov     edx, eax
0x1800207e0  mov     [rbx], eax
0x1800207e2  jz      short loc_18002081F
0x1800207e4  test    dl, 2
0x1800207e7  jnz     short loc_18002081F
0x1800207e9  mov     eax, edi
0x1800207eb  xor     eax, edx
0x1800207ed  and     eax, 180h
0x1800207f2  xor     eax, edx
0x1800207f4  mov     ecx, eax
0x1800207f6  xor     ecx, edi
0x1800207f8  and     ecx, r15d
0x1800207fb  xor     ecx, eax
0x1800207fd  mov     eax, ecx
0x1800207ff  xor     eax, edi
0x180020801  and     eax, 1
0x180020804  xor     eax, ecx
0x180020806  mov     r8d, eax
0x180020809  xor     r8d, edi
0x18002080c  and     r8d, 800h
0x180020813  xor     r8d, eax
0x180020816  or      r8d, 2
0x18002081a  mov     [rbx], r8d
0x18002081d  jmp     short loc_180020822
0x18002081f  mov     r8d, edx
0x180020822  mov     r9d, edx
0x180020825  and     r9d, 4
0x180020829  jnz     short loc_180020840
0x18002082b  mov     ecx, edi
0x18002082d  xor     ecx, r8d
0x180020830  and     ecx, 400h
0x180020836  xor     ecx, r8d
0x180020839  or      ecx, 4
0x18002083c  mov     [rbx], ecx
0x18002083e  jmp     short loc_180020843
0x180020840  mov     ecx, r8d
0x180020843  mov     eax, edx
0x180020845  lock cmpxchg [rsi], ecx
0x180020849  jnz     short loc_1800207D9
0x18002084b  test    r9d, r9d
0x18002084e  jnz     short loc_18002085F
0x180020850  mov     r8d, ebp
0x180020853  lea     edx, [r9+3]
0x180020857  mov     rcx, rsi
0x18002085a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002085f  test    byte ptr [rbx], 2
0x180020862  jnz     short loc_18002088E
0x180020864  mov     eax, [rbx]
0x180020866  xor     eax, edi
0x180020868  and     eax, 180h
0x18002086d  xor     eax, [rbx]
0x18002086f  mov     ecx, eax
0x180020871  xor     ecx, edi
0x180020873  and     ecx, r15d
0x180020876  xor     ecx, eax
0x180020878  mov     edx, ecx
0x18002087a  xor     edx, edi
0x18002087c  and     edx, 1
0x18002087f  xor     edx, ecx
0x180020881  mov     eax, edx
0x180020883  xor     eax, edi
0x180020885  and     eax, 800h
0x18002088a  xor     eax, edx
0x18002088c  mov     [rbx], eax
0x18002088e  mov     rbp, [rsp+38h+arg_10]
0x180020893  mov     rax, rbx
0x180020896  mov     rbx, [rsp+38h+arg_8]
0x18002089b  add     rsp, 20h
0x18002089f  pop     r15
0x1800208a1  pop     rdi
0x1800208a2  pop     rsi
0x1800208a3  retn
```
