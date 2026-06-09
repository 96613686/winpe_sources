# PSUI::CPrintTicketProvider::GetPrintDeviceResources(ushort const *,IXMLDOMDocument2 *,IXMLDOMDocument2 * *)

- ea: `0x18012f3d0`
- end: `0x180130f8f`
- name: `?GetPrintDeviceResources@CPrintTicketProvider@PSUI@@UEAAJPEBGPEAUIXMLDOMDocument2@@PEAPEAU3@@Z`
- size: `7103`
- prototype: `__int64 __fastcall(PSUI::CPrintTicketProvider *this, const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003400`
- `0x180004564`
- `0x1800064e0`
- `0x18000b444`
- `0x18000b470`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x180019618`
- `0x18001fa34`
- `0x18006872c`
- `0x18006c630`
- `0x180070db0`
- `0x180073430`
- `0x1800ecbb8`
- `0x1800ee0b4`
- `0x1800eea74`
- `0x1800ef068`
- `0x18012f3d0`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetThreadPreferredUILanguages` at `0x18012f443`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x18012f4bb`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x18012f443`
- `KERNEL32!GetThreadPreferredUILanguages` at `0x18012f4bb`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x18012f511`
- `api-ms-win-core-localization-l1-2-0!SetThreadUILanguage` at `0x18012f511`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18012f503`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18012f503`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180130ef3`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180130ef3`
- `ole32!CoTaskMemAlloc` at `0x18012f47d`
- `ole32!CoTaskMemAlloc` at `0x18012f47d`
- `ole32!CoTaskMemFree` at `0x18012f4e9`
- `ole32!CoTaskMemFree` at `0x180130f08`
- `ole32!CoTaskMemFree` at `0x18012f4e9`
- `ole32!CoTaskMemFree` at `0x180130f08`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall PSUI::CPrintTicketProvider::GetPrintDeviceResources(
        PSUI::CPrintTicketProvider *this,
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
  __int64 *inited; // rcx
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
  __int64 v83; // r8
  __int128 *p_Src; // rax
  __int64 v85; // rcx
  __int64 v86; // rax
  _QWORD *v87; // rbx
  volatile signed __int32 *v88; // rsi
  __int64 v89; // rax
  __int64 *v90; // rdx
  volatile signed __int32 *v91; // rbx
  __int64 v92; // rax
  volatile signed __int32 *v93; // r14
  char v94; // si
  volatile signed __int32 *v95; // rbx
  __int64 v96; // rax
  volatile signed __int32 *v97; // rsi
  const unsigned __int16 *v98; // r8
  volatile signed __int32 *v99; // rbx
  __int64 v100; // rbx
  __int64 v101; // rax
  __int64 **v102; // rsi
  volatile signed __int32 *v103; // rbx
  __int64 *v104; // r12
  __int64 *v105; // rax
  __int64 *v106; // rbx
  __int64 *v107; // rcx
  __int64 v108; // rax
  char v109; // si
  _QWORD *v110; // rdx
  __int64 v111; // rcx
  __int64 *v112; // rcx
  __int64 v113; // rax
  volatile signed __int32 *v114; // r14
  __int64 *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rdx
  int v118; // r13d
  __int64 v119; // rax
  __int64 *v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rdx
  int v123; // r13d
  __int64 v124; // rax
  __int64 *v125; // rcx
  __int64 v126; // rax
  __int64 v127; // rdx
  int v128; // r13d
  __int64 v129; // rax
  _QWORD *v130; // rcx
  int v131; // r13d
  __int64 v132; // rax
  __int64 v133; // rcx
  __int64 v134; // rax
  _QWORD *v135; // rdx
  int v136; // r13d
  __int64 v137; // rax
  __int64 v138; // r12
  __int64 v139; // rax
  volatile signed __int32 *v140; // rcx
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
  volatile signed __int32 *v152; // rbx
  __int64 *v153; // rcx
  __int64 v154; // rax
  __int64 v155; // rdx
  volatile signed __int32 *v156; // r14
  __int64 v157; // rax
  __int64 v158; // rcx
  volatile signed __int32 *v159; // rsi
  __int64 v160; // rax
  _QWORD *v161; // rdx
  volatile signed __int32 *v162; // rbx
  unsigned __int64 v163; // r8
  __int64 v164; // r8
  __int128 *v165; // rax
  __int64 v166; // rcx
  __int64 v167; // rax
  _QWORD *v168; // rax
  volatile signed __int32 *v169; // rsi
  __int64 v170; // rcx
  __int64 *v171; // rdx
  volatile signed __int32 *v172; // rbx
  __int64 v173; // rax
  volatile signed __int32 *v174; // r14
  char v175; // si
  volatile signed __int32 *v176; // rbx
  __int64 v177; // rax
  volatile signed __int32 *v178; // rsi
  const unsigned __int16 *v179; // r8
  volatile signed __int32 *v180; // rbx
  volatile signed __int32 *v181; // rbx
  struct IXMLDOMDocument2 *v182; // rbx
  __int64 v183; // rcx
  WCHAR *v184; // rbx
  unsigned int v185; // [rsp+28h] [rbp-4A0h]
  ULONG pcchLanguagesBuffer; // [rsp+2Ch] [rbp-49Ch] BYREF
  ULONG pulNumLanguages; // [rsp+30h] [rbp-498h] BYREF
  __int64 *v188; // [rsp+38h] [rbp-490h]
  __int64 *v189; // [rsp+40h] [rbp-488h]
  __int64 v190; // [rsp+48h] [rbp-480h] BYREF
  __int64 *i; // [rsp+50h] [rbp-478h]
  __int64 v192; // [rsp+58h] [rbp-470h] BYREF
  volatile signed __int32 *v193; // [rsp+60h] [rbp-468h]
  __int128 v194; // [rsp+68h] [rbp-460h] BYREF
  __int128 v195; // [rsp+78h] [rbp-450h] BYREF
  __int64 *v196; // [rsp+88h] [rbp-440h]
  struct IXMLDOMDocument2 **v197; // [rsp+90h] [rbp-438h]
  PCZZWSTR pwszLanguagesBuffer; // [rsp+98h] [rbp-430h]
  __int64 v199; // [rsp+A0h] [rbp-428h] BYREF
  volatile signed __int32 *v200; // [rsp+A8h] [rbp-420h]
  _QWORD v201[3]; // [rsp+B0h] [rbp-418h] BYREF
  volatile signed __int32 *v202; // [rsp+C8h] [rbp-400h]
  _QWORD *v203; // [rsp+D0h] [rbp-3F8h]
  volatile signed __int32 *v204; // [rsp+D8h] [rbp-3F0h]
  _QWORD v205[2]; // [rsp+E0h] [rbp-3E8h] BYREF
  _QWORD v206[2]; // [rsp+F0h] [rbp-3D8h] BYREF
  __int64 v207; // [rsp+100h] [rbp-3C8h]
  volatile signed __int32 *v208; // [rsp+108h] [rbp-3C0h]
  __int64 v209; // [rsp+110h] [rbp-3B8h]
  volatile signed __int32 *v210; // [rsp+118h] [rbp-3B0h]
  __int64 v211; // [rsp+120h] [rbp-3A8h]
  volatile signed __int32 *v212; // [rsp+128h] [rbp-3A0h]
  _QWORD *v213; // [rsp+130h] [rbp-398h]
  volatile signed __int32 *v214; // [rsp+138h] [rbp-390h]
  __int64 v215; // [rsp+140h] [rbp-388h]
  volatile signed __int32 *v216; // [rsp+148h] [rbp-380h]
  _QWORD *v217; // [rsp+150h] [rbp-378h]
  volatile signed __int32 *v218; // [rsp+158h] [rbp-370h]
  __int64 v219; // [rsp+160h] [rbp-368h]
  volatile signed __int32 *v220; // [rsp+168h] [rbp-360h]
  __int64 v221; // [rsp+170h] [rbp-358h]
  volatile signed __int32 *v222; // [rsp+178h] [rbp-350h]
  __int64 v223; // [rsp+180h] [rbp-348h]
  volatile signed __int32 *v224; // [rsp+188h] [rbp-340h]
  __int64 v225; // [rsp+190h] [rbp-338h]
  volatile signed __int32 *v226; // [rsp+198h] [rbp-330h]
  __int64 v227; // [rsp+1A0h] [rbp-328h]
  volatile signed __int32 *v228; // [rsp+1A8h] [rbp-320h]
  _QWORD v229[2]; // [rsp+1B0h] [rbp-318h] BYREF
  __int64 v230; // [rsp+1C0h] [rbp-308h]
  volatile signed __int32 *v231; // [rsp+1C8h] [rbp-300h]
  __int64 v232; // [rsp+1D0h] [rbp-2F8h]
  volatile signed __int32 *v233; // [rsp+1D8h] [rbp-2F0h]
  __int64 v234; // [rsp+1E0h] [rbp-2E8h]
  volatile signed __int32 *v235; // [rsp+1E8h] [rbp-2E0h]
  __int64 v236; // [rsp+1F0h] [rbp-2D8h]
  volatile signed __int32 *v237; // [rsp+1F8h] [rbp-2D0h]
  __int64 v238; // [rsp+200h] [rbp-2C8h]
  volatile signed __int32 *v239; // [rsp+208h] [rbp-2C0h]
  _QWORD *v240; // [rsp+210h] [rbp-2B8h]
  volatile signed __int32 *v241; // [rsp+218h] [rbp-2B0h]
  __int64 v242; // [rsp+220h] [rbp-2A8h]
  volatile signed __int32 *v243; // [rsp+228h] [rbp-2A0h]
  __int64 v244; // [rsp+230h] [rbp-298h]
  volatile signed __int32 *v245; // [rsp+238h] [rbp-290h]
  __int64 v246; // [rsp+240h] [rbp-288h]
  volatile signed __int32 *v247; // [rsp+248h] [rbp-280h]
  __int64 v248; // [rsp+250h] [rbp-278h]
  volatile signed __int32 *v249; // [rsp+258h] [rbp-270h]
  __int64 v250; // [rsp+260h] [rbp-268h]
  const hr_error *v251; // [rsp+268h] [rbp-260h] BYREF
  const PrintCore::WindowsError *v252; // [rsp+270h] [rbp-258h] BYREF
  __int64 v253; // [rsp+278h] [rbp-250h]
  volatile signed __int32 *v254; // [rsp+280h] [rbp-248h]
  __int64 v255; // [rsp+288h] [rbp-240h] BYREF
  volatile signed __int32 *v256; // [rsp+290h] [rbp-238h]
  __int64 v257; // [rsp+298h] [rbp-230h]
  volatile signed __int32 *v258; // [rsp+2A0h] [rbp-228h]
  __int64 v259; // [rsp+2A8h] [rbp-220h]
  volatile signed __int32 *v260; // [rsp+2B0h] [rbp-218h]
  _QWORD *v261; // [rsp+2B8h] [rbp-210h]
  volatile signed __int32 *v262; // [rsp+2C0h] [rbp-208h]
  _QWORD *v263; // [rsp+2C8h] [rbp-200h]
  volatile signed __int32 *v264; // [rsp+2D0h] [rbp-1F8h]
  __int64 *v265; // [rsp+2D8h] [rbp-1F0h]
  volatile signed __int32 *v266; // [rsp+2E0h] [rbp-1E8h]
  __int64 v267; // [rsp+2E8h] [rbp-1E0h] BYREF
  volatile signed __int32 *v268; // [rsp+2F0h] [rbp-1D8h]
  __int64 v269; // [rsp+2F8h] [rbp-1D0h]
  volatile signed __int32 *v270; // [rsp+300h] [rbp-1C8h]
  __int64 v271; // [rsp+308h] [rbp-1C0h] BYREF
  volatile signed __int32 *v272; // [rsp+310h] [rbp-1B8h]
  __int64 v273; // [rsp+318h] [rbp-1B0h]
  volatile signed __int32 *v274; // [rsp+320h] [rbp-1A8h]
  __int64 v275; // [rsp+328h] [rbp-1A0h] BYREF
  volatile signed __int32 *v276; // [rsp+330h] [rbp-198h]
  __int64 v277; // [rsp+338h] [rbp-190h]
  volatile signed __int32 *v278; // [rsp+340h] [rbp-188h]
  __int64 v279; // [rsp+348h] [rbp-180h]
  volatile signed __int32 *v280; // [rsp+350h] [rbp-178h]
  _QWORD *v281; // [rsp+358h] [rbp-170h]
  volatile signed __int32 *v282; // [rsp+360h] [rbp-168h]
  _QWORD *v283; // [rsp+368h] [rbp-160h]
  volatile signed __int32 *v284; // [rsp+370h] [rbp-158h]
  __int64 *v285; // [rsp+378h] [rbp-150h]
  volatile signed __int32 *v286; // [rsp+380h] [rbp-148h]
  __int64 v287; // [rsp+388h] [rbp-140h] BYREF
  volatile signed __int32 *v288; // [rsp+390h] [rbp-138h]
  __int64 v289; // [rsp+398h] [rbp-130h]
  volatile signed __int32 *v290; // [rsp+3A0h] [rbp-128h]
  __int64 v291; // [rsp+3A8h] [rbp-120h] BYREF
  volatile signed __int32 *v292; // [rsp+3B0h] [rbp-118h]
  _BYTE v293[24]; // [rsp+3B8h] [rbp-110h] BYREF
  struct IXMLDOMDocument2 *v294; // [rsp+3D0h] [rbp-F8h]
  _BYTE pExceptionObject[32]; // [rsp+3E0h] [rbp-E8h] BYREF
  _QWORD v296[4]; // [rsp+400h] [rbp-C8h] BYREF
  _QWORD v297[4]; // [rsp+420h] [rbp-A8h] BYREF
  __int128 Src; // [rsp+440h] [rbp-88h] BYREF
  __int64 v299; // [rsp+450h] [rbp-78h]
  unsigned __int64 v300; // [rsp+458h] [rbp-70h]
  __int128 v301; // [rsp+460h] [rbp-68h] BYREF
  __int64 v302; // [rsp+470h] [rbp-58h]
  unsigned __int64 v303; // [rsp+478h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+0h]

  v250 = -2;
  v197 = a4;
  v7 = 0;
  if ( !a4 )
    return 2147500035LL;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAB9,
             (int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
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
      (void *)0xABC,
      (__int64)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
      (const char *)0x8007000ELL);
    return LastError;
  }
  if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, v11, &pcchLanguagesBuffer) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAC0,
                  (int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
                  v13);
    CoTaskMemFree(v12);
    return LastError;
  }
  v185 = 0;
  v15 = LocaleNameToLCID(a2, 0);
  SetThreadUILanguage(v15);
  try
  {
    v190 = 0;
    v16 = (*(__int64 (__fastcall **)(PSUI::CPrintTicketProvider *, struct IXMLDOMDocument2 *, __int64 *))(*(_QWORD *)this + 64LL))(
            this,
            a3,
            &v190);
    if ( v16 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v16);
      throw (hr_error *)pExceptionObject;
    }
    v17 = std::make_shared<PrintDeviceCapabilitiesOM::PrintCapabilities,Microsoft::WRL::ComPtr<IXMLDOMDocument2> &>(
            &v192,
            (__int64)&v190);
    v18 = *v17;
    v205[0] = *v17;
    v205[1] = v17[1];
    *v17 = 0;
    v17[1] = 0;
    v19 = v193;
    if ( v193 )
    {
      if ( _InterlockedExchangeAdd(v193 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::PrintDeviceResourcesSerializer((PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer *)v293);
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
    v196 = v24;
LABEL_23:
    v188 = v23;
    if ( v23 != v24 )
    {
      v25 = (__int64 *)*v23;
      inited = PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(0);
      v194 = 0;
      v27 = inited[1];
      if ( v27 )
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
      v194 = *(_OWORD *)inited;
      v28 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v296, L"DisplayName", (__int64)&v194);
      v29 = v25[5];
      if ( v29 )
        _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
      v206[0] = v25[4];
      v206[1] = v25[5];
      PrintDeviceCapabilitiesOM::Parser::GenericSearchVector<PrintDeviceCapabilitiesOM::Property const>(
        v201,
        (__int64)v28,
        (__int64)v206);
      PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v296);
      v30 = (__int64 *)*v23;
      v31 = *(_QWORD *)(*v23 + 8);
      if ( v31 )
        _InterlockedIncrement((volatile signed __int32 *)(v31 + 8));
      v253 = *v30;
      v32 = (volatile signed __int32 *)v30[1];
      v254 = v32;
      v7 |= 1u;
      if ( !v253 )
        goto LABEL_61;
      v33 = (__int64 *)*v23;
      v34 = *(_QWORD *)(*v23 + 8);
      if ( v34 )
        _InterlockedIncrement((volatile signed __int32 *)(v34 + 8));
      v35 = *v33;
      v225 = v35;
      v226 = (volatile signed __int32 *)v33[1];
      v36 = v7 | 2;
      v37 = *(_QWORD *)(v35 + 24);
      if ( v37 )
        _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
      v223 = *(_QWORD *)(v35 + 16);
      v224 = *(volatile signed __int32 **)(v35 + 24);
      v7 = v36 | 4;
      if ( !v223 )
        goto LABEL_61;
      v38 = (__int64 *)*v23;
      v39 = *(_QWORD *)(*v23 + 8);
      if ( v39 )
        _InterlockedIncrement((volatile signed __int32 *)(v39 + 8));
      v40 = *v38;
      v236 = v40;
      v237 = (volatile signed __int32 *)v38[1];
      v41 = v7 | 8;
      v42 = *(_QWORD *)(v40 + 24);
      if ( v42 )
        _InterlockedIncrement((volatile signed __int32 *)(v42 + 8));
      v221 = *(_QWORD *)(v40 + 16);
      v222 = *(volatile signed __int32 **)(v40 + 24);
      v7 = v41 | 0x10;
      if ( *(_DWORD *)(v221 + 16) != 8 )
        goto LABEL_61;
      v43 = (__int64 *)*v23;
      v44 = *(_QWORD *)(*v23 + 8);
      if ( v44 )
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 8));
      v45 = *v43;
      v219 = v45;
      v220 = (volatile signed __int32 *)v43[1];
      v46 = v7 | 0x20;
      v47 = *(_QWORD *)(v45 + 24);
      if ( v47 )
        _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
      v48 = *(_QWORD **)(v45 + 16);
      v217 = v48;
      v218 = *(volatile signed __int32 **)(v45 + 24);
      v49 = v46 | 0x40;
      v50 = v48[1];
      if ( v50 )
        _InterlockedIncrement((volatile signed __int32 *)(v50 + 8));
      v215 = *v48;
      v216 = (volatile signed __int32 *)v48[1];
      v7 = v49 | 0x80;
      if ( !v215 )
        goto LABEL_61;
      v51 = *v23;
      v52 = *(_QWORD *)(*v23 + 8);
      if ( v52 )
        _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
      v53 = *(_QWORD **)v51;
      v213 = v53;
      v214 = *(volatile signed __int32 **)(v51 + 8);
      v54 = v7 | 0x100;
      v55 = v53[1];
      if ( v55 )
        _InterlockedIncrement((volatile signed __int32 *)(v55 + 8));
      v211 = *v53;
      v212 = (volatile signed __int32 *)v53[1];
      v7 = v54 | 0x200;
      if ( v211 )
      {
        v56 = v201[0];
        if ( v201[0] )
        {
          v57 = *(_QWORD *)(v201[0] + 24LL);
          if ( v57 )
            _InterlockedIncrement((volatile signed __int32 *)(v57 + 8));
          v209 = *(_QWORD *)(v56 + 16);
          v58 = *(volatile signed __int32 **)(v56 + 24);
          v210 = v58;
          v7 |= 0x400u;
          if ( v209 )
          {
            if ( v58 )
              _InterlockedIncrement(v58 + 2);
            v207 = *(_QWORD *)(v56 + 16);
            v208 = *(volatile signed __int32 **)(v56 + 24);
            v7 |= 0x1800u;
            if ( *PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v207, &v255) )
            {
              v59 = 1;
LABEL_63:
              if ( (v7 & 0x1000) != 0 )
              {
                v7 &= ~0x1000u;
                v60 = v256;
                if ( v256 )
                {
                  if ( _InterlockedExchangeAdd(v256 + 2, 0xFFFFFFFF) == 1 )
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
                v61 = v208;
                if ( v208 )
                {
                  if ( _InterlockedExchangeAdd(v208 + 2, 0xFFFFFFFF) == 1 )
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
                v62 = v210;
                if ( v210 )
                {
                  if ( _InterlockedExchangeAdd(v210 + 2, 0xFFFFFFFF) == 1 )
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
                v63 = v212;
                if ( v212 )
                {
                  if ( _InterlockedExchangeAdd(v212 + 2, 0xFFFFFFFF) == 1 )
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
                v64 = v214;
                if ( v214 )
                {
                  if ( _InterlockedExchangeAdd(v214 + 2, 0xFFFFFFFF) == 1 )
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
                v65 = v216;
                if ( v216 )
                {
                  if ( _InterlockedExchangeAdd(v216 + 2, 0xFFFFFFFF) == 1 )
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
                v66 = v218;
                if ( v218 )
                {
                  if ( _InterlockedExchangeAdd(v218 + 2, 0xFFFFFFFF) == 1 )
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
                v67 = v220;
                if ( v220 )
                {
                  if ( _InterlockedExchangeAdd(v220 + 2, 0xFFFFFFFF) == 1 )
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
                v68 = v222;
                if ( v222 )
                {
                  if ( _InterlockedExchangeAdd(v222 + 2, 0xFFFFFFFF) == 1 )
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
                v69 = v237;
                if ( v237 )
                {
                  if ( _InterlockedExchangeAdd(v237 + 2, 0xFFFFFFFF) == 1 )
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
                v70 = v224;
                if ( v224 )
                {
                  if ( _InterlockedExchangeAdd(v224 + 2, 0xFFFFFFFF) == 1 )
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
                v71 = v226;
                if ( v226 )
                {
                  if ( _InterlockedExchangeAdd(v226 + 2, 0xFFFFFFFF) == 1 )
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
              v72 = (__int64 *)*v188;
              v73 = *(_QWORD *)(*v188 + 8);
              if ( v73 )
                _InterlockedIncrement((volatile signed __int32 *)(v73 + 8));
              v74 = *v72;
              v257 = v74;
              v75 = (volatile signed __int32 *)v72[1];
              v258 = v75;
              v76 = *(_QWORD *)(v74 + 24);
              if ( v76 )
                _InterlockedIncrement((volatile signed __int32 *)(v76 + 8));
              v77 = *(_QWORD *)(v74 + 16);
              v259 = v77;
              v78 = *(volatile signed __int32 **)(v74 + 24);
              v260 = v78;
              v79 = *(_QWORD *)(v77 + 8);
              if ( v79 )
                _InterlockedIncrement((volatile signed __int32 *)(v79 + 8));
              v80 = *(_QWORD **)v77;
              v261 = v80;
              v81 = *(volatile signed __int32 **)(v77 + 8);
              v262 = v81;
              if ( v80[3] > 7u )
                v80 = (_QWORD *)*v80;
              Src = 0;
              v299 = 0;
              v300 = 0;
              v82 = -1;
              do
                ++v82;
              while ( *((_WORD *)v80 + v82) );
              std::wstring::_Construct<1,unsigned short const *>(&Src, v80, v82);
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
              if ( v299 )
              {
                p_Src = &Src;
                if ( v300 > 7 )
                  p_Src = (__int128 *)Src;
                if ( *((_WORD *)p_Src + v299 - 1) != 47 )
                  std::wstring::append((void **)&Src, L"/", v83);
              }
              v85 = *v188;
              v86 = *(_QWORD *)(*v188 + 8);
              if ( v86 )
                _InterlockedIncrement((volatile signed __int32 *)(v86 + 8));
              v87 = *(_QWORD **)v85;
              v263 = v87;
              v88 = *(volatile signed __int32 **)(v85 + 8);
              v264 = v88;
              v89 = v87[1];
              if ( v89 )
                _InterlockedIncrement((volatile signed __int32 *)(v89 + 8));
              v90 = (__int64 *)*v87;
              v265 = v90;
              v91 = (volatile signed __int32 *)v87[1];
              v266 = v91;
              if ( (unsigned __int64)v90[3] > 7 )
                v90 = (__int64 *)*v90;
              std::wstring::append((void **)&Src, v90, v83);
              if ( v91 )
              {
                if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v91)(v91);
                  if ( _InterlockedExchangeAdd(v91 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v91 + 8LL))(v91);
                }
              }
              if ( v88 )
              {
                if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
                  if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
                }
              }
              if ( v299 )
              {
                v92 = *(_QWORD *)(v56 + 24);
                if ( v92 )
                  _InterlockedIncrement((volatile signed __int32 *)(v92 + 8));
                v227 = *(_QWORD *)(v56 + 16);
                v93 = *(volatile signed __int32 **)(v56 + 24);
                v228 = v93;
                v7 |= 0x6000u;
                if ( *(_QWORD *)(*PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v227, &v267) + 16LL) )
                {
                  v94 = 1;
                  goto LABEL_177;
                }
              }
              else
              {
                v93 = v228;
              }
              v94 = 0;
LABEL_177:
              if ( (v7 & 0x4000) != 0 )
              {
                v7 &= ~0x4000u;
                v95 = v268;
                if ( v268 )
                {
                  if ( _InterlockedExchangeAdd(v268 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
                    if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
                  }
                }
              }
              if ( (v7 & 0x2000) != 0 )
              {
                v7 &= ~0x2000u;
                if ( v93 )
                {
                  if ( _InterlockedExchangeAdd(v93 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v93)(v93);
                    if ( _InterlockedExchangeAdd(v93 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v93 + 8LL))(v93);
                  }
                }
              }
              if ( v94 )
              {
                v96 = *(_QWORD *)(v56 + 24);
                if ( v96 )
                  _InterlockedIncrement((volatile signed __int32 *)(v96 + 8));
                v269 = *(_QWORD *)(v56 + 16);
                v97 = *(volatile signed __int32 **)(v56 + 24);
                v270 = v97;
                v98 = (const unsigned __int16 *)*PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(
                                                   v269,
                                                   &v271);
                PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::AddEntry(
                  (__int64)v293,
                  &Src,
                  v98);
                v99 = v272;
                if ( v272 )
                {
                  if ( _InterlockedExchangeAdd(v272 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
                    if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
                  }
                }
                if ( v97 )
                {
                  if ( _InterlockedExchangeAdd(v97 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
                    if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
                  }
                }
              }
              std::wstring::~wstring((char **)&Src);
LABEL_199:
              v100 = *v188;
              v101 = *(_QWORD *)(*v188 + 24);
              if ( v101 )
                _InterlockedIncrement((volatile signed __int32 *)(v101 + 8));
              v102 = *(__int64 ***)(v100 + 16);
              v103 = *(volatile signed __int32 **)(v100 + 24);
              if ( v103 )
              {
                if ( _InterlockedExchangeAdd(v103 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v103)(v103);
                  if ( _InterlockedExchangeAdd(v103 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v103 + 8LL))(v103);
                }
              }
              v104 = *v102;
              v105 = v102[1];
              for ( i = v105; ; v105 = i )
              {
                v189 = v104;
                if ( v104 == v105 )
                {
                  std::shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>::~shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>(v201);
                  v23 = v188 + 2;
                  v24 = v196;
                  goto LABEL_23;
                }
                v106 = (__int64 *)*v104;
                v107 = PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(0);
                v195 = 0;
                v108 = v107[1];
                v109 = 1;
                if ( v108 )
                  _InterlockedAdd((volatile signed __int32 *)(v108 + 8), 1u);
                v195 = *(_OWORD *)v107;
                v110 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v297, L"DisplayName", (__int64)&v195);
                v111 = v106[5];
                if ( v111 )
                  _InterlockedAdd((volatile signed __int32 *)(v111 + 8), 1u);
                v229[0] = v106[4];
                v229[1] = v106[5];
                PrintDeviceCapabilitiesOM::Parser::GenericSearchVector<PrintDeviceCapabilitiesOM::Property const>(
                  &v199,
                  (__int64)v110,
                  (__int64)v229);
                PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v297);
                v112 = (__int64 *)*v104;
                v113 = *(_QWORD *)(*v104 + 8);
                if ( v113 )
                  _InterlockedAdd((volatile signed __int32 *)(v113 + 8), 1u);
                v273 = *v112;
                v114 = (volatile signed __int32 *)v112[1];
                v274 = v114;
                v7 |= 0x8000u;
                if ( !v273 )
                  break;
                v115 = (__int64 *)*v104;
                v116 = *(_QWORD *)(*v104 + 8);
                if ( v116 )
                  _InterlockedAdd((volatile signed __int32 *)(v116 + 8), 1u);
                v117 = *v115;
                v201[2] = v117;
                v202 = (volatile signed __int32 *)v115[1];
                v118 = v7 | 0x10000;
                v119 = *(_QWORD *)(v117 + 24);
                if ( v119 )
                  _InterlockedAdd((volatile signed __int32 *)(v119 + 8), 1u);
                v248 = *(_QWORD *)(v117 + 16);
                v249 = *(volatile signed __int32 **)(v117 + 24);
                v7 = v118 | 0x20000;
                if ( !v248 )
                  break;
                v120 = (__int64 *)*v104;
                v121 = *(_QWORD *)(*v104 + 8);
                if ( v121 )
                  _InterlockedAdd((volatile signed __int32 *)(v121 + 8), 1u);
                v122 = *v120;
                v246 = v122;
                v247 = (volatile signed __int32 *)v120[1];
                v123 = v7 | 0x40000;
                v124 = *(_QWORD *)(v122 + 24);
                if ( v124 )
                  _InterlockedAdd((volatile signed __int32 *)(v124 + 8), 1u);
                v244 = *(_QWORD *)(v122 + 16);
                v245 = *(volatile signed __int32 **)(v122 + 24);
                v7 = v123 | 0x80000;
                if ( *(_DWORD *)(v244 + 16) != 8 )
                  break;
                v125 = (__int64 *)*v104;
                v126 = *(_QWORD *)(*v104 + 8);
                if ( v126 )
                  _InterlockedAdd((volatile signed __int32 *)(v126 + 8), 1u);
                v127 = *v125;
                v242 = v127;
                v243 = (volatile signed __int32 *)v125[1];
                v128 = v7 | 0x100000;
                v129 = *(_QWORD *)(v127 + 24);
                if ( v129 )
                  _InterlockedAdd((volatile signed __int32 *)(v129 + 8), 1u);
                v130 = *(_QWORD **)(v127 + 16);
                v240 = v130;
                v241 = *(volatile signed __int32 **)(v127 + 24);
                v131 = v128 | 0x200000;
                v132 = v130[1];
                if ( v132 )
                  _InterlockedAdd((volatile signed __int32 *)(v132 + 8), 1u);
                v238 = *v130;
                v239 = (volatile signed __int32 *)v130[1];
                v7 = v131 | 0x400000;
                if ( !v238 )
                  break;
                v133 = *v104;
                v134 = *(_QWORD *)(*v104 + 8);
                if ( v134 )
                  _InterlockedAdd((volatile signed __int32 *)(v134 + 8), 1u);
                v135 = *(_QWORD **)v133;
                v203 = v135;
                v204 = *(volatile signed __int32 **)(v133 + 8);
                v136 = v7 | 0x800000;
                v137 = v135[1];
                if ( v137 )
                  _InterlockedAdd((volatile signed __int32 *)(v137 + 8), 1u);
                v234 = *v135;
                v235 = (volatile signed __int32 *)v135[1];
                v7 = v136 | 0x1000000;
                if ( !v234 )
                  break;
                v138 = v199;
                if ( !v199 )
                  goto LABEL_245;
                v139 = *(_QWORD *)(v199 + 24);
                if ( v139 )
                  _InterlockedAdd((volatile signed __int32 *)(v139 + 8), 1u);
                v232 = *(_QWORD *)(v138 + 16);
                v140 = *(volatile signed __int32 **)(v138 + 24);
                v233 = v140;
                v7 |= 0x2000000u;
                if ( !v232 )
                  goto LABEL_245;
                if ( v140 )
                  _InterlockedAdd(v140 + 2, 1u);
                v230 = *(_QWORD *)(v138 + 16);
                v231 = *(volatile signed __int32 **)(v138 + 24);
                v7 |= 0xC000000u;
                if ( !*PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v230, &v275) )
                  goto LABEL_245;
LABEL_246:
                if ( (v7 & 0x8000000) != 0 )
                {
                  v7 &= ~0x8000000u;
                  v141 = v276;
                  if ( v276 )
                  {
                    if ( _InterlockedExchangeAdd(v276 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v141)(v141);
                      if ( _InterlockedExchangeAdd(v141 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v141 + 8LL))(v141);
                    }
                  }
                }
                if ( (v7 & 0x4000000) != 0 )
                {
                  v7 &= ~0x4000000u;
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
                if ( (v7 & 0x2000000) != 0 )
                {
                  v7 &= ~0x2000000u;
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
                if ( (v7 & 0x1000000) != 0 )
                {
                  v7 &= ~0x1000000u;
                  v144 = v235;
                  if ( v235 )
                  {
                    if ( _InterlockedExchangeAdd(v235 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v144)(v144);
                      if ( _InterlockedExchangeAdd(v144 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v144 + 8LL))(v144);
                    }
                  }
                }
                if ( (v7 & 0x800000) != 0 )
                {
                  v7 &= ~0x800000u;
                  v145 = v204;
                  if ( v204 )
                  {
                    if ( _InterlockedExchangeAdd(v204 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v145)(v145);
                      if ( _InterlockedExchangeAdd(v145 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v145 + 8LL))(v145);
                    }
                  }
                }
                if ( (v7 & 0x400000) != 0 )
                {
                  v7 &= ~0x400000u;
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
                if ( (v7 & 0x200000) != 0 )
                {
                  v7 &= ~0x200000u;
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
                if ( (v7 & 0x100000) != 0 )
                {
                  v7 &= ~0x100000u;
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
                if ( (v7 & 0x80000) != 0 )
                {
                  v7 &= ~0x80000u;
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
                if ( (v7 & 0x40000) != 0 )
                {
                  v7 &= ~0x40000u;
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
                if ( (v7 & 0x20000) != 0 )
                {
                  v7 &= ~0x20000u;
                  v151 = v249;
                  if ( v249 )
                  {
                    if ( _InterlockedExchangeAdd(v249 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v151)(v151);
                      if ( _InterlockedExchangeAdd(v151 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v151 + 8LL))(v151);
                    }
                  }
                }
                if ( (v7 & 0x10000) != 0 )
                {
                  v7 &= ~0x10000u;
                  v152 = v202;
                  if ( v202 )
                  {
                    if ( _InterlockedExchangeAdd(v202 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v152)(v152);
                      if ( _InterlockedExchangeAdd(v152 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v152 + 8LL))(v152);
                    }
                  }
                }
                if ( (v7 & 0x8000) != 0 )
                {
                  v7 &= ~0x8000u;
                  if ( v114 )
                  {
                    if ( _InterlockedExchangeAdd(v114 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v114)(v114);
                      if ( _InterlockedExchangeAdd(v114 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v114 + 8LL))(v114);
                    }
                  }
                }
                if ( v109 )
                {
                  v153 = (__int64 *)*v189;
                  v154 = *(_QWORD *)(*v189 + 8);
                  if ( v154 )
                    _InterlockedIncrement((volatile signed __int32 *)(v154 + 8));
                  v155 = *v153;
                  v277 = v155;
                  v156 = (volatile signed __int32 *)v153[1];
                  v278 = v156;
                  v157 = *(_QWORD *)(v155 + 24);
                  if ( v157 )
                    _InterlockedIncrement((volatile signed __int32 *)(v157 + 8));
                  v158 = *(_QWORD *)(v155 + 16);
                  v279 = v158;
                  v159 = *(volatile signed __int32 **)(v155 + 24);
                  v280 = v159;
                  v160 = *(_QWORD *)(v158 + 8);
                  if ( v160 )
                    _InterlockedIncrement((volatile signed __int32 *)(v160 + 8));
                  v161 = *(_QWORD **)v158;
                  v281 = v161;
                  v162 = *(volatile signed __int32 **)(v158 + 8);
                  v282 = v162;
                  if ( v161[3] > 7u )
                    v161 = (_QWORD *)*v161;
                  v301 = 0;
                  v302 = 0;
                  v303 = 0;
                  v163 = -1;
                  do
                    ++v163;
                  while ( *((_WORD *)v161 + v163) );
                  std::wstring::_Construct<1,unsigned short const *>(&v301, v161, v163);
                  if ( v162 )
                  {
                    if ( _InterlockedExchangeAdd(v162 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v162)(v162);
                      if ( _InterlockedExchangeAdd(v162 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v162 + 8LL))(v162);
                    }
                  }
                  if ( v159 )
                  {
                    if ( _InterlockedExchangeAdd(v159 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v159)(v159);
                      if ( _InterlockedExchangeAdd(v159 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v159 + 8LL))(v159);
                    }
                  }
                  if ( v156 )
                  {
                    if ( _InterlockedExchangeAdd(v156 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v156)(v156);
                      if ( _InterlockedExchangeAdd(v156 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v156 + 8LL))(v156);
                    }
                  }
                  if ( v302 )
                  {
                    v165 = &v301;
                    if ( v303 > 7 )
                      v165 = (__int128 *)v301;
                    if ( *((_WORD *)v165 + v302 - 1) != 47 )
                      std::wstring::append((void **)&v301, L"/", v164);
                  }
                  v166 = *v189;
                  v167 = *(_QWORD *)(*v189 + 8);
                  if ( v167 )
                    _InterlockedIncrement((volatile signed __int32 *)(v167 + 8));
                  v168 = *(_QWORD **)v166;
                  v283 = v168;
                  v169 = *(volatile signed __int32 **)(v166 + 8);
                  v284 = v169;
                  v170 = v168[1];
                  if ( v170 )
                    _InterlockedIncrement((volatile signed __int32 *)(v170 + 8));
                  v171 = (__int64 *)*v168;
                  v285 = v171;
                  v172 = (volatile signed __int32 *)v168[1];
                  v286 = v172;
                  if ( (unsigned __int64)v171[3] > 7 )
                    v171 = (__int64 *)*v171;
                  std::wstring::append((void **)&v301, v171, v164);
                  if ( v172 )
                  {
                    if ( _InterlockedExchangeAdd(v172 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v172)(v172);
                      if ( _InterlockedExchangeAdd(v172 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v172 + 8LL))(v172);
                    }
                  }
                  if ( v169 )
                  {
                    if ( _InterlockedExchangeAdd(v169 + 2, 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v169)(v169);
                      if ( _InterlockedExchangeAdd(v169 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v169 + 8LL))(v169);
                    }
                  }
                  if ( v302 )
                  {
                    v173 = *(_QWORD *)(v138 + 24);
                    if ( v173 )
                      _InterlockedIncrement((volatile signed __int32 *)(v173 + 8));
                    v192 = *(_QWORD *)(v138 + 16);
                    v174 = *(volatile signed __int32 **)(v138 + 24);
                    v193 = v174;
                    v7 |= 0x30000000u;
                    if ( *(_QWORD *)(*PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(v192, &v287) + 16LL) )
                    {
                      v175 = 1;
                      goto LABEL_360;
                    }
                  }
                  else
                  {
                    v174 = v193;
                  }
                  v175 = 0;
LABEL_360:
                  if ( (v7 & 0x20000000) != 0 )
                  {
                    v7 &= ~0x20000000u;
                    v176 = v288;
                    if ( v288 )
                    {
                      if ( _InterlockedExchangeAdd(v288 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v176)(v176);
                        if ( _InterlockedExchangeAdd(v176 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v176 + 8LL))(v176);
                      }
                    }
                  }
                  if ( (v7 & 0x10000000) != 0 )
                  {
                    v7 &= ~0x10000000u;
                    if ( v174 )
                    {
                      if ( _InterlockedExchangeAdd(v174 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v174)(v174);
                        if ( _InterlockedExchangeAdd(v174 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v174 + 8LL))(v174);
                      }
                    }
                  }
                  if ( v175 )
                  {
                    v177 = *(_QWORD *)(v138 + 24);
                    if ( v177 )
                      _InterlockedIncrement((volatile signed __int32 *)(v177 + 8));
                    v289 = *(_QWORD *)(v138 + 16);
                    v178 = *(volatile signed __int32 **)(v138 + 24);
                    v290 = v178;
                    v179 = (const unsigned __int16 *)*PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue::String(
                                                        v289,
                                                        &v291);
                    PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::AddEntry(
                      (__int64)v293,
                      &v301,
                      v179);
                    v180 = v292;
                    if ( v292 )
                    {
                      if ( _InterlockedExchangeAdd(v292 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v180)(v180);
                        if ( _InterlockedExchangeAdd(v180 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v180 + 8LL))(v180);
                      }
                    }
                    if ( v178 )
                    {
                      if ( _InterlockedExchangeAdd(v178 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v178)(v178);
                        if ( _InterlockedExchangeAdd(v178 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v178 + 8LL))(v178);
                      }
                    }
                  }
                  std::wstring::~wstring((char **)&v301);
                }
                v181 = v200;
                if ( v200 && _InterlockedExchangeAdd(v200 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v181)(v181);
                  if ( _InterlockedExchangeAdd(v181 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v181 + 8LL))(v181);
                }
                v104 = v189 + 2;
              }
              v138 = v199;
LABEL_245:
              v109 = 0;
              goto LABEL_246;
            }
          }
        }
      }
      else
      {
LABEL_61:
        v56 = v201[0];
      }
      v59 = 0;
      goto LABEL_63;
    }
    v182 = v294;
    if ( v294 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v294->lpVtbl->AddRef)(v294);
    *v197 = v182;
    PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::~PrintDeviceResourcesSerializer((PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer *)v293);
    std::shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>::~shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Feature>>>(v205);
    v183 = v190;
    if ( v190 )
    {
      v190 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v183 + 16LL))(v183);
    }
  }
  catch ( std::bad_alloc )
  {
    v185 = -2147024882;
  }
  catch ( const hr_error *v251 )
  {
    v185 = *((_DWORD *)v251 + 6);
  }
  catch ( const PrintCore::WindowsError *v252 )
  {
    v185 = *((_DWORD *)v252 + 6);
  }
  catch ( std::exception )
  {
    v185 = -2147467259;
  }
  catch ( ... )
  {
    v185 = -2147418113;
  }
  v184 = (WCHAR *)pwszLanguagesBuffer;
  SetThreadPreferredUILanguages(8u, pwszLanguagesBuffer, &pulNumLanguages);
  if ( v184 )
    CoTaskMemFree(v184);
  return v185;
}

```

