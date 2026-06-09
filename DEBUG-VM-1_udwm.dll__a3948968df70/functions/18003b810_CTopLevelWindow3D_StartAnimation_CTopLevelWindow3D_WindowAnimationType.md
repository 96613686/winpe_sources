# CTopLevelWindow3D::StartAnimation(CTopLevelWindow3D::WindowAnimationType)

- ea: `0x18003b810`
- end: `0x18003c988`
- name: `?StartAnimation@CTopLevelWindow3D@@QEAAJW4WindowAnimationType@1@@Z`
- size: `4472`
- prototype: ``
- caller_count: `15`
- callee_count: `31`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015a84`
- `0x180015e4c`
- `0x18003b278`
- `0x18003b350`
- `0x18003d360`
- `0x18006f69c`
- `0x18008208c`
- `0x180084340`
- `0x180089dd4`
- `0x1800cc6f4`
- `0x1800cc75c`
- `0x1800cc76c`
- `0x1800cc7cc`
- `0x1800cc848`
- `0x1800d97bc`

## callees

- `0x180005e9c`
- `0x180010204`
- `0x180017100`
- `0x180017658`
- `0x18001f43c`
- `0x180024100`
- `0x180024150`
- `0x1800288f8`
- `0x180028954`
- `0x180034fc0`
- `0x180036de4`
- `0x18003761c`
- `0x18003aad0`
- `0x18003b810`
- `0x180050dfc`
- `0x180064908`
- `0x180064974`
- `0x180065cc8`
- `0x180067128`
- `0x18006f854`
- `0x180070614`
- `0x18007beb4`
- `0x18007bf74`
- `0x180083a34`
- `0x180083a60`
- `0x180087508`
- `0x180089e80`
- `0x180095130`
- `0x180095b28`
- `0x1800b5b28`
- `0x1800ea010`

## import_xrefs

- `USER32!GetWindowMinimizeRect` at `0x18003bba2`
- `USER32!GetWindowMinimizeRect` at `0x18003bba2`
- `USER32!IsRectEmpty` at `0x18003bbab`
- `USER32!IsRectEmpty` at `0x18003bbab`
- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x18003b932`
- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x18003b932`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationTransform` at `0x18003bd3c`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationTransform` at `0x18003bd9a`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationTransform` at `0x18003bd3c`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationTransform` at `0x18003bd9a`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationProperty` at `0x18003bceb`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeAnimationProperty` at `0x18003bceb`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeTimingFunction` at `0x18003bddd`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeTimingFunction` at `0x18003be17`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeTimingFunction` at `0x18003bddd`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeTimingFunction` at `0x18003be17`

## pseudocode

```c
__int64 __fastcall CTopLevelWindow3D::StartAnimation(__int64 a1, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 *v5; // rsi
  __int64 v6; // rcx
  int TimelineForTransform; // eax
  int ThemeAnimationTransform; // ebx
  int v9; // r8d
  __int64 v10; // r10
  float v11; // xmm15_4
  __m128i v12; // xmm13
  unsigned int v13; // eax
  int v14; // r9d
  float v15; // xmm13_4
  __m128i v16; // xmm12
  unsigned int v17; // eax
  float v18; // xmm12_4
  __m128i v19; // xmm11
  unsigned int v20; // eax
  float v21; // xmm11_4
  __m128i v22; // xmm0
  unsigned int v23; // eax
  unsigned int v24; // ecx
  LONG v25; // xmm0_4
  __m128i v26; // xmm6
  unsigned int v27; // eax
  LONG v28; // xmm6_4
  __m128i v29; // xmm14
  int v30; // ecx
  __m128i v31; // xmm3
  unsigned int v32; // eax
  unsigned __int32 bottom; // xmm14_4
  float v34; // xmm3_4
  __int32 v35; // xmm1_4
  float v36; // xmm1_4
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  float v40; // xmm9_4
  int v41; // ecx
  float v42; // xmm1_4
  __int64 Theme; // rax
  unsigned int i; // r13d
  __int64 v45; // rax
  unsigned int v46; // ebx
  _DWORD *v47; // r14
  __int64 v48; // rax
  __int64 v49; // rcx
  const struct std::nothrow_t *v50; // rdx
  int v51; // r12d
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r9
  unsigned int v55; // ebx
  void *v56; // rsi
  __int64 v57; // rax
  __int64 v58; // rax
  __int128 v59; // xmm0
  __int64 v60; // xmm1_8
  const struct std::nothrow_t *v61; // rdx
  float v62; // xmm8_4
  unsigned int v63; // eax
  unsigned int v64; // ecx
  int v65; // eax
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // r8
  __int64 v69; // r9
  int *v70; // rax
  float v71; // xmm3_4
  float v72; // xmm1_4
  float v73; // xmm6_4
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // r8
  __int64 v79; // r9
  unsigned int v80; // esi
  int v81; // eax
  __int64 v82; // r8
  __int64 v83; // r9
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // r8
  __int64 v87; // r9
  float v88; // xmm6_4
  float v89; // xmm15_4
  char v90; // si
  float v91; // xmm0_4
  __int64 v92; // r8
  __int64 v93; // r9
  float v94; // xmm0_4
  __int64 v95; // rax
  _DWORD *v96; // rdx
  __int64 v97; // r9
  int v98; // r10d
  __int64 v99; // r8
  float v100; // xmm8_4
  float v101; // xmm3_4
  float v102; // xmm6_4
  double v103; // xmm1_8
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // r8
  __int64 v107; // r9
  __int64 v108; // r8
  __int64 v109; // r9
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // r8
  __int64 v115; // r9
  CTimelineBase *v116; // rcx
  struct D2D_POINT_2F v117; // rax
  int v118; // edx
  int v119; // r8d
  int v120; // r9d
  __int64 v121; // rax
  unsigned int *v122; // rax
  const struct std::nothrow_t *v123; // rdx
  unsigned int v125; // [rsp+28h] [rbp-E0h]
  void *v126; // [rsp+30h] [rbp-D8h]
  unsigned int Buf1; // [rsp+48h] [rbp-C0h] BYREF
  struct tagRECT Buf1_8; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v129; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v130; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v131[40]; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v132; // [rsp+A0h] [rbp-68h] BYREF
  float v133; // [rsp+A4h] [rbp-64h] BYREF
  struct D2D_POINT_2F v134; // [rsp+A8h] [rbp-60h] BYREF
  struct D2D_POINT_2F v135; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v136[40]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v137; // [rsp+1E0h] [rbp+D8h] BYREF

  v137 = a2;
  *(_BYTE *)(a1 + 424) = 0;
  v129 = 0;
  v132 = 0;
  Buf1 = 0;
  v130 = 0;
  if ( !CDesktopManager::CheckAnyPreference(0x10u) )
  {
    v5 = (__int64 *)(a1 + 232);
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0qp_EtwEventWriteTransfer(v4, &UdwmAnimation_Start, a2, *(_QWORD *)(*v5 + 40));
    UDwmTrace::TopLevelWindow3D_StartAnimation<enum CTopLevelWindow3D::WindowAnimationType &>(&v137);
    Buf1_8 = 0;
    CTopLevelWindow3D::GetScenarioGuid(v6, a2, &Buf1_8);
    if ( memcmp_0(&Buf1_8, &GUID_NULL, 0x10u) )
    {
      wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(a1 + 272);
      if ( (int)DCompositionCreateAnimationStats(a1 + 272) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 272) + 24LL))(*(_QWORD *)(a1 + 272), 0);
    }
    *(_BYTE *)(*v5 + 739) &= ~8u;
    *(_DWORD *)(a1 + 280) = a2;
    *(_OWORD *)(a1 + 200) = 0;
    TimelineForTransform = CTopLevelWindow3D::EnsureSecondaryWindowRepresentation((CTopLevelWindow3D *)a1, 1);
    ThemeAnimationTransform = TimelineForTransform;
    if ( TimelineForTransform < 0 )
    {
      v125 = 1239;
      goto LABEL_42;
    }
    CSecondaryWindowRepresentation::GetRelativeWindowRect(*(CSecondaryWindowRepresentation **)(a1 + 240), &Buf1_8);
    v9 = Buf1_8.right - Buf1_8.left;
    v10 = *v5;
    v11 = (float)(Buf1_8.left + *(_DWORD *)(a1 + 216));
    v12 = _mm_cvtsi32_si128(Buf1_8.top + *(_DWORD *)(a1 + 220));
    v13 = 0;
    if ( Buf1_8.right - Buf1_8.left >= 0 )
      v13 = Buf1_8.right - Buf1_8.left;
    *(float *)&v130 = (float)(Buf1_8.left + *(_DWORD *)(a1 + 216));
    v14 = Buf1_8.bottom - Buf1_8.top;
    LODWORD(v15) = _mm_cvtepi32_ps(v12).m128_u32[0];
    v16 = _mm_cvtsi32_si128(v13);
    v17 = 0;
    if ( Buf1_8.bottom - Buf1_8.top >= 0 )
      v17 = Buf1_8.bottom - Buf1_8.top;
    *((float *)&v130 + 1) = v15;
    LODWORD(v18) = _mm_cvtepi32_ps(v16).m128_u32[0];
    v19 = _mm_cvtsi32_si128(v17);
    v20 = Buf1_8.left + *(_DWORD *)(v10 + 48);
    *((float *)&v130 + 2) = v18;
    LODWORD(v21) = _mm_cvtepi32_ps(v19).m128_u32[0];
    v22 = _mm_cvtsi32_si128(v20);
    v23 = Buf1_8.top + *(_DWORD *)(v10 + 52);
    *((float *)&v130 + 3) = v21;
    v24 = Buf1_8.bottom - Buf1_8.top;
    v25 = _mm_cvtepi32_ps(v22).m128_u32[0];
    v26 = _mm_cvtsi32_si128(v23);
    v27 = 0;
    if ( v9 >= 0 )
      v27 = Buf1_8.right - Buf1_8.left;
    Buf1_8.left = v25;
    v28 = _mm_cvtepi32_ps(v26).m128_u32[0];
    if ( v14 < 0 )
      v24 = 0;
    v29 = _mm_cvtsi32_si128(v24);
    v30 = 274452;
    v31 = _mm_cvtsi32_si128(v27);
    v32 = *(_DWORD *)(a1 + 280);
    Buf1_8.top = v28;
    bottom = _mm_cvtepi32_ps(v29).m128_u32[0];
    Buf1_8.bottom = bottom;
    Buf1_8.right = _mm_cvtepi32_ps(v31).m128_u32[0];
    if ( v32 <= 0x12 && _bittest(&v30, v32) )
    {
      v11 = *(float *)(a1 + 428);
      v15 = *(float *)(a1 + 432);
      v18 = *(float *)(a1 + 436);
      if ( v9 < 0 )
        v9 = 0;
      v21 = *(float *)(a1 + 440);
      LODWORD(v130) = *(_DWORD *)(a1 + 428);
      if ( v14 < 0 )
        v14 = 0;
      *(_QWORD *)((char *)&v130 + 4) = __PAIR64__(LODWORD(v18), LODWORD(v15));
      v34 = (float)v9;
      *(float *)&bottom = (float)v14;
      *(float *)&Buf1_8.bottom = (float)v14;
      *((float *)&v130 + 3) = v21;
      *(float *)&Buf1_8.right = (float)v9;
      if ( *(char *)(v10 + 741) < 0 )
        *(_BYTE *)(a1 + 464) = 1;
      COERCE_FLOAT(v35 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
      if ( COERCE_FLOAT(LODWORD(v21) & v35) < 0.001 || COERCE_FLOAT(bottom & v35) < 0.001 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else if ( *(char *)(v10 + 741) >= 0 )
      {
        v36 = v34 / *(float *)&bottom;
        if ( (float)(v34 / *(float *)&bottom) <= (float)(v18 / v21) )
        {
          v21 = v21 + (float)((float)((float)(1.0 / v36) * v18) - v21);
          *((float *)&v130 + 3) = v21;
        }
        else
        {
          v18 = v18 + (float)((float)(v36 * v21) - v18);
          *((float *)&v130 + 2) = v18;
        }
      }
    }
    if ( ((*(_DWORD *)(a1 + 280) - 3) & 0xFFFFFFFD) == 0 )
    {
      GetWindowMinimizeRect(*(_QWORD *)(*v5 + 40), a1 + 200);
      if ( IsRectEmpty((const RECT *)(a1 + 200)) )
      {
        if ( *(_DWORD *)(a1 + 280) != 3 )
          goto LABEL_146;
        *(_DWORD *)(a1 + 280) = 6;
      }
      else
      {
        CTopLevelWindow3D::GetFinalMinRect(
          (struct tagRECT *)(a1 + 200),
          v21 / v18,
          (struct D2D_POINTANDSIZE_F *)&Buf1_8);
        bottom = Buf1_8.bottom;
      }
    }
    v37 = *(unsigned int *)(a1 + 280);
    if ( (unsigned int)(v37 - 7) <= 2 )
    {
      v40 = *((float *)CDesktopManager::GetWindowAnimationSettings() + 4);
      if ( v41 == 7 )
        v42 = FLOAT_1_0;
      else
        v42 = 0.0;
      *(_QWORD *)v131 = 4;
      memset(&v131[8], 0, 32);
      TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 4, v38, v39, LODWORD(v42), v131);
      ThemeAnimationTransform = TimelineForTransform;
      if ( TimelineForTransform < 0 )
      {
        v125 = 1347;
LABEL_42:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, TimelineForTransform, v125, 0);
        return (unsigned int)ThemeAnimationTransform;
      }
LABEL_139:
      v116 = *(CTimelineBase **)(a1 + 264);
      if ( v116 )
      {
        CTimelineBase::Restart(v116, v40);
LABEL_145:
        v122 = (unsigned int *)___ConvertDirtyEnumToFlag__MW4DTCVIDirtyFlags_CDesktopThumbnailCVIVisual__09_00__YA_AVDirtyFlags__XZ(&v133);
        CVisual::SetDirtyFlags(a1, *v122);
        goto LABEL_146;
      }
      v117 = (struct D2D_POINT_2F)CTimeline<float>::operator new();
      v135 = v117;
      if ( v117 )
      {
        v121 = CTimeline<float>::CTimeline<float>(LODWORD(v117.x), v118, v119, v120, 0);
        *(_QWORD *)(a1 + 264) = v121;
        if ( v121 )
        {
          if ( (int)CDesktopManager::RegisterForGlobalTimeChangeNotification((struct CVisual *)a1) >= 0 )
            ++*((_DWORD *)CDesktopManager::s_pDesktopManagerInstance + 10);
          goto LABEL_145;
        }
      }
      else
      {
        *(_QWORD *)(a1 + 264) = 0;
      }
      ThemeAnimationTransform = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x6A6u, 0);
      return (unsigned int)ThemeAnimationTransform;
    }
    if ( (unsigned int)(v37 - 16) <= 1 )
    {
      v95 = *(_QWORD *)(a1 + 240);
      v96 = (_DWORD *)(a1 + 452);
      v40 = FLOAT_0_167;
      v97 = *(unsigned int *)(v95 + 88);
      v98 = *(_DWORD *)(v95 + 96);
      *(_OWORD *)v131 = xmmword_1800FA1D8;
      *(_QWORD *)&v131[32] = 0x3FF0000000000000LL;
      *(_OWORD *)&v131[16] = xmmword_1800FA1E8;
      if ( (_DWORD)v37 == 16 )
      {
        *(_DWORD *)(a1 + 448) -= (int)v11;
        *v96 -= (int)v15;
      }
      v99 = (unsigned int)*v96;
      v100 = *(float *)(a1 + 444);
      v101 = (float)*(int *)(a1 + 448) * (float)(1.0 - v100);
      v102 = (float)(int)v99 * (float)(1.0 - v100);
      if ( (_DWORD)v37 == 16 )
      {
        v103 = 1.0 - v100;
        *(_DWORD *)(a1 + 456) = (int)((double)((int)v97 + *(_DWORD *)(a1 + 448)) * v103);
        *(_DWORD *)(a1 + 460) = (int)((double)((int)v99 + v98) * v103);
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 0, v99, v97, LODWORD(v101), v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1371;
          goto LABEL_42;
        }
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 1, v104, v105, LODWORD(v102), v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1372;
          goto LABEL_42;
        }
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                 a1,
                                 2,
                                 v106,
                                 v107,
                                 *(_DWORD *)(a1 + 444),
                                 v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1373;
          goto LABEL_42;
        }
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                 a1,
                                 3,
                                 v108,
                                 v109,
                                 *(_DWORD *)(a1 + 444),
                                 v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1374;
          goto LABEL_42;
        }
      }
      else
      {
        *(_QWORD *)(a1 + 456) = 0;
        *(_DWORD *)(a1 + 444) = 1065353216;
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 0, v99, v97, 0, v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1382;
          goto LABEL_42;
        }
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 1, v110, v111, 0, v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1383;
          goto LABEL_42;
        }
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                 a1,
                                 2,
                                 v112,
                                 v113,
                                 LODWORD(FLOAT_1_0),
                                 v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1384;
          goto LABEL_42;
        }
        TimelineForTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                 a1,
                                 3,
                                 v114,
                                 v115,
                                 LODWORD(FLOAT_1_0),
                                 v131);
        ThemeAnimationTransform = TimelineForTransform;
        if ( TimelineForTransform < 0 )
        {
          v125 = 1385;
          goto LABEL_42;
        }
      }
      goto LABEL_139;
    }
    TimelineForTransform = CTopLevelWindow3D::GetAnimationIds(v37, (unsigned int)v37, (char *)&v129 + 4, &v129);
    ThemeAnimationTransform = TimelineForTransform;
    if ( TimelineForTransform < 0 )
    {
      v125 = 1391;
      goto LABEL_42;
    }
    Theme = CDesktopManager::GetTheme(3);
    TimelineForTransform = GetThemeAnimationProperty(Theme, HIDWORD(v129), (unsigned int)v129, 1, &v132, 4, &Buf1);
    ThemeAnimationTransform = TimelineForTransform;
    if ( TimelineForTransform < 0 )
    {
      v125 = 1398;
      goto LABEL_42;
    }
    v40 = 0.0;
    for ( i = 0; ; ++i )
    {
      if ( i >= v132 )
        goto LABEL_139;
      v45 = CDesktopManager::GetTheme(3);
      LODWORD(v126) = 0;
      if ( (unsigned int)GetThemeAnimationTransform(v45, HIDWORD(v129), (unsigned int)v129, i, 0, v126, &Buf1) == -2147024662 )
        break;
LABEL_106:
      v15 = *((float *)&v130 + 1);
      v11 = *(float *)&v130;
    }
    v46 = Buf1;
    memset(v131, 0, sizeof(v131));
    v47 = operator new(Buf1);
    v48 = CDesktopManager::GetTheme(3);
    LODWORD(v126) = v46;
    ThemeAnimationTransform = GetThemeAnimationTransform(v48, HIDWORD(v129), (unsigned int)v129, i, v47, v126, &Buf1);
    if ( ThemeAnimationTransform < 0 )
    {
      v63 = 1422;
      goto LABEL_156;
    }
    if ( !(unsigned __int8)CTopLevelWindow3D::IsTransformSupported(v49, (unsigned int)*v47) )
    {
LABEL_105:
      CDisplayBlackCurtainAnimatedVisual::operator delete(v47, v50);
      goto LABEL_106;
    }
    v51 = v47[3];
    v52 = CDesktopManager::GetTheme(4);
    if ( (unsigned int)GetThemeTimingFunction(v52, (unsigned int)v47[1], 0, 0, &Buf1) == -2147024662 )
    {
      v55 = Buf1;
      v56 = operator new(Buf1);
      v57 = CDesktopManager::GetTheme(4);
      ThemeAnimationTransform = GetThemeTimingFunction(v57, (unsigned int)v47[1], v56, v55, &Buf1);
      if ( ThemeAnimationTransform < 0 )
      {
        v63 = 1441;
        goto LABEL_157;
      }
      v58 = CTopLevelWindow3D::ConvertTimingFunctionToInterpolationParameters(a1, v136, v56);
      v59 = *(_OWORD *)(v58 + 16);
      v60 = *(_QWORD *)(v58 + 32);
      *(_OWORD *)v131 = *(_OWORD *)v58;
      *(_OWORD *)&v131[16] = v59;
      *(_QWORD *)&v131[32] = v60;
      CDisplayBlackCurtainAnimatedVisual::operator delete(v56, v61);
    }
    v62 = (float)v51 / 1000.0;
    if ( *v47 )
    {
      if ( *v47 == 1 )
      {
        v64 = *(_DWORD *)(a1 + 280);
        if ( ((v64 - 3) & 0xFFFFFFFD) != 0 )
        {
          if ( (v47[4] & 1) != 0 )
          {
            if ( v64 > 0x12 || (v65 = 274452, !_bittest(&v65, v64)) )
            {
              ThemeAnimationTransform = -2147024809;
              v63 = 1612;
              goto LABEL_156;
            }
            v62 = *((float *)CDesktopManager::GetWindowAnimationSettings() + 5);
            ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                        a1,
                                        2,
                                        v66,
                                        v67,
                                        LODWORD(FLOAT_1_0),
                                        v131);
            if ( ThemeAnimationTransform < 0 )
            {
              v63 = 1601;
              goto LABEL_156;
            }
            ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                        a1,
                                        3,
                                        v68,
                                        v69,
                                        LODWORD(FLOAT_1_0),
                                        v131);
            if ( ThemeAnimationTransform < 0 )
            {
              v63 = 1607;
              goto LABEL_156;
            }
          }
          else
          {
            if ( (v47[4] & 4) != 0 )
            {
              v70 = *(int **)(a1 + 240);
              v71 = (float)v70[24];
              v72 = (float)v70[25];
              v133 = (float)((float)((float)((float)((float)((float)v70[22] + *(float *)&Buf1_8.right) + (float)v70[23])
                                           * *((float *)v47 + 9))
                                   - (float)v70[22])
                           / *(float *)&Buf1_8.right)
                   * *(float *)&Buf1_8.right;
              v73 = (float)((float)((float)((float)((float)((float)((float)(v71 + *(float *)&bottom) + v72)
                                                          * *((float *)v47 + 10))
                                                  - v71)
                                          / *(float *)&bottom)
                                  * *(float *)&bottom)
                          * (float)(1.0 - *((float *)v47 + 6)))
                  + (float)(*(float *)&Buf1_8.top - v15);
              if ( v64 == 10 || v64 == 11 )
              {
                if ( v64 == 10 )
                  v73 = v73 + (float)(int)(*((double *)CDesktopManager::s_pDesktopManagerInstance + 52) * 4.0);
                else
                  v73 = v73 + 0.0;
              }
              ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                          a1,
                                          0,
                                          v53,
                                          v54,
                                          (float)(v133 * (float)(1.0 - *((float *)v47 + 5)))
                                        + (float)(*(float *)&Buf1_8.left - v11),
                                          v131);
              if ( ThemeAnimationTransform < 0 )
              {
                v63 = 1658;
                goto LABEL_156;
              }
              ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(
                                          a1,
                                          1,
                                          v74,
                                          v75,
                                          LODWORD(v73),
                                          v131);
              if ( ThemeAnimationTransform < 0 )
              {
                v63 = 1659;
                goto LABEL_156;
              }
            }
            ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 2, v53, v54, v47[5], v131);
            if ( ThemeAnimationTransform < 0 )
            {
              v63 = 1663;
              goto LABEL_156;
            }
            ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 3, v76, v77, v47[6], v131);
            if ( ThemeAnimationTransform < 0 )
            {
              v63 = 1664;
              goto LABEL_156;
            }
          }
        }
        else
        {
          ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 2, v53, v54, v47[5], v131);
          if ( ThemeAnimationTransform < 0 )
          {
            v63 = 1578;
            goto LABEL_156;
          }
          ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 3, v78, v79, v47[6], v131);
          if ( ThemeAnimationTransform < 0 )
          {
            v63 = 1584;
            goto LABEL_156;
          }
        }
      }
      else if ( *v47 == 2 )
      {
        if ( (v47[4] & 1) != 0 )
        {
          ThemeAnimationTransform = -2147024809;
          v63 = 1672;
          goto LABEL_156;
        }
        ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 4, v53, v54, v47[5], v131);
        if ( ThemeAnimationTransform < 0 )
        {
          v63 = 1678;
          goto LABEL_156;
        }
      }
    }
    else
    {
      if ( (v47[4] & 1) == 0 )
      {
        ThemeAnimationTransform = -2147024809;
        v63 = 1456;
        goto LABEL_156;
      }
      v80 = *(_DWORD *)(a1 + 280);
      if ( ((v80 - 3) & 0xFFFFFFFD) == 0 )
        goto LABEL_95;
      if ( v80 <= 0xD && (v81 = 12308, _bittest(&v81, v80)) || (ThemeAnimationTransform = -2147024809, v80 == 18) )
        ThemeAnimationTransform = 0;
      if ( v80 - 10 <= 1 )
        goto LABEL_104;
      if ( ThemeAnimationTransform < 0 )
      {
        v63 = 1481;
        goto LABEL_156;
      }
      if ( v80 - 10 <= 1 )
        goto LABEL_104;
      if ( ((v80 - 3) & 0xFFFFFFFD) == 0 )
      {
LABEL_95:
        v134.x = 0.0;
        v88 = *(float *)&Buf1_8.left - v11;
        v89 = *(float *)&Buf1_8.top;
        v134.y = 0.0;
        if ( *(_BYTE *)(a1 + 425) )
        {
          v135 = *(struct D2D_POINT_2F *)&Buf1_8.left;
          CDisplayModeChangeAnimationHelper::AdjustMinimizeInitialPositionIfNeeded(
            *((const struct CDWMDisplaySet **)CDesktopManager::s_pDesktopManagerInstance + 18),
            (const struct D2D_POINTANDSIZE_F *)&v130,
            &v135,
            &v134);
        }
        if ( v80 == 3 )
        {
          v90 = 1;
          v91 = v88;
        }
        else
        {
          v90 = 0;
          v91 = 0.0;
        }
        ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 0, v53, v54, LODWORD(v91), v131);
        if ( ThemeAnimationTransform < 0 )
        {
          v63 = 1527;
          goto LABEL_156;
        }
        v94 = v89 - *((float *)&v130 + 1);
        if ( !v90 )
          v94 = 0.0;
        ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 1, v92, v93, LODWORD(v94), v131);
        if ( ThemeAnimationTransform < 0 )
        {
          v63 = 1534;
          goto LABEL_156;
        }
        goto LABEL_104;
      }
      v62 = *((float *)CDesktopManager::GetWindowAnimationSettings() + 5);
      ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 0, v82, v83, 0, v131);
      if ( ThemeAnimationTransform < 0 )
      {
        v63 = 1546;
        goto LABEL_156;
      }
      ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 1, v84, v85, 0, v131);
      if ( ThemeAnimationTransform < 0 )
      {
        v63 = 1553;
        goto LABEL_156;
      }
      *(_BYTE *)(a1 + 424) = 1;
      ThemeAnimationTransform = CTopLevelWindow3D::CreateTimelineForTransform(a1, 5, v86, v87, LODWORD(FLOAT_1_0), v131);
      if ( ThemeAnimationTransform < 0 )
      {
        v63 = 1562;
        goto LABEL_156;
      }
    }
