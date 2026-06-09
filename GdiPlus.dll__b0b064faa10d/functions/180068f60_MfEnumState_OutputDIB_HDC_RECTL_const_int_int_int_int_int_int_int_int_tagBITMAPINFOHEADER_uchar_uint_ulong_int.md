# MfEnumState::OutputDIB(HDC__ *,_RECTL const *,int,int,int,int,int,int,int,int,tagBITMAPINFOHEADER *,uchar *,uint,ulong,int)

- ea: `0x180068f60`
- end: `0x180069a54`
- name: `?OutputDIB@MfEnumState@@IEAAXPEAUHDC__@@PEBU_RECTL@@HHHHHHHHPEFAUtagBITMAPINFOHEADER@@PEAEIKH@Z`
- size: `2804`
- prototype: `void(MfEnumState *__hidden this, HDC, const struct _RECTL *, int, int, int, int, int, int, int, int, struct tagBITMAPINFOHEADER *, unsigned __int8 *, unsigned int, unsigned int, int)`
- caller_count: `5`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x18006bc18`
- `0x1801288f0`
- `0x180128d10`
- `0x180129168`
- `0x18012a95c`

## callees

- `0x1800067bc`
- `0x180009eb8`
- `0x18000c84c`
- `0x18001196c`
- `0x18001ec80`
- `0x180023ca4`
- `0x18002739c`
- `0x18003d19c`
- `0x180041e78`
- `0x18005e5c0`
- `0x180068f60`
- `0x180069a5c`
- `0x18006a7dc`
- `0x18006a86c`
- `0x18008e8c0`
- `0x180099e90`
- `0x180099ee0`
- `0x1800fe680`
- `0x180115cf0`
- `0x180129b24`
- `0x18013cb34`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800692ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180069396`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800692ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180069396`
- `GDI32!SetStretchBltMode` at `0x1800691dc`
- `GDI32!SetStretchBltMode` at `0x1800691dc`
- `GDI32!StretchDIBits` at `0x180069246`
- `GDI32!StretchDIBits` at `0x180069246`
- `GDI32!SetBkColor` at `0x180069609`
- `GDI32!SetBkColor` at `0x180069a25`
- `GDI32!SetBkColor` at `0x180069609`
- `GDI32!SetBkColor` at `0x180069a25`
- `GDI32!SetTextColor` at `0x18006961c`
- `GDI32!SetTextColor` at `0x180069a31`
- `GDI32!SetTextColor` at `0x18006961c`
- `GDI32!SetTextColor` at `0x180069a31`
- `GDI32!DeleteObject` at `0x180069a40`
- `GDI32!DeleteObject` at `0x180069a40`
- `GDI32!LPtoDP` at `0x18006907b`
- `GDI32!LPtoDP` at `0x18006907b`

## pseudocode

```c
void __fastcall MfEnumState::OutputDIB(
        COLORREF *this,
        HDC a2,
        const struct _RECTL *a3,
        int a4,
        LONG yDest,
        int DestWidth,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        BITMAPINFO *a12,
        unsigned __int8 *a13,
        UINT a14,
        DWORD a15,
        int a16)
{
  BITMAPINFO *v16; // rsi
  UINT iUsage; // r15d
  DWORD biSize; // edi
  int v21; // eax
  GpBitmap *v22; // rdi
  int v23; // ecx
  int SrcWidth; // r13d
  int v25; // r10d
  int SrcHeight; // r12d
  int v27; // eax
  int v28; // ecx
  LONG biWidth; // eax
  LONG biHeight; // r11d
  int v31; // r8d
  LONG v32; // r11d
  int v33; // edx
  int v34; // r9d
  int v35; // eax
  MfEnumState *v36; // rdx
  MfEnumState *v37; // r14
  int v38; // eax
  DWORD rop; // eax
  HDC v40; // rsi
  GpBitmap *v41; // rax
  GpBitmap *v42; // rax
  unsigned int v43; // r8d
  DWORD v44; // r9d
  DWORD v45; // edx
  struct tagBITMAPINFO *v46; // r15
  GpBitmap *v47; // rax
  int v48; // r9d
  GpBitmap *v49; // rax
  GpBitmap *v50; // r15
  __int64 v51; // rcx
  unsigned __int64 v52; // rcx
  unsigned int v53; // edx
  DWORD v54; // eax
  unsigned __int64 v55; // r15
  unsigned int v56; // ecx
  DWORD v57; // eax
  __int64 v58; // rcx
  struct tagBITMAPINFO *v59; // rax
  unsigned int biBitCount; // r8d
  DWORD biCompression; // r9d
  COLORREF v62; // eax
  COLORREF v63; // edx
  COLORREF v64; // eax
  unsigned int v65; // r8d
  DWORD v66; // r9d
  DWORD v67; // edx
  struct tagBITMAPINFO *v68; // r15
  struct tagBITMAPINFO *v69; // rax
  unsigned __int64 v70; // r15
  __int64 v71; // rax
  __int64 v72; // r8
  unsigned int v73; // edx
  GpGraphics *v74; // r8
  DWORD DestHeight; // [rsp+20h] [rbp-E0h]
  DWORD DestHeighta; // [rsp+20h] [rbp-E0h]
  DWORD DestHeightb; // [rsp+20h] [rbp-E0h]
  BITMAPINFO *lpbmi; // [rsp+50h] [rbp-B0h]
  DWORD Size; // [rsp+70h] [rbp-90h] BYREF
  unsigned int Size_4; // [rsp+74h] [rbp-8Ch]
  int v81; // [rsp+78h] [rbp-88h]
  unsigned int v82; // [rsp+7Ch] [rbp-84h]
  int v83; // [rsp+80h] [rbp-80h]
  int ySrc; // [rsp+84h] [rbp-7Ch]
  int xSrc; // [rsp+88h] [rbp-78h]
  MfEnumState *v86; // [rsp+90h] [rbp-70h]
  int IntDistance; // [rsp+98h] [rbp-68h]
  void *lpBits; // [rsp+A0h] [rbp-60h]
  int xDest; // [rsp+A8h] [rbp-58h]
  int v90; // [rsp+ACh] [rbp-54h]
  COLORREF color; // [rsp+B0h] [rbp-50h]
  COLORREF v92; // [rsp+B4h] [rbp-4Ch]
  int v93; // [rsp+B8h] [rbp-48h]
  LONG v94; // [rsp+BCh] [rbp-44h]
  int v95; // [rsp+C0h] [rbp-40h]
  int v96; // [rsp+C4h] [rbp-3Ch]
  GpGraphics *v97; // [rsp+C8h] [rbp-38h]
  HDC hdc; // [rsp+D0h] [rbp-30h]
  BITMAPINFO *v99; // [rsp+D8h] [rbp-28h] BYREF
  void *v100; // [rsp+E0h] [rbp-20h] BYREF
  BITMAPINFO *v101; // [rsp+E8h] [rbp-18h]
  __int128 *v102; // [rsp+F0h] [rbp-10h]
  HGDIOBJ ho; // [rsp+F8h] [rbp-8h] BYREF
  float v104[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v105; // [rsp+110h] [rbp+10h] BYREF
  float v106; // [rsp+118h] [rbp+18h]
  float v107; // [rsp+11Ch] [rbp+1Ch]
  __int128 v108; // [rsp+120h] [rbp+20h] BYREF
  __int128 v109; // [rsp+130h] [rbp+30h]
  _BYTE v110[8]; // [rsp+140h] [rbp+40h] BYREF
  volatile signed __int32 *v111; // [rsp+148h] [rbp+48h]
  _BYTE v112[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v113; // [rsp+160h] [rbp+60h]
  __int64 v114; // [rsp+174h] [rbp+74h]
  int v115; // [rsp+17Ch] [rbp+7Ch]
  struct tagPOINT pt; // [rsp+188h] [rbp+88h] BYREF
  struct tagPOINT v117; // [rsp+190h] [rbp+90h] BYREF
  struct tagPOINT v118; // [rsp+198h] [rbp+98h] BYREF
  _DWORD v119[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v120; // [rsp+1B0h] [rbp+B0h]
  __int64 v121; // [rsp+1C0h] [rbp+C0h]
  int v122; // [rsp+1C8h] [rbp+C8h]

  v16 = a12;
  iUsage = a14;
  xDest = a4;
  biSize = a12->bmiHeader.biSize;
  hdc = a2;
  v86 = (MfEnumState *)this;
  lpBits = a13;
  Size_4 = a14;
  if ( biSize < 0x28 )
    return;
  if ( a14 >= 2 )
  {
    TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(1, a14, 0);
    return;
  }
  if ( !a13 )
  {
    biBitCount = a12->bmiHeader.biBitCount;
    biCompression = a12->bmiHeader.biCompression;
    DestHeighta = a12->bmiHeader.biClrUsed;
    Size = 0;
    if ( !(unsigned int)GetDibNumPalEntries(a16, biSize, biBitCount, biCompression, DestHeighta, &Size) )
      return;
    lpBits = (void *)GetDibBits(a12, Size, a14);
    Size = 0;
    if ( !(unsigned int)GetDibBitsSize(&a12->bmiHeader, &Size)
      || a12->bmiHeader.biSizeImage && Size > a12->bmiHeader.biSizeImage )
    {
      return;
    }
    if ( biSize + Size < biSize || biSize + Size > this[42] )
      return;
    a4 = xDest;
  }
  v21 = -DestWidth;
  v102 = 0;
  if ( DestWidth > 0 )
    v21 = DestWidth;
  v22 = 0;
  v23 = -a7;
  ho = 0;
  v108 = 0;
  if ( a7 > 0 )
    v23 = a7;
  v109 = 0;
  v100 = 0;
  v99 = 0;
  v93 = 0;
  if ( a12->bmiHeader.biBitCount == 1 && a15 != 13369376 )
  {
    v62 = SetBkColor(a2, this[47]);
    v63 = this[48];
    color = v62;
    v64 = SetTextColor(a2, v63);
    SrcHeight = a11;
    SrcWidth = a10;
    v92 = v64;
    ySrc = a9;
    xSrc = a8;
    v90 = 1;
    goto LABEL_41;
  }
  v117.x = a4 + v21;
  pt.y = yDest;
  v117.y = yDest;
  v90 = 0;
  v118.y = v23 + yDest;
  color = 0;
  v92 = 0;
  pt.x = a4;
  v118.x = a4;
  if ( !LPtoDP(a2, &pt, 3) )
  {
    SrcHeight = a11;
    SrcWidth = a10;
    ySrc = a9;
    xSrc = a8;
    goto LABEL_40;
  }
  IntDistance = GetIntDistance(&pt, &v117);
  SrcWidth = a10;
  v25 = GetIntDistance(&pt, &v118);
  SrcHeight = a11;
  v81 = v25;
  v27 = -a10;
  if ( a10 > 0 )
    v27 = a10;
  v28 = -a11;
  v82 = v27;
  biWidth = a12->bmiHeader.biWidth;
  if ( a11 > 0 )
    v28 = a11;
  v83 = v28;
  if ( biWidth > 0 )
  {
    biHeight = a12->bmiHeader.biHeight;
    v31 = 0;
    v95 = a10 >> 31;
    v32 = -biHeight;
    v96 = a11 >> 31;
    v33 = 0;
    if ( v32 < 0 )
      v32 = a12->bmiHeader.biHeight;
    v94 = v32;
    if ( a8 >= 0 )
      v31 = a8;
    if ( v31 > biWidth )
      v31 = biWidth;
    xSrc = v31;
    if ( a9 >= 0 )
      v33 = a9;
    v34 = v31 + a10;
    if ( v33 > v32 )
      v33 = v32;
    ySrc = v33;
    if ( v34 < 0 )
      SrcWidth = -v31;
    if ( v34 > biWidth )
      SrcWidth = biWidth - v31;
    if ( v33 + a11 < 0 )
      SrcHeight = -v33;
    if ( v33 + a11 > v32 )
      SrcHeight = v32 - v33;
    v35 = v82;
    if ( (int)v82 > 0 && v28 > 0 )
    {
      v36 = v86;
      if ( !*((_DWORD *)v86 + 45) || a15 == 13369376 )
        goto LABEL_36;
      v65 = a12->bmiHeader.biBitCount;
      v66 = a12->bmiHeader.biCompression;
      v67 = a12->bmiHeader.biSize;
      DestHeightb = a12->bmiHeader.biClrUsed;
      Size = 0;
      if ( !(unsigned int)GetDibNumPalEntries(a16, v67, v65, v66, DestHeightb, &Size) )
      {
LABEL_71:
        v25 = v81;
        v36 = v86;
        v28 = v83;
        v35 = v82;
LABEL_36:
        if ( v35 == IntDistance && v28 == v25 )
          goto LABEL_40;
        if ( (*((_BYTE *)v36 + 8) & 1) == 0 && (*((_BYTE *)v36 + 8) & 2) == 0 )
          goto LABEL_40;
        v82 = *((_DWORD *)v36 + 44);
        if ( v82 == 5 )
          goto LABEL_40;
        if ( v28 <= 1 )
          goto LABEL_40;
        if ( v35 <= 1 )
          goto LABEL_40;
        if ( IntDistance * v25 >= 0x800000 )
          goto LABEL_40;
        v41 = (GpBitmap *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x5E0u);
        if ( !v41
          || (v42 = GpBitmap::GpBitmap(v41, IntDistance, v81, 137224), (v22 = v42) == 0)
          || !(*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v42 + 8LL))(v42)
          || (v43 = a12->bmiHeader.biBitCount,
              v44 = a12->bmiHeader.biCompression,
              v45 = a12->bmiHeader.biSize,
              DestHeight = a12->bmiHeader.biClrUsed,
              Size = 0,
              !(unsigned int)GetDibNumPalEntries(a16, v45, v43, v44, DestHeight, &Size)) )
        {
LABEL_40:
          if ( a15 == 13369376 )
          {
            v37 = v86;
            if ( (!*((_DWORD *)v86 + 45) || Globals::OsVer.dwMajorVersion != 4) && (*((_BYTE *)v86 + 8) & 4) == 0 )
            {
              v38 = 4;
LABEL_43:
              SetStretchBltMode(hdc, v38);
              rop = a15;
              if ( a15 != 13369376 && Globals::OsVer.dwMajorVersion == 4 && (*((_DWORD *)v37 + 2) & 0x10000) != 0 )
                rop = 13369376;
              lpbmi = v16;
              v40 = hdc;
              StretchDIBits(
                hdc,
                xDest,
                yDest,
                DestWidth,
                a7,
                xSrc,
                ySrc,
                SrcWidth,
                SrcHeight,
                lpBits,
                lpbmi,
                iUsage,
                rop);
              if ( v22 )
              {
                if ( v102 )
                  GpBitmap::UnlockBits(v22, v102);
                (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v22 + 56LL))(v22);
              }
              if ( v90 )
              {
                SetBkColor(v40, color);
                SetTextColor(v40, v92);
              }
              if ( v93 )
              {
                DeleteObject(ho);
                GpFree(v99);
              }
              return;
            }
LABEL_42:
            v38 = 3;
            goto LABEL_43;
          }
LABEL_41:
          v37 = v86;
          goto LABEL_42;
        }
        if ( ((unsigned __int8)a12 & 3) != 0 || iUsage )
        {
          v70 = (-(__int64)(iUsage != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4;
          if ( Size_4 == 1 )
            TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(2, 2, 0);
          v55 = Size * v70;
          if ( v55 > 0xFFFFFFFF )
            goto LABEL_67;
          v56 = 4 * Size;
          if ( 4 * (unsigned __int64)Size > 0xFFFFFFFF )
            goto LABEL_67;
          v57 = a12->bmiHeader.biSize;
          Size = a12->bmiHeader.biSize + v55;
          if ( v57 + (unsigned int)v55 < v57 )
            goto LABEL_67;
          v58 = v57 + v56;
          if ( (unsigned int)v58 < v57 )
            goto LABEL_67;
          v59 = (struct tagBITMAPINFO *)GpMallocEx(v58, 1);
          v101 = v59;
          v46 = v59;
          if ( !v59 )
            goto LABEL_67;
          memcpy_0(v59, a12, Size);
          Size = 1;
        }
        else
        {
          Size = 0;
          v46 = a12;
          v101 = a12;
        }
        v83 = 1;
        v47 = (GpBitmap *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x5E0u);
        if ( v47 )
        {
          v49 = GpBitmap::GpBitmap(v47, v46, lpBits, v48);
          v50 = v49;
          if ( v49 )
          {
            if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v49 + 8LL))(v49) )
            {
              v71 = (*(__int64 (__fastcall **)(GpBitmap *))(*(_QWORD *)v22 + 128LL))(v22);
              v97 = (GpGraphics *)v71;
              v74 = (GpGraphics *)v71;
              if ( v71 )
              {
                if ( *(_DWORD *)(v71 + 8) == 1634879281 )
                {
                  GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)v110, (struct GpRuntime::GpLockable *)(v71 + 16));
                  v105 = 0;
                  v107 = (float)v81;
                  v106 = (float)IntDistance;
                  v104[1] = (float)(v94 - ySrc - SrcHeight);
                  v104[0] = (float)xSrc;
                  v104[2] = (float)(int)(SrcWidth - (v95 & 0xFFFFFFFE) - 1);
                  v104[3] = (float)(int)(SrcHeight - (v96 & 0xFFFFFFFE) - 1);
                  GpGraphics::SetCompositingMode(v72, 1);
                  GpGraphics::SetInterpolationMode(v97, v82);
                  GpImageAttributes::GpImageAttributes((GpImageAttributes *)v112);
                  v114 = 3;
                  v115 = 0;
                  v113 = 0;
                  v83 = GpGraphics::DrawImage(v97, v50, &v105, v104, 2, v112);
                  GpImageAttributes::~GpImageAttributes((GpImageAttributes *)v112);
                  v74 = v97;
                  _InterlockedDecrement(v111);
                }
                GpGraphics::`scalar deleting destructor'(v74, v73);
              }
            }
            (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v50 + 56LL))(v50);
          }
        }
        if ( Size )
          GpFree(v101);
        if ( !v83 && !(unsigned int)GpBitmap::LockBits(v22, 0, 1, 137224, &v108) )
        {
          v16 = (BITMAPINFO *)v119;
          lpBits = (void *)v109;
          SrcWidth = IntDistance;
          SrcHeight = v81;
          v121 = 0;
          v122 = 0;
          v119[2] = -v81;
          iUsage = 0;
          v120 = 0;
          v102 = &v108;
          xSrc = 0;
          ySrc = 0;
          v119[0] = 40;
          v119[1] = IntDistance;
          v119[3] = 1572865;
          goto LABEL_40;
        }
LABEL_67:
        iUsage = Size_4;
        goto LABEL_40;
      }
      if ( ((unsigned __int8)a12 & 3) != 0 || a14 )
      {
        if ( Size_4 == 1 )
          TraceLogging::TraceLoggingUnsupportedGdiPlusUsage(2, 1, 0);
        v52 = ((-(__int64)(a14 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 4) * Size;
        if ( v52 > 0xFFFFFFFF
          || (v53 = 4 * Size, 4 * (unsigned __int64)Size > 0xFFFFFFFF)
          || (v54 = a12->bmiHeader.biSize, Size = a12->bmiHeader.biSize + v52, v54 + (unsigned int)v52 < v54)
          || (v51 = v53 + v54, (unsigned int)v51 < v54)
          || (v69 = (struct tagBITMAPINFO *)GpMallocEx(v51, 1), (v68 = v69) == 0) )
        {
LABEL_70:
          iUsage = Size_4;
          goto LABEL_71;
        }
        memcpy_0(v69, a12, Size);
        Size = 1;
      }
      else
      {
        Size = 0;
        v68 = a12;
      }
      if ( !(unsigned int)GpBitmap::DrawAndHalftoneForStretchBlt(
                            hdc,
                            v68,
                            lpBits,
                            xSrc,
                            ySrc,
                            v82,
                            v83,
                            IntDistance,
                            v81,
                            (HPALETTE)&v99,
                            &v100,
                            &ho,
                            *((_DWORD *)v86 + 44)) )
      {
        SrcWidth = IntDistance;
        SrcHeight = v81;
        v16 = v99;
        lpBits = v100;
        v93 = 1;
        xSrc = 0;
        ySrc = 0;
        if ( Size )
          GpFree(v68);
        iUsage = Size_4;
        goto LABEL_41;
      }
      if ( Size )
        GpFree(v68);
      goto LABEL_70;
    }
  }
}

```

## disassembly

```asm
0x180068f60  mov     [rsp-8+arg_10], rbx
0x180068f65  push    rbp
0x180068f66  push    rsi
0x180068f67  push    rdi
0x180068f68  push    r12
0x180068f6a  push    r13
0x180068f6c  push    r14
0x180068f6e  push    r15
0x180068f70  lea     rbp, [rsp-0E0h]
0x180068f78  sub     rsp, 1E0h
0x180068f7f  mov     rax, cs:__security_cookie
0x180068f86  xor     rax, rsp
0x180068f89  mov     [rbp+110h+var_40], rax
0x180068f90  mov     rsi, [rbp+110h+arg_58]
0x180068f97  mov     r12, rdx
0x180068f9a  mov     rax, [rbp+110h+arg_60]
0x180068fa1  mov     r13, rcx
0x180068fa4  mov     r15d, [rbp+110h+arg_68]
0x180068fab  mov     [rbp+110h+xDest], r9d
0x180068faf  mov     edi, [rsi]
0x180068fb1  mov     [rbp+110h+hdc], rdx
0x180068fb5  mov     [rbp+110h+var_180], rcx
0x180068fb9  mov     [rbp+110h+var_170], rax
0x180068fbd  mov     dword ptr [rsp+210h+Size+4], r15d
0x180068fc2  cmp     edi, 28h ; '('
0x180068fc5  jb      loc_180069267
0x180068fcb  xor     ebx, ebx
0x180068fcd  cmp     r15d, 2
0x180068fd1  jnb     loc_180069559
0x180068fd7  test    rax, rax
0x180068fda  jz      loc_180069575
0x180068fe0  mov     eax, [rbp+110h+DestWidth]
0x180068fe6  xorps   xmm0, xmm0
0x180068fe9  mov     ecx, [rbp+110h+arg_30]
0x180068fef  neg     eax
0x180068ff1  mov     r14d, 1
0x180068ff7  mov     [rbp+110h+var_120], rbx
0x180068ffb  cmovs   eax, [rbp+110h+DestWidth]
0x180069002  mov     rdi, rbx
0x180069005  neg     ecx
0x180069007  mov     [rbp+110h+ho], rbx
0x18006900b  movups  [rbp+110h+var_F0], xmm0
0x18006900f  cmovs   ecx, [rbp+110h+arg_30]
0x180069016  movups  [rbp+110h+var_E0], xmm0
0x18006901a  mov     [rbp+110h+var_130], rbx
0x18006901e  mov     [rbp+110h+var_138], rbx
0x180069022  mov     [rbp+110h+var_158], ebx
0x180069025  cmp     [rsi+0Eh], r14w
0x18006902a  jz      loc_1800695EF
0x180069030  mov     edx, [rbp+110h+yDest]
0x180069036  add     eax, r9d
0x180069039  mov     [rbp+110h+var_80.x], eax
0x18006903f  mov     r8d, 3; c
0x180069045  mov     [rbp+110h+pt.y], edx
0x18006904b  mov     [rbp+110h+var_80.y], edx
0x180069051  lea     eax, [rcx+rdx]
0x180069054  mov     [rbp+110h+var_164], ebx
0x180069057  lea     rdx, [rbp+110h+pt]; lppt
0x18006905e  mov     [rbp+110h+var_78.y], eax
0x180069064  mov     rcx, r12; hdc
0x180069067  mov     [rbp+110h+color], ebx
0x18006906a  mov     [rbp+110h+var_15C], ebx
0x18006906d  mov     [rbp+110h+pt.x], r9d
0x180069074  mov     [rbp+110h+var_78.x], r9d
0x18006907b  call    cs:__imp_LPtoDP
0x180069081  test    eax, eax
0x180069083  jz      loc_1800693D9
0x180069089  lea     rdx, [rbp+110h+var_80]; struct tagPOINT *
0x180069090  lea     rcx, [rbp+110h+pt]; struct tagPOINT *
0x180069097  call    ?GetIntDistance@@YAHAEAUtagPOINT@@0@Z; GetIntDistance(tagPOINT &,tagPOINT &)
0x18006909c  lea     rdx, [rbp+110h+var_78]; struct tagPOINT *
0x1800690a3  mov     [rbp+110h+var_178], eax
0x1800690a6  lea     rcx, [rbp+110h+pt]; struct tagPOINT *
0x1800690ad  call    ?GetIntDistance@@YAHAEAUtagPOINT@@0@Z; GetIntDistance(tagPOINT &,tagPOINT &)
0x1800690b2  mov     r13d, [rbp+110h+arg_48]
0x1800690b9  mov     r10d, eax
0x1800690bc  mov     r12d, [rbp+110h+arg_50]
0x1800690c3  mov     ecx, r12d
0x1800690c6  mov     [rsp+210h+var_198], eax
0x1800690ca  mov     eax, r13d
0x1800690cd  neg     eax
0x1800690cf  cmovs   eax, r13d
0x1800690d3  neg     ecx
0x1800690d5  mov     [rsp+210h+var_194], eax
0x1800690d9  mov     eax, [rsi+4]
0x1800690dc  cmovs   ecx, r12d
0x1800690e0  mov     [rbp+110h+var_190], ecx
0x1800690e3  test    eax, eax
0x1800690e5  jle     loc_180069267
0x1800690eb  mov     r11d, [rsi+8]
0x1800690ef  mov     edx, r13d
0x1800690f2  sar     edx, 1Fh
0x1800690f5  mov     r8d, ebx
0x1800690f8  mov     [rbp+110h+var_150], edx
0x1800690fb  mov     edx, r12d
0x1800690fe  sar     edx, 1Fh
0x180069101  neg     r11d
0x180069104  mov     [rbp+110h+var_14C], edx
0x180069107  mov     edx, ebx
0x180069109  cmovs   r11d, [rsi+8]
0x18006910e  cmp     [rbp+110h+arg_38], ebx
0x180069114  mov     [rbp+110h+var_154], r11d
0x180069118  cmovge  r8d, [rbp+110h+arg_38]
0x180069120  cmp     r8d, eax
0x180069123  cmovg   r8d, eax
0x180069127  cmp     [rbp+110h+arg_40], ebx
0x18006912d  mov     [rbp+110h+var_188], r8d
0x180069131  cmovge  edx, [rbp+110h+arg_40]
0x180069138  cmp     edx, r11d
0x18006913b  lea     r9d, [r8+r13]
0x18006913f  cmovg   edx, r11d
0x180069143  mov     [rbp+110h+var_18C], edx
0x180069146  test    r9d, r9d
0x180069149  js      loc_18006964E
0x18006914f  cmp     r9d, eax
0x180069152  jg      loc_180069659
0x180069158  lea     eax, [rdx+r12]
0x18006915c  test    eax, eax
0x18006915e  js      loc_180069664
0x180069164  cmp     eax, r11d
0x180069167  jg      loc_18006966F
0x18006916d  mov     eax, [rsp+210h+var_194]
0x180069171  test    eax, eax
0x180069173  jle     loc_180069267
0x180069179  test    ecx, ecx
0x18006917b  jle     loc_180069267
0x180069181  mov     rdx, [rbp+110h+var_180]
0x180069185  cmp     [rdx+0B4h], ebx
0x18006918b  jnz     loc_18006967A
0x180069191  mov     r8d, [rbp+110h+var_178]
0x180069195  cmp     eax, r8d
0x180069198  jz      loc_1800697B3
0x18006919e  test    [rdx+8], r14b
0x1800691a2  jnz     short loc_1800691AA
0x1800691a4  test    byte ptr [rdx+8], 2
0x1800691a8  jz      short loc_1800691BD
0x1800691aa  mov     edx, [rdx+0B0h]
0x1800691b0  mov     [rsp+210h+var_194], edx
0x1800691b4  cmp     edx, 5
0x1800691b7  jnz     loc_1800692B7
0x1800691bd  cmp     [rbp+110h+arg_70], 0CC0020h
0x1800691c7  jz      loc_180069291
0x1800691cd  mov     r14, [rbp+110h+var_180]
0x1800691d1  mov     eax, 3
0x1800691d6  mov     rcx, [rbp+110h+hdc]; hdc
0x1800691da  mov     edx, eax; mode
0x1800691dc  call    cs:__imp_SetStretchBltMode
0x1800691e2  mov     eax, [rbp+110h+arg_70]
0x1800691e8  mov     ecx, 0CC0020h
0x1800691ed  cmp     eax, ecx
0x1800691ef  jnz     loc_1800699DA
0x1800691f5  mov     r9d, [rbp+110h+DestWidth]; DestWidth
0x1800691fc  mov     r8d, [rbp+110h+yDest]; yDest
0x180069203  mov     edx, [rbp+110h+xDest]; xDest
0x180069206  mov     [rsp+210h+rop], eax; rop
0x18006920a  mov     rax, [rbp+110h+var_170]
0x18006920e  mov     [rsp+210h+iUsage], r15d; iUsage
0x180069213  mov     [rsp+210h+lpbmi], rsi; lpbmi
0x180069218  mov     rsi, [rbp+110h+hdc]
0x18006921c  mov     [rsp+210h+lpBits], rax; lpBits
0x180069221  mov     rcx, rsi; hdc
0x180069224  mov     eax, [rbp+110h+var_18C]
0x180069227  mov     [rsp+210h+SrcHeight], r12d; SrcHeight
0x18006922c  mov     [rsp+210h+SrcWidth], r13d; SrcWidth
0x180069231  mov     [rsp+210h+ySrc], eax; ySrc
0x180069235  mov     eax, [rbp+110h+var_188]
0x180069238  mov     [rsp+210h+xSrc], eax; xSrc
0x18006923c  mov     eax, [rbp+110h+arg_30]
0x180069242  mov     [rsp+210h+DestHeight], eax; DestHeight
0x180069246  call    cs:__imp_StretchDIBits
0x18006924c  test    rdi, rdi
0x18006924f  jnz     loc_1800699F7
0x180069255  cmp     [rbp+110h+var_164], ebx
0x180069258  jnz     loc_180069A1F
0x18006925e  cmp     [rbp+110h+var_158], ebx
0x180069261  jnz     loc_180069A3C
0x180069267  mov     rcx, [rbp+110h+var_40]
0x18006926e  xor     rcx, rsp; StackCookie
0x180069271  call    __security_check_cookie
0x180069276  mov     rbx, [rsp+210h+arg_10]
0x18006927e  add     rsp, 1E0h
0x180069285  pop     r15
0x180069287  pop     r14
0x180069289  pop     r13
0x18006928b  pop     r12
0x18006928d  pop     rdi
0x18006928e  pop     rsi
0x18006928f  pop     rbp
0x180069290  retn
0x180069291  mov     r14, [rbp+110h+var_180]
0x180069295  cmp     [r14+0B4h], ebx
0x18006929c  jnz     loc_1800699C8
0x1800692a2  test    byte ptr [r14+8], 4
0x1800692a7  jnz     loc_1800691D1
0x1800692ad  mov     eax, 4
0x1800692b2  jmp     loc_1800691D6
0x1800692b7  cmp     ecx, r14d
0x1800692ba  jle     loc_1800691BD
0x1800692c0  cmp     eax, r14d
0x1800692c3  jle     loc_1800691BD
0x1800692c9  mov     eax, r10d
0x1800692cc  imul    eax, r8d
0x1800692d0  cmp     eax, 800000h
0x1800692d5  jge     loc_1800691BD
0x1800692db  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800692e2  xor     edx, edx; dwFlags
0x1800692e4  mov     r8d, 5E0h; dwBytes
0x1800692ea  call    cs:__imp_HeapAlloc
0x1800692f0  test    rax, rax
0x1800692f3  jz      loc_1800691BD
0x1800692f9  mov     r8d, [rsp+210h+var_198]; int
0x1800692fe  mov     r9d, 21808h; int
0x180069304  mov     edx, [rbp+110h+var_178]; int
0x180069307  mov     rcx, rax; this
0x18006930a  call    ??0GpBitmap@@QEAA@HHH@Z; GpBitmap::GpBitmap(int,int,int)
0x18006930f  mov     rdi, rax
0x180069312  test    rax, rax
0x180069315  jz      loc_1800691BD
0x18006931b  mov     rax, [rax]
0x18006931e  mov     rcx, rdi
0x180069321  mov     rax, [rax+8]
0x180069325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006932a  test    eax, eax
0x18006932c  jz      loc_1800691BD
0x180069332  movzx   r8d, word ptr [rsi+0Eh]; unsigned int
0x180069337  lea     rax, [rsp+210h+Size]
0x18006933c  mov     r9d, [rsi+10h]; unsigned int
0x180069340  mov     edx, [rsi]; unsigned int
0x180069342  mov     ecx, [rbp+110h+arg_78]; int
0x180069348  mov     qword ptr [rsp+210h+xSrc], rax; unsigned int *
0x18006934d  mov     eax, [rsi+20h]
0x180069350  mov     [rsp+210h+DestHeight], eax; unsigned int
0x180069354  mov     dword ptr [rsp+210h+Size], ebx
0x180069358  call    ?GetDibNumPalEntries@@YAHHIIIIPEAI@Z; GetDibNumPalEntries(int,uint,uint,uint,uint,uint *)
0x18006935d  test    eax, eax
0x18006935f  jz      loc_1800691BD
0x180069365  test    sil, 3
0x180069369  jnz     loc_1800697C1
0x18006936f  test    r15d, r15d
0x180069372  jnz     loc_1800697C1
0x180069378  mov     dword ptr [rsp+210h+Size], ebx
0x18006937c  mov     r15, rsi
0x18006937f  mov     [rbp+110h+var_128], rsi
0x180069383  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18006938a  xor     edx, edx; dwFlags
0x18006938c  mov     r8d, 5E0h; dwBytes
0x180069392  mov     [rbp+110h+var_190], r14d
0x180069396  call    cs:__imp_HeapAlloc
0x18006939c  test    rax, rax
0x18006939f  jz      short loc_1800693BC
0x1800693a1  mov     r8, [rbp+110h+var_170]; void *
0x1800693a5  mov     rdx, r15; struct tagBITMAPINFO *
0x1800693a8  mov     rcx, rax; this
0x1800693ab  call    ??0GpBitmap@@QEAA@PEAUtagBITMAPINFO@@PEAXH@Z; GpBitmap::GpBitmap(tagBITMAPINFO *,void *,int)
0x1800693b0  mov     r15, rax
0x1800693b3  test    rax, rax
0x1800693b6  jnz     loc_1800697F9
0x1800693bc  cmp     dword ptr [rsp+210h+Size], ebx
0x1800693c0  jnz     loc_18006992A
0x1800693c6  cmp     [rbp+110h+var_190], ebx
0x1800693c9  jz      loc_180069938
0x1800693cf  mov     r15d, dword ptr [rsp+210h+Size+4]
0x1800693d4  jmp     loc_1800691BD
0x1800693d9  mov     eax, [rbp+110h+arg_40]
0x1800693df  mov     r12d, [rbp+110h+arg_50]
0x1800693e6  mov     r13d, [rbp+110h+arg_48]
0x1800693ed  mov     [rbp+110h+var_18C], eax
0x1800693f0  mov     eax, [rbp+110h+arg_38]
0x1800693f6  mov     [rbp+110h+var_188], eax
0x1800693f9  jmp     loc_1800691BD
0x1800693fe  lea     ecx, [rdx+rax]
0x180069401  cmp     ecx, eax
0x180069403  jnb     loc_1800696D4
0x180069409  mov     r15d, dword ptr [rsp+210h+Size+4]
0x18006940e  mov     r10d, [rsp+210h+var_198]
0x180069413  mov     rdx, [rbp+110h+var_180]
0x180069417  mov     ecx, [rbp+110h+var_190]
0x18006941a  mov     eax, [rsp+210h+var_194]
0x18006941e  jmp     loc_180069191
0x180069423  lea     eax, [rdi+rcx]
0x180069426  cmp     eax, edi
0x180069428  jb      loc_180069267
0x18006942e  cmp     eax, [r13+0A8h]
0x180069435  ja      loc_180069267
0x18006943b  mov     r9d, [rbp+110h+xDest]
0x18006943f  jmp     loc_180068FE0
0x180069444  test    sil, 3
0x180069448  jz      loc_1800696C2
0x18006944e  mov     eax, r15d
0x180069451  neg     eax
0x180069453  sbb     r15, r15
0x180069456  and     r15, 0FFFFFFFFFFFFFFFEh
0x18006945a  add     r15, 4
0x18006945e  cmp     dword ptr [rsp+210h+Size+4], r14d
0x180069463  jnz     short loc_18006947C
0x180069465  xor     r9d, r9d
0x180069468  mov     qword ptr [rsp+210h+DestHeight], rbx
0x18006946d  xor     r8d, r8d
0x180069470  mov     rdx, r14
0x180069473  lea     ecx, [r9+2]
  ... truncated ...
```
