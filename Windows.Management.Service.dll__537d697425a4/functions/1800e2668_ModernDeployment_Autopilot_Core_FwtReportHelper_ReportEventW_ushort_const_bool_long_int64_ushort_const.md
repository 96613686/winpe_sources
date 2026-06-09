# ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(ushort const *,bool,long,__int64,ushort const *)

- ea: `0x1800e2668`
- end: `0x1800e31c6`
- name: `?ReportEventW@FwtReportHelper@Core@Autopilot@ModernDeployment@@SAJPEBG_NJ_J0@Z`
- size: `2910`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, int, __int64, const unsigned __int16 *)`
- caller_count: `17`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a6b70`
- `0x1800a7250`
- `0x1800adda8`
- `0x1800be494`
- `0x1800c4bc0`
- `0x1800ca2f8`
- `0x1800ca518`
- `0x1800d4020`
- `0x1800d7080`
- `0x1800da4dc`
- `0x1800ef150`
- `0x1801008f0`
- `0x180101190`
- `0x180101620`
- `0x180101c60`
- `0x180102520`
- `0x1801065c8`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067398`
- `0x180067e54`
- `0x18006b4a8`
- `0x18006b644`
- `0x18006e43c`
- `0x18006e608`
- `0x180077e54`
- `0x1800829ec`
- `0x180086044`
- `0x1800dae6c`
- `0x1800e20d0`
- `0x1800e2140`
- `0x1800e2254`
- `0x1800e2388`
- `0x1800e2518`
- `0x1800e2554`
- `0x1800e2590`
- `0x1800e2668`
- `0x1800e3250`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e303f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e303f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e2758`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800e2758`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e2708`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e2708`

## string_xrefs

- `0x1800e26d0`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2775`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e27df`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2861`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e290c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2981`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2a52`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2b3a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2c26`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2cf0`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2d5f`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2de0`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2e75`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2f07`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e2fb7`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e3189`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(
        const unsigned __int16 *a1,
        char a2,
        unsigned int a3,
        __int64 a4,
        RTL_SRWLOCK *a5)
{
  int ActivationFactory; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  _QWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64, _BYTE *); // rdi
  const wchar_t *v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v32; // rbx
  __int64 v33; // rax
  int v34; // eax
  unsigned int v35; // ebx
  __int64 v36; // rsi
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v44; // rbx
  __int64 v45; // rax
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // eax
  unsigned int v49; // ebx
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  unsigned int v53; // ebx
  int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // rax
  int v57; // eax
  unsigned int v58; // ebx
  __int64 v59; // rbx
  __int64 v60; // r9
  _QWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // r9
  unsigned __int64 v65; // r9
  int v66; // [rsp+20h] [rbp-148h]
  _BYTE v67[8]; // [rsp+30h] [rbp-138h] BYREF
  struct _FILETIME v68; // [rsp+38h] [rbp-130h] BYREF
  __int64 v69; // [rsp+40h] [rbp-128h] BYREF
  _QWORD *v70; // [rsp+48h] [rbp-120h] BYREF
  __int64 (__fastcall ***v71)(_QWORD, GUID *, struct _FILETIME *); // [rsp+50h] [rbp-118h] BYREF
  __int64 *v72; // [rsp+58h] [rbp-110h] BYREF
  RTL_SRWLOCK *v73; // [rsp+60h] [rbp-108h] BYREF
  __int64 *v74; // [rsp+68h] [rbp-100h] BYREF
  const unsigned __int16 *v75; // [rsp+70h] [rbp-F8h] BYREF
  __int64 v76; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v77; // [rsp+80h] [rbp-E8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v79; // [rsp+90h] [rbp-D8h] BYREF
  HSTRING_HEADER v80; // [rsp+98h] [rbp-D0h] BYREF
  HSTRING_HEADER v81; // [rsp+B8h] [rbp-B0h] BYREF
  __int128 hstringHeader; // [rsp+E0h] [rbp-88h] BYREF
  __int128 hstringHeader_16; // [rsp+F0h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v75 = a1;
  v79 = a5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    if ( a1 && *a1 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v68 = 0;
      v72 = 0;
      *((_QWORD *)&hstringHeader_16 + 1) = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)&hstringHeader,
        L"Windows.Foundation.PropertyValue",
        0x21u,
        0x20u);
      ActivationFactory = RoGetActivationFactory(
                            *((_QWORD *)&hstringHeader_16 + 1),
                            &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858,
                            &v72);
      v11 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v71 = 0;
        v12 = *v72;
        v71 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64 *, struct _FILETIME, __int64 (__fastcall ****)(_QWORD, GUID *, struct _FILETIME *)))(v12 + 168))(
                v72,
                SystemTimeAsFileTime,
                &v71);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v68 = 0;
          v15 = (**v71)(v71, &GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c, &v68);
          v16 = v15;
          if ( v15 >= 0 )
          {
            v70 = 0;
            SystemTimeAsFileTime = v68;
            v75 = *(const unsigned __int16 **)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                 &hstringHeader,
                                                 &v75)
                                             + 24);
            v17 = v70;
            v70 = 0;
            if ( v17 )
              (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
            v18 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::TelemetryEvent,ModernDeployment::Autopilot::Core::ITelemetryEvent,HSTRING__ *,Windows::Foundation::IReference<Windows::Foundation::DateTime> *>(
                    &v70,
                    &v75,
                    &SystemTimeAsFileTime);
            v19 = v18;
            if ( v18 >= 0 )
            {
              v69 = 0;
              v20 = *v70;
              v69 = 0;
              v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v20 + 64))(v70, &v69);
              v22 = v21;
              if ( v21 >= 0 )
              {
                v67[0] = 0;
                v23 = v69;
                v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v69 + 80LL);
                v25 = L"true";
                if ( !a2 )
                  v25 = L"false";
                v75 = v25;
                v26 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v75) + 24);
                v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &v80,
                        &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Status);
                v28 = v24(v23, *(_QWORD *)(v27 + 24), v26, v67);
                v29 = v28;
                if ( v28 >= 0 )
                {
                  hstringHeader = 0;
                  hstringHeader_16 = 0;
                  _snwprintf_s<16>(&hstringHeader, -1, L"0x%08X", a3);
                  v67[0] = 0;
                  v30 = v69;
                  v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v69 + 80LL);
                  v32 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                      &v80,
                                      (PCWSTR)&hstringHeader)
                                  + 24);
                  v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &v81,
                          &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Error_Code);
                  v34 = v31(v30, *(_QWORD *)(v33 + 24), v32, v67);
                  v35 = v34;
                  if ( v34 >= 0 )
                  {
                    if ( a4 <= 0 )
                      goto LABEL_49;
                    memset_0(&hstringHeader, 0, 0x40u);
                    _snwprintf_s<32>(&hstringHeader, -1, L"%lld", a4);
                    v67[0] = 0;
                    v36 = v69;
                    v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v69 + 80LL);
                    v38 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                        &v81,
                                        (PCWSTR)&hstringHeader)
                                    + 24);
                    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &v80,
                            &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Duration);
                    v40 = v37(v36, *(_QWORD *)(v39 + 24), v38, v67);
                    v41 = v40;
                    if ( v40 >= 0 )
                    {
LABEL_49:
                      if ( a5
                        && LOWORD(a5->Ptr)
                        && (v67[0] = 0,
                            v42 = v69,
                            v43 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v69 + 80LL),
                            v44 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v81, &v79)
                                            + 24),
                            v45 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                    &v80,
                                    &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Phases),
                            v46 = v43(v42, *(_QWORD *)(v45 + 24), v44, v67),
                            v47 = v46,
                            v46 < 0) )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x72,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\f"
                                        "wtreporthelper.cpp",
                          (const char *)(unsigned int)v46,
                          v66);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                        return v47;
                      }
                      else
                      {
                        v73 = 0;
                        v48 = Windows::Management::Setup::VectorWrapperT<ModernDeployment::Autopilot::Core::TelemetryEvent,ModernDeployment::Autopilot::Core::ITelemetryEvent>::CreateVector(&v73);
                        v49 = v48;
                        if ( v48 >= 0 )
                        {
                          v50 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, _QWORD *))v73->Ptr + 13))(v73, v70);
                          v51 = v50;
                          if ( v50 >= 0 )
                          {
                            v79 = v73;
                            v77 = 0;
                            v52 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::UploadTelemetryRequest,ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,Windows::Foundation::Collections::IVector<ModernDeployment::Autopilot::Core::TelemetryEvent *> *>(
                                    &v77,
                                    &v79);
                            v53 = v52;
                            if ( v52 >= 0 )
                            {
                              v74 = 0;
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
                              v54 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::FastWindowsTelemetry,ModernDeployment::Autopilot::Core::FastWindowsTelemetry,>(&v74);
                              v55 = v54;
                              if ( v54 >= 0 )
                              {
                                v76 = 0;
                                v56 = *v74;
                                v76 = 0;
                                v57 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v56 + 48))(
                                        v74,
                                        v77,
                                        &v76);
                                v58 = v57;
                                if ( v57 >= 0 )
                                {
                                  AcquireSRWLockExclusive(&stru_1802B7450);
                                  v79 = &stru_1802B7450;
                                  v59 = xmmword_1802B77F0;
                                  LOBYTE(v60) = v67[0];
                                  v61 = (_QWORD *)std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::pair_Microsoft::WRL::ComPtr_ModernDeployment::Autopilot::Core::FastWindowsTelemetry__wil::com_ptr_t_Windows::Foundation::IAsyncAction_wil::err_returncode_policy___________ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW__::D_::_lambda_1___(
                                                    &v75,
                                                    qword_1802B77E8,
                                                    xmmword_1802B77F0,
                                                    v60);
                                  std::vector<std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>>::erase(
                                    v62,
                                    &SystemTimeAsFileTime,
                                    *v61,
                                    v59);
                                  if ( (_QWORD)xmmword_1802B77F0 == *((_QWORD *)&xmmword_1802B77F0 + 1) )
                                  {
                                    std::vector<std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>(
                                      xmmword_1802B77F0,
                                      xmmword_1802B77F0,
                                      &v74,
                                      &v76);
                                    v64 = xmmword_1802B77F0;
                                  }
                                  else
                                  {
                                    std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>(
                                      xmmword_1802B77F0,
                                      &v74,
                                      &v76);
                                    v64 = xmmword_1802B77F0 + 16;
                                    *(_QWORD *)&xmmword_1802B77F0 = xmmword_1802B77F0 + 16;
                                  }
                                  v65 = (v64 - qword_1802B77E8) >> 4;
                                  if ( v65 > 0x100 )
                                    std::vector<std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>>::erase(
                                      v63,
                                      &v75,
                                      qword_1802B77E8,
                                      qword_1802B77E8 + 16 * (v65 - 256));
                                  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v79);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v77);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                                  return 0;
                                }
                                else
                                {
                                  wil::details::in1diag3::Return_Hr(
                                    retaddr,
                                    (void *)0x87,
                                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowste"
                                                  "lemetry\\fwtreporthelper.cpp",
                                    (const char *)(unsigned int)v57,
                                    v66);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v77);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                                  return v58;
                                }
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0x84,
                                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstele"
                                                "metry\\fwtreporthelper.cpp",
                                  (const char *)(unsigned int)v54,
                                  v66);
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v77);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                                return v55;
                              }
                            }
                            else
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0x7D,
                                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowsteleme"
                                              "try\\fwtreporthelper.cpp",
                                (const char *)(unsigned int)v52,
                                v66);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v77);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                              return v53;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x7A,
                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetr"
                                            "y\\fwtreporthelper.cpp",
                              (const char *)(unsigned int)v50,
                              v66);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                            return v51;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x79,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\"
                                          "fwtreporthelper.cpp",
                            (const char *)(unsigned int)v48,
                            v66);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                          return v49;
                        }
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x68,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwt"
                                      "reporthelper.cpp",
                        (const char *)(unsigned int)v40,
                        v66);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                      return v41;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x5C,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
                      (const char *)(unsigned int)v34,
                      v66);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                    return v35;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x51,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
                    (const char *)(unsigned int)v28,
                    v66);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                  return v29;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x49,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
                  (const char *)(unsigned int)v21,
                  v66);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v69);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
                return v22;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x45,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
                (const char *)(unsigned int)v18,
                v66);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
              return v19;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
              (const char *)(unsigned int)v15,
              v66);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
            return v16;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3D,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
            (const char *)(unsigned int)v13,
            v66);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
          return v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v66);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v68);
        return v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
        (const char *)0x80070057LL,
        v66);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtreporthelper.cpp",
      (const char *)0x80004001LL,
      v66);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800e2668  push    rbx
