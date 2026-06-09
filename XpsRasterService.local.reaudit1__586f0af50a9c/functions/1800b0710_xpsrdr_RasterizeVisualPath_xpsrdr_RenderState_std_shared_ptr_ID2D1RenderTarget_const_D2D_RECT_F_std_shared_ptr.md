# xpsrdr::RasterizeVisualPath(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F &,std::shared_ptr<ID2D1Geometry> &,std::shared_ptr<IXpsOMVisual> const &,std::shared_ptr<IXpsOMBrush> &,xpsrdr::RenderStateHolder &,float,bool)

- ea: `0x1800b0710`
- end: `0x1800b0e8b`
- name: `?RasterizeVisualPath@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEAUD2D_RECT_F@@AEAV?$shared_ptr@UID2D1Geometry@@@4@AEBV?$shared_ptr@UIXpsOMVisual@@@4@AEAV?$shared_ptr@UIXpsOMBrush@@@4@AEAURenderStateHolder@1@M_N@Z`
- size: `1915`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800af8f4`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a82e8`
- `0x1800a86b4`
- `0x1800a9714`
- `0x1800aa8b4`
- `0x1800ab61c`
- `0x1800ab640`
- `0x1800adb68`
- `0x1800ae278`
- `0x1800aeaa8`
- `0x1800aeb6c`
- `0x1800b0710`
- `0x1800b0ff4`
- `0x1800b1150`
- `0x1800b20e8`
- `0x1800b3ecc`
- `0x1800b5da8`
- `0x1800b692c`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall xpsrdr::RasterizeVisualPath(
        __int64 a1,
        _QWORD *a2,
        float *a3,
        _QWORD *a4,
        _QWORD **a5,
        __int64 a6,
        std::_Ref_count_base *a7,
        float a8,
        char a9)
{
  __int64 (__fastcall ***v13)(_QWORD, GUID *, std::_Ref_count_base **); // rcx
  __int64 (__fastcall **v14)(_QWORD, GUID *, std::_Ref_count_base **); // rax
  int v15; // edi
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  int v19; // eax
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  __int64 v23; // rax
  int v24; // edi
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // edi
  int v32; // edx
  const char *v33; // r8
  const struct D2D_RECT_F *v34; // r9
  __int64 *D2D1StrokeStyle; // rax
  __int64 v36; // r15
  std::_Ref_count_base *v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  struct D2D_RECT_F *v40; // rax
  float v41; // xmm4_4
  float v42; // xmm2_4
  float v43; // xmm1_4
  const struct D2D_RECT_F *v44; // rdx
  __int64 v45; // rax
  char v46; // al
  __int64 v47; // rax
  int v48; // r12d
  const struct D2D_RECT_F *v49; // rdx
  const char *v50; // r8
  int v51; // r9d
  char v52; // r12
  int v53; // eax
  int v54; // edx
  const char *v55; // r8
  int v56; // r9d
  char v57; // al
  xpsrdr *v58; // rax
  char v59; // r13
  __int64 v60; // rcx
  __int64 v61; // r8
  xpsrdr *v62; // rax
  __int64 v63; // rcx
  __int64 v64; // r8
  int v65; // [rsp+48h] [rbp-C0h] BYREF
  float v66; // [rsp+4Ch] [rbp-BCh] BYREF
  xpsrdr *v67[2]; // [rsp+50h] [rbp-B8h] BYREF
  std::_Ref_count_base *v68[2]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v69[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v70; // [rsp+88h] [rbp-80h] BYREF
  std::_Ref_count_base *v71; // [rsp+90h] [rbp-78h]
  __int64 v72[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v73[2]; // [rsp+A8h] [rbp-60h] BYREF
  std::_Ref_count_base *v74[2]; // [rsp+B8h] [rbp-50h] BYREF
  std::_Ref_count_base *v75[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v76; // [rsp+D8h] [rbp-30h] BYREF
  std::_Ref_count_base *v77[2]; // [rsp+E8h] [rbp-20h] BYREF
  std::_Ref_count_base **v78; // [rsp+F8h] [rbp-10h]
  struct D2D_RECT_F v79; // [rsp+100h] [rbp-8h] BYREF
  struct D2D_RECT_F v80; // [rsp+110h] [rbp+8h] BYREF

  v72[0] = a6;
  v68[0] = a7;
  ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 88LL);
  *(_OWORD *)v67 = 0;
  v65 = 0;
  v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, std::_Ref_count_base **))*a5;
  v14 = (__int64 (__fastcall **)(_QWORD, GUID *, std::_Ref_count_base **))**a5;
  v77[0] = 0;
  v77[1] = (std::_Ref_count_base *)&v65;
  v78 = v67;
  v15 = (*v14)(v13, &GUID_37d38bb6_3ee9_4110_9312_14b194163337, v77);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v77);
  if ( v65 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v16, v17, v18);
  if ( v15 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
  v66 = 0.0;
  v19 = (*(__int64 (__fastcall **)(xpsrdr *, float *))(*(_QWORD *)v67[0] + 472LL))(v67[0], &v66);
  if ( v19 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
  *(_OWORD *)&v69[1] = 0;
  v65 = 0;
  v23 = *(_QWORD *)v67[0];
  v77[0] = 0;
  v77[1] = (std::_Ref_count_base *)&v65;
  v78 = (std::_Ref_count_base **)&v69[1];
  v24 = (*(__int64 (__fastcall **)(xpsrdr *, std::_Ref_count_base **))(v23 + 240))(v67[0], v77);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v77);
  if ( v65 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v25, v26, v27);
  if ( v24 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
  if ( v69[1] )
  {
    xpsrdr::CreateD2D1PathGeometry(&v70, a1, &v69[1]);
    v79 = 0;
    *(_OWORD *)v77 = 0;
    v28 = std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488);
    xpsrdr::GetGeometryBounds(a1, &v70, v28, &v69[1], 0, v77, &v79);
    if ( a9 )
    {
      *(__m128i *)v77 = _mm_load_si128((const __m128i *)&_xmm);
      xpsrdr::RenderBoundingBox(v29, a2, &v79, v77);
    }
    v80 = v79;
    *(_OWORD *)v74 = 0;
    v65 = 0;
    v30 = *(_QWORD *)v67[0];
    v77[0] = 0;
    v77[1] = (std::_Ref_count_base *)&v65;
    v78 = v74;
    v31 = (*(__int64 (__fastcall **)(xpsrdr *, std::_Ref_count_base **))(v30 + 328))(v67[0], v77);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v77);
    if ( v65 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v32, v33, (int)v34);
    if ( v31 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v31, v32, v33, (int)v34);
    v76 = 0;
    if ( v74[0] )
    {
      ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 92LL);
      D2D1StrokeStyle = (__int64 *)xpsrdr::CreateD2D1StrokeStyle(v77, a1, v67);
      v36 = *D2D1StrokeStyle;
      v37 = (std::_Ref_count_base *)D2D1StrokeStyle[1];
      *D2D1StrokeStyle = 0;
      D2D1StrokeStyle[1] = 0;
      *(_QWORD *)&v76 = v36;
      *((_QWORD *)&v76 + 1) = v37;
      if ( v77[1] )
        std::_Ref_count_base::_Decref(v77[1]);
      v38 = std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488);
      xpsrdr::GetGeometryBounds(a1, &v70, v38, &v69[1], LODWORD(v66), &v76, &v80);
      if ( a9 )
      {
        *(__m128i *)v77 = _mm_load_si128((const __m128i *)&_xmm);
        xpsrdr::RenderBoundingBox(v39, a2, &v80, v77);
      }
    }
    else
    {
      v37 = (std::_Ref_count_base *)*((_QWORD *)&v76 + 1);
      v36 = v76;
    }
    v40 = xpsrdr::RectUnion((xpsrdr *)v77, &v79, &v80, v34);
    v41 = fminf(a3[3], v40->bottom);
    v42 = fminf(a3[2], v40->right);
    v43 = fmaxf(a3[1], v40->top);
    *a3 = fmaxf(*a3, v40->left);
    a3[1] = v43;
    a3[2] = v42;
    a3[3] = v41;
    if ( !xpsrdr::RectEmpty((xpsrdr *)a3, v44) )
    {
      *(_OWORD *)v77 = 0;
      if ( !*(_QWORD *)v72[0]
        || (v45 = std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(v72, v72[0]),
            (unsigned __int8)xpsrdr::ProcessOpacityMaskBrush(a1, v45, a3, a4, v77)) )
      {
        if ( *a4 || v77[0] || a8 < 1.0 )
        {
          v46 = xpsrdr::CreateAndPushLayer(a1, a2, *(unsigned int *)(a1 + 88), a3, a4, LODWORD(a8), v77);
          *((_BYTE *)v68[0] + 48) = v46;
        }
        *(_OWORD *)v75 = 0;
        v65 = 0;
        v47 = *(_QWORD *)v67[0];
        v68[0] = 0;
        v68[1] = (std::_Ref_count_base *)&v65;
        v69[0] = v75;
        v48 = (*(__int64 (__fastcall **)(xpsrdr *, std::_Ref_count_base **))(v47 + 488))(v67[0], v68);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v68);
        if ( v65 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, (int)v49, v50, v51);
        if ( v48 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, (int)v49, v50, v51);
        v52 = 3;
        if ( v75[0] && !xpsrdr::RectEmpty((xpsrdr *)&v79, v49) )
        {
          ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 96LL);
          v65 = 0;
          v53 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v75[0] + 32LL))(v75[0], &v65);
          if ( v53 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v53, v54, v55, v56);
          if ( v65 != 10
            || (++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 56LL),
                xpsrdr::DepthGuard::DepthGuard((xpsrdr::DepthGuard *)v68, v54, (int *)(a1 + 540)),
                v57 = xpsrdr::UnrollVisualBrush(a1, (_DWORD)a2, (_DWORD)a3, (unsigned int)v75, (__int64)&v70),
                --*(_DWORD *)v68[0],
                !v57) )
          {
            v58 = (xpsrdr *)std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488);
            xpsrdr::CreateD2D1Brush(
              v72,
              a1,
              (__int64 (__fastcall ****)(__int64, GUID *, struct D2D_MATRIX_3X2_F *))v75,
              v58,
              &v79);
            v59 = 3;
            if ( v73[0] )
            {
              *(_OWORD *)v68 = 0;
              v59 = xpsrdr::CreateAndPushLayer(a1, a2, *(unsigned int *)(a1 + 88), a3, v73, LODWORD(FLOAT_1_0), v68);
            }
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 304LL))(*a2, 362854208, 1801);
            (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(*(_QWORD *)*a2 + 184LL))(*a2, v70, v72[0], 0);
            if ( v73[0] )
            {
              LOBYTE(v61) = v59;
              xpsrdr::PopLayer(v60, a2, v61);
            }
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v72);
          }
        }
        if ( v74[0] && !xpsrdr::RectEmpty((xpsrdr *)&v80, v49) )
        {
          v62 = (xpsrdr *)std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488);
          xpsrdr::CreateD2D1Brush(
            v72,
            a1,
            (__int64 (__fastcall ****)(__int64, GUID *, struct D2D_MATRIX_3X2_F *))v74,
            v62,
            &v80);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v36 + 104LL))(v36) == 1
            || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v36 + 104LL))(v36) == 2 )
          {
            v66 = (float)*(int *)(a1 + 532);
          }
          if ( v73[0] )
          {
            *(_OWORD *)v68 = 0;
            v52 = xpsrdr::CreateAndPushLayer(a1, a2, *(unsigned int *)(a1 + 88), a3, v73, LODWORD(FLOAT_1_0), v68);
          }
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 304LL))(*a2, 362854208, 1858);
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 176LL))(*a2, v70, v72[0]);
          if ( v73[0] )
          {
            LOBYTE(v64) = v52;
            xpsrdr::PopLayer(v63, a2, v64);
          }
          std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v72);
        }
        if ( v75[1] )
          std::_Ref_count_base::_Decref(v75[1]);
      }
      if ( v77[1] )
        std::_Ref_count_base::_Decref(v77[1]);
    }
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    if ( v74[1] )
      std::_Ref_count_base::_Decref(v74[1]);
    if ( v71 )
      std::_Ref_count_base::_Decref(v71);
  }
  if ( v69[2] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v69[2]);
  if ( v67[1] )
    std::_Ref_count_base::_Decref(v67[1]);
}

