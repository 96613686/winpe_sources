# InstallQueue2::CreateWorkForCatalogItem(std::shared_ptr<CatalogDataStore::CatalogItem>,CorrelationVector &,CallerContext2 const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)

- ea: `0x18015ed00`
- end: `0x1801621d1`
- name: `?CreateWorkForCatalogItem@InstallQueue2@@QEAA?AV?$vector@UInstallItem@Internal@WindowsUpdate@winrt@@V?$allocator@UInstallItem@Internal@WindowsUpdate@winrt@@@std@@@std@@V?$shared_ptr@UCatalogItem@CatalogDataStore@@@3@AEAVCorrelationVector@@AEBUCallerContext2@@AEBUhstring@winrt@@333@Z`
- size: `13521`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `102`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18015e8a0`

## callees

- `0x180009ea0`
- `0x18000ad3c`
- `0x1800111c8`
- `0x18001bf24`
- `0x18001c964`
- `0x180020868`
- `0x1800208e4`
- `0x180022298`
- `0x18002d98c`
- `0x180036618`
- `0x180036bd8`
- `0x180036e24`
- `0x180036e6c`
- `0x180037200`
- `0x1800377c0`
- `0x180037acc`
- `0x18003b848`
- `0x18003dfd4`
- `0x18003f848`
- `0x180044b84`
- `0x180044c3c`
- `0x180044e5c`
- `0x180045338`
- `0x1800453a0`
- `0x180045588`
- `0x18004579c`
- `0x180067ca8`
- `0x18006c330`
- `0x18006cc00`
- `0x18009588c`
- `0x180095b2c`
- `0x180095b68`
- `0x180097cbc`
- `0x180099350`
- `0x18009937c`
- `0x1800a6ffc`
- `0x1800a74fc`
- `0x1800b1e24`
- `0x1800b356c`
- `0x1800b7b08`
- `0x1800c18bc`
- `0x1800c5470`
- `0x1800ced70`
- `0x1800d326c`
- `0x1801020b4`
- `0x180138ec8`
- `0x18013a480`
- `0x180146dcc`
- `0x18014716c`
- `0x180149adc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180160cd9`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs_s` at `0x180160cd9`
- `msvcp_win!_Xtime_get_ticks` at `0x180161734`
- `msvcp_win!_Xtime_get_ticks` at `0x1801618a9`
- `msvcp_win!_Xtime_get_ticks` at `0x180161734`
- `msvcp_win!_Xtime_get_ticks` at `0x1801618a9`

## string_xrefs

