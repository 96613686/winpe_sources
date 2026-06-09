# CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers(CMsoDrmIdentities const &,bool)

- ea: `0x1807349b0`
- end: `0x18073623e`
- name: `?BootStrapLoggedInUsers@CMsoDrmRightsTemplatesManager@@EEAAXAEBVCMsoDrmIdentities@@_N@Z`
- size: `6286`
- prototype: `void __fastcall(CMsoDrmRightsTemplatesManager *__hidden this, const struct CMsoDrmIdentities *, bool)`
- caller_count: `2`
- callee_count: `59`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180734510`
- `0x181177f40`

## callees

- `0x180015d60`
- `0x1800164e0`
- `0x180029700`
- `0x18002ae88`
- `0x18002b13c`
- `0x18002c110`
- `0x18005f504`
- `0x18006b674`
- `0x1800778dc`
- `0x180081400`
- `0x1800b65ac`
- `0x1801290e8`
- `0x18012bacc`
- `0x1801c356c`
- `0x1802a96b0`
- `0x1802be724`
- `0x1802e76b8`
- `0x18035ff38`
- `0x180371700`
- `0x1803924b4`
- `0x180414a64`
- `0x180484870`
- `0x180485240`
- `0x180485dd0`
- `0x18054cc9c`
- `0x18055a6ac`
- `0x18055b5e0`
- `0x18055b670`
- `0x180646518`
- `0x1806468fc`
- `0x180648c74`
- `0x180698278`
- `0x1806bb06c`
- `0x1806bbde4`
- `0x1806bc664`
- `0x1806bc814`
- `0x180732c00`
- `0x180733e00`
- `0x1807349b0`
- `0x1807ee2d8`
- `0x180809534`
- `0x180920d30`
- `0x18095d904`
- `0x1809ec754`
- `0x1809ec9d4`
- `0x1809eca68`
- `0x1809ef020`
- `0x180abb290`
- `0x180ac63cc`
- `0x180ad2c10`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180735bf1`
- `KERNEL32!SetEvent` at `0x180735bf1`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x180735b36`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x180736059`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x1807360d0`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x18073613d`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x180735b36`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x180736059`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x1807360d0`
- `Mso30Win32Client!__imp_?RefactorLoadTemplatesAsync@CG@Config@Clp@Mso@@YAAEBVChangeGate@Optimized@AB@4@XZ` at `0x18073613d`
- `Mso30Win32Client!__imp_?IsAdRmsUsageTelemetryEnabled@FG@Config@Clp@Mso@@YAAEBVFeatureGate@Optimized@AB@4@XZ` at `0x180735a7a`
- `Mso30Win32Client!__imp_?IsAdRmsUsageTelemetryEnabled@FG@Config@Clp@Mso@@YAAEBVFeatureGate@Optimized@AB@4@XZ` at `0x180735d33`
- `Mso30Win32Client!__imp_?IsAdRmsUsageTelemetryEnabled@FG@Config@Clp@Mso@@YAAEBVFeatureGate@Optimized@AB@4@XZ` at `0x1807361af`
- `Mso30Win32Client!__imp_?IsAdRmsUsageTelemetryEnabled@FG@Config@Clp@Mso@@YAAEBVFeatureGate@Optimized@AB@4@XZ` at `0x180735a7a`
- `Mso30Win32Client!__imp_?IsAdRmsUsageTelemetryEnabled@FG@Config@Clp@Mso@@YAAEBVFeatureGate@Optimized@AB@4@XZ` at `0x180735d33`
- `Mso30Win32Client!__imp_?IsAdRmsUsageTelemetryEnabled@FG@Config@Clp@Mso@@YAAEBVFeatureGate@Optimized@AB@4@XZ` at `0x1807361af`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1807356ce`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180735ab1`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1807356ce`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180735ab1`
- `Mso20Win32Client!__imp_?MsoFOfficeShuttingDown@@YAHXZ` at `0x180734a10`
- `Mso20Win32Client!__imp_?MsoFOfficeShuttingDown@@YAHXZ` at `0x180734a10`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807350af`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180735c2e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807350af`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180735c2e`
- `Mso20Win32Client!__imp_?IsMainThread@Threadpool@Mso@@YA_NXZ` at `0x18073600d`
- `Mso20Win32Client!__imp_?IsMainThread@Threadpool@Mso@@YA_NXZ` at `0x18073600d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735472`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735497`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1807354d1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18073550b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735545`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18073557f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735608`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735472`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735497`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1807354d1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18073550b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735545`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18073557f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180735608`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x180734b6e`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1807350f8`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x180735c77`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x180734b6e`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1807350f8`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x180735c77`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735db9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735df9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735e22`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735e8a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735f42`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735db9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735df9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735e22`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735e8a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180735f42`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@$$QEAVEventExportability@12@@Z` at `0x180735464`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@$$QEAVEventExportability@12@@Z` at `0x180735464`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1807350ce`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x180735c4d`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1807350ce`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x180735c4d`
- `Mso20Win32Client!__imp_?ConcurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x18073610b`
- `Mso20Win32Client!__imp_?ConcurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x18073610b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180735d46`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180735d46`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x180735e5f`
- `Mso20Win32Client!__imp_MsoWaitForSingleObject` at `0x180735e5f`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z` at `0x1807355bb`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z` at `0x1807355bb`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180735e0b`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180735e43`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180735f55`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180735e0b`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180735e43`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180735f55`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734a54`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734bae`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734be0`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734e18`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734fa8`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735332`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735369`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1807353c6`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18073583e`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18073593e`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1807359d0`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735ba2`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735bd8`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734a54`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734bae`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734be0`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734e18`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180734fa8`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735332`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735369`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1807353c6`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18073583e`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18073593e`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1807359d0`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735ba2`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x180735bd8`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x180734a25`
- `Mso20Win32Client!__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z` at `0x180734a25`
- `MSVCP140!_Mtx_unlock` at `0x1807361fe`
- `MSVCP140!_Mtx_unlock` at `0x1807361fe`

## string_xrefs

- `0x1807359b9`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers we always call in silent mode and use token type as IPCP_TOKEN_TYPE_WINDOWS for non-domain joined mostly automation scenarios`
- `0x180735a4c`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers IpcpBootstrapUser no logged on user failed with error : 0x%x`
- `0x1807361e4`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers returning with error : 0x%x`
- `0x180735b8b`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers setting m_fUIPromptRequired to true`
- `0x180735bc1`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers user cancelled the action`
- `0x180735dc9`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers setting default server for QAT to %s `
- `0x180735927`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers Make an extra IpcpBootstrap call in non-logged in case with silent flag.`
- `0x1807355a2`: `UsesActiveDirectory`
- `0x1807357b2`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers failed.`
- `0x180735827`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers setting m_fUserOnlineRequired to true`
- `0x18073531d`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers if user isn't AD then we should have either token or user email address. we skip this user`
- `0x180735352`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers this is active directorry identity. Setting irmtoken type as windows`
- `0x1807353af`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers This is an ADAL identity`
- `0x180735059`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers ctx flag is %d`
- `0x18073523f`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers the stored userid for uniquied is %s is %s`
- `0x1807352de`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers No stored userid found, this is an ADAL identity, using emailID %s and uniquied is %s`
- `0x180734b97`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers online allowed`
- `0x180734bc9`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers prompt allowed`
- `0x180734e01`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers. we are in online mode before getting token`
- `0x180734f91`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers token is not empty`
- `0x180734a3f`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers Entering`
- `0x180734ae5`: `DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers num of users is %d`

## pseudocode

