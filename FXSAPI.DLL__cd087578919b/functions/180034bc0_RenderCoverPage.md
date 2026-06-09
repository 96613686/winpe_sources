# RenderCoverPage

- ea: `0x180034bc0`
- end: `0x180035c5c`
- name: `RenderCoverPage`
- size: `4252`
- prototype: `__int64 __fastcall(HDC hdc, RECT *lprect, __int64, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180034a6c`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180014314`
- `0x180021530`
- `0x18002bb58`
- `0x18002c7bc`
- `0x180031e24`
- `0x180034994`
- `0x180034bc0`
- `0x180035c64`
- `0x180035d0c`
- `0x18003d4a6`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `msvcrt!malloc` at `0x180034e31`
- `msvcrt!malloc` at `0x1800353ce`
- `msvcrt!malloc` at `0x180034e31`
- `msvcrt!malloc` at `0x1800353ce`
- `msvcrt!free` at `0x180035141`
- `msvcrt!free` at `0x180035156`
- `msvcrt!free` at `0x180035141`
- `msvcrt!free` at `0x180035156`
- `msvcrt!realloc` at `0x1800354a2`
- `msvcrt!realloc` at `0x1800354a2`
- `KERNEL32!ReadFile` at `0x180034db4`
- `KERNEL32!ReadFile` at `0x180034e9b`
- `KERNEL32!ReadFile` at `0x18003544c`
- `KERNEL32!ReadFile` at `0x1800354d7`
- `KERNEL32!ReadFile` at `0x1800357a8`
- `KERNEL32!ReadFile` at `0x180034db4`
- `KERNEL32!ReadFile` at `0x180034e9b`
- `KERNEL32!ReadFile` at `0x18003544c`
- `KERNEL32!ReadFile` at `0x1800354d7`
- `KERNEL32!ReadFile` at `0x1800357a8`
- `KERNEL32!CreateFileW` at `0x180034d27`
- `KERNEL32!CreateFileW` at `0x180034d27`
- `KERNEL32!MulDiv` at `0x18003563a`
- `KERNEL32!MulDiv` at `0x18003563a`
- `KERNEL32!CloseHandle` at `0x180035b7d`
- `KERNEL32!CloseHandle` at `0x180035b7d`
- `KERNEL32!GetLastError` at `0x180034d7f`
- `KERNEL32!GetLastError` at `0x180034dc4`
- `KERNEL32!GetLastError` at `0x180034eee`
- `KERNEL32!GetLastError` at `0x180034fa6`
- `KERNEL32!GetLastError` at `0x180035054`
- `KERNEL32!GetLastError` at `0x1800350bd`
- `KERNEL32!GetLastError` at `0x180035180`
- `KERNEL32!GetLastError` at `0x1800351f1`
- `KERNEL32!GetLastError` at `0x18003524a`
- `KERNEL32!GetLastError` at `0x1800352ae`
- `KERNEL32!GetLastError` at `0x180035315`
- `KERNEL32!GetLastError` at `0x180035386`
- `KERNEL32!GetLastError` at `0x1800357c1`
- `KERNEL32!GetLastError` at `0x1800358b9`
- `KERNEL32!GetLastError` at `0x18003590e`
- `KERNEL32!GetLastError` at `0x180035951`
- `KERNEL32!GetLastError` at `0x1800359c9`
- `KERNEL32!GetLastError` at `0x180035a0c`
- `KERNEL32!GetLastError` at `0x180035a9b`
- `KERNEL32!GetLastError` at `0x180035af5`
- `KERNEL32!GetLastError` at `0x180034d7f`
- `KERNEL32!GetLastError` at `0x180034dc4`
- `KERNEL32!GetLastError` at `0x180034eee`
- `KERNEL32!GetLastError` at `0x180034fa6`
- `KERNEL32!GetLastError` at `0x180035054`
- `KERNEL32!GetLastError` at `0x1800350bd`
- `KERNEL32!GetLastError` at `0x180035180`
- `KERNEL32!GetLastError` at `0x1800351f1`
- `KERNEL32!GetLastError` at `0x18003524a`
- `KERNEL32!GetLastError` at `0x1800352ae`
- `KERNEL32!GetLastError` at `0x180035315`
- `KERNEL32!GetLastError` at `0x180035386`
- `KERNEL32!GetLastError` at `0x1800357c1`
- `KERNEL32!GetLastError` at `0x1800358b9`
- `KERNEL32!GetLastError` at `0x18003590e`
- `KERNEL32!GetLastError` at `0x180035951`
- `KERNEL32!GetLastError` at `0x1800359c9`
- `KERNEL32!GetLastError` at `0x180035a0c`
- `KERNEL32!GetLastError` at `0x180035a9b`
- `KERNEL32!GetLastError` at `0x180035af5`
- `GDI32!SaveDC` at `0x180034f92`
- `GDI32!SaveDC` at `0x180034f92`
- `GDI32!SelectObject` at `0x1800356cb`
- `GDI32!SelectObject` at `0x180035741`
- `GDI32!SelectObject` at `0x1800356cb`
- `GDI32!SelectObject` at `0x180035741`
- `GDI32!PlayEnhMetaFile` at `0x180035170`
- `GDI32!PlayEnhMetaFile` at `0x180035170`
- `GDI32!SetEnhMetaFileBits` at `0x180035039`
- `GDI32!SetEnhMetaFileBits` at `0x180035039`
- `GDI32!SetWindowOrgEx` at `0x180035376`
- `GDI32!SetWindowOrgEx` at `0x180035376`
- `GDI32!CreateRectRgnIndirect` at `0x180034ed8`
- `GDI32!CreateRectRgnIndirect` at `0x180034ed8`
- `GDI32!GetEnhMetaFileHeader` at `0x1800350a9`
- `GDI32!GetEnhMetaFileHeader` at `0x1800350a9`
- `GDI32!SetWindowExtEx` at `0x18003529e`
- `GDI32!SetWindowExtEx` at `0x18003529e`
- `GDI32!DeleteEnhMetaFile` at `0x180035107`
- `GDI32!DeleteEnhMetaFile` at `0x180035107`
- `GDI32!SetViewportExtEx` at `0x180035305`
- `GDI32!SetViewportExtEx` at `0x180035305`
- `GDI32!GetDeviceCaps` at `0x180035622`
- `GDI32!GetDeviceCaps` at `0x180035622`
- `GDI32!SetTextColor` at `0x18003566f`
- `GDI32!SetTextColor` at `0x180035753`
- `GDI32!SetTextColor` at `0x18003566f`
- `GDI32!SetTextColor` at `0x180035753`
- `GDI32!SetBkMode` at `0x1800351dc`
- `GDI32!SetBkMode` at `0x1800351dc`
- `GDI32!SelectClipRgn` at `0x180034f49`
- `GDI32!SelectClipRgn` at `0x180034f49`
- `GDI32!RestoreDC` at `0x1800351c8`
- `GDI32!RestoreDC` at `0x180035b96`
- `GDI32!RestoreDC` at `0x1800351c8`
- `GDI32!RestoreDC` at `0x180035b96`
- `GDI32!LPtoDP` at `0x1800355f6`
- `GDI32!LPtoDP` at `0x1800355f6`
- `GDI32!DeleteObject` at `0x18003512d`
- `GDI32!DeleteObject` at `0x180035762`
- `GDI32!DeleteObject` at `0x180035c2a`
- `GDI32!DeleteObject` at `0x18003512d`
- `GDI32!DeleteObject` at `0x180035762`
- `GDI32!DeleteObject` at `0x180035c2a`
- `GDI32!SetMapMode` at `0x18003523a`
- `GDI32!SetMapMode` at `0x18003523a`
- `GDI32!CreateFontIndirectW` at `0x1800356ad`
- `GDI32!CreateFontIndirectW` at `0x1800356ad`
- `USER32!DrawTextW` at `0x180035727`
- `USER32!DrawTextW` at `0x180035727`

## pseudocode

```c
__int64 __fastcall RenderCoverPage(HDC hdc, RECT *lprect, __int64 a3, const WCHAR *a4, __int64 a5)
{
  __int64 v5; // r12
  HDC v8; // r14
  DWORD LastError; // ebx
  __int64 v11; // r13
  HANDLE FileW; // rax
  void *v13; // r15
  HGDIOBJ v14; // rdi
  int v15; // esi
  HFONT v16; // rdi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rax
  const BYTE *v20; // rbx
  __int64 v21; // r9
  HRGN RectRgnIndirect; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  HENHMETAFILE v26; // rbx
  void *v27; // r12
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  HENHMETAFILE v30; // rcx
  void *v31; // r12
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  int v35; // esi
  DWORD v36; // r8d
  unsigned __int64 v37; // rdi
  void *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  LPCWSTR v41; // rdi
  LONG v42; // r9d
  LONG v43; // eax
  LONG v44; // r8d
  LONG v45; // eax
  const WCHAR *v46; // rsi
  signed int v47; // eax
  int v48; // ecx
  int DeviceCaps; // eax
  COLORREF v50; // r13d
  HFONT v51; // rax
  HGDIOBJ v52; // r12
  int v53; // r14d
  int v54; // eax
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // r9
  int v58; // edx
  int v59; // r8d
  _QWORD *v60; // rcx
  __int64 v61; // rdx
  __int128 v62; // xmm1
  __int16 v63; // ax
  __int16 v64; // ax
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  HENHMETAFILE hmf; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  int v72; // [rsp+4Ch] [rbp-B4h]
  int v73; // [rsp+50h] [rbp-B0h]
  int nSavedDC; // [rsp+54h] [rbp-ACh]
  void *v75; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpchText; // [rsp+60h] [rbp-A0h]
  HANDLE hFile; // [rsp+68h] [rbp-98h]
  HGDIOBJ ho; // [rsp+70h] [rbp-90h]
  __int64 v79; // [rsp+78h] [rbp-88h]
  struct tagSIZE sz; // [rsp+80h] [rbp-80h] BYREF
  struct tagSIZE v81; // [rsp+88h] [rbp-78h] BYREF
  tagPOINT pt; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h]
  HDC hdca; // [rsp+A0h] [rbp-60h]
  __int64 v85; // [rsp+A8h] [rbp-58h]
  void *Block; // [rsp+B0h] [rbp-50h]
  __int128 Buffer; // [rsp+B8h] [rbp-48h] BYREF
  size_t Size[2]; // [rsp+C8h] [rbp-38h]
  int v89; // [rsp+D8h] [rbp-28h]
  LONG v90; // [rsp+E0h] [rbp-20h] BYREF
  LONG v91; // [rsp+E4h] [rbp-1Ch]
  LONG v92; // [rsp+E8h] [rbp-18h]
  LONG v93; // [rsp+ECh] [rbp-14h]
  COLORREF color; // [rsp+F0h] [rbp-10h]
  int v95; // [rsp+F4h] [rbp-Ch]
  _BYTE v96[92]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v97; // [rsp+154h] [rbp+54h]
  DWORD nNumberOfBytesToRead; // [rsp+158h] [rbp+58h]
  struct tagPOINT v99[2]; // [rsp+160h] [rbp+60h] BYREF
  tagRECT rc; // [rsp+170h] [rbp+70h] BYREF
  int nNumber[4]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v102; // [rsp+190h] [rbp+90h]
  __int128 v103; // [rsp+1A0h] [rbp+A0h]
  __int128 v104; // [rsp+1B0h] [rbp+B0h]
  _OWORD v105[2]; // [rsp+1C0h] [rbp+C0h]
  LOGFONTW lf; // [rsp+1E0h] [rbp+E0h] BYREF
  tagENHMETAHEADER EnhMetaHeader; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v108[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int16 v109; // [rsp+2B2h] [rbp+1B2h]
  __int16 v110; // [rsp+2B4h] [rbp+1B4h]

  v5 = a5;
  v83 = a3;
  hdca = hdc;
  v8 = hdc;
  v79 = a5;
  memset_0(&EnhMetaHeader, 0, sizeof(EnhMetaHeader));
  NumberOfBytesRead = 0;
  rc = 0;
  *(_OWORD *)&v99[0].x = 0;
  memset_0(&v90, 0, 0x7Cu);
  v89 = 0;
  Buffer = 0;
  *(_OWORD *)Size = 0;
  memset_0(nNumber, 0, 0x5Cu);
  memset_0(&lf, 0, sizeof(lf));
  ho = 0;
  sz = 0;
  pt = 0;
  v81 = 0;
  LastError = 11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
  }
  v99[0] = 0;
  v99[1] = 0;
  v72 = 0;
  Buffer = 0;
  v11 = (a3 + 8) & -(__int64)(a3 != 0);
  v89 = 0;
  v85 = v11;
  *(_OWORD *)Size = 0;
  memset_0(&v90, 0, 0x7Cu);
  FileW = CreateFileW(a4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  hFile = FileW;
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids,
        (_DWORD)a4,
        0);
    }
    v14 = ho;
    LastError = GetLastError();
    v15 = (int)ho;
    goto LABEL_227;
  }
  v16 = 0;
  nSavedDC = 0;
  if ( !ReadFile(FileW, &Buffer, 0x24u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 13;
LABEL_223:
      v21 = LastError;
      goto LABEL_224;
    }
    goto LABEL_225;
  }
  if ( NumberOfBytesRead == 36 && !memcmp_0(UNICODE_Signature, &Buffer, 0x14u) )
  {
    v19 = malloc(HIDWORD(Size[0]));
    Block = v19;
    v20 = (const BYTE *)v19;
    if ( !v19 )
    {
      LastError = 8;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 15;
        v21 = 8;
LABEL_224:
        WPP_SF_d(v17[2], v18, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v21);
        goto LABEL_225;
      }
      goto LABEL_225;
    }
    if ( !ReadFile(v13, v19, HIDWORD(Size[0]), &NumberOfBytesRead, 0) || HIDWORD(Size[0]) != NumberOfBytesRead )
    {
      LastError = GetLastError();
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_68;
      }
      v24 = 16;