LABEL_104:
    v40 = fmaxf(v62, v40);
    goto LABEL_105;
  }
LABEL_146:
  ThemeAnimationTransform = CTopLevelWindow3D::OnZOrderUpdated((CTopLevelWindow3D *)a1, 0);
  if ( ThemeAnimationTransform < 0 )
  {
    v63 = 1714;
    v47 = 0;
LABEL_156:
    v56 = 0;
LABEL_157:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, ThemeAnimationTransform, v63, 0);
    if ( v47 )
      CDisplayBlackCurtainAnimatedVisual::operator delete(v47, v123);
    if ( v56 )
      CDisplayBlackCurtainAnimatedVisual::operator delete(v56, v123);
  }
  else
  {
    UDwmTrace::TopLevelWindow3D_StartAnimationCompleted();
  }
  return (unsigned int)ThemeAnimationTransform;
}

```

## disassembly

```asm
0x18003b810  mov     rax, rsp
0x18003b813  mov     [rax+10h], edx
0x18003b816  push    rbp
0x18003b817  push    rbx
0x18003b818  push    rsi
0x18003b819  push    rdi
0x18003b81a  push    r12
0x18003b81c  push    r13
0x18003b81e  push    r14
0x18003b820  push    r15
0x18003b822  lea     rbp, [rax-0C8h]
0x18003b829  sub     rsp, 188h
0x18003b830  movaps  xmmword ptr [rax-58h], xmm6
0x18003b834  movaps  xmmword ptr [rax-68h], xmm7
0x18003b838  movaps  xmmword ptr [rax-78h], xmm8
0x18003b83d  movaps  xmmword ptr [rax-88h], xmm9
0x18003b845  movaps  xmmword ptr [rax-98h], xmm10
0x18003b84d  movaps  xmmword ptr [rax-0A8h], xmm11
0x18003b855  movaps  xmmword ptr [rax-0B8h], xmm12
0x18003b85d  movaps  xmmword ptr [rax-0C8h], xmm13
0x18003b865  movaps  xmmword ptr [rax-0D8h], xmm14
0x18003b86d  movaps  xmmword ptr [rax-0E8h], xmm15
0x18003b875  mov     rax, cs:__security_cookie
0x18003b87c  xor     rax, rsp
0x18003b87f  mov     [rbp+0C0h+var_E8], rax
0x18003b883  xor     r12d, r12d
0x18003b886  mov     rdi, rcx
0x18003b889  mov     [rcx+1A8h], r12b
0x18003b890  xorps   xmm0, xmm0
0x18003b893  mov     ebx, edx
0x18003b895  mov     dword ptr [rsp+1C0h+var_168+4], r12d
0x18003b89a  mov     dword ptr [rsp+1C0h+var_168], r12d
0x18003b89f  lea     r15d, [r12+10h]
0x18003b8a4  mov     [rbp+0C0h+var_128], r12d
0x18003b8a8  mov     ecx, r15d; unsigned int
0x18003b8ab  mov     dword ptr [rsp+1C0h+Buf1], r12d
0x18003b8b0  movups  [rsp+1C0h+var_168+8], xmm0
0x18003b8b5  call    ?CheckAnyPreference@CDesktopManager@@SA_NK@Z; CDesktopManager::CheckAnyPreference(ulong)
0x18003b8ba  test    al, al
0x18003b8bc  jnz     loc_18003C84E
0x18003b8c2  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x18003b8c9  lea     rsi, [rdi+0E8h]
0x18003b8d0  jz      short loc_18003B8E8
0x18003b8d2  mov     r9, [rsi]
0x18003b8d5  lea     rdx, UdwmAnimation_Start
0x18003b8dc  mov     r8d, ebx
0x18003b8df  mov     r9, [r9+28h]
0x18003b8e3  call    McTemplateU0qp_EtwEventWriteTransfer
0x18003b8e8  lea     rcx, [rbp+0C0h+arg_8]
0x18003b8ef  call    ??$TopLevelWindow3D_StartAnimation@AEAW4WindowAnimationType@CTopLevelWindow3D@@@UDwmTrace@@SAXAEAW4WindowAnimationType@CTopLevelWindow3D@@@Z; UDwmTrace::TopLevelWindow3D_StartAnimation<CTopLevelWindow3D::WindowAnimationType &>(CTopLevelWindow3D::WindowAnimationType &)
0x18003b8f4  xorps   xmm0, xmm0
0x18003b8f7  lea     r8, [rsp+1C0h+Buf1+8]
0x18003b8fc  mov     edx, ebx
0x18003b8fe  movups  [rsp+1C0h+Buf1+8], xmm0
0x18003b903  call    ?GetScenarioGuid@CTopLevelWindow3D@@AEAAXW4WindowAnimationType@1@PEAU_GUID@@@Z; CTopLevelWindow3D::GetScenarioGuid(CTopLevelWindow3D::WindowAnimationType,_GUID *)
0x18003b908  lea     rdx, GUID_NULL; Buf2
0x18003b90f  mov     r8, r15; Size
0x18003b912  lea     rcx, [rsp+1C0h+Buf1+8]; Buf1
0x18003b917  call    memcmp_0
0x18003b91c  test    eax, eax
0x18003b91e  jz      short loc_18003B94D
0x18003b920  lea     r14, [rdi+110h]
0x18003b927  mov     rcx, r14
0x18003b92a  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x18003b92f  mov     rcx, r14
0x18003b932  call    cs:__imp_DCompositionCreateAnimationStats
0x18003b938  test    eax, eax
0x18003b93a  js      short loc_18003B94D
0x18003b93c  mov     rcx, [r14]
0x18003b93f  xor     edx, edx
0x18003b941  mov     rax, [rcx]
0x18003b944  mov     rax, [rax+18h]
0x18003b948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b94d  mov     rax, [rsi]
0x18003b950  lea     r14, [rdi+0C8h]
0x18003b957  xorps   xmm0, xmm0
0x18003b95a  mov     dl, 1; bool
0x18003b95c  mov     rcx, rdi; this
0x18003b95f  and     byte ptr [rax+2E3h], 0F7h
0x18003b966  mov     [rdi+118h], ebx
0x18003b96c  movups  xmmword ptr [r14], xmm0
0x18003b970  call    ?EnsureSecondaryWindowRepresentation@CTopLevelWindow3D@@QEAAJ_N@Z; CTopLevelWindow3D::EnsureSecondaryWindowRepresentation(bool)
0x18003b975  mov     ebx, eax
0x18003b977  test    eax, eax
0x18003b979  js      loc_18003C8D5
0x18003b97f  mov     rcx, [rdi+0F0h]; this
0x18003b986  lea     rdx, [rsp+1C0h+Buf1+8]; retstr
0x18003b98b  call    ?GetRelativeWindowRect@CSecondaryWindowRepresentation@@QEBA?AUtagRECT@@XZ; CSecondaryWindowRepresentation::GetRelativeWindowRect(void)
0x18003b990  mov     ecx, dword ptr [rsp+1C0h+Buf1+0Ch]
0x18003b994  mov     edx, dword ptr [rsp+1C0h+Buf1+8]
0x18003b998  mov     r10d, [rdi+0D8h]
0x18003b99f  mov     r8d, [rsp+1C0h+var_170]
0x18003b9a4  add     r10d, edx
0x18003b9a7  mov     r9d, [rsp+1C0h+var_16C]
0x18003b9ac  mov     eax, [rdi+0DCh]
0x18003b9b2  movss   xmm10, cs:__real@3f800000
0x18003b9bb  add     eax, ecx
0x18003b9bd  sub     r8d, edx
0x18003b9c0  movd    xmm15, r10d
0x18003b9c5  mov     r10, [rsi]
0x18003b9c8  cvtdq2ps xmm15, xmm15
0x18003b9cc  movd    xmm13, eax
0x18003b9d1  mov     eax, r12d
0x18003b9d4  cmovns  eax, r8d
0x18003b9d8  movss   dword ptr [rsp+1C0h+var_168+8], xmm15
0x18003b9df  sub     r9d, ecx
0x18003b9e2  cvtdq2ps xmm13, xmm13
0x18003b9e6  movd    xmm12, eax
0x18003b9eb  mov     eax, r12d
0x18003b9ee  cmovns  eax, r9d
0x18003b9f2  movss   dword ptr [rsp+1C0h+var_168+0Ch], xmm13
0x18003b9f9  cvtdq2ps xmm12, xmm12
0x18003b9fd  movd    xmm11, eax
0x18003ba02  mov     eax, [r10+30h]
0x18003ba06  add     eax, edx
0x18003ba08  movss   dword ptr [rsp+1C0h+var_158], xmm12
0x18003ba0f  cvtdq2ps xmm11, xmm11
0x18003ba13  movd    xmm0, eax
0x18003ba17  mov     eax, [r10+34h]
0x18003ba1b  add     eax, ecx
0x18003ba1d  movss   dword ptr [rsp+1C0h+var_158+4], xmm11
0x18003ba24  test    r8d, r8d
0x18003ba27  mov     ecx, r9d
0x18003ba2a  cvtdq2ps xmm0, xmm0
0x18003ba2d  movd    xmm6, eax
0x18003ba31  mov     eax, r12d
0x18003ba34  cmovns  eax, r8d
0x18003ba38  movss   dword ptr [rsp+1C0h+Buf1+8], xmm0
0x18003ba3e  test    r9d, r9d
0x18003ba41  cvtdq2ps xmm6, xmm6
0x18003ba44  cmovs   ecx, r12d
0x18003ba48  movd    xmm14, ecx
0x18003ba4d  mov     ecx, 43014h
0x18003ba52  movd    xmm3, eax
0x18003ba56  mov     eax, [rdi+118h]
0x18003ba5c  movss   dword ptr [rsp+1C0h+Buf1+0Ch], xmm6
0x18003ba62  cvtdq2ps xmm14, xmm14
0x18003ba66  cvtdq2ps xmm3, xmm3
0x18003ba69  movss   [rsp+1C0h+var_16C], xmm14
0x18003ba70  movss   [rsp+1C0h+var_170], xmm3
0x18003ba76  cmp     eax, 12h
0x18003ba79  ja      loc_18003BB88
0x18003ba7f  bt      ecx, eax
0x18003ba82  jnb     loc_18003BB88
0x18003ba88  movss   xmm15, dword ptr [rdi+1ACh]
0x18003ba91  test    r8d, r8d
0x18003ba94  movss   xmm13, dword ptr [rdi+1B0h]
0x18003ba9d  movss   xmm12, dword ptr [rdi+1B4h]
0x18003baa6  cmovs   r8d, r12d
0x18003baaa  movss   xmm11, dword ptr [rdi+1B8h]
0x18003bab3  test    r9d, r9d
0x18003bab6  movss   dword ptr [rsp+1C0h+var_168+8], xmm15
0x18003babd  cmovs   r9d, r12d
0x18003bac1  movss   dword ptr [rsp+1C0h+var_168+0Ch], xmm13
0x18003bac8  movd    xmm3, r8d
0x18003bacd  cvtdq2ps xmm3, xmm3
0x18003bad0  movd    xmm14, r9d
0x18003bad5  cvtdq2ps xmm14, xmm14
0x18003bad9  movss   dword ptr [rsp+1C0h+var_158], xmm12
0x18003bae0  movss   [rsp+1C0h+var_16C], xmm14
0x18003bae7  movss   dword ptr [rsp+1C0h+var_158+4], xmm11
0x18003baee  movss   [rsp+1C0h+var_170], xmm3
0x18003baf4  cmp     [r10+2E5h], r12b
0x18003bafb  jge     short loc_18003BB04
0x18003bafd  mov     byte ptr [rdi+1D0h], 1
0x18003bb04  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18003bb0c  movaps  xmm0, xmm11
0x18003bb10  movss   xmm2, cs:__real@3a83126f
0x18003bb18  andps   xmm0, xmm1
0x18003bb1b  comiss  xmm2, xmm0
0x18003bb1e  ja      short loc_18003BB83
0x18003bb20  movaps  xmm0, xmm14
0x18003bb24  andps   xmm0, xmm1
0x18003bb27  comiss  xmm2, xmm0
0x18003bb2a  ja      short loc_18003BB83
0x18003bb2c  cmp     [r10+2E5h], r12b
0x18003bb33  jl      short loc_18003BB88
0x18003bb35  movaps  xmm1, xmm3
0x18003bb38  movaps  xmm0, xmm12
0x18003bb3c  divss   xmm1, xmm14
0x18003bb41  divss   xmm0, xmm11
0x18003bb46  comiss  xmm1, xmm0
0x18003bb49  jbe     short loc_18003BB63
0x18003bb4b  mulss   xmm1, xmm11
0x18003bb50  subss   xmm1, xmm12
0x18003bb55  addss   xmm12, xmm1
0x18003bb5a  movss   dword ptr [rsp+1C0h+var_158], xmm12
0x18003bb61  jmp     short loc_18003BB88
0x18003bb63  movaps  xmm0, xmm10
0x18003bb67  divss   xmm0, xmm1
0x18003bb6b  mulss   xmm0, xmm12
0x18003bb70  subss   xmm0, xmm11
0x18003bb75  addss   xmm11, xmm0
0x18003bb7a  movss   dword ptr [rsp+1C0h+var_158+4], xmm11
0x18003bb81  jmp     short loc_18003BB88
0x18003bb83  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false")
0x18003bb88  mov     eax, [rdi+118h]
0x18003bb8e  sub     eax, 3
0x18003bb91  test    eax, 0FFFFFFFDh
0x18003bb96  jnz     short loc_18003BBF1
0x18003bb98  mov     rcx, [rsi]
0x18003bb9b  mov     rdx, r14
0x18003bb9e  mov     rcx, [rcx+28h]
0x18003bba2  call    cs:__imp_GetWindowMinimizeRect
0x18003bba8  mov     rcx, r14; lprc
0x18003bbab  call    cs:__imp_IsRectEmpty
0x18003bbb1  test    eax, eax
0x18003bbb3  jz      short loc_18003BBCE
0x18003bbb5  cmp     dword ptr [rdi+118h], 3
0x18003bbbc  jnz     loc_18003C84E
0x18003bbc2  mov     dword ptr [rdi+118h], 6
0x18003bbcc  jmp     short loc_18003BBF1
0x18003bbce  movaps  xmm1, xmm11
0x18003bbd2  lea     r8, [rsp+1C0h+Buf1+8]; struct D2D_POINTANDSIZE_F *
0x18003bbd7  divss   xmm1, xmm12; float
0x18003bbdc  mov     rcx, r14; struct tagRECT *
0x18003bbdf  call    ?GetFinalMinRect@CTopLevelWindow3D@@SAXPEAUtagRECT@@MPEAUD2D_POINTANDSIZE_F@@@Z; CTopLevelWindow3D::GetFinalMinRect(tagRECT *,float,D2D_POINTANDSIZE_F *)
0x18003bbe4  movss   xmm14, [rsp+1C0h+var_16C]
0x18003bbeb  movss   xmm6, dword ptr [rsp+1C0h+Buf1+0Ch]
0x18003bbf1  mov     ecx, [rdi+118h]
0x18003bbf7  mov     esi, 2
0x18003bbfc  lea     eax, [rcx-7]
0x18003bbff  cmp     eax, esi
0x18003bc01  ja      loc_18003BC8C
0x18003bc07  call    ?GetWindowAnimationSettings@CDesktopManager@@SAAEBUWindowAnimationSettings@1@XZ; CDesktopManager::GetWindowAnimationSettings(void)
0x18003bc0c  xorps   xmm7, xmm7
0x18003bc0f  movss   xmm9, dword ptr [rax+10h]
0x18003bc15  cmp     ecx, 7
0x18003bc18  jnz     short loc_18003BC23
0x18003bc1a  xorps   xmm3, xmm3
0x18003bc1d  movaps  xmm1, xmm10
0x18003bc21  jmp     short loc_18003BC2A
0x18003bc23  xorps   xmm1, xmm1
0x18003bc26  movaps  xmm3, xmm10
0x18003bc2a  xorps   xmm0, xmm0
0x18003bc2d  mov     qword ptr [rsp+1C0h+var_158+8], 4
0x18003bc36  lea     rax, [rsp+1C0h+var_158+8]
0x18003bc3b  mov     edx, 4
0x18003bc40  mov     [rsp+1C0h+var_198], rax
0x18003bc45  movaps  xmm2, xmm9
0x18003bc49  mov     rcx, rdi
0x18003bc4c  movss   [rsp+1C0h+var_1A0], xmm1
0x18003bc52  movups  [rsp+1C0h+var_148], xmm0
0x18003bc57  movups  [rbp+0C0h+var_138], xmm0
0x18003bc5b  call    ?CreateTimelineForTransform@CTopLevelWindow3D@@AEAAJW4WindowTransformAttribute@1@MMMAEBUInterpolationParameters@@@Z; CTopLevelWindow3D::CreateTimelineForTransform(CTopLevelWindow3D::WindowTransformAttribute,float,float,float,InterpolationParameters const &)
0x18003bc60  mov     ebx, eax
0x18003bc62  test    eax, eax
0x18003bc64  jns     loc_18003C7D4
0x18003bc6a  mov     [rsp+1C0h+var_198], r12; void *
0x18003bc6f  mov     [rsp+1C0h+var_1A0], 543h; unsigned int
0x18003bc77  mov     r9d, eax; int
0x18003bc7a  xor     edx, edx; int *
0x18003bc7c  xor     r8d, r8d; unsigned int
0x18003bc7f  lea     ecx, [rdx+14h]; unsigned int
0x18003bc82  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18003bc87  jmp     loc_18003C927
0x18003bc8c  lea     eax, [rcx-10h]
0x18003bc8f  cmp     eax, 1
0x18003bc92  jbe     loc_18003C536
0x18003bc98  lea     r9, [rsp+1C0h+var_168]
0x18003bc9d  mov     edx, ecx
0x18003bc9f  lea     r8, [rsp+1C0h+var_168+4]
0x18003bca4  call    ?GetAnimationIds@CTopLevelWindow3D@@AEAAJW4WindowAnimationType@1@PEAH1@Z; CTopLevelWindow3D::GetAnimationIds(CTopLevelWindow3D::WindowAnimationType,int *,int *)
0x18003bca9  mov     ebx, eax
0x18003bcab  test    eax, eax
0x18003bcad  js      loc_18003C524
0x18003bcb3  mov     ecx, 3
0x18003bcb8  call    ?GetTheme@CDesktopManager@@SAPEAXW4ThemeClassName@1@@Z; CDesktopManager::GetTheme(CDesktopManager::ThemeClassName)
0x18003bcbd  mov     r8d, dword ptr [rsp+1C0h+var_168]
0x18003bcc2  mov     rcx, rax
0x18003bcc5  mov     edx, dword ptr [rsp+1C0h+var_168+4]
0x18003bcc9  lea     rax, [rsp+1C0h+Buf1]
0x18003bcce  mov     [rsp+1C0h+var_190], rax
0x18003bcd3  mov     r15d, 4
0x18003bcd9  lea     rax, [rbp+0C0h+var_128]
0x18003bcdd  mov     dword ptr [rsp+1C0h+var_198], r15d
0x18003bce2  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18003bce7  lea     r9d, [r15-3]
0x18003bceb  call    cs:__imp_GetThemeAnimationProperty
0x18003bcf1  mov     ebx, eax
0x18003bcf3  test    eax, eax
0x18003bcf5  js      loc_18003C512
0x18003bcfb  xorps   xmm7, xmm7
0x18003bcfe  xorps   xmm9, xmm9
0x18003bd02  mov     r13d, r12d
0x18003bd05  cmp     r13d, [rbp+0C0h+var_128]
0x18003bd09  jnb     loc_18003C7D4
0x18003bd0f  mov     ecx, 3
0x18003bd14  call    ?GetTheme@CDesktopManager@@SAPEAXW4ThemeClassName@1@@Z; CDesktopManager::GetTheme(CDesktopManager::ThemeClassName)
0x18003bd19  mov     r8d, dword ptr [rsp+1C0h+var_168]
0x18003bd1e  mov     rcx, rax
0x18003bd21  mov     edx, dword ptr [rsp+1C0h+var_168+4]
0x18003bd25  lea     rax, [rsp+1C0h+Buf1]
0x18003bd2a  mov     [rsp+1C0h+var_190], rax
0x18003bd2f  mov     r9d, r13d
0x18003bd32  mov     dword ptr [rsp+1C0h+var_198], r12d
0x18003bd37  mov     qword ptr [rsp+1C0h+var_1A0], r12
0x18003bd3c  call    cs:__imp_GetThemeAnimationTransform
0x18003bd42  cmp     eax, 800700EAh
0x18003bd47  jnz     loc_18003C44E
  ... truncated ...
```
