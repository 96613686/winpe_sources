# WinMainCommon(HINSTANCE__ *,HINSTANCE__ *,char *,int)

- ea: `0x140019a6c`
- end: `0x14001c987`
- name: `?WinMainCommon@@YAKPEAUHINSTANCE__@@0PEADH@Z`
- size: `12059`
- prototype: `__int64 __fastcall(HINSTANCE, HINSTANCE, char *)`
- caller_count: `1`
- callee_count: `113`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14001e280`

## callees

- `0x140001f30`
- `0x1400042f0`
- `0x140004588`
- `0x140004e28`
- `0x140005a5c`
- `0x140005ac4`
- `0x140009140`
- `0x1400095b4`
- `0x14000ad3c`
- `0x14000adcc`
- `0x14000afcc`
- `0x14000b0fc`
- `0x14000b37c`
- `0x14000b84c`
- `0x14000c2e4`
- `0x14000ccd0`
- `0x14000cd24`
- `0x14000df08`
- `0x14000df9c`
- `0x14000e548`
- `0x14000ea50`
- `0x14000f18c`
- `0x14000f614`
- `0x14000f78c`
- `0x14000fe60`
- `0x1400117ac`
- `0x140012178`
- `0x1400123f4`
- `0x140012964`
- `0x140012c28`
- `0x140013650`
- `0x140014040`
- `0x1400142a4`
- `0x140014fdc`
- `0x140015114`
- `0x1400174c0`
- `0x14001754c`
- `0x1400175d8`
- `0x140017664`
- `0x1400176f0`
- `0x1400179d0`
- `0x140017a88`
- `0x140017cb8`
- `0x140018b78`
- `0x140019a6c`
- `0x14001cbd4`
- `0x14001cd10`
- `0x14001cdb0`
- `0x14001d0c0`
- `0x14001d608`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentLinkedEnrollmentId` at `0x14001ab06`
- `dmEnrollEngine!GetEnrollmentLinkedEnrollmentId` at `0x14001ab06`
- `dmEnrollEngine!GetIsRecoveryAllowed` at `0x14001a6ce`
- `dmEnrollEngine!GetIsRecoveryAllowed` at `0x14001a6ce`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x14001ab73`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x14001c22e`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x14001ab73`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x14001c22e`
- `dmEnrollEngine!SetEnrollState` at `0x14001a732`
- `dmEnrollEngine!SetEnrollState` at `0x14001a732`
- `dmEnrollEngine!SetMmpcEnrollmentFlag` at `0x14001c5ed`
- `dmEnrollEngine!SetMmpcEnrollmentFlag` at `0x14001c5ed`
- `dmEnrollEngine!GetEnrollmentType` at `0x140019e30`
- `dmEnrollEngine!GetEnrollmentType` at `0x140019e30`
- `dmEnrollEngine!GetEnrollmentAuthPolicy` at `0x14001a6f9`
- `dmEnrollEngine!GetEnrollmentAuthPolicy` at `0x14001a6f9`
- `dmEnrollEngine!__imp_DiscoverEndpoint` at `0x14001c6bd`
- `dmEnrollEngine!__imp_DiscoverEndpoint` at `0x14001c6bd`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x14001a583`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x14001a583`
- `DMCmnUtils!DmDisableTask` at `0x14001ae9b`
- `DMCmnUtils!DmDisableTask` at `0x14001ae9b`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x14001a3ec`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x14001a3ec`
- `DMCmnUtils!DmRemoveToastNotificationByExecutablePath` at `0x14001a45d`
- `DMCmnUtils!DmRemoveToastNotificationByExecutablePath` at `0x14001a45d`
- `DMCmnUtils!CopyString` at `0x140019dbe`
- `DMCmnUtils!CopyString` at `0x140019ed7`
- `DMCmnUtils!CopyString` at `0x140019ef6`
- `DMCmnUtils!CopyString` at `0x140019f15`
- `DMCmnUtils!CopyString` at `0x140019f34`
- `DMCmnUtils!CopyString` at `0x140019f53`
- `DMCmnUtils!CopyString` at `0x140019dbe`
- `DMCmnUtils!CopyString` at `0x140019ed7`
- `DMCmnUtils!CopyString` at `0x140019ef6`
- `DMCmnUtils!CopyString` at `0x140019f15`
- `DMCmnUtils!CopyString` at `0x140019f34`
- `DMCmnUtils!CopyString` at `0x140019f53`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x14001a323`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x14001b8eb`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x14001c64f`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x14001a323`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x14001b8eb`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x14001c64f`
- `DMCmnUtils!DmDeleteTask` at `0x14001a57d`
- `DMCmnUtils!DmDeleteTask` at `0x14001aa7f`
- `DMCmnUtils!DmDeleteTask` at `0x14001aed8`
- `DMCmnUtils!DmDeleteTask` at `0x14001afec`
- `DMCmnUtils!DmDeleteTask` at `0x14001b14a`
- `DMCmnUtils!DmDeleteTask` at `0x14001b232`
- `DMCmnUtils!DmDeleteTask` at `0x14001bee9`
- `DMCmnUtils!DmDeleteTask` at `0x14001a57d`
- `DMCmnUtils!DmDeleteTask` at `0x14001aa7f`
- `DMCmnUtils!DmDeleteTask` at `0x14001aed8`
- `DMCmnUtils!DmDeleteTask` at `0x14001afec`
- `DMCmnUtils!DmDeleteTask` at `0x14001b14a`
- `DMCmnUtils!DmDeleteTask` at `0x14001b232`
- `DMCmnUtils!DmDeleteTask` at `0x14001bee9`
- `omadmapi!__imp_ProcessCommandLine` at `0x140019ca2`
- `omadmapi!__imp_ProcessCommandLine` at `0x140019cd5`
- `omadmapi!__imp_ProcessCommandLine` at `0x140019ca2`
- `omadmapi!__imp_ProcessCommandLine` at `0x140019cd5`
- `omadmapi!__imp_OmaDmInitiateSessionWithSessionID` at `0x14001ba11`
- `omadmapi!__imp_OmaDmInitiateSessionWithSessionID` at `0x14001ba60`
- `omadmapi!__imp_OmaDmInitiateSessionWithSessionID` at `0x14001bab0`
- `omadmapi!__imp_OmaDmInitiateSessionWithSessionID` at `0x14001ba11`
- `omadmapi!__imp_OmaDmInitiateSessionWithSessionID` at `0x14001ba60`
- `omadmapi!__imp_OmaDmInitiateSessionWithSessionID` at `0x14001bab0`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x14001b571`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x14001b84d`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x14001b94a`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x14001b571`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x14001b84d`
- `omadmapi!__imp_OmaDmInitiateSessionAsUser` at `0x14001b94a`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001ae2a`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001b506`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001b6f9`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001b8b4`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001c01a`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001ae2a`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001b506`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001b6f9`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001b8b4`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x14001c01a`
- `omadmapi!__imp_FreeCommandLineOptions` at `0x14001c7e7`
- `omadmapi!__imp_FreeCommandLineOptions` at `0x14001c7e7`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001a8d6`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001acbc`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001bcc7`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001bdf6`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001a8d6`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001acbc`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001bcc7`
- `omadmapi!__imp_?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z` at `0x14001bdf6`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a904`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a95b`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a995`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a9ab`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001acd8`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001ad2f`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001ad62`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bcf5`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bd4c`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bd86`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bd9c`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be2b`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be53`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be68`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be82`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a904`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a95b`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a995`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001a9ab`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001acd8`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001ad2f`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001ad62`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bcf5`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bd4c`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bd86`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001bd9c`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be2b`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be53`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be68`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14001be82`
- `omadmapi!__imp_?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z` at `0x14001a917`
- `omadmapi!__imp_?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z` at `0x14001aceb`
- `omadmapi!__imp_?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z` at `0x14001bd08`
- `omadmapi!__imp_?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z` at `0x14001a917`
- `omadmapi!__imp_?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z` at `0x14001aceb`
- `omadmapi!__imp_?IsConfigRefreshSemaphoreSignaled@@YAHPEBG@Z` at `0x14001bd08`
- `UMPDC!PdcActivationClientUnregister` at `0x14001c3b2`
- `UMPDC!PdcActivationClientUnregister` at `0x14001c46b`
- `UMPDC!PdcActivationClientUnregister` at `0x14001c3b2`
- `UMPDC!PdcActivationClientUnregister` at `0x14001c46b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001a1ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001a1ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001a1cd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001a1cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001a20e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001a20e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a4ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001aad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ab52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b7a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b875`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a4ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001aad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ab52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b7a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001b875`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a4df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aaca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ab44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b793`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b867`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a4df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aaca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ab44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b793`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001aac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001aac2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001a62f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001aae0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001a62f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001aae0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001c0c3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001c3f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001c0c3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001c3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001c39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001c457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001c55d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001c39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001c457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001c55d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14001c36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14001c36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001c0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001c3db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001c0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001c3db`

## string_xrefs

- `0x14001acb0`: `DeclaredConfigurationRefresh`
- `0x14001ace4`: `DeclaredConfigurationRefresh`
- `0x14001a8ca`: `ConfigRefresh`
- `0x14001a910`: `ConfigRefresh`
- `0x14001bcbd`: `ConfigRefresh`
- `0x14001bd01`: `ConfigRefresh`
- `0x14001bdec`: `ConfigRefresh`
- `0x14001a3e5`: `DMAppsRes.dll`
- `0x140019e64`: `Refresh schedule created by Declared Configuration to refresh any settings changed on the device`
- `0x140019ff9`: `com.microsoft:mdm.upgrade`
- `0x14001a1c6`: `ShellChromeAPI.dll`
- `0x14001a373`: `%windir%\system32\deviceenroller.exe`
- `0x14001a441`: `%windir%\system32\deviceenroller.exe`
- `0x14001a3d5`: `ms-settings:workplace-repairtoken`
- `0x14001a56d`: `Schedule created by enrollment client to reattest client certificate`
- `0x14001aa32`: `Schedule created by enrollment client for automatically enrolling in MDM from AAD`
- `0x14001aa6f`: `Schedule created by enrollment client for automatically enrolling in MDM from AAD using AAD device credential`
- `0x14001add7`: `com.microsoft.mdm.wscstartup`
- `0x14001ade5`: `Sync Session triggered by Device Status CSP update`
- `0x14001ae89`: `Wsc Startup event listener created by enrollment client`
- `0x14001aec5`: `Schedule created by dm client to unenroll Mmpc from dual enrollment`
- `0x14001b21f`: `Schedule created by dm client to unenroll Mmpc from dual enrollment`
- `0x14001afd9`: `Schedule created by dm client for dual enrollment to Mmpc`
- `0x14001b137`: `Schedule created by dm client for dual enrollment to Mmpc`
- `0x14001bed6`: `Login Schedule created by OmaDm client when container is not availbale`

## pseudocode

```c
__int64 __fastcall WinMainCommon(HINSTANCE a1, HINSTANCE a2, char *a3)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // r14
  int cchWideChar; // edi
  WCHAR *v7; // rax
  OLECHAR *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // r8d
  BOOL v13; // edi
  LPWSTR CommandLineW; // rax
  int v15; // eax
  LPWSTR v16; // rax
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // ecx
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned __int16 *v23; // rcx
  signed int ActiveUserLocalAdmin; // eax
  __int64 v25; // rdx
  const unsigned __int16 *v26; // rcx
  __int64 v27; // r8
  HRESULT v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  HRESULT v31; // eax
  __int64 v32; // rdx
  unsigned int v33; // r8d
  CEnrollmentLogger *Logger; // rax
  unsigned int v35; // eax
  __int64 *v36; // rdx
  HMODULE Library; // rax
  HMODULE v38; // rbx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  signed int v41; // eax
  int v42; // eax
  __int64 v43; // r8
  const unsigned __int16 *v44; // r8
  CEnrollmentLogger *v45; // rax
  void *v46; // rbx
  HANDLE ProcessHeap; // rax
  BSTR v48; // rbx
  __int64 DatabaseManagerInstance; // rbx
  int (__fastcall *v50)(__int64, __int64, BSTR **); // r14
  BSTR *v51; // rdx
  BSTR *v52; // rbx
  unsigned int (__fastcall *v53)(BSTR *, __int64 *); // r14
  __int64 v54; // rdx
  __int64 v55; // r15
  int (__fastcall *v56)(__int64, BSTR *); // r12
  OLECHAR *v57; // r14
  DWORD v58; // ebx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned int v62; // r8d
  HANDLE CurrentThread; // rax
  signed int v64; // eax
  __int64 v65; // r8
  CConfigRefreshLogger *v66; // rax
  const unsigned __int16 *v67; // rdx
  const unsigned __int16 *v68; // r8
  CConfigRefreshLogger *v69; // rax
  CConfigRefreshLogger *v70; // rax
  CConfigRefreshLogger *v71; // rax
  BSTR v72; // rcx
  __int64 v73; // r8
  CConfigRefreshLogger *v74; // rax
  CConfigRefreshLogger *v75; // rax
  int v76; // eax
  const unsigned __int16 *v77; // r8
  int v78; // eax
  const unsigned __int16 *v79; // rdx
  BSTR v80; // r14
  DWORD v81; // ebx
  HANDLE v82; // rax
  CEnrollmentLogger *v83; // rcx
  const unsigned __int16 *v84; // r8
  HANDLE v85; // rax
  int v86; // eax
  unsigned int v87; // r8d
  __int64 v88; // r8
  int v89; // eax
  __int64 v90; // r8
  int LinkedEnrollmentStringRegistry; // eax
  unsigned int v92; // ebx
  __int64 v93; // rdx
  unsigned int v94; // edx
  __int64 v95; // rcx
  int v96; // eax
  __int64 v97; // r8
  unsigned int v98; // r8d
  unsigned int v99; // edx
  const unsigned __int16 *v100; // rdx
  const unsigned __int16 *v101; // rdx
  unsigned int v102; // r8d
  __int64 v103; // rcx
  unsigned int v104; // r8d
  int v105; // eax
  __int64 v106; // r8
  __int64 v107; // r8
  const unsigned __int16 *v108; // rdx
  RPC_WSTR v109; // rcx
  unsigned int v110; // r8d
  int v111; // r9d
  int ConfigRefreshKey; // eax
  HKEY v113; // rcx
  HKEY v114; // rbx
  int ValueW; // eax
  bool v116; // sf
  BOOL v117; // r14d
  unsigned int v118; // eax
  __int64 v119; // rdx
  int *v120; // r8
  CEnrollmentLogger *v121; // rax
  void *v122; // rbx
  HANDLE v123; // rax
  const wchar_t *v124; // rbx
  __int64 v125; // rcx
  unsigned int v126; // eax
  void *v127; // rbx
  HANDLE v128; // rax
  const wchar_t *v129; // rbx
  __int64 v130; // rcx
  BSTR v131; // rbx
  bool v132; // zf
  HANDLE v133; // rax
  CEnrollmentLogger *v134; // rax
  CEnrollmentLogger *v135; // rax
  BSTR v136; // rcx
  CEnrollmentLogger *v137; // rax
  BSTR v138; // rcx
  CEnrollmentLogger *v139; // rax
  CEnrollmentLogger *v140; // rax
  CEnrollmentLogger *v141; // rax
  CEnrollmentLogger *v142; // rax
  __int64 v143; // r8
  __int64 *v144; // rdx
  unsigned int v145; // ebx
  int v146; // eax
  __int64 v147; // rdx
  CConfigRefreshLogger *v148; // rax
  void **v149; // rax
  CConfigRefreshLogger *v150; // rax
  __int64 v151; // r8
  CConfigRefreshLogger *v152; // rax
  CConfigRefreshLogger *v153; // rax
  __int64 v154; // r8
  unsigned int j; // r14d
  void **v156; // rax
  unsigned int refreshed; // eax
  CEnrollmentLogger *v158; // rax
  unsigned __int16 *v159; // rdx
  int AlertData; // eax
  BSTR v161; // rcx
  BSTR v162; // rcx
  BSTR *v163; // rcx
  BSTR v164; // rcx
  CEnrollmentLogger *v165; // rax
  int v166; // eax
  HSTRING *v167; // rax
  __int64 v168; // rdx
  HRESULT v169; // eax
  int v170; // eax
  BSTR v171; // rcx
  BSTR *v172; // rcx
  BSTR v173; // rcx
  BSTR *v174; // rcx
  BSTR v175; // rcx
  int v176; // eax
  __int64 v177; // r8
  int v178; // eax
  __int64 v179; // rcx
  unsigned __int64 v180; // rdx
  _BYTE *v181; // r11
  BSTR i; // rax
  REGHANDLE v183; // rcx
  REGHANDLE v184; // rcx
  REGHANDLE v185; // rcx
  REGHANDLE v186; // rcx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  LPWSTR lpWideCharStra; // [rsp+20h] [rbp-E0h]
  unsigned int v190[4]; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString[2]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING pvData; // [rsp+70h] [rbp-90h] BYREF
  RPC_WSTR StringUuid; // [rsp+78h] [rbp-88h] BYREF
  __int64 v194; // [rsp+80h] [rbp-80h] BYREF
  BSTR *v195; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v196; // [rsp+90h] [rbp-70h] BYREF
  char v197; // [rsp+94h] [rbp-6Ch]
  unsigned int v198; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbData; // [rsp+9Ch] [rbp-64h] BYREF
  struct IEnrollEngine *v200; // [rsp+A0h] [rbp-60h] BYREF
  RPC_WSTR v201; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v202; // [rsp+B0h] [rbp-50h] BYREF
  BOOL v203; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v204; // [rsp+BCh] [rbp-44h]
  HLOCAL v205; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+C8h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL v208; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v209; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR *v210; // [rsp+E8h] [rbp-18h]
  __int64 v211; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v212[16]; // [rsp+F8h] [rbp-8h] BYREF
  const unsigned __int16 *v213; // [rsp+108h] [rbp+8h]
  int v214; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v215; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v216; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v217; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v218; // [rsp+158h] [rbp+58h]
  int v219; // [rsp+170h] [rbp+70h]
  int v220; // [rsp+180h] [rbp+80h]
  int v221; // [rsp+190h] [rbp+90h]
  int v222; // [rsp+1A0h] [rbp+A0h]
  int v223; // [rsp+1B0h] [rbp+B0h]
  int v224; // [rsp+1C0h] [rbp+C0h]
  int v225; // [rsp+1D0h] [rbp+D0h]
  int v226; // [rsp+1E0h] [rbp+E0h]
  int v227; // [rsp+1F0h] [rbp+F0h]
  int v228; // [rsp+200h] [rbp+100h]
  int v229; // [rsp+230h] [rbp+130h]
  int v230; // [rsp+240h] [rbp+140h]
  int v231; // [rsp+250h] [rbp+150h]
  int v232; // [rsp+260h] [rbp+160h]
  int v233; // [rsp+270h] [rbp+170h]
  int v234; // [rsp+280h] [rbp+180h]
  const unsigned __int16 *v235; // [rsp+298h] [rbp+198h]
  int v236; // [rsp+2A0h] [rbp+1A0h]
  int v237; // [rsp+2B0h] [rbp+1B0h]
  __int64 v238; // [rsp+2B8h] [rbp+1B8h]
  int v239; // [rsp+2C0h] [rbp+1C0h]
  int v240; // [rsp+2D0h] [rbp+1D0h]
  int v241; // [rsp+2E0h] [rbp+1E0h]
  int v242; // [rsp+2F0h] [rbp+1F0h]
  int v243; // [rsp+300h] [rbp+200h]
  int v244; // [rsp+310h] [rbp+210h]
  int v245; // [rsp+320h] [rbp+220h]
  unsigned __int16 *v246; // [rsp+328h] [rbp+228h]
  int v247; // [rsp+330h] [rbp+230h]
  int v248; // [rsp+340h] [rbp+240h]
  int v249; // [rsp+350h] [rbp+250h]
  int v250; // [rsp+360h] [rbp+260h]
  unsigned __int16 *v251; // [rsp+368h] [rbp+268h]
  int v252; // [rsp+370h] [rbp+270h]
  int v253; // [rsp+380h] [rbp+280h]
  int v254; // [rsp+390h] [rbp+290h]
  int v255; // [rsp+3A0h] [rbp+2A0h]
  int v256; // [rsp+3B0h] [rbp+2B0h]
  int v257; // [rsp+3C0h] [rbp+2C0h]
  int v258; // [rsp+3D0h] [rbp+2D0h]
  int v259; // [rsp+3E0h] [rbp+2E0h]
  int v260; // [rsp+3F0h] [rbp+2F0h]
  int v261; // [rsp+400h] [rbp+300h]
  int v262; // [rsp+410h] [rbp+310h]
  int v263; // [rsp+420h] [rbp+320h]
  int v264; // [rsp+430h] [rbp+330h]
  int v265; // [rsp+440h] [rbp+340h]
  int v266; // [rsp+450h] [rbp+350h]
  int v267; // [rsp+460h] [rbp+360h]
  int v268; // [rsp+470h] [rbp+370h]
  int v269; // [rsp+480h] [rbp+380h]
  int v270; // [rsp+490h] [rbp+390h]
  int v271; // [rsp+4A0h] [rbp+3A0h]
  int v272; // [rsp+4B0h] [rbp+3B0h]
  int v273; // [rsp+4C0h] [rbp+3C0h]
  int v274; // [rsp+4D0h] [rbp+3D0h]
  int v275; // [rsp+4E0h] [rbp+3E0h]
  int v276; // [rsp+4F0h] [rbp+3F0h]
  HSTRING_HEADER hstringHeader; // [rsp+500h] [rbp+400h] BYREF
  HSTRING string; // [rsp+518h] [rbp+418h] BYREF
  HSTRING_HEADER Uuid; // [rsp+520h] [rbp+420h] BYREF
  HSTRING v280; // [rsp+538h] [rbp+438h] BYREF
  unsigned __int16 v281[4]; // [rsp+540h] [rbp+440h] BYREF
  __int128 v282; // [rsp+548h] [rbp+448h]
  __int128 v283; // [rsp+558h] [rbp+458h] BYREF
  _OWORD v284[2]; // [rsp+568h] [rbp+468h] BYREF
  unsigned __int16 v285[56]; // [rsp+590h] [rbp+490h] BYREF
  WCHAR sourceString[264]; // [rsp+600h] [rbp+500h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+868h] [rbp+768h]

  v190[0] = 0;
  hMem = 0;
  v205 = 0;
  v202 = 0;
  v201 = 0;
  StringUuid = 0;
  v209 = 0;
  v208 = 0;
  v211 = 0;
  memset_0(v212, 0, 0x408u);
  v5 = -1;
  if ( !a3 )
  {
    v8 = 0;
    v210 = 0;
    goto LABEL_7;
  }
  cchWideChar = MultiByteToWideChar(3u, 0, a3, -1, 0, 0);
  v7 = SysAllocStringLen(0, cchWideChar - 1);
  v8 = v7;
  if ( v7 && MultiByteToWideChar(3u, 0, a3, -1, v7, cchWideChar) != cchWideChar )
  {
    SysFreeString(v8);
LABEL_541:
    ATL::AtlThrowImpl(-2147024882);
  }
  v210 = v8;
  if ( !v8 )
    goto LABEL_541;
