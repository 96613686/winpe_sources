# GEL::GDITech::FillPathWithImage(GEL::RenderStage const &,Gdiplus::GpGraphics &,Gfx::IPostScriptSink *,Gdiplus::GpPath const *,Math::TRect<double> const &,bool,GEL::GDIImageBrushResource const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)

- ea: `0x180062b84`
- end: `0x180063fdc`
- name: `?FillPathWithImage@GDITech@GEL@@CAXAEBVRenderStage@2@AEAVGpGraphics@Gdiplus@@PEAUIPostScriptSink@Gfx@@PEBVGpPath@5@AEBU?$TRect@N@Math@@_NAEBVGDIImageBrushResource@2@AEBU?$TAffine3x3@N@Math@@PEBU?$TAffine3x3@N@Math@@@Z`
- size: `5208`
- prototype: ``
- caller_count: `2`
- callee_count: `46`
- tags: `broker_com_uri`

## callers

- `0x180064230`
- `0x180140ed4`

## callees

- `0x180008c40`
- `0x18000a5e0`
- `0x18000a64c`
- `0x18001516c`
- `0x1800151b0`
- `0x1800152c4`
- `0x1800153b0`
- `0x180015520`
- `0x180018ad0`
- `0x180019ce0`
- `0x18001b3d8`
- `0x18001cf08`
- `0x18001df20`
- `0x180024f30`
- `0x180024f60`
- `0x180037274`
- `0x18004dd30`
- `0x1800510b4`
- `0x1800523ec`
- `0x180056ee0`
- `0x1800573f0`
- `0x18005f210`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x180062490`
- `0x1800626b0`
- `0x180062b84`
- `0x180064124`
- `0x1800641cc`
- `0x18006450c`
- `0x180064550`
- `0x18007aa30`
- `0x18008d56c`
- `0x18008e4d4`
- `0x1800a4770`
- `0x1800b2bec`
- `0x180142fc0`
- `0x180145d2c`
- `0x180150ba4`
- `0x1801514ec`
- `0x18015ab8c`
- `0x18015fb40`
- `0x1801677c8`
- `0x18016b880`
- `0x1801ca060`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_controlfp_s` at `0x180062fd7`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp_s` at `0x180063b0a`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp_s` at `0x180063c2b`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp_s` at `0x180062fd7`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp_s` at `0x180063b0a`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp_s` at `0x180063c2b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180063552`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180063552`
- `Mso20Win32Client!__imp_?GetValue@?$AB_t@_N@AB@Mso@@AEBA_NXZ` at `0x180063ba0`
- `Mso20Win32Client!__imp_?GetValue@?$AB_t@_N@AB@Mso@@AEBA_NXZ` at `0x180063ba0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180062f97`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800637b5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180063acc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180063bed`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180062f97`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800637b5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180063acc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180063bed`
- `gdiplus!GdipDeleteRegion` at `0x180063771`
- `gdiplus!GdipDeleteRegion` at `0x180063771`
- `gdiplus!GdipCreateRegion` at `0x180063561`
- `gdiplus!GdipCreateRegion` at `0x180063561`
- `gdiplus!GdipGetClip` at `0x18006357f`
- `gdiplus!GdipGetClip` at `0x18006357f`
- `gdiplus!GdipSetClipPath` at `0x1800635e3`
- `gdiplus!GdipSetClipPath` at `0x1800635e3`
- `gdiplus!GdipSetClipRect` at `0x180063b57`
- `gdiplus!GdipSetClipRect` at `0x180063b57`
- `gdiplus!GdipDrawImageRect` at `0x1800638dd`
- `gdiplus!GdipDrawImageRect` at `0x1800638dd`
- `gdiplus!GdipFillRectangle` at `0x180063db4`
- `gdiplus!GdipFillRectangle` at `0x180063db4`
- `gdiplus!GdipGetSmoothingMode` at `0x180062e16`
- `gdiplus!GdipGetSmoothingMode` at `0x180062e16`
- `gdiplus!GdipSetImageAttributesColorMatrix` at `0x180063d4a`
- `gdiplus!GdipSetImageAttributesColorMatrix` at `0x180063d4a`
- `gdiplus!GdipCreateSolidFill` at `0x180063d8f`
- `gdiplus!GdipCreateSolidFill` at `0x180063d8f`
- `gdiplus!GdipDeleteBrush` at `0x180063dcb`
- `gdiplus!GdipDeleteBrush` at `0x180063dcb`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180063513`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180063513`
- `gdiplus!GdipCreateImageAttributes` at `0x1800634e3`
- `gdiplus!GdipCreateImageAttributes` at `0x1800634e3`
- `gdiplus!GdipDisposeImageAttributes` at `0x180063785`
- `gdiplus!GdipDisposeImageAttributes` at `0x180063785`
- `gdiplus!GdipSetSmoothingMode` at `0x180063ccf`
- `gdiplus!GdipSetSmoothingMode` at `0x180063ccf`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
errno_t __fastcall GEL::GDITech::FillPathWithImage(
        GEL::RenderStage *a1,
        struct Gdiplus::GpGraphics *a2,
        GEL::RenderStage *a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v9; // rcx
  char v10; // r14
  __int64 v11; // rdi
  __int64 v12; // rbx
  errno_t result; // eax
  unsigned int v14; // edx
  __int64 v15; // r14
  bool v16; // r13
  __int64 v17; // rbx
  GEL::RenderStage *v18; // rbx
  char v19; // r14
  char v20; // r15
  char v21; // al
  char v22; // r15
  char v23; // al
  char v24; // r15
  struct Gdiplus::GpGraphics *v25; // r14
  unsigned int SmoothingMode; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  _OWORD *v31; // rax
  struct GEL::IImage *v32; // r14
  Mso::Memory *v33; // rbx
  bool v34; // r8
  char v35; // cl
  __m128d v36; // xmm10
  __m128i si128; // xmm1
  char v38; // al
  _OWORD **v39; // r14
  void *v40; // rdx
  __int64 v41; // r13
  __int64 v42; // rax
  struct GEL::IImage *v43; // rcx
  bool v44; // al
  struct GEL::IImage **v45; // rax
  GEL::RenderStage *v46; // r13
  double *v47; // rdx
  unsigned int GpWrapMode; // eax
  __int64 v49; // r9
  struct Gdiplus::GpGraphics *v50; // rcx
  void *v51; // rdx
  int *v52; // rax
  double *v53; // rcx
  __int64 v54; // rdx
  unsigned int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r8
  unsigned int v58; // eax
  struct Gdiplus::GpGraphics *v59; // r15
  unsigned int Region; // eax
  __int64 v61; // rdx
  __int64 v62; // r8
  unsigned int Clip; // eax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  unsigned int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rax
  int v71; // xmm8_4
  int v72; // xmm7_4
  float v73; // xmm9_4
  float v74; // xmm6_4
  int v75; // edx
  int v76; // r15d
  __int64 (__fastcall ***v77)(_QWORD); // rcx
  unsigned __int8 v78; // al
  __int64 v79; // r15
  char v80; // dl
  char v81; // al
  void *v82; // rdx
  __int64 v83; // rdx
  __int64 v84; // rcx
  unsigned int v85; // eax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // rax
  _OWORD *v89; // rax
  char v90; // al
  bool v91; // zf
  __int64 v92; // rdx
  char v93; // al
  int v94; // eax
  __int64 v95; // [rsp+30h] [rbp-3D8h]
  char v96; // [rsp+90h] [rbp-378h]
  char v97; // [rsp+90h] [rbp-378h]
  int Format; // [rsp+94h] [rbp-374h]
  int v99; // [rsp+94h] [rbp-374h]
  char v100; // [rsp+99h] [rbp-36Fh]
  bool v101; // [rsp+9Ah] [rbp-36Eh]
  char v102; // [rsp+9Bh] [rbp-36Dh]
  char v103; // [rsp+9Ch] [rbp-36Ch]
  struct GEL::IImage *v104; // [rsp+A0h] [rbp-368h] BYREF
  unsigned int NewValue; // [rsp+A8h] [rbp-360h] BYREF
  GEL::RenderStage *v106; // [rsp+B0h] [rbp-358h] BYREF
  __int64 v107; // [rsp+B8h] [rbp-350h]
  __int64 v108; // [rsp+C0h] [rbp-348h] BYREF
  __int64 v109; // [rsp+C8h] [rbp-340h] BYREF
  struct Gdiplus::GpGraphics *v110; // [rsp+D0h] [rbp-338h]
  __int64 v111; // [rsp+D8h] [rbp-330h]
  int v112[2]; // [rsp+E0h] [rbp-328h]
  GEL::RenderStage *v113; // [rsp+E8h] [rbp-320h] BYREF
  int v114; // [rsp+F0h] [rbp-318h] BYREF
  int v115; // [rsp+F4h] [rbp-314h]
  float v116; // [rsp+F8h] [rbp-310h]
  float v117; // [rsp+FCh] [rbp-30Ch]
  struct GEL::IImage *v118; // [rsp+100h] [rbp-308h]
  __int64 v119; // [rsp+108h] [rbp-300h]
  int v120[2]; // [rsp+110h] [rbp-2F8h]
  int v121[2]; // [rsp+118h] [rbp-2F0h]
  Mso::Memory *v122; // [rsp+120h] [rbp-2E8h] BYREF
  struct Gdiplus::GpGraphics *v123[2]; // [rsp+128h] [rbp-2E0h] BYREF
  _OWORD *v124; // [rsp+138h] [rbp-2D0h]
  int v125[2]; // [rsp+140h] [rbp-2C8h]
  struct Gdiplus::GpGraphics *v126; // [rsp+148h] [rbp-2C0h] BYREF
  _BYTE v127[8]; // [rsp+150h] [rbp-2B8h] BYREF
  __int64 v128[2]; // [rsp+158h] [rbp-2B0h] BYREF
  __int128 v129; // [rsp+168h] [rbp-2A0h]
  __int64 v130; // [rsp+178h] [rbp-290h]
  __int64 v131; // [rsp+180h] [rbp-288h]
  struct Gdiplus::GpGraphics *v132; // [rsp+188h] [rbp-280h]
  GEL::RenderStage *v133; // [rsp+190h] [rbp-278h]
  char v134[16]; // [rsp+198h] [rbp-270h] BYREF
  __int64 v135[2]; // [rsp+1A8h] [rbp-260h] BYREF
  __int64 v136[2]; // [rsp+1B8h] [rbp-250h] BYREF
  __int64 v137[2]; // [rsp+1C8h] [rbp-240h] BYREF
  __int128 v138; // [rsp+1D8h] [rbp-230h]
  struct GEL::IImage *v139; // [rsp+1E8h] [rbp-220h]
  __int64 v140[2]; // [rsp+1F0h] [rbp-218h] BYREF
  __m128i v141; // [rsp+200h] [rbp-208h]
  __int128 v142; // [rsp+210h] [rbp-1F8h]
  _OWORD v143[2]; // [rsp+220h] [rbp-1E8h] BYREF
  const OException *v144; // [rsp+240h] [rbp-1C8h] BYREF
  _BYTE v145[16]; // [rsp+248h] [rbp-1C0h] BYREF
  __int64 v146[4]; // [rsp+258h] [rbp-1B0h] BYREF
  int v147[8]; // [rsp+278h] [rbp-190h] BYREF
  _OWORD v148[3]; // [rsp+298h] [rbp-170h] BYREF
  __int64 v149[6]; // [rsp+2C8h] [rbp-140h] BYREF
  _BYTE v150[48]; // [rsp+318h] [rbp-F0h] BYREF
  __int64 v151[2]; // [rsp+348h] [rbp-C0h] BYREF
  __int128 v152; // [rsp+358h] [rbp-B0h]
  _BYTE v153[16]; // [rsp+368h] [rbp-A0h] BYREF

  *(_QWORD *)v120 = a4;
  v113 = a3;
  v110 = a2;
  v106 = a1;
  *(_QWORD *)v112 = a5;
  v133 = a1;
  v132 = a2;
  v109 = a4;
  v130 = a5;
  v119 = a7;
  v111 = a8;
  NewValue = 0;
  *(_QWORD *)v125 = a7 + 40;
  *(_QWORD *)v121 = a7 + 40;
  v118 = *(struct GEL::IImage **)(a7 + 32);
  if ( GEL::ITech::IsEffectCallbackNeeded(*(const struct GEL::IEffectCallback **)(a7 + 72)) )
  {
    v12 = *(_QWORD *)(a7 + 72);
    if ( v12 )
      (**(void (__fastcall ***)(_QWORD))v12)(*(_QWORD *)(a7 + 72));
    v10 = 1;
    v11 = v12;
    v9 = v109;
  }
  else
  {
    v9 = 0;
    v10 = 2;
    v11 = 0;
    v12 = v109;
  }
  v131 = v11;
  if ( (v10 & 2) != 0 )
  {
    v10 &= ~2u;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  }
  if ( (v10 & 1) != 0 && v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  GEL::Image::FGetPixelBounds(v118);
  result = GEL::ITech::ComputeImageToLocalTransform(
             (int)v118,
             (int)a7 + 40,
             a9,
             v112[0],
             (__int64)v149,
             (Gfx::Rect *)v147,
             (__int64)v146);
  if ( (_BYTE)result )
  {
    v15 = *(_QWORD *)(a7 + 48);
    v107 = v15;
    if ( v15 )
    {
      if ( a9 )
      {
        v89 = (_OWORD *)Math::operator*<double,double,double>(v140, v15, a9);
        v148[0] = *v89;
        v148[1] = v89[1];
        v148[2] = v89[2];
        v107 = (__int64)v148;
        v124 = v148;
        goto LABEL_13;
      }
    }
    else
    {
      v15 = 0;
      if ( a9 )
        v15 = a9;
      v107 = v15;
    }
    v124 = (_OWORD *)v15;
LABEL_13:
    Gfx::FPURoundingRestorer::FPURoundingRestorer((Gfx::FPURoundingRestorer *)&NewValue, v14);
    v16 = !GEL::Image::IsRaster(*(GEL::Image **)(a7 + 32));
    v17 = v119;
    if ( (unsigned int)GEL::Image::GetFormat(*(_QWORD *)(v119 + 32)) == 11
      || (v102 = 0, (unsigned int)GEL::Image::GetFormat(*(_QWORD *)(v17 + 32)) == 12) )
    {
      v102 = 1;
    }
    Format = GEL::Image::GetFormat(*(_QWORD *)(v17 + 32));
    v101 = GEL::Image::ContainsPostScriptCommands(*(GEL::Image **)(v17 + 32));
    v18 = v106;
    if ( *(_BYTE *)(a7 + 64) != 4 )
    {
      v19 = a6;
LABEL_17:
      v20 = 1;
LABEL_18:
      if ( !v16 || !GEL::RenderStage::IsPrinter(v18) || v19 || (v21 = 1, !*(_QWORD *)v120) )
        v21 = 0;
      v22 = v21 | v20;
      if ( !v16
        || (unsigned __int8)GEL::RenderStage::GetDeviceType(v18) != 2
        || GEL::RenderStage::IsPrinter(v18)
        || (v23 = 1, *(_DWORD *)v18 == 3) )
      {
        v23 = 0;
      }
      v24 = v23 | v22;
      if ( (unsigned __int8)GEL::RenderStage::GetDeviceType(v18) != 4 || (v96 = 1, !v16) )
        v96 = 0;
      v25 = v110;
      v126 = v110;
      SmoothingMode = GdipGetSmoothingMode(v110, v127);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(SmoothingMode, v27, v28, 38322255);
      if ( GEL::RenderStage::IsPrinter(v18) && v16 )
        GdipSetSmoothingMode(v25, 4);
      if ( v113 && v101 )
        v24 = 0;
      *(_OWORD *)v137 = 0;
      v138 = 0;
      v31 = **(_OWORD ***)v125;
      if ( **(_QWORD **)v125 )
      {
        *(_OWORD *)v137 = *v31;
        v138 = v31[1];
      }
      v32 = v118;
      v104 = v118;
      if ( v118 )
      {
        (**(void (__fastcall ***)(struct GEL::IImage *))v118)(v118);
        v32 = v104;
      }
      v33 = 0;
      v122 = 0;
      v34 = v16 && (v11 || v24);
      v103 = v34;
      if ( v16 && *((_QWORD *)v106 + 22) )
      {
        if ( (unsigned int)GEL::RenderStage::GetTechType() == 2 )
        {
          v44 = Ofc::CObject::FIsKindOf(
                  (Ofc::CObject *)(*((_QWORD *)v106 + 4) + 8LL),
                  (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Gfx::ISpriteTarget const *>::c_typeInfo);
          v35 = v103;
          if ( v44 )
            v35 = 1;
          v103 = v35;
          v32 = v104;
LABEL_34:
          v36 = 0;
          *(_OWORD *)v134 = 0;
          *(_OWORD *)v135 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          *(__m128i *)v136 = si128;
          if ( v11 || v24 || v96 || (v100 = 0, v35) )
            v100 = 1;
          v97 = 0;
          if ( Format != 15
            || (v90 = sub_1801677C8(v32),
                si128 = _mm_load_si128((const __m128i *)&_xmm),
                v32 = v104,
                v91 = v90 == 0,
                v38 = 1,
                v91) )
          {
            v38 = 0;
          }
          if ( !v100 )
          {
            if ( v38 )
            {
              v45 = (struct GEL::IImage **)sub_1800A4770(&v108, v110, v32, v111, v149);
              v32 = *v45;
              *v45 = 0;
              if ( v104 )
                (*(void (__fastcall **)(struct GEL::IImage *))(*(_QWORD *)v104 + 8LL))(v104);
              v104 = v32;
              if ( v108 )
              {
                Mso::TRefCountedImpl<GEL::IImage>::Release();
                v32 = v104;
              }
              if ( !v32 )
                goto LABEL_146;
              v41 = v107;
LABEL_79:
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              goto LABEL_80;
            }
            if ( Format != 15 )
            {
              v41 = v107;
LABEL_80:
              v139 = v32;
              if ( v24 )
              {
                v46 = v106;
LABEL_82:
                GEL::Image::FGetPixelBounds(v32);
                if ( v102 )
                {
                  v109 = *(_QWORD *)&DOUBLE_1_000000003627494eN15;
                  if ( (unsigned __int8)Math::IsNotEqualToZero<Math::TUnits<double,Math::DevicePixels>,0>(v134, &v109)
                    || (v109 = *(_QWORD *)&DOUBLE_1_000000003627494eN15,
                        (unsigned __int8)Math::IsNotEqualToZero<Math::TUnits<double,Math::DevicePixels>,0>(
                                           &v134[8],
                                           &v109)) )
                  {
                    v128[0] = 0;
                    v128[1] = 0;
                    *(double *)&v129 = v36.m128d_f64[0];
                    *((_QWORD *)&v129 + 1) = *(_OWORD *)&_mm_unpackhi_pd(v36, v36);
                  }
                }
                *(_OWORD *)v151 = 0;
                v152 = 0;
                *(__m128i *)v140 = _mm_load_si128((const __m128i *)&_xmm);
                v141 = _mm_load_si128((const __m128i *)&_xmm);
                v142 = 0;
                if ( !(unsigned __int8)GEL::ITech::FComputeImageCropBounds(
                                         v125[0],
                                         (int)v135,
                                         (int)v136,
                                         (int)v147,
                                         (__int64)v146,
                                         v107,
                                         (__int64)v137,
                                         (Gfx::Rect *)v128,
                                         (__int64)v140,
                                         (__int64)v151) )
                  goto LABEL_116;
                GpWrapMode = GEL::GDIImageBrushResource::GetGpWrapMode(v119);
                try
                {
                  v76 = GEL::GDITech::FillPathWithTextureBrush(
                          (__int64)v110,
                          v32,
                          *(__int64 *)v120,
                          v49,
                          (Gfx::Rect *)v128,
                          (__int64)v140,
                          v95,
                          GpWrapMode);
                  v99 = v76;
                }
                catch ( const OException *v144 )
                {
                  v94 = *((_DWORD *)v144 + 129);
                  if ( v94 != -2147024882 && (unsigned int)(v94 + 2003292412) > 0x92 )
                    throw;
                  v33 = v122;
                  v76 = v99;
                  v50 = v132;
                  v46 = v133;
                  v47 = (double *)v130;
                  goto LABEL_86;
                }
LABEL_85:
                v47 = *(double **)v112;
                v50 = v110;
LABEL_86:
                if ( v76 && !*(_BYTE *)(*(_QWORD *)v121 + 56LL) )
                  GEL::GDITech::DrawPlaceholder(
                    (__int64)v46,
                    (__int64)v50,
                    1u,
                    (unsigned int)GEL::ITech::s_defaultRedXFontSize,
                    v47,
                    (double *)v111,
                    *(_QWORD *)(*(_QWORD *)v121 + 48LL));
LABEL_116:
                if ( v33 )
                  Mso::Memory::Free(v33, v47);
                v43 = v104;
                if ( !v104 )
                  goto LABEL_146;
                v42 = *(_QWORD *)v104;
LABEL_45:
                (*(void (__fastcall **)(struct GEL::IImage *))(v42 + 8))(v43);
LABEL_146:
                Gfx::TGpRestorer<enum Gdiplus::SmoothingMode>::~TGpRestorer<enum Gdiplus::SmoothingMode>(&v126);
                return _controlfp_s(0, NewValue, 0x300u);
              }
              v143[0] = si128;
              v143[1] = 0;
              GEL::Image::FGetPixelBounds(v32);
              *(__m128i *)v140 = _mm_load_si128((const __m128i *)&_xmm);
              v141 = _mm_load_si128((const __m128i *)&_xmm);
              v142 = 0;
              *(_OWORD *)v128 = 0;
              v129 = 0;
              if ( v97 )
              {
                if ( (unsigned __int8)GEL::ITech::FComputeImageCropBounds(
                                        v121[0],
                                        (int)v135,
                                        (int)v136,
                                        (int)v147,
                                        (__int64)v146,
                                        v41,
                                        (__int64)v137,
                                        (Gfx::Rect *)v143,
                                        (__int64)v140,
                                        (__int64)v128) )
                {
LABEL_91:
                  v52 = &v114;
                  v53 = (double *)v143;
                  v54 = 4;
                  do
                  {
                    *(float *)v52++ = *v53++;
                    --v54;
                  }
                  while ( v54 );
                  v108 = 0;
                  v55 = GdipCreateImageAttributes(&v108);
                  Gfx::GdipStatus_ThrowOnFailureMessageTag(v55, v56, v57, 39081227);
                  v58 = GEL::GDIImageBrushResource::GetGpWrapMode(v119);
                  GdipSetImageAttributesWrapMode(v108, v58, 0, 0);
                  v123[0] = 0;
                  v59 = v110;
                  v123[1] = v110;
                  GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v151, v110);
                  if ( v123[0] )
                    CrashWithRecovery(0x1E55E058u, 0);
                  Region = GdipCreateRegion(v123);
                  Gfx::GdipStatus_ThrowOnFailureMessageTag(Region, v61, v62, 39081176);
                  Clip = GdipGetClip(v59, v123[0]);
                  Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v64, v65, 39081177);
                  GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v151);
                  v66 = 4;
                  if ( dword_18052EAB0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                     + (unsigned int)tls_index)
                                                   + 4LL) )
                  {
                    Init_thread_header(&dword_18052EAB0);
                    if ( dword_18052EAB0 == -1 )
                    {
                      v88 = Mso::AB::AB_t<bool>::AB_t<bool>(v151);
                      byte_18052EAB4 = Mso::AB::AB_t<bool>::GetValue(v88);
                      std::unique_ptr<Mso::AB::Scope_t<bool>>::~unique_ptr<Mso::AB::Scope_t<bool>>(v153);
                      std::wstring::~wstring(v151);
                      Init_thread_footer(&dword_18052EAB0);
                    }
                  }
                  if ( a6 && byte_18052EAB4 )
                  {
                    Math::TRect<double>::GetHeight(*(_QWORD *)v112, v66);
                    Math::TRect<double>::GetWidth(v84, v83);
                    v85 = GdipSetClipRect(v59);
                    Gfx::GdipStatus_ThrowOnFailureMessageTag(v85, v86, v87, 594343554);
                  }
                  else
                  {
                    v67 = GdipSetClipPath(v59, *(_QWORD *)v120, 1);
                    Gfx::GdipStatus_ThrowOnFailureMessageTag(v67, v68, v69, 594343553);
                  }
                  Gfx::TGpRestorer<enum Gdiplus::CompositingQuality>::TGpRestorer<enum Gdiplus::CompositingQuality>(
                    v128,
                    v59);
                  v70 = Math::operator*<double,double,double>(v150, v140, v111);
                  GEL::GDITransformRestorer::GDITransformRestorer(v145, v59, v70);
                  if ( v113 && v101 )
                  {
                    v46 = v106;
                    v77 = *(__int64 (__fastcall ****)(_QWORD))(*((_QWORD *)v106 + 21) + 280LL);
                    if ( v77 )
                      v78 = (**v77)(v77);
                    else
                      v78 = 1;
                    GEL::IImage::GpImageLock::GpImageLock((GEL::IImage::GpImageLock *)v151, v32, v78);
                    v79 = *((_QWORD *)&v152 + 1);
                    v106 = v113;
                    (**(void (__fastcall ***)(GEL::RenderStage *))v113)(v113);
                    (*(void (__fastcall **)(GEL::RenderStage *, const char *))(*(_QWORD *)v106 + 16LL))(
                      v106,
                      "gsave\r\n0 setlinecap\r\n");
                    v76 = GdipDrawImageRect(v110, v79);
                    GEL::PostScriptDefaultsRestorer::~PostScriptDefaultsRestorer((GEL::PostScriptDefaultsRestorer *)&v106);
                    GEL::IImage::GpImageLock::~GpImageLock((GEL::IImage::GpImageLock *)v151);
                  }
                  else
                  {
                    if ( v33 )
                      GdipSetImageAttributesColorMatrix(v108, 0, 1, v33, 0, 0);
                    v71 = v114;
                    v72 = v115;
                    if ( *(float *)&v114 > v116 || *(float *)&v115 > v117 )
                      v73 = 0.0;
                    else
                      v73 = v116 - *(float *)&v114;
                    if ( *(float *)&v114 > v116 || *(float *)&v115 > v117 )
                      v74 = 0.0;
                    else
                      v74 = v117 - *(float *)&v115;
                    if ( BYTE7(xmmword_18051FD70) )
                      v75 = 0;
                    else
                      v75 = HIDWORD(xmmword_18051FD60);
                    if ( HIBYTE(v75) )
                    {
                      v113 = 0;
                      GdipCreateSolidFill((unsigned __int8)v75 | ((BYTE1(v75) | (HIWORD(v75) << 8)) << 8), &v113);
                      GdipFillRectangle(v59, v113);
                      if ( v113 )
                        GdipDeleteBrush(v113, v92);
                    }
                    v46 = v106;
                    v76 = GEL::GDITech::DrawImageRectRect(
                            v106,
                            v97,
                            v71,
                            v72,
                            SLODWORD(v73),
                            SLODWORD(v74),
                            v71,
                            v72,
                            SLODWORD(v73),
                            SLODWORD(v74));
                  }
                  GEL::GDITransformRestorer::~GDITransformRestorer((GEL::GDITransformRestorer *)v145);
                  Gfx::TGpRestorer<enum Gdiplus::CompositingQuality>::~TGpRestorer<enum Gdiplus::CompositingQuality>(v128);
                  GEL::GDIClip::Unapply((GEL::GDIClip *)v123, v123[1]);
                  if ( v123[0] )
                    GdipDeleteRegion();
                  if ( v108 )
                    GdipDisposeImageAttributes();
                  v47 = (double *)v118;
                  if ( !v76 )
                    goto LABEL_116;
                  if ( v104 == v118 )
                  {
                    v93 = *(_BYTE *)(*(_QWORD *)v121 + 59LL);
                    BYTE4(v109) = 0;
                    GEL::ITech::ResampleAndCropAndApplyEffectsToImage(
                      v46,
                      v111,
                      (__int64)v149,
                      v107,
                      *(_QWORD *)(*(_QWORD *)v121 + 40LL),
                      v11,
                      (__int64)&v109,
                      v103,
                      v93,
                      (__int64)v135,
                      (__int64)v136,
                      (GEL::CropInfo *)v137,
                      (__int64)&v104,
                      0);
                  }
                  if ( !v104 )
                    goto LABEL_85;
                  goto LABEL_82;
                }
                if ( v33 )
                  Mso::Memory::Free(v33, v51);
                if ( !v104 )
                  goto LABEL_146;
              }
              else
              {
                *(__m128i *)v123 = _mm_load_si128((const __m128i *)&_xmm);
                if ( (unsigned __int8)GEL::ITech::FComputeImageCropBounds(
                                        v121[0],
                                        (int)v135,
                                        (int)v123,
                                        0,
                                        0,
                                        v41,
                                        (__int64)v137,
                                        (Gfx::Rect *)v143,
                                        (__int64)v140,
                                        (__int64)v128) )
                  goto LABEL_91;
                if ( v33 )
                  Mso::Memory::Free(v33, v82);
                if ( !v104 )
                  goto LABEL_146;
              }
              (*(void (__fastcall **)(struct GEL::IImage *))(*(_QWORD *)v104 + 8LL))(v104);
              goto LABEL_146;
            }
          }
          LOBYTE(v30) = v16;
          LOBYTE(v29) = v24;
          v39 = *(_OWORD ***)v125;
          GEL::GDITech::BuildColorMatrix(*(_QWORD *)v125, v29, v30, &v122);
          v33 = v122;
          v41 = v107;
          if ( !v122 )
          {
            v80 = v103;
            if ( Format == 15 )
              v80 = 1;
            v103 = v80;
            v81 = *((_BYTE *)v39 + 59);
            BYTE4(v108) = 0;
            GEL::ITech::ResampleAndCropAndApplyEffectsToImage(
              v106,
              v111,
              (__int64)v149,
              v107,
              (__int64)v39[5],
              v11,
              (__int64)&v108,
              v80,
              v81,
              (__int64)v135,
              (__int64)v136,
              (GEL::CropInfo *)v137,
              (__int64)&v104,
              (char)v134);
            v97 = 1;
            v36 = *(__m128d *)v134;
          }
          v32 = v104;
          if ( !v104 )
          {
            if ( v33 )
            {
              Mso::Memory::Free(v33, v40);
              v32 = v104;
            }
            if ( !v32 )
              goto LABEL_146;
            v42 = *(_QWORD *)v32;
            v43 = v32;
            goto LABEL_45;
          }
          goto LABEL_79;
        }
        v32 = v104;
      }
      v35 = v103;
      goto LABEL_34;
    }
    if ( GEL::RenderStage::IsPrinter(v106) || GEL::RenderStage::IsVectorStage(v18) )
    {
      v19 = a6;
    }
    else
    {
      v19 = a6;
      if ( !a6 || *((_BYTE *)v18 + 242) && !v16 )
        goto LABEL_17;
    }
    v20 = 0;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x180062b84  mov     rax, rsp
0x180062b87  push    rbx
0x180062b88  push    rsi
0x180062b89  push    rdi
0x180062b8a  push    r12
0x180062b8c  push    r13
0x180062b8e  push    r14
0x180062b90  push    r15
0x180062b92  sub     rsp, 3D0h
0x180062b99  movaps  xmmword ptr [rax-48h], xmm6
0x180062b9d  movaps  xmmword ptr [rax-58h], xmm7
0x180062ba1  movaps  xmmword ptr [rax-68h], xmm8
0x180062ba6  movaps  xmmword ptr [rax-78h], xmm9
0x180062bab  movaps  xmmword ptr [rax-88h], xmm10
0x180062bb3  mov     rax, cs:__security_cookie
0x180062bba  xor     rax, rsp
0x180062bbd  mov     [rsp+408h+var_90], rax
0x180062bc5  mov     qword ptr [rsp+408h+var_2F8], r9
0x180062bcd  mov     [rsp+408h+var_320], r8
0x180062bd5  mov     [rsp+408h+var_338], rdx
0x180062bdd  mov     rax, rcx
0x180062be0  mov     [rsp+408h+var_358], rcx
0x180062be8  mov     rcx, [rsp+408h+arg_20]
0x180062bf0  mov     qword ptr [rsp+408h+var_328], rcx
0x180062bf8  mov     [rsp+408h+var_278], rax
0x180062c00  mov     [rsp+408h+var_280], rdx
0x180062c08  mov     [rsp+408h+var_340], r9
0x180062c10  mov     [rsp+408h+var_290], rcx
0x180062c18  mov     r13, [rsp+408h+arg_30]
0x180062c20  mov     [rsp+408h+var_300], r13
0x180062c28  mov     rax, [rsp+408h+arg_38]
0x180062c30  mov     [rsp+408h+var_330], rax
0x180062c38  xor     esi, esi
0x180062c3a  mov     [rsp+408h+NewValue], esi
0x180062c41  lea     r15, [r13+28h]
0x180062c45  mov     qword ptr [rsp+408h+var_2C8], r15
0x180062c4d  mov     qword ptr [rsp+408h+var_2F0], r15
0x180062c55  mov     rax, [r13+20h]
0x180062c59  mov     [rsp+408h+var_308], rax
0x180062c61  mov     rcx, [r15+20h]; struct GEL::IEffectCallback *
0x180062c65  call    ?IsEffectCallbackNeeded@ITech@GEL@@SA_NPEBUIEffectCallback@2@@Z; GEL::ITech::IsEffectCallbackNeeded(GEL::IEffectCallback const *)
0x180062c6a  test    al, al
0x180062c6c  jnz     loc_18006301D
0x180062c72  mov     ecx, esi
0x180062c74  lea     r14d, [rsi+2]
0x180062c78  mov     edi, esi
0x180062c7a  lea     r12d, [rsi+1]
0x180062c7e  mov     rbx, [rsp+408h+var_340]
0x180062c86  mov     [rsp+408h+var_288], rdi
0x180062c8e  test    r14b, 2
0x180062c92  jz      short loc_180062CAA
0x180062c94  and     r14d, 0FFFFFFFDh
0x180062c98  test    rcx, rcx
0x180062c9b  jz      short loc_180062CAA
0x180062c9d  mov     rax, [rcx]
0x180062ca0  mov     rax, [rax+8]
0x180062ca4  call    cs:__guard_dispatch_icall_fptr
0x180062caa  test    r12b, r14b
0x180062cad  jnz     loc_180063C36
0x180062cb3  lea     rdx, [rsp+408h+var_110]
0x180062cbb  mov     rcx, [rsp+408h+var_308]
0x180062cc3  call    ?FGetPixelBounds@Image@GEL@@UEBA_NAEAU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::Image::FGetPixelBounds(Math::TRect<Math::TUnits<double,Math::DevicePixels>> &)
0x180062cc8  lea     rax, [rsp+408h+var_1B0]
0x180062cd0  mov     [rsp+408h+var_3D8], rax; __int64
0x180062cd5  lea     rax, [rsp+408h+var_190]
0x180062cdd  mov     [rsp+408h+var_3E0], rax; Gfx::Rect *
0x180062ce2  lea     rax, [rsp+408h+var_140]
0x180062cea  mov     [rsp+408h+var_3E8], rax; __int64
0x180062cef  mov     r9, qword ptr [rsp+408h+var_328]; int
0x180062cf7  mov     rbx, qword ptr [rsp+408h+arg_40]
0x180062cff  mov     r8, rbx; int
0x180062d02  mov     rdx, r15; int
0x180062d05  mov     rcx, [rsp+408h+var_308]; int
0x180062d0d  call    ?ComputeImageToLocalTransform@ITech@GEL@@SA_NAEBUIImage@2@AEBUImageFillInfo@2@PEBU?$TAffine3x3@N@Math@@AEBU?$TRect@N@6@AEAU56@AEAU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@6@5@Z; GEL::ITech::ComputeImageToLocalTransform(GEL::IImage const &,GEL::ImageFillInfo const &,Math::TAffine3x3<double> const *,Math::TRect<double> const &,Math::TAffine3x3<double> &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> &)
0x180062d12  test    al, al
0x180062d14  jz      loc_180062FDD
0x180062d1a  mov     r14, [r15+8]
0x180062d1e  mov     [rsp+408h+var_350], r14
0x180062d26  test    r14, r14
0x180062d29  jnz     loc_180063C54
0x180062d2f  mov     r14, rsi
0x180062d32  test    rbx, rbx
0x180062d35  cmovnz  r14, rbx
0x180062d39  mov     [rsp+408h+var_350], r14
0x180062d41  mov     [rsp+408h+var_2D0], r14
0x180062d49  lea     rcx, [rsp+408h+NewValue]; this
0x180062d51  call    ??0FPURoundingRestorer@Gfx@@QEAA@K@Z; Gfx::FPURoundingRestorer::FPURoundingRestorer(ulong)
0x180062d56  mov     rcx, [r13+20h]; this
0x180062d5a  call    ?IsRaster@Image@GEL@@UEBA_NXZ; GEL::Image::IsRaster(void)
0x180062d5f  nop
0x180062d60  mov     r13b, al
0x180062d63  xor     r13b, r12b
0x180062d66  mov     rbx, [rsp+408h+var_300]
0x180062d6e  mov     rcx, [rbx+20h]
0x180062d72  call    ?GetFormat@Image@GEL@@UEBA?AW4ImageFormat@2@XZ; GEL::Image::GetFormat(void)
0x180062d77  cmp     eax, 0Bh
0x180062d7a  jnz     loc_1800630A5
0x180062d80  mov     [rsp+408h+var_36D], r12b
0x180062d88  mov     rcx, [rbx+20h]
0x180062d8c  call    ?GetFormat@Image@GEL@@UEBA?AW4ImageFormat@2@XZ; GEL::Image::GetFormat(void)
0x180062d91  mov     [rsp+408h+var_374], eax
0x180062d98  mov     rcx, [rbx+20h]; this
0x180062d9c  call    ?ContainsPostScriptCommands@Image@GEL@@QEBA_NXZ; GEL::Image::ContainsPostScriptCommands(void)
0x180062da1  mov     [rsp+408h+var_36E], al
0x180062da8  mov     rbx, [rsp+408h+var_358]
0x180062db0  cmp     byte ptr [r15+18h], 4
0x180062db5  jz      loc_18006305F
0x180062dbb  mov     r14b, [rsp+408h+arg_28]
0x180062dc3  mov     r15d, r12d
0x180062dc6  test    r13b, r13b
0x180062dc9  jnz     loc_18006390C
0x180062dcf  mov     eax, esi
0x180062dd1  or      r15d, eax
0x180062dd4  test    r13b, r13b
0x180062dd7  jnz     loc_180063A45
0x180062ddd  mov     al, sil
0x180062de0  or      r15b, al
0x180062de3  mov     rcx, rbx
0x180062de6  call    ?GetDeviceType@RenderStage@GEL@@QEBA?AW4DeviceType@2@XZ; GEL::RenderStage::GetDeviceType(void)
0x180062deb  cmp     al, 4
0x180062ded  jz      loc_1800630C4
0x180062df3  mov     [rsp+408h+var_378], sil
0x180062dfb  mov     r14, [rsp+408h+var_338]
0x180062e03  mov     [rsp+408h+var_2C0], r14
0x180062e0b  lea     rdx, [rsp+408h+var_2B8]
0x180062e13  mov     rcx, r14
0x180062e16  call    cs:__imp_GdipGetSmoothingMode
0x180062e1c  mov     r9d, 248C04Fh
0x180062e22  mov     ecx, eax
0x180062e24  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180062e29  mov     rcx, rbx; this
0x180062e2c  call    ?IsPrinter@RenderStage@GEL@@QEBA_NXZ; GEL::RenderStage::IsPrinter(void)
0x180062e31  test    al, al
0x180062e33  jnz     loc_180063CBE
0x180062e39  cmp     [rsp+408h+var_320], rsi
0x180062e41  jnz     loc_180063CDA
0x180062e47  xorps   xmm0, xmm0
0x180062e4a  movups  xmmword ptr [rsp+408h+var_240], xmm0
0x180062e52  xorps   xmm1, xmm1
0x180062e55  movups  [rsp+408h+var_230], xmm1
0x180062e5d  mov     rax, qword ptr [rsp+408h+var_2C8]
0x180062e65  mov     rax, [rax]
0x180062e68  test    rax, rax
0x180062e6b  jz      short loc_180062E84
0x180062e6d  movups  xmm0, xmmword ptr [rax]
0x180062e70  movups  xmmword ptr [rsp+408h+var_240], xmm0
0x180062e78  movups  xmm1, xmmword ptr [rax+10h]
0x180062e7c  movups  [rsp+408h+var_230], xmm1
0x180062e84  mov     rcx, [rsp+408h+var_308]
0x180062e8c  mov     r14, rcx
0x180062e8f  mov     [rsp+408h+var_368], rcx
0x180062e97  test    rcx, rcx
0x180062e9a  jz      short loc_180062EB0
0x180062e9c  mov     rax, [rcx]
0x180062e9f  mov     rax, [rax]
0x180062ea2  call    cs:__guard_dispatch_icall_fptr
0x180062ea8  mov     r14, [rsp+408h+var_368]
0x180062eb0  mov     rbx, rsi
0x180062eb3  mov     [rsp+408h+var_2E8], rbx
0x180062ebb  test    r13b, r13b
0x180062ebe  jnz     loc_18006304E
0x180062ec4  mov     r8b, sil
0x180062ec7  mov     [rsp+408h+var_370], r8b
0x180062ecf  mov     dword ptr [rsp+408h+var_36C], r8d
0x180062ed7  test    r13b, r13b
0x180062eda  jnz     loc_180063106
0x180062ee0  mov     ecx, dword ptr [rsp+408h+var_36C]
0x180062ee7  xorps   xmm10, xmm10
0x180062eeb  movups  xmmword ptr [rsp+408h+var_270], xmm10
0x180062ef4  xorps   xmm0, xmm0
0x180062ef7  movups  xmmword ptr [rsp+408h+var_260], xmm0
0x180062eff  movdqa  xmm1, cs:__xmm@3ff00000000000003ff0000000000000
0x180062f07  movups  xmmword ptr [rsp+408h+var_250], xmm1
0x180062f0f  test    rdi, rdi
0x180062f12  jz      loc_1800630DA
0x180062f18  mov     [rsp+408h+var_36F], r12b
0x180062f20  mov     [rsp+408h+var_378], sil
0x180062f28  cmp     [rsp+408h+var_374], 0Fh
0x180062f30  jz      loc_180063CFC
0x180062f36  mov     al, sil
0x180062f39  cmp     [rsp+408h+var_36F], sil
0x180062f41  jz      loc_180063180
0x180062f47  lea     r9, [rsp+408h+var_2E8]
0x180062f4f  mov     r8b, r13b
0x180062f52  mov     dl, r15b
0x180062f55  mov     r14, qword ptr [rsp+408h+var_2C8]
0x180062f5d  mov     rcx, r14
0x180062f60  call    ?BuildColorMatrix@GDITech@GEL@@CAXAEBUImageFillInfo@2@_N1AEAV?$TOwnerPtr@UColorMatrix@Gdiplus@@@Ofc@@@Z; GEL::GDITech::BuildColorMatrix(GEL::ImageFillInfo const &,bool,bool,Ofc::TOwnerPtr<Gdiplus::ColorMatrix> &)
0x180062f65  mov     rbx, [rsp+408h+var_2E8]
0x180062f6d  mov     r13, [rsp+408h+var_350]
0x180062f75  test    rbx, rbx
0x180062f78  jz      loc_18006393B
0x180062f7e  mov     r14, [rsp+408h+var_368]
0x180062f86  test    r14, r14
0x180062f89  jnz     loc_180063213
0x180062f8f  test    rbx, rbx
0x180062f92  jz      short loc_180062FA5
0x180062f94  mov     rcx, rbx
0x180062f97  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180062f9d  mov     r14, [rsp+408h+var_368]
0x180062fa5  test    r14, r14
0x180062fa8  jz      short loc_180062FBB
0x180062faa  mov     rax, [r14]
0x180062fad  mov     rcx, r14
0x180062fb0  mov     rax, [rax+8]
0x180062fb4  call    cs:__guard_dispatch_icall_fptr
0x180062fba  nop
0x180062fbb  lea     rcx, [rsp+408h+var_2C0]
0x180062fc3  call    ??1?$TGpRestorer@W4SmoothingMode@Gdiplus@@@Gfx@@QEAA@XZ; Gfx::TGpRestorer<Gdiplus::SmoothingMode>::~TGpRestorer<Gdiplus::SmoothingMode>(void)
0x180062fc8  mov     r8d, 300h; Mask
0x180062fce  mov     edx, [rsp+408h+NewValue]; NewValue
0x180062fd5  xor     ecx, ecx; CurrentState
0x180062fd7  call    cs:__imp__controlfp_s
0x180062fdd  mov     rcx, [rsp+408h+var_90]
0x180062fe5  xor     rcx, rsp; StackCookie
0x180062fe8  call    __security_check_cookie
0x180062fed  lea     r11, [rsp+408h+var_38]
0x180062ff5  movaps  xmm6, xmmword ptr [r11-10h]
0x180062ffa  movaps  xmm7, xmmword ptr [r11-20h]
0x180062fff  movaps  xmm8, xmmword ptr [r11-30h]
0x180063004  movaps  xmm9, xmmword ptr [r11-40h]
0x180063009  movaps  xmm10, xmmword ptr [r11-50h]
0x18006300e  mov     rsp, r11
0x180063011  pop     r15
0x180063013  pop     r14
0x180063015  pop     r13
0x180063017  pop     r12
0x180063019  pop     rdi
0x18006301a  pop     rsi
0x18006301b  pop     rbx
0x18006301c  retn
0x18006301d  mov     rbx, [r15+20h]
0x180063021  test    rbx, rbx
0x180063024  jz      short loc_180063035
0x180063026  mov     rax, [rbx]
0x180063029  mov     rcx, rbx
0x18006302c  mov     rax, [rax]
0x18006302f  call    cs:__guard_dispatch_icall_fptr
0x180063035  mov     r12d, 1
0x18006303b  mov     r14d, r12d
0x18006303e  mov     rdi, rbx
0x180063041  mov     rcx, [rsp+408h+var_340]
0x180063049  jmp     loc_180062C86
0x18006304e  test    rdi, rdi
0x180063051  jz      loc_180063205
0x180063057  mov     r8b, r12b
0x18006305a  jmp     loc_180062EC7
0x18006305f  mov     rcx, rbx; this
0x180063062  call    ?IsPrinter@RenderStage@GEL@@QEBA_NXZ; GEL::RenderStage::IsPrinter(void)
0x180063067  test    al, al
0x180063069  jnz     loc_180063173
0x18006306f  mov     rcx, rbx; this
0x180063072  call    ?IsVectorStage@RenderStage@GEL@@QEBA_NXZ; GEL::RenderStage::IsVectorStage(void)
0x180063077  test    al, al
0x180063079  jnz     loc_180063173
0x18006307f  mov     r14b, [rsp+408h+arg_28]
0x180063087  test    r14b, r14b
0x18006308a  jz      loc_180062DC3
0x180063090  cmp     [rbx+0F2h], sil
0x180063097  jnz     loc_180063CB0
0x18006309d  mov     r15d, esi
0x1800630a0  jmp     loc_180062DC6
0x1800630a5  mov     rcx, [rbx+20h]
0x1800630a9  call    ?GetFormat@Image@GEL@@UEBA?AW4ImageFormat@2@XZ; GEL::Image::GetFormat(void)
0x1800630ae  cmp     eax, 0Ch
0x1800630b1  mov     [rsp+408h+var_36D], sil
0x1800630b9  jnz     loc_180062D88
0x1800630bf  jmp     loc_180062D80
0x1800630c4  test    r13b, r13b
0x1800630c7  mov     [rsp+408h+var_378], r12b
0x1800630cf  jnz     loc_180062DFB
0x1800630d5  jmp     loc_180062DF3
0x1800630da  test    r15b, r15b
0x1800630dd  jnz     loc_180062F18
0x1800630e3  cmp     [rsp+408h+var_378], sil
0x1800630eb  jnz     loc_180062F18
0x1800630f1  test    cl, cl
0x1800630f3  mov     [rsp+408h+var_36F], sil
0x1800630fb  jz      loc_180062F20
0x180063101  jmp     loc_180062F18
0x180063106  mov     rcx, [rsp+408h+var_358]
0x18006310e  mov     rcx, [rcx+0B0h]
0x180063115  test    rcx, rcx
0x180063118  jz      loc_180062EE0
0x18006311e  call    ?GetTechType@RenderStage@GEL@@QEBA?AW4TechType@2@XZ; GEL::RenderStage::GetTechType(void)
0x180063123  cmp     eax, 2
0x180063126  jnz     loc_180063CEF
0x18006312c  mov     rax, [rsp+408h+var_358]
0x180063134  mov     rcx, [rax+20h]
0x180063138  add     rcx, 8; this
0x18006313c  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@PEBUISpriteTarget@Gfx@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x180063143  call    ?FIsKindOf@CObject@Ofc@@QEBA_NAEBVTypeInfo@2@@Z; Ofc::CObject::FIsKindOf(Ofc::TypeInfo const &)
0x180063148  mov     ecx, dword ptr [rsp+408h+var_36C]
0x18006314f  movzx   ecx, cl
0x180063152  test    al, al
0x180063154  cmovnz  ecx, r12d
0x180063158  mov     dword ptr [rsp+408h+var_36C], ecx
0x18006315f  mov     [rsp+408h+var_370], cl
0x180063166  mov     r14, [rsp+408h+var_368]
0x18006316e  jmp     loc_180062EE7
  ... truncated ...
```
