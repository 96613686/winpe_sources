# CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x1801fee00`
- end: `0x1802028df`
- name: `?DoExecute@CMigrateFramework@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `15071`
- prototype: `__int64 __fastcall(CMigrateFramework *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180014156`
- `0x180035de8`
- `0x18003c47c`
- `0x18003d0e8`
- `0x1800447ec`
- `0x180057dec`
- `0x18005dd8c`
- `0x1800ae6b4`
- `0x1801e71a4`
- `0x1801edddc`
- `0x1801ee484`
- `0x1801fee00`
- `0x18021b604`
- `0x1802cff64`
- `0x1802d010c`
- `0x1802d4590`
- `0x1802d68d4`
- `0x1802d8350`
- `0x1802d90d8`
- `0x1802e6970`
- `0x18031c078`
- `0x18031d784`
- `0x18031eff0`
- `0x18032962c`
- `0x18033606c`
- `0x18035734c`
- `0x180357748`
- `0x18040466c`
- `0x18040498c`
- `0x18040c590`
- `0x18040f020`
- `0x18040f0bc`
- `0x180411dfc`
- `0x180412308`
- `0x180412a5c`
- `0x180412e88`
- `0x18041a224`
- `0x18041a408`
- `0x18041b2e0`
- `0x18041b748`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ntdll!NtClose` at `0x1802000f3`
- `ntdll!NtClose` at `0x1802000f3`
- `ntdll!RtlFreeUnicodeString` at `0x1801ff70e`
- `ntdll!RtlFreeUnicodeString` at `0x1801ff7a2`
- `ntdll!RtlFreeUnicodeString` at `0x1801ff70e`
- `ntdll!RtlFreeUnicodeString` at `0x1801ff7a2`
- `ntdll!RtlFreeHeap` at `0x1801ffb58`
- `ntdll!RtlFreeHeap` at `0x1801ffc6f`
- `ntdll!RtlFreeHeap` at `0x1801ffd8a`
- `ntdll!RtlFreeHeap` at `0x1801fff9f`
- `ntdll!RtlFreeHeap` at `0x180200019`
- `ntdll!RtlFreeHeap` at `0x180200349`
- `ntdll!RtlFreeHeap` at `0x180200378`
- `ntdll!RtlFreeHeap` at `0x1802003a7`
- `ntdll!RtlFreeHeap` at `0x1801ffb58`
- `ntdll!RtlFreeHeap` at `0x1801ffc6f`
- `ntdll!RtlFreeHeap` at `0x1801ffd8a`
- `ntdll!RtlFreeHeap` at `0x1801fff9f`
- `ntdll!RtlFreeHeap` at `0x180200019`
- `ntdll!RtlFreeHeap` at `0x180200349`
- `ntdll!RtlFreeHeap` at `0x180200378`
- `ntdll!RtlFreeHeap` at `0x1802003a7`
- `ntdll!RtlAllocateHeap` at `0x1801ffbeb`
- `ntdll!RtlAllocateHeap` at `0x1801ffd27`
- `ntdll!RtlAllocateHeap` at `0x1801fff35`
- `ntdll!RtlAllocateHeap` at `0x1801ffbeb`
- `ntdll!RtlAllocateHeap` at `0x1801ffd27`
- `ntdll!RtlAllocateHeap` at `0x1801fff35`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801ff6d1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801ff765`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801ff6d1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801ff765`
- `ADVAPI32!RegCloseKey` at `0x18020046d`
- `ADVAPI32!RegCloseKey` at `0x180200487`
- `ADVAPI32!RegCloseKey` at `0x1802004a1`
- `ADVAPI32!RegCloseKey` at `0x1802004bb`
- `ADVAPI32!RegCloseKey` at `0x1802004d5`
- `ADVAPI32!RegCloseKey` at `0x18020046d`
- `ADVAPI32!RegCloseKey` at `0x180200487`
- `ADVAPI32!RegCloseKey` at `0x1802004a1`
- `ADVAPI32!RegCloseKey` at `0x1802004bb`
- `ADVAPI32!RegCloseKey` at `0x1802004d5`
- `KERNEL32!GetProcessHeap` at `0x1802003c9`
- `KERNEL32!GetProcessHeap` at `0x1802003fd`
- `KERNEL32!GetProcessHeap` at `0x180200436`
- `KERNEL32!GetProcessHeap` at `0x1802003c9`
- `KERNEL32!GetProcessHeap` at `0x1802003fd`
- `KERNEL32!GetProcessHeap` at `0x180200436`
- `KERNEL32!HeapFree` at `0x1802003df`
- `KERNEL32!HeapFree` at `0x180200410`
- `KERNEL32!HeapFree` at `0x180200449`
- `KERNEL32!HeapFree` at `0x1802003df`
- `KERNEL32!HeapFree` at `0x180200410`
- `KERNEL32!HeapFree` at `0x180200449`
- `KERNEL32!GetLastError` at `0x1801fee9b`
- `KERNEL32!GetLastError` at `0x1801fef36`
- `KERNEL32!GetLastError` at `0x1801fefe8`
- `KERNEL32!GetLastError` at `0x1801ff0ac`
- `KERNEL32!GetLastError` at `0x1801ff1c6`
- `KERNEL32!GetLastError` at `0x1801ff7f2`
- `KERNEL32!GetLastError` at `0x1801ff95f`
- `KERNEL32!GetLastError` at `0x180200120`
- `KERNEL32!GetLastError` at `0x1802001f8`
- `KERNEL32!GetLastError` at `0x180200273`
- `KERNEL32!GetLastError` at `0x18020058d`
- `KERNEL32!GetLastError` at `0x1802008b2`
- `KERNEL32!GetLastError` at `0x18020091f`
- `KERNEL32!GetLastError` at `0x180200c92`
- `KERNEL32!GetLastError` at `0x180200cff`
- `KERNEL32!GetLastError` at `0x180200e8a`
- `KERNEL32!GetLastError` at `0x180200f0a`
- `KERNEL32!GetLastError` at `0x18020108c`
- `KERNEL32!GetLastError` at `0x18020110f`
- `KERNEL32!GetLastError` at `0x1802011d4`
- `KERNEL32!GetLastError` at `0x18020123a`
- `KERNEL32!GetLastError` at `0x180201407`
- `KERNEL32!GetLastError` at `0x180201443`
- `KERNEL32!GetLastError` at `0x180201609`
- `KERNEL32!GetLastError` at `0x18020161f`
- `KERNEL32!GetLastError` at `0x180201644`
- `KERNEL32!GetLastError` at `0x1802016f9`
- `KERNEL32!GetLastError` at `0x180201795`
- `KERNEL32!GetLastError` at `0x1802017ab`
- `KERNEL32!GetLastError` at `0x1802017d0`
- `KERNEL32!GetLastError` at `0x18020187c`
- `KERNEL32!GetLastError` at `0x180201892`
- `KERNEL32!GetLastError` at `0x1802018b7`
- `KERNEL32!GetLastError` at `0x180201963`
- `KERNEL32!GetLastError` at `0x180201979`
- `KERNEL32!GetLastError` at `0x18020199e`
- `KERNEL32!GetLastError` at `0x180201a4a`
- `KERNEL32!GetLastError` at `0x180201a60`
- `KERNEL32!GetLastError` at `0x180201a85`
- `KERNEL32!GetLastError` at `0x180201b31`
- `KERNEL32!GetLastError` at `0x180201b47`
- `KERNEL32!GetLastError` at `0x180201b6c`
- `KERNEL32!GetLastError` at `0x180201c76`
- `KERNEL32!GetLastError` at `0x180201c8c`
- `KERNEL32!GetLastError` at `0x180201cd8`
- `KERNEL32!GetLastError` at `0x180201d83`
- `KERNEL32!GetLastError` at `0x180201e28`
- `KERNEL32!GetLastError` at `0x180201e3e`
- `KERNEL32!GetLastError` at `0x180201e63`
- `KERNEL32!GetLastError` at `0x180201ef2`
- `KERNEL32!GetLastError` at `0x180201f96`
- `KERNEL32!GetLastError` at `0x18020204d`
- `KERNEL32!GetLastError` at `0x1802020f5`
- `KERNEL32!GetLastError` at `0x180202186`
- `KERNEL32!GetLastError` at `0x180202449`
- `KERNEL32!GetLastError` at `0x18020250c`
- `KERNEL32!GetLastError` at `0x1802026e2`
- `KERNEL32!GetLastError` at `0x180202741`
- `KERNEL32!GetLastError` at `0x1802027a7`
- `KERNEL32!GetLastError` at `0x1801fee9b`
- `KERNEL32!GetLastError` at `0x1801fef36`
- `KERNEL32!GetLastError` at `0x1801fefe8`
- `KERNEL32!GetLastError` at `0x1801ff0ac`
- `KERNEL32!GetLastError` at `0x1801ff1c6`
- `KERNEL32!GetLastError` at `0x1801ff7f2`
- `KERNEL32!GetLastError` at `0x1801ff95f`
- `KERNEL32!GetLastError` at `0x180200120`
- `KERNEL32!GetLastError` at `0x1802001f8`
- `KERNEL32!GetLastError` at `0x180200273`
- `KERNEL32!GetLastError` at `0x18020058d`
- `KERNEL32!GetLastError` at `0x1802008b2`
- `KERNEL32!GetLastError` at `0x18020091f`
- `KERNEL32!GetLastError` at `0x180200c92`
- `KERNEL32!GetLastError` at `0x180200cff`
- `KERNEL32!GetLastError` at `0x180200e8a`
- `KERNEL32!GetLastError` at `0x180200f0a`
- `KERNEL32!GetLastError` at `0x18020108c`
- `KERNEL32!GetLastError` at `0x18020110f`
- `KERNEL32!GetLastError` at `0x1802011d4`
- `KERNEL32!GetLastError` at `0x18020123a`
- `KERNEL32!GetLastError` at `0x180201407`
- `KERNEL32!GetLastError` at `0x180201443`
- `KERNEL32!GetLastError` at `0x180201609`
- `KERNEL32!GetLastError` at `0x18020161f`
- `KERNEL32!GetLastError` at `0x180201644`
- `KERNEL32!GetLastError` at `0x1802016f9`
- `KERNEL32!GetLastError` at `0x180201795`
- `KERNEL32!GetLastError` at `0x1802017ab`
- `KERNEL32!GetLastError` at `0x1802017d0`
- `KERNEL32!GetLastError` at `0x18020187c`
- `KERNEL32!GetLastError` at `0x180201892`
- `KERNEL32!GetLastError` at `0x1802018b7`
- `KERNEL32!GetLastError` at `0x180201963`
- `KERNEL32!GetLastError` at `0x180201979`
- `KERNEL32!GetLastError` at `0x18020199e`
- `KERNEL32!GetLastError` at `0x180201a4a`
- `KERNEL32!GetLastError` at `0x180201a60`
- `KERNEL32!GetLastError` at `0x180201a85`
- `KERNEL32!GetLastError` at `0x180201b31`
- `KERNEL32!GetLastError` at `0x180201b47`
- `KERNEL32!GetLastError` at `0x180201b6c`
- `KERNEL32!GetLastError` at `0x180201c76`
- `KERNEL32!GetLastError` at `0x180201c8c`
- `KERNEL32!GetLastError` at `0x180201cd8`
- `KERNEL32!GetLastError` at `0x180201d83`
- `KERNEL32!GetLastError` at `0x180201e28`
- `KERNEL32!GetLastError` at `0x180201e3e`
- `KERNEL32!GetLastError` at `0x180201e63`
- `KERNEL32!GetLastError` at `0x180201ef2`
- `KERNEL32!GetLastError` at `0x180201f96`
- `KERNEL32!GetLastError` at `0x18020204d`
- `KERNEL32!GetLastError` at `0x1802020f5`
- `KERNEL32!GetLastError` at `0x180202186`
- `KERNEL32!GetLastError` at `0x180202449`
- `KERNEL32!GetLastError` at `0x18020250c`
- `KERNEL32!GetLastError` at `0x1802026e2`
- `KERNEL32!GetLastError` at `0x180202741`
- `KERNEL32!GetLastError` at `0x1802027a7`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200573`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200587`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200628`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200707`
- `KERNEL32!SetEnvironmentVariableW` at `0x1802025ee`
- `KERNEL32!SetEnvironmentVariableW` at `0x1802025fd`
- `KERNEL32!SetEnvironmentVariableW` at `0x18020260c`
- `KERNEL32!SetEnvironmentVariableW` at `0x18020261b`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200573`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200587`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200628`
- `KERNEL32!SetEnvironmentVariableW` at `0x180200707`
- `KERNEL32!SetEnvironmentVariableW` at `0x1802025ee`
- `KERNEL32!SetEnvironmentVariableW` at `0x1802025fd`
- `KERNEL32!SetEnvironmentVariableW` at `0x18020260c`
- `KERNEL32!SetEnvironmentVariableW` at `0x18020261b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180201576`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1802015af`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180201576`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1802015af`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1801ff13a`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1801ff13a`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802006c0`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802006c0`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801ff28c`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801ff535`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801ff28c`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801ff535`

## string_xrefs

- `0x1801fef26`: `SeSecurityPrivilege`
- `0x1802014bb`: `SeSecurityPrivilege`
- `0x1801ff2f9`: `SECURITY`
- `0x1801ff3f0`: `SECURITY`
- `0x1801ff5f1`: `SECURITY`
- `0x1802004fa`: `MigLog.xml`
- `0x1801ff3e9`: `$OFFLINE_RW$SECURITY`
- `0x1801ff5ea`: `$OFFLINE_RW$SECURITY`
- `0x1802004a7`: `$OFFLINE_RW$SECURITY`
- `0x180200b31`: `MigJournal.xml`
- `0x1802012bc`: `MigJournal.xml`
- `0x18020251d`: `FLOWTRACK: Framework apply complete, no need to run again`
- `0x1802025ac`: `FrameworkApplyComplete`
- `0x1801fef4e`: `%hs: Cannot enable SE_SECURITY_NAME privilege`
- `0x1801feeb3`: `%hs: Enabling SE_SECURITY_NAME privilege`
- `0x180201672`: `CMigrateFramework::DoExecute: Cannot load security hive for source offline OS %s. Error: 0x%08X`
- `0x18020170d`: `CMigrateFramework::DoExecute: Cannot get security info for the source security hive. Error: 0x%08X`
- `0x1802019cc`: `CMigrateFramework::DoExecute: Cannot load security hive for offline OS %s. Error: 0x%08X`
- `0x180201fc8`: `CMigrateFramework::DoExecute: Cannot convert new OS Dir %s to NT path. Error: 0x%08X`
- `0x18020207b`: `CMigrateFramework::DoExecute: Cannot convert new OS WinDir %s to NT path. Error: 0x%08X`
- `0x1801ff980`: `CMigrateFramework::DoExecute: ModifyOfflineRegHives: Changing paths from %s to %s`
- `0x180200209`: `CMigrateFramework::DoExecute: Pending upgrade hive update request for setupcl`
- `0x180201cec`: `CMigrateFramework::DoExecute: Updating paths in hives failed. Status = 0x%08X`
- `0x180201e77`: `CMigrateFramework::DoExecute: Failed to bypass root ACL migration. Error: 0x%08X`
- `0x1802002d2`: `SkipMigrateRootACL`
- `0x180200284`: `ACL mismatch detected, will initialize key`
- `0x180201f06`: `CMigrateFramework::DoExecute: Pending updated setupcl request failed. Status = 0x%08X`
- `0x18020145b`: `%hs: Disabling SE_SECURITY_NAME privilege`
- `0x180202759`: `%hs: Operation completed`
- `0x1802026f3`: `Don't have the date/time label, cannot write the migration scope`
- `0x1801ffca8`: `SidAccountDomainNew`
- `0x1801ffcf9`: `SidAccountDomainNew`
- `0x1801ffb6c`: `SidAccountDomainOld`
- `0x1801ffbbd`: `SidAccountDomainOld`
- `0x1801fffcc`: `SclpCanonicalizePaths failed. Error: 0x%08X`
- `0x1801ffc10`: `SclRetrieveSid`
- `0x1801ffc4a`: `SclRetrieveSid`
- `0x1801ffc84`: `SclRetrieveSid`
- `0x1801ffc9c`: `SclRetrieveSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=61 #try_helpers=4
__int64 __fastcall CMigrateFramework::DoExecute(
        CMigrateFramework *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  struct UnBCL::String *v11; // rax
  struct UnBCL::String *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  UnBCL::String *v15; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v17; // rax
  const struct UnBCL::String *v18; // rbx
  const struct UnBCL::String *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  const struct UnBCL::String *v23; // rax
  struct UnBCL::String *v24; // rax
  const struct UnBCL::String *v25; // rbx
  const struct UnBCL::String *v26; // rax
  DWORD v27; // ebx
  __int64 v28; // rdi
  UnBCL::String *v29; // rax
  const wchar_t *v30; // rax
  struct tagLOG_PARTIAL_MSG *v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rbx
  HKEY v34; // rdi
  struct UnBCL::String **v35; // rbx
  struct UnBCL::String *v36; // rax
  unsigned int v37; // r8d
  int RegSecurityInfo; // r14d
  UnBCL::String *v39; // rax
  const unsigned __int16 *v40; // rax
  const struct UnBCL::String *v41; // rbx
  const struct UnBCL::String *v42; // rax
  struct UnBCL::String *v43; // rax
  UnBCL::String *v44; // rax
  const unsigned __int16 *v45; // rax
  UnBCL::String *v46; // rax
  const unsigned __int16 *v47; // rax
  UnBCL::String *v48; // rax
  const unsigned __int16 *v49; // rax
  UnBCL::String *v50; // rax
  const unsigned __int16 *v51; // rax
  UnBCL::String *v52; // rax
  const unsigned __int16 *v53; // rax
  UnBCL::String *v54; // rax
  const unsigned __int16 *v55; // rax
  int v56; // r15d
  int v57; // r15d
  UnBCL::String *v58; // rax
  const unsigned __int16 *v59; // rax
  int v60; // r15d
  int v61; // r15d
  const char *String; // r14
  DWORD v63; // edi
  __int64 v64; // rbx
  struct tagLOG_PARTIAL_MSG *v65; // rax
  const wchar_t *v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r12
  __int64 v69; // rcx
  wchar_t *v70; // rax
  wchar_t v71; // r9
  __int64 v72; // rdx
  const wchar_t *v73; // r13
  const wchar_t *v74; // r8
  __int64 v75; // rcx
  wchar_t *v76; // rax
  wchar_t v77; // r9
  DWORD v78; // edi
  __int64 v79; // rbx
  struct tagLOG_PARTIAL_MSG *v80; // rax
  int v81; // r14d
  char v82; // al
  int v83; // r14d
  int v84; // eax
  DWORD v85; // edi
  __int64 v86; // rbx
  struct tagLOG_PARTIAL_MSG *v87; // rax
  wchar_t *v88; // rax
  __int64 v89; // rdx
  wchar_t v90; // cx
  DWORD v91; // edi
  __int64 v92; // rbx
  struct tagLOG_PARTIAL_MSG *v93; // rax
  int v94; // r14d
  HANDLE ProcessHeap; // rax
  __int64 v96; // rbx
  HANDLE v97; // rax
  BOOL v98; // eax
  void *v99; // rcx
  HANDLE v100; // rax
  BOOL v101; // eax
  void *v102; // rcx
  HKEY v103; // rcx
  HKEY v104; // rcx
  HKEY v105; // rcx
  HKEY v106; // rcx
  HKEY v107; // rcx
  const struct UnBCL::String *v108; // rbx
  const struct UnBCL::String *v109; // rax
  struct UnBCL::String *v110; // rax
  UnBCL::String *v111; // rax
  const WCHAR *v112; // rax
  __int64 v113; // rdi
  UnBCL::String *v114; // rax
  const char *v115; // rax
  struct tagLOG_PARTIAL_MSG *v116; // rax
  const struct UnBCL::String *v117; // rbx
  const struct UnBCL::String *v118; // rax
  struct UnBCL::String *v119; // rax
  UnBCL::String *v120; // rax
  const WCHAR *v121; // rax
  struct UnBCL::String *v122; // rax
  UnBCL::String *v123; // rax
  const WCHAR *v124; // rax
  BOOL v125; // r14d
  const struct UnBCL::String *v126; // rbx
  const struct UnBCL::String *v127; // rax
  struct UnBCL::String *v128; // rax
  const struct UnBCL::String *v129; // rbx
  const struct UnBCL::String *v130; // rax
  struct UnBCL::String *v131; // rax
  const struct UnBCL::String *v132; // rbx
  const struct UnBCL::String *v133; // rax
  struct UnBCL::String *v134; // rax
  const struct UnBCL::String *v135; // rbx
  const struct UnBCL::String *v136; // rax
  struct UnBCL::String *v137; // rax
  DWORD v138; // edi
  __int64 v139; // rbx
  struct tagLOG_PARTIAL_MSG *v140; // rax
  __int64 v141; // rdi
  UnBCL::String *v142; // rax
  const unsigned __int16 *v143; // rax
  unsigned __int64 v144; // rax
  struct tagLOG_PARTIAL_MSG *v145; // rax
  const struct UnBCL::String *v146; // rbx
  const struct UnBCL::String *v147; // rax
  struct UnBCL::String *v148; // rax
  const struct UnBCL::String *v149; // rax
  const struct UnBCL::String *v150; // rax
  struct UnBCL::DirectoryInfo *Dir; // rax
  const struct UnBCL::String *v152; // rbx
  const struct UnBCL::String *v153; // rax
  struct UnBCL::String *v154; // rax
  const struct UnBCL::String *v155; // rax
  const struct UnBCL::String *v156; // rax
  struct UnBCL::DirectoryInfo *v157; // rax
  const struct UnBCL::String *v158; // rbx
  const struct UnBCL::String *v159; // rax
  struct UnBCL::String *v160; // rax
  CSPMigProgress *v161; // rax
  CSPMigProgress *v162; // rax
  __int64 v163; // r15
  __int64 v164; // r14
  __int64 v165; // rdi
  unsigned int v166; // ebx
  __int64 v167; // rax
  unsigned int v168; // r14d
  DWORD v169; // edi
  __int64 v170; // rbx
  struct tagLOG_PARTIAL_MSG *v171; // rax
  __int64 v172; // rdi
  UnBCL::String *v173; // rax
  const unsigned __int16 *v174; // rax
  unsigned __int64 v175; // rax
  struct tagLOG_PARTIAL_MSG *v176; // rax
  CSPMigProgress *v177; // rax
  unsigned int v178; // edx
  unsigned int v179; // edx
  CSPMigProgress *v180; // rax
  __int64 v181; // r15
  BOOL v182; // ebx
  __int64 v183; // r12
  __int64 v184; // r14
  __int64 v185; // rdi
  __int64 v186; // rax
  UnBCL::String *v187; // rax
  const unsigned __int16 *v188; // rax
  UnBCL::String *v189; // rax
  const unsigned __int16 *v190; // rax
  signed int v191; // eax
  bool v192; // sf
  signed int v193; // eax
  unsigned int v194; // r14d
  DWORD v195; // ebx
  __int64 v196; // rdi
  UnBCL::String *v197; // rax
  const char *v198; // rax
  struct tagLOG_PARTIAL_MSG *v199; // rax
  DWORD v200; // edi
  __int64 v201; // rbx
  struct tagLOG_PARTIAL_MSG *v202; // rax
  signed int v203; // eax
  bool v204; // sf
  signed int v205; // eax
  unsigned int v206; // r14d
  DWORD v207; // ebx
  __int64 v208; // rdi
  UnBCL::String *v209; // rax
  const char *v210; // rax
  struct tagLOG_PARTIAL_MSG *v211; // rax
  signed int v212; // eax
  bool v213; // sf
  signed int v214; // eax
  unsigned int v215; // r14d
  DWORD v216; // ebx
  __int64 v217; // rdi
  UnBCL::String *v218; // rax
  const char *v219; // rax
  struct tagLOG_PARTIAL_MSG *v220; // rax
  signed int v221; // eax
  bool v222; // sf
  signed int v223; // eax
  unsigned int v224; // r14d
  DWORD v225; // ebx
  __int64 v226; // rdi
  UnBCL::String *v227; // rax
  const char *v228; // rax
  struct tagLOG_PARTIAL_MSG *v229; // rax
  signed int v230; // eax
  bool v231; // sf
  signed int v232; // eax
  unsigned int v233; // r14d
  DWORD v234; // ebx
  __int64 v235; // rdi
  UnBCL::String *v236; // rax
  const char *v237; // rax
  struct tagLOG_PARTIAL_MSG *v238; // rax
  signed int v239; // eax
  bool v240; // sf
  signed int v241; // eax
  unsigned int v242; // r14d
  DWORD v243; // ebx
  __int64 v244; // rdi
  UnBCL::String *v245; // rax
  const char *v246; // rax
  struct tagLOG_PARTIAL_MSG *v247; // rax
  struct tagLOG_PARTIAL_MSG *v248; // rax
  signed int v249; // eax
  bool v250; // sf
  DWORD v251; // edi
  __int64 v252; // rbx
  struct tagLOG_PARTIAL_MSG *v253; // rax
  DWORD v254; // edi
  __int64 v255; // rbx
  struct tagLOG_PARTIAL_MSG *v256; // rax
  DWORD v257; // edi
  __int64 v258; // rbx
  struct tagLOG_PARTIAL_MSG *v259; // rax
  DWORD v260; // ebx
  __int64 v261; // rdi
  UnBCL::String *v262; // rax
  const char *v263; // rax
  struct tagLOG_PARTIAL_MSG *v264; // rax
  DWORD v265; // ebx
  __int64 v266; // rdi
  UnBCL::String *v267; // rax
  const char *v268; // rax
  struct tagLOG_PARTIAL_MSG *v269; // rax
  DWORD v270; // edi
  __int64 v271; // rbx
  struct tagLOG_PARTIAL_MSG *v272; // rax
  DWORD v273; // edi
  __int64 v274; // rbx
  struct tagLOG_PARTIAL_MSG *v275; // rax
  BOOL v276; // [rsp+6Ch] [rbp-79Ch]
  PVOID P[3]; // [rsp+80h] [rbp-788h] BYREF
  HANDLE Handle[2]; // [rsp+98h] [rbp-770h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+A8h] [rbp-760h] BYREF
  int *v282; // [rsp+C0h] [rbp-748h]
  _BYTE v283[16]; // [rsp+C8h] [rbp-740h] BYREF
  void *v284[2]; // [rsp+D8h] [rbp-730h] BYREF
  int v285[2]; // [rsp+E8h] [rbp-720h]
  const char *v286; // [rsp+F0h] [rbp-718h] BYREF
  int v287[2]; // [rsp+F8h] [rbp-710h]
  int v288; // [rsp+100h] [rbp-708h] BYREF
  LPVOID lpMem; // [rsp+108h] [rbp-700h] BYREF
  LPVOID v290; // [rsp+110h] [rbp-6F8h] BYREF
  HKEY v291; // [rsp+118h] [rbp-6F0h]
  HKEY v292; // [rsp+120h] [rbp-6E8h]
  HKEY v293; // [rsp+128h] [rbp-6E0h]
  HKEY v294; // [rsp+130h] [rbp-6D8h]
  HKEY hKey; // [rsp+138h] [rbp-6D0h]
  int v296[2]; // [rsp+140h] [rbp-6C8h]
  int v297; // [rsp+148h] [rbp-6C0h] BYREF
  struct IInternalOperationsProgress *v298; // [rsp+150h] [rbp-6B8h]
  _BYTE v299[16]; // [rsp+158h] [rbp-6B0h] BYREF
  _BYTE v300[16]; // [rsp+168h] [rbp-6A0h] BYREF
  _QWORD v301[2]; // [rsp+178h] [rbp-690h] BYREF
  _QWORD v302[7]; // [rsp+188h] [rbp-680h] BYREF
  _BYTE v303[16]; // [rsp+1C0h] [rbp-648h] BYREF
  _BYTE v304[24]; // [rsp+1D0h] [rbp-638h] BYREF
  _BYTE v305[16]; // [rsp+1E8h] [rbp-620h] BYREF
  _BYTE v306[16]; // [rsp+1F8h] [rbp-610h] BYREF
  _BYTE v307[16]; // [rsp+208h] [rbp-600h] BYREF
  _BYTE v308[16]; // [rsp+218h] [rbp-5F0h] BYREF
  _BYTE v309[24]; // [rsp+228h] [rbp-5E0h] BYREF
  _QWORD v310[3]; // [rsp+240h] [rbp-5C8h] BYREF
  __int128 v311; // [rsp+258h] [rbp-5B0h]
  _QWORD *v312; // [rsp+268h] [rbp-5A0h] BYREF
  _QWORD *pExceptionObject; // [rsp+270h] [rbp-598h] BYREF
  _QWORD *v314; // [rsp+278h] [rbp-590h] BYREF
  _QWORD *v315; // [rsp+280h] [rbp-588h] BYREF
  _QWORD *v316; // [rsp+288h] [rbp-580h] BYREF
  _QWORD *v317; // [rsp+290h] [rbp-578h] BYREF
  _QWORD *v318; // [rsp+298h] [rbp-570h] BYREF
  _QWORD *v319; // [rsp+2A0h] [rbp-568h] BYREF
  _QWORD *v320; // [rsp+2A8h] [rbp-560h] BYREF
  _QWORD *v321; // [rsp+2D0h] [rbp-538h] BYREF
  _QWORD *v322; // [rsp+2D8h] [rbp-530h] BYREF
  _QWORD *v323; // [rsp+2E0h] [rbp-528h] BYREF
  _QWORD *v324; // [rsp+2E8h] [rbp-520h] BYREF
  _QWORD *v325; // [rsp+2F0h] [rbp-518h] BYREF
  _BYTE v326[16]; // [rsp+2F8h] [rbp-510h] BYREF
  _QWORD *v327; // [rsp+310h] [rbp-4F8h] BYREF
  _QWORD *v328; // [rsp+318h] [rbp-4F0h] BYREF
  _BYTE v329[16]; // [rsp+320h] [rbp-4E8h] BYREF
  __int64 v330; // [rsp+330h] [rbp-4D8h]
  int v331; // [rsp+340h] [rbp-4C8h] BYREF
  PVOID v332; // [rsp+348h] [rbp-4C0h]
  PVOID v333; // [rsp+350h] [rbp-4B8h]
  _WORD v334[260]; // [rsp+358h] [rbp-4B0h] BYREF
  _WORD v335[260]; // [rsp+560h] [rbp-2A8h] BYREF
  PVOID v336; // [rsp+768h] [rbp-A0h]

  v330 = -2;
  v298 = a4;
  v284[0] = a3;
  Handle[0] = this;
  *(_QWORD *)v296 = a2;
  v301[0] = a3;
  v286 = (const char *)a4;
  v282 = (int *)((char *)this + 280);
  if ( *((_DWORD *)this + 70) )
  {
    *(_QWORD *)&UnicodeString.Length = (char *)this + 280;
    v297 = 0;
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x4000000u, "%hs: Enabling SE_SECURITY_NAME privilege", "CMigrateFramework::DoExecute");
    WdsSetupLogMessageW(
      v7,
      819200,
      L"D",
      0,
      8849,
      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
      L"CMigrateFramework::DoExecute",
      v6,
      LastError,
      0,
      0);
    if ( !(unsigned int)SPEnablePrivilege(L"SeSecurityPrivilege", 1, &v297) )
    {
      v8 = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(
              0x2000000u,
              "%hs: Cannot enable SE_SECURITY_NAME privilege",
              "CMigrateFramework::DoExecute");
      WdsSetupLogMessageW(
        v10,
        819200,
        L"D",
        0,
        8852,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v9,
        v8,
        0,
        0);
    }
    v11 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 312);
    v12 = SPGetStoredString(a2, v11);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v303, v12);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v303) )
    {
      v13 = GetLastError();
      v14 = CurrentIP();
      v15 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v303);
      CString = (const char *)UnBCL::String::get_CString(v15);
      v17 = ConstructPartialMsgW(0x4000000u, "%s is %s", (const char *)L"MIG_SCENARIO_DATETIME", CString);
      WdsSetupLogMessageW(
        v17,
        819200,
        L"D",
        0,
        8861,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v14,
        v13,
        0,
        0);
      v18 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v303);
      v19 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v309, L"MIG_SCENARIO_DATETIME");
      UnBCL::Environment::SetEnvironmentVar(v19, v18);
      UnBCL::String::~String((UnBCL::String *)v309);
    }
    else
    {
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = ConstructPartialMsgW(0x4000000u, "%s does not exist", (const char *)L"MIG_SCENARIO_DATETIME");
      WdsSetupLogMessageW(
        v22,
        819200,
        L"D",
        0,
        8866,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v21,
        v20,
        0,
        0);
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v299);
    v23 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v309, L"%windir%");
    v24 = UnBCL::Environment::ExpandEnvironmentVariables(v23);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v329, v24);
    UnBCL::String::~String((UnBCL::String *)v309);
    if ( (*(unsigned int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 56LL))(a2) == 4
      || (v25 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v329),
          v26 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 216),
          UnBCL::String::Compare(v26, v25, 1)) )
    {
      UnBCL::SmartPtr<UnBCL::String>::operator=(v299, (char *)this + 216);
    }
    v27 = GetLastError();
    v28 = CurrentIP();
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v299) )
    {
      v29 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299);
      v30 = UnBCL::String::get_CString(v29);
    }
    else
    {
      v30 = L"NULL";
    }
    v31 = ConstructPartialMsgW(
            0x4000000u,
            "%hs: Source OS Windows dir: %s",
            "CMigrateFramework::DoExecute",
            (const char *)v30);
    WdsSetupLogMessageW(
      v31,
      819200,
      L"D",
      0,
      8881,
      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
      L"CMigrateFramework::DoExecute",
      v28,
      v27,
      0,
      0);
    if ( *((int *)this + 70) >= 2 )
    {
      *(_QWORD *)v285 = 0;
      UnBCL::Exception::Exception((UnBCL::Exception *)v302);
      v302[0] = &`CMigrateFramework::DoExecute'::`20'::CXXXXXHandledException::`vftable';
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v300, 0);
      v284[1] = 0;
      v284[0] = &Mig::CAutoDelete<UnBCL::String *>::`vftable';
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v299) )
      {
        v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299);
        v40 = UnBCL::String::get_CString(v39);
        v34 = SPMountOfflineHive(v40, L"SECURITY", L"$OFFLINE_RW$SECURITY");
        *(_QWORD *)v285 = v34;
        if ( !v34 )
        {
          v191 = GetLastError();
          v192 = v191 < 0;
          if ( v191 > 0 )
            v192 = 1;
          if ( v192 )
          {
            v193 = GetLastError();
            v194 = v193;
            if ( v193 > 0 )
              v194 = (unsigned __int16)v193 | 0x80070000;
          }
          else
          {
            v194 = -2147467259;
          }
          v195 = GetLastError();
          v196 = CurrentIP();
          v197 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299);
          v198 = (const char *)UnBCL::String::get_CString(v197);
          v199 = ConstructPartialMsgW(
                   0x2000000u,
                   "CMigrateFramework::DoExecute: Cannot load security hive for source offline OS %s. Error: 0x%08X",
                   v198,
                   v194);
          WdsSetupLogMessageW(
            v199,
            819200,
            L"D",
            0,
            8905,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CMigrateFramework::DoExecute",
            v196,
            v195,
            0,
            0);
          v312 = v302;
          throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`20'::CXXXXXHandledException **)&v312;
        }
      }
      else
      {
        v32 = UnBCL::Object::operator new(0x18u);
        v33 = v32;
        P[0] = v32;
        if ( v32 )
        {
          UnBCL::String::String((UnBCL::String *)v32, L"SECURITY");
          *v33 = &UnBCL::String::`local vftable';
        }
        else
        {
          v33 = 0;
        }
        v34 = HKEY_LOCAL_MACHINE;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v304, v33);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v300, v304);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v304);
      }
      v35 = (struct UnBCL::String **)(*(__int64 (__fastcall **)(void **))v284[0])(v284);
      v36 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v300);
      RegSecurityInfo = pGetRegSecurityInfo(v34, v36, v37, v35);
      if ( RegSecurityInfo < 0
        || (P[0] = 0, (*((unsigned __int8 (__fastcall **)(void **, PVOID *))v284[0] + 5))(v284, P)) )
      {
        v200 = GetLastError();
        v201 = CurrentIP();
        v202 = ConstructPartialMsgW(
                 0x2000000u,
                 "CMigrateFramework::DoExecute: Cannot get security info for the source security hive. Error: 0x%08X",
                 RegSecurityInfo);
        WdsSetupLogMessageW(
          v202,
          819200,
          L"D",
          0,
          8921,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CMigrateFramework::DoExecute",
          v201,
          v200,
          0,
          0);
        v314 = v302;
        throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`20'::CXXXXXHandledException **)&v314;
      }
      v187 = (UnBCL::String *)(*((__int64 (__fastcall **)(void **))v284[0] + 1))(v284);
      v188 = UnBCL::String::get_CString(v187);
      if ( UnBCL::String::Compare(v188, L"D:(A;CI;KA;;;SY)(A;CI;RCWD;;;BA)", 1) )
      {
        v189 = (UnBCL::String *)(*((__int64 (__fastcall **)(void **))v284[0] + 1))(v284);
        v190 = UnBCL::String::get_CString(v189);
        UnBCL::String::Compare(v190, L"D:P(A;CI;KA;;;SY)(A;CI;RCWD;;;BA)", 1);
      }
      Mig::CAutoDelete<UnBCL::String *>::~CAutoDelete<UnBCL::String *>(v284);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v300);
      pExceptionObject = v302;
      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`20'::CXXXXXHandledException **)&pExceptionObject;
    }
    v41 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, L"WINDOWS");
    v42 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 232);
    v43 = UnBCL::Path::Combine(v42, v41);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v283, v43);
    UnBCL::String::~String((UnBCL::String *)v304);
    memset_0(&v288, 0, 0x40u);
    memset_0(&v331, 0, 0x478u);
    v296[0] = 0;
    *(_QWORD *)v285 = 0;
    v286 = UnBCL::SmartPtr<CSPMigProgress>::`vftable';
    *(_QWORD *)v287 = 0;
    UnBCL::Exception::Exception((UnBCL::Exception *)v302);
    v302[0] = &`CMigrateFramework::DoExecute'::`46'::CXXXXXHandledException::`vftable';
    if ( !*((_WORD *)this + 104) )
    {
      if ( *v282 >= 2 )
      {
        v270 = GetLastError();
        v271 = CurrentIP();
        v272 = ConstructPartialMsgW(
                 0x2000000u,
                 "Cannot migrate framework without setting the correct drive letter first");
        WdsSetupLogMessageW(
          v272,
          819200,
          L"D",
          0,
          9129,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CMigrateFramework::DoExecute",
          v271,
          v270,
          0,
          0);
        v319 = v302;
        throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v319;
      }
LABEL_113:
      v108 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&UnicodeString, L"MigLog.xml");
      v109 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 16LL))(a2);
      v110 = UnBCL::Path::Combine(v109, v108);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v304, v110);
      UnBCL::String::~String((UnBCL::String *)&UnicodeString);
      v111 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v304);
      v112 = UnBCL::String::get_CString(v111);
      SetEnvironmentVariableW(L"MIG_ENABLE_DIAG", v112);
      SetEnvironmentVariableW(L"MIG_DIAG_APPEND", L"Yes");
      LODWORD(v108) = GetLastError();
      v113 = CurrentIP();
      v114 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v304);
      v115 = (const char *)UnBCL::String::get_CString(v114);
      v116 = ConstructPartialMsgW(0x4000000u, "Diagnostic file: %s", v115);
      WdsSetupLogMessageW(
        v116,
        819200,
        L"D",
        0,
        9137,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v113,
        (_DWORD)v108,
        0,
        0);
      SetEnvironmentVariableW(L"MIG_PROCESS_DEFAULT_USER_AS_USER", L"Yes");
      v117 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)P, L"SetupPlatform.cfg");
      v118 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
      v119 = UnBCL::Path::Combine(v118, v117);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v309, v119);
      UnBCL::String::~String((UnBCL::String *)P);
      v120 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v309);
      v121 = UnBCL::String::get_CString(v120);
      v122 = SPGetSectionContent(v121, L"Migration.VerbosePatterns");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v326, v122);
      if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v326) )
      {
        v123 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v326);
        v124 = UnBCL::String::get_CString(v123);
      }
      else
      {
        v124 = 0;
      }
      SetEnvironmentVariableW(L"MIG_VERBOSE_APPLY_PATTERNS", v124);
      v125 = (unsigned int)(*v282 - 4) <= 1;
      v276 = v125;
      v126 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&UnicodeString, L"Framework");
      v127 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 32) + 16LL))(
                                             *((_QWORD *)this + 32),
                                             **((_QWORD **)this + 32));
      v128 = UnBCL::Path::Combine(v127, v126);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v300, v128);
      UnBCL::String::~String((UnBCL::String *)&UnicodeString);
      v129 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)P, L"Framework");
      v130 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
      v131 = UnBCL::Path::Combine(v130, v129);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v308, v131);
      UnBCL::String::~String((UnBCL::String *)P);
      v132 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&UnicodeString, L"Offline");
      v133 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 16LL))(*((_QWORD *)this + 32));
      v134 = UnBCL::Path::Combine(v133, v132);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v307, v134);
      UnBCL::String::~String((UnBCL::String *)&UnicodeString);
      v135 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)P, L"Offline");
      v136 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
      v137 = UnBCL::Path::Combine(v136, v135);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v306, v137);
      UnBCL::String::~String((UnBCL::String *)P);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v305, 0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v301, 0);
      if ( v125 )
      {
        v138 = GetLastError();
        v139 = CurrentIP();
        v140 = ConstructPartialMsgW(
                 0x4000000u,
                 "%hs: Executing offline gather operation",
                 "CMigrateFramework::DoExecute");
        WdsSetupLogMessageW(
          v140,
          819200,
          L"D",
          0,
          9158,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CMigrateFramework::DoExecute",
          v139,
          v138,
          0,
          0);
        LODWORD(v139) = GetLastError();
        v141 = CurrentIP();
        v142 = (UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
        v143 = UnBCL::String::get_CString(v142);
        v144 = SPGetFreeDiskSpace(v143);
        v145 = ConstructPartialMsgW(0x4000000u, "DISKSPACETRACK: %I64u", v144);
        WdsSetupLogMessageW(
          v145,
          819200,
          L"D",
          0,
          9159,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CMigrateFramework::DoExecute",
          v141,
          v139,
          0,
          0);
        v146 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)P, L"Journals");
        v147 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
        v148 = UnBCL::Path::Combine(v147, v146);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, v148);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v305, &UnicodeString);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
        UnBCL::String::~String((UnBCL::String *)P);
        v149 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v305);
        if ( !UnBCL::Directory::Exists(v149) )
        {
          v150 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v305);
          Dir = UnBCL::Directory::CreateDir(v150);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(&UnicodeString, Dir);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(&UnicodeString);
        }
        v152 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)P, L"Framework");
        v153 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v305);
        v154 = UnBCL::Path::Combine(v153, v152);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, v154);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v301, &UnicodeString);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
        UnBCL::String::~String((UnBCL::String *)P);
        v155 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v301);
        if ( !UnBCL::Directory::Exists(v155) )
        {
          v156 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v301);
          v157 = UnBCL::Directory::CreateDir(v156);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(&UnicodeString, v157);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(&UnicodeString);
        }
        v158 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v310, L"MigJournal.xml");
        v159 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v301);
        v160 = UnBCL::Path::Combine(v159, v158);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(Handle, v160);
        UnBCL::String::~String((UnBCL::String *)v310);
        v161 = (CSPMigProgress *)UnBCL::Object::operator new(0x30u);
        *(_QWORD *)&UnicodeString.Length = v161;
        if ( v161 )
          v162 = CSPMigProgress::CSPMigProgress(v161, *((_DWORD *)this + 8) >> 2, v284[0], v298);
        else
          v162 = 0;
        UnBCL::SmartPtr<CSPMigProgress>::SmartPtr<CSPMigProgress>(P, v162);
        UnBCL::SmartPtr<CSPMigProgress>::operator=(&v286, P);
        P[0] = (PVOID)UnBCL::SmartPtr<CSPMigProgress>::`vftable';
        UnBCL::SmartPtr<COperationsProgress>::DeAssign(P);
        v163 = UnBCL::SmartPtr<UnBCL::String>::get_P(Handle);
        v164 = UnBCL::SmartPtr<UnBCL::String>::get_P(v306);
        v165 = UnBCL::SmartPtr<UnBCL::String>::get_P(v307);
        v166 = *v282;
        v167 = UnBCL::SmartPtr<UnBCL::String>::get_P(v299);
        v168 = SPDoOfflineGather(v167, v166, v165, v164, v163, *(_QWORD *)v287);
        if ( v168 )
        {
          v273 = GetLastError();
          v274 = CurrentIP();
          v275 = ConstructPartialMsgW(0x2000000u, "CMigrateFramework: Offline gather failed. Status: %d", v168);
          WdsSetupLogMessageW(
            v275,
            819200,
            L"D",
            0,
            9185,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CMigrateFramework::DoExecute",
            v274,
            v273,
            0,
            0);
          SPGetHResultFromMigStatus(v168);
          v320 = v302;
          throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v320;
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(Handle);
        v125 = v276;
      }
      v169 = GetLastError();
      v170 = CurrentIP();
      v171 = ConstructPartialMsgW(
               0x4000000u,
               "%hs: Executing framework gather operation",
               "CMigrateFramework::DoExecute");
      WdsSetupLogMessageW(
        v171,
        819200,
        L"D",
        0,
        9191,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v170,
        v169,
        0,
        0);
      LODWORD(v170) = GetLastError();
      v172 = CurrentIP();
      v173 = (UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
      v174 = UnBCL::String::get_CString(v173);
      v175 = SPGetFreeDiskSpace(v174);
      v176 = ConstructPartialMsgW(0x4000000u, "DISKSPACETRACK: %I64u", v175);
      WdsSetupLogMessageW(
        v176,
        819200,
        L"D",
        0,
        9192,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v172,
        v170,
        0,
        0);
      v177 = (CSPMigProgress *)UnBCL::Object::operator new(0x30u);
      *(_QWORD *)&UnicodeString.Length = v177;
      if ( v177 )
      {
        v178 = *((_DWORD *)this + 8);
        if ( v125 )
          v179 = v178 >> 2;
        else
          v179 = v178 >> 1;
        v180 = CSPMigProgress::CSPMigProgress(v177, v179, v284[0], v298);
      }
      else
      {
        v180 = 0;
      }
      UnBCL::SmartPtr<CSPMigProgress>::SmartPtr<CSPMigProgress>(P, v180);
      UnBCL::SmartPtr<CSPMigProgress>::operator=(&v286, P);
      P[0] = (PVOID)UnBCL::SmartPtr<CSPMigProgress>::`vftable';
      UnBCL::SmartPtr<COperationsProgress>::DeAssign(P);
      v181 = *(_QWORD *)v287;
      v182 = *v282 > 1;
      v183 = UnBCL::SmartPtr<UnBCL::String>::get_P(v308);
      v184 = UnBCL::SmartPtr<UnBCL::String>::get_P(v300);
      v185 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P((char *)this + 264);
      v186 = UnBCL::SmartPtr<UnBCL::String>::get_P(v299);
      SPDoFrameworkGather(v186, v185, v184, v183, v182, v181);
    }
    v44 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v45 = UnBCL::String::get_CString(v44);
    v291 = SPMountOfflineHive(v45, L"DEFAULT", L"$OFFLINE_RW$DEFAULT");
    if ( !v291 )
    {
      v203 = GetLastError();
      v204 = v203 < 0;
      if ( v203 > 0 )
        v204 = 1;
      if ( v204 )
      {
        v205 = GetLastError();
        v206 = v205;
        if ( v205 > 0 )
          v206 = (unsigned __int16)v205 | 0x80070000;
      }
      else
      {
        v206 = -2147467259;
      }
      v207 = GetLastError();
      v208 = CurrentIP();
      v209 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
      v210 = (const char *)UnBCL::String::get_CString(v209);
      v211 = ConstructPartialMsgW(
               0x2000000u,
               "CMigrateFramework::DoExecute: Cannot load default hive for offline OS %s. Error: 0x%08X",
               v210,
               v206);
      WdsSetupLogMessageW(
        v211,
        819200,
        L"D",
        0,
        8968,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v208,
        v207,
        0,
        0);
      v315 = v302;
      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v315;
    }
    v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v47 = UnBCL::String::get_CString(v46);
    v292 = SPMountOfflineHive(v47, L"SAM", L"$OFFLINE_RW$SAM");
    if ( !v292 )
    {
      v212 = GetLastError();
      v213 = v212 < 0;
      if ( v212 > 0 )
        v213 = 1;
      if ( v213 )
      {
        v214 = GetLastError();
        v215 = v214;
        if ( v214 > 0 )
          v215 = (unsigned __int16)v214 | 0x80070000;
      }
      else
      {
        v215 = -2147467259;
      }
      v216 = GetLastError();
      v217 = CurrentIP();
      v218 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
      v219 = (const char *)UnBCL::String::get_CString(v218);
      v220 = ConstructPartialMsgW(
               0x2000000u,
               "CMigrateFramework::DoExecute: Cannot load sam hive for offline OS %s. Error: 0x%08X",
               v219,
               v215);
      WdsSetupLogMessageW(
        v220,
        819200,
        L"D",
        0,
        8975,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v217,
        v216,
        0,
        0);
      v328 = v302;
      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v328;
    }
    v48 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v49 = UnBCL::String::get_CString(v48);
    v293 = SPMountOfflineHive(v49, L"SECURITY", L"$OFFLINE_RW$SECURITY");
    if ( !v293 )
    {
      v221 = GetLastError();
      v222 = v221 < 0;
      if ( v221 > 0 )
        v222 = 1;
      if ( v222 )
      {
        v223 = GetLastError();
        v224 = v223;
        if ( v223 > 0 )
          v224 = (unsigned __int16)v223 | 0x80070000;
      }
      else
      {
        v224 = -2147467259;
      }
      v225 = GetLastError();
      v226 = CurrentIP();
      v227 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
      v228 = (const char *)UnBCL::String::get_CString(v227);
      v229 = ConstructPartialMsgW(
               0x2000000u,
               "CMigrateFramework::DoExecute: Cannot load security hive for offline OS %s. Error: 0x%08X",
               v228,
               v224);
      WdsSetupLogMessageW(
        v229,
        819200,
        L"D",
        0,
        8982,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v226,
        v225,
        0,
        0);
      v327 = v302;
      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v327;
    }
    v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v51 = UnBCL::String::get_CString(v50);
    v294 = SPMountOfflineHive(v51, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
    if ( !v294 )
    {
      v230 = GetLastError();
      v231 = v230 < 0;
      if ( v230 > 0 )
        v231 = 1;
      if ( v231 )
      {
        v232 = GetLastError();
        v233 = v232;
        if ( v232 > 0 )
          v233 = (unsigned __int16)v232 | 0x80070000;
      }
      else
      {
        v233 = -2147467259;
      }
      v234 = GetLastError();
      v235 = CurrentIP();
      v236 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
      v237 = (const char *)UnBCL::String::get_CString(v236);
      v238 = ConstructPartialMsgW(
               0x2000000u,
               "CMigrateFramework::DoExecute: Cannot load software hive for offline OS %s. Error: 0x%08X",
               v237,
               v233);
      WdsSetupLogMessageW(
        v238,
        819200,
        L"D",
        0,
        8989,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v235,
        v234,
        0,
        0);
      v325 = v302;
      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v325;
    }
    v52 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v53 = UnBCL::String::get_CString(v52);
    hKey = SPMountOfflineHive(v53, L"SYSTEM", L"$OFFLINE_RW$SYSTEM");
    if ( !hKey )
    {
      v239 = GetLastError();
      v240 = v239 < 0;
      if ( v239 > 0 )
        v240 = 1;
      if ( v240 )
      {
        v241 = GetLastError();
        v242 = v241;
        if ( v241 > 0 )
          v242 = (unsigned __int16)v241 | 0x80070000;
      }
      else
      {
        v242 = -2147467259;
      }
      v243 = GetLastError();
      v244 = CurrentIP();
      v245 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
      v246 = (const char *)UnBCL::String::get_CString(v245);
      v247 = ConstructPartialMsgW(
               0x2000000u,
               "CMigrateFramework::DoExecute: Cannot load system hive for offline OS %s. Error: 0x%08X",
               v246,
               v242);
      WdsSetupLogMessageW(
        v247,
        819200,
        L"D",
        0,
        8996,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CMigrateFramework::DoExecute",
        v244,
        v243,
        0,
        0);
      v323 = v302;
      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v323;
    }
    v54 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v55 = UnBCL::String::get_CString(v54);
    UnicodeString = 0;
    if ( v55 )
    {
      lpMem = 0;
      v56 = RtlDosPathNameToNtPathName_U_WithStatus(v55, &UnicodeString, 0, 0);
      if ( v56 >= 0 || (v57 = v56 | 0x10000000, v57 >= 0) )
        v57 = StrAllocatingPrintf(&lpMem, L"%wZ", &UnicodeString);
      RtlFreeUnicodeString(&UnicodeString);
      if ( v57 >= 0 )
      {
        v58 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 232);
        v59 = UnBCL::String::get_CString(v58);
        UnicodeString = 0;
        if ( v59 )
        {
          v290 = 0;
          v60 = RtlDosPathNameToNtPathName_U_WithStatus(v59, &UnicodeString, 0, 0);
          if ( v60 >= 0 || (v61 = v60 | 0x10000000, v61 >= 0) )
            v61 = StrAllocatingPrintf(&v290, L"%wZ", &UnicodeString);
          RtlFreeUnicodeString(&UnicodeString);
          if ( v61 >= 0 )
          {
            v288 = 2;
            String = (const char *)RegGetStringEx(v294, L"Microsoft\\Windows NT\\CurrentVersion", L"SYSTEMROOT", 0);
            *(_QWORD *)&UnicodeString.Length = String;
            *(_QWORD *)v285 = String;
            v63 = GetLastError();
            v64 = CurrentIP();
            if ( !String )
            {
              v248 = ConstructPartialMsgW(
                       0x4000000u,
                       "CMigrateFramework::DoExecute: Could not find value %s in %s",
                       (const char *)L"SYSTEMROOT",
                       (const char *)L"Microsoft\\Windows NT\\CurrentVersion");
              WdsSetupLogMessageW(
                v248,
                819200,
                L"D",
                0,
                9020,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"CMigrateFramework::DoExecute",
                v64,
                v63,
                0,
                0);
              v249 = GetLastError();
              v250 = v249 < 0;
              if ( v249 > 0 )
                v250 = 1;
              if ( v250 )
                GetLastError();
              v322 = v302;
              throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v322;
            }
            v65 = ConstructPartialMsgW(0x4000000u, "CMigrateFramework::DoExecute: New system's SystemRoot: %s", String);
            WdsSetupLogMessageW(
              v65,
              819200,
              L"D",
              0,
              9025,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"CMigrateFramework::DoExecute",
              v64,
              v63,
              0,
              0);
            v66 = L"C:\\Windows";
            if ( *(_WORD *)String )
              v66 = (const wchar_t *)String;
            v67 = 2147483646;
            v68 = 260;
            v69 = 260;
            v70 = v334;
            do
            {
              if ( !v67 )
                goto LABEL_50;
              v71 = *v66;
              if ( !*v66 )
                break;
              ++v66;
              *v70++ = v71;
              --v67;
              --v69;
            }
            while ( v69 );
            if ( !v69 )
              --v70;
LABEL_50:
            *v70 = 0;
            v72 = 2147483646;
            v73 = L"?:\\";
            v74 = L"?:\\";
            v75 = 260;
            v76 = v335;
            do
            {
              if ( !v72 )
                goto LABEL_56;
              v77 = *v74;
              if ( !*v74 )
                break;
              ++v74;
              *v76++ = v77;
              --v72;
              --v75;
            }
            while ( v75 );
            if ( !v75 )
              --v76;
LABEL_56:
            *v76 = 0;
            v335[0] = *((_WORD *)this + 104);
            v334[3] = 0;
            v335[3] = 0;
            v310[0] = 0;
            v310[1] = 0;
            v311 = 0;
            v310[2] = SclLogCallback;
            v331 = 16130;
            v78 = GetLastError();
            v79 = CurrentIP();
            v80 = ConstructPartialMsgW(
                    0x4000000u,
                    "CMigrateFramework::DoExecute: ModifyOfflineRegHives: Changing paths from %s to %s",
                    (const char *)v334,
                    (const char *)v335);
            WdsSetupLogMessageW(
              v80,
              819200,
              L"D",
              0,
              9046,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"CMigrateFramework::DoExecute",
              v79,
              v78,
              0,
              0);
            v81 = SclExecuteRequest(&v331, &v288, v310);
            if ( v81 < 0 )
            {
              v251 = GetLastError();
              v252 = CurrentIP();
              v253 = ConstructPartialMsgW(
                       0x2000000u,
                       "CMigrateFramework::DoExecute: Updating paths in hives failed. Status = 0x%08X",
                       v81);
              WdsSetupLogMessageW(
                v253,
                819200,
                L"D",
                0,
                9050,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"CMigrateFramework::DoExecute",
                v252,
                v251,
                0,
                0);
              v321 = v302;
              throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v321;
            }
            memset_0(&v331, 0, 0x478u);
            if ( v288 )
            {
              if ( v288 == 1 )
              {
                if ( lpMem || v290 || v291 || v292 || v293 || v294 || (v82 = 1, hKey) )
                  v82 = 0;
                if ( v82 )
                {
LABEL_70:
                  Handle[0] = 0;
                  v83 = SclpStateOpenRequestKey(&v288, Handle);
                  if ( v83 >= 0 )
                  {
                    v83 = SclRegValueExists(Handle[0]);
                    if ( v83 >= 0 )
                    {
                      v83 = SclRegValueExists(Handle[0]);
                      if ( v83 >= 0 )
                      {
                        v83 = SclRegValueExists(Handle[0]);
                        if ( v83 >= 0 )
                        {
                          v83 = SclRegValueExists(Handle[0]);
                          if ( v83 >= 0 )
                          {
                            v83 = SclRegValueExists(Handle[0]);
                            if ( v83 >= 0 )
                            {
                              v83 = SclRegValueExists(Handle[0]);
                              if ( v83 >= 0 )
                              {
                                v83 = SclRegValueExists(Handle[0]);
                                if ( v83 >= 0 )
                                {
                                  if ( (unsigned __int8)SclRequestIsValid(&v288, &v331) )
                                    goto LABEL_81;
                                  SclLogGenericMessage(
                                    0,
                                    3,
                                    (unsigned int)SclEvent_Generic_Error,
                                    1306,
                                    (__int64)"SclGetPendedRequest");
                                  v83 = -1073741637;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  SclFreeRequest(&v331);
LABEL_81:
                  if ( Handle[0] )
                    NtClose(Handle[0]);
                  if ( v83 >= 0 )
                  {
                    v84 = 0;
                    v296[0] = 1;
                    if ( (v331 & 2) != 0 )
                    {
                      v85 = GetLastError();
                      v86 = CurrentIP();
                      v87 = ConstructPartialMsgW(
                              0x4000000u,
                              "CMigrateFramework::DoExecute: Setting WinDirNew for setupcl pended request in new system");
                      WdsSetupLogMessageW(
                        v87,
                        819200,
                        L"D",
                        0,
                        9072,
                        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                        L"CMigrateFramework::DoExecute",
                        v86,
                        v85,
                        0,
                        0);
                      v88 = v335;
                      v89 = 2147483646;
                      do
                      {
                        if ( !v89 )
                          goto LABEL_91;
                        v90 = *v73;
                        if ( !*v73 )
                          break;
                        ++v73;
                        *v88++ = v90;
                        --v89;
                        --v68;
                      }
                      while ( v68 );
                      if ( !v68 )
                        --v88;
LABEL_91:
                      *v88 = 0;
                      v335[0] = *((_WORD *)this + 104);
                      v84 = 1;
                    }
                    if ( *v282 < 2 )
                    {
                      if ( !v84 )
                      {
LABEL_96:
                        if ( v332 )
                        {
                          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v332);
                          v332 = 0;
                        }
                        if ( v333 )
                        {
                          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v333);
                          v333 = 0;
                        }
                        if ( v336 )
                          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v336);
                        memset_0(&v331, 0, 0x478u);
                        v296[0] = 0;
                        ProcessHeap = GetProcessHeap();
                        v96 = *(_QWORD *)&UnicodeString.Length;
                        if ( HeapFree(ProcessHeap, 0, *(LPVOID *)&UnicodeString.Length) )
                          v96 = 0;
                        *(_QWORD *)v285 = v96;
                        if ( lpMem )
                        {
                          v97 = GetProcessHeap();
                          v98 = HeapFree(v97, 0, lpMem);
                          v99 = lpMem;
                          if ( v98 )
                            v99 = 0;
                          lpMem = v99;
                        }
                        if ( v290 )
                        {
                          v100 = GetProcessHeap();
                          v101 = HeapFree(v100, 0, v290);
                          v102 = v290;
                          if ( v101 )
                            v102 = 0;
                          v290 = v102;
                        }
                        RegCloseKey(hKey);
                        SPUnloadKey(v103, L"$OFFLINE_RW$SYSTEM");
                        RegCloseKey(v294);
                        SPUnloadKey(v104, L"$OFFLINE_RW$SOFTWARE");
                        RegCloseKey(v293);
                        SPUnloadKey(v105, L"$OFFLINE_RW$SECURITY");
                        RegCloseKey(v292);
                        SPUnloadKey(v106, L"$OFFLINE_RW$SAM");
                        RegCloseKey(v291);
                        SPUnloadKey(v107, L"$OFFLINE_RW$DEFAULT");
                        memset_0(&v288, 0, 0x40u);
                        goto LABEL_113;
                      }
                    }
                    else
                    {
                      v91 = GetLastError();
                      v92 = CurrentIP();
                      v93 = ConstructPartialMsgW(
                              0x4000000u,
                              "CMigrateFramework::DoExecute: Pending upgrade hive update request for setupcl");
                      WdsSetupLogMessageW(
                        v93,
                        819200,
                        L"D",
                        0,
                        9084,
                        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                        L"CMigrateFramework::DoExecute",
                        v92,
                        v91,
                        0,
                        0);
                      v331 |= 0x20u;
                    }
                    v94 = SclPendRequest(&v331, &v288);
                    if ( v94 < 0 )
                    {
                      v257 = GetLastError();
                      v258 = CurrentIP();
                      v259 = ConstructPartialMsgW(
                               0x2000000u,
                               "CMigrateFramework::DoExecute: Pending updated setupcl request failed. Status = 0x%08X",
                               v94);
                      WdsSetupLogMessageW(
                        v259,
                        819200,
                        L"D",
                        0,
                        9107,
                        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                        L"CMigrateFramework::DoExecute",
                        v258,
                        v257,
                        0,
                        0);
                      v324 = v302;
                      throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v324;
                    }
                    goto LABEL_96;
                  }
LABEL_188:
                  v254 = GetLastError();
                  v255 = CurrentIP();
                  v256 = ConstructPartialMsgW(
                           0x2000000u,
                           "CMigrateFramework::DoExecute: Getting pended setupcl request failed. Status = 0x%08X",
                           v83);
                  WdsSetupLogMessageW(
                    v256,
                    819200,
                    L"D",
                    0,
                    9064,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                    L"CMigrateFramework::DoExecute",
                    v255,
                    v254,
                    0,
                    0);
                  v316 = v302;
                  throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v316;
                }
              }
              else if ( v288 == 2 )
              {
                goto LABEL_70;
              }
            }
            v83 = -1073741811;
            goto LABEL_188;
          }
        }
        else
        {
          v61 = -2147024809;
        }
        v260 = GetLastError();
        v261 = CurrentIP();
        v262 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 232);
        v263 = (const char *)UnBCL::String::get_CString(v262);
        v264 = ConstructPartialMsgW(
                 0x2000000u,
                 "CMigrateFramework::DoExecute: Cannot convert new OS Dir %s to NT path. Error: 0x%08X",
                 v263,
                 v61);
        WdsSetupLogMessageW(
          v264,
          819200,
          L"D",
          0,
          9009,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CMigrateFramework::DoExecute",
          v261,
          v260,
          0,
          0);
        v317 = v302;
        throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v317;
      }
    }
    else
    {
      v57 = -2147024809;
    }
    v265 = GetLastError();
    v266 = CurrentIP();
    v267 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v283);
    v268 = (const char *)UnBCL::String::get_CString(v267);
    v269 = ConstructPartialMsgW(
             0x2000000u,
             "CMigrateFramework::DoExecute: Cannot convert new OS WinDir %s to NT path. Error: 0x%08X",
             v268,
             v57);
    WdsSetupLogMessageW(
      v269,
      819200,
      L"D",
      0,
      9003,
      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
      L"CMigrateFramework::DoExecute",
      v266,
      v265,
      0,
      0);
    v318 = v302;
    throw (`CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`46'::CXXXXXHandledException **)&v318;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1801fee00  push    rbx
0x1801fee02  push    rsi
0x1801fee03  push    rdi
0x1801fee04  push    r12
0x1801fee06  push    r13
0x1801fee08  push    r14
0x1801fee0a  push    r15
0x1801fee0c  sub     rsp, 7D0h
0x1801fee13  mov     [rsp+808h+var_4D8], 0FFFFFFFFFFFFFFFEh
0x1801fee1f  mov     rax, cs:__security_cookie
0x1801fee26  xor     rax, rsp
0x1801fee29  mov     [rsp+808h+var_48], rax
0x1801fee31  mov     [rsp+808h+var_6B8], r9
0x1801fee39  mov     [rsp+808h+var_730], r8
0x1801fee41  mov     [rsp+808h+var_790], rdx
0x1801fee46  mov     rax, rcx
0x1801fee49  mov     [rsp+808h+var_798], rcx
0x1801fee4e  mov     [rsp+808h+Handle], rcx
0x1801fee56  mov     qword ptr [rsp+808h+var_6C8], rdx
0x1801fee5e  mov     [rsp+808h+var_690], r8
0x1801fee66  mov     [rsp+808h+var_718], r9
0x1801fee6e  add     rax, 118h
0x1801fee74  mov     [rsp+808h+var_748], rax
0x1801fee7c  xor     esi, esi
0x1801fee7e  cmp     [rax], esi
0x1801fee80  jnz     short loc_1801FEE8C
0x1801fee82  mov     eax, 80070057h
0x1801fee87  jmp     loc_180201524
0x1801fee8c  mov     qword ptr [rsp+808h+UnicodeString.Length], rax
0x1801fee94  mov     [rsp+808h+var_6C0], esi
0x1801fee9b  call    cs:__imp_GetLastError
0x1801feea1  mov     edi, eax
0x1801feea3  call    cs:__imp_CurrentIP
0x1801feea9  mov     rbx, rax
0x1801feeac  lea     r8, aCmigrateframew_16; "CMigrateFramework::DoExecute"
0x1801feeb3  lea     rdx, aHsEnablingSeSe; "%hs: Enabling SE_SECURITY_NAME privileg"...
0x1801feeba  mov     ecx, 4000000h; unsigned int
0x1801feebf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801feec4  mov     dword ptr [rsp+808h+var_7B8], esi
0x1801feec8  mov     qword ptr [rsp+808h+var_7C0], rsi
0x1801feecd  mov     [rsp+808h+var_7C8], edi
0x1801feed1  mov     qword ptr [rsp+808h+var_7D0], rbx
0x1801feed6  lea     r14, aCmigrateframew_15; "CMigrateFramework::DoExecute"
0x1801feedd  mov     [rsp+808h+var_7D8], r14
0x1801feee2  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801feee9  mov     qword ptr [rsp+808h+var_7E0], rcx
0x1801feeee  mov     [rsp+808h+var_7E8], 2291h
0x1801feef6  xor     r9d, r9d
0x1801feef9  lea     r12, aD_0; "D"
0x1801fef00  mov     r8, r12
0x1801fef03  mov     r13d, 0C8000h
0x1801fef09  mov     edx, r13d
0x1801fef0c  mov     rcx, rax
0x1801fef0f  call    cs:__imp_WdsSetupLogMessageW
0x1801fef15  lea     r8, [rsp+808h+var_6C0]; int *
0x1801fef1d  mov     r15d, 1
0x1801fef23  mov     edx, r15d; int
0x1801fef26  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x1801fef2d  call    ?SPEnablePrivilege@@YAHPEBGHPEAH@Z; SPEnablePrivilege(ushort const *,int,int *)
0x1801fef32  test    eax, eax
0x1801fef34  jnz     short loc_1801FEF9C
0x1801fef36  call    cs:__imp_GetLastError
0x1801fef3c  mov     edi, eax
0x1801fef3e  call    cs:__imp_CurrentIP
0x1801fef44  mov     rbx, rax
0x1801fef47  lea     r8, aCmigrateframew_16; "CMigrateFramework::DoExecute"
0x1801fef4e  lea     rdx, aHsCannotEnable; "%hs: Cannot enable SE_SECURITY_NAME pri"...
0x1801fef55  mov     ecx, 2000000h; unsigned int
0x1801fef5a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801fef5f  mov     dword ptr [rsp+808h+var_7B8], esi
0x1801fef63  mov     qword ptr [rsp+808h+var_7C0], rsi
0x1801fef68  mov     [rsp+808h+var_7C8], edi
0x1801fef6c  mov     qword ptr [rsp+808h+var_7D0], rbx
0x1801fef71  mov     [rsp+808h+var_7D8], r14
0x1801fef76  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801fef7d  mov     qword ptr [rsp+808h+var_7E0], rcx
0x1801fef82  mov     [rsp+808h+var_7E8], 2294h
0x1801fef8a  xor     r9d, r9d
0x1801fef8d  mov     r8, r12
0x1801fef90  mov     edx, r13d
0x1801fef93  mov     rcx, rax
0x1801fef96  call    cs:__imp_WdsSetupLogMessageW
0x1801fef9c  mov     [rsp+808h+var_7A4], esi
0x1801fefa0  mov     rcx, [rsp+808h+var_798]
0x1801fefa5  add     rcx, 138h
0x1801fefac  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801fefb2  mov     rdx, rax; struct UnBCL::String *
0x1801fefb5  mov     rcx, [rsp+808h+var_790]; struct IExecutionContext *
0x1801fefba  call    ?SPGetStoredString@@YAPEAVString@UnBCL@@PEAUIExecutionContext@@PEAV12@@Z; SPGetStoredString(IExecutionContext *,UnBCL::String *)
0x1801fefbf  mov     rdx, rax
0x1801fefc2  lea     rcx, [rsp+808h+var_648]
0x1801fefca  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801fefd0  nop
0x1801fefd1  lea     rcx, [rsp+808h+var_648]
0x1801fefd9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801fefdf  test    rax, rax
0x1801fefe2  jz      loc_1801FF0AC
0x1801fefe8  call    cs:__imp_GetLastError
0x1801fefee  mov     edi, eax
0x1801feff0  call    cs:__imp_CurrentIP
0x1801feff6  mov     rbx, rax
0x1801feff9  lea     rcx, [rsp+808h+var_648]
0x1801ff001  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801ff007  mov     rcx, rax
0x1801ff00a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801ff010  mov     r9, rax
0x1801ff013  lea     r8, aMigScenarioDat; "MIG_SCENARIO_DATETIME"
0x1801ff01a  lea     rdx, aSIsS; "%s is %s"
0x1801ff021  mov     ecx, 4000000h; unsigned int
0x1801ff026  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801ff02b  mov     dword ptr [rsp+808h+var_7B8], esi
0x1801ff02f  mov     qword ptr [rsp+808h+var_7C0], rsi
0x1801ff034  mov     [rsp+808h+var_7C8], edi
0x1801ff038  mov     qword ptr [rsp+808h+var_7D0], rbx
0x1801ff03d  mov     [rsp+808h+var_7D8], r14
0x1801ff042  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801ff049  mov     qword ptr [rsp+808h+var_7E0], rcx
0x1801ff04e  mov     [rsp+808h+var_7E8], 229Dh
0x1801ff056  xor     r9d, r9d
0x1801ff059  mov     r8, r12
0x1801ff05c  mov     edx, r13d
0x1801ff05f  mov     rcx, rax
0x1801ff062  call    cs:__imp_WdsSetupLogMessageW
0x1801ff068  lea     rcx, [rsp+808h+var_648]
0x1801ff070  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ff076  mov     rbx, rax
0x1801ff079  lea     rdx, aMigScenarioDat; "MIG_SCENARIO_DATETIME"
0x1801ff080  lea     rcx, [rsp+808h+var_5E0]
0x1801ff088  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801ff08e  nop
0x1801ff08f  mov     rdx, rbx
0x1801ff092  mov     rcx, rax
0x1801ff095  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x1801ff09b  nop
0x1801ff09c  lea     rcx, [rsp+808h+var_5E0]
0x1801ff0a4  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801ff0aa  jmp     short loc_1801FF112
0x1801ff0ac  call    cs:__imp_GetLastError
0x1801ff0b2  mov     edi, eax
0x1801ff0b4  call    cs:__imp_CurrentIP
0x1801ff0ba  mov     rbx, rax
0x1801ff0bd  lea     r8, aMigScenarioDat; "MIG_SCENARIO_DATETIME"
0x1801ff0c4  lea     rdx, aSDoesNotExist; "%s does not exist"
0x1801ff0cb  mov     ecx, 4000000h; unsigned int
0x1801ff0d0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801ff0d5  mov     dword ptr [rsp+808h+var_7B8], esi
0x1801ff0d9  mov     qword ptr [rsp+808h+var_7C0], rsi
0x1801ff0de  mov     [rsp+808h+var_7C8], edi
0x1801ff0e2  mov     qword ptr [rsp+808h+var_7D0], rbx
0x1801ff0e7  mov     [rsp+808h+var_7D8], r14
0x1801ff0ec  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801ff0f3  mov     qword ptr [rsp+808h+var_7E0], rcx
0x1801ff0f8  mov     [rsp+808h+var_7E8], 22A2h
0x1801ff100  xor     r9d, r9d
0x1801ff103  mov     r8, r12
0x1801ff106  mov     edx, r13d
0x1801ff109  mov     rcx, rax
0x1801ff10c  call    cs:__imp_WdsSetupLogMessageW
0x1801ff112  lea     rcx, [rsp+808h+var_6B0]
0x1801ff11a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1801ff120  nop
0x1801ff121  lea     rdx, aWindir; "%windir%"
0x1801ff128  lea     rcx, [rsp+808h+var_5E0]
0x1801ff130  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801ff136  nop
0x1801ff137  mov     rcx, rax
0x1801ff13a  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x1801ff140  mov     rdx, rax
0x1801ff143  lea     rcx, [rsp+808h+var_4E8]
0x1801ff14b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801ff151  nop
0x1801ff152  lea     rcx, [rsp+808h+var_5E0]
0x1801ff15a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801ff160  mov     rcx, [rsp+808h+var_790]
0x1801ff165  mov     rax, [rcx]
0x1801ff168  mov     rax, [rax+38h]
0x1801ff16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff171  cmp     eax, 4
0x1801ff174  jz      short loc_1801FF1AC
0x1801ff176  lea     rcx, [rsp+808h+var_4E8]
0x1801ff17e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ff184  mov     rbx, rax
0x1801ff187  mov     rcx, [rsp+808h+var_798]
0x1801ff18c  add     rcx, 0D8h
0x1801ff193  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ff199  mov     r8d, r15d
0x1801ff19c  mov     rdx, rbx
0x1801ff19f  mov     rcx, rax
0x1801ff1a2  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x1801ff1a8  test    eax, eax
0x1801ff1aa  jz      short loc_1801FF1C6
0x1801ff1ac  mov     rdx, [rsp+808h+var_798]
0x1801ff1b1  add     rdx, 0D8h
0x1801ff1b8  lea     rcx, [rsp+808h+var_6B0]
0x1801ff1c0  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1801ff1c6  call    cs:__imp_GetLastError
0x1801ff1cc  mov     ebx, eax
0x1801ff1ce  call    cs:__imp_CurrentIP
0x1801ff1d4  mov     rdi, rax
0x1801ff1d7  lea     rcx, [rsp+808h+var_6B0]
0x1801ff1df  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ff1e5  test    rax, rax
0x1801ff1e8  jz      short loc_1801FF203
0x1801ff1ea  lea     rcx, [rsp+808h+var_6B0]
0x1801ff1f2  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801ff1f8  mov     rcx, rax
0x1801ff1fb  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801ff201  jmp     short loc_1801FF20A
0x1801ff203  lea     rax, aNull_5; "NULL"
0x1801ff20a  mov     r9, rax
0x1801ff20d  lea     r8, aCmigrateframew_16; "CMigrateFramework::DoExecute"
0x1801ff214  lea     rdx, aHsSourceOsWind; "%hs: Source OS Windows dir: %s"
0x1801ff21b  mov     ecx, 4000000h; unsigned int
0x1801ff220  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801ff225  mov     dword ptr [rsp+808h+var_7B8], esi
0x1801ff229  mov     qword ptr [rsp+808h+var_7C0], rsi
0x1801ff22e  mov     [rsp+808h+var_7C8], ebx
0x1801ff232  mov     qword ptr [rsp+808h+var_7D0], rdi
0x1801ff237  mov     [rsp+808h+var_7D8], r14
0x1801ff23c  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801ff243  mov     qword ptr [rsp+808h+var_7E0], rcx
0x1801ff248  mov     [rsp+808h+var_7E8], 22B1h
0x1801ff250  xor     r9d, r9d
0x1801ff253  mov     r8, r12
0x1801ff256  mov     edx, r13d
0x1801ff259  mov     rcx, rax
0x1801ff25c  call    cs:__imp_WdsSetupLogMessageW
0x1801ff262  mov     [rsp+808h+var_79C], esi
0x1801ff266  mov     rdi, [rsp+808h+var_798]
0x1801ff26b  cmp     dword ptr [rdi+118h], 2
0x1801ff272  jl      loc_1801FF48A
0x1801ff278  mov     qword ptr [rsp+808h+var_720], rsi
0x1801ff280  mov     [rsp+808h+var_7A0], esi
0x1801ff284  lea     rcx, [rsp+808h+var_680]
0x1801ff28c  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1801ff292  lea     rax, ??_7CXXXXXHandledException@?BE@??DoExecute@CMigrateFramework@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CMigrateFramework::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`20'::CXXXXXHandledException::`vftable'
0x1801ff299  mov     [rsp+808h+var_680], rax
0x1801ff2a1  xor     edx, edx
0x1801ff2a3  lea     rcx, [rsp+808h+var_6A0]
0x1801ff2ab  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801ff2b1  nop
0x1801ff2b2  mov     [rsp+808h+var_728], rsi
0x1801ff2ba  lea     rax, ??_7?$CAutoDelete@PEAVString@UnBCL@@@Mig@@6B@; const Mig::CAutoDelete<UnBCL::String *>::`vftable'
0x1801ff2c1  mov     [rsp+808h+var_730], rax
0x1801ff2c9  lea     rcx, [rsp+808h+var_6B0]
0x1801ff2d1  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ff2d7  test    rax, rax
0x1801ff2da  jnz     loc_1801FF3D2
0x1801ff2e0  lea     ecx, [rax+18h]
0x1801ff2e3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1801ff2e9  mov     rbx, rax
0x1801ff2ec  mov     [rsp+808h+P], rax
0x1801ff2f4  test    rax, rax
0x1801ff2f7  jz      short loc_1801FF315
0x1801ff2f9  lea     rdx, aSecurity; "SECURITY"
0x1801ff300  mov     rcx, rax
0x1801ff303  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801ff309  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x1801ff310  mov     [rbx], rax
0x1801ff313  jmp     short loc_1801FF318
0x1801ff315  mov     rbx, rsi
0x1801ff318  mov     rdi, 0FFFFFFFF80000002h
0x1801ff31f  mov     rdx, rbx
0x1801ff322  lea     rcx, [rsp+808h+var_638]
0x1801ff32a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801ff330  nop
0x1801ff331  lea     rdx, [rsp+808h+var_638]
0x1801ff339  lea     rcx, [rsp+808h+var_6A0]
0x1801ff341  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1801ff347  nop
0x1801ff348  lea     rcx, [rsp+808h+var_638]
0x1801ff350  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1801ff356  mov     rax, [rsp+808h+var_730]
0x1801ff35e  lea     rcx, [rsp+808h+var_730]
0x1801ff366  mov     rax, [rax]
0x1801ff369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff36e  mov     rbx, rax
0x1801ff371  lea     rcx, [rsp+808h+var_6A0]
0x1801ff379  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ff37f  mov     r9, rbx; struct UnBCL::String **
0x1801ff382  mov     rdx, rax; struct UnBCL::String *
0x1801ff385  mov     rcx, rdi; hKey
0x1801ff388  call    ?pGetRegSecurityInfo@@YAJPEAUHKEY__@@PEAVString@UnBCL@@KPEAPEAV23@@Z; pGetRegSecurityInfo(HKEY__ *,UnBCL::String *,ulong,UnBCL::String * *)
0x1801ff38d  mov     r14d, eax
0x1801ff390  test    eax, eax
0x1801ff392  js      loc_1802016F9
0x1801ff398  mov     [rsp+808h+var_7A4], eax
0x1801ff39c  mov     [rsp+808h+P], rsi
0x1801ff3a4  mov     rcx, [rsp+808h+var_730]
0x1801ff3ac  mov     rax, [rcx+28h]
0x1801ff3b0  lea     rdx, [rsp+808h+P]
0x1801ff3b8  lea     rcx, [rsp+808h+var_730]
0x1801ff3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ff3c5  test    al, al
0x1801ff3c7  jz      loc_180201547
0x1801ff3cd  jmp     loc_1802016F9
0x1801ff3d2  lea     rcx, [rsp+808h+var_6B0]
0x1801ff3da  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801ff3e0  mov     rcx, rax
0x1801ff3e3  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
  ... truncated ...
```
