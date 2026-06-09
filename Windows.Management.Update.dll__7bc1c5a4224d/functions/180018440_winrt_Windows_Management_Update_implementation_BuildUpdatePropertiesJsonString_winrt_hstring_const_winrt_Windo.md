# winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)

- ea: `0x180018440`
- end: `0x18001b85b`
- name: `?BuildUpdatePropertiesJsonString@implementation@Update@Management@Windows@winrt@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z`
- size: `13339`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, __int64, __int64, __int64, _QWORD *, __int64, void *, _QWORD *, _QWORD *, __int64 *, _QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bf00`

## callees

- `0x1800028f0`
- `0x18000340c`
- `0x180005010`
- `0x180005030`
- `0x1800052d0`
- `0x180005380`
- `0x180005c40`
- `0x180006630`
- `0x1800066a0`
- `0x180006700`
- `0x180006770`
- `0x180006b10`
- `0x1800080b0`
- `0x180008653`
- `0x18000866b`
- `0x180011464`
- `0x180011b7c`
- `0x180014eb4`
- `0x180016fe4`
- `0x180017bec`
- `0x180017d0c`
- `0x180018238`
- `0x1800182e8`
- `0x180018440`
- `0x18001b864`
- `0x18001b8c4`
- `0x18001b924`
- `0x18001c174`
- `0x18001c1c8`
- `0x18001c21c`
- `0x18001c43c`
- `0x18001c780`
- `0x18001c81c`
- `0x18001d50c`
- `0x18001d738`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018f66`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800195dd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018f66`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800195dd`

## string_xrefs

