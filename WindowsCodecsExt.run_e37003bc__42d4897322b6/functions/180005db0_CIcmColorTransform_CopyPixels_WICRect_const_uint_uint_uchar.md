# CIcmColorTransform::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x180005db0`
- end: `0x180006cbf`
- name: `?CopyPixels@CIcmColorTransform@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `3855`
- prototype: `__int64 __fastcall(CIcmColorTransform *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18002a7b0`
- `0x18002a7c0`

## callees

- `0x180004ea0`
- `0x180005db0`
- `0x180006cc8`
- `0x180006e70`
- `0x180007410`
- `0x180014ae0`
- `0x1800171c4`
- `0x180021a30`
- `0x180022348`
- `0x180022644`
- `0x180022650`
- `0x1800307e0`
- `0x180030e70`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006be7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006b8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006be7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800068fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800068fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006840`

## string_xrefs

- `0x1800068f2`: `mscms.dll`
- `0x180006c04`: `GetColorDirectoryW`
- `0x180006b63`: `OpenColorProfileW`
- `0x180006bbf`: `DeleteColorTransform`
- `0x180006b53`: `OpenColorProfileA`
- `0x180006b7a`: `CreateMultiProfileTransform`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CopyPixels(
        CIcmColorTransform *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  unsigned int v6; // r12d
  CIcmColorTransform *v7; // r13
  unsigned int v8; // esi
  char *v9; // rdi
  int v10; // eax
  const struct WICRect *v11; // rbx
  unsigned int v12; // r15d
  signed int v13; // r14d
  int v14; // edx
  __int64 v15; // r8
  unsigned int PixelFormatSize; // r9d
  unsigned __int64 v17; // r10
  int v18; // r12d
  unsigned __int64 v19; // r15
  unsigned int v20; // r15d
  unsigned int v21; // r15d
  unsigned __int64 v22; // r12
  int v23; // r12d
  unsigned int X; // eax
  signed int v25; // r12d
  int v26; // r15d
  unsigned int Y; // eax
  int v28; // r15d
  int v29; // eax
  __int64 v30; // rcx
  unsigned __int8 v31; // al
  unsigned int v32; // r12d
  unsigned int i; // eax
  int v34; // eax
  int v35; // ecx
  __int64 v36; // rbx
  unsigned int v37; // r14d
  _WORD *j; // rcx
  __int16 v39; // ax
  char *v40; // r15
  void *v41; // r12
  bool v42; // zf
  __int64 v43; // r13
  int v44; // ebx
  int v45; // r14d
  unsigned int v46; // eax
  __int64 v47; // r15
  int v48; // eax
  __int64 result; // rax
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  __int64 v55; // rax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  unsigned int v60; // r9d
  char *v61; // r12
  unsigned int v62; // ebx
  unsigned __int8 v63; // al
  unsigned int v64; // ebx
  signed int LastError; // eax
  HMODULE Library; // rax
  HMODULE v67; // rbx
  __int64 v68; // rbx
  unsigned __int64 v69; // r15
  unsigned __int64 v70; // rbx
  signed __int32 v71[6]; // [rsp+8h] [rbp-100h] BYREF
  void *v72; // [rsp+28h] [rbp-E0h]
  unsigned int v73; // [rsp+68h] [rbp-A0h]
  unsigned int v74; // [rsp+70h] [rbp-98h] BYREF
  int v75; // [rsp+74h] [rbp-94h]
  unsigned int v76; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v77; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v78; // [rsp+80h] [rbp-88h]
  unsigned int v79; // [rsp+84h] [rbp-84h] BYREF
  CIcmColorTransform *v80; // [rsp+88h] [rbp-80h] BYREF
  void *v81[2]; // [rsp+90h] [rbp-78h] BYREF
  void *v82; // [rsp+A0h] [rbp-68h]
  _QWORD v83[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v84; // [rsp+B8h] [rbp-50h]
  __int64 v85; // [rsp+C8h] [rbp-40h] BYREF
  int v86; // [rsp+D0h] [rbp-38h]
  int v87; // [rsp+D4h] [rbp-34h]
  unsigned int v88[4]; // [rsp+D8h] [rbp-30h] BYREF

  v6 = a4;
  v7 = this;
  v82 = a5;
  v77 = a4;
  v78 = a3;
  v80 = this;
  v74 = _mm_getcsr();
  v8 = v74;
  if ( (v74 & 0xFF80) != 0x1F80 )
  {
    v74 = 8064;
    _mm_setcsr(0x1F80u);
  }
  v9 = (char *)this - 56;
  v86 = *((_DWORD *)this + 34);
  v87 = *((_DWORD *)this + 35);
  v85 = 0;
  *(_OWORD *)v88 = 0;
  if ( *((_BYTE *)this - 8) )
    EnterCriticalSection_0((LPCRITICAL_SECTION)(v9 + 8));
  if ( !a5 || a2 && (!a2->Height || !a2->Width) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(-2147024809);
    v13 = -2147024809;
    goto LABEL_115;
  }
  if ( !*((_QWORD *)v7 + 7) )
  {
    v13 = -2003292412;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292412);
    goto LABEL_115;
  }
  v10 = ICMModule::s_icmState;
  if ( !ICMModule::s_icmState )
  {
    if ( !byte_180041DC0 || (EnterCriticalSection_0(&CriticalSection), (v10 = ICMModule::s_icmState) == 0) )
    {
      Library = LoadLibraryExW(L"mscms.dll", 0, 0);
      v67 = Library;
      if ( Library )
      {
        ICMModule::s_pfnOpenColorProfileA = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(Library, "OpenColorProfileA");
        ICMModule::s_pfnOpenColorProfileW = (void *(*)(struct tagPROFILE *, unsigned int, unsigned int, unsigned int))GetProcAddress(v67, "OpenColorProfileW");
        ICMModule::s_pfnCreateMultiProfileTransform = (void *(*)(void **, unsigned int, unsigned int *, unsigned int, unsigned int, unsigned int))GetProcAddress(v67, "CreateMultiProfileTransform");
        ICMModule::s_pfnTranslateBitmapBits = (int (*)(void *, void *, enum BMFORMAT, unsigned int, unsigned int, unsigned int, void *, enum BMFORMAT, unsigned int, int (*)(unsigned int, unsigned int, __int64), unsigned int))GetProcAddress(v67, "TranslateBitmapBits");
        ICMModule::s_pfnCloseColorProfile = (int (*)(void *))GetProcAddress(v67, "CloseColorProfile");
        ICMModule::s_pfnDeleteColorTransform = (int (*)(void *))GetProcAddress(v67, "DeleteColorTransform");
        ICMModule::s_pfnTranslateColors = (int (*)(void *, void *, unsigned int, unsigned int, void *, unsigned int))GetProcAddress(v67, "TranslateColors");
        ICMModule::s_pfnGetColorProfileHeader = (int (*)(void *, struct tagPROFILEHEADER *))GetProcAddress(
                                                                                              v67,
                                                                                              "GetColorProfileHeader");
        ICMModule::s_pfnGetColorDirectoryW = (int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(v67, "GetColorDirectoryW");
        ICMModule::s_pfnGetStandardColorSpaceProfileW = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *))GetProcAddress(v67, "GetStandardColorSpaceProfileW");
        ICMModule::s_pfnGetColorProfileFromHandle = (int (*)(void *, unsigned __int8 *, unsigned int *))GetProcAddress(v67, "GetColorProfileFromHandle");
        ICMModule::s_pfnGetColorProfileElement = (int (*)(void *, unsigned int, unsigned int, unsigned int *, void *, int *))GetProcAddress(v67, "GetColorProfileElement");
      }
      _InterlockedOr(v71, 0);
      if ( v67
        && ICMModule::s_pfnOpenColorProfileA
        && ICMModule::s_pfnOpenColorProfileW
        && ICMModule::s_pfnCloseColorProfile
        && ICMModule::s_pfnCreateMultiProfileTransform
        && ICMModule::s_pfnDeleteColorTransform
        && ICMModule::s_pfnTranslateBitmapBits
        && ICMModule::s_pfnTranslateColors
        && ICMModule::s_pfnGetColorProfileHeader
        && ICMModule::s_pfnGetColorDirectoryW
        && ICMModule::s_pfnGetStandardColorSpaceProfileW
        && ICMModule::s_pfnGetColorProfileFromHandle
        && ICMModule::s_pfnGetColorProfileElement )
      {
        v10 = 1;
      }
      else
      {
        v10 = 2;
      }
      ICMModule::s_icmState = v10;
    }
    if ( byte_180041DC0 )
    {
      LeaveCriticalSection_0(&CriticalSection);
      v10 = ICMModule::s_icmState;
    }
  }
  if ( v10 != 1 )
  {
    v13 = -2003292336;
    if ( !g_doStackCaptures )
      goto LABEL_115;
    v50 = -2003292336;
    goto LABEL_150;
  }
  v11 = (const struct WICRect *)&v85;
  if ( a2 )
    v11 = a2;
  if ( *((_DWORD *)v7 + 40) )
  {
    v48 = (*(__int64 (__fastcall **)(_QWORD, const struct WICRect *, _QWORD, _QWORD, unsigned __int8 *))(**((_QWORD **)v7 + 7) + 56LL))(
            *((_QWORD *)v7 + 7),
            v11,
            v78,
            v6,
            a5);
    v13 = v48;
    if ( v48 >= 0 || !g_doStackCaptures )
      goto LABEL_115;
    v50 = v48;
LABEL_150:
    DoStackCapture(v50);
    goto LABEL_115;
  }
  v12 = 0;
  v76 = 0;
  if ( v11 && v11->Height >= 0 && v11->Width >= 0 )
  {
    v13 = 0;
    PixelFormatSize = (unsigned __int8)GetPixelFormatSize(*((unsigned int *)v7 + 25));
    v18 = 0;
    if ( v14 )
    {
      v19 = v15 * PixelFormatSize;
      if ( v19 > v17 )
      {
        LODWORD(v19) = v17;
        v13 = -2147024362;
      }
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        goto LABEL_44;
      }
      if ( (int)v19 + 7 < (unsigned int)v19 )
      {
        v20 = v17;
        v13 = -2147024362;
      }
      else
      {
        v20 = v19 + 7;
        v13 = 0;
      }
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        goto LABEL_44;
      }
      v21 = v20 >> 3;
      if ( v78 < v21 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(-2147024809);
        v13 = -2147024809;
        goto LABEL_44;
      }
      v22 = (unsigned int)(v14 - 1) * (unsigned __int64)v78;
      if ( v22 > 0xFFFFFFFF )
      {
        LODWORD(v22) = -1;
        v13 = -2147024362;
      }
      else
      {
        v13 = 0;
      }
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
LABEL_179:
        v12 = v76;
LABEL_45:
        if ( v13 < 0 && g_doStackCaptures )
          DoStackCapture(v13);
        v6 = v77;
        v7 = v80;
        goto LABEL_49;
      }
      if ( (unsigned int)v22 + v21 < (unsigned int)v22 )
      {
        v18 = -1;
        v13 = -2147024362;
      }
      else
      {
        v18 = v21 + v22;
        v13 = 0;
      }
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        goto LABEL_179;
      }
    }