0x1800e266a  push    rsi
0x1800e266b  push    rdi
0x1800e266c  push    r12
0x1800e266e  push    r13
0x1800e2670  push    r14
0x1800e2672  push    r15
0x1800e2674  sub     rsp, 130h
0x1800e267b  mov     rax, cs:__security_cookie
0x1800e2682  xor     rax, rsp
0x1800e2685  mov     [rsp+168h+var_48], rax
0x1800e268d  mov     r15, r9
0x1800e2690  mov     r13d, r8d
0x1800e2693  mov     r12b, dl
0x1800e2696  mov     rbx, rcx
0x1800e2699  mov     [rsp+168h+var_F8], rcx
0x1800e269e  mov     r14, [rsp+168h+arg_20]
0x1800e26a6  mov     [rsp+168h+var_D8], r14
0x1800e26ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e26b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e26ba  xor     edi, edi
0x1800e26bc  test    al, al
0x1800e26be  jnz     short loc_1800E26E6
0x1800e26c0  mov     rcx, [rsp+168h]; this
0x1800e26c8  mov     ebx, 80004001h
0x1800e26cd  mov     r9d, ebx; char *
0x1800e26d0  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e26d7  lea     edx, [rdi+25h]; void *
0x1800e26da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e26df  mov     eax, ebx
0x1800e26e1  jmp     loc_1800E31A2
0x1800e26e6  test    rbx, rbx
0x1800e26e9  jz      loc_1800E3179
0x1800e26ef  cmp     [rbx], di
0x1800e26f2  jz      loc_1800E3179
0x1800e26f8  mov     qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800e2700  lea     rcx, [rsp+168h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800e2708  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e270f  nop     dword ptr [rax+rax+00h]
0x1800e2714  mov     [rsp+168h+var_130], rdi
0x1800e2719  mov     [rsp+168h+var_110], rdi
0x1800e271e  mov     [rsp+168h+var_70], rdi
0x1800e2726  mov     r9d, 20h ; ' '; unsigned int
0x1800e272c  lea     r8d, [r9+1]; unsigned int
0x1800e2730  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800e2737  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x1800e273f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e2744  lea     r8, [rsp+168h+var_110]
0x1800e2749  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800e2750  mov     rcx, [rsp+168h+var_70]
0x1800e2758  call    cs:__imp_RoGetActivationFactory
0x1800e275f  nop     dword ptr [rax+rax+00h]
0x1800e2764  mov     ebx, eax
0x1800e2766  test    eax, eax
0x1800e2768  jns     short loc_1800E27A3
0x1800e276a  mov     rcx, [rsp+168h]; this
0x1800e2772  mov     r9d, eax; char *
0x1800e2775  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e277c  mov     edx, 3Ah ; ':'; void *
0x1800e2781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2786  nop
0x1800e2787  lea     rcx, [rsp+168h+var_110]
0x1800e278c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2791  nop
0x1800e2792  lea     rcx, [rsp+168h+var_130]
0x1800e2797  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e279c  mov     eax, ebx
0x1800e279e  jmp     loc_1800E31A2
0x1800e27a3  mov     [rsp+168h+var_118], rdi
0x1800e27a8  mov     rcx, [rsp+168h+var_110]
0x1800e27ad  mov     rax, [rcx]
0x1800e27b0  mov     [rsp+168h+var_118], rdi
0x1800e27b5  lea     r8, [rsp+168h+var_118]
0x1800e27ba  mov     rdx, qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime]
0x1800e27c2  mov     rax, [rax+0A8h]
0x1800e27c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e27ce  mov     ebx, eax
0x1800e27d0  test    eax, eax
0x1800e27d2  jns     short loc_1800E2818
0x1800e27d4  mov     rcx, [rsp+168h]; this
0x1800e27dc  mov     r9d, eax; char *
0x1800e27df  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e27e6  mov     edx, 3Dh ; '='; void *
0x1800e27eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e27f0  nop
0x1800e27f1  lea     rcx, [rsp+168h+var_118]
0x1800e27f6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e27fb  nop
0x1800e27fc  lea     rcx, [rsp+168h+var_110]
0x1800e2801  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2806  nop
0x1800e2807  lea     rcx, [rsp+168h+var_130]
0x1800e280c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2811  mov     eax, ebx
0x1800e2813  jmp     loc_1800E31A2
0x1800e2818  mov     rcx, [rsp+168h+var_130]
0x1800e281d  mov     [rsp+168h+var_130], rdi
0x1800e2822  test    rcx, rcx
0x1800e2825  jz      short loc_1800E2834
0x1800e2827  mov     rax, [rcx]
0x1800e282a  mov     rax, [rax+10h]
0x1800e282e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2833  nop
0x1800e2834  mov     rcx, [rsp+168h+var_118]
0x1800e2839  mov     rax, [rcx]
0x1800e283c  lea     r8, [rsp+168h+var_130]
0x1800e2841  lea     rdx, _GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c
0x1800e2848  mov     rax, [rax]
0x1800e284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2850  mov     ebx, eax
0x1800e2852  test    eax, eax
0x1800e2854  jns     short loc_1800E289A
0x1800e2856  mov     rcx, [rsp+168h]; this
0x1800e285e  mov     r9d, eax; char *
0x1800e2861  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2868  mov     edx, 3Eh ; '>'; void *
0x1800e286d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2872  nop
0x1800e2873  lea     rcx, [rsp+168h+var_118]
0x1800e2878  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e287d  nop
0x1800e287e  lea     rcx, [rsp+168h+var_110]
0x1800e2883  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2888  nop
0x1800e2889  lea     rcx, [rsp+168h+var_130]
0x1800e288e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2893  mov     eax, ebx
0x1800e2895  jmp     loc_1800E31A2
0x1800e289a  mov     [rsp+168h+var_120], rdi
0x1800e289f  mov     rax, [rsp+168h+var_130]
0x1800e28a4  mov     qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800e28ac  lea     rdx, [rsp+168h+var_F8]
0x1800e28b1  lea     rcx, [rsp+168h+hstringHeader]
0x1800e28b9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e28be  nop
0x1800e28bf  mov     rax, [rax+18h]
0x1800e28c3  mov     [rsp+168h+var_F8], rax
0x1800e28c8  mov     rcx, [rsp+168h+var_120]
0x1800e28cd  mov     [rsp+168h+var_120], rdi
0x1800e28d2  test    rcx, rcx
0x1800e28d5  jz      short loc_1800E28E4
0x1800e28d7  mov     rax, [rcx]
0x1800e28da  mov     rax, [rax+10h]
0x1800e28de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e28e3  nop
0x1800e28e4  lea     r8, [rsp+168h+SystemTimeAsFileTime]
0x1800e28ec  lea     rdx, [rsp+168h+var_F8]
0x1800e28f1  lea     rcx, [rsp+168h+var_120]
0x1800e28f6  call    ??$MakeAndInitialize@VTelemetryEvent@Core@Autopilot@ModernDeployment@@UITelemetryEvent@234@PEAUHSTRING__@@PEAU?$IReference@UDateTime@Foundation@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAUITelemetryEvent@Core@Autopilot@ModernDeployment@@$$QEAPEAUHSTRING__@@$$QEAPEAU?$IReference@UDateTime@Foundation@Windows@@@Foundation@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::TelemetryEvent,ModernDeployment::Autopilot::Core::ITelemetryEvent,HSTRING__ *,Windows::Foundation::IReference<Windows::Foundation::DateTime> *>(ModernDeployment::Autopilot::Core::ITelemetryEvent * *,HSTRING__ * &&,Windows::Foundation::IReference<Windows::Foundation::DateTime> * &&)
0x1800e28fb  mov     ebx, eax
0x1800e28fd  test    eax, eax
0x1800e28ff  jns     short loc_1800E2950
0x1800e2901  mov     rcx, [rsp+168h]; this
0x1800e2909  mov     r9d, eax; char *
0x1800e290c  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2913  mov     edx, 45h ; 'E'; void *
0x1800e2918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e291d  nop
0x1800e291e  lea     rcx, [rsp+168h+var_120]
0x1800e2923  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2928  nop
0x1800e2929  lea     rcx, [rsp+168h+var_118]
0x1800e292e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2933  nop
0x1800e2934  lea     rcx, [rsp+168h+var_110]
0x1800e2939  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e293e  nop
0x1800e293f  lea     rcx, [rsp+168h+var_130]
0x1800e2944  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2949  mov     eax, ebx
0x1800e294b  jmp     loc_1800E31A2
0x1800e2950  mov     [rsp+168h+var_128], rdi
0x1800e2955  mov     rcx, [rsp+168h+var_120]
0x1800e295a  mov     rax, [rcx]
0x1800e295d  mov     [rsp+168h+var_128], rdi
0x1800e2962  lea     rdx, [rsp+168h+var_128]
0x1800e2967  mov     rax, [rax+40h]
0x1800e296b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2970  mov     ebx, eax
0x1800e2972  test    eax, eax
0x1800e2974  jns     short loc_1800E29D0
0x1800e2976  mov     rcx, [rsp+168h]; this
0x1800e297e  mov     r9d, eax; char *
0x1800e2981  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2988  mov     edx, 49h ; 'I'; void *
0x1800e298d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2992  nop
0x1800e2993  lea     rcx, [rsp+168h+var_128]
0x1800e2998  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e299d  nop
0x1800e299e  lea     rcx, [rsp+168h+var_120]
0x1800e29a3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e29a8  nop
0x1800e29a9  lea     rcx, [rsp+168h+var_118]
0x1800e29ae  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e29b3  nop
0x1800e29b4  lea     rcx, [rsp+168h+var_110]
0x1800e29b9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e29be  nop
0x1800e29bf  lea     rcx, [rsp+168h+var_130]
0x1800e29c4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e29c9  mov     eax, ebx
0x1800e29cb  jmp     loc_1800E31A2
0x1800e29d0  mov     [rsp+168h+var_138], dil
0x1800e29d5  mov     rsi, [rsp+168h+var_128]
0x1800e29da  mov     rax, [rsi]
0x1800e29dd  mov     rdi, [rax+50h]
0x1800e29e1  lea     rcx, aFalse_0; "false"
0x1800e29e8  lea     rax, aTrue; "true"
0x1800e29ef  test    r12b, r12b
0x1800e29f2  cmovz   rax, rcx
0x1800e29f6  mov     [rsp+168h+var_F8], rax
0x1800e29fb  lea     rdx, [rsp+168h+var_F8]
0x1800e2a00  lea     rcx, [rsp+168h+hstringHeader]
0x1800e2a08  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e2a0d  nop
0x1800e2a0e  mov     rbx, [rax+18h]
0x1800e2a12  lea     rdx, ?Status@FwtTelemetrySchema@Core@Autopilot@ModernDeployment@@2QEBGEB; ushort const * const ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Status
0x1800e2a19  lea     rcx, [rsp+168h+var_D0]
0x1800e2a21  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e2a26  nop
0x1800e2a27  lea     r9, [rsp+168h+var_138]
0x1800e2a2c  mov     r8, rbx
0x1800e2a2f  mov     rdx, [rax+18h]
0x1800e2a33  mov     rcx, rsi
0x1800e2a36  mov     rax, rdi
0x1800e2a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a3e  mov     ebx, eax
0x1800e2a40  xor     r12d, r12d
0x1800e2a43  test    eax, eax
0x1800e2a45  jns     short loc_1800E2AA1
0x1800e2a47  mov     rcx, [rsp+168h]; this
0x1800e2a4f  mov     r9d, eax; char *
0x1800e2a52  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2a59  lea     edx, [r12+51h]; void *
0x1800e2a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2a63  nop
0x1800e2a64  lea     rcx, [rsp+168h+var_128]
0x1800e2a69  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2a6e  nop
0x1800e2a6f  lea     rcx, [rsp+168h+var_120]
0x1800e2a74  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2a79  nop
0x1800e2a7a  lea     rcx, [rsp+168h+var_118]
0x1800e2a7f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2a84  nop
0x1800e2a85  lea     rcx, [rsp+168h+var_110]
0x1800e2a8a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2a8f  nop
0x1800e2a90  lea     rcx, [rsp+168h+var_130]
0x1800e2a95  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2a9a  mov     eax, ebx
0x1800e2a9c  jmp     loc_1800E31A2
0x1800e2aa1  xorps   xmm0, xmm0
0x1800e2aa4  movups  xmmword ptr [rsp+168h+hstringHeader.Reserved], xmm0
0x1800e2aac  movups  xmmword ptr [rsp+0F0h], xmm0
0x1800e2ab4  mov     r9d, r13d
0x1800e2ab7  lea     r8, a0x08x_0; "0x%08X"
0x1800e2abe  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800e2ac2  mov     rdx, r13
0x1800e2ac5  lea     rcx, [rsp+168h+hstringHeader]
0x1800e2acd  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1800e2ad2  mov     [rsp+168h+var_138], r12b
0x1800e2ad7  mov     rsi, [rsp+168h+var_128]
0x1800e2adc  mov     rax, [rsi]
0x1800e2adf  mov     rdi, [rax+50h]
0x1800e2ae3  lea     rdx, [rsp+168h+hstringHeader]; sourceString
0x1800e2aeb  lea     rcx, [rsp+168h+var_D0]; hstringHeader
0x1800e2af3  call    ??$?0$0CA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[32])
0x1800e2af8  nop
0x1800e2af9  mov     rbx, [rax+18h]
0x1800e2afd  lea     rdx, ?Error_Code@FwtTelemetrySchema@Core@Autopilot@ModernDeployment@@2QEBGEB; ushort const * const ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Error_Code
0x1800e2b04  lea     rcx, [rsp+168h+var_B0]
0x1800e2b0c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e2b11  nop
0x1800e2b12  lea     r9, [rsp+168h+var_138]
0x1800e2b17  mov     r8, rbx
0x1800e2b1a  mov     rdx, [rax+18h]
0x1800e2b1e  mov     rcx, rsi
0x1800e2b21  mov     rax, rdi
0x1800e2b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2b29  mov     ebx, eax
0x1800e2b2b  test    eax, eax
0x1800e2b2d  jns     short loc_1800E2B88
0x1800e2b2f  mov     rcx, [rsp+168h]; this
0x1800e2b37  mov     r9d, eax; char *
0x1800e2b3a  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2b41  lea     edx, [r13+5Dh]; void *
0x1800e2b45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2b4a  nop
0x1800e2b4b  lea     rcx, [rsp+168h+var_128]
0x1800e2b50  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2b55  nop
0x1800e2b56  lea     rcx, [rsp+168h+var_120]
0x1800e2b5b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2b60  nop
0x1800e2b61  lea     rcx, [rsp+168h+var_118]
0x1800e2b66  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e2b6b  nop
0x1800e2b6c  lea     rcx, [rsp+168h+var_110]
  ... truncated ...
```
