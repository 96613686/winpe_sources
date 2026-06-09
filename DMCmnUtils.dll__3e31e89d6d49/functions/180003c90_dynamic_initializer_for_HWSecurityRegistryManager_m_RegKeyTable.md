# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x180003c90`
- end: `0x1800049ea`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `3418`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003c90`
- `0x180007270`
- `0x180007620`
- `0x180052020`
- `0x18005b2c4`
- `0x18005b73c`
- `0x180099dcc`
- `0x180099eb0`
- `0x18009a7b8`
- `0x18009aa80`
- `0x1800b2630`

## string_xrefs

- `0x180003e82`: `System\CurrentControlSet\Services`
- `0x180003dc3`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x180003f43`: `System\CurrentControlSet\Services\TPM`
- `0x1800040bf`: `System\CurrentControlSet\Services\TPM`
- `0x18000446f`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`
- `0x1800042f7`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x18000439f`: `TaskStates`
- `0x1800045e7`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x18000481d`: `System\CurrentControlSet\Control\IntegrityServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__()
{
  __int64 v0; // rsi
  int v1; // edi
  int v2; // ebx
  int v3; // eax
  __int64 v4; // rsi
  int v5; // edi
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rsi
  int v9; // edi
  int v10; // ebx
  int v11; // eax
  __int64 v12; // rsi
  int v13; // edi
  int v14; // ebx
  int v15; // eax
  __int64 v16; // rsi
  int v17; // edi
  int v18; // ebx
  int v19; // eax
  __int64 v20; // rsi
  int v21; // edi
  int v22; // ebx
  int v23; // eax
  __int64 v24; // rsi
  int v25; // edi
  int v26; // ebx
  int v27; // eax
  __int64 v28; // rsi
  int v29; // edi
  int v30; // ebx
  int v31; // eax
  __int64 v32; // rsi
  int v33; // edi
  int v34; // ebx
  int v35; // eax
  __int64 v36; // rsi
  int v37; // edi
  int v38; // ebx
  int v39; // eax
  __int64 v40; // rsi
  int v41; // edi
  int v42; // ebx
  int v43; // eax
  __int64 v44; // rsi
  int v45; // edi
  int v46; // ebx
  int v47; // eax
  __int64 v48; // rsi
  int v49; // edi
  int v50; // ebx
  int v51; // eax
  __int64 v52; // rsi
  int v53; // edi
  int v54; // ebx
  int v55; // eax
  __int64 v56; // rsi
  int v57; // edi
  int v58; // ebx
  int v59; // eax
  __int64 v60; // rsi
  int v61; // edi
  int v62; // ebx
  int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rdi
  __int64 *v66; // rbx
  int v68; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+64h] [rbp-9Ch] BYREF
  int v70; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+6Ch] [rbp-94h] BYREF
  int v72; // [rsp+70h] [rbp-90h] BYREF
  int v73; // [rsp+74h] [rbp-8Ch] BYREF
  int v74; // [rsp+78h] [rbp-88h] BYREF
  int v75; // [rsp+7Ch] [rbp-84h] BYREF
  int v76; // [rsp+80h] [rbp-80h] BYREF
  int v77; // [rsp+84h] [rbp-7Ch] BYREF
  int v78; // [rsp+88h] [rbp-78h] BYREF
  int v79; // [rsp+8Ch] [rbp-74h] BYREF
  int v80; // [rsp+90h] [rbp-70h] BYREF
  int v81; // [rsp+94h] [rbp-6Ch] BYREF
  int v82; // [rsp+98h] [rbp-68h] BYREF
  int v83; // [rsp+9Ch] [rbp-64h] BYREF
  _BYTE v84[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v85[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v86[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v87[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v88[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v89[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v90[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v91[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v92[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v93[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v94[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v95[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v96[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v97[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v98[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v99[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v100[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v101[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v102[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v103[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v104[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v105[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v106[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v107[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v108[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v109[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v110[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v111[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v112[32]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v113[32]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v114[32]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v115[32]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v116[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v117[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v118[32]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v119[32]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v120[32]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v121[32]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v122[32]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v123[32]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v124[32]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v125[32]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v126[32]; // [rsp+5E0h] [rbp+4E0h] BYREF
  _BYTE v127[32]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v128[32]; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v129[32]; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v130[32]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v131[32]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v132[32]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v133[32]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v134[32]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v135[32]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v136[32]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v137[32]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v138[32]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v139[32]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v140[32]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v141[32]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v142[32]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v143[32]; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v144[32]; // [rsp+820h] [rbp+720h] BYREF
  _BYTE v145[32]; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v146[32]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v147[32]; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v148[144]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v149[144]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v150[144]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v151[144]; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v152[144]; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v153[144]; // [rsp+B70h] [rbp+A70h] BYREF
  _BYTE v154[144]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v155[144]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v156[144]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v157[144]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v158[144]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v159[144]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v160[144]; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v161[144]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v162[144]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v163[144]; // [rsp+1110h] [rbp+1010h] BYREF
  _BYTE v164[144]; // [rsp+11A0h] [rbp+10A0h] BYREF
  _BYTE v165[144]; // [rsp+1230h] [rbp+1130h] BYREF
  _BYTE v166[144]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _BYTE v167[144]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v168[144]; // [rsp+13E0h] [rbp+12E0h] BYREF
  _BYTE v169[144]; // [rsp+1470h] [rbp+1370h] BYREF
  _BYTE v170[144]; // [rsp+1500h] [rbp+1400h] BYREF
  _BYTE v171[144]; // [rsp+1590h] [rbp+1490h] BYREF
  _BYTE v172[144]; // [rsp+1620h] [rbp+1520h] BYREF
  _BYTE v173[144]; // [rsp+16B0h] [rbp+15B0h] BYREF
  _BYTE v174[144]; // [rsp+1740h] [rbp+1640h] BYREF
  _BYTE v175[144]; // [rsp+17D0h] [rbp+16D0h] BYREF
  _BYTE v176[144]; // [rsp+1860h] [rbp+1760h] BYREF
  _BYTE v177[144]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _BYTE v178[144]; // [rsp+1980h] [rbp+1880h] BYREF
  _BYTE v179[144]; // [rsp+1A10h] [rbp+1910h] BYREF
  __int64 v180; // [rsp+1AA0h] [rbp+19A0h] BYREF

  v0 = std::wstring::wstring(v84, &pszSrc);
  v1 = std::wstring::wstring(v85, L"TpmRegDriverGroupPolicyData");
  v2 = std::wstring::wstring(v86, L"TPM");
  v3 = std::wstring::wstring(v87, L"Software\\Policies\\Microsoft");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v163, v3, v2, v1, 0, 131103, v0);
  v68 = 0;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v164,
    &v68,
    v163);
  v4 = std::wstring::wstring(v88, &pszSrc);
  v5 = std::wstring::wstring(v89, &pszSrc);
  v6 = std::wstring::wstring(v90, L"PcrInfo");
  v7 = std::wstring::wstring(v91, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v162, v7, v6, v5, 0, 131103, v4);
  v69 = 14;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v165,
    &v69,
    v162);
  v8 = std::wstring::wstring(v92, &pszSrc);
  v9 = std::wstring::wstring(v93, L"TpmRegDriverTpm");
  v10 = std::wstring::wstring(v94, L"TPM");
  v11 = std::wstring::wstring(v95, L"System\\CurrentControlSet\\Services");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v161, v11, v10, v9, 0, 131103, v8);
  v70 = 1;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v166,
    &v70,
    v161);
  v12 = std::wstring::wstring(v96, &pszSrc);
  v13 = std::wstring::wstring(v97, L"TpmRegPlatformQuoteKeysKey");
  v14 = std::wstring::wstring(v98, L"PlatformQuoteKeys");
  v15 = std::wstring::wstring(v99, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v160, v15, v14, v13, 0, 131103, v12);
  v71 = 2;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v167,
    &v71,
    v160);
  v16 = std::wstring::wstring(v100, &pszSrc);
  v17 = std::wstring::wstring(v101, L"TpmRegProvisioningKey");
  v18 = std::wstring::wstring(v102, L"ProvisionInfo");
  v19 = std::wstring::wstring(v103, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v159, v19, v18, v17, 0, 131103, v16);
  v72 = 3;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v168,
    &v72,
    v159);
  v20 = std::wstring::wstring(
          v104,
          L"O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KA;;;LS)(A;CIIO;GA;;;LS)"
           "(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v21 = std::wstring::wstring(v105, L"TpmRegDriverPersistedData");
  v22 = std::wstring::wstring(v106, L"WMI");
  v23 = std::wstring::wstring(v107, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v158, v23, v22, v21, 0, 131103, v20);
  v73 = 4;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v169,
    &v73,
    v158);
  v24 = std::wstring::wstring(
          v108,
          L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v25 = std::wstring::wstring(v109, L"TpmRegDriverPersistedDataAdmin");
  v26 = std::wstring::wstring(v110, L"Admin");
  v27 = std::wstring::wstring(v111, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v157, v27, v26, v25, 0, 131103, v24);
  v74 = 5;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v170,
    &v74,
    v157);
  v28 = std::wstring::wstring(
          v112,
          L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CI"
           "IO;GA;;;NS)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KR;;;S-1-5-4)(A;CIIO;GR;;;S-1-5-4)(A;;KR;;;S-1-5-1"
           "1)(A;CIIO;GR;;;S-1-5-11)");
  v29 = std::wstring::wstring(v113, L"TpmRegDriverPersistedDataEndorsement");
  v30 = std::wstring::wstring(v114, L"Endorsement");
  v31 = std::wstring::wstring(v115, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v156, v31, v30, v29, 0, 131103, v28);
  v75 = 6;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v171,
    &v75,
    v156);
  v32 = std::wstring::wstring(v116, &pszSrc);
  v33 = std::wstring::wstring(v117, L"TPMCoreProvisioningHealthCertStore");
  v34 = std::wstring::wstring(v118, L"Store");
  v35 = std::wstring::wstring(v119, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v155, v35, v34, v33, 0, 131103, v32);
  v76 = 7;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v172,
    &v76,
    v155);
  v36 = std::wstring::wstring(v120, &pszSrc);
  v37 = std::wstring::wstring(v121, &pszSrc);
  v38 = std::wstring::wstring(v122, L"TaskStates");
  v39 = std::wstring::wstring(v123, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v154, v39, v38, v37, 1, 131103, v36);
  v77 = 8;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v173,
    &v77,
    v154);
  v40 = std::wstring::wstring(v124, &pszSrc);
  v41 = std::wstring::wstring(v125, &pszSrc);
  v42 = std::wstring::wstring(v126, L"AttestationInfo");
  v43 = std::wstring::wstring(v127, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v153, v43, v42, v41, 1, 131103, v40);
  v78 = 9;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v174,
    &v78,
    v153);
  v44 = std::wstring::wstring(v128, &pszSrc);
  v45 = std::wstring::wstring(v129, &pszSrc);
  v46 = std::wstring::wstring(v130, L"Volatile-AIKCertEnroll-EXCLUSIVE");
  v47 = std::wstring::wstring(v131, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v152, v47, v46, v45, 1, 131103, v44);
  v79 = 10;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v175,
    &v79,
    v152);
  v48 = std::wstring::wstring(v132, &pszSrc);
  v49 = std::wstring::wstring(v133, L"TPMCoreProvisioningEKCertificates");
  v50 = std::wstring::wstring(v134, L"EkCertStore");
  v51 = std::wstring::wstring(v135, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v151, v51, v50, v49, 0, 983103, v48);
  v80 = 11;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v176,
    &v80,
    v151);
  v52 = std::wstring::wstring(v136, &pszSrc);
  v53 = std::wstring::wstring(v137, L"TPMCoreProvisioningEKCertificates");
  v54 = std::wstring::wstring(v138, L"EkCertStoreECC");
  v55 = std::wstring::wstring(v139, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v150, v55, v54, v53, 0, 983103, v52);
  v81 = 12;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v177,
    &v81,
    v150);
  v56 = std::wstring::wstring(v140, &pszSrc);
  v57 = std::wstring::wstring(v141, L"TPMCoreProvisioningIntermediateCACerts");
  v58 = std::wstring::wstring(v142, L"IntermediateCACertStore");
  v59 = std::wstring::wstring(v143, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v149, v59, v58, v57, 0, 983103, v56);
  v82 = 13;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v178,
    &v82,
    v149);
  v60 = std::wstring::wstring(v144, &pszSrc);
  v61 = std::wstring::wstring(v145, &pszSrc);
  v62 = std::wstring::wstring(v146, &pszSrc);
  v63 = std::wstring::wstring(v147, L"System\\CurrentControlSet\\Control\\IntegrityServices");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v148, v63, v62, v61, 0, 131097, v60);
  v83 = 15;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v179,
    &v83,
    v148);
  HWSecurityRegistryManager::m_RegKeyTable = 0;
  v65 = std::_Allocate<16,std::_Default_allocate_traits>(176);
  *(_QWORD *)v65 = v65;
  *(_QWORD *)(v65 + 8) = v65;
  *(_QWORD *)(v65 + 16) = v65;
  *(_WORD *)(v65 + 24) = 257;
  *(_QWORD *)&HWSecurityRegistryManager::m_RegKeyTable = v65;
  v66 = (__int64 *)v164;
  do
  {
    std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Emplace_hint<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(
      v64,
      v65,
      v66);
    v66 += 18;
  }
  while ( v66 != &v180 );
  `eh vector destructor iterator'(
    v164,
    0x90u,
    0x10u,
    std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v148);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v149);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v150);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v151);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v152);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v153);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v154);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v155);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v156);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v157);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v158);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v159);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v160);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v161);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v162);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v163);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegKeyTable__);
}

```

## disassembly

```asm
0x180003c90  push    rbp
0x180003c92  push    rbx
0x180003c93  push    rsi
0x180003c94  push    rdi
0x180003c95  push    r12
0x180003c97  push    r13
0x180003c99  push    r14
0x180003c9b  push    r15
0x180003c9d  lea     rbp, [rsp-19B8h]
0x180003ca5  mov     eax, 1AB8h
0x180003caa  call    _alloca_probe
0x180003caf  sub     rsp, rax
0x180003cb2  mov     rax, cs:__security_cookie
0x180003cb9  xor     rax, rsp
0x180003cbc  mov     [rbp+19F0h+var_50], rax
0x180003cc3  lea     rax, [rbp+19F0h+var_1A50]
0x180003cc7  mov     [rsp+1AF0h+var_1AB0], rax
0x180003ccc  lea     r12, pszSrc
0x180003cd3  mov     rdx, r12
0x180003cd6  lea     rcx, [rbp+19F0h+var_1A50]
0x180003cda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003cdf  mov     rsi, rax
0x180003ce2  lea     rax, [rbp+19F0h+var_1A30]
0x180003ce6  mov     [rsp+1AF0h+var_1AA8], rax
0x180003ceb  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x180003cf2  lea     rcx, [rbp+19F0h+var_1A30]
0x180003cf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003cfb  mov     rdi, rax
0x180003cfe  lea     rax, [rbp+19F0h+var_1A10]
0x180003d02  mov     [rsp+1AF0h+var_1AA0], rax
0x180003d07  lea     rdx, aTpm; "TPM"
0x180003d0e  lea     rcx, [rbp+19F0h+var_1A10]
0x180003d12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003d17  mov     rbx, rax
0x180003d1a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft"
0x180003d21  lea     rcx, [rbp+19F0h+var_19F0]
0x180003d25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003d2a  nop
0x180003d2b  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003d30  mov     r15d, 2001Fh
0x180003d36  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003d3b  xor     r13d, r13d
0x180003d3e  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003d43  mov     r9, rdi
0x180003d46  mov     r8, rbx
0x180003d49  mov     rdx, rax
0x180003d4c  lea     rcx, [rbp+19F0h+var_9E0]
0x180003d53  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003d58  nop
0x180003d59  mov     [rsp+1AF0h+var_1A90], r13d
0x180003d5e  lea     r8, [rbp+19F0h+var_9E0]
0x180003d65  lea     rdx, [rsp+1AF0h+var_1A90]
0x180003d6a  lea     rcx, [rbp+19F0h+var_950]
0x180003d71  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003d76  nop
0x180003d77  lea     rax, [rbp+19F0h+var_19D0]
0x180003d7b  mov     [rsp+1AF0h+var_1A98], rax
0x180003d80  mov     rdx, r12
0x180003d83  lea     rcx, [rbp+19F0h+var_19D0]
0x180003d87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003d8c  mov     rsi, rax
0x180003d8f  lea     rax, [rbp+19F0h+var_19B0]
0x180003d93  mov     [rsp+1AF0h+var_1AA0], rax
0x180003d98  mov     rdx, r12
0x180003d9b  lea     rcx, [rbp+19F0h+var_19B0]
0x180003d9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003da4  mov     rdi, rax
0x180003da7  lea     rax, [rbp+19F0h+var_1990]
0x180003dab  mov     [rsp+1AF0h+var_1AA8], rax
0x180003db0  lea     rdx, aPcrinfo_0; "PcrInfo"
0x180003db7  lea     rcx, [rbp+19F0h+var_1990]
0x180003dbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003dc0  mov     rbx, rax
0x180003dc3  lea     r14, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\TP"...
0x180003dca  mov     rdx, r14
0x180003dcd  lea     rcx, [rbp+19F0h+var_1970]
0x180003dd4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003dd9  nop
0x180003dda  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003ddf  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003de4  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003de9  mov     r9, rdi
0x180003dec  mov     r8, rbx
0x180003def  mov     rdx, rax
0x180003df2  lea     rcx, [rbp+19F0h+var_A70]
0x180003df9  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003dfe  nop
0x180003dff  mov     [rsp+1AF0h+var_1A8C], 0Eh
0x180003e07  lea     r8, [rbp+19F0h+var_A70]
0x180003e0e  lea     rdx, [rsp+1AF0h+var_1A8C]
0x180003e13  lea     rcx, [rbp+19F0h+var_8C0]
0x180003e1a  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003e1f  nop
0x180003e20  lea     rax, [rbp+19F0h+var_1950]
0x180003e27  mov     [rsp+1AF0h+var_1A98], rax
0x180003e2c  mov     rdx, r12
0x180003e2f  lea     rcx, [rbp+19F0h+var_1950]
0x180003e36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003e3b  mov     rsi, rax
0x180003e3e  lea     rax, [rbp+19F0h+var_1930]
0x180003e45  mov     [rsp+1AF0h+var_1AA0], rax
0x180003e4a  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x180003e51  lea     rcx, [rbp+19F0h+var_1930]
0x180003e58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003e5d  mov     rdi, rax
0x180003e60  lea     rax, [rbp+19F0h+var_1910]
0x180003e67  mov     [rsp+1AF0h+var_1AA8], rax
0x180003e6c  lea     rdx, aTpm; "TPM"
0x180003e73  lea     rcx, [rbp+19F0h+var_1910]
0x180003e7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003e7f  mov     rbx, rax
0x180003e82  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services"
0x180003e89  lea     rcx, [rbp+19F0h+var_18F0]
0x180003e90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003e95  nop
0x180003e96  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003e9b  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003ea0  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003ea5  mov     r9, rdi
0x180003ea8  mov     r8, rbx
0x180003eab  mov     rdx, rax
0x180003eae  lea     rcx, [rbp+19F0h+var_B00]
0x180003eb5  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003eba  nop
0x180003ebb  lea     r12d, [r13+1]
0x180003ebf  mov     [rsp+1AF0h+var_1A88], r12d
0x180003ec4  lea     r8, [rbp+19F0h+var_B00]
0x180003ecb  lea     rdx, [rsp+1AF0h+var_1A88]
0x180003ed0  lea     rcx, [rbp+19F0h+var_830]
0x180003ed7  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003edc  nop
0x180003edd  lea     rax, [rbp+19F0h+var_18D0]
0x180003ee4  mov     [rsp+1AF0h+var_1A98], rax
0x180003ee9  lea     rdx, pszSrc
0x180003ef0  lea     rcx, [rbp+19F0h+var_18D0]
0x180003ef7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003efc  mov     rsi, rax
0x180003eff  lea     rax, [rbp+19F0h+var_18B0]
0x180003f06  mov     [rsp+1AF0h+var_1AA0], rax
0x180003f0b  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180003f12  lea     rcx, [rbp+19F0h+var_18B0]
0x180003f19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003f1e  mov     rdi, rax
0x180003f21  lea     rax, [rbp+19F0h+var_1890]
0x180003f28  mov     [rsp+1AF0h+var_1AA8], rax
0x180003f2d  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x180003f34  lea     rcx, [rbp+19F0h+var_1890]
0x180003f3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003f40  mov     rbx, rax
0x180003f43  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\TP"...
0x180003f4a  lea     rcx, [rbp+19F0h+var_1870]
0x180003f51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003f56  nop
0x180003f57  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003f5c  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003f61  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003f66  mov     r9, rdi
0x180003f69  mov     r8, rbx
0x180003f6c  mov     rdx, rax
0x180003f6f  lea     rcx, [rbp+19F0h+var_B90]
0x180003f76  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003f7b  nop
0x180003f7c  mov     [rsp+1AF0h+var_1A84], 2
0x180003f84  lea     r8, [rbp+19F0h+var_B90]
0x180003f8b  lea     rdx, [rsp+1AF0h+var_1A84]
0x180003f90  lea     rcx, [rbp+19F0h+var_7A0]
0x180003f97  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003f9c  nop
0x180003f9d  lea     rax, [rbp+19F0h+var_1850]
0x180003fa4  mov     [rsp+1AF0h+var_1A98], rax
0x180003fa9  lea     rdx, pszSrc
0x180003fb0  lea     rcx, [rbp+19F0h+var_1850]
0x180003fb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003fbc  mov     rsi, rax
0x180003fbf  lea     rax, [rbp+19F0h+var_1830]
0x180003fc6  mov     [rsp+1AF0h+var_1AA0], rax
0x180003fcb  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x180003fd2  lea     rcx, [rbp+19F0h+var_1830]
0x180003fd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003fde  mov     rdi, rax
0x180003fe1  lea     rax, [rbp+19F0h+var_1810]
0x180003fe8  mov     [rsp+1AF0h+var_1AA8], rax
0x180003fed  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180003ff4  lea     rcx, [rbp+19F0h+var_1810]
0x180003ffb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004000  mov     rbx, rax
0x180004003  mov     rdx, r14
0x180004006  lea     rcx, [rbp+19F0h+var_17F0]
0x18000400d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004012  nop
0x180004013  mov     [rsp+1AF0h+var_1AC0], rsi
0x180004018  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000401d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180004022  mov     r9, rdi
0x180004025  mov     r8, rbx
0x180004028  mov     rdx, rax
0x18000402b  lea     rcx, [rbp+19F0h+var_C20]
0x180004032  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004037  nop
0x180004038  mov     [rsp+1AF0h+var_1A80], 3
0x180004040  lea     r8, [rbp+19F0h+var_C20]
0x180004047  lea     rdx, [rsp+1AF0h+var_1A80]
0x18000404c  lea     rcx, [rbp+19F0h+var_710]
0x180004053  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004058  nop
0x180004059  lea     rax, [rbp+19F0h+var_17D0]
0x180004060  mov     [rsp+1AF0h+var_1A98], rax
0x180004065  lea     rdx, aOSydAiarAKrAuA; "O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)("...
0x18000406c  lea     rcx, [rbp+19F0h+var_17D0]
0x180004073  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004078  mov     rsi, rax
0x18000407b  lea     rax, [rbp+19F0h+var_17B0]
0x180004082  mov     [rsp+1AF0h+var_1AA0], rax
0x180004087  lea     rdx, aTpmregdriverpe; "TpmRegDriverPersistedData"
0x18000408e  lea     rcx, [rbp+19F0h+var_17B0]
0x180004095  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000409a  mov     rdi, rax
0x18000409d  lea     rax, [rbp+19F0h+var_1790]
0x1800040a4  mov     [rsp+1AF0h+var_1AA8], rax
0x1800040a9  lea     rdx, aWmi; "WMI"
0x1800040b0  lea     rcx, [rbp+19F0h+var_1790]
0x1800040b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800040bc  mov     rbx, rax
0x1800040bf  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\TP"...
0x1800040c6  lea     rcx, [rbp+19F0h+var_1770]
0x1800040cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800040d2  nop
0x1800040d3  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800040d8  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800040dd  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800040e2  mov     r9, rdi
0x1800040e5  mov     r8, rbx
0x1800040e8  mov     rdx, rax
0x1800040eb  lea     rcx, [rbp+19F0h+var_CB0]
0x1800040f2  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800040f7  nop
0x1800040f8  mov     [rsp+1AF0h+var_1A7C], 4
0x180004100  lea     r8, [rbp+19F0h+var_CB0]
0x180004107  lea     rdx, [rsp+1AF0h+var_1A7C]
0x18000410c  lea     rcx, [rbp+19F0h+var_680]
0x180004113  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004118  nop
0x180004119  lea     rax, [rbp+19F0h+var_1750]
0x180004120  mov     [rsp+1AF0h+var_1A98], rax
0x180004125  lea     rdx, aOSydPaiAKaBaAC; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x18000412c  lea     rcx, [rbp+19F0h+var_1750]
0x180004133  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004138  mov     rsi, rax
0x18000413b  lea     rax, [rbp+19F0h+var_1730]
0x180004142  mov     [rsp+1AF0h+var_1AA0], rax
0x180004147  lea     rdx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x18000414e  lea     rcx, [rbp+19F0h+var_1730]
0x180004155  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000415a  mov     rdi, rax
0x18000415d  lea     rax, [rbp+19F0h+var_1710]
0x180004164  mov     [rsp+1AF0h+var_1AA8], rax
0x180004169  lea     rdx, aAdmin; "Admin"
0x180004170  lea     rcx, [rbp+19F0h+var_1710]
0x180004177  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000417c  mov     rbx, rax
0x18000417f  mov     rdx, r14
0x180004182  lea     rcx, [rbp+19F0h+var_16F0]
0x180004189  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000418e  nop
0x18000418f  mov     [rsp+1AF0h+var_1AC0], rsi
0x180004194  mov     [rsp+1AF0h+var_1AC8], r15d
0x180004199  mov     [rsp+1AF0h+var_1AD0], r13d
0x18000419e  mov     r9, rdi
0x1800041a1  mov     r8, rbx
0x1800041a4  mov     rdx, rax
0x1800041a7  lea     rcx, [rbp+19F0h+var_D40]
0x1800041ae  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800041b3  nop
0x1800041b4  mov     [rsp+1AF0h+var_1A78], 5
0x1800041bc  lea     r8, [rbp+19F0h+var_D40]
0x1800041c3  lea     rdx, [rsp+1AF0h+var_1A78]
0x1800041c8  lea     rcx, [rbp+19F0h+var_5F0]
0x1800041cf  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800041d4  nop
0x1800041d5  lea     rax, [rbp+19F0h+var_16D0]
0x1800041dc  mov     [rsp+1AF0h+var_1A98], rax
0x1800041e1  lea     rdx, aOSydPaiAKaBaAC_0; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x1800041e8  lea     rcx, [rbp+19F0h+var_16D0]
0x1800041ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800041f4  mov     rsi, rax
0x1800041f7  lea     rax, [rbp+19F0h+var_16B0]
0x1800041fe  mov     [rsp+1AF0h+var_1AA0], rax
0x180004203  lea     rdx, aTpmregdriverpe_1; "TpmRegDriverPersistedDataEndorsement"
0x18000420a  lea     rcx, [rbp+19F0h+var_16B0]
0x180004211  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004216  mov     rdi, rax
0x180004219  lea     rax, [rbp+19F0h+var_1690]
0x180004220  mov     [rsp+1AF0h+var_1AA8], rax
0x180004225  lea     rdx, aEndorsement; "Endorsement"
0x18000422c  lea     rcx, [rbp+19F0h+var_1690]
0x180004233  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004238  mov     rbx, rax
0x18000423b  mov     rdx, r14
0x18000423e  lea     rcx, [rbp+19F0h+var_1670]
0x180004245  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