LABEL_7:
  hObject = 0;
  v200 = 0;
  v198 = 63;
  McGenEventRegister_EventRegister(
    WP_ENROLLMENT_CLIENT_PROVIDER,
    v4,
    WP_ENROLLMENT_CLIENT_PROVIDER_Context,
    WP_ENROLLMENT_CLIENT_PROVIDER_Context);
  McGenEventRegister_EventRegister(
    MDM_ENTERPRISE_DIAGNOSTICS,
    v9,
    MDM_ENTERPRISE_DIAGNOSTICS_Context,
    MDM_ENTERPRISE_DIAGNOSTICS_Context);
  if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      WP_ENROLLMENT_CLIENT_PROVIDER_Context,
      EnrollmentClientStartedEvent,
      v11,
      1,
      &hstringHeader);
  v12 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
  if ( (*(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor & 4) == 0 )
  {
    bstrString[0] = *(BSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
                               v10,
                               bstrString);
    v12 = (unsigned int)bstrString[0];
  }
  v203 = 0;
  v204 = 3;
  wil::details::ReportUsageToService(&qword_14007E450, 57312060, (v12 >> 10) & 1, (v12 >> 11) & 1, &v203, 1, 3);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007D088);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007D1C0);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007D108);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007D050);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14007D1F8);
  v13 = CoInitializeEx(0, 0) >= 0;
  v203 = v13;
  CommandLineW = GetCommandLineW();
  lpWideCharStr = (LPWSTR)&v211;
  v15 = ProcessCommandLine(&off_14007D300, 66, CommandLineHandler, CommandLineW);
  v190[0] = v15;
  if ( v15 < 0 )
  {
    lpWideCharStr = (LPWSTR)&v211;
    v15 = ProcessCommandLine(&off_14007D300, 66, CommandLineHandler, v8);
    v190[0] = v15;
  }
  if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 1) != 0 )
  {
    LODWORD(pvData) = v15;
    v16 = GetCommandLineW();
    v18 = L"NULL";
    if ( v16 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v16[v19] );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v16 = L"NULL";
      v20 = 10;
    }
    *((_QWORD *)&v282 + 1) = v16;
    *(_QWORD *)&v283 = v20;
    if ( v8 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v8[v21] );
      v18 = v8;
      v22 = 2 * v21 + 2;
    }
    else
    {
      v22 = 10;
    }
    *((_QWORD *)&v283 + 1) = v18;
    *(_QWORD *)&v284[0] = v22;
    *((_QWORD *)&v284[0] + 1) = &pvData;
    *(_QWORD *)&v284[1] = 4;
    McGenEventWrite_EventWriteTransfer(
      WP_ENROLLMENT_CLIENT_PROVIDER_Context,
      EnrollmentClientCommandLineEvent,
      v17,
      4,
      v281);
    v15 = v190[0];
  }
  if ( v15 < 0 )
    goto LABEL_522;
  v190[0] = CopyString(v218, 0xFFFFFFFF, &StringUuid);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  if ( StringUuid )
  {
    *(_OWORD *)&Uuid.Reserved.Reserved1 = 0;
    if ( UuidFromStringW(StringUuid, (UUID *)&Uuid) )
    {
      v23 = StringUuid;
LABEL_30:
      ActiveUserLocalAdmin = UuidFromStringW(v23, (UUID *)&Uuid) | 0x80010000;
LABEL_99:
      v190[0] = ActiveUserLocalAdmin;
      goto LABEL_522;
    }
    *(_OWORD *)bstrString = *(_OWORD *)&Uuid.Reserved.Reserved1;
    v190[0] = GetEnrollmentType(bstrString, &v198);
    if ( (v190[0] & 0x80000000) != 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks>::GetImpl'::`2'::impl) )
      {
        if ( v262 )
          DeclaredConfigurationStore_DeleteScheduledTask(
            L"Refresh schedule created by Declared Configuration to refresh any settings changed on the device",
            StringUuid);
        if ( v276 )
          DeclaredConfigurationStore_DeleteScheduledTask(L"Policy Manager Login Refresh Schedule", StringUuid);
        if ( v229 )
          DeclaredConfigurationStore_DeleteScheduledTask(L"pushrenew", StringUuid);
        if ( v225 )
          DeclaredConfigurationStore_DeleteScheduledTask(L"pushlaunch", StringUuid);
      }
      goto LABEL_522;
    }
  }
  v190[0] = CopyString(v235, 0xFFFFFFFF, &v209);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  v190[0] = CopyString(v217, 0xFFFFFFFF, &v201);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  v190[0] = CopyString(v213, 0xFFFFFFFF, (unsigned __int16 **)&v205);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  v190[0] = CopyString(v215, 0xFFFFFFFF, (unsigned __int16 **)&v202);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  v190[0] = CopyString(v216, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  if ( v259 )
  {
    ActiveUserLocalAdmin = RunAsComServer();
    goto LABEL_99;
  }
  if ( v240 )
  {
    memset_0(sourceString, 0, 0x208u);
    *(_QWORD *)v281 = 0;
    v282 = 0;
    v283 = 0;
    memset(v284, 0, 24);
    v190[0] = DMCSP_DevDetail_GetSwV(260, sourceString);
    if ( (v190[0] & 0x80000000) == 0 )
    {
      string = 0;
      v28 = WindowsCreateStringReference(L"com.microsoft:mdm.upgrade", 0x19u, &hstringHeader, &string);
      if ( v28 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
      }
      else
      {
        do
          ++v5;
        while ( sourceString[v5] );
        if ( v5 > 0xFFFFFFFF )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v29, v30);
          JUMPOUT(0x14001C986LL);
        }
        if ( (int)v5 + 1 < (unsigned int)v5 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v29, v30);
          __debugbreak();
        }
        v31 = WindowsCreateStringReference(sourceString, v5, &Uuid, &v280);
        if ( v31 >= 0 )
        {
          *(_QWORD *)v281 = string;
          *(_QWORD *)&v284[0] = v280;
          DWORD2(v283) = 0;
          *((_QWORD *)&v284[0] + 1) = 0x100000001LL;
          LODWORD(v284[1]) = 3;
          bstrString[0] = (BSTR)0xC00000000LL;
          v190[0] = InitiateSessionAsDeviceAsyncWithAlerts(v202, v32, v281, 0xC00000000LL);
          if ( (v190[0] & 0x80000000) != 0 )
          {
            Logger = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogMigrationAlertSendFail(Logger, v190[0]);
          }
          v280 = 0;
          string = 0;
          goto LABEL_522;
        }
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
      __debugbreak();
    }
    goto LABEL_522;
  }
  if ( v255 )
  {
    if ( v250 )
      v35 = HandleNotification(v202, v251, 0);
    else
      v35 = -2147024809;
    v190[0] = v35;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) == 0 )
      goto LABEL_522;
    v36 = EnterpriseDiagnosticsOsEditionUpgradeEventProcessStatus;
    goto LABEL_64;
  }
  if ( v256 )
  {
    if ( v250 )
      v35 = HandleNotification(v202, v251, 1);
    else
      v35 = -2147024809;
    v190[0] = v35;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) == 0 )
      goto LABEL_522;
    v36 = EnterpriseDiagnosticsWin10SModeEventProcessStatus;
