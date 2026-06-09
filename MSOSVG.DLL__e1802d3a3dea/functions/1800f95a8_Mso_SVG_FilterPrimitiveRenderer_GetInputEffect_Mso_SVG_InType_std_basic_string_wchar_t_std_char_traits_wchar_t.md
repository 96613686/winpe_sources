# Mso::SVG::FilterPrimitiveRenderer::GetInputEffect(Mso::SVG::InType,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,GEL::IEffect const &,GEL::IEffect const &,std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Ofc::TCntPtr<GEL::IEffect const>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Ofc::TCntPtr<GEL::IEffect const>>>> const &)

- ea: `0x1800f95a8`
- end: `0x1800f99fb`
- name: `?GetInputEffect@FilterPrimitiveRenderer@SVG@Mso@@KA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@W4InType@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUIEffect@GEL@@2AEBV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@2@@8@@Z`
- size: `1107`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800f9a30`
- `0x1800f9b30`
- `0x1800fb340`

## callees

- `0x180009068`
- `0x1800244f8`
- `0x1800f95a8`
- `0x1800fbe60`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f97aa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f990b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f97aa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f990b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f9904`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f9904`
- `gfx!?Create@IEffectColorReplace@GEL@@SA?AV?$TCntPtr@UIEffectColorReplace@GEL@@@Ofc@@AEBUIEffect@2@AEBUColor@2@@Z` at `0x1800f999a`
- `gfx!?Create@IEffectColorReplace@GEL@@SA?AV?$TCntPtr@UIEffectColorReplace@GEL@@@Ofc@@AEBUIEffect@2@AEBUColor@2@@Z` at `0x1800f999a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Mso::SVG::FilterPrimitiveRenderer::GetInputEffect(
        _QWORD *a1,
        int a2,
        __int64 a3,
        void (__fastcall ***a4)(_QWORD),
        void (__fastcall ***a5)(_QWORD),
        __int64 a6)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  void (__fastcall ***v12)(_QWORD); // rdi
  void (__fastcall ***v13)(_QWORD); // rbx
  char v14; // r14
  __int64 v15; // rsi
  void (__fastcall **v16)(_QWORD); // rax
  _QWORD *v17; // rcx
  void **v18; // r8
  __int64 v19; // r9
  unsigned __int64 j; // rdx
  __int64 v21; // rdi
  void *v22; // rcx
  void (__fastcall ***v23)(_QWORD); // rbx
  void (__fastcall ***v24)(_QWORD); // rcx
  char v25; // si
  _QWORD *v26; // rdi
  bool v27; // zf
  void **v28; // r8
  __int64 v29; // r9
  unsigned __int64 i; // rdx
  __int64 v31; // rdi
  void *v32; // rcx
  void (__fastcall ***v33)(_QWORD); // rcx
  char v34; // si
  _QWORD *v35; // rdi
  __int64 *v36; // rax
  __int64 v37; // rcx
  _QWORD *v39; // [rsp+30h] [rbp-50h] BYREF
  int v40; // [rsp+38h] [rbp-48h]
  __m128i si128; // [rsp+40h] [rbp-40h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v43; // [rsp+60h] [rbp-20h]

  v39 = a1;
  v40 = 0;
  if ( !a2 )
  {
    *a1 = a4;
    if ( a4 )
      (**a4)(a4);
    return a1;
  }
  v7 = a2 - 1;
  if ( !v7 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v36 = (__int64 *)GEL::IEffectColorReplace::Create(&v39, a4, &si128);
    v37 = *v36;
    *v36 = 0;
    *a1 = v37;
    v17 = v39;
    if ( !v39 )
      return a1;
    v16 = (void (__fastcall **)(_QWORD))*v39;
    goto LABEL_25;
  }
  v8 = v7 - 1;
  if ( !v8 || (v9 = v8 - 1) == 0 || (v10 = v9 - 1) == 0 )
  {
    *(_OWORD *)Block = 0;
    v43 = 0;
    std::wstring::_Construct<1,wchar_t *>(Block, L"FillPaint", 9);
    v28 = Block;
    if ( *((_QWORD *)&v43 + 1) > 7u )
      v28 = (void **)Block[0];
    v29 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * (__int64)v43; ++i )
      v29 = 0x100000001B3LL * (*((unsigned __int8 *)v28 + i) ^ (unsigned __int64)v29);
    v31 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,Mso::TCntPtr<Mso::SVG::RenderableContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Mso::TCntPtr<Mso::SVG::RenderableContext>>>,0>>::_Find_last<std::wstring>(
                        a6,
                        &si128,
                        Block,
                        v29)
                    + 8);
    if ( !v31 )
      v31 = *(_QWORD *)(a6 + 8);
    if ( *((_QWORD *)&v43 + 1) > 7u )
    {
      v32 = Block[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v43 + 1) + 2) >= 0x1000 )
      {
        v32 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v32 - 8) > 0x1F )
          goto LABEL_59;
      }
      free(v32);
    }
    if ( v31 == *(_QWORD *)(a6 + 8) )
    {
      v35 = 0;
      v33 = 0;
      v34 = 5;
      v23 = (void (__fastcall ***)(_QWORD))v39;
    }
    else
    {
      v23 = *(void (__fastcall ****)(_QWORD))(v31 + 48);
      if ( v23 )
        (**v23)(*(_QWORD *)(v31 + 48));
      v33 = v23;
      v34 = 3;
      v35 = v39;
    }
    *a1 = v33;
    if ( v33 )
      (**v33)(v33);
    if ( (v34 & 4) != 0 )
    {
      v34 &= ~4u;
      if ( v35 )
        (*(void (__fastcall **)(_QWORD *))(*v35 + 8LL))(v35);
    }
    v27 = (v34 & 2) == 0;
    goto LABEL_47;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    *(_OWORD *)Block = 0;
    v43 = 0;
    std::wstring::_Construct<1,wchar_t *>(Block, L"StrokePaint", 11);
    v18 = Block;
    if ( *((_QWORD *)&v43 + 1) > 7u )
      v18 = (void **)Block[0];
    v19 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 2 * (__int64)v43; ++j )
      v19 = 0x100000001B3LL * (*((unsigned __int8 *)v18 + j) ^ (unsigned __int64)v19);
    v21 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,Mso::TCntPtr<Mso::SVG::RenderableContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Mso::TCntPtr<Mso::SVG::RenderableContext>>>,0>>::_Find_last<std::wstring>(
                        a6,
                        &si128,
                        Block,
                        v19)
                    + 8);
    if ( !v21 )
      v21 = *(_QWORD *)(a6 + 8);
    if ( *((_QWORD *)&v43 + 1) <= 7u )
      goto LABEL_36;
    v22 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v43 + 1) + 2) < 0x1000
      || (v22 = (void *)*((_QWORD *)Block[0] - 1), (unsigned __int64)((char *)Block[0] - (char *)v22 - 8) <= 0x1F) )
    {
      free(v22);
LABEL_36:
      if ( v21 == *(_QWORD *)(a6 + 8) )
      {
        v26 = 0;
        v24 = 0;
        v25 = 17;
        v23 = (void (__fastcall ***)(_QWORD))v39;
      }
      else
      {
        v23 = *(void (__fastcall ****)(_QWORD))(v21 + 48);
        if ( v23 )
          (**v23)(*(_QWORD *)(v21 + 48));
        v24 = v23;
        v25 = 9;
        v26 = v39;
      }
      *a1 = v24;
      if ( v24 )
        (**v24)(v24);
      if ( (v25 & 0x10) != 0 )
      {
        v25 &= ~0x10u;
        if ( v26 )
          (*(void (__fastcall **)(_QWORD *))(*v26 + 8LL))(v26);
      }
      v27 = (v25 & 8) == 0;
LABEL_47:
      if ( v27 || !v23 )
        return a1;
      v16 = *v23;
      v17 = v23;
LABEL_25:
      ((void (__fastcall **)(_QWORD *))v16)[1](v17);
      return a1;
    }
