# FirstSync::SchedulePollTask(ushort const *,ulong)

- ea: `0x1800a7754`
- end: `0x1800a8605`
- name: `?SchedulePollTask@FirstSync@@YAJPEBGK@Z`
- size: `3761`
- prototype: `__int64 __fastcall(FirstSync *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002430c`
- `0x1800a73f8`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x180009be4`
- `0x18000a5a4`
- `0x18000a5c4`
- `0x18000ac30`
- `0x1800179f8`
- `0x1800187d4`
- `0x18002335c`
- `0x180046204`
- `0x18006a99c`
- `0x1800a3a3c`
- `0x1800a3a8c`
- `0x1800a5900`
- `0x1800a63f0`
- `0x1800a67fc`
- `0x1800a7754`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a7822`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a7822`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a7863`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a7d5d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a839c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a85ae`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a7863`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a7d5d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a839c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a85ae`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a77e5`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a77e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a7e98`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a7e98`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a82d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a82d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800a7884`
- `OLEAUT32!__imp_VariantInit` at `0x1800a78a0`
- `OLEAUT32!__imp_VariantInit` at `0x1800a78bc`
- `OLEAUT32!__imp_VariantInit` at `0x1800a78d9`
- `OLEAUT32!__imp_VariantInit` at `0x1800a82af`
- `OLEAUT32!__imp_VariantInit` at `0x1800a83d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800a83eb`
- `OLEAUT32!__imp_VariantInit` at `0x1800a7884`
- `OLEAUT32!__imp_VariantInit` at `0x1800a78a0`
- `OLEAUT32!__imp_VariantInit` at `0x1800a78bc`
- `OLEAUT32!__imp_VariantInit` at `0x1800a78d9`
- `OLEAUT32!__imp_VariantInit` at `0x1800a82af`
- `OLEAUT32!__imp_VariantInit` at `0x1800a83d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800a83eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7958`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7969`
- `OLEAUT32!__imp_VariantClear` at `0x1800a797a`
- `OLEAUT32!__imp_VariantClear` at `0x1800a798b`
- `OLEAUT32!__imp_VariantClear` at `0x1800a830d`
- `OLEAUT32!__imp_VariantClear` at `0x1800a8479`
- `OLEAUT32!__imp_VariantClear` at `0x1800a848a`
- `OLEAUT32!__imp_VariantClear` at `0x1800a84c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800a851f`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7958`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7969`
- `OLEAUT32!__imp_VariantClear` at `0x1800a797a`
- `OLEAUT32!__imp_VariantClear` at `0x1800a798b`
- `OLEAUT32!__imp_VariantClear` at `0x1800a830d`
- `OLEAUT32!__imp_VariantClear` at `0x1800a8479`
- `OLEAUT32!__imp_VariantClear` at `0x1800a848a`
- `OLEAUT32!__imp_VariantClear` at `0x1800a84c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800a851f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800a7eb3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800a7eb3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800a7f0b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800a7f0b`

## string_xrefs

