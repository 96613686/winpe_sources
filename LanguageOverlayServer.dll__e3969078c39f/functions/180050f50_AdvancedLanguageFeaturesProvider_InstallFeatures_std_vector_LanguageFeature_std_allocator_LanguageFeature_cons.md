# AdvancedLanguageFeaturesProvider::InstallFeatures(std::vector<LanguageFeature,std::allocator<LanguageFeature>> const &,ushort const *,std::function<void (uint,LanguagePackInstallProgressState)> const &)

- ea: `0x180050f50`
- end: `0x1800526ab`
- name: `?InstallFeatures@AdvancedLanguageFeaturesProvider@@UEAAJAEBV?$vector@ULanguageFeature@@V?$allocator@ULanguageFeature@@@std@@@std@@PEBGAEBV?$function@$$A6AXIW4LanguagePackInstallProgressState@@@Z@3@@Z`
- size: `5979`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x18000a008`
- `0x18000a024`
- `0x18000a6cc`
- `0x180014ed0`
- `0x180034b30`
- `0x18003771c`
- `0x180049b88`
- `0x18004aea0`
- `0x18004af54`
- `0x18004bc48`
- `0x18004da80`
- `0x180050280`
- `0x180050f50`
- `0x180055024`
- `0x18005515c`
- `0x18005845c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052484`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800510d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005194c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800510d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005194c`
- `msvcp_win!_Cnd_wait` at `0x180052258`
- `msvcp_win!_Cnd_wait` at `0x180052258`
- `msvcp_win!_Mtx_unlock` at `0x180052267`
- `msvcp_win!_Mtx_unlock` at `0x180052267`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052225`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052241`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052225`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052241`
- `msvcp_win!_Mtx_lock` at `0x180052216`
- `msvcp_win!_Mtx_lock` at `0x180052216`

## string_xrefs

