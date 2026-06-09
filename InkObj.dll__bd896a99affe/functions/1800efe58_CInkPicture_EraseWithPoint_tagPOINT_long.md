# CInkPicture::_EraseWithPoint(tagPOINT,long)

- ea: `0x1800efe58`
- end: `0x1800f06e5`
- name: `?_EraseWithPoint@CInkPicture@@AEAAJUtagPOINT@@J@Z`
- size: `2189`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, struct tagPOINT, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800f1928`

## callees

- `0x180001c20`
- `0x18000a730`
- `0x1800217b0`
- `0x18002a3ac`
- `0x1800365f8`
- `0x180036824`
- `0x180036888`
- `0x1800a991c`
- `0x1800acf04`
- `0x1800d7eb4`
- `0x1800efe58`
- `0x1800f06ec`
- `0x1800f0d1c`
- `0x1800f1088`
- `0x1800f11e4`
- `0x1800f1870`
- `0x1800f2e2c`
- `0x1800f38a0`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f05b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f05ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f05b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f05ee`
- `USER32!InflateRect` at `0x1800f00c3`
- `USER32!InflateRect` at `0x1800f0454`
- `USER32!InflateRect` at `0x1800f00c3`
- `USER32!InflateRect` at `0x1800f0454`
- `GDI32!CombineRgn` at `0x1800f0574`
- `GDI32!CombineRgn` at `0x1800f0630`
- `GDI32!CombineRgn` at `0x1800f0659`
- `GDI32!CombineRgn` at `0x1800f0574`
- `GDI32!CombineRgn` at `0x1800f0630`
- `GDI32!CombineRgn` at `0x1800f0659`
- `GDI32!CreateRectRgn` at `0x1800efed7`
- `GDI32!CreateRectRgn` at `0x1800f0532`
- `GDI32!CreateRectRgn` at `0x1800f05a1`
- `GDI32!CreateRectRgn` at `0x1800f05dc`
- `GDI32!CreateRectRgn` at `0x1800efed7`
- `GDI32!CreateRectRgn` at `0x1800f0532`
- `GDI32!CreateRectRgn` at `0x1800f05a1`
- `GDI32!CreateRectRgn` at `0x1800f05dc`
- `GDI32!DeleteObject` at `0x1800f060c`
- `GDI32!DeleteObject` at `0x1800f067b`
- `GDI32!DeleteObject` at `0x1800f0697`
- `GDI32!DeleteObject` at `0x1800f060c`
- `GDI32!DeleteObject` at `0x1800f067b`
- `GDI32!DeleteObject` at `0x1800f0697`
- `OLEAUT32!__imp_VariantClear` at `0x1800f04dc`
- `OLEAUT32!__imp_VariantClear` at `0x1800f04dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CInkPicture::_EraseWithPoint(CInkPicture *this, struct tagPOINT a2, int a3)
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
  int v35; // [rsp+28h] [rbp-E0h]
  struct IInkStrokeDisp *v36; // [rsp+38h] [rbp-D0h] BYREF
  struct IInkStrokeDisp *v37; // [rsp+40h] [rbp-C8h] BYREF
  bool v38[4]; // [rsp+48h] [rbp-C0h] BYREF
  int v39; // [rsp+4Ch] [rbp-BCh] BYREF
  int v40[2]; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  int v42; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v43; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+6Ch] [rbp-9Ch] BYREF
  int dy[2]; // [rsp+70h] [rbp-98h] BYREF
  struct IInkStrokes *v46; // [rsp+78h] [rbp-90h] BYREF
  __int64 v47; // [rsp+80h] [rbp-88h] BYREF
  __int64 v48; // [rsp+88h] [rbp-80h] BYREF
  HRGN hrgnDst; // [rsp+90h] [rbp-78h]
  struct IUnknown *v50; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int8 *v51; // [rsp+A0h] [rbp-68h] BYREF
  struct tagRECT v52; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  struct tagRECT v54; // [rsp+D8h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+E8h] [rbp-20h] BYREF
  struct tagRECT v56; // [rsp+F8h] [rbp-10h] BYREF

  ppv = 0;
  v50 = 0;
  v46 = 0;
  v40[0] = 0;
  v4 = a2.x - a3;
  v54.left = a2.x - a3;
  v5 = a2.y - a3;
  v54.top = a2.y - a3;
  v6 = a3 + a2.x;
  v54.right = a3 + a2.x;
  v7 = a3 + a2.y;
  v54.bottom = a3 + a2.y;
  hrgnDst = CreateRectRgn(0, 0, 0, 0);
  v8 = ATL::CComObject<CInkRectangle>::CreateInstance(&ppv);
  SelectedStrokeSizeIncrease = v8;
  if ( !ppv )
  {
    SelectedStrokeSizeIncrease = -2147418113;
LABEL_57:
    if ( SelectedStrokeSizeIncrease >= 0 )
    {
      CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&v52, (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v26 = RectRgn;
      if ( RectRgn )
        SelectedStrokeSizeIncrease = CInkPicture::_PlaceInkSpaceRectIntoRegion(this, &v54, RectRgn, 0);
      if ( *((_BYTE *)this + 488) )
      {
        v27 = hrgnDst;
        if ( !CombineRgn(hrgnDst, hrgnDst, v26, 2) )
          SelectedStrokeSizeIncrease = -2147418113;
        if ( SelectedStrokeSizeIncrease >= 0 )
        {
          if ( !*((_QWORD *)this + 167) )
          {
            v28 = CreateRectRgn(0, 0, 0, 0);
            *((_QWORD *)this + 167) = v28;
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
            if ( !*((_QWORD *)this + 168) )
            {
              v30 = CreateRectRgn(0, 0, 0, 0);
              *((_QWORD *)this + 168) = v30;
              if ( !v30 )
              {
                v31 = GetLastError();
                SelectedStrokeSizeIncrease = v31;
                if ( v31 > 0 )
                  SelectedStrokeSizeIncrease = (unsigned __int16)v31 | 0x80070000;
                v32 = (void *)*((_QWORD *)this + 167);
                if ( v32 )
                {
                  DeleteObject(v32);
                  *((_QWORD *)this + 167) = 0;
                }
              }
            }
            if ( SelectedStrokeSizeIncrease >= 0 && !CombineRgn(*((HRGN *)this + 167), *((HRGN *)this + 167), v27, 2) )
              SelectedStrokeSizeIncrease = -2147418113;
          }
        }
        if ( v26 )
        {
          v33 = (HRGN)*((_QWORD *)this + 168);
          if ( v33 && !CombineRgn(v33, *((HRGN *)this + 168), v26, 2) )
            SelectedStrokeSizeIncrease = -2147418113;
          CInkPicture::_InvalidateWindow(this, 0, v26, 1, v35);
          DeleteObject(v26);
        }
      }
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&v52);
    }
    goto LABEL_84;
  }
  if ( v8 < 0 )
    goto LABEL_57;
  ATL::AtlComPtrAssign(&v50, (struct IUnknown *)ppv + 1);
  v10 = v50;
  v35 = v6;
  SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))v50->lpVtbl[6].QueryInterface)(
                                 v50,
                                 v5,
                                 v4,
                                 v7);
  if ( SelectedStrokeSizeIncrease < 0 )
    goto LABEL_57;
  SelectedStrokeSizeIncrease = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, __int64, struct IInkStrokes **))(**((_QWORD **)this + 95) + 160LL))(
                                 *((_QWORD *)this + 95),
                                 v10,
                                 v11,
                                 &v46);
  if ( SelectedStrokeSizeIncrease < 0 )
    goto LABEL_57;
  CInkPicture::_FilterCurrentStroke(this, *((_DWORD *)this + 212), v46);
  SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokes *, int *))v46->lpVtbl->get_Count)(v46, v40);
  if ( SelectedStrokeSizeIncrease < 0 || v40[0] <= 0 )
    goto LABEL_57;
  v12 = 0;
  v13 = hrgnDst;
  do
  {
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    v36 = 0;
    v51 = 0;
    v43 = 0;
    v44 = 0;
    CIRect::CIRect(&ppv, &v40[1]);
    v52 = v54;
    CIRect::SetRect((CIRect *)&ppv, &v52);
    SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokes *, _QWORD, struct IInkStrokeDisp **))v46->lpVtbl->Item)(
                                   v46,
                                   (unsigned int)v12,
                                   &v36);
    v48 = 0;
    if ( SelectedStrokeSizeIncrease < 0 )
    {
      v39 = 0;
    }
    else
    {
      SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64 *))v36->lpVtbl->get_DrawingAttributes)(
                                     v36,
                                     &v48);
      v39 = 0;
      if ( SelectedStrokeSizeIncrease >= 0 )
      {
        SelectedStrokeSizeIncrease = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 184LL))(v48, &v39);
        if ( SelectedStrokeSizeIncrease >= 0 )
        {
          if ( v39
            || (v40[1] = 0,
                SelectedStrokeSizeIncrease = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 72LL))(
                                               v48,
                                               &v40[1]),
                rc = v54,
                InflateRect(&rc, (int)(*(float *)&v40[1] * 0.5), (int)(*(float *)&v40[1] * 0.5)),
                v52 = rc,
                CIRect::SetRect((CIRect *)&ppv, &v52),
                SelectedStrokeSizeIncrease >= 0) )
          {
            SelectedStrokeSizeIncrease = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, LPVOID, VARIANTARG *))v36->lpVtbl->GetRectangleIntersections)(
                                           v36,
                                           ppv,
                                           &pvarg);
            if ( SelectedStrokeSizeIncrease >= 0 )
            {
              SelectedStrokeSizeIncrease = AccessVariantData(&pvarg, &v51, &v43, &v44, v38, 0);
              if ( SelectedStrokeSizeIncrease >= 0 )
              {
                v14 = v43 / v44 - 1;
                if ( v14 > 0 )
                {
                  v15 = v51;
                  while ( 1 )
                  {
                    v16 = *(float *)&v15[4 * v14];
                    v17 = *(float *)&v15[4 * v14 - 4];
                    v37 = 0;
                    v47 = 0;
                    CIRect::CIRect((CIRect *)&v42, 0);
                    if ( v16 == -1.0 )
                      break;
                    if ( v17 != -1.0 )
                      goto LABEL_33;
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, struct IInkStrokeDisp **))v36->lpVtbl->Split)(
                            v36,
                            v18,
                            &v37);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    IsSelected = CInkPicture::_IsSelected(this, v36);
                    if ( !IsSelected )
                    {
                      v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 123)
                                                                                       + 120LL))(
                              *((_QWORD *)this + 123),
                              v36);
                      SelectedStrokeSizeIncrease = v19;
                      if ( v19 < 0 )
                        goto LABEL_45;
                    }
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, int *))v36->lpVtbl->GetBoundingBox)(
                            v36,
                            0,
                            &v42);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 95) + 112LL))(
                            *((_QWORD *)this + 95),
                            v36);
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
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 123) + 104LL))(
                            *((_QWORD *)this + 123),
                            v37);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 >= 0 )
                    {
                      v19 = CInkPicture::_SetSelection(this, *((struct IInkStrokes **)this + 123));
                      goto LABEL_44;
                    }
LABEL_45:
                    IsSelected = v19;
LABEL_46:
                    CIRect::GetRect((CIRect *)&v42, &v56);
                    dy[1] = 0;
                    dy[0] = 0;
                    if ( IsSelected >= 0 )
                    {
                      SelectedStrokeSizeIncrease = CInkPicture::_GetSelectedStrokeSizeIncrease(this, &dy[1], dy, v24);
                      if ( SelectedStrokeSizeIncrease >= 0 )
                      {
                        InflateRect(&v56, dy[1], dy[0]);
                        CInkPicture::_PlaceInkSpaceRectIntoRegion(this, &v56, v13, 1);
                      }
                    }
                    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v42);
                    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v47);
                    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v37);
                    v14 -= 2;
                    if ( v14 <= 0 )
                      goto LABEL_52;
                  }
                  if ( v17 == -1.0 )
                  {
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 123) + 120LL))(
                            *((_QWORD *)this + 123),
                            v36);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, int *))v36->lpVtbl->GetBoundingBox)(
                            v36,
                            0,
                            &v42);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v20 = v36;
                    goto LABEL_23;
                  }
LABEL_33:
                  if ( v16 == -1.0 )
                  {
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, struct IInkStrokeDisp **))v36->lpVtbl->Split)(
                            v36,
                            v18,
                            &v37);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, _QWORD, int *))v37->lpVtbl->GetBoundingBox)(
                            v37,
                            0,
                            &v42);
                    SelectedStrokeSizeIncrease = v19;
                    if ( v19 < 0 )
                      goto LABEL_45;
                    v20 = v37;
LABEL_23:
                    v19 = (*(__int64 (__fastcall **)(_QWORD, struct IInkStrokeDisp *))(**((_QWORD **)this + 95) + 112LL))(
                            *((_QWORD *)this + 95),
                            v20);
LABEL_44:
                    SelectedStrokeSizeIncrease = v19;
                    goto LABEL_45;
                  }
                  v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, struct IInkStrokeDisp **))v36->lpVtbl->Split)(
                          v36,
                          v18,
                          &v37);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 )
                    goto LABEL_45;
                  v19 = ((__int64 (__fastcall *)(struct IInkStrokeDisp *, __int64, __int64 *))v36->lpVtbl->Split)(
                          v36,
                          v22,
                          &v47);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 )
                    goto LABEL_45;
                  v23 = CInkPicture::_IsSelected(this, v36);
                  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v47 + 160LL))(v47, 0, &v42);
                  SelectedStrokeSizeIncrease = v19;
                  if ( v19 < 0 )
                    goto LABEL_45;
                  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 95) + 112LL))(
                          *((_QWORD *)this + 95),
                          v47);
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
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v48);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v36);
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    ++v12;
  }
  while ( v12 < v40[0] );
  if ( SelectedStrokeSizeIncrease >= 0 )
  {
    SelectedStrokeSizeIncrease = CInkPicture::_UpdateSelectionRect(this, 0);
    goto LABEL_57;
  }
LABEL_84:
  if ( hrgnDst )
    DeleteObject(hrgnDst);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v46);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v50);
  return (unsigned int)SelectedStrokeSizeIncrease;
}

```