- `0x1800a7a03`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\DMAppsRes.dll,-26094)</Author>\n        <Description>$(@%systemRoot%\system32\DMAppsRes.dll,-26096)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Settings>\n        <MultipleInstancesPolicy>Queue</MultipleInstancesPolicy>\n        <Disallo`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall FirstSync::SchedulePollTask(FirstSync *this, const unsigned __int16 *a2)
{
  __int64 v2; // r12
  HRESULT LastError; // ebx
  int v6; // edi
  __int64 v7; // rdx
  LPVOID v8; // rsi
  __int64 (__fastcall *v9)(LPVOID, unsigned __int16 *, VARIANTARG *, VARIANTARG *); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  LPVOID v16; // rsi
  __int64 (__fastcall *v17)(LPVOID, _QWORD, __int64 *); // rbx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  __int64 v25; // rdx
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64, _QWORD); // rbx
  int v28; // eax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rsi
  int v31; // eax
  int EnrollmentSid; // eax
  OLECHAR *v33; // rbx
  __int64 v34; // rax
  bool v35; // si
  __int64 v36; // rdx
  int v37; // esi
  __int64 v38; // rdx
  __int64 bstr_nothrow; // rax
  bool v40; // si
  __int64 v41; // r14
  __int64 (__fastcall *v42)(__int64, __int64, _QWORD); // rsi
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  const char *v46; // r9
  __int64 v47; // rdx
  int v48; // eax
  __int64 v49; // r14
  __int64 (__fastcall *v50)(__int64, __int64 *); // rsi
  int v51; // eax
  __int64 v52; // r14
  __int64 (__fastcall *v53)(__int64, __int64, __int64 *); // rsi
  int v54; // eax
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rax
  bool v58; // si
  __int64 v59; // r8
  int TaskFolder; // eax
  __int64 v61; // rsi
  __int64 v62; // r14
  __int64 (__fastcall *v63)(__int64, __int64, __int64, __int64); // rbx
  __int128 v64; // xmm6
  IRecordInfo *v65; // xmm7_8
  int ppv; // [rsp+28h] [rbp-E0h]
  int *ppva; // [rsp+28h] [rbp-E0h]
  __int64 v68; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID v69; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v70; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v71; // [rsp+70h] [rbp-98h] BYREF
  __int64 v72; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR *psz; // [rsp+80h] [rbp-88h] BYREF
  __int64 v74; // [rsp+88h] [rbp-80h] BYREF
  __int64 (__fastcall ***v75)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-78h] BYREF
  __int64 v76; // [rsp+98h] [rbp-70h] BYREF
  struct _FILETIME FileTime; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v80; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v81; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v83; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v84; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v85; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+0h] BYREF
  int v87; // [rsp+120h] [rbp+18h]
  VARIANTARG v88; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG v89; // [rsp+148h] [rbp+40h] BYREF
  VARIANTARG v90; // [rsp+168h] [rbp+60h] BYREF
  int v91[4]; // [rsp+188h] [rbp+80h] BYREF
  IRecordInfo *v92; // [rsp+198h] [rbp+90h]
  VARIANTARG v93; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v94[8]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int128 v95; // [rsp+1D8h] [rbp+D0h]
  __int64 v96; // [rsp+1E8h] [rbp+E0h]
  unsigned __int16 v97[264]; // [rsp+1F8h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B0h] [rbp+3A8h]

  v2 = (unsigned int)a2;
  if ( !this )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x80070057LL,
      ppv);
    return (unsigned int)LastError;
  }
  v6 = RoInitialize(1);
  v87 = v6;
  v69 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  LastError = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v69);
  if ( LastError < 0 )
  {
    v7 = 669;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)LastError,
      (int)ppva);
    goto LABEL_7;
  }
  v8 = v69;
  v9 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v69 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v85);
  v12 = *(_OWORD *)&v85.vt;
  v13 = v85.pRecInfo;
  VariantInit(&v90);
  v14 = *(_OWORD *)&v90.vt;
  v15 = v90.pRecInfo;
  VariantInit(&v93);
  *(_OWORD *)v91 = v10;
  v92 = pRecInfo;
  *(_OWORD *)&v88.vt = v12;
  v88.pRecInfo = v13;
  *(_OWORD *)&v89.vt = v14;
  v89.pRecInfo = v15;
  *(_OWORD *)v94 = *(_OWORD *)&v93.vt;
  *(_QWORD *)&v95 = v93.pRecInfo;
  ppva = v91;
  LastError = v9(v8, v94, &v89, &v88);
  VariantClear(&v93);
  VariantClear(&v90);
  VariantClear(&v85);
  VariantClear(&pvarg);
  if ( LastError < 0 )
  {
    v7 = 670;
    goto LABEL_6;
  }
  v68 = 0;
  v16 = v69;
  v17 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v69 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v18 = v17(v16, 0, &v68);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v18,
      (int)v91);
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    if ( v6 >= 0 )
      RoUninitialize();
    return (unsigned int)LastError;
  }
  wil::make_bstr_nothrow(
    &v72,
    L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft-com:asm"
     ".v3\">\n"
     "    <RegistrationInfo>\n"
     "        <Author>$(@%systemRoot%\\system32\\DMAppsRes.dll,-26094)</Author>\n"
     "        <Description>$(@%systemRoot%\\system32\\DMAppsRes.dll,-26096)</Description>\n"
     "        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n"
     "    </RegistrationInfo>\n"
     "    <Settings>\n"
     "        <MultipleInstancesPolicy>Queue</MultipleInstancesPolicy>\n"
     "        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
     "        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
     "        <AllowHardTerminate>false</AllowHardTerminate>\n"
     "        <StartWhenAvailable>true</StartWhenAvailable>\n"
     "        <AllowStartOnDemand>true</AllowStartOnDemand>\n"
     "        <Hidden>true</Hidden>\n"
     "        <RunOnlyIfIdle>false</RunOnlyIfIdle>\n"
     "        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
     "        <ExecutionTimeLimit>PT1H</ExecutionTimeLimit>\n"
     "    </Settings>\n"
     "    <Actions>\n"
     "        <Exec>\n"
     "            <Command>%windir%\\system32\\deviceenroller.exe</Command>\n"
     "        </Exec>\n"
     "    </Actions>\n"
     "</Task>");
  if ( !v72 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x8007000ELL,
      (int)v91);
LABEL_96:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    if ( v6 >= 0 )
      RoUninitialize();
    return 2147942414LL;
  }
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 160LL))(v68);
  LastError = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v19,
      (int)v91);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
    goto LABEL_13;
  }
  v70 = 0;
  v20 = v68;
  v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  v22 = v21(v20, &v70);
  LastError = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v22,
      (int)v91);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    goto LABEL_18;
  }
  v71 = 0;
  v23 = v68;
  v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 120LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  LastError = v24(v23, &v71);
  if ( LastError < 0 )
  {
    v25 = 684;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)LastError,
      (int)v91);
LABEL_25:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    goto LABEL_21;
  }
  LastError = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 144LL))(v71, 1);
  if ( LastError < 0 )
  {
    v25 = 685;
    goto LABEL_24;
  }
  psz = 0;
  v75 = 0;
  v26 = v70;
  v27 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v70 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  v28 = v27(v26, 9, &v75);
  LastError = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v28,
      (int)v91);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
LABEL_31:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    goto LABEL_25;
  }
  v74 = 0;
  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
  v30 = **v75;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  v31 = v30(v29, &GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c, &v74);
  LastError = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v31,
      (int)v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    goto LABEL_30;
  }
  FileTime = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &psz,
    0);
  EnrollmentSid = anonymous_namespace_::GetEnrollmentSid(this, &psz);
  v33 = psz;
  if ( EnrollmentSid < 0 )
  {
    bstr_nothrow = wil::make_bstr_nothrow(&v81, L"S-1-5-32-545");
    v40 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                       &FileTime,
                       bstr_nothrow) == 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
    if ( v40 )
    {
      v36 = 706;
      goto LABEL_37;
    }
    v37 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v71 + 128LL))(v71, FileTime);
    if ( v37 < 0 )
    {
      v38 = 708;
      goto LABEL_41;
    }
  }
  else
  {
    v34 = wil::make_bstr_nothrow(&v81, psz);
    v35 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                       &FileTime,
                       v34) == 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
    if ( v35 )
    {
      v36 = 700;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)0x8007000ELL,
        (int)v91);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&FileTime);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
LABEL_38:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
LABEL_95:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      goto LABEL_96;
    }
    v37 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v74 + 184LL))(v74, FileTime);
    if ( v37 < 0 )
    {
      v38 = 701;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)(unsigned int)v37,
        (int)v91);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&FileTime);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
LABEL_42:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
LABEL_43:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      if ( v6 >= 0 )
        RoUninitialize();
      return (unsigned int)v37;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&FileTime);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  if ( (_DWORD)v2 )
  {
    v75 = 0;
    v41 = v70;
    v42 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v70 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    v43 = v42(v41, 1, &v75);
    v37 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)(unsigned int)v43,
        (int)v91);
      goto LABEL_42;
    }
    v74 = 0;
    v37 = Microsoft::WRL::ComPtr<ITrigger>::As<ITimeTrigger>(&v75, &v74);
    if ( v37 < 0 )
    {
      v44 = 718;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v44,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)(unsigned int)v37,
        (int)ppva);
LABEL_56:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
      goto LABEL_42;
    }
    *(_OWORD *)&v93.vt = 0;
    GetLocalTime((LPSYSTEMTIME)&v93);
    FileTime = 0;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)&v93, &FileTime) )
    {
      v47 = 724;
LABEL_59:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v47,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
                    v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
      goto LABEL_30;
    }
    FileTime = wil::FileTime::Add((wil::FileTime *)&FileTime, (const struct _FILETIME *)(10000 * v2), v45);
    if ( !FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)&v93) )
    {
      v47 = 728;
      goto LABEL_59;
    }
    *(_OWORD *)v94 = 0;
    v95 = 0;
    v96 = 0;
    LODWORD(ppva) = v93.wReserved1;
    v37 = StringCchPrintfW(v94, 0x14u, L"%04d-%02d-%02dT%02d:%02d:%02d", v93.vt);
    if ( v37 < 0 )
    {
      v44 = 737;
      goto LABEL_55;
    }
    wil::make_bstr_nothrow(&v81, v94);
    if ( !v81 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E4,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)0x8007000ELL,
        (int)ppva);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
      goto LABEL_38;
    }
    v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 120LL))(v74);
    v37 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)(unsigned int)v48,
        (int)ppva);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
      goto LABEL_56;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  }
  v76 = 0;
  v49 = v68;
  v50 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  v51 = v50(v49, &v76);
  v37 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v51,
      (int)ppva);
LABEL_71:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    goto LABEL_43;
  }
  v78 = 0;
  v52 = v76;
  v53 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v76 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  v54 = v53(v52, 1, &v78);
  v37 = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v54,
      (int)ppva);
LABEL_74:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    goto LABEL_71;
  }
  v79 = 0;
  v55 = Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(&v78, &v79);
  v37 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v55,
      (int)ppva);
LABEL_77:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    goto LABEL_74;
  }
  v80 = 0;
  memset_0(v97, 0, 0x208u);
  v37 = StringCchPrintfW(v97, 0x104u, L"/c /StatusPageTracking /o %s", this);
  if ( v37 < 0 )
  {
    v56 = 757;
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v56,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v37,
      (int)ppva);
LABEL_81:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
    goto LABEL_77;
  }
  v57 = wil::make_bstr_nothrow(&v81, v97);
  v58 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                     &v80,
                     v57) == 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
  if ( v58 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
LABEL_94:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    goto LABEL_95;
  }
  v37 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 104LL))(v79, v80);
  if ( v37 < 0 )
  {
    v56 = 762;
    goto LABEL_80;
  }
  v82 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
  LOBYTE(v59) = 1;
  TaskFolder = anonymous_namespace_::GetTaskFolder(v69, this, v59, &v82);
  v37 = TaskFolder;
  if ( TaskFolder < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)TaskFolder,
      (int)ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    goto LABEL_81;
  }
  wil::make_bstr_nothrow(&v74, L"Sync Status Poll");
  v61 = v74;
  if ( !v74 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x300,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)0x8007000ELL,
      (int)ppva);
LABEL_93:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    goto LABEL_94;
  }
  VariantInit(&v84);
  if ( v33 )
  {
    v84.vt = 8;
    v84.llVal = (LONGLONG)SysAllocString(v33);
    if ( !v84.llVal )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x306,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)0x8007000ELL,
        (int)ppva);
      VariantClear(&v84);
      goto LABEL_93;
    }
  }
  v83 = 0;
  v62 = v82;
  v63 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v82 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  VariantInit(&v85);
  v64 = *(_OWORD *)&v85.vt;
  v65 = v85.pRecInfo;
  VariantInit(&pvarg);
  *(_OWORD *)v94 = v64;
  *(_QWORD *)&v95 = v65;
  v89 = pvarg;
  v88 = v84;
  LastError = v63(v62, v61, v68, 6);
  VariantClear(&pvarg);
  VariantClear(&v85);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x312,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)LastError,
      (int)&v88);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    VariantClear(&v84);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    goto LABEL_31;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  VariantClear(&v84);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  if ( v6 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1800a7754  mov     rax, rsp
0x1800a7757  mov     [rax+18h], rbx
0x1800a775b  push    rbp
0x1800a775c  push    rsi
0x1800a775d  push    rdi
0x1800a775e  push    r12
0x1800a7760  push    r13
0x1800a7762  push    r14
0x1800a7764  push    r15
0x1800a7766  lea     rbp, [rax-3A8h]
0x1800a776d  sub     rsp, 470h
0x1800a7774  movaps  xmmword ptr [rax-48h], xmm6
0x1800a7778  movaps  xmmword ptr [rax-58h], xmm7
0x1800a777c  movaps  xmmword ptr [rax-68h], xmm8
0x1800a7781  movaps  xmmword ptr [rax-78h], xmm9
0x1800a7786  movaps  xmmword ptr [rax-88h], xmm10
0x1800a778e  movaps  xmmword ptr [rax-98h], xmm11
0x1800a7796  mov     rax, cs:__security_cookie
0x1800a779d  xor     rax, rsp
0x1800a77a0  mov     [rbp+3A0h+var_A0], rax
0x1800a77a7  mov     r12d, edx
0x1800a77aa  mov     r15, rcx
0x1800a77ad  xor     r13d, r13d
0x1800a77b0  test    rcx, rcx
0x1800a77b3  jnz     short loc_1800A77DC
0x1800a77b5  mov     rcx, [rbp+3A8h]; this
0x1800a77bc  mov     ebx, 80070057h
0x1800a77c1  mov     r9d, ebx; char *
0x1800a77c4  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a77cb  mov     edx, 299h; void *
0x1800a77d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a77d5  mov     eax, ebx
0x1800a77d7  jmp     loc_1800A85BC
0x1800a77dc  mov     r14d, 1
0x1800a77e2  mov     ecx, r14d
0x1800a77e5  call    cs:__imp_RoInitialize
0x1800a77ec  nop     dword ptr [rax+rax+00h]
0x1800a77f1  mov     edi, eax
0x1800a77f3  mov     [rbp+3A0h+var_388], eax
0x1800a77f6  mov     [rsp+4A0h+var_448], r13
0x1800a77fb  lea     rcx, [rsp+4A0h+var_448]
0x1800a7800  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7805  lea     rax, [rsp+4A0h+var_448]
0x1800a780a  mov     [rsp+4A0h+ppv], rax; int
0x1800a780f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800a7816  mov     r8d, r14d; dwClsContext
0x1800a7819  xor     edx, edx; pUnkOuter
0x1800a781b  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800a7822  call    cs:__imp_CoCreateInstance
0x1800a7829  nop     dword ptr [rax+rax+00h]
0x1800a782e  mov     ebx, eax
0x1800a7830  test    eax, eax
0x1800a7832  jns     short loc_1800A7874
0x1800a7834  mov     edx, 29Dh; void *
0x1800a7839  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7840  mov     r9d, ebx; char *
0x1800a7843  mov     rcx, [rbp+3A8h]; this
0x1800a784a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a784f  nop
0x1800a7850  lea     rcx, [rsp+4A0h+var_448]
0x1800a7855  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a785a  nop
0x1800a785b  test    edi, edi
0x1800a785d  js      loc_1800A77D5
0x1800a7863  call    cs:__imp_RoUninitialize
0x1800a786a  nop     dword ptr [rax+rax+00h]
0x1800a786f  jmp     loc_1800A77D5
0x1800a7874  mov     rsi, [rsp+4A0h+var_448]
0x1800a7879  mov     rax, [rsi]
0x1800a787c  mov     rbx, [rax+50h]
0x1800a7880  lea     rcx, [rbp+3A0h+pvarg]; pvarg
0x1800a7884  call    cs:__imp_VariantInit
0x1800a788b  nop     dword ptr [rax+rax+00h]
0x1800a7890  nop
0x1800a7891  movups  xmm10, xmmword ptr [rbp+3A0h+pvarg]
0x1800a7896  movsd   xmm11, qword ptr [rbp+3A0h+pvarg+10h]
0x1800a789c  lea     rcx, [rbp+3A0h+var_3B8]; pvarg
0x1800a78a0  call    cs:__imp_VariantInit
0x1800a78a7  nop     dword ptr [rax+rax+00h]
0x1800a78ac  nop
0x1800a78ad  movups  xmm8, xmmword ptr [rbp+3A0h+var_3B8]
0x1800a78b2  movsd   xmm9, qword ptr [rbp+3A0h+var_3B8+10h]
0x1800a78b8  lea     rcx, [rbp+3A0h+var_340]; pvarg
0x1800a78bc  call    cs:__imp_VariantInit
0x1800a78c3  nop     dword ptr [rax+rax+00h]
0x1800a78c8  nop
0x1800a78c9  movups  xmm6, xmmword ptr [rbp+3A0h+var_340]
0x1800a78cd  movsd   xmm7, qword ptr [rbp+3A0h+var_340+10h]
0x1800a78d2  lea     rcx, [rbp+3A0h+var_300]; pvarg
0x1800a78d9  call    cs:__imp_VariantInit
0x1800a78e0  nop     dword ptr [rax+rax+00h]
0x1800a78e5  nop
0x1800a78e6  movups  xmm0, xmmword ptr [rbp+3A0h+var_300]
0x1800a78ed  movsd   xmm1, qword ptr [rbp+3A0h+var_300+10h]
0x1800a78f5  movaps  xmmword ptr [rbp+3A0h+var_320], xmm10
0x1800a78fd  movsd   [rbp+3A0h+var_310], xmm11
0x1800a7906  movaps  xmmword ptr [rbp+3A0h+var_380], xmm8
0x1800a790b  movsd   [rbp+3A0h+var_370], xmm9
0x1800a7911  movaps  [rbp+3A0h+var_360], xmm6
0x1800a7915  movsd   [rbp+3A0h+var_350], xmm7
0x1800a791a  movaps  xmmword ptr [rbp+3A0h+var_2E0], xmm0
0x1800a7921  movsd   qword ptr [rbp+3A0h+var_2D0], xmm1
0x1800a7929  lea     rax, [rbp+3A0h+var_320]
0x1800a7930  mov     [rsp+4A0h+ppv], rax; int
0x1800a7935  lea     r9, [rbp+3A0h+var_380]
0x1800a7939  lea     r8, [rbp+3A0h+var_360]
0x1800a793d  lea     rdx, [rbp+3A0h+var_2E0]
0x1800a7944  mov     rcx, rsi
0x1800a7947  mov     rax, rbx
0x1800a794a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a794f  mov     ebx, eax
0x1800a7951  lea     rcx, [rbp+3A0h+var_300]; pvarg
0x1800a7958  call    cs:__imp_VariantClear
0x1800a795f  nop     dword ptr [rax+rax+00h]
0x1800a7964  nop
0x1800a7965  lea     rcx, [rbp+3A0h+var_340]; pvarg
0x1800a7969  call    cs:__imp_VariantClear
0x1800a7970  nop     dword ptr [rax+rax+00h]
0x1800a7975  nop
0x1800a7976  lea     rcx, [rbp+3A0h+var_3B8]; pvarg
0x1800a797a  call    cs:__imp_VariantClear
0x1800a7981  nop     dword ptr [rax+rax+00h]
0x1800a7986  nop
0x1800a7987  lea     rcx, [rbp+3A0h+pvarg]; pvarg
0x1800a798b  call    cs:__imp_VariantClear
0x1800a7992  nop     dword ptr [rax+rax+00h]
0x1800a7997  test    ebx, ebx
0x1800a7999  jns     short loc_1800A79A5
0x1800a799b  mov     edx, 29Eh
0x1800a79a0  jmp     loc_1800A7839
0x1800a79a5  mov     [rsp+4A0h+var_450], r13
0x1800a79aa  mov     rsi, [rsp+4A0h+var_448]
0x1800a79af  mov     rax, [rsi]
0x1800a79b2  mov     rbx, [rax+48h]
0x1800a79b6  lea     rcx, [rsp+4A0h+var_450]
0x1800a79bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a79c0  lea     r8, [rsp+4A0h+var_450]
0x1800a79c5  xor     edx, edx
0x1800a79c7  mov     rcx, rsi
0x1800a79ca  mov     rax, rbx
0x1800a79cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a79d2  mov     ebx, eax
0x1800a79d4  test    eax, eax
0x1800a79d6  jns     short loc_1800A7A03
0x1800a79d8  mov     rcx, [rbp+3A8h]; this
0x1800a79df  mov     r9d, eax; char *
0x1800a79e2  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a79e9  mov     edx, 2A1h; void *
0x1800a79ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a79f3  nop
0x1800a79f4  lea     rcx, [rsp+4A0h+var_450]
0x1800a79f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a79fe  jmp     loc_1800A7850
0x1800a7a03  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800a7a0a  lea     rcx, [rsp+4A0h+var_430]
0x1800a7a0f  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a7a14  nop
0x1800a7a15  mov     rdx, [rsp+4A0h+var_430]
0x1800a7a1a  test    rdx, rdx
0x1800a7a1d  jnz     short loc_1800A7A42
0x1800a7a1f  mov     rcx, [rbp+3A8h]; this
0x1800a7a26  mov     r9d, 8007000Eh; char *
0x1800a7a2c  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7a33  mov     edx, 2A4h; void *
0x1800a7a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7a3d  jmp     loc_1800A8377
0x1800a7a42  mov     rcx, [rsp+4A0h+var_450]
0x1800a7a47  mov     rax, [rcx]
0x1800a7a4a  mov     rax, [rax+0A0h]
0x1800a7a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7a56  mov     ebx, eax
0x1800a7a58  test    eax, eax
0x1800a7a5a  jns     short loc_1800A7A87
0x1800a7a5c  mov     rcx, [rbp+3A8h]; this
0x1800a7a63  mov     r9d, eax; char *
0x1800a7a66  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7a6d  mov     edx, 2A6h; void *
0x1800a7a72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7a77  nop
0x1800a7a78  lea     rcx, [rsp+4A0h+var_430]
0x1800a7a7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a7a82  jmp     loc_1800A79F4
0x1800a7a87  mov     [rsp+4A0h+var_440], r13
0x1800a7a8c  mov     rsi, [rsp+4A0h+var_450]
0x1800a7a91  mov     rax, [rsi]
0x1800a7a94  mov     rbx, [rax+48h]
0x1800a7a98  lea     rcx, [rsp+4A0h+var_440]
0x1800a7a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7aa2  lea     rdx, [rsp+4A0h+var_440]
0x1800a7aa7  mov     rcx, rsi
0x1800a7aaa  mov     rax, rbx
0x1800a7aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7ab2  mov     ebx, eax
0x1800a7ab4  test    eax, eax
0x1800a7ab6  jns     short loc_1800A7AE0
0x1800a7ab8  mov     rcx, [rbp+3A8h]; this
0x1800a7abf  mov     r9d, eax; char *
0x1800a7ac2  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7ac9  mov     edx, 2A9h; void *
0x1800a7ace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7ad3  nop
0x1800a7ad4  lea     rcx, [rsp+4A0h+var_440]
0x1800a7ad9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7ade  jmp     short loc_1800A7A78
0x1800a7ae0  mov     [rsp+4A0h+var_438], r13
0x1800a7ae5  mov     rsi, [rsp+4A0h+var_450]
0x1800a7aea  mov     rax, [rsi]
0x1800a7aed  mov     rbx, [rax+78h]
0x1800a7af1  lea     rcx, [rsp+4A0h+var_438]
0x1800a7af6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7afb  lea     rdx, [rsp+4A0h+var_438]
0x1800a7b00  mov     rcx, rsi
0x1800a7b03  mov     rax, rbx
0x1800a7b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7b0b  mov     ebx, eax
0x1800a7b0d  test    eax, eax
0x1800a7b0f  jns     short loc_1800A7B39
0x1800a7b11  mov     edx, 2ACh; void *
0x1800a7b16  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7b1d  mov     r9d, ebx; char *
0x1800a7b20  mov     rcx, [rbp+3A8h]; this
0x1800a7b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7b2c  nop
0x1800a7b2d  lea     rcx, [rsp+4A0h+var_438]
0x1800a7b32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7b37  jmp     short loc_1800A7AD4
0x1800a7b39  mov     rcx, [rsp+4A0h+var_438]
0x1800a7b3e  mov     rax, [rcx]
0x1800a7b41  mov     edx, r14d
0x1800a7b44  mov     rax, [rax+90h]
0x1800a7b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7b50  mov     ebx, eax
0x1800a7b52  test    eax, eax
0x1800a7b54  jns     short loc_1800A7B5D
0x1800a7b56  mov     edx, 2ADh
0x1800a7b5b  jmp     short loc_1800A7B16
0x1800a7b5d  mov     [rsp+4A0h+psz], r13
0x1800a7b62  mov     [rbp+3A0h+var_418], r13
0x1800a7b66  mov     rsi, [rsp+4A0h+var_440]
0x1800a7b6b  mov     rax, [rsi]
0x1800a7b6e  mov     rbx, [rax+50h]
0x1800a7b72  lea     rcx, [rbp+3A0h+var_418]
0x1800a7b76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7b7b  lea     r8, [rbp+3A0h+var_418]
0x1800a7b7f  mov     edx, 9
0x1800a7b84  mov     rcx, rsi
0x1800a7b87  mov     rax, rbx
0x1800a7b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7b8f  mov     ebx, eax
0x1800a7b91  test    eax, eax
0x1800a7b93  jns     short loc_1800A7BCA
0x1800a7b95  mov     rcx, [rbp+3A8h]; this
0x1800a7b9c  mov     r9d, eax; char *
0x1800a7b9f  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7ba6  mov     edx, 2B4h; void *
0x1800a7bab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7bb0  nop
0x1800a7bb1  lea     rcx, [rbp+3A0h+var_418]
0x1800a7bb5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7bba  nop
0x1800a7bbb  lea     rcx, [rsp+4A0h+psz]
0x1800a7bc0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a7bc5  jmp     loc_1800A7B2D
0x1800a7bca  mov     [rbp+3A0h+var_420], r13
0x1800a7bce  mov     rbx, [rbp+3A0h+var_418]
0x1800a7bd2  mov     rax, [rbx]
0x1800a7bd5  mov     rsi, [rax]
0x1800a7bd8  lea     rcx, [rbp+3A0h+var_420]
0x1800a7bdc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7be1  lea     r8, [rbp+3A0h+var_420]
0x1800a7be5  lea     rdx, _GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c
0x1800a7bec  mov     rcx, rbx
0x1800a7bef  mov     rax, rsi
0x1800a7bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7bf7  mov     ebx, eax
0x1800a7bf9  test    eax, eax
0x1800a7bfb  jns     short loc_1800A7C24
0x1800a7bfd  mov     rcx, [rbp+3A8h]; this
0x1800a7c04  mov     r9d, eax; char *
0x1800a7c07  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7c0e  mov     edx, 2B7h; void *
0x1800a7c13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7c18  nop
0x1800a7c19  lea     rcx, [rbp+3A0h+var_420]
0x1800a7c1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a7c22  jmp     short loc_1800A7BB1
0x1800a7c24  mov     qword ptr [rbp+3A0h+FileTime.dwLowDateTime], r13
0x1800a7c28  xor     edx, edx
0x1800a7c2a  lea     rcx, [rsp+4A0h+psz]
0x1800a7c2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a7c34  lea     rdx, [rsp+4A0h+psz]
0x1800a7c39  mov     rcx, r15
0x1800a7c3c  call    _anonymous_namespace___GetEnrollmentSid
0x1800a7c41  mov     rbx, [rsp+4A0h+psz]
0x1800a7c46  lea     rcx, [rbp+3A0h+var_3E8]
0x1800a7c4a  test    eax, eax
0x1800a7c4c  js      loc_1800A7D70
0x1800a7c52  mov     rdx, rbx
0x1800a7c55  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a7c5a  mov     rdx, rax
  ... truncated ...
```