- `0x180052698`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800510cc`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x18005126b`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallOptions`
- `0x180051945`: `Language Overlay Service`
- `0x180050fb7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800519e5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180051b12`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180051c30`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180051d6b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180051ec6`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052043`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800522ba`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800524c1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31 #try_helpers=1
__int64 __fastcall AdvancedLanguageFeaturesProvider::InstallFeatures(
        __int64 a1,
        __int64 *a2,
        const WCHAR *a3,
        __int64 a4)
{
  void *Reserved1; // rsi
  __int64 v5; // rdi
  int v6; // r14d
  __int64 v7; // r13
  __int64 v8; // rax
  __m128i si128; // xmm6
  int PackageFamilyName; // eax
  unsigned int v11; // ebx
  int ProductIdFromPackageFamilyName; // eax
  unsigned int v14; // ebx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  unsigned int v19; // ebx
  _QWORD *v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v24; // rcx
  int v25; // eax
  _QWORD *v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  HRESULT v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  int v31; // eax
  _QWORD *v32; // rcx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v34; // rcx
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v37)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v38; // rcx
  int v39; // eax
  _QWORD *v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rcx
  int v44; // eax
  __int64 v45; // rdx
  _QWORD *v46; // rcx
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rcx
  int v50; // eax
  _QWORD *v51; // rcx
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v53; // rcx
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rcx
  int v55; // eax
  _QWORD *v56; // rcx
  __int64 (__fastcall ***v57)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v58; // rcx
  __int64 (__fastcall ***v59)(_QWORD, _QWORD, _QWORD); // rcx
  int v60; // eax
  _QWORD *v61; // rcx
  __int64 (__fastcall ***v62)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v63; // rcx
  __int64 (__fastcall ***v64)(_QWORD, _QWORD, _QWORD); // rcx
  int v65; // eax
  unsigned int v66; // r8d
  _QWORD *v67; // rcx
  __int64 (__fastcall ***v68)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v69; // rcx
  __int64 (__fastcall ***v70)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v71; // rdi
  __int64 v72; // r15
  HSTRING_HEADER *v73; // rax
  HRESULT v74; // eax
  int v75; // edx
  unsigned int v76; // r8d
  HSTRING v77; // rbx
  const WCHAR *v78; // rax
  HSTRING_HEADER *v79; // rax
  int v80; // eax
  int v81; // r8d
  __int64 (__fastcall ***v82)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v83; // rcx
  __int64 (__fastcall ***v84)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v85; // rcx
  __int64 (__fastcall ***v86)(_QWORD, _QWORD, _QWORD); // rcx
  int v87; // eax
  __int64 v88; // rcx
  __int64 (__fastcall ***v89)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v90; // rcx
  __int64 (__fastcall ***v91)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v92; // rcx
  __int64 (__fastcall ***v93)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v94; // rcx
  __int64 (__fastcall ***v95)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v96; // rcx
  __int64 (__fastcall ***v97)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v98; // rcx
  _QWORD *v99; // rcx
  int v100; // eax
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 (__fastcall ***v103)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v104; // rcx
  __int64 (__fastcall ***v105)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v106; // rcx
  __int64 (__fastcall ***v107)(_QWORD, _QWORD, _QWORD); // rcx
  int v108; // eax
  __int64 v109; // rcx
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int64 (__fastcall ***v112)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v113; // rcx
  __int64 (__fastcall ***v114)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v115; // rcx
  __int64 (__fastcall ***v116)(_QWORD, _QWORD, _QWORD); // rcx
  int v117; // eax
  unsigned int v118; // r8d
  __int64 v119; // rcx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 (__fastcall ***v122)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v123; // rcx
  __int64 (__fastcall ***v124)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v125; // rcx
  __int64 (__fastcall ***v126)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v127)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v128)(_QWORD, GUID *, _QWORD **); // rbx
  const WCHAR *v129; // rdx
  HSTRING_HEADER *v130; // rax
  __int64 v131; // rbx
  __int64 v132; // rdi
  int v133; // eax
  unsigned int v134; // edi
  __int64 v135; // rcx
  __int64 v136; // rcx
  __int64 v137; // rcx
  __int64 v138; // rcx
  __int64 (__fastcall ***v139)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v140; // rcx
  __int64 (__fastcall ***v141)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v142; // rcx
  __int64 (__fastcall ***v143)(_QWORD, _QWORD, _QWORD); // rcx
  BOOL v144; // eax
  const char *v145; // r9
  wil::details::in1diag3 *v146; // rcx
  int v147; // eax
  __int64 v148; // rcx
  __int64 v149; // rcx
  __int64 v150; // rcx
  __int64 v151; // rcx
  __int64 (__fastcall ***v152)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v153; // rcx
  __int64 (__fastcall ***v154)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v155; // rcx
  __int64 (__fastcall ***v156)(_QWORD, _QWORD, _QWORD); // rcx
  int v157; // [rsp+20h] [rbp-1C8h]
  const WCHAR *v158; // [rsp+40h] [rbp-1A8h] BYREF
  int v159; // [rsp+48h] [rbp-1A0h]
  HANDLE hObject; // [rsp+50h] [rbp-198h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-190h] BYREF
  HSTRING string; // [rsp+70h] [rbp-178h] BYREF
  __int64 v163; // [rsp+78h] [rbp-170h]
  const WCHAR *v164; // [rsp+80h] [rbp-168h]
  __int64 v165; // [rsp+88h] [rbp-160h]
  __int64 v166; // [rsp+90h] [rbp-158h]
  __int64 v167; // [rsp+98h] [rbp-150h]
  __int64 *v168; // [rsp+A0h] [rbp-148h]
  __int64 *v169; // [rsp+A8h] [rbp-140h]
  char v170; // [rsp+B0h] [rbp-138h]
  HSTRING_HEADER v171; // [rsp+B8h] [rbp-130h] BYREF
  HSTRING_HEADER v172; // [rsp+D8h] [rbp-110h] BYREF
  const WCHAR *v173; // [rsp+F8h] [rbp-F0h] BYREF
  _QWORD *v174; // [rsp+100h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v175)(_QWORD, GUID *, _QWORD **); // [rsp+108h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v176)(_QWORD, GUID *, _QWORD **); // [rsp+110h] [rbp-D8h] BYREF
  _QWORD *v177; // [rsp+118h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v178)(_QWORD, GUID *, __int64 *); // [rsp+120h] [rbp-C8h]
  __int64 v179; // [rsp+128h] [rbp-C0h] BYREF
  __int64 v180; // [rsp+130h] [rbp-B8h] BYREF
  __int64 v181; // [rsp+138h] [rbp-B0h] BYREF
  __int64 v182; // [rsp+140h] [rbp-A8h] BYREF
  __int128 v183; // [rsp+148h] [rbp-A0h] BYREF
  __m128i v184; // [rsp+158h] [rbp-90h]
  int v185; // [rsp+168h] [rbp-80h] BYREF
  int v186; // [rsp+16Ch] [rbp-7Ch] BYREF
  _OWORD v187[2]; // [rsp+170h] [rbp-78h] BYREF
  __int64 v188; // [rsp+190h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v163 = a4;
  Reserved1 = (void *)a3;
  v164 = a3;
  v5 = a1;
  v165 = a1;
  v173 = a3;
  v6 = 0;
  v159 = 0;
  v7 = *a2;
  v8 = a2[1];
  v166 = v8;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    if ( v7 == v8 )
      return 0;
    v187[0] = 0;
    v187[1] = si128;
    LOWORD(v187[0]) = 0;
    PackageFamilyName = AdvancedLanguageFeaturesProvider::_GetPackageFamilyName(v5, v7, (void **)v187);
    v11 = PackageFamilyName;
    if ( PackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)PackageFamilyName,
        v157);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v187);
      return v11;
    }
    v183 = 0;
    v184 = si128;
    LOWORD(v183) = 0;
    ProductIdFromPackageFamilyName = AdvancedLanguageFeaturesProvider::_GetProductIdFromPackageFamilyName(
                                       v5,
                                       (const WCHAR *)v187,
                                       (char **)&v183);
    v14 = ProductIdFromPackageFamilyName;
    if ( ProductIdFromPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)ProductIdFromPackageFamilyName,
        v157);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v183);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v187);
      return v14;
    }
    v175 = 0;
    v174 = 0;
    string = 0;
    v15 = WindowsCreateStringReference(
            L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
            0x47u,
            &hstringHeader,
            &string);
    if ( v15 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
LABEL_251:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
LABEL_252:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v74, v75, v76);
LABEL_253:
      wil::details::in1diag3::_FailFast_GetLastError(
        v146,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v145);
    }
    v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager3>>(
            (__int64)string,
            (__int64 *)&v175);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v18,
        v157);
      v20 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
      }
      v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
      }
LABEL_193:
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v183);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v187);
      return v19;
    }
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    v23 = **v175;
    v24 = v174;
    if ( v174 )
    {
      v174 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v24 + 16LL))(v24, *v24);
    }
    v25 = v23(v22, &GUID_c9e7d408_f27a_4471_b2f4_e76efcbebcca, &v174);
    v19 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v25,
        v157);
      v26 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      }
      v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
      }
      goto LABEL_193;
    }
    v176 = 0;
    v177 = 0;
    string = 0;
    v28 = WindowsCreateStringReference(
            L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallOptions",
            0x47u,
            &hstringHeader,
            &string);
    if ( v28 < 0 )
      goto LABEL_251;
    v31 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions>>(
            (__int64)string,
            (__int64 *)&v176);
    v19 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v31,
        v157);
      v32 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
      }
      v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
      }
      v34 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
      }
      v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v35)[2])(v35);
      }
      goto LABEL_193;
    }
    v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
    v37 = **v176;
    v38 = v177;
    if ( v177 )
    {
      v177 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v38 + 16LL))(v38, *v38);
    }
    v39 = v37(v36, &GUID_8a04c0d7_c94b_425e_95b4_bf27faeaee89, &v177);
    v19 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v39,
        v157);
      v40 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
      }
      v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v41)[2])(v41);
      }
      v42 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
      }
      v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v43)[2])(v43);
      }
      goto LABEL_193;
    }
    v44 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **), _QWORD))(*v176)[7])(v176, 0);
    v19 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v44,
        v157);
      v46 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
      }
      v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v47)[2])(v47);
      }
      v48 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
      }
      v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v49)[2])(v49);
      }
      goto LABEL_193;
    }
    LOBYTE(v45) = 1;
    v50 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **), __int64))(*v176)[9])(v176, v45);
    v19 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v50,
        v157);
      v51 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
      }
      v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v52)[2])(v52);
      }
      v53 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v53 + 16LL))(v53);
      }
      v54 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v54)[2])(v54);
      }
      goto LABEL_193;
    }
    v55 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **), _QWORD))(*v176)[15])(v176, 0);
    v19 = v55;
    if ( v55 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v55,
        v157);
      v56 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
      }
      v57 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v57)[2])(v57);
      }
      v58 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
      }
      v59 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v59)[2])(v59);
      }
      goto LABEL_193;
    }
    v60 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v177 + 104LL))(v177, 3);
    v19 = v60;
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v60,
        v157);
      v61 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v61 + 16LL))(v61);
      }
      v62 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v62)[2])(v62);
      }
      v63 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
      }
      v64 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v64)[2])(v64);
      }
      goto LABEL_193;
    }
    v65 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v177 + 120LL))(v177, 3);
    v19 = v65;
    if ( v65 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v65,
        v157);
      v67 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v67 + 16LL))(v67);
      }
      v68 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v68)[2])(v68);
      }
      v69 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v69 + 16LL))(v69);
      }
      v70 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v70)[2])(v70);
      }
      goto LABEL_193;
    }
    v178 = 0;
    v71 = v174;
    v72 = *v174;
    if ( Reserved1 )
    {
      v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v172, &v173, v66);
      v6 |= 1u;
      v159 = v6;
      Reserved1 = v73[1].Reserved.Reserved1;
    }
    string = 0;
    v74 = WindowsCreateStringReference(L"Language Overlay Service", 0x18u, &hstringHeader, &string);
    if ( v74 < 0 )
      goto LABEL_252;
    v77 = string;
    v78 = (const WCHAR *)&v183;
    if ( v184.m128i_i64[1] > 7uLL )
      v78 = (const WCHAR *)v183;
    v158 = v78;
    v79 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v171, &v158, v76);
    v157 = (int)Reserved1;
    v80 = (*(__int64 (__fastcall **)(_QWORD *, PVOID, _QWORD, HSTRING))(v72 + 80))(
            v71,
            v79[1].Reserved.Reserved1,
            0,
            v77);
    v19 = v80;
    if ( (v6 & 1) != 0 )
    {
      v6 &= ~1u;
      v159 = v6;
    }
    if ( v80 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v80,
        (int)Reserved1);
      v82 = v178;
      if ( v178 )
      {
        v178 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v82)[2])(v82);
      }
      v83 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v83 + 16LL))(v83);
      }
      v84 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v84)[2])(v84);
      }
      v85 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v85 + 16LL))(v85);
      }
      v86 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v86)[2])(v86);
      }
      goto LABEL_193;
    }
    wil::WaitForCompletion<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>>>(
      &v179,
      v178,
      v81);
    v185 = 0;
    v87 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v179 + 56LL))(v179, &v185);
    v19 = v87;
    if ( v87 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v87,
        (int)Reserved1);
      v88 = v179;
      if ( v179 )
      {
        v179 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      v89 = v178;
      if ( v178 )
      {
        v178 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v89)[2])(v89);
      }
      v90 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v90 + 16LL))(v90);
      }
      v91 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v91)[2])(v91);
      }
      v92 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v92 + 16LL))(v92);
      }
      v93 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v93)[2])(v93);
      }
      goto LABEL_193;
    }
    if ( !v185 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)0x80004005LL,
        (int)Reserved1);
      v94 = v179;
      if ( v179 )
      {
        v179 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      }
      v95 = v178;
      if ( v178 )
      {
        v178 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v95)[2])(v95);
      }
      v96 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v96 + 16LL))(v96);
      }
      v97 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v97)[2])(v97);
      }
      v98 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v98 + 16LL))(v98);
      }
      v99 = v175;
      if ( v175 )
      {
        v175 = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v99 + 16LL))(v99, *v99);
      }
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v183);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v187);
      return 2147500037LL;
    }
    v180 = 0;
    v100 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v179 + 48LL))(v179, 0, &v180);
    v19 = v100;
    if ( v100 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v100,
        (int)Reserved1);
      v101 = v180;
      if ( v180 )
      {
        v180 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
      }
      v102 = v179;
      if ( v179 )
      {
        v179 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
      }
      v103 = v178;
      if ( v178 )
      {
        v178 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v103)[2])(v103);
      }
      v104 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v104 + 16LL))(v104);
      }
      v105 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v105)[2])(v105);
      }
      v106 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v106 + 16LL))(v106);
      }
      v107 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v107)[2])(v107);
      }
      goto LABEL_193;
    }
    v181 = 0;
    v108 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v180 + 80LL))(v180, &v181);
    v19 = v108;
    if ( v108 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v108,
        (int)Reserved1);
      v109 = v181;
      if ( v181 )
      {
        v181 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      }
      v110 = v180;
      if ( v180 )
      {
        v180 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
      }
      v111 = v179;
      if ( v179 )
      {
        v179 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      }
      v112 = v178;
      if ( v178 )
      {
        v178 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v112)[2])(v112);
      }
      v113 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v113 + 16LL))(v113);
      }
      v114 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v114)[2])(v114);
      }
      v115 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v115 + 16LL))(v115);
      }
      v116 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v116)[2])(v116);
      }
      goto LABEL_193;
    }
    v186 = 0;
    v117 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v181 + 48LL))(v181, &v186);
    v19 = v117;
    if ( v117 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v117,
        (int)Reserved1);
      v119 = v181;
      if ( v181 )
      {
        v181 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
      }
      v120 = v180;
      if ( v180 )
      {
        v180 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
      }
      v121 = v179;
      if ( v179 )
      {
        v179 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
      }
      v122 = v178;
      if ( v178 )
      {
        v178 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v122)[2])(v122);
      }
      v123 = v177;
      if ( v177 )
      {
        v177 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v123 + 16LL))(v123);
      }
      v124 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
      if ( v176 )
      {
        v176 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v124)[2])(v124);
      }
      v125 = v174;
      if ( v174 )
      {
        v174 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v125 + 16LL))(v125);
      }
      v126 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      if ( v175 )
      {
        v175 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v126)[2])(v126);
      }
      goto LABEL_193;
    }
    if ( !v186 )
    {
      v127 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
      v128 = (*v175)[13];
      v129 = (const WCHAR *)&v183;
      if ( v184.m128i_i64[1] > 7uLL )
        v129 = (const WCHAR *)v183;
      v158 = v129;
      v130 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v171, &v158, v118);
      v128(v127, (GUID *)v130[1].Reserved.Reserved1, 0);
    }
    Microsoft::WRL::Details::Make<AdvancedProgressHandler<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>,>(&v182);
    v131 = v182 + 16;
    v132 = v163 & -(__int64)(*(_QWORD *)(v163 + 56) != 0);
    if ( _Mtx_lock((_Mtx_t)(v182 + 16)) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *(_DWORD *)(v131 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v131 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    while ( *(_DWORD *)(v131 + 160) )
      _Cnd_wait((_Cnd_t)(v131 + 88), (_Mtx_t)v131);
    *(_QWORD *)(v131 + 80) = v132;
    _Mtx_unlock((_Mtx_t)v131);
    v167 = v131;
    v188 = 0;
    v133 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v180 + 128LL))(v180, v182, &v188);
    v134 = v133;
    if ( v133 < 0 )
      break;
    v168 = &v180;
    v169 = &v188;
    v170 = 1;
    LODWORD(v158) = 1;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &hObject,
      (int *)&v158);
    AdvancedProgressHandler<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::WaitForCompletion(
      v182,
      hObject);
    if ( hObject )
    {
      v144 = CloseHandle(hObject);
      v146 = retaddr;
      if ( !v144 )
        goto LABEL_253;
    }
    v147 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v180 + 136LL))(v180, v188);
    if ( v147 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v147,
        (int)Reserved1);
    ProgressCallBackHolder<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::_ReleaseCallBack((_Mtx_t)v131);
    v148 = v182;
    if ( v182 )
    {
      v182 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(v148);
    }
    v149 = v181;
    if ( v181 )
    {
      v181 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v149 + 16LL))(v149);
    }
    v150 = v180;
    if ( v180 )
    {
      v180 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v150 + 16LL))(v150);
    }
    v151 = v179;
    if ( v179 )
    {
      v179 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v151 + 16LL))(v151);
    }
    v152 = v178;
    if ( v178 )
    {
      v178 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v152)[2])(v152);
    }
    v153 = v177;
    if ( v177 )
    {
      v177 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v153 + 16LL))(v153);
    }
    v154 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
    if ( v176 )
    {
      v176 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v154)[2])(v154);
    }
    v155 = v174;
    if ( v174 )
    {
      v174 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v155 + 16LL))(v155);
    }
    v156 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
    if ( v175 )
    {
      v175 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v156)[2])(v156);
    }
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v183);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v187);
    v7 += 40;
    Reserved1 = (void *)v164;
    v5 = v165;
    v8 = v166;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x176,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
    (const char *)(unsigned int)v133,
    (int)Reserved1);
  if ( v131 )
    ProgressCallBackHolder<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::_ReleaseCallBack((_Mtx_t)v131);
  v135 = v182;
  if ( v182 )
  {
    v182 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(v135);
  }
  v136 = v181;
  if ( v181 )
  {
    v181 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
  }
  v137 = v180;
  if ( v180 )
  {
    v180 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
  }
  v138 = v179;
  if ( v179 )
  {
    v179 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 16LL))(v138);
  }
  v139 = v178;
  if ( v178 )
  {
    v178 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v139)[2])(v139);
  }
  v140 = v177;
  if ( v177 )
  {
    v177 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v140 + 16LL))(v140);
  }
  v141 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v176;
  if ( v176 )
  {
    v176 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v141)[2])(v141);
  }
  v142 = v174;
  if ( v174 )
  {
    v174 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v142 + 16LL))(v142);
  }
  v143 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v175;
  if ( v175 )
  {
    v175 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v143)[2])(v143);
  }
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)&v183);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)v187);
  return v134;
}

```