LABEL_44:
    v12 = v18;
    goto LABEL_45;
  }
  if ( g_doStackCaptures )
    DoStackCapture(-2147024809);
  v13 = -2147024809;
LABEL_49:
  if ( v13 < 0 )
  {
    if ( g_doStackCaptures )
      DoStackCapture(v13);
LABEL_55:
    if ( g_doStackCaptures )
      DoStackCapture(v13);
    goto LABEL_115;
  }
  if ( v12 > v6 )
  {
    v13 = -2003292276;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292276);
  }
  if ( v13 < 0 )
    goto LABEL_55;
  if ( *((_QWORD *)v7 + 9) )
  {
    v55 = *((_QWORD *)v7 + 9);
    v80 = 0;
    v56 = (*(__int64 (__fastcall **)(__int64, const struct WICRect *, __int64, CIcmColorTransform **))(*(_QWORD *)v55 + 72LL))(
            v55,
            v11,
            1,
            &v80);
    v13 = v56;
    if ( v56 < 0 && g_doStackCaptures )
      DoStackCapture(v56);
    v81[0] = 0;
    v79 = 0;
    if ( v13 >= 0 )
    {
      v57 = (*(__int64 (__fastcall **)(CIcmColorTransform *, unsigned int *, void **))(*(_QWORD *)v80 + 40LL))(
              v80,
              &v79,
              v81);
      v13 = v57;
      if ( v57 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v57);
      }
    }
    v77 = 0;
    v76 = 0;
    if ( v13 >= 0 )
    {
      v58 = (*(__int64 (__fastcall **)(CIcmColorTransform *, unsigned int *, unsigned int *))(*(_QWORD *)v80 + 24LL))(
              v80,
              &v77,
              &v76);
      v13 = v58;
      if ( v58 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v58);
      }
    }
    v74 = 0;
    if ( v13 < 0 )
      goto LABEL_176;
    v59 = (*(__int64 (__fastcall **)(CIcmColorTransform *, unsigned int *))(*(_QWORD *)v80 + 32LL))(v80, &v74);
    v13 = v59;
    if ( v59 < 0 && g_doStackCaptures )
      DoStackCapture(v59);
    if ( v13 < 0 )
      goto LABEL_176;
    v60 = v76;
    v61 = (char *)v82;
    if ( v76 > 1 )
    {
      v68 = v78;
      --v76;
      v13 = CIcmColorTransform::Transform((CIcmColorTransform *)((char *)v7 - 72), v81[0], v77, v60 - 1, v82, v74, v78);
      if ( v13 < 0 )
      {
LABEL_176:
        if ( v80 )
          (*(void (__fastcall **)(CIcmColorTransform *))(*(_QWORD *)v80 + 16LL))(v80);
        goto LABEL_115;
      }
      v69 = v76 * (unsigned __int64)v74;
      if ( v69 > 0xFFFFFFFF )
      {
        LODWORD(v69) = -1;
        v13 = -2147024362;
      }
      else
      {
        v13 = 0;
      }
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        goto LABEL_176;
      }
      v70 = v76 * v68;
      if ( v70 > 0xFFFFFFFF )
      {
        LODWORD(v70) = -1;
        v13 = -2147024362;
      }
      else
      {
        v13 = 0;
      }
      if ( v13 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v13);
        goto LABEL_176;
      }
      v81[0] = (char *)v81[0] + (unsigned int)v69;
      v61 += (unsigned int)v70;
    }
    v62 = v77;
    v63 = GetPixelFormatSize(*((unsigned int *)v7 + 23));
    if ( v63 && v62 <= 0x7FFFFFF8u / v63 )
    {
      v13 = 0;
      v64 = (((v63 * v62 + 7) >> 3) + 3) & 0xFFFFFFFC;
    }
    else
    {
      v64 = 0;
      if ( g_doStackCaptures )
        DoStackCapture(-2147024362);
      v13 = -2147024362;
    }
    if ( v13 >= 0 )
    {
      v13 = CIcmColorTransform::Transform((CIcmColorTransform *)((char *)v7 - 72), v81[0], v77, 1u, v61, v64, v78);
    }
    else if ( g_doStackCaptures )
    {
      DoStackCapture(v13);
    }
    goto LABEL_176;
  }
  if ( v11->X + v11->Width >= (int)v85 + v86 )
    v23 = v85 + v86;
  else
    v23 = v11->X + v11->Width;
  if ( v11->X <= (int)v85 )
    X = v85;
  else
    X = v11->X;
  v25 = v23 - X;
  v88[0] = X;
  v88[2] = v25;
  if ( v25 <= 0
    || (v11->Y + v11->Height >= HIDWORD(v85) + v87 ? (v26 = HIDWORD(v85) + v87) : (v26 = v11->Y + v11->Height),
        v11->Y <= SHIDWORD(v85) ? (Y = HIDWORD(v85)) : (Y = v11->Y),
        v28 = v26 - Y,
        v88[1] = Y,
        v77 = v28,
        v88[3] = v28,
        v28 <= 0) )
  {
    v29 = 0;
    v28 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    *(_OWORD *)v88 = 0;
    v77 = v28;
    v25 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
  }
  else
  {
    v29 = 1;
  }
  if ( v29 && v28 >= 1 && v25 >= 1 )
  {
    v30 = *((unsigned int *)v7 + 23);
    v88[3] = 1;
    v31 = GetPixelFormatSize(v30);
    if ( v31 && v25 <= 0x7FFFFFF8u / v31 )
    {
      v32 = ((((unsigned int)v31 * v25 + 7) >> 3) + 3) & 0xFFFFFFFC;
      v74 = v32;
      v13 = 0;
    }
    else
    {
      v32 = 0;
      v74 = 0;
      if ( g_doStackCaptures )
        DoStackCapture(-2147024362);
      v13 = -2147024362;
    }
    if ( v13 < 0 && g_doStackCaptures )
      DoStackCapture(v13);
    for ( i = 0; ; i = v76 + 1 )
    {
      v76 = i;
      if ( i >= v28 || v13 < 0 )
        goto LABEL_115;
      if ( !*((_QWORD *)v7 + 14) )
        goto LABEL_134;
      v34 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v7 + 7) + 56LL))(
              *((_QWORD *)v7 + 7),
              v88,
              v32,
              v32,
              *((_QWORD *)v7 + 14));
      v13 = v34;
      if ( v34 < 0 && g_doStackCaptures )
        DoStackCapture(v34);
      if ( v13 >= 0 )
        break;
