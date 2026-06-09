# UsageAndQualityInsights::Database::FactStoreDatabase::ConvertToDBFact(UsageAndQualityInsights::Facts::FactRecord const &)

- ea: `0x180045168`
- end: `0x180046cea`
- name: `?ConvertToDBFact@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAA?AV?$optional@UFactStoreRecord@Database@UsageAndQualityInsights@@@std@@AEBUFactRecord@Facts@3@@Z`
- size: `7042`
- prototype: ``
- caller_count: `1`
- callee_count: `47`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18004aec4`

## callees

- `0x1800033d0`
- `0x180003870`
- `0x1800040a0`
- `0x180004140`
- `0x180005e7c`
- `0x180006a90`
- `0x18000c844`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180011d6c`
- `0x180012dd4`
- `0x180012ea4`
- `0x180019458`
- `0x18001a8f4`
- `0x18001a9b0`
- `0x180020650`
- `0x180022230`
- `0x180022bb0`
- `0x180022d38`
- `0x180022de4`
- `0x180022fac`
- `0x180023334`
- `0x18002379c`
- `0x18002b470`
- `0x18002b510`
- `0x180042510`
- `0x1800439cc`
- `0x180045168`
- `0x18004c51c`
- `0x18004c634`
- `0x18004e078`
- `0x18004e0fc`
- `0x18004e180`
- `0x18004e1d8`
- `0x1800fd4fc`
- `0x1800fd5bc`
- `0x1800fd640`
- `0x1800fd6f0`
- `0x1800fd7b0`
- `0x1800fd834`
- `0x1800fdc08`
- `0x1800fdf1c`
- `0x1800ff804`
- `0x1800ff850`
- `0x1800ff89c`
- `0x1800ffc18`
- `0x180100788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045b1f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045b2a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045d50`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045b1f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045b2a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180045d50`

## string_xrefs

- `0x180046576`: `overwrite::PartA_Ext_App_ExpId`
- `0x180046192`: `overwrite::PartA_Ext_Os_BootId`
- `0x180046cd7`: `onecore\base\usageandqualityinsights\service\lib\configuration\uqiconfig.cpp`
- `0x180045580`: `onecore\base\usageandqualityinsights\service\lib\factstore\factkey.cpp`
- `0x180045a55`: `onecore\base\usageandqualityinsights\service\lib\factstore\factmetric.cpp`
- `0x180045c6c`: `onecore\base\usageandqualityinsights\service\lib\factstore\factmetric.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall UsageAndQualityInsights::Database::FactStoreDatabase::ConvertToDBFact(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 Dimension; // rax
  __int64 v6; // rax
  wchar_t *DimensionOrDefault; // rax
  _BYTE *v8; // r15
  wchar_t *v9; // rbx
  size_t v10; // r8
  const wchar_t *p_S1; // r9
  wchar_t *v12; // rax
  unsigned __int64 v13; // rcx
  char v14; // al
  wchar_t **v15; // r9
  __int64 v16; // rax
  wchar_t *v17; // rcx
  __int64 v18; // rax
  __int64 MetricName; // rax
  wchar_t *v20; // rcx
  __int64 v21; // rax
  int v22; // r12d
  __int64 v23; // rsi
  wchar_t *v24; // r8
  __int64 *v25; // rcx
  __int64 **v26; // rdx
  __int64 *i; // rax
  __int64 *j; // rdx
  _QWORD *v29; // rbx
  void *v30; // rcx
  __int64 v31; // rax
  void *v32; // rbx
  __int64 v33; // r14
  int v34; // eax
  HANDLE ProcessHeap; // rax
  __int64 v36; // rsi
  wchar_t *v37; // rbx
  int v38; // eax
  HANDLE v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  wchar_t *v44; // rbx
  int v45; // eax
  HANDLE v46; // rax
  __int64 v47; // rax
  wchar_t *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  wchar_t *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  wchar_t *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  const wchar_t *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  wchar_t *v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rax
  wchar_t *v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rax
  wchar_t *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  wchar_t *v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rax
  wchar_t *v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rax
  wchar_t *v76; // rcx
  __int64 v77; // rax
  wchar_t *v78; // rax
  wchar_t *v79; // rax
  wchar_t *v80; // rax
  wchar_t *v81; // rax
  wchar_t *v82; // rax
  wchar_t *v83; // rax
  __int64 v84; // rax
  wchar_t *v85; // rcx
  __int64 v86; // rax
  __int64 result; // rax
  const char *v88; // r9
  const char *v89; // rdx
  int v90; // [rsp+20h] [rbp-428h]
  int v91; // [rsp+20h] [rbp-428h]
  int v92; // [rsp+20h] [rbp-428h]
  char *v93; // [rsp+28h] [rbp-420h]
  LPVOID lpMem; // [rsp+30h] [rbp-418h] BYREF
  int v95; // [rsp+38h] [rbp-410h]
  __int64 v96; // [rsp+40h] [rbp-408h] BYREF
  int v97; // [rsp+48h] [rbp-400h]
  _QWORD v98[2]; // [rsp+50h] [rbp-3F8h] BYREF
  __int64 v99; // [rsp+60h] [rbp-3E8h]
  void **v100; // [rsp+70h] [rbp-3D8h] BYREF
  const char *v101; // [rsp+78h] [rbp-3D0h] BYREF
  __int128 v102; // [rsp+88h] [rbp-3C0h] BYREF
  __int64 v103; // [rsp+98h] [rbp-3B0h]
  __int64 v104; // [rsp+A0h] [rbp-3A8h]
  __int128 v105; // [rsp+A8h] [rbp-3A0h] BYREF
  __int64 v106; // [rsp+B8h] [rbp-390h]
  __int64 v107; // [rsp+C0h] [rbp-388h]
  wchar_t *S1; // [rsp+D0h] [rbp-378h] BYREF
  __int64 v109; // [rsp+D8h] [rbp-370h]
  size_t N; // [rsp+E0h] [rbp-368h]
  unsigned __int64 v111; // [rsp+E8h] [rbp-360h]
  __int128 v112; // [rsp+F0h] [rbp-358h] BYREF
  __int64 v113; // [rsp+100h] [rbp-348h]
  __int64 v114; // [rsp+108h] [rbp-340h]
  char *v115[4]; // [rsp+110h] [rbp-338h] BYREF
  _BYTE v116[8]; // [rsp+130h] [rbp-318h] BYREF
  __int128 v117; // [rsp+138h] [rbp-310h]
  __int64 v118; // [rsp+148h] [rbp-300h]
  __int64 v119; // [rsp+150h] [rbp-2F8h]
  __int64 v120; // [rsp+158h] [rbp-2F0h]
  __int64 v121; // [rsp+160h] [rbp-2E8h]
  char v122; // [rsp+168h] [rbp-2E0h]
  char v123; // [rsp+169h] [rbp-2DFh]
  __int128 v124; // [rsp+170h] [rbp-2D8h] BYREF
  __int64 v125; // [rsp+180h] [rbp-2C8h]
  __int64 v126; // [rsp+188h] [rbp-2C0h]
  __int64 v127; // [rsp+190h] [rbp-2B8h]
  int v128; // [rsp+198h] [rbp-2B0h]
  __int128 v129; // [rsp+1A0h] [rbp-2A8h] BYREF
  __int64 v130; // [rsp+1B0h] [rbp-298h]
  __int64 v131; // [rsp+1B8h] [rbp-290h]
  __int64 v132; // [rsp+1C0h] [rbp-288h]
  __int64 v133; // [rsp+1C8h] [rbp-280h]
  __int64 v134; // [rsp+1D0h] [rbp-278h]
  __int128 v135; // [rsp+1D8h] [rbp-270h] BYREF
  __int64 v136; // [rsp+1E8h] [rbp-260h]
  __int64 v137; // [rsp+1F0h] [rbp-258h]
  __int64 v138; // [rsp+1F8h] [rbp-250h]
  double Min; // [rsp+200h] [rbp-248h]
  double Max; // [rsp+208h] [rbp-240h]
  double Sum; // [rsp+210h] [rbp-238h]
  __int64 v142; // [rsp+218h] [rbp-230h]
  __int64 v143; // [rsp+220h] [rbp-228h]
  __int128 v144; // [rsp+228h] [rbp-220h] BYREF
  __int64 v145; // [rsp+238h] [rbp-210h]
  __int64 v146; // [rsp+240h] [rbp-208h]
  __int128 v147; // [rsp+248h] [rbp-200h] BYREF
  __int64 v148; // [rsp+258h] [rbp-1F0h]
  __int64 v149; // [rsp+260h] [rbp-1E8h]
  __int128 v150; // [rsp+268h] [rbp-1E0h] BYREF
  __int64 v151; // [rsp+278h] [rbp-1D0h]
  __int64 v152; // [rsp+280h] [rbp-1C8h]
  __int128 v153; // [rsp+288h] [rbp-1C0h] BYREF
  __int64 v154; // [rsp+298h] [rbp-1B0h]
  __int64 v155; // [rsp+2A0h] [rbp-1A8h]
  __int64 v156; // [rsp+2A8h] [rbp-1A0h]
  char AggregationWindowType; // [rsp+2B0h] [rbp-198h]
  __int64 v158; // [rsp+2B8h] [rbp-190h]
  __int64 v159; // [rsp+2C0h] [rbp-188h]
  __int64 v160; // [rsp+2C8h] [rbp-180h]
  __int64 v161; // [rsp+2D0h] [rbp-178h]
  __int64 v162; // [rsp+2D8h] [rbp-170h]
  __int64 v163; // [rsp+2E0h] [rbp-168h]
  __int64 v164; // [rsp+2E8h] [rbp-160h]
  __int128 v165; // [rsp+2F0h] [rbp-158h] BYREF
  __int64 v166; // [rsp+300h] [rbp-148h]
  __int64 v167; // [rsp+308h] [rbp-140h]
  __int128 v168; // [rsp+310h] [rbp-138h] BYREF
  __int64 v169; // [rsp+320h] [rbp-128h]
  __int64 v170; // [rsp+328h] [rbp-120h]
  __int128 v171; // [rsp+330h] [rbp-118h] BYREF
  __int64 v172; // [rsp+340h] [rbp-108h]
  __int64 v173; // [rsp+348h] [rbp-100h]
  __int128 v174; // [rsp+350h] [rbp-F8h] BYREF
  __int64 v175; // [rsp+360h] [rbp-E8h]
  __int64 v176; // [rsp+368h] [rbp-E0h]
  __int128 v177; // [rsp+370h] [rbp-D8h] BYREF
  __int64 v178; // [rsp+380h] [rbp-C8h]
  __int64 v179; // [rsp+388h] [rbp-C0h]
  __int128 v180; // [rsp+390h] [rbp-B8h] BYREF
  __int64 v181; // [rsp+3A0h] [rbp-A8h]
  __int64 v182; // [rsp+3A8h] [rbp-A0h]
  char v183; // [rsp+3B0h] [rbp-98h]
  int v184; // [rsp+3B4h] [rbp-94h]
  int v185; // [rsp+3B8h] [rbp-90h]
  __int64 v186; // [rsp+3C0h] [rbp-88h]
  int v187; // [rsp+3C8h] [rbp-80h]
  __int64 v188; // [rsp+3D0h] [rbp-78h]
  __int64 v189; // [rsp+3D8h] [rbp-70h]
  __int64 v190; // [rsp+3E0h] [rbp-68h]
  __int128 v191; // [rsp+3E8h] [rbp-60h] BYREF
  __int64 v192; // [rsp+3F8h] [rbp-50h]
  __int64 v193; // [rsp+400h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]

  v99 = a2;
  v95 = 0;
  UsageAndQualityInsightsCoreLogging::TraceLoggingInfo("ConvertToDBFact");
  try
  {
    v117 = 0;
    v118 = 0;
    v119 = 15;
    LOBYTE(v117) = 0;
    v124 = 0;
    v125 = 0;
    v126 = 15;
    LOBYTE(v124) = 0;
    v129 = 0;
    v130 = 0;
    v131 = 15;
    LOBYTE(v129) = 0;
    v135 = 0;
    v136 = 0;
    v137 = 15;
    LOBYTE(v135) = 0;
    v144 = 0;
    v145 = 0;
    v146 = 15;
    LOBYTE(v144) = 0;
    v147 = 0;
    v148 = 0;
    v149 = 15;
    LOBYTE(v147) = 0;
    v150 = 0;
    v151 = 0;
    v152 = 15;
    LOBYTE(v150) = 0;
    v153 = 0;
    v154 = 0;
    v155 = 15;
    LOBYTE(v153) = 0;
    v165 = 0;
    v166 = 0;
    v167 = 15;
    LOBYTE(v165) = 0;
    v168 = 0;
    v169 = 0;
    v170 = 15;
    LOBYTE(v168) = 0;
    v171 = 0;
    v172 = 0;
    v173 = 15;
    LOBYTE(v171) = 0;
    v174 = 0;
    v175 = 0;
    v176 = 15;
    LOBYTE(v174) = 0;
    v177 = 0;
    v178 = 0;
    v179 = 15;
    LOBYTE(v177) = 0;
    v180 = 0;
    v181 = 0;
    v182 = 15;
    LOBYTE(v180) = 0;
    v191 = 0;
    v192 = 0;
    v193 = 15;
    LOBYTE(v191) = 0;
    v102 = 0;
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::factTime", 0x10u);
    Dimension = UsageAndQualityInsights::Facts::FactKey::GetDimension(a3, &v105, &v102);
    v6 = UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(Dimension);
    UsageAndQualityInsights::Utilities::TimePointFromFileTime(&S1, v6);
    std::wstring::~wstring((char **)&v105);
    v120 = (__int64)S1 / 10000;
    S1 = (wchar_t *)&v102;
    v102 = 0;
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"0", 1u);
    v112 = 0;
    v113 = 0;
    v114 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v112, L"system::factFlags", 0x11u);
    DimensionOrDefault = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(
                                      a3,
                                      &v105,
                                      &v112,
                                      &v102);
    v121 = std::stoull(DimensionOrDefault);
    std::wstring::~wstring((char **)&v105);
    v8 = a3 + 3;
    v122 = *((_BYTE *)a3 + 24);
    v102 = 0;
    v103 = 0;
    v104 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::factSource", 0x12u);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
      a3 + 1,
      &S1,
      &v102);
    std::wstring::~wstring((char **)&v102);
    v9 = S1;
    LOBYTE(v90) = S1 == (wchar_t *)a3[1];
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factkey.cpp",
      (const char *)0x80070057LL,
      v90,
      (bool)"Fact source key not found in dimensions",
      (const char *)lpMem);
    std::wstring::wstring((__int64)&S1, (__int64)(v9 + 32));
    v10 = N;
    p_S1 = (const wchar_t *)&S1;
    v12 = S1;
    v13 = v111;
    if ( v111 > 7 )
      p_S1 = S1;
    if ( N == 12 )
    {
      if ( !wmemcmp(p_S1, L"MetricsEvent", 0xCu) )
      {
        v14 = 0;
LABEL_13:
        v123 = v14;
        std::wstring::~wstring((char **)&S1);
        S1 = (wchar_t *)&v102;
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, &::S1, 0);
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"system::factName", 0x10u);
        v16 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v105, &v102);
        if ( *(_QWORD *)(v16 + 24) <= 7u )
          v17 = (wchar_t *)v16;
        else
          v17 = *(wchar_t **)v16;
        v18 = *(_QWORD *)(v16 + 16);
        v112 = 0;
        v113 = 0;
        v114 = 15;
        LOBYTE(v112) = 0;
        v95 = 6;
        S1 = v17;
        v109 = v18;
        to_utf8(&S1, &v112);
        std::string::operator=(&v124, &v112);
        std::string::~string((char **)&v112);
        std::wstring::~wstring(v115);
        v127 = *a3;
        v128 = (unsigned __int8)*v8;
        MetricName = UsageAndQualityInsights::Facts::FactKey::GetMetricName(a3, v115);
        if ( *(_QWORD *)(MetricName + 24) <= 7u )
          v20 = (wchar_t *)MetricName;
        else
          v20 = *(wchar_t **)MetricName;
        v21 = *(_QWORD *)(MetricName + 16);
        v112 = 0;
        v113 = 0;
        v114 = 15;
        LOBYTE(v112) = 0;
        v95 = 10;
        S1 = v20;
        v109 = v21;
        to_utf8(&S1, &v112);
        std::string::operator=(&v129, &v112);
        v22 = 2;
        std::string::~string((char **)&v112);
        std::wstring::~wstring(v115);
        v23 = 0;
        if ( !*v8 && *((_DWORD *)a3 + 28) != 160 )
        {
          std::map<long,double>::map<long,double>(&S1, a3 + 18);
          v22 = 18;
          v24 = S1;
          v25 = *(__int64 **)S1;
          while ( !*((_BYTE *)v25 + 25) )
          {
            v23 |= 1LL << (*((_DWORD *)v25 + 8) / *((_DWORD *)a3 + 30));
            v26 = (__int64 **)v25[2];
            if ( *((_BYTE *)v26 + 25) )
            {
              for ( i = (__int64 *)v25[1]; !*((_BYTE *)i + 25) && v25 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                v25 = i;
              v25 = i;
            }
            else
            {
              v25 = (__int64 *)v25[2];
              for ( j = *v26; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                v25 = j;
            }
          }
          v29 = (_QWORD *)*((_QWORD *)S1 + 1);
          if ( !*((_BYTE *)v29 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<std::pair<long const,double>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<long const,double>,void *>>>(
                &S1,
                &S1,
                v29[2]);
              v30 = v29;
              v29 = (_QWORD *)*v29;
              operator delete(v30, 0x30u);
            }
            while ( !*((_BYTE *)v29 + 25) );
            v24 = S1;
          }
          operator delete(v24, 0x30u);
        }
        v132 = v23;
        v133 = a3[22] / 10000;
        v31 = UsageAndQualityInsights::Facts::FactMetric::ToJson(a3 + 3, &lpMem);
        winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(v31, &S1);
        if ( lpMem )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&lpMem);
        v97 = 0;
        v115[0] = (char *)S1;
        winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
          (const struct winrt::param::hstring *)&v112,
          (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)v115);
        *(_QWORD *)&v105 = *(_QWORD *)winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames::Sha256();
        winrt::Windows::Security::Cryptography::Core::HashAlgorithmProvider::OpenAlgorithm((const struct winrt::param::hstring *)v98);
        v32 = lpMem;
        v33 = -1;
        if ( lpMem )
        {
          v34 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v34 )
          {
            if ( v34 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v32);
          }
          lpMem = 0;
        }
        winrt::impl::consume_Windows_Security_Cryptography_Core_IHashAlgorithmProvider<winrt::Windows::Security::Cryptography::Core::IHashAlgorithmProvider>::HashData(
          v98,
          &v96,
          &v112);
        LOBYTE(v91) = (unsigned int)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::Length(&v96) < 8;
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factmetric.cpp",
          (const char *)0x8000000BLL,
          v91,
          (bool)"Hash length is less than size of size_t",
          (const char *)lpMem);
        v36 = *(_QWORD *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(&v96);
        if ( v96 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v96);
        if ( v98[0] )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v98);
        if ( (_QWORD)v112 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v112);
        v37 = S1;
        if ( S1 )
        {
          v38 = _InterlockedDecrement((volatile signed __int32 *)S1 + 6);
          if ( v38 )
          {
            if ( v38 < 0 )
              abort();
          }
          else
          {
            v39 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v39, 0, v37);
          }
        }
        v134 = v36;
        v40 = UsageAndQualityInsights::Facts::ExponentialHistogram::ToJson(a3 + 14, &lpMem);
        v41 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                           v40,
                           &S1);
        if ( v41 )
          v42 = *(const wchar_t **)(v41 + 16);
        else
          v42 = &::S1;
        v43 = -1;
        do
          ++v43;
        while ( v42[v43] );
        v102 = 0;
        v103 = 0;
        v104 = 15;
        LOBYTE(v102) = 0;
        v95 = v22 | 0x20;
        *(_QWORD *)&v112 = v42;
        *((_QWORD *)&v112 + 1) = v43;
        to_utf8(&v112, &v102);
        std::string::operator=(&v135, &v102);
        std::string::~string((char **)&v102);
        v44 = S1;
        if ( S1 )
        {
          v45 = _InterlockedDecrement((volatile signed __int32 *)S1 + 6);
          if ( v45 )
          {
            if ( v45 < 0 )
              abort();
          }
          else
          {
            v46 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v46, 0, v44);
          }
          S1 = 0;
        }
        if ( lpMem )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&lpMem);
        v138 = a3[4];
        Sum = UsageAndQualityInsights::Facts::FactMetric::GetSum((UsageAndQualityInsights::Facts::FactMetric *)(a3 + 3));
        Min = UsageAndQualityInsights::Facts::FactMetric::GetMin((UsageAndQualityInsights::Facts::FactMetric *)(a3 + 3));
        Max = UsageAndQualityInsights::Facts::FactMetric::GetMax((UsageAndQualityInsights::Facts::FactMetric *)(a3 + 3));
        LOBYTE(v92) = *v8 != 0;
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factmetric.cpp",
          (const char *)0x80070057LL,
          v92,
          (bool)"GetSOS() called on non-continuous metric",
          (const char *)lpMem);
        v142 = a3[11];
        v143 = a3[12];
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::contextId", 0x11u);
        v47 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v47 + 24) <= 7u )
          v48 = (wchar_t *)v47;
        else
          v48 = *(wchar_t **)v47;
        S1 = v48;
        v109 = *(_QWORD *)(v47 + 16);
        v49 = to_utf8(v115, &S1);
        std::string::operator=(&v144, v49);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::metricApp", 0x11u);
        v50 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v50 + 24) <= 7u )
          v51 = (wchar_t *)v50;
        else
          v51 = *(wchar_t **)v50;
        S1 = v51;
        v109 = *(_QWORD *)(v50 + 16);
        v52 = to_utf8(v115, &S1);
        std::string::operator=(&v147, v52);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::metricSession", 0x15u);
        v53 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v53 + 24) <= 7u )
          v54 = (wchar_t *)v53;
        else
          v54 = *(wchar_t **)v53;
        S1 = v54;
        v109 = *(_QWORD *)(v53 + 16);
        v55 = to_utf8(v115, &S1);
        std::string::operator=(&v150, v55);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        v56 = UsageAndQualityInsights::Facts::FactKey::ToJson(a3, &S1);
        v57 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                           v56,
                           &lpMem);
        if ( v57 )
          v58 = *(const wchar_t **)(v57 + 16);
        else
          v58 = &::S1;
        do
          ++v33;
        while ( v58[v33] );
        *(_QWORD *)&v112 = v58;
        *((_QWORD *)&v112 + 1) = v33;
        v59 = to_utf8(v115, &v112);
        std::string::operator=(&v153, v59);
        std::string::~string(v115);
        winrt::hstring::~hstring((winrt::hstring *)&lpMem);
        if ( S1 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&S1);
        v156 = a3[22] / 10000;
        AggregationWindowType = UsageAndQualityInsights::Facts::FactKey::GetAggregationWindowType(a3);
        v158 = (a3[22] - a3[21]) / 10000;
        v159 = 0;
        v160 = *(_QWORD *)UsageAndQualityInsights::Facts::FactKey::GetDayTimeBin(a3, &S1) / 10000LL;
        v161 = *(_QWORD *)UsageAndQualityInsights::Facts::FactKey::GetHourTimeBin(a3, &S1) / 10000LL;
        v162 = a3[5];
        v163 = a3[6];
        v164 = a3[7];
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"overwrite::PartA_Ext_Os_BootId", 0x1Eu);
        v60 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v60 + 24) <= 7u )
          v61 = (wchar_t *)v60;
        else
          v61 = *(wchar_t **)v60;
        S1 = v61;
        v109 = *(_QWORD *)(v60 + 16);
        v62 = to_utf8(v115, &S1);
        std::string::operator=(&v165, v62);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::partA__utc__shellId", 0x1Bu);
        v63 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v63 + 24) <= 7u )
          v64 = (wchar_t *)v63;
        else
          v64 = *(wchar_t **)v63;
        S1 = v64;
        v109 = *(_QWORD *)(v63 + 16);
        v65 = to_utf8(v115, &S1);
        std::string::operator=(&v168, v65);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::eTag", 0xCu);
        v66 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v66 + 24) <= 7u )
          v67 = (wchar_t *)v66;
        else
          v67 = *(wchar_t **)v66;
        S1 = v67;
        v109 = *(_QWORD *)(v66 + 16);
        v68 = to_utf8(v115, &S1);
        std::string::operator=(&v171, v68);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::buildFlight", 0x13u);
        v69 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v69 + 24) <= 7u )
          v70 = (wchar_t *)v69;
        else
          v70 = *(wchar_t **)v69;
        S1 = v70;
        v109 = *(_QWORD *)(v69 + 16);
        v71 = to_utf8(v115, &S1);
        std::string::operator=(&v174, v71);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"overwrite::PartA_Ext_App_ExpId", 0x1Eu);
        v72 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v72 + 24) <= 7u )
          v73 = (wchar_t *)v72;
        else
          v73 = *(wchar_t **)v72;
        S1 = v73;
        v109 = *(_QWORD *)(v72 + 16);
        v74 = to_utf8(v115, &S1);
        std::string::operator=(&v177, v74);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::osLoginId", 0x11u);
        v75 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v75 + 24) <= 7u )
          v76 = (wchar_t *)v75;
        else
          v76 = *(wchar_t **)v75;
        S1 = v76;
        v109 = *(_QWORD *)(v75 + 16);
        v77 = to_utf8(v115, &S1);
        std::string::operator=(&v180, v77);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        v183 = 3;
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::entityFlag", 0x12u);
        v78 = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v102, &v105);
        v184 = std::stoi(v78);
        std::wstring::~wstring(v115);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::telemetryLevel", 0x16u);
        v79 = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v102, &v105);
        v185 = std::stoi(v79);
        std::wstring::~wstring(v115);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::obsPolicies", 0x13u);
        v80 = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v102, &v105);
        v186 = std::stoull(v80);
        std::wstring::~wstring(v115);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::qualityFlags", 0x14u);
        v81 = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v102, &v105);
        v187 = std::stoi(v81);
        std::wstring::~wstring(v115);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::flushCounter", 0x14u);
        v82 = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v102, &v105);
        v188 = std::stoull(v82);
        std::wstring::~wstring(v115);
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, L"0", 1u);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::flushTime", 0x11u);
        v83 = (wchar_t *)UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, v115, &v102, &v105);
        v189 = std::stoull(v83);
        std::wstring::~wstring(v115);
        v190 = 0;
        S1 = (wchar_t *)&v105;
        v105 = 0;
        v106 = 0;
        v107 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v105, &::S1, 0);
        v102 = 0;
        v103 = 0;
        v104 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v102, L"system::dimPreserve", 0x13u);
        v84 = UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(a3, &v112, &v102, &v105);
        if ( *(_QWORD *)(v84 + 24) <= 7u )
          v85 = (wchar_t *)v84;
        else
          v85 = *(wchar_t **)v84;
        S1 = v85;
        v109 = *(_QWORD *)(v84 + 16);
        v86 = to_utf8(v115, &S1);
        std::string::operator=(&v191, v86);
        std::string::~string(v115);
        std::wstring::~wstring((char **)&v112);
        UsageAndQualityInsights::Database::FactStoreRecord::FactStoreRecord(a2, v116);
        *(_BYTE *)(a2 + 728) = 1;
        UsageAndQualityInsights::Database::FactStoreRecord::~FactStoreRecord((UsageAndQualityInsights::Database::FactStoreRecord *)v116);
        return a2;
      }
      v13 = v111;
      v10 = N;
      v12 = S1;
    }
    v15 = &S1;
    if ( v13 > 7 )
      v15 = (wchar_t **)v12;
    if ( v10 != 3 || wmemcmp((const wchar_t *)v15, L"TIP", 3u) )
    {
      v88 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\uqiconfig.cpp",
        v88,
        (int)"Unknown FactSourceType value",
        v93);
    }
    v14 = 1;
    goto LABEL_13;
  }
  catch ( std::exception v100 )
  {
    v89 = "Unknown exception";
    if ( v101 )
      v89 = v101;
    UsageAndQualityInsightsCoreLogging::TraceLoggingError("Error while converting fact to db record: %s", v89);
    *(_BYTE *)(v99 + 728) = 0;
    v100 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v101);
    UsageAndQualityInsights::Database::FactStoreRecord::~FactStoreRecord((UsageAndQualityInsights::Database::FactStoreRecord *)v116);
    return v99;
  }
  return result;
}

