# InstallQueue2::CreateWorkForCatalogItem(std::shared_ptr<CatalogDataStore::CatalogItem>,CorrelationVector &,CallerContext2 const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)

- ea: `0x18015ed00`
- end: `0x1801621d1`
- name: `?CreateWorkForCatalogItem@InstallQueue2@@QEAA?AV?$vector@UInstallItem@Internal@WindowsUpdate@winrt@@V?$allocator@UInstallItem@Internal@WindowsUpdate@winrt@@@std@@@std@@V?$shared_ptr@UCatalogItem@CatalogDataStore@@@3@AEAVCorrelationVector@@AEBUCallerContext2@@AEBUhstring@winrt@@333@Z`
- size: `13521`
- prototype: `_QWORD *__fastcall(InstallQueue2 *, _QWORD *, _QWORD *, CorrelationVector *, struct winrt::hstring *, struct winrt::hstring *, struct winrt::hstring *, _QWORD *, __int64)`
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
  __int128 v114; // xmm6
  __int64 v115; // rcx
  __int64 v116; // rbx
  InstallQueue2 *v117; // rbx
  struct winrt::hstring *v118; // rbx
  __int128 v119; // xmm6
  const struct store_lock *v120; // rdx
  __int64 Value; // rax
  __int64 *ClientAppId; // rax
  __int64 v123; // rbx
  __int64 v124; // rax
  winrt::hstring *v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rdx
  __int64 v128; // rdx
  WindowsUpdate::CommonTelemetry *v129; // rax
  const unsigned __int16 *v130; // r8
  const unsigned __int16 *v131; // r9
  const unsigned __int16 *v132; // r10
  const unsigned __int16 *v133; // r11
  __int64 v134; // rax
  __int64 *v135; // rax
  __int64 v136; // rbx
  __int64 v137; // rax
  winrt::hstring *v138; // rax
  __int64 v139; // rdx
  __int64 v140; // rdx
  __int64 v141; // rdx
  WindowsUpdate::CommonTelemetry *v142; // rax
  const unsigned __int16 *v143; // r8
  const unsigned __int16 *v144; // r9
  const unsigned __int16 *v145; // r10
  const unsigned __int16 *v146; // r11
  std::_Ref_count_base *v147; // rcx
  const struct winrt::hstring *v149; // rdx
  __int64 v150; // rax
  unsigned int *v151; // rax
  __int64 v152; // r8
  unsigned int *v153; // rax
  __int64 v154; // r8
  const struct winrt::impl::slim_source_location *v155; // rax
  unsigned int *v156; // rax
  __int64 v157; // r8
  const struct winrt::impl::slim_source_location *v158; // rax
  struct winrt::hstring *v159; // [rsp+20h] [rbp-6E8h]
  struct winrt::hstring *v160; // [rsp+20h] [rbp-6E8h]
  struct winrt::hstring *v161; // [rsp+20h] [rbp-6E8h]
  int v162; // [rsp+20h] [rbp-6E8h]
  int v163; // [rsp+20h] [rbp-6E8h]
  int v164; // [rsp+20h] [rbp-6E8h]
  struct winrt::hstring *v165; // [rsp+28h] [rbp-6E0h]
  char *v166; // [rsp+30h] [rbp-6D8h]
  char *v167; // [rsp+38h] [rbp-6D0h]
  char *v168; // [rsp+38h] [rbp-6D0h]
  unsigned __int16 *v169; // [rsp+40h] [rbp-6C8h]
  const char *v170; // [rsp+48h] [rbp-6C0h]
  const char *v171; // [rsp+50h] [rbp-6B8h]
  const char *v172; // [rsp+50h] [rbp-6B8h]
  char *v173; // [rsp+70h] [rbp-698h]
  int v174; // [rsp+70h] [rbp-698h]
  struct winrt::hstring *v175; // [rsp+78h] [rbp-690h] BYREF
  unsigned __int16 *v176; // [rsp+80h] [rbp-688h] BYREF
  int v177[2]; // [rsp+88h] [rbp-680h] BYREF
  __int64 v178; // [rsp+90h] [rbp-678h] BYREF
  struct winrt::hstring *v179; // [rsp+98h] [rbp-670h] BYREF
  __int128 v180; // [rsp+A0h] [rbp-668h] BYREF
  _BYTE *v181; // [rsp+B0h] [rbp-658h] BYREF
  std::_Ref_count_base *v182; // [rsp+B8h] [rbp-650h]
  struct winrt::hstring *v183; // [rsp+C0h] [rbp-648h] BYREF
  __int64 v184; // [rsp+C8h] [rbp-640h]
  CorrelationVector *v185; // [rsp+D0h] [rbp-638h]
  __int64 v186; // [rsp+D8h] [rbp-630h] BYREF
  __int64 v187; // [rsp+E0h] [rbp-628h] BYREF
  __int64 v188; // [rsp+E8h] [rbp-620h] BYREF
  bool v189[8]; // [rsp+F0h] [rbp-618h] BYREF
  int v190[2]; // [rsp+F8h] [rbp-610h] BYREF
  char v191[8]; // [rsp+100h] [rbp-608h] BYREF
  InstallQueue2 *v192; // [rsp+108h] [rbp-600h]
  __int64 v193; // [rsp+110h] [rbp-5F8h] BYREF
  std::_Ref_count_base *v194; // [rsp+118h] [rbp-5F0h]
  struct winrt::hstring *v195; // [rsp+120h] [rbp-5E8h]
  _QWORD *v196; // [rsp+128h] [rbp-5E0h]
  char v197[8]; // [rsp+130h] [rbp-5D8h] BYREF
  InstallQueue2 *v198; // [rsp+138h] [rbp-5D0h] BYREF
  _QWORD v199[2]; // [rsp+140h] [rbp-5C8h] BYREF
  std::_Ref_count_base *v200[2]; // [rsp+150h] [rbp-5B8h] BYREF
  int v201[2]; // [rsp+160h] [rbp-5A8h] BYREF
  __int64 v202; // [rsp+168h] [rbp-5A0h] BYREF
  _QWORD *v203; // [rsp+170h] [rbp-598h]
  __int64 v204; // [rsp+178h] [rbp-590h] BYREF
  _QWORD *v205; // [rsp+180h] [rbp-588h]
  _QWORD *v206; // [rsp+188h] [rbp-580h]
  _QWORD *v207; // [rsp+190h] [rbp-578h]
  InstallQueue2::Data *v208[2]; // [rsp+198h] [rbp-570h] BYREF
  __int64 v209; // [rsp+1A8h] [rbp-560h]
  char v210[8]; // [rsp+1B0h] [rbp-558h] BYREF
  char v211[8]; // [rsp+1B8h] [rbp-550h] BYREF
  char v212[8]; // [rsp+1C0h] [rbp-548h] BYREF
  char v213[8]; // [rsp+1C8h] [rbp-540h] BYREF
  char v214[8]; // [rsp+1D0h] [rbp-538h] BYREF
  char v215[8]; // [rsp+1D8h] [rbp-530h] BYREF
  struct winrt::hstring *v216; // [rsp+1E0h] [rbp-528h] BYREF
  __int128 v217; // [rsp+1E8h] [rbp-520h] BYREF
  __int64 v218; // [rsp+1F8h] [rbp-510h]
  InstallQueue2 *v219; // [rsp+200h] [rbp-508h]
  char v220[8]; // [rsp+208h] [rbp-500h] BYREF
  char v221[8]; // [rsp+210h] [rbp-4F8h] BYREF
  char v222[8]; // [rsp+218h] [rbp-4F0h] BYREF
  char v223[8]; // [rsp+220h] [rbp-4E8h] BYREF
  _QWORD v224[3]; // [rsp+228h] [rbp-4E0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+240h] [rbp-4C8h] BYREF
  _BYTE v226[24]; // [rsp+258h] [rbp-4B0h] BYREF
  _BYTE v227[24]; // [rsp+270h] [rbp-498h] BYREF
  _BYTE v228[24]; // [rsp+288h] [rbp-480h] BYREF
  _BYTE v229[48]; // [rsp+2A0h] [rbp-468h] BYREF
  _BYTE v230[56]; // [rsp+2D0h] [rbp-438h] BYREF
  struct winrt::hstring *v231; // [rsp+308h] [rbp-400h] BYREF
  __int64 v232; // [rsp+310h] [rbp-3F8h] BYREF
  __int64 ticks; // [rsp+318h] [rbp-3F0h] BYREF
  __int64 v234[2]; // [rsp+328h] [rbp-3E0h] BYREF
  __int64 v235[2]; // [rsp+338h] [rbp-3D0h] BYREF
  _QWORD v236[5]; // [rsp+348h] [rbp-3C0h] BYREF
  char v237[16]; // [rsp+370h] [rbp-398h] BYREF
  __int128 v238; // [rsp+380h] [rbp-388h]
  __int128 v239; // [rsp+390h] [rbp-378h]
  __int128 v240; // [rsp+3A0h] [rbp-368h]
  __int128 v241; // [rsp+3B0h] [rbp-358h]
  __int128 v242; // [rsp+3C0h] [rbp-348h]
  __int128 v243; // [rsp+3D0h] [rbp-338h]
  __int128 v244; // [rsp+3E0h] [rbp-328h]
  char v245; // [rsp+3F0h] [rbp-318h]
  __int64 v246; // [rsp+3F8h] [rbp-310h] BYREF
  __int64 v247; // [rsp+400h] [rbp-308h] BYREF
  std::_Ref_count_base *v248; // [rsp+408h] [rbp-300h] BYREF
  char v249[8]; // [rsp+420h] [rbp-2E8h] BYREF
  __int128 v250; // [rsp+428h] [rbp-2E0h] BYREF
  __int64 v251; // [rsp+438h] [rbp-2D0h]
  _BYTE v252[32]; // [rsp+440h] [rbp-2C8h] BYREF
  _BYTE v253[272]; // [rsp+460h] [rbp-2A8h] BYREF
  _BYTE v254[272]; // [rsp+570h] [rbp-198h] BYREF
  struct winrt::hstring *v255; // [rsp+680h] [rbp-88h] BYREF
  char v256[8]; // [rsp+688h] [rbp-80h] BYREF
  __int64 v257; // [rsp+690h] [rbp-78h]
  int v258[2]; // [rsp+698h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+0h]

  v9 = a4;
  v185 = a4;
  v10 = a3;
  v205 = a3;
  v196 = a2;
  v192 = a1;
  v219 = a1;
  v198 = a1;
  v206 = a2;
  v207 = a3;
  v199[0] = a4;
  v202 = (__int64)a4;
  *(_QWORD *)v190 = a4;
  v11 = a5;
  v195 = a5;
  v216 = a7;
  v203 = a8;
  v184 = a9;
  v12 = 0;
  v174 = 0;
  winrt::hstring::hstring((winrt::hstring *)v220, a6);
  winrt::hstring::hstring((winrt::hstring *)v221, a7);
  v236[0] = *a8;
  winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v191);
  LODWORD(v179) = 2
                * PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v191);
  PluginHelpers::WorkProperty::CatalogId::GetValue(v197, v191);
  PluginHelpers::WorkProperty::UserIdentityInfo::GetValue(v215, v191);
  winrt::hstring::hstring((winrt::hstring *)v177, (const unsigned __int16 *)&dword_18023C12C);
  v13 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v180, v10);
  CreateJointWorkPropertiesJSON((unsigned int)&v186, v13, (_DWORD)a8, v184, (__int64)v177);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
  winrt::hstring::hstring((winrt::hstring *)&v187, (const unsigned __int16 *)&dword_18023C12C);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetFreeEntitlementOnNoEntitlement>::GetImpl'::`2'::impl) )
  {
    try
    {
      v14 = (const struct winrt::hstring *)(*v10 + 160LL);
      if ( *(_QWORD *)v14 )
      {
        winrt::hstring::hstring((winrt::hstring *)v212, v14);
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v176);
        v236[0] = *(_QWORD *)(*v10 + 160LL);
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v236,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v176) )
        {
          if ( *(_QWORD *)(*v10 + 224LL) && *(_QWORD *)(*v10 + 216LL) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableAvailabilityId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v176,
                                     v236)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v231,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v234, L"PurchasableAvailabilityId"),
                  v12 = 1,
                  v174 = 1,
                  v15 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v176,
                                &v175,
                                v234,
                                &v231)) )
            {
              v15 = 1;
            }
            if ( (v12 & 1) != 0 )
            {
              v12 &= ~1u;
              v174 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
            }
            if ( v15 )
            {
              v236[0] = *(_QWORD *)(*v10 + 224LL);
              StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v175);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v231, L"PurchasableAvailabilityId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v176,
                &v231,
                StringValue);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableSkuId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v176,
                                     v236)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v231,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v234, L"PurchasableSkuId"),
                  v12 |= 2u,
                  v174 = v12,
                  v17 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v176,
                                &v175,
                                v234,
                                &v231)) )
            {
              v17 = 1;
            }
            if ( (v12 & 2) != 0 )
            {
              v12 &= ~2u;
              v174 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
            }
            if ( v17 )
            {
              v236[0] = *(_QWORD *)(*v10 + 216LL);
              v18 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v175);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v231, L"PurchasableSkuId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v176,
                &v231,
                v18);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
            }
          }
          v19 = (char *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                          &v176,
                          &v175);
          if ( v212 != v19 )
          {
            v20 = *(_QWORD *)v19;
            *(_QWORD *)v19 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v212, v20);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
          winrt::hstring::operator=(*v10 + 160LL, v212);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v176);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v212);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x5A6,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        "Failed to merge purchasableAvailabilityId and purchasableSkuId into fulfillmentData",
        (const char *)v161);
      v12 = v174;
      v196 = v206;
      v192 = v198;
      v10 = v207;
      v205 = v207;
      v9 = (CorrelationVector *)v199[0];
      v185 = (CorrelationVector *)v199[0];
      v11 = v195;
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
        winrt::hstring::operator=(&v187, v21);
        winrt::hstring::hstring((winrt::hstring *)v213, (const struct winrt::hstring *)&v187);
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v176);
        v236[0] = v187;
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v236,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v176) )
        {
          if ( *(_QWORD *)(*v10 + 224LL) && *(_QWORD *)(*v10 + 216LL) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableAvailabilityId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v176,
                                     v236)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v231,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v234, L"PurchasableAvailabilityId"),
                  v12 |= 4u,
                  v174 = v12,
                  v22 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v176,
                                &v175,
                                v234,
                                &v231)) )
            {
              v22 = 1;
            }
            if ( (v12 & 4) != 0 )
            {
              v12 &= ~4u;
              v174 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
            }
            if ( v22 )
            {
              v236[0] = *(_QWORD *)(*v10 + 224LL);
              v23 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v175);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v231, L"PurchasableAvailabilityId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v176,
                &v231,
                v23);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PurchasableSkuId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v176,
                                     v236)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v231,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v234, L"PurchasableSkuId"),
                  v12 |= 8u,
                  v174 = v12,
                  v24 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v176,
                                &v175,
                                v234,
                                &v231)) )
            {
              v24 = 1;
            }
            if ( (v12 & 8) != 0 )
            {
              v12 &= ~8u;
              v174 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
            }
            if ( v24 )
            {
              v236[0] = *(_QWORD *)(*v10 + 216LL);
              v25 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v175);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v231, L"PurchasableSkuId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v176,
                &v231,
                v25);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
            }
          }
          v26 = (char *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                          &v176,
                          &v175);
          if ( v213 != v26 )
          {
            v27 = *(_QWORD *)v26;
            *(_QWORD *)v26 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v213, v27);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
          winrt::hstring::operator=(&v187, v213);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v176);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v213);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x5CD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        "Failed to merge purchasableAvailabilityId and purchasableSkuId into mutableFulfillmentData",
        (const char *)v160);
      v12 = v174;
      v196 = v206;
      v192 = v198;
      v10 = v207;
      v205 = v207;
      v9 = (CorrelationVector *)v199[0];
      v185 = (CorrelationVector *)v199[0];
      v11 = v195;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
  {
    if ( v187 )
      v28 = (const struct winrt::hstring *)&v187;
    else
      v28 = (const struct winrt::hstring *)(*v10 + 160LL);
    try
    {
      winrt::hstring::hstring((winrt::hstring *)&v188, v28);
      if ( v188 )
      {
        winrt::hstring::hstring((winrt::hstring *)v214, (const struct winrt::hstring *)&v188);
        winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v176);
        v236[0] = v188;
        if ( (unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                                (const struct winrt::param::hstring *)v236,
                                (struct winrt::Windows::Data::Json::JsonObject *)&v176) )
        {
          if ( *(_QWORD *)(*v10 + 272LL) && *(_QWORD *)(*v10 + 200LL) )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PackageRankId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v176,
                                     v236)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v231,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v234, L"PackageRankId"),
                  v12 |= 0x10u,
                  v174 = v12,
                  v29 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v176,
                                &v175,
                                v234,
                                &v231)) )
            {
              v29 = 1;
            }
            if ( (v12 & 0x10) != 0 )
            {
              v12 &= ~0x10u;
              v174 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
            }
            if ( v29 && StringCchPrintfW((unsigned __int16 *)&v255, 0x15u, L"%llu", *(_QWORD *)(*v10 + 272LL)) >= 0 )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)v236, (const unsigned __int16 *const)&v255);
              v30 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v175);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v231, L"PackageRankId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v176,
                &v231,
                v30);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
            }
            winrt::param::hstring::hstring((winrt::param::hstring *)v236, L"PackageFullNameId");
            if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                     &v176,
                                     v236)
              || (winrt::param::hstring::hstring(
                    (winrt::param::hstring *)&v231,
                    (const unsigned __int16 *const)&dword_18023C12C),
                  winrt::param::hstring::hstring((winrt::param::hstring *)v234, L"PackageFullNameId"),
                  v12 |= 0x20u,
                  v174 = v12,
                  v31 = 0,
                  !*(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                                &v176,
                                &v175,
                                v234,
                                &v231)) )
            {
              v31 = 1;
            }
            if ( (v12 & 0x20) != 0 )
            {
              v12 &= ~0x20u;
              v174 = v12;
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
            }
            if ( v31 )
            {
              v236[0] = *(_QWORD *)(*v10 + 200LL);
              v32 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v175);
              winrt::param::hstring::hstring((winrt::param::hstring *)&v231, L"PackageFullNameId");
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v176,
                &v231,
                v32);
              winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
            }
          }
          v33 = (char *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(
                          &v176,
                          &v175);
          if ( v214 != v33 )
          {
            v34 = *(_QWORD *)v33;
            *(_QWORD *)v33 = 0;
            winrt::handle_type<winrt::impl::hstring_traits>::attach(v214, v34);
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
          winrt::hstring::operator=(&v187, v214);
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v176);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v214);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v188);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x5F9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp",
        "Failed to merge packageRank and packageFullName into mutableFulfillmentData",
        (const char *)v159);
      v12 = v174;
      v196 = v206;
      v192 = v198;
      v10 = v207;
      v205 = v207;
      v9 = (CorrelationVector *)v199[0];
      v185 = (CorrelationVector *)v199[0];
      v11 = v195;
    }
  }
  *(_OWORD *)v208 = 0;
  v209 = 0;
  *(_OWORD *)v200 = 0;
  v35 = 0;
  v188 = 0;
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(v191, &v204);
  if ( *(int *)(*v10 + 296LL) < 0 && *(_QWORD *)(*v10 + 120LL) == *(_QWORD *)(*v10 + 112LL) )
  {
    v149 = (const struct winrt::hstring *)(winrt::com_ptr<IUniversalOrchestrator>::operator->(v10) + 24);
    winrt::hstring::hstring((winrt::hstring *)&v181, v149);
    v182 = (std::_Ref_count_base *)*(unsigned int *)(winrt::com_ptr<IUniversalOrchestrator>::operator->(v10) + 296);
    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
      &v180,
      L"Not able to create install service work due to product unfulfillable");
    std::string::string(v234, "InstallQueue2::CreateWorkForCatalogItem");
    std::string::string(&v231, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::Log<Logging::ErrorCode>((unsigned int)&v231, 1542, (unsigned int)v234, 1, (__int64)&v180, (__int64)&v181);
    std::string::~string(&v231);
    std::string::~string(v234);
    PluginHelpers::WorkProperty::VolumePath::~VolumePath((PluginHelpers::WorkProperty::VolumePath *)&v181);
    winrt::impl::slim_source_location::current(&v231);
    v150 = winrt::com_ptr<IUniversalOrchestrator>::operator->(v10);
    v151 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v179, *(_DWORD *)(v150 + 296));
    winrt::hresult_error::hresult_error(pExceptionObject, *v151, v152);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  v37 = *v10;
  if ( !*(_BYTE *)(*v10 + 284LL)
    || (CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v177),
        v12 |= 0x40u,
        IsPluginAvailable = PluginHelpers::IsPluginAvailable(
                              (PluginHelpers *)v177,
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
    winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
  }
  if ( v40 )
  {
    std::make_pair<unsigned short const (&)[11],winrt::hstring &>(v210, v36, &v186);
    v193 = (__int64)L"Plugin available, Creating Work for Catalog Item";
    v194 = (std::_Ref_count_base *)48;
    std::string::string(v252, "InstallQueue2::CreateWorkForCatalogItem");
    std::string::string(&v231, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>(
      (unsigned int)v254,
      (unsigned int)&v231,
      v41,
      (unsigned int)v252,
      v162,
      (__int64)&v193,
      (__int64)v9,
      (__int64)v11,
      (__int64)v220,
      (__int64)v210);
    v12 |= 0x400u;
    std::string::~string(&v231);
    std::string::~string(v252);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl'::`2'::impl) )
    {
      v42 = *v10;
      if ( v187 )
      {
LABEL_88:
        CreateInstallServiceWorkByPlugin(
          (winrt::Windows::Foundation::IUnknown *)v234,
          v9,
          v11,
          (struct winrt::hstring *)(v42 + 152),
          (struct winrt::hstring *)&v187,
          (__int64)&v186);
LABEL_89:
        v255 = (struct winrt::hstring *)v234[0];
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v255);
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v256, v10);
        winrt::hstring::hstring((winrt::hstring *)&v178, L"Acquisition");
        *(_QWORD *)v177 = 0;
        v43 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v180, v10);
        CreateCheckPointData(
          (int)v258,
          v43,
          (int)v9,
          (int)v177,
          v11,
          (__int64)&v234[1],
          (__int64)v235,
          (__int64)&v186,
          v184,
          (__int64)&v178);
        std::vector<InstallQueue2::Data>::push_back(v208, &v255);
        InstallQueue2::Data::~Data((InstallQueue2::Data *)&v255);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
