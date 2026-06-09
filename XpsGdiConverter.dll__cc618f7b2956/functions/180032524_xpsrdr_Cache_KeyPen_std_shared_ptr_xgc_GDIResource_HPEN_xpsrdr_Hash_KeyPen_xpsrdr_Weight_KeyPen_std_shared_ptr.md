# xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::insert(std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>> const &)

- ea: `0x180032524`
- end: `0x180032631`
- name: `?insert@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@4@@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800314b8`

## callees

- `0x18000e9b0`
- `0x1800184e8`
- `0x18001ba90`
- `0x18001ca74`
- `0x18001cb04`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x18003147c`
- `0x180031734`
- `0x180032524`
- `0x180032638`
- `0x1800326c4`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::insert(
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

  v14 = xpsrdr::Hash<KeyPen>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v13,
    &v14);
  while ( v13[0] != v13[1] )
  {
    v6 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v13)
                   + 8);
    v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
    if ( (unsigned __int8)KeyPen::operator==(a3, v7) )
    {
      v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
      std::shared_ptr<ID2D1Brush>::operator=(v8 + 40, v9);
      v15 = *v6;
      LOBYTE(v14) = 0;
      goto LABEL_7;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v13);
  }
  xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::resize(a1);
  std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::push_front(a1 + 8, a3);
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
0x180032524  mov     [rsp-28h+arg_8], rbx
0x180032529  push    rbp
0x18003252a  push    rsi
0x18003252b  push    rdi
0x18003252c  push    r14
0x18003252e  push    r15
0x180032530  mov     rbp, rsp
0x180032533  sub     rsp, 30h
0x180032537  mov     rsi, rdx
0x18003253a  mov     rdi, r8
0x18003253d  mov     rdx, r8
0x180032540  mov     r14, rcx
0x180032543  call    ??R?$Hash@UKeyPen@@@xpsrdr@@QEBA_KAEBUKeyPen@@@Z; xpsrdr::Hash<KeyPen>::operator()(KeyPen const &)
0x180032548  lea     r8, [rbp+arg_0]
0x18003254c  mov     [rbp+arg_0], rax
0x180032550  lea     rdx, [rbp+var_10]
0x180032554  lea     rcx, [r14+18h]
0x180032558  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x18003255d  mov     rax, [rbp+var_8]
0x180032561  cmp     [rbp+var_10], rax
0x180032565  jz      short loc_1800325B8
0x180032567  lea     rcx, [rbp+var_10]
0x18003256b  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180032570  lea     rbx, [rax+8]
0x180032574  mov     rcx, rbx
0x180032577  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18003257c  mov     rdx, rax
0x18003257f  mov     rcx, rdi
0x180032582  call    ??8KeyPen@@QEBA_NAEBU0@@Z; KeyPen::operator==(KeyPen const &)
0x180032587  test    al, al
0x180032589  jnz     short loc_180032596
0x18003258b  lea     rcx, [rbp+var_10]
0x18003258f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180032594  jmp     short loc_18003255D
0x180032596  mov     rcx, rbx
0x180032599  lea     rdx, [rdi+28h]
0x18003259d  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x1800325a2  lea     rcx, [rax+28h]
0x1800325a6  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800325ab  mov     rax, [rbx]
0x1800325ae  mov     [rbp+arg_10], rax
0x1800325b2  mov     byte ptr [rbp+arg_0], 0
0x1800325b6  jmp     short loc_18003260D
0x1800325b8  movss   xmm1, dword ptr [r14]
0x1800325bd  mov     rcx, r14
0x1800325c0  call    ?resize@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::resize(float)
0x1800325c5  lea     rbx, [r14+8]
0x1800325c9  mov     rdx, rdi
0x1800325cc  mov     rcx, rbx
0x1800325cf  call    ?push_front@?$list@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@2@@std@@QEAAXAEBU?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@2@@Z; std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::push_front(std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>> const &)
0x1800325d4  mov     rax, [rbx]
0x1800325d7  lea     r8, [rbp+arg_10]
0x1800325db  lea     rcx, [rbp+var_10]
0x1800325df  mov     rdx, [rax]
0x1800325e2  mov     [rbp+arg_10], rdx
0x1800325e6  lea     rdx, [rbp+arg_0]
0x1800325ea  call    ??$?0AEA_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@$0A@@?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@QEAA@AEA_K$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@1@@Z; std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(unsigned __int64 &,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>> &&)
0x1800325ef  mov     r8, rax
0x1800325f2  lea     rdx, [rbp+arg_0]
0x1800325f6  lea     rcx, [r14+18h]
0x1800325fa  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>> &&)
0x1800325ff  mov     rax, [rbx]
0x180032602  mov     byte ptr [rbp+arg_0], 1
0x180032606  mov     rcx, [rax]
0x180032609  mov     [rbp+arg_10], rcx
0x18003260d  lea     r8, [rbp+arg_0]
0x180032611  mov     rcx, rsi
0x180032614  lea     rdx, [rbp+arg_10]
0x180032618  call    ??$make_pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@YA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@0@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@0@$$QEA_N@Z; std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>> &&,bool &&)
0x18003261d  mov     rbx, [rsp+30h+arg_8]
0x180032622  mov     rax, rsi
0x180032625  add     rsp, 30h
0x180032629  pop     r15
0x18003262b  pop     r14
0x18003262d  pop     rdi
0x18003262e  pop     rsi
0x18003262f  pop     rbp
0x180032630  retn
```
