# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::Initialize(void)

- ea: `0x1800ae29c`
- end: `0x1800af7da`
- name: `?Initialize@DeManagementServerSettingsGroupImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@QEAAXXZ`
- size: `5438`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `73`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ab808`

## callees

- `0x180005860`
- `0x1800058bc`
- `0x180009050`
- `0x180009984`
- `0x180009a84`
- `0x180009f68`
- `0x18000f778`
- `0x18000fa0c`
- `0x18000fa98`
- `0x18000fb14`
- `0x180012194`
- `0x1800121d0`
- `0x180012358`
- `0x180012670`
- `0x180013578`
- `0x18001f9d8`
- `0x180024f38`
- `0x18002ab7c`
- `0x18004ad88`
- `0x180062e04`
- `0x180062e90`
- `0x180063074`
- `0x1800630dc`
- `0x180063394`
- `0x180063440`
- `0x1800634ec`
- `0x180063560`
- `0x1800635c0`
- `0x180063c54`
- `0x180066454`
- `0x1800847b4`
- `0x18008e404`
- `0x18009f690`
- `0x18009f708`
- `0x18009f780`
- `0x18009f7f8`
- `0x1800ae29c`
- `0x1800af7e0`
- `0x1800af89c`
- `0x1800af958`
- `0x1800afa14`
- `0x1800afad0`
- `0x1800afb8c`
- `0x1800afc48`
- `0x1800afd04`
- `0x1800afdc0`
- `0x1800afe7c`
- `0x1800aff38`
- `0x1800afff4`
- `0x1800b00b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae34a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae34a`

## string_xrefs

- `0x1800af7c2`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`

## pseudocode

