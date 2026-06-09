# Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(ulong,_EVENT_TRACE *)

- ea: `0x180021250`
- end: `0x180022ccc`
- name: `?AddImageIdEvents@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAU_EVENT_TRACE@@@Z`
- size: `6780`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180025b40`

## callees

- `0x180001108`
- `0x180001b90`
- `0x180001bf8`
- `0x18000265c`
- `0x180002d25`
- `0x180002d31`
- `0x18000a924`
- `0x1800103a8`
- `0x1800104b8`
- `0x180015f9c`
- `0x18001618c`
- `0x18001a030`
- `0x18001e70c`
- `0x180020290`
- `0x180020a14`
- `0x180020ce4`
- `0x180020e38`
- `0x18002102c`
- `0x180021250`
- `0x180023010`
- `0x1800233a0`
- `0x1800239f4`
- `0x180023d60`
- `0x180024494`
- `0x1800249e0`
- `0x180024b54`
- `0x180027358`
- `0x180034a18`
- `0x180035050`
- `0x1800350b0`
- `0x180037040`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18002249e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18002249e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002147f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180021537`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002147f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180021537`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800228dd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800228dd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021d52`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021e84`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021eab`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021d52`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021e84`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180021eab`

## string_xrefs

- `0x1800214be`: `Unable to parse image path: %s`
- `0x1800214e8`: `NULL path in image path.`
- `0x1800217d8`: `\SystemRoot\System32\DriverStore\FileRepository\`
- `0x180021883`: `\\?\GLOBALROOT\DriverStores\BSPDRIVERS\System32\DriverStore\FileRepository\`
- `0x18002194c`: `OS bug workaround - trying alternate path: %s`
- `0x18002289b`: `CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        int a2,
        struct _EVENT_TRACE *a3)
{
  struct _EVENT_TRACE *v3; // r13
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v5; // rdi
  unsigned int v6; // esi
  unsigned __int64 v7; // r8
  unsigned int v8; // r14d
  wchar_t *v9; // rbx
  unsigned int *MofData; // rcx
  __int64 MofLength; // r9
  int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rcx
  const wchar_t **v15; // r12
  __int64 v16; // r14
  wchar_t *v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // r12
  __int64 result; // rax
  __int64 v21; // rbx
  wchar_t *v22; // rax
  const wchar_t *v23; // rcx
  unsigned __int64 v24; // rdx
  __int64 v25; // r12
  unsigned __int64 v26; // rax
  unsigned int *v27; // rax
  union _CVDD **v28; // r15
  int v29; // eax
  int v30; // r8d
  Microsoft::Xbox *v31; // rbx
  int Only2; // eax
  const unsigned __int16 *v33; // r8
  signed int CvDbgInfoFromRegistry; // r14d
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rdi
  void **v38; // rbx
  struct CODEVIEW_INFORMATION_1 *v39; // r14
  void **v40; // r8
  void **v41; // rdx
  HANDLE v42; // rbx
  int v43; // eax
  __int64 v44; // rdx
  void **v45; // r15
  int v46; // eax
  unsigned __int64 v47; // rdx
  struct Microsoft::Windows::Performance::CErrorEvent *v48; // r14
  union _CVDD **v49; // r14
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rdx
  unsigned int v52; // r14d
  void **v53; // rdx
  _DWORD *v54; // rax
  unsigned int v55; // ebx
  unsigned int v56; // r15d
  struct CODEVIEW_INFORMATION_1 **v57; // rcx
  unsigned __int16 *v58; // r14
  unsigned int *v59; // r9
  DWORD FinalPathNameByHandleW; // eax
  DWORD v61; // r8d
  unsigned __int64 v62; // rcx
  _BYTE *v63; // rbx
  unsigned __int64 v64; // rdx
  _BYTE *v65; // rcx
  void **v66; // rdx
  DWORD v67; // eax
  void **v68; // rdx
  __int64 v69; // r8
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v70; // rcx
  int v71; // eax
  const union _CVDD *v72; // rdx
  union _CVDD *v73; // rcx
  const struct CODEVIEW_INFORMATION_1 *v74; // r8
  unsigned int v75; // r14d
  unsigned int v76; // r9d
  unsigned int v77; // r14d
  int v78; // ecx
  __int64 v79; // rax
  int v80; // esp
  Microsoft::Windows::Performance::CCvDDCache *v81; // r15
  unsigned int v82; // eax
  unsigned int i; // edx
  __int64 v84; // rcx
  unsigned int v85; // eax
  Microsoft::Windows::Performance::CCvDDCache *v86; // rdx
  char v87; // al
  unsigned __int64 v88; // rax
  int v89; // eax
  unsigned int v90; // ecx
  unsigned int v91; // ecx
  int v92; // eax
  int EmbeddedPdb; // eax
  int v94; // ecx
  HRESULT v95; // edx
  GUID *p_pguid; // r12
  int v97; // r15d
  int v98; // eax
  int v99; // eax
  unsigned int v100; // [rsp+20h] [rbp-8F8h]
  unsigned int v101; // [rsp+20h] [rbp-8F8h]
  union _CVDD **v102; // [rsp+20h] [rbp-8F8h]
  unsigned int **v103; // [rsp+28h] [rbp-8F0h]
  struct CODEVIEW_INFORMATION_1 **v104; // [rsp+30h] [rbp-8E8h]
  union _CVDD *v105; // [rsp+38h] [rbp-8E0h]
  struct CODEVIEW_INFORMATION_1 *v106; // [rsp+40h] [rbp-8D8h]
  struct EMBEDDED_PDB_INFORMATION *v107; // [rsp+48h] [rbp-8D0h]
  bool *v108; // [rsp+50h] [rbp-8C8h]
  unsigned __int16 *v109; // [rsp+58h] [rbp-8C0h]
  unsigned int v110; // [rsp+60h] [rbp-8B8h]
  bool *v111; // [rsp+60h] [rbp-8B8h]
  bool *v112; // [rsp+60h] [rbp-8B8h]
  unsigned int v113[2]; // [rsp+68h] [rbp-8B0h]
  __int64 MappedAsImage; // [rsp+70h] [rbp-8A8h]
  struct EMBEDDED_PDB_INFORMATION *v115; // [rsp+78h] [rbp-8A0h]
  struct XPerfCore::IErrorMessage *v116; // [rsp+90h] [rbp-888h] BYREF
  unsigned int v117; // [rsp+98h] [rbp-880h]
  unsigned int v118; // [rsp+9Ch] [rbp-87Ch] BYREF
  Microsoft::Xbox *v119; // [rsp+A0h] [rbp-878h] BYREF
  unsigned int v120; // [rsp+A8h] [rbp-870h] BYREF
  __int64 v121; // [rsp+B0h] [rbp-868h] BYREF
  unsigned __int64 v122; // [rsp+B8h] [rbp-860h]
  __int64 v123; // [rsp+C0h] [rbp-858h] BYREF
  wchar_t *String1; // [rsp+C8h] [rbp-850h]
  struct CODEVIEW_INFORMATION_1 *v125; // [rsp+D8h] [rbp-840h] BYREF
  unsigned int *v126; // [rsp+E0h] [rbp-838h] BYREF
  union _CVDD *v127; // [rsp+E8h] [rbp-830h] BYREF
  struct Microsoft::Windows::Performance::CErrorEvent *v128; // [rsp+F0h] [rbp-828h]
  struct CODEVIEW_INFORMATION_1 **v129; // [rsp+F8h] [rbp-820h]
  void *v130; // [rsp+100h] [rbp-818h]
  unsigned int *v131; // [rsp+108h] [rbp-810h]
  union _CVDD *v132; // [rsp+110h] [rbp-808h]
  Microsoft::Windows::Performance::CCvDDCache *v133; // [rsp+118h] [rbp-800h]
  union _CVDD **v134; // [rsp+120h] [rbp-7F8h]
  void *v135; // [rsp+128h] [rbp-7F0h]
  __int128 v136; // [rsp+130h] [rbp-7E8h] BYREF
  __int64 v137; // [rsp+140h] [rbp-7D8h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v138; // [rsp+148h] [rbp-7D0h]
  HANDLE hFile[2]; // [rsp+150h] [rbp-7C8h] BYREF
  unsigned __int16 *v140; // [rsp+160h] [rbp-7B8h]
  void *v141; // [rsp+168h] [rbp-7B0h]
  struct _EVENT_TRACE *v142; // [rsp+170h] [rbp-7A8h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v143; // [rsp+178h] [rbp-7A0h]
  unsigned __int64 v144; // [rsp+180h] [rbp-798h]
  ATL::CAtlException *v145; // [rsp+188h] [rbp-790h] BYREF
  void *Src[2]; // [rsp+190h] [rbp-788h] BYREF
  unsigned __int64 v147; // [rsp+1A0h] [rbp-778h]
  unsigned __int64 v148; // [rsp+1A8h] [rbp-770h]
  GUID pguid; // [rsp+1B0h] [rbp-768h] BYREF
  unsigned __int64 v150; // [rsp+1C0h] [rbp-758h] BYREF
  unsigned __int64 v151; // [rsp+1C8h] [rbp-750h] BYREF
  unsigned int Data1; // [rsp+1D0h] [rbp-748h] BYREF
  unsigned int v153; // [rsp+1D4h] [rbp-744h]
  unsigned __int16 v154[4]; // [rsp+1D8h] [rbp-740h] BYREF
  int v155; // [rsp+1E0h] [rbp-738h]
  __int128 v156; // [rsp+800h] [rbp-118h] BYREF
  __m256i v157; // [rsp+810h] [rbp-108h]
  __int128 v158; // [rsp+830h] [rbp-E8h]
  __int128 v159; // [rsp+840h] [rbp-D8h]
  __int64 v160; // [rsp+850h] [rbp-C8h]
  int v161; // [rsp+858h] [rbp-C0h]
  int v162; // [rsp+85Ch] [rbp-BCh]
  wchar_t String2[56]; // [rsp+860h] [rbp-B8h] BYREF

