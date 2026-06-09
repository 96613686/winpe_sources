# UsageAndQualityInsights::Configuration::ParseUQIConfig(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x1800ed99c`
- end: `0x1800ef0d7`
- name: `?ParseUQIConfig@Configuration@UsageAndQualityInsights@@YA?AUUQIConfig@12@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `5947`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `58`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800e5324`
- `0x1800e733c`

## callees

- `0x1800033d0`
- `0x180003870`
- `0x1800038b8`
- `0x180003fac`
- `0x1800040a0`
- `0x180004140`
- `0x180005e7c`
- `0x180006a90`
- `0x18000c844`
- `0x18000eee0`
- `0x18000f124`
- `0x18001112c`
- `0x180012054`
- `0x180012dd4`
- `0x18001321c`
- `0x180013780`
- `0x18001386c`
- `0x180013cd4`
- `0x18001472c`
- `0x1800163f8`
- `0x180016680`
- `0x180016a6c`
- `0x180019458`
- `0x180019794`
- `0x180019c04`
- `0x18001a380`
- `0x18001a8f4`
- `0x18001d2dc`
- `0x180026878`
- `0x180027ba4`
- `0x180027cc4`
- `0x180027ee4`
- `0x180027f54`
- `0x180027fdc`
- `0x18002804c`
- `0x1800280b0`
- `0x180028120`
- `0x180028250`
- `0x18002832c`
- `0x1800283f4`
- `0x18002a9c8`
- `0x18002aa84`
- `0x18002ac8c`
- `0x1800e566c`
- `0x1800ec664`
- `0x1800ec898`
- `0x1800ec9c0`
- `0x1800ecc70`
- `0x1800ecea0`
- `0x1800ed1d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800edb51`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800edba6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea73`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea7a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea81`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea88`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea8f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea96`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeaa4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeaab`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeab2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeab9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeac0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeff5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800edb51`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800edba6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea73`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea7a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea81`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea88`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea8f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea96`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eea9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeaa4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeaab`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeab2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeab9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeac0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800eeff5`

## string_xrefs

