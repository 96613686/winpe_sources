# xgc::GDIResourceSelector<xgc::GDIResources<HFONT__ *,tagLOGFONTW>,xgc::FontFactory>::operator()(xgc::CDeviceContext &,xgc::GDIResources<HFONT__ *,tagLOGFONTW> &,tagLOGFONTW &)

- ea: `0x18001dff0`
- end: `0x18001e16c`
- name: `??R?$GDIResourceSelector@U?$GDIResources@PEAUHFONT__@@UtagLOGFONTW@@@xgc@@UFontFactory@2@@xgc@@QEAAXAEAVCDeviceContext@1@AEAU?$GDIResources@PEAUHFONT__@@UtagLOGFONTW@@@1@AEAUtagLOGFONTW@@@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800211f4`

## callees

- `0x180008854`
- `0x18000d7f8`
- `0x180011b0c`
- `0x180012088`
- `0x1800184e8`
- `0x18001bc1c`
- `0x18001de6c`
- `0x18001df40`
- `0x18001dff0`
- `0x1800229e8`
- `0x180022bec`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e069`
- `KERNEL32!GetLastError` at `0x18001e0d5`
- `KERNEL32!GetLastError` at `0x18001e10b`
- `KERNEL32!GetLastError` at `0x18001e069`
- `KERNEL32!GetLastError` at `0x18001e0d5`
- `KERNEL32!GetLastError` at `0x18001e10b`
- `GDI32!CreateFontIndirectW` at `0x18001e0b3`
- `GDI32!CreateFontIndirectW` at `0x18001e0b3`
- `GDI32!SelectObject` at `0x18001e05e`
- `GDI32!SelectObject` at `0x18001e100`
- `GDI32!SelectObject` at `0x18001e05e`
- `GDI32!SelectObject` at `0x18001e100`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall xgc::GDIResourceSelector<xgc::GDIResources<HFONT__ *,tagLOGFONTW>,xgc::FontFactory>::operator()(
        HFONT *a1,
        __int64 a2,
        __int64 a3,
        const LOGFONTW *a4)
{
  _QWORD *v7; // rax
  __int64 v8; // r10
  __int64 v9; // rbx
  void *v10; // rdx
  void **result; // rax
  signed int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  HFONT *v16; // rbx
  signed int LastError; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  signed int v21; // eax
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  __int64 v25; // rax
  _QWORD v26[5]; // [rsp+20h] [rbp-28h] BYREF
  HFONT *v27; // [rsp+50h] [rbp+8h] BYREF
  char v28; // [rsp+60h] [rbp+18h] BYREF

  v27 = a1;
  v27 = *(HFONT **)xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::find(
                     a3,
                     &v27,
                     a4);
  v7 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a3,
                   &v28);
  if ( v8 == *v7 )
  {
    v16 = (HFONT *)operator new(8u);
    v27 = v16;
    *v16 = CreateFontIndirectW(a4);
    std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>::shared_ptr<xgc::GDIResource<HBRUSH__ *>>(v26, v16);
    if ( !*(_QWORD *)v26[0] )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v18, v19, v20);
    }
    if ( !SelectObject(*(HDC *)(a2 + 32), *(HGDIOBJ *)v26[0]) )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      if ( v21 >= 0 )
        v21 = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, v22, v23, v24);
    }
    std::shared_ptr<XgcSolidPath>::swap(a3 + 40, v26);
    v25 = xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::operator[](
            a3,
            a4);
    std::shared_ptr<ID2D1Brush>::operator=(v25, a3 + 40);
    return (void **)std::_Ptr_base<ID2D1RenderTarget>::_Decref(v26);
  }
  else
  {
    v9 = std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>::operator*(&v27)
       + 96;
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
0x18001dff0  mov     [rsp+arg_8], rbx
0x18001dff5  mov     [rsp+arg_0], rcx
0x18001dffa  push    rbp
0x18001dffb  push    rsi
0x18001dffc  push    rdi
0x18001dffd  sub     rsp, 30h
0x18001e001  mov     rsi, r9
0x18001e004  mov     rdi, r8
0x18001e007  mov     rbp, rdx
0x18001e00a  mov     r8, r9
0x18001e00d  lea     rdx, [rsp+48h+arg_0]
0x18001e012  mov     rcx, rdi
0x18001e015  call    ?find@?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@std@@@std@@@std@@@std@@AEBUtagLOGFONTW@@@Z; xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::find(tagLOGFONTW const &)
0x18001e01a  mov     r10, [rax]
0x18001e01d  mov     [rsp+48h+arg_0], r10
0x18001e022  lea     rdx, [rsp+48h+arg_10]
0x18001e027  mov     rcx, rdi
0x18001e02a  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x18001e02f  cmp     r10, [rax]
0x18001e032  jz      short loc_18001E09E
0x18001e034  lea     rcx, [rsp+48h+arg_0]
0x18001e039  call    ??D?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@QEBAAEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@1@XZ; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>::operator*(void)
0x18001e03e  lea     rbx, [rax+60h]
0x18001e042  mov     rcx, rbx
0x18001e045  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x18001e04a  mov     rdx, [rax]; h
0x18001e04d  mov     rax, [rdi+28h]
0x18001e051  cmp     rdx, [rax]
0x18001e054  jz      loc_18001E15F
0x18001e05a  mov     rcx, [rbp+20h]; hdc
0x18001e05e  call    cs:__imp_SelectObject
0x18001e064  test    rax, rax
0x18001e067  jnz     short loc_18001E08D
0x18001e069  call    cs:__imp_GetLastError
0x18001e06f  test    eax, eax
0x18001e071  jle     short loc_18001E07B
0x18001e073  movzx   eax, ax
0x18001e076  or      eax, 80070000h
0x18001e07b  mov     ecx, 80004005h
0x18001e080  test    eax, eax
0x18001e082  cmovns  eax, ecx
0x18001e085  mov     ecx, eax; this
0x18001e087  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001e08d  mov     rdx, rbx
0x18001e090  lea     rcx, [rdi+28h]
0x18001e094  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18001e099  jmp     loc_18001E15F
0x18001e09e  mov     ecx, 8; Size
0x18001e0a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e0a8  mov     rbx, rax
0x18001e0ab  mov     [rsp+48h+arg_0], rax
0x18001e0b0  mov     rcx, rsi; lplf
0x18001e0b3  call    cs:__imp_CreateFontIndirectW
0x18001e0b9  mov     [rbx], rax
0x18001e0bc  mov     rdx, rbx
0x18001e0bf  lea     rcx, [rsp+48h+var_28]
0x18001e0c4  call    ??$?0U?$GDIResource@PEAUHBRUSH__@@@xgc@@$0A@@?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@QEAA@PEAU?$GDIResource@PEAUHBRUSH__@@@xgc@@@Z; std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>::shared_ptr<xgc::GDIResource<HBRUSH__ *>>(xgc::GDIResource<HBRUSH__ *> *)
0x18001e0c9  nop
0x18001e0ca  mov     rdx, [rsp+48h+var_28]
0x18001e0cf  cmp     qword ptr [rdx], 0
0x18001e0d3  jnz     short loc_18001E0F9
0x18001e0d5  call    cs:__imp_GetLastError
0x18001e0db  test    eax, eax
0x18001e0dd  jle     short loc_18001E0E7
0x18001e0df  movzx   eax, ax
0x18001e0e2  or      eax, 80070000h
0x18001e0e7  mov     ecx, 80004005h
0x18001e0ec  test    eax, eax
0x18001e0ee  cmovns  eax, ecx
0x18001e0f1  mov     ecx, eax; this
0x18001e0f3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001e0f9  mov     rdx, [rdx]; h
0x18001e0fc  mov     rcx, [rbp+20h]; hdc
0x18001e100  call    cs:__imp_SelectObject
0x18001e106  test    rax, rax
0x18001e109  jnz     short loc_18001E12F
0x18001e10b  call    cs:__imp_GetLastError
0x18001e111  test    eax, eax
0x18001e113  jle     short loc_18001E11D
0x18001e115  movzx   eax, ax
0x18001e118  or      eax, 80070000h
0x18001e11d  mov     ecx, 80004005h
0x18001e122  test    eax, eax
0x18001e124  cmovns  eax, ecx
0x18001e127  mov     ecx, eax; this
0x18001e129  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001e12f  lea     rdx, [rsp+48h+var_28]
0x18001e134  lea     rcx, [rdi+28h]
0x18001e138  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x18001e13d  mov     rdx, rsi
0x18001e140  mov     rcx, rdi
0x18001e143  call    ??A?$Cache@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@U?$Hash@UtagLOGFONTW@@@xpsrdr@@U?$Weight@UtagLOGFONTW@@V?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@@5@@xpsrdr@@QEAAAEAV?$shared_ptr@U?$GDIResource@PEAUHFONT__@@@xgc@@@std@@AEBUtagLOGFONTW@@@Z; xpsrdr::Cache<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>,xpsrdr::Hash<tagLOGFONTW>,xpsrdr::Weight<tagLOGFONTW,std::shared_ptr<xgc::GDIResource<HFONT__ *>>>>::operator[](tagLOGFONTW const &)
0x18001e148  mov     rcx, rax
0x18001e14b  lea     rdx, [rdi+28h]
0x18001e14f  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18001e154  nop
0x18001e155  lea     rcx, [rsp+48h+var_28]
0x18001e15a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001e15f  mov     rbx, [rsp+48h+arg_8]
0x18001e164  add     rsp, 30h
0x18001e168  pop     rdi
0x18001e169  pop     rsi
0x18001e16a  pop     rbp
0x18001e16b  retn
```
