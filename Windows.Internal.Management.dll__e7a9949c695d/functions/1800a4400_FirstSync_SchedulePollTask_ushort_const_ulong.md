# FirstSync::SchedulePollTask(ushort const *,ulong)

- ea: `0x1800a4400`
- end: `0x1800a5210`
- name: `?SchedulePollTask@FirstSync@@YAJPEBGK@Z`
- size: `3600`
- prototype: `__int64 __fastcall(FirstSync *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025be0`
- `0x1800a40ac`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000992c`
- `0x18000a284`
- `0x18000a2a4`
- `0x18000a8e8`
- `0x180017204`
- `0x180019fb8`
- `0x180024cd0`
- `0x180046584`
- `0x180069770`
- `0x1800a08e8`
- `0x1800a0938`
- `0x1800a25f0`
- `0x1800a3020`
- `0x1800a3424`
- `0x1800a4400`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a44c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a44c8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a44ff`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a49c3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a4fd8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a51c0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a44ff`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a49c3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a4fd8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a51c0`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a4491`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a4491`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a4af8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a4af8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a4f19`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a4f19`
- `OLEAUT32!__imp_VariantInit` at `0x1800a451a`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4530`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4546`
- `OLEAUT32!__imp_VariantInit` at `0x1800a455d`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4efd`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5007`
- `OLEAUT32!__imp_VariantInit` at `0x1800a501b`
- `OLEAUT32!__imp_VariantInit` at `0x1800a451a`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4530`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4546`
- `OLEAUT32!__imp_VariantInit` at `0x1800a455d`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4efd`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5007`
- `OLEAUT32!__imp_VariantInit` at `0x1800a501b`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45e1`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45f7`
- `OLEAUT32!__imp_VariantClear` at `0x1800a4f4f`
- `OLEAUT32!__imp_VariantClear` at `0x1800a50a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800a50ae`
- `OLEAUT32!__imp_VariantClear` at `0x1800a50e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5137`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45e1`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800a45f7`
- `OLEAUT32!__imp_VariantClear` at `0x1800a4f4f`
- `OLEAUT32!__imp_VariantClear` at `0x1800a50a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800a50ae`
- `OLEAUT32!__imp_VariantClear` at `0x1800a50e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800a5137`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800a4b0d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800a4b0d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800a4b5f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800a4b5f`

## string_xrefs

- `0x1800a4669`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\DMAppsRes.dll,-26094)</Author>\n        <Description>$(@%systemRoot%\system32\DMAppsRes.dll,-26096)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Settings>\n        <MultipleInstancesPolicy>Queue</MultipleInstancesPolicy>\n        <Disallo`

## pseudocode

