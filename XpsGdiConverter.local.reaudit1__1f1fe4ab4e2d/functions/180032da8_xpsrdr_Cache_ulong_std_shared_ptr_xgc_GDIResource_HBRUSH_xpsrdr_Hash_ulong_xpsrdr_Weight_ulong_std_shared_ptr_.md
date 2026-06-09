# xpsrdr::Cache<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<ulong>,xpsrdr::Weight<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::insert(std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>> const &)

- ea: `0x180032da8`
- end: `0x180032eaf`
- name: `?insert@?$Cache@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@U?$Hash@K@xpsrdr@@U?$Weight@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@4@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@4@@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180032840`

## callees

- `0x18000e9b0`
- `0x1800184e8`
- `0x18001ba90`
- `0x18001ca74`
- `0x18001cb04`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x180032da8`
- `0x180032eb8`
- `0x180032f44`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<unsigned long>,xpsrdr::Weight<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::insert(
        __int64 a1,
        __int64 a2,
        unsigned int *a3)
{
  unsigned int v3; // r14d
  __int64 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 *v12; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v15; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  v3 = *a3;
  v15 = *a3;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v14,
    &v15);
  while ( v14[0] != v14[1] )
  {
    v7 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v14)
                   + 8);
    if ( v3 == *(_DWORD *)std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v7) )
    {
      v9 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v8);
      std::shared_ptr<ID2D1Brush>::operator=(v9 + 8, v10);
      v16 = *v7;
      LOBYTE(v15) = 0;
      goto LABEL_7;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v14);
  }
  xpsrdr::Cache<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<unsigned long>,xpsrdr::Weight<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::resize(a1);
  std::list<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::push_front(a1 + 8, a3);
  v16 = **(_QWORD **)(a1 + 8);
  v11 = std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(
          v14,
          &v15,
          &v16);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(
    a1 + 24,
    &v15,
    v11);
  v12 = *(__int64 **)(a1 + 8);
  LOBYTE(v15) = 1;
  v16 = *v12;
LABEL_7:
  std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(
    a2,
    &v16,
    &v15);
  return a2;
}

```

## disassembly

```asm
0x180032da8  mov     [rsp-28h+arg_8], rbx
0x180032dad  mov     [rsp-28h+arg_18], rsi
0x180032db2  push    rbp
0x180032db3  push    rdi
0x180032db4  push    r12
0x180032db6  push    r14
0x180032db8  push    r15
0x180032dba  mov     rbp, rsp
0x180032dbd  sub     rsp, 30h
0x180032dc1  mov     r14d, [r8]
0x180032dc4  mov     rsi, r8
0x180032dc7  mov     r15, rcx
0x180032dca  mov     [rbp+arg_0], r14
0x180032dce  mov     rdi, rdx
0x180032dd1  lea     r8, [rbp+arg_0]
0x180032dd5  lea     rdx, [rbp+var_10]
0x180032dd9  add     rcx, 18h
0x180032ddd  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180032de2  mov     rax, [rbp+var_8]
0x180032de6  cmp     [rbp+var_10], rax
0x180032dea  jz      short loc_180032E30
0x180032dec  lea     rcx, [rbp+var_10]
0x180032df0  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180032df5  lea     rbx, [rax+8]
0x180032df9  mov     rcx, rbx
0x180032dfc  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180032e01  cmp     r14d, [rax]
0x180032e04  jz      short loc_180032E11
0x180032e06  lea     rcx, [rbp+var_10]
0x180032e0a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180032e0f  jmp     short loc_180032DE2
0x180032e11  lea     rdx, [rsi+8]
0x180032e15  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180032e1a  lea     rcx, [rax+8]
0x180032e1e  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180032e23  mov     rax, [rbx]
0x180032e26  mov     [rbp+arg_10], rax
0x180032e2a  mov     byte ptr [rbp+arg_0], 0
0x180032e2e  jmp     short loc_180032E85
0x180032e30  movss   xmm1, dword ptr [r15]
0x180032e35  mov     rcx, r15
0x180032e38  call    ?resize@?$Cache@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@U?$Hash@K@xpsrdr@@U?$Weight@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@4@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<ulong>,xpsrdr::Weight<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::resize(float)
0x180032e3d  lea     rbx, [r15+8]
0x180032e41  mov     rdx, rsi
0x180032e44  mov     rcx, rbx
0x180032e47  call    ?push_front@?$list@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@2@@std@@QEAAXAEBU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@2@@Z; std::list<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::push_front(std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>> const &)
0x180032e4c  mov     rax, [rbx]
0x180032e4f  lea     r8, [rbp+arg_10]
0x180032e53  lea     rcx, [rbp+var_10]
0x180032e57  mov     rdx, [rax]
0x180032e5a  mov     [rbp+arg_10], rdx
0x180032e5e  lea     rdx, [rbp+arg_0]
0x180032e62  call    ??$?0AEA_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@$0A@@?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@QEAA@AEA_K$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@1@@Z; std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(unsigned __int64 &,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>> &&)
0x180032e67  mov     r8, rax
0x180032e6a  lea     rdx, [rbp+arg_0]
0x180032e6e  lea     rcx, [r15+18h]
0x180032e72  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>> &&)
0x180032e77  mov     rax, [rbx]
0x180032e7a  mov     byte ptr [rbp+arg_0], 1
0x180032e7e  mov     rcx, [rax]
0x180032e81  mov     [rbp+arg_10], rcx
0x180032e85  lea     r8, [rbp+arg_0]
0x180032e89  mov     rcx, rdi
0x180032e8c  lea     rdx, [rbp+arg_10]
0x180032e90  call    ??$make_pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@YA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@0@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@0@$$QEA_N@Z; std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>> &&,bool &&)
0x180032e95  mov     rbx, [rsp+30h+arg_8]
0x180032e9a  mov     rax, rdi
0x180032e9d  mov     rsi, [rsp+30h+arg_18]
0x180032ea2  add     rsp, 30h
0x180032ea6  pop     r15
0x180032ea8  pop     r14
0x180032eaa  pop     r12
0x180032eac  pop     rdi
0x180032ead  pop     rbp
0x180032eae  retn
```
