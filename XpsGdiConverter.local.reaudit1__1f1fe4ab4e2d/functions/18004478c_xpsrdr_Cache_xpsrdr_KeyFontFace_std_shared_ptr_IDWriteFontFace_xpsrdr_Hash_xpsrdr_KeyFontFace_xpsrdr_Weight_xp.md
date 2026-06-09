# xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::insert(std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &)

- ea: `0x18004478c`
- end: `0x180044899`
- name: `?insert@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@4@@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180043174`

## callees

- `0x18000e9b0`
- `0x1800184e8`
- `0x18001ba90`
- `0x18001ca74`
- `0x18001cb04`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x180043130`
- `0x180043244`
- `0x18004478c`
- `0x1800448a0`
- `0x18004492c`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::insert(
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

  v14 = xpsrdr::Hash<xpsrdr::KeyFontFace>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v13,
    &v14);
  while ( v13[0] != v13[1] )
  {
    v6 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v13)
                   + 8);
    v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
    if ( (unsigned __int8)xpsrdr::KeyFontFace::operator==(a3, v7) )
    {
      v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
      std::shared_ptr<ID2D1Brush>::operator=(v8 + 40, v9);
      v15 = *v6;
      LOBYTE(v14) = 0;
      goto LABEL_7;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v13);
  }
  xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::resize(a1);
  std::list<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>::push_front(a1 + 8, a3);
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
0x18004478c  mov     [rsp-28h+arg_8], rbx
0x180044791  push    rbp
0x180044792  push    rsi
0x180044793  push    rdi
0x180044794  push    r14
0x180044796  push    r15
0x180044798  mov     rbp, rsp
0x18004479b  sub     rsp, 30h
0x18004479f  mov     rsi, rdx
0x1800447a2  mov     rdi, r8
0x1800447a5  mov     rdx, r8
0x1800447a8  mov     r14, rcx
0x1800447ab  call    ??R?$Hash@UKeyFontFace@xpsrdr@@@xpsrdr@@QEBA_KAEBUKeyFontFace@1@@Z; xpsrdr::Hash<xpsrdr::KeyFontFace>::operator()(xpsrdr::KeyFontFace const &)
0x1800447b0  lea     r8, [rbp+arg_0]
0x1800447b4  mov     [rbp+arg_0], rax
0x1800447b8  lea     rdx, [rbp+var_10]
0x1800447bc  lea     rcx, [r14+18h]
0x1800447c0  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x1800447c5  mov     rax, [rbp+var_8]
0x1800447c9  cmp     [rbp+var_10], rax
0x1800447cd  jz      short loc_180044820
0x1800447cf  lea     rcx, [rbp+var_10]
0x1800447d3  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x1800447d8  lea     rbx, [rax+8]
0x1800447dc  mov     rcx, rbx
0x1800447df  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x1800447e4  mov     rdx, rax
0x1800447e7  mov     rcx, rdi
0x1800447ea  call    ??8KeyFontFace@xpsrdr@@QEBA_NAEBU01@@Z; xpsrdr::KeyFontFace::operator==(xpsrdr::KeyFontFace const &)
0x1800447ef  test    al, al
0x1800447f1  jnz     short loc_1800447FE
0x1800447f3  lea     rcx, [rbp+var_10]
0x1800447f7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800447fc  jmp     short loc_1800447C5
0x1800447fe  mov     rcx, rbx
0x180044801  lea     rdx, [rdi+28h]
0x180044805  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18004480a  lea     rcx, [rax+28h]
0x18004480e  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180044813  mov     rax, [rbx]
0x180044816  mov     [rbp+arg_10], rax
0x18004481a  mov     byte ptr [rbp+arg_0], 0
0x18004481e  jmp     short loc_180044875
0x180044820  movss   xmm1, dword ptr [r14]
0x180044825  mov     rcx, r14
0x180044828  call    ?resize@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::resize(float)
0x18004482d  lea     rbx, [r14+8]
0x180044831  mov     rdx, rdi
0x180044834  mov     rcx, rbx
0x180044837  call    ?push_front@?$list@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@2@@std@@QEAAXAEBU?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@Z; std::list<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>::push_front(std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &)
0x18004483c  mov     rax, [rbx]
0x18004483f  lea     r8, [rbp+arg_10]
0x180044843  lea     rcx, [rbp+var_10]
0x180044847  mov     rdx, [rax]
0x18004484a  mov     [rbp+arg_10], rdx
0x18004484e  lea     rdx, [rbp+arg_0]
0x180044852  call    ??$?0AEA_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@$0A@@?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@QEAA@AEA_K$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@1@@Z; std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(unsigned __int64 &,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>> &&)
0x180044857  mov     r8, rax
0x18004485a  lea     rdx, [rbp+arg_0]
0x18004485e  lea     rcx, [r14+18h]
0x180044862  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>> &&)
0x180044867  mov     rax, [rbx]
0x18004486a  mov     byte ptr [rbp+arg_0], 1
0x18004486e  mov     rcx, [rax]
0x180044871  mov     [rbp+arg_10], rcx
0x180044875  lea     r8, [rbp+arg_0]
0x180044879  mov     rcx, rsi
0x18004487c  lea     rdx, [rbp+arg_10]
0x180044880  call    ??$make_pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@YA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@0@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@0@$$QEA_N@Z; std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>> &&,bool &&)
0x180044885  mov     rbx, [rsp+30h+arg_8]
0x18004488a  mov     rax, rsi
0x18004488d  add     rsp, 30h
0x180044891  pop     r15
0x180044893  pop     r14
0x180044895  pop     rdi
0x180044896  pop     rsi
0x180044897  pop     rbp
0x180044898  retn
```