LABEL_31:
      v25 = LastError;
LABEL_32:
      WPP_SF_d(v23[2], v24, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v25);
LABEL_68:
      free(Block);
      goto LABEL_225;
    }
    hmf = 0;
    lpchText = 0;
    if ( v8 )
    {
      RectRgnIndirect = CreateRectRgnIndirect(lprect);
      ho = RectRgnIndirect;
      if ( !RectRgnIndirect )
      {
        LastError = GetLastError();
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v24 = 17;
        goto LABEL_31;
      }
      if ( !SelectClipRgn(v8, RectRgnIndirect) )
      {
        LastError = 31;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v24 = 18;
        v25 = 0;
        goto LABEL_32;
      }
      nSavedDC = SaveDC(v8);
      if ( !nSavedDC )
      {
        LastError = GetLastError();
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v24 = 19;
        goto LABEL_31;
      }
      if ( !HIDWORD(Size[0]) )
      {
        LastError = 18;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
        }
        goto LABEL_68;
      }
      v26 = SetEnhMetaFileBits(HIDWORD(Size[0]), v20);
      hmf = v26;
      if ( !v26 )
      {
        LastError = GetLastError();
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v24 = 21;
        goto LABEL_31;
      }
      v27 = 0;
      if ( !GetEnhMetaFileHeader(v26, 0x6Cu, &EnhMetaHeader) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 22;
LABEL_58:
        WPP_SF_d(v28[2], v29, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, LastError);
LABEL_59:
        v30 = hmf;
LABEL_60:
        DeleteEnhMetaFile(v30);
LABEL_61:
        if ( lpchText )
          pMemFree((LPVOID)lpchText);
        if ( v16 )
          DeleteObject(v16);
        if ( v27 )
          free(v27);
        v5 = v79;
        goto LABEL_68;
      }
      if ( !PlayEnhMetaFile(v8, v26, lprect) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 23;
        goto LABEL_58;
      }
      RestoreDC(v8, 0);
      if ( SetBkMode(v8, 1) == -1 )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 24;
        goto LABEL_58;
      }
      if ( !SetMapMode(v8, 8) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 25;
        goto LABEL_58;
      }
      if ( !SetWindowExtEx(v8, SHIDWORD(Size[1]), -v89, &sz) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 26;
        goto LABEL_58;
      }
      if ( !SetViewportExtEx(v8, lprect->right - lprect->left, lprect->bottom - lprect->top, &v81) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 27;
        goto LABEL_58;
      }
      if ( !SetWindowOrgEx(v8, SHIDWORD(Size[1]) / -2, v89 / 2, &pt) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 28;
        goto LABEL_58;
      }
    }
    v75 = malloc(0x40u);
    v31 = v75;
    if ( !v75 )
    {
      LastError = 8;
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_165;
      }
      v33 = 29;
      v34 = 8;
      goto LABEL_164;
    }
    LastError = 0;
    v35 = 0;
    v73 = 0;
    if ( SLODWORD(Size[1]) > 0 )
    {
      while ( 1 )
      {
        if ( !ReadFile(hFile, &v90, 0x7Cu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 124 )
        {
          LastError = GetLastError();
          v60 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_165;
          }
          v61 = 30;
LABEL_214:
          WPP_SF_dd(v60[2], v61, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
          goto LABEL_165;
        }
        v36 = nNumberOfBytesToRead;
        if ( nNumberOfBytesToRead + 1 < nNumberOfBytesToRead )
          goto LABEL_206;
        v37 = 2LL * (nNumberOfBytesToRead + 1);
        if ( v37 > 0xFFFFFFFF || ((nNumberOfBytesToRead + 1) & 0x40000000) != 0 )
        {
          v16 = 0;
LABEL_206:
          LastError = 534;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
          }
          goto LABEL_165;
        }
        if ( (int)v37 > 64 )
        {
          v38 = realloc(v31, (int)v37);
          if ( !v38 )
          {
            LastError = 8;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_lll(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, (unsigned int)v35, v37);
            }
            goto LABEL_171;
          }
          v36 = nNumberOfBytesToRead;
          v31 = v38;
          v75 = v38;
        }
        v16 = 0;
        if ( !ReadFile(hFile, v31, v36, &NumberOfBytesRead, 0) || NumberOfBytesRead != nNumberOfBytesToRead )
        {
          LastError = GetLastError();
          v60 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_165;
          }
          v61 = 33;
          goto LABEL_214;
        }
        *((_WORD *)v31 + ((unsigned __int64)nNumberOfBytesToRead >> 1)) = 0;
        v41 = lpchText;
        if ( lpchText )
        {
          pMemFree((LPVOID)lpchText);
          v41 = 0;
          lpchText = 0;
        }
        if ( v31 )
        {
          lpchText = (LPCWSTR)StringDup((unsigned __int16 *)v31);
          v41 = lpchText;
          if ( !lpchText )
            break;
        }
        if ( v8 )
        {
          v42 = v93;
          v43 = v93;
          v44 = v92;
          if ( v91 > v93 )
            v43 = v91;
          rc.top = v43;
          v45 = v92;
          if ( v90 < v92 )
            v45 = v90;
          rc.left = v45;
          if ( v91 < v93 )
            v42 = v91;
          rc.bottom = v42;
          if ( v90 > v92 )
            v44 = v90;
          rc.right = v44;
        }
        v46 = 0;
        if ( v97 )
        {
          v47 = 0;
          v48 = 1;
          while ( v97 != *((_WORD *)InsertionTagResourceID + v47) )
          {
            ++v47;
            v48 *= 2;
            if ( (unsigned int)v47 >= 0x1D )
            {
              v46 = 0;
              goto LABEL_138;
            }
          }
          v46 = v83 ? *(const WCHAR **)(v11 + 8LL * v47) : 0LL;
          v72 |= v48;
LABEL_138:
          if ( v97 == 2063 && v8 )
          {
            *(tagRECT *)&v99[0].x = rc;
            LPtoDP(v8, v99, 2);
            LastError = CopyWLogFontToTLogFont(v96, nNumber);
            if ( LastError )
            {
              v55 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v56 = 35;
                v57 = LastError;
LABEL_176:
                WPP_SF_d(v55[2], v56, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v57);
              }
              goto LABEL_171;
            }
            DeviceCaps = GetDeviceCaps(v8, 90);
            nNumber[0] = MulDiv(nNumber[0], DeviceCaps, 100);
          }
        }
        if ( *v41 )
          v46 = v41;
        v16 = 0;
        if ( v8 && v46 )
        {
          v50 = SetTextColor(v8, color);
          if ( v50 == -1 )
          {
            LastError = GetLastError();
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 36;
LABEL_163:
            v34 = LastError;
LABEL_164:
            WPP_SF_d(v32[2], v33, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v34);
            goto LABEL_165;
          }
          LastError = CopyWLogFontToTLogFont(v96, &lf);
          if ( LastError )
          {
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 37;
            goto LABEL_163;
          }
          v51 = CreateFontIndirectW(&lf);
          v16 = v51;
          if ( !v51 )
          {
            LastError = GetLastError();
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 38;
            goto LABEL_163;
          }
          v52 = SelectObject(v8, v51);
          if ( !v52 )
          {
            LastError = GetLastError();
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 39;
            goto LABEL_163;
          }
          v53 = 0;
          if ( v97 && (unsigned int)StrHasRTLChar(0x800u, v46) )
            v53 = 0x20000;
          v54 = v53 | v95;
          v8 = hdca;
          if ( !DrawTextW(hdca, v46, -1, &rc, v54 | 0x810) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_lSl(*((_QWORD *)WPP_GLOBAL_Control + 2), v58, v59, v73, (__int64)v46, LastError);
            }
            goto LABEL_165;
          }
          SelectObject(v8, v52);
          SetTextColor(v8, v50);
          DeleteObject(v16);
          v31 = v75;
          v16 = 0;
          v11 = v85;
        }
        v35 = v73 + 1;
        v73 = v35;
        if ( v35 >= SLODWORD(Size[1]) )
          goto LABEL_156;
      }
      LastError = 8;
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v56 = 34;
        v57 = 8;
        goto LABEL_176;
      }
