# CacheEffect::Render(tagPOINT,tagSIZE,double,IImageBuffer * *)

- ea: `0x180224f20`
- end: `0x180225f6d`
- name: `?Render@CacheEffect@@UEAAJUtagPOINT@@UtagSIZE@@NPEAPEAUIImageBuffer@@@Z`
- size: `4173`
- prototype: `__int64 __fastcall(CacheEffect *__hidden this, struct tagPOINT, struct tagSIZE, double, struct IImageBuffer **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001397c`
- `0x18001db0c`
- `0x1802243f4`
- `0x180224f20`
- `0x1802264dc`
- `0x180226798`
- `0x1804605b0`
- `0x1804610a0`
- `0x18046145c`
- `0x1804614b4`
- `0x18046153c`
- `0x18046160c`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180225532`
- `OLEAUT32!__imp_SysFreeString` at `0x18022571d`
- `OLEAUT32!__imp_SysFreeString` at `0x180225d48`
- `OLEAUT32!__imp_SysFreeString` at `0x180225db9`
- `OLEAUT32!__imp_SysFreeString` at `0x180225de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180225532`
- `OLEAUT32!__imp_SysFreeString` at `0x18022571d`
- `OLEAUT32!__imp_SysFreeString` at `0x180225d48`
- `OLEAUT32!__imp_SysFreeString` at `0x180225db9`
- `OLEAUT32!__imp_SysFreeString` at `0x180225de8`
- `OLEAUT32!__imp_VariantInit` at `0x1802259ef`
- `OLEAUT32!__imp_VariantInit` at `0x1802259ef`
- `OLEAUT32!__imp_VariantClear` at `0x180225ae1`
- `OLEAUT32!__imp_VariantClear` at `0x180225ae1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18022516f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18022546b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180225c88`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18022516f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18022546b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180225c88`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802254f2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802256dd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180225d06`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802254f2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802256dd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180225d06`
- `GDI32!CombineRgn` at `0x1802251f9`
- `GDI32!CombineRgn` at `0x18022520e`
- `GDI32!CombineRgn` at `0x18022599b`
- `GDI32!CombineRgn` at `0x1802251f9`
- `GDI32!CombineRgn` at `0x18022520e`
- `GDI32!CombineRgn` at `0x18022599b`
- `GDI32!GetRgnBox` at `0x18022524d`
- `GDI32!GetRgnBox` at `0x1802259cc`
- `GDI32!GetRgnBox` at `0x18022524d`
- `GDI32!GetRgnBox` at `0x1802259cc`
- `GDI32!CreateRectRgn` at `0x1802251bd`
- `GDI32!CreateRectRgn` at `0x1802251bd`
- `GDI32!DeleteObject` at `0x18022521c`
- `GDI32!DeleteObject` at `0x18022522c`
- `GDI32!DeleteObject` at `0x180225501`
- `GDI32!DeleteObject` at `0x1802256ec`
- `GDI32!DeleteObject` at `0x1802259a9`
- `GDI32!DeleteObject` at `0x180225aef`
- `GDI32!DeleteObject` at `0x180225d15`
- `GDI32!DeleteObject` at `0x180225d88`
- `GDI32!DeleteObject` at `0x18022521c`
- `GDI32!DeleteObject` at `0x18022522c`
- `GDI32!DeleteObject` at `0x180225501`
- `GDI32!DeleteObject` at `0x1802256ec`
- `GDI32!DeleteObject` at `0x1802259a9`
- `GDI32!DeleteObject` at `0x180225aef`
- `GDI32!DeleteObject` at `0x180225d15`
- `GDI32!DeleteObject` at `0x180225d88`
- `GDI32!CreateRectRgnIndirect` at `0x1802251df`
- `GDI32!CreateRectRgnIndirect` at `0x18022596d`
- `GDI32!CreateRectRgnIndirect` at `0x180225983`
- `GDI32!CreateRectRgnIndirect` at `0x1802251df`
- `GDI32!CreateRectRgnIndirect` at `0x18022596d`
- `GDI32!CreateRectRgnIndirect` at `0x180225983`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CacheEffect::Render(
        CacheEffect *this,
        struct tagPOINT a2,
        struct tagSIZE a3,
        double a4,
        struct IImageBuffer **a5)
{
  int (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // r9
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  void *v13; // rax
  ImageCache **v14; // rdi
  HRGN RectRgn; // rsi
  HRGN RectRgnIndirect; // rbx
  HRGN v17; // rax
  __int64 v18; // rcx
  int i; // r8d
  int *v20; // rdx
  __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // r14
  __int64 v26; // r15
  double v27; // xmm0_8
  unsigned __int64 v28; // rax
  double v29; // xmm0_8
  double v30; // xmm1_8
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  void *v34; // rax
  __int64 v35; // rbx
  ImageCache **v36; // rcx
  struct IImageBuffer *v37; // rax
  int v38; // ebx
  int v39; // ebx
  int v40; // r14d
  int *v41; // r8
  __int64 v42; // rcx
  __int64 (__fastcall *v43)(__int64, _QWORD, _QWORD, unsigned __int64, _QWORD, struct IImageBuffer **); // r10
  __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // eax
  struct IImageBuffer *v47; // rax
  int v48; // eax
  bool v49; // di
  int j; // r15d
  const RECT *v51; // r14
  __int64 v52; // rcx
  __int64 (__fastcall *v53)(__int64, _QWORD, _QWORD, unsigned __int64, _QWORD, struct IImageBuffer **); // r10
  __int64 v54; // r8
  __int64 v55; // rdx
  int v56; // eax
  int v57; // eax
  LONG right; // ecx
  LONG top; // edx
  LONG bottom; // r8d
  HRGN v61; // rbx
  HRGN v62; // rdi
  __int64 (__fastcall *v63)(struct IImageBuffer *, _QWORD, unsigned __int64, VARIANTARG *); // r10
  __int64 v64; // r8
  __int64 v65; // rdx
  int v66; // eax
  LONG left; // r8d
  LONG v68; // edx
  LONG v69; // r11d
  LONG v70; // r9d
  __int64 (__fastcall *v71)(struct IImageBuffer *, struct IImageBuffer *, __int64, unsigned __int64); // rbx
  __int64 v72; // r10
  __int64 v73; // r9
  int v74; // eax
  int v75; // eax
  void *v76; // rax
  __int64 v77; // rbx
  ImageCache **v78; // rcx
  struct IImageBuffer *v79; // rax
  HRGN hrgnSrc2; // [rsp+40h] [rbp-188h] BYREF
  struct IImageBuffer *v82; // [rsp+48h] [rbp-180h] BYREF
  ImageCache **v83; // [rsp+50h] [rbp-178h] BYREF
  int v84; // [rsp+58h] [rbp-170h] BYREF
  struct IImageBuffer *v85; // [rsp+60h] [rbp-168h] BYREF
  int v86; // [rsp+68h] [rbp-160h] BYREF
  HRGN v87; // [rsp+70h] [rbp-158h] BYREF
  __int64 v88; // [rsp+78h] [rbp-150h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-148h] BYREF
  unsigned __int64 v90; // [rsp+88h] [rbp-140h]
  struct tagPOINT v91; // [rsp+90h] [rbp-138h] BYREF
  int v92; // [rsp+98h] [rbp-130h]
  int v93; // [rsp+9Ch] [rbp-12Ch]
  struct tagPOINT v94; // [rsp+A0h] [rbp-128h] BYREF
  _QWORD v95[3]; // [rsp+A8h] [rbp-120h] BYREF
  __int64 v96; // [rsp+C0h] [rbp-108h]
  void *Block; // [rsp+D0h] [rbp-F8h] BYREF
  HRGN v98; // [rsp+D8h] [rbp-F0h]
  VARIANTARG pvarg; // [rsp+F8h] [rbp-D0h] BYREF
  HRGN v100; // [rsp+110h] [rbp-B8h]
  VARIANTARG v101; // [rsp+120h] [rbp-A8h] BYREF
  struct tagRECT rc; // [rsp+150h] [rbp-78h] BYREF
  RECT rect; // [rsp+160h] [rbp-68h] BYREF

  v94 = a2;
  v95[0] = a3;
  if ( !a5 )
    ATL::BaseAtlThrow(-2147467261);
  bstrString = 0;
  v6 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 16);
  v7 = 0;
  v88 = 0;
  if ( v6 )
  {
    if ( (**v6)(v6, &GUID_3ed560b0_d9d0_42ba_b83c_941948c5b2b4, &v88) >= 0 )
    {
      v7 = v88;
    }
    else
    {
      v7 = 0;
      v88 = 0;
    }
  }
  v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v7 + 376LL))(v7, &bstrString);
  if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
    ATL::BaseAtlThrow(v8);
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  if ( *((double *)this + 27) != a4 )
  {
    *((double *)this + 27) = a4;
    ImageCache::CleanAll(*((ImageCache **)this + 18));
  }
  v86 = 0;
  v84 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**((_QWORD **)this + 16) + 240LL))(
         *((_QWORD *)this + 16),
         &v86,
         &v84);
  if ( v9 == -2147024882 || v9 == -2045378032 || v9 == -2045312765 || v9 == -2045247216 )
    ATL::BaseAtlThrow(v9);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  v10 = (*(__int64 (__fastcall **)(CacheEffect *, _QWORD, _QWORD, struct tagPOINT *, _QWORD *, _QWORD))(*(_QWORD *)this + 72LL))(
          this,
          0,
          0,
          &v94,
          v95,
          *(_QWORD *)&a4);
  if ( v10 == -2147024882 || v10 == -2045378032 || v10 == -2045312765 || v10 == -2045247216 )
    ATL::BaseAtlThrow(v10);
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  v91 = v94;
  v11 = v94.x + (__int64)SLODWORD(v95[0]);
  if ( (unsigned __int64)(v11 + 0x80000000LL) > 0xFFFFFFFF
    || (v92 = v94.x + LODWORD(v95[0]),
        v12 = v94.y + (__int64)SHIDWORD(v95[0]),
        (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v93 = v94.y + HIDWORD(v95[0]);
  if ( v94.x < (int)v11 && v94.y < (int)v12 )
  {
    v13 = malloc(0x38u);
    if ( !v13 )
      ThrowOOM();
    v90 = (unsigned __int64)v13;
    v14 = (ImageCache **)ImageCacheLock::ImageCacheLock(
                           (_DWORD)v13,
                           *((_QWORD *)this + 18),
                           (unsigned int)&v91,
                           v84,
                           v86);
    v83 = v14;
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v100 = RectRgn;
    ImageCache::GetLockedCacheRegion(*v14, &hrgnSrc2);
    RectRgnIndirect = CreateRectRgnIndirect((const RECT *)(v14 + 3));
    CombineRgn(RectRgnIndirect, RectRgnIndirect, hrgnSrc2, 4);
    CombineRgn(RectRgn, RectRgnIndirect, 0, 5);
    if ( RectRgnIndirect )
      DeleteObject(RectRgnIndirect);
    if ( hrgnSrc2 )
      DeleteObject(hrgnSrc2);
    *(_QWORD *)&rc.left = 0;
    *(_QWORD *)&rc.right = 0;
    GetRgnBox(RectRgn, &rc);
    if ( rc.left >= rc.right || rc.top >= rc.bottom )
    {
      hrgnSrc2 = 0;
      ImageCacheLock::GetTile(v14, &hrgnSrc2, 0, 0, 0);
      v79 = (struct IImageBuffer *)hrgnSrc2;
      hrgnSrc2 = 0;
      *a5 = v79;
      if ( RectRgn )
        DeleteObject(RectRgn);
      Base::Ptr<ImageCacheLock>::Release(&v83);
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      goto LABEL_179;
    }
    RegionRects::RegionRects((RegionRects *)&Block, RectRgn, 6);
    v17 = v98;
    hrgnSrc2 = v98;
    v18 = 0;
    for ( i = 0; i < (int)v17; ++i )
    {
      if ( i < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( i >= (unsigned __int64)v17 )
        ATL::BaseAtlThrow(-2147024809);
      v20 = (int *)((char *)Block + 16 * i);
      v21 = v20[2] - (__int64)*v20;
      if ( (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_215;
      v22 = v20[3] - (__int64)v20[1];
      if ( (unsigned __int64)(v22 + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_215;
      v23 = (int)v21 * (__int64)(int)v22;
      if ( (unsigned __int64)(v23 + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_215;
      v18 += (int)v23;
      v17 = hrgnSrc2;
    }
    v24 = v92 - (__int64)v91.x;
    if ( (unsigned __int64)(v24 + 0x80000000LL) > 0xFFFFFFFF
      || (v25 = v93 - (__int64)v91.y, (unsigned __int64)(v25 + 0x80000000LL) > 0xFFFFFFFF)
      || (v26 = (int)v24 * (__int64)(int)v25, (unsigned __int64)(v26 + 0x80000000LL) > 0xFFFFFFFF) )
    {
LABEL_215:
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    if ( (int)v26 < 0 )
    {
      v28 = v26 & 1 | ((unsigned __int64)(int)v26 >> 1);
      v27 = (double)(int)v28 + (double)(int)v28;
    }
    else
    {
      v27 = (double)(int)v26;
    }
    v29 = v27 * 0.8;
    if ( v18 < 0 )
      v30 = (double)(int)(v18 & 1 | ((unsigned __int64)v18 >> 1))
          + (double)(int)(v18 & 1 | ((unsigned __int64)v18 >> 1));
    else
      v30 = (double)(int)v18;
    if ( v30 > v29 )
    {
      Base::Ptr<ImageCacheLock>::Release(&v83);
      v82 = 0;
      v31 = (__int64 *)*((_QWORD *)this + 16);
      v32 = *v31;
      hrgnSrc2 = (HRGN)__PAIR64__(v25, v24);
      v33 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct tagPOINT, unsigned __int64, _QWORD, struct IImageBuffer **))(v32 + 160))(
              v31,
              0,
              v91,
              __PAIR64__(v25, v24),
              *(_QWORD *)&a4,
              &v82);
      if ( v33 == -2147024882 || v33 == -2045378032 || v33 == -2045312765 || v33 == -2045247216 )
        ATL::BaseAtlThrow(v33);
      if ( v33 < 0 )
        ATL::BaseAtlThrow(v33);
      v34 = malloc(0x38u);
      if ( !v34 )
        ThrowOOM();
      v90 = (unsigned __int64)v34;
      v35 = ImageCacheLock::ImageCacheLock((_DWORD)v34, *((_QWORD *)this + 18), (unsigned int)&v91, v84, v86);
      v36 = v83;
      if ( v83 != (ImageCache **)v35 )
      {
        Base::Ptr<ImageCacheLock>::Release(&v83);
        v36 = (ImageCache **)v35;
        v83 = (ImageCache **)v35;
      }
      ImageCache::AddTile(*v36, v82);
      v37 = v82;
      v82 = 0;
      *a5 = v37;
      if ( Block )
        free(Block);
      if ( RectRgn )
        DeleteObject(RectRgn);
      Base::Ptr<ImageCacheLock>::Release(&v83);
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
LABEL_179:
      SysFreeString(bstrString);
      return 0;
    }
    if ( v84 != 1 )
    {
      if ( v84 == 2 || v84 == 4 )
      {
        v38 = 8;
        goto LABEL_74;
      }
      if ( v84 == 8 )
      {
        v38 = 16;
        goto LABEL_74;
      }
    }
    v38 = 4;
LABEL_74:
    if ( (double)((int)v26 * v38) < ImageCache::GetLockedCacheByteSize(*v14) )
    {
      v85 = 0;
      ImageCacheLock::GetTile(v14, &v85, 1, 0, 1);
      Base::Ptr<ImageCacheLock>::Release(&v83);
      LODWORD(v87) = 0;
      v48 = (*(__int64 (__fastcall **)(struct IImageBuffer *, HRGN *))(*(_QWORD *)v85 + 72LL))(v85, &v87);
      if ( v48 == -2147024882 || v48 == -2045378032 || v48 == -2045312765 || v48 == -2045247216 )
        ATL::BaseAtlThrow(v48);
      if ( v48 < 0 )
        ATL::BaseAtlThrow(v48);
      v49 = (_DWORD)v87 == 0;
      for ( j = 0; j < (int)hrgnSrc2; ++j )
      {
        v82 = 0;
        if ( j < 0 )
          ATL::BaseAtlThrow(-2147024809);
        if ( j >= (unsigned __int64)v98 )
          ATL::BaseAtlThrow(-2147024809);
        v51 = (const RECT *)((char *)Block + 16 * j);
        v52 = *((_QWORD *)this + 16);
        v53 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int64, _QWORD, struct IImageBuffer **))(*(_QWORD *)v52 + 160LL);
        v54 = v51->bottom - (__int64)v51->top;
        if ( (unsigned __int64)(v54 + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_210;
        v55 = v51->right - (__int64)v51->left;
        if ( (unsigned __int64)(v55 + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_210;
        v95[1] = __PAIR64__(v54, v55);
        v56 = v53(v52, 0, *(_QWORD *)&v51->left, __PAIR64__(v54, v55), *(_QWORD *)&a4, &v82);
        if ( v56 == -2147024882 || v56 == -2045378032 || v56 == -2045312765 || v56 == -2045247216 )
          ATL::BaseAtlThrow(v56);
        if ( v56 < 0 )
          ATL::BaseAtlThrow(v56);
        if ( v49 )
          goto LABEL_120;
        LODWORD(v87) = 0;
        v57 = (*(__int64 (__fastcall **)(struct IImageBuffer *, HRGN *))(*(_QWORD *)v82 + 72LL))(v82, &v87);
        if ( v57 == -2147024882 || v57 == -2045378032 || v57 == -2045312765 || v57 == -2045247216 )
          ATL::BaseAtlThrow(v57);
        if ( v57 < 0 )
          ATL::BaseAtlThrow(v57);
        if ( !(_DWORD)v87 )
LABEL_120:
          v49 = 1;
        else
          v49 = 0;
        CacheEffect::GetRenderedRect(&rect, v82);
        right = v51->right;
        if ( v51->left < right )
        {
          top = v51->top;
          bottom = v51->bottom;
          if ( top < bottom && (rect.left > v51->left || rect.right < right || rect.top > top || rect.bottom < bottom) )
          {
            v61 = CreateRectRgnIndirect(v51);
            v87 = v61;
            v62 = CreateRectRgnIndirect(&rect);
            CombineRgn(v61, v61, v62, 4);
            if ( v62 )
              DeleteObject(v62);
            *(_QWORD *)&rc.left = 0;
            *(_QWORD *)&rc.right = 0;
            GetRgnBox(v61, &rc);
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            v63 = *(__int64 (__fastcall **)(struct IImageBuffer *, _QWORD, unsigned __int64, VARIANTARG *))(*(_QWORD *)v85 + 96LL);
            v64 = rc.bottom - (__int64)rc.top;
            if ( (unsigned __int64)(v64 + 0x80000000LL) > 0xFFFFFFFF
              || (v65 = rc.right - (__int64)rc.left, (unsigned __int64)(v65 + 0x80000000LL) > 0xFFFFFFFF) )
            {
              safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
            }
            v95[2] = __PAIR64__(v64, v65);
            v101 = pvarg;
            v66 = v63(v85, *(_QWORD *)&rc.left, __PAIR64__(v64, v65), &v101);
            if ( v66 == -2147024882 || v66 == -2045378032 || v66 == -2045312765 || v66 == -2045247216 )
              ATL::BaseAtlThrow(v66);
            if ( v66 < 0 )
              ATL::BaseAtlThrow(v66);
            v49 = 1;
            VariantClear(&pvarg);
            if ( v61 )
              DeleteObject(v61);
          }
        }
        left = v51->left;
        v68 = v51->top;
        v69 = v51->right;
        v70 = v51->bottom;
        if ( v51->left <= rect.left )
          left = rect.left;
        LODWORD(v96) = left;
        if ( v68 <= rect.top )
          v68 = rect.top;
        HIDWORD(v96) = v68;
        if ( v69 >= rect.right )
          v69 = rect.right;
        if ( v70 >= rect.bottom )
          v70 = rect.bottom;
        if ( left > v69 || v68 > v70 )
        {
          v70 = 0;
          v69 = 0;
          v68 = 0;
          v96 = 0;
          left = 0;
        }
        v71 = *(__int64 (__fastcall **)(struct IImageBuffer *, struct IImageBuffer *, __int64, unsigned __int64))(*(_QWORD *)v85 + 112LL);
        v72 = v70 - (__int64)v68;
        if ( (unsigned __int64)(v72 + 0x80000000LL) > 0xFFFFFFFF
          || (v73 = v69 - (__int64)left, (unsigned __int64)(v73 + 0x80000000LL) > 0xFFFFFFFF) )
        {
LABEL_210:
          safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
        }
        v90 = __PAIR64__(v72, v73);
        v74 = v71(v85, v82, v96, __PAIR64__(v72, v73));
        if ( v74 == -2147024882 || v74 == -2045378032 || v74 == -2045312765 || v74 == -2045247216 )
          ATL::BaseAtlThrow(v74);
        if ( v74 < 0 )
          ATL::BaseAtlThrow(v74);
        if ( v82 )
          (*(void (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v82 + 16LL))(v82);
      }
      if ( v49 )
      {
        v75 = (*(__int64 (__fastcall **)(struct IImageBuffer *, _QWORD))(*(_QWORD *)v85 + 80LL))(v85, 0);
        if ( v75 == -2147024882 || v75 == -2045378032 || v75 == -2045312765 || v75 == -2045247216 )
          ATL::BaseAtlThrow(v75);
        if ( v75 < 0 )
          ATL::BaseAtlThrow(v75);
      }
      v76 = malloc(0x38u);
      if ( !v76 )
        ThrowOOM();
      v90 = (unsigned __int64)v76;
      v77 = ImageCacheLock::ImageCacheLock((_DWORD)v76, *((_QWORD *)this + 18), (unsigned int)&v91, v84, v86);
      v78 = v83;
      if ( v83 != (ImageCache **)v77 )
      {
        Base::Ptr<ImageCacheLock>::Release(&v83);
        v78 = (ImageCache **)v77;
        v83 = (ImageCache **)v77;
      }
      ImageCache::AddTile(*v78, v85);
      *a5 = v85;
      if ( Block )
        free(Block);
      if ( RectRgn )
        DeleteObject(RectRgn);
      Base::Ptr<ImageCacheLock>::Release(&v83);
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    else
    {
      v39 = 0;
      v40 = (int)hrgnSrc2;
      while ( v39 < v40 )
      {
        v82 = 0;
        if ( v39 < 0 )
          ATL::BaseAtlThrow(-2147024809);
        if ( v39 >= (unsigned __int64)v98 )
          ATL::BaseAtlThrow(-2147024809);
        v41 = (int *)((char *)Block + 16 * v39);
        v42 = *((_QWORD *)this + 16);
        v43 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int64, _QWORD, struct IImageBuffer **))(*(_QWORD *)v42 + 160LL);
        v44 = v41[3] - (__int64)v41[1];
        if ( (unsigned __int64)(v44 + 0x80000000LL) > 0xFFFFFFFF
          || (v45 = v41[2] - (__int64)*v41, (unsigned __int64)(v45 + 0x80000000LL) > 0xFFFFFFFF) )
        {
          safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
        }
        hrgnSrc2 = (HRGN)__PAIR64__(v44, v45);
        v46 = v43(v42, 0, *(_QWORD *)v41, __PAIR64__(v44, v45), *(_QWORD *)&a4, &v82);
        if ( v46 == -2147024882 || v46 == -2045378032 || v46 == -2045312765 || v46 == -2045247216 )
          ATL::BaseAtlThrow(v46);
        if ( v46 < 0 )
          ATL::BaseAtlThrow(v46);
        ImageCache::AddTile(*v14, v82);
        if ( v82 )
          (*(void (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v82 + 16LL))(v82);
        ++v39;
      }
      v85 = 0;
      ImageCacheLock::GetTile(v14, &v85, 0, 1, 0);
      v47 = v85;
      v85 = 0;
      *a5 = v47;
      if ( Block )
        free(Block);
      if ( RectRgn )
        DeleteObject(RectRgn);
      Base::Ptr<ImageCacheLock>::Release(&v83);
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    goto LABEL_179;
  }
  *a5 = 0;
  if ( v88 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  SysFreeString(bstrString);
  return 0;
}

```

## disassembly

```asm
0x180224f20  mov     r11, rsp
0x180224f23  push    rbx
0x180224f24  push    rsi
0x180224f25  push    rdi
0x180224f26  push    r12
0x180224f28  push    r13
0x180224f2a  push    r14
0x180224f2c  push    r15
0x180224f2e  sub     rsp, 190h
0x180224f35  movaps  xmmword ptr [r11-48h], xmm6
0x180224f3a  mov     rax, cs:__security_cookie
0x180224f41  xor     rax, rsp
0x180224f44  mov     [rsp+1C8h+var_58], rax
0x180224f4c  movaps  xmm6, xmm3
0x180224f4f  mov     r12, rcx
0x180224f52  mov     r13, [rsp+1C8h+arg_20]
0x180224f5a  mov     [r11-128h], rdx
0x180224f61  mov     [r11-120h], r8
0x180224f68  xor     r14d, r14d
0x180224f6b  test    r13, r13
0x180224f6e  jz      loc_180225E2D
0x180224f74  mov     [rsp+1C8h+bstrString], r14
0x180224f7c  mov     r9, [rcx+80h]
0x180224f83  mov     rcx, r14
0x180224f86  mov     [rsp+1C8h+var_150], rcx
0x180224f8b  test    r9, r9
0x180224f8e  jz      short loc_180224FBE
0x180224f90  mov     rax, [r9]
0x180224f93  lea     r8, [rsp+1C8h+var_150]
0x180224f98  lea     rdx, _GUID_3ed560b0_d9d0_42ba_b83c_941948c5b2b4
0x180224f9f  mov     rcx, r9
0x180224fa2  mov     rax, [rax]
0x180224fa5  call    cs:__guard_dispatch_icall_fptr
0x180224fab  test    eax, eax
0x180224fad  jns     short loc_180224FB9
0x180224faf  mov     rcx, r14
0x180224fb2  mov     [rsp+1C8h+var_150], rcx
0x180224fb7  jmp     short loc_180224FBE
0x180224fb9  mov     rcx, [rsp+1C8h+var_150]
0x180224fbe  mov     rax, [rcx]
0x180224fc1  lea     rdx, [rsp+1C8h+bstrString]
0x180224fc9  mov     rax, [rax+178h]
0x180224fd0  call    cs:__guard_dispatch_icall_fptr
0x180224fd6  mov     ebx, 8007000Eh
0x180224fdb  cmp     eax, ebx
0x180224fdd  jz      loc_180225F64
0x180224fe3  mov     edi, 86160210h
0x180224fe8  cmp     eax, edi
0x180224fea  jz      loc_180225F64
0x180224ff0  mov     esi, 86170103h
0x180224ff5  cmp     eax, esi
0x180224ff7  jz      loc_180225F64
0x180224ffd  mov     r15d, 86180110h
0x180225003  cmp     eax, r15d
0x180225006  jz      loc_180225F64
0x18022500c  test    eax, eax
0x18022500e  js      loc_180225E3B
0x180225014  movsd   xmm0, qword ptr [r12+0D8h]
0x18022501e  ucomisd xmm0, xmm6
0x180225022  jp      short loc_180225026
0x180225024  jz      short loc_18022503D
0x180225026  movsd   qword ptr [r12+0D8h], xmm6
0x180225030  mov     rcx, [r12+90h]; this
0x180225038  call    ?CleanAll@ImageCache@@QEAAXXZ; ImageCache::CleanAll(void)
0x18022503d  mov     [rsp+1C8h+var_160], r14d
0x180225042  mov     [rsp+1C8h+var_170], r14d
0x180225047  mov     rcx, [r12+80h]
0x18022504f  mov     rax, [rcx]
0x180225052  lea     r8, [rsp+1C8h+var_170]
0x180225057  lea     rdx, [rsp+1C8h+var_160]
0x18022505c  mov     rax, [rax+0F0h]
0x180225063  call    cs:__guard_dispatch_icall_fptr
0x180225069  cmp     eax, ebx
0x18022506b  jz      loc_180225F5D
0x180225071  cmp     eax, edi
0x180225073  jz      loc_180225F5D
0x180225079  cmp     eax, esi
0x18022507b  jz      loc_180225F5D
0x180225081  cmp     eax, r15d
0x180225084  jz      loc_180225F5D
0x18022508a  test    eax, eax
0x18022508c  js      loc_180225E42
0x180225092  mov     rax, [r12]
0x180225096  movsd   [rsp+1C8h+var_1A0], xmm6
0x18022509c  lea     rcx, [rsp+1C8h+var_120]
0x1802250a4  mov     [rsp+1C8h+var_1A8], rcx
0x1802250a9  lea     r9, [rsp+1C8h+var_128]
0x1802250b1  xor     r8d, r8d
0x1802250b4  xor     edx, edx
0x1802250b6  mov     rcx, r12
0x1802250b9  mov     rax, [rax+48h]
0x1802250bd  call    cs:__guard_dispatch_icall_fptr
0x1802250c3  cmp     eax, ebx
0x1802250c5  jz      loc_180225F56
0x1802250cb  cmp     eax, edi
0x1802250cd  jz      loc_180225F56
0x1802250d3  cmp     eax, esi
0x1802250d5  jz      loc_180225F56
0x1802250db  cmp     eax, r15d
0x1802250de  jz      loc_180225F56
0x1802250e4  test    eax, eax
0x1802250e6  js      loc_180225E49
0x1802250ec  mov     rax, [rsp+1C8h+var_128]
0x1802250f4  mov     dword ptr [rsp+1C8h+var_138], eax
0x1802250fb  movsxd  r9, dword ptr [rsp+1C8h+var_128+4]
0x180225103  mov     dword ptr [rsp+1C8h+var_138+4], r9d
0x18022510b  movsxd  rdx, [rsp+1C8h+var_120]
0x180225113  movsxd  rcx, eax
0x180225116  add     rdx, rcx
0x180225119  mov     r15d, 80000000h
0x18022511f  lea     rcx, [r15+rdx]
0x180225123  mov     r10d, 0FFFFFFFFh
0x180225129  cmp     rcx, r10
0x18022512c  ja      loc_180225F50
0x180225132  mov     [rsp+1C8h+var_130], edx
0x180225139  movsxd  r8, [rsp+1C8h+var_11C]
0x180225141  add     r8, r9
0x180225144  lea     rcx, [r8+r15]
0x180225148  cmp     rcx, r10
0x18022514b  ja      loc_180225F50
0x180225151  mov     [rsp+1C8h+var_12C], r8d
0x180225159  cmp     eax, edx
0x18022515b  jge     loc_180225DC3
0x180225161  cmp     r9d, r8d
0x180225164  jge     loc_180225DC3
0x18022516a  mov     ecx, 38h ; '8'; Size
0x18022516f  call    cs:__imp_malloc
0x180225175  mov     rcx, rax
0x180225178  test    rax, rax
0x18022517b  jz      loc_180225E50
0x180225181  mov     [rsp+1C8h+var_140], rcx
0x180225189  mov     eax, [rsp+1C8h+var_160]
0x18022518d  mov     dword ptr [rsp+1C8h+var_1A8], eax
0x180225191  mov     r9d, [rsp+1C8h+var_170]
0x180225196  lea     r8, [rsp+1C8h+var_138]
0x18022519e  mov     rdx, [r12+90h]
0x1802251a6  call    ??0ImageCacheLock@@QEAA@PEAVImageCache@@AEBU?$RectT@UIntegerTypes@@@@W4ChannelFormat@@W4DeviceType@@H@Z; ImageCacheLock::ImageCacheLock(ImageCache *,RectT<IntegerTypes> const &,ChannelFormat,DeviceType,int)
0x1802251ab  mov     rdi, rax
0x1802251ae  mov     [rsp+1C8h+var_178], rax
0x1802251b3  xor     r9d, r9d; y2
0x1802251b6  xor     r8d, r8d; x2
0x1802251b9  xor     edx, edx; y1
0x1802251bb  xor     ecx, ecx; x1
0x1802251bd  call    cs:__imp_CreateRectRgn
0x1802251c3  mov     rsi, rax
0x1802251c6  mov     [rsp+1C8h+var_B8], rax
0x1802251ce  lea     rdx, [rsp+1C8h+hrgnSrc2]
0x1802251d3  mov     rcx, [rdi]
0x1802251d6  call    ?GetLockedCacheRegion@ImageCache@@AEAA?AVRegion@@AEBU?$RectT@UIntegerTypes@@@@@Z; ImageCache::GetLockedCacheRegion(RectT<IntegerTypes> const &)
0x1802251db  lea     rcx, [rdi+18h]; lprect
0x1802251df  call    cs:__imp_CreateRectRgnIndirect
0x1802251e5  mov     rbx, rax
0x1802251e8  mov     r9d, 4; iMode
0x1802251ee  mov     r8, [rsp+1C8h+hrgnSrc2]; hrgnSrc2
0x1802251f3  mov     rdx, rax; hrgnSrc1
0x1802251f6  mov     rcx, rax; hrgnDst
0x1802251f9  call    cs:__imp_CombineRgn
0x1802251ff  mov     r9d, 5; iMode
0x180225205  xor     r8d, r8d; hrgnSrc2
0x180225208  mov     rdx, rbx; hrgnSrc1
0x18022520b  mov     rcx, rsi; hrgnDst
0x18022520e  call    cs:__imp_CombineRgn
0x180225214  test    rbx, rbx
0x180225217  jz      short loc_180225222
0x180225219  mov     rcx, rbx; ho
0x18022521c  call    cs:__imp_DeleteObject
0x180225222  mov     rcx, [rsp+1C8h+hrgnSrc2]; ho
0x180225227  test    rcx, rcx
0x18022522a  jz      short loc_180225232
0x18022522c  call    cs:__imp_DeleteObject
0x180225232  mov     qword ptr [rsp+1C8h+rc.left], r14
0x18022523a  mov     qword ptr [rsp+1C8h+rc.right], r14
0x180225242  lea     rdx, [rsp+1C8h+rc]; lprc
0x18022524a  mov     rcx, rsi; hrgn
0x18022524d  call    cs:__imp_GetRgnBox
0x180225253  mov     eax, [rsp+1C8h+rc.right]
0x18022525a  cmp     [rsp+1C8h+rc.left], eax
0x180225261  jge     loc_180225D55
0x180225267  mov     eax, [rsp+1C8h+rc.bottom]
0x18022526e  cmp     [rsp+1C8h+rc.top], eax
0x180225275  jge     loc_180225D55
0x18022527b  mov     r8d, 6; int
0x180225281  mov     rdx, rsi; HRGN
0x180225284  lea     rcx, [rsp+1C8h+Block]; this
0x18022528c  call    ??0RegionRects@@QEAA@PEAUHRGN__@@H@Z; RegionRects::RegionRects(HRGN__ *,int)
0x180225291  nop
0x180225292  mov     rax, [rsp+1C8h+var_F0]
0x18022529a  mov     [rsp+1C8h+hrgnSrc2], rax
0x18022529f  mov     rcx, r14
0x1802252a2  mov     r8d, r14d
0x1802252a5  mov     r11d, 0FFFFFFFFh
0x1802252ab  cmp     r8d, eax
0x1802252ae  jge     short loc_180225327
0x1802252b0  test    r8d, r8d
0x1802252b3  js      loc_180225E59
0x1802252b9  movsxd  rdx, r8d
0x1802252bc  cmp     rdx, rax
0x1802252bf  jnb     loc_180225E63
0x1802252c5  shl     rdx, 4
0x1802252c9  add     rdx, [rsp+1C8h+Block]
0x1802252d1  movsxd  r10, dword ptr [rdx+8]
0x1802252d5  movsxd  rax, dword ptr [rdx]
0x1802252d8  sub     r10, rax
0x1802252db  lea     rax, [r15+r10]
0x1802252df  cmp     rax, r11
0x1802252e2  ja      loc_180225F47
0x1802252e8  movsxd  rax, dword ptr [rdx+4]
0x1802252ec  movsxd  r9, dword ptr [rdx+0Ch]
0x1802252f0  sub     r9, rax
0x1802252f3  lea     rax, [r9+r15]
0x1802252f7  cmp     rax, r11
0x1802252fa  ja      loc_180225F47
0x180225300  movsxd  rdx, r9d
0x180225303  movsxd  rax, r10d
0x180225306  imul    rdx, rax
0x18022530a  lea     rax, [r15+rdx]
0x18022530e  cmp     rax, r11
0x180225311  ja      loc_180225F47
0x180225317  movsxd  rax, edx
0x18022531a  add     rcx, rax
0x18022531d  inc     r8d
0x180225320  mov     rax, [rsp+1C8h+hrgnSrc2]
0x180225325  jmp     short loc_1802252AB
0x180225327  movsxd  rax, dword ptr [rsp+1C8h+var_138]
0x18022532f  movsxd  rbx, [rsp+1C8h+var_130]
0x180225337  sub     rbx, rax
0x18022533a  lea     rax, [r15+rbx]
0x18022533e  cmp     rax, r11
0x180225341  ja      loc_180225F47
0x180225347  movsxd  rax, dword ptr [rsp+1C8h+var_138+4]
0x18022534f  movsxd  r14, [rsp+1C8h+var_12C]
0x180225357  sub     r14, rax
0x18022535a  lea     rax, [r14+r15]
0x18022535e  cmp     rax, r11
0x180225361  ja      loc_180225F47
0x180225367  movsxd  r15, r14d
0x18022536a  movsxd  rax, ebx
0x18022536d  imul    r15, rax
0x180225371  mov     eax, 80000000h
0x180225376  add     rax, r15
0x180225379  cmp     rax, r11
0x18022537c  ja      loc_180225F47
0x180225382  movsxd  rdx, r15d
0x180225385  xorps   xmm0, xmm0
0x180225388  test    r15d, r15d
0x18022538b  js      short loc_180225394
0x18022538d  cvtsi2sd xmm0, rdx
0x180225392  jmp     short loc_1802253A9
0x180225394  mov     rax, rdx
0x180225397  shr     rax, 1
0x18022539a  and     edx, 1
0x18022539d  or      rax, rdx
0x1802253a0  cvtsi2sd xmm0, rax
0x1802253a5  addsd   xmm0, xmm0
0x1802253a9  mulsd   xmm0, cs:__real@3fe999999999999a
0x1802253b1  xorps   xmm1, xmm1
0x1802253b4  test    rcx, rcx
0x1802253b7  js      short loc_1802253C0
0x1802253b9  cvtsi2sd xmm1, rcx
0x1802253be  jmp     short loc_1802253D5
0x1802253c0  mov     rax, rcx
0x1802253c3  shr     rax, 1
0x1802253c6  and     ecx, 1
0x1802253c9  or      rax, rcx
0x1802253cc  cvtsi2sd xmm1, rax
0x1802253d1  addsd   xmm1, xmm1
0x1802253d5  comisd  xmm1, xmm0
0x1802253d9  jbe     loc_18022553F
0x1802253df  lea     rcx, [rsp+1C8h+var_178]
0x1802253e4  call    ?Release@?$Ptr@VImageCacheLock@@@Base@@QEAAXXZ; Base::Ptr<ImageCacheLock>::Release(void)
0x1802253e9  mov     [rsp+1C8h+var_180], 0
0x1802253f2  mov     rcx, [r12+80h]
0x1802253fa  mov     rax, [rcx]
0x1802253fd  mov     dword ptr [rsp+1C8h+hrgnSrc2], ebx
0x180225401  mov     dword ptr [rsp+1C8h+hrgnSrc2+4], r14d
0x180225406  lea     rdx, [rsp+1C8h+var_180]
0x18022540b  mov     [rsp+1C8h+var_1A0], rdx
0x180225410  movsd   [rsp+1C8h+var_1A8], xmm6
0x180225416  mov     r9, [rsp+1C8h+hrgnSrc2]
0x18022541b  mov     r8, [rsp+1C8h+var_138]
0x180225423  xor     edx, edx
0x180225425  mov     rax, [rax+0A0h]
0x18022542c  call    cs:__guard_dispatch_icall_fptr
0x180225432  cmp     eax, 8007000Eh
0x180225437  jz      loc_180225E7D
0x18022543d  cmp     eax, 86160210h
0x180225442  jz      loc_180225E7D
0x180225448  cmp     eax, 86170103h
0x18022544d  jz      loc_180225E7D
0x180225453  cmp     eax, 86180110h
0x180225458  jz      loc_180225E7D
0x18022545e  test    eax, eax
0x180225460  js      loc_180225E71
0x180225466  mov     ecx, 38h ; '8'; Size
0x18022546b  call    cs:__imp_malloc
0x180225471  mov     rcx, rax
0x180225474  test    rax, rax
0x180225477  jz      loc_180225E78
0x18022547d  mov     [rsp+1C8h+var_140], rcx
0x180225485  mov     eax, [rsp+1C8h+var_160]
  ... truncated ...
```
