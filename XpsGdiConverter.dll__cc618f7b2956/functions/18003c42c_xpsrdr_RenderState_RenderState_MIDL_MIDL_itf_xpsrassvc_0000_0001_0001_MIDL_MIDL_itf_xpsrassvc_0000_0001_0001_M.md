# xpsrdr::RenderState::RenderState(__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001,__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001,__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001,std::shared_ptr<IWICImagingFactory>)

- ea: `0x18003c42c`
- end: `0x18003c8c2`
- name: `??0RenderState@xpsrdr@@QEAA@W4__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001@@0W4__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001@@V?$shared_ptr@UIWICImagingFactory@@@std@@@Z`
- size: `1174`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x18000e25c`

## callees

- `0x180008830`
- `0x180008854`
- `0x180009f20`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x180013854`
- `0x180024348`
- `0x18002777c`
- `0x180027bc8`
- `0x1800336ec`
- `0x180034810`
- `0x180037278`
- `0x1800372e4`
- `0x18003c2d4`
- `0x18003c31c`
- `0x18003c338`
- `0x18003c354`
- `0x18003c39c`
- `0x18003c3e4`
- `0x18003c42c`
- `0x18003d1b8`
- `0x18003d1e4`
- `0x18003d210`
- `0x18003d23c`
- `0x180041d84`
- `0x18004a010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18003c6af`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003c6af`
- `DWrite!DWriteCreateFactory` at `0x18003c6fe`
- `DWrite!DWriteCreateFactory` at `0x18003c6fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall xpsrdr::RenderState::RenderState(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rcx
  __int64 v7; // rdi
  _QWORD *v8; // r14
  xpsrdr::Stat *v9; // rax
  __int64 v10; // rax
  HRESULT v11; // ebx
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  int v15; // ebx
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  int D3DDevice; // ebx
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  const char *v23; // rdx
  xpsrdr *v24; // rcx
  int v25; // r8d
  const char *v26; // rdx
  xpsrdr *v27; // rcx
  int v28; // r8d
  _QWORD *v29; // rcx
  int v30; // eax
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  xpsrdr *v34; // rax
  _QWORD *v35; // rcx
  int v36; // eax
  int v37; // edx
  xpsrdr *v38; // rcx
  const char *v39; // r8
  int v40; // r9d
  xpsrdr *v42; // [rsp+20h] [rbp-51h] BYREF
  void *ppIFactory; // [rsp+28h] [rbp-49h] BYREF
  xpsrdr **v44; // [rsp+30h] [rbp-41h]
  __int64 v45; // [rsp+38h] [rbp-39h]
  D2D1_FACTORY_OPTIONS pFactoryOptions; // [rsp+40h] [rbp-31h] BYREF
  __int64 v47; // [rsp+48h] [rbp-29h]
  __int64 v48; // [rsp+50h] [rbp-21h]
  __int64 v49; // [rsp+58h] [rbp-19h]
  struct ID3D11Device *v50[2]; // [rsp+60h] [rbp-11h] BYREF
  __int64 v51; // [rsp+70h] [rbp-1h]

  v48 = a1;
  v47 = a5;
  v49 = a5;
  ((void (*)(void))std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>)();
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>();
  v7 = v6 + 16;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v6 + 16);
  v8 = (_QWORD *)(a1 + 32);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1 + 32);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1 + 48);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1 + 64);
  *(_DWORD *)(a1 + 120) = 1090519040;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 128);
  std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 144);
  *(_DWORD *)(a1 + 160) = 1098907648;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 168);
  std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 184);
  *(_DWORD *)(a1 + 200) = 1124073472;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 208);
  std::list<std::pair<xpsrdr::KeySolidColorBrush const,std::shared_ptr<ID2D1Brush>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 224);
  *(_DWORD *)(a1 + 240) = 1098907648;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 248);
  std::list<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 264);
  *(_DWORD *)(a1 + 280) = 1124073472;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 288);
  std::list<std::pair<xpsrdr::KeyStrokeStyle const,std::shared_ptr<ID2D1StrokeStyle>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 304);
  *(_DWORD *)(a1 + 320) = 1090519040;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 328);
  std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 344);
  std::map<std::wstring,xpsrdr::FontFileData>::map<std::wstring,xpsrdr::FontFileData>(a1 + 360);
  *(_DWORD *)(a1 + 376) = 1111490560;
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1 + 384);
  std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::_Alloc_sentinel_and_proxy();
  std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(a1 + 400);
  std::map<IXpsOMGlyphs *,D2D_RECT_F>::map<IXpsOMGlyphs *,D2D_RECT_F>(a1 + 416);
  std::map<xpsrdr::PathGeometryKey,D2D_RECT_F>::map<xpsrdr::PathGeometryKey,D2D_RECT_F>(a1 + 432);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1 + 448);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1 + 464);
  *(_WORD *)(a1 + 480) = 0;
  std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>(a1 + 488);
  *(_DWORD *)(a1 + 528) = 0;
  *(_QWORD *)(a1 + 532) = 1;
  *(_DWORD *)(a1 + 540) = 0;
  v9 = (xpsrdr::Stat *)operator new(0x98u);
  HIDWORD(v42) = HIDWORD(v9);
  v10 = xpsrdr::Stat::Stat(v9);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(a1 + 544, v10);
  std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>(a1 + 552);
  *(_DWORD *)(a1 + 88) = 1;
  *(_DWORD *)(a1 + 96) = 1;
  *(_DWORD *)(a1 + 92) = 3;
  *(GUID *)(a1 + 100) = GUID_WICPixelFormat32bppPBGRA;
  pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE;
  LODWORD(v42) = 0;
  ppIFactory = 0;
  v44 = &v42;
  v45 = v7;
  v11 = D2D1CreateFactory(
          D2D1_FACTORY_TYPE_SINGLE_THREADED,
          &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f,
          &pFactoryOptions,
          &ppIFactory);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppIFactory);
  if ( (int)v42 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42, v12, v13, v14);
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
  LODWORD(v42) = 0;
  ppIFactory = 0;
  v44 = &v42;
  v45 = a1 + 32;
  v15 = DWriteCreateFactory(1, &GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48, &ppIFactory);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppIFactory);
  if ( (int)v42 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42, v16, v17, v18);
  if ( v15 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
  LODWORD(v42) = 0;
  v50[0] = 0;
  v50[1] = (struct ID3D11Device *)&v42;
  v51 = a1 + 64;
  ppIFactory = 0;
  v44 = &v42;
  v45 = a1 + 48;
  D3DDevice = xpsrdr::CreateD3DDevice(
                (D3D_FEATURE_LEVEL *)(a1 + 80),
                (enum D3D_FEATURE_LEVEL *)(a1 + 84),
                (xpsrdr **)&ppIFactory,
                v50);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppIFactory);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v50);
  if ( (int)v42 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42, v20, v21, v22);
  if ( D3DDevice < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)D3DDevice, v20, v21, v22);
  if ( !(unsigned __int8)std::operator!=<ID3D11Device>(a1 + 48) )
    xpsrdr::ThrowLogicException(v24, v23, v25);
  if ( !(unsigned __int8)std::operator!=<ID3D11Device>(a1 + 64) )
    xpsrdr::ThrowLogicException(v27, v26, v28);
  if ( (unsigned int)(*(_DWORD *)(a1 + 84) - 1) > 1 )
    xpsrdr::ThrowLogicException(v27, v26, v28);
  v42 = (xpsrdr *)operator new(0x18u);
  CUnknownBase<IDWriteFontFileLoader>::CUnknownBase<IDWriteFontFileLoader>(v42);
  *v29 = &xpsrdr::FontLoader::`vftable';
  v29[2] = a1;
  resetNoAddRef<xpsrdr::FontLoader>(a1 + 448, v29);
  v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v8 + 104LL))(*v8, *(_QWORD *)(a1 + 448));
  if ( v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v31, v32, v33);
  v34 = (xpsrdr *)operator new(0x10u);
  v42 = v34;
  *(_OWORD *)v34 = 0;
  CUnknownBase<IDWriteFontCollectionLoader>::CUnknownBase<IDWriteFontCollectionLoader>(v34);
  *v35 = &xpsrdr::XpsToSystemFontCollectionLoader::`vftable';
  resetNoAddRef<xpsrdr::FontLoader>(a1 + 464, v35);
  v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v8 + 40LL))(*v8, *(_QWORD *)(a1 + 464));
  if ( v36 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v36, v37, v39, v40);
  *(_BYTE *)(a1 + 480) = xpsrdr::IsMatchingSystemFonts(v38);
  *(__m128i *)v50 = _mm_load_si128((const __m128i *)&_xmm);
  v51 = 0;
  std::deque<D2D_MATRIX_3X2_F>::push_back(a1 + 488, v50);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v47);
  return a1;
}