## disassembly

```asm
0x180050f50  mov     r11, rsp
0x180050f53  push    rbx
0x180050f54  push    rsi
0x180050f55  push    rdi
0x180050f56  push    r12
0x180050f58  push    r13
0x180050f5a  push    r14
0x180050f5c  push    r15
0x180050f5e  sub     rsp, 1B0h
0x180050f65  movaps  xmmword ptr [r11-48h], xmm6
0x180050f6a  mov     rax, cs:__security_cookie
0x180050f71  xor     rax, rsp
0x180050f74  mov     [rsp+1E8h+var_50], rax
0x180050f7c  mov     [rsp+1E8h+var_170], r9
0x180050f81  mov     rsi, r8
0x180050f84  mov     [r11-168h], r8
0x180050f8b  mov     rdi, rcx
0x180050f8e  mov     [rsp+1E8h+var_160], rcx
0x180050f96  mov     [r11-0F0h], r8
0x180050f9d  xor     r12d, r12d
0x180050fa0  mov     r14d, r12d
0x180050fa3  mov     [rsp+1E8h+var_1A0], r12d
0x180050fa8  mov     r13, [rdx]
0x180050fab  mov     rax, [rdx+8]
0x180050faf  mov     [rsp+1E8h+var_158], rax
0x180050fb7  lea     r15, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180050fbe  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180050fc6  cmp     r13, rax
0x180050fc9  jz      loc_18005264D
0x180050fcf  xorps   xmm0, xmm0
0x180050fd2  movups  [rsp+1E8h+var_78], xmm0
0x180050fda  movdqu  [rsp+1E8h+var_68], xmm6
0x180050fe3  mov     word ptr [rsp+1E8h+var_78], r12w
0x180050fec  lea     r8, [rsp+1E8h+var_78]
0x180050ff4  mov     rdx, r13
0x180050ff7  mov     rcx, rdi
0x180050ffa  call    ?_GetPackageFamilyName@AdvancedLanguageFeaturesProvider@@AEAAJAEBULanguageFeature@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AdvancedLanguageFeaturesProvider::_GetPackageFamilyName(LanguageFeature const &,std::wstring *)
0x180050fff  mov     ebx, eax
0x180051001  test    eax, eax
0x180051003  jns     short loc_180051032
0x180051005  mov     rcx, [rsp+1E8h]; this
0x18005100d  mov     r9d, eax; char *
0x180051010  mov     r8, r15; unsigned int
0x180051013  mov     edx, 137h; void *
0x180051018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005101d  nop
0x18005101e  lea     rcx, [rsp+1E8h+var_78]; void *
0x180051026  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005102b  mov     eax, ebx
0x18005102d  jmp     loc_180052655
0x180051032  xorps   xmm0, xmm0
0x180051035  movups  [rsp+1E8h+var_A0], xmm0
0x18005103d  movdqu  [rsp+1E8h+var_90], xmm6
0x180051046  mov     word ptr [rsp+1E8h+var_A0], r12w
0x18005104f  lea     r8, [rsp+1E8h+var_A0]
0x180051057  lea     rdx, [rsp+1E8h+var_78]
0x18005105f  mov     rcx, rdi
0x180051062  call    ?_GetProductIdFromPackageFamilyName@AdvancedLanguageFeaturesProvider@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV23@@Z; AdvancedLanguageFeaturesProvider::_GetProductIdFromPackageFamilyName(std::wstring const &,std::wstring *)
0x180051067  mov     ebx, eax
0x180051069  test    eax, eax
0x18005106b  jns     short loc_1800510A8
0x18005106d  mov     rcx, [rsp+1E8h]; this
0x180051075  mov     r9d, eax; char *
0x180051078  mov     r8, r15; unsigned int
0x18005107b  mov     edx, 13Ah; void *
0x180051080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051085  nop
0x180051086  lea     rcx, [rsp+1E8h+var_A0]; void *
0x18005108e  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051093  nop
0x180051094  lea     rcx, [rsp+1E8h+var_78]; void *
0x18005109c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800510a1  mov     eax, ebx
0x1800510a3  jmp     loc_180052655
0x1800510a8  mov     [rsp+1E8h+var_E0], r12
0x1800510b0  mov     [rsp+1E8h+var_E8], r12
0x1800510b8  mov     [rsp+1E8h+string], r12
0x1800510bd  lea     r9, [rsp+1E8h+string]; string
0x1800510c2  lea     r8, [rsp+1E8h+hstringHeader]; hstringHeader
0x1800510c7  mov     edx, 47h ; 'G'; length
0x1800510cc  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x1800510d3  call    cs:__imp_WindowsCreateStringReference
0x1800510d9  test    eax, eax
0x1800510db  js      loc_180052680
0x1800510e1  lea     rdx, [rsp+1E8h+var_E0]
0x1800510e9  mov     rcx, [rsp+1E8h+string]
0x1800510ee  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager3@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager3@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager3>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager3>>)
0x1800510f3  mov     ebx, eax
0x1800510f5  test    eax, eax
0x1800510f7  jns     short loc_180051178
0x1800510f9  mov     rcx, [rsp+1E8h]; this
0x180051101  mov     r9d, eax; char *
0x180051104  mov     r8, r15; unsigned int
0x180051107  mov     edx, 140h; void *
0x18005110c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051111  nop
0x180051112  mov     rcx, [rsp+1E8h+var_E8]
0x18005111a  test    rcx, rcx
0x18005111d  jz      short loc_180051134
0x18005111f  mov     [rsp+1E8h+var_E8], r12
0x180051127  mov     rax, [rcx]
0x18005112a  mov     rax, [rax+10h]
0x18005112e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051133  nop
0x180051134  mov     rcx, [rsp+1E8h+var_E0]
0x18005113c  test    rcx, rcx
0x18005113f  jz      short loc_180051156
0x180051141  mov     [rsp+1E8h+var_E0], r12
0x180051149  mov     rax, [rcx]
0x18005114c  mov     rax, [rax+10h]
0x180051150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051155  nop
0x180051156  lea     rcx, [rsp+1E8h+var_A0]; void *
0x18005115e  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051163  nop
0x180051164  lea     rcx, [rsp+1E8h+var_78]; void *
0x18005116c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051171  mov     eax, ebx
0x180051173  jmp     loc_180052655
0x180051178  mov     rbx, [rsp+1E8h+var_E0]
0x180051180  mov     rax, [rbx]
0x180051183  mov     rdi, [rax]
0x180051186  mov     rcx, [rsp+1E8h+var_E8]
0x18005118e  test    rcx, rcx
0x180051191  jz      short loc_1800511A8
0x180051193  mov     [rsp+1E8h+var_E8], r12
0x18005119b  mov     rdx, [rcx]
0x18005119e  mov     rax, [rdx+10h]
0x1800511a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511a7  nop
0x1800511a8  lea     r8, [rsp+1E8h+var_E8]
0x1800511b0  lea     rdx, _GUID_c9e7d408_f27a_4471_b2f4_e76efcbebcca
0x1800511b7  mov     rcx, rbx
0x1800511ba  mov     rax, rdi
0x1800511bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511c2  mov     ebx, eax
0x1800511c4  test    eax, eax
0x1800511c6  jns     short loc_180051247
0x1800511c8  mov     rcx, [rsp+1E8h]; this
0x1800511d0  mov     r9d, eax; char *
0x1800511d3  mov     r8, r15; unsigned int
0x1800511d6  mov     edx, 141h; void *
0x1800511db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800511e0  nop
0x1800511e1  mov     rcx, [rsp+1E8h+var_E8]
0x1800511e9  test    rcx, rcx
0x1800511ec  jz      short loc_180051203
0x1800511ee  mov     [rsp+1E8h+var_E8], r12
0x1800511f6  mov     rax, [rcx]
0x1800511f9  mov     rax, [rax+10h]
0x1800511fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051202  nop
0x180051203  mov     rcx, [rsp+1E8h+var_E0]
0x18005120b  test    rcx, rcx
0x18005120e  jz      short loc_180051225
0x180051210  mov     [rsp+1E8h+var_E0], r12
0x180051218  mov     rax, [rcx]
0x18005121b  mov     rax, [rax+10h]
0x18005121f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051224  nop
0x180051225  lea     rcx, [rsp+1E8h+var_A0]; void *
0x18005122d  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051232  nop
0x180051233  lea     rcx, [rsp+1E8h+var_78]; void *
0x18005123b  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051240  mov     eax, ebx
0x180051242  jmp     loc_180052655
0x180051247  mov     [rsp+1E8h+var_D8], r12
0x18005124f  mov     [rsp+1E8h+var_D0], r12
0x180051257  mov     [rsp+1E8h+string], r12
0x18005125c  lea     r9, [rsp+1E8h+string]; string
0x180051261  lea     r8, [rsp+1E8h+hstringHeader]; hstringHeader
0x180051266  mov     edx, 47h ; 'G'; length
0x18005126b  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallOptions@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180051272  call    cs:__imp_WindowsCreateStringReference
0x180051278  test    eax, eax
0x18005127a  js      loc_180052688
0x180051280  lea     rdx, [rsp+1E8h+var_D8]
0x180051288  mov     rcx, [rsp+1E8h+string]
0x18005128d  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions>>)
0x180051292  mov     ebx, eax
0x180051294  test    eax, eax
0x180051296  jns     loc_18005135F
0x18005129c  mov     rcx, [rsp+1E8h]; this
0x1800512a4  mov     r9d, eax; char *
0x1800512a7  mov     r8, r15; unsigned int
0x1800512aa  mov     edx, 147h; void *
0x1800512af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800512b4  nop
0x1800512b5  mov     rcx, [rsp+1E8h+var_D0]
0x1800512bd  test    rcx, rcx
0x1800512c0  jz      short loc_1800512D7
0x1800512c2  mov     [rsp+1E8h+var_D0], r12
0x1800512ca  mov     rax, [rcx]
0x1800512cd  mov     rax, [rax+10h]
0x1800512d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512d6  nop
0x1800512d7  mov     rcx, [rsp+1E8h+var_D8]
0x1800512df  test    rcx, rcx
0x1800512e2  jz      short loc_1800512F9
0x1800512e4  mov     [rsp+1E8h+var_D8], r12
0x1800512ec  mov     rax, [rcx]
0x1800512ef  mov     rax, [rax+10h]
0x1800512f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512f8  nop
0x1800512f9  mov     rcx, [rsp+1E8h+var_E8]
0x180051301  test    rcx, rcx
0x180051304  jz      short loc_18005131B
0x180051306  mov     [rsp+1E8h+var_E8], r12
0x18005130e  mov     rax, [rcx]
0x180051311  mov     rax, [rax+10h]
0x180051315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005131a  nop
0x18005131b  mov     rcx, [rsp+1E8h+var_E0]
0x180051323  test    rcx, rcx
0x180051326  jz      short loc_18005133D
0x180051328  mov     [rsp+1E8h+var_E0], r12
0x180051330  mov     rax, [rcx]
0x180051333  mov     rax, [rax+10h]
0x180051337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005133c  nop
0x18005133d  lea     rcx, [rsp+1E8h+var_A0]; void *
0x180051345  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005134a  nop
0x18005134b  lea     rcx, [rsp+1E8h+var_78]; void *
0x180051353  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051358  mov     eax, ebx
0x18005135a  jmp     loc_180052655
0x18005135f  mov     rbx, [rsp+1E8h+var_D8]
0x180051367  mov     rax, [rbx]
0x18005136a  mov     rdi, [rax]
0x18005136d  mov     rcx, [rsp+1E8h+var_D0]
0x180051375  test    rcx, rcx
0x180051378  jz      short loc_18005138F
0x18005137a  mov     [rsp+1E8h+var_D0], r12
0x180051382  mov     rdx, [rcx]
0x180051385  mov     rax, [rdx+10h]
0x180051389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005138e  nop
0x18005138f  lea     r8, [rsp+1E8h+var_D0]
0x180051397  lea     rdx, _GUID_8a04c0d7_c94b_425e_95b4_bf27faeaee89
0x18005139e  mov     rcx, rbx
0x1800513a1  mov     rax, rdi
0x1800513a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513a9  mov     ebx, eax
0x1800513ab  test    eax, eax
0x1800513ad  jns     loc_180051476
0x1800513b3  mov     rcx, [rsp+1E8h]; this
0x1800513bb  mov     r9d, eax; char *
0x1800513be  mov     r8, r15; unsigned int
0x1800513c1  mov     edx, 148h; void *
0x1800513c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800513cb  nop
0x1800513cc  mov     rcx, [rsp+1E8h+var_D0]
0x1800513d4  test    rcx, rcx
0x1800513d7  jz      short loc_1800513EE
0x1800513d9  mov     [rsp+1E8h+var_D0], r12
0x1800513e1  mov     rax, [rcx]
0x1800513e4  mov     rax, [rax+10h]
0x1800513e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513ed  nop
0x1800513ee  mov     rcx, [rsp+1E8h+var_D8]
0x1800513f6  test    rcx, rcx
0x1800513f9  jz      short loc_180051410
0x1800513fb  mov     [rsp+1E8h+var_D8], r12
0x180051403  mov     rax, [rcx]
0x180051406  mov     rax, [rax+10h]
0x18005140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005140f  nop
0x180051410  mov     rcx, [rsp+1E8h+var_E8]
0x180051418  test    rcx, rcx
0x18005141b  jz      short loc_180051432
0x18005141d  mov     [rsp+1E8h+var_E8], r12
0x180051425  mov     rax, [rcx]
0x180051428  mov     rax, [rax+10h]
0x18005142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051431  nop
0x180051432  mov     rcx, [rsp+1E8h+var_E0]
0x18005143a  test    rcx, rcx
0x18005143d  jz      short loc_180051454
0x18005143f  mov     [rsp+1E8h+var_E0], r12
0x180051447  mov     rax, [rcx]
0x18005144a  mov     rax, [rax+10h]
0x18005144e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051453  nop
0x180051454  lea     rcx, [rsp+1E8h+var_A0]; void *
0x18005145c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180051461  nop
0x180051462  lea     rcx, [rsp+1E8h+var_78]; void *
0x18005146a  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005146f  mov     eax, ebx
0x180051471  jmp     loc_180052655
0x180051476  mov     rcx, [rsp+1E8h+var_D8]
0x18005147e  mov     rax, [rcx]
0x180051481  xor     edx, edx
0x180051483  mov     rax, [rax+38h]
0x180051487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005148c  mov     ebx, eax
0x18005148e  test    eax, eax
0x180051490  jns     loc_180051559
  ... truncated ...
```