LABEL_94:
        std::tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::~tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>(v234);
        Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo &,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v254);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v211);
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
          (winrt::Windows::Foundation::IUnknown *)v234,
          v9,
          v11,
          (struct winrt::hstring *)(v42 + 152),
          (struct winrt::hstring *)(v42 + 160),
          (__int64)&v186);
        v255 = (struct winrt::hstring *)v234[0];
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v255);
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v256, v10);
        winrt::hstring::hstring((winrt::hstring *)&v178, L"Acquisition");
        *(_QWORD *)v177 = 0;
        v45 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v180, v10);
        CreateCheckPointData(
          (int)v258,
          v45,
          (int)v9,
          (int)v177,
          v11,
          (__int64)&v234[1],
          (__int64)v235,
          (__int64)&v186,
          v184,
          (__int64)&v178);
        std::vector<InstallQueue2::Data>::push_back(v208, &v255);
        InstallQueue2::Data::~Data((InstallQueue2::Data *)&v255);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
        goto LABEL_94;
      }
      if ( v187 )
        goto LABEL_88;
    }
    CreateInstallServiceWorkByPlugin(
      (winrt::Windows::Foundation::IUnknown *)v234,
      v9,
      v11,
      (struct winrt::hstring *)(v42 + 152),
      (struct winrt::hstring *)(v42 + 160),
      (__int64)&v186);
    goto LABEL_89;
  }