```c
void __fastcall CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers(
        CMsoDrmRightsTemplatesManager *this,
        const struct CMsoDrmIdentities *a2,
        char a3)
{
  bool v5; // di
  struct _Mtx_internal_imp_t *v6; // r14
  Mso::Drm *v7; // rcx
  struct IDrmConfig *DrmConfig; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r9d
  Mso::Threadpool *v12; // rcx
  __int64 v13; // rax
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  struct Mso::Telemetry::Activity **v18; // rsi
  struct Mso::Telemetry::Activity *v19; // rdi
  __m128i si128; // xmm6
  __int64 v21; // r12
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 BootStrappedIdentityList; // rax
  _QWORD *v25; // rbx
  __int64 v26; // rax
  wchar_t **v27; // rcx
  __int64 v28; // rax
  unsigned int *v29; // rax
  unsigned int v30; // edx
  const wchar_t *v31; // r8
  int *v32; // rbx
  int v33; // edx
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  __int128 *v37; // rax
  int v38; // r8d
  int v39; // r9d
  __int128 *v40; // r8
  __int64 v41; // r9
  int v42; // edx
  int v43; // r8d
  int v44; // r9d
  __m128i v45; // xmm1
  __m128i v46; // xmm1
  __int128 *v47; // rax
  int v48; // r8d
  int v49; // r9d
  __int128 *v50; // rax
  char MsipcRmsClientType; // al
  __int64 v52; // rax
  struct Mso::Telemetry::IDataFieldCollection *v53; // rax
  struct Mso::Telemetry::IDataFieldCollection *v54; // rbx
  __int64 v55; // r8
  struct Mso::Telemetry::IDataFieldCollection *v56; // rbx
  __int64 v57; // r8
  struct Mso::Telemetry::IDataFieldCollection *v58; // rbx
  __int64 v59; // r8
  struct Mso::Telemetry::IDataFieldCollection *v60; // rbx
  __int64 v61; // r8
  struct Mso::Telemetry::IDataFieldCollection *v62; // rbx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rax
  __int128 *v66; // rax
  struct Mso::Telemetry::IDataFieldCollection *v67; // rbx
  __int64 v68; // rax
  int v69; // r9d
  int v70; // r8d
  int v71; // ebx
  Mso::Clp::Config::FG *v72; // rcx
  __int64 v73; // rax
  int v74; // edx
  int v75; // r9d
  __m128i v76; // xmm1
  __m128i v77; // xmm1
  __int64 v78; // rax
  __int64 v79; // r8
  __int8 v80; // bl
  __int64 v81; // rcx
  __int64 (__fastcall ***MsipcProxy)(_QWORD, _QWORD, _QWORD, _QWORD, _BYTE *, _QWORD, __m128i *, __m128i *); // r10
  __int64 (__fastcall *v83)(_QWORD, _QWORD, _QWORD, _QWORD, _BYTE *, _QWORD, __m128i *, __m128i *); // rax
  int v84; // edx
  int v85; // r8d
  int v86; // r9d
  int v87; // r8d
  Mso::Clp::Config::FG *v88; // rcx
  const struct Mso::AB::Optimized::FeatureGate *v89; // rax
  __m128i v90; // xmm1
  __m128i v91; // xmm1
  char v92; // bl
  const struct Mso::AB::Optimized::ChangeGate *v93; // rax
  __int64 v94; // rax
  Mso::Async *v95; // rcx
  CMsoDrmRightsTemplatesManager *v96; // rax
  __int128 *v97; // r8
  __int64 v98; // r9
  _QWORD *v99; // rax
  Mso::AB::Optimized::FeatureGate *v100; // rax
  bool v101; // al
  __int64 v102; // rax
  int v103; // r9d
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rax
  const wchar_t *v107; // rdx
  __int64 v108; // rdx
  _QWORD *v109; // rax
  __int64 v110; // rdx
  __int64 v111; // xmm1_8
  __m128i v112; // xmm0
  __int64 v113; // xmm1_8
  __m128i v114; // xmm0
  Mso::Clp::Config::CG *v115; // rcx
  Mso::Clp::Config::CG *v116; // rcx
  const struct Mso::AB::Optimized::ChangeGate *v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rax
  Mso::Clp::Config::CG *v120; // rcx
  const struct Mso::AB::Optimized::ChangeGate *TemplatesAsync; // rax
  __int64 v122; // rax
  struct Mso::Async::IDispatchQueue *v123; // rax
  Mso::Clp::Config::FG *v124; // rcx
  const struct Mso::AB::Optimized::ChangeGate *v125; // rax
  const struct Mso::AB::Optimized::FeatureGate *v126; // rax
  int v127; // [rsp+20h] [rbp-628h]
  char v128; // [rsp+50h] [rbp-5F8h]
  char v129; // [rsp+51h] [rbp-5F7h] BYREF
  char v130; // [rsp+52h] [rbp-5F6h]
  char v131; // [rsp+53h] [rbp-5F5h]
  char v132; // [rsp+54h] [rbp-5F4h]
  int Templates; // [rsp+58h] [rbp-5F0h] BYREF
  __m128i v134; // [rsp+60h] [rbp-5E8h] BYREF
  __m128i v135; // [rsp+70h] [rbp-5D8h] BYREF
  char v136; // [rsp+80h] [rbp-5C8h]
  bool v137; // [rsp+88h] [rbp-5C0h]
  __int64 v138; // [rsp+90h] [rbp-5B8h] BYREF
  struct Mso::Telemetry::Activity *v139; // [rsp+98h] [rbp-5B0h] BYREF
  _QWORD v140[2]; // [rsp+A0h] [rbp-5A8h] BYREF
  __m128i v141; // [rsp+B0h] [rbp-598h] BYREF
  __m128i v142; // [rsp+C0h] [rbp-588h] BYREF
  int v143; // [rsp+D0h] [rbp-578h] BYREF
  __int64 v144; // [rsp+D8h] [rbp-570h]
  int v145; // [rsp+E0h] [rbp-568h] BYREF
  int *v146; // [rsp+E8h] [rbp-560h]
  CMsoDrmRightsTemplatesManager *v147; // [rsp+F0h] [rbp-558h]
  __m128i *v148; // [rsp+F8h] [rbp-550h]
  __int64 v149; // [rsp+100h] [rbp-548h]
  CMsoDrmRightsTemplatesManager *v150; // [rsp+108h] [rbp-540h]
  _BYTE v151[24]; // [rsp+110h] [rbp-538h] BYREF
  _BYTE *v152; // [rsp+128h] [rbp-520h]
  int v153; // [rsp+130h] [rbp-518h] BYREF
  char v154; // [rsp+134h] [rbp-514h]
  _BYTE *v155; // [rsp+138h] [rbp-510h]
  char ***v156; // [rsp+140h] [rbp-508h] BYREF
  const char *v157; // [rsp+148h] [rbp-500h]
  __int128 v158; // [rsp+150h] [rbp-4F8h] BYREF
  __int64 v159; // [rsp+160h] [rbp-4E8h]
  _OWORD v160[2]; // [rsp+168h] [rbp-4E0h] BYREF
  char v161; // [rsp+188h] [rbp-4C0h]
  __int64 v162; // [rsp+190h] [rbp-4B8h] BYREF
  char v163; // [rsp+198h] [rbp-4B0h]
  _QWORD v164[2]; // [rsp+1A0h] [rbp-4A8h] BYREF
  __int64 *v165; // [rsp+1B0h] [rbp-498h]
  _QWORD v166[2]; // [rsp+1B8h] [rbp-490h] BYREF
  char v167[8]; // [rsp+1C8h] [rbp-480h] BYREF
  char v168[8]; // [rsp+1D0h] [rbp-478h] BYREF
  CMsoDrmRightsTemplatesManager *v169; // [rsp+1D8h] [rbp-470h]
  char *v170; // [rsp+1E0h] [rbp-468h]
  struct Mso::Telemetry::Activity **v171; // [rsp+1E8h] [rbp-460h]
  __int64 v172; // [rsp+1F0h] [rbp-458h]
  __int64 v173; // [rsp+1F8h] [rbp-450h]
  __int64 v174; // [rsp+200h] [rbp-448h]
  int *v175; // [rsp+208h] [rbp-440h]
  _QWORD *v176; // [rsp+210h] [rbp-438h]
  __int128 v177; // [rsp+220h] [rbp-428h] BYREF
  __int64 v178; // [rsp+230h] [rbp-418h]
  _OWORD v179[2]; // [rsp+238h] [rbp-410h] BYREF
  char v180; // [rsp+258h] [rbp-3F0h]
  _BYTE v181[16]; // [rsp+260h] [rbp-3E8h] BYREF
  int v182; // [rsp+270h] [rbp-3D8h]
  __int64 v183; // [rsp+278h] [rbp-3D0h]
  _QWORD *v184; // [rsp+280h] [rbp-3C8h]
  __int128 *v185; // [rsp+288h] [rbp-3C0h]
  char v186[8]; // [rsp+290h] [rbp-3B8h] BYREF
  char v187[16]; // [rsp+298h] [rbp-3B0h] BYREF
  char v188[16]; // [rsp+2A8h] [rbp-3A0h] BYREF
  char v189[16]; // [rsp+2B8h] [rbp-390h] BYREF
  __int128 v190; // [rsp+2C8h] [rbp-380h] BYREF
  __m128i v191; // [rsp+2D8h] [rbp-370h]
  wchar_t *v192[2]; // [rsp+2E8h] [rbp-360h] BYREF
  __int64 v193; // [rsp+2F8h] [rbp-350h]
  unsigned __int64 v194; // [rsp+300h] [rbp-348h]
  __int128 v195; // [rsp+308h] [rbp-340h] BYREF
  __m128i v196; // [rsp+318h] [rbp-330h]
  __int128 v197; // [rsp+328h] [rbp-320h] BYREF
  __m128i v198; // [rsp+338h] [rbp-310h]
  __int128 v199; // [rsp+350h] [rbp-2F8h] BYREF
  _BYTE v200[24]; // [rsp+360h] [rbp-2E8h] BYREF
  __int64 v201; // [rsp+378h] [rbp-2D0h]
  __int64 v202; // [rsp+380h] [rbp-2C8h]
  __int16 v203; // [rsp+388h] [rbp-2C0h]
  _BYTE v204[96]; // [rsp+390h] [rbp-2B8h] BYREF
  wchar_t v205[264]; // [rsp+3F0h] [rbp-258h] BYREF

  v131 = a3;
  v150 = this;
  v169 = this;
  v147 = this;
  v136 = a3;
  v130 = 0;
  if ( MsoFOfficeShuttingDown() )
    return;
  v5 = MsoFRegValueExists((const struct _msoreg *)&vmsoridDrmDefaultServer);
  v137 = v5;
  v132 = 0;
  v128 = 0;
  Mso::Logging::MsoSendTraceTag(
    37507989,
    586,
    100,
    L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers Entering");
  std::map<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>>::map<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>>(v151);
  v176 = (_QWORD *)((char *)a2 + 8);
  v138 = *((_QWORD *)a2 + 1);
  v149 = 0;
  v6 = (CMsoDrmRightsTemplatesManager *)((char *)this + 56);
  v170 = (char *)this + 56;
  std::_Mutex_base::lock((CMsoDrmRightsTemplatesManager *)((char *)this + 56));
  DrmConfig = Mso::Drm::GetDrmConfig(v7);
  if ( !(*(unsigned __int8 (__fastcall **)(struct IDrmConfig *))(*(_QWORD *)DrmConfig + 8LL))(DrmConfig) )
  {
    Templates = -2147467259;
    goto LABEL_157;
  }
  Templates = 0;
  v175 = (int *)((char *)this + 28);
  *((_DWORD *)this + 7) = 0;
  Mso::Logging::MsoSendTraceTag<unsigned __int64>(
    37507990,
    v9,
    v10,
    v11,
    (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers num of users is %d",
    &v138);
  v12 = *(Mso::Threadpool **)(CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList() + 16);
  if ( *((_QWORD *)a2 + 1) > (unsigned __int64)v12 )
  {
    v129 = 0;
    v13 = Mso::Telemetry::EventFlags::EventFlags(v140, 2);
    v142.m128i_i64[0] = (__int64)&off_181D9C1C0;
    v142.m128i_i64[1] = (__int64)"MipProtectionSDKEnabled";
    Mso::Telemetry::SendTelemetryEvent<>(&v142, v13, &v129);
  }
  if ( v5 )
  {
    MsoFRegReadWz((const struct _msoreg *)&vmsoridDrmDefaultServer, v205, 0x104u);
    Mso::Logging::MsoSendTraceTag<wchar_t [260]>(v15, v14, v16, v17, v127, (__int64)v205);
  }
  v152 = (char *)this + 20;
  if ( !*((_BYTE *)this + 20) )
  {
    Mso::Logging::MsoSendTraceTag(
      37507992,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers online allowed");
    *((_BYTE *)this + 22) = 0;
  }
  v155 = (char *)this + 21;
  if ( !*((_BYTE *)this + 21) )
  {
    Mso::Logging::MsoSendTraceTag(
      37507993,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers prompt allowed");
    *((_BYTE *)this + 23) = 0;
  }
  *((_DWORD *)this + 4) = 1;
  v18 = *(struct Mso::Telemetry::Activity ***)a2;
  v19 = *v18;
  v171 = v18;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v139 = v19;
    if ( v19 == (struct Mso::Telemetry::Activity *)v18 )
      goto LABEL_78;
    v172 = *((_QWORD *)v19 + 2);
    v21 = v172;
    v134 = 0;
    v135 = 0;
    v205[0] = 0;
    v158 = 0;
    v159 = 0;
    v160[0] = 0;
    v161 = 0;
    v160[1] = (unsigned __int64)&v158;
    v141.m128i_i32[0] = 0;
    v141.m128i_i64[1] = 0;
    v148 = 0;
    v173 = 0;
    v143 = 0;
    v144 = 0;
    v145 = 0;
    v146 = 0;
    v195 = 0;
    v196 = si128;
    LOWORD(v195) = 0;
    CIPC_PROMPT_CTX::CIPC_PROMPT_CTX((CIPC_PROMPT_CTX *)v181);
    v162 = 0;
    v163 = 0;
    v164[0] = 24;
    v164[1] = GetTokenCallbackQuiet;
    v165 = 0;
    v166[0] = 3;
    v166[1] = v164;
    v190 = 0;
    v191 = si128;
    LOWORD(v190) = 0;
    *(_OWORD *)v192 = 0;
    v193 = 0;
    v194 = 7;
    LOWORD(v192[0]) = 0;
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 112LL))(v21);
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v22 + 2 * v23) );
    std::wstring::assign(&v190);
    v174 = ++v149;
    BootStrappedIdentityList = CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList();
    v25 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                      BootStrappedIdentityList,
                      v186,
                      &v190);
    if ( *v25 != *(_QWORD *)(CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList() + 8) )
      goto LABEL_132;
    if ( *v152 )
      goto LABEL_31;
    Mso::Logging::MsoSendTraceTag(
      37507994,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers. we are in online mode before getting token");
    *((_BYTE *)v147 + 22) = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v21 + 72LL))(v21) )
    {
      v26 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 8LL))(v21, &v197);
      std::wstring::operator=(v192, v26);
      std::basic_string<char16_t>::~basic_string<char16_t>(&v197);
    }
    if ( !v193 )
    {
LABEL_31:
      v32 = v146;
    }
    else
    {
      v27 = v192;
      if ( v194 <= 7 || (v27 = (wchar_t **)v192[0]) != 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( *((_WORD *)v27 + v28) );
      }
      else
      {
        LODWORD(v28) = 0;
      }
      if ( (int)v28 < 0 )
        __fastfail(5u);
      LODWORD(v139) = v28;
      v29 = (unsigned int *)SafeInt<unsigned long,safeint_exception_handlers::SafeInt_InvalidParameter>::operator+<int>(
                              &v139,
                              v168,
                              1);
      v31 = (const wchar_t *)v192;
      if ( v194 > 7 )
        v31 = v192[0];
      IpcpTokenHolder::SetFromData((IpcpTokenHolder *)&v143, v30, v31, *v29);
      v32 = &v143;
      v146 = &v143;
      Mso::Logging::MsoSendTraceTag(
        37507995,
        586,
        100,
        L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers token is not empty");
    }
    LODWORD(v139) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 128LL))(v21);
    v37 = &v190;
    if ( v191.m128i_i64[1] > 7uLL )
      v37 = (__int128 *)v190;
    v140[0] = v37;
    Mso::Logging::MsoSendTraceTag<wchar_t const *,unsigned long,unsigned long>(
      v34,
      v33,
      v35,
      v36,
      v127,
      (__int64)v140,
      (__int64)&v139,
      (__int64)&v145);
    LODWORD(v139) = (*v155 != 0) | (*v152 != 0 ? 2 : 0);
    Mso::Logging::MsoSendTraceTag<unsigned long>(
      37507997,
      (_DWORD)v155,
      v38,
      v39,
      (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers ctx flag is %d");
    v182 = (int)v139;
    v40 = &v190;
    if ( v191.m128i_i64[1] > 7uLL )
      v40 = (__int128 *)v190;
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    if ( v40 )
      DynamicMsorid::InitForValue(&v158, &vmsoridUserSidEmailMapping, v40, v41, 1);
    else
      MsoShipAssertTagProc(508048471);
    if ( v161 && MsoFRegReadWz((const struct _msoreg *)v160, v205, 0x104u) )
    {
      if ( !IpcUserHolder::SetFromData((IpcUserHolder *)&v141, 1u, v205, 0x104u) )
      {
        Templates = -2147467259;
LABEL_45:
        std::basic_string<char16_t>::~basic_string<char16_t>(v192);
        std::basic_string<char16_t>::~basic_string<char16_t>(&v190);
        std::basic_string<char16_t>::~basic_string<char16_t>(&v195);
        IpcpTokenHolder::Free((IpcpTokenHolder *)&v143);
        IpcUserHolder::Free((IpcUserHolder *)&v141);
        DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v158);
        if ( v135.m128i_i64[0] )
        {
          v45 = v135;
          v135.m128i_i64[0] = 0;
          v135.m128i_i8[8] = 0;
          Mso::Drm::RmsClient::FreeMemory(v45.m128i_i64[0], (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v45, 8)));
        }
        if ( v134.m128i_i64[0] )
        {
          v46 = v134;
          v134.m128i_i64[0] = 0;
          v134.m128i_i8[8] = 0;
          Mso::Drm::RmsClient::FreeMemory(v46.m128i_i64[0], (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v46, 8)));
        }
        goto LABEL_157;
      }
      Templates = 0;
      v148 = &v141;
      v47 = &v190;
      if ( v191.m128i_i64[1] > 7uLL )
        v47 = (__int128 *)v190;
      v140[0] = v47;
      Mso::Logging::MsoSendTraceTag<wchar_t const *,wchar_t [260]>(
        37507998,
        v42,
        v43,
        v44,
        (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers the stored userid for uniquied is %s is %s",
        v140,
        v205);
    }
    else if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v21 + 56LL))(v21) )
    {
      (*(void (__fastcall **)(__int64, __m128i *, __int64))(*(_QWORD *)v21 + 40LL))(v21, &v141, 5);
      v148 = &v141;
      v50 = &v190;
      if ( v191.m128i_i64[1] > 7uLL )
        v50 = (__int128 *)v190;
      v140[0] = v50;
      Mso::Logging::MsoSendTraceTag<wchar_t const *,wchar_t const *>(
        37507999,
        586,
        v48,
        v49,
        (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers No stored userid found, this is an ADAL iden"
                  "tity, using emailID %s and uniquied is %s",
        &v141.m128i_u64[1],
        v140);
    }
    if ( !v32 && !v148 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v21 + 80LL))(v21) )
    {
      Mso::Logging::MsoSendTraceTag(
        37508000,
        586,
        100,
        L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers if user isn't AD then we should have either token or "
         "user email address. we skip this user");
      goto LABEL_132;
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v21 + 80LL))(v21) )
    {
      Mso::Logging::MsoSendTraceTag(
        37508001,
        586,
        100,
        L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers this is active directorry identity. Setting irmtoken type as windows");
      v143 = 2;
      v144 = 0;
      v145 = 0;
      v146 = &v143;
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v21 + 56LL))(v21) )
    {
      Mso::Logging::MsoSendTraceTag(
        37508002,
        586,
        100,
        L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers This is an ADAL identity");
      MsipcRmsClientType = Mso::Drm::GetMsipcRmsClientType();
      v162 = v21;
      v163 = MsipcRmsClientType;
      v165 = &v162;
      v184 = v166;
    }
    v183 = *((_QWORD *)v147 + 27);
    v129 = 0;
    v52 = Mso::Telemetry::EventFlags::EventFlags(v167, 2);
    v156 = &off_181D9C1C0;
    v157 = "BootstrapLoggedInUser";
    Mso::Telemetry::Activity::Activity(&v142, &v156, v52, &v129);
    v53 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned __int64>(v53, "Index", v149);
    v54 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    LOBYTE(v55) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL))(v21);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v54, "IsUnspecified", v55, 4);
    v56 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    LOBYTE(v57) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 88LL))(v21);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v56, "IsBootstrappable", v57, 4);
    v58 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    LOBYTE(v59) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 56LL))(v21);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v58, "UsesAdal", v59, 4);
    v60 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    LOBYTE(v61) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 64LL))(v21);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v60, "UsesLiveId", v61, 4);
    v62 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    LOBYTE(v63) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 80LL))(v21);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v62, "UsesActiveDirectory", v63, 4);
    LOBYTE(v64) = 1;
    v65 = OGuid::Create(&v197, v64);
    std::wstring::operator=(&v195, v65);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v197);
    v66 = &v195;
    if ( v196.m128i_i64[1] > 7uLL )
      v66 = (__int128 *)v195;
    v185 = v66;
    v67 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)&v142);
    v68 = std::wstring::wstring(&v197, &v195);
    Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v67, "CorrelatingScenarioId", v68, 256);
    sub_180646518(
      (unsigned int)&v153,
      (unsigned int)&v142,
      v21,
      v69,
      (__int64)v148,
      (__int64)v146,
      (__int64)v181,
      (__int64)&v135,
      (__int64)&v134);
    v71 = v153;
    if ( v153 >= 0 )
    {
      if ( v154 == 2 )
        v132 = 1;
      else
        v128 = 1;
    }
    Templates = v153;
    Mso::Telemetry::SetActivityResultHr(
      (Mso::Telemetry *)&v142,
      (struct Mso::Telemetry::Activity *)(unsigned int)v153,
      v70);
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)&v142);
    if ( v71 < 0 )
      break;
    v100 = Mso::Clp::Config::FG::IsAdRmsUsageTelemetryEnabled(v72);
    if ( *(char *)v100 < 0 )
      v101 = Mso::AB::Optimized::FeatureGate::Evaluate(v100);
    else
      v101 = *(_BYTE *)v100 != 0;
    if ( v101 )
      sub_1806468FC(v21, v135.m128i_i64[0]);
    v102 = CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList();
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
      v102,
      v188,
      &v190);
    if ( !v137 && (!v130 || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v21 + 80LL))(v21)) )
    {
      v104 = v135.m128i_i64[0];
      if ( !v135.m128i_i64[0] )
        CrashWithRecovery(0x1F31F70Cu, 0);
      Mso::Logging::MsoSendTraceTag<wchar_t const *>(
        37508035,
        586,
        100,
        v103,
        (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers setting default server for QAT to %s ",
        v104 + 16);
      v105 = v135.m128i_i64[0];
      if ( !v135.m128i_i64[0] )
        CrashWithRecovery(0x1F31F70Cu, 0);
      MsoFRegSetWz((const struct _msoreg *)&vmsoridDrmDefaultServer, *(const wchar_t **)(v105 + 16));
      v106 = v135.m128i_i64[0];
      if ( !v135.m128i_i64[0] )
        CrashWithRecovery(0x1F31F70Cu, 0);
      v107 = *(const wchar_t **)v106;
      if ( *(_QWORD *)v106 || (v107 = *(const wchar_t **)(v106 + 8)) != 0 )
        MsoFRegSetWz((const struct _msoreg *)&vmsoridDefaultServerUrl, v107);
      v130 = 1;
    }
    if ( !(unsigned int)MsoWaitForSingleObject(*((_QWORD *)v147 + 27), 0) )
    {
      Templates = -2147467260;
      goto LABEL_45;
    }
    Templates = 0;
    v108 = v134.m128i_i64[0];
    if ( !v134.m128i_i64[0] )
      CrashWithRecovery(0x1F31F70Cu, 0);
    std::wstring::wstring(&v197, *(_QWORD *)(v108 + 8));
    v199 = v197;
    *(__m128i *)v200 = v198;
    v198 = si128;
    LOWORD(v197) = 0;
    v200[16] = 0;
    v109 = (_QWORD *)std::map<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>>::_Try_emplace<std::pair<std::wstring,bool>,>(
                       v151,
                       v189,
                       &v199);
    std::wstring::operator=(*v109 + 72LL, &v190);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v199);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v197);
    if ( v161 )
    {
      v110 = v134.m128i_i64[0];
      if ( !v134.m128i_i64[0] )
        CrashWithRecovery(0x1F31F70Cu, 0);
      MsoFRegSetWz((const struct _msoreg *)v160, *(const wchar_t **)(v110 + 8));
    }
LABEL_132:
    std::basic_string<char16_t>::~basic_string<char16_t>(v192);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v190);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v195);
    IpcpTokenHolder::Free((IpcpTokenHolder *)&v143);
    IpcUserHolder::Free((IpcUserHolder *)&v141);
    DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v158);
    if ( v135.m128i_i64[0] )
    {
      v111 = v135.m128i_i64[0];
      v112 = _mm_srli_si128(v135, 8);
      v135.m128i_i64[0] = 0;
      v135.m128i_i8[8] = 0;
      Mso::Drm::RmsClient::FreeMemory(v111, (unsigned int)_mm_cvtsi128_si32(v112));
    }
    if ( v134.m128i_i64[0] )
    {
      v113 = v134.m128i_i64[0];
      v114 = _mm_srli_si128(v134, 8);
      v134.m128i_i64[0] = 0;
      v134.m128i_i8[8] = 0;
      Mso::Drm::RmsClient::FreeMemory(v113, (unsigned int)_mm_cvtsi128_si32(v114));
    }
    v19 = *(struct Mso::Telemetry::Activity **)v19;
  }
  v177 = 0;
  v178 = 0;
  v179[0] = 0;
  v180 = 0;
  v179[1] = (unsigned __int64)&v177;
  *v175 = v71;
  v140[0] = "CorrelatingScenarioId";
  v73 = Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(
          v204,
          v140,
          &v195,
          256);
  *((_QWORD *)&v199 + 1) = "HRESULT";
  *(_DWORD *)v200 = v71;
  *(_OWORD *)&v200[8] = 0;
  v201 = 0;
  v202 = 7;
  *(_WORD *)&v200[8] = 0;
  v203 = 4;
  *(_QWORD *)&v199 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
  v140[0] = "DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers failed.";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredHrNamed,Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>>(
    508428704,
    v74,
    100,
    v75,
    (__int64)v140,
    (__int64)&v199,
    v73);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v200[8]);
  Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v204);
  if ( *v152 && v71 == -2147220979 )
  {
    Mso::Logging::MsoSendTraceTag(
      37508032,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers setting m_fUserOnlineRequired to true");
    *((_BYTE *)v147 + 22) = 1;
    goto LABEL_74;
  }
  if ( *v155 && v71 == -2147220978 )
  {
    Mso::Logging::MsoSendTraceTag(
      37508033,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers setting m_fUIPromptRequired to true");
    *((_BYTE *)v147 + 23) = 1;
    goto LABEL_74;
  }
  if ( v71 != -2147023673 )
  {
    v97 = &v190;
    if ( v191.m128i_i64[1] > 7uLL )
      v97 = (__int128 *)v190;
    v98 = -1;
    do
      ++v98;
    while ( *((_WORD *)v97 + v98) );
    if ( v97 )
      DynamicMsorid::InitForValue(&v177, &vmsoridGetKeyUserMapping, v97, v98, 1);
    else
      MsoShipAssertTagProc(508048471);
    if ( v180 && MsoFRegReadWz((const struct _msoreg *)v179, v205, 0x104u) )
    {
      std::wstring::wstring(&v197, v205);
      v199 = v197;
      *(__m128i *)v200 = v198;
      v198 = si128;
      LOWORD(v197) = 0;
      v200[16] = 0;
      v99 = (_QWORD *)std::map<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>>::_Try_emplace<std::pair<std::wstring,bool>,>(
                        v151,
                        v187,
                        &v199);
      std::wstring::operator=(*v99 + 72LL, &v190);
      std::basic_string<char16_t>::~basic_string<char16_t>(&v199);
      std::basic_string<char16_t>::~basic_string<char16_t>(&v197);
    }
    DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v177);
    goto LABEL_132;
  }
  Mso::Logging::MsoSendTraceTag(
    37508034,
    586,
    100,
    L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers user cancelled the action");
  v96 = v147;
  *((_BYTE *)v147 + 23) = 1;
  SetEvent(*((HANDLE *)v96 + 27));
LABEL_74:
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v177);
  std::basic_string<char16_t>::~basic_string<char16_t>(v192);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v190);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v195);
  IpcpTokenHolder::Free((IpcpTokenHolder *)&v143);
  IpcUserHolder::Free((IpcUserHolder *)&v141);
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v158);
  if ( v135.m128i_i64[0] )
  {
    v76 = v135;
    v135.m128i_i64[0] = 0;
    v135.m128i_i8[8] = 0;
    Mso::Drm::RmsClient::FreeMemory(v76.m128i_i64[0], (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v76, 8)));
  }
  if ( v134.m128i_i64[0] )
  {
    v77 = v134;
    v134.m128i_i64[0] = 0;
    v134.m128i_i8[8] = 0;
    Mso::Drm::RmsClient::FreeMemory(v77.m128i_i64[0], (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v77, 8)));
  }
LABEL_78:
  if ( !v138 && !byte_1823105FD )
  {
    Mso::Logging::MsoSendTraceTag(
      37508036,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers Make an extra IpcpBootstrap call in non-logged in case "
       "with silent flag.");
    CIPC_PROMPT_CTX::CIPC_PROMPT_CTX((CIPC_PROMPT_CTX *)v181);
    v141 = 0;
    v142 = 0;
    v78 = Mso::Telemetry::EventFlags::EventFlags(v167, 2);
    v156 = &off_181D9C1C0;
    v157 = "BootstrapUser";
    LOBYTE(v79) = 1;
    Mso::Telemetry::Activity::Activity(&v134, &v156, v79, v78);
    v182 = 1;
    Mso::Logging::MsoSendTraceTag(
      37508037,
      586,
      100,
      L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers we always call in silent mode and use token type as IPC"
       "P_TOKEN_TYPE_WINDOWS for non-domain joined mostly automation scenarios");
    v80 = Mso::Drm::GetMsipcRmsClientType();
    LOBYTE(v81) = v80;
    MsipcProxy = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD, _QWORD, _BYTE *, _QWORD, __m128i *, __m128i *))Mso::Drm::GetMsipcProxyEx(v81);
    v83 = **MsipcProxy;
    v141.m128i_i8[8] = v80;
    v142.m128i_i8[8] = v80;
    LODWORD(v139) = v83(MsipcProxy, 0, 0, 0, v181, 0, &v142, &v141);
    Mso::Logging::MsoSendTraceTag<long>(
      37508038,
      v84,
      v85,
      v86,
      (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers IpcpBootstrapUser no logged on user failed with error : 0x%x",
      &v139);
    Mso::Telemetry::SetActivityResultHr(
      (Mso::Telemetry *)&v134,
      (struct Mso::Telemetry::Activity *)(unsigned int)v139,
      v87);
    byte_1823105FD = 1;
    v89 = Mso::Clp::Config::FG::IsAdRmsUsageTelemetryEnabled(v88);
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v89) && (int)v139 >= 0 )
      byte_1823105FC = (unsigned __int8)sub_1811774A4(v142.m128i_i64[0]) == 2;
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)&v134);
    if ( v142.m128i_i64[0] )
    {
      v90 = v142;
      v142.m128i_i64[0] = 0;
      v142.m128i_i8[8] = 0;
      Mso::Drm::RmsClient::FreeMemory(v90.m128i_i64[0], (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v90, 8)));
    }
    if ( v141.m128i_i64[0] )
    {
      v91 = v141;
      v141.m128i_i64[0] = 0;
      v141.m128i_i8[8] = 0;
      Mso::Drm::RmsClient::FreeMemory(v91.m128i_i64[0], (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v91, 8)));
    }
  }
  v92 = v131;
  if ( !v131 )
  {
    if ( Mso::Threadpool::IsMainThread(v12) )
    {
      if ( !v132 )
      {
        if ( v128 )
        {
          Templates = CMsoDrmRightsTemplatesManager::HrLoadTemplates((_DWORD)v150, (unsigned int)v151, 0, 0, 1);
          if ( Templates < 0 )
            goto LABEL_157;
          TemplatesAsync = Mso::Clp::Config::CG::RefactorLoadTemplatesAsync(v120);
          if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(TemplatesAsync) )
          {
            LOBYTE(v118) = 2;
            goto LABEL_152;
          }
          v122 = sub_1811770B0(&v143, v151);
          sub_181176044(&v138, v122);
        }
        else
        {
          v125 = Mso::Clp::Config::CG::RefactorLoadTemplatesAsync(v115);
          if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v125) )
            goto LABEL_151;
LABEL_89:
          v94 = sub_1811770B0(&v143, v151);
          sub_181175F70(&v138, v94);
        }
        goto LABEL_149;
      }
      if ( !v128 )
      {
        Templates = CMsoDrmRightsTemplatesManager::HrLoadTemplates((_DWORD)v150, (unsigned int)v151, 0, 0, 2);
        if ( Templates < 0 )
          goto LABEL_157;
        v117 = Mso::Clp::Config::CG::RefactorLoadTemplatesAsync(v116);
        if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v117) )
        {
          LOBYTE(v118) = 1;
          goto LABEL_152;
        }
        v119 = sub_1811770B0(&v143, v151);
        sub_181175FD8(&v138, v119);
LABEL_149:
        v123 = Mso::Async::ConcurrentQueue(v95);
        Mso::Async::Post<Mso::Async::IDispatchQueue &>(v123, &v138);
        Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v138);
        std::_Tree<std::_Tmap_traits<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>,0>>(&v143);
        goto LABEL_155;
      }
    }
    Templates = CMsoDrmRightsTemplatesManager::HrLoadTemplates((_DWORD)v150, (unsigned int)v151, 0, 0, 0);
    if ( Templates < 0 )
      goto LABEL_157;
    goto LABEL_155;
  }
  v93 = Mso::Clp::Config::CG::RefactorLoadTemplatesAsync(v12);
  if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v93) )
    goto LABEL_89;
LABEL_151:
  v118 = 0;
LABEL_152:
  sub_1809EC754(v151, v118);
LABEL_155:
  v126 = Mso::Clp::Config::FG::IsAdRmsUsageTelemetryEnabled(v124);
  if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v126) )
  {
    LOBYTE(v10) = byte_1823105FC;
    LOBYTE(v9) = v92;
    sub_180920D30(*v176, v9, v10);
  }
LABEL_157:
  Mso::Logging::MsoSendTraceTag<long>(
    37508039,
    v9,
    v10,
    v11,
    (__int64)L"DRM: CMsoDrmRightsTemplatesManager::BootStrapLoggedInUsers returning with error : 0x%x",
    &Templates);
  _Mtx_unlock(v6);
  std::_Tree<std::_Tmap_traits<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>,0>>(v151);
}

```

