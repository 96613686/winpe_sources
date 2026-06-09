# RenderCoverPage

- ea: `0x14007965c`
- end: `0x14007a5b4`
- name: `RenderCoverPage`
- size: `3928`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, RECT *lprect@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x140079000`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140004e68`
- `0x140035158`
- `0x1400354bc`
- `0x140065dbc`
- `0x140067168`
- `0x140072250`
- `0x140078f30`
- `0x14007965c`
- `0x140081866`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x140079fee`
- `KERNEL32!MulDiv` at `0x140079fee`
- `KERNEL32!CreateFileW` at `0x1400797c3`
- `KERNEL32!CreateFileW` at `0x1400797c3`
- `KERNEL32!GetLastError` at `0x140079815`
- `KERNEL32!GetLastError` at `0x14007984e`
- `KERNEL32!GetLastError` at `0x140079960`
- `KERNEL32!GetLastError` at `0x140079a06`
- `KERNEL32!GetLastError` at `0x140079aa8`
- `KERNEL32!GetLastError` at `0x140079b05`
- `KERNEL32!GetLastError` at `0x140079ba4`
- `KERNEL32!GetLastError` at `0x140079bff`
- `KERNEL32!GetLastError` at `0x140079c4c`
- `KERNEL32!GetLastError` at `0x140079ca4`
- `KERNEL32!GetLastError` at `0x140079cff`
- `KERNEL32!GetLastError` at `0x140079d64`
- `KERNEL32!GetLastError` at `0x14007a13f`
- `KERNEL32!GetLastError` at `0x14007a242`
- `KERNEL32!GetLastError` at `0x14007a29d`
- `KERNEL32!GetLastError` at `0x14007a2da`
- `KERNEL32!GetLastError` at `0x14007a34c`
- `KERNEL32!GetLastError` at `0x14007a389`
- `KERNEL32!GetLastError` at `0x14007a412`
- `KERNEL32!GetLastError` at `0x14007a466`
- `KERNEL32!GetLastError` at `0x140079815`
- `KERNEL32!GetLastError` at `0x14007984e`
- `KERNEL32!GetLastError` at `0x140079960`
- `KERNEL32!GetLastError` at `0x140079a06`
- `KERNEL32!GetLastError` at `0x140079aa8`
- `KERNEL32!GetLastError` at `0x140079b05`
- `KERNEL32!GetLastError` at `0x140079ba4`
- `KERNEL32!GetLastError` at `0x140079bff`
- `KERNEL32!GetLastError` at `0x140079c4c`
- `KERNEL32!GetLastError` at `0x140079ca4`
- `KERNEL32!GetLastError` at `0x140079cff`
- `KERNEL32!GetLastError` at `0x140079d64`
- `KERNEL32!GetLastError` at `0x14007a13f`
- `KERNEL32!GetLastError` at `0x14007a242`
- `KERNEL32!GetLastError` at `0x14007a29d`
- `KERNEL32!GetLastError` at `0x14007a2da`
- `KERNEL32!GetLastError` at `0x14007a34c`
- `KERNEL32!GetLastError` at `0x14007a389`
- `KERNEL32!GetLastError` at `0x14007a412`
- `KERNEL32!GetLastError` at `0x14007a466`
- `KERNEL32!CloseHandle` at `0x14007a4e8`
- `KERNEL32!CloseHandle` at `0x14007a4e8`
- `KERNEL32!ReadFile` at `0x140079844`
- `KERNEL32!ReadFile` at `0x140079919`
- `KERNEL32!ReadFile` at `0x140079e1e`
- `KERNEL32!ReadFile` at `0x140079e9d`
- `KERNEL32!ReadFile` at `0x14007a12c`
- `KERNEL32!ReadFile` at `0x140079844`
- `KERNEL32!ReadFile` at `0x140079919`
- `KERNEL32!ReadFile` at `0x140079e1e`
- `KERNEL32!ReadFile` at `0x140079e9d`
- `KERNEL32!ReadFile` at `0x14007a12c`
- `msvcrt!realloc` at `0x140079e6e`
- `msvcrt!realloc` at `0x140079e6e`
- `msvcrt!malloc` at `0x1400798b5`
- `msvcrt!malloc` at `0x140079da6`
- `msvcrt!malloc` at `0x1400798b5`
- `msvcrt!malloc` at `0x140079da6`
- `msvcrt!free` at `0x140079b77`
- `msvcrt!free` at `0x140079b86`
- `msvcrt!free` at `0x140079b77`
- `msvcrt!free` at `0x140079b86`
- `GDI32!SaveDC` at `0x1400799f8`
- `GDI32!SaveDC` at `0x1400799f8`
- `GDI32!SelectObject` at `0x14007a06d`
- `GDI32!SelectObject` at `0x14007a0d7`
- `GDI32!SelectObject` at `0x14007a06d`
- `GDI32!SelectObject` at `0x14007a0d7`
- `GDI32!PlayEnhMetaFile` at `0x140079b9a`
- `GDI32!PlayEnhMetaFile` at `0x140079b9a`
- `GDI32!SetEnhMetaFileBits` at `0x140079a93`
- `GDI32!SetEnhMetaFileBits` at `0x140079a93`
- `GDI32!SetWindowOrgEx` at `0x140079d5a`
- `GDI32!SetWindowOrgEx` at `0x140079d5a`
- `GDI32!CreateRectRgnIndirect` at `0x140079950`
- `GDI32!CreateRectRgnIndirect` at `0x140079950`
- `GDI32!GetEnhMetaFileHeader` at `0x140079af7`
- `GDI32!GetEnhMetaFileHeader` at `0x140079af7`
- `GDI32!SetWindowExtEx` at `0x140079c9a`
- `GDI32!SetWindowExtEx` at `0x140079c9a`
- `GDI32!DeleteEnhMetaFile` at `0x140079b49`
- `GDI32!DeleteEnhMetaFile` at `0x140079b49`
- `GDI32!SetViewportExtEx` at `0x140079cf5`
- `GDI32!SetViewportExtEx` at `0x140079cf5`
- `GDI32!GetDeviceCaps` at `0x140079fdc`
- `GDI32!GetDeviceCaps` at `0x140079fdc`
- `GDI32!SetTextColor` at `0x14007a01d`
- `GDI32!SetTextColor` at `0x14007a0e3`
- `GDI32!SetTextColor` at `0x14007a01d`
- `GDI32!SetTextColor` at `0x14007a0e3`
- `GDI32!SetBkMode` at `0x140079bf0`
- `GDI32!SetBkMode` at `0x140079bf0`
- `GDI32!SelectClipRgn` at `0x1400799b5`
- `GDI32!SelectClipRgn` at `0x1400799b5`
- `GDI32!RestoreDC` at `0x140079be2`
- `GDI32!RestoreDC` at `0x14007a4fb`
- `GDI32!RestoreDC` at `0x140079be2`
- `GDI32!RestoreDC` at `0x14007a4fb`
- `GDI32!LPtoDP` at `0x140079fb6`
- `GDI32!LPtoDP` at `0x140079fb6`
- `GDI32!DeleteObject` at `0x140079b69`
- `GDI32!DeleteObject` at `0x14007a0ec`
- `GDI32!DeleteObject` at `0x14007a589`
- `GDI32!DeleteObject` at `0x140079b69`
- `GDI32!DeleteObject` at `0x14007a0ec`
- `GDI32!DeleteObject` at `0x14007a589`
- `GDI32!SetMapMode` at `0x140079c42`
- `GDI32!SetMapMode` at `0x140079c42`
- `GDI32!CreateFontIndirectW` at `0x14007a055`
- `GDI32!CreateFontIndirectW` at `0x14007a055`
- `USER32!DrawTextW` at `0x14007a0c3`
- `USER32!DrawTextW` at `0x14007a0c3`

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
  CMapDeviceId *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rax
  const BYTE *v20; // rbx
  __int64 v21; // r9
  HRGN RectRgnIndirect; // rax
  CMapDeviceId *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  HENHMETAFILE v26; // rbx
  void *v27; // r12
  CMapDeviceId *v28; // rcx
  __int64 v29; // rdx
  HENHMETAFILE v30; // rcx
  void *v31; // r12
  CMapDeviceId *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  unsigned int v35; // esi
  DWORD v36; // r8d
  unsigned __int64 v37; // rdi
  void *v38; // rax
  LPCWSTR v39; // rdi
  LONG v40; // r9d
  LONG v41; // eax
  LONG v42; // r8d
  LONG v43; // eax
  const WCHAR *v44; // rsi
  signed int v45; // eax
  int v46; // ecx
  int DeviceCaps; // eax
  COLORREF v48; // r13d
  HFONT v49; // rax
  HGDIOBJ v50; // r12
  int v51; // r14d
  int v52; // eax
  CMapDeviceId *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r9
  CMapDeviceId *v56; // rcx
  __int64 v57; // rdx
  __int128 v58; // xmm1
  __int16 v59; // ax
  __int16 v60; // ax
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  HENHMETAFILE hmf; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  int v68; // [rsp+4Ch] [rbp-B4h]
  unsigned int v69; // [rsp+50h] [rbp-B0h]
  int nSavedDC; // [rsp+54h] [rbp-ACh]
  void *v71; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpchText; // [rsp+60h] [rbp-A0h]
  HANDLE hFile; // [rsp+68h] [rbp-98h]
  HGDIOBJ ho; // [rsp+70h] [rbp-90h]
  __int64 v75; // [rsp+78h] [rbp-88h]
  struct tagSIZE sz; // [rsp+80h] [rbp-80h] BYREF
  struct tagSIZE v77; // [rsp+88h] [rbp-78h] BYREF
  tagPOINT pt; // [rsp+90h] [rbp-70h] BYREF
  __int64 v79; // [rsp+98h] [rbp-68h]
  HDC hdca; // [rsp+A0h] [rbp-60h]
  __int64 v81; // [rsp+A8h] [rbp-58h]
  void *Block; // [rsp+B0h] [rbp-50h]
  __int128 Buffer; // [rsp+B8h] [rbp-48h] BYREF
  size_t Size[2]; // [rsp+C8h] [rbp-38h]
  int v85; // [rsp+D8h] [rbp-28h]
  LONG v86; // [rsp+E0h] [rbp-20h] BYREF
  LONG v87; // [rsp+E4h] [rbp-1Ch]
  LONG v88; // [rsp+E8h] [rbp-18h]
  LONG v89; // [rsp+ECh] [rbp-14h]
  COLORREF color; // [rsp+F0h] [rbp-10h]
  int v91; // [rsp+F4h] [rbp-Ch]
  _BYTE v92[92]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v93; // [rsp+154h] [rbp+54h]
  DWORD nNumberOfBytesToRead; // [rsp+158h] [rbp+58h]
  struct tagPOINT v95[2]; // [rsp+160h] [rbp+60h] BYREF
  tagRECT rc; // [rsp+170h] [rbp+70h] BYREF
  int nNumber[4]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v98; // [rsp+190h] [rbp+90h]
  __int128 v99; // [rsp+1A0h] [rbp+A0h]
  __int128 v100; // [rsp+1B0h] [rbp+B0h]
  _OWORD v101[2]; // [rsp+1C0h] [rbp+C0h]
  LOGFONTW lf; // [rsp+1E0h] [rbp+E0h] BYREF
  tagENHMETAHEADER EnhMetaHeader; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v104[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int16 v105; // [rsp+2B2h] [rbp+1B2h]
  __int16 v106; // [rsp+2B4h] [rbp+1B4h]

  v5 = a5;
  v79 = a3;
  hdca = hdc;
  v8 = hdc;
  v75 = a5;
  memset_0(&EnhMetaHeader, 0, sizeof(EnhMetaHeader));
  NumberOfBytesRead = 0;
  rc = 0;
  *(_OWORD *)&v95[0].x = 0;
  memset_0(&v86, 0, 0x7Cu);
  v85 = 0;
  Buffer = 0;
  *(_OWORD *)Size = 0;
  memset_0(nNumber, 0, 0x5Cu);
  memset_0(&lf, 0, sizeof(lf));
  ho = 0;
  sz = 0;
  pt = 0;
  v77 = 0;
  LastError = 11;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
  }
  v95[0] = 0;
  v95[1] = 0;
  v68 = 0;
  Buffer = 0;
  v11 = (a3 + 8) & -(__int64)(a3 != 0);
  v85 = 0;
  v81 = v11;
  *(_OWORD *)Size = 0;
  memset_0(&v86, 0, 0x7Cu);
  FileW = CreateFileW(a4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  hFile = FileW;
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 15;
        v21 = 8;
LABEL_224:
        WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v21);
        goto LABEL_225;
      }
      goto LABEL_225;
    }
    if ( !ReadFile(v13, v19, HIDWORD(Size[0]), &NumberOfBytesRead, 0) || HIDWORD(Size[0]) != NumberOfBytesRead )
    {
      LastError = GetLastError();
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_68;
      }
      v24 = 16;
LABEL_31:
      v25 = LastError;
LABEL_32:
      WPP_SF_d(*((_QWORD *)v23 + 2), v24, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v25);
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 22;
LABEL_58:
        WPP_SF_d(*((_QWORD *)v28 + 2), v29, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, LastError);
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
        v5 = v75;
        goto LABEL_68;
      }
      if ( !PlayEnhMetaFile(v8, v26, lprect) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 25;
        goto LABEL_58;
      }
      if ( !SetWindowExtEx(v8, SHIDWORD(Size[1]), -v85, &sz) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 26;
        goto LABEL_58;
      }
      if ( !SetViewportExtEx(v8, lprect->right - lprect->left, lprect->bottom - lprect->top, &v77) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 27;
        goto LABEL_58;
      }
      if ( !SetWindowOrgEx(v8, SHIDWORD(Size[1]) / -2, v85 / 2, &pt) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_59;
        }
        v29 = 28;
        goto LABEL_58;
      }
    }
    v71 = malloc(0x40u);
    v31 = v71;
    if ( !v71 )
    {
      LastError = 8;
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
    v69 = 0;
    if ( SLODWORD(Size[1]) > 0 )
    {
      while ( 1 )
      {
        if ( !ReadFile(hFile, &v86, 0x7Cu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 124 )
        {
          LastError = GetLastError();
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_165;
          }
          v57 = 30;
LABEL_214:
          WPP_SF_dd(*((_QWORD *)v56 + 2), v57, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v35, LastError);
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
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_lll(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                32,
                &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids,
                v35,
                v37,
                8);
            }
            goto LABEL_171;
          }
          v36 = nNumberOfBytesToRead;
          v31 = v38;
          v71 = v38;
        }
        v16 = 0;
        if ( !ReadFile(hFile, v31, v36, &NumberOfBytesRead, 0) || NumberOfBytesRead != nNumberOfBytesToRead )
        {
          LastError = GetLastError();
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_165;
          }
          v57 = 33;
          goto LABEL_214;
        }
        *((_WORD *)v31 + ((unsigned __int64)nNumberOfBytesToRead >> 1)) = 0;
        v39 = lpchText;
        if ( lpchText )
        {
          pMemFree((LPVOID)lpchText);
          v39 = 0;
          lpchText = 0;
        }
        if ( v31 )
        {
          lpchText = (LPCWSTR)StringDup((unsigned __int16 *)v31);
          v39 = lpchText;
          if ( !lpchText )
            break;
        }
        if ( v8 )
        {
          v40 = v89;
          v41 = v89;
          v42 = v88;
          if ( v87 > v89 )
            v41 = v87;
          rc.top = v41;
          v43 = v88;
          if ( v86 < v88 )
            v43 = v86;
          rc.left = v43;
          if ( v87 < v89 )
            v40 = v87;
          rc.bottom = v40;
          if ( v86 > v88 )
            v42 = v86;
          rc.right = v42;
        }
        v44 = 0;
        if ( v93 )
        {
          v45 = 0;
          v46 = 1;
          while ( v93 != *((_WORD *)InsertionTagResourceID + v45) )
          {
            ++v45;
            v46 *= 2;
            if ( (unsigned int)v45 >= 0x1D )
            {
              v44 = 0;
              goto LABEL_138;
            }
          }
          v44 = v79 ? *(const WCHAR **)(v11 + 8LL * v45) : 0LL;
          v68 |= v46;
LABEL_138:
          if ( v93 == 2063 && v8 )
          {
            *(tagRECT *)&v95[0].x = rc;
            LPtoDP(v8, v95, 2);
            LastError = CopyWLogFontToTLogFont(v92, nNumber);
            if ( LastError )
            {
              v53 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v54 = 35;
                v55 = LastError;
LABEL_176:
                WPP_SF_d(*((_QWORD *)v53 + 2), v54, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v55);
              }
              goto LABEL_171;
            }
            DeviceCaps = GetDeviceCaps(v8, 90);
            nNumber[0] = MulDiv(nNumber[0], DeviceCaps, 100);
          }
        }
        if ( *v39 )
          v44 = v39;
        v16 = 0;
        if ( v8 && v44 )
        {
          v48 = SetTextColor(v8, color);
          if ( v48 == -1 )
          {
            LastError = GetLastError();
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 36;
LABEL_163:
            v34 = LastError;
LABEL_164:
            WPP_SF_d(*((_QWORD *)v32 + 2), v33, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids, v34);
            goto LABEL_165;
          }
          LastError = CopyWLogFontToTLogFont(v92, &lf);
          if ( LastError )
          {
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 37;
            goto LABEL_163;
          }
          v49 = CreateFontIndirectW(&lf);
          v16 = v49;
          if ( !v49 )
          {
            LastError = GetLastError();
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 38;
            goto LABEL_163;
          }
          v50 = SelectObject(v8, v49);
          if ( !v50 )
          {
            LastError = GetLastError();
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_165;
            }
            v33 = 39;
            goto LABEL_163;
          }
          v51 = 0;
          if ( v93 && (unsigned int)StrHasRTLChar(0x800u, v44) )
            v51 = 0x20000;
          v52 = v51 | v91;
          v8 = hdca;
          if ( !DrawTextW(hdca, v44, -1, &rc, v52 | 0x810) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_lSl(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                43,
                (unsigned int)&WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids,
                v69,
                (__int64)v44,
                LastError);
            }
            goto LABEL_165;
          }
          SelectObject(v8, v50);
          SetTextColor(v8, v48);
          DeleteObject(v16);
          v31 = v71;
          v16 = 0;
          v11 = v81;
        }
        v35 = v69 + 1;
        v69 = v35;
        if ( (int)v35 >= SLODWORD(Size[1]) )
          goto LABEL_156;
      }
      LastError = 8;
      v53 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v54 = 34;
        v55 = 8;
        goto LABEL_176;
      }
LABEL_171:
      v16 = 0;
      goto LABEL_165;
    }
LABEL_156:
    if ( ReadFile(hFile, v104, 6u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == 6 )
        goto LABEL_165;
      v16 = 0;
    }
    LastError = GetLastError();
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = 44;
      goto LABEL_163;
    }
LABEL_165:
    v30 = hmf;
    v27 = v71;
    if ( !hmf )
      goto LABEL_61;
    goto LABEL_60;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 14;
    goto LABEL_223;
  }
LABEL_225:
  v14 = ho;
  v15 = v68;
  CloseHandle(hFile);
  if ( nSavedDC )
    RestoreDC(v8, nSavedDC);
LABEL_227:
  if ( !LastError && v5 )
  {
    v58 = v98;
    v59 = v105;
    *(_OWORD *)(v5 + 4) = *(_OWORD *)&v95[0].x;
    *(_WORD *)(v5 + 22) = v59;
    v60 = v106;
    *(_OWORD *)(v5 + 24) = *(_OWORD *)nNumber;
    *(_DWORD *)v5 = v15;
    v61 = v99;
    *(_OWORD *)(v5 + 40) = v58;
    *(_WORD *)(v5 + 20) = v60;
    v62 = v100;
    *(_OWORD *)(v5 + 56) = v61;
    v63 = v101[0];
    *(_OWORD *)(v5 + 72) = v62;
    v64 = *(_OWORD *)((char *)v101 + 12);
    *(_OWORD *)(v5 + 88) = v63;
    *(_OWORD *)(v5 + 100) = v64;
  }
  if ( v14 )
    DeleteObject(v14);
  return LastError;
}

```

