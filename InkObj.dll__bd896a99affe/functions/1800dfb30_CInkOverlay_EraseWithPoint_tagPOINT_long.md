# CInkOverlay::_EraseWithPoint(tagPOINT,long)

- ea: `0x1800dfb30`
- end: `0x1800e03c3`
- name: `?_EraseWithPoint@CInkOverlay@@AEAAJUtagPOINT@@J@Z`
- size: `2195`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this, struct tagPOINT, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e1434`

## callees

- `0x180001c20`
- `0x18000a730`
- `0x1800217b0`
- `0x18002a3ac`
- `0x1800365f8`
- `0x180036824`
- `0x180036888`
- `0x180037e68`
- `0x1800a991c`
- `0x1800acf04`
- `0x1800d7eb4`
- `0x1800dfb30`
- `0x1800e03cc`
- `0x1800e08c0`
- `0x1800e0ab0`
- `0x1800e0c54`
- `0x1800e137c`
- `0x1800e2850`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e028b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e02c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e028b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e02c6`
- `USER32!InflateRect` at `0x1800dfd9b`
- `USER32!InflateRect` at `0x1800e012c`
- `USER32!InflateRect` at `0x1800dfd9b`
- `USER32!InflateRect` at `0x1800e012c`
- `GDI32!CombineRgn` at `0x1800e024c`
- `GDI32!CombineRgn` at `0x1800e0308`
- `GDI32!CombineRgn` at `0x1800e0331`
- `GDI32!CombineRgn` at `0x1800e024c`
- `GDI32!CombineRgn` at `0x1800e0308`
- `GDI32!CombineRgn` at `0x1800e0331`
- `GDI32!CreateRectRgn` at `0x1800dfbaf`
- `GDI32!CreateRectRgn` at `0x1800e020a`
- `GDI32!CreateRectRgn` at `0x1800e0279`
- `GDI32!CreateRectRgn` at `0x1800e02b4`
- `GDI32!CreateRectRgn` at `0x1800dfbaf`
- `GDI32!CreateRectRgn` at `0x1800e020a`
- `GDI32!CreateRectRgn` at `0x1800e0279`
- `GDI32!CreateRectRgn` at `0x1800e02b4`
- `GDI32!DeleteObject` at `0x1800e02e4`
- `GDI32!DeleteObject` at `0x1800e0359`
- `GDI32!DeleteObject` at `0x1800e0375`
- `GDI32!DeleteObject` at `0x1800e02e4`
- `GDI32!DeleteObject` at `0x1800e0359`
- `GDI32!DeleteObject` at `0x1800e0375`
- `OLEAUT32!__imp_VariantClear` at `0x1800e01b4`
- `OLEAUT32!__imp_VariantClear` at `0x1800e01b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CInkOverlay::_EraseWithPoint(CInkOverlay *this, struct tagPOINT a2, int a3)
{
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  int v6; // r12d
  unsigned int v7; // r13d
  int v8; // eax
  signed int SelectedStrokeSizeIncrease; // edi
  struct IUnknown *v10; // rbx
  __int64 v11; // r8
  int v12; // r15d
  HRGN v13; // r13
  signed int v14; // r14d
  unsigned __int8 *v15; // r12
  float v16; // xmm7_4
  float v17; // xmm6_4
  __int64 v18; // rdx
  int v19; // eax
  struct IInkStrokeDisp *v20; // rdx
  int IsSelected; // ebx
  __int64 v22; // rdx
  int v23; // ebx
  HDC v24; // r9
  HRGN RectRgn; // rax
  HRGN v26; // rbx
  HRGN v27; // r14
  HRGN v28; // rax
  signed int LastError; // eax
  HRGN v30; // rax
  signed int v31; // eax
  void *v32; // rcx
  HRGN v33; // rcx
  struct IInkStrokeDisp *v35; // [rsp+38h] [rbp-D0h] BYREF
  struct IInkStrokeDisp *v36; // [rsp+40h] [rbp-C8h] BYREF
  bool v37[4]; // [rsp+48h] [rbp-C0h] BYREF
  int v38; // [rsp+4Ch] [rbp-BCh] BYREF
  int v39[2]; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  int v41; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v43; // [rsp+6Ch] [rbp-9Ch] BYREF
  int dy[2]; // [rsp+70h] [rbp-98h] BYREF
  struct IInkStrokes *v45; // [rsp+78h] [rbp-90h] BYREF
  __int64 v46; // [rsp+80h] [rbp-88h] BYREF
  __int64 v47; // [rsp+88h] [rbp-80h] BYREF
  HRGN hrgnDst; // [rsp+90h] [rbp-78h]
  struct IUnknown *v49; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int8 *v50; // [rsp+A0h] [rbp-68h] BYREF
  struct tagRECT v51; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  struct tagRECT v53; // [rsp+D8h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+E8h] [rbp-20h] BYREF
  struct tagRECT v55; // [rsp+F8h] [rbp-10h] BYREF

  ppv = 0;
  v49 = 0;
  v45 = 0;
  v39[0] = 0;
  v4 = a2.x - a3;
  v53.left = a2.x - a3;
  v5 = a2.y - a3;
  v53.top = a2.y - a3;
  v6 = a3 + a2.x;
  v53.right = a3 + a2.x;
  v7 = a3 + a2.y;
  v53.bottom = a3 + a2.y;
  hrgnDst = CreateRectRgn(0, 0, 0, 0);
  v8 = ATL::CComObject<CInkRectangle>::CreateInstance(&ppv);
  SelectedStrokeSizeIncrease = v8;
  if ( !ppv )
  {
    SelectedStrokeSizeIncrease = -2147418113;
LABEL_57:
    if ( SelectedStrokeSizeIncrease >= 0 )
    {
      CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&v51, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v26 = RectRgn;
      if ( RectRgn )
        SelectedStrokeSizeIncrease = CInkOverlay::_PlaceInkSpaceRectIntoRegion(this, &v53, RectRgn, 0);
      if ( *((_BYTE *)this + 264) )
      {
        v27 = hrgnDst;
        if ( !CombineRgn(hrgnDst, hrgnDst, v26, 2) )
          SelectedStrokeSizeIncrease = -2147418113;
        if ( SelectedStrokeSizeIncrease >= 0 )
        {
          if ( !*((_QWORD *)this + 140) )
          {
            v28 = CreateRectRgn(0, 0, 0, 0);
            *((_QWORD *)this + 140) = v28;
            if ( !v28 )
            {
              LastError = GetLastError();
              SelectedStrokeSizeIncrease = LastError;
              if ( LastError > 0 )
                SelectedStrokeSizeIncrease = (unsigned __int16)LastError | 0x80070000;
            }
          }
          if ( SelectedStrokeSizeIncrease >= 0 )
          {
            if ( !*((_QWORD *)this + 141) )
            {
              v30 = CreateRectRgn(0, 0, 0, 0);
              *((_QWORD *)this + 141) = v30;
              if ( !v30 )
              {
                v31 = GetLastError();
                SelectedStrokeSizeIncrease = v31;
                if ( v31 > 0 )
                  SelectedStrokeSizeIncrease = (unsigned __int16)v31 | 0x80070000;
                v32 = (void *)*((_QWORD *)this + 140);
                if ( v32 )
                {
                  DeleteObject(v32);
                  *((_QWORD *)this + 140) = 0;
                }
              }
            }
            if ( SelectedStrokeSizeIncrease >= 0 && !CombineRgn(*((HRGN *)this + 140), *((HRGN *)this + 140), v27, 2) )
              SelectedStrokeSizeIncrease = -2147418113;
          }
        }
        if ( v26 )
        {
          v33 = (HRGN)*((_QWORD *)this + 141);
          if ( v33 && !CombineRgn(v33, *((HRGN *)this + 141), v26, 2) )
            SelectedStrokeSizeIncrease = -2147418113;
          CInkOverlay::_InvalidateWindow(this, 0, v26, 1, 1);
          DeleteObject(v26);
        }
      }
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&v51);
    }
    goto LABEL_84;
  }
  if ( v8 < 0 )
    goto LABEL_57;
  ATL::AtlComPtrAssign(&v49, (struct IUnknown *)ppv + 1);
  v10 = v49;
  SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD, int))v49->lpVtbl[6].QueryInterface)(
                                 v49,
                                 v5,
                                 v4,
                                 v7,
                                 v6);
  if ( SelectedStrokeSizeIncrease < 0 )
    goto LABEL_57;
  SelectedStrokeSizeIncrease = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, __int64, struct IInkStrokes **))(**((_QWORD **)this + 67) + 160LL))(
                                 *((_QWORD *)this + 67),
                                 v10,
                                 v11,
                                 &v45);
  if ( SelectedStrokeSizeIncrease < 0 )
    goto LABEL_57;
  CInkOverlay::_FilterCurrentStroke(this, *((_DWORD *)this + 156), v45);
  SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokes *, int *))v45->lpVtbl->get_Count)(v45, v39);
  if ( SelectedStrokeSizeIncrease < 0 || v39[0] <= 0 )
    goto LABEL_57;
  v12 = 0;
  v13 = hrgnDst;
  do
  {
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    v35 = 0;
    v50 = 0;
    v42 = 0;
    v43 = 0;
    CIRect::CIRect(&ppv, &v39[1]);
    v51 = v53;
    CIRect::SetRect((CIRect *)&ppv, &v51);
    SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokes *, _QWORD, struct IInkStrokeDisp **))v45->lpVtbl->Item)(
                                   v45,
                                   (unsigned int)v12,
                                   &v35);
    v47 = 0;
    if ( SelectedStrokeSizeIncrease < 0 )
    {
      v38 = 0;
    }
    else
    {
      SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))v35->lpVtbl->get_DrawingAttributes)(
                                     v35,
                                     &v47);
      v38 = 0;
      if ( SelectedStrokeSizeIncrease >= 0 )
      {
        SelectedStrokeSizeIncrease = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 184LL))(v47, &v38);
        if ( SelectedStrokeSizeIncrease >= 0 )
        {
          if ( v38
            || (v39[1] = 0,
                SelectedStrokeSizeIncrease = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 72LL))(
                                               v47,
                                               &v39[1]),
                rc = v53,
                InflateRect(&rc, (int)(*(float *)&v39[1] * 0.5), (int)(*(float *)&v39[1] * 0.5)),
                v51 = rc,
                CIRect::SetRect((CIRect *)&ppv, &v51),
                SelectedStrokeSizeIncrease >= 0) )
          {
            SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, LPVOID, VARIANTARG *))v35->lpVtbl->GetRectangleIntersections)(
                                           v35,
                                           ppv,
                                           &pvarg);
            if ( SelectedStrokeSizeIncrease >= 0 )
            {
              SelectedStrokeSizeIncrease = AccessVariantData(&pvarg, &v50, &v42, &v43, v37, 0);
              if ( SelectedStrokeSizeIncrease >= 0 )
              {
                v14 = v42 / v43 - 1;
                if ( v14 > 0 )
                {
                  v15 = v50;
                  while ( 1 )
                  {
                    v16 = *(float *)&v15[4 * v14];
                    v17 = *(float *)&v15[4 * v14 - 4];
                    v36 = 0;
                    v46 = 0;
                    CIRect::CIRect((CIRect *)&v41, 0);
                    if ( v16 == -1.0 )
                      break;
                    if ( v17 != -1.0 )
                      goto LABEL_33;
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, struct IInkStrokeDisp **))v35->lpVtbl->Split)(
                            v35,
                            v18,
                            &v36);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    IsSelected = CInkOverlay::_IsSelected(this, v35);
                    if ( !IsSelected )
                    {
                      v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 95) + 120LL))(
                              *((_QWORD *)this + 95),
                              v35);
                      SelectedStrokeSizeIncrease = v19;
                      if ( v19 < 0 )
                        goto LABEL_45;
                    }
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, int *))v35->lpVtbl->GetBoundingBox)(
                            v35,
                            0,
                            &v41);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 67) + 112LL))(
                            *((_QWORD *)this + 67),
                            v35);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    if ( IsSelected )
                    {
                      if ( IsSelected != 1 )
                      {
                        SelectedStrokeSizeIncrease = IsSelected;
                        goto LABEL_46;
                      }
                      goto LABEL_45;
                    }
LABEL_42:
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 95) + 104LL))(
                            *((_QWORD *)this + 95),
                            v36);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 >= 0 )
                    {
                      v19 = CInkOverlay::_SetSelection(this, *((struct IInkStrokes **)this + 95));
                      goto LABEL_44;
                    }
LABEL_45:
                    IsSelected = v19;
LABEL_46:
                    CIRect::GetRect((CIRect *)&v41, &v55);
                    dy[1] = 0;
                    dy[0] = 0;
                    if ( IsSelected >= 0 )
                    {
                      SelectedStrokeSizeIncrease = CInkOverlay::_GetSelectedStrokeSizeIncrease(this, &dy[1], dy, v24);
                      if ( SelectedStrokeSizeIncrease >= 0 )
                      {
                        InflateRect(&v55, dy[1], dy[0]);
                        CInkOverlay::_PlaceInkSpaceRectIntoRegion(this, &v55, v13, 1);
                      }
                    }
                    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v41);
                    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v46);
                    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v36);
                    v14 -= 2;
                    if ( v14 <= 0 )
                      goto LABEL_52;
                  }
                  if ( v17 == -1.0 )
                  {
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 95) + 120LL))(
                            *((_QWORD *)this + 95),
                            v35);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, int *))v35->lpVtbl->GetBoundingBox)(
                            v35,
                            0,
                            &v41);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v20 = v35;
                    goto LABEL_23;
                  }
LABEL_33:
                  if ( v16 == -1.0 )
                  {
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, struct IInkStrokeDisp **))v35->lpVtbl->Split)(
                            v35,
                            v18,
                            &v36);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, int *))v36->lpVtbl->GetBoundingBox)(
                            v36,
                            0,
                            &v41);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v20 = v36;
LABEL_23:
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 67) + 112LL))(
                            *((_QWORD *)this + 67),
                            v20);
LABEL_44:
                    SelectedStrokeSizeIncrease = v19;
                    goto LABEL_45;
                  }
                  v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, struct IInkStrokeDisp **))v35->lpVtbl->Split)(
                          v35,
                          v18,
                          &v36);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 )
                    goto LABEL_45;
                  v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, __int64 *))v35->lpVtbl->Split)(
                          v35,
                          v22,
                          &v46);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 )
                    goto LABEL_45;
                  v23 = CInkOverlay::_IsSelected(this, v35);
                  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v46 + 160LL))(v46, 0, &v41);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 )
                    goto LABEL_45;
                  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 67) + 112LL))(
                          *((_QWORD *)this + 67),
                          v46);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 || v23 )
                    goto LABEL_45;
                  goto LABEL_42;
                }
              }
            }
          }
        }
      }
    }
LABEL_52:
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v47);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v35);
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    ++v12;
  }
  while ( v12 < v39[0] );
  if ( SelectedStrokeSizeIncrease >= 0 )
  {
    SelectedStrokeSizeIncrease = CInkOverlay::_UpdateSelectionRect(this, 0);
    goto LABEL_57;
  }
LABEL_84:
  if ( hrgnDst )
    DeleteObject(hrgnDst);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v45);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v49);
  return (unsigned int)SelectedStrokeSizeIncrease;
}

```

