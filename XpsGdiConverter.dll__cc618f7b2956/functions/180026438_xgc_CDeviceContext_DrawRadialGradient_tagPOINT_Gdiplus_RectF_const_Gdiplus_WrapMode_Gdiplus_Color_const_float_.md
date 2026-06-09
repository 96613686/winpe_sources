# xgc::CDeviceContext::DrawRadialGradient(tagPOINT,Gdiplus::RectF const &,Gdiplus::WrapMode,Gdiplus::Color const *,float const *,int,bool,tagPOINT const (&)[3],tagPOINT const (&)[2])

- ea: `0x180026438`
- end: `0x1800266d6`
- name: `?DrawRadialGradient@CDeviceContext@xgc@@QEAAXUtagPOINT@@AEBVRectF@Gdiplus@@W4WrapMode@5@PEBVColor@5@PEBMH_NAEAY02$$CBU3@AEAY01$$CBU3@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002e684`

## callees

- `0x180011b0c`
- `0x1800246a8`
- `0x180024998`
- `0x180024a20`
- `0x180024a84`
- `0x180026438`
- `0x180027208`
- `0x180027724`

## import_xrefs

- `gdiplus!GdipDeleteMatrix` at `0x1800266a7`
- `gdiplus!GdipDeleteMatrix` at `0x1800266a7`
- `gdiplus!GdipFillRectangleI` at `0x18002663f`
- `gdiplus!GdipFillRectangleI` at `0x18002668c`
- `gdiplus!GdipFillRectangleI` at `0x18002663f`
- `gdiplus!GdipFillRectangleI` at `0x18002668c`
- `gdiplus!GdipSetPathGradientCenterPointI` at `0x180026598`
- `gdiplus!GdipSetPathGradientCenterPointI` at `0x180026598`
- `gdiplus!GdipAddPathEllipse` at `0x1800264bc`
- `gdiplus!GdipAddPathEllipse` at `0x1800264bc`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x1800265e6`
- `gdiplus!GdipSetPathGradientGammaCorrection` at `0x1800265e6`
- `gdiplus!GdipFillPath` at `0x18002665a`
- `gdiplus!GdipFillPath` at `0x18002665a`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x1800265f2`
- `gdiplus!GdipSetPathGradientWrapMode` at `0x1800265f2`
- `gdiplus!GdipCreatePath` at `0x180026496`
- `gdiplus!GdipCreatePath` at `0x180026496`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x1800265b6`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x1800265b6`
- `gdiplus!GdipDeletePath` at `0x1800266b2`
- `gdiplus!GdipDeletePath` at `0x1800266b2`
- `gdiplus!GdipDeleteBrush` at `0x18002666b`
- `gdiplus!GdipDeleteBrush` at `0x18002669c`
- `gdiplus!GdipDeleteBrush` at `0x18002666b`
- `gdiplus!GdipDeleteBrush` at `0x18002669c`
- `gdiplus!GdipTransformPath` at `0x18002656d`
- `gdiplus!GdipTransformPath` at `0x18002656d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall xgc::CDeviceContext::DrawRadialGradient(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        struct Gdiplus::Color *a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int8 a8,
        int *a9,
        unsigned int *a10)
{
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  int v18; // ebx
  struct Gdiplus::Color *v19; // rdi
  int v20; // eax
  __int64 v21; // rbx
  unsigned int v22; // r15d
  unsigned int v23; // esi
  unsigned int v24; // r12d
  int v25; // r14d
  __int64 v26; // rdi
  int v27; // eax
  __int64 v28; // rdi
  int v29; // eax
  __int64 v30; // rdi
  int v31; // eax
  __int64 v32; // [rsp+40h] [rbp-51h] BYREF
  int v33; // [rsp+48h] [rbp-49h]
  _QWORD v34[2]; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-31h] BYREF
  _BYTE v36[8]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v37; // [rsp+78h] [rbp-19h]
  int v38; // [rsp+80h] [rbp-11h]
  __int64 v39; // [rsp+F0h] [rbp+5Fh] BYREF

  if ( *(float *)(a3 + 8) > 0.0 && *(float *)(a3 + 12) > 0.0 )
  {
    xgc::GdiSurface::GdiSurface((xgc::GdiSurface *)v34, *(HDC *)(a1 + 32), (unsigned __int64 *)(a1 + 312));
    v32 = 0;
    v33 = GdipCreatePath(0, &v32);
    v13 = GdipAddPathEllipse(v32);
    v14 = v33;
    if ( v13 )
      v14 = v13;
    v33 = v14;
    Gdiplus::Matrix::Matrix(
      (Gdiplus::Matrix *)v35,
      (float)(a9[2] - *a9) / *(float *)(a3 + 8),
      (float)(a9[3] - a9[1]) / *(float *)(a3 + 8),
      (float)(a9[4] - *a9) / *(float *)(a3 + 12),
      (float)(a9[5] - a9[1]) / *(float *)(a3 + 12),
      (float)*a9,
      (float)a9[1]);
    Gdiplus::Matrix::Translate(v35);
    v15 = GdipTransformPath(v32, v35[0]);
    v16 = v33;
    if ( v15 )
      v16 = v15;
    v33 = v16;
    Gdiplus::PathGradientBrush::PathGradientBrush(
      (Gdiplus::PathGradientBrush *)v36,
      (const struct Gdiplus::GraphicsPath *)&v32);
    v39 = a2;
    v17 = GdipSetPathGradientCenterPointI(v37, &v39);
    v18 = v38;
    if ( v17 )
      v18 = v17;
    v19 = a5;
    v20 = GdipSetPathGradientCenterColor(v37, *((unsigned int *)a5 + (int)a7 - 1));
    if ( v20 )
      v18 = v20;
    v38 = v18;
    Gdiplus::PathGradientBrush::SetInterpolationColors(v36, v19, a6, a7);
    v21 = v37;
    GdipSetPathGradientGammaCorrection(v37, a8);
    GdipSetPathGradientWrapMode(v21, a4);
    v22 = a10[1];
    v23 = a10[3] - v22;
    v24 = *a10;
    v25 = a10[2] - *a10;
    if ( a4 == 4 )
    {
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v36, v19);
      v26 = v34[0];
      v27 = GdipFillRectangleI(*(_QWORD *)v34[0], v37, v24, v22, v25, v23);
      if ( v27 )
        *(_DWORD *)(v26 + 8) = v27;
      v28 = v34[0];
      v29 = GdipFillPath(*(_QWORD *)v34[0], v21, v32);
      if ( v29 )
        *(_DWORD *)(v28 + 8) = v29;
      GdipDeleteBrush(v37);
    }
    else
    {
      v30 = v34[0];
      v31 = GdipFillRectangleI(*(_QWORD *)v34[0], v21, v24, v22, v25, a10[3] - v22);
      if ( v31 )
        *(_DWORD *)(v30 + 8) = v31;
    }
    GdipDeleteBrush(v21);
    GdipDeleteMatrix(v35[0]);
    GdipDeletePath(v32);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v34);
  }
}

```

