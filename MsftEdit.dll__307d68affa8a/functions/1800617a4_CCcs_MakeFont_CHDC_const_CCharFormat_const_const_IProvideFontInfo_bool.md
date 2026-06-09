# CCcs::MakeFont(CHDC const &,CCharFormat const * const,IProvideFontInfo *,bool)

- ea: `0x1800617a4`
- end: `0x1800623d4`
- name: `?MakeFont@CCcs@@AEAA_NAEBVCHDC@@QEBVCCharFormat@@PEAUIProvideFontInfo@@_N@Z`
- size: `3120`
- prototype: `bool __usercall@<al>(CCcs *__hidden this@<rcx>, const struct CHDC *@<rdx>, const struct CCharFormat *const@<r8>, struct IProvideFontInfo *@<r9>, bool)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x180061720`

## callees

- `0x1800228ac`
- `0x180028c3c`
- `0x180029234`
- `0x180050060`
- `0x180060670`
- `0x1800617a4`
- `0x1800623dc`
- `0x1800623f8`
- `0x180062904`
- `0x180062cec`
- `0x1800631a8`
- `0x180063368`
- `0x18006338c`
- `0x1800633dc`
- `0x18006933c`
- `0x18006e770`
- `0x1800714ac`
- `0x180071a84`
- `0x1800e6ae0`
- `0x1800ebd10`
- `0x1800f9968`
- `0x1800ff674`
- `0x18010a9ac`
- `0x18010ae08`
- `0x18013bad0`
- `0x18013c916`
- `0x1801464b0`
- `0x18017bd3c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061988`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061988`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180061ee1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800622b4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180061ee1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800622b4`

## pseudocode

