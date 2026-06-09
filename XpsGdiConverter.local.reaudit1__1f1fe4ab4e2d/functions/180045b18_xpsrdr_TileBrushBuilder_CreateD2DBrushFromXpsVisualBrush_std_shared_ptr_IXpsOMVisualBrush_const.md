# xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush(std::shared_ptr<IXpsOMVisualBrush> const &)

- ea: `0x180045b18`
- end: `0x180046019`
- name: `?CreateD2DBrushFromXpsVisualBrush@TileBrushBuilder@xpsrdr@@QEAAXAEBV?$shared_ptr@UIXpsOMVisualBrush@@@std@@@Z`
- size: `1281`
- prototype: `__int64 __fastcall(xpsrdr::TileBrushBuilder *this)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180040014`

## callees

- `0x180008830`
- `0x18000d61c`
- `0x18000d7f8`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e934`
- `0x180011b0c`
- `0x1800122a8`
- `0x180015ac0`
- `0x1800184e8`
- `0x180023fac`
- `0x180027bc8`
- `0x180037278`
- `0x1800393b4`
- `0x18003b644`
- `0x18003d5dc`
- `0x180041548`
- `0x180044aa8`
- `0x180044c48`
- `0x180044d08`
- `0x180045b18`
- `0x180046020`
- `0x1800461c8`
- `0x180046304`
- `0x1800463b0`
- `0x1800464a8`
- `0x18004661c`
- `0x1800466d4`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
double __fastcall xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush(
        xpsrdr::TileBrushBuilder *this,
        __int64 **a2)
{
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  int v7; // r9d
  __int64 EmptyBrushClipPair; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // edi
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  int v19; // r14d
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  __int64 v27; // rax
  enum D2D1_EXTEND_MODE v28; // edi
  enum D2D1_EXTEND_MODE v29; // esi
  __int64 v30; // rax
  int v31; // r14d
  int v32; // edx
  const char *v33; // r8
  int v34; // r9d
  int v35; // r8d
  int v36; // r9d
  char v37; // dl
  __int64 v38; // rax
  double result; // xmm0_8
  enum D2D1_EXTEND_MODE v40[2]; // [rsp+40h] [rbp-C0h] BYREF
  enum D2D1_EXTEND_MODE v41[4]; // [rsp+48h] [rbp-B8h] BYREF
  struct D2D_RECT_F v42; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v43[2]; // [rsp+68h] [rbp-98h] BYREF
  struct D2D_RECT_F v44; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v45[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v46[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v47[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v48[28]; // [rsp+B8h] [rbp-48h] BYREF
  struct D2D_RECT_F v49; // [rsp+D8h] [rbp-28h] BYREF
  struct D2D1_BRUSH_PROPERTIES v50; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v51[2]; // [rsp+108h] [rbp+8h] BYREF

  if ( xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(this) )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v43);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v45);
    xpsrdr::TileBrushBuilder::CreateRenderTarget(this, v43, v45);
    v9 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v43);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 592LL))(v9, v45[0]);
    v10 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v43);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 256LL))(
      v10,
      *(unsigned int *)(*((_QWORD *)this + 4) + 88LL));
    v11 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v43);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 272LL))(
      v11,
      *(unsigned int *)(*((_QWORD *)this + 4) + 92LL));
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v44);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v44, v43);
    xpsrdr::TileBrushBuilder::BeginDraw(v12, &v44);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v47);
    v40[0] = D2D1_EXTEND_MODE_CLAMP;
    v13 = *a2;
    v14 = **a2;
    *(_QWORD *)v48 = 0;
    *(_QWORD *)&v48[8] = v40;
    *(_QWORD *)&v48[16] = v47;
    v15 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v14 + 144))(v13, v48);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v48);
    if ( v40[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v40[0], v16, v17, v18);
    if ( v15 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
    std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(&v44, v43);
    v19 = 1;
    ++*(_DWORD *)(v20 + 528);
    std::deque<std::shared_ptr<ID2D1RenderTarget>>::push_back(v20 + 552, &v44);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v44);
    *(__m128i *)v48 = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)&v48[16] = 0;
    std::deque<D2D_MATRIX_3X2_F>::push_back(*((_QWORD *)this + 4) + 488LL, v48);
    v49 = 0;
    v44 = 0;
    xpsrdr::TileBrushBuilder::GetViewboxAndViewport(this, &v49, &v44);
    v42 = 0;
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v42);
    std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(v41, v43);
    xpsrdr::RasterizeVisual(*((_QWORD *)this + 4), (unsigned int)v41, 0, v21, 0);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v41);
    std::deque<int>::pop_back(*((_QWORD *)this + 4) + 488LL);
    std::deque<std::shared_ptr<ID2D1RenderTarget>>::pop_back(*((_QWORD *)this + 4) + 552LL);
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v42);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v42, v43);
    xpsrdr::TileBrushBuilder::EndDraw(v22, &v42);
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v43[0] + 592LL))(v43[0], 0);
    v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v45[0] + 40LL))(v45[0]);
    if ( v23 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
    *(_QWORD *)&v42.left = 0;
    v42.right = v49.right - v49.left;
    v42.bottom = v49.bottom - v49.top;
    memset(&v50, 0, sizeof(v50));
    xpsrdr::TileBrushBuilder::PopulateBrushProperties(this, &v42, &v44, &v50);
    v40[0] = D2D1_EXTEND_MODE_CLAMP;
    v41[0] = D2D1_EXTEND_MODE_CLAMP;
    xpsrdr::TileBrushBuilder::GetExtendMode(this, v40, v41);
    v27 = *((_QWORD *)this + 4);
    if ( *(_DWORD *)(v27 + 96) || *(_DWORD *)(v27 + 88) == 1 )
      v19 = 0;
    v28 = v40[0];
    *(enum D2D1_EXTEND_MODE *)&v48[16] = v40[0];
    v29 = v41[0];
    *(enum D2D1_EXTEND_MODE *)&v48[20] = v41[0];
    *(_DWORD *)&v48[24] = v19;
    *(struct D2D_RECT_F *)v48 = v49;
    v51[0] = v49;
    *(_OWORD *)((char *)v51 + 12) = *(_OWORD *)&v48[12];
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v46);
    v41[0] = D2D1_EXTEND_MODE_CLAMP;
    v30 = *(_QWORD *)v43[0];
    *(_QWORD *)v48 = 0;
    *(_QWORD *)&v48[8] = v41;
    *(_QWORD *)&v48[16] = v46;
    v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, struct D2D1_BRUSH_PROPERTIES *, _BYTE *))(v30 + 520))(
            v43[0],
            v45[0],
            v51,
            &v50,
            v48);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v48);
    if ( v41[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v41[0], v32, v33, v34);
    if ( v31 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v31, v32, v33, v34);
    std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(this, v46);
    xpsrdr::TileBrushBuilder::WillBrushTile(this, &v44);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v41);
    if ( v37 && (v28 == D2D1_EXTEND_MODE_CLAMP || v29 == D2D1_EXTEND_MODE_CLAMP) )
    {
      LOBYTE(v36) = v29 == D2D1_EXTEND_MODE_CLAMP;
      LOBYTE(v35) = v28 == D2D1_EXTEND_MODE_CLAMP;
      v38 = xpsrdr::TileBrushBuilder::CalculateClipRect(
              (int)this,
              (int)v48,
              v35,
              v36,
              (xpsrdr *)&v42,
              &v44,
              (__int64)&v42);
      std::shared_ptr<_devicemodeW>::operator=(v41, v38);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v48);
    }
    std::shared_ptr<ID2D1Brush>::operator=((char *)this + 16, v41);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v41);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v46);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v47);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v45);
    return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v43);
  }
  else
  {
    v40[0] = 1065353216;
    v4 = (*(__int64 (__fastcall **)(_QWORD, enum D2D1_EXTEND_MODE *))(***((_QWORD ***)this + 5) + 40LL))(
           **((_QWORD **)this + 5),
           v40);
    if ( v4 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v4, v5, v6, v7);
    EmptyBrushClipPair = xpsrdr::CreateEmptyBrushClipPair(v48, *((_QWORD *)this + 4), v40);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
      this,
      EmptyBrushClipPair);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v48);
  }
  return result;
}

```

