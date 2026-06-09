# Mso::SVG::FilterPrimitiveRenderer::GetInputEffect(Mso::SVG::InType,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,GEL::IEffect const &,GEL::IEffect const &,std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Ofc::TCntPtr<GEL::IEffect const>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Ofc::TCntPtr<GEL::IEffect const>>>> const &)

- ea: `0x1800f95c8`
- end: `0x1800f9a1b`
- name: `?GetInputEffect@FilterPrimitiveRenderer@SVG@Mso@@KA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@W4InType@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUIEffect@GEL@@2AEBV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@2@@8@@Z`
- size: `1107`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800f9a50`
- `0x1800f9b50`
- `0x1800fb360`

## callees

- `0x180009068`
- `0x1800244f8`
- `0x1800f95c8`
- `0x1800fbe80`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f97ca`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f992b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f97ca`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f992b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f9924`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f9924`
- `gfx!?Create@IEffectColorReplace@GEL@@SA?AV?$TCntPtr@UIEffectColorReplace@GEL@@@Ofc@@AEBUIEffect@2@AEBUColor@2@@Z` at `0x1800f99ba`
- `gfx!?Create@IEffectColorReplace@GEL@@SA?AV?$TCntPtr@UIEffectColorReplace@GEL@@@Ofc@@AEBUIEffect@2@AEBUColor@2@@Z` at `0x1800f99ba`

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
    std::wstring::_Construct<1,wchar_t *>(Block, L"FillPaint");
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
    std::wstring::_Construct<1,wchar_t *>(Block, L"StrokePaint");
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
0x1800f95c8  mov     [rsp-28h+arg_8], rbx
0x1800f95cd  push    rbp
0x1800f95ce  push    rsi
0x1800f95cf  push    rdi
0x1800f95d0  push    r14
0x1800f95d2  push    r15
0x1800f95d4  mov     rbp, rsp
0x1800f95d7  sub     rsp, 80h
0x1800f95de  mov     rax, cs:__security_cookie
0x1800f95e5  xor     rax, rsp
0x1800f95e8  mov     [rbp+var_10], rax
0x1800f95ec  mov     r15, rcx
0x1800f95ef  mov     [rbp+var_50], rcx
0x1800f95f3  mov     rbx, [rbp+arg_28]
0x1800f95f7  mov     [rbp+var_48], 0
0x1800f95fe  test    edx, edx
0x1800f9600  jz      loc_1800F99DE
0x1800f9606  sub     edx, 1
0x1800f9609  jz      loc_1800F99A3
0x1800f960f  sub     edx, 1
0x1800f9612  jz      loc_1800F9857
0x1800f9618  sub     edx, 1
0x1800f961b  jz      loc_1800F9857
0x1800f9621  sub     edx, 1
0x1800f9624  jz      loc_1800F9857
0x1800f962a  sub     edx, 1
0x1800f962d  jz      loc_1800F970D
0x1800f9633  cmp     edx, 1
0x1800f9636  jz      short loc_1800F9653
0x1800f9638  mov     rcx, [rbp+arg_20]
0x1800f963c  mov     [r15], rcx
0x1800f963f  test    rcx, rcx
0x1800f9642  jz      loc_1800F99F5
0x1800f9648  mov     rax, [rcx]
0x1800f964b  mov     rax, [rax]
0x1800f964e  jmp     loc_1800F99EF
0x1800f9653  lea     rdx, [rbp+var_50]
0x1800f9657  mov     rcx, rbx
0x1800f965a  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,Ofc::TCntPtr<GEL::IEffect const>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Ofc::TCntPtr<GEL::IEffect const>>>,0>>::find(std::wstring const &)
0x1800f965f  mov     rdi, [rbp+var_50]
0x1800f9663  cmp     rdi, [rbx+8]
0x1800f9667  jz      short loc_1800F9690
0x1800f9669  mov     rdi, [rdi+30h]
0x1800f966d  test    rdi, rdi
0x1800f9670  jz      short loc_1800F9681
0x1800f9672  mov     rax, [rdi]
0x1800f9675  mov     rcx, rdi
0x1800f9678  mov     rax, [rax]
0x1800f967b  call    cs:__guard_dispatch_icall_fptr
0x1800f9681  mov     rbx, rdi
0x1800f9684  mov     r14d, 21h ; '!'
0x1800f968a  mov     rsi, [rbp+var_50]
0x1800f968e  jmp     short loc_1800F96B5
0x1800f9690  mov     rbx, [rbp+arg_20]
0x1800f9694  mov     rsi, rbx
0x1800f9697  test    rbx, rbx
0x1800f969a  jz      short loc_1800F96AB
0x1800f969c  mov     rax, [rbx]
0x1800f969f  mov     rcx, rbx
0x1800f96a2  mov     rax, [rax]
0x1800f96a5  call    cs:__guard_dispatch_icall_fptr
0x1800f96ab  mov     r14d, 41h ; 'A'
0x1800f96b1  mov     rdi, [rbp+var_50]
0x1800f96b5  mov     [r15], rbx
0x1800f96b8  test    rbx, rbx
0x1800f96bb  jz      short loc_1800F96CC
0x1800f96bd  mov     rax, [rbx]
0x1800f96c0  mov     rcx, rbx
0x1800f96c3  mov     rax, [rax]
0x1800f96c6  call    cs:__guard_dispatch_icall_fptr
0x1800f96cc  test    r14b, 40h
0x1800f96d0  jz      short loc_1800F96EB
0x1800f96d2  and     r14d, 0FFFFFFBFh
0x1800f96d6  test    rsi, rsi
0x1800f96d9  jz      short loc_1800F96EB
0x1800f96db  mov     rax, [rsi]
0x1800f96de  mov     rcx, rsi
0x1800f96e1  mov     rax, [rax+8]
0x1800f96e5  call    cs:__guard_dispatch_icall_fptr
0x1800f96eb  test    r14b, 20h
0x1800f96ef  jz      loc_1800F99F5
0x1800f96f5  test    rdi, rdi
0x1800f96f8  jz      loc_1800F99F5
0x1800f96fe  mov     rax, [rdi]
0x1800f9701  mov     rcx, rdi
0x1800f9704  mov     rax, [rax+8]
0x1800f9708  jmp     loc_1800F99EF
0x1800f970d  xorps   xmm0, xmm0
0x1800f9710  movups  xmmword ptr [rbp+Block], xmm0
0x1800f9714  xorps   xmm1, xmm1
0x1800f9717  movdqu  [rbp+var_20], xmm1
0x1800f971c  mov     r8d, 0Bh
0x1800f9722  lea     rdx, aStrokepaint; "StrokePaint"
0x1800f9729  lea     rcx, [rbp+Block]
0x1800f972d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800f9732  lea     r8, [rbp+Block]
0x1800f9736  cmp     qword ptr [rbp+var_20+8], 7
0x1800f973b  cmova   r8, [rbp+Block]
0x1800f9740  mov     r9, 0CBF29CE484222325h
0x1800f974a  mov     rax, qword ptr [rbp+var_20]
0x1800f974e  lea     r10, [rax+rax]
0x1800f9752  xor     edx, edx
0x1800f9754  test    r10, r10
0x1800f9757  jz      short loc_1800F9777
0x1800f9759  mov     rcx, 100000001B3h
0x1800f9763  movzx   eax, byte ptr [r8+rdx]
0x1800f9768  xor     r9, rax
0x1800f976b  imul    r9, rcx
0x1800f976f  inc     rdx
0x1800f9772  cmp     rdx, r10
0x1800f9775  jb      short loc_1800F9763
0x1800f9777  lea     r8, [rbp+Block]
0x1800f977b  lea     rdx, [rbp+var_40]
0x1800f977f  mov     rcx, rbx
0x1800f9782  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,Mso::TCntPtr<Mso::SVG::RenderableContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Mso::TCntPtr<Mso::SVG::RenderableContext>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800f9787  mov     rdi, [rax+8]
0x1800f978b  test    rdi, rdi
0x1800f978e  jnz     short loc_1800F9794
0x1800f9790  mov     rdi, [rbx+8]
0x1800f9794  mov     rax, qword ptr [rbp+var_20+8]
0x1800f9798  cmp     rax, 7
0x1800f979c  jbe     short loc_1800F97D0
0x1800f979e  mov     rcx, [rbp+Block]
0x1800f97a2  mov     rdx, rcx
0x1800f97a5  lea     rax, ds:2[rax*2]
0x1800f97ad  cmp     rax, 1000h
0x1800f97b3  jb      short loc_1800F97CA
0x1800f97b5  mov     rcx, [rcx-8]; Block
0x1800f97b9  sub     rdx, rcx
0x1800f97bc  lea     rax, [rdx-8]
0x1800f97c0  cmp     rax, 1Fh
0x1800f97c4  ja      loc_1800F9911
0x1800f97ca  call    cs:__imp_free
0x1800f97d0  cmp     rdi, [rbx+8]
0x1800f97d4  jz      short loc_1800F97FC
0x1800f97d6  mov     rbx, [rdi+30h]
0x1800f97da  test    rbx, rbx
0x1800f97dd  jz      short loc_1800F97EE
0x1800f97df  mov     rax, [rbx]
0x1800f97e2  mov     rcx, rbx
0x1800f97e5  mov     rax, [rax]
0x1800f97e8  call    cs:__guard_dispatch_icall_fptr
0x1800f97ee  mov     rcx, rbx
0x1800f97f1  mov     esi, 9
0x1800f97f6  mov     rdi, [rbp+var_50]
0x1800f97fa  jmp     short loc_1800F9807
0x1800f97fc  xor     edi, edi
0x1800f97fe  xor     ecx, ecx
0x1800f9800  lea     esi, [rdi+11h]
0x1800f9803  mov     rbx, [rbp+var_50]
0x1800f9807  mov     [r15], rcx
0x1800f980a  test    rcx, rcx
0x1800f980d  jz      short loc_1800F981B
0x1800f980f  mov     rax, [rcx]
0x1800f9812  mov     rax, [rax]
0x1800f9815  call    cs:__guard_dispatch_icall_fptr
0x1800f981b  test    sil, 10h
0x1800f981f  jz      short loc_1800F9839
0x1800f9821  and     esi, 0FFFFFFEFh
0x1800f9824  test    rdi, rdi
0x1800f9827  jz      short loc_1800F9839
0x1800f9829  mov     rax, [rdi]
0x1800f982c  mov     rcx, rdi
0x1800f982f  mov     rax, [rax+8]
0x1800f9833  call    cs:__guard_dispatch_icall_fptr
0x1800f9839  test    sil, 8
0x1800f983d  jz      loc_1800F99F5
0x1800f9843  test    rbx, rbx
0x1800f9846  jz      loc_1800F99F5
0x1800f984c  mov     rax, [rbx]
0x1800f984f  mov     rcx, rbx
0x1800f9852  jmp     loc_1800F9704
0x1800f9857  xorps   xmm0, xmm0
0x1800f985a  movups  xmmword ptr [rbp+Block], xmm0
0x1800f985e  xorps   xmm1, xmm1
0x1800f9861  movdqu  [rbp+var_20], xmm1
0x1800f9866  mov     r8d, 9
0x1800f986c  lea     rdx, aFillpaint; "FillPaint"
0x1800f9873  lea     rcx, [rbp+Block]
0x1800f9877  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800f987c  nop
0x1800f987d  lea     r8, [rbp+Block]
0x1800f9881  cmp     qword ptr [rbp+var_20+8], 7
0x1800f9886  cmova   r8, [rbp+Block]
0x1800f988b  mov     r9, 0CBF29CE484222325h
0x1800f9895  mov     rax, qword ptr [rbp+var_20]
0x1800f9899  lea     r10, [rax+rax]
0x1800f989d  xor     edx, edx
0x1800f989f  test    r10, r10
0x1800f98a2  jz      short loc_1800F98C2
0x1800f98a4  mov     rcx, 100000001B3h
0x1800f98ae  movzx   eax, byte ptr [r8+rdx]
0x1800f98b3  xor     r9, rax
0x1800f98b6  imul    r9, rcx
0x1800f98ba  inc     rdx
0x1800f98bd  cmp     rdx, r10
0x1800f98c0  jb      short loc_1800F98AE
0x1800f98c2  lea     r8, [rbp+Block]
0x1800f98c6  lea     rdx, [rbp+var_40]
0x1800f98ca  mov     rcx, rbx
0x1800f98cd  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$TCntPtr@VRenderableContext@SVG@Mso@@@Mso@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,Mso::TCntPtr<Mso::SVG::RenderableContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Mso::TCntPtr<Mso::SVG::RenderableContext>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800f98d2  mov     rdi, [rax+8]
0x1800f98d6  test    rdi, rdi
0x1800f98d9  jnz     short loc_1800F98DF
0x1800f98db  mov     rdi, [rbx+8]
0x1800f98df  mov     rax, qword ptr [rbp+var_20+8]
0x1800f98e3  cmp     rax, 7
0x1800f98e7  jbe     short loc_1800F9931
0x1800f98e9  mov     rcx, [rbp+Block]; Block
0x1800f98ed  mov     rdx, rcx
0x1800f98f0  lea     rax, ds:2[rax*2]
0x1800f98f8  cmp     rax, 1000h
0x1800f98fe  jb      short loc_1800F992B
0x1800f9900  mov     rcx, [rcx-8]
0x1800f9904  sub     rdx, rcx
0x1800f9907  lea     rax, [rdx-8]
0x1800f990b  cmp     rax, 1Fh
0x1800f990f  jbe     short loc_1800F992B
0x1800f9911  mov     [rsp+80h+Reserved], 0; Reserved
0x1800f991a  xor     r9d, r9d; LineNo
0x1800f991d  xor     r8d, r8d; FileName
0x1800f9920  xor     edx, edx; FunctionName
0x1800f9922  xor     ecx, ecx; Expression
0x1800f9924  call    cs:__imp__invoke_watson
0x1800f992b  call    cs:__imp_free
0x1800f9931  cmp     rdi, [rbx+8]
0x1800f9935  jz      short loc_1800F995D
0x1800f9937  mov     rbx, [rdi+30h]
0x1800f993b  test    rbx, rbx
0x1800f993e  jz      short loc_1800F994F
0x1800f9940  mov     rax, [rbx]
0x1800f9943  mov     rcx, rbx
0x1800f9946  mov     rax, [rax]
0x1800f9949  call    cs:__guard_dispatch_icall_fptr
0x1800f994f  mov     rcx, rbx
0x1800f9952  mov     esi, 3
0x1800f9957  mov     rdi, [rbp+var_50]
0x1800f995b  jmp     short loc_1800F9968
0x1800f995d  xor     edi, edi
0x1800f995f  xor     ecx, ecx
0x1800f9961  lea     esi, [rdi+5]
0x1800f9964  mov     rbx, [rbp+var_50]
0x1800f9968  mov     [r15], rcx
0x1800f996b  test    rcx, rcx
0x1800f996e  jz      short loc_1800F997C
0x1800f9970  mov     rax, [rcx]
0x1800f9973  mov     rax, [rax]
0x1800f9976  call    cs:__guard_dispatch_icall_fptr
0x1800f997c  test    sil, 4
0x1800f9980  jz      short loc_1800F999A
0x1800f9982  and     esi, 0FFFFFFFBh
0x1800f9985  test    rdi, rdi
0x1800f9988  jz      short loc_1800F999A
0x1800f998a  mov     rax, [rdi]
0x1800f998d  mov     rcx, rdi
0x1800f9990  mov     rax, [rax+8]
0x1800f9994  call    cs:__guard_dispatch_icall_fptr
0x1800f999a  test    sil, 2
0x1800f999e  jmp     loc_1800F983D
0x1800f99a3  movdqa  xmm0, cs:__xmm@3f800000000000000000000000000000
0x1800f99ab  movups  [rbp+var_40], xmm0
0x1800f99af  lea     r8, [rbp+var_40]
0x1800f99b3  mov     rdx, r9
0x1800f99b6  lea     rcx, [rbp+var_50]
0x1800f99ba  call    cs:__imp_?Create@IEffectColorReplace@GEL@@SA?AV?$TCntPtr@UIEffectColorReplace@GEL@@@Ofc@@AEBUIEffect@2@AEBUColor@2@@Z; GEL::IEffectColorReplace::Create(GEL::IEffect const &,GEL::Color const &)
0x1800f99c0  mov     rcx, [rax]
0x1800f99c3  mov     qword ptr [rax], 0
0x1800f99ca  mov     [r15], rcx
0x1800f99cd  mov     rcx, [rbp+var_50]
0x1800f99d1  test    rcx, rcx
0x1800f99d4  jz      short loc_1800F99F5
0x1800f99d6  mov     rax, [rcx]
0x1800f99d9  jmp     loc_1800F9704
0x1800f99de  mov     [rcx], r9
0x1800f99e1  test    r9, r9
0x1800f99e4  jz      short loc_1800F99F5
0x1800f99e6  mov     rcx, [r9]
0x1800f99e9  mov     rax, [rcx]
0x1800f99ec  mov     rcx, r9
0x1800f99ef  call    cs:__guard_dispatch_icall_fptr
0x1800f99f5  mov     rax, r15
0x1800f99f8  mov     rcx, [rbp+var_10]
0x1800f99fc  xor     rcx, rsp; StackCookie
0x1800f99ff  call    __security_check_cookie
0x1800f9a04  mov     rbx, [rsp+80h+arg_8]
0x1800f9a0c  add     rsp, 80h
0x1800f9a13  pop     r15
0x1800f9a15  pop     r14
0x1800f9a17  pop     rdi
0x1800f9a18  pop     rsi
0x1800f9a19  pop     rbp
0x1800f9a1a  retn
```
