# KerbGetKdcRegParams(HKEY__ *,int)

- ea: `0x180038244`
- end: `0x1800391dc`
- name: `?KerbGetKdcRegParams@@YAXPEAUHKEY__@@H@Z`
- size: `3992`
- prototype: `void __fastcall(HKEY, int)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800394b4`
- `0x180040220`

## callees

- `0x1800010f0`
- `0x180002ad0`
- `0x1800038e4`
- `0x1800050ac`
- `0x1800058a8`
- `0x1800101c4`
- `0x1800101ec`
- `0x1800320c0`
- `0x1800347d8`
- `0x180034dac`
- `0x18003529c`
- `0x180035570`
- `0x180036bf0`
- `0x180036f28`
- `0x180037464`
- `0x180038244`
- `0x1800391e4`
- `0x18003a1bc`
- `0x18003a570`
- `0x18004009c`
- `0x18004026c`
- `0x18005a060`
- `0x18005a090`
- `0x18007352c`
- `0x180077b78`
- `0x180078408`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038fda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800390b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038fda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800390b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038bdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038bdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038bf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038bf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038f32`

## string_xrefs

- `0x1800384ab`: `ServiceIterationCount`
- `0x1800385b9`: `UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors`
- `0x180038737`: `FsoCacheTimeout`
- `0x180038795`: `A2DFProtocolTransition`
- `0x180038967`: `RequestCompoundId`
- `0x180038a04`: `PKInitHashAlgorithmConfigurationEnabled`
- `0x180038afe`: `CertificateBackdatingCompensation`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall KerbGetKdcRegParams(HKEY a1)
{
  unsigned int v1; // r15d
  unsigned int v2; // r12d
  unsigned int v3; // r13d
  LSTATUS v4; // eax
  HKEY v5; // rcx
  DWORD v6; // r8d
  HKEY v7; // rdx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ecx
  int v15; // eax
  LSTATUS v16; // eax
  unsigned int v17; // ecx
  BYTE *v18; // rax
  unsigned int v19; // esi
  unsigned int v20; // esi
  void *v21; // r14
  int v22; // r15d
  unsigned int v23; // ecx
  __int64 v24; // rax
  unsigned int v25; // [rsp+30h] [rbp-738h] BYREF
  DWORD Type; // [rsp+34h] [rbp-734h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-730h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-728h] BYREF
  RTL_SRWLOCK *v29; // [rsp+48h] [rbp-720h] BYREF
  LPBYTE lpData[2]; // [rsp+50h] [rbp-718h] BYREF
  int v31; // [rsp+60h] [rbp-708h] BYREF
  unsigned int v32; // [rsp+64h] [rbp-704h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-700h] BYREF
  unsigned int v34; // [rsp+6Ch] [rbp-6FCh] BYREF
  unsigned int v35; // [rsp+70h] [rbp-6F8h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-6F4h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-6F0h] BYREF
  unsigned int v38; // [rsp+7Ch] [rbp-6ECh] BYREF
  __int128 v39; // [rsp+80h] [rbp-6E8h] BYREF
  __int128 v40; // [rsp+90h] [rbp-6D8h] BYREF
  RTL_SRWLOCK *v41[2]; // [rsp+A0h] [rbp-6C8h] BYREF
  _QWORD v42[91]; // [rsp+B0h] [rbp-6B8h] BYREF
  int v43; // [rsp+388h] [rbp-3E0h]
  int v44; // [rsp+38Ch] [rbp-3DCh]
  const wchar_t *v45; // [rsp+390h] [rbp-3D8h]
  unsigned int *v46; // [rsp+398h] [rbp-3D0h]
  __int64 v47; // [rsp+3A0h] [rbp-3C8h]
  int v48; // [rsp+3A8h] [rbp-3C0h]
  int v49; // [rsp+3ACh] [rbp-3BCh]
  const wchar_t *v50; // [rsp+3B0h] [rbp-3B8h]
  unsigned int *v51; // [rsp+3B8h] [rbp-3B0h]
  __int64 v52; // [rsp+3C0h] [rbp-3A8h]
  __int64 v53; // [rsp+3C8h] [rbp-3A0h]
  const wchar_t *v54; // [rsp+3D0h] [rbp-398h]
  unsigned int *v55; // [rsp+3D8h] [rbp-390h]
  __int64 v56; // [rsp+3E0h] [rbp-388h]
  __int64 v57; // [rsp+3E8h] [rbp-380h]
  const wchar_t *v58; // [rsp+3F0h] [rbp-378h]
  unsigned int *v59; // [rsp+3F8h] [rbp-370h]
  __int64 v60; // [rsp+400h] [rbp-368h]
  __int64 v61; // [rsp+408h] [rbp-360h]
  const wchar_t *v62; // [rsp+410h] [rbp-358h]
  unsigned int *v63; // [rsp+418h] [rbp-350h]
  __int64 v64; // [rsp+420h] [rbp-348h]
  int v65; // [rsp+428h] [rbp-340h]
  int v66; // [rsp+42Ch] [rbp-33Ch]
  const wchar_t *v67; // [rsp+430h] [rbp-338h]
  unsigned int *v68; // [rsp+438h] [rbp-330h]
  __int64 v69; // [rsp+440h] [rbp-328h]
  int v70; // [rsp+448h] [rbp-320h]
  int v71; // [rsp+44Ch] [rbp-31Ch]
  const wchar_t *v72; // [rsp+450h] [rbp-318h]
  unsigned int *v73; // [rsp+458h] [rbp-310h]
  __int64 v74; // [rsp+460h] [rbp-308h]
  int v75; // [rsp+468h] [rbp-300h]
  int v76; // [rsp+46Ch] [rbp-2FCh]
  const wchar_t *v77; // [rsp+470h] [rbp-2F8h]
  unsigned int *v78; // [rsp+478h] [rbp-2F0h]
  __int64 v79; // [rsp+480h] [rbp-2E8h]
  int v80; // [rsp+488h] [rbp-2E0h]
  int v81; // [rsp+48Ch] [rbp-2DCh]
  const wchar_t *v82; // [rsp+490h] [rbp-2D8h]
  unsigned int *v83; // [rsp+498h] [rbp-2D0h]
  __int64 v84; // [rsp+4A0h] [rbp-2C8h]
  int v85; // [rsp+4A8h] [rbp-2C0h]
  int v86; // [rsp+4ACh] [rbp-2BCh]
  const wchar_t *v87; // [rsp+4B0h] [rbp-2B8h]
  unsigned int *v88; // [rsp+4B8h] [rbp-2B0h]
  __int64 v89; // [rsp+4C0h] [rbp-2A8h]
  int v90; // [rsp+4C8h] [rbp-2A0h]
  int v91; // [rsp+4CCh] [rbp-29Ch]
  const wchar_t *v92; // [rsp+4D0h] [rbp-298h]
  unsigned int *v93; // [rsp+4D8h] [rbp-290h]
  __int64 v94; // [rsp+4E0h] [rbp-288h]
  int v95; // [rsp+4E8h] [rbp-280h]
  int v96; // [rsp+4ECh] [rbp-27Ch]
  const wchar_t *v97; // [rsp+4F0h] [rbp-278h]
  unsigned int *v98; // [rsp+4F8h] [rbp-270h]
  __int64 v99; // [rsp+500h] [rbp-268h]
  int v100; // [rsp+508h] [rbp-260h]
  int v101; // [rsp+50Ch] [rbp-25Ch]
  const wchar_t *v102; // [rsp+510h] [rbp-258h]
  unsigned int *v103; // [rsp+518h] [rbp-250h]
  __int64 v104; // [rsp+520h] [rbp-248h]
  int v105; // [rsp+528h] [rbp-240h]
  int v106; // [rsp+52Ch] [rbp-23Ch]
  const wchar_t *v107; // [rsp+530h] [rbp-238h]
  unsigned int *v108; // [rsp+538h] [rbp-230h]
  __int64 v109; // [rsp+540h] [rbp-228h]
  int v110; // [rsp+548h] [rbp-220h]
  int v111; // [rsp+54Ch] [rbp-21Ch]
  const wchar_t *v112; // [rsp+550h] [rbp-218h]
  unsigned int *v113; // [rsp+558h] [rbp-210h]
  __int64 v114; // [rsp+560h] [rbp-208h]
  int v115; // [rsp+568h] [rbp-200h]
  int v116; // [rsp+56Ch] [rbp-1FCh]
  const wchar_t *v117; // [rsp+570h] [rbp-1F8h]
  int *v118; // [rsp+578h] [rbp-1F0h]
  __int64 v119; // [rsp+580h] [rbp-1E8h]
  int v120; // [rsp+588h] [rbp-1E0h]
  int v121; // [rsp+58Ch] [rbp-1DCh]
  const wchar_t *v122; // [rsp+590h] [rbp-1D8h]
  unsigned int *v123; // [rsp+598h] [rbp-1D0h]
  __int64 v124; // [rsp+5A0h] [rbp-1C8h]
  int v125; // [rsp+5A8h] [rbp-1C0h]
  int v126; // [rsp+5ACh] [rbp-1BCh]
  const wchar_t *v127; // [rsp+5B0h] [rbp-1B8h]
  unsigned int *v128; // [rsp+5B8h] [rbp-1B0h]
  __int64 v129; // [rsp+5C0h] [rbp-1A8h]
  int v130; // [rsp+5C8h] [rbp-1A0h]
  int v131; // [rsp+5CCh] [rbp-19Ch]
  const wchar_t *v132; // [rsp+5D0h] [rbp-198h]
  unsigned int *v133; // [rsp+5D8h] [rbp-190h]
  __int64 v134; // [rsp+5E0h] [rbp-188h]
  int v135; // [rsp+5E8h] [rbp-180h]
  int v136; // [rsp+5ECh] [rbp-17Ch]
  const wchar_t *v137; // [rsp+5F0h] [rbp-178h]
  unsigned int *v138; // [rsp+5F8h] [rbp-170h]
  __int64 v139; // [rsp+600h] [rbp-168h]
  int v140; // [rsp+608h] [rbp-160h]
  int v141; // [rsp+60Ch] [rbp-15Ch]
  const wchar_t *v142; // [rsp+610h] [rbp-158h]
  unsigned int *v143; // [rsp+618h] [rbp-150h]
  __int64 v144; // [rsp+620h] [rbp-148h]
  __int64 v145; // [rsp+628h] [rbp-140h]
  const wchar_t *v146; // [rsp+630h] [rbp-138h]
  unsigned int *v147; // [rsp+638h] [rbp-130h]
  __int64 v148; // [rsp+640h] [rbp-128h]
  __int64 v149; // [rsp+648h] [rbp-120h]
  const wchar_t *v150; // [rsp+650h] [rbp-118h]
  unsigned int *v151; // [rsp+658h] [rbp-110h]
  __int64 v152; // [rsp+660h] [rbp-108h]
  int v153; // [rsp+668h] [rbp-100h]
  int v154; // [rsp+66Ch] [rbp-FCh]
  const wchar_t *v155; // [rsp+670h] [rbp-F8h]
  unsigned int *v156; // [rsp+678h] [rbp-F0h]
  __int64 v157; // [rsp+680h] [rbp-E8h]
  __int64 v158; // [rsp+688h] [rbp-E0h]
  _BYTE v159[16]; // [rsp+690h] [rbp-D8h] BYREF
  _BYTE v160[16]; // [rsp+6A0h] [rbp-C8h] BYREF
  __int64 v161; // [rsp+6B0h] [rbp-B8h]
  const std::exception *v162; // [rsp+6B8h] [rbp-B0h] BYREF
  _QWORD v163[2]; // [rsp+6C0h] [rbp-A8h] BYREF
  int v164; // [rsp+6D0h] [rbp-98h]
  int v165; // [rsp+6D4h] [rbp-94h]
  const char *v166; // [rsp+6D8h] [rbp-90h]
  __int64 v167; // [rsp+6E0h] [rbp-88h]
  __int64 v168; // [rsp+6E8h] [rbp-80h]
  const char *v169; // [rsp+6F0h] [rbp-78h]
  __int64 v170; // [rsp+6F8h] [rbp-70h]
  unsigned int *v171; // [rsp+700h] [rbp-68h]
  __int64 v172; // [rsp+708h] [rbp-60h]
  __int64 v173; // [rsp+710h] [rbp-58h]
  __int64 v174; // [rsp+718h] [rbp-50h]

  v37 = 120;
  Type = 3;
  v38 = 0;
  *(_OWORD *)lpData = 0;
  hKey = 0;
  wil::AcquireSRWLockExclusive(v41, (RTL_SRWLOCK *)&qword_1800B4348);
  v36 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v25 = 0;
  v1 = 1;
  v2 = 1;
  v3 = 1;
  v42[0] = L"KdcUseClientAddresses";
  v42[1] = &KdcUseClientAddresses;
  v42[2] = 0;
  v42[3] = 1;
  v42[4] = L"KdcUseClientNetBIOSAddresses";
  v42[5] = &KdcUseClientNetBIOSAddresses;
  v42[6] = 0;
  v42[7] = 1;
  v42[8] = L"KdcDontCheckAddresses";
  v42[9] = &KdcDontCheckAddresses;
  v42[10] = 1;
  v42[11] = 1;
  v42[12] = L"NewConnectionTimeout";
  v42[13] = &KdcNewConnectionTimeout;
  v42[14] = 10;
  v42[15] = 1;
  v42[16] = L"ExistingConnectionTimeout";
  v42[17] = &KdcExistingConnectionTimeout;
  v42[18] = 50;
  v42[19] = 1;
  v42[20] = L"MaxDatagramReplySize";
  v42[21] = &KdcGlobalMaxDatagramReplySize;
  v42[22] = 1465;
  v42[23] = 0;
  v42[24] = L"KdcExtraLogLevel";
  v42[25] = &KdcExtraLogLevel;
  v42[26] = 255;
  v42[27] = 1;
  v42[28] = L"KdcControlLevel";
  v42[29] = &KDCInfoLevel;
  v42[30] = 0;
  v42[31] = 1;
  v42[32] = L"KdcIssueForwardedTickets";
  v42[33] = &KdcIssueForwardedTickets;
  v42[34] = 1;
  v42[35] = 1;
  v42[36] = L"IterationCount";
  v42[37] = &KdcGlobalIterationCount;
  v42[38] = 4096;
  v42[39] = 1;
  v42[40] = L"ServiceIterationCount";
  v42[41] = &KdcGlobalServiceIterationCount;
  v42[42] = 4096;
  v42[43] = 1;
  v42[44] = L"AllowedReplicationLatency";
  v42[45] = &KdcGlobalDomainPasswordReplSkew;
  v42[46] = 60;
  v42[47] = 1;
  v42[48] = L"CRLTimeoutPeriod";
  v42[49] = &KdcGlobalCRLRetrievalTimeout;
  v42[50] = 0;
  v42[51] = 1;
  v42[52] = L"CRLTimeoutPeriod";
  v42[53] = &KdcGlobalCRLRetrievalTimeout;
  v42[54] = 0;
  v42[55] = 1;
  v42[56] = L"UseSubjectAltName";
  v42[57] = &KdcGlobalUseSubjectAltName;
  v42[58] = 1;
  v42[59] = 1;
  v42[60] = L"SCLogonEKUNotRequired";
  v42[61] = &KdcGlobalSCLogonEKUNotRequired;
  v42[62] = 1;
  v42[63] = 1;
  v42[64] = L"UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors";
  v42[65] = &KdcGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors;
  v42[66] = 0;
  v42[67] = 1;
  v42[68] = L"DHKeyLifeTime";
  v42[69] = &v37;
  v42[70] = 120;
  v42[71] = 1;
  v42[72] = L"UseWellknownDHDomainParametersOnly";
  v42[73] = &KdcGlobalUseWellknownDHDomainParametersOnly;
  v42[74] = 1;
  v42[75] = 1;
  v42[76] = L"ModpDHOnly";
  v42[77] = &KdcGlobalModpDHOnly;
  v42[78] = 0;
  v42[79] = 1;
  v42[80] = L"LeafOnly";
  v42[81] = &KdcGlobalSendOnlyLeafCertificate;
  v42[82] = 1;
  v42[83] = 1;
  v42[84] = L"DisableNamespaceFiltering";
  v42[85] = &KdcGlobalDisableNamespaceFiltering;
  v42[86] = 0;
  v42[87] = 1;
  v42[88] = L"EmitLILI";
  v42[89] = &KdcGlobalEmitLILI;
  v42[90] = 0;
  v43 = 1;
  v44 = 1;
  v45 = L"UseForestSearch";
  v46 = &KdcUseForestSearchOrder;
  v47 = 0;
  v48 = 1;
  v49 = 1;
  v50 = L"FsoCacheTimeout";
  v51 = &v38;
  v52 = 30;
  v53 = 1;
  v54 = L"EnableA2DFCheck";
  v55 = &KdcGlobalEnableA2DFCheck;
  v56 = 1;
  v57 = 1;
  v58 = L"A2DFProtocolTransition";
  v59 = &KdcGlobalA2DFProtocolTransition;
  v60 = 1;
  v61 = 1;
  v62 = L"NonForwardableDelegation";
  v63 = &KdcGlobalNonForwardableDelegation;
  v64 = 0;
  v65 = 1;
  v66 = 1;
  v67 = L"CbacAndArmorLevel";
  v68 = &KdcGlobalCbacAndArmorLevel;
  v69 = 0;
  v70 = 1;
  v71 = 1;
  v72 = L"DomainFastLevel";
  v73 = &KdcGlobalDomainFastLevel;
  v74 = 0;
  v75 = 1;
  v76 = 1;
  v77 = L"DomainClaimsLevel";
  v78 = &KdcGlobalDomainClaimsLevel;
  v79 = 0;
  v80 = 1;
  v81 = 1;
  v82 = L"AdvertiseFast";
  v83 = &KdcGlobalAdvertiseFast;
  v84 = 0;
  v85 = 1;
  v86 = 1;
  v87 = L"DisableResourceGroupsFields";
  v88 = &KdcGlobalDisableResourceGroupsFields;
  v89 = 0;
  v90 = 1;
  v91 = 1;
  v92 = L"TicketSizeThreshold";
  v93 = &KdcGlobalTicketSizeThreshold;
  v94 = 12000;
  v95 = 1;
  v96 = 1;
  v97 = L"ChainWithIssuancePolicyOIDs";
  v98 = &KdcGlobalChainWithIssuancePolicyOIDs;
  v99 = 0;
  v100 = 1;
  v101 = 1;
  v102 = L"RequestCompoundId";
  v103 = &KdcGlobalRequestCompoundId;
  v104 = 0;
  v105 = 1;
  v106 = 1;
  v107 = L"PKINITFreshness";
  v108 = &KdcGlobalRequireFreshness;
  v109 = 0;
  v110 = 1;
  v111 = 1;
  v112 = L"PKINITEncryptionMode";
  v113 = &v36;
  v114 = 2;
  v115 = 1;
  v116 = 1;
  v117 = L"PKInitHashAlgorithmConfigurationEnabled";
  v118 = &v31;
  v119 = 0;
  v120 = 1;
  v121 = 1;
  v122 = L"PKINITSHA1";
  v123 = &v32;
  v124 = 1;
  v125 = 1;
  v126 = 1;
  v127 = L"PKINITSHA256";
  v128 = &v33;
  v129 = 1;
  v130 = 1;
  v131 = 1;
  v132 = L"PKINITSHA384";
  v133 = &v34;
  v134 = 1;
  v135 = 1;
  v136 = 1;
  v137 = L"PKINITSHA512";
  v138 = &v35;
  v139 = 1;
  v140 = 1;
  v141 = 1;
  v142 = L"CertificateBackdatingCompensation";
  v143 = &KdcGlobalCertBackdatingCompensationSeconds;
  v144 = 600;
  v145 = 1;
  v146 = L"StrongCertificateBindingEnforcement";
  v147 = &v25;
  v148 = 2;
  v149 = 1;
  v150 = L"UseStrongNameMatches";
  v151 = &KdcUseStrongNameMatches;
  v152 = 0;
  v153 = 1;
  v154 = 1;
  v155 = L"EnforceRev3KeyStructure";
  v156 = &KdcEnforceRev3KeyStructure;
  v157 = 0;
  v158 = 1;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kdc\\Parameters",
         0,
         0x20019u,
         &hKey);
  v7 = hKey;
  if ( v4 && hKey )
  {
    RegCloseKey(hKey);
    v7 = 0;
    hKey = 0;
  }
  GetRegistryDwords(v5, v7, v6, (struct _KDC_REG_PARAMETER *)v42);
  if ( v31 )
  {
    v1 = KerbPkinitHashAlgStateDwordToEnum(v32);
    v2 = KerbPkinitHashAlgStateDwordToEnum(v33);
    v3 = KerbPkinitHashAlgStateDwordToEnum(v34);
    v8 = KerbPkinitHashAlgStateDwordToEnum(v35);
  }
  else
  {
    v8 = 1;
  }
  v163[0] = "2.16.840.1.101.3.4.2.3";
  v163[1] = 22;
  v164 = v8;
  v165 = 3;
  v166 = "2.16.840.1.101.3.4.2.2";
  v167 = 22;
  v168 = v3 | 0x300000000LL;
  v169 = "2.16.840.1.101.3.4.2.1";
  v170 = 22;
  v171 = (unsigned int *)(v2 | 0x300000000LL);
  v172 = (__int64)"1.3.14.3.2.26";
  v173 = 13;
  v174 = v1 | 0x300000000LL;
  *(_QWORD *)&v39 = 0;
  utl::_SharedAlloc<KerbDigestAlgorithmPolicy,utl::allocator<int>,0>::_Create<utl::shared_ptr<KerbDigestAlgorithmPolicy>,>(
    (__int64 *)&v39,
    &v40);
  utl::_SharedAlloc<KerbDigestAlgorithmPolicy,utl::allocator<int>,0>::~_SharedAlloc<KerbDigestAlgorithmPolicy,utl::allocator<int>,0>(&v39);
  v39 = v40;
  utl::atomic<utl::shared_ptr<KerbDigestAlgorithmPolicy const>>::store(v9, &v39);
  KdcConfigureHashAlgorithmPolicy(v10, (struct PkinitAddAlgorithmParam *)v163);
  v11 = v36;
  if ( v36 > 2 )
    v11 = 2;
  KdcGlobalPkinitEncryptionMode = v11;
  if ( KdcGlobalTicketSizeThreshold < 0xFA0 )
    KdcGlobalTicketSizeThreshold = 4000;
  KdcGetCbacAndArmorPolicy();
  KerbGetKdcSearchForests(hKey);
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrongNameMatchPolicy>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_StrongNameMatchPolicy>::GetImpl'::`2'::impl,
    v12);
  if ( KdcUseStrongNameMatches )
  {
    std::map<std::wstring,std::vector<std::wstring>>::map<std::wstring,std::vector<std::wstring>>(v159);
    std::map<std::wstring,std::vector<std::wstring>>::map<std::wstring,std::vector<std::wstring>>(v160);
    v161 = 0;
    PreprocessStrongNameMatchPolicy(&v29, hKey, v159);
    if ( (int)v29 < 0 )
    {
      if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 0x40) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v13, KdcInvalidCertNameMatchPolicy, HIDWORD(v29));
    }
    else
    {
      wil::AcquireSRWLockExclusive(&v29, (RTL_SRWLOCK *)&qword_1800B2D30);
      try
      {
        std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::operator=(
          g_policyMaps,
          v159);
        std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::operator=(
          qword_1800B2D20,
          v160);
      }
      catch ( const std::exception *v162 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v24 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v162 + 8LL))(v162);
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v24);
        }
        std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear(g_policyMaps);
        std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear(qword_1800B2D20);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
    }
    KdcIssuerPolicyMaps::~KdcIssuerPolicyMaps((KdcIssuerPolicyMaps *)v159);
  }
  if ( (unsigned int)dword_1800B20C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800B20C0, 0x400000000000LL) )
  {
    *(_QWORD *)&v40 = 0x1000000;
    v27 = KdcUseStrongNameMatches;
    LODWORD(v29) = 0;
    *(_QWORD *)&v39 = 1;
    v173 = (__int64)&v40;
    v174 = 8;
    v171 = &v27;
    v172 = 4;
    v169 = (const char *)&v29;
    v170 = 4;
    v167 = (__int64)&v39;
    v168 = 8;
    tlgWriteAgg(v14, (unsigned int)&word_1800A5CA6, 0, 6, (__int64)v163);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( KdcGlobalMaxDatagramReplySize >= 0x10000 )
    KdcGlobalMaxDatagramReplySize = 0x10000;
  if ( !KdcGlobalIterationCount )
    KdcGlobalIterationCount = 1;
  if ( !KdcGlobalServiceIterationCount )
    KdcGlobalServiceIterationCount = 1;
  KdcGlobalAllowedDHKeyLifeTime.QuadPart = 600000000LL * v37;
  KerbFsoBindingCacheTimeout.QuadPart = 600000000LL * v38;
  KdcGlobalIgnoreClientPacRequests = 0;
  KdcGlobalNoExtraFieldsInUpnDnsInfo = 0;
  v15 = v25;
  if ( v25 > 2 )
  {
    v15 = 2;
    v25 = 2;
  }
  if ( !v15 )
  {
    v15 = 1;
    v25 = 1;
  }
  KdcGlobalEnforceStrongCertificateMapping = v15;
  v16 = RegQueryValueExW(0, L"DHDomainParameters", 0, &Type, lpData[1], (LPDWORD)lpData);
  if ( v16 == 2 )
  {
    if ( *((_QWORD *)&xmmword_1800B4250 + 1) )
    {
      MIDL_user_free(*((void **)&xmmword_1800B4250 + 1));
      v17 = (unsigned int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
      }
      KerbAddWellknownDomainParameters(v17, 0, 0);
    }
    xmmword_1800B4250 = 0;
  }
  else if ( !v16 )
  {
    v18 = (BYTE *)MIDL_user_allocate(LODWORD(lpData[0]));
    lpData[1] = v18;
    if ( v18 )
    {
      v19 = RegQueryValueExW(0, L"DHDomainParameters", 0, &Type, v18, (LPDWORD)lpData);
      if ( v19 )
      {
        if ( lpData[1] )
          MIDL_user_free(lpData[1]);
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v19);
        }
      }
      else if ( Type == 3 )
      {
        v20 = (unsigned int)lpData[0];
        v21 = (void *)*((_QWORD *)&xmmword_1800B4250 + 1);
        if ( (_DWORD)xmmword_1800B4250 != LODWORD(lpData[0])
          || (v22 = 0, memcmp_0(lpData[1], *((const void **)&xmmword_1800B4250 + 1), LODWORD(lpData[0]))) )
        {
          v22 = 1;
        }
        if ( v21 )
        {
          MIDL_user_free(v21);
          v20 = (unsigned int)lpData[0];
        }
        xmmword_1800B4250 = *(_OWORD *)lpData;
        if ( v22 )
        {
          v23 = (unsigned int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
            v20 = (unsigned int)lpData[0];
          }
          KerbAddWellknownDomainParameters(v23, lpData[1], v20);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v41);
}

```

## disassembly

```asm
0x180038244  push    rbx
0x180038246  push    rsi
0x180038247  push    rdi
0x180038248  push    r12
0x18003824a  push    r13
0x18003824c  push    r14
0x18003824e  push    r15
0x180038250  sub     rsp, 730h
0x180038257  mov     rax, cs:__security_cookie
0x18003825e  xor     rax, rsp
0x180038261  mov     [rsp+768h+var_48], rax
0x180038269  mov     esi, 78h ; 'x'
0x18003826e  mov     [rsp+768h+var_6F0], esi
0x180038272  lea     r14d, [rsi-75h]
0x180038276  mov     [rsp+768h+Type], r14d
0x18003827b  xor     ebx, ebx
0x18003827d  mov     [rsp+768h+var_6EC], ebx
0x180038281  xorps   xmm0, xmm0
0x180038284  movups  xmmword ptr [rsp+768h+lpData], xmm0
0x180038289  mov     [rsp+768h+hKey], rbx
0x18003828e  lea     rdx, qword_1800B4348
0x180038295  lea     rcx, [rsp+768h+var_6C8]
0x18003829d  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800382a2  nop
0x1800382a3  mov     [rsp+768h+var_6F4], ebx
0x1800382a7  mov     [rsp+768h+var_708], ebx
0x1800382ab  mov     [rsp+768h+var_704], ebx
0x1800382af  mov     [rsp+768h+var_700], ebx
0x1800382b3  mov     [rsp+768h+var_6FC], ebx
0x1800382b7  mov     [rsp+768h+var_6F8], ebx
0x1800382bb  mov     [rsp+768h+var_738], ebx
0x1800382bf  lea     edi, [rsi-77h]
0x1800382c2  mov     r15d, edi
0x1800382c5  mov     r12d, edi
0x1800382c8  mov     r13d, edi
0x1800382cb  lea     rax, aKdcuseclientad; "KdcUseClientAddresses"
0x1800382d2  mov     [rsp+768h+var_6B8], rax
0x1800382da  lea     rax, ?KdcUseClientAddresses@@3KA; ulong KdcUseClientAddresses
0x1800382e1  mov     [rsp+768h+var_6B0], rax
0x1800382e9  mov     [rsp+768h+var_6A8], rbx
0x1800382f1  mov     [rsp+768h+var_6A0], rdi
0x1800382f9  lea     rax, aKdcuseclientne; "KdcUseClientNetBIOSAddresses"
0x180038300  mov     [rsp+768h+var_698], rax
0x180038308  lea     rax, ?KdcUseClientNetBIOSAddresses@@3KA; ulong KdcUseClientNetBIOSAddresses
0x18003830f  mov     [rsp+768h+var_690], rax
0x180038317  mov     [rsp+768h+var_688], rbx
0x18003831f  mov     [rsp+768h+var_680], rdi
0x180038327  lea     rax, aKdcdontcheckad; "KdcDontCheckAddresses"
0x18003832e  mov     [rsp+768h+var_678], rax
0x180038336  lea     rax, ?KdcDontCheckAddresses@@3KA; ulong KdcDontCheckAddresses
0x18003833d  mov     [rsp+768h+var_670], rax
0x180038345  mov     [rsp+768h+var_668], rdi
0x18003834d  mov     [rsp+768h+var_660], rdi
0x180038355  lea     rax, aNewconnectiont; "NewConnectionTimeout"
0x18003835c  mov     [rsp+768h+var_658], rax
0x180038364  lea     rax, ?KdcNewConnectionTimeout@@3KA; ulong KdcNewConnectionTimeout
0x18003836b  mov     [rsp+768h+var_650], rax
0x180038373  mov     [rsp+768h+var_648], 0Ah
0x18003837f  mov     [rsp+768h+var_640], rdi
0x180038387  lea     rax, aExistingconnec; "ExistingConnectionTimeout"
0x18003838e  mov     [rsp+768h+var_638], rax
0x180038396  lea     rax, ?KdcExistingConnectionTimeout@@3KA; ulong KdcExistingConnectionTimeout
0x18003839d  mov     [rsp+768h+var_630], rax
0x1800383a5  mov     [rsp+768h+var_628], 32h ; '2'
0x1800383b1  mov     [rsp+768h+var_620], rdi
0x1800383b9  lea     rax, aMaxdatagramrep; "MaxDatagramReplySize"
0x1800383c0  mov     [rsp+768h+var_618], rax
0x1800383c8  lea     rax, ?KdcGlobalMaxDatagramReplySize@@3KA; ulong KdcGlobalMaxDatagramReplySize
0x1800383cf  mov     [rsp+768h+var_610], rax
0x1800383d7  mov     [rsp+768h+var_608], 5B9h
0x1800383e3  mov     [rsp+768h+var_600], rbx
0x1800383eb  lea     rax, aKdcextraloglev; "KdcExtraLogLevel"
0x1800383f2  mov     [rsp+768h+var_5F8], rax
0x1800383fa  lea     rax, ?KdcExtraLogLevel@@3KA; ulong KdcExtraLogLevel
0x180038401  mov     [rsp+768h+var_5F0], rax
0x180038409  mov     [rsp+768h+var_5E8], 0FFh
0x180038415  mov     [rsp+768h+var_5E0], rdi
0x18003841d  lea     rax, aKdccontrolleve; "KdcControlLevel"
0x180038424  mov     [rsp+768h+var_5D8], rax
0x18003842c  lea     rax, ?KDCInfoLevel@@3KA; ulong KDCInfoLevel
0x180038433  mov     [rsp+768h+var_5D0], rax
0x18003843b  mov     [rsp+768h+var_5C8], rbx
0x180038443  mov     [rsp+768h+var_5C0], rdi
0x18003844b  lea     rax, aKdcissueforwar; "KdcIssueForwardedTickets"
0x180038452  mov     [rsp+768h+var_5B8], rax
0x18003845a  lea     rax, ?KdcIssueForwardedTickets@@3KA; ulong KdcIssueForwardedTickets
0x180038461  mov     [rsp+768h+var_5B0], rax
0x180038469  mov     [rsp+768h+var_5A8], rdi
0x180038471  mov     [rsp+768h+var_5A0], rdi
0x180038479  lea     rax, aIterationcount; "IterationCount"
0x180038480  mov     [rsp+768h+var_598], rax
0x180038488  lea     rax, ?KdcGlobalIterationCount@@3KA; ulong KdcGlobalIterationCount
0x18003848f  mov     [rsp+768h+var_590], rax
0x180038497  mov     [rsp+768h+var_588], 1000h
0x1800384a3  mov     [rsp+768h+var_580], rdi
0x1800384ab  lea     rax, aServiceiterati; "ServiceIterationCount"
0x1800384b2  mov     [rsp+768h+var_578], rax
0x1800384ba  lea     rax, ?KdcGlobalServiceIterationCount@@3KA; ulong KdcGlobalServiceIterationCount
0x1800384c1  mov     [rsp+768h+var_570], rax
0x1800384c9  mov     [rsp+768h+var_568], 1000h
0x1800384d5  mov     [rsp+768h+var_560], rdi
0x1800384dd  lea     rax, aAllowedreplica; "AllowedReplicationLatency"
0x1800384e4  mov     [rsp+768h+var_558], rax
0x1800384ec  lea     rax, ?KdcGlobalDomainPasswordReplSkew@@3KA; ulong KdcGlobalDomainPasswordReplSkew
0x1800384f3  mov     [rsp+768h+var_550], rax
0x1800384fb  mov     [rsp+768h+var_548], 3Ch ; '<'
0x180038507  mov     [rsp+768h+var_540], rdi
0x18003850f  lea     rcx, aCrltimeoutperi; "CRLTimeoutPeriod"
0x180038516  mov     [rsp+768h+var_538], rcx
0x18003851e  lea     rax, ?KdcGlobalCRLRetrievalTimeout@@3KA; ulong KdcGlobalCRLRetrievalTimeout
0x180038525  mov     [rsp+768h+var_530], rax
0x18003852d  mov     [rsp+768h+var_528], rbx
0x180038535  mov     [rsp+768h+var_520], rdi
0x18003853d  mov     [rsp+768h+var_518], rcx
0x180038545  mov     [rsp+768h+var_510], rax
0x18003854d  mov     [rsp+768h+var_508], rbx
0x180038555  mov     [rsp+768h+var_500], rdi
0x18003855d  lea     rax, aUsesubjectaltn; "UseSubjectAltName"
0x180038564  mov     [rsp+768h+var_4F8], rax
0x18003856c  lea     rax, ?KdcGlobalUseSubjectAltName@@3KA; ulong KdcGlobalUseSubjectAltName
0x180038573  mov     [rsp+768h+var_4F0], rax
0x18003857b  mov     [rsp+768h+var_4E8], rdi
0x180038583  mov     [rsp+768h+var_4E0], rdi
0x18003858b  lea     rax, aSclogonekunotr; "SCLogonEKUNotRequired"
0x180038592  mov     [rsp+768h+var_4D8], rax
0x18003859a  lea     rax, ?KdcGlobalSCLogonEKUNotRequired@@3KA; ulong KdcGlobalSCLogonEKUNotRequired
0x1800385a1  mov     [rsp+768h+var_4D0], rax
0x1800385a9  mov     [rsp+768h+var_4C8], rdi
0x1800385b1  mov     [rsp+768h+var_4C0], rdi
0x1800385b9  lea     rax, aUsecachedcrlon; "UseCachedCRLOnlyAndIgnoreRevocationUnkn"...
0x1800385c0  mov     [rsp+768h+var_4B8], rax
0x1800385c8  lea     rax, ?KdcGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors@@3KA; ulong KdcGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors
0x1800385cf  mov     [rsp+768h+var_4B0], rax
0x1800385d7  mov     [rsp+768h+var_4A8], rbx
0x1800385df  mov     [rsp+768h+var_4A0], rdi
0x1800385e7  lea     rax, aDhkeylifetime; "DHKeyLifeTime"
0x1800385ee  mov     [rsp+768h+var_498], rax
0x1800385f6  lea     rax, [rsp+768h+var_6F0]
0x1800385fb  mov     [rsp+768h+var_490], rax
0x180038603  mov     [rsp+768h+var_488], 78h ; 'x'
0x18003860f  mov     [rsp+768h+var_480], rdi
0x180038617  lea     rax, aUsewellknowndh; "UseWellknownDHDomainParametersOnly"
0x18003861e  mov     [rsp+768h+var_478], rax
0x180038626  lea     rax, ?KdcGlobalUseWellknownDHDomainParametersOnly@@3KA; ulong KdcGlobalUseWellknownDHDomainParametersOnly
0x18003862d  mov     [rsp+768h+var_470], rax
0x180038635  mov     [rsp+768h+var_468], rdi
0x18003863d  mov     [rsp+768h+var_460], rdi
0x180038645  lea     rax, aModpdhonly; "ModpDHOnly"
0x18003864c  mov     [rsp+768h+var_458], rax
0x180038654  lea     rax, ?KdcGlobalModpDHOnly@@3KA; ulong KdcGlobalModpDHOnly
0x18003865b  mov     [rsp+768h+var_450], rax
0x180038663  mov     [rsp+768h+var_448], rbx
0x18003866b  mov     [rsp+768h+var_440], rdi
0x180038673  lea     rax, aLeafonly; "LeafOnly"
0x18003867a  mov     [rsp+768h+var_438], rax
0x180038682  lea     rax, ?KdcGlobalSendOnlyLeafCertificate@@3KA; ulong KdcGlobalSendOnlyLeafCertificate
0x180038689  mov     [rsp+768h+var_430], rax
0x180038691  mov     [rsp+768h+var_428], rdi
0x180038699  mov     [rsp+768h+var_420], rdi
0x1800386a1  lea     rax, aDisablenamespa; "DisableNamespaceFiltering"
0x1800386a8  mov     [rsp+768h+var_418], rax
0x1800386b0  lea     rax, ?KdcGlobalDisableNamespaceFiltering@@3KA; ulong KdcGlobalDisableNamespaceFiltering
0x1800386b7  mov     [rsp+768h+var_410], rax
0x1800386bf  mov     [rsp+768h+var_408], rbx
0x1800386c7  mov     [rsp+768h+var_400], rdi
0x1800386cf  lea     rax, aEmitlili; "EmitLILI"
0x1800386d6  mov     [rsp+768h+var_3F8], rax
0x1800386de  lea     rax, ?KdcGlobalEmitLILI@@3KA; ulong KdcGlobalEmitLILI
0x1800386e5  mov     [rsp+768h+var_3F0], rax
0x1800386ed  mov     [rsp+768h+var_3E8], rbx
0x1800386f5  mov     [rsp+768h+var_3E0], edi
0x1800386fc  mov     [rsp+768h+var_3DC], edi
0x180038703  lea     rax, aUseforestsearc; "UseForestSearch"
0x18003870a  mov     [rsp+768h+var_3D8], rax
0x180038712  lea     rax, ?KdcUseForestSearchOrder@@3KA; ulong KdcUseForestSearchOrder
0x180038719  mov     [rsp+768h+var_3D0], rax
0x180038721  mov     [rsp+768h+var_3C8], rbx
0x180038729  mov     [rsp+768h+var_3C0], edi
0x180038730  mov     [rsp+768h+var_3BC], edi
0x180038737  lea     rax, aFsocachetimeou; "FsoCacheTimeout"
0x18003873e  mov     [rsp+768h+var_3B8], rax
0x180038746  lea     rax, [rsp+768h+var_6EC]
0x18003874b  mov     [rsp+768h+var_3B0], rax
0x180038753  mov     [rsp+768h+var_3A8], 1Eh
0x18003875f  mov     [rsp+768h+var_3A0], rdi
0x180038767  lea     rax, aEnablea2dfchec; "EnableA2DFCheck"
0x18003876e  mov     [rsp+768h+var_398], rax
0x180038776  lea     rax, ?KdcGlobalEnableA2DFCheck@@3KA; ulong KdcGlobalEnableA2DFCheck
0x18003877d  mov     [rsp+768h+var_390], rax
0x180038785  mov     [rsp+768h+var_388], rdi
0x18003878d  mov     [rsp+768h+var_380], rdi
0x180038795  lea     rax, aA2dfprotocoltr; "A2DFProtocolTransition"
0x18003879c  mov     [rsp+768h+var_378], rax
0x1800387a4  lea     rax, ?KdcGlobalA2DFProtocolTransition@@3KA; ulong KdcGlobalA2DFProtocolTransition
0x1800387ab  mov     [rsp+768h+var_370], rax
0x1800387b3  mov     [rsp+768h+var_368], rdi
0x1800387bb  mov     [rsp+768h+var_360], rdi
0x1800387c3  lea     rax, aNonforwardable; "NonForwardableDelegation"
0x1800387ca  mov     [rsp+768h+var_358], rax
0x1800387d2  lea     rax, ?KdcGlobalNonForwardableDelegation@@3KA; ulong KdcGlobalNonForwardableDelegation
0x1800387d9  mov     [rsp+768h+var_350], rax
0x1800387e1  mov     [rsp+768h+var_348], rbx
0x1800387e9  mov     [rsp+768h+var_340], edi
0x1800387f0  mov     [rsp+768h+var_33C], edi
0x1800387f7  lea     rax, aCbacandarmorle; "CbacAndArmorLevel"
0x1800387fe  mov     [rsp+768h+var_338], rax
0x180038806  lea     rax, ?KdcGlobalCbacAndArmorLevel@@3KA; ulong KdcGlobalCbacAndArmorLevel
0x18003880d  mov     [rsp+768h+var_330], rax
0x180038815  mov     [rsp+768h+var_328], rbx
0x18003881d  mov     [rsp+768h+var_320], edi
0x180038824  mov     [rsp+768h+var_31C], edi
0x18003882b  lea     rax, aDomainfastleve; "DomainFastLevel"
0x180038832  mov     [rsp+768h+var_318], rax
0x18003883a  lea     rax, ?KdcGlobalDomainFastLevel@@3KA; ulong KdcGlobalDomainFastLevel
0x180038841  mov     [rsp+768h+var_310], rax
0x180038849  mov     [rsp+768h+var_308], rbx
0x180038851  mov     [rsp+768h+var_300], edi
0x180038858  mov     [rsp+768h+var_2FC], edi
0x18003885f  lea     rax, aDomainclaimsle; "DomainClaimsLevel"
0x180038866  mov     [rsp+768h+var_2F8], rax
0x18003886e  lea     rax, ?KdcGlobalDomainClaimsLevel@@3KA; ulong KdcGlobalDomainClaimsLevel
0x180038875  mov     [rsp+768h+var_2F0], rax
0x18003887d  mov     [rsp+768h+var_2E8], rbx
0x180038885  mov     [rsp+768h+var_2E0], edi
0x18003888c  mov     [rsp+768h+var_2DC], edi
0x180038893  lea     rax, aAdvertisefast; "AdvertiseFast"
0x18003889a  mov     [rsp+768h+var_2D8], rax
0x1800388a2  lea     rax, ?KdcGlobalAdvertiseFast@@3KA; ulong KdcGlobalAdvertiseFast
0x1800388a9  mov     [rsp+768h+var_2D0], rax
0x1800388b1  mov     [rsp+768h+var_2C8], rbx
0x1800388b9  mov     [rsp+768h+var_2C0], edi
0x1800388c0  mov     [rsp+768h+var_2BC], edi
0x1800388c7  lea     rax, aDisableresourc; "DisableResourceGroupsFields"
0x1800388ce  mov     [rsp+768h+var_2B8], rax
0x1800388d6  lea     rax, ?KdcGlobalDisableResourceGroupsFields@@3KA; ulong KdcGlobalDisableResourceGroupsFields
0x1800388dd  mov     [rsp+768h+var_2B0], rax
0x1800388e5  mov     [rsp+768h+var_2A8], rbx
0x1800388ed  mov     [rsp+768h+var_2A0], edi
0x1800388f4  mov     [rsp+768h+var_29C], edi
0x1800388fb  lea     rax, aTicketsizethre; "TicketSizeThreshold"
0x180038902  mov     [rsp+768h+var_298], rax
0x18003890a  lea     rax, ?KdcGlobalTicketSizeThreshold@@3KA; ulong KdcGlobalTicketSizeThreshold
0x180038911  mov     [rsp+768h+var_290], rax
0x180038919  mov     [rsp+768h+var_288], 2EE0h
0x180038925  mov     [rsp+768h+var_280], edi
0x18003892c  mov     [rsp+768h+var_27C], edi
0x180038933  lea     rax, aChainwithissua; "ChainWithIssuancePolicyOIDs"
0x18003893a  mov     [rsp+768h+var_278], rax
0x180038942  lea     rax, ?KdcGlobalChainWithIssuancePolicyOIDs@@3KA; ulong KdcGlobalChainWithIssuancePolicyOIDs
0x180038949  mov     [rsp+768h+var_270], rax
0x180038951  mov     [rsp+768h+var_268], rbx
0x180038959  mov     [rsp+768h+var_260], edi
0x180038960  mov     [rsp+768h+var_25C], edi
0x180038967  lea     rax, aRequestcompoun; "RequestCompoundId"
0x18003896e  mov     [rsp+768h+var_258], rax
0x180038976  lea     rax, ?KdcGlobalRequestCompoundId@@3KA; ulong KdcGlobalRequestCompoundId
0x18003897d  mov     [rsp+768h+var_250], rax
0x180038985  mov     [rsp+768h+var_248], rbx
0x18003898d  mov     [rsp+768h+var_240], edi
0x180038994  mov     [rsp+768h+var_23C], edi
0x18003899b  lea     rax, aPkinitfreshnes; "PKINITFreshness"
0x1800389a2  mov     [rsp+768h+var_238], rax
0x1800389aa  lea     rax, ?KdcGlobalRequireFreshness@@3KA; ulong KdcGlobalRequireFreshness
0x1800389b1  mov     [rsp+768h+var_230], rax
0x1800389b9  mov     [rsp+768h+var_228], rbx
0x1800389c1  mov     [rsp+768h+var_220], edi
0x1800389c8  mov     [rsp+768h+var_21C], edi
0x1800389cf  lea     rax, aPkinitencrypti; "PKINITEncryptionMode"
0x1800389d6  mov     [rsp+768h+var_218], rax
0x1800389de  lea     rax, [rsp+768h+var_6F4]
0x1800389e3  mov     [rsp+768h+var_210], rax
0x1800389eb  lea     esi, [rbx+2]
0x1800389ee  mov     [rsp+768h+var_208], rsi
0x1800389f6  mov     [rsp+768h+var_200], edi
0x1800389fd  mov     [rsp+768h+var_1FC], edi
0x180038a04  lea     rax, aPkinithashalgo; "PKInitHashAlgorithmConfigurationEnabled"
0x180038a0b  mov     [rsp+768h+var_1F8], rax
0x180038a13  lea     rax, [rsp+768h+var_708]
0x180038a18  mov     [rsp+768h+var_1F0], rax
0x180038a20  mov     [rsp+768h+var_1E8], rbx
0x180038a28  mov     [rsp+768h+var_1E0], edi
0x180038a2f  mov     [rsp+768h+var_1DC], edi
0x180038a36  lea     rax, aPkinitsha1; "PKINITSHA1"
0x180038a3d  mov     [rsp+768h+var_1D8], rax
0x180038a45  lea     rax, [rsp+768h+var_704]
0x180038a4a  mov     [rsp+768h+var_1D0], rax
0x180038a52  mov     [rsp+768h+var_1C8], rdi
0x180038a5a  mov     [rsp+768h+var_1C0], edi
0x180038a61  mov     [rsp+768h+var_1BC], edi
0x180038a68  lea     rax, aPkinitsha256; "PKINITSHA256"
0x180038a6f  mov     [rsp+768h+var_1B8], rax
0x180038a77  lea     rax, [rsp+768h+var_700]
0x180038a7c  mov     [rsp+768h+var_1B0], rax
0x180038a84  mov     [rsp+768h+var_1A8], rdi
0x180038a8c  mov     [rsp+768h+var_1A0], edi
0x180038a93  mov     [rsp+768h+var_19C], edi
0x180038a9a  lea     rax, aPkinitsha384; "PKINITSHA384"
0x180038aa1  mov     [rsp+768h+var_198], rax
0x180038aa9  lea     rax, [rsp+768h+var_6FC]
0x180038aae  mov     [rsp+768h+var_190], rax
  ... truncated ...
```
