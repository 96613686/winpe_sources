# CXgcGlyphs::CreateXgcGlyphs(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &,D2D_MATRIX_3X2_F const &,float)

- ea: `0x180019c1c`
- end: `0x180019e8c`
- name: `?CreateXgcGlyphs@CXgcGlyphs@@SA?AV?$shared_ptr@VCXgcGlyphs@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@AEBUD2D_MATRIX_3X2_F@@M@Z`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800109e0`

## callees

- `0x180008854`
- `0x18000d6f8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e934`
- `0x18000e990`
- `0x180011b0c`
- `0x180019a94`
- `0x180019c1c`
- `0x18002a684`
- `0x18003426c`
- `0x180034cac`
- `0x180037278`
- `0x18003dcd4`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
xpsrdr *__fastcall CXgcGlyphs::CreateXgcGlyphs(xpsrdr *a1, __int64 a2, __int64 **a3, struct D2D_RECT_F *a4, float a5)
{
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // esi
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  int v15; // eax
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  const struct D2D_RECT_F *v19; // rdx
  __int64 XgcBrush; // rax
  __int64 v21; // rax
  xpsrdr *v23; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v24[32]; // [rsp+40h] [rbp-59h] BYREF
  int v25[4]; // [rsp+60h] [rbp-39h] BYREF
  int v26[2]; // [rsp+70h] [rbp-29h] BYREF
  xpsrdr **v27; // [rsp+78h] [rbp-21h]
  __int64 (__fastcall ****v28)(__int64, GUID *, __int64 *); // [rsp+80h] [rbp-19h]
  __int64 (__fastcall ***v29[3])(__int64, GUID *, __int64 *); // [rsp+88h] [rbp-11h] BYREF

  v23 = a1;
  xpsrdr::CreateGlyphRun((_QWORD **)v25, a2, a3);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v25) )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v29);
    LODWORD(v23) = 0;
    v9 = *a3;
    v10 = **a3;
    *(_QWORD *)v26 = 0;
    v27 = &v23;
    v28 = v29;
    v11 = (*(__int64 (__fastcall **)(__int64 *, int *))(v10 + 400))(v9, v26);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v26);
    if ( (int)v23 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v12, v13, v14);
    if ( v11 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v26);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v29) )
    {
      v23 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64 *, xpsrdr **))(**a3 + 336))(*a3, &v23);
      if ( v15 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
      *(_OWORD *)v24 = 0;
      xpsrdr::GetGlyphRunBounds(a2, (int)v25, (int)a3, (int)&v23, a4, (struct D2D_MATRIX_3X2_F *)v24);
      if ( xpsrdr::RectEmpty((xpsrdr *)v24, v19) )
      {
        *(_OWORD *)a1 = 0;
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
LABEL_14:
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v26);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v29);
        goto LABEL_15;
      }
      *(_QWORD *)&v24[16] = __PAIR64__(
                              COERCE_UNSIGNED_INT(fmaxf(*(float *)&v24[4], -3.4028235e38)),
                              COERCE_UNSIGNED_INT(fmaxf(*(float *)v24, -3.4028235e38)));
      *(_QWORD *)&v24[24] = __PAIR64__(
                              COERCE_UNSIGNED_INT(fminf(*(float *)&v24[12], 3.4028235e38)),
                              COERCE_UNSIGNED_INT(fminf(*(float *)&v24[8], 3.4028235e38)));
      *(_DWORD *)v24 = *(_DWORD *)&v24[16];
      *(_DWORD *)&v24[4] = _mm_shuffle_ps(*(__m128 *)&v24[16], *(__m128 *)&v24[16], 85).m128_u32[0];
      *(_DWORD *)&v24[8] = _mm_shuffle_ps(*(__m128 *)&v24[16], *(__m128 *)&v24[16], 170).m128_u32[0];
      *(_DWORD *)&v24[12] = _mm_shuffle_ps(*(__m128 *)&v24[16], *(__m128 *)&v24[16], 255).m128_u32[0];
      XgcBrush = CXgcBrush::CreateXgcBrush((__int64)&v24[16], a2, v29, (__int64)a4, (float *)v24, 0);
      std::shared_ptr<_devicemodeW>::operator=(v26, XgcBrush);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v24[16]);
    }
    v23 = (xpsrdr *)operator new(0xC8u);
    v21 = CXgcGlyphs::CXgcGlyphs((int)v23, (int)a3, (int)v25, (int)v26, a5);
    std::shared_ptr<CXgcCanvas>::shared_ptr<CXgcCanvas>(&v24[16], v21);
    std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, &v24[16]);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v24[16]);
    goto LABEL_14;
  }
  *(_OWORD *)a1 = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a1);
LABEL_15:
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v25);
  return a1;
}

```

## disassembly