- `0x1801609eb`: `IsInstallServicePlugin`
- `0x18015fa77`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180160b47`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801611ea`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180161438`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180161f0d`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180161ffe`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x1801620fb`: `onecoreuap\enduser\winstore\installservice\libqueue2\installqueue2.cpp`
- `0x180160754`: `UACOpen`
- `0x180160897`: `UACOpen`
- `0x18015fa62`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x180160b32`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x1801611d5`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x180161423`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x180161ef8`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x180161fe9`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x1801620e6`: `InstallQueue2::CreateWorkForCatalogItem`
- `0x180161ee4`: `Not able to create install service work due to product unfulfillable`
- `0x180160b17`: `Plugin not available, Creating chained Work for Catalog Item`
- `0x180160186`: `Microsoft.GamingServices_8wekyb3d8bbwe`
- `0x18016051e`: `Microsoft.GamingServices_8wekyb3d8bbwe`
- `0x18015fa47`: `Plugin available, Creating Work for Catalog Item`
- `0x1801611ba`: `Creating Child Item through plugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=152 #try_helpers=1
_QWORD *__fastcall InstallQueue2::CreateWorkForCatalogItem(
        InstallQueue2 *a1,
        _QWORD *a2,
        _QWORD *a3,
        CorrelationVector *a4,
        struct winrt::hstring *a5,
        struct winrt::hstring *a6,
        struct winrt::hstring *a7,
        _QWORD *a8,
        __int64 a9)
{
  CorrelationVector *v9; // r14
  _QWORD *v10; // r13
  struct winrt::hstring *v11; // rsi
  int v12; // r12d
  int v13; // eax
  const struct winrt::hstring *v14; // rdx
  char v15; // bl
  __int64 StringValue; // rbx
  char v17; // bl
  __int64 v18; // rbx
  char *v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rdx
  char v22; // bl
  __int64 v23; // rbx
  char v24; // bl
  __int64 v25; // rbx
  char *v26; // rax
  __int64 v27; // rdx
  const struct winrt::hstring *v28; // rdx
  char v29; // bl
  __int64 v30; // rbx
  char v31; // bl
  __int64 v32; // rbx
  char *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rdi
  const struct winrt::hstring *v38; // r8
  bool IsPluginAvailable; // al
  char v40; // di
  int v41; // r8d
  __int64 v42; // r9
  int v43; // eax
  char IsEnabled; // al
  int v45; // eax
  __int64 v46; // rdi
  const struct winrt::hstring *v47; // r8
  bool v48; // al
  char v49; // di
  CorrelationVector *v50; // r14
  struct CorrelationVector *v51; // rax
  char v52; // al
  const unsigned __int16 *v53; // r14
  __int64 v54; // r8
  const unsigned __int16 *v55; // rsi
  __int64 v56; // r8
  const unsigned __int16 *v57; // rdi
  const struct winrt::hstring *v58; // rdx
  const unsigned __int16 *v59; // rax
  const unsigned __int16 *v60; // r8
  bool v61; // r14
  __int64 v62; // rdi
  struct winrt::hstring *v63; // rax
  __int64 Singleton; // rax
  unsigned int v65; // eax
  _BYTE *v66; // r14
  const struct winrt::hstring *v67; // r8
  bool v68; // al
  char v69; // r14
  int v70; // eax
  __int64 v71; // r8
  __int64 *JointWorkPropertiesJSON; // rax
  __int64 v73; // rdx
  __int64 v74; // rdi
  __int64 v75; // r10
  __int64 v76; // r10
  WindowsUpdate::CommonTelemetry *v77; // rax
  const unsigned __int16 *v78; // rdx
  const unsigned __int16 *v79; // r8
  const unsigned __int16 *v80; // r9
  __int64 v81; // r10
  __int64 v82; // r10
  WindowsUpdate::CommonTelemetry *v83; // rax
  const unsigned __int16 *v84; // rdx
  const unsigned __int16 *v85; // r8
  const unsigned __int16 *v86; // r9
  __int64 v87; // rdi
  unsigned int v88; // eax
  __int64 BooleanValue; // rdi
  __int64 v90; // rdi
  __int64 v91; // rdx
  int v92; // edi
  struct CorrelationVector *v93; // rax
  _BYTE *v94; // rdi
  _BYTE *v95; // rsi
  std::_Ref_count_base *v96; // rsi
  const struct winrt::hstring *v97; // rdi
  int v98; // eax
  const struct winrt::hstring *v99; // rdi
  unsigned __int16 *v100; // rax
  __int64 v101; // rax
  unsigned int v102; // eax
  int v103; // eax
  __int64 v104; // r8
  __int64 v105; // rdx
  _BYTE *v106; // r14
  const struct winrt::hstring *v107; // r8
  int v108; // eax
  const struct winrt::hstring *v109; // r14
  __int64 v110; // r14
  _QWORD *v111; // rbx
  InstallQueue2::Data *v112; // rdi
  InstallQueue2::Data *v113; // r12
  char *v114; // r13
  __int128 v115; // xmm6
  __int64 v116; // rcx
  __int64 v117; // rbx
  __int64 v118; // rax
  InstallQueue2 *v119; // rbx
  struct winrt::hstring *v120; // rbx
  __int128 v121; // xmm6
  const struct store_lock *v122; // rdx
  __int64 Value; // rax
  __int64 *ClientAppId; // rax
  __int64 v125; // rbx
  __int64 v126; // rax
  winrt::hstring *v127; // rax
  __int64 v128; // rdx
  __int64 v129; // rdx
  __int64 v130; // rdx
  WindowsUpdate::CommonTelemetry *v131; // rax
  const unsigned __int16 *v132; // r8
  const unsigned __int16 *v133; // r9
  const unsigned __int16 *v134; // r10
  const unsigned __int16 *v135; // r11
  __int64 v136; // rax
  __int64 *v137; // rax
  __int64 v138; // rbx
  __int64 v139; // rax
  winrt::hstring *v140; // rax
  __int64 v141; // rdx
  __int64 v142; // rdx
  __int64 v143; // rdx
  WindowsUpdate::CommonTelemetry *v144; // rax
  const unsigned __int16 *v145; // r8
  const unsigned __int16 *v146; // r9
  const unsigned __int16 *v147; // r10
  const unsigned __int16 *v148; // r11
  std::_Ref_count_base *v149; // rcx
  const struct winrt::hstring *v151; // rdx
  __int64 v152; // rax
  unsigned int *v153; // rax
  __int64 v154; // r8
  unsigned int *v155; // rax
  __int64 v156; // r8
  const struct winrt::impl::slim_source_location *v157; // rax
  unsigned int *v158; // rax
  __int64 v159; // r8
  const struct winrt::impl::slim_source_location *v160; // rax
  struct winrt::hstring *v161; // [rsp+20h] [rbp-6E8h]
  struct winrt::hstring *v162; // [rsp+20h] [rbp-6E8h]
  struct winrt::hstring *v163; // [rsp+20h] [rbp-6E8h]
  int v164; // [rsp+20h] [rbp-6E8h]
  int v165; // [rsp+20h] [rbp-6E8h]
  int v166; // [rsp+20h] [rbp-6E8h]
  struct winrt::hstring *v167; // [rsp+28h] [rbp-6E0h]
  char *v168; // [rsp+30h] [rbp-6D8h]
  char *v169; // [rsp+38h] [rbp-6D0h]
  char *v170; // [rsp+38h] [rbp-6D0h]
  unsigned __int16 *v171; // [rsp+40h] [rbp-6C8h]
  const char *v172; // [rsp+48h] [rbp-6C0h]
  const char *v173; // [rsp+50h] [rbp-6B8h]
  const char *v174; // [rsp+50h] [rbp-6B8h]
  char *v175; // [rsp+70h] [rbp-698h]
  int v176; // [rsp+70h] [rbp-698h]
  struct winrt::hstring *v177; // [rsp+78h] [rbp-690h] BYREF
  unsigned __int16 *v178; // [rsp+80h] [rbp-688h] BYREF
  int v179[2]; // [rsp+88h] [rbp-680h] BYREF
  __int64 v180; // [rsp+90h] [rbp-678h] BYREF
  struct winrt::hstring *v181; // [rsp+98h] [rbp-670h] BYREF
  __int128 v182; // [rsp+A0h] [rbp-668h] BYREF
  _BYTE *v183; // [rsp+B0h] [rbp-658h] BYREF
  std::_Ref_count_base *v184; // [rsp+B8h] [rbp-650h]
  struct winrt::hstring *v185; // [rsp+C0h] [rbp-648h] BYREF
  __int64 v186; // [rsp+C8h] [rbp-640h]
  CorrelationVector *v187; // [rsp+D0h] [rbp-638h]
  __int64 v188; // [rsp+D8h] [rbp-630h] BYREF
  __int64 v189; // [rsp+E0h] [rbp-628h] BYREF
  __int64 v190; // [rsp+E8h] [rbp-620h] BYREF
  bool v191[8]; // [rsp+F0h] [rbp-618h] BYREF
  int v192[2]; // [rsp+F8h] [rbp-610h] BYREF
  char v193[8]; // [rsp+100h] [rbp-608h] BYREF
  InstallQueue2 *v194; // [rsp+108h] [rbp-600h]
  __int64 v195; // [rsp+110h] [rbp-5F8h] BYREF
  std::_Ref_count_base *v196; // [rsp+118h] [rbp-5F0h]
  struct winrt::hstring *v197; // [rsp+120h] [rbp-5E8h]
  _QWORD *v198; // [rsp+128h] [rbp-5E0h]
  char v199[8]; // [rsp+130h] [rbp-5D8h] BYREF
  InstallQueue2 *v200; // [rsp+138h] [rbp-5D0h] BYREF
  _QWORD v201[2]; // [rsp+140h] [rbp-5C8h] BYREF
  std::_Ref_count_base *v202[2]; // [rsp+150h] [rbp-5B8h] BYREF
  int v203[2]; // [rsp+160h] [rbp-5A8h] BYREF
  __int64 v204; // [rsp+168h] [rbp-5A0h] BYREF
  _QWORD *v205; // [rsp+170h] [rbp-598h]
  __int64 v206; // [rsp+178h] [rbp-590h] BYREF
  _QWORD *v207; // [rsp+180h] [rbp-588h]
  _QWORD *v208; // [rsp+188h] [rbp-580h]
  _QWORD *v209; // [rsp+190h] [rbp-578h]
  InstallQueue2::Data *v210[2]; // [rsp+198h] [rbp-570h] BYREF
  __int64 v211; // [rsp+1A8h] [rbp-560h]
  char v212[8]; // [rsp+1B0h] [rbp-558h] BYREF
  char v213[8]; // [rsp+1B8h] [rbp-550h] BYREF
  char v214[8]; // [rsp+1C0h] [rbp-548h] BYREF
  char v215[8]; // [rsp+1C8h] [rbp-540h] BYREF
  char v216[8]; // [rsp+1D0h] [rbp-538h] BYREF
  char v217[8]; // [rsp+1D8h] [rbp-530h] BYREF
  struct winrt::hstring *v218; // [rsp+1E0h] [rbp-528h] BYREF
  __int128 v219; // [rsp+1E8h] [rbp-520h] BYREF
  __int64 v220; // [rsp+1F8h] [rbp-510h]
  InstallQueue2 *v221; // [rsp+200h] [rbp-508h]
  char v222[8]; // [rsp+208h] [rbp-500h] BYREF
  char v223[8]; // [rsp+210h] [rbp-4F8h] BYREF
  char v224[8]; // [rsp+218h] [rbp-4F0h] BYREF
  char v225[8]; // [rsp+220h] [rbp-4E8h] BYREF
  _QWORD v226[3]; // [rsp+228h] [rbp-4E0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+240h] [rbp-4C8h] BYREF
  _BYTE v228[24]; // [rsp+258h] [rbp-4B0h] BYREF
  _BYTE v229[24]; // [rsp+270h] [rbp-498h] BYREF
  _BYTE v230[24]; // [rsp+288h] [rbp-480h] BYREF
  _BYTE v231[48]; // [rsp+2A0h] [rbp-468h] BYREF
  _BYTE v232[56]; // [rsp+2D0h] [rbp-438h] BYREF
  struct winrt::hstring *v233; // [rsp+308h] [rbp-400h] BYREF
  __int64 v234; // [rsp+310h] [rbp-3F8h] BYREF
  __int64 ticks; // [rsp+318h] [rbp-3F0h] BYREF
  __int64 v236[2]; // [rsp+328h] [rbp-3E0h] BYREF
  __int64 v237[2]; // [rsp+338h] [rbp-3D0h] BYREF
  _QWORD v238[5]; // [rsp+348h] [rbp-3C0h] BYREF
  char v239[16]; // [rsp+370h] [rbp-398h] BYREF
  __int128 v240; // [rsp+380h] [rbp-388h]
  __int128 v241; // [rsp+390h] [rbp-378h]
  __int128 v242; // [rsp+3A0h] [rbp-368h]
  __int128 v243; // [rsp+3B0h] [rbp-358h]
  __int128 v244; // [rsp+3C0h] [rbp-348h]
  __int128 v245; // [rsp+3D0h] [rbp-338h]
  __int128 v246; // [rsp+3E0h] [rbp-328h]
  char v247; // [rsp+3F0h] [rbp-318h]
  __int64 v248; // [rsp+3F8h] [rbp-310h] BYREF
  __int64 v249; // [rsp+400h] [rbp-308h] BYREF
  std::_Ref_count_base *v250; // [rsp+408h] [rbp-300h] BYREF
  char v251[8]; // [rsp+420h] [rbp-2E8h] BYREF
  __int128 v252; // [rsp+428h] [rbp-2E0h] BYREF
  __int64 v253; // [rsp+438h] [rbp-2D0h]
  _BYTE v254[32]; // [rsp+440h] [rbp-2C8h] BYREF
  _BYTE v255[272]; // [rsp+460h] [rbp-2A8h] BYREF
  _BYTE v256[272]; // [rsp+570h] [rbp-198h] BYREF
  struct winrt::hstring *v257; // [rsp+680h] [rbp-88h] BYREF
  char v258[8]; // [rsp+688h] [rbp-80h] BYREF
  __int64 v259; // [rsp+690h] [rbp-78h]
  int v260[2]; // [rsp+698h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+0h]

  v9 = a4;
  v187 = a4;
  v10 = a3;
  v207 = a3;
  v198 = a2;
  v194 = a1;
  v221 = a1;
  v200 = a1;
  v208 = a2;
  v209 = a3;
  v201[0] = a4;
  v204 = (__int64)a4;
  *(_QWORD *)v192 = a4;
  v11 = a5;
  v197 = a5;
  v218 = a7;
  v205 = a8;
  v186 = a9;
  v12 = 0;
  v176 = 0;
  winrt::hstring::hstring((winrt::hstring *)v222, a6);
  winrt::hstring::hstring((winrt::hstring *)v223, a7);
  v238[0] = *a8;
  winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v193);
  LODWORD(v181) = 2
                * PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v193);
  PluginHelpers::WorkProperty::CatalogId::GetValue(v199, v193);
  PluginHelpers::WorkProperty::UserIdentityInfo::GetValue(v217, v193);
  winrt::hstring::hstring((winrt::hstring *)v179, (const unsigned __int16 *)&dword_18023C12C);
  v13 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v182, v10);
  CreateJointWorkPropertiesJSON((unsigned int)&v188, v13, (_DWORD)a8, v186, (__int64)v179);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
  winrt::hstring::hstring((winrt::hstring *)&v189, (const unsigned __int16 *)&dword_18023C12C);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::GetImpl'::`2'::impl) )
  {
    try
    {
      v14 = (const struct winrt::hstring *)(*v10 + 160LL);
      if ( *(_QWORD *)v14 )
      {
        winrt::hstring::hstring((winrt::hstring *)v214, v14);
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v178);
        v238[0] = *(_QWORD *)(*v10 + 160LL);
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v238,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v178) )
        {
          if ( *(_QWORD *)(*v10 + 224LL) && *(_QWORD *)(*v10 + 216LL) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v238, L"PurchasableAvailabilityId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v178,
                                     v238)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v233,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableAvailabilityId"),
                  v12 = 1,
                  v176 = 1,
                  v15 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v178,
                                &v177,
                                v236,
                                &v233)) )
            {
              v15 = 1;
            }
            if ( (v12 & 1) != 0 )
            {
              v12 &= ~1u;
              v176 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
            }
            if ( v15 )
            {
              v238[0] = *(_QWORD *)(*v10 + 224LL);
              StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v177);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v233, L"PurchasableAvailabilityId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v178,
                &v233,
                StringValue);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)v238, L"PurchasableSkuId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v178,
                                     v238)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v233,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableSkuId"),
                  v12 |= 2u,
                  v176 = v12,
                  v17 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v178,
                                &v177,
                                v236,
                                &v233)) )
            {
              v17 = 1;
            }
            if ( (v12 & 2) != 0 )
            {
              v12 &= ~2u;
              v176 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
            }
            if ( v17 )
            {
              v238[0] = *(_QWORD *)(*v10 + 216LL);
              v18 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v177);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v233, L"PurchasableSkuId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v178,
                &v233,
                v18);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
            }
          }
          v19 = (char *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                          &v178,
                          &v177);
          if ( v214 != v19 )
          {
            v20 = *(_QWORD *)v19;
            *(_QWORD *)v19 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v214, v20);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
          winrt::hstring::operator=(*v10 + 160LL, v214);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v178);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v214);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x5A6,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        "Failed to merge purchasableAvailabilityId and purchasableSkuId into fulfillmentData",
        (const char *)v163);
      v12 = v176;
      v198 = v208;
      v194 = v200;
      v10 = v209;
      v207 = v209;
      v9 = (CorrelationVector *)v201[0];
      v187 = (CorrelationVector *)v201[0];
      v11 = v197;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl'::`2'::impl)
    && GetEnableGetEntitlementIfNotPresent() )
  {
    try
    {
      v21 = (_QWORD *)(*v10 + 160LL);
      if ( *v21 )
      {
        winrt::hstring::operator=(&v189, v21);
        winrt::hstring::hstring((winrt::hstring *)v215, (const struct winrt::hstring *)&v189);
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v178);
        v238[0] = v189;
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v238,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v178) )
        {
          if ( *(_QWORD *)(*v10 + 224LL) && *(_QWORD *)(*v10 + 216LL) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v238, L"PurchasableAvailabilityId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v178,
                                     v238)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v233,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableAvailabilityId"),
                  v12 |= 4u,
                  v176 = v12,
                  v22 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v178,
                                &v177,
                                v236,
                                &v233)) )
            {
              v22 = 1;
            }
            if ( (v12 & 4) != 0 )
            {
              v12 &= ~4u;
              v176 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
            }
            if ( v22 )
            {
              v238[0] = *(_QWORD *)(*v10 + 224LL);
              v23 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v177);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v233, L"PurchasableAvailabilityId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v178,
                &v233,
                v23);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)v238, L"PurchasableSkuId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v178,
                                     v238)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v233,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableSkuId"),
                  v12 |= 8u,
                  v176 = v12,
                  v24 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v178,
                                &v177,
                                v236,
                                &v233)) )
            {
              v24 = 1;
            }
            if ( (v12 & 8) != 0 )
            {
              v12 &= ~8u;
              v176 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
            }
            if ( v24 )
            {
              v238[0] = *(_QWORD *)(*v10 + 216LL);
              v25 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v177);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v233, L"PurchasableSkuId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v178,
                &v233,
                v25);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
            }
          }
          v26 = (char *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                          &v178,
                          &v177);
          if ( v215 != v26 )
          {
            v27 = *(_QWORD *)v26;
            *(_QWORD *)v26 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v215, v27);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
          winrt::hstring::operator=(&v189, v215);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v178);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v215);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x5CD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        "Failed to merge purchasableAvailabilityId and purchasableSkuId into mutableFulfillmentData",
        (const char *)v162);
      v12 = v176;
      v198 = v208;
      v194 = v200;
      v10 = v209;
      v207 = v209;
      v9 = (CorrelationVector *)v201[0];
      v187 = (CorrelationVector *)v201[0];
      v11 = v197;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
  {
    if ( v189 )
      v28 = (const struct winrt::hstring *)&v189;
    else
      v28 = (const struct winrt::hstring *)(*v10 + 160LL);
    try
    {
      winrt::hstring::hstring((winrt::hstring *)&v190, v28);
      if ( v190 )
      {
        winrt::hstring::hstring((winrt::hstring *)v216, (const struct winrt::hstring *)&v190);
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v178);
        v238[0] = v190;
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v238,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v178) )
        {
          if ( *(_QWORD *)(*v10 + 272LL) && *(_QWORD *)(*v10 + 200LL) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v238, L"PackageRankId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v178,
                                     v238)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v233,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PackageRankId"),
                  v12 |= 0x10u,
                  v176 = v12,
                  v29 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v178,
                                &v177,
                                v236,
                                &v233)) )
            {
              v29 = 1;
            }
            if ( (v12 & 0x10) != 0 )
            {
              v12 &= ~0x10u;
              v176 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
            }
            if ( v29 && StringCchPrintfW((unsigned __int16 *)&v257, 0x15u, L"%llu", *(_QWORD *)(*v10 + 272LL)) >= 0 )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)v238, (const unsigned __int16 *const)&v257);
              v30 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v177);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v233, L"PackageRankId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v178,
                &v233,
                v30);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)v238, L"PackageFullNameId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v178,
                                     v238)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v233,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PackageFullNameId"),
                  v12 |= 0x20u,
                  v176 = v12,
                  v31 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v178,
                                &v177,
                                v236,
                                &v233)) )
            {
              v31 = 1;
            }
            if ( (v12 & 0x20) != 0 )
            {
              v12 &= ~0x20u;
              v176 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
            }
            if ( v31 )
            {
              v238[0] = *(_QWORD *)(*v10 + 200LL);
              v32 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v177);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v233, L"PackageFullNameId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v178,
                &v233,
                v32);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
            }
          }
          v33 = (char *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                          &v178,
                          &v177);
          if ( v216 != v33 )
          {
            v34 = *(_QWORD *)v33;
            *(_QWORD *)v33 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v216, v34);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
          winrt::hstring::operator=(&v189, v216);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v178);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v216);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v190);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x5F9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        "Failed to merge packageRank and packageFullName into mutableFulfillmentData",
        (const char *)v161);
      v12 = v176;
      v198 = v208;
      v194 = v200;
      v10 = v209;
      v207 = v209;
      v9 = (CorrelationVector *)v201[0];
      v187 = (CorrelationVector *)v201[0];
      v11 = v197;
    }
  }
  *(_OWORD *)v210 = 0;
  v211 = 0;
  *(_OWORD *)v202 = 0;
  v35 = 0;
  v190 = 0;
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(v193, &v206);
  if ( *(int *)(*v10 + 296LL) < 0 && *(_QWORD *)(*v10 + 120LL) == *(_QWORD *)(*v10 + 112LL) )
  {
    v151 = (const struct winrt::hstring *)(winrt::com_ptr<IUniversalOrchestrator>::operator->(v10) + 24);
    winrt::hstring::hstring((winrt::hstring *)&v183, v151);
    v184 = (std::_Ref_count_base *)*(unsigned int *)(winrt::com_ptr<IUniversalOrchestrator>::operator->(v10) + 296);
    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
      &v182,
      L"Not able to create install service work due to product unfulfillable");
    std::string::string(v236, "InstallQueue2::CreateWorkForCatalogItem");
    std::string::string(&v233, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::Log<Logging::ErrorCode>((unsigned int)&v233, 1542, (unsigned int)v236, 1, (__int64)&v182, (__int64)&v183);
    std::string::~string(&v233);
    std::string::~string(v236);
    PluginHelpers::WorkProperty::VolumePath::~VolumePath((PluginHelpers::WorkProperty::VolumePath *)&v183);
    winrt::impl::slim_source_location::current(&v233);
    v152 = winrt::com_ptr<IUniversalOrchestrator>::operator->(v10);
    v153 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v181, *(_DWORD *)(v152 + 296));
    winrt::hresult_error::hresult_error(pExceptionObject, *v153, v154);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  v37 = *v10;
  if ( !*(_BYTE *)(*v10 + 284LL)
    || (CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v179),
        v12 |= 0x40u,
        IsPluginAvailable = PluginHelpers::IsPluginAvailable(
                              (PluginHelpers *)v179,
                              (const struct winrt::hstring *)(v37 + 152),
                              v38),
        v40 = 1,
        !IsPluginAvailable) )
  {
    v40 = 0;
  }
  if ( (v12 & 0x40) != 0 )
  {
    v12 &= ~0x40u;
    winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
  }
  if ( v40 )
  {
    std::make_pair<unsigned short const (&)[11],winrt::hstring &>(v212, v36, &v188);
    v195 = (__int64)L"Plugin available, Creating Work for Catalog Item";
    v196 = (std::_Ref_count_base *)48;
    std::string::string(v254, "InstallQueue2::CreateWorkForCatalogItem");
    std::string::string(&v233, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>(
      (unsigned int)v256,
      (unsigned int)&v233,
      v41,
      (unsigned int)v254,
      v164,
      (__int64)&v195,
      (__int64)v9,
      (__int64)v11,
      (__int64)v222,
      (__int64)v212);
    v12 |= 0x400u;
    std::string::~string(&v233);
    std::string::~string(v254);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl'::`2'::impl) )
    {
      v42 = *v10;
      if ( v189 )
      {
LABEL_88:
        CreateInstallServiceWorkByPlugin(
          (winrt::Windows::Foundation::IUnknown *)v236,
          v9,
          v11,
          (struct winrt::hstring *)(v42 + 152),
          (struct winrt::hstring *)&v189,
          (__int64)&v188);
LABEL_89:
        v257 = (struct winrt::hstring *)v236[0];
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v257);
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v258, v10);
        winrt::hstring::hstring((winrt::hstring *)&v180, L"Acquisition");
        *(_QWORD *)v179 = 0;
        v43 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v182, v10);
        CreateCheckPointData(
          (int)v260,
          v43,
          (int)v9,
          (int)v179,
          v11,
          (__int64)&v236[1],
          (__int64)v237,
          (__int64)&v188,
          v186,
          (__int64)&v180);
        std::vector<InstallQueue2::Data>::push_back(v210, &v257);
        InstallQueue2::Data::~Data((InstallQueue2::Data *)&v257);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v180);
