# OpenTypeFontFaceBuilder::ReadFontFace(void)

- ea: `0x1800268c0`
- end: `0x180027c9e`
- name: `?ReadFontFace@OpenTypeFontFaceBuilder@@EEAAXXZ`
- size: `5086`
- prototype: `void __fastcall(OpenTypeFontFaceBuilder *__hidden this)`
- caller_count: `0`
- callee_count: `45`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004810`
- `0x180006330`
- `0x1800063d4`
- `0x180006528`
- `0x1800082b0`
- `0x180008e8c`
- `0x180009d78`
- `0x18000a690`
- `0x18000ac30`
- `0x18000ad40`
- `0x18000e0ac`
- `0x1800147dc`
- `0x180016c60`
- `0x180016fc0`
- `0x180017300`
- `0x18001b630`
- `0x18001c8d4`
- `0x18001cbb4`
- `0x1800201d8`
- `0x180021044`
- `0x180024000`
- `0x1800246cc`
- `0x180024c5c`
- `0x180024db0`
- `0x1800268c0`
- `0x180027cb0`
- `0x180027e0c`
- `0x180028c50`
- `0x180029a0c`
- `0x18002bf90`
- `0x18007cf00`
- `0x18007cf80`
- `0x18007d5d8`
- `0x180088ae8`
- `0x18008c004`
- `0x18008c490`
- `0x18008cc98`
- `0x18008ce68`
- `0x18008fed0`
- `0x1800918f8`
- `0x180092308`
- `0x18009e3b8`
- `0x1800aa650`
- `0x1800b86e0`
- `0x1800bc95c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027afd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027afd`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
void __fastcall OpenTypeFontFaceBuilder::ReadFontFace(OpenTypeFontFaceBuilder *this)
{
  __int64 v2; // rdi
  const struct OpenTypeFace *v3; // r15
  _WORD *v4; // r14
  __int64 v5; // rax
  int v6; // ecx
  int v7; // ecx
  const wchar_t *v8; // rcx
  struct DWrite::RefString::Data *v9; // rbx
  struct DWrite::RefString::Data *v10; // r12
  __int64 v11; // rdi
  _BYTE *v12; // rcx
  unsigned __int64 v13; // rbx
  unsigned int v14; // r9d
  __int128 v15; // xmm0
  __int64 v16; // r10
  _BYTE *v17; // rcx
  __int64 v18; // r8
  struct DWrite::RefString::Data *v19; // rdx
  __int64 v20; // rdi
  struct DWrite::RefString::Data *v21; // rbx
  struct DWrite::RefString::Data *i; // rax
  struct DWrite::RefString::Data *v23; // rbx
  int *v24; // rax
  int v25; // ecx
  int v26; // eax
  __int16 v27; // cx
  struct DWrite::RefString::Data *j; // rax
  char FontStretchFromFace; // dl
  int v30; // eax
  const wchar_t *v31; // rcx
  char Style; // al
  struct DWrite::RefString::Data **v33; // r12
  struct DWrite::RefString::Data *v34; // rdi
  struct DWrite::RefString::Data *v35; // rbx
  __int64 v36; // r9
  struct DWrite::RefString::Data *v37; // rdi
  char *v38; // rbx
  struct DWrite::RefString::Data *v39; // rdi
  char *v40; // rbx
  __int64 v41; // r9
  struct DWrite::RefString::Data *v42; // rdi
  char *v43; // rbx
  __int64 v44; // r9
  struct DWrite::RefString::Data *v45; // rdi
  char *v46; // rbx
  __int64 v47; // r9
  int v48; // eax
  struct DWrite::RefString::Data *v49; // rdi
  char *v50; // rbx
  struct DWrite::RefString::Data **v51; // rdx
  __int64 v52; // rcx
  __int64 PostscriptNamesFromExistingNames; // rax
  ArgumentInsufficientBufferException *v54; // rax
  __int64 v55[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v56; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v57; // [rsp+70h] [rbp-90h]
  struct DWrite::RefString::Data *v58; // [rsp+80h] [rbp-80h] BYREF
  struct DWrite::RefString::Data *v59; // [rsp+88h] [rbp-78h]
  _BYTE v60[80]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v61[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v62[24]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v63[24]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v64[56]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v65[56]; // [rsp+170h] [rbp+70h] BYREF
  int v66; // [rsp+1A8h] [rbp+A8h]
  _BYTE v67[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v68; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v69; // [rsp+1E0h] [rbp+E0h]
  unsigned int v70; // [rsp+1E8h] [rbp+E8h]
  __int128 v71; // [rsp+1F0h] [rbp+F0h]
  _BYTE v72[16]; // [rsp+210h] [rbp+110h] BYREF
  __int16 v73; // [rsp+220h] [rbp+120h]
  char v74; // [rsp+223h] [rbp+123h]
  __int64 v75; // [rsp+228h] [rbp+128h]
  wchar_t *Src[17]; // [rsp+238h] [rbp+138h] BYREF
  char v77; // [rsp+2C1h] [rbp+1C1h]
  __int16 v78; // [rsp+2C2h] [rbp+1C2h]
  char v79; // [rsp+2C4h] [rbp+1C4h]
  _BYTE v80[24]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v81[24]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v82[24]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v83[32]; // [rsp+310h] [rbp+210h] BYREF
  struct DWrite::RefString::Data *v84; // [rsp+330h] [rbp+230h] BYREF
  __int64 v85; // [rsp+338h] [rbp+238h]
  void *Block; // [rsp+340h] [rbp+240h]

  v57 = 0;
  v2 = *((_QWORD *)this + 1);
  v3 = (OpenTypeFontFaceBuilder *)((char *)this + 944);
  *((_WORD *)this + 57) = *((_WORD *)this + 696);
  *((_QWORD *)this + 4) = FontFileReference::GetLastWriteTime((FontFileReference *)(v2 + 40));
  ReadPanose(v3, (OpenTypeFontFaceBuilder *)((char *)this + 94));
  ReadSupportedLanguageBits(v3, (OpenTypeFontFaceBuilder *)((char *)this + 116));
  OpenTypeCharacterMapSubtable::OpenTypeCharacterMapSubtable(
    (OpenTypeCharacterMapSubtable *)v65,
    v3,
    *((unsigned __int16 *)this + 696),
    0);
  if ( v66 == 3 || this != (OpenTypeFontFaceBuilder *)-94LL && *((_BYTE *)this + 94) == 5 )
  {
    v4 = (_WORD *)((char *)this + 112);
    *((_WORD *)this + 56) |= 1u;
  }
  else
  {
    v4 = (_WORD *)((char *)this + 112);
  }
  CompactCmapRegion::Create((OpenTypeCharacterMap *)v65);
  FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(v65);
  OpenTypeFontFaceBuilder::ReadFontStyleAttributes(this);
  v5 = *((_QWORD *)this + 119);
  if ( v5 && (*(_BYTE *)(v5 + 17) & 8) != 0 )
    *v4 |= 0x10u;
  if ( *((_DWORD *)this + 267) && *((_DWORD *)this + 268) && *((_DWORD *)this + 269) && *((_DWORD *)this + 270)
    || *((_DWORD *)this + 331) && *((_DWORD *)this + 332)
    || *((_DWORD *)this + 329) && *((_DWORD *)this + 330)
    || *((_DWORD *)this + 325) && *((_DWORD *)this + 326) )
  {
    *v4 |= 0x80u;
  }
  if ( IsMonospacedFont(v3, (OpenTypeFontFaceBuilder *)((char *)this + 94)) )
    *v4 |= 2u;
  if ( *((_DWORD *)this + 309) && *((_DWORD *)this + 310)
    || *((_DWORD *)this + 311) && *((_DWORD *)this + 312)
    || *((_DWORD *)this + 313) && *((_DWORD *)this + 314) )
  {
    *v4 |= 0x40u;
  }
  if ( *((_WORD *)this + 697) )
    *v4 |= 0x100u;
  if ( *((_DWORD *)this + 321) && *((_DWORD *)this + 322) )
    *v4 |= 0x200u;
  OpenTypeNameTable::OpenTypeNameTable((OpenTypeNameTable *)v60, v3);
  MetaTable::MetaTable((MetaTable *)v64, v3);
  FontDifferentiator::FontDifferentiator((FontDifferentiator *)v72, v3);
  v6 = *((_DWORD *)this + 170);
  *(_QWORD *)&v56 = *((_QWORD *)this + 84);
  DWORD2(v56) = v6 - v56;
  v7 = *((_DWORD *)this + 164);
  v58 = (struct DWrite::RefString::Data *)*((_QWORD *)this + 81);
  LODWORD(v59) = v7 - (_DWORD)v58;
  FontStyleAttributes::FontStyleAttributes(
    (FontStyleAttributes *)&v68,
    (const struct FontStyleAttributesRegion *)&v58,
    (const struct FontStringsRegion *)&v56);
  *(_QWORD *)&v56 = *((_QWORD *)this + 112);
  *((_QWORD *)&v56 + 1) = v56 + 8 * ((__int64)(*((_QWORD *)this + 113) - v56) >> 3);
  FontStyleAttributes::GetCanonicalAxisValues(&v68, &v56, (char *)this + 920);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v61);
  FontNameList::AppendItems((FontNameList *)v61, (const struct OpenTypeNameTable *)v60, 16);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v63);
  FontNameList::AppendItems((FontNameList *)v63, (const struct OpenTypeNameTable *)v60, 1);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 0);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 44) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 5);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 45) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 7);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 46) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 8);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 47) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 9);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 48) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 12);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 49) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 10);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 50) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 11);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 51) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 13);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 52) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 14);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 53) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 19);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 58) = (_DWORD)v58;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
  FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 20);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 61) = (_DWORD)v58;
  MetaTable::GetFontNameList(v64, v55, 1735289956);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 63) = (_DWORD)v58;
  MetaTable::GetFontNameList(v64, v55, 1735289971);
  FontFaceRegionBuilder::AddNameDictionary(this, &v58, v55);
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 64) = (_DWORD)v58;
  if ( !*((_DWORD *)this + 345) || !*((_DWORD *)this + 346) )
  {
    *((_WORD *)this + 52) = v78;
    *((_WORD *)this + 53) = v73;
    *((_BYTE *)this + 108) = v79;
    *((_BYTE *)this + 109) = v77;
    *((_BYTE *)this + 110) = v74;
    *((_DWORD *)this + 40) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v81);
    *((_DWORD *)this + 42) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v83);
    *((_DWORD *)this + 56) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v61);
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 1);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 54) = v56;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 2);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 55) = v56;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 17);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 57) = v56;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 4);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 59) = v56;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 21);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 62) = v56;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 6);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 60) = v56;
    if ( *(_QWORD *)v2 == 1 )
    {
      v58 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
      LocalFileLoader::DeserializeReferenceKeyFrom(
        *(const void **)(v2 + 24),
        *(_DWORD *)(v2 + 12),
        0,
        0,
        (struct DWrite::RefString *)&v58);
      std::wstring::wstring(v67);
      std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
      *(_QWORD *)&v56 = &v68;
      std::wstring::wstring(&v68, v67);
      v23 = v58;
      *(_QWORD *)&v71 = v58;
      _InterlockedIncrement((volatile signed __int32 *)v58);
      std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::push_back(v55, &v68);
      KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>::~KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>(&v68);
      v24 = (int *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
      v25 = *v24;
      *((_DWORD *)this + 39) = *v24;
      *((_DWORD *)this + 41) = v25;
      FontNameList::~FontNameList((FontNameList *)v55);
      GenericLanguageTag<std::wstring>::~GenericLanguageTag<std::wstring>(v67);
      DWrite::RefString::DecrementRef(v23);
    }
    else
    {
      *((_DWORD *)this + 39) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v80);
      *((_DWORD *)this + 41) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v82);
    }
    goto LABEL_31;
  }
  v10 = (struct DWrite::RefString::Data *)*((_QWORD *)this + 115);
  v11 = *((_QWORD *)this + 116);
  v12 = v63;
  if ( v61[0] != v61[1] )
    v12 = v61;
  *(_QWORD *)&v56 = v12;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v62);
  v13 = v70;
  ScopedArray<FontStyleAttributes::MatchingAxisValueRecord,30>::ScopedArray<FontStyleAttributes::MatchingAxisValueRecord,30>(
    &v84,
    v70);
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((v85 - (__int64)v84) >> 3) < v13 )
  {
    v54 = ArgumentInsufficientBufferException::ArgumentInsufficientBufferException((ArgumentInsufficientBufferException *)&v56);
    LogAndThrow<ArgumentInsufficientBufferException>(v54, 0x6365725F7861LL, 950);
  }
  ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord>::resize(&v84, (unsigned int)v13);
  v14 = 0;
  if ( (_DWORD)v13 )
  {
    v15 = v71;
    v16 = v69;
    do
    {
      if ( v14 >= v13 )
        FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v16);
      v17 = (_BYTE *)(v16 + 12LL * v14);
      v18 = 5LL * v14;
      v19 = v84;
      *((_BYTE *)v84 + 8 * v18) = *v17;
      *((_QWORD *)v19 + v18 + 2) = v17;
      *(_OWORD *)((char *)v19 + 8 * v18 + 24) = v15;
      ++v14;
    }
    while ( v14 < (unsigned int)v13 );
  }
  v20 = (v11 - (__int64)v10) >> 3;
  v21 = (struct DWrite::RefString::Data *)((char *)v10 + 8 * v20);
  *(_OWORD *)v55 = v68;
  v58 = v10;
  v59 = v21;
  GetMatchingAxisValueRecords<CheckedPtr<FontStyleAttributesRegion::Axis const,FailAsExceptionPolicy<InvalidCacheDataException>,unsigned int>,ScopedArrayWithFixedBuffer<FontStyleAttributes::MatchingAxisValueRecord>>(
    (_DWORD **)&v58,
    v55,
    &v84);
  for ( i = v10; ; i = (struct DWrite::RefString::Data *)((char *)i + 8) )
  {
    if ( i == v21 )
    {
      LOWORD(v26) = GetFontWeightFromFace(v3);
LABEL_67:
      v27 = v26;
      goto LABEL_68;
    }
    if ( *(_DWORD *)i == 1952999287 )
      break;
  }
  v26 = (*((_DWORD *)i + 1) + 0x8000) >> 16;
  if ( v26 < 1 )
  {
    LOWORD(v26) = 1;
    goto LABEL_67;
  }
  v27 = 999;
  if ( v26 <= 999 )
    goto LABEL_67;
LABEL_68:
  *((_WORD *)this + 52) = v27;
  *((_WORD *)this + 53) = v27;
  for ( j = v10; ; j = (struct DWrite::RefString::Data *)((char *)j + 8) )
  {
    if ( j == v21 )
    {
      FontStretchFromFace = GetFontStretchFromFace(v3);
      goto LABEL_76;
    }
    if ( *(_DWORD *)j == 1752458359 )
      break;
  }
  v30 = *((_DWORD *)j + 1);
  FontStretchFromFace = 0;
  v31 = (const wchar_t *)qword_1801007E0;
  do
  {
    ++FontStretchFromFace;
    if ( v30 < *(_DWORD *)v31 )
      break;
    v31 += 2;
  }
  while ( v31 != L"\\" );
LABEL_76:
  *((_BYTE *)this + 108) = FontStretchFromFace;
  v58 = v10;
  v59 = (struct DWrite::RefString::Data *)((char *)v10 + 8 * v20);
  Style = FontStyleAttributes::GetStyle(v3, &v58);
  *((_BYTE *)this + 109) = Style;
  *((_BYTE *)this + 110) = Style;
  v33 = (struct DWrite::RefString::Data **)v56;
  *((_DWORD *)this + 56) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(this, &v56, v56);
  v34 = v84;
  v35 = (struct DWrite::RefString::Data *)((char *)v84 + 8 * ((v85 - (__int64)v84) >> 3));
  *(_QWORD *)&v56 = "wght";
  *((_QWORD *)&v56 + 1) = "wght";
  v58 = v84;
  v59 = v35;
  LOBYTE(v36) = 1;
  FontStyleAttributes::SetRecordVisibilityByAxisValue(&v68, &v58, &v56, v36);
  *(_QWORD *)&v56 = v34;
  *((_QWORD *)&v56 + 1) = v35;
  FontStyleAttributes::GetStrings(&v68, v55, &v56, v33);
  v57 = 2;
  FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
  LODWORD(v58) = 0;
  v57 = 0;
  FontNameList::~FontNameList((FontNameList *)v55);
  *((_DWORD *)this + 54) = v56;
  v37 = v84;
  v38 = (char *)v84 + 8 * ((v85 - (__int64)v84) >> 3);
  *(_QWORD *)&v56 = "wght";
  *((_QWORD *)&v56 + 1) = "wght";
  v55[0] = (__int64)v84;
  v55[1] = (__int64)v38;
  FontStyleAttributes::SetRecordVisibilityByAxisValue(&v68, v55, &v56, 0);
  v55[0] = (__int64)v37;
  v55[1] = (__int64)v38;
  FontStyleAttributes::GetStrings(&v68, v67, v55, v62);
  LODWORD(v38) = (unsigned int)v58 | 4;
  v57 = (unsigned int)v58 | 4;
  FontFaceRegionBuilder::AddNameDictionary(this, &v56, v67);
  LODWORD(v58) = (unsigned int)v38 & 0xFFFFFFFB;
  v57 = (unsigned int)v38 & 0xFFFFFFFB;
  FontNameList::~FontNameList((FontNameList *)v67);
  *((_DWORD *)this + 55) = v56;
  v39 = v84;
  v40 = (char *)v84 + 8 * ((v85 - (__int64)v84) >> 3);
  v56 = 0;
  v55[0] = (__int64)v84;
  v55[1] = (__int64)v40;
  LOBYTE(v41) = 1;
  FontStyleAttributes::SetRecordVisibilityByAxisValue(&v68, v55, &v56, v41);
  v55[0] = (__int64)v39;
  v55[1] = (__int64)v40;
  FontStyleAttributes::GetStrings(&v68, v67, v55, v62);
  LODWORD(v40) = (unsigned int)v58 | 8;
  v57 = (unsigned int)v58 | 8;
  FontFaceRegionBuilder::AddNameDictionary(this, &v56, v67);
  LODWORD(v58) = (unsigned int)v40 & 0xFFFFFFF7;
  v57 = (unsigned int)v40 & 0xFFFFFFF7;
  FontNameList::~FontNameList((FontNameList *)v67);
  *((_DWORD *)this + 57) = v56;
  v42 = v84;
  v43 = (char *)v84 + 8 * ((v85 - (__int64)v84) >> 3);
  v56 = 0;
  v55[0] = (__int64)v84;
  v55[1] = (__int64)v43;
  LOBYTE(v44) = 1;
  FontStyleAttributes::SetRecordVisibilityByAxisValue(&v68, v55, &v56, v44);
  v55[0] = (__int64)v42;
  v55[1] = (__int64)v43;
  FontStyleAttributes::GetStrings(&v68, v67, v55, v33);
  LODWORD(v43) = (unsigned int)v58 | 0x10;
  v57 = (unsigned int)v58 | 0x10;
  FontFaceRegionBuilder::AddNameDictionary(this, &v56, v67);
  LODWORD(v58) = (unsigned int)v43 & 0xFFFFFFEF;
  v57 = (unsigned int)v43 & 0xFFFFFFEF;
  FontNameList::~FontNameList((FontNameList *)v67);
  *((_DWORD *)this + 59) = v56;
  v45 = v84;
  v46 = (char *)v84 + 8 * ((v85 - (__int64)v84) >> 3);
  v55[0] = (__int64)"wght";
  v55[1] = (__int64)&dword_1800EB074;
  *(_QWORD *)&v56 = v84;
  *((_QWORD *)&v56 + 1) = v46;
  LOBYTE(v47) = 1;
  FontStyleAttributes::SetRecordVisibilityByAxisValue(&v68, &v56, v55, v47);
  v55[0] = (__int64)v45;
  v55[1] = (__int64)v46;
  FontStyleAttributes::GetStrings(&v68, v67, v55, v33);
  LODWORD(v46) = (unsigned int)v58 | 0x20;
  v57 = (unsigned int)v58 | 0x20;
  FontFaceRegionBuilder::AddNameDictionary(this, &v56, v67);
  LODWORD(v58) = (unsigned int)v46 & 0xFFFFFFDF;
  v57 = (unsigned int)v46 & 0xFFFFFFDF;
  FontNameList::~FontNameList((FontNameList *)v67);
  v48 = v56;
  *((_DWORD *)this + 62) = v56;
  *((_DWORD *)this + 39) = v48;
  v49 = v84;
  v50 = (char *)v84 + 8 * ((v85 - (__int64)v84) >> 3);
  v55[0] = (__int64)"wght";
  v55[1] = (__int64)&dword_1800EB074;
  *(_QWORD *)&v56 = v84;
  *((_QWORD *)&v56 + 1) = v50;
  FontStyleAttributes::SetRecordVisibilityByAxisValue(&v68, &v56, v55, 0);
  v55[0] = (__int64)v49;
  v55[1] = (__int64)v50;
  FontStyleAttributes::GetStrings(&v68, v67, v55, v62);
  LODWORD(v50) = (unsigned int)v58 | 0x40;
  v57 = (unsigned int)v58 | 0x40;
  FontFaceRegionBuilder::AddNameDictionary(this, &v56, v67);
  v57 = (unsigned int)v50 & 0xFFFFFFBF;
  FontNameList::~FontNameList((FontNameList *)v67);
  *((_DWORD *)this + 40) = v56;
  *((_DWORD *)this + 41) = *((_DWORD *)this + 56);
  *((_DWORD *)this + 42) = *((_DWORD *)this + 57);
  if ( *((_WORD *)this + 697) )
  {
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v58);
    FontNameList::AppendItems((FontNameList *)&v58, (const struct OpenTypeNameTable *)v60, 25);
    v51 = &v58;
    if ( v58 == v59 )
      v51 = v33;
    v56 = 0;
    v55[0] = (__int64)v84;
    v55[1] = (__int64)v84 + 8 * ((v85 - (__int64)v84) >> 3);
    OpenTypeFontFaceBuilder::CreateFontNames(
      (_DWORD)v84 + 8 * ((v85 - (__int64)v84) >> 3),
      (unsigned int)v67,
      (unsigned int)&v68,
      (unsigned int)v55,
      (__int64)&v56,
      (__int64)v51,
      1);
    PostscriptNamesFromExistingNames = OpenTypeFontFaceBuilder::CreatePostscriptNamesFromExistingNames(v52, v55, v67);
    *((_DWORD *)this + 60) = *(_DWORD *)FontFaceRegionBuilder::AddNameDictionary(
                                          this,
                                          &v56,
                                          PostscriptNamesFromExistingNames);
    FontNameList::~FontNameList((FontNameList *)v55);
    FontNameList::~FontNameList((FontNameList *)v67);
    FontNameList::~FontNameList((FontNameList *)&v58);
  }
  else
  {
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v55);
    FontNameList::AppendItems((FontNameList *)v55, (const struct OpenTypeNameTable *)v60, 6);
    FontFaceRegionBuilder::AddNameDictionary(this, &v56, v55);
    FontNameList::~FontNameList((FontNameList *)v55);
    *((_DWORD *)this + 60) = v56;
  }
  free(Block);
  FontNameList::~FontNameList((FontNameList *)v62);
LABEL_31:
  v8 = (const wchar_t *)Src;
  if ( Src[3] > (wchar_t *)7 )
    v8 = Src[0];
  v9 = DWrite::RefString::NewData(v8, (unsigned __int64)Src[2]);
  *(_QWORD *)&v56 = v9;
  *((_DWORD *)this + 38) = StringMemoryRegionDictionary::WriteString(
                             (OpenTypeFontFaceBuilder *)((char *)this + 392),
                             (const struct DWrite::RefString *)&v56,
                             (OpenTypeFontFaceBuilder *)((char *)this + 400));
  DWrite::RefString::DecrementRef(v9);
  if ( OpenTypeFontFaceBuilder::IsThinFontFamily((const wchar_t *)(v75 + 8)) )
    *v4 |= 4u;
  v55[0] = *((_QWORD *)this + 109);
  v55[1] = v55[0] + 4 * ((*((_QWORD *)this + 110) - v55[0]) >> 2);
  InitializeFontMetrics(v3, (__int64)this + 88);
  if ( (*v4 & 0x20) == 0
    && (!*((_DWORD *)this + 265)
     || !*((_DWORD *)this + 266)
     || !*((_QWORD *)this + 119)
     || !*((_QWORD *)this + 121)
     || !*((_DWORD *)this + 285)
     || !*((_DWORD *)this + 286)
     || !*((_DWORD *)this + 257)
     || !*((_DWORD *)this + 301)
     || !*((_DWORD *)this + 302)
     || !*((_QWORD *)this + 123)
     || !*((_DWORD *)this + 260)) )
  {
    *v4 |= 0x20u;
  }
  FontNameList::~FontNameList((FontNameList *)v63);
  FontNameList::~FontNameList((FontNameList *)v61);
  FontDifferentiator::~FontDifferentiator((FontDifferentiator *)v72);
  FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(v64);
  FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(v60);
}

```

