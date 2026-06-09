# DCEngine::ReconstructQueueAndExecute(bool,ushort const *,ushort const *,ushort const *,DCCSPURIState)

- ea: `0x18011440c`
- end: `0x180117892`
- name: `?ReconstructQueueAndExecute@DCEngine@@AEAAJ_NPEBG11W4DCCSPURIState@@@Z`
- size: `13446`
- prototype: `int __high(bool, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum DCCSPURIState)`
- caller_count: `3`
- callee_count: `87`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180113930`
- `0x180117898`
- `0x180118220`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000bf00`
- `0x18000bf4c`
- `0x18000c8f4`
- `0x18000e24c`
- `0x1800117dc`
- `0x180011fe0`
- `0x180013d4c`
- `0x18001438c`
- `0x180018a20`
- `0x180018ac0`
- `0x180018b30`
- `0x180018cc4`
- `0x180019d38`
- `0x18001a60c`
- `0x18001c08c`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18001d37c`
- `0x18001def8`
- `0x18004b7f4`
- `0x18004b870`
- `0x18004d158`
- `0x180056bcc`
- `0x18005860c`
- `0x180058b08`
- `0x180058b3c`
- `0x18005fa30`
- `0x18005fcf8`
- `0x1800725e0`
- `0x180076c10`
- `0x180086c10`
- `0x18008bb70`
- `0x18008ff9c`
- `0x180098e10`
- `0x18009a2e4`
- `0x1800a01ec`
- `0x1800a0228`
- `0x1800a1dbc`
- `0x1800a9e90`
- `0x1800abbe0`
- `0x1800f5c8c`
- `0x1800f9b5c`
- `0x1800f9d70`
- `0x1800f9e64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180114b1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180114c52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180114dc8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180114b1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180114c52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180114dc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011472c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011472c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801151b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180115263`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801153ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801151b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180115263`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801153ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801162d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801162d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801161c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801161c5`
- `OLEAUT32!__imp_SysAllocString` at `0x180114c1a`
- `OLEAUT32!__imp_SysAllocString` at `0x180114d31`
- `OLEAUT32!__imp_SysAllocString` at `0x180114df0`
- `OLEAUT32!__imp_SysAllocString` at `0x1801152a2`
- `OLEAUT32!__imp_SysAllocString` at `0x180114c1a`
- `OLEAUT32!__imp_SysAllocString` at `0x180114d31`
- `OLEAUT32!__imp_SysAllocString` at `0x180114df0`
- `OLEAUT32!__imp_SysAllocString` at `0x1801152a2`
- `OLEAUT32!__imp_VariantInit` at `0x180114fa9`
- `OLEAUT32!__imp_VariantInit` at `0x18011601d`
- `OLEAUT32!__imp_VariantInit` at `0x18011615f`
- `OLEAUT32!__imp_VariantInit` at `0x180116407`
- `OLEAUT32!__imp_VariantInit` at `0x18011685d`
- `OLEAUT32!__imp_VariantInit` at `0x180114fa9`
- `OLEAUT32!__imp_VariantInit` at `0x18011601d`
- `OLEAUT32!__imp_VariantInit` at `0x18011615f`
- `OLEAUT32!__imp_VariantInit` at `0x180116407`
- `OLEAUT32!__imp_VariantInit` at `0x18011685d`
- `OLEAUT32!__imp_VariantClear` at `0x1801155fa`
- `OLEAUT32!__imp_VariantClear` at `0x18011586f`
- `OLEAUT32!__imp_VariantClear` at `0x180115a00`
- `OLEAUT32!__imp_VariantClear` at `0x180115b80`
- `OLEAUT32!__imp_VariantClear` at `0x180115d22`
- `OLEAUT32!__imp_VariantClear` at `0x180115e9f`
- `OLEAUT32!__imp_VariantClear` at `0x180116142`
- `OLEAUT32!__imp_VariantClear` at `0x180116358`
- `OLEAUT32!__imp_VariantClear` at `0x1801163aa`
- `OLEAUT32!__imp_VariantClear` at `0x1801165e3`
- `OLEAUT32!__imp_VariantClear` at `0x180116600`
- `OLEAUT32!__imp_VariantClear` at `0x180116652`
- `OLEAUT32!__imp_VariantClear` at `0x1801167ab`
- `OLEAUT32!__imp_VariantClear` at `0x1801167c8`
- `OLEAUT32!__imp_VariantClear` at `0x18011681a`
- `OLEAUT32!__imp_VariantClear` at `0x1801169d0`
- `OLEAUT32!__imp_VariantClear` at `0x1801169fb`
- `OLEAUT32!__imp_VariantClear` at `0x180116a18`
- `OLEAUT32!__imp_VariantClear` at `0x180116a6a`
- `OLEAUT32!__imp_VariantClear` at `0x180116ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180116add`
- `OLEAUT32!__imp_VariantClear` at `0x180116afd`
- `OLEAUT32!__imp_VariantClear` at `0x180116e53`
- `OLEAUT32!__imp_VariantClear` at `0x1801170f1`
- `OLEAUT32!__imp_VariantClear` at `0x1801171ad`
- `OLEAUT32!__imp_VariantClear` at `0x180117269`
- `OLEAUT32!__imp_VariantClear` at `0x180117325`
- `OLEAUT32!__imp_VariantClear` at `0x1801173eb`
- `OLEAUT32!__imp_VariantClear` at `0x1801174ae`
- `OLEAUT32!__imp_VariantClear` at `0x180117595`
- `OLEAUT32!__imp_VariantClear` at `0x1801175e7`
- `OLEAUT32!__imp_VariantClear` at `0x1801155fa`
- `OLEAUT32!__imp_VariantClear` at `0x18011586f`
- `OLEAUT32!__imp_VariantClear` at `0x180115a00`
- `OLEAUT32!__imp_VariantClear` at `0x180115b80`
- `OLEAUT32!__imp_VariantClear` at `0x180115d22`
- `OLEAUT32!__imp_VariantClear` at `0x180115e9f`
- `OLEAUT32!__imp_VariantClear` at `0x180116142`
- `OLEAUT32!__imp_VariantClear` at `0x180116358`
- `OLEAUT32!__imp_VariantClear` at `0x1801163aa`
- `OLEAUT32!__imp_VariantClear` at `0x1801165e3`
- `OLEAUT32!__imp_VariantClear` at `0x180116600`
- `OLEAUT32!__imp_VariantClear` at `0x180116652`
- `OLEAUT32!__imp_VariantClear` at `0x1801167ab`
- `OLEAUT32!__imp_VariantClear` at `0x1801167c8`
- `OLEAUT32!__imp_VariantClear` at `0x18011681a`
- `OLEAUT32!__imp_VariantClear` at `0x1801169d0`
- `OLEAUT32!__imp_VariantClear` at `0x1801169fb`
- `OLEAUT32!__imp_VariantClear` at `0x180116a18`
- `OLEAUT32!__imp_VariantClear` at `0x180116a6a`
- `OLEAUT32!__imp_VariantClear` at `0x180116ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180116add`
- `OLEAUT32!__imp_VariantClear` at `0x180116afd`
- `OLEAUT32!__imp_VariantClear` at `0x180116e53`
- `OLEAUT32!__imp_VariantClear` at `0x1801170f1`
- `OLEAUT32!__imp_VariantClear` at `0x1801171ad`
- `OLEAUT32!__imp_VariantClear` at `0x180117269`
- `OLEAUT32!__imp_VariantClear` at `0x180117325`
- `OLEAUT32!__imp_VariantClear` at `0x1801173eb`
- `OLEAUT32!__imp_VariantClear` at `0x1801174ae`
- `OLEAUT32!__imp_VariantClear` at `0x180117595`
- `OLEAUT32!__imp_VariantClear` at `0x1801175e7`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180114c71`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180114c71`
- `omadmapi!__imp_OmaDmSendAlertNotification3` at `0x180116953`
- `omadmapi!__imp_OmaDmSendAlertNotification3` at `0x180116953`

## string_xrefs

- `0x1801149d6`: `DeleteRequest`
- `0x180116770`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x1801164a3`: `DeclaredConfigurationStore_WriteResultData`
- `0x180114ce6`: `DmGetActiveUserSid`
- `0x18011579c`: `GetEnrollmentIdSidStateDocIdVersionRawKey`
- `0x1801144d4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180114555`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180114d62`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18011633e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x18011650a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180117383`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180117630`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180117795`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\core\dcengine.cpp`
- `0x180115a9f`: `DCCDNUtil_GetRegistryDWORD(docIdVersionRawRegKey.get(),nullptr, c_szDCBehavior, &dwBehavior)`
- `0x18011591f`: `DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)`
- `0x180116de6`: `meta->CreateNotifEventHandle`
- `0x1801171fc`: `meta->CreateNotifEventHandle`
- `0x180117816`: `engine->StartExecutionThreadIfNotRunning`
- `0x180117059`: `engine->ConfigDC`
- `0x18011707c`: `engine->ConfigDC`
- `0x180114646`: `DeclaredConfigurationStore_DeleteScheduledTask(DECLARED_CONFIGURATION_REFRESH_ID)`
- `0x18011466d`: `No requests for Orchestrator, delete DC schedule task`
- `0x180114694`: `No requests for Orchestrator, delete DC schedule task`
- `0x180117712`: `Invalid user context - DeleteCorruptedDocAndRecord`
- `0x1801155dc`: `DeclaredConfigurationStore_ReadResultData state - DeleteCorruptedDocAndRecord`
- `0x18011552c`: `ReconstructQueueAndExecute:DeclaredConfigurationStore_ReadResultData failed`
- `0x1801159cc`: `DCCDNUtil_GetRegistryString osdefinedscenario - DeleteCorruptedDocAndRecord`
- `0x180115849`: `GetEnrollmentIdSidStateDocIdVersionRawKey - DeleteCorruptedDocAndRecord`
- `0x180115cd2`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey - DeleteCorruptedDocAndRecord`
- `0x180115b4c`: `DCCDNUtil_GetRegistryString behavior - DeleteCorruptedDocAndRecord`
- `0x180115e4f`: `GetResultsEnrollmentIdSidStateDocIdKey - DeleteCorruptedDocAndRecord`
- `0x18011757a`: `DeclaredConfigurationStore_GetPersistedDocument - DeleteCorruptedDocAndRecord`
- `0x1801164f9`: `failed to update doc result to ConfigCompletedSuccessNoRefresh for enrollment %ws doc %ws version %ws`
- `0x18011649c`: `Update doc result to DCCSPURIState::ConfigCompletedSuccessNoRefresh`
- `0x180116901`: `com.microsoft:mdm.declaredconfiguration.deviceaction.rebootcompleted`
- `0x1801168b2`: `DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state`
- `0x180116910`: `reboot completed for device action or policies`

## pseudocode

