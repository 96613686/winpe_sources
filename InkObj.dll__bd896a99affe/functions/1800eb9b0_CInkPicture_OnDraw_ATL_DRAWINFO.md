# CInkPicture::OnDraw(ATL_DRAWINFO &)

- ea: `0x1800eb9b0`
- end: `0x1800ec122`
- name: `?OnDraw@CInkPicture@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `1906`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x180026ce8`
- `0x1800276c4`
- `0x1800365f8`
- `0x180036824`
- `0x1800a38dc`
- `0x1800a9758`
- `0x1800aa22c`
- `0x1800eb9b0`
- `0x1800ef7e4`
- `0x1800f4240`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800ebfd4`
- `USER32!IsRectEmpty` at `0x1800ebfd4`
- `USER32!FillRect` at `0x1800ebb10`
- `USER32!FillRect` at `0x1800ebb10`
- `GDI32!IntersectClipRect` at `0x1800eba98`
- `GDI32!IntersectClipRect` at `0x1800ec067`
- `GDI32!IntersectClipRect` at `0x1800eba98`
- `GDI32!IntersectClipRect` at `0x1800ec067`
- `GDI32!CombineTransform` at `0x1800ebf94`
- `GDI32!CombineTransform` at `0x1800ebf94`
- `GDI32!CreateSolidBrush` at `0x1800ebaf5`
- `GDI32!CreateSolidBrush` at `0x1800ebaf5`
- `GDI32!RestoreDC` at `0x1800ebdbb`
- `GDI32!RestoreDC` at `0x1800ec0cb`
- `GDI32!RestoreDC` at `0x1800ebdbb`
- `GDI32!RestoreDC` at `0x1800ec0cb`
- `GDI32!SaveDC` at `0x1800eba76`
- `GDI32!SaveDC` at `0x1800ebd82`
- `GDI32!SaveDC` at `0x1800eba76`
- `GDI32!SaveDC` at `0x1800ebd82`
- `GDI32!GetDeviceCaps` at `0x1800ebeff`
- `GDI32!GetDeviceCaps` at `0x1800ebeff`
- `GDI32!DeleteObject` at `0x1800ebb19`
- `GDI32!DeleteObject` at `0x1800ebb19`
- `OLEAUT32!__imp_OleTranslateColor` at `0x1800ebae1`
- `OLEAUT32!__imp_OleTranslateColor` at `0x1800ebae1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CInkPicture::OnDraw(CInkPicture *this, struct ATL_DRAWINFO *a2)
{
  int v4; // ebx
  struct tagRECT *v5; // r15
  int v6; // r13d
  int v7; // r12d
  HDC *v8; // rdi
  double v9; // xmm10_8
  double v10; // xmm11_8
  int v11; // edi
  HBRUSH SolidBrush; // rax
  HBRUSH v13; // r12
  signed int v14; // eax
  int v15; // r10d
  int v16; // eax
  int v17; // r9d
  int v18; // r10d
  int v19; // r11d
  int v20; // edx
  int v21; // r8d
  int v22; // ebx
  int v23; // edi
  int v24; // ebx
  int v25; // eax
  int v26; // ebx
  int v27; // ebx
  struct tagRECT *v28; // r8
  struct IInkRenderer *v29; // rbx
  int v30; // r12d
  int v31; // r13d
  unsigned int v32; // r8d
  const unsigned __int16 *v33; // r9
  int v34; // eax
  float v35; // xmm8_4
  float v36; // xmm9_4
  float v37; // xmm6_4
  float v38; // xmm7_4
  FLOAT v39; // xmm0_4
  float v40; // xmm8_4
  float v41; // xmm9_4
  int v42; // eax
  int bottom; // ecx
  int v44; // r8d
  int v45; // r9d
  OLE_COLOR clr; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+64h] [rbp-9Ch] BYREF
  struct IInkRenderer *v49; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v50; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h] BYREF
  COLORREF colorref; // [rsp+7Ch] [rbp-84h] BYREF
  HDC *v53; // [rsp+80h] [rbp-80h]
  struct IUnknown *v54; // [rsp+88h] [rbp-78h] BYREF
  struct tagRECT v55; // [rsp+90h] [rbp-70h] BYREF
  struct IUnknown *v56[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _XFORM v57; // [rsp+B0h] [rbp-50h] BYREF
  struct _XFORM xfOut; // [rsp+D0h] [rbp-30h] BYREF
  struct _XFORM v59; // [rsp+F0h] [rbp-10h] BYREF

  v54 = 0;
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v56, (struct _RTL_CRITICAL_SECTION *)((char *)this + 448));
  ATL::AtlComPtrAssign(&v54, *((struct IUnknown **)this + 165));
  v4 = *((_DWORD *)this + 333);
  clr = *((_DWORD *)this + 335);
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v56);
  v5 = (struct tagRECT *)*((_QWORD *)a2 + 5);
  v6 = v5->right - v5->left;
  v7 = v5->bottom - v5->top;
  LODWORD(v49) = v7;
  v51 = 0;
  v48 = 0;
  v8 = (HDC *)((char *)a2 + 32);
  v53 = (HDC *)((char *)a2 + 32);
  if ( *((_DWORD *)a2 + 14) )
    v53 = (HDC *)((char *)a2 + 32);
  else
    SaveDC(*v8);
  IntersectClipRect(*v8, v5->left, v5->top, v5->right, v5->bottom);
  v9 = (double)v6 / (double)*((int *)this + 16);
  v10 = (double)v7 / (double)*((int *)this + 17);
  colorref = 0;
  v11 = OleTranslateColor(clr, 0, &colorref);
  clr = v11;
  if ( v11 >= 0 )
  {
    SolidBrush = CreateSolidBrush(colorref);
    v13 = SolidBrush;
    if ( SolidBrush )
    {
      FillRect(*v53, v5, SolidBrush);
      DeleteObject(v13);
    }
    v7 = (int)v49;
  }
  if ( v54 )
  {
    v50 = 0;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v54->lpVtbl->QueryInterface)(
            v54,
            &GUID_7bf80980_bf32_101a_8bbb_00aa00300cab,
            &v50);
    v11 = v14;
    clr = v14;
    if ( v14 < 0 )
      goto LABEL_36;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v50->lpVtbl[2].AddRef)(v50, &v48);
    v11 = v14;
    clr = v14;
    if ( v14 < 0 )
      goto LABEL_36;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v50->lpVtbl[2].QueryInterface)(v50, &v51);
    v11 = v14;
    clr = v14;
    if ( v14 < 0 || !v48 || !v51 || !v6 || !v7 )
      goto LABEL_36;
    clr = 0;
    LODWORD(v49) = 0;
    RoundToNearestLong((double)v51 * v9);
    v16 = RoundToNearestLong((double)v15 * v10);
    v48 = v16;
    v20 = v6 - v17;
    v21 = v7 - v16;
    if ( v4 )
    {
      v22 = v4 - 1;
      if ( !v22 )
      {
        if ( v20 < 0 )
        {
          v23 = (v19 - *((_DWORD *)this + 16)) / 2;
          v19 = *((_DWORD *)this + 16);
          v51 = v19;
        }
        else
        {
          clr = v20 / 2;
          v6 = v17;
          v23 = 0;
        }
        if ( v21 < 0 )
        {
          v24 = *((_DWORD *)this + 17);
          v18 -= (v18 - v24) / 2;
          goto LABEL_35;
        }
        LODWORD(v49) = v21 / 2;
        v7 = v48;
LABEL_20:
        v24 = v18;
LABEL_35:
        v48 = -v24;
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD, int, int, int, int, int, int, _QWORD))v50->lpVtbl[2].Release)(
                v50,
                *((_QWORD *)a2 + 4),
                v5->left + clr,
                (unsigned int)(v5->top + (_DWORD)v49),
                v6,
                v7,
                v23,
                v18,
                v19,
                -v24,
                *((_QWORD *)a2 + 6));
        v11 = v14;
        clr = v14;