```c
char __fastcall CCcs::MakeFont(
        CCcs *this,
        const struct CHDC *a2,
        const struct CCharFormat *const a3,
        struct IProvideFontInfo *a4,
        bool a5)
{
  unsigned __int8 v5; // bl
  __int64 v7; // rcx
  __int16 v9; // r15
  char v11; // al
  unsigned __int8 v12; // dl
  BYTE v13; // r10
  CFont *v14; // r13
  unsigned __int8 v15; // r9
  int v16; // eax
  unsigned __int16 v17; // ax
  unsigned int v18; // ecx
  BYTE v19; // al
  int v20; // eax
  BYTE v21; // al
  BYTE v22; // cl
  BYTE v23; // al
  const unsigned __int16 *FontName; // r8
  __int64 v25; // r9
  unsigned __int8 v26; // cl
  WCHAR *lfFaceName; // rsi
  int v28; // ebx
  bool v29; // zf
  BYTE lfOutPrecision; // al
  int v31; // ebx
  int v32; // eax
  unsigned __int8 v33; // al
  BYTE v34; // al
  struct IDWriteFont *v35; // rcx
  __int64 v36; // rax
  struct IDWriteFontFace *v37; // rbx
  struct IDWriteFont *DWrite; // rsi
  unsigned int v39; // eax
  unsigned __int8 v40; // al
  char v41; // dl
  __int64 v42; // rdx
  __int16 v43; // ax
  __int64 v44; // rax
  int v45; // eax
  __int128 v46; // xmm1
  struct IDWriteFont *v47; // r14
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  HFONT *v52; // rsi
  bool v53; // bl
  BOOL v55; // r11d
  __int16 v56; // ax
  unsigned __int16 v57; // dx
  WCHAR v58; // cx
  unsigned __int16 *v59; // r10
  WCHAR *v60; // r8
  HFONT v61; // rbx
  int v62; // eax
  BOOL v63; // r15d
  int v64; // eax
  BYTE v65; // dl
  int v66; // eax
  unsigned __int16 FontNameIndex; // ax
  char FontInfoFlags; // al
  int lfCharSet; // edx
  char v70; // bl
  signed __int16 v71; // r15
  struct IDWriteFontFace *SystemDWriteFontFace; // rax
  HDC ScreenDC; // rax
  void (__fastcall *v74)(struct ICustomTextOut *, __int64); // rbx
  __int64 v75; // rax
  int v76; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v77; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v78; // [rsp+50h] [rbp-B0h]
  char v79; // [rsp+51h] [rbp-AFh]
  __int16 v80; // [rsp+54h] [rbp-ACh]
  struct IDWriteFont *v81; // [rsp+58h] [rbp-A8h] BYREF
  int v82; // [rsp+60h] [rbp-A0h]
  struct tagLOGFONTW v83; // [rsp+70h] [rbp-90h] BYREF
  __int128 v84; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v85; // [rsp+E0h] [rbp-20h]
  _BYTE v86[128]; // [rsp+F0h] [rbp-10h] BYREF
  char v87; // [rsp+170h] [rbp+70h]
  unsigned __int16 v88[32]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 Src[32]; // [rsp+1C0h] [rbp+C0h] BYREF

  v5 = *((_BYTE *)a3 + 4);
  v7 = *(_QWORD *)a2;
  v9 = *((_WORD *)a3 + 3);
  v81 = a4;
  v78 = v5;
  v80 = v9;
  v79 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 80LL))(v7);
  memset_0(&v83, 0, sizeof(v83));
  CWidthCache::Free((CCcs *)((char *)this + 40));
  v11 = *((_BYTE *)this + 361) & 0xBF;
  *((_BYTE *)this + 352) = (*(_DWORD *)a3 >> 17) & 2;
  *((_BYTE *)this + 361) = v11 | *((_BYTE *)a3 + 2) & 0x40;
  v12 = CW32System::CharSetFromCharRep(v5);
  *((_BYTE *)this + 208) = v12;
  v14 = (CCcs *)((char *)this + 232);
  *((_BYTE *)this + 210) = v5;
  v15 = v13 - 63;
  *((_BYTE *)this + 350) = 0;
  if ( v5 == 98 )
    *((_BYTE *)this + 350) = v15;
  v16 = *((__int16 *)a3 + 4);
  *((_WORD *)this + 6) = v16;
  v83.lfHeight = -v16;
  v17 = *((_WORD *)a3 + 8);
  *((_WORD *)this + 102) = v17;
  if ( !*((_WORD *)a3 + 8) )
  {
    v17 = (v15 & (unsigned __int8)*(_DWORD *)a3) != 0 ? 700 : 400;
    *((_WORD *)this + 102) = v17;
  }
  v18 = *(_DWORD *)a3;
  *((_BYTE *)this + 361) &= 0xF3u;
  v83.lfWeight = v17;
  v83.lfItalic = v15 & (v18 >> 1);
  *((_BYTE *)this + 361) |= 4 * v83.lfItalic;
  if ( *((_BYTE *)this + 352) == 2 )
  {
    v83.lfCharSet = 0;
  }
  else
  {
    v19 = v12;
    if ( v12 == 0xFE )
      v19 = v13 - 63;
    v83.lfCharSet = v19;
  }
  v20 = *((unsigned __int8 *)this + 356);
  v83.lfOutPrecision = 0;
  if ( (_BYTE)v20 )
  {
    v83.lfEscapement = 900 * (4 - v20);
    v83.lfOrientation = v83.lfEscapement;
  }
  v21 = v13;
  if ( (*((_BYTE *)a3 + 52) & 0x20) != 0 )
    v21 = -64;
  v22 = *((_BYTE *)a3 + 5);
  v83.lfClipPrecision = v21;
  *((_BYTE *)this + 355) = v22;
  v23 = *((_BYTE *)a3 + 43);
  *((_BYTE *)this + 357) = v23;
  v83.lfQuality = v23;
  *((_BYTE *)this + 354) = *((_BYTE *)a3 + 61);
  v83.lfPitchAndFamily = v22;
  if ( (v22 & 0xF0u) >= 0x70 )
    v83.lfPitchAndFamily = v22 & 0xF | 0x10;
  *((_WORD *)this + 103) = CW32System::CodePageFromCharRep(v5);
  FontName = CFICache::GetFontName(v9);
  if ( *((char *)this + 361) >= 0 || v79 || FontName && *FontName == 64 )
  {
    v26 = 0;
  }
  else
  {
    v26 = 1;
    v83.lfFaceName[0] = 64;
  }
  lfFaceName = v83.lfFaceName;
  if ( v26 )
    lfFaceName = &v83.lfFaceName[1];
  if ( FontName )
  {
    v28 = v26 ^ 1;
    _o_wcsncpy_s(lfFaceName, (unsigned int)(v28 + 31), FontName, (unsigned int)(v28 + 30));
    lfFaceName[v28 + 30] = 0;
  }
  else
  {
    v83.lfFaceName[0] = 0;
  }
  v29 = (*((_BYTE *)this + 361) & 0x20) == 0;
  *(_QWORD *)&v84 = v81;
  BYTE8(v84) = v79;
  v85 = 0;
  if ( !v29
    || *((_BYTE *)this + 356)
    && (FontNameIndex = CFICache::GetFontNameIndex(v83.lfFaceName, 1),
        (CFICache::GetFontInfoFlags(FontNameIndex, &v84) & 8) != 0) )
  {
    v83.lfOutPrecision = 7;
    v29 = (CFICache::GetFontInfoFlags((unsigned __int16)v9, &v84) & 4) == 0;
    lfOutPrecision = v83.lfOutPrecision;
    if ( !v29 )
      lfOutPrecision = 9;
  }
  else
  {
    lfOutPrecision = v83.lfOutPrecision;
  }
  v31 = CW32System::_bCharSetSys;
  if ( v79 )
    lfOutPrecision = 7;
  v83.lfOutPrecision = lfOutPrecision;
  v32 = CW32System::_bCharSetSys - 177;
  LOBYTE(v32) = v83.lfCharSet;
  v82 = v32;
  if ( (unsigned int)CW32System::_bCharSetSys - 177 <= 1 && !v83.lfCharSet )
  {
    FontInfoFlags = CFICache::GetFontInfoFlags((unsigned __int16)v9, &v84);
    lfCharSet = v83.lfCharSet;
    if ( (FontInfoFlags & 0xA) == 8 )
      lfCharSet = v31;
    v82 = lfCharSet;
    v83.lfCharSet = lfCharSet;
  }
  if ( v79 )
  {
    v33 = *((_BYTE *)a3 + 63) & 0xF;
    *((_BYTE *)this + 354) = v33;
    v29 = (*(_BYTE *)a3 & 2) == 0;
    v83.lfWidth = v33;
    v34 = v29 ? (*((_WORD *)a3 + 26) & 0x200) != 0 : 2;
    *((_BYTE *)this + 361) &= 0xF3u;
    v35 = v81;
    v83.lfItalic = v34;
    *((_BYTE *)this + 361) |= 4 * v34;
    if ( v35 )
    {
      if ( *((_DWORD *)a3 + 7) )
      {
        v36 = (*(__int64 (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)v35 + 40LL))(v35);
        v37 = (struct IDWriteFontFace *)v36;
        if ( v36 )
        {
          DWrite = (struct IDWriteFont *)GetDWriteFont<IDWriteFontFace>(v36);
          CFont::SetDWriteFontFace((CCcs *)((char *)this + 232), v37, DWrite);
          if ( DWrite )
            (*(void (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)DWrite + 16LL))(DWrite);
          CWidthCache::Free((CCcs *)((char *)this + 40));
          *((_DWORD *)this + 50) = *((_DWORD *)a3 + 7);
          v39 = *(_DWORD *)a3;
          *((_BYTE *)this + 361) &= ~0x40u;
          *((_BYTE *)this + 352) = (v39 >> 17) & 2;
          v40 = CW32System::CharSetFromCharRep(v78);
          *((_BYTE *)this + 210) = v41;
          v42 = 0;
          *((_BYTE *)this + 208) = v40;
          *((_WORD *)this + 6) = *((_WORD *)a3 + 4);
          v43 = *((_WORD *)a3 + 8);
          *((_WORD *)this + 102) = v43;
          if ( !v43 )
            *((_WORD *)this + 102) = (*(_DWORD *)a3 & 1) != 0 ? 700 : 400;
          *((_BYTE *)this + 355) = *((_BYTE *)a3 + 5);
          *((_BYTE *)this + 357) = *((_BYTE *)a3 + 43);
          if ( a5 )
          {
            LODWORD(v85) = 0;
            v44 = *(_QWORD *)v37;
            v84 = 0;
            (*(void (__fastcall **)(struct IDWriteFontFace *, __int128 *))(v44 + 64))(v37, &v84);
            v45 = (__int16)v84;
            *((_WORD *)this + 6) = v84;
            v83.lfHeight = -v45;
          }
          (*(void (__fastcall **)(struct IDWriteFontFace *, __int64))(*(_QWORD *)v37 + 16LL))(v37, v42);
          v46 = *(_OWORD *)&v83.lfWeight;
          v47 = v81;
          *(_OWORD *)v14 = *(_OWORD *)&v83.lfHeight;
          v48 = *(_OWORD *)&v83.lfFaceName[2];
          *(_OWORD *)((char *)this + 248) = v46;
          v49 = *(_OWORD *)&v83.lfFaceName[10];
          *(_OWORD *)((char *)this + 264) = v48;
          v50 = *(_OWORD *)&v83.lfFaceName[18];
          *(_OWORD *)((char *)this + 280) = v49;
          v51 = *(_OWORD *)&v83.lfFaceName[24];
          *(_OWORD *)((char *)this + 296) = v50;
          *(_OWORD *)((char *)this + 308) = v51;
          CCcs::GetMetrics(this, a2, 0, 0, v47, v9);
          v52 = (HFONT *)((char *)this + 328);
          v53 = v79;
          goto LABEL_40;
        }
      }
    }
  }
  if ( (*(_BYTE *)a3 & 3) != 0 )
    v80 = -1;
  v52 = (HFONT *)((char *)this + 328);
  v88[0] = 0;
  if ( *((_QWORD *)this + 41) )
    CFont::Destroy((CCcs *)((char *)this + 232));
  v76 = (_DWORD)this + 360;
  LOBYTE(v25) = v78;
  (*(void (__fastcall **)(_QWORD, struct tagLOGFONTW *, char *, __int64))(**(_QWORD **)a2 + 128LL))(
    *(_QWORD *)a2,
    &v83,
    (char *)this + 232,
    v25);
  LOBYTE(v55) = 0;
  if ( *v52 )
  {
    CCcs::GetMetrics(this, a2, 32, v88, 0, 0xFFFF);
    LOBYTE(v55) = 0;
  }
  if ( !v79 && *((_BYTE *)a3 + 61) )
  {
    CFont::Destroy((CCcs *)((char *)this + 232));
    v83.lfWidth = CW32System::MulDivFunc(*((__int16 *)this + 16), *((unsigned __int8 *)a3 + 61), 100);
    CCcs::GetFontWithMetrics(this, a2, &v83, v78, v76, v88, 0);
    LOBYTE(v55) = 0;
  }
  if ( a5 )
  {
    CSelectFont::CSelectFont((CSelectFont *)v86, a2, (CCcs *)((char *)this + 232));
    v70 = v87;
    v71 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 328LL))(*(_QWORD *)a2);
    CSelectFont::~CSelectFont((CSelectFont *)v86);
    LOBYTE(v55) = 0;
    if ( v70 )
    {
      if ( *((_WORD *)this + 6) != v71 )
      {
        CFICache::SetFontEMSquare(*((_WORD *)a3 + 3), v71);
        CFont::Destroy((CCcs *)((char *)this + 232));
        v83.lfHeight = -v71;
        *((_WORD *)this + 6) = v71;
        CCcs::GetFontWithMetrics(this, a2, &v83, v78, v76, v88, 1);
        LOBYTE(v55) = 0;
      }
    }
  }
  v53 = v79;
  if ( !v79 )
  {
    v61 = 0;
    v60 = v83.lfFaceName;
    v59 = v88;
    do
    {
      v57 = *v59;
      if ( *v59 <= 0x5Au && *v60 >= 0x41u )
        v57 += 32;
      v58 = *v60;
      if ( (unsigned __int16)(*v60 - 65) <= 0x19u )
        v58 += 32;
      if ( v57 != v58 )
        break;
      ++v59;
      ++v60;
    }
    while ( v58 );
    v14 = (CCcs *)((char *)this + 232);
    if ( v57 == v58 )
      goto LABEL_62;
    v9 = -1;
    v80 = -1;
    if ( v83.lfCharSet != 2 )
    {
      if ( v83.lfCharSet == 1 )
      {
        if ( *((_BYTE *)this + 209) == 1 )
        {
          v83.lfCharSet = 2;
          CopyLFFontName(&v83, v88, 0);
          v61 = 0;
          if ( !*((_BYTE *)this + 348) )
            v61 = *v52;
          *v52 = 0;
          *((_QWORD *)this + 42) = 0;
          CCcs::GetFontWithMetrics(this, a2, &v83, 0xAu, v76, v88, 0);
          v62 = CW32System::wcsicmp(v88, v83.lfFaceName);
          LOBYTE(v55) = 0;
          v83.lfCharSet = v82;
          v63 = v62 == 0;
LABEL_76:
          if ( v61 )
          {
            if ( v63 )
            {
              DeleteObject(v61);
            }
            else
            {
              CFont::Destroy((CCcs *)((char *)this + 232));
              CFont::SetHFont((CCcs *)((char *)this + 232), v61);
              CCcs::GetMetrics(this, a2, 0, 0, 0, 0xFFFF);
            }
            LOBYTE(v55) = 0;
          }
LABEL_62:
          v9 = v80;
LABEL_63:
          v56 = *((_WORD *)a3 + 3);
          v47 = v81;
          CCcs::TryCreateFontWithCharsetMatching(this, a2, &v83, *((_BYTE *)this + 209), v55, v81, v56, v78, v77, v88);
          v53 = 0;
          goto LABEL_40;
        }
      }
      else if ( (unsigned __int8)(v83.lfCharSet + 79) <= 1u )
      {
        CFont::Destroy((CCcs *)((char *)this + 232));
        CopyLFFontName(&v83, v88, 0);
        CCcs::GetFontWithMetrics(this, a2, &v83, v78, v76, v88, 0);
        LOBYTE(v55) = 0;
        goto LABEL_63;
      }
      if ( *((_BYTE *)this + 353) == 2
        || !(unsigned int)CW32System::IsFECharSet(v83.lfCharSet)
        || CW32System::IsFELCID(CW32System::_syslcid) )
      {
        goto LABEL_63;
      }
      v63 = v55;
      CopyLFFontName(&v83, v88, 0);
      v61 = 0;
      if ( !*((_BYTE *)this + 348) )
        v61 = *v52;
      *v52 = 0;
      *((_QWORD *)this + 42) = 0;
      CCcs::GetFontWithMetrics(this, a2, &v83, v78, v76, v88, 0);
      v66 = CW32System::wcsicmp(v88, v83.lfFaceName);
      LOBYTE(v55) = 0;
      if ( !v66 )
        v63 = 1;
      goto LABEL_76;
    }
    v83.lfCharSet = 0;
    if ( !*((_BYTE *)this + 348) )
      v61 = *v52;
    *v52 = 0;
    *((_QWORD *)this + 42) = 0;
    CCcs::GetFontWithMetrics(this, a2, &v83, 0, v76, v88, 0);
    v64 = CW32System::wcsicmp(v88, v83.lfFaceName);
    v65 = v83.lfCharSet;
    LOBYTE(v55) = 0;
    v63 = 0;
    if ( v64 )
      v65 = v82;
    LOBYTE(v63) = v64 == 0;
    v83.lfCharSet = v65;
    goto LABEL_76;
  }
  v9 = v80;
  v47 = v81;
  if ( *((_BYTE *)this + 349) && *((_BYTE *)this + 209) != v83.lfCharSet )
    *((_BYTE *)this + 209) = v83.lfCharSet;
LABEL_40:
  if ( *v52 )
    goto LABEL_42;
  v9 = 59;
  if ( v53 )
  {
    v81 = 0;
    SystemDWriteFontFace = CW32System::GetSystemDWriteFontFace(v47, &v81);
    CFont::SetDWriteFontFace(v14, SystemDWriteFontFace, v81);
  }
  else
  {
    CFont::SetHFont(v14, CW32System::_hSystemFont);
  }
  if ( *v52 )
  {
    CCcs::GetMetrics(this, a2, 32, v88, 0, 0xFFFF);
    if ( *v52 )
    {
LABEL_42:
      if ( v9 < 0 || (*((_BYTE *)this + 361) & 0x40) != 0 )
      {
        if ( v53 )
          ScreenDC = 0;
        else
          ScreenDC = CW32System::GetScreenDC();
        CHDC::CHDC((CHDC *)&v84, v53, 0, 0, ScreenDC, 0);
        CSelectFont::CSelectFont((CSelectFont *)v86, (struct CHDC *)&v84, v14);
        if ( v87 )
        {
          if ( (*((_BYTE *)this + 361) & 0x40) != 0 && g_pcto )
          {
            v74 = *(void (__fastcall **)(struct ICustomTextOut *, __int64))(*(_QWORD *)g_pcto + 16LL);
            v75 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v84 + 48LL))(v84);
            v74(g_pcto, v75);
          }
          if ( v9 < 0 )
          {
            (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v84 + 160LL))(v84, 32, Src);
            v9 = CFICache::GetFontNameIndex(Src, 1);
          }
        }
        CSelectFont::~CSelectFont((CSelectFont *)v86);
        CHDC::~CHDC((CHDC *)&v84);
      }
    }
  }
  *((_WORD *)this + 106) = v9;
  return 1;
}

```