LABEL_64:
    LODWORD(pvData) = v35;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &pvData;
    string = (HSTRING)4;
    McGenEventWrite_EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, v36, v27, 2, &hstringHeader);
    goto LABEL_522;
  }
  if ( v241 )
  {
    Library = LoadLibraryExW(L"ShellChromeAPI.dll", 0, 0x800u);
    v38 = Library;
    bstrString[0] = (BSTR)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "Shell_LaunchSessionGeneric");
      if ( ProcAddress )
      {
        LastError = ((__int64 (__fastcall *)(const wchar_t *, const OLECHAR *, const OLECHAR *, _QWORD))ProcAddress)(
                      L"app://5B04B775-356B-4AA0-AAF8-6491FFEA562A/_default",
                      &SubKey,
                      &SubKey,
                      0);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      v190[0] = LastError;
      FreeLibrary(v38);
    }
    else
    {
      v41 = GetLastError();
      if ( v41 > 0 )
        v41 = (unsigned __int16)v41 | 0x80070000;
      v190[0] = v41;
    }
    goto LABEL_522;
  }
  if ( v242 )
  {
    v190[0] = -2147024891;
    goto LABEL_522;
  }
  if ( v258 )
  {
    ActiveUserLocalAdmin = RaiseToast((unsigned int)v26);
    goto LABEL_99;
  }
  if ( v243 )
  {
    ActiveUserLocalAdmin = ForcedReboot();
    goto LABEL_99;
  }
  if ( v260 )
  {
    if ( !(unsigned __int8)HasActiveLocalAdminAccount() )
    {
      ActiveUserLocalAdmin = MakeActiveUserLocalAdmin();
      goto LABEL_99;
    }
LABEL_522:
    LocalFree(hMem);
    if ( v205 )
    {
      bstrString[0] = 0;
      if ( (int)StringCbLengthW((const unsigned __int16 *)v205, v180, (unsigned __int64 *)bstrString) >= 0 )
      {
        for ( i = bstrString[0]; i; i = (BSTR)((char *)i - 1) )
          *v181++ = 0;
      }
      LocalFree(v205);
    }
    LocalFree(v202);
    LocalFree(v201);
    LocalFree(StringUuid);
    LocalFree(v208);
    if ( hObject )
      CloseHandle(hObject);
    if ( v200 )
    {
      (*(void (__fastcall **)(struct IEnrollEngine *))(*(_QWORD *)v200 + 120LL))(v200);
      (*(void (__fastcall **)(struct IEnrollEngine *))(*(_QWORD *)v200 + 112LL))(v200);
      v200 = 0;
    }
    FreeCommandLineOptions(&off_14007D300, 66, &v211, 1040);
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 1) != 0 )
      McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_CLIENT_PROVIDER_Context, EnrollmentClientStoppedEvent, v190[0]);
    McGenEventUnregister_EventUnregister(MDM_ENTERPRISE_DIAGNOSTICS_Context);
    McGenEventUnregister_EventUnregister(WP_ENROLLMENT_CLIENT_PROVIDER_Context);
    v183 = RegHandle;
    dword_14007D1C0 = 0;
    RegHandle = 0;
    EventUnregister(v183);
    v184 = qword_14007D070;
    dword_14007D050 = 0;
    qword_14007D070 = 0;
    EventUnregister(v184);
    v185 = qword_14007D128;
    dword_14007D108 = 0;
    qword_14007D128 = 0;
    EventUnregister(v185);
    v186 = qword_14007D218;
    dword_14007D1F8 = 0;
    qword_14007D218 = 0;
    EventUnregister(v186);
    v92 = v190[0];
    if ( (v190[0] & 0x80000000) == 0 )
      v92 = 0;
    goto LABEL_535;
  }
  if ( v245 )
  {
    v42 = DeleteAWAAccount(v26, v246);
    v190[0] = v42;
    if ( v42 < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      LODWORD(pvData) = v42;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &pvData;
      string = (HSTRING)4;
      McGenEventWrite_EventWriteTransfer(
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        EnterpriseDiagnosticsUnenrollmentDeleteAccountFailed,
        v43,
        2,
        &hstringHeader);
    }
    bstrString[0] = 0;
    DmGetCurrentUserSid(bstrString);
    DeleteTask(L"Run a Cmd as the User", bstrString[0], v44);
    goto LABEL_341;
  }
  if ( v265 )
  {
    memset_0(sourceString, 0, 0x208u);
    LODWORD(pvData) = 0;
    if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", sourceString, 0x104u) )
      goto LABEL_97;
    v190[0] = DmRaiseToastNotificationAndWait(
                L"DMAppsRes.dll",
                0x65F9u,
                0x65FAu,
                L"ms-settings:workplace-repairtoken",
                sourceString,
                L"MDMSYNCTFA",
                (const struct _GUID *)qword_140063368,
                0x7530u,
                (int *)&pvData);
    v45 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogAADTokenTfaRepairToastCreation(v45, v190[0]);
    if ( v190[0] != 1 )
      goto LABEL_522;
LABEL_521:
    v190[0] = 0;
    goto LABEL_522;
  }
  if ( v266 )
  {
    memset_0(sourceString, 0, 0x208u);
    if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", sourceString, 0x104u) )
    {
      ActiveUserLocalAdmin = DmRemoveToastNotificationByExecutablePath(sourceString);
      goto LABEL_99;
    }
LABEL_97:
    ActiveUserLocalAdmin = GetLastError();
    if ( ActiveUserLocalAdmin > 0 )
      ActiveUserLocalAdmin = (unsigned __int16)ActiveUserLocalAdmin | 0x80070000;
    goto LABEL_99;
  }
  if ( v267 )
  {
    ActiveUserLocalAdmin = UtilsRescheduleAllScepTasks((bool)v26);
    goto LABEL_99;
  }
  if ( v268 )
  {
    bstrString[0] = 0;
    if ( StringUuid )
    {
      hstringHeader.Reserved.Reserved1 = bstrString;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      RetrieveCompanyName(StringUuid, (unsigned __int16 **)&hstringHeader.Reserved.Reserved2[8]);
      if ( hstringHeader.Reserved.Reserved2[16] )
      {
        v46 = *(void **)hstringHeader.Reserved.Reserved1;
        *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        if ( v46 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v46);
        }
      }
    }
    v190[0] = RaiseRemoteFindToast(bstrString[0]);
    if ( dword_14007EAC8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&dword_14007EAC8);
      if ( dword_14007EAC8 == -1 )
      {
        dword_14007DAA0 = 1;
        off_14007DAA8 = &dword_14007D050;
        byte_14007DAB0 = 0;
        GetCorrelationVectorForEnrollmentSession(L"OmaDmSession", qword_14007DB38);
        Microsoft::Windows::TelemetryLogger::SetCorrelationVector(
          (Microsoft::Windows::TelemetryLogger *)&dword_14007DAA0,
          qword_14007DB38);
        atexit(CRemoteFindLogger::GetLogger_::_2_::_dynamic_atexit_destructor_for__m_pRemoteFindLogger__);
        Init_thread_footer(&dword_14007EAC8);
      }
    }
    CRemoteFindLogger::LogToastLaunch((CRemoteFindLogger *)&dword_14007DAA0, v190[0]);
    v48 = bstrString[0];
    bstrString[0] = 0;