LABEL_36:
        v26 = v14;
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v50);
        goto LABEL_38;
      }
      if ( v22 == 2 )
      {
        v23 = 0;
        goto LABEL_20;
      }
    }
    v23 = 0;
    if ( v21 > 0 )
    {
      v7 = v16;
      v24 = v18;
    }
    else
    {
      v24 = *((_DWORD *)this + 17);
      v25 = v24;
      if ( !*((_QWORD *)a2 + 6) )
        v25 = v18;
      v18 = v25;
    }
    if ( v20 > 0 )
    {
      v6 = v17;
    }
    else
    {
      v19 = *((_DWORD *)this + 16);
      v51 = v19;
    }
    goto LABEL_35;
  }
  v26 = v11;
LABEL_38:
  if ( v26 < 0 )
    goto LABEL_59;
  v50 = 0;
  v55 = *v5;
  CIRect::CIRect((CIRect *)v56, &v55, (int *)&clr);
  v11 = clr;
  if ( (clr & 0x80000000) == 0 )
  {
    ATL::AtlComPtrAssign(&v50, v56[0]);
    if ( *((_BYTE *)this + 1364) )
    {
      v27 = SaveDC(*((HDC *)a2 + 4));
      CInkPicture::_WindowInputRectangleToClippableRegion((CInkPicture *)((char *)this - 48), *((HDC *)a2 + 4), v28);
      *((_BYTE *)this + 1364) = 0;
      v11 = CInkPicture::_DrawInk((CInkPicture *)((char *)this - 48), *((HDC *)a2 + 4), (struct IInkRectangle *)v50, 0);
      RestoreDC(*((HDC *)a2 + 4), v27);
      goto LABEL_58;
    }
    v49 = 0;
    v11 = ATL::CComObject<CInkRenderer>::CreateInstance(&v49);
    if ( v11 < 0 )
      goto LABEL_58;
    v29 = v49;
    ((void (__fastcall *)(struct IInkRenderer *))v49->lpVtbl->AddRef)(v49);
    v30 = *((_DWORD *)a2 + 17);
    v31 = *((_DWORD *)a2 + 19);
    LODWORD(v49) = *((_DWORD *)a2 + 18);
    clr = *((_DWORD *)a2 + 20);
    memset(&v59, 0, sizeof(v59));
    ATL::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>(
      &v55,
      *((_QWORD *)this + 69));
    if ( *(_QWORD *)&v55.left )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, struct _XFORM *))(**(_QWORD **)&v55.left + 56LL))(
              *(_QWORD *)&v55.left,
              &v59);
      if ( v11 < 0 )
      {
LABEL_57:
        ((void (__fastcall *)(struct IInkRenderer *))v29->lpVtbl->Release)(v29);
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v55);
        goto LABEL_58;
      }
      xfOut = v59;
      v34 = ((__int64 (__fastcall *)(struct IInkRenderer *, struct _XFORM *))v29[1].lpVtbl->SetViewTransform)(
              &v29[1],
              &xfOut);
    }
    else
    {
      v34 = ATL::AtlSetErrorInfo(
              &CLSID_InkCollector,
              (const unsigned __int16 *)0x451,
              v32,
              v33,
              &IID_IInkCollector,
              -2144862204,
              hInstance);
    }
    v11 = v34;
    if ( v34 >= 0 )
    {
      v35 = (float)v30 / (float)v31;
      v36 = (float)(int)v49 / (float)(int)clr;
      v37 = v35 / *((float *)this + 349);
      v38 = v36 / *((float *)this + 350);
      if ( GetDeviceCaps(*((HDC *)a2 + 4), 2) == 5 )
      {
        v37 = v37 * v9;
        v38 = v38 * v10;
      }
      xfOut.eM11 = v37;
      *(_QWORD *)&xfOut.eM12 = 0;
      xfOut.eM22 = v38;
      *(_QWORD *)&xfOut.eDx = 0;
      if ( v5->left || v5->top )
      {
        v39 = (float)((float)v5->left * v37) / v9;
        xfOut.eDx = v39;
        xfOut.eDy = (float)((float)v5->top * v38) / v10;
      }
      CombineTransform(&xfOut, (const XFORM *)((char *)this + 1404), &xfOut);
      v57 = xfOut;
      v11 = ((__int64 (__fastcall *)(struct IInkRenderer *, struct _XFORM *))v29[1].lpVtbl->Invoke)(&v29[1], &v57);
      if ( v11 >= 0 )
      {
        if ( !IsRectEmpty((const RECT *)this + 86) )
        {
          v40 = v35 / *((float *)this + 342);
          v41 = v36 / *((float *)this + 343);
          RoundToNearestLong((float)*((int *)this + 347) * v41);
          RoundToNearestLong((float)*((int *)this + 346) * v40);
          RoundToNearestLong((float)*((int *)this + 345) * v41);
          v42 = RoundToNearestLong((float)*((int *)this + 344) * v40);
          IntersectClipRect(*v53, v5->left + v42, v44, v45, bottom);
        }
        v11 = CInkPicture::_DrawInk((CInkPicture *)((char *)this - 48), *v53, (struct IInkRectangle *)v50, v29 + 2);
      }
    }
    goto LABEL_57;
  }
