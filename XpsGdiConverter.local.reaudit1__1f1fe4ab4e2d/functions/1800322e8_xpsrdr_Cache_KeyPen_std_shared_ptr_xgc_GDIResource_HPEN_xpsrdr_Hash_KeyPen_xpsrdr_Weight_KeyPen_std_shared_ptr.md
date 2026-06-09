# xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::erase(KeyPen const &)

- ea: `0x1800322e8`
- end: `0x1800323a1`
- name: `?erase@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAAXAEBUKeyPen@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800326c4`

## callees

- `0x18000e9b0`
- `0x18001ca24`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x18003147c`
- `0x180031734`
- `0x1800322e8`
- `0x1800323a8`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::erase(
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

  v10 = xpsrdr::Hash<KeyPen>::operator()(a1, a2);
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
      if ( (unsigned __int8)KeyPen::operator==(a2, v7) )
      {
        std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::erase(a1 + 8, &v10, *v6);
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
0x1800322e8  mov     [rsp+arg_8], rbx
0x1800322ed  mov     [rsp+arg_10], rbp
0x1800322f2  push    rsi
0x1800322f3  push    rdi
0x1800322f4  push    r14
0x1800322f6  sub     rsp, 30h
0x1800322fa  mov     rbp, rdx
0x1800322fd  mov     rdi, rcx
0x180032300  call    ??R?$Hash@UKeyPen@@@xpsrdr@@QEBA_KAEBUKeyPen@@@Z; xpsrdr::Hash<KeyPen>::operator()(KeyPen const &)
0x180032305  lea     r8, [rsp+48h+arg_0]
0x18003230a  mov     [rsp+48h+arg_0], rax
0x18003230f  lea     rdx, [rsp+48h+var_28]
0x180032314  lea     rcx, [rdi+18h]
0x180032318  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x18003231d  mov     rax, [rsp+48h+var_20]
0x180032322  mov     rbx, [rsp+48h+var_28]
0x180032327  cmp     rbx, rax
0x18003232a  jz      short loc_18003238E
0x18003232c  cmp     rbx, rax
0x18003232f  jz      short loc_18003238E
0x180032331  lea     rcx, [rsp+48h+var_28]
0x180032336  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x18003233b  lea     r14, [rax+8]
0x18003233f  mov     rcx, r14
0x180032342  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180032347  mov     rdx, rax
0x18003234a  mov     rcx, rbp
0x18003234d  call    ??8KeyPen@@QEBA_NAEBU0@@Z; KeyPen::operator==(KeyPen const &)
0x180032352  test    al, al
0x180032354  jnz     short loc_18003236C
0x180032356  lea     rcx, [rsp+48h+var_28]
0x18003235b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180032360  mov     rax, [rsp+48h+var_20]
0x180032365  mov     rbx, [rsp+48h+var_28]
0x18003236a  jmp     short loc_18003232C
0x18003236c  mov     r8, [r14]
0x18003236f  lea     rcx, [rdi+8]
0x180032373  lea     rdx, [rsp+48h+arg_0]
0x180032378  call    ?erase@?$list@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@2@@Z; std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>)
0x18003237d  mov     r8, rbx
0x180032380  lea     rdx, [rsp+48h+arg_0]
0x180032385  lea     rcx, [rdi+18h]
0x180032389  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>)
0x18003238e  mov     rbx, [rsp+48h+arg_8]
0x180032393  mov     rbp, [rsp+48h+arg_10]
0x180032398  add     rsp, 30h
0x18003239c  pop     r14
0x18003239e  pop     rdi
0x18003239f  pop     rsi
0x1800323a0  retn
```
