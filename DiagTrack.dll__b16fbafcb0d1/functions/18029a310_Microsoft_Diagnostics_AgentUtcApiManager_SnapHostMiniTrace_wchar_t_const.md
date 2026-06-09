# Microsoft::Diagnostics::AgentUtcApiManager::SnapHostMiniTrace(wchar_t const *)

- ea: `0x18029a310`
- end: `0x18029b0e6`
- name: `?SnapHostMiniTrace@AgentUtcApiManager@Diagnostics@Microsoft@@UEAAJPEB_W@Z`
- size: `3542`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::AgentUtcApiManager *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180020150`
- `0x180022570`
- `0x1800249a0`
- `0x18002b318`
- `0x18002ba00`
- `0x18002cae0`
- `0x18002d7d0`
- `0x18002df00`
- `0x18004f698`
- `0x180052240`
- `0x180056a90`
- `0x180064e34`
- `0x180064e8c`
- `0x180085f08`
- `0x18009c8c0`
- `0x1800bc488`
- `0x1800bc508`
- `0x1800bc658`
- `0x1800be65c`
- `0x1800c53b4`
- `0x1800c5d5c`
- `0x1800cf7d8`
- `0x18010b7dc`
- `0x180140a5c`
- `0x1801b0820`
- `0x1801ba5dc`
- `0x1801bbd5c`
- `0x1801d4e24`
- `0x18020aac0`
- `0x18020aae4`
- `0x18029a310`
- `0x18029df5c`
- `0x1802b8b48`
- `0x1802f2544`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18029adc8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18029adc8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18029a3fe`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18029a3fe`

## string_xrefs

- `0x18029a35a`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a391`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a3ce`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a415`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a4b7`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a53b`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a5d3`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a708`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a908`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029a9d4`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029aab4`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029ab77`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029ac69`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029ade3`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x18029af59`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AgentUtcApiManager::SnapHostMiniTrace(
        Microsoft::Diagnostics::AgentUtcApiManager *this,
        const wchar_t *a2)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r8
  int appended; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  int Directory; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r8
  char *v17; // rdi
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r10
  __int64 v21; // r8
  struct Microsoft::Diagnostics::Agent *Agent; // rbx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // ebx
  struct Microsoft::Diagnostics::Agent *v27; // rax
  __int64 v28; // r8
  int v29; // eax
  unsigned int v30; // ebx
  struct Microsoft::Diagnostics::Agent *v31; // rax
  __int64 v32; // r8
  void **v33; // rax
  void *v34; // rcx
  struct Microsoft::Diagnostics::Agent *v35; // rax
  __int64 v36; // r8
  int v37; // ebx
  struct Microsoft::Diagnostics::Agent *v38; // rax
  __int64 v39; // r8
  __int64 v40; // rcx
  int RpcImpersonationToken; // eax
  unsigned int v42; // ebx
  struct Microsoft::Diagnostics::Agent *v43; // rax
  __int64 v44; // r8
  struct Microsoft::Diagnostics::UserManager *UserManager; // rax
  __int64 v46; // r8
  struct Microsoft::Diagnostics::UserManager *v47; // rax
  Microsoft::Diagnostics::UserManager *v48; // r8
  __int64 UserContextForSid; // rbx
  int UserToken; // eax
  unsigned int v51; // ebx
  struct Microsoft::Diagnostics::Agent *v52; // rax
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rax
  __int64 v58; // r8
  int v59; // eax
  unsigned int v60; // ebx
  struct Microsoft::Diagnostics::Agent *v61; // rax
  __int64 v62; // r8
  struct Microsoft::Diagnostics::Agent *v63; // rax
  __int64 v64; // r8
  int v65; // [rsp+20h] [rbp-188h]
  int v66; // [rsp+20h] [rbp-188h]
  int v67; // [rsp+20h] [rbp-188h]
  size_t Size; // [rsp+30h] [rbp-178h]
  size_t Sizea; // [rsp+30h] [rbp-178h]
  __int128 v70; // [rsp+40h] [rbp-168h] BYREF
  char Src; // [rsp+50h] [rbp-158h] BYREF
  char v72; // [rsp+51h] [rbp-157h] BYREF
  int v73[3]; // [rsp+52h] [rbp-156h] BYREF
  __int64 v74[2]; // [rsp+60h] [rbp-148h] BYREF
  __int64 v75[2]; // [rsp+70h] [rbp-138h] BYREF
  int v76[4]; // [rsp+80h] [rbp-128h] BYREF
  int v77[4]; // [rsp+90h] [rbp-118h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-100h]
  char v80; // [rsp+B0h] [rbp-F8h]
  __int128 v81; // [rsp+C0h] [rbp-E8h] BYREF
  __int128 v82; // [rsp+D0h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+E0h] [rbp-C8h] BYREF
  WCHAR v84[16]; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v85[32]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v86[32]; // [rsp+130h] [rbp-78h] BYREF
  _QWORD v87[4]; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( a2 )
  {
    if ( _InterlockedCompareExchange64((_QWORD *)&xmmword_180463230 + 1, 0, 0) )
    {
      if ( *((_BYTE *)Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager)
           + 192) )
      {
        pguid = GUID_NULL;
        v5 = CoCreateGuid(&pguid);
        v6 = v5;
        if ( v5 >= 0 )
        {
          Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(v84);
          v7 = Microsoft::Diagnostics::Utils::String::StringFromGuidW(v87, &pguid, 0);
          std::operator+<wchar_t>(v85, L"hostminitrace_", v7);
          std::wstring::_Tidy_deallocate(v87);
          *(_OWORD *)v74 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, &v70, v8);
          appended = Microsoft::Diagnostics::Utils::String::AppendPath(v84, v74);
          v11 = appended;
          if ( appended >= 0 )
          {
            *(_OWORD *)v74 = *(_OWORD *)&off_180385550;
            v82 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, &v70, v10);
            Directory = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(
                          (__int64)&v82,
                          0,
                          (__int128 *)v74);
            v13 = Directory;
            if ( Directory >= 0 )
            {
              *(_QWORD *)&v81 = v84;
              BYTE8(v81) = 1;
              std::wstring::wstring(v86, v84);
              *(_OWORD *)v74 = *(_OWORD *)&off_18036CE20;
              v14 = Microsoft::Diagnostics::Utils::String::AppendPath(v86, v74);
              v15 = v14;
              if ( v14 >= 0 )
              {
                v17 = (char *)operator new(0x58u);
                *(_QWORD *)v76 = v17;
                *((_DWORD *)v17 + 2) = 1;
                *((_DWORD *)v17 + 3) = 1;
                *(_QWORD *)v17 = &std::_Ref_count_obj2<Microsoft::Diagnostics::EscalationDataRequest>::`vftable';
                *(_OWORD *)v74 = *(_OWORD *)std::wstring::operator std::wstring_view(v86, &v70, v18);
                Microsoft::Diagnostics::EscalationDataRequest::EscalationDataRequest(v17 + 16, v74);
                *(_QWORD *)&v82 = v17 + 16;
                *((_QWORD *)&v82 + 1) = v17;
                Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
                  v74,
                  &v82);
                *(_OWORD *)v76 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                if ( Microsoft::Diagnostics::IAgentIoReceiver::RegisterEscalationDataRequest(
                       v20,
                       (__int64)&pguid,
                       (__int128 *)v76,
                       v19) )
                {
                  *(_QWORD *)&v70 = &pguid;
                  BYTE8(v70) = 1;
                  lpMem = 0;
                  v79 = 0;
                  v80 = 1;
                  Src = 2;
                  v74[0] = (__int64)L"tslty";
                  v74[1] = 5;
                  *(_QWORD *)v76 = &lpMem;
                  v76[2] = 0;
                  v76[3] = HIDWORD(v70);
                  LODWORD(Size) = 1;
                  JsonBuilder::AddValue((int)&lpMem, (int)v77, 0, (int)v76, (__int64)v74, 246, Size, &Src);
                  v74[0] = (__int64)L"trid";
                  v74[1] = 4;
                  *(_QWORD *)v76 = &lpMem;
                  v76[2] = 0;
                  v76[3] = v77[3];
                  LODWORD(Sizea) = 16;
                  JsonBuilder::AddValue((int)&lpMem, (int)v77, 0, (int)v76, (__int64)v74, 251, Sizea, &pguid);
                  Agent = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                  gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
                    v74,
                    lpMem,
                    4LL * (unsigned int)v79);
                  LOBYTE(v23) = 13;
                  v24 = Microsoft::Diagnostics::Agent::SendAgentMessage(Agent, v23, v74);
                  v26 = v24;
                  if ( v24 >= 0 )
                  {
                    LOBYTE(v25) = 13;
                    v29 = Microsoft::Diagnostics::AgentUtcApiManager::WaitForHostEvent(this, v25);
                    v30 = v29;
                    if ( v29 >= 0 )
                    {
                      v33 = (void **)*((_QWORD *)v17 + 6);
                      if ( v33 )
                        v34 = *v33;
                      else
                        v34 = 0;
                      if ( Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(v34, 0xEA60u) )
                      {
                        v37 = *((_DWORD *)v17 + 16);
                        if ( v37 >= 0 )
                        {
                          v75[0] = 0;
                          std::wstring::wstring(v87);
                          *(_QWORD *)v76 = 0;
                          RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(
                                                    v40,
                                                    (void **)v76,
                                                    v87);
                          v42 = RpcImpersonationToken;
                          if ( RpcImpersonationToken >= 0 )
                          {
                            UserManager = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                            *(_OWORD *)v74 = *(_OWORD *)std::wstring::operator std::wstring_view(v87, v77, UserManager);
                            if ( (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v46, v74)
                              && (v47 = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager),
                                  *(_OWORD *)v74 = *(_OWORD *)std::wstring::operator std::wstring_view(v87, v77, v47),
                                  UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v48),
                                  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                                    v75,
                                    0),
                                  UserToken = UMgrQueryUserToken(UserContextForSid, v75),
                                  v51 = UserToken,
                                  UserToken < 0) )
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0x55,
                                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                                (const char *)(unsigned int)UserToken,
                                v66);
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v76);
                              std::wstring::_Tidy_deallocate(v87);
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v75);
                              JsonInternal::PodVectorBase::Deallocate(lpMem);
                              v52 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                              v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                              Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                (__int64)v52,
                                (__int64)&pguid,
                                &v70);
                              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                              std::wstring::_Tidy_deallocate(v86);
                              v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v53);
                              Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                              std::wstring::_Tidy_deallocate(v85);
                              std::wstring::_Tidy_deallocate(v84);
                              return v51;
                            }
                            else
                            {
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v76);
                              std::wstring::_Tidy_deallocate(v87);
                              LOWORD(v73[0]) = 0;
                              v72 = 0;
                              v57 = std::_WChar_traits<wchar_t>::length(a2, v54, v55, v56);
                              v74[0] = (__int64)a2;
                              v74[1] = v57;
                              *(_OWORD *)v76 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v58);
                              v59 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
                                      (__int128 *)v76,
                                      (__int128 *)v74,
                                      v75,
                                      (_BYTE *)v73 + 1,
                                      v73,
                                      &v72);
                              v60 = v59;
                              if ( v59 >= 0 )
                              {
                                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v75);
                                JsonInternal::PodVectorBase::Deallocate(lpMem);
                                v63 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                                v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                                Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                  (__int64)v63,
                                  (__int64)&pguid,
                                  &v70);
                                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                                std::wstring::_Tidy_deallocate(v86);
                                v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v64);
                                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                                std::wstring::_Tidy_deallocate(v85);
                                std::wstring::_Tidy_deallocate(v84);
                                return 0;
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0x61,
                                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                                  (const char *)(unsigned int)v59,
                                  v67);
                                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v75);
                                JsonInternal::PodVectorBase::Deallocate(lpMem);
                                v61 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                                v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                                Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                  (__int64)v61,
                                  (__int64)&pguid,
                                  &v70);
                                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                                std::wstring::_Tidy_deallocate(v86);
                                v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v62);
                                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                                std::wstring::_Tidy_deallocate(v85);
                                std::wstring::_Tidy_deallocate(v84);
                                return v60;
                              }
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x50,
                              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                              (const char *)(unsigned int)RpcImpersonationToken,
                              v66);
                            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v76);
                            std::wstring::_Tidy_deallocate(v87);
                            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v75);
                            JsonInternal::PodVectorBase::Deallocate(lpMem);
                            v43 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                            v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                            Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                              (__int64)v43,
                              (__int64)&pguid,
                              &v70);
                            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                            std::wstring::_Tidy_deallocate(v86);
                            v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v44);
                            Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                            std::wstring::_Tidy_deallocate(v85);
                            std::wstring::_Tidy_deallocate(v84);
                            return v42;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x49,
                            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                            (const char *)(unsigned int)v37,
                            v66);
                          JsonInternal::PodVectorBase::Deallocate(lpMem);
                          v38 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                          v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                          Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                            (__int64)v38,
                            (__int64)&pguid,
                            &v70);
                          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                          std::wstring::_Tidy_deallocate(v86);
                          v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v39);
                          Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                          std::wstring::_Tidy_deallocate(v85);
                          std::wstring::_Tidy_deallocate(v84);
                          return (unsigned int)v37;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x47,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                          (const char *)0x800705B4LL,
                          v66);
                        JsonInternal::PodVectorBase::Deallocate(lpMem);
                        v35 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                        v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                        Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                          (__int64)v35,
                          (__int64)&pguid,
                          &v70);
                        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                        std::wstring::_Tidy_deallocate(v86);
                        v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v36);
                        Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                        std::wstring::_Tidy_deallocate(v85);
                        std::wstring::_Tidy_deallocate(v84);
                        return 2147943860LL;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x43,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                        (const char *)(unsigned int)v29,
                        v66);
                      JsonInternal::PodVectorBase::Deallocate(lpMem);
                      v31 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                      v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                      Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                        (__int64)v31,
                        (__int64)&pguid,
                        &v70);
                      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                      std::wstring::_Tidy_deallocate(v86);
                      v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v32);
                      Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                      std::wstring::_Tidy_deallocate(v85);
                      std::wstring::_Tidy_deallocate(v84);
                      return v30;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x40,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                      (const char *)(unsigned int)v24,
                      v66);
                    JsonInternal::PodVectorBase::Deallocate(lpMem);
                    v27 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                    v70 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                    Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                      (__int64)v27,
                      (__int64)&pguid,
                      &v70);
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                    std::wstring::_Tidy_deallocate(v86);
                    v70 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v77, v28);
                    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v70);
                    std::wstring::_Tidy_deallocate(v85);
                    std::wstring::_Tidy_deallocate(v84);
                    return v26;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2E,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                    (const char *)0x800700B7LL,
                    v65);
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
                  std::wstring::_Tidy_deallocate(v86);
                  v81 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, &v70, v21);
                  Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v81);
                  std::wstring::_Tidy_deallocate(v85);
                  std::wstring::_Tidy_deallocate(v84);
                  return 2147942583LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x29,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                  (const char *)(unsigned int)v14,
                  v65);
                std::wstring::_Tidy_deallocate(v86);
                v81 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, &v70, v16);
                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)&v81);
                std::wstring::_Tidy_deallocate(v85);
                std::wstring::_Tidy_deallocate(v84);
                return v15;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x20,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                (const char *)(unsigned int)Directory,
                v65);
              std::wstring::_Tidy_deallocate(v85);
              std::wstring::_Tidy_deallocate(v84);
              return v13;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
              (const char *)(unsigned int)appended,
              v65);
            std::wstring::_Tidy_deallocate(v85);
            std::wstring::_Tidy_deallocate(v84);
            return v11;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
            (const char *)(unsigned int)v5,
            v65);
          return v6;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
          (const char *)0x80070032LL,
          v65);
        return 2147942450LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
        (const char *)0x80070015LL,
        v65);
      return 2147942421LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
      (const char *)0x80070057LL,
      v65);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18029a310  mov     [rsp+arg_8], rbx
