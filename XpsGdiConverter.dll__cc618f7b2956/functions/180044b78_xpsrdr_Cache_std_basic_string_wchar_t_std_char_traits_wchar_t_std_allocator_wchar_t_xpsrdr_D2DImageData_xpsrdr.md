# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData>>::operator[](std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180044b78`
- end: `0x180044c42`
- name: `??A?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAAEAUD2DImageData@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180044f78`

## callees

- `0x180008830`
- `0x18000e604`
- `0x180011b0c`
- `0x18001df50`
- `0x1800229e8`
- `0x180044a50`
- `0x180044b04`
- `0x180044b78`
- `0x18004686c`
- `0x180046920`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::operator[](
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-19h] BYREF
  __int128 v10; // [rsp+28h] [rbp-11h] BYREF
  __int64 v11; // [rsp+38h] [rbp-1h]
  _BYTE v12[16]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v13[56]; // [rsp+50h] [rbp+17h] BYREF

  xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::find(
    a1,
    &v9,
    a2);
  v5 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a1,
                   (__int64)v12,
                   v4);
  if ( v9 == *v5 )
  {
    v10 = 0;
    v11 = 0;
    v6 = xpsrdr::D2DImageData::D2DImageData((xpsrdr::D2DImageData *)&v10);
    v7 = std::pair<std::wstring const,xpsrdr::D2DImageData>::pair<std::wstring const,xpsrdr::D2DImageData>(v13, a2, v6);
    v9 = *(_QWORD *)xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::insert(
                      a1,
                      (__int64)v12,
                      v7);
    std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(v13);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v10);
  }
  return std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v9)
       + 32;
}

```

## disassembly

```asm
0x180044b78  mov     [rsp-8+arg_10], rbx
0x180044b7d  mov     [rsp-8+arg_18], rdi
0x180044b82  push    rbp
0x180044b83  lea     rbp, [rsp-57h]
0x180044b88  sub     rsp, 90h
0x180044b8f  mov     rax, cs:__security_cookie
0x180044b96  xor     rax, rsp
0x180044b99  mov     [rbp+57h+var_8], rax
0x180044b9d  mov     rdi, rdx
0x180044ba0  mov     rbx, rcx
0x180044ba3  mov     r8, rdx
0x180044ba6  lea     rdx, [rbp+57h+var_70]
0x180044baa  call    ?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::find(std::wstring const &)
0x180044baf  lea     rdx, [rbp+57h+var_50]
0x180044bb3  mov     rcx, rbx
0x180044bb6  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180044bbb  mov     rcx, [rax]
0x180044bbe  cmp     [rbp+57h+var_70], rcx
0x180044bc2  jnz     short loc_180044C14
0x180044bc4  xorps   xmm0, xmm0
0x180044bc7  xor     eax, eax
0x180044bc9  movups  [rbp+57h+var_68], xmm0
0x180044bcd  mov     [rbp+57h+var_58], rax
0x180044bd1  lea     rcx, [rbp+57h+var_68]; this
0x180044bd5  call    ??0D2DImageData@xpsrdr@@QEAA@XZ; xpsrdr::D2DImageData::D2DImageData(void)
0x180044bda  nop
0x180044bdb  mov     r8, rax
0x180044bde  mov     rdx, rdi
0x180044be1  lea     rcx, [rbp+57h+var_40]
0x180044be5  call    ??$?0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@$0A@@?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAUD2DImageData@xpsrdr@@@Z; std::pair<std::wstring const,xpsrdr::D2DImageData>::pair<std::wstring const,xpsrdr::D2DImageData>(std::wstring const &,xpsrdr::D2DImageData &&)
0x180044bea  nop
0x180044beb  mov     r8, rax
0x180044bee  lea     rdx, [rbp+57h+var_50]
0x180044bf2  mov     rcx, rbx
0x180044bf5  call    ?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::insert(std::pair<std::wstring const,xpsrdr::D2DImageData> const &)
0x180044bfa  mov     rcx, [rax]
0x180044bfd  mov     [rbp+57h+var_70], rcx
0x180044c01  lea     rcx, [rbp+57h+var_40]
0x180044c05  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>::~pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>(void)
0x180044c0a  nop
0x180044c0b  lea     rcx, [rbp+57h+var_68]
0x180044c0f  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180044c14  lea     rcx, [rbp+57h+var_70]
0x180044c18  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180044c1d  add     rax, 20h ; ' '
0x180044c21  mov     rcx, [rbp+57h+var_8]
0x180044c25  xor     rcx, rsp; StackCookie
0x180044c28  call    __security_check_cookie
0x180044c2d  lea     r11, [rsp+90h+var_s0]
0x180044c35  mov     rbx, [r11+20h]
0x180044c39  mov     rdi, [r11+28h]
0x180044c3d  mov     rsp, r11
0x180044c40  pop     rbp
0x180044c41  retn
```
