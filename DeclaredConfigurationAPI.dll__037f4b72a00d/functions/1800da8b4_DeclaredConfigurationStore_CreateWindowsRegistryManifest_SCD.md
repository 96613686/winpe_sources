# DeclaredConfigurationStore_CreateWindowsRegistryManifest(SCD)

- ea: `0x1800da8b4`
- end: `0x1800db9da`
- name: `?DeclaredConfigurationStore_CreateWindowsRegistryManifest@@YAJVSCD@@@Z`
- size: `4390`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dc6a0`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x180019270`
- `0x1800192b4`
- `0x18001aaec`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004cb0c`
- `0x18004d100`
- `0x18004d1ac`
- `0x18004dc70`
- `0x18004ec0c`
- `0x18004ec50`
- `0x180057eec`
- `0x1800600bc`
- `0x1800c5fd0`
- `0x1800ce0f8`
- `0x1800d9f30`
- `0x1800da034`
- `0x1800da32c`
- `0x1800da648`
- `0x1800da6c8`
- `0x1800da718`
- `0x1800da8b4`
- `0x1800dd884`
- `0x1800dd9b8`
- `0x1800ddd9c`
- `0x1800de1b8`
- `0x1800de288`
- `0x180100418`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800daba0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800daf20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db239`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db27b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db33f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db3ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db418`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db440`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db543`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db614`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db665`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db6b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800daba0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800daf20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db239`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db27b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db33f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db3ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db418`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db440`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db543`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db614`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db665`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800db6b2`

## string_xrefs

