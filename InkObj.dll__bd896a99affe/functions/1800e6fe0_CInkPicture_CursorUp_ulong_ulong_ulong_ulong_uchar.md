# CInkPicture::CursorUp(ulong,ulong,ulong,ulong,uchar *)

- ea: `0x1800e6fe0`
- end: `0x1800e7e9c`
- name: `?CursorUp@CInkPicture@@UEAAJKKKKPEAE@Z`
- size: `3772`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int8 *)`
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
- `0x1800b3f28`
- `0x1800dbaf8`
- `0x1800dbb24`
- `0x1800dd478`
- `0x1800e6fe0`
- `0x1800e9bd0`
- `0x1800e9d28`
- `0x1800ea008`
- `0x1800edfec`
- `0x1800f06ec`
- `0x1800f0b9c`
- `0x1800f0cd8`
- `0x1800f0f48`
- `0x1800f1088`
- `0x1800f1704`
- `0x1800f180c`
- `0x1800f2090`
- `0x1800f2e2c`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e72ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e72ee`
- `USER32!InflateRect` at `0x1800e7522`
- `USER32!InflateRect` at `0x1800e7ce8`
- `USER32!InflateRect` at `0x1800e7522`
- `USER32!InflateRect` at `0x1800e7ce8`
- `USER32!SetTimer` at `0x1800e7289`
- `USER32!SetTimer` at `0x1800e7289`
- `USER32!GetKeyState` at `0x1800e7be6`
- `USER32!GetKeyState` at `0x1800e7bf5`
- `USER32!GetKeyState` at `0x1800e7be6`
- `USER32!GetKeyState` at `0x1800e7bf5`
- `USER32!ReleaseDC` at `0x1800e7df1`
- `USER32!ReleaseDC` at `0x1800e7df1`
- `USER32!EqualRect` at `0x1800e7707`
- `USER32!EqualRect` at `0x1800e7707`
- `GDI32!DeleteObject` at `0x1800e7d71`
- `GDI32!DeleteObject` at `0x1800e7d7e`
- `GDI32!DeleteObject` at `0x1800e7d71`
- `GDI32!DeleteObject` at `0x1800e7d7e`
- `OLEAUT32!__imp_VariantClear` at `0x1800e7e59`
- `OLEAUT32!__imp_VariantClear` at `0x1800e7e59`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800e71d5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800e71d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CInkPicture::CursorUp(CInkPicture *this, __int64 a2, unsigned int a3)
{
  CInkPicture *v4; // r14
  int *v5; // r12
  int CurrentStroke; // esi
  int v7; // r15d
  struct IInkStrokeDisp *v8; // rbx
  int v9; // eax
  __int16 v10; // ax
  int v11; // r15d
  __int64 v12; // r8
  bool v13; // zf
  int v14; // r15d
  CInkPicture *v15; // r12
  HDC v16; // rbx
  int v17; // r8d
  int v18; // r15d
  CSelectionRect *v19; // r15
  BOOL v20; // ebx
  int v21; // r8d
  HDC v22; // rbx
  int v23; // r8d
  int v24; // r8d
  int v25; // r12d
  int v26; // r15d
  int v27; // esi
  int v28; // ebx
  int v29; // eax
  int v30; // r15d
  int v31; // eax
  int v32; // eax
  int v33; // esi
  int v34; // eax
  char *v35; // rcx
  int v36; // r8d
  __int64 v37; // rcx
  HRGN v38; // r8
  HDC *v39; // rbx
  struct IInkRenderer *lpdwindex; // [rsp+20h] [rbp-168h]
  struct IInkRenderer *lpdwindexa; // [rsp+20h] [rbp-168h]
  struct IInkRenderer *v43; // [rsp+28h] [rbp-160h]
  int v44; // [rsp+30h] [rbp-158h] BYREF
  __int16 v45; // [rsp+34h] [rbp-154h] BYREF
  HDC v46; // [rsp+38h] [rbp-150h] BYREF
  __int16 v47; // [rsp+40h] [rbp-148h] BYREF
  LPVOID v48; // [rsp+48h] [rbp-140h] BYREF
  int v49[2]; // [rsp+50h] [rbp-138h] BYREF
  struct IInkStrokes *v50; // [rsp+58h] [rbp-130h] BYREF
  unsigned int v51[2]; // [rsp+60h] [rbp-128h] BYREF
  unsigned int v52; // [rsp+68h] [rbp-120h] BYREF
  int v53; // [rsp+70h] [rbp-118h]
  int v54; // [rsp+74h] [rbp-114h]
  CInkPicture *v55; // [rsp+78h] [rbp-110h]
  struct _RTL_CRITICAL_SECTION *v56; // [rsp+80h] [rbp-108h]
  struct IInkStrokeDisp *v57; // [rsp+88h] [rbp-100h] BYREF
  struct IUnknown *v58; // [rsp+90h] [rbp-F8h] BYREF
  DWORD dwindex; // [rsp+98h] [rbp-F0h] BYREF
  int v60; // [rsp+9Ch] [rbp-ECh] BYREF
  _QWORD v61[2]; // [rsp+A0h] [rbp-E8h] BYREF
  LPVOID ppv[2]; // [rsp+B0h] [rbp-D8h] BYREF
  struct tagRECT v63; // [rsp+C0h] [rbp-C8h] BYREF
  IRecordInfo *pRecInfo; // [rsp+D0h] [rbp-B8h]
  VARIANTARG pvarg; // [rsp+E0h] [rbp-A8h] BYREF
  HDC *v66; // [rsp+F8h] [rbp-90h]
  RECT rcSrc; // [rsp+100h] [rbp-88h] BYREF
  struct tagRECT rc; // [rsp+110h] [rbp-78h] BYREF
  RECT rc2; // [rsp+120h] [rbp-68h] BYREF
  __int128 v70; // [rsp+130h] [rbp-58h] BYREF
  struct tagRECT v71; // [rsp+140h] [rbp-48h] BYREF

  v51[0] = a3;
  v4 = this;
  *(_QWORD *)&rc2.left = this;
  v55 = this;
  v52 = a3;
  v71 = 0;
  v61[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v60 = 0;
  v58 = 0;
  v56 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 496);
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rc, (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
  try
  {
    v5 = (int *)((char *)v4 + 672);
    *(_QWORD *)&v70 = (char *)v4 + 672;
    v53 = *((_DWORD *)v4 + 168);
    v66 = (HDC *)((char *)v4 + 728);
    v46 = (HDC)*((_QWORD *)v4 + 91);
    *(_QWORD *)&rcSrc.left = v46;
    CurrentStroke = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown **, _QWORD))(*(_QWORD *)(*((_QWORD *)v4 + 105) + 8LL)
                                                                                           + 40LL))(
                      *((_QWORD *)v4 + 105) + 8LL,
                      a3,
                      &v58,
                      0);
    *((_DWORD *)v4 + 212) = a3;
    v49[0] = *((_DWORD *)v4 + 268);
    LODWORD(v48) = v49[0];
    v44 = *((_DWORD *)v4 + 168);
    v54 = v44;
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rc);
    if ( CurrentStroke >= 0 )
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 96) + 112LL))(
                        *((_QWORD *)v4 + 96),
                        a3,
                        0,
                        0);
    v7 = CurrentStroke;
    v45 = 0;
    v47 = -1;
    v8 = 0;
    v57 = 0;
    if ( CurrentStroke >= 0 )
    {
      CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rc, v56);
      v9 = *((_DWORD *)v4 + 157);
      if ( v9 )
        *((_DWORD *)v4 + 157) = v9 - 1;
      CurrentStroke = CInkPicture::_GetCurrentStroke(v4, a3, &v57);
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rc);
      v7 = CurrentStroke;
      v8 = v57;
    }
    dwindex = 0;
    ppv[0] = (char *)v4 + 664;
    if ( CoWaitForMultipleHandles(0, 0, 1u, (LPHANDLE)v4 + 83, &dwindex) >= 0 )
    {
      if ( v7 >= 0 && v53 )
      {
        try
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)v4 + 82) + 104LL))(
                            *((_QWORD *)v4 + 82),
                            v8);
          if ( CurrentStroke >= 0 )
          {
            ATL::AtlComPtrAssign((struct IUnknown **)v4 + 81, v58);
            if ( v53 == 2 )
            {
              CurrentStroke = CInkPicture::_RecognizeGestureStrokes(v4, &v47);
              if ( v47 )
                v10 = 0;
              else
                v10 = -1;
              v45 = v10;
              (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 82) + 128LL))(
                *((_QWORD *)v4 + 82),
                *((_QWORD *)v4 + 82));
            }
            else if ( !SetTimer(*(HWND *)(*((_QWORD *)v4 + 94) + 8LL), 1u, *(UINT *)&uElapse, 0) )
            {
              CurrentStroke = -2147467259;
            }
          }
        }
        catch ( ... )
        {
          CurrentStroke = ReportWispException();
          v8 = v57;
          v51[0] = v52;
          v4 = *(CInkPicture **)&rc2.left;
          v5 = (int *)v70;
          v44 = v54;
          v46 = *(HDC *)&rcSrc.left;
          v49[0] = (int)v48;
        }
      }
      ReleaseMutex(*(HANDLE *)ppv[0]);
    }
    CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rc, v56);
    v11 = *v5;
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rc);
    if ( CurrentStroke >= 0 && v11 != 1 && (*((_DWORD *)v4 + 169) & 2) != 0 && v47 == -1 )
    {
      CProxy_IInkPictureEvents<CInkPicture>::Fire_Stroke((char *)v4 + 336, v58, v8, &v45);
      v13 = v45 == 0;
      v45 = 0;
      if ( !v13 )
        v45 = -1;
    }
    v14 = 0;
    if ( v44 != 1 )
      v14 = v49[0];
    v15 = v55;
    if ( v14 == 1 )
    {
      v45 = -1;
    }
    else if ( v14 == 2 )
    {
      v45 = -1;
      if ( *((_DWORD *)v55 + 291) == 1 )
        CurrentStroke = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, int *))v8->lpVtbl->get_PacketCount)(v8, &v60);
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
                        v61);
      if ( CurrentStroke < 0 )
        goto LABEL_49;
      lpdwindex = (struct IInkRenderer *)&v71.right;
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LONG *, struct tagRECT *, LONG *))(*(_QWORD *)v61[0] + 136LL))(
                        v61[0],
                        &v71.top,
                        &v71,
                        &v71.bottom);
    }
    if ( CurrentStroke >= 0 && v45 == -1 )
    {
      v44 = 0;
      if ( ((int (__fastcall *)(struct IInkStrokeDisp *, int *))v8->lpVtbl->get_ID)(v8, &v44) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v4 + 96) + 72LL))(
          *((_QWORD *)v4 + 96),
          (unsigned int)v44,
          &v44);
      v48 = 0;
      if ( ((int (__fastcall *)(struct IInkStrokeDisp *, __int64, LPVOID *))v8->lpVtbl->GetBoundingBox)(v8, 4, &v48) < 0 )
      {
        v16 = v46;
      }
      else
      {
        rc = 0;
        (*(void (__fastcall **)(LPVOID, struct tagRECT *))(*(_QWORD *)v48 + 120LL))(v48, &rc);
        v16 = v46;
        CInkPicture::_InkSpaceToPixel(v4, &rc, v17, v46, 0);
        InflateRect(&rc, 2, 2);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v4 + 96) + 64LL))(
          *((_QWORD *)v4 + 96),
          (unsigned int)v44,
          1);
        CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)ppv, v56);
        if ( *((_BYTE *)v4 + 488) && !v14 )
          CInkPicture::_InvalidateWindow(v4, &rc, 0, 1);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)ppv);
      }
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v48);
      goto LABEL_50;
    }