```c
// Hidden C++ exception states: #wind=53
__int64 __fastcall DCEngine::ReconstructQueueAndExecute(
        __int64 a1,
        char a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  const unsigned __int16 *v6; // r15
  unsigned __int16 *v7; // rsi
  __int64 v8; // r12
  OrchestratorDBManager *v9; // rcx
  int v10; // r13d
  int v11; // eax
  const char *v12; // rax
  __int64 v13; // rdx
  int AllRequestsPerEnrollment; // eax
  const unsigned __int16 *v15; // rcx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v17; // r8
  int v18; // ebx
  CDeclaredConfigurationLogger *v19; // rax
  CDeclaredConfigurationLogger *v20; // rax
  int v21; // ecx
  char *v22; // rax
  char *v23; // rdi
  unsigned __int16 *v24; // r12
  OrchestratorDBManager *v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rax
  int v28; // ebx
  unsigned __int16 v29; // ax
  unsigned __int16 *v30; // rcx
  int v31; // ebx
  int v32; // ecx
  OrchestratorDBManager *v33; // rcx
  CDeclaredConfigurationLogger *v34; // rax
  int v35; // ebx
  unsigned __int16 **v36; // rcx
  unsigned __int16 **v37; // rax
  unsigned __int16 i; // ax
  unsigned __int16 **v39; // rbx
  char **v40; // rcx
  __int64 v41; // r8
  OLECHAR **v42; // rcx
  const OLECHAR *v43; // rcx
  OLECHAR **v44; // rcx
  CDeclaredConfigurationLogger *v45; // rax
  const unsigned __int16 *v46; // r9
  OLECHAR **v47; // rcx
  const OLECHAR *v48; // rcx
  const unsigned __int16 *v49; // rdx
  OLECHAR *v50; // rcx
  char IsEnabled; // al
  const unsigned __int16 *v52; // rdx
  OLECHAR *v53; // rcx
  unsigned int v54; // r8d
  _QWORD *v55; // r8
  unsigned __int16 **v56; // rdx
  signed int RegistryMultiString; // ebx
  VARTYPE v58; // ax
  HKEY v59; // r15
  OLECHAR *v60; // r12
  LSTATUS v61; // eax
  unsigned __int64 v62; // rbx
  unsigned __int64 v63; // rax
  BYTE *v64; // rax
  BYTE *v65; // rsi
  LSTATUS v66; // eax
  unsigned __int16 v67; // dx
  LSTATUS Value; // eax
  LONG v69; // eax
  _QWORD *v70; // rdx
  unsigned __int16 **v71; // rcx
  OLECHAR **v72; // rax
  OLECHAR **v73; // r9
  int v74; // ecx
  const unsigned __int16 *v75; // r8
  CDeclaredConfigurationLogger *v76; // rax
  const unsigned __int16 *v77; // r9
  unsigned __int64 Lo; // rbx
  _QWORD *v79; // r8
  unsigned __int16 **v80; // rdx
  _QWORD *v81; // rdx
  unsigned __int16 **v82; // rcx
  OLECHAR **v83; // rax
  OLECHAR **v84; // r9
  CDeclaredConfigurationLogger *v85; // rax
  const unsigned __int16 *v86; // r8
  CDeclaredConfigurationLogger *v87; // rax
  const unsigned __int16 *v88; // r9
  CDeclaredConfigurationLogger *v89; // rax
  const unsigned __int16 *v90; // r8
  CDeclaredConfigurationLogger *v91; // rax
  const unsigned __int16 *v92; // r9
  CDeclaredConfigurationLogger *v93; // rax
  const unsigned __int16 *v94; // r8
  CDeclaredConfigurationLogger *v95; // rax
  const unsigned __int16 *v96; // r9
  const unsigned __int16 *v97; // rdx
  const unsigned __int16 *v98; // r8
  CDeclaredConfigurationLogger *v99; // rax
  const unsigned __int16 *v100; // r9
  __int64 v101; // rax
  const unsigned __int16 *v102; // rax
  const unsigned __int16 *v103; // rax
  CDeclaredConfigurationLogger *v104; // r10
  __int64 v105; // rax
  __int64 v106; // rdx
  char v107; // r12
  __int64 v108; // rax
  __int64 v109; // rax
  int v110; // eax
  int v111; // r8d
  int v112; // r9d
  __int64 v113; // rdx
  CDeclaredConfigurationLogger *v114; // rax
  int v115; // r15d
  int v116; // edx
  int v117; // r8d
  int v118; // r9d
  int v119; // eax
  int v120; // r8d
  int v121; // r9d
  int v122; // ecx
  int v123; // esi
  LSTATUS v124; // esi
  int v125; // ecx
  LONG v126; // eax
  const unsigned __int16 *v127; // rdx
  const unsigned __int16 *v128; // r8
  CDeclaredConfigurationLogger *v129; // rax
  const char *v130; // rax
  __int64 v131; // rdx
  __int64 v132; // r8
  const unsigned __int16 *v133; // rax
  __int64 v134; // rax
  int v135; // ecx
  int updated; // eax
  int v137; // ecx
  int v138; // ebx
  char v139; // si
  __int64 v140; // rcx
  char *v141; // rcx
  __int64 v142; // r12
  __int64 v143; // rdx
  __int64 v144; // r15
  __int64 v145; // rdx
  unsigned __int16 *v146; // r14
  __int64 v147; // rdx
  unsigned __int16 *v148; // rsi
  __int64 v149; // rdx
  unsigned __int16 *v150; // rbx
  __int64 v151; // rdx
  unsigned __int16 *v152; // rax
  __int64 v153; // rax
  DCMetaData *v154; // rbx
  const unsigned __int16 *v155; // r15
  CDeclaredConfigurationLogger *v156; // rax
  __int64 (__fastcall ***v157)(_QWORD, DCMetaData *, __int64, __int64 *); // rsi
  __int64 v158; // r8
  int v159; // ecx
  CDeclaredConfigurationLogger *v160; // rax
  unsigned __int16 *v161; // rsi
  int v162; // ebx
  int v163; // ecx
  CDeclaredConfigurationLogger *v164; // rax
  int v165; // ecx
  CDeclaredConfigurationLogger *v166; // rax
  CDeclaredConfigurationLogger *v167; // rax
  const unsigned __int16 *v168; // rax
  const unsigned __int16 *v169; // rax
  CDeclaredConfigurationLogger *v170; // r10
  const unsigned __int16 *v171; // r8
  CDeclaredConfigurationLogger *v172; // rax
  const unsigned __int16 *v173; // r9
  __int64 v174; // rcx
  int lpData; // [rsp+20h] [rbp-A38h]
  int lpDataa; // [rsp+20h] [rbp-A38h]
  int lpDatab; // [rsp+20h] [rbp-A38h]
  DWORD lpDatac; // [rsp+20h] [rbp-A38h]
  LPBYTE lpDatad; // [rsp+20h] [rbp-A38h]
  int lpDatae; // [rsp+20h] [rbp-A38h]
  const char *lpcbData; // [rsp+28h] [rbp-A30h]
  HKEY lpcbDataa; // [rsp+28h] [rbp-A30h]
  char *v184; // [rsp+40h] [rbp-A18h] BYREF
  __int64 v185; // [rsp+48h] [rbp-A10h] BYREF
  char v186; // [rsp+50h] [rbp-A08h]
  OLECHAR *v187; // [rsp+58h] [rbp-A00h] BYREF
  __int64 v188; // [rsp+60h] [rbp-9F8h] BYREF
  DWORD v189[2]; // [rsp+68h] [rbp-9F0h] BYREF
  DWORD Type[2]; // [rsp+70h] [rbp-9E8h] BYREF
  HKEY v191; // [rsp+78h] [rbp-9E0h] BYREF
  _QWORD v192[2]; // [rsp+80h] [rbp-9D8h] BYREF
  char v193; // [rsp+90h] [rbp-9C8h]
  __int64 v194; // [rsp+98h] [rbp-9C0h] BYREF
  int v195[4]; // [rsp+A0h] [rbp-9B8h] BYREF
  int v196; // [rsp+B0h] [rbp-9A8h]
  int v197; // [rsp+B4h] [rbp-9A4h]
  __int64 v198; // [rsp+B8h] [rbp-9A0h] BYREF
  __int64 v199; // [rsp+C0h] [rbp-998h] BYREF
  const unsigned __int16 *v200; // [rsp+C8h] [rbp-990h]
  HKEY hKey; // [rsp+D0h] [rbp-988h] BYREF
  unsigned __int16 *v202; // [rsp+D8h] [rbp-980h]
  unsigned __int16 *v203; // [rsp+E0h] [rbp-978h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-970h] BYREF
  VARIANTARG v205; // [rsp+100h] [rbp-958h] BYREF
  VARIANTARG v206; // [rsp+120h] [rbp-938h] BYREF
  DWORD cbData[2]; // [rsp+140h] [rbp-918h] BYREF
  unsigned int v208; // [rsp+148h] [rbp-910h] BYREF
  unsigned __int16 *v209; // [rsp+150h] [rbp-908h]
  __int64 v210; // [rsp+158h] [rbp-900h] BYREF
  __int64 v211; // [rsp+160h] [rbp-8F8h] BYREF
  int v212; // [rsp+168h] [rbp-8F0h] BYREF
  int v213; // [rsp+16Ch] [rbp-8ECh] BYREF
  void *v214[2]; // [rsp+170h] [rbp-8E8h] BYREF
  __int64 v215; // [rsp+180h] [rbp-8D8h] BYREF
  __int64 (__fastcall ***v216)(_QWORD, DCMetaData *, __int64, __int64 *); // [rsp+188h] [rbp-8D0h]
  char v217[8]; // [rsp+190h] [rbp-8C8h] BYREF
  unsigned __int16 *v218; // [rsp+198h] [rbp-8C0h]
  VARIANTARG v219; // [rsp+1A0h] [rbp-8B8h] BYREF
  char v220[8]; // [rsp+1B8h] [rbp-8A0h] BYREF
  char v221[8]; // [rsp+1C0h] [rbp-898h] BYREF
  char v222[8]; // [rsp+1C8h] [rbp-890h] BYREF
  char v223[8]; // [rsp+1D0h] [rbp-888h] BYREF
  char v224[8]; // [rsp+1D8h] [rbp-880h] BYREF
  char v225[8]; // [rsp+1E0h] [rbp-878h] BYREF
  char v226[8]; // [rsp+1E8h] [rbp-870h] BYREF
  char v227[8]; // [rsp+1F0h] [rbp-868h] BYREF
  char v228[8]; // [rsp+1F8h] [rbp-860h] BYREF
  char v229[8]; // [rsp+200h] [rbp-858h] BYREF
  char v230[8]; // [rsp+208h] [rbp-850h] BYREF
  char v231[8]; // [rsp+210h] [rbp-848h] BYREF
  char v232[8]; // [rsp+218h] [rbp-840h] BYREF
  char v233[8]; // [rsp+220h] [rbp-838h] BYREF
  char v234[8]; // [rsp+228h] [rbp-830h] BYREF
  char v235[8]; // [rsp+230h] [rbp-828h] BYREF
  char v236[8]; // [rsp+238h] [rbp-820h] BYREF
  struct DCDocument *v237; // [rsp+240h] [rbp-818h]
  __int64 v238; // [rsp+248h] [rbp-810h] BYREF
  char v239[8]; // [rsp+250h] [rbp-808h] BYREF
  char v240[8]; // [rsp+258h] [rbp-800h] BYREF
  char v241[8]; // [rsp+260h] [rbp-7F8h] BYREF
  char v242[8]; // [rsp+268h] [rbp-7F0h] BYREF
  char v243[8]; // [rsp+270h] [rbp-7E8h] BYREF
  char v244[8]; // [rsp+278h] [rbp-7E0h] BYREF
  char v245[8]; // [rsp+280h] [rbp-7D8h] BYREF
  char v246[8]; // [rsp+288h] [rbp-7D0h] BYREF
  char v247[8]; // [rsp+290h] [rbp-7C8h] BYREF
  char v248[8]; // [rsp+298h] [rbp-7C0h] BYREF
  __int64 v249; // [rsp+2A0h] [rbp-7B8h]
  char v250[8]; // [rsp+2A8h] [rbp-7B0h] BYREF
  _BYTE *v251; // [rsp+2B0h] [rbp-7A8h]
  _BYTE *v252; // [rsp+2B8h] [rbp-7A0h]
  char v253[16]; // [rsp+2C0h] [rbp-798h] BYREF
  _BYTE v254[32]; // [rsp+2D0h] [rbp-788h] BYREF
  _BYTE v255[32]; // [rsp+2F0h] [rbp-768h] BYREF
  _BYTE v256[32]; // [rsp+310h] [rbp-748h] BYREF
  OLECHAR *psz[3]; // [rsp+330h] [rbp-728h] BYREF
  unsigned __int64 v258; // [rsp+348h] [rbp-710h]
  OLECHAR *v259[3]; // [rsp+350h] [rbp-708h] BYREF
  unsigned __int64 v260; // [rsp+368h] [rbp-6F0h]
  unsigned __int16 *v261[3]; // [rsp+370h] [rbp-6E8h] BYREF
  unsigned __int64 v262; // [rsp+388h] [rbp-6D0h]
  _QWORD v263[3]; // [rsp+390h] [rbp-6C8h] BYREF
  unsigned __int64 v264; // [rsp+3A8h] [rbp-6B0h]
  char v265[32]; // [rsp+3B0h] [rbp-6A8h] BYREF
  __int64 *v266; // [rsp+3D0h] [rbp-688h] BYREF
  HKEY v267; // [rsp+3D8h] [rbp-680h] BYREF
  char v268; // [rsp+3E0h] [rbp-678h]
  DWORD v269[8]; // [rsp+3F0h] [rbp-668h] BYREF
  char v270[64]; // [rsp+410h] [rbp-648h] BYREF
  char v271[656]; // [rsp+450h] [rbp-608h] BYREF
  unsigned __int16 v272[16]; // [rsp+6E0h] [rbp-378h] BYREF
  char v273[64]; // [rsp+700h] [rbp-358h] BYREF
  char v274[656]; // [rsp+740h] [rbp-318h] BYREF
  _DWORD v275[2]; // [rsp+9D0h] [rbp-88h] BYREF
  const wchar_t *v276; // [rsp+9D8h] [rbp-80h]
  const OLECHAR *v277; // [rsp+9E0h] [rbp-78h]
  const wchar_t *v278; // [rsp+9E8h] [rbp-70h]
  int v279; // [rsp+9F0h] [rbp-68h]
  int v280; // [rsp+9F4h] [rbp-64h]
  __int64 v281; // [rsp+9F8h] [rbp-60h]
  __int128 v282; // [rsp+A00h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+A58h] [rbp+0h]

  v6 = a4;
  v200 = a4;
  v7 = a3;
  v202 = a3;
  v186 = a2;
  v8 = a1;
  v249 = a1;
  v218 = a5;
  LODWORD(v184) = 0;
  std::list<std::wstring>::list<std::wstring>(v214);
  v208 = 0;
  OrchestratorDCInfo::OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  v212 = 0;
  v213 = 0;
  v238 = 0;
  if ( v7 )
  {
    if ( v6 )
    {
      if ( !a5 )
      {
        v10 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB5,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)0x80070057LL,
          lpDataa);
        goto LABEL_379;
      }
      *(_OWORD *)&v206.vt = 0;
      LODWORD(v184) = OrchestratorDBManager::FindRequest(v9, v7, a5, v6, (struct _GUID *)&v206);
      if ( (int)v184 < 0 )
      {
LABEL_14:
        Logger = CDeclaredConfigurationLogger::GetLogger();
        v17 = L"OrchestratorIDatabaseManagerSingleton::instance().GetAllRequests(requestIds)";
        goto LABEL_377;
      }
      v11 = GUIDToStringWithoutBracket_0(&v206, v275);
      v10 = v11;
      if ( v11 < 0 )
      {
        v12 = "failed to convert GUID to string with no bracket";
        v13 = 2753;
LABEL_8:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)(unsigned int)v10,
          (int)v12,
          lpcbData);
        goto LABEL_379;
      }
      try
      {
        std::wstring::wstring((__int64)&v266, (__int64)v275);
        std::list<std::wstring>::push_back(v214, &v266);
        std::wstring::_Tidy_deallocate(&v266);
        AllRequestsPerEnrollment = (int)v184;
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAC8,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
          (const char *)0x8007000ELL,
          lpData);
        goto LABEL_9;
      }
      goto LABEL_13;
    }
    AllRequestsPerEnrollment = OrchestratorDBManager::GetAllRequestsPerEnrollment(v9, v7, v214);
  }
  else
  {
    AllRequestsPerEnrollment = OrchestratorDBManager::GetAllRequests(v9, v214);
  }
  LODWORD(v184) = AllRequestsPerEnrollment;
LABEL_13:
  if ( AllRequestsPerEnrollment < 0 )
    goto LABEL_14;
  if ( !v214[1] )
  {
    v18 = DeclaredConfigurationStore_DeleteScheduledTask(v15, v7);
    if ( (int)(v18 + 0x80000000) >= 0 && v18 != -2147024894 )
    {
      v19 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v19,
        L"DCEngine::ReconstructQueueAndExecute",
        L"DeclaredConfigurationStore_DeleteScheduledTask(DECLARED_CONFIGURATION_REFRESH_ID)",
        &word_180142E98,
        v18);
    }
    v20 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
      v20,
      L"DCEngine::ReconstructQueueAndExecute",
      L"No requests for Orchestrator, delete DC schedule task",
      &word_180142E98);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v21,
        (unsigned int)OrchestratorGenericInformation,
        (unsigned int)L"DCEngine::ReconstructQueueAndExecute",
        (unsigned int)L"No requests for Orchestrator, delete DC schedule task",
        0);
    goto LABEL_378;
  }
  v216 = *(__int64 (__fastcall ****)(_QWORD, DCMetaData *, __int64, __int64 *))&qword_18018A6C8;
  if ( !*(_QWORD *)&qword_18018A6C8 )
  {
    InitOrchestratorEngine();
    v216 = *(__int64 (__fastcall ****)(_QWORD, DCMetaData *, __int64, __int64 *))&qword_18018A6C8;
    if ( !*(_QWORD *)&qword_18018A6C8 )
    {
      v12 = "could not get DC OrchestratorEngine";
      v10 = -2147467259;
      v13 = 2814;
      goto LABEL_8;
    }
  }
  v22 = (char *)v214[0];
  v23 = *(char **)v214[0];
  while ( v23 != v22 )
  {
    v188 = v8 + 224;
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 224));
    v24 = (unsigned __int16 *)(v23 + 16);
    v209 = (unsigned __int16 *)(v23 + 16);
    if ( *((_QWORD *)v23 + 5) > 7u )
    {
      v24 = *(unsigned __int16 **)v24;
      v209 = v24;
    }
    *(_OWORD *)&v206.vt = 0;
    v185 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
    {
      hKey = 0;
      v26 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::ensure_data(&hKey);
      tip2::details::shared_data<0,0,0>::start(*v26 + 8LL, v253);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::operator=(
        &v185,
        &hKey);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(&hKey);
      v27 = tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
              &v185,
              v239);
      *(_BYTE *)(*(_QWORD *)v27 + 272LL) = v186;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v239);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                               &v185,
                               v243)
                + 276LL) = a6;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v243);
      v28 = -2128831035;
      if ( v24 )
      {
        v29 = *v24;
        if ( *v24 )
        {
          v30 = v24;
          do
          {
            ++v30;
            v28 = 16777619 * (v28 ^ v29);
            v29 = *v30;
          }
          while ( *v30 );
        }
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                               &v185,
                               v244)
                + 284LL) = v28;
      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v244);
    }
    v192[0] = &v185;
    v192[1] = &v184;
    v193 = 1;
    LODWORD(v184) = OrchestratorDBManager::GetRequest(
                      v25,
                      v24,
                      (struct OrchestratorDCInfo *)psz,
                      (enum StateMachineTypeTag *)&v208,
                      (enum DMOrchestratorState *)&v212,
                      (enum DCLifecycleNotificationType *)&v213);
    if ( (int)v184 < 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
      {
        v31 = (int)v184;
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                 &v185,
                                 v245)
                  + 296LL) = v31;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v245);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                 &v185,
                                 v246)
                  + 280LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v246);
      }
      v272[0] = 0;
      if ( StringCchPrintfW(v272, 0x104u, L"ScenarioId: %s", v24) >= 0 && byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v32,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"ReconstructQueueAndExecute:OrchestratorIDatabaseManagerSingleton::instance().OrchestratorDBManag"
                         "er::GetRequest(scenarioId, &dcInfo, &statemachineType, &state, &notificationState)",
          (unsigned int)v272,
          (char)v184);
      if ( (int)GetGuidFromEnrollmentId(v24, (struct _GUID *)&v206) >= 0 )
      {
        LODWORD(v184) = OrchestratorDBManager::DeleteRequest(v33, (struct _GUID *)&v206);
        v34 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v34,
          L"DCEngine::ReconstructQueueAndExecute",
          L"DeleteRequest",
          v24,
          (int)v184);
      }
      goto LABEL_67;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
    {
      v35 = -2128831035;
      if ( v262 > 7 )
      {
        v36 = (unsigned __int16 **)v261[0];
        if ( v261[0] )
        {
          v37 = (unsigned __int16 **)v261[0];
LABEL_48:
          for ( i = *(_WORD *)v37; i; i = *(_WORD *)v36 )
          {
            v36 = (unsigned __int16 **)((char *)v36 + 2);
            v35 = 16777619 * (v35 ^ i);
          }
        }
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                 &v185,
                                 v247)
                  + 288LL) = v35;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v247);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationScenarioDefinitionIngestion>::GetImpl'::`2'::impl) )
        {
          v39 = v261;
          if ( v262 > 7 )
            v39 = (unsigned __int16 **)v261[0];
          v40 = (char **)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                       &v185,
                                       v248)
                        + 304LL);
          v41 = -1;
          do
            ++v41;
          while ( *((_WORD *)v39 + v41) );
          std::wstring::_Assign<unsigned short>(v40, v39, (char *)v41);
          tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v248);
        }
        goto LABEL_57;
      }
      v37 = v261;
      v36 = v261;
      goto LABEL_48;
    }
