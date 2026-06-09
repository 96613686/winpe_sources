# Art::UtilDrawPointedThumb(Gfx::ITarget::Frame &,NetUI::Fill const &,tagRECT const &,Art::RenderState,NetUI::Fill const &,Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::DeviceIndependentPixels>>,bool)

- ea: `0x180546138`
- end: `0x180546c70`
- name: `?UtilDrawPointedThumb@Art@@YAXAEAVFrame@ITarget@Gfx@@AEBUFill@NetUI@@AEBUtagRECT@@W4RenderState@1@1V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@_N@Z`
- size: `2872`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180545ea8`

## callees

- `0x180278e70`
- `0x180279050`
- `0x180546138`
- `0x180546c70`
- `0x180546df0`
- `0x180546f60`

## import_xrefs

- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180546338`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x1805463ac`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18054648c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18054656e`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x1805466c5`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x180546338`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x1805463ac`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18054648c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18054656e`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x1805466c5`
- `gfx!?Create@IPathPrimitive@Gfx@@SA?AV?$TCntPtr@UIPathPrimitive@Gfx@@@Ofc@@XZ` at `0x1805463b6`
- `gfx!?Create@IPathPrimitive@Gfx@@SA?AV?$TCntPtr@UIPathPrimitive@Gfx@@@Ofc@@XZ` at `0x1805463b6`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEAUIFigurePrimitive@2@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1805463cb`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEAUIFigurePrimitive@2@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1805463cb`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x180546c04`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x180546c04`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x18054640d`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x18054642b`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x18054640d`
- `mso40uiWin32Client!__imp_?MsoCrSysColorGet@@YAKH@Z` at `0x18054642b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1805462d1`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18054634d`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1805462d1`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18054634d`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x1805463ff`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x180546b90`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x1805463ff`
- `mso40uiWin32Client!__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ` at `0x180546b90`
- `USER32!SetRect` at `0x1805461bc`
- `USER32!SetRect` at `0x1805461bc`

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
0x180546138  mov     rax, rsp
0x18054613b  mov     [rax+20h], rbx
0x18054613f  push    rbp
0x180546140  push    rsi
0x180546141  push    rdi
0x180546142  push    r12
0x180546144  push    r13
0x180546146  push    r14
0x180546148  push    r15
0x18054614a  lea     rbp, [rsp-50h]
0x18054614f  sub     rsp, 150h
0x180546156  movaps  xmmword ptr [rax-48h], xmm6
0x18054615a  movaps  xmmword ptr [rax-58h], xmm7
0x18054615e  mov     rax, cs:__security_cookie
0x180546165  xor     rax, rsp
0x180546168  mov     [rbp+80h+var_58], rax
0x18054616c  mov     [rbp+80h+var_E0], r9d
0x180546170  mov     rbx, r8
0x180546173  mov     [rbp+80h+var_88], rbx
0x180546177  mov     [rbp+80h+var_A8], rdx
0x18054617b  mov     [rsp+180h+var_120], rcx
0x180546180  mov     rax, [rbp+80h+arg_20]
0x180546187  mov     [rbp+80h+var_70], rax
0x18054618b  mov     edx, 1
0x180546190  mov     ecx, [rbp+80h+arg_28]
0x180546196  call    ?ScaleForDPI@Art@@YAHV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@H@Z; Art::ScaleForDPI(Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::DeviceIndependentPixels>>,int)
0x18054619b  mov     r15d, eax
0x18054619e  xorps   xmm0, xmm0
0x1805461a1  movups  xmmword ptr [rbp+80h+rc.left], xmm0
0x1805461a5  movups  xmm7, xmmword ptr [rbx]
0x1805461a8  movaps  xmmword ptr [rbp+80h+var_D4+4], xmm7
0x1805461ac  mov     [rsp+180h+yBottom], eax; yBottom
0x1805461b0  mov     r9d, eax; xRight
0x1805461b3  mov     r8d, eax; yTop
0x1805461b6  mov     edx, eax; xLeft
0x1805461b8  lea     rcx, [rbp+80h+rc]; lprc
0x1805461bc  call    cs:__imp_SetRect
0x1805461c2  mov     r11d, [rbp+80h+rc.left]
0x1805461c6  movd    r12d, xmm7
0x1805461cb  add     r12d, r11d
0x1805461ce  mov     dword ptr [rbp+80h+var_D4+4], r12d
0x1805461d2  mov     r10d, [rbp+80h+rc.right]
0x1805461d6  mov     edi, [rbp+80h+var_C8]
0x1805461d9  cmp     r12d, edi
0x1805461dc  jle     loc_180546B07
0x1805461e2  mov     r12d, edi
0x1805461e5  mov     dword ptr [rbp+80h+var_D4+4], edi
0x1805461e8  mov     r9d, [rbp+80h+rc.top]
0x1805461ec  mov     ecx, [rbp-4Ch]
0x1805461ef  add     ecx, r9d
0x1805461f2  mov     [rbp-4Ch], ecx
0x1805461f5  mov     eax, [rbp-44h]
0x1805461f8  cmp     ecx, eax
0x1805461fa  jle     loc_180546B19
0x180546200  mov     [rbp-4Ch], eax
0x180546203  movaps  xmm0, xmmword ptr [rbp+80h+var_D4+4]
0x180546207  movdqa  xmmword ptr [rsp+180h+var_110], xmm0
0x18054620d  lea     r13d, [r11+r12]
0x180546211  mov     dword ptr [rbp+80h+var_F0], r13d
0x180546215  mov     esi, dword ptr [rsp+180h+var_110+8]
0x180546219  cmp     r13d, esi
0x18054621c  jle     loc_180546B29
0x180546222  mov     r13d, esi
0x180546225  mov     dword ptr [rbp+80h+var_F0], esi
0x180546228  mov     edx, dword ptr [rsp+180h+var_110+4]
0x18054622c  add     edx, r9d
0x18054622f  mov     [rsp+180h+var_140], edx
0x180546233  mov     ebx, dword ptr [rsp+180h+var_110+0Ch]
0x180546237  cmp     edx, ebx
0x180546239  jle     loc_180546B38
0x18054623f  mov     edx, ebx
0x180546241  mov     [rsp+180h+var_140], ebx
0x180546245  mov     r14d, esi
0x180546248  mov     eax, esi
0x18054624a  lea     ecx, [r11+r13]
0x18054624e  mov     dword ptr [rbp+80h+var_100], ecx
0x180546251  mov     r8d, eax
0x180546254  cmp     ecx, esi
0x180546256  jle     loc_180546B45
0x18054625c  mov     ecx, eax
0x18054625e  mov     dword ptr [rbp+80h+var_100], eax
0x180546261  add     edx, r9d
0x180546264  mov     dword ptr [rsp+180h+var_118], edx
0x180546268  cmp     edx, ebx
0x18054626a  jle     short loc_180546273
0x18054626c  mov     dword ptr [rsp+180h+var_118], ebx
0x180546270  mov     r8d, eax
0x180546273  sub     r8d, r13d
0x180546276  mov     [rbp+80h+var_90], r8d
0x18054627a  lea     eax, [r8+r15]
0x18054627e  cdq
0x18054627f  mov     r8d, 2
0x180546285  idiv    r8d
0x180546288  mov     [rbp+80h+var_A0], eax
0x18054628b  sub     ebx, eax
0x18054628d  mov     dword ptr [rsp+180h+var_130], r14d
0x180546292  lea     edx, [r11+rcx]
0x180546296  mov     dword ptr [rsp+180h+var_128], edx
0x18054629a  cmp     edx, r14d
0x18054629d  jle     loc_180546B59
0x1805462a3  mov     dword ptr [rsp+180h+var_128], r14d
0x1805462a8  mov     ecx, dword ptr [rsp+180h+var_118]
0x1805462ac  add     ecx, r9d
0x1805462af  mov     dword ptr [rsp+180h+var_130+4], ecx
0x1805462b3  cmp     ecx, ebx
0x1805462b5  jle     loc_180546B6D
0x1805462bb  mov     [rbp+80h+var_D8], ebx
0x1805462be  mov     dword ptr [rsp+180h+var_130+4], ebx
0x1805462c2  mov     ecx, 328h
0x1805462c7  lea     eax, [rcx+4]
0x1805462ca  cmp     [rbp+80h+var_E0], 1
0x1805462ce  cmovnz  ecx, eax
0x1805462d1  call    cs:__imp_MsoCrCbvGet
0x1805462d7  mov     ecx, eax
0x1805462d9  shr     ecx, 10h
0x1805462dc  movzx   ecx, cl
0x1805462df  movd    xmm2, ecx
0x1805462e3  cvtdq2ps xmm2, xmm2
0x1805462e6  movss   xmm6, cs:__real@437f0000
0x1805462ee  divss   xmm2, xmm6
0x1805462f2  movzx   ecx, ax
0x1805462f5  shr     cx, 8
0x1805462f9  movzx   ecx, cx
0x1805462fc  movd    xmm1, ecx
0x180546300  cvtdq2ps xmm1, xmm1
0x180546303  divss   xmm1, xmm6
0x180546307  movzx   eax, al
0x18054630a  movd    xmm0, eax
0x18054630e  cvtdq2ps xmm0, xmm0
0x180546311  divss   xmm0, xmm6
0x180546315  movss   dword ptr [rsp+180h+var_110], xmm0
0x18054631b  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180546321  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x180546327  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x18054632f  lea     rdx, [rsp+180h+var_110]
0x180546334  lea     rcx, [rbp+80h+var_B0]
0x180546338  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x18054633e  mov     ecx, 329h
0x180546343  lea     eax, [rcx+4]
0x180546346  cmp     [rbp+80h+var_E0], 1
0x18054634a  cmovnz  ecx, eax
0x18054634d  call    cs:__imp_MsoCrCbvGet
0x180546353  mov     ecx, eax
0x180546355  shr     ecx, 10h
0x180546358  movzx   ecx, cl
0x18054635b  movd    xmm2, ecx
0x18054635f  cvtdq2ps xmm2, xmm2
0x180546362  divss   xmm2, xmm6
0x180546366  movzx   ecx, ax
0x180546369  shr     cx, 8
0x18054636d  movzx   ecx, cx
0x180546370  movd    xmm1, ecx
0x180546374  cvtdq2ps xmm1, xmm1
0x180546377  divss   xmm1, xmm6
0x18054637b  movzx   eax, al
0x18054637e  movd    xmm0, eax
0x180546382  cvtdq2ps xmm0, xmm0
0x180546385  divss   xmm0, xmm6
0x180546389  movss   dword ptr [rsp+180h+var_110], xmm0
0x18054638f  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180546395  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x18054639b  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x1805463a3  lea     rdx, [rsp+180h+var_110]
0x1805463a8  lea     rcx, [rbp+80h+var_B8]
0x1805463ac  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x1805463b2  lea     rcx, [rbp+80h+var_78]
0x1805463b6  call    cs:__imp_?Create@IPathPrimitive@Gfx@@SA?AV?$TCntPtr@UIPathPrimitive@Gfx@@@Ofc@@XZ; Gfx::IPathPrimitive::Create(void)
0x1805463bc  xor     r9d, r9d
0x1805463bf  xor     r8d, r8d
0x1805463c2  mov     rdx, [rbp+80h+var_78]
0x1805463c6  lea     rcx, [rsp+180h+var_138]
0x1805463cb  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEAUIFigurePrimitive@2@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(Gfx::IFigurePrimitive &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x1805463d1  movdqa  xmm0, xmm7
0x1805463d5  psrldq  xmm0, 8
0x1805463da  movd    [rbp+80h+var_DC], xmm0
0x1805463df  movd    dword ptr [rbp+80h+var_D4], xmm7
0x1805463e4  cmp     [rbp+80h+arg_30], 0
0x1805463eb  jnz     loc_180546A10
0x1805463f1  cmp     [rbp+80h+var_E0], 1
0x1805463f5  jz      loc_180546A10
0x1805463fb  mov     rcx, [rbp+80h+var_A8]
0x1805463ff  call    cs:__imp_?GetPrimaryARGBColor@Fill@NetUI@@QEBAKXZ; NetUI::Fill::GetPrimaryARGBColor(void)
0x180546405  mov     dword ptr [rbp+80h+var_A8], eax
0x180546408  mov     ecx, 0Fh
0x18054640d  call    cs:__imp_?MsoCrSysColorGet@@YAKH@Z; MsoCrSysColorGet(int)
0x180546413  mov     edx, dword ptr [rbp+80h+var_A8]
0x180546416  mov     ecx, edx
0x180546418  and     ecx, 0FFFFFFh
0x18054641e  cmp     ecx, eax
0x180546420  jnz     loc_18054699A
0x180546426  mov     ecx, 15h
0x18054642b  call    cs:__imp_?MsoCrSysColorGet@@YAKH@Z; MsoCrSysColorGet(int)
0x180546431  mov     edx, eax
0x180546433  mov     eax, edx
0x180546435  shr     eax, 10h
0x180546438  movzx   eax, al
0x18054643b  movd    xmm2, eax
0x18054643f  cvtdq2ps xmm2, xmm2
0x180546442  divss   xmm2, xmm6
0x180546446  movzx   eax, dx
0x180546449  shr     ax, 8
0x18054644d  movzx   eax, ax
0x180546450  movd    xmm1, eax
0x180546454  cvtdq2ps xmm1, xmm1
0x180546457  divss   xmm1, xmm6
0x18054645b  movzx   eax, dl
0x18054645e  movd    xmm0, eax
0x180546462  cvtdq2ps xmm0, xmm0
0x180546465  divss   xmm0, xmm6
0x180546469  movss   dword ptr [rsp+180h+var_110], xmm0
0x18054646f  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180546475  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x18054647b  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x180546483  lea     rdx, [rsp+180h+var_110]
0x180546488  lea     rcx, [rbp+80h+var_98]
0x18054648c  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x180546492  mov     [rsp+180h+var_150], ebx; int
0x180546496  mov     eax, dword ptr [rbp+80h+var_100]
0x180546499  mov     [rsp+180h+var_158], eax; int
0x18054649d  mov     eax, [rsp+180h+var_140]
0x1805464a1  mov     [rsp+180h+yBottom], eax; int
0x1805464a5  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x1805464a8  mov     r8, [rbp+80h+var_98]; struct Gfx::IFigureShapeBuilder *
0x1805464ac  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x1805464b1  mov     rcx, [rsp+180h+var_120]; this
0x1805464b6  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x1805464bb  mov     eax, dword ptr [rsp+180h+var_118]
0x1805464bf  mov     [rsp+180h+var_150], eax; int
0x1805464c3  mov     [rsp+180h+var_158], esi; int
0x1805464c7  mov     eax, [rsp+180h+var_140]
0x1805464cb  mov     [rsp+180h+yBottom], eax; int
0x1805464cf  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x1805464d2  mov     r8, [rbp+80h+var_98]; struct Gfx::IFigureShapeBuilder *
0x1805464d6  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x1805464db  mov     rcx, [rsp+180h+var_120]; this
0x1805464e0  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x1805464e5  mov     [rsp+180h+var_150], ebx; int
0x1805464e9  mov     [rsp+180h+var_158], esi; int
0x1805464ed  mov     eax, [rsp+180h+var_140]
0x1805464f1  mov     [rsp+180h+yBottom], eax; int
0x1805464f5  mov     r9d, r14d; struct Gfx::IFigureStyle *
0x1805464f8  mov     r8, [rbp+80h+var_98]; struct Gfx::IFigureShapeBuilder *
0x1805464fc  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x180546501  mov     rcx, [rsp+180h+var_120]; this
0x180546506  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x18054650b  xor     edx, edx
0x18054650d  mov     ecx, dword ptr [rbp+80h+var_A8]
0x180546510  call    ?UtilAdjustBrightness@Art@@YAKKW4AdjustBrightnessDegree@1@@Z; Art::UtilAdjustBrightness(ulong,Art::AdjustBrightnessDegree)
0x180546515  mov     ecx, eax
0x180546517  shr     ecx, 10h
0x18054651a  movzx   ecx, cl
0x18054651d  movd    xmm2, ecx
0x180546521  cvtdq2ps xmm2, xmm2
0x180546524  divss   xmm2, xmm6
0x180546528  movzx   ecx, ax
0x18054652b  shr     cx, 8
0x18054652f  movzx   ecx, cx
0x180546532  movd    xmm1, ecx
0x180546536  cvtdq2ps xmm1, xmm1
0x180546539  divss   xmm1, xmm6
0x18054653d  movzx   eax, al
0x180546540  movd    xmm0, eax
0x180546544  cvtdq2ps xmm0, xmm0
0x180546547  divss   xmm0, xmm6
0x18054654b  movss   dword ptr [rsp+180h+var_110], xmm0
0x180546551  movss   dword ptr [rsp+180h+var_110+4], xmm1
0x180546557  movss   dword ptr [rsp+180h+var_110+8], xmm2
0x18054655d  mov     dword ptr [rsp+180h+var_110+0Ch], 3F800000h
0x180546565  lea     rdx, [rsp+180h+var_110]
0x18054656a  lea     rcx, [rbp+80h+var_C0]
0x18054656e  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z; Gfx::IFigureStyle::Create(GEL::Color const &)
0x180546574  nop
0x180546575  mov     [rsp+180h+var_150], ebx; int
0x180546579  mov     eax, dword ptr [rsp+180h+var_128]
0x18054657d  mov     [rsp+180h+var_158], eax; int
0x180546581  mov     eax, dword ptr [rsp+180h+var_118]
0x180546585  mov     [rsp+180h+yBottom], eax; int
0x180546589  mov     r13d, dword ptr [rbp+80h+var_100]
0x18054658d  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x180546590  mov     r8, [rbp+80h+var_C0]; struct Gfx::IFigureShapeBuilder *
0x180546594  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x180546599  mov     rcx, [rsp+180h+var_120]; this
0x18054659e  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x1805465a3  mov     eax, dword ptr [rsp+180h+var_130+4]
0x1805465a7  mov     [rsp+180h+var_150], eax; int
0x1805465ab  mov     [rsp+180h+var_158], r14d; int
0x1805465b0  mov     eax, dword ptr [rsp+180h+var_118]
0x1805465b4  mov     [rsp+180h+yBottom], eax; int
0x1805465b8  mov     r9d, r13d; struct Gfx::IFigureStyle *
0x1805465bb  mov     r8, [rbp+80h+var_C0]; struct Gfx::IFigureShapeBuilder *
0x1805465bf  mov     rdx, [rsp+180h+var_138]; struct Frame *
0x1805465c4  mov     rcx, [rsp+180h+var_120]; this
0x1805465c9  call    ?UtilFillSB@Art@@YAXAEAVFrame@ITarget@Gfx@@AEAUIFigureShapeBuilder@4@AEAUIFigureStyle@4@HHHH@Z; Art::UtilFillSB(Gfx::ITarget::Frame &,Gfx::IFigureShapeBuilder &,Gfx::IFigureStyle &,int,int,int,int)
0x1805465ce  mov     [rsp+180h+var_150], ebx; int
0x1805465d2  mov     [rsp+180h+var_158], r14d; int
0x1805465d7  mov     eax, dword ptr [rsp+180h+var_118]
0x1805465db  mov     [rsp+180h+yBottom], eax; int
0x1805465df  mov     r9d, dword ptr [rsp+180h+var_130]; struct Gfx::IFigureStyle *
0x1805465e4  mov     r8, [rbp+80h+var_C0]; struct Gfx::IFigureShapeBuilder *
0x1805465e8  mov     rdx, [rsp+180h+var_138]; struct Frame *
  ... truncated ...
```
