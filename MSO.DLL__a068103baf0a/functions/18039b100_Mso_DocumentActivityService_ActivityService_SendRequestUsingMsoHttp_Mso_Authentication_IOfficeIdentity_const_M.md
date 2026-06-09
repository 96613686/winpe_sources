# Mso::DocumentActivityService::ActivityService::SendRequestUsingMsoHttp(Mso::Authentication::IOfficeIdentity const *,Mso::DocumentActivities::Base::DocumentInfo const &,Mso::Collections::Either<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Mso::OfficeWebServiceApi::ConfigURL::URL> const &,wchar_t const *,wchar_t const *,std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,Mso::LogOperation::CLogOperationT<2> &,Mso::Functor<void (wchar_t const *,bool,uchar const *,unsigned __int64,bool,Mso::Http::IRequest &,Mso::Http::Result const &,std::optional<int> const &,Mso::Collections::Either<_GUID,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &,std::optional<bool> const &)> &&)

- ea: `0x18039b100`
- end: `0x18039c6e6`
- name: `?SendRequestUsingMsoHttp@ActivityService@DocumentActivityService@Mso@@CAJPEBUIOfficeIdentity@Authentication@3@AEBUDocumentInfo@Base@DocumentActivities@3@AEBV?$Either@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4URL@ConfigURL@OfficeWebServiceApi@Mso@@@Collections@3@PEB_W3AEBV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_NAEAV?$CLogOperationT@$01@LogOperation@3@$$QEAV?$Functor@$$A6AXPEB_W_NPEBE_K1AEAVIRequest@Http@Mso@@AEBUResult@23@AEBV?$optional@H@std@@AEBV?$Either@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Collections@3@AEBV?$optional@_N@6@@Z@3@@Z`
- size: `5606`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, char, Mso::LogOperation::CLogOperationBase *, __int64)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1803a4f48`

## callees

- `0x180031b90`
- `0x1800326a8`
- `0x180032d80`
- `0x180040d80`
- `0x180040e00`
- `0x18005273c`
- `0x18008a404`
- `0x1800c6d38`
- `0x1800e8d70`
- `0x1800e8e00`
- `0x1800f7aa8`
- `0x180143a60`
- `0x180188540`
- `0x1801b547c`
- `0x1801c9744`
- `0x180239aa0`
- `0x180239ab0`
- `0x18023c2e0`
- `0x18023e770`
- `0x18023e8d0`
- `0x1802f0300`
- `0x18039b100`
- `0x1803a76a4`
- `0x18041b058`
- `0x18041d804`
- `0x180612a50`
- `0x180988b50`
- `0x180a934e8`
- `0x180b46924`
- `0x180c17948`

## import_xrefs

- `Mso30Win32Client!__imp_?GetCanary@CanaryCache@Mso@@YA_NPEB_WPEA_WK@Z` at `0x18039b4af`
- `Mso30Win32Client!__imp_?GetCanary@CanaryCache@Mso@@YA_NPEB_WPEA_WK@Z` at `0x18039b4af`
- `Mso30Win32Client!__imp_?GetServiceUrlForIdentity@OfficeWebServiceApi@Mso@@YA?AW4Flags@Status@12@VMsoReserveTag@@W4URL@ConfigURL@12@PEA_WIPEBUIOfficeIdentity@Authentication@2@@Z` at `0x18039c278`
- `Mso30Win32Client!__imp_?GetServiceUrlForIdentity@OfficeWebServiceApi@Mso@@YA?AW4Flags@Status@12@VMsoReserveTag@@W4URL@ConfigURL@12@PEA_WIPEBUIOfficeIdentity@Authentication@2@@Z` at `0x18039c278`
- `Mso30Win32Client!__imp_?UsePreferAuthHeaderSetting@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x18039bd98`
- `Mso30Win32Client!__imp_?UsePreferAuthHeaderSetting@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x18039c08a`
- `Mso30Win32Client!__imp_?UsePreferAuthHeaderSetting@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x18039bd98`
- `Mso30Win32Client!__imp_?UsePreferAuthHeaderSetting@IdentityFlights@Authentication@Mso@@YA_NXZ` at `0x18039c08a`
- `Mso30Win32Client!__imp_?TheInstance@IOfficeCredStore@@SAPEAV1@XZ` at `0x18039c032`
- `Mso30Win32Client!__imp_?TheInstance@IOfficeCredStore@@SAPEAV1@XZ` at `0x18039c032`
- `Mso30Win32Client!__imp_?ConfigServiceReady@OfficeWebServiceApi@Mso@@YA_NPEBUIOfficeIdentity@Authentication@2@@Z` at `0x18039c28e`
- `Mso30Win32Client!__imp_?ConfigServiceReady@OfficeWebServiceApi@Mso@@YA_NPEBUIOfficeIdentity@Authentication@2@@Z` at `0x18039c28e`
- `Mso20Win32Client!__imp_?MsoWzGetUserAgent@@YAPEB_WPEA_W_K@Z` at `0x18039b26f`
- `Mso20Win32Client!__imp_?MsoWzGetUserAgent@@YAPEB_WPEA_W_K@Z` at `0x18039b26f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b338`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b419`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b49b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b5c2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b5de`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b6dc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b74e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b858`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b962`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039bd72`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039be1f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039c6df`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b338`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b419`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b49b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b5c2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b5de`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b6dc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b74e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b858`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039b962`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039bd72`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039be1f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18039c6df`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18039c4a9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18039c4a9`
- `Mso20Win32Client!__imp_?MsoCreateAsyncHttpRequestTag@Http@Mso@@YA?AUResult@12@PEAPEAVIRequest@12@I@Z` at `0x18039b218`
- `Mso20Win32Client!__imp_?MsoCreateAsyncHttpRequestTag@Http@Mso@@YA?AUResult@12@PEAPEAVIRequest@12@I@Z` at `0x18039b218`
- `Mso20Win32Client!__imp_?MsoCreateHttpRequestSettings@Http@Mso@@YA?AUResult@12@PEAPEAVIRequestSettings@12@@Z` at `0x18039b2dd`
- `Mso20Win32Client!__imp_?MsoCreateHttpRequestSettings@Http@Mso@@YA?AUResult@12@PEAPEAVIRequestSettings@12@@Z` at `0x18039b2dd`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AU_GUID@@XZ` at `0x18039b4d8`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AU_GUID@@XZ` at `0x18039b4d8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18039b63a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18039b63a`
- `Mso20Win32Client!__imp_?MsoCreateHttpRequestContext@Http@Mso@@YA?AUResult@12@PEB_WPEAPEAVIRequestContext@12@@Z` at `0x18039b238`
- `Mso20Win32Client!__imp_?MsoCreateHttpRequestContext@Http@Mso@@YA?AUResult@12@PEB_WPEAPEAVIRequestContext@12@@Z` at `0x18039b238`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b3d5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b484`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b7ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b8f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039ba10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bb8f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bbce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039be70`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bea0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bed9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b3d5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b484`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b7ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039b8f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039ba10`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bb8f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bbce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039be70`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bea0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18039bed9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039b3f4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039b47d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039bca9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039c217`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039b3f4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039b47d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039bca9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18039c217`

## string_xrefs

- `0x18039c29d`: `ConfigServiceReady`
- `0x18039b190`: `HasPathOverride`
- `0x18039b557`: `GetTokenForAuthHeader`
- `0x18039b537`: `TokenLength`
- `0x18039b51d`: `HasAuthToken`
- `0x18039bcf8`: `ssl.live.com`
- `0x18039b907`: `application/json`
- `0x18039b96c`: `application/json`
- `0x18039c2bb`: `GetServiceUrlForIdentityFlags`

## pseudocode

```c

```
