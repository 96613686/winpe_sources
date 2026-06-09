# xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::insert(std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>> const &)

- ea: `0x1800b5924`
- end: `0x1800b5a77`
- name: `?insert@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@4@@Z`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800b3d30`

## callees

- `0x1800a7d4c`
- `0x1800add54`
- `0x1800b1bbc`
- `0x1800b3918`
- `0x1800b3a5c`
- `0x1800b3b80`
- `0x1800b3c38`
- `0x1800b3ca8`
- `0x1800b3e10`
- `0x1800b5924`
- `0x1800b5a80`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b59d6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b59d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r15
  _QWORD *v7; // r12
  _QWORD **v8; // rbx
  __int64 v9; // r8
  __int64 **v10; // rsi
  __int64 v11; // rbx
  char *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // r9
  _QWORD **v17; // [rsp+20h] [rbp-20h] BYREF
  _QWORD **v18; // [rsp+28h] [rbp-18h]
  char v19[16]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+70h] [rbp+30h] BYREF

  v6 = xpsrdr::Hash<xpsrdr::KeyBrush>::operator()(a1, a3);
  v20 = v6;
  v7 = (_QWORD *)(a1 + 24);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(
    a1 + 24,
    &v17,
    &v20);
  while ( 1 )
  {
    v8 = v17;
    if ( v17 == v18 )
      break;
    if ( (unsigned __int8)xpsrdr::KeyBrush::operator==(a3, v17[5] + 2) )
    {
      std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
        v9 + 72,
        a3 + 56);
      *(_QWORD *)a2 = v8[5];
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(&v17);
  }
  xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::resize(a1);
  v10 = (__int64 **)(a1 + 8);
  if ( v10[1] == (__int64 *)0x276276276276276LL )
    std::_Xlength_error("list too long");
  v11 = **v10;
  v17 = v10;
  v18 = 0;
  v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x68u);
  std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>>>::construct<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>> const &>(
    v13,
    v12 + 16,
    a3,
    v12);
  v10[1] = (__int64 *)((char *)v10[1] + 1);
  v14 = *(_QWORD **)(v11 + 8);
  *v15 = v11;
  v15[1] = v14;
  v18 = 0;
  *(_QWORD *)(v11 + 8) = v15;
  *v14 = v15;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>>>(&v17);
  v17 = (_QWORD **)v6;
  v18 = (_QWORD **)**v10;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(
    v7,
    (__int64)v19,
    (__int64)&v17);
  *(_QWORD *)a2 = **v10;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800b5924  mov     [rsp-28h+arg_8], rbx
0x1800b5929  mov     [rsp-28h+arg_10], rsi
0x1800b592e  push    rbp
0x1800b592f  push    rdi
0x1800b5930  push    r12
0x1800b5932  push    r14
0x1800b5934  push    r15
0x1800b5936  mov     rbp, rsp
0x1800b5939  sub     rsp, 40h
0x1800b593d  mov     r14, r8
0x1800b5940  mov     rdi, rdx
0x1800b5943  mov     rsi, rcx
0x1800b5946  mov     rdx, r8
0x1800b5949  call    ??R?$Hash@UKeyBrush@xpsrdr@@@xpsrdr@@QEBA_KAEBUKeyBrush@1@@Z; xpsrdr::Hash<xpsrdr::KeyBrush>::operator()(xpsrdr::KeyBrush const &)
0x1800b594e  mov     r15, rax
0x1800b5951  mov     [rbp+arg_0], rax
0x1800b5955  lea     r12, [rsi+18h]
0x1800b5959  lea     r8, [rbp+arg_0]
0x1800b595d  lea     rdx, [rbp+var_20]
0x1800b5961  mov     rcx, r12
0x1800b5964  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x1800b5969  mov     rbx, [rbp+var_20]
0x1800b596d  cmp     rbx, [rbp+var_18]
0x1800b5971  jz      short loc_1800B59AF
0x1800b5973  mov     r8, [rbx+28h]
0x1800b5977  lea     rdx, [r8+10h]
0x1800b597b  mov     rcx, r14
0x1800b597e  call    ??8KeyBrush@xpsrdr@@QEBA_NAEBU01@@Z; xpsrdr::KeyBrush::operator==(xpsrdr::KeyBrush const &)
0x1800b5983  test    al, al
0x1800b5985  jnz     short loc_1800B5992
0x1800b5987  lea     rcx, [rbp+var_20]
0x1800b598b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800b5990  jmp     short loc_1800B5969
0x1800b5992  lea     rdx, [r14+38h]
0x1800b5996  lea     rcx, [r8+48h]
0x1800b599a  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x1800b599f  mov     rax, [rbx+28h]
0x1800b59a3  mov     [rdi], rax
0x1800b59a6  mov     byte ptr [rdi+8], 0
0x1800b59aa  jmp     loc_1800B5A5B
0x1800b59af  movss   xmm1, dword ptr [rsi]
0x1800b59b3  mov     rcx, rsi
0x1800b59b6  call    ?resize@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::resize(float)
0x1800b59bb  add     rsi, 8
0x1800b59bf  mov     rax, 276276276276276h
0x1800b59c9  cmp     [rsi+8], rax
0x1800b59cd  jnz     short loc_1800B59DD
0x1800b59cf  lea     rcx, aListTooLong; "list too long"
0x1800b59d6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b59dd  mov     rax, [rsi]
0x1800b59e0  mov     rbx, [rax]
0x1800b59e3  mov     [rbp+var_20], rsi
0x1800b59e7  mov     [rbp+var_18], 0
0x1800b59ef  mov     ecx, 68h ; 'h'
0x1800b59f4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800b59f9  mov     r9, rax
0x1800b59fc  lea     rdx, [rax+10h]
0x1800b5a00  mov     r8, r14
0x1800b5a03  call    ??$construct@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>>>::construct<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>> const &>(std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>> &,std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>> * const,std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>> const &)
0x1800b5a08  nop
0x1800b5a09  inc     qword ptr [rsi+8]
0x1800b5a0d  mov     rdx, [rbx+8]
0x1800b5a11  mov     [r9], rbx
0x1800b5a14  mov     [r9+8], rdx
0x1800b5a18  mov     [rbp+var_18], 0
0x1800b5a20  mov     [rbx+8], r9
0x1800b5a24  mov     [rdx], r9
0x1800b5a27  lea     rcx, [rbp+var_20]
0x1800b5a2b  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>,void *>>>(void)
0x1800b5a30  mov     [rbp+var_20], r15
0x1800b5a34  mov     rax, [rsi]
0x1800b5a37  mov     rdx, [rax]
0x1800b5a3a  mov     [rbp+var_18], rdx
0x1800b5a3e  lea     r8, [rbp+var_20]
0x1800b5a42  lea     rdx, [rbp+var_10]
0x1800b5a46  mov     rcx, r12
0x1800b5a49  call    ??$_Emplace@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>> &&)
0x1800b5a4e  mov     rax, [rsi]
0x1800b5a51  mov     rcx, [rax]
0x1800b5a54  mov     [rdi], rcx
0x1800b5a57  mov     byte ptr [rdi+8], 1
0x1800b5a5b  mov     rax, rdi
0x1800b5a5e  lea     r11, [rsp+40h+var_s0]
0x1800b5a63  mov     rbx, [r11+38h]
0x1800b5a67  mov     rsi, [r11+40h]
0x1800b5a6b  mov     rsp, r11
0x1800b5a6e  pop     r15
0x1800b5a70  pop     r14
0x1800b5a72  pop     r12
0x1800b5a74  pop     rdi
0x1800b5a75  pop     rbp
0x1800b5a76  retn
```
