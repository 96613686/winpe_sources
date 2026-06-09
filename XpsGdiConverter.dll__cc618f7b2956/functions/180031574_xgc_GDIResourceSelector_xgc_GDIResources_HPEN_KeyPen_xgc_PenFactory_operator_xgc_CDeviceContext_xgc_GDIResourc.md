# xgc::GDIResourceSelector<xgc::GDIResources<HPEN__ *,KeyPen>,xgc::PenFactory>::operator()(xgc::CDeviceContext &,xgc::GDIResources<HPEN__ *,KeyPen> &,KeyPen &)

- ea: `0x180031574`
- end: `0x18003172b`
- name: `??R?$GDIResourceSelector@U?$GDIResources@PEAUHPEN__@@UKeyPen@@@xgc@@UPenFactory@2@@xgc@@QEAAXAEAVCDeviceContext@1@AEAU?$GDIResources@PEAUHPEN__@@UKeyPen@@@1@AEAUKeyPen@@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180031ebc`

## callees

- `0x180008830`
- `0x180008854`
- `0x18000d7f8`
- `0x180011b0c`
- `0x180012088`
- `0x1800184e8`
- `0x18001bc1c`
- `0x18001df40`
- `0x1800229e8`
- `0x1800314b8`
- `0x180031574`
- `0x1800323f0`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800315f4`
- `KERNEL32!GetLastError` at `0x18003168c`
- `KERNEL32!GetLastError` at `0x1800316c2`
- `KERNEL32!GetLastError` at `0x1800315f4`
- `KERNEL32!GetLastError` at `0x18003168c`
- `KERNEL32!GetLastError` at `0x1800316c2`
- `GDI32!SelectObject` at `0x1800315e9`
- `GDI32!SelectObject` at `0x1800316b7`
- `GDI32!SelectObject` at `0x1800315e9`
- `GDI32!SelectObject` at `0x1800316b7`
- `GDI32!ExtCreatePen` at `0x18003166c`
- `GDI32!ExtCreatePen` at `0x18003166c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall xgc::GDIResourceSelector<xgc::GDIResources<HPEN__ *,KeyPen>,xgc::PenFactory>::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  void *v10; // rdx
  void **result; // rax
  signed int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  HPEN *v16; // rbx
  signed int LastError; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  signed int v21; // eax
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  __int64 v25; // rax
  __int64 v26; // [rsp+30h] [rbp-20h] BYREF
  LOGBRUSH plbrush; // [rsp+38h] [rbp-18h] BYREF

  v26 = *(_QWORD *)xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::find(
                     a3,
                     &v26,
                     a4);
  v7 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a3,
                   &plbrush);
  if ( v8 == *v7 )
  {
    v16 = (HPEN *)operator new(8u);
    plbrush.lbColor = HIDWORD(v16);
    plbrush.lbStyle = 0;
    plbrush.lbColor = *(_DWORD *)a4;
    plbrush.lbHatch = 0;
    *v16 = ExtCreatePen(
             *(_DWORD *)(a4 + 4),
             *(_DWORD *)(a4 + 8),
             &plbrush,
             (__int64)(*(_QWORD *)(a4 + 24) - *(_QWORD *)(a4 + 16)) >> 2,
             *(const DWORD **)(a4 + 16));
    std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>::shared_ptr<xgc::GDIResource<HBRUSH__ *>>(&plbrush, v16);
    if ( !**(_QWORD **)&plbrush.lbStyle )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v18, v19, v20);
    }
    if ( !SelectObject(*(HDC *)(a2 + 32), **(HGDIOBJ **)&plbrush.lbStyle) )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      if ( v21 >= 0 )
        v21 = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, v22, v23, v24);
    }
    std::shared_ptr<XgcSolidPath>::swap(a3 + 40, &plbrush);
    v25 = xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::operator[](
            a3,
            a4);
    std::shared_ptr<ID2D1Brush>::operator=(v25, a3 + 40);
    return (void **)std::_Ptr_base<ID2D1RenderTarget>::_Decref(&plbrush);
  }
  else
  {
    v9 = std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>::operator*(&v26)
       + 40;
    v10 = *(void **)std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v9);
    result = *(void ***)(a3 + 40);
    if ( v10 != *result )
    {
      if ( !SelectObject(*(HDC *)(a2 + 32), v10) )
      {
        v12 = GetLastError();
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 >= 0 )
          v12 = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
      }
      return (void **)std::shared_ptr<ID2D1Brush>::operator=(a3 + 40, v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031574  push    rbp
0x180031576  push    rbx
0x180031577  push    rsi
0x180031578  push    rdi
0x180031579  push    r14
0x18003157b  mov     rbp, rsp
0x18003157e  sub     rsp, 50h
0x180031582  mov     rax, cs:__security_cookie
0x180031589  xor     rax, rsp
0x18003158c  mov     [rbp+var_8], rax
0x180031590  mov     rsi, r9
0x180031593  mov     rdi, r8
0x180031596  mov     r14, rdx
0x180031599  mov     r8, r9
0x18003159c  lea     rdx, [rbp+var_20]
0x1800315a0  mov     rcx, rdi
0x1800315a3  call    ?find@?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBUKeyPen@@@Z; xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::find(KeyPen const &)
0x1800315a8  mov     r8, [rax]
0x1800315ab  mov     [rbp+var_20], r8
0x1800315af  lea     rdx, [rbp+plbrush]
0x1800315b3  mov     rcx, rdi
0x1800315b6  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x1800315bb  cmp     r8, [rax]
0x1800315be  jz      short loc_180031629
0x1800315c0  lea     rcx, [rbp+var_20]
0x1800315c4  call    ??D?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@QEBAAEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@1@XZ; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>::operator*(void)
0x1800315c9  lea     rbx, [rax+28h]
0x1800315cd  mov     rcx, rbx
0x1800315d0  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x1800315d5  mov     rdx, [rax]; h
0x1800315d8  mov     rax, [rdi+28h]
0x1800315dc  cmp     rdx, [rax]
0x1800315df  jz      loc_180031714
0x1800315e5  mov     rcx, [r14+20h]; hdc
0x1800315e9  call    cs:__imp_SelectObject
0x1800315ef  test    rax, rax
0x1800315f2  jnz     short loc_180031618
0x1800315f4  call    cs:__imp_GetLastError
0x1800315fa  test    eax, eax
0x1800315fc  jle     short loc_180031606
0x1800315fe  movzx   eax, ax
0x180031601  or      eax, 80070000h
0x180031606  mov     ecx, 80004005h
0x18003160b  test    eax, eax
0x18003160d  cmovns  eax, ecx
0x180031610  mov     ecx, eax; this
0x180031612  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180031618  mov     rdx, rbx
0x18003161b  lea     rcx, [rdi+28h]
0x18003161f  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180031624  jmp     loc_180031714
0x180031629  mov     ecx, 8; Size
0x18003162e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031633  mov     rbx, rax
0x180031636  mov     qword ptr [rbp+plbrush.lbStyle], rax
0x18003163a  mov     [rbp+plbrush.lbStyle], 0
0x180031641  mov     ecx, [rsi]
0x180031643  mov     [rbp+plbrush.lbColor], ecx
0x180031646  mov     [rbp+plbrush.lbHatch], 0
0x18003164e  mov     rcx, [rsi+10h]
0x180031652  mov     r9, [rsi+18h]
0x180031656  sub     r9, rcx
0x180031659  sar     r9, 2; cStyle
0x18003165d  mov     [rsp+50h+pstyle], rcx; pstyle
0x180031662  lea     r8, [rbp+plbrush]; plbrush
0x180031666  mov     edx, [rsi+8]; cWidth
0x180031669  mov     ecx, [rsi+4]; iPenStyle
0x18003166c  call    cs:__imp_ExtCreatePen
0x180031672  mov     [rbx], rax
0x180031675  mov     rdx, rbx
0x180031678  lea     rcx, [rbp+plbrush]
0x18003167c  call    ??$?0U?$GDIResource@PEAUHBRUSH__@@@xgc@@$0A@@?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@QEAA@PEAU?$GDIResource@PEAUHBRUSH__@@@xgc@@@Z; std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>::shared_ptr<xgc::GDIResource<HBRUSH__ *>>(xgc::GDIResource<HBRUSH__ *> *)
0x180031681  nop
0x180031682  mov     rdx, qword ptr [rbp+plbrush.lbStyle]
0x180031686  cmp     qword ptr [rdx], 0
0x18003168a  jnz     short loc_1800316B0
0x18003168c  call    cs:__imp_GetLastError
0x180031692  test    eax, eax
0x180031694  jle     short loc_18003169E
0x180031696  movzx   eax, ax
0x180031699  or      eax, 80070000h
0x18003169e  mov     ecx, 80004005h
0x1800316a3  test    eax, eax
0x1800316a5  cmovns  eax, ecx
0x1800316a8  mov     ecx, eax; this
0x1800316aa  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800316b0  mov     rdx, [rdx]; h
0x1800316b3  mov     rcx, [r14+20h]; hdc
0x1800316b7  call    cs:__imp_SelectObject
0x1800316bd  test    rax, rax
0x1800316c0  jnz     short loc_1800316E6
0x1800316c2  call    cs:__imp_GetLastError
0x1800316c8  test    eax, eax
0x1800316ca  jle     short loc_1800316D4
0x1800316cc  movzx   eax, ax
0x1800316cf  or      eax, 80070000h
0x1800316d4  mov     ecx, 80004005h
0x1800316d9  test    eax, eax
0x1800316db  cmovns  eax, ecx
0x1800316de  mov     ecx, eax; this
0x1800316e0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800316e6  lea     rdx, [rbp+plbrush]
0x1800316ea  lea     rcx, [rdi+28h]
0x1800316ee  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x1800316f3  mov     rdx, rsi
0x1800316f6  mov     rcx, rdi
0x1800316f9  call    ??A?$Cache@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@U?$Hash@UKeyPen@@@xpsrdr@@U?$Weight@UKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@5@@xpsrdr@@QEAAAEAV?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@AEBUKeyPen@@@Z; xpsrdr::Cache<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>,xpsrdr::Hash<KeyPen>,xpsrdr::Weight<KeyPen,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::operator[](KeyPen const &)
0x1800316fe  mov     rcx, rax
0x180031701  lea     rdx, [rdi+28h]
0x180031705  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18003170a  nop
0x18003170b  lea     rcx, [rbp+plbrush]
0x18003170f  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180031714  mov     rcx, [rbp+var_8]
0x180031718  xor     rcx, rsp; StackCookie
0x18003171b  call    __security_check_cookie
0x180031720  add     rsp, 50h
0x180031724  pop     r14
0x180031726  pop     rdi
0x180031727  pop     rsi
0x180031728  pop     rbx
0x180031729  pop     rbp
0x18003172a  retn
```
