# DriverNonPS::OutputBufferDIB(HDC__ *,DpContext *,DpBitmap *,GpRuntime::GpRect const *,GpRuntime::GpRect const *,DpPath *)

- ea: `0x1800d4420`
- end: `0x1800d4fa9`
- name: `?OutputBufferDIB@DriverNonPS@@UEAA?AW4Status@@PEAUHDC__@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@3PEAVDpPath@@@Z`
- size: `2953`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18004d398`
- `0x1800c1938`
- `0x1800d4420`
- `0x1800d4fb0`
- `0x1800fe680`
- `0x1801364f0`
- `0x1801387b0`
- `0x180138d30`

## import_xrefs

- `GDI32!StretchBlt` at `0x1800d4c0a`
- `GDI32!StretchBlt` at `0x1800d4e44`
- `GDI32!StretchBlt` at `0x1800d4c0a`
- `GDI32!StretchBlt` at `0x1800d4e44`
- `GDI32!SetStretchBltMode` at `0x1800d4a93`
- `GDI32!SetStretchBltMode` at `0x1800d4a93`
- `GDI32!StretchDIBits` at `0x1800d46eb`
- `GDI32!StretchDIBits` at `0x1800d47ac`
- `GDI32!StretchDIBits` at `0x1800d49c3`
- `GDI32!StretchDIBits` at `0x1800d4b73`
- `GDI32!StretchDIBits` at `0x1800d4d28`
- `GDI32!StretchDIBits` at `0x1800d4dc3`
- `GDI32!StretchDIBits` at `0x1800d4f02`
- `GDI32!StretchDIBits` at `0x1800d46eb`
- `GDI32!StretchDIBits` at `0x1800d47ac`
- `GDI32!StretchDIBits` at `0x1800d49c3`
- `GDI32!StretchDIBits` at `0x1800d4b73`
- `GDI32!StretchDIBits` at `0x1800d4d28`
- `GDI32!StretchDIBits` at `0x1800d4dc3`
- `GDI32!StretchDIBits` at `0x1800d4f02`
- `GDI32!SetBrushOrgEx` at `0x1800d4aac`
- `GDI32!SetBrushOrgEx` at `0x1800d4aac`
- `GDI32!SetBkColor` at `0x1800d4bb9`
- `GDI32!SetBkColor` at `0x1800d4bb9`
- `GDI32!SetTextColor` at `0x1800d4bc5`
- `GDI32!SetTextColor` at `0x1800d4bc5`
- `GDI32!CreateBitmap` at `0x1800d4a5a`
- `GDI32!CreateBitmap` at `0x1800d4a5a`
- `GDI32!PatBlt` at `0x1800d4b03`
- `GDI32!PatBlt` at `0x1800d4c90`
- `GDI32!PatBlt` at `0x1800d4e8a`
- `GDI32!PatBlt` at `0x1800d4b03`
- `GDI32!PatBlt` at `0x1800d4c90`
- `GDI32!PatBlt` at `0x1800d4e8a`
- `GDI32!GdiFlush` at `0x1800d4485`
- `GDI32!GdiFlush` at `0x1800d4485`
- `GDI32!DeleteDC` at `0x1800d4f2e`
- `GDI32!DeleteDC` at `0x1800d4f2e`
- `GDI32!SelectObject` at `0x1800d4a84`
- `GDI32!SelectObject` at `0x1800d4ae0`
- `GDI32!SelectObject` at `0x1800d4b15`
- `GDI32!SelectObject` at `0x1800d4c64`
- `GDI32!SelectObject` at `0x1800d4e9b`
- `GDI32!SelectObject` at `0x1800d4a84`
- `GDI32!SelectObject` at `0x1800d4ae0`
- `GDI32!SelectObject` at `0x1800d4b15`
- `GDI32!SelectObject` at `0x1800d4c64`
- `GDI32!SelectObject` at `0x1800d4e9b`
- `GDI32!CreateCompatibleDC` at `0x1800d4a11`
- `GDI32!CreateCompatibleDC` at `0x1800d4a11`
- `GDI32!DeleteObject` at `0x1800d4f44`
- `GDI32!DeleteObject` at `0x1800d4f44`

## pseudocode

```c
__int64 __fastcall DriverNonPS::OutputBufferDIB(
        _DWORD *a1,
        HDC a2,
        struct DpContext *a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        struct DpPath *a7)
{
  unsigned int v7; // r14d
  EpScanDIB *v8; // rdi
  int ActualBounds; // eax
  int v12; // r12d
  int v13; // r8d
  int v14; // r13d
  EpScanDIB *v15; // rcx
  char *v16; // r9
  int SrcHeight; // edi
  int v18; // eax
  int v19; // r11d
  char *v20; // rdx
  int v21; // r8d
  int v22; // edx
  int v23; // r10d
  int v24; // ebx
  int v25; // eax
  HGDIOBJ v26; // r13
  int v27; // r12d
  char *v28; // rax
  _BYTE *v29; // rcx
  char *v30; // r9
  int v31; // edx
  _BYTE *v32; // rcx
  int DestHeight; // ecx
  int v34; // edx
  HDC v35; // r13
  int v36; // eax
  int v37; // edx
  int v39; // r8d
  int v40; // r9d
  int v41; // ebx
  int v42; // edx
  int v43; // ecx
  HBITMAP Bitmap; // rax
  HBRUSH GdiBrush; // rax
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // eax
  HBRUSH v49; // rax
  HGDIOBJ v50; // rax
  int v51; // r8d
  int v52; // edx
  int v53; // r8d
  char *v54; // r9
  int v55; // edx
  __int64 v56; // rax
  int v57; // r8d
  int v58; // edx
  int v59; // eax
  BOOL v60; // r12d
  void *lpBits; // [rsp+48h] [rbp-B8h]
  int v62; // [rsp+70h] [rbp-90h]
  unsigned int v63; // [rsp+70h] [rbp-90h]
  unsigned int v64; // [rsp+70h] [rbp-90h]
  unsigned int v65; // [rsp+70h] [rbp-90h]
  unsigned int v66; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+78h] [rbp-88h]
  unsigned int v69; // [rsp+78h] [rbp-88h]
  BOOL v70; // [rsp+78h] [rbp-88h]
  unsigned int v71; // [rsp+78h] [rbp-88h]
  unsigned int v72; // [rsp+78h] [rbp-88h]
  int v73; // [rsp+80h] [rbp-80h]
  unsigned int v74; // [rsp+80h] [rbp-80h]
  unsigned int v75; // [rsp+80h] [rbp-80h]
  int v77; // [rsp+94h] [rbp-6Ch]
  int v78; // [rsp+94h] [rbp-6Ch]
  int v79; // [rsp+98h] [rbp-68h]
  int SrcWidth; // [rsp+9Ch] [rbp-64h]
  int v81; // [rsp+9Ch] [rbp-64h]
  HDC hdcSrc; // [rsp+A0h] [rbp-60h]
  HDC hdcSrca; // [rsp+A0h] [rbp-60h]
  int v84; // [rsp+A8h] [rbp-58h]
  int xSrc; // [rsp+ACh] [rbp-54h]
  int v86; // [rsp+B0h] [rbp-50h] BYREF
  int v87; // [rsp+B4h] [rbp-4Ch]
  int DestWidth; // [rsp+B8h] [rbp-48h]
  int nHeight; // [rsp+BCh] [rbp-44h]
  HGDIOBJ h; // [rsp+C0h] [rbp-40h]
  HGDIOBJ ho; // [rsp+C8h] [rbp-38h]
  void *v92; // [rsp+D0h] [rbp-30h]
  __int64 v93; // [rsp+D8h] [rbp-28h]
  void *v94; // [rsp+E0h] [rbp-20h]
  EpScanDIB *v95; // [rsp+E8h] [rbp-18h]
  char *v96; // [rsp+F0h] [rbp-10h]
  struct DpPath *v97; // [rsp+F8h] [rbp-8h]
  _BYTE bmi[48]; // [rsp+100h] [rbp+0h] BYREF
  int v99; // [rsp+130h] [rbp+30h]
  _BYTE lpbmi[48]; // [rsp+138h] [rbp+38h] BYREF

  v7 = 0;
  v8 = *(EpScanDIB **)(a4 + 128);
  v93 = a5;
  v97 = a7;
  h = 0;
  v95 = v8;
  GdiFlush();
  ActualBounds = EpScanDIB::GetActualBounds(v8, (struct GpRuntime::GpRect *)&v86);
  v12 = nHeight;
  v13 = ActualBounds;
  v14 = DestWidth;
  v15 = v95;
  v77 = ActualBounds;
  hdcSrc = 0;
  v16 = (char *)*((_QWORD *)v95 + 185);
  SrcHeight = nHeight / a1[12];
  ho = 0;
  v96 = v16;
  v18 = DestWidth / a1[11];
  v94 = 0;
  SrcWidth = v18;
  v19 = v87 / a1[12];
  v84 = v19;
  v20 = (char *)*((_QWORD *)v95 + 172);
  xSrc = v86 / a1[11];
  v62 = *((_DWORD *)v95 + 372);
  v73 = *((_DWORD *)v95 + 332);
  v92 = v20;
  memset(bmi, 0, sizeof(bmi));
  v99 = 0;
  memset(lpbmi, 0, sizeof(lpbmi));
  if ( !a1[45] && v97 && !a1[40] && (a1[41] || a1[42]) )
  {
    DriverPrint::SetupPathClipping((DriverPrint *)a1, a2, a3, v97);
    v19 = v84;
    v15 = v95;
    v13 = v77;
    v20 = (char *)v92;
    v16 = v96;
  }
  if ( !v13 || !v14 || !v12 )
    goto LABEL_80;
  if ( v20 )
  {
    *(_OWORD *)bmi = *(_OWORD *)((char *)v15 + 1416);
    *(_OWORD *)&bmi[16] = *(_OWORD *)((char *)v15 + 1432);
    *(_OWORD *)&bmi[32] = *(_OWORD *)((char *)v15 + 1448);
    v99 = *((_DWORD *)v15 + 366);
  }
  if ( v16 )
  {
    *(_OWORD *)lpbmi = *(_OWORD *)((char *)v15 + 1492);
    *(_OWORD *)&lpbmi[16] = *(_OWORD *)((char *)v15 + 1508);
    *(_OWORD *)&lpbmi[32] = *(_OWORD *)((char *)v15 + 1524);
    if ( !AllWhite((const struct tagBITMAPINFO *)lpbmi, v16) )
    {
      v13 = v77;
      v20 = (char *)v92;
      goto LABEL_8;
    }
LABEL_80:
    v35 = a2;
    goto LABEL_25;
  }