LABEL_49:
    v16 = v46;
LABEL_50:
    v50 = 0;
    if ( CurrentStroke < 0 )
      goto LABEL_122;
    v18 = v14 - 1;
    if ( !v18 )
    {
      v38 = (HRGN)*((_QWORD *)v4 + 167);
      if ( v38 )
      {
        CInkPicture::_InvalidateWindow(v4, 0, v38, 1);
        DeleteObject(*((HGDIOBJ *)v4 + 167));
        DeleteObject(*((HGDIOBJ *)v4 + 168));
        *((_QWORD *)v4 + 167) = 0;
        *((_QWORD *)v4 + 168) = 0;
      }
      goto LABEL_122;
    }
    if ( v18 != 1 )
    {
LABEL_122:
      CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&v63, v56);
      std::_Tree<std::_Tmap_traits<unsigned long,ATL::CComPtr<IInkStrokeDisp>,std::less<unsigned long>,inkobj_allocator<std::pair<unsigned long,ATL::CComPtr<IInkStrokeDisp>>>,0>>::erase(
        (char *)v4 + 776,
        &v52);
      std::_Tree<std::_Tmap_traits<unsigned long,enum InkOverlayEditingMode,std::less<unsigned long>,inkobj_allocator<std::pair<unsigned long,enum InkOverlayEditingMode>>,0>>::erase(
        (char *)v4 + 792,
        &v52);
      v39 = v66;
      if ( *v66 )
      {
        v13 = (*((_DWORD *)v55 + 184))-- == 1;
        if ( v13 )
        {
          ReleaseDC(*((HWND *)v4 + 21), *v39);
          *v39 = 0;
        }
      }
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&v63);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v50);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v57);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v58);
      goto LABEL_131;
    }
    v19 = (CInkPicture *)((char *)v4 + 1088);
    if ( *((_DWORD *)v4 + 291) != 1 )
    {
      if ( *((_DWORD *)v4 + 291) != 2 && *((_DWORD *)v4 + 291) != 3 )
      {
        if ( *((_DWORD *)v4 + 291) == 4 && !*((_DWORD *)v4 + 324) )
        {
          v46 = (HDC)*((_QWORD *)v4 + 159);
          v49[0] = 0;
          CurrentStroke = CInkPicture::_GetHitTestTolerance(v4, v49, v16);
          if ( CurrentStroke >= 0 )
          {
            CurrentStroke = CInkPicture::_PixelToInkSpace(v4, (int *)&v46, (int *)&v46 + 1, 7, v16, v43);
            if ( CurrentStroke >= 0 )
            {
              CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 95) + 152LL))(
                                *((_QWORD *)v4 + 95),
                                (unsigned int)v46,
                                HIDWORD(v46));
              if ( CurrentStroke >= 0 )
              {
                CInkPicture::_FilterCurrentStroke(v4, v51[0], v50);
                CurrentStroke = CInkPicture::_AddSubSelection(v4, v50);
              }
            }
          }
        }
        goto LABEL_119;
      }
      rc2 = 0;
      rc = 0;
      rcSrc = 0;
      v70 = 0;
      CSelectionRect::GetNormalizedDynamicPosition((CInkPicture *)((char *)v4 + 1088), &rc2);
      CSelectionRect::GetNormalizedPosition((RECT *)v4 + 68, &rc);
      v20 = EqualRect(&rc, &rc2);
      *(_QWORD *)v49 = 0;
      *(_QWORD *)v51 = 0;
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)v4 + 123) + 144LL))(
                        *((_QWORD *)v4 + 123),
                        0,
                        v49);
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      if ( v20 )
      {
LABEL_101:
        if ( *((_DWORD *)v4 + 323) )
        {
          v35 = (char *)v55 + 336;
          if ( *((_DWORD *)v55 + 291) == 2 )
            CProxy_IInkPictureEvents<CInkPicture>::Fire_SelectionMoved(v35, *(_QWORD *)v49);
          else
            CProxy_IInkPictureEvents<CInkPicture>::Fire_SelectionResized(v35, *(_QWORD *)v49);
        }
        goto LABEL_105;
      }
      v22 = v46;
      CurrentStroke = CInkPicture::_PixelToInkSpace(v4, &rc2, v21, v46, lpdwindex);
      v44 = CurrentStroke;
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      if ( *((_DWORD *)v15 + 291) == 2 )
      {
        CurrentStroke = CInkPicture::_PixelToInkSpace(v4, &rc, v23, v22, lpdwindexa);
        v44 = CurrentStroke;
        if ( CurrentStroke >= 0 )
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 123) + 168LL))(*((_QWORD *)v4 + 123));
          v44 = CurrentStroke;
        }
      }
      else
      {
        *(RECT *)ppv = rc2;
        CIRect::CIRect((CIRect *)&v48, (struct tagRECT *)ppv, &v44);
        CurrentStroke = v44;
        if ( v44 >= 0 )
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)v4 + 123) + 160LL))(
                            *((_QWORD *)v4 + 123),
                            v48);
          v44 = CurrentStroke;
        }
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v48);
      }
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)v4 + 123) + 144LL))(
                        *((_QWORD *)v4 + 123),
                        0,
                        v51);
      v44 = CurrentStroke;
      if ( CurrentStroke >= 0 )
      {
        CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LONG *, RECT *, LONG *, LONG *))(**(_QWORD **)v51 + 136LL))(
                          *(_QWORD *)v51,
                          &rcSrc.top,
                          &rcSrc,
                          &rcSrc.bottom,
                          &rcSrc.right);
        v44 = CurrentStroke;
        if ( CurrentStroke >= 0 )
        {
          CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, char *, __int128 *, char *, char *))(**(_QWORD **)v49
                                                                                                + 136LL))(
                            *(_QWORD *)v49,
                            (char *)&v70 + 4,
                            &v70,
                            (char *)&v70 + 12,
                            (char *)&v70 + 8);
          v44 = CurrentStroke;
        }
      }
      if ( CurrentStroke < 0 )
        goto LABEL_105;
      v25 = 0;
      if ( *((_DWORD *)v55 + 291) == 2 )
      {
LABEL_97:
        if ( CurrentStroke >= 0 )
        {
          CurrentStroke = CInkPicture::_InkSpaceToPixel(v4, &rcSrc, v24, v22, 0);
          if ( CurrentStroke >= 0 )
          {
            CSelectionRect::GetNormalizedDynamicPosition(v19, &rc2);
            CSelectionRect::SetPosition((struct tagRECT *)v19, *((HWND *)v4 + 21), &rc2, 1);
            if ( v25 )
              CSelectionRect::SetPosition((struct tagRECT *)v19, *((HWND *)v4 + 21), &rcSrc, 1);
            goto LABEL_101;
          }
        }
LABEL_105:
        *((_DWORD *)v4 + 323) = 0;
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v51);
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v49);
LABEL_119:
        *((_DWORD *)v19 + 19) = 0;
        *((_DWORD *)v4 + 324) = 0;
        goto LABEL_122;
      }
      v26 = DWORD2(v70) - v70;
      v27 = HIDWORD(v70) - DWORD1(v70);
      v28 = rcSrc.right - rcSrc.left;
      v54 = rcSrc.bottom - rcSrc.top;
      LODWORD(v48) = rc2.right - rc2.left;
      v53 = rc2.bottom - rc2.top;
      CIXForm::CIXForm(ppv, &v44);
      v29 = v28 - v26;
      if ( v28 - v26 < 0 )
        v29 = v26 - v28;
      if ( v29 < 2 )
      {
        v30 = v26 - (_DWORD)v48;
        v31 = -v30;
        if ( v30 > 0 )
          v31 = v30;
        if ( v31 >= 2 )
        {
          v25 = 1;
          rcSrc.left = v70;
          rcSrc.right = DWORD2(v70);
        }
      }
      v32 = v54 - v27;
      if ( v54 - v27 < 0 )
        v32 = v27 - v54;
      if ( v32 >= 2 )
        goto LABEL_91;
      v33 = v27 - v53;
      v34 = -v33;
      if ( v33 > 0 )
        v34 = v33;
      if ( v34 < 2 )
      {
LABEL_91:
        if ( !v25 )
        {
          CurrentStroke = v44;
LABEL_96:
          ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(ppv);
          v19 = (CInkPicture *)((char *)v4 + 1088);
          v22 = v46;
          goto LABEL_97;
        }
      }
      else
      {
        v25 = 1;
        rcSrc.top = DWORD1(v70);
        rcSrc.bottom = HIDWORD(v70);
      }
      CIRect::CIRect(&v48, &v44);
      CurrentStroke = v44;
      if ( v44 >= 0 )
      {
        v63 = rcSrc;
        CIRect::SetRect((CIRect *)&v48, &v63);
        CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)v4 + 123) + 160LL))(
                          *((_QWORD *)v4 + 123),
                          v48);
      }
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v48);
      goto LABEL_96;
    }
    if ( *((_DWORD *)v4 + 324) )
    {
      v37 = *((_QWORD *)v4 + 95);
      v63 = *(struct tagRECT *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      CurrentStroke = (*(__int64 (__fastcall **)(__int64, struct tagRECT *, __int64, _QWORD, struct IInkStrokes **))(*(_QWORD *)v37 + 168LL))(
                        v37,
                        &v63,
                        v12,
                        0,
                        &v50);
      if ( CurrentStroke < 0 )
      {
LABEL_115:
        *((_DWORD *)v4 + 320) = 0;
        CInkPicture::_InkSpaceToPixel(v4, &v71, v36, v16, 0);
        InflateRect(&v71, 3, 3);
        CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&v63, v56);
        if ( *((_BYTE *)v4 + 488) )
          CInkPicture::_InvalidateWindow(v4, &v71, 0, 1);
        CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&v63);
        if ( CurrentStroke >= 0 )
          CurrentStroke = CInkPicture::_SetSelection(v4, v50);
        goto LABEL_119;
      }
    }
    else
    {
      v46 = (HDC)*((_QWORD *)v4 + 159);
      v49[0] = 0;
      CurrentStroke = CInkPicture::_GetHitTestTolerance(v4, v49, v16);
      if ( CurrentStroke < 0
        || (CurrentStroke = CInkPicture::_PixelToInkSpace(v4, (int *)&v46, (int *)&v46 + 1, 7, v16, v43),
            CurrentStroke < 0)
        || (CurrentStroke = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v4 + 95) + 152LL))(
                              *((_QWORD *)v4 + 95),
                              (unsigned int)v46,
                              HIDWORD(v46)),
            CurrentStroke < 0)
        || (GetKeyState(162) & 0x80u) == 0 )
      {
        if ( (GetKeyState(163) & 0x80u) == 0 )
          goto LABEL_115;
      }
    }
    CInkPicture::_FilterCurrentStroke(v4, v51[0], v50);
    CurrentStroke = ((__int64 (__fastcall *)(struct IInkStrokes *, _QWORD))v50->lpVtbl->AddStrokes)(
                      v50,
                      *((_QWORD *)v4 + 123));
    goto LABEL_115;
  }
  catch ( ... )
  {
    v44 = ReportWispException();
    CurrentStroke = v44;
  }