```

## disassembly

```asm
0x1800b0710  mov     rax, rsp
0x1800b0713  push    rbp
0x1800b0714  push    rbx
0x1800b0715  push    rsi
0x1800b0716  push    rdi
0x1800b0717  push    r12
0x1800b0719  push    r13
0x1800b071b  push    r14
0x1800b071d  push    r15
0x1800b071f  lea     rbp, [rax-78h]
0x1800b0723  sub     rsp, 138h
0x1800b072a  movaps  xmmword ptr [rax-58h], xmm6
0x1800b072e  mov     rax, cs:__security_cookie
0x1800b0735  xor     rax, rsp
0x1800b0738  mov     qword ptr [rbp+70h+var_58], rax
0x1800b073c  mov     r12, r9
0x1800b073f  mov     r14, r8
0x1800b0742  mov     rsi, rdx
0x1800b0745  mov     rbx, rcx
0x1800b0748  mov     rcx, [rbp+70h+arg_20]
0x1800b074f  mov     rax, [rbp+70h+arg_28]
0x1800b0756  mov     [rbp+70h+var_E0], rax
0x1800b075a  mov     rax, [rbp+70h+arg_30]
0x1800b0761  mov     [rsp+170h+var_120+8], rax
0x1800b0766  mov     rax, [rbx+220h]
0x1800b076d  inc     dword ptr [rax+58h]
0x1800b0770  xorps   xmm0, xmm0
0x1800b0773  movdqu  xmmword ptr [rsp+170h+var_130+8], xmm0
0x1800b0779  xor     r15d, r15d
0x1800b077c  mov     dword ptr [rsp+170h+var_130], r15d
0x1800b0781  mov     rcx, [rcx]
0x1800b0784  mov     rax, [rcx]
0x1800b0787  mov     [rbp+70h+var_90], r15
0x1800b078b  lea     rdx, [rsp+170h+var_130]
0x1800b0790  mov     [rbp+70h+var_90+8], rdx
0x1800b0794  lea     rdx, [rsp+170h+var_130+8]
0x1800b0799  mov     [rbp+70h+var_80], rdx
0x1800b079d  lea     r8, [rbp+70h+var_90]
0x1800b07a1  lea     rdx, _GUID_37d38bb6_3ee9_4110_9312_14b194163337
0x1800b07a8  mov     rax, [rax]
0x1800b07ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07b0  mov     edi, eax
0x1800b07b2  lea     rcx, [rbp+70h+var_90]
0x1800b07b6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b07bb  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800b07bf  test    ecx, ecx
0x1800b07c1  jns     short loc_1800B07C9
0x1800b07c3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b07c9  test    edi, edi
0x1800b07cb  jns     short loc_1800B07D5
0x1800b07cd  mov     ecx, edi; this
0x1800b07cf  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b07d5  xorps   xmm6, xmm6
0x1800b07d8  mov     dword ptr [rsp+170h+var_130+4], 0
0x1800b07e0  mov     rcx, [rsp+170h+var_130+8]
0x1800b07e5  mov     rax, [rcx]
0x1800b07e8  lea     rdx, [rsp+170h+var_130+4]
0x1800b07ed  mov     rax, [rax+1D8h]
0x1800b07f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07f9  test    eax, eax
0x1800b07fb  jns     short loc_1800B0805
0x1800b07fd  mov     ecx, eax; this
0x1800b07ff  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b0805  xorps   xmm0, xmm0
0x1800b0808  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm0
0x1800b080e  mov     dword ptr [rsp+170h+var_130], r15d
0x1800b0813  mov     rcx, [rsp+170h+var_130+8]
0x1800b0818  mov     rax, [rcx]
0x1800b081b  mov     [rbp+70h+var_90], r15
0x1800b081f  lea     rdx, [rsp+170h+var_130]
0x1800b0824  mov     [rbp+70h+var_90+8], rdx
0x1800b0828  lea     rdx, [rsp+170h+var_108+8]
0x1800b082d  mov     [rbp+70h+var_80], rdx
0x1800b0831  lea     rdx, [rbp+70h+var_90]
0x1800b0835  mov     rax, [rax+0F0h]
0x1800b083c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0841  mov     edi, eax
0x1800b0843  lea     rcx, [rbp+70h+var_90]
0x1800b0847  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b084c  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800b0850  test    ecx, ecx
0x1800b0852  jns     short loc_1800B085A
0x1800b0854  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b085a  test    edi, edi
0x1800b085c  jns     short loc_1800B0866
0x1800b085e  mov     ecx, edi; this
0x1800b0860  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b0866  cmp     qword ptr [rsp+170h+var_108+8], r15
0x1800b086b  jz      loc_1800B0E44
0x1800b0871  lea     r8, [rsp+170h+var_108+8]
0x1800b0876  mov     rdx, rbx
0x1800b0879  lea     rcx, [rbp+70h+var_F0]
0x1800b087d  call    ?CreateD2D1PathGeometry@xpsrdr@@YA?AV?$shared_ptr@UID2D1Geometry@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGeometry@@@3@@Z; xpsrdr::CreateD2D1PathGeometry(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGeometry> const &)
0x1800b0882  nop
0x1800b0883  xorps   xmm0, xmm0
0x1800b0886  movups  xmmword ptr [rbp+70h+var_78.left], xmm0
0x1800b088a  movdqu  xmmword ptr [rbp+70h+var_90], xmm0
0x1800b088f  lea     rcx, [rbx+1E8h]
0x1800b0896  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x1800b089b  lea     rcx, [rbp+70h+var_78]
0x1800b089f  mov     [rsp+30h], rcx
0x1800b08a4  lea     rcx, [rbp+70h+var_90]
0x1800b08a8  mov     [rsp+170h+var_148], rcx
0x1800b08ad  movss   dword ptr [rsp+170h+var_150], xmm6
0x1800b08b3  lea     r9, [rsp+170h+var_108+8]
0x1800b08b8  mov     r8, rax
0x1800b08bb  lea     rdx, [rbp+70h+var_F0]
0x1800b08bf  mov     rcx, rbx
0x1800b08c2  call    ?GetGeometryBounds@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@UIXpsOMGeometry@@@4@MAEBV?$shared_ptr@UID2D1StrokeStyle1@@@4@AEAUD2D_RECT_F@@@Z; xpsrdr::GetGeometryBounds(xpsrdr::RenderState &,std::shared_ptr<ID2D1Geometry> const &,D2D_MATRIX_3X2_F const &,std::shared_ptr<IXpsOMGeometry> const &,float,std::shared_ptr<ID2D1StrokeStyle1> const &,D2D_RECT_F &)
0x1800b08c7  nop
0x1800b08c8  mov     r13b, [rbp+70h+arg_40]
0x1800b08cf  test    r13b, r13b
0x1800b08d2  jz      short loc_1800B08F0
0x1800b08d4  movdqa  xmm0, cs:__xmm@3e4ccccd00000000000000003e4ccccd
0x1800b08dc  movups  xmmword ptr [rbp+70h+var_90], xmm0
0x1800b08e0  lea     r9, [rbp+70h+var_90]
0x1800b08e4  lea     r8, [rbp+70h+var_78]
0x1800b08e8  mov     rdx, rsi
0x1800b08eb  call    ?RenderBoundingBox@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEBUD2D_RECT_F@@AEBU_D3DCOLORVALUE@@@Z; xpsrdr::RenderBoundingBox(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F const &,_D3DCOLORVALUE const &)
0x1800b08f0  movups  xmm0, xmmword ptr [rbp+70h+var_78.left]
0x1800b08f4  movups  xmmword ptr [rbp+70h+var_68.left], xmm0
0x1800b08f8  xorps   xmm1, xmm1
0x1800b08fb  movdqu  xmmword ptr [rbp+70h+var_C0], xmm1
0x1800b0900  mov     dword ptr [rsp+170h+var_130], r15d
0x1800b0905  mov     rcx, [rsp+170h+var_130+8]
0x1800b090a  mov     rax, [rcx]
0x1800b090d  mov     [rbp+70h+var_90], r15
0x1800b0911  lea     rdx, [rsp+170h+var_130]
0x1800b0916  mov     [rbp+70h+var_90+8], rdx
0x1800b091a  lea     rdx, [rbp+70h+var_C0]
0x1800b091e  mov     [rbp+70h+var_80], rdx
0x1800b0922  lea     rdx, [rbp+70h+var_90]
0x1800b0926  mov     rax, [rax+148h]
0x1800b092d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0932  mov     edi, eax
0x1800b0934  lea     rcx, [rbp+70h+var_90]
0x1800b0938  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b093d  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800b0941  test    ecx, ecx
0x1800b0943  jns     short loc_1800B094B
0x1800b0945  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b094b  test    edi, edi
0x1800b094d  jns     short loc_1800B0957
0x1800b094f  mov     ecx, edi; this
0x1800b0951  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b0957  xorps   xmm0, xmm0
0x1800b095a  movdqu  [rbp+70h+var_A0], xmm0
0x1800b095f  cmp     [rbp+70h+var_C0], r15
0x1800b0963  jz      loc_1800B0A11
0x1800b0969  mov     rax, [rbx+220h]
0x1800b0970  inc     dword ptr [rax+5Ch]
0x1800b0973  lea     r8, [rsp+170h+var_130+8]
0x1800b0978  mov     rdx, rbx
0x1800b097b  lea     rcx, [rbp+70h+var_90]
0x1800b097f  call    ?CreateD2D1StrokeStyle@xpsrdr@@YA?AV?$shared_ptr@UID2D1StrokeStyle1@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMPath@@@3@@Z; xpsrdr::CreateD2D1StrokeStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)
0x1800b0984  mov     r15, [rax]
0x1800b0987  mov     rdi, [rax+8]
0x1800b098b  mov     qword ptr [rax], 0
0x1800b0992  mov     qword ptr [rax+8], 0
0x1800b099a  mov     qword ptr [rbp+70h+var_A0], r15
0x1800b099e  mov     qword ptr [rbp+70h+var_A0+8], rdi
0x1800b09a2  mov     rcx, [rbp+70h+var_90+8]; this
0x1800b09a6  test    rcx, rcx
0x1800b09a9  jz      short loc_1800B09B0
0x1800b09ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b09b0  lea     rcx, [rbx+1E8h]
0x1800b09b7  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x1800b09bc  lea     rcx, [rbp+70h+var_68]
0x1800b09c0  mov     [rsp+30h], rcx
0x1800b09c5  lea     rcx, [rbp+70h+var_A0]
0x1800b09c9  mov     [rsp+170h+var_148], rcx
0x1800b09ce  movss   xmm0, dword ptr [rsp+170h+var_130+4]
0x1800b09d4  movss   dword ptr [rsp+170h+var_150], xmm0
0x1800b09da  lea     r9, [rsp+170h+var_108+8]
0x1800b09df  mov     r8, rax
0x1800b09e2  lea     rdx, [rbp+70h+var_F0]
0x1800b09e6  mov     rcx, rbx
0x1800b09e9  call    ?GetGeometryBounds@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@UIXpsOMGeometry@@@4@MAEBV?$shared_ptr@UID2D1StrokeStyle1@@@4@AEAUD2D_RECT_F@@@Z; xpsrdr::GetGeometryBounds(xpsrdr::RenderState &,std::shared_ptr<ID2D1Geometry> const &,D2D_MATRIX_3X2_F const &,std::shared_ptr<IXpsOMGeometry> const &,float,std::shared_ptr<ID2D1StrokeStyle1> const &,D2D_RECT_F &)
0x1800b09ee  test    r13b, r13b
0x1800b09f1  jz      short loc_1800B0A19
0x1800b09f3  movdqa  xmm0, cs:__xmm@3f00000000000000000000003f000000
0x1800b09fb  movups  xmmword ptr [rbp+70h+var_90], xmm0
0x1800b09ff  lea     r9, [rbp+70h+var_90]
0x1800b0a03  lea     r8, [rbp+70h+var_68]
0x1800b0a07  mov     rdx, rsi
0x1800b0a0a  call    ?RenderBoundingBox@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEBUD2D_RECT_F@@AEBU_D3DCOLORVALUE@@@Z; xpsrdr::RenderBoundingBox(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F const &,_D3DCOLORVALUE const &)
0x1800b0a0f  jmp     short loc_1800B0A19
0x1800b0a11  mov     rdi, qword ptr [rbp+70h+var_A0+8]
0x1800b0a15  mov     r15, qword ptr [rbp+70h+var_A0]
0x1800b0a19  lea     r8, [rbp+70h+var_68]; struct D2D_RECT_F *
0x1800b0a1d  lea     rdx, [rbp+70h+var_78]; retstr
0x1800b0a21  lea     rcx, [rbp+70h+var_90]; this
0x1800b0a25  call    ?RectUnion@xpsrdr@@YA?AUD2D_RECT_F@@AEBU2@0@Z; xpsrdr::RectUnion(D2D_RECT_F const &,D2D_RECT_F const &)
0x1800b0a2a  movss   xmm4, dword ptr [r14+0Ch]
0x1800b0a30  minss   xmm4, dword ptr [rax+0Ch]
0x1800b0a35  movss   xmm2, dword ptr [r14+8]
0x1800b0a3b  minss   xmm2, dword ptr [rax+8]
0x1800b0a40  movss   xmm1, dword ptr [r14+4]
0x1800b0a46  maxss   xmm1, dword ptr [rax+4]
0x1800b0a4b  movss   xmm0, dword ptr [r14]
0x1800b0a50  maxss   xmm0, dword ptr [rax]
0x1800b0a54  movss   dword ptr [r14], xmm0
0x1800b0a59  movss   dword ptr [r14+4], xmm1
0x1800b0a5f  movss   dword ptr [r14+8], xmm2
0x1800b0a65  movss   dword ptr [r14+0Ch], xmm4
0x1800b0a6b  mov     rcx, r14; this
0x1800b0a6e  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x1800b0a73  xor     r13d, r13d
0x1800b0a76  test    al, al
0x1800b0a78  jnz     loc_1800B0E18
0x1800b0a7e  xorps   xmm0, xmm0
0x1800b0a81  movdqu  xmmword ptr [rbp+70h+var_90], xmm0
0x1800b0a86  mov     rax, [rbp+70h+var_E0]
0x1800b0a8a  cmp     [rax], r13
0x1800b0a8d  jz      short loc_1800B0ABD
0x1800b0a8f  mov     rdx, rax
0x1800b0a92  lea     rcx, [rbp+70h+var_E0]
0x1800b0a96  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800b0a9b  lea     rcx, [rbp+70h+var_90]
0x1800b0a9f  mov     [rsp+170h+var_150], rcx
0x1800b0aa4  mov     r9, r12
0x1800b0aa7  mov     r8, r14
0x1800b0aaa  mov     rdx, rax
0x1800b0aad  mov     rcx, rbx
0x1800b0ab0  call    ?ProcessOpacityMaskBrush@xpsrdr@@YA_NAEAURenderState@1@V?$shared_ptr@UIXpsOMBrush@@@std@@AEAUD2D_RECT_F@@AEAV?$shared_ptr@UID2D1Geometry@@@4@AEAV?$shared_ptr@UID2D1Brush@@@4@@Z; xpsrdr::ProcessOpacityMaskBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush>,D2D_RECT_F &,std::shared_ptr<ID2D1Geometry> &,std::shared_ptr<ID2D1Brush> &)
0x1800b0ab5  test    al, al
0x1800b0ab7  jz      loc_1800B0E09
0x1800b0abd  movss   xmm0, [rbp+70h+arg_38]
0x1800b0ac5  movss   xmm6, cs:__real@3f800000
0x1800b0acd  cmp     [r12], r13
0x1800b0ad1  jnz     short loc_1800B0ADE
0x1800b0ad3  cmp     [rbp+70h+var_90], r13
0x1800b0ad7  jnz     short loc_1800B0ADE
0x1800b0ad9  comiss  xmm6, xmm0
0x1800b0adc  jbe     short loc_1800B0B0C
0x1800b0ade  lea     rax, [rbp+70h+var_90]
0x1800b0ae2  mov     [rsp+30h], rax
0x1800b0ae7  movss   dword ptr [rsp+170h+var_148], xmm0
0x1800b0aed  mov     [rsp+170h+var_150], r12
0x1800b0af2  mov     r9, r14
0x1800b0af5  mov     r8d, [rbx+58h]
0x1800b0af9  mov     rdx, rsi
0x1800b0afc  mov     rcx, rbx
0x1800b0aff  call    ?CreateAndPushLayer@xpsrdr@@YA?AW4LAYER_CLIP_USE@1@AEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@W4D2D1_ANTIALIAS_MODE@@AEBUD2D_RECT_F@@AEBV?$shared_ptr@UID2D1Geometry@@@5@MAEBV?$shared_ptr@UID2D1Brush@@@5@@Z; xpsrdr::CreateAndPushLayer(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D1_ANTIALIAS_MODE,D2D_RECT_F const &,std::shared_ptr<ID2D1Geometry> const &,float,std::shared_ptr<ID2D1Brush> const &)
0x1800b0b04  mov     rcx, [rsp+170h+var_120+8]
0x1800b0b09  mov     [rcx+30h], al
0x1800b0b0c  xorps   xmm0, xmm0
0x1800b0b0f  movdqu  xmmword ptr [rbp+70h+var_B0], xmm0
0x1800b0b14  mov     dword ptr [rsp+170h+var_130], r13d
0x1800b0b19  mov     rcx, [rsp+170h+var_130+8]
0x1800b0b1e  mov     rax, [rcx]
0x1800b0b21  mov     [rsp+170h+var_120+8], r13
0x1800b0b26  lea     rdx, [rsp+170h+var_130]
0x1800b0b2b  mov     [rsp+170h+var_110], rdx
0x1800b0b30  lea     rdx, [rbp+70h+var_B0]
0x1800b0b34  mov     qword ptr [rsp+170h+var_108], rdx
0x1800b0b39  lea     rdx, [rsp+170h+var_120+8]
0x1800b0b3e  mov     rax, [rax+1E8h]
0x1800b0b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b4a  mov     r12d, eax
0x1800b0b4d  lea     rcx, [rsp+170h+var_120+8]
0x1800b0b52  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b0b57  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800b0b5b  test    ecx, ecx
0x1800b0b5d  jns     short loc_1800B0B65
0x1800b0b5f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b0b65  test    r12d, r12d
0x1800b0b68  jns     short loc_1800B0B73
0x1800b0b6a  mov     ecx, r12d; this
0x1800b0b6d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b0b73  mov     r12b, 3
0x1800b0b76  cmp     [rbp+70h+var_B0], r13
0x1800b0b7a  jz      loc_1800B0CDD
0x1800b0b80  lea     rcx, [rbp+70h+var_78]; this
0x1800b0b84  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x1800b0b89  test    al, al
0x1800b0b8b  jnz     loc_1800B0CDD
0x1800b0b91  mov     rax, [rbx+220h]
0x1800b0b98  inc     dword ptr [rax+60h]
0x1800b0b9b  mov     dword ptr [rsp+170h+var_130], r13d
0x1800b0ba0  mov     rcx, [rbp+70h+var_B0]
0x1800b0ba4  mov     rax, [rcx]
0x1800b0ba7  lea     rdx, [rsp+170h+var_130]
0x1800b0bac  mov     rax, [rax+20h]
0x1800b0bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0bb5  test    eax, eax
0x1800b0bb7  jns     short loc_1800B0BC1
0x1800b0bb9  mov     ecx, eax; this
0x1800b0bbb  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b0bc1  cmp     dword ptr [rsp+170h+var_130], 0Ah
0x1800b0bc6  jnz     short loc_1800B0C0F
0x1800b0bc8  mov     rax, [rbx+220h]
0x1800b0bcf  inc     dword ptr [rax+38h]
0x1800b0bd2  lea     r8, [rbx+21Ch]; int *
0x1800b0bd9  lea     rcx, [rsp+170h+var_120+8]; this
0x1800b0bde  call    ??0DepthGuard@xpsrdr@@QEAA@HAEAH@Z; xpsrdr::DepthGuard::DepthGuard(int,int &)
0x1800b0be3  nop
0x1800b0be4  lea     rax, [rbp+70h+var_F0]
0x1800b0be8  mov     [rsp+170h+var_150], rax
0x1800b0bed  lea     r9, [rbp+70h+var_B0]
  ... truncated ...
```
