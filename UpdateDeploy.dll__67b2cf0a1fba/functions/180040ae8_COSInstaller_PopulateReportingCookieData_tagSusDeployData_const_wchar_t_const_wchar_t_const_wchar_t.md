# COSInstaller::PopulateReportingCookieData(tagSusDeployData const &,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x180040ae8`
- end: `0x180041ba5`
- name: `?PopulateReportingCookieData@COSInstaller@@AEAAJAEBUtagSusDeployData@@PEB_W1PEAPEA_W@Z`
- size: `4285`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this, const struct tagSusDeployData *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003f448`

## callees

- `0x180002214`
- `0x180003180`
- `0x180008ab8`
- `0x1800259b8`
- `0x180027948`
- `0x180040ae8`
- `0x180061960`
- `0x180068ea0`
- `0x180069960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800411eb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800411eb`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180040bce`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180040bce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040c9a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040c9a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180041503`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180041503`
- `OLEAUT32!__imp_SysStringLen` at `0x180040e62`
- `OLEAUT32!__imp_SysStringLen` at `0x180040e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040d3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040ef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800410aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004118c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800412c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800413b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004148b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800415f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800416d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800417a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004187b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004194b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040d3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040e11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040ef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800410aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004118c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800412c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800413b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004148b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800415f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800416d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800417a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004187b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004194b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041a5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041a5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041a24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041a24`

## string_xrefs