LABEL_57:
    if ( !v7 )
      goto LABEL_64;
    v42 = psz;
    if ( v258 > 7 )
      v42 = (OLECHAR **)psz[0];
    if ( (unsigned int)_o__wcsicmp(v42, v7) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
      {
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                 &v185,
                                 v250)
                  + 280LL) = 2;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v250);
      }
    }
    else
    {
LABEL_64:
      if ( v213 != 5 )
      {
        *(_OWORD *)v195 = 0;
        v196 = 0;
        v197 = 63;
        v187 = 0;
        v43 = (const OLECHAR *)psz;
        if ( v258 > 7 )
          v43 = psz[0];
        *(_QWORD *)v195 = SysAllocString(v43);
        if ( !*(_QWORD *)v195 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB6C,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
            (const char *)0x8007000ELL,
            lpDatab);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
          v193 = 0;
          lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
          goto LABEL_374;
        }
        v44 = v259;
        if ( v260 > 7 )
          v44 = (OLECHAR **)v259[0];
        if ( (unsigned int)_o__wcsicmp(v44, L"user") )
        {
          v47 = v259;
          if ( v260 > 7 )
            v47 = (OLECHAR **)v259[0];
          if ( !(unsigned int)_o__wcsicmp(v47, L"device") )
          {
            v48 = (const OLECHAR *)v259;
            if ( v260 > 7 )
              v48 = v259[0];
            *(_QWORD *)&v195[2] = SysAllocString(v48);
            if ( !*(_QWORD *)&v195[2] )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB84,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                (const char *)0x8007000ELL,
                lpDatab);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
              DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
              v193 = 0;
              lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
              goto LABEL_374;
            }
            goto LABEL_89;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
          {
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                     &v185,
                                     v242)
                      + 280LL) = 5;
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v242);
          }
          v171 = (const unsigned __int16 *)v261;
          if ( v262 > 7 )
            v171 = v261[0];
          DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v171);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
          {
            v172 = CDeclaredConfigurationLogger::GetLogger();
            v173 = (const unsigned __int16 *)v261;
            if ( v262 > 7 )
              v173 = v261[0];
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v172,
              L"DCEngine::ReconstructQueueAndExecute",
              L"Invalid user context - DeleteCorruptedDocAndRecord",
              v173,
              (int)v184);
          }
        }
        else
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v187,
            0);
          LODWORD(v184) = DmGetActiveUserSid(&v187);
          if ( (int)v184 < 0 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
            {
              *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                       &v185,
                                       v221)
                        + 280LL) = 4;
              tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v221);
            }
            v45 = CDeclaredConfigurationLogger::GetLogger();
            v46 = (const unsigned __int16 *)psz;
            if ( v258 > 7 )
              v46 = psz[0];
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v45,
              L"DCEngine::ReconstructQueueAndExecute",
              L"DmGetActiveUserSid",
              v46,
              (int)v184);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
            v193 = 0;
            lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
            goto LABEL_371;
          }
          *(_QWORD *)&v195[2] = SysAllocString(v187);
          if ( !*(_QWORD *)&v195[2] )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB7E,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
              (const char *)0x8007000ELL,
              lpDatab);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
            v193 = 0;
            lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
