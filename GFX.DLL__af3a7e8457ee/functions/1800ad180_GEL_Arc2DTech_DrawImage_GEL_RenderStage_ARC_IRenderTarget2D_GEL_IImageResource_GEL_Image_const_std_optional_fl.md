# GEL::Arc2DTech::DrawImage(GEL::RenderStage &,ARC::IRenderTarget2D &,GEL::IImageResource &,GEL::Image const *,std::optional<float> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TRect<double> const &,Math::TAffine3x3<double> const &,GEL::WrapMode)

- ea: `0x1800ad180`
- end: `0x1800ae05f`
- name: `?DrawImage@Arc2DTech@GEL@@CAXAEAVRenderStage@2@AEAUIRenderTarget2D@ARC@@AEAUIImageResource@2@PEBVImage@2@AEBV?$optional@M@std@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@AEBU?$TRect@N@Math@@AEBU?$TAffine3x3@N@Math@@W4WrapMode@2@@Z`
- size: `3807`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x1800a8f90`
- `0x1800ac160`

## callees

- `0x180008728`
- `0x18000fa2c`
- `0x18001507c`
- `0x180015b7c`
- `0x180016060`
- `0x180019c78`
- `0x18001ca64`
- `0x18001cbd0`
- `0x18001cd4c`
- `0x18001cee0`
- `0x18001d460`
- `0x180024f30`
- `0x180024f60`
- `0x18004f244`
- `0x18005238c`
- `0x180053330`
- `0x180054560`
- `0x1800573f0`
- `0x18005ffb8`
- `0x1800786fc`
- `0x1800ac098`
- `0x1800ad0d4`
- `0x1800ad180`
- `0x180119434`
- `0x1801828e0`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x1800ad4f2`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800ad50f`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800ad4f2`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1800ad50f`
- `api-ms-win-crt-math-l1-1-0!hypot` at `0x1800ad4ec`
- `api-ms-win-crt-math-l1-1-0!hypot` at `0x1800ad509`
- `api-ms-win-crt-math-l1-1-0!hypot` at `0x1800ad4ec`
- `api-ms-win-crt-math-l1-1-0!hypot` at `0x1800ad509`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800ad34a`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800ad34a`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800adedf`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800adedf`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800adb60`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800ade40`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800adb60`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800ade40`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800adad8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800adad8`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall GEL::Arc2DTech::DrawImage(
        GEL *a1,
        GEL *a2,
        const struct ARC::IPlatformBitmap *a3,
        const struct GEL::RenderStage *a4,
        __int64 a5,
        Gfx::Rect *a6,
        __int64 a7,
        double *a8,
        char a9)
{
  double *v11; // rcx
  unsigned __int64 v12; // r13
  unsigned int v13; // ebx
  unsigned int v14; // edi
  unsigned int v15; // r12d
  int v16; // eax
  const struct ARC::IPlatformBitmap *v18; // rcx
  struct ARC::IRenderTarget2D *v19; // rdx
  unsigned int v20; // edx
  unsigned int v21; // eax
  struct ARC::IRenderTarget2D *v22; // rcx
  struct ARC::IRenderTarget2D *v23; // rsi
  double Width; // xmm0_8
  double v25; // xmm3_8
  double v26; // xmm9_8
  double v27; // xmm2_8
  double v28; // xmm10_8
  double v29; // xmm6_8
  double v30; // xmm7_8
  __int64 v31; // rdx
  double Height; // xmm0_8
  double v33; // xmm9_8
  double v34; // xmm10_8
  double v35; // xmm0_8
  unsigned int v36; // esi
  double v37; // xmm0_8
  __int64 v38; // r15
  struct GEL::IImageResource *v39; // rsi
  const struct GEL::MipmappableImageProps *v40; // r15
  const struct Image *v41; // r8
  unsigned __int64 v42; // rdx
  unsigned int v43; // r8d
  const struct ARC::IPlatformBitmap *v44; // rsi
  struct GEL::IImageResource *v45; // r14
  GEL::RenderStage::Frame *v46; // rax
  struct GEL::IDeviceResource *v47; // rax
  int v48; // edx
  unsigned int v49; // eax
  unsigned int v50; // rcx^4
  unsigned __int64 v51; // r8
  unsigned __int8 j; // r11
  unsigned __int8 v53; // r11
  int v54; // eax
  unsigned int v55; // r11d
  unsigned __int8 v56; // si
  bool v57; // al
  struct GEL::IImageResource *v58; // rcx
  unsigned __int8 k; // cl
  char v60; // cl
  unsigned int v61; // eax
  int v62; // r14d
  __int64 v63; // rdx
  int v64; // eax
  int v65; // eax
  __int64 v66; // rdx
  double *v67; // rcx
  int v68; // r12d
  double *v69; // r13
  __int64 v70; // xmm4_8
  __int128 *v71; // rcx
  void *v72; // r12
  float *v73; // rax
  double *v74; // rcx
  __int64 v75; // rdx
  unsigned int v76; // ebx
  __int64 v77; // rax
  float *v78; // rcx
  __int64 v79; // rdx
  void *v80; // rdx
  struct ARC::IRenderTarget2D *v81; // rcx
  GEL::MipmappableImageProps *v82; // rax
  struct GEL::IImageResource *v83; // rcx
  unsigned __int8 i; // dl
  char v85; // dl
  GEL::RenderStage::Frame *CurrentFrame; // rax
  struct GEL::IDeviceResource *Resource; // rax
  int v88; // eax
  __int64 v89; // r8
  struct GEL::IImageResource *v90; // rax
  int v91; // r8d
  unsigned int v92; // edx
  int v93; // eax
  unsigned __int64 v94; // rax
  unsigned int *v95; // rax
  struct ARC::IRenderTarget2D **v96; // rax
  struct ARC::IRenderTarget2D *v97; // rsi
  unsigned __int64 v98; // rcx
  struct ARC::IRenderTarget2D *v99; // rcx
  __int64 v100; // rax
  float *v101; // rcx
  double *v102; // rdx
  __int64 v103; // r8
  struct ARC::IBitmap *v104; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v105[8]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int64 v106; // [rsp+50h] [rbp-B8h] BYREF
  struct GEL::IImageResource *v107; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v108; // [rsp+60h] [rbp-A8h] BYREF
  struct ARC::IRenderTarget2D *v109; // [rsp+68h] [rbp-A0h] BYREF
  struct ARC::IRenderTarget2D *v110; // [rsp+70h] [rbp-98h] BYREF
  void *v111; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v112; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v113; // [rsp+88h] [rbp-80h]
  unsigned int v114; // [rsp+8Ch] [rbp-7Ch]
  struct GEL::IImageResource *v115; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v116; // [rsp+98h] [rbp-70h]
  __int64 v117; // [rsp+A0h] [rbp-68h] BYREF
  float v118; // [rsp+A8h] [rbp-60h]
  float v119; // [rsp+ACh] [rbp-5Ch]
  struct GEL::IImageResource *v120; // [rsp+B0h] [rbp-58h]
  __int64 v121; // [rsp+B8h] [rbp-50h]
  __int64 v122; // [rsp+C0h] [rbp-48h] BYREF
  struct GEL::IImageResource *v123; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v124[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v125; // [rsp+F8h] [rbp-10h] BYREF
  char v126; // [rsp+108h] [rbp+0h]
  __int64 v127; // [rsp+10Ch] [rbp+4h]
  unsigned int v128; // [rsp+118h] [rbp+10h] BYREF
  unsigned int v129; // [rsp+11Ch] [rbp+14h]
  _BYTE v130[112]; // [rsp+120h] [rbp+18h] BYREF

  if ( Gfx::Rect::FIsEmpty(a6) || *v11 < 0.0 || v11[1] < 0.0 )
  {
    MsoShipAssertTagProc(18990033);
    return;
  }
  Math::snap_outward_cast<Math::TUnits<unsigned int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(
    &v112,
    v11);
  LODWORD(v12) = v114;
  v13 = HIDWORD(v112);
  v14 = v112;
  v15 = v113;
  if ( (unsigned int)v112 > v113 || HIDWORD(v112) > v114 )
    v16 = 0;
  else
    v16 = v113 - v112;
  if ( v16 )
  {
    if ( (unsigned int)v112 > v113 || HIDWORD(v112) > v114 ? 0 : v114 - HIDWORD(v112) )
    {
      if ( a3 )
      {
        _castguard_slow_path_check_user_handled(*(_QWORD *)a3, 73112, 0);
        v18 = a3;
      }
      else
      {
        v18 = 0;
      }
      LOBYTE(v104) = 0;
      (*(void (__fastcall **)(const struct ARC::IPlatformBitmap *, struct ARC::IRenderTarget2D **))(*(_QWORD *)v18
                                                                                                  + 344LL))(
        v18,
        &v109);
      memset(v124, 0, sizeof(v124));
      (*(void (__fastcall **)(const struct ARC::IPlatformBitmap *, struct GEL::IImageResource **))(*(_QWORD *)a3 + 48LL))(
        a3,
        &v115);
      if ( v14 || v13 || (struct GEL::IImageResource *)__PAIR64__(v12, v15) != v115 )
      {
        if ( v14 > v15 || v13 > (unsigned int)v12 )
          v20 = 0;
        else
          v20 = v15 - v14;
        if ( (unsigned int)v115 < v20 )
          v20 = (unsigned int)v115;
        if ( v14 > v15 || v13 > (unsigned int)v12 )
          v21 = 0;
        else
          v21 = v12 - v13;
        if ( HIDWORD(v115) < v21 )
          v21 = HIDWORD(v115);
        v112 = __PAIR64__(v13, v14);
        v113 = v20 + v14;
        v114 = v13 + v21;
        ARC::IPlatformBitmapClipper::Create(&v110, v109, &v112);
        if ( (_DWORD)v115 && HIDWORD(v115) )
        {
          *(double *)v124 = (double)(int)v14 / (double)(int)v115;
          *(double *)&v124[1] = 1.0 - (double)(int)v15 / (double)(int)v115;
          *((double *)v124 + 1) = (double)(int)v13 / (double)SHIDWORD(v115);
          *((double *)&v124[1] + 1) = 1.0 - (double)(int)v12 / (double)SHIDWORD(v115);
        }
        if ( (unsigned int)v112 > v113 || HIDWORD(v112) > v114 )
        {
          v111 = 0;
        }
        else
        {
          LODWORD(v111) = v113 - v112;
          HIDWORD(v111) = v114 - HIDWORD(v112);
        }
        v15 = (unsigned int)v111;
        v14 = 0;
        v13 = 0;
        v12 = (unsigned __int64)v111 >> 32;
        v22 = v110;
        v23 = v110;
        v19 = v109;
        if ( v109 != v110 )
        {
          if ( v110 )
          {
            (**(void (***)(void))v110)();
            v19 = v109;
            v22 = v110;
          }
          if ( v19 )
          {
            v109 = 0;
            (*(void (__fastcall **)(struct ARC::IRenderTarget2D *))(*(_QWORD *)v19 + 8LL))(v19);
            v22 = v110;
          }
          v109 = v23;
        }
        if ( v22 )
        {
          v110 = 0;
          (*(void (__fastcall **)(struct ARC::IRenderTarget2D *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      Width = Math::TRect<double>::GetWidth(a7, v19);
      v25 = *a8;
      v26 = a8[2];
      v27 = a8[1];
      v28 = a8[3];
      v29 = *a8 * Width + v26 * 0.0;
      v30 = v27 * Width + v28 * 0.0;
      Height = Math::TRect<double>::GetHeight(a7, v31);
      v33 = v26 * Height + v25 * 0.0;
      v34 = v28 * Height + v27 * 0.0;
      v35 = hypot(v29, v30);
      v36 = (int)round(v35);
      v121 = v36;
      v37 = hypot(v33, v34);
      v38 = (unsigned int)(int)round(v37);
      v117 = v38;
      if ( v36 && (v39 = 0, (_DWORD)v38) )
      {
        v111 = (void *)(*(__int64 (__fastcall **)(GEL *))(*(_QWORD *)a2 + 24LL))(a2);
        v120 = 0;
        v106 = __PAIR64__(v38, v121);
        v40 = 0;
        v110 = 0;
        v112 = 0;
        if ( !GEL::ShouldCacheImage(a1, a4, v41) )
          goto LABEL_44;
        v82 = (GEL::MipmappableImageProps *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v42, v43);
        v108 = (unsigned __int64)v82;
        if ( v82 )
        {
          v40 = (const struct GEL::MipmappableImageProps *)GEL::MipmappableImageProps::MipmappableImageProps(
                                                             v82,
                                                             a4,
                                                             0,
                                                             (const struct GEL::CropInfo *)v124,
                                                             0);
          v110 = v40;
        }
        else
        {
          v40 = 0;
          v110 = 0;
        }
        v112 = (unsigned __int64)v40;
        (*(void (__fastcall **)(GEL *))(*(_QWORD *)a2 + 24LL))(a2);
        ARC::TRef<ARC::ISwapChain>::TRef<ARC::ISwapChain>(v124);
        GEL::MipmappableImageProps::MipmappableImageProps((GEL::MipmappableImageProps *)((char *)v124 + 8), v40);
        v83 = v115;
        *((_QWORD *)&v125 + 1) = v115;
        for ( i = 0; i < 6u; ++i )
        {
          if ( (unsigned int)v83 < 0x40 || HIDWORD(v83) < 0x40 )
          {
            v85 = i + 1;
            goto LABEL_125;
          }
          LODWORD(v107) = (unsigned int)((_DWORD)v83 + 1) >> 1;
          HIDWORD(v107) = (unsigned int)(HIDWORD(v83) + 1) >> 1;
          v83 = v107;
        }
        v85 = 6;
LABEL_125:
        v126 = v85;
        v127 = 0;
        CurrentFrame = (GEL::RenderStage::Frame *)GEL::RenderStage::GetCurrentFrame(a1);
        Resource = GEL::RenderStage::Frame::GetResource(CurrentFrame);
        v105[0] = 0;
        v88 = (*(__int64 (__fastcall **)(struct GEL::IDeviceResource *, unsigned __int64 *))(*(_QWORD *)Resource + 96LL))(
                Resource,
                &v108);
        GEL::ImageMipmapManager::ComputeMipSizeAndLevel(
          v88,
          (unsigned int)&v125 + 8,
          (unsigned int)&v106,
          (unsigned int)&v123,
          (__int64)v105);
        LOBYTE(v89) = v105[0];
        GEL::ImageMipmapManager::GetMipBitmapForLevel(v124, &v107, v89);
        v90 = v107;
        if ( v107 )
        {
          v107 = 0;
          v39 = v90;
          v120 = v90;
        }
        if ( v39 )
        {
          v95 = (unsigned int *)(*(__int64 (__fastcall **)(struct GEL::IImageResource *, unsigned __int64 *))(*(_QWORD *)v39 + 64LL))(
                                  v39,
                                  &v108);
          v14 = 0;
          v13 = 0;
          v15 = *v95;
          LODWORD(v12) = v95[1];
        }
        GEL::MipmappableImageProps::~MipmappableImageProps((GEL::MipmappableImageProps *)((char *)v124 + 8));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v124[0] + 8LL))(*(_QWORD *)&v124[0]);
        if ( !v39 )
        {
LABEL_44:
          v44 = a3;
          _castguard_slow_path_check_user_handled(*(_QWORD *)a3, 73112, 0);
          if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IPlatformBitmap *))(*(_QWORD *)v44 + 416LL))(v44) )
          {
            (*(void (__fastcall **)(void *, struct GEL::IImageResource **))(*(_QWORD *)v111 + 408LL))(v111, &v107);
            GEL::CreateBitmapFromPlatformBitmap(a2, v109, a3, v107, v104);
            v58 = v107;
            v39 = v107;
            if ( v107 )
            {
              (**(void (__fastcall ***)(struct GEL::IImageResource *))v107)(v107);
              v58 = v107;
            }
            v120 = v39;
          }
          else
          {
            if ( v14 > v15 || v13 > (unsigned int)v12 )
            {
              v107 = 0;
            }
            else
            {
              LODWORD(v107) = v15 - v14;
              HIDWORD(v107) = v12 - v13;
            }
            v45 = v107;
            v108 = (unsigned __int64)v107;
            v123 = v107;
            v46 = (GEL::RenderStage::Frame *)GEL::RenderStage::GetCurrentFrame(a1);
            v47 = GEL::RenderStage::Frame::GetResource(v46);
            (*(void (__fastcall **)(struct GEL::IDeviceResource *, unsigned int *))(*(_QWORD *)v47 + 96LL))(v47, &v128);
            v105[0] = 0;
            v106 = (unsigned __int64)v45;
            v48 = (int)v45;
            if ( v128 < (unsigned int)v45 )
              v48 = v128;
            LODWORD(v106) = v48;
            v49 = HIDWORD(v106);
            if ( v129 < HIDWORD(v106) )
              v49 = v129;
            HIDWORD(v106) = v49;
            v50 = v49;
            v51 = v106;
            for ( j = 0; j < 6u; ++j )
            {
              if ( (unsigned int)v51 < 0x40 || HIDWORD(v51) < 0x40 )
              {
                v53 = j + 1;
                goto LABEL_60;
              }
              LODWORD(v116) = (unsigned int)(v51 + 1) >> 1;
              HIDWORD(v116) = (unsigned int)(HIDWORD(v51) + 1) >> 1;
              v51 = v116;
            }
            v53 = 6;
LABEL_60:
            v54 = v53;
            if ( v53 > 1u )
            {
              v55 = v53 - 1;
              if ( v54 != 1 )
              {
                v56 = v105[0];
                while ( v48 > v128
                     || v50 > v129
                     || (float)((float)(int)v121 / (float)v48) <= 0.5
                     && (float)((float)(int)v117 / (float)(int)v50) <= 0.5 )
                {
                  LODWORD(v116) = (unsigned int)(v48 + 1) >> 1;
                  v50 = (v50 + 1) >> 1;
                  HIDWORD(v116) = v50;
                  v106 = v116;
                  if ( ++v56 >= v55 )
                    break;
                  v48 = v106;
                }
                v105[0] = v56;
                v45 = v123;
                v40 = v110;
                v44 = a3;
              }
            }
            v57 = v105[0] != 0;
            if ( !v105[0] && ((unsigned int)v45 > v128 || HIDWORD(v108) > v129) )
            {
              v91 = v129 / HIDWORD(v108);
              if ( v129 / HIDWORD(v108) >= v128 / (unsigned int)v45 )
                v91 = v128 / (unsigned int)v45;
              v92 = (int)((double)(int)v45 * (double)v91);
              if ( !v92 )
                v92 = 1;
              v93 = (int)((double)SHIDWORD(v108) * (double)v91);
              if ( !v93 )
                v93 = 1;
              v108 = __PAIR64__(v93, v92);
              if ( v128 < v92 )
                v92 = v128;
              v94 = HIDWORD(v108);
              if ( v129 < HIDWORD(v108) )
                LODWORD(v94) = v129;
              v108 = __PAIR64__(v94, v92);
              v106 = __PAIR64__(v94, v92);
              v57 = 1;
            }
            if ( v57
              && (*(unsigned int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)a1 + 21) + 256LL) + 56LL))(
                   *(_QWORD *)(*((_QWORD *)a1 + 21) + 256LL),
                   3) == 3 )
            {
              LODWORD(v110) = 3;
              v96 = (struct ARC::IRenderTarget2D **)ARC::IPlatformBitmapScaler::Create(&v108, v109, &v106, &v110);
              v97 = *v96;
              *v96 = 0;
              v98 = v108;
              if ( v108 )
              {
                v108 = 0;
                (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v98 + 8LL))(v98);
              }
              v14 = 0;
              v13 = 0;
              v15 = v106;
              LODWORD(v12) = HIDWORD(v106);
              v99 = v109;
              if ( v109 != v97 )
              {
                if ( v97 )
                {
                  (**(void (__fastcall ***)(struct ARC::IRenderTarget2D *))v97)(v97);
                  v99 = v109;
                }
                if ( v99 )
                {
                  v109 = 0;
                  (*(void (__fastcall **)(struct ARC::IRenderTarget2D *))(*(_QWORD *)v99 + 8LL))(v99);
                }
                v109 = v97;
              }
              if ( v97 )
                (*(void (__fastcall **)(struct ARC::IRenderTarget2D *))(*(_QWORD *)v97 + 8LL))(v97);
              v44 = a3;
            }
            (*(void (__fastcall **)(void *, struct GEL::IImageResource **))(*(_QWORD *)v111 + 408LL))(v111, &v107);
            GEL::CreateBitmapFromPlatformBitmap(a2, v109, v44, v107, v104);
            v58 = v107;
            v39 = v107;
            if ( v107 )
            {
              (**(void (__fastcall ***)(struct GEL::IImageResource *))v107)(v107);
              v58 = v107;
            }
            v120 = v39;
            if ( v40 )
            {
              (*(void (__fastcall **)(GEL *))(*(_QWORD *)a2 + 24LL))(a2);
              ARC::TRef<ARC::ISwapChain>::TRef<ARC::ISwapChain>(v124);
              GEL::MipmappableImageProps::MipmappableImageProps((GEL::MipmappableImageProps *)((char *)v124 + 8), v40);
              *((_QWORD *)&v125 + 1) = v45;
              for ( k = 0; k < 6u; ++k )
              {
                if ( (unsigned int)v45 < 0x40 || HIDWORD(v45) < 0x40 )
                {
                  v60 = k + 1;
                  goto LABEL_80;
                }
                LODWORD(v108) = (unsigned int)((_DWORD)v45 + 1) >> 1;
                HIDWORD(v108) = (unsigned int)(HIDWORD(v45) + 1) >> 1;
                v45 = (struct GEL::IImageResource *)v108;
              }
              v60 = 6;
LABEL_80:
              v126 = v60;
              v127 = 0;
              GEL::ImageMipmapManager::CacheMipLevel((GEL::ImageMipmapManager *)v124, v39, v105[0]);
              GEL::MipmappableImageProps::~MipmappableImageProps((GEL::MipmappableImageProps *)((char *)v124 + 8));
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v124[0] + 8LL))(*(_QWORD *)&v124[0]);
              v58 = v107;
            }
          }
          if ( v58 )
            (*(void (__fastcall **)(struct GEL::IImageResource *))(*(_QWORD *)v58 + 8LL))(v58);
        }
        LODWORD(v110) = 0;
        LODWORD(v106) = 0;
        LOBYTE(v58) = a9;
        GEL::Arc2DTech::WrapModeToARCExtendMode(v58, &v110, &v106);
        v61 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)a1 + 21) + 256LL) + 56LL))(
                *(_QWORD *)(*((_QWORD *)a1 + 21) + 256LL),
                1);
        v62 = Gfx::ImageRenderQualityToARCInterpolationMode(v61);
        v63 = 0;
        if ( v62 )
        {
          v64 = v14 > v15 || v13 > (unsigned int)v12 ? 0 : v15 - v14;
          if ( v64 == (_DWORD)v121 )
          {
            v65 = v14 > v15 || v13 > (unsigned int)v12 ? 0 : v12 - v13;
            if ( v65 == (_DWORD)v117
              && (unsigned __int8)Math::TAffine3x3<double>::IsUpright(a8)
              && v29 * v34 - v30 * v33 > 0.0 )
            {
              v62 = v63;
            }
          }
        }
        Math::TRect<double>::GetHeight(a7, v63);
        if ( v14 > v15 || v13 > (unsigned int)v12 )
          v68 = v66;
        else
          v68 = v15 - v14;
        v69 = v67;
        *(double *)v124 = Math::TRect<double>::GetWidth(v67, v66) / (double)v68;
        *(_OWORD *)((char *)v124 + 8) = 0;
        *((_QWORD *)&v124[1] + 1) = v70;
        v125 = *v71;
        v72 = v111;
        (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)v111 + 488LL))(v111, &v122);
        v73 = (float *)v130;
        v74 = (double *)v124;
        v75 = 6;
        do
        {
          *v73++ = *v74++;
          --v75;
        }
        while ( v75 );
        ARC::IRenderTarget2D::CreateBitmapBrush(
          (_DWORD)a2,
          v122,
          (_DWORD)v39,
          v62,
          (__int64)v130,
          LODWORD(FLOAT_1_0),
          (_DWORD)v110,
          v106);
        if ( BYTE7(xmmword_18051FD70) )
        {
          LODWORD(v106) = 0;
          v76 = 0;
        }
        else
        {
          v76 = HIDWORD(xmmword_18051FD60);
        }
        if ( HIBYTE(v76) )
        {
          (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v72 + 456LL))(v72, &v111);
          *(float *)&v117 = (float)BYTE2(v76) / 255.0;
          *((float *)&v117 + 1) = (float)BYTE1(v76) / 255.0;
          v118 = (float)(unsigned __int8)v76 / 255.0;
          v119 = (float)HIBYTE(v76) / 255.0;
          ARC::IRenderTarget2D::CreateSolidColorBrush(a2, v111, &v117);
          v100 = *(_QWORD *)a2;
          v101 = (float *)&v117;
          v102 = v69;
          v103 = 4;
          do
          {
            *v101++ = *v102++;
            --v103;
          }
          while ( v103 );
          (*(void (__fastcall **)(GEL *, __int64 *, void *))(v100 + 200))(a2, &v117, v111);
          ARC::TPtr<ARC::IMultisampleRenderTarget>::~TPtr<ARC::IMultisampleRenderTarget>(&v111);
        }
        v77 = *(_QWORD *)a2;
        v78 = (float *)&v117;
        v79 = 4;
        do
        {
          *v78++ = *v69++;
          --v79;
        }
        while ( v79 );
        (*(void (__fastcall **)(GEL *, __int64 *, __int64))(v77 + 200))(a2, &v117, v122);
        if ( v122 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 8LL))(v122);
        if ( v40 )
        {
          GEL::MipmappableImageProps::~MipmappableImageProps(v40);
          Mso::Memory::Free(v40, v80);
        }
        if ( v39 )
          (*(void (__fastcall **)(struct GEL::IImageResource *))(*(_QWORD *)v39 + 8LL))(v39);
        v81 = v109;
        if ( v109 )
        {
          v109 = 0;
LABEL_111:
          (*(void (__fastcall **)(struct ARC::IRenderTarget2D *))(*(_QWORD *)v81 + 8LL))(v81);
        }
      }
      else
      {
        MsoShipAssertTagProc(18990035);
        v81 = v109;
        if ( v109 )
        {
          v109 = 0;
          goto LABEL_111;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800ad180  mov     rax, rsp
0x1800ad183  mov     [rax+20h], r9
0x1800ad187  mov     [rax+18h], r8
0x1800ad18b  mov     [rax+10h], rdx
0x1800ad18f  mov     [rax+8], rcx
0x1800ad193  push    rbp
0x1800ad194  push    rbx
0x1800ad195  push    rsi
0x1800ad196  push    rdi
0x1800ad197  push    r12
0x1800ad199  push    r13
0x1800ad19b  push    r14
0x1800ad19d  push    r15
0x1800ad19f  lea     rbp, [rax-0C8h]
0x1800ad1a6  sub     rsp, 188h
0x1800ad1ad  movaps  xmmword ptr [rax-58h], xmm6
0x1800ad1b1  movaps  xmmword ptr [rax-68h], xmm7
0x1800ad1b5  movaps  xmmword ptr [rax-78h], xmm8
0x1800ad1ba  movaps  xmmword ptr [rax-88h], xmm9
0x1800ad1c2  movaps  xmmword ptr [rax-98h], xmm10
0x1800ad1ca  mov     rsi, r8
0x1800ad1cd  mov     r14, rdx
0x1800ad1d0  xor     r15d, r15d
0x1800ad1d3  mov     rcx, [rbp+0C0h+arg_28]; this
0x1800ad1da  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x1800ad1df  test    al, al
0x1800ad1e1  jnz     loc_1800ADE3B
0x1800ad1e7  xorps   xmm8, xmm8
0x1800ad1eb  comisd  xmm8, qword ptr [rcx]
0x1800ad1f0  ja      loc_1800ADE3B
0x1800ad1f6  comisd  xmm8, qword ptr [rcx+8]
0x1800ad1fc  ja      loc_1800ADE3B
0x1800ad202  mov     rdx, rcx
0x1800ad205  lea     rcx, [rsp+1C0h+var_148]
0x1800ad20a  call    ??$snap_outward_cast@V?$TUnits@IUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<uint,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800ad20f  mov     r13d, [rbp+0C0h+var_13C]
0x1800ad213  mov     ebx, dword ptr [rsp+1C0h+var_148+4]
0x1800ad217  mov     edi, dword ptr [rsp+1C0h+var_148]
0x1800ad21b  mov     r12d, [rbp+0C0h+var_140]
0x1800ad21f  cmp     edi, r12d
0x1800ad222  ja      loc_1800AD68D
0x1800ad228  cmp     ebx, r13d
0x1800ad22b  ja      loc_1800AD68D
0x1800ad231  mov     eax, r12d
0x1800ad234  sub     eax, edi
0x1800ad236  test    eax, eax
0x1800ad238  jz      loc_1800ADB11
0x1800ad23e  cmp     edi, r12d
0x1800ad241  ja      loc_1800AD695
0x1800ad247  cmp     ebx, r13d
0x1800ad24a  ja      loc_1800AD695
0x1800ad250  mov     eax, r13d
0x1800ad253  sub     eax, ebx
0x1800ad255  test    eax, eax
0x1800ad257  jz      loc_1800ADB11
0x1800ad25d  test    rsi, rsi
0x1800ad260  jz      loc_1800ADB51
0x1800ad266  xor     r8d, r8d
0x1800ad269  mov     edx, 11D98h
0x1800ad26e  mov     rcx, [rsi]
0x1800ad271  call    __castguard_slow_path_check_user_handled
0x1800ad276  mov     rcx, rsi
0x1800ad279  mov     rax, [rcx]
0x1800ad27c  mov     r8, [rax+158h]
0x1800ad283  mov     rax, [rbp+0C0h+arg_20]
0x1800ad28a  mov     r9b, [rax+4]
0x1800ad28e  test    r9b, r9b
0x1800ad291  jz      loc_1800AD685
0x1800ad297  movss   xmm2, dword ptr [rax]
0x1800ad29b  mov     byte ptr [rsp+1C0h+var_1A0], r15b; struct ARC::IBitmap *
0x1800ad2a0  lea     rdx, [rsp+1C0h+var_160]
0x1800ad2a5  mov     rax, r8
0x1800ad2a8  call    cs:__guard_dispatch_icall_fptr
0x1800ad2ae  nop
0x1800ad2af  xorps   xmm0, xmm0
0x1800ad2b2  movups  [rbp+0C0h+var_F0], xmm0
0x1800ad2b6  xorps   xmm1, xmm1
0x1800ad2b9  movups  [rbp+0C0h+var_E0], xmm1
0x1800ad2bd  mov     rax, [rsi]
0x1800ad2c0  lea     rdx, [rbp+0C0h+var_138]
0x1800ad2c4  mov     rcx, rsi
0x1800ad2c7  mov     rax, [rax+30h]
0x1800ad2cb  call    cs:__guard_dispatch_icall_fptr
0x1800ad2d1  mov     rax, [rbp+0C0h+var_138]
0x1800ad2d5  mov     ecx, dword ptr [rbp+0C0h+var_138+4]
0x1800ad2d8  test    edi, edi
0x1800ad2da  jnz     short loc_1800AD2EE
0x1800ad2dc  test    ebx, ebx
0x1800ad2de  jnz     short loc_1800AD2EE
0x1800ad2e0  cmp     r12d, eax
0x1800ad2e3  jnz     short loc_1800AD2EE
0x1800ad2e5  cmp     r13d, ecx
0x1800ad2e8  jz      loc_1800AD46C
0x1800ad2ee  cmp     edi, r12d
0x1800ad2f1  ja      loc_1800ADCE1
0x1800ad2f7  cmp     ebx, r13d
0x1800ad2fa  ja      loc_1800ADCE1
0x1800ad300  mov     edx, r12d
0x1800ad303  sub     edx, edi
0x1800ad305  cmp     eax, edx
0x1800ad307  cmovb   edx, eax
0x1800ad30a  lea     r8d, [rdx+rdi]
0x1800ad30e  cmp     edi, r12d
0x1800ad311  ja      loc_1800ADCE9
0x1800ad317  cmp     ebx, r13d
0x1800ad31a  ja      loc_1800ADCE9
0x1800ad320  mov     eax, r13d
0x1800ad323  sub     eax, ebx
0x1800ad325  cmp     ecx, eax
0x1800ad327  cmovb   eax, ecx
0x1800ad32a  mov     dword ptr [rsp+1C0h+var_148], edi
0x1800ad32e  mov     dword ptr [rsp+1C0h+var_148+4], ebx
0x1800ad332  mov     [rbp+0C0h+var_140], r8d
0x1800ad336  add     eax, ebx
0x1800ad338  mov     [rbp+0C0h+var_13C], eax
0x1800ad33b  lea     r8, [rsp+1C0h+var_148]
0x1800ad340  mov     rdx, [rsp+1C0h+var_160]
0x1800ad345  lea     rcx, [rsp+1C0h+var_158]
0x1800ad34a  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800ad350  mov     rcx, [rbp+0C0h+var_138]
0x1800ad354  test    ecx, ecx
0x1800ad356  jz      short loc_1800AD3C8
0x1800ad358  mov     eax, dword ptr [rbp+0C0h+var_138+4]
0x1800ad35b  test    eax, eax
0x1800ad35d  jz      short loc_1800AD3C8
0x1800ad35f  xorps   xmm0, xmm0
0x1800ad362  cvtsi2sd xmm0, rdi
0x1800ad367  mov     edx, ecx
0x1800ad369  xorps   xmm2, xmm2
0x1800ad36c  cvtsi2sd xmm2, rdx
0x1800ad371  divsd   xmm0, xmm2
0x1800ad375  movsd   qword ptr [rbp+0C0h+var_F0], xmm0
0x1800ad37a  xorps   xmm1, xmm1
0x1800ad37d  cvtsi2sd xmm1, r12
0x1800ad382  divsd   xmm1, xmm2
0x1800ad386  movsd   xmm3, cs:__real@3ff0000000000000
0x1800ad38e  movaps  xmm0, xmm3
0x1800ad391  subsd   xmm0, xmm1
0x1800ad395  movsd   qword ptr [rbp+0C0h+var_E0], xmm0
0x1800ad39a  xorps   xmm1, xmm1
0x1800ad39d  cvtsi2sd xmm1, rbx
0x1800ad3a2  xorps   xmm2, xmm2
0x1800ad3a5  cvtsi2sd xmm2, rax
0x1800ad3aa  divsd   xmm1, xmm2
0x1800ad3ae  movsd   qword ptr [rbp+0C0h+var_F0+8], xmm1
0x1800ad3b3  xorps   xmm0, xmm0
0x1800ad3b6  cvtsi2sd xmm0, r13
0x1800ad3bb  divsd   xmm0, xmm2
0x1800ad3bf  subsd   xmm3, xmm0
0x1800ad3c3  movsd   qword ptr [rbp+0C0h+var_E0+8], xmm3
0x1800ad3c8  mov     eax, [rbp+0C0h+var_140]
0x1800ad3cb  cmp     dword ptr [rsp+1C0h+var_148], eax
0x1800ad3cf  ja      loc_1800ADCF1
0x1800ad3d5  mov     ecx, [rbp+0C0h+var_13C]
0x1800ad3d8  cmp     dword ptr [rsp+1C0h+var_148+4], ecx
0x1800ad3dc  ja      loc_1800ADCF1
0x1800ad3e2  sub     eax, dword ptr [rsp+1C0h+var_148]
0x1800ad3e6  mov     dword ptr [rsp+1C0h+var_150], eax
0x1800ad3ea  sub     ecx, dword ptr [rsp+1C0h+var_148+4]
0x1800ad3ee  mov     dword ptr [rsp+1C0h+var_150+4], ecx
0x1800ad3f2  mov     r12, [rsp+1C0h+var_150]
0x1800ad3f7  mov     edi, r15d
0x1800ad3fa  mov     ebx, r15d
0x1800ad3fd  mov     r13, r12
0x1800ad400  shr     r13, 20h
0x1800ad404  mov     rcx, [rsp+1C0h+var_158]
0x1800ad409  mov     rsi, rcx
0x1800ad40c  mov     rdx, [rsp+1C0h+var_160]
0x1800ad411  cmp     rdx, rcx
0x1800ad414  jz      short loc_1800AD455
0x1800ad416  test    rcx, rcx
0x1800ad419  jz      short loc_1800AD431
0x1800ad41b  mov     rax, [rcx]
0x1800ad41e  mov     rax, [rax]
0x1800ad421  call    cs:__guard_dispatch_icall_fptr
0x1800ad427  mov     rdx, [rsp+1C0h+var_160]
0x1800ad42c  mov     rcx, [rsp+1C0h+var_158]
0x1800ad431  test    rdx, rdx
0x1800ad434  jz      short loc_1800AD450
0x1800ad436  mov     [rsp+1C0h+var_160], r15
0x1800ad43b  mov     rax, [rdx]
0x1800ad43e  mov     rcx, rdx
0x1800ad441  mov     rax, [rax+8]
0x1800ad445  call    cs:__guard_dispatch_icall_fptr
0x1800ad44b  mov     rcx, [rsp+1C0h+var_158]
0x1800ad450  mov     [rsp+1C0h+var_160], rsi
0x1800ad455  test    rcx, rcx
0x1800ad458  jz      short loc_1800AD46C
0x1800ad45a  mov     [rsp+1C0h+var_158], r15
0x1800ad45f  mov     rax, [rcx]
0x1800ad462  mov     rax, [rax+8]
0x1800ad466  call    cs:__guard_dispatch_icall_fptr
0x1800ad46c  mov     rcx, [rbp+0C0h+arg_30]
0x1800ad473  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x1800ad478  mov     rcx, [rbp+0C0h+arg_38]
0x1800ad47f  movsd   xmm3, qword ptr [rcx]
0x1800ad483  movsd   xmm9, qword ptr [rcx+10h]
0x1800ad489  movsd   xmm2, qword ptr [rcx+8]
0x1800ad48e  movsd   xmm10, qword ptr [rcx+18h]
0x1800ad494  movaps  xmm6, xmm3
0x1800ad497  mulsd   xmm6, xmm0
0x1800ad49b  movaps  xmm1, xmm9
0x1800ad49f  mulsd   xmm1, xmm8
0x1800ad4a4  addsd   xmm6, xmm1
0x1800ad4a8  movaps  xmm7, xmm2
0x1800ad4ab  mulsd   xmm7, xmm0
0x1800ad4af  movaps  xmm0, xmm10
0x1800ad4b3  mulsd   xmm0, xmm8
0x1800ad4b8  addsd   xmm7, xmm0
0x1800ad4bc  mov     rcx, [rbp+0C0h+arg_30]
0x1800ad4c3  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x1800ad4c8  mulsd   xmm9, xmm0
0x1800ad4cd  mulsd   xmm3, xmm8
0x1800ad4d2  addsd   xmm9, xmm3
0x1800ad4d7  mulsd   xmm10, xmm0
0x1800ad4dc  mulsd   xmm2, xmm8
0x1800ad4e1  addsd   xmm10, xmm2
0x1800ad4e6  movaps  xmm1, xmm7; Y
0x1800ad4e9  movaps  xmm0, xmm6; X
0x1800ad4ec  call    cs:__imp_hypot
0x1800ad4f2  call    cs:__imp_round
0x1800ad4f8  cvttsd2si rsi, xmm0
0x1800ad4fd  mov     [rbp+0C0h+var_110], rsi
0x1800ad501  movaps  xmm1, xmm10; Y
0x1800ad505  movaps  xmm0, xmm9; X
0x1800ad509  call    cs:__imp_hypot
0x1800ad50f  call    cs:__imp_round
0x1800ad515  cvttsd2si r15, xmm0
0x1800ad51a  mov     [rbp+0C0h+var_128], r15
0x1800ad51e  test    esi, esi
0x1800ad520  jz      loc_1800ADB59
0x1800ad526  xor     esi, esi
0x1800ad528  test    r15d, r15d
0x1800ad52b  jz      loc_1800ADB5B
0x1800ad531  mov     rax, [r14]
0x1800ad534  mov     rcx, r14
0x1800ad537  mov     rax, [rax+18h]
0x1800ad53b  call    cs:__guard_dispatch_icall_fptr
0x1800ad541  mov     [rsp+1C0h+var_150], rax
0x1800ad546  mov     [rbp+0C0h+var_118], rsi
0x1800ad54a  mov     rax, [rbp+0C0h+var_110]
0x1800ad54e  mov     dword ptr [rsp+1C0h+var_178], eax
0x1800ad552  mov     dword ptr [rsp+1C0h+var_178+4], r15d
0x1800ad557  xor     r15d, r15d
0x1800ad55a  mov     [rsp+1C0h+var_158], r15
0x1800ad55f  mov     [rsp+1C0h+var_148], r15
0x1800ad564  mov     rdx, [rbp+0C0h+arg_18]; struct GEL::RenderStage *
0x1800ad56b  mov     rcx, [rbp+0C0h+arg_0]; this
0x1800ad572  call    ?ShouldCacheImage@GEL@@YA_NAEBVRenderStage@1@PEBVImage@1@@Z; GEL::ShouldCacheImage(GEL::RenderStage const &,GEL::Image const *)
0x1800ad577  test    al, al
0x1800ad579  jnz     loc_1800ADB77
0x1800ad57f  xor     r8d, r8d
0x1800ad582  mov     edx, 11D98h
0x1800ad587  mov     rsi, [rbp+0C0h+arg_10]
0x1800ad58e  mov     rcx, [rsi]
0x1800ad591  call    __castguard_slow_path_check_user_handled
0x1800ad596  mov     rax, [rsi]
0x1800ad599  mov     rcx, rsi
0x1800ad59c  mov     rax, [rax+1A0h]
0x1800ad5a3  call    cs:__guard_dispatch_icall_fptr
0x1800ad5a9  xor     ecx, ecx
0x1800ad5ab  test    al, al
0x1800ad5ad  jnz     loc_1800ADD09
0x1800ad5b3  cmp     edi, r12d
0x1800ad5b6  ja      loc_1800ADD60
0x1800ad5bc  cmp     ebx, r13d
0x1800ad5bf  ja      loc_1800ADD60
0x1800ad5c5  mov     eax, r12d
0x1800ad5c8  sub     eax, edi
0x1800ad5ca  mov     dword ptr [rsp+1C0h+var_170], eax
0x1800ad5ce  mov     eax, r13d
0x1800ad5d1  sub     eax, ebx
0x1800ad5d3  mov     dword ptr [rsp+1C0h+var_170+4], eax
0x1800ad5d7  mov     r14, [rsp+1C0h+var_170]
0x1800ad5dc  mov     [rsp+1C0h+var_168], r14
0x1800ad5e1  mov     [rbp+0C0h+var_100], r14
0x1800ad5e5  mov     rcx, [rbp+0C0h+arg_0]; this
0x1800ad5ec  call    ?GetCurrentFrame@RenderStage@GEL@@QEAAAEAVFrame@12@XZ; GEL::RenderStage::GetCurrentFrame(void)
0x1800ad5f1  mov     rcx, rax; this
0x1800ad5f4  call    ?GetResource@Frame@RenderStage@GEL@@QEAAAEAUIDeviceResource@3@XZ; GEL::RenderStage::Frame::GetResource(void)
0x1800ad5f9  mov     r8, rax
0x1800ad5fc  mov     rcx, [rax]
0x1800ad5ff  mov     rax, [rcx+60h]
0x1800ad603  lea     rdx, [rbp+0C0h+var_B0]
0x1800ad607  mov     rcx, r8
0x1800ad60a  call    cs:__guard_dispatch_icall_fptr
0x1800ad610  mov     [rsp+1C0h+var_180], 0
0x1800ad615  mov     [rsp+1C0h+var_178], r14
0x1800ad61a  mov     edx, r14d
0x1800ad61d  mov     r9, [rbp+0C0h+var_B0]
0x1800ad621  cmp     r9d, r14d
0x1800ad624  cmovb   edx, r9d
0x1800ad628  mov     dword ptr [rsp+1C0h+var_178], edx
0x1800ad62c  mov     eax, dword ptr [rsp+1C0h+var_178+4]
0x1800ad630  mov     r10d, dword ptr [rbp+0C0h+var_B0+4]
0x1800ad634  cmp     r10d, eax
0x1800ad637  cmovb   eax, r10d
0x1800ad63b  mov     dword ptr [rsp+1C0h+var_178+4], eax
0x1800ad63f  mov     rcx, [rsp+1C0h+var_178]
0x1800ad644  mov     r8, rcx
  ... truncated ...
```
