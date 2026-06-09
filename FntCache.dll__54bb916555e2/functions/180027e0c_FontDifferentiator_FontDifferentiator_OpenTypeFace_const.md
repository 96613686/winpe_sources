# FontDifferentiator::FontDifferentiator(OpenTypeFace const &)

- ea: `0x180027e0c`
- end: `0x180028c3d`
- name: `??0FontDifferentiator@@QEAA@AEBVOpenTypeFace@@@Z`
- size: `3633`
- prototype: `FontDifferentiator *(FontDifferentiator *__hidden this, const struct OpenTypeFace *)`
- caller_count: `2`
- callee_count: `40`
- tags: `broker_com_uri`

## callers

- `0x18001f934`
- `0x1800268c0`

## callees

- `0x180004810`
- `0x1800066a8`
- `0x180006ca0`
- `0x1800073a8`
- `0x180008554`
- `0x180009ccc`
- `0x18000aca0`
- `0x18001c8d4`
- `0x1800201d8`
- `0x180024db0`
- `0x180025d84`
- `0x180026860`
- `0x180027cb0`
- `0x180027e0c`
- `0x180028c50`
- `0x180028c84`
- `0x180028f48`
- `0x180029670`
- `0x180029e48`
- `0x18002a1a8`
- `0x18004d664`
- `0x1800723fc`
- `0x180073598`
- `0x180073904`
- `0x180073b40`
- `0x180073e14`
- `0x18007b9c4`
- `0x18007c62c`
- `0x18007dc80`
- `0x18007e24c`
- `0x180088914`
- `0x18008a77c`
- `0x18008cc98`
- `0x18008ce68`
- `0x18008cfac`
- `0x18008e0ec`
- `0x1800900e8`
- `0x18009c0e0`
- `0x18009d96c`
- `0x1800aa650`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180028bd0`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180028bd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
FontDifferentiator *__fastcall FontDifferentiator::FontDifferentiator(
        FontDifferentiator *this,
        const struct OpenTypeFace *a2)
{
  struct DWrite::RefString::Data *v2; // rsi
  __int64 v4; // rax
  unsigned __int16 v5; // cx
  char v6; // al
  void **v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r9
  _OWORD *v10; // r12
  __int128 *v11; // r15
  __int128 *v12; // r14
  __int128 *v13; // r13
  unsigned __int16 v14; // dx
  unsigned int CanonicalNamesAndLanguage; // eax
  const char *v16; // rdx
  unsigned int v17; // ecx
  char v18; // r8
  __int64 v19; // rsi
  unsigned __int64 v20; // rdx
  bool v21; // r15
  struct DWrite::RefString::Data **v22; // rbx
  __int16 v23; // ax
  struct DWrite::RefString::Data **v24; // rbx
  unsigned int v25; // r13d
  __int16 v26; // ax
  __int64 v27; // rax
  volatile signed __int32 **v28; // rbx
  const char *v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rsi
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // r11
  __int64 v34; // r14
  unsigned int v35; // ecx
  __int64 v36; // r12
  _BYTE *v37; // rsi
  __int128 v38; // xmm6
  unsigned __int16 ResolvedWeight; // r9
  unsigned int v40; // ecx
  unsigned int v41; // edx
  unsigned __int8 v42; // dl
  __int64 v43; // rdx
  struct DWrite::RefString::Data *v44; // rcx
  size_t v45; // r8
  __int64 i; // rax
  __int64 *v47; // rbx
  __int128 *v48; // rsi
  __int64 *v49; // rcx
  __int128 *v50; // r14
  double v51; // xmm6_8
  struct DWrite::RefString::Data *v52; // r10
  __int64 v54; // rdx
  size_t v55; // r8
  bool v56; // cc
  unsigned __int64 v57; // rsi
  unsigned __int64 v58; // rbx
  __int64 v59; // r15
  const WCHAR *v60; // rcx
  signed int v61; // eax
  signed int v62; // r12d
  char v63; // [rsp+58h] [rbp-B0h]
  _BYTE v64[7]; // [rsp+59h] [rbp-AFh] BYREF
  struct DWrite::RefString::Data *v65[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct DWrite::RefString::Data *v66[2]; // [rsp+78h] [rbp-90h] BYREF
  struct DWrite::RefString::Data *v67; // [rsp+88h] [rbp-80h] BYREF
  int v68; // [rsp+90h] [rbp-78h]
  int v69; // [rsp+94h] [rbp-74h]
  struct DWrite::RefString::Data *v70; // [rsp+98h] [rbp-70h] BYREF
  struct DWrite::RefString::Data *v71; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v72; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-50h]
  __int128 v74; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v75; // [rsp+D0h] [rbp-38h]
  struct DWrite::RefString::Data *v76[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v77; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v78; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v79; // [rsp+100h] [rbp-8h]
  __int64 v80; // [rsp+108h] [rbp+0h]
  __int128 v81; // [rsp+120h] [rbp+18h] BYREF
  __int64 v82; // [rsp+130h] [rbp+28h]
  __int128 v83; // [rsp+138h] [rbp+30h] BYREF
  __int64 v84; // [rsp+148h] [rbp+40h]
  __int128 v85; // [rsp+150h] [rbp+48h] BYREF
  __int64 v86; // [rsp+160h] [rbp+58h]
  __int128 v87; // [rsp+168h] [rbp+60h] BYREF
  __int64 v88; // [rsp+178h] [rbp+70h]
  __int128 v89; // [rsp+188h] [rbp+80h] BYREF
  __int128 v90; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v91[80]; // [rsp+1A8h] [rbp+A0h] BYREF
  FontDifferentiator *v92; // [rsp+1F8h] [rbp+F0h]
  __int128 v93; // [rsp+208h] [rbp+100h] BYREF
  _OWORD v94[2]; // [rsp+218h] [rbp+110h] BYREF

  v2 = a2;
  v67 = a2;
  v92 = this;
  *(_BYTE *)this = 0;
  v4 = *((_QWORD *)a2 + 5);
  if ( !v4 || (v5 = _byteswap_ushort(*(_WORD *)(v4 + 62)), v6 = 1, (v5 & 0x100) == 0) )
    v6 = 0;
  *((_BYTE *)this + 1) = v6;
  *((_WORD *)this + 8) = GetFontWeightFromFace(a2);
  *((_BYTE *)this + 18) = GetFontStretchFromFace(v2);
  *((_BYTE *)this + 19) = GetFontStyleFromFace(v2);
  *((_QWORD *)this + 3) = &DWrite::RefString::empty_;
  *((_QWORD *)this + 4) = &DWrite::RefString::empty_;
  v7 = (void **)((char *)this + 40);
  GenericLanguageTag<std::wstring>::GenericLanguageTag<std::wstring>((char *)this + 40);
  *((_QWORD *)this + 9) = v8;
  *((_WORD *)this + 40) = v9;
  *((_QWORD *)this + 11) = v8;
  *((_WORD *)this + 48) = v9;
  *((_QWORD *)this + 13) = v8;
  *((_QWORD *)this + 14) = v9;
  *((_DWORD *)this + 30) = v9;
  *((_BYTE *)this + 128) = v9;
  *((_QWORD *)this + 17) = v9;
  *((_DWORD *)this + 36) = v9;
  *((_WORD *)this + 76) = v9;
  *((_QWORD *)this + 20) = v9;
  *((_DWORD *)this + 42) = v9;
  *((_BYTE *)this + 176) = v9;
  *((_BYTE *)this + 177) = *((_BYTE *)this + 19);
  *((_WORD *)this + 89) = *((_WORD *)this + 8);
  *((_BYTE *)this + 180) = *((_BYTE *)this + 18);
  v10 = (_OWORD *)((char *)this + 184);
  FontNameList::FontNameList((FontDifferentiator *)((char *)this + 184));
  v11 = (__int128 *)((char *)this + 208);
  FontNameList::FontNameList((FontDifferentiator *)((char *)this + 208));
  v12 = (__int128 *)((char *)this + 232);
  FontNameList::FontNameList((FontDifferentiator *)((char *)this + 232));
  v13 = (__int128 *)((char *)this + 256);
  FontNameList::FontNameList((FontDifferentiator *)((char *)this + 256));
  OpenTypeNameTable::OpenTypeNameTable((OpenTypeNameTable *)v91, v2);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v74);
  FontNameList::AppendItems((FontNameList *)&v74, (const struct OpenTypeNameTable *)v91, 1);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v72);
  FontNameList::AppendItems((FontNameList *)&v72, (const struct OpenTypeNameTable *)v91, 2);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v81);
  FontNameList::AppendItems((FontNameList *)&v81, (const struct OpenTypeNameTable *)v91, 21);
  if ( (__int128 *)((char *)this + 184) != &v81 )
  {
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy((char *)this + 184);
    *v10 = v81;
    *((_QWORD *)this + 25) = v82;
    v81 = 0;
    v82 = 0;
  }
  FontNameList::~FontNameList((FontNameList *)&v81);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v83);
  FontNameList::AppendItems((FontNameList *)&v83, (const struct OpenTypeNameTable *)v91, 22);
  if ( v11 != &v83 )
  {
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy((char *)this + 208);
    *v11 = v83;
    *((_QWORD *)this + 28) = v84;
    v83 = 0;
    v84 = 0;
  }
  FontNameList::~FontNameList((FontNameList *)&v83);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v85);
  FontNameList::AppendItems((FontNameList *)&v85, (const struct OpenTypeNameTable *)v91, 16);
  if ( v12 != &v85 )
  {
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy((char *)this + 232);
    *v12 = v85;
    *((_QWORD *)this + 31) = v86;
    v85 = 0;
    v86 = 0;
  }
  FontNameList::~FontNameList((FontNameList *)&v85);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v87);
  FontNameList::AppendItems((FontNameList *)&v87, (const struct OpenTypeNameTable *)v91, 17);
  if ( v13 != &v87 )
  {
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy((char *)this + 256);
    *v13 = v87;
    *((_QWORD *)this + 34) = v88;
    v87 = 0;
    v88 = 0;
  }
  FontNameList::~FontNameList((FontNameList *)&v87);
  CanonicalNamesAndLanguage = TryGetCanonicalNamesAndLanguage(
                                (const struct OpenTypeNameTable *)v91,
                                v14,
                                (FontDifferentiator *)((char *)this + 24),
                                (FontDifferentiator *)((char *)this + 32));
  v17 = CanonicalNamesAndLanguage;
  LODWORD(v65[0]) = CanonicalNamesAndLanguage;
  v18 = 0;
  if ( CanonicalNamesAndLanguage )
  {
    v19 = GenericLanguageTag<std::wstring>::GenericLanguageTag<std::wstring>(v94, CanonicalNamesAndLanguage, 0);
    if ( v7 != (void **)v19 )
    {
      v20 = *((_QWORD *)this + 8);
      if ( v20 > 7 )
        std::_Deallocate<16>(*v7, 2 * v20 + 2);
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 8) = 7;
      *(_WORD *)v7 = 0;
      *(_OWORD *)v7 = *(_OWORD *)v19;
      *(_OWORD *)((char *)this + 56) = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
    }
    std::wstring::_Tidy_deallocate(v94);
    v2 = v67;
    v17 = (unsigned int)v65[0];
    v18 = 0;
  }
  if ( !*((_DWORD *)v2 + 109) || (LOBYTE(v16) = 1, !*((_DWORD *)v2 + 110)) )
    LOBYTE(v16) = 0;
  if ( *(_QWORD *)v12 != *((_QWORD *)this + 30) || *(_QWORD *)v13 != *((_QWORD *)this + 33) )
    v18 = 1;
  v63 = v18;
  v21 = *(_QWORD *)v10 != *((_QWORD *)this + 24) && *(_QWORD *)v11 != *((_QWORD *)this + 27);
  if ( v18 && v21 || !v17 || (_BYTE)v16 || *((_BYTE *)this + 1) )
  {
    v25 = (unsigned int)v65[0];
    goto LABEL_60;
  }
  v22 = (struct DWrite::RefString::Data **)((char *)this + 72);
  if ( (unsigned __int8)TryGetName(v91, 16, v17, (char *)this + 72) )
  {
    v23 = 16;
  }
  else
  {
    _InterlockedIncrement(*((volatile signed __int32 **)this + 3));
    DWrite::RefString::DecrementRef(*v22);
    *v22 = (struct DWrite::RefString::Data *)*((_QWORD *)this + 3);
    v23 = 1;
  }
  *((_WORD *)this + 40) = v23;
  v24 = (struct DWrite::RefString::Data **)((char *)this + 88);
  v25 = (unsigned int)v65[0];
  if ( (unsigned __int8)TryGetName(v91, 17, LODWORD(v65[0]), (char *)this + 88) )
  {
    v26 = 17;
  }
  else
  {
    _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
    DWrite::RefString::DecrementRef(*v24);
    *v24 = (struct DWrite::RefString::Data *)*((_QWORD *)this + 4);
    v26 = 2;
  }
  *((_WORD *)this + 48) = v26;
  Trim(&v70, (char *)this + 72);
  Trim(v76, (char *)this + 88);
  v65[0] = 0;
  LODWORD(v65[1]) = 0;
  v27 = RemoveRegularFromFaceName(v66, v76, v65);
  v28 = (volatile signed __int32 **)CombineFamilyAndFaceName(&v67, &v70, v27);
  _InterlockedIncrement(*v28);
  DWrite::RefString::DecrementRef(*((struct DWrite::RefString::Data **)this + 13));
  *((_QWORD *)this + 13) = *v28;
  DWrite::RefString::DecrementRef(v67);
  DWrite::RefString::DecrementRef(v66[0]);
  FontDifferentiatorTokens::FontDifferentiatorTokens(
    (FontDifferentiatorTokens *)&v78,
    (FontDifferentiator *)((char *)this + 104));
  v31 = v79;
  v32 = 0xAAAAAAAAAAAAAAABuLL * ((v80 - v79) >> 2);
  if ( (unsigned int)v32 <= 1 )
  {
LABEL_41:
    v66[0] = 0;
    LODWORD(v66[1]) = 0;
    goto LABEL_42;
  }
  v33 = (unsigned int)v32;
  while ( 1 )
  {
    if ( v33 <= 1 )
      goto LABEL_41;
    if ( --v33 >= 0xAAAAAAAAAAAAAAABuLL * ((v80 - v31) >> 2) )
    {
      FailAssert(0x2Du, v29);
      goto LABEL_120;
    }
    v34 = 3 * v33;
    if ( !*(_BYTE *)(v31 + 12 * v33 + 8) )
    {
      v35 = *(_DWORD *)(v31 + 12 * v33 + 4);
      if ( *(_DWORD *)(v31 + 12 * v33) > v35 || (v29 = (const char *)v78, v35 > *(_DWORD *)(v78 + 4)) )
      {
        FailAssert(0x4Bu, v29);
        __debugbreak();
      }
      v36 = v78 + 8 + 2LL * *(unsigned int *)(v31 + 12 * v33);
      v67 = (struct DWrite::RefString::Data *)(v35 - *(_DWORD *)(v31 + 12 * v33));
      ParseFontStyleName(v64, v36, v67);
      if ( v64[0] )
        break;
    }
  }
  *((_BYTE *)this + 128) = v64[0];
  if ( v33 >= v32 )
  {
    FailAssert(0x33u, v29);
    __debugbreak();
  }
  *(_BYTE *)(v31 + 4 * v34 + 8) = 1;
  v66[0] = (struct DWrite::RefString::Data *)v36;
  v66[1] = (struct DWrite::RefString::Data *)__PAIR64__(HIDWORD(v94[0]), (unsigned int)v67);
LABEL_42:
  *((_OWORD *)this + 7) = *(_OWORD *)v66;
  v37 = (char *)this + 176;
  *((_OWORD *)this + 10) = *(_OWORD *)ExtractFontStretch(v94, &v78, v30, (char *)this + 176);
  *(_OWORD *)((char *)this + 136) = *(_OWORD *)ExtractFontWeight(v94, &v78, 1, (char *)this + 152);
  if ( !*((_WORD *)this + 76)
    && *((_WORD *)this + 40) == 16
    && *((_WORD *)this + 48) == 17
    && (unsigned __int8)DWrite::operator==((char *)this + 104, (char *)this + 24) )
  {
    *(_OWORD *)((char *)this + 136) = *(_OWORD *)ExtractAbbreviatedFontWeight(
                                                   v94,
                                                   *((unsigned __int16 *)this + 8),
                                                   &v78,
                                                   (char *)this + 152);
  }
  v38 = *(_OWORD *)v65;
  if ( !v21 )
  {
    ResolvedWeight = GetResolvedWeight(*((unsigned __int16 *)this + 8), *((unsigned __int16 *)this + 76));
    *((_WORD *)this + 89) = ResolvedWeight;
    v40 = (unsigned __int8)*v37;
    v41 = *((unsigned __int8 *)this + 18);
    if ( !*v37 )
      goto LABEL_45;
    v56 = v41 <= 5;
    if ( v41 >= 5 )
    {
LABEL_102:
      if ( !v56 && v40 > 5 )
        goto LABEL_45;
    }
    else
    {
      if ( v40 >= 5 )
      {
        v56 = v41 <= 5;
        goto LABEL_102;
      }
LABEL_45:
      LOBYTE(v40) = *((_BYTE *)this + 18);
    }
    *((_BYTE *)this + 180) = v40;
    v42 = *((_BYTE *)this + 128);
    if ( !v42 )
      v42 = *((_BYTE *)this + 19);
    *((_BYTE *)this + 177) = v42;
    ExtractFaceNumber(&v70, &v78, v42, ResolvedWeight, (unsigned __int8)v40);
    FontDifferentiatorTokens::ToString(&v78, &v71, 0, -1);
    v43 = *((_QWORD *)this + 9);
    v44 = v71;
    if ( v71 != (struct DWrite::RefString::Data *)v43 )
    {
      v45 = *(unsigned int *)(v43 + 4);
      if ( *((_DWORD *)v71 + 1) == v45 )
      {
        if ( !wmemcmp((const wchar_t *)v71 + 4, (const wchar_t *)(v43 + 8), v45) )
          goto LABEL_51;
        v44 = v71;
      }
      v54 = *((_QWORD *)this + 3);
      if ( v44 == (struct DWrite::RefString::Data *)v54
        || (v55 = *(unsigned int *)(v54 + 4), *((_DWORD *)v44 + 1) == v55)
        && !wmemcmp((const wchar_t *)v44 + 4, (const wchar_t *)(v54 + 8), v55) )
      {
        if ( (__int128 *)((char *)this + 184) != &v74 )
          std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Assign_counted_range<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> *>(
            (__int64 *)this + 23,
            v74,
            0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v74 + 1) - v74) >> 3));
        if ( (__int128 *)((char *)this + 208) != &v72 )
          std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Assign_counted_range<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> *>(
            (__int64 *)this + 26,
            v72,
            0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v72 + 1) - v72) >> 3));
      }
      else
      {
        v77 = v38;
        *(_OWORD *)v66 = *((_OWORD *)this + 7);
        v89 = *(_OWORD *)((char *)this + 136);
        v90 = *((_OWORD *)this + 10);
        v67 = 0;
        v68 = 0;
        v69 = HIDWORD(v94[0]);
        BuildFaceName(
          (unsigned int)v65,
          (unsigned int)&v67,
          (unsigned int)&v90,
          *((unsigned __int8 *)this + 180),
          (__int64)&v89,
          *((unsigned __int16 *)this + 89),
          (__int64)v66,
          *((unsigned __int8 *)this + 177),
          (__int64)&v77);
        std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v94);
        FontNameList::AppendItem(v94, (char *)this + 40, &v71);
        FontNameList::operator=((char *)this + 184, v94);
        FontNameList::~FontNameList((FontNameList *)v94);
        std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v94);
        FontNameList::AppendItem(v94, (char *)this + 40, v65);
        FontNameList::operator=((char *)this + 208, v94);
        FontNameList::~FontNameList((FontNameList *)v94);
        DWrite::RefString::DecrementRef(v65[0]);
      }
    }
LABEL_51:
    DWrite::RefString::DecrementRef(v71);
  }
  if ( !v63 )
  {
    for ( i = v79; i != v80; i += 12 )
    {
      if ( *((_DWORD *)v70 + 1) >= *(_DWORD *)(i + 4) && *(_BYTE *)(i + 8) )
      {
        FontDifferentiatorTokens::ToString(&v78, &v67, 0, *((unsigned int *)v70 + 1));
        std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v94);
        FontNameList::AppendItem(v94, (char *)this + 40, &v67);
        FontNameList::operator=((char *)this + 232, v94);
        FontNameList::~FontNameList((FontNameList *)v94);
        FontDifferentiatorTokens::ToString(&v78, v66, *((unsigned int *)v70 + 1), 0xFFFFFFFFLL);
        v90 = v38;
        v89 = *((_OWORD *)this + 7);
        v93 = *(_OWORD *)((char *)this + 136);
        v94[0] = *((_OWORD *)this + 10);
        *(_QWORD *)&v77 = (char *)v66[0] + 8;
        DWORD2(v77) = *((_DWORD *)v66[0] + 1);
        HIDWORD(v77) = HIDWORD(v94[0]);
        BuildFaceName(
          (unsigned int)v65,
          (unsigned int)&v77,
          (unsigned int)v94,
          *((unsigned __int8 *)this + 180),
          (__int64)&v93,
          *((unsigned __int16 *)this + 89),
          (__int64)&v89,
          *((unsigned __int8 *)this + 177),
          (__int64)&v90);
        std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v94);
        FontNameList::AppendItem(v94, (char *)this + 40, v65);
        FontNameList::operator=((char *)this + 256, v94);
        FontNameList::~FontNameList((FontNameList *)v94);
        DWrite::RefString::DecrementRef(v65[0]);
        DWrite::RefString::DecrementRef(v66[0]);
        DWrite::RefString::DecrementRef(v67);
        break;
      }
    }
  }
  *(_BYTE *)this = 1;
  FontDifferentiatorTokens::~FontDifferentiatorTokens((FontDifferentiatorTokens *)&v78);
  DWrite::RefString::DecrementRef(v76[0]);
  DWrite::RefString::DecrementRef(v70);
LABEL_60:
  v47 = (__int64 *)((char *)this + 232);
  if ( *((_QWORD *)this + 29) == *((_QWORD *)this + 30) && v47 != (__int64 *)&v74 )
  {
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy((char *)this + 232);
    *(_OWORD *)v47 = v74;
    *((_QWORD *)this + 31) = v75;
    v74 = 0;
    v75 = 0;
  }
  v48 = (__int128 *)((char *)this + 256);
  if ( *((_QWORD *)this + 32) == *((_QWORD *)this + 33) && v48 != &v72 )
  {
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy((char *)this + 256);
    *v48 = v72;
    *((_QWORD *)this + 34) = v73;
    v72 = 0;
    v73 = 0;
  }
  v49 = (__int64 *)((char *)this + 184);
  if ( *((_QWORD *)this + 23) == *((_QWORD *)this + 24) && v49 != v47 )
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Assign_counted_range<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> *>(
      v49,
      *v47,
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 30) - *((_QWORD *)this + 29)) >> 3));
  v50 = (__int128 *)((char *)this + 208);
  if ( *((_QWORD *)this + 26) == *((_QWORD *)this + 27) && v50 != v48 )
    std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Assign_counted_range<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> *>(
      (__int64 *)this + 26,
      *(_QWORD *)v48,
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 33) - *((_QWORD *)this + 32)) >> 3));
  if ( !v25 )
  {
    LODWORD(v65[0]) = 0x7FFFFFFF;
    v57 = 0;
    v58 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 27) - *((_QWORD *)this + 26)) >> 3);
    if ( v58 )
    {
      while ( v57 < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 27) - *(_QWORD *)v50) >> 3) )
      {
        v59 = *(_QWORD *)v50 + 40 * v57;
        if ( *(_QWORD *)(v59 + 24) <= 7u )
          v60 = (const WCHAR *)(*(_QWORD *)v50 + 40 * v57);
        else
          v60 = *(const WCHAR **)v59;
        v61 = LocaleNameToLCID(v60, 0);
        v62 = v61;
        if ( v61 && v61 < SLODWORD(v65[0]) )
        {
          std::wstring::operator=((char *)this + 40, v59);
          LODWORD(v65[0]) = v62;
        }
        if ( ++v57 >= v58 )
          goto LABEL_73;
      }
LABEL_120:
      FailAssert(0x35u, v16);
      JUMPOUT(0x180028C3CLL);
    }
  }
LABEL_73:
  v65[0] = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
  if ( (unsigned __int8)TryGetName(v91, 5, v25, v65) )
  {
    v51 = VersionStringToDouble(
            (const wchar_t *const)v65[0] + 4,
            (const wchar_t *const)v65[0] + *((unsigned int *)v65[0] + 1) + 4);
    DWrite::RefString::DecrementRef(v52);
  }
  else
  {
    DWrite::RefString::DecrementRef(v65[0]);
    v51 = 0.0;
  }
  *((double *)this + 1) = v51;
  FontNameList::~FontNameList((FontNameList *)&v72);
  FontNameList::~FontNameList((FontNameList *)&v74);
  FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(v91);
  return this;
}

```

