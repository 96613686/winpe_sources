# xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::find(KeyPen const &)

- ea: `0x1800323f0`
- end: `0x18003249c`
- name: `?find@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBUKeyPen@@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800314b8`
- `0x180031574`

## callees

- `0x18000e9b0`
- `0x18001df50`
- `0x18001df68`
- `0x1800229e8`
- `0x180022a34`
- `0x18003147c`
- `0x180031734`
- `0x1800323f0`
- `0x180032738`

## pseudocode

```c
_QWORD *__fastcall xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::find(
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

  v13 = xpsrdr::Hash<KeyPen>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v12,
    &v13);
  while ( v12[0] != v12[1] )
  {
    v7 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v12)
                   + 8);
    v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v7);
    if ( (unsigned __int8)KeyPen::operator==(a3, v8) )
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
0x1800323f0  push    rbx
0x1800323f2  push    rbp
0x1800323f3  push    rsi
0x1800323f4  push    rdi
0x1800323f5  sub     rsp, 38h
0x1800323f9  mov     rdi, rdx
0x1800323fc  mov     rbp, r8
0x1800323ff  mov     rdx, r8
0x180032402  mov     rbx, rcx
0x180032405  call    ??R?$Hash@UKeyPen@@@xpsrdr@@QEBA_KAEBUKeyPen@@@Z; xpsrdr::Hash<KeyPen>::operator()(KeyPen const &)
0x18003240a  lea     rcx, [rbx+18h]
0x18003240e  mov     [rsp+58h+arg_0], rax
0x180032413  lea     r8, [rsp+58h+arg_0]
0x180032418  lea     rdx, [rsp+58h+var_38]
0x18003241d  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180032422  mov     rax, [rsp+58h+var_30]
0x180032427  cmp     [rsp+58h+var_38], rax
0x18003242c  jz      short loc_180032485
0x18003242e  lea     rcx, [rsp+58h+var_38]
0x180032433  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180032438  lea     rsi, [rax+8]
0x18003243c  mov     rcx, rsi
0x18003243f  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180032444  mov     rdx, rax
0x180032447  mov     rcx, rbp
0x18003244a  call    ??8KeyPen@@QEBA_NAEBU0@@Z; KeyPen::operator==(KeyPen const &)
0x18003244f  test    al, al
0x180032451  jnz     short loc_18003245F
0x180032453  lea     rcx, [rsp+58h+var_38]
0x180032458  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18003245d  jmp     short loc_180032422
0x18003245f  mov     rdx, [rbx+8]
0x180032463  lea     r8, [rbx+8]
0x180032467  mov     r9, [rsi]
0x18003246a  lea     rcx, [rbx+8]
0x18003246e  mov     rdx, [rdx]
0x180032471  call    ?splice@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@2@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@2@AEAV12@0@Z; std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::splice(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>,std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>> &,std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>)
0x180032476  mov     rax, [rbx+8]
0x18003247a  mov     rcx, [rax]
0x18003247d  mov     [rsi], rcx
0x180032480  mov     [rdi], rcx
0x180032483  jmp     short loc_180032490
0x180032485  mov     rdx, rdi
0x180032488  mov     rcx, rbx
0x18003248b  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180032490  mov     rax, rdi
0x180032493  add     rsp, 38h
0x180032497  pop     rdi
0x180032498  pop     rsi
0x180032499  pop     rbp
0x18003249a  pop     rbx
0x18003249b  retn
```
