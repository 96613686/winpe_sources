# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>>>::find(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180036e4c`
- end: `0x180036ef8`
- name: `?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `172`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180035264`
- `0x180035fa4`
- `0x18003ebd8`
- `0x18003edd0`

## callees

- `0x18000e9b0`
- `0x18001be30`
- `0x18001df50`
- `0x18001df68`
- `0x1800229e8`
- `0x180022a34`
- `0x180035330`
- `0x180036e4c`
- `0x180037130`

## pseudocode

```c
_QWORD *__fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(
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

  v13 = xpsrdr::Hash<std::wstring>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v12,
    &v13);
  while ( v12[0] != v12[1] )
  {
    v7 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v12)
                   + 8);
    v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v7);
    if ( (unsigned __int8)std::operator==<wchar_t>(a3, v8) )
    {
      std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>::splice(
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
0x180036e4c  push    rbx
0x180036e4e  push    rbp
0x180036e4f  push    rsi
0x180036e50  push    rdi
0x180036e51  sub     rsp, 38h
0x180036e55  mov     rdi, rdx
0x180036e58  mov     rbp, r8
0x180036e5b  mov     rdx, r8
0x180036e5e  mov     rbx, rcx
0x180036e61  call    ??R?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Hash<std::wstring>::operator()(std::wstring const &)
0x180036e66  lea     rcx, [rbx+18h]
0x180036e6a  mov     [rsp+58h+arg_0], rax
0x180036e6f  lea     r8, [rsp+58h+arg_0]
0x180036e74  lea     rdx, [rsp+58h+var_38]
0x180036e79  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180036e7e  mov     rax, [rsp+58h+var_30]
0x180036e83  cmp     [rsp+58h+var_38], rax
0x180036e88  jz      short loc_180036EE1
0x180036e8a  lea     rcx, [rsp+58h+var_38]
0x180036e8f  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180036e94  lea     rsi, [rax+8]
0x180036e98  mov     rcx, rsi
0x180036e9b  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180036ea0  mov     rdx, rax
0x180036ea3  mov     rcx, rbp
0x180036ea6  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x180036eab  test    al, al
0x180036ead  jnz     short loc_180036EBB
0x180036eaf  lea     rcx, [rsp+58h+var_38]
0x180036eb4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180036eb9  jmp     short loc_180036E7E
0x180036ebb  mov     rdx, [rbx+8]
0x180036ebf  lea     r8, [rbx+8]
0x180036ec3  mov     r9, [rsi]
0x180036ec6  lea     rcx, [rbx+8]
0x180036eca  mov     rdx, [rdx]
0x180036ecd  call    ?splice@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@2@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@2@AEAV12@0@Z; std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>::splice(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>> &,std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>)
0x180036ed2  mov     rax, [rbx+8]
0x180036ed6  mov     rcx, [rax]
0x180036ed9  mov     [rsi], rcx
0x180036edc  mov     [rdi], rcx
0x180036edf  jmp     short loc_180036EEC
0x180036ee1  mov     rdx, rdi
0x180036ee4  mov     rcx, rbx
0x180036ee7  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180036eec  mov     rax, rdi
0x180036eef  add     rsp, 38h
0x180036ef3  pop     rdi
0x180036ef4  pop     rsi
0x180036ef5  pop     rbp
0x180036ef6  pop     rbx
0x180036ef7  retn
```
