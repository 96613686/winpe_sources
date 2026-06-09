# Art::UtilDrawPointedThumb(Gfx::ITarget::Frame &,NetUI::Fill const &,tagRECT const &,Art::RenderState,NetUI::Fill const &,Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::DeviceIndependentPixels>>,bool)

- ea: `0x180519ca8`
- end: `0x18051a7e0`
- name: `?UtilDrawPointedThumb@Art@@YAXAEAVFrame@ITarget@Gfx@@AEBUFill@NetUI@@AEBUtagRECT@@W4RenderState@1@1V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@_N@Z`
- size: `2872`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180519a18`

## callees

- `0x180070fe0`
- `0x180071720`
- `0x180519ca8`
- `0x18051a7e0`
- `0x18051a960`
- `0x18051aad0`

## import_xrefs

- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180519ea8`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180519f1c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180519ffc`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18051a0de`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18051a235`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180519ea8`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180519f1c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180519ffc`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18051a0de`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18051a235`
- `gfx!?Create@IPathPrimitive@Gfx@@SA?AV?$TCntPtr@UIPathPrimitive@Gfx@@@Ofc@@XZ` at `0x180519f26`
- `gfx!?Create@IPathPrimitive@Gfx@@SA?AV?$TCntPtr@UIPathPrimitive@Gfx@@@Ofc@@XZ` at `0x180519f26`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEAUIFigurePrimitive@2@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x180519f3b`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEAUIFigurePrimitive@2@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x180519f3b`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18051a774`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18051a774`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x180519f7d`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x180519f9b`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x180519f7d`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x180519f9b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x180519e41`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x180519ebd`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x180519e41`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x180519ebd`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x180519f6f`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x18051a700`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x180519f6f`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x18051a700`
- `USER32!SetRect` at `0x180519d2c`
- `USER32!SetRect` at `0x180519d2c`

## pseudocode