LABEL_94:
        std::tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::~tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>(v236);
        Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v256);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v213);
        goto LABEL_95;
      }
    }
    else
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl);
      v42 = *v10;
      if ( !IsEnabled )
      {
        CreateInstallServiceWorkByPlugin(
          (winrt::Windows::Foundation::IUnknown *)v236,
          v9,
          v11,
          (struct winrt::hstring *)(v42 + 152),
          (struct winrt::hstring *)(v42 + 160),
          (__int64)&v188);
        v257 = (struct winrt::hstring *)v236[0];
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v257);
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v258, v10);
        winrt::hstring::hstring((winrt::hstring *)&v180, L"Acquisition");
        *(_QWORD *)v179 = 0;
        v45 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v182, v10);
        CreateCheckPointData(
          (int)v260,
          v45,
          (int)v9,
          (int)v179,
          v11,
          (__int64)&v236[1],
          (__int64)v237,
          (__int64)&v188,
          v186,
          (__int64)&v180);
        std::vector<InstallQueue2::Data>::push_back(v210, &v257);
        InstallQueue2::Data::~Data((InstallQueue2::Data *)&v257);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v180);
        goto LABEL_94;
      }
      if ( v189 )
        goto LABEL_88;
    }
    CreateInstallServiceWorkByPlugin(
      (winrt::Windows::Foundation::IUnknown *)v236,
      v9,
      v11,
      (struct winrt::hstring *)(v42 + 152),
      (struct winrt::hstring *)(v42 + 160),
      (__int64)&v188);
    goto LABEL_89;
  }
