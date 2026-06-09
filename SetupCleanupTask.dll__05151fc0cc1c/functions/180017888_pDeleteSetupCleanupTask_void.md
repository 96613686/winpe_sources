# pDeleteSetupCleanupTask(void)

- ea: `0x180017888`
- end: `0x180018214`
- name: `?pDeleteSetupCleanupTask@@YAJXZ`
- size: `2444`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800174c4`

## callees

- `0x180003d00`
- `0x180003d3c`
- `0x18000638c`
- `0x180017354`
- `0x180017430`
- `0x180017888`
- `0x18002d4d8`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800178d1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800178d1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017954`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017a2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017a2e`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180017990`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180017990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018084`
- `OLEAUT32!__imp_VariantInit` at `0x180017aad`
- `OLEAUT32!__imp_VariantInit` at `0x180017ac3`
- `OLEAUT32!__imp_VariantInit` at `0x180017ad9`
- `OLEAUT32!__imp_VariantInit` at `0x180017aed`
- `OLEAUT32!__imp_VariantInit` at `0x180017aad`
- `OLEAUT32!__imp_VariantInit` at `0x180017ac3`
- `OLEAUT32!__imp_VariantInit` at `0x180017ad9`
- `OLEAUT32!__imp_VariantInit` at `0x180017aed`
- `OLEAUT32!__imp_VariantClear` at `0x180017b4b`
- `OLEAUT32!__imp_VariantClear` at `0x180017b5d`
- `OLEAUT32!__imp_VariantClear` at `0x180017b6f`
- `OLEAUT32!__imp_VariantClear` at `0x180017b81`
- `OLEAUT32!__imp_VariantClear` at `0x180017b4b`
- `OLEAUT32!__imp_VariantClear` at `0x180017b5d`
- `OLEAUT32!__imp_VariantClear` at `0x180017b6f`
- `OLEAUT32!__imp_VariantClear` at `0x180017b81`
- `WDSCORE!CurrentIP` at `0x1800178fe`
- `WDSCORE!CurrentIP` at `0x1800179b4`
- `WDSCORE!CurrentIP` at `0x180017a42`
- `WDSCORE!CurrentIP` at `0x180017b9b`
- `WDSCORE!CurrentIP` at `0x180017c55`
- `WDSCORE!CurrentIP` at `0x180017d1d`
- `WDSCORE!CurrentIP` at `0x180017df4`
- `WDSCORE!CurrentIP` at `0x180017eb0`
- `WDSCORE!CurrentIP` at `0x180017f83`
- `WDSCORE!CurrentIP` at `0x18001808c`
- `WDSCORE!CurrentIP` at `0x1800178fe`
- `WDSCORE!CurrentIP` at `0x1800179b4`
- `WDSCORE!CurrentIP` at `0x180017a42`
- `WDSCORE!CurrentIP` at `0x180017b9b`
- `WDSCORE!CurrentIP` at `0x180017c55`
- `WDSCORE!CurrentIP` at `0x180017d1d`
- `WDSCORE!CurrentIP` at `0x180017df4`
- `WDSCORE!CurrentIP` at `0x180017eb0`
- `WDSCORE!CurrentIP` at `0x180017f83`
- `WDSCORE!CurrentIP` at `0x18001808c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001794b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017a01`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017a8f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017be8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017ca2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017d6a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017e41`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017efd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017fd0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800180d9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001794b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017a01`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017a8f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017be8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017ca2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017d6a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017e41`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017efd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017fd0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800180d9`

## string_xrefs

- `0x1800178e0`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskmanager.cpp`
- `0x1800179c0`: `CoInitializeSecurity hr = 0x%x`
- `0x180017a4e`: `CoCreateInstance failed for CLSID_TaskScheduler. hr = 0x%x`
- `0x180017ba7`: `ITaskService::Connect failed. hr = 0x%x`
- `0x180017c61`: `ITaskService::GetFolder failed. hr = 0x%x`
- `0x180017cd5`: `\Microsoft\Windows\Setup\SetupCleanupTask`
- `0x1800178d9`: `pDeleteSetupCleanupTask`
- `0x180017d29`: `ITaskFolder::DeleteTask failed. hr = 0x%x`
- `0x180017e00`: `ITaskFolder::GetFolder failed. hr = 0x%x`
- `0x180017ebc`: `ITaskFolder::GetTasks failed. hr = 0x%x`
- `0x180017f8f`: `IRegisteredTaskCollection::get_Count failed. hr = 0x%x`
- `0x180018098`: `IRegisteredTaskCollection::DeleteFolder failed. hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 pDeleteSetupCleanupTask(void)
{
  __int64 v0; // rdx
  HRESULT v1; // esi
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  HRESULT v5; // esi
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  HRESULT v9; // esi
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v15; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v17; // xmm8
  IRecordInfo *v18; // xmm9_8
  __int128 v19; // xmm6
  IRecordInfo *v20; // xmm7_8
  HRESULT v21; // eax
  struct IErrorInfo *v22; // rdx
  HRESULT v23; // eax
  struct IErrorInfo *v24; // rdx
  HRESULT v25; // eax
  struct IErrorInfo *v26; // rdx
  HRESULT v27; // eax
  struct IErrorInfo *v28; // rdx
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  LPVOID v32; // rbx
  __int64 (__fastcall *v33)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v34; // rax
  __int64 v35; // rdx
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v41; // rax
  __int64 v42; // rdx
  DWORD v43; // edi
  __int64 v44; // rbx
  struct tagLOG_PARTIAL_MSG *v45; // rax
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v48; // rax
  __int64 v49; // rdx
  DWORD v50; // edi
  __int64 v51; // rbx
  struct tagLOG_PARTIAL_MSG *v52; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  __int64 v59; // rbx
  __int64 (__fastcall *v60)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v61; // rax
  __int64 v62; // rdx
  DWORD v63; // edi
  __int64 v64; // rbx
  struct tagLOG_PARTIAL_MSG *v65; // rax
  __int64 v67; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v69[16]; // [rsp+80h] [rbp-88h] BYREF
  VARIANTARG v70; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v71; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v72; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v74; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v75; // [rsp+108h] [rbp+0h]
  __int128 v76; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v77; // [rsp+128h] [rbp+20h]
  __int128 v78; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v79; // [rsp+148h] [rbp+40h]
  VARIANTARG v80; // [rsp+158h] [rbp+50h] BYREF
  int v81; // [rsp+228h] [rbp+120h] BYREF
  LPVOID ppv; // [rsp+230h] [rbp+128h] BYREF
  __int64 v83; // [rsp+238h] [rbp+130h] BYREF
  __int64 v84; // [rsp+240h] [rbp+138h] BYREF

  v1 = CoInitializeEx(0, 0);
  if ( v1 < 0 )
  {
    LastError = GetLastError();
    v3 = CurrentIP();
    v4 = ConstructPartialMsgW(0x4000000, "CoInitializeEx hr = 0x%x", v1);
    WdsSetupLogMessageW(
      v4,
      0,
      L"D",
      0,
      466,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v3,
      LastError,
      0,
      0);
    LOBYTE(v0) = 0;
  }
  else
  {
    LOBYTE(v0) = 1;
  }
  MakeGuardIF<void (*)(void)>(v69, v0, CoUninitialize);
  v5 = CoInitializeSecurity(0, -1, 0, 0, 4u, 3u, 0, 0, 0);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147417831 )
  {
    v6 = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(0x4000000, "CoInitializeSecurity hr = 0x%x", v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      490,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v7,
      v6,
      0,
      0);
  }
  ppv = 0;
  v9 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v9 < 0 )
  {
    v10 = GetLastError();
    v11 = CurrentIP();
    v12 = ConstructPartialMsgW(0x2000000, "CoCreateInstance failed for CLSID_TaskScheduler. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      498,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v11,
      v10,
      0,
      0);
LABEL_65:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl0<void (*)(void)>>(v69);
    return (unsigned int)v9;
  }
  v13 = ppv;
  v14 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v15 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v72);
  v17 = *(_OWORD *)&v72.vt;
  v18 = v72.pRecInfo;
  VariantInit(&v71);
  v19 = *(_OWORD *)&v71.vt;
  v20 = v71.pRecInfo;
  VariantInit(&v70);
  v74 = v15;
  v75 = pRecInfo;
  v76 = v17;
  v77 = v18;
  v78 = v19;
  v79 = v20;
  v80 = v70;
  v9 = v14(v13, &v80, &v78, &v76, &v74);
  v21 = VariantClear(&v70);
  if ( v21 < 0 )
    _com_issue_error(v21, v22);
  v23 = VariantClear(&v71);
  if ( v23 < 0 )
    _com_issue_error(v23, v24);
  v25 = VariantClear(&v72);
  if ( v25 < 0 )
    _com_issue_error(v25, v26);
  v27 = VariantClear(&pvarg);
  if ( v27 < 0 )
    _com_issue_error(v27, v28);
  if ( v9 < 0 )
  {
    v29 = GetLastError();
    v30 = CurrentIP();
    v31 = ConstructPartialMsgW(0x2000000, "ITaskService::Connect failed. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v31,
      0,
      L"D",
      0,
      506,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v30,
      v29,
      0,
      0);
    goto LABEL_65;
  }
  v83 = 0;
  v32 = ppv;
  v33 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL);
  v34 = _bstr_t::_bstr_t((_bstr_t *)&v67, L"\\");
  if ( *(_QWORD *)v34 )
    v35 = **(_QWORD **)v34;
  else
    v35 = 0;
  v9 = v33(v32, v35, &v83);
  _bstr_t::~_bstr_t((_bstr_t *)&v67);
  if ( v9 < 0 )
  {
    v36 = GetLastError();
    v37 = CurrentIP();
    v38 = ConstructPartialMsgW(0x2000000, "ITaskService::GetFolder failed. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v38,
      0,
      L"D",
      0,
      515,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v37,
      v36,
      0,
      0);
    if ( v83 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    goto LABEL_65;
  }
  v39 = v83;
  v40 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v83 + 120LL);
  v41 = _bstr_t::_bstr_t((_bstr_t *)&v67, L"\\Microsoft\\Windows\\Setup\\SetupCleanupTask");
  if ( *(_QWORD *)v41 )
    v42 = **(_QWORD **)v41;
  else
    v42 = 0;
  v9 = v40(v39, v42, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&v67);
  if ( v9 < 0 )
  {
    v43 = GetLastError();
    v44 = CurrentIP();
    v45 = ConstructPartialMsgW(0x2000000, "ITaskFolder::DeleteTask failed. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v45,
      0,
      L"D",
      0,
      523,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v44,
      v43,
      0,
      0);
    if ( v83 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    goto LABEL_65;
  }
  v84 = 0;
  v46 = v83;
  v47 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v83 + 72LL);
  v48 = _bstr_t::_bstr_t((_bstr_t *)&v67, L"\\Microsoft\\Windows\\Setup");
  if ( *(_QWORD *)v48 )
    v49 = **(_QWORD **)v48;
  else
    v49 = 0;
  v9 = v47(v46, v49, &v84);
  _bstr_t::~_bstr_t((_bstr_t *)&v67);
  if ( v9 < 0 )
  {
    v50 = GetLastError();
    v51 = CurrentIP();
    v52 = ConstructPartialMsgW(0x2000000, "ITaskFolder::GetFolder failed. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v52,
      0,
      L"D",
      0,
      532,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v51,
      v50,
      0,
      0);
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    if ( v83 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    goto LABEL_65;
  }
  v68 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v84 + 112LL))(v84, 0, &v68);
  if ( v9 < 0 )
  {
    v53 = GetLastError();
    v54 = CurrentIP();
    v55 = ConstructPartialMsgW(0x2000000, "ITaskFolder::GetTasks failed. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v55,
      0,
      L"D",
      0,
      541,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v54,
      v53,
      0,
      0);
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    if ( v83 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    goto LABEL_65;
  }
  v81 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v68 + 56LL))(v68, &v81);
  if ( v9 < 0 )
  {
    v56 = GetLastError();
    v57 = CurrentIP();
    v58 = ConstructPartialMsgW(0x2000000, "IRegisteredTaskCollection::get_Count failed. hr = 0x%x", v9);
    WdsSetupLogMessageW(
      v58,
      0,
      L"D",
      0,
      550,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"pDeleteSetupCleanupTask",
      v57,
      v56,
      0,
      0);
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    if ( v83 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    goto LABEL_65;
  }
  if ( !v81 )
  {
    v59 = v83;
    v60 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v83 + 96LL);
    v61 = _bstr_t::_bstr_t((_bstr_t *)&v67, L"\\Microsoft\\Windows\\Setup");
    v62 = *(_QWORD *)v61 ? **(_QWORD **)v61 : 0LL;
    v9 = v60(v59, v62, 0);
    _bstr_t::~_bstr_t((_bstr_t *)&v67);
    if ( v9 < 0 )
    {
      v63 = GetLastError();
      v64 = CurrentIP();
      v65 = ConstructPartialMsgW(0x2000000, "IRegisteredTaskCollection::DeleteFolder failed. hr = 0x%x", v9);
      WdsSetupLogMessageW(
        v65,
        0,
        L"D",
        0,
        560,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
        L"pDeleteSetupCleanupTask",
        v64,
        v63,
        0,
        0);
      if ( v68 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      if ( v84 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
      if ( v83 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      goto LABEL_65;
    }
  }
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  if ( v84 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl0<void (*)(void)>>(v69);
  return 0;
}

```

