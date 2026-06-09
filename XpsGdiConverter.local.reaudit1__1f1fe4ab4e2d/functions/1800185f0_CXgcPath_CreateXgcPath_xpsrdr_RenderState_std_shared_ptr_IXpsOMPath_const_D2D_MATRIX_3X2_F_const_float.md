# CXgcPath::CreateXgcPath(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &,D2D_MATRIX_3X2_F const &,float)

- ea: `0x1800185f0`
- end: `0x180018a25`
- name: `?CreateXgcPath@CXgcPath@@SA?AV?$shared_ptr@VCXgcPath@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMPath@@@3@AEBUD2D_MATRIX_3X2_F@@M@Z`
- size: `1077`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800109e0`

## callees

- `0x180008830`
- `0x180008854`
- `0x18000d6f8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e934`
- `0x18000e990`
- `0x180011b0c`
- `0x180012088`
- `0x1800122fc`
- `0x1800123bc`
- `0x180018414`
- `0x1800185f0`
- `0x180018f78`
- `0x18002a684`
- `0x18002b9f4`
- `0x180034cac`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_OWORD *__fastcall CXgcPath::CreateXgcPath(_OWORD *a1, __int64 a2, __int64 **a3, int a4)
{
  void *v8; // rax
  __int64 v9; // rax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // esi
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 v16; // rax
  __int64 v17; // rsi
  _QWORD *v18; // r15
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v21; // r14d
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  __int64 v25; // rax
  __int64 v26; // rax
  const struct D2D_RECT_F *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // r14d
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  char v34; // al
  __int64 XgcBrush; // rax
  char v36; // al
  __int64 v37; // rax
  __m128 v39; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v40; // [rsp+48h] [rbp-91h] BYREF
  __m128 *v41; // [rsp+50h] [rbp-89h]
  _BYTE *v42; // [rsp+58h] [rbp-81h]
  _BYTE v43[16]; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v44[16]; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v45[16]; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v46[2]; // [rsp+90h] [rbp-49h] BYREF
  _QWORD v47[3]; // [rsp+A0h] [rbp-39h] BYREF
  struct D2D_RECT_F v48; // [rsp+B8h] [rbp-21h] BYREF

  v47[0] = a3;
  v8 = operator new(0xF0u);
  v39.m128_i32[1] = HIDWORD(v8);
  v9 = CXgcPath::CXgcPath(v8, a3);
  std::shared_ptr<CXgcCanvas>::shared_ptr<CXgcCanvas>(v46, v9);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v44);
  v39.m128_i32[0] = 0;
  v10 = *a3;
  v11 = **a3;
  v40 = 0;
  v41 = &v39;
  v42 = v44;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 240))(v10, &v40);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v40);
  if ( v39.m128_i32[0] < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)v39.m128_u32[0], v13, v14, v15);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v44) )
  {
    v16 = CXgcGeometry::CreateXgcGeometry(&v39, a2, v44);
    v17 = v46[0];
    v18 = (_QWORD *)(v46[0] + 216LL);
    std::shared_ptr<_devicemodeW>::operator=(v46[0] + 216LL, v16);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v39);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v43);
    v39.m128_i32[0] = 0;
    v19 = *a3;
    v20 = **a3;
    v40 = 0;
    v41 = &v39;
    v42 = v43;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v20 + 328))(v19, &v40);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v40);
    if ( v39.m128_i32[0] < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v39.m128_u32[0], v22, v23, v24);
    if ( v21 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, v22, v23, v24);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v43) )
    {
      v25 = CXgcPenStyle::CreateXgcPenStyle(&v40, a2, a3);
      v26 = std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(&v39, v25);
      std::shared_ptr<XgcSolidPath>::swap(v26, v17 + 200);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v39);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v40);
    }
    v48 = 0;
    CXgcGeometry::GetBounds(*v18, a2, a4, v17 + 200, &v48);
    if ( xpsrdr::RectEmpty((xpsrdr *)&v48, v27) )
    {
      *a1 = 0;
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
    }
    else
    {
      v39.m128_u64[0] = __PAIR64__(
                          COERCE_UNSIGNED_INT(fmaxf(v48.top, -3.4028235e38)),
                          COERCE_UNSIGNED_INT(fmaxf(v48.left, -3.4028235e38)));
      v39.m128_u64[1] = __PAIR64__(
                          COERCE_UNSIGNED_INT(fminf(v48.bottom, 3.4028235e38)),
                          COERCE_UNSIGNED_INT(fminf(v48.right, 3.4028235e38)));
      LODWORD(v48.left) = v39.m128_i32[0];
      LODWORD(v48.top) = _mm_shuffle_ps(v39, v39, 85).m128_u32[0];
      LODWORD(v48.right) = _mm_shuffle_ps(v39, v39, 170).m128_u32[0];
      LODWORD(v48.bottom) = _mm_shuffle_ps(v39, v39, 255).m128_u32[0];
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v45);
      v39.m128_i32[0] = 0;
      v28 = *(_QWORD *)v47[0];
      v29 = **(_QWORD **)v47[0];
      v40 = 0;
      v41 = &v39;
      v42 = v45;
      v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v29 + 488))(v28, &v40);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v40);
      if ( v39.m128_i32[0] < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)v39.m128_u32[0], v31, v32, v33);
      if ( v30 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v31, v32, v33);
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(v45) )
      {
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v47);
        v34 = IsViewPortFull(a2);
        XgcBrush = CXgcBrush::CreateXgcBrush((unsigned int)&v40, a2, (unsigned int)v45, a4, (__int64)&v48, v34);
        std::shared_ptr<_devicemodeW>::operator=(v17 + 168, XgcBrush);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v40);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v47);
      }
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(v43) )
      {
        v36 = IsViewPortFull(a2);
        v37 = CXgcBrush::CreateXgcBrush((unsigned int)&v40, a2, (unsigned int)v43, a4, (__int64)&v48, v36);
        std::shared_ptr<_devicemodeW>::operator=(v17 + 184, v37);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v40);
      }
      std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v46);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v45);
    }
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v43);
  }
  else
  {
    *a1 = 0;
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v44);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v46);
  return a1;
}

```

