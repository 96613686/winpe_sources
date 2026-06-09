# _ResToIcon(void *,HBITMAP__ * *,HBITMAP__ * *,int,int,int,int,int)

- ea: `0x180027c48`
- end: `0x180028338`
- name: `?_ResToIcon@@YAPEAUHICON__@@PEAXPEAPEAUHBITMAP__@@1HHHHH@Z`
- size: `1776`
- prototype: `HICON__ *__fastcall(void *hRes, HBITMAP__ **phbmpXor, HBITMAP__ **phbmpAnd, int xHot, int yHot, int xSize, int ySize, int fCursor)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800268e4`

## callees

- `0x18001e420`
- `0x180027c48`
- `0x180028340`
- `0x1800289f8`
- `0x180028a20`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180028027`
- `KERNELBASE!GlobalAlloc` at `0x1800281b8`
- `KERNELBASE!GlobalAlloc` at `0x180028027`
- `KERNELBASE!GlobalAlloc` at `0x1800281b8`
- `KERNELBASE!GlobalFree` at `0x18002825f`
- `KERNELBASE!GlobalFree` at `0x18002828b`
- `KERNELBASE!GlobalFree` at `0x18002830e`
- `KERNELBASE!GlobalFree` at `0x18002825f`
- `KERNELBASE!GlobalFree` at `0x18002828b`
- `KERNELBASE!GlobalFree` at `0x18002830e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002831b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002831b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027c98`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180027cc9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180027cc9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002824e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002826d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180028305`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002824e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002826d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180028305`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180027cbd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180028043`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800281c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180027cbd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180028043`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800281c9`
- `GDI32!CreateCompatibleBitmap` at `0x180027f38`
- `GDI32!CreateCompatibleBitmap` at `0x180027f38`
- `GDI32!StretchDIBits` at `0x180027fd8`
- `GDI32!StretchDIBits` at `0x18002817f`
- `GDI32!StretchDIBits` at `0x180027fd8`
- `GDI32!StretchDIBits` at `0x18002817f`
- `GDI32!DeleteObject` at `0x1800282b1`
- `GDI32!DeleteObject` at `0x1800282c7`
- `GDI32!DeleteObject` at `0x1800282b1`
- `GDI32!DeleteObject` at `0x1800282c7`
- `GDI32!CreateBitmap` at `0x180027f27`
- `GDI32!CreateBitmap` at `0x180028080`
- `GDI32!CreateBitmap` at `0x180027f27`
- `GDI32!CreateBitmap` at `0x180028080`
- `GDI32!GetObjectW` at `0x180027fea`
- `GDI32!GetObjectW` at `0x180028192`
- `GDI32!GetObjectW` at `0x180027fea`
- `GDI32!GetObjectW` at `0x180028192`
- `GDI32!GetBitmapBits` at `0x180028056`
- `GDI32!GetBitmapBits` at `0x1800281dc`
- `GDI32!GetBitmapBits` at `0x180028056`
- `GDI32!GetBitmapBits` at `0x1800281dc`
- `GDI32!SelectObject` at `0x180027f51`
- `GDI32!SelectObject` at `0x18002809b`
- `GDI32!SelectObject` at `0x180027f51`
- `GDI32!SelectObject` at `0x18002809b`
- `USER32!ReleaseDC` at `0x1800282fc`
- `USER32!ReleaseDC` at `0x1800282fc`
- `USER32!GetDC` at `0x180027efc`
- `USER32!GetDC` at `0x180027efc`
- `USER32!CreateCursor` at `0x18002820f`
- `USER32!CreateCursor` at `0x18002820f`
- `USER32!CreateIcon` at `0x180028228`
- `USER32!CreateIcon` at `0x180028228`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HICON__ *__fastcall _ResToIcon(
        void *hRes,
        HBITMAP__ **phbmpXor,
        HBITMAP__ **phbmpAnd,
        int xHot,
        int yHot,
        int xSize,
        int ySize,
        int fCursor)
{
  void *v8; // r12
  HBITMAP v9; // r13
  const BITMAPINFO *lpbmi; // rsi
  SIZE_T v11; // rax
  SIZE_T v12; // r15
  unsigned __int64 v13; // r9
  int biHeight; // r14d
  __int64 v15; // rdi
  HBITMAP__ *v16; // rax
  unsigned int biClrUsed; // edx
  unsigned __int16 *p_biBitCount; // rdi
  unsigned int biCompression; // ebx
  bool v20; // zf
  __int64 v21; // r12
  __int64 v22; // r11
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // r10
  __int64 v25; // r11
  unsigned __int64 v26; // rax
  int v27; // r9d
  unsigned __int64 biSizeImage; // r14
  int v29; // r9d
  __int64 v30; // r10
  tagRGBQUAD *bmiColors; // rbx
  HDC DC; // rax
  HBITMAP Bitmap; // rax
  HBITMAP__ *v34; // r15
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  LONG v38; // ebx
  HGLOBAL v39; // rax
  void *v40; // r14
  void *v41; // r12
  HBITMAP v42; // rax
  HBITMAP__ *v43; // rax
  unsigned __int64 v44; // r10
  unsigned __int64 biWidth; // rax
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // r9
  unsigned __int64 v48; // r10
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rdx
  LONG v51; // ebx
  HGLOBAL v52; // rax
  HDC__ *v53; // rbx
  HCURSOR Cursor; // rax
  HGLOBAL v55; // rbx
  unsigned __int64 v56; // rsi
  HBITMAP cbRemaining; // [rsp+78h] [rbp-90h]
  HDC__ *hdcMem; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 cbTotalSize; // [rsp+88h] [rbp-80h] BYREF
  HGLOBAL hMem; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 nSafe; // [rsp+98h] [rbp-70h]
  unsigned __int64 v63; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 cbitsWidth; // [rsp+A8h] [rbp-60h]
  unsigned __int64 pullResult; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE bmpXOR[72]; // [rsp+B8h] [rbp-50h] OVERLAPPED BYREF

  v8 = hRes;
  cbTotalSize = 0;
  memset(&bmpXOR[8], 0, 64);
  EnterCriticalSection(&g_sys.m_critDCBusy);
  nSafe = 0;
  cbRemaining = 0;
  v9 = 0;
  SysInfo::GetHdc(&g_sys, (HDC__ **)&cbTotalSize);
  lpbmi = (const BITMAPINFO *)GlobalLock(v8);
  v11 = GlobalSize(v8);
  v12 = v11;
  if ( v11 < 0x28 )
    goto LABEL_8;
  if ( lpbmi->bmiHeader.biSize != 40 )
    goto LABEL_8;
  v63 = (unsigned __int64)lpbmi + v11;
  v13 = v11 - 40;
  *(_QWORD *)bmpXOR = v11 - 40;
  hdcMem = (HDC__ *)(v11 - 40);
  if ( lpbmi->bmiHeader.biWidth <= 0 )
    goto LABEL_8;
  biHeight = lpbmi->bmiHeader.biHeight;
  if ( !biHeight || biHeight < 0 && lpbmi->bmiHeader.biCompression && lpbmi->bmiHeader.biCompression != 3 )
    goto LABEL_8;
  if ( lpbmi->bmiHeader.biPlanes != 1
    || (biClrUsed = lpbmi->bmiHeader.biClrUsed,
        p_biBitCount = &lpbmi->bmiHeader.biBitCount,
        cbitsWidth = (unsigned __int64)&lpbmi->bmiHeader.biBitCount,
        biClrUsed > 0x100)
    && *p_biBitCount == 8 )
  {
LABEL_8:
    v15 = 0xFFFF;
    v16 = 0;
    goto LABEL_99;
  }
  biCompression = lpbmi->bmiHeader.biCompression;
  if ( biCompression == 3 )
  {
    p_biBitCount = &lpbmi->bmiHeader.biBitCount;
    v20 = lpbmi->bmiHeader.biBitCount == 16;
    cbitsWidth = (unsigned __int64)&lpbmi->bmiHeader.biBitCount;
    if ( v20 )
    {
      cbitsWidth = (unsigned __int64)&lpbmi->bmiHeader.biBitCount;
    }
    else if ( *p_biBitCount != 32 )
    {
      v15 = 0xFFFF;
      v16 = 0;
      goto LABEL_99;
    }
  }
  if ( !biClrUsed && (unsigned __int16)(*p_biBitCount - 1) <= 7u )
    biClrUsed = 1 << *p_biBitCount;
  v21 = biClrUsed;
  hMem = 0;
  v22 = 12;
  if ( biCompression != 3 )
    v22 = 0;
  if ( !is_mul_ok(biClrUsed, 4u) )
    goto LABEL_30;
  v23 = v22 + 4LL * biClrUsed;
  if ( v23 < 4 * (unsigned __int64)biClrUsed )
    goto LABEL_30;
  if ( v13 < v23 )
    goto LABEL_30;
  if ( SizeTSub(v13, v23, (unsigned __int64 *)&hdcMem) < 0 )
    goto LABEL_30;
  v26 = v24 + 40;
  if ( v24 >= 0xFFFFFFFFFFFFFFD8uLL )
    goto LABEL_30;
  if ( v25 + v26 < v26 )
    goto LABEL_30;
  if ( v12 < v25 + v26 )
    goto LABEL_30;
  lpbmi->bmiHeader.biHeight = biHeight / 2;
  v27 = biHeight / 2;
  if ( !(biHeight / 2) )
    goto LABEL_30;
  biSizeImage = 0;
  hMem = 0;
  if ( !biCompression || biCompression == 3 )
  {
    pullResult = 0;
    if ( v27 < 0 && v27 == 0x80000000 )
      goto LABEL_30;
    if ( ULongLongMult(lpbmi->bmiHeader.biWidth, *p_biBitCount, &pullResult) < 0 )
      goto LABEL_30;
    if ( pullResult + 31 < pullResult )
      goto LABEL_30;
    if ( ULongLongMult(v29, v30 & ((pullResult + 31) >> 3), (unsigned __int64 *)&hMem) < 0 )
      goto LABEL_30;
    biSizeImage = (unsigned __int64)hMem;
    if ( hdcMem < hMem
      || lpbmi->bmiHeader.biCompression
      && lpbmi->bmiHeader.biSizeImage
      && (unsigned __int64)hMem > lpbmi->bmiHeader.biSizeImage )
    {
      goto LABEL_30;
    }
  }
  if ( (unsigned __int64)hdcMem < lpbmi->bmiHeader.biSizeImage )
  {
    if ( lpbmi->bmiHeader.biCompression )
      goto LABEL_30;
    lpbmi->bmiHeader.biSizeImage = 0;
  }
  if ( lpbmi->bmiHeader.biClrUsed )
  {
    bmiColors = &lpbmi->bmiColors[lpbmi->bmiHeader.biClrUsed];
  }
  else
  {
    bmiColors = lpbmi->bmiColors;
    if ( *p_biBitCount == 24 )
      goto LABEL_51;
    bmiColors += v21;
  }
  if ( bmiColors < lpbmi->bmiColors )
  {
LABEL_30:
    v15 = 0xFFFF;
LABEL_31:
    v16 = 0;
    goto LABEL_98;
  }
LABEL_51:
  if ( bmiColors >= (tagRGBQUAD *)((char *)lpbmi + v12) )
    goto LABEL_30;
  v15 = 0;
  DC = GetDC(0);
  nSafe = (unsigned __int64)DC;
  if ( fCursor )
    Bitmap = CreateBitmap(xSize, ySize, 1u, 1u, 0);
  else
    Bitmap = CreateCompatibleBitmap(DC, xSize, ySize);
  v9 = Bitmap;
  if ( !Bitmap )
  {
    v16 = 0;
    goto LABEL_98;
  }
  v34 = (HBITMAP__ *)SelectObject((HDC)cbTotalSize, Bitmap);
  if ( lpbmi->bmiHeader.biCompression && lpbmi->bmiHeader.biCompression != 3 )
  {
    if ( !lpbmi->bmiHeader.biSizeImage )
    {
LABEL_90:
      v15 = 0xFFFF;
      goto LABEL_91;
    }
    biSizeImage = lpbmi->bmiHeader.biSizeImage;
  }
  v35 = (unsigned __int64)bmiColors + biSizeImage;
  pullResult = (unsigned __int64)bmiColors + biSizeImage;
  if ( (tagRGBQUAD *)((char *)bmiColors + biSizeImage) < bmiColors
    || v35 < (unsigned __int64)lpbmi->bmiColors
    || v35 > v63 )
  {
    goto LABEL_90;
  }
  StretchDIBits(
    (HDC)cbTotalSize,
    0,
    0,
    xSize,
    ySize,
    0,
    0,
    lpbmi->bmiHeader.biWidth,
    lpbmi->bmiHeader.biHeight,
    bmiColors,
    lpbmi,
    0,
    0xCC0020u);
  GetObjectW(v9, 32, &bmpXOR[8]);
  v36 = *(unsigned int *)&bmpXOR[16] * (unsigned __int64)*(unsigned int *)&bmpXOR[20];
  if ( v36 > 0xFFFFFFFF )
    goto LABEL_91;
  v37 = *(unsigned __int16 *)&bmpXOR[24] * (unsigned __int64)(unsigned int)v36;
  v38 = v37;
  if ( v37 > 0xFFFFFFFF )
    goto LABEL_91;
  v39 = GlobalAlloc(2u, (unsigned int)v37);
  hMem = v39;
  if ( !v39 )
    goto LABEL_91;
  v40 = 0;
  v41 = 0;
  hdcMem = (HDC__ *)GlobalLock(v39);
  GetBitmapBits(v9, v38, hdcMem);
  _RestoreBitmap((HDC__ *)cbTotalSize, v34);
  v42 = CreateBitmap(xSize, ySize, 1u, 1u, 0);
  cbRemaining = v42;
  if ( v42 )
  {
    v43 = (HBITMAP__ *)SelectObject((HDC)cbTotalSize, v42);
    v44 = v63;
    lpbmi->bmiHeader.biClrUsed = 0;
    v34 = v43;
    *(_WORD *)cbitsWidth = 1;
    if ( (unsigned __int64)lpbmi->bmiColors >= v44 || *(_QWORD *)bmpXOR < 6u )
    {
      v15 = 0xFFFF;
    }
    else
    {
      lpbmi->bmiColors[0] = (tagRGBQUAD)-16777216;
      LOWORD(lpbmi[1].bmiHeader.biSize) = -1;
      biWidth = lpbmi->bmiHeader.biWidth;
      if ( biWidth + 31 < biWidth
        || (v46 = lpbmi->bmiHeader.biHeight,
            v63 = ((biWidth + 31) >> 3) & 0x1FFFFFFFFFFFFFFCLL,
            ULongLongMult(v63, v46, &v63) < 0)
        || (v49 = pullResult + v63, pullResult + v63 < pullResult)
        || v49 < v47
        || v49 > v48
        || (StretchDIBits(
              (HDC)cbTotalSize,
              0,
              0,
              xSize,
              ySize,
              0,
              0,
              lpbmi->bmiHeader.biWidth,
              lpbmi->bmiHeader.biHeight,
              (const void *)pullResult,
              lpbmi,
              0,
              0xCC0020u),
            GetObjectW(cbRemaining, 32, &bmpXOR[40]),
            v50 = *(unsigned int *)&bmpXOR[48] * (unsigned __int64)*(unsigned int *)&bmpXOR[52],
            v50 > 0xFFFFFFFF) )
      {
        v15 = 0xFFFF;
      }
      else
      {
        v51 = *(_DWORD *)&bmpXOR[48] * *(_DWORD *)&bmpXOR[52];
        v52 = GlobalAlloc(2u, (unsigned int)v50);
        v40 = v52;
        if ( v52 )
        {
          v41 = GlobalLock(v52);
          GetBitmapBits(cbRemaining, v51, v41);
          v53 = hdcMem;
          if ( fCursor )
            Cursor = CreateCursor(g_hinstDLL, xHot, yHot, xSize, ySize, v41, hdcMem);
          else
            Cursor = CreateIcon(
                       g_hinstDLL,
                       xSize,
                       ySize,
                       bmpXOR[24],
                       bmpXOR[26],
                       (const BYTE *)v41,
                       (const BYTE *)hdcMem);
          v15 = (__int64)Cursor;
          goto $Error_2;
        }
      }
    }
  }
  v53 = hdcMem;
$Error_2:
  v20 = v53 == 0;
  v55 = hMem;
  if ( !v20 )
    GlobalUnlock(hMem);
  v56 = nSafe;
  GlobalFree(v55);
  if ( v41 )
    GlobalUnlock(v40);
  else
    nSafe = v56;
  if ( v40 )
    GlobalFree(v40);
LABEL_91:
  if ( v34 )
    _RestoreBitmap((HDC__ *)cbTotalSize, v34);
  if ( v15 )
  {
    v16 = cbRemaining;
    goto LABEL_98;
  }
  DeleteObject(v9);
  v16 = cbRemaining;
  v9 = 0;
  if ( cbRemaining )
  {
    DeleteObject(cbRemaining);
    goto LABEL_31;
  }
LABEL_98:
  v8 = hRes;
LABEL_99:
  *phbmpXor = v9;
  *phbmpAnd = v16;
  if ( nSafe )
    ReleaseDC(0, (HDC)nSafe);
  GlobalUnlock(v8);
  GlobalFree(v8);
  LeaveCriticalSection(&g_sys.m_critDCBusy);
  return (HICON__ *)v15;
}