```

## disassembly

```asm
0x180045168  mov     [rsp+arg_0], rbx
0x18004516d  mov     [rsp+arg_18], rsi
0x180045172  push    rdi
0x180045173  push    r12
0x180045175  push    r13
0x180045177  push    r14
0x180045179  push    r15
0x18004517b  sub     rsp, 420h
0x180045182  mov     rax, cs:__security_cookie
0x180045189  xor     rax, rsp
0x18004518c  mov     [rsp+448h+var_38], rax
0x180045194  mov     rdi, r8
0x180045197  mov     r13, rdx
0x18004519a  mov     [rsp+448h+var_3E8], rdx
0x18004519f  xor     r14d, r14d
0x1800451a2  mov     [rsp+448h+var_410], r14d
0x1800451a7  lea     rcx, aConverttodbfac; "ConvertToDBFact"
0x1800451ae  call    ?TraceLoggingInfo@UsageAndQualityInsightsCoreLogging@@SAXPEBDZZ; UsageAndQualityInsightsCoreLogging::TraceLoggingInfo(char const *,...)
0x1800451b3  xorps   xmm0, xmm0
0x1800451b6  movups  [rsp+448h+var_310], xmm0
0x1800451be  mov     [rsp+448h+var_300], r14
0x1800451c6  lea     eax, [r14+0Fh]
0x1800451ca  mov     [rsp+448h+var_2F8], rax
0x1800451d2  mov     byte ptr [rsp+448h+var_310], r14b
0x1800451da  movups  [rsp+448h+var_2D8], xmm0
0x1800451e2  mov     [rsp+448h+var_2C8], r14
0x1800451ea  mov     [rsp+448h+var_2C0], rax
0x1800451f2  mov     byte ptr [rsp+448h+var_2D8], r14b
0x1800451fa  movups  [rsp+448h+var_2A8], xmm0
0x180045202  mov     [rsp+448h+var_298], r14
0x18004520a  mov     [rsp+448h+var_290], rax
0x180045212  mov     byte ptr [rsp+448h+var_2A8], r14b
0x18004521a  movups  [rsp+448h+var_270], xmm0
0x180045222  mov     [rsp+448h+var_260], r14
0x18004522a  mov     [rsp+448h+var_258], rax
0x180045232  mov     byte ptr [rsp+448h+var_270], r14b
0x18004523a  movups  [rsp+448h+var_220], xmm0
0x180045242  mov     [rsp+448h+var_210], r14
0x18004524a  mov     [rsp+448h+var_208], rax
0x180045252  mov     byte ptr [rsp+448h+var_220], r14b
0x18004525a  movups  [rsp+448h+var_200], xmm0
0x180045262  mov     [rsp+448h+var_1F0], r14
0x18004526a  mov     [rsp+448h+var_1E8], rax
0x180045272  mov     byte ptr [rsp+448h+var_200], r14b
0x18004527a  movups  [rsp+448h+var_1E0], xmm0
0x180045282  mov     [rsp+448h+var_1D0], r14
0x18004528a  mov     [rsp+448h+var_1C8], rax
0x180045292  mov     byte ptr [rsp+448h+var_1E0], r14b
0x18004529a  movups  [rsp+448h+var_1C0], xmm0
0x1800452a2  mov     [rsp+448h+var_1B0], r14
0x1800452aa  mov     [rsp+448h+var_1A8], rax
0x1800452b2  mov     byte ptr [rsp+448h+var_1C0], r14b
0x1800452ba  movups  [rsp+448h+var_158], xmm0
0x1800452c2  mov     [rsp+448h+var_148], r14
0x1800452ca  mov     [rsp+448h+var_140], rax
0x1800452d2  mov     byte ptr [rsp+448h+var_158], r14b
0x1800452da  movups  [rsp+448h+var_138], xmm0
0x1800452e2  mov     [rsp+448h+var_128], r14
0x1800452ea  mov     [rsp+448h+var_120], rax
0x1800452f2  mov     byte ptr [rsp+448h+var_138], r14b
0x1800452fa  movups  [rsp+448h+var_118], xmm0
0x180045302  mov     [rsp+448h+var_108], r14
0x18004530a  mov     [rsp+448h+var_100], rax
0x180045312  mov     byte ptr [rsp+448h+var_118], r14b
0x18004531a  movups  [rsp+448h+var_F8], xmm0
0x180045322  mov     [rsp+448h+var_E8], r14
0x18004532a  mov     [rsp+448h+var_E0], rax
0x180045332  mov     byte ptr [rsp+448h+var_F8], r14b
0x18004533a  movups  [rsp+448h+var_D8], xmm0
0x180045342  mov     [rsp+448h+var_C8], r14
0x18004534a  mov     [rsp+448h+var_C0], rax
0x180045352  mov     byte ptr [rsp+448h+var_D8], r14b
0x18004535a  movups  [rsp+448h+var_B8], xmm0
0x180045362  mov     [rsp+448h+var_A8], r14
0x18004536a  mov     [rsp+448h+var_A0], rax
0x180045372  mov     byte ptr [rsp+448h+var_B8], r14b
0x18004537a  movups  [rsp+448h+var_60], xmm0
0x180045382  mov     [rsp+448h+var_50], r14
0x18004538a  mov     [rsp+448h+var_48], rax
0x180045392  mov     byte ptr [rsp+448h+var_60], r14b
0x18004539a  movups  [rsp+448h+var_3C0], xmm0
0x1800453a2  mov     [rsp+448h+var_3B0], r14
0x1800453aa  mov     [rsp+448h+var_3A8], r14
0x1800453b2  lea     r12d, [r14+10h]
0x1800453b6  mov     r8d, r12d
0x1800453b9  lea     rdx, aSystemFacttime; "system::factTime"
0x1800453c0  lea     rcx, [rsp+448h+var_3C0]
0x1800453c8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800453cd  lea     r8, [rsp+448h+var_3C0]
0x1800453d5  lea     rdx, [rsp+448h+var_3A0]
0x1800453dd  mov     rcx, rdi
0x1800453e0  call    ?GetDimension@FactKey@Facts@UsageAndQualityInsights@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V45@@Z; UsageAndQualityInsights::Facts::FactKey::GetDimension(std::wstring)
0x1800453e5  nop
0x1800453e6  mov     rcx, rax
0x1800453e9  call    ?PreciseUtc8601ToFileTime@Utilities@UsageAndQualityInsights@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(std::wstring const &)
0x1800453ee  mov     rdx, rax
0x1800453f1  lea     rcx, [rsp+448h+S1]
0x1800453f9  call    ?TimePointFromFileTime@Utilities@UsageAndQualityInsights@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_K@Z; UsageAndQualityInsights::Utilities::TimePointFromFileTime(unsigned __int64)
0x1800453fe  nop
0x1800453ff  lea     rcx, [rsp+448h+var_3A0]; void *
0x180045407  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004540c  mov     rax, 346DC5D63886594Bh
0x180045416  imul    [rsp+448h+S1]
0x18004541e  sar     rdx, 0Bh
0x180045422  mov     rax, rdx
0x180045425  shr     rax, 3Fh
0x180045429  add     rdx, rax
0x18004542c  mov     [rsp+448h+var_2F0], rdx
0x180045434  lea     rax, [rsp+448h+var_3C0]
0x18004543c  mov     [rsp+448h+S1], rax
0x180045444  xorps   xmm0, xmm0
0x180045447  movups  [rsp+448h+var_3C0], xmm0
0x18004544f  mov     [rsp+448h+var_3B0], r14
0x180045457  mov     [rsp+448h+var_3A8], r14
0x18004545f  lea     r8d, [r14+1]
0x180045463  lea     rdx, a0_0; "0"
0x18004546a  lea     rcx, [rsp+448h+var_3C0]
0x180045472  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180045477  nop
0x180045478  xorps   xmm0, xmm0
0x18004547b  movups  [rsp+448h+var_358], xmm0
0x180045483  mov     [rsp+448h+var_348], r14
0x18004548b  mov     [rsp+448h+var_340], r14
0x180045493  lea     r8d, [r14+11h]
0x180045497  lea     rdx, aSystemFactflag; "system::factFlags"
0x18004549e  lea     rcx, [rsp+448h+var_358]
0x1800454a6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800454ab  nop
0x1800454ac  lea     r9, [rsp+448h+var_3C0]
0x1800454b4  lea     r8, [rsp+448h+var_358]
0x1800454bc  lea     rdx, [rsp+448h+var_3A0]
0x1800454c4  mov     rcx, rdi
0x1800454c7  call    ?GetDimensionOrDefault@FactKey@Facts@UsageAndQualityInsights@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V45@0@Z; UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(std::wstring,std::wstring)
0x1800454cc  nop
0x1800454cd  mov     rcx, rax; String
0x1800454d0  call    ?stoull@std@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoull(std::wstring const &,unsigned __int64 *,int)
0x1800454d5  mov     [rsp+448h+var_2E8], rax
0x1800454dd  lea     rcx, [rsp+448h+var_3A0]; void *
0x1800454e5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800454ea  lea     r15, [rdi+18h]
0x1800454ee  mov     al, [r15]
0x1800454f1  mov     [rsp+448h+var_2E0], al
0x1800454f8  xorps   xmm0, xmm0
0x1800454fb  movups  [rsp+448h+var_3C0], xmm0
0x180045503  mov     [rsp+448h+var_3B0], r14
0x18004550b  mov     [rsp+448h+var_3A8], r14
0x180045513  lea     r8d, [r14+12h]
0x180045517  lea     rdx, aSystemFactsour; "system::factSource"
0x18004551e  lea     rcx, [rsp+448h+var_3C0]
0x180045526  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004552b  lea     r8, [rsp+448h+var_3C0]
0x180045533  lea     rdx, [rsp+448h+S1]
0x18004553b  lea     rcx, [rdi+8]
0x18004553f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180045544  lea     rcx, [rsp+448h+var_3C0]; void *
0x18004554c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045551  mov     rbx, [rsp+448h+S1]
0x180045559  cmp     rbx, [rdi+8]
0x18004555d  setz    al
0x180045560  mov     rcx, [rsp+448h]; this
0x180045568  lea     rdx, aFactSourceKeyN; "Fact source key not found in dimensions"
0x18004556f  mov     [rsp+448h+var_420], rdx; char *
0x180045574  mov     byte ptr [rsp+448h+var_428], al; int
0x180045578  mov     esi, 80070057h
0x18004557d  mov     r9d, esi; char *
0x180045580  lea     r8, aOnecoreBaseUsa_11; "onecore\\base\\usageandqualityinsights"...
0x180045587  mov     edx, 0A8h; void *
0x18004558c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180045591  lea     rdx, [rbx+40h]
0x180045595  lea     rcx, [rsp+448h+S1]
0x18004559d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800455a2  nop
0x1800455a3  mov     r8, [rsp+448h+N]; N
0x1800455ab  lea     r9, [rsp+448h+S1]
0x1800455b3  mov     rax, [rsp+448h+S1]
0x1800455bb  mov     rcx, [rsp+448h+var_360]
0x1800455c3  cmp     rcx, 7
0x1800455c7  cmova   r9, rax
0x1800455cb  cmp     r8, 0Ch
0x1800455cf  jnz     short loc_180045601
0x1800455d1  lea     rdx, aMetricsevent; "MetricsEvent"
0x1800455d8  mov     rcx, r9; S1
0x1800455db  call    wmemcmp
0x1800455e0  test    eax, eax
0x1800455e2  jnz     short loc_1800455E9
0x1800455e4  mov     al, r14b
0x1800455e7  jmp     short loc_180045634
0x1800455e9  mov     rcx, [rsp+448h+var_360]
0x1800455f1  mov     r8, [rsp+448h+N]; N
0x1800455f9  mov     rax, [rsp+448h+S1]
0x180045601  lea     r9, [rsp+448h+S1]
0x180045609  cmp     rcx, 7
0x18004560d  cmova   r9, rax
0x180045611  cmp     r8, 3
0x180045615  jnz     loc_180046CB9
0x18004561b  lea     rdx, aTip; "TIP"
0x180045622  mov     rcx, r9; S1
0x180045625  call    wmemcmp
0x18004562a  test    eax, eax
0x18004562c  jnz     loc_180046CB9
0x180045632  mov     al, 1
0x180045634  mov     [rsp+448h+var_2DF], al
0x18004563b  lea     rcx, [rsp+448h+S1]; void *
0x180045643  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045648  lea     rax, [rsp+448h+var_3C0]
0x180045650  mov     [rsp+448h+S1], rax
0x180045658  xorps   xmm0, xmm0
0x18004565b  movups  [rsp+448h+var_3C0], xmm0
0x180045663  mov     [rsp+448h+var_3B0], r14
0x18004566b  mov     [rsp+448h+var_3A8], r14
0x180045673  xor     r8d, r8d
0x180045676  lea     rdx, S1
0x18004567d  lea     rcx, [rsp+448h+var_3C0]
0x180045685  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004568a  nop
0x18004568b  xorps   xmm0, xmm0
0x18004568e  movups  [rsp+448h+var_3A0], xmm0
0x180045696  mov     [rsp+448h+var_390], r14
0x18004569e  mov     [rsp+448h+var_388], r14
0x1800456a6  mov     r8, r12
0x1800456a9  lea     rdx, aSystemFactname; "system::factName"
0x1800456b0  lea     rcx, [rsp+448h+var_3A0]
0x1800456b8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800456bd  nop
0x1800456be  lea     r9, [rsp+448h+var_3C0]
0x1800456c6  lea     r8, [rsp+448h+var_3A0]
0x1800456ce  lea     rdx, [rsp+448h+var_338]
0x1800456d6  mov     rcx, rdi
0x1800456d9  call    ?GetDimensionOrDefault@FactKey@Facts@UsageAndQualityInsights@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V45@0@Z; UsageAndQualityInsights::Facts::FactKey::GetDimensionOrDefault(std::wstring,std::wstring)
0x1800456de  nop
0x1800456df  cmp     qword ptr [rax+18h], 7
0x1800456e4  jbe     short loc_1800456EB
0x1800456e6  mov     rcx, [rax]
0x1800456e9  jmp     short loc_1800456EE
0x1800456eb  mov     rcx, rax
0x1800456ee  mov     rax, [rax+10h]
0x1800456f2  xorps   xmm0, xmm0
0x1800456f5  movups  [rsp+448h+var_358], xmm0
0x1800456fd  mov     [rsp+448h+var_348], r14
0x180045705  mov     ebx, 0Fh
0x18004570a  mov     [rsp+448h+var_340], rbx
0x180045712  mov     byte ptr [rsp+448h+var_358], r14b
0x18004571a  mov     [rsp+448h+var_410], 6
0x180045722  mov     [rsp+448h+S1], rcx
0x18004572a  mov     [rsp+448h+var_370], rax
0x180045732  lea     rdx, [rsp+448h+var_358]
0x18004573a  lea     rcx, [rsp+448h+S1]
0x180045742  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x180045747  lea     rdx, [rsp+448h+var_358]
0x18004574f  lea     rcx, [rsp+448h+var_2D8]
0x180045757  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004575c  nop
0x18004575d  lea     rcx, [rsp+448h+var_358]; void *
0x180045765  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004576a  nop
0x18004576b  lea     rcx, [rsp+448h+var_338]; void *
0x180045773  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045778  mov     rax, [rdi]
0x18004577b  mov     [rsp+448h+var_2B8], rax
0x180045783  movzx   eax, byte ptr [r15]
0x180045787  mov     [rsp+448h+var_2B0], eax
0x18004578e  lea     rdx, [rsp+448h+var_338]
0x180045796  mov     rcx, rdi
0x180045799  call    ?GetMetricName@FactKey@Facts@UsageAndQualityInsights@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UsageAndQualityInsights::Facts::FactKey::GetMetricName(void)
0x18004579e  nop
0x18004579f  cmp     qword ptr [rax+18h], 7
0x1800457a4  jbe     short loc_1800457AB
0x1800457a6  mov     rcx, [rax]
0x1800457a9  jmp     short loc_1800457AE
0x1800457ab  mov     rcx, rax
0x1800457ae  mov     rax, [rax+10h]
0x1800457b2  xorps   xmm0, xmm0
0x1800457b5  movups  [rsp+448h+var_358], xmm0
0x1800457bd  mov     [rsp+448h+var_348], r14
0x1800457c5  mov     [rsp+448h+var_340], rbx
0x1800457cd  mov     byte ptr [rsp+448h+var_358], r14b
0x1800457d5  mov     [rsp+448h+var_410], 0Ah
0x1800457dd  mov     [rsp+448h+S1], rcx
0x1800457e5  mov     [rsp+448h+var_370], rax
0x1800457ed  lea     rdx, [rsp+448h+var_358]
0x1800457f5  lea     rcx, [rsp+448h+S1]
0x1800457fd  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x180045802  lea     rdx, [rsp+448h+var_358]
0x18004580a  lea     rcx, [rsp+448h+var_2A8]
0x180045812  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180045817  mov     r12d, 2
0x18004581d  lea     rcx, [rsp+448h+var_358]; void *
0x180045825  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004582a  nop
0x18004582b  lea     rcx, [rsp+448h+var_338]; void *
0x180045833  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045838  mov     rsi, r14
0x18004583b  cmp     [r15], r14b
0x18004583e  jnz     loc_18004591C
0x180045844  cmp     dword ptr [r15+58h], 0A0h
0x18004584c  jz      loc_18004591C
0x180045852  lea     rdx, [r15+78h]
0x180045856  lea     rcx, [rsp+448h+S1]
0x18004585e  call    ??0?$map@JNU?$less@J@std@@V?$allocator@U?$pair@$$CBJN@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<long,double>::map<long,double>(std::map<long,double> const &)
0x180045863  mov     r12d, 12h
  ... truncated ...
```