- `0x18001b72a`: `AppPackageInfo cannot be null for AppPackage installation type.`
- `0x18001b7a8`: `ExecutionInfo cannot be null for Executable or Powershell installation type.`
- `0x180018639`: `InstallationType`
- `0x1800186f2`: `UpdateId`
- `0x180018a47`: `InstallSizeInBytes`
- `0x18001991f`: `InstallUri`
- `0x180019fd4`: `InstallInfo`
- `0x18001aa1f`: `CloseAndInstallInfo`
- `0x18001b828`: `ComplianceDeadlineInDays must be a non-negative value less than or equal to 30 days.`
- `0x18001b49f`: `ComplianceDeadlineInDays`
- `0x18001b6eb`: `ComplianceGracePeriodInDays must be a non-negative value less than or equal to 7 days.`
- `0x18001b5dc`: `ComplianceGracePeriodInDays`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        void *a9,
        _QWORD *a10,
        _QWORD *a11,
        __int64 *a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 a15,
        __int64 a16)
{
  int *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  int *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rbx
  __int64 v27; // rax
  int *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rbx
  __int64 v31; // rax
  int *v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  int *v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rbx
  __int64 v40; // rax
  void *v41; // rbx
  int v42; // eax
  HANDLE ProcessHeap; // rax
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rax
  unsigned int v48; // eax
  __int64 v49; // rbx
  __int64 v50; // rax
  unsigned int v51; // eax
  __int64 v52; // rbx
  __int64 v53; // rax
  unsigned int v54; // eax
  __int64 v55; // rbx
  __int64 v56; // rax
  unsigned int v57; // eax
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rax
  _QWORD *v61; // rdi
  unsigned int v62; // eax
  __int64 v63; // rbx
  __int64 v64; // rax
  unsigned int v65; // eax
  __int64 v66; // rbx
  __int64 v67; // rax
  unsigned int v68; // eax
  __int64 v69; // rbx
  __int64 v70; // rax
  unsigned int v71; // eax
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rbx
  __int64 v79; // rax
  __int64 v80; // rbx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rbx
  __int64 v84; // rax
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // rbx
  __int64 v88; // rax
  __int64 v89; // rbx
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rcx
  int v93; // eax
  __int64 v94; // rax
  int *v95; // rdx
  __int64 v96; // r8
  __int64 v97; // rbx
  int v98; // esi
  __int64 v99; // rax
  void *v100; // rbx
  int v101; // eax
  HANDLE v102; // rax
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // rbx
  int v106; // esi
  __int64 v107; // rax
  __int64 *v108; // rdi
  __int64 v109; // rcx
  int v110; // eax
  int *v111; // rdx
  __int64 v112; // r8
  __int64 v113; // rbx
  __int64 v114; // rax
  __int64 v115; // rcx
  int v116; // eax
  __int64 v117; // rbx
  __int64 v118; // rax
  __int64 v119; // rbx
  __int64 v120; // rax
  __int64 v121; // rax
  int *v122; // rdx
  __int64 v123; // r8
  __int64 v124; // rbx
  __int64 v125; // rax
  __int64 v126; // rax
  _QWORD *v127; // rcx
  __int64 v128; // rdi
  __int64 v129; // rbx
  __int64 v130; // rax
  __int64 v131; // rax
  int *v132; // rdx
  __int64 v133; // r8
  __int64 v134; // rbx
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  int *v138; // rdx
  __int64 v139; // r8
  __int64 v140; // rbx
  __int64 v141; // rax
  __int64 v142; // rax
  unsigned int v143; // eax
  __int64 v144; // rbx
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rbx
  __int64 v148; // rax
  __int64 v149; // rax
  int *v150; // rdx
  __int64 v151; // r8
  __int64 v152; // rbx
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  int *v156; // rdx
  __int64 v157; // r8
  __int64 v158; // rbx
  __int64 v159; // rax
  __int64 v160; // rax
  unsigned int v161; // eax
  __int64 v162; // rbx
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rbx
  __int64 v166; // rax
  __int64 v167; // rax
  int *v168; // rdx
  __int64 v169; // r8
  __int64 v170; // rbx
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rax
  int *v174; // rdx
  __int64 v175; // r8
  __int64 v176; // rbx
  __int64 v177; // rax
  __int64 v178; // rax
  unsigned int v179; // eax
  __int64 v180; // rbx
  __int64 v181; // rax
  __int64 v182; // rax
  __int64 v183; // rbx
  __int64 v184; // rax
  __int64 v185; // rbx
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  int *v189; // rdx
  __int64 v190; // r8
  __int64 v191; // rbx
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // rax
  __int64 v195; // rax
  int *v196; // rdx
  __int64 v197; // r8
  __int64 v198; // rbx
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rax
  unsigned int v202; // eax
  __int64 v203; // rbx
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rax
  __int64 v207; // rbx
  __int64 v208; // rax
  __int64 v209; // rax
  __int64 v210; // rax
  int *v211; // rdx
  __int64 v212; // r8
  __int64 v213; // rbx
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  int *v218; // rdx
  __int64 v219; // r8
  __int64 v220; // rbx
  __int64 v221; // rax
  __int64 v222; // rax
  __int64 v223; // rax
  unsigned int v224; // eax
  __int64 v225; // rbx
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // rax
  __int64 v229; // rbx
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rax
  int *v233; // rdx
  __int64 v234; // r8
  __int64 v235; // rbx
  __int64 v236; // rax
  __int64 v237; // rax
  __int64 v238; // rax
  __int64 v239; // rax
  int *v240; // rdx
  __int64 v241; // r8
  __int64 v242; // rbx
  __int64 v243; // rax
  __int64 v244; // rax
  __int64 v245; // rax
  unsigned int v246; // eax
  __int64 v247; // rbx
  __int64 v248; // rax
  __int64 v249; // rax
  __int64 v250; // rax
  _QWORD *v251; // rdi
  _QWORD *v252; // rax
  unsigned int v253; // esi
  __int64 v254; // rax
  char v255; // bl
  __int64 v256; // rax
  unsigned int v257; // eax
  int v258; // r15d
  unsigned int v259; // r14d
  int v260; // r12d
  _QWORD *v261; // rbx
  int v262; // esi
  int v263; // eax
  int v264; // eax
  __int64 v265; // rdi
  __int64 v266; // rax
  __int64 v267; // rax
  int *v268; // rdx
  __int64 v269; // r8
  __int64 v270; // rdi
  __int64 v271; // rax
  __int64 v272; // rax
  int *v273; // rdx
  __int64 v274; // r8
  __int64 v275; // rdi
  __int64 v276; // rax
  __int64 v277; // rdi
  __int64 v278; // rax
  __int64 v279; // rax
  int *v280; // rdx
  __int64 v281; // r8
  __int64 v282; // rdi
  __int64 v283; // rax
  __int64 v284; // rax
  __int64 v285; // rax
  __int64 v286; // rbx
  __int64 v287; // rax
  __int64 v288; // rdx
  __int64 v289; // rax
  char v290; // bl
  __int64 v291; // rax
  unsigned int v292; // eax
  __int64 v293; // rbx
  __int64 v294; // rax
  __int64 v295; // rbx
  __int64 v296; // rax
  int v297; // esi
  __int64 v298; // rdx
  __int64 v299; // rax
  char v300; // bl
  __int64 v301; // rax
  unsigned int v302; // eax
  __int64 v303; // rbx
  __int64 v304; // rax
  __int64 v305; // rax
  __int64 v306; // rbx
  const struct winrt::impl::slim_source_location *v308; // rbx
  const struct winrt::impl::slim_source_location *v309; // rbx
  const struct winrt::impl::slim_source_location *v310; // rbx
  const struct winrt::impl::slim_source_location *v311; // rbx
  const struct winrt::impl::slim_source_location *v312; // rbx
  __int64 v313; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v314; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v315; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v316; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v317; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v318; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v319; // [rsp+50h] [rbp-B0h]
  __int64 *v320; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v321; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v324; // [rsp+88h] [rbp-78h]
  LPVOID v325; // [rsp+90h] [rbp-70h] BYREF
  __int64 v326; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v327; // [rsp+A0h] [rbp-60h]
  __int128 v328; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v329; // [rsp+B8h] [rbp-48h]
  __int64 v330; // [rsp+C0h] [rbp-40h]
  __int64 v331; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v332[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v333; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v334[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v335; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v336; // [rsp+F0h] [rbp-10h]
  __int128 v337; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v338; // [rsp+108h] [rbp+8h]
  __int128 v339; // [rsp+118h] [rbp+18h] BYREF
  __int128 v340; // [rsp+128h] [rbp+28h]
  __int128 v341; // [rsp+138h] [rbp+38h] BYREF

  v314 = a3;
  v336 = a1;
  v327 = a14;
  v317 = (__int64)a13;
  v320 = a12;
  v315 = a16;
  v326 = a15;
  v316 = a11;
  *(_QWORD *)&v341 = a1;
  v325 = a9;
  v319 = 0;
  if ( !*(_QWORD *)a2 || !*(_QWORD *)a4 || !*(_QWORD *)a5 || !*(_QWORD *)a6 || !*a7 )
  {
    v310 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v341, a13);
    winrt::param::hstring::hstring((winrt::param::hstring *)&v339, L"Required parameters cannot be empty.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)&v339,
      v310);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  if ( *a3 == 1 )
  {
    if ( !*a12 )
    {
      v309 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v341, a13);
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)&v339,
        L"AppPackageInfo cannot be null for AppPackage installation type.");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)&v339,
        v309);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
  }
  else if ( (unsigned int)(*a3 - 2) <= 1 && !*a13 )
  {
    v311 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v341, a13);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)&v339,
      L"ExecutionInfo cannot be null for Executable or Powershell installation type.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)&v339,
      v311);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  web::json::value::object(&v321, 0);
  if ( *(_QWORD *)a2 )
    v18 = *(int **)(*(_QWORD *)a2 + 16LL);
  else
    v18 = &dword_18002EB94;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v324 = 0;
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)v18 + v19) );
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, v18, v19);
  v20 = web::json::value::string(&v313, pExceptionObject);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"ProviderId", 10);
  v21 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v21, v20);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  v22 = web::json::value::number(&v313, *(unsigned int *)v314);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"InstallationType", 16);
  v23 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v23, v22);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  if ( *(_QWORD *)a4 )
    v24 = *(int **)(*(_QWORD *)a4 + 16LL);
  else
    v24 = &dword_18002EB94;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v324 = 0;
  v25 = -1;
  do
    ++v25;
  while ( *((_WORD *)v24 + v25) );
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, v24, v25);
  v26 = web::json::value::string(&v313, pExceptionObject);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"UpdateId", 8);
  v27 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v27, v26);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  if ( *(_QWORD *)a5 )
    v28 = *(int **)(*(_QWORD *)a5 + 16LL);
  else
    v28 = &dword_18002EB94;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v324 = 0;
  v29 = -1;
  do
    ++v29;
  while ( *((_WORD *)v28 + v29) );
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, v28, v29);
  v30 = web::json::value::string(&v313, pExceptionObject);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"Title", 5);
  v31 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v31, v30);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  if ( *(_QWORD *)a6 )
    v32 = *(int **)(*(_QWORD *)a6 + 16LL);
  else
    v32 = &dword_18002EB94;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v324 = 0;
  v33 = -1;
  do
    ++v33;
  while ( *((_WORD *)v32 + v33) );
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, v32, v33);
  v34 = web::json::value::string(&v313, pExceptionObject);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"Description", 11);
  v35 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v35, v34);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  v36 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(
          a7,
          &lpMem);
  if ( *(_QWORD *)v36 )
    v37 = *(int **)(*(_QWORD *)v36 + 16LL);
  else
    v37 = &dword_18002EB94;
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v324 = 0;
  v38 = -1;
  do
    ++v38;
  while ( *((_WORD *)v37 + v38) );
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, v37, v38);
  v39 = web::json::value::string(&v313, pExceptionObject);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"MoreInfoUrl", 11);
  v40 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v40, v39);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  v41 = lpMem;
  if ( lpMem )
  {
    v42 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v42 )
    {
      if ( v42 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v41);
    }
  }
  v44 = web::json::value::number(&v313, a8);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"DownloadSizeInBytes", 19);
  v45 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v45, v44);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  v46 = web::json::value::number(&v313, v325);
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"InstallSizeInBytes", 18);
  v47 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v47, v46);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v313 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  if ( *a10 )
  {
    web::json::value::object(&v318, 0);
    v48 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a10);
    v49 = web::json::value::number(&v313, v48);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Major", 5);
    v50 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v50, v49);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v51 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(a10);
    v52 = web::json::value::number(&v313, v51);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Minor", 5);
    v53 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v53, v52);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v54 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(a10);
    v55 = web::json::value::number(&v313, v54);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMajor", 13);
    v56 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v56, v55);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v57 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::RevisionMinor(a10);
    v58 = web::json::value::number(&v313, v57);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMinor", 13);
    v59 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v59, v58);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"SourceVersion", 13);
    v60 = web::json::value::operator[](&v321, &v337);
    web::json::value::operator=(v60, &v318);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v318 )