LABEL_171:
      v16 = 0;
      goto LABEL_165;
    }
LABEL_156:
    if ( ReadFile(hFile, v108, 6u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == 6 )
        goto LABEL_165;
      v16 = 0;
    }
    LastError = GetLastError();
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = 44;
      goto LABEL_163;
    }
LABEL_165:
    v30 = hmf;
    v27 = v75;
    if ( !hmf )
      goto LABEL_61;
    goto LABEL_60;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 14;
    goto LABEL_223;
  }
LABEL_225:
  v14 = ho;
  v15 = v72;
  CloseHandle(hFile);
  if ( nSavedDC )
    RestoreDC(v8, nSavedDC);
LABEL_227:
  if ( !LastError && v5 )
  {
    v62 = v102;
    v63 = v109;
    *(_OWORD *)(v5 + 4) = *(_OWORD *)&v99[0].x;
    *(_WORD *)(v5 + 22) = v63;
    v64 = v110;
    *(_OWORD *)(v5 + 24) = *(_OWORD *)nNumber;
    *(_DWORD *)v5 = v15;
    v65 = v103;
    *(_OWORD *)(v5 + 40) = v62;
    *(_WORD *)(v5 + 20) = v64;
    v66 = v104;
    *(_OWORD *)(v5 + 56) = v65;
    v67 = v105[0];
    *(_OWORD *)(v5 + 72) = v66;
    v68 = *(_OWORD *)((char *)v105 + 12);
    *(_OWORD *)(v5 + 88) = v67;
    *(_OWORD *)(v5 + 100) = v68;
  }
  if ( v14 )
    DeleteObject(v14);
  return LastError;
}