LABEL_95:
  if ( !*(_BYTE *)(*v10 + 284LL)
    || !(unsigned __int8)winrt::operator==(*v10 + 152LL, L"Microsoft.GamingServices_8wekyb3d8bbwe")
    || (v46 = *v10,
        CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v179),
        v12 |= 0x80u,
        v48 = PluginHelpers::IsPluginAvailable((PluginHelpers *)v179, (const struct winrt::hstring *)(v46 + 152), v47),
        v49 = 1,
        v48) )
  {
    v49 = 0;
  }
  if ( (v12 & 0x80u) != 0 )
  {
    v12 &= ~0x80u;
    winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
  }
  if ( v49 )
  {
    std::shared_ptr<CheckpointData::Data>::operator=(v202, v10);
    winrt::hstring::operator=(&v206, &v188);
  }
  else
  {
    v62 = *(_QWORD *)(*v10 + 112LL);
    v63 = *(struct winrt::hstring **)(*v10 + 120LL);
    v177 = v63;
    while ( (struct winrt::hstring *)v62 != v63 )
    {
      Singleton = CatalogDataStore::GetSingleton();
      std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v249, Singleton);
      winrt::hstring::hstring((winrt::hstring *)v179, L"StoreId");
      v65 = (unsigned int)CorrelationVector::Increment(v9);
      CatalogDataStore::LookupForUser(
        v249,
        (unsigned int)&v183,
        v65,
        (_DWORD)v11,
        (__int64)v199,
        (__int64)v217,
        (__int64)v179,
        v62,
        0);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
      if ( !(unsigned __int8)winrt::operator==(v183 + 152, L"Microsoft.GamingServices_8wekyb3d8bbwe")
        || (v66 = v183,
            CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)&v180),
            v12 |= 0x100u,
            v68 = PluginHelpers::IsPluginAvailable(
                    (PluginHelpers *)&v180,
                    (const struct winrt::hstring *)(v66 + 152),
                    v67),
            v69 = 1,
            v68) )
      {
        v69 = 0;
      }
      if ( (v12 & 0x100) != 0 )
      {
        v12 &= ~0x100u;
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v180);
      }
      if ( v69 )
      {
        std::shared_ptr<CheckpointData::Data>::operator=(v202, &v183);
        v70 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v182, v202);
        JointWorkPropertiesJSON = (__int64 *)CreateJointWorkPropertiesJSON(
                                               (unsigned int)&v177,
                                               v70,
                                               (_DWORD)v205,
                                               v186,
                                               v71);
        if ( &v206 != JointWorkPropertiesJSON )
        {
          v73 = *JointWorkPropertiesJSON;
          *JointWorkPropertiesJSON = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v206, v73);
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
        if ( v184 )
          std::_Ref_count_base::_Decref(v184);
        if ( v250 )
          std::_Ref_count_base::_Decref(v250);
        break;
      }
      if ( v184 )
        std::_Ref_count_base::_Decref(v184);
      if ( v250 )
        std::_Ref_count_base::_Decref(v250);
      v62 += 8;
      v63 = v177;
      v9 = v187;
    }
  }
  v50 = v187;
  if ( v202[0] )
  {
    LODWORD(v178) = 0;
    v51 = CorrelationVector::Increment(v187);
    *(_OWORD *)v239 = *(_OWORD *)((char *)v51 + 8);
    v240 = *(_OWORD *)((char *)v51 + 24);
    v241 = *(_OWORD *)((char *)v51 + 40);
    v242 = *(_OWORD *)((char *)v51 + 56);
    v243 = *(_OWORD *)((char *)v51 + 72);
    v244 = *(_OWORD *)((char *)v51 + 88);
    v245 = *(_OWORD *)((char *)v51 + 104);
    v246 = *(_OWORD *)((char *)v51 + 120);
    v247 = *((_BYTE *)v51 + 136);
    winrt::hstring::hstring((winrt::hstring *)&v248, (struct CorrelationVector *)((char *)v51 + 144));
    v12 |= 0x800u;
    v35 = winrt::impl::create_and_initialize<ChainedInstallServiceWork,unsigned short const (&)[18],winrt::hstring &,CorrelationVector::Stringified,CallerContext2 const &,enum winrt::Windows::Internal::InstallService::Plugin::InstallServiceWorkPriority &,int>(
            L"PackageFamilyName",
            (__int64)&v181,
            (__int64)&v178);
    v190 = v35;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v248);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UACStateTransitionTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UACStateTransitionTelemetry>::GetImpl'::`2'::impl) )
    {
      v52 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateStateTransitionForUAC>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UpdateStateTransitionForUAC>::GetImpl'::`2'::impl);
      v185 = (struct winrt::hstring *)(*(_QWORD *)v192 + 144LL);
      if ( v52 )
      {
        v53 = winrt::hstring::c_str((std::_Ref_count_base *)((char *)v202[0] + 24));
        v55 = winrt::hstring::c_str((winrt::hstring *)(v54 + 32));
        v57 = winrt::hstring::c_str((winrt::hstring *)(v56 + 152));
        *(_OWORD *)v239 = *(_OWORD *)(v204 + 8);
        v240 = *(_OWORD *)(v204 + 24);
        v241 = *(_OWORD *)(v204 + 40);
        v242 = *(_OWORD *)(v204 + 56);
        v243 = *(_OWORD *)(v204 + 72);
        v244 = *(_OWORD *)(v204 + 88);
        v245 = *(_OWORD *)(v204 + 104);
        v246 = *(_OWORD *)(v204 + 120);
        v247 = *(_BYTE *)(v204 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v248, v58);
        v59 = winrt::hstring::c_str((winrt::hstring *)v199);
        v60 = v55;
        v11 = v197;
        v61 = CallerContext2::CheckElevationRequirement(v197, v53, v60, v59, v57, v239);
      }
      else
      {
        v74 = v204;
        *(_OWORD *)v239 = *(_OWORD *)(v204 + 8);
        v240 = *(_OWORD *)(v204 + 24);
        v241 = *(_OWORD *)(v204 + 40);
        v242 = *(_OWORD *)(v204 + 56);
        v243 = *(_OWORD *)(v204 + 72);
        v244 = *(_OWORD *)(v204 + 88);
        v245 = *(_OWORD *)(v204 + 104);
        v246 = *(_OWORD *)(v204 + 120);
        v247 = *(_BYTE *)(v204 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v248, (const struct winrt::hstring *)(*(_QWORD *)v192 + 144LL));
        winrt::hstring::c_str((std::_Ref_count_base *)((char *)v202[0] + 152));
        winrt::hstring::c_str((winrt::hstring *)v199);
        winrt::hstring::c_str((winrt::hstring *)(v75 + 32));
        v77 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v76 + 24));
        LOBYTE(v169) = 0;
        WindowsUpdate::CommonTelemetry::StateTransition(
          v77,
          v78,
          v79,
          v80,
          0,
          "FulfillmentInitiate",
          "UACOpen",
          v169,
          0,
          (__int64)v239,
          v173);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v248);
        v61 = CallerContext2::CheckElevationRequirement(v11, 0, 0, 0, 0, 0);
        *(_OWORD *)v239 = *(_OWORD *)(v74 + 8);
        v240 = *(_OWORD *)(v74 + 24);
        v241 = *(_OWORD *)(v74 + 40);
        v242 = *(_OWORD *)(v74 + 56);
        v243 = *(_OWORD *)(v74 + 72);
        v244 = *(_OWORD *)(v74 + 88);
        v245 = *(_OWORD *)(v74 + 104);
        v246 = *(_OWORD *)(v74 + 120);
        v247 = *(_BYTE *)(v74 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v248, v185);
        winrt::hstring::c_str((std::_Ref_count_base *)((char *)v202[0] + 152));
        winrt::hstring::c_str((winrt::hstring *)v199);
        winrt::hstring::c_str((winrt::hstring *)(v81 + 32));
        v83 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v82 + 24));
        LOBYTE(v170) = 0;
        WindowsUpdate::CommonTelemetry::StateTransition(
          v83,
          v84,
          v85,
          v86,
          0,
          (const unsigned __int16 *)"UACOpen",
          "UACClose",
          v170,
          !v61 ? 0x13 : 0,
          (__int64)v239,
          v174);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v248);
      if ( !v61 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HResultForElevationDenied>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HResultForElevationDenied>::GetImpl'::`2'::impl) )
        {
          std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
            &v182,
            L"The user declined the UAC prompt");
          std::string::string(v236, "InstallQueue2::CreateWorkForCatalogItem");
          std::string::string(&v233, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::Log<>((unsigned int)&v233, 1668, (unsigned int)v236, 3, (__int64)&v182);
          std::string::~string(&v233);
          std::string::~string(v236);
          winrt::impl::slim_source_location::current(&v233);
          v155 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v181, -2143309549);
          winrt::hresult_error::hresult_error(v228, *v155, v156);
          throw (winrt::hresult_error *)v228;
        }
        v157 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v233);
        winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v229, v157);
        throw (winrt::hresult_access_denied *)v229;
      }
      v50 = v187;
    }
    else if ( !CallerContext2::CheckElevationRequirement(v11, 0, 0, 0, 0, 0) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HResultForElevationDenied>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HResultForElevationDenied>::GetImpl'::`2'::impl) )
      {
        std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
          &v182,
          L"The user declined the UAC prompt");
        std::string::string(v236, "InstallQueue2::CreateWorkForCatalogItem");
        std::string::string(&v233, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<>((unsigned int)&v233, 1684, (unsigned int)v236, 3, (__int64)&v182);
        std::string::~string(&v233);
        std::string::~string(v236);
        winrt::impl::slim_source_location::current(&v233);
        v158 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v181, -2143309549);
        winrt::hresult_error::hresult_error(v230, *v158, v159);
        throw (winrt::hresult_error *)v230;
      }
      v160 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v233);
      winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v231, v160);
      throw (winrt::hresult_access_denied *)v231;
    }
    v87 = *(_QWORD *)CatalogDataStore::GetSingleton();
    winrt::hstring::hstring((winrt::hstring *)&v181, L"PackageFamilyName");
    v88 = (unsigned int)CorrelationVector::Increment(v50);
    CatalogDataStore::LookupForUser(
      v87,
      (unsigned int)&v183,
      v88,
      (_DWORD)v11,
      (__int64)v217,
      (__int64)v199,
      (__int64)&v181,
      (__int64)v202[0] + 152,
      0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v181);
    v183[280] = 1;
    v238[0] = v206;
    winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v179);
    BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&v185);
    v195 = (__int64)L"IsInstallServicePlugin";
    v196 = (std::_Ref_count_base *)22;
    winrt::param::hstring::hstring(&v233, &v195);
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      v179,
      &v233,
      BooleanValue);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v185);
    v90 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v191);
    v195 = (__int64)L"RequiresElevation";
    v196 = (std::_Ref_count_base *)17;
    winrt::param::hstring::hstring(&v233, &v195);
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      v179,
      &v233,
      v90);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v191);
    winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(v179, &v180);
    PluginHelpers::ParseCreateWorkProperties((PluginHelpers *)&v177, (const struct winrt::hstring *)&v180);
    std::make_pair<unsigned short const (&)[11],winrt::hstring &>(v212, v91, &v180);
    winrt::hstring::hstring((winrt::hstring *)&v249, L"StoreId");
    winrt::hstring::hstring((winrt::hstring *)&v250, (std::_Ref_count_base *)((char *)v202[0] + 24));
    v195 = (__int64)L"Plugin not available, Creating chained Work for Catalog Item";
    v196 = (std::_Ref_count_base *)60;
    std::string::string(v236, "InstallQueue2::CreateWorkForCatalogItem");
    std::string::string(&v233, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::TraceActivity_CorrelationVector___CallerContext2_const___Logging::CatalogSearchInfo_std::pair_unsigned_short_const___winrt::hstring__const___(
      (unsigned int)v255,
      (unsigned int)&v233,
      1705,
      (unsigned int)v236,
      v165,
      (__int64)&v195,
      (__int64)v50,
      (__int64)v11,
      (__int64)&v249,
      (__int64)v212);
    std::string::~string(&v233);
    std::string::~string(v236);
    Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)&v249);
    v92 = CreateUWAPlugin(&v178);
    v181 = 0;
    v238[0] = *((_QWORD *)v183 + 20);
    v233 = *(struct winrt::hstring **)CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v191);
    v93 = CorrelationVector::Increment(v50);
    *(_OWORD *)v239 = *(_OWORD *)((char *)v93 + 8);
    v240 = *(_OWORD *)((char *)v93 + 24);
    v241 = *(_OWORD *)((char *)v93 + 40);
    v242 = *(_OWORD *)((char *)v93 + 56);
    v243 = *(_OWORD *)((char *)v93 + 72);
    v244 = *(_OWORD *)((char *)v93 + 88);
    v245 = *(_OWORD *)((char *)v93 + 104);
    v246 = *(_OWORD *)((char *)v93 + 120);
    v247 = *((_BYTE *)v93 + 136);
    winrt::hstring::hstring((winrt::hstring *)&v248, (struct CorrelationVector *)((char *)v93 + 144));
    if ( !v248 )
    {
      _o_mbstowcs_s(0, v256, 129, v239, 129);
      winrt::hstring::operator=(&v248, v256);
    }
    v236[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v185, (const struct winrt::hstring *)&v248);
    winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServicePlugin<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>::CreateInstallServiceWork(
      v92,
      (unsigned int)v203,
      (unsigned int)v236,
      (unsigned int)&v233,
      (__int64)v238,
      (__int64)&v177,
      (__int64)&v181);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v185);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v248);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v191);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v181);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v178);
    v94 = v183 + 160;
    v95 = v183 + 152;
    v181 = *(struct winrt::hstring **)v203;
    winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v181);
    ChainedInstallServiceWork::AddWorkItem(v35, &v181, v95, v94, &v180);
    v96 = v202[0];
    v97 = (std::_Ref_count_base *)((char *)v202[0] + 160);
    winrt::hstring::hstring((winrt::hstring *)&v181, L"PackageFamilyName");
    ChainedInstallServiceWork::AddWorkItem(
      (ChainedInstallServiceWork *)v35,
      (const struct winrt::hstring *)&v181,
      (std::_Ref_count_base *)((char *)v96 + 32),
      (std::_Ref_count_base *)((char *)v96 + 152),
      v97,
      (const struct winrt::hstring *)&v180);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v181);
    v185 = (struct winrt::hstring *)(v35 + 16);
    v257 = (struct winrt::hstring *)(v35 + 16);
    winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v257);
    std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v258, v202);
    winrt::hstring::hstring((winrt::hstring *)v191, L"Acquisition");
    winrt::hstring::hstring((winrt::hstring *)&v178, L"ChainedWork");
    v181 = 0;
    v98 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v182, v202);
    v11 = v197;
    CreateCheckPointData(
      (int)v260,
      v98,
      (int)v50,
      (int)&v181,
      v197,
      (__int64)v97,
      (__int64)&v178,
      (__int64)&v206,
      v186,
      (__int64)v191);
    std::vector<InstallQueue2::Data>::push_back(v210, &v257);
    InstallQueue2::Data::~Data((InstallQueue2::Data *)&v257);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v181);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v191);
    v185 = 0;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v185);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v203);
    Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v255);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v213);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v177);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v180);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v179);
    if ( v184 )
      std::_Ref_count_base::_Decref(v184);
  }
  v99 = *(const struct winrt::hstring **)(*v10 + 112LL);
  v100 = *(unsigned __int16 **)(*v10 + 120LL);
  v178 = v100;
  while ( v99 != (const struct winrt::hstring *)v100 )
  {
    v101 = CatalogDataStore::GetSingleton();
    std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v195, v101);
    winrt::hstring::hstring((winrt::hstring *)&v177, L"StoreId");
    v102 = (unsigned int)CorrelationVector::Increment(v50);
    CatalogDataStore::LookupForUser(
      v195,
      (unsigned int)&v183,
      v102,
      (_DWORD)v11,
      (__int64)v199,
      (__int64)v217,
      (__int64)&v177,
      (__int64)v99,
      0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v177);
    if ( !v202[0] || !(unsigned __int8)winrt::operator==(v183 + 24, (char *)v202[0] + 24) )
    {
      v103 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v254, &v183);
      CreateJointWorkPropertiesJSON((unsigned int)&v180, v103, (_DWORD)v205, v186, v104);
      std::make_pair<unsigned short const (&)[11],winrt::hstring &>(v212, v105, &v180);
      if ( v183[284] && !(unsigned __int8)winrt::operator==(v183 + 24, *v10 + 24LL) )
      {
        v106 = v183;
        CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v203);
        LOBYTE(v106) = PluginHelpers::IsPluginAvailable(
                         (PluginHelpers *)v203,
                         (const struct winrt::hstring *)(v106 + 152),
                         v107);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v203);
        if ( (_BYTE)v106 )
        {
          winrt::hstring::hstring((winrt::hstring *)v224, L"StoreId");
          winrt::hstring::hstring((winrt::hstring *)v225, v99);
          v226[0] = L"Creating Child Item through plugin";
          v226[1] = 34;
          std::string::string(v238, "InstallQueue2::CreateWorkForCatalogItem");
          std::string::string(&v249, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          v50 = v187;
          Logging::TraceActivity_CorrelationVector___CallerContext2_const___Logging::CatalogSearchInfo_std::pair_unsigned_short_const___winrt::hstring__const___(
            (unsigned int)v255,
            (unsigned int)&v249,
            1734,
            (unsigned int)v238,
            v166,
            (__int64)v226,
            (__int64)v187,
            (__int64)v11,
            (__int64)v224,
            (__int64)v212);
          std::string::~string(&v249);
          std::string::~string(v238);
          Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v224);
          CreateInstallServiceWorkByPlugin(
            (winrt::Windows::Foundation::IUnknown *)&v233,
            v50,
            v11,
            (struct winrt::hstring *)(v183 + 152),
            (struct winrt::hstring *)(v183 + 160),
            (__int64)&v180);
          v257 = v233;
          winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v257);
          std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v258, &v183);
          winrt::hstring::hstring((winrt::hstring *)v191, L"Acquisition");
          v185 = 0;
          v108 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v236, &v183);
          CreateCheckPointData(
            (int)v260,
            v108,
            (int)v50,
            (int)&v185,
            v11,
            (__int64)&v234,
            (__int64)&ticks,
            (__int64)&v180,
            v186,
            (__int64)v191);
          std::vector<InstallQueue2::Data>::push_back(v210, &v257);
          InstallQueue2::Data::~Data((InstallQueue2::Data *)&v257);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v185);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v191);
          std::tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::~tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>(&v233);
          Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v255);
        }
        else
        {
          winrt::hstring::hstring((winrt::hstring *)v251, L"StoreId");
          winrt::hstring::hstring((winrt::hstring *)&v252, v99);
          *(_QWORD *)&v182 = L"Adding child into existing chained item";
          *((_QWORD *)&v182 + 1) = 39;
          std::string::string(&v233, "InstallQueue2::CreateWorkForCatalogItem");
          std::string::string(v238, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::TraceActivity_CorrelationVector___CallerContext2_const___Logging::CatalogSearchInfo_std::pair_unsigned_short_const___winrt::hstring__const___(
            (unsigned int)v255,
            (unsigned int)v238,
            1740,
            (unsigned int)&v233,
            v166,
            (__int64)&v182,
            (__int64)v187,
            (__int64)v11,
            (__int64)v251,
            (__int64)v212);
          std::string::~string(v238);
          std::string::~string(&v233);
          Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v251);
          v109 = (const struct winrt::hstring *)(v183 + 160);
          v185 = (struct winrt::hstring *)(v183 + 152);
          v181 = (struct winrt::hstring *)(v183 + 32);
          winrt::hstring::hstring((winrt::hstring *)v179, L"PackageFamilyName");
          ChainedInstallServiceWork::AddWorkItem(
            (ChainedInstallServiceWork *)v35,
            (const struct winrt::hstring *)v179,
            v181,
            v185,
            v109,
            (const struct winrt::hstring *)&v180);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v179);
          Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v255);
          v50 = v187;
        }
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(v213);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v180);
    }
    if ( v184 )
      std::_Ref_count_base::_Decref(v184);
    if ( v196 )
      std::_Ref_count_base::_Decref(v196);
    v99 = (const struct winrt::hstring *)((char *)v99 + 8);
    v100 = v178;
  }
  v110 = v204;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v206);
  if ( v35 )
    winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(&v190);
  if ( v202[1] )
    std::_Ref_count_base::_Decref(v202[1]);
  v111 = v198;
  *v198 = 0;
  v111[1] = 0;
  v111[2] = 0;
  LODWORD(v175) = v12 | 0x200;
  v219 = 0;
  v220 = 0;
  v112 = v210[0];
  v113 = v210[1];
  if ( v210[0] != v210[1] )
  {
    v177 = (struct winrt::hstring *)(*(_QWORD *)v192 + 144LL);
    v114 = (char *)v187;
    do
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl'::`2'::impl)
        && PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v193)
        && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl'::`2'::impl) )
      {
        *(_QWORD *)v192 = 0;
        tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::start(
          v192,
          v236);
        v115 = *(_OWORD *)v236;
        ticks = _Xtime_get_ticks();
        v116 = *(_QWORD *)std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::EnqueueToWorkingDelayTipData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>,0>>::_Try_emplace<winrt::hstring const &,>(
                            (char *)v194 + 712,
                            v226,
                            *((_QWORD *)v112 + 1) + 24LL);
        *(_OWORD *)(v116 + 24) = v115;
        *(_QWORD *)(v116 + 40) = ticks;
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(v192);
      }
      v195 = *((_QWORD *)v112 + 3);
      v196 = (std::_Ref_count_base *)*((_QWORD *)v112 + 4);
      *((_QWORD *)v112 + 3) = 0;
      *((_QWORD *)v112 + 4) = 0;
      v204 = *(_QWORD *)v112;
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v204);
      v117 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v254, (char *)v112 + 8);
      v118 = InstallQueue2::_LockQueueForEdit(v194, v232);
      v167 = (struct winrt::hstring *)v117;
      v119 = v194;
      InstallQueue2::_EnqueueWork(v194, (__int64)&v257, v118, v114, v11, v167, &v204, (__int64)&v195, 0);
      __1__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAA_XZ(v232);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl'::`2'::impl)
        && PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v193)
        && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl'::`2'::impl) )
      {
        *(_QWORD *)v192 = 0;
        tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::start(
          v192,
          &v182);
        v120 = v257;
        v121 = v182;
        ticks = _Xtime_get_ticks();
        winrt::hstring::hstring((winrt::hstring *)v251, v120);
        v252 = v121;
        v253 = ticks;
        v119 = v194;
        std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::EnqueueToWorkingDelayTipData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>,0>>::emplace<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>(
          (char *)v194 + 712,
          v212,
          v251);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v251);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(v192);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::GetImpl'::`2'::impl) )
      {
        InstallQueue2::_LockQueueForRead(v119, &v233);
        *(_OWORD *)v239 = *(_OWORD *)(v110 + 8);
        v240 = *(_OWORD *)(v110 + 24);
        v241 = *(_OWORD *)(v110 + 40);
        v242 = *(_OWORD *)(v110 + 56);
        v243 = *(_OWORD *)(v110 + 72);
        v244 = *(_OWORD *)(v110 + 88);
        v245 = *(_OWORD *)(v110 + 104);
        v246 = *(_OWORD *)(v110 + 120);
        v247 = *(_BYTE *)(v110 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v248, v177);
        LODWORD(v181) = InstallQueue2::GetAvailableOperationsCount(v119, v122);
        *(_QWORD *)v192 = (__int64)(*((_QWORD *)v119 + 46) - *((_QWORD *)v119 + 45)) >> 4;
        *(_QWORD *)v203 = (__int64)(*((_QWORD *)v221 + 34) - *((_QWORD *)v221 + 33)) >> 4;
        v185 = (struct winrt::hstring *)((__int64)(*((_QWORD *)v119 + 37) - *((_QWORD *)v119 + 36)) >> 4);
        LODWORD(v178) = *((_DWORD *)v119 + 54);
        Value = PluginHelpers::WorkProperty::CallerApplicationId::GetValue(&v218, v193);
        ClientAppId = (__int64 *)GetClientAppId(v238, L"Acquisition;", Value);
        v125 = (__int64)ClientAppId;
        if ( (unsigned __int64)ClientAppId[3] > 7 )
          v125 = *ClientAppId;
        v126 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Attributes(
                 v112,
                 v179);
        v127 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkAttributes<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkAttributes>::TelemetryData(
                                   v126,
                                   v191);
        winrt::hstring::c_str(v127);
        winrt::hstring::c_str((winrt::hstring *)(*((_QWORD *)v112 + 1) + 152LL));
        winrt::hstring::c_str((winrt::hstring *)(v128 + 80));
        winrt::hstring::c_str((winrt::hstring *)(v129 + 32));
        v131 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v130 + 24));
        LODWORD(v171) = (_DWORD)v178;
        LODWORD(v168) = 0;
        WindowsUpdate::CommonTelemetry::FulfillmentInitiate(
          v131,
          v134,
          0,
          v133,
          v132,
          v135,
          (const unsigned __int16 *)v168,
          v125,
          v171,
          (int)v185,
          v203[0],
          v192[0],
          (int)v181,
          (__int64)v239,
          v175);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v191);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v179);
        std::wstring::_Tidy_deallocate(v238);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v248);
        shared_lock::~shared_lock((shared_lock *)&v233);
      }
      else
      {
        *(_OWORD *)v239 = *(_OWORD *)(v110 + 8);
        v240 = *(_OWORD *)(v110 + 24);
        v241 = *(_OWORD *)(v110 + 40);
        v242 = *(_OWORD *)(v110 + 56);
        v243 = *(_OWORD *)(v110 + 72);
        v244 = *(_OWORD *)(v110 + 88);
        v245 = *(_OWORD *)(v110 + 104);
        v246 = *(_OWORD *)(v110 + 120);
        v247 = *(_BYTE *)(v110 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v248, v177);
        v136 = PluginHelpers::WorkProperty::CallerApplicationId::GetValue(&v190, v193);
        v137 = (__int64 *)GetClientAppId(v238, L"Acquisition;", v136);
        v138 = (__int64)v137;
        if ( (unsigned __int64)v137[3] > 7 )
          v138 = *v137;
        v139 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Attributes(
                 v112,
                 &v200);
        v140 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkAttributes<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkAttributes>::TelemetryData(
                                   v139,
                                   v201);
        winrt::hstring::c_str(v140);
        winrt::hstring::c_str((winrt::hstring *)(*((_QWORD *)v112 + 1) + 152LL));
        winrt::hstring::c_str((winrt::hstring *)(v141 + 80));
        winrt::hstring::c_str((winrt::hstring *)(v142 + 32));
        v144 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v143 + 24));
        LODWORD(v168) = 0;
        WindowsUpdate::CommonTelemetry::FulfillmentInitiate(
          v144,
          v147,
          0,
          v146,
          v145,
          v148,
          (const unsigned __int16 *)v168,
          v138,
          (const unsigned __int16 *)v239,
          v172);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v201);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v200);
        std::wstring::_Tidy_deallocate(v238);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v248);
      }
      v111 = v198;
      std::vector<winrt::WindowsUpdate::Internal::InstallItem>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::WindowsUpdate::Internal::InstallItem>>>,0>(
        (_DWORD)v198,
        (unsigned int)&v180,
        v198[1],
        v259,
        *(__int64 *)v260);
      if ( *((_QWORD *)&v219 + 1) == v220 )
      {
        std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(
          &v219,
          *((_QWORD *)&v219 + 1),
          &v257);
      }
      else
      {
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(*((_QWORD *)&v219 + 1), &v257);
        *((_QWORD *)&v219 + 1) += 16LL;
      }
      std::tuple<std::vector<winrt::WindowsUpdate::Internal::InstallItem>,std::shared_ptr<InstallQueue2::QueueItem>>::~tuple<std::vector<winrt::WindowsUpdate::Internal::InstallItem>,std::shared_ptr<InstallQueue2::QueueItem>>(&v257);
      v112 = (InstallQueue2::Data *)((char *)v112 + 40);
    }
    while ( v112 != v113 );
    v10 = v207;
  }
  std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(&v219);
  if ( v210[0] )
  {
    std::_Destroy_range<std::allocator<InstallQueue2::Data>>(v210[0]);
    std::_Deallocate<16>(v210[0], 8 * ((signed __int64)(v211 - (unsigned __int64)v210[0]) >> 3));
    *(_OWORD *)v210 = 0;
    v211 = 0;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v189);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v188);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v217);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v199);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v193);
  Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v222);
  v149 = (std::_Ref_count_base *)v10[1];
  if ( v149 )
    std::_Ref_count_base::_Decref(v149);
  return v111;
}