LABEL_374:
            wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(&v185);
            gate<critical_section>::~gate<critical_section>(&v188);
LABEL_9:
            v10 = -2147024882;
            goto LABEL_379;
          }
          v196 = 1;
LABEL_89:
          Type[0] = 0;
          v49 = (const unsigned __int16 *)v261;
          if ( v262 > 7 )
            v49 = v261[0];
          v50 = (OLECHAR *)psz;
          if ( v258 > 7 )
            v50 = psz[0];
          LODWORD(v184) = DeclaredConfigurationStore_GetDriftControl(v50, v49, Type);
          if ( (int)v184 < 0 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
            {
              *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                       &v185,
                                       v222)
                        + 280LL) = 6;
              tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v222);
            }
            LODWORD(v184) = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
            DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
            v193 = 0;
            lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
            goto LABEL_371;
          }
          if ( Type[0] )
          {
            if ( v186 )
            {
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl);
              v52 = (const unsigned __int16 *)v261;
              v53 = (OLECHAR *)psz;
              if ( IsEnabled )
                v54 = (v6 != 0) + 1;
              else
                v54 = 1;
              if ( v262 > 7 )
                v52 = v261[0];
              if ( v258 > 7 )
                v53 = psz[0];
              DeclaredConfigurationStore_UpdateRefreshFlag(v53, v52, v54);
            }
            VariantInit(&pvarg);
            pvarg.vt = 3;
            v55 = v263;
            if ( v264 > 7 )
              v55 = (_QWORD *)v263[0];
            v56 = v261;
            if ( v262 > 7 )
              v56 = (unsigned __int16 **)v261[0];
            hKey = 0;
            if ( !v56 || !v55 )
            {
              RegistryMultiString = -2147024809;
              goto LABEL_170;
            }
            *(_QWORD *)&v205.vt = &hKey;
            v205.llVal = 0;
            *((_BYTE *)&v205.decVal + 16) = 1;
            GetResultsEnrollmentIdSidStateDocIdVersionKey_3(v195, v56, v55, &v205.decVal.Lo32);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v205);
            v203 = 0;
            switch ( pvarg.vt )
            {
              case 3u:
                cbData[0] = 0;
                Type[0] = 4;
                v189[0] = 4;
                if ( hKey )
                {
                  Value = RegQueryValueExW(hKey, L"state", 0, Type, (LPBYTE)cbData, v189);
                  RegistryMultiString = Value;
                  if ( Value )
                  {
                    if ( Value > 0 )
                      RegistryMultiString = (unsigned __int16)Value | 0x80070000;
                    v69 = 0;
                    if ( RegistryMultiString < 0 )
                      goto LABEL_150;
                  }
                  else
                  {
                    if ( Type[0] != 4 )
                    {
                      RegistryMultiString = -2147418113;
                      goto LABEL_150;
                    }
                    v69 = cbData[0];
                  }
                  pvarg.vt = 3;
                  pvarg.lVal = v69;
                  goto LABEL_168;
                }
                break;
              case 5u:
                goto LABEL_151;
              case 8u:
                v59 = hKey;
                Type[0] = 1;
                cbData[0] = 0;
                if ( hKey )
                {
                  v60 = 0;
                  v61 = RegQueryValueExW(hKey, L"state", 0, Type, 0, cbData);
                  RegistryMultiString = v61;
                  if ( v61 )
                  {
                    if ( v61 > 0 )
                      RegistryMultiString = (unsigned __int16)v61 | 0x80070000;
                    goto LABEL_145;
                  }
                  if ( Type[0] != 1 )
                  {
                    RegistryMultiString = -2147418113;
                    goto LABEL_136;
                  }
                  v62 = ((unsigned __int64)cbData[0] >> 1) + 1;
                  v63 = 2 * v62;
                  if ( !is_mul_ok(v62, 2u) )
                    v63 = -1;
                  v64 = (BYTE *)operator new[](v63, (const struct std::nothrow_t *)std::nothrow);
                  v65 = v64;
                  if ( !v64 )
                  {
                    RegistryMultiString = -2147024882;
                    v24 = v209;
                    goto LABEL_150;
                  }
                  memset_0(v64, 0, v62);
                  v66 = RegQueryValueExW(v59, L"state", 0, Type, v65, cbData);
                  RegistryMultiString = v66;
                  if ( v66 )
                  {
                    if ( v66 > 0 )
                      RegistryMultiString = (unsigned __int16)v66 | 0x80070000;
                    operator delete(v65);
LABEL_145:
                    if ( RegistryMultiString < 0 )
                    {
LABEL_136:
                      v24 = v209;
                      goto LABEL_150;
                    }
                  }
                  else
                  {
                    v60 = (OLECHAR *)v65;
                  }
                  pvarg.vt = 8;
                  pvarg.llVal = (LONGLONG)SysAllocString(v60);
                  operator delete(v60);
                  v24 = v209;
                  goto LABEL_168;
                }
                break;
              case 0x14u:
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                {
                  *(_QWORD *)v189 = 0;
                  RegistryMultiString = DCGetRegistryQWORD(hKey, v203, L"state", v189);
                  if ( RegistryMultiString < 0 )
                    goto LABEL_150;
                  v58 = 20;
LABEL_129:
                  pvarg.vt = v58;
                  pvarg.llVal = *(_QWORD *)v189;
                  goto LABEL_168;
                }
LABEL_151:
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                  goto LABEL_154;
                *(_QWORD *)v189 = 0;
                RegistryMultiString = DCGetRegistryQWORD(hKey, v203, L"state", v189);
                if ( RegistryMultiString < 0 )
                  goto LABEL_150;
                v58 = 5;
                goto LABEL_129;
              case 0x2008u:
LABEL_154:
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                  goto LABEL_157;
                *(_QWORD *)Type = 0;
                RegistryMultiString = DCCDNUtil_GetRegistryMultiString(
                                        hKey,
                                        v203,
                                        L"state",
                                        (unsigned __int16 **)Type,
                                        v189);
                if ( RegistryMultiString < 0 )
                  goto LABEL_150;
                pvarg.vt = 8200;
                MultiStringToSafeArray(*(OLECHAR **)Type, v67, &pvarg.parray);
                operator delete(*(void **)Type);
LABEL_168:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v203);
                RegistryMultiString = 0;
                goto LABEL_170;
              case 0x2011u:
                *(_QWORD *)v189 = 0;
                Type[0] = 0;
                RegistryMultiString = DCGetRegistryBinary_1(hKey, 0, L"state", v189, Type);
                if ( RegistryMultiString >= 0 )
                {
                  RegistryMultiString = DCInlineSetBinaryToVariant(*(void **)v189, Type[0]);
                  if ( RegistryMultiString >= 0 )
                  {
                    std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(v189);
                    goto LABEL_168;
                  }
                }
                std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(v189);