  v3 = a3;
  v142 = a3;
  v5 = this;
  v138 = this;
  v143 = this;
  v130 = a3;
  v6 = 0;
  v121 = 0;
  v7 = 0;
  v122 = 0;
  v8 = 0;
  v123 = 0;
  v9 = 0;
  String1 = 0;
  MofData = (unsigned int *)v3->MofData;
  MofLength = v3->MofLength;
  if ( !v3->Header.Class.Version )
  {
LABEL_230:
    if ( (**((unsigned __int8 (__fastcall ***)(__int64, const wchar_t *, unsigned __int64, __int64))v5 + 47))(
           (__int64)v5 + 376,
           L"Failed to parse image event.",
           v7,
           MofLength) )
    {
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
    }
    return 1;
  }
  if ( v3->Header.Class.Version == 1 )
  {
    if ( a2 != 4 )
      goto LABEL_230;
    if ( (unsigned int)MofLength < 0x10 )
      goto LABEL_8;
    HIDWORD(v121) = MofData[1];
    v9 = (wchar_t *)(MofData + 3);
    goto LABEL_19;
  }
  if ( (unsigned int)v3->Header.Class.Version - 2 > 1 )
    goto LABEL_230;
  if ( *((_DWORD *)v5 + 8) < 0xBu )
  {
    if ( a2 != 4 )
      goto LABEL_6;
    if ( (unsigned int)MofLength >= 0x2C )
    {
      v9 = (wchar_t *)(MofData + 10);
      goto LABEL_12;
    }
LABEL_8:
    v12 = -2147024883;
    v13 = 0;
    goto LABEL_21;
  }
  if ( a2 == 4 )
  {
    if ( (unsigned int)MofLength >= 0x30 )
    {
      v9 = (wchar_t *)(MofData + 11);
LABEL_12:
      HIDWORD(v121) = MofData[1];
      v8 = MofData[3];
      LODWORD(v123) = v8;
      HIDWORD(v123) = MofData[4];
LABEL_19:
      v13 = MofData[2];
      v7 = *MofData;
      goto LABEL_20;
    }
    goto LABEL_8;
  }
LABEL_6:
  if ( a2 != 8 )
    goto LABEL_230;
  if ( (unsigned int)MofLength < 0x40 )
    goto LABEL_8;
  v13 = MofData[4];
  HIDWORD(v121) = MofData[2];
  v7 = *(_QWORD *)MofData;
  v9 = (wchar_t *)(MofData + 14);
  v8 = MofData[5];
  LODWORD(v123) = v8;
  HIDWORD(v123) = MofData[6];
LABEL_20:
  v12 = 0;
  String1 = v9;
  v122 = v7;
  LODWORD(v121) = v13;
LABEL_21:
  if ( v12 < 0 )
    goto LABEL_230;
  if ( *((_QWORD *)v5 + 5) == v3->Header.TimeStamp.QuadPart && *((_DWORD *)v5 + 12) == v13 && *((_QWORD *)v5 + 7) == v7 )
    return 1;
  if ( !*((_BYTE *)v5 + 176) )
  {
    try
    {
      Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize((Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 64));
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
    catch ( ATL::CAtlException *v145 )
    {
      if ( *(_DWORD *)v145 == -2147024882 )
        return 2147942414LL;
      *((_BYTE *)v143 + 200) = 1;
      return 1;
    }
  }
  if ( (unsigned __int8)Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
                          (char *)v5 + 64,
                          v9,
                          (char *)v5 + 192) )
  {
    v15 = (const wchar_t **)((char *)v5 + 192);
  }
  else
  {
    v14 = *((_QWORD *)v5 + 23);
    if ( !v14
      || (v15 = (const wchar_t **)((char *)v5 + 192),
          !(unsigned __int8)Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
                              v14,
                              v9,
                              (char *)v5 + 192)) )
    {
      if ( v9 )
      {
        v16 = 0;
        if ( !*((_BYTE *)v5 + 201) )
        {
          v17 = wcsrchr(v9, 0x5Cu);
          if ( v17 )
          {
            v18 = v17 - v9 + 1;
            v19 = -1;
            do
              ++v19;
            while ( v9[v19] );
            v16 = v18 & -(__int64)(v18 < v19);
          }
        }
        if ( !(**((unsigned __int8 (***)(__int64, const wchar_t *, ...))v5 + 47))(
                (__int64)v5 + 376,
                L"Unable to parse image path: %s",
                &v9[v16]) )
          return 1;
      }
      else if ( !(**((unsigned __int8 (__fastcall ***)(__int64, const wchar_t *))v5 + 47))(
                   (__int64)v5 + 376,
                   L"NULL path in image path.") )
      {
        return 1;
      }
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
      return 1;
    }
  }
  try
  {
    v132 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 201);
    if ( *((_BYTE *)v5 + 201) )
    {
      (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))((__int64)v5 + 376, L"%s [%s] failure: ", *v15, v9);
      v25 = -1;
    }
    else
    {
      v21 = 0;
      v22 = wcsrchr(*v15, 0x5Cu);
      if ( v22 )
      {
        v23 = *v15;
        v24 = v22 - *v15 + 1;
        v25 = -1;
        v26 = -1;
        do
          ++v26;
        while ( v23[v26] );
        v21 = v24 & -(__int64)(v24 < v26);
      }
      else
      {
        v25 = -1;
      }
      (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))(
        (__int64)v5 + 376,
        L"%s failure: ",
        *((_QWORD *)v5 + 24) + 2 * v21);
    }
    v135 = v132;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  memset_0(&v150, 0, 0x640u);
  if ( a2 == 4 )
    v27 = &Data1;
  else
    v27 = (unsigned int *)v154;
  v131 = v27;
  HIDWORD(v116) = 0;
  v127 = 0;
  v126 = 0;
  v125 = 0;
  v136 = 0;
  v137 = 0;
  BYTE1(v116) = 0;
  v133 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 208);
  v28 = (union _CVDD **)((char *)v5 + 192);
  v29 = Microsoft::Windows::Performance::CCvDDCache::Find(
          (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 208),
          *((const unsigned __int16 **)v5 + 24),
          v8,
          (unsigned int *)&v116 + 1,
          &v127,
          (const unsigned int **)&v126,
          &v125,
          (unsigned int *)&v123 + 1,
          (unsigned int *)&v121 + 1,
          (struct EMBEDDED_PDB_INFORMATION *)&v136,
          (bool *)&v116 + 1,
          (unsigned __int16 *)v27,
          v110);
  v30 = v29;
  if ( v29 >= 0 )
  {
    v56 = HIDWORD(v123);
    v77 = v121;
    v117 = HIDWORD(v116);
    v132 = v127;
    v127 = (union _CVDD *)v126;
    v126 = (unsigned int *)v125;
    goto LABEL_153;
  }
  if ( v29 != -2147023728 )
  {
    if ( v29 != -2147467259 && v29 != -2147024774 )
    {
      result = 2147942414LL;
      if ( v30 != -2147024882 )
      {
        (*(void (**)(__int64, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
          (__int64)v5 + 376,
          L"unexpected caching error: %x");
        Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
        result = 1;
        *((_BYTE *)v5 + 200) = 1;
      }
      return result;
    }
    return 1;
  }
  v117 = *((_DWORD *)v5 + 92);
  HIDWORD(v116) = v117;
  v128 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 344);
  if ( !*((_QWORD *)v5 + 43) )
    return 2147549183LL;
  v134 = (union _CVDD **)((char *)v5 + 352);
  if ( !*((_QWORD *)v5 + 44) )
    return 2147549183LL;
  v129 = (struct CODEVIEW_INFORMATION_1 **)((char *)v5 + 360);
  if ( !*((_QWORD *)v5 + 45) )
    return 2147549183LL;
  *(_QWORD *)&pguid.Data1 = (char *)v5 + 208;
  v126 = (unsigned int *)((char *)v5 + 352);
  LOBYTE(v116) = Performance::COSVersionInfo::IsWin8AndUp();
  *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm);
  v140 = 0;
  v141 = 0;
  v31 = *v28;
  v119 = v31;
  v127 = v31;
  v125 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376);
  Only2 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
            (XPerfCore::CFileMapping *)hFile,
            (const unsigned __int16 *)v31,
            (bool)v116,
            (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
  CvDbgInfoFromRegistry = Only2;
  if ( Only2 >= 0 )
    goto LABEL_78;
  if ( Only2 != -2147024893
    || (wcscpy(String2, L"\\SystemRoot\\System32\\DriverStore\\FileRepository\\"), wcsncmp_0(String1, String2, 0x30u)) )
  {
LABEL_128:
    v45 = (void **)v129;
    goto LABEL_87;
  }
  try
  {
    *(_OWORD *)Src = 0;
    v147 = 0;
    v148 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      Src,
      L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS\\System32\\DriverStore\\FileRepository\\",
      75);
    v35 = -1;
    do
      ++v35;
    while ( String1[v35 + 48] );
    v36 = v147;
    if ( v35 > v148 - v147 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        Src,
        v35);
    }
    else
    {
      v37 = v147 + v35;
      v147 += v35;
      v38 = Src;
      if ( v148 > 7 )
        v38 = (void **)Src[0];
      memmove_0((char *)v38 + 2 * v36, String1 + 48, 2 * v35);
      *((_WORD *)v38 + v37) = 0;
      v5 = v138;
      v31 = v119;
    }
    v39 = v125;
    v40 = Src;
    if ( v148 > 7 )
      v40 = (void **)Src[0];
    (*(void (**)(struct CODEVIEW_INFORMATION_1 *, const wchar_t *, ...))(*(_QWORD *)v125 + 8LL))(
      v125,
      L"OS bug workaround - trying alternate path: %s",
      v40);
    v41 = Src;
    if ( v148 > 7 )
      v41 = (void **)Src[0];
    CvDbgInfoFromRegistry = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
                              (XPerfCore::CFileMapping *)hFile,
                              (const unsigned __int16 *)v41,
                              (bool)v116,
                              v39);
    if ( CvDbgInfoFromRegistry < 0 )
      goto LABEL_76;
    v42 = hFile[0];
    if ( hFile[0] == (HANDLE)-1LL )
    {
      LOWORD(v43) = 87;
LABEL_75:
      CvDbgInfoFromRegistry = (unsigned __int16)v43 | 0x80070000;
      v31 = v119;
LABEL_76:
      v119 = v31;
      std::wstring::~wstring(Src);
      goto LABEL_251;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile[0], 0, 0, 0);
    v61 = FinalPathNameByHandleW;
    v118 = FinalPathNameByHandleW;
    v144 = v147;
    v62 = v148;
    if ( v147 <= FinalPathNameByHandleW && v148 != FinalPathNameByHandleW )
    {
      if ( v148 < FinalPathNameByHandleW )
      {
        std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(Src);
        v147 = v144;
        v62 = v148;
LABEL_110:
        v61 = v118;
        goto LABEL_111;
      }
      if ( FinalPathNameByHandleW <= 7uLL && v148 > 7 )
      {
        v63 = Src[0];
        memcpy_0(Src, Src[0], 2 * v147 + 2);
        v64 = 2 * v148 + 2;
        if ( v64 < 0x1000 )
        {
          v65 = v63;
        }
        else
        {
          v65 = (_BYTE *)*((_QWORD *)v63 - 1);
          if ( (unsigned __int64)(v63 - v65 - 8) > 0x1F )
            __fastfail(5u);
          v64 = 2 * v148 + 41;
        }
        operator delete(v65, v64);
        v62 = 7;
        v148 = 7;
        v42 = hFile[0];
        goto LABEL_110;
      }
    }
