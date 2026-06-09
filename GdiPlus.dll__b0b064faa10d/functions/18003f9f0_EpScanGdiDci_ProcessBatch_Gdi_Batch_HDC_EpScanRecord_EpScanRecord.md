# EpScanGdiDci::ProcessBatch_Gdi_Batch(HDC__ *,EpScanRecord *,EpScanRecord *)

- ea: `0x18003f9f0`
- end: `0x18004041b`
- name: `?ProcessBatch_Gdi_Batch@EpScanGdiDci@@AEAAXPEAUHDC__@@PEAUEpScanRecord@@1@Z`
- size: `2603`
- prototype: `void(EpScanGdiDci *__hidden this, HDC, struct EpScanRecord *, struct EpScanRecord *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003dbc0`

## callees

- `0x18003f9f0`
- `0x18004050c`
- `0x1800415b8`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003fcbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003fcbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fc66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fc66`
- `GDI32!StretchBlt` at `0x18003ff0c`
- `GDI32!StretchBlt` at `0x180040101`
- `GDI32!StretchBlt` at `0x18003ff0c`
- `GDI32!StretchBlt` at `0x180040101`
- `GDI32!CreateDIBSection` at `0x18003fc2d`
- `GDI32!CreateDIBSection` at `0x18003fc2d`
- `GDI32!SelectObject` at `0x18003fc4b`
- `GDI32!SelectObject` at `0x18003fc4b`
- `GDI32!DeleteObject` at `0x18003fad2`
- `GDI32!DeleteObject` at `0x18003fad2`
- `GDI32!GetDCOrgEx` at `0x18003fa48`
- `GDI32!GetDCOrgEx` at `0x18003fa48`
- `GDI32!GetDeviceCaps` at `0x18003fb2b`
- `GDI32!GetDeviceCaps` at `0x18003fb2b`

## pseudocode

```c
void __fastcall EpScanGdiDci::ProcessBatch_Gdi_Batch(
        EpScanGdiDci *this,
        HDC a2,
        struct EpScanRecord *a3,
        struct EpScanRecord *a4)
{
  struct EpScanRecord *v4; // rdi
  EpScanGdiDci *v5; // rbx
  int v6; // esi
  int v7; // r9d
  int v8; // r11d
  int v9; // r10d
  int v10; // r8d
  __int64 v11; // rsi
  int PixelFormatFromHDC; // r14d
  void *v13; // rcx
  __int64 v14; // r13
  HDC v15; // r15
  int v16; // ecx
  DWORD biCompression; // edx
  WORD biBitCount; // r8
  HBITMAP v19; // rax
  HDC v20; // rcx
  void *v21; // r8
  char *v22; // r8
  int v23; // esi
  __int64 v24; // rcx
  int v25; // r8d
  __int64 v26; // rdx
  __m128i si128; // xmm6
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // r14d
  int v38; // r15d
  int v39; // esi
  unsigned int v40; // r9d
  int v41; // esi
  int v42; // edx
  int v43; // r13d
  __int64 v44; // r8
  size_t v45; // r12
  void *v46; // rsi
  __int16 v47; // ax
  char *v48; // r15
  int v49; // edx
  int v50; // r13d
  __int64 v51; // rcx
  char *v52; // r14
  char *v53; // rbx
  char *v54; // r9
  __int64 v55; // rcx
  void *v56; // rdx
  void (__fastcall *v57)(__int64, void *, _QWORD, char *); // rax
  __int64 v58; // rbx
  int v59; // ecx
  __int64 v60; // rdx
  __int64 v61; // r8
  char *v62; // r8
  __int64 v63; // rax
  unsigned int v64; // r9d
  int v65; // ecx
  char *v66; // r15
  __int64 v67; // rax
  char *v68; // rdi
  char *v69; // r14
  void *v70; // rdx
  char *v71; // r9
  __int64 v72; // rcx
  void (__fastcall *v73)(__int64, void *, _QWORD, char *); // rax
  char *v74; // rcx
  char *v75; // rdx
  char *v76; // rcx
  unsigned __int64 v77; // rax
  int v78; // edx
  int v79; // eax
  int v80; // edx
  int v81; // eax
  unsigned int v82; // r11d
  RGBQUAD *bmiColors; // r9
  __int64 v84; // r10
  int v85; // ecx
  int offset; // [rsp+28h] [rbp-D8h]
  int offseta; // [rsp+28h] [rbp-D8h]
  int xSrc; // [rsp+30h] [rbp-D0h]
  int xSrca; // [rsp+30h] [rbp-D0h]
  int ySrc; // [rsp+38h] [rbp-C8h]
  int ySrca; // [rsp+38h] [rbp-C8h]
  int wSrc[2]; // [rsp+40h] [rbp-C0h]
  int v93; // [rsp+80h] [rbp-80h]
  int v94; // [rsp+84h] [rbp-7Ch]
  int v95; // [rsp+88h] [rbp-78h]
  unsigned __int16 v96; // [rsp+88h] [rbp-78h]
  int hDest; // [rsp+8Ch] [rbp-74h]
  struct EpScanRecord *v98; // [rsp+90h] [rbp-70h]
  unsigned __int64 v99; // [rsp+90h] [rbp-70h]
  LONG v100; // [rsp+98h] [rbp-68h]
  int v101; // [rsp+9Ch] [rbp-64h]
  int v102; // [rsp+A0h] [rbp-60h]
  int v103; // [rsp+A4h] [rbp-5Ch]
  unsigned int v104; // [rsp+A8h] [rbp-58h]
  int v105; // [rsp+ACh] [rbp-54h]
  int v106; // [rsp+B0h] [rbp-50h]
  int wDest; // [rsp+B4h] [rbp-4Ch]
  int yDest; // [rsp+B8h] [rbp-48h]
  int xDest; // [rsp+BCh] [rbp-44h]
  HDC hdcDest; // [rsp+C8h] [rbp-38h]
  char *v113; // [rsp+D8h] [rbp-28h] BYREF
  char *v114; // [rsp+E0h] [rbp-20h]
  int v115; // [rsp+E8h] [rbp-18h]
  __m128i v116; // [rsp+F0h] [rbp-10h]
  int v117; // [rsp+100h] [rbp+0h]
  int v118; // [rsp+104h] [rbp+4h]
  __int64 v119; // [rsp+108h] [rbp+8h]
  struct EpScanRecord *v120; // [rsp+110h] [rbp+10h]
  BITMAPINFO pbmi; // [rsp+120h] [rbp+20h] BYREF
  int v122; // [rsp+14Ch] [rbp+4Ch]
  int v123; // [rsp+150h] [rbp+50h]