## disassembly

```asm
0x1800617a4  push    rbp
0x1800617a6  push    rbx
0x1800617a7  push    rsi
0x1800617a8  push    rdi
0x1800617a9  push    r12
0x1800617ab  push    r13
0x1800617ad  push    r14
0x1800617af  push    r15
0x1800617b1  lea     rbp, [rsp-118h]
0x1800617b9  sub     rsp, 218h
0x1800617c0  mov     rax, cs:__security_cookie
0x1800617c7  xor     rax, rsp
0x1800617ca  mov     [rbp+150h+var_50], rax
0x1800617d1  mov     bl, [r8+4]
0x1800617d5  mov     rdi, rcx
0x1800617d8  mov     rcx, [rdx]
0x1800617db  mov     r14, r8
0x1800617de  movzx   r15d, word ptr [r8+6]
0x1800617e3  mov     r12, rdx
0x1800617e6  mov     [rsp+250h+var_1F8], r9
0x1800617eb  mov     [rsp+250h+var_200], bl
0x1800617ef  mov     rax, [rcx]
0x1800617f2  mov     [rsp+250h+var_1FC], r15d
0x1800617f7  mov     rax, [rax+50h]
0x1800617fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061800  xor     edx, edx; Val
0x180061802  mov     [rsp+250h+var_1FF], al
0x180061806  lea     rcx, [rsp+250h+var_1E0]; void *
0x18006180b  mov     sil, al
0x18006180e  lea     r8d, [rdx+5Ch]; Size
0x180061812  call    memset_0
0x180061817  lea     rcx, [rdi+28h]; this
0x18006181b  call    ?Free@CWidthCache@@QEAAXXZ; CWidthCache::Free(void)
0x180061820  mov     ecx, [r14]
0x180061823  mov     r10d, 40h ; '@'
0x180061829  mov     al, [rdi+169h]
0x18006182f  shr     ecx, 11h
0x180061832  and     al, 0BFh
0x180061834  and     cl, 2
0x180061837  mov     [rdi+160h], cl
0x18006183d  mov     cl, [r14+2]
0x180061841  and     cl, r10b
0x180061844  or      cl, al
0x180061846  mov     [rdi+169h], cl
0x18006184c  mov     cl, bl; unsigned __int8
0x18006184e  call    ?CharSetFromCharRep@CW32System@@SAEE@Z; CW32System::CharSetFromCharRep(uchar)
0x180061853  xor     r8d, r8d
0x180061856  movzx   edx, al
0x180061859  mov     [rdi+0D0h], dl
0x18006185f  lea     r13, [rdi+0E8h]
0x180061866  mov     [rdi+0D2h], bl
0x18006186c  lea     r9d, [r10-3Fh]
0x180061870  mov     [r13+76h], r8b
0x180061874  cmp     bl, 62h ; 'b'
0x180061877  jz      loc_180061FF8
0x18006187d  movsx   eax, word ptr [r14+8]
0x180061882  mov     [rdi+0Ch], ax
0x180061886  neg     eax
0x180061888  mov     [rsp+250h+var_1E0.lfHeight], eax
0x18006188c  movzx   eax, word ptr [r14+10h]
0x180061891  mov     [rdi+0CCh], ax
0x180061898  cmp     [r14+10h], r8w
0x18006189d  jz      loc_180062004
0x1800618a3  mov     ecx, [r14]
0x1800618a6  and     byte ptr [rdi+169h], 0F3h
0x1800618ad  movzx   eax, ax
0x1800618b0  shr     ecx, 1
0x1800618b2  and     cl, r9b
0x1800618b5  mov     [rbp+150h+var_1E0.lfWeight], eax
0x1800618b8  mov     al, cl
0x1800618ba  mov     [rbp+150h+var_1E0.lfItalic], cl
0x1800618bd  shl     al, 2
0x1800618c0  or      [rdi+169h], al
0x1800618c6  cmp     byte ptr [rdi+160h], 2
0x1800618cd  jz      loc_180062023
0x1800618d3  cmp     dl, 0FEh
0x1800618d6  mov     eax, edx
0x1800618d8  cmovz   eax, r9d
0x1800618dc  mov     [rbp+150h+var_1E0.lfCharSet], al
0x1800618df  movzx   eax, byte ptr [rdi+164h]
0x1800618e6  mov     [rbp+150h+var_1E0.lfOutPrecision], r8b
0x1800618ea  test    al, al
0x1800618ec  jnz     loc_18006202C
0x1800618f2  test    byte ptr [r14+34h], 20h
0x1800618f7  mov     ecx, 0C0h
0x1800618fc  mov     eax, r10d
0x1800618ff  cmovnz  eax, ecx
0x180061902  mov     cl, [r14+5]
0x180061906  mov     [rbp+150h+var_1E0.lfClipPrecision], al
0x180061909  mov     [rdi+163h], cl
0x18006190f  mov     al, [r14+2Bh]
0x180061913  mov     [rdi+165h], al
0x180061919  mov     [rbp+150h+var_1E0.lfQuality], al
0x18006191c  mov     al, [r14+3Dh]
0x180061920  mov     [rdi+162h], al
0x180061926  mov     al, cl
0x180061928  and     al, 0F0h
0x18006192a  mov     [rbp+150h+var_1E0.lfPitchAndFamily], cl
0x18006192d  cmp     al, 70h ; 'p'
0x18006192f  jnb     loc_180062046
0x180061935  mov     cl, bl; unsigned __int8
0x180061937  call    ?CodePageFromCharRep@CW32System@@SAGE@Z; CW32System::CodePageFromCharRep(uchar)
0x18006193c  movzx   ecx, r15w; __int16
0x180061940  mov     [rdi+0CEh], ax
0x180061947  call    ?GetFontName@CFICache@@SAPEBGF@Z; CFICache::GetFontName(short)
0x18006194c  xor     ebx, ebx
0x18006194e  mov     r8, rax
0x180061951  cmp     [rdi+169h], bl
0x180061957  jl      loc_180062054
0x18006195d  mov     cl, bl
0x18006195f  test    cl, cl
0x180061961  lea     rsi, [rbp+150h+var_1E0.lfFaceName]
0x180061965  lea     rax, [rbp+150h+var_1E0.lfFaceName+2]
0x180061969  cmovnz  rsi, rax
0x18006196d  test    r8, r8
0x180061970  jz      loc_180061D34
0x180061976  movzx   ebx, cl
0x180061979  mov     rcx, rsi
0x18006197c  xor     ebx, 1
0x18006197f  lea     eax, [rbx+1Eh]
0x180061982  mov     r9d, eax
0x180061985  lea     edx, [rax+1]
0x180061988  call    cs:__imp__o_wcsncpy_s
0x18006198e  movsxd  rcx, ebx
0x180061991  xor     ebx, ebx
0x180061993  mov     [rsi+rcx*2+3Ch], bx
0x180061998  test    byte ptr [rdi+169h], 20h
0x18006199f  mov     rax, [rsp+250h+var_1F8]
0x1800619a4  mov     sil, [rsp+250h+var_1FF]
0x1800619a9  mov     qword ptr [rbp+150h+var_180], rax
0x1800619ad  mov     eax, 7
0x1800619b2  mov     byte ptr [rbp+150h+var_180+8], sil
0x1800619b6  mov     [rbp+150h+var_170], rbx
0x1800619ba  jnz     loc_1800620A3
0x1800619c0  cmp     [rdi+164h], bl
0x1800619c6  jnz     loc_18006207C
0x1800619cc  mov     al, [rbp+150h+var_1E0.lfOutPrecision]
0x1800619cf  movzx   ebx, cs:?_bCharSetSys@CW32System@@0EA; uchar CW32System::_bCharSetSys
0x1800619d6  test    sil, sil
0x1800619d9  movzx   eax, al
0x1800619dc  mov     ecx, 7
0x1800619e1  cmovnz  eax, ecx
0x1800619e4  mov     [rbp+150h+var_1E0.lfOutPrecision], al
0x1800619e7  lea     eax, [rbx-0B1h]
0x1800619ed  cmp     eax, 1
0x1800619f0  mov     al, [rbp+150h+var_1E0.lfCharSet]
0x1800619f3  mov     [rsp+250h+var_1F0], eax
0x1800619f7  jbe     loc_1800620C6
0x1800619fd  or      eax, 0FFFFFFFFh
0x180061a00  xor     ebx, ebx
0x180061a02  test    sil, sil
0x180061a05  jz      loc_180061C11
0x180061a0b  mov     al, [r14+3Fh]
0x180061a0f  and     al, 0Fh
0x180061a11  movzx   ecx, al
0x180061a14  mov     [rdi+162h], cl
0x180061a1a  test    byte ptr [r14], 2
0x180061a1e  mov     [rsp+250h+var_1E0.lfWidth], ecx
0x180061a22  jnz     loc_180061D3D
0x180061a28  movzx   eax, word ptr [r14+34h]
0x180061a2d  shr     ax, 9
0x180061a31  and     al, 1
0x180061a33  and     byte ptr [rdi+169h], 0F3h
0x180061a3a  mov     rcx, [rsp+250h+var_1F8]
0x180061a3f  mov     [rbp+150h+var_1E0.lfItalic], al
0x180061a42  shl     al, 2
0x180061a45  or      [rdi+169h], al
0x180061a4b  test    rcx, rcx
0x180061a4e  jz      loc_180062114
0x180061a54  mov     edx, [r14+1Ch]
0x180061a58  test    edx, edx
0x180061a5a  jz      loc_180062114
0x180061a60  mov     rax, [rcx]
0x180061a63  mov     rax, [rax+28h]
0x180061a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a6c  mov     rbx, rax
0x180061a6f  test    rax, rax
0x180061a72  jz      loc_180062112
0x180061a78  mov     rcx, rax
0x180061a7b  call    ??$GetDWriteFont@UIDWriteFontFace@@@@YAPEAUIDWriteFont@@PEAUIDWriteFontFace@@@Z; GetDWriteFont<IDWriteFontFace>(IDWriteFontFace *)
0x180061a80  mov     r8, rax; struct IDWriteFont *
0x180061a83  mov     rdx, rbx; struct IDWriteFontFace *
0x180061a86  mov     rcx, r13; this
0x180061a89  mov     rsi, rax
0x180061a8c  call    ?SetDWriteFontFace@CFont@@AEAAXPEAUIDWriteFontFace@@PEAUIDWriteFont@@@Z; CFont::SetDWriteFontFace(IDWriteFontFace *,IDWriteFont *)
0x180061a91  test    rsi, rsi
0x180061a94  jz      short loc_180061AA5
0x180061a96  mov     rdx, [rsi]
0x180061a99  mov     rcx, rsi
0x180061a9c  mov     rax, [rdx+10h]
0x180061aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061aa5  lea     rcx, [rdi+28h]; this
0x180061aa9  call    ?Free@CWidthCache@@QEAAXXZ; CWidthCache::Free(void)
0x180061aae  mov     eax, [r14+1Ch]
0x180061ab2  mov     dl, [rsp+250h+var_200]
0x180061ab6  mov     [rdi+0C8h], eax
0x180061abc  mov     cl, dl; unsigned __int8
0x180061abe  mov     eax, [r14]
0x180061ac1  and     byte ptr [rdi+169h], 0BFh
0x180061ac8  shr     eax, 11h
0x180061acb  and     al, 2
0x180061acd  mov     [rdi+160h], al
0x180061ad3  call    ?CharSetFromCharRep@CW32System@@SAEE@Z; CW32System::CharSetFromCharRep(uchar)
0x180061ad8  mov     [rdi+0D2h], dl
0x180061ade  xor     edx, edx
0x180061ae0  mov     [rdi+0D0h], al
0x180061ae6  movzx   eax, word ptr [r14+8]
0x180061aeb  mov     [rdi+0Ch], ax
0x180061aef  movzx   eax, word ptr [r14+10h]
0x180061af4  mov     [rdi+0CCh], ax
0x180061afb  test    ax, ax
0x180061afe  jz      loc_1800620F2
0x180061b04  mov     al, [r14+5]
0x180061b08  mov     [rdi+163h], al
0x180061b0e  mov     al, [r14+2Bh]
0x180061b12  mov     [rdi+165h], al
0x180061b18  cmp     [rbp+150h+arg_20], dl
0x180061b1e  jz      short loc_180061B4F
0x180061b20  xor     eax, eax
0x180061b22  lea     rdx, [rbp+150h+var_180]
0x180061b26  mov     dword ptr [rbp+150h+var_170], eax
0x180061b29  xorps   xmm0, xmm0
0x180061b2c  mov     rax, [rbx]
0x180061b2f  mov     rcx, rbx
0x180061b32  movups  [rbp+150h+var_180], xmm0
0x180061b36  mov     rax, [rax+40h]
0x180061b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b3f  movsx   eax, word ptr [rbp+150h+var_180]
0x180061b43  mov     ecx, eax
0x180061b45  mov     [rdi+0Ch], ax
0x180061b49  neg     ecx
0x180061b4b  mov     [rsp+250h+var_1E0.lfHeight], ecx
0x180061b4f  mov     rax, [rbx]
0x180061b52  mov     rcx, rbx
0x180061b55  mov     rax, [rax+10h]
0x180061b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b5e  movaps  xmm0, xmmword ptr [rsp+250h+var_1E0.lfHeight]
0x180061b63  xor     r9d, r9d; unsigned __int16 *
0x180061b66  movaps  xmm1, xmmword ptr [rbp+150h+var_1E0.lfWeight]
0x180061b6a  xor     r8d, r8d; int
0x180061b6d  mov     r14, [rsp+250h+var_1F8]
0x180061b72  mov     rdx, r12; struct CHDC *
0x180061b75  movups  xmmword ptr [r13+0], xmm0
0x180061b7a  mov     rcx, rdi; this
0x180061b7d  mov     word ptr [rsp+250h+var_228], r15w; __int16
0x180061b83  movaps  xmm0, xmmword ptr [rbp+150h+var_1E0.lfFaceName+4]
0x180061b87  movups  xmmword ptr [r13+10h], xmm1
0x180061b8c  mov     [rsp+250h+var_230], r14; struct IProvideFontInfo *
0x180061b91  movaps  xmm1, xmmword ptr [rbp+150h+var_1E0.lfFaceName+14h]
0x180061b95  movups  xmmword ptr [r13+20h], xmm0
0x180061b9a  movaps  xmm0, xmmword ptr [rbp+150h+var_1E0.lfFaceName+24h]
0x180061b9e  movups  xmmword ptr [r13+30h], xmm1
0x180061ba3  movups  xmm1, xmmword ptr [rbp+150h+var_1E0.lfFaceName+30h]
0x180061ba7  movups  xmmword ptr [r13+40h], xmm0
0x180061bac  movups  xmmword ptr [r13+4Ch], xmm1
0x180061bb1  call    ?GetMetrics@CCcs@@AEAA_NAEBVCHDC@@JPEAGPEAUIProvideFontInfo@@F@Z; CCcs::GetMetrics(CHDC const &,long,ushort *,IProvideFontInfo *,short)
0x180061bb6  lea     rsi, [rdi+148h]
0x180061bbd  mov     bl, [rsp+250h+var_1FF]
0x180061bc1  xor     r11d, r11d
0x180061bc4  cmp     [rsi], r11
0x180061bc7  jz      loc_1800622BF
0x180061bcd  test    r15w, r15w
0x180061bd1  js      loc_180062304
0x180061bd7  test    byte ptr [rdi+169h], 40h
0x180061bde  jnz     loc_180062304
0x180061be4  mov     [rdi+0D4h], r15w
0x180061bec  mov     al, 1
0x180061bee  mov     rcx, [rbp+150h+var_50]
0x180061bf5  xor     rcx, rsp; StackCookie
0x180061bf8  call    __security_check_cookie
0x180061bfd  add     rsp, 218h
0x180061c04  pop     r15
0x180061c06  pop     r14
0x180061c08  pop     r13
0x180061c0a  pop     r12
0x180061c0c  pop     rdi
0x180061c0d  pop     rsi
0x180061c0e  pop     rbx
0x180061c0f  pop     rbp
0x180061c10  retn
0x180061c11  test    byte ptr [r14], 3
0x180061c15  jnz     loc_18006211C
0x180061c1b  lea     rsi, [rdi+148h]
0x180061c22  mov     [rbp+150h+var_D0], bx
0x180061c29  cmp     [rsi], rbx
0x180061c2c  jnz     loc_180062125
0x180061c32  mov     rcx, [r12]
0x180061c36  lea     rdx, [rdi+168h]
0x180061c3d  mov     bl, [rsp+250h+var_200]
0x180061c41  mov     r8, r13
0x180061c44  mov     [rsp+250h+var_230], rdx; int
0x180061c49  mov     r9b, bl
0x180061c4c  lea     rdx, [rsp+250h+var_1E0]
0x180061c51  mov     rax, [rcx]
0x180061c54  mov     rax, [rax+80h]
0x180061c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c60  xor     r11d, r11d
0x180061c63  cmp     [rsi], r11
0x180061c66  jnz     short loc_180061CB9
0x180061c68  cmp     [rsp+250h+var_1FF], r11b
  ... truncated ...
```
