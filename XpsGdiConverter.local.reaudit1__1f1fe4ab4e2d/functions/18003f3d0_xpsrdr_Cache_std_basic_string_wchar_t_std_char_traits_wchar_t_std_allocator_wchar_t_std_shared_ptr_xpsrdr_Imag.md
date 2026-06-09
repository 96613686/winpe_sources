# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::Image>>>::insert(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::shared_ptr<xpsrdr::Image>> const &)

- ea: `0x18003f3d0`
- end: `0x18003f4dd`
- name: `?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@4@@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18003ebd8`

## callees

- `0x18000e9b0`
- `0x1800184e8`
- `0x18001ba90`
- `0x18001be30`
- `0x18001ca74`
- `0x18001cb04`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x180035330`
- `0x180037014`
- `0x18003f3d0`
- `0x18003f4e4`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 *v11; // rax
  _QWORD v13[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+30h] BYREF
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF

  v14 = xpsrdr::Hash<std::wstring>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v13,
    &v14);
  while ( v13[0] != v13[1] )
  {
    v6 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v13)
                   + 8);
    v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
    if ( (unsigned __int8)std::operator==<wchar_t>(a3, v7) )
    {
      v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
      std::shared_ptr<ID2D1Brush>::operator=(v8 + 32, v9);
      v15 = *v6;
      LOBYTE(v14) = 0;
      goto LABEL_7;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v13);
  }
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::resize(a1);
  std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>::push_front(a1 + 8, a3);
  v15 = **(_QWORD **)(a1 + 8);
  v10 = std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(
          v13,
          &v14,
          &v15);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(
    a1 + 24,
    &v14,
    v10);
  v11 = *(__int64 **)(a1 + 8);
  LOBYTE(v14) = 1;
  v15 = *v11;
LABEL_7:
  std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(
    a2,
    &v15,
    &v14);
  return a2;
}

```

## disassembly

```asm
0x18003f3d0  mov     [rsp-28h+arg_8], rbx
0x18003f3d5  push    rbp
0x18003f3d6  push    rsi
0x18003f3d7  push    rdi
0x18003f3d8  push    r14
0x18003f3da  push    r15
0x18003f3dc  mov     rbp, rsp
0x18003f3df  sub     rsp, 30h
0x18003f3e3  mov     rsi, rdx
0x18003f3e6  mov     rdi, r8
0x18003f3e9  mov     rdx, r8
0x18003f3ec  mov     r14, rcx
0x18003f3ef  call    ??R?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Hash<std::wstring>::operator()(std::wstring const &)
0x18003f3f4  lea     r8, [rbp+arg_0]
0x18003f3f8  mov     [rbp+arg_0], rax
0x18003f3fc  lea     rdx, [rbp+var_10]
0x18003f400  lea     rcx, [r14+18h]
0x18003f404  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x18003f409  mov     rax, [rbp+var_8]
0x18003f40d  cmp     [rbp+var_10], rax
0x18003f411  jz      short loc_18003F464
0x18003f413  lea     rcx, [rbp+var_10]
0x18003f417  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x18003f41c  lea     rbx, [rax+8]
0x18003f420  mov     rcx, rbx
0x18003f423  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18003f428  mov     rdx, rax
0x18003f42b  mov     rcx, rdi
0x18003f42e  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x18003f433  test    al, al
0x18003f435  jnz     short loc_18003F442
0x18003f437  lea     rcx, [rbp+var_10]
0x18003f43b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18003f440  jmp     short loc_18003F409
0x18003f442  mov     rcx, rbx
0x18003f445  lea     rdx, [rdi+20h]
0x18003f449  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18003f44e  lea     rcx, [rax+20h]
0x18003f452  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18003f457  mov     rax, [rbx]
0x18003f45a  mov     [rbp+arg_10], rax
0x18003f45e  mov     byte ptr [rbp+arg_0], 0
0x18003f462  jmp     short loc_18003F4B9
0x18003f464  movss   xmm1, dword ptr [r14]
0x18003f469  mov     rcx, r14
0x18003f46c  call    ?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::resize(float)
0x18003f471  lea     rbx, [r14+8]
0x18003f475  mov     rdx, rdi
0x18003f478  mov     rcx, rbx
0x18003f47b  call    ?push_front@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@2@@std@@QEAAXAEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@2@@Z; std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>::push_front(std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> const &)
0x18003f480  mov     rax, [rbx]
0x18003f483  lea     r8, [rbp+arg_10]
0x18003f487  lea     rcx, [rbp+var_10]
0x18003f48b  mov     rdx, [rax]
0x18003f48e  mov     [rbp+arg_10], rdx
0x18003f492  lea     rdx, [rbp+arg_0]
0x18003f496  call    ??$?0AEA_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@$0A@@?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@QEAA@AEA_K$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@1@@Z; std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(unsigned __int64 &,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>> &&)
0x18003f49b  mov     r8, rax
0x18003f49e  lea     rdx, [rbp+arg_0]
0x18003f4a2  lea     rcx, [r14+18h]
0x18003f4a6  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>> &&)
0x18003f4ab  mov     rax, [rbx]
0x18003f4ae  mov     byte ptr [rbp+arg_0], 1
0x18003f4b2  mov     rcx, [rax]
0x18003f4b5  mov     [rbp+arg_10], rcx
0x18003f4b9  lea     r8, [rbp+arg_0]
0x18003f4bd  mov     rcx, rsi
0x18003f4c0  lea     rdx, [rbp+arg_10]
0x18003f4c4  call    ??$make_pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@YA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@0@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@0@$$QEA_N@Z; std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>> &&,bool &&)
0x18003f4c9  mov     rbx, [rsp+30h+arg_8]
0x18003f4ce  mov     rax, rsi
0x18003f4d1  add     rsp, 30h
0x18003f4d5  pop     r15
0x18003f4d7  pop     r14
0x18003f4d9  pop     rdi
0x18003f4da  pop     rsi
0x18003f4db  pop     rbp
0x18003f4dc  retn
```
