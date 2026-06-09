# xgc::GDIResourceSelector<xgc::GDIResources<HBRUSH__ *,ulong>,xgc::BrushFactory>::operator()(xgc::CDeviceContext &,xgc::GDIResources<HBRUSH__ *,ulong> &,ulong &)

- ea: `0x1800328f4`
- end: `0x180032a8c`
- name: `??R?$GDIResourceSelector@U?$GDIResources@PEAUHBRUSH__@@K@xgc@@UBrushFactory@2@@xgc@@QEAAXAEAVCDeviceContext@1@AEAU?$GDIResources@PEAUHBRUSH__@@K@1@AEAK@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180032a94`

## callees

- `0x180008854`
- `0x18000d7f8`
- `0x180011b0c`
- `0x180012088`
- `0x1800184e8`
- `0x18001bc1c`
- `0x18001df40`
- `0x1800229e8`
- `0x180032840`
- `0x1800328f4`
- `0x180032d08`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003296d`
- `KERNEL32!GetLastError` at `0x1800329f5`
- `KERNEL32!GetLastError` at `0x180032a2b`
- `KERNEL32!GetLastError` at `0x18003296d`
- `KERNEL32!GetLastError` at `0x1800329f5`
- `KERNEL32!GetLastError` at `0x180032a2b`
- `GDI32!SelectObject` at `0x180032962`
- `GDI32!SelectObject` at `0x180032a20`
- `GDI32!SelectObject` at `0x180032962`
- `GDI32!SelectObject` at `0x180032a20`
- `GDI32!CreateSolidBrush` at `0x1800329d3`
- `GDI32!CreateSolidBrush` at `0x1800329d3`
- `GDI32!GetStockObject` at `0x1800329bf`
- `GDI32!GetStockObject` at `0x1800329bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall xgc::GDIResourceSelector<xgc::GDIResources<HBRUSH__ *,unsigned long>,xgc::BrushFactory>::operator()(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        COLORREF *a4)
{
  _QWORD *v7; // rax
  __int64 v8; // r10
  __int64 v9; // rbx
  void *v10; // rdx
  void **result; // rax
  signed int LastError; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  _QWORD *v16; // rbx
  COLORREF v17; // ecx
  int v18; // ecx
  void *SolidBrush; // rax
  signed int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  signed int v24; // eax
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  __int64 v28; // rax
  _QWORD v29[5]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *v30; // [rsp+50h] [rbp+8h] BYREF
  char v31; // [rsp+60h] [rbp+18h] BYREF

  v30 = a1;
  v30 = *(_QWORD **)xpsrdr::Cache<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<unsigned long>,xpsrdr::Weight<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::find(
                      a3,
                      &v30,
                      a4);
  v7 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a3,
                   &v31);
  if ( v8 != *v7 )
  {
    v9 = std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>::operator*(&v30)
       + 8;
    v10 = *(void **)std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v9);
    result = *(void ***)(a3 + 40);
    if ( v10 != *result )
    {
      if ( !SelectObject(*(HDC *)(a2 + 32), v10) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v13, v14, v15);
      }
      return (void **)std::shared_ptr<ID2D1Brush>::operator=(a3 + 40, v9);
    }
    return result;
  }
  v16 = operator new(8u);
  v30 = v16;
  v17 = *a4;
  if ( *a4 )
  {
    if ( v17 != 0xFFFFFF )
    {
      SolidBrush = CreateSolidBrush(v17);
      goto LABEL_16;
    }
    v18 = 0;
  }
  else
  {
    v18 = 4;
  }
  SolidBrush = GetStockObject(v18);
LABEL_16:
  *v16 = SolidBrush;
  std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>::shared_ptr<xgc::GDIResource<HBRUSH__ *>>(v29, v16);
  if ( !*(_QWORD *)v29[0] )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    if ( v20 >= 0 )
      v20 = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
  }
  if ( !SelectObject(*(HDC *)(a2 + 32), *(HGDIOBJ *)v29[0]) )
  {
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    if ( v24 >= 0 )
      v24 = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
  }
  std::shared_ptr<XgcSolidPath>::swap(a3 + 40, v29);
  v28 = xpsrdr::Cache<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<unsigned long>,xpsrdr::Weight<unsigned long,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::operator[](
          a3,
          a4);
  std::shared_ptr<ID2D1Brush>::operator=(v28, a3 + 40);
  return (void **)std::_Ptr_base<ID2D1RenderTarget>::_Decref(v29);
}

