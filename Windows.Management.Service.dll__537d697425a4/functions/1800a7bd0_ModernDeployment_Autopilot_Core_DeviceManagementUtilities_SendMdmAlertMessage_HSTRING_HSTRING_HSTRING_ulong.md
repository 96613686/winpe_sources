# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::SendMdmAlertMessage(HSTRING__ *,HSTRING__ *,HSTRING__ *,ulong)

- ea: `0x1800a7bd0`
- end: `0x1800a8682`
- name: `?SendMdmAlertMessage@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJPEAUHSTRING__@@00K@Z`
- size: `2738`
- prototype: `int(ModernDeployment::Autopilot::Core::DeviceManagementUtilities *__hidden this, HSTRING, HSTRING, HSTRING, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006cb94`
- `0x18006e43c`
- `0x180077de0`
- `0x180080bac`
- `0x180081cac`
- `0x180084574`
- `0x180086044`
- `0x18008aea8`
- `0x18008aecc`
- `0x18008d620`
- `0x1800a2b18`
- `0x1800a35a8`
- `0x1800a4824`
- `0x1800a48b4`
- `0x1800a5544`
- `0x1800a5ce4`
- `0x1800a6300`
- `0x1800a7bd0`
- `0x1800a9c3c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a8412`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a8412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a83db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a83db`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a7e5a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a7e5a`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a8397`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x1800a8397`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a8432`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a844b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a8489`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a8432`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a844b`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1800a8489`
- `omadmapi!__imp_OmaDmInitiateSessionFullSync` at `0x1800a80e9`
- `omadmapi!__imp_OmaDmInitiateSessionFullSync` at `0x1800a80e9`

## string_xrefs

- `0x1800a7c2f`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7c67`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7d01`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7d5d`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7e8c`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a8201`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a8470`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a7f80`: `User SID count = %d; management server ID count = %d; alert type = %s; alert data = %s`
- `0x1800a8315`: `AttemptedSyncSession`

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
0x1800a7bd0  push    rbx
0x1800a7bd2  push    rsi
0x1800a7bd3  push    rdi
0x1800a7bd4  push    r12
0x1800a7bd6  push    r13
0x1800a7bd8  push    r14
0x1800a7bda  push    r15
0x1800a7bdc  sub     rsp, 170h
0x1800a7be3  mov     rax, cs:__security_cookie
0x1800a7bea  xor     rax, rsp
0x1800a7bed  mov     [rsp+1A8h+var_48], rax
0x1800a7bf5  mov     rsi, r9
0x1800a7bf8  mov     rdi, r8
0x1800a7bfb  mov     r15, rdx
0x1800a7bfe  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a7c02  mov     r8, r12
0x1800a7c05  lea     rdx, aDevicemanageme; "DeviceManagementUtilities.SendMdmAlertM"...
0x1800a7c0c  lea     rcx, [rsp+1A8h+var_160]
0x1800a7c11  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a7c16  nop
0x1800a7c17  xor     r13d, r13d
0x1800a7c1a  test    r15, r15
0x1800a7c1d  jnz     short loc_1800A7C52
0x1800a7c1f  mov     rcx, [rsp+1A8h]; this
0x1800a7c27  mov     ebx, 80070057h
0x1800a7c2c  mov     r9d, ebx; char *
0x1800a7c2f  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7c36  mov     edx, 1D8h; void *
0x1800a7c3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7c40  nop
0x1800a7c41  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a7c46  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7c4b  mov     eax, ebx
0x1800a7c4d  jmp     loc_1800A865E
0x1800a7c52  test    rdi, rdi
0x1800a7c55  jnz     short loc_1800A7C8A
0x1800a7c57  mov     rcx, [rsp+1A8h]; this
0x1800a7c5f  mov     ebx, 80070057h
0x1800a7c64  mov     r9d, ebx; char *
0x1800a7c67  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7c6e  mov     edx, 1D9h; void *
0x1800a7c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7c78  nop
0x1800a7c79  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a7c7e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7c83  mov     eax, ebx
0x1800a7c85  jmp     loc_1800A865E
0x1800a7c8a  xorps   xmm0, xmm0
0x1800a7c8d  movups  [rsp+1A8h+var_C8], xmm0
0x1800a7c95  mov     [rsp+1A8h+var_B8], r13
0x1800a7c9d  mov     [rsp+1A8h+var_B0], 7
0x1800a7ca9  mov     word ptr [rsp+1A8h+var_C8], r13w
0x1800a7cb2  mov     [rsp+1A8h+var_158], r13
0x1800a7cb7  mov     [rsp+1A8h+var_90], r13
0x1800a7cbf  mov     r9d, 30h ; '0'; unsigned int
0x1800a7cc5  lea     r8d, [r9+1]; unsigned int
0x1800a7cc9  lea     rdx, ?RuntimeClass_ModernDeployment_Autopilot_Core_AutopilotLogging@@3QBGB; "ModernDeployment.Autopilot.Core.Autopil"...
0x1800a7cd0  lea     rcx, [rsp+1A8h+hstringHeader]; hstringHeader
0x1800a7cd8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a7cdd  nop
0x1800a7cde  lea     rdx, [rsp+1A8h+var_158]
0x1800a7ce3  mov     rcx, [rsp+1A8h+var_90]
0x1800a7ceb  call    ??$ActivateInstance@UIAutopilotLogging@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAutopilotLogging@Core@Autopilot@ModernDeployment@@@Z; Windows::Foundation::ActivateInstance<ModernDeployment::Autopilot::Core::IAutopilotLogging>(HSTRING__ *,ModernDeployment::Autopilot::Core::IAutopilotLogging * *)
0x1800a7cf0  mov     ebx, eax
0x1800a7cf2  test    eax, eax
0x1800a7cf4  jns     short loc_1800A7D3D
0x1800a7cf6  mov     rcx, [rsp+1A8h]; this
0x1800a7cfe  mov     r9d, eax; char *
0x1800a7d01  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7d08  mov     edx, 1E0h; void *
0x1800a7d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7d12  nop
0x1800a7d13  lea     rcx, [rsp+1A8h+var_158]
0x1800a7d18  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a7d1d  nop
0x1800a7d1e  lea     rcx, [rsp+1A8h+var_C8]
0x1800a7d26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7d2b  nop
0x1800a7d2c  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a7d31  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7d36  mov     eax, ebx
0x1800a7d38  jmp     loc_1800A865E
0x1800a7d3d  mov     [rsp+1A8h+var_168], r13d
0x1800a7d42  lea     rcx, [rsp+1A8h+var_168]; int *
0x1800a7d47  call    ?IsSyncSchedulingDisabledByPolicy@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEAH@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::IsSyncSchedulingDisabledByPolicy(int &)
0x1800a7d4c  mov     ebx, eax
0x1800a7d4e  test    eax, eax
0x1800a7d50  jns     short loc_1800A7D99
0x1800a7d52  mov     rcx, [rsp+1A8h]; this
0x1800a7d5a  mov     r9d, eax; char *
0x1800a7d5d  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7d64  mov     edx, 1E4h; void *
0x1800a7d69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7d6e  nop
0x1800a7d6f  lea     rcx, [rsp+1A8h+var_158]
0x1800a7d74  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a7d79  nop
0x1800a7d7a  lea     rcx, [rsp+1A8h+var_C8]
0x1800a7d82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7d87  nop
0x1800a7d88  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a7d8d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7d92  mov     eax, ebx
0x1800a7d94  jmp     loc_1800A865E
0x1800a7d99  cmp     [rsp+1A8h+var_168], r13d
0x1800a7d9e  jz      loc_1800A7E44
0x1800a7da4  mov     rbx, [rsp+1A8h+var_158]
0x1800a7da9  mov     rax, [rbx]
0x1800a7dac  mov     rsi, [rax+30h]
0x1800a7db0  mov     r8, r12
0x1800a7db3  lea     rdx, aDisabledbypoli; "DisabledByPolicy"
0x1800a7dba  lea     rcx, [rsp+1A8h+var_168]
0x1800a7dbf  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a7dc4  nop
0x1800a7dc5  mov     rdi, [rax]
0x1800a7dc8  mov     r8, r12
0x1800a7dcb  lea     rdx, aPolicyprecheck; "PolicyPrecheck"
0x1800a7dd2  lea     rcx, [rsp+1A8h+var_148]
0x1800a7dd7  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a7ddc  nop
0x1800a7ddd  mov     dword ptr [rsp+1A8h+var_180], 80070005h
0x1800a7de5  mov     qword ptr [rsp+1A8h+var_188], rdi
0x1800a7dea  mov     r9, [rax]
0x1800a7ded  mov     r8, r15
0x1800a7df0  mov     rdx, [rsp+1A8h+var_160]
0x1800a7df5  mov     rcx, rbx
0x1800a7df8  mov     rax, rsi
0x1800a7dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e00  nop
0x1800a7e01  lea     rcx, [rsp+1A8h+var_148]; this
0x1800a7e06  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7e0b  nop
0x1800a7e0c  lea     rcx, [rsp+1A8h+var_168]; this
0x1800a7e11  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7e16  nop
0x1800a7e17  lea     rcx, [rsp+1A8h+var_158]
0x1800a7e1c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a7e21  nop
0x1800a7e22  lea     rcx, [rsp+1A8h+var_C8]
0x1800a7e2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7e2f  nop
0x1800a7e30  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a7e35  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7e3a  mov     eax, 80070005h
0x1800a7e3f  jmp     loc_1800A865E
0x1800a7e44  mov     [rsp+1A8h+var_150], r13
0x1800a7e49  xor     edx, edx
0x1800a7e4b  lea     rcx, [rsp+1A8h+var_150]
0x1800a7e50  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a7e55  lea     rcx, [rsp+1A8h+var_150]
0x1800a7e5a  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a7e61  nop     dword ptr [rax+rax+00h]
0x1800a7e66  lea     rcx, [rsp+1A8h+var_140]
0x1800a7e6b  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800a7e70  nop
0x1800a7e71  lea     rcx, [rsp+1A8h+var_140]
0x1800a7e76  call    ?GetEnrollmentIds@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentIds(std::map<std::wstring,std::wstring> &)
0x1800a7e7b  mov     ebx, eax
0x1800a7e7d  test    eax, eax
0x1800a7e7f  jns     short loc_1800A7EE3
0x1800a7e81  mov     rcx, [rsp+1A8h]; this
0x1800a7e89  mov     r9d, eax; char *
0x1800a7e8c  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a7e93  mov     edx, 1F9h; void *
0x1800a7e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7e9d  nop
0x1800a7e9e  lea     rdx, [rsp+1A8h+var_140]
0x1800a7ea3  lea     rcx, [rsp+1A8h+var_140]
0x1800a7ea8  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1800a7ead  nop
0x1800a7eae  lea     rcx, [rsp+1A8h+var_150]
0x1800a7eb3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a7eb8  nop
0x1800a7eb9  lea     rcx, [rsp+1A8h+var_158]
0x1800a7ebe  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800a7ec3  nop
0x1800a7ec4  lea     rcx, [rsp+1A8h+var_C8]
0x1800a7ecc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7ed1  nop
0x1800a7ed2  lea     rcx, [rsp+1A8h+var_160]; this
0x1800a7ed7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a7edc  mov     eax, ebx
0x1800a7ede  jmp     loc_1800A865E
0x1800a7ee3  mov     ebx, 40h ; '@'
0x1800a7ee8  mov     r8d, ebx; Size
0x1800a7eeb  xor     edx, edx; Val
0x1800a7eed  lea     rcx, [rsp+1A8h+var_108]; void *
0x1800a7ef5  call    memset_0
0x1800a7efa  mov     [rsp+1A8h+var_108], ebx
0x1800a7f01  mov     [rsp+1A8h+var_104], 4C8h
0x1800a7f0c  xor     edx, edx; length
0x1800a7f0e  mov     rcx, rdi; string
0x1800a7f11  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7f18  nop     dword ptr [rax+rax+00h]
0x1800a7f1d  mov     [rsp+1A8h+var_100], rax
0x1800a7f25  mov     [rsp+1A8h+var_E8], 1
0x1800a7f30  test    rsi, rsi
0x1800a7f33  jnz     short loc_1800A7F3E
0x1800a7f35  lea     rax, ?c_NullPtrString@@3QBGB; "<nullptr>"
0x1800a7f3c  jmp     short loc_1800A7F4F
0x1800a7f3e  xor     edx, edx; length
0x1800a7f40  mov     rcx, rsi; string
0x1800a7f43  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7f4a  nop     dword ptr [rax+rax+00h]
0x1800a7f4f  mov     [rsp+1A8h+var_F0], rax
0x1800a7f57  mov     [rsp+1A8h+var_B8], r13
0x1800a7f5f  lea     rcx, [rsp+1A8h+var_C8]
0x1800a7f67  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7f6c  mov     [rax], r13w
0x1800a7f70  mov     rdi, [rsp+1A8h+var_138]
0x1800a7f75  mov     ebx, r13d
0x1800a7f78  cmp     [rsp+1A8h+var_150], r13
0x1800a7f7d  setnz   bl
0x1800a7f80  lea     rdx, aUserSidCountDM; "User SID count = %d; management server "...
0x1800a7f87  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a7f8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7f94  nop
0x1800a7f95  mov     rax, [rsp+1A8h+var_F0]
0x1800a7f9d  mov     [rsp+1A8h+var_180], rax
0x1800a7fa2  mov     rax, [rsp+1A8h+var_100]
0x1800a7faa  mov     qword ptr [rsp+1A8h+var_188], rax
0x1800a7faf  mov     r9, rdi
0x1800a7fb2  mov     r8d, ebx
0x1800a7fb5  lea     rdx, [rsp+1A8h+var_C8]
0x1800a7fbd  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a7fc5  call    ?FormatString@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV56@ZZ; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::FormatString(std::wstring const &,std::wstring *,...)
0x1800a7fca  nop
0x1800a7fcb  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a7fd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a7fd8  mov     rbx, [rsp+1A8h+var_158]
0x1800a7fdd  mov     rax, [rbx]
0x1800a7fe0  mov     rsi, [rax+30h]
0x1800a7fe4  lea     rcx, [rsp+1A8h+var_C8]
0x1800a7fec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7ff1  mov     rdx, rax
0x1800a7ff4  mov     r8, r12
0x1800a7ff7  lea     rcx, [rsp+1A8h+var_168]
0x1800a7ffc  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a8001  nop
0x1800a8002  mov     rdi, [rax]
0x1800a8005  mov     r8, r12
0x1800a8008  lea     rdx, aStarting; "Starting"
0x1800a800f  lea     rcx, [rsp+1A8h+var_148]
0x1800a8014  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a8019  nop
0x1800a801a  mov     dword ptr [rsp+1A8h+var_180], r13d
0x1800a801f  mov     qword ptr [rsp+1A8h+var_188], rdi
0x1800a8024  mov     r9, [rax]
0x1800a8027  mov     r8, r15
0x1800a802a  mov     rdx, [rsp+1A8h+var_160]
0x1800a802f  mov     rcx, rbx
0x1800a8032  mov     rax, rsi
0x1800a8035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a803a  nop
0x1800a803b  lea     rcx, [rsp+1A8h+var_148]; this
0x1800a8040  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a8045  nop
0x1800a8046  lea     rcx, [rsp+1A8h+var_168]; this
0x1800a804b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a8050  mov     rdx, [rsp+1A8h+var_140]
0x1800a8055  mov     rdx, [rdx]
0x1800a8058  mov     [rsp+1A8h+var_148], rdx
0x1800a805d  mov     edi, 80000000h
0x1800a8062  cmp     [rdx+19h], r13b
0x1800a8066  jnz     loc_1800A8618
0x1800a806c  add     rdx, 20h ; ' '
0x1800a8070  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a8078  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a807d  nop
0x1800a807e  mov     qword ptr [rsp+1A8h+var_168], r13
0x1800a8083  lea     rax, [rsp+1A8h+var_168]
0x1800a8088  mov     [rsp+1A8h+var_88], rax
0x1800a8090  mov     [rsp+1A8h+var_80], r13
0x1800a8098  mov     [rsp+1A8h+var_78], 1
0x1800a80a0  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800a80a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a80ad  mov     rdx, rax
0x1800a80b0  mov     [rsp+1A8h+var_170], 18h
0x1800a80b8  lea     rax, [rsp+1A8h+var_80]
0x1800a80c0  mov     [rsp+1A8h+var_178], rax
0x1800a80c5  mov     dword ptr [rsp+1A8h+var_180], 1
0x1800a80cd  lea     rax, [rsp+1A8h+var_108]
0x1800a80d5  mov     qword ptr [rsp+1A8h+var_188], rax
0x1800a80da  mov     r9d, 2
0x1800a80e0  lea     r8d, [r9-1]
0x1800a80e4  mov     rcx, [rsp+1A8h+var_150]
0x1800a80e9  call    cs:__imp_OmaDmInitiateSessionFullSync
0x1800a80f0  nop     dword ptr [rax+rax+00h]
0x1800a80f5  mov     ebx, eax
0x1800a80f7  lea     rcx, [rsp+1A8h+var_88]
0x1800a80ff  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a8104  lea     ecx, [rbx+rdi]
0x1800a8107  test    edi, ecx
0x1800a8109  jnz     loc_1800A8271
0x1800a810f  cmp     ebx, 82AC0204h
0x1800a8115  jz      loc_1800A8271
0x1800a811b  mov     [rsp+1A8h+var_B8], r13
0x1800a8123  lea     rcx, [rsp+1A8h+var_C8]
0x1800a812b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a8130  mov     [rax], r13w
  ... truncated ...
```