LABEL_59:
    _invoke_watson(0, 0, 0, 0, 0);
  }
  if ( v11 != 1 )
  {
    *a1 = a5;
    if ( a5 )
      (**a5)(a5);
    return a1;
  }
  std::_Hash<std::_Umap_traits<std::wstring,Ofc::TCntPtr<GEL::IEffect const>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Ofc::TCntPtr<GEL::IEffect const>>>,0>>::find(
    a6,
    &v39);
  if ( v39 == *(_QWORD **)(a6 + 8) )
  {
    v13 = a5;
    v15 = (__int64)a5;
    if ( a5 )
      (**a5)(a5);
    v14 = 65;
    v12 = (void (__fastcall ***)(_QWORD))v39;
  }
  else
  {
    v12 = (void (__fastcall ***)(_QWORD))v39[6];
    if ( v12 )
      (**v12)(v12);
    v13 = v12;
    v14 = 33;
    v15 = (__int64)v39;
  }
  *a1 = v13;
  if ( v13 )
    (**v13)(v13);
  if ( (v14 & 0x40) != 0 )
  {
    v14 &= ~0x40u;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  }
  if ( (v14 & 0x20) != 0 && v12 )
  {
    v16 = *v12;
    v17 = v12;
    goto LABEL_25;
  }
  return a1;
}