- `0x1800ef01c`: `onecore\base\usageandqualityinsights\service\lib\configuration\uqiconfig.cpp`
- `0x1800ef04e`: `onecore\base\usageandqualityinsights\service\lib\configuration\uqiconfig.cpp`
- `0x1800ef086`: `onecore\base\usageandqualityinsights\service\lib\configuration\uqiconfig.cpp`
- `0x1800ef0c5`: `onecore\base\usageandqualityinsights\service\lib\configuration\uqiconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=66
__int64 __fastcall UsageAndQualityInsights::Configuration::ParseUQIConfig(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // r15
  _QWORD *v4; // r13
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  unsigned int v7; // r12d
  __int64 NamedString; // rax
  __int64 v9; // r8
  const wchar_t *v10; // r9
  unsigned __int64 v11; // rdx
  char *v12; // rdi
  __int64 v13; // rbx
  void *v14; // rbx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  int v17; // r12d
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r8
  char *v23; // r9
  unsigned __int64 v24; // rdx
  void **v25; // rdi
  __int64 v26; // rbx
  void *v27; // rbx
  int v28; // eax
  HANDLE v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  char *v32; // r9
  unsigned __int64 v33; // rdx
  void **v34; // rdi
  __int64 v35; // rbx
  void *v36; // rbx
  int v37; // eax
  HANDLE v38; // rax
  __int64 NamedArray; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rdi
  __int64 v45; // r14
  __int64 v46; // rsi
  __int64 v47; // rbx
  _QWORD *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  char *v51; // rdx
  __int64 NamedObject; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  char *v55; // rax
  __int64 v56; // rax
  char *v57; // rax
  char *v58; // rbx
  __int64 v59; // rax
  __int128 v60; // xmm6
  __int64 v61; // rcx
  void *v62; // r8
  char v63; // r15
  __int16 v64; // r12
  char v65; // r13
  __int64 v66; // rax
  __int64 v67; // rax
  char *v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  char *v72; // rdx
  unsigned int i; // r14d
  __int64 v74; // rax
  unsigned __int64 v75; // rdi
  wchar_t *v76; // rsi
  wchar_t *v77; // rbx
  char v78; // al
  __int64 v79; // rdx
  __int64 v80; // rax
  char *v81; // rax
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v85; // eax
  unsigned int v86; // eax
  const char *v87; // [rsp+30h] [rbp-D8h]
  __int64 v88; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v89; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v90; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v91; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v92; // [rsp+68h] [rbp-A0h]
  const wchar_t *v93; // [rsp+70h] [rbp-98h]
  __int64 v94; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v95[5]; // [rsp+80h] [rbp-88h] BYREF
  __int16 v96; // [rsp+85h] [rbp-83h]
  char v97; // [rsp+87h] [rbp-81h]
  int v98; // [rsp+88h] [rbp-80h]
  __int64 v99; // [rsp+90h] [rbp-78h] BYREF
  __int64 v100; // [rsp+98h] [rbp-70h] BYREF
  __int64 v101; // [rsp+A0h] [rbp-68h] BYREF
  void *v102[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v103; // [rsp+B8h] [rbp-50h]
  int *v104; // [rsp+C8h] [rbp-40h] BYREF
  int v105; // [rsp+D0h] [rbp-38h] BYREF
  int v106; // [rsp+D4h] [rbp-34h]
  const wchar_t *v107; // [rsp+E0h] [rbp-28h]
  __int64 v108; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v109; // [rsp+F0h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v111; // [rsp+100h] [rbp-8h] BYREF
  _BYTE *v112; // [rsp+108h] [rbp+0h] BYREF
  __int64 v113; // [rsp+110h] [rbp+8h] BYREF
  __int64 v114; // [rsp+118h] [rbp+10h] BYREF
  int *v115; // [rsp+120h] [rbp+18h] BYREF
  int v116; // [rsp+128h] [rbp+20h] BYREF
  int v117; // [rsp+12Ch] [rbp+24h]
  const wchar_t *v118; // [rsp+138h] [rbp+30h]
  __int64 v119; // [rsp+140h] [rbp+38h] BYREF
  _BYTE v120[32]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v121[8]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v122[8]; // [rsp+170h] [rbp+68h] BYREF
  __int64 v123; // [rsp+178h] [rbp+70h]
  _QWORD v124[2]; // [rsp+180h] [rbp+78h] BYREF
  __int128 v125; // [rsp+190h] [rbp+88h] BYREF
  __int64 v126; // [rsp+1A0h] [rbp+98h]
  int *v127; // [rsp+1A8h] [rbp+A0h] BYREF
  int v128; // [rsp+1B0h] [rbp+A8h] BYREF
  int v129; // [rsp+1B4h] [rbp+ACh]
  const wchar_t *v130; // [rsp+1C0h] [rbp+B8h]
  __int64 v131; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v132; // [rsp+1D0h] [rbp+C8h] BYREF
  __int64 v133; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v134; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v135[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v136; // [rsp+1F0h] [rbp+E8h] BYREF
  LPVOID v137; // [rsp+1F8h] [rbp+F0h] BYREF
  LPVOID v138; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v139; // [rsp+208h] [rbp+100h] BYREF
  wchar_t *S1; // [rsp+210h] [rbp+108h] BYREF
  wchar_t *v141; // [rsp+218h] [rbp+110h]
  _DWORD *v142; // [rsp+228h] [rbp+120h] BYREF
  _DWORD v143[4]; // [rsp+230h] [rbp+128h] BYREF
  const wchar_t *v144; // [rsp+240h] [rbp+138h]
  __int64 v145; // [rsp+248h] [rbp+140h]
  _DWORD *v146; // [rsp+250h] [rbp+148h] BYREF
  _DWORD v147[4]; // [rsp+258h] [rbp+150h] BYREF
  const wchar_t *v148; // [rsp+268h] [rbp+160h]
  int v149; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v150[32]; // [rsp+280h] [rbp+178h] BYREF
  _BYTE v151[32]; // [rsp+2A0h] [rbp+198h] BYREF
  _BYTE v152[24]; // [rsp+2C0h] [rbp+1B8h] BYREF
  _BYTE v153[24]; // [rsp+2D8h] [rbp+1D0h] BYREF
  char v154; // [rsp+2F0h] [rbp+1E8h]
  _BYTE v155[24]; // [rsp+2F8h] [rbp+1F0h] BYREF
  char v156; // [rsp+310h] [rbp+208h]
  _BYTE v157[16]; // [rsp+318h] [rbp+210h] BYREF
  char v158; // [rsp+328h] [rbp+220h]
  __int64 v159; // [rsp+338h] [rbp+230h]
  void *v160[2]; // [rsp+348h] [rbp+240h] BYREF
  unsigned __int64 v161; // [rsp+358h] [rbp+250h]
  unsigned __int64 v162; // [rsp+360h] [rbp+258h]
  void *v163[2]; // [rsp+368h] [rbp+260h] BYREF
  unsigned __int64 v164; // [rsp+378h] [rbp+270h]
  unsigned __int64 v165; // [rsp+380h] [rbp+278h]
  __int128 v166; // [rsp+388h] [rbp+280h] BYREF
  __int128 v167; // [rsp+398h] [rbp+290h] BYREF
  __int128 v168; // [rsp+3A8h] [rbp+2A0h]
  _BYTE v169[24]; // [rsp+3B8h] [rbp+2B0h] BYREF
  __int64 v170; // [rsp+3D0h] [rbp+2C8h]
  __int128 v171; // [rsp+3D8h] [rbp+2D0h] BYREF
  __int64 v172; // [rsp+3E8h] [rbp+2E0h]
  __int128 v173; // [rsp+3F0h] [rbp+2E8h] BYREF
  __int64 v174; // [rsp+400h] [rbp+2F8h]
  __int64 v175; // [rsp+408h] [rbp+300h]
  int NamedNumber; // [rsp+410h] [rbp+308h]
  int v177; // [rsp+414h] [rbp+30Ch]
  __int128 v178; // [rsp+418h] [rbp+310h] BYREF
  __int64 v179; // [rsp+428h] [rbp+320h]
  wil::details::in1diag3 *retaddr; // [rsp+490h] [rbp+388h]

  v2 = a2;
  v114 = a2;
  v3 = a1;
  v145 = a1;
  v159 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v4 = (_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  v5 = operator new(0xF8u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *v4 = v5;
  v123 = v3 + 56;
  *(_QWORD *)(v3 + 56) = 0;
  *(_QWORD *)(v3 + 64) = 0;
  v6 = operator new(0xB8u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *(_QWORD *)(v3 + 56) = v6;
  v7 = 1;
  v98 = 1;
  if ( aName[4] )
    goto LABEL_223;
  v128 = 1;
  v129 = 4;
  v130 = L"Name";
  v127 = &v128;
  NamedString = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                  v2,
                  &lpMem,
                  &v127);
  v10 = *(_QWORD *)NamedString
      ? *(const wchar_t **)(*(_QWORD *)NamedString + 16LL)
      : (const wchar_t *)((char *)&Src + 1);
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  if ( v11 > *(_QWORD *)(v3 + 24) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v3,
      v11,
      v9,
      v10);
  }
  else
  {
    v12 = *(_QWORD *)(v3 + 24) <= 7u ? (char *)v3 : *(char **)v3;
    *(_QWORD *)(v3 + 16) = v11;
    v13 = 2 * v11;
    memmove_0(v12, v10, 2 * v11);
    *(_WORD *)&v12[v13] = 0;
    v2 = v114;
  }
  v14 = lpMem;
  if ( lpMem )
  {
    v15 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( !v15 )
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v14);
      goto LABEL_17;
    }
    if ( v15 < 0 )
LABEL_223:
      abort();
  }
LABEL_17:
  if ( aVersion[7] )
    abort();
  v128 = 1;
  v129 = 7;
  v130 = L"Version";
  v127 = &v128;
  *(_DWORD *)(v3 + 32) = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                v2,
                                &v127);
  if ( aFactdefinition[15] )
    abort();
  v147[0] = 1;
  v147[1] = 15;
  v148 = L"FactDefinitions";
  v146 = v147;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
    v2,
    &v119,
    &v146);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
    &v119,
    &v90);
  lpMem = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator!=(&v90, &lpMem) )
  {
    do
    {
      v94 = 0;
      v17 = v7 | 4;
      v98 = v17;
      LODWORD(v91) = 46;
      *((_QWORD *)&v91 + 1) = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
      v92 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 48LL))(v90, &v94);
      if ( v18 < 0 )
        winrt::throw_hresult((unsigned int)v18, &v91);
      v7 = v17 & 0xFFFFFFF9 | 2;
      v98 = v7;
      v154 = 0;
      v156 = 0;
      v158 = 0;
      v19 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(
              &v94,
              &v131);
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(v19, &v88);
      if ( v131 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v131);
      if ( aFactsource[10] )
        abort();
      v143[0] = 1;
      v143[1] = 10;
      v144 = L"FactSource";
      v142 = v143;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
        &v88,
        &v113,
        &v142);
      v20 = v113;
      if ( !v113 )
      {
LABEL_227:
        v85 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\uqiconfig.cpp",
          (const char *)v85,
          (int)"Unknown FactSource value",
          v87);
      }
      if ( *(_DWORD *)(v113 + 4) == 12 && !wmemcmp(*(const wchar_t **)(v113 + 16), L"MetricsEvent", 0xCu) )
      {
        v149 = 0;
      }
      else
      {
        if ( !v20 || *(_DWORD *)(v20 + 4) != 3 || wmemcmp(*(const wchar_t **)(v20 + 16), L"TIP", 3u) )
          goto LABEL_227;
        v149 = 1;
      }
      if ( aMetricsevent[12] )
        abort();
      *((_QWORD *)&v91 + 1) = 0xC00000001LL;
      v93 = L"MetricsEvent";
      *(_QWORD *)&v91 = (char *)&v91 + 8;
      if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                              &v88,
                              &v91) )
      {
        *(_OWORD *)v160 = 0;
        v161 = 0;
        v162 = 7;
        LOWORD(v160[0]) = 0;
        *(_OWORD *)v163 = 0;
        v164 = 0;
        v165 = 7;
        LOWORD(v163[0]) = 0;
        v166 = 0;
        v167 = 0;
        v168 = 0;
        if ( aMetricsevent[12] )
          abort();
        *((_QWORD *)&v91 + 1) = 0xC00000001LL;
        v93 = L"MetricsEvent";
        *(_QWORD *)&v91 = (char *)&v91 + 8;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
          &v88,
          &v99,
          &v91);
        if ( aSourceeventinf[15] )
          abort();
        v116 = 1;
        v117 = 15;
        v118 = L"SourceEventInfo";
        v115 = &v116;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
          &v99,
          &v100,
          &v115);
        if ( aSourceeventful[19] )
LABEL_160:
          abort();
        *((_QWORD *)&v91 + 1) = 0x1300000001LL;
        v93 = L"SourceEventFullName";
        *(_QWORD *)&v91 = (char *)&v91 + 8;
        v21 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                &v100,
                &v138,
                &v91);
        if ( *(_QWORD *)v21 )
          v23 = *(char **)(*(_QWORD *)v21 + 16LL);
        else
          v23 = (char *)&Src + 1;
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&v23[2 * v24] );
        if ( v24 > v162 )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
            v160,
            v24,
            v22,
            v23);
        }
        else
        {
          v25 = v160;
          if ( v162 > 7 )
            v25 = (void **)v160[0];
          v161 = v24;
          v26 = 2 * v24;
          memmove_0(v25, v23, 2 * v24);
          *(_WORD *)((char *)v25 + v26) = 0;
        }
        v27 = v138;
        if ( v138 )
        {
          v28 = _InterlockedDecrement((volatile signed __int32 *)v138 + 6);
          if ( v28 )
          {
            if ( v28 < 0 )
              goto LABEL_160;
          }
          else
          {
            v29 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v29, 0, v27);
          }
          v138 = 0;
        }
        if ( aSourceeventpro[23] )
LABEL_159:
          abort();
        *((_QWORD *)&v91 + 1) = 0x1700000001LL;
        v93 = L"SourceEventProviderGuid";
        *(_QWORD *)&v91 = (char *)&v91 + 8;
        v30 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                &v100,
                &v137,
                &v91);
        if ( *(_QWORD *)v30 )
          v32 = *(char **)(*(_QWORD *)v30 + 16LL);
        else
          v32 = (char *)&Src + 1;
        v33 = -1;
        do
          ++v33;
        while ( *(_WORD *)&v32[2 * v33] );
        if ( v33 > v165 )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
            v163,
            v33,
            v31,
            v32);
        }
        else
        {
          v34 = v163;
          if ( v165 > 7 )
            v34 = (void **)v163[0];
          v164 = v33;
          v35 = 2 * v33;
          memmove_0(v34, v32, 2 * v33);
          *(_WORD *)((char *)v34 + v35) = 0;
        }
        v36 = v137;
        if ( v137 )
        {
          v37 = _InterlockedDecrement((volatile signed __int32 *)v137 + 6);
          if ( v37 )
          {
            if ( v37 < 0 )
              goto LABEL_159;
          }
          else
          {
            v38 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v38, 0, v36);
          }
          v137 = 0;
        }
        if ( aDimensions_0[10] )
          abort();
        v105 = 1;
        v106 = 10;
        v107 = L"Dimensions";
        v104 = &v105;
        NamedArray = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                       &v99,
                       &v136,
                       &v104);
        v40 = UsageAndQualityInsights::Configuration::JsonArrayToVector(&v91, NamedArray);
        if ( &v166 != (__int128 *)v40 )
        {
          std::vector<std::wstring>::_Tidy(&v166);
          v166 = *(_OWORD *)v40;
          *(_QWORD *)&v167 = *(_QWORD *)(v40 + 16);
          *(_QWORD *)v40 = 0;
          *(_QWORD *)(v40 + 8) = 0;
          *(_QWORD *)(v40 + 16) = 0;
        }
        std::vector<std::wstring>::_Tidy(&v91);
        if ( v136 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v136);
        if ( aMetrics[7] )
          abort();
        v105 = 1;
        v106 = 7;
        v107 = L"Metrics";
        v104 = &v105;
        v41 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                &v99,
                &v133,
                &v104);
        v42 = UsageAndQualityInsights::Configuration::JsonArrayToVector(&v91, v41);
        if ( (__int128 *)((char *)&v167 + 8) != (__int128 *)v42 )
        {
          std::vector<std::wstring>::_Tidy((char *)&v167 + 8);
          *((_QWORD *)&v167 + 1) = *(_QWORD *)v42;
          v168 = *(_OWORD *)(v42 + 8);
          *(_QWORD *)v42 = 0;
          *(_QWORD *)(v42 + 8) = 0;
          *(_QWORD *)(v42 + 16) = 0;
        }
        std::vector<std::wstring>::_Tidy(&v91);
        if ( v133 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v133);
        if ( v154 )
        {
          std::wstring::operator=(v150, v160);
          std::wstring::operator=(v151, v163);
          std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(
            v152,
            v166,
            (__int64)(*((_QWORD *)&v166 + 1) - v166) >> 5);
          std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(
            v153,
            *((_QWORD *)&v167 + 1),
            (__int64)(v168 - *((_QWORD *)&v167 + 1)) >> 5);
        }
        else
        {
          *(_QWORD *)&v91 = v150;
          v112 = v150;
          std::wstring::wstring(v150, v160);
          std::wstring::wstring(v151, v163);
          std::vector<std::wstring>::vector<std::wstring>(v152, &v166);
          std::vector<std::wstring>::vector<std::wstring>(v153, (char *)&v167 + 8);
          v154 = 1;
        }
        if ( v100 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v100);
        if ( v99 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v99);
        std::vector<std::wstring>::_Tidy((char *)&v167 + 8);
        std::vector<std::wstring>::_Tidy(&v166);
        std::wstring::~wstring(v163);
        std::wstring::~wstring(v160);
      }
      if ( aTip_0[3] )
        abort();
      v105 = 1;
      v106 = 3;
      v107 = L"Tip";
      v104 = &v105;
      if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                              &v88,
                              &v104) )
      {
        v125 = 0;
        v126 = 0;
        if ( aTip_0[3] )
          abort();
        v105 = 1;
        v106 = 3;
        v107 = L"Tip";
        v104 = &v105;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
          &v88,
          &v108,
          &v104);
        if ( aTestcaseids[11] )
          abort();
        v116 = 1;
        v117 = 11;
        v118 = L"TestCaseIds";
        v115 = &v116;
        v43 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                &v108,
                &v132,
                &v115);
        v44 = UsageAndQualityInsights::Configuration::JsonArrayToVector(&v91, v43);
        v45 = 0;
        if ( &v125 == (__int128 *)v44 )
        {
          v47 = *((_QWORD *)&v125 + 1);
          v46 = v125;
        }
        else
        {
          std::vector<std::wstring>::_Tidy(&v125);
          v45 = *(_QWORD *)v44;
          v46 = *(_QWORD *)v44;
          *(_QWORD *)&v125 = *(_QWORD *)v44;
          v47 = *(_QWORD *)(v44 + 8);
          *((_QWORD *)&v125 + 1) = v47;
          v126 = *(_QWORD *)(v44 + 16);
          *(_QWORD *)v44 = 0;
          *(_QWORD *)(v44 + 8) = 0;
          *(_QWORD *)(v44 + 16) = 0;
        }
        std::vector<std::wstring>::_Tidy(&v91);
        if ( v132 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v132);
        if ( v156 )
        {
          std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(v155, v46, (v47 - v45) >> 5);
        }
        else
        {
          std::vector<std::wstring>::vector<std::wstring>(v155, &v125);
          v156 = 1;
        }
        if ( v108 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v108);
        std::vector<std::wstring>::_Tidy(&v125);
      }
      if ( aEnrichedfields[14] )
        abort();
      v105 = 1;
      v106 = 14;
      v107 = L"EnrichedFields";
      v104 = &v105;
      if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                              &v88,
                              &v104) )
      {
        v124[0] = 0;
        v124[1] = 0;
        v48 = operator new(0x80u);
        *v48 = v48;
        v48[1] = v48;
        v48[2] = v48;
        *((_WORD *)v48 + 12) = 257;
        v124[0] = v48;
        winrt::param::hstring::hstring((winrt::param::hstring *)&v104, L"EnrichedFields");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
          &v88,
          &v109,
          &v104);
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
          &v109,
          &v111);
        v112 = 0;
        while ( (unsigned __int8)winrt::Windows::Foundation::operator!=(&v111, &v112) )
        {
          winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator*(
            &v111,
            &v101);
          *(_OWORD *)&v169[8] = 0;
          v170 = 0;
          *(_QWORD *)&v171 = 7;
          *(_WORD *)&v169[8] = 0;
          LOBYTE(v173) = 0;
          v49 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(
                  &v101,
                  &v139);
          winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
            v49,
            &v89);
          if ( v139 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v139);
          winrt::param::hstring::hstring((winrt::param::hstring *)&v115, L"EnrichmentType");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
            &v89,
            v135,
            &v115);
          if ( !(unsigned __int8)winrt::operator==(v135, L"inlineMap") )
          {
            v84 = wil::verify_hresult<long>(2147942487LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0xFC,
              (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\uqiconfig.cpp",
              (const char *)v84,
              (int)"Unknown EnrichmentType value",
              v87);
          }
          *(_DWORD *)v169 = 0;
          winrt::param::hstring::hstring((winrt::param::hstring *)&v91, L"PrimaryKeyField");
          v50 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                  &v89,
                  v122,
                  &v91);
          if ( *(_QWORD *)v50 )
            v51 = *(char **)(*(_QWORD *)v50 + 16LL);
          else
            v51 = (char *)&Src + 1;
          std::wstring::operator=(&v169[8], v51);
          winrt::hstring::~hstring((winrt::hstring *)v122);
          winrt::param::hstring::hstring((winrt::param::hstring *)&v91, L"InlineMap");
          if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                  &v89,
                                  &v91) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"InlineMap");
            NamedObject = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
                            &v89,
                            &v134,
                            v120);
            v53 = UsageAndQualityInsights::Configuration::JsonObjectToMap(&S1, NamedObject);
            std::optional<std::map<std::wstring,std::wstring>>::operator=<std::map<std::wstring,std::wstring>,0>(
              (char *)&v171 + 8,
              v53);
            std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&S1);
            if ( v134 )
              winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v134);
          }
          v54 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                             &v101,
                             v121);
          if ( v54 )
            v55 = *(char **)(v54 + 16);
          else
            v55 = (char *)&Src + 1;
          *(_QWORD *)&v91 = v55;
          std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::EnrichedField,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::EnrichedField>>,0>>::_Emplace<wchar_t const *,UsageAndQualityInsights::Configuration::EnrichedField>(
            v124,
            &v127,
            &v91,
            v169);
          winrt::hstring::~hstring((winrt::hstring *)v121);
          winrt::hstring::~hstring((winrt::hstring *)v135);
          if ( v89 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v89);
          if ( (_BYTE)v173 )
            std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)&v171 + 8);
          std::wstring::~wstring(&v169[8]);
          if ( v101 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v101);
          winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(&v111);
        }
        if ( v111 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v111);
        if ( v158 )
        {
          UsageAndQualityInsights::Configuration::EnrichedFields::operator=(v157, v124);
        }
        else
        {
          UsageAndQualityInsights::Configuration::EnrichedFields::EnrichedFields(
            (UsageAndQualityInsights::Configuration::EnrichedFields *)v157,
            (const struct UsageAndQualityInsights::Configuration::EnrichedFields *)v124);
          v158 = 1;
        }
        if ( v109 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v109);
        std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::EnrichedField,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::EnrichedField>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::EnrichedField,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::EnrichedField>>,0>>(v124);
      }
      v56 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
              &v94,
              v95);
      if ( *(_QWORD *)v56 )
        v57 = *(char **)(*(_QWORD *)v56 + 16LL);
      else
        v57 = (char *)&Src + 1;
      *(_QWORD *)&v91 = v57;
      std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>,void *>>>(
        (unsigned int)v102,
        (_DWORD)v4,
        *v4,
        (unsigned int)&v91,
        (__int64)&v149);
      v58 = (char *)v102[1];
      v59 = std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::MetricEventConfigEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>,0>>::_Find_lower_bound<std::wstring>(
              v4,
              &v91,
              (char *)v102[1] + 32);
      v60 = *(_OWORD *)v59;
      if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::FactDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>>,0>>::_Lower_bound_duplicate<std::wstring>(
                              v61,
                              *(_QWORD *)(v59 + 16),
                              v58 + 32) )
      {
        if ( v102[1] )
        {
          std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>::~pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>((char *)v102[1] + 32);
          if ( v102[1] )
            operator delete(v102[1], 0xF8u);
        }
      }
      else
      {
        if ( v4[1] == 0x108421084210842LL )
          std::_Throw_tree_length_error();
        v62 = v102[1];
        v102[1] = 0;
        v91 = v60;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(
          v4,
          &v91,
          v62);
      }
      winrt::hstring::~hstring((winrt::hstring *)v95);
      winrt::hstring::~hstring((winrt::hstring *)&v113);
      if ( v88 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v88);
      UsageAndQualityInsights::Configuration::FactDefinition::~FactDefinition((UsageAndQualityInsights::Configuration::FactDefinition *)&v149);
      if ( v94 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v94);
      winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(&v90);
    }
    while ( (unsigned __int8)winrt::Windows::Foundation::operator!=(&v90, &lpMem) );
    v2 = v114;
  }
  if ( v90 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v90);
  winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"Consumption");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
    v2,
    &v99,
    v120);
  winrt::param::hstring::hstring((winrt::param::hstring *)&v104, L"Facts");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
    &v99,
    &v108,
    &v104);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
    &v108,
    &v90);
  v112 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator!=(&v90, &v112) )
  {
    v63 = v97;
    v64 = v96;
    v65 = v97;
    do
    {
      winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator*(
        &v90,
        &v100);
      memset(v169, 0, sizeof(v169));
      v170 = 7;
      *(_WORD *)v169 = 0;
      v171 = 0;
      v172 = 0;
      v173 = 0;
      v174 = 0;
      v175 = 7;
      LOWORD(v173) = 0;
      v178 = 0;
      v179 = 0;
      v66 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(
              &v100,
              &v114);
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(v66, &v88);
      if ( v114 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v114);
      winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"SourceFact");
      v67 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
              &v88,
              v95,
              v120);
      if ( *(_QWORD *)v67 )
        v68 = *(char **)(*(_QWORD *)v67 + 16LL);
      else
        v68 = (char *)&Src + 1;
      std::wstring::operator=(v169, v68);
      winrt::hstring::~hstring((winrt::hstring *)v95);
      winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"Fields");
      v69 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
              &v88,
              &lpMem,
              v120);
      v70 = UsageAndQualityInsights::Configuration::JsonArrayToVector(&S1, v69);
      std::vector<std::wstring>::operator=(&v171, v70);
      std::vector<std::wstring>::_Tidy(&S1);
      if ( lpMem )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&lpMem);
      winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"AggregationWindowType");
      v71 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
              &v88,
              v121,
              v120);
      if ( *(_QWORD *)v71 )
        v72 = *(char **)(*(_QWORD *)v71 + 16LL);
      else
        v72 = (char *)&Src + 1;
      std::wstring::operator=(&v173, v72);
      winrt::hstring::~hstring((winrt::hstring *)v121);
      winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"AggregationWindowSize");
      NamedNumber = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                           &v88,
                           v120);
      winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"TriggerFrequencyInHours");
      v177 = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                    &v88,
                    v120);
      winrt::param::hstring::hstring((winrt::param::hstring *)v120, L"Endpoints");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
        &v88,
        &v94,
        v120);
      for ( i = 0;
            i < (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v94);
            ++i )
      {
        LOBYTE(v102[1]) = 0;
        BYTE8(v103) = 0;
        winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
          &v94,
          &v89,
          i);
        winrt::param::hstring::hstring((winrt::param::hstring *)&v104, L"Type");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
          &v89,
          &v109,
          &v104);
        if ( (unsigned __int8)winrt::operator==(&v109, L"telemetry") )
        {
          LODWORD(v102[0]) = 0;
        }
        else
        {
          if ( !(unsigned __int8)winrt::operator==(&v109, L"localApi") )
          {
            v83 = wil::verify_hresult<long>(2147942487LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x12E,
              (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\uqiconfig.cpp",
              (const char *)v83,
              (int)"Unknown ConsumptionEndpoint",
              v87);
          }
          LODWORD(v102[0]) = 1;
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)&v115, L"TelemetryLevel");
        if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                &v89,
                                &v115) )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&v142, L"TelemetryLevel");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
            &v89,
            &v101,
            &v142);
          if ( (unsigned __int8)winrt::operator==(&v101, L"measure") )
          {
            HIDWORD(v102[0]) = 0;
            *(_WORD *)((char *)&v102[1] + 1) = v64;
            BYTE3(v102[1]) = v63;
          }
          else if ( (unsigned __int8)winrt::operator==(&v101, L"critical") )
          {
            HIDWORD(v102[0]) = 1;
            *(_WORD *)((char *)&v102[1] + 1) = v96;
            BYTE3(v102[1]) = v65;
          }
          else
          {
            if ( !(unsigned __int8)winrt::operator==(&v101, L"core") )
            {
              v86 = wil::verify_hresult<long>(2147942487LL);
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x143,
                (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\uqiconfig.cpp",
                (const char *)v86,
                (int)"Unknown TelemetryLevel value",
                v87);
            }
            HIDWORD(v102[0]) = 2;
            *(_WORD *)((char *)&v102[1] + 1) = v96;
            BYTE3(v102[1]) = v97;
          }
          LOBYTE(v102[1]) = 1;
          winrt::hstring::~hstring((winrt::hstring *)&v101);
        }
        winrt::param::hstring::hstring((winrt::param::hstring *)&v115, L"PrivacyTags");
        if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                &v89,
                                &v115) )
        {
          winrt::param::hstring::hstring((winrt::param::hstring *)&v142, L"PrivacyTags");
          v74 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                  &v89,
                  &v113,
                  &v142);
          UsageAndQualityInsights::Configuration::JsonArrayToVector(&S1, v74);
          if ( v113 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v113);
          v75 = 0;
          v76 = v141;
          v77 = S1;
          if ( S1 == v141 )
            goto LABEL_195;
          do
          {
            v75 |= UsageAndQualityInsights::Configuration::PrivacyTagStringToBit(v77);
            v77 += 16;
          }
          while ( v77 != v76 );
          if ( !v75 )
          {
LABEL_195:
            v75 = (unsigned __int64)v102[0];
            v78 = 0;
          }
          else
          {
            v78 = 1;
          }
          *(_QWORD *)&v103 = v75;
          BYTE8(v103) = v78;
          *(_DWORD *)((char *)&v103 + 9) = *(_DWORD *)((char *)&v102[1] + 1);
          *(_WORD *)((char *)&v103 + 13) = *(_WORD *)((char *)&v102[1] + 5);
          HIBYTE(v103) = HIBYTE(v102[1]);
          std::vector<std::wstring>::_Tidy(&S1);
        }
        v79 = *((_QWORD *)&v178 + 1);
        if ( *((_QWORD *)&v178 + 1) == v179 )
        {
          std::vector<UsageAndQualityInsights::Configuration::ConsumptionEndpoint>::_Emplace_reallocate<UsageAndQualityInsights::Configuration::ConsumptionEndpoint>(
            &v178,
            *((_QWORD *)&v178 + 1),
            v102);
        }
        else
        {
          **((_OWORD **)&v178 + 1) = *(_OWORD *)v102;
          *(_OWORD *)(v79 + 16) = v103;
          *((_QWORD *)&v178 + 1) += 32LL;
        }
        winrt::hstring::~hstring((winrt::hstring *)&v109);
        if ( v89 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v89);
      }
      v80 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
                         &v100,
                         v122);
      if ( v80 )
        v81 = *(char **)(v80 + 16);
      else
        v81 = (char *)&Src + 1;
      *(_QWORD *)&v91 = v81;
      std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::ConsumptionFact,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::ConsumptionFact>>,0>>::_Emplace<wchar_t const *,UsageAndQualityInsights::Configuration::ConsumptionFact>(
        v123,
        &v127,
        &v91,
        v169);
      winrt::hstring::~hstring((winrt::hstring *)v122);
      if ( v94 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v94);
      if ( v88 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v88);
      std::vector<UsageAndQualityInsights::Configuration::ConsumptionEndpoint>::~vector<UsageAndQualityInsights::Configuration::ConsumptionEndpoint>(&v178);
      std::wstring::~wstring(&v173);
      std::vector<std::wstring>::_Tidy(&v171);
      std::wstring::~wstring(v169);
      if ( v100 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v100);
      winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(&v90);
    }
    while ( (unsigned __int8)winrt::Windows::Foundation::operator!=(&v90, &v112) );
    v3 = v145;
  }
  if ( v90 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v90);
  if ( v108 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v108);
  if ( v99 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v99);
  if ( v119 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v119);
  return v3;
}

```