LABEL_112:
      v82 = (char *)v82 + v78;
      ++v88[1];
    }
    v35 = *((_DWORD *)v7 + 23);
    v37 = v88[2];
    v83[0] = *((_QWORD *)v7 + 14);
    v36 = v83[0];
    v83[1] = v83[0];
    *(_OWORD *)v81 = 0;
    LODWORD(v81[1]) = v88[2];
    v84 = 0;
    if ( v35 == 22 )
      goto LABEL_88;
    v51 = v35 - 16;
    if ( !v51 )
      goto LABEL_188;
    v52 = v51 - 7;
    if ( !v52 )
    {
      AlphaDivide_64bppPRGBA((const struct PipelineParams *)v81, (const struct ScanOpParams *)v83);
LABEL_88:
      for ( j = (_WORD *)*((_QWORD *)v7 + 18); v37; --v37 )
      {
        v39 = *(_WORD *)(v36 + 4);
        v36 += 8;
        *j = v39;
        j += 3;
        *(j - 2) = *(_WORD *)(v36 - 6);
        *(j - 1) = *(_WORD *)(v36 - 8);
      }
      goto LABEL_90;
    }
    v53 = v52 - 46;
    if ( v53 )
    {
      v54 = v53 - 3;
      if ( !v54 )
      {
LABEL_143:
        if ( *((_QWORD *)v7 + 18) )
          v83[0] = *((_QWORD *)v7 + 18);
        Quantize_64bppRGBA_48bppRGB((const struct PipelineParams *)v81, (const struct ScanOpParams *)v83);
        goto LABEL_90;
      }
      if ( v54 == 1 )
      {
        AlphaDivide_64bppPRGBA((const struct PipelineParams *)v81, (const struct ScanOpParams *)v83);
        goto LABEL_143;
      }
    }
    else
    {
LABEL_188:
      AlphaDivide_32bppPBGRA((const struct PipelineParams *)v81, (const struct ScanOpParams *)v83);
    }