## disassembly

```asm
0x14007965c  push    rbp
0x14007965e  push    rbx
0x14007965f  push    rsi
0x140079660  push    rdi
0x140079661  push    r12
0x140079663  push    r13
0x140079665  push    r14
0x140079667  push    r15
0x140079669  lea     rbp, [rsp-1C8h]
0x140079671  sub     rsp, 2C8h
0x140079678  mov     rax, cs:__security_cookie
0x14007967f  xor     rax, rsp
0x140079682  mov     [rbp+200h+var_48], rax
0x140079689  mov     r12, [rbp+200h+arg_20]
0x140079690  mov     rsi, rdx
0x140079693  xor     edx, edx; Val
0x140079695  mov     [rbp+200h+var_268], r8
0x140079699  mov     r15, r8
0x14007969c  mov     [rbp+200h+hdc], rcx
0x1400796a0  mov     r14, rcx
0x1400796a3  mov     [rsp+300h+var_288], r12
0x1400796a8  lea     rcx, [rbp+200h+EnhMetaHeader]; void *
0x1400796af  mov     rdi, r9
0x1400796b2  lea     r8d, [rdx+6Ch]; Size
0x1400796b6  call    memset_0
0x1400796bb  xor     r13d, r13d
0x1400796be  lea     rcx, [rbp+200h+var_220]; void *
0x1400796c2  xorps   xmm0, xmm0
0x1400796c5  mov     [rsp+300h+NumberOfBytesRead], r13d
0x1400796ca  xorps   xmm1, xmm1
0x1400796cd  xor     edx, edx; Val
0x1400796cf  movups  xmmword ptr [rbp+200h+rc.left], xmm0
0x1400796d3  lea     r8d, [r13+7Ch]; Size
0x1400796d7  movups  xmmword ptr [rbp+200h+var_1A0.x], xmm1
0x1400796db  call    memset_0
0x1400796e0  xor     eax, eax
0x1400796e2  lea     rcx, [rbp+200h+nNumber]; void *
0x1400796e9  xorps   xmm0, xmm0
0x1400796ec  mov     [rbp+200h+var_228], eax
0x1400796ef  xor     edx, edx; Val
0x1400796f1  movups  [rbp+200h+Buffer], xmm0
0x1400796f5  lea     ebx, [rax+5Ch]
0x1400796f8  mov     r8d, ebx; Size
0x1400796fb  movups  xmmword ptr [rbp+200h+Size], xmm0
0x1400796ff  call    memset_0
0x140079704  mov     r8d, ebx; Size
0x140079707  lea     rcx, [rbp+200h+lf]; void *
0x14007970e  xor     edx, edx; Val
0x140079710  call    memset_0
0x140079715  mov     [rsp+300h+ho], r13
0x14007971a  mov     qword ptr [rbp+200h+sz.cx], r13
0x14007971e  mov     qword ptr [rbp+200h+pt.x], r13
0x140079722  mov     qword ptr [rbp+200h+var_278.cx], r13
0x140079726  mov     rcx, cs:WPP_GLOBAL_Control
0x14007972d  lea     rax, WPP_GLOBAL_Control
0x140079734  lea     ebx, [r13+0Bh]
0x140079738  cmp     rcx, rax
0x14007973b  jz      short loc_14007975B
0x14007973d  test    byte ptr [rcx+1Ch], 2
0x140079741  jz      short loc_14007975B
0x140079743  cmp     byte ptr [rcx+19h], 5
0x140079747  jb      short loc_14007975B
0x140079749  mov     rcx, [rcx+10h]
0x14007974d  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079754  mov     edx, ebx
0x140079756  call    WPP_SF_
0x14007975b  xorps   xmm0, xmm0
0x14007975e  mov     qword ptr [rbp+200h+var_1A0.x], r13
0x140079762  mov     qword ptr [rbp+200h+var_1A0.x+8], r13
0x140079766  lea     rcx, [r15+8]
0x14007976a  mov     [rsp+300h+var_2B4], r13d
0x14007976f  mov     rax, r15
0x140079772  neg     rax
0x140079775  movups  [rbp+200h+Buffer], xmm0
0x140079779  sbb     r13, r13
0x14007977c  xor     eax, eax
0x14007977e  and     r13, rcx
0x140079781  mov     [rbp+200h+var_228], eax
0x140079784  xor     edx, edx; Val
0x140079786  mov     [rbp+200h+var_258], r13
0x14007978a  lea     rcx, [rbp+200h+var_220]; void *
0x14007978e  lea     r8d, [rax+7Ch]; Size
0x140079792  movups  xmmword ptr [rbp+200h+Size], xmm0
0x140079796  call    memset_0
0x14007979b  xor     r9d, r9d; lpSecurityAttributes
0x14007979e  mov     [rsp+300h+hTemplateFile], 0; hTemplateFile
0x1400797a7  mov     [rsp+300h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400797af  mov     edx, 80000000h; dwDesiredAccess
0x1400797b4  mov     rcx, rdi; lpFileName
0x1400797b7  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x1400797bf  lea     r8d, [r9+1]; dwShareMode
0x1400797c3  call    cs:__imp_CreateFileW
0x1400797c9  mov     [rsp+300h+hFile], rax
0x1400797ce  mov     r15, rax
0x1400797d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400797d5  jnz     short loc_140079829
0x1400797d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400797de  lea     rax, WPP_GLOBAL_Control
0x1400797e5  cmp     rcx, rax
0x1400797e8  jz      short loc_140079815
0x1400797ea  test    byte ptr [rcx+1Ch], 2
0x1400797ee  jz      short loc_140079815
0x1400797f0  cmp     byte ptr [rcx+19h], 2
0x1400797f4  jb      short loc_140079815
0x1400797f6  mov     rcx, [rcx+10h]
0x1400797fa  lea     edx, [r15+0Dh]
0x1400797fe  mov     r9, rdi
0x140079801  mov     [rsp+300h+dwCreationDisposition], 0
0x140079809  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079810  call    WPP_SF_Sd
0x140079815  call    cs:__imp_GetLastError
0x14007981b  mov     rdi, [rsp+300h+ho]
0x140079820  mov     ebx, eax
0x140079822  mov     esi, edi
0x140079824  jmp     loc_14007A501
0x140079829  xor     edi, edi
0x14007982b  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140079830  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x140079834  mov     [rsp+300h+nSavedDC], edi
0x140079838  mov     rcx, r15; hFile
0x14007983b  mov     qword ptr [rsp+300h+dwCreationDisposition], rdi; lpOverlapped
0x140079840  lea     r8d, [rdi+24h]; nNumberOfBytesToRead
0x140079844  call    cs:__imp_ReadFile
0x14007984a  test    eax, eax
0x14007984c  jnz     short loc_140079889
0x14007984e  call    cs:__imp_GetLastError
0x140079854  mov     ebx, eax
0x140079856  mov     rcx, cs:WPP_GLOBAL_Control
0x14007985d  lea     rax, WPP_GLOBAL_Control
0x140079864  cmp     rcx, rax
0x140079867  jz      loc_14007A4DA
0x14007986d  test    byte ptr [rcx+1Ch], 2
0x140079871  jz      loc_14007A4DA
0x140079877  cmp     byte ptr [rcx+19h], 2
0x14007987b  jb      loc_14007A4DA
0x140079881  lea     edx, [rdi+0Dh]
0x140079884  jmp     loc_14007A4C7
0x140079889  cmp     [rsp+300h+NumberOfBytesRead], 24h ; '$'
0x14007988e  jnz     loc_14007A4A3
0x140079894  mov     r8d, 14h; Size
0x14007989a  lea     rdx, [rbp+200h+Buffer]; Buf2
0x14007989e  lea     rcx, UNICODE_Signature; Buf1
0x1400798a5  call    memcmp_0
0x1400798aa  test    eax, eax
0x1400798ac  jnz     loc_14007A4A3
0x1400798b2  mov     ecx, dword ptr [rbp+200h+Size+4]; Size
0x1400798b5  call    cs:__imp_malloc
0x1400798bb  mov     [rbp+200h+Block], rax
0x1400798bf  mov     rbx, rax
0x1400798c2  test    rax, rax
0x1400798c5  jnz     short loc_140079905
0x1400798c7  lea     r15d, [rax+8]
0x1400798cb  mov     ebx, r15d
0x1400798ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400798d5  lea     rax, WPP_GLOBAL_Control
0x1400798dc  cmp     rcx, rax
0x1400798df  jz      loc_14007A4DA
0x1400798e5  test    byte ptr [rcx+1Ch], 2
0x1400798e9  jz      loc_14007A4DA
0x1400798ef  cmp     byte ptr [rcx+19h], 2
0x1400798f3  jb      loc_14007A4DA
0x1400798f9  lea     edx, [r15+7]
0x1400798fd  mov     r9d, r15d
0x140079900  jmp     loc_14007A4CA
0x140079905  mov     r8d, dword ptr [rbp+200h+Size+4]; nNumberOfBytesToRead
0x140079909  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14007990e  mov     rdx, rbx; lpBuffer
0x140079911  mov     qword ptr [rsp+300h+dwCreationDisposition], rdi; lpOverlapped
0x140079916  mov     rcx, r15; hFile
0x140079919  call    cs:__imp_ReadFile
0x14007991f  test    eax, eax
0x140079921  jz      loc_14007A466
0x140079927  mov     eax, [rsp+300h+NumberOfBytesRead]
0x14007992b  cmp     dword ptr [rbp+200h+Size+4], eax
0x14007992e  jnz     loc_14007A466
0x140079934  mov     [rsp+300h+hmf], rdi
0x140079939  mov     r15d, 8
0x14007993f  mov     [rsp+300h+lpchText], rdi
0x140079944  test    r14, r14
0x140079947  jz      loc_140079DA1
0x14007994d  mov     rcx, rsi; lprect
0x140079950  call    cs:__imp_CreateRectRgnIndirect
0x140079956  mov     [rsp+300h+ho], rax
0x14007995b  test    rax, rax
0x14007995e  jnz     short loc_1400799AF
0x140079960  call    cs:__imp_GetLastError
0x140079966  mov     ebx, eax
0x140079968  mov     rcx, cs:WPP_GLOBAL_Control
0x14007996f  lea     rax, WPP_GLOBAL_Control
0x140079976  cmp     rcx, rax
0x140079979  jz      loc_140079B82
0x14007997f  test    byte ptr [rcx+1Ch], 2
0x140079983  jz      loc_140079B82
0x140079989  cmp     byte ptr [rcx+19h], 2
0x14007998d  jb      loc_140079B82
0x140079993  lea     edx, [r15+9]
0x140079997  mov     r9d, ebx
0x14007999a  mov     rcx, [rcx+10h]
0x14007999e  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x1400799a5  call    WPP_SF_d
0x1400799aa  jmp     loc_140079B82
0x1400799af  mov     rdx, rax; hrgn
0x1400799b2  mov     rcx, r14; hdc
0x1400799b5  call    cs:__imp_SelectClipRgn
0x1400799bb  test    eax, eax
0x1400799bd  jnz     short loc_1400799F5
0x1400799bf  lea     ebx, [rax+1Fh]
0x1400799c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400799c9  lea     rax, WPP_GLOBAL_Control
0x1400799d0  cmp     rcx, rax
0x1400799d3  jz      loc_140079B82
0x1400799d9  test    byte ptr [rcx+1Ch], 2
0x1400799dd  jz      loc_140079B82
0x1400799e3  cmp     byte ptr [rcx+19h], 2
0x1400799e7  jb      loc_140079B82
0x1400799ed  lea     edx, [rbx-0Dh]
0x1400799f0  xor     r9d, r9d
0x1400799f3  jmp     short loc_14007999A
0x1400799f5  mov     rcx, r14; hdc
0x1400799f8  call    cs:__imp_SaveDC
0x1400799fe  mov     [rsp+300h+nSavedDC], eax
0x140079a02  test    eax, eax
0x140079a04  jnz     short loc_140079A43
0x140079a06  call    cs:__imp_GetLastError
0x140079a0c  mov     ebx, eax
0x140079a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140079a15  lea     rax, WPP_GLOBAL_Control
0x140079a1c  cmp     rcx, rax
0x140079a1f  jz      loc_140079B82
0x140079a25  test    byte ptr [rcx+1Ch], 2
0x140079a29  jz      loc_140079B82
0x140079a2f  cmp     byte ptr [rcx+19h], 2
0x140079a33  jb      loc_140079B82
0x140079a39  mov     edx, 13h
0x140079a3e  jmp     loc_140079997
0x140079a43  mov     ecx, dword ptr [rbp+200h+Size+4]; nSize
0x140079a46  test    ecx, ecx
0x140079a48  jnz     short loc_140079A90
0x140079a4a  lea     ebx, [rcx+12h]
0x140079a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079a54  lea     rax, WPP_GLOBAL_Control
0x140079a5b  cmp     rcx, rax
0x140079a5e  jz      loc_140079B82
0x140079a64  test    byte ptr [rcx+1Ch], 2
0x140079a68  jz      loc_140079B82
0x140079a6e  cmp     byte ptr [rcx+19h], 2
0x140079a72  jb      loc_140079B82
0x140079a78  mov     rcx, [rcx+10h]
0x140079a7c  lea     edx, [rbx+2]
0x140079a7f  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079a86  call    WPP_SF_
0x140079a8b  jmp     loc_140079B82
0x140079a90  mov     rdx, rbx; pb
0x140079a93  call    cs:__imp_SetEnhMetaFileBits
0x140079a99  mov     rbx, rax
0x140079a9c  mov     [rsp+300h+hmf], rax
0x140079aa1  xor     eax, eax
0x140079aa3  test    rbx, rbx
0x140079aa6  jnz     short loc_140079AE5
0x140079aa8  call    cs:__imp_GetLastError
0x140079aae  mov     ebx, eax
0x140079ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ab7  lea     rax, WPP_GLOBAL_Control
0x140079abe  cmp     rcx, rax
0x140079ac1  jz      loc_140079B82
0x140079ac7  test    byte ptr [rcx+1Ch], 2
0x140079acb  jz      loc_140079B82
0x140079ad1  cmp     byte ptr [rcx+19h], 2
0x140079ad5  jb      loc_140079B82
0x140079adb  mov     edx, 15h
0x140079ae0  jmp     loc_140079997
0x140079ae5  lea     r8, [rbp+200h+EnhMetaHeader]; lpEnhMetaHeader
0x140079aec  mov     edx, 6Ch ; 'l'; nSize
0x140079af1  mov     rcx, rbx; hemf
0x140079af4  mov     r12, rax
0x140079af7  call    cs:__imp_GetEnhMetaFileHeader
0x140079afd  test    eax, eax
0x140079aff  jnz     loc_140079B91
0x140079b05  call    cs:__imp_GetLastError
0x140079b0b  mov     ebx, eax
0x140079b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b14  lea     rax, WPP_GLOBAL_Control
0x140079b1b  cmp     rcx, rax
0x140079b1e  jz      short loc_140079B44
0x140079b20  test    byte ptr [rcx+1Ch], 2
0x140079b24  jz      short loc_140079B44
0x140079b26  cmp     byte ptr [rcx+19h], 2
0x140079b2a  jb      short loc_140079B44
0x140079b2c  mov     edx, 16h
0x140079b31  mov     rcx, [rcx+10h]
0x140079b35  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x140079b3c  mov     r9d, ebx
0x140079b3f  call    WPP_SF_d
0x140079b44  mov     rcx, [rsp+300h+hmf]; hmf
0x140079b49  call    cs:__imp_DeleteEnhMetaFile
0x140079b4f  mov     rax, [rsp+300h+lpchText]
0x140079b54  test    rax, rax
0x140079b57  jz      short loc_140079B61
0x140079b59  mov     rcx, rax; lpMem
0x140079b5c  call    pMemFree
  ... truncated ...
```
