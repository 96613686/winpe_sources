# Windows::Networking::UX::Internal::CategoryBase::_SetStaticIpConfigInternal(Windows::Networking::UX::IStaticIpConfig *,_GUID const &,ulong)

- ea: `0x18007e920`
- end: `0x18007fec0`
- name: `?_SetStaticIpConfigInternal@CategoryBase@Internal@UX@Networking@Windows@@CAJPEAUIStaticIpConfig@345@AEBU_GUID@@K@Z`
- size: `5536`
- prototype: `static int(struct Windows::Networking::UX::IStaticIpConfig *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007e004`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008e30`
- `0x1800097b4`
- `0x18000de4c`
- `0x18001668c`
- `0x18001b230`
- `0x18001be60`
- `0x18001d3f0`
- `0x18001d4d4`
- `0x180029d00`
- `0x18005cfec`
- `0x18007d734`
- `0x18007e3fc`
- `0x18007e7d4`
- `0x18007e920`
- `0x180086d30`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlIpv6StringToAddressExW` at `0x18007f4c9`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18007fb65`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18007fc17`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18007f4c9`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18007fb65`
- `ntdll!RtlIpv6StringToAddressExW` at `0x18007fc17`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18007f3c7`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18007f980`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18007fa2c`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18007f3c7`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18007f980`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18007fa2c`
- `IPHLPAPI!InternalCreateIpForwardEntry2` at `0x18007fd06`
- `IPHLPAPI!InternalCreateIpForwardEntry2` at `0x18007fd06`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x18007f8ff`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x18007f8ff`
- `IPHLPAPI!InternalDeleteIpForwardEntry2` at `0x18007f6e1`
- `IPHLPAPI!InternalDeleteIpForwardEntry2` at `0x18007f6e1`
- `IPHLPAPI!InternalCreateUnicastIpAddressEntry` at `0x18007f588`
- `IPHLPAPI!InternalCreateUnicastIpAddressEntry` at `0x18007f588`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18007f34b`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18007f34b`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x18007f129`
- `IPHLPAPI!InternalDeleteUnicastIpAddressEntry` at `0x18007f129`
- `IPHLPAPI!GetIpForwardTable2` at `0x18007f671`
- `IPHLPAPI!GetIpForwardTable2` at `0x18007f671`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18007f0be`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18007f0be`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18007f014`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18007f014`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f30b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f4ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f8b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007fa14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007fbf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f30b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f4ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f8b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007fa14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007fbf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f1aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f3f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f5f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f64c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fa59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fb92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fc44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fd67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fdc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f1aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f3f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f5f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f64c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fa59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fb92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fc44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fd67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007fdc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CategoryBase::_SetStaticIpConfigInternal(
        struct Windows::Networking::UX::IStaticIpConfig *a1,
        const struct _GUID *a2,
        int a3)
{
  const GUID *v3; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 (__fastcall *v14)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  char v19; // bl
  char DhcpEnabled; // al
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 (__fastcall *v27)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 (__fastcall *v36)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  int v47; // eax
  unsigned int v48; // ebx
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 (__fastcall *v55)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  unsigned int v59; // ebx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 (__fastcall *v70)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *); // rbx
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // r8
  unsigned int v74; // ebx
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // rdx
  __int64 v84; // r8
  int v85; // eax
  unsigned int v86; // ebx
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // r8
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // r8
  char v97; // di
  int StaticIpConfig_Static; // eax
  ADDRESS_FAMILY v99; // r12
  int v100; // eax
  __int64 v101; // rdx
  __int64 v102; // r8
  unsigned int v103; // ebx
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // rdx
  __int64 v115; // r8
  int v116; // eax
  __int64 v117; // rdx
  __int64 v118; // r8
  __int64 v119; // rdx
  __int64 v120; // r8
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // rdx
  __int64 v124; // r8
  __int64 v125; // rdx
  __int64 v126; // r8
  unsigned int v127; // eax
  unsigned int v128; // ebx
  __int64 v129; // rdx
  __int64 v130; // r8
  __int64 v131; // rdx
  __int64 v132; // r8
  __int64 v133; // rdx
  __int64 v134; // r8
  __int64 v135; // rdx
  __int64 v136; // r8
  __int64 v137; // rdx
  __int64 v138; // r8
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // rbx
  PMIB_UNICASTIPADDRESS_TABLE v142; // r8
  int i; // edi
  __int64 v144; // rdx
  unsigned int v145; // eax
  unsigned int j; // esi
  __int64 v147; // rdi
  __int64 (__fastcall *v148)(__int64, _QWORD, HSTRING *); // rbx
  int v149; // eax
  unsigned int v150; // ebx
  __int64 v151; // rdx
  __int64 v152; // r8
  __int64 v153; // rdx
  __int64 v154; // r8
  __int64 v155; // rdx
  __int64 v156; // r8
  __int64 v157; // rdx
  __int64 v158; // r8
  __int64 v159; // rdx
  __int64 v160; // r8
  __int64 v161; // rdx
  __int64 v162; // r8
  int v163; // eax
  unsigned int v164; // ebx
  __int64 v165; // rdx
  __int64 v166; // r8
  __int64 v167; // rdx
  __int64 v168; // r8
  __int64 v169; // rdx
  __int64 v170; // r8
  __int64 v171; // rdx
  __int64 v172; // r8
  __int64 v173; // rdx
  __int64 v174; // r8
  __int64 v175; // rdx
  __int64 v176; // r8
  char v177; // bl
  unsigned int StringRawBuffer; // eax
  const WCHAR *v179; // rax
  LONG v180; // eax
  unsigned int v181; // ebx
  __int64 v182; // rdx
  __int64 v183; // r8
  __int64 v184; // rdx
  __int64 v185; // r8
  __int64 v186; // rdx
  __int64 v187; // r8
  __int64 v188; // rdx
  __int64 v189; // r8
  __int64 v190; // rdx
  __int64 v191; // r8
  __int64 v192; // rdx
  __int64 v193; // r8
  const WCHAR *v194; // rax
  LONG v195; // eax
  unsigned int v196; // ebx
  __int64 v197; // rdx
  __int64 v198; // r8
  __int64 v199; // rdx
  __int64 v200; // r8
  __int64 v201; // rdx
  __int64 v202; // r8
  __int64 v203; // rdx
  __int64 v204; // r8
  __int64 v205; // rdx
  __int64 v206; // r8
  __int64 v207; // rdx
  __int64 v208; // r8
  unsigned int v209; // eax
  unsigned int v210; // ebx
  __int64 v211; // rdx
  __int64 v212; // r8
  __int64 v213; // rdx
  __int64 v214; // r8
  __int64 v215; // rdx
  __int64 v216; // r8
  __int64 v217; // rdx
  __int64 v218; // r8
  __int64 v219; // rdx
  __int64 v220; // r8
  __int64 v221; // rdx
  __int64 v222; // r8
  PMIB_IPFORWARD_TABLE2 k; // r8
  ULONG v224; // ebx
  __int64 v225; // rdx
  unsigned int v226; // eax
  unsigned int m; // esi
  __int64 v228; // rdi
  __int64 (__fastcall *v229)(__int64, _QWORD, HSTRING *); // rbx
  int v230; // eax
  unsigned int v231; // ebx
  __int64 v232; // rdx
  __int64 v233; // r8
  __int64 v234; // rdx
  __int64 v235; // r8
  __int64 v236; // rdx
  __int64 v237; // r8
  __int64 v238; // rdx
  __int64 v239; // r8
  __int64 v240; // rdx
  __int64 v241; // r8
  __int64 v242; // rdx
  __int64 v243; // r8
  int v244; // eax
  unsigned int v245; // ebx
  __int64 v246; // rdx
  __int64 v247; // r8
  __int64 v248; // rdx
  __int64 v249; // r8
  __int64 v250; // rdx
  __int64 v251; // r8
  __int64 v252; // rdx
  __int64 v253; // r8
  __int64 v254; // rdx
  __int64 v255; // r8
  __int64 v256; // rdx
  __int64 v257; // r8
  char v258; // bl
  unsigned int v259; // eax
  LONG v260; // eax
  unsigned int v261; // ebx
  __int64 v262; // rdx
  __int64 v263; // r8
  __int64 v264; // rdx
  __int64 v265; // r8
  __int64 v266; // rdx
  __int64 v267; // r8
  __int64 v268; // rdx
  __int64 v269; // r8
  __int64 v270; // rdx
  __int64 v271; // r8
  __int64 v272; // rdx
  __int64 v273; // r8
  const WCHAR *v274; // rax
  LONG v275; // eax
  unsigned int v276; // ebx
  __int64 v277; // rdx
  __int64 v278; // r8
  __int64 v279; // rdx
  __int64 v280; // r8
  __int64 v281; // rdx
  __int64 v282; // r8
  __int64 v283; // rdx
  __int64 v284; // r8
  __int64 v285; // rdx
  __int64 v286; // r8
  __int64 v287; // rdx
  __int64 v288; // r8
  LONG v289; // eax
  unsigned int v290; // ebx
  __int64 v291; // rdx
  __int64 v292; // r8
  __int64 v293; // rdx
  __int64 v294; // r8
  __int64 v295; // rdx
  __int64 v296; // r8
  __int64 v297; // rdx
  __int64 v298; // r8
  __int64 v299; // rdx
  __int64 v300; // r8
  __int64 v301; // rdx
  __int64 v302; // r8
  const WCHAR *v303; // rax
  LONG v304; // eax
  unsigned int v305; // ebx
  __int64 v306; // rdx
  __int64 v307; // r8
  __int64 v308; // rdx
  __int64 v309; // r8
  __int64 v310; // rdx
  __int64 v311; // r8
  __int64 v312; // rdx
  __int64 v313; // r8
  __int64 v314; // rdx
  __int64 v315; // r8
  __int64 v316; // rdx
  __int64 v317; // r8
  unsigned int v318; // eax
  unsigned int v319; // ebx
  __int64 v320; // rdx
  __int64 v321; // r8
  __int64 v322; // rdx
  __int64 v323; // r8
  __int64 v324; // rdx
  __int64 v325; // r8
  __int64 v326; // rdx
  __int64 v327; // r8
  __int64 v328; // rdx
  __int64 v329; // r8
  __int64 v330; // rdx
  __int64 v331; // r8
  unsigned int v332; // [rsp+20h] [rbp-198h]
  __int64 v333; // [rsp+30h] [rbp-188h] BYREF
  unsigned int v334; // [rsp+38h] [rbp-180h] BYREF
  HSTRING v335; // [rsp+40h] [rbp-178h] BYREF
  __int64 v336; // [rsp+48h] [rbp-170h] BYREF
  __int64 v337; // [rsp+50h] [rbp-168h] BYREF
  USHORT Port[4]; // [rsp+58h] [rbp-160h] BYREF
  __int64 v339; // [rsp+60h] [rbp-158h] BYREF
  __int64 v340; // [rsp+68h] [rbp-150h] BYREF
  __int64 v341; // [rsp+70h] [rbp-148h] BYREF
  HSTRING string; // [rsp+78h] [rbp-140h] BYREF
  unsigned int v343; // [rsp+80h] [rbp-138h] BYREF
  int v344; // [rsp+84h] [rbp-134h] BYREF
  int v345; // [rsp+88h] [rbp-130h]
  int v346; // [rsp+8Ch] [rbp-12Ch] BYREF
  unsigned int v347; // [rsp+90h] [rbp-128h] BYREF
  unsigned int v348; // [rsp+94h] [rbp-124h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+98h] [rbp-120h] BYREF
  PMIB_IPFORWARD_TABLE2 v350; // [rsp+A0h] [rbp-118h] BYREF
  NET_LUID InterfaceLuid; // [rsp+A8h] [rbp-110h] BYREF
  const struct _GUID *v352; // [rsp+B0h] [rbp-108h]
  ADDRESS_FAMILY v353; // [rsp+B8h] [rbp-100h]
  struct in_addr Address[7]; // [rsp+BAh] [rbp-FEh] BYREF
  ADDRESS_FAMILY v355; // [rsp+D8h] [rbp-E0h]
  struct in_addr v356[9]; // [rsp+DAh] [rbp-DEh] BYREF
  struct _MIB_IPFORWARD_ROW2 Row; // [rsp+100h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  LODWORD(v335) = a3;
  v3 = a2;
  v352 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
  v344 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, int *))(*(_QWORD *)a1 + 176LL))(
         a1,
         &v344);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v5,
      v332);
    return v6;
  }
  v334 = 4;
  v333 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, unsigned int *))(*(_QWORD *)a1 + 48LL))(
         a1,
         &v334);
  v11 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v8,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v12, v13);
    return v11;
  }
  v14 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v9, v10);
  v15 = v14(a1, &v333);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v15,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v17, v18);
    return v16;
  }
  if ( v344 == 1 || (v19 = 0, v344 == 4) )
    v19 = 1;
  DhcpEnabled = Windows::Networking::UX::Internal::CategoryBase::_GetDhcpEnabled(v3, v334);
  if ( v19 != DhcpEnabled )
  {
    if ( DhcpEnabled )
    {
      if ( !v19 )
      {
        v345 = 2;
        goto LABEL_20;
      }
    }
    else if ( v19 )
    {
      v345 = 1;
      goto LABEL_20;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)0x80070057LL,
      v332);
  }
  v345 = 0;
LABEL_20:
  v347 = 0;
  if ( v333 )
  {
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v333 + 56LL))(v333, &v347);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v23,
        v332);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v25, v26);
      return v24;
    }
  }
  v337 = 0;
  v27 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v21, v22);
  v28 = v27(a1, &v337);
  v31 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v28,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v32, v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v34, v35);
    return v31;
  }
  v336 = 0;
  v36 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v29, v30);
  v37 = v36(a1, &v336);
  v40 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v37,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v41, v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v43, v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v45, v46);
    return v40;
  }
  v348 = 0;
  if ( v336 )
  {
    v47 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v336 + 56LL))(v336, &v348);
    v48 = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v47,
        v332);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v49, v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v51, v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v53, v54);
      return v48;
    }
  }
  v340 = 0;
  v339 = 0;
  v55 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v38, v39);
  v56 = v55(a1, &v340);
  v59 = v56;
  if ( v56 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v56,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v60, v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v62, v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v64, v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v66, v67);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v68, v69);
    return v59;
  }
  v70 = *(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, __int64 *))(*(_QWORD *)a1 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v57, v58);
  v71 = v70(a1, &v339);
  v74 = v71;
  if ( v71 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v71,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v75, v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v77, v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v79, v80);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v81, v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v83, v84);
    return v74;
  }
  v346 = 0;
  if ( v339 )
  {
    v85 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v339 + 56LL))(v339, &v346);
    v86 = v85;
    if ( v85 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20E,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
        (const char *)(unsigned int)v85,
        v332);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v87, v88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v89, v90);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v91, v92);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v93, v94);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v95, v96);
      return v86;
    }
  }
  v97 = 1;
  v341 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v341, v72, v73);
  StaticIpConfig_Static = Windows::Networking::UX::Internal::CategoryBase::GetStaticIpConfig_Static(v3, v334, &v341);
  if ( StaticIpConfig_Static < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)StaticIpConfig_Static,
      v332);
    goto LABEL_39;
  }
  *(_DWORD *)Port = 0;
  v100 = (*(__int64 (__fastcall **)(__int64, USHORT *))(*(_QWORD *)v341 + 176LL))(v341, Port);
  v103 = v100;
  if ( v100 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
      (const char *)(unsigned int)v100,
      v332);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v341, v104, v105);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v106, v107);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v108, v109);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v110, v111);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v112, v113);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v114, v115);
    return v103;
  }
  if ( v344 == 1 )
  {
    v116 = *(_DWORD *)Port;
    if ( *(_DWORD *)Port == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v341, v101, v102);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v117, v118);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v119, v120);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v121, v122);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v123, v124);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v125, v126);
      return 0;
    }
    goto LABEL_51;
  }
  if ( v344 != 4 )
    goto LABEL_39;
  v116 = *(_DWORD *)Port;
  if ( *(_DWORD *)Port != 1 )
  {
LABEL_51:
    if ( v116 != 4 )
      goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
  v97 = 0;
  LOBYTE(v102) = 1;
  Windows::Networking::UX::Internal::CategoryBase::_EnsureDhcpEnabled(v3, v334, v102);
LABEL_39:
  if ( v334 == 4 )
    v99 = 2;
  else
    v99 = 23;
  InterfaceLuid.Value = 0;
  v127 = ConvertInterfaceGuidToLuid(v3, &InterfaceLuid);
  if ( !v127 )
  {
    if ( v97 )
    {
      if ( v345 == 2 )
        Windows::Networking::UX::Internal::CategoryBase::_EnsureDhcpEnabled(v3, v334, 0);
      Table = 0;
      if ( GetUnicastIpAddressTable(v99, &Table) )
      {
        i = (int)v335;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        v141 = 0;
        v142 = Table;
        for ( i = (int)v335; (unsigned int)v141 < v142->NumEntries; v141 = (unsigned int)(v141 + 1) )
        {
          v144 = (__int64)&v142->Table[v141];
          if ( *(_DWORD *)(v144 + 40) == i
            && *(_WORD *)v144 == v99
            && *(_DWORD *)(v144 + 44) == 1
            && *(_DWORD *)(v144 + 48) == 1 )
          {
            v145 = InternalDeleteUnicastIpAddressEntry(2);
            if ( v145 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                (const char *)v145,
                v332);
            v142 = Table;
          }
        }
      }
      for ( j = 0; j < v347; ++j )
      {
        v353 = 0;
        memset(Address, 0, 26);
        string = 0;
        v343 = 0;
        v147 = v333;
        v148 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v333 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v149 = v148(v147, j, &string);
        v150 = v149;
        if ( v149 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x255,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v149,
            v332);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v341,
            v151,
            v152);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v339,
            v153,
            v154);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v340,
            v155,
            v156);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v336,
            v157,
            v158);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v337,
            v159,
            v160);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v333,
            v161,
            v162);
          return v150;
        }
        v163 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v337 + 48LL))(v337, j, &v343);
        v164 = v163;
        if ( v163 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x256,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v163,
            v332);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v341,
            v165,
            v166);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v339,
            v167,
            v168);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v340,
            v169,
            v170);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v336,
            v171,
            v172);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v337,
            v173,
            v174);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v333,
            v175,
            v176);
          return v164;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v177 = v343;
          StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)WPP_426275660baf32778194b91bb4cd93ce_Traceguids,
            StringRawBuffer,
            v177);
        }
        memset_0(&Row, 0, 0x50u);
        InitializeUnicastIpAddressEntry((PMIB_UNICASTIPADDRESS_ROW)&Row);
        *(NET_LUID *)(&Row.DestinationPrefix.Prefix.si_family + 10) = InterfaceLuid;
        i = (int)v335;
        *(_DWORD *)&Row.DestinationPrefix.PrefixLength = (_DWORD)v335;
        Row.NextHop.Ipv6.sin6_addr.u.Byte[8] = v343;
        *(_QWORD *)&Row.NextHop.Ipv4.sin_family = 0x100000001LL;
        Port[0] = 0;
        if ( v334 == 4 )
        {
          v353 = 2;
          v179 = WindowsGetStringRawBuffer(string, 0);
          v180 = RtlIpv4StringToAddressExW(v179, 1u, (struct in_addr *)&Address[0].S_un.S_un_w.s_w2, Port);
          if ( v180 < 0 )
          {
            v181 = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x268,
                     (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                     (const char *)(unsigned int)v180,
                     v332);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v341,
              v182,
              v183);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v339,
              v184,
              v185);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v340,
              v186,
              v187);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v336,
              v188,
              v189);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v337,
              v190,
              v191);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v333,
              v192,
              v193);
            return v181;
          }
          LOWORD(Row.InterfaceLuid.Value) = v353;
          *(struct _NET_LUID_LH::$0227A65EDE726BD8ABDBF310B0E65A75 *)((char *)&Row.InterfaceLuid.Info + 2) = *(struct _NET_LUID_LH::$0227A65EDE726BD8ABDBF310B0E65A75 *)&Address[0].S_un.S_un_b.s_b1;
          *(struct in_addr *)((char *)&Row.InterfaceIndex + 2) = Address[2];
          Row.DestinationPrefix.Prefix.Ipv4.sin_port = Address[3].S_un.S_un_w.s_w1;
        }
        else if ( v334 == 6 )
        {
          v353 = 23;
          v194 = WindowsGetStringRawBuffer(string, 0);
          v195 = RtlIpv6StringToAddressExW(
                   v194,
                   (struct in6_addr *)&Address[1].S_un.S_un_w.s_w2,
                   (PULONG)&Address[5].S_un.S_un_w.s_w2,
                   Port);
          if ( v195 < 0 )
          {
            v196 = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x26F,
                     (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                     (const char *)(unsigned int)v195,
                     v332);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v341,
              v197,
              v198);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v339,
              v199,
              v200);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v340,
              v201,
              v202);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v336,
              v203,
              v204);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v337,
              v205,
              v206);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v333,
              v207,
              v208);
            return v196;
          }
          LOWORD(Row.InterfaceLuid.Value) = v353;
          *(_OWORD *)((char *)&Row.InterfaceLuid.Info + 2) = *(_OWORD *)&Address[0].S_un.S_un_b.s_b1;
          Row.DestinationPrefix.Prefix.Ipv4 = *(SOCKADDR_IN *)&Address[2].S_un.S_un_w.s_w2;
        }
        v209 = InternalCreateUnicastIpAddressEntry(2, &Row);
        if ( v209 == 5010 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        }
        else if ( v209 )
        {
          v210 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x27A,
                   (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                   (const char *)v209,
                   v332);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v341,
            v211,
            v212);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v339,
            v213,
            v214);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v340,
            v215,
            v216);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v336,
            v217,
            v218);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v337,
            v219,
            v220);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v333,
            v221,
            v222);
          return v210;
        }
        WindowsDeleteString(string);
      }
      v350 = 0;
      if ( !GetIpForwardTable2(v99, &v350) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        v224 = 0;
        for ( k = v350; v224 < k->NumEntries; ++v224 )
        {
          v225 = (__int64)&k->Table[v224];
          if ( *(_DWORD *)(v225 + 8) == i
            && *(_WORD *)(v225 + 44) == v99
            && !*(_BYTE *)(v225 + 40)
            && !*(_DWORD *)(v225 + 100) )
          {
            v226 = InternalDeleteIpForwardEntry2(2);
            if ( v226 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x28C,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                (const char *)v226,
                v332);
            k = v350;
          }
        }
      }
      for ( m = 0; m < v348; ++m )
      {
        v335 = 0;
        v355 = 0;
        memset(v356, 0, 26);
        v343 = 0;
        v228 = v336;
        v229 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v336 + 48LL);
        WindowsDeleteString(0);
        v335 = 0;
        v230 = v229(v228, m, &v335);
        v231 = v230;
        if ( v230 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x297,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v230,
            v332);
          WindowsDeleteString(v335);
          v335 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v341,
            v232,
            v233);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v339,
            v234,
            v235);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v340,
            v236,
            v237);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v336,
            v238,
            v239);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v337,
            v240,
            v241);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v333,
            v242,
            v243);
          return v231;
        }
        v244 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v340 + 48LL))(v340, m, &v343);
        v245 = v244;
        if ( v244 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x298,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
            (const char *)(unsigned int)v244,
            v332);
          WindowsDeleteString(v335);
          v335 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v341,
            v246,
            v247);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v339,
            v248,
            v249);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v340,
            v250,
            v251);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v336,
            v252,
            v253);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v337,
            v254,
            v255);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v333,
            v256,
            v257);
          return v245;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v258 = v343;
          v259 = (unsigned int)WindowsGetStringRawBuffer(v335, 0);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_426275660baf32778194b91bb4cd93ce_Traceguids,
            v259,
            v258);
        }
        memset_0(&Row, 0, sizeof(Row));
        InitializeIpForwardEntry(&Row);
        Row.InterfaceLuid = InterfaceLuid;
        Row.Metric = (unsigned __int8)v343;
        Row.DestinationPrefix.PrefixLength = 0;
        Row.Origin = NlroManual;
        v353 = 0;
        memset(Address, 0, 26);
        Port[0] = 0;
        if ( v334 == 4 )
        {
          v353 = 2;
          v260 = RtlIpv4StringToAddressExW(L"0.0.0.0", 1u, (struct in_addr *)&Address[0].S_un.S_un_w.s_w2, Port);
          if ( v260 < 0 )
          {
            v261 = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x2AA,
                     (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                     (const char *)(unsigned int)v260,
                     v332);
            WindowsDeleteString(v335);
            v335 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v341,
              v262,
              v263);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v339,
              v264,
              v265);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v340,
              v266,
              v267);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v336,
              v268,
              v269);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v337,
              v270,
              v271);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v333,
              v272,
              v273);
            return v261;
          }
          v355 = 2;
          v274 = WindowsGetStringRawBuffer(v335, 0);
          v275 = RtlIpv4StringToAddressExW(v274, 1u, (struct in_addr *)&v356[0].S_un.S_un_w.s_w2, Port);
          if ( v275 < 0 )
          {
            v276 = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x2AE,
                     (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                     (const char *)(unsigned int)v275,
                     v332);
            WindowsDeleteString(v335);
            v335 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v341,
              v277,
              v278);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v339,
              v279,
              v280);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v340,
              v281,
              v282);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v336,
              v283,
              v284);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v337,
              v285,
              v286);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v333,
              v287,
              v288);
            return v276;
          }
          Row.DestinationPrefix.Prefix.Ipv4.sin_family = v353;
          *(_QWORD *)&Row.DestinationPrefix.Prefix.Ipv6.sin6_port = *(_QWORD *)&Address[0].S_un.S_un_b.s_b1;
          *(struct in_addr *)(&Row.DestinationPrefix.Prefix.si_family + 5) = Address[2];
          Row.DestinationPrefix.Prefix.Ipv6.sin6_addr.u.Word[3] = Address[3].S_un.S_un_w.s_w1;
          Row.NextHop.Ipv4.sin_family = v355;
          *(_QWORD *)&Row.NextHop.Ipv6.sin6_port = *(_QWORD *)&v356[0].S_un.S_un_b.s_b1;
          *(struct in_addr *)(&Row.NextHop.si_family + 5) = v356[2];
          Row.NextHop.Ipv6.sin6_addr.u.Word[3] = v356[3].S_un.S_un_w.s_w1;
        }
        else if ( v334 == 6 )
        {
          v353 = 23;
          v289 = RtlIpv6StringToAddressExW(
                   L"::",
                   (struct in6_addr *)&Address[1].S_un.S_un_w.s_w2,
                   (PULONG)&Address[5].S_un.S_un_w.s_w2,
                   Port);
          if ( v289 < 0 )
          {
            v290 = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x2B7,
                     (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                     (const char *)(unsigned int)v289,
                     v332);
            WindowsDeleteString(v335);
            v335 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v341,
              v291,
              v292);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v339,
              v293,
              v294);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v340,
              v295,
              v296);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v336,
              v297,
              v298);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v337,
              v299,
              v300);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v333,
              v301,
              v302);
            return v290;
          }
          v355 = 23;
          v303 = WindowsGetStringRawBuffer(v335, 0);
          v304 = RtlIpv6StringToAddressExW(
                   v303,
                   (struct in6_addr *)&v356[1].S_un.S_un_w.s_w2,
                   (PULONG)&v356[5].S_un.S_un_w.s_w2,
                   Port);
          if ( v304 < 0 )
          {
            v305 = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x2BB,
                     (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                     (const char *)(unsigned int)v304,
                     v332);
            WindowsDeleteString(v335);
            v335 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v341,
              v306,
              v307);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v339,
              v308,
              v309);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v340,
              v310,
              v311);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v336,
              v312,
              v313);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v337,
              v314,
              v315);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v333,
              v316,
              v317);
            return v305;
          }
          Row.DestinationPrefix.Prefix.Ipv4.sin_family = v353;
          *(_OWORD *)&Row.DestinationPrefix.Prefix.Ipv6.sin6_port = *(_OWORD *)&Address[0].S_un.S_un_b.s_b1;
          *(_OWORD *)(&Row.DestinationPrefix.Prefix.si_family + 6) = *(_OWORD *)&Address[2].S_un.S_un_w.s_w2;
          Row.NextHop.Ipv4.sin_family = v355;
          *(_OWORD *)&Row.NextHop.Ipv6.sin6_port = *(_OWORD *)&v356[0].S_un.S_un_b.s_b1;
          *(_OWORD *)(&Row.NextHop.si_family + 6) = *(_OWORD *)&v356[2].S_un.S_un_w.s_w2;
        }
        v318 = InternalCreateIpForwardEntry2(2, &Row);
        if ( v318 == 5010 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
        }
        else if ( v318 )
        {
          v319 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x2C8,
                   (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
                   (const char *)v318,
                   v332);
          WindowsDeleteString(v335);
          v335 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v341,
            v320,
            v321);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v339,
            v322,
            v323);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v340,
            v324,
            v325);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v336,
            v326,
            v327);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v337,
            v328,
            v329);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v333,
            v330,
            v331);
          return v319;
        }
        WindowsDeleteString(v335);
      }
      v3 = v352;
      if ( v345 == 1 )
      {
        LOBYTE(k) = 1;
        Windows::Networking::UX::Internal::CategoryBase::_EnsureDhcpEnabled(v352, v334, k);
      }
    }
    SetInterfaceDns(v334, v3, v339);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_426275660baf32778194b91bb4cd93ce_Traceguids, 0);
    goto LABEL_48;
  }
  v128 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x22B,
           (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\categorybase.cpp",
           (const char *)v127,
           v332);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v341, v129, v130);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v339, v131, v132);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v340, v133, v134);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v336, v135, v136);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v337, v137, v138);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v333, v139, v140);
  return v128;
}

```

