# DeleteSchedules(ushort const *)

- ea: `0x14002e208`
- end: `0x14002f148`
- name: `?DeleteSchedules@@YAJPEBG@Z`
- size: `3904`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002c854`

## callees

- `0x14000715c`
- `0x1400095b4`
- `0x14000f614`
- `0x14000fe60`
- `0x1400176f0`
- `0x14001ea48`
- `0x14001ef20`
- `0x14001ef94`
- `0x14002e208`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14002efba`
- `OLEAUT32!__imp_SysFreeString` at `0x14002efba`
- `OLEAUT32!__imp_VariantInit` at `0x14002e42e`
- `OLEAUT32!__imp_VariantInit` at `0x14002e443`
- `OLEAUT32!__imp_VariantInit` at `0x14002e458`
- `OLEAUT32!__imp_VariantInit` at `0x14002e46b`
- `OLEAUT32!__imp_VariantInit` at `0x14002ef2a`
- `OLEAUT32!__imp_VariantInit` at `0x14002e42e`
- `OLEAUT32!__imp_VariantInit` at `0x14002e443`
- `OLEAUT32!__imp_VariantInit` at `0x14002e458`
- `OLEAUT32!__imp_VariantInit` at `0x14002e46b`
- `OLEAUT32!__imp_VariantInit` at `0x14002ef2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002e3ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002e3ce`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002eec1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002f0ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002eec1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002f0ed`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002e395`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002e395`

## string_xrefs

- `0x14002e299`: `First Login Schedule created by enrollment client`
- `0x14002e262`: `Login Schedule created by enrollment client`
- `0x14002e34b`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x14002e733`: `Schedule created by enrollment client to reattest client certificate`
- `0x14002e2f7`: `Wsc Startup event listener created by enrollment client`
- `0x14002e32f`: `Schedule created by dm client to unenroll Mmpc from dual enrollment`
- `0x14002e321`: `Schedule created by dm client for dual enrollment to Mmpc`
- `0x14002e2af`: `Unenroll alert created by enrollment client`
- `0x14002e2c5`: `Passport for Work alert created by enrollment client`
- `0x14002e2db`: `OS Edition Upgrade event listener created by enrollment client`
- `0x14002e2e9`: `Win10 S Mode event listener created by enrollment client`
- `0x14002e248`: `Schedule #1 created by enrollment client`
- `0x14002e257`: `Schedule #3 created by enrollment client`
- `0x14002e28e`: `Maintenance Schedule created by enrollment client`
- `0x14002e26d`: `Schedule created by enrollment client for renewal of certificate warning`
- `0x14002e2ba`: `Migration alert created by enrollment client`
- `0x14002e305`: `Schedule #4 created by enrollment client`
- `0x14002e313`: `User Maintenance Schedule created by enrollment client`
- `0x14002ebd8`: `Schedule created by dm client to refresh settings`
- `0x14002e2a4`: `Retry Schedule created for incomplete session`
- `0x14002e33d`: `Watchdog schedule created by Declared Configuration to configure device`
- `0x14002e375`: `PushUpdate`
- `0x14002e383`: `Schedule created by enrollment client after the certificate has expired`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DeleteSchedules(const unsigned __int16 *a1)
{
  HRESULT v2; // eax
  int v3; // ebx
  HRESULT v4; // eax
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  LPVOID v13; // rbx
  __int64 (__fastcall *v14)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rbx
  void (__fastcall *v19)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  unsigned __int64 i; // rdi
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *); // r14
  _bstr_t *v29; // rax
  __int64 v30; // rdx
  int v31; // ebx
  __int64 v32; // rbx
  void (__fastcall *v33)(__int64, __int64, _QWORD); // r14
  _bstr_t *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rbx
  void (__fastcall *v37)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  unsigned int v41; // r8d
  int v42; // eax
  __int64 v43; // rbx
  __int64 (__fastcall *v44)(__int64, __int64, BSTR *); // rdi
  _bstr_t *v45; // rax
  __int64 v46; // rdx
  BSTR v47; // rbx
  void (__fastcall *v48)(BSTR, __int64, _QWORD); // rdi
  _bstr_t *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rbx
  void (__fastcall *v52)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rcx
  unsigned int v56; // r8d
  int v57; // eax
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v60; // rax
  __int64 v61; // rdx
  int v62; // eax
  LONG j; // ebx
  int v64; // eax
  __int64 v65; // rcx
  __int64 v66; // rbx
  void (__fastcall *v67)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v68; // rax
  __int64 v69; // rdx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  int ppvb; // [rsp+28h] [rbp-E0h]
  int ppvc; // [rsp+28h] [rbp-E0h]
  LPVOID v75; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v76; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v77; // [rsp+58h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v79; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v80; // [rsp+70h] [rbp-98h] BYREF
  __int64 v81; // [rsp+78h] [rbp-90h] BYREF
  __int64 v82; // [rsp+80h] [rbp-88h] BYREF
  VARIANTARG v83; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v84; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v85; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v86; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int16 *v88[28]; // [rsp+118h] [rbp+10h]
  int v89[4]; // [rsp+1F8h] [rbp+F0h] BYREF
  IRecordInfo *v90; // [rsp+208h] [rbp+100h]
  __int128 v91; // [rsp+218h] [rbp+110h] BYREF
  IRecordInfo *v92; // [rsp+228h] [rbp+120h]
  __int128 v93; // [rsp+238h] [rbp+130h] BYREF
  IRecordInfo *v94; // [rsp+248h] [rbp+140h]
  wil::details::in1diag3 *retaddr; // [rsp+2F0h] [rbp+1E8h]
  __int64 v96; // [rsp+300h] [rbp+1F8h] BYREF
  __int64 v97; // [rsp+308h] [rbp+200h] BYREF
  __int64 v98; // [rsp+310h] [rbp+208h] BYREF

  v88[0] = L"Schedule #1 created by enrollment client";
  v88[1] = L"Schedule #1 created by enrollment client";
  v88[2] = L"Schedule #3 created by enrollment client";
  v88[3] = L"Login Schedule created by enrollment client";
  v88[4] = L"Schedule created by enrollment client for renewal of certificate warning";
  v88[5] = L"Schedule to run OMADMClient by client";
  v88[6] = L"Schedule to run OMADMClient by server";
  v88[7] = L"Maintenance Schedule created by enrollment client";
  v88[8] = L"First Login Schedule created by enrollment client";
  v88[9] = L"Retry Schedule created for incomplete session";
  v88[10] = L"Unenroll alert created by enrollment client";
  v88[11] = L"Migration alert created by enrollment client";
  v88[12] = L"Passport for Work alert created by enrollment client";
  v88[13] = L"Provisioning initiated session";
  v88[14] = L"OS Edition Upgrade event listener created by enrollment client";
  v88[15] = L"Win10 S Mode event listener created by enrollment client";
  v88[16] = L"Wsc Startup event listener created by enrollment client";
  v88[17] = L"Schedule #4 created by enrollment client";
  v88[18] = L"User Maintenance Schedule created by enrollment client";
  v88[19] = L"Schedule created by dm client for dual enrollment to Mmpc";
  v88[20] = L"Schedule created by dm client to unenroll Mmpc from dual enrollment";
  v88[21] = L"Watchdog schedule created by Declared Configuration to configure device";
  v88[22] = L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device";
  v88[23] = L"PushLaunch";
  v88[24] = L"PushRenewal";
  v88[25] = L"PushUpdate";
  v88[26] = L"Schedule created by enrollment client after the certificate has expired";
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    return (unsigned int)v3;
  }
  v75 = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v75);
  v3 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v4,
      ppva);
    wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v75);