LABEL_65:
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v318 + 192LL))(v318, 1);
  }
  else
  {
    web::json::value::object(&v318, 0);
    v74 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Major", 5);
    v75 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v75, v74);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v76 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Minor", 5);
    v77 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v77, v76);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v78 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMajor", 13);
    v79 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v79, v78);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v80 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMinor", 13);
    v81 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v81, v80);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"SourceVersion", 13);
    v82 = web::json::value::operator[](&v321, &v337);
    web::json::value::operator=(v82, &v318);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v318 )
      goto LABEL_65;
  }
  v61 = v316;
  if ( *v316 )
  {
    web::json::value::object(&v318, 0);
    v62 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v61);
    v63 = web::json::value::number(&v313, v62);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Major", 5);
    v64 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v64, v63);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v65 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(v61);
    v66 = web::json::value::number(&v313, v65);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Minor", 5);
    v67 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v67, v66);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v68 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v61);
    v69 = web::json::value::number(&v313, v68);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMajor", 13);
    v70 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v70, v69);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v71 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::RevisionMinor(v61);
    v72 = web::json::value::number(&v313, v71);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMinor", 13);
    v73 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v73, v72);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  }
  else
  {
    web::json::value::object(&v318, 0);
    v83 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Major", 5);
    v84 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v84, v83);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v85 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"Minor", 5);
    v86 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v86, v85);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v87 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMajor", 13);
    v88 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v88, v87);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    v89 = web::json::value::number(&v313, 0);
    v337 = 0;
    v338 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v337, L"RevisionMinor", 13);
    v90 = web::json::value::operator[](&v318, &v337);
    web::json::value::operator=(v90, v89);
    std::wstring::_Tidy_deallocate(&v337);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  }
  v337 = 0;
  v338 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v337, L"TargetVersion", 13);
  v91 = web::json::value::operator[](&v321, &v337);
  web::json::value::operator=(v91, &v318);
  std::wstring::_Tidy_deallocate(&v337);
  if ( v318 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v318 + 192LL))(v318, 1);
  v92 = *(_QWORD *)v326;
  if ( *(_QWORD *)v326 )
  {
    v341 = 0;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v93 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v92 + 48LL))(v92, &v341);
    if ( v93 < 0 )
      winrt::throw_hresult((unsigned int)v93, pExceptionObject);
    v94 = winrt::to_hstring(&v325, &v341);
    v319 = 1;
    if ( *(_QWORD *)v94 )
      v95 = *(int **)(*(_QWORD *)v94 + 16LL);
    else
      v95 = &dword_18002EB94;
    v328 = 0;
    v329 = 0;
    v330 = 0;
    v96 = -1;
    do
      ++v96;
    while ( *((_WORD *)v95 + v96) );
    std::wstring::_Construct<1,unsigned short const *>(&v328, v95, v96);
    v97 = web::json::value::string(&lpMem, &v328);
    v98 = 3;
  }
  else
  {
    v337 = 0;
    v338 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v337, &dword_18002EB94, 0);
    v97 = web::json::value::string(&v313, &v337);
    v98 = 4;
  }
  v319 = v98;
  v339 = 0;
  v340 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v339, L"ProductCode", 11);
  v99 = web::json::value::operator[](&v321, &v339);
  web::json::value::operator=(v99, v97);
  std::wstring::_Tidy_deallocate(&v339);
  if ( (v98 & 4) != 0 )
  {
    v98 &= ~4u;
    v319 = v98;
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  }
  if ( (v98 & 2) != 0 )
  {
    v98 &= ~2u;
    v319 = v98;
    if ( lpMem )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)lpMem + 192LL))(lpMem, 1);
  }
  if ( (v98 & 1) != 0 )
  {
    v98 &= ~1u;
    v319 = v98;
    v100 = v325;
    if ( v325 )
    {
      v101 = _InterlockedDecrement((volatile signed __int32 *)v325 + 6);
      if ( v101 )
      {
        if ( v101 < 0 )
          abort();
      }
      else
      {
        v102 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v102, 0, v100);
      }
    }
  }
  if ( *(_QWORD *)v315 )
  {
    v103 = *(_QWORD *)(*(_QWORD *)v315 + 16LL);
    v337 = 0;
    v338 = 0u;
    v104 = -1;
    do
      ++v104;
    while ( *(_WORD *)(v103 + 2 * v104) );
    std::wstring::_Construct<1,unsigned short const *>(&v337, v103, v104);
    v105 = web::json::value::string(&lpMem, &v337);
    v106 = v98 | 8;
  }
  else
  {
    v328 = 0;
    v329 = 0;
    v330 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v328, &dword_18002EB94, 0);
    v105 = web::json::value::string(&v313, &v328);
    v106 = v98 | 0x10;
  }
  v319 = v106;
  v339 = 0;
  v340 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v339, L"PackageFamilyName", 17);
  v107 = web::json::value::operator[](&v321, &v339);
  web::json::value::operator=(v107, v105);
  std::wstring::_Tidy_deallocate(&v339);
  if ( (v106 & 0x10) != 0 )
  {
    v106 &= ~0x10u;
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
  }
  if ( (v106 & 8) != 0 )
  {
    v106 &= ~8u;
    if ( lpMem )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)lpMem + 192LL))(lpMem, 1);
  }
  if ( *(_DWORD *)v314 == 1 )
  {
    v108 = v320;
    if ( !*v320 )
      goto LABEL_350;
    web::json::value::object(&v315, 0);
    v314 = 0;
    v109 = *v108;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v110 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v109 + 48LL))(v109, &v314);
    if ( v110 < 0 )
      winrt::throw_hresult((unsigned int)v110, pExceptionObject);
    lpMem = v314;
    v106 |= 0x1000u;
    if ( v314 )
      v111 = (int *)v314[2];
    else
      v111 = &dword_18002EB94;
    v337 = 0;
    v338 = 0u;
    v112 = -1;
    do
      ++v112;
    while ( *((_WORD *)v111 + v112) );
    std::wstring::_Construct<1,unsigned short const *>(&v337, v111, v112);
    v113 = web::json::value::string(&v313, &v337);
    v339 = 0;
    v340 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v339, L"PackageFamilyName", 17);
    v114 = web::json::value::operator[](&v315, &v339);
    web::json::value::operator=(v114, v113);
    std::wstring::_Tidy_deallocate(&v339);
    if ( v313 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
    winrt::hstring::~hstring((winrt::hstring *)&lpMem);
    LODWORD(v320) = 0;
    v115 = *v108;
    *(_DWORD *)pExceptionObject = 0;
    *(_OWORD *)&pExceptionObject[8] = 0;
    v116 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v115 + 56LL))(v115, &v320);
    if ( v116 < 0 )
      winrt::throw_hresult((unsigned int)v116, pExceptionObject);
    v117 = web::json::value::number(&v325, (unsigned int)v320);
    v339 = 0;
    v340 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v339, L"PackageArchitecture", 19);
    v118 = web::json::value::operator[](&v315, &v339);
    web::json::value::operator=(v118, v117);
    std::wstring::_Tidy_deallocate(&v339);
    if ( v325 )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v325 + 192LL))(v325, 1);
    v119 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                        v108,
                        &v314);
    if ( v314 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    if ( v119 )
    {
      v120 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
               v108,
               &v314);
      v121 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(
               v120,
               &lpMem);
      if ( *(_QWORD *)v121 )
        v122 = *(int **)(*(_QWORD *)v121 + 16LL);
      else
        v122 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v123 = -1;
      do
        ++v123;
      while ( *((_WORD *)v122 + v123) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v122, v123);
      v124 = web::json::value::string(&v313, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"InstallUri", 10);
      v125 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v125, v124);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v313 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
      winrt::hstring::~hstring((winrt::hstring *)&lpMem);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    }
    v339 = 0;
    v340 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v339, L"AppPackageInfo", 14);
    v126 = web::json::value::operator[](&v321, &v339);
    web::json::value::operator=(v126, &v315);
    std::wstring::_Tidy_deallocate(&v339);
    v127 = (_QWORD *)v315;
  }
  else
  {
    if ( (unsigned int)(*(_DWORD *)v314 - 2) > 1 )
      goto LABEL_350;
    v128 = v317;
    if ( !*(_QWORD *)v317 )
      goto LABEL_350;
    web::json::value::object(&v320, 0);
    v129 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                        v128,
                        &v314);
    if ( v314 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    if ( v129 )
    {
      web::json::value::object(&v315, 0);
      v130 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v128,
               &v314);
      v131 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v130,
               &v313);
      if ( *(_QWORD *)v131 )
        v132 = *(int **)(*(_QWORD *)v131 + 16LL);
      else
        v132 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v133 = -1;
      do
        ++v133;
      while ( *((_WORD *)v132 + v133) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v132, v133);
      v134 = web::json::value::string(&v317, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileName", 8);
      v135 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v135, v134);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v313);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v136 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v128,
               &v314);
      v137 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v136,
               &v313);
      if ( *(_QWORD *)v137 )
        v138 = *(int **)(*(_QWORD *)v137 + 16LL);
      else
        v138 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v139 = -1;
      do
        ++v139;
      while ( *((_WORD *)v138 + v139) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v138, v139);
      v140 = web::json::value::string(&v317, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileArguments", 13);
      v141 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v141, v140);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v313);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v142 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v128,
               &v314);
      v143 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v142);
      v144 = web::json::value::number(&v317, v143);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"ActionType", 10);
      v145 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v145, v144);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"DownloadInfo", 12);
      v146 = web::json::value::operator[](&v320, &v339);
      web::json::value::operator=(v146, &v315);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v315 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
    }
    v147 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                        v128,
                        &v314);
    if ( v314 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    if ( v147 )
    {
      web::json::value::object(&v315, 0);
      v148 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v128,
               &v314);
      v149 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v148,
               &v313);
      if ( *(_QWORD *)v149 )
        v150 = *(int **)(*(_QWORD *)v149 + 16LL);
      else
        v150 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v151 = -1;
      do
        ++v151;
      while ( *((_WORD *)v150 + v151) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v150, v151);
      v152 = web::json::value::string(&v317, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileName", 8);
      v153 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v153, v152);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v313);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v154 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v128,
               &v314);
      v155 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v154,
               &v313);
      if ( *(_QWORD *)v155 )
        v156 = *(int **)(*(_QWORD *)v155 + 16LL);
      else
        v156 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v157 = -1;
      do
        ++v157;
      while ( *((_WORD *)v156 + v157) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v156, v157);
      v158 = web::json::value::string(&v317, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileArguments", 13);
      v159 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v159, v158);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v313);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v160 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v128,
               &v314);
      v161 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v160);
      v162 = web::json::value::number(&v317, v161);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"ActionType", 10);
      v163 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v163, v162);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"InstallInfo", 11);
      v164 = web::json::value::operator[](&v320, &v339);
      web::json::value::operator=(v164, &v315);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v315 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
    }
    v165 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                        v128,
                        &v314);
    if ( v314 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    if ( v165 )
    {
      web::json::value::object(&v315, 0);
      v166 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
               v128,
               &v314);
      v167 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v166,
               &v313);
      if ( *(_QWORD *)v167 )
        v168 = *(int **)(*(_QWORD *)v167 + 16LL);
      else
        v168 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v169 = -1;
      do
        ++v169;
      while ( *((_WORD *)v168 + v169) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v168, v169);
      v170 = web::json::value::string(&v317, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileName", 8);
      v171 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v171, v170);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v313);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v172 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
               v128,
               &v314);
      v173 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v172,
               &v313);
      if ( *(_QWORD *)v173 )
        v174 = *(int **)(*(_QWORD *)v173 + 16LL);
      else
        v174 = &dword_18002EB94;
      v337 = 0;
      v338 = 0u;
      v175 = -1;
      do
        ++v175;
      while ( *((_WORD *)v174 + v175) );
      std::wstring::_Construct<1,unsigned short const *>(&v337, v174, v175);
      v176 = web::json::value::string(&v317, &v337);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileArguments", 13);
      v177 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v177, v176);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v313);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v178 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
               v128,
               &v314);
      v179 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v178);
      v180 = web::json::value::number(&v317, v179);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"ActionType", 10);
      v181 = web::json::value::operator[](&v315, &v339);
      web::json::value::operator=(v181, v180);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v317 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      v339 = 0;
      v340 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v339, L"DeployInfo", 10);
      v182 = web::json::value::operator[](&v320, &v339);
      web::json::value::operator=(v182, &v315);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v315 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
    }
    v183 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                        v128,
                        &v314);
    if ( v314 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    if ( v183 )
    {
      v184 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
               v128,
               &v316);
      v185 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                          v184,
                          &v314);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      if ( v316 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
      if ( v185 )
      {
        web::json::value::object(&v315, 0);
        v186 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v187 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v186,
                 &v314);
        v188 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v187,
                 &v313);
        if ( *(_QWORD *)v188 )
          v189 = *(int **)(*(_QWORD *)v188 + 16LL);
        else
          v189 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v190 = -1;
        do
          ++v190;
        while ( *((_WORD *)v189 + v190) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v189, v190);
        v191 = web::json::value::string(&v317, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileName", 8);
        v192 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v192, v191);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v313);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v193 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v194 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v193,
                 &v314);
        v195 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v194,
                 &v313);
        if ( *(_QWORD *)v195 )
          v196 = *(int **)(*(_QWORD *)v195 + 16LL);
        else
          v196 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v197 = -1;
        do
          ++v197;
        while ( *((_WORD *)v196 + v197) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v196, v197);
        v198 = web::json::value::string(&v317, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileArguments", 13);
        v199 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v199, v198);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v313);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v200 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v201 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v200,
                 &v314);
        v202 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v201);
        v203 = web::json::value::number(&v317, v202);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"ActionType", 10);
        v204 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v204, v203);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"CloseAndDeployInfo", 18);
        v205 = web::json::value::operator[](&v320, &v339);
        web::json::value::operator=(v205, &v315);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v315 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
      }
      v206 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
               v128,
               &v316);
      v207 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                          v206,
                          &v314);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      if ( v316 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
      if ( v207 )
      {
        web::json::value::object(&v315, 0);
        v208 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v209 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v208,
                 &v314);
        v210 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v209,
                 &v313);
        if ( *(_QWORD *)v210 )
          v211 = *(int **)(*(_QWORD *)v210 + 16LL);
        else
          v211 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v212 = -1;
        do
          ++v212;
        while ( *((_WORD *)v211 + v212) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v211, v212);
        v213 = web::json::value::string(&v317, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileName", 8);
        v214 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v214, v213);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v313);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v215 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v216 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v215,
                 &v314);
        v217 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v216,
                 &v313);
        if ( *(_QWORD *)v217 )
          v218 = *(int **)(*(_QWORD *)v217 + 16LL);
        else
          v218 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v219 = -1;
        do
          ++v219;
        while ( *((_WORD *)v218 + v219) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v218, v219);
        v220 = web::json::value::string(&v317, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileArguments", 13);
        v221 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v221, v220);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v313);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v222 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v223 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v222,
                 &v314);
        v224 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v223);
        v225 = web::json::value::number(&v317, v224);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"ActionType", 10);
        v226 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v226, v225);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"CloseAndInstallInfo", 19);
        v227 = web::json::value::operator[](&v320, &v339);
        web::json::value::operator=(v227, &v315);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v315 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
      }
      v228 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
               v128,
               &v316);
      v229 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                          v228,
                          &v314);
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
      if ( v316 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
      if ( v229 )
      {
        web::json::value::object(&v315, 0);
        v230 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v231 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                 v230,
                 &v314);
        v232 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v231,
                 &v313);
        if ( *(_QWORD *)v232 )
          v233 = *(int **)(*(_QWORD *)v232 + 16LL);
        else
          v233 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v234 = -1;
        do
          ++v234;
        while ( *((_WORD *)v233 + v234) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v233, v234);
        v235 = web::json::value::string(&v317, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileName", 8);
        v236 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v236, v235);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v313);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v237 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v238 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                 v237,
                 &v314);
        v239 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v238,
                 &v313);
        if ( *(_QWORD *)v239 )
          v240 = *(int **)(*(_QWORD *)v239 + 16LL);
        else
          v240 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v241 = -1;
        do
          ++v241;
        while ( *((_WORD *)v240 + v241) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v240, v241);
        v242 = web::json::value::string(&v317, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"FileArguments", 13);
        v243 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v243, v242);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v313);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v244 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v128,
                 &v316);
        v245 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                 v244,
                 &v314);
        v246 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v245);
        v247 = web::json::value::number(&v317, v246);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"ActionType", 10);
        v248 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v248, v247);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        if ( v314 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
        if ( v316 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"CloseAndRestartInfo", 19);
        v249 = web::json::value::operator[](&v320, &v339);
        web::json::value::operator=(v249, &v315);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v315 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
      }
    }
    v339 = 0;
    v340 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v339, L"ExecutionInfo", 13);
    v250 = web::json::value::operator[](&v321, &v339);
    web::json::value::operator=(v250, &v320);
    std::wstring::_Tidy_deallocate(&v339);
    v127 = v320;
  }
  if ( v127 )
    (*(void (__fastcall **)(_QWORD *, __int64))(*v127 + 192LL))(v127, 1);