## disassembly

```asm
0x1800dfb30  mov     rax, rsp
0x1800dfb33  mov     [rax+20h], rbx
0x1800dfb37  push    rbp
0x1800dfb38  push    rsi
0x1800dfb39  push    rdi
0x1800dfb3a  push    r12
0x1800dfb3c  push    r13
0x1800dfb3e  push    r14
0x1800dfb40  push    r15
0x1800dfb42  lea     rbp, [rax-68h]
0x1800dfb46  sub     rsp, 130h
0x1800dfb4d  movaps  xmmword ptr [rax-48h], xmm6
0x1800dfb51  movaps  xmmword ptr [rax-58h], xmm7
0x1800dfb55  mov     rax, cs:__security_cookie
0x1800dfb5c  xor     rax, rsp
0x1800dfb5f  mov     [rbp+60h+var_60], rax
0x1800dfb63  mov     rsi, rcx
0x1800dfb66  mov     rax, rdx
0x1800dfb69  shr     rax, 20h
0x1800dfb6d  xor     ebx, ebx
0x1800dfb6f  mov     [rsp+160h+ppv], rbx
0x1800dfb74  mov     [rbp+60h+var_D0], rbx
0x1800dfb78  mov     [rsp+160h+var_F0], rbx
0x1800dfb7d  mov     [rsp+160h+var_118], ebx
0x1800dfb81  mov     r14d, edx
0x1800dfb84  sub     r14d, r8d
0x1800dfb87  mov     [rbp+60h+var_90.left], r14d
0x1800dfb8b  mov     r15d, eax
0x1800dfb8e  sub     r15d, r8d
0x1800dfb91  mov     [rbp+60h+var_90.top], r15d
0x1800dfb95  lea     r12d, [r8+rdx]
0x1800dfb99  mov     [rbp+60h+var_90.right], r12d
0x1800dfb9d  lea     r13d, [r8+rax]
0x1800dfba1  mov     [rbp+60h+var_90.bottom], r13d
0x1800dfba5  xor     r9d, r9d; y2
0x1800dfba8  xor     r8d, r8d; x2
0x1800dfbab  xor     edx, edx; y1
0x1800dfbad  xor     ecx, ecx; x1
0x1800dfbaf  call    cs:__imp_CreateRectRgn
0x1800dfbb5  mov     [rbp+60h+hrgnDst], rax
0x1800dfbb9  lea     rcx, [rsp+160h+ppv]
0x1800dfbbe  call    ?CreateInstance@?$CComObject@VCInkRectangle@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkRectangle>::CreateInstance(ATL::CComObject<CInkRectangle> * *)
0x1800dfbc3  mov     edi, eax
0x1800dfbc5  mov     rdx, [rsp+160h+ppv]
0x1800dfbca  test    rdx, rdx
0x1800dfbcd  jnz     short loc_1800DFBE0
0x1800dfbcf  mov     r13d, 8000FFFFh
0x1800dfbd5  mov     edi, r13d
0x1800dfbd8  xor     r12d, r12d
0x1800dfbdb  jmp     loc_1800E01E7
0x1800dfbe0  test    eax, eax
0x1800dfbe2  js      loc_1800E01DE
0x1800dfbe8  add     rdx, 8; struct IUnknown *
0x1800dfbec  lea     rcx, [rbp+60h+var_D0]; struct IUnknown **
0x1800dfbf0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800dfbf5  mov     rbx, [rbp+60h+var_D0]
0x1800dfbf9  mov     rax, [rbx]
0x1800dfbfc  mov     dword ptr [rsp+160h+var_140], r12d
0x1800dfc01  mov     r9d, r13d
0x1800dfc04  mov     r8d, r14d
0x1800dfc07  mov     edx, r15d
0x1800dfc0a  mov     rcx, rbx
0x1800dfc0d  mov     rax, [rax+90h]
0x1800dfc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc19  mov     edi, eax
0x1800dfc1b  xor     r12d, r12d
0x1800dfc1e  test    eax, eax
0x1800dfc20  js      loc_1800E01E1
0x1800dfc26  mov     rcx, [rsi+218h]
0x1800dfc2d  mov     rax, [rcx]
0x1800dfc30  lea     r9, [rsp+160h+var_F0]
0x1800dfc35  xorps   xmm2, xmm2
0x1800dfc38  mov     rdx, rbx
0x1800dfc3b  mov     rax, [rax+0A0h]
0x1800dfc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc47  mov     edi, eax
0x1800dfc49  test    eax, eax
0x1800dfc4b  js      loc_1800E01E1
0x1800dfc51  mov     r8, [rsp+160h+var_F0]; struct IInkStrokes *
0x1800dfc56  mov     edx, [rsi+270h]; unsigned int
0x1800dfc5c  mov     rcx, rsi; this
0x1800dfc5f  call    ?_FilterCurrentStroke@CInkOverlay@@AEAAJKPEAUIInkStrokes@@@Z; CInkOverlay::_FilterCurrentStroke(ulong,IInkStrokes *)
0x1800dfc64  mov     rcx, [rsp+160h+var_F0]
0x1800dfc69  mov     rax, [rcx]
0x1800dfc6c  lea     rdx, [rsp+160h+var_118]
0x1800dfc71  mov     rax, [rax+38h]
0x1800dfc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc7a  mov     edi, eax
0x1800dfc7c  test    eax, eax
0x1800dfc7e  js      loc_1800E01E1
0x1800dfc84  mov     eax, [rsp+160h+var_118]
0x1800dfc88  test    eax, eax
0x1800dfc8a  jle     loc_1800E01E1
0x1800dfc90  mov     r15d, r12d
0x1800dfc93  mov     r13, [rbp+60h+hrgnDst]
0x1800dfc97  xorps   xmm0, xmm0
0x1800dfc9a  xor     eax, eax
0x1800dfc9c  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x1800dfca0  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x1800dfca4  mov     word ptr [rbp+60h+pvarg], r12w
0x1800dfca9  mov     [rsp+160h+var_130], r12
0x1800dfcae  mov     [rbp+60h+var_C8], r12
0x1800dfcb2  mov     [rsp+160h+var_100], r12d
0x1800dfcb7  mov     [rsp+160h+var_FC], r12d
0x1800dfcbc  lea     rdx, [rsp+160h+var_118+4]; int *
0x1800dfcc1  lea     rcx, [rsp+160h+ppv]; ppv
0x1800dfcc6  call    ??0CIRect@@QEAA@AEAJ@Z; CIRect::CIRect(long &)
0x1800dfccb  nop
0x1800dfccc  movaps  xmm0, xmmword ptr [rbp+60h+var_90.left]
0x1800dfcd0  movdqa  xmmword ptr [rbp+60h+var_C0.left], xmm0
0x1800dfcd5  lea     rdx, [rbp+60h+var_C0]; struct tagRECT
0x1800dfcd9  lea     rcx, [rsp+160h+ppv]; this
0x1800dfcde  call    ?SetRect@CIRect@@QEAAXUtagRECT@@@Z; CIRect::SetRect(tagRECT)
0x1800dfce3  mov     rcx, [rsp+160h+var_F0]
0x1800dfce8  mov     rax, [rcx]
0x1800dfceb  lea     r8, [rsp+160h+var_130]
0x1800dfcf0  mov     edx, r15d
0x1800dfcf3  mov     rax, [rax+60h]
0x1800dfcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfcfc  mov     edi, eax
0x1800dfcfe  mov     [rbp+60h+var_E0], r12
0x1800dfd02  test    eax, eax
0x1800dfd04  js      loc_1800E0177
0x1800dfd0a  mov     rcx, [rsp+160h+var_130]
0x1800dfd0f  mov     rax, [rcx]
0x1800dfd12  lea     rdx, [rbp+60h+var_E0]
0x1800dfd16  mov     rax, [rax+48h]
0x1800dfd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfd1f  mov     edi, eax
0x1800dfd21  mov     [rsp+160h+var_11C], r12d
0x1800dfd26  test    eax, eax
0x1800dfd28  js      loc_1800E017C
0x1800dfd2e  mov     rcx, [rbp+60h+var_E0]
0x1800dfd32  mov     rax, [rcx]
0x1800dfd35  lea     rdx, [rsp+160h+var_11C]
0x1800dfd3a  mov     rax, [rax+0B8h]
0x1800dfd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfd46  mov     edi, eax
0x1800dfd48  test    eax, eax
0x1800dfd4a  js      loc_1800E017C
0x1800dfd50  cmp     [rsp+160h+var_11C], r12d
0x1800dfd55  jnz     short loc_1800DFDC0
0x1800dfd57  mov     [rsp+160h+var_118+4], 0
0x1800dfd5f  mov     rcx, [rbp+60h+var_E0]
0x1800dfd63  mov     rax, [rcx]
0x1800dfd66  lea     rdx, [rsp+160h+var_118+4]
0x1800dfd6b  mov     rax, [rax+48h]
0x1800dfd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfd74  mov     edi, eax
0x1800dfd76  movaps  xmm0, xmmword ptr [rbp+60h+var_90.left]
0x1800dfd7a  movdqa  xmmword ptr [rbp+60h+rc.left], xmm0
0x1800dfd7f  movss   xmm1, [rsp+160h+var_118+4]
0x1800dfd85  cvtps2pd xmm1, xmm1
0x1800dfd88  mulsd   xmm1, cs:__real@3fe0000000000000
0x1800dfd90  cvttsd2si edx, xmm1; dx
0x1800dfd94  mov     r8d, edx; dy
0x1800dfd97  lea     rcx, [rbp+60h+rc]; lprc
0x1800dfd9b  call    cs:__imp_InflateRect
0x1800dfda1  movaps  xmm0, xmmword ptr [rbp+60h+rc.left]
0x1800dfda5  movdqa  xmmword ptr [rbp+60h+var_C0.left], xmm0
0x1800dfdaa  lea     rdx, [rbp+60h+var_C0]; struct tagRECT
0x1800dfdae  lea     rcx, [rsp+160h+ppv]; this
0x1800dfdb3  call    ?SetRect@CIRect@@QEAAXUtagRECT@@@Z; CIRect::SetRect(tagRECT)
0x1800dfdb8  test    edi, edi
0x1800dfdba  js      loc_1800E017C
0x1800dfdc0  mov     rcx, [rsp+160h+var_130]
0x1800dfdc5  mov     rax, [rcx]
0x1800dfdc8  lea     r8, [rbp+60h+pvarg]
0x1800dfdcc  mov     rdx, [rsp+160h+ppv]
0x1800dfdd1  mov     rax, [rax+0B0h]
0x1800dfdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfddd  mov     edi, eax
0x1800dfddf  test    eax, eax
0x1800dfde1  js      loc_1800E017C
0x1800dfde7  mov     [rsp+160h+var_138], r12; unsigned __int16 *
0x1800dfdec  lea     rax, [rsp+160h+var_120]
0x1800dfdf1  mov     [rsp+160h+var_140], rax; bool *
0x1800dfdf6  lea     r9, [rsp+160h+var_FC]; unsigned int *
0x1800dfdfb  lea     r8, [rsp+160h+var_100]; unsigned int *
0x1800dfe00  lea     rdx, [rbp+60h+var_C8]; unsigned __int8 **
0x1800dfe04  lea     rcx, [rbp+60h+pvarg]; struct tagVARIANT *
0x1800dfe08  call    ?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z; AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)
0x1800dfe0d  mov     edi, eax
0x1800dfe0f  test    eax, eax
0x1800dfe11  js      loc_1800E017C
0x1800dfe17  xor     edx, edx
0x1800dfe19  mov     eax, [rsp+160h+var_100]
0x1800dfe1d  div     [rsp+160h+var_FC]
0x1800dfe21  lea     r14d, [rax-1]
0x1800dfe25  test    r14d, r14d
0x1800dfe28  jle     loc_1800E017C
0x1800dfe2e  mov     r12, [rbp+60h+var_C8]
0x1800dfe32  movsxd  rcx, r14d
0x1800dfe35  movss   xmm7, dword ptr [r12+rcx*4]
0x1800dfe3b  movss   xmm6, dword ptr [r12+rcx*4-4]
0x1800dfe42  mov     [rsp+160h+var_128], 0
0x1800dfe4b  mov     [rsp+160h+var_E8], 0
0x1800dfe54  xor     edx, edx; struct IInkRectangle *
0x1800dfe56  lea     rcx, [rsp+160h+var_108]; this
0x1800dfe5b  call    ??0CIRect@@QEAA@PEAUIInkRectangle@@@Z; CIRect::CIRect(IInkRectangle *)
0x1800dfe60  nop
0x1800dfe61  ucomiss xmm7, cs:__real@bf800000
0x1800dfe68  jp      short loc_1800DFEE3
0x1800dfe6a  jnz     short loc_1800DFEE3
0x1800dfe6c  ucomiss xmm6, cs:__real@bf800000
0x1800dfe73  jp      loc_1800DFFB3
0x1800dfe79  jnz     loc_1800DFFB3
0x1800dfe7f  mov     rcx, [rsi+2F8h]
0x1800dfe86  mov     rax, [rcx]
0x1800dfe89  mov     rdx, [rsp+160h+var_130]
0x1800dfe8e  mov     rax, [rax+78h]
0x1800dfe92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe97  mov     edi, eax
0x1800dfe99  test    eax, eax
0x1800dfe9b  js      loc_1800E00E3
0x1800dfea1  mov     rcx, [rsp+160h+var_130]
0x1800dfea6  mov     rax, [rcx]
0x1800dfea9  lea     r8, [rsp+160h+var_108]
0x1800dfeae  xor     edx, edx
0x1800dfeb0  mov     rax, [rax+0A0h]
0x1800dfeb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfebc  mov     edi, eax
0x1800dfebe  test    eax, eax
0x1800dfec0  js      loc_1800E00E3
0x1800dfec6  mov     rdx, [rsp+160h+var_130]
0x1800dfecb  mov     rcx, [rsi+218h]
0x1800dfed2  mov     rax, [rcx]
0x1800dfed5  mov     rax, [rax+70h]
0x1800dfed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfede  jmp     loc_1800E00E1
0x1800dfee3  ucomiss xmm6, cs:__real@bf800000
0x1800dfeea  jp      loc_1800DFFB3
0x1800dfef0  jnz     loc_1800DFFB3
0x1800dfef6  mov     rcx, [rsp+160h+var_130]
0x1800dfefb  mov     rax, [rcx]
0x1800dfefe  lea     r8, [rsp+160h+var_128]
0x1800dff03  movaps  xmm1, xmm7
0x1800dff06  mov     rax, [rax+0D0h]
0x1800dff0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff12  mov     edi, eax
0x1800dff14  test    eax, eax
0x1800dff16  js      loc_1800E00E3
0x1800dff1c  mov     rdx, [rsp+160h+var_130]; struct IInkStrokeDisp *
0x1800dff21  mov     rcx, rsi; this
0x1800dff24  call    ?_IsSelected@CInkOverlay@@AEAAJPEAUIInkStrokeDisp@@@Z; CInkOverlay::_IsSelected(IInkStrokeDisp *)
0x1800dff29  mov     ebx, eax
0x1800dff2b  test    eax, eax
0x1800dff2d  jnz     short loc_1800DFF54
0x1800dff2f  mov     r8, [rsi+2F8h]
0x1800dff36  mov     rcx, [r8]
0x1800dff39  mov     rax, [rcx+78h]
0x1800dff3d  mov     rdx, [rsp+160h+var_130]
0x1800dff42  mov     rcx, r8
0x1800dff45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff4a  mov     edi, eax
0x1800dff4c  test    eax, eax
0x1800dff4e  js      loc_1800E00E3
0x1800dff54  mov     rcx, [rsp+160h+var_130]
0x1800dff59  mov     rax, [rcx]
0x1800dff5c  lea     r8, [rsp+160h+var_108]
0x1800dff61  xor     edx, edx
0x1800dff63  mov     rax, [rax+0A0h]
0x1800dff6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff6f  mov     edi, eax
0x1800dff71  test    eax, eax
0x1800dff73  js      loc_1800E00E3
0x1800dff79  mov     rcx, [rsi+218h]
0x1800dff80  mov     rax, [rcx]
0x1800dff83  mov     rdx, [rsp+160h+var_130]
0x1800dff88  mov     rax, [rax+70h]
0x1800dff8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff91  mov     edi, eax
0x1800dff93  test    eax, eax
0x1800dff95  js      loc_1800E00E3
0x1800dff9b  test    ebx, ebx
0x1800dff9d  jz      loc_1800E00B4
0x1800dffa3  cmp     ebx, 1
0x1800dffa6  jz      loc_1800E00E3
0x1800dffac  mov     edi, ebx
0x1800dffae  jmp     loc_1800E00E5
0x1800dffb3  ucomiss xmm7, cs:__real@bf800000
0x1800dffba  jp      short loc_1800E0013
0x1800dffbc  jnz     short loc_1800E0013
0x1800dffbe  mov     rcx, [rsp+160h+var_130]
0x1800dffc3  mov     rax, [rcx]
0x1800dffc6  lea     r8, [rsp+160h+var_128]
0x1800dffcb  movaps  xmm1, xmm6
0x1800dffce  mov     rax, [rax+0D0h]
0x1800dffd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dffda  mov     edi, eax
0x1800dffdc  test    eax, eax
0x1800dffde  js      loc_1800E00E3
0x1800dffe4  mov     rcx, [rsp+160h+var_128]
0x1800dffe9  mov     rax, [rcx]
0x1800dffec  lea     r8, [rsp+160h+var_108]
0x1800dfff1  xor     edx, edx
0x1800dfff3  mov     rax, [rax+0A0h]
0x1800dfffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dffff  mov     edi, eax
0x1800e0001  test    eax, eax
  ... truncated ...
```