```c
void __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::Initialize(
        Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *this)
{
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  HKEY v5; // rbx
  __int64 v6; // rax
  __int64 v7; // r8
  const WCHAR *v8; // rax
  PHKEY phkResult; // rdx
  unsigned int Key; // eax
  __int64 Shared; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry **v12; // r14
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  std::_Ref_count_base *v16; // rcx
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  std::_Ref_count_base *v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  std::_Ref_count_base *v24; // rcx
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  std::_Ref_count_base *v28; // rcx
  __int64 *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  std::_Ref_count_base *v32; // rcx
  __int64 *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  std::_Ref_count_base *v36; // rcx
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rdx
  std::_Ref_count_base *v40; // rcx
  __int64 *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  std::_Ref_count_base *v44; // rcx
  __int64 *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  std::_Ref_count_base *v48; // rcx
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  std::_Ref_count_base *v52; // rcx
  __int64 *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rdx
  std::_Ref_count_base *v56; // rcx
  __int64 *v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rdx
  std::_Ref_count_base *v60; // rcx
  __int64 *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  std::_Ref_count_base *v64; // rcx
  __int64 *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdx
  std::_Ref_count_base *v68; // rcx
  __int64 *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rdx
  std::_Ref_count_base *v72; // rcx
  __int64 *v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rdx
  std::_Ref_count_base *v76; // rcx
  __int64 *v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rdx
  std::_Ref_count_base *v80; // rcx
  __int64 *v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rdx
  std::_Ref_count_base *v84; // rcx
  __int64 v85; // rax
  std::_Ref_count_base *v86; // rcx
  __int64 v87; // rax
  std::_Ref_count_base *v88; // rcx
  __int64 v89; // rax
  std::_Ref_count_base *v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 *v93; // rax
  __int64 v94; // rcx
  __int64 v95; // rdx
  std::_Ref_count_base *v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 *v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rdx
  std::_Ref_count_base *v102; // rcx
  __int64 v103; // rax
  std::_Ref_count_base *v104; // rcx
  __int64 v105; // rax
  __int64 *v106; // rax
  __int64 v107; // rcx
  __int64 v108; // rdx
  std::_Ref_count_base *v109; // rcx
  __int64 v110; // rax
  _QWORD *v111; // rbx
  __int64 v112; // rax
  __int64 v113; // rax
  std::_Ref_count_base *v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  char v118; // cl
  __int64 v119; // rax
  std::_Ref_count_base *v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  std::_Ref_count_base *v125; // rcx
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 *v129; // rax
  __int64 v130; // rcx
  __int64 v131; // rdx
  std::_Ref_count_base *v132; // rcx
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 **v136; // rbx
  __int64 *v137; // rcx
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 **v140; // rbx
  __int64 *v141; // rcx
  __int64 v142; // rax
  __int64 v143; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v144; // rbx
  __int64 v145; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v146; // rbx
  __int64 v147; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v148; // rbx
  __int64 v149; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v150; // rbx
  __int64 v151; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v152; // rsi
  char v153; // bl
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v154; // rbx
  __int64 v155; // rax
  __int64 DeviceInterfaceId; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v157; // rsi
  char v158; // bl
  __int64 v159; // rax
  bool v160; // si
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v161; // rbx
  __int64 v162; // rax
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry *v163; // rbx
  __int64 v164; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  void **v166; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v167; // [rsp+58h] [rbp-A8h]
  char v168[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v169[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v170[8]; // [rsp+70h] [rbp-90h] BYREF
  void ***v171; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v172; // [rsp+80h] [rbp-80h]
  __int128 v173; // [rsp+88h] [rbp-78h] BYREF
  void ***v174; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v175; // [rsp+A0h] [rbp-60h]
  _QWORD v176[2]; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v178[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v179[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v180[2]; // [rsp+E0h] [rbp-20h] BYREF
  void **v181; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v182; // [rsp+F8h] [rbp-8h]
  int v183; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall **v184)(); // [rsp+120h] [rbp+20h] BYREF
  _QWORD v185[6]; // [rsp+128h] [rbp+28h] BYREF
  __int64 (__fastcall ***v186)(); // [rsp+158h] [rbp+58h]
  __int128 v187; // [rsp+160h] [rbp+60h] BYREF
  __int64 v188; // [rsp+170h] [rbp+70h]
  float v189; // [rsp+178h] [rbp+78h]
  int v190; // [rsp+180h] [rbp+80h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *((_BYTE *)this + 24) = Microsoft::Windows::DisplayEnhancement::Foundation::RegKeyUtils::IsPowerGuidsShimDisabled();
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::GetOrMakeShared(v176);
  Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::GetServiceRegistryStateKey(&hKey);
  v5 = hKey;
  if ( !hKey )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v2, v3, v4);
  v173 = 0;
  v6 = wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(&v173);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 568, v6, v7);
  Key = RegCreateKeyExW(v5, v8, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagements"
                    "erversettingsgroup.cpp",
      (const char *)Key,
      dwOptions);
  Shared = Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(&v166, (char *)this + 568);
  v12 = (Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry **)((char *)this + 632);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (char *)this + 632,
    Shared);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  LOBYTE(v167) = 1;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v13 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<0>::Make(
                     &v171,
                     &v173,
                     &v166);
  v14 = *v13;
  v15 = v13[1];
  *v13 = 0;
  v13[1] = 0;
  *((_QWORD *)this + 4) = v14;
  v16 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v15;
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v17 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<1>::Make(
                     &v171,
                     &v173,
                     &v166);
  v18 = *v17;
  v19 = v17[1];
  *v17 = 0;
  v17[1] = 0;
  *((_QWORD *)this + 6) = v18;
  v20 = (std::_Ref_count_base *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v19;
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  DWORD2(v187) = 0;
  v188 = 0;
  v189 = FLOAT_6500_0;
  v190 = 1;
  *(_QWORD *)&v187 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementTransitionSettingType::`vftable';
  v21 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<2>::Make(
                     &v166,
                     &v173,
                     &v187);
  v22 = *v21;
  v23 = v21[1];
  *v21 = 0;
  v21[1] = 0;
  *((_QWORD *)this + 8) = v22;
  v24 = (std::_Ref_count_base *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v23;
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  v182 = (std::_Ref_count_base *)0x3EA8754F3EA01B86LL;
  v183 = 1;
  v181 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementChromaticityXYSettingType::`vftable';
  v25 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<3>::Make(
                     &v166,
                     &v173,
                     &v181);
  v26 = *v25;
  v27 = v25[1];
  *v25 = 0;
  v25[1] = 0;
  *((_QWORD *)this + 10) = v26;
  v28 = (std::_Ref_count_base *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = v27;
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  v182 = (std::_Ref_count_base *)0x3EA8754F3EA01B86LL;
  v183 = 1;
  v181 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementChromaticityXYSettingType::`vftable';
  v29 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<4>::Make(
                     &v166,
                     &v173,
                     &v181);
  v30 = *v29;
  v31 = v29[1];
  *v29 = 0;
  v29[1] = 0;
  *((_QWORD *)this + 12) = v30;
  v32 = (std::_Ref_count_base *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = v31;
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  v167 = (std::_Ref_count_base *)(Microsoft::Windows::DisplayEnhancement::Foundation::TimeHelpers::GetSecondsSinceEpoch()
                                | 0x400000000LL);
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v33 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<5>::Make(
                     &v171,
                     &v173,
                     &v166);
  v34 = *v33;
  v35 = v33[1];
  *v33 = 0;
  v33[1] = 0;
  *((_QWORD *)this + 14) = v34;
  v36 = (std::_Ref_count_base *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v35;
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v37 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<6>::Make(
                     &v171,
                     &v173,
                     &v166);
  v38 = *v37;
  v39 = v37[1];
  *v37 = 0;
  v37[1] = 0;
  *((_QWORD *)this + 16) = v38;
  v40 = (std::_Ref_count_base *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = v39;
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v41 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<7>::Make(
                     &v171,
                     &v173,
                     &v166);
  v42 = *v41;
  v43 = v41[1];
  *v41 = 0;
  v41[1] = 0;
  *((_QWORD *)this + 18) = v42;
  v44 = (std::_Ref_count_base *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = v43;
  if ( v44 )
    std::_Ref_count_base::_Decref(v44);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = *(_BYTE *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ****))(*(_QWORD *)v176[0] + 184LL))(
                                         v176[0],
                                         &v174)
                          + 8LL);
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v45 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<8>::Make(
                     &v171,
                     &v173,
                     &v166);
  v46 = *v45;
  v47 = v45[1];
  *v45 = 0;
  v45[1] = 0;
  *((_QWORD *)this + 20) = v46;
  v48 = (std::_Ref_count_base *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = v47;
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  if ( v175 )
    std::_Ref_count_base::_Decref(v175);
  LOBYTE(v167) = *(_BYTE *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ****))(*(_QWORD *)v176[0] + 24LL))(
                                         v176[0],
                                         &v174)
                          + 8LL);
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v49 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<12>::Make(
                     &v171,
                     &v173,
                     &v166);
  v50 = *v49;
  v51 = v49[1];
  *v49 = 0;
  v49[1] = 0;
  *((_QWORD *)this + 28) = v50;
  v52 = (std::_Ref_count_base *)*((_QWORD *)this + 29);
  *((_QWORD *)this + 29) = v51;
  if ( v52 )
    std::_Ref_count_base::_Decref(v52);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  if ( v175 )
    std::_Ref_count_base::_Decref(v175);
  LODWORD(v167) = *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ****))(*(_QWORD *)v176[0] + 192LL))(
                                           v176[0],
                                           &v174)
                            + 8LL);
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v53 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<9>::Make(
                     &v171,
                     &v173,
                     &v166);
  v54 = *v53;
  v55 = v53[1];
  *v53 = 0;
  v53[1] = 0;
  *((_QWORD *)this + 22) = v54;
  v56 = (std::_Ref_count_base *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = v55;
  if ( v56 )
    std::_Ref_count_base::_Decref(v56);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  if ( v175 )
    std::_Ref_count_base::_Decref(v175);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v57 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<10>::Make(
                     &v171,
                     &v173,
                     &v166);
  v58 = *v57;
  v59 = v57[1];
  *v57 = 0;
  v57[1] = 0;
  *((_QWORD *)this + 24) = v58;
  v60 = (std::_Ref_count_base *)*((_QWORD *)this + 25);
  *((_QWORD *)this + 25) = v59;
  if ( v60 )
    std::_Ref_count_base::_Decref(v60);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v61 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<11>::Make(
                     &v171,
                     &v173,
                     &v166);
  v62 = *v61;
  v63 = v61[1];
  *v61 = 0;
  v61[1] = 0;
  *((_QWORD *)this + 26) = v62;
  v64 = (std::_Ref_count_base *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = v63;
  if ( v64 )
    std::_Ref_count_base::_Decref(v64);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v65 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<13>::Make(
                     &v171,
                     &v173,
                     &v166);
  v66 = *v65;
  v67 = v65[1];
  *v65 = 0;
  v65[1] = 0;
  *((_QWORD *)this + 30) = v66;
  v68 = (std::_Ref_count_base *)*((_QWORD *)this + 31);
  *((_QWORD *)this + 31) = v67;
  if ( v68 )
    std::_Ref_count_base::_Decref(v68);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  v167 = (std::_Ref_count_base *)0x33F800000LL;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v69 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<18>::Make(
                     &v171,
                     &v173,
                     &v166);
  v70 = *v69;
  v71 = v69[1];
  *v69 = 0;
  v69[1] = 0;
  *((_QWORD *)this + 40) = v70;
  v72 = (std::_Ref_count_base *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = v71;
  if ( v72 )
    std::_Ref_count_base::_Decref(v72);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  v167 = (std::_Ref_count_base *)0x400000032LL;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v73 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<21>::Make(
                     &v171,
                     &v173,
                     &v166);
  v74 = *v73;
  v75 = v73[1];
  *v73 = 0;
  v73[1] = 0;
  *((_QWORD *)this + 47) = v74;
  v76 = (std::_Ref_count_base *)*((_QWORD *)this + 48);
  *((_QWORD *)this + 48) = v75;
  if ( v76 )
    std::_Ref_count_base::_Decref(v76);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  v167 = (std::_Ref_count_base *)0x400000032LL;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v77 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<22>::Make(
                     &v171,
                     &v173,
                     &v166);
  v78 = *v77;
  v79 = v77[1];
  *v77 = 0;
  v77[1] = 0;
  *((_QWORD *)this + 49) = v78;
  v80 = (std::_Ref_count_base *)*((_QWORD *)this + 50);
  *((_QWORD *)this + 50) = v79;
  if ( v80 )
    std::_Ref_count_base::_Decref(v80);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v81 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<23>::Make(
                     &v171,
                     &v173,
                     &v166);
  v82 = *v81;
  v83 = v81[1];
  *v81 = 0;
  v81[1] = 0;
  *((_QWORD *)this + 51) = v82;
  v84 = (std::_Ref_count_base *)*((_QWORD *)this + 52);
  *((_QWORD *)this + 52) = v83;
  if ( v84 )
    std::_Ref_count_base::_Decref(v84);
  if ( v172 )
    std::_Ref_count_base::_Decref(v172);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v174 = &v166;
  v168[0] = 0;
  v169[0] = 0;
  v170[0] = 0;
  v171 = (void ***)operator new(0xE0u);
  v85 = std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<24>>::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<24>>(
          (_DWORD)v171,
          (unsigned int)&v173,
          (unsigned int)&v166,
          (unsigned int)v170,
          (__int64)v169,
          (__int64)v168);
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
  *((_QWORD *)this + 53) = v85 + 16;
  v86 = (std::_Ref_count_base *)*((_QWORD *)this + 54);
  *((_QWORD *)this + 54) = v85;
  if ( v86 )
    std::_Ref_count_base::_Decref(v86);
  v167 = (std::_Ref_count_base *)0x47FFFFFFFLL;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v171 = &v166;
  v170[0] = 0;
  v169[0] = 0;
  v168[0] = 0;
  v174 = (void ***)operator new(0xE0u);
  v87 = std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<25>>::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<25>>(
          (_DWORD)v174,
          (unsigned int)&v173,
          (unsigned int)&v166,
          (unsigned int)v168,
          (__int64)v169,
          (__int64)v170);
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
  *((_QWORD *)this + 55) = v87 + 16;
  v88 = (std::_Ref_count_base *)*((_QWORD *)this + 56);
  *((_QWORD *)this + 56) = v87;
  if ( v88 )
    std::_Ref_count_base::_Decref(v88);
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v171 = &v166;
  v170[0] = 0;
  v169[0] = 0;
  v168[0] = 0;
  v174 = (void ***)operator new(0xE0u);
  v89 = std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<26>>::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<26>>(
          (_DWORD)v174,
          (unsigned int)&v173,
          (unsigned int)&v166,
          (unsigned int)v168,
          (__int64)v169,
          (__int64)v170);
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
  *((_QWORD *)this + 57) = v89 + 16;
  v90 = (std::_Ref_count_base *)*((_QWORD *)this + 58);
  *((_QWORD *)this + 58) = v89;
  if ( v90 )
    std::_Ref_count_base::_Decref(v90);
  v91 = std::wstring::wstring(&v187, &dword_180100DC4);
  v92 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementWstringSettingType::DeManagementWstringSettingType(
          &v184,
          v91);
  v93 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<27>::Make(
                     &v166,
                     &v173,
                     v92);
  v94 = *v93;
  v95 = v93[1];
  *v93 = 0;
  v93[1] = 0;
  *((_QWORD *)this + 59) = v94;
  v96 = (std::_Ref_count_base *)*((_QWORD *)this + 60);
  *((_QWORD *)this + 60) = v95;
  if ( v96 )
    std::_Ref_count_base::_Decref(v96);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  std::wstring::_Tidy_deallocate(&v187);
  v97 = std::wstring::wstring(&v187, &dword_180100DC4);
  v98 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementWstringSettingType::DeManagementWstringSettingType(
          &v184,
          v97);
  v99 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<28>::Make(
                     &v166,
                     &v173,
                     v98);
  v100 = *v99;
  v101 = v99[1];
  *v99 = 0;
  v99[1] = 0;
  *((_QWORD *)this + 61) = v100;
  v102 = (std::_Ref_count_base *)*((_QWORD *)this + 62);
  *((_QWORD *)this + 62) = v101;
  if ( v102 )
    std::_Ref_count_base::_Decref(v102);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  std::wstring::_Tidy_deallocate(&v187);
  v167 = (std::_Ref_count_base *)0x400000000LL;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v171 = &v166;
  v170[0] = 0;
  v169[0] = 0;
  v168[0] = 1;
  v174 = (void ***)operator new(0xE0u);
  v103 = std::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<29>>::_Ref_count_obj2<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingImpl<29>>(
           (_DWORD)v174,
           (unsigned int)&v173,
           (unsigned int)&v166,
           (unsigned int)v168,
           (__int64)v169,
           (__int64)v170);
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<int>::`vftable';
  *((_QWORD *)this + 63) = v103 + 16;
  v104 = (std::_Ref_count_base *)*((_QWORD *)this + 64);
  *((_QWORD *)this + 64) = v103;
  if ( v104 )
    std::_Ref_count_base::_Decref(v104);
  v187 = 0;
  v188 = 0;
  v105 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementAutobrightnessBiasVectorSettingType::DeManagementAutobrightnessBiasVectorSettingType(
           &v181,
           &v187);
  v106 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<30>::Make(
                      &v166,
                      &v173,
                      v105);
  v107 = *v106;
  v108 = v106[1];
  *v106 = 0;
  v106[1] = 0;
  *((_QWORD *)this + 65) = v107;
  v109 = (std::_Ref_count_base *)*((_QWORD *)this + 66);
  *((_QWORD *)this + 66) = v108;
  if ( v109 )
    std::_Ref_count_base::_Decref(v109);
  if ( v167 )
    std::_Ref_count_base::_Decref(v167);
  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v176[0] + 32LL))(v176[0], v180);
  *((_BYTE *)this + 25) = *(_BYTE *)(v180[0] + 12LL);
  Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)&v174,
    (Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *)((char *)this + 336));
  if ( *((_BYTE *)this + 25) )
  {
    LODWORD(v167) = *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***))(*(_QWORD *)v176[0] + 32LL))(
                                             v176[0],
                                             &v181)
                              + 8LL);
    HIDWORD(v167) = 4;
    v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    v110 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<19>::Make(
             &v171,
             &v173,
             &v166);
    v111 = (_QWORD *)((char *)this + 344);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 344,
      v110);
    if ( v172 )
      std::_Ref_count_base::_Decref(v172);
    goto LABEL_106;
  }
  v111 = (_QWORD *)((char *)this + 344);
  if ( *((_BYTE *)this + 24) )
  {
    v167 = (std::_Ref_count_base *)0x400000064LL;
    v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    v115 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<19>::Make(
             &v181,
             &v173,
             &v166);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 344,
      v115);
LABEL_106:
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
    v112 = (**(__int64 (__fastcall ***)(_QWORD, void ***))*v111)(*v111, &v181);
    v113 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<20>::Make(
             &v166,
             &v173,
             v112);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 360,
      v113);
    v114 = v167;
    goto LABEL_114;
  }
  v184 = off_1800F5680;
  v185[0] = this;
  v186 = &v184;
  v116 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<19>::Make(
           &v181,
           &v173,
           &v184);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (char *)this + 344,
    v116);
  if ( v182 )
    std::_Ref_count_base::_Decref(v182);
  v184 = off_1800F5650;
  v185[0] = this;
  v186 = &v184;
  v117 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<20>::Make(
           &v181,
           &v173,
           &v184);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (char *)this + 360,
    v117);
  v114 = v182;
LABEL_114:
  if ( v114 )
    std::_Ref_count_base::_Decref(v114);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v174);
  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v176[0] + 8LL))(v176[0], v179);
  v118 = *(_BYTE *)(v179[0] + 12LL);
  *((_BYTE *)this + 26) = v118;
  if ( v118 )
  {
    *(float *)&v167 = (float)*(int *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ****))(*(_QWORD *)v176[0] + 8LL))(
                                                   v176[0],
                                                   &v171)
                                    + 8LL)
                    / 100.0;
    HIDWORD(v167) = 3;
    v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    v119 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<17>::Make(
             &v181,
             &v173,
             &v166);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 304,
      v119);
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
    v120 = v172;
    goto LABEL_122;
  }
  if ( *((_BYTE *)this + 24) )
  {
    v167 = (std::_Ref_count_base *)0x33F4CCCCDLL;
    v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    v121 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<17>::Make(
             &v181,
             &v173,
             &v166);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 304,
      v121);
    v120 = v182;
LABEL_122:
    if ( v120 )
      std::_Ref_count_base::_Decref(v120);
    goto LABEL_126;
  }
  v184 = off_1800F5620;
  v185[0] = this;
  v186 = &v184;
  v122 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<17>::Make(
           &v181,
           &v173,
           &v184);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (char *)this + 304,
    v122);
  if ( v182 )
    std::_Ref_count_base::_Decref(v182);
LABEL_126:
  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v176[0] + 16LL))(v176[0], v178);
  *((_BYTE *)this + 27) = *(_BYTE *)(v178[0] + 12LL);
  if ( *((_BYTE *)this + 26) )
  {
    *(float *)&v167 = (float)*(int *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ****))(*(_QWORD *)v176[0] + 16LL))(
                                                   v176[0],
                                                   &v171)
                                    + 8LL)
                    / 100.0;
    HIDWORD(v167) = 3;
    v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    v123 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<14>::Make(
             &v181,
             &v173,
             &v166);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 256,
      v123);
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
    if ( v172 )
      std::_Ref_count_base::_Decref(v172);
    *(float *)&v167 = (float)*(int *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ****))(*(_QWORD *)v176[0] + 16LL))(
                                                   v176[0],
                                                   &v171)
                                    + 8LL)
                    / 100.0;
    HIDWORD(v167) = 3;
    v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
    v124 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<15>::Make(
             &v181,
             &v173,
             &v166);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 272,
      v124);
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
    v125 = v172;
  }
  else
  {
    if ( *((_BYTE *)this + 24) )
    {
      v167 = (std::_Ref_count_base *)0x33F800000LL;
      v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
      v126 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<14>::Make(
               &v181,
               &v173,
               &v166);
      std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
        (char *)this + 256,
        v126);
      if ( v182 )
        std::_Ref_count_base::_Decref(v182);
      v167 = (std::_Ref_count_base *)0x33F800000LL;
      v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
      v127 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<15>::Make(
               &v181,
               &v173,
               &v166);
    }
    else
    {
      v184 = off_1800F55F0;
      v185[0] = this;
      v186 = &v184;
      v128 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<14>::Make(
               &v181,
               &v173,
               &v184);
      std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
        (char *)this + 256,
        v128);
      if ( v182 )
        std::_Ref_count_base::_Decref(v182);
      v184 = off_1800F55C0;
      v185[0] = this;
      v186 = &v184;
      v127 = Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<15>::Make(
               &v181,
               &v173,
               &v184);
    }
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 272,
      v127);
    v125 = v182;
  }
  if ( v125 )
    std::_Ref_count_base::_Decref(v125);
  LOBYTE(v175) = 0;
  HIDWORD(v175) = 4;
  v174 = (void ***)&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  LOBYTE(v167) = 0;
  HIDWORD(v167) = 4;
  v166 = &Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable';
  v129 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<16>::Make(
                      &v181,
                      &v173,
                      &v166);
  v130 = *v129;
  v131 = v129[1];
  *v129 = 0;
  v129[1] = 0;
  *((_QWORD *)this + 36) = v130;
  v132 = (std::_Ref_count_base *)*((_QWORD *)this + 37);
  *((_QWORD *)this + 37) = v131;
  if ( v132 )
    std::_Ref_count_base::_Decref(v132);
  if ( v182 )
    std::_Ref_count_base::_Decref(v182);
  if ( !*((_QWORD *)this + 83) )
  {
    v133 = Microsoft::Windows::DisplayEnhancement::LightSensorSelector::LightSensorSelector::Make(&v181, 0);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 664,
      v133);
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
  }
  if ( !*((_QWORD *)this + 87) )
  {
    v134 = Microsoft::Windows::DisplayEnhancement::LightSensorSelector::LightSensorSelector::Make(&v181, 1);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      (char *)this + 696,
      v134);
    if ( v182 )
      std::_Ref_count_base::_Decref(v182);
  }
  v135 = (*(__int64 (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 83) + 8LL))(*((_QWORD *)this + 83), &v181);
  v136 = (__int64 **)((char *)this + 680);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (char *)this + 680,
    v135);
  if ( v182 )
    std::_Ref_count_base::_Decref(v182);
  v137 = *v136;
  v138 = **v136;
  v184 = off_1800F5590;
  v185[0] = this;
  v186 = &v184;
  (*(void (__fastcall **)(__int64 *, __int64 (__fastcall ***)()))(v138 + 16))(v137, &v184);
  std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(&v184);
  v139 = (*(__int64 (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 87) + 8LL))(*((_QWORD *)this + 87), &v181);
  v140 = (__int64 **)((char *)this + 712);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (char *)this + 712,
    v139);
  if ( v182 )
    std::_Ref_count_base::_Decref(v182);
  v141 = *v140;
  v142 = **v140;
  v184 = off_1800F5560;
  v185[0] = this;
  v186 = &v184;
  (*(void (__fastcall **)(__int64 *, __int64 (__fastcall ***)()))(v142 + 16))(v141, &v184);
  std::function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>::~function<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType (void)>(&v184);
  v143 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 8))(*((_QWORD *)this + 8), &v181);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestIsNightLightOn(
    *v12,
    COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(float *)(v143 + 24) - 6500.0) & _xmm) >= 0.00009999999747378752);
  v144 = *v12;
  v145 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 20))(*((_QWORD *)this + 20), &v181);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestIsAdaptiveColorOn(
    v144,
    *(_BYTE *)(v145 + 8));
  v146 = *v12;
  v147 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 63))(*((_QWORD *)this + 63), &v181);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestAbsBiasOffset(v146, *(_DWORD *)(v147 + 8));
  v148 = *v12;
  v149 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 32))(*((_QWORD *)this + 32), &v181);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestBatterySaverMultiplier(
    v148,
    *(float *)(v149 + 8));
  v150 = *v12;
  v151 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 22))(*((_QWORD *)this + 22), &v181);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestAdaptiveColorSlider(
    v150,
    *(_BYTE *)(v151 + 8));
  v152 = *v12;
  v153 = *(_BYTE *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***))(*(_QWORD *)v176[0] + 184LL))(
                                 v176[0],
                                 &v181)
                  + 8LL);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f6d4b31e49e13dc6e69cc23c4cb0d398_Traceguids);
  }
  *((_BYTE *)v152 + 51) = v153;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v181);
  v154 = *v12;
  v155 = (***((__int64 (__fastcall ****)(_QWORD, __int64 (__fastcall ***)()))this + 61))(*((_QWORD *)this + 61), &v184);
  DeviceInterfaceId = Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDeviceInterfaceId(
                        v155,
                        &v181);
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestHasColorSensor(
    v154,
    *(_QWORD *)(DeviceInterfaceId + 16) != 0);
  std::wstring::_Tidy_deallocate(&v181);
  v184 = (__int64 (__fastcall **)())&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<std::wstring>::`vftable';
  std::wstring::_Tidy_deallocate(v185);
  v157 = *v12;
  v158 = *(_BYTE *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***))(*(_QWORD *)v176[0] + 24LL))(v176[0], &v181)
                  + 8LL);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f6d4b31e49e13dc6e69cc23c4cb0d398_Traceguids);
  }
  *((_BYTE *)v157 + 50) = v158;
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v181);
  v159 = (***((__int64 (__fastcall ****)(_QWORD, __int64 (__fastcall ***)()))this + 59))(*((_QWORD *)this + 59), &v184);
  v160 = *(_QWORD *)(Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDeviceInterfaceId(
                       v159,
                       &v181)
                   + 16) != 0;
  std::wstring::_Tidy_deallocate(&v181);
  v184 = (__int64 (__fastcall **)())&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<std::wstring>::`vftable';
  std::wstring::_Tidy_deallocate(v185);
  if ( v160 )
  {
    v161 = *v12;
    v162 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 28))(*((_QWORD *)this + 28), &v181);
    Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestIsAutobrightnessOn(
      v161,
      *(_BYTE *)(v162 + 8));
    v163 = *v12;
    v164 = (***((__int64 (__fastcall ****)(_QWORD, void ***))this + 43))(*((_QWORD *)this + 43), &v181);
    Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestBrightnessSlider(
      v163,
      *(_BYTE *)(v164 + 8));
  }
  Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::CacheLatestHasAls(*v12, v160);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v178);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v179);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v180);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(&v187);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(&v173);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(v176);
}

```

