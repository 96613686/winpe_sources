# ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(ushort const *,bool,long,__int64,ushort const *)

- ea: `0x1800dfdf0`
- end: `0x1800e0952`
- name: `?ReportEventW@FwtReportHelper@Core@Autopilot@ModernDeployment@@SAJPEBG_NJ_J0@Z`
- size: `2914`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, int, __int64, const unsigned __int16 *)`
- caller_count: `17`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a5490`
- `0x1800a5b20`
- `0x1800ac438`
- `0x1800bc698`
- `0x1800c2c00`
- `0x1800c8174`
- `0x1800c838c`
- `0x1800d1b00`
- `0x1800d4a68`
- `0x1800d7dd0`
- `0x1800ec580`
- `0x1800fd7c0`
- `0x1800fe040`
- `0x1800fe4d0`
- `0x1800feb10`
- `0x1800ff3c0`
- `0x1801032d0`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067008`
- `0x180067a54`
- `0x18006afb0`
- `0x18006b158`
- `0x18006defc`
- `0x18006e0a8`
- `0x1800775c4`
- `0x180081f1c`
- `0x1800853a0`
- `0x1800d8758`
- `0x1800df880`
- `0x1800df9d4`
- `0x1800dfb04`
- `0x1800dfca0`
- `0x1800dfcdc`
- `0x1800dfd18`
- `0x1800dfdf0`
- `0x1800e09dc`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e07bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e07bb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800dfeda`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800dfeda`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800dfe90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800dfe90`

## string_xrefs

