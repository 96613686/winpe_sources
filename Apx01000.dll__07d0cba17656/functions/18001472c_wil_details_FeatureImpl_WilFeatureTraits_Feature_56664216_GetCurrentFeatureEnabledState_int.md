# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001472c`
- end: `0x180014834`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `264`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013040`

## callees

- `0x18001472c`
- `0x18001535c`
- `0x1800156ac`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // edx
  char v12; // si
  bool v13; // cl

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(56664216, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( v5 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_21;
  }
  v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55795972>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55795972>::GetImpl'::`2'::impl);
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_21:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001472c  push    rbx
0x18001472e  push    rbp
0x18001472f  push    rsi
0x180014730  push    rdi
0x180014731  sub     rsp, 28h
0x180014735  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001473c  mov     rbx, rdx
0x18001473f  mov     edi, 3
0x180014744  test    rax, rax
0x180014747  jz      short loc_180014759
0x180014749  mov     edx, edi
0x18001474b  mov     ecx, 360A098h
0x180014750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014755  mov     edx, eax
0x180014757  jmp     short loc_180014767
0x180014759  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014760  test    rax, rax
0x180014763  jnz     short loc_180014749
0x180014765  xor     edx, edx
0x180014767  mov     r8d, edx
0x18001476a  mov     qword ptr [rbx], 0
0x180014771  mov     eax, edx
0x180014773  and     r8d, 0FFFFFF3Fh
0x18001477a  and     edx, 80h
0x180014780  mov     ecx, r8d
0x180014783  and     ecx, edi
0x180014785  mov     ebp, 40h ; '@'
0x18001478a  shl     ecx, 2
0x18001478d  and     eax, ebp
0x18001478f  or      ecx, eax
0x180014791  shl     ecx, 2
0x180014794  or      ecx, edx
0x180014796  lea     edx, ds:0[rcx*8]
0x18001479d  test    r8d, r8d
0x1800147a0  jnz     short loc_1800147A9
0x1800147a2  mov     ecx, ebp
0x1800147a4  mov     r8d, ebp
0x1800147a7  jmp     short loc_1800147B5
0x1800147a9  xor     ecx, ecx
0x1800147ab  cmp     r8d, 2
0x1800147af  cmovz   ecx, ebp
0x1800147b2  mov     r8d, ecx
0x1800147b5  mov     eax, edx
0x1800147b7  mov     edi, 1
0x1800147bc  or      eax, r8d
0x1800147bf  or      edx, ecx
0x1800147c1  mov     [rbx], eax
0x1800147c3  bt      edx, 0Ah
0x1800147c7  jnb     short loc_1800147D6
0x1800147c9  cmp     edx, 800h
0x1800147cf  jb      short loc_1800147D6
0x1800147d1  mov     sil, dil
0x1800147d4  jmp     short loc_1800147E0
0x1800147d6  xor     sil, sil
0x1800147d9  xor     cl, cl
0x1800147db  test    bpl, dl
0x1800147de  jz      short loc_180014814
0x1800147e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x1800147e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x1800147ec  test    al, al
0x1800147ee  jz      short loc_180014805
0x1800147f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55795972@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55795972@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55795972> `wil::Feature<__WilFeatureTraits_Feature_55795972>::GetImpl(void)'::`2'::impl
0x1800147f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55795972@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55795972>::__private_IsEnabled(wil::ReportingKind)
0x1800147fc  test    al, al
0x1800147fe  jz      short loc_180014805
0x180014800  mov     cl, dil
0x180014803  jmp     short loc_180014807
0x180014805  xor     cl, cl
0x180014807  test    sil, sil
0x18001480a  jz      short loc_180014814
0x18001480c  test    cl, cl
0x18001480e  jnz     short loc_180014814
0x180014810  btr     dword ptr [rbx], 0Ah
0x180014814  mov     eax, [rbx]
0x180014816  test    bpl, al
0x180014819  jz      short loc_18001481F
0x18001481b  test    cl, cl
0x18001481d  jnz     short loc_180014821
0x18001481f  xor     edi, edi
0x180014821  and     eax, 0FFFFFFFEh
0x180014824  or      eax, edi
0x180014826  mov     [rbx], eax
0x180014828  mov     rax, rbx
0x18001482b  add     rsp, 28h
0x18001482f  pop     rdi
0x180014830  pop     rsi
0x180014831  pop     rbp
0x180014832  pop     rbx
0x180014833  retn
```