LABEL_195:
    if ( v48 )
    {
      v85 = GetProcessHeap();
      HeapFree(v85, 0, v48);
    }
    goto LABEL_522;
  }
  if ( v272 )
  {
    v195 = 0;
    v194 = 0;
    bstrString[0] = 0;
    *(_OWORD *)&Uuid.Reserved.Reserved1 = 0;
    pcbData = 0;
    LODWORD(pvData) = 3;
    DmDeleteTask(
      L"\\Microsoft\\Windows\\EnterpriseMgmt",
      0,
      L"Schedule created by enrollment client to reattest client certificate");
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v50 = *(int (__fastcall **)(__int64, __int64, BSTR **))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    v51 = v195;
    if ( v195 )
    {
      v195 = 0;
      (*((void (__fastcall **)(BSTR *))*v51 + 2))(v51);
    }
    if ( v50(DatabaseManagerInstance, 8289, &v195) >= 0 )
    {
      v52 = v195;
      v53 = (unsigned int (__fastcall *)(BSTR *, __int64 *))*((_QWORD *)*v195 + 3);
      v54 = v194;
      if ( v194 )
      {
        v194 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      if ( !v53(v52, &v194) )
      {
        v55 = v194;
        v56 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v194 + 32LL);
        v57 = bstrString[0];
        if ( bstrString[0] )
        {
          v58 = GetLastError();
          SysFreeString(v57);
          SetLastError(v58);
        }
        bstrString[0] = 0;
        if ( v56(v55, bstrString) >= 0 )
        {
          if ( UuidFromStringW(bstrString[0], (UUID *)&Uuid) )
          {
            UuidFromStringW(bstrString[0], (UUID *)&Uuid);
          }
          else
          {
            *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
            if ( (int)GetIsRecoveryAllowed(&hstringHeader, &pcbData) >= 0 )
            {
              if ( pcbData )
              {
                *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
                if ( (int)GetEnrollmentAuthPolicy(&hstringHeader, &pvData) >= 0 && (_DWORD)pvData == 1 )
                {
                  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
                  v190[0] = SetEnrollState(&hstringHeader, 6);
                  if ( (v190[0] & 0x80000000) == 0 )
                  {
                    if ( bstrString[0] )
                      SysFreeString(bstrString[0]);
                    v61 = v194;
                    if ( v194 )
                    {
                      v194 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                    }
                  }
                  else
                  {
                    if ( bstrString[0] )
                      SysFreeString(bstrString[0]);
                    v60 = v194;
                    if ( v194 )
                    {
                      v194 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                    }
                  }
                  goto LABEL_443;
                }
              }
            }
          }
        }
      }
    }
    v190[0] = -2147467259;
    if ( bstrString[0] )
      SysFreeString(bstrString[0]);
    v59 = v194;
    if ( v194 )
    {
      v194 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
LABEL_443:
    v163 = v195;
    if ( v195 )
    {
      v195 = 0;
      (*((void (__fastcall **)(BSTR *))*v163 + 2))(v163);
    }
    goto LABEL_522;
  }
  if ( v273 )
  {
    v62 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
    if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
    {
      bstrString[0] = *(BSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                                 v26,
                                 bstrString);
      v62 = (unsigned int)bstrString[0];
    }
    LODWORD(pvData) = 0;
    WORD2(pvData) = 3;
    wil::details::ReportUsageToService(&qword_14007E368, 43467477, (v62 >> 10) & 1, (v62 >> 11) & 1, &pvData, 1, 3);
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, -2) )
    {
      v64 = GetLastError();
      if ( v64 > 0 )
        v64 = (unsigned __int16)v64 | 0x80070000;
      v190[0] = v64;
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
      {
        LODWORD(pvData) = v64;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &pvData;
        string = (HSTRING)4;
        McGenEventWrite_EventWriteTransfer(
          MDM_ENTERPRISE_DIAGNOSTICS_Context,
          ConfigRefreshSetThreadPriorityLowestFailure,
          v65,
          2,
          &hstringHeader);
      }
    }
    if ( StringUuid )
    {
      v66 = CConfigRefreshLogger::GetLogger();
      CConfigRefreshLogger::LogConfigRefreshPausePeriodDeleteStart(v66);
      v190[0] = DMClient::DeleteConfigRefreshValue((DMClient *)StringUuid, v67, v68);
      v69 = CConfigRefreshLogger::GetLogger();
      CConfigRefreshLogger::LogConfigRefreshPausePeriodDeleteEnd(v69, v190[0]);
    }
    v70 = CConfigRefreshLogger::GetLogger();
    CConfigRefreshLogger::LogConfigRefreshStart(v70);
    bstrString[0] = 0;
    v190[0] = AcquireConfigRefreshMutex((void **)bstrString, L"ConfigRefresh");
    if ( (v190[0] & 0x80000000) == 0 )
    {
      if ( IsConfigRefreshSemaphoreSignaled(L"ConfigRefresh") )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x400) != 0 )
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            ConfigRefreshSkipped,
            v73,
            1,
            &hstringHeader);
        v72 = bstrString[0];
        if ( !bstrString[0] )
          goto LABEL_522;
      }
      else
      {
        v190[0] = EnterprisePolicyManagerStore_RefreshAll();
        if ( (v190[0] & 0x80000000) == 0 )
        {
          if ( bstrString[0] )
            ReleaseConfigRefreshMutex(bstrString[0]);
          v75 = CConfigRefreshLogger::GetLogger();
          CConfigRefreshLogger::LogConfigRefreshEnd(v75, v190[0]);
          goto LABEL_522;
        }
        v74 = CConfigRefreshLogger::GetLogger();
        CConfigRefreshLogger::LogConfigRefreshEnd(v74, v190[0]);
        v72 = bstrString[0];
        if ( !bstrString[0] )
          goto LABEL_522;
      }
    }
    else
    {
      v71 = CConfigRefreshLogger::GetLogger();
      CConfigRefreshLogger::LogConfigRefreshEnd(v71, v190[0]);
      v72 = bstrString[0];
      if ( !bstrString[0] )
        goto LABEL_522;
    }
LABEL_406:
    ReleaseConfigRefreshMutex(v72);
    goto LABEL_522;
  }
  if ( v274 )
  {
    ActiveUserLocalAdmin = CleanupStaleEnrollments();
    goto LABEL_99;
  }
  if ( !(_DWORD)v211 )
    goto LABEL_522;
  if ( v234 )
  {
    ActiveUserLocalAdmin = PopupUnenrollmentUI(v209);
    goto LABEL_99;
  }
  if ( v254 )
  {
    v76 = RegisterDeviceWithManagementUsingAADCredentials(0);
    v190[0] = v76;
    if ( v76 < 0 && (unsigned int)(v76 + 2145844848) > 1 && v76 != -2145844845 && v76 != -2145910774 )
      goto LABEL_522;
    v77 = L"Schedule created by enrollment client for automatically enrolling in MDM from AAD";
    goto LABEL_187;
  }
  if ( v264 )
  {
    v78 = RegisterDeviceWithManagementUsingAADDeviceCredentials();
    v190[0] = v78;
    if ( v78 < 0 && (unsigned int)(v78 + 2145844848) > 1 && v78 != -2145844845 && v78 != -2145910774 )
      goto LABEL_522;
    v77 = L"Schedule created by enrollment client for automatically enrolling in MDM from AAD using AAD device credential";
LABEL_187:
    DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", 0, v77);
    goto LABEL_522;
  }
  if ( v219 )
  {
    *(_OWORD *)&Uuid.Reserved.Reserved1 = 0;
    bstrString[0] = 0;
    if ( UuidFromStringW(v201, (UUID *)&Uuid) >= 0 )
    {
      v80 = bstrString[0];
      if ( bstrString[0] )
      {
        v81 = GetLastError();
        v82 = GetProcessHeap();
        HeapFree(v82, 0, v80);
        SetLastError(v81);
      }
      bstrString[0] = 0;
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
      if ( (int)GetEnrollmentLinkedEnrollmentId(&hstringHeader, bstrString) >= 0 )
        UnEnroll(bstrString[0], v79);
    }
    v190[0] = UnEnroll(v201, v79);
    CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogUnenrollSource(v83, v190[0], v84);
    v48 = bstrString[0];
    goto LABEL_195;
  }
  if ( v220 )
  {
    v190[0] = EnrollEngineInitialize(1, 0, &v200);
    if ( (v190[0] & 0x80000000) != 0 || !v201 )
      goto LABEL_522;
    *(_OWORD *)&Uuid.Reserved.Reserved1 = 0;
    if ( UuidFromStringW(v201, (UUID *)&Uuid) )
    {
      v23 = v201;
      goto LABEL_30;
    }
    v190[0] = 0;
    bstrString[0] = 0;
    v86 = (*(__int64 (__fastcall **)(struct IEnrollEngine *, HSTRING_HEADER *, _QWORD, BSTR *))(*(_QWORD *)v200 + 136LL))(
            v200,
            &Uuid,
            0,
            bstrString);
LABEL_203:
    v190[0] = v86;
    if ( v86 >= 0 )
    {
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
      v190[0] = WaitForUnenrollment(v200, bstrString[0], (struct _GUID *)&hstringHeader);
      bstrString[0] = 0;
    }
    goto LABEL_522;
  }
  if ( v252 )
  {
    ActiveUserLocalAdmin = AlertServerForProvisioning(StringUuid);
    goto LABEL_99;
  }
  if ( v262 )
  {
    v87 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
    if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
    {
      bstrString[0] = *(BSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                                 v26,
                                 bstrString);
      v87 = (unsigned int)bstrString[0];
    }
    LODWORD(pvData) = 0;
    WORD2(pvData) = 3;
    wil::details::ReportUsageToService(&qword_14007E368, 43467477, (v87 >> 10) & 1, (v87 >> 11) & 1, &pvData, 1, 3);
    bstrString[0] = 0;
    v190[0] = AcquireConfigRefreshMutex((void **)bstrString, L"DeclaredConfigurationRefresh");
    if ( (v190[0] & 0x80000000) == 0 )
    {
      if ( IsConfigRefreshSemaphoreSignaled(L"DeclaredConfigurationRefresh") )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x400) != 0 )
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            DeclaredConfigurationRefreshSkipped,
            v88,
            1,
            &hstringHeader);
        v72 = bstrString[0];
        if ( !bstrString[0] )
          goto LABEL_522;
      }
      else
      {
        if ( StringUuid )
          DMOrchestratorRefreshPerEnrollment();
        else
          DMOrchestratorRefresh();
        v72 = bstrString[0];
        if ( !bstrString[0] )
          goto LABEL_522;
      }
    }
    else
    {
      v72 = bstrString[0];
      if ( !bstrString[0] )
        goto LABEL_522;
    }
    goto LABEL_406;
  }
  if ( v261 || v275 )
    goto LABEL_522;
  if ( v263 )
  {
    JobExecution::DownloadCDN_HandleWatchDog(0);
    goto LABEL_522;
  }
  if ( v269 )
  {
    *((_QWORD *)&v282 + 1) = 0;
    memset(v284, 0, 24);
    *(_DWORD *)v281 = 64;
    *(_DWORD *)&v281[2] = 1226;
    *(_QWORD *)&v282 = L"com.microsoft.mdm.wscstartup";
    *(_QWORD *)&v283 = L"Sync Session triggered by Device Status CSP update";
    *((_QWORD *)&v283 + 1) = 0x200000001LL;
    LODWORD(lpWideCharStr) = 1;
    v89 = OmaDmInitiateSessionAsDevice(v202, 1, 2, v281, lpWideCharStr, 0, 53);
    v190[0] = v89;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    {
      LODWORD(pvData) = v89;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &pvData;
      string = (HSTRING)4;
      McGenEventWrite_EventWriteTransfer(
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        EnterpriseDiagnosticsWscStartupAlertEventProcessStatus,
        v90,
        2,
        &hstringHeader);
      v89 = v190[0];
    }
    if ( v89 >= 0 )
      DmDisableTask(
        L"\\Microsoft\\Windows\\EnterpriseMgmt",
        (const unsigned __int16 *)v202,
        L"Wsc Startup event listener created by enrollment client");
    goto LABEL_522;
  }
  if ( v270 )
  {
    memset_0(v281, 0, 0x4Eu);
    DmDeleteTask(
      L"\\Microsoft\\Windows\\EnterpriseMgmt",
      StringUuid,
      L"Schedule created by dm client to unenroll Mmpc from dual enrollment");
    LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"EnrollStatus", 1u);
    v92 = LinkedEnrollmentStringRegistry;
    v190[0] = LinkedEnrollmentStringRegistry;
    if ( LinkedEnrollmentStringRegistry >= 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl'::`2'::impl)
        && v198 == 13 )
      {
        v96 = RegisterDeviceDualEnrollMmpcUsingCertificateCredentials(StringUuid, v94, v281);
      }
      else
      {
        v98 = *(_DWORD *)Feature_DeclaredConfiguration_Allow_Custom_Endpoint_3rd_Party__descriptor;
        if ( (*(_DWORD *)Feature_DeclaredConfiguration_Allow_Custom_Endpoint_3rd_Party__descriptor & 4) == 0 )
        {
          bstrString[0] = *(BSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Allow_Custom_Endpoint_3rd_Party>::GetCachedFeatureEnabledState(
                                     v95,
                                     bstrString);
          v98 = (unsigned int)bstrString[0];
        }
        LODWORD(pvData) = 0;
        WORD2(pvData) = 3;
        wil::details::ReportUsageToService(&qword_14007E518, 44700043, (v98 >> 10) & 1, (v98 >> 11) & 1, &pvData, 1, 3);
        v96 = RegisterDeviceDualEnrollMmpcUsingAADDeviceCredentials(StringUuid, v99, v281);
      }
      v190[0] = v96;
      if ( (int)(v96 + 0x80000000) < 0 || v96 == -2145910774 )
      {
        DmDeleteTask(
          L"\\Microsoft\\Windows\\EnterpriseMgmt",
          StringUuid,
          L"Schedule created by dm client for dual enrollment to Mmpc");
        v96 = v190[0];
      }
      if ( v96 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          LODWORD(pvData) = v96;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &pvData;
          string = (HSTRING)4;
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsDualModeEnrollmentFailed,
            v97,
            2,
            &hstringHeader);
        }
        LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"EnrollStatus", 4u);
        v92 = LinkedEnrollmentStringRegistry;
        if ( LinkedEnrollmentStringRegistry >= 0 )
        {
          LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"LastError", v190[0]);
          v92 = LinkedEnrollmentStringRegistry;
          if ( LinkedEnrollmentStringRegistry >= 0 )
            goto LABEL_522;
          v93 = 2343;
        }
        else
        {
          v93 = 2342;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsDualModeEnrollmentSucceeded,
            v97,
            1,
            &hstringHeader);
        LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"EnrollStatus", 3u);
        v92 = LinkedEnrollmentStringRegistry;
        if ( LinkedEnrollmentStringRegistry >= 0 )
        {
          LinkedEnrollmentStringRegistry = SetLinkedEnrollmentStringRegistry(StringUuid, v100, v281);
          v92 = LinkedEnrollmentStringRegistry;
          if ( LinkedEnrollmentStringRegistry >= 0 )
          {
            LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"LastError", v190[0]);
            v92 = LinkedEnrollmentStringRegistry;
            if ( LinkedEnrollmentStringRegistry >= 0 )
              goto LABEL_522;
            v93 = 2337;
          }
          else
          {
            v93 = 2336;
          }
        }
        else
        {
          v93 = 2335;
        }
      }
    }
    else
    {
      v93 = 2294;
    }
