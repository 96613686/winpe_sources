# Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(bool,bool,bool,ulong,ulong,bool,ulong,ulong,bool,ulong,RtlArray<ushort const *> const *,RtlArray<ushort const *> const *,RtlArray<ushort const *> const *,_LARGE_INTEGER,bool,ushort const *,ushort const *,Windows::Compat::Appraiser::DataFile *,ushort const *,ushort const *,bool)

- ea: `0x1800dc444`
- end: `0x1800ddb26`
- name: `?Initialize@RegistryMarkerOutputter@Appraiser@Compat@Windows@@QEAAJ_N00KK0KK0KPEBV?$RtlArray@PEBG@@11T_LARGE_INTEGER@@0PEBG3PEAVDataFile@234@330@Z`
- size: `5858`
- prototype: `__int64 __usercall@<rax>(Windows::Compat::Appraiser::RegistryMarkerOutputter *this@<rcx>, int, int, char, int, int, char, int, __int64, __int64, __int64, __int64, char, __int64, __int64, __int64, int, __int64, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003f0b8`
- `0x1800ddb30`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x180013c7c`
- `0x1800144c4`
- `0x1800151f4`
- `0x1800287d4`
- `0x180029258`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800393ec`
- `0x180071ac8`
- `0x180076ddc`
- `0x180096ef0`
- `0x1800b7bfc`
- `0x1800bda24`
- `0x1800dc444`
- `0x1800de098`
- `0x18010e90c`
- `0x18010ed08`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800dd6b3`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800dd6b3`
- `KERNEL32!GetSystemTime` at `0x1800dc7cb`
- `KERNEL32!GetSystemTime` at `0x1800dc95a`
- `KERNEL32!GetSystemTime` at `0x1800dd4fd`
- `KERNEL32!GetSystemTime` at `0x1800dd838`
- `KERNEL32!GetSystemTime` at `0x1800dda42`
- `KERNEL32!GetSystemTime` at `0x1800dc7cb`
- `KERNEL32!GetSystemTime` at `0x1800dc95a`
- `KERNEL32!GetSystemTime` at `0x1800dd4fd`
- `KERNEL32!GetSystemTime` at `0x1800dd838`
- `KERNEL32!GetSystemTime` at `0x1800dda42`
- `KERNEL32!HeapReAlloc` at `0x1800dcf32`
- `KERNEL32!HeapReAlloc` at `0x1800dd235`
- `KERNEL32!HeapReAlloc` at `0x1800dcf32`
- `KERNEL32!HeapReAlloc` at `0x1800dd235`
- `KERNEL32!GetProcessHeap` at `0x1800dc4d2`
- `KERNEL32!GetProcessHeap` at `0x1800dc504`
- `KERNEL32!GetProcessHeap` at `0x1800dd00c`
- `KERNEL32!GetProcessHeap` at `0x1800dd070`
- `KERNEL32!GetProcessHeap` at `0x1800dc4d2`
- `KERNEL32!GetProcessHeap` at `0x1800dc504`
- `KERNEL32!GetProcessHeap` at `0x1800dd00c`
- `KERNEL32!GetProcessHeap` at `0x1800dd070`
- `KERNEL32!HeapAlloc` at `0x1800dcf12`
- `KERNEL32!HeapAlloc` at `0x1800dd215`
- `KERNEL32!HeapAlloc` at `0x1800dcf12`
- `KERNEL32!HeapAlloc` at `0x1800dd215`
- `KERNEL32!HeapFree` at `0x1800ddae5`
- `KERNEL32!HeapFree` at `0x1800ddafb`
- `KERNEL32!HeapFree` at `0x1800ddae5`
- `KERNEL32!HeapFree` at `0x1800ddafb`
- `SHLWAPI!StrStrW` at `0x1800dcdc7`
- `SHLWAPI!StrStrW` at `0x1800dcdc7`

## string_xrefs

