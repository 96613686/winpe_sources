# Windows::Internal::AssignedAccess::_dynamic_initializer_for__c_defaultLocalGroupPolicyConfiguration__

- ea: `0x1800037a0`
- end: `0x180003d5f`
- name: `Windows::Internal::AssignedAccess::_dynamic_initializer_for__c_defaultLocalGroupPolicyConfiguration__`
- size: `1471`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006640`
- `0x1800069f0`
- `0x180013f14`
- `0x18003bf88`
- `0x18003d530`
- `0x18003d558`
- `0x18003d588`
- `0x18003d5b8`
- `0x18003d5e8`
- `0x18003d618`
- `0x18003d640`
- `0x18003d724`

## string_xrefs

- `0x180003812`: `NoUninstallFromStart`
- `0x180003866`: `NoPinningToTaskbar`
- `0x180003a03`: `LockTaskbar`
- `0x1800039ee`: `TaskbarLockAll`
- `0x180003a1f`: `TaskbarNoRedock`
- `0x180003a11`: `TaskbarNoAddRemoveToolbar`
- `0x180003a3b`: `TaskbarNoResize`
- `0x180003a2d`: `TaskbarNoDragToolbar`
- `0x180003a57`: `TaskbarNoPinnedList`
- `0x180003a73`: `TaskbarNoNotification`
- `0x180003b80`: `HideTaskViewButton`
- `0x180003a81`: `NoBalloonFeatureAdvertisements`

## pseudocode

```c
int Windows::Internal::AssignedAccess::_dynamic_initializer_for__c_defaultLocalGroupPolicyConfiguration__()
{
  int v0; // r11d
  int v1; // r10d
  int v2; // edx
  __int64 v3; // rax
  int v4; // r11d
  int v5; // r10d
  int v6; // edx
  int v7; // r8d
  __int64 v8; // rax
  int v9; // r11d
  int v10; // r10d
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rax
  int v14; // r11d
  int v15; // r10d
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rax
  int v19; // r11d
  int v20; // r10d
  int v21; // edx
  int v22; // r8d
  __int64 v23; // rax
  int v24; // r11d
  int v25; // r10d
  int v26; // edx
  int v27; // r8d
  __int64 v28; // rax
  int v29; // r11d
  int v30; // r10d
  int v31; // edx
  __int64 v32; // rax
  int v33; // edx
  __int64 v34; // rax
  int v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+34h] [rbp-CCh] BYREF
  int v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+3Ch] [rbp-C4h] BYREF
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+44h] [rbp-BCh] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+4Ch] [rbp-B4h] BYREF
  int v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+54h] [rbp-ACh] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+5Ch] [rbp-A4h] BYREF
  int v48; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+64h] [rbp-9Ch] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  int v51; // [rsp+6Ch] [rbp-94h] BYREF
  _DWORD v52[2]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v53; // [rsp+78h] [rbp-88h]
  const wchar_t *v54; // [rsp+80h] [rbp-80h]
  __int128 v55; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v56[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v57; // [rsp+B0h] [rbp-50h] BYREF
  char v58; // [rsp+C8h] [rbp-38h] BYREF
  char v59; // [rsp+E0h] [rbp-20h] BYREF
  char v60; // [rsp+F8h] [rbp-8h] BYREF
  char v61; // [rsp+110h] [rbp+10h] BYREF
  char v62; // [rsp+128h] [rbp+28h] BYREF
  char v63; // [rsp+140h] [rbp+40h] BYREF
  char v64; // [rsp+158h] [rbp+58h] BYREF
  _DWORD v65[2]; // [rsp+170h] [rbp+70h] BYREF
  const wchar_t *v66; // [rsp+178h] [rbp+78h]
  const wchar_t *v67; // [rsp+180h] [rbp+80h]
  int v68; // [rsp+188h] [rbp+88h]
  int v69; // [rsp+18Ch] [rbp+8Ch]
  const wchar_t *v70; // [rsp+190h] [rbp+90h]
  const wchar_t *v71; // [rsp+198h] [rbp+98h]
  int v72; // [rsp+1A0h] [rbp+A0h]
  int v73; // [rsp+1A4h] [rbp+A4h]
  const wchar_t *v74; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v75; // [rsp+1B0h] [rbp+B0h]
  int v76; // [rsp+1B8h] [rbp+B8h]
  int v77; // [rsp+1BCh] [rbp+BCh]
  const wchar_t *v78; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v79; // [rsp+1C8h] [rbp+C8h]
  int v80; // [rsp+1D0h] [rbp+D0h]
  int v81; // [rsp+1D4h] [rbp+D4h]
  const wchar_t *v82; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v83; // [rsp+1E0h] [rbp+E0h]
  int v84; // [rsp+1E8h] [rbp+E8h]
  int v85; // [rsp+1ECh] [rbp+ECh]
  const wchar_t *v86; // [rsp+1F0h] [rbp+F0h]
  const wchar_t *v87; // [rsp+1F8h] [rbp+F8h]
  int v88; // [rsp+200h] [rbp+100h]
  int v89; // [rsp+204h] [rbp+104h]
  const wchar_t *v90; // [rsp+208h] [rbp+108h]
  const wchar_t *v91; // [rsp+210h] [rbp+110h]
  int v92; // [rsp+218h] [rbp+118h]
  int v93; // [rsp+21Ch] [rbp+11Ch]
  const wchar_t *v94; // [rsp+220h] [rbp+120h]
  const wchar_t *v95; // [rsp+228h] [rbp+128h]
  int v96; // [rsp+230h] [rbp+130h]
  int v97; // [rsp+234h] [rbp+134h]
  const wchar_t *v98; // [rsp+238h] [rbp+138h]
  const wchar_t *v99; // [rsp+240h] [rbp+140h]
  int v100; // [rsp+248h] [rbp+148h]
  int v101; // [rsp+24Ch] [rbp+14Ch]
  const wchar_t *v102; // [rsp+250h] [rbp+150h]
  const wchar_t *v103; // [rsp+258h] [rbp+158h]
  int v104; // [rsp+260h] [rbp+160h]
  int v105; // [rsp+264h] [rbp+164h]
  const wchar_t *v106; // [rsp+268h] [rbp+168h]
  const wchar_t *v107; // [rsp+270h] [rbp+170h]
  int v108; // [rsp+278h] [rbp+178h]
  int v109; // [rsp+27Ch] [rbp+17Ch]
  const wchar_t *v110; // [rsp+280h] [rbp+180h]
  const wchar_t *v111; // [rsp+288h] [rbp+188h]
  int v112; // [rsp+290h] [rbp+190h]
  int v113; // [rsp+294h] [rbp+194h]
  const wchar_t *v114; // [rsp+298h] [rbp+198h]
  const wchar_t *v115; // [rsp+2A0h] [rbp+1A0h]
  int v116; // [rsp+2A8h] [rbp+1A8h]
  int v117; // [rsp+2ACh] [rbp+1ACh]
  const wchar_t *v118; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v119; // [rsp+2B8h] [rbp+1B8h]
  int v120; // [rsp+2C0h] [rbp+1C0h]
  int v121; // [rsp+2C4h] [rbp+1C4h]
  const wchar_t *v122; // [rsp+2C8h] [rbp+1C8h]
  const wchar_t *v123; // [rsp+2D0h] [rbp+1D0h]
  int v124; // [rsp+2D8h] [rbp+1D8h]
  int v125; // [rsp+2DCh] [rbp+1DCh]
  const wchar_t *v126; // [rsp+2E0h] [rbp+1E0h]
  const wchar_t *v127; // [rsp+2E8h] [rbp+1E8h]
  int v128; // [rsp+2F0h] [rbp+1F0h]
  int v129; // [rsp+2F4h] [rbp+1F4h]
  const wchar_t *v130; // [rsp+2F8h] [rbp+1F8h]
  const wchar_t *v131; // [rsp+300h] [rbp+200h]
  int v132; // [rsp+308h] [rbp+208h]
  int v133; // [rsp+30Ch] [rbp+20Ch]
  const wchar_t *v134; // [rsp+310h] [rbp+210h]
  const wchar_t *v135; // [rsp+318h] [rbp+218h]
  int v136; // [rsp+320h] [rbp+220h]
  int v137; // [rsp+324h] [rbp+224h]
  const wchar_t *v138; // [rsp+328h] [rbp+228h]
  const wchar_t *v139; // [rsp+330h] [rbp+230h]
  int v140; // [rsp+338h] [rbp+238h]
  int v141; // [rsp+33Ch] [rbp+23Ch]
  const wchar_t *v142; // [rsp+340h] [rbp+240h]
  const wchar_t *v143; // [rsp+348h] [rbp+248h]
  int v144; // [rsp+350h] [rbp+250h]
  int v145; // [rsp+354h] [rbp+254h]
  const wchar_t *v146; // [rsp+358h] [rbp+258h]
  const wchar_t *v147; // [rsp+360h] [rbp+260h]
  int v148; // [rsp+368h] [rbp+268h]
  int v149; // [rsp+36Ch] [rbp+26Ch]
  const wchar_t *v150; // [rsp+370h] [rbp+270h]
  const wchar_t *v151; // [rsp+378h] [rbp+278h]
  int v152; // [rsp+380h] [rbp+280h]
  int v153; // [rsp+384h] [rbp+284h]
  const wchar_t *v154; // [rsp+388h] [rbp+288h]
  const wchar_t *v155; // [rsp+390h] [rbp+290h]
  int v156; // [rsp+398h] [rbp+298h]
  int v157; // [rsp+39Ch] [rbp+29Ch]
  const wchar_t *v158; // [rsp+3A0h] [rbp+2A0h]
  const wchar_t *v159; // [rsp+3A8h] [rbp+2A8h]
  int v160; // [rsp+3B0h] [rbp+2B0h]
  int v161; // [rsp+3B4h] [rbp+2B4h]
  const wchar_t *v162; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v163; // [rsp+3C0h] [rbp+2C0h]
  _BYTE v164[24]; // [rsp+3C8h] [rbp+2C8h] BYREF
  _BYTE v165[24]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v166[24]; // [rsp+3F8h] [rbp+2F8h] BYREF
  _BYTE v167[24]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v168[24]; // [rsp+428h] [rbp+328h] BYREF
  _BYTE v169[24]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v170[24]; // [rsp+458h] [rbp+358h] BYREF
  _BYTE v171[24]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v172[24]; // [rsp+488h] [rbp+388h] BYREF
  __int64 v173; // [rsp+4A0h] [rbp+3A0h] BYREF

  v65[0] = 1;
  v65[1] = 0x7FFFFFFF;
  v67 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v66 = L"NoTrayContextMenu";
  v70 = L"ClearRecentDocsOnExit";
  v74 = L"NoChangeStartMenu";
  v78 = L"NoUninstallFromStart";
  v82 = L"NoMoreProgramsList";
  v86 = L"NoRun";
  v90 = L"NoDesktop";
  v94 = L"EnableLegacyBalloonNotifications";
  v98 = L"NoPinningToDestinations";
  v102 = L"NoPinningToTaskbar";
  v106 = L"NoRemoteDestinations";
  v110 = L"DisableNotificationCenter";
  v114 = L"DisableControlCenter";
  v118 = L"AlwaysShowNotificationIcon";
  v122 = L"TurnOffAbbreviatedDateTimeFormat";
  v68 = 1;
  v69 = 0x7FFFFFFF;
  v71 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v72 = 1;
  v73 = 0x7FFFFFFF;
  v75 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v76 = 1;
  v77 = 0x7FFFFFFF;
  v79 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v80 = 1;
  v81 = 0x7FFFFFFF;
  v83 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v84 = 1;
  v85 = 0x7FFFFFFF;
  v87 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v88 = 1;
  v89 = 0x7FFFFFFF;
  v91 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v92 = 1;
  v93 = 0x7FFFFFFF;
  v95 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v96 = 1;
  v97 = 0x7FFFFFFF;
  v99 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v100 = 1;
  v101 = 0x7FFFFFFF;
  v103 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v104 = 1;
  v105 = 0x7FFFFFFF;
  v107 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v108 = 1;
  v109 = 0x7FFFFFFF;
  v111 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v112 = 1;
  v113 = 0x7FFFFFFF;
  v115 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v116 = 1;
  v117 = 0x7FFFFFFF;
  v119 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v120 = 1;
  v121 = 0x7FFFFFFF;
  v123 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v124 = 1;
  v125 = 0x7FFFFFFF;
  v127 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v126 = L"TaskbarLockAll";
  v130 = L"LockTaskbar";
  v134 = L"TaskbarNoAddRemoveToolbar";
  v138 = L"TaskbarNoRedock";
  v142 = L"TaskbarNoDragToolbar";
  v146 = L"TaskbarNoResize";
  v150 = L"NoFrequentUsedPrograms";
  v154 = L"TaskbarNoPinnedList";
  v158 = L"HideSCAHealth";
  v162 = L"TaskbarNoNotification";
  v131 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v135 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v139 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v143 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v147 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v151 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v155 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v159 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v163 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer";
  v54 = L"Software\\Policies\\Microsoft\\Windows\\Explorer";
  v53 = L"NoBalloonFeatureAdvertisements";
  v128 = 1;
  v129 = 0x7FFFFFFF;
  v132 = 1;
  v133 = 0x7FFFFFFF;
  v136 = 1;
  v137 = 0x7FFFFFFF;
  v140 = 1;
  v141 = 0x7FFFFFFF;
  v144 = 1;
  v145 = 0x7FFFFFFF;
  v148 = 1;
  v149 = 0x7FFFFFFF;
  v152 = 1;
  v153 = 103;
  v156 = 1;
  v157 = 0x7FFFFFFF;
  v160 = 1;
  v161 = 0x7FFFFFFF;
  v52[0] = 1;
  v52[1] = 0x7FFFFFFF;
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v164,
    (__int64)v52);
  v36 = v0;
  v37 = v1;
  v3 = std::make_tuple<unsigned short const (&)[45],unsigned short const (&)[19],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
         (unsigned int)&v57,
         v2,
         (unsigned int)L"HideTaskViewButton",
         (unsigned int)&v37,
         (__int64)&v36);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v165,
    v3);
  v38 = v4;
  v39 = v5;
  v8 = std::make_tuple<unsigned short const (&)[51],unsigned short const (&)[22],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
         (unsigned int)&v58,
         v6,
         v7,
         (unsigned int)&v39,
         (__int64)&v38);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v166,
    v8);
  v40 = v9;
  v41 = v10;
  v13 = std::make_tuple<unsigned short const (&)[69],unsigned short const (&)[31],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
          (unsigned int)&v59,
          v11,
          v12,
          (unsigned int)&v41,
          (__int64)&v40);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v167,
    v13);
  v42 = v14;
  v43 = v15;
  v18 = std::make_tuple<unsigned short const (&)[58],unsigned short const (&)[15],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
          (unsigned int)&v60,
          v16,
          v17,
          (unsigned int)&v43,
          (__int64)&v42);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v168,
    v18);
  v44 = v19;
  v45 = v20;
  v23 = std::make_tuple<unsigned short const (&)[58],unsigned short const (&)[22],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
          (unsigned int)&v61,
          v21,
          v22,
          (unsigned int)&v45,
          (__int64)&v44);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v169,
    v23);
  v46 = v24;
  v47 = v25;
  v28 = std::make_tuple<unsigned short const (&)[60],unsigned short const (&)[9],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
          (unsigned int)&v62,
          v26,
          v27,
          (unsigned int)&v47,
          (__int64)&v46);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v170,
    v28);
  v48 = v29;
  v49 = v30;
  v32 = std::make_tuple<unsigned short const (&)[60],unsigned short const (&)[23],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
          (unsigned int)&v63,
          v31,
          (unsigned int)L"NoNetConnectDisconnect",
          (unsigned int)&v49,
          (__int64)&v48);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v171,
    v32);
  v50 = 0x3FFFFFF;
  v51 = 3;
  v34 = std::make_tuple<unsigned short const (&)[60],unsigned short const (&)[23],enum Windows::Internal::AssignedAccess::DefinitionVersion,int>(
          (unsigned int)&v64,
          v33,
          (unsigned int)L"NoViewOnDrive",
          (unsigned int)&v51,
          (__int64)&v50);
  std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>(
    (__int64)v172,
    v34);
  v55 = *(_OWORD *)std::initializer_list<std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>>::initializer_list<std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>>(
                     v56,
                     v65,
                     &v173);
  std::vector<std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>>::vector<std::tuple<unsigned short const *,unsigned short const *,enum Windows::Internal::AssignedAccess::DefinitionVersion,unsigned long>>(
    Windows::Internal::AssignedAccess::c_defaultLocalGroupPolicyConfiguration,
    &v55);
  return atexit(Windows::Internal::AssignedAccess::_dynamic_atexit_destructor_for__c_defaultLocalGroupPolicyConfiguration__);
}