## disassembly

```asm
0x180045b18  mov     [rsp-8+arg_10], rbx
0x180045b1d  mov     [rsp-8+arg_18], rsi
0x180045b22  push    rbp
0x180045b23  push    rdi
0x180045b24  push    r14
0x180045b26  lea     rbp, [rsp-30h]
0x180045b2b  sub     rsp, 130h
0x180045b32  mov     rax, cs:__security_cookie
0x180045b39  xor     rax, rsp
0x180045b3c  mov     [rbp+40h+var_18], rax
0x180045b40  mov     rdi, rdx
0x180045b43  mov     rbx, rcx
0x180045b46  call    ?ValidBoxAndPortSizes@TileBrushBuilder@xpsrdr@@AEAA_NXZ; xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(void)
0x180045b4b  test    al, al
0x180045b4d  jnz     short loc_180045BA6
0x180045b4f  mov     [rsp+140h+var_100], 3F800000h
0x180045b57  mov     rax, [rbx+28h]
0x180045b5b  mov     rcx, [rax]
0x180045b5e  mov     rax, [rcx]
0x180045b61  lea     rdx, [rsp+140h+var_100]
0x180045b66  mov     rax, [rax+28h]
0x180045b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b6f  test    eax, eax
0x180045b71  jns     short loc_180045B7B
0x180045b73  mov     ecx, eax; this
0x180045b75  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180045b7b  lea     r8, [rsp+140h+var_100]
0x180045b80  mov     rdx, [rbx+20h]
0x180045b84  lea     rcx, [rbp+40h+var_88]
0x180045b88  call    ?CreateEmptyBrushClipPair@xpsrdr@@YA?AU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEAURenderState@1@PEAM@Z; xpsrdr::CreateEmptyBrushClipPair(xpsrdr::RenderState &,float *)
0x180045b8d  mov     rdx, rax
0x180045b90  mov     rcx, rbx
0x180045b93  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> &&)
0x180045b98  lea     rcx, [rbp+40h+var_88]
0x180045b9c  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x180045ba1  jmp     loc_180045FF5
0x180045ba6  lea     rcx, [rsp+140h+var_D8]
0x180045bab  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180045bb0  nop
0x180045bb1  lea     rcx, [rbp+40h+var_B8]
0x180045bb5  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180045bba  nop
0x180045bbb  lea     r8, [rbp+40h+var_B8]
0x180045bbf  lea     rdx, [rsp+140h+var_D8]
0x180045bc4  mov     rcx, rbx
0x180045bc7  call    ?CreateRenderTarget@TileBrushBuilder@xpsrdr@@AEAAXAEAV?$shared_ptr@UID2D1DeviceContext@@@std@@AEAV?$shared_ptr@UID2D1CommandList@@@4@@Z; xpsrdr::TileBrushBuilder::CreateRenderTarget(std::shared_ptr<ID2D1DeviceContext> &,std::shared_ptr<ID2D1CommandList> &)
0x180045bcc  lea     rcx, [rsp+140h+var_D8]
0x180045bd1  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180045bd6  mov     r8, rax
0x180045bd9  mov     rcx, [rax]
0x180045bdc  mov     rax, [rcx+250h]
0x180045be3  mov     rdx, [rbp+40h+var_B8]
0x180045be7  mov     rcx, r8
0x180045bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bef  lea     rcx, [rsp+140h+var_D8]
0x180045bf4  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180045bf9  mov     r8, rax
0x180045bfc  mov     rcx, [rax]
0x180045bff  mov     rdx, [rbx+20h]
0x180045c03  mov     rax, [rcx+100h]
0x180045c0a  mov     edx, [rdx+58h]
0x180045c0d  mov     rcx, r8
0x180045c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c15  lea     rcx, [rsp+140h+var_D8]
0x180045c1a  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180045c1f  mov     r8, rax
0x180045c22  mov     rcx, [rax]
0x180045c25  mov     rdx, [rbx+20h]
0x180045c29  mov     rax, [rcx+110h]
0x180045c30  mov     edx, [rdx+5Ch]
0x180045c33  mov     rcx, r8
0x180045c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c3b  lea     rcx, [rsp+140h+var_C8]
0x180045c40  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180045c45  lea     rdx, [rsp+140h+var_D8]
0x180045c4a  lea     rcx, [rsp+140h+var_C8]
0x180045c4f  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180045c54  lea     rdx, [rsp+140h+var_C8]
0x180045c59  call    ?BeginDraw@TileBrushBuilder@xpsrdr@@AEAAXV?$shared_ptr@UID2D1DeviceContext@@@std@@@Z; xpsrdr::TileBrushBuilder::BeginDraw(std::shared_ptr<ID2D1DeviceContext>)
0x180045c5e  lea     rcx, [rbp+40h+var_98]
0x180045c62  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180045c67  nop
0x180045c68  mov     [rsp+140h+var_100], 0
0x180045c70  mov     rcx, [rdi]
0x180045c73  mov     rax, [rcx]
0x180045c76  mov     qword ptr [rbp+40h+var_88], 0
0x180045c7e  lea     rdx, [rsp+140h+var_100]
0x180045c83  mov     qword ptr [rbp+40h+var_88+8], rdx
0x180045c87  lea     rdx, [rbp+40h+var_98]
0x180045c8b  mov     [rbp+40h+var_78], rdx
0x180045c8f  lea     rdx, [rbp+40h+var_88]
0x180045c93  mov     rax, [rax+90h]
0x180045c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c9f  mov     edi, eax
0x180045ca1  lea     rcx, [rbp+40h+var_88]
0x180045ca5  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180045caa  mov     ecx, [rsp+140h+var_100]; this
0x180045cae  test    ecx, ecx
0x180045cb0  jns     short loc_180045CB8
0x180045cb2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180045cb8  test    edi, edi
0x180045cba  jns     short loc_180045CC4
0x180045cbc  mov     ecx, edi; this
0x180045cbe  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180045cc4  mov     r8, [rbx+20h]
0x180045cc8  lea     rdx, [rsp+140h+var_D8]
0x180045ccd  lea     rcx, [rsp+140h+var_C8]
0x180045cd2  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x180045cd7  nop
0x180045cd8  mov     r14d, 1
0x180045cde  add     [r8+210h], r14d
0x180045ce5  lea     rcx, [r8+228h]
0x180045cec  lea     rdx, [rsp+140h+var_C8]
0x180045cf1  call    ?push_back@?$deque@V?$shared_ptr@UID2D1RenderTarget@@@std@@V?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@UID2D1RenderTarget@@@2@@Z; std::deque<std::shared_ptr<ID2D1RenderTarget>>::push_back(std::shared_ptr<ID2D1RenderTarget> const &)
0x180045cf6  nop
0x180045cf7  lea     rcx, [rsp+140h+var_C8]
0x180045cfc  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045d01  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180045d09  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x180045d0d  mov     [rbp+40h+var_78], 0
0x180045d15  mov     rcx, [rbx+20h]
0x180045d19  mov     edi, 1E8h
0x180045d1e  add     rcx, rdi
0x180045d21  lea     rdx, [rbp+40h+var_88]
0x180045d25  call    ?push_back@?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAAXAEBUD2D_MATRIX_3X2_F@@@Z; std::deque<D2D_MATRIX_3X2_F>::push_back(D2D_MATRIX_3X2_F const &)
0x180045d2a  xorps   xmm0, xmm0
0x180045d2d  movups  xmmword ptr [rbp+40h+var_68.left], xmm0
0x180045d31  xorps   xmm1, xmm1
0x180045d34  movups  xmmword ptr [rsp+140h+var_C8.left], xmm1
0x180045d39  lea     r8, [rsp+140h+var_C8]; struct D2D_RECT_F *
0x180045d3e  lea     rdx, [rbp+40h+var_68]; struct D2D_RECT_F *
0x180045d42  mov     rcx, rbx; this
0x180045d45  call    ?GetViewboxAndViewport@TileBrushBuilder@xpsrdr@@AEAAXAEAUD2D_RECT_F@@0@Z; xpsrdr::TileBrushBuilder::GetViewboxAndViewport(D2D_RECT_F &,D2D_RECT_F &)
0x180045d4a  xorps   xmm0, xmm0
0x180045d4d  movups  xmmword ptr [rsp+140h+var_E8.left], xmm0
0x180045d52  lea     rcx, [rsp+140h+var_E8]
0x180045d57  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180045d5c  mov     r8, rax
0x180045d5f  lea     rdx, [rsp+140h+var_D8]
0x180045d64  lea     rcx, [rsp+140h+var_F8]
0x180045d69  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x180045d6e  nop
0x180045d6f  mov     byte ptr [rsp+140h+var_110], 0
0x180045d74  mov     [rsp+140h+var_118], r8
0x180045d79  mov     [rsp+140h+var_120], 0
0x180045d82  lea     r9, [rbp+40h+var_98]
0x180045d86  lea     r8, [rbp+40h+var_68]
0x180045d8a  lea     rdx, [rsp+140h+var_F8]
0x180045d8f  mov     rcx, [rbx+20h]
0x180045d93  call    ?RasterizeVisual@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEBUD2D_RECT_F@@AEBV?$shared_ptr@UIXpsOMVisual@@@4@PEBUD2D_MATRIX_3X2_F@@V?$shared_ptr@UID2D1Geometry@@@4@_N@Z; xpsrdr::RasterizeVisual(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F const &,std::shared_ptr<IXpsOMVisual> const &,D2D_MATRIX_3X2_F const *,std::shared_ptr<ID2D1Geometry>,bool)
0x180045d98  nop
0x180045d99  lea     rcx, [rsp+140h+var_F8]
0x180045d9e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045da3  mov     rcx, [rbx+20h]
0x180045da7  add     rcx, rdi
0x180045daa  call    ?pop_back@?$deque@HV?$allocator@H@std@@@std@@QEAAXXZ; std::deque<int>::pop_back(void)
0x180045daf  mov     rcx, [rbx+20h]
0x180045db3  add     rcx, 228h
0x180045dba  call    ?pop_back@?$deque@V?$shared_ptr@UID2D1RenderTarget@@@std@@V?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<ID2D1RenderTarget>>::pop_back(void)
0x180045dbf  lea     rcx, [rsp+140h+var_E8]
0x180045dc4  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180045dc9  lea     rdx, [rsp+140h+var_D8]
0x180045dce  lea     rcx, [rsp+140h+var_E8]
0x180045dd3  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180045dd8  lea     rdx, [rsp+140h+var_E8]
0x180045ddd  call    ?EndDraw@TileBrushBuilder@xpsrdr@@AEAAXV?$shared_ptr@UID2D1DeviceContext@@@std@@@Z; xpsrdr::TileBrushBuilder::EndDraw(std::shared_ptr<ID2D1DeviceContext>)
0x180045de2  mov     rcx, [rsp+140h+var_D8]
0x180045de7  mov     rax, [rcx]
0x180045dea  xor     edx, edx
0x180045dec  mov     rax, [rax+250h]
0x180045df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045df8  mov     rcx, [rbp+40h+var_B8]
0x180045dfc  mov     rax, [rcx]
0x180045dff  mov     rax, [rax+28h]
0x180045e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e08  test    eax, eax
0x180045e0a  jns     short loc_180045E14
0x180045e0c  mov     ecx, eax; this
0x180045e0e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180045e14  mov     qword ptr [rsp+140h+var_E8.left], 0
0x180045e1d  movss   xmm0, [rbp+40h+var_68.right]
0x180045e22  subss   xmm0, [rbp+40h+var_68.left]
0x180045e27  movss   [rsp+140h+var_E8.right], xmm0
0x180045e2d  movss   xmm1, [rbp+40h+var_68.bottom]
0x180045e32  subss   xmm1, [rbp+40h+var_68.top]
0x180045e37  movss   [rsp+140h+var_E8.bottom], xmm1
0x180045e3d  xorps   xmm0, xmm0
0x180045e40  movups  xmmword ptr [rbp+40h+var_58.opacity], xmm0
0x180045e44  movups  xmmword ptr [rbp+40h+var_58.transform+8], xmm0
0x180045e48  lea     r9, [rbp+40h+var_58]; struct D2D1_BRUSH_PROPERTIES *
0x180045e4c  lea     r8, [rsp+140h+var_C8]; struct D2D_RECT_F *
0x180045e51  lea     rdx, [rsp+140h+var_E8]; struct D2D_RECT_F *
0x180045e56  mov     rcx, rbx; this
0x180045e59  call    ?PopulateBrushProperties@TileBrushBuilder@xpsrdr@@AEAAXAEBUD2D_RECT_F@@0AEAUD2D1_BRUSH_PROPERTIES@@@Z; xpsrdr::TileBrushBuilder::PopulateBrushProperties(D2D_RECT_F const &,D2D_RECT_F const &,D2D1_BRUSH_PROPERTIES &)
0x180045e5e  mov     [rsp+140h+var_100], 0
0x180045e66  mov     [rsp+140h+var_F8], 0
0x180045e6e  lea     r8, [rsp+140h+var_F8]; enum D2D1_EXTEND_MODE *
0x180045e73  lea     rdx, [rsp+140h+var_100]; enum D2D1_EXTEND_MODE *
0x180045e78  mov     rcx, rbx; this
0x180045e7b  call    ?GetExtendMode@TileBrushBuilder@xpsrdr@@AEAAXAEAW4D2D1_EXTEND_MODE@@0@Z; xpsrdr::TileBrushBuilder::GetExtendMode(D2D1_EXTEND_MODE &,D2D1_EXTEND_MODE &)
0x180045e80  mov     rax, [rbx+20h]
0x180045e84  cmp     dword ptr [rax+60h], 0
0x180045e88  jnz     short loc_180045E90
0x180045e8a  cmp     [rax+58h], r14d
0x180045e8e  jnz     short loc_180045E93
0x180045e90  xor     r14d, r14d
0x180045e93  movups  xmm0, xmmword ptr [rbp+40h+var_68.left]
0x180045e97  mov     edi, [rsp+140h+var_100]
0x180045e9b  mov     dword ptr [rbp+40h+var_78], edi
0x180045e9e  mov     esi, [rsp+140h+var_F8]
0x180045ea2  mov     dword ptr [rbp+40h+var_78+4], esi
0x180045ea5  mov     [rbp+40h+var_70], r14d
0x180045ea9  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x180045ead  movups  xmmword ptr [rbp+40h+var_38], xmm0
0x180045eb1  movups  xmm0, xmmword ptr [rbp+40h+var_88+0Ch]
0x180045eb5  movups  xmmword ptr [rbp+40h+var_38+0Ch], xmm0
0x180045eb9  lea     rcx, [rbp+40h+var_A8]
0x180045ebd  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180045ec2  nop
0x180045ec3  mov     [rsp+140h+var_F8], 0
0x180045ecb  mov     rcx, [rsp+140h+var_D8]
0x180045ed0  mov     rax, [rcx]
0x180045ed3  mov     qword ptr [rbp+40h+var_88], 0
0x180045edb  lea     rdx, [rsp+140h+var_F8]
0x180045ee0  mov     qword ptr [rbp+40h+var_88+8], rdx
0x180045ee4  lea     rdx, [rbp+40h+var_A8]
0x180045ee8  mov     [rbp+40h+var_78], rdx
0x180045eec  lea     rdx, [rbp+40h+var_88]
0x180045ef0  mov     [rsp+140h+var_120], rdx
0x180045ef5  lea     r9, [rbp+40h+var_58]
0x180045ef9  lea     r8, [rbp+40h+var_38]
0x180045efd  mov     rdx, [rbp+40h+var_B8]
0x180045f01  mov     rax, [rax+208h]
0x180045f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f0d  mov     r14d, eax
0x180045f10  lea     rcx, [rbp+40h+var_88]
0x180045f14  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180045f19  mov     ecx, [rsp+140h+var_F8]; this
0x180045f1d  test    ecx, ecx
0x180045f1f  jns     short loc_180045F27
0x180045f21  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180045f27  test    r14d, r14d
0x180045f2a  jns     short loc_180045F35
0x180045f2c  mov     ecx, r14d; this
0x180045f2f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180045f35  lea     rdx, [rbp+40h+var_A8]
0x180045f39  mov     rcx, rbx
0x180045f3c  call    ??$?4UID2D1ImageBrush@@$0A@@?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV?$shared_ptr@UID2D1ImageBrush@@@1@@Z; std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(std::shared_ptr<ID2D1ImageBrush> const &)
0x180045f41  lea     rdx, [rsp+140h+var_C8]; struct D2D_RECT_F *
0x180045f46  mov     rcx, rbx; this
0x180045f49  call    ?WillBrushTile@TileBrushBuilder@xpsrdr@@AEAA_NAEBUD2D_RECT_F@@@Z; xpsrdr::TileBrushBuilder::WillBrushTile(D2D_RECT_F const &)
0x180045f4e  mov     dl, al
0x180045f50  lea     rcx, [rsp+140h+var_F8]
0x180045f55  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180045f5a  nop
0x180045f5b  test    dl, dl
0x180045f5d  jz      short loc_180045FB3
0x180045f5f  test    edi, edi
0x180045f61  jz      short loc_180045F67
0x180045f63  test    esi, esi
0x180045f65  jnz     short loc_180045FB3
0x180045f67  test    esi, esi
0x180045f69  setz    r9b; int
0x180045f6d  test    edi, edi
0x180045f6f  setz    r8b; int
0x180045f73  lea     rax, [rsp+140h+var_E8]
0x180045f78  mov     [rsp+140h+var_110], rax; __int64
0x180045f7d  lea     rax, [rsp+140h+var_C8]
0x180045f82  mov     [rsp+140h+var_118], rax; struct D2D_RECT_F *
0x180045f87  lea     rax, [rsp+140h+var_E8]
0x180045f8c  mov     [rsp+140h+var_120], rax; xpsrdr *
0x180045f91  lea     rdx, [rbp+40h+var_88]; int
0x180045f95  mov     rcx, rbx; int
0x180045f98  call    ?CalculateClipRect@TileBrushBuilder@xpsrdr@@AEAA?AV?$shared_ptr@UID2D1Geometry@@@std@@_N0AEBUD2D_RECT_F@@11@Z; xpsrdr::TileBrushBuilder::CalculateClipRect(bool,bool,D2D_RECT_F const &,D2D_RECT_F const &,D2D_RECT_F const &)
0x180045f9d  mov     rdx, rax
0x180045fa0  lea     rcx, [rsp+140h+var_F8]
0x180045fa5  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x180045faa  lea     rcx, [rbp+40h+var_88]
0x180045fae  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045fb3  lea     rcx, [rbx+10h]
0x180045fb7  lea     rdx, [rsp+140h+var_F8]
0x180045fbc  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180045fc1  nop
0x180045fc2  lea     rcx, [rsp+140h+var_F8]
0x180045fc7  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045fcc  nop
0x180045fcd  lea     rcx, [rbp+40h+var_A8]
0x180045fd1  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045fd6  nop
0x180045fd7  lea     rcx, [rbp+40h+var_98]
0x180045fdb  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045fe0  nop
0x180045fe1  lea     rcx, [rbp+40h+var_B8]
0x180045fe5  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045fea  nop
0x180045feb  lea     rcx, [rsp+140h+var_D8]
0x180045ff0  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180045ff5  mov     rcx, [rbp+40h+var_18]
0x180045ff9  xor     rcx, rsp; StackCookie
0x180045ffc  call    __security_check_cookie
  ... truncated ...
```