LABEL_235:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v93,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)LinkedEnrollmentStringRegistry,
      (int)lpWideCharStr);
    goto LABEL_535;
  }
  if ( v271 )
  {
    DmDeleteTask(
      L"\\Microsoft\\Windows\\EnterpriseMgmt",
      StringUuid,
      L"Schedule created by dm client for dual enrollment to Mmpc");
    SetLinkedEnrollmentLongValueRegistry(StringUuid, L"EnrollStatus", 1u);
    memset_0(v285, 0, 0x64u);
    LinkedEnrollmentStringRegistry = GetLinkedEnrollmentStringRegistry(StringUuid, v101, v102, v285);
    v92 = LinkedEnrollmentStringRegistry;
    v190[0] = LinkedEnrollmentStringRegistry;
    if ( LinkedEnrollmentStringRegistry >= 0 )
    {
      v104 = *(_DWORD *)Feature_MMPC_Desktop__descriptor;
      if ( (*(_DWORD *)Feature_MMPC_Desktop__descriptor & 4) == 0 )
      {
        bstrString[0] = *(BSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_Desktop>::GetCachedFeatureEnabledState(
                                   v103,
                                   bstrString);
        v104 = (unsigned int)bstrString[0];
      }
      LODWORD(pvData) = 0;
      WORD2(pvData) = 3;
      wil::details::ReportUsageToService(&qword_14007EAF8, 33231644, (v104 >> 10) & 1, (v104 >> 11) & 1, &pvData, 1, 3);
      v105 = UnEnrollMmpcFromDualEnrollment(v285);
      v190[0] = v105;
      if ( v105 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          LODWORD(pvData) = v105;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &pvData;
          string = (HSTRING)4;
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsDualModeUnenrollmentFailed,
            v106,
            2,
            &hstringHeader);
        }
        LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"EnrollStatus", 8u);
        v92 = LinkedEnrollmentStringRegistry;
        if ( LinkedEnrollmentStringRegistry >= 0 )
        {
          LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"LastError", v190[0]);
          v92 = LinkedEnrollmentStringRegistry;
          if ( LinkedEnrollmentStringRegistry >= 0 )
            goto LABEL_522;
          v93 = 2379;
        }
        else
        {
          v93 = 2378;
        }
      }
      else
      {
        DmDeleteTask(
          L"\\Microsoft\\Windows\\EnterpriseMgmt",
          StringUuid,
          L"Schedule created by dm client to unenroll Mmpc from dual enrollment");
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsDualModeUnenrollmentSucceeded,
            v107,
            1,
            &hstringHeader);
        LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"EnrollStatus", 7u);
        v92 = LinkedEnrollmentStringRegistry;
        if ( LinkedEnrollmentStringRegistry >= 0 )
        {
          LinkedEnrollmentStringRegistry = SetLinkedEnrollmentStringRegistry(StringUuid, v108, &SubKey);
          v92 = LinkedEnrollmentStringRegistry;
          if ( LinkedEnrollmentStringRegistry >= 0 )
          {
            LinkedEnrollmentStringRegistry = SetLinkedEnrollmentLongValueRegistry(StringUuid, L"LastError", v190[0]);
            v92 = LinkedEnrollmentStringRegistry;
            if ( LinkedEnrollmentStringRegistry >= 0 )
              goto LABEL_522;
            v93 = 2373;
          }
          else
          {
            v93 = 2372;
          }
        }
        else
        {
          v93 = 2371;
        }
      }
    }
    else
    {
      v93 = 2360;
    }
    goto LABEL_235;
  }
  v109 = StringUuid;
  if ( StringUuid )
  {
    if ( v221 )
    {
      v110 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
      if ( (*(_DWORD *)Feature_ConfigRefresh__descriptor & 4) == 0 )
      {
        bstrString[0] = *(BSTR *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
                                   StringUuid,
                                   bstrString);
        v110 = (unsigned int)bstrString[0];
      }
      LODWORD(pvData) = 0;
      WORD2(pvData) = 3;
      wil::details::ReportUsageToService(&qword_14007E368, 43467477, (v110 >> 10) & 1, (v110 >> 11) & 1, &pvData, 1, 3);
      LODWORD(pvData) = 0;
      pcbData = 4;
      if ( !StringUuid )
        goto LABEL_297;
      bstrString[0] = 0;
      ConfigRefreshKey = DMClient::GetConfigRefreshKey(
                           (DMClient *)StringUuid,
                           (const unsigned __int16 *)bstrString,
                           0,
                           v111);
      if ( ConfigRefreshKey >= 0 )
      {
        v114 = (HKEY)bstrString[0];
        ValueW = RegGetValueW((HKEY)bstrString[0], 0, L"Enabled", 0x10u, 0, &pvData, &pcbData);
        v116 = ValueW < 0;
        if ( !ValueW )
          goto LABEL_294;
        if ( ValueW > 0 )
        {
          ValueW = (unsigned __int16)ValueW | 0x80070000;
          v116 = ValueW < 0;
        }
        if ( !v116 )
        {
LABEL_294:
          v117 = (_DWORD)pvData == 1;
          if ( v114 )
            RegCloseKey(v114);
          if ( v117 )
            goto LABEL_298;
          goto LABEL_297;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15D1,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
          (const char *)(unsigned int)ValueW,
          (int)lpWideCharStra);
        if ( v114 )
        {
          v113 = v114;
          goto LABEL_287;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15C3,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
          (const char *)(unsigned int)ConfigRefreshKey,
          (int)lpWideCharStra);
        v113 = (HKEY)bstrString[0];
        if ( bstrString[0] )
LABEL_287:
          RegCloseKey(v113);
      }
LABEL_297:
      EnterprisePolicyManagerStore_RefreshAll();
LABEL_298:
      LODWORD(lpWideCharStra) = 0;
      v118 = OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, 0, lpWideCharStra, 0, 3);
LABEL_455:
      v190[0] = v118;
      goto LABEL_456;
    }
    if ( v222 )
    {
      LOBYTE(v25) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::ReportUsage(
        &`wil::Feature<__WilFeatureTraits_Feature_ConfigRefresh>::GetImpl'::`2'::impl,
        v25);
      LODWORD(pvData) = 0;
      DMClient::GetIsRefreshEnabled((DMClient *)StringUuid, (const unsigned __int16 *)&pvData, v120);
      if ( !(_DWORD)pvData )
        EnterprisePolicyManagerStore_RefreshAll();
      v118 = OmaDmInitiateSessionAsUser(0, StringUuid, 1, 2, 0, 0, 0, 51);
      goto LABEL_455;
    }
    if ( v223 )
    {
      v118 = OmaDmInitiateSessionAsUser(0, StringUuid, 1, 2, 0, 0, 0, 52);
      goto LABEL_455;
    }
    if ( v224 )
    {
      v190[0] = AlertServerForPFW(StringUuid);
      v121 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogPFWEvent(v121, v190[0]);
      goto LABEL_456;
    }
    if ( v225 )
    {
      LOBYTE(v25) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WNSPushNotificationPayload>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_WNSPushNotificationPayload>::GetImpl'::`2'::impl,
        v25);
      bstrString[0] = 0;
      memset_0(v281, 0, 0x40u);
      hstringHeader.Reserved.Reserved1 = bstrString;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v190[0] = GetPushAlertInfo(StringUuid, v198, &hstringHeader.Reserved.Reserved2[8], v281);
      if ( hstringHeader.Reserved.Reserved2[16] )
      {
        v122 = *(void **)hstringHeader.Reserved.Reserved1;
        *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        if ( v122 )
        {
          v123 = GetProcessHeap();
          HeapFree(v123, 0, v122);
        }
      }
      v124 = L"notificationIdNotRetrieved";
      if ( bstrString[0] )
        v124 = bstrString[0];
      v195 = (BSTR *)v124;
      MDMPushProvider::GetPushAlertInfo<unsigned short * &,long &>(&v195, v190);
      if ( (v190[0] & 0x80000000) != 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
          McTemplateU0zd_EventWriteTransfer(v125, GetPushAlertInfoFailure, v124);
        LODWORD(lpWideCharStr) = 0;
        v126 = OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, 0, lpWideCharStr, 0, 7);
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(v125, GetPushAlertInfoSuccess, v124);
        LODWORD(lpWideCharStr) = 1;
        v126 = OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, v281, lpWideCharStr, 0, 7);
      }
