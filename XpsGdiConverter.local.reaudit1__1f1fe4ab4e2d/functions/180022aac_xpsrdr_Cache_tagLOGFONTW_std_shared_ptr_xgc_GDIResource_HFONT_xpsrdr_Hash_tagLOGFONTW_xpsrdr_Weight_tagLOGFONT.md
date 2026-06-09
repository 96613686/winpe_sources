# xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::erase(tagLOGFONTW const &)

- ea: `0x180022aac`
- end: `0x180022b65`
- name: `?erase@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAAXAEBUtagLOGFONTW@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800230e0`

## callees

- `0x18000e9b0`
- `0x18001ca24`
- `0x18001de1c`
- `0x18001df50`
- `0x18001df68`
- `0x18001e174`
- `0x180022a34`
- `0x180022aac`
- `0x180022ba4`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::erase(
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

  v10 = xpsrdr::Hash<tagLOGFONTW>::operator()(a1, a2);
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
      if ( (unsigned __int8)operator==(a2, v7) )
      {
        std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::erase(a1 + 8, &v10, *v6);
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
0x180022aac  mov     [rsp+arg_8], rbx
0x180022ab1  mov     [rsp+arg_10], rbp
0x180022ab6  push    rsi
0x180022ab7  push    rdi
0x180022ab8  push    r14
0x180022aba  sub     rsp, 30h
0x180022abe  mov     rbp, rdx
0x180022ac1  mov     rdi, rcx
0x180022ac4  call    ??R?$Hash@UtagLOGFONTW@@@xpsrdr@@QEBA_KAEBUtagLOGFONTW@@@Z; xpsrdr::Hash<tagLOGFONTW>::operator()(tagLOGFONTW const &)
0x180022ac9  lea     r8, [rsp+48h+arg_0]
0x180022ace  mov     [rsp+48h+arg_0], rax
0x180022ad3  lea     rdx, [rsp+48h+var_28]
0x180022ad8  lea     rcx, [rdi+18h]
0x180022adc  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180022ae1  mov     rax, [rsp+48h+var_20]
0x180022ae6  mov     rbx, [rsp+48h+var_28]
0x180022aeb  cmp     rbx, rax
0x180022aee  jz      short loc_180022B52
0x180022af0  cmp     rbx, rax
0x180022af3  jz      short loc_180022B52
0x180022af5  lea     rcx, [rsp+48h+var_28]
0x180022afa  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180022aff  lea     r14, [rax+8]
0x180022b03  mov     rcx, r14
0x180022b06  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180022b0b  mov     rdx, rax
0x180022b0e  mov     rcx, rbp
0x180022b11  call    ??8@YA_NAEBUtagLOGFONTW@@0@Z; operator==(tagLOGFONTW const &,tagLOGFONTW const &)
0x180022b16  test    al, al
0x180022b18  jnz     short loc_180022B30
0x180022b1a  lea     rcx, [rsp+48h+var_28]
0x180022b1f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180022b24  mov     rax, [rsp+48h+var_20]
0x180022b29  mov     rbx, [rsp+48h+var_28]
0x180022b2e  jmp     short loc_180022AF0
0x180022b30  mov     r8, [r14]
0x180022b33  lea     rcx, [rdi+8]
0x180022b37  lea     rdx, [rsp+48h+arg_0]
0x180022b3c  call    ?erase@?$list@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@2@@Z; std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>>>)
0x180022b41  mov     r8, rbx
0x180022b44  lea     rdx, [rsp+48h+arg_0]
0x180022b49  lea     rcx, [rdi+18h]
0x180022b4d  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>)
0x180022b52  mov     rbx, [rsp+48h+arg_8]
0x180022b57  mov     rbp, [rsp+48h+arg_10]
0x180022b5c  add     rsp, 30h
0x180022b60  pop     r14
0x180022b62  pop     rdi
0x180022b63  pop     rsi
0x180022b64  retn
```