LABEL_150:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v203);
LABEL_170:
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                LODWORD(v184) = RegistryMultiString;
                if ( RegistryMultiString < 0 )
                {
                  v272[0] = 0;
                  v70 = v263;
                  if ( v264 > 7 )
                    v70 = (_QWORD *)v263[0];
                  v71 = v261;
                  if ( v262 > 7 )
                    v71 = (unsigned __int16 **)v261[0];
                  v72 = v259;
                  if ( v260 > 7 )
                    v72 = (OLECHAR **)v259[0];
                  v73 = psz;
                  if ( v258 > 7 )
                    v73 = (OLECHAR **)psz[0];
                  if ( StringCchPrintfW(
                         v272,
                         0x104u,
                         L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s",
                         v73,
                         v72,
                         v71,
                         v70) >= 0
                    && byte_180189FC1 < 0 )
                  {
                    McTemplateU0zzd_EventWriteTransfer(
                      v74,
                      (unsigned int)OrchestratorGenericFailure,
                      (unsigned int)L"ReconstructQueueAndExecute:DeclaredConfigurationStore_ReadResultData failed",
                      (unsigned int)v272,
                      (char)v184);
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v224)
                              + 280LL) = 61;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v224);
                  }
                  v75 = (const unsigned __int16 *)v261;
                  if ( v262 > 7 )
                    v75 = v261[0];
                  DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v75);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                  {
                    v76 = CDeclaredConfigurationLogger::GetLogger();
                    v77 = (const unsigned __int16 *)v261;
                    if ( v262 > 7 )
                      v77 = v261[0];
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v76,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"DeclaredConfigurationStore_ReadResultData state - DeleteCorruptedDocAndRecord",
                      v77,
                      (int)v184);
                  }
                  LODWORD(v184) = 0;
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                  v193 = 0;
                  lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                  goto LABEL_225;
                }
                Lo = pvarg.cyVal.Lo;
                v191 = 0;
                *(_QWORD *)&v205.vt = &v191;
                v205.llVal = 0;
                *((_BYTE *)&v205.decVal + 16) = 1;
                v79 = v263;
                if ( v264 > 7 )
                  LODWORD(v79) = v263[0];
                v80 = v261;
                if ( v262 > 7 )
                  LODWORD(v80) = v261[0];
                LODWORD(v184) = GetEnrollmentIdSidStateDocIdVersionRawKey_0(
                                  (unsigned int)v195,
                                  (_DWORD)v80,
                                  (_DWORD)v79,
                                  (unsigned int)&v205.cyVal.Lo,
                                  0);
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v205);
                if ( (int)v184 < 0 )
                {
                  v272[0] = 0;
                  v81 = v263;
                  if ( v264 > 7 )
                    v81 = (_QWORD *)v263[0];
                  v82 = v261;
                  if ( v262 > 7 )
                    v82 = (unsigned __int16 **)v261[0];
                  v83 = v259;
                  if ( v260 > 7 )
                    v83 = (OLECHAR **)v259[0];
                  v84 = psz;
                  if ( v258 > 7 )
                    v84 = (OLECHAR **)psz[0];
                  if ( StringCchPrintfW(
                         v272,
                         0x104u,
                         L"enrollmentId: %s, context:%s, docId:%s, docVersion:%s",
                         v84,
                         v83,
                         v82,
                         v81) >= 0 )
                  {
                    v85 = CDeclaredConfigurationLogger::GetLogger();
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v85,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"GetEnrollmentIdSidStateDocIdVersionRawKey",
                      v272,
                      (int)v184);
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v225)
                              + 280LL) = 62;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v225);
                  }
                  v86 = (const unsigned __int16 *)v261;
                  if ( v262 > 7 )
                    v86 = v261[0];
                  DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v86);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                  {
                    v87 = CDeclaredConfigurationLogger::GetLogger();
                    v88 = (const unsigned __int16 *)v261;
                    if ( v262 > 7 )
                      v88 = v261[0];
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v87,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"GetEnrollmentIdSidStateDocIdVersionRawKey - DeleteCorruptedDocAndRecord",
                      v88,
                      (int)v184);
                  }
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                  v193 = 0;
                  lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                  goto LABEL_225;
                }
                v194 = 0;
                *(_QWORD *)&v205.vt = &v194;
                v205.llVal = 0;
                *((_BYTE *)&v205.decVal + 16) = 1;
                LODWORD(v184) = DCCDNUtil_GetRegistryString(v191, 0, L"osdefinedscenario", &v205.bstrVal);
                wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v205);
                if ( (int)v184 < 0 )
                {
                  v89 = CDeclaredConfigurationLogger::GetLogger();
                  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                    v89,
                    L"DCEngine::ReconstructQueueAndExecute",
                    L"DCCDNUtil_GetRegistryString(docIdVersionRawRegKey.get(),nullptr, c_szDCOSDefinedScenario, &pszOSDefinedScenario)",
                    &word_180142E98,
                    (int)v184);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v226)
                              + 280LL) = 63;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v226);
                  }
                  v90 = (const unsigned __int16 *)v261;
                  if ( v262 > 7 )
                    v90 = v261[0];
                  DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v90);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                  {
                    v91 = CDeclaredConfigurationLogger::GetLogger();
                    v92 = (const unsigned __int16 *)v261;
                    if ( v262 > 7 )
                      v92 = v261[0];
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v91,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"DCCDNUtil_GetRegistryString osdefinedscenario - DeleteCorruptedDocAndRecord",
                      v92,
                      (int)v184);
                  }
                  goto LABEL_224;
                }
                Type[0] = 0;
                LODWORD(v184) = DCCDNUtil_GetRegistryDWORD(v191, 0, L"behavior", Type);
                if ( (int)v184 < 0 )
                {
                  v93 = CDeclaredConfigurationLogger::GetLogger();
                  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                    v93,
                    L"DCEngine::ReconstructQueueAndExecute",
                    L"DCCDNUtil_GetRegistryDWORD(docIdVersionRawRegKey.get(),nullptr, c_szDCBehavior, &dwBehavior)",
                    &word_180142E98,
                    (int)v184);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v227)
                              + 280LL) = 64;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v227);
                  }
                  v94 = (const unsigned __int16 *)v261;
                  if ( v262 > 7 )
                    v94 = v261[0];
                  DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v94);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                  {
                    v95 = CDeclaredConfigurationLogger::GetLogger();
                    v96 = (const unsigned __int16 *)v261;
                    if ( v262 > 7 )
                      v96 = v261[0];
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v95,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"DCCDNUtil_GetRegistryString behavior - DeleteCorruptedDocAndRecord",
                      v96,
                      (int)v184);
                  }
LABEL_224:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                  v193 = 0;
                  lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
LABEL_225:
                  wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(&v185);
                  gate<critical_section>::~gate<critical_section>(&v188);
                  v7 = v202;
                  v6 = v200;
                  goto LABEL_372;
                }
                v198 = 0;
                v199 = 0;
                *(_QWORD *)&v205.vt = &v198;
                v205.llVal = 0;
                *((_BYTE *)&v205.decVal + 16) = 1;
                v97 = (const unsigned __int16 *)v261;
                if ( v262 > 7 )
                  v97 = v261[0];
                LODWORD(v184) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                  (struct DeclaredConfigurationScopeData *)v195,
                                  v97,
                                  (HKEY *)&v205.llVal,
                                  0);
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v205);
                if ( (int)v184 < 0 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v228)
                              + 280LL) = 65;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v228);
                  }
                  v98 = (const unsigned __int16 *)v261;
                  if ( v262 > 7 )
                    v98 = v261[0];
                  DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v98);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                  {
                    v99 = CDeclaredConfigurationLogger::GetLogger();
                    v100 = (const unsigned __int16 *)v261;
                    if ( v262 > 7 )
                      v100 = v261[0];
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v99,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey - DeleteCorruptedDocAndRecord",
                      v100,
                      (int)v184);
                  }
