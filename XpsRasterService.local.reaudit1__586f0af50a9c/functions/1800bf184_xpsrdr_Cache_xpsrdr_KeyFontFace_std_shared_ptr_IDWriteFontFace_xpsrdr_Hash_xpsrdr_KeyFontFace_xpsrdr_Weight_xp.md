# xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::insert(std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &)

- ea: `0x1800bf184`
- end: `0x1800bf2d2`
- name: `?insert@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@4@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800bdaf8`

## callees

- `0x1800a7d4c`
- `0x1800adcc0`
- `0x1800add54`
- `0x1800b1bbc`
- `0x1800b3a5c`
- `0x1800bd90c`
- `0x1800bda38`
- `0x1800bda98`
- `0x1800bdbf8`
- `0x1800bf184`
- `0x1800bf2d8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800bf235`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800bf235`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r12
  __int64 v7; // r13
  _QWORD **v8; // rbx
  __int64 **v9; // r15
  __int64 v10; // rdi
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  _QWORD **v15; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *v16; // [rsp+28h] [rbp-20h]
  char v17[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v18; // [rsp+90h] [rbp+48h] BYREF

  v6 = xpsrdr::Hash<xpsrdr::KeyFontFace>::operator()(a1, a3);
  v18 = v6;
  v7 = a1 + 24;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(
    a1 + 24,
    &v15,
    &v18);
  while ( 1 )
  {
    v8 = v15;
    if ( v15 == v16 )
      break;
    if ( (unsigned __int8)xpsrdr::KeyFontFace::operator==(a3, v15[5] + 2) )
    {
      std::shared_ptr<ID2D1Brush>::operator=(v8[5] + 7, a3 + 40);
      *(_QWORD *)a2 = v8[5];
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(&v15);
  }
  xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::resize(a1);
  v9 = (__int64 **)(a1 + 8);
  if ( *(_QWORD *)(a1 + 16) == 0x38E38E38E38E38ELL )
    std::_Xlength_error("list too long");
  v10 = **v9;
  v15 = v9;
  v16 = 0;
  v11 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(72);
  v16 = v11;
  std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>>>::construct<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &>(
    v12,
    v11 + 2,
    a3);
  v9[1] = (__int64 *)((char *)v9[1] + 1);
  v13 = *(_QWORD **)(v10 + 8);
  *v11 = v10;
  v11[1] = v13;
  v16 = 0;
  *(_QWORD *)(v10 + 8) = v11;
  *v13 = v11;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>>>(&v15);
  v15 = (_QWORD **)v6;
  v16 = (_QWORD *)**v9;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(
    v7,
    v17,
    &v15);
  *(_QWORD *)a2 = **v9;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800bf184  push    rbp
0x1800bf186  push    rbx
0x1800bf187  push    rsi
0x1800bf188  push    rdi
0x1800bf189  push    r12
0x1800bf18b  push    r13
0x1800bf18d  push    r14
0x1800bf18f  push    r15
0x1800bf191  mov     rbp, rsp
0x1800bf194  sub     rsp, 48h
0x1800bf198  mov     r14, r8
0x1800bf19b  mov     rsi, rdx
0x1800bf19e  mov     rdi, rcx
0x1800bf1a1  mov     rdx, r8
0x1800bf1a4  call    ??R?$Hash@UKeyFontFace@xpsrdr@@@xpsrdr@@QEBA_KAEBUKeyFontFace@1@@Z; xpsrdr::Hash<xpsrdr::KeyFontFace>::operator()(xpsrdr::KeyFontFace const &)
0x1800bf1a9  mov     r12, rax
0x1800bf1ac  mov     [rbp+arg_0], rax
0x1800bf1b0  lea     r13, [rdi+18h]
0x1800bf1b4  lea     r8, [rbp+arg_0]
0x1800bf1b8  lea     rdx, [rbp+var_28]
0x1800bf1bc  mov     rcx, r13
0x1800bf1bf  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x1800bf1c4  mov     rbx, [rbp+var_28]
0x1800bf1c8  cmp     rbx, [rbp+var_20]
0x1800bf1cc  jz      short loc_1800BF20E
0x1800bf1ce  mov     rdx, [rbx+28h]
0x1800bf1d2  add     rdx, 10h
0x1800bf1d6  mov     rcx, r14
0x1800bf1d9  call    ??8KeyFontFace@xpsrdr@@QEBA_NAEBU01@@Z; xpsrdr::KeyFontFace::operator==(xpsrdr::KeyFontFace const &)
0x1800bf1de  test    al, al
0x1800bf1e0  jnz     short loc_1800BF1ED
0x1800bf1e2  lea     rcx, [rbp+var_28]
0x1800bf1e6  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800bf1eb  jmp     short loc_1800BF1C4
0x1800bf1ed  lea     rdx, [r14+28h]
0x1800bf1f1  mov     rcx, [rbx+28h]
0x1800bf1f5  add     rcx, 38h ; '8'
0x1800bf1f9  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bf1fe  mov     rax, [rbx+28h]
0x1800bf202  mov     [rsi], rax
0x1800bf205  mov     byte ptr [rsi+8], 0
0x1800bf209  jmp     loc_1800BF2BE
0x1800bf20e  movss   xmm1, dword ptr [rdi]
0x1800bf212  mov     rcx, rdi
0x1800bf215  call    ?resize@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::resize(float)
0x1800bf21a  lea     r15, [rdi+8]
0x1800bf21e  mov     rax, 38E38E38E38E38Eh
0x1800bf228  cmp     [r15+8], rax
0x1800bf22c  jnz     short loc_1800BF23C
0x1800bf22e  lea     rcx, aListTooLong; "list too long"
0x1800bf235  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800bf23c  mov     rax, [r15]
0x1800bf23f  mov     rdi, [rax]
0x1800bf242  mov     [rbp+var_28], r15
0x1800bf246  mov     [rbp+var_20], 0
0x1800bf24e  mov     ecx, 48h ; 'H'
0x1800bf253  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800bf258  mov     rbx, rax
0x1800bf25b  mov     [rbp+var_20], rax
0x1800bf25f  lea     rdx, [rax+10h]
0x1800bf263  mov     r8, r14
0x1800bf266  call    ??$construct@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>>>::construct<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &>(std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>> &,std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> * const,std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &)
0x1800bf26b  nop
0x1800bf26c  inc     qword ptr [r15+8]
0x1800bf270  mov     rdx, [rdi+8]
0x1800bf274  mov     [rbx], rdi
0x1800bf277  mov     [rbx+8], rdx
0x1800bf27b  mov     [rbp+var_20], 0
0x1800bf283  mov     [rdi+8], rbx
0x1800bf287  mov     [rdx], rbx
0x1800bf28a  lea     rcx, [rbp+var_28]
0x1800bf28e  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>,void *>>>(void)
0x1800bf293  mov     [rbp+var_28], r12
0x1800bf297  mov     rax, [r15]
0x1800bf29a  mov     rdx, [rax]
0x1800bf29d  mov     [rbp+var_20], rdx
0x1800bf2a1  lea     r8, [rbp+var_28]
0x1800bf2a5  lea     rdx, [rbp+var_18]
0x1800bf2a9  mov     rcx, r13
0x1800bf2ac  call    ??$_Emplace@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>> &&)
0x1800bf2b1  mov     rax, [r15]
0x1800bf2b4  mov     rcx, [rax]
0x1800bf2b7  mov     [rsi], rcx
0x1800bf2ba  mov     byte ptr [rsi+8], 1
0x1800bf2be  mov     rax, rsi
0x1800bf2c1  add     rsp, 48h
0x1800bf2c5  pop     r15
0x1800bf2c7  pop     r14
0x1800bf2c9  pop     r13
0x1800bf2cb  pop     r12
0x1800bf2cd  pop     rdi
0x1800bf2ce  pop     rsi
0x1800bf2cf  pop     rbx
0x1800bf2d0  pop     rbp
0x1800bf2d1  retn
```
