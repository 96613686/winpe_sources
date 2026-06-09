# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x1800041e0`
- end: `0x180004f39`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `3417`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800041e0`
- `0x180007670`
- `0x180007a20`
- `0x180007d4c`
- `0x180008f0c`
- `0x180017d70`
- `0x180083344`
- `0x180083394`
- `0x180083b74`
- `0x180083e30`
- `0x1800842b0`

## string_xrefs

- `0x180004313`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x1800043d2`: `System\CurrentControlSet\Services`
- `0x180004493`: `System\CurrentControlSet\Services\TPM`
- `0x18000460f`: `System\CurrentControlSet\Services\TPM`
- `0x1800049bf`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`
- `0x180004847`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x1800048ef`: `TaskStates`
- `0x180004b37`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x180004d6d`: `System\CurrentControlSet\Control\IntegrityServices`

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
  _QWORD *v65; // rdi
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
  _DWORD v164[36]; // [rsp+11A0h] [rbp+10A0h] BYREF
  _DWORD v165[36]; // [rsp+1230h] [rbp+1130h] BYREF
  _DWORD v166[36]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _DWORD v167[36]; // [rsp+1350h] [rbp+1250h] BYREF
  _DWORD v168[36]; // [rsp+13E0h] [rbp+12E0h] BYREF
  _DWORD v169[36]; // [rsp+1470h] [rbp+1370h] BYREF
  _DWORD v170[36]; // [rsp+1500h] [rbp+1400h] BYREF
  _DWORD v171[36]; // [rsp+1590h] [rbp+1490h] BYREF
  _DWORD v172[36]; // [rsp+1620h] [rbp+1520h] BYREF
  _DWORD v173[36]; // [rsp+16B0h] [rbp+15B0h] BYREF
  _DWORD v174[36]; // [rsp+1740h] [rbp+1640h] BYREF
  _DWORD v175[36]; // [rsp+17D0h] [rbp+16D0h] BYREF
  _DWORD v176[36]; // [rsp+1860h] [rbp+1760h] BYREF
  _DWORD v177[36]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _DWORD v178[36]; // [rsp+1980h] [rbp+1880h] BYREF
  _DWORD v179[36]; // [rsp+1A10h] [rbp+1910h] BYREF
  __int64 v180; // [rsp+1AA0h] [rbp+19A0h] BYREF

  v0 = std::wstring::wstring(v84, &LocaleName);
  v1 = std::wstring::wstring(v85, L"TpmRegDriverGroupPolicyData");
  v2 = std::wstring::wstring(v86, L"TPM");
  v3 = std::wstring::wstring(v87, L"Software\\Policies\\Microsoft");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v163, v3, v2, v1, 0, 131103, v0);
  v68 = 0;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v164,
    &v68,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v163);
  v4 = std::wstring::wstring(v88, &LocaleName);
  v5 = std::wstring::wstring(v89, &LocaleName);
  v6 = std::wstring::wstring(v90, L"PcrInfo");
  v7 = std::wstring::wstring(v91, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v162, v7, v6, v5, 0, 131103, v4);
  v69 = 14;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v165,
    &v69,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v162);
  v8 = std::wstring::wstring(v92, &LocaleName);
  v9 = std::wstring::wstring(v93, L"TpmRegDriverTpm");
  v10 = std::wstring::wstring(v94, L"TPM");
  v11 = std::wstring::wstring(v95, L"System\\CurrentControlSet\\Services");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v161, v11, v10, v9, 0, 131103, v8);
  v70 = 1;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v166,
    &v70,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v161);
  v12 = std::wstring::wstring(v96, &LocaleName);
  v13 = std::wstring::wstring(v97, L"TpmRegPlatformQuoteKeysKey");
  v14 = std::wstring::wstring(v98, L"PlatformQuoteKeys");
  v15 = std::wstring::wstring(v99, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v160, v15, v14, v13, 0, 131103, v12);
  v71 = 2;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v167,
    &v71,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v160);
  v16 = std::wstring::wstring(v100, &LocaleName);
  v17 = std::wstring::wstring(v101, L"TpmRegProvisioningKey");
  v18 = std::wstring::wstring(v102, L"ProvisionInfo");
  v19 = std::wstring::wstring(v103, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v159, v19, v18, v17, 0, 131103, v16);
  v72 = 3;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v168,
    &v72,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v159);
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
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v158);
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
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v157);
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
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v156);
  v32 = std::wstring::wstring(v116, &LocaleName);
  v33 = std::wstring::wstring(v117, L"TPMCoreProvisioningHealthCertStore");
  v34 = std::wstring::wstring(v118, L"Store");
  v35 = std::wstring::wstring(v119, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v155, v35, v34, v33, 0, 131103, v32);
  v76 = 7;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v172,
    &v76,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v155);
  v36 = std::wstring::wstring(v120, &LocaleName);
  v37 = std::wstring::wstring(v121, &LocaleName);
  v38 = std::wstring::wstring(v122, L"TaskStates");
  v39 = std::wstring::wstring(v123, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v154, v39, v38, v37, 1, 131103, v36);
  v77 = 8;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v173,
    &v77,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v154);
  v40 = std::wstring::wstring(v124, &LocaleName);
  v41 = std::wstring::wstring(v125, &LocaleName);
  v42 = std::wstring::wstring(v126, L"AttestationInfo");
  v43 = std::wstring::wstring(v127, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v153, v43, v42, v41, 1, 131103, v40);
  v78 = 9;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v174,
    &v78,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v153);
  v44 = std::wstring::wstring(v128, &LocaleName);
  v45 = std::wstring::wstring(v129, &LocaleName);
  v46 = std::wstring::wstring(v130, L"Volatile-AIKCertEnroll-EXCLUSIVE");
  v47 = std::wstring::wstring(v131, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v152, v47, v46, v45, 1, 131103, v44);
  v79 = 10;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v175,
    &v79,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v152);
  v48 = std::wstring::wstring(v132, &LocaleName);
  v49 = std::wstring::wstring(v133, L"TPMCoreProvisioningEKCertificates");
  v50 = std::wstring::wstring(v134, L"EkCertStore");
  v51 = std::wstring::wstring(v135, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v151, v51, v50, v49, 0, 983103, v48);
  v80 = 11;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v176,
    &v80,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v151);
  v52 = std::wstring::wstring(v136, &LocaleName);
  v53 = std::wstring::wstring(v137, L"TPMCoreProvisioningEKCertificates");
  v54 = std::wstring::wstring(v138, L"EkCertStoreECC");
  v55 = std::wstring::wstring(v139, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v150, v55, v54, v53, 0, 983103, v52);
  v81 = 12;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v177,
    &v81,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v150);
  v56 = std::wstring::wstring(v140, &LocaleName);
  v57 = std::wstring::wstring(v141, L"TPMCoreProvisioningIntermediateCACerts");
  v58 = std::wstring::wstring(v142, L"IntermediateCACertStore");
  v59 = std::wstring::wstring(v143, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v149, v59, v58, v57, 0, 983103, v56);
  v82 = 13;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v178,
    &v82,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v149);
  v60 = std::wstring::wstring(v144, &LocaleName);
  v61 = std::wstring::wstring(v145, &LocaleName);
  v62 = std::wstring::wstring(v146, &LocaleName);
  v63 = std::wstring::wstring(v147, L"System\\CurrentControlSet\\Control\\IntegrityServices");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((unsigned int)v148, v63, v62, v61, 0, 131097, v60);
  v83 = 15;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v179,
    &v83,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v148);
  HWSecurityRegistryManager::m_RegKeyTable = 0;
  v65 = operator new(0xB0u);
  *v65 = v65;
  v65[1] = v65;
  v65[2] = v65;
  *((_WORD *)v65 + 12) = 257;
  *(_QWORD *)&HWSecurityRegistryManager::m_RegKeyTable = v65;
  v66 = (__int64 *)v164;
  do
  {
    std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Emplace_hint<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(
      v64,
      (__int64)v65,
      (__int64)v66);
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
0x1800041e0  push    rbp
0x1800041e2  push    rbx
0x1800041e3  push    rsi
0x1800041e4  push    rdi
0x1800041e5  push    r12
0x1800041e7  push    r13
0x1800041e9  push    r14
0x1800041eb  push    r15
0x1800041ed  lea     rbp, [rsp-19B8h]
0x1800041f5  mov     eax, 1AB8h
0x1800041fa  call    _alloca_probe
0x1800041ff  sub     rsp, rax
0x180004202  mov     rax, cs:__security_cookie
0x180004209  xor     rax, rsp
0x18000420c  mov     [rbp+19F0h+var_50], rax
0x180004213  lea     rax, [rbp+19F0h+var_1A50]
0x180004217  mov     [rsp+1AF0h+var_1AB0], rax
0x18000421c  lea     r12, LocaleName
0x180004223  mov     rdx, r12
0x180004226  lea     rcx, [rbp+19F0h+var_1A50]
0x18000422a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000422f  mov     rsi, rax
0x180004232  lea     rax, [rbp+19F0h+var_1A30]
0x180004236  mov     [rsp+1AF0h+var_1AA8], rax
0x18000423b  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x180004242  lea     rcx, [rbp+19F0h+var_1A30]
0x180004246  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000424b  mov     rdi, rax
0x18000424e  lea     rax, [rbp+19F0h+var_1A10]
0x180004252  mov     [rsp+1AF0h+var_1AA0], rax
0x180004257  lea     rdx, aTpm; "TPM"
0x18000425e  lea     rcx, [rbp+19F0h+var_1A10]
0x180004262  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004267  mov     rbx, rax
0x18000426a  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft"
0x180004271  lea     rcx, [rbp+19F0h+var_19F0]
0x180004275  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000427a  nop
0x18000427b  mov     [rsp+1AF0h+var_1AC0], rsi
0x180004280  mov     r15d, 2001Fh
0x180004286  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000428b  xor     r13d, r13d
0x18000428e  mov     [rsp+1AF0h+var_1AD0], r13d
0x180004293  mov     r9, rdi
0x180004296  mov     r8, rbx
0x180004299  mov     rdx, rax
0x18000429c  lea     rcx, [rbp+19F0h+var_9E0]
0x1800042a3  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800042a8  nop
0x1800042a9  mov     [rsp+1AF0h+var_1A90], r13d
0x1800042ae  lea     r8, [rbp+19F0h+var_9E0]
0x1800042b5  lea     rdx, [rsp+1AF0h+var_1A90]
0x1800042ba  lea     rcx, [rbp+19F0h+var_950]
0x1800042c1  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800042c6  nop
0x1800042c7  lea     rax, [rbp+19F0h+var_19D0]
0x1800042cb  mov     [rsp+1AF0h+var_1A98], rax
0x1800042d0  mov     rdx, r12
0x1800042d3  lea     rcx, [rbp+19F0h+var_19D0]
0x1800042d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800042dc  mov     rsi, rax
0x1800042df  lea     rax, [rbp+19F0h+var_19B0]
0x1800042e3  mov     [rsp+1AF0h+var_1AA0], rax
0x1800042e8  mov     rdx, r12
0x1800042eb  lea     rcx, [rbp+19F0h+var_19B0]
0x1800042ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800042f4  mov     rdi, rax
0x1800042f7  lea     rax, [rbp+19F0h+var_1990]
0x1800042fb  mov     [rsp+1AF0h+var_1AA8], rax
0x180004300  lea     rdx, aPcrinfo; "PcrInfo"
0x180004307  lea     rcx, [rbp+19F0h+var_1990]
0x18000430b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004310  mov     rbx, rax
0x180004313  lea     r14, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\TP"...
0x18000431a  mov     rdx, r14
0x18000431d  lea     rcx, [rbp+19F0h+var_1970]
0x180004324  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004329  nop
0x18000432a  mov     [rsp+1AF0h+var_1AC0], rsi
0x18000432f  mov     [rsp+1AF0h+var_1AC8], r15d
0x180004334  mov     [rsp+1AF0h+var_1AD0], r13d
0x180004339  mov     r9, rdi
0x18000433c  mov     r8, rbx
0x18000433f  mov     rdx, rax
0x180004342  lea     rcx, [rbp+19F0h+var_A70]
0x180004349  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000434e  nop
0x18000434f  mov     [rsp+1AF0h+var_1A8C], 0Eh
0x180004357  lea     r8, [rbp+19F0h+var_A70]
0x18000435e  lea     rdx, [rsp+1AF0h+var_1A8C]
0x180004363  lea     rcx, [rbp+19F0h+var_8C0]
0x18000436a  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18000436f  nop
0x180004370  lea     rax, [rbp+19F0h+var_1950]
0x180004377  mov     [rsp+1AF0h+var_1A98], rax
0x18000437c  mov     rdx, r12
0x18000437f  lea     rcx, [rbp+19F0h+var_1950]
0x180004386  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000438b  mov     rsi, rax
0x18000438e  lea     rax, [rbp+19F0h+var_1930]
0x180004395  mov     [rsp+1AF0h+var_1AA0], rax
0x18000439a  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x1800043a1  lea     rcx, [rbp+19F0h+var_1930]
0x1800043a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800043ad  mov     rdi, rax
0x1800043b0  lea     rax, [rbp+19F0h+var_1910]
0x1800043b7  mov     [rsp+1AF0h+var_1AA8], rax
0x1800043bc  lea     rdx, aTpm; "TPM"
0x1800043c3  lea     rcx, [rbp+19F0h+var_1910]
0x1800043ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800043cf  mov     rbx, rax
0x1800043d2  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services"
0x1800043d9  lea     rcx, [rbp+19F0h+var_18F0]
0x1800043e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800043e5  nop
0x1800043e6  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800043eb  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800043f0  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800043f5  mov     r9, rdi
0x1800043f8  mov     r8, rbx
0x1800043fb  mov     rdx, rax
0x1800043fe  lea     rcx, [rbp+19F0h+var_B00]
0x180004405  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000440a  nop
0x18000440b  lea     r12d, [r13+1]
0x18000440f  mov     [rsp+1AF0h+var_1A88], r12d
0x180004414  lea     r8, [rbp+19F0h+var_B00]
0x18000441b  lea     rdx, [rsp+1AF0h+var_1A88]
0x180004420  lea     rcx, [rbp+19F0h+var_830]
0x180004427  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18000442c  nop
0x18000442d  lea     rax, [rbp+19F0h+var_18D0]
0x180004434  mov     [rsp+1AF0h+var_1A98], rax
0x180004439  lea     rdx, LocaleName
0x180004440  lea     rcx, [rbp+19F0h+var_18D0]
0x180004447  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000444c  mov     rsi, rax
0x18000444f  lea     rax, [rbp+19F0h+var_18B0]
0x180004456  mov     [rsp+1AF0h+var_1AA0], rax
0x18000445b  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180004462  lea     rcx, [rbp+19F0h+var_18B0]
0x180004469  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000446e  mov     rdi, rax
0x180004471  lea     rax, [rbp+19F0h+var_1890]
0x180004478  mov     [rsp+1AF0h+var_1AA8], rax
0x18000447d  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x180004484  lea     rcx, [rbp+19F0h+var_1890]
0x18000448b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004490  mov     rbx, rax
0x180004493  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\TP"...
0x18000449a  lea     rcx, [rbp+19F0h+var_1870]
0x1800044a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800044a6  nop
0x1800044a7  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800044ac  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800044b1  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800044b6  mov     r9, rdi
0x1800044b9  mov     r8, rbx
0x1800044bc  mov     rdx, rax
0x1800044bf  lea     rcx, [rbp+19F0h+var_B90]
0x1800044c6  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800044cb  nop
0x1800044cc  mov     [rsp+1AF0h+var_1A84], 2
0x1800044d4  lea     r8, [rbp+19F0h+var_B90]
0x1800044db  lea     rdx, [rsp+1AF0h+var_1A84]
0x1800044e0  lea     rcx, [rbp+19F0h+var_7A0]
0x1800044e7  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800044ec  nop
0x1800044ed  lea     rax, [rbp+19F0h+var_1850]
0x1800044f4  mov     [rsp+1AF0h+var_1A98], rax
0x1800044f9  lea     rdx, LocaleName
0x180004500  lea     rcx, [rbp+19F0h+var_1850]
0x180004507  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000450c  mov     rsi, rax
0x18000450f  lea     rax, [rbp+19F0h+var_1830]
0x180004516  mov     [rsp+1AF0h+var_1AA0], rax
0x18000451b  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x180004522  lea     rcx, [rbp+19F0h+var_1830]
0x180004529  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000452e  mov     rdi, rax
0x180004531  lea     rax, [rbp+19F0h+var_1810]
0x180004538  mov     [rsp+1AF0h+var_1AA8], rax
0x18000453d  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180004544  lea     rcx, [rbp+19F0h+var_1810]
0x18000454b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004550  mov     rbx, rax
0x180004553  mov     rdx, r14
0x180004556  lea     rcx, [rbp+19F0h+var_17F0]
0x18000455d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004562  nop
0x180004563  mov     [rsp+1AF0h+var_1AC0], rsi
0x180004568  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000456d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180004572  mov     r9, rdi
0x180004575  mov     r8, rbx
0x180004578  mov     rdx, rax
0x18000457b  lea     rcx, [rbp+19F0h+var_C20]
0x180004582  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004587  nop
0x180004588  mov     [rsp+1AF0h+var_1A80], 3
0x180004590  lea     r8, [rbp+19F0h+var_C20]
0x180004597  lea     rdx, [rsp+1AF0h+var_1A80]
0x18000459c  lea     rcx, [rbp+19F0h+var_710]
0x1800045a3  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800045a8  nop
0x1800045a9  lea     rax, [rbp+19F0h+var_17D0]
0x1800045b0  mov     [rsp+1AF0h+var_1A98], rax
0x1800045b5  lea     rdx, aOSydAiarAKrAuA; "O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)("...
0x1800045bc  lea     rcx, [rbp+19F0h+var_17D0]
0x1800045c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800045c8  mov     rsi, rax
0x1800045cb  lea     rax, [rbp+19F0h+var_17B0]
0x1800045d2  mov     [rsp+1AF0h+var_1AA0], rax
0x1800045d7  lea     rdx, aTpmregdriverpe; "TpmRegDriverPersistedData"
0x1800045de  lea     rcx, [rbp+19F0h+var_17B0]
0x1800045e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800045ea  mov     rdi, rax
0x1800045ed  lea     rax, [rbp+19F0h+var_1790]
0x1800045f4  mov     [rsp+1AF0h+var_1AA8], rax
0x1800045f9  lea     rdx, aWmi; "WMI"
0x180004600  lea     rcx, [rbp+19F0h+var_1790]
0x180004607  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000460c  mov     rbx, rax
0x18000460f  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\TP"...
0x180004616  lea     rcx, [rbp+19F0h+var_1770]
0x18000461d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004622  nop
0x180004623  mov     [rsp+1AF0h+var_1AC0], rsi
0x180004628  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000462d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180004632  mov     r9, rdi
0x180004635  mov     r8, rbx
0x180004638  mov     rdx, rax
0x18000463b  lea     rcx, [rbp+19F0h+var_CB0]
0x180004642  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004647  nop
0x180004648  mov     [rsp+1AF0h+var_1A7C], 4
0x180004650  lea     r8, [rbp+19F0h+var_CB0]
0x180004657  lea     rdx, [rsp+1AF0h+var_1A7C]
0x18000465c  lea     rcx, [rbp+19F0h+var_680]
0x180004663  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004668  nop
0x180004669  lea     rax, [rbp+19F0h+var_1750]
0x180004670  mov     [rsp+1AF0h+var_1A98], rax
0x180004675  lea     rdx, aOSydPaiAKaBaAC; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x18000467c  lea     rcx, [rbp+19F0h+var_1750]
0x180004683  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004688  mov     rsi, rax
0x18000468b  lea     rax, [rbp+19F0h+var_1730]
0x180004692  mov     [rsp+1AF0h+var_1AA0], rax
0x180004697  lea     rdx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x18000469e  lea     rcx, [rbp+19F0h+var_1730]
0x1800046a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800046aa  mov     rdi, rax
0x1800046ad  lea     rax, [rbp+19F0h+var_1710]
0x1800046b4  mov     [rsp+1AF0h+var_1AA8], rax
0x1800046b9  lea     rdx, aAdmin; "Admin"
0x1800046c0  lea     rcx, [rbp+19F0h+var_1710]
0x1800046c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800046cc  mov     rbx, rax
0x1800046cf  mov     rdx, r14
0x1800046d2  lea     rcx, [rbp+19F0h+var_16F0]
0x1800046d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800046de  nop
0x1800046df  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800046e4  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800046e9  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800046ee  mov     r9, rdi
0x1800046f1  mov     r8, rbx
0x1800046f4  mov     rdx, rax
0x1800046f7  lea     rcx, [rbp+19F0h+var_D40]
0x1800046fe  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004703  nop
0x180004704  mov     [rsp+1AF0h+var_1A78], 5
0x18000470c  lea     r8, [rbp+19F0h+var_D40]
0x180004713  lea     rdx, [rsp+1AF0h+var_1A78]
0x180004718  lea     rcx, [rbp+19F0h+var_5F0]
0x18000471f  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004724  nop
0x180004725  lea     rax, [rbp+19F0h+var_16D0]
0x18000472c  mov     [rsp+1AF0h+var_1A98], rax
0x180004731  lea     rdx, aOSydPaiAKaBaAC_0; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x180004738  lea     rcx, [rbp+19F0h+var_16D0]
0x18000473f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004744  mov     rsi, rax
0x180004747  lea     rax, [rbp+19F0h+var_16B0]
0x18000474e  mov     [rsp+1AF0h+var_1AA0], rax
0x180004753  lea     rdx, aTpmregdriverpe_1; "TpmRegDriverPersistedDataEndorsement"
0x18000475a  lea     rcx, [rbp+19F0h+var_16B0]
0x180004761  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004766  mov     rdi, rax
0x180004769  lea     rax, [rbp+19F0h+var_1690]
0x180004770  mov     [rsp+1AF0h+var_1AA8], rax
0x180004775  lea     rdx, aEndorsement; "Endorsement"
0x18000477c  lea     rcx, [rbp+19F0h+var_1690]
0x180004783  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004788  mov     rbx, rax
0x18000478b  mov     rdx, r14
0x18000478e  lea     rcx, [rbp+19F0h+var_1670]
0x180004795  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
