# xpsrdr::RenderState::RenderState(__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001,__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001,__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001,std::shared_ptr<IWICImagingFactory>)

- ea: `0x1800ac0f4`
- end: `0x1800ac59e`
- name: `??0RenderState@xpsrdr@@QEAA@W4__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001@@0W4__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001@@V?$shared_ptr@UIWICImagingFactory@@@std@@@Z`
- size: `1194`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x1800a8334`
- `0x1800a848c`

## callees

- `0x180003180`
- `0x18000358c`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a9ffc`
- `0x1800ab0fc`
- `0x1800abb8c`
- `0x1800abe60`
- `0x1800abec4`
- `0x1800abee0`
- `0x1800abefc`
- `0x1800abf50`
- `0x1800abfa4`
- `0x1800abff8`
- `0x1800ac04c`
- `0x1800ac0a0`
- `0x1800ac0f4`
- `0x1800ac7b8`
- `0x1800acfc8`
- `0x1800acffc`
- `0x1800ad030`
- `0x1800ad68c`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800b27d8`
- `0x1800c3010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x1800ac381`
- `d2d1!__imp_D2D1CreateFactory` at `0x1800ac381`
- `DWrite!DWriteCreateFactory` at `0x1800ac3d1`
- `DWrite!DWriteCreateFactory` at `0x1800ac3d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall xpsrdr::RenderState::RenderState(__int64 a1, int a2, int a3, int a4, _QWORD *a5)
{
  __int64 v9; // rax
  const char *v10; // rdx
  xpsrdr *v11; // rcx
  int v12; // r8d
  int v13; // eax
  int v14; // eax
  int v15; // ebx
  int v16; // ebx
  GUID v17; // xmm0
  HRESULT v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  _QWORD *v22; // rsi
  int v23; // ebx
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  int D3DDevice; // ebx
  const char *v28; // rdx
  const char *v29; // r8
  int v30; // r9d
  _QWORD *v31; // rcx
  int v32; // eax
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  xpsrdr *v36; // rax
  _QWORD *v37; // rcx
  int v38; // eax
  int v39; // edx
  xpsrdr *v40; // rcx
  const char *v41; // r8
  int v42; // r9d
  std::_Ref_count_base *v43; // rcx
  xpsrdr *v45; // [rsp+20h] [rbp-51h] BYREF
  void *ppIFactory; // [rsp+28h] [rbp-49h] BYREF
  xpsrdr **v47; // [rsp+30h] [rbp-41h]
  __int64 v48; // [rsp+38h] [rbp-39h]
  D2D1_FACTORY_OPTIONS pFactoryOptions; // [rsp+40h] [rbp-31h] BYREF
  __int64 v50; // [rsp+48h] [rbp-29h]
  _QWORD *v51; // [rsp+50h] [rbp-21h]
  struct ID3D11Device *v52[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v53; // [rsp+68h] [rbp-9h]

  v50 = a1;
  v51 = a5;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v9 = a5[1];
  if ( v9 )
    _InterlockedAdd((volatile signed __int32 *)(v9 + 8), 1u);
  *(_QWORD *)a1 = *a5;
  *(_QWORD *)(a1 + 8) = a5[1];
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>(a1 + 120);
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>(a1 + 160);
  xpsrdr::Cache<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>,xpsrdr::Hash<xpsrdr::KeySolidColorBrush>,xpsrdr::Weight<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>>>::Cache<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>,xpsrdr::Hash<xpsrdr::KeySolidColorBrush>,xpsrdr::Weight<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>>>(a1 + 200);
  xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>(a1 + 240);
  xpsrdr::Cache<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>,xpsrdr::Hash<xpsrdr::KeyStrokeStyle>,xpsrdr::Weight<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>>>::Cache<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>,xpsrdr::Hash<xpsrdr::KeyStrokeStyle>,xpsrdr::Weight<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>>>(a1 + 280);
  xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>(a1 + 320);
  *(_QWORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 368) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::_Alloc_sentinel_and_proxy();
  xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>(a1 + 376);
  *(_QWORD *)(a1 + 416) = 0;
  *(_QWORD *)(a1 + 424) = 0;
  std::_Tree<std::_Tmap_traits<IXpsOMGlyphs *,D2D_RECT_F,std::less<IXpsOMGlyphs *>,std::allocator<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>>,0>>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  std::_Tree<std::_Tmap_traits<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>,0>>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  *(_QWORD *)(a1 + 464) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_WORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 496) = 0;
  *(_QWORD *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 512) = 0;
  *(_QWORD *)(a1 + 520) = 0;
  ((void (*)(void))std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>)();
  *(_DWORD *)(a1 + 528) = 0;
  *(_QWORD *)(a1 + 532) = 1;
  *(_DWORD *)(a1 + 540) = 0;
  v45 = (xpsrdr *)operator new(0x98u);
  *(_QWORD *)(a1 + 544) = xpsrdr::Stat::Stat(v45);
  *(_QWORD *)(a1 + 552) = 0;
  *(_QWORD *)(a1 + 560) = 0;
  *(_QWORD *)(a1 + 568) = 0;
  *(_QWORD *)(a1 + 576) = 0;
  *(_QWORD *)(a1 + 584) = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(a1 + 552);
  if ( a2 )
  {
    if ( a2 != 1 )
      xpsrdr::ThrowLogicException(v11, v10, v12);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  *(_DWORD *)(a1 + 88) = v13;
  *(_DWORD *)(a1 + 96) = v13;
  if ( a3 )
  {
    if ( a3 != 1 )
      xpsrdr::ThrowLogicException(v11, v10, v12);
    v14 = 3;
  }
  else
  {
    v14 = 2;
  }
  *(_DWORD *)(a1 + 92) = v14;
  v15 = a4 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( v16 != 1 )
        xpsrdr::ThrowLogicException(v11, v10, v12);
      v17 = GUID_WICPixelFormat128bppPRGBAFloat;
    }
    else
    {
      v17 = GUID_WICPixelFormat64bppPRGBAHalf;
    }
  }
  else
  {
    v17 = GUID_WICPixelFormat32bppPBGRA;
  }
  *(GUID *)(a1 + 100) = v17;
  pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE;
  LODWORD(v45) = 0;
  ppIFactory = 0;
  v47 = &v45;
  v48 = a1 + 16;
  v18 = D2D1CreateFactory(
          D2D1_FACTORY_TYPE_SINGLE_THREADED,
          &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f,
          &pFactoryOptions,
          &ppIFactory);
  detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(&ppIFactory);
  if ( (int)v45 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v45, v19, v20, v21);
  if ( v18 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  LODWORD(v45) = 0;
  ppIFactory = 0;
  v47 = &v45;
  v22 = (_QWORD *)(a1 + 32);
  v48 = a1 + 32;
  v23 = DWriteCreateFactory(1, &GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48, &ppIFactory);
  detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(&ppIFactory);
  if ( (int)v45 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v45, v24, v25, v26);
  if ( v23 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
  LODWORD(v45) = 0;
  v52[0] = 0;
  v52[1] = (struct ID3D11Device *)&v45;
  v53 = a1 + 64;
  ppIFactory = 0;
  v47 = &v45;
  v48 = a1 + 48;
  D3DDevice = xpsrdr::CreateD3DDevice(
                (D3D_FEATURE_LEVEL *)(a1 + 80),
                (enum D3D_FEATURE_LEVEL *)(a1 + 84),
                (std::_Ref_count_base **)&ppIFactory,
                v52);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppIFactory);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v52);
  if ( (int)v45 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v45, (int)v28, v29, v30);
  if ( D3DDevice < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)D3DDevice, (int)v28, v29, v30);
  if ( !*(_QWORD *)(a1 + 48) )
    xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)v45, v28, (int)v29);
  if ( !*(_QWORD *)(a1 + 64) )
    xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)v45, v28, (int)v29);
  if ( (unsigned int)(*(_DWORD *)(a1 + 84) - 1) > 1 )
    xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)v45, v28, (int)v29);
  v45 = (xpsrdr *)operator new(0x18u);
  CUnknownBase<IDWriteFontFileLoader>::CUnknownBase<IDWriteFontFileLoader>(v45);
  *v31 = &xpsrdr::FontLoader::`vftable';
  v31[2] = a1;
  resetNoAddRef<xpsrdr::SourceColorBitmap>(a1 + 448, v31);
  v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v22 + 104LL))(*v22, *(_QWORD *)(a1 + 448));
  if ( v32 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v33, v34, v35);
  v36 = (xpsrdr *)operator new(0x10u);
  v45 = v36;
  *(_OWORD *)v36 = 0;
  CUnknownBase<IDWriteFontCollectionLoader>::CUnknownBase<IDWriteFontCollectionLoader>(v36);
  *v37 = &xpsrdr::XpsToSystemFontCollectionLoader::`vftable';
  resetNoAddRef<xpsrdr::SourceColorBitmap>(a1 + 464, v37);
  v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v22 + 40LL))(*v22, *(_QWORD *)(a1 + 464));
  if ( v38 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, v39, v41, v42);
  *(_BYTE *)(a1 + 480) = xpsrdr::IsMatchingSystemFonts(v40);
  *(__m128i *)v52 = _mm_load_si128((const __m128i *)&_xmm);
  v53 = 0;
  std::stack<D2D_MATRIX_3X2_F>::push(a1 + 488, v52);
  v43 = (std::_Ref_count_base *)a5[1];
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  return a1;
}