- `0x1800dcdbd`: `_CompatMarker_`
- `0x1800dc65c`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dc685`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800dc655`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize`
- `0x1800dc67e`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize`
- `0x1800dca4f`: `Failed to append required component: [0x%x].`
- `0x1800dca84`: `Failed to append required component: [0x%x].`
- `0x1800dcbce`: `Failed to append required component: [0x%x].`
- `0x1800dcc1d`: `Failed to append required component: [0x%x].`
- `0x1800dcd27`: `Failed to append required component: [0x%x].`
- `0x1800dce5b`: `Failed to append required component: [0x%x].`
- `0x1800dcfae`: `Failed to append required component: [0x%x].`
- `0x1800dd1a3`: `Failed to append required component: [0x%x].`
- `0x1800dd30d`: `Failed to append required component: [0x%x].`
- `0x1800dd3a4`: `Failed to append required component: [0x%x].`
- `0x1800dd966`: `Failed to initialize indicators to remove duplicates, swallowing: [0x%x].`
- `0x1800ddabc`: `Failed to initialize indicators to remove duplicates, swallowing: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(
        Windows::Compat::Appraiser::RegistryMarkerOutputter *this,
        char a2,
        char a3,
        char a4,
        int a5,
        int a6,
        char a7,
        int a8,
        int a9,
        char a10,
        unsigned int a11,
        unsigned __int64 *a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        char a16,
        __int64 a17,
        const size_t *a18,
        struct Windows::Compat::Appraiser::DataFile *a19,
        int a20,
        char *a21,
        char a22)
{
  struct Windows::Compat::Appraiser::DataFile *v26; // r12
  const size_t *v27; // rax
  int v28; // eax
  int v29; // ebx
  char *v30; // rbx
  __int64 ListTableByName; // rax
  volatile signed __int64 *v32; // rcx
  void **v33; // rdx
  int v34; // ebx
  int v35; // r8d
  int v36; // r9d
  __int64 v37; // rax
  volatile signed __int64 *v38; // rcx
  void **v39; // rdx
  int v40; // ebx
  int v41; // r8d
  int v42; // r9d
  unsigned __int64 v43; // rax
  unsigned __int64 v44; // r12
  char *v45; // r8
  _QWORD *v46; // rdx
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rcx
  const char *v49; // rax
  char v50; // dl
  unsigned __int64 v51; // rax
  unsigned __int64 *v52; // rbx
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // r12
  const char *v55; // r8
  _QWORD *v56; // rdx
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rcx
  unsigned __int64 *v59; // r13
  char **v60; // rdx
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // kr00_8
  unsigned __int64 v63; // rcx
  unsigned __int64 *v64; // rbx
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // r12
  _QWORD *v67; // rdx
  unsigned __int64 v68; // rax
  unsigned __int64 v69; // rcx
  unsigned __int64 *v70; // r13
  char **v71; // rdx
  unsigned __int64 v72; // rax
  unsigned __int64 v73; // kr10_8
  unsigned __int64 v74; // rcx
  unsigned __int64 *v75; // r13
  unsigned __int64 v76; // rax
  unsigned __int64 v77; // r12
  const WCHAR **v78; // rbx
  unsigned __int64 v79; // rax
  unsigned __int64 v80; // rcx
  const WCHAR *v81; // rbx
  PWSTR v82; // rax
  const WCHAR *v83; // r10
  unsigned __int64 v84; // r8
  _QWORD *v85; // rdx
  __int64 v86; // rax
  const WCHAR *v87; // rax
  __int64 v88; // r9
  int v89; // ecx
  int v90; // edx
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // rcx
  __int64 v93; // rbx
  unsigned __int64 v94; // rbx
  unsigned __int128 v95; // rax
  size_t v96; // r13
  void *v97; // r8
  void *v98; // rcx
  void *v99; // rax
  LPVOID v100; // r12
  unsigned __int64 v101; // rax
  unsigned __int64 v102; // kr20_8
  unsigned __int64 v103; // rax
  int v104; // eax
  unsigned __int64 v105; // r12
  __int64 v106; // rdx
  __int64 v107; // r8
  _QWORD *v108; // r8
  unsigned __int64 v109; // rax
  unsigned __int64 v110; // rcx
  unsigned __int64 v111; // rax
  unsigned __int64 v112; // rcx
  int v113; // ecx
  __int64 v114; // rbx
  unsigned __int64 v115; // rbx
  unsigned __int128 v116; // rax
  size_t v117; // r13
  void *v118; // r8
  void *v119; // rcx
  void *v120; // rax
  LPVOID v121; // r12
  unsigned __int64 v122; // rax
  unsigned __int64 v123; // kr30_8
  _OWORD *v124; // rax
  int v125; // ecx
  char *v126; // r12
  __int64 v127; // rax
  char *v128; // rcx
  unsigned __int64 *v129; // r13
  volatile signed __int64 *v130; // rcx
  void **v131; // rdx
  int v132; // ebx
  int v133; // r8d
  int v134; // r9d
  unsigned __int64 v135; // r12
  RtlStringArray *v136; // r9
  const unsigned __int16 **v137; // rdx
  unsigned __int64 v138; // rax
  unsigned __int64 v139; // rcx
  struct Windows::Compat::Appraiser::DataFile *v140; // r13
  Windows::Compat::Appraiser::MapTable *v141; // rax
  int AssociatedRightValue; // eax
  const char *v143; // r9
  char v144; // dl
  int v145; // eax
  __int64 v146; // rax
  unsigned __int64 *v147; // rbx
  unsigned __int64 v148; // r12
  volatile signed __int64 *v149; // rcx
  void **v150; // rdx
  int v151; // ebx
  int v152; // r8d
  int v153; // r9d
  __int64 *v154; // rax
  unsigned __int64 v155; // rcx
  __int64 v156; // rdx
  __int64 v157; // r8
  int v158; // eax
  int v159; // ebx
  volatile signed __int64 *v160; // rcx
  void **v161; // rdx
  int v162; // edi
  int v163; // r8d
  int v164; // r9d
  char *v166; // [rsp+20h] [rbp-E0h]
  const char *v167; // [rsp+28h] [rbp-D8h]
  char *v168; // [rsp+30h] [rbp-D0h]
  char *v169; // [rsp+60h] [rbp-A0h] BYREF
  char *v170; // [rsp+68h] [rbp-98h] BYREF
  char *v171; // [rsp+70h] [rbp-90h] BYREF
  bool v172; // [rsp+78h] [rbp-88h]
  char v173[8]; // [rsp+80h] [rbp-80h] BYREF
  const char *v174; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Compat::Appraiser::DataFile *v175; // [rsp+90h] [rbp-70h]
  __int64 v176; // [rsp+98h] [rbp-68h]
  const char *v177; // [rsp+A0h] [rbp-60h] BYREF
  const char *v178; // [rsp+A8h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v180; // [rsp+C0h] [rbp-40h]
  char *v181; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v182; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v183[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v184; // [rsp+E8h] [rbp-18h]
  LPVOID v185[2]; // [rsp+F8h] [rbp-8h]
  HANDLE hHeap[2]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v187; // [rsp+118h] [rbp+18h]
  LPVOID lpMem[2]; // [rsp+128h] [rbp+28h]
  __int64 v189; // [rsp+138h] [rbp+38h]
  _OWORD v190[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v191[64]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v192; // [rsp+1A0h] [rbp+A0h]
  _BYTE v193[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v194; // [rsp+1F0h] [rbp+F0h]
  char v195[144]; // [rsp+200h] [rbp+100h] BYREF

  v189 = -2;
  v180 = a13;
  v176 = a14;
  v175 = a19;
  v170 = a21;
  v182 = 0;
  v183[0] = GetProcessHeap();
  v185[0] = (LPVOID)16;
  v184 = 0;
  v185[1] = 0;
  v183[1] = (HANDLE)8;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v187 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v171 = *(char **)(a13 + 16);
  v172 = *(_QWORD *)(a14 + 16) != 0;
  *((_BYTE *)this + 317) = a2;
  *((_BYTE *)this + 318) = a3;
  *((_BYTE *)this + 319) = a4;
  *((_DWORD *)this + 80) = a5;
  *((_DWORD *)this + 81) = a6;
  *((_BYTE *)this + 328) = a7;
  *((_BYTE *)this + 340) = a10;
  *((_DWORD *)this + 83) = a8;
  *((_DWORD *)this + 84) = a9;
  *((_QWORD *)this + 44) = a15;
  *((_BYTE *)this + 360) = a16;
  *((_QWORD *)this + 46) = a17;
  v26 = v175;
  *((_DWORD *)this + 78) = *((_DWORD *)v175 + 160);
  *((_BYTE *)this + 316) = *((_DWORD *)v26 + 160) >= a11;
  std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::clear((char *)this + 912);
  v27 = &szValueBuf;
  if ( a18 )
    v27 = a18;
  v28 = StringCchPrintfW((unsigned __int16 *)this + 188, 0x104u, L"%ls%ls", *((_QWORD *)this + 46), v27);
  v29 = v28;
  if ( v28 < 0 )
  {
    LODWORD(v168) = v28;
    LODWORD(v166) = v28;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      141,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      v166,
      (int)"Failed to printf: [0x%x].",
      v168);
    goto LABEL_208;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x8Du,
      "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      "Failed to printf: [0x%x].",
      v28);
  v30 = v170;
  if ( v170 )
  {
    ListTableByName = Windows::Compat::Appraiser::DataFile::FindListTableByName((char *)v26 + 144, v170);
    *((_QWORD *)this + 112) = ListTableByName;
    if ( !ListTableByName )
    {
      LODWORD(v166) = -2147023728;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        149,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        v166,
        (int)"Failed to find table, swallowing [%ls].  ",
        v30);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v191);
      v32 = (volatile signed __int64 *)v191;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v32 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v32,
        _InterlockedExchangeAdd64(v32 + 17, 0),
        v195);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v33);
      v34 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v181 = v195;
        *(_DWORD *)v173 = -2147023728;
        v177 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize";
        v178 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
        LODWORD(v170) = 149;
        v174 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v190[0] = SystemTime;
        v169 = (char *)v190;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v34,
          (unsigned int)&unk_1802A442B,
          v35,
          v36,
          (__int64)&v169,
          (__int64)&v174,
          (__int64)&v170,
          (__int64)&v178,
          (__int64)&v177,
          (__int64)v173,
          (__int64)&v181);
      }
    }
  }
  if ( !*((_QWORD *)this + 113) )
  {
    v37 = Windows::Compat::Appraiser::DataFile::FindListTableByName((char *)v26 + 144, L"FT_ANY_IncludeInTelemetry");
    *((_QWORD *)this + 113) = v37;
    if ( !v37 )
    {
      LODWORD(v166) = -2147023728;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        159,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        v166,
        (int)"Failed to find table, swallowing [%ls].",
        L"FT_ANY_IncludeInTelemetry");
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v191);
      v38 = (volatile signed __int64 *)v191;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v38 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v38,
        _InterlockedExchangeAdd64(v38 + 17, 0),
        v195);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v39);
      v40 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v169 = v195;
        LODWORD(v170) = -2147023728;
        v174 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize";
        v178 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
        *(_DWORD *)v173 = 159;
        v177 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v190[0] = SystemTime;
        v181 = (char *)v190;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)&unk_1802A448E,
          v41,
          v42,
          (__int64)&v181,
          (__int64)&v177,
          (__int64)v173,
          (__int64)&v178,
          (__int64)&v174,
          (__int64)&v170,
          (__int64)&v169);
      }
    }
  }
  v43 = a12[2];
  if ( v43 )
  {
    v44 = 0;
    v45 = (char *)v175 + 288;
    v170 = (char *)v175 + 288;
    while ( 1 )
    {
      v46 = 0;
      if ( v44 < v43 )
      {
        v169 = 0;
        v47 = a12[1] * v44;
        if ( !is_mul_ok(a12[1], v44) || (v48 = a12[5], v46 = (_QWORD *)(v47 + v48), v47 + v48 < v48) )
          v46 = 0;
      }
      v169 = (char *)Windows::Compat::Appraiser::DataFile::FindListTableByName(v45, *v46);
      if ( !v169 )
        break;
      v29 = RtlArray<JsonValue *>::Append((char *)this + 208, &v169);
      if ( v29 < 0 )
      {
        LODWORD(v168) = v29;
        v49 = "Failed to append required component: [0x%x].";
        v50 = -79;
LABEL_46:
        LODWORD(v167) = (_DWORD)v49;
        LODWORD(v166) = v29;
        goto LABEL_47;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xB1u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
          "Failed to append required component: [0x%x].",
          v29);
      ++v44;
      v43 = a12[2];
      v45 = v170;
      if ( v44 >= v43 )
        goto LABEL_49;
    }
    v51 = 0;
    if ( v44 < a12[2] )
    {
      if ( !is_mul_ok(a12[1], v44) || (v51 = a12[5] + a12[1] * v44, v51 < a12[5]) )
        v51 = 0;
    }
    v50 = -83;
LABEL_45:
    v168 = *(char **)v51;
    v49 = "List table %ls was not found in data file.";
    v29 = -2147024883;
    goto LABEL_46;
  }
  v170 = (char *)v26 + 288;
LABEL_49:
  v52 = (unsigned __int64 *)v180;
  v53 = *(_QWORD *)(v180 + 16);
  if ( !v53 )
    goto LABEL_74;
  v54 = 0;
  v55 = (char *)v175 + 288;
  v174 = (char *)v175 + 288;
  while ( 2 )
  {
    v56 = 0;
    if ( v54 < v53 )
    {
      v169 = 0;
      v57 = v52[1] * v54;
      if ( !is_mul_ok(v52[1], v54) || (v58 = v52[5], v56 = (_QWORD *)(v57 + v58), v57 + v58 < v58) )
        v56 = 0;
    }
    v59 = (unsigned __int64 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(v55, *v56);
    v51 = 0;
    if ( !v59 )
    {
      if ( v54 < v52[2] )
      {
        if ( !is_mul_ok(v52[1], v54) || (v51 = v52[5] + v52[1] * v54, v51 < v52[5]) )
          v51 = 0;
      }
      v50 = -66;
      goto LABEL_45;
    }
    *(_QWORD *)v173 = 0;
    if ( !v59[18] )
      goto LABEL_66;
    do
    {
      v60 = 0;
      if ( v51 < v59[18] )
      {
        v169 = 0;
        v62 = v51;
        v61 = v59[17] * v51;
        if ( !is_mul_ok(v59[17], v62) || (v63 = v59[21], v60 = (char **)(v61 + v63), v61 + v63 < v63) )
          v60 = 0;
      }
      v169 = *v60;
      v29 = RtlArray<JsonValue *>::Append(v183, &v169);
      if ( v29 < 0 )
      {
        LODWORD(v168) = v29;
        v49 = "Failed to append required component: [0x%x].";
        v50 = -60;
        goto LABEL_46;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xC4u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
          "Failed to append required component: [0x%x].",
          v29);
      v51 = *(_QWORD *)v173 + 1LL;
      *(_QWORD *)v173 = v51;
    }
    while ( v51 < v59[18] );
    v52 = (unsigned __int64 *)v180;
LABEL_66:
    ++v54;
    v53 = v52[2];
    if ( v54 < v53 )
    {
      v55 = v174;
      continue;
    }
    break;
  }
LABEL_74:
  v64 = (unsigned __int64 *)v176;
  v65 = *(_QWORD *)(v176 + 16);
  if ( !v65 )
    goto LABEL_92;
  v66 = 0;
  while ( 2 )
  {
    v67 = 0;
    if ( v66 < v65 )
    {
      v169 = 0;
      v68 = v64[1] * v66;
      if ( !is_mul_ok(v64[1], v66) || (v69 = v64[5], v67 = (_QWORD *)(v68 + v69), v68 + v69 < v69) )
        v67 = 0;
    }
    v70 = (unsigned __int64 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(v170, *v67);
    v51 = 0;
    if ( !v70 )
    {
      if ( v66 < v64[2] )
      {
        if ( !is_mul_ok(v64[1], v66) || (v51 = v64[5] + v64[1] * v66, v51 < v64[5]) )
          v51 = 0;
      }
      v50 = -50;
      goto LABEL_45;
    }
    v180 = 0;
    if ( !v70[18] )
      goto LABEL_91;
    while ( 2 )
    {
      v71 = 0;
      if ( v51 < v70[18] )
      {
        v169 = 0;
        v73 = v51;
        v72 = v70[17] * v51;
        if ( !is_mul_ok(v70[17], v73) || (v74 = v70[21], v71 = (char **)(v72 + v74), v72 + v74 < v74) )
          v71 = 0;
      }
      v169 = *v71;
      v29 = RtlArray<JsonValue *>::Append(hHeap, &v169);
      if ( v29 < 0 )
      {
        LODWORD(v168) = v29;
        v49 = "Failed to append required component: [0x%x].";
        v50 = -44;
        goto LABEL_46;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xD4u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
          "Failed to append required component: [0x%x].",
          v29);
      v51 = v180 + 1;
      v180 = v51;
      if ( v51 < v70[18] )
        continue;
      break;
    }
    v64 = (unsigned __int64 *)v176;
LABEL_91:
    ++v66;
    v65 = v64[2];
    if ( v66 < v65 )
      continue;
    break;
  }
LABEL_92:
  v75 = (unsigned __int64 *)v175;
  v76 = *((_QWORD *)v175 + 8);
  if ( !v76 )
  {
LABEL_136:
    v104 = 0;
    *(_DWORD *)v173 = 0;
    v105 = 0;
    v176 = 0;
    if ( v75[44] )
    {
      while ( 1 )
      {
        memset(v191, 0, 56);
        *(_QWORD *)&v191[8] = GetProcessHeap();
        *(_OWORD *)&v191[40] = 0x10u;
        *(_OWORD *)&v191[24] = 0u;
        *(_QWORD *)&v191[16] = 8;
        *(_QWORD *)&v191[56] = 0;
        v192 = 0u;
        *(_DWORD *)v193 = 0;
        memset(&v193[8], 0, 48);
        *(_QWORD *)&v193[8] = GetProcessHeap();
        *(_OWORD *)&v193[40] = 0x10u;
        *(_OWORD *)&v193[24] = 0u;
        *(_QWORD *)&v193[16] = 16;
        *(_DWORD *)&v193[56] = 0;
        RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(&v193[8], v106, v107, 16);
        *(_QWORD *)&v194 = 0;
        DWORD2(v194) = 1;
        v108 = 0;
        if ( v105 < v75[44] )
        {
          v171 = 0;
          v109 = v75[43] * v105;
          if ( !is_mul_ok(v75[43], v105) || (v110 = v75[47], v108 = (_QWORD *)(v110 + v109), v110 + v109 < v110) )
            v108 = 0;
        }
        LOBYTE(v166) = v172;
        v29 = Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry::Initialize(
                v191,
                v173,
                *v108,
                v75,
                (_DWORD)v166,
                hHeap);
        if ( v29 < 0 )
          break;
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x10Au,
            "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
            "Failed to initialize indicator constraint entry: [0x%x].",
            v29);
        if ( v29 != 1 )
        {
          v111 = *((_QWORD *)this + 10);
          v171 = (char *)v111;
          if ( v111 >= *((_QWORD *)this + 11) )
          {
            v112 = v111 + 1;
            if ( v111 + 1 <= *((_QWORD *)this + 11) )
            {
              v29 = -2147024809;
              goto LABEL_172;
            }
            v114 = *((_QWORD *)this + 12) - 1LL;
            if ( v114 + v112 < v112
              || (v169 = 0, !is_mul_ok(*((_QWORD *)this + 11), *((_QWORD *)this + 9)))
              || (v115 = (v114 + v112) & ~v114,
                  v169 = 0,
                  v116 = v115 * (unsigned __int128)*((unsigned __int64 *)this + 9),
                  v117 = v115 * *((_QWORD *)this + 9),
                  !is_mul_ok(v115, *((_QWORD *)this + 9))) )
            {
              v29 = -2147483637;
LABEL_172:
              v125 = v29;
LABEL_174:
              LODWORD(v168) = v125;
              LODWORD(v166) = v125;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                22,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
                "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
                v166,
                (int)"Failed to append required component: [0x%x].",
                v168);
              goto LABEL_176;
            }
            v118 = (void *)*((_QWORD *)this + 13);
            v119 = (void *)*((_QWORD *)this + 8);
            if ( v118 )
            {
              v121 = HeapReAlloc(v119, DWORD2(v116), v118, v115 * *((_QWORD *)this + 9));
            }
            else
            {
              v120 = HeapAlloc(v119, DWORD2(v116), v115 * *((_QWORD *)this + 9));
              v121 = v120;
              if ( v120 )
                memset_0(v120, 0, v117);
            }
            v75 = (unsigned __int64 *)v175;
            if ( !v121 )
            {
              v29 = -2147024882;
              goto LABEL_172;
            }
            *((_QWORD *)this + 13) = v121;
            *((_QWORD *)this + 11) = v115;
            v111 = (unsigned __int64)v171;
            v105 = v176;
          }
          v171 = 0;
          v123 = v111;
          v122 = *((_QWORD *)this + 9) * v111;
          if ( !is_mul_ok(*((_QWORD *)this + 9), v123)
            || (v124 = (_OWORD *)(*((_QWORD *)this + 13) + v122), (unsigned __int64)v124 < *((_QWORD *)this + 13)) )
          {
            v125 = -2147483637;
            v29 = -2147483637;
            goto LABEL_174;
          }
          *v124 = *(_OWORD *)v191;
          v124[1] = *(_OWORD *)&v191[16];
          v124[2] = *(_OWORD *)&v191[32];
          v124[3] = *(_OWORD *)&v191[48];
          v124[4] = v192;
          v124[5] = *(_OWORD *)v193;
          v124[6] = *(_OWORD *)&v193[16];
          v124[7] = *(_OWORD *)&v193[32];
          v124[8] = *(_OWORD *)&v193[48];
          v124[9] = v194;
          ++*((_QWORD *)this + 10);
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x116u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
              "Failed to append required component: [0x%x].",
              0);
          memset_0(v191, 0, 0xA0u);
        }
        Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry::~RegistryIndicatorConstraintEntry((Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry *)v191);
        v176 = ++v105;
        if ( v105 >= v75[44] )
        {
          v104 = *(_DWORD *)v173;
          goto LABEL_169;
        }
      }
      LODWORD(v168) = v29;
      LODWORD(v166) = v29;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        10,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        v166,
        (int)"Failed to initialize indicator constraint entry: [0x%x].",
        v168);
LABEL_176:
      Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry::~RegistryIndicatorConstraintEntry((Windows::Compat::Appraiser::RegistryIndicatorConstraintEntry *)v191);
      goto LABEL_208;
    }
LABEL_169:
    if ( v104 )
    {
      v29 = -2147024883;
      LODWORD(v166) = -2147024883;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        28,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        v166,
        (int)"Should have the same set of indicators regardless of if run generates new markers or not.",
        v168);
      goto LABEL_208;
    }
    v126 = v170;
    v127 = Windows::Compat::Appraiser::DataFile::FindListTableByName(v170, L"LT_IndicatorsToIgnoreForUTC");
    v129 = (unsigned __int64 *)v127;
    if ( v127 )
    {
      v135 = 0;
      if ( *(_QWORD *)(v127 + 144) )
      {
        v136 = (Windows::Compat::Appraiser::RegistryMarkerOutputter *)((char *)this + 256);
        while ( 1 )
        {
          v137 = 0;
          if ( v135 < v129[18] )
          {
            v171 = 0;
            v138 = v129[17] * v135;
            if ( !is_mul_ok(v129[17], v135)
              || (v139 = v129[21], v137 = (const unsigned __int16 **)(v138 + v139), v138 + v139 < v139) )
            {
              v137 = 0;
            }
          }
          v29 = RtlStringArray::Append(v136, *v137, 0);
          if ( v29 < 0 )
            break;
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x12Du,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
              "RtlArray Append failed: [0x%x].",
              v29);
          ++v135;
          v136 = (Windows::Compat::Appraiser::RegistryMarkerOutputter *)((char *)this + 256);
          if ( v135 >= v129[18] )
          {
            v126 = v170;
            goto LABEL_199;
          }
        }
        LODWORD(v168) = v29;
        v49 = "RtlArray Append failed: [0x%x].";
        v50 = 45;
        goto LABEL_46;
      }
      v126 = v128;
    }
    else
    {
      LODWORD(v168) = -2147023728;
      LODWORD(v166) = -2147023728;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        39,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        v166,
        (int)"Failed to find list table of indicators that should not send UTC, swallowing: [0x%x].",
        v168);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v191);
      v130 = (volatile signed __int64 *)v191;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v130 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v130,
        _InterlockedExchangeAdd64(v130 + 17, 0),
        v195);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v131);
      v132 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v171 = v195;
        LODWORD(v170) = -2147023728;
        v169 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize";
        v174 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
        *(_DWORD *)v173 = 295;
        v178 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v190[0] = SystemTime;
        v177 = (const char *)v190;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v132,
          (unsigned int)&unk_1802A4365,
          v133,
          v134,
          (__int64)&v177,
          (__int64)&v178,
          (__int64)v173,
          (__int64)&v174,
          (__int64)&v169,
          (__int64)&v170,
          (__int64)&v171);
      }
    }
LABEL_199:
    v140 = v175;
    v141 = (Windows::Compat::Appraiser::MapTable *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                                     (char *)v175 + 432,
                                                     L"MT_MarkerIndicatorVersions");
    if ( !v141 )
    {
      v29 = -2147024883;
      LODWORD(v166) = -2147024883;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        56,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
        v166,
        (int)"Did not find a map table listing marker and indicator versions.",
        v168);
      goto LABEL_208;
    }
    AssociatedRightValue = Windows::Compat::Appraiser::MapTable::FindAssociatedRightValue(
                             v141,
                             (const unsigned __int16 **)&v182,
                             L"NewAppraiserMarkerVersion");
    v29 = AssociatedRightValue;
    if ( AssociatedRightValue >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x13Cu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
          "Failed to find NewAppraiserMarkerVersion");
      v145 = _o__wtoi(v182);
      *((_DWORD *)this + 86) = v145;
      if ( v145 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x140u,
            "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
            "Invalid NewAppraiserMarkerVersion");
        if ( !a22 )
        {
          v146 = Windows::Compat::Appraiser::DataFile::FindListTableByName(v126, L"LT_IndicatorsForRegMarkerDeltas");
          v147 = (unsigned __int64 *)v146;
          v148 = 0;
          if ( v146 )
          {
            if ( *(_QWORD *)(v146 + 144) )
            {
              do
              {
                v154 = 0;
                if ( v148 < v147[18] )
                {
                  v171 = 0;
                  if ( !is_mul_ok(v147[17], v148)
                    || (v155 = v147[21], v154 = (__int64 *)(v155 + v147[17] * v148), (unsigned __int64)v154 < v155) )
                  {
                    v154 = 0;
                  }
                }
                v156 = *v154;
                memset(v190, 0, sizeof(v190));
                v157 = -1;
                do
                  ++v157;
                while ( *(_WORD *)(v156 + 2 * v157) );
                std::wstring::_Construct<1,unsigned short const *>(v190, v156);
                *(_DWORD *)std::unordered_map<std::wstring,int>::operator[]((char *)this + 912, v190) = 0;
                std::wstring::~wstring(v190);
                ++v148;
              }
              while ( v148 < v147[18] );
              v140 = v175;
            }
          }
          else
          {
            LODWORD(v168) = -2147023728;
            LODWORD(v166) = -2147023728;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              76,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
              v166,
              (int)"Failed to find list table of indicators to track deltas of, swallowing: [0x%x].",
              v168);
            TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v191);
            v149 = (volatile signed __int64 *)v191;
            if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
              v149 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
            TraceLoggingCorrelationVector::ToStringImpl(
              (TraceLoggingCorrelationVector *)v149,
              _InterlockedExchangeAdd64(v149 + 17, 0),
              v195);
            if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
              UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v150);
            v151 = qword_1802C9628;
            if ( *(_DWORD *)qword_1802C9628 > 5u
              && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              v171 = v195;
              LODWORD(v170) = -2147023728;
              v169 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize";
              v174 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
              *(_DWORD *)v173 = 332;
              v178 = (const char *)&szValueBuf;
              SystemTime = 0;
              GetSystemTime(&SystemTime);
              v190[0] = SystemTime;
              v177 = (const char *)v190;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v151,
                (unsigned int)&unk_1802A43C8,
                v152,
                v153,
                (__int64)&v177,
                (__int64)&v178,
                (__int64)v173,
                (__int64)&v174,
                (__int64)&v169,
                (__int64)&v170,
                (__int64)&v171);
            }
          }
        }
        v158 = Windows::Compat::Appraiser::RegistryMarkerOutputter::InitializeIndicatorsToRemoveDuplicates(this, v140);
        v159 = v158;
        if ( v158 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x15Au,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
              "Failed to initialize indicators to remove duplicates, swallowing: [0x%x].",
              v158);
        }
        else
        {
          LODWORD(v168) = v158;
          LODWORD(v166) = v158;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            90,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
            "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
            v166,
            (int)"Failed to initialize indicators to remove duplicates, swallowing: [0x%x].",
            v168);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v191);
          v160 = (volatile signed __int64 *)v191;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v160 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v160,
            _InterlockedExchangeAdd64(v160 + 17, 0),
            v195);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v161);
          v162 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v171 = v195;
            LODWORD(v170) = v159;
            v169 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize";
            v174 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
            *(_DWORD *)v173 = 346;
            v178 = (const char *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v190[0] = SystemTime;
            v177 = (const char *)v190;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v162,
              (unsigned int)&unk_1802A4302,
              v163,
              v164,
              (__int64)&v177,
              (__int64)&v178,
              (__int64)v173,
              (__int64)&v174,
              (__int64)&v169,
              (__int64)&v170,
              (__int64)&v171);
          }
        }
        v29 = 0;
        goto LABEL_242;
      }
      AssociatedRightValue = -2147024809;
      v29 = -2147024809;
      v143 = "Invalid NewAppraiserMarkerVersion";
      v144 = 64;
    }
    else
    {
      v143 = "Failed to find NewAppraiserMarkerVersion";
      v144 = 60;
    }
    LODWORD(v166) = AssociatedRightValue;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v144,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
      v166,
      (int)v143,
      v168);
    goto LABEL_208;
  }
  v77 = 0;
  v176 = 0;
  while ( 1 )
  {
    *(_OWORD *)((char *)v190 + 8) = 0;
    v78 = 0;
    if ( v77 < v76 )
    {
      v169 = 0;
      v79 = v75[7] * v77;
      if ( !is_mul_ok(v75[7], v77) || (v80 = v75[11], v78 = (const WCHAR **)(v79 + v80), v79 + v80 < v80) )
        v78 = 0;
    }
    v81 = *v78;
    *(_QWORD *)&v190[0] = v81;
    v82 = StrStrW(v81, L"_CompatMarker_");
    v83 = 0;
    if ( v81 + 6 == v82 )
      v83 = v81 + 20;
    *((_QWORD *)&v190[0] + 1) = v83;
    if ( !v171 )
      break;
    v84 = 0;
    if ( (_QWORD)v184 )
    {
      do
      {
        v85 = 0;
        if ( v84 < (unsigned __int64)v184 )
        {
          v169 = 0;
          v86 = (unsigned __int64)v183[1] * v84;
          if ( !is_mul_ok((unsigned __int64)v183[1], v84)
            || (v85 = (char *)v185[1] + v86, (char *)v185[1] + v86 < v185[1]) )
          {
            v85 = 0;
          }
        }
        v87 = v83;
        v88 = *v85 - (_QWORD)v83;
        do
        {
          v89 = *(const WCHAR *)((char *)v87 + v88);
          v90 = *v87 - v89;
          if ( v90 )
            break;
          ++v87;
        }
        while ( v89 );
        if ( !v90 )
          goto LABEL_118;
      }
      while ( ++v84 < (unsigned __int64)v184 );
    }
LABEL_135:
    v176 = ++v77;
    v76 = v75[8];
    if ( v77 >= v76 )
      goto LABEL_136;
  }
LABEL_118:
  v91 = *((_QWORD *)this + 4);
  v169 = (char *)v91;
  if ( v91 >= *((_QWORD *)this + 5) )
  {
    v92 = v91 + 1;
    if ( v91 + 1 <= *((_QWORD *)this + 5) )
    {
      v29 = -2147024809;
LABEL_149:
      v113 = v29;
      goto LABEL_151;
    }
    v93 = *((_QWORD *)this + 6) - 1LL;
    if ( v93 + v92 < v92
      || (v174 = 0, !is_mul_ok(*((_QWORD *)this + 5), *((_QWORD *)this + 3)))
      || (v94 = (v93 + v92) & ~v93,
          v174 = 0,
          v95 = v94 * (unsigned __int128)*((unsigned __int64 *)this + 3),
          v96 = v94 * *((_QWORD *)this + 3),
          !is_mul_ok(v94, *((_QWORD *)this + 3))) )
    {
      v29 = -2147483637;
      goto LABEL_149;
    }
    v97 = (void *)*((_QWORD *)this + 7);
    v98 = (void *)*((_QWORD *)this + 2);
    if ( v97 )
    {
      v100 = HeapReAlloc(v98, DWORD2(v95), v97, v94 * *((_QWORD *)this + 3));
    }
    else
    {
      v99 = HeapAlloc(v98, DWORD2(v95), v94 * *((_QWORD *)this + 3));
      v100 = v99;
      if ( v99 )
        memset_0(v99, 0, v96);
    }
    v75 = (unsigned __int64 *)v175;
    if ( !v100 )
    {
      v29 = -2147024882;
      goto LABEL_149;
    }
    *((_QWORD *)this + 7) = v100;
    *((_QWORD *)this + 5) = v94;
    v91 = (unsigned __int64)v169;
    v77 = v176;
  }
  v169 = 0;
  v102 = v91;
  v101 = *((_QWORD *)this + 3) * v91;
  if ( is_mul_ok(*((_QWORD *)this + 3), v102) )
  {
    v103 = *((_QWORD *)this + 7) + v101;
    if ( v103 >= *((_QWORD *)this + 7) )
    {
      *(_OWORD *)v103 = v190[0];
      *(_QWORD *)(v103 + 16) = *(_QWORD *)&v190[1];
      ++*((_QWORD *)this + 4);
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xF9u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
          "Failed to append required component: [0x%x].",
          0);
      goto LABEL_135;
    }
  }
  v113 = -2147483637;
  v29 = -2147483637;
LABEL_151:
  LODWORD(v168) = v113;
  v167 = "Failed to append required component: [0x%x].";
  LODWORD(v166) = v113;
  v50 = -7;
LABEL_47:
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v50,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
    "Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize",
    v166,
    (int)v167,
    v168);
LABEL_208:
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
LABEL_242:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  if ( v185[1] )
    HeapFree(v183[0], 0, v185[1]);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x1800dc444  push    rbp
0x1800dc446  push    rbx
0x1800dc447  push    rsi
0x1800dc448  push    rdi
0x1800dc449  push    r12
0x1800dc44b  push    r13
0x1800dc44d  push    r14
0x1800dc44f  push    r15
0x1800dc451  lea     rbp, [rsp-1A8h]
0x1800dc459  sub     rsp, 2A8h
0x1800dc460  mov     [rbp+1E0h+var_1A8], 0FFFFFFFFFFFFFFFEh
0x1800dc468  mov     rax, cs:__security_cookie
0x1800dc46f  xor     rax, rsp
0x1800dc472  mov     [rbp+1E0h+var_50], rax
0x1800dc479  mov     sil, r9b
0x1800dc47c  mov     dil, r8b
0x1800dc47f  mov     bl, dl
0x1800dc481  mov     r15, rcx
0x1800dc484  mov     r14, [rbp+1E0h+arg_88]
0x1800dc48b  mov     r13, [rbp+1E0h+arg_58]
0x1800dc492  mov     r12, [rbp+1E0h+arg_60]
0x1800dc499  mov     [rbp+1E0h+var_220], r12
0x1800dc49d  mov     rax, [rbp+1E0h+arg_68]
0x1800dc4a4  mov     [rbp+1E0h+var_248], rax
0x1800dc4a8  mov     rax, [rbp+1E0h+arg_90]
0x1800dc4af  mov     [rbp+1E0h+var_250], rax
0x1800dc4b3  mov     rax, [rbp+1E0h+arg_A0]
0x1800dc4ba  mov     [rsp+2E0h+var_278], rax
0x1800dc4bf  mov     [rbp+1E0h+var_210], 0
0x1800dc4c7  xorps   xmm0, xmm0
0x1800dc4ca  movups  xmmword ptr [rbp+1E0h+var_208], xmm0
0x1800dc4ce  movups  xmmword ptr [rbp+1E0h+var_1E8], xmm0
0x1800dc4d2  call    cs:__imp_GetProcessHeap
0x1800dc4d8  mov     [rbp+1E0h+var_208], rax
0x1800dc4dc  mov     [rbp+1E0h+var_1E8], 10h
0x1800dc4e4  xorps   xmm0, xmm0
0x1800dc4e7  movdqu  [rbp+1E0h+var_1F8], xmm0
0x1800dc4ec  mov     [rbp+1E0h+var_1E8+8], 0
0x1800dc4f4  mov     [rbp+1E0h+var_208+8], 8
0x1800dc4fc  movups  xmmword ptr [rbp+1E0h+hHeap], xmm0
0x1800dc500  movups  xmmword ptr [rbp+1E0h+lpMem], xmm0
0x1800dc504  call    cs:__imp_GetProcessHeap
0x1800dc50a  mov     [rbp+1E0h+hHeap], rax
0x1800dc50e  mov     [rbp+1E0h+lpMem], 10h
0x1800dc516  xorps   xmm0, xmm0
0x1800dc519  movdqu  [rbp+1E0h+var_1C8], xmm0
0x1800dc51e  xor     ecx, ecx
0x1800dc520  mov     [rbp+1E0h+lpMem+8], rcx
0x1800dc524  mov     [rbp+1E0h+hHeap+8], 8
0x1800dc52c  mov     rax, [r12+10h]
0x1800dc531  mov     [rsp+2E0h+var_270], rax
0x1800dc536  mov     rax, [rbp+1E0h+var_248]
0x1800dc53a  cmp     [rax+10h], rcx
0x1800dc53e  setnz   [rsp+2E0h+var_268]
0x1800dc543  mov     [r15+13Dh], bl
0x1800dc54a  mov     [r15+13Eh], dil
0x1800dc551  mov     [r15+13Fh], sil
0x1800dc558  mov     eax, [rbp+1E0h+arg_20]
0x1800dc55e  mov     [r15+140h], eax
0x1800dc565  mov     eax, [rbp+1E0h+arg_28]
0x1800dc56b  mov     [r15+144h], eax
0x1800dc572  mov     al, [rbp+1E0h+arg_30]
0x1800dc578  mov     [r15+148h], al
0x1800dc57f  mov     al, [rbp+1E0h+arg_48]
0x1800dc585  mov     [r15+154h], al
0x1800dc58c  mov     eax, [rbp+1E0h+arg_38]
0x1800dc592  mov     [r15+14Ch], eax
0x1800dc599  mov     eax, [rbp+1E0h+arg_40]
0x1800dc59f  mov     [r15+150h], eax
0x1800dc5a6  mov     rax, [rbp+1E0h+arg_70]
0x1800dc5ad  mov     [r15+160h], rax
0x1800dc5b4  mov     al, [rbp+1E0h+arg_78]
0x1800dc5ba  mov     [r15+168h], al
0x1800dc5c1  mov     rax, [rbp+1E0h+arg_80]
0x1800dc5c8  mov     [r15+170h], rax
0x1800dc5cf  mov     r12, [rbp+1E0h+var_250]
0x1800dc5d3  mov     eax, [r12+280h]
0x1800dc5db  mov     [r15+138h], eax
0x1800dc5e2  mov     eax, [rbp+1E0h+arg_50]
0x1800dc5e8  cmp     [r12+280h], eax
0x1800dc5f0  setnb   al
0x1800dc5f3  mov     [r15+13Ch], al
0x1800dc5fa  lea     rcx, [r15+390h]
0x1800dc601  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,int>>,0>>::clear(void)
0x1800dc606  lea     rax, szValueBuf
0x1800dc60d  test    r14, r14
0x1800dc610  cmovnz  rax, r14
0x1800dc614  lea     rcx, [r15+178h]; unsigned __int16 *
0x1800dc61b  mov     [rsp+2E0h+var_2C0], rax
0x1800dc620  mov     r9, [r15+170h]
0x1800dc627  lea     r8, aLsLs_3; "%ls%ls"
0x1800dc62e  mov     edx, 104h; unsigned __int64
0x1800dc633  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800dc638  mov     ebx, eax
0x1800dc63a  xor     r11d, r11d
0x1800dc63d  test    eax, eax
0x1800dc63f  jns     short loc_1800DC671
0x1800dc641  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x1800dc645  lea     r9, aFailedToPrintf_0; "Failed to printf: [0x%x]."
0x1800dc64c  mov     qword ptr [rsp+2E0h+var_2B8], r9
0x1800dc651  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x1800dc655  lea     r9, aWindowsCompatA_185; "Windows::Compat::Appraiser::RegistryMar"...
0x1800dc65c  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800dc663  mov     edx, 8Dh
0x1800dc668  lea     ecx, [r11+1]
0x1800dc66c  jmp     loc_1800DCADE
0x1800dc671  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800dc677  mov     edi, 1
0x1800dc67c  and     eax, edi
0x1800dc67e  lea     rsi, aWindowsCompatA_185; "Windows::Compat::Appraiser::RegistryMar"...
0x1800dc685  lea     r14, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800dc68c  test    al, al
0x1800dc68e  jz      short loc_1800DC6AE
0x1800dc690  mov     dword ptr [rsp+2E0h+var_2C0], ebx
0x1800dc694  lea     r9, aFailedToPrintf_0; "Failed to printf: [0x%x]."
0x1800dc69b  mov     r8, rsi; char *
0x1800dc69e  mov     rdx, r14; char *
0x1800dc6a1  mov     ecx, 8Dh; unsigned int
0x1800dc6a6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800dc6ab  xor     r11d, r11d
0x1800dc6ae  mov     rbx, [rsp+2E0h+var_278]
0x1800dc6b3  test    rbx, rbx
0x1800dc6b6  jz      loc_1800DC836
0x1800dc6bc  lea     rcx, [r12+90h]
0x1800dc6c4  mov     rdx, rbx
0x1800dc6c7  call    ?FindListTableByName@DataFile@Appraiser@Compat@Windows@@SAPEAUListTable@234@AEAV?$RtlArray@PEAUListTable@Appraiser@Compat@Windows@@@@PEBG@Z; Windows::Compat::Appraiser::DataFile::FindListTableByName(RtlArray<Windows::Compat::Appraiser::ListTable *> &,ushort const *)
0x1800dc6cc  mov     [r15+380h], rax
0x1800dc6d3  xor     r11d, r11d
0x1800dc6d6  test    rax, rax
0x1800dc6d9  jnz     loc_1800DC836
0x1800dc6df  mov     [rsp+2E0h+var_2B0], rbx; char *
0x1800dc6e4  lea     rax, aFailedToFindTa_2; "Failed to find table, swallowing [%ls]."...
0x1800dc6eb  mov     qword ptr [rsp+2E0h+var_2B8], rax; int
0x1800dc6f0  mov     dword ptr [rsp+2E0h+var_2C0], 80070490h; char *
0x1800dc6f8  mov     r9, rsi; char *
0x1800dc6fb  mov     r8, r14; unsigned int
0x1800dc6fe  mov     edx, 95h; bool
0x1800dc703  mov     ecx, edi; this
0x1800dc705  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800dc70a  lea     rcx, [rbp+1E0h+var_180]; this
0x1800dc70e  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800dc713  lea     rcx, [rbp+1E0h+var_180]
0x1800dc717  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800dc71e  xor     edx, edx
0x1800dc720  test    rax, rax
0x1800dc723  cmovnz  rcx, rax; this
0x1800dc727  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800dc730  lea     r8, [rbp+1E0h+var_E0]; char *
0x1800dc737  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800dc73c  xor     r11d, r11d
0x1800dc73f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r11b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800dc746  jz      short loc_1800DC757
0x1800dc748  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800dc74f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800dc754  xor     r11d, r11d
0x1800dc757  mov     rbx, cs:qword_1802C9628
0x1800dc75e  mov     eax, [rbx]
0x1800dc760  cmp     eax, 5
0x1800dc763  jbe     loc_1800DC836
0x1800dc769  mov     rcx, [rbx+18h]
0x1800dc76d  mov     rax, [rbx+10h]
0x1800dc771  mov     rdx, 200000000000h
0x1800dc77b  test    rdx, rax
0x1800dc77e  jz      loc_1800DC836
0x1800dc784  mov     rax, rcx
0x1800dc787  and     rax, rdx
0x1800dc78a  cmp     rax, rcx
0x1800dc78d  jnz     loc_1800DC836
0x1800dc793  lea     rax, [rbp+1E0h+var_E0]
0x1800dc79a  mov     [rbp+1E0h+var_218], rax
0x1800dc79e  mov     dword ptr [rbp+1E0h+var_260], 80070490h
0x1800dc7a5  mov     [rbp+1E0h+var_240], rsi
0x1800dc7a9  mov     [rbp+1E0h+var_238], r14
0x1800dc7ad  mov     dword ptr [rsp+2E0h+var_278], 95h
0x1800dc7b5  lea     rax, szValueBuf
0x1800dc7bc  mov     [rbp+1E0h+var_258], rax
0x1800dc7c0  xorps   xmm0, xmm0
0x1800dc7c3  movups  xmmword ptr [rbp+1E0h+SystemTime.wYear], xmm0
0x1800dc7c7  lea     rcx, [rbp+1E0h+SystemTime]; lpSystemTime
0x1800dc7cb  call    cs:__imp_GetSystemTime
0x1800dc7d1  movaps  xmm0, xmmword ptr [rbp+1E0h+SystemTime.wYear]
0x1800dc7d5  movdqa  [rbp+1E0h+var_1A0], xmm0
0x1800dc7da  lea     rax, [rbp+1E0h+var_1A0]
0x1800dc7de  mov     [rsp+2E0h+var_280], rax
0x1800dc7e3  lea     rax, [rbp+1E0h+var_218]
0x1800dc7e7  mov     [rsp+2E0h+var_290], rax
0x1800dc7ec  lea     rax, [rbp+1E0h+var_260]
0x1800dc7f0  mov     [rsp+2E0h+var_298], rax
0x1800dc7f5  lea     rax, [rbp+1E0h+var_240]
0x1800dc7f9  mov     [rsp+2E0h+var_2A0], rax
0x1800dc7fe  lea     rax, [rbp+1E0h+var_238]
0x1800dc802  mov     [rsp+2E0h+var_2A8], rax
0x1800dc807  lea     rax, [rsp+2E0h+var_278]
0x1800dc80c  mov     [rsp+2E0h+var_2B0], rax
0x1800dc811  lea     rax, [rbp+1E0h+var_258]
0x1800dc815  mov     qword ptr [rsp+2E0h+var_2B8], rax
0x1800dc81a  lea     rax, [rsp+2E0h+var_280]
0x1800dc81f  mov     [rsp+2E0h+var_2C0], rax
0x1800dc824  lea     rdx, unk_1802A442B
0x1800dc82b  mov     rcx, rbx
0x1800dc82e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dc833  xor     r11d, r11d
0x1800dc836  cmp     [r15+388h], r11
0x1800dc83d  jnz     loc_1800DC9C4
0x1800dc843  lea     rcx, [r12+90h]
0x1800dc84b  lea     rbx, aFtAnyIncludein; "FT_ANY_IncludeInTelemetry"
0x1800dc852  mov     rdx, rbx
0x1800dc855  call    ?FindListTableByName@DataFile@Appraiser@Compat@Windows@@SAPEAUListTable@234@AEAV?$RtlArray@PEAUListTable@Appraiser@Compat@Windows@@@@PEBG@Z; Windows::Compat::Appraiser::DataFile::FindListTableByName(RtlArray<Windows::Compat::Appraiser::ListTable *> &,ushort const *)
0x1800dc85a  mov     [r15+388h], rax
0x1800dc861  xor     r11d, r11d
0x1800dc864  test    rax, rax
0x1800dc867  jnz     loc_1800DC9C4
0x1800dc86d  mov     [rsp+2E0h+var_2B0], rbx; char *
0x1800dc872  lea     rax, aFailedToFindTa; "Failed to find table, swallowing [%ls]."
0x1800dc879  mov     qword ptr [rsp+2E0h+var_2B8], rax; int
0x1800dc87e  mov     dword ptr [rsp+2E0h+var_2C0], 80070490h; char *
0x1800dc886  mov     r9, rsi; char *
0x1800dc889  mov     r8, r14; unsigned int
0x1800dc88c  mov     edx, 9Fh; bool
0x1800dc891  mov     ecx, edi; this
0x1800dc893  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800dc898  lea     rcx, [rbp+1E0h+var_180]; this
0x1800dc89c  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800dc8a1  lea     rcx, [rbp+1E0h+var_180]
0x1800dc8a5  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800dc8ac  xor     edx, edx
0x1800dc8ae  test    rax, rax
0x1800dc8b1  cmovnz  rcx, rax; this
0x1800dc8b5  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800dc8be  lea     r8, [rbp+1E0h+var_E0]; char *
0x1800dc8c5  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800dc8ca  xor     r11d, r11d
0x1800dc8cd  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r11b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800dc8d4  jz      short loc_1800DC8E5
0x1800dc8d6  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800dc8dd  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800dc8e2  xor     r11d, r11d
0x1800dc8e5  mov     rbx, cs:qword_1802C9628
0x1800dc8ec  mov     eax, [rbx]
0x1800dc8ee  cmp     eax, 5
0x1800dc8f1  jbe     loc_1800DC9C4
0x1800dc8f7  mov     rcx, [rbx+18h]
0x1800dc8fb  mov     rax, [rbx+10h]
0x1800dc8ff  mov     rdx, 200000000000h
0x1800dc909  test    rdx, rax
0x1800dc90c  jz      loc_1800DC9C4
0x1800dc912  mov     rax, rcx
0x1800dc915  and     rax, rdx
0x1800dc918  cmp     rax, rcx
0x1800dc91b  jnz     loc_1800DC9C4
0x1800dc921  lea     rax, [rbp+1E0h+var_E0]
0x1800dc928  mov     [rsp+2E0h+var_280], rax
0x1800dc92d  mov     dword ptr [rsp+2E0h+var_278], 80070490h
0x1800dc935  mov     [rbp+1E0h+var_258], rsi
0x1800dc939  mov     [rbp+1E0h+var_238], r14
0x1800dc93d  mov     dword ptr [rbp+1E0h+var_260], 9Fh
0x1800dc944  lea     rax, szValueBuf
0x1800dc94b  mov     [rbp+1E0h+var_240], rax
0x1800dc94f  xorps   xmm0, xmm0
0x1800dc952  movups  xmmword ptr [rbp+1E0h+SystemTime.wYear], xmm0
0x1800dc956  lea     rcx, [rbp+1E0h+SystemTime]; lpSystemTime
0x1800dc95a  call    cs:__imp_GetSystemTime
0x1800dc960  movaps  xmm0, xmmword ptr [rbp+1E0h+SystemTime.wYear]
0x1800dc964  movdqa  [rbp+1E0h+var_1A0], xmm0
0x1800dc969  lea     rax, [rbp+1E0h+var_1A0]
0x1800dc96d  mov     [rbp+1E0h+var_218], rax
0x1800dc971  lea     rax, [rsp+2E0h+var_280]
0x1800dc976  mov     [rsp+2E0h+var_290], rax
0x1800dc97b  lea     rax, [rsp+2E0h+var_278]
0x1800dc980  mov     [rsp+2E0h+var_298], rax
0x1800dc985  lea     rax, [rbp+1E0h+var_258]
0x1800dc989  mov     [rsp+2E0h+var_2A0], rax
0x1800dc98e  lea     rax, [rbp+1E0h+var_238]
0x1800dc992  mov     [rsp+2E0h+var_2A8], rax
0x1800dc997  lea     rax, [rbp+1E0h+var_260]
0x1800dc99b  mov     [rsp+2E0h+var_2B0], rax; char *
0x1800dc9a0  lea     rax, [rbp+1E0h+var_240]
0x1800dc9a4  mov     qword ptr [rsp+2E0h+var_2B8], rax
0x1800dc9a9  lea     rax, [rbp+1E0h+var_218]
0x1800dc9ad  mov     [rsp+2E0h+var_2C0], rax
0x1800dc9b2  lea     rdx, unk_1802A448E
0x1800dc9b9  mov     rcx, rbx
0x1800dc9bc  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dc9c1  xor     r11d, r11d
0x1800dc9c4  mov     rax, [r13+10h]
0x1800dc9c8  test    rax, rax
0x1800dc9cb  jz      loc_1800DCAE8
0x1800dc9d1  mov     r12, r11
0x1800dc9d4  mov     r8, [rbp+1E0h+var_250]
0x1800dc9d8  add     r8, 120h
0x1800dc9df  mov     [rsp+2E0h+var_278], r8
0x1800dc9e4  mov     rdx, r11
0x1800dc9e7  cmp     r12, rax
0x1800dc9ea  jnb     short loc_1800DCA0D
0x1800dc9ec  mov     [rsp+2E0h+var_280], r11
0x1800dc9f1  mov     rax, r12
0x1800dc9f4  mul     qword ptr [r13+8]
0x1800dc9f8  test    rdx, rdx
0x1800dc9fb  jnz     short loc_1800DCA0A
0x1800dc9fd  mov     rcx, [r13+28h]
  ... truncated ...
```
