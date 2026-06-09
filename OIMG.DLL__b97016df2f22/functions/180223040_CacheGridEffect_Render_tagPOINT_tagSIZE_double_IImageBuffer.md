# CacheGridEffect::Render(tagPOINT,tagSIZE,double,IImageBuffer * *)

- ea: `0x180223040`
- end: `0x180223db1`
- name: `?Render@CacheGridEffect@@UEAAJUtagPOINT@@UtagSIZE@@NPEAPEAUIImageBuffer@@@Z`
- size: `3441`
- prototype: `__int64 __fastcall(CacheGridEffect *__hidden this, struct tagPOINT, struct tagSIZE, double, struct IImageBuffer **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001db0c`
- `0x1801c64f4`
- `0x18022297c`
- `0x180222ab8`
- `0x180223040`
- `0x180223f50`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180223a1c`
- `OLEAUT32!__imp_VariantInit` at `0x180223a1c`
- `OLEAUT32!__imp_VariantClear` at `0x180223b0b`
- `OLEAUT32!__imp_VariantClear` at `0x180223b0b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802230c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802230c2`
- `GDI32!CombineRgn` at `0x18022396c`
- `GDI32!CombineRgn` at `0x1802239a0`
- `GDI32!CombineRgn` at `0x18022396c`
- `GDI32!CombineRgn` at `0x1802239a0`
- `GDI32!GetRgnBox` at `0x1802239d1`
- `GDI32!GetRgnBox` at `0x1802239d1`
- `GDI32!DeleteObject` at `0x18022397a`
- `GDI32!DeleteObject` at `0x1802239ae`
- `GDI32!DeleteObject` at `0x180223b1a`
- `GDI32!DeleteObject` at `0x18022397a`
- `GDI32!DeleteObject` at `0x1802239ae`
- `GDI32!DeleteObject` at `0x180223b1a`
- `GDI32!CreateRectRgnIndirect` at `0x18022393e`
- `GDI32!CreateRectRgnIndirect` at `0x180223954`
- `GDI32!CreateRectRgnIndirect` at `0x180223988`
- `GDI32!CreateRectRgnIndirect` at `0x18022393e`
- `GDI32!CreateRectRgnIndirect` at `0x180223954`
- `GDI32!CreateRectRgnIndirect` at `0x180223988`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CacheGridEffect::Render(
        CacheGridEffect *this,
        struct tagPOINT a2,
        struct tagSIZE a3,
        double a4,
        struct IImageBuffer **a5)
{
  struct IImageBuffer **v6; // rbx
  _QWORD *v7; // rbx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  LONG left; // edi
  int top; // r9d
  LONG right; // ecx
  int bottom; // eax
  struct tagPOINT v17; // r8
  __int64 v18; // rsi
  __int64 v19; // rbx
  int v20; // ecx
  int v21; // r12d
  signed int v22; // r10d
  signed int v23; // ebx
  signed int v24; // eax
  char v25; // r12
  bool v26; // cc
  int v27; // edi
  __int64 y; // r9
  int v29; // r14d
  LONG v30; // ecx
  LONG v31; // r8d
  LONG v32; // eax
  LONG v33; // r9d
  char Tile; // r13
  __int64 v35; // r10
  __int64 (__fastcall *v36)(__int64, _QWORD, _QWORD, unsigned __int64, _QWORD, struct IImageBuffer **); // r11
  __int64 v37; // r8
  __int64 v38; // rdx
  int v39; // eax
  struct IImageBuffer *v40; // r10
  struct IImageBuffer *v41; // rbx
  struct IImageBuffer *v42; // rcx
  int v43; // eax
  __int64 v44; // r10
  __int64 (__fastcall *v45)(__int64, _QWORD, unsigned __int64, _QWORD, __int64, __int64, _DWORD, struct IImageBuffer **); // rbx
  __int64 v46; // r8
  __int64 v47; // rdx
  int v48; // eax
  HRGN v49; // rbx
  HRGN v50; // rsi
  HRGN v51; // rsi
  __int64 (__fastcall *v52)(struct IImageBuffer *, _QWORD, unsigned __int64, VARIANTARG *); // r10
  __int64 v53; // r8
  __int64 v54; // rdx
  int v55; // eax
  __int64 (__fastcall *v56)(struct IImageBuffer *, struct IImageBuffer *, _QWORD, unsigned __int64); // rbx
  __int64 v57; // r11
  __int64 v58; // r9
  int v59; // eax
  bool v60; // al
  int v61; // eax
  __int64 result; // rax
  __int64 v63; // [rsp+20h] [rbp-1C8h]
  __int64 v64; // [rsp+28h] [rbp-1C0h]
  char v65; // [rsp+50h] [rbp-198h]
  struct IImageBuffer *v66; // [rsp+58h] [rbp-190h] BYREF
  struct IImageBuffer *v67; // [rsp+60h] [rbp-188h] BYREF
  unsigned __int64 v68; // [rsp+68h] [rbp-180h] BYREF
  struct tagPOINT v69; // [rsp+70h] [rbp-178h] BYREF
  HRGN v70; // [rsp+78h] [rbp-170h] BYREF
  int v71; // [rsp+80h] [rbp-168h]
  int v72; // [rsp+84h] [rbp-164h] BYREF
  unsigned int v73; // [rsp+88h] [rbp-160h] BYREF
  __int64 v74; // [rsp+90h] [rbp-158h] BYREF
  __int64 v75; // [rsp+98h] [rbp-150h] BYREF
  __int64 v76; // [rsp+A0h] [rbp-148h]
  unsigned __int64 v77; // [rsp+A8h] [rbp-140h]
  unsigned __int64 v78; // [rsp+B0h] [rbp-138h]
  unsigned __int64 v79; // [rsp+B8h] [rbp-130h]
  unsigned __int64 v80; // [rsp+C0h] [rbp-128h]
  struct IImageBuffer **v81; // [rsp+C8h] [rbp-120h]
  _DWORD v82[4]; // [rsp+D0h] [rbp-118h] BYREF
  int v83; // [rsp+E0h] [rbp-108h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-100h]
  __int64 v85; // [rsp+F0h] [rbp-F8h]
  VARIANTARG pvarg; // [rsp+F8h] [rbp-F0h] BYREF
  VARIANTARG v87; // [rsp+110h] [rbp-D8h] BYREF
  char v88[16]; // [rsp+130h] [rbp-B8h] BYREF
  _DWORD v89[4]; // [rsp+140h] [rbp-A8h] BYREF
  RECT v90; // [rsp+150h] [rbp-98h] BYREF
  RECT rect; // [rsp+160h] [rbp-88h] BYREF
  RECT v92; // [rsp+170h] [rbp-78h] BYREF
  struct tagRECT rc; // [rsp+180h] [rbp-68h] BYREF

  try
  {
    v6 = a5;
    v81 = a5;
    v69 = a2;
    v68 = (unsigned __int64)a3;
    if ( !a5 )
      ATL::BaseAtlThrow(-2147467261);
    if ( *((double *)this + 19) != a4 )
    {
      v7 = (_QWORD *)*((_QWORD *)this + 18);
      if ( *v7 )
      {
        ATL::CAtlArray<ImageBufferCacheRecord,ATL::CElementTraits<ImageBufferCacheRecord>>::CallDestructors(*v7, v7[1]);
        free((void *)*v7);
        *v7 = 0;
      }
      v7[1] = 0;
      v7[2] = 0;
      *((double *)this + 19) = a4;
      v6 = v81;
    }
    v72 = 0;
    v73 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, int *, unsigned int *))(**((_QWORD **)this + 16) + 240LL))(
           *((_QWORD *)this + 16),
           &v72,
           &v73);
    if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
      ATL::BaseAtlThrow(v8);
    if ( v8 < 0 )
      ATL::BaseAtlThrow(v8);
    v9 = (*(__int64 (__fastcall **)(CacheGridEffect *, _QWORD, _QWORD, struct tagPOINT *, unsigned __int64 *, _QWORD))(*(_QWORD *)this + 72LL))(
           this,
           0,
           0,
           &v69,
           &v68,
           *(_QWORD *)&a4);
    if ( v9 == -2147024882 || v9 == -2045378032 || v9 == -2045312765 || v9 == -2045247216 )
      ATL::BaseAtlThrow(v9);
    if ( v9 < 0 )
      ATL::BaseAtlThrow(v9);
    *(struct tagPOINT *)&v90.left = v69;
    if ( (unsigned __int64)(v69.x + (__int64)(int)v68 + 0x80000000LL) > 0xFFFFFFFF )
      goto LABEL_185;
    v90.right = v69.x + v68;
    if ( (unsigned __int64)(v69.y + (__int64)SHIDWORD(v68) + 0x80000000LL) > 0xFFFFFFFF )
      goto LABEL_185;
    v90.bottom = v69.y + HIDWORD(v68);
    v74 = 0;
    v75 = 0;
    v10 = (*(__int64 (__fastcall **)(CacheGridEffect *, __int64, _QWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)this + 72LL))(
            this,
            1,
            0,
            &v74,
            &v75,
            *(_QWORD *)&a4);
    if ( v10 == -2147024882 || v10 == -2045378032 || v10 == -2045312765 || v10 == -2045247216 )
      ATL::BaseAtlThrow(v10);
    if ( v10 < 0 )
      ATL::BaseAtlThrow(v10);
    v76 = v74;
    v11 = (int)v74 + (__int64)(int)v75;
    v84 = v11;
    if ( (unsigned __int64)(v11 + 0x80000000LL) > 0xFFFFFFFF )
      goto LABEL_185;
    v12 = SHIDWORD(v74) + (__int64)SHIDWORD(v75);
    v85 = v12;
    if ( (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF )
      goto LABEL_185;
    left = v90.left;
    if ( v90.left <= (int)v74 )
      left = v74;
    v90.left = left;
    top = v90.top;
    if ( v90.top <= SHIDWORD(v74) )
      top = HIDWORD(v74);
    v90.top = top;
    right = v90.right;
    if ( v90.right >= (int)v11 )
      right = v74 + v75;
    v90.right = right;
    bottom = v90.bottom;
    if ( v90.bottom >= (int)v12 )
      bottom = HIDWORD(v74) + HIDWORD(v75);
    v90.bottom = bottom;
    if ( left > right || top > bottom )
    {
      bottom = 0;
      v90.bottom = 0;
      right = 0;
      v90.right = 0;
      top = 0;
      *(_QWORD *)&v90.left = 0;
      left = 0;
    }
    if ( left >= right || top >= bottom )
    {
      *v6 = 0;
      return 0;
    }
    v17 = *(struct tagPOINT *)&v90.left;
    v69 = *(struct tagPOINT *)&v90.left;
    v18 = bottom - (__int64)top;
    if ( (unsigned __int64)(v18 + 0x80000000LL) > 0xFFFFFFFF
      || (v19 = right - (__int64)left, (unsigned __int64)(v19 + 0x80000000LL) > 0xFFFFFFFF) )
    {
LABEL_185:
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    v68 = __PAIR64__(v18, v19);
    v20 = right - left;
    v21 = 0;
    v71 = 0;
    if ( left % 512 )
    {
      v22 = (((left >> 31) & 0x1FF) + left) & 0xFFFFFE00;
      if ( left <= 0 )
        v22 -= 512;
    }
    else
    {
      v22 = left;
    }
    v23 = left + v19;
    while ( v22 < v23 && v21 < 2 )
    {
      v24 = top;
      if ( top % 512 )
      {
        v24 = (((top >> 31) & 0x1FF) + top) & 0xFFFFFE00;
        if ( top <= 0 )
          v24 -= 512;
      }
      while ( v24 < (int)v18 + top && v21 < 2 )
      {
        v71 = ++v21;
        v24 += 512;
      }
      v22 += 512;
    }
    v67 = 0;
    v25 = 0;
    v65 = 0;
    if ( left % 512 )
    {
      v26 = left <= 0;
      v27 = ((left >> 31) & 0x1FF) + left;
      if ( v26 )
        left = (v27 & 0xFFFFFE00) - 512;
      else
        left = v27 & 0xFFFFFE00;
    }
    y = (unsigned int)v69.y;
    while ( left < v17.x + v20 )
    {
      if ( (int)y % 512 )
      {
        v29 = (y + (((int)y >> 31) & 0x1FF)) & 0xFFFFFE00;
        if ( (int)y <= 0 )
          v29 -= 512;
      }
      else
      {
        v29 = y;
      }
      while ( v29 < (int)y + HIDWORD(v68) )
      {
        v82[0] = left;
        v82[1] = v29;
        v82[2] = left + 512;
        v82[3] = v29 + 512;
        v30 = v76;
        if ( (int)v76 <= left )
          v30 = left;
        rect.left = v30;
        v31 = HIDWORD(v76);
        if ( SHIDWORD(v76) <= v29 )
          v31 = v29;
        rect.top = v31;
        v32 = v84;
        if ( (int)v84 >= left + 512 )
          v32 = left + 512;
        rect.right = v32;
        v33 = v85;
        if ( (int)v85 >= v29 + 512 )
          v33 = v29 + 512;
        rect.bottom = v33;
        if ( v30 > v32 || v31 > v33 )
        {
          *(_QWORD *)&rect.right = 0;
          *(_QWORD *)&rect.left = 0;
        }
        v66 = 0;
        Tile = ImageCacheGrid::FindTile(*((_QWORD *)this + 18), v82, &v66, &v92);
        if ( !Tile )
        {
          v35 = *((_QWORD *)this + 16);
          v36 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int64, _QWORD, struct IImageBuffer **))(*(_QWORD *)v35 + 160LL);
          v37 = rect.bottom - (__int64)rect.top;
          if ( (unsigned __int64)(v37 + 0x80000000LL) > 0xFFFFFFFF
            || (v38 = rect.right - (__int64)rect.left, (unsigned __int64)(v38 + 0x80000000LL) > 0xFFFFFFFF) )
          {
LABEL_180:
            safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
          }
          v77 = __PAIR64__(v37, v38);
          v39 = v36(v35, 0, *(_QWORD *)&rect.left, __PAIR64__(v37, v38), *(_QWORD *)&a4, &v66);
          if ( v39 == -2147024882 || v39 == -2045378032 || v39 == -2045312765 || v39 == -2045247216 )
            ATL::BaseAtlThrow(v39);
          if ( v39 < 0 )
            ATL::BaseAtlThrow(v39);
          v92 = *(RECT *)CacheGridEffect::GetRenderedRect(v88, v66);
        }
        if ( v71 == 1
          && v90.left == v92.left
          && v90.top == v92.top
          && v90.right == v92.right
          && v90.bottom == v92.bottom )
        {
          v40 = v66;
          if ( v67 != v66 )
          {
            v41 = v66;
            if ( v66 )
            {
              (*(void (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v66 + 8LL))(v66);
              v40 = v66;
            }
            v42 = v67;
            v67 = v41;
            if ( v42 )
            {
              (*(void (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v42 + 16LL))(v42);
              v40 = v66;
            }
          }
          v65 = 1;
        }
        else
        {
          if ( !v67 )
          {
            v44 = *((_QWORD *)this + 16);
            v45 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64, _QWORD, __int64, __int64, _DWORD, struct IImageBuffer **))(*(_QWORD *)v44 + 248LL);
            v46 = v90.bottom - (__int64)v90.top;
            if ( (unsigned __int64)(v46 + 0x80000000LL) > 0xFFFFFFFF )
              goto LABEL_180;
            v47 = v90.right - (__int64)v90.left;
            if ( (unsigned __int64)(v47 + 0x80000000LL) > 0xFFFFFFFF )
              goto LABEL_180;
            v78 = __PAIR64__(v46, v47);
            LODWORD(v64) = 4;
            LODWORD(v63) = v72;
            v48 = v45(v44, *(_QWORD *)&v90.left, __PAIR64__(v46, v47), v73, v63, v64, 0, &v67);
            if ( v48 == -2147024882 || v48 == -2045378032 || v48 == -2045312765 || v48 == -2045247216 )
              ATL::BaseAtlThrow(v48);
            if ( v48 < 0 )
              ATL::BaseAtlThrow(v48);
          }
          if ( rect.left < rect.right
            && rect.top < rect.bottom
            && (v92.left > rect.left || v92.right < rect.right || v92.top > rect.top || v92.bottom < rect.bottom) )
          {
            v49 = CreateRectRgnIndirect(&rect);
            v70 = v49;
            v50 = CreateRectRgnIndirect(&v92);
            CombineRgn(v49, v49, v50, 4);
            if ( v50 )
              DeleteObject(v50);
            v51 = CreateRectRgnIndirect(&v90);
            CombineRgn(v49, v49, v51, 1);
            if ( v51 )
              DeleteObject(v51);
            *(_QWORD *)&rc.left = 0;
            *(_QWORD *)&rc.right = 0;
            GetRgnBox(v49, &rc);
            if ( rc.left < rc.right && rc.top < rc.bottom )
            {
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              v52 = *(__int64 (__fastcall **)(struct IImageBuffer *, _QWORD, unsigned __int64, VARIANTARG *))(*(_QWORD *)v67 + 96LL);
              v53 = rc.bottom - (__int64)rc.top;
              if ( (unsigned __int64)(v53 + 0x80000000LL) > 0xFFFFFFFF
                || (v54 = rc.right - (__int64)rc.left, (unsigned __int64)(v54 + 0x80000000LL) > 0xFFFFFFFF) )
              {
                safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
              }
              v79 = __PAIR64__(v53, v54);
              v87 = pvarg;
              v55 = v52(v67, *(_QWORD *)&rc.left, __PAIR64__(v53, v54), &v87);
              if ( v55 == -2147024882 || v55 == -2045378032 || v55 == -2045312765 || v55 == -2045247216 )
                ATL::BaseAtlThrow(v55);
              if ( v55 < 0 )
                ATL::BaseAtlThrow(v55);
              v25 = 1;
              VariantClear(&pvarg);
            }
            if ( v49 )
              DeleteObject(v49);
          }
          v40 = v66;
          if ( v66 )
          {
            v56 = *(__int64 (__fastcall **)(struct IImageBuffer *, struct IImageBuffer *, _QWORD, unsigned __int64))(*(_QWORD *)v67 + 112LL);
            v57 = v92.bottom - (__int64)v92.top;
            if ( (unsigned __int64)(v57 + 0x80000000LL) > 0xFFFFFFFF )
              goto LABEL_180;
            v58 = v92.right - (__int64)v92.left;
            if ( (unsigned __int64)(v58 + 0x80000000LL) > 0xFFFFFFFF )
              goto LABEL_180;
            v80 = __PAIR64__(v57, v58);
            v59 = v56(v67, v66, *(_QWORD *)&v92.left, __PAIR64__(v57, v58));
            if ( v59 == -2147024882 || v59 == -2045378032 || v59 == -2045312765 || v59 == -2045247216 )
              ATL::BaseAtlThrow(v59);
            if ( v59 < 0 )
              ATL::BaseAtlThrow(v59);
            v40 = v66;
          }
        }
        if ( !Tile )
        {
          ImageCacheGrid::AddTile(*((_QWORD *)this + 18), v82, v40, &v92);
          v40 = v66;
        }
        if ( v25 )
          goto LABEL_149;
        if ( v40 )
        {
          LODWORD(v70) = 0;
          v43 = (*(__int64 (__fastcall **)(struct IImageBuffer *, HRGN *))(*(_QWORD *)v40 + 72LL))(v40, &v70);
          if ( v43 == -2147024882 || v43 == -2045378032 || v43 == -2045312765 || v43 == -2045247216 )
            ATL::BaseAtlThrow(v43);
          if ( v43 < 0 )
            ATL::BaseAtlThrow(v43);
          v60 = (_DWORD)v70 == 0;
          v40 = v66;
        }
        else
        {
          v60 = 0;
        }
        v25 = 0;
        if ( v60 )
LABEL_149:
          v25 = 1;
        if ( v40 )
          (*(void (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v40 + 16LL))(v40);
        v29 += 512;
        v17 = v69;
        y = (unsigned int)v69.y;
        v20 = v68;
      }
      left += 512;
    }
    if ( !v25 && !v65 )
    {
      v61 = (*(__int64 (__fastcall **)(struct IImageBuffer *, __int64, struct tagPOINT, __int64))(*(_QWORD *)v67 + 80LL))(
              v67,
              1,
              v17,
              y);
      if ( v61 == -2147024882 || v61 == -2045378032 || v61 == -2045312765 || v61 == -2045247216 )
        ATL::BaseAtlThrow(v61);
      if ( v61 < 0 )
        ATL::BaseAtlThrow(v61);
    }
    *v81 = v67;
    result = 0;
  }
  catch ( Base::Exception v89 )
  {
    LODWORD(v70) = v89[2];
    goto LABEL_163;
  }
  catch ( long v83 )
  {
    LODWORD(v70) = v83;
LABEL_163:
    result = (unsigned int)v70;
    if ( (_WORD)v70 == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x180223040  mov     rax, rsp
0x180223043  push    rbx
0x180223044  push    rsi
0x180223045  push    rdi
0x180223046  push    r12
0x180223048  push    r13
0x18022304a  push    r14
0x18022304c  push    r15
0x18022304e  sub     rsp, 1B0h
0x180223055  movaps  xmmword ptr [rax-48h], xmm6
0x180223059  mov     rax, cs:__security_cookie
0x180223060  xor     rax, rsp
0x180223063  mov     [rsp+1E8h+var_58], rax
0x18022306b  movaps  xmm6, xmm3
0x18022306e  mov     r15, rcx
0x180223071  mov     rbx, [rsp+1E8h+arg_20]
0x180223079  mov     [rsp+1E8h+var_120], rbx
0x180223081  mov     [rsp+1E8h+var_178], rdx
0x180223086  mov     [rsp+1E8h+var_180], r8
0x18022308b  xor     r14d, r14d
0x18022308e  test    rbx, rbx
0x180223091  jz      loc_180223CF6
0x180223097  movsd   xmm0, qword ptr [rcx+98h]
0x18022309f  ucomisd xmm0, xmm6
0x1802230a3  jp      short loc_1802230A7
0x1802230a5  jz      short loc_1802230E4
0x1802230a7  mov     rbx, [rcx+90h]
0x1802230ae  mov     rcx, [rbx]
0x1802230b1  test    rcx, rcx
0x1802230b4  jz      short loc_1802230CB
0x1802230b6  mov     rdx, [rbx+8]
0x1802230ba  call    ?CallDestructors@?$CAtlArray@UImageBufferCacheRecord@@V?$CElementTraits@UImageBufferCacheRecord@@@ATL@@@ATL@@CAXPEAUImageBufferCacheRecord@@_K@Z; ATL::CAtlArray<ImageBufferCacheRecord,ATL::CElementTraits<ImageBufferCacheRecord>>::CallDestructors(ImageBufferCacheRecord *,unsigned __int64)
0x1802230bf  mov     rcx, [rbx]; Block
0x1802230c2  call    cs:__imp_free
0x1802230c8  mov     [rbx], r14
0x1802230cb  mov     [rbx+8], r14
0x1802230cf  mov     [rbx+10h], r14
0x1802230d3  movsd   qword ptr [r15+98h], xmm6
0x1802230dc  mov     rbx, [rsp+1E8h+var_120]
0x1802230e4  mov     [rsp+1E8h+var_164], r14d
0x1802230ec  mov     [rsp+1E8h+var_160], r14d
0x1802230f4  mov     rcx, [r15+80h]
0x1802230fb  mov     rax, [rcx]
0x1802230fe  lea     r8, [rsp+1E8h+var_160]
0x180223106  lea     rdx, [rsp+1E8h+var_164]
0x18022310e  mov     rax, [rax+0F0h]
0x180223115  call    cs:__guard_dispatch_icall_fptr
0x18022311b  mov     edi, 8007000Eh
0x180223120  cmp     eax, edi
0x180223122  jz      loc_180223DA7
0x180223128  mov     esi, 86160210h
0x18022312d  cmp     eax, esi
0x18022312f  jz      loc_180223DA7
0x180223135  mov     r12d, 86170103h
0x18022313b  cmp     eax, r12d
0x18022313e  jz      loc_180223DA7
0x180223144  mov     r13d, 86180110h
0x18022314a  cmp     eax, r13d
0x18022314d  jz      loc_180223DA7
0x180223153  test    eax, eax
0x180223155  js      loc_180223D00
0x18022315b  mov     rax, [r15]
0x18022315e  movsd   [rsp+1E8h+var_1C0], xmm6
0x180223164  lea     rcx, [rsp+1E8h+var_180]
0x180223169  mov     [rsp+1E8h+var_1C8], rcx
0x18022316e  lea     r9, [rsp+1E8h+var_178]
0x180223173  xor     r8d, r8d
0x180223176  xor     edx, edx
0x180223178  mov     rcx, r15
0x18022317b  mov     rax, [rax+48h]
0x18022317f  call    cs:__guard_dispatch_icall_fptr
0x180223185  cmp     eax, edi
0x180223187  jz      loc_180223DA0
0x18022318d  cmp     eax, esi
0x18022318f  jz      loc_180223DA0
0x180223195  cmp     eax, r12d
0x180223198  jz      loc_180223DA0
0x18022319e  cmp     eax, r13d
0x1802231a1  jz      loc_180223DA0
0x1802231a7  test    eax, eax
0x1802231a9  js      loc_180223D07
0x1802231af  mov     rax, [rsp+1E8h+var_178]
0x1802231b4  mov     [rsp+1E8h+var_98.left], eax
0x1802231bb  movsxd  r8, dword ptr [rsp+1E8h+var_178+4]
0x1802231c0  mov     [rsp+1E8h+var_98.top], r8d
0x1802231c8  movsxd  rdx, dword ptr [rsp+1E8h+var_180]
0x1802231cd  movsxd  rcx, eax
0x1802231d0  add     rdx, rcx
0x1802231d3  mov     r12d, 80000000h
0x1802231d9  lea     rax, [rdx+r12]
0x1802231dd  mov     r13d, 0FFFFFFFFh
0x1802231e3  cmp     rax, r13
0x1802231e6  ja      loc_180223D9A
0x1802231ec  mov     [rsp+1E8h+var_98.right], edx
0x1802231f3  movsxd  rcx, dword ptr [rsp+1E8h+var_180+4]
0x1802231f8  add     rcx, r8
0x1802231fb  lea     rax, [r12+rcx]
0x1802231ff  cmp     rax, r13
0x180223202  ja      loc_180223D9A
0x180223208  mov     [rsp+1E8h+var_98.bottom], ecx
0x18022320f  mov     [rsp+1E8h+var_158], r14
0x180223217  mov     [rsp+1E8h+var_150], r14
0x18022321f  mov     rax, [r15]
0x180223222  movsd   [rsp+1E8h+var_1C0], xmm6
0x180223228  lea     rcx, [rsp+1E8h+var_150]
0x180223230  mov     [rsp+1E8h+var_1C8], rcx
0x180223235  lea     r9, [rsp+1E8h+var_158]
0x18022323d  xor     r8d, r8d
0x180223240  lea     edx, [r8+1]
0x180223244  mov     rcx, r15
0x180223247  mov     rax, [rax+48h]
0x18022324b  call    cs:__guard_dispatch_icall_fptr
0x180223251  cmp     eax, edi
0x180223253  jz      loc_180223D93
0x180223259  cmp     eax, esi
0x18022325b  jz      loc_180223D93
0x180223261  cmp     eax, 86170103h
0x180223266  jz      loc_180223D93
0x18022326c  cmp     eax, 86180110h
0x180223271  jz      loc_180223D93
0x180223277  test    eax, eax
0x180223279  js      loc_180223D0E
0x18022327f  movsxd  r9, dword ptr [rsp+1E8h+var_158]
0x180223287  mov     dword ptr [rsp+1E8h+var_148], r9d
0x18022328f  movsxd  rcx, dword ptr [rsp+1E8h+var_158+4]
0x180223297  mov     dword ptr [rsp+1E8h+var_148+4], ecx
0x18022329e  movsxd  rdx, dword ptr [rsp+1E8h+var_150]
0x1802232a6  add     rdx, r9
0x1802232a9  mov     [rsp+1E8h+var_100], rdx
0x1802232b1  lea     rax, [rdx+r12]
0x1802232b5  cmp     rax, r13
0x1802232b8  ja      loc_180223D9A
0x1802232be  movsxd  r8, dword ptr [rsp+1E8h+var_150+4]
0x1802232c6  add     r8, rcx
0x1802232c9  mov     [rsp+1E8h+var_F8], r8
0x1802232d1  lea     rax, [r12+r8]
0x1802232d5  cmp     rax, r13
0x1802232d8  ja      loc_180223D9A
0x1802232de  mov     edi, [rsp+1E8h+var_98.left]
0x1802232e5  cmp     edi, r9d
0x1802232e8  cmovle  edi, r9d
0x1802232ec  mov     [rsp+1E8h+var_98.left], edi
0x1802232f3  mov     r9d, [rsp+1E8h+var_98.top]
0x1802232fb  cmp     r9d, ecx
0x1802232fe  cmovle  r9d, ecx
0x180223302  mov     [rsp+1E8h+var_98.top], r9d
0x18022330a  mov     ecx, [rsp+1E8h+var_98.right]
0x180223311  cmp     ecx, edx
0x180223313  cmovge  ecx, edx
0x180223316  mov     [rsp+1E8h+var_98.right], ecx
0x18022331d  mov     eax, [rsp+1E8h+var_98.bottom]
0x180223324  cmp     eax, r8d
0x180223327  cmovge  eax, r8d
0x18022332b  mov     [rsp+1E8h+var_98.bottom], eax
0x180223332  cmp     edi, ecx
0x180223334  jg      short loc_18022333B
0x180223336  cmp     r9d, eax
0x180223339  jle     short loc_18022335D
0x18022333b  mov     eax, r14d
0x18022333e  mov     [rsp+1E8h+var_98.bottom], eax
0x180223345  mov     ecx, r14d
0x180223348  mov     [rsp+1E8h+var_98.right], ecx
0x18022334f  mov     r9d, r14d
0x180223352  mov     qword ptr [rsp+1E8h+var_98.left], r14
0x18022335a  mov     edi, r14d
0x18022335d  cmp     edi, ecx
0x18022335f  jge     loc_180223CB4
0x180223365  cmp     r9d, eax
0x180223368  jge     loc_180223CB4
0x18022336e  mov     r8, qword ptr [rsp+1E8h+var_98.left]
0x180223376  mov     [rsp+1E8h+var_178], r8
0x18022337b  movsxd  rsi, eax
0x18022337e  movsxd  rax, r9d
0x180223381  sub     rsi, rax
0x180223384  lea     rax, [rsi+r12]
0x180223388  cmp     rax, r13
0x18022338b  ja      loc_180223D9A
0x180223391  movsxd  rax, edi
0x180223394  movsxd  rbx, ecx
0x180223397  sub     rbx, rax
0x18022339a  lea     rax, [r12+rbx]
0x18022339e  cmp     rax, r13
0x1802233a1  ja      loc_180223D9A
0x1802233a7  mov     dword ptr [rsp+1E8h+var_180], ebx
0x1802233ab  mov     dword ptr [rsp+1E8h+var_180+4], esi
0x1802233af  mov     rcx, [rsp+1E8h+var_180]
0x1802233b4  mov     [rsp+1E8h+var_180], rcx
0x1802233b9  mov     r12d, r14d
0x1802233bc  mov     [rsp+1E8h+var_168], r14d
0x1802233c4  mov     r11d, edi
0x1802233c7  and     r11d, 800001FFh
0x1802233ce  jge     short loc_1802233DD
0x1802233d0  dec     r11d
0x1802233d3  or      r11d, 0FFFFFE00h
0x1802233da  inc     r11d
0x1802233dd  mov     r14d, 1FFh
0x1802233e3  lea     r13d, [r14+1]
0x1802233e7  test    r11d, r11d
0x1802233ea  jnz     short loc_1802233F1
0x1802233ec  mov     r10d, edi
0x1802233ef  jmp     short loc_180223409
0x1802233f1  mov     eax, edi
0x1802233f3  cdq
0x1802233f4  and     edx, r14d
0x1802233f7  lea     r10d, [rdx+rax]
0x1802233fb  and     r10d, 0FFFFFE00h
0x180223402  test    edi, edi
0x180223404  jg      short loc_180223409
0x180223406  sub     r10d, r13d
0x180223409  add     ebx, edi
0x18022340b  jmp     short loc_180223461
0x18022340d  cmp     r12d, 2
0x180223411  jge     short loc_180223466
0x180223413  mov     eax, r9d
0x180223416  and     eax, 800001FFh
0x18022341b  jge     short loc_180223426
0x18022341d  dec     eax
0x18022341f  or      eax, 0FFFFFE00h
0x180223424  inc     eax
0x180223426  test    eax, eax
0x180223428  mov     eax, r9d
0x18022342b  jz      short loc_180223440
0x18022342d  cdq
0x18022342e  and     edx, r14d
0x180223431  add     eax, edx
0x180223433  and     eax, 0FFFFFE00h
0x180223438  test    r9d, r9d
0x18022343b  jg      short loc_180223440
0x18022343d  sub     eax, r13d
0x180223440  lea     edx, [rsi+r9]
0x180223444  jmp     short loc_18022345A
0x180223446  cmp     r12d, 2
0x18022344a  jge     short loc_18022345E
0x18022344c  inc     r12d
0x18022344f  mov     [rsp+1E8h+var_168], r12d
0x180223457  add     eax, r13d
0x18022345a  cmp     eax, edx
0x18022345c  jl      short loc_180223446
0x18022345e  add     r10d, r13d
0x180223461  cmp     r10d, ebx
0x180223464  jl      short loc_18022340D
0x180223466  xor     esi, esi
0x180223468  mov     [rsp+1E8h+var_188], rsi
0x18022346d  mov     r12b, sil
0x180223470  mov     [rsp+1E8h+var_198], sil
0x180223475  test    r11d, r11d
0x180223478  jz      short loc_180223498
0x18022347a  mov     eax, edi
0x18022347c  cdq
0x18022347d  and     edx, r14d
0x180223480  test    edi, edi
0x180223482  lea     edi, [rdx+rax]
0x180223485  jle     short loc_18022348F
0x180223487  and     edi, 0FFFFFE00h
0x18022348d  jmp     short loc_180223498
0x18022348f  and     edi, 0FFFFFE00h
0x180223495  sub     edi, r13d
0x180223498  mov     r9d, dword ptr [rsp+1E8h+var_178+4]
0x18022349d  lea     eax, [r8+rcx]
0x1802234a1  cmp     edi, eax
0x1802234a3  jge     loc_180223C49
0x1802234a9  mov     eax, r9d
0x1802234ac  and     eax, 800001FFh
0x1802234b1  jge     short loc_1802234BC
0x1802234b3  dec     eax
0x1802234b5  or      eax, 0FFFFFE00h
0x1802234ba  inc     eax
0x1802234bc  test    eax, eax
0x1802234be  jnz     short loc_1802234C5
0x1802234c0  mov     r14d, r9d
0x1802234c3  jmp     short loc_1802234DE
0x1802234c5  mov     eax, r9d
0x1802234c8  cdq
0x1802234c9  and     r14d, edx
0x1802234cc  add     r14d, eax
0x1802234cf  and     r14d, 0FFFFFE00h
0x1802234d6  test    r9d, r9d
0x1802234d9  jg      short loc_1802234DE
0x1802234db  sub     r14d, r13d
0x1802234de  lea     r10d, [rdi+200h]
0x1802234e5  mov     edx, dword ptr [rsp+1E8h+var_180+4]
0x1802234e9  add     edx, r9d
0x1802234ec  cmp     r14d, edx
0x1802234ef  jge     loc_180223C3B
0x1802234f5  mov     [rsp+1E8h+var_118], edi
0x1802234fc  mov     [rsp+1E8h+var_114], r14d
0x180223504  mov     [rsp+1E8h+var_110], r10d
0x18022350c  lea     edx, [r14+200h]
0x180223513  mov     [rsp+1E8h+var_10C], edx
0x18022351a  mov     ecx, dword ptr [rsp+1E8h+var_148]
0x180223521  cmp     ecx, edi
0x180223523  cmovle  ecx, edi
0x180223526  mov     [rsp+1E8h+rect.left], ecx
0x18022352d  mov     r8d, dword ptr [rsp+1E8h+var_148+4]
0x180223535  cmp     r8d, r14d
0x180223538  cmovle  r8d, r14d
0x18022353c  mov     [rsp+1E8h+rect.top], r8d
0x180223544  mov     r9, [rsp+1E8h+var_100]
0x18022354c  mov     eax, r9d
0x18022354f  cmp     r9d, r10d
  ... truncated ...
```
