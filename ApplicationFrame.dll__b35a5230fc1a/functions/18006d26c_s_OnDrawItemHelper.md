# s_OnDrawItemHelper

- ea: `0x18006d26c`
- end: `0x18006dd02`
- name: `s_OnDrawItemHelper`
- size: `2710`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18006d230`

## callees

- `0x18000da80`
- `0x180039388`
- `0x18003f214`
- `0x180041ec0`
- `0x180043c30`
- `0x180044690`
- `0x1800446fc`
- `0x18006beb8`
- `0x18006c3f4`
- `0x18006c464`
- `0x18006c840`
- `0x18006c9bc`
- `0x18006cc70`
- `0x18006d26c`
- `0x18006e750`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006d8ef`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006d903`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006d8ef`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006d903`
- `SHCORE!__imp_GetScaleFactorForWindow` at `0x18006d2e0`
- `SHCORE!__imp_GetScaleFactorForWindow` at `0x18006d2e0`
- `UxTheme!CloseThemeData` at `0x18006dccb`
- `UxTheme!CloseThemeData` at `0x18006dccb`
- `UxTheme!OpenThemeData` at `0x18006d318`
- `UxTheme!OpenThemeData` at `0x18006d318`
- `UxTheme!GetThemeColor` at `0x18006d975`
- `UxTheme!GetThemeColor` at `0x18006d975`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18006d485`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18006d485`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetStockIconInfo` at `0x18006d7b5`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetStockIconInfo` at `0x18006d7b5`
- `ext-ms-win-uxtheme-themes-l1-1-0!DrawThemeBackground` at `0x18006d4e9`
- `ext-ms-win-uxtheme-themes-l1-1-0!DrawThemeBackground` at `0x18006dca3`
- `ext-ms-win-uxtheme-themes-l1-1-0!DrawThemeBackground` at `0x18006d4e9`
- `ext-ms-win-uxtheme-themes-l1-1-0!DrawThemeBackground` at `0x18006dca3`
- `ext-ms-win-uxtheme-themes-l1-1-0!IsThemePartDefined` at `0x18006d4a0`
- `ext-ms-win-uxtheme-themes-l1-1-0!IsThemePartDefined` at `0x18006d4a0`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeMargins` at `0x18006d433`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeMargins` at `0x18006d433`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x18006d2c6`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x18006d2c6`
- `GDI32!SetStretchBltMode` at `0x18006da3b`
- `GDI32!SetStretchBltMode` at `0x18006da3b`
- `GDI32!ExcludeClipRect` at `0x18006dcc1`
- `GDI32!ExcludeClipRect` at `0x18006dcc1`
- `GDI32!BitBlt` at `0x18006dab5`
- `GDI32!BitBlt` at `0x18006dab5`
- `GDI32!GetObjectW` at `0x18006d85a`
- `GDI32!GetObjectW` at `0x18006d9b8`
- `GDI32!GetObjectW` at `0x18006d85a`
- `GDI32!GetObjectW` at `0x18006d9b8`
- `GDI32!SelectObject` at `0x18006d98d`
- `GDI32!SelectObject` at `0x18006dad3`
- `GDI32!SelectObject` at `0x18006d98d`
- `GDI32!SelectObject` at `0x18006dad3`
- `GDI32!GdiAlphaBlend` at `0x18006da20`
- `GDI32!GdiAlphaBlend` at `0x18006da20`
- `GDI32!StretchBlt` at `0x18006da80`
- `GDI32!StretchBlt` at `0x18006da80`
- `USER32!WindowFromDC` at `0x18006d475`
- `USER32!WindowFromDC` at `0x18006d475`
- `USER32!DrawIconEx` at `0x18006d7fc`
- `USER32!DrawIconEx` at `0x18006d7fc`

## pseudocode

```c
__int64 __fastcall s_OnDrawItemHelper(HWND a1, __int64 a2, __int64 a3)
{
  int ScaleFactorForWindow; // ebx
  unsigned int v7; // r12d
  _BYTE *v8; // rdi
  const WCHAR *v9; // rdx
  __int64 v10; // rdx
  HTHEME v11; // r14
  int v12; // ebx
  unsigned int v13; // r14d
  __int64 v14; // rdx
  HTHEME v15; // rbx
  HDC v16; // rdx
  HWND v17; // rax
  unsigned int PropW; // r14d
  int v19; // r9d
  int v20; // r8d
  __int64 v21; // rdx
  int v22; // ebx
  int v23; // edi
  int v24; // r14d
  int v25; // esi
  int v26; // eax
  __int64 v27; // r9
  int v28; // eax
  HWND v29; // rsi
  int v30; // edi
  bool v31; // zf
  __int64 v32; // r8
  __int64 v33; // r9
  __m128i *v34; // rax
  __int64 v35; // r9
  __int64 v36; // rcx
  int v37; // ebx
  int v38; // eax
  int Error; // eax
  __int64 v40; // r8
  __int64 v41; // r9
  __m128i *v42; // rax
  __int64 v43; // r9
  __m128i v44; // xmm0
  __int64 v45; // rcx
  int v46; // edi
  int v47; // eax
  __int32 v48; // r14d
  int v49; // r14d
  SHSTOCKICONID v50; // ecx
  void *v51; // rdi
  int v52; // eax
  int v53; // r14d
  int v54; // ebx
  __int64 v55; // r9
  __int64 v56; // rcx
  int v57; // eax
  HDC v58; // rcx
  BOOL v59; // eax
  HDC v60; // rcx
  __int64 v61; // r9
  __int64 v62; // rcx
  int v63; // edi
  __int64 v64; // r8
  __int64 v65; // r9
  __m128i v66; // xmm6
  int v67; // ebx
  int v68; // eax
  __int64 v69; // rdx
  int v70; // r8d
  __int64 v71; // rdx
  int v72; // eax
  float v73; // xmm0_4
  HDC v74; // rdx
  int prc; // [rsp+30h] [rbp-D8h]
  UINT diFlags; // [rsp+48h] [rbp-C0h]
  UINT diFlagsa; // [rsp+48h] [rbp-C0h]
  char v79; // [rsp+68h] [rbp-A0h]
  int xLeft; // [rsp+6Ch] [rbp-9Ch] BYREF
  int yTop; // [rsp+70h] [rbp-98h]
  int yTop_4; // [rsp+74h] [rbp-94h]
  __m128i yTop_8; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v84; // [rsp+88h] [rbp-80h] BYREF
  COLORREF pColor; // [rsp+8Ch] [rbp-7Ch] BYREF
  HTHEME hTheme; // [rsp+90h] [rbp-78h]
  HWND hWnd; // [rsp+98h] [rbp-70h]
  _OWORD pv[2]; // [rsp+A0h] [rbp-68h] BYREF
  HGDIOBJ h; // [rsp+C0h] [rbp-48h]
  SHSTOCKICONINFO psii; // [rsp+C8h] [rbp-40h] BYREF
  HDC hdc[2]; // [rsp+2E8h] [rbp+1E0h] BYREF
  MARGINS pMargins; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE v93[46]; // [rsp+308h] [rbp+200h] BYREF
  __int16 v94; // [rsp+336h] [rbp+22Eh]
  int v95; // [rsp+338h] [rbp+230h]

  hWnd = a1;
  ScaleFactorForWindow = -2147418113;
  if ( a3 )
  {
    v7 = 2;
    if ( MonitorFromWindow(a1, 2u) )
    {
      v84 = 0;
      ScaleFactorForWindow = GetScaleFactorForWindow(a1, &v84);
      if ( ScaleFactorForWindow >= 0 )
      {
        v8 = (_BYTE *)(a3 + 69);
        if ( *(_BYTE *)(a3 + 68) )
        {
          v9 = L"DarkMode_ImmersiveStart::Menu";
        }
        else
        {
          v9 = L"LightMode_ImmersiveStart::Menu";
          if ( !*v8 )
            v9 = L"ImmersiveStart::Menu";
        }
        hTheme = OpenThemeData(0, v9);
        v11 = hTheme;
        if ( hTheme )
        {
          v12 = *(_DWORD *)(a2 + 16);
          yTop = v12;
          LOBYTE(v10) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_HVCZMTest>::GetImpl'::`2'::impl,
            v10);
          if ( !(unsigned int)IsHighContrast() )
            s_SetDwmAttributes(*(_QWORD *)(a2 + 24), v11);
          v13 = 6;
          if ( (*(_BYTE *)(a3 + 56) & 1) != 0 )
          {
            if ( *v8 || (v14 = 2, (*(_BYTE *)(a3 + 56) & 4) != 0) )
              v14 = 6;
            *(_DWORD *)(a2 + 44) += DPIToPPIHelpers::ScaleByType(
                                      *(unsigned int *)(a3 + 60),
                                      v14,
                                      a1,
                                      *(unsigned int *)(a3 + 64));
          }
          if ( (*(_BYTE *)(a3 + 56) & 2) != 0 )
          {
            if ( !*v8 && (*(_BYTE *)(a3 + 56) & 4) == 0 )
              v13 = 2;
            *(_DWORD *)(a2 + 52) -= DPIToPPIHelpers::ScaleByType(
                                      *(unsigned int *)(a3 + 60),
                                      v13,
                                      a1,
                                      *(unsigned int *)(a3 + 64));
          }
          if ( (v12 & 4) != 0 )
          {
            if ( (v12 & 1) != 0 && *(_QWORD *)a3 && **(_WORD **)a3 )
              v7 = 4;
            else
              v7 = 3;
          }
          else if ( (v12 & 1) == 0 || !*(_QWORD *)a3 || !**(_WORD **)a3 )
          {
            v7 = 1;
          }
          v15 = hTheme;
          v16 = *(HDC *)(a2 + 32);
          pMargins = 0;
          if ( GetThemeMargins(hTheme, v16, 27, v7, 3602, 0, &pMargins) >= 0 )
          {
            *(_DWORD *)(a2 + 40) += DPIToPPIHelpers::ScaleByType(
                                      *(unsigned int *)(a3 + 60),
                                      (unsigned int)pMargins.cxLeftWidth,
                                      a1,
                                      *(unsigned int *)(a3 + 64));
            *(_DWORD *)(a2 + 48) -= DPIToPPIHelpers::ScaleByType(
                                      *(unsigned int *)(a3 + 60),
                                      (unsigned int)pMargins.cxRightWidth,
                                      a1,
                                      *(unsigned int *)(a3 + 64));
          }
          v17 = WindowFromDC(*(HDC *)(a2 + 32));
          PropW = (unsigned int)GetPropW(v17, L"KB_FOCUS_MENU");
          if ( (unsigned int)IsHighContrast()
            || !IsThemePartDefined(v15, 26, 0)
            || !PropW
            || ((v7 - 2) & 0xFFFFFFFD) != 0 )
          {
            v19 = v7;
            v20 = 27;
          }
          else
          {
            v19 = 1;
            v20 = 26;
          }
          ScaleFactorForWindow = DrawThemeBackground(v15, *(HDC *)(a2 + 32), v20, v19, (LPCRECT)(a2 + 40), 0);
          if ( ScaleFactorForWindow < 0 )
            goto LABEL_98;
          v21 = 2048;
          if ( *(_QWORD *)a3 && **(_WORD **)a3 )
          {
            if ( *(_DWORD *)(a3 + 24) != 2048 )
            {
              v22 = *(_DWORD *)(a2 + 40);
              v23 = *(_DWORD *)(a2 + 44);
              v24 = *(_DWORD *)(a2 + 48);
              v25 = *(_DWORD *)(a2 + 52);
              v26 = DPIToPPIHelpers::ScaleByType(*(unsigned int *)(a3 + 60), 32, hWnd, *(unsigned int *)(a3 + 64));
              v27 = *(unsigned int *)(a3 + 64);
              HIDWORD(hdc[0]) = v23;
              LODWORD(hdc[0]) = v26 + v22;
              v28 = DPIToPPIHelpers::ScaleByType(*(unsigned int *)(a3 + 60), 17, hWnd, v27);
              HIDWORD(hdc[1]) = v25;
              v29 = hWnd;
              LODWORD(hdc[1]) = v24 - v28;
              ScaleFactorForWindow = s_DrawThemeTextPPIAware(hTheme, v7, (__int64)hWnd, a2, a3, (__m128i *)hdc);
              if ( ScaleFactorForWindow < 0 )
                goto LABEL_98;
              v30 = *(_DWORD *)(a2 + 52) - *(_DWORD *)(a2 + 44);
              LODWORD(hWnd) = v30;
              if ( (yTop & 8) != 0 && !*(_QWORD *)(a3 + 40) )
              {
                v31 = *(_DWORD *)(a3 + 60) == 1;
                yTop_8 = _mm_load_si128((const __m128i *)&_xmm);
                if ( v31 )
                {
                  v32 = v84;
                  v33 = 100;
                }
                else
                {
                  v33 = 96;
                  v32 = *(unsigned int *)(a3 + 64);
                }
                v34 = (__m128i *)Geometry::CRect::MulDiv(hdc, &yTop_8, v32, v33);
                v35 = *(unsigned int *)(a3 + 64);
                v36 = *(unsigned int *)(a3 + 60);
                v37 = *(_DWORD *)(a2 + 44);
                yTop_8 = *v34;
                v38 = v30 / 2 - (int)DPIToPPIHelpers::ScaleByType(v36, 16, v29, v35) / 2;
                yTop_8.m128i_i32[3] += v37 + v38;
                diFlags = *(_DWORD *)(a3 + 60);
                yTop_8.m128i_i32[1] += v37 + v38;
                prc = *(_DWORD *)(a3 + 24);
                *(__m128i *)hdc = yTop_8;
                Error = s_DrawGlyph(v29, 11, prc, v7, (__int64)hdc, diFlags);
                goto LABEL_61;
              }
              if ( *(_DWORD *)(a3 + 28) == -1 )
              {
                v51 = *(void **)(a3 + 32);
                if ( v51 || (yTop & 8) != 0 && (v51 = *(void **)(a3 + 40)) != 0 || (v51 = *(void **)(a3 + 48)) != 0 )
                {
                  memset(pv, 0, sizeof(pv));
                  ScaleFactorForWindow = -2147467259;
                  if ( !GetObjectW(v51, 32, pv) )
                    goto LABEL_98;
                  Microsoft::WRL::Wrappers::CompatibleDC::CompatibleDC(
                    (Microsoft::WRL::Wrappers::CompatibleDC *)hdc,
                    *(HDC *)(a2 + 32));
                  if ( hdc[1] || (ScaleFactorForWindow = ResultFromKnownLastError(), ScaleFactorForWindow >= 0) )
                  {
                    v52 = DPIToPPIHelpers::ScaleByType(*(unsigned int *)(a3 + 60), 16, v29, *(unsigned int *)(a3 + 64));
                    v53 = DWORD2(pv[0]);
                    v54 = DWORD1(pv[0]);
                    v79 = 0;
                    if ( SDWORD2(pv[0]) > v52 || SDWORD1(pv[0]) > v52 )
                    {
                      yTop = *(_DWORD *)(a3 + 64);
                      xLeft = 0;
                      SHComputeDPI(0, &xLeft, 0);
                      if ( xLeft > yTop )
                      {
                        v79 = 1;
                        v54 = MulDiv(v54, yTop, xLeft);
                        v53 = MulDiv(v53, yTop, xLeft);
                      }
                    }
                    v55 = *(unsigned int *)(a3 + 64);
                    v56 = *(unsigned int *)(a3 + 60);
                    yTop_4 = *(_DWORD *)(a2 + 44);
                    v57 = DPIToPPIHelpers::ScaleByType(v56, 16, v29, v55);
                    if ( v57 > v54 )
                    {
                      v79 = 1;
                      v57 = 2 * v57 - v54;
                    }
                    pColor = 0;
                    yTop = v57 / 2;
                    yTop_4 += ((int)hWnd - v53) / 2;
                    GetThemeColor(hTheme, 27, v7, 3803, &pColor);
                    yTop_8.m128i_i64[0] = (__int64)hdc[1];
                    h = SelectObject(hdc[1], v51);
                    memset_0(v93, 0, 0x68u);
                    if ( GetObjectW(v51, 104, v93) == 104 && v94 == 32 && !v95 )
                    {
                      v58 = *(HDC *)(a2 + 32);
                      xLeft = 33488896;
                      v59 = GdiAlphaBlend(
                              v58,
                              yTop,
                              yTop_4,
                              v54,
                              v53,
                              hdc[1],
                              0,
                              0,
                              SDWORD1(pv[0]),
                              SDWORD2(pv[0]),
                              (BLENDFUNCTION)33488896);
                    }
                    else
                    {
                      v60 = *(HDC *)(a2 + 32);
                      if ( v79 )
                      {
                        SetStretchBltMode(v60, 3);
                        v59 = StretchBlt(
                                *(HDC *)(a2 + 32),
                                yTop,
                                yTop_4,
                                v54,
                                v53,
                                hdc[1],
                                0,
                                0,
                                SDWORD1(pv[0]),
                                SDWORD2(pv[0]),
                                0xCC0020u);
                      }
                      else
                      {
                        v59 = BitBlt(v60, yTop, yTop_4, v54, v53, hdc[1], 0, 0, 0xCC0020u);
                      }
                    }
                    if ( v59 )
                      ScaleFactorForWindow = 0;
                    else
                      ScaleFactorForWindow = ResultFromKnownLastError();
                    SelectObject((HDC)yTop_8.m128i_i64[0], h);
                  }
                  Microsoft::WRL::Wrappers::CompatibleDC::~CompatibleDC((Microsoft::WRL::Wrappers::CompatibleDC *)hdc);
                  goto LABEL_87;
                }
              }
              else
              {
                v31 = *(_DWORD *)(a3 + 60) == 1;
                yTop_8 = _mm_load_si128((const __m128i *)&_xmm);
                if ( v31 )
                {
                  v40 = v84;
                  v41 = 100;
                }
                else
                {
                  v41 = 96;
                  v40 = *(unsigned int *)(a3 + 64);
                }
                v42 = (__m128i *)Geometry::CRect::MulDiv(hdc, &yTop_8, v40, v41);
                v43 = *(unsigned int *)(a3 + 64);
                v44 = *v42;
                v45 = *(unsigned int *)(a3 + 60);
                yTop_4 = *(_DWORD *)(a2 + 44);
                yTop_8 = v44;
                v46 = v30 / 2 - (int)DPIToPPIHelpers::ScaleByType(v45, 16, v29, v43) / 2;
                v31 = *(_DWORD *)(a3 + 60) == 0;
                yTop = yTop_4 + v46 + yTop_8.m128i_i32[1];
                if ( v31 )
                {
                  v47 = (int)DPIToPPIHelpers::ScaleByType(0, 16, v29, *(unsigned int *)(a3 + 64)) / 2;
                  xLeft = v47 + yTop_8.m128i_i32[0];
                  v48 = v47 + yTop_8.m128i_i32[2];
                }
                else
                {
                  v48 = yTop_8.m128i_i32[2];
                  xLeft = yTop_8.m128i_i32[0];
                }
                memset_0(&psii.cbSize + 1, 0, 0x21Cu);
                v49 = v48 - xLeft;
                v50 = *(_DWORD *)(a3 + 28);
                psii.cbSize = 544;
                if ( SHGetStockIconInfo(v50, (v49 < 24) + 256, &psii) >= 0 )
                {
                  if ( DrawIconEx(
                         *(HDC *)(a2 + 32),
                         xLeft,
                         yTop,
                         psii.hIcon,
                         v49,
                         yTop_8.m128i_i32[3] + yTop_4 + v46 - yTop,
                         0,
                         0,
                         3u) )
                  {
                    ScaleFactorForWindow = 0;
                    goto LABEL_87;
                  }
                  Error = ResultFromKnownLastError();
LABEL_61:
                  ScaleFactorForWindow = Error;
LABEL_87:
                  if ( ScaleFactorForWindow >= 0 )
                    goto LABEL_88;
LABEL_98:
                  ExcludeClipRect(
                    *(HDC *)(a2 + 32),
                    *(_DWORD *)(a2 + 40),
                    *(_DWORD *)(a2 + 44),
                    *(_DWORD *)(a2 + 48),
                    *(_DWORD *)(a2 + 52));
                  CloseThemeData(hTheme);
                  return (unsigned int)ScaleFactorForWindow;
                }
              }
LABEL_88:
              if ( (*(_BYTE *)(a3 + 24) & 0x10) != 0 )
              {
                v61 = *(unsigned int *)(a3 + 64);
                v62 = *(unsigned int *)(a3 + 60);
                *(__m128i *)hdc = _mm_load_si128((const __m128i *)&_xmm);
                v63 = *(_DWORD *)(a2 + 48) - DPIToPPIHelpers::ScaleByType(v62, 28, v29, v61);
                if ( *(_DWORD *)(a3 + 60) == 1 )
                {
                  v64 = v84;
                  v65 = 100;
                }
                else
                {
                  v64 = *(unsigned int *)(a3 + 64);
                  v65 = 96;
                }
                v66 = *(__m128i *)Geometry::CRect::MulDiv(&yTop_8, hdc, v64, v65);
                v67 = *(_DWORD *)(a2 + 44);
                v68 = DPIToPPIHelpers::ScaleByType(*(unsigned int *)(a3 + 60), 16, v29, *(unsigned int *)(a3 + 64));
                v69 = v66.m128i_i64[0];
                v66.m128i_i64[0] = _mm_srli_si128(v66, 8).m128i_u64[0];
                v70 = (int)hWnd / 2 - v68 / 2;
                LODWORD(hdc[0]) = v63 + v69;
                HIDWORD(hdc[0]) = v67 + v70 + HIDWORD(v69);
                LODWORD(hdc[1]) = v63 + v66.m128i_i32[0];
                diFlagsa = *(_DWORD *)(a3 + 60);
                HIDWORD(hdc[1]) = v67 + v70 + v66.m128i_i32[1];
                ScaleFactorForWindow = s_DrawGlyph(v29, 16, *(_DWORD *)(a3 + 24), v7, (__int64)hdc, diFlagsa);
              }
              goto LABEL_98;
            }
          }
          else if ( *(_DWORD *)(a3 + 24) != 2048 )
          {
            goto LABEL_98;
          }
          *(_OWORD *)hdc = *(_OWORD *)(a2 + 40);
          LOBYTE(v21) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_HVCZMTest>::GetImpl'::`2'::impl,
            v21);
          if ( *v8 || (v71 = 7, (*(_BYTE *)(a3 + 56) & 4) != 0) )
            v71 = 9;
          v72 = DPIToPPIHelpers::ScaleByType(*(unsigned int *)(a3 + 60), v71, a1, *(unsigned int *)(a3 + 64));
          v73 = floorf((double)(v72 - 5) * 0.5);
          --HIDWORD(hdc[1]);
          v74 = *(HDC *)(a2 + 32);
          HIDWORD(hdc[0]) += (int)v73;
          DrawThemeBackground(hTheme, v74, 15, v7, (LPCRECT)hdc, 0);
          goto LABEL_98;
        }
      }
    }
  }
  return (unsigned int)ScaleFactorForWindow;
}