```

## disassembly

```asm
0x180034bc0  push    rbp
0x180034bc2  push    rbx
0x180034bc3  push    rsi
0x180034bc4  push    rdi
0x180034bc5  push    r12
0x180034bc7  push    r13
0x180034bc9  push    r14
0x180034bcb  push    r15
0x180034bcd  lea     rbp, [rsp-1C8h]
0x180034bd5  sub     rsp, 2C8h
0x180034bdc  mov     rax, cs:__security_cookie
0x180034be3  xor     rax, rsp
0x180034be6  mov     [rbp+200h+var_48], rax
0x180034bed  mov     r12, [rbp+200h+arg_20]
0x180034bf4  mov     rsi, rdx
0x180034bf7  xor     edx, edx; Val
0x180034bf9  mov     [rbp+200h+var_268], r8
0x180034bfd  mov     r15, r8
0x180034c00  mov     [rbp+200h+hdc], rcx
0x180034c04  mov     r14, rcx
0x180034c07  mov     [rsp+300h+var_288], r12
0x180034c0c  lea     rcx, [rbp+200h+EnhMetaHeader]; void *
0x180034c13  mov     rdi, r9
0x180034c16  lea     r8d, [rdx+6Ch]; Size
0x180034c1a  call    memset_0
0x180034c1f  xor     r13d, r13d
0x180034c22  lea     rcx, [rbp+200h+var_220]; void *
0x180034c26  xorps   xmm0, xmm0
0x180034c29  mov     [rsp+300h+NumberOfBytesRead], r13d
0x180034c2e  xorps   xmm1, xmm1
0x180034c31  xor     edx, edx; Val
0x180034c33  movups  xmmword ptr [rbp+200h+rc.left], xmm0
0x180034c37  lea     r8d, [r13+7Ch]; Size
0x180034c3b  movups  xmmword ptr [rbp+200h+var_1A0.x], xmm1
0x180034c3f  call    memset_0
0x180034c44  xor     eax, eax
0x180034c46  lea     rcx, [rbp+200h+nNumber]; void *
0x180034c4d  xorps   xmm0, xmm0
0x180034c50  mov     [rbp+200h+var_228], eax
0x180034c53  xor     edx, edx; Val
0x180034c55  movups  [rbp+200h+Buffer], xmm0
0x180034c59  lea     ebx, [rax+5Ch]
0x180034c5c  mov     r8d, ebx; Size
0x180034c5f  movups  xmmword ptr [rbp+200h+Size], xmm0
0x180034c63  call    memset_0
0x180034c68  mov     r8d, ebx; Size
0x180034c6b  lea     rcx, [rbp+200h+lf]; void *
0x180034c72  xor     edx, edx; Val
0x180034c74  call    memset_0
0x180034c79  mov     [rsp+300h+ho], r13
0x180034c7e  mov     qword ptr [rbp+200h+sz.cx], r13
0x180034c82  mov     qword ptr [rbp+200h+pt.x], r13
0x180034c86  mov     qword ptr [rbp+200h+var_278.cx], r13
0x180034c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c91  lea     rax, WPP_GLOBAL_Control
0x180034c98  lea     ebx, [r13+0Bh]
0x180034c9c  cmp     rcx, rax
0x180034c9f  jz      short loc_180034CBF
0x180034ca1  test    byte ptr [rcx+1Ch], 2
0x180034ca5  jz      short loc_180034CBF
0x180034ca7  cmp     byte ptr [rcx+19h], 5
0x180034cab  jb      short loc_180034CBF
0x180034cad  mov     rcx, [rcx+10h]
0x180034cb1  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x180034cb8  mov     edx, ebx
0x180034cba  call    WPP_SF_
0x180034cbf  xorps   xmm0, xmm0
0x180034cc2  mov     qword ptr [rbp+200h+var_1A0.x], r13
0x180034cc6  mov     qword ptr [rbp+200h+var_1A0.x+8], r13
0x180034cca  lea     rcx, [r15+8]
0x180034cce  mov     [rsp+300h+var_2B4], r13d
0x180034cd3  mov     rax, r15
0x180034cd6  neg     rax
0x180034cd9  movups  [rbp+200h+Buffer], xmm0
0x180034cdd  sbb     r13, r13
0x180034ce0  xor     eax, eax
0x180034ce2  and     r13, rcx
0x180034ce5  mov     [rbp+200h+var_228], eax
0x180034ce8  xor     edx, edx; Val
0x180034cea  mov     [rbp+200h+var_258], r13
0x180034cee  lea     rcx, [rbp+200h+var_220]; void *
0x180034cf2  lea     r8d, [rax+7Ch]; Size
0x180034cf6  movups  xmmword ptr [rbp+200h+Size], xmm0
0x180034cfa  call    memset_0
0x180034cff  xor     r9d, r9d; lpSecurityAttributes
0x180034d02  mov     [rsp+300h+hTemplateFile], 0; hTemplateFile
0x180034d0b  mov     [rsp+300h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180034d13  mov     edx, 80000000h; dwDesiredAccess
0x180034d18  mov     rcx, rdi; lpFileName
0x180034d1b  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x180034d23  lea     r8d, [r9+1]; dwShareMode
0x180034d27  call    cs:__imp_CreateFileW
0x180034d2e  nop     dword ptr [rax+rax+00h]
0x180034d33  mov     [rsp+300h+hFile], rax
0x180034d38  mov     r15, rax
0x180034d3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034d3f  jnz     short loc_180034D99
0x180034d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d48  lea     rax, WPP_GLOBAL_Control
0x180034d4f  cmp     rcx, rax
0x180034d52  jz      short loc_180034D7F
0x180034d54  test    byte ptr [rcx+1Ch], 2
0x180034d58  jz      short loc_180034D7F
0x180034d5a  cmp     byte ptr [rcx+19h], 2
0x180034d5e  jb      short loc_180034D7F
0x180034d60  mov     rcx, [rcx+10h]
0x180034d64  lea     edx, [r15+0Dh]
0x180034d68  mov     r9, rdi
0x180034d6b  mov     [rsp+300h+dwCreationDisposition], 0
0x180034d73  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x180034d7a  call    WPP_SF_Sd
0x180034d7f  call    cs:__imp_GetLastError
0x180034d86  nop     dword ptr [rax+rax+00h]
0x180034d8b  mov     rdi, [rsp+300h+ho]
0x180034d90  mov     ebx, eax
0x180034d92  mov     esi, edi
0x180034d94  jmp     loc_180035BA2
0x180034d99  xor     edi, edi
0x180034d9b  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180034da0  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x180034da4  mov     [rsp+300h+nSavedDC], edi
0x180034da8  mov     rcx, r15; hFile
0x180034dab  mov     qword ptr [rsp+300h+dwCreationDisposition], rdi; lpOverlapped
0x180034db0  lea     r8d, [rdi+24h]; nNumberOfBytesToRead
0x180034db4  call    cs:__imp_ReadFile
0x180034dbb  nop     dword ptr [rax+rax+00h]
0x180034dc0  test    eax, eax
0x180034dc2  jnz     short loc_180034E05
0x180034dc4  call    cs:__imp_GetLastError
0x180034dcb  nop     dword ptr [rax+rax+00h]
0x180034dd0  mov     ebx, eax
0x180034dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180034dd9  lea     rax, WPP_GLOBAL_Control
0x180034de0  cmp     rcx, rax
0x180034de3  jz      loc_180035B6F
0x180034de9  test    byte ptr [rcx+1Ch], 2
0x180034ded  jz      loc_180035B6F
0x180034df3  cmp     byte ptr [rcx+19h], 2
0x180034df7  jb      loc_180035B6F
0x180034dfd  lea     edx, [rdi+0Dh]
0x180034e00  jmp     loc_180035B5C
0x180034e05  cmp     [rsp+300h+NumberOfBytesRead], 24h ; '$'
0x180034e0a  jnz     loc_180035B38
0x180034e10  mov     r8d, 14h; Size
0x180034e16  lea     rdx, [rbp+200h+Buffer]; Buf2
0x180034e1a  lea     rcx, UNICODE_Signature; Buf1
0x180034e21  call    memcmp_0
0x180034e26  test    eax, eax
0x180034e28  jnz     loc_180035B38
0x180034e2e  mov     ecx, dword ptr [rbp+200h+Size+4]; Size
0x180034e31  call    cs:__imp_malloc
0x180034e38  nop     dword ptr [rax+rax+00h]
0x180034e3d  mov     [rbp+200h+Block], rax
0x180034e41  mov     rbx, rax
0x180034e44  test    rax, rax
0x180034e47  jnz     short loc_180034E87
0x180034e49  lea     r15d, [rax+8]
0x180034e4d  mov     ebx, r15d
0x180034e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e57  lea     rax, WPP_GLOBAL_Control
0x180034e5e  cmp     rcx, rax
0x180034e61  jz      loc_180035B6F
0x180034e67  test    byte ptr [rcx+1Ch], 2
0x180034e6b  jz      loc_180035B6F
0x180034e71  cmp     byte ptr [rcx+19h], 2
0x180034e75  jb      loc_180035B6F
0x180034e7b  lea     edx, [r15+7]
0x180034e7f  mov     r9d, r15d
0x180034e82  jmp     loc_180035B5F
0x180034e87  mov     r8d, dword ptr [rbp+200h+Size+4]; nNumberOfBytesToRead
0x180034e8b  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180034e90  mov     rdx, rbx; lpBuffer
0x180034e93  mov     qword ptr [rsp+300h+dwCreationDisposition], rdi; lpOverlapped
0x180034e98  mov     rcx, r15; hFile
0x180034e9b  call    cs:__imp_ReadFile
0x180034ea2  nop     dword ptr [rax+rax+00h]
0x180034ea7  test    eax, eax
0x180034ea9  jz      loc_180035AF5
0x180034eaf  mov     eax, [rsp+300h+NumberOfBytesRead]
0x180034eb3  cmp     dword ptr [rbp+200h+Size+4], eax
0x180034eb6  jnz     loc_180035AF5
0x180034ebc  mov     [rsp+300h+hmf], rdi
0x180034ec1  mov     r15d, 8
0x180034ec7  mov     [rsp+300h+lpchText], rdi
0x180034ecc  test    r14, r14
0x180034ecf  jz      loc_1800353C9
0x180034ed5  mov     rcx, rsi; lprect
0x180034ed8  call    cs:__imp_CreateRectRgnIndirect
0x180034edf  nop     dword ptr [rax+rax+00h]
0x180034ee4  mov     [rsp+300h+ho], rax
0x180034ee9  test    rax, rax
0x180034eec  jnz     short loc_180034F43
0x180034eee  call    cs:__imp_GetLastError
0x180034ef5  nop     dword ptr [rax+rax+00h]
0x180034efa  mov     ebx, eax
0x180034efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f03  lea     rax, WPP_GLOBAL_Control
0x180034f0a  cmp     rcx, rax
0x180034f0d  jz      loc_180035152
0x180034f13  test    byte ptr [rcx+1Ch], 2
0x180034f17  jz      loc_180035152
0x180034f1d  cmp     byte ptr [rcx+19h], 2
0x180034f21  jb      loc_180035152
0x180034f27  lea     edx, [r15+9]
0x180034f2b  mov     r9d, ebx
0x180034f2e  mov     rcx, [rcx+10h]
0x180034f32  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x180034f39  call    WPP_SF_d
0x180034f3e  jmp     loc_180035152
0x180034f43  mov     rdx, rax; hrgn
0x180034f46  mov     rcx, r14; hdc
0x180034f49  call    cs:__imp_SelectClipRgn
0x180034f50  nop     dword ptr [rax+rax+00h]
0x180034f55  test    eax, eax
0x180034f57  jnz     short loc_180034F8F
0x180034f59  lea     ebx, [rax+1Fh]
0x180034f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f63  lea     rax, WPP_GLOBAL_Control
0x180034f6a  cmp     rcx, rax
0x180034f6d  jz      loc_180035152
0x180034f73  test    byte ptr [rcx+1Ch], 2
0x180034f77  jz      loc_180035152
0x180034f7d  cmp     byte ptr [rcx+19h], 2
0x180034f81  jb      loc_180035152
0x180034f87  lea     edx, [rbx-0Dh]
0x180034f8a  xor     r9d, r9d
0x180034f8d  jmp     short loc_180034F2E
0x180034f8f  mov     rcx, r14; hdc
0x180034f92  call    cs:__imp_SaveDC
0x180034f99  nop     dword ptr [rax+rax+00h]
0x180034f9e  mov     [rsp+300h+nSavedDC], eax
0x180034fa2  test    eax, eax
0x180034fa4  jnz     short loc_180034FE9
0x180034fa6  call    cs:__imp_GetLastError
0x180034fad  nop     dword ptr [rax+rax+00h]
0x180034fb2  mov     ebx, eax
0x180034fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fbb  lea     rax, WPP_GLOBAL_Control
0x180034fc2  cmp     rcx, rax
0x180034fc5  jz      loc_180035152
0x180034fcb  test    byte ptr [rcx+1Ch], 2
0x180034fcf  jz      loc_180035152
0x180034fd5  cmp     byte ptr [rcx+19h], 2
0x180034fd9  jb      loc_180035152
0x180034fdf  mov     edx, 13h
0x180034fe4  jmp     loc_180034F2B
0x180034fe9  mov     ecx, dword ptr [rbp+200h+Size+4]; nSize
0x180034fec  test    ecx, ecx
0x180034fee  jnz     short loc_180035036
0x180034ff0  lea     ebx, [rcx+12h]
0x180034ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ffa  lea     rax, WPP_GLOBAL_Control
0x180035001  cmp     rcx, rax
0x180035004  jz      loc_180035152
0x18003500a  test    byte ptr [rcx+1Ch], 2
0x18003500e  jz      loc_180035152
0x180035014  cmp     byte ptr [rcx+19h], 2
0x180035018  jb      loc_180035152
0x18003501e  mov     rcx, [rcx+10h]
0x180035022  lea     edx, [rbx+2]
0x180035025  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x18003502c  call    WPP_SF_
0x180035031  jmp     loc_180035152
0x180035036  mov     rdx, rbx; pb
0x180035039  call    cs:__imp_SetEnhMetaFileBits
0x180035040  nop     dword ptr [rax+rax+00h]
0x180035045  mov     rbx, rax
0x180035048  mov     [rsp+300h+hmf], rax
0x18003504d  xor     eax, eax
0x18003504f  test    rbx, rbx
0x180035052  jnz     short loc_180035097
0x180035054  call    cs:__imp_GetLastError
0x18003505b  nop     dword ptr [rax+rax+00h]
0x180035060  mov     ebx, eax
0x180035062  mov     rcx, cs:WPP_GLOBAL_Control
0x180035069  lea     rax, WPP_GLOBAL_Control
0x180035070  cmp     rcx, rax
0x180035073  jz      loc_180035152
0x180035079  test    byte ptr [rcx+1Ch], 2
0x18003507d  jz      loc_180035152
0x180035083  cmp     byte ptr [rcx+19h], 2
0x180035087  jb      loc_180035152
0x18003508d  mov     edx, 15h
0x180035092  jmp     loc_180034F2B
0x180035097  lea     r8, [rbp+200h+EnhMetaHeader]; lpEnhMetaHeader
0x18003509e  mov     edx, 6Ch ; 'l'; nSize
0x1800350a3  mov     rcx, rbx; hemf
0x1800350a6  mov     r12, rax
0x1800350a9  call    cs:__imp_GetEnhMetaFileHeader
0x1800350b0  nop     dword ptr [rax+rax+00h]
0x1800350b5  test    eax, eax
0x1800350b7  jnz     loc_180035167
0x1800350bd  call    cs:__imp_GetLastError
0x1800350c4  nop     dword ptr [rax+rax+00h]
0x1800350c9  mov     ebx, eax
0x1800350cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350d2  lea     rax, WPP_GLOBAL_Control
0x1800350d9  cmp     rcx, rax
0x1800350dc  jz      short loc_180035102
0x1800350de  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