```

## disassembly

```asm
0x18003c42c  push    rbp
0x18003c42e  push    rbx
0x18003c42f  push    rsi
0x18003c430  push    rdi
0x18003c431  push    r12
0x18003c433  push    r13
0x18003c435  push    r14
0x18003c437  push    r15
0x18003c439  lea     rbp, [rsp-17h]
0x18003c43e  sub     rsp, 88h
0x18003c445  mov     rax, cs:__security_cookie
0x18003c44c  xor     rax, rsp
0x18003c44f  mov     [rbp+4Fh+var_48], rax
0x18003c453  mov     rsi, rcx
0x18003c456  mov     [rbp+4Fh+var_70], rcx
0x18003c45a  mov     rdx, [rbp+4Fh+arg_20]
0x18003c45e  mov     [rbp+4Fh+var_78], rdx
0x18003c462  mov     [rbp+4Fh+var_68], rdx
0x18003c466  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c46b  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18003c470  nop
0x18003c471  lea     rdi, [rcx+10h]
0x18003c475  mov     rcx, rdi
0x18003c478  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003c47d  nop
0x18003c47e  lea     r14, [rsi+20h]
0x18003c482  mov     rcx, r14
0x18003c485  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003c48a  nop
0x18003c48b  lea     r15, [rsi+30h]
0x18003c48f  mov     rcx, r15
0x18003c492  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003c497  nop
0x18003c498  lea     r12, [rsi+40h]
0x18003c49c  mov     rcx, r12
0x18003c49f  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003c4a4  nop
0x18003c4a5  lea     rbx, [rsi+78h]
0x18003c4a9  mov     [rbp+4Fh+var_A0], rbx
0x18003c4ad  mov     dword ptr [rbx], 41000000h
0x18003c4b3  lea     rcx, [rbx+8]
0x18003c4b7  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c4bc  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::_Alloc_sentinel_and_proxy(void)
0x18003c4c1  nop
0x18003c4c2  lea     rcx, [rbx+18h]
0x18003c4c6  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c4cb  nop
0x18003c4cc  lea     rbx, [rsi+0A0h]
0x18003c4d3  mov     [rbp+4Fh+var_A0], rbx
0x18003c4d7  mov     dword ptr [rbx], 41800000h
0x18003c4dd  lea     rcx, [rbx+8]
0x18003c4e1  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c4e6  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::_Alloc_sentinel_and_proxy(void)
0x18003c4eb  nop
0x18003c4ec  lea     rcx, [rbx+18h]
0x18003c4f0  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c4f5  nop
0x18003c4f6  lea     rbx, [rsi+0C8h]
0x18003c4fd  mov     [rbp+4Fh+var_A0], rbx
0x18003c501  mov     r13d, 43000000h
0x18003c507  mov     [rbx], r13d
0x18003c50a  lea     rcx, [rbx+8]
0x18003c50e  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c513  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBUKeySolidColorBrush@xpsrdr@@V?$shared_ptr@UID2D1Brush@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeySolidColorBrush@xpsrdr@@V?$shared_ptr@UID2D1Brush@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<xpsrdr::KeySolidColorBrush const,std::shared_ptr<ID2D1Brush>>>::_Alloc_sentinel_and_proxy(void)
0x18003c518  nop
0x18003c519  lea     rcx, [rbx+18h]
0x18003c51d  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c522  nop
0x18003c523  lea     rbx, [rsi+0F0h]
0x18003c52a  mov     [rbp+4Fh+var_A0], rbx
0x18003c52e  mov     dword ptr [rbx], 41800000h
0x18003c534  lea     rcx, [rbx+8]
0x18003c538  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c53d  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::_Alloc_sentinel_and_proxy(void)
0x18003c542  nop
0x18003c543  lea     rcx, [rbx+18h]
0x18003c547  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c54c  nop
0x18003c54d  lea     rbx, [rsi+118h]
0x18003c554  mov     [rbp+4Fh+var_A0], rbx
0x18003c558  mov     [rbx], r13d
0x18003c55b  lea     rcx, [rbx+8]
0x18003c55f  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c564  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBUKeyStrokeStyle@xpsrdr@@V?$shared_ptr@UID2D1StrokeStyle@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyStrokeStyle@xpsrdr@@V?$shared_ptr@UID2D1StrokeStyle@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<xpsrdr::KeyStrokeStyle const,std::shared_ptr<ID2D1StrokeStyle>>>::_Alloc_sentinel_and_proxy(void)
0x18003c569  nop
0x18003c56a  lea     rcx, [rbx+18h]
0x18003c56e  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c573  nop
0x18003c574  lea     rbx, [rsi+140h]
0x18003c57b  mov     [rbp+4Fh+var_A0], rbx
0x18003c57f  mov     dword ptr [rbx], 41000000h
0x18003c585  lea     rcx, [rbx+8]
0x18003c589  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c58e  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::_Alloc_sentinel_and_proxy(void)
0x18003c593  nop
0x18003c594  lea     rcx, [rbx+18h]
0x18003c598  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c59d  nop
0x18003c59e  lea     rcx, [rsi+168h]
0x18003c5a5  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFontFileData@xpsrdr@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,xpsrdr::FontFileData>::map<std::wstring,xpsrdr::FontFileData>(void)
0x18003c5aa  nop
0x18003c5ab  lea     rbx, [rsi+178h]
0x18003c5b2  mov     [rbp+4Fh+var_A0], rbx
0x18003c5b6  mov     dword ptr [rbx], 42400000h
0x18003c5bc  lea     rcx, [rbx+8]
0x18003c5c0  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003c5c5  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@V?$allocator@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>::_Alloc_sentinel_and_proxy(void)
0x18003c5ca  nop
0x18003c5cb  lea     rcx, [rbx+18h]
0x18003c5cf  call    ??0?$multimap@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>::multimap<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>(void)
0x18003c5d4  nop
0x18003c5d5  lea     rcx, [rsi+1A0h]
0x18003c5dc  call    ??0?$map@PEAUIXpsOMGlyphs@@UD2D_RECT_F@@U?$less@PEAUIXpsOMGlyphs@@@std@@V?$allocator@U?$pair@QEAUIXpsOMGlyphs@@UD2D_RECT_F@@@std@@@4@@std@@QEAA@XZ; std::map<IXpsOMGlyphs *,D2D_RECT_F>::map<IXpsOMGlyphs *,D2D_RECT_F>(void)
0x18003c5e1  nop
0x18003c5e2  lea     rcx, [rsi+1B0h]
0x18003c5e9  call    ??0?$map@UPathGeometryKey@xpsrdr@@UD2D_RECT_F@@U?$less@UPathGeometryKey@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBUPathGeometryKey@xpsrdr@@UD2D_RECT_F@@@std@@@5@@std@@QEAA@XZ; std::map<xpsrdr::PathGeometryKey,D2D_RECT_F>::map<xpsrdr::PathGeometryKey,D2D_RECT_F>(void)
0x18003c5ee  nop
0x18003c5ef  lea     r13, [rsi+1C0h]
0x18003c5f6  mov     rcx, r13
0x18003c5f9  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003c5fe  nop
0x18003c5ff  lea     rcx, [rsi+1D0h]
0x18003c606  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003c60b  nop
0x18003c60c  xor     ebx, ebx
0x18003c60e  mov     [rsi+1E0h], bx
0x18003c615  lea     rcx, [rsi+1E8h]
0x18003c61c  call    ??0?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAA@XZ; std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>(void)
0x18003c621  nop
0x18003c622  mov     [rsi+210h], ebx
0x18003c628  mov     qword ptr [rsi+214h], 1
0x18003c633  mov     [rsi+21Ch], ebx
0x18003c639  mov     ecx, 98h; Size
0x18003c63e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c643  mov     [rbp+4Fh+var_A0], rax
0x18003c647  mov     rcx, rax; this
0x18003c64a  call    ??0Stat@xpsrdr@@QEAA@XZ; xpsrdr::Stat::Stat(void)
0x18003c64f  lea     rcx, [rsi+220h]
0x18003c656  mov     rdx, rax
0x18003c659  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003c65e  nop
0x18003c65f  lea     rcx, [rsi+228h]
0x18003c666  call    ??0?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAA@XZ; std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>(void)
0x18003c66b  nop
0x18003c66c  lea     eax, [rbx+1]
0x18003c66f  mov     [rsi+58h], eax
0x18003c672  mov     [rsi+60h], eax
0x18003c675  mov     dword ptr [rsi+5Ch], 3
0x18003c67c  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppPBGRA.Data1
0x18003c683  movdqu  xmmword ptr [rsi+64h], xmm0
0x18003c688  mov     [rbp+4Fh+pFactoryOptions.debugLevel], ebx
0x18003c68b  mov     dword ptr [rbp+4Fh+var_A0], ebx
0x18003c68e  mov     [rbp+4Fh+ppIFactory], rbx
0x18003c692  lea     rax, [rbp+4Fh+var_A0]
0x18003c696  mov     [rbp+4Fh+var_90], rax
0x18003c69a  mov     [rbp+4Fh+var_88], rdi
0x18003c69e  lea     r9, [rbp+4Fh+ppIFactory]; ppIFactory
0x18003c6a2  lea     r8, [rbp+4Fh+pFactoryOptions]; pFactoryOptions
0x18003c6a6  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x18003c6ad  xor     ecx, ecx; factoryType
0x18003c6af  call    cs:__imp_D2D1CreateFactory
0x18003c6b5  mov     ebx, eax
0x18003c6b7  lea     rcx, [rbp+4Fh+ppIFactory]
0x18003c6bb  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003c6c0  mov     ecx, dword ptr [rbp+4Fh+var_A0]; this
0x18003c6c3  xor     edi, edi
0x18003c6c5  test    ecx, ecx
0x18003c6c7  jns     short loc_18003C6CF
0x18003c6c9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c6cf  test    ebx, ebx
0x18003c6d1  jns     short loc_18003C6DB
0x18003c6d3  mov     ecx, ebx; this
0x18003c6d5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c6db  mov     dword ptr [rbp+4Fh+var_A0], edi
0x18003c6de  mov     [rbp+4Fh+ppIFactory], rdi
0x18003c6e2  lea     rax, [rbp+4Fh+var_A0]
0x18003c6e6  mov     [rbp+4Fh+var_90], rax
0x18003c6ea  mov     [rbp+4Fh+var_88], r14
0x18003c6ee  lea     r8, [rbp+4Fh+ppIFactory]
0x18003c6f2  lea     rdx, _GUID_b859ee5a_d838_4b5b_a2e8_1adc7d93db48
0x18003c6f9  mov     ecx, 1
0x18003c6fe  call    cs:__imp_DWriteCreateFactory
0x18003c704  mov     ebx, eax
0x18003c706  lea     rcx, [rbp+4Fh+ppIFactory]
0x18003c70a  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003c70f  mov     ecx, dword ptr [rbp+4Fh+var_A0]; this
0x18003c712  test    ecx, ecx
0x18003c714  jns     short loc_18003C71C
0x18003c716  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c71c  test    ebx, ebx
0x18003c71e  jns     short loc_18003C728
0x18003c720  mov     ecx, ebx; this
0x18003c722  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c728  mov     dword ptr [rbp+4Fh+var_A0], edi
0x18003c72b  mov     [rbp+4Fh+var_60], rdi
0x18003c72f  lea     rax, [rbp+4Fh+var_A0]
0x18003c733  mov     [rbp+4Fh+var_60+8], rax
0x18003c737  mov     [rbp+4Fh+var_50], r12
0x18003c73b  mov     [rbp+4Fh+ppIFactory], rdi
0x18003c73f  lea     rax, [rbp+4Fh+var_A0]
0x18003c743  mov     [rbp+4Fh+var_90], rax
0x18003c747  mov     [rbp+4Fh+var_88], r15
0x18003c74b  lea     rcx, [rsi+50h]; pFeatureLevel
0x18003c74f  lea     r9, [rbp+4Fh+var_60]; struct ID3D11Device **
0x18003c753  lea     r8, [rbp+4Fh+ppIFactory]; enum xpsrdr::XPSRAS_DRIVER_TYPE *
0x18003c757  lea     rdx, [rsi+54h]; enum D3D_FEATURE_LEVEL *
0x18003c75b  call    ?CreateD3DDevice@xpsrdr@@YAJPEAW4D3D_FEATURE_LEVEL@@PEAW4XPSRAS_DRIVER_TYPE@1@PEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@@Z; xpsrdr::CreateD3DDevice(D3D_FEATURE_LEVEL *,xpsrdr::XPSRAS_DRIVER_TYPE *,ID3D11Device * *,ID3D11DeviceContext * *)
0x18003c760  mov     ebx, eax
0x18003c762  lea     rcx, [rbp+4Fh+ppIFactory]
0x18003c766  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003c76b  nop
0x18003c76c  lea     rcx, [rbp+4Fh+var_60]
0x18003c770  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003c775  mov     ecx, dword ptr [rbp+4Fh+var_A0]; this
0x18003c778  test    ecx, ecx
0x18003c77a  jns     short loc_18003C782
0x18003c77c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c782  test    ebx, ebx
0x18003c784  jns     short loc_18003C78E
0x18003c786  mov     ecx, ebx; this
0x18003c788  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c78e  mov     rcx, r15
0x18003c791  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003c796  test    al, al
0x18003c798  jnz     short loc_18003C7A0
0x18003c79a  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003c7a0  mov     rcx, r12
0x18003c7a3  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003c7a8  test    al, al
0x18003c7aa  jnz     short loc_18003C7B2
0x18003c7ac  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003c7b2  mov     eax, [rsi+54h]
0x18003c7b5  dec     eax
0x18003c7b7  cmp     eax, 1
0x18003c7ba  jbe     short loc_18003C7C2
0x18003c7bc  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003c7c2  mov     ecx, 18h; Size
0x18003c7c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c7cc  mov     rcx, rax
0x18003c7cf  mov     [rbp+4Fh+var_A0], rax
0x18003c7d3  call    ??0?$CUnknownBase@UIDWriteFontFileLoader@@@@QEAA@XZ; CUnknownBase<IDWriteFontFileLoader>::CUnknownBase<IDWriteFontFileLoader>(void)
0x18003c7d8  lea     rdx, ??_7FontLoader@xpsrdr@@6B@; const xpsrdr::FontLoader::`vftable'
0x18003c7df  mov     [rcx], rdx
0x18003c7e2  mov     [rcx+10h], rsi
0x18003c7e6  mov     rdx, rcx
0x18003c7e9  mov     rcx, r13
0x18003c7ec  call    ??$resetNoAddRef@VFontLoader@xpsrdr@@@@YAXAEAV?$shared_ptr@VFontLoader@xpsrdr@@@std@@PEAVFontLoader@xpsrdr@@@Z; resetNoAddRef<xpsrdr::FontLoader>(std::shared_ptr<xpsrdr::FontLoader> &,xpsrdr::FontLoader *)
0x18003c7f1  mov     rcx, [r14]
0x18003c7f4  mov     rax, [rcx]
0x18003c7f7  mov     rdx, [r13+0]
0x18003c7fb  mov     rax, [rax+68h]
0x18003c7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c804  test    eax, eax
0x18003c806  jns     short loc_18003C810
0x18003c808  mov     ecx, eax; this
0x18003c80a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c810  mov     ecx, 10h; Size
0x18003c815  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c81a  mov     rcx, rax
0x18003c81d  mov     [rbp+4Fh+var_A0], rax
0x18003c821  xorps   xmm0, xmm0
0x18003c824  movups  xmmword ptr [rax], xmm0
0x18003c827  call    ??0?$CUnknownBase@UIDWriteFontCollectionLoader@@@@QEAA@XZ; CUnknownBase<IDWriteFontCollectionLoader>::CUnknownBase<IDWriteFontCollectionLoader>(void)
0x18003c82c  lea     rdx, ??_7XpsToSystemFontCollectionLoader@xpsrdr@@6B@; const xpsrdr::XpsToSystemFontCollectionLoader::`vftable'
0x18003c833  mov     [rcx], rdx
0x18003c836  mov     rdx, rcx
0x18003c839  lea     rbx, [rsi+1D0h]
0x18003c840  mov     rcx, rbx
0x18003c843  call    ??$resetNoAddRef@VFontLoader@xpsrdr@@@@YAXAEAV?$shared_ptr@VFontLoader@xpsrdr@@@std@@PEAVFontLoader@xpsrdr@@@Z; resetNoAddRef<xpsrdr::FontLoader>(std::shared_ptr<xpsrdr::FontLoader> &,xpsrdr::FontLoader *)
0x18003c848  mov     rcx, [r14]
0x18003c84b  mov     rax, [rcx]
0x18003c84e  mov     rdx, [rbx]
0x18003c851  mov     rax, [rax+28h]
0x18003c855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c85a  test    eax, eax
0x18003c85c  jns     short loc_18003C866
0x18003c85e  mov     ecx, eax; this
0x18003c860  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003c866  call    ?IsMatchingSystemFonts@xpsrdr@@YA_NXZ; xpsrdr::IsMatchingSystemFonts(void)
0x18003c86b  mov     [rsi+1E0h], al
0x18003c871  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18003c879  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x18003c87d  mov     [rbp+4Fh+var_50], 0
0x18003c885  lea     rdx, [rbp+4Fh+var_60]
0x18003c889  lea     rcx, [rsi+1E8h]
0x18003c890  call    ?push_back@?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAAXAEBUD2D_MATRIX_3X2_F@@@Z; std::deque<D2D_MATRIX_3X2_F>::push_back(D2D_MATRIX_3X2_F const &)
0x18003c895  nop
0x18003c896  mov     rcx, [rbp+4Fh+var_78]
0x18003c89a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18003c89f  mov     rax, rsi
0x18003c8a2  mov     rcx, [rbp+4Fh+var_48]
0x18003c8a6  xor     rcx, rsp; StackCookie
0x18003c8a9  call    __security_check_cookie
0x18003c8ae  add     rsp, 88h
0x18003c8b5  pop     r15
0x18003c8b7  pop     r14
0x18003c8b9  pop     r13
0x18003c8bb  pop     r12
0x18003c8bd  pop     rdi
0x18003c8be  pop     rsi
  ... truncated ...
```
