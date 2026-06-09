# CtapPluginAddAuthenticator

- ea: `0x18010f334`
- end: `0x180111443`
- name: `CtapPluginAddAuthenticator`
- size: `8463`
- prototype: `__int64 __fastcall(void *, _OWORD *, const BYTE *, void *, const OLECHAR *, _WORD *, _WORD *, BYTE *, DWORD cbData, __int64, int, const void *)`
- caller_count: `1`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800db110`

## callees

- `0x180003d08`
- `0x180003ff4`
- `0x18001df88`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x180021bac`
- `0x1800328b8`
- `0x180036da4`
- `0x18003737c`
- `0x180037f6c`
- `0x18003a9e8`
- `0x18004349c`
- `0x180043a6c`
- `0x1800441c4`
- `0x180044f9c`
- `0x1800467e0`
- `0x180046820`
- `0x180047db8`
- `0x180048b70`
- `0x180049dbc`
- `0x180049e00`
- `0x180049e1c`
- `0x18004d8f4`
- `0x18004f5b4`
- `0x1800501cc`
- `0x180050e10`
- `0x180066b34`
- `0x18006b260`
- `0x18006f174`
- `0x180072974`
- `0x18007e064`
- `0x1800ae560`
- `0x1800b2624`
- `0x18010a8a4`
- `0x18010aa7c`
- `0x18010baac`
- `0x18010c50c`
- `0x18010ca28`
- `0x18010e490`
- `0x18010e7d0`
- `0x18010f334`
- `0x18011c42c`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011077b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180110931`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011094d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801109f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180110a0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011077b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180110931`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011094d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801109f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180110a0e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010f77e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010f77e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010fa92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010fb93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010fc94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010ff0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110010`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011024e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110349`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110449`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110548`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110a40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110b3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801110ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010fa92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010fb93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010fc94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010ff0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110010`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011024e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110349`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110449`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110548`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110a40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180110b3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801110ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010f73e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010f73e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010f99a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fa1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fb0e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fc0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fd10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010ff97`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18011009a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801101e8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801102d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801103d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801104d3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801105d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801107e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801109b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180110aca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180110bc8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180110d34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18011106d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180111154`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010f99a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fa1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fb0e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fc0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010fd10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18010ff97`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18011009a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801101e8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801102d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801103d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801104d3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801105d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801107e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1801109b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180110aca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180110bc8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180110d34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18011106d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180111154`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180110f84`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180110f84`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010f63b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010f63b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180110db1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180110db1`

## string_xrefs

- `0x18010f5f2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010f6c9`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010f793`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010f93b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010faab`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010fbac`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010fcad`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18010ff26`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110029`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110178`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110267`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110364`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110462`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110564`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110754`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110910`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110a59`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110b57`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110cc4`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110e6d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110f36`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180110fef`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801110e3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801111c7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801112e9`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801113dd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180111430`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x18010f69a`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x1801106c2`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x18011087e`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x180110c32`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x180110e7e`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_kcm_key`
- `0x1801113aa`: `WebAuthNPluginAddAuthenticatorTest::reason::decoding_failed`
- `0x18010f5bf`: `WebAuthNPluginAddAuthenticatorTest::reason::registry_access_failed`
- `0x18010fe6c`: `WebAuthNPluginAddAuthenticatorTest::reason::unsupported_algorithm`
- `0x1801100ea`: `WebAuthNPluginAddAuthenticatorTest::reason::unsupported_algorithm`
- `0x180111249`: `WebAuthNPluginAddAuthenticatorTest::reason::clsid_exists`
- `0x18010f897`: `WebAuthNPluginAddAuthenticatorTest::reason::package_verification_failed`

## pseudocode

```c
__int64 __fastcall CtapPluginAddAuthenticator(
        void *a1,
        _OWORD *a2,
        const BYTE *a3,
        void *a4,
        const OLECHAR *a5,
        _WORD *a6,
        _WORD *a7,
        BYTE *a8,
        DWORD cbData,
        __int64 a10,
        int a11,
        const void *a12)
{
  int v16; // r8d
  int v17; // r9d
  _DWORD *v18; // rcx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rdx
  __int64 v22; // r8
  LPCWSTR v23; // rdi
  __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  unsigned int UserPluginAuthenticatorsRegKey; // ebx
  __int64 v30; // r8
  const char *v31; // rdx
  int v32; // r8d
  int v33; // r9d
  int *v34; // rcx
  char *v35; // rdx
  const char *v36; // rax
  const char *v37; // r9
  __int64 result; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  const char *v41; // rdx
  int v42; // r8d
  int v43; // r9d
  int *v44; // rcx
  char *v45; // rdx
  const char *v46; // rax
  HKEY *v47; // rax
  const char *v48; // rdx
  HKEY *v49; // rax
  unsigned int Key; // eax
  unsigned int v51; // ebx
  const char *v52; // rdx
  const char *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // r8d
  int v57; // r9d
  int *v58; // rcx
  char *v59; // rdx
  const BYTE *v60; // rcx
  unsigned int v61; // eax
  unsigned int v62; // ebx
  const BYTE *v63; // rcx
  unsigned int v64; // eax
  const BYTE *v65; // rcx
  unsigned int v66; // eax
  LPCWSTR *i; // rbx
  LPCWSTR *v68; // r14
  const char *v69; // rdx
  const char *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  int v73; // r8d
  int v74; // r9d
  int *v75; // rcx
  char *v76; // rdx
  unsigned int v77; // eax
  __int64 v78; // rax
  unsigned int v79; // eax
  const char *v80; // rax
  __int64 v81; // rdx
  __int64 v82; // r8
  int v83; // r8d
  int v84; // r9d
  int *v85; // rcx
  char *v86; // rdx
  __int64 v87; // rax
  unsigned int v88; // eax
  unsigned int v89; // eax
  __int64 v90; // rax
  unsigned int v91; // eax
  __int64 v92; // rax
  unsigned int v93; // eax
  __int64 v94; // rax
  const char *v95; // rdx
  int v96; // ebx
  const char *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // r8
  int v100; // r8d
  int v101; // r9d
  int *v102; // rcx
  char *v103; // rdx
  HLOCAL v104; // rcx
  __int64 v105; // rax
  const char *v106; // rdx
  const char *v107; // rax
  __int64 v108; // rdx
  __int64 v109; // r8
  int v110; // r8d
  int v111; // r9d
  int *v112; // rcx
  char *v113; // rdx
  HLOCAL v114; // rcx
  HLOCAL v115; // rcx
  HLOCAL v116; // rcx
  HLOCAL v117; // rcx
  unsigned int v118; // eax
  unsigned int v119; // eax
  const char *v120; // rdx
  const char *v121; // rax
  __int64 v122; // rdx
  __int64 v123; // r8
  int v124; // r8d
  int v125; // r9d
  int *v126; // rcx
  char *v127; // rdx
  _WORD *v128; // rbx
  __int64 v129; // r8
  wil::reg::reg_view_details::reg_value_type_info *v130; // rdi
  __int64 v131; // rax
  HANDLE v132; // r12
  int v133; // eax
  const char *v134; // rdx
  const char *v135; // rax
  __int64 v136; // rdx
  __int64 v137; // r8
  int v138; // r8d
  int v139; // r9d
  int *v140; // rcx
  __int16 *v141; // rdx
  int KeyFromKcmKeyName; // eax
  DWORD buffer_size_bytes; // eax
  int v144; // eax
  unsigned int v145; // eax
  int v146; // eax
  const char *v147; // rax
  __int64 v148; // rdx
  __int64 v149; // r8
  int v150; // r8d
  int v151; // r9d
  int *v152; // rcx
  __int16 *v153; // rdx
  const char *v154; // rdx
  int v155; // r8d
  int v156; // r9d
  int *v157; // rcx
  __int16 *v158; // rdx
  const char *v159; // rax
  int phkResult; // [rsp+20h] [rbp-238h]
  int phkResulta; // [rsp+20h] [rbp-238h]
  unsigned int phkResultb; // [rsp+20h] [rbp-238h]
  int phkResultc; // [rsp+20h] [rbp-238h]
  unsigned int phkResultd; // [rsp+20h] [rbp-238h]
  unsigned int phkResulte; // [rsp+20h] [rbp-238h]
  unsigned int phkResultf; // [rsp+20h] [rbp-238h]
  unsigned int phkResultg; // [rsp+20h] [rbp-238h]
  unsigned int phkResulth; // [rsp+20h] [rbp-238h]
  unsigned int phkResulti; // [rsp+20h] [rbp-238h]
  unsigned int phkResultj; // [rsp+20h] [rbp-238h]
  unsigned int phkResultk; // [rsp+20h] [rbp-238h]
  unsigned int phkResultl; // [rsp+20h] [rbp-238h]
  int phkResultm; // [rsp+20h] [rbp-238h]
  int phkResultn; // [rsp+20h] [rbp-238h]
  unsigned int phkResulto; // [rsp+20h] [rbp-238h]
  unsigned int phkResultp; // [rsp+20h] [rbp-238h]
  int phkResultq; // [rsp+20h] [rbp-238h]
  unsigned int phkResultr; // [rsp+20h] [rbp-238h]
  int v179; // [rsp+50h] [rbp-208h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-200h] BYREF
  HKEY v181; // [rsp+60h] [rbp-1F8h] BYREF
  int v182; // [rsp+68h] [rbp-1F0h] BYREF
  HLOCAL pv; // [rsp+70h] [rbp-1E8h] BYREF
  LPCOLESTR lpsz; // [rsp+78h] [rbp-1E0h] BYREF
  int v185[2]; // [rsp+80h] [rbp-1D8h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-1D0h] BYREF
  _BYTE *v187; // [rsp+90h] [rbp-1C8h] BYREF
  char v188; // [rsp+98h] [rbp-1C0h]
  BYTE v189[8]; // [rsp+A0h] [rbp-1B8h] BYREF
  __int128 v190; // [rsp+A8h] [rbp-1B0h] BYREF
  __int64 v191; // [rsp+B8h] [rbp-1A0h]
  BYTE Data[16]; // [rsp+C0h] [rbp-198h] BYREF
  _BYTE v193[56]; // [rsp+D0h] [rbp-188h] BYREF
  __int64 v194; // [rsp+108h] [rbp-150h] BYREF
  _OWORD v195[2]; // [rsp+110h] [rbp-148h] BYREF
  BYTE v196[8]; // [rsp+130h] [rbp-128h] BYREF
  BYTE *v197; // [rsp+138h] [rbp-120h]
  __int64 v198; // [rsp+140h] [rbp-118h]
  LPCVOID v199; // [rsp+148h] [rbp-110h]
  HANDLE Token; // [rsp+150h] [rbp-108h]
  HKEY *p_hKey; // [rsp+158h] [rbp-100h]
  LPCOLESTR *p_lpsz; // [rsp+160h] [rbp-F8h]
  char v203; // [rsp+168h] [rbp-F0h]
  _QWORD v204[3]; // [rsp+170h] [rbp-E8h] BYREF
  BYTE *v205[2]; // [rsp+188h] [rbp-D0h] BYREF
  int v206; // [rsp+198h] [rbp-C0h]
  unsigned __int64 v207; // [rsp+1A0h] [rbp-B8h]
  BYTE *v208[2]; // [rsp+1A8h] [rbp-B0h] BYREF
  int v209; // [rsp+1B8h] [rbp-A0h]
  unsigned __int64 v210; // [rsp+1C0h] [rbp-98h]
  BYTE *lpData[2]; // [rsp+1C8h] [rbp-90h] BYREF
  int v212; // [rsp+1D8h] [rbp-80h]
  unsigned __int64 v213; // [rsp+1E0h] [rbp-78h]
  _BYTE v214[32]; // [rsp+1E8h] [rbp-70h] BYREF
  GUID pclsid; // [rsp+208h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  Token = a1;
  v199 = a12;
  lpsz = a5;
  v197 = a8;
  v198 = a10;
  v182 = a11;
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            a2,
                            a3) )
    {
      v18 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( *v18 > 4u )
      {
        pv = (HLOCAL)lpsz;
        hMem = a4;
        *(_QWORD *)v185 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v18,
          (unsigned int)&byte_18018D707,
          v19,
          v20,
          (__int64)v185,
          (__int64)&hMem,
          (__int64)&pv);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 4 )
    {
      pv = (HLOCAL)lpsz;
      hMem = a4;
      *(_QWORD *)v185 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_1801AB110,
        (unsigned int)byte_18018D6B5,
        v16,
        v17,
        (__int64)v185,
        (__int64)&hMem,
        (__int64)&pv);
    }
    pv = 0;
    v195[0] = *a2;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::open_and_watch_errors(
      &pv,
      v193,
      v195);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&pv);
    if ( cbData )
    {
      if ( a8 )
      {
        v23 = 0;
        if ( lpsz )
        {
          v24 = -1;
          v25 = -1;
          do
            ++v25;
          while ( lpsz[v25] );
          if ( v25 )
          {
            if ( a4 )
            {
              v26 = -1;
              do
                ++v26;
              while ( *((_WORD *)a4 + v26) );
              if ( v26 )
              {
                if ( a3 )
                {
                  v27 = -1;
                  do
                    ++v27;
                  while ( *(_WORD *)&a3[2 * v27] );
                  if ( v27 )
                  {
                    hKey = 0;
                    UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, &hKey);
                    if ( (UserPluginAuthenticatorsRegKey & 0x80000000) != 0 )
                    {
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                              v28,
                                              v30) )
                      {
                        v34 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                        if ( (unsigned int)*v34 > 3 )
                        {
                          v35 = &byte_18018D4AF;
LABEL_27:
                          v179 = UserPluginAuthenticatorsRegKey;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                            (_DWORD)v34,
                            (_DWORD)v35,
                            v32,
                            v33,
                            (__int64)&v179);
                        }
                      }
                      else if ( (unsigned int)dword_1801AB110 > 3 )
                      {
                        v35 = byte_18018D44B;
                        v34 = &dword_1801AB110;
                        goto LABEL_27;
                      }
                      v36 = tip2::details::reason_string(
                              (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::registry_access_failed",
                              v31);
                      tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(
                        v194 + 8,
                        9,
                        v36,
                        UserPluginAuthenticatorsRegKey);
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x16B,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                        (const char *)UserPluginAuthenticatorsRegKey,
                        phkResult);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                      return UserPluginAuthenticatorsRegKey;
                    }
                    pclsid = 0;
                    if ( CLSIDFromString(lpsz, &pclsid) )
                    {
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                              v39,
                                              v40) )
                      {
                        v44 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                        if ( (unsigned int)*v44 > 3 )
                        {
                          v45 = byte_18018D55D;
LABEL_35:
                          v179 = UserPluginAuthenticatorsRegKey;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                            (_DWORD)v44,
                            (_DWORD)v45,
                            v42,
                            v43,
                            (__int64)&v179);
                        }
                      }
                      else if ( (unsigned int)dword_1801AB110 > 3 )
                      {
                        v45 = byte_18018D50B;
                        v44 = &dword_1801AB110;
                        goto LABEL_35;
                      }
                      v46 = tip2::details::reason_string(
                              (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
                              v41);
                      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<unsigned short const *>(
                        v193,
                        2,
                        v46);
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x17D,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                        (const char *)0x80070057LL,
                        phkResult);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                      return 2147942487LL;
                    }
                    v187 = v193;
                    v188 = 1;
                    v181 = 0;
                    v47 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v181);
                    if ( RegOpenKeyExW(hKey, lpsz, 0, 0xF003Fu, v47) == 2 )
                    {
                      v49 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v181);
                      Key = RegCreateKeyExW(hKey, lpsz, 0, 0, 0, 0xF003Fu, 0, v49, 0);
                      if ( Key )
                      {
                        v51 = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x196,
                                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                (const char *)Key,
                                phkResultb);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                        v188 = 0;
                        CtapPluginAddAuthenticator_::_3_::_lambda_1_::operator()(&v187);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                        return v51;
                      }
                      p_hKey = &hKey;
                      p_lpsz = &lpsz;
                      v203 = 1;
                      v179 = 0;
                      *(_DWORD *)Data = 0;
                      std::wstring::wstring(lpData);
                      std::wstring::wstring(v208);
                      std::wstring::wstring(v205);
                      std::wstring::wstring(v214);
                      if ( (int)GetCallerPackageDetails(
                                  (_DWORD)a1,
                                  (unsigned int)&v179,
                                  (unsigned int)Data,
                                  (unsigned int)lpData,
                                  (__int64)v208,
                                  (__int64)v205,
                                  (__int64)v214) < 0 )
                      {
                        v53 = tip2::details::reason_string(
                                (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::package_verification_failed",
                                v52);
                        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v194 + 8, 5, v53);
                        v188 = 0;
                        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                                `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                                v54,
                                                v55) )
                        {
                          v58 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                          if ( (unsigned int)*v58 > 3 )
                          {
                            v59 = byte_18018D3F9;
LABEL_46:
                            v179 = -2147009196;
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                              (_DWORD)v58,
                              (_DWORD)v59,
                              v56,
                              v57,
                              (__int64)&v179);
                          }
                        }
                        else if ( (unsigned int)dword_1801AB110 > 3 )
                        {
                          v59 = byte_18018D309;
                          v58 = &dword_1801AB110;
                          goto LABEL_46;
                        }
                        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x1D5,
                            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                            (const char *)0x80073D54LL,
                            phkResultc);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                        }
                        else
                        {
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                        }
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                        return 2147958100LL;
                      }
                      v60 = (const BYTE *)lpData;
                      if ( v213 > 7 )
                        v60 = lpData[0];
                      v61 = RegSetValueExW(v181, L"PackageFullName", 0, 1u, v60, 2 * v212);
                      if ( v61 )
                      {
                        v62 = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x1E1,
                                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                (const char *)v61,
                                phkResultd);
                        std::wstring::_Tidy_deallocate(v214);
                        std::wstring::_Tidy_deallocate(v205);
                        std::wstring::_Tidy_deallocate(v208);
                        std::wstring::_Tidy_deallocate(lpData);
                        if ( hKey )
                          RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
LABEL_222:
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                        v188 = 0;
                        CtapPluginAddAuthenticator_::_3_::_lambda_1_::operator()(&v187);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                        return v62;
                      }
                      v63 = (const BYTE *)v208;
                      if ( v210 > 7 )
                        v63 = v208[0];
                      v64 = RegSetValueExW(v181, L"PackageFamilyName", 0, 1u, v63, 2 * v209);
                      if ( v64 )
                      {
                        v62 = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x1E5,
                                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                (const char *)v64,
                                phkResulte);
                        std::wstring::_Tidy_deallocate(v214);
                        std::wstring::_Tidy_deallocate(v205);
                        std::wstring::_Tidy_deallocate(v208);
                        std::wstring::_Tidy_deallocate(lpData);
                        if ( hKey )
                          RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                        goto LABEL_222;
                      }
                      v65 = (const BYTE *)v205;
                      if ( v207 > 7 )
                        v65 = v205[0];
                      v66 = RegSetValueExW(v181, L"PublisherDisplayName", 0, 1u, v65, 2 * v206);
                      if ( v66 )
                      {
                        v62 = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x1E9,
                                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                (const char *)v66,
                                phkResultf);
                        std::wstring::_Tidy_deallocate(v214);
                        std::wstring::_Tidy_deallocate(v205);
                        std::wstring::_Tidy_deallocate(v208);
                        std::wstring::_Tidy_deallocate(lpData);
                        if ( hKey )
                          RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                        goto LABEL_222;
                      }
                      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(
                        &pv,
                        &v194);
                      std::wstring::operator=((char *)pv + 368, v205);
                      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&pv);
                      v179 = 0;
                      v204[0] = L"ECDSA_P384";
                      v204[1] = L"ECDSA_P256";
                      v204[2] = L"RSA";
                      v190 = 0;
                      v191 = 0;
                      pv = v205;
                      hMem = v204;
                      std::vector<unsigned short const *>::_Construct_n<unsigned short const * const *,unsigned short const * const *>(
                        &v190,
                        3,
                        &hMem,
                        &pv);
                      v68 = (LPCWSTR *)*((_QWORD *)&v190 + 1);
                      for ( i = (LPCWSTR *)v190; i != v68; ++i )
                      {
                        if ( (int)GetTpmAlgCapability_0(*i) >= 0 && v179 == 1 )
                        {
                          v23 = *i;
                          break;
                        }
                      }
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
                      {
                        if ( !v23 )
                        {
                          v70 = tip2::details::reason_string(
                                  (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::unsupported_algorithm",
                                  v69);
                          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v194 + 8, 7, v70);
                          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                                  v71,
                                                  v72) )
                          {
                            v75 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                            if ( (unsigned int)*v75 <= 3 )
                              goto LABEL_87;
                            v76 = byte_18018D2B9;
                          }
                          else
                          {
                            if ( (unsigned int)dword_1801AB110 <= 3 )
                              goto LABEL_87;
                            v76 = byte_18018D261;
                            v75 = &dword_1801AB110;
                          }
                          v179 = -2146893783;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                            (_DWORD)v75,
                            (_DWORD)v76,
                            v73,
                            v74,
                            (__int64)&v179);
LABEL_87:
                          v77 = RegSetValueExW(v181, L"SigningKeyAlgorithm", 0, 1u, (const BYTE *)L"RSA", 8u);
                          if ( v77 )
                          {
                            v62 = wil::details::in1diag3::Return_Win32(
                                    retaddr,
                                    (void *)0x210,
                                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                    (const char *)v77,
                                    phkResultg);
                            std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                            std::wstring::_Tidy_deallocate(v214);
                            std::wstring::_Tidy_deallocate(v205);
                            std::wstring::_Tidy_deallocate(v208);
                            std::wstring::_Tidy_deallocate(lpData);
                            if ( hKey )
                              RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                            goto LABEL_222;
                          }
                          goto LABEL_113;
                        }
                        v78 = -1;
                        do
                          ++v78;
                        while ( v23[v78] );
                        v79 = RegSetValueExW(v181, L"SigningKeyAlgorithm", 0, 1u, (const BYTE *)v23, 2 * v78 + 2);
                        if ( v79 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x216,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v79,
                                  phkResulth);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
LABEL_113:
                        v89 = RegSetValueExW(v181, L"PackageSignatureKind", 0, 4u, Data, 4u);
                        if ( v89 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x235,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v89,
                                  phkResultj);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        v90 = -1;
                        do
                          ++v90;
                        while ( *(_WORD *)&a3[2 * v90] );
                        v91 = RegSetValueExW(v181, L"Name", 0, 1u, a3, 2 * v90);
                        if ( v91 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x239,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v91,
                                  phkResultk);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        v92 = -1;
                        do
                          ++v92;
                        while ( *((_WORD *)a4 + v92) );
                        v93 = RegSetValueExW(v181, L"RpId", 0, 1u, (const BYTE *)a4, 2 * v92);
                        if ( v93 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x23D,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v93,
                                  phkResultl);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        if ( a6 && a7 && *a6 && *a7 )
                        {
                          v179 = 0;
                          wil::make_unique_hlocal<unsigned char [0]>(&hMem, 0);
                          v185[0] = 0;
                          v94 = -1;
                          do
                            ++v94;
                          while ( a6[v94] );
                          *(_QWORD *)&v195[0] = a6;
                          *((_QWORD *)&v195[0] + 1) = v94;
                          v96 = DecodeBase64ToBinaryAndSaveToRegistry(v181, (__int64)&hMem);
                          if ( v96 < 0 )
                          {
                            v97 = tip2::details::reason_string(
                                    (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
                                    v95);
                            tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(
                              v194 + 8,
                              2,
                              v97,
                              (unsigned int)v96);
                            v188 = 0;
                            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                                    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                                    v98,
                                                    v99) )
                            {
                              v102 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                              if ( (unsigned int)*v102 > 3 )
                              {
                                v103 = byte_18018D091;
LABEL_141:
                                v185[0] = v96;
                                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                                  (_DWORD)v102,
                                  (_DWORD)v103,
                                  v100,
                                  v101,
                                  (__int64)v185);
                              }
                            }
                            else if ( (unsigned int)dword_1801AB110 > 3 )
                            {
                              v103 = byte_18018D151;
                              v102 = &dword_1801AB110;
                              goto LABEL_141;
                            }
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x25B,
                              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                              (const char *)(unsigned int)v96,
                              phkResultm);
                            v104 = hMem;
                            hMem = 0;
                            if ( v104 )
                              LocalFree(v104);
                            std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                            std::wstring::_Tidy_deallocate(v214);
                            std::wstring::_Tidy_deallocate(v205);
                            std::wstring::_Tidy_deallocate(v208);
                            std::wstring::_Tidy_deallocate(lpData);
                            if ( hKey )
                              RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
LABEL_218:
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                            return (unsigned int)v96;
                          }
                          v185[0] = 0;
                          wil::make_unique_hlocal<unsigned char [0]>(&pv, 0);
                          v179 = 1;
                          v105 = -1;
                          do
                            ++v105;
                          while ( a7[v105] );
                          *(_QWORD *)&v195[0] = a7;
                          *((_QWORD *)&v195[0] + 1) = v105;
                          v96 = DecodeBase64ToBinaryAndSaveToRegistry(v181, (__int64)&pv);
                          if ( v96 < 0 )
                          {
                            v107 = tip2::details::reason_string(
                                     (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
                                     v106);
                            tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(
                              v194 + 8,
                              2,
                              v107,
                              (unsigned int)v96);
                            v188 = 0;
                            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                                    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                                    v108,
                                                    v109) )
                            {
                              v112 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                              if ( (unsigned int)*v112 > 3 )
                              {
                                v113 = byte_18018D0F1;
LABEL_155:
                                v185[0] = v96;
                                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                                  (_DWORD)v112,
                                  (_DWORD)v113,
                                  v110,
                                  v111,
                                  (__int64)v185);
                              }
                            }
                            else if ( (unsigned int)dword_1801AB110 > 3 )
                            {
                              v113 = byte_18018CF69;
                              v112 = &dword_1801AB110;
                              goto LABEL_155;
                            }
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x277,
                              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                              (const char *)(unsigned int)v96,
                              phkResultn);
                            v114 = pv;
                            pv = 0;
                            if ( v114 )
                              LocalFree(v114);
                            v115 = hMem;
                            hMem = 0;
                            if ( v115 )
                              LocalFree(v115);
                            std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                            std::wstring::_Tidy_deallocate(v214);
                            std::wstring::_Tidy_deallocate(v205);
                            std::wstring::_Tidy_deallocate(v208);
                            std::wstring::_Tidy_deallocate(lpData);
                            if ( hKey )
                              RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                            goto LABEL_218;
                          }
                          v116 = pv;
                          pv = 0;
                          if ( v116 )
                            LocalFree(v116);
                          v117 = hMem;
                          hMem = 0;
                          if ( v117 )
                            LocalFree(v117);
                        }
                        *(_DWORD *)v196 = 0;
                        v118 = RegSetValueExW(v181, L"UvCount", 0, 4u, v196, 4u);
                        if ( v118 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x27E,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v118,
                                  phkResulto);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        v119 = RegSetValueExW(v181, L"AuthenticatorInfo", 0, 3u, v197, cbData);
                        if ( v119 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x281,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v119,
                                  phkResultp);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        pv = 0;
                        v96 = SaveAuthenticatorAaguidToRegistry(v181);
                        if ( v96 < 0 )
                        {
                          v121 = tip2::details::reason_string(
                                   (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
                                   v120);
                          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(
                            v194 + 8,
                            2,
                            v121,
                            (unsigned int)v96);
                          v188 = 0;
                          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                                  v122,
                                                  v123) )
                          {
                            v126 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                            if ( (unsigned int)*v126 <= 3 )
                              goto LABEL_182;
                            v127 = byte_18018D035;
                          }
                          else
                          {
                            if ( (unsigned int)dword_1801AB110 <= 3 )
                              goto LABEL_182;
                            v127 = byte_18018CFD1;
                            v126 = &dword_1801AB110;
                          }
                          v185[0] = v96;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                            (_DWORD)v126,
                            (_DWORD)v127,
                            v124,
                            v125,
                            (__int64)v185);
LABEL_182:
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x295,
                            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                            (const char *)(unsigned int)v96,
                            phkResultp);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_218;
                        }
                        v128 = pv;
                        if ( pv )
                        {
                          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(
                            &pv,
                            &v194);
                          v129 = -1;
                          do
                            ++v129;
                          while ( v128[v129] );
                          std::wstring::_Assign<unsigned short>((char *)pv + 336, v128);
                          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&pv);
                          CoTaskMemFree(v128);
                        }
                        if ( v182 && v198 )
                        {
                          std::vector<std::wstring>::vector<std::wstring>(v195, v198, v198 + 8LL * (unsigned int)v182);
                          wil::reg::set_value(v181);
                          std::vector<std::wstring>::_Tidy(v195);
                        }
                        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
                        {
                          v130 = (wil::reg::reg_view_details::reg_value_type_info *)v199;
                          if ( v199 )
                          {
                            v131 = -1;
                            do
                              ++v131;
                            while ( *((_WORD *)v199 + v131) );
                            if ( v131 )
                            {
                              hMem = (HLOCAL)-1LL;
                              v132 = Token;
                              v133 = wil::impersonate_token_nothrow(Token);
                              v96 = v133;
                              if ( v133 < 0 )
                              {
                                wil::details::in1diag3::_Log_Hr(
                                  retaddr,
                                  (void *)0x2AB,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)(unsigned int)v133,
                                  phkResultp);
                                goto LABEL_199;
                              }
                              pv = 0;
                              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
                                &pv,
                                0);
                              do
                                ++v24;
                              while ( *((_WORD *)v130 + v24) );
                              *(_QWORD *)&v195[0] = v130;
                              *((_QWORD *)&v195[0] + 1) = v24;
                              KeyFromKcmKeyName = CtapPluginInternal::GetKeyFromKcmKeyName(v132, v195, &pv, 0);
                              v96 = KeyFromKcmKeyName;
                              if ( KeyFromKcmKeyName < 0 )
                                wil::details::in1diag3::_Log_Hr(
                                  retaddr,
                                  (void *)0x2AF,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)(unsigned int)KeyFromKcmKeyName,
                                  phkResultp);
                              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&pv);
                              if ( v96 < 0 )
                              {
LABEL_199:
                                v135 = tip2::details::reason_string(
                                         (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_kcm_key",
                                         v134);
                                tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(
                                  v194 + 8,
                                  10,
                                  v135,
                                  (unsigned int)v96);
                                v188 = 0;
                                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                                        `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                                        v136,
                                                        v137) )
                                {
                                  v140 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                                  if ( (unsigned int)*v140 > 3 )
                                  {
                                    v141 = word_18018CF22;
LABEL_213:
                                    v182 = v96;
                                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                                      (_DWORD)v140,
                                      (_DWORD)v141,
                                      v138,
                                      v139,
                                      (__int64)&v182);
                                  }
                                }
                                else if ( (unsigned int)dword_1801AB110 > 3 )
                                {
                                  v141 = (__int16 *)byte_18018CED3;
                                  v140 = &dword_1801AB110;
                                  goto LABEL_213;
                                }
                                if ( v96 < 0 )
                                  wil::details::in1diag3::Return_Hr(
                                    retaddr,
                                    (void *)0x2C9,
                                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                    (const char *)(unsigned int)v96,
                                    phkResultp);
                                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hMem);
                                std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                                std::wstring::_Tidy_deallocate(v214);
                                std::wstring::_Tidy_deallocate(v205);
                                std::wstring::_Tidy_deallocate(v208);
                                std::wstring::_Tidy_deallocate(lpData);
                                if ( hKey )
                                  RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                                goto LABEL_218;
                              }
                              buffer_size_bytes = wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(
                                                    v130,
                                                    (const unsigned __int16 *)v134);
                              v144 = RegSetKeyValueW(v181, 0, L"UvKeyIdFromKcm", 1u, v130, buffer_size_bytes);
                              if ( v144 > 0 )
                                v144 = (unsigned __int16)v144 | 0x80070000;
                              if ( v144 < 0 )
                                wil::details::in1diag3::Throw_Hr(
                                  retaddr,
                                  (void *)0x1CBE,
                                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
                                  (const char *)(unsigned int)v144,
                                  phkResultq);
                              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hMem);
                            }
                          }
                        }
                        *(_DWORD *)v189 = 0;
                        v145 = RegSetValueExW(v181, L"State", 0, 4u, v189, 4u);
                        if ( v145 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x2D1,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v145,
                                  phkResultr);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        v182 = 0;
                        v146 = wil::reg::set_value_nothrow<unsigned int>(v181, 0, L"StateToggled", &v182);
                        if ( v146 < 0 )
                          wil::details::in1diag3::_Log_Hr(
                            retaddr,
                            (void *)0x2D3,
                            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                            (const char *)(unsigned int)v146,
                            phkResultr);
                        std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                        std::wstring::_Tidy_deallocate(v214);
                        std::wstring::_Tidy_deallocate(v205);
                        std::wstring::_Tidy_deallocate(v208);
                        std::wstring::_Tidy_deallocate(lpData);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                        return 0;
                      }
                      if ( v23 )
                      {
                        v87 = -1;
                        do
                          ++v87;
                        while ( v23[v87] );
                        v88 = RegSetValueExW(v181, L"SigningKeyAlgorithm", 0, 1u, (const BYTE *)v23, 2 * v87 + 2);
                        if ( v88 )
                        {
                          v62 = wil::details::in1diag3::Return_Win32(
                                  retaddr,
                                  (void *)0x230,
                                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                                  (const char *)v88,
                                  phkResulti);
                          std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                          std::wstring::_Tidy_deallocate(v214);
                          std::wstring::_Tidy_deallocate(v205);
                          std::wstring::_Tidy_deallocate(v208);
                          std::wstring::_Tidy_deallocate(lpData);
                          if ( hKey )
                            RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                          goto LABEL_222;
                        }
                        goto LABEL_113;
                      }
                      v80 = tip2::details::reason_string(
                              (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::unsupported_algorithm",
                              v69);
                      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v194 + 8, 7, v80);
                      v188 = 0;
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                              v81,
                                              v82) )
                      {
                        v85 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                        if ( (unsigned int)*v85 > 3 )
                        {
                          v86 = byte_18018D211;
LABEL_103:
                          v179 = -2146893783;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                            (_DWORD)v85,
                            (_DWORD)v86,
                            v83,
                            v84,
                            (__int64)&v179);
                        }
                      }
                      else if ( (unsigned int)dword_1801AB110 > 3 )
                      {
                        v86 = byte_18018D1B9;
                        v85 = &dword_1801AB110;
                        goto LABEL_103;
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x22B,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                        (const char *)0x80090029LL,
                        phkResultf);
                      std::vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>::~vector<_WEBAUTHN_CRED_WITH_HMAC_SECRET_SALT *>(&v190);
                      std::wstring::_Tidy_deallocate(v214);
                      std::wstring::_Tidy_deallocate(v205);
                      std::wstring::_Tidy_deallocate(v208);
                      std::wstring::_Tidy_deallocate(lpData);
                      if ( hKey )
                        RegDeleteKeyExW(hKey, lpsz, 0xF003Fu, 0);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                      return 2148073513LL;
                    }
                    v147 = tip2::details::reason_string(
                             (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::clsid_exists",
                             v48);
                    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v194 + 8, 6, v147);
                    v188 = 0;
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                            v148,
                                            v149) )
                    {
                      v152 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
                      if ( (unsigned int)*v152 > 3 )
                      {
                        v153 = word_18018D3B2;
LABEL_231:
                        v182 = -2146893809;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                          (_DWORD)v152,
                          (_DWORD)v153,
                          v150,
                          v151,
                          (__int64)&v182);
                      }
                    }
                    else if ( (unsigned int)dword_1801AB110 > 3 )
                    {
                      v153 = (__int16 *)byte_18018D363;
                      v152 = &dword_1801AB110;
                      goto LABEL_231;
                    }
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x1AB,
                        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                        (const char *)0x8009000FLL,
                        phkResulta);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v181);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
                    return 2148073487LL;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v21,
                            v22) )
    {
      v157 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
      if ( (unsigned int)*v157 > 3 )
      {
        v158 = word_18018D60A;
LABEL_240:
        v182 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v157,
          (_DWORD)v158,
          v155,
          v156,
          (__int64)&v182);
      }
    }
    else if ( (unsigned int)dword_1801AB110 > 3 )
    {
      v158 = (__int16 *)&byte_18018D5A7;
      v157 = &dword_1801AB110;
      goto LABEL_240;
    }
    v159 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::decoding_failed",
             v154);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v194 + 8, 4, v159);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80070057LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v193);
    result = 2147942487LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D9,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v37);
  }
  return result;
}

