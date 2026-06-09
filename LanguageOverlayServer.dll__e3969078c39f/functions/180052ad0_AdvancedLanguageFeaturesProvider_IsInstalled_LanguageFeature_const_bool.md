# AdvancedLanguageFeaturesProvider::IsInstalled(LanguageFeature const &,bool *)

- ea: `0x180052ad0`
- end: `0x1800543fb`
- name: `?IsInstalled@AdvancedLanguageFeaturesProvider@@UEBAJAEBULanguageFeature@@PEA_N@Z`
- size: `6443`
- prototype: `__int64 __fastcall(AdvancedLanguageFeaturesProvider *__hidden this, const struct LanguageFeature *, bool *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180014ed0`
- `0x180034b30`
- `0x18003771c`
- `0x180050308`
- `0x180050594`
- `0x180052ad0`
- `0x180060f7c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800541df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800541df`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052bc4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053805`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053805`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054173`

## string_xrefs

- `0x180052b40`: `com.microsoft.speech.model.1`
- `0x180052b1b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052bdb`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052c59`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052cd6`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052d84`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052e43`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052f10`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052fe5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800530ed`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005320f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005337e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800534e4`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005366c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180053841`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180053a0d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180053bf5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180053fa4`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052b39`: `com.microsoft.voice.model.1`
- `0x180052b7c`: `Windows.ApplicationModel.AppExtensions.AppExtensionCatalog`

## pseudocode

```c
// Hidden C++ exception states: #wind=35 #try_helpers=1
__int64 __fastcall AdvancedLanguageFeaturesProvider::IsInstalled(
        AdvancedLanguageFeaturesProvider *this,
        const struct LanguageFeature *a2,
        bool *a3)
{
  wchar_t *v6; // rax
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int ActivationFactory; // eax
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  unsigned int v22; // ebx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rdi
  int v27; // ebx
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rcx
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  unsigned int i; // r14d
  int v39; // eax
  unsigned int v40; // ebx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // eax
  unsigned int v47; // ebx
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rdi
  int v55; // ebx
  __int64 (__fastcall ***v56)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 (__fastcall ***v60)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  int v63; // eax
  unsigned int v64; // ebx
  _QWORD *v65; // rcx
  __int64 (__fastcall ***v66)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v67)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 (__fastcall ***v70)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  _QWORD *v73; // rbx
  __int64 v74; // rdi
  HRESULT v75; // eax
  int v76; // edx
  unsigned int v77; // r8d
  int v78; // eax
  unsigned int v79; // ebx
  __int64 (__fastcall ***v80)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v81; // rcx
  __int64 (__fastcall ***v82)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v83)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 (__fastcall ***v86)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  int v89; // eax
  unsigned int v90; // ebx
  __int64 (__fastcall ***v91)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v92)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v93; // rcx
  __int64 (__fastcall ***v94)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v95)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 (__fastcall ***v98)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  int v101; // eax
  unsigned int v102; // ebx
  _QWORD *v103; // rcx
  __int64 (__fastcall ***v104)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v105)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v106; // rcx
  __int64 (__fastcall ***v107)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v108)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v109; // rcx
  __int64 v110; // rcx
  __int64 (__fastcall ***v111)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v112; // rcx
  __int64 v113; // rcx
  _QWORD *v114; // rbx
  __int64 v115; // rdi
  HRESULT v116; // eax
  int v117; // edx
  unsigned int v118; // r8d
  int v119; // eax
  unsigned int v120; // ebx
  __int64 (__fastcall ***v121)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v122; // rcx
  __int64 (__fastcall ***v123)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v124)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v125; // rcx
  __int64 (__fastcall ***v126)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v127)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v128; // rcx
  __int64 v129; // rcx
  __int64 (__fastcall ***v130)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v131; // rcx
  __int64 v132; // rcx
  int v133; // eax
  unsigned int v134; // ebx
  __int64 v135; // rcx
  __int64 (__fastcall ***v136)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v137; // rcx
  __int64 (__fastcall ***v138)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v139)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v140; // rcx
  __int64 (__fastcall ***v141)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v142)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v143; // rcx
  __int64 v144; // rcx
  __int64 (__fastcall ***v145)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v146; // rcx
  __int64 v147; // rcx
  int v148; // eax
  unsigned int v149; // ebx
  __int64 v150; // rcx
  __int64 (__fastcall ***v151)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v152; // rcx
  __int64 (__fastcall ***v153)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v154)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v155; // rcx
  __int64 (__fastcall ***v156)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v157)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v158; // rcx
  __int64 v159; // rcx
  __int64 (__fastcall ***v160)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v161; // rcx
  __int64 v162; // rcx
  __int64 v163; // rcx
  __int64 (__fastcall ***v164)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v165; // rcx
  __int64 (__fastcall ***v166)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v167)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v168; // rcx
  __int64 (__fastcall ***v169)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v170)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v171; // rcx
  __int64 v172; // rcx
  __int64 (__fastcall ***v173)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v174; // rcx
  __int64 v175; // rcx
  __int64 v176; // rdi
  __int64 (__fastcall *v177)(__int64, HSTRING *); // rbx
  int v178; // eax
  unsigned int v179; // ebx
  __int64 v180; // rcx
  __int64 (__fastcall ***v181)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v182; // rcx
  __int64 (__fastcall ***v183)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v184)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v185; // rcx
  __int64 (__fastcall ***v186)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v187)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v188; // rcx
  __int64 v189; // rcx
  __int64 (__fastcall ***v190)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v191; // rcx
  __int64 v192; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v194; // rcx
  const struct LanguageFeature *v195; // rdx
  void *p_hstringHeader; // rcx
  __int64 v197; // rcx
  __int64 (__fastcall ***v198)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v199; // rcx
  __int64 (__fastcall ***v200)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v201)(_QWORD, GUID *, _QWORD); // rcx
  _QWORD *v202; // rcx
  __int64 (__fastcall ***v203)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v204)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v205; // rcx
  __int64 v206; // rcx
  __int64 (__fastcall ***v207)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v208; // rcx
  __int64 v209; // rcx
  HSTRING_HEADER v210; // [rsp+20h] [rbp-108h] BYREF
  HSTRING v211; // [rsp+38h] [rbp-F0h] BYREF
  _QWORD v212[2]; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v213; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v214; // [rsp+58h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v215)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-C8h] BYREF
  __int64 v216; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v217; // [rsp+70h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v218)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v219)(_QWORD, GUID *, _QWORD **); // [rsp+80h] [rbp-A8h] BYREF
  _QWORD *v220; // [rsp+88h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v221)(_QWORD, GUID *, _QWORD); // [rsp+90h] [rbp-98h] BYREF
  __int64 (__fastcall ***v222)(_QWORD, GUID *, _QWORD **); // [rsp+98h] [rbp-90h] BYREF
  _QWORD *v223; // [rsp+A0h] [rbp-88h] BYREF
  __int64 (__fastcall ***v224)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-80h] BYREF
  __int64 v225; // [rsp+B0h] [rbp-78h] BYREF
  int v226; // [rsp+B8h] [rbp-70h] BYREF
  HSTRING v227; // [rsp+C0h] [rbp-68h] BYREF
  unsigned int v228; // [rsp+C8h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-58h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  if ( ((*((_DWORD *)a2 + 8) - 512) & 0xFFFFFDFF) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
      (const char *)0x80070057LL,
      (int)v210.Reserved.Reserved1);
    return 2147942487LL;
  }
  else
  {
    *a3 = 0;
    v6 = L"com.microsoft.speech.model.1";
    if ( *((_DWORD *)a2 + 8) != 512 )
      v6 = L"com.microsoft.voice.model.1";
    v227 = (HSTRING)v6;
    v213 = 0;
    string = 0;
    v7 = WindowsCreateStringReference(
           L"Windows.ApplicationModel.AppExtensions.AppExtensionCatalog",
           0x3Au,
           &hstringHeader,
           &string);
    if ( v7 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
LABEL_356:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v75, v76, v77);
LABEL_357:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v116, v117, v118);
      JUMPOUT(0x1800543F9LL);
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11, &v213);
    v12 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v214 = 0;
      v14 = v213;
      v15 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v213 + 48LL);
      v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v210, (const WCHAR **)&v227, v11);
      v17 = v15(v14, v16[1].Reserved.Reserved1, &v214);
      v18 = v17;
      if ( v17 >= 0 )
      {
        v215 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v214 + 48LL))(
                v214,
                &v215);
        v22 = v21;
        if ( v21 >= 0 )
        {
          v216 = 0;
          v26 = v215;
          v27 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(v215);
          if ( v27 >= 0 )
            v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v26)[8])(
                    v26,
                    &v216);
          if ( v27 >= 0 )
          {
            v228 = 0;
            v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v216 + 56LL))(v216, &v228);
            v33 = v32;
            if ( v32 >= 0 )
            {
              for ( i = 0; i < v228; ++i )
              {
                v217 = 0;
                v39 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v216 + 48LL))(v216, i, &v217);
                v40 = v39;
                if ( v39 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xFF,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v39,
                    (int)v210.Reserved.Reserved1);
                  v41 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                  v42 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                  }
                  v43 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v43)[2])(v43);
                  }
                  v44 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                  }
                  v45 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
                  }
                  return v40;
                }
                v218 = 0;
                v46 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v217 + 88LL))(
                        v217,
                        &v218);
                v47 = v46;
                if ( v46 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x102,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v46,
                    (int)v210.Reserved.Reserved1);
                  v48 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v48)[2])(v48);
                  }
                  v49 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
                  }
                  v50 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                  }
                  v51 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v51)[2])(v51);
                  }
                  v52 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                  }
                  v53 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                  }
                  return v47;
                }
                v219 = 0;
                v54 = v218;
                v55 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *>(v218);
                if ( v55 >= 0 )
                  v55 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **)))(*v54)[8])(
                          v54,
                          &v219);
                if ( v55 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x105,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v55,
                    (int)v210.Reserved.Reserved1);
                  v56 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v56)[2])(v56);
                  }
                  v57 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v57)[2])(v57);
                  }
                  v58 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                  }
                  v59 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
                  }
                  v60 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v60)[2])(v60);
                  }
                  v61 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                  }
                  v62 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                  }
                  return (unsigned int)v55;
                }
                v220 = 0;
                v63 = (**v219)(v219, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v220);
                v64 = v63;
                if ( v63 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x108,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v63,
                    (int)v210.Reserved.Reserved1);
                  v65 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v65 + 16LL))(v65);
                  }
                  v66 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v66)[2])(v66);
                  }
                  v67 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v67)[2])(v67);
                  }
                  v68 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
                  }
                  v69 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
                  }
                  v70 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v70)[2])(v70);
                  }
                  v71 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
                  }
                  v72 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
                  }
                  return v64;
                }
                v221 = 0;
                v73 = v220;
                v74 = *v220;
                v211 = 0;
                v75 = WindowsCreateStringReference(L"LocaleId", 8u, &v210, &v211);
                if ( v75 < 0 )
                  goto LABEL_356;
                v78 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v74 + 48))(v73, v211, &v221);
                v79 = v78;
                if ( v78 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x10B,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v78,
                    (int)v210.Reserved.Reserved1);
                  v80 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v80)[2])(v80);
                  }
                  v81 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v81 + 16LL))(v81);
                  }
                  v82 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v82)[2])(v82);
                  }
                  v83 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v83)[2])(v83);
                  }
                  v84 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                  }
                  v85 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                  }
                  v86 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v86)[2])(v86);
                  }
                  v87 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
                  }
                  v88 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
                  }
                  return v79;
                }
                v222 = 0;
                v89 = (**v221)(v221, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v222);
                v90 = v89;
                if ( v89 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x10E,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v89,
                    (int)v210.Reserved.Reserved1);
                  v91 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v91)[2])(v91);
                  }
                  v92 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v92)[2])(v92);
                  }
                  v93 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v93 + 16LL))(v93);
                  }
                  v94 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v94)[2])(v94);
                  }
                  v95 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v95)[2])(v95);
                  }
                  v96 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
                  }
                  v97 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
                  }
                  v98 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v98)[2])(v98);
                  }
                  v99 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
                  }
                  v100 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
                  }
                  return v90;
                }
                v223 = 0;
                v101 = (**v222)(v222, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v223);
                v102 = v101;
                if ( v101 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x111,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v101,
                    (int)v210.Reserved.Reserved1);
                  v103 = v223;
                  if ( v223 )
                  {
                    v223 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v103 + 16LL))(v103);
                  }
                  v104 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v104)[2])(v104);
                  }
                  v105 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v105)[2])(v105);
                  }
                  v106 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v106 + 16LL))(v106);
                  }
                  v107 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v107)[2])(v107);
                  }
                  v108 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v108)[2])(v108);
                  }
                  v109 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
                  }
                  v110 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
                  }
                  v111 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v111)[2])(v111);
                  }
                  v112 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
                  }
                  v113 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
                  }
                  return v102;
                }
                v224 = 0;
                v114 = v223;
                v115 = *v223;
                v211 = 0;
                v116 = WindowsCreateStringReference(L"#text", 5u, &v210, &v211);
                if ( v116 < 0 )
                  goto LABEL_357;
                v119 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v115 + 48))(v114, v211, &v224);
                v120 = v119;
                if ( v119 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x114,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v119,
                    (int)v210.Reserved.Reserved1);
                  v121 = v224;
                  if ( v224 )
                  {
                    v224 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v121)[2])(v121);
                  }
                  v122 = v223;
                  if ( v223 )
                  {
                    v223 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v122 + 16LL))(v122);
                  }
                  v123 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v123)[2])(v123);
                  }
                  v124 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v124)[2])(v124);
                  }
                  v125 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v125 + 16LL))(v125);
                  }
                  v126 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v126)[2])(v126);
                  }
                  v127 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v127)[2])(v127);
                  }
                  v128 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
                  }
                  v129 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
                  }
                  v130 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v130)[2])(v130);
                  }
                  v131 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
                  }
                  v132 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
                  }
                  return v120;
                }
                v225 = 0;
                v133 = (**v224)(v224, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v225);
                v134 = v133;
                if ( v133 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x117,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v133,
                    (int)v210.Reserved.Reserved1);
                  v135 = v225;
                  if ( v225 )
                  {
                    v225 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
                  }
                  v136 = v224;
                  if ( v224 )
                  {
                    v224 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v136)[2])(v136);
                  }
                  v137 = v223;
                  if ( v223 )
                  {
                    v223 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v137 + 16LL))(v137);
                  }
                  v138 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v138)[2])(v138);
                  }
                  v139 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v139)[2])(v139);
                  }
                  v140 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v140 + 16LL))(v140);
                  }
                  v141 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v141)[2])(v141);
                  }
                  v142 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v142)[2])(v142);
                  }
                  v143 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v143 + 16LL))(v143);
                  }
                  v144 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v144 + 16LL))(v144);
                  }
                  v145 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v145)[2])(v145);
                  }
                  v146 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v146 + 16LL))(v146);
                  }
                  v147 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v147 + 16LL))(v147);
                  }
                  return v134;
                }
                v226 = 0;
                v148 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v225 + 48LL))(v225, &v226);
                v149 = v148;
                if ( v148 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v148,
                    (int)v210.Reserved.Reserved1);
                  v150 = v225;
                  if ( v225 )
                  {
                    v225 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v150 + 16LL))(v150);
                  }
                  v151 = v224;
                  if ( v224 )
                  {
                    v224 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v151)[2])(v151);
                  }
                  v152 = v223;
                  if ( v223 )
                  {
                    v223 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v152 + 16LL))(v152);
                  }
                  v153 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v153)[2])(v153);
                  }
                  v154 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v154)[2])(v154);
                  }
                  v155 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
                  }
                  v156 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v156)[2])(v156);
                  }
                  v157 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v157)[2])(v157);
                  }
                  v158 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v158 + 16LL))(v158);
                  }
                  v159 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v159 + 16LL))(v159);
                  }
                  v160 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v160)[2])(v160);
                  }
                  v161 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v161 + 16LL))(v161);
                  }
                  v162 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v162 + 16LL))(v162);
                  }
                  return v149;
                }
                if ( v226 != 12 )
                {
                  v163 = v225;
                  if ( v225 )
                  {
                    v225 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v163 + 16LL))(v163);
                  }
                  v164 = v224;
                  if ( v224 )
                  {
                    v224 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v164)[2])(v164);
                  }
                  v165 = v223;
                  if ( v223 )
                  {
                    v223 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v165 + 16LL))(v165);
                  }
                  v166 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v166)[2])(v166);
                  }
                  v167 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v167)[2])(v167);
                  }
                  v168 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v168 + 16LL))(v168);
                  }
                  v169 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v169)[2])(v169);
                  }
                  v170 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v170)[2])(v170);
                  }
                  v171 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v171 + 16LL))(v171);
                  }
                  v172 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v172 + 16LL))(v172);
                  }
                  v173 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v173)[2])(v173);
                  }
                  v174 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v174 + 16LL))(v174);
                  }
                  v175 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v175 + 16LL))(v175);
                  }
                  return 2147942450LL;
                }
                v227 = 0;
                v176 = v225;
                v177 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v225 + 152LL);
                WindowsDeleteString(0);
                v227 = 0;
                v178 = v177(v176, &v227);
                v179 = v178;
                if ( v178 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x122,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                    (const char *)(unsigned int)v178,
                    (int)v210.Reserved.Reserved1);
                  WindowsDeleteString(v227);
                  v227 = 0;
                  v180 = v225;
                  if ( v225 )
                  {
                    v225 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v180 + 16LL))(v180);
                  }
                  v181 = v224;
                  if ( v224 )
                  {
                    v224 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v181)[2])(v181);
                  }
                  v182 = v223;
                  if ( v223 )
                  {
                    v223 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v182 + 16LL))(v182);
                  }
                  v183 = v222;
                  if ( v222 )
                  {
                    v222 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v183)[2])(v183);
                  }
                  v184 = v221;
                  if ( v221 )
                  {
                    v221 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v184)[2])(v184);
                  }
                  v185 = v220;
                  if ( v220 )
                  {
                    v220 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v185 + 16LL))(v185);
                  }
                  v186 = v219;
                  if ( v219 )
                  {
                    v219 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v186)[2])(v186);
                  }
                  v187 = v218;
                  if ( v218 )
                  {
                    v218 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v187)[2])(v187);
                  }
                  v188 = v217;
                  if ( v217 )
                  {
                    v217 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v188 + 16LL))(v188);
                  }
                  v189 = v216;
                  if ( v216 )
                  {
                    v216 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v189 + 16LL))(v189);
                  }
                  v190 = v215;
                  if ( v215 )
                  {
                    v215 = 0;
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v190)[2])(v190);
                  }
                  v191 = v214;
                  if ( v214 )
                  {
                    v214 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v191 + 16LL))(v191);
                  }
                  v192 = v213;
                  if ( v213 )
                  {
                    v213 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v192 + 16LL))(v192);
                  }
                  return v179;
                }
                StringRawBuffer = WindowsGetStringRawBuffer(v227, 0);
                v212[0] = StringRawBuffer;
                v194 = -1;
                do
                  ++v194;
                while ( StringRawBuffer[v194] );
                v212[1] = v194;
                bcp47::ConvertToNormalizedForm(&hstringHeader, v212);
                if ( *((_QWORD *)a2 + 3) <= 7u )
                  v195 = a2;
                else
                  v195 = *(const struct LanguageFeature **)a2;
                p_hstringHeader = &hstringHeader;
                if ( (unsigned __int64)string > 7 )
                  p_hstringHeader = hstringHeader.Reserved.Reserved1;
                if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] == *((_QWORD *)a2 + 2)
                  && (!*(_QWORD *)&hstringHeader.Reserved.Reserved2[16]
                   || !(unsigned int)_o__wcsnicmp(p_hstringHeader, v195)) )
                {
                  *a3 = 1;
                }
                std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&hstringHeader);
                WindowsDeleteString(v227);
                v227 = 0;
                v197 = v225;
                if ( v225 )
                {
                  v225 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v197 + 16LL))(v197);
                }
                v198 = v224;
                if ( v224 )
                {
                  v224 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v198)[2])(v198);
                }
                v199 = v223;
                if ( v223 )
                {
                  v223 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v199 + 16LL))(v199);
                }
                v200 = v222;
                if ( v222 )
                {
                  v222 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v200)[2])(v200);
                }
                v201 = v221;
                if ( v221 )
                {
                  v221 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v201)[2])(v201);
                }
                v202 = v220;
                if ( v220 )
                {
                  v220 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v202 + 16LL))(v202);
                }
                v203 = v219;
                if ( v219 )
                {
                  v219 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v203)[2])(v203);
                }
                v204 = v218;
                if ( v218 )
                {
                  v218 = 0;
                  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v204)[2])(v204);
                }
                v205 = v217;
                if ( v217 )
                {
                  v217 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v205 + 16LL))(v205);
                }
              }
              v206 = v216;
              if ( v216 )
              {
                v216 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
              }
              v207 = v215;
              if ( v215 )
              {
                v215 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v207)[2])(v207);
              }
              v208 = v214;
              if ( v214 )
              {
                v214 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v208 + 16LL))(v208);
              }
              v209 = v213;
              if ( v213 )
              {
                v213 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v209 + 16LL))(v209);
              }
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFB,
                (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
                (const char *)(unsigned int)v32,
                (int)v210.Reserved.Reserved1);
              v34 = v216;
              if ( v216 )
              {
                v216 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              }
              v35 = v215;
              if ( v215 )
              {
                v215 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v35)[2])(v35);
              }
              v36 = v214;
              if ( v214 )
              {
                v214 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
              v37 = v213;
              if ( v213 )
              {
                v213 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              }
              return v33;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF8,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
              (const char *)(unsigned int)v27,
              (int)v210.Reserved.Reserved1);
            v28 = v216;
            if ( v216 )
            {
              v216 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            v29 = v215;
            if ( v215 )
            {
              v215 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v29)[2])(v29);
            }
            v30 = v214;
            if ( v214 )
            {
              v214 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            v31 = v213;
            if ( v213 )
            {
              v213 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            }
            return (unsigned int)v27;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF5,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
            (const char *)(unsigned int)v21,
            (int)v210.Reserved.Reserved1);
          v23 = v215;
          if ( v215 )
          {
            v215 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
          }
          v24 = v214;
          if ( v214 )
          {
            v214 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          v25 = v213;
          if ( v213 )
          {
            v213 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          return v22;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          (const char *)(unsigned int)v17,
          (int)v210.Reserved.Reserved1);
        v19 = v214;
        if ( v214 )
        {
          v214 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v20 = v213;
        if ( v213 )
        {
          v213 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        return v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)v210.Reserved.Reserved1);
      v13 = v213;
      if ( v213 )
      {
        v213 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v12;
    }
  }
}