LABEL_140:
    CoUninitialize();
    return (unsigned int)v3;
  }
  v97 = 0;
  v98 = 0;
  v77 = 0;
  v76 = 0;
  v5 = v75;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v75 + 80LL);
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v86);
  v9 = *(_OWORD *)&v86.vt;
  v10 = v86.pRecInfo;
  VariantInit(&v85);
  v11 = *(_OWORD *)&v85.vt;
  v12 = v85.pRecInfo;
  VariantInit(&v83);
  *(_OWORD *)v89 = v7;
  v90 = pRecInfo;
  v91 = v9;
  v92 = v10;
  v93 = v11;
  v94 = v12;
  v84 = v83;
  v3 = v6(v5, &v84, &v93, &v91);
  _variant_t::~_variant_t(&v83);
  _variant_t::~_variant_t(&v85);
  _variant_t::~_variant_t(&v86);
  _variant_t::~_variant_t(&pvarg);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18AF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v3,
      (int)v89);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
LABEL_139:
    wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v75);
    goto LABEL_140;
  }
  v13 = v75;
  v14 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v75 + 56LL);
  v15 = _bstr_t::_bstr_t((_bstr_t *)&v96, L"\\");
  if ( *(_QWORD *)v15 )
    v16 = **(_QWORD **)v15;
  else
    v16 = 0;
  v3 = v14(v13, v16, &v97);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v3,
      (int)v89);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64 *))(*(_QWORD *)v97 + 72LL))(
          v97,
          L"\\Microsoft\\Windows\\EnterpriseMgmt",
          &v98);
  v3 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v17,
      (int)v89);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  v18 = v98;
  v19 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v98 + 120LL);
  v20 = _bstr_t::_bstr_t((_bstr_t *)&v96, L"Schedule created by enrollment client to reattest client certificate");
  if ( *(_QWORD *)v20 )
    v21 = **(_QWORD **)v20;
  else
    v21 = 0;
  v19(v18, v21, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  v80 = 0;
  v22 = v98;
  v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v98 + 72LL);
  v24 = _bstr_t::_bstr_t((_bstr_t *)&v96, a1);
  if ( *(_QWORD *)v24 )
    v25 = **(_QWORD **)v24;
  else
    v25 = 0;
  v3 = v23(v22, v25, &v80);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18BB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v3,
      (int)v89);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  for ( i = 0; i < 0x1B; ++i )
  {
    v96 = 0;
    v27 = v80;
    v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v80 + 104LL);
    v29 = _bstr_t::_bstr_t((_bstr_t *)&v79, v88[i]);
    if ( *(_QWORD *)v29 )
      v30 = **(_QWORD **)v29;
    else
      v30 = 0;
    v31 = v28(v27, v30, &v96);
    _bstr_t::~_bstr_t((_bstr_t *)&v79);
    if ( v31 >= 0 )
    {
      v32 = v80;
      v33 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v80 + 120LL);
      v34 = _bstr_t::_bstr_t((_bstr_t *)&v82, v88[i]);
      if ( *(_QWORD *)v34 )
        v35 = **(_QWORD **)v34;
      else
        v35 = 0;
      v33(v32, v35, 0);
      _bstr_t::~_bstr_t((_bstr_t *)&v82);
    }
    if ( v96 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  }
  v36 = v98;
  v37 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v98 + 96LL);
  v38 = _bstr_t::_bstr_t((_bstr_t *)&v96, a1);
  if ( *(_QWORD *)v38 )
    v39 = **(_QWORD **)v38;
  else
    v39 = 0;
  v37(v36, v39, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  (*(void (__fastcall **)(__int64, const OLECHAR *, _QWORD))(*(_QWORD *)v97 + 96LL))(
    v97,
    L"\\Microsoft\\Windows\\EnterpriseMgmt",
    0);
  v41 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
  if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
  {
    v79 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                       v40,
                       &v79);
    v41 = v79;
  }
  LODWORD(v96) = 0;
  WORD2(v96) = 3;
  wil::details::ReportUsageToService(&qword_14007E368, 43467477, (v41 >> 10) & 1, (v41 >> 11) & 1, &v96, 1, 3);
  v42 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v97 + 72LL))(
          v97,
          L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
          &v77);
  v3 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v42,
      ppvb);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  bstrString = 0;
  v43 = v77;
  v44 = *(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v77 + 72LL);
  v45 = _bstr_t::_bstr_t((_bstr_t *)&v96, a1);
  if ( *(_QWORD *)v45 )
    v46 = **(_QWORD **)v45;
  else
    v46 = 0;
  v3 = v44(v43, v46, &bstrString);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v3,
      ppvb);
    if ( bstrString )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  v47 = bstrString;
  v48 = *(void (__fastcall **)(BSTR, __int64, _QWORD))(*(_QWORD *)bstrString + 120LL);
  v49 = _bstr_t::_bstr_t((_bstr_t *)&v96, L"Schedule created by dm client to refresh settings");
  if ( *(_QWORD *)v49 )
    v50 = **(_QWORD **)v49;
  else
    v50 = 0;
  v48(v47, v50, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  if ( bstrString )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
  v51 = v77;
  v52 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v77 + 96LL);
  v53 = _bstr_t::_bstr_t((_bstr_t *)&v96, a1);
  if ( *(_QWORD *)v53 )
    v54 = **(_QWORD **)v53;
  else
    v54 = 0;
  v52(v51, v54, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&v96);
  (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v97 + 96LL))(
    v97,
    L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
    0);
  v56 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
  if ( (*(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor & 4) == 0 )
  {
    v79 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
                       v55,
                       &v79);
    v56 = v79;
  }
  LODWORD(v96) = 0;
  WORD2(v96) = 3;
  wil::details::ReportUsageToService(&qword_14007E450, 57312060, (v56 >> 10) & 1, (v56 >> 11) & 1, &v96, 1, 3);
  v57 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v97 + 72LL))(
          v97,
          L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry",
          &v76);
  v3 = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18DE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v57,
      ppvc);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  v82 = 0;
  v58 = v76;
  v59 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v76 + 72LL);
  v60 = _bstr_t::_bstr_t((_bstr_t *)&v81, a1);
  if ( *(_QWORD *)v60 )
    v61 = **(_QWORD **)v60;
  else
    v61 = 0;
  v3 = v59(v58, v61, &v82);
  _bstr_t::~_bstr_t((_bstr_t *)&v81);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v3,
      ppvc);
    if ( v82 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    if ( v98 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
    if ( v97 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_139;
  }
  v79 = 0;
  v62 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v82 + 112LL))(v82, 1, &v79);
  LODWORD(v96) = 0;
  if ( v62 >= 0 && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 56LL))(v79, &v96) >= 0 )
  {
    memset(&v83, 0, sizeof(v83));
    VariantInit(&v83);
    v83.vt = 3;
    for ( j = 1; j <= (int)v96; ++j )
    {
      v83.lVal = j;
      v81 = 0;
      v84 = v83;
      v64 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64 *))(*(_QWORD *)v79 + 64LL))(v79, &v84, &v81);
      v65 = v81;
      if ( v64 >= 0 )
      {
        bstrString = 0;
        if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v81 + 56LL))(v81, &bstrString) >= 0 )
          (*(void (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v82 + 120LL))(v82, bstrString, 0);
        SysFreeString(bstrString);
        v65 = v81;
      }
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
  }
  v66 = v76;
  v67 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v76 + 96LL);
  v68 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, a1);
  if ( *(_QWORD *)v68 )
    v69 = **(_QWORD **)v68;
  else
    v69 = 0;
  v67(v66, v69, 0);
  _bstr_t::~_bstr_t((_bstr_t *)&bstrString);
  (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v97 + 96LL))(
    v97,
    L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry",
    0);
  if ( v79 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  if ( v82 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  if ( v76 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  if ( v98 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v75);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x14002e208  mov     rax, rsp
0x14002e20b  push    rbp
0x14002e20c  push    rbx
0x14002e20d  push    rsi
0x14002e20e  push    rdi
0x14002e20f  push    r12
0x14002e211  push    r14
0x14002e213  push    r15
0x14002e215  lea     rbp, [rax-1E8h]
0x14002e21c  sub     rsp, 2B0h
0x14002e223  movaps  xmmword ptr [rax-48h], xmm6
0x14002e227  movaps  xmmword ptr [rax-58h], xmm7
0x14002e22b  movaps  xmmword ptr [rax-68h], xmm8
0x14002e230  movaps  xmmword ptr [rax-78h], xmm9
0x14002e235  movaps  xmmword ptr [rax-88h], xmm10
0x14002e23d  movaps  xmmword ptr [rax-98h], xmm11
0x14002e245  mov     rsi, rcx
0x14002e248  lea     rax, aSchedule1Creat; "Schedule #1 created by enrollment clien"...
0x14002e24f  mov     [rbp+1E0h+var_1D0], rax
0x14002e253  mov     [rbp+1E0h+var_1C8], rax
0x14002e257  lea     rax, aSchedule3Creat; "Schedule #3 created by enrollment clien"...
0x14002e25e  mov     [rbp+1E0h+var_1C0], rax
0x14002e262  lea     rax, aLoginScheduleC_0; "Login Schedule created by enrollment cl"...
0x14002e269  mov     [rbp+1E0h+var_1B8], rax
0x14002e26d  lea     rax, aScheduleCreate_0; "Schedule created by enrollment client f"...
0x14002e274  mov     [rbp+1E0h+var_1B0], rax
0x14002e278  lea     rax, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x14002e27f  mov     [rbp+1E0h+var_1A8], rax
0x14002e283  lea     rax, aScheduleToRunO_0; "Schedule to run OMADMClient by server"
0x14002e28a  mov     [rbp+1E0h+var_1A0], rax
0x14002e28e  lea     rax, aMaintenanceSch; "Maintenance Schedule created by enrollm"...
0x14002e295  mov     [rbp+1E0h+var_198], rax
0x14002e299  lea     rax, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x14002e2a0  mov     [rbp+1E0h+var_190], rax
0x14002e2a4  lea     rax, aRetryScheduleC; "Retry Schedule created for incomplete s"...
0x14002e2ab  mov     [rbp+1E0h+var_188], rax
0x14002e2af  lea     rax, aUnenrollAlertC; "Unenroll alert created by enrollment cl"...
0x14002e2b6  mov     [rbp+1E0h+var_180], rax
0x14002e2ba  lea     rax, aMigrationAlert; "Migration alert created by enrollment c"...
0x14002e2c1  mov     [rbp+1E0h+var_178], rax
0x14002e2c5  lea     rax, aPassportForWor; "Passport for Work alert created by enro"...
0x14002e2cc  mov     [rbp+1E0h+var_170], rax
0x14002e2d0  lea     rax, aProvisioningIn; "Provisioning initiated session"
0x14002e2d7  mov     [rbp+1E0h+var_168], rax
0x14002e2db  lea     rax, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x14002e2e2  mov     [rbp+1E0h+var_160], rax
0x14002e2e9  lea     rax, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x14002e2f0  mov     [rbp+1E0h+var_158], rax
0x14002e2f7  lea     rax, aWscStartupEven; "Wsc Startup event listener created by e"...
0x14002e2fe  mov     [rbp+1E0h+var_150], rax
0x14002e305  lea     rax, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x14002e30c  mov     [rbp+1E0h+var_148], rax
0x14002e313  lea     rax, aUserMaintenanc; "User Maintenance Schedule created by en"...
0x14002e31a  mov     [rbp+1E0h+var_140], rax
0x14002e321  lea     rax, aScheduleCreate_1; "Schedule created by dm client for dual "...
0x14002e328  mov     [rbp+1E0h+var_138], rax
0x14002e32f  lea     rax, aScheduleCreate_2; "Schedule created by dm client to unenro"...
0x14002e336  mov     [rbp+1E0h+var_130], rax
0x14002e33d  lea     rax, aWatchdogSchedu; "Watchdog schedule created by Declared C"...
0x14002e344  mov     [rbp+1E0h+var_128], rax
0x14002e34b  lea     rax, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x14002e352  mov     [rbp+1E0h+var_120], rax
0x14002e359  lea     rax, aPushlaunch_0; "PushLaunch"
0x14002e360  mov     [rbp+1E0h+var_118], rax
0x14002e367  lea     rax, aPushrenewal; "PushRenewal"
0x14002e36e  mov     [rbp+1E0h+var_110], rax
0x14002e375  lea     rax, aPushupdate; "PushUpdate"
0x14002e37c  mov     [rbp+1E0h+var_108], rax
0x14002e383  lea     rax, aScheduleCreate_4; "Schedule created by enrollment client a"...
0x14002e38a  mov     [rbp+1E0h+var_100], rax
0x14002e391  xor     edx, edx; dwCoInit
0x14002e393  xor     ecx, ecx; pvReserved
0x14002e395  call    cs:__imp_CoInitializeEx
0x14002e39b  mov     ebx, eax
0x14002e39d  xor     r15d, r15d
0x14002e3a0  test    eax, eax
0x14002e3a2  js      loc_14002F0F7
0x14002e3a8  mov     [rsp+2E0h+var_2A0], r15
0x14002e3ad  lea     rax, [rsp+2E0h+var_2A0]
0x14002e3b2  mov     [rsp+2E0h+ppv], rax; int
0x14002e3b7  lea     r9, IID_ITaskService; riid
0x14002e3be  lea     r12d, [r15+1]
0x14002e3c2  mov     r8d, r12d; dwClsContext
0x14002e3c5  xor     edx, edx; pUnkOuter
0x14002e3c7  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002e3ce  call    cs:__imp_CoCreateInstance
0x14002e3d4  mov     ebx, eax
0x14002e3d6  test    eax, eax
0x14002e3d8  jns     short loc_14002E406
0x14002e3da  mov     rcx, [rbp+1E8h]; this
0x14002e3e1  mov     r9d, eax; char *
0x14002e3e4  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002e3eb  mov     edx, 18A7h; void *
0x14002e3f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e3f5  nop
0x14002e3f6  lea     rcx, [rsp+2E0h+var_2A0]
0x14002e3fb  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002e400  nop
0x14002e401  jmp     loc_14002EEC1
0x14002e406  mov     [rbp+1E0h+arg_10], r15
0x14002e40d  mov     [rbp+1E0h+arg_18], r15
0x14002e414  mov     [rsp+2E0h+var_290], r15
0x14002e419  mov     [rsp+2E0h+var_298], r15
0x14002e41e  mov     rdi, [rsp+2E0h+var_2A0]
0x14002e423  mov     rax, [rdi]
0x14002e426  mov     rbx, [rax+50h]
0x14002e42a  lea     rcx, [rbp+1E0h+pvarg]; pvarg
0x14002e42e  call    cs:__imp_VariantInit
0x14002e434  movups  xmm10, xmmword ptr [rbp+1E0h+pvarg]
0x14002e439  movsd   xmm11, qword ptr [rbp+1E0h+pvarg+10h]
0x14002e43f  lea     rcx, [rbp+1E0h+var_208]; pvarg
0x14002e443  call    cs:__imp_VariantInit
0x14002e449  movups  xmm8, xmmword ptr [rbp+1E0h+var_208]
0x14002e44e  movsd   xmm9, qword ptr [rbp+1E0h+var_208+10h]
0x14002e454  lea     rcx, [rbp+1E0h+var_220]; pvarg
0x14002e458  call    cs:__imp_VariantInit
0x14002e45e  movups  xmm6, xmmword ptr [rbp+1E0h+var_220]
0x14002e462  movsd   xmm7, qword ptr [rbp+1E0h+var_220+10h]
0x14002e467  lea     rcx, [rbp+1E0h+var_260]; pvarg
0x14002e46b  call    cs:__imp_VariantInit
0x14002e471  movups  xmm0, xmmword ptr [rbp+1E0h+var_260]
0x14002e475  movsd   xmm1, qword ptr [rbp+1E0h+var_260+10h]
0x14002e47a  movaps  xmmword ptr [rbp+1E0h+var_F0], xmm10
0x14002e482  movsd   [rbp+1E0h+var_E0], xmm11
0x14002e48b  movaps  [rbp+1E0h+var_D0], xmm8
0x14002e493  movsd   [rbp+1E0h+var_C0], xmm9
0x14002e49c  movaps  [rbp+1E0h+var_B0], xmm6
0x14002e4a3  movsd   [rbp+1E0h+var_A0], xmm7
0x14002e4ab  movaps  [rbp+1E0h+var_240], xmm0
0x14002e4af  movsd   [rbp+1E0h+var_230], xmm1
0x14002e4b4  lea     rax, [rbp+1E0h+var_F0]
0x14002e4bb  mov     [rsp+2E0h+ppv], rax; int
0x14002e4c0  lea     r9, [rbp+1E0h+var_D0]
0x14002e4c7  lea     r8, [rbp+1E0h+var_B0]
0x14002e4ce  lea     rdx, [rbp+1E0h+var_240]
0x14002e4d2  mov     rcx, rdi
0x14002e4d5  mov     rax, rbx
0x14002e4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e4dd  mov     ebx, eax
0x14002e4df  lea     rcx, [rbp+1E0h+var_260]; this
0x14002e4e3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002e4e8  lea     rcx, [rbp+1E0h+var_220]; this
0x14002e4ec  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002e4f1  lea     rcx, [rbp+1E0h+var_208]; this
0x14002e4f5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002e4fa  lea     rcx, [rbp+1E0h+pvarg]; this
0x14002e4fe  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14002e503  test    ebx, ebx
0x14002e505  jns     loc_14002E593
0x14002e50b  mov     rcx, [rbp+1E8h]; this
0x14002e512  mov     r9d, ebx; char *
0x14002e515  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002e51c  mov     edx, 18AFh; void *
0x14002e521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e526  mov     rcx, [rsp+2E0h+var_298]
0x14002e52b  test    rcx, rcx
0x14002e52e  jz      short loc_14002E53C
0x14002e530  mov     rax, [rcx]
0x14002e533  mov     rax, [rax+10h]
0x14002e537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e53c  mov     rcx, [rsp+2E0h+var_290]
0x14002e541  test    rcx, rcx
0x14002e544  jz      short loc_14002E552
0x14002e546  mov     rax, [rcx]
0x14002e549  mov     rax, [rax+10h]
0x14002e54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e552  mov     rcx, [rbp+1E0h+arg_18]
0x14002e559  test    rcx, rcx
0x14002e55c  jz      short loc_14002E56A
0x14002e55e  mov     rax, [rcx]
0x14002e561  mov     rax, [rax+10h]
0x14002e565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e56a  mov     rcx, [rbp+1E0h+arg_10]
0x14002e571  test    rcx, rcx
0x14002e574  jz      short loc_14002E583
0x14002e576  mov     rax, [rcx]
0x14002e579  mov     rax, [rax+10h]
0x14002e57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e582  nop
0x14002e583  lea     rcx, [rsp+2E0h+var_2A0]
0x14002e588  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002e58d  nop
0x14002e58e  jmp     loc_14002EEC1
0x14002e593  mov     rbx, [rsp+2E0h+var_2A0]
0x14002e598  mov     rax, [rbx]
0x14002e59b  mov     rdi, [rax+38h]
0x14002e59f  lea     rdx, asc_140061150; "\\"
0x14002e5a6  lea     rcx, [rbp+1E0h+arg_8]; this
0x14002e5ad  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14002e5b2  mov     rdx, [rax]
0x14002e5b5  test    rdx, rdx
0x14002e5b8  jz      short loc_14002E5BF
0x14002e5ba  mov     rdx, [rdx]
0x14002e5bd  jmp     short loc_14002E5C2
0x14002e5bf  mov     rdx, r15
0x14002e5c2  lea     r8, [rbp+1E0h+arg_10]
0x14002e5c9  mov     rcx, rbx
0x14002e5cc  mov     rax, rdi
0x14002e5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e5d4  mov     ebx, eax
0x14002e5d6  lea     rcx, [rbp+1E0h+arg_8]; this
0x14002e5dd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002e5e2  test    ebx, ebx
0x14002e5e4  jns     loc_14002E672
0x14002e5ea  mov     rcx, [rbp+1E8h]; this
0x14002e5f1  mov     r9d, ebx; char *
0x14002e5f4  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002e5fb  mov     edx, 18B2h; void *
0x14002e600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e605  mov     rcx, [rsp+2E0h+var_298]
0x14002e60a  test    rcx, rcx
0x14002e60d  jz      short loc_14002E61B
0x14002e60f  mov     rax, [rcx]
0x14002e612  mov     rax, [rax+10h]
0x14002e616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e61b  mov     rcx, [rsp+2E0h+var_290]
0x14002e620  test    rcx, rcx
0x14002e623  jz      short loc_14002E631
0x14002e625  mov     rax, [rcx]
0x14002e628  mov     rax, [rax+10h]
0x14002e62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e631  mov     rcx, [rbp+1E0h+arg_18]
0x14002e638  test    rcx, rcx
0x14002e63b  jz      short loc_14002E649
0x14002e63d  mov     rax, [rcx]
0x14002e640  mov     rax, [rax+10h]
0x14002e644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e649  mov     rcx, [rbp+1E0h+arg_10]
0x14002e650  test    rcx, rcx
0x14002e653  jz      short loc_14002E662
0x14002e655  mov     rax, [rcx]
0x14002e658  mov     rax, [rax+10h]
0x14002e65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e661  nop
0x14002e662  lea     rcx, [rsp+2E0h+var_2A0]
0x14002e667  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002e66c  nop
0x14002e66d  jmp     loc_14002EEC1
0x14002e672  mov     rcx, [rbp+1E0h+arg_10]
0x14002e679  mov     rax, [rcx]
0x14002e67c  lea     r8, [rbp+1E0h+arg_18]
0x14002e683  lea     rdx, aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14002e68a  mov     rax, [rax+48h]
0x14002e68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e693  mov     ebx, eax
0x14002e695  test    eax, eax
0x14002e697  jns     loc_14002E725
0x14002e69d  mov     rcx, [rbp+1E8h]; this
0x14002e6a4  mov     r9d, eax; char *
0x14002e6a7  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002e6ae  mov     edx, 18B6h; void *
0x14002e6b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e6b8  mov     rcx, [rsp+2E0h+var_298]
0x14002e6bd  test    rcx, rcx
0x14002e6c0  jz      short loc_14002E6CE
0x14002e6c2  mov     rdx, [rcx]
0x14002e6c5  mov     rax, [rdx+10h]
0x14002e6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e6ce  mov     rcx, [rsp+2E0h+var_290]
0x14002e6d3  test    rcx, rcx
0x14002e6d6  jz      short loc_14002E6E4
0x14002e6d8  mov     rax, [rcx]
0x14002e6db  mov     rax, [rax+10h]
0x14002e6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e6e4  mov     rcx, [rbp+1E0h+arg_18]
0x14002e6eb  test    rcx, rcx
0x14002e6ee  jz      short loc_14002E6FC
0x14002e6f0  mov     rax, [rcx]
0x14002e6f3  mov     rax, [rax+10h]
0x14002e6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e6fc  mov     rcx, [rbp+1E0h+arg_10]
0x14002e703  test    rcx, rcx
0x14002e706  jz      short loc_14002E715
0x14002e708  mov     rax, [rcx]
0x14002e70b  mov     rax, [rax+10h]
0x14002e70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e714  nop
0x14002e715  lea     rcx, [rsp+2E0h+var_2A0]
0x14002e71a  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002e71f  nop
0x14002e720  jmp     loc_14002EEC1
0x14002e725  mov     rbx, [rbp+1E0h+arg_18]
0x14002e72c  mov     rax, [rbx]
0x14002e72f  mov     rdi, [rax+78h]
0x14002e733  lea     rdx, aScheduleCreate_6; "Schedule created by enrollment client t"...
0x14002e73a  lea     rcx, [rbp+1E0h+arg_8]; this
0x14002e741  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14002e746  mov     rcx, [rax]
0x14002e749  test    rcx, rcx
0x14002e74c  jz      short loc_14002E753
0x14002e74e  mov     rdx, [rcx]
0x14002e751  jmp     short loc_14002E756
0x14002e753  mov     rdx, r15
0x14002e756  xor     r8d, r8d
0x14002e759  mov     rcx, rbx
0x14002e75c  mov     rax, rdi
0x14002e75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e764  lea     rcx, [rbp+1E0h+arg_8]; this
0x14002e76b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002e770  mov     [rsp+2E0h+var_278], r15
  ... truncated ...
```