LABEL_111:
    v66 = Src;
    if ( v62 > 7 )
      v66 = (void **)Src[0];
    if ( v42 == (HANDLE)-1LL )
    {
      v43 = 87;
    }
    else
    {
      if ( v66 && v61 )
      {
        v67 = GetFinalPathNameByHandleW(v42, (LPWSTR)v66, v61, 0);
        v43 = v67 >= v118 ? 0x7A : 0;
      }
      else
      {
        GetFinalPathNameByHandleW(v42, 0, 0, 0);
        v43 = 122;
      }
      v62 = v148;
    }
    if ( v43 )
      goto LABEL_75;
    if ( v62 <= 7 )
    {
      v68 = Src;
    }
    else
    {
      v68 = (void **)Src[0];
      if ( !Src[0] )
      {
        v69 = 0;
LABEL_127:
        ATL::CSimpleStringT<unsigned short,0>::SetString(v28, v68, v69);
        v31 = *v28;
        v127 = *v28;
        goto LABEL_76;
      }
    }
    v69 = -1;
    do
      ++v69;
    while ( *((_WORD *)v68 + v69) );
    goto LABEL_127;
  }
  catch ( std::bad_alloc )
  {
    v6 = 0;
    v25 = -1;
    CvDbgInfoFromRegistry = -2147024882;
    v117 = HIDWORD(v116);
    v119 = v127;
    v133 = *(Microsoft::Windows::Performance::CCvDDCache **)&pguid.Data1;
    v132 = (union _CVDD *)v135;
    v5 = v143;
    v138 = v143;
    v3 = (struct _EVENT_TRACE *)v130;
    v142 = (struct _EVENT_TRACE *)v130;
    goto LABEL_128;
  }