```

## disassembly

```asm
0x18015ed00  mov     r11, rsp
0x18015ed03  push    rbx
0x18015ed04  push    rsi
0x18015ed05  push    rdi
0x18015ed06  push    r12
0x18015ed08  push    r13
0x18015ed0a  push    r14
0x18015ed0c  push    r15
0x18015ed0e  sub     rsp, 6D0h
0x18015ed15  movaps  xmmword ptr [r11-48h], xmm6
0x18015ed1a  mov     rax, cs:__security_cookie
0x18015ed21  xor     rax, rsp
0x18015ed24  mov     [rsp+708h+var_58], rax
0x18015ed2c  mov     r14, r9
0x18015ed2f  mov     [rsp+708h+var_638], r9
0x18015ed37  mov     r13, r8
0x18015ed3a  mov     [r11-588h], r8
0x18015ed41  mov     [r11-5E0h], rdx
0x18015ed48  mov     [rsp+708h+var_600], rcx
0x18015ed50  mov     [rsp+708h+var_508], rcx
0x18015ed58  mov     [rsp+708h+var_5D0], rcx
0x18015ed60  mov     [r11-580h], rdx
0x18015ed67  mov     [r11-578h], r8
0x18015ed6e  mov     [rsp+708h+var_5C8], r9
0x18015ed76  mov     [rsp+708h+var_5A0], r9
0x18015ed7e  mov     qword ptr [rsp+708h+var_610], r9
0x18015ed86  mov     rsi, [rsp+708h+arg_20]
0x18015ed8e  mov     [rsp+708h+var_5E8], rsi
0x18015ed96  mov     rdx, [rsp+708h+arg_28]; struct winrt::hstring *
0x18015ed9e  mov     rbx, [rsp+708h+arg_30]
0x18015eda6  mov     [rsp+708h+var_528], rbx
0x18015edae  mov     rax, [rsp+708h+arg_38]
0x18015edb6  mov     [rsp+708h+var_598], rax
0x18015edbe  mov     rax, [rsp+708h+arg_40]
0x18015edc6  mov     [rsp+708h+var_640], rax
0x18015edce  xor     r15d, r15d
0x18015edd1  mov     r12d, r15d
0x18015edd4  mov     dword ptr [rsp+708h+var_698], r15d
0x18015edd9  lea     rcx, [r11-500h]; this
0x18015ede0  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18015ede5  nop
0x18015ede6  mov     rdx, rbx; struct winrt::hstring *
0x18015ede9  lea     rcx, [rsp+708h+var_4F8]; this
0x18015edf1  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18015edf6  nop
0x18015edf7  mov     rbx, [rsp+708h+var_598]
0x18015edff  mov     rax, [rbx]
0x18015ee02  mov     [rsp+708h+var_3C0], rax
0x18015ee0a  lea     rdx, [rsp+708h+var_3C0]
0x18015ee12  lea     rcx, [rsp+708h+var_608]; struct winrt::param::hstring *
0x18015ee1a  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x18015ee1f  nop
0x18015ee20  lea     rcx, [rsp+708h+var_608]; struct winrt::Windows::Data::Json::JsonObject *
0x18015ee28  call    ?GetValue@IsInteractive@WorkProperty@PluginHelpers@@SA_NAEBUJsonObject@Json@Data@Windows@winrt@@@Z; PluginHelpers::WorkProperty::IsInteractive::GetValue(winrt::Windows::Data::Json::JsonObject const &)
0x18015ee2d  movzx   eax, al
0x18015ee30  add     eax, eax
0x18015ee32  mov     dword ptr [rsp+708h+var_670], eax
0x18015ee39  lea     rdx, [rsp+708h+var_608]
0x18015ee41  lea     rcx, [rsp+708h+var_5D8]
0x18015ee49  call    ?GetValue@CatalogId@WorkProperty@PluginHelpers@@SA?AUhstring@winrt@@AEBUJsonObject@Json@Data@Windows@5@@Z; PluginHelpers::WorkProperty::CatalogId::GetValue(winrt::Windows::Data::Json::JsonObject const &)
0x18015ee4e  nop
0x18015ee4f  lea     rdx, [rsp+708h+var_608]
0x18015ee57  lea     rcx, [rsp+708h+var_530]
0x18015ee5f  call    ?GetValue@UserIdentityInfo@WorkProperty@PluginHelpers@@SA?AUhstring@winrt@@AEBUJsonObject@Json@Data@Windows@5@@Z; PluginHelpers::WorkProperty::UserIdentityInfo::GetValue(winrt::Windows::Data::Json::JsonObject const &)
0x18015ee64  nop
0x18015ee65  lea     rdi, dword_18023C12C
0x18015ee6c  mov     rdx, rdi; unsigned __int16 *
0x18015ee6f  lea     rcx, [rsp+708h+var_680]; this
0x18015ee77  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18015ee7c  nop
0x18015ee7d  mov     rdx, r13
0x18015ee80  lea     rcx, [rsp+708h+var_668]
0x18015ee88  call    ??0?$shared_ptr@VNotificationQueue@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(std::shared_ptr<NotificationQueue> const &)
0x18015ee8d  lea     rcx, [rsp+708h+var_680]
0x18015ee95  mov     [rsp+708h+var_6E8], rcx
0x18015ee9a  mov     r9, [rsp+708h+var_640]
0x18015eea2  mov     r8, rbx
0x18015eea5  mov     rdx, rax
0x18015eea8  lea     rcx, [rsp+708h+var_630]
0x18015eeb0  call    CreateJointWorkPropertiesJSON
0x18015eeb5  nop
0x18015eeb6  lea     rcx, [rsp+708h+var_680]
0x18015eebe  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18015eec3  mov     rdx, rdi; unsigned __int16 *
0x18015eec6  lea     rcx, [rsp+708h+var_628]; this
0x18015eece  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18015eed3  nop
0x18015eed4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement> `wil::Feature<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::GetImpl(void)'::`2'::impl
0x18015eedb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::__private_IsEnabled(void)
0x18015eee0  test    al, al
0x18015eee2  jz      loc_18015F234
0x18015eee8  mov     rdx, [r13+0]
0x18015eeec  add     rdx, 0A0h; struct winrt::hstring *
0x18015eef3  cmp     [rdx], r15
0x18015eef6  jz      loc_18015F1DB
0x18015eefc  lea     rcx, [rsp+708h+var_548]; this
0x18015ef04  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18015ef09  nop
0x18015ef0a  lea     rcx, [rsp+708h+var_688]; this
0x18015ef12  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18015ef17  nop
0x18015ef18  mov     rax, [r13+0]
0x18015ef1c  mov     rcx, [rax+0A0h]
0x18015ef23  mov     [rsp+708h+var_3C0], rcx
0x18015ef2b  lea     rdx, [rsp+708h+var_688]; struct winrt::Windows::Data::Json::JsonObject *
0x18015ef33  lea     rcx, [rsp+708h+var_3C0]; struct winrt::param::hstring *
0x18015ef3b  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x18015ef40  test    al, al
0x18015ef42  jz      loc_18015F1BF
0x18015ef48  mov     rax, [r13+0]
0x18015ef4c  cmp     [rax+0E0h], r15
0x18015ef53  jz      loc_18015F16A
0x18015ef59  cmp     [rax+0D8h], r15
0x18015ef60  jz      loc_18015F16A
0x18015ef66  lea     rdx, aPurchasableava; "PurchasableAvailabilityId"
0x18015ef6d  lea     rcx, [rsp+708h+var_3C0]; this
0x18015ef75  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015ef7a  lea     rdx, [rsp+708h+var_3C0]
0x18015ef82  lea     rcx, [rsp+708h+var_688]
0x18015ef8a  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18015ef8f  test    al, al
0x18015ef91  jz      short loc_18015EFEA
0x18015ef93  mov     rdx, rdi; unsigned __int16 *
0x18015ef96  lea     rcx, [rsp+708h+var_400]; this
0x18015ef9e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015efa3  lea     rdx, aPurchasableava; "PurchasableAvailabilityId"
0x18015efaa  lea     rcx, [rsp+708h+var_3E0]; this
0x18015efb2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015efb7  lea     r9, [rsp+708h+var_400]
0x18015efbf  lea     r8, [rsp+708h+var_3E0]
0x18015efc7  lea     rdx, [rsp+708h+var_690]
0x18015efcc  lea     rcx, [rsp+708h+var_688]
0x18015efd4  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18015efd9  lea     r12d, [r15+1]
0x18015efdd  mov     dword ptr [rsp+708h+var_698], r12d
0x18015efe2  cmp     [rax], r15
0x18015efe5  mov     bl, r15b
0x18015efe8  jnz     short loc_18015EFEC
0x18015efea  mov     bl, 1
0x18015efec  test    r12b, 1
0x18015eff0  jz      short loc_18015F005
0x18015eff2  and     r12d, 0FFFFFFFEh
0x18015eff6  mov     dword ptr [rsp+708h+var_698], r12d
0x18015effb  lea     rcx, [rsp+708h+var_690]
0x18015f000  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18015f005  test    bl, bl
0x18015f007  jz      short loc_18015F068
0x18015f009  mov     rax, [r13+0]
0x18015f00d  mov     rcx, [rax+0E0h]
0x18015f014  mov     [rsp+708h+var_3C0], rcx
0x18015f01c  lea     rdx, [rsp+708h+var_3C0]
0x18015f024  lea     rcx, [rsp+708h+var_690]; struct winrt::param::hstring *
0x18015f029  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18015f02e  mov     rbx, rax
0x18015f031  lea     rdx, aPurchasableava; "PurchasableAvailabilityId"
0x18015f038  lea     rcx, [rsp+708h+var_400]; this
0x18015f040  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f045  mov     r8, rbx
0x18015f048  lea     rdx, [rsp+708h+var_400]
0x18015f050  lea     rcx, [rsp+708h+var_688]
0x18015f058  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18015f05d  nop
0x18015f05e  lea     rcx, [rsp+708h+var_690]; void *
0x18015f063  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18015f068  lea     rdx, aPurchasablesku; "PurchasableSkuId"
0x18015f06f  lea     rcx, [rsp+708h+var_3C0]; this
0x18015f077  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f07c  lea     rdx, [rsp+708h+var_3C0]
0x18015f084  lea     rcx, [rsp+708h+var_688]
0x18015f08c  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18015f091  test    al, al
0x18015f093  jz      short loc_18015F0EC
0x18015f095  mov     rdx, rdi; unsigned __int16 *
0x18015f098  lea     rcx, [rsp+708h+var_400]; this
0x18015f0a0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f0a5  lea     rdx, aPurchasablesku; "PurchasableSkuId"
0x18015f0ac  lea     rcx, [rsp+708h+var_3E0]; this
0x18015f0b4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f0b9  lea     r9, [rsp+708h+var_400]
0x18015f0c1  lea     r8, [rsp+708h+var_3E0]
0x18015f0c9  lea     rdx, [rsp+708h+var_690]
0x18015f0ce  lea     rcx, [rsp+708h+var_688]
0x18015f0d6  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18015f0db  or      r12d, 2
0x18015f0df  mov     dword ptr [rsp+708h+var_698], r12d
0x18015f0e4  cmp     [rax], r15
0x18015f0e7  mov     bl, r15b
0x18015f0ea  jnz     short loc_18015F0EE
0x18015f0ec  mov     bl, 1
0x18015f0ee  test    r12b, 2
0x18015f0f2  jz      short loc_18015F107
0x18015f0f4  and     r12d, 0FFFFFFFDh
0x18015f0f8  mov     dword ptr [rsp+708h+var_698], r12d
0x18015f0fd  lea     rcx, [rsp+708h+var_690]
0x18015f102  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18015f107  test    bl, bl
0x18015f109  jz      short loc_18015F16A
0x18015f10b  mov     rax, [r13+0]
0x18015f10f  mov     rcx, [rax+0D8h]
0x18015f116  mov     [rsp+708h+var_3C0], rcx
0x18015f11e  lea     rdx, [rsp+708h+var_3C0]
0x18015f126  lea     rcx, [rsp+708h+var_690]; struct winrt::param::hstring *
0x18015f12b  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18015f130  mov     rbx, rax
0x18015f133  lea     rdx, aPurchasablesku; "PurchasableSkuId"
0x18015f13a  lea     rcx, [rsp+708h+var_400]; this
0x18015f142  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f147  mov     r8, rbx
0x18015f14a  lea     rdx, [rsp+708h+var_400]
0x18015f152  lea     rcx, [rsp+708h+var_688]
0x18015f15a  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18015f15f  nop
0x18015f160  lea     rcx, [rsp+708h+var_690]; void *
0x18015f165  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18015f16a  lea     rdx, [rsp+708h+var_690]
0x18015f16f  lea     rcx, [rsp+708h+var_688]
0x18015f177  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(void)
0x18015f17c  lea     rcx, [rsp+708h+var_548]
0x18015f184  cmp     rcx, rax
0x18015f187  jz      short loc_18015F19C
0x18015f189  mov     rdx, [rax]
0x18015f18c  mov     [rax], r15
0x18015f18f  lea     rcx, [rsp+708h+var_548]
0x18015f197  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18015f19c  lea     rcx, [rsp+708h+var_690]
0x18015f1a1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18015f1a6  mov     rcx, [r13+0]
0x18015f1aa  add     rcx, 0A0h
0x18015f1b1  lea     rdx, [rsp+708h+var_548]
0x18015f1b9  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18015f1be  nop
0x18015f1bf  lea     rcx, [rsp+708h+var_688]; void *
0x18015f1c7  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18015f1cc  nop
0x18015f1cd  lea     rcx, [rsp+708h+var_548]
0x18015f1d5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18015f1da  nop
0x18015f1db  jmp     short loc_18015F234
0x18015f1dd  xor     r15d, r15d
0x18015f1e0  lea     rdi, dword_18023C12C
0x18015f1e7  mov     r12d, dword ptr [rsp+708h+var_698]
0x18015f1ec  mov     rdx, [rsp+708h+var_580]
0x18015f1f4  mov     [rsp+708h+var_5E0], rdx
0x18015f1fc  mov     rax, [rsp+708h+var_5D0]
0x18015f204  mov     [rsp+708h+var_600], rax
0x18015f20c  mov     r13, [rsp+708h+var_578]
0x18015f214  mov     [rsp+708h+var_588], r13
0x18015f21c  mov     r14, [rsp+708h+var_5C8]
0x18015f224  mov     [rsp+708h+var_638], r14
0x18015f22c  mov     rsi, [rsp+708h+var_5E8]
0x18015f234  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GetEntitlementIfNotPresent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GetEntitlementIfNotPresent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent> `wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl(void)'::`2'::impl
0x18015f23b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GetEntitlementIfNotPresent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(void)
0x18015f240  test    al, al
0x18015f242  jz      loc_18015F5B0
0x18015f248  call    ?GetEnableGetEntitlementIfNotPresent@@YA_NXZ; GetEnableGetEntitlementIfNotPresent(void)
0x18015f24d  test    al, al
0x18015f24f  jz      loc_18015F5B0
0x18015f255  mov     rdx, [r13+0]
0x18015f259  add     rdx, 0A0h
0x18015f260  cmp     [rdx], r15
0x18015f263  jz      loc_18015F557
0x18015f269  lea     rcx, [rsp+708h+var_628]
0x18015f271  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18015f276  lea     rdx, [rsp+708h+var_628]; struct winrt::hstring *
0x18015f27e  lea     rcx, [rsp+708h+var_540]; this
0x18015f286  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18015f28b  nop
0x18015f28c  lea     rcx, [rsp+708h+var_688]; this
0x18015f294  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18015f299  nop
0x18015f29a  mov     rax, [rsp+708h+var_628]
0x18015f2a2  mov     [rsp+708h+var_3C0], rax
0x18015f2aa  lea     rdx, [rsp+708h+var_688]; struct winrt::Windows::Data::Json::JsonObject *
0x18015f2b2  lea     rcx, [rsp+708h+var_3C0]; struct winrt::param::hstring *
0x18015f2ba  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x18015f2bf  test    al, al
0x18015f2c1  jz      loc_18015F53B
0x18015f2c7  mov     rax, [r13+0]
0x18015f2cb  cmp     [rax+0E0h], r15
0x18015f2d2  jz      loc_18015F4E9
0x18015f2d8  cmp     [rax+0D8h], r15
0x18015f2df  jz      loc_18015F4E9
0x18015f2e5  lea     rdx, aPurchasableava; "PurchasableAvailabilityId"
0x18015f2ec  lea     rcx, [rsp+708h+var_3C0]; this
0x18015f2f4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f2f9  lea     rdx, [rsp+708h+var_3C0]
0x18015f301  lea     rcx, [rsp+708h+var_688]
0x18015f309  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18015f30e  test    al, al
0x18015f310  jz      short loc_18015F369
0x18015f312  mov     rdx, rdi; unsigned __int16 *
0x18015f315  lea     rcx, [rsp+708h+var_400]; this
0x18015f31d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f322  lea     rdx, aPurchasableava; "PurchasableAvailabilityId"
0x18015f329  lea     rcx, [rsp+708h+var_3E0]; this
0x18015f331  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18015f336  lea     r9, [rsp+708h+var_400]
0x18015f33e  lea     r8, [rsp+708h+var_3E0]
0x18015f346  lea     rdx, [rsp+708h+var_690]
0x18015f34b  lea     rcx, [rsp+708h+var_688]
  ... truncated ...
```
