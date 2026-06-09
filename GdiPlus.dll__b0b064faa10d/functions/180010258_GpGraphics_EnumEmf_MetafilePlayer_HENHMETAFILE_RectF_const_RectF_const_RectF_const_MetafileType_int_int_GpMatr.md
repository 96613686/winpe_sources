# GpGraphics::EnumEmf(MetafilePlayer *,HENHMETAFILE__ *,RectF const &,RectF const &,RectF const &,MetafileType,int,int,GpMatrix const &,int)

- ea: `0x180010258`
- end: `0x180010a62`
- name: `?EnumEmf@GpGraphics@@QEAA?AW4Status@@PEAVMetafilePlayer@@PEAUHENHMETAFILE__@@AEBVRectF@@22W4MetafileType@@HHAEBVGpMatrix@@H@Z`
- size: `2058`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f07c`

## callees

- `0x18000ca18`
- `0x18000cb6c`
- `0x18001006c`
- `0x180010258`
- `0x180010a68`
- `0x180014ce4`
- `0x18003d260`
- `0x18003d33c`
- `0x18004396c`
- `0x18005b2a0`
- `0x180076f28`
- `0x1800daab8`
- `0x1800fe680`
- `0x1800fefe0`
- `0x180119efc`
- `0x18011a194`
- `0x18011b4d0`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180010714`
- `GDI32!SetWorldTransform` at `0x180010714`
- `GDI32!SetGraphicsMode` at `0x1800106e2`
- `GDI32!SetGraphicsMode` at `0x1800106e2`
- `GDI32!SetViewportExtEx` at `0x18001054a`
- `GDI32!SetViewportExtEx` at `0x180010998`
- `GDI32!SetViewportExtEx` at `0x18001054a`
- `GDI32!SetViewportExtEx` at `0x180010998`
- `GDI32!SetViewportOrgEx` at `0x180010531`
- `GDI32!SetViewportOrgEx` at `0x180010983`
- `GDI32!SetViewportOrgEx` at `0x180010531`
- `GDI32!SetViewportOrgEx` at `0x180010983`
- `GDI32!SetWindowExtEx` at `0x18001051f`
- `GDI32!SetWindowExtEx` at `0x180010972`
- `GDI32!SetWindowExtEx` at `0x18001051f`
- `GDI32!SetWindowExtEx` at `0x180010972`
- `GDI32!SetWindowOrgEx` at `0x18001050a`
- `GDI32!SetWindowOrgEx` at `0x18001095d`
- `GDI32!SetWindowOrgEx` at `0x18001050a`
- `GDI32!SetWindowOrgEx` at `0x18001095d`
- `GDI32!SetMapMode` at `0x1800104f5`
- `GDI32!SetMapMode` at `0x180010948`
- `GDI32!SetMapMode` at `0x1800104f5`
- `GDI32!SetMapMode` at `0x180010948`
- `GDI32!SaveDC` at `0x1800102d2`
- `GDI32!SaveDC` at `0x1800102d2`
- `GDI32!RestoreDC` at `0x180010580`
- `GDI32!RestoreDC` at `0x180010580`
- `GDI32!DeleteDC` at `0x1800109c3`
- `GDI32!DeleteDC` at `0x1800109c3`
- `GDI32!SelectObject` at `0x1800108f8`
- `GDI32!SelectObject` at `0x1800108f8`
- `GDI32!CreateCompatibleDC` at `0x1800108e0`
- `GDI32!CreateCompatibleDC` at `0x1800108e0`
- `GDI32!DeleteObject` at `0x180010a3d`
- `GDI32!DeleteObject` at `0x180010a3d`

## pseudocode