## disassembly

```asm
0x180026438  push    rbp
0x18002643a  push    rbx
0x18002643b  push    rsi
0x18002643c  push    rdi
0x18002643d  push    r12
0x18002643f  push    r13
0x180026441  push    r14
0x180026443  push    r15
0x180026445  lea     rbp, [rsp-7]
0x18002644a  sub     rsp, 98h
0x180026451  mov     r13d, r9d
0x180026454  mov     rdi, r8
0x180026457  mov     rbx, rdx
0x18002645a  xorps   xmm0, xmm0
0x18002645d  comiss  xmm0, dword ptr [r8+8]
0x180026462  jnb     loc_1800266C2
0x180026468  comiss  xmm0, dword ptr [r8+0Ch]
0x18002646d  jnb     loc_1800266C2
0x180026473  lea     r8, [rcx+138h]; unsigned __int64 *
0x18002647a  mov     rdx, [rcx+20h]; HDC
0x18002647e  lea     rcx, [rbp+3Fh+var_80]; this
0x180026482  call    ??0GdiSurface@xgc@@QEAA@PEAUHDC__@@AEA_K@Z; xgc::GdiSurface::GdiSurface(HDC__ *,unsigned __int64 &)
0x180026487  nop
0x180026488  mov     [rbp+3Fh+var_90], 0
0x180026490  lea     rdx, [rbp+3Fh+var_90]
0x180026494  xor     ecx, ecx
0x180026496  call    cs:__imp_GdipCreatePath
0x18002649c  mov     [rbp+3Fh+var_88], eax
0x18002649f  movss   xmm0, dword ptr [rdi+0Ch]
0x1800264a4  movss   [rsp+0D0h+var_B0], xmm0
0x1800264aa  movss   xmm3, dword ptr [rdi+8]
0x1800264af  movss   xmm2, dword ptr [rdi+4]
0x1800264b4  movss   xmm1, dword ptr [rdi]
0x1800264b8  mov     rcx, [rbp+3Fh+var_90]
0x1800264bc  call    cs:__imp_GdipAddPathEllipse
0x1800264c2  mov     ecx, [rbp+3Fh+var_88]
0x1800264c5  test    eax, eax
0x1800264c7  cmovnz  ecx, eax
0x1800264ca  mov     [rbp+3Fh+var_88], ecx
0x1800264cd  mov     rcx, [rbp+3Fh+arg_40]
0x1800264d4  movd    xmm4, dword ptr [rcx+4]
0x1800264d9  cvtdq2ps xmm4, xmm4
0x1800264dc  movd    xmm5, dword ptr [rcx]
0x1800264e0  cvtdq2ps xmm5, xmm5
0x1800264e3  mov     eax, [rcx+14h]
0x1800264e6  sub     eax, [rcx+4]
0x1800264e9  movd    xmm0, eax
0x1800264ed  cvtdq2ps xmm0, xmm0
0x1800264f0  divss   xmm0, dword ptr [rdi+0Ch]
0x1800264f5  mov     eax, [rcx+10h]
0x1800264f8  sub     eax, [rcx]
0x1800264fa  movd    xmm3, eax
0x1800264fe  cvtdq2ps xmm3, xmm3
0x180026501  divss   xmm3, dword ptr [rdi+0Ch]; float
0x180026506  mov     eax, [rcx+0Ch]
0x180026509  sub     eax, [rcx+4]
0x18002650c  movd    xmm2, eax
0x180026510  cvtdq2ps xmm2, xmm2
0x180026513  divss   xmm2, dword ptr [rdi+8]; float
0x180026518  mov     eax, [rcx+8]
0x18002651b  sub     eax, [rcx]
0x18002651d  movd    xmm1, eax
0x180026521  cvtdq2ps xmm1, xmm1
0x180026524  divss   xmm1, dword ptr [rdi+8]; float
0x180026529  movss   [rsp+0D0h+var_A0], xmm4; float
0x18002652f  movss   [rsp+0D0h+var_A8], xmm5; float
0x180026535  movss   [rsp+0D0h+var_B0], xmm0; float
0x18002653b  lea     rcx, [rbp+3Fh+var_70]; this
0x18002653f  call    ??0Matrix@Gdiplus@@QEAA@MMMMMM@Z; Gdiplus::Matrix::Matrix(float,float,float,float,float,float)
0x180026544  nop
0x180026545  movss   xmm2, dword ptr [rdi+4]
0x18002654a  xorps   xmm2, cs:__xmm@80000000800000008000000080000000
0x180026551  movss   xmm1, dword ptr [rdi]
0x180026555  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x18002655c  lea     rcx, [rbp+3Fh+var_70]
0x180026560  call    ?Translate@Matrix@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Matrix::Translate(float,float,Gdiplus::MatrixOrder)
0x180026565  mov     rdx, [rbp+3Fh+var_70]
0x180026569  mov     rcx, [rbp+3Fh+var_90]
0x18002656d  call    cs:__imp_GdipTransformPath
0x180026573  mov     ecx, [rbp+3Fh+var_88]
0x180026576  test    eax, eax
0x180026578  cmovnz  ecx, eax
0x18002657b  mov     [rbp+3Fh+var_88], ecx
0x18002657e  lea     rdx, [rbp+3Fh+var_90]; struct Gdiplus::GraphicsPath *
0x180026582  lea     rcx, [rbp+3Fh+var_60]; this
0x180026586  call    ??0PathGradientBrush@Gdiplus@@QEAA@PEBVGraphicsPath@1@@Z; Gdiplus::PathGradientBrush::PathGradientBrush(Gdiplus::GraphicsPath const *)
0x18002658b  nop
0x18002658c  mov     [rbp+3Fh+arg_10], rbx
0x180026590  lea     rdx, [rbp+3Fh+arg_10]
0x180026594  mov     rcx, [rbp+3Fh+var_58]
0x180026598  call    cs:__imp_GdipSetPathGradientCenterPointI
0x18002659e  mov     ebx, [rbp+3Fh+var_50]
0x1800265a1  test    eax, eax
0x1800265a3  cmovnz  ebx, eax
0x1800265a6  movsxd  rdx, [rbp+3Fh+arg_30]
0x1800265aa  mov     rdi, [rbp+3Fh+arg_20]
0x1800265ae  mov     edx, [rdi+rdx*4-4]
0x1800265b2  mov     rcx, [rbp+3Fh+var_58]
0x1800265b6  call    cs:__imp_GdipSetPathGradientCenterColor
0x1800265bc  test    eax, eax
0x1800265be  cmovnz  ebx, eax
0x1800265c1  mov     [rbp+3Fh+var_50], ebx
0x1800265c4  mov     r9d, [rbp+3Fh+arg_30]
0x1800265c8  mov     r8, [rbp+3Fh+arg_28]
0x1800265cc  mov     rdx, rdi
0x1800265cf  lea     rcx, [rbp+3Fh+var_60]
0x1800265d3  call    ?SetInterpolationColors@PathGradientBrush@Gdiplus@@QEAA?AW4Status@2@PEBVColor@2@PEBMH@Z; Gdiplus::PathGradientBrush::SetInterpolationColors(Gdiplus::Color const *,float const *,int)
0x1800265d8  movzx   edx, [rbp+3Fh+arg_38]
0x1800265df  mov     rbx, [rbp+3Fh+var_58]
0x1800265e3  mov     rcx, rbx
0x1800265e6  call    cs:__imp_GdipSetPathGradientGammaCorrection
0x1800265ec  mov     edx, r13d
0x1800265ef  mov     rcx, rbx
0x1800265f2  call    cs:__imp_GdipSetPathGradientWrapMode
0x1800265f8  mov     rax, [rbp+3Fh+arg_48]
0x1800265ff  mov     r15d, [rax+4]
0x180026603  mov     esi, [rax+0Ch]
0x180026606  sub     esi, r15d
0x180026609  mov     r12d, [rax]
0x18002660c  mov     r14d, [rax+8]
0x180026610  sub     r14d, r12d
0x180026613  cmp     r13d, 4
0x180026617  jnz     short loc_180026673
0x180026619  mov     rdx, rdi; struct Gdiplus::Color *
0x18002661c  lea     rcx, [rbp+3Fh+var_60]; this
0x180026620  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180026625  mov     rdi, [rbp+3Fh+var_80]
0x180026629  mov     [rsp+0D0h+var_A8], esi
0x18002662d  mov     [rsp+0D0h+var_B0], r14d
0x180026632  mov     r9d, r15d
0x180026635  mov     r8d, r12d
0x180026638  mov     rdx, [rbp+3Fh+var_58]
0x18002663c  mov     rcx, [rdi]
0x18002663f  call    cs:__imp_GdipFillRectangleI
0x180026645  test    eax, eax
0x180026647  jz      short loc_18002664C
0x180026649  mov     [rdi+8], eax
0x18002664c  mov     rdi, [rbp+3Fh+var_80]
0x180026650  mov     r8, [rbp+3Fh+var_90]
0x180026654  mov     rdx, rbx
0x180026657  mov     rcx, [rdi]
0x18002665a  call    cs:__imp_GdipFillPath
0x180026660  test    eax, eax
0x180026662  jz      short loc_180026667
0x180026664  mov     [rdi+8], eax
0x180026667  mov     rcx, [rbp+3Fh+var_58]
0x18002666b  call    cs:__imp_GdipDeleteBrush
0x180026671  jmp     short loc_180026699
0x180026673  mov     rdi, [rbp+3Fh+var_80]
0x180026677  mov     [rsp+0D0h+var_A8], esi
0x18002667b  mov     [rsp+0D0h+var_B0], r14d
0x180026680  mov     r9d, r15d
0x180026683  mov     r8d, r12d
0x180026686  mov     rdx, rbx
0x180026689  mov     rcx, [rdi]
0x18002668c  call    cs:__imp_GdipFillRectangleI
0x180026692  test    eax, eax
0x180026694  jz      short loc_180026699
0x180026696  mov     [rdi+8], eax
0x180026699  mov     rcx, rbx
0x18002669c  call    cs:__imp_GdipDeleteBrush
0x1800266a2  nop
0x1800266a3  mov     rcx, [rbp+3Fh+var_70]
0x1800266a7  call    cs:__imp_GdipDeleteMatrix
0x1800266ad  nop
0x1800266ae  mov     rcx, [rbp+3Fh+var_90]
0x1800266b2  call    cs:__imp_GdipDeletePath
0x1800266b8  nop
0x1800266b9  lea     rcx, [rbp+3Fh+var_80]
0x1800266bd  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800266c2  add     rsp, 98h
0x1800266c9  pop     r15
0x1800266cb  pop     r14
0x1800266cd  pop     r13
0x1800266cf  pop     r12
0x1800266d1  pop     rdi
0x1800266d2  pop     rsi
0x1800266d3  pop     rbx
0x1800266d4  pop     rbp
0x1800266d5  retn
```