## disassembly

```asm
0x180027e0c  mov     rax, rsp
0x180027e0f  mov     [rax+18h], rbx
0x180027e13  push    rbp
0x180027e14  push    rsi
0x180027e15  push    rdi
0x180027e16  push    r12
0x180027e18  push    r13
0x180027e1a  push    r14
0x180027e1c  push    r15
0x180027e1e  lea     rbp, [rax-188h]
0x180027e25  sub     rsp, 250h
0x180027e2c  movaps  xmmword ptr [rax-48h], xmm6
0x180027e30  mov     rax, cs:__security_cookie
0x180027e37  xor     rax, rsp
0x180027e3a  mov     [rbp+180h+var_50], rax
0x180027e41  mov     rsi, rdx
0x180027e44  mov     [rbp+180h+var_200], rdx
0x180027e48  mov     rdi, rcx
0x180027e4b  mov     [rbp+180h+var_90], rcx
0x180027e52  xor     r9d, r9d
0x180027e55  mov     [rcx], r9b
0x180027e58  mov     rax, [rdx+28h]
0x180027e5c  test    rax, rax
0x180027e5f  jz      loc_1800288DF
0x180027e65  movzx   ecx, byte ptr [rax+3Fh]
0x180027e69  movzx   eax, byte ptr [rax+3Eh]
0x180027e6d  shl     ax, 8
0x180027e71  or      cx, ax
0x180027e74  bt      cx, 8
0x180027e79  mov     al, 1
0x180027e7b  jnb     loc_1800288DF
0x180027e81  mov     [rdi+1], al
0x180027e84  mov     rcx, rsi
0x180027e87  call    ?GetFontWeightFromFace@@YA?AW4DWRITE_FONT_WEIGHT@@AEBVOpenTypeFace@@@Z; GetFontWeightFromFace(OpenTypeFace const &)
0x180027e8c  mov     [rdi+10h], ax
0x180027e90  mov     rcx, rsi
0x180027e93  call    ?GetFontStretchFromFace@@YA?AW4DWRITE_FONT_STRETCH@@AEBVOpenTypeFace@@@Z; GetFontStretchFromFace(OpenTypeFace const &)
0x180027e98  mov     [rdi+12h], al
0x180027e9b  mov     rcx, rsi
0x180027e9e  call    ?GetFontStyleFromFace@@YA?AW4DWRITE_FONT_STYLE@@AEBVOpenTypeFace@@@Z; GetFontStyleFromFace(OpenTypeFace const &)
0x180027ea3  mov     [rdi+13h], al
0x180027ea6  lea     rdx, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180027ead  mov     [rdi+18h], rdx
0x180027eb1  mov     [rdi+20h], rdx
0x180027eb5  lea     rbx, [rdi+28h]
0x180027eb9  mov     rcx, rbx
0x180027ebc  call    ??0?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@QEAA@XZ; GenericLanguageTag<std::wstring>::GenericLanguageTag<std::wstring>(void)
0x180027ec1  nop
0x180027ec2  mov     [rdi+48h], rdx
0x180027ec6  mov     [rdi+50h], r9w
0x180027ecb  mov     [rdi+58h], rdx
0x180027ecf  mov     [rdi+60h], r9w
0x180027ed4  mov     [rdi+68h], rdx
0x180027ed8  mov     [rdi+70h], r9
0x180027edc  mov     [rdi+78h], r9d
0x180027ee0  mov     [rdi+80h], r9b
0x180027ee7  mov     [rdi+88h], r9
0x180027eee  mov     [rdi+90h], r9d
0x180027ef5  mov     [rdi+98h], r9w
0x180027efd  mov     [rdi+0A0h], r9
0x180027f04  mov     [rdi+0A8h], r9d
0x180027f0b  mov     [rdi+0B0h], r9b
0x180027f12  mov     al, [rdi+13h]
0x180027f15  mov     [rdi+0B1h], al
0x180027f1b  movzx   eax, word ptr [rdi+10h]
0x180027f1f  mov     [rdi+0B2h], ax
0x180027f26  mov     al, [rdi+12h]
0x180027f29  mov     [rdi+0B4h], al
0x180027f2f  lea     r12, [rdi+0B8h]
0x180027f36  mov     rcx, r12; this
0x180027f39  call    ??0FontNameList@@QEAA@XZ; FontNameList::FontNameList(void)
0x180027f3e  nop
0x180027f3f  lea     r15, [rdi+0D0h]
0x180027f46  mov     rcx, r15; this
0x180027f49  call    ??0FontNameList@@QEAA@XZ; FontNameList::FontNameList(void)
0x180027f4e  nop
0x180027f4f  lea     r14, [rdi+0E8h]
0x180027f56  mov     rcx, r14; this
0x180027f59  call    ??0FontNameList@@QEAA@XZ; FontNameList::FontNameList(void)
0x180027f5e  nop
0x180027f5f  lea     r13, [rdi+100h]
0x180027f66  mov     rcx, r13; this
0x180027f69  call    ??0FontNameList@@QEAA@XZ; FontNameList::FontNameList(void)
0x180027f6e  nop
0x180027f6f  mov     rdx, rsi; struct OpenTypeTables *
0x180027f72  lea     rcx, [rbp+180h+var_E0]; this
0x180027f79  call    ??0OpenTypeNameTable@@QEAA@AEBVOpenTypeTables@@@Z; OpenTypeNameTable::OpenTypeNameTable(OpenTypeTables const &)
0x180027f7e  nop
0x180027f7f  lea     rcx, [rbp+180h+var_1C8]; void *
0x180027f83  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180027f88  nop
0x180027f89  mov     r8d, 1; unsigned __int16
0x180027f8f  lea     rdx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x180027f96  lea     rcx, [rbp+180h+var_1C8]; this
0x180027f9a  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180027f9f  nop
0x180027fa0  lea     rcx, [rbp+180h+var_1E0]; void *
0x180027fa4  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180027fa9  nop
0x180027faa  mov     r8d, 2; unsigned __int16
0x180027fb0  lea     rdx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x180027fb7  lea     rcx, [rbp+180h+var_1E0]; this
0x180027fbb  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180027fc0  nop
0x180027fc1  lea     rcx, [rbp+180h+var_168]; void *
0x180027fc5  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180027fca  nop
0x180027fcb  mov     r8d, 15h; unsigned __int16
0x180027fd1  lea     rdx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x180027fd8  lea     rcx, [rbp+180h+var_168]; this
0x180027fdc  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180027fe1  nop
0x180027fe2  lea     rax, [rbp+180h+var_168]
0x180027fe6  cmp     r12, rax
0x180027fe9  jz      short loc_180028018
0x180027feb  mov     rcx, r12
0x180027fee  call    ?_Tidy@?$vector@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@V?$allocator@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@@std@@@std@@AEAAXXZ; std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy(void)
0x180027ff3  movups  xmm0, [rbp+180h+var_168]
0x180027ff7  movups  xmmword ptr [r12], xmm0
0x180027ffc  movsd   xmm1, [rbp+180h+var_158]
0x180028001  movsd   qword ptr [r12+10h], xmm1
0x180028008  xorps   xmm0, xmm0
0x18002800b  movdqu  [rbp+180h+var_168], xmm0
0x180028010  mov     [rbp+180h+var_158], 0
0x180028018  lea     rcx, [rbp+180h+var_168]; this
0x18002801c  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180028021  lea     rcx, [rbp+180h+var_150]; void *
0x180028025  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18002802a  nop
0x18002802b  mov     r8d, 16h; unsigned __int16
0x180028031  lea     rdx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x180028038  lea     rcx, [rbp+180h+var_150]; this
0x18002803c  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180028041  nop
0x180028042  lea     rax, [rbp+180h+var_150]
0x180028046  cmp     r15, rax
0x180028049  jz      short loc_180028076
0x18002804b  mov     rcx, r15
0x18002804e  call    ?_Tidy@?$vector@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@V?$allocator@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@@std@@@std@@AEAAXXZ; std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy(void)
0x180028053  movups  xmm0, [rbp+180h+var_150]
0x180028057  movups  xmmword ptr [r15], xmm0
0x18002805b  movsd   xmm1, [rbp+180h+var_140]
0x180028060  movsd   qword ptr [r15+10h], xmm1
0x180028066  xorps   xmm0, xmm0
0x180028069  movdqu  [rbp+180h+var_150], xmm0
0x18002806e  mov     [rbp+180h+var_140], 0
0x180028076  lea     rcx, [rbp+180h+var_150]; this
0x18002807a  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x18002807f  lea     rcx, [rbp+180h+var_138]; void *
0x180028083  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180028088  nop
0x180028089  mov     r8d, 10h; unsigned __int16
0x18002808f  lea     rdx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x180028096  lea     rcx, [rbp+180h+var_138]; this
0x18002809a  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x18002809f  nop
0x1800280a0  lea     rax, [rbp+180h+var_138]
0x1800280a4  cmp     r14, rax
0x1800280a7  jz      short loc_1800280D4
0x1800280a9  mov     rcx, r14
0x1800280ac  call    ?_Tidy@?$vector@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@V?$allocator@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@@std@@@std@@AEAAXXZ; std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy(void)
0x1800280b1  movups  xmm0, [rbp+180h+var_138]
0x1800280b5  movups  xmmword ptr [r14], xmm0
0x1800280b9  movsd   xmm1, [rbp+180h+var_128]
0x1800280be  movsd   qword ptr [r14+10h], xmm1
0x1800280c4  xorps   xmm0, xmm0
0x1800280c7  movdqu  [rbp+180h+var_138], xmm0
0x1800280cc  mov     [rbp+180h+var_128], 0
0x1800280d4  lea     rcx, [rbp+180h+var_138]; this
0x1800280d8  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x1800280dd  lea     rcx, [rbp+180h+var_120]; void *
0x1800280e1  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x1800280e6  nop
0x1800280e7  mov     r8d, 11h; unsigned __int16
0x1800280ed  lea     rdx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x1800280f4  lea     rcx, [rbp+180h+var_120]; this
0x1800280f8  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x1800280fd  nop
0x1800280fe  lea     rax, [rbp+180h+var_120]
0x180028102  cmp     r13, rax
0x180028105  jz      short loc_180028133
0x180028107  mov     rcx, r13
0x18002810a  call    ?_Tidy@?$vector@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@V?$allocator@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@@std@@@std@@AEAAXXZ; std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Tidy(void)
0x18002810f  movups  xmm0, [rbp+180h+var_120]
0x180028113  movups  xmmword ptr [r13+0], xmm0
0x180028118  movsd   xmm1, [rbp+180h+var_110]
0x18002811d  movsd   qword ptr [r13+10h], xmm1
0x180028123  xorps   xmm0, xmm0
0x180028126  movdqu  [rbp+180h+var_120], xmm0
0x18002812b  mov     [rbp+180h+var_110], 0
0x180028133  lea     rcx, [rbp+180h+var_120]; this
0x180028137  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x18002813c  lea     r9, [rdi+20h]; struct DWrite::RefString *
0x180028140  lea     r8, [rdi+18h]; struct DWrite::RefString *
0x180028144  lea     rcx, [rbp+180h+var_E0]; struct OpenTypeNameTable *
0x18002814b  call    ?TryGetCanonicalNamesAndLanguage@@YAHAEBVOpenTypeNameTable@@GPEAVRefString@DWrite@@1@Z; TryGetCanonicalNamesAndLanguage(OpenTypeNameTable const &,ushort,DWrite::RefString *,DWrite::RefString *)
0x180028150  mov     ecx, eax
0x180028152  mov     dword ptr [rsp+280h+var_228+8], eax
0x180028156  xor     r8d, r8d
0x180028159  test    eax, eax
0x18002815b  jz      short loc_1800281C1
0x18002815d  mov     edx, eax
0x18002815f  lea     rcx, [rbp+180h+var_70]
0x180028166  call    ??0?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@QEAA@H_N@Z; GenericLanguageTag<std::wstring>::GenericLanguageTag<std::wstring>(int,bool)
0x18002816b  mov     rsi, rax
0x18002816e  cmp     rbx, rax
0x180028171  jz      short loc_1800281AA
0x180028173  mov     rdx, [rbx+18h]
0x180028177  cmp     rdx, 7
0x18002817b  ja      loc_180028B6A
0x180028181  xor     ecx, ecx
0x180028183  mov     [rbx+10h], rcx
0x180028187  lea     edx, [rcx+7]
0x18002818a  mov     [rbx+18h], rdx
0x18002818e  mov     [rbx], cx
0x180028191  movups  xmm0, xmmword ptr [rsi]
0x180028194  movups  xmmword ptr [rbx], xmm0
0x180028197  movups  xmm1, xmmword ptr [rsi+10h]
0x18002819b  movups  xmmword ptr [rbx+10h], xmm1
0x18002819f  mov     [rsi+10h], rcx
0x1800281a3  mov     [rsi+18h], rdx
0x1800281a7  mov     [rsi], cx
0x1800281aa  lea     rcx, [rbp+180h+var_70]; void *
0x1800281b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800281b6  mov     rsi, [rbp+180h+var_200]
0x1800281ba  mov     ecx, dword ptr [rsp+280h+var_228+8]
0x1800281be  xor     r8d, r8d
0x1800281c1  cmp     [rsi+1B4h], r8d
0x1800281c8  jnz     loc_1800288E7
0x1800281ce  mov     dl, r8b
0x1800281d1  mov     rax, [r14+8]
0x1800281d5  cmp     [r14], rax
0x1800281d8  jz      loc_1800288B4
0x1800281de  mov     r8b, 1
0x1800281e1  mov     [rsp+280h+var_230], r8b
0x1800281e6  mov     rax, [r12+8]
0x1800281eb  cmp     [r12], rax
0x1800281ef  jnz     loc_1800288C7
0x1800281f5  xor     r12d, r12d
0x1800281f8  mov     r15b, r12b
0x1800281fb  test    r8b, r8b
0x1800281fe  jnz     loc_18002895D
0x180028204  test    ecx, ecx
0x180028206  jz      loc_180028966
0x18002820c  test    dl, dl
0x18002820e  jnz     loc_180028966
0x180028214  cmp     [rdi+1], r12b
0x180028218  jnz     loc_180028966
0x18002821e  lea     rbx, [rdi+48h]
0x180028222  mov     r9, rbx
0x180028225  mov     r8d, ecx
0x180028228  mov     esi, 10h
0x18002822d  mov     edx, esi
0x18002822f  lea     rcx, [rbp+180h+var_E0]
0x180028236  call    ?TryGetName@@YA_NAEBVOpenTypeNameTable@@W4OpenTypeNameID@@HPEAVRefString@DWrite@@@Z; TryGetName(OpenTypeNameTable const &,OpenTypeNameID,int,DWrite::RefString *)
0x18002823b  test    al, al
0x18002823d  jnz     loc_180028A05
0x180028243  mov     rax, [rdi+18h]
0x180028247  lock inc dword ptr [rax]
0x18002824a  mov     rcx, [rbx]; struct DWrite::RefString::Data *
0x18002824d  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180028252  mov     rax, [rdi+18h]
0x180028256  mov     [rbx], rax
0x180028259  lea     eax, [rsi-0Fh]
0x18002825c  mov     [rdi+50h], ax
0x180028260  lea     rbx, [rdi+58h]
0x180028264  mov     r9, rbx
0x180028267  mov     r13d, dword ptr [rsp+280h+var_228+8]
0x18002826c  mov     r8d, r13d
0x18002826f  mov     esi, 11h
0x180028274  mov     edx, esi
0x180028276  lea     rcx, [rbp+180h+var_E0]
0x18002827d  call    ?TryGetName@@YA_NAEBVOpenTypeNameTable@@W4OpenTypeNameID@@HPEAVRefString@DWrite@@@Z; TryGetName(OpenTypeNameTable const &,OpenTypeNameID,int,DWrite::RefString *)
0x180028282  test    al, al
0x180028284  jnz     loc_180028955
0x18002828a  mov     rax, [rdi+20h]
0x18002828e  lock inc dword ptr [rax]
0x180028291  mov     rcx, [rbx]; struct DWrite::RefString::Data *
0x180028294  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180028299  mov     rax, [rdi+20h]
0x18002829d  mov     [rbx], rax
0x1800282a0  lea     eax, [rsi-0Fh]
0x1800282a3  mov     [rdi+60h], ax
0x1800282a7  lea     rdx, [rdi+48h]
0x1800282ab  lea     rcx, [rbp+180h+var_1F0]
0x1800282af  call    ?Trim@@YA?AVRefString@DWrite@@AEBV12@@Z; Trim(DWrite::RefString const &)
0x1800282b4  nop
0x1800282b5  lea     rdx, [rdi+58h]
0x1800282b9  lea     rcx, [rbp+180h+var_1B0]
0x1800282bd  call    ?Trim@@YA?AVRefString@DWrite@@AEBV12@@Z; Trim(DWrite::RefString const &)
0x1800282c2  nop
0x1800282c3  mov     [rsp+280h+var_228+8], r12
0x1800282c8  mov     dword ptr [rsp+280h+var_218], r12d
0x1800282cd  lea     r8, [rsp+280h+var_228+8]
0x1800282d2  lea     rdx, [rbp+180h+var_1B0]
0x1800282d6  lea     rcx, [rsp+280h+var_218+8]
0x1800282db  call    ?RemoveRegularFromFaceName@@YA?AVRefString@DWrite@@AEBV12@PEAV?$CheckedPtr@$$CB_WVFailAsAssertionPolicy@@I@@@Z; RemoveRegularFromFaceName(DWrite::RefString const &,CheckedPtr<wchar_t const,FailAsAssertionPolicy,uint> *)
0x1800282e0  nop
0x1800282e1  mov     r8, rax
0x1800282e4  lea     rdx, [rbp+180h+var_1F0]
  ... truncated ...
```
