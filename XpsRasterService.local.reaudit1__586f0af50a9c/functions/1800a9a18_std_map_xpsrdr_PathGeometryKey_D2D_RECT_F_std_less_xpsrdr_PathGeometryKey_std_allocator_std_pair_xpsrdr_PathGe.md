# std::map<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>>::_Try_emplace<xpsrdr::PathGeometryKey const &,>(xpsrdr::PathGeometryKey const &)

- ea: `0x1800a9a18`
- end: `0x1800a9b21`
- name: `??$_Try_emplace@AEBUPathGeometryKey@xpsrdr@@$$V@?$map@UPathGeometryKey@xpsrdr@@UD2D_RECT_F@@U?$less@UPathGeometryKey@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@PEAX@std@@_N@1@AEBUPathGeometryKey@xpsrdr@@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800aa8b4`

## callees

- `0x1800a7d4c`
- `0x1800a9830`
- `0x1800a9894`
- `0x1800a9944`
- `0x1800a9a18`
- `0x1800a9c20`
- `0x1800a9cb4`
- `0x1800ab8e4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a9a75`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a9a75`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::map<xpsrdr::PathGeometryKey,D2D_RECT_F>::_Try_emplace<xpsrdr::PathGeometryKey const &,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  std::_Tree<std::_Tmap_traits<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>,0>>::_Find_lower_bound<xpsrdr::PathGeometryKey>(
    a1,
    &v14);
  v6 = v15;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>,0>>::_Lower_bound_duplicate<xpsrdr::PathGeometryKey>(
                          v7,
                          v15,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x38E38E38E38E38ELL )
      std::_Xlength_error("map/set too long");
    v12 = a3;
    v16 = *a1;
    v13 = (unsigned __int64)a1;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(72);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>,void *>>>::construct<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>,std::piecewise_construct_t const &,std::tuple<xpsrdr::PathGeometryKey const &>,std::tuple<>>(
      v9,
      v8 + 32,
      v10,
      &v12);
    std::_Construct_in_place<wchar_t *,wchar_t * const &>(v8, &v16);
    std::_Construct_in_place<wchar_t *,wchar_t * const &>(v8 + 8, &v16);
    std::_Construct_in_place<wchar_t *,wchar_t * const &>(v8 + 16, &v16);
    *(_WORD *)(v8 + 24) = 0;
    *((_QWORD *)&v13 + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>(&v13);
    v13 = v14;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>>>::_Insert_node(
                      a1,
                      &v13,
                      v8);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x1800a9a18  mov     [rsp-18h+arg_0], rbx
0x1800a9a1d  mov     [rsp-18h+arg_8], rsi
0x1800a9a22  push    rbp
0x1800a9a23  push    rdi
0x1800a9a24  push    r14
0x1800a9a26  mov     rbp, rsp
0x1800a9a29  sub     rsp, 70h
0x1800a9a2d  mov     r14, r8
0x1800a9a30  mov     rdi, rdx
0x1800a9a33  mov     rsi, rcx
0x1800a9a36  lea     rdx, [rbp+var_20]
0x1800a9a3a  call    ??$_Find_lower_bound@UPathGeometryKey@xpsrdr@@@?$_Tree@V?$_Tmap_traits@UPathGeometryKey@xpsrdr@@UD2D_RECT_F@@U?$less@UPathGeometryKey@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@PEAX@std@@@1@AEBUPathGeometryKey@xpsrdr@@@Z; std::_Tree<std::_Tmap_traits<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>,0>>::_Find_lower_bound<xpsrdr::PathGeometryKey>(xpsrdr::PathGeometryKey const &)
0x1800a9a3f  mov     r8, r14
0x1800a9a42  mov     rbx, [rbp+var_10]
0x1800a9a46  mov     rdx, rbx
0x1800a9a49  call    ??$_Lower_bound_duplicate@UPathGeometryKey@xpsrdr@@@?$_Tree@V?$_Tmap_traits@UPathGeometryKey@xpsrdr@@UD2D_RECT_F@@U?$less@UPathGeometryKey@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@@5@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@PEAX@1@AEBUPathGeometryKey@xpsrdr@@@Z; std::_Tree<std::_Tmap_traits<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>,0>>::_Lower_bound_duplicate<xpsrdr::PathGeometryKey>(std::_Tree_node<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>,void *> * const,xpsrdr::PathGeometryKey const &)
0x1800a9a4e  test    al, al
0x1800a9a50  jz      short loc_1800A9A5E
0x1800a9a52  mov     [rdi], rbx
0x1800a9a55  mov     byte ptr [rdi+8], 0
0x1800a9a59  jmp     loc_1800A9B09
0x1800a9a5e  mov     rax, 38E38E38E38E38Eh
0x1800a9a68  cmp     [rsi+8], rax
0x1800a9a6c  jnz     short loc_1800A9A7C
0x1800a9a6e  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800a9a75  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800a9a7c  mov     [rbp+var_40], r14
0x1800a9a80  mov     rax, [rsi]
0x1800a9a83  mov     [rbp+arg_18], rax
0x1800a9a87  mov     qword ptr [rbp+var_30], rsi
0x1800a9a8b  mov     qword ptr [rbp+var_30+8], 0
0x1800a9a93  mov     ecx, 48h ; 'H'
0x1800a9a98  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800a9a9d  mov     rbx, rax
0x1800a9aa0  lea     rdx, [rax+20h]
0x1800a9aa4  lea     r9, [rbp+var_40]
0x1800a9aa8  call    ??$construct@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBUPathGeometryKey@xpsrdr@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBUPathGeometryKey@xpsrdr@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>,void *>>>::construct<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>,std::piecewise_construct_t const &,std::tuple<xpsrdr::PathGeometryKey const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>,void *>> &,std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F> * const,std::piecewise_construct_t const &,std::tuple<xpsrdr::PathGeometryKey const &> &&,std::tuple<> &&)
0x1800a9aad  lea     rdx, [rbp+arg_18]
0x1800a9ab1  mov     rcx, rbx
0x1800a9ab4  call    ??$_Construct_in_place@PEA_WAEBQEA_W@std@@YAXAEAPEA_WAEBQEA_W@Z; std::_Construct_in_place<wchar_t *,wchar_t * const &>(wchar_t * &,wchar_t * const &)
0x1800a9ab9  lea     rcx, [rbx+8]
0x1800a9abd  lea     rdx, [rbp+arg_18]
0x1800a9ac1  call    ??$_Construct_in_place@PEA_WAEBQEA_W@std@@YAXAEAPEA_WAEBQEA_W@Z; std::_Construct_in_place<wchar_t *,wchar_t * const &>(wchar_t * &,wchar_t * const &)
0x1800a9ac6  lea     rcx, [rbx+10h]
0x1800a9aca  lea     rdx, [rbp+arg_18]
0x1800a9ace  call    ??$_Construct_in_place@PEA_WAEBQEA_W@std@@YAXAEAPEA_WAEBQEA_W@Z; std::_Construct_in_place<wchar_t *,wchar_t * const &>(wchar_t * &,wchar_t * const &)
0x1800a9ad3  mov     word ptr [rbx+18h], 0
0x1800a9ad9  mov     qword ptr [rbp+var_30+8], 0
0x1800a9ae1  lea     rcx, [rbp+var_30]
0x1800a9ae5  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>(void)
0x1800a9aea  movups  xmm0, [rbp+var_20]
0x1800a9aee  movdqu  [rbp+var_30], xmm0
0x1800a9af3  mov     r8, rbx
0x1800a9af6  lea     rdx, [rbp+var_30]
0x1800a9afa  mov     rcx, rsi
0x1800a9afd  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>,void *> *>,std::_Tree_node<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>,void *> * const)
0x1800a9b02  mov     [rdi], rax
0x1800a9b05  mov     byte ptr [rdi+8], 1
0x1800a9b09  mov     rax, rdi
0x1800a9b0c  lea     r11, [rsp+70h+var_s0]
0x1800a9b11  mov     rbx, [r11+20h]
0x1800a9b15  mov     rsi, [r11+28h]
0x1800a9b19  mov     rsp, r11
0x1800a9b1c  pop     r14
0x1800a9b1e  pop     rdi
0x1800a9b1f  pop     rbp
0x1800a9b20  retn
```