## disassembly

```asm
0x1807349b0  mov     rax, rsp
0x1807349b3  mov     [rax+20h], rbx
0x1807349b7  push    rsi
0x1807349b8  push    rdi
0x1807349b9  push    r12
0x1807349bb  push    r14
0x1807349bd  push    r15
0x1807349bf  sub     rsp, 620h
0x1807349c6  movaps  xmmword ptr [rax-38h], xmm6
0x1807349ca  mov     rax, cs:__security_cookie
0x1807349d1  xor     rax, rsp
0x1807349d4  mov     [rsp+648h+var_48], rax
0x1807349dc  mov     al, r8b
0x1807349df  mov     [rsp+648h+var_5F5], al
0x1807349e3  mov     rsi, rdx
0x1807349e6  mov     [rsp+648h+var_540], rcx
0x1807349ee  mov     [rsp+648h+var_470], rcx
0x1807349f6  mov     rbx, rcx
0x1807349f9  mov     [rsp+648h+var_558], rcx
0x180734a01  mov     [rsp+648h+var_5C8], al
0x180734a08  xor     r15d, r15d
0x180734a0b  mov     [rsp+648h+var_5F6], r15b
0x180734a10  call    cs:__imp_?MsoFOfficeShuttingDown@@YAHXZ; MsoFOfficeShuttingDown(void)
0x180734a16  test    eax, eax
0x180734a18  jnz     loc_180736211
0x180734a1e  lea     rcx, ?vmsoridDrmDefaultServer@@3U_msoreg@@B; _msoreg const vmsoridDrmDefaultServer
0x180734a25  call    cs:__imp_?MsoFRegValueExists@@YA_NPEBU_msoreg@@@Z; MsoFRegValueExists(_msoreg const *)
0x180734a2b  mov     dil, al
0x180734a2e  mov     [rsp+648h+var_5C0], al
0x180734a35  mov     [rsp+648h+var_5F4], r15b
0x180734a3a  mov     [rsp+648h+var_5F8], r15b
0x180734a3f  lea     r9, aDrmCmsodrmrigh_99; "DRM: CMsoDrmRightsTemplatesManager::Boo"...
0x180734a46  mov     edx, 24Ah
0x180734a4b  mov     ecx, 23C5395h
0x180734a50  lea     r8d, [r15+64h]
0x180734a54  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x180734a5a  lea     rcx, [rsp+648h+var_538]
0x180734a62  call    ??0?$map@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@VEmailAddressComparer@@V?$allocator@U?$pair@$$CBU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>>::map<std::pair<std::wstring,bool>,std::wstring,EmailAddressComparer,std::allocator<std::pair<std::pair<std::wstring,bool> const,std::wstring>>>(void)
0x180734a67  lea     r12, [rsi+8]
0x180734a6b  mov     [rsp+648h+var_438], r12
0x180734a73  mov     rax, [r12]
0x180734a77  mov     [rsp+648h+var_5B8], rax
0x180734a7f  mov     [rsp+648h+var_548], r15
0x180734a87  lea     r14, [rbx+38h]
0x180734a8b  mov     [rsp+648h+var_468], r14
0x180734a93  mov     rcx, r14; this
0x180734a96  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180734a9b  call    ?GetDrmConfig@Drm@Mso@@YAAEAUIDrmConfig@@XZ; Mso::Drm::GetDrmConfig(void)
0x180734aa0  mov     rdx, rax
0x180734aa3  mov     rcx, [rax]
0x180734aa6  mov     rax, [rcx+8]
0x180734aaa  mov     rcx, rdx
0x180734aad  call    cs:__guard_dispatch_icall_fptr
0x180734ab3  test    al, al
0x180734ab5  jnz     short loc_180734AC4
0x180734ab7  mov     [rsp+648h+var_5F0], 80004005h
0x180734abf  jmp     loc_1807361DA
0x180734ac4  mov     [rsp+648h+var_5F0], r15d
0x180734ac9  lea     rax, [rbx+1Ch]
0x180734acd  mov     [rsp+648h+var_440], rax
0x180734ad5  mov     [rax], r15d
0x180734ad8  lea     rax, [rsp+648h+var_5B8]
0x180734ae0  mov     [rsp+648h+var_620], rax
0x180734ae5  lea     rax, aDrmCmsodrmrigh_64; "DRM: CMsoDrmRightsTemplatesManager::Boo"...
0x180734aec  mov     [rsp+648h+var_628], rax
0x180734af1  mov     ecx, 23C5396h
0x180734af6  call    ??$MsoSendTraceTag@_K@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEB_K@Z; Mso::Logging::MsoSendTraceTag<unsigned __int64>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,unsigned __int64 const &)
0x180734afb  call    ?GetBootStrappedIdentityList@CMsoDrmRightsTemplatesManager@@SAAEAV?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList(void)
0x180734b00  mov     rcx, [rax+10h]
0x180734b04  cmp     [r12], rcx
0x180734b08  jbe     short loc_180734B54
0x180734b0a  mov     [rsp+648h+var_5F7], r15b
0x180734b0f  mov     edx, 2
0x180734b14  lea     rcx, [rsp+648h+var_5A8]
0x180734b1c  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x180734b21  lea     r12, off_181D9C1C0
0x180734b28  mov     qword ptr [rsp+648h+var_588], r12
0x180734b30  lea     rcx, aMipprotections; "MipProtectionSDKEnabled"
0x180734b37  mov     qword ptr [rsp+648h+var_588+8], rcx
0x180734b3f  lea     r8, [rsp+648h+var_5F7]
0x180734b44  mov     rdx, rax
0x180734b47  lea     rcx, [rsp+648h+var_588]
0x180734b4f  call    ??$SendTelemetryEvent@$$V@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@$$QEAVEventExportability@01@@Z; Mso::Telemetry::SendTelemetryEvent<>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Mso::Telemetry::EventExportability &&)
0x180734b54  test    dil, dil
0x180734b57  jz      short loc_180734B86
0x180734b59  mov     r8d, 104h
0x180734b5f  lea     rdx, [rsp+648h+var_258]
0x180734b67  lea     rcx, ?vmsoridDrmDefaultServer@@3U_msoreg@@B; _msoreg const vmsoridDrmDefaultServer
0x180734b6e  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x180734b74  lea     rax, [rsp+648h+var_258]
0x180734b7c  mov     [rsp+648h+var_620], rax
0x180734b81  call    ??$MsoSendTraceTag@$$BY0BAE@_W@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEAY0BAE@$$CB_W@Z; Mso::Logging::MsoSendTraceTag<wchar_t [260]>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,wchar_t const (&)[260])
0x180734b86  lea     rax, [rbx+14h]
0x180734b8a  mov     [rsp+648h+var_520], rax
0x180734b92  cmp     [rax], r15b
0x180734b95  jnz     short loc_180734BB8
0x180734b97  lea     r9, aDrmCmsodrmrigh_59; "DRM: CMsoDrmRightsTemplatesManager::Boo"...
0x180734b9e  mov     edx, 24Ah
0x180734ba3  mov     ecx, 23C5398h
0x180734ba8  mov     r8d, 64h ; 'd'
0x180734bae  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x180734bb4  mov     [rbx+16h], r15b
0x180734bb8  lea     rax, [rbx+15h]
0x180734bbc  mov     [rsp+648h+var_510], rax
0x180734bc4  cmp     [rax], r15b
0x180734bc7  jnz     short loc_180734BEA
0x180734bc9  lea     r9, aDrmCmsodrmrigh_83; "DRM: CMsoDrmRightsTemplatesManager::Boo"...
0x180734bd0  mov     edx, 24Ah
0x180734bd5  mov     ecx, 23C5399h
0x180734bda  mov     r8d, 64h ; 'd'
0x180734be0  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x180734be6  mov     [rbx+17h], r15b
0x180734bea  mov     dword ptr [rbx+10h], 1
0x180734bf1  mov     rsi, [rsi]
0x180734bf4  mov     rdi, [rsi]
0x180734bf7  mov     [rsp+648h+var_460], rsi
0x180734bff  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180734c07  mov     [rsp+648h+var_5B0], rdi
0x180734c0f  cmp     rdi, rsi
0x180734c12  jz      loc_18073590C
0x180734c18  mov     r12, [rdi+10h]
0x180734c1c  mov     [rsp+648h+var_458], r12
0x180734c24  xorps   xmm0, xmm0
0x180734c27  movdqa  [rsp+648h+var_5E8], xmm0
0x180734c2d  movdqa  [rsp+648h+var_5D8], xmm0
0x180734c33  mov     [rsp+648h+var_258], r15w
0x180734c3c  xor     eax, eax
0x180734c3e  movups  [rsp+648h+var_4F8], xmm0
0x180734c46  mov     [rsp+648h+var_4E8], rax
0x180734c4e  xorps   xmm1, xmm1
0x180734c51  movups  [rsp+648h+var_4E0], xmm1
0x180734c59  movups  [rsp+648h+var_4D0], xmm1
0x180734c61  mov     [rsp+648h+var_4C0], r15b
0x180734c69  lea     rax, [rsp+648h+var_4F8]
0x180734c71  mov     qword ptr [rsp+648h+var_4D0], rax
0x180734c79  mov     dword ptr [rsp+648h+var_598], r15d
0x180734c81  mov     qword ptr [rsp+648h+var_598+8], r15
0x180734c89  mov     rax, r15
0x180734c8c  mov     [rsp+648h+var_550], rax
0x180734c94  mov     [rsp+648h+var_450], rax
0x180734c9c  mov     [rsp+648h+var_578], r15d
0x180734ca4  mov     [rsp+648h+var_570], r15
0x180734cac  mov     [rsp+648h+var_568], r15d
0x180734cb4  mov     [rsp+648h+var_560], r15
0x180734cbc  movups  [rsp+648h+var_340], xmm0
0x180734cc4  movdqu  [rsp+648h+var_330], xmm6
0x180734ccd  mov     word ptr [rsp+648h+var_340], r15w
0x180734cd6  lea     rcx, [rsp+648h+var_3E8]; this
0x180734cde  call    ??0CIPC_PROMPT_CTX@@QEAA@XZ; CIPC_PROMPT_CTX::CIPC_PROMPT_CTX(void)
0x180734ce3  mov     [rsp+648h+var_4B8], r15
0x180734ceb  mov     [rsp+648h+var_4B0], r15b
0x180734cf3  mov     [rsp+648h+var_4A8], 18h
0x180734cff  lea     rax, ?GetTokenCallbackQuiet@@YAJPEAXPEAU_IPC_NAME_VALUE_LIST@@PEAPEAUIPC_AUTH_TOKEN_HANDLE__@@@Z; GetTokenCallbackQuiet(void *,_IPC_NAME_VALUE_LIST *,IPC_AUTH_TOKEN_HANDLE__ * *)
0x180734d06  mov     [rsp+648h+var_4A0], rax
0x180734d0e  mov     [rsp+648h+var_498], r15
0x180734d16  mov     [rsp+648h+var_490], 3
0x180734d22  lea     rax, [rsp+648h+var_4A8]
0x180734d2a  mov     [rsp+648h+var_488], rax
0x180734d32  xorps   xmm0, xmm0
0x180734d35  movups  [rsp+648h+var_380], xmm0
0x180734d3d  movdqu  [rsp+648h+var_370], xmm6
0x180734d46  mov     word ptr [rsp+648h+var_380], r15w
0x180734d4f  movups  xmmword ptr [rsp+648h+var_360], xmm0
0x180734d57  mov     [rsp+648h+var_350], r15
0x180734d5f  mov     [rsp+648h+var_348], 7
0x180734d6b  mov     word ptr [rsp+648h+var_360], r15w
0x180734d74  mov     rax, [r12]
0x180734d78  mov     rcx, r12
0x180734d7b  mov     rax, [rax+70h]
0x180734d7f  call    cs:__guard_dispatch_icall_fptr
0x180734d85  or      r8, 0FFFFFFFFFFFFFFFFh
0x180734d89  inc     r8
0x180734d8c  cmp     [rax+r8*2], r15w
0x180734d91  jnz     short loc_180734D89
0x180734d93  mov     rdx, rax
0x180734d96  lea     rcx, [rsp+648h+var_380]; void *
0x180734d9e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180734da3  mov     rax, [rsp+648h+var_548]
0x180734dab  inc     rax
0x180734dae  mov     [rsp+648h+var_548], rax
0x180734db6  mov     [rsp+648h+var_448], rax
0x180734dbe  call    ?GetBootStrappedIdentityList@CMsoDrmRightsTemplatesManager@@SAAEAV?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList(void)
0x180734dc3  lea     r8, [rsp+648h+var_380]
0x180734dcb  lea     rdx, [rsp+648h+var_3B8]
0x180734dd3  mov     rcx, rax
0x180734dd6  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180734ddb  mov     rbx, rax
0x180734dde  call    ?GetBootStrappedIdentityList@CMsoDrmRightsTemplatesManager@@SAAEAV?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; CMsoDrmRightsTemplatesManager::GetBootStrappedIdentityList(void)
0x180734de3  mov     rcx, [rax+8]
0x180734de7  cmp     [rbx], rcx
0x180734dea  jnz     loc_180735F5C
0x180734df0  mov     rax, [rsp+648h+var_520]
0x180734df8  cmp     [rax], r15b
0x180734dfb  jnz     loc_180734FB0
0x180734e01  lea     r9, aDrmCmsodrmrigh_3; "DRM: CMsoDrmRightsTemplatesManager::Boo"...
0x180734e08  mov     edx, 24Ah
0x180734e0d  mov     ecx, 23C539Ah
0x180734e12  mov     r8d, 64h ; 'd'
0x180734e18  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x180734e1e  mov     rax, [rsp+648h+var_558]
0x180734e26  mov     [rax+16h], r15b
0x180734e2a  mov     rax, [r12]
0x180734e2e  mov     rcx, r12
0x180734e31  mov     rax, [rax+48h]
0x180734e35  call    cs:__guard_dispatch_icall_fptr
0x180734e3b  test    al, al
0x180734e3d  jnz     loc_180734EE9
0x180734e43  mov     rax, [r12]
0x180734e47  lea     rdx, [rsp+648h+var_320]
0x180734e4f  mov     rcx, r12
0x180734e52  mov     rax, [rax+8]
0x180734e56  call    cs:__guard_dispatch_icall_fptr
0x180734e5c  mov     rdx, rax
0x180734e5f  lea     rcx, [rsp+648h+var_360]
0x180734e67  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180734e6c  lea     rcx, [rsp+648h+var_320]; void *
0x180734e74  call    ??1?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@XZ; std::basic_string<char16_t>::~basic_string<char16_t>(void)
0x180734e79  jmp     short loc_180734EE9
0x180734e7b  xor     r15d, r15d
0x180734e7e  mov     rax, [rsp+648h+var_448]
0x180734e86  mov     [rsp+648h+var_548], rax
0x180734e8e  mov     r14, [rsp+648h+var_468]
0x180734e96  mov     rdi, [rsp+648h+var_5B0]
0x180734e9e  mov     rsi, [rsp+648h+var_460]
0x180734ea6  mov     r12, [rsp+648h+var_458]
0x180734eae  mov     rax, [rsp+648h+var_450]
0x180734eb6  mov     [rsp+648h+var_550], rax
0x180734ebe  mov     [rsp+648h+var_560], rax
0x180734ec6  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180734ece  mov     rax, [rsp+648h+var_470]
0x180734ed6  mov     [rsp+648h+var_540], rax
0x180734ede  mov     al, [rsp+648h+var_5C8]
0x180734ee5  mov     [rsp+648h+var_5F5], al
0x180734ee9  cmp     [rsp+648h+var_350], r15
0x180734ef1  jz      loc_180734FB0
0x180734ef7  lea     rcx, [rsp+648h+var_360]
0x180734eff  cmp     [rsp+648h+var_348], 7
0x180734f08  jbe     short loc_180734F1C
0x180734f0a  mov     rcx, [rsp+648h+var_360]
0x180734f12  test    rcx, rcx
0x180734f15  jnz     short loc_180734F1C
0x180734f17  mov     rax, r15
0x180734f1a  jmp     short loc_180734F2A
0x180734f1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180734f20  inc     rax
0x180734f23  cmp     [rcx+rax*2], r15w
0x180734f28  jnz     short loc_180734F20
0x180734f2a  test    eax, eax
0x180734f2c  jns     short loc_180734F35
0x180734f2e  mov     ecx, 5
0x180734f33  int     29h; Win8: RtlFailFast(ecx)
0x180734f35  mov     dword ptr [rsp+648h+var_5B0], eax
0x180734f3c  mov     r8d, 1
0x180734f42  lea     rdx, [rsp+648h+var_478]
0x180734f4a  lea     rcx, [rsp+648h+var_5B0]
0x180734f52  call    ??$?HH@?$SafeInt@KVSafeInt_InvalidParameter@safeint_exception_handlers@@@@QEBA?AV0@H@Z; SafeInt<ulong,safeint_exception_handlers::SafeInt_InvalidParameter>::operator+<int>(int)
0x180734f57  lea     r8, [rsp+648h+var_360]
0x180734f5f  cmp     [rsp+648h+var_348], 7
0x180734f68  cmova   r8, [rsp+648h+var_360]; wchar_t *
0x180734f71  mov     r9d, [rax]; unsigned int
0x180734f74  lea     rcx, [rsp+648h+var_578]; this
0x180734f7c  call    ?SetFromData@IpcpTokenHolder@@QEAA_NKPEB_WK@Z; IpcpTokenHolder::SetFromData(ulong,wchar_t const *,ulong)
0x180734f81  lea     rbx, [rsp+648h+var_578]
0x180734f89  mov     [rsp+648h+var_560], rbx
0x180734f91  lea     r9, aDrmCmsodrmrigh_11; "DRM: CMsoDrmRightsTemplatesManager::Boo"...
0x180734f98  mov     edx, 24Ah
0x180734f9d  mov     ecx, 23C539Bh
0x180734fa2  mov     r8d, 64h ; 'd'
0x180734fa8  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x180734fae  jmp     short loc_180734FB8
0x180734fb0  mov     rbx, [rsp+648h+var_560]
0x180734fb8  mov     rax, [r12]
0x180734fbc  mov     rcx, r12
0x180734fbf  mov     rax, [rax+80h]
0x180734fc6  call    cs:__guard_dispatch_icall_fptr
0x180734fcc  mov     dword ptr [rsp+648h+var_5B0], eax
0x180734fd3  lea     rax, [rsp+648h+var_380]
0x180734fdb  cmp     qword ptr [rsp+648h+var_370+8], 7
0x180734fe4  cmova   rax, qword ptr [rsp+648h+var_380]
0x180734fed  mov     [rsp+648h+var_5A8], rax
0x180734ff5  lea     rax, [rsp+648h+var_568]
0x180734ffd  mov     [rsp+648h+var_610], rax
0x180735002  lea     rax, [rsp+648h+var_5B0]
0x18073500a  mov     [rsp+648h+var_618], rax
0x18073500f  lea     rax, [rsp+648h+var_5A8]
0x180735017  mov     [rsp+648h+var_620], rax
0x18073501c  call    ??$MsoSendTraceTag@PEB_WKK@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBQEB_WAEBK5@Z; Mso::Logging::MsoSendTraceTag<wchar_t const *,ulong,ulong>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,wchar_t const * const &,ulong const &,ulong const &)
0x180735021  mov     rcx, [rsp+648h+var_520]
0x180735029  mov     al, [rcx]
0x18073502b  neg     al
0x18073502d  sbb     ecx, ecx
0x18073502f  and     ecx, 2
0x180735032  mov     eax, r15d
0x180735035  mov     rdx, [rsp+648h+var_510]
0x18073503d  cmp     [rdx], r15b
0x180735040  setnz   al
0x180735043  or      ecx, eax
0x180735045  mov     dword ptr [rsp+648h+var_5B0], ecx
0x18073504c  lea     rax, [rsp+648h+var_5B0]
0x180735054  mov     [rsp+648h+var_620], rax
  ... truncated ...
```