```c
__int64 __fastcall Art::UtilDrawPointedThumb(
        Art *a1,
        NetUI::Fill *a2,
        __m128i *a3,
        int a4,
        NetUI::Fill *a5,
        unsigned int a6,
        char a7)
{
  int yBottom; // r15d
  __m128i v9; // xmm7
  unsigned int v10; // r12d
  unsigned int v11; // edi
  __int32 v12; // ecx
  unsigned int v13; // r13d
  int v14; // esi
  int v15; // edx
  int v16; // ebx
  int v17; // r14d
  int v18; // ecx
  int v19; // r8d
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  int v25; // edx
  __int64 v26; // rax
  unsigned int v27; // r13d
  struct Gfx::IFigureStyle *v28; // r9
  Art *v29; // r13
  int v30; // r13d
  __int64 v31; // rax
  int v32; // edx
  __int64 result; // rax
  unsigned int v34; // ecx
  int v35; // eax
  int v36; // ecx
  int v37; // ecx
  __int32 v38; // eax
  int v39; // eax
  int v40; // eax
  unsigned int v41; // eax
  float v42; // xmm0_4
  int v43; // [rsp+38h] [rbp-C8h]
  int v44; // [rsp+38h] [rbp-C8h]
  int v45; // [rsp+38h] [rbp-C8h]
  int v46; // [rsp+38h] [rbp-C8h]
  int v47; // [rsp+38h] [rbp-C8h]
  int v48; // [rsp+38h] [rbp-C8h]
  int v49; // [rsp+38h] [rbp-C8h]
  int v50; // [rsp+38h] [rbp-C8h]
  int v51; // [rsp+38h] [rbp-C8h]
  int v52; // [rsp+38h] [rbp-C8h]
  int v53; // [rsp+38h] [rbp-C8h]
  int v54; // [rsp+38h] [rbp-C8h]
  int v55; // [rsp+38h] [rbp-C8h]
  int v56; // [rsp+38h] [rbp-C8h]
  int v57; // [rsp+38h] [rbp-C8h]
  int v58; // [rsp+38h] [rbp-C8h]
  int v59; // [rsp+38h] [rbp-C8h]
  int v60; // [rsp+38h] [rbp-C8h]
  int v61; // [rsp+40h] [rbp-C0h]
  int v62; // [rsp+40h] [rbp-C0h]
  struct Frame *v63; // [rsp+48h] [rbp-B8h] BYREF
  int v64; // [rsp+50h] [rbp-B0h]
  int v65; // [rsp+54h] [rbp-ACh]
  struct Gfx::IFigureStyle *v66; // [rsp+58h] [rbp-A8h]
  Art *v67; // [rsp+60h] [rbp-A0h]
  struct Gfx::IFigureShapeBuilder *v68; // [rsp+68h] [rbp-98h] BYREF
  struct Gfx::IFigureStyle *v69[2]; // [rsp+70h] [rbp-90h] BYREF
  struct Gfx::IFigureStyle *v70; // [rsp+80h] [rbp-80h]
  struct Gfx::IFigureStyle *v71; // [rsp+90h] [rbp-70h]
  int v72; // [rsp+A0h] [rbp-60h]
  int v73; // [rsp+A4h] [rbp-5Ch]
  int v74; // [rsp+A8h] [rbp-58h]
  unsigned int v75; // [rsp+ACh] [rbp-54h]
  __m128i v76; // [rsp+B0h] [rbp-50h]
  struct Gfx::IFigureShapeBuilder *v77; // [rsp+C0h] [rbp-40h] BYREF
  struct Gfx::IFigureShapeBuilder *v78; // [rsp+C8h] [rbp-38h] BYREF
  struct Gfx::IFigureShapeBuilder *v79; // [rsp+D0h] [rbp-30h] BYREF
  NetUI::Fill *v80; // [rsp+D8h] [rbp-28h]
  int v81; // [rsp+E0h] [rbp-20h]
  struct Gfx::IFigureShapeBuilder *v82; // [rsp+E8h] [rbp-18h] BYREF
  signed int v83; // [rsp+F0h] [rbp-10h]
  __m128i *v84; // [rsp+F8h] [rbp-8h]
  struct Gfx::IFigureShapeBuilder *v85; // [rsp+100h] [rbp+0h] BYREF
  __int64 v86; // [rsp+108h] [rbp+8h] BYREF
  NetUI::Fill *v87; // [rsp+110h] [rbp+10h]
  struct tagRECT rc; // [rsp+118h] [rbp+18h] BYREF

  v72 = a4;
  v84 = a3;
  v80 = a2;
  v67 = a1;
  v87 = a5;
  yBottom = Art::ScaleForDPI(a6, 1);
  rc = 0;
  v76 = *a3;
  v9 = v76;
  SetRect(&rc, yBottom, yBottom, yBottom, yBottom);
  v10 = rc.left + _mm_cvtsi128_si32(v76);
  v76.m128i_i32[0] = v10;
  v11 = v76.m128i_u32[2];
  if ( (int)v10 <= v76.m128i_i32[2] )
  {
    v11 = v76.m128i_i32[2] - rc.right;
    if ( v76.m128i_i32[2] - rc.right < (int)v10 )
      v11 = v10;
    v76.m128i_i32[2] = v11;
  }
  else
  {
    v10 = v76.m128i_u32[2];
    v76.m128i_i32[0] = v76.m128i_i32[2];
  }
  v12 = rc.top + v76.m128i_i32[1];
  v76.m128i_i32[1] = v12;
  if ( v12 <= v76.m128i_i32[3] )
  {
    v38 = v76.m128i_i32[3] - rc.bottom;
    if ( v76.m128i_i32[3] - rc.bottom < v12 )
      v38 = v12;
    v76.m128i_i32[3] = v38;
  }
  else
  {
    v76.m128i_i32[1] = v76.m128i_i32[3];
  }
  *(__m128i *)v69 = v76;
  v13 = rc.left + v10;
  LODWORD(v71) = rc.left + v10;
  v14 = v76.m128i_i32[2];
  if ( (int)(rc.left + v10) <= v76.m128i_i32[2] )
  {
    v14 = v76.m128i_i32[2] - rc.right;
    if ( v76.m128i_i32[2] - rc.right < (int)v13 )
      v14 = rc.left + v10;
  }
  else
  {
    v13 = v76.m128i_u32[2];
    LODWORD(v71) = v76.m128i_i32[2];
  }
  v15 = rc.top + HIDWORD(v69[0]);
  v61 = rc.top + HIDWORD(v69[0]);
  v16 = HIDWORD(v69[1]);
  if ( rc.top + HIDWORD(v69[0]) <= SHIDWORD(v69[1]) )
  {
    v16 = HIDWORD(v69[1]) - rc.bottom;
    if ( HIDWORD(v69[1]) - rc.bottom < v15 )
      v16 = rc.top + HIDWORD(v69[0]);
  }
  else
  {
    v15 = HIDWORD(v69[1]);
    v61 = HIDWORD(v69[1]);
  }
  v17 = v14;
  v18 = rc.left + v13;
  LODWORD(v70) = rc.left + v13;
  v19 = v14;
  if ( (int)(rc.left + v13) <= v14 )
  {
    v17 = v14 - rc.right;
    if ( v14 - rc.right < v18 )
      v17 = rc.left + v13;
  }
  else
  {
    v18 = v14;
    LODWORD(v70) = v14;
  }
  LODWORD(v68) = rc.top + v15;
  if ( rc.top + v15 > v16 )
  {
    LODWORD(v68) = v16;
    v19 = v14;
  }
  v83 = v19 - v13;
  v81 = (int)(v19 - v13 + yBottom) / 2;
  v20 = v16 - v81;
  v64 = v17;
  LODWORD(v66) = rc.left + v18;
  if ( rc.left + v18 <= v17 )
  {
    v39 = v17 - rc.right;
    if ( v17 - rc.right < rc.left + v18 )
      v39 = rc.left + v18;
    v64 = v39;
  }
  else
  {
    LODWORD(v66) = v17;
  }
  v65 = rc.top + (_DWORD)v68;
  if ( rc.top + (int)v68 <= v20 )
  {
    v40 = v20 - rc.bottom;
    if ( v20 - rc.bottom < rc.top + (int)v68 )
      v40 = rc.top + (_DWORD)v68;
    v74 = v40;
  }
  else
  {
    v74 = v20;
    v65 = v20;
  }
  v21 = 808;
  if ( v72 != 1 )
    v21 = 812;
  v22 = MsoCrCbvGet(v21);
  *(float *)v69 = (float)(unsigned __int8)v22 / 255.0;
  *((float *)v69 + 1) = (float)BYTE1(v22) / 255.0;
  *(float *)&v69[1] = (float)BYTE2(v22) / 255.0;
  HIDWORD(v69[1]) = 1065353216;
  Gfx::IFigureStyle::Create(&v79, v69);
  v23 = 809;
  if ( v72 != 1 )
    v23 = 813;
  v24 = MsoCrCbvGet(v23);
  *(float *)v69 = (float)(unsigned __int8)v24 / 255.0;
  *((float *)v69 + 1) = (float)BYTE1(v24) / 255.0;
  *(float *)&v69[1] = (float)BYTE2(v24) / 255.0;
  HIDWORD(v69[1]) = 1065353216;
  Gfx::IFigureStyle::Create(&v78, v69);
  Gfx::IPathPrimitive::Create(&v86);
  Gfx::IFigureShapeBuilder::Create(&v63, v86, 0, 0);
  v73 = _mm_cvtsi128_si32(_mm_srli_si128(v9, 8));
  v75 = _mm_cvtsi128_si32(v9);
  if ( a7 || v72 == 1 )
  {
    Art::UtilFillSB(
      v67,
      v63,
      v79,
      (struct Gfx::IFigureStyle *)(unsigned int)_mm_cvtsi128_si32(v9),
      v76.m128i_i32[1],
      v10,
      v20,
      v43);
    Art::UtilFillSB(
      v67,
      v63,
      v79,
      (struct Gfx::IFigureStyle *)v10,
      _mm_cvtsi128_si32(_mm_srli_si128(v9, 4)),
      v11,
      v76.m128i_i32[1],
      v56);
    Art::UtilFillSB(v67, v63, v79, (struct Gfx::IFigureStyle *)v11, v76.m128i_i32[1], v73, v20, v57);
    Art::UtilFillSB(v67, v63, v78, (struct Gfx::IFigureStyle *)v10, v61, v13, v20, v58);
    Art::UtilFillSB(v67, v63, v78, (struct Gfx::IFigureStyle *)v10, v76.m128i_i32[1], v11, v61, v59);
    Art::UtilFillSB(v67, v63, v78, (struct Gfx::IFigureStyle *)(unsigned int)v14, v61, v11, v20, v60);
  }
  LODWORD(v80) = NetUI::Fill::GetPrimaryARGBColor(v80);
  if ( ((unsigned int)v80 & 0xFFFFFF) == MsoCrSysColorGet(15) )
    v25 = MsoCrSysColorGet(21);
  else
    v25 = (unsigned __int8)(int)((double)(unsigned __int8)v80 - (double)(unsigned __int8)v80 * 0.75)
        | ((unsigned __int8)(int)((double)BYTE2(v80) - (double)BYTE2(v80) * 0.75) << 16)
        | ((unsigned __int8)(int)((double)((unsigned __int16)v80 >> 8) - (double)((unsigned __int16)v80 >> 8) * 0.75) << 8);
  *(float *)v69 = (float)(unsigned __int8)v25 / 255.0;
  *((float *)v69 + 1) = (float)BYTE1(v25) / 255.0;
  *(float *)&v69[1] = (float)BYTE2(v25) / 255.0;
  HIDWORD(v69[1]) = 1065353216;
  Gfx::IFigureStyle::Create(&v82, v69);
  Art::UtilFillSB(v67, v63, v82, (struct Gfx::IFigureStyle *)v13, v61, (int)v70, v20, v43);
  Art::UtilFillSB(v67, v63, v82, (struct Gfx::IFigureStyle *)v13, v61, v14, (int)v68, v44);
  Art::UtilFillSB(v67, v63, v82, (struct Gfx::IFigureStyle *)(unsigned int)v17, v61, v14, v20, v45);
  v26 = Art::UtilAdjustBrightness((unsigned int)v80, 0);
  *(float *)v69 = (float)(unsigned __int8)v26 / 255.0;
  *((float *)v69 + 1) = (float)BYTE1(v26) / 255.0;
  *(float *)&v69[1] = (float)BYTE2(v26) / 255.0;
  HIDWORD(v69[1]) = 1065353216;
  Gfx::IFigureStyle::Create(&v77, v69);
  v27 = (unsigned int)v70;
  Art::UtilFillSB(v67, v63, v77, (struct Gfx::IFigureStyle *)(unsigned int)v70, (int)v68, (int)v66, v20, v46);
  Art::UtilFillSB(v67, v63, v77, (struct Gfx::IFigureStyle *)v27, (int)v68, v17, v65, v47);
  Art::UtilFillSB(v67, v63, v77, (struct Gfx::IFigureStyle *)(unsigned int)v64, (int)v68, v17, v20, v48);
  v62 = v20 + yBottom;
  v28 = (struct Gfx::IFigureStyle *)v27;
  v29 = v67;
  Art::UtilFillSB(v67, v63, v77, v28, v20 - yBottom, v17, v20 + yBottom, v49);
  if ( (int)v66 < v64 && v65 < v74 )
  {
    v41 = NetUI::Fill::GetPrimaryARGBColor(v87) & 0xFFFFFF;
    v42 = (double)(unsigned __int8)v41 / 255.0;
    *(float *)v69 = v42;
    *((float *)v69 + 1) = (double)BYTE1(v41) / 255.0;
    *(float *)&v69[1] = (double)HIWORD(v41) / 255.0;
    HIDWORD(v69[1]) = 1065353216;
    Gfx::IFigureStyle::Create(&v68);
    (*(void (__fastcall **)(struct Gfx::IFigureShapeBuilder *, struct Gfx::IFigureStyle **))(*(_QWORD *)v68 + 24LL))(
      v68,
      v69);
    Art::UtilFillSB(v29, v63, v68, (struct Gfx::IFigureStyle *)(unsigned int)v66, v65, v64, v74, v50);
    if ( v68 )
      (*(void (__fastcall **)(struct Gfx::IFigureShapeBuilder *))(*(_QWORD *)v68 + 8LL))(v68);
  }
  LODWORD(v66) = v20;
  v65 = v20 + yBottom;
  v64 = v20;
  LODWORD(v68) = v20 + yBottom;
  v30 = (_DWORD)v71 + v83 / 2;
  v31 = Art::UtilAdjustBrightness((unsigned int)v80, 2);
  *(float *)v69 = (float)(unsigned __int8)v31 / 255.0;
  *((float *)v69 + 1) = (float)BYTE1(v31) / 255.0;
  *(float *)&v69[1] = (float)BYTE2(v31) / 255.0;
  HIDWORD(v69[1]) = 1065353216;
  Gfx::IFigureStyle::Create(&v85, v69);
  v32 = (int)v68;
  while ( 1 )
  {
    result = (__int64)v84;
    if ( v32 > v84->m128i_i32[3] + v81 )
      break;
    if ( a7 || v72 == 1 )
    {
      Art::UtilFillSB(v67, v63, v79, (struct Gfx::IFigureStyle *)v75, v20, v10, v62, v50);
      Art::UtilFillSB(v67, v63, v79, (struct Gfx::IFigureStyle *)v11, v20, v73, v62, v51);
      Art::UtilFillSB(v67, v63, v78, (struct Gfx::IFigureStyle *)v10, (int)v66, (int)v71, v65, v52);
      Art::UtilFillSB(v67, v63, v78, (struct Gfx::IFigureStyle *)(unsigned int)v14, (int)v66, v11, v65, v53);
      v20 += yBottom;
      v62 += yBottom;
      v34 = yBottom + v75;
      if ( v30 < (int)(yBottom + v75) )
        v34 = v30;
      v75 = v34;
      v35 = v73 - yBottom;
      if ( v30 > v73 - yBottom )
        v35 = v30;
      v73 = v35;
      LODWORD(v66) = yBottom + (_DWORD)v66;
      v65 += yBottom;
      v10 += yBottom;
      if ( v30 < (int)v10 )
        v10 = v30;
      v11 -= yBottom;
      if ( v30 > (int)v11 )
        v11 = v30;
      v32 = (int)v68;
    }
    Art::UtilFillSB(v67, v63, v85, (struct Gfx::IFigureStyle *)(unsigned int)v71, v64, (int)v70, v32, v50);
    Art::UtilFillSB(v67, v63, v82, (struct Gfx::IFigureStyle *)(unsigned int)v17, v64, v14, (int)v68, v54);
    Art::UtilFillSB(v67, v63, v77, (struct Gfx::IFigureStyle *)(unsigned int)v70, v64, v17, (int)v68, v55);
    v64 += yBottom;
    v32 = yBottom + (_DWORD)v68;
    LODWORD(v68) = yBottom + (_DWORD)v68;
    v36 = yBottom + (_DWORD)v71;
    if ( v30 < yBottom + (int)v71 )
      v36 = v30;
    LODWORD(v71) = v36;
    v14 -= yBottom;
    if ( v30 > v14 )
      v14 = v30;
    v37 = yBottom + (_DWORD)v70;
    if ( v30 < yBottom + (int)v70 )
      v37 = v30;
    LODWORD(v70) = v37;
    v17 -= yBottom;
    if ( v30 > v17 )
      v17 = v30;
  }
  if ( v85 )
    result = (*(__int64 (__fastcall **)(struct Gfx::IFigureShapeBuilder *))(*(_QWORD *)v85 + 8LL))(v85);
  if ( v77 )
    result = (*(__int64 (__fastcall **)(struct Gfx::IFigureShapeBuilder *))(*(_QWORD *)v77 + 8LL))(v77);
  if ( v82 )
    result = (*(__int64 (__fastcall **)(struct Gfx::IFigureShapeBuilder *))(*(_QWORD *)v82 + 8LL))(v82);
  if ( v63 )
    result = ((__int64 (__fastcall *)(struct Frame *))v63->lpVtbl->AddRef)(v63);
  if ( v86 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 8LL))(v86);
  if ( v78 )
    result = (*(__int64 (__fastcall **)(struct Gfx::IFigureShapeBuilder *))(*(_QWORD *)v78 + 8LL))(v78);
  if ( v79 )
    return (*(__int64 (__fastcall **)(struct Gfx::IFigureShapeBuilder *))(*(_QWORD *)v79 + 8LL))(v79);
  return result;
}

```