```

## disassembly

```asm
0x1800328f4  mov     [rsp+arg_8], rbx
0x1800328f9  mov     [rsp+arg_0], rcx
0x1800328fe  push    rbp
0x1800328ff  push    rsi
0x180032900  push    rdi
0x180032901  sub     rsp, 30h
0x180032905  mov     rsi, r9
0x180032908  mov     rdi, r8
0x18003290b  mov     rbp, rdx
0x18003290e  mov     r8, r9
0x180032911  lea     rdx, [rsp+48h+arg_0]
0x180032916  mov     rcx, rdi
0x180032919  call    ?find@?$Cache@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@U?$Hash@K@xpsrdr@@U?$Weight@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@4@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBK@Z; xpsrdr::Cache<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<ulong>,xpsrdr::Weight<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::find(ulong const &)
0x18003291e  mov     r10, [rax]
0x180032921  mov     [rsp+48h+arg_0], r10
0x180032926  lea     rdx, [rsp+48h+arg_10]
0x18003292b  mov     rcx, rdi
0x18003292e  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180032933  cmp     r10, [rax]
0x180032936  jz      short loc_1800329A2
0x180032938  lea     rcx, [rsp+48h+arg_0]
0x18003293d  call    ??D?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@QEBAAEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@1@XZ; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>::operator*(void)
0x180032942  lea     rbx, [rax+8]
0x180032946  mov     rcx, rbx
0x180032949  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x18003294e  mov     rdx, [rax]; h
0x180032951  mov     rax, [rdi+28h]
0x180032955  cmp     rdx, [rax]
0x180032958  jz      loc_180032A7F
0x18003295e  mov     rcx, [rbp+20h]; hdc
0x180032962  call    cs:__imp_SelectObject
0x180032968  test    rax, rax
0x18003296b  jnz     short loc_180032991
0x18003296d  call    cs:__imp_GetLastError
0x180032973  test    eax, eax
0x180032975  jle     short loc_18003297F
0x180032977  movzx   eax, ax
0x18003297a  or      eax, 80070000h
0x18003297f  mov     ecx, 80004005h
0x180032984  test    eax, eax
0x180032986  cmovns  eax, ecx
0x180032989  mov     ecx, eax; this
0x18003298b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180032991  mov     rdx, rbx
0x180032994  lea     rcx, [rdi+28h]
0x180032998  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18003299d  jmp     loc_180032A7F
0x1800329a2  mov     ecx, 8; Size
0x1800329a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800329ac  mov     rbx, rax
0x1800329af  mov     [rsp+48h+arg_0], rax
0x1800329b4  mov     ecx, [rsi]; color
0x1800329b6  test    ecx, ecx
0x1800329b8  jnz     short loc_1800329C7
0x1800329ba  mov     ecx, 4; i
0x1800329bf  call    cs:__imp_GetStockObject
0x1800329c5  jmp     short loc_1800329D9
0x1800329c7  cmp     ecx, 0FFFFFFh
0x1800329cd  jnz     short loc_1800329D3
0x1800329cf  xor     ecx, ecx
0x1800329d1  jmp     short loc_1800329BF
0x1800329d3  call    cs:__imp_CreateSolidBrush
0x1800329d9  mov     [rbx], rax
0x1800329dc  mov     rdx, rbx
0x1800329df  lea     rcx, [rsp+48h+var_28]
0x1800329e4  call    ??$?0U?$GDIResource@PEAUHBRUSH__@@@xgc@@$0A@@?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@QEAA@PEAU?$GDIResource@PEAUHBRUSH__@@@xgc@@@Z; std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>::shared_ptr<xgc::GDIResource<HBRUSH__ *>>(xgc::GDIResource<HBRUSH__ *> *)
0x1800329e9  nop
0x1800329ea  mov     rdx, [rsp+48h+var_28]
0x1800329ef  cmp     qword ptr [rdx], 0
0x1800329f3  jnz     short loc_180032A19
0x1800329f5  call    cs:__imp_GetLastError
0x1800329fb  test    eax, eax
0x1800329fd  jle     short loc_180032A07
0x1800329ff  movzx   eax, ax
0x180032a02  or      eax, 80070000h
0x180032a07  mov     ecx, 80004005h
0x180032a0c  test    eax, eax
0x180032a0e  cmovns  eax, ecx
0x180032a11  mov     ecx, eax; this
0x180032a13  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180032a19  mov     rdx, [rdx]; h
0x180032a1c  mov     rcx, [rbp+20h]; hdc
0x180032a20  call    cs:__imp_SelectObject
0x180032a26  test    rax, rax
0x180032a29  jnz     short loc_180032A4F
0x180032a2b  call    cs:__imp_GetLastError
0x180032a31  test    eax, eax
0x180032a33  jle     short loc_180032A3D
0x180032a35  movzx   eax, ax
0x180032a38  or      eax, 80070000h
0x180032a3d  mov     ecx, 80004005h
0x180032a42  test    eax, eax
0x180032a44  cmovns  eax, ecx
0x180032a47  mov     ecx, eax; this
0x180032a49  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180032a4f  lea     rdx, [rsp+48h+var_28]
0x180032a54  lea     rcx, [rdi+28h]
0x180032a58  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x180032a5d  mov     rdx, rsi
0x180032a60  mov     rcx, rdi
0x180032a63  call    ??A?$Cache@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@U?$Hash@K@xpsrdr@@U?$Weight@KV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@4@@xpsrdr@@QEAAAEAV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@AEBK@Z; xpsrdr::Cache<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>,xpsrdr::Hash<ulong>,xpsrdr::Weight<ulong,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>::operator[](ulong const &)
0x180032a68  mov     rcx, rax
0x180032a6b  lea     rdx, [rdi+28h]
0x180032a6f  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180032a74  nop
0x180032a75  lea     rcx, [rsp+48h+var_28]
0x180032a7a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180032a7f  mov     rbx, [rsp+48h+arg_8]
0x180032a84  add     rsp, 30h
0x180032a88  pop     rdi
0x180032a89  pop     rsi
0x180032a8a  pop     rbp
0x180032a8b  retn
```