LABEL_247:
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                  DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                  v193 = 0;
                  lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                  goto LABEL_225;
                }
                *(_QWORD *)&v205.vt = &v199;
                v205.llVal = 0;
                *((_BYTE *)&v205.decVal + 16) = 1;
                v101 = std::wstring::c_str(v261);
                LODWORD(v184) = GetResultsEnrollmentIdSidStateDocIdKey_0(v195, v101, &v205.decVal.Lo32);
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v205);
                if ( (int)v184 < 0 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v229)
                              + 280LL) = 66;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v229);
                  }
                  v102 = (const unsigned __int16 *)std::wstring::c_str(v261);
                  DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v24, v102);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                  {
                    CDeclaredConfigurationLogger::GetLogger();
                    v103 = (const unsigned __int16 *)std::wstring::c_str(v261);
                    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                      v104,
                      L"DCEngine::ReconstructQueueAndExecute",
                      L"GetResultsEnrollmentIdSidStateDocIdKey - DeleteCorruptedDocAndRecord",
                      v103,
                      (int)v184);
                  }
                  goto LABEL_247;
                }
                DCDocument::DCDocument((DCDocument *)v269);
                std::wstring::operator=(v269, v261);
                std::wstring::operator=(v270, v259);
                std::wstring::operator=(v271, v263);
                v105 = std::wstring::c_str(v263);
                LODWORD(v184) = DeclaredConfigurationStore_GetPersistedDocument(v195, v198, v105, 0, v269, 1);
                v107 = Type[0];
                if ( (int)v184 < 0 && (Type[0] & 0x20) == 0
                  || (v108 = std::wstring::c_str(v263),
                      LODWORD(v184) = DeclaredConfigurationStore_GetPersistedDocument(v195, v198, v108, 0, v269, 2),
                      (int)v184 < 0)
                  || (v109 = std::wstring::c_str(v263),
                      LODWORD(v184) = DeclaredConfigurationStore_GetPersistedDocument(v195, v199, v109, 0, v269, 3),
                      (int)v184 < 0) )
                {
                  LOBYTE(v106) = 1;
                  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DocumentDeletionTransientErrorHandling>::ReportUsage(
                    `wil::Feature<__WilFeatureTraits_Feature_Servicing_DocumentDeletionTransientErrorHandling>::GetImpl'::`2'::impl,
                    v106);
                  VariantInit(&v205);
                  v205.vt = 3;
                  std::wstring::c_str(v263);
                  v110 = std::wstring::c_str(v261);
                  if ( (int)DeclaredConfigurationStore_ReadResultData_3(
                              (int)v195,
                              v110,
                              v111,
                              v112,
                              lpDatac,
                              lpcbDataa,
                              L"state",
                              (DWORD)&v205) < 0
                    || (v205.lVal > 0x24u || (v113 = 0x1DC0000000LL, !_bittest64(&v113, v205.cyVal.Lo)))
                    && (unsigned int)(v205.lVal - 90) > 9 )
                  {
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                    {
                      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                               &v185,
                                               v241)
                                + 280LL) = 67;
                      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v241);
                    }
                    v168 = (const unsigned __int16 *)std::wstring::c_str(v261);
                    DeleteCorruptedDocAndRecord((struct DeclaredConfigurationScopeData *)v195, v209, v168);
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
                    {
                      CDeclaredConfigurationLogger::GetLogger();
                      v169 = (const unsigned __int16 *)std::wstring::c_str(v261);
                      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                        v170,
                        L"DCEngine::ReconstructQueueAndExecute",
                        L"DeclaredConfigurationStore_GetPersistedDocument - DeleteCorruptedDocAndRecord",
                        v169,
                        (int)v184);
                    }
                    VariantClear(&v205);
                    DCDocument::~DCDocument((DCDocument *)v269);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                    VariantClear(&pvarg);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                    DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                    v193 = 0;
                    lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                    goto LABEL_225;
                  }
                  v114 = CDeclaredConfigurationLogger::GetLogger();
                  CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
                    v114,
                    L"DCEngine::ReconstructQueueAndExecute",
                    L"Skipping deletion of due to cdndownload issues",
                    0);
                  v215 = 0;
                  *(_QWORD *)&v206.vt = &v215;
                  v206.llVal = 0;
                  *((_BYTE *)&v206.decVal + 16) = 1;
                  LODWORD(v184) = DCCDNUtil_GetRegistryString(v191, 0, L"downloadGUID", &v206.bstrVal);
                  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v206);
                  if ( (int)v184 >= 0 )
                    CDNDownload_SetDownloadState(v215, 1);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v215);
                  VariantClear(&v205);
                }
                if ( (unsigned int)(Lo - 5) <= 1 )
                {
                  v115 = 0;
                  VariantInit(&v219);
                  v219.vt = 3;
                  std::wstring::c_str(v263);
                  v116 = std::wstring::c_str(v261);
                  LODWORD(v184) = DeclaredConfigurationStore_ReadResultData_3(
                                    (int)v195,
                                    v116,
                                    v117,
                                    v118,
                                    lpDatac,
                                    lpcbDataa,
                                    L"curTickCount",
                                    (DWORD)&v219);
                  if ( (int)v184 >= 0 && GetTickCount() < v219.lVal )
                  {
                    std::wstring::c_str(v263);
                    v119 = std::wstring::c_str(v261);
                    LODWORD(v184) = DeclaredConfigurationStore_DeleteResultData_0(
                                      (unsigned int)v195,
                                      v119,
                                      v120,
                                      v121,
                                      (__int64)lpDatad);
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl)
                      && (int)v184 < 0 )
                    {
                      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                               &v185,
                                               v230)
                                + 280LL) = 20;
                      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v230);
                    }
                    v123 = (int)v184;
                    if ( (int)v184 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xD18,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                        (const char *)(unsigned int)v184,
                        lpDatae);
                      VariantClear(&v219);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(&v185);
                      gate<critical_section>::~gate<critical_section>(&v188);
                      v10 = v123;
                      goto LABEL_379;
                    }
                    v115 = 1;
                    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
                      McTemplateU0zzd_EventWriteTransfer(
                        v122,
                        (unsigned int)OrchestratorGenericInformation,
                        (unsigned int)L"ReconstructQueueAndExecute",
                        (unsigned int)L"CurTickCount is less than previous Curcount, indicating a reboot has happened",
                        0);
                  }
                  v211 = 0;
                  *(_QWORD *)&v205.vt = &v211;
                  v205.llVal = 0;
                  *((_BYTE *)&v205.decVal + 16) = 1;
                  v124 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, qword_18018A680, 0, 0x20119u, (PHKEY)&v205.llVal);
                  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v205);
                  if ( v115 || v124 == 2 )
                  {
                    if ( v124 == 2
                      && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
                    {
                      McTemplateU0zzd_EventWriteTransfer(
                        v125,
                        (unsigned int)OrchestratorGenericInformation,
                        (unsigned int)L"ReconstructQueueAndExecute",
                        (unsigned int)L"Volatile key is gone, indicating a reboot has happened",
                        0);
                    }
                    VariantInit(&v206);
                    v206.vt = 3;
                    v126 = 60;
                    if ( (_DWORD)Lo == 5 )
                      v126 = 63;
                    v206.lVal = v126;
                    std::wstring::c_str(v263);
                    v127 = (const unsigned __int16 *)std::wstring::c_str(v261);
                    LODWORD(v184) = DeclaredConfigurationStore_WriteResultData(
                                      (struct DeclaredConfigurationScopeData *)v195,
                                      v127,
                                      v128,
                                      0,
                                      0,
                                      0,
                                      L"state",
                                      &v206);
                    if ( (int)v184 < 0 )
                    {
                      v129 = CDeclaredConfigurationLogger::GetLogger();
                      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                        v129,
                        L"DCEngine::ReconstructQueueAndExecute",
                        L"DeclaredConfigurationStore_WriteResultData",
                        L"Update doc result to DCCSPURIState::ConfigCompletedSuccessNoRefresh",
                        (int)v184);
                      std::wstring::c_str(v263);
                      std::wstring::c_str(v261);
                      v130 = (const char *)std::wstring::c_str(psz);
                      wil::details::in1diag3::Log_IfFailedMsg(
                        retaddr,
                        (void *)0xD43,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                        (const char *)(unsigned int)v184,
                        (int)"failed to update doc result to ConfigCompletedSuccessNoRefresh for enrollment %ws doc %ws version %ws",
                        v130,
                        v131,
                        v132);
                      LODWORD(v184) = 0;
                    }
                    v210 = 0;
                    v266 = &v210;
                    v267 = 0;
                    v268 = 1;
                    v133 = (const unsigned __int16 *)std::wstring::c_str(v261);
                    LODWORD(v184) = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                      (struct DeclaredConfigurationScopeData *)v195,
                                      v133,
                                      &v267,
                                      0);
                    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v266);
                    if ( (int)v184 < 0 )
                    {
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                      {
                        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                                 &v185,
                                                 v231)
                                  + 280LL) = 14;
                        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v231);
                      }
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v210);
                      VariantClear(&v206);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v211);
                      VariantClear(&v219);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_225;
                    }
                    DCDocument::DCDocument((DCDocument *)v272);
                    std::wstring::operator=(v272, v261);
                    std::wstring::operator=(v273, v259);
                    std::wstring::operator=(v274, v263);
                    v134 = std::wstring::c_str(v263);
                    LODWORD(v184) = DeclaredConfigurationStore_GetPersistedDocument(v195, v210, v134, 0, v272, 2);
                    if ( (int)v184 < 0 )
                    {
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                      {
                        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                                 &v185,
                                                 v232)
                                  + 280LL) = 15;
                        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v232);
                      }
                      if ( byte_180189FC1 < 0 )
                        McTemplateU0zzd_EventWriteTransfer(
                          v135,
                          (unsigned int)OrchestratorGenericFailure,
                          (unsigned int)L"DCEngine::ReconstructQueueAndExecute",
                          (unsigned int)L"DeclaredConfigurationStore_GetPersistedDocument",
                          (char)v184);
                      DCDocument::~DCDocument((DCDocument *)v272);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v210);
                      VariantClear(&v206);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v211);
                      VariantClear(&v219);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_225;
                    }
                    VariantInit(&v205);
                    v205.vt = 3;
                    v205.lVal = Lo;
                    updated = DeclaredConfiguration_UpdateAllCspUriState(
                                (struct DeclaredConfigurationScopeData *)v195,
                                (struct DCDocument *)v272,
                                &v206,
                                &v205);
                    LODWORD(v184) = updated;
                    if ( updated < 0 )
                    {
                      if ( byte_180189FC1 < 0 )
                        McTemplateU0zzd_EventWriteTransfer(
                          v137,
                          (unsigned int)OrchestratorGenericFailure,
                          (unsigned int)L"DCEngine::ReconstructQueueAndExecute",
                          (unsigned int)L"DeclaredConfiguration_UpdateAllCspUriState: failed to update csp/uri state",
                          updated);
                      LODWORD(v184) = 0;
                    }
                    v281 = 0;
                    v282 = 0;
                    v275[0] = 64;
                    v275[1] = 1226;
                    v280 = 2;
                    v276 = L"com.microsoft:mdm.declaredconfiguration.deviceaction.rebootcompleted";
                    v278 = L"reboot completed for device action or policies";
                    v277 = &word_180142E98;
                    v279 = 1;
                    lpDatac = 48;
                    v138 = OmaDmSendAlertNotification3(*(_QWORD *)v195, 0, v275, 1);
                    if ( v138 < 0 )
                    {
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                      {
                        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                                 &v185,
                                                 v233)
                                  + 296LL) = v138;
                        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v233);
                        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                                 &v185,
                                                 v234)
                                  + 280LL) = 16;
                        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v234);
                      }
                      VariantClear(&v205);
                      DCDocument::~DCDocument((DCDocument *)v272);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v210);
                      VariantClear(&v206);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v211);
                      VariantClear(&v219);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_225;
                    }
                    Lo = 63;
                    VariantClear(&v205);
                    DCDocument::~DCDocument((DCDocument *)v272);
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v210);
                    VariantClear(&v206);
                  }
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v211);
                  VariantClear(&v219);
                }
                if ( v208 == 63 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                  {
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v240)
                              + 280LL) = 18;
                    v141 = v240;
LABEL_354:
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v141);
                  }
                }
                else
                {
                  v139 = v186;
                  if ( (!v186 || (_DWORD)Lo == 63 || (v107 & 0x29) != 0)
                    && ((LOBYTE(v106) = 1,
                         wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
                           `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
                           v106),
                         !v139)
                     || (unsigned int)Lo < 0x3C
                     || (_DWORD)Lo == 63
                     || (_DWORD)Lo == 65
                     || (v107 & 8) != 0
                     || (v107 & 0x21) == 0)
                    && (unsigned int)(v212 - 1) > 1
                    && ((unsigned int)Lo > 0x3B || (v140 = 0xFFFFFFFBFEFFBF5LL, !_bittest64(&v140, Lo))) )
                  {
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                    {
                      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                               &v185,
                                               v235)
                                + 280LL) = 19;
                      tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v235);
                      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                               &v185,
                                               v236)
                                + 292LL) = Lo;
                      v141 = v236;
                      goto LABEL_354;
                    }
                  }
                  else if ( !a6 || (_DWORD)Lo == a6 )
                  {
                    *(_QWORD *)v189 = 0;
                    v237 = (struct DCDocument *)operator new(0x388u, (const struct std::nothrow_t *)std::nothrow);
                    if ( v237 )
                    {
                      hKey = (HKEY)&v266;
                      v142 = std::wstring::wstring((__int64)&v266, v194);
                      *(_QWORD *)Type = &v205;
                      v143 = std::wstring::c_str(v265);
                      v144 = std::wstring::wstring((__int64)&v205, v143);
                      *(_QWORD *)cbData = v254;
                      v145 = std::wstring::c_str(v263);
                      v146 = (unsigned __int16 *)std::wstring::wstring((__int64)v254, v145);
                      v251 = v255;
                      v147 = std::wstring::c_str(v261);
                      v148 = (unsigned __int16 *)std::wstring::wstring((__int64)v255, v147);
                      v252 = v256;
                      v149 = std::wstring::c_str(v259);
                      v150 = (unsigned __int16 *)std::wstring::wstring((__int64)v256, v149);
                      v151 = std::wstring::c_str(psz);
                      v152 = (unsigned __int16 *)std::wstring::wstring((__int64)v275, v151);
                      v153 = DCMetaData::DCMetaData(v237, v152, v150, v148, v146, v144, v142);
                    }
                    else
                    {
                      v153 = 0;
                    }
                    std::unique_ptr<DCMetaData>::reset(v189, v153);
                    v154 = *(DCMetaData **)v189;
                    if ( !*(_QWORD *)v189 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xE51,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\core\\dcengine.cpp",
                        (const char *)0x8007000ELL,
                        lpDatac);
                      std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(v189);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_374;
                    }
                    LODWORD(v184) = DCMetaData::set_Key(*(DCMetaData **)v189, v209);
                    if ( (int)v184 < 0 )
                    {
                      v167 = CDeclaredConfigurationLogger::GetLogger();
                      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                        v167,
                        L"DCEngine::ReconstructQueueAndExecute",
                        L"meta->set_Key",
                        &word_180142E98,
                        (int)v184);
                      v10 = (int)v184;
                      std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(v189);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_350;
                    }
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
                    {
                      v155 = v200;
                      if ( !v200 )
                      {
                        LODWORD(v184) = DCMetaData::CreateNotifEventHandle(v154);
                        if ( (int)v184 < 0 )
                        {
LABEL_329:
                          v156 = CDeclaredConfigurationLogger::GetLogger();
                          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                            v156,
                            L"DCEngine::ReconstructQueueAndExecute",
                            L"meta->CreateNotifEventHandle",
                            &word_180142E98,
                            (int)v184);
                          v10 = (int)v184;
                          std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(v189);
                          DCDocument::~DCDocument((DCDocument *)v269);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                          VariantClear(&pvarg);
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                          DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                          v193 = 0;
                          lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
LABEL_350:
                          wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(&v185);
                          gate<critical_section>::~gate<critical_section>(&v188);
                          goto LABEL_379;
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v184) = DCMetaData::CreateNotifEventHandle(v154);
                      if ( (int)v184 < 0 )
                        goto LABEL_329;
                      v155 = v200;
                    }
                    *((_DWORD *)v154 + 218) = 3;
                    LODWORD(v184) = 0;
                    v157 = v216;
                    LODWORD(v184) = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, DCMetaData *, __int64, __int64 *), _QWORD))(*v216)[6])(
                                      v216,
                                      v208);
                    if ( (int)v184 < 0 )
                    {
                      v166 = CDeclaredConfigurationLogger::GetLogger();
                      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                        v166,
                        L"DCEngine::ReconstructQueueAndExecute",
                        L"engine->SetStateMachine",
                        &word_180142E98,
                        (int)v184);
                      v10 = (int)v184;
                      std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(v189);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_350;
                    }
                    LOBYTE(v158) = 1;
                    LODWORD(v184) = (**v157)(v157, v154, v158, &v238);
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl)
                      && (_DWORD)v184 == -2147024713 )
                    {
                      if ( v155 )
                      {
                        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
                          McTemplateU0zzztd_EventWriteTransfer(
                            v159,
                            (unsigned int)OrchestratorEnqueueRequestInformation,
                            (_DWORD)v202,
                            (_DWORD)v155,
                            (__int64)v218,
                            1,
                            183);
                        LODWORD(v184) = 1;
                      }
                      else
                      {
                        v160 = CDeclaredConfigurationLogger::GetLogger();
                        v161 = v218;
                        v162 = (int)v202;
                        CDeclaredConfigurationLogger::LogOrchestratorEnqueueRequestFailure(
                          v160,
                          v202,
                          0,
                          v218,
                          lpDatac,
                          (int)v184);
                        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
                          McTemplateU0zzztd_EventWriteTransfer(
                            v163,
                            (unsigned int)OrchestratorEnqueueRequestFailure,
                            v162,
                            0,
                            (__int64)v161,
                            1,
                            (char)v184);
                      }
                    }
                    if ( (int)v184 < 0 )
                    {
                      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
                      {
                        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                                 &v185,
                                                 v217)
                                  + 280LL) = 17;
                        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v217);
                      }
                      v164 = CDeclaredConfigurationLogger::GetLogger();
                      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                        v164,
                        L"DCEngine::ReconstructQueueAndExecute",
                        L"engine->ConfigDC",
                        &word_180142E98,
                        (int)v184);
                      if ( byte_180189FC1 < 0 )
                        McTemplateU0zzd_EventWriteTransfer(
                          v165,
                          (unsigned int)OrchestratorGenericFailure,
                          (unsigned int)L"ReconstructQueueAndExecute",
                          (unsigned int)L"engine->ConfigDC",
                          (char)v184);
                      v10 = (int)v184;
                      std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(v189);
                      DCDocument::~DCDocument((DCDocument *)v269);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                      DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                      v193 = 0;
                      lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                      goto LABEL_350;
                    }
                    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                             &v185,
                                             v217)
                              + 280LL) = 0;
                    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v217);
                    std::unique_ptr<DCMetaData>::~unique_ptr<DCMetaData>(v189);
                  }
                }
                DCDocument::~DCDocument((DCDocument *)v269);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v199);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v198);
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v194);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v191);
                VariantClear(&pvarg);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
                DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
                v193 = 0;
                lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
                goto LABEL_225;
              default:
LABEL_157:
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v203);
                RegistryMultiString = -2147418113;
                goto LABEL_170;
            }
            RegistryMultiString = -2147024809;
            goto LABEL_150;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
          {
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                     &v185,
                                     v223)
                      + 280LL) = 7;
            tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v223);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v187);
        DeclaredConfigurationScopeData::~DeclaredConfigurationScopeData((DeclaredConfigurationScopeData *)v195);
        v193 = 0;
        lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
        goto LABEL_371;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl'::`2'::impl) )
      {
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(
                                 &v185,
                                 v220)
                  + 280LL) = 3;
        tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(v220);
      }
    }
LABEL_67:
    v193 = 0;
    lambda_96645691a4f9f14f5f9ebf9f7ade5e88_::operator()(v192);
LABEL_371:
    wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(&v185);
    gate<critical_section>::~gate<critical_section>(&v188);
LABEL_372:
    v23 = *(char **)v23;
    v22 = (char *)v214[0];
    v8 = v249;
  }
  v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, DCMetaData *, __int64, __int64 *)))(*v216)[7])(v216);
  LODWORD(v184) = v10;
  if ( v10 >= 0 )
    goto LABEL_379;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  v17 = L"engine->StartExecutionThreadIfNotRunning";
