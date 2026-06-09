# xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::operator[](tagLOGFONTW const &)

- ea: `0x18001de6c`
- end: `0x18001df38`
- name: `??A?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAAAEAV?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@AEBUtagLOGFONTW@@@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001dff0`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x180011b0c`
- `0x18001bb4c`
- `0x18001de6c`
- `0x18001df50`
- `0x1800229e8`
- `0x180022bec`
- `0x180022d68`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::operator[](
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-B8h] BYREF
  __int128 v10; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v12[96]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v13[16]; // [rsp+B0h] [rbp-28h] BYREF

  xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::find(
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
    v7 = std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>(
           v12,
           a2,
           v6);
    v9 = *(_QWORD *)xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::insert(
                      a1,
                      (__int64)v11,
                      v7);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v13);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v10);
  }
  return std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v9)
       + 96;
}

```

## disassembly

```asm
0x18001de6c  mov     [rsp+arg_10], rbx
0x18001de71  push    rdi
0x18001de72  sub     rsp, 0D0h
0x18001de79  mov     rax, cs:__security_cookie
0x18001de80  xor     rax, rsp
0x18001de83  mov     [rsp+0D8h+var_18], rax
0x18001de8b  mov     rdi, rdx
0x18001de8e  mov     rbx, rcx
0x18001de91  mov     r8, rdx
0x18001de94  lea     rdx, [rsp+0D8h+var_B8]
0x18001de99  call    ?find@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBUtagLOGFONTW@@@Z; xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::find(tagLOGFONTW const &)
0x18001de9e  lea     rdx, [rsp+0D8h+var_B0]
0x18001dea3  mov     rcx, rbx
0x18001dea6  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x18001deab  mov     rcx, [rax]
0x18001deae  cmp     [rsp+0D8h+var_B8], rcx
0x18001deb3  jnz     short loc_18001DF09
0x18001deb5  xorps   xmm0, xmm0
0x18001deb8  movups  [rsp+0D8h+var_B0], xmm0
0x18001debd  lea     rcx, [rsp+0D8h+var_B0]
0x18001dec2  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18001dec7  nop
0x18001dec8  mov     r8, rax
0x18001decb  mov     rdx, rdi
0x18001dece  lea     rcx, [rsp+0D8h+var_88]
0x18001ded3  call    ??$?0AEBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@$0A@@?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@QEAA@AEBUtagLOGFONTW@@$$QEAV?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@1@@Z; std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>(tagLOGFONTW const &,std::shared_ptr<xgc::GDIResource<HFONT__ *>> &&)
0x18001ded8  nop
0x18001ded9  mov     r8, rax
0x18001dedc  lea     rdx, [rsp+0D8h+var_A0]
0x18001dee1  mov     rcx, rbx
0x18001dee4  call    ?insert@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@4@@Z; xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::insert(std::pair<tagLOGFONTW const,std::shared_ptr<xgc::GDIResource<HFONT__ *>>> const &)
0x18001dee9  mov     rcx, [rax]
0x18001deec  mov     [rsp+0D8h+var_B8], rcx
0x18001def1  lea     rcx, [rsp+0D8h+var_28]
0x18001def9  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001defe  nop
0x18001deff  lea     rcx, [rsp+0D8h+var_B0]
0x18001df04  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001df09  lea     rcx, [rsp+0D8h+var_B8]
0x18001df0e  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18001df13  add     rax, 60h ; '`'
0x18001df17  mov     rcx, [rsp+0D8h+var_18]
0x18001df1f  xor     rcx, rsp; StackCookie
0x18001df22  call    __security_check_cookie
0x18001df27  mov     rbx, [rsp+0D8h+arg_10]
0x18001df2f  add     rsp, 0D0h
0x18001df36  pop     rdi
0x18001df37  retn
```
