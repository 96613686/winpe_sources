# xpsrdr::RasterizeVisualPath(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F &,std::shared_ptr<ID2D1Geometry> &,std::shared_ptr<IXpsOMVisual> const &,std::shared_ptr<IXpsOMBrush> &,xpsrdr::RenderStateHolder &,float,bool)

- ea: `0x18003a18c`
- end: `0x18003a985`
- name: `?RasterizeVisualPath@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEAUD2D_RECT_F@@AEAV?$shared_ptr@UID2D1Geometry@@@4@AEBV?$shared_ptr@UIXpsOMVisual@@@4@AEAV?$shared_ptr@UIXpsOMBrush@@@4@AEAURenderStateHolder@1@M_N@Z`
- size: `2041`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1800393b4`

## callees

- `0x180008830`
- `0x18000d7f8`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x180012088`
- `0x1800122a8`
- `0x180027cac`
- `0x180033fb0`
- `0x180034cac`
- `0x180034d10`
- `0x180037278`
- `0x180037864`
- `0x180037e18`
- `0x180038418`
- `0x1800384fc`
- `0x18003a18c`
- `0x18003aad8`
- `0x18003ac3c`
- `0x18003b810`
- `0x18003f5ec`
- `0x180040014`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
double __fastcall xpsrdr::RasterizeVisualPath(
        __int64 a1,
        _QWORD *a2,
        float *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        float a8,
        char a9)
{
  _QWORD **v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __m128i *); // rcx
  __int64 (__fastcall **v15)(_QWORD, GUID *, __m128i *); // rax
  int v16; // r14d
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  __int64 v24; // rax
  int v25; // r14d
  int v26; // edx
  const char *v27; // r8
  int v28; // r9d
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // r14d
  int v37; // edx
  const char *v38; // r8
  int v39; // r9d
  const struct D2D_RECT_F *v40; // r9
  __int64 D2D1StrokeStyle; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rcx
  struct D2D_RECT_F *v48; // rax
  float v49; // xmm4_4
  float v50; // xmm2_4
  float v51; // xmm1_4
  const struct D2D_RECT_F *v52; // rdx
  char v53; // al
  __int64 v54; // rax
  int v55; // r14d
  int v56; // edx
  const char *v57; // r8
  int v58; // r9d
  const struct D2D_RECT_F *v59; // rdx
  char v60; // r15
  int v61; // eax
  __int64 v62; // rdx
  const char *v63; // r8
  __int64 v64; // r9
  char v65; // al
  __int64 v66; // r12
  xpsrdr *v67; // rax
  char v68; // r14
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rcx
  __int64 v72; // r8
  const struct D2D_RECT_F *v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  xpsrdr *v77; // rax
  __int64 v78; // r14
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rcx
  __int64 v82; // r8
  xpsrdr *v84[2]; // [rsp+40h] [rbp-C0h] BYREF
  float v85; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v86[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v87; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ****v88)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *); // [rsp+78h] [rbp-88h]
  _BYTE v89[16]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v90[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall ***v91[2])(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *); // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall ***v92[2])(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *); // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v93[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v94[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v95[16]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-10h] BYREF
  __int64 (__fastcall ****v97)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *); // [rsp+100h] [rbp+0h]
  struct D2D_RECT_F v98; // [rsp+108h] [rbp+8h] BYREF
  struct D2D_RECT_F v99; // [rsp+118h] [rbp+18h] BYREF

  *(_QWORD *)&v87 = a7;
  ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 88LL);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v86);
  LODWORD(v84[0]) = 0;
  v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __m128i *))*v13;
  v15 = (__int64 (__fastcall **)(_QWORD, GUID *, __m128i *))**v13;
  si128.m128i_i64[0] = 0;
  si128.m128i_i64[1] = (__int64)v84;
  v97 = (__int64 (__fastcall ****)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *))v86;
  v16 = (*v15)(v14, &GUID_37d38bb6_3ee9_4110_9312_14b194163337, &si128);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&si128);
  if ( SLODWORD(v84[0]) < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v84[0]), v17, v18, v19);
  if ( v16 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
  v85 = 0.0;
  v20 = (*(__int64 (__fastcall **)(_QWORD, float *))(*(_QWORD *)v86[0] + 472LL))(v86[0], &v85);
  if ( v20 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v89);
  LODWORD(v84[0]) = 0;
  v24 = *(_QWORD *)v86[0];
  si128.m128i_i64[0] = 0;
  si128.m128i_i64[1] = (__int64)v84;
  v97 = (__int64 (__fastcall ****)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *))v89;
  v25 = (*(__int64 (__fastcall **)(_QWORD, __m128i *))(v24 + 240))(v86[0], &si128);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&si128);
  if ( SLODWORD(v84[0]) < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v84[0]), v26, v27, v28);
  if ( v25 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v26, v27, v28);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v89) )
  {
    xpsrdr::CreateD2D1PathGeometry(v90, a1, v89);
    v98 = 0;
    si128 = 0;
    v29 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&si128);
    v32 = std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488, v30, v31, v29);
    xpsrdr::GetGeometryBounds(a1, v90, v32, v89, 0, v33, &v98);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&si128);
    if ( a9 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      xpsrdr::RenderBoundingBox(v34, a2, &v98, &si128);
    }
    v99 = v98;
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v91);
    LODWORD(v84[0]) = 0;
    v35 = *(_QWORD *)v86[0];
    si128.m128i_i64[0] = 0;
    si128.m128i_i64[1] = (__int64)v84;
    v97 = v91;
    v36 = (*(__int64 (__fastcall **)(_QWORD, __m128i *))(v35 + 328))(v86[0], &si128);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&si128);
    if ( SLODWORD(v84[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v84[0]), v37, v38, v39);
    if ( v36 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v36, v37, v38, v39);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v93);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v91) )
    {
      ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 92LL);
      D2D1StrokeStyle = xpsrdr::CreateD2D1StrokeStyle(v84, a1, v86);
      v42 = std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(&si128, D2D1StrokeStyle);
      std::shared_ptr<XgcSolidPath>::swap(v42, v93);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&si128);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v84);
      v46 = std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488, v43, v44, v45);
      xpsrdr::GetGeometryBounds(a1, v90, v46, v89, LODWORD(v85), v93, &v99);
      if ( a9 )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        xpsrdr::RenderBoundingBox(v47, a2, &v99, &si128);
      }
    }
    v48 = xpsrdr::RectUnion((xpsrdr *)&si128, &v98, &v99, v40);
    v49 = fminf(a3[3], v48->bottom);
    v50 = fminf(a3[2], v48->right);
    v51 = fmaxf(a3[1], v48->top);
    *a3 = fmaxf(*a3, v48->left);
    a3[1] = v51;
    a3[2] = v50;
    a3[3] = v49;
    if ( !xpsrdr::RectEmpty((xpsrdr *)a3, v52) )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&si128);
      if ( !(unsigned __int8)std::operator!=<ID3D11Device>(a6)
        || (std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v84),
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v84, a6),
            (unsigned __int8)xpsrdr::ProcessOpacityMaskBrush(a1, v84, a3, a4, &si128)) )
      {
        if ( (unsigned __int8)std::operator!=<ID3D11Device>(a4)
          || (unsigned __int8)std::operator!=<ID3D11Device>(&si128)
          || a8 < 1.0 )
        {
          v53 = xpsrdr::CreateAndPushLayer(a1, a2, *(unsigned int *)(a1 + 88), a3, a4, LODWORD(a8), &si128);
          *(_BYTE *)(v87 + 48) = v53;
        }
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v92);
        LODWORD(v84[0]) = 0;
        v54 = *(_QWORD *)v86[0];
        *(_QWORD *)&v87 = 0;
        *((_QWORD *)&v87 + 1) = v84;
        v88 = v92;
        v55 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(v54 + 488))(v86[0], &v87);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v87);
        if ( SLODWORD(v84[0]) < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v84[0]), v56, v57, v58);
        if ( v55 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v55, v56, v57, v58);
        v60 = 3;
        if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v92) || xpsrdr::RectEmpty((xpsrdr *)&v98, v59) )
          goto LABEL_43;
        ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 96LL);
        LODWORD(v84[0]) = 0;
        v61 = (*((__int64 (__fastcall **)(__int64 (__fastcall ***)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *), xpsrdr **))*v92[0]
               + 4))(
                v92[0],
                v84);
        if ( v61 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v61, v62, v63, v64);
        if ( LODWORD(v84[0]) == 10
          && (++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 56LL),
              xpsrdr::DepthGuard::DepthGuard((xpsrdr::DepthGuard *)&v87, v62, (int *)(a1 + 540)),
              v65 = xpsrdr::UnrollVisualBrush(a1, (_DWORD)a2, (_DWORD)a3, (unsigned int)v92, (__int64)v90),
              --*(_DWORD *)v87,
              v65) )
        {
LABEL_43:
          v66 = a1 + 488;
        }
        else
        {
          v66 = a1 + 488;
          v67 = (xpsrdr *)std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488, v62, v63, v64);
          xpsrdr::CreateD2D1Brush(v94, a1, v92, v67, (__int128 *)&v98);
          v68 = 3;
          if ( (unsigned __int8)std::operator!=<ID3D11Device>(v95) )
          {
            v87 = 0;
            v69 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v87);
            v68 = xpsrdr::CreateAndPushLayer(a1, a2, *(unsigned int *)(a1 + 88), a3, v95, LODWORD(FLOAT_1_0), v69);
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v87);
          }
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 304LL))(*a2, 362854208, 1801);
          v70 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(a2);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v70 + 184LL))(v70, v90[0], v94[0], 0);
          if ( (unsigned __int8)std::operator!=<ID3D11Device>(v95) )
          {
            LOBYTE(v72) = v68;
            xpsrdr::PopLayer(v71, a2, v72);
          }
          std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v94);
        }
        if ( (unsigned __int8)std::operator!=<ID3D11Device>(v91) && !xpsrdr::RectEmpty((xpsrdr *)&v99, v73) )
        {
          v77 = (xpsrdr *)std::stack<D2D_MATRIX_3X2_F>::top(v66, v74, v75, v76);
          xpsrdr::CreateD2D1Brush(v94, a1, v91, v77, (__int128 *)&v99);
          v78 = v93[0];
          if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v93[0] + 104LL))(v93[0]) == 1
            || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v78 + 104LL))(v78) == 2 )
          {
            v85 = (float)*(int *)(a1 + 532);
          }
          if ( (unsigned __int8)std::operator!=<ID3D11Device>(v95) )
          {
            v87 = 0;
            v79 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v87);
            v60 = xpsrdr::CreateAndPushLayer(a1, a2, *(unsigned int *)(a1 + 88), a3, v95, LODWORD(FLOAT_1_0), v79);
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v87);
          }
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 304LL))(*a2, 362854208, 1858);
          v80 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(a2);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v80 + 176LL))(v80, v90[0], v94[0]);
          if ( (unsigned __int8)std::operator!=<ID3D11Device>(v95) )
          {
            LOBYTE(v82) = v60;
            xpsrdr::PopLayer(v81, a2, v82);
          }
          std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v94);
        }
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v92);
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&si128);
    }
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v93);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v91);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v90);
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v89);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v86);
}