```

## disassembly

```asm
0x18006d26c  mov     rax, rsp
0x18006d26f  mov     [rax+20h], rbx
0x18006d273  push    rbp
0x18006d274  push    rsi
0x18006d275  push    rdi
0x18006d276  push    r12
0x18006d278  push    r13
0x18006d27a  push    r14
0x18006d27c  push    r15
0x18006d27e  lea     rbp, [rax-2C8h]
0x18006d285  sub     rsp, 390h
0x18006d28c  movaps  xmmword ptr [rax-48h], xmm6
0x18006d290  mov     rax, cs:__security_cookie
0x18006d297  xor     rax, rsp
0x18006d29a  mov     [rbp+2C0h+var_50], rax
0x18006d2a1  xor     r14d, r14d
0x18006d2a4  mov     [rbp+2C0h+hWnd], rcx
0x18006d2a8  mov     r15, r8
0x18006d2ab  mov     r13, rdx
0x18006d2ae  mov     rsi, rcx
0x18006d2b1  mov     ebx, 8000FFFFh
0x18006d2b6  test    r8, r8
0x18006d2b9  jz      loc_18006DCD1
0x18006d2bf  lea     r12d, [r14+2]
0x18006d2c3  mov     edx, r12d; dwFlags
0x18006d2c6  call    cs:__imp_MonitorFromWindow
0x18006d2cc  test    rax, rax
0x18006d2cf  jz      loc_18006DCD1
0x18006d2d5  lea     rdx, [rbp+2C0h+var_340]
0x18006d2d9  mov     [rbp+2C0h+var_340], r14d
0x18006d2dd  mov     rcx, rsi
0x18006d2e0  call    cs:__imp_GetScaleFactorForWindow
0x18006d2e6  mov     ebx, eax
0x18006d2e8  test    eax, eax
0x18006d2ea  js      loc_18006DCD1
0x18006d2f0  lea     rdi, [r15+45h]
0x18006d2f4  cmp     [r15+44h], r14b
0x18006d2f8  jz      short loc_18006D303
0x18006d2fa  lea     rdx, aDarkmodeImmers; "DarkMode_ImmersiveStart::Menu"
0x18006d301  jmp     short loc_18006D316
0x18006d303  lea     rdx, aLightmodeImmer; "LightMode_ImmersiveStart::Menu"
0x18006d30a  cmp     [rdi], r14b
0x18006d30d  jnz     short loc_18006D316
0x18006d30f  lea     rdx, aImmersivestart; "ImmersiveStart::Menu"
0x18006d316  xor     ecx, ecx; hwnd
0x18006d318  call    cs:__imp_OpenThemeData
0x18006d31e  mov     [rbp+2C0h+hTheme], rax
0x18006d322  mov     r14, rax
0x18006d325  test    rax, rax
0x18006d328  jz      loc_18006DCD1
0x18006d32e  mov     ebx, [r13+10h]
0x18006d332  mov     [rsp+3C0h+yTop], ebx
0x18006d336  mov     dl, 1
0x18006d338  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HVCZMTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HVCZMTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest> `wil::Feature<__WilFeatureTraits_Feature_HVCZMTest>::GetImpl(void)'::`2'::impl
0x18006d33f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HVCZMTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVCZMTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18006d344  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x18006d349  test    eax, eax
0x18006d34b  jnz     short loc_18006D359
0x18006d34d  mov     rcx, [r13+18h]
0x18006d351  mov     rdx, r14
0x18006d354  call    s_SetDwmAttributes
0x18006d359  test    byte ptr [r15+38h], 1
0x18006d35e  mov     r14d, 6
0x18006d364  jz      short loc_18006D38C
0x18006d366  cmp     byte ptr [rdi], 0
0x18006d369  jnz     short loc_18006D375
0x18006d36b  test    byte ptr [r15+38h], 4
0x18006d370  mov     edx, r12d
0x18006d373  jz      short loc_18006D378
0x18006d375  mov     edx, r14d
0x18006d378  mov     r9d, [r15+40h]
0x18006d37c  mov     r8, rsi
0x18006d37f  mov     ecx, [r15+3Ch]
0x18006d383  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d388  add     [r13+2Ch], eax
0x18006d38c  test    [r15+38h], r12b
0x18006d390  jz      short loc_18006D3B8
0x18006d392  cmp     byte ptr [rdi], 0
0x18006d395  jnz     short loc_18006D3A1
0x18006d397  test    byte ptr [r15+38h], 4
0x18006d39c  jnz     short loc_18006D3A1
0x18006d39e  mov     r14d, r12d
0x18006d3a1  mov     r9d, [r15+40h]
0x18006d3a5  mov     r8, rsi
0x18006d3a8  mov     ecx, [r15+3Ch]
0x18006d3ac  mov     edx, r14d
0x18006d3af  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d3b4  sub     [r13+34h], eax
0x18006d3b8  mov     eax, ebx
0x18006d3ba  test    bl, 4
0x18006d3bd  jz      short loc_18006D3E1
0x18006d3bf  and     eax, 1
0x18006d3c2  jz      short loc_18006D3D9
0x18006d3c4  mov     rax, [r15]
0x18006d3c7  xor     ecx, ecx
0x18006d3c9  test    rax, rax
0x18006d3cc  jz      short loc_18006D3D9
0x18006d3ce  cmp     [rax], cx
0x18006d3d1  jz      short loc_18006D3D9
0x18006d3d3  lea     r12d, [rcx+4]
0x18006d3d7  jmp     short loc_18006D3FB
0x18006d3d9  mov     r12d, 3
0x18006d3df  jmp     short loc_18006D3FB
0x18006d3e1  and     eax, 1
0x18006d3e4  jz      short loc_18006D3F5
0x18006d3e6  mov     rax, [r15]
0x18006d3e9  xor     ecx, ecx
0x18006d3eb  test    rax, rax
0x18006d3ee  jz      short loc_18006D3F5
0x18006d3f0  cmp     [rax], cx
0x18006d3f3  jnz     short loc_18006D3FB
0x18006d3f5  mov     r12d, 1
0x18006d3fb  mov     rbx, [rbp+2C0h+hTheme]
0x18006d3ff  lea     rax, [rbp+2C0h+var_D0]
0x18006d406  mov     rdx, [r13+20h]; hdc
0x18006d40a  xor     r14d, r14d
0x18006d40d  mov     [rsp+3C0h+pMargins], rax; pMargins
0x18006d412  xorps   xmm0, xmm0
0x18006d415  mov     [rsp+3C0h+prc], r14; prc
0x18006d41a  mov     r9d, r12d; iStateId
0x18006d41d  mov     rcx, rbx; hTheme
0x18006d420  mov     [rsp+3C0h+iPropId], 0E12h; iPropId
0x18006d428  lea     r8d, [r14+1Bh]; iPartId
0x18006d42c  movups  xmmword ptr [rbp+2C0h+var_D0.cxLeftWidth], xmm0
0x18006d433  call    cs:__imp_GetThemeMargins
0x18006d439  test    eax, eax
0x18006d43b  js      short loc_18006D471
0x18006d43d  mov     r9d, [r15+40h]
0x18006d441  mov     r8, rsi
0x18006d444  mov     edx, [rbp+2C0h+var_D0.cxLeftWidth]
0x18006d44a  mov     ecx, [r15+3Ch]
0x18006d44e  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d453  add     [r13+28h], eax
0x18006d457  mov     r8, rsi
0x18006d45a  mov     r9d, [r15+40h]
0x18006d45e  mov     ecx, [r15+3Ch]
0x18006d462  mov     edx, [rbp+2C0h+var_D0.cxRightWidth]
0x18006d468  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d46d  sub     [r13+30h], eax
0x18006d471  mov     rcx, [r13+20h]; hDC
0x18006d475  call    cs:__imp_WindowFromDC
0x18006d47b  mov     rcx, rax; hWnd
0x18006d47e  lea     rdx, aKbFocusMenu; "KB_FOCUS_MENU"
0x18006d485  call    cs:__imp_GetPropW
0x18006d48b  mov     r14, rax
0x18006d48e  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x18006d493  test    eax, eax
0x18006d495  jnz     short loc_18006D4C7
0x18006d497  xor     r8d, r8d; iStateId
0x18006d49a  lea     edx, [rax+1Ah]; iPartId
0x18006d49d  mov     rcx, rbx; hTheme
0x18006d4a0  call    cs:__imp_IsThemePartDefined
0x18006d4a6  test    eax, eax
0x18006d4a8  jz      short loc_18006D4C7
0x18006d4aa  test    r14d, r14d
0x18006d4ad  jz      short loc_18006D4C7
0x18006d4af  lea     eax, [r12-2]
0x18006d4b4  test    eax, 0FFFFFFFDh
0x18006d4b9  jnz     short loc_18006D4C7
0x18006d4bb  mov     r9d, 1
0x18006d4c1  lea     r8d, [r9+19h]
0x18006d4c5  jmp     short loc_18006D4D0
0x18006d4c7  mov     r9d, r12d; iStateId
0x18006d4ca  mov     r8d, 1Bh; iPartId
0x18006d4d0  mov     rdx, [r13+20h]; hdc
0x18006d4d4  lea     r14, [r13+28h]
0x18006d4d8  mov     [rsp+3C0h+prc], 0; pClipRect
0x18006d4e1  mov     rcx, rbx; hTheme
0x18006d4e4  mov     qword ptr [rsp+3C0h+iPropId], r14; pRect
0x18006d4e9  call    cs:__imp_DrawThemeBackground
0x18006d4ef  xor     ecx, ecx
0x18006d4f1  mov     ebx, eax
0x18006d4f3  test    eax, eax
0x18006d4f5  js      loc_18006DCA9
0x18006d4fb  mov     rax, [r15]
0x18006d4fe  mov     edx, 800h
0x18006d503  test    rax, rax
0x18006d506  jz      loc_18006DC09
0x18006d50c  cmp     [rax], cx
0x18006d50f  jz      loc_18006DC09
0x18006d515  cmp     [r15+18h], edx
0x18006d519  jz      loc_18006DC13
0x18006d51f  mov     r9d, [r15+40h]
0x18006d523  mov     r8, [rbp+2C0h+hWnd]
0x18006d527  mov     edx, cs:dword_18007DA74
0x18006d52d  mov     ecx, [r15+3Ch]
0x18006d531  mov     ebx, [r13+28h]
0x18006d535  mov     edi, [r13+2Ch]
0x18006d539  mov     r14d, [r13+30h]
0x18006d53d  mov     esi, [r13+34h]
0x18006d541  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d546  mov     r9d, [r15+40h]
0x18006d54a  mov     edx, 11h
0x18006d54f  mov     r8, [rbp+2C0h+hWnd]
0x18006d553  mov     dword ptr [rbp+2C0h+hdc+4], edi
0x18006d559  lea     ecx, [rax+rbx]
0x18006d55c  mov     dword ptr [rbp+2C0h+hdc], ecx
0x18006d562  mov     ecx, [r15+3Ch]
0x18006d566  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d56b  sub     r14d, eax
0x18006d56e  mov     dword ptr [rbp+2C0h+hdc+0Ch], esi
0x18006d574  mov     rsi, [rbp+2C0h+hWnd]
0x18006d578  lea     rax, [rbp+2C0h+hdc]
0x18006d57f  mov     dword ptr [rbp+2C0h+hdc+8], r14d
0x18006d586  mov     r9, r13
0x18006d589  mov     r14, [rbp+2C0h+hTheme]
0x18006d58d  mov     r8, rsi
0x18006d590  mov     [rsp+3C0h+prc], rax
0x18006d595  mov     rcx, r14
0x18006d598  mov     edx, r12d
0x18006d59b  mov     qword ptr [rsp+3C0h+iPropId], r15
0x18006d5a0  call    s_DrawThemeTextPPIAware
0x18006d5a5  xor     ecx, ecx
0x18006d5a7  mov     ebx, eax
0x18006d5a9  test    eax, eax
0x18006d5ab  js      loc_18006DCA9
0x18006d5b1  mov     edi, [r13+34h]
0x18006d5b5  lea     edx, [rcx+64h]
0x18006d5b8  sub     edi, [r13+2Ch]
0x18006d5bc  lea     r8d, [rcx+60h]
0x18006d5c0  mov     eax, [rsp+3C0h+yTop]
0x18006d5c4  mov     dword ptr [rbp+2C0h+hWnd], edi
0x18006d5c7  and     eax, 8
0x18006d5ca  jz      loc_18006D6B3
0x18006d5d0  cmp     [r15+28h], rcx
0x18006d5d4  jnz     loc_18006D6B3
0x18006d5da  cmp     dword ptr [r15+3Ch], 1
0x18006d5df  lea     rcx, [rbp+2C0h+hdc]
0x18006d5e6  movdqa  xmm0, cs:__xmm@00000010000000180000000000000008
0x18006d5ee  movdqa  xmmword ptr [rsp+3C0h+yTop+8], xmm0
0x18006d5f4  jnz     short loc_18006D5FF
0x18006d5f6  mov     r8d, [rbp+2C0h+var_340]
0x18006d5fa  mov     r9d, edx
0x18006d5fd  jmp     short loc_18006D606
0x18006d5ff  mov     r9d, r8d
0x18006d602  mov     r8d, [r15+40h]
0x18006d606  lea     rdx, [rsp+3C0h+yTop+8]
0x18006d60b  call    ?MulDiv@CRect@Geometry@@SA?AU12@AEBUtagRECT@@HH@Z; Geometry::CRect::MulDiv(tagRECT const &,int,int)
0x18006d610  mov     r9d, [r15+40h]
0x18006d614  mov     r8, rsi
0x18006d617  mov     edx, cs:dword_18007DA78
0x18006d61d  mov     ecx, [r15+3Ch]
0x18006d621  movups  xmm0, xmmword ptr [rax]
0x18006d624  mov     ebx, [r13+2Ch]
0x18006d628  movdqu  xmmword ptr [rsp+3C0h+yTop+8], xmm0
0x18006d62e  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006d633  mov     r9, [r13+20h]
0x18006d637  cdq
0x18006d638  sub     eax, edx
0x18006d63a  mov     r8, r14
0x18006d63d  sar     eax, 1
0x18006d63f  mov     ecx, eax
0x18006d641  mov     eax, edi
0x18006d643  cdq
0x18006d644  sub     eax, edx
0x18006d646  mov     edx, [r15+40h]
0x18006d64a  sar     eax, 1
0x18006d64c  sub     eax, ecx
0x18006d64e  mov     rcx, [rsp+3C0h+var_348]
0x18006d653  shr     rcx, 20h
0x18006d657  add     ecx, eax
0x18006d659  add     ecx, ebx
0x18006d65b  mov     dword ptr [rsp+3C0h+var_348+4], ecx
0x18006d65f  mov     rcx, qword ptr [rsp+3C0h+yTop+8]
0x18006d664  shr     rcx, 20h
0x18006d668  add     ecx, eax
0x18006d66a  mov     eax, [r15+3Ch]
0x18006d66e  mov     [rsp+3C0h+diFlags], eax; int
0x18006d672  add     ecx, ebx
0x18006d674  lea     rax, [rbp+2C0h+hdc]
0x18006d67b  mov     [rsp+3C0h+yTop+0Ch], ecx
0x18006d67f  movaps  xmm0, xmmword ptr [rsp+3C0h+yTop+8]
0x18006d684  mov     rcx, rsi; hWnd
0x18006d687  mov     [rsp+3C0h+hbrFlickerFreeDraw], rax; __int64
0x18006d68c  mov     eax, [r15+18h]
0x18006d690  mov     dword ptr [rsp+3C0h+pMargins], r12d; iStateId
0x18006d695  mov     dword ptr [rsp+3C0h+prc], eax; int
0x18006d699  mov     [rsp+3C0h+iPropId], 0Bh; int
0x18006d6a1  movdqa  xmmword ptr [rbp+2C0h+hdc], xmm0
0x18006d6a9  call    s_DrawGlyph
0x18006d6ae  jmp     loc_18006D814
0x18006d6b3  cmp     dword ptr [r15+1Ch], 0FFFFFFFFh
0x18006d6b8  jz      loc_18006D81B
0x18006d6be  cmp     dword ptr [r15+3Ch], 1
0x18006d6c3  lea     rcx, [rbp+2C0h+hdc]
0x18006d6ca  movdqa  xmm0, cs:__xmm@00000010000000180000000000000008
0x18006d6d2  movdqu  xmmword ptr [rsp+3C0h+yTop+8], xmm0
0x18006d6d8  jnz     short loc_18006D6E3
0x18006d6da  mov     r8d, [rbp+2C0h+var_340]
0x18006d6de  mov     r9d, edx
0x18006d6e1  jmp     short loc_18006D6EA
0x18006d6e3  mov     r9d, r8d
0x18006d6e6  mov     r8d, [r15+40h]
0x18006d6ea  lea     rdx, [rsp+3C0h+yTop+8]
0x18006d6ef  call    ?MulDiv@CRect@Geometry@@SA?AU12@AEBUtagRECT@@HH@Z; Geometry::CRect::MulDiv(tagRECT const &,int,int)
0x18006d6f4  mov     r14d, [r13+2Ch]
0x18006d6f8  mov     r8, rsi
0x18006d6fb  mov     r9d, [r15+40h]
0x18006d6ff  mov     edx, cs:dword_18007DA78
0x18006d705  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
