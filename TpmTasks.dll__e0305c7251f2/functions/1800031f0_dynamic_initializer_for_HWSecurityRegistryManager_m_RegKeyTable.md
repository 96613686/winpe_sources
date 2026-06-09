# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x1800031f0`
- end: `0x180003f49`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `3417`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800031f0`
- `0x1800078b0`
- `0x180007968`
- `0x180007dc4`
- `0x18000bbe4`
- `0x18000d524`
- `0x1800421e8`
- `0x18004237c`
- `0x180042c88`
- `0x180042f40`
- `0x180059200`

## string_xrefs

- `0x180003323`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x1800039cf`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`
- `0x1800033e2`: `System\CurrentControlSet\Services`
- `0x1800034a3`: `System\CurrentControlSet\Services\TPM`
- `0x18000361f`: `System\CurrentControlSet\Services\TPM`
- `0x1800038ff`: `TaskStates`
- `0x180003857`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x180003b47`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x180003d7d`: `System\CurrentControlSet\Control\IntegrityServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__()
{
  __int64 v0; // rsi
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rsi
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rsi
  __int64 v33; // rdi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rsi
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rsi
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rdi
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rsi
  __int64 v49; // rdi
  __int64 v50; // rbx
  __int64 v51; // rax
  __int64 v52; // rsi
  __int64 v53; // rdi
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rsi
  __int64 v57; // rdi
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rsi
  __int64 v61; // rdi
  __int64 v62; // rbx
  __int64 v63; // rax
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

  v0 = std::wstring::wstring((__int64)v84, (__int64)&sourceString);
  v1 = std::wstring::wstring((__int64)v85, (__int64)L"TpmRegDriverGroupPolicyData");
  v2 = std::wstring::wstring((__int64)v86, (__int64)L"TPM");
  v3 = std::wstring::wstring((__int64)v87, (__int64)L"Software\\Policies\\Microsoft");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v163, v3, v2, v1, 0, 131103, v0);
  v68 = 0;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v164,
    &v68,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v163);
  v4 = std::wstring::wstring((__int64)v88, (__int64)&sourceString);
  v5 = std::wstring::wstring((__int64)v89, (__int64)&sourceString);
  v6 = std::wstring::wstring((__int64)v90, (__int64)L"PcrInfo");
  v7 = std::wstring::wstring((__int64)v91, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v162, v7, v6, v5, 0, 131103, v4);
  v69 = 14;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v165,
    &v69,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v162);
  v8 = std::wstring::wstring((__int64)v92, (__int64)&sourceString);
  v9 = std::wstring::wstring((__int64)v93, (__int64)L"TpmRegDriverTpm");
  v10 = std::wstring::wstring((__int64)v94, (__int64)L"TPM");
  v11 = std::wstring::wstring((__int64)v95, (__int64)L"System\\CurrentControlSet\\Services");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v161, v11, v10, v9, 0, 131103, v8);
  v70 = 1;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v166,
    &v70,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v161);
  v12 = std::wstring::wstring((__int64)v96, (__int64)&sourceString);
  v13 = std::wstring::wstring((__int64)v97, (__int64)L"TpmRegPlatformQuoteKeysKey");
  v14 = std::wstring::wstring((__int64)v98, (__int64)L"PlatformQuoteKeys");
  v15 = std::wstring::wstring((__int64)v99, (__int64)L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v160, v15, v14, v13, 0, 131103, v12);
  v71 = 2;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v167,
    &v71,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v160);
  v16 = std::wstring::wstring((__int64)v100, (__int64)&sourceString);
  v17 = std::wstring::wstring((__int64)v101, (__int64)L"TpmRegProvisioningKey");
  v18 = std::wstring::wstring((__int64)v102, (__int64)L"ProvisionInfo");
  v19 = std::wstring::wstring((__int64)v103, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v159, v19, v18, v17, 0, 131103, v16);
  v72 = 3;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v168,
    &v72,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v159);
  v20 = std::wstring::wstring(
          (__int64)v104,
          (__int64)L"O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KA;;;LS)(A;CIIO"
                    ";GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v21 = std::wstring::wstring((__int64)v105, (__int64)L"TpmRegDriverPersistedData");
  v22 = std::wstring::wstring((__int64)v106, (__int64)L"WMI");
  v23 = std::wstring::wstring((__int64)v107, (__int64)L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v158, v23, v22, v21, 0, 131103, v20);
  v73 = 4;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v169,
    &v73,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v158);
  v24 = std::wstring::wstring(
          (__int64)v108,
          (__int64)L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;"
                    ";NS)(A;CIIO;GA;;;NS)");
  v25 = std::wstring::wstring((__int64)v109, (__int64)L"TpmRegDriverPersistedDataAdmin");
  v26 = std::wstring::wstring((__int64)v110, (__int64)L"Admin");
  v27 = std::wstring::wstring((__int64)v111, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v157, v27, v26, v25, 0, 131103, v24);
  v74 = 5;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v170,
    &v74,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v157);
  v28 = std::wstring::wstring(
          (__int64)v112,
          (__int64)L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;"
                    ";NS)(A;CIIO;GA;;;NS)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KR;;;S-1-5-4)(A;CIIO;GR;;;S-1-5-"
                    "4)(A;;KR;;;S-1-5-11)(A;CIIO;GR;;;S-1-5-11)");
  v29 = std::wstring::wstring((__int64)v113, (__int64)L"TpmRegDriverPersistedDataEndorsement");
  v30 = std::wstring::wstring((__int64)v114, (__int64)L"Endorsement");
  v31 = std::wstring::wstring((__int64)v115, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v156, v31, v30, v29, 0, 131103, v28);
  v75 = 6;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v171,
    &v75,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v156);
  v32 = std::wstring::wstring((__int64)v116, (__int64)&sourceString);
  v33 = std::wstring::wstring((__int64)v117, (__int64)L"TPMCoreProvisioningHealthCertStore");
  v34 = std::wstring::wstring((__int64)v118, (__int64)L"Store");
  v35 = std::wstring::wstring((__int64)v119, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v155, v35, v34, v33, 0, 131103, v32);
  v76 = 7;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v172,
    &v76,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v155);
  v36 = std::wstring::wstring((__int64)v120, (__int64)&sourceString);
  v37 = std::wstring::wstring((__int64)v121, (__int64)&sourceString);
  v38 = std::wstring::wstring((__int64)v122, (__int64)L"TaskStates");
  v39 = std::wstring::wstring((__int64)v123, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v154, v39, v38, v37, 1, 131103, v36);
  v77 = 8;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v173,
    &v77,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v154);
  v40 = std::wstring::wstring((__int64)v124, (__int64)&sourceString);
  v41 = std::wstring::wstring((__int64)v125, (__int64)&sourceString);
  v42 = std::wstring::wstring((__int64)v126, (__int64)L"AttestationInfo");
  v43 = std::wstring::wstring((__int64)v127, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v153, v43, v42, v41, 1, 131103, v40);
  v78 = 9;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v174,
    &v78,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v153);
  v44 = std::wstring::wstring((__int64)v128, (__int64)&sourceString);
  v45 = std::wstring::wstring((__int64)v129, (__int64)&sourceString);
  v46 = std::wstring::wstring((__int64)v130, (__int64)L"Volatile-AIKCertEnroll-EXCLUSIVE");
  v47 = std::wstring::wstring((__int64)v131, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v152, v47, v46, v45, 1, 131103, v44);
  v79 = 10;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v175,
    &v79,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v152);
  v48 = std::wstring::wstring((__int64)v132, (__int64)&sourceString);
  v49 = std::wstring::wstring((__int64)v133, (__int64)L"TPMCoreProvisioningEKCertificates");
  v50 = std::wstring::wstring((__int64)v134, (__int64)L"EkCertStore");
  v51 = std::wstring::wstring((__int64)v135, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v151, v51, v50, v49, 0, 983103, v48);
  v80 = 11;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v176,
    &v80,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v151);
  v52 = std::wstring::wstring((__int64)v136, (__int64)&sourceString);
  v53 = std::wstring::wstring((__int64)v137, (__int64)L"TPMCoreProvisioningEKCertificates");
  v54 = std::wstring::wstring((__int64)v138, (__int64)L"EkCertStoreECC");
  v55 = std::wstring::wstring((__int64)v139, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v150, v55, v54, v53, 0, 983103, v52);
  v81 = 12;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v177,
    &v81,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v150);
  v56 = std::wstring::wstring((__int64)v140, (__int64)&sourceString);
  v57 = std::wstring::wstring((__int64)v141, (__int64)L"TPMCoreProvisioningIntermediateCACerts");
  v58 = std::wstring::wstring((__int64)v142, (__int64)L"IntermediateCACertStore");
  v59 = std::wstring::wstring((__int64)v143, (__int64)L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v149, v59, v58, v57, 0, 983103, v56);
  v82 = 13;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v178,
    &v82,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v149);
  v60 = std::wstring::wstring((__int64)v144, (__int64)&sourceString);
  v61 = std::wstring::wstring((__int64)v145, (__int64)&sourceString);
  v62 = std::wstring::wstring((__int64)v146, (__int64)&sourceString);
  v63 = std::wstring::wstring((__int64)v147, (__int64)L"System\\CurrentControlSet\\Control\\IntegrityServices");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v148, v63, v62, v61, 0, 131097, v60);
  v83 = 15;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v179,
    &v83,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v148);
  HWSecurityRegistryManager::m_RegKeyTable = 0;
  v65 = std::_Allocate<16,std::_Default_allocate_traits>(0xB0u);
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
    (void (*)(void *))std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>);
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
0x1800031f0  push    rbp
0x1800031f2  push    rbx
0x1800031f3  push    rsi
0x1800031f4  push    rdi
0x1800031f5  push    r12
0x1800031f7  push    r13
0x1800031f9  push    r14
0x1800031fb  push    r15
0x1800031fd  lea     rbp, [rsp-19B8h]
0x180003205  mov     eax, 1AB8h
0x18000320a  call    _alloca_probe
0x18000320f  sub     rsp, rax
0x180003212  mov     rax, cs:__security_cookie
0x180003219  xor     rax, rsp
0x18000321c  mov     [rbp+19F0h+var_50], rax
0x180003223  lea     rax, [rbp+19F0h+var_1A50]
0x180003227  mov     [rsp+1AF0h+var_1AB0], rax
0x18000322c  lea     r12, sourceString
0x180003233  mov     rdx, r12
0x180003236  lea     rcx, [rbp+19F0h+var_1A50]
0x18000323a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000323f  mov     rsi, rax
0x180003242  lea     rax, [rbp+19F0h+var_1A30]
0x180003246  mov     [rsp+1AF0h+var_1AA8], rax
0x18000324b  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x180003252  lea     rcx, [rbp+19F0h+var_1A30]
0x180003256  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000325b  mov     rdi, rax
0x18000325e  lea     rax, [rbp+19F0h+var_1A10]
0x180003262  mov     [rsp+1AF0h+var_1AA0], rax
0x180003267  lea     rdx, aTpm; "TPM"
0x18000326e  lea     rcx, [rbp+19F0h+var_1A10]
0x180003272  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003277  mov     rbx, rax
0x18000327a  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft"
0x180003281  lea     rcx, [rbp+19F0h+var_19F0]
0x180003285  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000328a  nop
0x18000328b  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003290  mov     r15d, 2001Fh
0x180003296  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000329b  xor     r13d, r13d
0x18000329e  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800032a3  mov     r9, rdi
0x1800032a6  mov     r8, rbx
0x1800032a9  mov     rdx, rax
0x1800032ac  lea     rcx, [rbp+19F0h+var_9E0]
0x1800032b3  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800032b8  nop
0x1800032b9  mov     [rsp+1AF0h+var_1A90], r13d
0x1800032be  lea     r8, [rbp+19F0h+var_9E0]
0x1800032c5  lea     rdx, [rsp+1AF0h+var_1A90]
0x1800032ca  lea     rcx, [rbp+19F0h+var_950]
0x1800032d1  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800032d6  nop
0x1800032d7  lea     rax, [rbp+19F0h+var_19D0]
0x1800032db  mov     [rsp+1AF0h+var_1A98], rax
0x1800032e0  mov     rdx, r12
0x1800032e3  lea     rcx, [rbp+19F0h+var_19D0]
0x1800032e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800032ec  mov     rsi, rax
0x1800032ef  lea     rax, [rbp+19F0h+var_19B0]
0x1800032f3  mov     [rsp+1AF0h+var_1AA0], rax
0x1800032f8  mov     rdx, r12
0x1800032fb  lea     rcx, [rbp+19F0h+var_19B0]
0x1800032ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003304  mov     rdi, rax
0x180003307  lea     rax, [rbp+19F0h+var_1990]
0x18000330b  mov     [rsp+1AF0h+var_1AA8], rax
0x180003310  lea     rdx, aPcrinfo; "PcrInfo"
0x180003317  lea     rcx, [rbp+19F0h+var_1990]
0x18000331b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003320  mov     rbx, rax
0x180003323  lea     r14, aSystemCurrentc; "System\\CurrentControlSet\\Services\\TP"...
0x18000332a  mov     rdx, r14
0x18000332d  lea     rcx, [rbp+19F0h+var_1970]
0x180003334  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003339  nop
0x18000333a  mov     [rsp+1AF0h+var_1AC0], rsi
0x18000333f  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003344  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003349  mov     r9, rdi
0x18000334c  mov     r8, rbx
0x18000334f  mov     rdx, rax
0x180003352  lea     rcx, [rbp+19F0h+var_A70]
0x180003359  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000335e  nop
0x18000335f  mov     [rsp+1AF0h+var_1A8C], 0Eh
0x180003367  lea     r8, [rbp+19F0h+var_A70]
0x18000336e  lea     rdx, [rsp+1AF0h+var_1A8C]
0x180003373  lea     rcx, [rbp+19F0h+var_8C0]
0x18000337a  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18000337f  nop
0x180003380  lea     rax, [rbp+19F0h+var_1950]
0x180003387  mov     [rsp+1AF0h+var_1A98], rax
0x18000338c  mov     rdx, r12
0x18000338f  lea     rcx, [rbp+19F0h+var_1950]
0x180003396  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000339b  mov     rsi, rax
0x18000339e  lea     rax, [rbp+19F0h+var_1930]
0x1800033a5  mov     [rsp+1AF0h+var_1AA0], rax
0x1800033aa  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x1800033b1  lea     rcx, [rbp+19F0h+var_1930]
0x1800033b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800033bd  mov     rdi, rax
0x1800033c0  lea     rax, [rbp+19F0h+var_1910]
0x1800033c7  mov     [rsp+1AF0h+var_1AA8], rax
0x1800033cc  lea     rdx, aTpm; "TPM"
0x1800033d3  lea     rcx, [rbp+19F0h+var_1910]
0x1800033da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800033df  mov     rbx, rax
0x1800033e2  lea     rdx, aSystemCurrentc_21; "System\\CurrentControlSet\\Services"
0x1800033e9  lea     rcx, [rbp+19F0h+var_18F0]
0x1800033f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800033f5  nop
0x1800033f6  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800033fb  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003400  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003405  mov     r9, rdi
0x180003408  mov     r8, rbx
0x18000340b  mov     rdx, rax
0x18000340e  lea     rcx, [rbp+19F0h+var_B00]
0x180003415  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000341a  nop
0x18000341b  lea     r12d, [r13+1]
0x18000341f  mov     [rsp+1AF0h+var_1A88], r12d
0x180003424  lea     r8, [rbp+19F0h+var_B00]
0x18000342b  lea     rdx, [rsp+1AF0h+var_1A88]
0x180003430  lea     rcx, [rbp+19F0h+var_830]
0x180003437  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18000343c  nop
0x18000343d  lea     rax, [rbp+19F0h+var_18D0]
0x180003444  mov     [rsp+1AF0h+var_1A98], rax
0x180003449  lea     rdx, sourceString
0x180003450  lea     rcx, [rbp+19F0h+var_18D0]
0x180003457  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000345c  mov     rsi, rax
0x18000345f  lea     rax, [rbp+19F0h+var_18B0]
0x180003466  mov     [rsp+1AF0h+var_1AA0], rax
0x18000346b  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180003472  lea     rcx, [rbp+19F0h+var_18B0]
0x180003479  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000347e  mov     rdi, rax
0x180003481  lea     rax, [rbp+19F0h+var_1890]
0x180003488  mov     [rsp+1AF0h+var_1AA8], rax
0x18000348d  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x180003494  lea     rcx, [rbp+19F0h+var_1890]
0x18000349b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800034a0  mov     rbx, rax
0x1800034a3  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\TP"...
0x1800034aa  lea     rcx, [rbp+19F0h+var_1870]
0x1800034b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800034b6  nop
0x1800034b7  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800034bc  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800034c1  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800034c6  mov     r9, rdi
0x1800034c9  mov     r8, rbx
0x1800034cc  mov     rdx, rax
0x1800034cf  lea     rcx, [rbp+19F0h+var_B90]
0x1800034d6  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800034db  nop
0x1800034dc  mov     [rsp+1AF0h+var_1A84], 2
0x1800034e4  lea     r8, [rbp+19F0h+var_B90]
0x1800034eb  lea     rdx, [rsp+1AF0h+var_1A84]
0x1800034f0  lea     rcx, [rbp+19F0h+var_7A0]
0x1800034f7  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800034fc  nop
0x1800034fd  lea     rax, [rbp+19F0h+var_1850]
0x180003504  mov     [rsp+1AF0h+var_1A98], rax
0x180003509  lea     rdx, sourceString
0x180003510  lea     rcx, [rbp+19F0h+var_1850]
0x180003517  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000351c  mov     rsi, rax
0x18000351f  lea     rax, [rbp+19F0h+var_1830]
0x180003526  mov     [rsp+1AF0h+var_1AA0], rax
0x18000352b  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x180003532  lea     rcx, [rbp+19F0h+var_1830]
0x180003539  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000353e  mov     rdi, rax
0x180003541  lea     rax, [rbp+19F0h+var_1810]
0x180003548  mov     [rsp+1AF0h+var_1AA8], rax
0x18000354d  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180003554  lea     rcx, [rbp+19F0h+var_1810]
0x18000355b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003560  mov     rbx, rax
0x180003563  mov     rdx, r14
0x180003566  lea     rcx, [rbp+19F0h+var_17F0]
0x18000356d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003572  nop
0x180003573  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003578  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000357d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003582  mov     r9, rdi
0x180003585  mov     r8, rbx
0x180003588  mov     rdx, rax
0x18000358b  lea     rcx, [rbp+19F0h+var_C20]
0x180003592  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003597  nop
0x180003598  mov     [rsp+1AF0h+var_1A80], 3
0x1800035a0  lea     r8, [rbp+19F0h+var_C20]
0x1800035a7  lea     rdx, [rsp+1AF0h+var_1A80]
0x1800035ac  lea     rcx, [rbp+19F0h+var_710]
0x1800035b3  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800035b8  nop
0x1800035b9  lea     rax, [rbp+19F0h+var_17D0]
0x1800035c0  mov     [rsp+1AF0h+var_1A98], rax
0x1800035c5  lea     rdx, aOSydAiarAKrAuA; "O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)("...
0x1800035cc  lea     rcx, [rbp+19F0h+var_17D0]
0x1800035d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800035d8  mov     rsi, rax
0x1800035db  lea     rax, [rbp+19F0h+var_17B0]
0x1800035e2  mov     [rsp+1AF0h+var_1AA0], rax
0x1800035e7  lea     rdx, aTpmregdriverpe_0; "TpmRegDriverPersistedData"
0x1800035ee  lea     rcx, [rbp+19F0h+var_17B0]
0x1800035f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800035fa  mov     rdi, rax
0x1800035fd  lea     rax, [rbp+19F0h+var_1790]
0x180003604  mov     [rsp+1AF0h+var_1AA8], rax
0x180003609  lea     rdx, aWmi; "WMI"
0x180003610  lea     rcx, [rbp+19F0h+var_1790]
0x180003617  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000361c  mov     rbx, rax
0x18000361f  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\TP"...
0x180003626  lea     rcx, [rbp+19F0h+var_1770]
0x18000362d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003632  nop
0x180003633  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003638  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000363d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003642  mov     r9, rdi
0x180003645  mov     r8, rbx
0x180003648  mov     rdx, rax
0x18000364b  lea     rcx, [rbp+19F0h+var_CB0]
0x180003652  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003657  nop
0x180003658  mov     [rsp+1AF0h+var_1A7C], 4
0x180003660  lea     r8, [rbp+19F0h+var_CB0]
0x180003667  lea     rdx, [rsp+1AF0h+var_1A7C]
0x18000366c  lea     rcx, [rbp+19F0h+var_680]
0x180003673  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003678  nop
0x180003679  lea     rax, [rbp+19F0h+var_1750]
0x180003680  mov     [rsp+1AF0h+var_1A98], rax
0x180003685  lea     rdx, aOSydPaiAKaBaAC; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x18000368c  lea     rcx, [rbp+19F0h+var_1750]
0x180003693  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003698  mov     rsi, rax
0x18000369b  lea     rax, [rbp+19F0h+var_1730]
0x1800036a2  mov     [rsp+1AF0h+var_1AA0], rax
0x1800036a7  lea     rdx, aTpmregdriverpe_1; "TpmRegDriverPersistedDataAdmin"
0x1800036ae  lea     rcx, [rbp+19F0h+var_1730]
0x1800036b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800036ba  mov     rdi, rax
0x1800036bd  lea     rax, [rbp+19F0h+var_1710]
0x1800036c4  mov     [rsp+1AF0h+var_1AA8], rax
0x1800036c9  lea     rdx, aAdmin; "Admin"
0x1800036d0  lea     rcx, [rbp+19F0h+var_1710]
0x1800036d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800036dc  mov     rbx, rax
0x1800036df  mov     rdx, r14
0x1800036e2  lea     rcx, [rbp+19F0h+var_16F0]
0x1800036e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800036ee  nop
0x1800036ef  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800036f4  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800036f9  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800036fe  mov     r9, rdi
0x180003701  mov     r8, rbx
0x180003704  mov     rdx, rax
0x180003707  lea     rcx, [rbp+19F0h+var_D40]
0x18000370e  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003713  nop
0x180003714  mov     [rsp+1AF0h+var_1A78], 5
0x18000371c  lea     r8, [rbp+19F0h+var_D40]
0x180003723  lea     rdx, [rsp+1AF0h+var_1A78]
0x180003728  lea     rcx, [rbp+19F0h+var_5F0]
0x18000372f  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003734  nop
0x180003735  lea     rax, [rbp+19F0h+var_16D0]
0x18000373c  mov     [rsp+1AF0h+var_1A98], rax
0x180003741  lea     rdx, aOSydPaiAKaBaAC_0; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x180003748  lea     rcx, [rbp+19F0h+var_16D0]
0x18000374f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003754  mov     rsi, rax
0x180003757  lea     rax, [rbp+19F0h+var_16B0]
0x18000375e  mov     [rsp+1AF0h+var_1AA0], rax
0x180003763  lea     rdx, aTpmregdriverpe_2; "TpmRegDriverPersistedDataEndorsement"
0x18000376a  lea     rcx, [rbp+19F0h+var_16B0]
0x180003771  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003776  mov     rdi, rax
0x180003779  lea     rax, [rbp+19F0h+var_1690]
0x180003780  mov     [rsp+1AF0h+var_1AA8], rax
0x180003785  lea     rdx, aEndorsement; "Endorsement"
0x18000378c  lea     rcx, [rbp+19F0h+var_1690]
0x180003793  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003798  mov     rbx, rax
0x18000379b  mov     rdx, r14
0x18000379e  lea     rcx, [rbp+19F0h+var_1670]
0x1800037a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