```

## disassembly

```asm
0x18003a18c  mov     rax, rsp
0x18003a18f  push    rbp
0x18003a190  push    rbx
0x18003a191  push    rsi
0x18003a192  push    rdi
0x18003a193  push    r12
0x18003a195  push    r13
0x18003a197  push    r14
0x18003a199  push    r15
0x18003a19b  lea     rbp, [rsp-48h]
0x18003a1a0  sub     rsp, 148h
0x18003a1a7  movaps  xmmword ptr [rax-58h], xmm6
0x18003a1ab  mov     rax, cs:__security_cookie
0x18003a1b2  xor     rax, rsp
0x18003a1b5  mov     [rbp+80h+var_58], rax
0x18003a1b9  mov     r15, r9
0x18003a1bc  mov     rsi, r8
0x18003a1bf  mov     rdi, rdx
0x18003a1c2  mov     rbx, rcx
0x18003a1c5  mov     rdx, [rbp+80h+arg_20]
0x18003a1cc  mov     r12, [rbp+80h+arg_28]
0x18003a1d3  mov     rax, [rbp+80h+arg_30]
0x18003a1da  mov     qword ptr [rsp+180h+var_118], rax
0x18003a1df  mov     rax, [rcx+220h]
0x18003a1e6  inc     dword ptr [rax+58h]
0x18003a1e9  lea     rcx, [rsp+180h+var_128]
0x18003a1ee  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a1f3  nop
0x18003a1f4  xor     r13d, r13d
0x18003a1f7  mov     dword ptr [rsp+180h+var_140], r13d
0x18003a1fc  mov     rcx, [rdx]
0x18003a1ff  mov     rax, [rcx]
0x18003a202  mov     qword ptr [rbp+80h+var_90], r13
0x18003a206  lea     rdx, [rsp+180h+var_140]
0x18003a20b  mov     qword ptr [rbp+80h+var_90+8], rdx
0x18003a20f  lea     rdx, [rsp+180h+var_128]
0x18003a214  mov     [rbp+80h+var_80], rdx
0x18003a218  lea     r8, [rbp+80h+var_90]
0x18003a21c  lea     rdx, _GUID_37d38bb6_3ee9_4110_9312_14b194163337
0x18003a223  mov     rax, [rax]
0x18003a226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a22b  mov     r14d, eax
0x18003a22e  lea     rcx, [rbp+80h+var_90]
0x18003a232  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003a237  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x18003a23b  test    ecx, ecx
0x18003a23d  jns     short loc_18003A245
0x18003a23f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a245  test    r14d, r14d
0x18003a248  jns     short loc_18003A253
0x18003a24a  mov     ecx, r14d; this
0x18003a24d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a253  xorps   xmm6, xmm6
0x18003a256  mov     [rsp+180h+var_130], 0
0x18003a25e  mov     rcx, [rsp+180h+var_128]
0x18003a263  mov     rax, [rcx]
0x18003a266  lea     rdx, [rsp+180h+var_130]
0x18003a26b  mov     rax, [rax+1D8h]
0x18003a272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a277  test    eax, eax
0x18003a279  jns     short loc_18003A283
0x18003a27b  mov     ecx, eax; this
0x18003a27d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a283  lea     rcx, [rbp+80h+var_100]
0x18003a287  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a28c  nop
0x18003a28d  mov     dword ptr [rsp+180h+var_140], r13d
0x18003a292  mov     rcx, [rsp+180h+var_128]
0x18003a297  mov     rax, [rcx]
0x18003a29a  mov     qword ptr [rbp+80h+var_90], r13
0x18003a29e  lea     rdx, [rsp+180h+var_140]
0x18003a2a3  mov     qword ptr [rbp+80h+var_90+8], rdx
0x18003a2a7  lea     rdx, [rbp+80h+var_100]
0x18003a2ab  mov     [rbp+80h+var_80], rdx
0x18003a2af  lea     rdx, [rbp+80h+var_90]
0x18003a2b3  mov     rax, [rax+0F0h]
0x18003a2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2bf  mov     r14d, eax
0x18003a2c2  lea     rcx, [rbp+80h+var_90]
0x18003a2c6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003a2cb  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x18003a2cf  test    ecx, ecx
0x18003a2d1  jns     short loc_18003A2D9
0x18003a2d3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a2d9  test    r14d, r14d
0x18003a2dc  jns     short loc_18003A2E7
0x18003a2de  mov     ecx, r14d; this
0x18003a2e1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a2e7  lea     rcx, [rbp+80h+var_100]
0x18003a2eb  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003a2f0  test    al, al
0x18003a2f2  jz      loc_18003A949
0x18003a2f8  lea     r8, [rbp+80h+var_100]
0x18003a2fc  mov     rdx, rbx
0x18003a2ff  lea     rcx, [rbp+80h+var_F0]
0x18003a303  call    ?CreateD2D1PathGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGeometry@@@3@@Z; xpsrdr::CreateD2D1PathGeometry(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGeometry> const &)
0x18003a308  nop
0x18003a309  xorps   xmm0, xmm0
0x18003a30c  movups  xmmword ptr [rbp+80h+var_78.left], xmm0
0x18003a310  xorps   xmm1, xmm1
0x18003a313  movups  [rbp+80h+var_90], xmm1
0x18003a317  lea     rcx, [rbp+80h+var_90]
0x18003a31b  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a320  mov     r9, rax
0x18003a323  lea     rcx, [rbx+1E8h]
0x18003a32a  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x18003a32f  lea     rcx, [rbp+80h+var_78]
0x18003a333  mov     [rsp+180h+var_150], rcx
0x18003a338  mov     [rsp+180h+var_158], r9
0x18003a33d  movss   dword ptr [rsp+180h+var_160], xmm6
0x18003a343  lea     r9, [rbp+80h+var_100]
0x18003a347  mov     r8, rax
0x18003a34a  lea     rdx, [rbp+80h+var_F0]
0x18003a34e  mov     rcx, rbx
0x18003a351  call    ?GetGeometryBounds@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@UIXpsOMGeometry@@@4@MAEBV?$shared_ptr@UID2D1StrokeStyle1@@@4@AEAUD2D_RECT_F@@@Z; xpsrdr::GetGeometryBounds(xpsrdr::RenderState &,std::shared_ptr<ID2D1Geometry> const &,D2D_MATRIX_3X2_F const &,std::shared_ptr<IXpsOMGeometry> const &,float,std::shared_ptr<ID2D1StrokeStyle1> const &,D2D_RECT_F &)
0x18003a356  nop
0x18003a357  lea     rcx, [rbp+80h+var_90]
0x18003a35b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18003a360  mov     r13b, [rbp+80h+arg_40]
0x18003a367  test    r13b, r13b
0x18003a36a  jz      short loc_18003A388
0x18003a36c  movdqa  xmm0, cs:__xmm@3e4ccccd00000000000000003e4ccccd
0x18003a374  movups  [rbp+80h+var_90], xmm0
0x18003a378  lea     r9, [rbp+80h+var_90]
0x18003a37c  lea     r8, [rbp+80h+var_78]
0x18003a380  mov     rdx, rdi
0x18003a383  call    ?RenderBoundingBox@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEBUD2D_RECT_F@@AEBU_D3DCOLORVALUE@@@Z; xpsrdr::RenderBoundingBox(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F const &,_D3DCOLORVALUE const &)
0x18003a388  movups  xmm0, xmmword ptr [rbp+80h+var_78.left]
0x18003a38c  movups  xmmword ptr [rbp+80h+var_68.left], xmm0
0x18003a390  lea     rcx, [rbp+80h+var_E0]
0x18003a394  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a399  nop
0x18003a39a  mov     dword ptr [rsp+180h+var_140], 0
0x18003a3a2  mov     rcx, [rsp+180h+var_128]
0x18003a3a7  mov     rax, [rcx]
0x18003a3aa  mov     qword ptr [rbp+80h+var_90], 0
0x18003a3b2  lea     rdx, [rsp+180h+var_140]
0x18003a3b7  mov     qword ptr [rbp+80h+var_90+8], rdx
0x18003a3bb  lea     rdx, [rbp+80h+var_E0]
0x18003a3bf  mov     [rbp+80h+var_80], rdx
0x18003a3c3  lea     rdx, [rbp+80h+var_90]
0x18003a3c7  mov     rax, [rax+148h]
0x18003a3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3d3  mov     r14d, eax
0x18003a3d6  lea     rcx, [rbp+80h+var_90]
0x18003a3da  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003a3df  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x18003a3e3  test    ecx, ecx
0x18003a3e5  jns     short loc_18003A3ED
0x18003a3e7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a3ed  test    r14d, r14d
0x18003a3f0  jns     short loc_18003A3FB
0x18003a3f2  mov     ecx, r14d; this
0x18003a3f5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a3fb  lea     rcx, [rbp+80h+var_C0]
0x18003a3ff  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a404  nop
0x18003a405  lea     rcx, [rbp+80h+var_E0]
0x18003a409  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003a40e  test    al, al
0x18003a410  jz      loc_18003A4BB
0x18003a416  mov     rax, [rbx+220h]
0x18003a41d  inc     dword ptr [rax+5Ch]
0x18003a420  lea     r8, [rsp+180h+var_128]
0x18003a425  mov     rdx, rbx
0x18003a428  lea     rcx, [rsp+180h+var_140]
0x18003a42d  call    ?CreateD2D1StrokeStyle@xpsrdr@@YA?AV?$shared_ptr@UID2D1StrokeStyle1@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMPath@@@3@@Z; xpsrdr::CreateD2D1StrokeStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)
0x18003a432  mov     rdx, rax
0x18003a435  lea     rcx, [rbp+80h+var_90]
0x18003a439  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x18003a43e  lea     rdx, [rbp+80h+var_C0]
0x18003a442  mov     rcx, rax
0x18003a445  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x18003a44a  lea     rcx, [rbp+80h+var_90]
0x18003a44e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18003a453  lea     rcx, [rsp+180h+var_140]
0x18003a458  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18003a45d  lea     rcx, [rbx+1E8h]
0x18003a464  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x18003a469  lea     rcx, [rbp+80h+var_68]
0x18003a46d  mov     [rsp+180h+var_150], rcx
0x18003a472  lea     rcx, [rbp+80h+var_C0]
0x18003a476  mov     [rsp+180h+var_158], rcx
0x18003a47b  movss   xmm0, [rsp+180h+var_130]
0x18003a481  movss   dword ptr [rsp+180h+var_160], xmm0
0x18003a487  lea     r9, [rbp+80h+var_100]
0x18003a48b  mov     r8, rax
0x18003a48e  lea     rdx, [rbp+80h+var_F0]
0x18003a492  mov     rcx, rbx
0x18003a495  call    ?GetGeometryBounds@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@UIXpsOMGeometry@@@4@MAEBV?$shared_ptr@UID2D1StrokeStyle1@@@4@AEAUD2D_RECT_F@@@Z; xpsrdr::GetGeometryBounds(xpsrdr::RenderState &,std::shared_ptr<ID2D1Geometry> const &,D2D_MATRIX_3X2_F const &,std::shared_ptr<IXpsOMGeometry> const &,float,std::shared_ptr<ID2D1StrokeStyle1> const &,D2D_RECT_F &)
0x18003a49a  test    r13b, r13b
0x18003a49d  jz      short loc_18003A4BB
0x18003a49f  movdqa  xmm0, cs:__xmm@3f00000000000000000000003f000000
0x18003a4a7  movups  [rbp+80h+var_90], xmm0
0x18003a4ab  lea     r9, [rbp+80h+var_90]
0x18003a4af  lea     r8, [rbp+80h+var_68]
0x18003a4b3  mov     rdx, rdi
0x18003a4b6  call    ?RenderBoundingBox@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEBUD2D_RECT_F@@AEBU_D3DCOLORVALUE@@@Z; xpsrdr::RenderBoundingBox(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F const &,_D3DCOLORVALUE const &)
0x18003a4bb  lea     r8, [rbp+80h+var_68]; struct D2D_RECT_F *
0x18003a4bf  lea     rdx, [rbp+80h+var_78]; retstr
0x18003a4c3  lea     rcx, [rbp+80h+var_90]; this
0x18003a4c7  call    ?RectUnion@xpsrdr@@YA?AUD2D_RECT_F@@AEBU2@0@Z; xpsrdr::RectUnion(D2D_RECT_F const &,D2D_RECT_F const &)
0x18003a4cc  movss   xmm4, dword ptr [rsi+0Ch]
0x18003a4d1  minss   xmm4, dword ptr [rax+0Ch]
0x18003a4d6  movss   xmm2, dword ptr [rsi+8]
0x18003a4db  minss   xmm2, dword ptr [rax+8]
0x18003a4e0  movss   xmm1, dword ptr [rsi+4]
0x18003a4e5  maxss   xmm1, dword ptr [rax+4]
0x18003a4ea  movss   xmm0, dword ptr [rsi]
0x18003a4ee  maxss   xmm0, dword ptr [rax]
0x18003a4f2  movss   dword ptr [rsi], xmm0
0x18003a4f6  movss   dword ptr [rsi+4], xmm1
0x18003a4fb  movss   dword ptr [rsi+8], xmm2
0x18003a500  movss   dword ptr [rsi+0Ch], xmm4
0x18003a505  mov     rcx, rsi; this
0x18003a508  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x18003a50d  xor     r13d, r13d
0x18003a510  test    al, al
0x18003a512  jnz     loc_18003A92B
0x18003a518  lea     rcx, [rbp+80h+var_90]
0x18003a51c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a521  nop
0x18003a522  mov     rcx, r12
0x18003a525  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003a52a  test    al, al
0x18003a52c  jz      short loc_18003A569
0x18003a52e  lea     rcx, [rsp+180h+var_140]
0x18003a533  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003a538  mov     rdx, r12
0x18003a53b  lea     rcx, [rsp+180h+var_140]
0x18003a540  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18003a545  lea     rcx, [rbp+80h+var_90]
0x18003a549  mov     [rsp+180h+var_160], rcx
0x18003a54e  mov     r9, r15
0x18003a551  mov     r8, rsi
0x18003a554  lea     rdx, [rsp+180h+var_140]
0x18003a559  mov     rcx, rbx
0x18003a55c  call    ?ProcessOpacityMaskBrush@xpsrdr@@YA_NAEAURenderState@1@V?$shared_ptr@UIXpsOMBrush@@@std@@AEAUD2D_RECT_F@@AEAV?$shared_ptr@UID2D1Geometry@@@4@AEAV?$shared_ptr@UID2D1Brush@@@4@@Z; xpsrdr::ProcessOpacityMaskBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush>,D2D_RECT_F &,std::shared_ptr<ID2D1Geometry> &,std::shared_ptr<ID2D1Brush> &)
0x18003a561  test    al, al
0x18003a563  jz      loc_18003A921
0x18003a569  mov     rcx, r15
0x18003a56c  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003a571  movss   xmm0, [rbp+80h+arg_38]
0x18003a579  movss   xmm6, cs:__real@3f800000
0x18003a581  test    al, al
0x18003a583  jnz     short loc_18003A597
0x18003a585  lea     rcx, [rbp+80h+var_90]
0x18003a589  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003a58e  test    al, al
0x18003a590  jnz     short loc_18003A597
0x18003a592  comiss  xmm6, xmm0
0x18003a595  jbe     short loc_18003A5C5
0x18003a597  lea     rax, [rbp+80h+var_90]
0x18003a59b  mov     [rsp+180h+var_150], rax
0x18003a5a0  movss   dword ptr [rsp+180h+var_158], xmm0
0x18003a5a6  mov     [rsp+180h+var_160], r15
0x18003a5ab  mov     r9, rsi
0x18003a5ae  mov     r8d, [rbx+58h]
0x18003a5b2  mov     rdx, rdi
0x18003a5b5  mov     rcx, rbx
0x18003a5b8  call    ?CreateAndPushLayer@xpsrdr@@YA?AW4LAYER_CLIP_USE@1@AEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@W4D2D1_ANTIALIAS_MODE@@AEBUD2D_RECT_F@@AEBV?$shared_ptr@UID2D1Geometry@@@5@MAEBV?$shared_ptr@UID2D1Brush@@@5@@Z; xpsrdr::CreateAndPushLayer(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D1_ANTIALIAS_MODE,D2D_RECT_F const &,std::shared_ptr<ID2D1Geometry> const &,float,std::shared_ptr<ID2D1Brush> const &)
0x18003a5bd  mov     rcx, qword ptr [rsp+180h+var_118]
0x18003a5c2  mov     [rcx+30h], al
0x18003a5c5  lea     rcx, [rbp+80h+var_D0]
0x18003a5c9  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003a5ce  nop
0x18003a5cf  mov     dword ptr [rsp+180h+var_140], r13d
0x18003a5d4  mov     rcx, [rsp+180h+var_128]
0x18003a5d9  mov     rax, [rcx]
0x18003a5dc  mov     qword ptr [rsp+180h+var_118], r13
0x18003a5e1  lea     rdx, [rsp+180h+var_140]
0x18003a5e6  mov     qword ptr [rsp+180h+var_118+8], rdx
0x18003a5eb  lea     rdx, [rbp+80h+var_D0]
0x18003a5ef  mov     [rsp+180h+var_108], rdx
0x18003a5f4  lea     rdx, [rsp+180h+var_118]
0x18003a5f9  mov     rax, [rax+1E8h]
0x18003a600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a605  mov     r14d, eax
0x18003a608  lea     rcx, [rsp+180h+var_118]
0x18003a60d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003a612  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x18003a616  test    ecx, ecx
0x18003a618  jns     short loc_18003A620
0x18003a61a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a620  test    r14d, r14d
0x18003a623  jns     short loc_18003A62E
0x18003a625  mov     ecx, r14d; this
0x18003a628  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003a62e  lea     rcx, [rbp+80h+var_D0]
0x18003a632  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003a637  mov     r15b, 3
0x18003a63a  test    al, al
0x18003a63c  jz      loc_18003A7C4
0x18003a642  lea     rcx, [rbp+80h+var_78]; this
0x18003a646  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x18003a64b  test    al, al
0x18003a64d  jnz     loc_18003A7C4
0x18003a653  mov     rax, [rbx+220h]
0x18003a65a  inc     dword ptr [rax+60h]
0x18003a65d  mov     dword ptr [rsp+180h+var_140], r13d
  ... truncated ...
```
