# xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::operator[](xpsrdr::KeyFontFace const &)

- ea: `0x180043174`
- end: `0x18004323d`
- name: `??A?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAAAEAV?$shared_ptr@UIDWriteFontFace@@@std@@AEBUKeyFontFace@1@@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800432dc`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x180011b0c`
- `0x18001df50`
- `0x1800229e8`
- `0x18003cca8`
- `0x180042d84`
- `0x180043174`
- `0x1800446d8`
- `0x18004478c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::operator[](
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-78h] BYREF
  __int128 v10; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v12[56]; // [rsp+48h] [rbp-50h] BYREF

  xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(
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
    v7 = std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>(
           v12,
           a2,
           v6);
    v9 = *(_QWORD *)xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::insert(
                      a1,
                      (__int64)v11,
                      v7);
    std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>::~pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>(v12);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v10);
  }
  return std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v9)
       + 40;
}

```

## disassembly

```asm
0x180043174  mov     [rsp+arg_10], rbx
0x180043179  push    rdi
0x18004317a  sub     rsp, 90h
0x180043181  mov     rax, cs:__security_cookie
0x180043188  xor     rax, rsp
0x18004318b  mov     [rsp+98h+var_18], rax
0x180043193  mov     rdi, rdx
0x180043196  mov     rbx, rcx
0x180043199  mov     r8, rdx
0x18004319c  lea     rdx, [rsp+98h+var_78]
0x1800431a1  call    ?find@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@AEBUKeyFontFace@2@@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::find(xpsrdr::KeyFontFace const &)
0x1800431a6  lea     rdx, [rsp+98h+var_70]
0x1800431ab  mov     rcx, rbx
0x1800431ae  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x1800431b3  mov     rcx, [rax]
0x1800431b6  cmp     [rsp+98h+var_78], rcx
0x1800431bb  jnz     short loc_18004320E
0x1800431bd  xorps   xmm0, xmm0
0x1800431c0  movups  [rsp+98h+var_70], xmm0
0x1800431c5  lea     rcx, [rsp+98h+var_70]
0x1800431ca  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800431cf  nop
0x1800431d0  mov     r8, rax
0x1800431d3  mov     rdx, rdi
0x1800431d6  lea     rcx, [rsp+98h+var_50]
0x1800431db  call    ??$?0AEBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@$0A@@?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@QEAA@AEBUKeyFontFace@xpsrdr@@$$QEAV?$shared_ptr@UIDWriteFontFace@@@1@@Z; std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>(xpsrdr::KeyFontFace const &,std::shared_ptr<IDWriteFontFace> &&)
0x1800431e0  nop
0x1800431e1  mov     r8, rax
0x1800431e4  lea     rdx, [rsp+98h+var_60]
0x1800431e9  mov     rcx, rbx
0x1800431ec  call    ?insert@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@4@@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::insert(std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>> const &)
0x1800431f1  mov     rcx, [rax]
0x1800431f4  mov     [rsp+98h+var_78], rcx
0x1800431f9  lea     rcx, [rsp+98h+var_50]
0x1800431fe  call    ??1?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@QEAA@XZ; std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>::~pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>(void)
0x180043203  nop
0x180043204  lea     rcx, [rsp+98h+var_70]
0x180043209  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004320e  lea     rcx, [rsp+98h+var_78]
0x180043213  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180043218  add     rax, 28h ; '('
0x18004321c  mov     rcx, [rsp+98h+var_18]
0x180043224  xor     rcx, rsp; StackCookie
0x180043227  call    __security_check_cookie
0x18004322c  mov     rbx, [rsp+98h+arg_10]
0x180043234  add     rsp, 90h
0x18004323b  pop     rdi
0x18004323c  retn
```