```asm
0x180019c1c  mov     rax, rsp
0x180019c1f  push    rbp
0x180019c20  push    rbx
0x180019c21  push    rsi
0x180019c22  push    rdi
0x180019c23  push    r14
0x180019c25  push    r15
0x180019c27  lea     rbp, [rax-57h]
0x180019c2b  sub     rsp, 0B8h
0x180019c32  movaps  xmmword ptr [rax-48h], xmm6
0x180019c36  mov     r15, r9
0x180019c39  mov     rdi, r8
0x180019c3c  mov     r14, rdx
0x180019c3f  mov     rbx, rcx
0x180019c42  mov     [rbp+4Fh+var_B0], rcx
0x180019c46  movss   xmm6, [rbp+4Fh+arg_20]
0x180019c4b  lea     rcx, [rbp+4Fh+var_88]
0x180019c4f  call    ?CreateGlyphRun@xpsrdr@@YA?AV?$shared_ptr@UGlyphRun@xpsrdr@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z; xpsrdr::CreateGlyphRun(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)
0x180019c54  nop
0x180019c55  lea     rcx, [rbp+4Fh+var_88]
0x180019c59  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019c5e  test    al, al
0x180019c60  jnz     short loc_180019C75
0x180019c62  xorps   xmm0, xmm0
0x180019c65  movups  xmmword ptr [rbx], xmm0
0x180019c68  mov     rcx, rbx
0x180019c6b  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019c70  jmp     loc_180019E68
0x180019c75  lea     rcx, [rbp+4Fh+var_60]
0x180019c79  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019c7e  nop
0x180019c7f  mov     dword ptr [rbp+4Fh+var_B0], 0
0x180019c86  mov     rcx, [rdi]
0x180019c89  mov     rax, [rcx]
0x180019c8c  mov     qword ptr [rbp+4Fh+var_78], 0
0x180019c94  lea     rdx, [rbp+4Fh+var_B0]
0x180019c98  mov     [rbp+4Fh+var_70], rdx
0x180019c9c  lea     rdx, [rbp+4Fh+var_60]
0x180019ca0  mov     [rbp+4Fh+var_68], rdx
0x180019ca4  lea     rdx, [rbp+4Fh+var_78]
0x180019ca8  mov     rax, [rax+190h]
0x180019caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cb4  mov     esi, eax
0x180019cb6  lea     rcx, [rbp+4Fh+var_78]
0x180019cba  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180019cbf  mov     ecx, dword ptr [rbp+4Fh+var_B0]; this
0x180019cc2  test    ecx, ecx
0x180019cc4  jns     short loc_180019CCC
0x180019cc6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180019ccc  test    esi, esi
0x180019cce  jns     short loc_180019CD8
0x180019cd0  mov     ecx, esi; this
0x180019cd2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180019cd8  lea     rcx, [rbp+4Fh+var_78]
0x180019cdc  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019ce1  nop
0x180019ce2  lea     rcx, [rbp+4Fh+var_60]
0x180019ce6  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019ceb  test    al, al
0x180019ced  jz      loc_180019E0B
0x180019cf3  xor     eax, eax
0x180019cf5  mov     [rbp+4Fh+var_B0], rax
0x180019cf9  mov     rcx, [rdi]
0x180019cfc  mov     rax, [rcx]
0x180019cff  lea     rdx, [rbp+4Fh+var_B0]
0x180019d03  mov     rax, [rax+150h]
0x180019d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d0f  test    eax, eax
0x180019d11  jns     short loc_180019D1B
0x180019d13  mov     ecx, eax; this
0x180019d15  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180019d1b  xorps   xmm0, xmm0
0x180019d1e  movups  xmmword ptr [rbp+4Fh+var_A8], xmm0
0x180019d22  lea     rax, [rbp+4Fh+var_A8]
0x180019d26  mov     [rsp+28h], rax; struct D2D_MATRIX_3X2_F *
0x180019d2b  mov     [rsp+0E0h+var_C0], r15; struct D2D_RECT_F *
0x180019d30  lea     r9, [rbp+4Fh+var_B0]; int
0x180019d34  mov     r8, rdi; int
0x180019d37  lea     rdx, [rbp+4Fh+var_88]; int
0x180019d3b  mov     rcx, r14; int
0x180019d3e  call    ?GetGlyphRunBounds@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UGlyphRun@xpsrdr@@@std@@AEBV?$shared_ptr@UIXpsOMGlyphs@@@4@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0017@@AEBUD2D_MATRIX_3X2_F@@AEAUD2D_RECT_F@@@Z; xpsrdr::GetGlyphRunBounds(xpsrdr::RenderState &,std::shared_ptr<xpsrdr::GlyphRun> const &,std::shared_ptr<IXpsOMGlyphs> const &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0017 const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F &)
0x180019d43  lea     rcx, [rbp+4Fh+var_A8]; this
0x180019d47  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x180019d4c  test    al, al
0x180019d4e  jz      short loc_180019D63
0x180019d50  xorps   xmm0, xmm0
0x180019d53  movups  xmmword ptr [rbx], xmm0
0x180019d56  mov     rcx, rbx
0x180019d59  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019d5e  jmp     loc_180019E54
0x180019d63  movss   xmm0, dword ptr [rbp+4Fh+var_A8]
0x180019d68  maxss   xmm0, cs:__real@ff7fffff
0x180019d70  movss   dword ptr [rbp+4Fh+var_A8+10h], xmm0
0x180019d75  movss   xmm0, dword ptr [rbp+4Fh+var_A8+4]
0x180019d7a  maxss   xmm0, cs:__real@ff7fffff
0x180019d82  movss   dword ptr [rbp+4Fh+var_A8+14h], xmm0
0x180019d87  movss   xmm1, dword ptr [rbp+4Fh+var_A8+8]
0x180019d8c  minss   xmm1, cs:__real@7f7fffff
0x180019d94  movss   dword ptr [rbp+4Fh+var_A8+18h], xmm1
0x180019d99  movss   xmm0, dword ptr [rbp+4Fh+var_A8+0Ch]
0x180019d9e  minss   xmm0, cs:__real@7f7fffff
0x180019da6  movss   dword ptr [rbp+4Fh+var_A8+1Ch], xmm0
0x180019dab  movups  xmm3, xmmword ptr [rbp+4Fh+var_A8+10h]
0x180019daf  movss   dword ptr [rbp+4Fh+var_A8], xmm3
0x180019db4  movaps  xmm0, xmm3
0x180019db7  shufps  xmm0, xmm3, 55h ; 'U'
0x180019dbb  movss   dword ptr [rbp+4Fh+var_A8+4], xmm0
0x180019dc0  movaps  xmm1, xmm3
0x180019dc3  shufps  xmm1, xmm3, 0AAh
0x180019dc7  movss   dword ptr [rbp+4Fh+var_A8+8], xmm1
0x180019dcc  shufps  xmm3, xmm3, 0FFh
0x180019dd0  movss   dword ptr [rbp+4Fh+var_A8+0Ch], xmm3
0x180019dd5  mov     byte ptr [rsp+28h], 0
0x180019dda  lea     rax, [rbp+4Fh+var_A8]
0x180019dde  mov     [rsp+0E0h+var_C0], rax
0x180019de3  mov     r9, r15
0x180019de6  lea     r8, [rbp+4Fh+var_60]
0x180019dea  mov     rdx, r14
0x180019ded  lea     rcx, [rbp+4Fh+var_A8+10h]
0x180019df1  call    ?CreateXgcBrush@CXgcBrush@@SA?AV?$shared_ptr@VCXgcBrush@@@std@@AEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@_N@Z; CXgcBrush::CreateXgcBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &,bool)
0x180019df6  mov     rdx, rax
0x180019df9  lea     rcx, [rbp+4Fh+var_78]
0x180019dfd  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x180019e02  lea     rcx, [rbp+4Fh+var_A8+10h]
0x180019e06  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019e0b  mov     ecx, 0C8h; Size
0x180019e10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019e15  mov     [rbp+4Fh+var_B0], rax
0x180019e19  movss   dword ptr [rsp+0E0h+var_C0], xmm6; float
0x180019e1f  lea     r9, [rbp+4Fh+var_78]; int
0x180019e23  lea     r8, [rbp+4Fh+var_88]; int
0x180019e27  mov     rdx, rdi; int
0x180019e2a  mov     rcx, rax; int
0x180019e2d  call    ??0CXgcGlyphs@@QEAA@AEBV?$shared_ptr@UIXpsOMGlyphs@@@std@@AEBV?$shared_ptr@UGlyphRun@xpsrdr@@@2@AEBV?$shared_ptr@VCXgcBrush@@@2@M@Z; CXgcGlyphs::CXgcGlyphs(std::shared_ptr<IXpsOMGlyphs> const &,std::shared_ptr<xpsrdr::GlyphRun> const &,std::shared_ptr<CXgcBrush> const &,float)
0x180019e32  mov     rdx, rax
0x180019e35  lea     rcx, [rbp+4Fh+var_A8+10h]
0x180019e39  call    ??$?0VCXgcCanvas@@$0A@@?$shared_ptr@VCXgcCanvas@@@std@@QEAA@PEAVCXgcCanvas@@@Z; std::shared_ptr<CXgcCanvas>::shared_ptr<CXgcCanvas>(CXgcCanvas *)
0x180019e3e  lea     rdx, [rbp+4Fh+var_A8+10h]
0x180019e42  mov     rcx, rbx
0x180019e45  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x180019e4a  lea     rcx, [rbp+4Fh+var_A8+10h]
0x180019e4e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019e53  nop
0x180019e54  lea     rcx, [rbp+4Fh+var_78]
0x180019e58  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019e5d  nop
0x180019e5e  lea     rcx, [rbp+4Fh+var_60]
0x180019e62  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019e67  nop
0x180019e68  lea     rcx, [rbp+4Fh+var_88]
0x180019e6c  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019e71  mov     rax, rbx
0x180019e74  movaps  xmm6, [rsp+0E0h+var_48+8]
0x180019e7c  add     rsp, 0B8h
0x180019e83  pop     r15
0x180019e85  pop     r14
0x180019e87  pop     rdi
0x180019e88  pop     rsi
0x180019e89  pop     rbx
0x180019e8a  pop     rbp
0x180019e8b  retn
```