## disassembly

```asm
0x18012f3d0  push    rbx
0x18012f3d2  push    rsi
0x18012f3d3  push    rdi
0x18012f3d4  push    r12
0x18012f3d6  push    r13
0x18012f3d8  push    r14
0x18012f3da  push    r15
0x18012f3dc  sub     rsp, 490h
0x18012f3e3  mov     [rsp+4C8h+var_268], 0FFFFFFFFFFFFFFFEh
0x18012f3ef  mov     rax, cs:__security_cookie
0x18012f3f6  xor     rax, rsp
0x18012f3f9  mov     [rsp+4C8h+var_48], rax
0x18012f401  mov     [rsp+4C8h+var_438], r9
0x18012f409  mov     r12, r8
0x18012f40c  mov     r15, rdx
0x18012f40f  mov     r14, rcx
0x18012f412  xor     edi, edi
0x18012f414  mov     r13d, edi
0x18012f417  mov     [rsp+4C8h+var_4A8], edi; int
0x18012f41b  test    r9, r9
0x18012f41e  jnz     short loc_18012F42A
0x18012f420  mov     eax, 80004003h
0x18012f425  jmp     loc_180130F46
0x18012f42a  mov     [rsp+4C8h+pulNumLanguages], edi
0x18012f42e  mov     [rsp+4C8h+pcchLanguagesBuffer], edi
0x18012f432  lea     r9, [rsp+4C8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18012f437  xor     r8d, r8d; pwszLanguagesBuffer
0x18012f43a  lea     rdx, [rsp+4C8h+pulNumLanguages]; pulNumLanguages
0x18012f43f  lea     ecx, [r8+48h]; dwFlags
0x18012f443  call    cs:__imp_GetThreadPreferredUILanguages
0x18012f44a  nop     dword ptr [rax+rax+00h]
0x18012f44f  test    eax, eax
0x18012f451  jnz     short loc_18012F471
0x18012f453  mov     rcx, [rsp+4C8h]; this
0x18012f45b  lea     r8, aPrintscanPrint_21; "printscan\\print\\drivers\\usermode\\dr"...
0x18012f462  mov     edx, 0AB9h; void *
0x18012f467  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012f46c  jmp     loc_180130F46
0x18012f471  mov     ebx, [rsp+4C8h+pcchLanguagesBuffer]
0x18012f475  lea     rcx, ds:2[rbx*2]; cb
0x18012f47d  call    cs:__imp_CoTaskMemAlloc
0x18012f484  nop     dword ptr [rax+rax+00h]
0x18012f489  mov     rsi, rax
0x18012f48c  test    rax, rax
0x18012f48f  jz      short loc_18012F498
0x18012f491  mov     [rax], di
0x18012f494  mov     [rax+rbx*2], di
0x18012f498  mov     [rsp+4C8h+pwszLanguagesBuffer], rsi
0x18012f4a0  test    rsi, rsi
0x18012f4a3  jz      loc_180130F22
0x18012f4a9  lea     r9, [rsp+4C8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18012f4ae  mov     r8, rsi; pwszLanguagesBuffer
0x18012f4b1  lea     rdx, [rsp+4C8h+pulNumLanguages]; pulNumLanguages
0x18012f4b6  mov     ecx, 48h ; 'H'; dwFlags
0x18012f4bb  call    cs:__imp_GetThreadPreferredUILanguages
0x18012f4c2  nop     dword ptr [rax+rax+00h]
0x18012f4c7  test    eax, eax
0x18012f4c9  jnz     short loc_18012F4FA
0x18012f4cb  mov     rcx, [rsp+4C8h]; this
0x18012f4d3  lea     r8, aPrintscanPrint_21; "printscan\\print\\drivers\\usermode\\dr"...
0x18012f4da  mov     edx, 0AC0h; void *
0x18012f4df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012f4e4  mov     ebx, eax
0x18012f4e6  mov     rcx, rsi; pv
0x18012f4e9  call    cs:__imp_CoTaskMemFree
0x18012f4f0  nop     dword ptr [rax+rax+00h]
0x18012f4f5  jmp     loc_180130F44
0x18012f4fa  mov     [rsp+4C8h+var_4A0], edi
0x18012f4fe  xor     edx, edx; dwFlags
0x18012f500  mov     rcx, r15; lpName
0x18012f503  call    cs:__imp_LocaleNameToLCID
0x18012f50a  nop     dword ptr [rax+rax+00h]
0x18012f50f  mov     ecx, eax; LangId
0x18012f511  call    cs:__imp_SetThreadUILanguage
0x18012f518  nop     dword ptr [rax+rax+00h]
0x18012f51d  nop
0x18012f51e  mov     [rsp+4C8h+var_480], rdi
0x18012f523  mov     rax, [r14]
0x18012f526  lea     r8, [rsp+4C8h+var_480]
0x18012f52b  mov     rdx, r12
0x18012f52e  mov     rcx, r14
0x18012f531  mov     rax, [rax+40h]
0x18012f535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f53a  test    eax, eax
0x18012f53c  js      loc_180130F6A
0x18012f542  lea     rdx, [rsp+4C8h+var_480]
0x18012f547  lea     rcx, [rsp+4C8h+var_470]
0x18012f54c  call    ??$make_shared@VPrintCapabilities@PrintDeviceCapabilitiesOM@@AEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@VPrintCapabilities@PrintDeviceCapabilitiesOM@@@0@AEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintCapabilities,Microsoft::WRL::ComPtr<IXMLDOMDocument2> &>(Microsoft::WRL::ComPtr<IXMLDOMDocument2> &)
0x18012f551  mov     rsi, [rax]
0x18012f554  mov     [rsp+4C8h+var_3E8], rsi
0x18012f55c  mov     rcx, [rax+8]
0x18012f560  mov     [rsp+4C8h+var_3E0], rcx
0x18012f568  mov     [rax], rdi
0x18012f56b  mov     [rax+8], rdi
0x18012f56f  mov     rbx, [rsp+4C8h+var_468]
0x18012f574  or      r15, 0FFFFFFFFFFFFFFFFh
0x18012f578  test    rbx, rbx
0x18012f57b  jz      short loc_18012F5B4
0x18012f57d  mov     eax, r15d
0x18012f580  lock xadd [rbx+8], eax
0x18012f585  add     eax, r15d
0x18012f588  jnz     short loc_18012F5B4
0x18012f58a  mov     rax, [rbx]
0x18012f58d  mov     rcx, rbx
0x18012f590  mov     rax, [rax]
0x18012f593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f598  mov     eax, r15d
0x18012f59b  lock xadd [rbx+0Ch], eax
0x18012f5a0  add     eax, r15d
0x18012f5a3  jnz     short loc_18012F5B4
0x18012f5a5  mov     rax, [rbx]
0x18012f5a8  mov     rcx, rbx
0x18012f5ab  mov     rax, [rax+8]
0x18012f5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f5b4  lea     rcx, [rsp+4C8h+var_110]; this
0x18012f5bc  call    ??0PrintDeviceResourcesSerializer@Serializer@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::PrintDeviceResourcesSerializer(void)
0x18012f5c1  nop
0x18012f5c2  mov     rax, [rsi+8]
0x18012f5c6  test    rax, rax
0x18012f5c9  jz      short loc_18012F5CF
0x18012f5cb  lock inc dword ptr [rax+8]
0x18012f5cf  mov     r14, [rsi]
0x18012f5d2  mov     rbx, [rsi+8]
0x18012f5d6  test    rbx, rbx
0x18012f5d9  jz      short loc_18012F612
0x18012f5db  mov     eax, r15d
0x18012f5de  lock xadd [rbx+8], eax
0x18012f5e3  add     eax, r15d
0x18012f5e6  jnz     short loc_18012F612
0x18012f5e8  mov     rax, [rbx]
0x18012f5eb  mov     rcx, rbx
0x18012f5ee  mov     rax, [rax]
0x18012f5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f5f6  mov     eax, r15d
0x18012f5f9  lock xadd [rbx+0Ch], eax
0x18012f5fe  add     eax, r15d
0x18012f601  jnz     short loc_18012F612
0x18012f603  mov     rax, [rbx]
0x18012f606  mov     rcx, rbx
0x18012f609  mov     rax, [rax+8]
0x18012f60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f612  mov     rsi, [r14]
0x18012f615  mov     rax, [r14+8]
0x18012f619  mov     [rsp+4C8h+var_440], rax
0x18012f621  mov     [rsp+4C8h+var_490], rsi
0x18012f626  cmp     rsi, rax
0x18012f629  jz      loc_180130E7E
0x18012f62f  mov     rbx, [rsi]
0x18012f632  xor     ecx, ecx
0x18012f634  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18012f639  mov     rcx, rax
0x18012f63c  xorps   xmm0, xmm0
0x18012f63f  movdqu  [rsp+4C8h+var_460], xmm0
0x18012f645  mov     rax, [rax+8]
0x18012f649  test    rax, rax
0x18012f64c  jz      short loc_18012F652
0x18012f64e  lock inc dword ptr [rax+8]
0x18012f652  mov     rax, [rcx]
0x18012f655  mov     qword ptr [rsp+4C8h+var_460], rax
0x18012f65a  mov     rax, [rcx+8]
0x18012f65e  mov     qword ptr [rsp+4C8h+var_460+8], rax
0x18012f663  lea     r8, [rsp+4C8h+var_460]
0x18012f668  lea     rdx, aDisplayname_4; "DisplayName"
0x18012f66f  lea     rcx, [rsp+4C8h+var_C8]
0x18012f677  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18012f67c  mov     rdx, rax
0x18012f67f  mov     rcx, [rbx+28h]
0x18012f683  test    rcx, rcx
0x18012f686  jz      short loc_18012F68C
0x18012f688  lock inc dword ptr [rcx+8]
0x18012f68c  mov     rax, [rbx+20h]
0x18012f690  mov     [rsp+4C8h+var_3D8], rax
0x18012f698  mov     rax, [rbx+28h]
0x18012f69c  mov     [rsp+4C8h+var_3D0], rax
0x18012f6a4  lea     r8, [rsp+4C8h+var_3D8]
0x18012f6ac  lea     rcx, [rsp+4C8h+var_418]
0x18012f6b4  call    ??$GenericSearchVector@$$CBVProperty@PrintDeviceCapabilitiesOM@@@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@AEBVQualifiedName@1@V?$shared_ptr@V?$vector@V?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@V?$allocator@V?$shared_ptr@$$CBVProperty@PrintDeviceCapabilitiesOM@@@std@@@2@@std@@@3@@Z; PrintDeviceCapabilitiesOM::Parser::GenericSearchVector<PrintDeviceCapabilitiesOM::Property const>(PrintDeviceCapabilitiesOM::QualifiedName const &,std::shared_ptr<std::vector<std::shared_ptr<PrintDeviceCapabilitiesOM::Property const>>>)
0x18012f6b9  nop
0x18012f6ba  lea     rcx, [rsp+4C8h+var_C8]; this
0x18012f6c2  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18012f6c7  mov     rcx, [rsi]
0x18012f6ca  mov     rax, [rcx+8]
0x18012f6ce  test    rax, rax
0x18012f6d1  jz      short loc_18012F6D7
0x18012f6d3  lock inc dword ptr [rax+8]
0x18012f6d7  mov     rax, [rcx]
0x18012f6da  mov     [rsp+4C8h+var_250], rax
0x18012f6e2  mov     r14, [rcx+8]
0x18012f6e6  mov     [rsp+4C8h+var_248], r14
0x18012f6ee  or      r13d, 1
0x18012f6f2  test    rax, rax
0x18012f6f5  jz      loc_18012F93F
0x18012f6fb  mov     rcx, [rsi]
0x18012f6fe  mov     rax, [rcx+8]
0x18012f702  test    rax, rax
0x18012f705  jz      short loc_18012F70B
0x18012f707  lock inc dword ptr [rax+8]
0x18012f70b  mov     rdx, [rcx]
0x18012f70e  mov     [rsp+4C8h+var_338], rdx
0x18012f716  mov     rax, [rcx+8]
0x18012f71a  mov     [rsp+4C8h+var_330], rax
0x18012f722  or      r13d, 2
0x18012f726  mov     [rsp+4C8h+var_4A8], r13d
0x18012f72b  mov     rax, [rdx+18h]
0x18012f72f  test    rax, rax
0x18012f732  jz      short loc_18012F738
0x18012f734  lock inc dword ptr [rax+8]
0x18012f738  mov     rax, [rdx+10h]
0x18012f73c  mov     [rsp+4C8h+var_348], rax
0x18012f744  mov     rcx, [rdx+18h]
0x18012f748  mov     [rsp+4C8h+var_340], rcx
0x18012f750  or      r13d, 4
0x18012f754  test    rax, rax
0x18012f757  jz      loc_18012F93F
0x18012f75d  mov     rcx, [rsi]
0x18012f760  mov     rax, [rcx+8]
0x18012f764  test    rax, rax
0x18012f767  jz      short loc_18012F76D
0x18012f769  lock inc dword ptr [rax+8]
0x18012f76d  mov     rdx, [rcx]
0x18012f770  mov     [rsp+4C8h+var_2D8], rdx
0x18012f778  mov     rax, [rcx+8]
0x18012f77c  mov     [rsp+4C8h+var_2D0], rax
0x18012f784  or      r13d, 8
0x18012f788  mov     [rsp+4C8h+var_4A8], r13d
0x18012f78d  mov     rax, [rdx+18h]
0x18012f791  test    rax, rax
0x18012f794  jz      short loc_18012F79A
0x18012f796  lock inc dword ptr [rax+8]
0x18012f79a  mov     rax, [rdx+10h]
0x18012f79e  mov     [rsp+4C8h+var_358], rax
0x18012f7a6  mov     rcx, [rdx+18h]
0x18012f7aa  mov     [rsp+4C8h+var_350], rcx
0x18012f7b2  or      r13d, 10h
0x18012f7b6  cmp     dword ptr [rax+10h], 8
0x18012f7ba  jnz     loc_18012F93F
0x18012f7c0  mov     rcx, [rsi]
0x18012f7c3  mov     rax, [rcx+8]
0x18012f7c7  test    rax, rax
0x18012f7ca  jz      short loc_18012F7D0
0x18012f7cc  lock inc dword ptr [rax+8]
0x18012f7d0  mov     rdx, [rcx]
0x18012f7d3  mov     [rsp+4C8h+var_368], rdx
0x18012f7db  mov     rax, [rcx+8]
0x18012f7df  mov     [rsp+4C8h+var_360], rax
0x18012f7e7  or      r13d, 20h
0x18012f7eb  mov     [rsp+4C8h+var_4A8], r13d
0x18012f7f0  mov     rax, [rdx+18h]
0x18012f7f4  test    rax, rax
0x18012f7f7  jz      short loc_18012F7FD
0x18012f7f9  lock inc dword ptr [rax+8]
0x18012f7fd  mov     rcx, [rdx+10h]
0x18012f801  mov     [rsp+4C8h+var_378], rcx
0x18012f809  mov     rax, [rdx+18h]
0x18012f80d  mov     [rsp+4C8h+var_370], rax
0x18012f815  or      r13d, 40h
0x18012f819  mov     [rsp+4C8h+var_4A8], r13d
0x18012f81e  mov     rax, [rcx+8]
0x18012f822  test    rax, rax
0x18012f825  jz      short loc_18012F82B
0x18012f827  lock inc dword ptr [rax+8]
0x18012f82b  mov     rax, [rcx]
0x18012f82e  mov     [rsp+4C8h+var_388], rax
0x18012f836  mov     rdx, [rcx+8]
0x18012f83a  mov     [rsp+4C8h+var_380], rdx
0x18012f842  bts     r13d, 7
0x18012f847  test    rax, rax
0x18012f84a  jz      loc_18012F93F
0x18012f850  mov     rdx, [rsi]
0x18012f853  mov     rax, [rdx+8]
0x18012f857  test    rax, rax
0x18012f85a  jz      short loc_18012F860
0x18012f85c  lock inc dword ptr [rax+8]
0x18012f860  mov     rcx, [rdx]
0x18012f863  mov     [rsp+4C8h+var_398], rcx
0x18012f86b  mov     rax, [rdx+8]
0x18012f86f  mov     [rsp+4C8h+var_390], rax
0x18012f877  bts     r13d, 8
0x18012f87c  mov     [rsp+4C8h+var_4A8], r13d
0x18012f881  mov     rax, [rcx+8]
0x18012f885  test    rax, rax
0x18012f888  jz      short loc_18012F88E
0x18012f88a  lock inc dword ptr [rax+8]
0x18012f88e  mov     rax, [rcx]
0x18012f891  mov     [rsp+4C8h+var_3A8], rax
0x18012f899  mov     rdx, [rcx+8]
0x18012f89d  mov     [rsp+4C8h+var_3A0], rdx
0x18012f8a5  bts     r13d, 9
0x18012f8aa  test    rax, rax
0x18012f8ad  jz      loc_18012F93F
0x18012f8b3  mov     r12, [rsp+4C8h+var_418]
0x18012f8bb  test    r12, r12
0x18012f8be  jz      loc_18012F947
0x18012f8c4  mov     rax, [r12+18h]
0x18012f8c9  test    rax, rax
0x18012f8cc  jz      short loc_18012F8D2
0x18012f8ce  lock inc dword ptr [rax+8]
0x18012f8d2  mov     rax, [r12+10h]
0x18012f8d7  mov     [rsp+4C8h+var_3B8], rax
0x18012f8df  mov     rcx, [r12+18h]
  ... truncated ...
```
