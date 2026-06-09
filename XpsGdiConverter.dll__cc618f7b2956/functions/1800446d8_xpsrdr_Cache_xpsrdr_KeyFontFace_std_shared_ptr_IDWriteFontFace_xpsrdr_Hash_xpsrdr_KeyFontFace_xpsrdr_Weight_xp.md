# xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(xpsrdr::KeyFontFace const &)

- ea: `0x1800446d8`
- end: `0x180044784`
- name: `?find@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@AEBUKeyFontFace@2@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180043174`
- `0x1800432dc`

## callees

- `0x18000e9b0`
- `0x18001df50`
- `0x18001df68`
- `0x1800229e8`
- `0x180022a34`
- `0x180032738`
- `0x180043130`
- `0x180043244`
- `0x1800446d8`

## pseudocode

```c
_QWORD *__fastcall xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // r8
  __int64 *v7; // rsi
  __int64 v8; // rax
  __int64 *v9; // rax
  __int64 v10; // rcx
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = xpsrdr::Hash<xpsrdr::KeyFontFace>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v12,
    &v13);
  while ( v12[0] != v12[1] )
  {
    v7 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v12)
                   + 8);
    v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v7);
    if ( (unsigned __int8)xpsrdr::KeyFontFace::operator==(a3, v8) )
    {
      std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::splice(a1 + 8, **(_QWORD **)(a1 + 8), a1 + 8, *v7);
      v9 = *(__int64 **)(a1 + 8);
      v10 = *v9;
      *v7 = *v9;
      *a2 = v10;
      return a2;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v12);
  }
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
    a1,
    (__int64)a2,
    v6);
  return a2;
}

```

## disassembly

```asm
0x1800446d8  push    rbx
0x1800446da  push    rbp
0x1800446db  push    rsi
0x1800446dc  push    rdi
0x1800446dd  sub     rsp, 38h
0x1800446e1  mov     rdi, rdx
0x1800446e4  mov     rbp, r8
0x1800446e7  mov     rdx, r8
0x1800446ea  mov     rbx, rcx
0x1800446ed  call    ??R?$Hash@UKeyFontFace@xpsrdr@@@xpsrdr@@QEBA_KAEBUKeyFontFace@1@@Z; xpsrdr::Hash<xpsrdr::KeyFontFace>::operator()(xpsrdr::KeyFontFace const &)
0x1800446f2  lea     rcx, [rbx+18h]
0x1800446f6  mov     [rsp+58h+arg_0], rax
0x1800446fb  lea     r8, [rsp+58h+arg_0]
0x180044700  lea     rdx, [rsp+58h+var_38]
0x180044705  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x18004470a  mov     rax, [rsp+58h+var_30]
0x18004470f  cmp     [rsp+58h+var_38], rax
0x180044714  jz      short loc_18004476D
0x180044716  lea     rcx, [rsp+58h+var_38]
0x18004471b  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180044720  lea     rsi, [rax+8]
0x180044724  mov     rcx, rsi
0x180044727  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18004472c  mov     rdx, rax
0x18004472f  mov     rcx, rbp
0x180044732  call    ??8KeyFontFace@xpsrdr@@QEBA_NAEBU01@@Z; xpsrdr::KeyFontFace::operator==(xpsrdr::KeyFontFace const &)
0x180044737  test    al, al
0x180044739  jnz     short loc_180044747
0x18004473b  lea     rcx, [rsp+58h+var_38]
0x180044740  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180044745  jmp     short loc_18004470A
0x180044747  mov     rdx, [rbx+8]
0x18004474b  lea     r8, [rbx+8]
0x18004474f  mov     r9, [rsi]
0x180044752  lea     rcx, [rbx+8]
0x180044756  mov     rdx, [rdx]
0x180044759  call    ?splice@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@2@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@2@AEAV12@0@Z; std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::splice(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>,std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>> &,std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>)
0x18004475e  mov     rax, [rbx+8]
0x180044762  mov     rcx, [rax]
0x180044765  mov     [rsi], rcx
0x180044768  mov     [rdi], rcx
0x18004476b  jmp     short loc_180044778
0x18004476d  mov     rdx, rdi
0x180044770  mov     rcx, rbx
0x180044773  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180044778  mov     rax, rdi
0x18004477b  add     rsp, 38h
0x18004477f  pop     rdi
0x180044780  pop     rsi
0x180044781  pop     rbp
0x180044782  pop     rbx
0x180044783  retn
```