LABEL_90:
    v40 = (char *)v7 - 72;
    if ( *((_QWORD *)v7 + 19) )
      v41 = (void *)*((_QWORD *)v7 + 19);
    else
      v41 = v82;
    v42 = *((_QWORD *)v7 + 18) == 0;
    v79 = v88[2];
    if ( v42 )
      v43 = *((_QWORD *)v7 + 14);
    else
      v43 = *((_QWORD *)v7 + 18);
    v13 = -2147024809;
    v75 = _mm_getcsr();
    v44 = v75;
    if ( (v75 & 0xFF80) != 0x1F80 )
    {
      v75 = 8064;
      _mm_setcsr(0x1F80u);
    }
    if ( *((_DWORD *)v40 + 44) && v43 && v41 && v88[2] )
    {
      if ( *((_DWORD *)v40 + 42) == 8 || *((_DWORD *)v40 + 42) == 16 )
        memset_0(v41, 255, v78);
      v45 = 0;
      v75 = *((_DWORD *)v40 + 42);
      v46 = *((_DWORD *)v40 + 40);
      v47 = *((_QWORD *)v40 + 19);
      v73 = v46;
      if ( (unsigned int)ICMModule::EnsureLoaded() )
      {
        LODWORD(v72) = 1;
        v45 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, void *, unsigned int, void *, int, unsigned int, _QWORD, _DWORD))ICMModule::s_pfnTranslateBitmapBits)(
                v47,
                v43,
                v73,
                v79,
                v72,
                v74,
                v41,
                v75,
                v78,
                0,
                0);
      }
      if ( v45 )
      {
        v13 = 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    if ( (v44 & 0xFF80) != 0x1F80 )
    {
      v73 = v44 & 0xFFFFFFC0;
      _mm_setcsr(v44 & 0xFFFFFFC0);
    }
    if ( v13 < 0 && g_doStackCaptures )
      DoStackCapture(v13);
    v7 = v80;
    CIcmColorTransform::PostTranslationFormatConversion((CIcmColorTransform *)((char *)v80 - 72), v82, v88[2]);
    v32 = v74;
    v28 = v77;
    goto LABEL_112;
  }