## disassembly

```asm
0x18007e920  push    rbx
0x18007e922  push    rsi
0x18007e923  push    rdi
0x18007e924  push    r12
0x18007e926  push    r13
0x18007e928  push    r14
0x18007e92a  push    r15
0x18007e92c  sub     rsp, 180h
0x18007e933  mov     rax, cs:__security_cookie
0x18007e93a  xor     rax, rsp
0x18007e93d  mov     [rsp+1B8h+var_48], rax
0x18007e945  mov     dword ptr [rsp+1B8h+var_178], r8d
0x18007e94a  mov     rsi, rdx
0x18007e94d  mov     [rsp+1B8h+var_108], rdx
0x18007e955  mov     rdi, rcx
0x18007e958  lea     rax, WPP_GLOBAL_Control
0x18007e95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e966  lea     r14, WPP_426275660baf32778194b91bb4cd93ce_Traceguids
0x18007e96d  cmp     rcx, rax
0x18007e970  jz      short loc_18007E989
0x18007e972  test    byte ptr [rcx+1Ch], 40h
0x18007e976  jz      short loc_18007E989
0x18007e978  mov     edx, 2Dh ; '-'
0x18007e97d  mov     r8, r14
0x18007e980  mov     rcx, [rcx+10h]
0x18007e984  call    WPP_SF_
0x18007e989  xor     r12d, r12d
0x18007e98c  mov     [rsp+1B8h+var_134], r12d
0x18007e994  mov     rax, [rdi]
0x18007e997  lea     rdx, [rsp+1B8h+var_134]
0x18007e99f  mov     rcx, rdi
0x18007e9a2  mov     rax, [rax+0B0h]
0x18007e9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e9ae  mov     ebx, eax
0x18007e9b0  test    eax, eax
0x18007e9b2  jns     short loc_18007E9D7
0x18007e9b4  mov     rcx, [rsp+1B8h]; this
0x18007e9bc  mov     r9d, eax; char *
0x18007e9bf  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007e9c6  mov     edx, 1E9h; void *
0x18007e9cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e9d0  mov     eax, ebx
0x18007e9d2  jmp     loc_18007FE9C
0x18007e9d7  mov     [rsp+1B8h+var_180], 4
0x18007e9df  mov     [rsp+1B8h+var_188], r12
0x18007e9e4  mov     rax, [rdi]
0x18007e9e7  lea     rdx, [rsp+1B8h+var_180]
0x18007e9ec  mov     rcx, rdi
0x18007e9ef  mov     rax, [rax+30h]
0x18007e9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e9f8  mov     ebx, eax
0x18007e9fa  test    eax, eax
0x18007e9fc  jns     short loc_18007EA2C
0x18007e9fe  mov     rcx, [rsp+1B8h]; this
0x18007ea06  mov     r9d, eax; char *
0x18007ea09  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ea10  mov     edx, 1EDh; void *
0x18007ea15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ea1a  nop
0x18007ea1b  lea     rcx, [rsp+1B8h+var_188]
0x18007ea20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ea25  mov     eax, ebx
0x18007ea27  jmp     loc_18007FE9C
0x18007ea2c  mov     rax, [rdi]
0x18007ea2f  mov     rbx, [rax+40h]
0x18007ea33  lea     rcx, [rsp+1B8h+var_188]
0x18007ea38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ea3d  lea     rdx, [rsp+1B8h+var_188]
0x18007ea42  mov     rcx, rdi
0x18007ea45  mov     rax, rbx
0x18007ea48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea4d  mov     ebx, eax
0x18007ea4f  test    eax, eax
0x18007ea51  jns     short loc_18007EA81
0x18007ea53  mov     rcx, [rsp+1B8h]; this
0x18007ea5b  mov     r9d, eax; char *
0x18007ea5e  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ea65  mov     edx, 1EEh; void *
0x18007ea6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ea6f  nop
0x18007ea70  lea     rcx, [rsp+1B8h+var_188]
0x18007ea75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ea7a  mov     eax, ebx
0x18007ea7c  jmp     loc_18007FE9C
0x18007ea81  mov     r13d, 1
0x18007ea87  cmp     [rsp+1B8h+var_134], r13d
0x18007ea8f  jz      short loc_18007EA9E
0x18007ea91  cmp     [rsp+1B8h+var_134], 4
0x18007ea99  mov     bl, r12b
0x18007ea9c  jnz     short loc_18007EAA1
0x18007ea9e  mov     bl, r13b
0x18007eaa1  mov     edx, [rsp+1B8h+var_180]
0x18007eaa5  mov     rcx, rsi
0x18007eaa8  call    ?_GetDhcpEnabled@CategoryBase@Internal@UX@Networking@Windows@@CA_NAEBU_GUID@@W4IpFamily@345@@Z; Windows::Networking::UX::Internal::CategoryBase::_GetDhcpEnabled(_GUID const &,Windows::Networking::UX::IpFamily)
0x18007eaad  cmp     bl, al
0x18007eaaf  jnz     short loc_18007EABB
0x18007eab1  mov     [rsp+1B8h+var_130], r12d
0x18007eab9  jmp     short loc_18007EAE7
0x18007eabb  test    al, al
0x18007eabd  jz      short loc_18007EAD7
0x18007eabf  test    bl, bl
0x18007eac1  jnz     loc_18007FE75
0x18007eac7  mov     r15d, 2
0x18007eacd  mov     [rsp+1B8h+var_130], r15d
0x18007ead5  jmp     short loc_18007EAED
0x18007ead7  test    bl, bl
0x18007ead9  jz      loc_18007FE75
0x18007eadf  mov     [rsp+1B8h+var_130], r13d
0x18007eae7  mov     r15d, 2
0x18007eaed  mov     [rsp+1B8h+var_128], r12d
0x18007eaf5  mov     rcx, [rsp+1B8h+var_188]
0x18007eafa  test    rcx, rcx
0x18007eafd  jz      short loc_18007EB47
0x18007eaff  mov     rax, [rcx]
0x18007eb02  lea     rdx, [rsp+1B8h+var_128]
0x18007eb0a  mov     rax, [rax+38h]
0x18007eb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb13  mov     ebx, eax
0x18007eb15  test    eax, eax
0x18007eb17  jns     short loc_18007EB47
0x18007eb19  mov     rcx, [rsp+1B8h]; this
0x18007eb21  mov     r9d, eax; char *
0x18007eb24  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007eb2b  mov     edx, 1F5h; void *
0x18007eb30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eb35  nop
0x18007eb36  lea     rcx, [rsp+1B8h+var_188]
0x18007eb3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007eb40  mov     eax, ebx
0x18007eb42  jmp     loc_18007FE9C
0x18007eb47  mov     [rsp+1B8h+var_168], r12
0x18007eb4c  mov     rax, [rdi]
0x18007eb4f  mov     rbx, [rax+48h]
0x18007eb53  lea     rcx, [rsp+1B8h+var_168]
0x18007eb58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007eb5d  lea     rdx, [rsp+1B8h+var_168]
0x18007eb62  mov     rcx, rdi
0x18007eb65  mov     rax, rbx
0x18007eb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb6d  mov     ebx, eax
0x18007eb6f  test    eax, eax
0x18007eb71  jns     short loc_18007EBAC
0x18007eb73  mov     rcx, [rsp+1B8h]; this
0x18007eb7b  mov     r9d, eax; char *
0x18007eb7e  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007eb85  mov     edx, 1FAh; void *
0x18007eb8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eb8f  nop
0x18007eb90  lea     rcx, [rsp+1B8h+var_168]
0x18007eb95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007eb9a  nop
0x18007eb9b  lea     rcx, [rsp+1B8h+var_188]
0x18007eba0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007eba5  mov     eax, ebx
0x18007eba7  jmp     loc_18007FE9C
0x18007ebac  mov     [rsp+1B8h+var_170], r12
0x18007ebb1  mov     rax, [rdi]
0x18007ebb4  mov     rbx, [rax+50h]
0x18007ebb8  lea     rcx, [rsp+1B8h+var_170]
0x18007ebbd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ebc2  lea     rdx, [rsp+1B8h+var_170]
0x18007ebc7  mov     rcx, rdi
0x18007ebca  mov     rax, rbx
0x18007ebcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebd2  mov     ebx, eax
0x18007ebd4  test    eax, eax
0x18007ebd6  jns     short loc_18007EC1C
0x18007ebd8  mov     rcx, [rsp+1B8h]; this
0x18007ebe0  mov     r9d, eax; char *
0x18007ebe3  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ebea  mov     edx, 1FDh; void *
0x18007ebef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ebf4  nop
0x18007ebf5  lea     rcx, [rsp+1B8h+var_170]
0x18007ebfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ebff  nop
0x18007ec00  lea     rcx, [rsp+1B8h+var_168]
0x18007ec05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ec0a  nop
0x18007ec0b  lea     rcx, [rsp+1B8h+var_188]
0x18007ec10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ec15  mov     eax, ebx
0x18007ec17  jmp     loc_18007FE9C
0x18007ec1c  mov     [rsp+1B8h+var_124], r12d
0x18007ec24  mov     rcx, [rsp+1B8h+var_170]
0x18007ec29  test    rcx, rcx
0x18007ec2c  jz      short loc_18007EC8C
0x18007ec2e  mov     rax, [rcx]
0x18007ec31  lea     rdx, [rsp+1B8h+var_124]
0x18007ec39  mov     rax, [rax+38h]
0x18007ec3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec42  mov     ebx, eax
0x18007ec44  test    eax, eax
0x18007ec46  jns     short loc_18007EC8C
0x18007ec48  mov     rcx, [rsp+1B8h]; this
0x18007ec50  mov     r9d, eax; char *
0x18007ec53  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ec5a  mov     edx, 202h; void *
0x18007ec5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ec64  nop
0x18007ec65  lea     rcx, [rsp+1B8h+var_170]
0x18007ec6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ec6f  nop
0x18007ec70  lea     rcx, [rsp+1B8h+var_168]
0x18007ec75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ec7a  nop
0x18007ec7b  lea     rcx, [rsp+1B8h+var_188]
0x18007ec80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ec85  mov     eax, ebx
0x18007ec87  jmp     loc_18007FE9C
0x18007ec8c  mov     [rsp+1B8h+var_150], r12
0x18007ec91  mov     [rsp+1B8h+var_158], r12
0x18007ec96  mov     rax, [rdi]
0x18007ec99  mov     rbx, [rax+58h]
0x18007ec9d  lea     rcx, [rsp+1B8h+var_150]
0x18007eca2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007eca7  lea     rdx, [rsp+1B8h+var_150]
0x18007ecac  mov     rcx, rdi
0x18007ecaf  mov     rax, rbx
0x18007ecb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ecb7  mov     ebx, eax
0x18007ecb9  test    eax, eax
0x18007ecbb  jns     short loc_18007ED17
0x18007ecbd  mov     rcx, [rsp+1B8h]; this
0x18007ecc5  mov     r9d, eax; char *
0x18007ecc8  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007eccf  mov     edx, 208h; void *
0x18007ecd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ecd9  nop
0x18007ecda  lea     rcx, [rsp+1B8h+var_158]
0x18007ecdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ece4  nop
0x18007ece5  lea     rcx, [rsp+1B8h+var_150]
0x18007ecea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ecef  nop
0x18007ecf0  lea     rcx, [rsp+1B8h+var_170]
0x18007ecf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ecfa  nop
0x18007ecfb  lea     rcx, [rsp+1B8h+var_168]
0x18007ed00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed05  nop
0x18007ed06  lea     rcx, [rsp+1B8h+var_188]
0x18007ed0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed10  mov     eax, ebx
0x18007ed12  jmp     loc_18007FE9C
0x18007ed17  mov     rax, [rdi]
0x18007ed1a  mov     rbx, [rax+60h]
0x18007ed1e  lea     rcx, [rsp+1B8h+var_158]
0x18007ed23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed28  lea     rdx, [rsp+1B8h+var_158]
0x18007ed2d  mov     rcx, rdi
0x18007ed30  mov     rax, rbx
0x18007ed33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed38  mov     ebx, eax
0x18007ed3a  test    eax, eax
0x18007ed3c  jns     short loc_18007ED98
0x18007ed3e  mov     rcx, [rsp+1B8h]; this
0x18007ed46  mov     r9d, eax; char *
0x18007ed49  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ed50  mov     edx, 209h; void *
0x18007ed55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ed5a  nop
0x18007ed5b  lea     rcx, [rsp+1B8h+var_158]
0x18007ed60  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed65  nop
0x18007ed66  lea     rcx, [rsp+1B8h+var_150]
0x18007ed6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed70  nop
0x18007ed71  lea     rcx, [rsp+1B8h+var_170]
0x18007ed76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed7b  nop
0x18007ed7c  lea     rcx, [rsp+1B8h+var_168]
0x18007ed81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed86  nop
0x18007ed87  lea     rcx, [rsp+1B8h+var_188]
0x18007ed8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ed91  mov     eax, ebx
0x18007ed93  jmp     loc_18007FE9C
0x18007ed98  mov     [rsp+1B8h+var_12C], r12d
0x18007eda0  mov     rcx, [rsp+1B8h+var_158]
0x18007eda5  test    rcx, rcx
0x18007eda8  jz      short loc_18007EE1E
0x18007edaa  mov     rax, [rcx]
0x18007edad  lea     rdx, [rsp+1B8h+var_12C]
0x18007edb5  mov     rax, [rax+38h]
0x18007edb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007edbe  mov     ebx, eax
0x18007edc0  test    eax, eax
0x18007edc2  jns     short loc_18007EE1E
0x18007edc4  mov     rcx, [rsp+1B8h]; this
0x18007edcc  mov     r9d, eax; char *
0x18007edcf  lea     r8, aOnecoreuapNetU_21; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007edd6  mov     edx, 20Eh; void *
0x18007eddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ede0  nop
0x18007ede1  lea     rcx, [rsp+1B8h+var_158]
0x18007ede6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007edeb  nop
0x18007edec  lea     rcx, [rsp+1B8h+var_150]
0x18007edf1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