## disassembly

```asm
0x1800185f0  mov     rax, rsp
0x1800185f3  push    rbp
0x1800185f4  push    rbx
0x1800185f5  push    rsi
0x1800185f6  push    rdi
0x1800185f7  push    r12
0x1800185f9  push    r13
0x1800185fb  push    r14
0x1800185fd  push    r15
0x1800185ff  lea     rbp, [rax-57h]
0x180018603  sub     rsp, 0E8h
0x18001860a  movaps  xmmword ptr [rax-58h], xmm6
0x18001860e  mov     rax, cs:__security_cookie
0x180018615  xor     rax, rsp
0x180018618  mov     [rbp+4Fh+var_60], rax
0x18001861c  mov     r13, r9
0x18001861f  mov     r12, r8
0x180018622  mov     [rbp+4Fh+var_88], r8
0x180018626  mov     rdi, rdx
0x180018629  mov     rbx, rcx
0x18001862c  mov     [rsp+120h+var_F8+8], rcx
0x180018631  movss   xmm6, [rbp+4Fh+arg_20]
0x180018636  xor     r14d, r14d
0x180018639  mov     ecx, 0F0h; Size
0x18001863e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018643  mov     [rsp+120h+var_F8+8], rax
0x180018648  movaps  xmm2, xmm6
0x18001864b  mov     rdx, r12
0x18001864e  mov     rcx, rax
0x180018651  call    ??0CXgcPath@@QEAA@AEBV?$shared_ptr@UIXpsOMPath@@@std@@M@Z; CXgcPath::CXgcPath(std::shared_ptr<IXpsOMPath> const &,float)
0x180018656  mov     rdx, rax
0x180018659  lea     rcx, [rbp+4Fh+var_98]
0x18001865d  call    ??$?0VCXgcCanvas@@$0A@@?$shared_ptr@VCXgcCanvas@@@std@@QEAA@PEAVCXgcCanvas@@@Z; std::shared_ptr<CXgcCanvas>::shared_ptr<CXgcCanvas>(CXgcCanvas *)
0x180018662  nop
0x180018663  lea     rcx, [rbp+4Fh+var_B8]
0x180018667  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18001866c  nop
0x18001866d  mov     dword ptr [rsp+120h+var_F8+8], r14d
0x180018672  mov     rcx, [r12]
0x180018676  mov     rax, [rcx]
0x180018679  mov     [rsp+120h+var_E0], r14
0x18001867e  lea     rdx, [rsp+120h+var_F8+8]
0x180018683  mov     [rsp+120h+var_D8], rdx
0x180018688  lea     rdx, [rbp+4Fh+var_B8]
0x18001868c  mov     [rsp+120h+var_D0], rdx
0x180018691  lea     rdx, [rsp+120h+var_E0]
0x180018696  mov     rax, [rax+0F0h]
0x18001869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a2  mov     esi, eax
0x1800186a4  lea     rcx, [rsp+120h+var_E0]
0x1800186a9  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800186ae  mov     ecx, dword ptr [rsp+120h+var_F8+8]; this
0x1800186b2  test    ecx, ecx
0x1800186b4  jns     short loc_1800186BC
0x1800186b6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800186bc  test    esi, esi
0x1800186be  jns     short loc_1800186C8
0x1800186c0  mov     ecx, esi; this
0x1800186c2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800186c8  lea     rcx, [rbp+4Fh+var_B8]
0x1800186cc  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800186d1  test    al, al
0x1800186d3  jnz     short loc_1800186E8
0x1800186d5  xorps   xmm0, xmm0
0x1800186d8  movups  xmmword ptr [rbx], xmm0
0x1800186db  mov     rcx, rbx
0x1800186de  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800186e3  jmp     loc_1800189E7
0x1800186e8  lea     r8, [rbp+4Fh+var_B8]
0x1800186ec  mov     rdx, rdi
0x1800186ef  lea     rcx, [rsp+120h+var_F8+8]
0x1800186f4  call    ?CreateXgcGeometry@CXgcGeometry@@SA?AV?$shared_ptr@VCXgcGeometry@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMGeometry@@@3@@Z; CXgcGeometry::CreateXgcGeometry(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGeometry> const &)
0x1800186f9  mov     rsi, [rbp+4Fh+var_98]
0x1800186fd  lea     r15, [rsi+0D8h]
0x180018704  mov     rdx, rax
0x180018707  mov     rcx, r15
0x18001870a  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x18001870f  lea     rcx, [rsp+120h+var_F8+8]
0x180018714  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180018719  lea     rcx, [rbp+4Fh+var_C8]
0x18001871d  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180018722  nop
0x180018723  mov     dword ptr [rsp+120h+var_F8+8], r14d
0x180018728  mov     rcx, [r12]
0x18001872c  mov     rax, [rcx]
0x18001872f  mov     [rsp+120h+var_E0], r14
0x180018734  lea     rdx, [rsp+120h+var_F8+8]
0x180018739  mov     [rsp+120h+var_D8], rdx
0x18001873e  lea     rdx, [rbp+4Fh+var_C8]
0x180018742  mov     [rsp+120h+var_D0], rdx
0x180018747  lea     rdx, [rsp+120h+var_E0]
0x18001874c  mov     rax, [rax+148h]
0x180018753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018758  mov     r14d, eax
0x18001875b  lea     rcx, [rsp+120h+var_E0]
0x180018760  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180018765  mov     ecx, dword ptr [rsp+120h+var_F8+8]; this
0x180018769  test    ecx, ecx
0x18001876b  jns     short loc_180018773
0x18001876d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180018773  test    r14d, r14d
0x180018776  jns     short loc_180018781
0x180018778  mov     ecx, r14d; this
0x18001877b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180018781  lea     rcx, [rbp+4Fh+var_C8]
0x180018785  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18001878a  test    al, al
0x18001878c  jz      short loc_1800187CE
0x18001878e  mov     r8, r12
0x180018791  mov     rdx, rdi
0x180018794  lea     rcx, [rsp+120h+var_E0]
0x180018799  call    ?CreateXgcPenStyle@CXgcPenStyle@@SA?AV?$shared_ptr@VCXgcPenStyle@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMPath@@@3@@Z; CXgcPenStyle::CreateXgcPenStyle(xpsrdr::RenderState &,std::shared_ptr<IXpsOMPath> const &)
0x18001879e  mov     rdx, rax
0x1800187a1  lea     rcx, [rsp+120h+var_F8+8]
0x1800187a6  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x1800187ab  lea     rdx, [rsi+0C8h]
0x1800187b2  mov     rcx, rax
0x1800187b5  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x1800187ba  lea     rcx, [rsp+120h+var_F8+8]
0x1800187bf  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800187c4  lea     rcx, [rsp+120h+var_E0]
0x1800187c9  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800187ce  xorps   xmm0, xmm0
0x1800187d1  movups  xmmword ptr [rbp+4Fh+var_70.left], xmm0
0x1800187d5  lea     r12, [rsi+0C8h]
0x1800187dc  lea     rax, [rbp+4Fh+var_70]
0x1800187e0  mov     [rsp+120h+var_100], rax; struct D2D_RECT_F *
0x1800187e5  mov     r9, r12; int
0x1800187e8  mov     r8, r13; int
0x1800187eb  mov     rdx, rdi; int
0x1800187ee  mov     rcx, [r15]; int
0x1800187f1  call    ?GetBounds@CXgcGeometry@@QEAAXAEAURenderState@xpsrdr@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@VCXgcPenStyle@@@std@@AEAUD2D_RECT_F@@@Z; CXgcGeometry::GetBounds(xpsrdr::RenderState &,D2D_MATRIX_3X2_F const &,std::shared_ptr<CXgcPenStyle> const &,D2D_RECT_F &)
0x1800187f6  lea     rcx, [rbp+4Fh+var_70]; this
0x1800187fa  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x1800187ff  test    al, al
0x180018801  jz      short loc_180018816
0x180018803  xorps   xmm0, xmm0
0x180018806  movups  xmmword ptr [rbx], xmm0
0x180018809  mov     rcx, rbx
0x18001880c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180018811  jmp     loc_1800189DD
0x180018816  movss   xmm0, [rbp+4Fh+var_70.left]
0x18001881b  maxss   xmm0, cs:__real@ff7fffff
0x180018823  movss   dword ptr [rsp+120h+var_F8+8], xmm0
0x180018829  movss   xmm0, [rbp+4Fh+var_70.top]
0x18001882e  maxss   xmm0, cs:__real@ff7fffff
0x180018836  movss   dword ptr [rsp+120h+var_F8+0Ch], xmm0
0x18001883c  movss   xmm1, [rbp+4Fh+var_70.right]
0x180018841  minss   xmm1, cs:__real@7f7fffff
0x180018849  movss   dword ptr [rsp+120h+var_E8], xmm1
0x18001884f  movss   xmm0, [rbp+4Fh+var_70.bottom]
0x180018854  minss   xmm0, cs:__real@7f7fffff
0x18001885c  movss   dword ptr [rsp+120h+var_E8+4], xmm0
0x180018862  movups  xmm3, xmmword ptr [rsp+120h+var_F8+8]
0x180018867  movss   [rbp+4Fh+var_70.left], xmm3
0x18001886c  movaps  xmm0, xmm3
0x18001886f  shufps  xmm0, xmm3, 55h ; 'U'
0x180018873  movss   [rbp+4Fh+var_70.top], xmm0
0x180018878  movaps  xmm1, xmm3
0x18001887b  shufps  xmm1, xmm3, 0AAh
0x18001887f  movss   [rbp+4Fh+var_70.right], xmm1
0x180018884  shufps  xmm3, xmm3, 0FFh
0x180018888  movss   [rbp+4Fh+var_70.bottom], xmm3
0x18001888d  lea     rcx, [rbp+4Fh+var_A8]
0x180018891  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180018896  nop
0x180018897  mov     dword ptr [rsp+120h+var_F8+8], 0
0x18001889f  mov     rcx, [rbp+4Fh+var_88]
0x1800188a3  mov     rcx, [rcx]
0x1800188a6  mov     rax, [rcx]
0x1800188a9  mov     [rsp+120h+var_E0], 0
0x1800188b2  lea     rdx, [rsp+120h+var_F8+8]
0x1800188b7  mov     [rsp+120h+var_D8], rdx
0x1800188bc  lea     rdx, [rbp+4Fh+var_A8]
0x1800188c0  mov     [rsp+120h+var_D0], rdx
0x1800188c5  lea     rdx, [rsp+120h+var_E0]
0x1800188ca  mov     rax, [rax+1E8h]
0x1800188d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188d6  mov     r14d, eax
0x1800188d9  lea     rcx, [rsp+120h+var_E0]
0x1800188de  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800188e3  mov     ecx, dword ptr [rsp+120h+var_F8+8]; this
0x1800188e7  test    ecx, ecx
0x1800188e9  jns     short loc_1800188F1
0x1800188eb  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800188f1  test    r14d, r14d
0x1800188f4  jns     short loc_1800188FF
0x1800188f6  mov     ecx, r14d; this
0x1800188f9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800188ff  lea     rcx, [rbp+4Fh+var_A8]
0x180018903  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180018908  test    al, al
0x18001890a  jz      short loc_18001896D
0x18001890c  lea     rcx, [rbp+4Fh+var_88]
0x180018910  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180018915  nop
0x180018916  lea     r9, [rbp+4Fh+var_A8]
0x18001891a  lea     r8, [rbp+4Fh+var_88]
0x18001891e  mov     rdx, r15
0x180018921  mov     rcx, rdi; int
0x180018924  call    ?IsViewPortFull@@YA_NAEAURenderState@xpsrdr@@AEBV?$shared_ptr@VCXgcGeometry@@@std@@AEBV?$shared_ptr@VCXgcPenStyle@@@4@AEBV?$shared_ptr@UIXpsOMBrush@@@4@@Z; IsViewPortFull(xpsrdr::RenderState &,std::shared_ptr<CXgcGeometry> const &,std::shared_ptr<CXgcPenStyle> const &,std::shared_ptr<IXpsOMBrush> const &)
0x180018929  mov     byte ptr [rsp+120h+var_F8], al
0x18001892d  lea     rax, [rbp+4Fh+var_70]
0x180018931  mov     [rsp+120h+var_100], rax
0x180018936  mov     r9, r13
0x180018939  lea     r8, [rbp+4Fh+var_A8]
0x18001893d  mov     rdx, rdi
0x180018940  lea     rcx, [rsp+120h+var_E0]
0x180018945  call    ?CreateXgcBrush@CXgcBrush@@SA?AV?$shared_ptr@VCXgcBrush@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@_N@Z; CXgcBrush::CreateXgcBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &,bool)
0x18001894a  lea     rcx, [rsi+0A8h]
0x180018951  mov     rdx, rax
0x180018954  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x180018959  lea     rcx, [rsp+120h+var_E0]
0x18001895e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180018963  nop
0x180018964  lea     rcx, [rbp+4Fh+var_88]
0x180018968  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001896d  lea     rcx, [rbp+4Fh+var_C8]
0x180018971  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180018976  test    al, al
0x180018978  jz      short loc_1800189C6
0x18001897a  lea     r9, [rbp+4Fh+var_C8]
0x18001897e  mov     r8, r12
0x180018981  mov     rdx, r15
0x180018984  mov     rcx, rdi; int
0x180018987  call    ?IsViewPortFull@@YA_NAEAURenderState@xpsrdr@@AEBV?$shared_ptr@VCXgcGeometry@@@std@@AEBV?$shared_ptr@VCXgcPenStyle@@@4@AEBV?$shared_ptr@UIXpsOMBrush@@@4@@Z; IsViewPortFull(xpsrdr::RenderState &,std::shared_ptr<CXgcGeometry> const &,std::shared_ptr<CXgcPenStyle> const &,std::shared_ptr<IXpsOMBrush> const &)
0x18001898c  mov     byte ptr [rsp+120h+var_F8], al
0x180018990  lea     rax, [rbp+4Fh+var_70]
0x180018994  mov     [rsp+120h+var_100], rax
0x180018999  mov     r9, r13
0x18001899c  lea     r8, [rbp+4Fh+var_C8]
0x1800189a0  mov     rdx, rdi
0x1800189a3  lea     rcx, [rsp+120h+var_E0]
0x1800189a8  call    ?CreateXgcBrush@CXgcBrush@@SA?AV?$shared_ptr@VCXgcBrush@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@_N@Z; CXgcBrush::CreateXgcBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &,bool)
0x1800189ad  lea     rcx, [rsi+0B8h]
0x1800189b4  mov     rdx, rax
0x1800189b7  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x1800189bc  lea     rcx, [rsp+120h+var_E0]
0x1800189c1  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800189c6  lea     rdx, [rbp+4Fh+var_98]
0x1800189ca  mov     rcx, rbx
0x1800189cd  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x1800189d2  nop
0x1800189d3  lea     rcx, [rbp+4Fh+var_A8]
0x1800189d7  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800189dc  nop
0x1800189dd  lea     rcx, [rbp+4Fh+var_C8]
0x1800189e1  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800189e6  nop
0x1800189e7  lea     rcx, [rbp+4Fh+var_B8]
0x1800189eb  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800189f0  nop
0x1800189f1  lea     rcx, [rbp+4Fh+var_98]
0x1800189f5  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800189fa  mov     rax, rbx
0x1800189fd  mov     rcx, [rbp+4Fh+var_60]
0x180018a01  xor     rcx, rsp; StackCookie
0x180018a04  call    __security_check_cookie
0x180018a09  movaps  xmm6, [rsp+120h+var_58+8]
0x180018a11  add     rsp, 0E8h
0x180018a18  pop     r15
0x180018a1a  pop     r14
0x180018a1c  pop     r13
0x180018a1e  pop     r12
0x180018a20  pop     rdi
0x180018a21  pop     rsi
0x180018a22  pop     rbx
0x180018a23  pop     rbp
0x180018a24  retn
```