LABEL_131:
  if ( pvarg.vt == 4095 )
    pvarg.vt = 8;
  VariantClear(&pvarg);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v61);
  return (unsigned int)CurrentStroke;
}

```

## disassembly

```asm
0x1800e6fe0  mov     r11, rsp
0x1800e6fe3  mov     [r11+10h], rbx
0x1800e6fe7  mov     [r11+20h], rsi
0x1800e6feb  push    rdi
0x1800e6fec  push    r12
0x1800e6fee  push    r13
0x1800e6ff0  push    r14
0x1800e6ff2  push    r15
0x1800e6ff4  sub     rsp, 160h
0x1800e6ffb  mov     rax, cs:__security_cookie
0x1800e7002  xor     rax, rsp
0x1800e7005  mov     [rsp+188h+var_38], rax
0x1800e700d  mov     r13d, r8d
0x1800e7010  mov     [rsp+188h+var_128], r8d
0x1800e7015  mov     r14, rcx
0x1800e7018  mov     qword ptr [rsp+188h+rc2.left], rcx
0x1800e7020  mov     [rsp+188h+var_110], rcx
0x1800e7025  mov     [rsp+188h+var_120], r8d
0x1800e702a  xorps   xmm0, xmm0
0x1800e702d  movups  xmmword ptr [r11-48h], xmm0
0x1800e7032  xor     edi, edi
0x1800e7034  mov     [r11-0E8h], rdi
0x1800e703b  xor     eax, eax
0x1800e703d  movups  xmmword ptr [rsp+188h+pvarg], xmm0
0x1800e7045  mov     [r11-98h], rax
0x1800e704c  mov     word ptr [rsp+188h+pvarg], di
0x1800e7054  mov     [rsp+188h+var_EC], edi
0x1800e705b  mov     [r11-0F8h], rdi
0x1800e7062  lea     rax, [rcx+1F0h]
0x1800e7069  mov     [rsp+188h+var_108], rax
0x1800e7071  mov     rdx, rax; struct _RTL_CRITICAL_SECTION *
0x1800e7074  lea     rcx, [r11-78h]; this
0x1800e7078  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e707d  nop
0x1800e707e  lea     r12, [r14+2A0h]
0x1800e7085  mov     qword ptr [rsp+188h+var_58], r12
0x1800e708d  mov     eax, [r12]
0x1800e7091  mov     [rsp+188h+var_118], eax
0x1800e7095  lea     rax, [r14+2D8h]
0x1800e709c  mov     [rsp+188h+var_90], rax
0x1800e70a4  mov     rax, [rax]
0x1800e70a7  mov     [rsp+188h+var_150], rax
0x1800e70ac  mov     qword ptr [rsp+188h+rcSrc.left], rax
0x1800e70b4  mov     rcx, [r14+348h]
0x1800e70bb  add     rcx, 8
0x1800e70bf  mov     rax, [rcx]
0x1800e70c2  xor     r9d, r9d
0x1800e70c5  lea     r8, [rsp+188h+var_F8]
0x1800e70cd  mov     edx, r13d
0x1800e70d0  mov     rax, [rax+28h]
0x1800e70d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e70d9  mov     esi, eax
0x1800e70db  mov     [r14+350h], r13d
0x1800e70e2  mov     eax, [r14+430h]
0x1800e70e9  mov     [rsp+188h+var_138], eax
0x1800e70ed  mov     dword ptr [rsp+188h+var_140], eax
0x1800e70f1  mov     eax, [r12]
0x1800e70f5  mov     [rsp+188h+var_158], eax
0x1800e70f9  mov     [rsp+188h+var_114], eax
0x1800e70fd  lea     rcx, [rsp+188h+rc]; this
0x1800e7105  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e710a  test    esi, esi
0x1800e710c  js      short loc_1800E712C
0x1800e710e  mov     rcx, [r14+300h]
0x1800e7115  mov     rax, [rcx]
0x1800e7118  xor     r9d, r9d
0x1800e711b  xor     r8d, r8d
0x1800e711e  mov     edx, r13d
0x1800e7121  mov     rax, [rax+70h]
0x1800e7125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e712a  mov     esi, eax
0x1800e712c  mov     r15d, esi
0x1800e712f  mov     [rsp+188h+var_154], di
0x1800e7134  or      eax, 0FFFFFFFFh
0x1800e7137  mov     [rsp+188h+var_148], ax
0x1800e713c  mov     rbx, rdi
0x1800e713f  mov     [rsp+188h+var_100], rbx
0x1800e7147  test    esi, esi
0x1800e7149  js      short loc_1800E71A2
0x1800e714b  mov     rdx, [rsp+188h+var_108]; struct _RTL_CRITICAL_SECTION *
0x1800e7153  lea     rcx, [rsp+188h+rc]; this
0x1800e715b  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e7160  nop
0x1800e7161  mov     eax, [r14+274h]
0x1800e7168  test    eax, eax
0x1800e716a  jz      short loc_1800E7175
0x1800e716c  dec     eax
0x1800e716e  mov     [r14+274h], eax
0x1800e7175  lea     r8, [rsp+188h+var_100]; struct IInkStrokeDisp **
0x1800e717d  mov     edx, r13d; unsigned int
0x1800e7180  mov     rcx, r14; this
0x1800e7183  call    ?_GetCurrentStroke@CInkPicture@@AEAAJKPEAPEAUIInkStrokeDisp@@@Z; CInkPicture::_GetCurrentStroke(ulong,IInkStrokeDisp * *)
0x1800e7188  mov     esi, eax
0x1800e718a  lea     rcx, [rsp+188h+rc]; this
0x1800e7192  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e7197  mov     r15d, esi
0x1800e719a  mov     rbx, [rsp+188h+var_100]
0x1800e71a2  mov     [rsp+188h+dwindex], edi
0x1800e71a9  lea     rax, [r14+298h]
0x1800e71b0  mov     [rsp+188h+ppv], rax
0x1800e71b8  lea     rcx, [rsp+188h+dwindex]
0x1800e71c0  mov     [rsp+188h+lpdwindex], rcx; lpdwindex
0x1800e71c5  mov     r9, rax; pHandles
0x1800e71c8  mov     r13d, 1
0x1800e71ce  mov     r8d, r13d; cHandles
0x1800e71d1  xor     edx, edx; dwTimeout
0x1800e71d3  xor     ecx, ecx; dwFlags
0x1800e71d5  call    cs:__imp_CoWaitForMultipleHandles
0x1800e71db  test    eax, eax
0x1800e71dd  js      loc_1800E72F4
0x1800e71e3  test    r15d, r15d
0x1800e71e6  js      loc_1800E729A
0x1800e71ec  mov     r15d, [rsp+188h+var_118]
0x1800e71f1  test    r15d, r15d
0x1800e71f4  jz      loc_1800E729A
0x1800e71fa  mov     rcx, [r14+290h]
0x1800e7201  mov     rax, [rcx]
0x1800e7204  mov     rdx, rbx
0x1800e7207  mov     rax, [rax+68h]
0x1800e720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7210  mov     esi, eax
0x1800e7212  test    eax, eax
0x1800e7214  js      loc_1800E729A
0x1800e721a  lea     rcx, [r14+288h]; struct IUnknown **
0x1800e7221  mov     rdx, [rsp+188h+var_F8]; struct IUnknown *
0x1800e7229  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e722e  cmp     r15d, 2
0x1800e7232  jnz     short loc_1800E7271
0x1800e7234  lea     rdx, [rsp+188h+var_148]; __int16 *
0x1800e7239  mov     rcx, r14; this
0x1800e723c  call    ?_RecognizeGestureStrokes@CInkPicture@@AEAAJPEAF@Z; CInkPicture::_RecognizeGestureStrokes(short *)
0x1800e7241  mov     esi, eax
0x1800e7243  cmp     di, [rsp+188h+var_148]
0x1800e7248  jnz     short loc_1800E724F
0x1800e724a  or      eax, 0FFFFFFFFh
0x1800e724d  jmp     short loc_1800E7251
0x1800e724f  mov     eax, edi
0x1800e7251  mov     [rsp+188h+var_154], ax
0x1800e7256  mov     rcx, [r14+290h]
0x1800e725d  mov     rax, [rcx]
0x1800e7260  mov     rdx, rcx
0x1800e7263  mov     rax, [rax+80h]
0x1800e726a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e726f  jmp     short loc_1800E729A
0x1800e7271  mov     rcx, [r14+2F0h]
0x1800e7278  xor     r9d, r9d; lpTimerFunc
0x1800e727b  mov     r8d, cs:uElapse; uElapse
0x1800e7282  mov     rdx, r13; nIDEvent
0x1800e7285  mov     rcx, [rcx+8]; hWnd
0x1800e7289  call    cs:__imp_SetTimer
0x1800e728f  mov     ecx, 80004005h
0x1800e7294  test    rax, rax
0x1800e7297  cmovz   esi, ecx
0x1800e729a  jmp     short loc_1800E72E3
0x1800e729c  xor     edi, edi
0x1800e729e  lea     r13d, [rdi+1]
0x1800e72a2  mov     esi, [rsp+188h+var_158]
0x1800e72a6  mov     rbx, [rsp+188h+var_100]
0x1800e72ae  mov     eax, [rsp+188h+var_120]
0x1800e72b2  mov     [rsp+188h+var_128], eax
0x1800e72b6  mov     r14, qword ptr [rsp+188h+rc2.left]
0x1800e72be  mov     r12, qword ptr [rsp+188h+var_58]
0x1800e72c6  mov     eax, [rsp+188h+var_114]
0x1800e72ca  mov     [rsp+188h+var_158], eax
0x1800e72ce  mov     rax, qword ptr [rsp+188h+rcSrc.left]
0x1800e72d6  mov     [rsp+188h+var_150], rax
0x1800e72db  mov     eax, dword ptr [rsp+188h+var_140]
0x1800e72df  mov     [rsp+188h+var_138], eax
0x1800e72e3  mov     rcx, [rsp+188h+ppv]
0x1800e72eb  mov     rcx, [rcx]; hMutex
0x1800e72ee  call    cs:__imp_ReleaseMutex
0x1800e72f4  mov     rdx, [rsp+188h+var_108]; struct _RTL_CRITICAL_SECTION *
0x1800e72fc  lea     rcx, [rsp+188h+rc]; this
0x1800e7304  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e7309  mov     r15d, [r12]
0x1800e730d  lea     rcx, [rsp+188h+rc]; this
0x1800e7315  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e731a  or      edx, 0FFFFFFFFh
0x1800e731d  test    esi, esi
0x1800e731f  js      short loc_1800E7368
0x1800e7321  cmp     r15d, r13d
0x1800e7324  jz      short loc_1800E7368
0x1800e7326  mov     eax, [r14+2A4h]
0x1800e732d  test    al, 2
0x1800e732f  jz      short loc_1800E7368
0x1800e7331  cmp     dx, [rsp+188h+var_148]
0x1800e7336  jnz     short loc_1800E7368
0x1800e7338  lea     rcx, [r14+150h]
0x1800e733f  lea     r9, [rsp+188h+var_154]
0x1800e7344  mov     r8, rbx
0x1800e7347  mov     rdx, [rsp+188h+var_F8]
0x1800e734f  call    ?Fire_Stroke@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJPEAUIInkCursor@@PEAUIInkStrokeDisp@@PEAF@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_Stroke(IInkCursor *,IInkStrokeDisp *,short *)
0x1800e7354  or      edx, 0FFFFFFFFh
0x1800e7357  cmp     [rsp+188h+var_154], di
0x1800e735c  mov     [rsp+188h+var_154], di
0x1800e7361  jz      short loc_1800E7368
0x1800e7363  mov     [rsp+188h+var_154], dx
0x1800e7368  mov     r15d, edi
0x1800e736b  cmp     [rsp+188h+var_158], r13d
0x1800e7370  cmovnz  r15d, [rsp+188h+var_138]
0x1800e7376  mov     ecx, r15d
0x1800e7379  sub     ecx, 1
0x1800e737c  mov     r12, [rsp+188h+var_110]
0x1800e7381  jz      loc_1800E7455
0x1800e7387  cmp     ecx, 1
0x1800e738a  jnz     loc_1800E745A
0x1800e7390  mov     [rsp+188h+var_154], dx
0x1800e7395  cmp     [r12+48Ch], r13d
0x1800e739d  jnz     short loc_1800E73BE
0x1800e739f  mov     rax, [rbx]
0x1800e73a2  lea     rdx, [rsp+188h+var_EC]
0x1800e73aa  mov     rcx, rbx
0x1800e73ad  mov     rax, [rax+80h]
0x1800e73b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e73b9  mov     esi, eax
0x1800e73bb  or      edx, 0FFFFFFFFh
0x1800e73be  test    esi, esi
0x1800e73c0  js      loc_1800E759D
0x1800e73c6  mov     rax, [rbx]
0x1800e73c9  lea     r9, [rsp+188h+pvarg]
0x1800e73d1  mov     r8d, edx
0x1800e73d4  xor     edx, edx
0x1800e73d6  mov     rcx, rbx
0x1800e73d9  mov     rax, [rax+0E0h]
0x1800e73e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e73e5  mov     esi, eax
0x1800e73e7  test    eax, eax
0x1800e73e9  js      loc_1800E759D
0x1800e73ef  mov     rax, [rbx]
0x1800e73f2  lea     r8, [rsp+188h+var_E8]
0x1800e73fa  xor     edx, edx
0x1800e73fc  mov     rcx, rbx
0x1800e73ff  mov     rax, [rax+0A0h]
0x1800e7406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e740b  mov     esi, eax
0x1800e740d  test    eax, eax
0x1800e740f  js      loc_1800E759D
0x1800e7415  mov     rcx, [rsp+188h+var_E8]
0x1800e741d  mov     rax, [rcx]
0x1800e7420  lea     rdx, [rsp+188h+var_48.right]
0x1800e7428  mov     [rsp+188h+lpdwindex], rdx
0x1800e742d  lea     r9, [rsp+188h+var_48.bottom]
0x1800e7435  lea     r8, [rsp+188h+var_48]
0x1800e743d  lea     rdx, [rsp+188h+var_48.top]
0x1800e7445  mov     rax, [rax+88h]
0x1800e744c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7451  mov     esi, eax
0x1800e7453  jmp     short loc_1800E745A
0x1800e7455  mov     [rsp+188h+var_154], dx
0x1800e745a  test    esi, esi
0x1800e745c  js      loc_1800E759D
0x1800e7462  or      eax, 0FFFFFFFFh
0x1800e7465  cmp     [rsp+188h+var_154], ax
0x1800e746a  jnz     loc_1800E759D
0x1800e7470  mov     [rsp+188h+var_158], edi
0x1800e7474  mov     rax, [rbx]
0x1800e7477  lea     rdx, [rsp+188h+var_158]
0x1800e747c  mov     rcx, rbx
0x1800e747f  mov     rax, [rax+38h]
0x1800e7483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7488  test    eax, eax
0x1800e748a  js      short loc_1800E74A8
0x1800e748c  mov     rcx, [r14+300h]
0x1800e7493  mov     rax, [rcx]
0x1800e7496  lea     r8, [rsp+188h+var_158]
0x1800e749b  mov     edx, [rsp+188h+var_158]
0x1800e749f  mov     rax, [rax+48h]
0x1800e74a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e74a8  mov     [rsp+188h+var_140], rdi
0x1800e74ad  mov     rax, [rbx]
0x1800e74b0  lea     r8, [rsp+188h+var_140]
0x1800e74b5  mov     edx, 4
0x1800e74ba  mov     rcx, rbx
0x1800e74bd  mov     rax, [rax+0A0h]
0x1800e74c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e74c9  test    eax, eax
0x1800e74cb  js      loc_1800E758C
0x1800e74d1  xorps   xmm0, xmm0
0x1800e74d4  movups  xmmword ptr [rsp+188h+rc.left], xmm0
0x1800e74dc  mov     rcx, [rsp+188h+var_140]
0x1800e74e1  mov     rax, [rcx]
0x1800e74e4  lea     rdx, [rsp+188h+rc]
0x1800e74ec  mov     rax, [rax+78h]
0x1800e74f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e74f5  mov     [rsp+188h+lpdwindex], rdi; int
0x1800e74fa  mov     rbx, [rsp+188h+var_150]
0x1800e74ff  mov     r9, rbx; HDC
0x1800e7502  lea     rdx, [rsp+188h+rc]; struct tagRECT *
0x1800e750a  mov     rcx, r14; this
0x1800e750d  call    ?_InkSpaceToPixel@CInkPicture@@AEAAJPEAUtagRECT@@HPEAUHDC__@@PEAUIInkRenderer@@@Z; CInkPicture::_InkSpaceToPixel(tagRECT *,int,HDC__ *,IInkRenderer *)
0x1800e7512  mov     edx, 2; dx
0x1800e7517  mov     r8d, edx; dy
0x1800e751a  lea     rcx, [rsp+188h+rc]; lprc
0x1800e7522  call    cs:__imp_InflateRect
0x1800e7528  mov     rcx, [r14+300h]
0x1800e752f  mov     rax, [rcx]
0x1800e7532  mov     r8d, r13d
0x1800e7535  mov     edx, [rsp+188h+var_158]
0x1800e7539  mov     rax, [rax+40h]
0x1800e753d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
