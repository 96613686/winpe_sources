# RenderCoverPage

- ea: `0x14007e520`
- end: `0x14007f5d9`
- name: `RenderCoverPage`
- size: `4281`
- prototype: `__int64 __fastcall(HDC hdc, RECT *lprect, __int64, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14007de2c`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140004fe4`
- `0x140036e08`
- `0x140037184`
- `0x14006998c`
- `0x14006af2c`
- `0x140076b04`
- `0x14007dd54`
- `0x14007e520`
- `0x140086e76`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x14007ef9a`
- `KERNEL32!MulDiv` at `0x14007ef9a`
- `KERNEL32!CreateFileW` at `0x14007e687`
- `KERNEL32!CreateFileW` at `0x14007e687`
- `KERNEL32!GetLastError` at `0x14007e6df`
- `KERNEL32!GetLastError` at `0x14007e724`
- `KERNEL32!GetLastError` at `0x14007e84e`
- `KERNEL32!GetLastError` at `0x14007e906`
- `KERNEL32!GetLastError` at `0x14007e9b4`
- `KERNEL32!GetLastError` at `0x14007ea1d`
- `KERNEL32!GetLastError` at `0x14007eae0`
- `KERNEL32!GetLastError` at `0x14007eb51`
- `KERNEL32!GetLastError` at `0x14007ebaa`
- `KERNEL32!GetLastError` at `0x14007ec0e`
- `KERNEL32!GetLastError` at `0x14007ec75`
- `KERNEL32!GetLastError` at `0x14007ece6`
- `KERNEL32!GetLastError` at `0x14007f121`
- `KERNEL32!GetLastError` at `0x14007f22a`
- `KERNEL32!GetLastError` at `0x14007f28b`
- `KERNEL32!GetLastError` at `0x14007f2ce`
- `KERNEL32!GetLastError` at `0x14007f346`
- `KERNEL32!GetLastError` at `0x14007f389`
- `KERNEL32!GetLastError` at `0x14007f418`
- `KERNEL32!GetLastError` at `0x14007f472`
- `KERNEL32!GetLastError` at `0x14007e6df`
- `KERNEL32!GetLastError` at `0x14007e724`
- `KERNEL32!GetLastError` at `0x14007e84e`
- `KERNEL32!GetLastError` at `0x14007e906`
- `KERNEL32!GetLastError` at `0x14007e9b4`
- `KERNEL32!GetLastError` at `0x14007ea1d`
- `KERNEL32!GetLastError` at `0x14007eae0`
- `KERNEL32!GetLastError` at `0x14007eb51`
- `KERNEL32!GetLastError` at `0x14007ebaa`
- `KERNEL32!GetLastError` at `0x14007ec0e`
- `KERNEL32!GetLastError` at `0x14007ec75`
- `KERNEL32!GetLastError` at `0x14007ece6`
- `KERNEL32!GetLastError` at `0x14007f121`
- `KERNEL32!GetLastError` at `0x14007f22a`
- `KERNEL32!GetLastError` at `0x14007f28b`
- `KERNEL32!GetLastError` at `0x14007f2ce`
- `KERNEL32!GetLastError` at `0x14007f346`
- `KERNEL32!GetLastError` at `0x14007f389`
- `KERNEL32!GetLastError` at `0x14007f418`
- `KERNEL32!GetLastError` at `0x14007f472`
- `KERNEL32!CloseHandle` at `0x14007f4fa`
- `KERNEL32!CloseHandle` at `0x14007f4fa`
- `KERNEL32!ReadFile` at `0x14007e714`
- `KERNEL32!ReadFile` at `0x14007e7fb`
- `KERNEL32!ReadFile` at `0x14007edac`
- `KERNEL32!ReadFile` at `0x14007ee37`
- `KERNEL32!ReadFile` at `0x14007f108`
- `KERNEL32!ReadFile` at `0x14007e714`
- `KERNEL32!ReadFile` at `0x14007e7fb`
- `KERNEL32!ReadFile` at `0x14007edac`
- `KERNEL32!ReadFile` at `0x14007ee37`
- `KERNEL32!ReadFile` at `0x14007f108`
- `msvcrt!realloc` at `0x14007ee02`
- `msvcrt!realloc` at `0x14007ee02`
- `msvcrt!malloc` at `0x14007e791`
- `msvcrt!malloc` at `0x14007ed2e`
- `msvcrt!malloc` at `0x14007e791`
- `msvcrt!malloc` at `0x14007ed2e`
- `msvcrt!free` at `0x14007eaa1`
- `msvcrt!free` at `0x14007eab6`
- `msvcrt!free` at `0x14007eaa1`
- `msvcrt!free` at `0x14007eab6`
- `GDI32!SaveDC` at `0x14007e8f2`
- `GDI32!SaveDC` at `0x14007e8f2`
- `GDI32!SelectObject` at `0x14007f02b`
- `GDI32!SelectObject` at `0x14007f0a1`
- `GDI32!SelectObject` at `0x14007f02b`
- `GDI32!SelectObject` at `0x14007f0a1`
- `GDI32!PlayEnhMetaFile` at `0x14007ead0`
- `GDI32!PlayEnhMetaFile` at `0x14007ead0`
- `GDI32!SetEnhMetaFileBits` at `0x14007e999`
- `GDI32!SetEnhMetaFileBits` at `0x14007e999`
- `GDI32!SetWindowOrgEx` at `0x14007ecd6`
- `GDI32!SetWindowOrgEx` at `0x14007ecd6`
- `GDI32!CreateRectRgnIndirect` at `0x14007e838`
- `GDI32!CreateRectRgnIndirect` at `0x14007e838`
- `GDI32!GetEnhMetaFileHeader` at `0x14007ea09`
- `GDI32!GetEnhMetaFileHeader` at `0x14007ea09`
- `GDI32!SetWindowExtEx` at `0x14007ebfe`
- `GDI32!SetWindowExtEx` at `0x14007ebfe`
- `GDI32!DeleteEnhMetaFile` at `0x14007ea67`
- `GDI32!DeleteEnhMetaFile` at `0x14007ea67`
- `GDI32!SetViewportExtEx` at `0x14007ec65`
- `GDI32!SetViewportExtEx` at `0x14007ec65`
- `GDI32!GetDeviceCaps` at `0x14007ef82`
- `GDI32!GetDeviceCaps` at `0x14007ef82`
- `GDI32!SetTextColor` at `0x14007efcf`
- `GDI32!SetTextColor` at `0x14007f0b3`
- `GDI32!SetTextColor` at `0x14007efcf`
- `GDI32!SetTextColor` at `0x14007f0b3`
- `GDI32!SetBkMode` at `0x14007eb3c`
- `GDI32!SetBkMode` at `0x14007eb3c`
- `GDI32!SelectClipRgn` at `0x14007e8a9`
- `GDI32!SelectClipRgn` at `0x14007e8a9`
- `GDI32!RestoreDC` at `0x14007eb28`
- `GDI32!RestoreDC` at `0x14007f513`
- `GDI32!RestoreDC` at `0x14007eb28`
- `GDI32!RestoreDC` at `0x14007f513`
- `GDI32!LPtoDP` at `0x14007ef56`
- `GDI32!LPtoDP` at `0x14007ef56`
- `GDI32!DeleteObject` at `0x14007ea8d`
- `GDI32!DeleteObject` at `0x14007f0c2`
- `GDI32!DeleteObject` at `0x14007f5a7`
- `GDI32!DeleteObject` at `0x14007ea8d`
- `GDI32!DeleteObject` at `0x14007f0c2`
- `GDI32!DeleteObject` at `0x14007f5a7`
- `GDI32!SetMapMode` at `0x14007eb9a`
- `GDI32!SetMapMode` at `0x14007eb9a`
- `GDI32!CreateFontIndirectW` at `0x14007f00d`
- `GDI32!CreateFontIndirectW` at `0x14007f00d`
- `USER32!DrawTextW` at `0x14007f087`
- `USER32!DrawTextW` at `0x14007f087`

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
  int v35; // esi
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
  int v69; // [rsp+50h] [rbp-B0h]
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
          WPP_SF_dd(*((_QWORD *)v56 + 2), v57, &WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids);
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
                (unsigned int)v35,
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
        if ( v35 >= SLODWORD(Size[1]) )
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
0x14007e520  push    rbp
0x14007e522  push    rbx
0x14007e523  push    rsi
0x14007e524  push    rdi
0x14007e525  push    r12
0x14007e527  push    r13
0x14007e529  push    r14
0x14007e52b  push    r15
0x14007e52d  lea     rbp, [rsp-1C8h]
0x14007e535  sub     rsp, 2C8h
0x14007e53c  mov     rax, cs:__security_cookie
0x14007e543  xor     rax, rsp
0x14007e546  mov     [rbp+200h+var_48], rax
0x14007e54d  mov     r12, [rbp+200h+arg_20]
0x14007e554  mov     rsi, rdx
0x14007e557  xor     edx, edx; Val
0x14007e559  mov     [rbp+200h+var_268], r8
0x14007e55d  mov     r15, r8
0x14007e560  mov     [rbp+200h+hdc], rcx
0x14007e564  mov     r14, rcx
0x14007e567  mov     [rsp+300h+var_288], r12
0x14007e56c  lea     rcx, [rbp+200h+EnhMetaHeader]; void *
0x14007e573  mov     rdi, r9
0x14007e576  lea     r8d, [rdx+6Ch]; Size
0x14007e57a  call    memset_0
0x14007e57f  xor     r13d, r13d
0x14007e582  lea     rcx, [rbp+200h+var_220]; void *
0x14007e586  xorps   xmm0, xmm0
0x14007e589  mov     [rsp+300h+NumberOfBytesRead], r13d
0x14007e58e  xorps   xmm1, xmm1
0x14007e591  xor     edx, edx; Val
0x14007e593  movups  xmmword ptr [rbp+200h+rc.left], xmm0
0x14007e597  lea     r8d, [r13+7Ch]; Size
0x14007e59b  movups  xmmword ptr [rbp+200h+var_1A0.x], xmm1
0x14007e59f  call    memset_0
0x14007e5a4  xor     eax, eax
0x14007e5a6  lea     rcx, [rbp+200h+nNumber]; void *
0x14007e5ad  xorps   xmm0, xmm0
0x14007e5b0  mov     [rbp+200h+var_228], eax
0x14007e5b3  xor     edx, edx; Val
0x14007e5b5  movups  [rbp+200h+Buffer], xmm0
0x14007e5b9  lea     ebx, [rax+5Ch]
0x14007e5bc  mov     r8d, ebx; Size
0x14007e5bf  movups  xmmword ptr [rbp+200h+Size], xmm0
0x14007e5c3  call    memset_0
0x14007e5c8  mov     r8d, ebx; Size
0x14007e5cb  lea     rcx, [rbp+200h+lf]; void *
0x14007e5d2  xor     edx, edx; Val
0x14007e5d4  call    memset_0
0x14007e5d9  mov     [rsp+300h+ho], r13
0x14007e5de  mov     qword ptr [rbp+200h+sz.cx], r13
0x14007e5e2  mov     qword ptr [rbp+200h+pt.x], r13
0x14007e5e6  mov     qword ptr [rbp+200h+var_278.cx], r13
0x14007e5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5f1  lea     rax, WPP_GLOBAL_Control
0x14007e5f8  lea     ebx, [r13+0Bh]
0x14007e5fc  cmp     rcx, rax
0x14007e5ff  jz      short loc_14007E61F
0x14007e601  test    byte ptr [rcx+1Ch], 2
0x14007e605  jz      short loc_14007E61F
0x14007e607  cmp     byte ptr [rcx+19h], 5
0x14007e60b  jb      short loc_14007E61F
0x14007e60d  mov     rcx, [rcx+10h]
0x14007e611  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e618  mov     edx, ebx
0x14007e61a  call    WPP_SF_
0x14007e61f  xorps   xmm0, xmm0
0x14007e622  mov     qword ptr [rbp+200h+var_1A0.x], r13
0x14007e626  mov     qword ptr [rbp+200h+var_1A0.x+8], r13
0x14007e62a  lea     rcx, [r15+8]
0x14007e62e  mov     [rsp+300h+var_2B4], r13d
0x14007e633  mov     rax, r15
0x14007e636  neg     rax
0x14007e639  movups  [rbp+200h+Buffer], xmm0
0x14007e63d  sbb     r13, r13
0x14007e640  xor     eax, eax
0x14007e642  and     r13, rcx
0x14007e645  mov     [rbp+200h+var_228], eax
0x14007e648  xor     edx, edx; Val
0x14007e64a  mov     [rbp+200h+var_258], r13
0x14007e64e  lea     rcx, [rbp+200h+var_220]; void *
0x14007e652  lea     r8d, [rax+7Ch]; Size
0x14007e656  movups  xmmword ptr [rbp+200h+Size], xmm0
0x14007e65a  call    memset_0
0x14007e65f  xor     r9d, r9d; lpSecurityAttributes
0x14007e662  mov     [rsp+300h+hTemplateFile], 0; hTemplateFile
0x14007e66b  mov     [rsp+300h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14007e673  mov     edx, 80000000h; dwDesiredAccess
0x14007e678  mov     rcx, rdi; lpFileName
0x14007e67b  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x14007e683  lea     r8d, [r9+1]; dwShareMode
0x14007e687  call    cs:__imp_CreateFileW
0x14007e68e  nop     dword ptr [rax+rax+00h]
0x14007e693  mov     [rsp+300h+hFile], rax
0x14007e698  mov     r15, rax
0x14007e69b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007e69f  jnz     short loc_14007E6F9
0x14007e6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e6a8  lea     rax, WPP_GLOBAL_Control
0x14007e6af  cmp     rcx, rax
0x14007e6b2  jz      short loc_14007E6DF
0x14007e6b4  test    byte ptr [rcx+1Ch], 2
0x14007e6b8  jz      short loc_14007E6DF
0x14007e6ba  cmp     byte ptr [rcx+19h], 2
0x14007e6be  jb      short loc_14007E6DF
0x14007e6c0  mov     rcx, [rcx+10h]
0x14007e6c4  lea     edx, [r15+0Dh]
0x14007e6c8  mov     r9, rdi
0x14007e6cb  mov     [rsp+300h+dwCreationDisposition], 0
0x14007e6d3  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e6da  call    WPP_SF_Sd
0x14007e6df  call    cs:__imp_GetLastError
0x14007e6e6  nop     dword ptr [rax+rax+00h]
0x14007e6eb  mov     rdi, [rsp+300h+ho]
0x14007e6f0  mov     ebx, eax
0x14007e6f2  mov     esi, edi
0x14007e6f4  jmp     loc_14007F51F
0x14007e6f9  xor     edi, edi
0x14007e6fb  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14007e700  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x14007e704  mov     [rsp+300h+nSavedDC], edi
0x14007e708  mov     rcx, r15; hFile
0x14007e70b  mov     qword ptr [rsp+300h+dwCreationDisposition], rdi; lpOverlapped
0x14007e710  lea     r8d, [rdi+24h]; nNumberOfBytesToRead
0x14007e714  call    cs:__imp_ReadFile
0x14007e71b  nop     dword ptr [rax+rax+00h]
0x14007e720  test    eax, eax
0x14007e722  jnz     short loc_14007E765
0x14007e724  call    cs:__imp_GetLastError
0x14007e72b  nop     dword ptr [rax+rax+00h]
0x14007e730  mov     ebx, eax
0x14007e732  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e739  lea     rax, WPP_GLOBAL_Control
0x14007e740  cmp     rcx, rax
0x14007e743  jz      loc_14007F4EC
0x14007e749  test    byte ptr [rcx+1Ch], 2
0x14007e74d  jz      loc_14007F4EC
0x14007e753  cmp     byte ptr [rcx+19h], 2
0x14007e757  jb      loc_14007F4EC
0x14007e75d  lea     edx, [rdi+0Dh]
0x14007e760  jmp     loc_14007F4D9
0x14007e765  cmp     [rsp+300h+NumberOfBytesRead], 24h ; '$'
0x14007e76a  jnz     loc_14007F4B5
0x14007e770  mov     r8d, 14h; Size
0x14007e776  lea     rdx, [rbp+200h+Buffer]; Buf2
0x14007e77a  lea     rcx, UNICODE_Signature; Buf1
0x14007e781  call    memcmp_0
0x14007e786  test    eax, eax
0x14007e788  jnz     loc_14007F4B5
0x14007e78e  mov     ecx, dword ptr [rbp+200h+Size+4]; Size
0x14007e791  call    cs:__imp_malloc
0x14007e798  nop     dword ptr [rax+rax+00h]
0x14007e79d  mov     [rbp+200h+Block], rax
0x14007e7a1  mov     rbx, rax
0x14007e7a4  test    rax, rax
0x14007e7a7  jnz     short loc_14007E7E7
0x14007e7a9  lea     r15d, [rax+8]
0x14007e7ad  mov     ebx, r15d
0x14007e7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e7b7  lea     rax, WPP_GLOBAL_Control
0x14007e7be  cmp     rcx, rax
0x14007e7c1  jz      loc_14007F4EC
0x14007e7c7  test    byte ptr [rcx+1Ch], 2
0x14007e7cb  jz      loc_14007F4EC
0x14007e7d1  cmp     byte ptr [rcx+19h], 2
0x14007e7d5  jb      loc_14007F4EC
0x14007e7db  lea     edx, [r15+7]
0x14007e7df  mov     r9d, r15d
0x14007e7e2  jmp     loc_14007F4DC
0x14007e7e7  mov     r8d, dword ptr [rbp+200h+Size+4]; nNumberOfBytesToRead
0x14007e7eb  lea     r9, [rsp+300h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14007e7f0  mov     rdx, rbx; lpBuffer
0x14007e7f3  mov     qword ptr [rsp+300h+dwCreationDisposition], rdi; lpOverlapped
0x14007e7f8  mov     rcx, r15; hFile
0x14007e7fb  call    cs:__imp_ReadFile
0x14007e802  nop     dword ptr [rax+rax+00h]
0x14007e807  test    eax, eax
0x14007e809  jz      loc_14007F472
0x14007e80f  mov     eax, [rsp+300h+NumberOfBytesRead]
0x14007e813  cmp     dword ptr [rbp+200h+Size+4], eax
0x14007e816  jnz     loc_14007F472
0x14007e81c  mov     [rsp+300h+hmf], rdi
0x14007e821  mov     r15d, 8
0x14007e827  mov     [rsp+300h+lpchText], rdi
0x14007e82c  test    r14, r14
0x14007e82f  jz      loc_14007ED29
0x14007e835  mov     rcx, rsi; lprect
0x14007e838  call    cs:__imp_CreateRectRgnIndirect
0x14007e83f  nop     dword ptr [rax+rax+00h]
0x14007e844  mov     [rsp+300h+ho], rax
0x14007e849  test    rax, rax
0x14007e84c  jnz     short loc_14007E8A3
0x14007e84e  call    cs:__imp_GetLastError
0x14007e855  nop     dword ptr [rax+rax+00h]
0x14007e85a  mov     ebx, eax
0x14007e85c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e863  lea     rax, WPP_GLOBAL_Control
0x14007e86a  cmp     rcx, rax
0x14007e86d  jz      loc_14007EAB2
0x14007e873  test    byte ptr [rcx+1Ch], 2
0x14007e877  jz      loc_14007EAB2
0x14007e87d  cmp     byte ptr [rcx+19h], 2
0x14007e881  jb      loc_14007EAB2
0x14007e887  lea     edx, [r15+9]
0x14007e88b  mov     r9d, ebx
0x14007e88e  mov     rcx, [rcx+10h]
0x14007e892  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e899  call    WPP_SF_d
0x14007e89e  jmp     loc_14007EAB2
0x14007e8a3  mov     rdx, rax; hrgn
0x14007e8a6  mov     rcx, r14; hdc
0x14007e8a9  call    cs:__imp_SelectClipRgn
0x14007e8b0  nop     dword ptr [rax+rax+00h]
0x14007e8b5  test    eax, eax
0x14007e8b7  jnz     short loc_14007E8EF
0x14007e8b9  lea     ebx, [rax+1Fh]
0x14007e8bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e8c3  lea     rax, WPP_GLOBAL_Control
0x14007e8ca  cmp     rcx, rax
0x14007e8cd  jz      loc_14007EAB2
0x14007e8d3  test    byte ptr [rcx+1Ch], 2
0x14007e8d7  jz      loc_14007EAB2
0x14007e8dd  cmp     byte ptr [rcx+19h], 2
0x14007e8e1  jb      loc_14007EAB2
0x14007e8e7  lea     edx, [rbx-0Dh]
0x14007e8ea  xor     r9d, r9d
0x14007e8ed  jmp     short loc_14007E88E
0x14007e8ef  mov     rcx, r14; hdc
0x14007e8f2  call    cs:__imp_SaveDC
0x14007e8f9  nop     dword ptr [rax+rax+00h]
0x14007e8fe  mov     [rsp+300h+nSavedDC], eax
0x14007e902  test    eax, eax
0x14007e904  jnz     short loc_14007E949
0x14007e906  call    cs:__imp_GetLastError
0x14007e90d  nop     dword ptr [rax+rax+00h]
0x14007e912  mov     ebx, eax
0x14007e914  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e91b  lea     rax, WPP_GLOBAL_Control
0x14007e922  cmp     rcx, rax
0x14007e925  jz      loc_14007EAB2
0x14007e92b  test    byte ptr [rcx+1Ch], 2
0x14007e92f  jz      loc_14007EAB2
0x14007e935  cmp     byte ptr [rcx+19h], 2
0x14007e939  jb      loc_14007EAB2
0x14007e93f  mov     edx, 13h
0x14007e944  jmp     loc_14007E88B
0x14007e949  mov     ecx, dword ptr [rbp+200h+Size+4]; nSize
0x14007e94c  test    ecx, ecx
0x14007e94e  jnz     short loc_14007E996
0x14007e950  lea     ebx, [rcx+12h]
0x14007e953  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e95a  lea     rax, WPP_GLOBAL_Control
0x14007e961  cmp     rcx, rax
0x14007e964  jz      loc_14007EAB2
0x14007e96a  test    byte ptr [rcx+1Ch], 2
0x14007e96e  jz      loc_14007EAB2
0x14007e974  cmp     byte ptr [rcx+19h], 2
0x14007e978  jb      loc_14007EAB2
0x14007e97e  mov     rcx, [rcx+10h]
0x14007e982  lea     edx, [rbx+2]
0x14007e985  lea     r8, WPP_7184d656e8e93f0831cdf6c26abbe201_Traceguids
0x14007e98c  call    WPP_SF_
0x14007e991  jmp     loc_14007EAB2
0x14007e996  mov     rdx, rbx; pb
0x14007e999  call    cs:__imp_SetEnhMetaFileBits
0x14007e9a0  nop     dword ptr [rax+rax+00h]
0x14007e9a5  mov     rbx, rax
0x14007e9a8  mov     [rsp+300h+hmf], rax
0x14007e9ad  xor     eax, eax
0x14007e9af  test    rbx, rbx
0x14007e9b2  jnz     short loc_14007E9F7
0x14007e9b4  call    cs:__imp_GetLastError
0x14007e9bb  nop     dword ptr [rax+rax+00h]
0x14007e9c0  mov     ebx, eax
0x14007e9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e9c9  lea     rax, WPP_GLOBAL_Control
0x14007e9d0  cmp     rcx, rax
0x14007e9d3  jz      loc_14007EAB2
0x14007e9d9  test    byte ptr [rcx+1Ch], 2
0x14007e9dd  jz      loc_14007EAB2
0x14007e9e3  cmp     byte ptr [rcx+19h], 2
0x14007e9e7  jb      loc_14007EAB2
0x14007e9ed  mov     edx, 15h
0x14007e9f2  jmp     loc_14007E88B
0x14007e9f7  lea     r8, [rbp+200h+EnhMetaHeader]; lpEnhMetaHeader
0x14007e9fe  mov     edx, 6Ch ; 'l'; nSize
0x14007ea03  mov     rcx, rbx; hemf
0x14007ea06  mov     r12, rax
0x14007ea09  call    cs:__imp_GetEnhMetaFileHeader
0x14007ea10  nop     dword ptr [rax+rax+00h]
0x14007ea15  test    eax, eax
0x14007ea17  jnz     loc_14007EAC7
0x14007ea1d  call    cs:__imp_GetLastError
0x14007ea24  nop     dword ptr [rax+rax+00h]
0x14007ea29  mov     ebx, eax
0x14007ea2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ea32  lea     rax, WPP_GLOBAL_Control
0x14007ea39  cmp     rcx, rax
0x14007ea3c  jz      short loc_14007EA62
0x14007ea3e  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
