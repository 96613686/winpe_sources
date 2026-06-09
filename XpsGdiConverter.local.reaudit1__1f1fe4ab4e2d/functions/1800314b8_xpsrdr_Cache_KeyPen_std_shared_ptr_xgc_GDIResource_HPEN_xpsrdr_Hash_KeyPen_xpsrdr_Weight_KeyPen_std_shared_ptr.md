# xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::operator[](KeyPen const &)

- ea: `0x1800314b8`
- end: `0x18003156c`
- name: `??A?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAAAEAV?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@AEBUKeyPen@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180031574`

## callees

- `0x18000e15c`
- `0x180011b0c`
- `0x18001df50`
- `0x1800229e8`
- `0x180024e0c`
- `0x180030ae0`
- `0x1800314b8`
- `0x1800323f0`
- `0x180032524`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::operator[](
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int128 v9; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v10[16]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v11[72]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v12; // [rsp+A0h] [rbp+18h] BYREF
  char v13; // [rsp+A8h] [rbp+20h] BYREF

  xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::find(
    a1,
    &v12,
    a2);
  v5 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a1,
                   (__int64)&v13,
                   v4);
  if ( v12 == *v5 )
  {
    v9 = 0;
    v6 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v9);
    v7 = std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>(
           v11,
           a2,
           v6);
    v12 = *(_QWORD *)xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::insert(
                       a1,
                       (__int64)v10,
                       v7);
    std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>::~pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>(v11);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v9);
  }
  return std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v12)
       + 40;
}

```

## disassembly

```asm
0x1800314b8  mov     rax, rsp
0x1800314bb  mov     [rax+8], rbx
0x1800314bf  push    rdi
0x1800314c0  sub     rsp, 80h
0x1800314c7  mov     rdi, rdx
0x1800314ca  mov     rbx, rcx
0x1800314cd  mov     r8, rdx
0x1800314d0  lea     rdx, [rax+18h]
0x1800314d4  call    ?find@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBUKeyPen@@@Z; xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::find(KeyPen const &)
0x1800314d9  lea     rdx, [rsp+88h+arg_18]
0x1800314e1  mov     rcx, rbx
0x1800314e4  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x1800314e9  mov     r8, [rax]
0x1800314ec  cmp     [rsp+88h+arg_10], r8
0x1800314f4  jnz     short loc_18003154A
0x1800314f6  xorps   xmm0, xmm0
0x1800314f9  movups  [rsp+88h+var_68], xmm0
0x1800314fe  lea     rcx, [rsp+88h+var_68]
0x180031503  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180031508  nop
0x180031509  mov     r8, rax
0x18003150c  mov     rdx, rdi
0x18003150f  lea     rcx, [rsp+88h+var_48]
0x180031514  call    ??$?0AEBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@$0A@@?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@QEAA@AEBUKeyPen@@$$QEAV?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@1@@Z; std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>(KeyPen const &,std::shared_ptr<xgc::GDIResource<HPEN__ *>> &&)
0x180031519  nop
0x18003151a  mov     r8, rax
0x18003151d  lea     rdx, [rsp+88h+var_58]
0x180031522  mov     rcx, rbx
0x180031525  call    ?insert@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@4@@Z; xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::insert(std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>> const &)
0x18003152a  mov     rcx, [rax]
0x18003152d  mov     [rsp+88h+arg_10], rcx
0x180031535  lea     rcx, [rsp+88h+var_48]
0x18003153a  call    ??1?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@QEAA@XZ; std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>::~pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>(void)
0x18003153f  nop
0x180031540  lea     rcx, [rsp+88h+var_68]
0x180031545  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18003154a  lea     rcx, [rsp+88h+arg_10]
0x180031552  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180031557  add     rax, 28h ; '('
0x18003155b  mov     rbx, [rsp+88h+arg_0]
0x180031563  add     rsp, 80h
0x18003156a  pop     rdi
0x18003156b  retn
```