## disassembly

```asm
0x1800ed99c  mov     rax, rsp
0x1800ed99f  mov     [rax+18h], rbx
0x1800ed9a3  push    rbp
0x1800ed9a4  push    rsi
0x1800ed9a5  push    rdi
0x1800ed9a6  push    r12
0x1800ed9a8  push    r13
0x1800ed9aa  push    r14
0x1800ed9ac  push    r15
0x1800ed9ae  lea     rbp, [rax-388h]
0x1800ed9b5  sub     rsp, 450h
0x1800ed9bc  movaps  xmmword ptr [rax-48h], xmm6
0x1800ed9c0  mov     rax, cs:__security_cookie
0x1800ed9c7  xor     rax, rsp
0x1800ed9ca  mov     [rbp+380h+var_50], rax
0x1800ed9d1  mov     rdi, rdx
0x1800ed9d4  mov     [rbp+380h+var_370], rdx
0x1800ed9d8  mov     r15, rcx
0x1800ed9db  mov     [rbp+380h+var_240], rcx
0x1800ed9e2  mov     [rbp+380h+var_150], rcx
0x1800ed9e9  xor     esi, esi
0x1800ed9eb  mov     [rbp+380h+var_400], esi
0x1800ed9ee  xorps   xmm0, xmm0
0x1800ed9f1  movups  xmmword ptr [rcx], xmm0
0x1800ed9f4  mov     [rcx+10h], rsi
0x1800ed9f8  mov     qword ptr [rcx+18h], 7
0x1800eda00  mov     [rcx], si
0x1800eda03  lea     r13, [rcx+28h]
0x1800eda07  mov     [r13+0], rsi
0x1800eda0b  mov     [r13+8], rsi
0x1800eda0f  mov     ecx, 0F8h; Size
0x1800eda14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eda19  mov     [rax], rax
0x1800eda1c  mov     [rax+8], rax
0x1800eda20  mov     [rax+10h], rax
0x1800eda24  lea     r14d, [rsi+1]
0x1800eda28  mov     word ptr [rax+18h], 101h
0x1800eda2e  mov     [r13+0], rax
0x1800eda32  lea     rbx, [r15+38h]
0x1800eda36  mov     [rbp+380h+var_310], rbx
0x1800eda3a  mov     [rbx], rsi
0x1800eda3d  mov     [rbx+8], rsi
0x1800eda41  mov     ecx, 0B8h; Size
0x1800eda46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eda4b  mov     [rax], rax
0x1800eda4e  mov     [rax+8], rax
0x1800eda52  mov     [rax+10h], rax
0x1800eda56  mov     word ptr [rax+18h], 101h
0x1800eda5c  mov     [rbx], rax
0x1800eda5f  mov     r12d, r14d
0x1800eda62  mov     [rbp+380h+var_400], r14d
0x1800eda66  cmp     word ptr cs:aName+8, si; ""
0x1800eda6d  jnz     loc_1800EEFF5
0x1800eda73  mov     [rbp+380h+var_2D8], r14d
0x1800eda7a  mov     [rbp+380h+var_2D4], 4
0x1800eda84  lea     rax, aName; "Name"
0x1800eda8b  mov     [rbp+380h+var_2C8], rax
0x1800eda92  lea     rax, [rbp+380h+var_2D8]
0x1800eda99  mov     [rbp+380h+var_2E0], rax
0x1800edaa0  lea     r8, [rbp+380h+var_2E0]
0x1800edaa7  lea     rdx, [rbp+380h+lpMem]
0x1800edaab  mov     rcx, rdi
0x1800edaae  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1800edab3  nop
0x1800edab4  mov     r9, [rax]
0x1800edab7  test    r9, r9
0x1800edaba  jz      short loc_1800EDAC2
0x1800edabc  mov     r9, [r9+10h]
0x1800edac0  jmp     short loc_1800EDAC9
0x1800edac2  lea     r9, Src+1
0x1800edac9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800edacd  inc     rdx
0x1800edad0  cmp     [r9+rdx*2], si
0x1800edad5  jnz     short loc_1800EDACD
0x1800edad7  cmp     rdx, [r15+18h]
0x1800edadb  ja      short loc_1800EDB0C
0x1800edadd  cmp     qword ptr [r15+18h], 7
0x1800edae2  jbe     short loc_1800EDAE9
0x1800edae4  mov     rdi, [r15]
0x1800edae7  jmp     short loc_1800EDAEC
0x1800edae9  mov     rdi, r15
0x1800edaec  mov     [r15+10h], rdx
0x1800edaf0  lea     rbx, [rdx+rdx]
0x1800edaf4  mov     r8, rbx; Size
0x1800edaf7  mov     rdx, r9; Src
0x1800edafa  mov     rcx, rdi; void *
0x1800edafd  call    memmove_0
0x1800edb02  mov     [rbx+rdi], si
0x1800edb06  mov     rdi, [rbp+380h+var_370]
0x1800edb0a  jmp     short loc_1800EDB15
0x1800edb0c  mov     rcx, r15
0x1800edb0f  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800edb14  nop
0x1800edb15  mov     rbx, [rbp+380h+lpMem]
0x1800edb19  test    rbx, rbx
0x1800edb1c  jz      short loc_1800EDB48
0x1800edb1e  or      eax, 0FFFFFFFFh
0x1800edb21  lock xadd [rbx+18h], eax
0x1800edb26  sub     eax, 1
0x1800edb29  jnz     short loc_1800EDB40
0x1800edb2b  nop
0x1800edb2c  call    WINRT_IMPL_GetProcessHeap
0x1800edb31  mov     rcx, rax; hHeap
0x1800edb34  mov     r8, rbx; lpMem
0x1800edb37  xor     edx, edx; dwFlags
0x1800edb39  call    WINRT_IMPL_HeapFree
0x1800edb3e  jmp     short loc_1800EDB48
0x1800edb40  test    eax, eax
0x1800edb42  js      loc_1800EEFF5
0x1800edb48  cmp     word ptr cs:aVersion+0Eh, si; ""
0x1800edb4f  jz      short loc_1800EDB58
0x1800edb51  call    cs:__imp_abort
0x1800edb58  mov     [rbp+380h+var_2D8], r14d
0x1800edb5f  mov     [rbp+380h+var_2D4], 7
0x1800edb69  lea     rax, aVersion; "Version"
0x1800edb70  mov     [rbp+380h+var_2C8], rax
0x1800edb77  lea     rax, [rbp+380h+var_2D8]
0x1800edb7e  mov     [rbp+380h+var_2E0], rax
0x1800edb85  lea     rdx, [rbp+380h+var_2E0]
0x1800edb8c  mov     rcx, rdi
0x1800edb8f  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x1800edb94  cvttsd2si rax, xmm0
0x1800edb99  mov     [r15+20h], eax
0x1800edb9d  cmp     word ptr cs:aFactdefinition+1Eh, si; ""
0x1800edba4  jz      short loc_1800EDBAD
0x1800edba6  call    cs:__imp_abort
0x1800edbad  mov     [rbp+380h+var_230], r14d
0x1800edbb4  mov     [rbp+380h+var_22C], 0Fh
0x1800edbbe  lea     rax, aFactdefinition; "FactDefinitions"
0x1800edbc5  mov     [rbp+380h+var_220], rax
0x1800edbcc  lea     rax, [rbp+380h+var_230]
0x1800edbd3  mov     [rbp+380h+var_238], rax
0x1800edbda  lea     r8, [rbp+380h+var_238]
0x1800edbe1  lea     rdx, [rbp+380h+var_348]
0x1800edbe5  mov     rcx, rdi
0x1800edbe8  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x1800edbed  nop
0x1800edbee  lea     rdx, [rsp+480h+var_440]
0x1800edbf3  lea     rcx, [rbp+380h+var_348]
0x1800edbf7  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(void)
0x1800edbfc  nop
0x1800edbfd  mov     [rbp+380h+lpMem], rsi
0x1800edc01  lea     rdx, [rbp+380h+lpMem]
0x1800edc05  lea     rcx, [rsp+480h+var_440]
0x1800edc0a  call    ??9Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator!=(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800edc0f  test    al, al
0x1800edc11  jz      loc_1800EE916
0x1800edc17  lea     rdi, aMetricsevent; "MetricsEvent"
0x1800edc1e  mov     [rsp+480h+var_410], rsi
0x1800edc23  or      r12d, 4
0x1800edc27  mov     [rbp+380h+var_400], r12d
0x1800edc2b  mov     rcx, [rsp+480h+var_440]
0x1800edc30  mov     dword ptr [rsp+480h+var_438+8], 2Eh ; '.'
0x1800edc38  lea     rax, aOnecoreuapInte; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x1800edc3f  mov     [rsp+480h+var_428], rax
0x1800edc44  mov     [rsp+480h+var_420], rsi
0x1800edc49  mov     rax, [rcx]
0x1800edc4c  lea     rdx, [rsp+480h+var_410]
0x1800edc51  mov     rax, [rax+30h]
0x1800edc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc5a  test    eax, eax
0x1800edc5c  js      loc_1800EF098
0x1800edc62  and     r12d, 0FFFFFFFBh
0x1800edc66  or      r12d, 2
0x1800edc6a  mov     [rbp+380h+var_400], r12d
0x1800edc6e  mov     [rbp+380h+var_198], sil
0x1800edc75  mov     [rbp+380h+var_178], sil
0x1800edc7c  mov     [rbp+380h+var_160], sil
0x1800edc83  lea     rdx, [rbp+380h+var_2C0]
0x1800edc8a  lea     rcx, [rsp+480h+var_410]
0x1800edc8f  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(void)
0x1800edc94  nop
0x1800edc95  lea     rdx, [rsp+480h+var_450]
0x1800edc9a  mov     rcx, rax
0x1800edc9d  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x1800edca2  nop
0x1800edca3  cmp     [rbp+380h+var_2C0], rsi
0x1800edcaa  jz      short loc_1800EDCB8
0x1800edcac  lea     rcx, [rbp+380h+var_2C0]
0x1800edcb3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800edcb8  cmp     word ptr cs:aFactsource+14h, si; ""
0x1800edcbf  jnz     loc_1800EEAC0
0x1800edcc5  mov     [rbp+380h+var_258], r14d
0x1800edccc  mov     [rbp+380h+var_254], 0Ah
0x1800edcd6  lea     rax, aFactsource; "FactSource"
0x1800edcdd  mov     [rbp+380h+var_248], rax
0x1800edce4  lea     rax, [rbp+380h+var_258]
0x1800edceb  mov     [rbp+380h+var_260], rax
0x1800edcf2  lea     r8, [rbp+380h+var_260]
0x1800edcf9  lea     rdx, [rbp+380h+var_378]
0x1800edcfd  lea     rcx, [rsp+480h+var_450]
0x1800edd02  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1800edd07  nop
0x1800edd08  mov     rbx, [rbp+380h+var_378]
0x1800edd0c  test    rbx, rbx
0x1800edd0f  jz      loc_1800EF066
0x1800edd15  mov     r8d, [rbx+4]; N
0x1800edd19  cmp     r8, 0Ch
0x1800edd1d  jnz     short loc_1800EDD37
0x1800edd1f  mov     rdx, rdi; S2
0x1800edd22  mov     rcx, [rbx+10h]; S1
0x1800edd26  call    wmemcmp
0x1800edd2b  test    eax, eax
0x1800edd2d  jnz     short loc_1800EDD37
0x1800edd2f  mov     [rbp+380h+var_210], esi
0x1800edd35  jmp     short loc_1800EDD6D
0x1800edd37  test    rbx, rbx
0x1800edd3a  jz      loc_1800EF066
0x1800edd40  mov     r8d, [rbx+4]; N
0x1800edd44  cmp     r8, 3
0x1800edd48  jnz     loc_1800EF066
0x1800edd4e  lea     rdx, aTip; "TIP"
0x1800edd55  mov     rcx, [rbx+10h]; S1
0x1800edd59  call    wmemcmp
0x1800edd5e  test    eax, eax
0x1800edd60  jnz     loc_1800EF066
0x1800edd66  mov     [rbp+380h+var_210], r14d
0x1800edd6d  cmp     word ptr cs:aMetricsevent+18h, si; ""
0x1800edd74  jnz     loc_1800EEAB9
0x1800edd7a  mov     dword ptr [rsp+480h+var_428], r14d
0x1800edd7f  mov     dword ptr [rsp+480h+var_428+4], 0Ch
0x1800edd87  mov     [rsp+480h+var_418], rdi
0x1800edd8c  lea     rax, [rsp+480h+var_428]
0x1800edd91  mov     qword ptr [rsp+480h+var_438+8], rax
0x1800edd96  lea     rdx, [rsp+480h+var_438+8]
0x1800edd9b  lea     rcx, [rsp+480h+var_450]
0x1800edda0  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x1800edda5  test    al, al
0x1800edda7  jz      loc_1800EE2EE
0x1800eddad  xorps   xmm0, xmm0
0x1800eddb0  movups  xmmword ptr [rbp+380h+var_140], xmm0
0x1800eddb7  mov     [rbp+380h+var_130], rsi
0x1800eddbe  mov     ebx, 7
0x1800eddc3  mov     [rbp+380h+var_128], rbx
0x1800eddca  mov     word ptr [rbp+380h+var_140], si
0x1800eddd1  movups  xmmword ptr [rbp+380h+var_120], xmm0
0x1800eddd8  mov     [rbp+380h+var_110], rsi
0x1800edddf  mov     [rbp+380h+var_108], rbx
0x1800edde6  mov     word ptr [rbp+380h+var_120], si
0x1800edded  movdqa  [rbp+380h+var_100], xmm0
0x1800eddf5  xorps   xmm1, xmm1
0x1800eddf8  movdqa  [rbp+380h+var_F0], xmm1
0x1800ede00  movdqa  [rbp+380h+var_E0], xmm0
0x1800ede08  cmp     word ptr cs:aMetricsevent+18h, si; ""
0x1800ede0f  jnz     loc_1800EEA96
0x1800ede15  mov     dword ptr [rsp+480h+var_428], r14d
0x1800ede1a  mov     dword ptr [rsp+480h+var_428+4], 0Ch
0x1800ede22  mov     [rsp+480h+var_418], rdi
0x1800ede27  lea     rax, [rsp+480h+var_428]
0x1800ede2c  mov     qword ptr [rsp+480h+var_438+8], rax
0x1800ede31  lea     r8, [rsp+480h+var_438+8]
0x1800ede36  lea     rdx, [rbp+380h+var_3F8]
0x1800ede3a  lea     rcx, [rsp+480h+var_450]
0x1800ede3f  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x1800ede44  nop
0x1800ede45  cmp     word ptr cs:aSourceeventinf+1Eh, si; ""
0x1800ede4c  jnz     loc_1800EEA8F
0x1800ede52  mov     [rbp+380h+var_360], r14d
0x1800ede56  mov     [rbp+380h+var_35C], 0Fh
0x1800ede5d  lea     rax, aSourceeventinf; "SourceEventInfo"
0x1800ede64  mov     [rbp+380h+var_350], rax
0x1800ede68  lea     rax, [rbp+380h+var_360]
0x1800ede6c  mov     [rbp+380h+var_368], rax
0x1800ede70  lea     r8, [rbp+380h+var_368]
0x1800ede74  lea     rdx, [rbp+380h+var_3F0]
0x1800ede78  lea     rcx, [rbp+380h+var_3F8]
0x1800ede7c  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x1800ede81  nop
0x1800ede82  cmp     word ptr cs:aSourceeventful+26h, si; ""
0x1800ede89  jnz     loc_1800EEA88
0x1800ede8f  mov     dword ptr [rsp+480h+var_428], r14d
0x1800ede94  mov     dword ptr [rsp+480h+var_428+4], 13h
0x1800ede9c  lea     rax, aSourceeventful; "SourceEventFullName"
0x1800edea3  mov     [rsp+480h+var_418], rax
0x1800edea8  lea     rax, [rsp+480h+var_428]
0x1800edead  mov     qword ptr [rsp+480h+var_438+8], rax
0x1800edeb2  lea     r8, [rsp+480h+var_438+8]
0x1800edeb7  lea     rdx, [rbp+380h+var_288]
0x1800edebe  lea     rcx, [rbp+380h+var_3F0]
0x1800edec2  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1800edec7  nop
0x1800edec8  mov     r9, [rax]
0x1800edecb  test    r9, r9
0x1800edece  jz      short loc_1800EDED6
0x1800eded0  mov     r9, [r9+10h]
0x1800eded4  jmp     short loc_1800EDEDD
0x1800eded6  lea     r9, Src+1
0x1800ededd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800edee1  inc     rdx
0x1800edee4  cmp     [r9+rdx*2], si
0x1800edee9  jnz     short loc_1800EDEE1
0x1800edeeb  cmp     rdx, [rbp+380h+var_128]
0x1800edef2  ja      short loc_1800EDF29
0x1800edef4  lea     rdi, [rbp+380h+var_140]
0x1800edefb  cmp     [rbp+380h+var_128], rbx
0x1800edf02  cmova   rdi, [rbp+380h+var_140]
0x1800edf0a  mov     [rbp+380h+var_130], rdx
0x1800edf11  lea     rbx, [rdx+rdx]
0x1800edf15  mov     r8, rbx; Size
0x1800edf18  mov     rdx, r9; Src
  ... truncated ...
```
