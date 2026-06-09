# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56976978>::GetCachedFeatureEnabledState(void)

- ea: `0x1400076a4`
- end: `0x140007834`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_56976978@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400056f4`
- `0x14000783c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400076a4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_56976978>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // ebx
  signed __int32 v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  int v17; // ecx
  int v19; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v19 = 0;
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(56976978, 0, &v19);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      v11 = v9 | v10;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = v9;
LABEL_10:
  v12 = v11 | (v11 >> 6) & 1;
  if ( !v5 )
    v19 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v19 == 0;
    v15 = v13;
    *(_DWORD *)a2 = v13;
    v16 = v13;
    if ( !v14 && (v13 & 2) == 0 )
    {
      v17 = v13
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)v12)
          & 0x180
          ^ (v12
           ^ v13
           ^ ((unsigned __int16)v13
            ^ (unsigned __int16)v12)
           & 0x180)
          & 0x40;
      v16 = v17
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v17)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v17 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v17) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    if ( (v13 & 4) == 0 )
    {
      v16 = ((unsigned __int16)v16 ^ (unsigned __int16)v12) & 0x400 ^ v16 | 4;
      *(_DWORD *)a2 = v16;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v16, v13);
  }
  while ( v15 != v13 );
  if ( (v15 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 0, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (*(_DWORD *)a2
                    ^ v12)
                   & 0x180
                   ^ (v12
                    ^ *(_DWORD *)a2
                    ^ (*(_DWORD *)a2
                     ^ v12)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v12
                    ^ *(_BYTE *)a2
                    ^ (*(_BYTE *)a2
                     ^ (unsigned __int8)v12)
                    & 0x80
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v12
                    ^ *(_WORD *)a2
                    ^ (*(_WORD *)a2
                     ^ (unsigned __int16)v12)
                    & 0x180
                    ^ ((unsigned __int16)v12
                     ^ *(_WORD *)a2
                     ^ (*(_WORD *)a2
                      ^ (unsigned __int16)v12)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v12
                     ^ *(_BYTE *)a2
                     ^ (*(_BYTE *)a2
                      ^ (unsigned __int8)v12)
                     & 0x80
                     ^ ((unsigned __int8)v12
                      ^ *(_BYTE *)a2
                      ^ (*(_BYTE *)a2
                       ^ (unsigned __int8)v12)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x1400076a4  mov     [rsp+arg_10], rbx
0x1400076a9  mov     [rsp+arg_18], rbp
0x1400076ae  push    rsi
0x1400076af  push    rdi
0x1400076b0  push    r15
0x1400076b2  sub     rsp, 30h
0x1400076b6  mov     rax, cs:__security_cookie
0x1400076bd  xor     rax, rsp
0x1400076c0  mov     [rsp+48h+var_20], rax
0x1400076c5  mov     qword ptr [rdx], 0
0x1400076cc  mov     rdi, rdx
0x1400076cf  mov     eax, [rcx]
0x1400076d1  mov     rsi, rcx
0x1400076d4  mov     [rdx], eax
0x1400076d6  and     eax, 6
0x1400076d9  cmp     al, 6
0x1400076db  jz      loc_140007811
0x1400076e1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400076e6  mov     ebp, eax
0x1400076e8  mov     [rsp+48h+var_28], 0
0x1400076f0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400076f7  mov     r15d, 40h ; '@'
0x1400076fd  test    rax, rax
0x140007700  jnz     short loc_14000770E
0x140007702  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140007709  test    rax, rax
0x14000770c  jz      short loc_14000775A
0x14000770e  lea     r8, [rsp+48h+var_28]
0x140007713  xor     edx, edx
0x140007715  mov     ecx, 3656652h
0x14000771a  call    _guard_dispatch_icall
0x14000771f  mov     r8d, eax
0x140007722  mov     edx, eax
0x140007724  and     r8d, 0FFFFFF3Fh
0x14000772b  and     eax, r15d
0x14000772e  and     edx, 80h
0x140007734  mov     ecx, r8d
0x140007737  and     ecx, 3
0x14000773a  shl     ecx, 2
0x14000773d  or      ecx, eax
0x14000773f  shl     ecx, 2
0x140007742  or      ecx, edx
0x140007744  shl     ecx, 3
0x140007747  test    r8d, r8d
0x14000774a  jz      short loc_14000775C
0x14000774c  xor     eax, eax
0x14000774e  cmp     r8d, 2
0x140007752  cmovz   eax, r15d
0x140007756  or      eax, ecx
0x140007758  jmp     short loc_14000775E
0x14000775a  xor     ecx, ecx
0x14000775c  mov     eax, ecx
0x14000775e  mov     ebx, eax
0x140007760  shr     ebx, 6
0x140007763  and     ebx, 1
0x140007766  or      ebx, eax
0x140007768  test    ebp, ebp
0x14000776a  jnz     short loc_140007770
0x14000776c  mov     [rsp+48h+var_28], ebp
0x140007770  mov     eax, [rdi]
0x140007772  cmp     [rsp+48h+var_28], 0
0x140007777  mov     edx, eax
0x140007779  mov     [rdi], eax
0x14000777b  mov     ecx, eax
0x14000777d  jz      short loc_1400077B2
0x14000777f  test    dl, 2
0x140007782  jnz     short loc_1400077B2
0x140007784  mov     eax, ebx
0x140007786  xor     eax, ecx
0x140007788  and     eax, 180h
0x14000778d  xor     eax, ecx
0x14000778f  mov     ecx, eax
0x140007791  xor     ecx, ebx
0x140007793  and     ecx, r15d
0x140007796  xor     ecx, eax
0x140007798  mov     eax, ecx
0x14000779a  xor     eax, ebx
0x14000779c  and     eax, 1
0x14000779f  xor     eax, ecx
0x1400077a1  mov     ecx, eax
0x1400077a3  xor     ecx, ebx
0x1400077a5  and     ecx, 800h
0x1400077ab  xor     ecx, eax
0x1400077ad  or      ecx, 2
0x1400077b0  mov     [rdi], ecx
0x1400077b2  test    dl, 4
0x1400077b5  jnz     short loc_1400077C7
0x1400077b7  mov     eax, ebx
0x1400077b9  xor     eax, ecx
0x1400077bb  and     eax, 400h
0x1400077c0  xor     ecx, eax
0x1400077c2  or      ecx, 4
0x1400077c5  mov     [rdi], ecx
0x1400077c7  mov     eax, edx
0x1400077c9  lock cmpxchg [rsi], ecx
0x1400077cd  jnz     short loc_140007772
0x1400077cf  test    dl, 4
0x1400077d2  jnz     short loc_1400077E1
0x1400077d4  mov     r8d, ebp
0x1400077d7  xor     edx, edx
0x1400077d9  mov     rcx, rsi
0x1400077dc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400077e1  test    byte ptr [rdi], 2
0x1400077e4  jnz     short loc_140007811
0x1400077e6  mov     eax, ebx
0x1400077e8  xor     eax, [rdi]
0x1400077ea  and     eax, 180h
0x1400077ef  xor     eax, [rdi]
0x1400077f1  mov     ecx, eax
0x1400077f3  xor     ecx, ebx
0x1400077f5  and     ecx, r15d
0x1400077f8  xor     ecx, eax
0x1400077fa  mov     edx, ecx
0x1400077fc  xor     edx, ebx
0x1400077fe  and     edx, 1
0x140007801  xor     edx, ecx
0x140007803  mov     ecx, edx
0x140007805  xor     ecx, ebx
0x140007807  and     ecx, 800h
0x14000780d  xor     ecx, edx
0x14000780f  mov     [rdi], ecx
0x140007811  mov     rax, rdi
0x140007814  mov     rcx, [rsp+48h+var_20]
0x140007819  xor     rcx, rsp; StackCookie
0x14000781c  call    __security_check_cookie
0x140007821  mov     rbx, [rsp+48h+arg_10]
0x140007826  mov     rbp, [rsp+48h+arg_18]
0x14000782b  add     rsp, 30h
0x14000782f  pop     r15
0x140007831  pop     rdi
0x140007832  pop     rsi
0x140007833  retn
```