LABEL_251:
  if ( CvDbgInfoFromRegistry < 0 )
    goto LABEL_128;
LABEL_78:
  v44 = 0xFFFFFFFFLL;
  if ( (unsigned __int64)v141 < 0xFFFFFFFF )
    v44 = (unsigned int)v141;
  v130 = (void *)v44;
  LODWORD(v111) = 780;
  v45 = (void **)v129;
  v46 = XPerf::Internal::CvDbgInfoFromImage2(
          v31,
          v140,
          (void *)(unsigned int)v44,
          v123,
          v100,
          (unsigned int *)&v116 + 1,
          *(union _CVDD **)v128,
          *v134,
          *v129,
          (struct CODEVIEW_INFORMATION_1 *)((char *)&v123 + 4),
          (unsigned int *)&v121 + 1,
          v131,
          (unsigned __int16 *)v111,
          (unsigned int)&v120,
          (BOOLEAN)v116,
          (struct EMBEDDED_PDB_INFORMATION *)&v136,
          (struct EMBEDDED_PDB_INFORMATION *)((char *)&v116 + 1),
          (bool *)v125,
          v116);
  CvDbgInfoFromRegistry = v46;
  if ( v46 < 0 )
  {
    if ( v46 != -2146893023 )
      goto LABEL_86;
    *((_DWORD *)v5 + 92) = 0;
    v48 = v128;
    operator delete(*(void **)v128, v47);
    *(_QWORD *)v48 = 0;
    v49 = v134;
    operator delete(*v134, v50);
    *v49 = 0;
    operator delete(*v45, v51);
    *v45 = 0;
    v52 = HIDWORD(v116);
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v128, HIDWORD(v116))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v134, v52)
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(v45, v52) )
    {
      v55 = -2147024882;
      goto LABEL_143;
    }
    *((_DWORD *)v5 + 92) = HIDWORD(v116);
    LODWORD(v112) = 780;
    CvDbgInfoFromRegistry = XPerf::Internal::CvDbgInfoFromImage2(
                              v31,
                              v140,
                              (void *)(unsigned int)v130,
                              v123,
                              v101,
                              (unsigned int *)&v116 + 1,
                              *(union _CVDD **)v128,
                              *v134,
                              (struct CODEVIEW_INFORMATION_1 *)*v45,
                              (struct CODEVIEW_INFORMATION_1 *)((char *)&v123 + 4),
                              (unsigned int *)&v121 + 1,
                              v131,
                              (unsigned __int16 *)v112,
                              (unsigned int)&v120,
                              (BOOLEAN)v116,
                              (struct EMBEDDED_PDB_INFORMATION *)&v136,
                              (struct EMBEDDED_PDB_INFORMATION *)((char *)&v116 + 1),
                              (bool *)v125,
                              v116);
    if ( CvDbgInfoFromRegistry < 0 )
    {
LABEL_86:
      v117 = HIDWORD(v116);
LABEL_87:
      if ( !*((_BYTE *)v5 + 202) )
      {
        v55 = 1;
        v56 = HIDWORD(v123);
        v59 = v126;
LABEL_133:
        if ( CvDbgInfoFromRegistry < 0 )
        {
          Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
          Microsoft::Windows::Performance::CCvDDCache::AddFailure(v133, (const unsigned __int16 *)v119, v123);
          goto LABEL_143;
        }
        v70 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v117;
        goto LABEL_137;
      }
      v53 = (void **)v128;
      if ( *(_QWORD *)v128 )
      {
        if ( *v134 )
        {
          v54 = *v45;
          if ( *v45 )
          {
            v55 = 1;
            v117 = 1;
            v56 = HIDWORD(v123);
            *v54 = HIDWORD(v123);
            v57 = v129;
            *((_WORD *)*v129 + 2) = 0;
            *((_WORD *)*v57 + 3) = 0;
            v135 = *v53;
            if ( !byte_18004B24A
              || (byte_18004B24A = 0,
                  CvDbgInfoFromRegistry = Microsoft::Xbox::LoadCvDbgInfoFromRegistry(
                                            v125,
                                            (struct Microsoft::Windows::Performance::CErrorEvent *)v53),
                  CvDbgInfoFromRegistry >= 0) )
            {
              v58 = Microsoft::Xbox::pdbRecords;
              v130 = qword_18004D700;
              if ( Microsoft::Xbox::pdbRecords == qword_18004D700 )
              {
LABEL_96:
                CvDbgInfoFromRegistry = -2147467259;
              }
              else
              {
                while ( !(unsigned int)Microsoft::Xbox::StringEndsWithW(v119, v58, v33) )
                {
                  v58 += 1048;
                  if ( v58 == v130 )
                    goto LABEL_96;
                }
                memcpy_0(v135, v58 + 260, 0x628u);
                CvDbgInfoFromRegistry = 0;
              }
            }
            v59 = v126;
            **(_DWORD **)v126 = 1576;
            goto LABEL_133;
          }
        }
      }
      v55 = -2147418113;
LABEL_143:
      XPerfCore::CFileMapping::~CFileMapping((XPerfCore::CFileMapping *)hFile);
      return v55;
    }
  }
  v56 = HIDWORD(v123);
  v70 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)HIDWORD(v116);
  v117 = HIDWORD(v116);
  v59 = v126;