0x18029a315  mov     [rsp+arg_10], rsi
0x18029a31a  push    rdi
0x18029a31b  push    r12
0x18029a31d  push    r13
0x18029a31f  push    r14
0x18029a321  push    r15
0x18029a323  sub     rsp, 180h
0x18029a32a  mov     rax, cs:__security_cookie
0x18029a331  xor     rax, rsp
0x18029a334  mov     [rsp+1A8h+var_38], rax
0x18029a33c  mov     r14, rdx
0x18029a33f  mov     r15, rcx
0x18029a342  xor     r12d, r12d
0x18029a345  test    rdx, rdx
0x18029a348  jnz     short loc_18029A371
0x18029a34a  mov     rcx, [rsp+1A8h]; this
0x18029a352  mov     ebx, 80070057h
0x18029a357  mov     r9d, ebx; char *
0x18029a35a  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a361  lea     edx, [r14+12h]; void *
0x18029a365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a36a  mov     eax, ebx
0x18029a36c  jmp     loc_18029B0B8
0x18029a371  mov     rcx, r12
0x18029a374  xor     eax, eax
0x18029a376  lock cmpxchg qword ptr cs:xmmword_180463230+8, rcx
0x18029a37f  jnz     short loc_18029A3A9
0x18029a381  mov     rcx, [rsp+1A8h]; this
0x18029a389  mov     ebx, 80070015h
0x18029a38e  mov     r9d, ebx; char *
0x18029a391  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a398  mov     edx, 13h; void *
0x18029a39d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a3a2  mov     eax, ebx
0x18029a3a4  jmp     loc_18029B0B8
0x18029a3a9  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18029a3b0  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x18029a3b5  cmp     [rax+0C0h], r12b
0x18029a3bc  jnz     short loc_18029A3E6
0x18029a3be  mov     rcx, [rsp+1A8h]; this
0x18029a3c6  mov     ebx, 80070032h
0x18029a3cb  mov     r9d, ebx; char *
0x18029a3ce  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a3d5  mov     edx, 16h; void *
0x18029a3da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a3df  mov     eax, ebx
0x18029a3e1  jmp     loc_18029B0B8
0x18029a3e6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18029a3ed  movdqu  xmmword ptr [rsp+1A8h+pguid.Data1], xmm0
0x18029a3f6  lea     rcx, [rsp+1A8h+pguid]; pguid
0x18029a3fe  call    cs:__imp_CoCreateGuid
0x18029a404  mov     ebx, eax
0x18029a406  test    eax, eax
0x18029a408  jns     short loc_18029A42D
0x18029a40a  mov     rcx, [rsp+1A8h]; this
0x18029a412  mov     r9d, eax; char *
0x18029a415  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a41c  mov     edx, 1Ah; void *
0x18029a421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a426  mov     eax, ebx
0x18029a428  jmp     loc_18029B0B8
0x18029a42d  lea     rcx, [rsp+1A8h+var_B8]; lpSrc
0x18029a435  call    ?GetUtcTemporaryPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(void)
0x18029a43a  nop
0x18029a43b  xor     r8d, r8d
0x18029a43e  lea     rdx, [rsp+1A8h+pguid]
0x18029a446  lea     rcx, [rsp+1A8h+var_58]
0x18029a44e  call    ?StringFromGuidW@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::StringFromGuidW(_GUID const &,bool)
0x18029a453  nop
0x18029a454  mov     r8, rax
0x18029a457  lea     rdx, aHostminitrace; "hostminitrace_"
0x18029a45e  lea     rcx, [rsp+1A8h+var_98]
0x18029a466  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x18029a46b  nop
0x18029a46c  lea     rcx, [rsp+1A8h+var_58]
0x18029a474  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a479  lea     rdx, [rsp+1A8h+var_168]
0x18029a47e  lea     rcx, [rsp+1A8h+var_98]
0x18029a486  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a48b  movups  xmm0, xmmword ptr [rax]
0x18029a48e  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a494  lea     rdx, [rsp+1A8h+var_148]
0x18029a499  lea     rcx, [rsp+1A8h+var_B8]
0x18029a4a1  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18029a4a6  mov     ebx, eax
0x18029a4a8  test    eax, eax
0x18029a4aa  jns     short loc_18029A4EB
0x18029a4ac  mov     rcx, [rsp+1A8h]; this
0x18029a4b4  mov     r9d, eax; char *
0x18029a4b7  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a4be  mov     edx, 1Fh; void *
0x18029a4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a4c8  nop
0x18029a4c9  lea     rcx, [rsp+1A8h+var_98]
0x18029a4d1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a4d6  nop
0x18029a4d7  lea     rcx, [rsp+1A8h+var_B8]
0x18029a4df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a4e4  mov     eax, ebx
0x18029a4e6  jmp     loc_18029B0B8
0x18029a4eb  movups  xmm0, xmmword ptr cs:off_180385550; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x18029a4f2  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a4f8  lea     rdx, [rsp+1A8h+var_168]
0x18029a4fd  lea     rcx, [rsp+1A8h+var_B8]
0x18029a505  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a50a  movups  xmm0, xmmword ptr [rax]
0x18029a50d  movdqu  [rsp+1A8h+var_D8], xmm0
0x18029a516  lea     r8, [rsp+1A8h+var_148]
0x18029a51b  xor     edx, edx
0x18029a51d  lea     rcx, [rsp+1A8h+var_D8]
0x18029a525  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x18029a52a  mov     ebx, eax
0x18029a52c  test    eax, eax
0x18029a52e  jns     short loc_18029A56F
0x18029a530  mov     rcx, [rsp+1A8h]; this
0x18029a538  mov     r9d, eax; char *
0x18029a53b  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a542  mov     edx, 20h ; ' '; void *
0x18029a547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a54c  nop
0x18029a54d  lea     rcx, [rsp+1A8h+var_98]
0x18029a555  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a55a  nop
0x18029a55b  lea     rcx, [rsp+1A8h+var_B8]
0x18029a563  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a568  mov     eax, ebx
0x18029a56a  jmp     loc_18029B0B8
0x18029a56f  lea     rax, [rsp+1A8h+var_B8]
0x18029a577  mov     qword ptr [rsp+1A8h+var_E8], rax
0x18029a57f  mov     r13d, 1
0x18029a585  mov     byte ptr [rsp+1A8h+var_E8+8], r13b
0x18029a58d  lea     rdx, [rsp+1A8h+var_B8]
0x18029a595  lea     rcx, [rsp+1A8h+var_78]
0x18029a59d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18029a5a2  nop
0x18029a5a3  movaps  xmm0, xmmword ptr cs:off_18036CE20; "minitrace.etl"
0x18029a5aa  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a5b0  lea     rdx, [rsp+1A8h+var_148]
0x18029a5b5  lea     rcx, [rsp+1A8h+var_78]
0x18029a5bd  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18029a5c2  mov     ebx, eax
0x18029a5c4  test    eax, eax
0x18029a5c6  jns     short loc_18029A640
0x18029a5c8  mov     rcx, [rsp+1A8h]; this
0x18029a5d0  mov     r9d, eax; char *
0x18029a5d3  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a5da  lea     edx, [r13+28h]; void *
0x18029a5de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a5e3  nop
0x18029a5e4  lea     rcx, [rsp+1A8h+var_78]
0x18029a5ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a5f1  nop
0x18029a5f2  lea     rdx, [rsp+1A8h+var_168]
0x18029a5f7  lea     rcx, [rsp+1A8h+var_B8]
0x18029a5ff  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a604  movups  xmm0, xmmword ptr [rax]
0x18029a607  movdqu  [rsp+1A8h+var_E8], xmm0
0x18029a610  lea     rcx, [rsp+1A8h+var_E8]
0x18029a618  call    ?RecursivelyDeleteDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(std::wstring_view)
0x18029a61d  nop
0x18029a61e  lea     rcx, [rsp+1A8h+var_98]
0x18029a626  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a62b  nop
0x18029a62c  lea     rcx, [rsp+1A8h+var_B8]
0x18029a634  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a639  mov     eax, ebx
0x18029a63b  jmp     loc_18029B0B8
0x18029a640  mov     ecx, 58h ; 'X'; Size
0x18029a645  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18029a64a  mov     rdi, rax
0x18029a64d  mov     qword ptr [rsp+1A8h+var_128], rax
0x18029a655  mov     [rax+8], r13d
0x18029a659  mov     [rax+0Ch], r13d
0x18029a65d  lea     rax, ??_7?$_Ref_count_obj2@UEscalationDataRequest@Diagnostics@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Diagnostics::EscalationDataRequest>::`vftable'
0x18029a664  mov     [rdi], rax
0x18029a667  lea     rsi, [rdi+10h]
0x18029a66b  lea     rdx, [rsp+1A8h+var_168]
0x18029a670  lea     rcx, [rsp+1A8h+var_78]
0x18029a678  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a67d  movups  xmm0, xmmword ptr [rax]
0x18029a680  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a686  lea     rdx, [rsp+1A8h+var_148]
0x18029a68b  mov     rcx, rsi
0x18029a68e  call    ??0EscalationDataRequest@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::EscalationDataRequest::EscalationDataRequest(std::wstring_view)
0x18029a693  nop
0x18029a694  mov     qword ptr [rsp+1A8h+var_D8], rsi
0x18029a69c  mov     qword ptr [rsp+1A8h+var_D8+8], rdi
0x18029a6a4  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18029a6ab  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x18029a6b0  mov     r10, rax
0x18029a6b3  lea     rdx, [rsp+1A8h+var_D8]; void *
0x18029a6bb  lea     rcx, [rsp+1A8h+var_148]; void *
0x18029a6c0  call    ??0?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> const &)
0x18029a6c5  movups  xmm0, xmmword ptr cs:?k_hostAgentTransportId@Agent@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::Agent::k_hostAgentTransportId
0x18029a6cc  movdqu  xmmword ptr [rsp+1A8h+var_128], xmm0
0x18029a6d5  mov     r9, rax
0x18029a6d8  lea     r8, [rsp+1A8h+var_128]
0x18029a6e0  lea     rdx, [rsp+1A8h+pguid]
0x18029a6e8  mov     rcx, r10
0x18029a6eb  call    ?RegisterEscalationDataRequest@IAgentIoReceiver@Diagnostics@Microsoft@@QEAA_NAEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@UEscalationDataRequest@Diagnostics@Microsoft@@@6@@Z; Microsoft::Diagnostics::IAgentIoReceiver::RegisterEscalationDataRequest(_GUID const &,std::wstring_view,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>)
0x18029a6f0  test    al, al
0x18029a6f2  jnz     loc_18029A77F
0x18029a6f8  mov     rcx, [rsp+1A8h]; this
0x18029a700  mov     ebx, 800700B7h
0x18029a705  mov     r9d, ebx; char *
0x18029a708  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a70f  mov     edx, 2Eh ; '.'; void *
0x18029a714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a719  nop
0x18029a71a  mov     rcx, rdi; this
0x18029a71d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18029a722  nop
0x18029a723  lea     rcx, [rsp+1A8h+var_78]
0x18029a72b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a730  nop
0x18029a731  lea     rdx, [rsp+1A8h+var_168]
0x18029a736  lea     rcx, [rsp+1A8h+var_B8]
0x18029a73e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029a743  movups  xmm0, xmmword ptr [rax]
0x18029a746  movdqu  [rsp+1A8h+var_E8], xmm0
0x18029a74f  lea     rcx, [rsp+1A8h+var_E8]
0x18029a757  call    ?RecursivelyDeleteDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(std::wstring_view)
0x18029a75c  nop
0x18029a75d  lea     rcx, [rsp+1A8h+var_98]
0x18029a765  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a76a  nop
0x18029a76b  lea     rcx, [rsp+1A8h+var_B8]
0x18029a773  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029a778  mov     eax, ebx
0x18029a77a  jmp     loc_18029B0B8
0x18029a77f  lea     rax, [rsp+1A8h+pguid]
0x18029a787  mov     qword ptr [rsp+1A8h+var_168], rax
0x18029a78c  mov     byte ptr [rsp+1A8h+var_168+8], r13b
0x18029a791  mov     [rsp+1A8h+lpMem], r12
0x18029a799  mov     [rsp+1A8h+var_100], r12
0x18029a7a1  mov     [rsp+1A8h+var_F8], r13b
0x18029a7a9  mov     [rsp+1A8h+var_158], 2
0x18029a7ae  mov     rax, cs:off_180385510; "tslty"
0x18029a7b5  mov     [rsp+1A8h+var_148], rax
0x18029a7ba  mov     [rsp+1A8h+var_148+8], 5
0x18029a7c3  lea     rax, [rsp+1A8h+lpMem]
0x18029a7cb  mov     qword ptr [rsp+1A8h+var_128], rax
0x18029a7d3  mov     [rsp+1A8h+var_128+8], r12d
0x18029a7db  mov     eax, dword ptr [rsp+1A8h+var_168+0Ch]
0x18029a7df  mov     [rsp+1A8h+var_128+0Ch], eax
0x18029a7e6  lea     rax, [rsp+1A8h+var_158]
0x18029a7eb  mov     [rsp+1A8h+Src], rax; Src
0x18029a7f0  mov     dword ptr [rsp+1A8h+Size], r13d; Size
0x18029a7f5  mov     [rsp+1A8h+var_180], 0F6h; int
0x18029a7fd  lea     rax, [rsp+1A8h+var_148]
0x18029a802  mov     [rsp+1A8h+var_188], rax; __int64
0x18029a807  lea     r9, [rsp+1A8h+var_128]; int
0x18029a80f  xor     r8d, r8d; int
0x18029a812  lea     rdx, [rsp+1A8h+var_118]; int
0x18029a81a  lea     rcx, [rsp+1A8h+lpMem]; int
0x18029a822  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x18029a827  mov     rax, cs:off_180385520; "trid"
0x18029a82e  mov     [rsp+1A8h+var_148], rax
0x18029a833  mov     [rsp+1A8h+var_148+8], 4
0x18029a83c  lea     rax, [rsp+1A8h+lpMem]
0x18029a844  mov     qword ptr [rsp+1A8h+var_128], rax
0x18029a84c  mov     [rsp+1A8h+var_128+8], r12d
0x18029a854  mov     eax, [rsp+1A8h+var_10C]
0x18029a85b  mov     [rsp+1A8h+var_128+0Ch], eax
0x18029a862  lea     rax, [rsp+1A8h+pguid]
0x18029a86a  mov     [rsp+1A8h+Src], rax; Src
0x18029a86f  mov     dword ptr [rsp+1A8h+Size], 10h; Size
0x18029a877  mov     [rsp+1A8h+var_180], 0FBh; int
0x18029a87f  lea     rax, [rsp+1A8h+var_148]
0x18029a884  mov     [rsp+1A8h+var_188], rax; int
0x18029a889  lea     r9, [rsp+1A8h+var_128]; int
0x18029a891  xor     r8d, r8d; int
0x18029a894  lea     rdx, [rsp+1A8h+var_118]; int
0x18029a89c  lea     rcx, [rsp+1A8h+lpMem]; int
0x18029a8a4  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x18029a8a9  lea     r13, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x18029a8b0  mov     rcx, r13; this
0x18029a8b3  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x18029a8b8  mov     rbx, rax
0x18029a8bb  mov     r8d, dword ptr [rsp+1A8h+var_100]
0x18029a8c3  shl     r8, 2
0x18029a8c7  mov     rdx, [rsp+1A8h+lpMem]
0x18029a8cf  lea     rcx, [rsp+1A8h+var_148]
0x18029a8d4  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x18029a8d9  movups  xmm0, xmmword ptr [rsp+1A8h+var_148]
0x18029a8de  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x18029a8e4  lea     r8, [rsp+1A8h+var_148]
0x18029a8e9  mov     dl, 0Dh
0x18029a8eb  mov     rcx, rbx
0x18029a8ee  call    ?SendAgentMessage@Agent@Diagnostics@Microsoft@@QEAAJVAgentMessageType@23@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; Microsoft::Diagnostics::Agent::SendAgentMessage(Microsoft::Diagnostics::AgentMessageType,gsl::span<gsl::byte const,-1>)
0x18029a8f3  mov     ebx, eax
0x18029a8f5  test    eax, eax
0x18029a8f7  jns     loc_18029A9B5
0x18029a8fd  mov     rcx, [rsp+1A8h]; this
0x18029a905  mov     r9d, eax; char *
0x18029a908  lea     r8, aOnecoreBaseTel_187; "onecore\\base\\telemetry\\utc\\service"...
0x18029a90f  mov     edx, 40h ; '@'; void *
0x18029a914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029a919  nop
  ... truncated ...
```