## disassembly

```asm
0x1800ae29c  push    rbp
0x1800ae29e  push    rbx
0x1800ae29f  push    rsi
0x1800ae2a0  push    rdi
0x1800ae2a1  push    r12
0x1800ae2a3  push    r13
0x1800ae2a5  push    r14
0x1800ae2a7  push    r15
0x1800ae2a9  lea     rbp, [rsp-98h]
0x1800ae2b1  sub     rsp, 198h
0x1800ae2b8  mov     rax, cs:__security_cookie
0x1800ae2bf  xor     rax, rsp
0x1800ae2c2  mov     [rbp+0D0h+var_48], rax
0x1800ae2c9  mov     rdi, rcx
0x1800ae2cc  xor     r15d, r15d
0x1800ae2cf  call    ?IsPowerGuidsShimDisabled@RegKeyUtils@Foundation@DisplayEnhancement@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::DisplayEnhancement::Foundation::RegKeyUtils::IsPowerGuidsShimDisabled(void)
0x1800ae2d4  mov     [rdi+18h], al
0x1800ae2d7  lea     rcx, [rbp+0D0h+var_128]
0x1800ae2db  call    ?GetOrMakeShared@OEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VOEMSettingsManager@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManager::GetOrMakeShared(void)
0x1800ae2e0  nop
0x1800ae2e1  lea     rcx, [rbp+0D0h+hKey]
0x1800ae2e5  call    ?GetServiceRegistryStateKey@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4SERVICE_REGISTRY_STATE_TYPE@@K@Z; Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::GetServiceRegistryStateKey(SERVICE_REGISTRY_STATE_TYPE,ulong)
0x1800ae2ea  nop
0x1800ae2eb  mov     rcx, [rbp+0D8h]; this
0x1800ae2f2  mov     rbx, [rbp+0D0h+hKey]
0x1800ae2f6  test    rbx, rbx
0x1800ae2f9  jz      loc_1800AF7D4
0x1800ae2ff  xorps   xmm1, xmm1
0x1800ae302  movdqu  [rbp+0D0h+var_148], xmm1
0x1800ae307  lea     rcx, [rbp+0D0h+var_148]
0x1800ae30b  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(void)
0x1800ae310  mov     rdx, rax
0x1800ae313  lea     rsi, [rdi+238h]
0x1800ae31a  mov     rcx, rsi
0x1800ae31d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ae322  mov     [rsp+1D0h+lpdwDisposition], r15; lpdwDisposition
0x1800ae327  mov     [rsp+1D0h+phkResult], rdx; phkResult
0x1800ae32c  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800ae331  mov     [rsp+1D0h+samDesired], 0F003Fh; samDesired
0x1800ae339  mov     [rsp+1D0h+dwOptions], r15d; unsigned int
0x1800ae33e  xor     r9d, r9d; lpClass
0x1800ae341  xor     r8d, r8d; Reserved
0x1800ae344  mov     rdx, rax; lpSubKey
0x1800ae347  mov     rcx, rbx; hKey
0x1800ae34a  call    cs:__imp_RegCreateKeyExW
0x1800ae350  mov     rcx, [rbp+0D8h]; this
0x1800ae357  test    eax, eax
0x1800ae359  jnz     loc_1800AF7BF
0x1800ae35f  mov     rdx, rsi
0x1800ae362  lea     rcx, [rsp+1D0h+var_180]
0x1800ae367  call    ?GetOrMakeShared@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(std::wstring const &)
0x1800ae36c  lea     r14, [rdi+278h]
0x1800ae373  mov     rdx, rax
0x1800ae376  mov     rcx, r14
0x1800ae379  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800ae37e  mov     rcx, [rsp+1D0h+var_178]; this
0x1800ae383  test    rcx, rcx
0x1800ae386  jz      short loc_1800AE38D
0x1800ae388  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae38d  mov     ebx, 1
0x1800ae392  mov     byte ptr [rsp+1D0h+var_178], bl
0x1800ae396  lea     esi, [rbx+3]
0x1800ae399  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae39d  lea     r12, ??_7DeManagementFloatSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable'
0x1800ae3a4  mov     [rsp+1D0h+var_180], r12
0x1800ae3a9  lea     r8, [rsp+1D0h+var_180]
0x1800ae3ae  lea     rdx, [rbp+0D0h+var_148]
0x1800ae3b2  lea     rcx, [rsp+1D0h+var_158]
0x1800ae3b7  call    ?Make@?$DeManagementServerSetting@$0A@@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$0A@@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementBoolSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<0>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementBoolSettingType,bool,bool,bool)
0x1800ae3bc  mov     rcx, [rax]
0x1800ae3bf  mov     rdx, [rax+8]
0x1800ae3c3  mov     [rax], r15
0x1800ae3c6  mov     [rax+8], r15
0x1800ae3ca  mov     [rdi+20h], rcx
0x1800ae3ce  mov     rcx, [rdi+28h]; this
0x1800ae3d2  mov     [rdi+28h], rdx
0x1800ae3d6  test    rcx, rcx
0x1800ae3d9  jz      short loc_1800AE3E0
0x1800ae3db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae3e0  mov     rcx, [rbp+0D0h+var_150]; this
0x1800ae3e4  test    rcx, rcx
0x1800ae3e7  jz      short loc_1800AE3EE
0x1800ae3e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae3ee  mov     byte ptr [rsp+1D0h+var_178], r15b
0x1800ae3f3  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae3f7  mov     [rsp+1D0h+var_180], r12
0x1800ae3fc  lea     r8, [rsp+1D0h+var_180]
0x1800ae401  lea     rdx, [rbp+0D0h+var_148]
0x1800ae405  lea     rcx, [rsp+1D0h+var_158]
0x1800ae40a  call    ?Make@?$DeManagementServerSetting@$00@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$00@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementBoolSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<1>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementBoolSettingType,bool,bool,bool)
0x1800ae40f  mov     rcx, [rax]
0x1800ae412  mov     rdx, [rax+8]
0x1800ae416  mov     [rax], r15
0x1800ae419  mov     [rax+8], r15
0x1800ae41d  mov     [rdi+30h], rcx
0x1800ae421  mov     rcx, [rdi+38h]; this
0x1800ae425  mov     [rdi+38h], rdx
0x1800ae429  test    rcx, rcx
0x1800ae42c  jz      short loc_1800AE433
0x1800ae42e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae433  mov     rcx, [rbp+0D0h+var_150]; this
0x1800ae437  test    rcx, rcx
0x1800ae43a  jz      short loc_1800AE441
0x1800ae43c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae441  xorps   xmm0, xmm0
0x1800ae444  movss   xmm1, cs:__real@45cb2000
0x1800ae44c  mov     dword ptr [rbp+0D0h+var_70+8], r15d
0x1800ae450  movsd   [rbp+0D0h+var_60], xmm0
0x1800ae455  movss   [rbp+0D0h+var_58], xmm1
0x1800ae45a  mov     [rbp+0D0h+var_50], ebx
0x1800ae460  lea     rax, ??_7DeManagementTransitionSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementTransitionSettingType::`vftable'
0x1800ae467  mov     qword ptr [rbp+0D0h+var_70], rax
0x1800ae46b  lea     r8, [rbp+0D0h+var_70]
0x1800ae46f  lea     rdx, [rbp+0D0h+var_148]
0x1800ae473  lea     rcx, [rsp+1D0h+var_180]
0x1800ae478  call    ?Make@?$DeManagementServerSetting@$01@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$01@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementTransitionSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<2>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementTransitionSettingType,bool,bool,bool)
0x1800ae47d  mov     rcx, [rax]
0x1800ae480  mov     rdx, [rax+8]
0x1800ae484  mov     [rax], r15
0x1800ae487  mov     [rax+8], r15
0x1800ae48b  mov     [rdi+40h], rcx
0x1800ae48f  mov     rcx, [rdi+48h]; this
0x1800ae493  mov     [rdi+48h], rdx
0x1800ae497  test    rcx, rcx
0x1800ae49a  jz      short loc_1800AE4A1
0x1800ae49c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae4a1  mov     rcx, [rsp+1D0h+var_178]; this
0x1800ae4a6  test    rcx, rcx
0x1800ae4a9  jz      short loc_1800AE4B0
0x1800ae4ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae4b0  mov     dword ptr [rbp+0D0h+var_D8], 3EA01B86h
0x1800ae4b7  mov     dword ptr [rbp+0D0h+var_D8+4], 3EA8754Fh
0x1800ae4be  mov     [rbp+0D0h+var_D0], ebx
0x1800ae4c1  lea     r13, ??_7DeManagementChromaticityXYSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementChromaticityXYSettingType::`vftable'
0x1800ae4c8  mov     [rbp+0D0h+var_E0], r13
0x1800ae4cc  lea     r8, [rbp+0D0h+var_E0]
0x1800ae4d0  lea     rdx, [rbp+0D0h+var_148]
0x1800ae4d4  lea     rcx, [rsp+1D0h+var_180]
0x1800ae4d9  call    ?Make@?$DeManagementServerSetting@$02@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$02@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementChromaticityXYSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<3>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementChromaticityXYSettingType,bool,bool,bool)
0x1800ae4de  mov     rcx, [rax]
0x1800ae4e1  mov     rdx, [rax+8]
0x1800ae4e5  mov     [rax], r15
0x1800ae4e8  mov     [rax+8], r15
0x1800ae4ec  mov     [rdi+50h], rcx
0x1800ae4f0  mov     rcx, [rdi+58h]; this
0x1800ae4f4  mov     [rdi+58h], rdx
0x1800ae4f8  test    rcx, rcx
0x1800ae4fb  jz      short loc_1800AE502
0x1800ae4fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae502  mov     rcx, [rsp+1D0h+var_178]; this
0x1800ae507  test    rcx, rcx
0x1800ae50a  jz      short loc_1800AE511
0x1800ae50c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae511  mov     dword ptr [rbp+0D0h+var_D8], 3EA01B86h
0x1800ae518  mov     dword ptr [rbp+0D0h+var_D8+4], 3EA8754Fh
0x1800ae51f  mov     [rbp+0D0h+var_D0], ebx
0x1800ae522  mov     [rbp+0D0h+var_E0], r13
0x1800ae526  lea     r8, [rbp+0D0h+var_E0]
0x1800ae52a  lea     rdx, [rbp+0D0h+var_148]
0x1800ae52e  lea     rcx, [rsp+1D0h+var_180]
0x1800ae533  call    ?Make@?$DeManagementServerSetting@$03@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$03@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementChromaticityXYSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<4>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementChromaticityXYSettingType,bool,bool,bool)
0x1800ae538  mov     rcx, [rax]
0x1800ae53b  mov     rdx, [rax+8]
0x1800ae53f  mov     [rax], r15
0x1800ae542  mov     [rax+8], r15
0x1800ae546  mov     [rdi+60h], rcx
0x1800ae54a  mov     rcx, [rdi+68h]; this
0x1800ae54e  mov     [rdi+68h], rdx
0x1800ae552  test    rcx, rcx
0x1800ae555  jz      short loc_1800AE55C
0x1800ae557  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae55c  mov     rcx, [rsp+1D0h+var_178]; this
0x1800ae561  test    rcx, rcx
0x1800ae564  jz      short loc_1800AE56B
0x1800ae566  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae56b  call    ?GetSecondsSinceEpoch@TimeHelpers@Foundation@DisplayEnhancement@Windows@Microsoft@@SAKXZ; Microsoft::Windows::DisplayEnhancement::Foundation::TimeHelpers::GetSecondsSinceEpoch(void)
0x1800ae570  mov     dword ptr [rsp+1D0h+var_178], eax
0x1800ae574  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae578  lea     r13, ??_7DeManagementFloatSettingType@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@6B@; const Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementFloatSettingType::`vftable'
0x1800ae57f  mov     [rsp+1D0h+var_180], r13
0x1800ae584  lea     r8, [rsp+1D0h+var_180]
0x1800ae589  lea     rdx, [rbp+0D0h+var_148]
0x1800ae58d  lea     rcx, [rsp+1D0h+var_158]
0x1800ae592  call    ?Make@?$DeManagementServerSetting@$04@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$04@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementULongSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<5>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementULongSettingType,bool,bool,bool)
0x1800ae597  mov     rcx, [rax]
0x1800ae59a  mov     rdx, [rax+8]
0x1800ae59e  mov     [rax], r15
0x1800ae5a1  mov     [rax+8], r15
0x1800ae5a5  mov     [rdi+70h], rcx
0x1800ae5a9  mov     rcx, [rdi+78h]; this
0x1800ae5ad  mov     [rdi+78h], rdx
0x1800ae5b1  test    rcx, rcx
0x1800ae5b4  jz      short loc_1800AE5BB
0x1800ae5b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae5bb  mov     rcx, [rbp+0D0h+var_150]; this
0x1800ae5bf  test    rcx, rcx
0x1800ae5c2  jz      short loc_1800AE5C9
0x1800ae5c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae5c9  mov     byte ptr [rsp+1D0h+var_178], r15b
0x1800ae5ce  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae5d2  mov     [rsp+1D0h+var_180], r12
0x1800ae5d7  lea     r8, [rsp+1D0h+var_180]
0x1800ae5dc  lea     rdx, [rbp+0D0h+var_148]
0x1800ae5e0  lea     rcx, [rsp+1D0h+var_158]
0x1800ae5e5  call    ?Make@?$DeManagementServerSetting@$05@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$05@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementBoolSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<6>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementBoolSettingType,bool,bool,bool)
0x1800ae5ea  mov     rcx, [rax]
0x1800ae5ed  mov     rdx, [rax+8]
0x1800ae5f1  mov     [rax], r15
0x1800ae5f4  mov     [rax+8], r15
0x1800ae5f8  mov     [rdi+80h], rcx
0x1800ae5ff  mov     rcx, [rdi+88h]; this
0x1800ae606  mov     [rdi+88h], rdx
0x1800ae60d  test    rcx, rcx
0x1800ae610  jz      short loc_1800AE617
0x1800ae612  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae617  mov     rcx, [rbp+0D0h+var_150]; this
0x1800ae61b  test    rcx, rcx
0x1800ae61e  jz      short loc_1800AE625
0x1800ae620  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae625  mov     byte ptr [rsp+1D0h+var_178], r15b
0x1800ae62a  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae62e  mov     [rsp+1D0h+var_180], r12
0x1800ae633  lea     r8, [rsp+1D0h+var_180]
0x1800ae638  lea     rdx, [rbp+0D0h+var_148]
0x1800ae63c  lea     rcx, [rsp+1D0h+var_158]
0x1800ae641  call    ?Make@?$DeManagementServerSetting@$06@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$06@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementBoolSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<7>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementBoolSettingType,bool,bool,bool)
0x1800ae646  mov     rcx, [rax]
0x1800ae649  mov     rdx, [rax+8]
0x1800ae64d  mov     [rax], r15
0x1800ae650  mov     [rax+8], r15
0x1800ae654  mov     [rdi+90h], rcx
0x1800ae65b  mov     rcx, [rdi+98h]; this
0x1800ae662  mov     [rdi+98h], rdx
0x1800ae669  test    rcx, rcx
0x1800ae66c  jz      short loc_1800AE673
0x1800ae66e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae673  mov     rcx, [rbp+0D0h+var_150]; this
0x1800ae677  test    rcx, rcx
0x1800ae67a  jz      short loc_1800AE681
0x1800ae67c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae681  mov     rcx, [rbp+0D0h+var_128]
0x1800ae685  mov     rax, [rcx]
0x1800ae688  lea     rdx, [rbp+0D0h+var_138]
0x1800ae68c  mov     rax, [rax+0B8h]
0x1800ae693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae698  nop
0x1800ae699  mov     rax, [rax]
0x1800ae69c  mov     cl, [rax+8]
0x1800ae69f  mov     byte ptr [rsp+1D0h+var_178], cl
0x1800ae6a3  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae6a7  mov     [rsp+1D0h+var_180], r12
0x1800ae6ac  lea     r8, [rsp+1D0h+var_180]
0x1800ae6b1  lea     rdx, [rbp+0D0h+var_148]
0x1800ae6b5  lea     rcx, [rsp+1D0h+var_158]
0x1800ae6ba  call    ?Make@?$DeManagementServerSetting@$07@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$07@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementBoolSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<8>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementBoolSettingType,bool,bool,bool)
0x1800ae6bf  mov     rcx, [rax]
0x1800ae6c2  mov     rdx, [rax+8]
0x1800ae6c6  mov     [rax], r15
0x1800ae6c9  mov     [rax+8], r15
0x1800ae6cd  mov     [rdi+0A0h], rcx
0x1800ae6d4  mov     rcx, [rdi+0A8h]; this
0x1800ae6db  mov     [rdi+0A8h], rdx
0x1800ae6e2  test    rcx, rcx
0x1800ae6e5  jz      short loc_1800AE6EC
0x1800ae6e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae6ec  mov     rcx, [rbp+0D0h+var_150]; this
0x1800ae6f0  test    rcx, rcx
0x1800ae6f3  jz      short loc_1800AE6FB
0x1800ae6f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae6fa  nop
0x1800ae6fb  mov     rcx, [rbp+0D0h+var_130]; this
0x1800ae6ff  test    rcx, rcx
0x1800ae702  jz      short loc_1800AE709
0x1800ae704  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae709  mov     rcx, [rbp+0D0h+var_128]
0x1800ae70d  mov     rax, [rcx]
0x1800ae710  lea     rdx, [rbp+0D0h+var_138]
0x1800ae714  mov     rax, [rax+18h]
0x1800ae718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae71d  nop
0x1800ae71e  mov     rax, [rax]
0x1800ae721  mov     cl, [rax+8]
0x1800ae724  mov     byte ptr [rsp+1D0h+var_178], cl
0x1800ae728  mov     dword ptr [rsp+1D0h+var_178+4], esi
0x1800ae72c  mov     [rsp+1D0h+var_180], r12
0x1800ae731  lea     r8, [rsp+1D0h+var_180]
0x1800ae736  lea     rdx, [rbp+0D0h+var_148]
0x1800ae73a  lea     rcx, [rsp+1D0h+var_158]
0x1800ae73f  call    ?Make@?$DeManagementServerSetting@$0M@@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@V?$DeManagementServerSetting@$0M@@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@VDeManagementBoolSettingType@2345@_N22@Z; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSetting<12>::Make(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> const &,Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementBoolSettingType,bool,bool,bool)
0x1800ae744  mov     rcx, [rax]
0x1800ae747  mov     rdx, [rax+8]
0x1800ae74b  mov     [rax], r15
0x1800ae74e  mov     [rax+8], r15
0x1800ae752  mov     [rdi+0E0h], rcx
0x1800ae759  mov     rcx, [rdi+0E8h]; this
0x1800ae760  mov     [rdi+0E8h], rdx
0x1800ae767  test    rcx, rcx
0x1800ae76a  jz      short loc_1800AE771
0x1800ae76c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ae771  mov     rcx, [rbp+0D0h+var_150]; this
  ... truncated ...
```
