# LaunchFactsAppTask::Execute(void)

- ea: `0x180027b20`
- end: `0x1800284c7`
- name: `?Execute@LaunchFactsAppTask@@MEAAXXZ`
- size: `2471`
- prototype: `void __fastcall(LaunchFactsAppTask *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000e330`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180013988`
- `0x180014930`
- `0x18001bf68`
- `0x18001e19c`
- `0x18001e55c`
- `0x180022180`
- `0x18002666c`
- `0x180027760`
- `0x1800277fc`
- `0x180027a38`
- `0x180027a90`
- `0x180027b20`
- `0x180028690`
- `0x1800329d8`
- `0x180033750`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027ba6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027ba6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028221`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800283b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028221`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800283b0`

## string_xrefs

- `0x180027b98`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x180027c32`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180027c8b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180027d09`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180027d90`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180027df5`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180027e35`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180027f84`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x18002801b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180028078`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x18002810e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180028172`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x1800281d5`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180028236`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180028290`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x180028339`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x1800283c5`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`
- `0x18002841f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchfactsapptask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall LaunchFactsAppTask::Execute(LaunchFactsAppTask *this)
{
  LaunchFactsAppTask *v1; // r13
  struct Windows::Foundation::Collections::IPropertySet *v2; // r12
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // r9d
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r14d
  __int64 *v12; // rdi
  __int64 (__fastcall *v13)(__int64 *, const unsigned __int16 **); // rbx
  int v14; // eax
  RDXAppServiceConnection **v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  const unsigned __int16 *v18; // rbx
  struct Windows::Foundation::Collections::IPropertySet *v19; // rcx
  int v20; // eax
  __int64 (__fastcall *v21)(const unsigned __int16 *, const wchar_t *, __int64, GUID *); // r10
  __int64 *v22; // rax
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  const char *v28; // r9
  int v29; // eax
  __int64 v30; // rax
  unsigned int v31; // edi
  __int64 v32; // rdx
  char v33; // al
  int v34; // eax
  __int64 v35; // rax
  unsigned int v36; // edi
  __int64 v37; // rdx
  char v38; // al
  int v39; // eax
  __int64 v40; // rax
  struct Windows::Foundation::Collections::IPropertySet **v41; // r13
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  HRESULT v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  LPVOID v48; // rdi
  __int64 (__fastcall *v49)(LPVOID, GUID *, GUID *, const unsigned __int16 **); // rbx
  int v50; // eax
  const unsigned __int16 *v51; // rbx
  __int64 (__fastcall *v52)(const unsigned __int16 *, _QWORD, __int64, __int64); // r14
  __int64 v53; // rsi
  __int64 v54; // rdi
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  HRESULT v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  LPVOID v64; // rdi
  __int64 (__fastcall *v65)(LPVOID, GUID *, GUID *, const unsigned __int16 **); // rbx
  int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  int pdwType; // [rsp+20h] [rbp-278h]
  int pdwTypea; // [rsp+20h] [rbp-278h]
  int pdwTypeb; // [rsp+20h] [rbp-278h]
  int pdwTypec; // [rsp+20h] [rbp-278h]
  int v75[2]; // [rsp+48h] [rbp-250h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-248h] BYREF
  const unsigned __int16 *v77; // [rsp+58h] [rbp-240h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v78; // [rsp+60h] [rbp-238h] BYREF
  __int64 *v79; // [rsp+68h] [rbp-230h] BYREF
  unsigned int pvData; // [rsp+70h] [rbp-228h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v81; // [rsp+78h] [rbp-220h] BYREF
  __int64 *v82; // [rsp+80h] [rbp-218h] BYREF
  const unsigned __int16 *v83; // [rsp+88h] [rbp-210h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp-208h] BYREF
  const unsigned __int16 *v85; // [rsp+98h] [rbp-200h] BYREF
  LaunchFactsAppTask *v86; // [rsp+A0h] [rbp-1F8h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-1F0h] BYREF
  HSTRING v88; // [rsp+C0h] [rbp-1D8h]
  _BYTE v89[32]; // [rsp+C8h] [rbp-1D0h] BYREF
  _BYTE v90[40]; // [rsp+E8h] [rbp-1B0h] BYREF
  _QWORD v91[42]; // [rsp+110h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v1 = this;
  v86 = this;
  v75[0] = 0;
  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
         L"IdleTimeoutInSeconds",
         0x20000010u,
         0,
         &pvData,
         &pcbData) )
  {
    pvData = 120;
  }
  wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v91);
  v91[0] = &RetailDemoTelemetry::LaunchLaunchFactsApp::`vftable';
  v2 = (LaunchFactsAppTask *)((char *)v1 + 88);
  v81 = (LaunchFactsAppTask *)((char *)v1 + 88);
  RetailDemoTelemetry::LaunchLaunchFactsApp::StartActivity(
    (RetailDemoTelemetry::LaunchLaunchFactsApp *)v91,
    *((_BYTE *)v1 + 88),
    pvData);
  v82 = 0;
  v3 = (__int64 *)*((_QWORD *)v1 + 8);
  v4 = *v3;
  v82 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v4 + 96))(v3, &v82);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
      (const char *)(unsigned int)v5,
      pdwType);
  v79 = 0;
  v6 = *v82;
  v79 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v6 + 72))(v82, &v79);
  if ( v7 == 1 )
  {
    RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<27,long>(1);
  }
  else
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
        (const char *)(unsigned int)v7,
        pdwType);
    v75[0] = 0;
    SHRegGetBOOLWithREGSAM(
      (HKEY)retaddr,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
      L"DisableDFT",
      v8,
      v75);
    v11 = v75[0];
    if ( v75[0] )
      goto LABEL_58;
    try
    {
      v77 = 0;
      v12 = v79;
      v13 = *(__int64 (__fastcall **)(__int64 *, const unsigned __int16 **))(*v79 + 24);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v77,
        0);
      v14 = v13(v12, &v77);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)(unsigned int)(v11 + 85),
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v14,
          pdwTypea);
      v83 = v77;
      v85 = L"Microsoft-RetailDemo-ShouldLaunch";
      v15 = wil::MakeOrThrow<RDXAppServiceConnection,unsigned short const * &,unsigned short const * &>(
              (RDXAppServiceConnection **)v75,
              &v85,
              &v83);
      v18 = (const unsigned __int16 *)*v15;
      *v15 = 0;
      v85 = v18;
      v19 = *(struct Windows::Foundation::Collections::IPropertySet **)v75;
      if ( *(_QWORD *)v75 )
      {
        *(_QWORD *)v75 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRDXAppServiceConnection,Microsoft::WRL::FtmBase>::Release(
          v19,
          v16,
          v17);
      }
      v20 = (*(__int64 (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v18 + 24LL))(v18);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v20,
          pdwTypea);
      ppv = 0;
      v21 = *(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, __int64, GUID *))(*(_QWORD *)v18 + 56LL);
      ppv = 0;
      v22 = (__int64 *)*((_QWORD *)v1 + 6);
      if ( v22 )
        v23 = *v22;
      else
        v23 = 0;
      v24 = v21(v18, L"ShouldLaunch", v23, &GUID_8d503cec_9aa3_4e68_9559_9de63e372ce4);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v24,
          (int)&ppv);
      v78 = 0;
      v25 = *(_QWORD *)ppv;
      v78 = 0;
      v26 = (*(__int64 (__fastcall **)(LPVOID, struct Windows::Foundation::Collections::IPropertySet **))(v25 + 48))(
              ppv,
              &v78);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v26,
          (int)&ppv);
      Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
        (Windows::Internal::ShellHelpers::PropertySetHelper *)&v83,
        v78);
      v88 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Launch", 7u, 6u);
      v75[0] = 3;
      Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned char>(
        (Windows::Internal::ShellHelpers::PropertySetHelper *)&v83,
        v88);
      if ( v83 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v83 + 16LL))(v83);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v78);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&ppv);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v85);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v77);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x69,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
        v28);
      v75[0] = 1;
      v11 = 1;
      v1 = v86;
      v2 = v81;
    }
    if ( v11 )
    {
LABEL_58:
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v9, v10);
      v61 = CoCreateInstance(
              &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
              0,
              4u,
              &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
              &ppv);
      if ( v61 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v61,
          pdwTypec);
      v77 = 0;
      v64 = ppv;
      v65 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, const unsigned __int16 **))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77, v62, v63);
      v66 = v65(v64, &GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f, &GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f, &v77);
      if ( v66 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v66,
          pdwTypec);
      if ( v77 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v77 + 64LL))(v77);
      RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<27,long>(1);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77, v67, v68);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v69, v70);
    }
    else
    {
      v78 = 0;
      *(_QWORD *)v75 = 0;
      if ( *(_BYTE *)v2 )
      {
        hstringHeader.Reserved.Reserved1 = &v78;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        v29 = _AllocStringWorker<CTCoAllocPolicy>(v27, v9, L"Interactive");
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
            (const char *)(unsigned int)v29,
            (int)&ppv);
      }
      else
      {
        v30 = *v79;
        hstringHeader.Reserved.Reserved1 = v75;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        v31 = (*(__int64 (__fastcall **)(__int64 *, char *))(v30 + 64))(v79, &hstringHeader.Reserved.Reserved2[8]);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
        if ( (int)(v31 + 0x80000000) < 0 || (v33 = 1, v31 == -2147024664) )
          v33 = 0;
        if ( v33 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x86,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
            (const char *)v31,
            (int)&ppv);
        hstringHeader.Reserved.Reserved1 = &v78;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        v34 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v32, L"Idle");
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x87,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
            (const char *)(unsigned int)v34,
            (int)&ppv);
      }
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
      if ( !*(_QWORD *)v75 )
      {
        v35 = *v79;
        hstringHeader.Reserved.Reserved1 = v75;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        v36 = (*(__int64 (__fastcall **)(__int64 *, char *))(v35 + 72))(v79, &hstringHeader.Reserved.Reserved2[8]);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
        if ( ((v36 + 0x80000000) & 0x80000000) != 0 || (v38 = 1, v36 == -2147024664) )
          v38 = 0;
        if ( v38 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8E,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
            (const char *)v36,
            (int)&ppv);
        if ( !*(_QWORD *)v75 )
        {
          hstringHeader.Reserved.Reserved1 = v75;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
          hstringHeader.Reserved.Reserved2[16] = 1;
          v39 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v37, &qword_180057BE0);
          if ( v39 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x93,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
              (const char *)(unsigned int)v39,
              (int)&ppv);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
        }
      }
      v40 = *v79;
      v41 = (struct Windows::Foundation::Collections::IPropertySet **)((char *)v1 + 80);
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v41;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v42 = (*(__int64 (__fastcall **)(__int64 *, char *))(v40 + 48))(v79, &hstringHeader.Reserved.Reserved2[8]);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x96,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v42,
          (int)&ppv);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v43, v44);
      v45 = CoCreateInstance(
              &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
              0,
              4u,
              &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
              &ppv);
      if ( v45 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x99,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v45,
          pdwTypeb);
      v77 = 0;
      v48 = ppv;
      v49 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, const unsigned __int16 **))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77, v46, v47);
      v50 = v49(v48, &GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f, &GUID_c83ec4e0_068f_4a90_a1c7_20841a08f99f, &v77);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
          (const char *)(unsigned int)v50,
          pdwTypeb);
      v51 = v77;
      if ( v77 )
      {
        v52 = *(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, __int64, __int64))(*(_QWORD *)v77 + 112LL);
        v81 = *(struct Windows::Foundation::Collections::IPropertySet **)v75;
        v53 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v81) + 24);
        v81 = v78;
        v54 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v89, &v81) + 24);
        v81 = *v41;
        v55 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v90, &v81);
        v56 = v52(v51, *(_QWORD *)(v55 + 24), v54, v53);
        if ( v56 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA0,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchfactsapptask.cpp",
            (const char *)(unsigned int)v56,
            pdwTypeb);
      }
      RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<27,long>(0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77, v57, v58);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v59, v60);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v75);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v78);
    }
    wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v91, 0);
  }
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v79);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v82);
  RetailDemoTelemetry::LaunchLaunchFactsApp::~LaunchLaunchFactsApp((RetailDemoTelemetry::LaunchLaunchFactsApp *)v91);
}