LABEL_58:
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v56);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v50);
LABEL_59:
  if ( !*((_DWORD *)a2 + 14) )
    RestoreDC(*v53, -1);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v54);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800eb9b0  mov     rax, rsp
0x1800eb9b3  mov     [rax+18h], rbx
0x1800eb9b7  push    rbp
0x1800eb9b8  push    rsi
0x1800eb9b9  push    rdi
0x1800eb9ba  push    r12
0x1800eb9bc  push    r13
0x1800eb9be  push    r14
0x1800eb9c0  push    r15
0x1800eb9c2  lea     rbp, [rsp-70h]
0x1800eb9c7  sub     rsp, 170h
0x1800eb9ce  movaps  xmmword ptr [rax-48h], xmm6
0x1800eb9d2  movaps  xmmword ptr [rax-58h], xmm7
0x1800eb9d6  movaps  xmmword ptr [rax-68h], xmm8
0x1800eb9db  movaps  xmmword ptr [rax-78h], xmm9
0x1800eb9e0  movaps  xmmword ptr [rax-88h], xmm10
0x1800eb9e8  movaps  xmmword ptr [rax-98h], xmm11
0x1800eb9f0  mov     rax, cs:__security_cookie
0x1800eb9f7  xor     rax, rsp
0x1800eb9fa  mov     [rbp+0A0h+var_98], rax
0x1800eb9fe  mov     r14, rdx
0x1800eba01  mov     rsi, rcx
0x1800eba04  xor     edi, edi
0x1800eba06  mov     [rbp+0A0h+var_118], rdi
0x1800eba0a  lea     rdx, [rcx+1C0h]; struct _RTL_CRITICAL_SECTION *
0x1800eba11  lea     rcx, [rbp+0A0h+var_100]; this
0x1800eba15  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800eba1a  nop
0x1800eba1b  mov     rdx, [rsi+528h]; struct IUnknown *
0x1800eba22  lea     rcx, [rbp+0A0h+var_118]; struct IUnknown **
0x1800eba26  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800eba2b  mov     ebx, [rsi+534h]
0x1800eba31  mov     eax, [rsi+53Ch]
0x1800eba37  mov     [rsp+1A0h+clr], eax
0x1800eba3b  lea     rcx, [rbp+0A0h+var_100]; this
0x1800eba3f  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800eba44  mov     r15, [r14+28h]
0x1800eba48  mov     r13d, [r15+8]
0x1800eba4c  sub     r13d, [r15]
0x1800eba4f  mov     r12d, [r15+0Ch]
0x1800eba53  sub     r12d, [r15+4]
0x1800eba57  mov     dword ptr [rsp+1A0h+var_138], r12d
0x1800eba5c  mov     [rsp+1A0h+var_128], edi
0x1800eba60  mov     [rsp+1A0h+var_13C], edi
0x1800eba64  lea     rdi, [r14+20h]
0x1800eba68  mov     [rbp+0A0h+var_120], rdi
0x1800eba6c  cmp     dword ptr [r14+38h], 0
0x1800eba71  jnz     short loc_1800EBA7E
0x1800eba73  mov     rcx, [rdi]; hdc
0x1800eba76  call    cs:__imp_SaveDC
0x1800eba7c  jmp     short loc_1800EBA82
0x1800eba7e  mov     [rbp+0A0h+var_120], rdi
0x1800eba82  mov     eax, [r15+0Ch]
0x1800eba86  mov     [rsp+1A0h+bottom], eax; bottom
0x1800eba8a  mov     r9d, [r15+8]; right
0x1800eba8e  mov     r8d, [r15+4]; top
0x1800eba92  mov     edx, [r15]; left
0x1800eba95  mov     rcx, [rdi]; hdc
0x1800eba98  call    cs:__imp_IntersectClipRect
0x1800eba9e  movd    xmm10, r13d
0x1800ebaa3  cvtdq2pd xmm10, xmm10
0x1800ebaa8  movd    xmm0, dword ptr [rsi+40h]
0x1800ebaad  cvtdq2pd xmm0, xmm0
0x1800ebab1  divsd   xmm10, xmm0
0x1800ebab6  movd    xmm11, r12d
0x1800ebabb  cvtdq2pd xmm11, xmm11
0x1800ebac0  movd    xmm0, dword ptr [rsi+44h]
0x1800ebac5  cvtdq2pd xmm0, xmm0
0x1800ebac9  divsd   xmm11, xmm0
0x1800ebace  mov     [rsp+1A0h+colorref], 0
0x1800ebad6  lea     r8, [rsp+1A0h+colorref]; lpcolorref
0x1800ebadb  xor     edx, edx; hpal
0x1800ebadd  mov     ecx, [rsp+1A0h+clr]; clr
0x1800ebae1  call    cs:__imp_OleTranslateColor
0x1800ebae7  mov     edi, eax
0x1800ebae9  mov     [rsp+1A0h+clr], eax
0x1800ebaed  test    eax, eax
0x1800ebaef  js      short loc_1800EBB24
0x1800ebaf1  mov     ecx, [rsp+1A0h+colorref]; color
0x1800ebaf5  call    cs:__imp_CreateSolidBrush
0x1800ebafb  mov     r12, rax
0x1800ebafe  test    rax, rax
0x1800ebb01  jz      short loc_1800EBB1F
0x1800ebb03  mov     r8, rax; hbr
0x1800ebb06  mov     rdx, r15; lprc
0x1800ebb09  mov     rcx, [rbp+0A0h+var_120]
0x1800ebb0d  mov     rcx, [rcx]; hDC
0x1800ebb10  call    cs:__imp_FillRect
0x1800ebb16  mov     rcx, r12; ho
0x1800ebb19  call    cs:__imp_DeleteObject
0x1800ebb1f  mov     r12d, dword ptr [rsp+1A0h+var_138]
0x1800ebb24  mov     rcx, [rbp+0A0h+var_118]
0x1800ebb28  test    rcx, rcx
0x1800ebb2b  jz      loc_1800EBD2D
0x1800ebb31  mov     [rsp+1A0h+var_130], 0
0x1800ebb3a  mov     rax, [rcx]
0x1800ebb3d  lea     r8, [rsp+1A0h+var_130]
0x1800ebb42  lea     rdx, _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab
0x1800ebb49  mov     rax, [rax]
0x1800ebb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb51  mov     edi, eax
0x1800ebb53  mov     [rsp+1A0h+clr], eax
0x1800ebb57  test    eax, eax
0x1800ebb59  js      loc_1800EBD1F
0x1800ebb5f  mov     rcx, [rsp+1A0h+var_130]
0x1800ebb64  mov     rax, [rcx]
0x1800ebb67  lea     rdx, [rsp+1A0h+var_13C]
0x1800ebb6c  mov     rax, [rax+38h]
0x1800ebb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb75  mov     edi, eax
0x1800ebb77  mov     [rsp+1A0h+clr], eax
0x1800ebb7b  test    eax, eax
0x1800ebb7d  js      loc_1800EBD1F
0x1800ebb83  mov     rcx, [rsp+1A0h+var_130]
0x1800ebb88  mov     rax, [rcx]
0x1800ebb8b  lea     rdx, [rsp+1A0h+var_128]
0x1800ebb90  mov     rax, [rax+30h]
0x1800ebb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb99  mov     edi, eax
0x1800ebb9b  mov     [rsp+1A0h+clr], eax
0x1800ebb9f  test    eax, eax
0x1800ebba1  js      loc_1800EBD1F
0x1800ebba7  mov     r10d, [rsp+1A0h+var_13C]
0x1800ebbac  test    r10d, r10d
0x1800ebbaf  jz      loc_1800EBD1F
0x1800ebbb5  mov     r11d, [rsp+1A0h+var_128]
0x1800ebbba  test    r11d, r11d
0x1800ebbbd  jz      loc_1800EBD1F
0x1800ebbc3  test    r13d, r13d
0x1800ebbc6  jz      loc_1800EBD1F
0x1800ebbcc  test    r12d, r12d
0x1800ebbcf  jz      loc_1800EBD1F
0x1800ebbd5  mov     [rsp+1A0h+clr], 0
0x1800ebbdd  mov     dword ptr [rsp+1A0h+var_138], 0
0x1800ebbe5  movd    xmm0, r11d
0x1800ebbea  cvtdq2pd xmm0, xmm0
0x1800ebbee  mulsd   xmm0, xmm10
0x1800ebbf3  cvtpd2ps xmm0, xmm0; float
0x1800ebbf7  call    ?RoundToNearestLong@@YAJM@Z; RoundToNearestLong(float)
0x1800ebbfc  mov     r9d, eax
0x1800ebbff  movd    xmm2, r10d
0x1800ebc04  cvtdq2pd xmm2, xmm2
0x1800ebc08  mulsd   xmm2, xmm11
0x1800ebc0d  cvtpd2ps xmm0, xmm2; float
0x1800ebc11  call    ?RoundToNearestLong@@YAJM@Z; RoundToNearestLong(float)
0x1800ebc16  mov     [rsp+1A0h+var_13C], eax
0x1800ebc1a  mov     edx, r13d
0x1800ebc1d  sub     edx, r9d
0x1800ebc20  mov     r8d, r12d
0x1800ebc23  sub     r8d, eax
0x1800ebc26  test    ebx, ebx
0x1800ebc28  jz      short loc_1800EBC97
0x1800ebc2a  sub     ebx, 1
0x1800ebc2d  jz      short loc_1800EBC43
0x1800ebc2f  sub     ebx, 1
0x1800ebc32  jz      short loc_1800EBC97
0x1800ebc34  cmp     ebx, 1
0x1800ebc37  jnz     short loc_1800EBC97
0x1800ebc39  xor     edi, edi
0x1800ebc3b  mov     ebx, r10d
0x1800ebc3e  jmp     loc_1800EBCC8
0x1800ebc43  mov     ecx, 2
0x1800ebc48  test    edx, edx
0x1800ebc4a  js      short loc_1800EBC5C
0x1800ebc4c  mov     eax, edx
0x1800ebc4e  cdq
0x1800ebc4f  idiv    ecx
0x1800ebc51  mov     [rsp+1A0h+clr], eax
0x1800ebc55  mov     r13d, r9d
0x1800ebc58  xor     edi, edi
0x1800ebc5a  jmp     short loc_1800EBC71
0x1800ebc5c  sub     r11d, [rsi+40h]
0x1800ebc60  mov     eax, r11d
0x1800ebc63  cdq
0x1800ebc64  idiv    ecx
0x1800ebc66  mov     edi, eax
0x1800ebc68  mov     r11d, [rsi+40h]
0x1800ebc6c  mov     [rsp+1A0h+var_128], r11d
0x1800ebc71  test    r8d, r8d
0x1800ebc74  js      short loc_1800EBC87
0x1800ebc76  mov     eax, r8d
0x1800ebc79  cdq
0x1800ebc7a  idiv    ecx
0x1800ebc7c  mov     dword ptr [rsp+1A0h+var_138], eax
0x1800ebc80  mov     r12d, [rsp+1A0h+var_13C]
0x1800ebc85  jmp     short loc_1800EBC3B
0x1800ebc87  mov     ebx, [rsi+44h]
0x1800ebc8a  mov     eax, r10d
0x1800ebc8d  sub     eax, ebx
0x1800ebc8f  cdq
0x1800ebc90  idiv    ecx
0x1800ebc92  sub     r10d, eax
0x1800ebc95  jmp     short loc_1800EBCC8
0x1800ebc97  xor     edi, edi
0x1800ebc99  test    r8d, r8d
0x1800ebc9c  jg      short loc_1800EBCB0
0x1800ebc9e  mov     ebx, [rsi+44h]
0x1800ebca1  mov     eax, ebx
0x1800ebca3  cmp     [r14+30h], rdi
0x1800ebca7  cmovz   eax, r10d
0x1800ebcab  mov     r10d, eax
0x1800ebcae  jmp     short loc_1800EBCB6
0x1800ebcb0  mov     r12d, eax
0x1800ebcb3  mov     ebx, r10d
0x1800ebcb6  test    edx, edx
0x1800ebcb8  jg      short loc_1800EBCC5
0x1800ebcba  mov     r11d, [rsi+40h]
0x1800ebcbe  mov     [rsp+1A0h+var_128], r11d
0x1800ebcc3  jmp     short loc_1800EBCC8
0x1800ebcc5  mov     r13d, r9d
0x1800ebcc8  neg     ebx
0x1800ebcca  mov     [rsp+1A0h+var_13C], ebx
0x1800ebcce  mov     rcx, [rsp+1A0h+var_130]
0x1800ebcd3  mov     rdx, [rcx]
0x1800ebcd6  mov     r9d, dword ptr [rsp+1A0h+var_138]
0x1800ebcdb  add     r9d, [r15+4]
0x1800ebcdf  mov     r8d, [rsp+1A0h+clr]
0x1800ebce4  add     r8d, [r15]
0x1800ebce7  mov     rax, [rdx+40h]
0x1800ebceb  mov     rdx, [r14+30h]
0x1800ebcef  mov     [rsp+1A0h+var_150], rdx
0x1800ebcf4  mov     [rsp+1A0h+var_158], ebx
0x1800ebcf8  mov     [rsp+1A0h+var_160], r11d
0x1800ebcfd  mov     [rsp+1A0h+var_168], r10d
0x1800ebd02  mov     dword ptr [rsp+1A0h+var_170], edi
0x1800ebd06  mov     [rsp+1A0h+var_178], r12d
0x1800ebd0b  mov     [rsp+1A0h+bottom], r13d
0x1800ebd10  mov     rdx, [r14+20h]
0x1800ebd14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebd19  mov     edi, eax
0x1800ebd1b  mov     [rsp+1A0h+clr], eax
0x1800ebd1f  mov     ebx, eax
0x1800ebd21  lea     rcx, [rsp+1A0h+var_130]; void *
0x1800ebd26  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800ebd2b  jmp     short loc_1800EBD2F
0x1800ebd2d  mov     ebx, edi
0x1800ebd2f  xor     r12d, r12d
0x1800ebd32  test    ebx, ebx
0x1800ebd34  js      loc_1800EC0BB
0x1800ebd3a  mov     [rsp+1A0h+var_130], r12
0x1800ebd3f  movups  xmm0, xmmword ptr [r15]
0x1800ebd43  movdqu  xmmword ptr [rbp+0A0h+var_110.left], xmm0
0x1800ebd48  lea     r8, [rsp+1A0h+clr]; int *
0x1800ebd4d  lea     rdx, [rbp+0A0h+var_110]; struct tagRECT
0x1800ebd51  lea     rcx, [rbp+0A0h+var_100]; this
0x1800ebd55  call    ??0CIRect@@QEAA@UtagRECT@@AEAJ@Z; CIRect::CIRect(tagRECT,long &)
0x1800ebd5a  nop
0x1800ebd5b  mov     edi, [rsp+1A0h+clr]
0x1800ebd5f  test    edi, edi
0x1800ebd61  js      loc_1800EC0A7
0x1800ebd67  mov     rdx, [rbp+0A0h+var_100]; struct IUnknown *
0x1800ebd6b  lea     rcx, [rsp+1A0h+var_130]; struct IUnknown **
0x1800ebd70  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ebd75  cmp     [rsi+554h], r12b
0x1800ebd7c  jz      short loc_1800EBDC6
0x1800ebd7e  mov     rcx, [r14+20h]; hdc
0x1800ebd82  call    cs:__imp_SaveDC
0x1800ebd88  mov     ebx, eax
0x1800ebd8a  mov     rdx, [r14+20h]; HDC
0x1800ebd8e  lea     rcx, [rsi-30h]; this
0x1800ebd92  call    ?_WindowInputRectangleToClippableRegion@CInkPicture@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z; CInkPicture::_WindowInputRectangleToClippableRegion(HDC__ *,tagRECT *)
0x1800ebd97  mov     [rsi+554h], r12b
0x1800ebd9e  xor     r9d, r9d; struct IInkRenderer *
0x1800ebda1  mov     r8, [rsp+1A0h+var_130]; struct IInkRectangle *
0x1800ebda6  mov     rdx, [r14+20h]; HDC
0x1800ebdaa  lea     rcx, [rsi-30h]; this
0x1800ebdae  call    ?_DrawInk@CInkPicture@@AEAAJPEAUHDC__@@PEAUIInkRectangle@@PEAUIInkRenderer@@@Z; CInkPicture::_DrawInk(HDC__ *,IInkRectangle *,IInkRenderer *)
0x1800ebdb3  mov     edi, eax
0x1800ebdb5  mov     edx, ebx; nSavedDC
0x1800ebdb7  mov     rcx, [r14+20h]; hdc
0x1800ebdbb  call    cs:__imp_RestoreDC
0x1800ebdc1  jmp     loc_1800EC0A7
0x1800ebdc6  mov     [rsp+1A0h+var_138], r12
0x1800ebdcb  lea     rcx, [rsp+1A0h+var_138]
0x1800ebdd0  call    ?CreateInstance@?$CComObject@VCInkRenderer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInkRenderer>::CreateInstance(ATL::CComObject<CInkRenderer> * *)
0x1800ebdd5  mov     edi, eax
0x1800ebdd7  test    eax, eax
0x1800ebdd9  js      loc_1800EC0A7
0x1800ebddf  mov     rbx, [rsp+1A0h+var_138]
0x1800ebde4  mov     rax, [rbx]
0x1800ebde7  mov     rcx, rbx
0x1800ebdea  mov     rax, [rax+8]
0x1800ebdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebdf3  mov     r12d, [r14+44h]
0x1800ebdf7  mov     r13d, [r14+4Ch]
0x1800ebdfb  mov     eax, [r14+48h]
0x1800ebdff  mov     dword ptr [rsp+1A0h+var_138], eax
0x1800ebe03  mov     eax, [r14+50h]
0x1800ebe07  mov     [rsp+1A0h+clr], eax
0x1800ebe0b  xorps   xmm0, xmm0
0x1800ebe0e  xor     eax, eax
0x1800ebe10  movups  [rbp+0A0h+var_B0], xmm0
0x1800ebe14  mov     [rbp+0A0h+var_A0], rax
0x1800ebe18  mov     rdx, [rsi+228h]
0x1800ebe1f  lea     rcx, [rbp+0A0h+var_110]
0x1800ebe23  call    ??0?$CComQIPtr@UPIInkRenderer@@$1?_GUID_8d7b1448_7629_47a0_9b88_a986ef25648c@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>::CComQIPtr<PIInkRenderer,&__s_GUID const _GUID_8d7b1448_7629_47a0_9b88_a986ef25648c>(IUnknown *)
0x1800ebe28  nop
0x1800ebe29  mov     rcx, qword ptr [rbp+0A0h+var_110.left]
0x1800ebe2d  test    rcx, rcx
0x1800ebe30  jz      short loc_1800EBE74
  ... truncated ...
```