```

## disassembly

```asm
0x1800037a0  push    rbp
0x1800037a2  lea     rbp, [rsp-3B0h]
0x1800037aa  sub     rsp, 4B0h
0x1800037b1  mov     rax, cs:__security_cookie
0x1800037b8  xor     rax, rsp
0x1800037bb  mov     [rbp+3B0h+var_10], rax
0x1800037c2  mov     r11d, 1
0x1800037c8  lea     rcx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\Windows"...
0x1800037cf  mov     r10d, 7FFFFFFFh
0x1800037d5  mov     [rbp+3B0h+var_340], r11d
0x1800037d9  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800037e0  mov     [rbp+3B0h+var_33C], r10d
0x1800037e4  lea     rax, aNotraycontextm; "NoTrayContextMenu"
0x1800037eb  mov     [rbp+3B0h+var_330], rdx
0x1800037f2  mov     [rbp+3B0h+var_338], rax
0x1800037f6  lea     rax, aClearrecentdoc; "ClearRecentDocsOnExit"
0x1800037fd  mov     [rbp+3B0h+var_320], rax
0x180003804  lea     rax, aNochangestartm; "NoChangeStartMenu"
0x18000380b  mov     [rbp+3B0h+var_308], rax
0x180003812  lea     rax, aNouninstallfro; "NoUninstallFromStart"
0x180003819  mov     [rbp+3B0h+var_2F0], rax
0x180003820  lea     rax, aNomoreprograms; "NoMoreProgramsList"
0x180003827  mov     [rbp+3B0h+var_2D8], rax
0x18000382e  lea     rax, aNorun; "NoRun"
0x180003835  mov     [rbp+3B0h+var_2C0], rax
0x18000383c  lea     rax, aNodesktop; "NoDesktop"
0x180003843  mov     [rbp+3B0h+var_2A8], rax
0x18000384a  lea     rax, aEnablelegacyba; "EnableLegacyBalloonNotifications"
0x180003851  mov     [rbp+3B0h+var_290], rax
0x180003858  lea     rax, aNopinningtodes; "NoPinningToDestinations"
0x18000385f  mov     [rbp+3B0h+var_278], rax
0x180003866  lea     rax, aNopinningtotas; "NoPinningToTaskbar"
0x18000386d  mov     [rbp+3B0h+var_260], rax
0x180003874  lea     rax, aNoremotedestin; "NoRemoteDestinations"
0x18000387b  mov     [rbp+3B0h+var_248], rax
0x180003882  lea     rax, aDisablenotific; "DisableNotificationCenter"
0x180003889  mov     [rbp+3B0h+var_230], rax
0x180003890  lea     rax, aDisablecontrol; "DisableControlCenter"
0x180003897  mov     [rbp+3B0h+var_218], rax
0x18000389e  lea     rax, aAlwaysshownoti; "AlwaysShowNotificationIcon"
0x1800038a5  mov     [rbp+3B0h+var_200], rax
0x1800038ac  lea     rax, aTurnoffabbrevi; "TurnOffAbbreviatedDateTimeFormat"
0x1800038b3  mov     [rbp+3B0h+var_1E8], rax
0x1800038ba  mov     [rbp+3B0h+var_328], r11d
0x1800038c1  mov     [rbp+3B0h+var_324], r10d
0x1800038c8  mov     [rbp+3B0h+var_318], rdx
0x1800038cf  mov     [rbp+3B0h+var_310], r11d
0x1800038d6  mov     [rbp+3B0h+var_30C], r10d
0x1800038dd  mov     [rbp+3B0h+var_300], rdx
0x1800038e4  mov     [rbp+3B0h+var_2F8], r11d
0x1800038eb  mov     [rbp+3B0h+var_2F4], r10d
0x1800038f2  mov     [rbp+3B0h+var_2E8], rcx
0x1800038f9  mov     [rbp+3B0h+var_2E0], r11d
0x180003900  mov     [rbp+3B0h+var_2DC], r10d
0x180003907  mov     [rbp+3B0h+var_2D0], rdx
0x18000390e  mov     [rbp+3B0h+var_2C8], r11d
0x180003915  mov     [rbp+3B0h+var_2C4], r10d
0x18000391c  mov     [rbp+3B0h+var_2B8], rdx
0x180003923  mov     [rbp+3B0h+var_2B0], r11d
0x18000392a  mov     [rbp+3B0h+var_2AC], r10d
0x180003931  mov     [rbp+3B0h+var_2A0], rdx
0x180003938  mov     [rbp+3B0h+var_298], r11d
0x18000393f  mov     [rbp+3B0h+var_294], r10d
0x180003946  mov     [rbp+3B0h+var_288], rcx
0x18000394d  mov     [rbp+3B0h+var_280], r11d
0x180003954  mov     [rbp+3B0h+var_27C], r10d
0x18000395b  mov     [rbp+3B0h+var_270], rcx
0x180003962  mov     [rbp+3B0h+var_268], r11d
0x180003969  mov     [rbp+3B0h+var_264], r10d
0x180003970  mov     [rbp+3B0h+var_258], rcx
0x180003977  mov     [rbp+3B0h+var_250], r11d
0x18000397e  mov     [rbp+3B0h+var_24C], r10d
0x180003985  mov     [rbp+3B0h+var_240], rcx
0x18000398c  mov     [rbp+3B0h+var_238], r11d
0x180003993  mov     [rbp+3B0h+var_234], r10d
0x18000399a  mov     [rbp+3B0h+var_228], rcx
0x1800039a1  mov     [rbp+3B0h+var_220], r11d
0x1800039a8  mov     [rbp+3B0h+var_21C], r10d
0x1800039af  mov     [rbp+3B0h+var_210], rcx
0x1800039b6  mov     [rbp+3B0h+var_208], r11d
0x1800039bd  mov     [rbp+3B0h+var_204], r10d
0x1800039c4  mov     [rbp+3B0h+var_1F8], rcx
0x1800039cb  mov     [rbp+3B0h+var_1F0], r11d
0x1800039d2  mov     [rbp+3B0h+var_1EC], r10d
0x1800039d9  mov     [rbp+3B0h+var_1E0], rcx
0x1800039e0  mov     [rbp+3B0h+var_1D8], r11d
0x1800039e7  mov     [rbp+3B0h+var_1D4], r10d
0x1800039ee  lea     rax, aTaskbarlockall; "TaskbarLockAll"
0x1800039f5  mov     [rbp+3B0h+var_1C8], rdx
0x1800039fc  mov     [rbp+3B0h+var_1D0], rax
0x180003a03  lea     rax, aLocktaskbar; "LockTaskbar"
0x180003a0a  mov     [rbp+3B0h+var_1B8], rax
0x180003a11  lea     rax, aTaskbarnoaddre; "TaskbarNoAddRemoveToolbar"
0x180003a18  mov     [rbp+3B0h+var_1A0], rax
0x180003a1f  lea     rax, aTaskbarnoredoc; "TaskbarNoRedock"
0x180003a26  mov     [rbp+3B0h+var_188], rax
0x180003a2d  lea     rax, aTaskbarnodragt; "TaskbarNoDragToolbar"
0x180003a34  mov     [rbp+3B0h+var_170], rax
0x180003a3b  lea     rax, aTaskbarnoresiz; "TaskbarNoResize"
0x180003a42  mov     [rbp+3B0h+var_158], rax
0x180003a49  lea     rax, aNofrequentused; "NoFrequentUsedPrograms"
0x180003a50  mov     [rbp+3B0h+var_140], rax
0x180003a57  lea     rax, aTaskbarnopinne; "TaskbarNoPinnedList"
0x180003a5e  mov     [rbp+3B0h+var_128], rax
0x180003a65  lea     rax, aHidescahealth; "HideSCAHealth"
0x180003a6c  mov     [rbp+3B0h+var_110], rax
0x180003a73  lea     rax, aTaskbarnonotif; "TaskbarNoNotification"
0x180003a7a  mov     [rbp+3B0h+var_F8], rax
0x180003a81  lea     rax, aNoballoonfeatu; "NoBalloonFeatureAdvertisements"
0x180003a88  mov     [rbp+3B0h+var_1B0], rdx
0x180003a8f  mov     [rbp+3B0h+var_198], rdx
0x180003a96  mov     [rbp+3B0h+var_180], rdx
0x180003a9d  mov     [rbp+3B0h+var_168], rdx
0x180003aa4  mov     [rbp+3B0h+var_150], rdx
0x180003aab  mov     [rbp+3B0h+var_138], rdx
0x180003ab2  mov     [rbp+3B0h+var_120], rcx
0x180003ab9  mov     [rbp+3B0h+var_108], rdx
0x180003ac0  mov     [rbp+3B0h+var_F0], rdx
0x180003ac7  lea     rdx, [rsp+4B0h+var_440]
0x180003acc  mov     [rbp+3B0h+var_430], rcx
0x180003ad0  lea     rcx, [rbp+3B0h+var_E8]
0x180003ad7  mov     [rsp+4B0h+var_438], rax
0x180003adc  mov     [rbp+3B0h+var_1C0], r11d
0x180003ae3  mov     [rbp+3B0h+var_1BC], r10d
0x180003aea  mov     [rbp+3B0h+var_1A8], r11d
0x180003af1  mov     [rbp+3B0h+var_1A4], r10d
0x180003af8  mov     [rbp+3B0h+var_190], r11d
0x180003aff  mov     [rbp+3B0h+var_18C], r10d
0x180003b06  mov     [rbp+3B0h+var_178], r11d
0x180003b0d  mov     [rbp+3B0h+var_174], r10d
0x180003b14  mov     [rbp+3B0h+var_160], r11d
0x180003b1b  mov     [rbp+3B0h+var_15C], r10d
0x180003b22  mov     [rbp+3B0h+var_148], r11d
0x180003b29  mov     [rbp+3B0h+var_144], r10d
0x180003b30  mov     [rbp+3B0h+var_130], r11d
0x180003b37  mov     [rbp+3B0h+var_12C], 67h ; 'g'
0x180003b41  mov     [rbp+3B0h+var_118], r11d
0x180003b48  mov     [rbp+3B0h+var_114], r10d
0x180003b4f  mov     [rbp+3B0h+var_100], r11d
0x180003b56  mov     [rbp+3B0h+var_FC], r10d
0x180003b5d  mov     [rsp+4B0h+var_440], r11d
0x180003b62  mov     [rsp+4B0h+var_43C], r10d
0x180003b67  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003b6c  lea     rax, [rsp+4B0h+var_480]
0x180003b71  mov     [rsp+4B0h+var_480], r11d
0x180003b76  lea     r9, [rsp+4B0h+var_47C]
0x180003b7b  mov     [rsp+4B0h+var_490], rax
0x180003b80  lea     r8, aHidetaskviewbu; "HideTaskViewButton"
0x180003b87  mov     [rsp+4B0h+var_47C], r10d
0x180003b8c  lea     rcx, [rbp+3B0h+var_400]
0x180003b90  call    ??$make_tuple@AEAY0CN@$$CBGAEAY0BD@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0CN@$$CBGAEAY0BD@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[45],ushort const (&)[19],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[45],ushort const (&)[19],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003b95  mov     rdx, rax
0x180003b98  lea     rcx, [rbp+3B0h+var_D0]
0x180003b9f  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003ba4  lea     rax, [rsp+4B0h+var_478]
0x180003ba9  mov     [rsp+4B0h+var_478], r11d
0x180003bae  lea     r9, [rsp+4B0h+var_474]
0x180003bb3  mov     [rsp+4B0h+var_490], rax
0x180003bb8  lea     rcx, [rbp+3B0h+var_3E8]
0x180003bbc  mov     [rsp+4B0h+var_474], r10d
0x180003bc1  call    ??$make_tuple@AEAY0DD@$$CBGAEAY0BG@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0DD@$$CBGAEAY0BG@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[51],ushort const (&)[22],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[51],ushort const (&)[22],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003bc6  mov     rdx, rax
0x180003bc9  lea     rcx, [rbp+3B0h+var_B8]
0x180003bd0  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003bd5  lea     rax, [rsp+4B0h+var_470]
0x180003bda  mov     [rsp+4B0h+var_470], r11d
0x180003bdf  mov     [rsp+4B0h+var_490], rax
0x180003be4  mov     [rsp+4B0h+var_46C], r10d
0x180003be9  lea     r9, [rsp+4B0h+var_46C]
0x180003bee  lea     rcx, [rbp+3B0h+var_3D0]
0x180003bf2  call    ??$make_tuple@AEAY0EF@$$CBGAEAY0BP@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0EF@$$CBGAEAY0BP@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[69],ushort const (&)[31],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[69],ushort const (&)[31],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003bf7  mov     rdx, rax
0x180003bfa  lea     rcx, [rbp+3B0h+var_A0]
0x180003c01  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003c06  lea     rax, [rsp+4B0h+var_468]
0x180003c0b  mov     [rsp+4B0h+var_468], r11d
0x180003c10  lea     r9, [rsp+4B0h+var_464]
0x180003c15  mov     [rsp+4B0h+var_490], rax
0x180003c1a  lea     rcx, [rbp+3B0h+var_3B8]
0x180003c1e  mov     [rsp+4B0h+var_464], r10d
0x180003c23  call    ??$make_tuple@AEAY0DK@$$CBGAEAY0P@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0DK@$$CBGAEAY0P@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[58],ushort const (&)[15],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[58],ushort const (&)[15],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003c28  mov     rdx, rax
0x180003c2b  lea     rcx, [rbp+3B0h+var_88]
0x180003c32  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003c37  lea     rax, [rsp+4B0h+var_460]
0x180003c3c  mov     [rsp+4B0h+var_460], r11d
0x180003c41  lea     r9, [rsp+4B0h+var_45C]
0x180003c46  mov     [rsp+4B0h+var_490], rax
0x180003c4b  lea     rcx, [rbp+3B0h+var_3A0]
0x180003c4f  mov     [rsp+4B0h+var_45C], r10d
0x180003c54  call    ??$make_tuple@AEAY0DK@$$CBGAEAY0BG@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0DK@$$CBGAEAY0BG@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[58],ushort const (&)[22],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[58],ushort const (&)[22],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003c59  mov     rdx, rax
0x180003c5c  lea     rcx, [rbp+3B0h+var_70]
0x180003c63  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003c68  lea     rax, [rsp+4B0h+var_458]
0x180003c6d  mov     [rsp+4B0h+var_458], r11d
0x180003c72  lea     r9, [rsp+4B0h+var_454]
0x180003c77  mov     [rsp+4B0h+var_490], rax
0x180003c7c  lea     rcx, [rbp+3B0h+var_388]
0x180003c80  mov     [rsp+4B0h+var_454], r10d
0x180003c85  call    ??$make_tuple@AEAY0DM@$$CBGAEAY08$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0DM@$$CBGAEAY08$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[60],ushort const (&)[9],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[60],ushort const (&)[9],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003c8a  mov     rdx, rax
0x180003c8d  lea     rcx, [rbp+3B0h+var_58]
0x180003c94  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003c99  lea     rax, [rsp+4B0h+var_450]
0x180003c9e  mov     [rsp+4B0h+var_450], r11d
0x180003ca3  lea     r9, [rsp+4B0h+var_44C]
0x180003ca8  mov     [rsp+4B0h+var_490], rax
0x180003cad  lea     r8, aNonetconnectdi; "NoNetConnectDisconnect"
0x180003cb4  mov     [rsp+4B0h+var_44C], r10d
0x180003cb9  lea     rcx, [rbp+3B0h+var_370]
0x180003cbd  call    ??$make_tuple@AEAY0DM@$$CBGAEAY0BH@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0DM@$$CBGAEAY0BH@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[60],ushort const (&)[23],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[60],ushort const (&)[23],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003cc2  mov     rdx, rax
0x180003cc5  lea     rcx, [rbp+3B0h+var_40]
0x180003ccc  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003cd1  lea     rax, [rsp+4B0h+var_448]
0x180003cd6  mov     [rsp+4B0h+var_448], 3FFFFFFh
0x180003cde  lea     r9, [rsp+4B0h+var_444]
0x180003ce3  mov     [rsp+4B0h+var_490], rax
0x180003ce8  lea     r8, aNoviewondrive; "NoViewOnDrive"
0x180003cef  mov     [rsp+4B0h+var_444], 3
0x180003cf7  lea     rcx, [rbp+3B0h+var_358]
0x180003cfb  call    ??$make_tuple@AEAY0DM@$$CBGAEAY0BH@$$CBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@std@@YA?AV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@0@AEAY0DM@$$CBGAEAY0BH@$$CBG$$QEAW4DefinitionVersion@AssignedAccess@Internal@Windows@@$$QEAH@Z; std::make_tuple<ushort const (&)[60],ushort const (&)[23],Windows::Internal::AssignedAccess::DefinitionVersion,int>(ushort const (&)[60],ushort const (&)[23],Windows::Internal::AssignedAccess::DefinitionVersion &&,int &&)
0x180003d00  mov     rdx, rax
0x180003d03  lea     rcx, [rbp+3B0h+var_28]
0x180003d0a  call    ??$?0PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H$0A@@?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@QEAA@$$QEAV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@H@1@@Z; std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,int> &&)
0x180003d0f  lea     r8, [rbp+3B0h+var_10]
0x180003d16  lea     rdx, [rbp+3B0h+var_340]
0x180003d1a  lea     rcx, [rbp+3B0h+var_410]
0x180003d1e  call    ??0?$initializer_list@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@@std@@QEAA@PEBV?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@1@0@Z; std::initializer_list<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>>::initializer_list<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>>(std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong> const *,std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong> const *)
0x180003d23  lea     rdx, [rbp+3B0h+var_420]
0x180003d27  lea     rcx, ?c_defaultLocalGroupPolicyConfiguration@AssignedAccess@Internal@Windows@@3V?$vector@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@V?$allocator@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@@2@@std@@B; std::vector<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>> const Windows::Internal::AssignedAccess::c_defaultLocalGroupPolicyConfiguration
0x180003d2e  movups  xmm0, xmmword ptr [rax]
0x180003d31  movdqu  [rbp+3B0h+var_420], xmm0
0x180003d36  call    ??0?$vector@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@V?$allocator@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@@2@@std@@QEAA@V?$initializer_list@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@@1@AEBV?$allocator@V?$tuple@PEBGPEBGW4DefinitionVersion@AssignedAccess@Internal@Windows@@K@std@@@1@@Z; std::vector<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>>::vector<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>>(std::initializer_list<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>>,std::allocator<std::tuple<ushort const *,ushort const *,Windows::Internal::AssignedAccess::DefinitionVersion,ulong>> const &)
0x180003d3b  lea     rcx, Windows__Internal__AssignedAccess___dynamic_atexit_destructor_for__c_defaultLocalGroupPolicyConfiguration__; void (__cdecl *)()
0x180003d42  call    atexit
0x180003d47  mov     rcx, [rbp+3B0h+var_10]
0x180003d4e  xor     rcx, rsp; StackCookie
0x180003d51  call    __security_check_cookie
0x180003d56  add     rsp, 4B0h
0x180003d5d  pop     rbp
0x180003d5e  retn
```