LABEL_377:
  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
    Logger,
    L"DCEngine::ReconstructQueueAndExecute",
    v17,
    &word_180142E98,
    (int)v184);
LABEL_378:
  v10 = (int)v184;
LABEL_379:
  OrchestratorDCInfo::~OrchestratorDCInfo((OrchestratorDCInfo *)psz);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v174,
    v214[0]);
  std::_Deallocate<16>(v214[0], 0x30u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18011440c  mov     [rsp+arg_0], rbx
0x180114411  mov     [rsp+arg_8], rsi
0x180114416  push    rdi
0x180114417  push    r12
0x180114419  push    r13
0x18011441b  push    r14
0x18011441d  push    r15
0x18011441f  sub     rsp, 0A30h
0x180114426  mov     rax, cs:__security_cookie
0x18011442d  xor     rax, rsp
0x180114430  mov     [rsp+0A58h+var_38], rax
0x180114438  mov     r15, r9
0x18011443b  mov     [rsp+0A58h+var_990], r9
0x180114443  mov     rsi, r8
0x180114446  mov     [rsp+0A58h+var_980], r8
0x18011444e  mov     [rsp+0A58h+var_A08], dl
0x180114452  mov     r12, rcx
0x180114455  mov     [rsp+0A58h+var_7B8], rcx
0x18011445d  mov     rbx, [rsp+0A58h+arg_20]
0x180114465  mov     [rsp+0A58h+var_8C0], rbx
0x18011446d  xor     edi, edi
0x18011446f  mov     dword ptr [rsp+0A58h+var_A18], edi
0x180114473  lea     rcx, [rsp+0A58h+var_8E8]
0x18011447b  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180114480  nop
0x180114481  mov     [rsp+0A58h+var_910], edi
0x180114488  lea     rcx, [rsp+0A58h+psz]; this
0x180114490  call    ??0OrchestratorDCInfo@@QEAA@XZ; OrchestratorDCInfo::OrchestratorDCInfo(void)
0x180114495  nop
0x180114496  mov     [rsp+0A58h+var_8F0], edi
0x18011449d  mov     [rsp+0A58h+var_8EC], edi
0x1801144a4  mov     [rsp+0A58h+var_810], rdi
0x1801144ac  test    rsi, rsi
0x1801144af  jz      loc_1801145D3
0x1801144b5  test    r15, r15
0x1801144b8  jz      loc_1801145C1
0x1801144be  test    rbx, rbx
0x1801144c1  jnz     short loc_1801144EA
0x1801144c3  mov     rcx, [rsp+0A58h]; this
0x1801144cb  mov     r13d, 80070057h
0x1801144d1  mov     r9d, r13d; char *
0x1801144d4  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801144db  mov     edx, 0AB5h; void *
0x1801144e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801144e5  jmp     loc_180117835
0x1801144ea  xorps   xmm0, xmm0
0x1801144ed  movups  xmmword ptr [rsp+0A58h+var_938], xmm0
0x1801144f5  lea     rax, [rsp+0A58h+var_938]
0x1801144fd  mov     [rsp+0A58h+lpData], rax; struct _GUID *
0x180114502  mov     r9, r15; unsigned __int16 *
0x180114505  mov     r8, rbx; unsigned __int16 *
0x180114508  mov     rdx, rsi; unsigned __int16 *
0x18011450b  call    ?FindRequest@OrchestratorDBManager@@QEAAJPEBG00PEAU_GUID@@@Z; OrchestratorDBManager::FindRequest(ushort const *,ushort const *,ushort const *,_GUID *)
0x180114510  mov     dword ptr [rsp+0A58h+var_A18], eax
0x180114514  test    eax, eax
0x180114516  js      loc_1801145E8
0x18011451c  movaps  xmm0, xmmword ptr [rsp+0A58h+var_938]
0x180114524  movdqa  xmmword ptr [rsp+0A58h+var_938], xmm0
0x18011452d  lea     rdx, [rsp+0A58h+var_88]
0x180114535  lea     rcx, [rsp+0A58h+var_938]
0x18011453d  call    GUIDToStringWithoutBracket_0
0x180114542  mov     r13d, eax
0x180114545  test    eax, eax
0x180114547  jns     short loc_180114576
0x180114549  lea     rax, aFailedToConver_1; "failed to convert GUID to string with n"...
0x180114550  mov     edx, 0AC1h; void *
0x180114555  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18011455c  mov     r9d, r13d; char *
0x18011455f  mov     [rsp+0A58h+lpData], rax; int
0x180114564  mov     rcx, [rsp+0A58h]; this
0x18011456c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180114571  jmp     loc_180117835
0x180114576  lea     rdx, [rsp+0A58h+var_88]
0x18011457e  lea     rcx, [rsp+0A58h+var_688]
0x180114586  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18011458b  nop
0x18011458c  lea     rdx, [rsp+0A58h+var_688]
0x180114594  lea     rcx, [rsp+0A58h+var_8E8]
0x18011459c  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x1801145a1  nop
0x1801145a2  lea     rcx, [rsp+0A58h+var_688]
0x1801145aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801145af  nop
0x1801145b0  mov     eax, dword ptr [rsp+0A58h+var_A18]
0x1801145b4  jmp     short loc_1801145E4
0x1801145b6  mov     r13d, 8007000Eh
0x1801145bc  jmp     loc_180117835
0x1801145c1  lea     r8, [rsp+0A58h+var_8E8]
0x1801145c9  mov     rdx, rsi
0x1801145cc  call    ?GetAllRequestsPerEnrollment@OrchestratorDBManager@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; OrchestratorDBManager::GetAllRequestsPerEnrollment(ushort const *,std::list<std::wstring> &)
0x1801145d1  jmp     short loc_1801145E0
0x1801145d3  lea     rdx, [rsp+0A58h+var_8E8]
0x1801145db  call    ?GetAllRequests@OrchestratorDBManager@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; OrchestratorDBManager::GetAllRequests(std::list<std::wstring> &)
0x1801145e0  mov     dword ptr [rsp+0A58h+var_A18], eax
0x1801145e4  test    eax, eax
0x1801145e6  jns     short loc_180114607
0x1801145e8  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801145ed  lea     r9, word_180142E98
0x1801145f4  lea     r8, aOrchestratorid_1; "OrchestratorIDatabaseManagerSingleton::"...
0x1801145fb  lea     rdx, aDcengineRecons; "DCEngine::ReconstructQueueAndExecute"
0x180114602  jmp     loc_180117820
0x180114607  cmp     [rsp+0A58h+var_8E0], rdi
0x18011460f  jnz     loc_1801146B3
0x180114615  mov     rdx, rsi; unsigned __int16 *
0x180114618  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x18011461d  mov     ebx, eax
0x18011461f  mov     eax, 80000000h
0x180114624  lea     ecx, [rbx+rax]
0x180114627  test    eax, ecx
0x180114629  jnz     short loc_18011465E
0x18011462b  cmp     ebx, 80070002h
0x180114631  jz      short loc_18011465E
0x180114633  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180114638  mov     dword ptr [rsp+0A58h+lpData], ebx; int
0x18011463c  lea     rbx, word_180142E98
0x180114643  mov     r9, rbx; unsigned __int16 *
0x180114646  lea     r8, aDeclaredconfig_154; "DeclaredConfigurationStore_DeleteSchedu"...
0x18011464d  lea     rdx, aDcengineRecons; "DCEngine::ReconstructQueueAndExecute"
0x180114654  mov     rcx, rax; this
0x180114657  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18011465c  jmp     short loc_180114665
0x18011465e  lea     rbx, word_180142E98
0x180114665  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18011466a  mov     r9, rbx; unsigned __int16 *
0x18011466d  lea     r8, aNoRequestsForO; "No requests for Orchestrator, delete DC"...
0x180114674  lea     rdx, aDcengineRecons; "DCEngine::ReconstructQueueAndExecute"
0x18011467b  mov     rcx, rax; this
0x18011467e  call    ?LogOrchestratorGenericInfo@CDeclaredConfigurationLogger@@QEAAXPEBG00@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(ushort const *,ushort const *,ushort const *)
0x180114683  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18011468a  jz      loc_180117830
0x180114690  mov     dword ptr [rsp+0A58h+lpData], edi
0x180114694  lea     r9, aNoRequestsForO; "No requests for Orchestrator, delete DC"...
0x18011469b  lea     r8, aDcengineRecons; "DCEngine::ReconstructQueueAndExecute"
0x1801146a2  lea     rdx, OrchestratorGenericInformation
0x1801146a9  call    McTemplateU0zzd_EventWriteTransfer
0x1801146ae  jmp     loc_180117830
0x1801146b3  mov     rcx, cs:qword_18018A6C8
0x1801146ba  mov     [rsp+0A58h+var_8D0], rcx
0x1801146c2  test    rcx, rcx
0x1801146c5  jnz     short loc_1801146F7
0x1801146c7  call    InitOrchestratorEngine
0x1801146cc  mov     rcx, cs:qword_18018A6C8
0x1801146d3  mov     [rsp+0A58h+var_8D0], rcx
0x1801146db  test    rcx, rcx
0x1801146de  jnz     short loc_1801146F7
0x1801146e0  lea     rax, aCouldNotGetDcO; "could not get DC OrchestratorEngine"
0x1801146e7  mov     r13d, 80004005h
0x1801146ed  mov     edx, 0AFEh
0x1801146f2  jmp     loc_180114555
0x1801146f7  mov     rax, [rsp+0A58h+var_8E8]
0x1801146ff  mov     rdi, [rax]
0x180114702  mov     r13d, 80070057h
0x180114708  lea     rbx, word_180142E98
0x18011470f  lea     r14, aDcengineRecons; "DCEngine::ReconstructQueueAndExecute"
0x180114716  cmp     rdi, rax
0x180114719  jz      loc_1801177EF
0x18011471f  lea     rcx, [r12+0E0h]; lpCriticalSection
0x180114727  mov     [rsp+0A58h+var_9F8], rcx
0x18011472c  call    cs:__imp_EnterCriticalSection
0x180114732  nop
0x180114733  lea     r12, [rdi+10h]
0x180114737  mov     [rsp+0A58h+var_908], r12
0x18011473f  cmp     qword ptr [rdi+28h], 7
0x180114744  jbe     short loc_180114752
0x180114746  mov     r12, [r12]
0x18011474a  mov     [rsp+0A58h+var_908], r12
0x180114752  xorps   xmm0, xmm0
0x180114755  movups  xmmword ptr [rsp+0A58h+var_938], xmm0
0x18011475d  xor     ebx, ebx
0x18011475f  mov     [rsp+0A58h+var_A10], rbx
0x180114764  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl(void)'::`2'::impl
0x18011476b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(void)
0x180114770  test    al, al
0x180114772  jz      loc_180114873
0x180114778  mov     [rsp+0A58h+hKey], rbx
0x180114780  lea     rcx, [rsp+0A58h+hKey]
0x180114788  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::ensure_data(void)
0x18011478d  mov     rcx, [rax]
0x180114790  add     rcx, 8
0x180114794  lea     rdx, [rsp+0A58h+var_798]
0x18011479c  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1801147a1  lea     rdx, [rsp+0A58h+hKey]
0x1801147a9  lea     rcx, [rsp+0A58h+var_A10]
0x1801147ae  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy> &&)
0x1801147b3  lea     rcx, [rsp+0A58h+hKey]
0x1801147bb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>,wil::err_returncode_policy>(void)
0x1801147c0  lea     rdx, [rsp+0A58h+var_808]
0x1801147c8  lea     rcx, [rsp+0A58h+var_A10]
0x1801147cd  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(void)
0x1801147d2  mov     rcx, [rax]
0x1801147d5  mov     al, [rsp+0A58h+var_A08]
0x1801147d9  mov     [rcx+110h], al
0x1801147df  lea     rcx, [rsp+0A58h+var_808]
0x1801147e7  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(void)
0x1801147ec  lea     rdx, [rsp+0A58h+var_7E8]
0x1801147f4  lea     rcx, [rsp+0A58h+var_A10]
0x1801147f9  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(void)
0x1801147fe  mov     rcx, [rax]
0x180114801  mov     eax, [rsp+0A58h+arg_28]
0x180114808  mov     [rcx+114h], eax
0x18011480e  lea     rcx, [rsp+0A58h+var_7E8]
0x180114816  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(void)
0x18011481b  mov     ebx, 811C9DC5h
0x180114820  test    r12, r12
0x180114823  jz      short loc_180114849
0x180114825  movzx   eax, word ptr [r12]
0x18011482a  test    ax, ax
0x18011482d  jz      short loc_180114849
0x18011482f  mov     rcx, r12
0x180114832  lea     rcx, [rcx+2]
0x180114836  movzx   eax, ax
0x180114839  xor     eax, ebx
0x18011483b  imul    ebx, eax, 1000193h
0x180114841  movzx   eax, word ptr [rcx]
0x180114844  test    ax, ax
0x180114847  jnz     short loc_180114832
0x180114849  lea     rdx, [rsp+0A58h+var_7E0]
0x180114851  lea     rcx, [rsp+0A58h+var_A10]
0x180114856  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(void)
0x18011485b  mov     rcx, [rax]
0x18011485e  mov     [rcx+11Ch], ebx
0x180114864  lea     rcx, [rsp+0A58h+var_7E0]
0x18011486c  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(void)
0x180114871  xor     ebx, ebx
0x180114873  lea     rax, [rsp+0A58h+var_A10]
0x180114878  mov     [rsp+0A58h+var_9D8], rax
0x180114880  lea     rax, [rsp+0A58h+var_A18]
0x180114885  mov     [rsp+0A58h+var_9D0], rax
0x18011488d  mov     [rsp+0A58h+var_9C8], 1
0x180114895  lea     rax, [rsp+0A58h+var_8EC]
0x18011489d  mov     [rsp+0A58h+lpcbData], rax; enum DCLifecycleNotificationType *
0x1801148a2  lea     rax, [rsp+0A58h+var_8F0]
0x1801148aa  mov     [rsp+0A58h+lpData], rax; enum DMOrchestratorState *
0x1801148af  lea     r9, [rsp+0A58h+var_910]; enum StateMachineTypeTag *
0x1801148b7  lea     r8, [rsp+0A58h+psz]; struct OrchestratorDCInfo *
0x1801148bf  mov     rdx, r12; unsigned __int16 *
0x1801148c2  call    ?GetRequest@OrchestratorDBManager@@QEAAJPEBGPEAUOrchestratorDCInfo@@PEAW4StateMachineTypeTag@@PEAW4DMOrchestratorState@@PEAW4DCLifecycleNotificationType@@@Z; OrchestratorDBManager::GetRequest(ushort const *,OrchestratorDCInfo *,StateMachineTypeTag *,DMOrchestratorState *,DCLifecycleNotificationType *)
0x1801148c7  mov     dword ptr [rsp+0A58h+var_A18], eax
0x1801148cb  test    eax, eax
0x1801148cd  jns     loc_180114A03
0x1801148d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::GetImpl(void)'::`2'::impl
0x1801148da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigRefreshBehaviorUpdateNew>::__private_IsEnabled(void)
0x1801148df  test    al, al
0x1801148e1  jz      short loc_18011493D
0x1801148e3  mov     ebx, dword ptr [rsp+0A58h+var_A18]
0x1801148e7  lea     rdx, [rsp+0A58h+var_7D8]
0x1801148ef  lea     rcx, [rsp+0A58h+var_A10]
0x1801148f4  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(void)
0x1801148f9  mov     rcx, [rax]
0x1801148fc  mov     [rcx+128h], ebx
0x180114902  lea     rcx, [rsp+0A58h+var_7D8]
0x18011490a  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(void)
0x18011490f  lea     rdx, [rsp+0A58h+var_7D0]
0x180114917  lea     rcx, [rsp+0A58h+var_A10]
0x18011491c  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::operator->(void)
0x180114921  mov     rcx, [rax]
0x180114924  mov     dword ptr [rcx+118h], 1
0x18011492e  lea     rcx, [rsp+0A58h+var_7D0]
0x180114936  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigRefreshTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigRefreshTipTest,_tip_OsConfigRefreshTipTest>>(void)
0x18011493b  xor     ebx, ebx
0x18011493d  mov     [rsp+0A58h+var_378], bx
0x180114945  mov     r9, r12
0x180114948  lea     r8, aScenarioidS; "ScenarioId: %s"
0x18011494f  mov     edx, 104h; unsigned __int64
0x180114954  lea     rcx, [rsp+0A58h+var_378]; unsigned __int16 *
0x18011495c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180114961  test    eax, eax
0x180114963  js      short loc_180114990
0x180114965  cmp     cs:byte_180189FC1, bl
0x18011496b  jge     short loc_180114990
0x18011496d  mov     eax, dword ptr [rsp+0A58h+var_A18]
0x180114971  mov     dword ptr [rsp+0A58h+lpData], eax
0x180114975  lea     r9, [rsp+0A58h+var_378]
0x18011497d  lea     r8, aReconstructque; "ReconstructQueueAndExecute:Orchestrator"...
0x180114984  lea     rdx, OrchestratorGenericFailure
0x18011498b  call    McTemplateU0zzd_EventWriteTransfer
0x180114990  lea     rdx, [rsp+0A58h+var_938]; struct _GUID *
0x180114998  mov     rcx, r12; unsigned __int16 *
0x18011499b  call    ?GetGuidFromEnrollmentId@@YAJPEBGPEAU_GUID@@@Z; GetGuidFromEnrollmentId(ushort const *,_GUID *)
0x1801149a0  test    eax, eax
0x1801149a2  js      short loc_1801149E9
0x1801149a4  movaps  xmm0, xmmword ptr [rsp+0A58h+var_938]
0x1801149ac  movdqa  xmmword ptr [rsp+0A58h+var_938], xmm0
0x1801149b5  lea     rdx, [rsp+0A58h+var_938]; struct _GUID
0x1801149bd  call    ?DeleteRequest@OrchestratorDBManager@@QEAAJU_GUID@@@Z; OrchestratorDBManager::DeleteRequest(_GUID)
0x1801149c2  mov     dword ptr [rsp+0A58h+var_A18], eax
0x1801149c6  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801149cb  mov     ecx, dword ptr [rsp+0A58h+var_A18]
0x1801149cf  mov     dword ptr [rsp+0A58h+lpData], ecx; int
0x1801149d3  mov     r9, r12; unsigned __int16 *
0x1801149d6  lea     r8, aDeleterequest; "DeleteRequest"
0x1801149dd  mov     rdx, r14; unsigned __int16 *
0x1801149e0  mov     rcx, rax; this
0x1801149e3  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1801149e8  nop
0x1801149e9  mov     [rsp+0A58h+var_9C8], bl
0x1801149f0  lea     rcx, [rsp+0A58h+var_9D8]
0x1801149f8  call    _lambda_96645691a4f9f14f5f9ebf9f7ade5e88___operator__
0x1801149fd  nop
0x1801149fe  jmp     loc_180117753
  ... truncated ...
```