```c
__int64 __fastcall GpGraphics::EnumEmf(
        struct DpBitmap **a1,
        __int64 a2,
        __int64 a3,
        float *a4,
        unsigned int *a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        int a11)
{
  struct DpBitmap *v12; // rdx
  DpContext *v14; // rcx
  HDC Hdc; // rax
  HDC v17; // rdi
  int v18; // eax
  DpContext *v19; // rcx
  bool v20; // r15
  unsigned int v21; // r14d
  __m128 v22; // xmm1
  int v23; // eax
  __m128 v24; // xmm1
  int v25; // eax
  __m128 v26; // xmm1
  int v27; // eax
  __m128 v28; // xmm1
  int v29; // eax
  float v30; // xmm6_4
  int v31; // eax
  float v32; // xmm7_4
  int v33; // eax
  float v34; // xmm6_4
  int v35; // eax
  float v36; // xmm7_4
  PointF *v37; // r15
  __int64 v38; // r13
  float v39; // xmm1_4
  FLOAT v40; // r12d
  FLOAT v41; // r13d
  FLOAT eM22; // r15d
  unsigned int v43; // eax
  __m128 v45; // xmm7
  __m128 v46; // xmm1
  int v47; // eax
  __m128 v48; // xmm6
  __m128 v49; // xmm1
  int v50; // eax
  int v51; // r13d
  int v52; // eax
  FLOAT v53; // xmm1_4
  XFORM *p_xf; // r9
  struct DpBitmap *v55; // rax
  void *DibSection32Bpp; // r13
  HDC CompatibleDC; // rax
  HDC v58; // r15
  unsigned int v59; // eax
  struct DpBitmap *v60; // rax
  int v61; // r15d
  int v62; // [rsp+28h] [rbp-E0h]
  int v63; // [rsp+38h] [rbp-D0h]
  __int128 v64; // [rsp+48h] [rbp-C0h] BYREF
  int y; // [rsp+58h] [rbp-B0h]
  int x; // [rsp+5Ch] [rbp-ACh]
  int v67[2]; // [rsp+60h] [rbp-A8h]
  __int64 v68; // [rsp+68h] [rbp-A0h]
  __int128 v69; // [rsp+70h] [rbp-98h] BYREF
  __int64 v70; // [rsp+80h] [rbp-88h]
  int nSavedDC; // [rsp+88h] [rbp-80h]
  _BYTE v72[24]; // [rsp+90h] [rbp-78h] BYREF
  int v73; // [rsp+A8h] [rbp-60h]
  XFORM xf; // [rsp+B0h] [rbp-58h] BYREF

  v12 = a1[5];
  v14 = a1[17];
  *(_QWORD *)&xf.eM11 = a6;
  v70 = a10;
  v68 = a3;
  Hdc = DpContext::GetHdc(v14, v12);
  v17 = Hdc;
  if ( Hdc )
  {
    v18 = SaveDC(Hdc);
    v19 = a1[17];
    nSavedDC = v18;
    if ( v18 )
    {
      DpContext::CleanTheHdc(v19, v17);
      v20 = Feature_GdiPlusOptimizations_Misc_IsEnabled;
      v21 = 0;
      *(_DWORD *)(a2 + 5240) = 1;
      v22 = (__m128)*a5;
      v22.m128_f32[0] = v22.m128_f32[0] + 0.5;
      if ( v20 )
        v23 = (int)_mm_round_ss(v22, v22, 9).m128_f32[0];
      else
        v23 = (int)floor(v22.m128_f32[0]);
      v24 = (__m128)a5[1];
      x = v23;
      v24.m128_f32[0] = v24.m128_f32[0] + 0.5;
      if ( v20 )
        v25 = (int)_mm_round_ss(v24, v24, 9).m128_f32[0];
      else
        v25 = (int)floor(v24.m128_f32[0]);
      v26 = (__m128)a5[2];
      y = v25;
      v26.m128_f32[0] = v26.m128_f32[0] + 0.5;
      if ( v20 )
        v27 = (int)_mm_round_ss(v26, v26, 9).m128_f32[0];
      else
        v27 = (int)floor(v26.m128_f32[0]);
      v28 = (__m128)a5[3];
      v67[1] = v27;
      v28.m128_f32[0] = v28.m128_f32[0] + 0.5;
      if ( v20 )
        v29 = (int)_mm_round_ss(v28, v28, 9).m128_f32[0];
      else
        v29 = (int)floor(v28.m128_f32[0]);
      v67[0] = v29;
      v30 = **(float **)&xf.eM11;
      v31 = RasterizerCeiling(**(float **)&xf.eM11);
      v32 = *(float *)(*(_QWORD *)&xf.eM11 + 4LL);
      LODWORD(v69) = v31;
      v33 = RasterizerCeiling(v32);
      v34 = v30 + *(float *)(*(_QWORD *)&xf.eM11 + 8LL);
      DWORD1(v69) = v33;
      v35 = RasterizerCeiling(v34);
      v36 = v32 + *(float *)(*(_QWORD *)&xf.eM11 + 12LL);
      DWORD2(v69) = v35;
      HIDWORD(v69) = RasterizerCeiling(v36);
      if ( a8 )
      {
        SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
          (SetupClippingForMetafilePlayback *)v72,
          v17,
          a1[16],
          a1[17],
          v62);
        if ( v73 )
          goto LABEL_20;
        *(_QWORD *)&xf.eM11 = 0;
        v37 = (PointF *)&v64;
        v38 = 2;
        do
        {
          PointF::PointF(v37);
          v37 = (PointF *)((char *)v37 + 8);
          --v38;
        }
        while ( v38 );
        v39 = a4[1];
        *(float *)&v64 = *a4;
        *(_QWORD *)((char *)&v64 + 4) = __PAIR64__(*(float *)&v64 + a4[2], LODWORD(v39));
        *((float *)&v64 + 3) = v39 + a4[3];
        GpMatrix::Transform((GpMatrix *)(a2 + 5256), (struct PointF *)&v64, 2);
        LODWORD(xf.eM11) = RasterizerCeiling(*(float *)&v64);
        LODWORD(v40) = RasterizerCeiling(*((float *)&v64 + 1));
        xf.eM12 = v40;
        LODWORD(v41) = RasterizerCeiling(*((float *)&v64 + 2));
        xf.eM21 = v41;
        LODWORD(xf.eM22) = RasterizerCeiling(*((float *)&v64 + 3));
        eM22 = xf.eM22;
        if ( SLODWORD(v40) >= SLODWORD(xf.eM22) || SLODWORD(xf.eM11) >= SLODWORD(v41) )
          goto LABEL_20;
        if ( (unsigned int)(a7 - 1) <= 1 )
        {
          SetMapMode(v17, 8);
          SetWindowOrgEx(v17, x, y, 0);
          SetWindowExtEx(v17, v67[1], v67[0], 0);
          SetViewportOrgEx(v17, SLODWORD(xf.eM11), SLODWORD(v40), 0);
          SetViewportExtEx(v17, LODWORD(v41) - LODWORD(xf.eM11), LODWORD(eM22) - LODWORD(v40), 0);
          v43 = MetafilePlayer::EnumerateWmfRecords(a2, v17, v68, &xf, &v69);
LABEL_19:
          v21 = v43;
          goto LABEL_20;
        }
        p_xf = &xf;
        if ( a11 )
        {
          LODWORD(xf.eM11) = x;
          v63 = a11;
          LODWORD(xf.eM21) = v67[1] + 1 + x;
          LODWORD(xf.eM12) = y;
          LODWORD(xf.eM22) = v67[0] + 1 + y;
          goto LABEL_40;
        }
      }
      else
      {
        v64 = 0;
        if ( a9 )
        {
          v55 = a1[17];
          *(_QWORD *)&xf.eM11 = 0;
          v21 = 1;
          *(_DWORD *)(a2 + 5336) = *((_DWORD *)v55 + 18);
          DibSection32Bpp = (void *)CreateDibSection32Bpp(v17, a2 + 5336, (GpMatrix *)(a2 + 5256));
          if ( DibSection32Bpp )
          {
            Init32BppDibToTransparent(*(unsigned int **)&xf.eM11, DWORD2(v64) * HIDWORD(v64));
            CompatibleDC = CreateCompatibleDC(0);
            v58 = CompatibleDC;
            if ( CompatibleDC )
            {
              SelectObject(CompatibleDC, DibSection32Bpp);
              if ( (unsigned int)(a7 - 1) <= 1 )
              {
                SetMapMode(v58, 8);
                SetWindowOrgEx(v58, x, y, 0);
                SetWindowExtEx(v58, v67[1], v67[0], 0);
                SetViewportOrgEx(v58, 0, 0, 0);
                SetViewportExtEx(v58, SDWORD2(v64), SHIDWORD(v64), 0);
                v59 = MetafilePlayer::EnumerateWmfRecords(a2, v58, v68, &v64, &v64);
              }
              else
              {
                v59 = MetafilePlayer::EnumerateEmfRecords(a2, v58, v68, &v64, &v64, &EnumEmfDownLevel, 0);
              }
              v21 = v59;
              DeleteDC(v58);
              if ( v21 != 9 )
              {
                v60 = a1[17];
                v61 = *((_DWORD *)v60 + 12);
                if ( v61 == 5 )
                  *((_DWORD *)v60 + 12) = 3;
                GpGraphics::SetWorldTransform(a1, v70);
                v21 = Draw32BppDib(
                        a1,
                        *(_QWORD *)&xf.eM11,
                        DWORD2(v64),
                        HIDWORD(v64),
                        a4,
                        *(_DWORD *)(a2 + 5336),
                        *(_DWORD *)(a2 + 5412) == 0);
                *((_DWORD *)a1[17] + 12) = v61;
              }
            }
            DeleteObject(DibSection32Bpp);
          }
          else if ( !DWORD2(v64) || !HIDWORD(v64) )
          {
            v21 = 0;
          }
          goto LABEL_21;
        }
        v45 = (__m128)*(unsigned int *)a4;
        v46 = v45;
        v46.m128_f32[0] = v45.m128_f32[0] + 0.5;
        if ( v20 )
          v47 = (int)_mm_round_ss(v46, v46, 9).m128_f32[0];
        else
          v47 = (int)floor(v46.m128_f32[0]);
        v48 = (__m128)*((unsigned int *)a4 + 1);
        LODWORD(xf.eM11) = v47;
        v49 = v48;
        LODWORD(v64) = v47;
        v49.m128_f32[0] = v48.m128_f32[0] + 0.5;
        if ( v20 )
          v50 = (int)_mm_round_ss(v49, v49, 9).m128_f32[0];
        else
          v50 = (int)floor(v49.m128_f32[0]);
        LODWORD(v70) = v50;
        DWORD1(v64) = v50;
        v45.m128_f32[0] = (float)(v45.m128_f32[0] + a4[2]) + 0.5;
        if ( v20 )
          v51 = (int)_mm_round_ss(v45, v45, 9).m128_f32[0];
        else
          v51 = (int)floor(v45.m128_f32[0]);
        DWORD2(v64) = v51;
        v48.m128_f32[0] = (float)(v48.m128_f32[0] + a4[3]) + 0.5;
        if ( v20 )
          v52 = (int)_mm_round_ss(v48, v48, 9).m128_f32[0];
        else
          v52 = (int)floor(v48.m128_f32[0]);
        HIDWORD(v64) = v52;
        if ( v52 <= (int)v70 || v51 <= SLODWORD(xf.eM11) )
        {
LABEL_21:
          RestoreDC(v17, nSavedDC);
          DpContext::ReleaseHdc(a1[17], v17, a1[5]);
          return v21;
        }
        SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(
          (SetupClippingForMetafilePlayback *)v72,
          v17,
          a1[16],
          a1[17],
          v62);
        if ( v73 )
        {
LABEL_20:
          SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback((SetupClippingForMetafilePlayback *)v72);
          goto LABEL_21;
        }
        if ( a11 )
        {
          *(_QWORD *)&v69 = __PAIR64__(y, x);
          DWORD2(v69) = v67[1] + 1 + x;
          HIDWORD(v69) = v67[0] + 1 + y;
          v64 = 0;
          v43 = MetafilePlayer::EnumerateEmfRecords(a2, v17, v68, &v69, &v64, &EnumEmfDownLevel, a11);
          goto LABEL_19;
        }
        SetGraphicsMode(v17, 2);
        v53 = *(float *)(a2 + 5292);
        *(_OWORD *)&xf.eM11 = *(_OWORD *)(a2 + 5272);
        xf.eDx = *(FLOAT *)(a2 + 5288);
        xf.eDy = v53;
        SetWorldTransform(v17, &xf);
        p_xf = (XFORM *)&v64;
        v69 = 0;
      }
      v63 = 0;
LABEL_40:
      v43 = MetafilePlayer::EnumerateEmfRecords(a2, v17, v68, p_xf, &v69, &EnumEmfDownLevel, v63);
      goto LABEL_19;
    }
    DpContext::ReleaseHdc(v19, v17, a1[5]);
  }
  return 1;
}

```

