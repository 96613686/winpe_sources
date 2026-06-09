# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>>>::operator[](std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180035264`
- end: `0x180035327`
- name: `??A?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAAAEAV?$shared_ptr@UColorContext@xpsrdr@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180035fa4`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e604`
- `0x180011b0c`
- `0x18001ba44`
- `0x18001df50`
- `0x1800229e8`
- `0x180035264`
- `0x180036e4c`
- `0x180036f00`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::operator[](
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-68h] BYREF
  __int128 v10; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[48]; // [rsp+48h] [rbp-40h] BYREF

  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(
    a1,
    &v9,
    a2);
  v5 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a1,
                   (__int64)&v10,
                   v4);
  if ( v9 == *v5 )
  {
    v10 = 0;
    v6 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v10);
    v7 = std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(
           v12,
           a2,
           v6);
    v9 = *(_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::insert(
                      a1,
                      (__int64)v11,
                      v7);
    std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(v12);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v10);
  }
  return std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v9)
       + 32;
}

```

## disassembly

```asm
0x180035264  mov     [rsp+arg_10], rbx
0x180035269  push    rdi
0x18003526a  sub     rsp, 80h
0x180035271  mov     rax, cs:__security_cookie
0x180035278  xor     rax, rsp
0x18003527b  mov     [rsp+88h+var_10], rax
0x180035280  mov     rdi, rdx
0x180035283  mov     rbx, rcx
0x180035286  mov     r8, rdx
0x180035289  lea     rdx, [rsp+88h+var_68]
0x18003528e  call    ?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(std::wstring const &)
0x180035293  lea     rdx, [rsp+88h+var_60]
0x180035298  mov     rcx, rbx
0x18003529b  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x1800352a0  mov     rcx, [rax]
0x1800352a3  cmp     [rsp+88h+var_68], rcx
0x1800352a8  jnz     short loc_1800352FB
0x1800352aa  xorps   xmm0, xmm0
0x1800352ad  movups  [rsp+88h+var_60], xmm0
0x1800352b2  lea     rcx, [rsp+88h+var_60]
0x1800352b7  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800352bc  nop
0x1800352bd  mov     r8, rax
0x1800352c0  mov     rdx, rdi
0x1800352c3  lea     rcx, [rsp+88h+var_40]
0x1800352c8  call    ??$?0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@1@$0A@@?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV?$shared_ptr@UImage@xpsrdr@@@1@@Z; std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(std::wstring const &,std::shared_ptr<xpsrdr::Image> &&)
0x1800352cd  nop
0x1800352ce  mov     r8, rax
0x1800352d1  lea     rdx, [rsp+88h+var_50]
0x1800352d6  mov     rcx, rbx
0x1800352d9  call    ?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@4@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::insert(std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>> const &)
0x1800352de  mov     rcx, [rax]
0x1800352e1  mov     [rsp+88h+var_68], rcx
0x1800352e6  lea     rcx, [rsp+88h+var_40]
0x1800352eb  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(void)
0x1800352f0  nop
0x1800352f1  lea     rcx, [rsp+88h+var_60]
0x1800352f6  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800352fb  lea     rcx, [rsp+88h+var_68]
0x180035300  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180035305  add     rax, 20h ; ' '
0x180035309  mov     rcx, [rsp+88h+var_10]
0x18003530e  xor     rcx, rsp; StackCookie
0x180035311  call    __security_check_cookie
0x180035316  mov     rbx, [rsp+88h+arg_10]
0x18003531e  add     rsp, 80h
0x180035325  pop     rdi
0x180035326  retn
```
