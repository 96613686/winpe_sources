# xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::insert(std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>> const &)

- ea: `0x180022d68`
- end: `0x180022e75`
- name: `?insert@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@4@@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001de6c`

## callees

- `0x18000e9b0`
- `0x1800184e8`
- `0x18001ba90`
- `0x18001ca74`
- `0x18001cb04`
- `0x18001de1c`
- `0x18001df50`
- `0x18001df68`
- `0x18001e174`
- `0x180022a34`
- `0x180022d68`
- `0x180022f00`
- `0x1800230e0`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::insert(
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

  v14 = xpsrdr::Hash<tagLOGFONTW>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v13,
    &v14);
  while ( v13[0] != v13[1] )
  {
    v6 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v13)
                   + 8);
    v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
    if ( (unsigned __int8)operator==(a3, v7) )
    {
      v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
      std::shared_ptr<ID2D1Brush>::operator=(v8 + 96, v9);
      v15 = *v6;
      LOBYTE(v14) = 0;
      goto LABEL_7;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v13);
  }
  xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::resize(a1);
  std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::push_front(a1 + 8, a3);
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
0x180022d68  mov     [rsp-28h+arg_8], rbx
0x180022d6d  push    rbp
0x180022d6e  push    rsi
0x180022d6f  push    rdi
0x180022d70  push    r14
0x180022d72  push    r15
0x180022d74  mov     rbp, rsp
0x180022d77  sub     rsp, 30h
0x180022d7b  mov     rsi, rdx
0x180022d7e  mov     rdi, r8
0x180022d81  mov     rdx, r8
0x180022d84  mov     r14, rcx
0x180022d87  call    ??R?$Hash@UtagLOGFONTW@@@xpsrdr@@QEBA_KAEBUtagLOGFONTW@@@Z; xpsrdr::Hash<tagLOGFONTW>::operator()(tagLOGFONTW const &)
0x180022d8c  lea     r8, [rbp+arg_0]
0x180022d90  mov     [rbp+arg_0], rax
0x180022d94  lea     rdx, [rbp+var_10]
0x180022d98  lea     rcx, [r14+18h]
0x180022d9c  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180022da1  mov     rax, [rbp+var_8]
0x180022da5  cmp     [rbp+var_10], rax
0x180022da9  jz      short loc_180022DFC
0x180022dab  lea     rcx, [rbp+var_10]
0x180022daf  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180022db4  lea     rbx, [rax+8]
0x180022db8  mov     rcx, rbx
0x180022dbb  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180022dc0  mov     rdx, rax
0x180022dc3  mov     rcx, rdi
0x180022dc6  call    ??8@YA_NAEBUtagLOGFONTW@@0@Z; operator==(tagLOGFONTW const &,tagLOGFONTW const &)
0x180022dcb  test    al, al
0x180022dcd  jnz     short loc_180022DDA
0x180022dcf  lea     rcx, [rbp+var_10]
0x180022dd3  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180022dd8  jmp     short loc_180022DA1
0x180022dda  mov     rcx, rbx
0x180022ddd  lea     rdx, [rdi+60h]
0x180022de1  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180022de6  lea     rcx, [rax+60h]
0x180022dea  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180022def  mov     rax, [rbx]
0x180022df2  mov     [rbp+arg_10], rax
0x180022df6  mov     byte ptr [rbp+arg_0], 0
0x180022dfa  jmp     short loc_180022E51
0x180022dfc  movss   xmm1, dword ptr [r14]
0x180022e01  mov     rcx, r14
0x180022e04  call    ?resize@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::resize(float)
0x180022e09  lea     rbx, [r14+8]
0x180022e0d  mov     rdx, rdi
0x180022e10  mov     rcx, rbx
0x180022e13  call    ?push_front@?$list@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@2@@std@@QEAAXAEBU?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@2@@Z; std::list<std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::push_front(std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>> const &)
0x180022e18  mov     rax, [rbx]
0x180022e1b  lea     r8, [rbp+arg_10]
0x180022e1f  lea     rcx, [rbp+var_10]
0x180022e23  mov     rdx, [rax]
0x180022e26  mov     [rbp+arg_10], rdx
0x180022e2a  lea     rdx, [rbp+arg_0]
0x180022e2e  call    ??$?0AEA_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@$0A@@?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@QEAA@AEA_K$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@1@@Z; std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(unsigned __int64 &,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>> &&)
0x180022e33  mov     r8, rax
0x180022e36  lea     rdx, [rbp+arg_0]
0x180022e3a  lea     rcx, [r14+18h]
0x180022e3e  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>> &&)
0x180022e43  mov     rax, [rbx]
0x180022e46  mov     byte ptr [rbp+arg_0], 1
0x180022e4a  mov     rcx, [rax]
0x180022e4d  mov     [rbp+arg_10], rcx
0x180022e51  lea     r8, [rbp+arg_0]
0x180022e55  mov     rcx, rsi
0x180022e58  lea     rdx, [rbp+arg_10]
0x180022e5c  call    ??$make_pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@YA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@0@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@0@$$QEA_N@Z; std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>> &&,bool &&)
0x180022e61  mov     rbx, [rsp+30h+arg_8]
0x180022e66  mov     rax, rsi
0x180022e69  add     rsp, 30h
0x180022e6d  pop     r15
0x180022e6f  pop     r14
0x180022e71  pop     rdi
0x180022e72  pop     rsi
0x180022e73  pop     rbp
0x180022e74  retn
```