LABEL_333:
      v131 = bstrString[0];
      v132 = bstrString[0] == 0;
      bstrString[0] = 0;
      v190[0] = v126;
      if ( !v132 )
      {
        v133 = GetProcessHeap();
        HeapFree(v133, 0, v131);
      }
      MDMPushProvider::PushInitiatedSession<unsigned short * &,long &>(&StringUuid, v190);
      goto LABEL_456;
    }
    if ( v226 )
    {
      LOBYTE(v25) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WNSPushNotificationPayload>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_WNSPushNotificationPayload>::GetImpl'::`2'::impl,
        v25);
      bstrString[0] = 0;
      memset_0(v281, 0, 0x40u);
      hstringHeader.Reserved.Reserved1 = bstrString;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v190[0] = GetPushAlertInfo(StringUuid, v198, &hstringHeader.Reserved.Reserved2[8], v281);
      if ( hstringHeader.Reserved.Reserved2[16] )
      {
        v127 = *(void **)hstringHeader.Reserved.Reserved1;
        *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        if ( v127 )
        {
          v128 = GetProcessHeap();
          HeapFree(v128, 0, v127);
        }
      }
      v129 = L"notificationIdNotRetrieved";
      if ( bstrString[0] )
        v129 = bstrString[0];
      v195 = (BSTR *)v129;
      MDMPushProvider::GetPushAlertInfo<unsigned short * &,long &>(&v195, v190);
      if ( (v190[0] & 0x80000000) != 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
          McTemplateU0zd_EventWriteTransfer(v130, GetPushAlertInfoFailure, v129);
        v126 = OmaDmInitiateSessionAsUser(0, StringUuid, 1, 2, 0, 0, 0, 7);
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(v130, GetPushAlertInfoSuccess, v129);
        v126 = OmaDmInitiateSessionAsUser(0, StringUuid, 1, 2, v281, 1, 0, 7);
      }
      goto LABEL_333;
    }
    if ( v227 )
    {
      LODWORD(lpWideCharStr) = 0;
      v190[0] = OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, 0, lpWideCharStr, 0, 8);
      v134 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogBitsEvent(v134, v190[0]);
      goto LABEL_456;
    }
    if ( v228 )
    {
      bstrString[0] = 0;
      v190[0] = DmGetCurrentUserSid(bstrString);
      if ( (v190[0] & 0x80000000) != 0 )
      {
        v135 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogBitsEvent(v135, v190[0]);
LABEL_341:
        v136 = bstrString[0];
        bstrString[0] = 0;
        LocalFree(v136);
        goto LABEL_522;
      }
      v190[0] = OmaDmInitiateSessionAsUser(bstrString[0], StringUuid, 1, 2, 0, 0, 0, 8);
      v137 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogBitsEvent(v137, v190[0]);
      v138 = bstrString[0];
      bstrString[0] = 0;
      LocalFree(v138);
      goto LABEL_456;
    }
    if ( v236 )
    {
      if ( v237 )
      {
        hstringHeader.Reserved.Reserved1 = &StringUuid;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v190;
        hstringHeader.Reserved.Reserved2[16] = 1;
        LOBYTE(v25) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::ReportUsage(
          &`wil::Feature<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetImpl'::`2'::impl,
          v25);
        if ( !v238 )
        {
          v139 = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogRetryAccountIdEvent(v139, StringUuid, v190[0]);
          goto LABEL_522;
        }
        v190[0] = OmaDmInitiateSessionWithSessionID(StringUuid, 1, v238, 2, 0, 0, 0, 57);
        v140 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogRetryAccountIdEvent(v140, StringUuid, v190[0]);
      }
      else
      {
        v190[0] = OmaDmInitiateSessionWithSessionID(
                    StringUuid,
                    1,
                    L"{973CC073-B7F4-4B3B-ABF8-74DF3FCAE76F}",
                    2,
                    0,
                    0,
                    0,
                    25);
        v141 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogRetryEvent(v141, v190[0]);
      }
      goto LABEL_456;
    }
    if ( v239 )
    {
      v190[0] = OmaDmInitiateSessionWithSessionID(
                  StringUuid,
                  1,
                  L"{862BBF62-A6E3-3A2A-9CE7-63CE2EB9D65E}",
                  2,
                  0,
                  0,
                  0,
                  30);
      v142 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDequeueEvent(v142, StringUuid, v190[0]);
      goto LABEL_456;
    }
    if ( v229 )
    {
      v190[0] = PerformPushRenew(StringUuid, v198);
      if ( (v190[0] & 0x80000000) != 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x20) != 0 )
          McTemplateU0d_EventWriteTransfer(v72, EnterpriseDiagnosticsMDMPushRenewFail, v190[0]);
        goto LABEL_456;
      }
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
      {
        v144 = EnterpriseDiagnosticsMDMPushRenewSuccess;
LABEL_355:
        McGenEventWrite_EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, v144, v143, 1, &hstringHeader);
        goto LABEL_456;
      }
      goto LABEL_456;
    }
    if ( v244 )
    {
      v190[0] = PerformPushUpgrade(StringUuid, v198);
      if ( (v190[0] & 0x80000000) != 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x20) != 0 )
          McTemplateU0d_EventWriteTransfer(v72, EnterpriseDiagnosticsMDMPushUpgradeFail, v190[0]);
        LODWORD(hstringHeader.Reserved.Reserved1) = 0;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        *(_DWORD *)&hstringHeader.Reserved.Reserved2[20] = 0;
        v190[0] = CMDMPushConfiguration::Initialize(&hstringHeader, StringUuid, v198);
        LODWORD(pvData) = 0;
        if ( (v190[0] & 0x80000000) == 0 )
        {
          v190[0] = CMDMPushConfiguration::GetRetryCount(
                      (CMDMPushConfiguration *)&hstringHeader,
                      (unsigned int *)&pvData);
          if ( (v190[0] & 0x80000000) == 0 )
          {
            v145 = (unsigned int)pvData;
            v190[0] = CMDMPushConfiguration::SetRetryCount((CMDMPushConfiguration *)&hstringHeader, (int)pvData + 1);
            if ( (v190[0] & 0x80000000) == 0 && v145 < 3 )
              v190[0] = CMDMPushConfiguration::CreatePushUpgradeSchedule((CMDMPushConfiguration *)&hstringHeader, 0x1Eu);
          }
        }
        CMDMPushConfiguration::~CMDMPushConfiguration((CMDMPushConfiguration *)&hstringHeader);
        goto LABEL_456;
      }
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
      {
        v144 = EnterpriseDiagnosticsMDMPushUpgradeSuccess;
        goto LABEL_355;
      }
LABEL_456:
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v72, v119, StringUuid, v190[0]);
      goto LABEL_522;
    }
    if ( v230 )
    {
      bstrString[0] = (BSTR)0xA00000000LL;
      LOBYTE(v27) = 1;
      v190[0] = InitiateSessionAsync(StringUuid, 0xA00000000LL, v27);
      if ( (v190[0] & 0x80000000) != 0 )
        goto LABEL_456;
      v146 = DisableAllPollOnLoginTask(StringUuid);
      goto LABEL_430;
    }
    if ( v231 )
    {
      HIDWORD(bstrString[0]) = 10;
      LOBYTE(v27) = 1;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
        && v232 )
      {
        v148 = CConfigRefreshLogger::GetLogger();
        CConfigRefreshLogger::LogConfigRefreshJustPerUserStart(v148);
        bstrString[0] = 0;
        v149 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(bstrString);
        v190[0] = AcquireConfigRefreshMutex(v149, L"ConfigRefresh");
        if ( (v190[0] & 0x80000000) != 0 )
        {
          v150 = CConfigRefreshLogger::GetLogger();
          CConfigRefreshLogger::LogConfigRefreshJustPerUserEnd(v150, v190[0]);
          v72 = bstrString[0];
          if ( !bstrString[0] )
            goto LABEL_522;
          goto LABEL_406;
        }
        if ( IsConfigRefreshSemaphoreSignaled(L"ConfigRefresh") )
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x400) != 0 )
            McGenEventWrite_EventWriteTransfer(
              MDM_ENTERPRISE_DIAGNOSTICS_Context,
              ConfigRefreshJustPerUserSkipped,
              v151,
              1,
              &hstringHeader);
          v72 = bstrString[0];
          if ( !bstrString[0] )
            goto LABEL_522;
          goto LABEL_406;
        }
        v190[0] = EnterprisePolicyManagerStore_RefreshPerUserPoliciesForMDMEnrollments();
        if ( (v190[0] & 0x80000000) != 0 )
        {
          v152 = CConfigRefreshLogger::GetLogger();
          CConfigRefreshLogger::LogConfigRefreshJustPerUserEnd(v152, v190[0]);
          v72 = bstrString[0];
          if ( !bstrString[0] )
            goto LABEL_522;
          goto LABEL_406;
        }
        if ( bstrString[0] )
          ReleaseConfigRefreshMutex(bstrString[0]);
        v153 = CConfigRefreshLogger::GetLogger();
        CConfigRefreshLogger::LogConfigRefreshJustPerUserEnd(v153, v190[0]);
        goto LABEL_456;
      }
      LOBYTE(v147) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshBetterInAvd>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RefreshBetterInAvd>::GetImpl'::`2'::impl,
        v147);
      if ( v276 )
      {
        bstrString[0] = 0;
        for ( j = 0; ; ++j )
        {
          v156 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(bstrString);
          refreshed = AcquireConfigRefreshMutex(v156, L"ConfigRefresh");
          v190[0] = refreshed;
          if ( ((refreshed + 0x80000000) & 0x80000000) == 0 && refreshed != -2147023436 )
          {
            v72 = bstrString[0];
            if ( !bstrString[0] )
              goto LABEL_522;
            goto LABEL_406;
          }
          if ( j > 0x1E )
          {
            v72 = bstrString[0];
            if ( !bstrString[0] )
              goto LABEL_522;
            goto LABEL_406;
          }
          if ( !refreshed )
            break;
        }
        EnterprisePolicyManagerStore_RefreshAll();
        v72 = bstrString[0];
        if ( (v190[0] & 0x80000000) == 0 )
        {
          if ( bstrString[0] )
            ReleaseConfigRefreshMutex(bstrString[0]);
          goto LABEL_456;
        }
        if ( !bstrString[0] )
          goto LABEL_522;
        goto LABEL_406;
      }
      if ( v233 )
      {
        bstrString[0] = (BSTR)0xB00000000LL;
        LOBYTE(v154) = 1;
        v190[0] = InitiateSessionAsync(StringUuid, 0xB00000000LL, v154);
        v158 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogContainerSessionAfterUserLogonEvent(v158, v190[0]);
        if ( (v190[0] & 0x80000000) != 0 )
          goto LABEL_456;
        v146 = DmDeleteTask(
                 L"\\Microsoft\\Windows\\EnterpriseMgmt",
                 StringUuid,
                 L"Login Schedule created by OmaDm client when container is not availbale");
        goto LABEL_430;
      }
      if ( v247 )
      {
        v159 = 0;
        if ( v250 )
          v159 = v251;
        if ( v249 )
        {
          v146 = DynamoUserLoginHandler(StringUuid);
        }
        else if ( v248 )
        {
          v146 = DynamoRebootHandler(StringUuid, v159);
        }
        else
        {
          if ( v253 )
          {
            bstrString[0] = 0;
            bstrString[1] = 0;
            Uuid.Reserved.Reserved1 = bstrString;
            Uuid.Reserved.Reserved2[8] = 1;
            v195 = bstrString;
            v196 = 0;
            v197 = 1;
            AlertData = DynamoGetAlertData(StringUuid, v159, (struct OMADMALERTINFO **)bstrString, &v196);
            v190[0] = AlertData;
            if ( v197 )
            {
              v195[1] = (BSTR)v196;
              AlertData = v190[0];
            }
            if ( AlertData >= 0 )
            {
              if ( bstrString[1] > (BSTR)0xFFFFFFFFLL )
              {
                v190[0] = -2147024362;
              }
              else
              {
                v190[0] = 0;
                if ( !LODWORD(bstrString[1])
                  || (LODWORD(lpWideCharStr) = bstrString[1],
                      v190[0] = OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, bstrString[0], lpWideCharStr, 0, 17),
                      (v190[0] & 0x80000000) == 0) )
                {
                  wil::details::ScopeExitFn__lambda_8b4ff283cf0951643c10e64da2111026___::_ScopeExitFn__lambda_8b4ff283cf0951643c10e64da2111026___(&Uuid);
                  v72 = bstrString[0];
                  if ( bstrString[0] )
                  {
                    CoTaskMemFree(bstrString[0]);
                    bstrString[0] = 0;
                    bstrString[1] = 0;
                  }
                  goto LABEL_456;
                }
              }
            }
            wil::details::ScopeExitFn__lambda_8b4ff283cf0951643c10e64da2111026___::_ScopeExitFn__lambda_8b4ff283cf0951643c10e64da2111026___(&Uuid);
            if ( bstrString[0] )
            {
              CoTaskMemFree(bstrString[0]);
              bstrString[0] = 0;
              bstrString[1] = 0;
            }
            goto LABEL_522;
          }
          v146 = DynamoTriggerContext(StringUuid, v159);
        }