LABEL_134:
  if ( g_doStackCaptures )
    DoStackCapture(-2147024809);
  v13 = -2147024809;
LABEL_115:
  if ( v13 < 0 && g_doStackCaptures )
    DoStackCapture(v13);
  if ( v9[48] )
    LeaveCriticalSection_0((LPCRITICAL_SECTION)(v9 + 8));
  result = (unsigned int)v13;
  if ( (v8 & 0xFF80) != 0x1F80 )
  {
    v73 = v8 & 0xFFFFFFC0;
    _mm_setcsr(v8 & 0xFFFFFFC0);
  }
  return result;
}

```

## disassembly

```asm
0x180005db0  mov     r11, rsp
0x180005db3  push    rbp
0x180005db4  push    rsi
0x180005db5  push    r14
0x180005db7  lea     rbp, [r11-38h]
0x180005dbb  sub     rsp, 120h
0x180005dc2  mov     rax, cs:__security_cookie
0x180005dc9  xor     rax, rsp
0x180005dcc  mov     [rbp+30h+var_50], rax
0x180005dd0  mov     [r11-28h], rdi
0x180005dd4  mov     r14, rdx
0x180005dd7  mov     [r11-30h], r12
0x180005ddb  mov     r12d, r9d
0x180005dde  mov     [r11-38h], r13
0x180005de2  mov     r13, rcx
0x180005de5  mov     [r11-40h], r15
0x180005de9  mov     r15, [rbp+30h+arg_20]
0x180005ded  mov     [rbp+30h+var_98], r15
0x180005df1  mov     [rsp+130h+var_BC], r9d
0x180005df6  mov     [rsp+130h+var_B8], r8d
0x180005dfb  mov     [rbp+30h+var_B0], rcx
0x180005dff  stmxcsr [rsp+130h+var_C8]
0x180005e04  mov     esi, [rsp+130h+var_C8]
0x180005e08  mov     eax, esi
0x180005e0a  and     eax, 0FF80h
0x180005e0f  cmp     eax, 1F80h
0x180005e14  jz      short loc_180005E23
0x180005e16  mov     [rsp+130h+var_C8], 1F80h
0x180005e1e  ldmxcsr [rsp+130h+var_C8]
0x180005e23  mov     eax, [rcx+88h]
0x180005e29  lea     rdi, [rcx-38h]
0x180005e2d  mov     [rbp+30h+var_68], eax
0x180005e30  xorps   xmm0, xmm0
0x180005e33  mov     eax, [rcx+8Ch]
0x180005e39  mov     [rbp+30h+var_64], eax
0x180005e3c  mov     [rbp+30h+var_70], 0
0x180005e44  movups  xmmword ptr [rbp+30h+var_60], xmm0
0x180005e48  cmp     byte ptr [rdi+30h], 0
0x180005e4c  jz      short loc_180005E57
0x180005e4e  lea     rcx, [rdi+8]; lpCriticalSection
0x180005e52  call    EnterCriticalSection_0
0x180005e57  test    r15, r15
0x180005e5a  jz      loc_180006ADF
0x180005e60  test    r14, r14
0x180005e63  jz      short loc_180005E7B
0x180005e65  cmp     dword ptr [r14+0Ch], 0
0x180005e6a  jz      loc_180006ADF
0x180005e70  cmp     dword ptr [r14+8], 0
0x180005e75  jz      loc_180006ADF
0x180005e7b  cmp     qword ptr [r13+38h], 0
0x180005e80  jz      loc_18000687F
0x180005e86  mov     eax, cs:?s_icmState@ICMModule@@0W4DllLoadState@@A; DllLoadState ICMModule::s_icmState
0x180005e8c  mov     [rsp+118h], rbx
0x180005e94  test    eax, eax
0x180005e96  jz      loc_1800068CC
0x180005e9c  cmp     eax, 1
0x180005e9f  jnz     loc_18000644B
0x180005ea5  test    r14, r14
0x180005ea8  lea     rbx, [rbp+30h+var_70]
0x180005eac  cmovnz  rbx, r14
0x180005eb0  cmp     dword ptr [r13+0A0h], 0
0x180005eb8  jnz     loc_180006396
0x180005ebe  xor     r15d, r15d
0x180005ec1  mov     r10d, 0FFFFFFFFh
0x180005ec7  mov     [rsp+130h+var_C0], r15d
0x180005ecc  test    rbx, rbx
0x180005ecf  jz      loc_180006597
0x180005ed5  cmp     [rbx+0Ch], r15d
0x180005ed9  jl      loc_180006597
0x180005edf  cmp     [rbx+8], r15d
0x180005ee3  jl      loc_180006597
0x180005ee9  mov     ecx, [r13+64h]
0x180005eed  mov     edx, [rbx+0Ch]
0x180005ef0  mov     r8d, [rbx+8]
0x180005ef4  call    ?GetPixelFormatSize@@YAEW4Enum@MilPixelFormat@@@Z; GetPixelFormatSize(MilPixelFormat::Enum)
0x180005ef9  xor     r14d, r14d
0x180005efc  movzx   r9d, al
0x180005f00  xor     r12d, r12d
0x180005f03  test    edx, edx
0x180005f05  jz      loc_180005FDF
0x180005f0b  mov     r15d, r9d
0x180005f0e  lea     r13d, [rdx-1]
0x180005f12  imul    r15, r8
0x180005f16  cmp     r15, r10
0x180005f19  jbe     short loc_180005F24
0x180005f1b  mov     r15d, r10d
0x180005f1e  mov     r14d, 80070216h
0x180005f24  test    r14d, r14d
0x180005f27  jns     short loc_180005F3F
0x180005f29  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180005f30  jnz     loc_1800065C9
0x180005f36  test    r14d, r14d
0x180005f39  js      loc_180005FDF
0x180005f3f  lea     eax, [r15+7]
0x180005f43  cmp     eax, r15d
0x180005f46  jb      loc_1800064A7
0x180005f4c  add     r15d, 7
0x180005f50  xor     r14d, r14d
0x180005f53  test    r14d, r14d
0x180005f56  jns     short loc_180005F6A
0x180005f58  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180005f5f  jnz     loc_1800065E9
0x180005f65  test    r14d, r14d
0x180005f68  js      short loc_180005FDF
0x180005f6a  mov     eax, [rsp+130h+var_B8]
0x180005f6e  shr     r15d, 3
0x180005f72  cmp     eax, r15d
0x180005f75  jb      loc_180006819
0x180005f7b  mov     r12d, eax
0x180005f7e  mov     ecx, 0FFFFFFFFh
0x180005f83  mov     eax, r13d
0x180005f86  imul    r12, rax
0x180005f8a  cmp     r12, rcx
0x180005f8d  ja      loc_1800064B5
0x180005f93  xor     r14d, r14d
0x180005f96  test    r14d, r14d
0x180005f99  jns     short loc_180005FB1
0x180005f9b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005fa2  jnz     loc_1800065F6
0x180005fa8  test    r14d, r14d
0x180005fab  js      loc_1800067EF
0x180005fb1  lea     eax, [r12+r15]
0x180005fb5  cmp     eax, r12d
0x180005fb8  jb      loc_1800064C3
0x180005fbe  add     r12d, r15d
0x180005fc1  xor     r14d, r14d
0x180005fc4  test    r14d, r14d
0x180005fc7  jns     short loc_180005FDF
0x180005fc9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005fd0  jnz     loc_180006608
0x180005fd6  test    r14d, r14d
0x180005fd9  js      loc_1800067EF
0x180005fdf  mov     r15d, r12d
0x180005fe2  test    r14d, r14d
0x180005fe5  jns     short loc_180005FF4
0x180005fe7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005fee  jnz     loc_1800065DC
0x180005ff4  mov     r12d, [rsp+130h+var_BC]
0x180005ff9  mov     r13, [rbp+30h+var_B0]
0x180005ffd  test    r14d, r14d
0x180006000  jns     short loc_180006014
0x180006002  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006009  jnz     loc_1800065AF
0x18000600f  test    r14d, r14d
0x180006012  js      short loc_180006022
0x180006014  cmp     r15d, r12d
0x180006017  ja      loc_18000689F
0x18000601d  test    r14d, r14d
0x180006020  jns     short loc_180006038
0x180006022  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006029  jnz     loc_1800065BC
0x18000602f  test    r14d, r14d
0x180006032  js      loc_1800063CD
0x180006038  cmp     qword ptr [r13+48h], 0
0x18000603d  jnz     loc_18000662E
0x180006043  mov     edx, [rbx+8]
0x180006046  mov     ecx, [rbp+30h+var_68]
0x180006049  add     edx, [rbx]
0x18000604b  add     ecx, dword ptr [rbp+30h+var_70]
0x18000604e  cmp     edx, ecx
0x180006050  jge     loc_18000647D
0x180006056  mov     r12d, [rbx+8]
0x18000605a  add     r12d, [rbx]
0x18000605d  mov     eax, dword ptr [rbp+30h+var_70]
0x180006060  cmp     [rbx], eax
0x180006062  jle     loc_18000648A
0x180006068  mov     eax, [rbx]
0x18000606a  sub     r12d, eax
0x18000606d  mov     [rbp+30h+var_60], eax
0x180006070  mov     [rbp+30h+var_60+8], r12d
0x180006074  test    r12d, r12d
0x180006077  jle     loc_1800064D1
0x18000607d  mov     edx, [rbx+0Ch]
0x180006080  mov     ecx, [rbp+30h+var_64]
0x180006083  add     edx, [rbx+4]
0x180006086  add     ecx, dword ptr [rbp+30h+var_70+4]
0x180006089  cmp     edx, ecx
0x18000608b  jge     loc_180006492
0x180006091  mov     r15d, [rbx+0Ch]
0x180006095  add     r15d, [rbx+4]
0x180006099  mov     eax, dword ptr [rbp+30h+var_70+4]
0x18000609c  cmp     [rbx+4], eax
0x18000609f  jle     loc_18000649F
0x1800060a5  mov     eax, [rbx+4]
0x1800060a8  sub     r15d, eax
0x1800060ab  mov     [rbp+30h+var_60+4], eax
0x1800060ae  mov     [rsp+130h+var_BC], r15d
0x1800060b3  mov     [rbp+30h+var_60+0Ch], r15d
0x1800060b7  test    r15d, r15d
0x1800060ba  jle     loc_1800064D1
0x1800060c0  mov     eax, 1
0x1800060c5  test    eax, eax
0x1800060c7  jz      loc_1800064FB
0x1800060cd  cmp     r15d, 1
0x1800060d1  jl      loc_1800064FB
0x1800060d7  cmp     r12d, 1
0x1800060db  jl      loc_1800064FB
0x1800060e1  mov     ecx, [r13+5Ch]
0x1800060e5  mov     [rbp+30h+var_60+0Ch], 1
0x1800060ec  call    ?GetPixelFormatSize@@YAEW4Enum@MilPixelFormat@@@Z; GetPixelFormatSize(MilPixelFormat::Enum)
0x1800060f1  movzx   r8d, al
0x1800060f5  test    al, al
0x1800060f7  jz      loc_1800067F9
0x1800060fd  xor     edx, edx
0x1800060ff  mov     eax, 7FFFFFF8h
0x180006104  div     r8d
0x180006107  cmp     r12d, eax
0x18000610a  ja      loc_1800067F9
0x180006110  imul    r12d, r8d
0x180006114  add     r12d, 7
0x180006118  shr     r12d, 3
0x18000611c  add     r12d, 3
0x180006120  and     r12d, 0FFFFFFFCh
0x180006124  mov     [rsp+130h+var_C8], r12d
0x180006129  xor     r14d, r14d
0x18000612c  test    r14d, r14d
0x18000612f  jns     short loc_18000613E
0x180006131  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006138  jnz     loc_180006615
0x18000613e  xor     eax, eax
0x180006140  mov     [rsp+130h+var_C0], eax
0x180006144  cmp     eax, r15d
0x180006147  jnb     loc_1800063CD
0x18000614d  test    r14d, r14d
0x180006150  js      loc_1800063CD
0x180006156  cmp     qword ptr [r13+70h], 0
0x18000615b  jz      loc_1800064FB
0x180006161  mov     rax, [r13+38h]
0x180006165  mov     r9d, r12d
0x180006168  mov     rcx, [r13+38h]
0x18000616c  mov     r8d, r12d
0x18000616f  mov     rdx, [rax]
0x180006172  mov     rax, [rdx+38h]
0x180006176  mov     rdx, [r13+70h]
0x18000617a  mov     [rsp+130h+var_110], rdx
0x18000617f  lea     rdx, [rbp+30h+var_60]
0x180006183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006188  mov     r14d, eax
0x18000618b  test    eax, eax
0x18000618d  jns     short loc_18000619C
0x18000618f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006196  jnz     loc_180006513
0x18000619c  test    r14d, r14d
0x18000619f  js      loc_180006380
0x1800061a5  mov     rax, [r13+70h]
0x1800061a9  xorps   xmm0, xmm0
0x1800061ac  mov     ecx, [r13+5Ch]
0x1800061b0  mov     rbx, rax
0x1800061b3  mov     r14d, [rbp+30h+var_60+8]
0x1800061b7  mov     [rbp+30h+var_90], rax
0x1800061bb  mov     [rbp+30h+var_88], rax
0x1800061bf  movups  xmmword ptr [rbp+30h+var_A8], xmm0
0x1800061c3  mov     dword ptr [rbp+30h+var_A8+8], r14d
0x1800061c7  movups  [rbp+30h+var_80], xmm0
0x1800061cb  cmp     ecx, 16h
0x1800061ce  jnz     loc_18000652D
0x1800061d4  mov     rcx, [r13+90h]
0x1800061db  test    r14d, r14d
0x1800061de  jz      short loc_180006214
0x1800061e0  mov     edx, 0FFFFFFFFh
0x1800061e5  nop     word ptr [rax+rax+00000000h]
0x1800061f0  movzx   eax, word ptr [rbx+4]
0x1800061f4  lea     rbx, [rbx+8]
0x1800061f8  mov     [rcx], ax
0x1800061fb  lea     rcx, [rcx+6]
0x1800061ff  movzx   eax, word ptr [rbx-6]
0x180006203  mov     [rcx-4], ax
0x180006207  movzx   eax, word ptr [rbx-8]
0x18000620b  mov     [rcx-2], ax
0x18000620f  add     r14d, edx
0x180006212  jnz     short loc_1800061F0
0x180006214  cmp     qword ptr [r13+98h], 0
0x18000621c  lea     r15, [r13-48h]
0x180006220  jnz     loc_180006873
0x180006226  mov     r12, [rbp+30h+var_98]
0x18000622a  cmp     qword ptr [r13+90h], 0
0x180006232  mov     ecx, [rbp+30h+var_60+8]
0x180006235  mov     [rsp+130h+var_B4], ecx
0x180006239  jnz     loc_1800067E3
0x18000623f  mov     r13, [r13+70h]
0x180006243  mov     r14d, 80070057h
0x180006249  stmxcsr [rsp+130h+var_C4]
0x18000624e  mov     ebx, [rsp+130h+var_C4]
0x180006252  mov     eax, ebx
0x180006254  and     eax, 0FF80h
0x180006259  cmp     eax, 1F80h
0x18000625e  jz      short loc_18000626D
0x180006260  mov     [rsp+130h+var_C4], 1F80h
0x180006268  ldmxcsr [rsp+130h+var_C4]
0x18000626d  cmp     dword ptr [r15+0B0h], 0
0x180006275  jz      loc_180006335
0x18000627b  test    r13, r13
0x18000627e  jz      loc_180006335
0x180006284  test    r12, r12
0x180006287  jz      loc_180006335
0x18000628d  test    ecx, ecx
0x18000628f  jz      loc_180006335
0x180006295  cmp     dword ptr [r15+0A8h], 8
0x18000629d  jz      loc_180006466
0x1800062a3  cmp     dword ptr [r15+0A8h], 10h
  ... truncated ...
```