## disassembly

```asm
0x1800268c0  push    rbp
0x1800268c2  push    rbx
0x1800268c3  push    rsi
0x1800268c4  push    rdi
0x1800268c5  push    r12
0x1800268c7  push    r13
0x1800268c9  push    r14
0x1800268cb  push    r15
0x1800268cd  lea     rbp, [rsp-728h]
0x1800268d5  sub     rsp, 828h
0x1800268dc  mov     rax, cs:__security_cookie
0x1800268e3  xor     rax, rsp
0x1800268e6  mov     [rbp+760h+var_50], rax
0x1800268ed  mov     rsi, rcx
0x1800268f0  xor     r12d, r12d
0x1800268f3  mov     [rsp+860h+var_7F0], r12d
0x1800268f8  mov     rdi, [rcx+8]
0x1800268fc  lea     r15, [rcx+3B0h]
0x180026903  movzx   eax, word ptr [r15+1C0h]
0x18002690b  mov     [rcx+72h], ax
0x18002690f  lea     rcx, [rdi+28h]; this
0x180026913  call    ?GetLastWriteTime@FontFileReference@@QEBA_KXZ; FontFileReference::GetLastWriteTime(void)
0x180026918  mov     [rsi+20h], rax
0x18002691c  lea     rbx, [rsi+5Eh]
0x180026920  mov     rdx, rbx; union DWRITE_PANOSE *
0x180026923  mov     rcx, r15; struct OpenTypeFace *
0x180026926  call    ?ReadPanose@@YAXAEBVOpenTypeFace@@AEATDWRITE_PANOSE@@@Z; ReadPanose(OpenTypeFace const &,DWRITE_PANOSE &)
0x18002692b  lea     rdx, [rsi+74h]; struct FontFaceRegion::SupportedLanguageBits *
0x18002692f  mov     rcx, r15; struct OpenTypeFace *
0x180026932  call    ?ReadSupportedLanguageBits@@YAXAEBVOpenTypeFace@@AEAUSupportedLanguageBits@FontFaceRegion@@@Z; ReadSupportedLanguageBits(OpenTypeFace const &,FontFaceRegion::SupportedLanguageBits &)
0x180026937  movzx   r8d, word ptr [rsi+570h]; unsigned int
0x18002693f  xor     r9d, r9d; unsigned int
0x180026942  mov     rdx, r15; struct OpenTypeTables *
0x180026945  lea     rcx, [rbp+760h+var_6F0]; this
0x180026949  call    ??0OpenTypeCharacterMapSubtable@@IEAA@AEBVOpenTypeTables@@II@Z; OpenTypeCharacterMapSubtable::OpenTypeCharacterMapSubtable(OpenTypeTables const &,uint,uint)
0x18002694e  nop
0x18002694f  lea     eax, [r12+1]
0x180026954  cmp     [rbp+760h+var_6B8], 3
0x18002695b  jz      short loc_18002696F
0x18002695d  test    rbx, rbx
0x180026960  jz      loc_18002755A
0x180026966  cmp     byte ptr [rbx], 5
0x180026969  jnz     loc_18002755A
0x18002696f  lea     r14, [rsi+70h]
0x180026973  or      [r14], ax
0x180026977  lea     rdx, [rsi+1E0h]
0x18002697e  lea     rcx, [rbp+760h+var_6F0]; this
0x180026982  call    ?Create@CompactCmapRegion@@SAXAEBVOpenTypeCharacterMap@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CompactCmapRegion::Create(OpenTypeCharacterMap const &,std::vector<uchar> &)
0x180026987  nop
0x180026988  lea     rcx, [rbp+760h+var_6F0]
0x18002698c  call    ??1?$FontFragmentPtr@UPostScript@@@@QEAA@XZ; FontFragmentPtr<PostScript>::~FontFragmentPtr<PostScript>(void)
0x180026991  mov     rcx, rsi; this
0x180026994  call    ?ReadFontStyleAttributes@OpenTypeFontFaceBuilder@@AEAAXXZ; OpenTypeFontFaceBuilder::ReadFontStyleAttributes(void)
0x180026999  mov     rax, [rsi+3B8h]
0x1800269a0  mov     ecx, 10h
0x1800269a5  test    rax, rax
0x1800269a8  jz      short loc_1800269B4
0x1800269aa  test    byte ptr [rax+11h], 8
0x1800269ae  jz      short loc_1800269B4
0x1800269b0  or      [r14], cx
0x1800269b4  cmp     [rsi+42Ch], r12d
0x1800269bb  jnz     short loc_180026A2B
0x1800269bd  cmp     [rsi+52Ch], r12d
0x1800269c4  jnz     loc_180027BFE
0x1800269ca  cmp     [rsi+524h], r12d
0x1800269d1  jnz     loc_180027C10
0x1800269d7  cmp     [rsi+514h], r12d
0x1800269de  jnz     loc_180027C22
0x1800269e4  mov     rdx, rbx; union DWRITE_PANOSE *
0x1800269e7  mov     rcx, r15; struct OpenTypeFace *
0x1800269ea  call    ?IsMonospacedFont@@YA_NAEBVOpenTypeFace@@AEBTDWRITE_PANOSE@@@Z; IsMonospacedFont(OpenTypeFace const &,DWRITE_PANOSE const &)
0x1800269ef  mov     ebx, 2
0x1800269f4  test    al, al
0x1800269f6  jz      short loc_1800269FC
0x1800269f8  or      [r14], bx
0x1800269fc  mov     eax, 40h ; '@'
0x180026a01  cmp     [rsi+4D4h], r12d
0x180026a08  jnz     short loc_180026A55
0x180026a0a  cmp     [rsi+4DCh], r12d
0x180026a11  jnz     loc_180027C60
0x180026a17  cmp     [rsi+4E4h], r12d
0x180026a1e  jz      short loc_180026A62
0x180026a20  cmp     [rsi+4E8h], r12d
0x180026a27  jz      short loc_180026A62
0x180026a29  jmp     short loc_180026A5E
0x180026a2b  cmp     [rsi+430h], r12d
0x180026a32  jz      short loc_1800269BD
0x180026a34  cmp     [rsi+434h], r12d
0x180026a3b  jz      short loc_1800269BD
0x180026a3d  cmp     [rsi+438h], r12d
0x180026a44  jz      loc_1800269BD
0x180026a4a  mov     eax, 80h
0x180026a4f  or      [r14], ax
0x180026a53  jmp     short loc_1800269E4
0x180026a55  cmp     [rsi+4D8h], r12d
0x180026a5c  jz      short loc_180026A0A
0x180026a5e  or      [r14], ax
0x180026a62  cmp     [rsi+572h], r12w
0x180026a6a  ja      loc_1800272AD
0x180026a70  cmp     [rsi+504h], r12d
0x180026a77  jnz     loc_1800272BB
0x180026a7d  mov     rdx, r15; struct OpenTypeTables *
0x180026a80  lea     rcx, [rbp+760h+var_7C0]; this
0x180026a84  call    ??0OpenTypeNameTable@@QEAA@AEBVOpenTypeTables@@@Z; OpenTypeNameTable::OpenTypeNameTable(OpenTypeTables const &)
0x180026a89  nop
0x180026a8a  mov     rdx, r15; struct OpenTypeTables *
0x180026a8d  lea     rcx, [rbp+760h+var_728]; this
0x180026a91  call    ??0MetaTable@@QEAA@AEBVOpenTypeTables@@@Z; MetaTable::MetaTable(OpenTypeTables const &)
0x180026a96  nop
0x180026a97  mov     rdx, r15; struct OpenTypeFace *
0x180026a9a  lea     rcx, [rbp+760h+var_650]; this
0x180026aa1  call    ??0FontDifferentiator@@QEAA@AEBVOpenTypeFace@@@Z; FontDifferentiator::FontDifferentiator(OpenTypeFace const &)
0x180026aa6  nop
0x180026aa7  mov     rax, [rsi+2A0h]
0x180026aae  mov     ecx, [rsi+2A8h]
0x180026ab4  mov     qword ptr [rsp+860h+var_800], rax
0x180026ab9  sub     ecx, eax
0x180026abb  mov     dword ptr [rsp+860h+var_800+8], ecx
0x180026abf  mov     rax, [rsi+288h]
0x180026ac6  mov     ecx, [rsi+290h]
0x180026acc  mov     [rbp+760h+var_7E0], rax
0x180026ad0  sub     ecx, eax
0x180026ad2  mov     dword ptr [rbp+760h+var_7D8], ecx
0x180026ad5  lea     r8, [rsp+860h+var_800]; struct FontStringsRegion *
0x180026ada  lea     rdx, [rbp+760h+var_7E0]; struct FontStyleAttributesRegion *
0x180026ade  lea     rcx, [rbp+760h+var_690]; this
0x180026ae5  call    ??0FontStyleAttributes@@QEAA@AEBVFontStyleAttributesRegion@@AEBVFontStringsRegion@@@Z; FontStyleAttributes::FontStyleAttributes(FontStyleAttributesRegion const &,FontStringsRegion const &)
0x180026aea  mov     rcx, [rsi+380h]
0x180026af1  mov     qword ptr [rsp+860h+var_800], rcx
0x180026af6  mov     rax, [rsi+388h]
0x180026afd  sub     rax, rcx
0x180026b00  sar     rax, 3
0x180026b04  lea     rax, [rcx+rax*8]
0x180026b08  mov     qword ptr [rsp+860h+var_800+8], rax
0x180026b0d  lea     r13, [rsi+398h]
0x180026b14  mov     r8, r13
0x180026b17  lea     rdx, [rsp+860h+var_800]
0x180026b1c  lea     rcx, [rbp+760h+var_690]
0x180026b23  call    ?GetCanonicalAxisValues@FontStyleAttributes@@QEBAXV?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE_FIXED@@@@AEAV?$vector@UDWRITE_FONT_AXIS_VALUE_FIXED@@V?$allocator@UDWRITE_FONT_AXIS_VALUE_FIXED@@@std@@@std@@@Z; FontStyleAttributes::GetCanonicalAxisValues(array_ref<DWRITE_FONT_AXIS_VALUE_FIXED const>,std::vector<DWRITE_FONT_AXIS_VALUE_FIXED> &)
0x180026b28  lea     rcx, [rbp+760h+var_770]; void *
0x180026b2c  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026b31  nop
0x180026b32  mov     r8d, 10h; unsigned __int16
0x180026b38  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026b3c  lea     rcx, [rbp+760h+var_770]; this
0x180026b40  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026b45  nop
0x180026b46  lea     rcx, [rbp+760h+var_740]; void *
0x180026b4a  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026b4f  nop
0x180026b50  mov     r8d, 1; unsigned __int16
0x180026b56  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026b5a  lea     rcx, [rbp+760h+var_740]; this
0x180026b5e  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026b63  nop
0x180026b64  lea     rcx, [rsp+860h+var_820]; void *
0x180026b69  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026b6e  nop
0x180026b6f  xor     r8d, r8d; unsigned __int16
0x180026b72  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026b76  lea     rcx, [rsp+860h+var_820]; this
0x180026b7b  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026b80  nop
0x180026b81  lea     r8, [rsp+860h+var_820]
0x180026b86  lea     rdx, [rbp+760h+var_7E0]
0x180026b8a  mov     rcx, rsi
0x180026b8d  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026b92  nop
0x180026b93  lea     rcx, [rsp+860h+var_820]; this
0x180026b98  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026b9d  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026ba0  mov     [rsi+0B0h], eax
0x180026ba6  lea     rcx, [rsp+860h+var_820]; void *
0x180026bab  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026bb0  nop
0x180026bb1  mov     r8d, 5; unsigned __int16
0x180026bb7  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026bbb  lea     rcx, [rsp+860h+var_820]; this
0x180026bc0  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026bc5  nop
0x180026bc6  lea     r8, [rsp+860h+var_820]
0x180026bcb  lea     rdx, [rbp+760h+var_7E0]
0x180026bcf  mov     rcx, rsi
0x180026bd2  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026bd7  nop
0x180026bd8  lea     rcx, [rsp+860h+var_820]; this
0x180026bdd  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026be2  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026be5  mov     [rsi+0B4h], eax
0x180026beb  lea     rcx, [rsp+860h+var_820]; void *
0x180026bf0  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026bf5  nop
0x180026bf6  mov     r8d, 7; unsigned __int16
0x180026bfc  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026c00  lea     rcx, [rsp+860h+var_820]; this
0x180026c05  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026c0a  nop
0x180026c0b  lea     r8, [rsp+860h+var_820]
0x180026c10  lea     rdx, [rbp+760h+var_7E0]
0x180026c14  mov     rcx, rsi
0x180026c17  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026c1c  nop
0x180026c1d  lea     rcx, [rsp+860h+var_820]; this
0x180026c22  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026c27  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026c2a  mov     [rsi+0B8h], eax
0x180026c30  lea     rcx, [rsp+860h+var_820]; void *
0x180026c35  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026c3a  nop
0x180026c3b  mov     r8d, 8; unsigned __int16
0x180026c41  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026c45  lea     rcx, [rsp+860h+var_820]; this
0x180026c4a  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026c4f  nop
0x180026c50  lea     r8, [rsp+860h+var_820]
0x180026c55  lea     rdx, [rbp+760h+var_7E0]
0x180026c59  mov     rcx, rsi
0x180026c5c  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026c61  nop
0x180026c62  lea     rcx, [rsp+860h+var_820]; this
0x180026c67  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026c6c  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026c6f  mov     [rsi+0BCh], eax
0x180026c75  lea     rcx, [rsp+860h+var_820]; void *
0x180026c7a  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026c7f  nop
0x180026c80  mov     r8d, 9; unsigned __int16
0x180026c86  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026c8a  lea     rcx, [rsp+860h+var_820]; this
0x180026c8f  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026c94  nop
0x180026c95  lea     r8, [rsp+860h+var_820]
0x180026c9a  lea     rdx, [rbp+760h+var_7E0]
0x180026c9e  mov     rcx, rsi
0x180026ca1  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026ca6  nop
0x180026ca7  lea     rcx, [rsp+860h+var_820]; this
0x180026cac  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026cb1  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026cb4  mov     [rsi+0C0h], eax
0x180026cba  lea     rcx, [rsp+860h+var_820]; void *
0x180026cbf  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026cc4  nop
0x180026cc5  mov     r8d, 0Ch; unsigned __int16
0x180026ccb  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026ccf  lea     rcx, [rsp+860h+var_820]; this
0x180026cd4  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026cd9  nop
0x180026cda  lea     r8, [rsp+860h+var_820]
0x180026cdf  lea     rdx, [rbp+760h+var_7E0]
0x180026ce3  mov     rcx, rsi
0x180026ce6  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026ceb  nop
0x180026cec  lea     rcx, [rsp+860h+var_820]; this
0x180026cf1  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026cf6  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026cf9  mov     [rsi+0C4h], eax
0x180026cff  lea     rcx, [rsp+860h+var_820]; void *
0x180026d04  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026d09  nop
0x180026d0a  mov     r8d, 0Ah; unsigned __int16
0x180026d10  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026d14  lea     rcx, [rsp+860h+var_820]; this
0x180026d19  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026d1e  nop
0x180026d1f  lea     r8, [rsp+860h+var_820]
0x180026d24  lea     rdx, [rbp+760h+var_7E0]
0x180026d28  mov     rcx, rsi
0x180026d2b  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026d30  nop
0x180026d31  lea     rcx, [rsp+860h+var_820]; this
0x180026d36  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026d3b  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026d3e  mov     [rsi+0C8h], eax
0x180026d44  lea     rcx, [rsp+860h+var_820]; void *
0x180026d49  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026d4e  nop
0x180026d4f  mov     r8d, 0Bh; unsigned __int16
0x180026d55  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026d59  lea     rcx, [rsp+860h+var_820]; this
0x180026d5e  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026d63  nop
0x180026d64  lea     r8, [rsp+860h+var_820]
0x180026d69  lea     rdx, [rbp+760h+var_7E0]
0x180026d6d  mov     rcx, rsi
0x180026d70  call    ?AddNameDictionary@FontFaceRegionBuilder@@IEAA?AV?$BasedRegionPtr@VNameDictionariesRegion@@VNameDictionaryRegion@@I@@AEBVFontNameList@@@Z; FontFaceRegionBuilder::AddNameDictionary(FontNameList const &)
0x180026d75  nop
0x180026d76  lea     rcx, [rsp+860h+var_820]; this
0x180026d7b  call    ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180026d80  mov     eax, dword ptr [rbp+760h+var_7E0]
0x180026d83  mov     [rsi+0CCh], eax
0x180026d89  lea     rcx, [rsp+860h+var_820]; void *
0x180026d8e  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180026d93  nop
0x180026d94  mov     r8d, 0Dh; unsigned __int16
0x180026d9a  lea     rdx, [rbp+760h+var_7C0]; struct OpenTypeNameTable *
0x180026d9e  lea     rcx, [rsp+860h+var_820]; this
0x180026da3  call    ?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z; FontNameList::AppendItems(OpenTypeNameTable const &,ushort)
0x180026da8  nop
0x180026da9  lea     r8, [rsp+860h+var_820]
  ... truncated ...
```