## disassembly

```asm
0x180017888  mov     rax, rsp
0x18001788b  push    rbp
0x18001788c  push    rbx
0x18001788d  push    rsi
0x18001788e  push    rdi
0x18001788f  push    r12
0x180017891  push    r13
0x180017893  push    r14
0x180017895  push    r15
0x180017897  lea     rbp, [rax-118h]
0x18001789e  sub     rsp, 1D8h
0x1800178a5  movaps  xmmword ptr [rax-58h], xmm6
0x1800178a9  movaps  xmmword ptr [rax-68h], xmm7
0x1800178ad  movaps  xmmword ptr [rax-78h], xmm8
0x1800178b2  movaps  xmmword ptr [rax-88h], xmm9
0x1800178ba  movaps  xmmword ptr [rax-98h], xmm10
0x1800178c2  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800178ca  xor     r14d, r14d
0x1800178cd  xor     edx, edx; dwCoInit
0x1800178cf  xor     ecx, ecx; pvReserved
0x1800178d1  call    cs:__imp_CoInitializeEx
0x1800178d7  mov     esi, eax
0x1800178d9  lea     r12, aPdeletesetupcl; "pDeleteSetupCleanupTask"
0x1800178e0  lea     r13, aBaseNtsetupSet_0; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800178e7  lea     r15, aD_0; "D"
0x1800178ee  test    eax, eax
0x1800178f0  js      short loc_1800178F6
0x1800178f2  mov     dl, 1
0x1800178f4  jmp     short loc_180017954
0x1800178f6  call    cs:__imp_GetLastError
0x1800178fc  mov     edi, eax
0x1800178fe  call    cs:__imp_CurrentIP
0x180017904  mov     rbx, rax
0x180017907  mov     r8d, esi
0x18001790a  lea     rdx, aCoinitializeex; "CoInitializeEx hr = 0x%x"
0x180017911  mov     ecx, 4000000h; unsigned int
0x180017916  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001791b  mov     [rsp+210h+var_1C0], r14d
0x180017920  mov     qword ptr [rsp+210h+var_1C8], r14
0x180017925  mov     dword ptr [rsp+210h+pReserved3], edi
0x180017929  mov     qword ptr [rsp+210h+dwCapabilities], rbx
0x18001792e  mov     [rsp+210h+pAuthList], r12
0x180017933  mov     qword ptr [rsp+210h+dwImpLevel], r13
0x180017938  mov     [rsp+210h+dwAuthnLevel], 1D2h
0x180017940  xor     r9d, r9d
0x180017943  mov     r8, r15
0x180017946  xor     edx, edx
0x180017948  mov     rcx, rax
0x18001794b  call    cs:__imp_WdsSetupLogMessageW
0x180017951  mov     dl, r14b
0x180017954  mov     r8, cs:__imp_CoUninitialize
0x18001795b  lea     rcx, [rsp+210h+var_198]
0x180017960  call    ??$MakeGuardIF@P6AXXZ@@YA?AV?$ScopeGuardImpl0@P6AXXZ@@_NP6AXXZ@Z; MakeGuardIF<void (*)(void)>(bool,void (*)(void))
0x180017965  nop
0x180017966  mov     [rsp+210h+pReserved3], r14; pReserved3
0x18001796b  mov     [rsp+210h+dwCapabilities], r14d; dwCapabilities
0x180017970  mov     [rsp+210h+pAuthList], r14; pAuthList
0x180017975  mov     [rsp+210h+dwImpLevel], 3; dwImpLevel
0x18001797d  mov     [rsp+210h+dwAuthnLevel], 4; dwAuthnLevel
0x180017985  xor     r9d, r9d; pReserved1
0x180017988  xor     r8d, r8d; asAuthSvc
0x18001798b  or      edx, 0FFFFFFFFh; cAuthSvc
0x18001798e  xor     ecx, ecx; pSecDesc
0x180017990  call    cs:__imp_CoInitializeSecurity
0x180017996  mov     esi, eax
0x180017998  mov     eax, 80000000h
0x18001799d  lea     edx, [rsi+rax]
0x1800179a0  test    eax, edx
0x1800179a2  jnz     short loc_180017A07
0x1800179a4  cmp     esi, 80010119h
0x1800179aa  jz      short loc_180017A07
0x1800179ac  call    cs:__imp_GetLastError
0x1800179b2  mov     edi, eax
0x1800179b4  call    cs:__imp_CurrentIP
0x1800179ba  mov     rbx, rax
0x1800179bd  mov     r8d, esi
0x1800179c0  lea     rdx, aCoinitializese; "CoInitializeSecurity hr = 0x%x"
0x1800179c7  mov     ecx, 4000000h; unsigned int
0x1800179cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800179d1  mov     [rsp+210h+var_1C0], r14d
0x1800179d6  mov     qword ptr [rsp+210h+var_1C8], r14
0x1800179db  mov     dword ptr [rsp+210h+pReserved3], edi
0x1800179df  mov     qword ptr [rsp+210h+dwCapabilities], rbx
0x1800179e4  mov     [rsp+210h+pAuthList], r12
0x1800179e9  mov     qword ptr [rsp+210h+dwImpLevel], r13
0x1800179ee  mov     [rsp+210h+dwAuthnLevel], 1EAh
0x1800179f6  xor     r9d, r9d
0x1800179f9  mov     r8, r15
0x1800179fc  xor     edx, edx
0x1800179fe  mov     rcx, rax
0x180017a01  call    cs:__imp_WdsSetupLogMessageW
0x180017a07  mov     [rbp+110h+ppv], r14
0x180017a0e  lea     rax, [rbp+110h+ppv]
0x180017a15  mov     qword ptr [rsp+210h+dwAuthnLevel], rax; ppv
0x180017a1a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180017a21  xor     edx, edx; pUnkOuter
0x180017a23  lea     r8d, [rdx+1]; dwClsContext
0x180017a27  lea     rcx, CLSID_TaskScheduler; rclsid
0x180017a2e  call    cs:__imp_CoCreateInstance
0x180017a34  mov     esi, eax
0x180017a36  test    eax, eax
0x180017a38  jns     short loc_180017A9B
0x180017a3a  call    cs:__imp_GetLastError
0x180017a40  mov     edi, eax
0x180017a42  call    cs:__imp_CurrentIP
0x180017a48  mov     rbx, rax
0x180017a4b  mov     r8d, esi
0x180017a4e  lea     rdx, aCocreateinstan; "CoCreateInstance failed for CLSID_TaskS"...
0x180017a55  mov     ecx, 2000000h; unsigned int
0x180017a5a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017a5f  mov     [rsp+210h+var_1C0], r14d
0x180017a64  mov     qword ptr [rsp+210h+var_1C8], r14
0x180017a69  mov     dword ptr [rsp+210h+pReserved3], edi
0x180017a6d  mov     qword ptr [rsp+210h+dwCapabilities], rbx
0x180017a72  mov     [rsp+210h+pAuthList], r12
0x180017a77  mov     qword ptr [rsp+210h+dwImpLevel], r13
0x180017a7c  mov     [rsp+210h+dwAuthnLevel], 1F2h
0x180017a84  xor     r9d, r9d
0x180017a87  mov     r8, r15
0x180017a8a  xor     edx, edx
0x180017a8c  mov     rcx, rax
0x180017a8f  call    cs:__imp_WdsSetupLogMessageW
0x180017a95  nop
0x180017a96  jmp     loc_180018129
0x180017a9b  mov     rdi, [rbp+110h+ppv]
0x180017aa2  mov     rax, [rdi]
0x180017aa5  mov     rbx, [rax+50h]
0x180017aa9  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180017aad  call    cs:__imp_VariantInit
0x180017ab3  nop
0x180017ab4  movups  xmm10, xmmword ptr [rbp+110h+pvarg]
0x180017ab9  movsd   xmm11, qword ptr [rbp+110h+pvarg+10h]
0x180017abf  lea     rcx, [rbp+110h+var_158]; pvarg
0x180017ac3  call    cs:__imp_VariantInit
0x180017ac9  nop
0x180017aca  movups  xmm8, xmmword ptr [rbp+110h+var_158]
0x180017acf  movsd   xmm9, qword ptr [rbp+110h+var_158+10h]
0x180017ad5  lea     rcx, [rbp+110h+var_170]; pvarg
0x180017ad9  call    cs:__imp_VariantInit
0x180017adf  nop
0x180017ae0  movups  xmm6, xmmword ptr [rbp+110h+var_170]
0x180017ae4  movsd   xmm7, qword ptr [rbp+110h+var_170+10h]
0x180017ae9  lea     rcx, [rbp+110h+var_188]; pvarg
0x180017aed  call    cs:__imp_VariantInit
0x180017af3  nop
0x180017af4  movups  xmm0, xmmword ptr [rbp+110h+var_188]
0x180017af8  movsd   xmm1, qword ptr [rbp+110h+var_188+10h]
0x180017afd  movaps  [rbp+110h+var_120], xmm10
0x180017b02  movsd   [rbp+110h+var_110], xmm11
0x180017b08  movaps  [rbp+110h+var_100], xmm8
0x180017b0d  movsd   [rbp+110h+var_F0], xmm9
0x180017b13  movaps  [rbp+110h+var_E0], xmm6
0x180017b17  movsd   [rbp+110h+var_D0], xmm7
0x180017b1c  movaps  [rbp+110h+var_C0], xmm0
0x180017b20  movsd   [rbp+110h+var_B0], xmm1
0x180017b25  lea     rax, [rbp+110h+var_120]
0x180017b29  mov     qword ptr [rsp+210h+dwAuthnLevel], rax
0x180017b2e  lea     r9, [rbp+110h+var_100]
0x180017b32  lea     r8, [rbp+110h+var_E0]
0x180017b36  lea     rdx, [rbp+110h+var_C0]
0x180017b3a  mov     rcx, rdi
0x180017b3d  mov     rax, rbx
0x180017b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b45  mov     esi, eax
0x180017b47  lea     rcx, [rbp+110h+var_188]; pvarg
0x180017b4b  call    cs:__imp_VariantClear
0x180017b51  test    eax, eax
0x180017b53  js      loc_1800181FC
0x180017b59  lea     rcx, [rbp+110h+var_170]; pvarg
0x180017b5d  call    cs:__imp_VariantClear
0x180017b63  test    eax, eax
0x180017b65  js      loc_180018204
0x180017b6b  lea     rcx, [rbp+110h+var_158]; pvarg
0x180017b6f  call    cs:__imp_VariantClear
0x180017b75  test    eax, eax
0x180017b77  js      loc_18001820C
0x180017b7d  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180017b81  call    cs:__imp_VariantClear
0x180017b87  test    eax, eax
0x180017b89  js      loc_1800181F4
0x180017b8f  test    esi, esi
0x180017b91  jns     short loc_180017BF4
0x180017b93  call    cs:__imp_GetLastError
0x180017b99  mov     edi, eax
0x180017b9b  call    cs:__imp_CurrentIP
0x180017ba1  mov     rbx, rax
0x180017ba4  mov     r8d, esi
0x180017ba7  lea     rdx, aItaskserviceCo; "ITaskService::Connect failed. hr = 0x%x"
0x180017bae  mov     ecx, 2000000h; unsigned int
0x180017bb3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017bb8  mov     [rsp+210h+var_1C0], r14d
0x180017bbd  mov     qword ptr [rsp+210h+var_1C8], r14
0x180017bc2  mov     dword ptr [rsp+210h+pReserved3], edi
0x180017bc6  mov     qword ptr [rsp+210h+dwCapabilities], rbx
0x180017bcb  mov     [rsp+210h+pAuthList], r12
0x180017bd0  mov     qword ptr [rsp+210h+dwImpLevel], r13
0x180017bd5  mov     [rsp+210h+dwAuthnLevel], 1FAh
0x180017bdd  xor     r9d, r9d
0x180017be0  mov     r8, r15
0x180017be3  xor     edx, edx
0x180017be5  mov     rcx, rax
0x180017be8  call    cs:__imp_WdsSetupLogMessageW
0x180017bee  nop
0x180017bef  jmp     loc_180018129
0x180017bf4  mov     [rbp+110h+arg_10], r14
0x180017bfb  mov     rbx, [rbp+110h+ppv]
0x180017c02  mov     rax, [rbx]
0x180017c05  mov     rdi, [rax+38h]
0x180017c09  lea     rdx, pszSrc; "\\"
0x180017c10  lea     rcx, [rsp+210h+var_1B0]; this
0x180017c15  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180017c1a  nop
0x180017c1b  mov     rdx, [rax]
0x180017c1e  test    rdx, rdx
0x180017c21  jz      short loc_180017C28
0x180017c23  mov     rdx, [rdx]
0x180017c26  jmp     short loc_180017C2B
0x180017c28  mov     rdx, r14
0x180017c2b  lea     r8, [rbp+110h+arg_10]
0x180017c32  mov     rcx, rbx
0x180017c35  mov     rax, rdi
0x180017c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c3d  mov     esi, eax
0x180017c3f  lea     rcx, [rsp+210h+var_1B0]; this
0x180017c44  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017c49  test    esi, esi
0x180017c4b  jns     short loc_180017CC7
0x180017c4d  call    cs:__imp_GetLastError
0x180017c53  mov     edi, eax
0x180017c55  call    cs:__imp_CurrentIP
0x180017c5b  mov     rbx, rax
0x180017c5e  mov     r8d, esi
0x180017c61  lea     rdx, aItaskserviceGe; "ITaskService::GetFolder failed. hr = 0x"...
0x180017c68  mov     ecx, 2000000h; unsigned int
0x180017c6d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017c72  mov     [rsp+210h+var_1C0], r14d
0x180017c77  mov     qword ptr [rsp+210h+var_1C8], r14
0x180017c7c  mov     dword ptr [rsp+210h+pReserved3], edi
0x180017c80  mov     qword ptr [rsp+210h+dwCapabilities], rbx
0x180017c85  mov     [rsp+210h+pAuthList], r12
0x180017c8a  mov     qword ptr [rsp+210h+dwImpLevel], r13
0x180017c8f  mov     [rsp+210h+dwAuthnLevel], 203h
0x180017c97  xor     r9d, r9d
0x180017c9a  mov     r8, r15
0x180017c9d  xor     edx, edx
0x180017c9f  mov     rcx, rax
0x180017ca2  call    cs:__imp_WdsSetupLogMessageW
0x180017ca8  nop
0x180017ca9  mov     rcx, [rbp+110h+arg_10]
0x180017cb0  test    rcx, rcx
0x180017cb3  jz      short loc_180017CC2
0x180017cb5  mov     rax, [rcx]
0x180017cb8  mov     rax, [rax+10h]
0x180017cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cc1  nop
0x180017cc2  jmp     loc_180018129
0x180017cc7  mov     rbx, [rbp+110h+arg_10]
0x180017cce  mov     rax, [rbx]
0x180017cd1  mov     rdi, [rax+78h]
0x180017cd5  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Setup\\SetupClean"...
0x180017cdc  lea     rcx, [rsp+210h+var_1B0]; this
0x180017ce1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180017ce6  nop
0x180017ce7  mov     rdx, [rax]
0x180017cea  test    rdx, rdx
0x180017ced  jz      short loc_180017CF4
0x180017cef  mov     rdx, [rdx]
0x180017cf2  jmp     short loc_180017CF7
0x180017cf4  mov     rdx, r14
0x180017cf7  xor     r8d, r8d
0x180017cfa  mov     rcx, rbx
0x180017cfd  mov     rax, rdi
0x180017d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d05  mov     esi, eax
0x180017d07  lea     rcx, [rsp+210h+var_1B0]; this
0x180017d0c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017d11  test    esi, esi
0x180017d13  jns     short loc_180017D8F
0x180017d15  call    cs:__imp_GetLastError
0x180017d1b  mov     edi, eax
0x180017d1d  call    cs:__imp_CurrentIP
0x180017d23  mov     rbx, rax
0x180017d26  mov     r8d, esi
0x180017d29  lea     rdx, aItaskfolderDel; "ITaskFolder::DeleteTask failed. hr = 0x"...
0x180017d30  mov     ecx, 2000000h; unsigned int
0x180017d35  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017d3a  mov     [rsp+210h+var_1C0], r14d
0x180017d3f  mov     qword ptr [rsp+210h+var_1C8], r14
0x180017d44  mov     dword ptr [rsp+210h+pReserved3], edi
0x180017d48  mov     qword ptr [rsp+210h+dwCapabilities], rbx
0x180017d4d  mov     [rsp+210h+pAuthList], r12
0x180017d52  mov     qword ptr [rsp+210h+dwImpLevel], r13
0x180017d57  mov     [rsp+210h+dwAuthnLevel], 20Bh
0x180017d5f  xor     r9d, r9d
0x180017d62  mov     r8, r15
0x180017d65  xor     edx, edx
0x180017d67  mov     rcx, rax
0x180017d6a  call    cs:__imp_WdsSetupLogMessageW
0x180017d70  nop
0x180017d71  mov     rcx, [rbp+110h+arg_10]
  ... truncated ...
```
