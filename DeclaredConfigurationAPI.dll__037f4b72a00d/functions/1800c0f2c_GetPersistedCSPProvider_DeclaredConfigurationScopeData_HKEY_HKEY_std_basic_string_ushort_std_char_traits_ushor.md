# GetPersistedCSPProvider(DeclaredConfigurationScopeData *,HKEY__ *,HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,DCDocument *,DCPersistedDocType,ushort const *)

- ea: `0x1800c0f2c`
- end: `0x1800c3de6`
- name: `?GetPersistedCSPProvider@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2PEBGPEAVDCDocument@@W4DCPersistedDocType@@3@Z`
- size: `11962`
- prototype: ``
- caller_count: `3`
- callee_count: `60`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180076c10`
- `0x180078e2c`
- `0x18008f070`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000bf4c`
- `0x18000c8f4`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001438c`
- `0x1800143c8`
- `0x180018a20`
- `0x180018ac0`
- `0x180018b30`
- `0x180019208`
- `0x18001924c`
- `0x180019d38`
- `0x180019f08`
- `0x18001b394`
- `0x18001b65c`
- `0x18001bdd0`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001db48`
- `0x18001dea8`
- `0x18001df28`
- `0x18001df78`
- `0x180049100`
- `0x18004abf8`
- `0x18004b7f4`
- `0x18004cf10`
- `0x18004eb5c`
- `0x1800503b8`
- `0x180054814`
- `0x180056c10`
- `0x180058148`
- `0x18005860c`
- `0x18005f8cc`
- `0x18005fa30`
- `0x18005fcf8`
- `0x1800600bc`
- `0x18006026c`
- `0x180098e10`
- `0x1800a15ac`
- `0x1800ad74c`
- `0x1800adba4`
- `0x1800adcb0`
- `0x1800add44`
- `0x1800ae03c`
- `0x1800baf74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2c31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2e1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c321b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c32b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c349a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2b95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2c31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c2e1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c321b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c32b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c349a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c130d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c130d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2c6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2e65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c32f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c34e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2c6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c2e65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c32f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c34e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c123b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c129a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1b2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1b9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2dce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c31d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c344c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c123b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c129a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1b2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1b9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c2dce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c31d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c344c`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800c1371`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800c1371`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2c8b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c3311`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2c8b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c3311`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0fc7`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2399`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2496`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2535`
- `OLEAUT32!__imp_VariantInit` at `0x1800c25dc`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2848`
- `OLEAUT32!__imp_VariantInit` at `0x1800c288c`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2f02`
- `OLEAUT32!__imp_VariantInit` at `0x1800c35f8`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0fc7`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2399`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2496`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2535`
- `OLEAUT32!__imp_VariantInit` at `0x1800c25dc`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2848`
- `OLEAUT32!__imp_VariantInit` at `0x1800c288c`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2f02`
- `OLEAUT32!__imp_VariantInit` at `0x1800c35f8`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1064`
- `OLEAUT32!__imp_VariantClear` at `0x1800c10e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800c17c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1856`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1c8b`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1eee`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1f88`
- `OLEAUT32!__imp_VariantClear` at `0x1800c201a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c243c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c269a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c275b`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3124`
- `OLEAUT32!__imp_VariantClear` at `0x1800c36ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800c37c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3cfa`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3d69`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3d9c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1064`
- `OLEAUT32!__imp_VariantClear` at `0x1800c10e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800c17c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1856`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1c8b`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1eee`
- `OLEAUT32!__imp_VariantClear` at `0x1800c1f88`
- `OLEAUT32!__imp_VariantClear` at `0x1800c201a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c243c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c269a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c275b`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3124`
- `OLEAUT32!__imp_VariantClear` at `0x1800c36ca`
- `OLEAUT32!__imp_VariantClear` at `0x1800c37c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3cfa`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3d69`
- `OLEAUT32!__imp_VariantClear` at `0x1800c3d9c`

## string_xrefs

- `0x1800c20ac`: `typeConfig`
- `0x1800c23db`: `valueConfigured`
- `0x1800c1144`: `UriCount`
- `0x1800c1416`: `ResourceSuccessUri`
- `0x1800c14e6`: `ResourceFailureUri`
- `0x1800c15ac`: `ResourceInProgressUri`
- `0x1800c1e34`: `ResourceDeleteUri`
- `0x1800c1920`: `URI%d`
- `0x1800c1037`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c1395`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c173c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c1c08`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c27f7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c36b0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
__int64 __fastcall GetPersistedCSPProvider(
        __int64 a1,
        HKEY a2,
        HKEY a3,
        __int64 a4,
        unsigned __int16 *a5,
        __int64 a6,
        __int64 *a7,
        int a8,
        __int64 a9)
{
  __int64 v9; // r15
  unsigned __int16 *v12; // r13
  __int64 v13; // rax
  std::_Ref_count_base *v14; // rsi
  __int64 result; // rax
  const unsigned __int16 *v16; // rdx
  int RegistryString; // ebx
  unsigned __int16 *v18; // rcx
  __int64 v19; // r8
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  const WCHAR *v23; // rdx
  LSTATUS v24; // ebx
  LSTATUS v25; // ebx
  DWORD i; // r14d
  const unsigned __int16 *v27; // rbx
  LSTATUS v28; // eax
  signed int v29; // esi
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // r8
  _QWORD *v36; // r14
  __int64 v37; // r8
  __int64 v38; // rdx
  int v39; // ebx
  int ResultData_1; // eax
  LONG lVal; // ecx
  __int64 v42; // r8
  __int64 v43; // rdx
  int v44; // eax
  LONG v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // eax
  __int64 v48; // rbx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rbx
  __int64 v53; // r8
  __int64 v54; // rax
  __int64 v55; // rax
  const WCHAR *v56; // rdx
  LSTATUS v57; // ebx
  const WCHAR *v58; // rdx
  LSTATUS v59; // ebx
  _QWORD *v60; // rax
  std::_Ref_count_base *v61; // r13
  DWORD v62; // esi
  int v63; // ebx
  __int64 v64; // r8
  __int64 v65; // r8
  __int64 v66; // rdx
  int v67; // ebx
  int v68; // eax
  LONG v69; // ecx
  __int64 v70; // r8
  __int64 v71; // rdx
  int v72; // eax
  LONG v73; // ecx
  __int64 v74; // r8
  __int64 v75; // rdx
  int v76; // eax
  LONG v77; // ecx
  __int64 v78; // rax
  __int64 v79; // r8
  __int64 v80; // r8
  __int64 v81; // r8
  int v82; // eax
  int v83; // ecx
  __int64 v84; // r8
  unsigned __int16 *v85; // rdx
  __int64 v86; // r8
  unsigned __int16 *v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rdx
  int RegistryDWORD; // ebx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // rsi
  int v94; // ecx
  int v95; // ecx
  int v96; // ecx
  int v97; // ecx
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // r8
  __int64 v101; // rdx
  VARIANTARG *v102; // rcx
  __int64 v103; // r8
  __int64 v104; // rdx
  int RegistryBinary; // ebx
  int v106; // esi
  int v107; // ecx
  int v108; // ecx
  int v109; // ecx
  int v110; // ecx
  __int64 v111; // r8
  _QWORD *v112; // r8
  __int64 *v113; // rdx
  unsigned __int16 *v114; // r14
  int v115; // ebx
  OLECHAR *v116; // r15
  HKEY v117; // rcx
  LSTATUS v118; // eax
  signed int v119; // ebx
  LSTATUS v120; // eax
  unsigned __int64 v121; // rbx
  unsigned __int64 v122; // rax
  BYTE *v123; // rax
  BYTE *v124; // rsi
  LSTATUS v125; // eax
  unsigned __int16 v126; // dx
  LONG v127; // esi
  HKEY v128; // rcx
  LSTATUS v129; // eax
  signed int v130; // ebx
  LSTATUS Value; // eax
  _QWORD *v132; // r8
  __int64 *v133; // rdx
  unsigned __int16 *v134; // r14
  int v135; // ebx
  VARTYPE v136; // ax
  OLECHAR *v137; // r15
  HKEY v138; // rcx
  LSTATUS v139; // eax
  signed int v140; // ebx
  LSTATUS v141; // eax
  unsigned __int64 v142; // rbx
  unsigned __int64 v143; // rax
  BYTE *v144; // rax
  BYTE *v145; // rsi
  LSTATUS v146; // eax
  unsigned __int16 v147; // dx
  LONG v148; // esi
  HKEY v149; // rcx
  LSTATUS v150; // eax
  signed int v151; // ebx
  LSTATUS v152; // eax
  __int64 v153; // rdx
  __int64 v154; // r8
  int v155; // eax
  int v156; // r8d
  int v157; // eax
  __int64 v158; // rdi
  unsigned __int16 *v159; // rsi
  __int64 v160; // rax
  DWORD v161; // esi
  DWORD v162; // esi
  DWORD v163; // esi
  DWORD v164; // esi
  DWORD v165; // esi
  DWORD v166; // esi
  __int64 v167; // rax
  int v168; // eax
  _QWORD *v169; // rcx
  __int64 v170; // r9
  int phkResult; // [rsp+20h] [rbp-478h]
  int phkResulta; // [rsp+20h] [rbp-478h]
  int phkResultb; // [rsp+20h] [rbp-478h]
  int phkResultc; // [rsp+20h] [rbp-478h]
  int phkResultd; // [rsp+20h] [rbp-478h]
  int phkResulte; // [rsp+20h] [rbp-478h]
  int phkResultf; // [rsp+20h] [rbp-478h]
  int phkResultg; // [rsp+20h] [rbp-478h]
  int phkResulth; // [rsp+20h] [rbp-478h]
  int phkResulti; // [rsp+20h] [rbp-478h]
  int phkResultj; // [rsp+20h] [rbp-478h]
  HKEY v182; // [rsp+60h] [rbp-438h] BYREF
  DWORD Type[2]; // [rsp+68h] [rbp-430h] BYREF
  HKEY v184; // [rsp+70h] [rbp-428h] BYREF
  DWORD cbData; // [rsp+78h] [rbp-420h] BYREF
  void *Block; // [rsp+80h] [rbp-418h] BYREF
  unsigned __int16 *v187; // [rsp+88h] [rbp-410h] BYREF
  std::_Ref_count_base *v188; // [rsp+90h] [rbp-408h]
  BYTE Data[4]; // [rsp+98h] [rbp-400h] BYREF
  unsigned __int16 *v190; // [rsp+A0h] [rbp-3F8h] BYREF
  HKEY v191; // [rsp+A8h] [rbp-3F0h] BYREF
  LPWSTR lpName; // [rsp+B0h] [rbp-3E8h] BYREF
  __int64 v193; // [rsp+B8h] [rbp-3E0h]
  int v194[2]; // [rsp+C0h] [rbp-3D8h]
  __int64 v195; // [rsp+C8h] [rbp-3D0h] BYREF
  std::_Ref_count_base *v196[2]; // [rsp+D0h] [rbp-3C8h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-3B8h] BYREF
  unsigned __int16 *v198; // [rsp+F8h] [rbp-3A0h] BYREF
  unsigned __int16 *v199; // [rsp+100h] [rbp-398h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+108h] [rbp-390h] BYREF
  unsigned __int16 *v201; // [rsp+110h] [rbp-388h]
  std::_Ref_count_base *v202[2]; // [rsp+118h] [rbp-380h] BYREF
  HKEY v203; // [rsp+128h] [rbp-370h] BYREF
  unsigned __int16 *v204; // [rsp+130h] [rbp-368h] BYREF
  __int64 v205; // [rsp+138h] [rbp-360h]
  unsigned __int16 *v206; // [rsp+140h] [rbp-358h] BYREF
  DWORD cSubKeys; // [rsp+148h] [rbp-350h] BYREF
  unsigned int v208; // [rsp+14Ch] [rbp-34Ch] BYREF
  unsigned int v209; // [rsp+150h] [rbp-348h]
  unsigned int v210; // [rsp+154h] [rbp-344h]
  VARIANTARG v211; // [rsp+158h] [rbp-340h] BYREF
  VARIANTARG v212; // [rsp+170h] [rbp-328h] BYREF
  VARIANTARG v213; // [rsp+188h] [rbp-310h] BYREF
  __int64 v214; // [rsp+1A0h] [rbp-2F8h] BYREF
  int v215[2]; // [rsp+1A8h] [rbp-2F0h]
  const void *v216[2]; // [rsp+1B0h] [rbp-2E8h] BYREF
  _BYTE v217[64]; // [rsp+1C0h] [rbp-2D8h] BYREF
  char v218; // [rsp+200h] [rbp-298h]
  unsigned __int16 *v219; // [rsp+210h] [rbp-288h] BYREF
  unsigned __int16 *v220; // [rsp+218h] [rbp-280h] BYREF
  unsigned __int16 *v221; // [rsp+220h] [rbp-278h] BYREF
  unsigned __int16 *v222; // [rsp+228h] [rbp-270h] BYREF
  HKEY hKey; // [rsp+230h] [rbp-268h]
  HKEY v224; // [rsp+238h] [rbp-260h] BYREF
  std::_Ref_count_base *v225; // [rsp+240h] [rbp-258h]
  VARIANTARG v226; // [rsp+248h] [rbp-250h] BYREF
  __int64 v227; // [rsp+260h] [rbp-238h] BYREF
  std::_Ref_count_base *v228; // [rsp+268h] [rbp-230h]
  char v229[16]; // [rsp+270h] [rbp-228h] BYREF
  unsigned __int16 *v230; // [rsp+280h] [rbp-218h]
  __int64 v231; // [rsp+288h] [rbp-210h]
  VARIANTARG v232; // [rsp+290h] [rbp-208h] BYREF
  VARIANTARG v233; // [rsp+2B0h] [rbp-1E8h] BYREF
  LPCWSTR v234[4]; // [rsp+2D0h] [rbp-1C8h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+2F0h] [rbp-1A8h] BYREF
  _BYTE v236[32]; // [rsp+310h] [rbp-188h] BYREF
  _BYTE v237[64]; // [rsp+330h] [rbp-168h] BYREF
  char *v238[4]; // [rsp+370h] [rbp-128h] BYREF
  char *v239; // [rsp+390h] [rbp-108h] BYREF
  char *v240; // [rsp+3B0h] [rbp-E8h] BYREF
  char *v241; // [rsp+3D0h] [rbp-C8h] BYREF
  char *v242; // [rsp+3F0h] [rbp-A8h] BYREF
  char *v243; // [rsp+410h] [rbp-88h] BYREF
  unsigned __int16 v244[16]; // [rsp+430h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+0h]

  v9 = a4;
  v205 = a4;
  v224 = a3;
  hKey = a2;
  *(_QWORD *)v215 = a1;
  v231 = a4;
  v12 = a5;
  v201 = a5;
  v230 = a5;
  v193 = a6;
  *(_QWORD *)v194 = a9;
  VariantInit(&pvarg);
  try
  {
    *(_OWORD *)v196 = 0;
    *(_OWORD *)v202 = 0;
    v244[0] = 0;
    v13 = std::make_shared<DCCSP,>(&v187);
    std::shared_ptr<DCURI>::operator=(v196, v13);
    if ( v188 )
      std::_Ref_count_base::_Decref(v188);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x750,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)0x8007000ELL,
      phkResulte);
    if ( v196[1] )
      std::_Ref_count_base::_Decref(v196[1]);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v231);
    std::wstring::_Tidy_deallocate(v230);
    return 2147942414LL;
  }
  v14 = v196[0];
  if ( !v196[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)0x8007000ELL,
      phkResultf);
    if ( v196[1] )
      std::_Ref_count_base::_Decref(v196[1]);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v9);
    std::wstring::_Tidy_deallocate(a5);
    return 2147942414LL;
  }
  *((_DWORD *)v196[0] + 32) = 1;
  v187 = 0;
  if ( *((_QWORD *)a5 + 3) <= 7u )
    v16 = a5;
  else
    v16 = *(const unsigned __int16 **)a5;
  RegistryString = DCCDNUtil_GetRegistryString(a3, v16, L"csp", &v187);
  if ( RegistryString < 0 )
  {
LABEL_12:
    if ( !v196[1] )
      goto LABEL_14;
    std::_Ref_count_base::_Decref(v196[1]);
    goto LABEL_14;
  }
  v190 = v187;
  v19 = -1;
  do
    ++v19;
  while ( v187[v19] );
  std::wstring::_Assign<unsigned short>((char **)v14 + 11, v187, (char *)v19);
  v208 = 0;
  if ( *(_QWORD *)(v9 + 24) <= 7u )
    v20 = (const unsigned __int16 *)v9;
  else
    v20 = *(const unsigned __int16 **)v9;
  RegistryString = DCCDNUtil_GetRegistryDWORD(a2, v20, L"UriCount", &v208);
  if ( RegistryString < 0 )
  {
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
    goto LABEL_12;
  }
  if ( a8 == 2 )
  {
    Type[0] = 0;
    if ( *(_QWORD *)(v9 + 24) <= 7u )
      v21 = (const unsigned __int16 *)v9;
    else
      v21 = *(const unsigned __int16 **)v9;
    DCCDNUtil_GetRegistryDWORD(a2, v21, L"atomicFlagNecessary", Type);
    *((_BYTE *)v14 + 80) = Type[0] != 0;
    Type[0] = 0;
    if ( *(_QWORD *)(v9 + 24) <= 7u )
      v22 = (const unsigned __int16 *)v9;
    else
      v22 = *(const unsigned __int16 **)v9;
    DCCDNUtil_GetRegistryDWORD(a2, v22, L"oneTimeExecutionNodeNecessary", Type);
    *((_BYTE *)v14 + 81) = Type[0] != 0;
    v203 = 0;
    v191 = 0;
    *(_QWORD *)&v213.vt = &v203;
    v213.llVal = 0;
    *((_BYTE *)&v213.decVal + 16) = 1;
    if ( *(_QWORD *)(v9 + 24) <= 7u )
      v23 = (const WCHAR *)v9;
    else
      v23 = *(const WCHAR **)v9;
    v24 = RegOpenKeyExW(hKey, v23, 0, 0x20119u, (PHKEY)&v213.llVal);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v213);
    if ( !v24 )
    {
      *(_QWORD *)&v213.vt = &v191;
      v213.llVal = 0;
      *((_BYTE *)&v213.decVal + 16) = 1;
      v25 = RegOpenKeyExW(v203, L"resourceTracking", 0, 0x20119u, (PHKEY)&v213.llVal);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v213);
      if ( !v25 )
      {
        cSubKeys = 0;
        cbMaxSubKeyLen = 0;
        if ( !RegQueryInfoKeyW(v191, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= cSubKeys )
              goto LABEL_76;
            wil::make_hlocal_string_nothrow((wil *)&lpName, 0, cbMaxSubKeyLen + 1);
            v27 = lpName;
            if ( !lpName )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x796,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                (const char *)0x8007000ELL,
                phkResultg);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v203);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
              if ( !v196[1] )
                goto LABEL_493;
              std::_Ref_count_base::_Decref(v196[1]);
              goto LABEL_493;
            }
            v28 = RegEnumKeyW(v191, i, lpName, cbMaxSubKeyLen + 1);
            v29 = v28;
            if ( v28 > 0 )
              v29 = (unsigned __int16)v28 | 0x80070000;
            if ( v29 < 0 )
              break;
            ResourceValidationUrisAndValues::ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v238);
            v187 = 0;
            v29 = DCCDNUtil_GetRegistryString(v191, v27, L"ResourceSuccessUri", &v187);
            if ( v29 < 0 )
            {
              ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v238);
LABEL_43:
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v203);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
              if ( v196[1] )
                std::_Ref_count_base::_Decref(v196[1]);
              RegistryString = v29;
              goto LABEL_14;
            }
            v206 = v187;
            v30 = -1;
            do
              ++v30;
            while ( v187[v30] );
            std::wstring::_Assign<unsigned short>(v238, v187, (char *)v30);
            v187 = 0;
            if ( DCCDNUtil_GetRegistryString(v191, v27, L"ResourceSuccessValues", &v187) >= 0 )
            {
              v31 = -1;
              do
                ++v31;
              while ( v187[v31] );
              std::wstring::_Assign<unsigned short>(&v239, v187, (char *)v31);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v187);
            }
            v187 = 0;
            if ( DCCDNUtil_GetRegistryString(v191, v27, L"ResourceFailureUri", &v187) >= 0 )
            {
              v32 = -1;
              do
                ++v32;
              while ( v187[v32] );
              std::wstring::_Assign<unsigned short>(&v240, v187, (char *)v32);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v187);
            }
            v187 = 0;
            if ( DCCDNUtil_GetRegistryString(v191, v27, L"ResourceFailureValues", &v187) >= 0 )
            {
              v33 = -1;
              do
                ++v33;
              while ( v187[v33] );
              std::wstring::_Assign<unsigned short>(&v241, v187, (char *)v33);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v187);
            }
            v187 = 0;
            if ( DCCDNUtil_GetRegistryString(v191, v27, L"ResourceInProgressUri", &v187) >= 0 )
            {
              v34 = -1;
              do
                ++v34;
              while ( v187[v34] );
              std::wstring::_Assign<unsigned short>(&v242, v187, (char *)v34);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v187);
            }
            v187 = 0;
            if ( DCCDNUtil_GetRegistryString(v191, v27, L"ResourceInProgressValues", &v187) >= 0 )
            {
              v35 = -1;
              do
                ++v35;
              while ( v187[v35] );
              std::wstring::_Assign<unsigned short>(&v243, v187, (char *)v35);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v187);
            }
            try
            {
              v14 = v196[0];
              if ( *((_QWORD *)v196[0] + 6) == *((_QWORD *)v196[0] + 7) )
              {
                std::vector<ResourceValidationUrisAndValues>::_Emplace_reallocate<ResourceValidationUrisAndValues const &>(
                  (__int64 *)v196[0] + 5,
                  *((_QWORD *)v196[0] + 6),
                  (const struct ResourceValidationUrisAndValues *)v238);
              }
              else
              {
                ResourceValidationUrisAndValues::ResourceValidationUrisAndValues(
                  *((ResourceValidationUrisAndValues **)v196[0] + 6),
                  (const struct ResourceValidationUrisAndValues *)v238);
                *((_QWORD *)v14 + 6) += 192LL;
              }
            }
            catch ( std::bad_alloc )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7D4,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                (const char *)0x8007000ELL,
                phkResultd);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v206);
              ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v238);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v203);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
LABEL_490:
              if ( v196[1] )
                std::_Ref_count_base::_Decref(v196[1]);
              v12 = v230;
              v9 = v231;
LABEL_493:
              RegistryString = -2147024882;
LABEL_14:
              VariantClear(&pvarg);
              std::wstring::_Tidy_deallocate(v9);
              v18 = v12;
              goto LABEL_15;
            }
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v206);
            ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v238);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x79D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)(unsigned int)v29,
            phkResultg);
          goto LABEL_43;
        }
      }
    }
LABEL_76:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v203);
  }
  VariantClear(&pvarg);
  pvarg.vt = 3;
  v36 = a7 + 12;
  if ( (unsigned __int64)a7[15] <= 7 )
    LODWORD(v37) = (_DWORD)a7 + 96;
  else
    v37 = *v36;
  if ( (unsigned __int64)a7[3] <= 7 )
    LODWORD(v38) = (_DWORD)a7;
  else
    v38 = *a7;
  v39 = v215[0];
  ResultData_1 = DeclaredConfigurationStore_ReadResultData_1(
                   v215[0],
                   v38,
                   v37,
                   v194[0],
                   v193,
                   0,
                   L"state",
                   (DWORD)&pvarg);
  lVal = 0;
  if ( ResultData_1 >= 0 )
    lVal = pvarg.lVal;
  *((_DWORD *)v14 + 30) = lVal;
  VariantClear(&pvarg);
  pvarg.vt = 3;
  if ( (unsigned __int64)a7[15] <= 7 )
    LODWORD(v42) = (_DWORD)a7 + 96;
  else
    v42 = *v36;
  if ( (unsigned __int64)a7[3] <= 7 )
    LODWORD(v43) = (_DWORD)a7;
  else
    v43 = *a7;
  v44 = DeclaredConfigurationStore_ReadResultData_1(v39, v43, v42, v194[0], v193, 0, L"hresultAtomic", (DWORD)&pvarg);
  v45 = 0;
  if ( v44 >= 0 )
    v45 = pvarg.lVal;
  *((_DWORD *)v14 + 33) = v45;
  v46 = 1;
  v47 = 0;
  while ( 1 )
  {
    v209 = v47;
    v210 = v46;
    if ( v47 >= v208 )
      break;
    v195 = 0;
    v184 = 0;
    v204 = 0;
    v214 = 0;
    cbData = 0;
    LODWORD(v182) = 0;
    RegistryString = StringCchPrintfW(v244, 0xFu, L"URI%d", v46);
    if ( RegistryString < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
      if ( v202[1] )
        std::_Ref_count_base::_Decref(v202[1]);
      goto LABEL_12;
    }
    std::wstring::wstring((__int64)lpSubKey);
    std::wstring::wstring((__int64)v234);
    try
    {
      v48 = std::wstring::wstring((__int64)v236, (__int64)v244);
      v49 = std::wstring::wstring((__int64)v237, (__int64)L"\\");
      v50 = std::operator+<unsigned short>(&v232, v9, v49);
      v51 = std::operator+<unsigned short>(&v233, v50, v48);
      std::wstring::operator=(lpSubKey, v51);
      std::wstring::_Tidy_deallocate(&v233);
      std::wstring::_Tidy_deallocate(&v232);
      std::wstring::_Tidy_deallocate(v237);
      std::wstring::_Tidy_deallocate(v236);
      v52 = std::wstring::wstring((__int64)&v232, (__int64)v244);
      v53 = std::wstring::wstring((__int64)&v233, (__int64)L"\\");
      v54 = std::operator+<unsigned short>(v237, v12, v53);
      v55 = std::operator+<unsigned short>(v236, v54, v52);
      std::wstring::operator=(v234, v55);
      std::wstring::_Tidy_deallocate(v236);
      std::wstring::_Tidy_deallocate(v237);
      std::wstring::_Tidy_deallocate(&v233);
      std::wstring::_Tidy_deallocate(&v232);
      *(_QWORD *)&v232.vt = &v195;
      v232.llVal = 0;
      *((_BYTE *)&v232.decVal + 16) = 1;
      v56 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v56 = lpSubKey[0];
      v57 = RegOpenKeyExW(hKey, v56, 0, 0x20119u, (PHKEY)&v232.llVal);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v232);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x846,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
        (const char *)0x8007000ELL,
        phkResultc);
      goto LABEL_488;
    }
    if ( !v57 )
    {
      *(_QWORD *)&v232.vt = &v184;
      v232.llVal = 0;
      *((_BYTE *)&v232.decVal + 16) = 1;
      v58 = (const WCHAR *)v234;
      if ( v234[3] > (LPCWSTR)7 )
        v58 = v234[0];
      v59 = RegOpenKeyExW(v224, v58, 0, 0x20119u, (PHKEY)&v232.llVal);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v232);
      if ( !v59 )
      {
        try
        {
          v60 = std::make_shared<DCURI,>(&v227);
          std::shared_ptr<DCURI>::operator=(v202, v60);
          if ( v228 )
            std::_Ref_count_base::_Decref(v228);
        }
        catch ( std::bad_alloc )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85C,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)0x8007000ELL,
            phkResultb);
LABEL_488:
          std::wstring::_Tidy_deallocate(v234);
          std::wstring::_Tidy_deallocate(lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
          if ( !v202[1] )
            goto LABEL_490;
          std::_Ref_count_base::_Decref(v202[1]);
          goto LABEL_490;
        }
        v61 = v202[0];
        if ( !v202[0] )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x858,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)0x8007000ELL,
            phkResulth);
          std::wstring::_Tidy_deallocate(v234);
          std::wstring::_Tidy_deallocate(lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
          if ( v202[1] )
            std::_Ref_count_base::_Decref(v202[1]);
          if ( v196[1] )
            std::_Ref_count_base::_Decref(v196[1]);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v9);
          std::wstring::_Tidy_deallocate(v201);
          return 2147942414LL;
        }
        Type[0] = 0;
        *(_DWORD *)Data = 0;
        v220 = 0;
        v221 = 0;
        v222 = 0;
        v219 = 0;
        v206 = 0;
        v187 = 0;
        lpName = 0;
        LODWORD(Block) = 0;
        if ( DCCDNUtil_GetRegistryDWORD(v184, 0, L"typeStored", Type) < 0 )
          goto LABEL_487;
        v62 = Type[0];
        *((_DWORD *)v61 + 96) = Type[0];
        Type[0] = 0;
        DCCDNUtil_GetRegistryDWORD(v184, 0, L"operation", Type);
        *((_DWORD *)v61 + 46) = Type[0];
        if ( a8 == 2 )
        {
          Type[0] = 0;
          DCCDNUtil_GetRegistryDWORD(v184, 0, L"atomicFlagNecessary", Type);
          *((_BYTE *)v61 + 190) = Type[0] != 0;
          Type[0] = 0;
          DCCDNUtil_GetRegistryDWORD(v184, 0, L"instanceDataAllowed", Type);
          *((_BYTE *)v61 + 191) = Type[0] != 0;
          Type[0] = 0;
          DCCDNUtil_GetRegistryDWORD(v184, 0, L"executeNodeNecessary", Type);
          *((_BYTE *)v61 + 192) = Type[0] != 0;
          Type[0] = 0;
          DCCDNUtil_GetRegistryDWORD(v184, 0, L"checkValueNodeNecessary", Type);
          *((_BYTE *)v61 + 193) = Type[0] != 0;
          v216[0] = 0;
          *(_QWORD *)&v232.vt = v216;
          v232.llVal = 0;
          *((_BYTE *)&v232.decVal + 16) = 1;
          v63 = DCCDNUtil_GetRegistryString(v184, 0, L"ResourceDeleteUri", &v232.bstrVal);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v232);
          if ( v63 >= 0 )
          {
            v64 = -1;
            do
              ++v64;
            while ( *((_WORD *)v216[0] + v64) );
            std::wstring::_Assign<unsigned short>((char **)v61 + 29, v216[0], (char *)v64);
            *(const void **)&v232.vt = v216[0];
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<unsigned short *>(
              (char *)v196[0] + 64,
              v229,
              &v232);
          }
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v216);
        }
        Type[0] = 0;
        DCCDNUtil_GetRegistryDWORD(v184, 0, L"RecursiveQueryLevel", Type);
        *((_DWORD *)v61 + 49) = Type[0];
        VariantClear(&pvarg);
        pvarg.vt = 3;
        if ( (unsigned __int64)a7[15] <= 7 )
          LODWORD(v65) = (_DWORD)v36;
        else
          v65 = *v36;
        if ( (unsigned __int64)a7[3] <= 7 )
          LODWORD(v66) = (_DWORD)a7;
        else
          v66 = *a7;
        v67 = v215[0];
        v68 = DeclaredConfigurationStore_ReadResultData_1(
                v215[0],
                v66,
                v65,
                v194[0],
                v193,
                (__int64)v244,
                L"httpstatus",
                (DWORD)&pvarg);
        v69 = 0;
        if ( v68 >= 0 )
          v69 = pvarg.lVal;
        *((_DWORD *)v61 + 43) = v69;
        VariantClear(&pvarg);
        pvarg.vt = 3;
        if ( (unsigned __int64)a7[15] <= 7 )
          LODWORD(v70) = (_DWORD)v36;
        else
          v70 = *v36;
        if ( (unsigned __int64)a7[3] <= 7 )
          LODWORD(v71) = (_DWORD)a7;
        else
          v71 = *a7;
        v72 = DeclaredConfigurationStore_ReadResultData_1(
                v67,
                v71,
                v70,
                v194[0],
                v193,
                (__int64)v244,
                L"hresult",
                (DWORD)&pvarg);
        v73 = 0;
        if ( v72 >= 0 )
          v73 = pvarg.lVal;
        *((_DWORD *)v61 + 42) = v73;
        VariantClear(&pvarg);
        pvarg.vt = 3;
        if ( (unsigned __int64)a7[15] <= 7 )
          LODWORD(v74) = (_DWORD)v36;
        else
          v74 = *v36;
        if ( (unsigned __int64)a7[3] <= 7 )
          LODWORD(v75) = (_DWORD)a7;
        else
          v75 = *a7;
        v76 = DeclaredConfigurationStore_ReadResultData_1(
                v67,
                v75,
                v74,
                v194[0],
                v193,
                (__int64)v244,
                L"state",
                (DWORD)&pvarg);
        v77 = pvarg.lVal;
        if ( v76 < 0 )
          v77 = 0;
        *((_DWORD *)v61 + 44) = v77;
        if ( DCCDNUtil_GetRegistryDWORD(v184, 0, L"typeConfig", (unsigned int *)Data) < 0 )
          goto LABEL_487;
        *((_DWORD *)v61 + 41) = *(_DWORD *)Data;
        v78 = lambda_93083c850ad2f2ee8ffe7108d6f8beb5_::_lambda_93083c850ad2f2ee8ffe7108d6f8beb5_(
                (unsigned int)v237,
                (unsigned int)&v204,
                (unsigned int)&v214,
                (unsigned int)&v220,
                (__int64)&v221,
                (__int64)&v206,
                (__int64)&v187,
                (__int64)&v219,
                (__int64)&v222);
        wil::ScopeExit__lambda_93083c850ad2f2ee8ffe7108d6f8beb5___(v217, v78);
        if ( *((_BYTE *)v61 + 191) )
        {
          if ( (*((_BYTE *)a7 + 676) & 0x23) != 0 )
          {
            DCCDNUtil_GetRegistryString(v184, 0, L"instanceDataVariable", &v219);
            if ( v219 )
            {
              v79 = -1;
              do
                ++v79;
              while ( v219[v79] );
              std::wstring::_Assign<unsigned short>((char **)v61 + 25, v219, (char *)v79);
            }
          }
        }
        if ( DCCDNUtil_GetRegistryString(v184, 0, L"uri", &v220) < 0 )
          goto LABEL_486;
        v80 = -1;
        do
          ++v80;
        while ( v220[v80] );
        std::wstring::_Assign<unsigned short>((char **)v61, v220, (char *)v80);
        *((_BYTE *)v61 + 189) = 0;
        if ( DCCDNUtil_GetRegistryString(v184, 0, L"alias", &v221) < 0 )
          goto LABEL_486;
        v81 = -1;
        do
          ++v81;
        while ( v221[v81] );
        std::wstring::_Assign<unsigned short>((char **)v61 + 33, v221, (char *)v81);
        v82 = DCCDNUtil_GetRegistryString(v184, 0, L"reserved", &v222);
        v83 = 0;
        if ( v82 != -2147024894 )
          v83 = v82;
        if ( v83 < 0 )
        {
LABEL_486:
          wil::details::ScopeExitFn__lambda_93083c850ad2f2ee8ffe7108d6f8beb5___::_ScopeExitFn__lambda_93083c850ad2f2ee8ffe7108d6f8beb5___(v217);
LABEL_487:
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpName);
          std::wstring::_Tidy_deallocate(v234);
          std::wstring::_Tidy_deallocate(lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
          v12 = v201;
          goto LABEL_495;
        }
        if ( v222 )
        {
          v84 = -1;
          do
            ++v84;
          while ( v222[v84] );
          std::wstring::_Assign<unsigned short>((char **)v61 + 37, v222, (char *)v84);
        }
        if ( DCCDNUtil_GetRegistryString(v184, 0, L"conflictDocId", &v206) >= 0 )
        {
          v85 = v206;
          v86 = -1;
          do
            ++v86;
          while ( v206[v86] );
        }
        else
        {
          v85 = (unsigned __int16 *)&word_180142E98;
          v86 = 0;
        }
        std::wstring::_Assign<unsigned short>((char **)v61 + 12, v85, (char *)v86);
        if ( DCCDNUtil_GetRegistryString(v184, 0, L"conflictAuthorityId", &v187) >= 0 )
        {
          v87 = v187;
          v88 = -1;
          do
            ++v88;
          while ( v187[v88] );
        }
        else
        {
          v87 = (unsigned __int16 *)&word_180142E98;
          v88 = 0;
        }
        std::wstring::_Assign<unsigned short>((char **)v61 + 16, v87, (char *)v88);
        RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v184, 0, L"conflictErrorCode", (unsigned int *)&Block);
        if ( RegistryDWORD < 0 )
          RegistryDWORD = 0;
        else
          *((_DWORD *)v61 + 40) = (_DWORD)Block;
        if ( *((_DWORD *)a7 + 68) != 1 )
        {
          if ( *((_DWORD *)a7 + 68) == 2 )
            goto LABEL_231;
          if ( *((_DWORD *)a7 + 68) != 4 )
            goto LABEL_481;
          LOBYTE(v89) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_SupportNotConfigured>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_SupportNotConfigured>::GetImpl'::`2'::impl,
            v89);
          if ( *((_DWORD *)a7 + 69) == 2 )
          {
            VariantInit(&v232);
            v232.vt = 3;
            if ( (unsigned __int64)a7[15] <= 7 )
              LODWORD(v91) = (_DWORD)v36;
            else
              v91 = *v36;
            if ( (unsigned __int64)a7[3] <= 7 )
              LODWORD(v92) = (_DWORD)a7;
            else
              v92 = *a7;
            v93 = *(_QWORD *)v215;
            RegistryDWORD = DeclaredConfigurationStore_ReadResultData_1(
                              v215[0],
                              v92,
                              v91,
                              v194[0],
                              v193,
                              (__int64)v244,
                              L"valueConfigured",
                              (DWORD)&v232);
            if ( RegistryDWORD >= 0 )
              *((_BYTE *)v61 + 408) = v232.lVal == 0;
            else
              RegistryDWORD = 0;
            VariantClear(&v232);
          }
          else
          {
            v93 = *(_QWORD *)v215;
          }
          v94 = *((_DWORD *)v61 + 41);
          if ( v94 > 6 )
          {
            v107 = v94 - 7;
            if ( !v107 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
              {
                VariantInit(&v213);
                v213.vt = 8200;
                std::wstring::c_str(v36);
                v155 = std::wstring::c_str(a7);
                RegistryDWORD = DeclaredConfigurationStore_ReadResultData_1(
                                  v93,
                                  v155,
                                  v156,
                                  v194[0],
                                  v193,
                                  (__int64)v244,
                                  L"value",
                                  (DWORD)&v213);
                if ( RegistryDWORD >= 0 )
                {
                  v182 = 0;
                  *(_QWORD *)&v232.vt = 0;
                  v157 = SafeArrayToMultiString(
                           v213.parray,
                           0,
                           (unsigned __int16 **)&v182,
                           (unsigned __int64 *)&v232.vt);
                  v106 = v157;
                  if ( v157 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xA9F,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                      (const char *)(unsigned int)v157,
                      phkResultj);
                    VariantClear(&v213);
LABEL_432:
                    if ( v218 )
                    {
                      v218 = 0;
                      lambda_93083c850ad2f2ee8ffe7108d6f8beb5_::operator()(v217);
                    }
                    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpName);
                    std::wstring::_Tidy_deallocate(v234);
                    std::wstring::_Tidy_deallocate(lpSubKey);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
                    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
                    if ( v202[1] )
                      std::_Ref_count_base::_Decref(v202[1]);
                    if ( v196[1] )
                      std::_Ref_count_base::_Decref(v196[1]);
                    RegistryString = v106;
                    goto LABEL_439;
                  }
                  v160 = std::wstring::wstring(v236, v182, *(_QWORD *)&v232.vt);
                  std::wstring::operator=((char *)v61 + 32, v160);
                  std::wstring::_Tidy_deallocate(v236);
                  *((_BYTE *)v61 + 189) = 1;
                }
                else
                {
                  RegistryDWORD = 0;
                }
                VariantClear(&v213);
              }
              goto LABEL_442;
            }
            v108 = v107 - 1;
            if ( !v108 )
              goto LABEL_241;
            v109 = v108 - 3;
            if ( !v109 )
              goto LABEL_243;
            v110 = v109 - 1;
            if ( v110 )
            {
              if ( v110 != 1 )
                goto LABEL_442;
              goto LABEL_241;
            }
          }
          else
          {
            if ( v94 == 6 )
            {
              VariantInit(&v226);
              v226.vt = 8209;
              if ( (unsigned __int64)a7[15] <= 7 )
                LODWORD(v103) = (_DWORD)v36;
              else
                v103 = *v36;
              if ( (unsigned __int64)a7[3] <= 7 )
                LODWORD(v104) = (_DWORD)a7;
              else
                v104 = *a7;
              if ( (int)DeclaredConfigurationStore_ReadResultData_1(
                          v93,
                          v104,
                          v103,
                          v194[0],
                          v193,
                          (__int64)v244,
                          L"value",
                          (DWORD)&v226) >= 0 )
              {
                *(_QWORD *)&v232.vt = 0;
                LODWORD(Block) = 0;
                RegistryString = DCVariantToBinary(&v226, (unsigned int *)&Block, (unsigned __int8 **)&v232);
                if ( RegistryString < 0 )
                {
                  VariantClear(&v226);
                  wil::details::ScopeExitFn__lambda_93083c850ad2f2ee8ffe7108d6f8beb5___::_ScopeExitFn__lambda_93083c850ad2f2ee8ffe7108d6f8beb5___(v217);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpName);
                  std::wstring::_Tidy_deallocate(v234);
                  std::wstring::_Tidy_deallocate(lpSubKey);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
                  if ( v202[1] )
                    std::_Ref_count_base::_Decref(v202[1]);
                  if ( v196[1] )
                    std::_Ref_count_base::_Decref(v196[1]);
LABEL_439:
                  v158 = v205;
                  v159 = v201;
                  goto LABEL_509;
                }
                *((_DWORD *)v61 + 100) = (_DWORD)Block;
                *((_QWORD *)v61 + 49) = *(_QWORD *)&v232.vt;
                *((_BYTE *)v61 + 189) = 1;
              }
              v102 = &v226;
              goto LABEL_230;
            }
            if ( !v94 )
            {
              VariantInit(&v232);
              v232.vt = 3;
              if ( (unsigned __int64)a7[15] <= 7 )
                LODWORD(v100) = (_DWORD)v36;
              else
                v100 = *v36;
              if ( (unsigned __int64)a7[3] <= 7 )
                LODWORD(v101) = (_DWORD)a7;
              else
                v101 = *a7;
              if ( (int)DeclaredConfigurationStore_ReadResultData_1(
                          v93,
                          v101,
                          v100,
                          v194[0],
                          v193,
                          (__int64)v244,
                          L"value",
                          (DWORD)&v232) >= 0 )
              {
                *((_DWORD *)v61 + 98) = v232.lVal;
                *((_BYTE *)v61 + 189) = 1;
              }
LABEL_215:
              v102 = &v232;
              goto LABEL_230;
            }
            v95 = v94 - 1;
            if ( !v95 )
              goto LABEL_241;
            v96 = v95 - 1;
            if ( v96 )
            {
              v97 = v96 - 2;
              if ( v97 )
              {
                if ( v97 == 1 )
                {
                  VariantInit(&v232);
                  v232.vt = 3;
                  if ( (unsigned __int64)a7[15] <= 7 )
                    LODWORD(v98) = (_DWORD)v36;
                  else
                    v98 = *v36;
                  if ( (unsigned __int64)a7[3] <= 7 )
                    LODWORD(v99) = (_DWORD)a7;
                  else
                    v99 = *a7;
                  if ( (int)DeclaredConfigurationStore_ReadResultData_1(
                              v93,
                              v99,
                              v98,
                              v194[0],
                              v193,
                              (__int64)v244,
                              L"value",
                              (DWORD)&v232) >= 0 )
                  {
                    *((_DWORD *)v61 + 98) = v232.lVal;
                    *((_BYTE *)v61 + 189) = 1;
                  }
                  goto LABEL_215;
                }
LABEL_442:
                if ( RegistryDWORD < 0 )
                {
LABEL_481:
                  if ( v218 )
                  {
                    v218 = 0;
                    lambda_93083c850ad2f2ee8ffe7108d6f8beb5_::operator()(v217);
                  }
                  goto LABEL_487;
                }
LABEL_231:
                LOBYTE(v89) = 1;
                wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
                  `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
                  v89);
                if ( *((_DWORD *)a7 + 68) == 1 )
                {
                  *(_QWORD *)&v232.vt = 0;
                  *(_OWORD *)&v233.vt = (unsigned __int64)v61 + 328;
                  *((_BYTE *)&v233.decVal + 16) = 1;
                  RegistryBinary = DCCDNUtil_GetRegistryBinary(
                                     v184,
                                     0,
                                     L"hashValue",
                                     &v233.pbVal,
                                     (unsigned int *)&v182);
                  wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&v233);
                  v106 = 0;
                  if ( RegistryBinary != -2147024894 )
                    v106 = RegistryBinary;
                  if ( v106 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xB25,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                      (const char *)(unsigned int)v106,
                      phkResulti);
                    std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v232);
                    goto LABEL_432;
                  }
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v232);
                }
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl)
                  && *((_DWORD *)a7 + 69) == 2
                  && *((_DWORD *)a7 + 68) == 1 )
                {
                  LODWORD(v182) = 0;
                  DCCDNUtil_GetRegistryDWORD(v184, 0, L"behavior", (unsigned int *)&v182);
                  *((_DWORD *)v61 + 84) = (_DWORD)v182;
                }
                try
                {
                  v169 = (_QWORD *)*((_QWORD *)v196[0] + 3);
                  if ( v169 == *((_QWORD **)v196[0] + 4) )
                  {
                    std::vector<std::shared_ptr<DCURI>>::_Emplace_reallocate<std::shared_ptr<DCURI> const &>(
                      (__int64 *)v196[0] + 2,
                      *((void **)v196[0] + 3),
                      (__int64)v202);
                  }
                  else
                  {
                    std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v169, v202);
                    *(_QWORD *)(v170 + 24) += 16LL;
                  }
                  *(_OWORD *)&v232.vt = 0;
                  std::shared_ptr<DCURI>::operator=(v202, &v232);
                  if ( v232.llVal )
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v232.llVal);
                }
                catch ( std::bad_alloc )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xB3D,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                    (const char *)0x8007000ELL,
                    phkResulta);
                  if ( v218 )
                  {
                    v218 = 0;
                    lambda_93083c850ad2f2ee8ffe7108d6f8beb5_::operator()(v217);
                  }
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpName);
                  std::wstring::_Tidy_deallocate(v234);
                  std::wstring::_Tidy_deallocate(lpSubKey);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
LABEL_504:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
                  if ( v202[1] )
                    std::_Ref_count_base::_Decref(v202[1]);
                  if ( v196[1] )
                    std::_Ref_count_base::_Decref(v196[1]);
                  v159 = v230;
                  v158 = v231;
                  RegistryString = -2147024882;
LABEL_509:
                  VariantClear(&pvarg);
                  std::wstring::_Tidy_deallocate(v158);
                  v18 = v159;
LABEL_15:
                  std::wstring::_Tidy_deallocate(v18);
                  return (unsigned int)RegistryString;
                }
                goto LABEL_481;
              }
LABEL_241:
              VariantInit(&v233);
              v233.vt = 8;
              if ( (unsigned __int64)a7[15] <= 7 )
                LODWORD(v111) = (_DWORD)v36;
              else
                v111 = *v36;
              if ( (unsigned __int64)a7[3] <= 7 )
                LODWORD(v153) = (_DWORD)a7;
              else
                v153 = *a7;
              if ( (int)DeclaredConfigurationStore_ReadResultData_1(
                          v93,
                          v153,
                          v111,
                          v194[0],
                          v193,
                          (__int64)v244,
                          L"value",
                          (DWORD)&v233) >= 0 )
              {
                v154 = -1;
                do
                  ++v154;
                while ( *(_WORD *)(v233.llVal + 2 * v154) );
                std::wstring::_Assign<unsigned short>((char **)v61 + 4, v233.bstrVal, (char *)v154);
                *((_BYTE *)v61 + 189) = 1;
              }
              v102 = &v233;
LABEL_230:
              VariantClear(v102);
              goto LABEL_231;
            }
LABEL_243:
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            {
              VariantInit(&v211);
              v211.vt = 20;
              if ( (unsigned __int64)a7[15] <= 7 )
                v112 = v36;
              else
                v112 = (_QWORD *)*v36;
              if ( (unsigned __int64)a7[3] <= 7 )
                v113 = a7;
              else
                v113 = (__int64 *)*a7;
              *(_QWORD *)&v232.vt = 0;
              if ( !v93 || !v113 || !v112 )
              {
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v232);
                goto LABEL_330;
              }
              v233.llVal = 0;
              *((_BYTE *)&v233.decVal + 16) = 1;
              *(_QWORD *)&v233.vt = &v232;
              if ( *(_QWORD *)v194 )
                GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey_0(
                  v93,
                  (_DWORD)v113,
                  (_DWORD)v112,
                  v194[0],
                  (__int64)&v233.llVal);
              else
                GetResultsEnrollmentIdSidStateDocIdVersionKey_1(v93, v113, v112, &v233.decVal.Lo32);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v233);
              v114 = 0;
              v198 = 0;
              if ( v193 )
              {
                *(_QWORD *)&v233.vt = &v198;
                v233.llVal = 0;
                *((_BYTE *)&v233.decVal + 16) = 1;
                v115 = DCStringCchPrintfAllStrings(&v233.decVal.Lo32, L"%s\\%s", 2, v193, v244);
                wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v233);
                if ( v115 >= 0 )
                {
                  v114 = v198;
                  goto LABEL_259;
                }
LABEL_269:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v198);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v232);
LABEL_270:
                v36 = a7 + 12;
LABEL_330:
                v102 = &v211;
                goto LABEL_230;
              }
LABEL_259:
              if ( v211.vt != 3 )
              {
                if ( v211.vt == 5 )
                  goto LABEL_302;
                if ( v211.vt != 8 )
                {
                  if ( v211.vt != 20 )
                  {
                    if ( v211.vt != 8200 )
                    {
                      if ( v211.vt != 8209 )
                        goto LABEL_269;
                      v182 = 0;
                      LODWORD(Block) = 0;
                      if ( (int)DCGetRegistryBinary(*(_QWORD *)&v232.vt, v114, L"value", &v182, &Block) < 0
                        || (int)DCInlineSetBinaryToVariant(v182, (unsigned int)Block) < 0 )
                      {
                        std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v182);
                        goto LABEL_269;
                      }
                      std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v182);
                      goto LABEL_327;
                    }
LABEL_305:
                    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                      goto LABEL_269;
                    Block = 0;
                    if ( DCCDNUtil_GetRegistryMultiString(
                           *(HKEY *)&v232.vt,
                           v198,
                           L"value",
                           (unsigned __int16 **)&Block,
                           (unsigned int *)&v182) < 0 )
                      goto LABEL_269;
                    v211.vt = 8200;
                    MultiStringToSafeArray((OLECHAR *)Block, v126, &v211.parray);
                    operator delete(Block);
                    goto LABEL_327;
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                  {
                    v182 = 0;
                    if ( (int)DCGetRegistryQWORD(*(_QWORD *)&v232.vt, v198, L"value", &v182) < 0 )
                      goto LABEL_269;
                    v211.vt = 20;
                    goto LABEL_274;
                  }
LABEL_302:
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                    goto LABEL_305;
                  v182 = 0;
                  if ( (int)DCGetRegistryQWORD(*(_QWORD *)&v232.vt, v198, L"value", &v182) < 0 )
                    goto LABEL_269;
                  v211.vt = 5;
LABEL_274:
                  v211.llVal = (LONGLONG)v182;
LABEL_327:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v198);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v232);
                  *((_QWORD *)v61 + 49) = v211.llVal;
                  *((_BYTE *)v61 + 189) = 1;
                  goto LABEL_270;
                }
                v116 = 0;
                v117 = *(HKEY *)&v232.vt;
                Type[0] = 1;
                v182 = 0;
                cbData = 0;
                if ( *(_QWORD *)&v232.vt )
                {
                  if ( v114 )
                  {
                    v118 = RegOpenKeyExW(*(HKEY *)&v232.vt, v114, 0, 0x20119u, &v182);
                    v119 = v118;
                    if ( v118 )
                    {
                      if ( v118 > 0 )
                        v119 = (unsigned __int16)v118 | 0x80070000;
LABEL_298:
                      if ( v182 )
                        RegCloseKey(v182);
LABEL_300:
                      if ( v119 < 0 )
                      {
                        v9 = v205;
                        goto LABEL_269;
                      }
                      v211.vt = 8;
                      v211.llVal = (LONGLONG)SysAllocString(v116);
                      operator delete(v116);
                      v9 = v205;
                      goto LABEL_327;
                    }
                    v117 = v182;
                  }
                  else
                  {
                    v182 = *(HKEY *)&v232.vt;
                  }
                  v120 = RegQueryValueExW(v117, L"value", 0, Type, 0, &cbData);
                  v119 = v120;
                  if ( v120 )
                  {
                    if ( v120 > 0 )
                      v119 = (unsigned __int16)v120 | 0x80070000;
                  }
                  else if ( Type[0] == 1 )
                  {
                    v121 = ((unsigned __int64)cbData >> 1) + 1;
                    v122 = 2 * v121;
                    if ( !is_mul_ok(v121, 2u) )
                      v122 = -1;
                    v123 = (BYTE *)operator new[](v122, (const struct std::nothrow_t *)std::nothrow);
                    v124 = v123;
                    if ( v123 )
                    {
                      memset_0(v123, 0, v121);
                      v125 = RegQueryValueExW(v182, L"value", 0, Type, v124, &cbData);
                      v119 = v125;
                      if ( v125 )
                      {
                        if ( v125 > 0 )
                          v119 = (unsigned __int16)v125 | 0x80070000;
                        operator delete(v124);
                      }
                      else
                      {
                        v119 = 0;
                        v116 = (OLECHAR *)v124;
                      }
                    }
                    else
                    {
                      v119 = -2147024882;
                    }
                  }
                  else
                  {
                    v119 = -2147418113;
                  }
                }
                else
                {
                  v119 = -2147024809;
                }
                if ( v114 )
                  goto LABEL_298;
                goto LABEL_300;
              }
              v127 = 0;
              v128 = *(HKEY *)&v232.vt;
              *(_DWORD *)Data = 0;
              LODWORD(Block) = 4;
              *(_QWORD *)Type = 0;
              LODWORD(v182) = 4;
              if ( *(_QWORD *)&v232.vt )
              {
                if ( v114 )
                {
                  v129 = RegOpenKeyExW(*(HKEY *)&v232.vt, v114, 0, 0x20119u, (PHKEY)Type);
                  v130 = v129;
                  if ( v129 )
                  {
                    if ( v129 > 0 )
                      v130 = (unsigned __int16)v129 | 0x80070000;
LABEL_323:
                    if ( *(_QWORD *)Type )
                      RegCloseKey(*(HKEY *)Type);
LABEL_325:
                    if ( v130 < 0 )
                      goto LABEL_269;
                    v211.vt = 3;
                    v211.lVal = v127;
                    goto LABEL_327;
                  }
                  v128 = *(HKEY *)Type;
                }
                else
                {
                  *(_QWORD *)Type = *(_QWORD *)&v232.vt;
                }
                Value = RegQueryValueExW(v128, L"value", 0, (LPDWORD)&Block, Data, (LPDWORD)&v182);
                v130 = Value;
                if ( Value )
                {
                  if ( Value > 0 )
                    v130 = (unsigned __int16)Value | 0x80070000;
                }
                else if ( (_DWORD)Block == 4 )
                {
                  v130 = 0;
                  v127 = *(_DWORD *)Data;
                }
                else
                {
                  v130 = -2147418113;
                }
              }
              else
              {
                v130 = -2147024809;
              }
              if ( v114 )
                goto LABEL_323;
              goto LABEL_325;
            }
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            goto LABEL_442;
          VariantInit(&v212);
          v212.vt = 8;
          if ( (unsigned __int64)a7[15] <= 7 )
            v132 = v36;
          else
            v132 = (_QWORD *)*v36;
          if ( (unsigned __int64)a7[3] <= 7 )
            v133 = a7;
          else
            v133 = (__int64 *)*a7;
          *(_QWORD *)&v232.vt = 0;
          if ( !v93 || !v133 || !v132 )
            goto LABEL_358;
          v233.llVal = 0;
          *((_BYTE *)&v233.decVal + 16) = 1;
          *(_QWORD *)&v233.vt = &v232;
          if ( *(_QWORD *)v194 )
            GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey_0(
              v93,
              (_DWORD)v133,
              (_DWORD)v132,
              v194[0],
              (__int64)&v233.llVal);
          else
            GetResultsEnrollmentIdSidStateDocIdVersionKey_1(v93, v133, v132, &v233.decVal.Lo32);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v233);
          v134 = 0;
          v199 = 0;
          if ( v193 )
          {
            *(_QWORD *)&v233.vt = &v199;
            v233.llVal = 0;
            *((_BYTE *)&v233.decVal + 16) = 1;
            v135 = DCStringCchPrintfAllStrings(&v233.decVal.Lo32, L"%s\\%s", 2, v193, v244);
            wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v233);
            if ( v135 >= 0 )
            {
              v134 = v199;
              goto LABEL_347;
            }
LABEL_357:
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v199);
LABEL_358:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v232);
            RegistryDWORD = 0;
LABEL_359:
            VariantClear(&v212);
            v36 = a7 + 12;
            goto LABEL_442;
          }
LABEL_347:
          if ( v212.vt != 3 )
          {
            if ( v212.vt == 5 )
              goto LABEL_391;
            if ( v212.vt != 8 )
            {
              if ( v212.vt != 20 )
              {
                if ( v212.vt != 8200 )
                {
                  if ( v212.vt != 8209 )
                    goto LABEL_357;
                  v182 = 0;
                  LODWORD(Block) = 0;
                  if ( (int)DCGetRegistryBinary(*(_QWORD *)&v232.vt, v134, L"value", &v182, &Block) < 0
                    || (int)DCInlineSetBinaryToVariant(v182, (unsigned int)Block) < 0 )
                  {
                    std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v182);
                    goto LABEL_357;
                  }
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v182);
                  goto LABEL_416;
                }
LABEL_394:
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                  goto LABEL_357;
                Block = 0;
                if ( DCCDNUtil_GetRegistryMultiString(
                       *(HKEY *)&v232.vt,
                       v199,
                       L"value",
                       (unsigned __int16 **)&Block,
                       (unsigned int *)&v182) < 0 )
                  goto LABEL_357;
                v212.vt = 8200;
                MultiStringToSafeArray((OLECHAR *)Block, v147, &v212.parray);
                operator delete(Block);
                goto LABEL_416;
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
              {
                v182 = 0;
                if ( (int)DCGetRegistryQWORD(*(_QWORD *)&v232.vt, v199, L"value", &v182) < 0 )
                  goto LABEL_357;
                v136 = 20;
                goto LABEL_363;
              }
LABEL_391:
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                goto LABEL_394;
              v182 = 0;
              if ( (int)DCGetRegistryQWORD(*(_QWORD *)&v232.vt, v199, L"value", &v182) < 0 )
                goto LABEL_357;
              v136 = 5;
LABEL_363:
              v212.vt = v136;
              v212.llVal = (LONGLONG)v182;
LABEL_416:
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v199);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v232);
              RegistryDWORD = 0;
              std::wstring::operator=((char *)v61 + 32, v212.llVal);
              *((_BYTE *)v61 + 189) = 1;
              goto LABEL_359;
            }
            v137 = 0;
            v138 = *(HKEY *)&v232.vt;
            cbData = 1;
            v182 = 0;
            Type[0] = 0;
            if ( *(_QWORD *)&v232.vt )
            {
              if ( v134 )
              {
                v139 = RegOpenKeyExW(*(HKEY *)&v232.vt, v134, 0, 0x20119u, &v182);
                v140 = v139;
                if ( v139 )
                {
                  if ( v139 > 0 )
                    v140 = (unsigned __int16)v139 | 0x80070000;
LABEL_387:
                  if ( v182 )
                    RegCloseKey(v182);
LABEL_389:
                  if ( v140 < 0 )
                  {
                    v9 = v205;
                    goto LABEL_357;
                  }
                  v212.vt = 8;
                  v212.llVal = (LONGLONG)SysAllocString(v137);
                  operator delete(v137);
                  v9 = v205;
                  goto LABEL_416;
                }
                v138 = v182;
              }
              else
              {
                v182 = *(HKEY *)&v232.vt;
              }
              v141 = RegQueryValueExW(v138, L"value", 0, &cbData, 0, Type);
              v140 = v141;
              if ( v141 )
              {
                if ( v141 > 0 )
                  v140 = (unsigned __int16)v141 | 0x80070000;
              }
              else if ( cbData == 1 )
              {
                v142 = ((unsigned __int64)Type[0] >> 1) + 1;
                v143 = 2 * v142;
                if ( !is_mul_ok(v142, 2u) )
                  v143 = -1;
                v144 = (BYTE *)operator new[](v143, (const struct std::nothrow_t *)std::nothrow);
                v145 = v144;
                if ( v144 )
                {
                  memset_0(v144, 0, v142);
                  v146 = RegQueryValueExW(v182, L"value", 0, &cbData, v145, Type);
                  v140 = v146;
                  if ( v146 )
                  {
                    if ( v146 > 0 )
                      v140 = (unsigned __int16)v146 | 0x80070000;
                    operator delete(v145);
                  }
                  else
                  {
                    v140 = 0;
                    v137 = (OLECHAR *)v145;
                  }
                }
                else
                {
                  v140 = -2147024882;
                }
              }
              else
              {
                v140 = -2147418113;
              }
            }
            else
            {
              v140 = -2147024809;
            }
            if ( v134 )
              goto LABEL_387;
            goto LABEL_389;
          }
          v148 = 0;
          v149 = *(HKEY *)&v232.vt;
          *(_DWORD *)Data = 0;
          LODWORD(Block) = 4;
          *(_QWORD *)Type = 0;
          LODWORD(v182) = 4;
          if ( *(_QWORD *)&v232.vt )
          {
            if ( v134 )
            {
              v150 = RegOpenKeyExW(*(HKEY *)&v232.vt, v134, 0, 0x20119u, (PHKEY)Type);
              v151 = v150;
              if ( v150 )
              {
                if ( v150 > 0 )
                  v151 = (unsigned __int16)v150 | 0x80070000;
LABEL_412:
                if ( *(_QWORD *)Type )
                  RegCloseKey(*(HKEY *)Type);
LABEL_414:
                if ( v151 < 0 )
                  goto LABEL_357;
                v212.vt = 3;
                v212.lVal = v148;
                goto LABEL_416;
              }
              v149 = *(HKEY *)Type;
            }
            else
            {
              *(_QWORD *)Type = *(_QWORD *)&v232.vt;
            }
            v152 = RegQueryValueExW(v149, L"value", 0, (LPDWORD)&Block, Data, (LPDWORD)&v182);
            v151 = v152;
            if ( v152 )
            {
              if ( v152 > 0 )
                v151 = (unsigned __int16)v152 | 0x80070000;
            }
            else if ( (_DWORD)Block == 4 )
            {
              v151 = 0;
              v148 = *(_DWORD *)Data;
            }
            else
            {
              v151 = -2147418113;
            }
          }
          else
          {
            v151 = -2147024809;
          }
          if ( v134 )
            goto LABEL_412;
          goto LABEL_414;
        }
        v161 = v62 - 1;
        if ( v161 )
        {
          v162 = v161 - 2;
          if ( !v162 )
          {
            RegistryDWORD = DCGetRegistryBinary(v184, 0, L"value", &v214, &cbData);
            if ( RegistryDWORD < 0 )
              goto LABEL_481;
            *((_DWORD *)v61 + 100) = cbData;
            *((_QWORD *)v61 + 49) = v214;
            v214 = 0;
            goto LABEL_465;
          }
          v163 = v162 - 1;
          if ( !v163 )
          {
            RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v184, 0, L"value", (unsigned int *)&v182);
            if ( RegistryDWORD < 0 )
              goto LABEL_481;
            *((_DWORD *)v61 + 98) = (_DWORD)v182;
            goto LABEL_465;
          }
          v164 = v163 - 1;
          if ( !v164 )
            goto LABEL_465;
          v165 = v164 - 1;
          if ( !v165 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
              goto LABEL_455;
            RegistryDWORD = DCCDNUtil_GetRegistryQWORD(v184, 0, L"value", (unsigned __int64 *)v61 + 49);
            if ( RegistryDWORD < 0 )
              goto LABEL_481;
LABEL_465:
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl)
              && *((_DWORD *)a7 + 69) == 2
              && *((_DWORD *)a7 + 68) == 1 )
            {
              LODWORD(v182) = 1;
              v168 = DCCDNUtil_GetRegistryDWORD(v184, 0, L"setValueChanged", (unsigned int *)&v182);
              RegistryDWORD = 0;
              if ( v168 >= 0 )
                RegistryDWORD = v168;
              *((_BYTE *)v61 + 409) = (_DWORD)v182 != 0;
            }
            goto LABEL_442;
          }
          v166 = v165 - 1;
          if ( !v166 )
            goto LABEL_551;
          if ( v166 != 1 )
            goto LABEL_451;
LABEL_455:
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          {
LABEL_551:
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            {
              RegistryDWORD = DCCDNUtil_GetRegistryMultiString(v184, 0, L"value", &v204, &cbData);
              if ( RegistryDWORD < 0 )
                goto LABEL_481;
              v167 = std::wstring::wstring(v236, v204, (unsigned __int64)cbData >> 1);
              std::wstring::operator=((char *)v61 + 32, v167);
              std::wstring::_Tidy_deallocate(v236);
            }
            else
            {
LABEL_451:
              RegistryDWORD = -2147418113;
            }
            goto LABEL_465;
          }
        }
        RegistryDWORD = DCCDNUtil_GetRegistryString(v184, 0, L"value", &v204);
        if ( RegistryDWORD < 0 )
          goto LABEL_481;
        std::wstring::operator=((char *)v61 + 32, v204);
        goto LABEL_465;
      }
    }
    std::wstring::_Tidy_deallocate(v234);
    std::wstring::_Tidy_deallocate(lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v184);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v195);
LABEL_495:
    v47 = v209 + 1;
    v46 = v210 + 1;
  }
  std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v224, v196);
  try
  {
    std::vector<std::shared_ptr<DCProviderOrchestration>>::push_back(a7 + 20, &v224);
    if ( v225 )
      std::_Ref_count_base::_Decref(v225);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v190);
    if ( v202[1] )
      std::_Ref_count_base::_Decref(v202[1]);
    if ( v196[1] )
      std::_Ref_count_base::_Decref(v196[1]);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v9);
    std::wstring::_Tidy_deallocate(v12);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB56,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    goto LABEL_504;
  }
  return result;
}

```

## disassembly

```asm
0x1800c0f2c  mov     r11, rsp
0x1800c0f2f  push    rbx
0x1800c0f30  push    rsi
0x1800c0f31  push    rdi
0x1800c0f32  push    r12
0x1800c0f34  push    r13
0x1800c0f36  push    r14
0x1800c0f38  push    r15
0x1800c0f3a  sub     rsp, 460h
0x1800c0f41  mov     rax, cs:__security_cookie
0x1800c0f48  xor     rax, rsp
0x1800c0f4b  mov     [rsp+498h+var_48], rax
0x1800c0f53  mov     r15, r9
0x1800c0f56  mov     [r11-360h], r9
0x1800c0f5d  mov     rbx, r8
0x1800c0f60  mov     [rsp+498h+var_260], rbx
0x1800c0f68  mov     r14, rdx
0x1800c0f6b  mov     [rsp+498h+hKey], rdx
0x1800c0f73  mov     qword ptr [rsp+498h+var_2F0], rcx
0x1800c0f7b  mov     r12, [rsp+498h+arg_30]
0x1800c0f83  mov     [r11-210h], r9
0x1800c0f8a  mov     r13, [rsp+498h+arg_20]
0x1800c0f92  mov     [r11-388h], r13
0x1800c0f99  mov     [r11-218h], r13
0x1800c0fa0  mov     rax, [rsp+498h+arg_28]
0x1800c0fa8  mov     [rsp+498h+var_3E0], rax
0x1800c0fb0  mov     rax, [rsp+498h+arg_40]
0x1800c0fb8  mov     qword ptr [rsp+498h+var_3D8], rax
0x1800c0fc0  lea     rcx, [r11-3B8h]; pvarg
0x1800c0fc7  call    cs:__imp_VariantInit
0x1800c0fcd  nop
0x1800c0fce  xorps   xmm0, xmm0
0x1800c0fd1  movdqu  xmmword ptr [rsp+498h+var_3C8], xmm0
0x1800c0fda  movdqu  xmmword ptr [rsp+498h+var_380], xmm0
0x1800c0fe3  xor     edi, edi
0x1800c0fe5  mov     [rsp+498h+var_68], di
0x1800c0fed  lea     rcx, [rsp+498h+var_410]
0x1800c0ff5  call    ??$make_shared@VDCCSP@@$$V@std@@YA?AV?$shared_ptr@VDCCSP@@@0@XZ; std::make_shared<DCCSP,>(void)
0x1800c0ffa  mov     rdx, rax
0x1800c0ffd  lea     rcx, [rsp+498h+var_3C8]
0x1800c1005  call    ??4?$shared_ptr@VDCURI@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DCURI>::operator=(std::shared_ptr<DCURI> &&)
0x1800c100a  mov     rcx, [rsp+498h+var_408]; this
0x1800c1012  test    rcx, rcx
0x1800c1015  jz      short loc_1800C101C
0x1800c1017  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c101c  mov     rsi, [rsp+498h+var_3C8]
0x1800c1024  test    rsi, rsi
0x1800c1027  jnz     short loc_1800C1086
0x1800c1029  mov     rcx, [rsp+498h]; this
0x1800c1031  mov     r9d, 8007000Eh; char *
0x1800c1037  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c103e  mov     edx, 74Ch; void *
0x1800c1043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1048  nop
0x1800c1049  mov     rcx, [rsp+498h+var_3C8+8]; this
0x1800c1051  test    rcx, rcx
0x1800c1054  jz      short loc_1800C105C
0x1800c1056  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c105b  nop
0x1800c105c  lea     rcx, [rsp+498h+pvarg]; pvarg
0x1800c1064  call    cs:__imp_VariantClear
0x1800c106a  nop
0x1800c106b  mov     rcx, r15
0x1800c106e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c1073  nop
0x1800c1074  mov     rcx, r13
0x1800c1077  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c107c  mov     eax, 8007000Eh
0x1800c1081  jmp     loc_1800C3DC3
0x1800c1086  mov     dword ptr [rsi+80h], 1
0x1800c1090  mov     [rsp+498h+var_410], rdi
0x1800c1098  cmp     qword ptr [r13+18h], 7
0x1800c109d  jbe     short loc_1800C10A5
0x1800c109f  mov     rdx, [r13+0]
0x1800c10a3  jmp     short loc_1800C10A8
0x1800c10a5  mov     rdx, r13; unsigned __int16 *
0x1800c10a8  lea     r9, [rsp+498h+var_410]; unsigned __int16 **
0x1800c10b0  lea     r8, aCsp_0; "csp"
0x1800c10b7  mov     rcx, rbx; HKEY
0x1800c10ba  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800c10bf  mov     ebx, eax
0x1800c10c1  test    eax, eax
0x1800c10c3  jns     short loc_1800C10FF
0x1800c10c5  mov     rcx, [rsp+498h+var_3C8+8]; this
0x1800c10cd  test    rcx, rcx
0x1800c10d0  jz      short loc_1800C10D8
0x1800c10d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c10d7  nop
0x1800c10d8  lea     rcx, [rsp+498h+pvarg]; pvarg
0x1800c10e0  call    cs:__imp_VariantClear
0x1800c10e6  nop
0x1800c10e7  mov     rcx, r15
0x1800c10ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c10ef  nop
0x1800c10f0  mov     rcx, r13
0x1800c10f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c10f8  mov     eax, ebx
0x1800c10fa  jmp     loc_1800C3DC3
0x1800c10ff  mov     rdx, [rsp+498h+var_410]
0x1800c1107  mov     [rsp+498h+var_3F8], rdx
0x1800c110f  lea     rcx, [rsi+58h]
0x1800c1113  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c1117  inc     r8
0x1800c111a  cmp     [rdx+r8*2], di
0x1800c111f  jnz     short loc_1800C1117
0x1800c1121  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c1126  mov     [rsp+498h+var_34C], edi
0x1800c112d  cmp     qword ptr [r15+18h], 7
0x1800c1132  jbe     short loc_1800C1139
0x1800c1134  mov     rdx, [r15]
0x1800c1137  jmp     short loc_1800C113C
0x1800c1139  mov     rdx, r15; unsigned __int16 *
0x1800c113c  lea     r9, [rsp+498h+var_34C]; unsigned int *
0x1800c1144  lea     r8, aUricount; "UriCount"
0x1800c114b  mov     rcx, r14; HKEY
0x1800c114e  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800c1153  mov     ebx, eax
0x1800c1155  test    eax, eax
0x1800c1157  jns     short loc_1800C116B
0x1800c1159  lea     rcx, [rsp+498h+var_3F8]
0x1800c1161  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800c1166  jmp     loc_1800C10C5
0x1800c116b  cmp     [rsp+498h+arg_38], 2
0x1800c1173  jnz     loc_1800C17BC
0x1800c1179  mov     [rsp+498h+Type], edi
0x1800c117d  cmp     qword ptr [r15+18h], 7
0x1800c1182  jbe     short loc_1800C1189
0x1800c1184  mov     rdx, [r15]
0x1800c1187  jmp     short loc_1800C118C
0x1800c1189  mov     rdx, r15; unsigned __int16 *
0x1800c118c  lea     r9, [rsp+498h+Type]; unsigned int *
0x1800c1191  lea     r8, aAtomicflagnece; "atomicFlagNecessary"
0x1800c1198  mov     rcx, r14; HKEY
0x1800c119b  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800c11a0  cmp     [rsp+498h+Type], edi
0x1800c11a4  setnz   al
0x1800c11a7  mov     [rsi+50h], al
0x1800c11aa  mov     [rsp+498h+Type], edi
0x1800c11ae  cmp     qword ptr [r15+18h], 7
0x1800c11b3  jbe     short loc_1800C11BA
0x1800c11b5  mov     rdx, [r15]
0x1800c11b8  jmp     short loc_1800C11BD
0x1800c11ba  mov     rdx, r15; unsigned __int16 *
0x1800c11bd  lea     r9, [rsp+498h+Type]; unsigned int *
0x1800c11c2  lea     r8, aOnetimeexecuti; "oneTimeExecutionNodeNecessary"
0x1800c11c9  mov     rcx, r14; HKEY
0x1800c11cc  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800c11d1  cmp     [rsp+498h+Type], edi
0x1800c11d5  setnz   al
0x1800c11d8  mov     [rsi+51h], al
0x1800c11db  mov     [rsp+498h+var_370], rdi
0x1800c11e3  mov     [rsp+498h+var_3F0], rdi
0x1800c11eb  lea     rax, [rsp+498h+var_370]
0x1800c11f3  mov     qword ptr [rsp+498h+var_310], rax
0x1800c11fb  mov     qword ptr [rsp+498h+var_310+8], rdi
0x1800c1203  mov     byte ptr [rsp+498h+var_310+10h], 1
0x1800c120b  cmp     qword ptr [r15+18h], 7
0x1800c1210  jbe     short loc_1800C1217
0x1800c1212  mov     rdx, [r15]
0x1800c1215  jmp     short loc_1800C121A
0x1800c1217  mov     rdx, r15; lpSubKey
0x1800c121a  lea     rax, [rsp+498h+var_310+8]
0x1800c1222  mov     [rsp+498h+phkResult], rax; phkResult
0x1800c1227  mov     r14d, 20119h
0x1800c122d  mov     r9d, r14d; samDesired
0x1800c1230  xor     r8d, r8d; ulOptions
0x1800c1233  mov     rcx, [rsp+498h+hKey]; hKey
0x1800c123b  call    cs:__imp_RegOpenKeyExW
0x1800c1241  mov     ebx, eax
0x1800c1243  lea     rcx, [rsp+498h+var_310]
0x1800c124b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800c1250  test    ebx, ebx
0x1800c1252  jnz     loc_1800C17A1
0x1800c1258  lea     rax, [rsp+498h+var_3F0]
0x1800c1260  mov     qword ptr [rsp+498h+var_310], rax
0x1800c1268  mov     qword ptr [rsp+498h+var_310+8], rdi
0x1800c1270  mov     byte ptr [rsp+498h+var_310+10h], 1
0x1800c1278  lea     rax, [rsp+498h+var_310+8]
0x1800c1280  mov     [rsp+498h+phkResult], rax; phkResult
0x1800c1285  mov     r9d, r14d; samDesired
0x1800c1288  xor     r8d, r8d; ulOptions
0x1800c128b  lea     rdx, aResourcetracki; "resourceTracking"
0x1800c1292  mov     rcx, [rsp+498h+var_370]; hKey
0x1800c129a  call    cs:__imp_RegOpenKeyExW
0x1800c12a0  mov     ebx, eax
0x1800c12a2  lea     rcx, [rsp+498h+var_310]
0x1800c12aa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800c12af  test    ebx, ebx
0x1800c12b1  jnz     loc_1800C17A1
0x1800c12b7  mov     [rsp+498h+cSubKeys], edi
0x1800c12be  mov     [rsp+498h+cbMaxSubKeyLen], edi
0x1800c12c5  mov     [rsp+498h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800c12ca  mov     [rsp+498h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800c12cf  mov     [rsp+498h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800c12d4  mov     [rsp+498h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800c12d9  mov     [rsp+498h+lpcValues], rdi; lpcValues
0x1800c12de  mov     [rsp+498h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800c12e3  lea     rax, [rsp+498h+cbMaxSubKeyLen]
0x1800c12eb  mov     [rsp+498h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800c12f0  lea     rax, [rsp+498h+cSubKeys]
0x1800c12f8  mov     [rsp+498h+phkResult], rax; int
0x1800c12fd  xor     r9d, r9d; lpReserved
0x1800c1300  xor     r8d, r8d; lpcchClass
0x1800c1303  xor     edx, edx; lpClass
0x1800c1305  mov     rcx, [rsp+498h+var_3F0]; hKey
0x1800c130d  call    cs:__imp_RegQueryInfoKeyW
0x1800c1313  test    eax, eax
0x1800c1315  jnz     loc_1800C17A1
0x1800c131b  mov     r14d, edi
0x1800c131e  cmp     r14d, [rsp+498h+cSubKeys]
0x1800c1326  jnb     loc_1800C17A1
0x1800c132c  mov     r8d, [rsp+498h+cbMaxSubKeyLen]
0x1800c1334  inc     r8d; unsigned __int64
0x1800c1337  xor     edx, edx; unsigned __int16 *
0x1800c1339  lea     rcx, [rsp+498h+lpName]; this
0x1800c1341  call    ?make_hlocal_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_hlocal_string_nothrow(ushort const *,unsigned __int64)
0x1800c1346  nop
0x1800c1347  mov     rbx, [rsp+498h+lpName]
0x1800c134f  test    rbx, rbx
0x1800c1352  jz      loc_1800C172E
0x1800c1358  mov     r9d, [rsp+498h+cbMaxSubKeyLen]
0x1800c1360  inc     r9d; cchName
0x1800c1363  mov     r8, rbx; lpName
0x1800c1366  mov     edx, r14d; dwIndex
0x1800c1369  mov     rcx, [rsp+498h+var_3F0]; hKey
0x1800c1371  call    cs:__imp_RegEnumKeyW
0x1800c1377  mov     esi, eax
0x1800c1379  test    eax, eax
0x1800c137b  jle     short loc_1800C1386
0x1800c137d  movzx   esi, ax
0x1800c1380  or      esi, 80070000h
0x1800c1386  test    esi, esi
0x1800c1388  jns     short loc_1800C13F8
0x1800c138a  mov     rcx, [rsp+498h]; this
0x1800c1392  mov     r9d, esi; char *
0x1800c1395  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c139c  mov     edx, 79Dh; void *
0x1800c13a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c13a6  nop
0x1800c13a7  lea     rcx, [rsp+498h+lpName]
0x1800c13af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c13b4  nop
0x1800c13b5  lea     rcx, [rsp+498h+var_3F0]
0x1800c13bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c13c2  nop
0x1800c13c3  lea     rcx, [rsp+498h+var_370]
0x1800c13cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c13d0  nop
0x1800c13d1  lea     rcx, [rsp+498h+var_3F8]
0x1800c13d9  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800c13de  nop
0x1800c13df  mov     rcx, [rsp+498h+var_3C8+8]; this
0x1800c13e7  test    rcx, rcx
0x1800c13ea  jz      short loc_1800C13F1
0x1800c13ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c13f1  mov     ebx, esi
0x1800c13f3  jmp     loc_1800C10D8
0x1800c13f8  lea     rcx, [rsp+498h+var_128]; this
0x1800c1400  call    ??0ResourceValidationUrisAndValues@@QEAA@XZ; ResourceValidationUrisAndValues::ResourceValidationUrisAndValues(void)
0x1800c1405  nop
0x1800c1406  mov     [rsp+498h+var_410], rdi
0x1800c140e  lea     r9, [rsp+498h+var_410]; unsigned __int16 **
0x1800c1416  lea     r8, aResourcesucces; "ResourceSuccessUri"
0x1800c141d  mov     rdx, rbx; unsigned __int16 *
0x1800c1420  mov     rcx, [rsp+498h+var_3F0]; HKEY
0x1800c1428  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800c142d  mov     esi, eax
0x1800c142f  test    eax, eax
0x1800c1431  jns     short loc_1800C1445
0x1800c1433  lea     rcx, [rsp+498h+var_128]; this
0x1800c143b  call    ??1ResourceValidationUrisAndValues@@QEAA@XZ; ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues(void)
0x1800c1440  jmp     loc_1800C13A7
0x1800c1445  mov     rdx, [rsp+498h+var_410]
0x1800c144d  mov     [rsp+498h+var_358], rdx
0x1800c1455  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800c1459  mov     r8, rsi
0x1800c145c  inc     r8
0x1800c145f  cmp     [rdx+r8*2], di
0x1800c1464  jnz     short loc_1800C145C
0x1800c1466  lea     rcx, [rsp+498h+var_128]
0x1800c146e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c1473  mov     [rsp+498h+var_410], rdi
0x1800c147b  lea     r9, [rsp+498h+var_410]; unsigned __int16 **
0x1800c1483  lea     r8, aResourcesucces_0; "ResourceSuccessValues"
0x1800c148a  mov     rdx, rbx; unsigned __int16 *
0x1800c148d  mov     rcx, [rsp+498h+var_3F0]; HKEY
0x1800c1495  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800c149a  test    eax, eax
0x1800c149c  js      short loc_1800C14D6
0x1800c149e  mov     rdx, [rsp+498h+var_410]
0x1800c14a6  mov     [rsp+498h+var_410], rdx
0x1800c14ae  mov     r8, rsi
0x1800c14b1  inc     r8
0x1800c14b4  cmp     [rdx+r8*2], di
0x1800c14b9  jnz     short loc_1800C14B1
0x1800c14bb  lea     rcx, [rsp+498h+var_108]
0x1800c14c3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c14c8  nop
0x1800c14c9  lea     rcx, [rsp+498h+var_410]
0x1800c14d1  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
  ... truncated ...
```
