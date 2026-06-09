# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x180025810`
- end: `0x180026555`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `3397`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180022110`
- `0x1800225e4`
- `0x18002321c`
- `0x180023680`
- `0x180025424`
- `0x18002655c`
- `0x1800764d0`
- `0x180076880`
- `0x180077d98`
- `0x1800c2c80`

## string_xrefs

- `0x180025ac3`: `System\CurrentControlSet\Services\TPM`
- `0x180025c3f`: `System\CurrentControlSet\Services\TPM`
- `0x180025e77`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x180025f1f`: `TaskStates`
- `0x18002639d`: `System\CurrentControlSet\Control\IntegrityServices`
- `0x180025a02`: `System\CurrentControlSet\Services`
- `0x180026167`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x180025fef`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`
- `0x180025943`: `System\CurrentControlSet\Services\TPM\WMI`

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
  __int64 v64; // rax
  __int64 v65; // rcx
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  int v68; // [rsp+64h] [rbp-9Ch] BYREF
  int v69; // [rsp+68h] [rbp-98h] BYREF
  int v70; // [rsp+6Ch] [rbp-94h] BYREF
  int v71; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+74h] [rbp-8Ch] BYREF
  int v73; // [rsp+78h] [rbp-88h] BYREF
  int v74; // [rsp+7Ch] [rbp-84h] BYREF
  int v75; // [rsp+80h] [rbp-80h] BYREF
  int v76; // [rsp+84h] [rbp-7Ch] BYREF
  int v77; // [rsp+88h] [rbp-78h] BYREF
  int v78; // [rsp+8Ch] [rbp-74h] BYREF
  int v79; // [rsp+90h] [rbp-70h] BYREF
  int v80; // [rsp+94h] [rbp-6Ch] BYREF
  int v81; // [rsp+98h] [rbp-68h] BYREF
  int v82; // [rsp+9Ch] [rbp-64h] BYREF
  _BYTE v83[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v84[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v85[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v86[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v87[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v88[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v89[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v90[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v91[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v92[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v93[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v94[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v95[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v96[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v97[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v98[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v99[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v100[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v101[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v102[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v103[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v104[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v105[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v106[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v107[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v108[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v109[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v110[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v111[32]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v112[32]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v113[32]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v114[32]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v115[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v116[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v117[32]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v118[32]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v119[32]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v120[32]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v121[32]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v122[32]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v123[32]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v124[32]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v125[32]; // [rsp+5E0h] [rbp+4E0h] BYREF
  _BYTE v126[32]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v127[32]; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v128[32]; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v129[32]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v130[32]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v131[32]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v132[32]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v133[32]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v134[32]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v135[32]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v136[32]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v137[32]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v138[32]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v139[32]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v140[32]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v141[32]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v142[32]; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v143[32]; // [rsp+820h] [rbp+720h] BYREF
  _BYTE v144[32]; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v145[32]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v146[32]; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v147[144]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v148[144]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v149[144]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v150[144]; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v151[144]; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v152[144]; // [rsp+B70h] [rbp+A70h] BYREF
  _BYTE v153[144]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v154[144]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v155[144]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v156[144]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v157[144]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v158[144]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v159[144]; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v160[144]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v161[144]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v162[144]; // [rsp+1110h] [rbp+1010h] BYREF
  _BYTE v163[144]; // [rsp+11A0h] [rbp+10A0h] BYREF
  _BYTE v164[144]; // [rsp+1230h] [rbp+1130h] BYREF
  _BYTE v165[144]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _BYTE v166[144]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v167[144]; // [rsp+13E0h] [rbp+12E0h] BYREF
  _BYTE v168[144]; // [rsp+1470h] [rbp+1370h] BYREF
  _BYTE v169[144]; // [rsp+1500h] [rbp+1400h] BYREF
  _BYTE v170[144]; // [rsp+1590h] [rbp+1490h] BYREF
  _BYTE v171[144]; // [rsp+1620h] [rbp+1520h] BYREF
  _BYTE v172[144]; // [rsp+16B0h] [rbp+15B0h] BYREF
  _BYTE v173[144]; // [rsp+1740h] [rbp+1640h] BYREF
  _BYTE v174[144]; // [rsp+17D0h] [rbp+16D0h] BYREF
  _BYTE v175[144]; // [rsp+1860h] [rbp+1760h] BYREF
  _BYTE v176[144]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _BYTE v177[144]; // [rsp+1980h] [rbp+1880h] BYREF
  _BYTE v178[144]; // [rsp+1A10h] [rbp+1910h] BYREF
  _QWORD v179[10]; // [rsp+1AA0h] [rbp+19A0h] BYREF

  v0 = std::wstring::wstring(v83, &dword_1800DB714);
  v1 = std::wstring::wstring(v84, L"TpmRegDriverGroupPolicyData");
  v2 = std::wstring::wstring(v85, L"TPM");
  v3 = std::wstring::wstring(v86, L"Software\\Policies\\Microsoft");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v162, v3, v2, v1, 0, 131103, v0);
  v67 = 0;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v163,
    &v67,
    v162);
  v4 = std::wstring::wstring(v87, &dword_1800DB714);
  v5 = std::wstring::wstring(v88, &dword_1800DB714);
  v6 = std::wstring::wstring(v89, L"PcrInfo");
  v7 = std::wstring::wstring(v90, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v161, v7, v6, v5, 0, 131103, v4);
  v68 = 14;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v164,
    &v68,
    v161);
  v8 = std::wstring::wstring(v91, &dword_1800DB714);
  v9 = std::wstring::wstring(v92, L"TpmRegDriverTpm");
  v10 = std::wstring::wstring(v93, L"TPM");
  v11 = std::wstring::wstring(v94, L"System\\CurrentControlSet\\Services");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v160, v11, v10, v9, 0, 131103, v8);
  v69 = 1;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v165,
    &v69,
    v160);
  v12 = std::wstring::wstring(v95, &dword_1800DB714);
  v13 = std::wstring::wstring(v96, L"TpmRegPlatformQuoteKeysKey");
  v14 = std::wstring::wstring(v97, L"PlatformQuoteKeys");
  v15 = std::wstring::wstring(v98, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v159, v15, v14, v13, 0, 131103, v12);
  v70 = 2;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v166,
    &v70,
    v159);
  v16 = std::wstring::wstring(v99, &dword_1800DB714);
  v17 = std::wstring::wstring(v100, L"TpmRegProvisioningKey");
  v18 = std::wstring::wstring(v101, L"ProvisionInfo");
  v19 = std::wstring::wstring(v102, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v158, v19, v18, v17, 0, 131103, v16);
  v71 = 3;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v167,
    &v71,
    v158);
  v20 = std::wstring::wstring(
          v103,
          L"O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KA;;;LS)(A;CIIO;GA;;;LS)"
           "(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v21 = std::wstring::wstring(v104, L"TpmRegDriverPersistedData");
  v22 = std::wstring::wstring(v105, L"WMI");
  v23 = std::wstring::wstring(v106, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v157, v23, v22, v21, 0, 131103, v20);
  v72 = 4;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v168,
    &v72,
    v157);
  v24 = std::wstring::wstring(
          v107,
          L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v25 = std::wstring::wstring(v108, L"TpmRegDriverPersistedDataAdmin");
  v26 = std::wstring::wstring(v109, L"Admin");
  v27 = std::wstring::wstring(v110, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v156, v27, v26, v25, 0, 131103, v24);
  v73 = 5;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v169,
    &v73,
    v156);
  v28 = std::wstring::wstring(
          v111,
          L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CI"
           "IO;GA;;;NS)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KR;;;S-1-5-4)(A;CIIO;GR;;;S-1-5-4)(A;;KR;;;S-1-5-1"
           "1)(A;CIIO;GR;;;S-1-5-11)");
  v29 = std::wstring::wstring(v112, L"TpmRegDriverPersistedDataEndorsement");
  v30 = std::wstring::wstring(v113, L"Endorsement");
  v31 = std::wstring::wstring(v114, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v155, v31, v30, v29, 0, 131103, v28);
  v74 = 6;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v170,
    &v74,
    v155);
  v32 = std::wstring::wstring(v115, &dword_1800DB714);
  v33 = std::wstring::wstring(v116, L"TPMCoreProvisioningHealthCertStore");
  v34 = std::wstring::wstring(v117, L"Store");
  v35 = std::wstring::wstring(v118, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v154, v35, v34, v33, 0, 131103, v32);
  v75 = 7;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v171,
    &v75,
    v154);
  v36 = std::wstring::wstring(v119, &dword_1800DB714);
  v37 = std::wstring::wstring(v120, &dword_1800DB714);
  v38 = std::wstring::wstring(v121, L"TaskStates");
  v39 = std::wstring::wstring(v122, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v153, v39, v38, v37, 1, 131103, v36);
  v76 = 8;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v172,
    &v76,
    v153);
  v40 = std::wstring::wstring(v123, &dword_1800DB714);
  v41 = std::wstring::wstring(v124, &dword_1800DB714);
  v42 = std::wstring::wstring(v125, L"AttestationInfo");
  v43 = std::wstring::wstring(v126, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v152, v43, v42, v41, 1, 131103, v40);
  v77 = 9;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v173,
    &v77,
    v152);
  v44 = std::wstring::wstring(v127, &dword_1800DB714);
  v45 = std::wstring::wstring(v128, &dword_1800DB714);
  v46 = std::wstring::wstring(v129, L"Volatile-AIKCertEnroll-EXCLUSIVE");
  v47 = std::wstring::wstring(v130, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v151, v47, v46, v45, 1, 131103, v44);
  v78 = 10;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v174,
    &v78,
    v151);
  v48 = std::wstring::wstring(v131, &dword_1800DB714);
  v49 = std::wstring::wstring(v132, L"TPMCoreProvisioningEKCertificates");
  v50 = std::wstring::wstring(v133, L"EkCertStore");
  v51 = std::wstring::wstring(v134, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v150, v51, v50, v49, 0, 983103, v48);
  v79 = 11;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v175,
    &v79,
    v150);
  v52 = std::wstring::wstring(v135, &dword_1800DB714);
  v53 = std::wstring::wstring(v136, L"TPMCoreProvisioningEKCertificates");
  v54 = std::wstring::wstring(v137, L"EkCertStoreECC");
  v55 = std::wstring::wstring(v138, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v149, v55, v54, v53, 0, 983103, v52);
  v80 = 12;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v176,
    &v80,
    v149);
  v56 = std::wstring::wstring(v139, &dword_1800DB714);
  v57 = std::wstring::wstring(v140, L"TPMCoreProvisioningIntermediateCACerts");
  v58 = std::wstring::wstring(v141, L"IntermediateCACertStore");
  v59 = std::wstring::wstring(v142, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v148, v59, v58, v57, 0, 983103, v56);
  v81 = 13;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v177,
    &v81,
    v148);
  v60 = std::wstring::wstring(v143, &dword_1800DB714);
  v61 = std::wstring::wstring(v144, &dword_1800DB714);
  v62 = std::wstring::wstring(v145, &dword_1800DB714);
  v63 = std::wstring::wstring(v146, L"System\\CurrentControlSet\\Control\\IntegrityServices");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v147, v63, v62, v61, 0, 131097, v60);
  v82 = 15;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v178,
    &v82,
    v147);
  HWSecurityRegistryManager::m_RegKeyTable = 0;
  v64 = std::_Allocate<16,std::_Default_allocate_traits>(176);
  *(_QWORD *)v64 = v64;
  *(_QWORD *)(v64 + 8) = v64;
  *(_QWORD *)(v64 + 16) = v64;
  *(_WORD *)(v64 + 24) = 257;
  *(_QWORD *)&HWSecurityRegistryManager::m_RegKeyTable = v64;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Insert_range_unchecked<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const *,std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const *>(
    v65,
    v163,
    v179);
  `eh vector destructor iterator'(
    v163,
    0x90u,
    0x10u,
    std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v147);
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
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegKeyTable__);
}

```

## disassembly

```asm
0x180025810  push    rbp
0x180025812  push    rbx
0x180025813  push    rsi
0x180025814  push    rdi
0x180025815  push    r12
0x180025817  push    r13
0x180025819  push    r14
0x18002581b  push    r15
0x18002581d  lea     rbp, [rsp-19B8h]
0x180025825  mov     eax, 1AB8h
0x18002582a  call    _alloca_probe
0x18002582f  sub     rsp, rax
0x180025832  mov     rax, cs:__security_cookie
0x180025839  xor     rax, rsp
0x18002583c  mov     [rbp+19F0h+var_50], rax
0x180025843  lea     rax, [rbp+19F0h+var_1A50]
0x180025847  mov     [rsp+1AF0h+var_1AB0], rax
0x18002584c  lea     r12, dword_1800DB714
0x180025853  mov     rdx, r12
0x180025856  lea     rcx, [rbp+19F0h+var_1A50]
0x18002585a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002585f  mov     rsi, rax
0x180025862  lea     rax, [rbp+19F0h+var_1A30]
0x180025866  mov     [rsp+1AF0h+var_1AA8], rax
0x18002586b  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x180025872  lea     rcx, [rbp+19F0h+var_1A30]
0x180025876  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002587b  mov     rdi, rax
0x18002587e  lea     rax, [rbp+19F0h+var_1A10]
0x180025882  mov     [rsp+1AF0h+var_1AA0], rax
0x180025887  lea     rdx, aTpm; "TPM"
0x18002588e  lea     rcx, [rbp+19F0h+var_1A10]
0x180025892  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025897  mov     rbx, rax
0x18002589a  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft"
0x1800258a1  lea     rcx, [rbp+19F0h+var_19F0]
0x1800258a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800258aa  nop
0x1800258ab  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800258b0  mov     r15d, 2001Fh
0x1800258b6  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800258bb  xor     r13d, r13d
0x1800258be  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800258c3  mov     r9, rdi
0x1800258c6  mov     r8, rbx
0x1800258c9  mov     rdx, rax
0x1800258cc  lea     rcx, [rbp+19F0h+var_9E0]
0x1800258d3  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800258d8  nop
0x1800258d9  mov     [rsp+1AF0h+var_1A90], r13d
0x1800258de  lea     r8, [rbp+19F0h+var_9E0]
0x1800258e5  lea     rdx, [rsp+1AF0h+var_1A90]
0x1800258ea  lea     rcx, [rbp+19F0h+var_950]
0x1800258f1  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800258f6  nop
0x1800258f7  lea     rax, [rbp+19F0h+var_19D0]
0x1800258fb  mov     [rsp+1AF0h+var_1A98], rax
0x180025900  mov     rdx, r12
0x180025903  lea     rcx, [rbp+19F0h+var_19D0]
0x180025907  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002590c  mov     rsi, rax
0x18002590f  lea     rax, [rbp+19F0h+var_19B0]
0x180025913  mov     [rsp+1AF0h+var_1AA0], rax
0x180025918  mov     rdx, r12
0x18002591b  lea     rcx, [rbp+19F0h+var_19B0]
0x18002591f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025924  mov     rdi, rax
0x180025927  lea     rax, [rbp+19F0h+var_1990]
0x18002592b  mov     [rsp+1AF0h+var_1AA8], rax
0x180025930  lea     rdx, aPcrinfo_0; "PcrInfo"
0x180025937  lea     rcx, [rbp+19F0h+var_1990]
0x18002593b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025940  mov     rbx, rax
0x180025943  lea     r14, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\TP"...
0x18002594a  mov     rdx, r14
0x18002594d  lea     rcx, [rbp+19F0h+var_1970]
0x180025954  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025959  nop
0x18002595a  mov     [rsp+1AF0h+var_1AC0], rsi
0x18002595f  mov     [rsp+1AF0h+var_1AC8], r15d
0x180025964  mov     [rsp+1AF0h+var_1AD0], r13d
0x180025969  mov     r9, rdi
0x18002596c  mov     r8, rbx
0x18002596f  mov     rdx, rax
0x180025972  lea     rcx, [rbp+19F0h+var_A70]
0x180025979  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18002597e  nop
0x18002597f  mov     [rsp+1AF0h+var_1A8C], 0Eh
0x180025987  lea     r8, [rbp+19F0h+var_A70]
0x18002598e  lea     rdx, [rsp+1AF0h+var_1A8C]
0x180025993  lea     rcx, [rbp+19F0h+var_8C0]
0x18002599a  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18002599f  nop
0x1800259a0  lea     rax, [rbp+19F0h+var_1950]
0x1800259a7  mov     [rsp+1AF0h+var_1A98], rax
0x1800259ac  mov     rdx, r12
0x1800259af  lea     rcx, [rbp+19F0h+var_1950]
0x1800259b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800259bb  mov     rsi, rax
0x1800259be  lea     rax, [rbp+19F0h+var_1930]
0x1800259c5  mov     [rsp+1AF0h+var_1AA0], rax
0x1800259ca  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x1800259d1  lea     rcx, [rbp+19F0h+var_1930]
0x1800259d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800259dd  mov     rdi, rax
0x1800259e0  lea     rax, [rbp+19F0h+var_1910]
0x1800259e7  mov     [rsp+1AF0h+var_1AA8], rax
0x1800259ec  lea     rdx, aTpm; "TPM"
0x1800259f3  lea     rcx, [rbp+19F0h+var_1910]
0x1800259fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800259ff  mov     rbx, rax
0x180025a02  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Services"
0x180025a09  lea     rcx, [rbp+19F0h+var_18F0]
0x180025a10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025a15  nop
0x180025a16  mov     [rsp+1AF0h+var_1AC0], rsi
0x180025a1b  mov     [rsp+1AF0h+var_1AC8], r15d
0x180025a20  mov     [rsp+1AF0h+var_1AD0], r13d
0x180025a25  mov     r9, rdi
0x180025a28  mov     r8, rbx
0x180025a2b  mov     rdx, rax
0x180025a2e  lea     rcx, [rbp+19F0h+var_B00]
0x180025a35  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180025a3a  nop
0x180025a3b  lea     r12d, [r13+1]
0x180025a3f  mov     [rsp+1AF0h+var_1A88], r12d
0x180025a44  lea     r8, [rbp+19F0h+var_B00]
0x180025a4b  lea     rdx, [rsp+1AF0h+var_1A88]
0x180025a50  lea     rcx, [rbp+19F0h+var_830]
0x180025a57  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180025a5c  nop
0x180025a5d  lea     rax, [rbp+19F0h+var_18D0]
0x180025a64  mov     [rsp+1AF0h+var_1A98], rax
0x180025a69  lea     rdx, dword_1800DB714
0x180025a70  lea     rcx, [rbp+19F0h+var_18D0]
0x180025a77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025a7c  mov     rsi, rax
0x180025a7f  lea     rax, [rbp+19F0h+var_18B0]
0x180025a86  mov     [rsp+1AF0h+var_1AA0], rax
0x180025a8b  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180025a92  lea     rcx, [rbp+19F0h+var_18B0]
0x180025a99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025a9e  mov     rdi, rax
0x180025aa1  lea     rax, [rbp+19F0h+var_1890]
0x180025aa8  mov     [rsp+1AF0h+var_1AA8], rax
0x180025aad  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x180025ab4  lea     rcx, [rbp+19F0h+var_1890]
0x180025abb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025ac0  mov     rbx, rax
0x180025ac3  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\TP"...
0x180025aca  lea     rcx, [rbp+19F0h+var_1870]
0x180025ad1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025ad6  nop
0x180025ad7  mov     [rsp+1AF0h+var_1AC0], rsi
0x180025adc  mov     [rsp+1AF0h+var_1AC8], r15d
0x180025ae1  mov     [rsp+1AF0h+var_1AD0], r13d
0x180025ae6  mov     r9, rdi
0x180025ae9  mov     r8, rbx
0x180025aec  mov     rdx, rax
0x180025aef  lea     rcx, [rbp+19F0h+var_B90]
0x180025af6  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180025afb  nop
0x180025afc  mov     [rsp+1AF0h+var_1A84], 2
0x180025b04  lea     r8, [rbp+19F0h+var_B90]
0x180025b0b  lea     rdx, [rsp+1AF0h+var_1A84]
0x180025b10  lea     rcx, [rbp+19F0h+var_7A0]
0x180025b17  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180025b1c  nop
0x180025b1d  lea     rax, [rbp+19F0h+var_1850]
0x180025b24  mov     [rsp+1AF0h+var_1A98], rax
0x180025b29  lea     rdx, dword_1800DB714
0x180025b30  lea     rcx, [rbp+19F0h+var_1850]
0x180025b37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025b3c  mov     rsi, rax
0x180025b3f  lea     rax, [rbp+19F0h+var_1830]
0x180025b46  mov     [rsp+1AF0h+var_1AA0], rax
0x180025b4b  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x180025b52  lea     rcx, [rbp+19F0h+var_1830]
0x180025b59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025b5e  mov     rdi, rax
0x180025b61  lea     rax, [rbp+19F0h+var_1810]
0x180025b68  mov     [rsp+1AF0h+var_1AA8], rax
0x180025b6d  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180025b74  lea     rcx, [rbp+19F0h+var_1810]
0x180025b7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025b80  mov     rbx, rax
0x180025b83  mov     rdx, r14
0x180025b86  lea     rcx, [rbp+19F0h+var_17F0]
0x180025b8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025b92  nop
0x180025b93  mov     [rsp+1AF0h+var_1AC0], rsi
0x180025b98  mov     [rsp+1AF0h+var_1AC8], r15d
0x180025b9d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180025ba2  mov     r9, rdi
0x180025ba5  mov     r8, rbx
0x180025ba8  mov     rdx, rax
0x180025bab  lea     rcx, [rbp+19F0h+var_C20]
0x180025bb2  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180025bb7  nop
0x180025bb8  mov     [rsp+1AF0h+var_1A80], 3
0x180025bc0  lea     r8, [rbp+19F0h+var_C20]
0x180025bc7  lea     rdx, [rsp+1AF0h+var_1A80]
0x180025bcc  lea     rcx, [rbp+19F0h+var_710]
0x180025bd3  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180025bd8  nop
0x180025bd9  lea     rax, [rbp+19F0h+var_17D0]
0x180025be0  mov     [rsp+1AF0h+var_1A98], rax
0x180025be5  lea     rdx, aOSydAiarAKrAuA; "O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)("...
0x180025bec  lea     rcx, [rbp+19F0h+var_17D0]
0x180025bf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025bf8  mov     rsi, rax
0x180025bfb  lea     rax, [rbp+19F0h+var_17B0]
0x180025c02  mov     [rsp+1AF0h+var_1AA0], rax
0x180025c07  lea     rdx, aTpmregdriverpe_3; "TpmRegDriverPersistedData"
0x180025c0e  lea     rcx, [rbp+19F0h+var_17B0]
0x180025c15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025c1a  mov     rdi, rax
0x180025c1d  lea     rax, [rbp+19F0h+var_1790]
0x180025c24  mov     [rsp+1AF0h+var_1AA8], rax
0x180025c29  lea     rdx, aWmi; "WMI"
0x180025c30  lea     rcx, [rbp+19F0h+var_1790]
0x180025c37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025c3c  mov     rbx, rax
0x180025c3f  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\TP"...
0x180025c46  lea     rcx, [rbp+19F0h+var_1770]
0x180025c4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025c52  nop
0x180025c53  mov     [rsp+1AF0h+var_1AC0], rsi
0x180025c58  mov     [rsp+1AF0h+var_1AC8], r15d
0x180025c5d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180025c62  mov     r9, rdi
0x180025c65  mov     r8, rbx
0x180025c68  mov     rdx, rax
0x180025c6b  lea     rcx, [rbp+19F0h+var_CB0]
0x180025c72  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180025c77  nop
0x180025c78  mov     [rsp+1AF0h+var_1A7C], 4
0x180025c80  lea     r8, [rbp+19F0h+var_CB0]
0x180025c87  lea     rdx, [rsp+1AF0h+var_1A7C]
0x180025c8c  lea     rcx, [rbp+19F0h+var_680]
0x180025c93  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180025c98  nop
0x180025c99  lea     rax, [rbp+19F0h+var_1750]
0x180025ca0  mov     [rsp+1AF0h+var_1A98], rax
0x180025ca5  lea     rdx, aOSydPaiAKaBaAC; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x180025cac  lea     rcx, [rbp+19F0h+var_1750]
0x180025cb3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025cb8  mov     rsi, rax
0x180025cbb  lea     rax, [rbp+19F0h+var_1730]
0x180025cc2  mov     [rsp+1AF0h+var_1AA0], rax
0x180025cc7  lea     rdx, aTpmregdriverpe_4; "TpmRegDriverPersistedDataAdmin"
0x180025cce  lea     rcx, [rbp+19F0h+var_1730]
0x180025cd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025cda  mov     rdi, rax
0x180025cdd  lea     rax, [rbp+19F0h+var_1710]
0x180025ce4  mov     [rsp+1AF0h+var_1AA8], rax
0x180025ce9  lea     rdx, aAdmin; "Admin"
0x180025cf0  lea     rcx, [rbp+19F0h+var_1710]
0x180025cf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025cfc  mov     rbx, rax
0x180025cff  mov     rdx, r14
0x180025d02  lea     rcx, [rbp+19F0h+var_16F0]
0x180025d09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025d0e  nop
0x180025d0f  mov     [rsp+1AF0h+var_1AC0], rsi
0x180025d14  mov     [rsp+1AF0h+var_1AC8], r15d
0x180025d19  mov     [rsp+1AF0h+var_1AD0], r13d
0x180025d1e  mov     r9, rdi
0x180025d21  mov     r8, rbx
0x180025d24  mov     rdx, rax
0x180025d27  lea     rcx, [rbp+19F0h+var_D40]
0x180025d2e  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180025d33  nop
0x180025d34  mov     [rsp+1AF0h+var_1A78], 5
0x180025d3c  lea     r8, [rbp+19F0h+var_D40]
0x180025d43  lea     rdx, [rsp+1AF0h+var_1A78]
0x180025d48  lea     rcx, [rbp+19F0h+var_5F0]
0x180025d4f  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180025d54  nop
0x180025d55  lea     rax, [rbp+19F0h+var_16D0]
0x180025d5c  mov     [rsp+1AF0h+var_1A98], rax
0x180025d61  lea     rdx, aOSydPaiAKaBaAC_0; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x180025d68  lea     rcx, [rbp+19F0h+var_16D0]
0x180025d6f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025d74  mov     rsi, rax
0x180025d77  lea     rax, [rbp+19F0h+var_16B0]
0x180025d7e  mov     [rsp+1AF0h+var_1AA0], rax
0x180025d83  lea     rdx, aTpmregdriverpe_5; "TpmRegDriverPersistedDataEndorsement"
0x180025d8a  lea     rcx, [rbp+19F0h+var_16B0]
0x180025d91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025d96  mov     rdi, rax
0x180025d99  lea     rax, [rbp+19F0h+var_1690]
0x180025da0  mov     [rsp+1AF0h+var_1AA8], rax
0x180025da5  lea     rdx, aEndorsement; "Endorsement"
0x180025dac  lea     rcx, [rbp+19F0h+var_1690]
0x180025db3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025db8  mov     rbx, rax
0x180025dbb  mov     rdx, r14
0x180025dbe  lea     rcx, [rbp+19F0h+var_1670]
0x180025dc5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
