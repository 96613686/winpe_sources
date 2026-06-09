# UniDrvUI::CPrintTicketProvider::GetPrintDeviceResources(ushort const *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *)

- ea: `0x1800f3f60`
- end: `0x1800f5aee`
- name: `?GetPrintDeviceResources@CPrintTicketProvider@UniDrvUI@@UEAAJPEBGPEAUIXMLDOMDocument2@@PEAPEAU3@@Z`
- size: `7054`
- prototype: `int(UniDrvUI::CPrintTicketProvider *__hidden this, const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x180006430`
- `0x18000b274`
- `0x18000b29c`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x180018a28`
- `0x18001f0a8`
- `0x180066110`
- `0x180069f68`
- `0x18006e0dc`
- `0x1800707fc`
- `0x1800e831c`
- `0x1800e9848`
- `0x1800ea1c0`
- `0x1800ea780`
- `0x1800f3f60`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetThreadPreferredUILanguages` at `0x1800f3fd3`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x1800f403f`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x1800f3fd3`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x1800f403f`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x1800f5a5f`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x1800f5a5f`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x1800f4083`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x1800f4083`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800f407b`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800f407b`
- `ole32!CoTaskMemAlloc` at `0x1800f4007`
- `ole32!CoTaskMemAlloc` at `0x1800f4007`
- `ole32!CoTaskMemFree` at `0x1800f4067`
- `ole32!CoTaskMemFree` at `0x1800f5a6e`
- `ole32!CoTaskMemFree` at `0x1800f4067`
- `ole32!CoTaskMemFree` at `0x1800f5a6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall UniDrvUI::CPrintTicketProvider::GetPrintDeviceResources(
        UniDrvUI::CPrintTicketProvider *this,
        const unsigned __int16 *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMDocument2 **a4)
{
  int v7; // r13d
  const char *v9; // r9
  __int64 v10; // rbx
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  const char *v13; // r9
  unsigned int LastError; // ebx
  LANGID v15; // ax
  int v16; // eax
  __int64 *v17; // rax
  __int64 v18; // rsi
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rax
  __int64 **v21; // r14
  volatile signed __int32 *v22; // rbx
  __int64 *v23; // rsi
  __int64 *v24; // rax
  __int64 *v25; // rbx
  __int64 inited; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // rcx
  __int64 *v30; // rcx
  __int64 v31; // rax
  volatile signed __int32 *v32; // r14
  __int64 *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rdx
  int v36; // r13d
  __int64 v37; // rax
  __int64 *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // r13d
  __int64 v42; // rax
  __int64 *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  int v46; // r13d
  __int64 v47; // rax
  _QWORD *v48; // rcx
  int v49; // r13d
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rax
  _QWORD *v53; // rcx
  int v54; // r13d
  __int64 v55; // rax
  __int64 v56; // r12
  __int64 v57; // rax
  volatile signed __int32 *v58; // rcx
  char v59; // si
  volatile signed __int32 *v60; // rbx
  volatile signed __int32 *v61; // rbx
  volatile signed __int32 *v62; // rbx
  volatile signed __int32 *v63; // rbx
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rbx
  volatile signed __int32 *v66; // rbx
  volatile signed __int32 *v67; // rbx
  volatile signed __int32 *v68; // rbx
  volatile signed __int32 *v69; // rbx
  volatile signed __int32 *v70; // rbx
  volatile signed __int32 *v71; // rbx
  __int64 *v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rcx
  volatile signed __int32 *v75; // r14
  __int64 v76; // rax
  __int64 v77; // rax
  volatile signed __int32 *v78; // rsi
  __int64 v79; // rcx
  _QWORD *v80; // rdx
  volatile signed __int32 *v81; // rbx
  unsigned __int64 v82; // r8
  __int128 *p_Src; // rax
  __int64 *v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rbx
  volatile signed __int32 *v87; // rsi
  __int64 v88; // rax
  _QWORD *v89; // rdx
  volatile signed __int32 *v90; // rbx
  __int64 v91; // rax
  volatile signed __int32 *v92; // r14
  char v93; // si
  volatile signed __int32 *v94; // rbx
  __int64 v95; // rax
  volatile signed __int32 *v96; // rsi
  __int64 v97; // r8
  volatile signed __int32 *v98; // rbx
  __int64 v99; // rbx
  __int64 v100; // rax
  __int64 **v101; // rsi
  volatile signed __int32 *v102; // rbx
  __int64 *v103; // r12
  __int64 *v104; // rax
  __int64 *v105; // rbx
  __int64 v106; // rcx
  __int64 v107; // rax
  char v108; // si
  _QWORD *v109; // rdx
  __int64 v110; // rcx
  __int64 *v111; // rcx
  __int64 v112; // rax
  volatile signed __int32 *v113; // r14
  __int64 *v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rdx
  int v117; // r13d
  __int64 v118; // rax
  __int64 *v119; // rcx
  __int64 v120; // rax
  __int64 v121; // rdx
  int v122; // r13d
  __int64 v123; // rax
  __int64 *v124; // rcx
  __int64 v125; // rax
  __int64 v126; // rdx
  int v127; // r13d
  __int64 v128; // rax
  _QWORD *v129; // rcx
  int v130; // r13d
  __int64 v131; // rax
  __int64 v132; // rcx
  __int64 v133; // rax
  _QWORD *v134; // rdx
  int v135; // r13d
  __int64 v136; // rax
  __int64 v137; // r12
  __int64 v138; // rax
  volatile signed __int32 *v139; // rcx
  volatile signed __int32 *v140; // rbx
  volatile signed __int32 *v141; // rbx
  volatile signed __int32 *v142; // rbx
  volatile signed __int32 *v143; // rbx
  volatile signed __int32 *v144; // rbx
  volatile signed __int32 *v145; // rbx
  volatile signed __int32 *v146; // rbx
  volatile signed __int32 *v147; // rbx
  volatile signed __int32 *v148; // rbx
  volatile signed __int32 *v149; // rbx
  volatile signed __int32 *v150; // rbx
  volatile signed __int32 *v151; // rbx
  __int64 *v152; // rcx
  __int64 v153; // rax
  __int64 v154; // rdx
  volatile signed __int32 *v155; // r14
  __int64 v156; // rax
  __int64 v157; // rcx
  volatile signed __int32 *v158; // rsi
  __int64 v159; // rax
  _QWORD *v160; // rdx
  volatile signed __int32 *v161; // rbx
  unsigned __int64 v162; // r8
  __int128 *v163; // rax
  __int64 *v164; // rcx
  __int64 v165; // rax
  __int64 v166; // rax
  volatile signed __int32 *v167; // rsi
  __int64 v168; // rcx
  _QWORD *v169; // rdx
  volatile signed __int32 *v170; // rbx
  __int64 v171; // rax
  volatile signed __int32 *v172; // r14
  char v173; // si
  volatile signed __int32 *v174; // rbx
  __int64 v175; // rax
  volatile signed __int32 *v176; // rsi
  __int64 v177; // r8
  volatile signed __int32 *v178; // rbx
  volatile signed __int32 *v179; // rbx
  struct IXMLDOMDocument2 *v180; // rbx
  __int64 v181; // rcx
  WCHAR *v182; // rbx
  unsigned int v183; // [rsp+28h] [rbp-4A0h]
  ULONG pcchLanguagesBuffer; // [rsp+2Ch] [rbp-49Ch] BYREF
  ULONG pulNumLanguages; // [rsp+30h] [rbp-498h] BYREF
  __int64 *v186; // [rsp+38h] [rbp-490h]
  __int64 *v187; // [rsp+40h] [rbp-488h]
  __int64 v188; // [rsp+48h] [rbp-480h] BYREF
  __int64 *i; // [rsp+50h] [rbp-478h]
  __int64 v190; // [rsp+58h] [rbp-470h] BYREF
  volatile signed __int32 *v191; // [rsp+60h] [rbp-468h]
  __int128 v192; // [rsp+68h] [rbp-460h] BYREF
  __int128 v193; // [rsp+78h] [rbp-450h] BYREF
  __int64 *v194; // [rsp+88h] [rbp-440h]
  struct IXMLDOMDocument2 **v195; // [rsp+90h] [rbp-438h]
  PCZZWSTR pwszLanguagesBuffer; // [rsp+98h] [rbp-430h]
  __int64 v197; // [rsp+A0h] [rbp-428h] BYREF
  volatile signed __int32 *v198; // [rsp+A8h] [rbp-420h]
  _QWORD v199[3]; // [rsp+B0h] [rbp-418h] BYREF
  volatile signed __int32 *v200; // [rsp+C8h] [rbp-400h]
  _QWORD *v201; // [rsp+D0h] [rbp-3F8h]
  volatile signed __int32 *v202; // [rsp+D8h] [rbp-3F0h]
  _QWORD v203[2]; // [rsp+E0h] [rbp-3E8h] BYREF
  _QWORD v204[2]; // [rsp+F0h] [rbp-3D8h] BYREF
  __int64 v205; // [rsp+100h] [rbp-3C8h]
  volatile signed __int32 *v206; // [rsp+108h] [rbp-3C0h]
  __int64 v207; // [rsp+110h] [rbp-3B8h]
  volatile signed __int32 *v208; // [rsp+118h] [rbp-3B0h]
  __int64 v209; // [rsp+120h] [rbp-3A8h]
  volatile signed __int32 *v210; // [rsp+128h] [rbp-3A0h]
  _QWORD *v211; // [rsp+130h] [rbp-398h]
  volatile signed __int32 *v212; // [rsp+138h] [rbp-390h]
  __int64 v213; // [rsp+140h] [rbp-388h]
  volatile signed __int32 *v214; // [rsp+148h] [rbp-380h]
  _QWORD *v215; // [rsp+150h] [rbp-378h]
  volatile signed __int32 *v216; // [rsp+158h] [rbp-370h]
  __int64 v217; // [rsp+160h] [rbp-368h]
  volatile signed __int32 *v218; // [rsp+168h] [rbp-360h]
  __int64 v219; // [rsp+170h] [rbp-358h]
  volatile signed __int32 *v220; // [rsp+178h] [rbp-350h]
  __int64 v221; // [rsp+180h] [rbp-348h]
  volatile signed __int32 *v222; // [rsp+188h] [rbp-340h]
  __int64 v223; // [rsp+190h] [rbp-338h]
  volatile signed __int32 *v224; // [rsp+198h] [rbp-330h]
  __int64 v225; // [rsp+1A0h] [rbp-328h]
  volatile signed __int32 *v226; // [rsp+1A8h] [rbp-320h]
  _QWORD v227[2]; // [rsp+1B0h] [rbp-318h] BYREF
  __int64 v228; // [rsp+1C0h] [rbp-308h]
  volatile signed __int32 *v229; // [rsp+1C8h] [rbp-300h]
  __int64 v230; // [rsp+1D0h] [rbp-2F8h]
  volatile signed __int32 *v231; // [rsp+1D8h] [rbp-2F0h]
  __int64 v232; // [rsp+1E0h] [rbp-2E8h]
  volatile signed __int32 *v233; // [rsp+1E8h] [rbp-2E0h]
  __int64 v234; // [rsp+1F0h] [rbp-2D8h]
  volatile signed __int32 *v235; // [rsp+1F8h] [rbp-2D0h]
  __int64 v236; // [rsp+200h] [rbp-2C8h]
  volatile signed __int32 *v237; // [rsp+208h] [rbp-2C0h]
  _QWORD *v238; // [rsp+210h] [rbp-2B8h]
  volatile signed __int32 *v239; // [rsp+218h] [rbp-2B0h]
  __int64 v240; // [rsp+220h] [rbp-2A8h]
  volatile signed __int32 *v241; // [rsp+228h] [rbp-2A0h]
  __int64 v242; // [rsp+230h] [rbp-298h]
  volatile signed __int32 *v243; // [rsp+238h] [rbp-290h]
  __int64 v244; // [rsp+240h] [rbp-288h]
  volatile signed __int32 *v245; // [rsp+248h] [rbp-280h]
  __int64 v246; // [rsp+250h] [rbp-278h]
  volatile signed __int32 *v247; // [rsp+258h] [rbp-270h]
  __int64 v248; // [rsp+260h] [rbp-268h]
  const hr_error *v249; // [rsp+268h] [rbp-260h] BYREF
  const PrintCore::WindowsError *v250; // [rsp+270h] [rbp-258h] BYREF
  __int64 v251; // [rsp+278h] [rbp-250h]
  volatile signed __int32 *v252; // [rsp+280h] [rbp-248h]
  char v253[8]; // [rsp+288h] [rbp-240h] BYREF
  volatile signed __int32 *v254; // [rsp+290h] [rbp-238h]
  __int64 v255; // [rsp+298h] [rbp-230h]
  volatile signed __int32 *v256; // [rsp+2A0h] [rbp-228h]
  __int64 v257; // [rsp+2A8h] [rbp-220h]
  volatile signed __int32 *v258; // [rsp+2B0h] [rbp-218h]
  _QWORD *v259; // [rsp+2B8h] [rbp-210h]
  volatile signed __int32 *v260; // [rsp+2C0h] [rbp-208h]
  __int64 v261; // [rsp+2C8h] [rbp-200h]
  volatile signed __int32 *v262; // [rsp+2D0h] [rbp-1F8h]
  _QWORD *v263; // [rsp+2D8h] [rbp-1F0h]
  volatile signed __int32 *v264; // [rsp+2E0h] [rbp-1E8h]
  char v265[8]; // [rsp+2E8h] [rbp-1E0h] BYREF
  volatile signed __int32 *v266; // [rsp+2F0h] [rbp-1D8h]
  __int64 v267; // [rsp+2F8h] [rbp-1D0h]
  volatile signed __int32 *v268; // [rsp+300h] [rbp-1C8h]
  char v269[8]; // [rsp+308h] [rbp-1C0h] BYREF
  volatile signed __int32 *v270; // [rsp+310h] [rbp-1B8h]
  __int64 v271; // [rsp+318h] [rbp-1B0h]
  volatile signed __int32 *v272; // [rsp+320h] [rbp-1A8h]
  char v273[8]; // [rsp+328h] [rbp-1A0h] BYREF
  volatile signed __int32 *v274; // [rsp+330h] [rbp-198h]
  __int64 v275; // [rsp+338h] [rbp-190h]
  volatile signed __int32 *v276; // [rsp+340h] [rbp-188h]
  __int64 v277; // [rsp+348h] [rbp-180h]
  volatile signed __int32 *v278; // [rsp+350h] [rbp-178h]
  _QWORD *v279; // [rsp+358h] [rbp-170h]
  volatile signed __int32 *v280; // [rsp+360h] [rbp-168h]
  __int64 v281; // [rsp+368h] [rbp-160h]
  volatile signed __int32 *v282; // [rsp+370h] [rbp-158h]
  _QWORD *v283; // [rsp+378h] [rbp-150h]
  volatile signed __int32 *v284; // [rsp+380h] [rbp-148h]
  char v285[8]; // [rsp+388h] [rbp-140h] BYREF
  volatile signed __int32 *v286; // [rsp+390h] [rbp-138h]
  __int64 v287; // [rsp+398h] [rbp-130h]
  volatile signed __int32 *v288; // [rsp+3A0h] [rbp-128h]
  char v289[8]; // [rsp+3A8h] [rbp-120h] BYREF
  volatile signed __int32 *v290; // [rsp+3B0h] [rbp-118h]
  _BYTE v291[24]; // [rsp+3B8h] [rbp-110h] BYREF
  struct IXMLDOMDocument2 *v292; // [rsp+3D0h] [rbp-F8h]
  _BYTE pExceptionObject[32]; // [rsp+3E0h] [rbp-E8h] BYREF
  _QWORD v294[4]; // [rsp+400h] [rbp-C8h] BYREF
  _QWORD v295[4]; // [rsp+420h] [rbp-A8h] BYREF
  __int128 Src; // [rsp+440h] [rbp-88h] BYREF
  __int64 v297; // [rsp+450h] [rbp-78h]
  unsigned __int64 v298; // [rsp+458h] [rbp-70h]
  __int128 v299; // [rsp+460h] [rbp-68h] BYREF
  __int64 v300; // [rsp+470h] [rbp-58h]
  unsigned __int64 v301; // [rsp+478h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+0h]

  v248 = -2;
  v195 = a4;
  v7 = 0;
  if ( !a4 )
    return 2147500035LL;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xA7F,
             (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
             v9);
  v10 = pcchLanguagesBuffer;
  v11 = (WCHAR *)CoTaskMemAlloc(2LL * pcchLanguagesBuffer + 2);
  v12 = v11;
  if ( v11 )
  {
    *v11 = 0;
    v11[v10] = 0;
  }
  pwszLanguagesBuffer = v11;
  if ( !v11 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA82,
      (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
      (const char *)0x8007000ELL,
      0);
    return LastError;
  }
  if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, v11, &pcchLanguagesBuffer) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA86,
                  (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
                  v13);
    CoTaskMemFree(v12);
    return LastError;
  }
  v183 = 0;
  v15 = LocaleNameToLCID(a2, 0);
  SetThreadUILanguage(v15);
  try
  {
    v188 = 0;
    v16 = (*(__int64 (__fastcall **)(UniDrvUI::CPrintTicketProvider *, struct IXMLDOMDocument2 *, __int64 *))(*(_QWORD *)this + 64LL))(
            this,
            a3,
            &v188);
    if ( v16 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v16);
      throw (hr_error *)pExceptionObject;
    }
    v17 = std::make_shared<PrintDeviceCapabilitiesOM::PrintCapabilities,Microsoft::WRL::ComPtr<IXMLDOMDocument2> &>(
            &v190,
            (__int64)&v188);
    v18 = *v17;
    v203[0] = *v17;
    v203[1] = v17[1];
    *v17 = 0;
    v17[1] = 0;
    v19 = v191;
    if ( v191 )
    {
      if ( _InterlockedExchangeAdd(v191 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::PrintDeviceResourcesSerializer((PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer *)v291);
    v20 = *(_QWORD *)(v18 + 8);
    if ( v20 )
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
    v21 = *(__int64 ***)v18;
    v22 = *(volatile signed __int32 **)(v18 + 8);
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
    v23 = *v21;
    v24 = v21[1];
    v194 = v24;
LABEL_23:
    v186 = v23;
    if ( v23 != v24 )
    {
      v25 = (__int64 *)*v23;
      inited = PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(0);
      v192 = 0;
      v27 = *(_QWORD *)(inited + 8);
      if ( v27 )
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
      v192 = *(_OWORD *)inited;
      v28 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v294, (__int64)L"DisplayName", (__int64)&v192);
      v29 = v25[5];
      if ( v29 )
        _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
      v204[0] = v25[4];
      v204[1] = v25[5];
      PrintDeviceCapabilitiesOM::Parser::GenericSearchVector<PrintDeviceCapabilitiesOM::Property const>(v199, v28, v204);
      PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v294);
      v30 = (__int64 *)*v23;
      v31 = *(_QWORD *)(*v23 + 8);
      if ( v31 )
        _InterlockedIncrement((volatile signed __int32 *)(v31 + 8));
      v251 = *v30;
      v32 = (volatile signed __int32 *)v30[1];
      v252 = v32;
      v7 |= 1u;
      if ( !v251 )
        goto LABEL_61;
      v33 = (__int64 *)*v23;
      v34 = *(_QWORD *)(*v23 + 8);
      if ( v34 )
        _InterlockedIncrement((volatile signed __int32 *)(v34 + 8));
      v35 = *v33;
      v223 = v35;
      v224 = (volatile signed __int32 *)v33[1];
      v36 = v7 | 2;
      v37 = *(_QWORD *)(v35 + 24);
      if ( v37 )
        _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
      v221 = *(_QWORD *)(v35 + 16);
      v222 = *(volatile signed __int32 **)(v35 + 24);
      v7 = v36 | 4;
      if ( !v221 )
        goto LABEL_61;
      v38 = (__int64 *)*v23;
      v39 = *(_QWORD *)(*v23 + 8);
      if ( v39 )
        _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
      v40 = *v38;
      v234 = v40;
      v235 = (volatile signed __int32 *)v38[1];
      v41 = v7 | 8;
      v42 = *(_QWORD *)(v40 + 24);
      if ( v42 )
        _InterlockedIncrement((volatile signed __int32 *)(v42 + 8));
      v219 = *(_QWORD *)(v40 + 16);
      v220 = *(volatile signed __int32 **)(v40 + 24);
      v7 = v41 | 0x10;
      if ( *(_DWORD *)(v219 + 16) != 8 )
        goto LABEL_61;
      v43 = (__int64 *)*v23;
      v44 = *(_QWORD *)(*v23 + 8);
      if ( v44 )
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 8));
      v45 = *v43;
      v217 = v45;
      v218 = (volatile signed __int32 *)v43[1];
      v46 = v7 | 0x20;
      v47 = *(_QWORD *)(v45 + 24);
      if ( v47 )
        _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
      v48 = *(_QWORD **)(v45 + 16);
      v215 = v48;
      v216 = *(volatile signed __int32 **)(v45 + 24);
      v49 = v46 | 0x40;
      v50 = v48[1];
      if ( v50 )
        _InterlockedIncrement((volatile signed __int32 *)(v50 + 8));
      v213 = *v48;
      v214 = (volatile signed __int32 *)v48[1];
      v7 = v49 | 0x80;
      if ( !v213 )
        goto LABEL_61;
      v51 = *v23;
      v52 = *(_QWORD *)(*v23 + 8);
      if ( v52 )
        _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
      v53 = *(_QWORD **)v51;
      v211 = v53;
      v212 = *(volatile signed __int32 **)(v51 + 8);
      v54 = v7 | 0x100;
      v55 = v53[1];
      if ( v55 )
        _InterlockedIncrement((volatile signed __int32 *)(v55 + 8));
      v209 = *v53;
      v210 = (volatile signed __int32 *)v53[1];
      v7 = v54 | 0x200;
      if ( v209 )
      {
        v56 = v199[0];
        if ( v199[0] )
        {
          v57 = *(_QWORD *)(v199[0] + 24LL);
          if ( v57 )
            _InterlockedIncrement((volatile signed __int32 *)(v57 + 8));
          v207 = *(_QWORD *)(v56 + 16);
          v58 = *(volatile signed __int32 **)(v56 + 24);
          v208 = v58;
          v7 |= 0x400u;
          if ( v207 )
          {
            if ( v58 )
              _InterlockedIncrement(v58 + 2);
            v205 = *(_QWORD *)(v56 + 16);
            v206 = *(volatile signed __int32 **)(v56 + 24);
            v7 |= 0x1800u;
            if ( *(_QWORD *)PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v205, v253) )
            {
              v59 = 1;
LABEL_63:
              if ( (v7 & 0x1000) != 0 )
              {
                v7 &= ~0x1000u;
                v60 = v254;
                if ( v254 )
                {
                  if ( _InterlockedExchangeAdd(v254 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
                    if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
                  }
                }
              }
              if ( (v7 & 0x800) != 0 )
              {
                v7 &= ~0x800u;
                v61 = v206;
                if ( v206 )
                {
                  if ( _InterlockedExchangeAdd(v206 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
                    if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
                  }
                }
              }
              if ( (v7 & 0x400) != 0 )
              {
                v7 &= ~0x400u;
                v62 = v208;
                if ( v208 )
                {
                  if ( _InterlockedExchangeAdd(v208 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
                    if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
                  }
                }
              }
              if ( (v7 & 0x200) != 0 )
              {
                v7 &= ~0x200u;
                v63 = v210;
                if ( v210 )
                {
                  if ( _InterlockedExchangeAdd(v210 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
                    if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
                  }
                }
              }
              if ( (v7 & 0x100) != 0 )
              {
                v7 &= ~0x100u;
                v64 = v212;
                if ( v212 )
                {
                  if ( _InterlockedExchangeAdd(v212 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
                    if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
                  }
                }
              }
              if ( (v7 & 0x80u) != 0 )
              {
                v7 &= ~0x80u;
                v65 = v214;
                if ( v214 )
                {
                  if ( _InterlockedExchangeAdd(v214 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
                    if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
                  }
                }
              }
              if ( (v7 & 0x40) != 0 )
              {
                v7 &= ~0x40u;
                v66 = v216;
                if ( v216 )
                {
                  if ( _InterlockedExchangeAdd(v216 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
                    if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
                  }
                }
              }
              if ( (v7 & 0x20) != 0 )
              {
                v7 &= ~0x20u;
                v67 = v218;
                if ( v218 )
                {
                  if ( _InterlockedExchangeAdd(v218 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
                    if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
                  }
                }
              }
              if ( (v7 & 0x10) != 0 )
              {
                v7 &= ~0x10u;
                v68 = v220;
                if ( v220 )
                {
                  if ( _InterlockedExchangeAdd(v220 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
                    if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
                  }
                }
              }
              if ( (v7 & 8) != 0 )
              {
                v7 &= ~8u;
                v69 = v235;
                if ( v235 )
                {
                  if ( _InterlockedExchangeAdd(v235 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
                    if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
                  }
                }
              }
              if ( (v7 & 4) != 0 )
              {
                v7 &= ~4u;
                v70 = v222;
                if ( v222 )
                {
                  if ( _InterlockedExchangeAdd(v222 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
                    if ( _InterlockedExchangeAdd(v70 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
                  }
                }
              }
              if ( (v7 & 2) != 0 )
              {
                v7 &= ~2u;
                v71 = v224;
                if ( v224 )
                {
                  if ( _InterlockedExchangeAdd(v224 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
                    if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
                  }
                }
              }
              if ( (v7 & 1) != 0 )
              {
                v7 &= ~1u;
                if ( v32 )
                {
                  if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
                    if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
                  }
                }
              }
              if ( !v59 )
                goto LABEL_199;
              v72 = (__int64 *)*v186;
              v73 = *(_QWORD *)(*v186 + 8);
              if ( v73 )
                _InterlockedIncrement((volatile signed __int32 *)(v73 + 8));
              v74 = *v72;
              v255 = v74;
              v75 = (volatile signed __int32 *)v72[1];
              v256 = v75;
              v76 = *(_QWORD *)(v74 + 24);
              if ( v76 )
                _InterlockedIncrement((volatile signed __int32 *)(v76 + 8));
              v77 = *(_QWORD *)(v74 + 16);
              v257 = v77;
              v78 = *(volatile signed __int32 **)(v74 + 24);
              v258 = v78;
              v79 = *(_QWORD *)(v77 + 8);
              if ( v79 )
                _InterlockedIncrement((volatile signed __int32 *)(v79 + 8));
              v80 = *(_QWORD **)v77;
              v259 = v80;
              v81 = *(volatile signed __int32 **)(v77 + 8);
              v260 = v81;
              if ( v80[3] > 7u )
                v80 = (_QWORD *)*v80;
              Src = 0;
              v297 = 0;
              v298 = 0;
              v82 = -1;
              do
                ++v82;
              while ( *((_WORD *)v80 + v82) );
              std::wstring::_Construct<1,unsigned short const *>((char **)&Src, v80, v82);
              if ( v81 )
              {
                if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v81)(v81);
                  if ( _InterlockedExchangeAdd(v81 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v81 + 8LL))(v81);
                }
              }
              if ( v78 )
              {
                if ( _InterlockedExchangeAdd(v78 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
                  if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
                }
              }
              if ( v75 )
              {
                if ( _InterlockedExchangeAdd(v75 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
                  if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
                }
              }
              if ( v297 )
              {
                p_Src = &Src;
                if ( v298 > 7 )
                  p_Src = (__int128 *)Src;
                if ( *((_WORD *)p_Src + v297 - 1) != 47 )
                  std::wstring::append(&Src, L"/");
              }
              v84 = (__int64 *)*v186;
              v85 = *(_QWORD *)(*v186 + 8);
              if ( v85 )
                _InterlockedIncrement((volatile signed __int32 *)(v85 + 8));
              v86 = *v84;
              v261 = v86;
              v87 = (volatile signed __int32 *)v84[1];
              v262 = v87;
              v88 = *(_QWORD *)(v86 + 8);
              if ( v88 )
                _InterlockedIncrement((volatile signed __int32 *)(v88 + 8));
              v89 = *(_QWORD **)v86;
              v263 = v89;
              v90 = *(volatile signed __int32 **)(v86 + 8);
              v264 = v90;
              if ( v89[3] > 7u )
                v89 = (_QWORD *)*v89;
              std::wstring::append(&Src, v89);
              if ( v90 )
              {
                if ( _InterlockedExchangeAdd(v90 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
                  if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
                }
              }
              if ( v87 )
              {
                if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
                  if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
                }
              }
              if ( v297 )
              {
                v91 = *(_QWORD *)(v56 + 24);
                if ( v91 )
                  _InterlockedIncrement((volatile signed __int32 *)(v91 + 8));
                v225 = *(_QWORD *)(v56 + 16);
                v92 = *(volatile signed __int32 **)(v56 + 24);
                v226 = v92;
                v7 |= 0x6000u;
                if ( *(_QWORD *)(*(_QWORD *)PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v225, v265)
                               + 16LL) )
                {
                  v93 = 1;
                  goto LABEL_177;
                }
              }
              else
              {
                v92 = v226;
              }
              v93 = 0;
LABEL_177:
              if ( (v7 & 0x4000) != 0 )
              {
                v7 &= ~0x4000u;
                v94 = v266;
                if ( v266 )
                {
                  if ( _InterlockedExchangeAdd(v266 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
                    if ( _InterlockedExchangeAdd(v94 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
                  }
                }
              }
              if ( (v7 & 0x2000) != 0 )
              {
                v7 &= ~0x2000u;
                if ( v92 )
                {
                  if ( _InterlockedExchangeAdd(v92 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v92)(v92);
                    if ( _InterlockedExchangeAdd(v92 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v92 + 8LL))(v92);
                  }
                }
              }
              if ( v93 )
              {
                v95 = *(_QWORD *)(v56 + 24);
                if ( v95 )
                  _InterlockedIncrement((volatile signed __int32 *)(v95 + 8));
                v267 = *(_QWORD *)(v56 + 16);
                v96 = *(volatile signed __int32 **)(v56 + 24);
                v268 = v96;
                v97 = *(_QWORD *)PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v267, v269);
                PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::AddEntry(v291, &Src, v97);
                v98 = v270;
                if ( v270 )
                {
                  if ( _InterlockedExchangeAdd(v270 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
                    if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
                  }
                }
                if ( v96 )
                {
                  if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
                    if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
                  }
                }
              }
              std::wstring::~wstring(&Src);
LABEL_199:
              v99 = *v186;
              v100 = *(_QWORD *)(*v186 + 24);
              if ( v100 )
                _InterlockedIncrement((volatile signed __int32 *)(v100 + 8));
              v101 = *(__int64 ***)(v99 + 16);
              v102 = *(volatile signed __int32 **)(v99 + 24);
              if ( v102 )
              {
                if ( _InterlockedExchangeAdd(v102 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v102)(v102);
                  if ( _InterlockedExchangeAdd(v102 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v102 + 8LL))(v102);
                }
              }
              v103 = *v101;
              v104 = v101[1];
              for ( i = v104; ; v104 = i )
              {
                v187 = v103;
                if ( v103 == v104 )
                {
                  std::shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>::~shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>(v199);
                  v23 = v186 + 2;
                  v24 = v194;
                  goto LABEL_23;
                }
                v105 = (__int64 *)*v103;
                v106 = PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(0);
                v193 = 0;
                v107 = *(_QWORD *)(v106 + 8);
                v108 = 1;
                if ( v107 )
                  _InterlockedAdd((volatile signed __int32 *)(v107 + 8), 1u);
                v193 = *(_OWORD *)v106;
                v109 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(
                         v295,
                         (__int64)L"DisplayName",
                         (__int64)&v193);
                v110 = v105[5];
                if ( v110 )
                  _InterlockedAdd((volatile signed __int32 *)(v110 + 8), 1u);
                v227[0] = v105[4];
                v227[1] = v105[5];
                PrintDeviceCapabilitiesOM::Parser::GenericSearchVector<PrintDeviceCapabilitiesOM::Property const>(
                  &v197,
                  v109,
                  v227);
                PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v295);
                v111 = (__int64 *)*v103;
                v112 = *(_QWORD *)(*v103 + 8);
                if ( v112 )
                  _InterlockedAdd((volatile signed __int32 *)(v112 + 8), 1u);
                v271 = *v111;
                v113 = (volatile signed __int32 *)v111[1];
                v272 = v113;
                v7 |= 0x8000u;
                if ( !v271 )
                  break;
                v114 = (__int64 *)*v103;
                v115 = *(_QWORD *)(*v103 + 8);
                if ( v115 )
                  _InterlockedAdd((volatile signed __int32 *)(v115 + 8), 1u);
                v116 = *v114;
                v199[2] = v116;
                v200 = (volatile signed __int32 *)v114[1];
                v117 = v7 | 0x10000;
                v118 = *(_QWORD *)(v116 + 24);
                if ( v118 )
                  _InterlockedAdd((volatile signed __int32 *)(v118 + 8), 1u);
                v246 = *(_QWORD *)(v116 + 16);
                v247 = *(volatile signed __int32 **)(v116 + 24);
                v7 = v117 | 0x20000;
                if ( !v246 )
                  break;
                v119 = (__int64 *)*v103;
                v120 = *(_QWORD *)(*v103 + 8);
                if ( v120 )
                  _InterlockedAdd((volatile signed __int32 *)(v120 + 8), 1u);
                v121 = *v119;
                v244 = v121;
                v245 = (volatile signed __int32 *)v119[1];
                v122 = v7 | 0x40000;
                v123 = *(_QWORD *)(v121 + 24);
                if ( v123 )
                  _InterlockedAdd((volatile signed __int32 *)(v123 + 8), 1u);
                v242 = *(_QWORD *)(v121 + 16);
                v243 = *(volatile signed __int32 **)(v121 + 24);
                v7 = v122 | 0x80000;
                if ( *(_DWORD *)(v242 + 16) != 8 )
                  break;
                v124 = (__int64 *)*v103;
                v125 = *(_QWORD *)(*v103 + 8);
                if ( v125 )
                  _InterlockedAdd((volatile signed __int32 *)(v125 + 8), 1u);
                v126 = *v124;
                v240 = v126;
                v241 = (volatile signed __int32 *)v124[1];
                v127 = v7 | 0x100000;
                v128 = *(_QWORD *)(v126 + 24);
                if ( v128 )
                  _InterlockedAdd((volatile signed __int32 *)(v128 + 8), 1u);
                v129 = *(_QWORD **)(v126 + 16);
                v238 = v129;
                v239 = *(volatile signed __int32 **)(v126 + 24);
                v130 = v127 | 0x200000;
                v131 = v129[1];
                if ( v131 )
                  _InterlockedAdd((volatile signed __int32 *)(v131 + 8), 1u);
                v236 = *v129;
                v237 = (volatile signed __int32 *)v129[1];
                v7 = v130 | 0x400000;
                if ( !v236 )
                  break;
                v132 = *v103;
                v133 = *(_QWORD *)(*v103 + 8);
                if ( v133 )
                  _InterlockedAdd((volatile signed __int32 *)(v133 + 8), 1u);
                v134 = *(_QWORD **)v132;
                v201 = v134;
                v202 = *(volatile signed __int32 **)(v132 + 8);
                v135 = v7 | 0x800000;
                v136 = v134[1];
                if ( v136 )
                  _InterlockedAdd((volatile signed __int32 *)(v136 + 8), 1u);
                v232 = *v134;
                v233 = (volatile signed __int32 *)v134[1];
                v7 = v135 | 0x1000000;
                if ( !v232 )
                  break;
                v137 = v197;
                if ( !v197 )
                  goto LABEL_245;
                v138 = *(_QWORD *)(v197 + 24);
                if ( v138 )
                  _InterlockedAdd((volatile signed __int32 *)(v138 + 8), 1u);
                v230 = *(_QWORD *)(v137 + 16);
                v139 = *(volatile signed __int32 **)(v137 + 24);
                v231 = v139;
                v7 |= 0x2000000u;
                if ( !v230 )
                  goto LABEL_245;
                if ( v139 )
                  _InterlockedAdd(v139 + 2, 1u);
                v228 = *(_QWORD *)(v137 + 16);
                v229 = *(volatile signed __int32 **)(v137 + 24);
                v7 |= 0xC000000u;
                if ( !*(_QWORD *)PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v228, v273) )
                  goto LABEL_245;
LABEL_246:
                if ( (v7 & 0x8000000) != 0 )
                {
                  v7 &= ~0x8000000u;
                  v140 = v274;
                  if ( v274 )
                  {
                    if ( _InterlockedExchangeAdd(v274 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v140)(v140);
                      if ( _InterlockedExchangeAdd(v140 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v140 + 8LL))(v140);
                    }
                  }
                }
                if ( (v7 & 0x4000000) != 0 )
                {
                  v7 &= ~0x4000000u;
                  v141 = v229;
                  if ( v229 )
                  {
                    if ( _InterlockedExchangeAdd(v229 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v141)(v141);
                      if ( _InterlockedExchangeAdd(v141 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v141 + 8LL))(v141);
                    }
                  }
                }
                if ( (v7 & 0x2000000) != 0 )
                {
                  v7 &= ~0x2000000u;
                  v142 = v231;
                  if ( v231 )
                  {
                    if ( _InterlockedExchangeAdd(v231 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v142)(v142);
                      if ( _InterlockedExchangeAdd(v142 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v142 + 8LL))(v142);
                    }
                  }
                }
                if ( (v7 & 0x1000000) != 0 )
                {
                  v7 &= ~0x1000000u;
                  v143 = v233;
                  if ( v233 )
                  {
                    if ( _InterlockedExchangeAdd(v233 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v143)(v143);
                      if ( _InterlockedExchangeAdd(v143 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v143 + 8LL))(v143);
                    }
                  }
                }
                if ( (v7 & 0x800000) != 0 )
                {
                  v7 &= ~0x800000u;
                  v144 = v202;
                  if ( v202 )
                  {
                    if ( _InterlockedExchangeAdd(v202 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v144)(v144);
                      if ( _InterlockedExchangeAdd(v144 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v144 + 8LL))(v144);
                    }
                  }
                }
                if ( (v7 & 0x400000) != 0 )
                {
                  v7 &= ~0x400000u;
                  v145 = v237;
                  if ( v237 )
                  {
                    if ( _InterlockedExchangeAdd(v237 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v145)(v145);
                      if ( _InterlockedExchangeAdd(v145 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v145 + 8LL))(v145);
                    }
                  }
                }
                if ( (v7 & 0x200000) != 0 )
                {
                  v7 &= ~0x200000u;
                  v146 = v239;
                  if ( v239 )
                  {
                    if ( _InterlockedExchangeAdd(v239 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v146)(v146);
                      if ( _InterlockedExchangeAdd(v146 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v146 + 8LL))(v146);
                    }
                  }
                }
                if ( (v7 & 0x100000) != 0 )
                {
                  v7 &= ~0x100000u;
                  v147 = v241;
                  if ( v241 )
                  {
                    if ( _InterlockedExchangeAdd(v241 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v147)(v147);
                      if ( _InterlockedExchangeAdd(v147 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v147 + 8LL))(v147);
                    }
                  }
                }
                if ( (v7 & 0x80000) != 0 )
                {
                  v7 &= ~0x80000u;
                  v148 = v243;
                  if ( v243 )
                  {
                    if ( _InterlockedExchangeAdd(v243 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v148)(v148);
                      if ( _InterlockedExchangeAdd(v148 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v148 + 8LL))(v148);
                    }
                  }
                }
                if ( (v7 & 0x40000) != 0 )
                {
                  v7 &= ~0x40000u;
                  v149 = v245;
                  if ( v245 )
                  {
                    if ( _InterlockedExchangeAdd(v245 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v149)(v149);
                      if ( _InterlockedExchangeAdd(v149 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v149 + 8LL))(v149);
                    }
                  }
                }
                if ( (v7 & 0x20000) != 0 )
                {
                  v7 &= ~0x20000u;
                  v150 = v247;
                  if ( v247 )
                  {
                    if ( _InterlockedExchangeAdd(v247 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v150)(v150);
                      if ( _InterlockedExchangeAdd(v150 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v150 + 8LL))(v150);
                    }
                  }
                }
                if ( (v7 & 0x10000) != 0 )
                {
                  v7 &= ~0x10000u;
                  v151 = v200;
                  if ( v200 )
                  {
                    if ( _InterlockedExchangeAdd(v200 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v151)(v151);
                      if ( _InterlockedExchangeAdd(v151 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v151 + 8LL))(v151);
                    }
                  }
                }
                if ( (v7 & 0x8000) != 0 )
                {
                  v7 &= ~0x8000u;
                  if ( v113 )
                  {
                    if ( _InterlockedExchangeAdd(v113 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v113)(v113);
                      if ( _InterlockedExchangeAdd(v113 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v113 + 8LL))(v113);
                    }
                  }
                }
                if ( v108 )
                {
                  v152 = (__int64 *)*v187;
                  v153 = *(_QWORD *)(*v187 + 8);
                  if ( v153 )
                    _InterlockedIncrement((volatile signed __int32 *)(v153 + 8));
                  v154 = *v152;
                  v275 = v154;
                  v155 = (volatile signed __int32 *)v152[1];
                  v276 = v155;
                  v156 = *(_QWORD *)(v154 + 24);
                  if ( v156 )
                    _InterlockedIncrement((volatile signed __int32 *)(v156 + 8));
                  v157 = *(_QWORD *)(v154 + 16);
                  v277 = v157;
                  v158 = *(volatile signed __int32 **)(v154 + 24);
                  v278 = v158;
                  v159 = *(_QWORD *)(v157 + 8);
                  if ( v159 )
                    _InterlockedIncrement((volatile signed __int32 *)(v159 + 8));
                  v160 = *(_QWORD **)v157;
                  v279 = v160;
                  v161 = *(volatile signed __int32 **)(v157 + 8);
                  v280 = v161;
                  if ( v160[3] > 7u )
                    v160 = (_QWORD *)*v160;
                  v299 = 0;
                  v300 = 0;
                  v301 = 0;
                  v162 = -1;
                  do
                    ++v162;
                  while ( *((_WORD *)v160 + v162) );
                  std::wstring::_Construct<1,unsigned short const *>((char **)&v299, v160, v162);
                  if ( v161 )
                  {
                    if ( _InterlockedExchangeAdd(v161 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v161)(v161);
                      if ( _InterlockedExchangeAdd(v161 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v161 + 8LL))(v161);
                    }
                  }
                  if ( v158 )
                  {
                    if ( _InterlockedExchangeAdd(v158 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v158)(v158);
                      if ( _InterlockedExchangeAdd(v158 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v158 + 8LL))(v158);
                    }
                  }
                  if ( v155 )
                  {
                    if ( _InterlockedExchangeAdd(v155 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v155)(v155);
                      if ( _InterlockedExchangeAdd(v155 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v155 + 8LL))(v155);
                    }
                  }
                  if ( v300 )
                  {
                    v163 = &v299;
                    if ( v301 > 7 )
                      v163 = (__int128 *)v299;
                    if ( *((_WORD *)v163 + v300 - 1) != 47 )
                      std::wstring::append(&v299, L"/");
                  }
                  v164 = (__int64 *)*v187;
                  v165 = *(_QWORD *)(*v187 + 8);
                  if ( v165 )
                    _InterlockedIncrement((volatile signed __int32 *)(v165 + 8));
                  v166 = *v164;
                  v281 = v166;
                  v167 = (volatile signed __int32 *)v164[1];
                  v282 = v167;
                  v168 = *(_QWORD *)(v166 + 8);
                  if ( v168 )
                    _InterlockedIncrement((volatile signed __int32 *)(v168 + 8));
                  v169 = *(_QWORD **)v166;
                  v283 = v169;
                  v170 = *(volatile signed __int32 **)(v166 + 8);
                  v284 = v170;
                  if ( v169[3] > 7u )
                    v169 = (_QWORD *)*v169;
                  std::wstring::append(&v299, v169);
                  if ( v170 )
                  {
                    if ( _InterlockedExchangeAdd(v170 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v170)(v170);
                      if ( _InterlockedExchangeAdd(v170 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v170 + 8LL))(v170);
                    }
                  }
                  if ( v167 )
                  {
                    if ( _InterlockedExchangeAdd(v167 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v167)(v167);
                      if ( _InterlockedExchangeAdd(v167 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v167 + 8LL))(v167);
                    }
                  }
                  if ( v300 )
                  {
                    v171 = *(_QWORD *)(v137 + 24);
                    if ( v171 )
                      _InterlockedIncrement((volatile signed __int32 *)(v171 + 8));
                    v190 = *(_QWORD *)(v137 + 16);
                    v172 = *(volatile signed __int32 **)(v137 + 24);
                    v191 = v172;
                    v7 |= 0x30000000u;
                    if ( *(_QWORD *)(*(_QWORD *)PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(
                                                  v190,
                                                  v285)
                                   + 16LL) )
                    {
                      v173 = 1;
                      goto LABEL_360;
                    }
                  }
                  else
                  {
                    v172 = v191;
                  }
                  v173 = 0;
LABEL_360:
                  if ( (v7 & 0x20000000) != 0 )
                  {
                    v7 &= ~0x20000000u;
                    v174 = v286;
                    if ( v286 )
                    {
                      if ( _InterlockedExchangeAdd(v286 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v174)(v174);
                        if ( _InterlockedExchangeAdd(v174 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v174 + 8LL))(v174);
                      }
                    }
                  }
                  if ( (v7 & 0x10000000) != 0 )
                  {
                    v7 &= ~0x10000000u;
                    if ( v172 )
                    {
                      if ( _InterlockedExchangeAdd(v172 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v172)(v172);
                        if ( _InterlockedExchangeAdd(v172 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v172 + 8LL))(v172);
                      }
                    }
                  }
                  if ( v173 )
                  {
                    v175 = *(_QWORD *)(v137 + 24);
                    if ( v175 )
                      _InterlockedIncrement((volatile signed __int32 *)(v175 + 8));
                    v287 = *(_QWORD *)(v137 + 16);
                    v176 = *(volatile signed __int32 **)(v137 + 24);
                    v288 = v176;
                    v177 = *(_QWORD *)PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v287, v289);
                    PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::AddEntry(v291, &v299, v177);
                    v178 = v290;
                    if ( v290 )
                    {
                      if ( _InterlockedExchangeAdd(v290 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v178)(v178);
                        if ( _InterlockedExchangeAdd(v178 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v178 + 8LL))(v178);
                      }
                    }
                    if ( v176 )
                    {
                      if ( _InterlockedExchangeAdd(v176 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v176)(v176);
                        if ( _InterlockedExchangeAdd(v176 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v176 + 8LL))(v176);
                      }
                    }
                  }
                  std::wstring::~wstring(&v299);
                }
                v179 = v198;
                if ( v198 && _InterlockedExchangeAdd(v198 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v179)(v179);
                  if ( _InterlockedExchangeAdd(v179 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v179 + 8LL))(v179);
                }
                v103 = v187 + 2;
              }
              v137 = v197;
LABEL_245:
              v108 = 0;
              goto LABEL_246;
            }
          }
        }
      }
      else
      {
LABEL_61:
        v56 = v199[0];
      }
      v59 = 0;
      goto LABEL_63;
    }
    v180 = v292;
    if ( v292 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v292->lpVtbl->AddRef)(v292);
    *v195 = v180;
    PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::~PrintDeviceResourcesSerializer((PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer *)v291);
    std::shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>::~shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>(v203);
    v181 = v188;
    if ( v188 )
    {
      v188 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v181 + 16LL))(v181);
    }
  }
  catch ( std::bad_alloc )
  {
    v183 = -2147024882;
  }
  catch ( const hr_error *v249 )
  {
    v183 = *((_DWORD *)v249 + 6);
  }
  catch ( const PrintCore::WindowsError *v250 )
  {
    v183 = *((_DWORD *)v250 + 6);
  }
  catch ( std::exception )
  {
    v183 = -2147467259;
  }
  catch ( ... )
  {
    v183 = -2147418113;
  }
  v182 = (WCHAR *)pwszLanguagesBuffer;
  SetThreadPreferredUILanguages(8u, pwszLanguagesBuffer, &pulNumLanguages);
  if ( v182 )
    CoTaskMemFree(v182);
  return v183;
}

```

## disassembly

```asm
0x1800f3f60  push    rbx
0x1800f3f62  push    rsi
0x1800f3f63  push    rdi
0x1800f3f64  push    r12
0x1800f3f66  push    r13
0x1800f3f68  push    r14
0x1800f3f6a  push    r15
0x1800f3f6c  sub     rsp, 490h
0x1800f3f73  mov     [rsp+4C8h+var_268], 0FFFFFFFFFFFFFFFEh
0x1800f3f7f  mov     rax, cs:__security_cookie
0x1800f3f86  xor     rax, rsp
0x1800f3f89  mov     [rsp+4C8h+var_48], rax
0x1800f3f91  mov     [rsp+4C8h+var_438], r9
0x1800f3f99  mov     r12, r8
0x1800f3f9c  mov     r15, rdx
0x1800f3f9f  mov     r14, rcx
0x1800f3fa2  xor     edi, edi
0x1800f3fa4  mov     r13d, edi
0x1800f3fa7  mov     [rsp+4C8h+var_4A8], edi; int
0x1800f3fab  test    r9, r9
0x1800f3fae  jnz     short loc_1800F3FBA
0x1800f3fb0  mov     eax, 80004003h
0x1800f3fb5  jmp     loc_1800F5AA6
0x1800f3fba  mov     [rsp+4C8h+pulNumLanguages], edi
0x1800f3fbe  mov     [rsp+4C8h+pcchLanguagesBuffer], edi
0x1800f3fc2  lea     r9, [rsp+4C8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800f3fc7  xor     r8d, r8d; pwszLanguagesBuffer
0x1800f3fca  lea     rdx, [rsp+4C8h+pulNumLanguages]; pulNumLanguages
0x1800f3fcf  lea     ecx, [r8+48h]; dwFlags
0x1800f3fd3  call    cs:__imp_GetThreadPreferredUILanguages
0x1800f3fd9  test    eax, eax
0x1800f3fdb  jnz     short loc_1800F3FFB
0x1800f3fdd  mov     rcx, [rsp+4C8h]; this
0x1800f3fe5  lea     r8, aPrintscanPrint_21; "printscan\\print\\drivers\\usermode\\dr"...
0x1800f3fec  mov     edx, 0A7Fh; void *
0x1800f3ff1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f3ff6  jmp     loc_1800F5AA6
0x1800f3ffb  mov     ebx, [rsp+4C8h+pcchLanguagesBuffer]
0x1800f3fff  lea     rcx, ds:2[rbx*2]; cb
0x1800f4007  call    cs:__imp_CoTaskMemAlloc
0x1800f400d  mov     rsi, rax
0x1800f4010  test    rax, rax
0x1800f4013  jz      short loc_1800F401C
0x1800f4015  mov     [rax], di
0x1800f4018  mov     [rax+rbx*2], di
0x1800f401c  mov     [rsp+4C8h+pwszLanguagesBuffer], rsi
0x1800f4024  test    rsi, rsi
0x1800f4027  jz      loc_1800F5A82
0x1800f402d  lea     r9, [rsp+4C8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800f4032  mov     r8, rsi; pwszLanguagesBuffer
0x1800f4035  lea     rdx, [rsp+4C8h+pulNumLanguages]; pulNumLanguages
0x1800f403a  mov     ecx, 48h ; 'H'; dwFlags
0x1800f403f  call    cs:__imp_GetThreadPreferredUILanguages
0x1800f4045  test    eax, eax
0x1800f4047  jnz     short loc_1800F4072
0x1800f4049  mov     rcx, [rsp+4C8h]; this
0x1800f4051  lea     r8, aPrintscanPrint_21; "printscan\\print\\drivers\\usermode\\dr"...
0x1800f4058  mov     edx, 0A86h; void *
0x1800f405d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f4062  mov     ebx, eax
0x1800f4064  mov     rcx, rsi; pv
0x1800f4067  call    cs:__imp_CoTaskMemFree
0x1800f406d  jmp     loc_1800F5AA4
0x1800f4072  mov     [rsp+4C8h+var_4A0], edi
0x1800f4076  xor     edx, edx; dwFlags
0x1800f4078  mov     rcx, r15; lpName
0x1800f407b  call    cs:__imp_LocaleNameToLCID
0x1800f4081  mov     ecx, eax; LangId
0x1800f4083  call    cs:__imp_SetThreadUILanguage
0x1800f4089  nop
0x1800f408a  mov     [rsp+4C8h+var_480], rdi
0x1800f408f  mov     rax, [r14]
0x1800f4092  lea     r8, [rsp+4C8h+var_480]
0x1800f4097  mov     rdx, r12
0x1800f409a  mov     rcx, r14
0x1800f409d  mov     rax, [rax+40h]
0x1800f40a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f40a6  test    eax, eax
0x1800f40a8  js      loc_1800F5AC9
0x1800f40ae  lea     rdx, [rsp+4C8h+var_480]
0x1800f40b3  lea     rcx, [rsp+4C8h+var_470]
0x1800f40b8  call    ??$make_shared@VPrintCapabilities@PrintDeviceCapabilitiesOM@@AEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@VPrintCapabilities@PrintDeviceCapabilitiesOM@@@0@AEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintCapabilities,Microsoft::WRL::ComPtr<IXMLDOMDocument2> &>(Microsoft::WRL::ComPtr<IXMLDOMDocument2> &)
0x1800f40bd  mov     rsi, [rax]
0x1800f40c0  mov     [rsp+4C8h+var_3E8], rsi
0x1800f40c8  mov     rcx, [rax+8]
0x1800f40cc  mov     [rsp+4C8h+var_3E0], rcx
0x1800f40d4  mov     [rax], rdi
0x1800f40d7  mov     [rax+8], rdi
0x1800f40db  mov     rbx, [rsp+4C8h+var_468]
0x1800f40e0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800f40e4  test    rbx, rbx
0x1800f40e7  jz      short loc_1800F4120
0x1800f40e9  mov     eax, r15d
0x1800f40ec  lock xadd [rbx+8], eax
0x1800f40f1  add     eax, r15d
0x1800f40f4  jnz     short loc_1800F4120
0x1800f40f6  mov     rax, [rbx]
0x1800f40f9  mov     rcx, rbx
0x1800f40fc  mov     rax, [rax]
0x1800f40ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4104  mov     eax, r15d
0x1800f4107  lock xadd [rbx+0Ch], eax
0x1800f410c  add     eax, r15d
0x1800f410f  jnz     short loc_1800F4120
0x1800f4111  mov     rax, [rbx]
0x1800f4114  mov     rcx, rbx
0x1800f4117  mov     rax, [rax+8]
0x1800f411b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4120  lea     rcx, [rsp+4C8h+var_110]; this
0x1800f4128  call    ??0PrintDeviceResourcesSerializer@Serializer@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::PrintDeviceResourcesSerializer(void)
0x1800f412d  nop
0x1800f412e  mov     rax, [rsi+8]
0x1800f4132  test    rax, rax
0x1800f4135  jz      short loc_1800F413B
0x1800f4137  lock inc dword ptr [rax+8]
0x1800f413b  mov     r14, [rsi]
0x1800f413e  mov     rbx, [rsi+8]
0x1800f4142  test    rbx, rbx
0x1800f4145  jz      short loc_1800F417E
0x1800f4147  mov     eax, r15d
0x1800f414a  lock xadd [rbx+8], eax
0x1800f414f  add     eax, r15d
0x1800f4152  jnz     short loc_1800F417E
0x1800f4154  mov     rax, [rbx]
0x1800f4157  mov     rcx, rbx
0x1800f415a  mov     rax, [rax]
0x1800f415d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4162  mov     eax, r15d
0x1800f4165  lock xadd [rbx+0Ch], eax
0x1800f416a  add     eax, r15d
0x1800f416d  jnz     short loc_1800F417E
0x1800f416f  mov     rax, [rbx]
0x1800f4172  mov     rcx, rbx
0x1800f4175  mov     rax, [rax+8]
0x1800f4179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f417e  mov     rsi, [r14]
0x1800f4181  mov     rax, [r14+8]
0x1800f4185  mov     [rsp+4C8h+var_440], rax
0x1800f418d  mov     [rsp+4C8h+var_490], rsi
0x1800f4192  cmp     rsi, rax
0x1800f4195  jz      loc_1800F59EA
0x1800f419b  mov     rbx, [rsi]
0x1800f419e  xor     ecx, ecx
0x1800f41a0  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x1800f41a5  mov     rcx, rax
0x1800f41a8  xorps   xmm0, xmm0
0x1800f41ab  movdqu  [rsp+4C8h+var_460], xmm0
0x1800f41b1  mov     rax, [rax+8]
0x1800f41b5  test    rax, rax
0x1800f41b8  jz      short loc_1800F41BE
0x1800f41ba  lock inc dword ptr [rax+8]
0x1800f41be  mov     rax, [rcx]
0x1800f41c1  mov     qword ptr [rsp+4C8h+var_460], rax
0x1800f41c6  mov     rax, [rcx+8]
0x1800f41ca  mov     qword ptr [rsp+4C8h+var_460+8], rax
0x1800f41cf  lea     r8, [rsp+4C8h+var_460]
0x1800f41d4  lea     rdx, aDisplayname_0; "DisplayName"
0x1800f41db  lea     rcx, [rsp+4C8h+var_C8]
0x1800f41e3  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x1800f41e8  mov     rdx, rax
0x1800f41eb  mov     rcx, [rbx+28h]
0x1800f41ef  test    rcx, rcx
0x1800f41f2  jz      short loc_1800F41F8
0x1800f41f4  lock inc dword ptr [rcx+8]
0x1800f41f8  mov     rax, [rbx+20h]
0x1800f41fc  mov     [rsp+4C8h+var_3D8], rax
0x1800f4204  mov     rax, [rbx+28h]
0x1800f4208  mov     [rsp+4C8h+var_3D0], rax
0x1800f4210  lea     r8, [rsp+4C8h+var_3D8]
0x1800f4218  lea     rcx, [rsp+4C8h+var_418]
0x1800f4220  call    ??$GenericSearchVector@$$CBVProperty@PrintDeviceCapabilitiesOM@@@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@AEBVQualifiedName@1@V?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@3@@Z; PrintDeviceCapabilitiesOM::Parser::GenericSearchVector<PrintDeviceCapabilitiesOM::Property const>(PrintDeviceCapabilitiesOM::QualifiedName const &,std::shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Property const>>>)
0x1800f4225  nop
0x1800f4226  lea     rcx, [rsp+4C8h+var_C8]; this
0x1800f422e  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x1800f4233  mov     rcx, [rsi]
0x1800f4236  mov     rax, [rcx+8]
0x1800f423a  test    rax, rax
0x1800f423d  jz      short loc_1800F4243
0x1800f423f  lock inc dword ptr [rax+8]
0x1800f4243  mov     rax, [rcx]
0x1800f4246  mov     [rsp+4C8h+var_250], rax
0x1800f424e  mov     r14, [rcx+8]
0x1800f4252  mov     [rsp+4C8h+var_248], r14
0x1800f425a  or      r13d, 1
0x1800f425e  test    rax, rax
0x1800f4261  jz      loc_1800F44AB
0x1800f4267  mov     rcx, [rsi]
0x1800f426a  mov     rax, [rcx+8]
0x1800f426e  test    rax, rax
0x1800f4271  jz      short loc_1800F4277
0x1800f4273  lock inc dword ptr [rax+8]
0x1800f4277  mov     rdx, [rcx]
0x1800f427a  mov     [rsp+4C8h+var_338], rdx
0x1800f4282  mov     rax, [rcx+8]
0x1800f4286  mov     [rsp+4C8h+var_330], rax
0x1800f428e  or      r13d, 2
0x1800f4292  mov     [rsp+4C8h+var_4A8], r13d
0x1800f4297  mov     rax, [rdx+18h]
0x1800f429b  test    rax, rax
0x1800f429e  jz      short loc_1800F42A4
0x1800f42a0  lock inc dword ptr [rax+8]
0x1800f42a4  mov     rax, [rdx+10h]
0x1800f42a8  mov     [rsp+4C8h+var_348], rax
0x1800f42b0  mov     rcx, [rdx+18h]
0x1800f42b4  mov     [rsp+4C8h+var_340], rcx
0x1800f42bc  or      r13d, 4
0x1800f42c0  test    rax, rax
0x1800f42c3  jz      loc_1800F44AB
0x1800f42c9  mov     rcx, [rsi]
0x1800f42cc  mov     rax, [rcx+8]
0x1800f42d0  test    rax, rax
0x1800f42d3  jz      short loc_1800F42D9
0x1800f42d5  lock inc dword ptr [rax+8]
0x1800f42d9  mov     rdx, [rcx]
0x1800f42dc  mov     [rsp+4C8h+var_2D8], rdx
0x1800f42e4  mov     rax, [rcx+8]
0x1800f42e8  mov     [rsp+4C8h+var_2D0], rax
0x1800f42f0  or      r13d, 8
0x1800f42f4  mov     [rsp+4C8h+var_4A8], r13d
0x1800f42f9  mov     rax, [rdx+18h]
0x1800f42fd  test    rax, rax
0x1800f4300  jz      short loc_1800F4306
0x1800f4302  lock inc dword ptr [rax+8]
0x1800f4306  mov     rax, [rdx+10h]
0x1800f430a  mov     [rsp+4C8h+var_358], rax
0x1800f4312  mov     rcx, [rdx+18h]
0x1800f4316  mov     [rsp+4C8h+var_350], rcx
0x1800f431e  or      r13d, 10h
0x1800f4322  cmp     dword ptr [rax+10h], 8
0x1800f4326  jnz     loc_1800F44AB
0x1800f432c  mov     rcx, [rsi]
0x1800f432f  mov     rax, [rcx+8]
0x1800f4333  test    rax, rax
0x1800f4336  jz      short loc_1800F433C
0x1800f4338  lock inc dword ptr [rax+8]
0x1800f433c  mov     rdx, [rcx]
0x1800f433f  mov     [rsp+4C8h+var_368], rdx
0x1800f4347  mov     rax, [rcx+8]
0x1800f434b  mov     [rsp+4C8h+var_360], rax
0x1800f4353  or      r13d, 20h
0x1800f4357  mov     [rsp+4C8h+var_4A8], r13d
0x1800f435c  mov     rax, [rdx+18h]
0x1800f4360  test    rax, rax
0x1800f4363  jz      short loc_1800F4369
0x1800f4365  lock inc dword ptr [rax+8]
0x1800f4369  mov     rcx, [rdx+10h]
0x1800f436d  mov     [rsp+4C8h+var_378], rcx
0x1800f4375  mov     rax, [rdx+18h]
0x1800f4379  mov     [rsp+4C8h+var_370], rax
0x1800f4381  or      r13d, 40h
0x1800f4385  mov     [rsp+4C8h+var_4A8], r13d
0x1800f438a  mov     rax, [rcx+8]
0x1800f438e  test    rax, rax
0x1800f4391  jz      short loc_1800F4397
0x1800f4393  lock inc dword ptr [rax+8]
0x1800f4397  mov     rax, [rcx]
0x1800f439a  mov     [rsp+4C8h+var_388], rax
0x1800f43a2  mov     rdx, [rcx+8]
0x1800f43a6  mov     [rsp+4C8h+var_380], rdx
0x1800f43ae  bts     r13d, 7
0x1800f43b3  test    rax, rax
0x1800f43b6  jz      loc_1800F44AB
0x1800f43bc  mov     rdx, [rsi]
0x1800f43bf  mov     rax, [rdx+8]
0x1800f43c3  test    rax, rax
0x1800f43c6  jz      short loc_1800F43CC
0x1800f43c8  lock inc dword ptr [rax+8]
0x1800f43cc  mov     rcx, [rdx]
0x1800f43cf  mov     [rsp+4C8h+var_398], rcx
0x1800f43d7  mov     rax, [rdx+8]
0x1800f43db  mov     [rsp+4C8h+var_390], rax
0x1800f43e3  bts     r13d, 8
0x1800f43e8  mov     [rsp+4C8h+var_4A8], r13d
0x1800f43ed  mov     rax, [rcx+8]
0x1800f43f1  test    rax, rax
0x1800f43f4  jz      short loc_1800F43FA
0x1800f43f6  lock inc dword ptr [rax+8]
0x1800f43fa  mov     rax, [rcx]
0x1800f43fd  mov     [rsp+4C8h+var_3A8], rax
0x1800f4405  mov     rdx, [rcx+8]
0x1800f4409  mov     [rsp+4C8h+var_3A0], rdx
0x1800f4411  bts     r13d, 9
0x1800f4416  test    rax, rax
0x1800f4419  jz      loc_1800F44AB
0x1800f441f  mov     r12, [rsp+4C8h+var_418]
0x1800f4427  test    r12, r12
0x1800f442a  jz      loc_1800F44B3
0x1800f4430  mov     rax, [r12+18h]
0x1800f4435  test    rax, rax
0x1800f4438  jz      short loc_1800F443E
0x1800f443a  lock inc dword ptr [rax+8]
0x1800f443e  mov     rax, [r12+10h]
0x1800f4443  mov     [rsp+4C8h+var_3B8], rax
0x1800f444b  mov     rcx, [r12+18h]
0x1800f4450  mov     [rsp+4C8h+var_3B0], rcx
0x1800f4458  bts     r13d, 0Ah
0x1800f445d  test    rax, rax
0x1800f4460  jz      short loc_1800F44B3
0x1800f4462  test    rcx, rcx
0x1800f4465  jz      short loc_1800F446B
  ... truncated ...
```