LABEL_137:
  if ( !*(_BYTE *)v132 )
  {
    v71 = Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
            v70,
            (unsigned int)v70,
            *(union _CVDD **)v128,
            *(unsigned int **)v59);
    if ( v71 < 0 )
      goto LABEL_142;
  }
  v72 = *(const union _CVDD **)v128;
  v132 = *(union _CVDD **)v128;
  v73 = *(union _CVDD **)v126;
  v127 = *(union _CVDD **)v126;
  v74 = *v129;
  v126 = (unsigned int *)*v129;
  if ( (*((_DWORD *)v5 + 93) & 0x100) == 0 )
  {
    v136 = 0;
    v137 = 0;
  }
  LOBYTE(v116) = 0;
  v75 = HIDWORD(v121);
  v71 = Microsoft::Windows::Performance::CCvDDCache::Add(
          v133,
          (const unsigned __int16 *)v119,
          v123,
          v117,
          v72,
          (const unsigned int *)v73,
          v74,
          v56,
          HIDWORD(v121),
          (struct EMBEDDED_PDB_INFORMATION *)&v136,
          SBYTE1(v116),
          (const unsigned __int16 *)v131,
          (bool *)&v116);
  if ( v71 < 0 )
  {
LABEL_142:
    v55 = v71;
    goto LABEL_143;
  }
  if ( (_BYTE)v116 )
  {
    v76 = v75;
    v77 = v121;
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddFileVersionEvent(
      v5,
      v3,
      v121,
      v76,
      v56,
      (const unsigned __int16 *)v131,
      (const unsigned __int16 *)v119,
      (struct XPerfCore::CFileMapping *)hFile);
  }
  else
  {
    v77 = v121;
  }
  XPerfCore::CFileMapping::~CFileMapping((XPerfCore::CFileMapping *)hFile);
LABEL_153:
  if ( a2 == 4 )
  {
    v78 = v122;
    v150 = __PAIR64__(HIDWORD(v121), v122);
    v151 = __PAIR64__(v56, v77);
  }
  else
  {
    if ( a2 != 8 )
      return 2147549183LL;
    v78 = v122;
    v150 = v122;
    v151 = HIDWORD(v121);
    Data1 = v77;
    v153 = v56;
  }
  HIDWORD(v116) = v78;
  v79 = -1;
  do
    ++v79;
  while ( *((_WORD *)v131 + v79) );
  v156 = *(_OWORD *)&v3->Header.Size;
  v157 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
  v158 = *(_OWORD *)&v3->InstanceId;
  v159 = *(_OWORD *)v3->ParentGuid.Data4;
  HIDWORD(v160) = HIDWORD(*(_QWORD *)&v3->MofLength);
  *(_OWORD *)&v157.m256i_u64[1] = ImageIdGuid;
  DWORD1(v156) = 0x20000;
  HIDWORD(v156) = v77;
  *((_QWORD *)&v159 + 1) = &v150;
  LODWORD(v160) = (_DWORD)v131 + 2 + 2 * v79 - (v80 + 448);
  result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
             *((_QWORD *)v5 + 2),
             &v156,
             0,
             0);
  if ( (int)result < 0 )
    return result;
  v81 = 0;
  v125 = 0;
  v82 = 0;
  LODWORD(v119) = 0;
  for ( i = v117; v82 < i; LODWORD(v119) = v82 )
  {
    v84 = v82;
    v85 = *((_DWORD *)v127 + v82);
    v118 = v85;
    if ( v85 >= 4 )
    {
      if ( v85 > 0x628 )
        return 2147549183LL;
      v86 = (union _CVDD *)((char *)v132 + 1576 * v84);
      v133 = v86;
      if ( *(_DWORD *)v86 )
      {
        switch ( *(_DWORD *)v86 )
        {
          case 1:
            v87 = 33;
            break;
          case 2:
            v87 = 34;
            break;
          case 3:
            v87 = 37;
            break;
          case 0x3031424E:
            v87 = 35;
            break;
          case 0x53445352:
            v87 = 36;
            break;
          default:
            return 1;
        }
      }
      else
      {
        v87 = 32;
      }
      LOBYTE(v116) = v87;
      if ( (_DWORD)v136 )
      {
        if ( v87 == 36 )
        {
          v88 = -1;
          do
            ++v88;
          while ( *((_BYTE *)v86 + v88 + 24) );
          if ( v88 <= 7 || (v89 = _o__stricmp((char *)v86 + v88 + 17, ".ni.pdb"), v86 = v133, v89) )
          {
            v81 = v86;
            v125 = v86;
          }
        }
      }
      if ( a2 == 4 )
      {
        memcpy_0((char *)&v150 + 4, v86, v118);
        v150 = __PAIR64__(v77, HIDWORD(v116));
        v90 = v118 + 4;
      }
      else
      {
        if ( a2 != 8 )
          return 2147549183LL;
        memcpy_0(&v151, v86, v118);
        v150 = v122;
        LODWORD(v151) = v77;
        v90 = v118 + 8;
      }
      v156 = *(_OWORD *)&v3->Header.Size;
      v157 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
      v158 = *(_OWORD *)&v3->InstanceId;
      v159 = *(_OWORD *)v3->ParentGuid.Data4;
      HIDWORD(v160) = HIDWORD(*(_QWORD *)&v3->MofLength);
      *(_OWORD *)&v157.m256i_u64[1] = ImageIdGuid;
      DWORD1(v156) = (unsigned __int8)v116 | 0x20000;
      HIDWORD(v156) = v77;
      *((_QWORD *)&v159 + 1) = &v150;
      LODWORD(v160) = v90;
      result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                 *((_QWORD *)v5 + 2),
                 &v156,
                 0,
                 0);
      if ( (int)result < 0 )
        return result;
      i = v117;
    }
    v82 = (_DWORD)v119 + 1;
  }
  v91 = 0;
  LODWORD(v119) = 0;
  if ( i )
  {
    v92 = a2;
    do
    {
      if ( v92 == 4 )
      {
        v150 = __PAIR64__(v77, HIDWORD(v116));
      }
      else
      {
        if ( v92 != 8 )
          return 2147549183LL;
        v150 = v122;
        LODWORD(v151) = v77;
      }
      if ( v126[2 * v91] )
      {
        HIDWORD(v151) = v126[2 * v91];
        Data1 = v126[2 * v91 + 1];
        *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
        *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
        *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
        *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
        *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
        *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
        *(_OWORD *)&String2[12] = ImageIdGuid;
        *(_DWORD *)&String2[2] = 131110;
        *(_DWORD *)&String2[6] = v77;
        *(_QWORD *)&String2[36] = &v150;
        *(_DWORD *)&String2[40] = 20;
        result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                   *((_QWORD *)v5 + 2),
                   String2,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
        v92 = a2;
        v91 = (unsigned int)v119;
      }
      LODWORD(v119) = ++v91;
    }
    while ( v91 < v117 );
  }
  if ( (_DWORD)v136 )
  {
    pguid = 0;
    if ( v81 )
    {
      try
      {
        p_pguid = (GUID *)((char *)v81 + 4);
        v130 = (char *)v81 + 4;
        v135 = (char *)v81 + 24;
        EmbeddedPdb = Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
                        v5,
                        (const char *)v81 + 24,
                        (const struct _GUID *)((char *)v81 + 4),
                        *((_DWORD *)v81 + 5),
                        (DWORD *)&v136);
      }
      catch ( std::bad_alloc )
      {
        return 2147942414LL;
      }
      LODWORD(v119) = EmbeddedPdb;
      if ( EmbeddedPdb < 0 )
      {
        LODWORD(v115) = *((_DWORD *)v125 + 5);
        LODWORD(MappedAsImage) = *((unsigned __int8 *)v81 + 19);
        v113[0] = *((unsigned __int8 *)v81 + 18);
        LODWORD(v111) = *((unsigned __int8 *)v81 + 17);
        LODWORD(v109) = *((unsigned __int8 *)v81 + 16);
        LODWORD(v108) = *((unsigned __int8 *)v81 + 15);
        LODWORD(v107) = *((unsigned __int8 *)v81 + 14);
        LODWORD(v106) = *((unsigned __int8 *)v81 + 13);
        LODWORD(v105) = *((unsigned __int8 *)v81 + 12);
        LODWORD(v104) = *((unsigned __int16 *)v81 + 5);
        LODWORD(v103) = *((unsigned __int16 *)v81 + 4);
        LODWORD(v102) = *(_DWORD *)v130;
        (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))(
          (__int64)v5 + 376,
          L"CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d",
          (unsigned int)v119,
          v135,
          v102,
          v103,
          v104,
          v105,
          v106,
          v107,
          v108,
          v109,
          v111,
          *(_QWORD *)v113,
          MappedAsImage,
          v115);
        Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v138, v142);
        return 1;
      }
      v94 = *((_DWORD *)v81 + 5);
      goto LABEL_213;
    }
    v95 = CoCreateGuid(&pguid);
    if ( v95 >= 0 )
    {
      v94 = 1;
      p_pguid = &pguid;
LABEL_213:
      v97 = a2;
      if ( a2 == 4 )
      {
        v150 = __PAIR64__(v77, HIDWORD(v116));
LABEL_217:
        HIDWORD(v151) = v137;
        Data1 = p_pguid->Data1;
        v153 = *(_DWORD *)&p_pguid->Data2;
        *(_QWORD *)v154 = *(_QWORD *)p_pguid->Data4;
        v155 = v94;
        *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
        *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
        *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
        *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
        *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
        *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
        *(_OWORD *)&String2[12] = ImageIdGuid;
        *(_DWORD *)&String2[2] = 65575;
        *(_DWORD *)&String2[6] = v77;
        *(_QWORD *)&String2[36] = &v150;
        wcscpy(&String2[40], L"$");
        result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                   *((_QWORD *)v5 + 2),
                   String2,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
        goto LABEL_220;
      }
      if ( a2 == 8 )
      {
        v150 = v122;
        LODWORD(v151) = v77;
        goto LABEL_217;
      }
      return 2147549183LL;
    }
    if ( (unsigned int)dword_18004AE58 > 2
      && (qword_18004AE68 & 0x20000000) != 0
      && (qword_18004AE70 & 0x20000000) == qword_18004AE70 )
    {
      LODWORD(v119) = v95;
      v118 = 1441;
      do
        ++v25;
      while ( *(_BYTE *)(v25 + 24) );
      v160 = 24;
      v161 = v25 + 1;
      v162 = 0;
      *(_QWORD *)&v159 = &v119;
      *((_QWORD *)&v159 + 1) = 4;
      *(_QWORD *)&v158 = &v118;
      *((_QWORD *)&v158 + 1) = 4;
      v157.m256i_i64[2] = (__int64)"AddImageIdEvents";
      v157.m256i_i64[3] = 17;
      tlgWriteTransfer_EventWriteTransfer(&dword_18004AE58, &unk_1800425C0, 0, 0, 6, &v156);
    }
    return 1;
  }
  v97 = a2;
