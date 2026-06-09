# std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>> &&)

- ea: `0x1800b3a5c`
- end: `0x1800b3b7a`
- name: `??$_Emplace@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@1@@Z`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800b5924`
- `0x1800ba858`
- `0x1800bb370`
- `0x1800bd420`
- `0x1800bf184`

## callees

- `0x1800a7d4c`
- `0x1800a9830`
- `0x1800ab8e4`
- `0x1800b3a5c`
- `0x1800b3bb8`
- `0x1800b3c14`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b3b2a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b3b2a`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _WORD *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 *v10; // rcx
  unsigned int v11; // ebx
  _QWORD *v12; // rsi
  _QWORD *v14; // [rsp+20h] [rbp-10h] BYREF
  _WORD *v15; // [rsp+28h] [rbp-8h]
  __int64 v16; // [rsp+60h] [rbp+30h] BYREF

  v16 = *a1;
  v14 = a1;
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
  v15 = v6;
  v8 = std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>,void *>>>::construct<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>,std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>(
         v7,
         v6 + 16,
         a3);
  std::_Construct_in_place<wchar_t *,wchar_t * const &>(v8, &v16);
  std::_Construct_in_place<wchar_t *,wchar_t * const &>(v9 + 8, &v16);
  std::_Construct_in_place<wchar_t *,wchar_t * const &>(v6 + 8, &v16);
  v6[12] = 0;
  v10 = *(__int64 **)(*a1 + 8LL);
  v11 = 0;
  if ( *((_BYTE *)v10 + 25) )
  {
    v12 = *(_QWORD **)(*a1 + 8LL);
  }
  else
  {
    do
    {
      v12 = v10;
      if ( *((_QWORD *)v6 + 4) >= (unsigned __int64)v10[4] )
      {
        v11 = 0;
        v10 = (__int64 *)v10[2];
      }
      else
      {
        v11 = 1;
        v10 = (__int64 *)*v10;
      }
    }
    while ( !*((_BYTE *)v10 + 25) );
  }
  if ( a1[1] == 0x555555555555555LL )
    std::_Xlength_error("map/set too long");
  v15 = 0;
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>,void *>>>(&v14);
  v14 = v12;
  v15 = (_WORD *)v11;
  *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>>>::_Insert_node(
                    a1,
                    &v14,
                    v6);
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800b3a5c  mov     [rsp-28h+arg_8], rbx
0x1800b3a61  mov     [rsp-28h+arg_10], rsi
0x1800b3a66  push    rbp
0x1800b3a67  push    rdi
0x1800b3a68  push    r13
0x1800b3a6a  push    r14
0x1800b3a6c  push    r15
0x1800b3a6e  mov     rbp, rsp
0x1800b3a71  sub     rsp, 30h
0x1800b3a75  mov     rbx, r8
0x1800b3a78  mov     r15, rdx
0x1800b3a7b  mov     r14, rcx
0x1800b3a7e  mov     rax, [rcx]
0x1800b3a81  mov     [rbp+arg_0], rax
0x1800b3a85  mov     [rbp+var_10], rcx
0x1800b3a89  mov     [rbp+var_8], 0
0x1800b3a91  mov     ecx, 30h ; '0'
0x1800b3a96  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800b3a9b  mov     rdi, rax
0x1800b3a9e  mov     [rbp+var_8], rax
0x1800b3aa2  lea     rdx, [rax+20h]
0x1800b3aa6  mov     r8, rbx
0x1800b3aa9  call    ??$construct@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@U12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@$$QEAU31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>,void *>>>::construct<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>,std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>,void *>> &,std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>> * const,std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>> &&)
0x1800b3aae  lea     rdx, [rbp+arg_0]
0x1800b3ab2  mov     rcx, rax
0x1800b3ab5  call    ??$_Construct_in_place@PEA_WAEBQEA_W@std@@YAXAEAPEA_WAEBQEA_W@Z; std::_Construct_in_place<wchar_t *,wchar_t * const &>(wchar_t * &,wchar_t * const &)
0x1800b3aba  lea     rcx, [rcx+8]
0x1800b3abe  lea     rdx, [rbp+arg_0]
0x1800b3ac2  call    ??$_Construct_in_place@PEA_WAEBQEA_W@std@@YAXAEAPEA_WAEBQEA_W@Z; std::_Construct_in_place<wchar_t *,wchar_t * const &>(wchar_t * &,wchar_t * const &)
0x1800b3ac7  lea     rcx, [rdi+10h]
0x1800b3acb  lea     rdx, [rbp+arg_0]
0x1800b3acf  call    ??$_Construct_in_place@PEA_WAEBQEA_W@std@@YAXAEAPEA_WAEBQEA_W@Z; std::_Construct_in_place<wchar_t *,wchar_t * const &>(wchar_t * &,wchar_t * const &)
0x1800b3ad4  mov     word ptr [rdi+18h], 0
0x1800b3ada  mov     rax, [r14]
0x1800b3add  mov     rcx, [rax+8]
0x1800b3ae1  xor     ebx, ebx
0x1800b3ae3  xor     r13d, r13d
0x1800b3ae6  cmp     [rcx+19h], bl
0x1800b3ae9  jnz     short loc_1800B3B10
0x1800b3aeb  mov     rax, [rdi+20h]
0x1800b3aef  mov     rsi, rcx
0x1800b3af2  cmp     rax, [rcx+20h]
0x1800b3af6  jnb     short loc_1800B3B02
0x1800b3af8  mov     ebx, 1
0x1800b3afd  mov     rcx, [rcx]
0x1800b3b00  jmp     short loc_1800B3B08
0x1800b3b02  xor     ebx, ebx
0x1800b3b04  mov     rcx, [rcx+10h]
0x1800b3b08  cmp     [rcx+19h], r13b
0x1800b3b0c  jz      short loc_1800B3AEF
0x1800b3b0e  jmp     short loc_1800B3B13
0x1800b3b10  mov     rsi, rcx
0x1800b3b13  mov     rax, 555555555555555h
0x1800b3b1d  cmp     [r14+8], rax
0x1800b3b21  jnz     short loc_1800B3B31
0x1800b3b23  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800b3b2a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b3b31  mov     [rbp+var_8], r13
0x1800b3b35  lea     rcx, [rbp+var_10]
0x1800b3b39  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>,void *>>>(void)
0x1800b3b3e  mov     [rbp+var_10], rsi
0x1800b3b42  mov     dword ptr [rbp+var_8], ebx
0x1800b3b45  mov     dword ptr [rbp+var_8+4], r13d
0x1800b3b49  mov     r8, rdi
0x1800b3b4c  lea     rdx, [rbp+var_10]
0x1800b3b50  mov     rcx, r14
0x1800b3b53  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>,void *> *>,std::_Tree_node<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>,void *> * const)
0x1800b3b58  mov     [r15], rax
0x1800b3b5b  mov     byte ptr [r15+8], 1
0x1800b3b60  mov     rax, r15
0x1800b3b63  mov     rbx, [rsp+30h+arg_8]
0x1800b3b68  mov     rsi, [rsp+30h+arg_10]
0x1800b3b6d  add     rsp, 30h
0x1800b3b71  pop     r15
0x1800b3b73  pop     r14
0x1800b3b75  pop     r13
0x1800b3b77  pop     rdi
0x1800b3b78  pop     rbp
0x1800b3b79  retn
```