  v4 = a3;
  v98 = a3;
  v5 = this;
  v6 = *(_DWORD *)(*((_QWORD *)this + 164) + 776LL);
  v95 = v6;
  v120 = a4;
  GetDCOrgEx(a2, (LPPOINT)((char *)this + 1404));
  v7 = *((_DWORD *)v5 + 342);
  v8 = *((_DWORD *)v5 + 343);
  v9 = *((_DWORD *)v5 + 344);
  v10 = *((_DWORD *)v5 + 345);
  if ( v6 > 1 )
  {
    if ( v8 < v7 || v10 < v9 )
      return;
    v7 -= v7 % v6;
    v78 = (v8 - v7) % v6;
    v79 = 0;
    if ( v78 > 0 )
      v79 = v6 - v78;
    v8 += v79;
    v9 -= v9 % v6;
    v80 = (v10 - v9 + 1) % v6;
    v81 = 0;
    if ( v80 > 0 )
      v81 = v6 - v80;
    v10 += v81;
  }
  v11 = *((_QWORD *)v5 + 163);
  v93 = v7;
  v94 = v9;
  if ( Globals::g_fClientSession )
    PixelFormatFromHDC = *((_DWORD *)Globals::g_pRemoteSurface + 3);
  else
    PixelFormatFromHDC = 0;
  v13 = *(void **)(v11 + 16);
  v100 = v8 - v7;
  v14 = *(_QWORD *)(*((_QWORD *)v5 + 164) + 664LL);
  hDest = v10 - v9 + 1;
  if ( v13 )
    DeleteObject(v13);
  if ( !v14 )
    v14 = *(_QWORD *)(v11 + 1576);
  v15 = *(HDC *)(v11 + 1504);
  memset_0(&pbmi, 0, 0x428u);
  if ( !PixelFormatFromHDC )
    PixelFormatFromHDC = ExtractPixelFormatFromHDC(v15);
  *(_DWORD *)(v11 + 80) = PixelFormatFromHDC;
  if ( (PixelFormatFromHDC & 0x10000) != 0 )
    *(_DWORD *)(v11 + 80) = 198659;
  if ( GetDeviceCaps(v15, 2) == 2 && (*(_DWORD *)(v11 + 80) & 0x10000) != 0 || (v16 = *(_DWORD *)(v11 + 80)) == 0 )
  {
    LOBYTE(v16) = 9;
    pbmi.bmiHeader.biSize = 40;
    *(_DWORD *)(v11 + 80) = 139273;
    pbmi.bmiHeader.biHeight = 0;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    biBitCount = 32;
    goto LABEL_16;
  }
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biHeight = 0;
  pbmi.bmiHeader.biPlanes = 1;
  pbmi.bmiHeader.biBitCount = BYTE1(v16);
  biCompression = 0;
  pbmi.bmiHeader.biCompression = 0;
  biBitCount = BYTE1(v16);
  if ( (v16 & 0x10000) == 0 )
  {
    if ( (((v16 & 0xFF00) - 4096) & 0xFFFFEFFF) != 0 )
    {
LABEL_17:
      pbmi.bmiColors[0] = (RGBQUAD)dword_1801809C0[(unsigned __int8)v16];
      v122 = dword_180180970[(unsigned __int8)v16];
      v123 = dword_180180920[(unsigned __int8)v16];
      goto LABEL_18;
    }
LABEL_16:
    biCompression = 3;
    pbmi.bmiHeader.biCompression = 3;
    goto LABEL_17;
  }
  if ( v14 )
  {
    v82 = *(_DWORD *)(v14 + 4);
    bmiColors = pbmi.bmiColors;
    v84 = 0;
    if ( v82 )
    {
      do
      {
        v85 = *(_DWORD *)(v14 + 4 * v84 + 8);
        v84 = (unsigned int)(v84 + 1);
        bmiColors->rgbRed = BYTE2(v85);
        *(_WORD *)&bmiColors->rgbBlue = v85;
        ++bmiColors;
      }
      while ( (unsigned int)v84 < v82 );
      biCompression = pbmi.bmiHeader.biCompression;
      biBitCount = pbmi.bmiHeader.biBitCount;
    }
  }
LABEL_18:
  pbmi.bmiHeader.biWidth = v100;
  if ( hDest < 0 )
  {
    *(_QWORD *)(v11 + 16) = 0;
    goto LABEL_91;
  }
  pbmi.bmiHeader.biHeight = -hDest;
  if ( !biCompression )
  {
LABEL_89:
    pbmi.bmiHeader.biSizeImage = 0;
    goto LABEL_23;
  }
  if ( biBitCount != 16 )
  {
    if ( biBitCount == 32 )
    {
      pbmi.bmiHeader.biSizeImage = 4 * hDest * v100;
      goto LABEL_23;
    }
    goto LABEL_89;
  }
  pbmi.bmiHeader.biSizeImage = 2 * hDest * v100;
LABEL_23:
  *(_QWORD *)&pbmi.bmiHeader.biClrUsed = 0;
  v19 = CreateDIBSection(v15, &pbmi, 0, (void **)(v11 + 32), 0, 0);
  *(_QWORD *)(v11 + 16) = v19;
  if ( v19 )
  {
    v20 = *(HDC *)(v11 + 24);
    *(_DWORD *)(v11 + 12) = v100;
    SelectObject(v20, v19);
    goto LABEL_25;
  }
LABEL_91:
  *(_DWORD *)(v11 + 12) = 0;
LABEL_25:
  v21 = *(void **)(v11 + 40);
  if ( v21 )
  {
    HeapFree(GpRuntime::GpMemHeap, 0, v21);
    *(_QWORD *)(v11 + 40) = 0;
  }
  if ( v100 < 0 )
  {
    v22 = 0;
    *(_QWORD *)(v11 + 40) = 0;
LABEL_32:
    *(_DWORD *)(v11 + 12) = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int64)(5LL * v100) > 0x1FFFFFFFFFFFFFFFLL )
    v22 = 0;
  else
    v22 = (char *)HeapAlloc(GpRuntime::GpMemHeap, 0, 40LL * v100);
  *(_QWORD *)(v11 + 40) = v22;
  if ( !v22 )
    goto LABEL_32;
  v74 = &v22[8 * v100];
  *(_QWORD *)(v11 + 48) = v74;
  v75 = &v74[8 * v100];
  v76 = &v75[8 * v100];
  *(_QWORD *)(v11 + 56) = v75;
  *(_QWORD *)(v11 + 64) = v76;
  *(_QWORD *)(v11 + 72) = &v76[8 * v100];