LABEL_95:
  if ( !*(_BYTE *)(*v10 + 284LL)
    || !(unsigned __int8)winrt::operator==(*v10 + 152LL, L"Microsoft.GamingServices_8wekyb3d8bbwe")
    || (v46 = *v10,
        CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v177),
        v12 |= 0x80u,
        v48 = PluginHelpers::IsPluginAvailable((PluginHelpers *)v177, (const struct winrt::hstring *)(v46 + 152), v47),
        v49 = 1,
        v48) )
  {
    v49 = 0;
  }
  if ( (v12 & 0x80u) != 0 )
  {
    v12 &= ~0x80u;
    winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
  }
  if ( v49 )
  {
    std::shared_ptr<CheckpointData::Data>::operator=(v200, v10);
    winrt::hstring::operator=(&v204, &v186);
  }
  else
  {
    v62 = *(_QWORD *)(*v10 + 112LL);
    v63 = *(struct winrt::hstring **)(*v10 + 120LL);
    v175 = v63;
    while ( (struct winrt::hstring *)v62 != v63 )
    {
      Singleton = CatalogDataStore::GetSingleton();
      std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v247, Singleton);
      winrt::hstring::hstring((winrt::hstring *)v177, L"StoreId");
      v65 = (unsigned int)CorrelationVector::Increment(v9);
      CatalogDataStore::LookupForUser(
        v247,
        (unsigned int)&v181,
        v65,
        (_DWORD)v11,
        (__int64)v197,
        (__int64)v215,
        (__int64)v177,
        v62,
        0);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
      if ( !(unsigned __int8)winrt::operator==(v181 + 152, L"Microsoft.GamingServices_8wekyb3d8bbwe")
        || (v66 = v181,
            CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)&v178),
            v12 |= 0x100u,
            v68 = PluginHelpers::IsPluginAvailable(
                    (PluginHelpers *)&v178,
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
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
      }
      if ( v69 )
      {
        std::shared_ptr<CheckpointData::Data>::operator=(v200, &v181);
        v70 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v180, v200);
        JointWorkPropertiesJSON = (__int64 *)CreateJointWorkPropertiesJSON(
                                               (unsigned int)&v175,
                                               v70,
                                               (_DWORD)v203,
                                               v184,
                                               v71);
        if ( &v204 != JointWorkPropertiesJSON )
        {
          v73 = *JointWorkPropertiesJSON;
          *JointWorkPropertiesJSON = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v204, v73);
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
        if ( v182 )
          std::_Ref_count_base::_Decref(v182);
        if ( v248 )
          std::_Ref_count_base::_Decref(v248);
        break;
      }
      if ( v182 )
        std::_Ref_count_base::_Decref(v182);
      if ( v248 )
        std::_Ref_count_base::_Decref(v248);
      v62 += 8;
      v63 = v175;
      v9 = v185;
    }
  }
  v50 = v185;
  if ( v200[0] )
  {
    LODWORD(v176) = 0;
    v51 = CorrelationVector::Increment(v185);
    *(_OWORD *)v237 = *(_OWORD *)((char *)v51 + 8);
    v238 = *(_OWORD *)((char *)v51 + 24);
    v239 = *(_OWORD *)((char *)v51 + 40);
    v240 = *(_OWORD *)((char *)v51 + 56);
    v241 = *(_OWORD *)((char *)v51 + 72);
    v242 = *(_OWORD *)((char *)v51 + 88);
    v243 = *(_OWORD *)((char *)v51 + 104);
    v244 = *(_OWORD *)((char *)v51 + 120);
    v245 = *((_BYTE *)v51 + 136);
    winrt::hstring::hstring((winrt::hstring *)&v246, (struct CorrelationVector *)((char *)v51 + 144));
    v12 |= 0x800u;
    v35 = winrt::impl::create_and_initialize<ChainedInstallServiceWork,unsigned short const (&)[18],winrt::hstring &,CorrelationVector::Stringified,CallerContext2 const &,enum winrt::Windows::Internal::InstallService::Plugin::InstallServiceWorkPriority &,int>(
            L"PackageFamilyName",
            (__int64)&v179,
            (__int64)&v176);
    v188 = v35;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v246);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UACStateTransitionTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UACStateTransitionTelemetry>::GetImpl'::`2'::impl) )
    {
      v52 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateStateTransitionForUAC>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UpdateStateTransitionForUAC>::GetImpl'::`2'::impl);
      v183 = (struct winrt::hstring *)(*(_QWORD *)v190 + 144LL);
      if ( v52 )
      {
        v53 = winrt::hstring::c_str((std::_Ref_count_base *)((char *)v200[0] + 24));
        v55 = winrt::hstring::c_str((winrt::hstring *)(v54 + 32));
        v57 = winrt::hstring::c_str((winrt::hstring *)(v56 + 152));
        *(_OWORD *)v237 = *(_OWORD *)(v202 + 8);
        v238 = *(_OWORD *)(v202 + 24);
        v239 = *(_OWORD *)(v202 + 40);
        v240 = *(_OWORD *)(v202 + 56);
        v241 = *(_OWORD *)(v202 + 72);
        v242 = *(_OWORD *)(v202 + 88);
        v243 = *(_OWORD *)(v202 + 104);
        v244 = *(_OWORD *)(v202 + 120);
        v245 = *(_BYTE *)(v202 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v246, v58);
        v59 = winrt::hstring::c_str((winrt::hstring *)v197);
        v60 = v55;
        v11 = v195;
        v61 = CallerContext2::CheckElevationRequirement(v195, v53, v60, v59, v57, v237);
      }
      else
      {
        v74 = v202;
        *(_OWORD *)v237 = *(_OWORD *)(v202 + 8);
        v238 = *(_OWORD *)(v202 + 24);
        v239 = *(_OWORD *)(v202 + 40);
        v240 = *(_OWORD *)(v202 + 56);
        v241 = *(_OWORD *)(v202 + 72);
        v242 = *(_OWORD *)(v202 + 88);
        v243 = *(_OWORD *)(v202 + 104);
        v244 = *(_OWORD *)(v202 + 120);
        v245 = *(_BYTE *)(v202 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v246, (const struct winrt::hstring *)(*(_QWORD *)v190 + 144LL));
        winrt::hstring::c_str((std::_Ref_count_base *)((char *)v200[0] + 152));
        winrt::hstring::c_str((winrt::hstring *)v197);
        winrt::hstring::c_str((winrt::hstring *)(v75 + 32));
        v77 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v76 + 24));
        LOBYTE(v167) = 0;
        WindowsUpdate::CommonTelemetry::StateTransition(
          v77,
          v78,
          v79,
          v80,
          0,
          "FulfillmentInitiate",
          "UACOpen",
          v167,
          0,
          (__int64)v237,
          v171);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v246);
        v61 = CallerContext2::CheckElevationRequirement(v11, 0, 0, 0, 0, 0);
        *(_OWORD *)v237 = *(_OWORD *)(v74 + 8);
        v238 = *(_OWORD *)(v74 + 24);
        v239 = *(_OWORD *)(v74 + 40);
        v240 = *(_OWORD *)(v74 + 56);
        v241 = *(_OWORD *)(v74 + 72);
        v242 = *(_OWORD *)(v74 + 88);
        v243 = *(_OWORD *)(v74 + 104);
        v244 = *(_OWORD *)(v74 + 120);
        v245 = *(_BYTE *)(v74 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v246, v183);
        winrt::hstring::c_str((std::_Ref_count_base *)((char *)v200[0] + 152));
        winrt::hstring::c_str((winrt::hstring *)v197);
        winrt::hstring::c_str((winrt::hstring *)(v81 + 32));
        v83 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v82 + 24));
        LOBYTE(v168) = 0;
        WindowsUpdate::CommonTelemetry::StateTransition(
          v83,
          v84,
          v85,
          v86,
          0,
          (const unsigned __int16 *)"UACOpen",
          "UACClose",
          v168,
          !v61 ? 0x13 : 0,
          (__int64)v237,
          v172);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v246);
      if ( !v61 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HResultForElevationDenied>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HResultForElevationDenied>::GetImpl'::`2'::impl) )
        {
          std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
            &v180,
            L"The user declined the UAC prompt");
          std::string::string(v234, "InstallQueue2::CreateWorkForCatalogItem");
          std::string::string(&v231, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::Log<>((unsigned int)&v231, 1668, (unsigned int)v234, 3, (__int64)&v180);
          std::string::~string(&v231);
          std::string::~string(v234);
          winrt::impl::slim_source_location::current(&v231);
          v153 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v179, -2143309549);
          winrt::hresult_error::hresult_error(v226, *v153, v154);
          throw (winrt::hresult_error *)v226;
        }
        v155 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v231);
        winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v227, v155);
        throw (winrt::hresult_access_denied *)v227;
      }
      v50 = v185;
    }
    else if ( !CallerContext2::CheckElevationRequirement(v11, 0, 0, 0, 0, 0) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HResultForElevationDenied>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HResultForElevationDenied>::GetImpl'::`2'::impl) )
      {
        std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
          &v180,
          L"The user declined the UAC prompt");
        std::string::string(v234, "InstallQueue2::CreateWorkForCatalogItem");
        std::string::string(&v231, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
        Logging::Log<>((unsigned int)&v231, 1684, (unsigned int)v234, 3, (__int64)&v180);
        std::string::~string(&v231);
        std::string::~string(v234);
        winrt::impl::slim_source_location::current(&v231);
        v156 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v179, -2143309549);
        winrt::hresult_error::hresult_error(v228, *v156, v157);
        throw (winrt::hresult_error *)v228;
      }
      v158 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v231);
      winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v229, v158);
      throw (winrt::hresult_access_denied *)v229;
    }
    v87 = *(_QWORD *)CatalogDataStore::GetSingleton();
    winrt::hstring::hstring((winrt::hstring *)&v179, L"PackageFamilyName");
    v88 = (unsigned int)CorrelationVector::Increment(v50);
    CatalogDataStore::LookupForUser(
      v87,
      (unsigned int)&v181,
      v88,
      (_DWORD)v11,
      (__int64)v215,
      (__int64)v197,
      (__int64)&v179,
      (__int64)v200[0] + 152,
      0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v179);
    v181[280] = 1;
    v236[0] = v204;
    winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v177);
    BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&v183);
    v193 = (__int64)L"IsInstallServicePlugin";
    v194 = (std::_Ref_count_base *)22;
    winrt::param::hstring::hstring(&v231, &v193);
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      v177,
      &v231,
      BooleanValue);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v183);
    v90 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v189);
    v193 = (__int64)L"RequiresElevation";
    v194 = (std::_Ref_count_base *)17;
    winrt::param::hstring::hstring(&v231, &v193);
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      v177,
      &v231,
      v90);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v189);
    winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonArray>::Stringify(v177, &v178);
    PluginHelpers::ParseCreateWorkProperties((PluginHelpers *)&v175, (const struct winrt::hstring *)&v178);
    std::make_pair<unsigned short const (&)[11],winrt::hstring &>(v210, v91, &v178);
    winrt::hstring::hstring((winrt::hstring *)&v247, L"StoreId");
    winrt::hstring::hstring((winrt::hstring *)&v248, (std::_Ref_count_base *)((char *)v200[0] + 24));
    v193 = (__int64)L"Plugin not available, Creating chained Work for Catalog Item";
    v194 = (std::_Ref_count_base *)60;
    std::string::string(v234, "InstallQueue2::CreateWorkForCatalogItem");
    std::string::string(&v231, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
    Logging::TraceActivity_CorrelationVector___CallerContext2_const___Logging::CatalogSearchInfo_std::pair_unsigned_short_const___winrt::hstring__const___(
      (unsigned int)v253,
      (unsigned int)&v231,
      1705,
      (unsigned int)v234,
      v163,
      (__int64)&v193,
      (__int64)v50,
      (__int64)v11,
      (__int64)&v247,
      (__int64)v210);
    std::string::~string(&v231);
    std::string::~string(v234);
    Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)&v247);
    v92 = CreateUWAPlugin(&v176);
    v179 = 0;
    v236[0] = *((_QWORD *)v181 + 20);
    v231 = *(struct winrt::hstring **)CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v189);
    v93 = CorrelationVector::Increment(v50);
    *(_OWORD *)v237 = *(_OWORD *)((char *)v93 + 8);
    v238 = *(_OWORD *)((char *)v93 + 24);
    v239 = *(_OWORD *)((char *)v93 + 40);
    v240 = *(_OWORD *)((char *)v93 + 56);
    v241 = *(_OWORD *)((char *)v93 + 72);
    v242 = *(_OWORD *)((char *)v93 + 88);
    v243 = *(_OWORD *)((char *)v93 + 104);
    v244 = *(_OWORD *)((char *)v93 + 120);
    v245 = *((_BYTE *)v93 + 136);
    winrt::hstring::hstring((winrt::hstring *)&v246, (struct CorrelationVector *)((char *)v93 + 144));
    if ( !v246 )
    {
      _o_mbstowcs_s(0, v254, 129, v237, 129);
      winrt::hstring::operator=(&v246, v254);
    }
    v234[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v183, (const struct winrt::hstring *)&v246);
    winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServicePlugin<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>::CreateInstallServiceWork(
      v92,
      (unsigned int)v201,
      (unsigned int)v234,
      (unsigned int)&v231,
      (__int64)v236,
      (__int64)&v175,
      (__int64)&v179);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v183);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v246);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v189);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v179);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v176);
    v94 = v181 + 160;
    v95 = v181 + 152;
    v179 = *(struct winrt::hstring **)v201;
    winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v179);
    ChainedInstallServiceWork::AddWorkItem(v35, &v179, v95, v94, &v178);
    v96 = v200[0];
    v97 = (std::_Ref_count_base *)((char *)v200[0] + 160);
    winrt::hstring::hstring((winrt::hstring *)&v179, L"PackageFamilyName");
    ChainedInstallServiceWork::AddWorkItem(
      (ChainedInstallServiceWork *)v35,
      (const struct winrt::hstring *)&v179,
      (std::_Ref_count_base *)((char *)v96 + 32),
      (std::_Ref_count_base *)((char *)v96 + 152),
      v97,
      (const struct winrt::hstring *)&v178);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v179);
    v183 = (struct winrt::hstring *)(v35 + 16);
    v255 = (struct winrt::hstring *)(v35 + 16);
    winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v255);
    std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v256, v200);
    winrt::hstring::hstring((winrt::hstring *)v189, L"Acquisition");
    winrt::hstring::hstring((winrt::hstring *)&v176, L"ChainedWork");
    v179 = 0;
    v98 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v180, v200);
    v11 = v195;
    CreateCheckPointData(
      (int)v258,
      v98,
      (int)v50,
      (int)&v179,
      v195,
      (__int64)v97,
      (__int64)&v176,
      (__int64)&v204,
      v184,
      (__int64)v189);
    std::vector<InstallQueue2::Data>::push_back(v208, &v255);
    InstallQueue2::Data::~Data((InstallQueue2::Data *)&v255);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v179);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v176);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v189);
    v183 = 0;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v183);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v201);
    Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v253);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v211);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v175);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v177);
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
  }
  v99 = *(const struct winrt::hstring **)(*v10 + 112LL);
  v100 = *(unsigned __int16 **)(*v10 + 120LL);
  v176 = v100;
  while ( v99 != (const struct winrt::hstring *)v100 )
  {
    v101 = CatalogDataStore::GetSingleton();
    std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(&v193, v101);
    winrt::hstring::hstring((winrt::hstring *)&v175, L"StoreId");
    v102 = (unsigned int)CorrelationVector::Increment(v50);
    CatalogDataStore::LookupForUser(
      v193,
      (unsigned int)&v181,
      v102,
      (_DWORD)v11,
      (__int64)v197,
      (__int64)v215,
      (__int64)&v175,
      (__int64)v99,
      0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v175);
    if ( !v200[0] || !(unsigned __int8)winrt::operator==(v181 + 24, (char *)v200[0] + 24) )
    {
      v103 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v252, &v181);
      CreateJointWorkPropertiesJSON((unsigned int)&v178, v103, (_DWORD)v203, v184, v104);
      std::make_pair<unsigned short const (&)[11],winrt::hstring &>(v210, v105, &v178);
      if ( v181[284] && !(unsigned __int8)winrt::operator==(v181 + 24, *v10 + 24LL) )
      {
        v106 = v181;
        CallerContext2::operator winrt::hstring(v11, (winrt::hstring *)v201);
        LOBYTE(v106) = PluginHelpers::IsPluginAvailable(
                         (PluginHelpers *)v201,
                         (const struct winrt::hstring *)(v106 + 152),
                         v107);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v201);
        if ( (_BYTE)v106 )
        {
          winrt::hstring::hstring((winrt::hstring *)v222, L"StoreId");
          winrt::hstring::hstring((winrt::hstring *)v223, v99);
          v224[0] = L"Creating Child Item through plugin";
          v224[1] = 34;
          std::string::string(v236, "InstallQueue2::CreateWorkForCatalogItem");
          std::string::string(&v247, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          v50 = v185;
          Logging::TraceActivity_CorrelationVector___CallerContext2_const___Logging::CatalogSearchInfo_std::pair_unsigned_short_const___winrt::hstring__const___(
            (unsigned int)v253,
            (unsigned int)&v247,
            1734,
            (unsigned int)v236,
            v164,
            (__int64)v224,
            (__int64)v185,
            (__int64)v11,
            (__int64)v222,
            (__int64)v210);
          std::string::~string(&v247);
          std::string::~string(v236);
          Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v222);
          CreateInstallServiceWorkByPlugin(
            (winrt::Windows::Foundation::IUnknown *)&v231,
            v50,
            v11,
            (struct winrt::hstring *)(v181 + 152),
            (struct winrt::hstring *)(v181 + 160),
            (__int64)&v178);
          v255 = v231;
          winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v255);
          std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v256, &v181);
          winrt::hstring::hstring((winrt::hstring *)v189, L"Acquisition");
          v183 = 0;
          v108 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v234, &v181);
          CreateCheckPointData(
            (int)v258,
            v108,
            (int)v50,
            (int)&v183,
            v11,
            (__int64)&v232,
            (__int64)&ticks,
            (__int64)&v178,
            v184,
            (__int64)v189);
          std::vector<InstallQueue2::Data>::push_back(v208, &v255);
          InstallQueue2::Data::~Data((InstallQueue2::Data *)&v255);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v183);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v189);
          std::tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::~tuple<winrt::hstring,winrt::hstring,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>(&v231);
          Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v253);
        }
        else
        {
          winrt::hstring::hstring((winrt::hstring *)v249, L"StoreId");
          winrt::hstring::hstring((winrt::hstring *)&v250, v99);
          *(_QWORD *)&v180 = L"Adding child into existing chained item";
          *((_QWORD *)&v180 + 1) = 39;
          std::string::string(&v231, "InstallQueue2::CreateWorkForCatalogItem");
          std::string::string(v236, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\installqueue2.cpp");
          Logging::TraceActivity_CorrelationVector___CallerContext2_const___Logging::CatalogSearchInfo_std::pair_unsigned_short_const___winrt::hstring__const___(
            (unsigned int)v253,
            (unsigned int)v236,
            1740,
            (unsigned int)&v231,
            v164,
            (__int64)&v180,
            (__int64)v185,
            (__int64)v11,
            (__int64)v249,
            (__int64)v210);
          std::string::~string(v236);
          std::string::~string(&v231);
          Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v249);
          v109 = (const struct winrt::hstring *)(v181 + 160);
          v183 = (struct winrt::hstring *)(v181 + 152);
          v179 = (struct winrt::hstring *)(v181 + 32);
          winrt::hstring::hstring((winrt::hstring *)v177, L"PackageFamilyName");
          ChainedInstallServiceWork::AddWorkItem(
            (ChainedInstallServiceWork *)v35,
            (const struct winrt::hstring *)v177,
            v179,
            v183,
            v109,
            (const struct winrt::hstring *)&v178);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v177);
          Logging::ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>::~ActivityScope<CorrelationVector &,CallerContext2 const &,Logging::CatalogSearchInfo,std::pair<unsigned short const *,winrt::hstring> const &>((Logging::Context *)v253);
          v50 = v185;
        }
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(v211);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v178);
    }
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
    if ( v194 )
      std::_Ref_count_base::_Decref(v194);
    v99 = (const struct winrt::hstring *)((char *)v99 + 8);
    v100 = v176;
  }
  v110 = v202;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v204);
  if ( v35 )
    winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(&v188);
  if ( v200[1] )
    std::_Ref_count_base::_Decref(v200[1]);
  v111 = v196;
  *v196 = 0;
  v111[1] = 0;
  v111[2] = 0;
  LODWORD(v173) = v12 | 0x200;
  v217 = 0;
  v218 = 0;
  v112 = v208[0];
  v113 = v208[1];
  if ( v208[0] != v208[1] )
  {
    v175 = (struct winrt::hstring *)(*(_QWORD *)v190 + 144LL);
    do
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl'::`2'::impl)
        && PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v191)
        && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl'::`2'::impl) )
      {
        *(_QWORD *)v190 = 0;
        tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::start(
          v190,
          v234);
        v114 = *(_OWORD *)v234;
        ticks = _Xtime_get_ticks();
        v115 = *(_QWORD *)std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::EnqueueToWorkingDelayTipData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>,0>>::_Try_emplace<winrt::hstring const &,>(
                            (char *)v192 + 712,
                            v224,
                            *((_QWORD *)v112 + 1) + 24LL);
        *(_OWORD *)(v115 + 24) = v114;
        *(_QWORD *)(v115 + 40) = ticks;
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(v190);
      }
      v193 = *((_QWORD *)v112 + 3);
      v194 = (std::_Ref_count_base *)*((_QWORD *)v112 + 4);
      *((_QWORD *)v112 + 3) = 0;
      *((_QWORD *)v112 + 4) = 0;
      v202 = *(_QWORD *)v112;
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v202);
      v116 = std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(v252, (char *)v112 + 8);
      InstallQueue2::_LockQueueForEdit(v192, v230);
      v165 = (struct winrt::hstring *)v116;
      v117 = v192;
      InstallQueue2::_EnqueueWork(v192, (__int64)v11, (__int64)v165, (__int64)&v202, (__int64)&v193, 0);
      __1__exclusive_lock_with_release_callback_VInstallQueue2__P81_EAAXX_E__UEAA_XZ(v230);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcquisitionEnqueueToWorkingDelayTip>::GetImpl'::`2'::impl)
        && PluginHelpers::WorkProperty::IsInteractive::GetValue((const struct winrt::Windows::Data::Json::JsonObject *)v191)
        && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAcquisitionToWorkingDedupTIP>::GetImpl'::`2'::impl) )
      {
        *(_QWORD *)v190 = 0;
        tip2::tip_test<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>>::start(
          v190,
          &v180);
        v118 = v255;
        v119 = v180;
        ticks = _Xtime_get_ticks();
        winrt::hstring::hstring((winrt::hstring *)v249, v118);
        v250 = v119;
        v251 = ticks;
        v117 = v192;
        std::_Hash<std::_Umap_traits<winrt::hstring,InstallQueue2::EnqueueToWorkingDelayTipData,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>,0>>::emplace<std::pair<winrt::hstring const,InstallQueue2::EnqueueToWorkingDelayTipData>>(
          (char *)v192 + 712,
          v210,
          v249);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v249);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest,TipTests::_tip_AcquisitionEnqueueToWorkingDelayTipTest>,wil::err_returncode_policy>(v190);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhanceFulfillmentInitiateEvent>::GetImpl'::`2'::impl) )
      {
        InstallQueue2::_LockQueueForRead(v117, &v231);
        *(_OWORD *)v237 = *(_OWORD *)(v110 + 8);
        v238 = *(_OWORD *)(v110 + 24);
        v239 = *(_OWORD *)(v110 + 40);
        v240 = *(_OWORD *)(v110 + 56);
        v241 = *(_OWORD *)(v110 + 72);
        v242 = *(_OWORD *)(v110 + 88);
        v243 = *(_OWORD *)(v110 + 104);
        v244 = *(_OWORD *)(v110 + 120);
        v245 = *(_BYTE *)(v110 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v246, v175);
        LODWORD(v179) = InstallQueue2::GetAvailableOperationsCount(v117, v120);
        *(_QWORD *)v190 = (__int64)(*((_QWORD *)v117 + 46) - *((_QWORD *)v117 + 45)) >> 4;
        *(_QWORD *)v201 = (__int64)(*((_QWORD *)v219 + 34) - *((_QWORD *)v219 + 33)) >> 4;
        v183 = (struct winrt::hstring *)((__int64)(*((_QWORD *)v117 + 37) - *((_QWORD *)v117 + 36)) >> 4);
        LODWORD(v176) = *((_DWORD *)v117 + 54);
        Value = PluginHelpers::WorkProperty::CallerApplicationId::GetValue(&v216, v191);
        ClientAppId = (__int64 *)GetClientAppId(v236, L"Acquisition;", Value);
        v123 = (__int64)ClientAppId;
        if ( (unsigned __int64)ClientAppId[3] > 7 )
          v123 = *ClientAppId;
        v124 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Attributes(
                 v112,
                 v177);
        v125 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkAttributes<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkAttributes>::TelemetryData(
                                   v124,
                                   v189);
        winrt::hstring::c_str(v125);
        winrt::hstring::c_str((winrt::hstring *)(*((_QWORD *)v112 + 1) + 152LL));
        winrt::hstring::c_str((winrt::hstring *)(v126 + 80));
        winrt::hstring::c_str((winrt::hstring *)(v127 + 32));
        v129 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v128 + 24));
        LODWORD(v169) = (_DWORD)v176;
        LODWORD(v166) = 0;
        WindowsUpdate::CommonTelemetry::FulfillmentInitiate(
          v129,
          v132,
          0,
          v131,
          v130,
          v133,
          (const unsigned __int16 *)v166,
          v123,
          v169,
          (int)v183,
          v201[0],
          v190[0],
          (int)v179,
          (__int64)v237,
          v173);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v189);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v177);
        std::wstring::_Tidy_deallocate(v236);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v246);
        shared_lock::~shared_lock((shared_lock *)&v231);
      }
      else
      {
        *(_OWORD *)v237 = *(_OWORD *)(v110 + 8);
        v238 = *(_OWORD *)(v110 + 24);
        v239 = *(_OWORD *)(v110 + 40);
        v240 = *(_OWORD *)(v110 + 56);
        v241 = *(_OWORD *)(v110 + 72);
        v242 = *(_OWORD *)(v110 + 88);
        v243 = *(_OWORD *)(v110 + 104);
        v244 = *(_OWORD *)(v110 + 120);
        v245 = *(_BYTE *)(v110 + 136);
        winrt::hstring::hstring((winrt::hstring *)&v246, v175);
        v134 = PluginHelpers::WorkProperty::CallerApplicationId::GetValue(&v188, v191);
        v135 = (__int64 *)GetClientAppId(v236, L"Acquisition;", v134);
        v136 = (__int64)v135;
        if ( (unsigned __int64)v135[3] > 7 )
          v136 = *v135;
        v137 = winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkItem<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem>::Attributes(
                 v112,
                 &v198);
        v138 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceWorkAttributes<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkAttributes>::TelemetryData(
                                   v137,
                                   v199);
        winrt::hstring::c_str(v138);
        winrt::hstring::c_str((winrt::hstring *)(*((_QWORD *)v112 + 1) + 152LL));
        winrt::hstring::c_str((winrt::hstring *)(v139 + 80));
        winrt::hstring::c_str((winrt::hstring *)(v140 + 32));
        v142 = (WindowsUpdate::CommonTelemetry *)winrt::hstring::c_str((winrt::hstring *)(v141 + 24));
        LODWORD(v166) = 0;
        WindowsUpdate::CommonTelemetry::FulfillmentInitiate(
          v142,
          v145,
          0,
          v144,
          v143,
          v146,
          (const unsigned __int16 *)v166,
          v136,
          (const unsigned __int16 *)v237,
          v170);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v199);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v198);
        std::wstring::_Tidy_deallocate(v236);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v246);
      }
      v111 = v196;
      std::vector<winrt::WindowsUpdate::Internal::InstallItem>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::WindowsUpdate::Internal::InstallItem>>>,0>(
        (_DWORD)v196,
        (unsigned int)&v178,
        v196[1],
        v257,
        *(__int64 *)v258);
      if ( *((_QWORD *)&v217 + 1) == v218 )
      {
        std::vector<std::shared_ptr<InstallQueue2::QueueItem>>::_Emplace_reallocate<std::shared_ptr<InstallQueue2::QueueItem> const &>(
          &v217,
          *((_QWORD *)&v217 + 1),
          &v255);
      }
      else
      {
        std::shared_ptr<NotificationQueue>::shared_ptr<NotificationQueue>(*((_QWORD *)&v217 + 1), &v255);
        *((_QWORD *)&v217 + 1) += 16LL;
      }
      std::tuple<std::vector<winrt::WindowsUpdate::Internal::InstallItem>,std::shared_ptr<InstallQueue2::QueueItem>>::~tuple<std::vector<winrt::WindowsUpdate::Internal::InstallItem>,std::shared_ptr<InstallQueue2::QueueItem>>(&v255);
      v112 = (InstallQueue2::Data *)((char *)v112 + 40);
    }
    while ( v112 != v113 );
    v10 = v205;
  }
  std::vector<std::shared_ptr<NotificationQueue>>::~vector<std::shared_ptr<NotificationQueue>>(&v217);
  if ( v208[0] )
  {
    std::_Destroy_range<std::allocator<InstallQueue2::Data>>(v208[0]);
    std::_Deallocate<16>(v208[0], 8 * ((signed __int64)(v209 - (unsigned __int64)v208[0]) >> 3));
    *(_OWORD *)v208 = 0;
    v209 = 0;
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v187);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v186);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v215);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v197);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v191);
  Logging::CheckpointRecovery::~CheckpointRecovery((Logging::CheckpointRecovery *)v220);
  v147 = (std::_Ref_count_base *)v10[1];
  if ( v147 )
    std::_Ref_count_base::_Decref(v147);
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