LABEL_350:
  v251 = v327;
  if ( *v327 )
  {
    web::json::value::object(&v326, 0);
    v252 = (_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                       v251,
                       &v316);
    v253 = v106 | 0x20;
    v319 = v253;
    if ( !*v252
      || (v254 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                   v251,
                   &v314),
          v253 |= 0x40u,
          v319 = v253,
          v255 = 1,
          !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(v254)) )
    {
      v255 = 0;
    }
    if ( (v253 & 0x40) != 0 )
    {
      v253 &= ~0x40u;
      if ( v314 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v314);
    }
    if ( (v253 & 0x20) != 0 )
    {
      v253 &= ~0x20u;
      if ( v316 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
    }
    if ( v255 )
    {
      v256 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v251,
               &v325);
      v257 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(v256);
      web::json::value::array(&v314, v257);
      if ( v325 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v325);
      v258 = 0;
      winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
        v251,
        &v316);
      v259 = 0;
      v260 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(&v316);
      v261 = v316;
      while ( v259 != v260 )
      {
        v318 = 0;
        v262 = v253 | 0x4000;
        v319 = v262;
        *(_DWORD *)pExceptionObject = 0;
        *(_OWORD *)&pExceptionObject[8] = 0;
        v263 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*v261 + 48LL))(v261, v259, &v318);
        if ( v263 < 0 )
          winrt::throw_hresult((unsigned int)v263, pExceptionObject);
        v319 = v262 & 0xFFFFBFFF;
        v253 = v262 & 0xFFFF9FFF | 0x2000;
        web::json::value::object(&v315, 0);
        LODWORD(v320) = 0;
        *(_DWORD *)pExceptionObject = 0;
        *(_OWORD *)&pExceptionObject[8] = 0;
        v264 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v318 + 48LL))(v318, &v320);
        if ( v264 < 0 )
          winrt::throw_hresult((unsigned int)v264, pExceptionObject);
        v265 = web::json::value::number(&v317, (unsigned int)v320);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"LanguageId", 10);
        v266 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v266, v265);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v317 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v317 + 192LL))(v317, 1);
        v267 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 &v318,
                 v332);
        if ( *(_QWORD *)v267 )
          v268 = *(int **)(*(_QWORD *)v267 + 16LL);
        else
          v268 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v269 = -1;
        do
          ++v269;
        while ( *((_WORD *)v268 + v269) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v268, v269);
        v270 = web::json::value::string(&v331, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"Title", 5);
        v271 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v271, v270);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v331 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v331 + 192LL))(v331, 1);
        winrt::hstring::~hstring((winrt::hstring *)v332);
        v272 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                 &v318,
                 v334);
        if ( *(_QWORD *)v272 )
          v273 = *(int **)(*(_QWORD *)v272 + 16LL);
        else
          v273 = &dword_18002EB94;
        v337 = 0;
        v338 = 0u;
        v274 = -1;
        do
          ++v274;
        while ( *((_WORD *)v273 + v274) );
        std::wstring::_Construct<1,unsigned short const *>(&v337, v273, v274);
        v275 = web::json::value::string(&v333, &v337);
        v339 = 0;
        v340 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v339, L"Description", 11);
        v276 = web::json::value::operator[](&v315, &v339);
        web::json::value::operator=(v276, v275);
        std::wstring::_Tidy_deallocate(&v339);
        if ( v333 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v333 + 192LL))(v333, 1);
        winrt::hstring::~hstring((winrt::hstring *)v334);
        v277 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                            &v318,
                            &lpMem);
        if ( lpMem )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
        if ( v277 )
        {
          v278 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                   &v318,
                   &v313);
          v279 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(
                   v278,
                   &v341);
          if ( *(_QWORD *)v279 )
            v280 = *(int **)(*(_QWORD *)v279 + 16LL);
          else
            v280 = &dword_18002EB94;
          v337 = 0;
          v338 = 0u;
          v281 = -1;
          do
            ++v281;
          while ( *((_WORD *)v280 + v281) );
          std::wstring::_Construct<1,unsigned short const *>(&v337, v280, v281);
          v282 = web::json::value::string(&v335, &v337);
          v339 = 0;
          v340 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v339, L"MoreInfoUrl", 11);
          v283 = web::json::value::operator[](&v315, &v339);
          web::json::value::operator=(v283, v282);
          std::wstring::_Tidy_deallocate(&v339);
          if ( v335 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v335 + 192LL))(v335, 1);
          winrt::hstring::~hstring((winrt::hstring *)&v341);
          if ( v313 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
        }
        v284 = web::json::value::operator[](&v314, v258++);
        web::json::value::operator=(v284, &v315);
        if ( v315 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v315 + 192LL))(v315, 1);
        if ( v318 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v318);
        ++v259;
      }
      if ( v261 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v316);
      std::wstring::wstring(&v339, L"LocalizationInfo");
      v285 = web::json::value::operator[](&v326, &v339);
      web::json::value::operator=(v285, &v314);
      std::wstring::_Tidy_deallocate(&v339);
      if ( v314 )
        (*(void (__fastcall **)(_QWORD *, __int64))(*v314 + 192LL))(v314, 1);
      v251 = v327;
    }
    v286 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                        v251,
                        &v313);
    if ( v313 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
    if ( v286 )
    {
      v287 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v251,
               &lpMem);
      v253 |= 0x80u;
      v319 = v253;
      if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v287) < 0
        || (v289 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                     v251,
                     &v313),
            v253 |= 0x100u,
            v319 = v253,
            v290 = 0,
            (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v289) > 30) )
      {
        v290 = 1;
      }
      if ( (v253 & 0x100) != 0 )
      {
        v253 &= ~0x100u;
        if ( v313 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
      }
      if ( (v253 & 0x80u) != 0 )
      {
        v253 &= ~0x80u;
        if ( lpMem )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      }
      if ( v290 )
      {
        v312 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v341, v288);
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)&v339,
          L"ComplianceDeadlineInDays must be a non-negative value less than or equal to 30 days.");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)pExceptionObject,
          (const struct winrt::param::hstring *)&v339,
          v312);
        throw (winrt::hresult_invalid_argument *)pExceptionObject;
      }
      v291 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v251,
               &v313);
      v292 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v291);
      v293 = web::json::value::number(&v341, v292);
      std::wstring::wstring(&v339, L"ComplianceDeadlineInDays");
      v294 = web::json::value::operator[](&v326, &v339);
      web::json::value::operator=(v294, v293);
      std::wstring::_Tidy_deallocate(&v339);
      if ( (_QWORD)v341 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v341 + 192LL))(v341, 1);
      if ( v313 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
    }
    v295 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                        v251,
                        &v313);
    if ( v313 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
    if ( v295 )
    {
      v296 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
               v251,
               &lpMem);
      v297 = v253 | 0x200;
      v319 = v297;
      if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v296) < 0
        || (v299 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
                     v251,
                     &v313),
            v297 |= 0x400u,
            v319 = v297,
            v300 = 0,
            (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v299) > 7) )
      {
        v300 = 1;
      }
      if ( (v297 & 0x400) != 0 )
      {
        LOWORD(v297) = v297 & 0xFBFF;
        if ( v313 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
      }
      if ( (v297 & 0x200) != 0 && lpMem )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      if ( v300 )
      {
        v308 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v341, v298);
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)&v339,
          L"ComplianceGracePeriodInDays must be a non-negative value less than or equal to 7 days.");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)pExceptionObject,
          (const struct winrt::param::hstring *)&v339,
          v308);
        throw (winrt::hresult_invalid_argument *)pExceptionObject;
      }
      v301 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateLocalizationInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfo>::Description(
               v251,
               &v313);
      v302 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v301);
      v303 = web::json::value::number(&v341, v302);
      std::wstring::wstring(&v339, L"ComplianceGracePeriodInDays");
      v304 = web::json::value::operator[](&v326, &v339);
      web::json::value::operator=(v304, v303);
      std::wstring::_Tidy_deallocate(&v339);
      if ( (_QWORD)v341 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v341 + 192LL))(v341, 1);
      if ( v313 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v313);
    }
    std::wstring::wstring(&v339, L"OptionalInfo");
    v305 = web::json::value::operator[](&v321, &v339);
    web::json::value::operator=(v305, &v326);
    std::wstring::_Tidy_deallocate(&v339);
    if ( v326 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v326 + 192LL))(v326, 1);
  }
  v306 = v336;
  web::json::value::serialize(&v321, v336);
  if ( v321 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v321 + 192LL))(v321, 1);
  return v306;
}