LABEL_430:
        v190[0] = v146;
        if ( v146 < 0 )
          goto LABEL_522;
        goto LABEL_456;
      }
      if ( v257 )
      {
        v195 = 0;
        if ( WindowsCreateStringReference(
               L"EnterpriseDeviceManagement.Enrollment.ReflectedEnroller",
               0x37u,
               (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
               (HSTRING *)&hstringHeader) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v190[0] = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<EnterpriseDeviceManagement::Enrollment::IReflectedEnrollment>>(
                    hstringHeader.Reserved.Reserved1,
                    &v195);
        if ( (v190[0] & 0x80000000) != 0 )
          goto LABEL_443;
        bstrString[0] = 0;
        v190[0] = (*((__int64 (__fastcall **)(BSTR *, _QWORD, _QWORD, __int64, BSTR *))*v195 + 19))(
                    v195,
                    0,
                    0,
                    2,
                    bstrString);
        if ( (v190[0] & 0x80000000) != 0 )
        {
          v161 = bstrString[0];
          if ( bstrString[0] )
          {
            bstrString[0] = 0;
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v161 + 16LL))(v161);
          }
          goto LABEL_443;
        }
        v190[0] = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress> *>(bstrString[0]);
        if ( (v190[0] & 0x80000000) != 0 )
        {
          v162 = bstrString[0];
          if ( bstrString[0] )
          {
            bstrString[0] = 0;
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v162 + 16LL))(v162);
          }
          goto LABEL_443;
        }
        v164 = bstrString[0];
        if ( bstrString[0] )
        {
          bstrString[0] = 0;
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v164 + 16LL))(v164);
        }
        v72 = (BSTR)v195;
        if ( v195 )
        {
          v195 = 0;
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v72 + 16LL))(v72);
        }
        goto LABEL_456;
      }
      v190[0] = EnsureLogonTasksCreated();
      if ( (v190[0] & 0x80000000) != 0 )
      {
        v165 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogUpdatePollOnLoginTaskAfterUpgradeFailed(v165, v190[0]);
        v190[0] = 0;
      }
      HIDWORD(bstrString[0]) = 6;
      v27 = 0;
      v109 = StringUuid;
    }
    LODWORD(bstrString[0]) = 0;
    v118 = InitiateSessionAsync(v109, bstrString[0], v27);
    goto LABEL_455;
  }
  v190[0] = EnrollEngineInitialize(1, 0, &v200);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  if ( !v201 )
  {
    memset_0(v281, 0, 0x48u);
    *(_OWORD *)&Uuid.Reserved.Reserved1 = 0;
    v190[0] = DmGetCurrentUserSid((unsigned __int16 **)&v208);
    if ( (v190[0] & 0x80000000) != 0 )
      goto LABEL_522;
    LODWORD(v283) = 1;
    *((_QWORD *)&v282 + 1) = v205;
    *(_QWORD *)v281 = hMem;
    *(_QWORD *)&v284[1] = v208;
    *(_QWORD *)&v282 = v202;
    bstrString[0] = 0;
    v190[0] = DiscoverEndpoint(v202, hMem, &v283, v284, (char *)v284 + 8, bstrString);
    if ( (v190[0] & 0x80000000) != 0 )
      goto LABEL_522;
    v190[0] = (**(__int64 (__fastcall ***)(struct IEnrollEngine *, unsigned __int16 *, HANDLE *, HSTRING_HEADER *))v200)(
                v200,
                v281,
                &hObject,
                &Uuid);
    if ( (v190[0] & 0x80000000) != 0 )
      goto LABEL_522;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
    v190[0] = WaitForEnrollment(v200, hObject, (struct _GUID *)&hstringHeader);
    hObject = 0;
    if ( (v190[0] & 0x80000000) != 0 )
      goto LABEL_522;
    goto LABEL_521;
  }
  *(_OWORD *)&Uuid.Reserved.Reserved1 = 0;
  if ( UuidFromStringW(v201, (UUID *)&Uuid) )
  {
    v23 = v201;
    goto LABEL_30;
  }
  v190[0] = 0;
  if ( !v214 )
  {
    bstrString[0] = 0;
    v86 = (*(__int64 (__fastcall **)(struct IEnrollEngine *, HSTRING_HEADER *, _QWORD, BSTR *))(*(_QWORD *)v200 + 32LL))(
            v200,
            &Uuid,
            0,
            bstrString);
    goto LABEL_203;
  }
  LODWORD(pvData) = 0;
  pcbData = 63;
  v190[0] = IsValidEnrollment(v201, (int *)&pvData, (enum EnrollmentStateTag *)&pcbData);
  if ( (v190[0] & 0x80000000) != 0 )
    goto LABEL_522;
  if ( !(_DWORD)pvData )
    goto LABEL_522;
  if ( pcbData == 4 )
    goto LABEL_522;
  v190[0] = CheckRenewParametersAndTask(v201);
  if ( v190[0] == -2145910762 )
    goto LABEL_522;
  v194 = 0;
  v166 = ActivationClientWrapper::RequestNetworkActivity((ActivationClientWrapper *)&v194);
  v190[0] = v166;
  if ( v166 < 0 && (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(
      WP_ENROLLMENT_CLIENT_PROVIDER_Context,
      StartingRenewalFailedEvent,
      (unsigned int)v166);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Move_Renew_To_EnrollmentService>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Move_Renew_To_EnrollmentService>::GetImpl'::`2'::impl) )
  {
    bstrString[0] = 0;
    v176 = (*(__int64 (__fastcall **)(struct IEnrollEngine *, HSTRING_HEADER *, BSTR *))(*(_QWORD *)v200 + 144LL))(
             v200,
             &Uuid,
             bstrString);
    v190[0] = v176;
    if ( v176 < 0 )
    {
      if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) == 0 )
        goto LABEL_479;
      v177 = (unsigned int)v176;
LABEL_509:
      McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_CLIENT_PROVIDER_Context, StartingRenewalFailedEvent, v177);
LABEL_479:
      if ( v194 )
      {
        PdcActivationClientUnregister();
        v194 = 0;
      }
      goto LABEL_522;
    }
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&Uuid.Reserved.Reserved1;
    v190[0] = WaitForRenewal(v200, bstrString[0], (struct _GUID *)&hstringHeader);
    bstrString[0] = 0;
LABEL_511:
    ClearRenewNowFlag(v201);
    v178 = SetMmpcEnrollmentFlag(0);
    if ( v178 < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(v179, EnterpriseDiagnosticsSetMmpcFlagFailed, (unsigned int)v178);
    v177 = v190[0];
    if ( (v190[0] & 0x80000000) == 0 || (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) == 0 )
      goto LABEL_479;
    goto LABEL_509;
  }
  pvData = 0;
  v167 = (HSTRING *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator&(&pvData);
  v168 = -1;
  do
    ++v168;
  while ( v201[v168] );
  v169 = WindowsCreateString(v201, v168, v167);
  v190[0] = v169;
  if ( v169 < 0 )
  {
    if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(
        WP_ENROLLMENT_CLIENT_PROVIDER_Context,
        StartingRenewalFailedEvent,
        (unsigned int)v169);
LABEL_477:
    if ( pvData )
      WindowsDeleteString(pvData);
    goto LABEL_479;
  }
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.Enrollment.Enroller",
         0x2Fu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  bstrString[0] = 0;
  v170 = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(
           hstringHeader.Reserved.Reserved1,
           bstrString);
  v92 = v170;
  if ( v170 >= 0 )
  {
    v195 = 0;
    v190[0] = (*(__int64 (__fastcall **)(BSTR, HSTRING, BSTR **))(*(_QWORD *)bstrString[0] + 208LL))(
                bstrString[0],
                pvData,
                &v195);
    if ( (v190[0] & 0x80000000) == 0 )
    {
      v172 = v195;
      if ( !v195 )
      {
        v190[0] = -2147467261;
        if ( (Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits & 2) != 0 )
        {
          McTemplateU0q_EventWriteTransfer(
            WP_ENROLLMENT_CLIENT_PROVIDER_Context,
            StartingRenewalFailedEvent,
            2147500035LL);
          v172 = v195;
        }
        if ( v172 )
        {
          v195 = 0;
          (*((void (__fastcall **)(BSTR *))*v172 + 2))(v172);
        }
        v173 = bstrString[0];
        if ( bstrString[0] )
        {
          bstrString[0] = 0;
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v173 + 16LL))(v173);
        }
        goto LABEL_477;
      }
      v190[0] = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
                  v195,
                  0xFFFFFFFFLL);
    }
    v174 = v195;
    if ( v195 )
    {
      v195 = 0;
      (*((void (__fastcall **)(BSTR *))*v174 + 2))(v174);
    }
    v175 = bstrString[0];
    if ( bstrString[0] )
    {
      bstrString[0] = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v175 + 16LL))(v175);
    }
    if ( pvData )
      WindowsDeleteString(pvData);
    goto LABEL_511;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBB9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
    (const char *)(unsigned int)v170,
    (int)lpWideCharStr);
  v171 = bstrString[0];
  if ( bstrString[0] )
  {
    bstrString[0] = 0;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v171 + 16LL))(v171);
  }
  if ( pvData )
    WindowsDeleteString(pvData);
  if ( v194 )
  {
    PdcActivationClientUnregister();
    v194 = 0;
  }
LABEL_535:
  if ( v13 )
    CoUninitialize();
  SysFreeString(v8);
  return v92;
}

