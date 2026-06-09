# CloseIdleAppTask::Execute(void)

- ea: `0x180020240`
- end: `0x180020ae7`
- name: `?Execute@CloseIdleAppTask@@EEAAXXZ`
- size: `2215`
- prototype: `void __fastcall(CloseIdleAppTask *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000e3bc`
- `0x1800106c4`
- `0x18001094c`
- `0x180013988`
- `0x1800181b0`
- `0x18001e19c`
- `0x18001e55c`
- `0x18001ff9c`
- `0x180020208`
- `0x180020240`
- `0x180020b00`
- `0x180020bc0`
- `0x18002e5b8`
- `0x180030dc0`
- `0x180050010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18002042c`
- `SHCORE!IUnknown_QueryService` at `0x1800204c8`
- `SHCORE!IUnknown_QueryService` at `0x18002042c`
- `SHCORE!IUnknown_QueryService` at `0x1800204c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800203e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002047f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002061c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800203e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002047f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002061c`

## string_xrefs

- `0x180020512`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x1800202d2`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x18002031c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x180020365`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x1800203a7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x1800203f7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x180020440`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x180020493`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`
- `0x18002051e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\closeidleapptask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall CloseIdleAppTask::Execute(CloseIdleAppTask *this)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, __int64 *); // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 **); // rbx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  HRESULT Instance; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  HRESULT v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  HRESULT v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  HKEY v26; // rcx
  char v27; // r14
  int v28; // edi
  int v29; // ebx
  __int64 v30; // rdx
  _QWORD *UserAgent; // rax
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  HRESULT v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 LaunchOptionFromPrelaunchOptions; // r9
  int v45; // eax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, __int64 **); // rbx
  int v48; // eax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // r8
  int v55; // eax
  __int64 v56; // rdx
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rdx
  __int64 v77; // r8
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  char v81; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v82[3]; // [rsp+51h] [rbp-AFh] BYREF
  int v83; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID v84; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v85; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v86; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v87; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v88; // [rsp+78h] [rbp-88h] BYREF
  __int64 v89; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v90; // [rsp+88h] [rbp-78h] BYREF
  int v91; // [rsp+90h] [rbp-70h] BYREF
  int v92; // [rsp+94h] [rbp-6Ch] BYREF
  IUnknown *punk; // [rsp+98h] [rbp-68h] BYREF
  __int64 v94; // [rsp+A0h] [rbp-60h] BYREF
  void *v95; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v96[2]; // [rsp+B0h] [rbp-50h] BYREF
  char v97; // [rsp+C0h] [rbp-40h]
  void *ppvOut; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v99; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v100; // [rsp+D8h] [rbp-28h] BYREF
  char v101; // [rsp+E8h] [rbp-18h]
  __int128 v102; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v103[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v103);
  v103[0] = &RetailDemoTelemetry::CloseIdleApplication::`vftable';
  RetailDemoTelemetry::CloseIdleApplication::StartActivity((RetailDemoTelemetry::CloseIdleApplication *)v103);
  v94 = 0;
  v2 = *((_QWORD *)this + 8);
  v3 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94, v4, v5);
  v6 = v3(v2, &v94);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v87 = 0;
  v9 = v94;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v94 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87, v7, v8);
  v11 = v10(v9, &v87);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  v90 = 0;
  v12 = *v87;
  *(_QWORD *)&v100 = &v90;
  *((_QWORD *)&v100 + 1) = 0;
  v101 = 1;
  v13 = (*(__int64 (__fastcall **)(__int64 *, char *))(v12 + 48))(v87, (char *)&v100 + 8);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v13,
      ppv);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v100);
  v92 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v87 + 56))(v87, &v92);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v14,
      ppv);
  punk = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v15, v16);
  Instance = CoCreateInstance(
               &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
               0,
               4u,
               &GUID_00000000_0000_0000_c000_000000000046,
               (LPVOID *)&punk);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v18, v19);
  v20 = IUnknown_QueryService(
          punk,
          (const GUID *const)&SID_ImmersiveApplicationArrayService,
          &GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a,
          &ppvOut);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v20,
      ppva);
  v86 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86, v21, v22);
  v23 = CoCreateInstance(
          &GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d,
          0,
          1u,
          &GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e,
          &v86);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v23,
      ppvb);
  v95 = 0;
  v91 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95, v24, v25);
  if ( IUnknown_QueryService(
         punk,
         &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a,
         &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a,
         &v95) < 0
    || (*(int (__fastcall **)(void *, int *))(*(_QWORD *)v95 + 24LL))(v95, &v91) < 0
    || (v27 = 1, v91 != 1) )
  {
    v27 = 0;
  }
  v28 = v92 & 4;
  v29 = v92 & 2;
  v88 = 0;
  if ( (int)SHRegGetDWORD(
              v26,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
              L"ActiveScreenTopology",
              &v88) >= 0 )
  {
    UserAgent = (_QWORD *)RetailDemoUtil::GetUserAgent(&v89, 0);
    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(*(_QWORD *)*UserAgent + 192LL))(
            *UserAgent,
            v88,
            &v88);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v32,
        ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89, v33, v34);
  }
  v99 = 0;
  v81 = 0;
  LOBYTE(v30) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
    v30);
  v35 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, char *))(*(_QWORD *)v86 + 64LL))(v86, v90, &v81);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v35,
      ppvb);
  if ( !v81 )
  {
LABEL_41:
    if ( v29 || v28 )
      goto LABEL_70;
    goto LABEL_43;
  }
  if ( v29 || v28 )
  {
    v84 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84, v36, v37);
    v38 = CoCreateInstance(
            &GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d,
            0,
            1u,
            &GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e,
            &v84);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v38,
        ppvb);
    v102 = 0;
    v39 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int128 *))(*(_QWORD *)v84 + 48LL))(v84, v87, &v102);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v39,
        ppvb);
    v83 = 0;
    v40 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v87 + 176))(v87, &v83);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v40,
        ppvb);
    LODWORD(v85) = 0;
    v41 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v87 + 96))(v87, &v85);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v41,
        ppvb);
    LaunchOptionFromPrelaunchOptions = (unsigned int)RetailDemoUtil::GetLaunchOptionFromPrelaunchOptions(
                                                       (unsigned int)v85,
                                                       1);
    if ( (v83 & 2) != 0 )
    {
      ppvb = 0;
      v45 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, const wchar_t *, __int64))(*(_QWORD *)v84 + 40LL))(
              v84,
              v90,
              L"Hub",
              LaunchOptionFromPrelaunchOptions);
      if ( v45 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
          (const char *)(unsigned int)v45,
          0);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84, v42, v43);
    goto LABEL_41;
  }
  (*(void (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v86 + 32LL))(v86, v90);
LABEL_43:
  v85 = 0;
  v46 = v94;
  v47 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v94 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85, v36, v37);
  v48 = v47(v46, &v85);
  if ( v48 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v48,
      ppvb);
  v89 = 0;
  v49 = *v85;
  *(_QWORD *)&v100 = &v89;
  *((_QWORD *)&v100 + 1) = 0;
  v101 = 1;
  v50 = (*(__int64 (__fastcall **)(__int64 *, char *))(v49 + 48))(v85, (char *)&v100 + 8);
  if ( v50 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v50,
      ppvb);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v100);
  *(_QWORD *)&v102 = 0;
  v82[0] = 0;
  LOBYTE(v51) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
    v51);
  v52 = (*(__int64 (__fastcall **)(LPVOID, __int64, _BYTE *))(*(_QWORD *)v86 + 64LL))(v86, v89, v82);
  if ( v52 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
      (const char *)(unsigned int)v52,
      ppvb);
  if ( v82[0] )
  {
    if ( v27 )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v86 + 32LL))(v86, v89);
    v83 = 0;
    v55 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v85 + 176))(v85, &v83);
    if ( v55 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v55,
        ppvb);
    v84 = 0;
    v96[1] = 0;
    v97 = 1;
    v96[0] = &v84;
    if ( (v83 & 2) != 0 )
    {
      if ( v27 )
      {
        v57 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v56, L"Hub");
        if ( v57 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x94,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
            (const char *)(unsigned int)v57,
            ppvb);
      }
      else
      {
        v58 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v56, L"Interactive");
        if ( v58 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x98,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
            (const char *)(unsigned int)v58,
            ppvb);
      }
    }
    else
    {
      v59 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v56, &qword_180057BE0);
      if ( v59 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9D,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
          (const char *)(unsigned int)v59,
          ppvb);
    }
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v96);
    v100 = 0;
    v60 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int128 *))(*(_QWORD *)v86 + 48LL))(v86, v85, &v100);
    if ( v60 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v60,
        ppvb);
    v61 = (*(__int64 (__fastcall **)(LPVOID, __int64, LPVOID, __int64))(*(_QWORD *)v86 + 40LL))(v86, v89, v84, 1);
    if ( v61 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\closeidleapptask.cpp",
        (const char *)(unsigned int)v61,
        3000);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v84);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v53, v54);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v89);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85, v62, v63);
LABEL_70:
  RetailDemoTelemetry::CloseIdleApplication::Stop((RetailDemoTelemetry::CloseIdleApplication *)v103, v90, v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99, v64, v65);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95, v66, v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86, v68, v69);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v70, v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk, v72, v73);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v90);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87, v74, v75);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94, v76, v77);
  RetailDemoTelemetry::CloseIdleApplication::~CloseIdleApplication((RetailDemoTelemetry::CloseIdleApplication *)v103);
}

```

