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
// Hidden C++ exception states: #wind=124
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
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rdi
  __int64 *v21; // rcx
  __int64 v22; // rax
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v25; // rdi
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 *v29; // rcx
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // rdi
  __int64 v32; // rax
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v35; // rdi
  HRESULT v36; // eax
  int v37; // edx
  unsigned int v38; // r8d
  __int64 *v39; // rcx
  __int64 v40; // rbx
  __int64 (__fastcall *v41)(__int64, _QWORD, __int64 *); // rsi
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v45)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v46; // rdi
  HRESULT v47; // eax
  int v48; // edx
  unsigned int v49; // r8d
  __int64 *v50; // rcx
  __int64 v51; // rbx
  __int64 (__fastcall *v52)(__int64, _QWORD, __int64 *); // rdi
  __int64 *v53; // rcx
  __int64 v54; // rax
  __int64 (__fastcall ***v55)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v56)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v57; // rdi
  HRESULT v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  __int64 *v61; // rcx
  __int64 v62; // rbx
  __int64 (__fastcall *v63)(__int64, _QWORD, __int64 *); // rdi
  __int64 *v64; // rcx
  __int64 v65; // rax
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v67)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v68; // rdi
  HRESULT v69; // eax
  int v70; // edx
  unsigned int v71; // r8d
  __int64 *v72; // rcx
  __int64 v73; // rbx
  __int64 (__fastcall *v74)(__int64, _QWORD, __int64 *); // rsi
  __int64 v75; // rax
  __int64 (__fastcall ***v76)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v77)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v78; // rdi
  HRESULT v79; // eax
  int v80; // edx
  unsigned int v81; // r8d
  __int64 *v82; // rcx
  unsigned int v83; // r8d
  __int64 v84; // rbx
  __int64 (__fastcall *v85)(__int64, HSTRING, __int64 *); // rsi
  __int64 *v86; // rcx
  unsigned __int64 v87; // rdi
  unsigned __int64 v88; // rdx
  HRESULT v89; // eax
  int v90; // edx
  unsigned int v91; // r8d
  __int64 (__fastcall ***v92)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v93)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v94; // rsi
  HRESULT v95; // eax
  int v96; // edx
  unsigned int v97; // r8d
  __int64 v98; // rdx
  __int64 *v99; // rcx
  __int64 v100; // rbx
  __int64 (__fastcall *v101)(__int64, _QWORD, __int64 *); // rsi
  __int64 *v102; // rcx
  __int64 v103; // rax
  __int64 (__fastcall ***v104)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v105)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v106; // rsi
  HRESULT v107; // eax
  int v108; // edx
  unsigned int v109; // r8d
  __int64 *v110; // rcx
  __int64 v111; // rbx
  __int64 (__fastcall *v112)(__int64, _QWORD, __int64 *); // r14
  __int64 *v113; // rcx
  __int64 v114; // rax
  __int64 (__fastcall ***v115)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v116)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v117; // rsi
  HRESULT v118; // eax
  int v119; // edx
  unsigned int v120; // r8d
  unsigned __int64 v121; // r9
  __int64 *v122; // rcx
  int v123; // edx
  unsigned int v124; // r8d
  const char *v125; // r9
  int LastError; // eax
  __int64 v127; // rbx
  __int64 (__fastcall *v128)(__int64, HSTRING, __int64 *); // rsi
  __int64 *v129; // rcx
  HRESULT v130; // eax
  int v131; // edx
  unsigned int v132; // r8d
  __int64 (__fastcall ***v133)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v134)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v135; // rdi
  HRESULT v136; // eax
  int v137; // edx
  unsigned int v138; // r8d
  __int64 *v139; // rcx
  __int64 v140; // rbx
  __int64 (__fastcall *v141)(__int64, __int64, __int64 *); // rdi
  __int64 *v142; // rcx
  __int64 (__fastcall ***v143)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v144)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v145; // rdi
  HRESULT v146; // eax
  int v147; // edx
  unsigned int v148; // r8d
  __int64 *v149; // rdx
  __int64 v150; // rbx
  __int64 (__fastcall *v151)(__int64, __int64, __int64 *); // rdi
  __int64 (__fastcall ***v152)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v153)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v154; // rdi
  HRESULT v155; // eax
  int v156; // edx
  unsigned int v157; // r8d
  __int64 *v158; // rdx
  __int64 v159; // rbx
  __int64 (__fastcall *v160)(__int64, __int64, __int64 *); // rdi
  __int64 (__fastcall ***v161)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v162)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v163; // rdi
  HRESULT v164; // eax
  int v165; // edx
  unsigned int v166; // r8d
  __int64 *v167; // rdx
  __int64 v168; // rbx
  __int64 (__fastcall *v169)(__int64, __int64, __int64 *); // rdi
  __int64 (__fastcall ***v170)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v171)(_QWORD, GUID *, __int64 *); // rsi
  __int64 *v172; // rdi
  HRESULT v173; // eax
  int v174; // edx
  unsigned int v175; // r8d
  __int64 *v176; // rdx
  __int64 (__fastcall ***v177)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v178)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v179; // rbx
  __int64 (__fastcall *v180)(__int64, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 *v182; // rcx
  __int64 (__fastcall ***v183)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v184; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v189)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v190; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v191; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v192; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v193)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v194; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v195[2]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR WideCharStr[136]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v191 = a3;
  v190 = a4;
  v194 = 0;
  v193 = 0;
  v192 = 0;
  v195[0] = 0;
  if ( !*((_QWORD *)a2 + 7) )
  {
    v7 = 2029;
LABEL_7:
    ActivationFactory = -2147467261;
LABEL_114:
    v121 = (unsigned int)ActivationFactory;
LABEL_179:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v121,
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
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  if ( v193 )
  {
    v193 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
  }
  v193 = 0;
  v189 = 0;
  ActivationFactory = RoActivateInstance(v12, &v189);
  if ( ActivationFactory >= 0 )
  {
    if ( !memcmp(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v193 = v189;
    }
    else
    {
      ActivationFactory = (**v189)(v189, &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, (__int64 *)&v193);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v189)[2])(v189);
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
  v18 = v194;
  if ( v194 )
  {
    v194 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  ActivationFactory = RoGetActivationFactory(v17, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v194);
  if ( ActivationFactory < 0 )
  {
    v7 = 2046;
    goto LABEL_114;
  }
  v19 = v194;
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
  v21 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v21 + 16LL))((__int64 *)v21);
  }
  v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, *((_QWORD *)a2 + 7) + 352LL);
  ActivationFactory = v20(v19, *(_QWORD *)(v22 + 24), (__int64 *)&v192);
  if ( ActivationFactory < 0 )
  {
    v7 = 2049;
    goto LABEL_114;
  }
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v24 = (*v193)[7];
  v25 = v192;
  string = 0;
  v26 = WindowsCreateStringReference(L"ProductName", 0xBu, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
    __debugbreak();
  }
  ActivationFactory = v24(v23, (GUID *)string, v25);
  if ( ActivationFactory < 0 )
  {
    v7 = 2050;
    goto LABEL_114;
  }
  v29 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v29 + 16LL))((__int64 *)v29);
    v29 = (__int64)v192;
  }
  v30 = v194;
  v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
  if ( v29 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v29 + 16LL))((__int64 *)v29);
  }
  v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)a2 + 16);
  ActivationFactory = v31(v30, *(_QWORD *)(v32 + 24), (__int64 *)&v192);
  if ( ActivationFactory < 0 )
  {
    v7 = 2053;
    goto LABEL_114;
  }
  v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v34 = (*v193)[7];
  v35 = v192;
  string = 0;
  v36 = WindowsCreateStringReference(L"SandboxPath", 0xBu, &hstringHeader, &string);
  if ( v36 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v36, v37, v38);
    __debugbreak();
  }
  ActivationFactory = v34(v33, (GUID *)string, v35);
  if ( ActivationFactory < 0 )
  {
    v7 = 2054;
    goto LABEL_114;
  }
  v39 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v39 + 16LL))((__int64 *)v39);
  }
  if ( SysStringLen(*((BSTR *)a2 + 3)) )
  {
    v40 = v194;
    v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
    v42 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v42 + 16LL))((__int64 *)v42);
    }
    v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)a2 + 24);
    ActivationFactory = v41(v40, *(_QWORD *)(v43 + 24), (__int64 *)&v192);
    if ( ActivationFactory < 0 )
    {
      v7 = 2060;
      goto LABEL_114;
    }
    v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
    v45 = (*v193)[7];
    v46 = v192;
    string = 0;
    v47 = WindowsCreateStringReference(L"MergedSandboxPath", 0x11u, &hstringHeader, &string);
    if ( v47 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v47, v48, v49);
      __debugbreak();
    }
    ActivationFactory = v45(v44, (GUID *)string, v46);
    if ( ActivationFactory < 0 )
    {
      v7 = 2062;
      goto LABEL_114;
    }
    v50 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v50 + 16LL))((__int64 *)v50);
    }
  }
  if ( a4 )
  {
    v51 = v194;
    v52 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
    v53 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v53 + 16LL))((__int64 *)v53);
    }
    v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v190);
    ActivationFactory = v52(v51, *(_QWORD *)(v54 + 24), (__int64 *)&v192);
    if ( ActivationFactory < 0 )
    {
      v7 = 2068;
      goto LABEL_114;
    }
    v55 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
    v56 = (*v193)[7];
    v57 = v192;
    string = 0;
    v58 = WindowsCreateStringReference(L"UpdateStackCabFileName", 0x16u, &hstringHeader, &string);
    if ( v58 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
      __debugbreak();
    }
    ActivationFactory = v56(v55, (GUID *)string, v57);
    if ( ActivationFactory < 0 )
    {
      v7 = 2070;
      goto LABEL_114;
    }
    v61 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v61 + 16LL))((__int64 *)v61);
    }
  }
  v62 = v194;
  v63 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
  v64 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v64 + 16LL))((__int64 *)v64);
  }
  v65 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v191);
  ActivationFactory = v63(v62, *(_QWORD *)(v65 + 24), (__int64 *)&v192);
  if ( ActivationFactory < 0 )
  {
    v7 = 2074;
    goto LABEL_114;
  }
  v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v67 = (*v193)[7];
  v68 = v192;
  string = 0;
  v69 = WindowsCreateStringReference(L"UpdateAgentName", 0xFu, &hstringHeader, &string);
  if ( v69 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v69, v70, v71);
    __debugbreak();
  }
  ActivationFactory = v67(v66, (GUID *)string, v68);
  if ( ActivationFactory < 0 )
  {
    v7 = 2075;
    goto LABEL_114;
  }
  v72 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v72 + 16LL))((__int64 *)v72);
    v72 = (__int64)v192;
  }
  if ( *((_QWORD *)a2 + 32) )
  {
    v73 = v194;
    v74 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
    if ( v72 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v72 + 16LL))((__int64 *)v72);
    }
    v75 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)a2 + 256);
    ActivationFactory = v74(v73, *(_QWORD *)(v75 + 24), (__int64 *)&v192);
    if ( ActivationFactory < 0 )
    {
      v7 = 2081;
      goto LABEL_114;
    }
    v76 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
    v77 = (*v193)[7];
    v78 = v192;
    string = 0;
    v79 = WindowsCreateStringReference(L"SessionData", 0xBu, &hstringHeader, &string);
    if ( v79 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v79, v80, v81);
      __debugbreak();
    }
    ActivationFactory = v77(v76, (GUID *)string, v78);
    if ( ActivationFactory < 0 )
    {
      v7 = 2082;
      goto LABEL_114;
    }
    v82 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v82 + 16LL))((__int64 *)v82);
    }
  }
  if ( !StringFromGUID2((const GUID *const)(*((_QWORD *)a2 + 7) + 4LL), sz, 39) )
  {
    ActivationFactory = -2147024809;
    v7 = 2087;
    goto LABEL_114;
  }
  v84 = v194;
  v85 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v194 + 80LL);
  v86 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v86 + 16LL))((__int64 *)v86);
  }
  v87 = -1;
  v88 = -1;
  do
    ++v88;
  while ( sz[v88] );
  if ( v88 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v88, v83);
    __debugbreak();
  }
  if ( (int)v88 + 1 < (unsigned int)v88 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v88, v83);
    __debugbreak();
  }
  v89 = WindowsCreateStringReference(sz, v88, &hstringHeader, &string);
  if ( v89 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v89, v90, v91);
    __debugbreak();
  }
  ActivationFactory = v85(v84, string, (__int64 *)&v192);
  if ( ActivationFactory < 0 )
  {
    v7 = 2088;
    goto LABEL_114;
  }
  v92 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v93 = (*v193)[7];
  v94 = v192;
  string = 0;
  v95 = WindowsCreateStringReference(L"UpdateId", 8u, &hstringHeader, &string);
  if ( v95 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v95, v96, v97);
    __debugbreak();
  }
  ActivationFactory = v93(v92, (GUID *)string, v94);
  if ( ActivationFactory < 0 )
  {
    v7 = 2089;
    goto LABEL_114;
  }
  v99 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v99 + 16LL))((__int64 *)v99);
  }
  if ( *(_QWORD *)a2 && **(_WORD **)a2 )
  {
    v100 = v194;
    v101 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
    v102 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v102 + 16LL))((__int64 *)v102);
    }
    v103 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, a2);
    ActivationFactory = v101(v100, *(_QWORD *)(v103 + 24), (__int64 *)&v192);
    if ( ActivationFactory < 0 )
    {
      v7 = 2094;
      goto LABEL_114;
    }
    v104 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
    v105 = (*v193)[7];
    v106 = v192;
    string = 0;
    v107 = WindowsCreateStringReference(L"ServerId", 8u, &hstringHeader, &string);
    if ( v107 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v107, v108, v109);
      __debugbreak();
    }
    ActivationFactory = v105(v104, (GUID *)string, v106);
    if ( ActivationFactory < 0 )
    {
      v7 = 2095;
      goto LABEL_114;
    }
    v110 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v110 + 16LL))((__int64 *)v110);
    }
  }
  if ( *((_QWORD *)a2 + 13) )
  {
    v111 = v194;
    v112 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v194 + 80LL);
    v113 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v113 + 16LL))((__int64 *)v113);
    }
    v114 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)a2 + 104);
    ActivationFactory = v112(v111, *(_QWORD *)(v114 + 24), (__int64 *)&v192);
    if ( ActivationFactory < 0 )
    {
      v7 = 2101;
      goto LABEL_114;
    }
    v115 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
    v116 = (*v193)[7];
    v117 = v192;
    string = 0;
    v118 = WindowsCreateStringReference(L"FlightId", 8u, &hstringHeader, &string);
    if ( v118 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v118, v119, v120);
      __debugbreak();
    }
    ActivationFactory = v116(v115, (GUID *)string, v117);
    if ( ActivationFactory < 0 )
    {
      v7 = 2102;
      goto LABEL_114;
    }
    v122 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v122 + 16LL))((__int64 *)v122);
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
                    v125);
      ActivationFactory = LastError;
      if ( LastError < 0 )
      {
        v7 = 2111;
LABEL_178:
        v121 = (unsigned int)LastError;
        goto LABEL_179;
      }
    }
    v127 = v194;
    v128 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v194 + 80LL);
    v129 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v129 + 16LL))((__int64 *)v129);
    }
    do
      ++v87;
    while ( WideCharStr[v87] );
    if ( v87 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v123, v124);
      __debugbreak();
    }
    if ( (int)v87 + 1 < (unsigned int)v87 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v123, v124);
      __debugbreak();
    }
    v130 = WindowsCreateStringReference(WideCharStr, v87, &hstringHeader, &string);
    if ( v130 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v130, v131, v132);
      __debugbreak();
    }
    LastError = v128(v127, string, (__int64 *)&v192);
    ActivationFactory = LastError;
    if ( LastError < 0 )
    {
      v7 = 2112;
      goto LABEL_178;
    }
    v133 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
    v134 = (*v193)[7];
    v135 = v192;
    string = 0;
    v136 = WindowsCreateStringReference(L"CV", 2u, &hstringHeader, &string);
    if ( v136 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v136, v137, v138);
      __debugbreak();
    }
    LastError = v134(v133, (GUID *)string, v135);
    ActivationFactory = LastError;
    if ( LastError < 0 )
    {
      v7 = 2113;
      goto LABEL_178;
    }
    v139 = (__int64)v192;
    if ( v192 )
    {
      v192 = 0;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v139 + 16LL))((__int64 *)v139);
    }
  }
  v189 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)a2 + 7) + 360LL);
  v140 = v194;
  v141 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v194 + 72LL);
  v142 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v142 + 16LL))((__int64 *)v142);
  }
  LastError = v141(v140, v98, (__int64 *)&v192);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2118;
    goto LABEL_178;
  }
  v143 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v144 = (*v193)[7];
  v145 = v192;
  string = 0;
  v146 = WindowsCreateStringReference(L"ProductMajorVer", 0xFu, &hstringHeader, &string);
  if ( v146 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v146, v147, v148);
    __debugbreak();
  }
  LastError = v144(v143, (GUID *)string, v145);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2119;
    goto LABEL_178;
  }
  v149 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v149 + 16LL))((__int64 *)v149);
    v149 = (__int64)v192;
  }
  v150 = v194;
  v151 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v194 + 72LL);
  if ( v149 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v149 + 16LL))((__int64 *)v149);
  }
  LastError = v151(v150, v149, (__int64 *)&v192);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2122;
    goto LABEL_178;
  }
  v152 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v153 = (*v193)[7];
  v154 = v192;
  string = 0;
  v155 = WindowsCreateStringReference(L"ProductMinorVer", 0xFu, &hstringHeader, &string);
  if ( v155 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v155, v156, v157);
    __debugbreak();
  }
  LastError = v153(v152, (GUID *)string, v154);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2123;
    goto LABEL_178;
  }
  v158 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v158 + 16LL))((__int64 *)v158);
    v158 = (__int64)v192;
  }
  v159 = v194;
  v160 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v194 + 72LL);
  if ( v158 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v158 + 16LL))((__int64 *)v158);
  }
  LastError = v160(v159, v158, (__int64 *)&v192);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2126;
    goto LABEL_178;
  }
  v161 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v162 = (*v193)[7];
  v163 = v192;
  string = 0;
  v164 = WindowsCreateStringReference(L"ProductBuildMajorVer", 0x14u, &hstringHeader, &string);
  if ( v164 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v164, v165, v166);
    JUMPOUT(0x180041BA4LL);
  }
  LastError = v162(v161, (GUID *)string, v163);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2128;
    goto LABEL_178;
  }
  v167 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v167 + 16LL))((__int64 *)v167);
    v167 = (__int64)v192;
  }
  v168 = v194;
  v169 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v194 + 72LL);
  if ( v167 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v167 + 16LL))((__int64 *)v167);
  }
  LastError = v169(v168, v167, (__int64 *)&v192);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2131;
    goto LABEL_178;
  }
  v170 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v171 = (*v193)[7];
  v172 = v192;
  string = 0;
  v173 = WindowsCreateStringReference(L"ProductBuildMinorVer", 0x14u, &hstringHeader, &string);
  if ( v173 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v173, v174, v175);
    __debugbreak();
  }
  LastError = v171(v170, (GUID *)string, v172);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2133;
    goto LABEL_178;
  }
  v176 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v176 + 16LL))((__int64 *)v176);
    v176 = (__int64)v192;
  }
  v177 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  v178 = **v193;
  if ( v176 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v176 + 16LL))((__int64 *)v176);
  }
  LastError = v178(v177, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, (__int64 *)&v192);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2137;
    goto LABEL_178;
  }
  v179 = (__int64)v192;
  v180 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*v192 + 56);
  WindowsDeleteString(v195[0]);
  v195[0] = 0;
  LastError = v180(v179, v195);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2138;
    goto LABEL_178;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v195[0], 0);
  LastError = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer, a5);
  ActivationFactory = LastError;
  if ( LastError < 0 )
  {
    v7 = 2140;
    goto LABEL_178;
  }
  ActivationFactory = 0;
LABEL_181:
  WindowsDeleteString(v195[0]);
  v195[0] = 0;
  v182 = (__int64)v192;
  if ( v192 )
  {
    v192 = 0;
    (*(void (__fastcall **)(__int64 *))(*(_QWORD *)v182 + 16LL))((__int64 *)v182);
  }
  v183 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v193;
  if ( v193 )
  {
    v193 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v183)[2])(v183);
  }
  v184 = v194;
  if ( v194 )
  {
    v194 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v184 + 16LL))(v184);
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