## disassembly

```asm
0x180519ca8  mov     rax, rsp
0x180519cab  mov     [rax+20h], rbx
0x180519caf  push    rbp
0x180519cb0  push    rsi
0x180519cb1  push    rdi
0x180519cb2  push    r12
0x180519cb4  push    r13
0x180519cb6  push    r14
0x180519cb8  push    r15
0x180519cba  lea     rbp, [rsp-50h]
0x180519cbf  sub     rsp, 150h
0x180519cc6  movaps  xmmword ptr [rax-48h], xmm6
0x180519cca  movaps  xmmword ptr [rax-58h], xmm7
0x180519cce  mov     rax, cs:__security_cookie
0x180519cd5  xor     rax, rsp
0x180519cd8  mov     [rbp+80h+var_58], rax
0x180519cdc  mov     [rbp+80h+var_E0], r9d
0x180519ce0  mov     rbx, r8
0x180519ce3  mov     [rbp+80h+var_88], rbx
0x180519ce7  mov     [rbp+80h+var_A8], rdx
0x180519ceb  mov     [rsp+180h+var_120], rcx
0x180519cf0  mov     rax, [rbp+80h+arg_20]
0x180519cf7  mov     [rbp+80h+var_70], rax
0x180519cfb  mov     edx, 1
0x180519d00  mov     ecx, [rbp+80h+arg_28]
0x180519d06  call    ?ScaleForDPI@Art@@YAHV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@H@Z; Art::ScaleForDPI(Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::DeviceIndependentPixels>>,int)
0x180519d0b  mov     r15d, eax
0x180519d0e  xorps   xmm0, xmm0
0x180519d11  movups  xmmword ptr [rbp+80h+rc.left], xmm0
0x180519d15  movups  xmm7, xmmword ptr [rbx]
0x180519d18  movaps  xmmword ptr [rbp+80h+var_D4+4], xmm7
0x180519d1c  mov     [rsp+180h+yBottom], eax; yBottom
0x180519d20  mov     r9d, eax; xRight
0x180519d23  mov     r8d, eax; yTop
0x180519d26  mov     edx, eax; xLeft
0x180519d28  lea     rcx, [rbp+80h+rc]; lprc
0x180519d2c  call    cs:__imp_SetRect
0x180519d32  mov     r11d, [rbp+80h+rc.left]
0x180519d36  movd    r12d, xmm7
0x180519d3b  add     r12d, r11d
0x180519d3e  mov     dword ptr [rbp+80h+var_D4+4], r12d
0x180519d42  mov     r10d, [rbp+80h+rc.right]
0x180519d46  mov     edi, [rbp+80h+var_C8]
0x180519d49  cmp     r12d, edi
0x180519d4c  jle     loc_18051A677
0x180519d52  mov     r12d, edi
0x180519d55  mov     dword ptr [rbp+80h+var_D4+4], edi
0x180519d58  mov     r9d, [rbp+80h+rc.top]
0x180519d5c  mov     ecx, [rbp-4Ch]
0x180519d5f  add     ecx, r9d
0x180519d62  mov     [rbp-4Ch], ecx
0x180519d65  mov     eax, [rbp-44h]
0x180519d68  cmp     ecx, eax
0x180519d6a  jle     loc_18051A689
0x180519d70  mov     [rbp-4Ch], eax
0x180519d73  movaps  xmm0, xmmword ptr [rbp+80h+var_D4+4]
0x180519d77  movdqa  xmmword ptr [rsp+180h+var_110], xmm0
0x180519d7d  lea     r13d, [r11+r12]
0x180519d81  mov     dword ptr [rbp+80h+var_F0], r13d
0x180519d85  mov     esi, dword ptr [rsp+180h+var_110+8]
0x180519d89  cmp     r13d, esi
0x180519d8c  jle     loc_18051A699
0x180519d92  mov     r13d, esi
0x180519d95  mov     dword ptr [rbp+80h+var_F0], esi
0x180519d98  mov     edx, dword ptr [rsp+180h+var_110+4]
0x180519d9c  add     edx, r9d
0x180519d9f  mov     [rsp+180h+var_140], edx
0x180519da3  mov     ebx, dword ptr [rsp+180h+var_110+0Ch]
0x180519da7  cmp     edx, ebx
0x180519da9  jle     loc_18051A6A8
0x180519daf  mov     edx, ebx
0x180519db1  mov     [rsp+180h+var_140], ebx
0x180519db5  mov     r14d, esi
0x180519db8  mov     eax, esi
0x180519dba  lea     ecx, [r11+r13]
0x180519dbe  mov     dword ptr [rbp+80h+var_100], ecx
0x180519dc1  mov     r8d, eax
0x180519dc4  cmp     ecx, esi
0x180519dc6  jle     loc_18051A6B5
0x180519dcc  mov     ecx, eax
0x180519dce  mov     dword ptr [rbp+80h+var_100], eax
0x180519dd1  add     edx, r9d
0x180519dd4  mov     dword ptr [rsp+180h+var_118], edx
0x180519dd8  cmp     edx, ebx
0x180519dda  jle     short loc_180519DE3
0x180519ddc  mov     dword ptr [rsp+180h+var_118], ebx
0x180519de0  mov     r8d, eax
0x180519de3  sub     r8d, r13d
0x180519de6  mov     [rbp+80h+var_90], r8d
0x180519dea  lea     eax, [r8+r15]
0x180519dee  cdq
0x180519def  mov     r8d, 2
0x180519df5  idiv    r8d
0x180519df8  mov     [rbp+80h+var_A0], eax
0x180519dfb  sub     ebx, eax
0x180519dfd  mov     dword ptr [rsp+180h+var_130], r14d
0x180519e02  lea     edx, [r11+rcx]
0x180519e06  mov     dword ptr [rsp+180h+var_128], edx
0x180519e0a  cmp     edx, r14d
0x180519e0d  jle     loc_18051A6C9
0x180519e13  mov     dword ptr [rsp+180h+var_128], r14d
0x180519e18  mov     ecx, dword ptr [rsp+180h+var_118]
0x180519e1c  add     ecx, r9d
0x180519e1f  mov     dword ptr [rsp+180h+var_130+4], ecx
0x180519e23  cmp     ecx, ebx
0x180519e25  jle     loc_18051A6DD
0x180519e2b  mov     [rbp+80h+var_D8], ebx
0x180519e2e  mov     dword ptr [rsp+180h+var_130+4], ebx
0x180519e32  mov     ecx, 328h
0x180519e37  lea     eax, [rcx+4]
0x180519e3a  cmp     [rbp+80h+var_E0], 1
0x180519e3e  cmovnz  ecx, eax
0x180519e41  call    cs:__imp_MsoCrCbvGet
0x180519e47  mov     ecx, eax
0x180519e49  shr     ecx, 10h
0x180519e4c  movzx   ecx, cl
0x180519e4f  movd    xmm2, ecx
0x180519e53  cvtdq2ps xmm2, xmm2
0x180519e56  movss   xmm6, cs:__real@437f0000
0x180519e5e  divss   xmm2, xmm6
0x180519e62  movzx   ecx, ax
0x180519e65  shr     cx, 8
0x180519e69  movzx   ecx, cx
0x180519e6c  movd    xmm1, ecx
0x180519e70  cvtdq2ps xmm1, xmm1
0x180519e73  divss   xmm1, xmm6
0x180519e77  movzx   eax, al
0x180519e7a  movd    xmm0, eax
0x180519e7e  cvtdq2ps xmm0, xmm0
0x180519e81  divss   xmm0, xmm6
0x180519e85  movss   dword ptr [rsp+180h+var_110], xmm0
0x180519e8b  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180519e91  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x180519e97  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x180519e9f  lea     rdx, [rsp+180h+var_110]
0x180519ea4  lea     rcx, [rbp+80h+var_B0]
0x180519ea8  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x180519eae  mov     ecx, 329h
0x180519eb3  lea     eax, [rcx+4]
0x180519eb6  cmp     [rbp+80h+var_E0], 1
0x180519eba  cmovnz  ecx, eax
0x180519ebd  call    cs:__imp_MsoCrCbvGet
0x180519ec3  mov     ecx, eax
0x180519ec5  shr     ecx, 10h
0x180519ec8  movzx   ecx, cl
0x180519ecb  movd    xmm2, ecx
0x180519ecf  cvtdq2ps xmm2, xmm2
0x180519ed2  divss   xmm2, xmm6
0x180519ed6  movzx   ecx, ax
0x180519ed9  shr     cx, 8
0x180519edd  movzx   ecx, cx
0x180519ee0  movd    xmm1, ecx
0x180519ee4  cvtdq2ps xmm1, xmm1
0x180519ee7  divss   xmm1, xmm6
0x180519eeb  movzx   eax, al
0x180519eee  movd    xmm0, eax
0x180519ef2  cvtdq2ps xmm0, xmm0
0x180519ef5  divss   xmm0, xmm6
0x180519ef9  movss   dword ptr [rsp+180h+var_110], xmm0
0x180519eff  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180519f05  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x180519f0b  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x180519f13  lea     rdx, [rsp+180h+var_110]
0x180519f18  lea     rcx, [rbp+80h+var_B8]
0x180519f1c  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x180519f22  lea     rcx, [rbp+80h+var_78]
0x180519f26  call    cs:__imp_?Create@IPathPrimitive@Gfx@@SA?AV?$TCntPtr@UIPathPrimitive@Gfx@@@Ofc@@XZ; Gfx::IPathPrimitive::Create(void)
0x180519f2c  xor     r9d, r9d
0x180519f2f  xor     r8d, r8d
0x180519f32  mov     rdx, [rbp+80h+var_78]
0x180519f36  lea     rcx, [rsp+180h+var_138]
0x180519f3b  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEAUIFigurePrimitive@2@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(Gfx::IFigurePrimitive &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x180519f41  movdqa  xmm0, xmm7
0x180519f45  psrldq  xmm0, 8
0x180519f4a  movd    [rbp+80h+var_DC], xmm0
0x180519f4f  movd    dword ptr [rbp+80h+var_D4], xmm7
0x180519f54  cmp     [rbp+80h+arg_30], 0
0x180519f5b  jnz     loc_18051A580
0x180519f61  cmp     [rbp+80h+var_E0], 1
0x180519f65  jz      loc_18051A580
0x180519f6b  mov     rcx, [rbp+80h+var_A8]
0x180519f6f  call    cs:__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ; NetUI::Fill::GetPrimaryARGBColor(void)
0x180519f75  mov     dword ptr [rbp+80h+var_A8], eax
0x180519f78  mov     ecx, 0Fh
0x180519f7d  call    cs:__imp_?MsoCrSysColorGet@@YAKH@Z; MsoCrSysColorGet(int)
0x180519f83  mov     edx, dword ptr [rbp+80h+var_A8]
0x180519f86  mov     ecx, edx
0x180519f88  and     ecx, 0FFFFFFh
0x180519f8e  cmp     ecx, eax
0x180519f90  jnz     loc_18051A50A
0x180519f96  mov     ecx, 15h
0x180519f9b  call    cs:__imp_?MsoCrSysColorGet@@YAKH@Z; MsoCrSysColorGet(int)
0x180519fa1  mov     edx, eax
0x180519fa3  mov     eax, edx
0x180519fa5  shr     eax, 10h
0x180519fa8  movzx   eax, al
0x180519fab  movd    xmm2, eax
0x180519faf  cvtdq2ps xmm2, xmm2
0x180519fb2  divss   xmm2, xmm6
0x180519fb6  movzx   eax, dx
0x180519fb9  shr     ax, 8
0x180519fbd  movzx   eax, ax
0x180519fc0  movd    xmm1, eax
0x180519fc4  cvtdq2ps xmm1, xmm1
0x180519fc7  divss   xmm1, xmm6
0x180519fcb  movzx   eax, dl
0x180519fce  movd    xmm0, eax
0x180519fd2  cvtdq2ps xmm0, xmm0
0x180519fd5  divss   xmm0, xmm6
0x180519fd9  movss   dword ptr [rsp+180h+var_110], xmm0
0x180519fdf  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180519fe5  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x180519feb  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x180519ff3  lea     rdx, [rsp+180h+var_110]
0x180519ff8  lea     rcx, [rbp+80h+var_98]
0x180519ffc  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x18051a002  mov     [rsp+180h+var_150], ebx; int
0x18051a006  mov     eax, dword ptr [rbp+80h+var_100]
0x18051a009  mov     [rsp+180h+var_158], eax; int
0x18051a00d  mov     eax, [rsp+180h+var_140]
0x18051a011  mov     [rsp+180h+yBottom], eax; int
0x18051a015  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x18051a018  mov     r8, [rbp+80h+var_98]; struct Gfx::IFigureShapeBuilder *
0x18051a01c  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x18051a021  mov     rcx, [rsp+180h+var_120]; this
0x18051a026  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x18051a02b  mov     eax, dword ptr [rsp+180h+var_118]
0x18051a02f  mov     [rsp+180h+var_150], eax; int
0x18051a033  mov     [rsp+180h+var_158], esi; int
0x18051a037  mov     eax, [rsp+180h+var_140]
0x18051a03b  mov     [rsp+180h+yBottom], eax; int
0x18051a03f  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x18051a042  mov     r8, [rbp+80h+var_98]; struct Gfx::IFigureShapeBuilder *
0x18051a046  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x18051a04b  mov     rcx, [rsp+180h+var_120]; this
0x18051a050  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x18051a055  mov     [rsp+180h+var_150], ebx; int
0x18051a059  mov     [rsp+180h+var_158], esi; int
0x18051a05d  mov     eax, [rsp+180h+var_140]
0x18051a061  mov     [rsp+180h+yBottom], eax; int
0x18051a065  mov     r9d, r14d; struct Gfx::IFigureStyle *
0x18051a068  mov     r8, [rbp+80h+var_98]; struct Gfx::IFigureShapeBuilder *
0x18051a06c  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x18051a071  mov     rcx, [rsp+180h+var_120]; this
0x18051a076  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x18051a07b  xor     edx, edx
0x18051a07d  mov     ecx, dword ptr [rbp+80h+var_A8]
0x18051a080  call    ?UtilAdjustBrightness@Art@@YAKKW4AdjustBrightnessDegree@1@@Z; Art::UtilAdjustBrightness(ulong,Art::AdjustBrightnessDegree)
0x18051a085  mov     ecx, eax
0x18051a087  shr     ecx, 10h
0x18051a08a  movzx   ecx, cl
0x18051a08d  movd    xmm2, ecx
0x18051a091  cvtdq2ps xmm2, xmm2
0x18051a094  divss   xmm2, xmm6
0x18051a098  movzx   ecx, ax
0x18051a09b  shr     cx, 8
0x18051a09f  movzx   ecx, cx
0x18051a0a2  movd    xmm1, ecx
0x18051a0a6  cvtdq2ps xmm1, xmm1
0x18051a0a9  divss   xmm1, xmm6
0x18051a0ad  movzx   eax, al
0x18051a0b0  movd    xmm0, eax
0x18051a0b4  cvtdq2ps xmm0, xmm0
0x18051a0b7  divss   xmm0, xmm6
0x18051a0bb  movss   dword ptr [rsp+180h+var_110], xmm0
0x18051a0c1  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x18051a0c7  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x18051a0cd  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x18051a0d5  lea     rdx, [rsp+180h+var_110]
0x18051a0da  lea     rcx, [rbp+80h+var_C0]
0x18051a0de  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x18051a0e4  nop
0x18051a0e5  mov     [rsp+180h+var_150], ebx; int
0x18051a0e9  mov     eax, dword ptr [rsp+180h+var_128]
0x18051a0ed  mov     [rsp+180h+var_158], eax; int
0x18051a0f1  mov     eax, dword ptr [rsp+180h+var_118]
0x18051a0f5  mov     [rsp+180h+yBottom], eax; int
0x18051a0f9  mov     r13d, dword ptr [rbp+80h+var_100]
0x18051a0fd  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x18051a100  mov     r8, [rbp+80h+var_C0]; struct Gfx::IFigureShapeBuilder *
0x18051a104  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x18051a109  mov     rcx, [rsp+180h+var_120]; this
0x18051a10e  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x18051a113  mov     eax, dword ptr [rsp+180h+var_130+4]
0x18051a117  mov     [rsp+180h+var_150], eax; int
0x18051a11b  mov     [rsp+180h+var_158], r14d; int
0x18051a120  mov     eax, dword ptr [rsp+180h+var_118]
0x18051a124  mov     [rsp+180h+yBottom], eax; int
0x18051a128  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x18051a12b  mov     r8, [rbp+80h+var_C0]; struct Gfx::IFigureShapeBuilder *
0x18051a12f  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x18051a134  mov     rcx, [rsp+180h+var_120]; this
0x18051a139  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x18051a13e  mov     [rsp+180h+var_150], ebx; int
0x18051a142  mov     [rsp+180h+var_158], r14d; int
0x18051a147  mov     eax, dword ptr [rsp+180h+var_118]
0x18051a14b  mov     [rsp+180h+yBottom], eax; int
0x18051a14f  mov     r9d, dword ptr [rsp+180h+var_130]; struct Gfx::IFigureStyle *
0x18051a154  mov     r8, [rbp+80h+var_C0]; struct Gfx::IFigureShapeBuilder *
0x18051a158  mov     rdx, [rsp+180h+var_138]; struct Frame *
  ... truncated ...
```