```

## disassembly

```asm
0x18010f334  push    rbx
0x18010f336  push    rsi
0x18010f337  push    rdi
0x18010f338  push    r12
0x18010f33a  push    r13
0x18010f33c  push    r14
0x18010f33e  push    r15
0x18010f340  sub     rsp, 220h
0x18010f347  mov     rax, cs:__security_cookie
0x18010f34e  xor     rax, rsp
0x18010f351  mov     [rsp+258h+var_40], rax
0x18010f359  mov     r13, r9
0x18010f35c  mov     r12, r8
0x18010f35f  mov     rbx, rdx
0x18010f362  mov     r14, rcx
0x18010f365  mov     [rsp+258h+Token], rcx
0x18010f36d  mov     rax, [rsp+258h+arg_58]
0x18010f375  mov     [rsp+258h+var_110], rax
0x18010f37d  mov     rax, [rsp+258h+arg_20]
0x18010f385  mov     [rsp+258h+lpsz], rax
0x18010f38a  mov     rdi, [rsp+258h+arg_38]
0x18010f392  mov     [rsp+258h+var_120], rdi
0x18010f39a  mov     rax, [rsp+258h+arg_48]
0x18010f3a2  mov     [rsp+258h+var_118], rax
0x18010f3aa  mov     ecx, [rsp+258h+arg_50]
0x18010f3b1  mov     [rsp+258h+var_1F0], ecx
0x18010f3b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18010f3bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18010f3c1  xor     r15d, r15d
0x18010f3c4  test    al, al
0x18010f3c6  jz      loc_18010F52F
0x18010f3cc  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x18010f3d1  mov     rcx, [rax+10h]
0x18010f3d5  mov     eax, [rcx]
0x18010f3d7  cmp     eax, 4
0x18010f3da  jbe     short loc_18010F426
0x18010f3dc  mov     rax, [rsp+258h+lpsz]
0x18010f3e1  mov     [rsp+258h+pv], rax
0x18010f3e6  mov     [rsp+258h+hMem], r13
0x18010f3ee  mov     qword ptr [rsp+258h+var_1D8], r12
0x18010f3f6  lea     rax, [rsp+258h+pv]
0x18010f3fb  mov     [rsp+258h+lpSecurityAttributes], rax
0x18010f400  lea     rax, [rsp+258h+hMem]
0x18010f408  mov     qword ptr [rsp+258h+samDesired], rax
0x18010f40d  lea     rax, [rsp+258h+var_1D8]
0x18010f415  mov     [rsp+258h+phkResult], rax
0x18010f41a  lea     rdx, byte_18018D707
0x18010f421  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18010f426  lea     rsi, dword_1801AB110
0x18010f42d  mov     [rsp+258h+pv], r15
0x18010f432  movups  xmm0, xmmword ptr [rbx]
0x18010f435  movdqu  [rsp+258h+var_148], xmm0
0x18010f43e  lea     r8, [rsp+258h+var_148]
0x18010f446  lea     rdx, [rsp+258h+var_188]
0x18010f44e  lea     rcx, [rsp+258h+pv]
0x18010f453  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::open_and_watch_errors(_GUID)
0x18010f458  lea     rcx, [rsp+258h+pv]
0x18010f45d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x18010f462  nop
0x18010f463  cmp     [rsp+258h+cbData], r15d
0x18010f46b  jz      loc_180111355
0x18010f471  test    rdi, rdi
0x18010f474  jz      loc_180111355
0x18010f47a  mov     rcx, [rsp+258h+lpsz]
0x18010f47f  xor     edi, edi
0x18010f481  test    rcx, rcx
0x18010f484  jz      loc_180111355
0x18010f48a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18010f48e  mov     rax, r15
0x18010f491  inc     rax
0x18010f494  cmp     [rcx+rax*2], di
0x18010f498  jnz     short loc_18010F491
0x18010f49a  test    rax, rax
0x18010f49d  jz      loc_180111355
0x18010f4a3  test    r13, r13
0x18010f4a6  jz      loc_180111355
0x18010f4ac  mov     rax, r15
0x18010f4af  inc     rax
0x18010f4b2  cmp     [r13+rax*2+0], di
0x18010f4b8  jnz     short loc_18010F4AF
0x18010f4ba  test    rax, rax
0x18010f4bd  jz      loc_180111355
0x18010f4c3  test    r12, r12
0x18010f4c6  jz      loc_180111355
0x18010f4cc  mov     rax, r15
0x18010f4cf  inc     rax
0x18010f4d2  cmp     [r12+rax*2], di
0x18010f4d7  jnz     short loc_18010F4CF
0x18010f4d9  test    rax, rax
0x18010f4dc  jz      loc_180111355
0x18010f4e2  mov     [rsp+258h+hKey], rdi
0x18010f4e7  lea     rdx, [rsp+258h+hKey]
0x18010f4ec  mov     rcx, r14
0x18010f4ef  call    GetUserPluginAuthenticatorsRegKey
0x18010f4f4  mov     ebx, eax
0x18010f4f6  test    eax, eax
0x18010f4f8  jns     loc_18010F623
0x18010f4fe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18010f505  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18010f50a  test    al, al
0x18010f50c  jz      loc_18010F597
0x18010f512  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x18010f517  mov     rcx, [rax+10h]
0x18010f51b  mov     eax, [rcx]
0x18010f51d  cmp     eax, 3
0x18010f520  jbe     loc_18010F5BF
0x18010f526  lea     rdx, byte_18018D4AF
0x18010f52d  jmp     short loc_18010F5AC
0x18010f52f  mov     eax, cs:dword_1801AB110
0x18010f535  cmp     eax, 4
0x18010f538  jbe     loc_18010F426
0x18010f53e  mov     rax, [rsp+258h+lpsz]
0x18010f543  mov     [rsp+258h+pv], rax
0x18010f548  mov     [rsp+258h+hMem], r13
0x18010f550  mov     qword ptr [rsp+258h+var_1D8], r12
0x18010f558  lea     rax, [rsp+258h+pv]
0x18010f55d  mov     [rsp+258h+lpSecurityAttributes], rax
0x18010f562  lea     rax, [rsp+258h+hMem]
0x18010f56a  mov     qword ptr [rsp+258h+samDesired], rax
0x18010f56f  lea     rax, [rsp+258h+var_1D8]
0x18010f577  mov     [rsp+258h+phkResult], rax
0x18010f57c  lea     rdx, byte_18018D6B5
0x18010f583  lea     rsi, dword_1801AB110
0x18010f58a  mov     rcx, rsi
0x18010f58d  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18010f592  jmp     loc_18010F42D
0x18010f597  mov     eax, cs:dword_1801AB110
0x18010f59d  cmp     eax, 3
0x18010f5a0  jbe     short loc_18010F5BF
0x18010f5a2  lea     rdx, byte_18018D44B
0x18010f5a9  mov     rcx, rsi
0x18010f5ac  lea     rax, [rsp+258h+var_208]
0x18010f5b1  mov     [rsp+258h+phkResult], rax; int
0x18010f5b6  mov     [rsp+258h+var_208], ebx
0x18010f5ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18010f5bf  lea     rcx, aWebauthnplugin_94; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x18010f5c6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18010f5cb  mov     r8, rax
0x18010f5ce  mov     edx, 9
0x18010f5d3  mov     rcx, [rsp+258h+var_150]
0x18010f5db  add     rcx, 8
0x18010f5df  mov     r9d, ebx
0x18010f5e2  call    ??$set_flag_value_without_lock@J@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(ushort,char const *,long)
0x18010f5e7  mov     rcx, [rsp+258h]; this
0x18010f5ef  mov     r9d, ebx; char *
0x18010f5f2  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010f5f9  mov     edx, 16Bh; void *
0x18010f5fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f603  nop
0x18010f604  lea     rcx, [rsp+258h+hKey]
0x18010f609  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f60e  nop
0x18010f60f  lea     rcx, [rsp+258h+var_188]
0x18010f617  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x18010f61c  mov     eax, ebx
0x18010f61e  jmp     loc_18011140A
0x18010f623  xorps   xmm0, xmm0
0x18010f626  movups  xmmword ptr [rsp+258h+pclsid.Data1], xmm0
0x18010f62e  lea     rdx, [rsp+258h+pclsid]; pclsid
0x18010f636  mov     rcx, [rsp+258h+lpsz]; lpsz
0x18010f63b  call    cs:__imp_CLSIDFromString
0x18010f641  test    eax, eax
0x18010f643  jz      loc_18010F6FD
0x18010f649  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18010f650  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18010f655  test    al, al
0x18010f657  jz      short loc_18010F672
0x18010f659  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x18010f65e  mov     rcx, [rax+10h]
0x18010f662  mov     eax, [rcx]
0x18010f664  cmp     eax, 3
0x18010f667  jbe     short loc_18010F69A
0x18010f669  lea     rdx, byte_18018D55D
0x18010f670  jmp     short loc_18010F687
0x18010f672  mov     eax, cs:dword_1801AB110
0x18010f678  cmp     eax, 3
0x18010f67b  jbe     short loc_18010F69A
0x18010f67d  lea     rdx, byte_18018D50B
0x18010f684  mov     rcx, rsi
0x18010f687  lea     rax, [rsp+258h+var_208]
0x18010f68c  mov     [rsp+258h+phkResult], rax; int
0x18010f691  mov     [rsp+258h+var_208], ebx
0x18010f695  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18010f69a  lea     rcx, aWebauthnplugin_117; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x18010f6a1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18010f6a6  mov     r8, rax
0x18010f6a9  mov     edx, 2
0x18010f6ae  lea     rcx, [rsp+258h+var_188]
0x18010f6b6  call    ??$set_flag_value@PEBG@?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDPEBG@Z; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<ushort const *>(ushort,char const *,ushort const *)
0x18010f6bb  mov     rcx, [rsp+258h]; this
0x18010f6c3  mov     r9d, 80070057h; char *
0x18010f6c9  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010f6d0  mov     edx, 17Dh; void *
0x18010f6d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f6da  nop
0x18010f6db  lea     rcx, [rsp+258h+hKey]
0x18010f6e0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f6e5  nop
0x18010f6e6  lea     rcx, [rsp+258h+var_188]
0x18010f6ee  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x18010f6f3  mov     eax, 80070057h
0x18010f6f8  jmp     loc_18011140A
0x18010f6fd  lea     rax, [rsp+258h+var_188]
0x18010f705  mov     [rsp+258h+var_1C8], rax
0x18010f70d  mov     [rsp+258h+var_1C0], 1
0x18010f715  mov     [rsp+258h+var_1F8], rdi
0x18010f71a  lea     rcx, [rsp+258h+var_1F8]
0x18010f71f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010f724  mov     [rsp+258h+phkResult], rax; phkResult
0x18010f729  mov     ebx, 0F003Fh
0x18010f72e  mov     r9d, ebx; samDesired
0x18010f731  xor     r8d, r8d; ulOptions
0x18010f734  mov     rdx, [rsp+258h+lpsz]; lpSubKey
0x18010f739  mov     rcx, [rsp+258h+hKey]; hKey
0x18010f73e  call    cs:__imp_RegOpenKeyExW
0x18010f744  cmp     eax, 2
0x18010f747  jnz     loc_180111249
0x18010f74d  lea     rcx, [rsp+258h+var_1F8]
0x18010f752  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18010f757  mov     [rsp+258h+lpdwDisposition], rdi; lpdwDisposition
0x18010f75c  mov     [rsp+258h+var_220], rax; phkResult
0x18010f761  mov     [rsp+258h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18010f766  mov     [rsp+258h+samDesired], ebx; samDesired
0x18010f76a  mov     dword ptr [rsp+258h+phkResult], edi; unsigned int
0x18010f76e  xor     r9d, r9d; lpClass
0x18010f771  xor     r8d, r8d; Reserved
0x18010f774  mov     rdx, [rsp+258h+lpsz]; lpSubKey
0x18010f779  mov     rcx, [rsp+258h+hKey]; hKey
0x18010f77e  call    cs:__imp_RegCreateKeyExW
0x18010f784  test    eax, eax
0x18010f786  jz      short loc_18010F7E6
0x18010f788  mov     rcx, [rsp+258h]; this
0x18010f790  mov     r9d, eax; char *
0x18010f793  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010f79a  mov     edx, 196h; void *
0x18010f79f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f7a4  mov     ebx, eax
0x18010f7a6  lea     rcx, [rsp+258h+var_1F8]
0x18010f7ab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f7b0  nop
0x18010f7b1  mov     [rsp+258h+var_1C0], dil
0x18010f7b9  lea     rcx, [rsp+258h+var_1C8]
0x18010f7c1  call    _CtapPluginAddAuthenticator____3____lambda_1___operator__
0x18010f7c6  nop
0x18010f7c7  lea     rcx, [rsp+258h+hKey]
0x18010f7cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010f7d1  nop
0x18010f7d2  lea     rcx, [rsp+258h+var_188]
0x18010f7da  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x18010f7df  mov     eax, ebx
0x18010f7e1  jmp     loc_18011140A
0x18010f7e6  lea     rax, [rsp+258h+hKey]
0x18010f7eb  mov     [rsp+258h+var_100], rax
0x18010f7f3  lea     rax, [rsp+258h+lpsz]
0x18010f7f8  mov     [rsp+258h+var_F8], rax
0x18010f800  mov     [rsp+258h+var_F0], 1
0x18010f808  mov     [rsp+258h+var_208], edi
0x18010f80c  mov     dword ptr [rsp+258h+Data], edi
0x18010f813  lea     rcx, [rsp+258h+lpData]
0x18010f81b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010f820  nop
0x18010f821  lea     rcx, [rsp+258h+var_B0]
0x18010f829  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010f82e  nop
0x18010f82f  lea     rcx, [rsp+258h+var_D0]
0x18010f837  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010f83c  nop
0x18010f83d  lea     rcx, [rsp+258h+var_70]
0x18010f845  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010f84a  nop
0x18010f84b  lea     rax, [rsp+258h+var_70]
0x18010f853  mov     [rsp+258h+lpSecurityAttributes], rax
0x18010f858  lea     rax, [rsp+258h+var_D0]
0x18010f860  mov     qword ptr [rsp+258h+samDesired], rax
0x18010f865  lea     rax, [rsp+258h+var_B0]
0x18010f86d  mov     [rsp+258h+phkResult], rax
0x18010f872  lea     r9, [rsp+258h+lpData]
0x18010f87a  lea     r8, [rsp+258h+Data]
0x18010f882  lea     rdx, [rsp+258h+var_208]
0x18010f887  mov     rcx, r14
0x18010f88a  call    ?GetCallerPackageDetails@@YAJQEAXAEAH1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@222@Z; GetCallerPackageDetails(void * const,int &,int &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x18010f88f  test    eax, eax
0x18010f891  jns     loc_18010FA4F
0x18010f897  lea     rcx, aWebauthnplugin_109; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x18010f89e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18010f8a3  mov     r8, rax
0x18010f8a6  mov     edx, 5
0x18010f8ab  mov     rcx, [rsp+258h+var_150]
0x18010f8b3  add     rcx, 8
0x18010f8b7  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x18010f8bc  mov     [rsp+258h+var_1C0], dil
0x18010f8c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18010f8cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18010f8d0  test    al, al
0x18010f8d2  jz      short loc_18010F8ED
0x18010f8d4  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x18010f8d9  mov     rcx, [rax+10h]
0x18010f8dd  mov     eax, [rcx]
0x18010f8df  cmp     eax, 3
0x18010f8e2  jbe     short loc_18010F919
  ... truncated ...
```