```

## disassembly

```asm
0x180052ad0  mov     [rsp+arg_0], rbx
0x180052ad5  push    rsi
0x180052ad6  push    rdi
0x180052ad7  push    r12
0x180052ad9  push    r14
0x180052adb  push    r15
0x180052add  sub     rsp, 100h
0x180052ae4  mov     rax, cs:__security_cookie
0x180052aeb  xor     rax, rsp
0x180052aee  mov     [rsp+128h+var_38], rax
0x180052af6  mov     r15, r8
0x180052af9  mov     rsi, rdx
0x180052afc  mov     eax, [rdx+20h]
0x180052aff  add     eax, 0FFFFFE00h
0x180052b04  test    eax, 0FFFFFDFFh
0x180052b09  jz      short loc_180052B33
0x180052b0b  mov     rcx, [rsp+128h]; this
0x180052b13  mov     ebx, 80070057h
0x180052b18  mov     r9d, ebx; char *
0x180052b1b  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052b22  mov     edx, 0E9h; void *
0x180052b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b2c  mov     eax, ebx
0x180052b2e  jmp     loc_1800543BA
0x180052b33  xor     r12d, r12d
0x180052b36  mov     [r8], r12b
0x180052b39  lea     rcx, aComMicrosoftVo; "com.microsoft.voice.model.1"
0x180052b40  lea     rax, aComMicrosoftSp; "com.microsoft.speech.model.1"
0x180052b47  cmp     dword ptr [rdx+20h], 200h
0x180052b4e  cmovnz  rax, rcx
0x180052b52  mov     [rsp+128h+var_68], rax
0x180052b5a  mov     [rsp+128h+var_D8], r12
0x180052b5f  mov     [rsp+128h+string], r12
0x180052b67  lea     r9, [rsp+128h+string]; string
0x180052b6f  lea     r8, [rsp+128h+hstringHeader]; hstringHeader
0x180052b77  lea     edx, [r12+3Ah]; length
0x180052b7c  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_AppExtensions_AppExtensionCatalog@@3QBGB; "Windows.ApplicationModel.AppExtensions."...
0x180052b83  call    cs:__imp_WindowsCreateStringReference
0x180052b89  test    eax, eax
0x180052b8b  js      loc_1800543E2
0x180052b91  mov     rbx, [rsp+128h+string]
0x180052b99  mov     rcx, [rsp+128h+var_D8]
0x180052b9e  test    rcx, rcx
0x180052ba1  jz      short loc_180052BB5
0x180052ba3  mov     [rsp+128h+var_D8], r12
0x180052ba8  mov     rax, [rcx]
0x180052bab  mov     rax, [rax+10h]
0x180052baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052bb4  nop
0x180052bb5  lea     r8, [rsp+128h+var_D8]
0x180052bba  lea     rdx, _GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11
0x180052bc1  mov     rcx, rbx
0x180052bc4  call    cs:__imp_RoGetActivationFactory
0x180052bca  mov     ebx, eax
0x180052bcc  test    eax, eax
0x180052bce  jns     short loc_180052C10
0x180052bd0  mov     rcx, [rsp+128h]; this
0x180052bd8  mov     r9d, eax; char *
0x180052bdb  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052be2  mov     edx, 0EFh; void *
0x180052be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052bec  nop
0x180052bed  mov     rcx, [rsp+128h+var_D8]
0x180052bf2  test    rcx, rcx
0x180052bf5  jz      short loc_180052C09
0x180052bf7  mov     [rsp+128h+var_D8], r12
0x180052bfc  mov     rax, [rcx]
0x180052bff  mov     rax, [rax+10h]
0x180052c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c08  nop
0x180052c09  mov     eax, ebx
0x180052c0b  jmp     loc_1800543BA
0x180052c10  mov     [rsp+128h+var_D0], r12
0x180052c15  mov     rdi, [rsp+128h+var_D8]
0x180052c1a  mov     rax, [rdi]
0x180052c1d  mov     rbx, [rax+30h]
0x180052c21  lea     rdx, [rsp+128h+var_68]
0x180052c29  lea     rcx, [rsp+128h+var_108]
0x180052c2e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180052c33  nop
0x180052c34  lea     r8, [rsp+128h+var_D0]
0x180052c39  mov     rdx, [rax+18h]
0x180052c3d  mov     rcx, rdi
0x180052c40  mov     rax, rbx
0x180052c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c48  mov     ebx, eax
0x180052c4a  test    eax, eax
0x180052c4c  jns     short loc_180052CAA
0x180052c4e  mov     rcx, [rsp+128h]; this
0x180052c56  mov     r9d, eax; char *
0x180052c59  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052c60  mov     edx, 0F2h; void *
0x180052c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052c6a  nop
0x180052c6b  mov     rcx, [rsp+128h+var_D0]
0x180052c70  test    rcx, rcx
0x180052c73  jz      short loc_180052C87
0x180052c75  mov     [rsp+128h+var_D0], r12
0x180052c7a  mov     rax, [rcx]
0x180052c7d  mov     rax, [rax+10h]
0x180052c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c86  nop
0x180052c87  mov     rcx, [rsp+128h+var_D8]
0x180052c8c  test    rcx, rcx
0x180052c8f  jz      short loc_180052CA3
0x180052c91  mov     [rsp+128h+var_D8], r12
0x180052c96  mov     rax, [rcx]
0x180052c99  mov     rax, [rax+10h]
0x180052c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ca2  nop
0x180052ca3  mov     eax, ebx
0x180052ca5  jmp     loc_1800543BA
0x180052caa  mov     [rsp+128h+var_C8], r12
0x180052caf  mov     rcx, [rsp+128h+var_D0]
0x180052cb4  mov     rax, [rcx]
0x180052cb7  lea     rdx, [rsp+128h+var_C8]
0x180052cbc  mov     rax, [rax+30h]
0x180052cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cc5  mov     ebx, eax
0x180052cc7  test    eax, eax
0x180052cc9  jns     short loc_180052D43
0x180052ccb  mov     rcx, [rsp+128h]; this
0x180052cd3  mov     r9d, eax; char *
0x180052cd6  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052cdd  mov     edx, 0F5h; void *
0x180052ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ce7  nop
0x180052ce8  mov     rcx, [rsp+128h+var_C8]
0x180052ced  test    rcx, rcx
0x180052cf0  jz      short loc_180052D04
0x180052cf2  mov     [rsp+128h+var_C8], r12
0x180052cf7  mov     rax, [rcx]
0x180052cfa  mov     rax, [rax+10h]
0x180052cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d03  nop
0x180052d04  mov     rcx, [rsp+128h+var_D0]
0x180052d09  test    rcx, rcx
0x180052d0c  jz      short loc_180052D20
0x180052d0e  mov     [rsp+128h+var_D0], r12
0x180052d13  mov     rax, [rcx]
0x180052d16  mov     rax, [rax+10h]
0x180052d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d1f  nop
0x180052d20  mov     rcx, [rsp+128h+var_D8]
0x180052d25  test    rcx, rcx
0x180052d28  jz      short loc_180052D3C
0x180052d2a  mov     [rsp+128h+var_D8], r12
0x180052d2f  mov     rax, [rcx]
0x180052d32  mov     rax, [rax+10h]
0x180052d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d3b  nop
0x180052d3c  mov     eax, ebx
0x180052d3e  jmp     loc_1800543BA
0x180052d43  mov     [rsp+128h+var_C0], r12
0x180052d48  mov     rdi, [rsp+128h+var_C8]
0x180052d4d  mov     rcx, rdi
0x180052d50  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180052d55  mov     ebx, eax
0x180052d57  test    eax, eax
0x180052d59  js      short loc_180052D71
0x180052d5b  mov     rax, [rdi]
0x180052d5e  lea     rdx, [rsp+128h+var_C0]
0x180052d63  mov     rcx, rdi
0x180052d66  mov     rax, [rax+40h]
0x180052d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d6f  mov     ebx, eax
0x180052d71  test    ebx, ebx
0x180052d73  jns     loc_180052E0D
0x180052d79  mov     rcx, [rsp+128h]; this
0x180052d81  mov     r9d, ebx; char *
0x180052d84  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052d8b  mov     edx, 0F8h; void *
0x180052d90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d95  nop
0x180052d96  mov     rcx, [rsp+128h+var_C0]
0x180052d9b  test    rcx, rcx
0x180052d9e  jz      short loc_180052DB2
0x180052da0  mov     [rsp+128h+var_C0], r12
0x180052da5  mov     rax, [rcx]
0x180052da8  mov     rax, [rax+10h]
0x180052dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052db1  nop
0x180052db2  mov     rcx, [rsp+128h+var_C8]
0x180052db7  test    rcx, rcx
0x180052dba  jz      short loc_180052DCE
0x180052dbc  mov     [rsp+128h+var_C8], r12
0x180052dc1  mov     rax, [rcx]
0x180052dc4  mov     rax, [rax+10h]
0x180052dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dcd  nop
0x180052dce  mov     rcx, [rsp+128h+var_D0]
0x180052dd3  test    rcx, rcx
0x180052dd6  jz      short loc_180052DEA
0x180052dd8  mov     [rsp+128h+var_D0], r12
0x180052ddd  mov     rax, [rcx]
0x180052de0  mov     rax, [rax+10h]
0x180052de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052de9  nop
0x180052dea  mov     rcx, [rsp+128h+var_D8]
0x180052def  test    rcx, rcx
0x180052df2  jz      short loc_180052E06
0x180052df4  mov     [rsp+128h+var_D8], r12
0x180052df9  mov     rax, [rcx]
0x180052dfc  mov     rax, [rax+10h]
0x180052e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e05  nop
0x180052e06  mov     eax, ebx
0x180052e08  jmp     loc_1800543BA
0x180052e0d  mov     [rsp+128h+var_60], r12d
0x180052e15  mov     rcx, [rsp+128h+var_C0]
0x180052e1a  mov     rax, [rcx]
0x180052e1d  lea     rdx, [rsp+128h+var_60]
0x180052e25  mov     rax, [rax+38h]
0x180052e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e2e  mov     ebx, eax
0x180052e30  test    eax, eax
0x180052e32  jns     loc_180052ECC
0x180052e38  mov     rcx, [rsp+128h]; this
0x180052e40  mov     r9d, eax; char *
0x180052e43  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052e4a  mov     edx, 0FBh; void *
0x180052e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052e54  nop
0x180052e55  mov     rcx, [rsp+128h+var_C0]
0x180052e5a  test    rcx, rcx
0x180052e5d  jz      short loc_180052E71
0x180052e5f  mov     [rsp+128h+var_C0], r12
0x180052e64  mov     rax, [rcx]
0x180052e67  mov     rax, [rax+10h]
0x180052e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e70  nop
0x180052e71  mov     rcx, [rsp+128h+var_C8]
0x180052e76  test    rcx, rcx
0x180052e79  jz      short loc_180052E8D
0x180052e7b  mov     [rsp+128h+var_C8], r12
0x180052e80  mov     rax, [rcx]
0x180052e83  mov     rax, [rax+10h]
0x180052e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e8c  nop
0x180052e8d  mov     rcx, [rsp+128h+var_D0]
0x180052e92  test    rcx, rcx
0x180052e95  jz      short loc_180052EA9
0x180052e97  mov     [rsp+128h+var_D0], r12
0x180052e9c  mov     rax, [rcx]
0x180052e9f  mov     rax, [rax+10h]
0x180052ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ea8  nop
0x180052ea9  mov     rcx, [rsp+128h+var_D8]
0x180052eae  test    rcx, rcx
0x180052eb1  jz      short loc_180052EC5
0x180052eb3  mov     [rsp+128h+var_D8], r12
0x180052eb8  mov     rax, [rcx]
0x180052ebb  mov     rax, [rax+10h]
0x180052ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ec4  nop
0x180052ec5  mov     eax, ebx
0x180052ec7  jmp     loc_1800543BA
0x180052ecc  mov     r14d, r12d
0x180052ecf  cmp     r14d, [rsp+128h+var_60]
0x180052ed7  jnb     loc_18005433F
0x180052edd  mov     [rsp+128h+var_B8], r12
0x180052ee2  mov     rcx, [rsp+128h+var_C0]
0x180052ee7  mov     rax, [rcx]
0x180052eea  lea     r8, [rsp+128h+var_B8]
0x180052eef  mov     edx, r14d
0x180052ef2  mov     rax, [rax+30h]
0x180052ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052efb  mov     ebx, eax
0x180052efd  test    eax, eax
0x180052eff  jns     loc_180052FB5
0x180052f05  mov     rcx, [rsp+128h]; this
0x180052f0d  mov     r9d, eax; char *
0x180052f10  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052f17  mov     edx, 0FFh; void *
0x180052f1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052f21  nop
0x180052f22  mov     rcx, [rsp+128h+var_B8]
0x180052f27  test    rcx, rcx
0x180052f2a  jz      short loc_180052F3E
0x180052f2c  mov     [rsp+128h+var_B8], r12
0x180052f31  mov     rax, [rcx]
0x180052f34  mov     rax, [rax+10h]
0x180052f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f3d  nop
0x180052f3e  mov     rcx, [rsp+128h+var_C0]
0x180052f43  test    rcx, rcx
0x180052f46  jz      short loc_180052F5A
0x180052f48  mov     [rsp+128h+var_C0], r12
0x180052f4d  mov     rax, [rcx]
0x180052f50  mov     rax, [rax+10h]
0x180052f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f59  nop
0x180052f5a  mov     rcx, [rsp+128h+var_C8]
0x180052f5f  test    rcx, rcx
0x180052f62  jz      short loc_180052F76
0x180052f64  mov     [rsp+128h+var_C8], r12
0x180052f69  mov     rax, [rcx]
0x180052f6c  mov     rax, [rax+10h]
0x180052f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f75  nop
  ... truncated ...
```
