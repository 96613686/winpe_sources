# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180015778`
- end: `0x1800158cb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `339`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001606c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000cfc0`
- `0x180015778`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667CA2,
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
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v13 ^ v12) & 0x180 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x180) & 0x40) | 1))
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
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v5);
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
0x180015778  mov     [rsp+arg_8], rbx
0x18001577d  mov     [rsp+arg_10], rbp
0x180015782  mov     [rsp+arg_0], rcx
0x180015787  push    rsi
0x180015788  push    rdi
0x180015789  push    r15
0x18001578b  sub     rsp, 20h
0x18001578f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180015796  mov     rbx, rdx
0x180015799  mov     qword ptr [rdx], 0
0x1800157a0  mov     eax, [rsi]
0x1800157a2  mov     [rdx], eax
0x1800157a4  and     eax, 6
0x1800157a7  cmp     al, 6
0x1800157a9  jz      loc_1800158B5
0x1800157af  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800157b4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800157b9  mov     dword ptr [rsp+38h+arg_0], 0
0x1800157c1  mov     ecx, 3667CA2h; this
0x1800157c6  mov     ebp, eax
0x1800157c8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800157cd  mov     r8d, eax
0x1800157d0  mov     ecx, eax
0x1800157d2  and     r8d, 0FFFFFF3Fh
0x1800157d9  and     eax, 80h
0x1800157de  mov     edx, r8d
0x1800157e1  mov     r15d, 40h ; '@'
0x1800157e7  and     edx, 3
0x1800157ea  and     ecx, r15d
0x1800157ed  shl     edx, 2
0x1800157f0  or      edx, ecx
0x1800157f2  shl     edx, 2
0x1800157f5  or      edx, eax
0x1800157f7  lea     edi, ds:0[rdx*8]
0x1800157fe  test    r8d, r8d
0x180015801  jnz     short loc_180015808
0x180015803  mov     eax, r15d
0x180015806  jmp     short loc_180015812
0x180015808  xor     eax, eax
0x18001580a  cmp     r8d, 2
0x18001580e  cmovz   eax, r15d
0x180015812  or      edi, eax
0x180015814  mov     eax, [rbx]
0x180015816  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001581b  mov     edx, eax
0x18001581d  mov     [rbx], eax
0x18001581f  jz      short loc_18001584F
0x180015821  test    dl, 2
0x180015824  jnz     short loc_18001584F
0x180015826  mov     eax, edi
0x180015828  xor     eax, edx
0x18001582a  and     eax, 180h
0x18001582f  xor     eax, edx
0x180015831  mov     ecx, eax
0x180015833  xor     ecx, edi
0x180015835  and     ecx, r15d
0x180015838  xor     ecx, eax
0x18001583a  or      ecx, 1
0x18001583d  mov     eax, ecx
0x18001583f  xor     eax, edi
0x180015841  and     eax, 800h
0x180015846  xor     eax, ecx
0x180015848  or      eax, 2
0x18001584b  mov     [rbx], eax
0x18001584d  jmp     short loc_180015851
0x18001584f  mov     eax, edx
0x180015851  mov     r8d, edx
0x180015854  and     r8d, 4
0x180015858  jnz     short loc_18001586D
0x18001585a  mov     ecx, edi
0x18001585c  xor     ecx, eax
0x18001585e  and     ecx, 400h
0x180015864  xor     ecx, eax
0x180015866  or      ecx, 4
0x180015869  mov     [rbx], ecx
0x18001586b  jmp     short loc_18001586F
0x18001586d  mov     ecx, eax
0x18001586f  mov     eax, edx
0x180015871  lock cmpxchg [rsi], ecx
0x180015875  jnz     short loc_180015816
0x180015877  test    r8d, r8d
0x18001587a  jnz     short loc_18001588C
0x18001587c  mov     r8d, ebp
0x18001587f  mov     edx, 3
0x180015884  mov     rcx, rsi
0x180015887  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001588c  test    byte ptr [rbx], 2
0x18001588f  jnz     short loc_1800158B5
0x180015891  mov     eax, [rbx]
0x180015893  xor     eax, edi
0x180015895  and     eax, 180h
0x18001589a  xor     eax, [rbx]
0x18001589c  mov     ecx, eax
0x18001589e  xor     ecx, edi
0x1800158a0  and     ecx, r15d
0x1800158a3  xor     ecx, eax
0x1800158a5  or      ecx, 1
0x1800158a8  mov     eax, ecx
0x1800158aa  xor     eax, edi
0x1800158ac  and     eax, 800h
0x1800158b1  xor     eax, ecx
0x1800158b3  mov     [rbx], eax
0x1800158b5  mov     rbp, [rsp+38h+arg_10]
0x1800158ba  mov     rax, rbx
0x1800158bd  mov     rbx, [rsp+38h+arg_8]
0x1800158c2  add     rsp, 20h
0x1800158c6  pop     r15
0x1800158c8  pop     rdi
0x1800158c9  pop     rsi
0x1800158ca  retn
```