```

## disassembly

```asm
0x1800ac0f4  push    rbp
0x1800ac0f6  push    rbx
0x1800ac0f7  push    rsi
0x1800ac0f8  push    rdi
0x1800ac0f9  push    r12
0x1800ac0fb  push    r13
0x1800ac0fd  push    r14
0x1800ac0ff  push    r15
0x1800ac101  lea     rbp, [rsp-17h]
0x1800ac106  sub     rsp, 88h
0x1800ac10d  mov     rax, cs:__security_cookie
0x1800ac114  xor     rax, rsp
0x1800ac117  mov     [rbp+4Fh+var_50], rax
0x1800ac11b  mov     ebx, r9d
0x1800ac11e  mov     esi, r8d
0x1800ac121  mov     r14d, edx
0x1800ac124  mov     rdi, rcx
0x1800ac127  mov     [rbp+4Fh+var_78], rcx
0x1800ac12b  mov     r15, [rbp+4Fh+arg_20]
0x1800ac12f  mov     [rbp+4Fh+var_70], r15
0x1800ac133  xor     r12d, r12d
0x1800ac136  mov     [rcx], r12
0x1800ac139  mov     [rcx+8], r12
0x1800ac13d  mov     rax, [r15+8]
0x1800ac141  lea     r13d, [r12+1]
0x1800ac146  test    rax, rax
0x1800ac149  jz      short loc_1800AC150
0x1800ac14b  lock add [rax+8], r13d
0x1800ac150  mov     rax, [r15]
0x1800ac153  mov     [rcx], rax
0x1800ac156  mov     rax, [r15+8]
0x1800ac15a  mov     [rcx+8], rax
0x1800ac15e  mov     [rcx+10h], r12
0x1800ac162  mov     [rcx+18h], r12
0x1800ac166  mov     [rcx+20h], r12
0x1800ac16a  mov     [rcx+28h], r12
0x1800ac16e  mov     [rcx+30h], r12
0x1800ac172  mov     [rcx+38h], r12
0x1800ac176  mov     [rcx+40h], r12
0x1800ac17a  mov     [rcx+48h], r12
0x1800ac17e  add     rcx, 78h ; 'x'
0x1800ac182  movss   xmm1, cs:__real@41000000
0x1800ac18a  call    ??0?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>(float)
0x1800ac18f  nop
0x1800ac190  lea     rcx, [rdi+0A0h]
0x1800ac197  movss   xmm1, cs:__real@41800000
0x1800ac19f  call    ??0?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>(float)
0x1800ac1a4  nop
0x1800ac1a5  lea     rcx, [rdi+0C8h]
0x1800ac1ac  movss   xmm1, cs:__real@43000000
0x1800ac1b4  call    ??0?$Cache@UKeySolidColorBrush@xpsrdr@@V?$shared_ptr@UID2D1Brush@@@std@@U?$Hash@UKeySolidColorBrush@xpsrdr@@@2@U?$Weight@UKeySolidColorBrush@xpsrdr@@V?$shared_ptr@UID2D1Brush@@@std@@@2@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>,xpsrdr::Hash<xpsrdr::KeySolidColorBrush>,xpsrdr::Weight<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>>>::Cache<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>,xpsrdr::Hash<xpsrdr::KeySolidColorBrush>,xpsrdr::Weight<xpsrdr::KeySolidColorBrush,std::shared_ptr<ID2D1Brush>>>(float)
0x1800ac1b9  nop
0x1800ac1ba  lea     rcx, [rdi+0F0h]
0x1800ac1c1  movss   xmm1, cs:__real@41800000
0x1800ac1c9  call    ??0?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>(float)
0x1800ac1ce  nop
0x1800ac1cf  lea     rcx, [rdi+118h]
0x1800ac1d6  movss   xmm1, cs:__real@43000000
0x1800ac1de  call    ??0?$Cache@UKeyStrokeStyle@xpsrdr@@V?$shared_ptr@UID2D1StrokeStyle@@@std@@U?$Hash@UKeyStrokeStyle@xpsrdr@@@2@U?$Weight@UKeyStrokeStyle@xpsrdr@@V?$shared_ptr@UID2D1StrokeStyle@@@std@@@2@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>,xpsrdr::Hash<xpsrdr::KeyStrokeStyle>,xpsrdr::Weight<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>>>::Cache<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>,xpsrdr::Hash<xpsrdr::KeyStrokeStyle>,xpsrdr::Weight<xpsrdr::KeyStrokeStyle,std::shared_ptr<ID2D1StrokeStyle>>>(float)
0x1800ac1e3  nop
0x1800ac1e4  lea     rcx, [rdi+140h]
0x1800ac1eb  movss   xmm1, cs:__real@41000000
0x1800ac1f3  call    ??0?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>(float)
0x1800ac1f8  nop
0x1800ac1f9  lea     rcx, [rdi+168h]
0x1800ac200  mov     [rcx], r12
0x1800ac203  mov     [rcx+8], r12
0x1800ac207  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,xpsrdr::FontFileData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,xpsrdr::FontFileData>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800ac20c  nop
0x1800ac20d  lea     rcx, [rdi+178h]
0x1800ac214  movss   xmm1, cs:__real@42400000
0x1800ac21c  call    ??0?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEAA@M@Z; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>(float)
0x1800ac221  nop
0x1800ac222  lea     rcx, [rdi+1A0h]
0x1800ac229  mov     [rcx], r12
0x1800ac22c  mov     [rcx+8], r12
0x1800ac230  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEAUIXpsOMGlyphs@@UD2D_RECT_F@@U?$less@PEAUIXpsOMGlyphs@@@std@@V?$allocator@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<IXpsOMGlyphs *,D2D_RECT_F,std::less<IXpsOMGlyphs *>,std::allocator<std::pair<IXpsOMGlyphs * const,D2D_RECT_F>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800ac235  nop
0x1800ac236  lea     rcx, [rdi+1B0h]
0x1800ac23d  mov     [rcx], r12
0x1800ac240  mov     [rcx+8], r12
0x1800ac244  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@UPathGeometryKey@xpsrdr@@UD2D_RECT_F@@U?$less@UPathGeometryKey@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<xpsrdr::PathGeometryKey,D2D_RECT_F,std::less<xpsrdr::PathGeometryKey>,std::allocator<std::pair<xpsrdr::PathGeometryKey const,D2D_RECT_F>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800ac249  nop
0x1800ac24a  mov     [rdi+1C0h], r12
0x1800ac251  mov     [rdi+1C8h], r12
0x1800ac258  mov     [rdi+1D0h], r12
0x1800ac25f  mov     [rdi+1D8h], r12
0x1800ac266  mov     [rdi+1E0h], r12w
0x1800ac26e  lea     rcx, [rdi+1E8h]
0x1800ac275  mov     [rcx], r12
0x1800ac278  mov     [rcx+8], r12
0x1800ac27c  mov     [rcx+10h], r12
0x1800ac280  mov     [rcx+18h], r12
0x1800ac284  mov     [rcx+20h], r12
0x1800ac288  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1800ac28d  nop
0x1800ac28e  mov     [rdi+210h], r12d
0x1800ac295  mov     qword ptr [rdi+214h], 1
0x1800ac2a0  mov     [rdi+21Ch], r12d
0x1800ac2a7  mov     ecx, 98h; Size
0x1800ac2ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac2b1  mov     [rbp+4Fh+var_A0], rax
0x1800ac2b5  mov     rcx, rax; this
0x1800ac2b8  call    ??0Stat@xpsrdr@@QEAA@XZ; xpsrdr::Stat::Stat(void)
0x1800ac2bd  mov     [rdi+220h], rax
0x1800ac2c4  lea     rcx, [rdi+228h]
0x1800ac2cb  mov     [rcx], r12
0x1800ac2ce  mov     [rcx+8], r12
0x1800ac2d2  mov     [rcx+10h], r12
0x1800ac2d6  mov     [rcx+18h], r12
0x1800ac2da  mov     [rcx+20h], r12
0x1800ac2de  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1800ac2e3  nop
0x1800ac2e4  test    r14d, r14d
0x1800ac2e7  jz      short loc_1800AC2FA
0x1800ac2e9  cmp     r14d, 1
0x1800ac2ed  jz      short loc_1800AC2F5
0x1800ac2ef  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800ac2f5  mov     eax, r13d
0x1800ac2f8  jmp     short loc_1800AC2FD
0x1800ac2fa  mov     eax, r12d
0x1800ac2fd  mov     [rdi+58h], eax
0x1800ac300  mov     [rdi+60h], eax
0x1800ac303  test    esi, esi
0x1800ac305  jz      short loc_1800AC319
0x1800ac307  cmp     esi, 1
0x1800ac30a  jz      short loc_1800AC312
0x1800ac30c  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800ac312  mov     eax, 3
0x1800ac317  jmp     short loc_1800AC31E
0x1800ac319  mov     eax, 2
0x1800ac31e  mov     [rdi+5Ch], eax
0x1800ac321  sub     ebx, 1
0x1800ac324  jz      short loc_1800AC348
0x1800ac326  sub     ebx, 1
0x1800ac329  jz      short loc_1800AC33F
0x1800ac32b  cmp     ebx, 1
0x1800ac32e  jz      short loc_1800AC336
0x1800ac330  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800ac336  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat128bppPRGBAFloat.Data1
0x1800ac33d  jmp     short loc_1800AC34F
0x1800ac33f  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat64bppPRGBAHalf.Data1
0x1800ac346  jmp     short loc_1800AC34F
0x1800ac348  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppPBGRA.Data1
0x1800ac34f  movdqu  xmmword ptr [rdi+64h], xmm0
0x1800ac354  mov     [rbp+4Fh+pFactoryOptions.debugLevel], r12d
0x1800ac358  mov     dword ptr [rbp+4Fh+var_A0], r12d
0x1800ac35c  mov     [rbp+4Fh+ppIFactory], r12
0x1800ac360  lea     rax, [rbp+4Fh+var_A0]
0x1800ac364  mov     [rbp+4Fh+var_90], rax
0x1800ac368  lea     rax, [rdi+10h]
0x1800ac36c  mov     [rbp+4Fh+var_88], rax
0x1800ac370  lea     r9, [rbp+4Fh+ppIFactory]; ppIFactory
0x1800ac374  lea     r8, [rbp+4Fh+pFactoryOptions]; pFactoryOptions
0x1800ac378  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x1800ac37f  xor     ecx, ecx; factoryType
0x1800ac381  call    cs:__imp_D2D1CreateFactory
0x1800ac387  mov     ebx, eax
0x1800ac389  lea     rcx, [rbp+4Fh+ppIFactory]
0x1800ac38d  call    ??1?$ComReset@UID2D1RenderTarget@@@detail@@QEAA@XZ; detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(void)
0x1800ac392  mov     ecx, dword ptr [rbp+4Fh+var_A0]; this
0x1800ac395  test    ecx, ecx
0x1800ac397  jns     short loc_1800AC39F
0x1800ac399  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac39f  test    ebx, ebx
0x1800ac3a1  jns     short loc_1800AC3AB
0x1800ac3a3  mov     ecx, ebx; this
0x1800ac3a5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac3ab  mov     dword ptr [rbp+4Fh+var_A0], r12d
0x1800ac3af  mov     [rbp+4Fh+ppIFactory], r12
0x1800ac3b3  lea     rax, [rbp+4Fh+var_A0]
0x1800ac3b7  mov     [rbp+4Fh+var_90], rax
0x1800ac3bb  lea     rsi, [rdi+20h]
0x1800ac3bf  mov     [rbp+4Fh+var_88], rsi
0x1800ac3c3  lea     r8, [rbp+4Fh+ppIFactory]
0x1800ac3c7  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x1800ac3ce  mov     ecx, r13d
0x1800ac3d1  call    cs:__imp_DWriteCreateFactory
0x1800ac3d7  mov     ebx, eax
0x1800ac3d9  lea     rcx, [rbp+4Fh+ppIFactory]
0x1800ac3dd  call    ??1?$ComReset@UID2D1RenderTarget@@@detail@@QEAA@XZ; detail::ComReset<ID2D1RenderTarget>::~ComReset<ID2D1RenderTarget>(void)
0x1800ac3e2  mov     ecx, dword ptr [rbp+4Fh+var_A0]; this
0x1800ac3e5  test    ecx, ecx
0x1800ac3e7  jns     short loc_1800AC3EF
0x1800ac3e9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac3ef  test    ebx, ebx
0x1800ac3f1  jns     short loc_1800AC3FB
0x1800ac3f3  mov     ecx, ebx; this
0x1800ac3f5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac3fb  mov     dword ptr [rbp+4Fh+var_A0], r12d
0x1800ac3ff  mov     [rbp+4Fh+var_68], r12
0x1800ac403  lea     rax, [rbp+4Fh+var_A0]
0x1800ac407  mov     [rbp+4Fh+var_68+8], rax
0x1800ac40b  lea     r14, [rdi+40h]
0x1800ac40f  mov     [rbp+4Fh+var_58], r14
0x1800ac413  mov     [rbp+4Fh+ppIFactory], r12
0x1800ac417  lea     rax, [rbp+4Fh+var_A0]
0x1800ac41b  mov     [rbp+4Fh+var_90], rax
0x1800ac41f  lea     r12, [rdi+30h]
0x1800ac423  mov     [rbp+4Fh+var_88], r12
0x1800ac427  lea     rcx, [rdi+50h]; pFeatureLevel
0x1800ac42b  lea     r9, [rbp+4Fh+var_68]; struct ID3D11Device **
0x1800ac42f  lea     r8, [rbp+4Fh+ppIFactory]; enum xpsrdr::XPSRAS_DRIVER_TYPE *
0x1800ac433  lea     rdx, [rdi+54h]; enum D3D_FEATURE_LEVEL *
0x1800ac437  call    ?CreateD3DDevice@xpsrdr@@YAJPEAW4D3D_FEATURE_LEVEL@@PEAW4XPSRAS_DRIVER_TYPE@1@PEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@@Z; xpsrdr::CreateD3DDevice(D3D_FEATURE_LEVEL *,xpsrdr::XPSRAS_DRIVER_TYPE *,ID3D11Device * *,ID3D11DeviceContext * *)
0x1800ac43c  mov     ebx, eax
0x1800ac43e  lea     rcx, [rbp+4Fh+ppIFactory]
0x1800ac442  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ac447  nop
0x1800ac448  lea     rcx, [rbp+4Fh+var_68]
0x1800ac44c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800ac451  mov     ecx, dword ptr [rbp+4Fh+var_A0]; this
0x1800ac454  test    ecx, ecx
0x1800ac456  jns     short loc_1800AC45E
0x1800ac458  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac45e  test    ebx, ebx
0x1800ac460  jns     short loc_1800AC46A
0x1800ac462  mov     ecx, ebx; this
0x1800ac464  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac46a  cmp     qword ptr [r12], 0
0x1800ac46f  jnz     short loc_1800AC477
0x1800ac471  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800ac477  cmp     qword ptr [r14], 0
0x1800ac47b  jnz     short loc_1800AC483
0x1800ac47d  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800ac483  mov     eax, [rdi+54h]
0x1800ac486  dec     eax
0x1800ac488  cmp     eax, 1
0x1800ac48b  jbe     short loc_1800AC493
0x1800ac48d  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800ac493  mov     ecx, 18h; Size
0x1800ac498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac49d  mov     rcx, rax
0x1800ac4a0  mov     [rbp+4Fh+var_A0], rax
0x1800ac4a4  call    ??0?$CUnknownBase@UIDWriteFontFileLoader@@@@QEAA@XZ; CUnknownBase<IDWriteFontFileLoader>::CUnknownBase<IDWriteFontFileLoader>(void)
0x1800ac4a9  lea     rdx, ??_7FontLoader@xpsrdr@@6B@; const xpsrdr::FontLoader::`vftable'
0x1800ac4b0  mov     [rcx], rdx
0x1800ac4b3  mov     [rcx+10h], rdi
0x1800ac4b7  lea     rbx, [rdi+1C0h]
0x1800ac4be  mov     rdx, rcx
0x1800ac4c1  mov     rcx, rbx
0x1800ac4c4  call    ??$resetNoAddRef@USourceColorBitmap@xpsrdr@@@@YAXAEAV?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@PEAUSourceColorBitmap@xpsrdr@@@Z; resetNoAddRef<xpsrdr::SourceColorBitmap>(std::shared_ptr<xpsrdr::SourceColorBitmap> &,xpsrdr::SourceColorBitmap *)
0x1800ac4c9  mov     rcx, [rsi]
0x1800ac4cc  mov     rax, [rcx]
0x1800ac4cf  mov     rdx, [rbx]
0x1800ac4d2  mov     rax, [rax+68h]
0x1800ac4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac4db  test    eax, eax
0x1800ac4dd  jns     short loc_1800AC4E7
0x1800ac4df  mov     ecx, eax; this
0x1800ac4e1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac4e7  mov     ecx, 10h; Size
0x1800ac4ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac4f1  mov     rcx, rax
0x1800ac4f4  mov     [rbp+4Fh+var_A0], rax
0x1800ac4f8  xorps   xmm0, xmm0
0x1800ac4fb  movups  xmmword ptr [rax], xmm0
0x1800ac4fe  call    ??0?$CUnknownBase@UIDWriteFontCollectionLoader@@@@QEAA@XZ; CUnknownBase<IDWriteFontCollectionLoader>::CUnknownBase<IDWriteFontCollectionLoader>(void)
0x1800ac503  lea     rdx, ??_7XpsToSystemFontCollectionLoader@xpsrdr@@6B@; const xpsrdr::XpsToSystemFontCollectionLoader::`vftable'
0x1800ac50a  mov     [rcx], rdx
0x1800ac50d  lea     rbx, [rdi+1D0h]
0x1800ac514  mov     rdx, rcx
0x1800ac517  mov     rcx, rbx
0x1800ac51a  call    ??$resetNoAddRef@USourceColorBitmap@xpsrdr@@@@YAXAEAV?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@PEAUSourceColorBitmap@xpsrdr@@@Z; resetNoAddRef<xpsrdr::SourceColorBitmap>(std::shared_ptr<xpsrdr::SourceColorBitmap> &,xpsrdr::SourceColorBitmap *)
0x1800ac51f  mov     rcx, [rsi]
0x1800ac522  mov     rax, [rcx]
0x1800ac525  mov     rdx, [rbx]
0x1800ac528  mov     rax, [rax+28h]
0x1800ac52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac531  test    eax, eax
0x1800ac533  jns     short loc_1800AC53D
0x1800ac535  mov     ecx, eax; this
0x1800ac537  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800ac53d  call    ?IsMatchingSystemFonts@xpsrdr@@YA_NXZ; xpsrdr::IsMatchingSystemFonts(void)
0x1800ac542  mov     [rdi+1E0h], al
0x1800ac548  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800ac550  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800ac554  mov     [rbp+4Fh+var_58], 0
0x1800ac55c  lea     rcx, [rdi+1E8h]
0x1800ac563  lea     rdx, [rbp+4Fh+var_68]
0x1800ac567  call    ?push@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAX$$QEAUD2D_MATRIX_3X2_F@@@Z; std::stack<D2D_MATRIX_3X2_F>::push(D2D_MATRIX_3X2_F &&)
0x1800ac56c  nop
0x1800ac56d  mov     rcx, [r15+8]; this
0x1800ac571  test    rcx, rcx
0x1800ac574  jz      short loc_1800AC57B
0x1800ac576  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ac57b  mov     rax, rdi
0x1800ac57e  mov     rcx, [rbp+4Fh+var_50]
0x1800ac582  xor     rcx, rsp; StackCookie
0x1800ac585  call    __security_check_cookie
0x1800ac58a  add     rsp, 88h
0x1800ac591  pop     r15
0x1800ac593  pop     r14
0x1800ac595  pop     r13
0x1800ac597  pop     r12
0x1800ac599  pop     rdi
0x1800ac59a  pop     rsi
0x1800ac59b  pop     rbx
0x1800ac59c  pop     rbp
0x1800ac59d  retn
  ... truncated ...
```