```

## disassembly

```asm
0x180018440  push    rbp
0x180018442  push    rbx
0x180018443  push    rsi
0x180018444  push    rdi
0x180018445  push    r12
0x180018447  push    r13
0x180018449  push    r14
0x18001844b  push    r15
0x18001844d  lea     rbp, [rsp-68h]
0x180018452  sub     rsp, 168h
0x180018459  mov     rax, cs:__security_cookie
0x180018460  xor     rax, rsp
0x180018463  mov     [rbp+0A0h+var_50], rax
0x180018467  mov     rdi, r9
0x18001846a  mov     [rsp+1A0h+var_178], r8
0x18001846f  mov     rbx, rdx
0x180018472  mov     r9, rcx
0x180018475  mov     [rbp+0A0h+var_B0], rcx
0x180018479  mov     rax, [rbp+0A0h+arg_68]
0x180018480  mov     [rbp+0A0h+var_100], rax
0x180018484  mov     rdx, [rbp+0A0h+arg_60]
0x18001848b  mov     [rsp+1A0h+var_160], rdx
0x180018490  mov     rcx, [rbp+0A0h+arg_58]
0x180018497  mov     [rsp+1A0h+var_148], rcx
0x18001849c  mov     rax, [rbp+0A0h+arg_78]
0x1800184a3  mov     [rsp+1A0h+var_170], rax
0x1800184a8  mov     rax, [rbp+0A0h+arg_70]
0x1800184af  mov     [rbp+0A0h+var_108], rax
0x1800184b3  mov     rax, [rbp+0A0h+arg_50]
0x1800184ba  mov     [rsp+1A0h+var_168], rax
0x1800184bf  mov     r12, [rbp+0A0h+arg_48]
0x1800184c6  mov     r14, [rbp+0A0h+arg_28]
0x1800184cd  mov     rsi, [rbp+0A0h+arg_20]
0x1800184d4  mov     r15, [rbp+0A0h+arg_30]
0x1800184db  mov     qword ptr [rbp+0A0h+var_68], r9
0x1800184df  mov     r13, [rbp+0A0h+arg_38]
0x1800184e6  mov     rax, [rbp+0A0h+arg_40]
0x1800184ed  mov     [rbp+0A0h+var_110], rax
0x1800184f1  xor     r9d, r9d
0x1800184f4  mov     [rsp+1A0h+var_150], r9d
0x1800184f9  cmp     [rbx], r9
0x1800184fc  jz      loc_18001B75D
0x180018502  cmp     [rdi], r9
0x180018505  jz      loc_18001B75D
0x18001850b  cmp     [rsi], r9
0x18001850e  jz      loc_18001B75D
0x180018514  cmp     [r14], r9
0x180018517  jz      loc_18001B75D
0x18001851d  cmp     [r15], r9
0x180018520  jz      loc_18001B75D
0x180018526  mov     eax, [r8]
0x180018529  cmp     eax, 1
0x18001852c  jnz     short loc_180018539
0x18001852e  cmp     [rcx], r9
0x180018531  jz      loc_18001B71E
0x180018537  jmp     short loc_18001854A
0x180018539  add     eax, 0FFFFFFFEh
0x18001853c  cmp     eax, 1
0x18001853f  ja      short loc_18001854A
0x180018541  cmp     [rdx], r9
0x180018544  jz      loc_18001B79C
0x18001854a  xor     edx, edx
0x18001854c  lea     rcx, [rsp+1A0h+var_140]
0x180018551  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180018556  nop
0x180018557  mov     rax, [rbx]
0x18001855a  xor     ecx, ecx
0x18001855c  test    rax, rax
0x18001855f  jz      short loc_180018567
0x180018561  mov     rdx, [rax+10h]
0x180018565  jmp     short loc_18001856E
0x180018567  lea     rdx, dword_18002EB94
0x18001856e  xorps   xmm0, xmm0
0x180018571  movups  [rsp+1A0h+pExceptionObject], xmm0
0x180018576  mov     [rbp+0A0h+var_120], rcx
0x18001857a  mov     [rbp+0A0h+var_118], rcx
0x18001857e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018582  inc     r8
0x180018585  cmp     [rdx+r8*2], cx
0x18001858a  jnz     short loc_180018582
0x18001858c  lea     rcx, [rsp+1A0h+pExceptionObject]
0x180018591  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018596  lea     rdx, [rsp+1A0h+pExceptionObject]
0x18001859b  lea     rcx, [rsp+1A0h+var_180]
0x1800185a0  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800185a5  mov     rbx, rax
0x1800185a8  xorps   xmm0, xmm0
0x1800185ab  movups  [rbp+0A0h+var_A8], xmm0
0x1800185af  xorps   xmm1, xmm1
0x1800185b2  movdqu  [rbp+0A0h+var_98], xmm1
0x1800185b7  mov     r8d, 0Ah
0x1800185bd  lea     rdx, aProviderid; "ProviderId"
0x1800185c4  lea     rcx, [rbp+0A0h+var_A8]
0x1800185c8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800185cd  nop
0x1800185ce  lea     rdx, [rbp+0A0h+var_A8]
0x1800185d2  lea     rcx, [rsp+1A0h+var_140]
0x1800185d7  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800185dc  mov     rcx, rax
0x1800185df  mov     rdx, rbx
0x1800185e2  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800185e7  nop
0x1800185e8  lea     rcx, [rbp+0A0h+var_A8]
0x1800185ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800185f1  nop
0x1800185f2  mov     rcx, [rsp+1A0h+var_180]
0x1800185f7  test    rcx, rcx
0x1800185fa  jz      short loc_180018610
0x1800185fc  mov     rax, [rcx]
0x1800185ff  mov     edx, 1
0x180018604  mov     rax, [rax+0C0h]
0x18001860b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018610  mov     rdx, [rsp+1A0h+var_178]
0x180018615  mov     edx, [rdx]
0x180018617  lea     rcx, [rsp+1A0h+var_180]
0x18001861c  call    ?number@value@json@web@@SA?AV123@H@Z; web::json::value::number(int)
0x180018621  mov     rbx, rax
0x180018624  xorps   xmm0, xmm0
0x180018627  movups  [rbp+0A0h+var_A8], xmm0
0x18001862b  xorps   xmm1, xmm1
0x18001862e  movdqu  [rbp+0A0h+var_98], xmm1
0x180018633  mov     r8d, 10h
0x180018639  lea     rdx, aInstallationty; "InstallationType"
0x180018640  lea     rcx, [rbp+0A0h+var_A8]
0x180018644  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018649  nop
0x18001864a  lea     rdx, [rbp+0A0h+var_A8]
0x18001864e  lea     rcx, [rsp+1A0h+var_140]
0x180018653  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180018658  mov     rcx, rax
0x18001865b  mov     rdx, rbx
0x18001865e  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180018663  nop
0x180018664  lea     rcx, [rbp+0A0h+var_A8]
0x180018668  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001866d  nop
0x18001866e  mov     rcx, [rsp+1A0h+var_180]
0x180018673  test    rcx, rcx
0x180018676  jz      short loc_18001868C
0x180018678  mov     rax, [rcx]
0x18001867b  mov     edx, 1
0x180018680  mov     rax, [rax+0C0h]
0x180018687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001868c  mov     rax, [rdi]
0x18001868f  xor     edi, edi
0x180018691  test    rax, rax
0x180018694  jz      short loc_18001869C
0x180018696  mov     rdx, [rax+10h]
0x18001869a  jmp     short loc_1800186A3
0x18001869c  lea     rdx, dword_18002EB94
0x1800186a3  xorps   xmm0, xmm0
0x1800186a6  movups  [rsp+1A0h+pExceptionObject], xmm0
0x1800186ab  mov     [rbp+0A0h+var_120], rdi
0x1800186af  mov     [rbp+0A0h+var_118], rdi
0x1800186b3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800186b7  inc     r8
0x1800186ba  cmp     [rdx+r8*2], di
0x1800186bf  jnz     short loc_1800186B7
0x1800186c1  lea     rcx, [rsp+1A0h+pExceptionObject]
0x1800186c6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800186cb  lea     rdx, [rsp+1A0h+pExceptionObject]
0x1800186d0  lea     rcx, [rsp+1A0h+var_180]
0x1800186d5  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800186da  mov     rbx, rax
0x1800186dd  xorps   xmm0, xmm0
0x1800186e0  movups  [rbp+0A0h+var_A8], xmm0
0x1800186e4  xorps   xmm1, xmm1
0x1800186e7  movdqu  [rbp+0A0h+var_98], xmm1
0x1800186ec  mov     r8d, 8
0x1800186f2  lea     rdx, aUpdateid; "UpdateId"
0x1800186f9  lea     rcx, [rbp+0A0h+var_A8]
0x1800186fd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018702  nop
0x180018703  lea     rdx, [rbp+0A0h+var_A8]
0x180018707  lea     rcx, [rsp+1A0h+var_140]
0x18001870c  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180018711  mov     rcx, rax
0x180018714  mov     rdx, rbx
0x180018717  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18001871c  nop
0x18001871d  lea     rcx, [rbp+0A0h+var_A8]
0x180018721  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018726  nop
0x180018727  mov     rcx, [rsp+1A0h+var_180]
0x18001872c  test    rcx, rcx
0x18001872f  jz      short loc_180018745
0x180018731  mov     rax, [rcx]
0x180018734  mov     edx, 1
0x180018739  mov     rax, [rax+0C0h]
0x180018740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018745  mov     rax, [rsi]
0x180018748  lea     rsi, dword_18002EB94
0x18001874f  test    rax, rax
0x180018752  jz      short loc_18001875A
0x180018754  mov     rdx, [rax+10h]
0x180018758  jmp     short loc_18001875D
0x18001875a  mov     rdx, rsi
0x18001875d  xorps   xmm0, xmm0
0x180018760  movups  [rsp+1A0h+pExceptionObject], xmm0
0x180018765  mov     [rbp+0A0h+var_120], rdi
0x180018769  mov     [rbp+0A0h+var_118], rdi
0x18001876d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018771  inc     r8
0x180018774  cmp     [rdx+r8*2], di
0x180018779  jnz     short loc_180018771
0x18001877b  lea     rcx, [rsp+1A0h+pExceptionObject]
0x180018780  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018785  lea     rdx, [rsp+1A0h+pExceptionObject]
0x18001878a  lea     rcx, [rsp+1A0h+var_180]
0x18001878f  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180018794  mov     rbx, rax
0x180018797  xorps   xmm0, xmm0
0x18001879a  movups  [rbp+0A0h+var_A8], xmm0
0x18001879e  xorps   xmm1, xmm1
0x1800187a1  movdqu  [rbp+0A0h+var_98], xmm1
0x1800187a6  mov     r8d, 5
0x1800187ac  lea     rdx, aTitle_0; "Title"
0x1800187b3  lea     rcx, [rbp+0A0h+var_A8]
0x1800187b7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800187bc  nop
0x1800187bd  lea     rdx, [rbp+0A0h+var_A8]
0x1800187c1  lea     rcx, [rsp+1A0h+var_140]
0x1800187c6  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800187cb  mov     rcx, rax
0x1800187ce  mov     rdx, rbx
0x1800187d1  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800187d6  nop
0x1800187d7  lea     rcx, [rbp+0A0h+var_A8]
0x1800187db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800187e0  nop
0x1800187e1  mov     rcx, [rsp+1A0h+var_180]
0x1800187e6  test    rcx, rcx
0x1800187e9  jz      short loc_1800187FF
0x1800187eb  mov     rax, [rcx]
0x1800187ee  mov     edx, 1
0x1800187f3  mov     rax, [rax+0C0h]
0x1800187fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ff  mov     rax, [r14]
0x180018802  test    rax, rax
0x180018805  jz      short loc_18001880D
0x180018807  mov     rdx, [rax+10h]
0x18001880b  jmp     short loc_180018810
0x18001880d  mov     rdx, rsi
0x180018810  xorps   xmm0, xmm0
0x180018813  movups  [rsp+1A0h+pExceptionObject], xmm0
0x180018818  mov     [rbp+0A0h+var_120], rdi
0x18001881c  mov     [rbp+0A0h+var_118], rdi
0x180018820  or      r14, 0FFFFFFFFFFFFFFFFh
0x180018824  mov     r8, r14
0x180018827  inc     r8
0x18001882a  cmp     [rdx+r8*2], di
0x18001882f  jnz     short loc_180018827
0x180018831  lea     rcx, [rsp+1A0h+pExceptionObject]
0x180018836  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001883b  lea     rdx, [rsp+1A0h+pExceptionObject]
0x180018840  lea     rcx, [rsp+1A0h+var_180]
0x180018845  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x18001884a  mov     rbx, rax
0x18001884d  xorps   xmm0, xmm0
0x180018850  movups  [rbp+0A0h+var_A8], xmm0
0x180018854  xorps   xmm1, xmm1
0x180018857  movdqu  [rbp+0A0h+var_98], xmm1
0x18001885c  mov     r8d, 0Bh
0x180018862  lea     rdx, aDescription_0; "Description"
0x180018869  lea     rcx, [rbp+0A0h+var_A8]
0x18001886d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018872  nop
0x180018873  lea     rdx, [rbp+0A0h+var_A8]
0x180018877  lea     rcx, [rsp+1A0h+var_140]
0x18001887c  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180018881  mov     rcx, rax
0x180018884  mov     rdx, rbx
0x180018887  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x18001888c  nop
0x18001888d  lea     rcx, [rbp+0A0h+var_A8]
0x180018891  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018896  nop
0x180018897  mov     rcx, [rsp+1A0h+var_180]
0x18001889c  test    rcx, rcx
0x18001889f  jz      short loc_1800188B5
0x1800188a1  mov     rax, [rcx]
0x1800188a4  mov     edx, 1
0x1800188a9  mov     rax, [rax+0C0h]
0x1800188b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188b5  lea     rdx, [rsp+1A0h+lpMem]
0x1800188ba  mov     rcx, r15
0x1800188bd  call    ?RawUri@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(void)
0x1800188c2  nop
0x1800188c3  mov     rdx, [rax]
0x1800188c6  test    rdx, rdx
0x1800188c9  jz      short loc_1800188D1
0x1800188cb  mov     rdx, [rdx+10h]
0x1800188cf  jmp     short loc_1800188D4
0x1800188d1  mov     rdx, rsi
0x1800188d4  xorps   xmm0, xmm0
0x1800188d7  movups  [rsp+1A0h+pExceptionObject], xmm0
0x1800188dc  mov     [rbp+0A0h+var_120], rdi
0x1800188e0  mov     [rbp+0A0h+var_118], rdi
0x1800188e4  mov     r8, r14
0x1800188e7  inc     r8
  ... truncated ...
```
