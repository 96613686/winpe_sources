# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData>>::erase(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18003b4dc`
- end: `0x18003b595`
- name: `?erase@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180037aa8`
- `0x180046acc`

## callees

- `0x18000e9b0`
- `0x18001be30`
- `0x18001ca24`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x180035330`
- `0x18003b4dc`
- `0x18003b59c`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::erase(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  _QWORD *v6; // r14
  __int64 v7; // rax
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v10 = xpsrdr::Hash<std::wstring>::operator()(a1, a2);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    &v8,
    &v10);
  result = v9;
  v5 = v8;
  if ( v8 != v9 )
  {
    while ( v5 != result )
    {
      v6 = (_QWORD *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(&v8)
                    + 8);
      v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
      if ( (unsigned __int8)std::operator==<wchar_t>(a2, v7) )
      {
        std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::erase(a1 + 8, &v10, *v6);
        return std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>,0>(
                 a1 + 24,
                 &v10,
                 v5);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v8);
      result = v9;
      v5 = v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003b4dc  mov     [rsp+arg_8], rbx
0x18003b4e1  mov     [rsp+arg_10], rbp
0x18003b4e6  push    rsi
0x18003b4e7  push    rdi
0x18003b4e8  push    r14
0x18003b4ea  sub     rsp, 30h
0x18003b4ee  mov     rbp, rdx
0x18003b4f1  mov     rdi, rcx
0x18003b4f4  call    ??R?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Hash<std::wstring>::operator()(std::wstring const &)
0x18003b4f9  lea     r8, [rsp+48h+arg_0]
0x18003b4fe  mov     [rsp+48h+arg_0], rax
0x18003b503  lea     rdx, [rsp+48h+var_28]
0x18003b508  lea     rcx, [rdi+18h]
0x18003b50c  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x18003b511  mov     rax, [rsp+48h+var_20]
0x18003b516  mov     rbx, [rsp+48h+var_28]
0x18003b51b  cmp     rbx, rax
0x18003b51e  jz      short loc_18003B582
0x18003b520  cmp     rbx, rax
0x18003b523  jz      short loc_18003B582
0x18003b525  lea     rcx, [rsp+48h+var_28]
0x18003b52a  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x18003b52f  lea     r14, [rax+8]
0x18003b533  mov     rcx, r14
0x18003b536  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18003b53b  mov     rdx, rax
0x18003b53e  mov     rcx, rbp
0x18003b541  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x18003b546  test    al, al
0x18003b548  jnz     short loc_18003B560
0x18003b54a  lea     rcx, [rsp+48h+var_28]
0x18003b54f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18003b554  mov     rax, [rsp+48h+var_20]
0x18003b559  mov     rbx, [rsp+48h+var_28]
0x18003b55e  jmp     short loc_18003B520
0x18003b560  mov     r8, [r14]
0x18003b563  lea     rcx, [rdi+8]
0x18003b567  lea     rdx, [rsp+48h+arg_0]
0x18003b56c  call    ?erase@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@2@@Z; std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>)
0x18003b571  mov     r8, rbx
0x18003b574  lea     rdx, [rsp+48h+arg_0]
0x18003b579  lea     rcx, [rdi+18h]
0x18003b57d  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>)
0x18003b582  mov     rbx, [rsp+48h+arg_8]
0x18003b587  mov     rbp, [rsp+48h+arg_10]
0x18003b58c  add     rsp, 30h
0x18003b590  pop     r14
0x18003b592  pop     rdi
0x18003b593  pop     rsi
0x18003b594  retn
```