```

## disassembly

```asm
0x180027b20  mov     [rsp+arg_8], rbx
0x180027b25  mov     [rsp+arg_10], rsi
0x180027b2a  push    rdi
0x180027b2b  push    r12
0x180027b2d  push    r13
0x180027b2f  push    r14
0x180027b31  push    r15
0x180027b33  sub     rsp, 270h
0x180027b3a  mov     rax, cs:__security_cookie
0x180027b41  xor     rax, rsp
0x180027b44  mov     [rsp+298h+var_38], rax
0x180027b4c  mov     r13, rcx
0x180027b4f  mov     [rsp+298h+var_1F8], rcx
0x180027b57  xor     r15d, r15d
0x180027b5a  mov     [rsp+298h+var_250], r15d
0x180027b5f  mov     [rsp+298h+var_228], r15d
0x180027b64  mov     [rsp+298h+var_208], 4
0x180027b6f  lea     rax, [rsp+298h+var_208]
0x180027b77  mov     [rsp+298h+pcbData], rax; pcbData
0x180027b7c  lea     rax, [rsp+298h+var_228]
0x180027b81  mov     [rsp+298h+pvData], rax; pvData
0x180027b86  mov     [rsp+298h+pdwType], r15; int
0x180027b8b  mov     r9d, 20000010h; dwFlags
0x180027b91  lea     r8, ?c_retailDemoValueIdleTimeout@@3QBGB; "IdleTimeoutInSeconds"
0x180027b98  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027b9f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180027ba6  call    cs:__imp_RegGetValueW
0x180027bac  test    eax, eax
0x180027bae  jz      short loc_180027BB8
0x180027bb0  mov     [rsp+298h+var_228], 78h ; 'x'
0x180027bb8  lea     rdx, aLaunchlaunchfa; "LaunchLaunchFactsApp"
0x180027bbf  lea     rcx, [rsp+298h+var_188]; struct wil::details::IFailureCallback *
0x180027bc7  call    ??0?$ActivityBase@VRetailDemoLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180027bcc  lea     rax, ??_7LaunchLaunchFactsApp@RetailDemoTelemetry@@6B@; const RetailDemoTelemetry::LaunchLaunchFactsApp::`vftable'
0x180027bd3  mov     [rsp+298h+var_188], rax
0x180027bdb  lea     r12, [r13+58h]
0x180027bdf  mov     [rsp+298h+var_220], r12
0x180027be4  mov     r8d, [rsp+298h+var_228]; unsigned int
0x180027be9  mov     dl, [r12]; bool
0x180027bed  lea     rcx, [rsp+298h+var_188]; this
0x180027bf5  call    ?StartActivity@LaunchLaunchFactsApp@RetailDemoTelemetry@@QEAAX_NK@Z; RetailDemoTelemetry::LaunchLaunchFactsApp::StartActivity(bool,ulong)
0x180027bfa  nop
0x180027bfb  mov     [rsp+298h+var_218], r15
0x180027c03  mov     rcx, [r13+40h]
0x180027c07  mov     rax, [rcx]
0x180027c0a  mov     [rsp+298h+var_218], r15
0x180027c12  lea     rdx, [rsp+298h+var_218]
0x180027c1a  mov     rax, [rax+60h]
0x180027c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c23  mov     rcx, [rsp+298h]; this
0x180027c2b  test    eax, eax
0x180027c2d  jns     short loc_180027C44
0x180027c2f  mov     r9d, eax; char *
0x180027c32  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027c39  mov     edx, 43h ; 'C'; void *
0x180027c3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027c44  mov     [rsp+298h+var_230], r15
0x180027c49  mov     rcx, [rsp+298h+var_218]
0x180027c51  mov     rax, [rcx]
0x180027c54  mov     [rsp+298h+var_230], r15
0x180027c59  lea     rdx, [rsp+298h+var_230]
0x180027c5e  mov     rax, [rax+48h]
0x180027c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c67  mov     esi, 1
0x180027c6c  cmp     eax, esi
0x180027c6e  jnz     short loc_180027C7C
0x180027c70  mov     ecx, esi
0x180027c72  call    ??$HandleEvent@$0BL@J@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAXJ@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<27,long>(long)
0x180027c77  jmp     loc_180028474
0x180027c7c  mov     rcx, [rsp+298h]; HKEY
0x180027c84  test    eax, eax
0x180027c86  jns     short loc_180027C9D
0x180027c88  mov     r9d, eax; char *
0x180027c8b  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027c92  mov     edx, 4Ch ; 'L'; void *
0x180027c97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027c9d  mov     [rsp+298h+var_250], r15d
0x180027ca2  lea     rax, [rsp+298h+var_250]
0x180027ca7  mov     [rsp+298h+pdwType], rax; int
0x180027cac  lea     r8, aDisabledft; "DisableDFT"
0x180027cb3  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027cba  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180027cbf  mov     r14d, [rsp+298h+var_250]
0x180027cc4  test    r14d, r14d
0x180027cc7  jnz     loc_180028383
0x180027ccd  mov     [rsp+298h+var_240], r15
0x180027cd2  mov     rdi, [rsp+298h+var_230]
0x180027cd7  mov     rax, [rdi]
0x180027cda  mov     rbx, [rax+18h]
0x180027cde  xor     edx, edx
0x180027ce0  lea     rcx, [rsp+298h+var_240]
0x180027ce5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180027cea  lea     rdx, [rsp+298h+var_240]
0x180027cef  mov     rcx, rdi
0x180027cf2  mov     rax, rbx
0x180027cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cfa  mov     rcx, [rsp+298h]; this
0x180027d02  test    eax, eax
0x180027d04  jns     short loc_180027D19
0x180027d06  mov     r9d, eax; char *
0x180027d09  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027d10  lea     edx, [r14+55h]; void *
0x180027d14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027d19  mov     rax, [rsp+298h+var_240]
0x180027d1e  mov     [rsp+298h+var_210], rax
0x180027d26  lea     rax, aMicrosoftRetai; "Microsoft-RetailDemo-ShouldLaunch"
0x180027d2d  mov     [rsp+298h+var_200], rax
0x180027d35  lea     r8, [rsp+298h+var_210]
0x180027d3d  lea     rdx, [rsp+298h+var_200]
0x180027d45  lea     rcx, [rsp+298h+var_250]
0x180027d4a  call    ??$MakeOrThrow@VRDXAppServiceConnection@@AEAPEBGAEAPEBG@wil@@YA?AV?$ComPtr@VRDXAppServiceConnection@@@WRL@Microsoft@@AEAPEBG0@Z; wil::MakeOrThrow<RDXAppServiceConnection,ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x180027d4f  mov     rbx, [rax]
0x180027d52  mov     [rax], r15
0x180027d55  mov     [rsp+298h+var_200], rbx
0x180027d5d  mov     rcx, qword ptr [rsp+298h+var_250]
0x180027d62  test    rcx, rcx
0x180027d65  jz      short loc_180027D72
0x180027d67  mov     qword ptr [rsp+298h+var_250], r15
0x180027d6c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRDXAppServiceConnection@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRDXAppServiceConnection,Microsoft::WRL::FtmBase>::Release(void)
0x180027d71  nop
0x180027d72  mov     rax, [rbx]
0x180027d75  mov     rcx, rbx
0x180027d78  mov     rax, [rax+18h]
0x180027d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d81  mov     rcx, [rsp+298h]; this
0x180027d89  test    eax, eax
0x180027d8b  jns     short loc_180027DA1
0x180027d8d  mov     r9d, eax; char *
0x180027d90  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027d97  mov     edx, 59h ; 'Y'; void *
0x180027d9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027da1  mov     [rsp+298h+ppv], r15
0x180027da6  mov     rax, [rbx]
0x180027da9  mov     r10, [rax+38h]
0x180027dad  mov     [rsp+298h+ppv], r15
0x180027db2  mov     rax, [r13+30h]
0x180027db6  test    rax, rax
0x180027db9  jz      short loc_180027DC0
0x180027dbb  mov     r8, [rax]
0x180027dbe  jmp     short loc_180027DC3
0x180027dc0  mov     r8, r15
0x180027dc3  lea     rax, [rsp+298h+ppv]
0x180027dc8  mov     [rsp+298h+pdwType], rax; int
0x180027dcd  lea     r9, _GUID_8d503cec_9aa3_4e68_9559_9de63e372ce4
0x180027dd4  lea     rdx, aShouldlaunch; "ShouldLaunch"
0x180027ddb  mov     rcx, rbx
0x180027dde  mov     rax, r10
0x180027de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027de6  mov     rcx, [rsp+298h]; this
0x180027dee  test    eax, eax
0x180027df0  jns     short loc_180027E06
0x180027df2  mov     r9d, eax; char *
0x180027df5  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027dfc  mov     edx, 5Bh ; '['; void *
0x180027e01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027e06  mov     [rsp+298h+var_238], r15
0x180027e0b  mov     rcx, [rsp+298h+ppv]
0x180027e10  mov     rax, [rcx]
0x180027e13  mov     [rsp+298h+var_238], r15
0x180027e18  lea     rdx, [rsp+298h+var_238]
0x180027e1d  mov     rax, [rax+30h]
0x180027e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e26  mov     rcx, [rsp+298h]; this
0x180027e2e  test    eax, eax
0x180027e30  jns     short loc_180027E46
0x180027e32  mov     r9d, eax; char *
0x180027e35  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027e3c  mov     edx, 5Dh ; ']'; void *
0x180027e41  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027e46  mov     rdx, [rsp+298h+var_238]; struct Windows::Foundation::Collections::IPropertySet *
0x180027e4b  lea     rcx, [rsp+298h+var_210]; this
0x180027e53  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x180027e58  nop
0x180027e59  mov     [rsp+298h+var_258], sil
0x180027e5e  mov     [rsp+298h+var_1D8], r15
0x180027e66  mov     r9d, 6; unsigned int
0x180027e6c  lea     r8d, [r9+1]; unsigned int
0x180027e70  lea     rdx, aLaunch; "Launch"
0x180027e77  lea     rcx, [rsp+298h+hstringHeader]; hstringHeader
0x180027e7f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027e84  nop
0x180027e85  mov     [rsp+298h+var_250], 3
0x180027e8d  lea     r9, [rsp+298h+var_258]
0x180027e92  mov     rdx, [rsp+298h+var_1D8]; HSTRING
0x180027e9a  lea     rcx, [rsp+298h+var_210]; this
0x180027ea2  call    ??$GetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAE@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uchar *),uchar *)
0x180027ea7  test    eax, eax
0x180027ea9  js      short loc_180027EB5
0x180027eab  cmp     [rsp+298h+var_258], r15b
0x180027eb0  mov     al, sil
0x180027eb3  jz      short loc_180027EB8
0x180027eb5  mov     al, r15b
0x180027eb8  test    al, al
0x180027eba  cmovnz  r14d, esi
0x180027ebe  mov     rcx, [rsp+298h+var_210]
0x180027ec6  test    rcx, rcx
0x180027ec9  jz      short loc_180027ED8
0x180027ecb  mov     rax, [rcx]
0x180027ece  mov     rax, [rax+10h]
0x180027ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ed7  nop
0x180027ed8  lea     rcx, [rsp+298h+var_238]
0x180027edd  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180027ee2  nop
0x180027ee3  lea     rcx, [rsp+298h+ppv]
0x180027ee8  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180027eed  nop
0x180027eee  lea     rcx, [rsp+298h+var_200]
0x180027ef6  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180027efb  nop
0x180027efc  lea     rcx, [rsp+298h+var_240]
0x180027f01  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180027f06  nop
0x180027f07  jmp     short loc_180027F22
0x180027f09  xor     r15d, r15d
0x180027f0c  lea     esi, [r15+1]
0x180027f10  mov     r14d, [rsp+298h+var_250]
0x180027f15  mov     r13, [rsp+298h+var_1F8]
0x180027f1d  mov     r12, [rsp+298h+var_220]
0x180027f22  test    r14d, r14d
0x180027f25  jnz     loc_180028383
0x180027f2b  mov     [rsp+298h+var_238], r15
0x180027f30  mov     qword ptr [rsp+298h+var_250], r15
0x180027f35  cmp     [r12], r15b
0x180027f39  jz      short loc_180027FAD
0x180027f3b  lea     rax, [rsp+298h+var_238]
0x180027f40  mov     qword ptr [rsp+298h+hstringHeader.Reserved], rax
0x180027f48  mov     qword ptr [rsp+298h+hstringHeader.Reserved+8], r15
0x180027f50  mov     byte ptr [rsp+298h+hstringHeader.Reserved+10h], sil
0x180027f58  lea     rax, [rsp+298h+hstringHeader.Reserved+8]
0x180027f60  mov     [rsp+298h+pvData], rax
0x180027f65  lea     r9d, [r14+0Bh]
0x180027f69  lea     r8, aInteractive; "Interactive"
0x180027f70  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180027f75  mov     rcx, [rsp+298h]; this
0x180027f7d  test    eax, eax
0x180027f7f  jns     short loc_180027F96
0x180027f81  mov     r9d, eax; char *
0x180027f84  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027f8b  mov     edx, 81h; void *
0x180027f90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027f96  lea     rcx, [rsp+298h+hstringHeader]
0x180027f9e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180027fa3  mov     ebx, 80000000h
0x180027fa8  jmp     loc_180028097
0x180027fad  mov     rcx, [rsp+298h+var_230]
0x180027fb2  mov     rax, [rcx]
0x180027fb5  lea     rdx, [rsp+298h+var_250]
0x180027fba  mov     qword ptr [rsp+298h+hstringHeader.Reserved], rdx
0x180027fc2  mov     qword ptr [rsp+298h+hstringHeader.Reserved+8], r15
0x180027fca  mov     byte ptr [rsp+298h+hstringHeader.Reserved+10h], sil
0x180027fd2  lea     rdx, [rsp+298h+hstringHeader.Reserved+8]
0x180027fda  mov     rax, [rax+40h]
0x180027fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fe3  mov     edi, eax
0x180027fe5  lea     rcx, [rsp+298h+hstringHeader]
0x180027fed  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180027ff2  mov     ebx, 80000000h
0x180027ff7  lea     ecx, [rdi+rbx]
0x180027ffa  test    ebx, ecx
0x180027ffc  jnz     short loc_180028009
0x180027ffe  cmp     edi, 800700E8h
0x180028004  mov     al, sil
0x180028007  jnz     short loc_18002800C
0x180028009  mov     al, r15b
0x18002800c  mov     rcx, [rsp+298h]; this
0x180028014  test    al, al
0x180028016  jz      short loc_18002802D
0x180028018  mov     r9d, edi; char *
0x18002801b  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180028022  mov     edx, 86h; void *
0x180028027  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002802d  lea     rax, [rsp+298h+var_238]
0x180028032  mov     qword ptr [rsp+298h+hstringHeader.Reserved], rax
0x18002803a  mov     qword ptr [rsp+298h+hstringHeader.Reserved+8], r15
0x180028042  mov     byte ptr [rsp+298h+hstringHeader.Reserved+10h], sil
0x18002804a  lea     rax, [rsp+298h+hstringHeader.Reserved+8]
0x180028052  mov     [rsp+298h+pvData], rax
0x180028057  mov     r9d, 4
0x18002805d  lea     r8, aIdle; "Idle"
0x180028064  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180028069  mov     rcx, [rsp+298h]; this
0x180028071  test    eax, eax
0x180028073  jns     short loc_18002808A
0x180028075  mov     r9d, eax; char *
0x180028078  lea     r8, aPcshellShellRe_24; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002807f  mov     edx, 87h; void *
0x180028084  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002808a  lea     rcx, [rsp+298h+hstringHeader]
0x180028092  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180028097  mov     rax, qword ptr [rsp+298h+var_250]
0x18002809c  test    rax, rax
0x18002809f  jnz     loc_180028191
0x1800280a5  mov     rcx, [rsp+298h+var_230]
0x1800280aa  mov     rax, [rcx]
0x1800280ad  lea     rdx, [rsp+298h+var_250]
0x1800280b2  mov     qword ptr [rsp+298h+hstringHeader.Reserved], rdx
0x1800280ba  mov     qword ptr [rsp+298h+hstringHeader.Reserved+8], r15
0x1800280c2  mov     byte ptr [rsp+298h+hstringHeader.Reserved+10h], sil
0x1800280ca  lea     rdx, [rsp+298h+hstringHeader.Reserved+8]
  ... truncated ...
```
