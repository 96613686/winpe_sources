# CInkOverlay::CursorUp(ulong,ulong,ulong,ulong,uchar *)

- ea: `0x1800d8c30`
- end: `0x1800d9af7`
- name: `?CursorUp@CInkOverlay@@UEAAJKKKKPEAE@Z`
- size: `3783`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `29`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x1800276c4`
- `0x18002a3ac`
- `0x1800349c4`
- `0x1800365f8`
- `0x180036824`
- `0x18003821c`
- `0x1800a991c`
- `0x1800b1368`
- `0x1800b16d4`
- `0x1800b3f28`
- `0x1800d8c30`
- `0x1800db464`
- `0x1800db5bc`
- `0x1800db714`
- `0x1800dbaf8`
- `0x1800dbb24`
- `0x1800dd478`
- `0x1800ddfd8`
- `0x1800e03cc`
- `0x1800e087c`
- `0x1800e0ab0`
- `0x1800e1218`
- `0x1800e1318`
- `0x1800e1954`
- `0x1800e2850`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d8f3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d8f3b`
- `USER32!InflateRect` at `0x1800d9168`
- `USER32!InflateRect` at `0x1800d992a`
- `USER32!InflateRect` at `0x1800d9168`
- `USER32!InflateRect` at `0x1800d992a`
- `USER32!SetTimer` at `0x1800d8ed6`
- `USER32!SetTimer` at `0x1800d8ed6`
- `USER32!GetKeyState` at `0x1800d9828`
- `USER32!GetKeyState` at `0x1800d9837`
- `USER32!GetKeyState` at `0x1800d9828`
- `USER32!GetKeyState` at `0x1800d9837`
- `USER32!ReleaseDC` at `0x1800d9a4c`
- `USER32!ReleaseDC` at `0x1800d9a4c`
- `USER32!EqualRect` at `0x1800d9354`
- `USER32!EqualRect` at `0x1800d9354`
- `GDI32!DeleteObject` at `0x1800d99ba`
- `GDI32!DeleteObject` at `0x1800d99c7`
- `GDI32!DeleteObject` at `0x1800d99ba`
- `GDI32!DeleteObject` at `0x1800d99c7`
- `OLEAUT32!__imp_VariantClear` at `0x1800d9ab4`
- `OLEAUT32!__imp_VariantClear` at `0x1800d9ab4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d8e22`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d8e22`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CInkOverlay::CursorUp(CInkOverlay *this, __int64 a2, unsigned int a3)
{
  CInkOverlay *v4; // r14
  int *v5; // r13
  int CurrentStroke; // esi
  int v7; // r15d
  struct IInkStrokeDisp *v8; // rbx
  int v9; // eax
  __int16 v10; // ax
  int v11; // r15d
  __int64 v12; // r8
  bool v13; // zf
  int v14; // r15d
  HDC v15; // rbx
  int v16; // r8d
  int v17; // r15d
  CSelectionRect *v18; // r15
  HDC v19; // rbx
  BOOL v20; // ebx
  int v21; // r8d
  HDC v22; // r13
  int v23; // r8d
  CInkOverlay *v24; // rbx
  int v25; // r8d
  int v26; // r13d
  int v27; // r15d
  int v28; // esi
  int v29; // ebx
  int v30; // eax
  int v31; // r15d
  int v32; // eax
  int v33; // eax
  int v34; // esi
  int v35; // eax
  char *v36; // rcx
  int v37; // r8d
  __int64 v38; // rcx
  HRGN v39; // r8
  HDC *v40; // rbx
  CInkOverlay *v41; // r8
  __int64 v42; // rcx
  struct IInkRenderer *lpdwindex; // [rsp+20h] [rbp-168h]
  struct IInkRenderer *lpdwindexa; // [rsp+20h] [rbp-168h]
  struct IInkRenderer *v46; // [rsp+28h] [rbp-160h]
  int v47; // [rsp+30h] [rbp-158h] BYREF
  __int16 v48; // [rsp+34h] [rbp-154h] BYREF
  LPVOID v49; // [rsp+38h] [rbp-150h] BYREF
  HDC v50; // [rsp+40h] [rbp-148h] BYREF
  __int16 v51; // [rsp+48h] [rbp-140h] BYREF
  int v52[2]; // [rsp+50h] [rbp-138h] BYREF
  struct IInkStrokes *v53; // [rsp+58h] [rbp-130h] BYREF
  unsigned int v54[2]; // [rsp+60h] [rbp-128h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-120h] BYREF
  int v56; // [rsp+70h] [rbp-118h]
  int v57; // [rsp+74h] [rbp-114h]
  struct _RTL_CRITICAL_SECTION *v58; // [rsp+78h] [rbp-110h]
  CInkOverlay *v59; // [rsp+80h] [rbp-108h]
  struct IInkStrokeDisp *v60; // [rsp+88h] [rbp-100h] BYREF
  struct IUnknown *v61; // [rsp+90h] [rbp-F8h] BYREF
  DWORD dwindex; // [rsp+98h] [rbp-F0h] BYREF
  int v63; // [rsp+9Ch] [rbp-ECh] BYREF
  _QWORD v64[2]; // [rsp+A0h] [rbp-E8h] BYREF
  LPVOID ppv[2]; // [rsp+B0h] [rbp-D8h] BYREF
  struct tagRECT v66; // [rsp+C0h] [rbp-C8h] BYREF
  IRecordInfo *pRecInfo; // [rsp+D0h] [rbp-B8h]
  VARIANTARG pvarg; // [rsp+E0h] [rbp-A8h] BYREF
  HDC *v69; // [rsp+F8h] [rbp-90h]
  RECT rcSrc; // [rsp+100h] [rbp-88h] BYREF
  struct tagRECT rc; // [rsp+110h] [rbp-78h] BYREF
  RECT rc2; // [rsp+120h] [rbp-68h] BYREF
  __int128 v73; // [rsp+130h] [rbp-58h] BYREF
  struct tagRECT v74; // [rsp+140h] [rbp-48h] BYREF

  v54[0] = a3;
  v4 = this;
  *(_QWORD *)&rc2.left = this;
  v59 = this;
  v55 = a3;
  v74 = 0;
  v64[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v63 = 0;
  v61 = 0;
  v58 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 272);
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rc, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
  try
  {
    v5 = (int *)((char *)v4 + 448);
    *(_QWORD *)&v73 = (char *)v4 + 448;
    v56 = *((_DWORD *)v4 + 112);
    v69 = (HDC *)((char *)v4 + 504);
    v50 = (HDC)*((_QWORD *)v4 + 63);
    *(_QWORD *)&rcSrc.left = v50;
    CurrentStroke = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **, _QWORD))(*(_QWORD *)(*((_QWORD *)v4 + 77) + 8LL)
                                                                                           + 40LL))(
                      *((_QWORD *)v4 + 77) + 8LL,
                      a3,
                      &v61,
                      0);
    *((_DWORD *)v4 + 156) = a3;
    v52[0] = *((_DWORD *)v4 + 212);
    LODWORD(v49) = v52[0];
    v47 = *((_DWORD *)v4 + 112);
    v57 = v47;
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rc);
    if ( CurrentStroke >= 0 )
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 68) + 112LL))(
                        *((_QWORD *)v4 + 68),
                        a3,
                        0,
                        0);
    v7 = CurrentStroke;
    v48 = 0;
    v51 = -1;
    v8 = 0;
    v60 = 0;
    if ( CurrentStroke >= 0 )
    {
      CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rc, v58);
      v9 = *((_DWORD *)v4 + 101);
      if ( v9 )
        *((_DWORD *)v4 + 101) = v9 - 1;
      CurrentStroke = CInkOverlay::_GetCurrentStroke(v4, a3, &v60);
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rc);
      v7 = CurrentStroke;
      v8 = v60;
    }
    dwindex = 0;
    ppv[0] = (char *)v4 + 440;
    if ( CoWaitForMultipleHandles(0, 0, 1u, (LPHANDLE)v4 + 55, &dwindex) >= 0 )
    {
      if ( v7 >= 0 && v56 )
      {
        try
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)v4 + 54) + 104LL))(
                            *((_QWORD *)v4 + 54),
                            v8);
          if ( CurrentStroke >= 0 )
          {
            ATL::AtlComPtrAssign((struct IUnknown **)v4 + 53, v61);
            if ( v56 == 2 )
            {
              CurrentStroke = CInkOverlay::_RecognizeGestureStrokes(v4, &v51);
              if ( v51 )
                v10 = 0;
              else
                v10 = -1;
              v48 = v10;
              (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 54) + 128LL))(
                *((_QWORD *)v4 + 54),
                *((_QWORD *)v4 + 54));
            }
            else if ( !SetTimer(*(HWND *)(*((_QWORD *)v4 + 66) + 8LL), 1u, *(UINT *)&uElapse, 0) )
            {
              CurrentStroke = -2147467259;
            }
          }
        }
        catch ( ... )
        {
          CurrentStroke = ReportWispException();
          v8 = v60;
          v54[0] = v55;
          v4 = *(CInkOverlay **)&rc2.left;
          v5 = (int *)v73;
          v47 = v57;
          v50 = *(HDC *)&rcSrc.left;
          v52[0] = (int)v49;
        }
      }
      ReleaseMutex(*(HANDLE *)ppv[0]);
    }
    CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rc, v58);
    v11 = *v5;
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rc);
    if ( CurrentStroke >= 0 && v11 != 1 && (*((_DWORD *)v4 + 113) & 2) != 0 && v51 == -1 )
    {
      CProxy_IInkOverlayEvents<CInkOverlay>::Fire_Stroke((char *)v4 + 112, v61, v8, &v48);
      v13 = v48 == 0;
      v48 = 0;
      if ( !v13 )
        v48 = -1;
    }
    v14 = 0;
    if ( v47 != 1 )
      v14 = v52[0];
    if ( v14 == 1 )
    {
      v48 = -1;
    }
    else if ( v14 == 2 )
    {
      v48 = -1;
      if ( *((_DWORD *)v59 + 235) == 1 )
        CurrentStroke = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, int *))v8->lpVtbl->get_PacketCount)(v8, &v63);
      if ( CurrentStroke < 0 )
        goto LABEL_49;
      CurrentStroke = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, __int64, VARIANTARG *))v8->lpVtbl->GetPoints)(
                        v8,
                        0,
                        0xFFFFFFFFLL,
                        &pvarg);
      if ( CurrentStroke < 0 )
        goto LABEL_49;
      CurrentStroke = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, _QWORD *))v8->lpVtbl->GetBoundingBox)(
                        v8,
                        0,
                        v64);
      if ( CurrentStroke < 0 )
        goto LABEL_49;
      lpdwindex = (struct IInkRenderer *)&v74.right;
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LONG *, struct tagRECT *, LONG *))(*(_QWORD *)v64[0] + 136LL))(
                        v64[0],
                        &v74.top,
                        &v74,
                        &v74.bottom);
    }
    if ( CurrentStroke >= 0 && v48 == -1 )
    {
      v47 = 0;
      if ( ((int (__fastcall *)(struct IInkStrokeDisp *, int *))v8->lpVtbl->get_ID)(v8, &v47) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v4 + 68) + 72LL))(
          *((_QWORD *)v4 + 68),
          (unsigned int)v47,
          &v47);
      v49 = 0;
      if ( ((int (__fastcall *)(struct IInkStrokeDisp *, __int64, LPVOID *))v8->lpVtbl->GetBoundingBox)(v8, 4, &v49) < 0 )
      {
        v15 = v50;
      }
      else
      {
        rc = 0;
        (*(void (__fastcall **)(LPVOID, struct tagRECT *))(*(_QWORD *)v49 + 120LL))(v49, &rc);
        v15 = v50;
        CInkCollector::_InkSpaceToPixel(v4, &rc, v16, v50, 0);
        InflateRect(&rc, 2, 2);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v4 + 68) + 64LL))(
          *((_QWORD *)v4 + 68),
          (unsigned int)v47,
          1);
        CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)ppv, v58);
        if ( *((_BYTE *)v4 + 264) && !v14 )
          CInkOverlay::_InvalidateWindow(v4, &rc, 0, 1, 1);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)ppv);
      }
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v49);
      goto LABEL_50;
    }
LABEL_49:
    v15 = v50;
LABEL_50:
    v53 = 0;
    if ( CurrentStroke < 0 )
      goto LABEL_122;
    v17 = v14 - 1;
    if ( !v17 )
    {
      v39 = (HRGN)*((_QWORD *)v4 + 140);
      if ( v39 )
      {
        CInkOverlay::_InvalidateWindow(v4, 0, v39, 1, 1);
        DeleteObject(*((HGDIOBJ *)v4 + 140));
        DeleteObject(*((HGDIOBJ *)v4 + 141));
        *((_QWORD *)v4 + 140) = 0;
        *((_QWORD *)v4 + 141) = 0;
      }
      goto LABEL_122;
    }
    if ( v17 != 1 )
    {
LABEL_122:
      CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&v66, v58);
      std::_Tree<std::_Tmap_traits<unsigned long,ATL::CComPtr<IInkStrokeDisp>,std::less<unsigned long>,inkobj_allocator<std::pair<unsigned long,ATL::CComPtr<IInkStrokeDisp>>>,0>>::erase(
        (char *)v4 + 552,
        &v55);
      std::_Tree<std::_Tmap_traits<unsigned long,enum InkOverlayEditingMode,std::less<unsigned long>,inkobj_allocator<std::pair<unsigned long,enum InkOverlayEditingMode>>,0>>::erase(
        (char *)v4 + 568,
        &v55);
      v40 = v69;
      if ( *v69 )
      {
        v41 = v59;
        v13 = (*((_DWORD *)v59 + 128))-- == 1;
        if ( v13 )
        {
          v42 = 768;
          if ( *((_DWORD *)v4 + 213) != 1 )
            v42 = 56;
          ReleaseDC(*(HWND *)((char *)v41 + v42), *v40);
          *v40 = 0;
        }
      }
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&v66);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v53);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v60);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v61);
      goto LABEL_133;
    }
    v18 = (CInkOverlay *)((char *)v4 + 864);
    if ( *((_DWORD *)v4 + 235) != 1 )
    {
      if ( *((_DWORD *)v4 + 235) != 2 && *((_DWORD *)v4 + 235) != 3 )
      {
        if ( *((_DWORD *)v4 + 235) == 4 && !*((_DWORD *)v4 + 270) )
        {
          v49 = (LPVOID)*((_QWORD *)v4 + 132);
          v52[0] = 0;
          v19 = v50;
          CurrentStroke = CInkOverlay::_GetHitTestTolerance(v4, v52, v50);
          if ( CurrentStroke >= 0 )
          {
            CurrentStroke = CInkOverlay::_PixelToInkSpace(v4, (int *)&v49, (int *)&v49 + 1, 7, v19, v46);
            if ( CurrentStroke >= 0 )
            {
              CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 67) + 152LL))(
                                *((_QWORD *)v4 + 67),
                                (unsigned int)v49,
                                HIDWORD(v49));
              if ( CurrentStroke >= 0 )
              {
                CInkOverlay::_FilterCurrentStroke(v4, v54[0], v53);
                CurrentStroke = CInkOverlay::_AddSubSelection(v4, v53);
              }
            }
          }
        }
        goto LABEL_119;
      }
      rc2 = 0;
      rc = 0;
      rcSrc = 0;
      v73 = 0;
      CSelectionRect::GetNormalizedDynamicPosition((CInkOverlay *)((char *)v4 + 864), &rc2);
      CSelectionRect::GetNormalizedPosition((RECT *)v4 + 54, &rc);
      v20 = EqualRect(&rc, &rc2);
      *(_QWORD *)v52 = 0;
      *(_QWORD *)v54 = 0;
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v4 + 95) + 144LL))(
                        *((_QWORD *)v4 + 95),
                        0,
                        v52);
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      if ( v20 )
      {
LABEL_101:
        if ( *((_DWORD *)v4 + 269) )
        {
          v36 = (char *)v59 + 112;
          if ( *((_DWORD *)v59 + 235) == 2 )
            CProxy_IInkOverlayEvents<CInkOverlay>::Fire_SelectionMoved(v36, *(_QWORD *)v52);
          else
            CProxy_IInkOverlayEvents<CInkOverlay>::Fire_SelectionResized(v36, *(_QWORD *)v52);
        }
        goto LABEL_105;
      }
      v22 = v50;
      CurrentStroke = CInkOverlay::_PixelToInkSpace(v4, &rc2, v21, v50, lpdwindex);
      v47 = CurrentStroke;
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      v24 = v59;
      if ( *((_DWORD *)v59 + 235) == 2 )
      {
        CurrentStroke = CInkOverlay::_PixelToInkSpace(v4, &rc, v23, v22, lpdwindexa);
        v47 = CurrentStroke;
        if ( CurrentStroke >= 0 )
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 95) + 168LL))(*((_QWORD *)v4 + 95));
          v47 = CurrentStroke;
        }
      }
      else
      {
        *(RECT *)ppv = rc2;
        CIRect::CIRect((CIRect *)&v49, (struct tagRECT *)ppv, &v47);
        CurrentStroke = v47;
        if ( v47 >= 0 )
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)v4 + 95) + 160LL))(
                            *((_QWORD *)v4 + 95),
                            v49);
          v47 = CurrentStroke;
        }
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v49);
      }
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)v4 + 95) + 144LL))(
                        *((_QWORD *)v4 + 95),
                        0,
                        v54);
      v47 = CurrentStroke;
      if ( CurrentStroke >= 0 )
      {
        CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LONG *, RECT *, LONG *, LONG *))(**(_QWORD **)v54 + 136LL))(
                          *(_QWORD *)v54,
                          &rcSrc.top,
                          &rcSrc,
                          &rcSrc.bottom,
                          &rcSrc.right);
        v47 = CurrentStroke;
        if ( CurrentStroke >= 0 )
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, char *, __int128 *, char *, char *))(**(_QWORD **)v52
                                                                                                + 136LL))(
                            *(_QWORD *)v52,
                            (char *)&v73 + 4,
                            &v73,
                            (char *)&v73 + 12,
                            (char *)&v73 + 8);
          v47 = CurrentStroke;
        }
      }
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      v26 = 0;
      if ( *((_DWORD *)v24 + 235) == 2 )
      {
LABEL_97:
        if ( CurrentStroke >= 0 )
        {
          CurrentStroke = CInkCollector::_InkSpaceToPixel(v4, &rcSrc, v25, v50, 0);
          if ( CurrentStroke >= 0 )
          {
            CSelectionRect::GetNormalizedDynamicPosition(v18, &rc2);
            CSelectionRect::SetPosition((struct tagRECT *)v18, *((HWND *)v4 + 7), &rc2, 1);
            if ( v26 )
              CSelectionRect::SetPosition((struct tagRECT *)v18, *((HWND *)v4 + 7), &rcSrc, 1);
            goto LABEL_101;
          }
        }
LABEL_105:
        *((_DWORD *)v4 + 269) = 0;
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v54);
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v52);
LABEL_119:
        *((_DWORD *)v18 + 19) = 0;
        *((_DWORD *)v4 + 270) = 0;
        goto LABEL_122;
      }
      v27 = DWORD2(v73) - v73;
      v28 = HIDWORD(v73) - DWORD1(v73);
      v29 = rcSrc.right - rcSrc.left;
      v57 = rcSrc.bottom - rcSrc.top;
      LODWORD(v49) = rc2.right - rc2.left;
      v56 = rc2.bottom - rc2.top;
      CIXForm::CIXForm(ppv, &v47);
      v30 = v29 - v27;
      if ( v29 - v27 < 0 )
        v30 = v27 - v29;
      if ( v30 < 2 )
      {
        v31 = v27 - (_DWORD)v49;
        v32 = -v31;
        if ( v31 > 0 )
          v32 = v31;
        if ( v32 >= 2 )
        {
          v26 = 1;
          rcSrc.left = v73;
          rcSrc.right = DWORD2(v73);
        }
      }
      v33 = v57 - v28;
      if ( v57 - v28 < 0 )
        v33 = v28 - v57;
      if ( v33 >= 2 )
        goto LABEL_91;
      v34 = v28 - v56;
      v35 = -v34;
      if ( v34 > 0 )
        v35 = v34;
      if ( v35 < 2 )
      {
LABEL_91:
        if ( !v26 )
        {
          CurrentStroke = v47;
LABEL_96:
          ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(ppv);
          v18 = (CInkOverlay *)((char *)v4 + 864);
          goto LABEL_97;
        }
      }
      else
      {
        v26 = 1;
        rcSrc.top = DWORD1(v73);
        rcSrc.bottom = HIDWORD(v73);
      }
      CIRect::CIRect(&v49, &v47);
      CurrentStroke = v47;
      if ( v47 >= 0 )
      {
        v66 = rcSrc;
        CIRect::SetRect((CIRect *)&v49, &v66);
        CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)v4 + 95) + 160LL))(
                          *((_QWORD *)v4 + 95),
                          v49);
      }
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v49);
      goto LABEL_96;
    }
    if ( *((_DWORD *)v4 + 270) )
    {
      v38 = *((_QWORD *)v4 + 67);
      v66 = *(struct tagRECT *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      CurrentStroke = (*(__int64 (__fastcall **)(__int64, struct tagRECT *, __int64, _QWORD, struct IInkStrokes **))(*(_QWORD *)v38 + 168LL))(
                        v38,
                        &v66,
                        v12,
                        0,
                        &v53);
      if ( CurrentStroke < 0 )
      {
LABEL_115:
        *((_DWORD *)v4 + 266) = 0;
        CInkCollector::_InkSpaceToPixel(v4, &v74, v37, v15, 0);
        InflateRect(&v74, 3, 3);
        CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&v66, v58);
        if ( *((_BYTE *)v4 + 264) )
          CInkOverlay::_InvalidateWindow(v4, &v74, 0, 1, 1);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&v66);
        if ( CurrentStroke >= 0 )
          CurrentStroke = CInkOverlay::_SetSelection(v4, v53);
        goto LABEL_119;
      }
    }
    else
    {
      v50 = (HDC)*((_QWORD *)v4 + 132);
      v52[0] = 0;
      CurrentStroke = CInkOverlay::_GetHitTestTolerance(v4, v52, v15);
      if ( CurrentStroke < 0
        || (CurrentStroke = CInkOverlay::_PixelToInkSpace(v4, (int *)&v50, (int *)&v50 + 1, 7, v15, v46),
            CurrentStroke < 0)
        || (CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 67) + 152LL))(
                              *((_QWORD *)v4 + 67),
                              (unsigned int)v50,
                              HIDWORD(v50)),
            CurrentStroke < 0)
        || (GetKeyState(162) & 0x80u) == 0 )
      {
        if ( (GetKeyState(163) & 0x80u) == 0 )
          goto LABEL_115;
      }
    }
    CInkOverlay::_FilterCurrentStroke(v4, v54[0], v53);
    CurrentStroke = ((__int64 (__fastcall *)(struct IInkStrokes *, _QWORD))v53->lpVtbl->AddStrokes)(
                      v53,
                      *((_QWORD *)v4 + 95));
    goto LABEL_115;
  }
  catch ( ... )
  {
    v47 = ReportWispException();
    CurrentStroke = v47;
  }
LABEL_133:
  if ( pvarg.vt == 4095 )
    pvarg.vt = 8;
  VariantClear(&pvarg);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v64);
  return (unsigned int)CurrentStroke;
}

```