## disassembly

```asm
0x180020240  mov     [rsp-8+arg_8], rbx
0x180020245  mov     [rsp-8+arg_10], rsi
0x18002024a  push    rbp
0x18002024b  push    rdi
0x18002024c  push    r12
0x18002024e  push    r14
0x180020250  push    r15
0x180020252  lea     rbp, [rsp-160h]
0x18002025a  sub     rsp, 260h
0x180020261  mov     rax, cs:__security_cookie
0x180020268  xor     rax, rsp
0x18002026b  mov     [rbp+180h+var_30], rax
0x180020272  mov     r15, rcx
0x180020275  lea     rdx, aCloseidleappli; "CloseIdleApplication"
0x18002027c  lea     rcx, [rbp+180h+var_180]; struct wil::details::IFailureCallback *
0x180020280  call    ??0?$ActivityBase@VRetailDemoLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020285  lea     rax, ??_7CloseIdleApplication@RetailDemoTelemetry@@6B@; const RetailDemoTelemetry::CloseIdleApplication::`vftable'
0x18002028c  mov     [rbp+180h+var_180], rax
0x180020290  lea     rcx, [rbp+180h+var_180]; this
0x180020294  call    ?StartActivity@CloseIdleApplication@RetailDemoTelemetry@@QEAAXXZ; RetailDemoTelemetry::CloseIdleApplication::StartActivity(void)
0x180020299  nop
0x18002029a  xor     r12d, r12d
0x18002029d  mov     [rbp+180h+var_1E0], r12
0x1800202a1  mov     rdi, [r15+40h]
0x1800202a5  mov     rax, [rdi]
0x1800202a8  mov     rbx, [rax+60h]
0x1800202ac  lea     rcx, [rbp+180h+var_1E0]
0x1800202b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800202b5  lea     rdx, [rbp+180h+var_1E0]
0x1800202b9  mov     rcx, rdi
0x1800202bc  mov     rax, rbx
0x1800202bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202c4  mov     rcx, [rbp+188h]; this
0x1800202cb  test    eax, eax
0x1800202cd  jns     short loc_1800202E4
0x1800202cf  mov     r9d, eax; char *
0x1800202d2  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800202d9  lea     edx, [r12+29h]; void *
0x1800202de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800202e4  mov     [rsp+280h+var_210], r12
0x1800202e9  mov     rdi, [rbp+180h+var_1E0]
0x1800202ed  mov     rax, [rdi]
0x1800202f0  mov     rbx, [rax+38h]
0x1800202f4  lea     rcx, [rsp+280h+var_210]
0x1800202f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800202fe  lea     rdx, [rsp+280h+var_210]
0x180020303  mov     rcx, rdi
0x180020306  mov     rax, rbx
0x180020309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002030e  mov     rcx, [rbp+188h]; this
0x180020315  test    eax, eax
0x180020317  jns     short loc_18002032E
0x180020319  mov     r9d, eax; char *
0x18002031c  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180020323  mov     edx, 2Bh ; '+'; void *
0x180020328  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002032e  mov     [rbp+180h+var_1F8], r12
0x180020332  mov     rcx, [rsp+280h+var_210]
0x180020337  mov     rax, [rcx]
0x18002033a  lea     rdx, [rbp+180h+var_1F8]
0x18002033e  mov     qword ptr [rbp+180h+var_1A8], rdx
0x180020342  mov     qword ptr [rbp+180h+var_1A8+8], r12
0x180020346  mov     [rbp+180h+var_198], 1
0x18002034a  lea     rdx, [rbp+180h+var_1A8+8]
0x18002034e  mov     rax, [rax+30h]
0x180020352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020357  mov     rcx, [rbp+188h]; this
0x18002035e  test    eax, eax
0x180020360  jns     short loc_180020377
0x180020362  mov     r9d, eax; char *
0x180020365  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002036c  mov     edx, 2Dh ; '-'; void *
0x180020371  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020377  lea     rcx, [rbp+180h+var_1A8]
0x18002037b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180020380  mov     [rbp+180h+var_1EC], r12d
0x180020384  mov     rcx, [rsp+280h+var_210]
0x180020389  mov     rax, [rcx]
0x18002038c  lea     rdx, [rbp+180h+var_1EC]
0x180020390  mov     rax, [rax+38h]
0x180020394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020399  mov     rcx, [rbp+188h]; this
0x1800203a0  test    eax, eax
0x1800203a2  jns     short loc_1800203B9
0x1800203a4  mov     r9d, eax; char *
0x1800203a7  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800203ae  mov     edx, 2Fh ; '/'; void *
0x1800203b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800203b9  mov     [rbp+180h+punk], r12
0x1800203bd  lea     rcx, [rbp+180h+punk]
0x1800203c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800203c6  lea     rax, [rbp+180h+punk]
0x1800203ca  mov     [rsp+280h+ppv], rax; int
0x1800203cf  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800203d6  xor     edx, edx; pUnkOuter
0x1800203d8  lea     r8d, [rdx+4]; dwClsContext
0x1800203dc  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x1800203e3  call    cs:__imp_CoCreateInstance
0x1800203e9  mov     rcx, [rbp+188h]; this
0x1800203f0  test    eax, eax
0x1800203f2  jns     short loc_180020409
0x1800203f4  mov     r9d, eax; char *
0x1800203f7  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800203fe  mov     edx, 32h ; '2'; void *
0x180020403  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020409  mov     [rbp+180h+ppvOut], r12
0x18002040d  lea     rcx, [rbp+180h+ppvOut]
0x180020411  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020416  lea     r9, [rbp+180h+ppvOut]; ppvOut
0x18002041a  lea     r8, _GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a; riid
0x180020421  lea     rdx, SID_ImmersiveApplicationArrayService; guidService
0x180020428  mov     rcx, [rbp+180h+punk]; punk
0x18002042c  call    cs:__imp_IUnknown_QueryService
0x180020432  mov     rcx, [rbp+188h]; this
0x180020439  test    eax, eax
0x18002043b  jns     short loc_180020452
0x18002043d  mov     r9d, eax; char *
0x180020440  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180020447  mov     edx, 34h ; '4'; void *
0x18002044c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020452  mov     [rsp+280h+var_218], r12
0x180020457  lea     rcx, [rsp+280h+var_218]
0x18002045c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020461  lea     rax, [rsp+280h+var_218]
0x180020466  mov     [rsp+280h+ppv], rax; int
0x18002046b  lea     r9, _GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e; riid
0x180020472  xor     edx, edx; pUnkOuter
0x180020474  lea     r8d, [rdx+1]; dwClsContext
0x180020478  lea     rcx, _GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d; rclsid
0x18002047f  call    cs:__imp_CoCreateInstance
0x180020485  mov     rcx, [rbp+188h]; this
0x18002048c  test    eax, eax
0x18002048e  jns     short loc_1800204A5
0x180020490  mov     r9d, eax; char *
0x180020493  lea     r8, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002049a  mov     edx, 36h ; '6'; void *
0x18002049f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800204a5  mov     [rbp+180h+var_1D8], r12
0x1800204a9  mov     [rbp+180h+var_1F0], r12d
0x1800204ad  lea     rcx, [rbp+180h+var_1D8]
0x1800204b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800204b6  lea     r9, [rbp+180h+var_1D8]; ppvOut
0x1800204ba  lea     rdx, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a; guidService
0x1800204c1  mov     r8, rdx; riid
0x1800204c4  mov     rcx, [rbp+180h+punk]; punk
0x1800204c8  call    cs:__imp_IUnknown_QueryService
0x1800204ce  test    eax, eax
0x1800204d0  js      short loc_1800204F3
0x1800204d2  mov     rcx, [rbp+180h+var_1D8]
0x1800204d6  mov     rax, [rcx]
0x1800204d9  lea     rdx, [rbp+180h+var_1F0]
0x1800204dd  mov     rax, [rax+18h]
0x1800204e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204e6  test    eax, eax
0x1800204e8  js      short loc_1800204F3
0x1800204ea  cmp     [rbp+180h+var_1F0], 1
0x1800204ee  mov     r14b, 1
0x1800204f1  jz      short loc_1800204F6
0x1800204f3  mov     r14b, r12b
0x1800204f6  mov     ebx, [rbp+180h+var_1EC]
0x1800204f9  mov     edi, ebx
0x1800204fb  and     edi, 4
0x1800204fe  and     ebx, 2
0x180020501  mov     [rsp+280h+var_208], r12d
0x180020506  lea     r9, [rsp+280h+var_208]; unsigned int *
0x18002050b  lea     r8, ?c_retailDemoValueActiveScreenTopology@@3QBGB; "ActiveScreenTopology"
0x180020512  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180020519  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002051e  lea     rsi, aPcshellShellRe_2; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180020525  test    eax, eax
0x180020527  js      short loc_180020575
0x180020529  xor     edx, edx
0x18002052b  lea     rcx, [rbp+180h+var_200]
0x18002052f  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x180020534  nop
0x180020535  mov     rcx, [rax]
0x180020538  mov     rax, [rcx]
0x18002053b  lea     r8, [rsp+280h+var_208]
0x180020540  mov     edx, [rsp+280h+var_208]
0x180020544  mov     rax, [rax+0C0h]
0x18002054b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020550  mov     rcx, [rbp+188h]; this
0x180020557  test    eax, eax
0x180020559  jns     short loc_18002056C
0x18002055b  mov     r9d, eax; char *
0x18002055e  mov     r8, rsi; unsigned int
0x180020561  mov     edx, 44h ; 'D'; void *
0x180020566  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002056b  nop
0x18002056c  lea     rcx, [rbp+180h+var_200]
0x180020570  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020575  mov     [rbp+180h+var_1B0], r12
0x180020579  mov     [rsp+280h+var_230], r12b
0x18002057e  mov     dl, 1
0x180020580  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x180020587  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002058c  mov     rcx, [rsp+280h+var_218]
0x180020591  mov     rax, [rcx]
0x180020594  lea     r8, [rsp+280h+var_230]
0x180020599  mov     rdx, [rbp+180h+var_1F8]
0x18002059d  mov     rax, [rax+40h]
0x1800205a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205a6  mov     rcx, [rbp+188h]; this
0x1800205ad  test    eax, eax
0x1800205af  jns     short loc_1800205C2
0x1800205b1  mov     r9d, eax; char *
0x1800205b4  mov     r8, rsi; unsigned int
0x1800205b7  mov     edx, 4Dh ; 'M'; void *
0x1800205bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800205c2  cmp     [rsp+280h+var_230], r12b
0x1800205c7  jz      loc_18002075E
0x1800205cd  test    ebx, ebx
0x1800205cf  jnz     short loc_1800205EF
0x1800205d1  test    edi, edi
0x1800205d3  jnz     short loc_1800205EF
0x1800205d5  mov     rcx, [rsp+280h+var_218]
0x1800205da  mov     rax, [rcx]
0x1800205dd  mov     rdx, [rbp+180h+var_1F8]
0x1800205e1  mov     rax, [rax+20h]
0x1800205e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205ea  jmp     loc_18002076E
0x1800205ef  mov     [rsp+280h+var_228], r12
0x1800205f4  lea     rcx, [rsp+280h+var_228]
0x1800205f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800205fe  lea     rax, [rsp+280h+var_228]
0x180020603  mov     [rsp+280h+ppv], rax; int
0x180020608  lea     r9, _GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e; riid
0x18002060f  xor     edx, edx; pUnkOuter
0x180020611  lea     r8d, [rdx+1]; dwClsContext
0x180020615  lea     rcx, _GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d; rclsid
0x18002061c  call    cs:__imp_CoCreateInstance
0x180020622  mov     rcx, [rbp+188h]; this
0x180020629  test    eax, eax
0x18002062b  jns     short loc_18002063E
0x18002062d  mov     r9d, eax; char *
0x180020630  mov     r8, rsi; unsigned int
0x180020633  mov     edx, 59h ; 'Y'; void *
0x180020638  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002063e  xorps   xmm0, xmm0
0x180020641  movups  [rbp+180h+var_190], xmm0
0x180020645  mov     rcx, [rsp+280h+var_228]
0x18002064a  mov     rax, [rcx]
0x18002064d  lea     r8, [rbp+180h+var_190]
0x180020651  mov     rdx, [rsp+280h+var_210]
0x180020656  mov     rax, [rax+30h]
0x18002065a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002065f  mov     rcx, [rbp+188h]; this
0x180020666  test    eax, eax
0x180020668  jns     short loc_18002067B
0x18002066a  mov     r9d, eax; char *
0x18002066d  mov     r8, rsi; unsigned int
0x180020670  mov     edx, 5Bh ; '['; void *
0x180020675  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002067b  mov     [rsp+280h+var_22C], r12d
0x180020680  mov     rcx, [rsp+280h+var_210]
0x180020685  mov     rax, [rcx]
0x180020688  lea     rdx, [rsp+280h+var_22C]
0x18002068d  mov     rax, [rax+0B0h]
0x180020694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020699  mov     rcx, [rbp+188h]; this
0x1800206a0  test    eax, eax
0x1800206a2  jns     short loc_1800206B5
0x1800206a4  mov     r9d, eax; char *
0x1800206a7  mov     r8, rsi; unsigned int
0x1800206aa  mov     edx, 5Eh ; '^'; void *
0x1800206af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800206b5  mov     dword ptr [rsp+280h+var_220], r12d
0x1800206ba  mov     rcx, [rsp+280h+var_210]
0x1800206bf  mov     rax, [rcx]
0x1800206c2  lea     rdx, [rsp+280h+var_220]
0x1800206c7  mov     rax, [rax+60h]
0x1800206cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206d0  mov     rcx, [rbp+188h]; this
0x1800206d7  test    eax, eax
0x1800206d9  jns     short loc_1800206EC
0x1800206db  mov     r9d, eax; char *
0x1800206de  mov     r8, rsi; unsigned int
0x1800206e1  mov     edx, 61h ; 'a'; void *
0x1800206e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800206ec  mov     edx, 1
0x1800206f1  mov     ecx, dword ptr [rsp+280h+var_220]
0x1800206f5  call    ?GetLaunchOptionFromPrelaunchOptions@RetailDemoUtil@@YA?AW4LaunchOptions@@W4RetailDemoPrelaunchOptions@@W42@@Z; RetailDemoUtil::GetLaunchOptionFromPrelaunchOptions(RetailDemoPrelaunchOptions,LaunchOptions)
0x1800206fa  mov     r9d, eax
0x1800206fd  test    byte ptr [rsp+280h+var_22C], 2
0x180020702  jz      short loc_180020754
0x180020704  mov     rcx, [rsp+280h+var_228]
0x180020709  mov     r8, [rcx]
0x18002070c  mov     rax, [r8+28h]
0x180020710  mov     [rsp+280h+var_248], r12b
0x180020715  lea     rdx, [rbp+180h+var_190]
0x180020719  mov     [rsp+280h+var_250], rdx
0x18002071e  mov     [rsp+280h+var_258], r12
0x180020723  mov     dword ptr [rsp+280h+ppv], r12d; int
0x180020728  lea     r8, aHub; "Hub"
0x18002072f  mov     rdx, [rbp+180h+var_1F8]
0x180020733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020738  mov     rcx, [rbp+188h]; this
0x18002073f  test    eax, eax
0x180020741  jns     short loc_180020754
0x180020743  mov     r9d, eax; char *
  ... truncated ...
```
