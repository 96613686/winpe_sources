# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::SendMdmAlertMessage(HSTRING__ *,HSTRING__ *,HSTRING__ *,ulong)

- ea: `0x1800a6470`
- end: `0x1800a6ee6`
- name: `?SendMdmAlertMessage@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJPEAUHSTRING__@@00K@Z`
- size: `2678`
- prototype: `int(ModernDeployment::Autopilot::Core::DeviceManagementUtilities *__hidden this, HSTRING, HSTRING, HSTRING, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x18006b708`
- `0x18006c694`
- `0x18006defc`
- `0x18007755c`
- `0x18008019c`
- `0x18008122c`
- `0x1800839bc`
- `0x1800853a0`
- `0x180089ff4`
- `0x18008a014`
- `0x18008c588`
- `0x1800a1508`
- `0x1800a1f94`
- `0x1800a31d4`
- `0x1800a3264`
- `0x1800a3ec8`
- `0x1800a4644`
- `0x1800a4c48`
- `0x1800a6470`
- `0x1800a8420`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a6c8e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a6c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a67ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a67d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6c5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a67ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a67d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6c5d`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a66fa`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a66fa`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a6c1f`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a6c1f`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a6ca8`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a6cbb`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a6cf3`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a6ca8`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a6cbb`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a6cf3`
- `omadmapi!__imp_OmaDmInitiateSessionFullSync` at `0x1800a6977`
- `omadmapi!__imp_OmaDmInitiateSessionFullSync` at `0x1800a6977`

## string_xrefs

- `0x1800a64cf`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6507`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a65a1`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a65fd`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6726`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6a89`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6cda`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6b9d`: `AttemptedSyncSession`
- `0x1800a680e`: `User SID count = %d; management server ID count = %d; alert type = %s; alert data = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceManagementUtilities::SendMdmAlertMessage(
        ModernDeployment::Autopilot::Core::DeviceManagementUtilities *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        unsigned int a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int IsSyncSchedulingDisabledByPolicy; // eax
  unsigned int v12; // ebx
  __int64 v13; // rbx
  void (__fastcall *v14)(__int64, __int64, HSTRING, _QWORD, __int64, int); // rsi
  __int64 v15; // rdi
  _QWORD *v16; // rax
  int EnrollmentIds; // eax
  unsigned int v18; // ebx
  PCWSTR v19; // rax
  __int64 v20; // rdi
  BOOL v21; // ebx
  __int64 v22; // rbx
  void (__fastcall *v23)(__int64, __int64, HSTRING, __int64, __int64, _DWORD); // rsi
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rax
  unsigned int v29; // ebx
  __int64 v30; // rdi
  __int64 v31; // r9
  __int64 v32; // rdi
  void (__fastcall *v33)(__int64, __int64, HSTRING, __int64); // r14
  __int64 v34; // rdx
  __int64 v35; // rsi
  __int64 v36; // r9
  unsigned int v37; // esi
  __int64 v38; // rdi
  __int64 v39; // r14
  __int64 v40; // rdi
  void (__fastcall *v41)(__int64, __int64, HSTRING, __int64); // r12
  __int64 v42; // rdx
  __int64 v43; // r9
  bool v44; // r14
  __int64 v45; // rbx
  __int64 v46; // rdi
  unsigned int v47; // eax
  int v48; // edx
  __int64 v49; // rbx
  __int64 v50; // rdi
  __int64 v51; // rbx
  void (__fastcall *v52)(__int64, __int64, HSTRING, __int64, __int64, int); // rsi
  __int64 v53; // rdx
  __int64 v54; // rdi
  __int64 v55; // r9
  int v56; // [rsp+20h] [rbp-188h]
  int v57[2]; // [rsp+20h] [rbp-188h]
  __int64 v58; // [rsp+28h] [rbp-180h]
  int v59[2]; // [rsp+40h] [rbp-168h] BYREF
  __int64 v60; // [rsp+48h] [rbp-160h] BYREF
  __int64 v61; // [rsp+50h] [rbp-158h] BYREF
  unsigned __int16 *v62; // [rsp+58h] [rbp-150h] BYREF
  __int64 v63; // [rsp+60h] [rbp-148h] BYREF
  _QWORD v64[2]; // [rsp+68h] [rbp-140h] BYREF
  _BYTE v65[8]; // [rsp+78h] [rbp-130h] BYREF
  _BYTE v66[8]; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v67[8]; // [rsp+88h] [rbp-120h] BYREF
  _BYTE v68[16]; // [rsp+90h] [rbp-118h] BYREF
  _DWORD v69[2]; // [rsp+A0h] [rbp-108h] BYREF
  PCWSTR StringRawBuffer; // [rsp+A8h] [rbp-100h]
  PCWSTR v71; // [rsp+B8h] [rbp-F0h]
  int v72; // [rsp+C0h] [rbp-E8h]
  __int128 v73; // [rsp+E0h] [rbp-C8h] BYREF
  __int64 v74; // [rsp+F0h] [rbp-B8h]
  __int64 v75; // [rsp+F8h] [rbp-B0h]
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp-A8h] BYREF
  __int64 v77; // [rsp+118h] [rbp-90h]
  _QWORD v78[2]; // [rsp+120h] [rbp-88h] BYREF
  char v79; // [rsp+130h] [rbp-78h]
  int v80; // [rsp+134h] [rbp-74h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
    &v60,
    L"DeviceManagementUtilities.SendMdmAlertMessage",
    -1);
  if ( a2 )
  {
    if ( a3 )
    {
      v73 = 0;
      v74 = 0;
      v75 = 7;
      LOWORD(v73) = 0;
      v61 = 0;
      v77 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"ModernDeployment.Autopilot.Core.AutopilotLogging",
        0x31u,
        0x30u);
      v9 = Windows::Foundation::ActivateInstance<ModernDeployment::Autopilot::Core::IAutopilotLogging>(v77, &v61);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v59[0] = 0;
        IsSyncSchedulingDisabledByPolicy = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncSchedulingDisabledByPolicy(v59);
        v12 = IsSyncSchedulingDisabledByPolicy;
        if ( IsSyncSchedulingDisabledByPolicy >= 0 )
        {
          if ( v59[0] )
          {
            v13 = v61;
            v14 = *(void (__fastcall **)(__int64, __int64, HSTRING, _QWORD, __int64, int))(*(_QWORD *)v61 + 48LL);
            v15 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                               v59,
                               L"DisabledByPolicy",
                               -1);
            v16 = (_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                              &v63,
                              L"PolicyPrecheck",
                              -1);
            v14(v13, v60, a2, *v16, v15, -2147024891);
            Windows::Internal::String::~String((Windows::Internal::String *)&v63);
            Windows::Internal::String::~String((Windows::Internal::String *)v59);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
            std::wstring::_Tidy_deallocate(&v73);
            Windows::Internal::String::~String((Windows::Internal::String *)&v60);
            return 2147942405LL;
          }
          else
          {
            v62 = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v62,
              0);
            DmGetActiveUserSid(&v62);
            std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v64);
            EnrollmentIds = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentIds(v64);
            v18 = EnrollmentIds;
            if ( EnrollmentIds >= 0 )
            {
              memset_0(v69, 0, 0x40u);
              v69[0] = 64;
              v69[1] = 1224;
              StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
              v72 = 1;
              if ( a4 )
                v19 = WindowsGetStringRawBuffer(a4, 0);
              else
                v19 = L"<nullptr>";
              v71 = v19;
              v74 = 0;
              *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73) = 0;
              v20 = v64[1];
              v21 = v62 != 0;
              std::wstring::wstring(
                &hstringHeader,
                L"User SID count = %d; management server ID count = %d; alert type = %s; alert data = %s");
              ModernDeployment::Autopilot::Core::DeviceManagementUtilities::FormatString(
                &hstringHeader,
                &v73,
                v21,
                v20,
                StringRawBuffer,
                v71);
              std::wstring::_Tidy_deallocate(&hstringHeader);
              v22 = v61;
              v23 = *(void (__fastcall **)(__int64, __int64, HSTRING, __int64, __int64, _DWORD))(*(_QWORD *)v61 + 48LL);
              v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73);
              v25 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                 v59,
                                 v24,
                                 -1);
              v26 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                 &v63,
                                 L"Starting",
                                 -1);
              v23(v22, v60, a2, v26, v25, 0);
              Windows::Internal::String::~String((Windows::Internal::String *)&v63);
              Windows::Internal::String::~String((Windows::Internal::String *)v59);
              v27 = *(_QWORD *)v64[0];
              v63 = *(_QWORD *)v64[0];
              while ( !*(_BYTE *)(v27 + 25) )
              {
                std::wstring::wstring(&hstringHeader, v27 + 32);
                *(_QWORD *)v59 = 0;
                v78[0] = v59;
                v78[1] = 0;
                v79 = 1;
                v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                LODWORD(v58) = 1;
                v29 = OmaDmInitiateSessionFullSync(v62, v28, 1);
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v78);
                if ( ((v29 + 0x80000000) & 0x80000000) == 0 && v29 != -2102656508 )
                {
                  v74 = 0;
                  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73) = 0;
                  v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                  std::wstring::wstring(v78, L"EnrollmentId = %s");
                  ModernDeployment::Autopilot::Core::DeviceManagementUtilities::FormatString(
                    v78,
                    &v73,
                    v30,
                    v31,
                    v69,
                    v58);
                  std::wstring::_Tidy_deallocate(v78);
                  v32 = v61;
                  v33 = *(void (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v61 + 48LL);
                  v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73);
                  v35 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                     v65,
                                     v34,
                                     -1);
                  v36 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                     &v63,
                                     L"FailedToStartSyncSession",
                                     -1);
                  v33(v32, v60, a2, v36);
                  Windows::Internal::String::~String((Windows::Internal::String *)&v63);
                  Windows::Internal::String::~String((Windows::Internal::String *)v65);
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x26B,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                    (const char *)v29,
                    v35);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v59);
                  std::wstring::_Tidy_deallocate(&hstringHeader);
                  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                    v64,
                    v64);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v62);
                  wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                  std::wstring::_Tidy_deallocate(&v73);
                  Windows::Internal::String::~String((Windows::Internal::String *)&v60);
                  return v29;
                }
                v37 = 0;
                v74 = 0;
                *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73) = 0;
                v38 = *(_QWORD *)v59;
                v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                std::wstring::wstring(v78, L"EnrollmentId = %s, SyncSessionId = %s");
                ModernDeployment::Autopilot::Core::DeviceManagementUtilities::FormatString(
                  v78,
                  &v73,
                  v39,
                  v38,
                  v69,
                  v58);
                std::wstring::_Tidy_deallocate(v78);
                v40 = v61;
                v41 = *(void (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v61 + 48LL);
                v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73);
                LODWORD(v58) = v29;
                *(_QWORD *)v57 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                              v66,
                                              v42,
                                              -1);
                v43 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                   v65,
                                   L"AttemptedSyncSession",
                                   -1);
                v41(v40, v60, a2, v43);
                Windows::Internal::String::~String((Windows::Internal::String *)v65);
                Windows::Internal::String::~String((Windows::Internal::String *)v66);
                while ( v37 < a5 )
                {
                  memset_0(v78, 0, 0x40u);
                  LODWORD(v78[0]) = 64;
                  if ( (int)OmaDmGetInitiationInfo(*(_QWORD *)v59, v78) >= 0 )
                  {
                    v44 = (unsigned int)(v80 - 5) <= 1;
                    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
                    {
                      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                      v46 = *(_QWORD *)v59;
                      v47 = (unsigned int)WindowsGetStringRawBuffer(a2, 0);
                      McTemplateU0zqqzz_EventWriteTransfer(v80, v48, v47, v44, v80, v46, v45);
                    }
                    if ( v44 )
                    {
                      OmaDmFreeInitiationInfo(v78);
                      goto LABEL_32;
                    }
                  }
                  Sleep(0x1388u);
                  if ( v37 + 5000 < v37 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x251,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                      (const char *)0x80070216LL,
                      v57[0]);
                    OmaDmFreeInitiationInfo(v78);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v59);
                    std::wstring::_Tidy_deallocate(&hstringHeader);
                    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                      v64,
                      v64);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v62);
                    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                    std::wstring::_Tidy_deallocate(&v73);
                    Windows::Internal::String::~String((Windows::Internal::String *)&v60);
                    return 2147942934LL;
                  }
                  v37 += 5000;
                  OmaDmFreeInitiationInfo(v78);
                }
                v74 = 0;
                *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73) = 0;
                v49 = *(_QWORD *)v59;
                v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                std::wstring::wstring(v78, L"EnrollmentId = %s, SyncSessionId = %s");
                ModernDeployment::Autopilot::Core::DeviceManagementUtilities::FormatString(
                  v78,
                  &v73,
                  v50,
                  v49,
                  *(_QWORD *)v57,
                  v58);
                std::wstring::_Tidy_deallocate(v78);
                v51 = v61;
                v52 = *(void (__fastcall **)(__int64, __int64, HSTRING, __int64, __int64, int))(*(_QWORD *)v61 + 48LL);
                v53 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v73);
                v54 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                   v68,
                                   v53,
                                   -1);
                v55 = *(_QWORD *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                   v67,
                                   L"SyncSessionTimedOut",
                                   -1);
                v52(v51, v60, a2, v55, v54, -2147023436);
                Windows::Internal::String::~String((Windows::Internal::String *)v67);
                Windows::Internal::String::~String((Windows::Internal::String *)v68);
LABEL_32:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v59);
                std::wstring::_Tidy_deallocate(&hstringHeader);
                std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v63);
                v27 = v63;
              }
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v64,
                v64);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v62);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
              std::wstring::_Tidy_deallocate(&v73);
              Windows::Internal::String::~String((Windows::Internal::String *)&v60);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1F9,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
                (const char *)(unsigned int)EnrollmentIds,
                v56);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v64,
                v64);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v62);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
              std::wstring::_Tidy_deallocate(&v73);
              Windows::Internal::String::~String((Windows::Internal::String *)&v60);
              return v18;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E4,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
            (const char *)(unsigned int)IsSyncSchedulingDisabledByPolicy,
            v56);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
          std::wstring::_Tidy_deallocate(&v73);
          Windows::Internal::String::~String((Windows::Internal::String *)&v60);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
          (const char *)(unsigned int)v9,
          v56);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
        std::wstring::_Tidy_deallocate(&v73);
        Windows::Internal::String::~String((Windows::Internal::String *)&v60);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
        (const char *)0x80070057LL,
        v56);
      Windows::Internal::String::~String((Windows::Internal::String *)&v60);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
      (const char *)0x80070057LL,
      v56);
    Windows::Internal::String::~String((Windows::Internal::String *)&v60);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800a6470  push    rbx
0x1800a6472  push    rsi
0x1800a6473  push    rdi
0x1800a6474  push    r12
0x1800a6476  push    r13
0x1800a6478  push    r14
0x1800a647a  push    r15
0x1800a647c  sub     rsp, 170h
0x1800a6483  mov     rax, cs:__security_cookie
0x1800a648a  xor     rax, rsp
0x1800a648d  mov     [rsp+1A8h+var_48], rax
0x1800a6495  mov     rsi, r9
0x1800a6498  mov     rdi, r8
0x1800a649b  mov     r15, rdx
0x1800a649e  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a64a2  mov     r8, r12
0x1800a64a5  lea     rdx, aDevicemanageme; "DeviceManagementUtilities.SendMdmAlertM"...
0x1800a64ac  lea     rcx, [rsp+1A8h+var_160]
0x1800a64b1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a64b6  nop
0x1800a64b7  xor     r13d, r13d
0x1800a64ba  test    r15, r15
0x1800a64bd  jnz     short loc_1800A64F2
0x1800a64bf  mov     rcx, [rsp+1A8h]; this
0x1800a64c7  mov     ebx, 80070057h
0x1800a64cc  mov     r9d, ebx; char *
0x1800a64cf  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a64d6  mov     edx, 1D8h; void *
0x1800a64db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a64e0  nop
0x1800a64e1  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a64e6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a64eb  mov     eax, ebx
0x1800a64ed  jmp     loc_1800A6EC2
0x1800a64f2  test    rdi, rdi
0x1800a64f5  jnz     short loc_1800A652A
0x1800a64f7  mov     rcx, [rsp+1A8h]; this
0x1800a64ff  mov     ebx, 80070057h
0x1800a6504  mov     r9d, ebx; char *
0x1800a6507  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a650e  mov     edx, 1D9h; void *
0x1800a6513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6518  nop
0x1800a6519  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a651e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6523  mov     eax, ebx
0x1800a6525  jmp     loc_1800A6EC2
0x1800a652a  xorps   xmm0, xmm0
0x1800a652d  movups  [rsp+1A8h+var_C8], xmm0
0x1800a6535  mov     [rsp+1A8h+var_B8], r13
0x1800a653d  mov     [rsp+1A8h+var_B0], 7
0x1800a6549  mov     word ptr [rsp+1A8h+var_C8], r13w
0x1800a6552  mov     [rsp+1A8h+var_158], r13
0x1800a6557  mov     [rsp+1A8h+var_90], r13
0x1800a655f  mov     r9d, 30h ; '0'; unsigned int
0x1800a6565  lea     r8d, [r9+1]; unsigned int
0x1800a6569  lea     rdx, ?RuntimeClass_ModernDeployment_Autopilot_Core_AutopilotLogging@@3QBGB; "ModernDeployment.Autopilot.Core.Autopil"...
0x1800a6570  lea     rcx, [rsp+1A8h+hstringHeader]; hstringHeader
0x1800a6578  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a657d  nop
0x1800a657e  lea     rdx, [rsp+1A8h+var_158]
0x1800a6583  mov     rcx, [rsp+1A8h+var_90]
0x1800a658b  call    ??$ActivateInstance@UIAutopilotLogging@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAutopilotLogging@Core@Autopilot@ModernDeployment@@@Z; Windows::Foundation::ActivateInstance<ModernDeployment::Autopilot::Core::IAutopilotLogging>(HSTRING__ *,ModernDeployment::Autopilot::Core::IAutopilotLogging * *)
0x1800a6590  mov     ebx, eax
0x1800a6592  test    eax, eax
0x1800a6594  jns     short loc_1800A65DD
0x1800a6596  mov     rcx, [rsp+1A8h]; this
0x1800a659e  mov     r9d, eax; char *
0x1800a65a1  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a65a8  mov     edx, 1E0h; void *
0x1800a65ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a65b2  nop
0x1800a65b3  lea     rcx, [rsp+1A8h+var_158]
0x1800a65b8  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a65bd  nop
0x1800a65be  lea     rcx, [rsp+1A8h+var_C8]
0x1800a65c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a65cb  nop
0x1800a65cc  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a65d1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a65d6  mov     eax, ebx
0x1800a65d8  jmp     loc_1800A6EC2
0x1800a65dd  mov     [rsp+1A8h+var_168], r13d
0x1800a65e2  lea     rcx, [rsp+1A8h+var_168]; int *
0x1800a65e7  call    ?IsSyncSchedulingDisabledByPolicy@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncSchedulingDisabledByPolicy(int &)
0x1800a65ec  mov     ebx, eax
0x1800a65ee  test    eax, eax
0x1800a65f0  jns     short loc_1800A6639
0x1800a65f2  mov     rcx, [rsp+1A8h]; this
0x1800a65fa  mov     r9d, eax; char *
0x1800a65fd  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a6604  mov     edx, 1E4h; void *
0x1800a6609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a660e  nop
0x1800a660f  lea     rcx, [rsp+1A8h+var_158]
0x1800a6614  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a6619  nop
0x1800a661a  lea     rcx, [rsp+1A8h+var_C8]
0x1800a6622  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6627  nop
0x1800a6628  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a662d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6632  mov     eax, ebx
0x1800a6634  jmp     loc_1800A6EC2
0x1800a6639  cmp     [rsp+1A8h+var_168], r13d
0x1800a663e  jz      loc_1800A66E4
0x1800a6644  mov     rbx, [rsp+1A8h+var_158]
0x1800a6649  mov     rax, [rbx]
0x1800a664c  mov     rsi, [rax+30h]
0x1800a6650  mov     r8, r12
0x1800a6653  lea     rdx, aDisabledbypoli; "DisabledByPolicy"
0x1800a665a  lea     rcx, [rsp+1A8h+var_168]
0x1800a665f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a6664  nop
0x1800a6665  mov     rdi, [rax]
0x1800a6668  mov     r8, r12
0x1800a666b  lea     rdx, aPolicyprecheck; "PolicyPrecheck"
0x1800a6672  lea     rcx, [rsp+1A8h+var_148]
0x1800a6677  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a667c  nop
0x1800a667d  mov     dword ptr [rsp+1A8h+var_180], 80070005h
0x1800a6685  mov     qword ptr [rsp+1A8h+var_188], rdi
0x1800a668a  mov     r9, [rax]
0x1800a668d  mov     r8, r15
0x1800a6690  mov     rdx, [rsp+1A8h+var_160]
0x1800a6695  mov     rcx, rbx
0x1800a6698  mov     rax, rsi
0x1800a669b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a66a0  nop
0x1800a66a1  lea     rcx, [rsp+1A8h+var_148]; this
0x1800a66a6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a66ab  nop
0x1800a66ac  lea     rcx, [rsp+1A8h+var_168]; this
0x1800a66b1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a66b6  nop
0x1800a66b7  lea     rcx, [rsp+1A8h+var_158]
0x1800a66bc  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a66c1  nop
0x1800a66c2  lea     rcx, [rsp+1A8h+var_C8]
0x1800a66ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a66cf  nop
0x1800a66d0  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a66d5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a66da  mov     eax, 80070005h
0x1800a66df  jmp     loc_1800A6EC2
0x1800a66e4  mov     [rsp+1A8h+var_150], r13
0x1800a66e9  xor     edx, edx
0x1800a66eb  lea     rcx, [rsp+1A8h+var_150]
0x1800a66f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a66f5  lea     rcx, [rsp+1A8h+var_150]
0x1800a66fa  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a6700  lea     rcx, [rsp+1A8h+var_140]
0x1800a6705  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800a670a  nop
0x1800a670b  lea     rcx, [rsp+1A8h+var_140]
0x1800a6710  call    ?GetEnrollmentIds@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentIds(std::map<std::wstring,std::wstring> &)
0x1800a6715  mov     ebx, eax
0x1800a6717  test    eax, eax
0x1800a6719  jns     short loc_1800A677D
0x1800a671b  mov     rcx, [rsp+1A8h]; this
0x1800a6723  mov     r9d, eax; char *
0x1800a6726  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a672d  mov     edx, 1F9h; void *
0x1800a6732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6737  nop
0x1800a6738  lea     rdx, [rsp+1A8h+var_140]
0x1800a673d  lea     rcx, [rsp+1A8h+var_140]
0x1800a6742  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1800a6747  nop
0x1800a6748  lea     rcx, [rsp+1A8h+var_150]
0x1800a674d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6752  nop
0x1800a6753  lea     rcx, [rsp+1A8h+var_158]
0x1800a6758  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a675d  nop
0x1800a675e  lea     rcx, [rsp+1A8h+var_C8]
0x1800a6766  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a676b  nop
0x1800a676c  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a6771  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a6776  mov     eax, ebx
0x1800a6778  jmp     loc_1800A6EC2
0x1800a677d  mov     ebx, 40h ; '@'
0x1800a6782  mov     r8d, ebx; Size
0x1800a6785  xor     edx, edx; Val
0x1800a6787  lea     rcx, [rsp+1A8h+var_108]; void *
0x1800a678f  call    memset_0
0x1800a6794  mov     [rsp+1A8h+var_108], ebx
0x1800a679b  mov     [rsp+1A8h+var_104], 4C8h
0x1800a67a6  xor     edx, edx; length
0x1800a67a8  mov     rcx, rdi; string
0x1800a67ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a67b1  mov     [rsp+1A8h+var_100], rax
0x1800a67b9  mov     [rsp+1A8h+var_E8], 1
0x1800a67c4  test    rsi, rsi
0x1800a67c7  jnz     short loc_1800A67D2
0x1800a67c9  lea     rax, ?c_NullPtrString@@3QBGB; "<nullptr>"
0x1800a67d0  jmp     short loc_1800A67DD
0x1800a67d2  xor     edx, edx; length
0x1800a67d4  mov     rcx, rsi; string
0x1800a67d7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a67dd  mov     [rsp+1A8h+var_F0], rax
0x1800a67e5  mov     [rsp+1A8h+var_B8], r13
0x1800a67ed  lea     rcx, [rsp+1A8h+var_C8]
0x1800a67f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a67fa  mov     [rax], r13w
0x1800a67fe  mov     rdi, [rsp+1A8h+var_138]
0x1800a6803  mov     ebx, r13d
0x1800a6806  cmp     [rsp+1A8h+var_150], r13
0x1800a680b  setnz   bl
0x1800a680e  lea     rdx, aUserSidCountDM; "User SID count = %d; management server "...
0x1800a6815  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a681d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a6822  nop
0x1800a6823  mov     rax, [rsp+1A8h+var_F0]
0x1800a682b  mov     [rsp+1A8h+var_180], rax
0x1800a6830  mov     rax, [rsp+1A8h+var_100]
0x1800a6838  mov     qword ptr [rsp+1A8h+var_188], rax
0x1800a683d  mov     r9, rdi
0x1800a6840  mov     r8d, ebx
0x1800a6843  lea     rdx, [rsp+1A8h+var_C8]
0x1800a684b  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a6853  call    ?FormatString@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV56@ZZ; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::FormatString(std::wstring const &,std::wstring *,...)
0x1800a6858  nop
0x1800a6859  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a6861  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6866  mov     rbx, [rsp+1A8h+var_158]
0x1800a686b  mov     rax, [rbx]
0x1800a686e  mov     rsi, [rax+30h]
0x1800a6872  lea     rcx, [rsp+1A8h+var_C8]
0x1800a687a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a687f  mov     rdx, rax
0x1800a6882  mov     r8, r12
0x1800a6885  lea     rcx, [rsp+1A8h+var_168]
0x1800a688a  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a688f  nop
0x1800a6890  mov     rdi, [rax]
0x1800a6893  mov     r8, r12
0x1800a6896  lea     rdx, aStarting; "Starting"
0x1800a689d  lea     rcx, [rsp+1A8h+var_148]
0x1800a68a2  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a68a7  nop
0x1800a68a8  mov     dword ptr [rsp+1A8h+var_180], r13d
0x1800a68ad  mov     qword ptr [rsp+1A8h+var_188], rdi
0x1800a68b2  mov     r9, [rax]
0x1800a68b5  mov     r8, r15
0x1800a68b8  mov     rdx, [rsp+1A8h+var_160]
0x1800a68bd  mov     rcx, rbx
0x1800a68c0  mov     rax, rsi
0x1800a68c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a68c8  nop
0x1800a68c9  lea     rcx, [rsp+1A8h+var_148]; this
0x1800a68ce  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a68d3  nop
0x1800a68d4  lea     rcx, [rsp+1A8h+var_168]; this
0x1800a68d9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a68de  mov     rdx, [rsp+1A8h+var_140]
0x1800a68e3  mov     rdx, [rdx]
0x1800a68e6  mov     [rsp+1A8h+var_148], rdx
0x1800a68eb  mov     edi, 80000000h
0x1800a68f0  cmp     [rdx+19h], r13b
0x1800a68f4  jnz     loc_1800A6E7C
0x1800a68fa  add     rdx, 20h ; ' '
0x1800a68fe  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a6906  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a690b  nop
0x1800a690c  mov     qword ptr [rsp+1A8h+var_168], r13
0x1800a6911  lea     rax, [rsp+1A8h+var_168]
0x1800a6916  mov     [rsp+1A8h+var_88], rax
0x1800a691e  mov     [rsp+1A8h+var_80], r13
0x1800a6926  mov     [rsp+1A8h+var_78], 1
0x1800a692e  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a6936  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a693b  mov     rdx, rax
0x1800a693e  mov     [rsp+1A8h+var_170], 18h
0x1800a6946  lea     rax, [rsp+1A8h+var_80]
0x1800a694e  mov     [rsp+1A8h+var_178], rax
0x1800a6953  mov     dword ptr [rsp+1A8h+var_180], 1
0x1800a695b  lea     rax, [rsp+1A8h+var_108]
0x1800a6963  mov     qword ptr [rsp+1A8h+var_188], rax
0x1800a6968  mov     r9d, 2
0x1800a696e  lea     r8d, [r9-1]
0x1800a6972  mov     rcx, [rsp+1A8h+var_150]
0x1800a6977  call    cs:__imp_OmaDmInitiateSessionFullSync
0x1800a697d  mov     ebx, eax
0x1800a697f  lea     rcx, [rsp+1A8h+var_88]
0x1800a6987  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a698c  lea     ecx, [rbx+rdi]
0x1800a698f  test    edi, ecx
0x1800a6991  jnz     loc_1800A6AF9
0x1800a6997  cmp     ebx, 82AC0204h
0x1800a699d  jz      loc_1800A6AF9
0x1800a69a3  mov     [rsp+1A8h+var_B8], r13
0x1800a69ab  lea     rcx, [rsp+1A8h+var_C8]
0x1800a69b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a69b8  mov     [rax], r13w
0x1800a69bc  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a69c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a69c9  mov     rdi, rax
0x1800a69cc  lea     rdx, aEnrollmentidS; "EnrollmentId = %s"
  ... truncated ...
```