```

## disassembly

```asm
0x140019a6c  push    rbp
0x140019a6e  push    rbx
0x140019a6f  push    rsi
0x140019a70  push    rdi
0x140019a71  push    r12
0x140019a73  push    r13
0x140019a75  push    r14
0x140019a77  push    r15
0x140019a79  lea     rbp, [rsp-728h]
0x140019a81  sub     rsp, 828h
0x140019a88  mov     rax, cs:__security_cookie
0x140019a8f  xor     rax, rsp
0x140019a92  mov     [rbp+760h+var_50], rax
0x140019a99  mov     rbx, r8
0x140019a9c  xor     r13d, r13d
0x140019a9f  mov     [rsp+860h+var_810], r13d
0x140019aa4  mov     [rbp+760h+hMem], r13
0x140019aa8  mov     [rbp+760h+var_7A0], r13
0x140019aac  mov     [rbp+760h+var_7B0], r13
0x140019ab0  mov     [rbp+760h+var_7B8], r13
0x140019ab4  mov     [rsp+860h+StringUuid], r13
0x140019ab9  mov     [rbp+760h+var_780], r13
0x140019abd  mov     [rbp+760h+var_788], r13
0x140019ac1  mov     [rbp+760h+var_770], r13
0x140019ac5  xor     edx, edx; Val
0x140019ac7  mov     r8d, 408h; Size
0x140019acd  lea     rcx, [rbp+760h+var_768]; void *
0x140019ad1  call    memset_0
0x140019ad6  or      r14, 0FFFFFFFFFFFFFFFFh
0x140019ada  lea     r15d, [r13+3]
0x140019ade  test    rbx, rbx
0x140019ae1  jz      short loc_140019B44
0x140019ae3  mov     [rsp+860h+cchWideChar], r13d; cchWideChar
0x140019ae8  mov     [rsp+860h+lpWideCharStr], r13; lpWideCharStr
0x140019aed  mov     r9d, r14d; cbMultiByte
0x140019af0  mov     r8, rbx; lpMultiByteStr
0x140019af3  xor     edx, edx; dwFlags
0x140019af5  mov     ecx, r15d; CodePage
0x140019af8  call    cs:__imp_MultiByteToWideChar
0x140019afe  mov     edi, eax
0x140019b00  lea     edx, [rax-1]; ui
0x140019b03  xor     ecx, ecx; strIn
0x140019b05  call    cs:__imp_SysAllocStringLen
0x140019b0b  mov     rsi, rax
0x140019b0e  test    rax, rax
0x140019b11  jz      short loc_140019B35
0x140019b13  mov     [rsp+860h+cchWideChar], edi; cchWideChar
0x140019b17  mov     [rsp+860h+lpWideCharStr], rax; lpWideCharStr
0x140019b1c  mov     r9d, r14d; cbMultiByte
0x140019b1f  mov     r8, rbx; lpMultiByteStr
0x140019b22  xor     edx, edx; dwFlags
0x140019b24  mov     ecx, r15d; CodePage
0x140019b27  call    cs:__imp_MultiByteToWideChar
0x140019b2d  cmp     eax, edi
0x140019b2f  jnz     loc_14001C94D
0x140019b35  mov     [rbp+760h+var_778], rsi
0x140019b39  test    rsi, rsi
0x140019b3c  jz      loc_14001C956
0x140019b42  jmp     short loc_140019B4B
0x140019b44  mov     rsi, r13
0x140019b47  mov     [rbp+760h+var_778], r13
0x140019b4b  mov     [rbp+760h+hObject], r13
0x140019b4f  mov     [rbp+760h+var_7C0], r13
0x140019b53  mov     [rbp+760h+var_7C8], 3Fh ; '?'
0x140019b5a  lea     rbx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x140019b61  mov     r9, rbx
0x140019b64  mov     r8, rbx
0x140019b67  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER
0x140019b6e  call    McGenEventRegister_EventRegister
0x140019b73  lea     r9, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140019b7a  lea     r8, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140019b81  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS
0x140019b88  call    McGenEventRegister_EventRegister
0x140019b8d  mov     r15d, 1
0x140019b93  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r15b
0x140019b9a  jz      short loc_140019BBA
0x140019b9c  lea     rax, [rbp+760h+hstringHeader]
0x140019ba3  mov     [rsp+860h+lpWideCharStr], rax
0x140019ba8  mov     r9d, r15d
0x140019bab  lea     rdx, EnrollmentClientStartedEvent
0x140019bb2  mov     rcx, rbx
0x140019bb5  call    McGenEventWrite_EventWriteTransfer
0x140019bba  mov     rax, cs:Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor
0x140019bc1  mov     r8d, [rax]
0x140019bc4  mov     r12d, 4
0x140019bca  test    r12b, r8b
0x140019bcd  jnz     short loc_140019BE4
0x140019bcf  lea     rdx, [rsp+860h+bstrString]
0x140019bd4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(void)
0x140019bd9  mov     rcx, [rax]
0x140019bdc  mov     [rsp+860h+bstrString], rcx
0x140019be1  mov     r8d, ecx
0x140019be4  mov     [rbp+760h+var_7A8], r13d
0x140019be8  mov     ebx, 3
0x140019bed  mov     [rbp+760h+var_7A4], bx
0x140019bf1  mov     r9d, r8d
0x140019bf4  shr     r9d, 0Bh
0x140019bf8  and     r9d, r15d
0x140019bfb  shr     r8d, 0Ah
0x140019bff  and     r8d, r15d
0x140019c02  mov     dword ptr [rsp+860h+pcbData], ebx
0x140019c06  mov     [rsp+860h+cchWideChar], r15d
0x140019c0b  lea     rax, [rbp+760h+var_7A8]
0x140019c0f  mov     [rsp+860h+lpWideCharStr], rax
0x140019c14  mov     edx, 36A833Ch
0x140019c19  lea     rcx, qword_14007E450
0x140019c20  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140019c25  lea     rcx, dword_14007D088; CallbackContext
0x140019c2c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140019c31  lea     rcx, dword_14007D1C0; CallbackContext
0x140019c38  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140019c3d  lea     rcx, dword_14007D108; CallbackContext
0x140019c44  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140019c49  lea     rcx, dword_14007D050; CallbackContext
0x140019c50  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140019c55  lea     rcx, dword_14007D1F8; CallbackContext
0x140019c5c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140019c61  mov     edi, r13d
0x140019c64  xor     edx, edx; dwCoInit
0x140019c66  xor     ecx, ecx; pvReserved
0x140019c68  call    cs:__imp_CoInitializeEx
0x140019c6e  test    eax, eax
0x140019c70  cmovns  edi, r15d
0x140019c74  mov     [rbp+760h+var_7A8], edi
0x140019c77  call    cs:__imp_GetCommandLineW
0x140019c7d  mov     r9, rax
0x140019c80  mov     [rsp+860h+cchWideChar], 410h
0x140019c88  lea     rax, [rbp+760h+var_770]
0x140019c8c  mov     [rsp+860h+lpWideCharStr], rax
0x140019c91  lea     r8, ?CommandLineHandler@@YAJPEBGPEAE@Z; CommandLineHandler(ushort const *,uchar *)
0x140019c98  lea     edx, [rbx+3Fh]
0x140019c9b  lea     rcx, off_14007D300; "c"
0x140019ca2  call    cs:__imp_ProcessCommandLine
0x140019ca8  mov     [rsp+860h+var_810], eax
0x140019cac  test    eax, eax
0x140019cae  jns     short loc_140019CDF
0x140019cb0  mov     [rsp+860h+cchWideChar], 410h
0x140019cb8  lea     rax, [rbp+760h+var_770]
0x140019cbc  mov     [rsp+860h+lpWideCharStr], rax
0x140019cc1  mov     r9, rsi
0x140019cc4  lea     r8, ?CommandLineHandler@@YAJPEBGPEAE@Z; CommandLineHandler(ushort const *,uchar *)
0x140019ccb  lea     edx, [rbx+3Fh]
0x140019cce  lea     rcx, off_14007D300; "c"
0x140019cd5  call    cs:__imp_ProcessCommandLine
0x140019cdb  mov     [rsp+860h+var_810], eax
0x140019cdf  test    cs:Microsoft_WindowsPhone_EnrollmentClient_ProviderEnableBits, r15b
0x140019ce6  jz      loc_140019DA8
0x140019cec  mov     dword ptr [rsp+860h+pvData], eax
0x140019cf0  call    cs:__imp_GetCommandLineW
0x140019cf6  lea     rdx, aNull_0; "NULL"
0x140019cfd  test    rax, rax
0x140019d00  jz      short loc_140019D18
0x140019d02  mov     rcx, r14
0x140019d05  inc     rcx
0x140019d08  cmp     [rax+rcx*2], r13w
0x140019d0d  jnz     short loc_140019D05
0x140019d0f  lea     ecx, ds:2[rcx*2]
0x140019d16  jmp     short loc_140019D20
0x140019d18  mov     rax, rdx
0x140019d1b  mov     ecx, 0Ah
0x140019d20  mov     [rbp+760h+var_310], rax
0x140019d27  mov     dword ptr [rbp+760h+var_308], ecx
0x140019d2d  mov     dword ptr [rbp+760h+var_308+4], r13d
0x140019d34  test    rsi, rsi
0x140019d37  jz      short loc_140019D52
0x140019d39  mov     rax, r14
0x140019d3c  inc     rax
0x140019d3f  cmp     [rsi+rax*2], r13w
0x140019d44  jnz     short loc_140019D3C
0x140019d46  mov     rdx, rsi
0x140019d49  lea     eax, ds:2[rax*2]
0x140019d50  jmp     short loc_140019D57
0x140019d52  mov     eax, 0Ah
0x140019d57  mov     qword ptr [rbp+760h+var_308+8], rdx
0x140019d5e  mov     dword ptr [rbp+760h+var_2F8], eax
0x140019d64  mov     dword ptr [rbp+760h+var_2F8+4], r13d
0x140019d6b  lea     rax, [rsp+860h+pvData]
0x140019d70  mov     qword ptr [rbp+760h+var_2F8+8], rax
0x140019d77  mov     [rbp+760h+var_2E8], 4
0x140019d82  lea     rax, [rbp+760h+var_320]
0x140019d89  mov     [rsp+860h+lpWideCharStr], rax; int
0x140019d8e  mov     r9d, r12d
0x140019d91  lea     rdx, EnrollmentClientCommandLineEvent
0x140019d98  lea     rcx, WP_ENROLLMENT_CLIENT_PROVIDER_Context
0x140019d9f  call    McGenEventWrite_EventWriteTransfer
0x140019da4  mov     eax, [rsp+860h+var_810]
0x140019da8  test    eax, eax
0x140019daa  js      loc_14001C728
0x140019db0  lea     r8, [rsp+860h+StringUuid]
0x140019db5  mov     edx, 0FFFFFFFFh
0x140019dba  mov     rcx, [rbp+760h+var_708]
0x140019dbe  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140019dc4  mov     [rsp+860h+var_810], eax
0x140019dc8  test    eax, eax
0x140019dca  js      loc_14001C728
0x140019dd0  mov     rcx, [rsp+860h+StringUuid]; StringUuid
0x140019dd5  test    rcx, rcx
0x140019dd8  jz      loc_140019EC7
0x140019dde  xorps   xmm0, xmm0
0x140019de1  movups  xmmword ptr [rbp+760h+Uuid], xmm0
0x140019de8  lea     rdx, [rbp+760h+Uuid]; Uuid
0x140019def  call    cs:__imp_UuidFromStringW
0x140019df5  test    eax, eax
0x140019df7  jz      short loc_140019E15
0x140019df9  mov     rcx, [rsp+860h+StringUuid]; StringUuid
0x140019dfe  lea     rdx, [rbp+760h+Uuid]; Uuid
0x140019e05  call    cs:__imp_UuidFromStringW
0x140019e0b  or      eax, 80010000h
0x140019e10  jmp     loc_14001A396
0x140019e15  mov     [rsp+860h+var_810], r13d
0x140019e1a  movaps  xmm0, xmmword ptr [rbp+760h+Uuid]
0x140019e21  movdqa  xmmword ptr [rsp+860h+bstrString], xmm0
0x140019e27  lea     rdx, [rbp+760h+var_7C8]
0x140019e2b  lea     rcx, [rsp+860h+bstrString]
0x140019e30  call    cs:__imp_GetEnrollmentType
0x140019e36  mov     [rsp+860h+var_810], eax
0x140019e3a  test    eax, eax
0x140019e3c  jns     loc_140019EC7
0x140019e42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks>::GetImpl(void)'::`2'::impl
0x140019e49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Cleanup_LeftOver_Tasks>::__private_IsEnabled(void)
0x140019e4e  test    al, al
0x140019e50  jz      loc_14001C728
0x140019e56  cmp     [rbp+760h+var_450], r13d
0x140019e5d  jz      short loc_140019E70
0x140019e5f  mov     rdx, [rsp+860h+StringUuid]; unsigned __int16 *
0x140019e64  lea     rcx, aRefreshSchedul; "Refresh schedule created by Declared Co"...
0x140019e6b  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x140019e70  cmp     [rbp+760h+var_370], r13d
0x140019e77  jz      short loc_140019E8A
0x140019e79  mov     rdx, [rsp+860h+StringUuid]; unsigned __int16 *
0x140019e7e  lea     rcx, aPolicyManagerL; "Policy Manager Login Refresh Schedule"
0x140019e85  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x140019e8a  cmp     [rbp+760h+var_630], r13d
0x140019e91  jz      short loc_140019EA4
0x140019e93  mov     rdx, [rsp+860h+StringUuid]; unsigned __int16 *
0x140019e98  lea     rcx, aPushrenew; "pushrenew"
0x140019e9f  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x140019ea4  cmp     [rbp+760h+var_690], r13d
0x140019eab  jz      loc_14001C728
0x140019eb1  mov     rdx, [rsp+860h+StringUuid]; unsigned __int16 *
0x140019eb6  lea     rcx, aPushlaunch; "pushlaunch"
0x140019ebd  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x140019ec2  jmp     loc_14001C728
0x140019ec7  lea     r8, [rbp+760h+var_780]
0x140019ecb  mov     edx, 0FFFFFFFFh
0x140019ed0  mov     rcx, [rbp+760h+var_5C8]
0x140019ed7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140019edd  mov     [rsp+860h+var_810], eax
0x140019ee1  test    eax, eax
0x140019ee3  js      loc_14001C728
0x140019ee9  lea     r8, [rbp+760h+var_7B8]
0x140019eed  mov     edx, 0FFFFFFFFh
0x140019ef2  mov     rcx, [rbp+760h+var_718]
0x140019ef6  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140019efc  mov     [rsp+860h+var_810], eax
0x140019f00  test    eax, eax
0x140019f02  js      loc_14001C728
0x140019f08  lea     r8, [rbp+760h+var_7A0]
0x140019f0c  mov     edx, 0FFFFFFFFh
0x140019f11  mov     rcx, [rbp+760h+var_758]
0x140019f15  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140019f1b  mov     [rsp+860h+var_810], eax
0x140019f1f  test    eax, eax
0x140019f21  js      loc_14001C728
0x140019f27  lea     r8, [rbp+760h+var_7B0]
0x140019f2b  mov     edx, 0FFFFFFFFh
0x140019f30  mov     rcx, [rbp+760h+var_738]
0x140019f34  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140019f3a  mov     [rsp+860h+var_810], eax
0x140019f3e  test    eax, eax
0x140019f40  js      loc_14001C728
0x140019f46  lea     r8, [rbp+760h+hMem]
0x140019f4a  mov     edx, 0FFFFFFFFh
0x140019f4f  mov     rcx, [rbp+760h+var_728]
0x140019f53  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x140019f59  mov     [rsp+860h+var_810], eax
0x140019f5d  test    eax, eax
0x140019f5f  js      loc_14001C728
0x140019f65  cmp     [rbp+760h+var_480], r13d
0x140019f6c  jz      short loc_140019F78
0x140019f6e  call    RunAsComServer
0x140019f73  jmp     loc_14001A396
0x140019f78  cmp     [rbp+760h+var_590], r13d
0x140019f7f  jz      loc_14001A0E6
0x140019f85  xor     edx, edx; Val
0x140019f87  mov     r8d, 208h; Size
0x140019f8d  lea     rcx, [rbp+760h+sourceString]; void *
0x140019f94  call    memset_0
0x140019f99  mov     qword ptr [rbp+760h+var_320], r13
0x140019fa0  xorps   xmm0, xmm0
0x140019fa3  xor     eax, eax
0x140019fa5  movups  xmmword ptr [rbp+448h], xmm0
0x140019fac  movups  [rbp+760h+var_308], xmm0
0x140019fb3  movups  [rbp+760h+var_2F8], xmm0
0x140019fba  mov     [rbp+760h+var_2E8], rax
0x140019fc1  lea     rdx, [rbp+760h+sourceString]
0x140019fc8  mov     ecx, 104h
0x140019fcd  call    cs:__imp_DMCSP_DevDetail_GetSwV
0x140019fd3  mov     [rsp+860h+var_810], eax
0x140019fd7  test    eax, eax
  ... truncated ...
```