- `0x1800daf19`: `registry`
- `0x1800dafb8`: `regpath`
- `0x1800db39c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db75a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db7bc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db7e8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db814`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db8d5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db8ff`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db94c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db979`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparsescd.cpp`
- `0x1800db0f0`: `Config/System/`
- `0x1800db167`: `uripath`
- `0x1800db5a4`: `uripath`
- `0x1800db200`: `geturipath`
- `0x1800db5db`: `geturipath`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall DeclaredConfigurationStore_CreateWindowsRegistryManifest(unsigned __int16 *a1)
{
  int v2; // edi
  const struct ConfigDoc *v3; // r13
  const struct ConfigDoc *v4; // rax
  struct Configurations *v5; // rax
  struct Configurations *v6; // rcx
  _QWORD *v7; // rax
  int *v8; // rcx
  _QWORD *v9; // r9
  int HKey; // eax
  const unsigned __int16 *v11; // r9
  HKEY v12; // rbx
  const unsigned __int16 *v13; // r9
  const unsigned __int16 *v14; // r9
  const unsigned __int16 *v15; // r9
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // r9
  int v18; // esi
  struct Settings *v19; // r14
  struct Settings *v20; // r15
  _QWORD *v21; // rcx
  __int64 v22; // rax
  const unsigned __int16 *v23; // r9
  const unsigned __int16 *v24; // r8
  int v25; // eax
  __int64 v26; // rdx
  struct Settings *v27; // r14
  struct Settings *v28; // r15
  int *v29; // rax
  _QWORD *v30; // rcx
  int *v31; // rdx
  __int64 v32; // r9
  int v33; // eax
  _QWORD *v34; // rdx
  int v35; // eax
  HKEY v36; // rbx
  const unsigned __int16 *v37; // r9
  const unsigned __int16 *v38; // r9
  const unsigned __int16 *v39; // r9
  const unsigned __int16 *v40; // r9
  const unsigned __int16 *v41; // r9
  unsigned __int16 **v42; // rcx
  const unsigned __int16 *v43; // r9
  const unsigned __int16 *v44; // r9
  const unsigned __int16 *v45; // r9
  const unsigned __int16 *v46; // r9
  int *v47; // rax
  int *v48; // r9
  int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rax
  const unsigned __int16 *v52; // r9
  int v53; // eax
  __int64 v54; // rax
  __int64 v55; // rax
  const unsigned __int16 *v56; // r9
  int v57; // eax
  unsigned __int16 **v58; // rcx
  unsigned int v59; // esi
  unsigned __int16 **v60; // rcx
  __int64 v61; // rdi
  __int64 v62; // rax
  unsigned __int16 **v63; // rcx
  Settings *v64; // rax
  _QWORD *v65; // rdx
  int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r9
  unsigned __int16 **v69; // rcx
  unsigned __int16 **v70; // rcx
  unsigned __int16 **v71; // rcx
  Settings *v72; // rax
  _QWORD *v73; // rdx
  Settings *v74; // rax
  _QWORD *v75; // rdx
  unsigned __int16 **v76; // rcx
  const unsigned __int16 *v77; // r9
  const unsigned __int16 *v78; // r9
  const unsigned __int16 *v79; // r9
  unsigned __int16 **v80; // rcx
  __int64 v81; // rdx
  unsigned __int16 **v82; // rcx
  unsigned __int16 **v83; // rcx
  Settings *v84; // rcx
  __int64 v85; // r9
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // r9
  int v90; // [rsp+20h] [rbp-E0h]
  int v91; // [rsp+20h] [rbp-E0h]
  int v92; // [rsp+20h] [rbp-E0h]
  int v93; // [rsp+20h] [rbp-E0h]
  HKEY v94; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v95; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v96; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-A8h] BYREF
  struct Configurations *v98; // [rsp+60h] [rbp-A0h]
  struct Configurations *v99; // [rsp+70h] [rbp-90h]
  const struct ConfigDoc *v100; // [rsp+78h] [rbp-88h]
  struct Configurations *v101; // [rsp+80h] [rbp-80h] BYREF
  struct Configurations *v102; // [rsp+88h] [rbp-78h]
  _BYTE v103[576]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v104; // [rsp+2D8h] [rbp+1D8h]
  wchar_t String[4]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v106; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v107; // [rsp+2F0h] [rbp+1F0h]
  _QWORD Src[3]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 v109; // [rsp+318h] [rbp+218h]
  unsigned __int16 *v110[4]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 *v111[4]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v112[32]; // [rsp+360h] [rbp+260h] BYREF
  _QWORD v113[4]; // [rsp+380h] [rbp+280h] BYREF
  int v114[2]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int64 v115; // [rsp+3B8h] [rbp+2B8h]
  unsigned __int16 *v116[4]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 *v117[3]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int64 v118; // [rsp+3F8h] [rbp+2F8h]
  unsigned __int16 *v119[4]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 *v120[4]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 *v121[3]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int64 v122; // [rsp+458h] [rbp+358h]
  unsigned __int16 *v123[4]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 *v124[12]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 *v125[4]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 *v126[4]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 *v127[4]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 *v128[4]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 *v129[12]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 *v130[4]; // [rsp+5C0h] [rbp+4C0h] BYREF
  int v131[2]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int64 v132; // [rsp+5F8h] [rbp+4F8h]
  _QWORD v133[3]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int64 v134; // [rsp+618h] [rbp+518h]
  unsigned __int16 *v135[3]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int64 v136; // [rsp+658h] [rbp+558h]
  unsigned __int16 *v137[4]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 *v138[4]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 *v139[4]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 *v140[4]; // [rsp+6E0h] [rbp+5E0h] BYREF
  struct Settings *v141; // [rsp+700h] [rbp+600h]
  struct Settings *v142; // [rsp+708h] [rbp+608h]
  _BYTE v143[32]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v144[32]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v145[32]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v146[32]; // [rsp+780h] [rbp+680h] BYREF
  unsigned __int16 *v147[44]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _QWORD v148[24]; // [rsp+900h] [rbp+800h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A18h] [rbp+918h]

  v104 = a1;
  v2 = 0;
  v3 = (const struct ConfigDoc *)*((_QWORD *)a1 + 20);
  v4 = (const struct ConfigDoc *)*((_QWORD *)a1 + 21);
  v100 = v4;
  while ( v3 != v4 )
  {
    ConfigDoc::ConfigDoc((ConfigDoc *)&v101, v3);
    v5 = v101;
    v6 = v102;
    v99 = v102;
LABEL_4:
    v98 = v5;
    if ( v5 != v6 )
    {
      Configurations::Configurations((Configurations *)v131, v5);
      lpSubKey = 0;
      v7 = v133;
      if ( v134 > 7 )
        v7 = (_QWORD *)v133[0];
      v8 = v131;
      if ( v132 > 7 )
        v8 = *(int **)v131;
      if ( *((_QWORD *)a1 + 7) <= 7u )
        v9 = a1 + 16;
      else
        v9 = (_QWORD *)*((_QWORD *)a1 + 4);
      *(_QWORD *)String = &lpSubKey;
      v106 = 0;
      LOBYTE(v107) = 1;
      v2 = DCStringCchPrintfAllStrings(&v106, qword_18018A618, 3, v9, v8, v7);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(String);
      if ( v2 >= 0 )
      {
        v94 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v94,
          0);
        HKey = DCCDNUtil_GetHKey(lpSubKey, &v94, 1);
        v2 = HKey;
        if ( HKey < 0 )
        {
          v26 = 184;
        }
        else
        {
          v11 = (const unsigned __int16 *)v135;
          if ( v136 > 7 )
            v11 = v135[0];
          v12 = v94;
          HKey = DCCDNUtil_SetRegistryString(v94, 0, L"context", v11, 0);
          v2 = HKey;
          if ( HKey < 0 )
          {
            v26 = 188;
          }
          else
          {
            v13 = (const unsigned __int16 *)v137;
            if ( v137[3] > (unsigned __int16 *)7 )
              v13 = v137[0];
            HKey = DCCDNUtil_SetRegistryString(v12, 0, L"description", v13, 0);
            v2 = HKey;
            if ( HKey < 0 )
            {
              v26 = 192;
            }
            else
            {
              v14 = (const unsigned __int16 *)v139;
              if ( v139[3] > (unsigned __int16 *)7 )
                v14 = v139[0];
              HKey = DCCDNUtil_SetRegistryString(v12, 0, L"getscenarioalias", v14, 0);
              v2 = HKey;
              if ( HKey < 0 )
              {
                v26 = 196;
              }
              else
              {
                v15 = (const unsigned __int16 *)v138;
                if ( v138[3] > (unsigned __int16 *)7 )
                  v15 = v138[0];
                HKey = DCCDNUtil_SetRegistryString(v12, 0, L"setscenarioalias", v15, 0);
                v2 = HKey;
                if ( HKey < 0 )
                {
                  v26 = 200;
                }
                else
                {
                  if ( *((_QWORD *)a1 + 3) <= 7u )
                    v16 = a1;
                  else
                    v16 = *(const unsigned __int16 **)a1;
                  HKey = DCCDNUtil_SetRegistryString(v12, 0, L"referenceSCD", v16, 0);
                  v2 = HKey;
                  if ( HKey < 0 )
                  {
                    v26 = 204;
                  }
                  else
                  {
                    v17 = (const unsigned __int16 *)v140;
                    if ( v140[3] > (unsigned __int16 *)7 )
                      v17 = v140[0];
                    HKey = DCCDNUtil_SetRegistryString(v12, 0, L"allsettingsrequired", v17, 0);
                    v2 = HKey;
                    if ( HKey >= 0 )
                    {
                      v18 = 1;
                      v19 = v141;
                      v20 = v142;
                      while ( v19 != v20 )
                      {
                        Settings::Settings((Settings *)v146, v19);
                        v21 = v148;
                        if ( v148[3] > 7u )
                          v21 = (_QWORD *)v148[0];
                        if ( !(unsigned int)_o__wcsicmp(v21, L"true") )
                        {
                          v22 = std::to_wstring(String, (unsigned int)v18);
                          std::operator+<unsigned short>(v130, L"Setting", v22);
                          std::wstring::_Tidy_deallocate(String);
                          v23 = (const unsigned __int16 *)v147;
                          if ( v147[3] > (unsigned __int16 *)7 )
                            v23 = v147[0];
                          v24 = (const unsigned __int16 *)v130;
                          if ( v130[3] > (unsigned __int16 *)7 )
                            v24 = v130[0];
                          v25 = DCCDNUtil_SetRegistryString(v12, 0, v24, v23, 0);
                          v2 = v25;
                          if ( v25 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0xDB,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
                              (const char *)(unsigned int)v25,
                              v90);
                            std::wstring::_Tidy_deallocate(v130);
                            v84 = (Settings *)v146;
                            goto LABEL_173;
                          }
                          ++v18;
                          std::wstring::_Tidy_deallocate(v130);
                        }
                        Settings::~Settings((Settings *)v146);
                        v19 = (struct Settings *)((char *)v19 + 576);
                      }
                      if ( v18 > 1 )
                      {
                        HKey = DCCDNUtil_SetRegistryDWORD(v12, 0, L"Size", v18 - 1);
                        v2 = HKey;
                        if ( HKey < 0 )
                        {
                          v26 = 229;
                          goto LABEL_216;
                        }
                      }
                      v27 = v141;
                      v28 = v142;
                      while ( 1 )
                      {
                        if ( v27 == v28 )
                        {
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v94);
                          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
                          Configurations::~Configurations((Configurations *)v131);
                          v5 = (struct Configurations *)((char *)v98 + 312);
                          v6 = v99;
                          goto LABEL_4;
                        }
                        Settings::Settings((Settings *)v113, v27);
                        std::unique_ptr<unsigned short>::reset(&lpSubKey, 0);
                        v29 = v114;
                        if ( v115 > 7 )
                          v29 = *(int **)v114;
                        v30 = v133;
                        if ( v134 > 7 )
                          v30 = (_QWORD *)v133[0];
                        v31 = v131;
                        if ( v132 > 7 )
                          v31 = *(int **)v131;
                        v32 = *((_QWORD *)a1 + 7) <= 7u ? (__int64)(a1 + 16) : *((_QWORD *)a1 + 4);
                        *(_QWORD *)String = &lpSubKey;
                        v106 = 0;
                        LOBYTE(v107) = 1;
                        v2 = DCStringCchPrintfAllStrings(&v106, qword_18018A620, 4, v32, v31, v30, v29);
                        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(String);
                        if ( v2 < 0 )
                          break;
                        v95 = 0;
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                          &v95,
                          0);
                        v33 = DCCDNUtil_GetHKey(lpSubKey, &v95, 1);
                        v2 = v33;
                        if ( v33 < 0 )
                        {
                          v81 = 244;
                          goto LABEL_204;
                        }
                        v34 = v113;
                        if ( v113[3] > 7u )
                          v34 = (_QWORD *)v113[0];
                        std::wstring::wstring((__int64)String, (__int64)v34);
                        v35 = std::stoul(String);
                        v36 = v95;
                        v2 = DCCDNUtil_SetRegistryDWORD(v95, 0, L"order", v35);
                        std::wstring::_Tidy_deallocate(String);
                        if ( v2 < 0 )
                        {
                          v88 = (unsigned int)v2;
                          v81 = 248;
                          goto LABEL_205;
                        }
                        v37 = (const unsigned __int16 *)v121;
                        if ( v122 > 7 )
                          v37 = v121[0];
                        v33 = DCCDNUtil_SetRegistryString(v36, 0, L"provider", v37, 0);
                        v2 = v33;
                        if ( v33 < 0 )
                        {
                          v81 = 252;
                          goto LABEL_204;
                        }
                        v38 = (const unsigned __int16 *)v126;
                        if ( v126[3] > (unsigned __int16 *)7 )
                          v38 = v126[0];
                        v33 = DCCDNUtil_SetRegistryString(v36, 0, L"managed", v38, 0);
                        v2 = v33;
                        if ( v33 < 0 )
                        {
                          v81 = 256;
                          goto LABEL_204;
                        }
                        v39 = (const unsigned __int16 *)v116;
                        if ( v116[3] > (unsigned __int16 *)7 )
                          v39 = v116[0];
                        v33 = DCCDNUtil_SetRegistryString(v36, 0, L"description", v39, 0);
                        v2 = v33;
                        if ( v33 < 0 )
                        {
                          v81 = 260;
                          goto LABEL_204;
                        }
                        v40 = (const unsigned __int16 *)v125;
                        if ( v125[3] > (unsigned __int16 *)7 )
                          v40 = v125[0];
                        v33 = DCCDNUtil_SetRegistryString(v36, 0, L"buildtimeset", v40, 0);
                        v2 = v33;
                        if ( v33 < 0 )
                        {
                          v81 = 264;
                          goto LABEL_204;
                        }
                        v41 = (const unsigned __int16 *)v120;
                        if ( v120[3] > (unsigned __int16 *)7 )
                          v41 = v120[0];
                        v33 = DCCDNUtil_SetRegistryString(v36, 0, L"defaultvalue", v41, 0);
                        v2 = v33;
                        if ( v33 < 0 )
                        {
                          v81 = 268;
                          goto LABEL_204;
                        }
                        v42 = v121;
                        if ( v122 > 7 )
                          v42 = (unsigned __int16 **)v121[0];
                        if ( (unsigned int)_o__wcsicmp(v42, L"registry") )
                        {
                          v76 = v121;
                          if ( v122 > 7 )
                            v76 = (unsigned __int16 **)v121[0];
                          if ( (unsigned int)_o__wcsicmp(v76, L"csp") )
                          {
                            v2 = -2147418113;
                            v88 = 2147549183LL;
                            v81 = 445;
                            goto LABEL_205;
                          }
                          v77 = (const unsigned __int16 *)v127;
                          if ( v127[3] > (unsigned __int16 *)7 )
                            v77 = v127[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"CspName", v77, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 403;
                            goto LABEL_204;
                          }
                          v78 = (const unsigned __int16 *)v128;
                          if ( v128[3] > (unsigned __int16 *)7 )
                            v78 = v128[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"uripath", v78, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 407;
                            goto LABEL_204;
                          }
                          v79 = (const unsigned __int16 *)v129;
                          if ( v129[3] > (unsigned __int16 *)7 )
                            v79 = v129[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"geturipath", v79, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 411;
                            goto LABEL_204;
                          }
                          v80 = v117;
                          if ( v118 > 7 )
                            v80 = (unsigned __int16 **)v117[0];
                          if ( (unsigned int)_o__wcsicmp(v80, L"integer") )
                          {
                            v82 = v117;
                            if ( v118 > 7 )
                              v82 = (unsigned __int16 **)v117[0];
                            if ( (unsigned int)_o__wcsicmp(v82, L"string") )
                            {
                              v83 = v117;
                              if ( v118 > 7 )
                                v83 = (unsigned __int16 **)v117[0];
                              if ( (unsigned int)_o__wcsicmp(v83, L"binary") )
                              {
                                v2 = -2147418113;
                                v88 = 2147549183LL;
                                v81 = 438;
LABEL_205:
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)v81,
                                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\l"
                                                "ib\\dcparsescd.cpp",
                                  (const char *)v88,
                                  v91);
                                goto LABEL_206;
                              }
                              v33 = DCCDNUtil_SetRegistryDWORD(v36, 0, L"DataType", 4);
                              v2 = v33;
                              if ( v33 < 0 )
                              {
                                v81 = 432;
                                goto LABEL_204;
                              }
                            }
                            else
                            {
                              v33 = DCCDNUtil_SetRegistryDWORD(v36, 0, L"DataType", 3);
                              v2 = v33;
                              if ( v33 < 0 )
                              {
                                v81 = 425;
                                goto LABEL_204;
                              }
                            }
                          }
                          else
                          {
                            v33 = DCCDNUtil_SetRegistryDWORD(v36, 0, L"DataType", 2);
                            v2 = v33;
                            if ( v33 < 0 )
                            {
                              v81 = 418;
LABEL_204:
                              v88 = (unsigned int)v33;
                              goto LABEL_205;
                            }
                          }
                        }
                        else
                        {
                          v43 = (const unsigned __int16 *)v119;
                          if ( v119[3] > (unsigned __int16 *)7 )
                            v43 = v119[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"regdatatype", v43, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 274;
                            goto LABEL_204;
                          }
                          v44 = (const unsigned __int16 *)v117;
                          if ( v118 > 7 )
                            v44 = v117[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"settingdatatype", v44, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 278;
                            goto LABEL_204;
                          }
                          v45 = (const unsigned __int16 *)v123;
                          if ( v123[3] > (unsigned __int16 *)7 )
                            v45 = v123[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"regpath", v45, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 282;
                            goto LABEL_204;
                          }
                          v46 = (const unsigned __int16 *)v124;
                          if ( v124[3] > (unsigned __int16 *)7 )
                            v46 = v124[0];
                          v33 = DCCDNUtil_SetRegistryString(v36, 0, L"regvaluename", v46, 0);
                          v2 = v33;
                          if ( v33 < 0 )
                          {
                            v81 = 286;
                            goto LABEL_204;
                          }
                          std::unique_ptr<unsigned short>::reset(&lpSubKey, 0);
                          v47 = v114;
                          if ( v115 > 7 )
                            v47 = *(int **)v114;
                          v48 = v131;
                          if ( v132 > 7 )
                            v48 = *(int **)v131;
                          *(_QWORD *)String = &lpSubKey;
                          v106 = 0;
                          LOBYTE(v107) = 1;
                          v2 = DCStringCchPrintfAllStrings(&v106, qword_18018A628, 2, v48, v47);
                          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(String);
                          if ( v2 < 0 )
                          {
                            v88 = (unsigned int)v2;
                            v81 = 291;
                            goto LABEL_205;
                          }
                          v96 = 0;
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                            &v96,
                            0);
                          v49 = DCCDNUtil_GetHKey(lpSubKey, &v96, 1);
                          v2 = v49;
                          if ( v49 < 0 )
                          {
                            v87 = 297;
LABEL_184:
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)v87,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
                              (const char *)(unsigned int)v49,
                              v91);
                            goto LABEL_185;
                          }
                          v49 = DCCDNUtil_SetRegistryString(v36, 0, L"CspName", L"./Vendor/MSFT/Policy", 0);
                          v2 = v49;
                          if ( v49 < 0 )
                          {
                            v87 = 301;
                            goto LABEL_184;
                          }
                          v50 = std::operator+<unsigned short>(v143, L"Config/System/", v131);
                          v51 = std::operator+<unsigned short>(String, v50, L"_");
                          std::operator+<unsigned short>(v110, v51, v114);
                          std::wstring::_Tidy_deallocate(String);
                          std::wstring::_Tidy_deallocate(v143);
                          v52 = (const unsigned __int16 *)v110;
                          if ( v110[3] > (unsigned __int16 *)7 )
                            v52 = v110[0];
                          v53 = DCCDNUtil_SetRegistryString(v36, 0, L"uripath", v52, 0);
                          v2 = v53;
                          if ( v53 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x132,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
                              (const char *)(unsigned int)v53,
                              v92);
LABEL_181:
                            std::wstring::_Tidy_deallocate(v110);
LABEL_185:
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v96);
LABEL_206:
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v95);
                            goto LABEL_208;
                          }
                          v54 = std::operator+<unsigned short>(v145, L"Result/System/", v131);
                          v55 = std::operator+<unsigned short>(v144, v54, L"_");
                          std::operator+<unsigned short>(v111, v55, v114);
                          std::wstring::_Tidy_deallocate(v144);
                          std::wstring::_Tidy_deallocate(v145);
                          v56 = (const unsigned __int16 *)v111;
                          if ( v111[3] > (unsigned __int16 *)7 )
                            v56 = v111[0];
                          v57 = DCCDNUtil_SetRegistryString(v36, 0, L"geturipath", v56, 0);
                          v2 = v57;
                          if ( v57 < 0 )
                          {
                            v85 = (unsigned int)v57;
                            v86 = 311;
LABEL_178:
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)v86,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
                              (const char *)v85,
                              v93);
LABEL_179:
                            std::wstring::_Tidy_deallocate(v111);
                            goto LABEL_181;
                          }
                          v58 = v135;
                          if ( v136 > 7 )
                            v58 = (unsigned __int16 **)v135[0];
                          if ( (unsigned int)_o__wcsicmp(v58, L"device") )
                          {
                            v60 = v135;
                            if ( v136 > 7 )
                              v60 = (unsigned __int16 **)v135[0];
                            if ( (unsigned int)_o__wcsicmp(v60, L"user") )
                            {
                              v2 = -2147418113;
                              v85 = 2147549183LL;
                              v86 = 332;
                              goto LABEL_178;
                            }
                            std::string::string(String, "HKEY_CURRENT_USER\\");
                            v59 = 16;
                          }
                          else
                          {
                            std::string::string(String, "HKEY_LOCAL_MACHINE\\");
                            v59 = 32;
                          }
                          v61 = v107;
                          std::string::~string(String);
                          std::wstring::substr(v123, Src, v61, -1);
                          std::wstring::wstring((__int64)v112, (__int64)L"ControlSet001");
                          v62 = std::wstring::find(Src, v112);
                          if ( v62 != -1 )
                            std::wstring::_Replace<unsigned short>(Src, v62, 0x1Fu, (char *)L"CurrentControlSet", 17);
                          v63 = v117;
                          if ( v118 > 7 )
                            v63 = (unsigned __int16 **)v117[0];
                          if ( (unsigned int)_o__wcsicmp(v63, L"integer") )
                          {
                            v69 = v117;
                            if ( v118 > 7 )
                              v69 = (unsigned __int16 **)v117[0];
                            if ( !(unsigned int)_o__wcsicmp(v69, L"string") )
                              goto LABEL_139;
                            v70 = v117;
                            if ( v118 > 7 )
                              v70 = (unsigned __int16 **)v117[0];
                            if ( (unsigned int)_o__wcsicmp(v70, L"multistring") )
                            {
                              v71 = v117;
                              if ( v118 > 7 )
                                v71 = (unsigned __int16 **)v117[0];
                              if ( (unsigned int)_o__wcsicmp(v71, L"binary") )
                              {
                                v2 = -2147418113;
                                v68 = 2147549183LL;
                                v67 = 396;
                                goto LABEL_125;
                              }
                              v72 = Settings::Settings((Settings *)v103, (const struct Settings *)v113);
                              v73 = Src;
                              if ( v109 > 7 )
                                v73 = (_QWORD *)Src[0];
                              v93 = (int)v36;
                              v66 = DeclaredConfigurationStore_SetRegistryCaseBinary(v59, v73, v72, v96);
                              v2 = v66;
                              if ( v66 < 0 )
                              {
                                v67 = 390;
                                goto LABEL_124;
                              }
                            }
                            else
                            {
LABEL_139:
                              v74 = Settings::Settings((Settings *)v103, (const struct Settings *)v113);
                              v75 = Src;
                              if ( v109 > 7 )
                                v75 = (_QWORD *)Src[0];
                              v93 = (int)v36;
                              v66 = DeclaredConfigurationStore_SetRegistryCaseString(v59, v75, v74, v96);
                              v2 = v66;
                              if ( v66 < 0 )
                              {
                                v67 = 385;
LABEL_124:
                                v68 = (unsigned int)v66;
LABEL_125:
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)v67,
                                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\l"
                                                "ib\\dcparsescd.cpp",
                                  (const char *)v68,
                                  v93);
                                std::wstring::_Tidy_deallocate(v112);
                                std::wstring::_Tidy_deallocate(Src);
                                goto LABEL_179;
                              }
                            }
                          }
                          else
                          {
                            v64 = Settings::Settings((Settings *)v103, (const struct Settings *)v113);
                            v65 = Src;
                            if ( v109 > 7 )
                              v65 = (_QWORD *)Src[0];
                            v93 = (int)v36;
                            v66 = DeclaredConfigurationStore_SetRegistryCaseInteger(v59, v65, v64, v96);
                            v2 = v66;
                            if ( v66 < 0 )
                            {
                              v67 = 380;
                              goto LABEL_124;
                            }
                          }
                          std::wstring::_Tidy_deallocate(v112);
                          std::wstring::_Tidy_deallocate(Src);
                          std::wstring::_Tidy_deallocate(v111);
                          std::wstring::_Tidy_deallocate(v110);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v96);
                        }
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v95);
                        Settings::~Settings((Settings *)v113);
                        v27 = (struct Settings *)((char *)v27 + 576);
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xEE,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
                        (const char *)(unsigned int)v2,
                        v91);
LABEL_208:
                      v84 = (Settings *)v113;
LABEL_173:
                      Settings::~Settings(v84);
LABEL_217:
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v94);
LABEL_219:
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
                      Configurations::~Configurations((Configurations *)v131);
                      std::vector<Configurations>::_Tidy(&v101);
                      break;
                    }
                    v26 = 208;
                  }
                }
              }
            }
          }
        }
LABEL_216:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
          (const char *)(unsigned int)HKey,
          v90);
        goto LABEL_217;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparsescd.cpp",
        (const char *)(unsigned int)v2,
        v90);
      goto LABEL_219;
    }
    std::vector<Configurations>::_Tidy(&v101);
    v3 = (const struct ConfigDoc *)((char *)v3 + 24);
    v4 = v100;
  }
  SCD::~SCD((SCD *)a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800da8b4  push    rbp
0x1800da8b6  push    rbx
0x1800da8b7  push    rsi
0x1800da8b8  push    rdi
0x1800da8b9  push    r12
0x1800da8bb  push    r13
0x1800da8bd  push    r14
0x1800da8bf  push    r15
0x1800da8c1  lea     rbp, [rsp-8D8h]
0x1800da8c9  sub     rsp, 9D8h
0x1800da8d0  mov     rax, cs:__security_cookie
0x1800da8d7  xor     rax, rsp
0x1800da8da  mov     [rbp+910h+var_50], rax
0x1800da8e1  mov     r12, rcx
0x1800da8e4  mov     [rbp+910h+var_738], rcx
0x1800da8eb  xor     esi, esi
0x1800da8ed  mov     edi, esi
0x1800da8ef  mov     r13, [rcx+0A0h]
0x1800da8f6  mov     rax, [rcx+0A8h]
0x1800da8fd  mov     [rsp+0A10h+var_998], rax
0x1800da902  cmp     r13, rax
0x1800da905  jz      loc_1800DB9AD
0x1800da90b  mov     rdx, r13; struct ConfigDoc *
0x1800da90e  lea     rcx, [rbp+910h+var_990]; this
0x1800da912  call    ??0ConfigDoc@@QEAA@AEBV0@@Z; ConfigDoc::ConfigDoc(ConfigDoc const &)
0x1800da917  nop
0x1800da918  mov     rax, [rbp+910h+var_990]
0x1800da91c  mov     rcx, [rbp+910h+var_988]
0x1800da920  mov     [rsp+0A10h+var_9A0], rcx
0x1800da925  mov     [rsp+0A10h+var_9B0], rax
0x1800da92a  cmp     rax, rcx
0x1800da92d  jz      loc_1800DB739
0x1800da933  mov     rdx, rax; struct Configurations *
0x1800da936  lea     rcx, [rbp+910h+var_430]; this
0x1800da93d  call    ??0Configurations@@QEAA@AEBV0@@Z; Configurations::Configurations(Configurations const &)
0x1800da942  nop
0x1800da943  mov     [rsp+0A10h+lpSubKey], rsi
0x1800da948  lea     rax, [rbp+910h+var_410]
0x1800da94f  cmp     [rbp+910h+var_3F8], 7
0x1800da957  cmova   rax, [rbp+910h+var_410]
0x1800da95f  lea     rcx, [rbp+910h+var_430]
0x1800da966  cmp     [rbp+910h+var_418], 7
0x1800da96e  cmova   rcx, qword ptr [rbp+910h+var_430]
0x1800da976  cmp     qword ptr [r12+38h], 7
0x1800da97c  jbe     short loc_1800DA985
0x1800da97e  mov     r9, [r12+20h]
0x1800da983  jmp     short loc_1800DA98A
0x1800da985  lea     r9, [r12+20h]
0x1800da98a  lea     rdx, [rsp+0A10h+lpSubKey]
0x1800da98f  mov     qword ptr [rbp+910h+String], rdx
0x1800da996  mov     [rbp+910h+var_728], rsi
0x1800da99d  mov     byte ptr [rbp+910h+var_720], 1
0x1800da9a4  mov     [rsp+0A10h+var_9E8], rax
0x1800da9a9  mov     [rsp+0A10h+var_9F0], rcx; int
0x1800da9ae  mov     r8d, 3
0x1800da9b4  mov     rdx, cs:qword_18018A618
0x1800da9bb  lea     rcx, [rbp+910h+var_728]
0x1800da9c2  call    DCStringCchPrintfAllStrings
0x1800da9c7  mov     edi, eax
0x1800da9c9  lea     rcx, [rbp+910h+String]
0x1800da9d0  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800da9d5  test    edi, edi
0x1800da9d7  js      loc_1800DB96F
0x1800da9dd  mov     [rsp+0A10h+var_9D0], rsi
0x1800da9e2  xor     edx, edx
0x1800da9e4  lea     rcx, [rsp+0A10h+var_9D0]
0x1800da9e9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800da9ee  mov     r8d, 1; int
0x1800da9f4  lea     rdx, [rsp+0A10h+var_9D0]; HKEY *
0x1800da9f9  mov     rcx, [rsp+0A10h+lpSubKey]; lpSubKey
0x1800da9fe  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x1800daa03  mov     edi, eax
0x1800daa05  test    eax, eax
0x1800daa07  js      loc_1800DB947
0x1800daa0d  lea     r9, [rbp+910h+var_3D0]
0x1800daa14  cmp     [rbp+910h+var_3B8], 7
0x1800daa1c  cmova   r9, [rbp+910h+var_3D0]; unsigned __int16 *
0x1800daa24  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800daa29  lea     r8, aContext_1; "context"
0x1800daa30  xor     edx, edx; unsigned __int16 *
0x1800daa32  mov     rbx, [rsp+0A10h+var_9D0]
0x1800daa37  mov     rcx, rbx; HKEY
0x1800daa3a  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800daa3f  mov     edi, eax
0x1800daa41  test    eax, eax
0x1800daa43  js      loc_1800DB940
0x1800daa49  lea     r9, [rbp+910h+var_390]
0x1800daa50  cmp     [rbp+910h+var_378], 7
0x1800daa58  cmova   r9, [rbp+910h+var_390]; unsigned __int16 *
0x1800daa60  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800daa65  lea     r8, aDescription_0; "description"
0x1800daa6c  xor     edx, edx; unsigned __int16 *
0x1800daa6e  mov     rcx, rbx; HKEY
0x1800daa71  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800daa76  mov     edi, eax
0x1800daa78  test    eax, eax
0x1800daa7a  js      loc_1800DB939
0x1800daa80  lea     r9, [rbp+910h+var_350]
0x1800daa87  cmp     [rbp+910h+var_338], 7
0x1800daa8f  cmova   r9, [rbp+910h+var_350]; unsigned __int16 *
0x1800daa97  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800daa9c  lea     r8, aGetscenarioali_0; "getscenarioalias"
0x1800daaa3  xor     edx, edx; unsigned __int16 *
0x1800daaa5  mov     rcx, rbx; HKEY
0x1800daaa8  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800daaad  mov     edi, eax
0x1800daaaf  test    eax, eax
0x1800daab1  js      loc_1800DB932
0x1800daab7  lea     r9, [rbp+910h+var_370]
0x1800daabe  cmp     [rbp+910h+var_358], 7
0x1800daac6  cmova   r9, [rbp+910h+var_370]; unsigned __int16 *
0x1800daace  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800daad3  lea     r8, aSetscenarioali; "setscenarioalias"
0x1800daada  xor     edx, edx; unsigned __int16 *
0x1800daadc  mov     rcx, rbx; HKEY
0x1800daadf  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800daae4  mov     edi, eax
0x1800daae6  test    eax, eax
0x1800daae8  js      loc_1800DB92B
0x1800daaee  cmp     qword ptr [r12+18h], 7
0x1800daaf4  jbe     short loc_1800DAAFC
0x1800daaf6  mov     r9, [r12]
0x1800daafa  jmp     short loc_1800DAAFF
0x1800daafc  mov     r9, r12; unsigned __int16 *
0x1800daaff  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800dab04  lea     r8, aReferencescd; "referenceSCD"
0x1800dab0b  xor     edx, edx; unsigned __int16 *
0x1800dab0d  mov     rcx, rbx; HKEY
0x1800dab10  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800dab15  mov     edi, eax
0x1800dab17  test    eax, eax
0x1800dab19  js      loc_1800DB924
0x1800dab1f  lea     r9, [rbp+910h+var_330]
0x1800dab26  cmp     [rbp+910h+var_318], 7
0x1800dab2e  cmova   r9, [rbp+910h+var_330]; unsigned __int16 *
0x1800dab36  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800dab3b  lea     r8, aAllsettingsreq_1; "allsettingsrequired"
0x1800dab42  xor     edx, edx; unsigned __int16 *
0x1800dab44  mov     rcx, rbx; HKEY
0x1800dab47  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800dab4c  mov     edi, eax
0x1800dab4e  test    eax, eax
0x1800dab50  js      loc_1800DB91D
0x1800dab56  mov     esi, 1
0x1800dab5b  mov     r14, [rbp+910h+var_310]
0x1800dab62  mov     r15, [rbp+910h+var_308]
0x1800dab69  cmp     r14, r15
0x1800dab6c  jz      loc_1800DAC4E
0x1800dab72  mov     rdx, r14; struct Settings *
0x1800dab75  lea     rcx, [rbp+910h+var_290]; this
0x1800dab7c  call    ??0Settings@@QEAA@AEBV0@@Z; Settings::Settings(Settings const &)
0x1800dab81  nop
0x1800dab82  lea     rcx, [rbp+910h+var_110]
0x1800dab89  cmp     [rbp+910h+var_F8], 7
0x1800dab91  cmova   rcx, [rbp+910h+var_110]
0x1800dab99  lea     rdx, aTrue; "true"
0x1800daba0  call    cs:__imp__o__wcsicmp
0x1800daba6  test    eax, eax
0x1800daba8  jnz     loc_1800DAC36
0x1800dabae  mov     edx, esi
0x1800dabb0  lea     rcx, [rbp+910h+String]
0x1800dabb7  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800dabbc  nop
0x1800dabbd  mov     r8, rax
0x1800dabc0  lea     rdx, aSetting; "Setting"
0x1800dabc7  lea     rcx, [rbp+910h+var_450]
0x1800dabce  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800dabd3  nop
0x1800dabd4  lea     rcx, [rbp+910h+String]
0x1800dabdb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dabe0  lea     r9, [rbp+910h+var_270]
0x1800dabe7  cmp     [rbp+910h+var_258], 7
0x1800dabef  cmova   r9, [rbp+910h+var_270]; unsigned __int16 *
0x1800dabf7  lea     r8, [rbp+910h+var_450]
0x1800dabfe  cmp     [rbp+910h+var_438], 7
0x1800dac06  cmova   r8, [rbp+910h+var_450]; unsigned __int16 *
0x1800dac0e  mov     byte ptr [rsp+0A10h+var_9F0], 0; int
0x1800dac13  xor     edx, edx; unsigned __int16 *
0x1800dac15  mov     rcx, rbx; HKEY
0x1800dac18  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800dac1d  mov     edi, eax
0x1800dac1f  test    eax, eax
0x1800dac21  js      loc_1800DB750
0x1800dac27  inc     esi
0x1800dac29  lea     rcx, [rbp+910h+var_450]
0x1800dac30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dac35  nop
0x1800dac36  lea     rcx, [rbp+910h+var_290]; this
0x1800dac3d  call    ??1Settings@@QEAA@XZ; Settings::~Settings(void)
0x1800dac42  add     r14, 240h
0x1800dac49  jmp     loc_1800DAB69
0x1800dac4e  cmp     esi, 1
0x1800dac51  jle     short loc_1800DAC7A
0x1800dac53  lea     r9d, [rsi-1]; unsigned int
0x1800dac57  lea     r8, aSize; "Size"
0x1800dac5e  xor     edx, edx; unsigned __int16 *
0x1800dac60  mov     rcx, rbx; HKEY
0x1800dac63  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800dac68  mov     edi, eax
0x1800dac6a  xor     esi, esi
0x1800dac6c  test    eax, eax
0x1800dac6e  jns     short loc_1800DAC7C
0x1800dac70  mov     edx, 0E5h
0x1800dac75  jmp     loc_1800DB94C
0x1800dac7a  xor     esi, esi
0x1800dac7c  mov     r14, [rbp+910h+var_310]
0x1800dac83  mov     r15, [rbp+910h+var_308]
0x1800dac8a  cmp     r14, r15
0x1800dac8d  jz      loc_1800DB702
0x1800dac93  mov     rdx, r14; struct Settings *
0x1800dac96  lea     rcx, [rbp+910h+var_690]; this
0x1800dac9d  call    ??0Settings@@QEAA@AEBV0@@Z; Settings::Settings(Settings const &)
0x1800daca2  nop
0x1800daca3  xor     edx, edx
0x1800daca5  lea     rcx, [rsp+0A10h+lpSubKey]
0x1800dacaa  call    ?reset@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort>::reset(ushort *)
0x1800dacaf  lea     rax, [rbp+910h+var_670]
0x1800dacb6  cmp     [rbp+910h+var_658], 7
0x1800dacbe  cmova   rax, qword ptr [rbp+910h+var_670]
0x1800dacc6  lea     rcx, [rbp+910h+var_410]
0x1800daccd  cmp     [rbp+910h+var_3F8], 7
0x1800dacd5  cmova   rcx, [rbp+910h+var_410]
0x1800dacdd  lea     rdx, [rbp+910h+var_430]
0x1800dace4  cmp     [rbp+910h+var_418], 7
0x1800dacec  cmova   rdx, qword ptr [rbp+910h+var_430]
0x1800dacf4  cmp     qword ptr [r12+38h], 7
0x1800dacfa  jbe     short loc_1800DAD03
0x1800dacfc  mov     r9, [r12+20h]
0x1800dad01  jmp     short loc_1800DAD08
0x1800dad03  lea     r9, [r12+20h]
0x1800dad08  lea     r8, [rsp+0A10h+lpSubKey]
0x1800dad0d  mov     qword ptr [rbp+910h+String], r8
0x1800dad14  mov     [rbp+910h+var_728], rsi
0x1800dad1b  mov     byte ptr [rbp+910h+var_720], 1
0x1800dad22  mov     [rsp+0A10h+var_9E0], rax
0x1800dad27  mov     [rsp+0A10h+var_9E8], rcx
0x1800dad2c  mov     [rsp+0A10h+var_9F0], rdx; int
0x1800dad31  mov     r8d, 4
0x1800dad37  mov     rdx, cs:qword_18018A620
0x1800dad3e  lea     rcx, [rbp+910h+var_728]
0x1800dad45  call    DCStringCchPrintfAllStrings
0x1800dad4a  mov     edi, eax
0x1800dad4c  lea     rcx, [rbp+910h+String]
0x1800dad53  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800dad58  test    edi, edi
0x1800dad5a  js      loc_1800DB8F5
0x1800dad60  mov     [rsp+0A10h+var_9C8], rsi
0x1800dad65  xor     edx, edx
0x1800dad67  lea     rcx, [rsp+0A10h+var_9C8]
0x1800dad6c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800dad71  mov     r8d, 1; int
0x1800dad77  lea     rdx, [rsp+0A10h+var_9C8]; HKEY *
0x1800dad7c  mov     rcx, [rsp+0A10h+lpSubKey]; lpSubKey
0x1800dad81  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x1800dad86  mov     edi, eax
0x1800dad88  test    eax, eax
0x1800dad8a  js      loc_1800DB8CD
0x1800dad90  lea     rdx, [rbp+910h+var_690]
0x1800dad97  cmp     [rbp+910h+var_678], 7
0x1800dad9f  cmova   rdx, [rbp+910h+var_690]
0x1800dada7  lea     rcx, [rbp+910h+String]
0x1800dadae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dadb3  nop
0x1800dadb4  lea     rcx, [rbp+910h+String]; String
0x1800dadbb  call    ?stoul@std@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoul(std::wstring const &,unsigned __int64 *,int)
0x1800dadc0  mov     r9d, eax; unsigned int
0x1800dadc3  lea     r8, aOrder; "order"
0x1800dadca  xor     edx, edx; unsigned __int16 *
0x1800dadcc  mov     rbx, [rsp+0A10h+var_9C8]
0x1800dadd1  mov     rcx, rbx; HKEY
0x1800dadd4  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800dadd9  mov     edi, eax
0x1800daddb  lea     rcx, [rbp+910h+String]
0x1800dade2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dade7  test    edi, edi
0x1800dade9  js      loc_1800DB8C3
0x1800dadef  lea     r9, [rbp+910h+var_5D0]
0x1800dadf6  cmp     [rbp+910h+var_5B8], 7
0x1800dadfe  cmova   r9, [rbp+910h+var_5D0]; unsigned __int16 *
0x1800dae06  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800dae0b  lea     r8, aProvider; "provider"
0x1800dae12  xor     edx, edx; unsigned __int16 *
0x1800dae14  mov     rcx, rbx; HKEY
0x1800dae17  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800dae1c  mov     edi, eax
0x1800dae1e  test    eax, eax
0x1800dae20  js      loc_1800DB8BC
0x1800dae26  lea     r9, [rbp+910h+var_510]
0x1800dae2d  cmp     [rbp+910h+var_4F8], 7
0x1800dae35  cmova   r9, [rbp+910h+var_510]; unsigned __int16 *
0x1800dae3d  mov     byte ptr [rsp+0A10h+var_9F0], sil; bool
0x1800dae42  lea     r8, aManaged; "managed"
0x1800dae49  xor     edx, edx; unsigned __int16 *
0x1800dae4b  mov     rcx, rbx; HKEY
0x1800dae4e  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800dae53  mov     edi, eax
0x1800dae55  test    eax, eax
0x1800dae57  js      loc_1800DB8B5
0x1800dae5d  lea     r9, [rbp+910h+var_650]
0x1800dae64  cmp     [rbp+910h+var_638], 7
  ... truncated ...
```