```c
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
0x1800a4400  mov     rax, rsp
0x1800a4403  mov     [rax+18h], rbx
0x1800a4407  push    rbp
0x1800a4408  push    rsi
0x1800a4409  push    rdi
0x1800a440a  push    r12
0x1800a440c  push    r13
0x1800a440e  push    r14
0x1800a4410  push    r15
0x1800a4412  lea     rbp, [rax-3A8h]
0x1800a4419  sub     rsp, 470h
0x1800a4420  movaps  xmmword ptr [rax-48h], xmm6
0x1800a4424  movaps  xmmword ptr [rax-58h], xmm7
0x1800a4428  movaps  xmmword ptr [rax-68h], xmm8
0x1800a442d  movaps  xmmword ptr [rax-78h], xmm9
0x1800a4432  movaps  xmmword ptr [rax-88h], xmm10
0x1800a443a  movaps  xmmword ptr [rax-98h], xmm11
0x1800a4442  mov     rax, cs:__security_cookie
0x1800a4449  xor     rax, rsp
0x1800a444c  mov     [rbp+3A0h+var_A0], rax
0x1800a4453  mov     r12d, edx
0x1800a4456  mov     r15, rcx
0x1800a4459  xor     r13d, r13d
0x1800a445c  test    rcx, rcx
0x1800a445f  jnz     short loc_1800A4488
0x1800a4461  mov     rcx, [rbp+3A8h]; this
0x1800a4468  mov     ebx, 80070057h
0x1800a446d  mov     r9d, ebx; char *
0x1800a4470  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a4477  mov     edx, 299h; void *
0x1800a447c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4481  mov     eax, ebx
0x1800a4483  jmp     loc_1800A51C8
0x1800a4488  mov     r14d, 1
0x1800a448e  mov     ecx, r14d
0x1800a4491  call    cs:__imp_RoInitialize
0x1800a4497  mov     edi, eax
0x1800a4499  mov     [rbp+3A0h+var_388], eax
0x1800a449c  mov     [rsp+4A0h+var_448], r13
0x1800a44a1  lea     rcx, [rsp+4A0h+var_448]
0x1800a44a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a44ab  lea     rax, [rsp+4A0h+var_448]
0x1800a44b0  mov     [rsp+4A0h+ppv], rax; int
0x1800a44b5  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800a44bc  mov     r8d, r14d; dwClsContext
0x1800a44bf  xor     edx, edx; pUnkOuter
0x1800a44c1  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800a44c8  call    cs:__imp_CoCreateInstance
0x1800a44ce  mov     ebx, eax
0x1800a44d0  test    eax, eax
0x1800a44d2  jns     short loc_1800A450A
0x1800a44d4  mov     edx, 29Dh; void *
0x1800a44d9  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a44e0  mov     r9d, ebx; char *
0x1800a44e3  mov     rcx, [rbp+3A8h]; this
0x1800a44ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a44ef  nop
0x1800a44f0  lea     rcx, [rsp+4A0h+var_448]
0x1800a44f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a44fa  nop
0x1800a44fb  test    edi, edi
0x1800a44fd  js      short loc_1800A4481
0x1800a44ff  call    cs:__imp_RoUninitialize
0x1800a4505  jmp     loc_1800A4481
0x1800a450a  mov     rsi, [rsp+4A0h+var_448]
0x1800a450f  mov     rax, [rsi]
0x1800a4512  mov     rbx, [rax+50h]
0x1800a4516  lea     rcx, [rbp+3A0h+pvarg]; pvarg
0x1800a451a  call    cs:__imp_VariantInit
0x1800a4520  nop
0x1800a4521  movups  xmm10, xmmword ptr [rbp+3A0h+pvarg]
0x1800a4526  movsd   xmm11, qword ptr [rbp+3A0h+pvarg+10h]
0x1800a452c  lea     rcx, [rbp+3A0h+var_3B8]; pvarg
0x1800a4530  call    cs:__imp_VariantInit
0x1800a4536  nop
0x1800a4537  movups  xmm8, xmmword ptr [rbp+3A0h+var_3B8]
0x1800a453c  movsd   xmm9, qword ptr [rbp+3A0h+var_3B8+10h]
0x1800a4542  lea     rcx, [rbp+3A0h+var_340]; pvarg
0x1800a4546  call    cs:__imp_VariantInit
0x1800a454c  nop
0x1800a454d  movups  xmm6, xmmword ptr [rbp+3A0h+var_340]
0x1800a4551  movsd   xmm7, qword ptr [rbp+3A0h+var_340+10h]
0x1800a4556  lea     rcx, [rbp+3A0h+var_300]; pvarg
0x1800a455d  call    cs:__imp_VariantInit
0x1800a4563  nop
0x1800a4564  movups  xmm0, xmmword ptr [rbp+3A0h+var_300]
0x1800a456b  movsd   xmm1, qword ptr [rbp+3A0h+var_300+10h]
0x1800a4573  movaps  xmmword ptr [rbp+3A0h+var_320], xmm10
0x1800a457b  movsd   [rbp+3A0h+var_310], xmm11
0x1800a4584  movaps  xmmword ptr [rbp+3A0h+var_380], xmm8
0x1800a4589  movsd   [rbp+3A0h+var_370], xmm9
0x1800a458f  movaps  [rbp+3A0h+var_360], xmm6
0x1800a4593  movsd   [rbp+3A0h+var_350], xmm7
0x1800a4598  movaps  xmmword ptr [rbp+3A0h+var_2E0], xmm0
0x1800a459f  movsd   qword ptr [rbp+3A0h+var_2D0], xmm1
0x1800a45a7  lea     rax, [rbp+3A0h+var_320]
0x1800a45ae  mov     [rsp+4A0h+ppv], rax; int
0x1800a45b3  lea     r9, [rbp+3A0h+var_380]
0x1800a45b7  lea     r8, [rbp+3A0h+var_360]
0x1800a45bb  lea     rdx, [rbp+3A0h+var_2E0]
0x1800a45c2  mov     rcx, rsi
0x1800a45c5  mov     rax, rbx
0x1800a45c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45cd  mov     ebx, eax
0x1800a45cf  lea     rcx, [rbp+3A0h+var_300]; pvarg
0x1800a45d6  call    cs:__imp_VariantClear
0x1800a45dc  nop
0x1800a45dd  lea     rcx, [rbp+3A0h+var_340]; pvarg
0x1800a45e1  call    cs:__imp_VariantClear
0x1800a45e7  nop
0x1800a45e8  lea     rcx, [rbp+3A0h+var_3B8]; pvarg
0x1800a45ec  call    cs:__imp_VariantClear
0x1800a45f2  nop
0x1800a45f3  lea     rcx, [rbp+3A0h+pvarg]; pvarg
0x1800a45f7  call    cs:__imp_VariantClear
0x1800a45fd  test    ebx, ebx
0x1800a45ff  jns     short loc_1800A460B
0x1800a4601  mov     edx, 29Eh
0x1800a4606  jmp     loc_1800A44D9
0x1800a460b  mov     [rsp+4A0h+var_450], r13
0x1800a4610  mov     rsi, [rsp+4A0h+var_448]
0x1800a4615  mov     rax, [rsi]
0x1800a4618  mov     rbx, [rax+48h]
0x1800a461c  lea     rcx, [rsp+4A0h+var_450]
0x1800a4621  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4626  lea     r8, [rsp+4A0h+var_450]
0x1800a462b  xor     edx, edx
0x1800a462d  mov     rcx, rsi
0x1800a4630  mov     rax, rbx
0x1800a4633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4638  mov     ebx, eax
0x1800a463a  test    eax, eax
0x1800a463c  jns     short loc_1800A4669
0x1800a463e  mov     rcx, [rbp+3A8h]; this
0x1800a4645  mov     r9d, eax; char *
0x1800a4648  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a464f  mov     edx, 2A1h; void *
0x1800a4654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4659  nop
0x1800a465a  lea     rcx, [rsp+4A0h+var_450]
0x1800a465f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4664  jmp     loc_1800A44F0
0x1800a4669  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1800a4670  lea     rcx, [rsp+4A0h+var_430]
0x1800a4675  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a467a  nop
0x1800a467b  mov     rdx, [rsp+4A0h+var_430]
0x1800a4680  test    rdx, rdx
0x1800a4683  jnz     short loc_1800A46A8
0x1800a4685  mov     rcx, [rbp+3A8h]; this
0x1800a468c  mov     r9d, 8007000Eh; char *
0x1800a4692  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a4699  mov     edx, 2A4h; void *
0x1800a469e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a46a3  jmp     loc_1800A4FB3
0x1800a46a8  mov     rcx, [rsp+4A0h+var_450]
0x1800a46ad  mov     rax, [rcx]
0x1800a46b0  mov     rax, [rax+0A0h]
0x1800a46b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a46bc  mov     ebx, eax
0x1800a46be  test    eax, eax
0x1800a46c0  jns     short loc_1800A46ED
0x1800a46c2  mov     rcx, [rbp+3A8h]; this
0x1800a46c9  mov     r9d, eax; char *
0x1800a46cc  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a46d3  mov     edx, 2A6h; void *
0x1800a46d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a46dd  nop
0x1800a46de  lea     rcx, [rsp+4A0h+var_430]
0x1800a46e3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a46e8  jmp     loc_1800A465A
0x1800a46ed  mov     [rsp+4A0h+var_440], r13
0x1800a46f2  mov     rsi, [rsp+4A0h+var_450]
0x1800a46f7  mov     rax, [rsi]
0x1800a46fa  mov     rbx, [rax+48h]
0x1800a46fe  lea     rcx, [rsp+4A0h+var_440]
0x1800a4703  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4708  lea     rdx, [rsp+4A0h+var_440]
0x1800a470d  mov     rcx, rsi
0x1800a4710  mov     rax, rbx
0x1800a4713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4718  mov     ebx, eax
0x1800a471a  test    eax, eax
0x1800a471c  jns     short loc_1800A4746
0x1800a471e  mov     rcx, [rbp+3A8h]; this
0x1800a4725  mov     r9d, eax; char *
0x1800a4728  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a472f  mov     edx, 2A9h; void *
0x1800a4734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4739  nop
0x1800a473a  lea     rcx, [rsp+4A0h+var_440]
0x1800a473f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4744  jmp     short loc_1800A46DE
0x1800a4746  mov     [rsp+4A0h+var_438], r13
0x1800a474b  mov     rsi, [rsp+4A0h+var_450]
0x1800a4750  mov     rax, [rsi]
0x1800a4753  mov     rbx, [rax+78h]
0x1800a4757  lea     rcx, [rsp+4A0h+var_438]
0x1800a475c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4761  lea     rdx, [rsp+4A0h+var_438]
0x1800a4766  mov     rcx, rsi
0x1800a4769  mov     rax, rbx
0x1800a476c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4771  mov     ebx, eax
0x1800a4773  test    eax, eax
0x1800a4775  jns     short loc_1800A479F
0x1800a4777  mov     edx, 2ACh; void *
0x1800a477c  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a4783  mov     r9d, ebx; char *
0x1800a4786  mov     rcx, [rbp+3A8h]; this
0x1800a478d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4792  nop
0x1800a4793  lea     rcx, [rsp+4A0h+var_438]
0x1800a4798  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a479d  jmp     short loc_1800A473A
0x1800a479f  mov     rcx, [rsp+4A0h+var_438]
0x1800a47a4  mov     rax, [rcx]
0x1800a47a7  mov     edx, r14d
0x1800a47aa  mov     rax, [rax+90h]
0x1800a47b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47b6  mov     ebx, eax
0x1800a47b8  test    eax, eax
0x1800a47ba  jns     short loc_1800A47C3
0x1800a47bc  mov     edx, 2ADh
0x1800a47c1  jmp     short loc_1800A477C
0x1800a47c3  mov     [rsp+4A0h+psz], r13
0x1800a47c8  mov     [rbp+3A0h+var_418], r13
0x1800a47cc  mov     rsi, [rsp+4A0h+var_440]
0x1800a47d1  mov     rax, [rsi]
0x1800a47d4  mov     rbx, [rax+50h]
0x1800a47d8  lea     rcx, [rbp+3A0h+var_418]
0x1800a47dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a47e1  lea     r8, [rbp+3A0h+var_418]
0x1800a47e5  mov     edx, 9
0x1800a47ea  mov     rcx, rsi
0x1800a47ed  mov     rax, rbx
0x1800a47f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47f5  mov     ebx, eax
0x1800a47f7  test    eax, eax
0x1800a47f9  jns     short loc_1800A4830
0x1800a47fb  mov     rcx, [rbp+3A8h]; this
0x1800a4802  mov     r9d, eax; char *
0x1800a4805  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a480c  mov     edx, 2B4h; void *
0x1800a4811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4816  nop
0x1800a4817  lea     rcx, [rbp+3A0h+var_418]
0x1800a481b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4820  nop
0x1800a4821  lea     rcx, [rsp+4A0h+psz]
0x1800a4826  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a482b  jmp     loc_1800A4793
0x1800a4830  mov     [rbp+3A0h+var_420], r13
0x1800a4834  mov     rbx, [rbp+3A0h+var_418]
0x1800a4838  mov     rax, [rbx]
0x1800a483b  mov     rsi, [rax]
0x1800a483e  lea     rcx, [rbp+3A0h+var_420]
0x1800a4842  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4847  lea     r8, [rbp+3A0h+var_420]
0x1800a484b  lea     rdx, _GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c
0x1800a4852  mov     rcx, rbx
0x1800a4855  mov     rax, rsi
0x1800a4858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a485d  mov     ebx, eax
0x1800a485f  test    eax, eax
0x1800a4861  jns     short loc_1800A488A
0x1800a4863  mov     rcx, [rbp+3A8h]; this
0x1800a486a  mov     r9d, eax; char *
0x1800a486d  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a4874  mov     edx, 2B7h; void *
0x1800a4879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a487e  nop
0x1800a487f  lea     rcx, [rbp+3A0h+var_420]
0x1800a4883  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4888  jmp     short loc_1800A4817
0x1800a488a  mov     qword ptr [rbp+3A0h+FileTime.dwLowDateTime], r13
0x1800a488e  xor     edx, edx
0x1800a4890  lea     rcx, [rsp+4A0h+psz]
0x1800a4895  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a489a  lea     rdx, [rsp+4A0h+psz]
0x1800a489f  mov     rcx, r15
0x1800a48a2  call    _anonymous_namespace___GetEnrollmentSid
0x1800a48a7  mov     rbx, [rsp+4A0h+psz]
0x1800a48ac  lea     rcx, [rbp+3A0h+var_3E8]
0x1800a48b0  test    eax, eax
0x1800a48b2  js      loc_1800A49D0
0x1800a48b8  mov     rdx, rbx
0x1800a48bb  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800a48c0  mov     rdx, rax
0x1800a48c3  lea     rcx, [rbp+3A0h+FileTime]
0x1800a48c7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800a48cc  cmp     [rax], r13
0x1800a48cf  setz    sil
0x1800a48d3  lea     rcx, [rbp+3A0h+var_3E8]
0x1800a48d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a48dc  test    sil, sil
0x1800a48df  jz      short loc_1800A4922
0x1800a48e1  mov     edx, 2BCh; void *
0x1800a48e6  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a48ed  mov     r9d, 8007000Eh; char *
  ... truncated ...
```