## disassembly

```asm
0x1800efe58  mov     rax, rsp
0x1800efe5b  mov     [rax+20h], rbx
0x1800efe5f  push    rbp
0x1800efe60  push    rsi
0x1800efe61  push    rdi
0x1800efe62  push    r12
0x1800efe64  push    r13
0x1800efe66  push    r14
0x1800efe68  push    r15
0x1800efe6a  lea     rbp, [rax-68h]
0x1800efe6e  sub     rsp, 130h
0x1800efe75  movaps  xmmword ptr [rax-48h], xmm6
0x1800efe79  movaps  xmmword ptr [rax-58h], xmm7
0x1800efe7d  mov     rax, cs:__security_cookie
0x1800efe84  xor     rax, rsp
0x1800efe87  mov     [rbp+60h+var_60], rax
0x1800efe8b  mov     rsi, rcx
0x1800efe8e  mov     rax, rdx
0x1800efe91  shr     rax, 20h
0x1800efe95  xor     ebx, ebx
0x1800efe97  mov     [rsp+160h+ppv], rbx
0x1800efe9c  mov     [rbp+60h+var_D0], rbx
0x1800efea0  mov     [rsp+160h+var_F0], rbx
0x1800efea5  mov     [rsp+160h+var_118], ebx
0x1800efea9  mov     r14d, edx
0x1800efeac  sub     r14d, r8d
0x1800efeaf  mov     [rbp+60h+var_90.left], r14d
0x1800efeb3  mov     r15d, eax
0x1800efeb6  sub     r15d, r8d
0x1800efeb9  mov     [rbp+60h+var_90.top], r15d
0x1800efebd  lea     r12d, [r8+rdx]
0x1800efec1  mov     [rbp+60h+var_90.right], r12d
0x1800efec5  lea     r13d, [r8+rax]
0x1800efec9  mov     [rbp+60h+var_90.bottom], r13d
0x1800efecd  xor     r9d, r9d; y2
0x1800efed0  xor     r8d, r8d; x2
0x1800efed3  xor     edx, edx; y1
0x1800efed5  xor     ecx, ecx; x1
0x1800efed7  call    cs:__imp_CreateRectRgn
0x1800efedd  mov     [rbp+60h+hrgnDst], rax
0x1800efee1  lea     rcx, [rsp+160h+ppv]
0x1800efee6  call    ?CreateInstance@?$CComObject@VCInkRectangle@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkRectangle>::CreateInstance(ATL::CComObject<CInkRectangle> * *)
0x1800efeeb  mov     edi, eax
0x1800efeed  mov     rdx, [rsp+160h+ppv]
0x1800efef2  test    rdx, rdx
0x1800efef5  jnz     short loc_1800EFF08
0x1800efef7  mov     r13d, 8000FFFFh
0x1800efefd  mov     edi, r13d
0x1800eff00  xor     r12d, r12d
0x1800eff03  jmp     loc_1800F050F
0x1800eff08  test    eax, eax
0x1800eff0a  js      loc_1800F0506
0x1800eff10  add     rdx, 8; struct IUnknown *
0x1800eff14  lea     rcx, [rbp+60h+var_D0]; struct IUnknown **
0x1800eff18  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800eff1d  mov     rbx, [rbp+60h+var_D0]
0x1800eff21  mov     rax, [rbx]
0x1800eff24  mov     dword ptr [rsp+160h+var_140], r12d
0x1800eff29  mov     r9d, r13d
0x1800eff2c  mov     r8d, r14d
0x1800eff2f  mov     edx, r15d
0x1800eff32  mov     rcx, rbx
0x1800eff35  mov     rax, [rax+90h]
0x1800eff3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff41  mov     edi, eax
0x1800eff43  xor     r12d, r12d
0x1800eff46  test    eax, eax
0x1800eff48  js      loc_1800F0509
0x1800eff4e  mov     rcx, [rsi+2F8h]
0x1800eff55  mov     rax, [rcx]
0x1800eff58  lea     r9, [rsp+160h+var_F0]
0x1800eff5d  xorps   xmm2, xmm2
0x1800eff60  mov     rdx, rbx
0x1800eff63  mov     rax, [rax+0A0h]
0x1800eff6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff6f  mov     edi, eax
0x1800eff71  test    eax, eax
0x1800eff73  js      loc_1800F0509
0x1800eff79  mov     r8, [rsp+160h+var_F0]; struct IInkStrokes *
0x1800eff7e  mov     edx, [rsi+350h]; unsigned int
0x1800eff84  mov     rcx, rsi; this
0x1800eff87  call    ?_FilterCurrentStroke@CInkPicture@@AEAAJKPEAUIInkStrokes@@@Z; CInkPicture::_FilterCurrentStroke(ulong,IInkStrokes *)
0x1800eff8c  mov     rcx, [rsp+160h+var_F0]
0x1800eff91  mov     rax, [rcx]
0x1800eff94  lea     rdx, [rsp+160h+var_118]
0x1800eff99  mov     rax, [rax+38h]
0x1800eff9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800effa2  mov     edi, eax
0x1800effa4  test    eax, eax
0x1800effa6  js      loc_1800F0509
0x1800effac  mov     eax, [rsp+160h+var_118]
0x1800effb0  test    eax, eax
0x1800effb2  jle     loc_1800F0509
0x1800effb8  mov     r15d, r12d
0x1800effbb  mov     r13, [rbp+60h+hrgnDst]
0x1800effbf  xorps   xmm0, xmm0
0x1800effc2  xor     eax, eax
0x1800effc4  movups  xmmword ptr [rbp+60h+pvarg], xmm0
0x1800effc8  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x1800effcc  mov     word ptr [rbp+60h+pvarg], r12w
0x1800effd1  mov     [rsp+160h+var_130], r12
0x1800effd6  mov     [rbp+60h+var_C8], r12
0x1800effda  mov     [rsp+160h+var_100], r12d
0x1800effdf  mov     [rsp+160h+var_FC], r12d
0x1800effe4  lea     rdx, [rsp+160h+var_118+4]; int *
0x1800effe9  lea     rcx, [rsp+160h+ppv]; ppv
0x1800effee  call    ??0CIRect@@QEAA@AEAJ@Z; CIRect::CIRect(long &)
0x1800efff3  nop
0x1800efff4  movaps  xmm0, xmmword ptr [rbp+60h+var_90.left]
0x1800efff8  movdqa  xmmword ptr [rbp+60h+var_C0.left], xmm0
0x1800efffd  lea     rdx, [rbp+60h+var_C0]; struct tagRECT
0x1800f0001  lea     rcx, [rsp+160h+ppv]; this
0x1800f0006  call    ?SetRect@CIRect@@QEAAXUtagRECT@@@Z; CIRect::SetRect(tagRECT)
0x1800f000b  mov     rcx, [rsp+160h+var_F0]
0x1800f0010  mov     rax, [rcx]
0x1800f0013  lea     r8, [rsp+160h+var_130]
0x1800f0018  mov     edx, r15d
0x1800f001b  mov     rax, [rax+60h]
0x1800f001f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0024  mov     edi, eax
0x1800f0026  mov     [rbp+60h+var_E0], r12
0x1800f002a  test    eax, eax
0x1800f002c  js      loc_1800F049F
0x1800f0032  mov     rcx, [rsp+160h+var_130]
0x1800f0037  mov     rax, [rcx]
0x1800f003a  lea     rdx, [rbp+60h+var_E0]
0x1800f003e  mov     rax, [rax+48h]
0x1800f0042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0047  mov     edi, eax
0x1800f0049  mov     [rsp+160h+var_11C], r12d
0x1800f004e  test    eax, eax
0x1800f0050  js      loc_1800F04A4
0x1800f0056  mov     rcx, [rbp+60h+var_E0]
0x1800f005a  mov     rax, [rcx]
0x1800f005d  lea     rdx, [rsp+160h+var_11C]
0x1800f0062  mov     rax, [rax+0B8h]
0x1800f0069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f006e  mov     edi, eax
0x1800f0070  test    eax, eax
0x1800f0072  js      loc_1800F04A4
0x1800f0078  cmp     [rsp+160h+var_11C], r12d
0x1800f007d  jnz     short loc_1800F00E8
0x1800f007f  mov     [rsp+160h+var_118+4], 0
0x1800f0087  mov     rcx, [rbp+60h+var_E0]
0x1800f008b  mov     rax, [rcx]
0x1800f008e  lea     rdx, [rsp+160h+var_118+4]
0x1800f0093  mov     rax, [rax+48h]
0x1800f0097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f009c  mov     edi, eax
0x1800f009e  movaps  xmm0, xmmword ptr [rbp+60h+var_90.left]
0x1800f00a2  movdqa  xmmword ptr [rbp+60h+rc.left], xmm0
0x1800f00a7  movss   xmm1, [rsp+160h+var_118+4]
0x1800f00ad  cvtps2pd xmm1, xmm1
0x1800f00b0  mulsd   xmm1, cs:__real@3fe0000000000000
0x1800f00b8  cvttsd2si edx, xmm1; dx
0x1800f00bc  mov     r8d, edx; dy
0x1800f00bf  lea     rcx, [rbp+60h+rc]; lprc
0x1800f00c3  call    cs:__imp_InflateRect
0x1800f00c9  movaps  xmm0, xmmword ptr [rbp+60h+rc.left]
0x1800f00cd  movdqa  xmmword ptr [rbp+60h+var_C0.left], xmm0
0x1800f00d2  lea     rdx, [rbp+60h+var_C0]; struct tagRECT
0x1800f00d6  lea     rcx, [rsp+160h+ppv]; this
0x1800f00db  call    ?SetRect@CIRect@@QEAAXUtagRECT@@@Z; CIRect::SetRect(tagRECT)
0x1800f00e0  test    edi, edi
0x1800f00e2  js      loc_1800F04A4
0x1800f00e8  mov     rcx, [rsp+160h+var_130]
0x1800f00ed  mov     rax, [rcx]
0x1800f00f0  lea     r8, [rbp+60h+pvarg]
0x1800f00f4  mov     rdx, [rsp+160h+ppv]
0x1800f00f9  mov     rax, [rax+0B0h]
0x1800f0100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0105  mov     edi, eax
0x1800f0107  test    eax, eax
0x1800f0109  js      loc_1800F04A4
0x1800f010f  mov     [rsp+160h+var_138], r12; unsigned __int16 *
0x1800f0114  lea     rax, [rsp+160h+var_120]
0x1800f0119  mov     [rsp+160h+var_140], rax; bool *
0x1800f011e  lea     r9, [rsp+160h+var_FC]; unsigned int *
0x1800f0123  lea     r8, [rsp+160h+var_100]; unsigned int *
0x1800f0128  lea     rdx, [rbp+60h+var_C8]; unsigned __int8 **
0x1800f012c  lea     rcx, [rbp+60h+pvarg]; struct tagVARIANT *
0x1800f0130  call    ?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z; AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)
0x1800f0135  mov     edi, eax
0x1800f0137  test    eax, eax
0x1800f0139  js      loc_1800F04A4
0x1800f013f  xor     edx, edx
0x1800f0141  mov     eax, [rsp+160h+var_100]
0x1800f0145  div     [rsp+160h+var_FC]
0x1800f0149  lea     r14d, [rax-1]
0x1800f014d  test    r14d, r14d
0x1800f0150  jle     loc_1800F04A4
0x1800f0156  mov     r12, [rbp+60h+var_C8]
0x1800f015a  movsxd  rcx, r14d
0x1800f015d  movss   xmm7, dword ptr [r12+rcx*4]
0x1800f0163  movss   xmm6, dword ptr [r12+rcx*4-4]
0x1800f016a  mov     [rsp+160h+var_128], 0
0x1800f0173  mov     [rsp+160h+var_E8], 0
0x1800f017c  xor     edx, edx; struct IInkRectangle *
0x1800f017e  lea     rcx, [rsp+160h+var_108]; this
0x1800f0183  call    ??0CIRect@@QEAA@PEAUIInkRectangle@@@Z; CIRect::CIRect(IInkRectangle *)
0x1800f0188  nop
0x1800f0189  ucomiss xmm7, cs:__real@bf800000
0x1800f0190  jp      short loc_1800F020B
0x1800f0192  jnz     short loc_1800F020B
0x1800f0194  ucomiss xmm6, cs:__real@bf800000
0x1800f019b  jp      loc_1800F02DB
0x1800f01a1  jnz     loc_1800F02DB
0x1800f01a7  mov     rcx, [rsi+3D8h]
0x1800f01ae  mov     rax, [rcx]
0x1800f01b1  mov     rdx, [rsp+160h+var_130]
0x1800f01b6  mov     rax, [rax+78h]
0x1800f01ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f01bf  mov     edi, eax
0x1800f01c1  test    eax, eax
0x1800f01c3  js      loc_1800F040B
0x1800f01c9  mov     rcx, [rsp+160h+var_130]
0x1800f01ce  mov     rax, [rcx]
0x1800f01d1  lea     r8, [rsp+160h+var_108]
0x1800f01d6  xor     edx, edx
0x1800f01d8  mov     rax, [rax+0A0h]
0x1800f01df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f01e4  mov     edi, eax
0x1800f01e6  test    eax, eax
0x1800f01e8  js      loc_1800F040B
0x1800f01ee  mov     rdx, [rsp+160h+var_130]
0x1800f01f3  mov     rcx, [rsi+2F8h]
0x1800f01fa  mov     rax, [rcx]
0x1800f01fd  mov     rax, [rax+70h]
0x1800f0201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0206  jmp     loc_1800F0409
0x1800f020b  ucomiss xmm6, cs:__real@bf800000
0x1800f0212  jp      loc_1800F02DB
0x1800f0218  jnz     loc_1800F02DB
0x1800f021e  mov     rcx, [rsp+160h+var_130]
0x1800f0223  mov     rax, [rcx]
0x1800f0226  lea     r8, [rsp+160h+var_128]
0x1800f022b  movaps  xmm1, xmm7
0x1800f022e  mov     rax, [rax+0D0h]
0x1800f0235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f023a  mov     edi, eax
0x1800f023c  test    eax, eax
0x1800f023e  js      loc_1800F040B
0x1800f0244  mov     rdx, [rsp+160h+var_130]; struct IInkStrokeDisp *
0x1800f0249  mov     rcx, rsi; this
0x1800f024c  call    ?_IsSelected@CInkPicture@@AEAAJPEAUIInkStrokeDisp@@@Z; CInkPicture::_IsSelected(IInkStrokeDisp *)
0x1800f0251  mov     ebx, eax
0x1800f0253  test    eax, eax
0x1800f0255  jnz     short loc_1800F027C
0x1800f0257  mov     r8, [rsi+3D8h]
0x1800f025e  mov     rcx, [r8]
0x1800f0261  mov     rax, [rcx+78h]
0x1800f0265  mov     rdx, [rsp+160h+var_130]
0x1800f026a  mov     rcx, r8
0x1800f026d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0272  mov     edi, eax
0x1800f0274  test    eax, eax
0x1800f0276  js      loc_1800F040B
0x1800f027c  mov     rcx, [rsp+160h+var_130]
0x1800f0281  mov     rax, [rcx]
0x1800f0284  lea     r8, [rsp+160h+var_108]
0x1800f0289  xor     edx, edx
0x1800f028b  mov     rax, [rax+0A0h]
0x1800f0292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0297  mov     edi, eax
0x1800f0299  test    eax, eax
0x1800f029b  js      loc_1800F040B
0x1800f02a1  mov     rcx, [rsi+2F8h]
0x1800f02a8  mov     rax, [rcx]
0x1800f02ab  mov     rdx, [rsp+160h+var_130]
0x1800f02b0  mov     rax, [rax+70h]
0x1800f02b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f02b9  mov     edi, eax
0x1800f02bb  test    eax, eax
0x1800f02bd  js      loc_1800F040B
0x1800f02c3  test    ebx, ebx
0x1800f02c5  jz      loc_1800F03DC
0x1800f02cb  cmp     ebx, 1
0x1800f02ce  jz      loc_1800F040B
0x1800f02d4  mov     edi, ebx
0x1800f02d6  jmp     loc_1800F040D
0x1800f02db  ucomiss xmm7, cs:__real@bf800000
0x1800f02e2  jp      short loc_1800F033B
0x1800f02e4  jnz     short loc_1800F033B
0x1800f02e6  mov     rcx, [rsp+160h+var_130]
0x1800f02eb  mov     rax, [rcx]
0x1800f02ee  lea     r8, [rsp+160h+var_128]
0x1800f02f3  movaps  xmm1, xmm6
0x1800f02f6  mov     rax, [rax+0D0h]
0x1800f02fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0302  mov     edi, eax
0x1800f0304  test    eax, eax
0x1800f0306  js      loc_1800F040B
0x1800f030c  mov     rcx, [rsp+160h+var_128]
0x1800f0311  mov     rax, [rcx]
0x1800f0314  lea     r8, [rsp+160h+var_108]
0x1800f0319  xor     edx, edx
0x1800f031b  mov     rax, [rax+0A0h]
0x1800f0322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0327  mov     edi, eax
0x1800f0329  test    eax, eax
  ... truncated ...
```