- `0x180040c55`: `Windows.Data.Json.JsonValue`
- `0x180040b86`: `Windows.Data.Json.JsonObject`
- `0x180041a4a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800412c0`: `UpdateId`
- `0x180040fce`: `UpdateStackCabFileName`
- `0x1800410a3`: `UpdateAgentName`
- `0x180040e0a`: `SandboxPath`
- `0x180040ef0`: `MergedSandboxPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=120
__int64 __fastcall COSInstaller::PopulateReportingCookieData(
        COSInstaller *this,
        const struct tagSusDeployData *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t **a5)
{
  __int64 v7; // rdx
  int ActivationFactory; // ebx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HSTRING v12; // rbx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  HSTRING v17; // rbx
  __int64 v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, PVOID, __int64 *); // rdi
  __int64 *v22; // rcx
  HSTRING_HEADER *v23; // rax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v26; // rdi
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  __int64 *v31; // rcx
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, PVOID, __int64 *); // rdi
  HSTRING_HEADER *v34; // rax
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v36)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v37; // rdi
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  __int64 *v41; // rcx
  unsigned int v42; // r8d
  __int64 v43; // rbx
  __int64 (__fastcall *v44)(__int64, PVOID, __int64 *); // rsi
  __int64 *v45; // rcx
  HSTRING_HEADER *v46; // rax
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v48)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v49; // rdi
  HRESULT v50; // eax
  int v51; // edx
  unsigned int v52; // r8d
  __int64 *v53; // rcx
  __int64 v54; // rbx
  __int64 (__fastcall *v55)(__int64, PVOID, __int64 *); // rdi
  __int64 *v56; // rcx
  HSTRING_HEADER *v57; // rax
  __int64 (__fastcall ***v58)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v59)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v60; // rdi
  HRESULT v61; // eax
  int v62; // edx
  unsigned int v63; // r8d
  __int64 *v64; // rcx
  __int64 v65; // rbx
  __int64 (__fastcall *v66)(__int64, PVOID, __int64 *); // rdi
  __int64 *v67; // rcx
  HSTRING_HEADER *v68; // rax
  __int64 (__fastcall ***v69)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v70)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v71; // rdi
  HRESULT v72; // eax
  int v73; // edx
  unsigned int v74; // r8d
  unsigned int v75; // r8d
  __int64 *v76; // rcx
  __int64 v77; // rbx
  __int64 (__fastcall *v78)(__int64, PVOID, __int64 *); // rsi
  HSTRING_HEADER *v79; // rax
  __int64 (__fastcall ***v80)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v81)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v82; // rdi
  HRESULT v83; // eax
  int v84; // edx
  unsigned int v85; // r8d
  __int64 *v86; // rcx
  unsigned int v87; // r8d
  __int64 v88; // rbx
  __int64 (__fastcall *v89)(__int64, HSTRING, __int64 *); // rsi
  __int64 *v90; // rcx
  unsigned __int64 v91; // rdi
  unsigned __int64 v92; // rdx
  HRESULT v93; // eax
  int v94; // edx
  unsigned int v95; // r8d
  __int64 (__fastcall ***v96)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v97)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v98; // rsi
  HRESULT v99; // eax
  int v100; // edx
  unsigned int v101; // r8d
  __int64 v102; // rdx
  unsigned int v103; // r8d
  __int64 *v104; // rcx
  __int64 v105; // rbx
  __int64 (__fastcall *v106)(__int64, PVOID, __int64 *); // rsi
  __int64 *v107; // rcx
  HSTRING_HEADER *v108; // rax
  __int64 (__fastcall ***v109)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v110)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v111; // rsi
  HRESULT v112; // eax
  int v113; // edx
  unsigned int v114; // r8d
  __int64 *v115; // rcx
  __int64 v116; // rbx
  __int64 (__fastcall *v117)(__int64, PVOID, __int64 *); // r14
  __int64 *v118; // rcx
  HSTRING_HEADER *v119; // rax
  __int64 (__fastcall ***v120)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v121)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v122; // rsi
  HRESULT v123; // eax
  int v124; // edx
  unsigned int v125; // r8d
  unsigned __int64 v126; // r9
  __int64 *v127; // rcx
  int v128; // edx
  unsigned int v129; // r8d
  const char *v130; // r9
  int LastError; // eax
  __int64 v132; // rbx
  __int64 (__fastcall *v133)(__int64, HSTRING, __int64 *); // rsi
  __int64 *v134; // rcx
  HRESULT v135; // eax
  int v136; // edx
  unsigned int v137; // r8d
  __int64 (__fastcall ***v138)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v139)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v140; // rdi
  HRESULT v141; // eax
  int v142; // edx
  unsigned int v143; // r8d
  __int64 *v144; // rcx
  __int64 v145; // rbx
  __int64 (__fastcall *v146)(__int64, __int64, __int64 *); // rdi
  __int64 *v147; // rcx
  __int64 (__fastcall ***v148)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v149)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v150; // rdi
  HRESULT v151; // eax
  int v152; // edx
  unsigned int v153; // r8d
  __int64 *v154; // rdx
  __int64 v155; // rbx
  __int64 (__fastcall *v156)(__int64, __int64, __int64 *); // rdi
  __int64 (__fastcall ***v157)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v158)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v159; // rdi
  HRESULT v160; // eax
  int v161; // edx
  unsigned int v162; // r8d
  __int64 *v163; // rdx
  __int64 v164; // rbx
  __int64 (__fastcall *v165)(__int64, __int64, __int64 *); // rdi
  __int64 (__fastcall ***v166)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v167)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v168; // rdi
  HRESULT v169; // eax
  int v170; // edx
  unsigned int v171; // r8d
  __int64 *v172; // rdx
  __int64 v173; // rbx
  __int64 (__fastcall *v174)(__int64, __int64, __int64 *); // rdi
  __int64 (__fastcall ***v175)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v176)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v177; // rdi
  HRESULT v178; // eax
  int v179; // edx
  unsigned int v180; // r8d
  __int64 *v181; // rdx
  __int64 (__fastcall ***v182)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v183)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v184; // rbx
  __int64 (__fastcall *v185)(__int64, HSTRING *); // rdi
  WCHAR *StringRawBuffer; // rax
  __int64 *v187; // rcx
  __int64 (__fastcall ***v188)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v189; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v194)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v195; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v196; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v197; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v198)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v199; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v200[2]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR WideCharStr[136]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v196 = a3;
  v195 = a4;
  v199 = 0;
  v198 = 0;
  v197 = 0;
  v200[0] = 0;
  if ( !*((_QWORD *)a2 + 7) )
  {
    v7 = 2029;
LABEL_7:
    ActivationFactory = -2147467261;
LABEL_114:
    v126 = (unsigned int)ActivationFactory;
LABEL_179:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v126,
      lpWideCharStr);
    goto LABEL_181;
  }
  if ( !a3 )
  {
    v7 = 2030;
    goto LABEL_7;
  }
  if ( !a5 )
  {
    v7 = 2031;
    goto LABEL_7;
  }
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    __debugbreak();
  }
  v12 = string;
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  if ( v198 )
  {
    v198 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
  }
  v198 = 0;
  v194 = 0;
  ActivationFactory = RoActivateInstance(v12, &v194);
  if ( ActivationFactory >= 0 )
  {
    if ( !memcmp(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v198 = v194;
    }
    else
    {
      ActivationFactory = (**v194)(v194, &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, (__int64 *)&v198);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v194)[2])(v194);
    }
  }
  if ( ActivationFactory < 0 )
  {
    v7 = 2044;
    goto LABEL_114;
  }
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
    __debugbreak();
  }
  v17 = string;
  v18 = v199;
  if ( v199 )
  {
    v199 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  ActivationFactory = RoGetActivationFactory(v17, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v199);
  if ( ActivationFactory < 0 )
  {
    v7 = 2046;
    goto LABEL_114;
  }
  v20 = v199;
  v21 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
  v22 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v22 + 16LL))((__int64 *)v22);
  }
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &hstringHeader,
          (const WCHAR **)(*((_QWORD *)a2 + 7) + 352LL),
          v19);
  ActivationFactory = v21(v20, v23[1].Reserved.Reserved1, (__int64 *)&v197);
  if ( ActivationFactory < 0 )
  {
    v7 = 2049;
    goto LABEL_114;
  }
  v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v25 = (*v198)[7];
  v26 = v197;
  string = 0;
  v27 = WindowsCreateStringReference(L"ProductName", 0xBu, &hstringHeader, &string);
  if ( v27 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
    __debugbreak();
  }
  ActivationFactory = v25(v24, (GUID *)string, v26);
  if ( ActivationFactory < 0 )
  {
    v7 = 2050;
    goto LABEL_114;
  }
  v31 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v31 + 16LL))((__int64 *)v31);
    v31 = (__int64)v197;
  }
  v32 = v199;
  v33 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
  if ( v31 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v31 + 16LL))((__int64 *)v31);
  }
  v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)a2 + 2, v30);
  ActivationFactory = v33(v32, v34[1].Reserved.Reserved1, (__int64 *)&v197);
  if ( ActivationFactory < 0 )
  {
    v7 = 2053;
    goto LABEL_114;
  }
  v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v36 = (*v198)[7];
  v37 = v197;
  string = 0;
  v38 = WindowsCreateStringReference(L"SandboxPath", 0xBu, &hstringHeader, &string);
  if ( v38 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
    __debugbreak();
  }
  ActivationFactory = v36(v35, (GUID *)string, v37);
  if ( ActivationFactory < 0 )
  {
    v7 = 2054;
    goto LABEL_114;
  }
  v41 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v41 + 16LL))((__int64 *)v41);
  }
  if ( SysStringLen(*((BSTR *)a2 + 3)) )
  {
    v43 = v199;
    v44 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
    v45 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v45 + 16LL))((__int64 *)v45);
    }
    v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)a2 + 3, v42);
    ActivationFactory = v44(v43, v46[1].Reserved.Reserved1, (__int64 *)&v197);
    if ( ActivationFactory < 0 )
    {
      v7 = 2060;
      goto LABEL_114;
    }
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
    v48 = (*v198)[7];
    v49 = v197;
    string = 0;
    v50 = WindowsCreateStringReference(L"MergedSandboxPath", 0x11u, &hstringHeader, &string);
    if ( v50 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v50, v51, v52);
      __debugbreak();
    }
    ActivationFactory = v48(v47, (GUID *)string, v49);
    if ( ActivationFactory < 0 )
    {
      v7 = 2062;
      goto LABEL_114;
    }
    v53 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v53 + 16LL))((__int64 *)v53);
    }
  }
  if ( a4 )
  {
    v54 = v199;
    v55 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
    v56 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v56 + 16LL))((__int64 *)v56);
    }
    v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v195, v42);
    ActivationFactory = v55(v54, v57[1].Reserved.Reserved1, (__int64 *)&v197);
    if ( ActivationFactory < 0 )
    {
      v7 = 2068;
      goto LABEL_114;
    }
    v58 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
    v59 = (*v198)[7];
    v60 = v197;
    string = 0;
    v61 = WindowsCreateStringReference(L"UpdateStackCabFileName", 0x16u, &hstringHeader, &string);
    if ( v61 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v61, v62, v63);
      __debugbreak();
    }
    ActivationFactory = v59(v58, (GUID *)string, v60);
    if ( ActivationFactory < 0 )
    {
      v7 = 2070;
      goto LABEL_114;
    }
    v64 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v64 + 16LL))((__int64 *)v64);
    }
  }
  v65 = v199;
  v66 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
  v67 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v67 + 16LL))((__int64 *)v67);
  }
  v68 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v196, v42);
  ActivationFactory = v66(v65, v68[1].Reserved.Reserved1, (__int64 *)&v197);
  if ( ActivationFactory < 0 )
  {
    v7 = 2074;
    goto LABEL_114;
  }
  v69 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v70 = (*v198)[7];
  v71 = v197;
  string = 0;
  v72 = WindowsCreateStringReference(L"UpdateAgentName", 0xFu, &hstringHeader, &string);
  if ( v72 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v72, v73, v74);
    __debugbreak();
  }
  ActivationFactory = v70(v69, (GUID *)string, v71);
  if ( ActivationFactory < 0 )
  {
    v7 = 2075;
    goto LABEL_114;
  }
  v76 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v76 + 16LL))((__int64 *)v76);
    v76 = (__int64)v197;
  }
  if ( *((_QWORD *)a2 + 32) )
  {
    v77 = v199;
    v78 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
    if ( v76 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v76 + 16LL))((__int64 *)v76);
    }
    v79 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)a2 + 32, v75);
    ActivationFactory = v78(v77, v79[1].Reserved.Reserved1, (__int64 *)&v197);
    if ( ActivationFactory < 0 )
    {
      v7 = 2081;
      goto LABEL_114;
    }
    v80 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
    v81 = (*v198)[7];
    v82 = v197;
    string = 0;
    v83 = WindowsCreateStringReference(L"SessionData", 0xBu, &hstringHeader, &string);
    if ( v83 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v83, v84, v85);
      __debugbreak();
    }
    ActivationFactory = v81(v80, (GUID *)string, v82);
    if ( ActivationFactory < 0 )
    {
      v7 = 2082;
      goto LABEL_114;
    }
    v86 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v86 + 16LL))((__int64 *)v86);
    }
  }
  if ( !StringFromGUID2((const GUID *const)(*((_QWORD *)a2 + 7) + 4LL), sz, 39) )
  {
    ActivationFactory = -2147024809;
    v7 = 2087;
    goto LABEL_114;
  }
  v88 = v199;
  v89 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v199 + 80LL);
  v90 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v90 + 16LL))((__int64 *)v90);
  }
  v91 = -1;
  v92 = -1;
  do
    ++v92;
  while ( sz[v92] );
  if ( v92 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v92, v87);
    __debugbreak();
  }
  if ( (int)v92 + 1 < (unsigned int)v92 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v92, v87);
    __debugbreak();
  }
  v93 = WindowsCreateStringReference(sz, v92, &hstringHeader, &string);
  if ( v93 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v93, v94, v95);
    __debugbreak();
  }
  ActivationFactory = v89(v88, string, (__int64 *)&v197);
  if ( ActivationFactory < 0 )
  {
    v7 = 2088;
    goto LABEL_114;
  }
  v96 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v97 = (*v198)[7];
  v98 = v197;
  string = 0;
  v99 = WindowsCreateStringReference(L"UpdateId", 8u, &hstringHeader, &string);
  if ( v99 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v99, v100, v101);
    __debugbreak();
  }
  ActivationFactory = v97(v96, (GUID *)string, v98);
  if ( ActivationFactory < 0 )
  {
    v7 = 2089;
    goto LABEL_114;
  }
  v104 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v104 + 16LL))((__int64 *)v104);
  }
  if ( *(_QWORD *)a2 && **(_WORD **)a2 )
  {
    v105 = v199;
    v106 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
    v107 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v107 + 16LL))((__int64 *)v107);
    }
    v108 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)a2, v103);
    ActivationFactory = v106(v105, v108[1].Reserved.Reserved1, (__int64 *)&v197);
    if ( ActivationFactory < 0 )
    {
      v7 = 2094;
      goto LABEL_114;
    }
    v109 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
    v110 = (*v198)[7];
    v111 = v197;
    string = 0;
    v112 = WindowsCreateStringReference(L"ServerId", 8u, &hstringHeader, &string);
    if ( v112 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v112, v113, v114);
      __debugbreak();
    }
    ActivationFactory = v110(v109, (GUID *)string, v111);
    if ( ActivationFactory < 0 )
    {
      v7 = 2095;
      goto LABEL_114;
    }
    v115 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v115 + 16LL))((__int64 *)v115);
    }
  }
  if ( *((_QWORD *)a2 + 13) )
  {
    v116 = v199;
    v117 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v199 + 80LL);
    v118 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v118 + 16LL))((__int64 *)v118);
    }
    v119 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)a2 + 13, v103);
    ActivationFactory = v117(v116, v119[1].Reserved.Reserved1, (__int64 *)&v197);
    if ( ActivationFactory < 0 )
    {
      v7 = 2101;
      goto LABEL_114;
    }
    v120 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
    v121 = (*v198)[7];
    v122 = v197;
    string = 0;
    v123 = WindowsCreateStringReference(L"FlightId", 8u, &hstringHeader, &string);
    if ( v123 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v123, v124, v125);
      __debugbreak();
    }
    ActivationFactory = v121(v120, (GUID *)string, v122);
    if ( ActivationFactory < 0 )
    {
      v7 = 2102;
      goto LABEL_114;
    }
    v127 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v127 + 16LL))((__int64 *)v127);
    }
  }
  if ( *((_BYTE *)a2 + 112) )
  {
    if ( !MultiByteToWideChar(0, 1u, (LPCCH)a2 + 112, -1, WideCharStr, 129) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7F,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MultiByteUtil.cpp",
                    v130);
      ActivationFactory = LastError;
      if ( LastError < 0 )
      {
        v7 = 2111;
LABEL_178:
        v126 = (unsigned int)LastError;
        goto LABEL_179;
      }
    }
    v132 = v199;
    v133 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v199 + 80LL);
    v134 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v134 + 16LL))((__int64 *)v134);
    }
    do
      ++v91;
    while ( WideCharStr[v91] );
    if ( v91 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v128, v129);
      __debugbreak();
    }
    if ( (int)v91 + 1 < (unsigned int)v91 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v128, v129);
      __debugbreak();
    }
    v135 = WindowsCreateStringReference(WideCharStr, v91, &hstringHeader, &string);
    if ( v135 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v135, v136, v137);
      __debugbreak();
    }
    LastError = v133(v132, string, (__int64 *)&v197);
    ActivationFactory = LastError;
    if ( LastError < 0 )
    {
      v7 = 2112;
      goto LABEL_178;
    }
    v138 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
    v139 = (*v198)[7];
    v140 = v197;
    string = 0;
    v141 = WindowsCreateStringReference(L"CV", 2u, &hstringHeader, &string);
    if ( v141 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v141, v142, v143);
      __debugbreak();
    }
    LastError = v139(v138, (GUID *)string, v140);
    ActivationFactory = LastError;
    if ( LastError < 0 )
    {
      v7 = 2113;
      goto LABEL_178;
    }
    v144 = (__int64)v197;
    if ( v197 )
    {
      v197 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v144 + 16LL))((__int64 *)v144);
    }
  }
  v194 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)a2 + 7) + 360LL);
  v145 = v199;
  v146 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v199 + 72LL);
  v147 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v147 + 16LL))((__int64 *)v147);
  }
  LastError = v146(v145, v102, (__int64 *)&v197);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2118;
    goto LABEL_178;
  }
  v148 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v149 = (*v198)[7];
  v150 = v197;
  string = 0;
  v151 = WindowsCreateStringReference(L"ProductMajorVer", 0xFu, &hstringHeader, &string);
  if ( v151 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v151, v152, v153);
    __debugbreak();
  }
  LastError = v149(v148, (GUID *)string, v150);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2119;
    goto LABEL_178;
  }
  v154 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v154 + 16LL))((__int64 *)v154);
    v154 = (__int64)v197;
  }
  v155 = v199;
  v156 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v199 + 72LL);
  if ( v154 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v154 + 16LL))((__int64 *)v154);
  }
  LastError = v156(v155, v154, (__int64 *)&v197);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2122;
    goto LABEL_178;
  }
  v157 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v158 = (*v198)[7];
  v159 = v197;
  string = 0;
  v160 = WindowsCreateStringReference(L"ProductMinorVer", 0xFu, &hstringHeader, &string);
  if ( v160 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v160, v161, v162);
    __debugbreak();
  }
  LastError = v158(v157, (GUID *)string, v159);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2123;
    goto LABEL_178;
  }
  v163 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v163 + 16LL))((__int64 *)v163);
    v163 = (__int64)v197;
  }
  v164 = v199;
  v165 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v199 + 72LL);
  if ( v163 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v163 + 16LL))((__int64 *)v163);
  }
  LastError = v165(v164, v163, (__int64 *)&v197);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2126;
    goto LABEL_178;
  }
  v166 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v167 = (*v198)[7];
  v168 = v197;
  string = 0;
  v169 = WindowsCreateStringReference(L"ProductBuildMajorVer", 0x14u, &hstringHeader, &string);
  if ( v169 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v169, v170, v171);
    JUMPOUT(0x180041BA4LL);
  }
  LastError = v167(v166, (GUID *)string, v168);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2128;
    goto LABEL_178;
  }
  v172 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v172 + 16LL))((__int64 *)v172);
    v172 = (__int64)v197;
  }
  v173 = v199;
  v174 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v199 + 72LL);
  if ( v172 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v172 + 16LL))((__int64 *)v172);
  }
  LastError = v174(v173, v172, (__int64 *)&v197);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2131;
    goto LABEL_178;
  }
  v175 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v176 = (*v198)[7];
  v177 = v197;
  string = 0;
  v178 = WindowsCreateStringReference(L"ProductBuildMinorVer", 0x14u, &hstringHeader, &string);
  if ( v178 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v178, v179, v180);
    __debugbreak();
  }
  LastError = v176(v175, (GUID *)string, v177);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2133;
    goto LABEL_178;
  }
  v181 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v181 + 16LL))((__int64 *)v181);
    v181 = (__int64)v197;
  }
  v182 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  v183 = **v198;
  if ( v181 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v181 + 16LL))((__int64 *)v181);
  }
  LastError = v183(v182, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, (__int64 *)&v197);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2137;
    goto LABEL_178;
  }
  v184 = (__int64)v197;
  v185 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*v197 + 56);
  WindowsDeleteString(v200[0]);
  v200[0] = 0;
  LastError = v185(v184, v200);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2138;
    goto LABEL_178;
  }
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(v200[0], 0);
  LastError = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a5);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2140;
    goto LABEL_178;
  }
  ActivationFactory = 0;
LABEL_181:
  WindowsDeleteString(v200[0]);
  v200[0] = 0;
  v187 = (__int64)v197;
  if ( v197 )
  {
    v197 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v187 + 16LL))((__int64 *)v187);
  }
  v188 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v198;
  if ( v198 )
  {
    v198 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v188)[2])(v188);
  }
  v189 = v199;
  if ( v199 )
  {
    v199 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v189 + 16LL))(v189);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180040ae8  mov     [rsp-8+arg_0], rbx
0x180040aed  push    rbp
0x180040aee  push    rsi
0x180040aef  push    rdi
0x180040af0  push    r12
0x180040af2  push    r13
0x180040af4  push    r14
0x180040af6  push    r15
0x180040af8  lea     rbp, [rsp-100h]
0x180040b00  sub     rsp, 200h
0x180040b07  mov     rax, cs:__security_cookie
0x180040b0e  xor     rax, rsp
0x180040b11  mov     [rbp+130h+var_40], rax
0x180040b18  mov     r14, r9
0x180040b1b  mov     r15, rdx
0x180040b1e  mov     [rsp+230h+var_1D0], r8
0x180040b23  mov     [rsp+230h+var_1D8], r9
0x180040b28  mov     r12, [rbp+130h+arg_20]
0x180040b2f  xor     r13d, r13d
0x180040b32  mov     [rsp+230h+var_1B8], r13
0x180040b37  mov     [rsp+230h+var_1C0], r13
0x180040b3c  mov     [rsp+230h+var_1C8], r13
0x180040b41  mov     [rbp+130h+var_1B0], r13
0x180040b45  cmp     [rdx+38h], r13
0x180040b49  jnz     short loc_180040B52
0x180040b4b  mov     edx, 7EDh
0x180040b50  jmp     short loc_180040B68
0x180040b52  test    r8, r8
0x180040b55  jnz     short loc_180040B5E
0x180040b57  mov     edx, 7EEh
0x180040b5c  jmp     short loc_180040B68
0x180040b5e  test    r12, r12
0x180040b61  jnz     short loc_180040B72
0x180040b63  mov     edx, 7EFh
0x180040b68  mov     ebx, 80004003h
0x180040b6d  jmp     loc_1800414B7
0x180040b72  mov     [rsp+230h+string], r13
0x180040b77  lea     r9, [rsp+230h+string]; string
0x180040b7c  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x180040b81  mov     edx, 1Ch; length
0x180040b86  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x180040b8d  call    cs:__imp_WindowsCreateStringReference
0x180040b93  test    eax, eax
0x180040b95  js      loc_180041AFC
0x180040b9b  mov     rbx, [rsp+230h+string]
0x180040ba0  mov     rcx, [rsp+230h+var_1C0]
0x180040ba5  test    rcx, rcx
0x180040ba8  jz      short loc_180040BBC
0x180040baa  mov     [rsp+230h+var_1C0], r13
0x180040baf  mov     rax, [rcx]
0x180040bb2  mov     rax, [rax+10h]
0x180040bb6  call    _guard_dispatch_icall
0x180040bbb  nop
0x180040bbc  mov     [rsp+230h+var_1C0], r13
0x180040bc1  mov     [rsp+230h+var_1E0], r13
0x180040bc6  lea     rdx, [rsp+230h+var_1E0]
0x180040bcb  mov     rcx, rbx
0x180040bce  call    cs:__imp_RoActivateInstance
0x180040bd4  mov     ebx, eax
0x180040bd6  test    eax, eax
0x180040bd8  js      short loc_180040C33
0x180040bda  mov     r8d, 10h; Size
0x180040be0  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180040be7  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x180040bee  call    memcmp
0x180040bf3  test    eax, eax
0x180040bf5  jnz     short loc_180040C03
0x180040bf7  mov     rax, [rsp+230h+var_1E0]
0x180040bfc  mov     [rsp+230h+var_1C0], rax
0x180040c01  jmp     short loc_180040C33
0x180040c03  mov     rcx, [rsp+230h+var_1E0]
0x180040c08  mov     rax, [rcx]
0x180040c0b  lea     r8, [rsp+230h+var_1C0]
0x180040c10  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x180040c17  mov     rax, [rax]
0x180040c1a  call    _guard_dispatch_icall
0x180040c1f  mov     ebx, eax
0x180040c21  mov     rcx, [rsp+230h+var_1E0]
0x180040c26  mov     rax, [rcx]
0x180040c29  mov     rax, [rax+10h]
0x180040c2d  call    _guard_dispatch_icall
0x180040c32  nop
0x180040c33  test    ebx, ebx
0x180040c35  jns     short loc_180040C41
0x180040c37  mov     edx, 7FCh
0x180040c3c  jmp     loc_1800414B7
0x180040c41  mov     [rsp+230h+string], r13
0x180040c46  lea     r9, [rsp+230h+string]; string
0x180040c4b  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x180040c50  mov     edx, 1Bh; length
0x180040c55  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x180040c5c  call    cs:__imp_WindowsCreateStringReference
0x180040c62  test    eax, eax
0x180040c64  js      loc_180041B04
0x180040c6a  mov     rbx, [rsp+230h+string]
0x180040c6f  mov     rcx, [rsp+230h+var_1B8]
0x180040c74  test    rcx, rcx
0x180040c77  jz      short loc_180040C8B
0x180040c79  mov     [rsp+230h+var_1B8], r13
0x180040c7e  mov     rax, [rcx]
0x180040c81  mov     rax, [rax+10h]
0x180040c85  call    _guard_dispatch_icall
0x180040c8a  nop
0x180040c8b  lea     r8, [rsp+230h+var_1B8]
0x180040c90  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180040c97  mov     rcx, rbx
0x180040c9a  call    cs:__imp_RoGetActivationFactory
0x180040ca0  mov     ebx, eax
0x180040ca2  test    eax, eax
0x180040ca4  jns     short loc_180040CB0
0x180040ca6  mov     edx, 7FEh
0x180040cab  jmp     loc_1800414B7
0x180040cb0  mov     rbx, [rsp+230h+var_1B8]
0x180040cb5  mov     rax, [rbx]
0x180040cb8  mov     rdi, [rax+50h]
0x180040cbc  mov     rcx, [rsp+230h+var_1C8]
0x180040cc1  test    rcx, rcx
0x180040cc4  jz      short loc_180040CD8
0x180040cc6  mov     [rsp+230h+var_1C8], r13
0x180040ccb  mov     rax, [rcx]
0x180040cce  mov     rax, [rax+10h]
0x180040cd2  call    _guard_dispatch_icall
0x180040cd7  nop
0x180040cd8  mov     rdx, [r15+38h]
0x180040cdc  add     rdx, 160h
0x180040ce3  lea     rcx, [rsp+230h+hstringHeader]
0x180040ce8  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x180040ced  nop
0x180040cee  lea     r8, [rsp+230h+var_1C8]
0x180040cf3  mov     rdx, [rax+18h]
0x180040cf7  mov     rcx, rbx
0x180040cfa  mov     rax, rdi
0x180040cfd  call    _guard_dispatch_icall
0x180040d02  mov     ebx, eax
0x180040d04  test    eax, eax
0x180040d06  jns     short loc_180040D12
0x180040d08  mov     edx, 801h
0x180040d0d  jmp     loc_1800414B7
0x180040d12  mov     rbx, [rsp+230h+var_1C0]
0x180040d17  mov     rax, [rbx]
0x180040d1a  mov     rsi, [rax+38h]
0x180040d1e  mov     rdi, [rsp+230h+var_1C8]
0x180040d23  mov     [rsp+230h+string], r13
0x180040d28  lea     r9, [rsp+230h+string]; string
0x180040d2d  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x180040d32  mov     edx, 0Bh; length
0x180040d37  lea     rcx, aProductname; "ProductName"
0x180040d3e  call    cs:__imp_WindowsCreateStringReference
0x180040d44  test    eax, eax
0x180040d46  js      loc_180041B0C
0x180040d4c  mov     r8, rdi
0x180040d4f  mov     rdx, [rsp+230h+string]
0x180040d54  mov     rcx, rbx
0x180040d57  mov     rax, rsi
0x180040d5a  call    _guard_dispatch_icall
0x180040d5f  mov     ebx, eax
0x180040d61  test    eax, eax
0x180040d63  jns     short loc_180040D6F
0x180040d65  mov     edx, 802h
0x180040d6a  jmp     loc_1800414B7
0x180040d6f  mov     rcx, [rsp+230h+var_1C8]
0x180040d74  test    rcx, rcx
0x180040d77  jz      short loc_180040D8F
0x180040d79  mov     [rsp+230h+var_1C8], r13
0x180040d7e  mov     rax, [rcx]
0x180040d81  mov     rax, [rax+10h]
0x180040d85  call    _guard_dispatch_icall
0x180040d8a  mov     rcx, [rsp+230h+var_1C8]
0x180040d8f  mov     rbx, [rsp+230h+var_1B8]
0x180040d94  mov     rax, [rbx]
0x180040d97  mov     rdi, [rax+50h]
0x180040d9b  test    rcx, rcx
0x180040d9e  jz      short loc_180040DB2
0x180040da0  mov     [rsp+230h+var_1C8], r13
0x180040da5  mov     rax, [rcx]
0x180040da8  mov     rax, [rax+10h]
0x180040dac  call    _guard_dispatch_icall
0x180040db1  nop
0x180040db2  lea     rdx, [r15+10h]
0x180040db6  lea     rcx, [rsp+230h+hstringHeader]
0x180040dbb  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x180040dc0  nop
0x180040dc1  lea     r8, [rsp+230h+var_1C8]
0x180040dc6  mov     rdx, [rax+18h]
0x180040dca  mov     rcx, rbx
0x180040dcd  mov     rax, rdi
0x180040dd0  call    _guard_dispatch_icall
0x180040dd5  mov     ebx, eax
0x180040dd7  test    eax, eax
0x180040dd9  jns     short loc_180040DE5
0x180040ddb  mov     edx, 805h
0x180040de0  jmp     loc_1800414B7
0x180040de5  mov     rbx, [rsp+230h+var_1C0]
0x180040dea  mov     rax, [rbx]
0x180040ded  mov     rsi, [rax+38h]
0x180040df1  mov     rdi, [rsp+230h+var_1C8]
0x180040df6  mov     [rsp+230h+string], r13
0x180040dfb  lea     r9, [rsp+230h+string]; string
0x180040e00  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x180040e05  mov     edx, 0Bh; length
0x180040e0a  lea     rcx, aSandboxpath_0; "SandboxPath"
0x180040e11  call    cs:__imp_WindowsCreateStringReference
0x180040e17  test    eax, eax
0x180040e19  js      loc_180041B14
0x180040e1f  mov     r8, rdi
0x180040e22  mov     rdx, [rsp+230h+string]
0x180040e27  mov     rcx, rbx
0x180040e2a  mov     rax, rsi
0x180040e2d  call    _guard_dispatch_icall
0x180040e32  mov     ebx, eax
0x180040e34  test    eax, eax
0x180040e36  jns     short loc_180040E42
0x180040e38  mov     edx, 806h
0x180040e3d  jmp     loc_1800414B7
0x180040e42  mov     rcx, [rsp+230h+var_1C8]
0x180040e47  test    rcx, rcx
0x180040e4a  jz      short loc_180040E5E
0x180040e4c  mov     [rsp+230h+var_1C8], r13
0x180040e51  mov     rax, [rcx]
0x180040e54  mov     rax, [rax+10h]
0x180040e58  call    _guard_dispatch_icall
0x180040e5d  nop
0x180040e5e  mov     rcx, [r15+18h]; pbstr
0x180040e62  call    cs:__imp_SysStringLen
0x180040e68  test    eax, eax
0x180040e6a  jz      loc_180040F44
0x180040e70  mov     rbx, [rsp+230h+var_1B8]
0x180040e75  mov     rax, [rbx]
0x180040e78  mov     rsi, [rax+50h]
0x180040e7c  mov     rcx, [rsp+230h+var_1C8]
0x180040e81  test    rcx, rcx
0x180040e84  jz      short loc_180040E98
0x180040e86  mov     [rsp+230h+var_1C8], r13
0x180040e8b  mov     rax, [rcx]
0x180040e8e  mov     rax, [rax+10h]
0x180040e92  call    _guard_dispatch_icall
0x180040e97  nop
0x180040e98  lea     rdx, [r15+18h]
0x180040e9c  lea     rcx, [rsp+230h+hstringHeader]
0x180040ea1  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x180040ea6  nop
0x180040ea7  lea     r8, [rsp+230h+var_1C8]
0x180040eac  mov     rdx, [rax+18h]
0x180040eb0  mov     rcx, rbx
0x180040eb3  mov     rax, rsi
0x180040eb6  call    _guard_dispatch_icall
0x180040ebb  mov     ebx, eax
0x180040ebd  test    eax, eax
0x180040ebf  jns     short loc_180040ECB
0x180040ec1  mov     edx, 80Ch
0x180040ec6  jmp     loc_1800414B7
0x180040ecb  mov     rbx, [rsp+230h+var_1C0]
0x180040ed0  mov     rax, [rbx]
0x180040ed3  mov     rsi, [rax+38h]
0x180040ed7  mov     rdi, [rsp+230h+var_1C8]
0x180040edc  mov     [rsp+230h+string], r13
0x180040ee1  lea     r9, [rsp+230h+string]; string
0x180040ee6  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x180040eeb  mov     edx, 11h; length
0x180040ef0  lea     rcx, aMergedsandboxp_0; "MergedSandboxPath"
0x180040ef7  call    cs:__imp_WindowsCreateStringReference
0x180040efd  test    eax, eax
0x180040eff  js      loc_180041B1C
0x180040f05  mov     r8, rdi
0x180040f08  mov     rdx, [rsp+230h+string]
0x180040f0d  mov     rcx, rbx
0x180040f10  mov     rax, rsi
0x180040f13  call    _guard_dispatch_icall
0x180040f18  mov     ebx, eax
0x180040f1a  test    eax, eax
0x180040f1c  jns     short loc_180040F28
0x180040f1e  mov     edx, 80Eh
0x180040f23  jmp     loc_1800414B7
0x180040f28  mov     rcx, [rsp+230h+var_1C8]
0x180040f2d  test    rcx, rcx
0x180040f30  jz      short loc_180040F44
0x180040f32  mov     [rsp+230h+var_1C8], r13
0x180040f37  mov     rax, [rcx]
0x180040f3a  mov     rax, [rax+10h]
0x180040f3e  call    _guard_dispatch_icall
0x180040f43  nop
0x180040f44  test    r14, r14
0x180040f47  jz      loc_180041022
0x180040f4d  mov     rbx, [rsp+230h+var_1B8]
0x180040f52  mov     rax, [rbx]
0x180040f55  mov     rdi, [rax+50h]
0x180040f59  mov     rcx, [rsp+230h+var_1C8]
0x180040f5e  test    rcx, rcx
0x180040f61  jz      short loc_180040F75
0x180040f63  mov     [rsp+230h+var_1C8], r13
0x180040f68  mov     rax, [rcx]
0x180040f6b  mov     rax, [rax+10h]
0x180040f6f  call    _guard_dispatch_icall
0x180040f74  nop
0x180040f75  lea     rdx, [rsp+230h+var_1D8]
0x180040f7a  lea     rcx, [rsp+230h+hstringHeader]
0x180040f7f  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x180040f84  nop
0x180040f85  lea     r8, [rsp+230h+var_1C8]
0x180040f8a  mov     rdx, [rax+18h]
  ... truncated ...
```