LABEL_33:
  v119 = *(_QWORD *)(v11 + 32);
  hdcDest = *(HDC *)(v11 + 24);
  if ( v5 != (EpScanGdiDci *)-1328LL )
  {
    *((_QWORD *)v5 + 166) = v22;
    *((_QWORD *)v5 + 167) = *(_QWORD *)(v11 + 48);
    *((_QWORD *)v5 + 168) = *(_QWORD *)(v11 + 56);
    *((_QWORD *)v5 + 169) = *(_QWORD *)(v11 + 64);
    *((_QWORD *)v5 + 170) = *(_QWORD *)(v11 + 72);
  }
  if ( *(_DWORD *)(v11 + 12) )
  {
    v23 = *(_DWORD *)(v11 + 80);
    if ( v23 )
    {
      v24 = *((_QWORD *)v5 + 164);
      v25 = *((_DWORD *)v5 + 355);
      v26 = *(_QWORD *)(v24 + 664);
      if ( !v26 )
        v26 = *(_QWORD *)(*((_QWORD *)v5 + 163) + 1576LL);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v28 = *((unsigned int *)v5 + 162);
      v113 = (char *)v5 + 168;
      *(_QWORD *)wSrc = v26;
      v29 = *((unsigned int *)v5 + 163);
      ySrc = *(_DWORD *)(v24 + 44);
      xSrc = *(_DWORD *)(v24 + 32);
      offset = *(_DWORD *)(v24 + 28);
      v30 = *(_QWORD *)(v24 + 672);
      v114 = (char *)v5 + 1328;
      v116 = si128;
      v115 = 0;
      v117 = 1;
      v118 = 2;
      EpAlphaBlender::BuildPipeline(
        (char *)v5 + 24,
        v29,
        (unsigned int)v23,
        v28,
        v30,
        offset,
        xSrc,
        ySrc,
        *(_QWORD *)wSrc,
        (char *)v5 + 1328,
        1,
        1,
        v25,
        &v113,
        1);
      *((_QWORD *)v113 - 1) = 0;
      v31 = *((_QWORD *)v5 + 164);
      v32 = *((_DWORD *)v5 + 355);
      v33 = *(_QWORD *)(v31 + 664);
      if ( !v33 )
        v33 = *(_QWORD *)(*((_QWORD *)v5 + 163) + 1576LL);
      v34 = *((unsigned int *)v5 + 320);
      v113 = (char *)v5 + 800;
      ySrca = *(_DWORD *)(v31 + 44);
      xSrca = *(_DWORD *)(v31 + 32);
      offseta = *(_DWORD *)(v31 + 28);
      v35 = *(_QWORD *)(v31 + 672);
      v36 = *((unsigned int *)v5 + 321);
      v114 = (char *)v5 + 1328;
      v116 = si128;
      v115 = 0;
      v117 = 1;
      v118 = 2;
      EpAlphaBlender::BuildPipeline(
        (char *)v5 + 656,
        v36,
        (unsigned int)v23,
        v34,
        v35,
        offseta,
        xSrca,
        ySrca,
        v33,
        (char *)v5 + 1328,
        1,
        1,
        v32,
        &v113,
        1);
      v37 = v93;
      *((_QWORD *)v113 - 1) = 0;
      v38 = v94;
      v102 = *((_DWORD *)v5 + 4);
      v103 = *((_DWORD *)v5 + 5);
      v106 = hDest / v95;
      wDest = v100 / v95;
      yDest = v94 / v95;
      xDest = v93 / v95;
      StretchBlt(hdcDest, 0, 0, v100, hDest, a2, v93 / v95, v94 / v95, v100 / v95, hDest / v95, 0xCC0020u);
      v39 = v23 >> 8;
      if ( (_BYTE)v39 )
      {
        if ( v100 <= 0x7FFFFFF8u / (unsigned __int8)v39 )
        {
          v40 = (((v100 * (unsigned int)(unsigned __int8)v39 + 7) >> 3) + 3) & 0xFFFFFFFC;
          v104 = v40;
          if ( v40 )
          {
            v41 = (unsigned __int8)(v39 & 0xF8) >> 3;
            v105 = v41;
            while ( 1 )
            {
              v42 = *((_DWORD *)v5 + 354) + *((_DWORD *)v4 + 2);
              v43 = *((_DWORD *)v5 + 353) + *((_DWORD *)v4 + 1);
              v44 = *(unsigned __int16 *)v4;
              v45 = *((int *)v4 + 3);
              v96 = *(_WORD *)v4;
              v101 = v42;
              v46 = (void *)(v40 * (v42 - v38) + v119 + (unsigned int)((v43 - v37) * v41));
              v47 = *((_WORD *)v4 + 1);
              if ( v47 != 1 )
                break;
              v58 = *(unsigned __int16 *)v4;
              if ( (_DWORD)v45 )
              {
                v66 = (char *)v4 + 24;
                v67 = 632 * v44;
                if ( !*((_DWORD *)this + 158 * v44 + 32) )
                  *(_QWORD *)((char *)this + v67 + 96) = v66;
                v68 = (char *)this + v67;
                *(_QWORD *)((char *)this + v67 + 72) = 0;
                v69 = (char *)this + v67 + 168;
                *(_DWORD *)((char *)this + v67 + 56) = v43 - v102;
                *(_DWORD *)((char *)this + v67 + 60) = v42 - v103;
                while ( 1 )
                {
                  v70 = (void *)*((_QWORD *)v69 + 1);
                  v71 = v68 + 32;
                  v72 = *((_QWORD *)v69 + 2);
                  v73 = *(void (__fastcall **)(__int64, void *, _QWORD, char *))v69;
                  if ( v70 == (void *)1 )
                    v70 = v66;
                  if ( !v70 )
                    v70 = v46;
                  if ( !v72 )
                    break;
                  v73(v72, v70, (unsigned int)v45, v71);
                  v69 += 24;
                }
                v73((__int64)v46, v70, (unsigned int)v45, v71);
                v4 = v98;
                goto LABEL_62;
              }
LABEL_63:
              v59 = *((unsigned __int16 *)v4 + 1);
              v60 = *((int *)v4 + 3);
              if ( v59 == 3 )
              {
                v5 = this;
                v61 = v60 + 20;
              }
              else
              {
                v63 = 632 * v58;
                v5 = this;
                v62 = 0;
                v64 = ((*(int *)((char *)this + v63 + 648) >> 8) & 0xF8u) >> 3;
                if ( *((_WORD *)v4 + 1) )
                {
                  v65 = v59 - 1;
                  if ( v65 )
                  {
                    if ( v65 == 1 )
                      v62 = (char *)(v60
                                   + (((unsigned __int64)v4 + (int)(*((_DWORD *)v4 + 4) * v64) + 27)
                                    & 0xFFFFFFFFFFFFFFFCuLL));
                    goto LABEL_66;
                  }
                }
                v61 = (int)(v64 * v60) + 24LL;
              }
              v62 = (char *)v4 + v61;
LABEL_66:
              v40 = v104;
              v41 = v105;
              v4 = (struct EpScanRecord *)((unsigned __int64)(v62 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
              v98 = v4;
              if ( v4 >= v120 )
              {
                StretchBlt(a2, xDest, yDest, wDest, v106, hdcDest, 0, 0, v100, hDest, 0xCC0020u);
                return;
              }
            }
            if ( v47 == 3 )
            {
              v48 = 0;
            }
            else
            {
              v48 = (char *)v4 + 24;
              if ( v47 == 2 )
              {
                v77 = ((unsigned __int64)v4
                     + (int)(*((_DWORD *)v4 + 4) * (((*((int *)v5 + 162) >> 8) & 0xF8u) >> 3))
                     + 27)
                    & 0xFFFFFFFFFFFFFFFCuLL;
                goto LABEL_87;
              }
            }
            v99 = 0;
            if ( v47 != 3 )
            {
LABEL_49:
              if ( (*(_DWORD *)(*((_QWORD *)v5 + 165) + 12LL) & 0xFF00u) < 0x800 )
              {
                memset_0(v46, 0, v45);
                v42 = v101;
              }
              if ( (_DWORD)v45 )
              {
                v49 = v42 - *((_DWORD *)v5 + 5);
                v50 = v43 - *((_DWORD *)v5 + 4);
                v51 = 632LL * *(unsigned __int16 *)v4;
                if ( !*(_DWORD *)((char *)v5 + v51 + 128) )
                  *(_QWORD *)((char *)v5 + v51 + 96) = v48;
                v52 = (char *)v5 + v51;
                *(_DWORD *)((char *)v5 + v51 + 56) = v50;
                *(_DWORD *)((char *)v5 + v51 + 60) = v49;
                v53 = (char *)v5 + v51 + 168;
                *((_QWORD *)v52 + 9) = v99;
                while ( 1 )
                {
                  v54 = v52 + 32;
                  v55 = *((_QWORD *)v53 + 2);
                  v56 = v48;
                  if ( *((_QWORD *)v53 + 1) != 1 )
                    v56 = (void *)*((_QWORD *)v53 + 1);
                  v57 = *(void (__fastcall **)(__int64, void *, _QWORD, char *))v53;
                  if ( !v56 )
                    v56 = v46;
                  if ( !v55 )
                    break;
                  v57(v55, v56, (unsigned int)v45, v54);
                  v53 += 24;
                }
                v57((__int64)v46, v56, (unsigned int)v45, v54);
              }
              v58 = v96;
LABEL_62:
              v38 = v94;
              v37 = v93;
              goto LABEL_63;
            }
            v77 = (unsigned __int64)v4 + 20;
LABEL_87:
            v99 = v77;
            goto LABEL_49;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18003f9f0  push    rbp
0x18003f9f2  push    rbx
0x18003f9f3  push    rsi
0x18003f9f4  push    rdi
0x18003f9f5  lea     rbp, [rsp-488h]
0x18003f9fd  sub     rsp, 588h
0x18003fa04  mov     rax, cs:__security_cookie
0x18003fa0b  xor     rax, rsp
0x18003fa0e  mov     [rbp+4A0h+var_50], rax
0x18003fa15  mov     rax, [rcx+520h]
0x18003fa1c  mov     rdi, r8
0x18003fa1f  mov     [rbp+4A0h+var_510], r8
0x18003fa23  mov     rbx, rcx
0x18003fa26  mov     r8, rdx
0x18003fa29  mov     [rbp+4A0h+hdcSrc], rdx
0x18003fa2d  mov     [rbp+4A0h+var_4E0], rcx
0x18003fa31  lea     rdx, [rcx+57Ch]; lppt
0x18003fa38  mov     esi, [rax+308h]
0x18003fa3e  mov     rcx, r8; hdc
0x18003fa41  mov     [rbp+4A0h+var_518], esi
0x18003fa44  mov     [rbp+4A0h+var_490], r9
0x18003fa48  call    cs:__imp_GetDCOrgEx
0x18003fa4e  mov     r9d, [rbx+558h]
0x18003fa55  mov     r11d, [rbx+55Ch]
0x18003fa5c  mov     r10d, [rbx+560h]
0x18003fa63  mov     r8d, [rbx+564h]
0x18003fa6a  cmp     esi, 1
0x18003fa6d  jg      loc_1800402EA
0x18003fa73  cmp     cs:?g_fClientSession@Globals@@3HA, 0; int Globals::g_fClientSession
0x18003fa7a  mov     rsi, [rbx+518h]
0x18003fa81  mov     [rsp+5A0h+var_20], r13
0x18003fa89  mov     [rsp+5A0h+var_28], r14
0x18003fa91  mov     [rsp+5A0h+var_30], r15
0x18003fa99  mov     [rbp+4A0h+var_520], r9d
0x18003fa9d  mov     [rbp+4A0h+var_51C], r10d
0x18003faa1  jnz     loc_18004037F
0x18003faa7  xor     r14d, r14d
0x18003faaa  mov     rax, [rbx+520h]
0x18003fab1  sub     r8d, r10d
0x18003fab4  mov     rcx, [rsi+10h]; ho
0x18003fab8  sub     r11d, r9d
0x18003fabb  mov     [rbp+4A0h+var_508], r11d
0x18003fabf  mov     r13, [rax+298h]
0x18003fac6  lea     eax, [r8+1]
0x18003faca  mov     [rbp+4A0h+hDest], eax
0x18003facd  test    rcx, rcx
0x18003fad0  jz      short loc_18003FAD8
0x18003fad2  call    cs:__imp_DeleteObject
0x18003fad8  test    r13, r13
0x18003fadb  jnz     short loc_18003FAE4
0x18003fadd  mov     r13, [rsi+628h]
0x18003fae4  mov     r15, [rsi+5E0h]
0x18003faeb  lea     rcx, [rbp+4A0h+pbmi]; void *
0x18003faef  xor     edx, edx; Val
0x18003faf1  mov     r8d, 428h; Size
0x18003faf7  call    memset_0
0x18003fafc  test    r14d, r14d
0x18003faff  jnz     short loc_18003FB0C
0x18003fb01  mov     rcx, r15; hdc
0x18003fb04  call    ?ExtractPixelFormatFromHDC@@YAHPEAUHDC__@@@Z; ExtractPixelFormatFromHDC(HDC__ *)
0x18003fb09  mov     r14d, eax
0x18003fb0c  mov     [rsi+50h], r14d
0x18003fb10  bt      r14d, 10h
0x18003fb15  jb      loc_18004038F
0x18003fb1b  mov     edx, 2; index
0x18003fb20  mov     [rsp+5A0h+arg_18], r12
0x18003fb28  mov     rcx, r15; hdc
0x18003fb2b  call    cs:__imp_GetDeviceCaps
0x18003fb31  cmp     eax, 2
0x18003fb34  jz      loc_180040343
0x18003fb3a  mov     ecx, [rsi+50h]
0x18003fb3d  test    ecx, ecx
0x18003fb3f  jz      loc_180040350
0x18003fb45  xor     r11d, r11d
0x18003fb48  mov     [rbp+4A0h+pbmi.bmiHeader.biSize], 28h ; '('
0x18003fb4f  mov     edx, 0FFh
0x18003fb54  mov     [rbp+4A0h+pbmi.bmiHeader.biHeight], r11d
0x18003fb58  mov     eax, ecx
0x18003fb5a  mov     r12d, 1
0x18003fb60  sar     eax, 8
0x18003fb63  and     ax, dx
0x18003fb66  mov     [rbp+4A0h+pbmi.bmiHeader.biPlanes], r12w
0x18003fb6b  mov     [rbp+4A0h+pbmi.bmiHeader.biBitCount], ax
0x18003fb6f  mov     edx, r11d
0x18003fb72  mov     [rbp+4A0h+pbmi.bmiHeader.biCompression], edx
0x18003fb75  movzx   r8d, ax
0x18003fb79  bt      ecx, 10h
0x18003fb7d  jb      loc_18004039B
0x18003fb83  mov     eax, ecx
0x18003fb85  and     eax, 0FF00h
0x18003fb8a  sub     eax, 1000h
0x18003fb8f  test    eax, 0FFFFEFFFh
0x18003fb94  jnz     short loc_18003FB9E
0x18003fb96  mov     edx, 3
0x18003fb9b  mov     [rbp+4A0h+pbmi.bmiHeader.biCompression], edx
0x18003fb9e  movzx   ecx, cl
0x18003fba1  lea     r9, __ImageBase
0x18003fba8  mov     eax, ds:rva dword_1801809C0[r9+rcx*4]
0x18003fbb0  mov     dword ptr [rbp+4A0h+pbmi.bmiColors.rgbBlue], eax
0x18003fbb3  mov     eax, ds:rva dword_180180970[r9+rcx*4]
0x18003fbbb  mov     [rbp+4A0h+var_454], eax
0x18003fbbe  mov     eax, ds:rva dword_180180920[r9+rcx*4]
0x18003fbc6  mov     [rbp+4A0h+var_450], eax
0x18003fbc9  movsxd  r13, [rbp+4A0h+var_508]
0x18003fbcd  mov     ecx, [rbp+4A0h+hDest]
0x18003fbd0  mov     [rbp+4A0h+pbmi.bmiHeader.biWidth], r13d
0x18003fbd4  test    ecx, ecx
0x18003fbd6  js      loc_1800402B5
0x18003fbdc  mov     eax, ecx
0x18003fbde  lea     r9, [rsi+20h]; ppvBits
0x18003fbe2  neg     eax
0x18003fbe4  mov     [rbp+4A0h+pbmi.bmiHeader.biHeight], eax
0x18003fbe7  test    edx, edx
0x18003fbe9  jz      loc_1800402AC
0x18003fbef  cmp     r8w, 10h
0x18003fbf4  jz      loc_1800403EA
0x18003fbfa  cmp     r8w, 20h ; ' '
0x18003fbff  jnz     loc_1800402AC
0x18003fc05  mov     eax, r13d
0x18003fc08  imul    eax, ecx
0x18003fc0b  shl     eax, 2
0x18003fc0e  mov     [rbp+4A0h+pbmi.bmiHeader.biSizeImage], eax
0x18003fc11  mov     [rsp+5A0h+offset], r11d; offset
0x18003fc16  lea     rdx, [rbp+4A0h+pbmi]; pbmi
0x18003fc1a  xor     r8d, r8d; usage
0x18003fc1d  mov     [rsp+5A0h+hSection], r11; hSection
0x18003fc22  mov     rcx, r15; hdc
0x18003fc25  mov     qword ptr [rbp+4A0h+pbmi.bmiHeader.biClrUsed], 0
0x18003fc2d  call    cs:__imp_CreateDIBSection
0x18003fc33  mov     [rsi+10h], rax
0x18003fc37  test    rax, rax
0x18003fc3a  jz      loc_1800403FA
0x18003fc40  mov     rcx, [rsi+18h]; hdc
0x18003fc44  mov     rdx, rax; h
0x18003fc47  mov     [rsi+0Ch], r13d
0x18003fc4b  call    cs:__imp_SelectObject
0x18003fc51  xor     r11d, r11d
0x18003fc54  mov     r8, [rsi+28h]; lpMem
0x18003fc58  test    r8, r8
0x18003fc5b  jz      short loc_18003FC73
0x18003fc5d  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18003fc64  xor     edx, edx; dwFlags
0x18003fc66  call    cs:__imp_HeapFree
0x18003fc6c  xor     r11d, r11d
0x18003fc6f  mov     [rsi+28h], r11
0x18003fc73  test    r13d, r13d
0x18003fc76  js      short loc_18003FC87
0x18003fc78  mov     rax, 3333333333333333h
0x18003fc82  cmp     r13, rax
0x18003fc85  jbe     short loc_18003FC90
0x18003fc87  mov     r8, r11
0x18003fc8a  mov     [rsi+28h], r11
0x18003fc8e  jmp     short loc_18003FCD8
0x18003fc90  lea     r8, ds:0[r13*4]
0x18003fc98  mov     rax, 1FFFFFFFFFFFFFFFh
0x18003fca2  add     r8, r13
0x18003fca5  cmp     r8, rax
0x18003fca8  ja      loc_180040402
0x18003fcae  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18003fcb5  lea     r8, ds:0[r8*8]; dwBytes
0x18003fcbd  xor     edx, edx; dwFlags
0x18003fcbf  call    cs:__imp_HeapAlloc
0x18003fcc5  mov     r8, rax
0x18003fcc8  xor     r11d, r11d
0x18003fccb  mov     [rsi+28h], r8
0x18003fccf  test    r8, r8
0x18003fcd2  jnz     loc_18004024E
0x18003fcd8  mov     [rsi+0Ch], r11d
0x18003fcdc  mov     rax, [rsi+20h]
0x18003fce0  lea     r14, [rbx+530h]
0x18003fce7  mov     [rbp+4A0h+var_498], rax
0x18003fceb  mov     rax, [rsi+18h]
0x18003fcef  mov     [rbp+4A0h+hdcDest], rax
0x18003fcf3  test    r14, r14
0x18003fcf6  jnz     loc_1800402C2
0x18003fcfc  cmp     dword ptr [rsi+0Ch], 0
0x18003fd00  jz      loc_180040107
0x18003fd06  mov     esi, [rsi+50h]
0x18003fd09  test    esi, esi
0x18003fd0b  jz      loc_180040107
0x18003fd11  mov     rcx, [rbx+520h]
0x18003fd18  mov     r8d, [rbx+58Ch]
0x18003fd1f  movaps  [rsp+5A0h+var_40], xmm6
0x18003fd27  mov     rdx, [rcx+298h]
0x18003fd2e  test    rdx, rdx
0x18003fd31  jnz     short loc_18003FD41
0x18003fd33  mov     rax, [rbx+518h]
0x18003fd3a  mov     rdx, [rax+628h]
0x18003fd41  movdqa  xmm6, cs:__xmm@00000000000000010000000000000000
0x18003fd49  lea     rax, [rbx+0A8h]
0x18003fd50  mov     r9d, [rbx+288h]
0x18003fd57  mov     [rsp+5A0h+var_530], r12d
0x18003fd5c  mov     [rbp+4A0h+var_4C8], rax
0x18003fd60  lea     rax, [rbp+4A0h+var_4C8]
0x18003fd64  mov     [rsp+5A0h+var_538], rax
0x18003fd69  mov     eax, [rcx+2Ch]
0x18003fd6c  mov     [rsp+5A0h+var_540], r8d
0x18003fd71  mov     r8d, esi
0x18003fd74  mov     [rsp+5A0h+var_548], r12d
0x18003fd79  mov     [rsp+5A0h+rop], r12d
0x18003fd7e  mov     qword ptr [rsp+5A0h+hSrc], r14
0x18003fd83  mov     qword ptr [rsp+5A0h+wSrc], rdx
0x18003fd88  mov     edx, [rbx+28Ch]
0x18003fd8e  mov     [rsp+5A0h+ySrc], eax
0x18003fd92  mov     eax, [rcx+20h]
0x18003fd95  mov     [rsp+5A0h+xSrc], eax
0x18003fd99  mov     eax, [rcx+1Ch]
0x18003fd9c  mov     [rsp+5A0h+offset], eax
0x18003fda0  mov     rax, [rcx+2A0h]
0x18003fda7  lea     rcx, [rbx+18h]
0x18003fdab  mov     [rsp+5A0h+hSection], rax
0x18003fdb0  mov     [rbp+4A0h+var_4C0], r14
0x18003fdb4  movdqu  [rbp+4A0h+var_4B0], xmm6
0x18003fdb9  mov     [rbp+4A0h+var_4B8], r11d
0x18003fdbd  mov     [rbp+4A0h+var_4A0], r12d
0x18003fdc1  mov     [rbp+4A0h+var_49C], 2
0x18003fdc8  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x18003fdcd  mov     rax, [rbp+4A0h+var_4C8]
0x18003fdd1  xor     r15d, r15d
0x18003fdd4  mov     [rax-8], r15
0x18003fdd8  mov     rdx, [rbx+520h]
0x18003fddf  mov     r8d, [rbx+58Ch]
0x18003fde6  mov     rcx, [rdx+298h]
0x18003fded  test    rcx, rcx
0x18003fdf0  jnz     short loc_18003FE00
0x18003fdf2  mov     rax, [rbx+518h]
0x18003fdf9  mov     rcx, [rax+628h]
0x18003fe00  mov     r9d, [rbx+500h]
0x18003fe07  lea     rax, [rbx+320h]
0x18003fe0e  mov     [rsp+5A0h+var_530], r12d
0x18003fe13  mov     [rbp+4A0h+var_4C8], rax
0x18003fe17  lea     rax, [rbp+4A0h+var_4C8]
0x18003fe1b  mov     [rsp+5A0h+var_538], rax
0x18003fe20  mov     eax, [rdx+2Ch]
0x18003fe23  mov     [rsp+5A0h+var_540], r8d
0x18003fe28  mov     r8d, esi
0x18003fe2b  mov     [rsp+5A0h+var_548], r12d
0x18003fe30  mov     [rsp+5A0h+rop], r12d
0x18003fe35  mov     qword ptr [rsp+5A0h+hSrc], r14
0x18003fe3a  mov     qword ptr [rsp+5A0h+wSrc], rcx
0x18003fe3f  lea     rcx, [rbx+290h]
0x18003fe46  mov     [rsp+5A0h+ySrc], eax
0x18003fe4a  mov     eax, [rdx+20h]
0x18003fe4d  mov     [rsp+5A0h+xSrc], eax
0x18003fe51  mov     eax, [rdx+1Ch]
0x18003fe54  mov     [rsp+5A0h+offset], eax
0x18003fe58  mov     rax, [rdx+2A0h]
0x18003fe5f  mov     edx, [rbx+504h]
0x18003fe65  mov     [rsp+5A0h+hSection], rax
0x18003fe6a  mov     [rbp+4A0h+var_4C0], r14
0x18003fe6e  movdqu  [rbp+4A0h+var_4B0], xmm6
0x18003fe73  mov     [rbp+4A0h+var_4B8], r15d
0x18003fe77  mov     [rbp+4A0h+var_4A0], r12d
0x18003fe7b  mov     [rbp+4A0h+var_49C], 2
0x18003fe82  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x18003fe87  mov     ecx, [rbp+4A0h+var_518]
0x18003fe8a  mov     r8d, [rbp+4A0h+hDest]
0x18003fe8e  mov     rax, [rbp+4A0h+var_4C8]
0x18003fe92  mov     r14d, [rbp+4A0h+var_520]
0x18003fe96  mov     [rsp+5A0h+rop], 0CC0020h; rop
0x18003fe9e  mov     [rax-8], r15
0x18003fea2  mov     eax, [rbx+10h]
0x18003fea5  mov     r15d, [rbp+4A0h+var_51C]
0x18003fea9  mov     [rbp+4A0h+var_500], eax
0x18003feac  mov     eax, [rbx+14h]
0x18003feaf  mov     [rbp+4A0h+var_4FC], eax
0x18003feb2  mov     eax, r8d
0x18003feb5  cdq
0x18003feb6  idiv    ecx
0x18003feb8  mov     r9d, eax
0x18003febb  mov     [rbp+4A0h+var_4F0], eax
0x18003febe  mov     eax, r13d
0x18003fec1  mov     [rsp+5A0h+hSrc], r9d; hSrc
0x18003fec6  cdq
0x18003fec7  mov     r9d, r13d; wDest
0x18003feca  idiv    ecx
0x18003fecc  mov     r10d, eax
0x18003fecf  mov     [rbp+4A0h+wDest], eax
0x18003fed2  mov     eax, r15d
0x18003fed5  mov     [rsp+5A0h+wSrc], r10d; wSrc
0x18003feda  cdq
0x18003fedb  idiv    ecx
0x18003fedd  mov     r11d, eax
0x18003fee0  mov     [rbp+4A0h+yDest], eax
0x18003fee3  mov     [rsp+5A0h+ySrc], r11d; ySrc
0x18003fee8  mov     eax, r14d
0x18003feeb  cdq
0x18003feec  idiv    ecx
0x18003feee  mov     rcx, [rbp+4A0h+hdcDest]; hdcDest
0x18003fef2  xor     edx, edx; xDest
0x18003fef4  mov     [rsp+5A0h+xSrc], eax; xSrc
0x18003fef8  mov     [rbp+4A0h+xDest], eax
0x18003fefb  mov     rax, [rbp+4A0h+hdcSrc]
0x18003feff  mov     qword ptr [rsp+5A0h+offset], rax; hdcSrc
0x18003ff04  mov     dword ptr [rsp+5A0h+hSection], r8d; hDest
0x18003ff09  xor     r8d, r8d; yDest
0x18003ff0c  call    cs:__imp_StretchBlt
0x18003ff12  movaps  xmm6, [rsp+5A0h+var_40]
0x18003ff1a  sar     esi, 8
0x18003ff1d  movzx   r9d, sil
  ... truncated ...
```