```

## disassembly

```asm
0x1800f95a8  mov     [rsp-28h+arg_8], rbx
0x1800f95ad  push    rbp
0x1800f95ae  push    rsi
0x1800f95af  push    rdi
0x1800f95b0  push    r14
0x1800f95b2  push    r15
0x1800f95b4  mov     rbp, rsp
0x1800f95b7  sub     rsp, 80h
0x1800f95be  mov     rax, cs:__security_cookie
0x1800f95c5  xor     rax, rsp
0x1800f95c8  mov     [rbp+var_10], rax
0x1800f95cc  mov     r15, rcx
0x1800f95cf  mov     [rbp+var_50], rcx
0x1800f95d3  mov     rbx, [rbp+arg_28]
0x1800f95d7  mov     [rbp+var_48], 0
0x1800f95de  test    edx, edx
0x1800f95e0  jz      loc_1800F99BE
0x1800f95e6  sub     edx, 1
0x1800f95e9  jz      loc_1800F9983
0x1800f95ef  sub     edx, 1
0x1800f95f2  jz      loc_1800F9837
0x1800f95f8  sub     edx, 1
0x1800f95fb  jz      loc_1800F9837
0x1800f9601  sub     edx, 1
0x1800f9604  jz      loc_1800F9837
0x1800f960a  sub     edx, 1
0x1800f960d  jz      loc_1800F96ED
0x1800f9613  cmp     edx, 1
0x1800f9616  jz      short loc_1800F9633
0x1800f9618  mov     rcx, [rbp+arg_20]
0x1800f961c  mov     [r15], rcx
0x1800f961f  test    rcx, rcx
0x1800f9622  jz      loc_1800F99D5
0x1800f9628  mov     rax, [rcx]
0x1800f962b  mov     rax, [rax]
0x1800f962e  jmp     loc_1800F99CF
0x1800f9633  lea     rdx, [rbp+var_50]
0x1800f9637  mov     rcx, rbx
0x1800f963a  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,Ofc::TCntPtr<GEL::IEffect const>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Ofc::TCntPtr<GEL::IEffect const>>>,0>>::find(std::wstring const &)
0x1800f963f  mov     rdi, [rbp+var_50]
0x1800f9643  cmp     rdi, [rbx+8]
0x1800f9647  jz      short loc_1800F9670
0x1800f9649  mov     rdi, [rdi+30h]
0x1800f964d  test    rdi, rdi
0x1800f9650  jz      short loc_1800F9661
0x1800f9652  mov     rax, [rdi]
0x1800f9655  mov     rcx, rdi
0x1800f9658  mov     rax, [rax]
0x1800f965b  call    cs:__guard_dispatch_icall_fptr
0x1800f9661  mov     rbx, rdi
0x1800f9664  mov     r14d, 21h ; '!'
0x1800f966a  mov     rsi, [rbp+var_50]
0x1800f966e  jmp     short loc_1800F9695
0x1800f9670  mov     rbx, [rbp+arg_20]
0x1800f9674  mov     rsi, rbx
0x1800f9677  test    rbx, rbx
0x1800f967a  jz      short loc_1800F968B
0x1800f967c  mov     rax, [rbx]
0x1800f967f  mov     rcx, rbx
0x1800f9682  mov     rax, [rax]
0x1800f9685  call    cs:__guard_dispatch_icall_fptr
0x1800f968b  mov     r14d, 41h ; 'A'
0x1800f9691  mov     rdi, [rbp+var_50]
0x1800f9695  mov     [r15], rbx
0x1800f9698  test    rbx, rbx
0x1800f969b  jz      short loc_1800F96AC
0x1800f969d  mov     rax, [rbx]
0x1800f96a0  mov     rcx, rbx
0x1800f96a3  mov     rax, [rax]
0x1800f96a6  call    cs:__guard_dispatch_icall_fptr
0x1800f96ac  test    r14b, 40h
0x1800f96b0  jz      short loc_1800F96CB
0x1800f96b2  and     r14d, 0FFFFFFBFh
0x1800f96b6  test    rsi, rsi
0x1800f96b9  jz      short loc_1800F96CB
0x1800f96bb  mov     rax, [rsi]
0x1800f96be  mov     rcx, rsi
0x1800f96c1  mov     rax, [rax+8]
0x1800f96c5  call    cs:__guard_dispatch_icall_fptr
0x1800f96cb  test    r14b, 20h
0x1800f96cf  jz      loc_1800F99D5
0x1800f96d5  test    rdi, rdi
0x1800f96d8  jz      loc_1800F99D5
0x1800f96de  mov     rax, [rdi]
0x1800f96e1  mov     rcx, rdi
0x1800f96e4  mov     rax, [rax+8]
0x1800f96e8  jmp     loc_1800F99CF
0x1800f96ed  xorps   xmm0, xmm0
0x1800f96f0  movups  xmmword ptr [rbp+Block], xmm0
0x1800f96f4  xorps   xmm1, xmm1
0x1800f96f7  movdqu  [rbp+var_20], xmm1
0x1800f96fc  mov     r8d, 0Bh
0x1800f9702  lea     rdx, aStrokepaint; "StrokePaint"
0x1800f9709  lea     rcx, [rbp+Block]
0x1800f970d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800f9712  lea     r8, [rbp+Block]
0x1800f9716  cmp     qword ptr [rbp+var_20+8], 7
0x1800f971b  cmova   r8, [rbp+Block]
0x1800f9720  mov     r9, 0CBF29CE484222325h
0x1800f972a  mov     rax, qword ptr [rbp+var_20]
0x1800f972e  lea     r10, [rax+rax]
0x1800f9732  xor     edx, edx
0x1800f9734  test    r10, r10
0x1800f9737  jz      short loc_1800F9757
0x1800f9739  mov     rcx, 100000001B3h
0x1800f9743  movzx   eax, byte ptr [r8+rdx]
0x1800f9748  xor     r9, rax
0x1800f974b  imul    r9, rcx
0x1800f974f  inc     rdx
0x1800f9752  cmp     rdx, r10
0x1800f9755  jb      short loc_1800F9743
0x1800f9757  lea     r8, [rbp+Block]
0x1800f975b  lea     rdx, [rbp+var_40]
0x1800f975f  mov     rcx, rbx
0x1800f9762  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,Mso::TCntPtr<Mso::SVG::RenderableContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Mso::TCntPtr<Mso::SVG::RenderableContext>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800f9767  mov     rdi, [rax+8]
0x1800f976b  test    rdi, rdi
0x1800f976e  jnz     short loc_1800F9774
0x1800f9770  mov     rdi, [rbx+8]
0x1800f9774  mov     rax, qword ptr [rbp+var_20+8]
0x1800f9778  cmp     rax, 7
0x1800f977c  jbe     short loc_1800F97B0
0x1800f977e  mov     rcx, [rbp+Block]
0x1800f9782  mov     rdx, rcx
0x1800f9785  lea     rax, ds:2[rax*2]
0x1800f978d  cmp     rax, 1000h
0x1800f9793  jb      short loc_1800F97AA
0x1800f9795  mov     rcx, [rcx-8]; Block
0x1800f9799  sub     rdx, rcx
0x1800f979c  lea     rax, [rdx-8]
0x1800f97a0  cmp     rax, 1Fh
0x1800f97a4  ja      loc_1800F98F1
0x1800f97aa  call    cs:__imp_free
0x1800f97b0  cmp     rdi, [rbx+8]
0x1800f97b4  jz      short loc_1800F97DC
0x1800f97b6  mov     rbx, [rdi+30h]
0x1800f97ba  test    rbx, rbx
0x1800f97bd  jz      short loc_1800F97CE
0x1800f97bf  mov     rax, [rbx]
0x1800f97c2  mov     rcx, rbx
0x1800f97c5  mov     rax, [rax]
0x1800f97c8  call    cs:__guard_dispatch_icall_fptr
0x1800f97ce  mov     rcx, rbx
0x1800f97d1  mov     esi, 9
0x1800f97d6  mov     rdi, [rbp+var_50]
0x1800f97da  jmp     short loc_1800F97E7
0x1800f97dc  xor     edi, edi
0x1800f97de  xor     ecx, ecx
0x1800f97e0  lea     esi, [rdi+11h]
0x1800f97e3  mov     rbx, [rbp+var_50]
0x1800f97e7  mov     [r15], rcx
0x1800f97ea  test    rcx, rcx
0x1800f97ed  jz      short loc_1800F97FB
0x1800f97ef  mov     rax, [rcx]
0x1800f97f2  mov     rax, [rax]
0x1800f97f5  call    cs:__guard_dispatch_icall_fptr
0x1800f97fb  test    sil, 10h
0x1800f97ff  jz      short loc_1800F9819
0x1800f9801  and     esi, 0FFFFFFEFh
0x1800f9804  test    rdi, rdi
0x1800f9807  jz      short loc_1800F9819
0x1800f9809  mov     rax, [rdi]
0x1800f980c  mov     rcx, rdi
0x1800f980f  mov     rax, [rax+8]
0x1800f9813  call    cs:__guard_dispatch_icall_fptr
0x1800f9819  test    sil, 8
0x1800f981d  jz      loc_1800F99D5
0x1800f9823  test    rbx, rbx
0x1800f9826  jz      loc_1800F99D5
0x1800f982c  mov     rax, [rbx]
0x1800f982f  mov     rcx, rbx
0x1800f9832  jmp     loc_1800F96E4
0x1800f9837  xorps   xmm0, xmm0
0x1800f983a  movups  xmmword ptr [rbp+Block], xmm0
0x1800f983e  xorps   xmm1, xmm1
0x1800f9841  movdqu  [rbp+var_20], xmm1
0x1800f9846  mov     r8d, 9
0x1800f984c  lea     rdx, aFillpaint; "FillPaint"
0x1800f9853  lea     rcx, [rbp+Block]
0x1800f9857  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800f985c  nop
0x1800f985d  lea     r8, [rbp+Block]
0x1800f9861  cmp     qword ptr [rbp+var_20+8], 7
0x1800f9866  cmova   r8, [rbp+Block]
0x1800f986b  mov     r9, 0CBF29CE484222325h
0x1800f9875  mov     rax, qword ptr [rbp+var_20]
0x1800f9879  lea     r10, [rax+rax]
0x1800f987d  xor     edx, edx
0x1800f987f  test    r10, r10
0x1800f9882  jz      short loc_1800F98A2
0x1800f9884  mov     rcx, 100000001B3h
0x1800f988e  movzx   eax, byte ptr [r8+rdx]
0x1800f9893  xor     r9, rax
0x1800f9896  imul    r9, rcx
0x1800f989a  inc     rdx
0x1800f989d  cmp     rdx, r10
0x1800f98a0  jb      short loc_1800F988E
0x1800f98a2  lea     r8, [rbp+Block]
0x1800f98a6  lea     rdx, [rbp+var_40]
0x1800f98aa  mov     rcx, rbx
0x1800f98ad  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,Mso::TCntPtr<Mso::SVG::RenderableContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Mso::TCntPtr<Mso::SVG::RenderableContext>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800f98b2  mov     rdi, [rax+8]
0x1800f98b6  test    rdi, rdi
0x1800f98b9  jnz     short loc_1800F98BF
0x1800f98bb  mov     rdi, [rbx+8]
0x1800f98bf  mov     rax, qword ptr [rbp+var_20+8]
0x1800f98c3  cmp     rax, 7
0x1800f98c7  jbe     short loc_1800F9911
0x1800f98c9  mov     rcx, [rbp+Block]; Block
0x1800f98cd  mov     rdx, rcx
0x1800f98d0  lea     rax, ds:2[rax*2]
0x1800f98d8  cmp     rax, 1000h
0x1800f98de  jb      short loc_1800F990B
0x1800f98e0  mov     rcx, [rcx-8]
0x1800f98e4  sub     rdx, rcx
0x1800f98e7  lea     rax, [rdx-8]
0x1800f98eb  cmp     rax, 1Fh
0x1800f98ef  jbe     short loc_1800F990B
0x1800f98f1  mov     [rsp+80h+Reserved], 0; Reserved
0x1800f98fa  xor     r9d, r9d; LineNo
0x1800f98fd  xor     r8d, r8d; FileName
0x1800f9900  xor     edx, edx; FunctionName
0x1800f9902  xor     ecx, ecx; Expression
0x1800f9904  call    cs:__imp__invoke_watson
0x1800f990b  call    cs:__imp_free
0x1800f9911  cmp     rdi, [rbx+8]
0x1800f9915  jz      short loc_1800F993D
0x1800f9917  mov     rbx, [rdi+30h]
0x1800f991b  test    rbx, rbx
0x1800f991e  jz      short loc_1800F992F
0x1800f9920  mov     rax, [rbx]
0x1800f9923  mov     rcx, rbx
0x1800f9926  mov     rax, [rax]
0x1800f9929  call    cs:__guard_dispatch_icall_fptr
0x1800f992f  mov     rcx, rbx
0x1800f9932  mov     esi, 3
0x1800f9937  mov     rdi, [rbp+var_50]
0x1800f993b  jmp     short loc_1800F9948
0x1800f993d  xor     edi, edi
0x1800f993f  xor     ecx, ecx
0x1800f9941  lea     esi, [rdi+5]
0x1800f9944  mov     rbx, [rbp+var_50]
0x1800f9948  mov     [r15], rcx
0x1800f994b  test    rcx, rcx
0x1800f994e  jz      short loc_1800F995C
0x1800f9950  mov     rax, [rcx]
0x1800f9953  mov     rax, [rax]
0x1800f9956  call    cs:__guard_dispatch_icall_fptr
0x1800f995c  test    sil, 4
0x1800f9960  jz      short loc_1800F997A
0x1800f9962  and     esi, 0FFFFFFFBh
0x1800f9965  test    rdi, rdi
0x1800f9968  jz      short loc_1800F997A
0x1800f996a  mov     rax, [rdi]
0x1800f996d  mov     rcx, rdi
0x1800f9970  mov     rax, [rax+8]
0x1800f9974  call    cs:__guard_dispatch_icall_fptr
0x1800f997a  test    sil, 2
0x1800f997e  jmp     loc_1800F981D
0x1800f9983  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x1800f998b  movups  [rbp+var_40], xmm0
0x1800f998f  lea     r8, [rbp+var_40]
0x1800f9993  mov     rdx, r9
0x1800f9996  lea     rcx, [rbp+var_50]
0x1800f999a  call    cs:__imp_?Create@IEffectColorReplace@GEL@@SA?AV?$TCntPtr@UIEffectColorReplace@GEL@@@Ofc@@AEBUIEffect@2@AEBUColor@2@@Z; GEL::IEffectColorReplace::Create(GEL::IEffect const &,GEL::Color const &)
0x1800f99a0  mov     rcx, [rax]
0x1800f99a3  mov     qword ptr [rax], 0
0x1800f99aa  mov     [r15], rcx
0x1800f99ad  mov     rcx, [rbp+var_50]
0x1800f99b1  test    rcx, rcx
0x1800f99b4  jz      short loc_1800F99D5
0x1800f99b6  mov     rax, [rcx]
0x1800f99b9  jmp     loc_1800F96E4
0x1800f99be  mov     [rcx], r9
0x1800f99c1  test    r9, r9
0x1800f99c4  jz      short loc_1800F99D5
0x1800f99c6  mov     rcx, [r9]
0x1800f99c9  mov     rax, [rcx]
0x1800f99cc  mov     rcx, r9
0x1800f99cf  call    cs:__guard_dispatch_icall_fptr
0x1800f99d5  mov     rax, r15
0x1800f99d8  mov     rcx, [rbp+var_10]
0x1800f99dc  xor     rcx, rsp; StackCookie
0x1800f99df  call    __security_check_cookie
0x1800f99e4  mov     rbx, [rsp+80h+arg_8]
0x1800f99ec  add     rsp, 80h
0x1800f99f3  pop     r15
0x1800f99f5  pop     r14
0x1800f99f7  pop     rdi
0x1800f99f8  pop     rsi
0x1800f99f9  pop     rbp
0x1800f99fa  retn
```