LABEL_220:
  if ( !BYTE1(v116) )
    return 0;
  if ( v97 == 4 )
  {
    v150 = __PAIR64__(v77, HIDWORD(v116));
    v98 = 8;
  }
  else
  {
    if ( v97 != 8 )
      return 2147549183LL;
    v150 = v122;
    LODWORD(v151) = v77;
    v98 = 12;
  }
  *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
  *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
  *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
  *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
  *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
  *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
  *(_OWORD *)&String2[12] = ImageIdGuid;
  *(_DWORD *)&String2[2] = 65576;
  *(_DWORD *)&String2[6] = v77;
  *(_QWORD *)&String2[36] = &v150;
  *(_DWORD *)&String2[40] = v98;
  v99 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
          *((_QWORD *)v5 + 2),
          String2,
          0,
          0);
  if ( v99 < 0 )
    return (unsigned int)v99;
  return v6;
}

```

## disassembly

```asm
0x180021250  mov     [rsp+arg_8], edx
0x180021254  mov     r11, rsp
0x180021257  push    rbx
0x180021258  push    rsi
0x180021259  push    rdi
0x18002125a  push    r12
0x18002125c  push    r13
0x18002125e  push    r14
0x180021260  push    r15
0x180021262  sub     rsp, 8E0h
0x180021269  mov     rax, cs:__security_cookie
0x180021270  xor     rax, rsp
0x180021273  mov     [rsp+918h+var_48], rax
0x18002127b  mov     r13, r8
0x18002127e  mov     [rsp+918h+var_7A8], r8
0x180021286  mov     r15d, edx
0x180021289  mov     rdi, rcx
0x18002128c  mov     [rsp+918h+var_7D0], rcx
0x180021294  mov     [rsp+918h+var_7A0], rcx
0x18002129c  mov     [rsp+918h+var_818], r8
0x1800212a4  xor     esi, esi
0x1800212a6  mov     [r11-868h], rsi
0x1800212ad  mov     r8d, esi
0x1800212b0  mov     [r11-860h], rsi
0x1800212b7  mov     r14d, esi
0x1800212ba  mov     [r11-858h], rsi
0x1800212c1  mov     ebx, esi
0x1800212c3  mov     [r11-850h], rbx
0x1800212ca  mov     rcx, [r13+48h]
0x1800212ce  mov     r9d, [r13+50h]
0x1800212d2  movzx   edx, word ptr [r13+6]
0x1800212d7  test    edx, edx
0x1800212d9  jz      loc_180022C7B
0x1800212df  sub     edx, 1
0x1800212e2  jz      loc_18002138B
0x1800212e8  sub     edx, 1
0x1800212eb  jz      short loc_1800212F6
0x1800212ed  cmp     edx, 1
0x1800212f0  jnz     loc_180022C7B
0x1800212f6  cmp     dword ptr [rdi+20h], 0Bh
0x1800212fa  jb      short loc_180021379
0x1800212fc  cmp     r15d, 4
0x180021300  jz      short loc_18002134D
0x180021302  cmp     r15d, 8
0x180021306  jnz     loc_180022C7B
0x18002130c  cmp     r9d, 40h ; '@'
0x180021310  jnb     short loc_18002131E
0x180021312  mov     eax, 8007000Dh
0x180021317  mov     edx, esi
0x180021319  jmp     loc_1800213F2
0x18002131e  mov     edx, [rcx+10h]
0x180021321  mov     eax, [rcx+8]
0x180021324  mov     [rsp+918h+var_864], eax
0x18002132b  mov     r8, [rcx]
0x18002132e  lea     rbx, [rcx+38h]
0x180021332  mov     r14d, [rcx+14h]
0x180021336  mov     [rsp+918h+var_858], r14d
0x18002133e  mov     eax, [rcx+18h]
0x180021341  mov     [rsp+918h+var_854], eax
0x180021348  jmp     loc_1800213D9
0x18002134d  cmp     r9d, 30h ; '0'
0x180021351  jb      short loc_180021312
0x180021353  lea     rbx, [rcx+2Ch]
0x180021357  mov     eax, [rcx+4]
0x18002135a  mov     [rsp+918h+var_864], eax
0x180021361  mov     r14d, [rcx+0Ch]
0x180021365  mov     [rsp+918h+var_858], r14d
0x18002136d  mov     eax, [rcx+10h]
0x180021370  mov     [rsp+918h+var_854], eax
0x180021377  jmp     short loc_1800213D3
0x180021379  cmp     r15d, 4
0x18002137d  jnz     short loc_180021302
0x18002137f  cmp     r9d, 2Ch ; ','
0x180021383  jb      short loc_180021312
0x180021385  lea     rbx, [rcx+28h]
0x180021389  jmp     short loc_180021357
0x18002138b  cmp     r15d, 4
0x18002138f  jz      short loc_1800213BB
0x180021391  cmp     r15d, 8
0x180021395  jnz     loc_180022C7B
0x18002139b  cmp     r9d, 18h
0x18002139f  jb      loc_180021312
0x1800213a5  mov     edx, [rcx+10h]
0x1800213a8  mov     eax, [rcx+8]
0x1800213ab  mov     [rsp+918h+var_864], eax
0x1800213b2  mov     r8, [rcx]
0x1800213b5  lea     rbx, [rcx+14h]
0x1800213b9  jmp     short loc_1800213D9
0x1800213bb  cmp     r9d, 10h
0x1800213bf  jb      loc_180021312
0x1800213c5  mov     eax, [rcx+4]
0x1800213c8  mov     [rsp+918h+var_864], eax
0x1800213cf  lea     rbx, [rcx+0Ch]
0x1800213d3  mov     edx, [rcx+8]
0x1800213d6  mov     r8d, [rcx]
0x1800213d9  mov     eax, esi
0x1800213db  mov     [rsp+918h+String1], rbx
0x1800213e3  mov     [rsp+918h+var_860], r8
0x1800213eb  mov     [rsp+918h+var_868], edx
0x1800213f2  test    eax, eax
0x1800213f4  js      loc_180022C7B
0x1800213fa  mov     rax, [r13+10h]
0x1800213fe  cmp     [rdi+28h], rax
0x180021402  jnz     short loc_180021413
0x180021404  cmp     [rdi+30h], edx
0x180021407  jnz     short loc_180021413
0x180021409  cmp     [rdi+38h], r8
0x18002140d  jz      loc_180022CA3
0x180021413  cmp     [rdi+0B0h], sil
0x18002141a  jnz     short loc_180021425
0x18002141c  lea     rcx, [rdi+40h]; this
0x180021420  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x180021425  lea     r8, [rdi+0C0h]
0x18002142c  mov     rdx, rbx
0x18002142f  lea     rcx, [rdi+40h]
0x180021433  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180021438  test    al, al
0x18002143a  jnz     loc_180021510
0x180021440  mov     rcx, [rdi+0B8h]
0x180021447  test    rcx, rcx
0x18002144a  jz      short loc_180021466
0x18002144c  lea     r12, [rdi+0C0h]
0x180021453  mov     r8, r12
0x180021456  mov     rdx, rbx
0x180021459  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002145e  test    al, al
0x180021460  jnz     loc_180021517
0x180021466  test    rbx, rbx
0x180021469  jz      short loc_1800214DE
0x18002146b  mov     r14, rsi
0x18002146e  cmp     [rdi+0C9h], sil
0x180021475  jnz     short loc_1800214B0
0x180021477  mov     edx, 5Ch ; '\'; Ch
0x18002147c  mov     rcx, rbx; Str
0x18002147f  call    cs:__imp_wcsrchr
0x180021486  nop     dword ptr [rax+rax+00h]
0x18002148b  test    rax, rax
0x18002148e  jz      short loc_1800214B0
0x180021490  sub     rax, rbx
0x180021493  sar     rax, 1
0x180021496  inc     rax
0x180021499  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002149d  inc     r12
0x1800214a0  cmp     [rbx+r12*2], si
0x1800214a5  jnz     short loc_18002149D
0x1800214a7  cmp     rax, r12
0x1800214aa  sbb     r14, r14
0x1800214ad  and     r14, rax
0x1800214b0  lea     rcx, [rdi+178h]
0x1800214b7  mov     rax, [rcx]
0x1800214ba  lea     r8, [rbx+r14*2]
0x1800214be  lea     rdx, aUnableToParseI; "Unable to parse image path: %s"
0x1800214c5  mov     rax, [rax]
0x1800214c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214cd  test    al, al
0x1800214cf  jz      short loc_180021506
0x1800214d1  mov     rdx, r13; struct _EVENT_TRACE *
0x1800214d4  mov     rcx, rdi; this
0x1800214d7  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x1800214dc  jmp     short loc_180021506
0x1800214de  lea     rcx, [rdi+178h]
0x1800214e5  mov     rax, [rcx]
0x1800214e8  lea     rdx, aNullPathInImag; "NULL path in image path."
0x1800214ef  mov     rax, [rax]
0x1800214f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214f7  test    al, al
0x1800214f9  jz      short loc_180021506
0x1800214fb  mov     rdx, r13; struct _EVENT_TRACE *
0x1800214fe  mov     rcx, rdi; this
0x180021501  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x180021506  mov     eax, 1
0x18002150b  jmp     loc_180022CA8
0x180021510  lea     r12, [rdi+0C0h]
0x180021517  lea     rax, [rdi+0C9h]
0x18002151e  mov     [rsp+918h+var_808], rax
0x180021526  cmp     [rax], sil
0x180021529  jnz     short loc_18002159B
0x18002152b  mov     rbx, rsi
0x18002152e  mov     edx, 5Ch ; '\'; Ch
0x180021533  mov     rcx, [r12]; Str
0x180021537  call    cs:__imp_wcsrchr
0x18002153e  nop     dword ptr [rax+rax+00h]
0x180021543  test    rax, rax
0x180021546  jz      short loc_180021571
0x180021548  mov     rcx, [r12]
0x18002154c  sub     rax, rcx
0x18002154f  sar     rax, 1
0x180021552  lea     rdx, [rax+1]
0x180021556  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002155a  mov     rax, r12
0x18002155d  inc     rax
0x180021560  cmp     [rcx+rax*2], si
0x180021564  jnz     short loc_18002155D
0x180021566  cmp     rdx, rax
0x180021569  sbb     rbx, rbx
0x18002156c  and     rbx, rdx
0x18002156f  jmp     short loc_180021575
0x180021571  or      r12, 0FFFFFFFFFFFFFFFFh
0x180021575  lea     rcx, [rdi+178h]
0x18002157c  mov     rdx, [rcx]
0x18002157f  mov     rax, [rdi+0C0h]
0x180021586  lea     r8, [rax+rbx*2]
0x18002158a  mov     rax, [rdx]
0x18002158d  lea     rdx, aSFailure; "%s failure: "
0x180021594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021599  jmp     short loc_1800215C2
0x18002159b  lea     rcx, [rdi+178h]
0x1800215a2  mov     rax, [rcx]
0x1800215a5  mov     r9, rbx
0x1800215a8  mov     r8, [r12]
0x1800215ac  lea     rdx, aSSFailure; "%s [%s] failure: "
0x1800215b3  mov     rax, [rax]
0x1800215b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215bb  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800215c2  mov     rax, [rsp+918h+var_808]
0x1800215ca  mov     [rsp+918h+var_7F0], rax
0x1800215d2  xor     edx, edx; Val
0x1800215d4  mov     r8d, 640h; Size
0x1800215da  lea     rcx, [rsp+918h+var_758]; void *
0x1800215e2  call    memset_0
0x1800215e7  cmp     r15d, 4
0x1800215eb  jz      short loc_180021601
0x1800215ed  cmp     r15d, 8
0x1800215f1  jnz     loc_180022B76
0x1800215f7  lea     rax, [rsp+918h+var_740]
0x1800215ff  jmp     short loc_180021609
0x180021601  lea     rax, [rsp+918h+var_748]
0x180021609  mov     [rsp+918h+var_810], rax
0x180021611  mov     [rsp+918h+var_884], esi
0x180021618  mov     [rsp+918h+var_830], rsi
0x180021620  mov     [rsp+918h+var_838], rsi
0x180021628  mov     [rsp+918h+var_840], rsi
0x180021630  xorps   xmm0, xmm0
0x180021633  xor     ecx, ecx
0x180021635  movups  [rsp+918h+var_7E8], xmm0
0x18002163d  mov     [rsp+918h+var_7D8], rcx
0x180021645  mov     [rsp+918h+var_887], sil
0x18002164d  lea     rbx, [rdi+0D0h]
0x180021654  mov     [rsp+918h+var_800], rbx
0x18002165c  mov     [rsp+918h+var_8C0], rax; unsigned __int16 *
0x180021661  lea     rax, [rsp+918h+var_887]
0x180021669  mov     [rsp+918h+var_8C8], rax; bool *
0x18002166e  lea     rax, [rsp+918h+var_7E8]
0x180021676  mov     [rsp+918h+var_8D0], rax; struct EMBEDDED_PDB_INFORMATION *
0x18002167b  lea     rax, [rsp+918h+var_864]
0x180021683  mov     [rsp+918h+var_8D8], rax; unsigned int *
0x180021688  lea     rax, [rsp+918h+var_854]
0x180021690  mov     [rsp+918h+var_8E0], rax; unsigned int *
0x180021695  lea     rax, [rsp+918h+var_840]
0x18002169d  mov     [rsp+918h+var_8E8], rax; struct CODEVIEW_INFORMATION_1 **
0x1800216a2  lea     rax, [rsp+918h+var_838]
0x1800216aa  mov     [rsp+918h+var_8F0], rax; unsigned int **
0x1800216af  lea     rax, [rsp+918h+var_830]
0x1800216b7  mov     [rsp+918h+var_8F8], rax; union _CVDD **
0x1800216bc  lea     r9, [rsp+918h+var_884]; unsigned int *
0x1800216c4  mov     r8d, r14d; unsigned int
0x1800216c7  lea     r15, [rdi+0C0h]
0x1800216ce  mov     rdx, [r15]; unsigned __int16 *
0x1800216d1  mov     rcx, rbx; this
0x1800216d4  call    ?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z; Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)
0x1800216d9  mov     r8d, eax
0x1800216dc  test    eax, eax
0x1800216de  jns     loc_180022225
0x1800216e4  cmp     eax, 80070490h
0x1800216e9  jnz     loc_1800221C6
0x1800216ef  mov     eax, [rdi+170h]
0x1800216f5  mov     dword ptr [rsp+918h+var_880], eax
0x1800216fc  mov     [rsp+918h+var_884], eax
0x180021703  lea     rax, [rdi+158h]
0x18002170a  mov     [rsp+918h+var_828], rax
0x180021712  cmp     [rax], rsi
0x180021715  jz      loc_180022B76
0x18002171b  lea     rcx, [rdi+160h]
0x180021722  mov     [rsp+918h+var_7F8], rcx
0x18002172a  cmp     [rcx], rsi
0x18002172d  jz      loc_180022B76
0x180021733  lea     rax, [rdi+168h]
0x18002173a  mov     [rsp+918h+var_820], rax
0x180021742  cmp     [rax], rsi
0x180021745  jz      loc_180022B76
0x18002174b  mov     qword ptr [rsp+918h+pguid.Data1], rbx
0x180021753  mov     [rsp+918h+var_838], rcx
0x18002175b  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x180021760  mov     cl, al
0x180021762  mov     [rsp+918h+var_888], al; struct XPerfCore::IErrorMessage *
0x180021769  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x180021771  movdqu  xmmword ptr [rsp+918h+hFile], xmm0
0x18002177a  mov     [rsp+918h+var_7B8], rsi
0x180021782  mov     [rsp+918h+var_7B0], rsi
0x18002178a  mov     rbx, [r15]
0x18002178d  mov     [rsp+918h+var_878], rbx
0x180021795  mov     [rsp+918h+var_830], rbx
0x18002179d  lea     rax, [rdi+178h]
0x1800217a4  mov     [rsp+918h+var_840], rax
0x1800217ac  mov     r9, rax; struct XPerfCore::IErrorMessage *
0x1800217af  mov     r8b, cl; bool
0x1800217b2  mov     rdx, rbx; unsigned __int16 *
0x1800217b5  lea     rcx, [rsp+918h+hFile]; this
0x1800217bd  call    ?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z; XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)
0x1800217c2  mov     r14d, eax
  ... truncated ...
```