- `0x1800dfe58`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800dfef1`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800dff5b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800dffdd`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e0088`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e00fd`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e01ce`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e02b6`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e03a2`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e046c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e04db`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e055c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e05f1`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e0683`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e0733`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`
- `0x1800e0915`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtreporthelper.cpp`

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
  __int64 **v64; // rdx
  __int64 v65; // rax
  __int64 v66; // r9
  unsigned __int64 v67; // r9
  int v68; // [rsp+20h] [rbp-148h]
  _BYTE v69[8]; // [rsp+30h] [rbp-138h] BYREF
  struct _FILETIME v70; // [rsp+38h] [rbp-130h] BYREF
  __int64 v71; // [rsp+40h] [rbp-128h] BYREF
  _QWORD *v72; // [rsp+48h] [rbp-120h] BYREF
  __int64 (__fastcall ***v73)(_QWORD, GUID *, struct _FILETIME *); // [rsp+50h] [rbp-118h] BYREF
  __int64 *v74; // [rsp+58h] [rbp-110h] BYREF
  __int64 *v75; // [rsp+60h] [rbp-108h] BYREF
  RTL_SRWLOCK *v76; // [rsp+68h] [rbp-100h] BYREF
  __int64 v77; // [rsp+70h] [rbp-F8h] BYREF
  const unsigned __int16 *v78; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v79; // [rsp+80h] [rbp-E8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v81; // [rsp+90h] [rbp-D8h] BYREF
  HSTRING_HEADER v82; // [rsp+98h] [rbp-D0h] BYREF
  HSTRING_HEADER v83; // [rsp+B8h] [rbp-B0h] BYREF
  __int128 hstringHeader; // [rsp+E0h] [rbp-88h] BYREF
  __int128 hstringHeader_16; // [rsp+F0h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v78 = a1;
  v81 = a5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    if ( a1 && *a1 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v70 = 0;
      v74 = 0;
      *((_QWORD *)&hstringHeader_16 + 1) = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)&hstringHeader,
        L"Windows.Foundation.PropertyValue",
        0x21u,
        0x20u);
      ActivationFactory = RoGetActivationFactory(
                            *((_QWORD *)&hstringHeader_16 + 1),
                            &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858,
                            &v74);
      v11 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v73 = 0;
        v12 = *v74;
        v73 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64 *, struct _FILETIME, __int64 (__fastcall ****)(_QWORD, GUID *, struct _FILETIME *)))(v12 + 168))(
                v74,
                SystemTimeAsFileTime,
                &v73);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v70 = 0;
          v15 = (**v73)(v73, &GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c, &v70);
          v16 = v15;
          if ( v15 >= 0 )
          {
            v72 = 0;
            SystemTimeAsFileTime = v70;
            v78 = *(const unsigned __int16 **)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                 &hstringHeader,
                                                 &v78)
                                             + 24);
            v17 = v72;
            v72 = 0;
            if ( v17 )
              (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
            v18 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::TelemetryEvent,ModernDeployment::Autopilot::Core::ITelemetryEvent,HSTRING__ *,Windows::Foundation::IReference<Windows::Foundation::DateTime> *>(
                    &v72,
                    &v78,
                    &SystemTimeAsFileTime);
            v19 = v18;
            if ( v18 >= 0 )
            {
              v71 = 0;
              v20 = *v72;
              v71 = 0;
              v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v20 + 64))(v72, &v71);
              v22 = v21;
              if ( v21 >= 0 )
              {
                v69[0] = 0;
                v23 = v71;
                v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v71 + 80LL);
                v25 = L"true";
                if ( !a2 )
                  v25 = L"false";
                v78 = v25;
                v26 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v78) + 24);
                v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &v82,
                        &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Status);
                v28 = v24(v23, *(_QWORD *)(v27 + 24), v26, v69);
                v29 = v28;
                if ( v28 >= 0 )
                {
                  hstringHeader = 0;
                  hstringHeader_16 = 0;
                  _snwprintf_s<16>(&hstringHeader, -1, L"0x%08X", a3);
                  v69[0] = 0;
                  v30 = v71;
                  v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v71 + 80LL);
                  v32 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                      &v82,
                                      (PCWSTR)&hstringHeader)
                                  + 24);
                  v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &v83,
                          &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Error_Code);
                  v34 = v31(v30, *(_QWORD *)(v33 + 24), v32, v69);
                  v35 = v34;
                  if ( v34 >= 0 )
                  {
                    if ( a4 <= 0 )
                      goto LABEL_51;
                    memset_0(&hstringHeader, 0, 0x40u);
                    _snwprintf_s<32>(&hstringHeader, -1, L"%lld", a4);
                    v69[0] = 0;
                    v36 = v71;
                    v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v71 + 80LL);
                    v38 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                        &v83,
                                        (PCWSTR)&hstringHeader)
                                    + 24);
                    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &v82,
                            &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Duration);
                    v40 = v37(v36, *(_QWORD *)(v39 + 24), v38, v69);
                    v41 = v40;
                    if ( v40 >= 0 )
                    {
LABEL_51:
                      if ( a5
                        && LOWORD(a5->Ptr)
                        && (v69[0] = 0,
                            v42 = v71,
                            v43 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v71 + 80LL),
                            v44 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v83, &v81)
                                            + 24),
                            v45 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                    &v82,
                                    &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Phases),
                            v46 = v43(v42, *(_QWORD *)(v45 + 24), v44, v69),
                            v47 = v46,
                            v46 < 0) )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x72,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\f"
                                        "wtreporthelper.cpp",
                          (const char *)(unsigned int)v46,
                          v68);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
                        return v47;
                      }
                      else
                      {
                        v76 = 0;
                        v48 = Windows::Management::Setup::VectorWrapperT<ModernDeployment::Autopilot::Core::TelemetryEvent,ModernDeployment::Autopilot::Core::ITelemetryEvent>::CreateVector(&v76);
                        v49 = v48;
                        if ( v48 >= 0 )
                        {
                          v50 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, _QWORD *))v76->Ptr + 13))(v76, v72);
                          v51 = v50;
                          if ( v50 >= 0 )
                          {
                            v81 = v76;
                            v79 = 0;
                            v52 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::UploadTelemetryRequest,ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,Windows::Foundation::Collections::IVector<ModernDeployment::Autopilot::Core::TelemetryEvent *> *>(
                                    &v79,
                                    &v81);
                            v53 = v52;
                            if ( v52 >= 0 )
                            {
                              v75 = 0;
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
                              v54 = Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::FastWindowsTelemetry,ModernDeployment::Autopilot::Core::FastWindowsTelemetry,>(&v75);
                              v55 = v54;
                              if ( v54 >= 0 )
                              {
                                v77 = 0;
                                v56 = *v75;
                                v77 = 0;
                                v57 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v56 + 48))(
                                        v75,
                                        v79,
                                        &v77);
                                v58 = v57;
                                if ( v57 >= 0 )
                                {
                                  AcquireSRWLockExclusive(&stru_1802B2320);
                                  v81 = &stru_1802B2320;
                                  v59 = xmmword_1802B27D0;
                                  LOBYTE(v60) = v69[0];
                                  v61 = (_QWORD *)std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::pair_Microsoft::WRL::ComPtr_ModernDeployment::Autopilot::Core::FastWindowsTelemetry__wil::com_ptr_t_Windows::Foundation::IAsyncAction_wil::err_returncode_policy___________ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW__::D_::_lambda_1___(
                                                    &v78,
                                                    qword_1802B27C8,
                                                    xmmword_1802B27D0,
                                                    v60);
                                  std::vector<std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>>::erase(
                                    v62,
                                    &SystemTimeAsFileTime,
                                    *v61,
                                    v59);
                                  v64 = (__int64 **)xmmword_1802B27D0;
                                  if ( (_QWORD)xmmword_1802B27D0 == *((_QWORD *)&xmmword_1802B27D0 + 1) )
                                  {
                                    std::vector<std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>(
                                      v63,
                                      xmmword_1802B27D0,
                                      (char *)&v75,
                                      &v77);
                                    v66 = xmmword_1802B27D0;
                                  }
                                  else
                                  {
                                    *(_QWORD *)xmmword_1802B27D0 = 0;
                                    if ( v64 != &v75 )
                                    {
                                      *v64 = v75;
                                      v75 = 0;
                                    }
                                    v65 = v77;
                                    v77 = 0;
                                    v64[1] = (__int64 *)v65;
                                    v66 = xmmword_1802B27D0 + 16;
                                    *(_QWORD *)&xmmword_1802B27D0 = xmmword_1802B27D0 + 16;
                                  }
                                  v67 = (v66 - qword_1802B27C8) >> 4;
                                  if ( v67 > 0x100 )
                                    std::vector<std::pair<Microsoft::WRL::ComPtr<ModernDeployment::Autopilot::Core::FastWindowsTelemetry>,wil::com_ptr_t<Windows::Foundation::IAsyncAction,wil::err_returncode_policy>>>::erase(
                                      v63,
                                      &v78,
                                      qword_1802B27C8,
                                      qword_1802B27C8 + 16 * (v67 - 256));
                                  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v81);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v77);
                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v79);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                                    v68);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v77);
                                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v79);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                                  v68);
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v79);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                                v68);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v79);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                              v68);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                            v68);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v76);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                        v68);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                      v68);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                    v68);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                  v68);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v71);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
                v68);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v72);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
              v68);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
            v68);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v73);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
          v68);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v74);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v70);
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
        v68);
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
      v68);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800dfdf0  push    rbx
0x1800dfdf2  push    rsi
0x1800dfdf3  push    rdi
0x1800dfdf4  push    r12
0x1800dfdf6  push    r13
0x1800dfdf8  push    r14
0x1800dfdfa  push    r15
0x1800dfdfc  sub     rsp, 130h
0x1800dfe03  mov     rax, cs:__security_cookie
0x1800dfe0a  xor     rax, rsp
0x1800dfe0d  mov     [rsp+168h+var_48], rax
0x1800dfe15  mov     r15, r9
0x1800dfe18  mov     r13d, r8d
0x1800dfe1b  mov     r12b, dl
0x1800dfe1e  mov     rbx, rcx
0x1800dfe21  mov     [rsp+168h+var_F0], rcx
0x1800dfe26  mov     r14, [rsp+168h+arg_20]
0x1800dfe2e  mov     [rsp+168h+var_D8], r14
0x1800dfe36  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800dfe3d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800dfe42  xor     edi, edi
0x1800dfe44  test    al, al
0x1800dfe46  jnz     short loc_1800DFE6E
0x1800dfe48  mov     rcx, [rsp+168h]; this
0x1800dfe50  mov     ebx, 80004001h
0x1800dfe55  mov     r9d, ebx; char *
0x1800dfe58  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dfe5f  lea     edx, [rdi+25h]; void *
0x1800dfe62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dfe67  mov     eax, ebx
0x1800dfe69  jmp     loc_1800E092E
0x1800dfe6e  test    rbx, rbx
0x1800dfe71  jz      loc_1800E0905
0x1800dfe77  cmp     [rbx], di
0x1800dfe7a  jz      loc_1800E0905
0x1800dfe80  mov     qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800dfe88  lea     rcx, [rsp+168h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800dfe90  call    cs:__imp_GetSystemTimeAsFileTime
0x1800dfe96  mov     [rsp+168h+var_130], rdi
0x1800dfe9b  mov     [rsp+168h+var_110], rdi
0x1800dfea0  mov     [rsp+168h+var_70], rdi
0x1800dfea8  mov     r9d, 20h ; ' '; unsigned int
0x1800dfeae  lea     r8d, [r9+1]; unsigned int
0x1800dfeb2  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800dfeb9  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x1800dfec1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800dfec6  lea     r8, [rsp+168h+var_110]
0x1800dfecb  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800dfed2  mov     rcx, [rsp+168h+var_70]
0x1800dfeda  call    cs:__imp_RoGetActivationFactory
0x1800dfee0  mov     ebx, eax
0x1800dfee2  test    eax, eax
0x1800dfee4  jns     short loc_1800DFF1F
0x1800dfee6  mov     rcx, [rsp+168h]; this
0x1800dfeee  mov     r9d, eax; char *
0x1800dfef1  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dfef8  mov     edx, 3Ah ; ':'; void *
0x1800dfefd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dff02  nop
0x1800dff03  lea     rcx, [rsp+168h+var_110]
0x1800dff08  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dff0d  nop
0x1800dff0e  lea     rcx, [rsp+168h+var_130]
0x1800dff13  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dff18  mov     eax, ebx
0x1800dff1a  jmp     loc_1800E092E
0x1800dff1f  mov     [rsp+168h+var_118], rdi
0x1800dff24  mov     rcx, [rsp+168h+var_110]
0x1800dff29  mov     rax, [rcx]
0x1800dff2c  mov     [rsp+168h+var_118], rdi
0x1800dff31  lea     r8, [rsp+168h+var_118]
0x1800dff36  mov     rdx, qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime]
0x1800dff3e  mov     rax, [rax+0A8h]
0x1800dff45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff4a  mov     ebx, eax
0x1800dff4c  test    eax, eax
0x1800dff4e  jns     short loc_1800DFF94
0x1800dff50  mov     rcx, [rsp+168h]; this
0x1800dff58  mov     r9d, eax; char *
0x1800dff5b  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dff62  mov     edx, 3Dh ; '='; void *
0x1800dff67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dff6c  nop
0x1800dff6d  lea     rcx, [rsp+168h+var_118]
0x1800dff72  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dff77  nop
0x1800dff78  lea     rcx, [rsp+168h+var_110]
0x1800dff7d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dff82  nop
0x1800dff83  lea     rcx, [rsp+168h+var_130]
0x1800dff88  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dff8d  mov     eax, ebx
0x1800dff8f  jmp     loc_1800E092E
0x1800dff94  mov     rcx, [rsp+168h+var_130]
0x1800dff99  mov     [rsp+168h+var_130], rdi
0x1800dff9e  test    rcx, rcx
0x1800dffa1  jz      short loc_1800DFFB0
0x1800dffa3  mov     rax, [rcx]
0x1800dffa6  mov     rax, [rax+10h]
0x1800dffaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dffaf  nop
0x1800dffb0  mov     rcx, [rsp+168h+var_118]
0x1800dffb5  mov     rax, [rcx]
0x1800dffb8  lea     r8, [rsp+168h+var_130]
0x1800dffbd  lea     rdx, _GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c
0x1800dffc4  mov     rax, [rax]
0x1800dffc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dffcc  mov     ebx, eax
0x1800dffce  test    eax, eax
0x1800dffd0  jns     short loc_1800E0016
0x1800dffd2  mov     rcx, [rsp+168h]; this
0x1800dffda  mov     r9d, eax; char *
0x1800dffdd  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dffe4  mov     edx, 3Eh ; '>'; void *
0x1800dffe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dffee  nop
0x1800dffef  lea     rcx, [rsp+168h+var_118]
0x1800dfff4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dfff9  nop
0x1800dfffa  lea     rcx, [rsp+168h+var_110]
0x1800dffff  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0004  nop
0x1800e0005  lea     rcx, [rsp+168h+var_130]
0x1800e000a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e000f  mov     eax, ebx
0x1800e0011  jmp     loc_1800E092E
0x1800e0016  mov     [rsp+168h+var_120], rdi
0x1800e001b  mov     rax, [rsp+168h+var_130]
0x1800e0020  mov     qword ptr [rsp+168h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800e0028  lea     rdx, [rsp+168h+var_F0]
0x1800e002d  lea     rcx, [rsp+168h+hstringHeader]
0x1800e0035  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e003a  nop
0x1800e003b  mov     rax, [rax+18h]
0x1800e003f  mov     [rsp+168h+var_F0], rax
0x1800e0044  mov     rcx, [rsp+168h+var_120]
0x1800e0049  mov     [rsp+168h+var_120], rdi
0x1800e004e  test    rcx, rcx
0x1800e0051  jz      short loc_1800E0060
0x1800e0053  mov     rax, [rcx]
0x1800e0056  mov     rax, [rax+10h]
0x1800e005a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e005f  nop
0x1800e0060  lea     r8, [rsp+168h+SystemTimeAsFileTime]
0x1800e0068  lea     rdx, [rsp+168h+var_F0]
0x1800e006d  lea     rcx, [rsp+168h+var_120]
0x1800e0072  call    ??$MakeAndInitialize@VTelemetryEvent@Core@Autopilot@ModernDeployment@@UITelemetryEvent@234@PEAUHSTRING__@@PEAU?$IReference@UDateTime@Foundation@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAUITelemetryEvent@Core@Autopilot@ModernDeployment@@$$QEAPEAUHSTRING__@@$$QEAPEAU?$IReference@UDateTime@Foundation@Windows@@@Foundation@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ModernDeployment::Autopilot::Core::TelemetryEvent,ModernDeployment::Autopilot::Core::ITelemetryEvent,HSTRING__ *,Windows::Foundation::IReference<Windows::Foundation::DateTime> *>(ModernDeployment::Autopilot::Core::ITelemetryEvent * *,HSTRING__ * &&,Windows::Foundation::IReference<Windows::Foundation::DateTime> * &&)
0x1800e0077  mov     ebx, eax
0x1800e0079  test    eax, eax
0x1800e007b  jns     short loc_1800E00CC
0x1800e007d  mov     rcx, [rsp+168h]; this
0x1800e0085  mov     r9d, eax; char *
0x1800e0088  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e008f  mov     edx, 45h ; 'E'; void *
0x1800e0094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0099  nop
0x1800e009a  lea     rcx, [rsp+168h+var_120]
0x1800e009f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e00a4  nop
0x1800e00a5  lea     rcx, [rsp+168h+var_118]
0x1800e00aa  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e00af  nop
0x1800e00b0  lea     rcx, [rsp+168h+var_110]
0x1800e00b5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e00ba  nop
0x1800e00bb  lea     rcx, [rsp+168h+var_130]
0x1800e00c0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e00c5  mov     eax, ebx
0x1800e00c7  jmp     loc_1800E092E
0x1800e00cc  mov     [rsp+168h+var_128], rdi
0x1800e00d1  mov     rcx, [rsp+168h+var_120]
0x1800e00d6  mov     rax, [rcx]
0x1800e00d9  mov     [rsp+168h+var_128], rdi
0x1800e00de  lea     rdx, [rsp+168h+var_128]
0x1800e00e3  mov     rax, [rax+40h]
0x1800e00e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e00ec  mov     ebx, eax
0x1800e00ee  test    eax, eax
0x1800e00f0  jns     short loc_1800E014C
0x1800e00f2  mov     rcx, [rsp+168h]; this
0x1800e00fa  mov     r9d, eax; char *
0x1800e00fd  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0104  mov     edx, 49h ; 'I'; void *
0x1800e0109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e010e  nop
0x1800e010f  lea     rcx, [rsp+168h+var_128]
0x1800e0114  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0119  nop
0x1800e011a  lea     rcx, [rsp+168h+var_120]
0x1800e011f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0124  nop
0x1800e0125  lea     rcx, [rsp+168h+var_118]
0x1800e012a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e012f  nop
0x1800e0130  lea     rcx, [rsp+168h+var_110]
0x1800e0135  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e013a  nop
0x1800e013b  lea     rcx, [rsp+168h+var_130]
0x1800e0140  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0145  mov     eax, ebx
0x1800e0147  jmp     loc_1800E092E
0x1800e014c  mov     [rsp+168h+var_138], dil
0x1800e0151  mov     rsi, [rsp+168h+var_128]
0x1800e0156  mov     rax, [rsi]
0x1800e0159  mov     rdi, [rax+50h]
0x1800e015d  lea     rcx, aFalse_0; "false"
0x1800e0164  lea     rax, aTrue; "true"
0x1800e016b  test    r12b, r12b
0x1800e016e  cmovz   rax, rcx
0x1800e0172  mov     [rsp+168h+var_F0], rax
0x1800e0177  lea     rdx, [rsp+168h+var_F0]
0x1800e017c  lea     rcx, [rsp+168h+hstringHeader]
0x1800e0184  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e0189  nop
0x1800e018a  mov     rbx, [rax+18h]
0x1800e018e  lea     rdx, ?Status@FwtTelemetrySchema@Core@Autopilot@ModernDeployment@@2QEBGEB; ushort const * const ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Status
0x1800e0195  lea     rcx, [rsp+168h+var_D0]
0x1800e019d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e01a2  nop
0x1800e01a3  lea     r9, [rsp+168h+var_138]
0x1800e01a8  mov     r8, rbx
0x1800e01ab  mov     rdx, [rax+18h]
0x1800e01af  mov     rcx, rsi
0x1800e01b2  mov     rax, rdi
0x1800e01b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e01ba  mov     ebx, eax
0x1800e01bc  xor     r12d, r12d
0x1800e01bf  test    eax, eax
0x1800e01c1  jns     short loc_1800E021D
0x1800e01c3  mov     rcx, [rsp+168h]; this
0x1800e01cb  mov     r9d, eax; char *
0x1800e01ce  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e01d5  lea     edx, [r12+51h]; void *
0x1800e01da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e01df  nop
0x1800e01e0  lea     rcx, [rsp+168h+var_128]
0x1800e01e5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e01ea  nop
0x1800e01eb  lea     rcx, [rsp+168h+var_120]
0x1800e01f0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e01f5  nop
0x1800e01f6  lea     rcx, [rsp+168h+var_118]
0x1800e01fb  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0200  nop
0x1800e0201  lea     rcx, [rsp+168h+var_110]
0x1800e0206  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e020b  nop
0x1800e020c  lea     rcx, [rsp+168h+var_130]
0x1800e0211  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0216  mov     eax, ebx
0x1800e0218  jmp     loc_1800E092E
0x1800e021d  xorps   xmm0, xmm0
0x1800e0220  movups  xmmword ptr [rsp+168h+hstringHeader.Reserved], xmm0
0x1800e0228  movups  xmmword ptr [rsp+0F0h], xmm0
0x1800e0230  mov     r9d, r13d
0x1800e0233  lea     r8, a0x08x_0; "0x%08X"
0x1800e023a  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800e023e  mov     rdx, r13
0x1800e0241  lea     rcx, [rsp+168h+hstringHeader]
0x1800e0249  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1800e024e  mov     [rsp+168h+var_138], r12b
0x1800e0253  mov     rsi, [rsp+168h+var_128]
0x1800e0258  mov     rax, [rsi]
0x1800e025b  mov     rdi, [rax+50h]
0x1800e025f  lea     rdx, [rsp+168h+hstringHeader]; sourceString
0x1800e0267  lea     rcx, [rsp+168h+var_D0]; hstringHeader
0x1800e026f  call    ??$?0$0CA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[32])
0x1800e0274  nop
0x1800e0275  mov     rbx, [rax+18h]
0x1800e0279  lea     rdx, ?Error_Code@FwtTelemetrySchema@Core@Autopilot@ModernDeployment@@2QEBGEB; ushort const * const ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Error_Code
0x1800e0280  lea     rcx, [rsp+168h+var_B0]
0x1800e0288  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e028d  nop
0x1800e028e  lea     r9, [rsp+168h+var_138]
0x1800e0293  mov     r8, rbx
0x1800e0296  mov     rdx, [rax+18h]
0x1800e029a  mov     rcx, rsi
0x1800e029d  mov     rax, rdi
0x1800e02a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e02a5  mov     ebx, eax
0x1800e02a7  test    eax, eax
0x1800e02a9  jns     short loc_1800E0304
0x1800e02ab  mov     rcx, [rsp+168h]; this
0x1800e02b3  mov     r9d, eax; char *
0x1800e02b6  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e02bd  lea     edx, [r13+5Dh]; void *
0x1800e02c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e02c6  nop
0x1800e02c7  lea     rcx, [rsp+168h+var_128]
0x1800e02cc  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e02d1  nop
0x1800e02d2  lea     rcx, [rsp+168h+var_120]
0x1800e02d7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e02dc  nop
0x1800e02dd  lea     rcx, [rsp+168h+var_118]
0x1800e02e2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e02e7  nop
0x1800e02e8  lea     rcx, [rsp+168h+var_110]
0x1800e02ed  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e02f2  nop
  ... truncated ...
```