## disassembly

```asm
0x1800d8c30  mov     r11, rsp
0x1800d8c33  mov     [r11+10h], rbx
0x1800d8c37  mov     [r11+20h], rsi
0x1800d8c3b  push    rdi
0x1800d8c3c  push    r12
0x1800d8c3e  push    r13
0x1800d8c40  push    r14
0x1800d8c42  push    r15
0x1800d8c44  sub     rsp, 160h
0x1800d8c4b  mov     rax, cs:__security_cookie
0x1800d8c52  xor     rax, rsp
0x1800d8c55  mov     [rsp+188h+var_38], rax
0x1800d8c5d  mov     r12d, r8d
0x1800d8c60  mov     [rsp+188h+var_128], r8d
0x1800d8c65  mov     r14, rcx
0x1800d8c68  mov     qword ptr [rsp+188h+rc2.left], rcx
0x1800d8c70  mov     [rsp+188h+var_108], rcx
0x1800d8c78  mov     [rsp+188h+var_120], r8d
0x1800d8c7d  xorps   xmm0, xmm0
0x1800d8c80  movups  xmmword ptr [r11-48h], xmm0
0x1800d8c85  xor     edi, edi
0x1800d8c87  mov     [r11-0E8h], rdi
0x1800d8c8e  xor     eax, eax
0x1800d8c90  movups  xmmword ptr [rsp+188h+pvarg], xmm0
0x1800d8c98  mov     [r11-98h], rax
0x1800d8c9f  mov     word ptr [rsp+188h+pvarg], di
0x1800d8ca7  mov     [rsp+188h+var_EC], edi
0x1800d8cae  mov     [r11-0F8h], rdi
0x1800d8cb5  lea     rax, [rcx+110h]
0x1800d8cbc  mov     [rsp+188h+var_110], rax
0x1800d8cc1  mov     rdx, rax; struct _RTL_CRITICAL_SECTION *
0x1800d8cc4  lea     rcx, [r11-78h]; this
0x1800d8cc8  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800d8ccd  nop
0x1800d8cce  lea     r13, [r14+1C0h]
0x1800d8cd5  mov     qword ptr [rsp+188h+var_58], r13
0x1800d8cdd  mov     eax, [r13+0]
0x1800d8ce1  mov     [rsp+188h+var_118], eax
0x1800d8ce5  lea     rax, [r14+1F8h]
0x1800d8cec  mov     [rsp+188h+var_90], rax
0x1800d8cf4  mov     rax, [rax]
0x1800d8cf7  mov     [rsp+188h+var_148], rax
0x1800d8cfc  mov     qword ptr [rsp+188h+rcSrc.left], rax
0x1800d8d04  mov     rcx, [r14+268h]
0x1800d8d0b  add     rcx, 8
0x1800d8d0f  mov     rax, [rcx]
0x1800d8d12  xor     r9d, r9d
0x1800d8d15  lea     r8, [rsp+188h+var_F8]
0x1800d8d1d  mov     edx, r12d
0x1800d8d20  mov     rax, [rax+28h]
0x1800d8d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8d29  mov     esi, eax
0x1800d8d2b  mov     [r14+270h], r12d
0x1800d8d32  mov     eax, [r14+350h]
0x1800d8d39  mov     [rsp+188h+var_138], eax
0x1800d8d3d  mov     dword ptr [rsp+188h+var_150], eax
0x1800d8d41  mov     eax, [r13+0]
0x1800d8d45  mov     [rsp+188h+var_158], eax
0x1800d8d49  mov     [rsp+188h+var_114], eax
0x1800d8d4d  lea     rcx, [rsp+188h+rc]; this
0x1800d8d55  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800d8d5a  test    esi, esi
0x1800d8d5c  js      short loc_1800D8D7C
0x1800d8d5e  mov     rcx, [r14+220h]
0x1800d8d65  mov     rax, [rcx]
0x1800d8d68  xor     r9d, r9d
0x1800d8d6b  xor     r8d, r8d
0x1800d8d6e  mov     edx, r12d
0x1800d8d71  mov     rax, [rax+70h]
0x1800d8d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8d7a  mov     esi, eax
0x1800d8d7c  mov     r15d, esi
0x1800d8d7f  mov     [rsp+188h+var_154], di
0x1800d8d84  or      eax, 0FFFFFFFFh
0x1800d8d87  mov     [rsp+188h+var_140], ax
0x1800d8d8c  mov     rbx, rdi
0x1800d8d8f  mov     [rsp+188h+var_100], rbx
0x1800d8d97  test    esi, esi
0x1800d8d99  js      short loc_1800D8DEF
0x1800d8d9b  mov     rdx, [rsp+188h+var_110]; struct _RTL_CRITICAL_SECTION *
0x1800d8da0  lea     rcx, [rsp+188h+rc]; this
0x1800d8da8  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800d8dad  nop
0x1800d8dae  mov     eax, [r14+194h]
0x1800d8db5  test    eax, eax
0x1800d8db7  jz      short loc_1800D8DC2
0x1800d8db9  dec     eax
0x1800d8dbb  mov     [r14+194h], eax
0x1800d8dc2  lea     r8, [rsp+188h+var_100]; struct IInkStrokeDisp **
0x1800d8dca  mov     edx, r12d; unsigned int
0x1800d8dcd  mov     rcx, r14; this
0x1800d8dd0  call    ?_GetCurrentStroke@CInkOverlay@@AEAAJKPEAPEAUIInkStrokeDisp@@@Z; CInkOverlay::_GetCurrentStroke(ulong,IInkStrokeDisp * *)
0x1800d8dd5  mov     esi, eax
0x1800d8dd7  lea     rcx, [rsp+188h+rc]; this
0x1800d8ddf  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800d8de4  mov     r15d, esi
0x1800d8de7  mov     rbx, [rsp+188h+var_100]
0x1800d8def  mov     [rsp+188h+dwindex], edi
0x1800d8df6  lea     rax, [r14+1B8h]
0x1800d8dfd  mov     [rsp+188h+ppv], rax
0x1800d8e05  lea     rcx, [rsp+188h+dwindex]
0x1800d8e0d  mov     [rsp+188h+lpdwindex], rcx; lpdwindex
0x1800d8e12  mov     r9, rax; pHandles
0x1800d8e15  mov     r12d, 1
0x1800d8e1b  mov     r8d, r12d; cHandles
0x1800d8e1e  xor     edx, edx; dwTimeout
0x1800d8e20  xor     ecx, ecx; dwFlags
0x1800d8e22  call    cs:__imp_CoWaitForMultipleHandles
0x1800d8e28  test    eax, eax
0x1800d8e2a  js      loc_1800D8F41
0x1800d8e30  test    r15d, r15d
0x1800d8e33  js      loc_1800D8EE7
0x1800d8e39  mov     r15d, [rsp+188h+var_118]
0x1800d8e3e  test    r15d, r15d
0x1800d8e41  jz      loc_1800D8EE7
0x1800d8e47  mov     rcx, [r14+1B0h]
0x1800d8e4e  mov     rax, [rcx]
0x1800d8e51  mov     rdx, rbx
0x1800d8e54  mov     rax, [rax+68h]
0x1800d8e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8e5d  mov     esi, eax
0x1800d8e5f  test    eax, eax
0x1800d8e61  js      loc_1800D8EE7
0x1800d8e67  lea     rcx, [r14+1A8h]; struct IUnknown **
0x1800d8e6e  mov     rdx, [rsp+188h+var_F8]; struct IUnknown *
0x1800d8e76  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800d8e7b  cmp     r15d, 2
0x1800d8e7f  jnz     short loc_1800D8EBE
0x1800d8e81  lea     rdx, [rsp+188h+var_140]; __int16 *
0x1800d8e86  mov     rcx, r14; this
0x1800d8e89  call    ?_RecognizeGestureStrokes@CInkOverlay@@AEAAJPEAF@Z; CInkOverlay::_RecognizeGestureStrokes(short *)
0x1800d8e8e  mov     esi, eax
0x1800d8e90  cmp     di, [rsp+188h+var_140]
0x1800d8e95  jnz     short loc_1800D8E9C
0x1800d8e97  or      eax, 0FFFFFFFFh
0x1800d8e9a  jmp     short loc_1800D8E9E
0x1800d8e9c  mov     eax, edi
0x1800d8e9e  mov     [rsp+188h+var_154], ax
0x1800d8ea3  mov     rcx, [r14+1B0h]
0x1800d8eaa  mov     rax, [rcx]
0x1800d8ead  mov     rdx, rcx
0x1800d8eb0  mov     rax, [rax+80h]
0x1800d8eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8ebc  jmp     short loc_1800D8EE7
0x1800d8ebe  mov     rcx, [r14+210h]
0x1800d8ec5  xor     r9d, r9d; lpTimerFunc
0x1800d8ec8  mov     r8d, cs:uElapse; uElapse
0x1800d8ecf  mov     rdx, r12; nIDEvent
0x1800d8ed2  mov     rcx, [rcx+8]; hWnd
0x1800d8ed6  call    cs:__imp_SetTimer
0x1800d8edc  mov     ecx, 80004005h
0x1800d8ee1  test    rax, rax
0x1800d8ee4  cmovz   esi, ecx
0x1800d8ee7  jmp     short loc_1800D8F30
0x1800d8ee9  xor     edi, edi
0x1800d8eeb  lea     r12d, [rdi+1]
0x1800d8eef  mov     esi, [rsp+188h+var_158]
0x1800d8ef3  mov     rbx, [rsp+188h+var_100]
0x1800d8efb  mov     eax, [rsp+188h+var_120]
0x1800d8eff  mov     [rsp+188h+var_128], eax
0x1800d8f03  mov     r14, qword ptr [rsp+188h+rc2.left]
0x1800d8f0b  mov     r13, qword ptr [rsp+188h+var_58]
0x1800d8f13  mov     eax, [rsp+188h+var_114]
0x1800d8f17  mov     [rsp+188h+var_158], eax
0x1800d8f1b  mov     rax, qword ptr [rsp+188h+rcSrc.left]
0x1800d8f23  mov     [rsp+188h+var_148], rax
0x1800d8f28  mov     eax, dword ptr [rsp+188h+var_150]
0x1800d8f2c  mov     [rsp+188h+var_138], eax
0x1800d8f30  mov     rcx, [rsp+188h+ppv]
0x1800d8f38  mov     rcx, [rcx]; hMutex
0x1800d8f3b  call    cs:__imp_ReleaseMutex
0x1800d8f41  mov     rdx, [rsp+188h+var_110]; struct _RTL_CRITICAL_SECTION *
0x1800d8f46  lea     rcx, [rsp+188h+rc]; this
0x1800d8f4e  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800d8f53  mov     r15d, [r13+0]
0x1800d8f57  lea     rcx, [rsp+188h+rc]; this
0x1800d8f5f  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800d8f64  or      r13d, 0FFFFFFFFh
0x1800d8f68  test    esi, esi
0x1800d8f6a  js      short loc_1800D8FAF
0x1800d8f6c  cmp     r15d, r12d
0x1800d8f6f  jz      short loc_1800D8FAF
0x1800d8f71  mov     eax, [r14+1C4h]
0x1800d8f78  test    al, 2
0x1800d8f7a  jz      short loc_1800D8FAF
0x1800d8f7c  cmp     r13w, [rsp+188h+var_140]
0x1800d8f82  jnz     short loc_1800D8FAF
0x1800d8f84  lea     rcx, [r14+70h]
0x1800d8f88  lea     r9, [rsp+188h+var_154]
0x1800d8f8d  mov     r8, rbx
0x1800d8f90  mov     rdx, [rsp+188h+var_F8]
0x1800d8f98  call    ?Fire_Stroke@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJPEAUIInkCursor@@PEAUIInkStrokeDisp@@PEAF@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_Stroke(IInkCursor *,IInkStrokeDisp *,short *)
0x1800d8f9d  cmp     [rsp+188h+var_154], di
0x1800d8fa2  mov     [rsp+188h+var_154], di
0x1800d8fa7  jz      short loc_1800D8FAF
0x1800d8fa9  mov     [rsp+188h+var_154], r13w
0x1800d8faf  mov     r15d, edi
0x1800d8fb2  cmp     [rsp+188h+var_158], r12d
0x1800d8fb7  cmovnz  r15d, [rsp+188h+var_138]
0x1800d8fbd  mov     ecx, r15d
0x1800d8fc0  sub     ecx, 1
0x1800d8fc3  jz      loc_1800D909C
0x1800d8fc9  cmp     ecx, 1
0x1800d8fcc  jnz     loc_1800D90A2
0x1800d8fd2  mov     [rsp+188h+var_154], r13w
0x1800d8fd8  mov     rax, [rsp+188h+var_108]
0x1800d8fe0  cmp     [rax+3ACh], r12d
0x1800d8fe7  jnz     short loc_1800D9005
0x1800d8fe9  mov     rax, [rbx]
0x1800d8fec  lea     rdx, [rsp+188h+var_EC]
0x1800d8ff4  mov     rcx, rbx
0x1800d8ff7  mov     rax, [rax+80h]
0x1800d8ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9003  mov     esi, eax
0x1800d9005  test    esi, esi
0x1800d9007  js      loc_1800D91E5
0x1800d900d  mov     rax, [rbx]
0x1800d9010  lea     r9, [rsp+188h+pvarg]
0x1800d9018  mov     r8d, r13d
0x1800d901b  xor     edx, edx
0x1800d901d  mov     rcx, rbx
0x1800d9020  mov     rax, [rax+0E0h]
0x1800d9027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d902c  mov     esi, eax
0x1800d902e  test    eax, eax
0x1800d9030  js      loc_1800D91E5
0x1800d9036  mov     rax, [rbx]
0x1800d9039  lea     r8, [rsp+188h+var_E8]
0x1800d9041  xor     edx, edx
0x1800d9043  mov     rcx, rbx
0x1800d9046  mov     rax, [rax+0A0h]
0x1800d904d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9052  mov     esi, eax
0x1800d9054  test    eax, eax
0x1800d9056  js      loc_1800D91E5
0x1800d905c  mov     rcx, [rsp+188h+var_E8]
0x1800d9064  mov     rax, [rcx]
0x1800d9067  lea     rdx, [rsp+188h+var_48.right]
0x1800d906f  mov     [rsp+188h+lpdwindex], rdx
0x1800d9074  lea     r9, [rsp+188h+var_48.bottom]
0x1800d907c  lea     r8, [rsp+188h+var_48]
0x1800d9084  lea     rdx, [rsp+188h+var_48.top]
0x1800d908c  mov     rax, [rax+88h]
0x1800d9093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9098  mov     esi, eax
0x1800d909a  jmp     short loc_1800D90A2
0x1800d909c  mov     [rsp+188h+var_154], r13w
0x1800d90a2  test    esi, esi
0x1800d90a4  js      loc_1800D91E5
0x1800d90aa  cmp     [rsp+188h+var_154], r13w
0x1800d90b0  jnz     loc_1800D91E5
0x1800d90b6  mov     [rsp+188h+var_158], edi
0x1800d90ba  mov     rax, [rbx]
0x1800d90bd  lea     rdx, [rsp+188h+var_158]
0x1800d90c2  mov     rcx, rbx
0x1800d90c5  mov     rax, [rax+38h]
0x1800d90c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d90ce  test    eax, eax
0x1800d90d0  js      short loc_1800D90EE
0x1800d90d2  mov     rcx, [r14+220h]
0x1800d90d9  mov     rax, [rcx]
0x1800d90dc  lea     r8, [rsp+188h+var_158]
0x1800d90e1  mov     edx, [rsp+188h+var_158]
0x1800d90e5  mov     rax, [rax+48h]
0x1800d90e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d90ee  mov     [rsp+188h+var_150], rdi
0x1800d90f3  mov     rax, [rbx]
0x1800d90f6  lea     r8, [rsp+188h+var_150]
0x1800d90fb  mov     edx, 4
0x1800d9100  mov     rcx, rbx
0x1800d9103  mov     rax, [rax+0A0h]
0x1800d910a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d910f  test    eax, eax
0x1800d9111  js      loc_1800D91D4
0x1800d9117  xorps   xmm0, xmm0
0x1800d911a  movups  xmmword ptr [rsp+188h+rc.left], xmm0
0x1800d9122  mov     rcx, [rsp+188h+var_150]
0x1800d9127  mov     rax, [rcx]
0x1800d912a  lea     rdx, [rsp+188h+rc]
0x1800d9132  mov     rax, [rax+78h]
0x1800d9136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d913b  mov     [rsp+188h+lpdwindex], rdi; struct IInkRenderer *
0x1800d9140  mov     rbx, [rsp+188h+var_148]
0x1800d9145  mov     r9, rbx; HDC
0x1800d9148  lea     rdx, [rsp+188h+rc]; struct tagRECT *
0x1800d9150  mov     rcx, r14; this
0x1800d9153  call    ?_InkSpaceToPixel@CInkCollector@@AEAAJPEAUtagRECT@@HPEAUHDC__@@PEAUIInkRenderer@@@Z; CInkCollector::_InkSpaceToPixel(tagRECT *,int,HDC__ *,IInkRenderer *)
0x1800d9158  mov     edx, 2; dx
0x1800d915d  mov     r8d, edx; dy
0x1800d9160  lea     rcx, [rsp+188h+rc]; lprc
0x1800d9168  call    cs:__imp_InflateRect
0x1800d916e  mov     rcx, [r14+220h]
0x1800d9175  mov     rax, [rcx]
0x1800d9178  mov     r8d, r12d
0x1800d917b  mov     edx, [rsp+188h+var_158]
0x1800d917f  mov     rax, [rax+40h]
0x1800d9183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9188  mov     rdx, [rsp+188h+var_110]; struct _RTL_CRITICAL_SECTION *
0x1800d918d  lea     rcx, [rsp+188h+ppv]; this
0x1800d9195  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
  ... truncated ...
```