LABEL_8:
  if ( a1[42] )
  {
    v21 = 0;
    v22 = xSrc;
    v23 = 0;
    v24 = xSrc + SrcWidth;
    v78 = 0;
    v79 = 0;
    *(_DWORD *)&bmi[8] = 1;
    *(_WORD *)&bmi[14] = 24;
    v25 = v19 + SrcHeight;
    v68 = v19 + SrcHeight;
    *(_DWORD *)&bmi[16] = 0;
    v81 = xSrc + SrcWidth;
    while ( 1 )
    {
      if ( v19 >= v25 )
        goto LABEL_47;
      v26 = 0;
      v27 = v22;
      h = 0;
      v28 = (char *)v92 + 4 * v22 + (unsigned int)(*((_DWORD *)v95 + 332) * (*(_DWORD *)(v93 + 12) - v19 - 1));
      v29 = 0;
      hdcSrca = 0;
      v30 = v28;
      ho = v28;
      while ( 1 )
      {
        if ( v27 >= v24 )
        {
          v35 = a2;
          goto LABEL_22;
        }
        v31 = *(_DWORD *)v28;
        v94 = v28 + 4;
        if ( HIBYTE(v31) <= 4u )
          break;
        if ( !v21 )
        {
          v79 = v27;
          v78 = 1;
          h = &v30[4 * v27];
          v29 = h;
        }
        *v29 = v31;
        v32 = v29 + 1;
        *v32++ = BYTE1(v31);
        *v32 = BYTE2(v31);
        v29 = v32 + 1;
        hdcSrca = (HDC)v29;
LABEL_15:
        v23 = v79;
        ++v27;
        v21 = v78;
        v28 = (char *)v94;
        v26 = h;
      }
      if ( !v21 )
        goto LABEL_15;
      DestHeight = a1[12];
      v74 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v74);
      v78 = 0;
      v34 = *a6 + a1[11] * v23;
      *(_DWORD *)&bmi[4] = v27 - v23;
      lpBits = v26;
      v35 = a2;
      v36 = StretchDIBits(
              a2,
              v34,
              a6[1] + v19 * DestHeight,
              a1[11] * (v27 - v23),
              DestHeight,
              0,
              0,
              v27 - v23,
              1,
              lpBits,
              (const BITMAPINFO *)bmi,
              0,
              0xCC0020u);
      v19 = v84;
      if ( v36 )
        break;
      v21 = 0;
      v7 = 1;
      v23 = v79;
      _mm_setcsr(v74);
LABEL_22:
      if ( v21 )
      {
        v75 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v75);
        v37 = *a6 + a1[11] * v23;
        v78 = 0;
        *(_DWORD *)&bmi[4] = v27 - v23;
        if ( !StretchDIBits(
                v35,
                v37,
                a6[1] + v19 * a1[12],
                a1[11] * (v27 - v23),
                a1[12],
                0,
                0,
                v27 - v23,
                1,
                h,
                (const BITMAPINFO *)bmi,
                0,
                0xCC0020u) )
        {
          v7 = 1;
          _mm_setcsr(v75);
          goto LABEL_25;
        }
        v19 = v84;
        v21 = 0;
        _mm_setcsr(v75);
      }
      v23 = v79;
      ++v19;
      v22 = xSrc;
      v25 = v68;
      v24 = v81;
      v84 = v19;
    }
    v29 = hdcSrca;
    v30 = (char *)ho;
    _mm_setcsr(v74);
    v24 = v81;
    goto LABEL_15;
  }
  if ( a1[40] || !a1[41] )
  {
    if ( a1[16] == 2 )
    {
      v41 = _mm_getcsr();
      _mm_setcsr(v41 & 0xFFFFFFC0);
      hdcSrc = CreateCompatibleDC(a2);
      if ( !hdcSrc )
      {
        v7 = 1;
        _mm_setcsr(v41 & 0xFFFFFFC0);
LABEL_47:
        v35 = a2;
        goto LABEL_25;
      }
      v42 = -v12;
      if ( v12 > 0 )
        v42 = v12;
      v43 = -v14;
      if ( v14 > 0 )
        v43 = v14;
      Bitmap = CreateBitmap(v43, v42, 1u, 1u, 0);
      ho = Bitmap;
      if ( !Bitmap )
      {
        v7 = 1;
        _mm_setcsr(v41 & 0xFFFFFFC0);
LABEL_76:
        if ( hdcSrc )
          DeleteDC(hdcSrc);
        if ( ho )
          DeleteObject(ho);
        goto LABEL_47;
      }
      SelectObject(hdcSrc, Bitmap);
      SetStretchBltMode(hdcSrc, 4);
      SetBrushOrgEx(hdcSrc, -*a6, -a6[1], 0);
      if ( a1[40] )
      {
        ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 22), a1[43], 0, 0);
        GdiBrush = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 22));
        h = SelectObject(hdcSrc, GdiBrush);
        v70 = PatBlt(hdcSrc, 0, 0, v14, v12, 0xF00021u);
        SelectObject(hdcSrc, h);
        v46 = v70;
      }
      else
      {
        v46 = StretchDIBits(
                hdcSrc,
                0,
                0,
                v14,
                v12,
                xSrc,
                *(_DWORD *)(v93 + 12) - v84 - SrcHeight,
                SrcWidth,
                SrcHeight,
                v92,
                (const BITMAPINFO *)bmi,
                0,
                0xCC0020u);
      }
      v47 = v41 & 0xFFFFFFC0;
      if ( !v46 )
      {
        v7 = 1;
        _mm_setcsr(v47);
        goto LABEL_76;
      }
      _mm_setcsr(v47);
      v71 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v71);
      SetBkColor(a2, 0xFFFFFFu);
      SetTextColor(a2, 0);
      v48 = StretchBlt(a2, *a6 + v86, a6[1] + v87, v14, v12, hdcSrc, 0, 0, v14, v12, 0x660046u);
      _mm_setcsr(v71);
    }
    else
    {
      if ( a1[40] )
      {
        v72 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v72);
        ConvertBrushToGdi::SetColor((ConvertBrushToGdi *)(a1 + 22), a1[43], 0, 0);
        v49 = ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)(a1 + 22));
        v50 = SelectObject(a2, v49);
        v51 = a6[1] + v87;
        v52 = *a6 + v86;
        h = v50;
        v48 = PatBlt(a2, v52, v51, v14, v12, 0x5A0049u);
      }
      else
      {
        v53 = a6[1] + v87;
        v72 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v72);
        *(_DWORD *)&bmi[8] = SrcHeight;
        v54 = &v20[v73 * (*(_DWORD *)(v93 + 12) - v19 - SrcHeight)];
        v55 = *a6 + v86;
        v94 = v54;
        v48 = StretchDIBits(
                a2,
                v55,
                v53,
                v14,
                v12,
                xSrc,
                0,
                SrcWidth,
                SrcHeight,
                v54,
                (const BITMAPINFO *)bmi,
                0,
                0x660046u);
      }
      _mm_setcsr(v72);
    }
    if ( !v48 )
    {
      v7 = 1;
      goto LABEL_76;
    }
    v56 = (unsigned int)(v62 * (a6[3] - v87 - v12));
    *(_DWORD *)&lpbmi[8] = v12;
    v63 = _mm_getcsr() & 0xFFFFFFC0;
    _mm_setcsr(v63);
    if ( !StretchDIBits(
            a2,
            v86 + *a6,
            v87 + a6[1],
            v14,
            v12,
            v86,
            0,
            v14,
            v12,
            &v96[v56],
            (const BITMAPINFO *)lpbmi,
            0,
            0x8800C6u) )
    {
      v7 = 1;
      _mm_setcsr(v63);
      goto LABEL_76;
    }
    v57 = a6[1] + v87;
    v58 = *a6 + v86;
    _mm_setcsr(v63);
    if ( hdcSrc )
    {
      v64 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v64);
      v59 = StretchBlt(a2, v58, v57, v14, v12, hdcSrc, 0, 0, v14, v12, 0x660046u);
      _mm_setcsr(v64);
    }
    else
    {
      if ( a1[40] )
      {
        v65 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v65);
        v60 = PatBlt(a2, v58, v57, v14, v12, 0x5A0049u);
        SelectObject(a2, h);
        _mm_setcsr(v65);
        goto LABEL_74;
      }
      v66 = _mm_getcsr() & 0xFFFFFFC0;
      _mm_setcsr(v66);
      v59 = StretchDIBits(
              a2,
              v58,
              v57,
              v14,
              v12,
              xSrc,
              0,
              SrcWidth,
              SrcHeight,
              v94,
              (const BITMAPINFO *)bmi,
              0,
              0x660046u);
      _mm_setcsr(v66);
    }
    v60 = v59;
