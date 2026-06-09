# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_54845374>::GetCachedFeatureEnabledState(void)

- ea: `0x1400085f4`
- end: `0x140008784`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UCPD_54845374@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005898`
- `0x14000878c`

## callees

- `0x140004168`
- `0x14000422c`
- `0x1400085f4`
- `0x14000a390`
- `0x14000f4d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UCPD_54845374>::GetCachedFeatureEnabledState(
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
    v7 = v6(54845374, 0, &v19);
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
0x1400085f4  mov     [rsp+arg_10], rbx
0x1400085f9  mov     [rsp+arg_18], rbp
0x1400085fe  push    rsi
0x1400085ff  push    rdi
0x140008600  push    r15
0x140008602  sub     rsp, 30h
0x140008606  mov     rax, cs:__security_cookie
0x14000860d  xor     rax, rsp
0x140008610  mov     [rsp+48h+var_20], rax
0x140008615  mov     qword ptr [rdx], 0
0x14000861c  mov     rdi, rdx
0x14000861f  mov     eax, [rcx]
0x140008621  mov     rsi, rcx
0x140008624  mov     [rdx], eax
0x140008626  and     eax, 6
0x140008629  cmp     al, 6
0x14000862b  jz      loc_140008761
0x140008631  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140008636  mov     ebp, eax
0x140008638  mov     [rsp+48h+var_28], 0
0x140008640  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140008647  mov     r15d, 40h ; '@'
0x14000864d  test    rax, rax
0x140008650  jnz     short loc_14000865E
0x140008652  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140008659  test    rax, rax
0x14000865c  jz      short loc_1400086AA
0x14000865e  lea     r8, [rsp+48h+var_28]
0x140008663  xor     edx, edx
0x140008665  mov     ecx, 344DFBEh
0x14000866a  call    _guard_dispatch_icall
0x14000866f  mov     r8d, eax
0x140008672  mov     edx, eax
0x140008674  and     r8d, 0FFFFFF3Fh
0x14000867b  and     eax, r15d
0x14000867e  and     edx, 80h
0x140008684  mov     ecx, r8d
0x140008687  and     ecx, 3
0x14000868a  shl     ecx, 2
0x14000868d  or      ecx, eax
0x14000868f  shl     ecx, 2
0x140008692  or      ecx, edx
0x140008694  shl     ecx, 3
0x140008697  test    r8d, r8d
0x14000869a  jz      short loc_1400086AC
0x14000869c  xor     eax, eax
0x14000869e  cmp     r8d, 2
0x1400086a2  cmovz   eax, r15d
0x1400086a6  or      eax, ecx
0x1400086a8  jmp     short loc_1400086AE
0x1400086aa  xor     ecx, ecx
0x1400086ac  mov     eax, ecx
0x1400086ae  mov     ebx, eax
0x1400086b0  shr     ebx, 6
0x1400086b3  and     ebx, 1
0x1400086b6  or      ebx, eax
0x1400086b8  test    ebp, ebp
0x1400086ba  jnz     short loc_1400086C0
0x1400086bc  mov     [rsp+48h+var_28], ebp
0x1400086c0  mov     eax, [rdi]
0x1400086c2  cmp     [rsp+48h+var_28], 0
0x1400086c7  mov     edx, eax
0x1400086c9  mov     [rdi], eax
0x1400086cb  mov     ecx, eax
0x1400086cd  jz      short loc_140008702
0x1400086cf  test    dl, 2
0x1400086d2  jnz     short loc_140008702
0x1400086d4  mov     eax, ebx
0x1400086d6  xor     eax, ecx
0x1400086d8  and     eax, 180h
0x1400086dd  xor     eax, ecx
0x1400086df  mov     ecx, eax
0x1400086e1  xor     ecx, ebx
0x1400086e3  and     ecx, r15d
0x1400086e6  xor     ecx, eax
0x1400086e8  mov     eax, ecx
0x1400086ea  xor     eax, ebx
0x1400086ec  and     eax, 1
0x1400086ef  xor     eax, ecx
0x1400086f1  mov     ecx, eax
0x1400086f3  xor     ecx, ebx
0x1400086f5  and     ecx, 800h
0x1400086fb  xor     ecx, eax
0x1400086fd  or      ecx, 2
0x140008700  mov     [rdi], ecx
0x140008702  test    dl, 4
0x140008705  jnz     short loc_140008717
0x140008707  mov     eax, ebx
0x140008709  xor     eax, ecx
0x14000870b  and     eax, 400h
0x140008710  xor     ecx, eax
0x140008712  or      ecx, 4
0x140008715  mov     [rdi], ecx
0x140008717  mov     eax, edx
0x140008719  lock cmpxchg [rsi], ecx
0x14000871d  jnz     short loc_1400086C2
0x14000871f  test    dl, 4
0x140008722  jnz     short loc_140008731
0x140008724  mov     r8d, ebp
0x140008727  xor     edx, edx
0x140008729  mov     rcx, rsi
0x14000872c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140008731  test    byte ptr [rdi], 2
0x140008734  jnz     short loc_140008761
0x140008736  mov     eax, ebx
0x140008738  xor     eax, [rdi]
0x14000873a  and     eax, 180h
0x14000873f  xor     eax, [rdi]
0x140008741  mov     ecx, eax
0x140008743  xor     ecx, ebx
0x140008745  and     ecx, r15d
0x140008748  xor     ecx, eax
0x14000874a  mov     edx, ecx
0x14000874c  xor     edx, ebx
0x14000874e  and     edx, 1
0x140008751  xor     edx, ecx
0x140008753  mov     ecx, edx
0x140008755  xor     ecx, ebx
0x140008757  and     ecx, 800h
0x14000875d  xor     ecx, edx
0x14000875f  mov     [rdi], ecx
0x140008761  mov     rax, rdi
0x140008764  mov     rcx, [rsp+48h+var_20]
0x140008769  xor     rcx, rsp; StackCookie
0x14000876c  call    __security_check_cookie
0x140008771  mov     rbx, [rsp+48h+arg_10]
0x140008776  mov     rbp, [rsp+48h+arg_18]
0x14000877b  add     rsp, 30h
0x14000877f  pop     r15
0x140008781  pop     rdi
0x140008782  pop     rsi
0x140008783  retn
```
