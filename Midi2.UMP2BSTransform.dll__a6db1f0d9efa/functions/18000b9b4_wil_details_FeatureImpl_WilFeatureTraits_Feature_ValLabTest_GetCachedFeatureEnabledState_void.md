# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b9b4`
- end: `0x18000bb2b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f4`

## callees

- `0x18000ab78`
- `0x18000b9b4`
- `0x18000d258`
- `0x18000f010`

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
0x18000b9b4  mov     [rsp+arg_8], rbx
0x18000b9b9  mov     [rsp+arg_10], rbp
0x18000b9be  mov     [rsp+arg_0], rcx
0x18000b9c3  push    rsi
0x18000b9c4  push    rdi
0x18000b9c5  push    r15
0x18000b9c7  sub     rsp, 20h
0x18000b9cb  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000b9d2  mov     rbx, rdx
0x18000b9d5  mov     qword ptr [rdx], 0
0x18000b9dc  mov     eax, [rsi]
0x18000b9de  mov     [rdx], eax
0x18000b9e0  and     eax, 6
0x18000b9e3  cmp     al, 6
0x18000b9e5  jz      loc_18000BB15
0x18000b9eb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b9f0  mov     ebp, eax
0x18000b9f2  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b9fa  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ba01  test    rax, rax
0x18000ba04  jz      short loc_18000BA1E
0x18000ba06  lea     r8, [rsp+38h+arg_0]
0x18000ba0b  mov     edx, 3
0x18000ba10  mov     ecx, 3667CA2h
0x18000ba15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba1a  mov     edx, eax
0x18000ba1c  jmp     short loc_18000BA2C
0x18000ba1e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ba25  test    rax, rax
0x18000ba28  jnz     short loc_18000BA06
0x18000ba2a  xor     edx, edx
0x18000ba2c  mov     r8d, edx
0x18000ba2f  mov     eax, edx
0x18000ba31  and     r8d, 0FFFFFF3Fh
0x18000ba38  and     edx, 80h
0x18000ba3e  mov     ecx, r8d
0x18000ba41  mov     r15d, 40h ; '@'
0x18000ba47  and     ecx, 3
0x18000ba4a  and     eax, r15d
0x18000ba4d  shl     ecx, 2
0x18000ba50  or      ecx, eax
0x18000ba52  shl     ecx, 2
0x18000ba55  or      ecx, edx
0x18000ba57  lea     edi, ds:0[rcx*8]
0x18000ba5e  test    r8d, r8d
0x18000ba61  jnz     short loc_18000BA68
0x18000ba63  mov     eax, r15d
0x18000ba66  jmp     short loc_18000BA72
0x18000ba68  xor     eax, eax
0x18000ba6a  cmp     r8d, 2
0x18000ba6e  cmovz   eax, r15d
0x18000ba72  or      edi, eax
0x18000ba74  mov     eax, [rbx]
0x18000ba76  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ba7b  mov     edx, eax
0x18000ba7d  mov     [rbx], eax
0x18000ba7f  jz      short loc_18000BAAF
0x18000ba81  test    dl, 2
0x18000ba84  jnz     short loc_18000BAAF
0x18000ba86  mov     eax, edi
0x18000ba88  xor     eax, edx
0x18000ba8a  and     eax, 180h
0x18000ba8f  xor     eax, edx
0x18000ba91  mov     ecx, eax
0x18000ba93  xor     ecx, edi
0x18000ba95  and     ecx, r15d
0x18000ba98  xor     ecx, eax
0x18000ba9a  or      ecx, 1
0x18000ba9d  mov     eax, ecx
0x18000ba9f  xor     eax, edi
0x18000baa1  and     eax, 800h
0x18000baa6  xor     eax, ecx
0x18000baa8  or      eax, 2
0x18000baab  mov     [rbx], eax
0x18000baad  jmp     short loc_18000BAB1
0x18000baaf  mov     eax, edx
0x18000bab1  mov     r8d, edx
0x18000bab4  and     r8d, 4
0x18000bab8  jnz     short loc_18000BACD
0x18000baba  mov     ecx, edi
0x18000babc  xor     ecx, eax
0x18000babe  and     ecx, 400h
0x18000bac4  xor     ecx, eax
0x18000bac6  or      ecx, 4
0x18000bac9  mov     [rbx], ecx
0x18000bacb  jmp     short loc_18000BACF
0x18000bacd  mov     ecx, eax
0x18000bacf  mov     eax, edx
0x18000bad1  lock cmpxchg [rsi], ecx
0x18000bad5  jnz     short loc_18000BA76
0x18000bad7  test    r8d, r8d
0x18000bada  jnz     short loc_18000BAEC
0x18000badc  mov     r8d, ebp
0x18000badf  mov     edx, 3
0x18000bae4  mov     rcx, rsi
0x18000bae7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000baec  test    byte ptr [rbx], 2
0x18000baef  jnz     short loc_18000BB15
0x18000baf1  mov     eax, [rbx]
0x18000baf3  xor     eax, edi
0x18000baf5  and     eax, 180h
0x18000bafa  xor     eax, [rbx]
0x18000bafc  mov     ecx, eax
0x18000bafe  xor     ecx, edi
0x18000bb00  and     ecx, r15d
0x18000bb03  xor     ecx, eax
0x18000bb05  or      ecx, 1
0x18000bb08  mov     eax, ecx
0x18000bb0a  xor     eax, edi
0x18000bb0c  and     eax, 800h
0x18000bb11  xor     eax, ecx
0x18000bb13  mov     [rbx], eax
0x18000bb15  mov     rbp, [rsp+38h+arg_10]
0x18000bb1a  mov     rax, rbx
0x18000bb1d  mov     rbx, [rsp+38h+arg_8]
0x18000bb22  add     rsp, 20h
0x18000bb26  pop     r15
0x18000bb28  pop     rdi
0x18000bb29  pop     rsi
0x18000bb2a  retn
```