```

## disassembly

```asm
0x180027c48  mov     rax, rsp
0x180027c4b  mov     [rax+20h], xHot
0x180027c4f  mov     [rax+18h], phbmpAnd
0x180027c53  mov     [rax+10h], phbmpXor
0x180027c57  mov     [rax+8], hRes
0x180027c5b  push    rbp
0x180027c5c  push    rbx
0x180027c5d  push    rsi
0x180027c5e  push    rdi
0x180027c5f  push    r12
0x180027c61  push    r13
0x180027c63  push    r14
0x180027c65  push    r15
0x180027c67  lea     rbp, [rax-48h]
0x180027c6b  sub     rsp, 108h
0x180027c72  xorps   xmm0, xmm0
0x180027c75  xorps   xmm1, xmm1
0x180027c78  mov     r12, hRes
0x180027c7b  xor     ebx, ebx
0x180027c7d  lea     hRes, ?g_sys@@3USysInfo@@A.m_critDCBusy; lpCriticalSection
0x180027c84  mov     [rbp+40h+cbTotalSize], rbx
0x180027c88  movups  xmmword ptr [rbp+40h+bmpXOR.bmHeight], xmm0
0x180027c8c  movups  xmmword ptr [rbp+40h+bmpXOR.bmBits], xmm0
0x180027c90  movups  xmmword ptr [rbp+40h+bmpAND.bmHeight], xmm1
0x180027c94  movups  xmmword ptr [rbp+40h+bmpAND.bmBits], xmm1
0x180027c98  call    cs:__imp_EnterCriticalSection
0x180027c9e  lea     phbmpXor, [rbp+40h+cbTotalSize]; phdc
0x180027ca2  mov     [rbp+40h+nSafe], rbx
0x180027ca6  lea     hRes, ?g_sys@@3USysInfo@@A; this
0x180027cad  mov     [rsp+140h+cbRemaining], rbx
0x180027cb2  mov     r13d, ebx
0x180027cb5  call    ?GetHdc@SysInfo@@QEAAJPEAPEAUHDC__@@@Z; SysInfo::GetHdc(HDC__ * *)
0x180027cba  mov     hRes, r12; hMem
0x180027cbd  call    cs:__imp_GlobalLock
0x180027cc3  mov     hRes, r12; hMem
0x180027cc6  mov     rsi, rax
0x180027cc9  call    cs:__imp_GlobalSize
0x180027ccf  mov     r15, rax
0x180027cd2  cmp     rax, 28h ; '('
0x180027cd6  jb      short loc_180027D13
0x180027cd8  cmp     dword ptr [rsi], 28h ; '('
0x180027cdb  jnz     short loc_180027D13
0x180027cdd  lea     hRes, [rsi+rax]
0x180027ce1  mov     r9, hRes
0x180027ce4  mov     [rbp+40h+var_A8], hRes
0x180027ce8  lea     rax, [rsi+28h]
0x180027cec  sub     r9, rax
0x180027cef  mov     qword ptr [rbp+40h+bmpXOR.bmType], r9
0x180027cf3  mov     [rsp+140h+hdcMem], r9
0x180027cf8  cmp     [rsi+4], ebx
0x180027cfb  jle     short loc_180027D13
0x180027cfd  mov     r14d, [rsi+8]
0x180027d01  test    r14d, r14d
0x180027d04  jz      short loc_180027D13
0x180027d06  jns     short loc_180027D20
0x180027d08  cmp     [rsi+10h], ebx
0x180027d0b  jz      short loc_180027D20
0x180027d0d  cmp     dword ptr [rsi+10h], 3
0x180027d11  jz      short loc_180027D20
0x180027d13  mov     edi, 0FFFFh
0x180027d18  mov     rax, rbx
0x180027d1b  jmp     loc_1800282E0
0x180027d20  mov     r8d, 1
0x180027d26  cmp     [rsi+0Ch], r8w
0x180027d2b  jnz     short loc_180027D13
0x180027d2d  mov     edx, [rsi+20h]
0x180027d30  lea     rdi, [rsi+0Eh]
0x180027d34  mov     [rbp+40h+cbitsWidth], rdi
0x180027d38  cmp     edx, 100h
0x180027d3e  jbe     short loc_180027D46
0x180027d40  cmp     word ptr [rdi], 8
0x180027d44  jz      short loc_180027D13
0x180027d46  mov     ebx, [rsi+10h]
0x180027d49  mov     eax, 20h ; ' '
0x180027d4e  cmp     ebx, 3
0x180027d51  jnz     short loc_180027D77
0x180027d53  lea     rdi, [rsi+0Eh]
0x180027d57  cmp     word ptr [rdi], 10h
0x180027d5b  mov     [rbp+40h+cbitsWidth], rdi
0x180027d5f  jz      short loc_180027D73
0x180027d61  cmp     [rdi], ax
0x180027d64  jz      short loc_180027D77
0x180027d66  mov     edi, 0FFFFh
0x180027d6b  mov     rax, r13
0x180027d6e  jmp     loc_1800282E0
0x180027d73  mov     [rbp+40h+cbitsWidth], rdi
0x180027d77  test    edx, edx
0x180027d79  jnz     short loc_180027D90
0x180027d7b  movzx   ecx, word ptr [rdi]
0x180027d7e  movzx   eax, cx
0x180027d81  sub     ax, r8w
0x180027d85  cmp     ax, 7
0x180027d89  ja      short loc_180027D90
0x180027d8b  mov     edx, r8d
0x180027d8e  shl     edx, cl
0x180027d90  xor     eax, eax
0x180027d92  mov     r12d, edx
0x180027d95  cmp     ebx, 3
0x180027d98  mov     [rbp+40h+hMem], rax
0x180027d9c  lea     r11d, [rax+0Ch]
0x180027da0  cmovnz  r11d, eax
0x180027da4  mov     eax, 4
0x180027da9  mul     r12
0x180027dac  mov     r10, rax
0x180027daf  test    phbmpXor, phbmpXor
0x180027db2  jnz     short loc_180027E0E
0x180027db4  add     rax, r11
0x180027db7  or      phbmpXor, 0FFFFFFFFFFFFFFFFh
0x180027dbb  cmp     rax, r10
0x180027dbe  cmovnb  phbmpXor, rax; Subtrahend
0x180027dc2  sbb     eax, eax
0x180027dc4  test    eax, 80070216h
0x180027dc9  jl      short loc_180027E0E
0x180027dcb  cmp     r9, phbmpXor
0x180027dce  jb      short loc_180027E0E
0x180027dd0  lea     phbmpAnd, [rsp+140h+hdcMem]; pResult
0x180027dd5  mov     hRes, r9; Minuend
0x180027dd8  call    ?SizeTSub@@YAJ_K0PEA_K@Z; SizeTSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180027ddd  test    eax, eax
0x180027ddf  js      short loc_180027E0E
0x180027de1  lea     rax, [r10+28h]
0x180027de5  cmp     rax, 28h ; '('
0x180027de9  jb      short loc_180027E0E
0x180027deb  lea     hRes, [r11+rax]
0x180027def  cmp     hRes, rax
0x180027df2  jb      short loc_180027E0E
0x180027df4  cmp     r15, hRes
0x180027df7  jb      short loc_180027E0E
0x180027df9  mov     eax, r14d
0x180027dfc  mov     ecx, 2
0x180027e01  cdq
0x180027e02  idiv    ecx
0x180027e04  mov     [rsi+8], eax
0x180027e07  mov     xHot, eax
0x180027e0a  test    eax, eax
0x180027e0c  jnz     short loc_180027E1B
0x180027e0e  mov     edi, 0FFFFh
0x180027e13  mov     rax, r13
0x180027e16  jmp     loc_1800282DC
0x180027e1b  xor     r14d, r14d
0x180027e1e  mov     r10, 1FFFFFFFFFFFFFFCh
0x180027e28  mov     [rbp+40h+hMem], r14
0x180027e2c  test    ebx, ebx
0x180027e2e  jz      short loc_180027E35
0x180027e30  cmp     ebx, 3
0x180027e33  jnz     short loc_180027EA5
0x180027e35  mov     [rbp+40h+pullResult], r13
0x180027e39  test    xHot, xHot
0x180027e3c  jns     short loc_180027E4A
0x180027e3e  cmp     xHot, 80000000h
0x180027e45  jz      short loc_180027E0E
0x180027e47  neg     xHot
0x180027e4a  movzx   edx, word ptr [rdi]; ullMultiplier
0x180027e4d  lea     phbmpAnd, [rbp+40h+pullResult]; pullResult
0x180027e51  movsxd  hRes, dword ptr [rsi+4]; ullMultiplicand
0x180027e55  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180027e5a  test    eax, eax
0x180027e5c  js      short loc_180027E0E
0x180027e5e  mov     rax, [rbp+40h+pullResult]
0x180027e62  lea     phbmpXor, [rax+1Fh]
0x180027e66  cmp     phbmpXor, rax
0x180027e69  jb      short loc_180027E0E
0x180027e6b  shr     phbmpXor, 3
0x180027e6f  lea     phbmpAnd, [rbp+40h+hMem]; pullResult
0x180027e73  and     phbmpXor, r10; ullMultiplier
0x180027e76  movsxd  hRes, xHot; ullMultiplicand
0x180027e79  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180027e7e  test    eax, eax
0x180027e80  js      short loc_180027E0E
0x180027e82  mov     r14, [rbp+40h+hMem]
0x180027e86  cmp     [rsp+140h+hdcMem], r14
0x180027e8b  jb      short loc_180027E0E
0x180027e8d  cmp     [rsi+10h], r13d
0x180027e91  jz      short loc_180027EA5
0x180027e93  cmp     [rsi+14h], r13d
0x180027e97  jz      short loc_180027EA5
0x180027e99  mov     eax, [rsi+14h]
0x180027e9c  cmp     r14, rax
0x180027e9f  ja      loc_180027E0E
0x180027ea5  mov     eax, [rsi+14h]
0x180027ea8  cmp     [rsp+140h+hdcMem], rax
0x180027ead  jnb     short loc_180027EBD
0x180027eaf  cmp     [rsi+10h], r13d
0x180027eb3  jnz     loc_180027E0E
0x180027eb9  mov     [rsi+14h], r13d
0x180027ebd  cmp     [rsi+20h], r13d
0x180027ec1  jz      short loc_180027ED0
0x180027ec3  mov     ebx, [rsi+20h]
0x180027ec6  add     rbx, 0Ah
0x180027eca  lea     rbx, [rsi+rbx*4]
0x180027ece  jmp     short loc_180027EDE
0x180027ed0  cmp     word ptr [rdi], 18h
0x180027ed4  lea     rbx, [rsi+28h]
0x180027ed8  jz      short loc_180027EEB
0x180027eda  lea     rbx, [rbx+r12*4]
0x180027ede  lea     rax, [rsi+28h]
0x180027ee2  cmp     rbx, rax
0x180027ee5  jb      loc_180027E0E
0x180027eeb  lea     rax, [rsi+r15]
0x180027eef  cmp     rbx, rax
0x180027ef2  jnb     loc_180027E0E
0x180027ef8  xor     ecx, ecx; hWnd
0x180027efa  xor     edi, edi
0x180027efc  call    cs:__imp_GetDC
0x180027f02  mov     r12d, [rbp+40h+nHeight]
0x180027f09  mov     [rbp+40h+nSafe], rax
0x180027f0d  cmp     [rbp+40h+arg_38], edi
0x180027f13  jz      short loc_180027F2F
0x180027f15  mov     ecx, [rbp+40h+nWidth]; nWidth
0x180027f18  lea     r8d, [rdi+1]; nPlanes
0x180027f1c  mov     xHot, r8d; nBitCount
0x180027f1f  mov     [rsp+140h+lpBits], rdi; lpBits
0x180027f24  mov     edx, r12d; nHeight
0x180027f27  call    cs:__imp_CreateBitmap
0x180027f2d  jmp     short loc_180027F3E
0x180027f2f  mov     edx, [rbp+40h+nWidth]; cx
0x180027f32  mov     r8d, r12d; cy
0x180027f35  mov     hRes, rax; hdc
0x180027f38  call    cs:__imp_CreateCompatibleBitmap
0x180027f3e  mov     r13, rax
0x180027f41  test    rax, rax
0x180027f44  jz      loc_1800282D2
0x180027f4a  mov     hRes, [rbp+40h+cbTotalSize]; hdc
0x180027f4e  mov     phbmpXor, rax; h
0x180027f51  call    cs:__imp_SelectObject
0x180027f57  mov     r15, rax
0x180027f5a  cmp     [rsi+10h], edi
0x180027f5d  jz      short loc_180027F72
0x180027f5f  cmp     dword ptr [rsi+10h], 3
0x180027f63  jz      short loc_180027F72
0x180027f65  cmp     [rsi+14h], edi
0x180027f68  jz      loc_180028293
0x180027f6e  mov     r14d, [rsi+14h]
0x180027f72  lea     rax, [r14+rbx]
0x180027f76  mov     [rbp+40h+pullResult], rax
0x180027f7a  cmp     rax, rbx
0x180027f7d  jb      loc_180028293
0x180027f83  lea     hRes, [rsi+28h]
0x180027f87  cmp     rax, hRes
0x180027f8a  jb      loc_180028293
0x180027f90  cmp     rax, [rbp+40h+var_A8]
0x180027f94  ja      loc_180028293
0x180027f9a  mov     eax, [rsi+8]
0x180027f9d  xor     r8d, r8d; yDest
0x180027fa0  mov     xHot, [rbp+40h+nWidth]; DestWidth
0x180027fa4  xor     edx, edx; xDest
0x180027fa6  mov     hRes, [rbp+40h+cbTotalSize]; hdc
0x180027faa  mov     dword ptr [rsp+60h], 0CC0020h; rop
0x180027fb2  mov     [rsp+140h+iUsage], edi; iUsage
0x180027fb6  mov     [rsp+140h+lpbmi], rsi; lpbmi
0x180027fbb  mov     [rsp+140h+var_F8], rbx; lpBits
0x180027fc0  mov     [rsp+140h+SrcHeight], eax; SrcHeight
0x180027fc4  mov     eax, [rsi+4]
0x180027fc7  mov     [rsp+140h+SrcWidth], eax; SrcWidth
0x180027fcb  mov     [rsp+140h+ySrc], edi; ySrc
0x180027fcf  mov     [rsp+140h+xSrc], edi; xSrc
0x180027fd3  mov     dword ptr [rsp+140h+lpBits], r12d; DestHeight
0x180027fd8  call    cs:__imp_StretchDIBits
0x180027fde  lea     phbmpAnd, [rbp+40h+bmpXOR.bmHeight]; pv
0x180027fe2  mov     edx, 20h ; ' '; c
0x180027fe7  mov     hRes, r13; h
0x180027fea  call    cs:__imp_GetObjectW
0x180027ff0  mov     ecx, dword ptr [rbp+40h+bmpXOR+14h]
0x180027ff3  mov     edx, 0FFFFFFFFh
0x180027ff8  mov     eax, dword ptr [rbp+40h+bmpXOR.bmPlanes]
0x180027ffb  imul    hRes, rax
0x180027fff  cmp     hRes, phbmpXor
0x180028002  ja      loc_180028298
0x180028008  movzx   eax, word ptr [rbp+40h+bmpXOR.bmBits]
0x18002800c  mov     ecx, ecx
0x18002800e  imul    hRes, rax
0x180028012  mov     ebx, ecx
0x180028014  cmp     hRes, phbmpXor
0x180028017  jbe     short loc_180028020
0x180028019  mov     ebx, edx
0x18002801b  jmp     loc_180028298
0x180028020  mov     edx, ebx; dwBytes
0x180028022  mov     ecx, 2; uFlags
0x180028027  call    cs:__imp_GlobalAlloc
0x18002802d  mov     [rbp+40h+hMem], rax
0x180028031  test    rax, rax
0x180028034  jz      loc_180028298
0x18002803a  mov     hRes, rax; hMem
0x18002803d  xor     r14d, r14d
0x180028040  xor     r12d, r12d
0x180028043  call    cs:__imp_GlobalLock
0x180028049  mov     edx, ebx; cb
0x18002804b  mov     hRes, r13; hbit
0x18002804e  mov     phbmpAnd, rax; lpvBits
0x180028051  mov     [rsp+140h+hdcMem], rax
0x180028056  call    cs:__imp_GetBitmapBits
0x18002805c  mov     hRes, [rbp+40h+cbTotalSize]; hdc
0x180028060  mov     phbmpXor, r15; hbmp
0x180028063  call    ?_RestoreBitmap@@YAXPEAUHDC__@@PEAUHBITMAP__@@@Z; _RestoreBitmap(HDC__ *,HBITMAP__ *)
0x180028068  mov     edx, [rbp+40h+nHeight]; nHeight
0x18002806e  lea     ebx, [r14+1]
0x180028072  mov     ecx, [rbp+40h+nWidth]; nWidth
0x180028075  mov     xHot, ebx; nBitCount
0x180028078  mov     r8d, ebx; nPlanes
0x18002807b  mov     [rsp+140h+lpBits], rdi; lpBits
  ... truncated ...
```
