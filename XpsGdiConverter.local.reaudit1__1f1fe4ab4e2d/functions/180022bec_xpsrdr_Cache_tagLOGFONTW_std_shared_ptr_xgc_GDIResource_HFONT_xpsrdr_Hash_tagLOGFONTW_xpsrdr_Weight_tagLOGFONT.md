# xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::find(tagLOGFONTW const &)

- ea: `0x180022bec`
- end: `0x180022c98`
- name: `?find@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBUtagLOGFONTW@@@Z`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001de6c`
- `0x18001dff0`

## callees

- `0x18000e9b0`
- `0x18001de1c`
- `0x18001df50`
- `0x18001df68`
- `0x18001e174`
- `0x1800229e8`
- `0x180022a34`
- `0x180022bec`
- `0x1800231c8`

## pseudocode

```c
_QWORD *__fastcall xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::find(
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

  v13 = xpsrdr::Hash<tagLOGFONTW>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v12,
    &v13);
  while ( v12[0] != v12[1] )
  {
    v7 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v12)
                   + 8);
    v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v7);
    if ( (unsigned __int8)operator==(a3, v8) )
    {
      std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::splice(
        a1 + 8,
        **(_QWORD **)(a1 + 8),
        a1 + 8,
        *v7);
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
0x180022bec  push    rbx
0x180022bee  push    rbp
0x180022bef  push    rsi
0x180022bf0  push    rdi
0x180022bf1  sub     rsp, 38h
0x180022bf5  mov     rdi, rdx
0x180022bf8  mov     rbp, r8
0x180022bfb  mov     rdx, r8
0x180022bfe  mov     rbx, rcx
0x180022c01  call    ??R?$Hash@UtagLOGFONTW@@@xpsrdr@@QEBA_KAEBUtagLOGFONTW@@@Z; xpsrdr::Hash<tagLOGFONTW>::operator()(tagLOGFONTW const &)
0x180022c06  lea     rcx, [rbx+18h]
0x180022c0a  mov     [rsp+58h+arg_0], rax
0x180022c0f  lea     r8, [rsp+58h+arg_0]
0x180022c14  lea     rdx, [rsp+58h+var_38]
0x180022c19  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180022c1e  mov     rax, [rsp+58h+var_30]
0x180022c23  cmp     [rsp+58h+var_38], rax
0x180022c28  jz      short loc_180022C81
0x180022c2a  lea     rcx, [rsp+58h+var_38]
0x180022c2f  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180022c34  lea     rsi, [rax+8]
0x180022c38  mov     rcx, rsi
0x180022c3b  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180022c40  mov     rdx, rax
0x180022c43  mov     rcx, rbp
0x180022c46  call    ??8@YA_NAEBUtagLOGFONTW@@0@Z; operator==(tagLOGFONTW const &,tagLOGFONTW const &)
0x180022c4b  test    al, al
0x180022c4d  jnz     short loc_180022C5B
0x180022c4f  lea     rcx, [rsp+58h+var_38]
0x180022c54  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180022c59  jmp     short loc_180022C1E
0x180022c5b  mov     rdx, [rbx+8]
0x180022c5f  lea     r8, [rbx+8]
0x180022c63  mov     r9, [rsi]
0x180022c66  lea     rcx, [rbx+8]
0x180022c6a  mov     rdx, [rdx]
0x180022c6d  call    ?splice@?$list@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@2@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@2@AEAV12@0@Z; std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::splice(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>>>,std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>> &,std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>>>)
0x180022c72  mov     rax, [rbx+8]
0x180022c76  mov     rcx, [rax]
0x180022c79  mov     [rsi], rcx
0x180022c7c  mov     [rdi], rcx
0x180022c7f  jmp     short loc_180022C8C
0x180022c81  mov     rdx, rdi
0x180022c84  mov     rcx, rbx
0x180022c87  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180022c8c  mov     rax, rdi
0x180022c8f  add     rsp, 38h
0x180022c93  pop     rdi
0x180022c94  pop     rsi
0x180022c95  pop     rbp
0x180022c96  pop     rbx
0x180022c97  retn
```