## disassembly

```asm
0x180010258  mov     rax, rsp
0x18001025b  push    rbp
0x18001025c  push    rbx
0x18001025d  push    rsi
0x18001025e  push    rdi
0x18001025f  push    r12
0x180010261  push    r13
0x180010263  push    r14
0x180010265  push    r15
0x180010267  lea     rbp, [rax-48h]
0x18001026b  sub     rsp, 108h
0x180010272  movaps  xmmword ptr [rax-58h], xmm6
0x180010276  movaps  xmmword ptr [rax-68h], xmm7
0x18001027a  movaps  xmmword ptr [rax-78h], xmm8
0x18001027f  mov     rax, cs:__security_cookie
0x180010286  xor     rax, rsp
0x180010289  mov     [rbp+40h+var_80], rax
0x18001028d  mov     rax, [rbp+40h+arg_28]
0x180010291  mov     rsi, rdx
0x180010294  mov     rdx, [rcx+28h]; struct DpBitmap *
0x180010298  mov     rbx, rcx
0x18001029b  mov     rcx, [rcx+88h]; this
0x1800102a2  mov     r12, r9
0x1800102a5  mov     r13, [rbp+40h+arg_20]
0x1800102a9  mov     qword ptr [rbp+40h+xf.eM11], rax
0x1800102ad  mov     rax, [rbp+40h+arg_48]
0x1800102b4  mov     [rsp+140h+var_C8], rax
0x1800102b9  mov     qword ptr [rsp+140h+var_E0], r8
0x1800102be  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x1800102c3  mov     rdi, rax
0x1800102c6  test    rax, rax
0x1800102c9  jz      loc_1800105A7
0x1800102cf  mov     rcx, rax; hdc
0x1800102d2  call    cs:__imp_SaveDC
0x1800102d8  mov     rcx, [rbx+88h]; this
0x1800102df  mov     rdx, rdi; HDC
0x1800102e2  mov     [rbp+40h+nSavedDC], eax
0x1800102e5  test    eax, eax
0x1800102e7  jz      loc_18001059E
0x1800102ed  call    ?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z; DpContext::CleanTheHdc(HDC__ *)
0x1800102f2  mov     r15b, cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x1800102f9  xor     r14d, r14d
0x1800102fc  movss   xmm8, cs:__real@3f000000
0x180010305  mov     dword ptr [rsi+1478h], 1
0x18001030f  movss   xmm1, dword ptr [r13+0]
0x180010315  addss   xmm1, xmm8
0x18001031a  test    r15b, r15b
0x18001031d  jnz     loc_18001076B
0x180010323  cvtps2pd xmm0, xmm1; X
0x180010326  call    floor
0x18001032b  cvttsd2si eax, xmm0
0x18001032f  movss   xmm1, dword ptr [r13+4]
0x180010335  mov     [rsp+140h+x], eax
0x180010339  addss   xmm1, xmm8
0x18001033e  test    r15b, r15b
0x180010341  jnz     loc_18001077D
0x180010347  cvtps2pd xmm0, xmm1; X
0x18001034a  call    floor
0x18001034f  cvttsd2si eax, xmm0
0x180010353  movss   xmm1, dword ptr [r13+8]
0x180010359  mov     [rsp+140h+y], eax
0x18001035d  addss   xmm1, xmm8
0x180010362  test    r15b, r15b
0x180010365  jnz     loc_18001078F
0x18001036b  cvtps2pd xmm0, xmm1; X
0x18001036e  call    floor
0x180010373  cvttsd2si eax, xmm0
0x180010377  movss   xmm1, dword ptr [r13+0Ch]
0x18001037d  mov     [rsp+140h+var_E8+4], eax
0x180010381  addss   xmm1, xmm8
0x180010386  test    r15b, r15b
0x180010389  jnz     loc_1800107A1
0x18001038f  cvtps2pd xmm0, xmm1; X
0x180010392  call    floor
0x180010397  cvttsd2si eax, xmm0
0x18001039b  mov     r13, qword ptr [rbp+40h+xf.eM11]
0x18001039f  mov     [rsp+140h+var_E8], eax
0x1800103a3  movss   xmm6, dword ptr [r13+0]
0x1800103a9  movaps  xmm0, xmm6; float
0x1800103ac  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800103b1  movss   xmm7, dword ptr [r13+4]
0x1800103b7  movaps  xmm0, xmm7; float
0x1800103ba  mov     dword ptr [rsp+140h+var_E0+8], eax
0x1800103be  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800103c3  addss   xmm6, dword ptr [r13+8]
0x1800103c9  mov     dword ptr [rsp+140h+var_E0+0Ch], eax
0x1800103cd  movaps  xmm0, xmm6; float
0x1800103d0  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800103d5  addss   xmm7, dword ptr [r13+0Ch]
0x1800103db  mov     dword ptr [rsp+140h+var_D0], eax
0x1800103df  movaps  xmm0, xmm7; float
0x1800103e2  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800103e7  xor     r13d, r13d
0x1800103ea  mov     dword ptr [rsp+140h+var_D0+4], eax
0x1800103ee  cmp     [rbp+40h+arg_38], r13d
0x1800103f5  jz      loc_1800105DF
0x1800103fb  mov     r9, [rbx+88h]; struct DpContext *
0x180010402  lea     rcx, [rbp+40h+var_B8]; this
0x180010406  mov     r8, [rbx+80h]; struct DpDriver *
0x18001040d  mov     rdx, rdi; HDC
0x180010410  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x180010415  cmp     [rbp+40h+var_A0], r13d
0x180010419  jnz     loc_180010571
0x18001041f  mov     qword ptr [rbp+40h+xf.eM11], r13
0x180010423  lea     r15, [rsp+140h+var_108+8]
0x180010428  mov     r13d, 2
0x18001042e  mov     rcx, r15; this
0x180010431  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x180010436  add     r15, 8
0x18001043a  sub     r13, 1
0x18001043e  jnz     short loc_18001042E
0x180010440  movss   xmm0, dword ptr [r12]
0x180010446  lea     rcx, [rsi+1488h]; this
0x18001044d  movss   xmm1, dword ptr [r12+4]
0x180010454  lea     r8d, [r13+2]; int
0x180010458  movss   [rsp+140h+var_108+8], xmm0
0x18001045e  lea     rdx, [rsp+140h+var_108+8]; struct PointF *
0x180010463  addss   xmm0, dword ptr [r12+8]
0x18001046a  movss   [rsp+140h+var_108+0Ch], xmm1
0x180010470  addss   xmm1, dword ptr [r12+0Ch]
0x180010477  movss   [rsp+140h+var_F8], xmm0
0x18001047d  movss   [rsp+140h+var_F4], xmm1
0x180010483  call    ?Transform@GpMatrix@@QEBAXPEAVPointF@@H@Z; GpMatrix::Transform(PointF *,int)
0x180010488  movss   xmm0, [rsp+140h+var_108+8]; float
0x18001048e  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x180010493  movss   xmm0, [rsp+140h+var_108+0Ch]; float
0x180010499  mov     [rbp+40h+xf.eM11], eax
0x18001049c  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800104a1  movss   xmm0, [rsp+140h+var_F8]; float
0x1800104a7  mov     r12d, eax
0x1800104aa  mov     [rbp+40h+xf.eM12], eax
0x1800104ad  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800104b2  movss   xmm0, [rsp+140h+var_F4]; float
0x1800104b8  mov     r13d, eax
0x1800104bb  mov     [rbp+40h+xf.eM21], eax
0x1800104be  call    ?RasterizerCeiling@@YAHM@Z; RasterizerCeiling(float)
0x1800104c3  mov     [rbp+40h+xf.eM22], eax
0x1800104c6  mov     r15d, eax
0x1800104c9  cmp     r12d, eax
0x1800104cc  jge     loc_180010571
0x1800104d2  cmp     [rbp+40h+xf.eM11], r13d
0x1800104d6  jge     loc_180010571
0x1800104dc  mov     eax, [rbp+40h+arg_30]
0x1800104e2  dec     eax
0x1800104e4  cmp     eax, 1
0x1800104e7  ja      loc_180010729
0x1800104ed  mov     edx, 8; iMode
0x1800104f2  mov     rcx, rdi; hdc
0x1800104f5  call    cs:__imp_SetMapMode
0x1800104fb  mov     r8d, [rsp+140h+y]; y
0x180010500  xor     r9d, r9d; lppt
0x180010503  mov     edx, [rsp+140h+x]; x
0x180010507  mov     rcx, rdi; hdc
0x18001050a  call    cs:__imp_SetWindowOrgEx
0x180010510  mov     r8d, [rsp+140h+var_E8]; y
0x180010515  xor     r9d, r9d; lpsz
0x180010518  mov     edx, [rsp+140h+var_E8+4]; x
0x18001051c  mov     rcx, rdi; hdc
0x18001051f  call    cs:__imp_SetWindowExtEx
0x180010525  mov     edx, [rbp+40h+xf.eM11]; x
0x180010528  xor     r9d, r9d; lppt
0x18001052b  mov     r8d, r12d; y
0x18001052e  mov     rcx, rdi; hdc
0x180010531  call    cs:__imp_SetViewportOrgEx
0x180010537  sub     r13d, [rbp+40h+xf.eM11]
0x18001053b  sub     r15d, r12d
0x18001053e  mov     r8d, r15d; y
0x180010541  mov     edx, r13d; x
0x180010544  xor     r9d, r9d; lpsz
0x180010547  mov     rcx, rdi; hdc
0x18001054a  call    cs:__imp_SetViewportExtEx
0x180010550  mov     r8, qword ptr [rsp+140h+var_E0]
0x180010555  lea     rax, [rsp+140h+var_E0+8]
0x18001055a  lea     r9, [rbp+40h+xf]
0x18001055e  mov     [rsp+140h+var_120], rax
0x180010563  mov     rdx, rdi
0x180010566  mov     rcx, rsi
0x180010569  call    ?EnumerateWmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHMETAFILE__@@PEBUtagRECT@@2@Z; MetafilePlayer::EnumerateWmfRecords(HDC__ *,HMETAFILE__ *,tagRECT const *,tagRECT const *)
0x18001056e  mov     r14d, eax
0x180010571  lea     rcx, [rbp+40h+var_B8]; this
0x180010575  call    ??1SetupClippingForMetafilePlayback@@QEAA@XZ; SetupClippingForMetafilePlayback::~SetupClippingForMetafilePlayback(void)
0x18001057a  mov     edx, [rbp+40h+nSavedDC]; nSavedDC
0x18001057d  mov     rcx, rdi; hdc
0x180010580  call    cs:__imp_RestoreDC
0x180010586  mov     r8, [rbx+28h]; struct DpBitmap *
0x18001058a  mov     rdx, rdi; HDC
0x18001058d  mov     rcx, [rbx+88h]; this
0x180010594  call    ?ReleaseHdc@DpContext@@QEAAXPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::ReleaseHdc(HDC__ *,DpBitmap *)
0x180010599  mov     eax, r14d
0x18001059c  jmp     short loc_1800105AC
0x18001059e  mov     r8, [rbx+28h]; struct DpBitmap *
0x1800105a2  call    ?ReleaseHdc@DpContext@@QEAAXPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::ReleaseHdc(HDC__ *,DpBitmap *)
0x1800105a7  mov     eax, 1
0x1800105ac  mov     rcx, [rbp+40h+var_80]
0x1800105b0  xor     rcx, rsp; StackCookie
0x1800105b3  call    __security_check_cookie
0x1800105b8  lea     r11, [rsp+140h+var_38]
0x1800105c0  movaps  xmm6, xmmword ptr [r11-18h]
0x1800105c5  movaps  xmm7, xmmword ptr [r11-28h]
0x1800105ca  movaps  xmm8, xmmword ptr [r11-38h]
0x1800105cf  mov     rsp, r11
0x1800105d2  pop     r15
0x1800105d4  pop     r14
0x1800105d6  pop     r13
0x1800105d8  pop     r12
0x1800105da  pop     rdi
0x1800105db  pop     rsi
0x1800105dc  pop     rbx
0x1800105dd  pop     rbp
0x1800105de  retn
0x1800105df  xorps   xmm0, xmm0
0x1800105e2  movups  xmmword ptr [rsp+140h+var_108+8], xmm0
0x1800105e7  cmp     [rbp+40h+arg_40], r13d
0x1800105ee  jnz     loc_18001087E
0x1800105f4  movss   xmm7, dword ptr [r12]
0x1800105fa  movaps  xmm1, xmm7
0x1800105fd  addss   xmm1, xmm8
0x180010602  test    r15b, r15b
0x180010605  jnz     loc_1800107B3
0x18001060b  cvtps2pd xmm0, xmm1; X
0x18001060e  call    floor
0x180010613  cvttsd2si eax, xmm0
0x180010617  movss   xmm6, dword ptr [r12+4]
0x18001061e  mov     [rbp+40h+xf.eM11], eax
0x180010621  movaps  xmm1, xmm6
0x180010624  mov     [rsp+140h+var_108+8], eax
0x180010628  addss   xmm1, xmm8
0x18001062d  test    r15b, r15b
0x180010630  jnz     loc_1800107C5
0x180010636  cvtps2pd xmm0, xmm1; X
0x180010639  call    floor
0x18001063e  cvttsd2si eax, xmm0
0x180010642  mov     dword ptr [rsp+140h+var_C8], eax
0x180010646  mov     [rsp+140h+var_108+0Ch], eax
0x18001064a  addss   xmm7, dword ptr [r12+8]
0x180010651  addss   xmm7, xmm8
0x180010656  test    r15b, r15b
0x180010659  jnz     loc_1800107D7
0x18001065f  cvtps2pd xmm0, xmm7; X
0x180010662  call    floor
0x180010667  cvttsd2si r13d, xmm0
0x18001066c  mov     [rsp+140h+var_F8], r13d
0x180010671  addss   xmm6, dword ptr [r12+0Ch]
0x180010678  addss   xmm6, xmm8
0x18001067d  test    r15b, r15b
0x180010680  jnz     loc_1800107EA
0x180010686  cvtps2pd xmm0, xmm6; X
0x180010689  call    floor
0x18001068e  cvttsd2si eax, xmm0
0x180010692  mov     [rsp+140h+var_F4], eax
0x180010696  cmp     eax, dword ptr [rsp+140h+var_C8]
0x18001069a  jle     loc_18001057A
0x1800106a0  cmp     r13d, [rbp+40h+xf.eM11]
0x1800106a4  jle     loc_18001057A
0x1800106aa  mov     r9, [rbx+88h]; struct DpContext *
0x1800106b1  lea     rcx, [rbp+40h+var_B8]; this
0x1800106b5  mov     r8, [rbx+80h]; struct DpDriver *
0x1800106bc  mov     rdx, rdi; HDC
0x1800106bf  call    ??0SetupClippingForMetafilePlayback@@QEAA@PEAUHDC__@@PEAVDpDriver@@PEAVDpContext@@H@Z; SetupClippingForMetafilePlayback::SetupClippingForMetafilePlayback(HDC__ *,DpDriver *,DpContext *,int)
0x1800106c4  cmp     [rbp+40h+var_A0], r14d
0x1800106c8  jnz     loc_180010571
0x1800106ce  mov     ecx, [rbp+40h+arg_50]
0x1800106d4  test    ecx, ecx
0x1800106d6  jnz     loc_18001082C
0x1800106dc  lea     edx, [rcx+2]; iMode
0x1800106df  mov     rcx, rdi; hdc
0x1800106e2  call    cs:__imp_SetGraphicsMode
0x1800106e8  movups  xmm0, xmmword ptr [rsi+1498h]
0x1800106ef  lea     rdx, [rbp+40h+xf]; lpxf
0x1800106f3  mov     rcx, rdi; hdc
0x1800106f6  movss   xmm1, dword ptr [rsi+14ACh]
0x1800106fe  movups  xmmword ptr [rbp+40h+xf.eM11], xmm0
0x180010702  movss   xmm0, dword ptr [rsi+14A8h]
0x18001070a  movss   [rbp+40h+xf.eDx], xmm0
0x18001070f  movss   [rbp+40h+xf.eDy], xmm1
0x180010714  call    cs:__imp_SetWorldTransform
0x18001071a  xorps   xmm0, xmm0
0x18001071d  lea     r9, [rsp+140h+var_108+8]
0x180010722  movups  [rsp+140h+var_E0+8], xmm0
0x180010727  jmp     short loc_18001073B
0x180010729  mov     ecx, [rbp+40h+arg_50]
0x18001072f  lea     r9, [rbp+40h+xf]
0x180010733  test    ecx, ecx
0x180010735  jnz     loc_1800107FC
0x18001073b  mov     [rsp+140h+var_110], r14d
0x180010740  lea     rax, EnumEmfDownLevel
0x180010747  mov     [rsp+140h+var_118], rax
0x18001074c  lea     rax, [rsp+140h+var_E0+8]
0x180010751  mov     r8, qword ptr [rsp+140h+var_E0]
0x180010756  mov     rdx, rdi
0x180010759  mov     rcx, rsi
0x18001075c  mov     [rsp+140h+var_120], rax
0x180010761  call    ?EnumerateEmfRecords@MetafilePlayer@@QEAA?AW4Status@@PEAUHDC__@@PEAUHENHMETAFILE__@@PEBUtagRECT@@2P6AH0PEAUtagHANDLETABLE@@PEBUtagENHMETARECORD@@H_J@ZH@Z; MetafilePlayer::EnumerateEmfRecords(HDC__ *,HENHMETAFILE__ *,tagRECT const *,tagRECT const *,int (*)(HDC__ *,tagHANDLETABLE *,tagENHMETARECORD const *,int,__int64),int)
0x180010766  jmp     loc_18001056E
0x18001076b  movaps  xmm0, xmm1
0x18001076e  roundss xmm0, xmm0, 9
0x180010774  cvttss2si eax, xmm0
0x180010778  jmp     loc_18001032F
0x18001077d  movaps  xmm0, xmm1
0x180010780  roundss xmm0, xmm0, 9
  ... truncated ...
```