LABEL_74:
    if ( !v60 )
      v7 = 1;
    goto LABEL_76;
  }
  if ( v14 <= 0 || v12 <= 0 )
  {
    v35 = a2;
  }
  else
  {
    v39 = a6[1] + v87;
    v69 = _mm_getcsr() & 0xFFFFFFC0;
    _mm_setcsr(v69);
    *(_DWORD *)&bmi[8] = SrcHeight;
    v40 = v14;
    v35 = a2;
    v13 = StretchDIBits(
            a2,
            *a6 + v86,
            v39,
            v40,
            v12,
            xSrc,
            0,
            SrcWidth,
            SrcHeight,
            &v20[v73 * (*(_DWORD *)(v93 + 12) - v19 - SrcHeight)],
            (const BITMAPINFO *)bmi,
            0,
            0xCC0020u);
    _mm_setcsr(v69);
  }
  LOBYTE(v7) = v13 == 0;
LABEL_25:
  if ( a1[45] == a1[46] - 1 && v97 && !a1[40] && (a1[41] || a1[42]) )
  {
    DriverPrint::RestoreClipping((DriverPrint *)a1, v35, a1[83], 0);
    a1[83] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800d4420  push    rbp
0x1800d4422  push    rbx
0x1800d4423  push    rsi
0x1800d4424  push    rdi
0x1800d4425  push    r12
0x1800d4427  push    r13
0x1800d4429  push    r14
0x1800d442b  push    r15
0x1800d442d  lea     rbp, [rsp-78h]
0x1800d4432  sub     rsp, 178h
0x1800d4439  mov     rax, cs:__security_cookie
0x1800d4440  xor     rax, rsp
0x1800d4443  mov     [rbp+0B0h+var_48], rax
0x1800d4447  mov     rax, [rbp+0B0h+arg_20]
0x1800d444e  xor     r14d, r14d
0x1800d4451  mov     rdi, [r9+80h]
0x1800d4458  mov     rbx, rdx
0x1800d445b  mov     r15, [rbp+0B0h+arg_28]
0x1800d4462  mov     rsi, rcx
0x1800d4465  mov     [rbp+0B0h+var_D8], rax
0x1800d4469  mov     rax, [rbp+0B0h+arg_30]
0x1800d4470  mov     [rbp+0B0h+var_B8], rax
0x1800d4474  mov     [rsp+1B0h+var_138], r8
0x1800d4479  mov     [rbp+0B0h+hdc], rdx
0x1800d447d  mov     [rbp+0B0h+h], r14
0x1800d4481  mov     [rbp+0B0h+var_C8], rdi
0x1800d4485  call    cs:__imp_GdiFlush
0x1800d448b  lea     rdx, [rbp+0B0h+var_100]; struct GpRuntime::GpRect *
0x1800d448f  mov     rcx, rdi; this
0x1800d4492  call    ?GetActualBounds@EpScanDIB@@QEAAHPEAVGpRect@GpRuntime@@@Z; EpScanDIB::GetActualBounds(GpRuntime::GpRect *)
0x1800d4497  mov     r12d, [rbp+0B0h+nHeight]
0x1800d449b  mov     r8d, eax
0x1800d449e  mov     r13d, [rbp+0B0h+DestWidth]
0x1800d44a2  xorps   xmm0, xmm0
0x1800d44a5  mov     rcx, [rbp+0B0h+var_C8]
0x1800d44a9  mov     [rbp+0B0h+var_11C], eax
0x1800d44ac  mov     eax, r12d
0x1800d44af  cdq
0x1800d44b0  mov     [rbp+0B0h+hdcSrc], r14
0x1800d44b4  idiv    dword ptr [rsi+30h]
0x1800d44b7  mov     r9, [rcx+5C8h]
0x1800d44be  mov     edi, eax
0x1800d44c0  mov     [rbp+0B0h+var_118], eax
0x1800d44c3  mov     eax, r13d
0x1800d44c6  mov     [rbp+0B0h+ho], r14
0x1800d44ca  cdq
0x1800d44cb  mov     [rbp+0B0h+var_C0], r9
0x1800d44cf  idiv    dword ptr [rsi+2Ch]
0x1800d44d2  mov     [rbp+0B0h+var_D0], r14
0x1800d44d6  mov     [rbp+0B0h+var_114], eax
0x1800d44d9  mov     eax, [rbp+0B0h+var_FC]
0x1800d44dc  cdq
0x1800d44dd  idiv    dword ptr [rsi+30h]
0x1800d44e0  mov     r11d, eax
0x1800d44e3  mov     [rbp+0B0h+var_108], eax
0x1800d44e6  mov     eax, [rbp+0B0h+var_100]
0x1800d44e9  cdq
0x1800d44ea  idiv    dword ptr [rsi+2Ch]
0x1800d44ed  mov     rdx, [rcx+560h]
0x1800d44f4  mov     [rbp+0B0h+var_104], eax
0x1800d44f7  mov     eax, [rcx+5D0h]
0x1800d44fd  mov     [rsp+1B0h+var_140], eax
0x1800d4501  mov     eax, [rcx+530h]
0x1800d4507  mov     [rbp+0B0h+var_130], eax
0x1800d450a  xor     eax, eax
0x1800d450c  mov     [rbp+0B0h+var_E0], rdx
0x1800d4510  movups  xmmword ptr [rbp+0B0h+bmi], xmm0
0x1800d4514  mov     [rbp+0B0h+var_80], eax
0x1800d4517  movups  xmmword ptr [rbp+0B0h+bmi+10h], xmm0
0x1800d451b  movups  xmmword ptr [rbp+0B0h+bmi+20h], xmm0
0x1800d451f  movups  xmmword ptr [rbp+0B0h+var_78], xmm0
0x1800d4523  movups  xmmword ptr [rbp+0B0h+var_78+10h], xmm0
0x1800d4527  movups  xmmword ptr [rbp+0B0h+var_78+20h], xmm0
0x1800d452b  cmp     [rsi+0B4h], eax
0x1800d4531  jz      loc_1800D4800
0x1800d4537  test    r8d, r8d
0x1800d453a  jz      loc_1800D4F4F
0x1800d4540  test    r13d, r13d
0x1800d4543  jz      loc_1800D4F4F
0x1800d4549  test    r12d, r12d
0x1800d454c  jz      loc_1800D4F4F
0x1800d4552  test    rdx, rdx
0x1800d4555  jnz     loc_1800D485C
0x1800d455b  test    r9, r9
0x1800d455e  jnz     loc_1800D488B
0x1800d4564  cmp     [rsi+0A8h], r14d
0x1800d456b  jz      loc_1800D4910
0x1800d4571  mov     ebx, [rbp+0B0h+var_114]
0x1800d4574  xor     r8d, r8d
0x1800d4577  mov     edx, [rbp+0B0h+var_104]
0x1800d457a  xor     r10d, r10d
0x1800d457d  add     ebx, edx
0x1800d457f  mov     [rbp+0B0h+var_11C], r8d
0x1800d4583  mov     [rbp+0B0h+var_118], r10d
0x1800d4587  lea     eax, [r8+18h]
0x1800d458b  mov     dword ptr [rbp+0B0h+bmi+8], 1
0x1800d4592  mov     word ptr [rbp+0B0h+bmi+0Eh], ax
0x1800d4596  lea     eax, [r11+rdi]
0x1800d459a  mov     dword ptr [rsp+1B0h+var_138], eax
0x1800d459e  mov     edi, 0FFFFFFC0h
0x1800d45a3  mov     dword ptr [rbp+0B0h+bmi+10h], r8d
0x1800d45a7  mov     [rbp+0B0h+var_114], ebx
0x1800d45aa  cmp     r11d, eax
0x1800d45ad  jge     loc_1800D4A2F
0x1800d45b3  mov     rax, [rbp+0B0h+var_D8]
0x1800d45b7  xor     r13d, r13d
0x1800d45ba  mov     rcx, [rbp+0B0h+var_C8]
0x1800d45be  mov     r12d, edx
0x1800d45c1  mov     [rbp+0B0h+h], r13
0x1800d45c5  mov     eax, [rax+0Ch]
0x1800d45c8  sub     eax, r11d
0x1800d45cb  dec     eax
0x1800d45cd  imul    eax, [rcx+530h]
0x1800d45d4  movsxd  rcx, edx
0x1800d45d7  add     rax, [rbp+0B0h+var_E0]
0x1800d45db  lea     rax, [rax+rcx*4]
0x1800d45df  xor     ecx, ecx
0x1800d45e1  mov     [rbp+0B0h+hdcSrc], rcx
0x1800d45e5  mov     r9, rax
0x1800d45e8  mov     [rbp+0B0h+ho], rax
0x1800d45ec  cmp     r12d, ebx
0x1800d45ef  jge     loc_1800D4716
0x1800d45f5  mov     edx, [rax]
0x1800d45f7  add     rax, 4
0x1800d45fb  mov     [rbp+0B0h+var_D0], rax
0x1800d45ff  mov     eax, edx
0x1800d4601  shr     eax, 18h
0x1800d4604  cmp     al, 4
0x1800d4606  ja      short loc_1800D4628
0x1800d4608  test    r8d, r8d
0x1800d460b  jnz     short loc_1800D4666
0x1800d460d  mov     r8d, 1
0x1800d4613  mov     r10d, [rbp+0B0h+var_118]
0x1800d4617  add     r12d, r8d
0x1800d461a  mov     r8d, [rbp+0B0h+var_11C]
0x1800d461e  mov     rax, [rbp+0B0h+var_D0]
0x1800d4622  mov     r13, [rbp+0B0h+h]
0x1800d4626  jmp     short loc_1800D45EC
0x1800d4628  test    r8d, r8d
0x1800d462b  mov     r8d, 1
0x1800d4631  jnz     short loc_1800D4649
0x1800d4633  movsxd  rax, r12d
0x1800d4636  mov     [rbp+0B0h+var_118], r12d
0x1800d463a  mov     [rbp+0B0h+var_11C], r8d
0x1800d463e  lea     r13, [r9+rax*4]
0x1800d4642  mov     [rbp+0B0h+h], r13
0x1800d4646  mov     rcx, r13
0x1800d4649  mov     [rcx], dl
0x1800d464b  mov     eax, edx
0x1800d464d  add     rcx, r8
0x1800d4650  shr     eax, 8
0x1800d4653  shr     edx, 10h
0x1800d4656  mov     [rcx], al
0x1800d4658  add     rcx, r8
0x1800d465b  mov     [rcx], dl
0x1800d465d  add     rcx, r8
0x1800d4660  mov     [rbp+0B0h+hdcSrc], rcx
0x1800d4664  jmp     short loc_1800D4613
0x1800d4666  stmxcsr [rbp+0B0h+var_130]
0x1800d466a  mov     ebx, [rbp+0B0h+var_130]
0x1800d466d  mov     edx, r10d
0x1800d4670  mov     ecx, [rsi+30h]
0x1800d4673  mov     eax, ebx
0x1800d4675  imul    edx, [rsi+2Ch]
0x1800d4679  and     eax, edi
0x1800d467b  mov     [rsp+1B0h+rop], 0CC0020h; rop
0x1800d4683  mov     r8d, ecx
0x1800d4686  mov     [rbp+0B0h+var_130], eax
0x1800d4689  xor     eax, eax
0x1800d468b  ldmxcsr [rbp+0B0h+var_130]
0x1800d468f  mov     [rbp+0B0h+var_11C], eax
0x1800d4692  mov     eax, r12d
0x1800d4695  add     edx, [r15]; xDest
0x1800d4698  sub     eax, r10d
0x1800d469b  mov     dword ptr [rbp+0B0h+bmi+4], eax
0x1800d469e  mov     eax, r12d
0x1800d46a1  sub     eax, r10d
0x1800d46a4  imul    r8d, r11d
0x1800d46a8  xor     r11d, r11d
0x1800d46ab  lea     r10, [rbp+0B0h+bmi]
0x1800d46af  mov     [rsp+1B0h+iUsage], r11d; iUsage
0x1800d46b4  mov     r9d, eax
0x1800d46b7  imul    r9d, [rsi+2Ch]; DestWidth
0x1800d46bc  mov     [rsp+1B0h+lpbmi], r10; lpbmi
0x1800d46c1  add     r8d, [r15+4]; yDest
0x1800d46c5  mov     [rsp+1B0h+lpBits], r13; lpBits
0x1800d46ca  mov     r13, [rbp+0B0h+hdc]
0x1800d46ce  mov     [rsp+1B0h+SrcHeight], 1; SrcHeight
0x1800d46d6  mov     [rsp+1B0h+SrcWidth], eax; SrcWidth
0x1800d46da  mov     [rsp+1B0h+ySrc], r11d; ySrc
0x1800d46df  mov     [rsp+1B0h+xSrc], r11d; xSrc
0x1800d46e4  mov     [rsp+1B0h+DestHeight], ecx; DestHeight
0x1800d46e8  mov     rcx, r13; hdc
0x1800d46eb  call    cs:__imp_StretchDIBits
0x1800d46f1  mov     r11d, [rbp+0B0h+var_108]
0x1800d46f5  and     ebx, edi
0x1800d46f7  test    eax, eax
0x1800d46f9  jz      loc_1800D48CD
0x1800d46ff  mov     rcx, [rbp+0B0h+hdcSrc]
0x1800d4703  mov     r9, [rbp+0B0h+ho]
0x1800d4707  mov     [rbp+0B0h+var_130], ebx
0x1800d470a  ldmxcsr [rbp+0B0h+var_130]
0x1800d470e  mov     ebx, [rbp+0B0h+var_114]
0x1800d4711  jmp     loc_1800D460D
0x1800d4716  mov     r13, [rbp+0B0h+hdc]
0x1800d471a  test    r8d, r8d
0x1800d471d  jz      loc_1800D48F6
0x1800d4723  stmxcsr [rbp+0B0h+var_130]
0x1800d4727  mov     ebx, [rbp+0B0h+var_130]
0x1800d472a  lea     rcx, [rbp+0B0h+bmi]
0x1800d472e  mov     [rsp+1B0h+rop], 0CC0020h; rop
0x1800d4736  mov     eax, ebx
0x1800d4738  mov     [rsp+1B0h+iUsage], 0; iUsage
0x1800d4740  and     eax, edi
0x1800d4742  mov     [rsp+1B0h+lpbmi], rcx; lpbmi
0x1800d4747  mov     edx, r10d
0x1800d474a  imul    edx, [rsi+2Ch]
0x1800d474e  mov     rcx, [rbp+0B0h+h]
0x1800d4752  mov     [rsp+1B0h+lpBits], rcx; lpBits
0x1800d4757  mov     rcx, r13; hdc
0x1800d475a  mov     [rbp+0B0h+var_130], eax
0x1800d475d  xor     eax, eax
0x1800d475f  ldmxcsr [rbp+0B0h+var_130]
0x1800d4763  add     edx, [r15]; xDest
0x1800d4766  mov     [rbp+0B0h+var_11C], eax
0x1800d4769  mov     eax, r12d
0x1800d476c  mov     [rsp+1B0h+SrcHeight], 1; SrcHeight
0x1800d4774  sub     eax, r10d
0x1800d4777  sub     r12d, r10d
0x1800d477a  mov     dword ptr [rbp+0B0h+bmi+4], eax
0x1800d477d  mov     eax, [rsi+30h]
0x1800d4780  mov     r9d, r12d
0x1800d4783  imul    r9d, [rsi+2Ch]; DestWidth
0x1800d4788  mov     r8d, eax
0x1800d478b  mov     [rsp+1B0h+SrcWidth], r12d; SrcWidth
0x1800d4790  imul    r8d, r11d
0x1800d4794  mov     [rsp+1B0h+ySrc], 0; ySrc
0x1800d479c  mov     [rsp+1B0h+xSrc], 0; xSrc
0x1800d47a4  mov     [rsp+1B0h+DestHeight], eax; DestHeight
0x1800d47a8  add     r8d, [r15+4]; yDest
0x1800d47ac  call    cs:__imp_StretchDIBits
0x1800d47b2  and     ebx, edi
0x1800d47b4  test    eax, eax
0x1800d47b6  jnz     loc_1800D48E7
0x1800d47bc  mov     dword ptr [rsp+1B0h+var_138], ebx
0x1800d47c0  lea     r14d, [rax+1]
0x1800d47c4  ldmxcsr dword ptr [rsp+1B0h+var_138]
0x1800d47c9  mov     eax, [rsi+0B8h]
0x1800d47cf  dec     eax
0x1800d47d1  cmp     [rsi+0B4h], eax
0x1800d47d7  jz      loc_1800D4F57
0x1800d47dd  mov     eax, r14d
0x1800d47e0  mov     rcx, [rbp+0B0h+var_48]
0x1800d47e4  xor     rcx, rsp; StackCookie
0x1800d47e7  call    __security_check_cookie
0x1800d47ec  add     rsp, 178h
0x1800d47f3  pop     r15
0x1800d47f5  pop     r14
0x1800d47f7  pop     r13
0x1800d47f9  pop     r12
0x1800d47fb  pop     rdi
0x1800d47fc  pop     rsi
0x1800d47fd  pop     rbx
0x1800d47fe  pop     rbp
0x1800d47ff  retn
0x1800d4800  mov     rax, [rbp+0B0h+var_B8]
0x1800d4804  test    rax, rax
0x1800d4807  jz      loc_1800D4537
0x1800d480d  cmp     [rsi+0A0h], r14d
0x1800d4814  jnz     loc_1800D4537
0x1800d481a  cmp     [rsi+0A4h], r14d
0x1800d4821  jnz     short loc_1800D4830
0x1800d4823  cmp     [rsi+0A8h], r14d
0x1800d482a  jz      loc_1800D4537
0x1800d4830  mov     r8, [rsp+1B0h+var_138]; struct DpContext *
0x1800d4835  mov     r9, rax; struct DpPath *
0x1800d4838  mov     rdx, rbx; HDC
0x1800d483b  mov     rcx, rsi; this
0x1800d483e  call    ?SetupPathClipping@DriverPrint@@MEAAXPEAUHDC__@@PEAVDpContext@@PEBVDpPath@@@Z; DriverPrint::SetupPathClipping(HDC__ *,DpContext *,DpPath const *)
0x1800d4843  mov     r11d, [rbp+0B0h+var_108]
0x1800d4847  mov     rcx, [rbp+0B0h+var_C8]
0x1800d484b  mov     r8d, [rbp+0B0h+var_11C]
0x1800d484f  mov     rdx, [rbp+0B0h+var_E0]
0x1800d4853  mov     r9, [rbp+0B0h+var_C0]
0x1800d4857  jmp     loc_1800D4537
0x1800d485c  movups  xmm0, xmmword ptr [rcx+588h]
0x1800d4863  movups  xmmword ptr [rbp+0B0h+bmi], xmm0
0x1800d4867  movups  xmm1, xmmword ptr [rcx+598h]
0x1800d486e  movups  xmmword ptr [rbp+0B0h+bmi+10h], xmm1
0x1800d4872  movups  xmm0, xmmword ptr [rcx+5A8h]
0x1800d4879  movups  xmmword ptr [rbp+0B0h+bmi+20h], xmm0
0x1800d487d  mov     eax, [rcx+5B8h]
0x1800d4883  mov     [rbp+0B0h+var_80], eax
0x1800d4886  jmp     loc_1800D455B
0x1800d488b  movups  xmm0, xmmword ptr [rcx+5D4h]
0x1800d4892  mov     rdx, r9; void *
0x1800d4895  movups  xmmword ptr [rbp+0B0h+var_78], xmm0
0x1800d4899  movups  xmm1, xmmword ptr [rcx+5E4h]
0x1800d48a0  movups  xmmword ptr [rbp+0B0h+var_78+10h], xmm1
0x1800d48a4  movups  xmm0, xmmword ptr [rcx+5F4h]
  ... truncated ...
```
