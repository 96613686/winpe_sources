# xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::erase(xpsrdr::KeyBrush const &)

- ea: `0x18004193c`
- end: `0x1800419e2`
- name: `?erase@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAAXAEBUKeyBrush@2@@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180041c84`

## callees

- `0x18000e9b0`
- `0x18001ca24`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x18003fe28`
- `0x18003ff7c`
- `0x18004193c`
- `0x1800419e8`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::erase(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // r8
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+28h] [rbp-30h]
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = xpsrdr::Hash<xpsrdr::KeyBrush>::operator()(a1, a2);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    &v9,
    &v11);
  result = v10;
  v5 = v9;
  if ( v9 != v10 )
  {
    while ( v5 != result )
    {
      v6 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(&v9);
      v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6 + 8);
      if ( (unsigned __int8)xpsrdr::KeyBrush::operator==(a2, v7) )
      {
        std::list<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::erase(
          a1 + 8,
          &v11,
          *v8);
        return std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>,0>(
                 a1 + 24,
                 &v11,
                 v5);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v9);
      result = v10;
      v5 = v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004193c  push    rbx
0x18004193e  push    rbp
0x18004193f  push    rsi
0x180041940  push    rdi
0x180041941  sub     rsp, 38h
0x180041945  mov     rbp, rdx
0x180041948  mov     rdi, rcx
0x18004194b  call    ??R?$Hash@UKeyBrush@xpsrdr@@@xpsrdr@@QEBA_KAEBUKeyBrush@1@@Z; xpsrdr::Hash<xpsrdr::KeyBrush>::operator()(xpsrdr::KeyBrush const &)
0x180041950  lea     r8, [rsp+58h+arg_0]
0x180041955  mov     [rsp+58h+arg_0], rax
0x18004195a  lea     rdx, [rsp+58h+var_38]
0x18004195f  lea     rcx, [rdi+18h]
0x180041963  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180041968  mov     rax, [rsp+58h+var_30]
0x18004196d  mov     rbx, [rsp+58h+var_38]
0x180041972  cmp     rbx, rax
0x180041975  jz      short loc_1800419D9
0x180041977  cmp     rbx, rax
0x18004197a  jz      short loc_1800419D9
0x18004197c  lea     rcx, [rsp+58h+var_38]
0x180041981  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x180041986  lea     r8, [rax+8]
0x18004198a  mov     rcx, r8
0x18004198d  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180041992  mov     rdx, rax
0x180041995  mov     rcx, rbp
0x180041998  call    ??8KeyBrush@xpsrdr@@QEBA_NAEBU01@@Z; xpsrdr::KeyBrush::operator==(xpsrdr::KeyBrush const &)
0x18004199d  test    al, al
0x18004199f  jnz     short loc_1800419B7
0x1800419a1  lea     rcx, [rsp+58h+var_38]
0x1800419a6  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800419ab  mov     rax, [rsp+58h+var_30]
0x1800419b0  mov     rbx, [rsp+58h+var_38]
0x1800419b5  jmp     short loc_180041977
0x1800419b7  mov     r8, [r8]
0x1800419ba  lea     rcx, [rdi+8]
0x1800419be  lea     rdx, [rsp+58h+arg_0]
0x1800419c3  call    ?erase@?$list@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@2@@Z; std::list<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>>>)
0x1800419c8  mov     r8, rbx
0x1800419cb  lea     rdx, [rsp+58h+arg_0]
0x1800419d0  lea     rcx, [rdi+18h]
0x1800419d4  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>>>)
0x1800419d9  add     rsp, 38h
0x1800419dd  pop     rdi
0x1800419de  pop     rsi
0x1800419df  pop     rbp
0x1800419e0  pop     rbx
0x1800419e1  retn
```
