# CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x180167100`
- end: `0x18016f292`
- name: `?DoExecute@CRelocateOS@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `33170`
- prototype: `int(CRelocateOS *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `68`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180035cc0`
- `0x18003d070`
- `0x1800447d0`
- `0x1800447ec`
- `0x180044810`
- `0x18004d46c`
- `0x180057dec`
- `0x18005dd24`
- `0x18005dde0`
- `0x1800b4770`
- `0x1800b478c`
- `0x18010b740`
- `0x18010f584`
- `0x18011bc64`
- `0x18012a5c0`
- `0x18012aa88`
- `0x18012b0fc`
- `0x180131d68`
- `0x180131d90`
- `0x1801556c4`
- `0x180156428`
- `0x180156484`
- `0x1801564dc`
- `0x18015df34`
- `0x18015df5c`
- `0x18015df84`
- `0x180167100`
- `0x180176a30`
- `0x18017ac00`
- `0x18017af8c`
- `0x1802c6538`
- `0x1802cfe0c`
- `0x1802cff64`
- `0x1802d539c`
- `0x1802d8bfc`
- `0x1802d8e3c`
- `0x1802d8f5c`
- `0x1802dacac`
- `0x1802dd344`
- `0x1802dd3d4`
- `0x1802dd720`
- `0x1802df8e4`
- `0x1802dfd34`
- `0x1802dff40`
- `0x1802e1ef4`
- `0x1802e2078`
- `0x1802e293c`
- `0x1802e2e20`
- `0x1802e4174`

## import_xrefs

- `ntdll!NtClose` at `0x18016baea`
- `ntdll!NtClose` at `0x18016baea`
- `ntdll!RtlInitUnicodeString` at `0x18016b66e`
- `ntdll!RtlInitUnicodeString` at `0x18016b66e`
- `ntdll!NtCreateFile` at `0x18016b6f7`
- `ntdll!NtCreateFile` at `0x18016b6f7`
- `ntdll!NtSetSecurityObject` at `0x18016ba53`
- `ntdll!NtSetSecurityObject` at `0x18016ba53`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18016b48a`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18016b48a`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18016b507`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18016b507`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18016b811`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18016b811`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18016b82f`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18016b82f`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18016b855`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18016b855`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18016b87b`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18016b87b`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18016b899`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18016b899`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x18016b964`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x18016b964`
- `KERNEL32!GetProcessHeap` at `0x18016bb05`
- `KERNEL32!GetProcessHeap` at `0x18016bb05`
- `KERNEL32!HeapFree` at `0x18016bb13`
- `KERNEL32!HeapFree` at `0x18016bb13`
- `KERNEL32!GetLastError` at `0x180167259`
- `KERNEL32!GetLastError` at `0x1801672e2`
- `KERNEL32!GetLastError` at `0x1801673a9`
- `KERNEL32!GetLastError` at `0x1801673bf`
- `KERNEL32!GetLastError` at `0x1801673df`
- `KERNEL32!GetLastError` at `0x1801674ac`
- `KERNEL32!GetLastError` at `0x1801675f8`
- `KERNEL32!GetLastError` at `0x18016760e`
- `KERNEL32!GetLastError` at `0x18016762e`
- `KERNEL32!GetLastError` at `0x180167709`
- `KERNEL32!GetLastError` at `0x1801677b0`
- `KERNEL32!GetLastError` at `0x18016787c`
- `KERNEL32!GetLastError` at `0x180167967`
- `KERNEL32!GetLastError` at `0x18016798c`
- `KERNEL32!GetLastError` at `0x180167a8d`
- `KERNEL32!GetLastError` at `0x180167b5c`
- `KERNEL32!GetLastError` at `0x180167d2d`
- `KERNEL32!GetLastError` at `0x1801680fb`
- `KERNEL32!GetLastError` at `0x1801681e3`
- `KERNEL32!GetLastError` at `0x180168270`
- `KERNEL32!GetLastError` at `0x180168369`
- `KERNEL32!GetLastError` at `0x18016878c`
- `KERNEL32!GetLastError` at `0x180168847`
- `KERNEL32!GetLastError` at `0x180168c08`
- `KERNEL32!GetLastError` at `0x180168ca3`
- `KERNEL32!GetLastError` at `0x180169039`
- `KERNEL32!GetLastError` at `0x1801690dd`
- `KERNEL32!GetLastError` at `0x1801693b6`
- `KERNEL32!GetLastError` at `0x180169453`
- `KERNEL32!GetLastError` at `0x180169537`
- `KERNEL32!GetLastError` at `0x1801696cf`
- `KERNEL32!GetLastError` at `0x1801696e5`
- `KERNEL32!GetLastError` at `0x180169705`
- `KERNEL32!GetLastError` at `0x180169964`
- `KERNEL32!GetLastError` at `0x180169a5a`
- `KERNEL32!GetLastError` at `0x180169acd`
- `KERNEL32!GetLastError` at `0x180169bde`
- `KERNEL32!GetLastError` at `0x180169e3c`
- `KERNEL32!GetLastError` at `0x180169f26`
- `KERNEL32!GetLastError` at `0x18016a11e`
- `KERNEL32!GetLastError` at `0x18016a937`
- `KERNEL32!GetLastError` at `0x18016aa22`
- `KERNEL32!GetLastError` at `0x18016adb7`
- `KERNEL32!GetLastError` at `0x18016aeb8`
- `KERNEL32!GetLastError` at `0x18016af97`
- `KERNEL32!GetLastError` at `0x18016b071`
- `KERNEL32!GetLastError` at `0x18016b273`
- `KERNEL32!GetLastError` at `0x18016b35b`
- `KERNEL32!GetLastError` at `0x18016b511`
- `KERNEL32!GetLastError` at `0x18016b522`
- `KERNEL32!GetLastError` at `0x18016b57f`
- `KERNEL32!GetLastError` at `0x18016b70f`
- `KERNEL32!GetLastError` at `0x18016b972`
- `KERNEL32!GetLastError` at `0x18016b988`
- `KERNEL32!GetLastError` at `0x18016b9b2`
- `KERNEL32!GetLastError` at `0x18016ba6a`
- `KERNEL32!GetLastError` at `0x18016c2a7`
- `KERNEL32!GetLastError` at `0x18016c95a`
- `KERNEL32!GetLastError` at `0x18016cdad`
- `KERNEL32!GetLastError` at `0x18016ce34`
- `KERNEL32!GetLastError` at `0x18016cee2`
- `KERNEL32!GetLastError` at `0x18016d06e`
- `KERNEL32!GetLastError` at `0x18016d1aa`
- `KERNEL32!GetLastError` at `0x18016d1be`
- `KERNEL32!GetLastError` at `0x18016d295`
- `KERNEL32!GetLastError` at `0x18016d3c4`
- `KERNEL32!GetLastError` at `0x18016d423`
- `KERNEL32!GetLastError` at `0x18016d4fa`
- `KERNEL32!GetLastError` at `0x18016d5be`
- `KERNEL32!GetLastError` at `0x18016d662`
- `KERNEL32!GetLastError` at `0x18016d7d9`
- `KERNEL32!GetLastError` at `0x18016d7ef`
- `KERNEL32!GetLastError` at `0x18016d80d`
- `KERNEL32!GetLastError` at `0x18016db11`
- `KERNEL32!GetLastError` at `0x18016db27`
- `KERNEL32!GetLastError` at `0x18016db4c`
- `KERNEL32!GetLastError` at `0x18016dbd7`
- `KERNEL32!GetLastError` at `0x18016dc69`
- `KERNEL32!GetLastError` at `0x18016dd16`
- `KERNEL32!GetLastError` at `0x18016dd2c`
- `KERNEL32!GetLastError` at `0x18016dd51`
- `KERNEL32!GetLastError` at `0x18016de05`
- `KERNEL32!GetLastError` at `0x18016deb1`
- `KERNEL32!GetLastError` at `0x18016dec7`
- `KERNEL32!GetLastError` at `0x18016deec`
- `KERNEL32!GetLastError` at `0x18016df99`
- `KERNEL32!GetLastError` at `0x18016dfaf`
- `KERNEL32!GetLastError` at `0x18016dfd4`
- `KERNEL32!GetLastError` at `0x18016e0dc`
- `KERNEL32!GetLastError` at `0x18016e0f2`
- `KERNEL32!GetLastError` at `0x18016e117`
- `KERNEL32!GetLastError` at `0x18016e1ea`
- `KERNEL32!GetLastError` at `0x18016e200`
- `KERNEL32!GetLastError` at `0x18016e225`
- `KERNEL32!GetLastError` at `0x18016e2ef`
- `KERNEL32!GetLastError` at `0x18016e305`
- `KERNEL32!GetLastError` at `0x18016e32a`
- `KERNEL32!GetLastError` at `0x18016e3fc`
- `KERNEL32!GetLastError` at `0x18016e412`
- `KERNEL32!GetLastError` at `0x18016e437`
- `KERNEL32!GetLastError` at `0x18016e51b`
- `KERNEL32!GetLastError` at `0x18016e605`
- `KERNEL32!GetLastError` at `0x18016e6b5`
- `KERNEL32!GetLastError` at `0x18016e773`
- `KERNEL32!GetLastError` at `0x18016e824`
- `KERNEL32!GetLastError` at `0x18016eba0`
- `KERNEL32!GetLastError` at `0x18016ed4b`
- `KERNEL32!GetLastError` at `0x18016ed61`
- `KERNEL32!GetLastError` at `0x18016ed7f`
- `KERNEL32!GetLastError` at `0x18016efe2`
- `KERNEL32!GetLastError` at `0x18016f183`
- `KERNEL32!GetLastError` at `0x180167259`
- `KERNEL32!GetLastError` at `0x1801672e2`
- `KERNEL32!GetLastError` at `0x1801673a9`
- `KERNEL32!GetLastError` at `0x1801673bf`
- `KERNEL32!GetLastError` at `0x1801673df`
- `KERNEL32!GetLastError` at `0x1801674ac`
- `KERNEL32!GetLastError` at `0x1801675f8`
- `KERNEL32!GetLastError` at `0x18016760e`
- `KERNEL32!GetLastError` at `0x18016762e`
- `KERNEL32!GetLastError` at `0x180167709`
- `KERNEL32!GetLastError` at `0x1801677b0`
- `KERNEL32!GetLastError` at `0x18016787c`
- `KERNEL32!GetLastError` at `0x180167967`
- `KERNEL32!GetLastError` at `0x18016798c`
- `KERNEL32!GetLastError` at `0x180167a8d`
- `KERNEL32!GetLastError` at `0x180167b5c`
- `KERNEL32!GetLastError` at `0x180167d2d`
- `KERNEL32!GetLastError` at `0x1801680fb`
- `KERNEL32!GetLastError` at `0x1801681e3`
- `KERNEL32!GetLastError` at `0x180168270`
- `KERNEL32!GetLastError` at `0x180168369`
- `KERNEL32!GetLastError` at `0x18016878c`
- `KERNEL32!GetLastError` at `0x180168847`
- `KERNEL32!GetLastError` at `0x180168c08`
- `KERNEL32!GetLastError` at `0x180168ca3`
- `KERNEL32!GetLastError` at `0x180169039`
- `KERNEL32!GetLastError` at `0x1801690dd`
- `KERNEL32!GetLastError` at `0x1801693b6`
- `KERNEL32!GetLastError` at `0x180169453`
- `KERNEL32!GetLastError` at `0x180169537`
- `KERNEL32!GetLastError` at `0x1801696cf`
- `KERNEL32!GetLastError` at `0x1801696e5`
- `KERNEL32!GetLastError` at `0x180169705`
- `KERNEL32!GetLastError` at `0x180169964`
- `KERNEL32!GetLastError` at `0x180169a5a`
- `KERNEL32!GetLastError` at `0x180169acd`
- `KERNEL32!GetLastError` at `0x180169bde`
- `KERNEL32!GetLastError` at `0x180169e3c`
- `KERNEL32!GetLastError` at `0x180169f26`
- `KERNEL32!GetLastError` at `0x18016a11e`
- `KERNEL32!GetLastError` at `0x18016a937`
- `KERNEL32!GetLastError` at `0x18016aa22`
- `KERNEL32!GetLastError` at `0x18016adb7`
- `KERNEL32!GetLastError` at `0x18016aeb8`
- `KERNEL32!GetLastError` at `0x18016af97`
- `KERNEL32!GetLastError` at `0x18016b071`
- `KERNEL32!GetLastError` at `0x18016b273`
- `KERNEL32!GetLastError` at `0x18016b35b`
- `KERNEL32!GetLastError` at `0x18016b511`
- `KERNEL32!GetLastError` at `0x18016b522`
- `KERNEL32!GetLastError` at `0x18016b57f`
- `KERNEL32!GetLastError` at `0x18016b70f`
- `KERNEL32!GetLastError` at `0x18016b972`
- `KERNEL32!GetLastError` at `0x18016b988`
- `KERNEL32!GetLastError` at `0x18016b9b2`
- `KERNEL32!GetLastError` at `0x18016ba6a`
- `KERNEL32!GetLastError` at `0x18016c2a7`
- `KERNEL32!GetLastError` at `0x18016c95a`
- `KERNEL32!GetLastError` at `0x18016cdad`
- `KERNEL32!GetLastError` at `0x18016ce34`
- `KERNEL32!GetLastError` at `0x18016cee2`

## string_xrefs

- `0x180167546`: `ExternalRollback`
- `0x18016ec48`: `FolderMoveLog.TXT`
- `0x180169770`: `%hs: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x1801672f3`: `Error setting OS Switch Rollback checkpoint`
- `0x1801679ba`: `Failed to read the migration scope from %s. hr = 0x%08X`
- `0x180167894`: `%hs: Failed to save the rollback GUID`
- `0x18016740d`: `Failed to read the new OS entry GUID from %s. hr = 0x%X`
- `0x18016d7c5`: `Quarantine.NewPaths`
- `0x18016726a`: `Attempting to set the OS switch checkpoint`
- `0x18016e63b`: `%hs: Cannot unmount overlay for %s. Error: 0x%08X`
- `0x18016db60`: `SETUPMON: Failed to get the client's full path. Error 0x%08X`
- `0x18016765c`: `Failed to read rollback or safe OS entry GUIDs from %s. hr = 0x%X`
- `0x180167cc9`: `    Name: %s, Original path: %s, Current path: %s (%sallow relocation)`
- `0x18016b1fe`: `    Name: %s, Original path: %s, Current path: %s (%sallow relocation)`
- `0x18016837a`: `No source symbolic mappings found`
- `0x18016879d`: `Final list of Windows.old roots:`
- `0x1801681f4`: `Initial list of source symbolic mappings:`
- `0x18016906d`: `%hs: Cannot find stored path for exception ID %s`
- `0x180168c19`: `Final list of source symbolic mappings:`
- `0x1801692f3`: `Recovery\ReAgentOld.xml`
- `0x1801693c7`: `Final list of source move exceptions:`
- `0x18016968c`: `Paths.Exceptions`
- `0x18016dbeb`: `CRelocateOS: Cannot create security descriptor for Windows.old folders. Error: 0x%08X`
- `0x18016dd7f`: `CRelocateOS: Cannot find room to move stale %s out of the way. Error: 0x%08X`
- `0x180169f51`: `CRelocateOS: Failing to remove existing %s directory, will move out of the way`
- `0x18016e543`: `%hs: Cannot move path %s from the previos OS to Windows.old. Error: 0x%08X`
- `0x18016df1a`: `CRelocateOS: Cannot create %s. Error: 0x%08X`
- `0x18016d850`: `CRelocateOS: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x18016e057`: `CRelocateOS: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x18016e164`: `CRelocateOS: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x18016e269`: `CRelocateOS: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x18016e377`: `CRelocateOS: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x18016e485`: `CRelocateOS: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x18016b52b`: `CRelocateOS: ConvertSecurityDescriptorToStringSecurityDescriptor failed. Error: 0x%08X`
- `0x18016b5b9`: `CRelocateOS: Setting ACL on %s: %s`
- `0x18016e6e4`: `CRelocateOS: Can't find the new OS installation in %s`
- `0x18016e7a5`: `CRelocateOS: Cannot access security information for source root %s (error 0x%08X)`
- `0x18016b9d0`: `CRelocateOS: Failed to set security descriptor control on destination NT path %s. Error: 0x%08X`
- `0x18016ba86`: `CRelocateOS: Failed to set security on destination NT path %s. Error: 0x%08X`
- `0x18016e856`: `CRelocateOS: Cannot convert destination path to NT path for %s (error 0x%08X)`
- `0x18016b72b`: `CRelocateOS: Failed to open the destination NT path %s (error 0x%08X)`
- `0x18016cdd8`: `CRelocateOS: Collision detected for path %s, which is one of the OS pieces.`
- `0x18016ce7c`: `CRelocateOS: Will attempt to merge %s into %s`
- `0x18016c31f`: `CRelocateOS: Path %s\%s excluded, will not be moved in the final place.`
- `0x18016d1ec`: `CRelocateOS: Cannot move path %s out of the way of the new OS. Error: 0x%08X`
- `0x18016cf0d`: `CRelocateOS_VERBOSE: Collision detected for path %s, which is not an OS piece.`
- `0x18016d099`: `CRelocateOS: Collision detected for path %s, which is not an OS piece. Moving out of the way.`
- `0x18016d68d`: `CRelocateOS: Source path %s does not exist`
- `0x18016d44e`: `CRelocateOS: Failed to move path %s, we've unloaded all hives from it and will retry`
- `0x18016d525`: `CRelocateOS: Failed to move path %s, we'll wait for one second and retry`
- `0x18016d5ec`: `CRelocateOS: Cannot move path %s from Windows.NEW. Error: 0x%08X`
- `0x18016f02a`: `CRelocateOS: Failed to write converted entries from %s to %s`
- `0x18016ecc1`: `FolderMoveLog.TXT.BAK`
- `0x18016edcb`: `CRelocateOS: Cannot move journal file from %s to %s. Error: 0x%08X`
- `0x18016f1b9`: `%hs: Cannot mount overlay for %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=172 #try_helpers=2
__int64 __fastcall CRelocateOS::DoExecute(
        CRelocateOS *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        __int64 a28,
        __int64 a29,
        __int64 a30,
        __int64 a31,
        __int64 a32,
        __int64 a33,
        __int64 a34,
        __int64 a35,
        __int64 a36,
        __int64 a37,
        __int64 a38,
        unsigned __int64 *a39)
{
  const struct UnBCL::String *v40; // rbx
  const struct UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  struct UnBCL::String *v43; // r14
  struct UnBCL::String *v44; // rax
  __int64 v45; // rax
  struct IRollback *v46; // rsi
  DWORD LastError; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  DWORD v50; // edi
  __int64 v51; // rbx
  struct tagLOG_PARTIAL_MSG *v52; // rax
  UnBCL::String *v53; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v55; // rax
  signed int v56; // eax
  bool v57; // sf
  signed int v58; // eax
  signed int v59; // r14d
  DWORD v60; // edi
  __int64 v61; // rbx
  UnBCL::String *v62; // rax
  const char *v63; // rax
  struct tagLOG_PARTIAL_MSG *v64; // rax
  _BYTE *v65; // rcx
  UnBCL::String *v66; // rax
  const unsigned __int16 *v67; // rax
  DWORD v68; // edi
  __int64 v69; // rbx
  UnBCL::String *v70; // rax
  const char *v71; // rax
  struct tagLOG_PARTIAL_MSG *v72; // rax
  unsigned int v73; // ebx
  UnBCL::String *v74; // rax
  const WCHAR *v75; // rax
  struct UnBCL::String *v76; // rax
  UnBCL::String *v77; // rax
  const WCHAR *v78; // rax
  struct UnBCL::String *v79; // rax
  signed int v80; // eax
  bool v81; // sf
  signed int v82; // eax
  DWORD v83; // edi
  __int64 v84; // rbx
  UnBCL::String *v85; // rax
  const char *v86; // rax
  struct tagLOG_PARTIAL_MSG *v87; // rax
  UnBCL::String *v88; // rax
  const unsigned __int16 *v89; // rax
  DWORD v90; // edi
  __int64 v91; // rbx
  UnBCL::String *v92; // rax
  const char *v93; // rax
  DWORD v94; // edi
  __int64 v95; // rbx
  struct tagLOG_PARTIAL_MSG *v96; // rax
  DWORD v97; // edi
  __int64 v98; // rbx
  UnBCL::String *v99; // rax
  const WCHAR *v100; // rax
  struct UnBCL::String *v101; // rax
  DWORD v102; // edi
  __int64 v103; // rbx
  UnBCL::String *v104; // rax
  const char *v105; // rax
  struct tagLOG_PARTIAL_MSG *v106; // rax
  __int64 P; // rax
  UnBCL::String *v108; // rax
  const WCHAR *v109; // rax
  __int64 v110; // rax
  DWORD v111; // edi
  __int64 v112; // rbx
  struct tagLOG_PARTIAL_MSG *v113; // rax
  unsigned int i; // ebx
  int (__fastcall ***v115)(_QWORD); // rcx
  __int64 v116; // rcx
  DWORD v117; // esi
  __int64 v118; // r14
  __int64 v119; // rcx
  const wchar_t *v120; // rdi
  __int64 v121; // rcx
  __int64 v122; // rax
  UnBCL::String *v123; // rax
  __int64 v124; // rcx
  _QWORD *v125; // rax
  UnBCL::String *v126; // rax
  __int64 v127; // rcx
  _QWORD *v128; // rax
  __int64 v129; // rcx
  _QWORD *v130; // rax
  UnBCL::String *v131; // rax
  const wchar_t *v132; // rax
  struct tagLOG_PARTIAL_MSG *v133; // rax
  DWORD v134; // edi
  __int64 v135; // rbx
  struct tagLOG_PARTIAL_MSG *v136; // rax
  void *v137; // rax
  __int64 v138; // rax
  unsigned int v139; // edi
  struct UnBCL::String *v140; // rax
  struct UnBCL::String *v141; // rax
  UnBCL::String *v142; // rax
  const WCHAR *v143; // rbx
  UnBCL::String *v144; // rax
  const WCHAR *v145; // rax
  struct CGlobalPath *v146; // rax
  UnBCL::String *v147; // rax
  const WCHAR *v148; // rbx
  UnBCL::String *v149; // rax
  const WCHAR *v150; // rax
  struct CGlobalPath *v151; // rax
  UnBCL::String *v152; // rax
  struct UnBCL::String *v153; // rax
  UnBCL::String *v154; // rax
  struct UnBCL::String *v155; // rax
  char *v156; // r14
  void *v157; // rsi
  __int64 v158; // rbx
  __int64 v159; // rax
  __int64 v160; // rax
  DWORD v161; // edi
  __int64 v162; // rbx
  struct tagLOG_PARTIAL_MSG *v163; // rax
  int (__fastcall ***v164)(_QWORD); // rcx
  DWORD v165; // edi
  __int64 v166; // rbx
  struct tagLOG_PARTIAL_MSG *v167; // rax
  unsigned int j; // r14d
  int (__fastcall ***v169)(_QWORD); // rcx
  DWORD v170; // esi
  __int64 v171; // rdi
  __int64 v172; // rcx
  _QWORD *v173; // rax
  UnBCL::String *v174; // rax
  const char *v175; // rbx
  __int64 v176; // rcx
  _QWORD *v177; // rax
  UnBCL::String *v178; // rax
  const char *v179; // rax
  struct tagLOG_PARTIAL_MSG *v180; // rax
  DWORD v181; // edi
  __int64 v182; // rbx
  struct tagLOG_PARTIAL_MSG *v183; // rax
  void *v184; // rax
  __int64 v185; // rax
  __int64 v186; // rdx
  unsigned int k; // edi
  int (__fastcall ***v188)(_QWORD); // rcx
  __int64 v189; // rcx
  __int64 v190; // rcx
  _QWORD *v191; // rax
  __int64 v192; // rax
  __int64 v193; // rcx
  __int64 v194; // rcx
  const struct UnBCL::String *v195; // rax
  struct UnBCL::String *PathRoot; // rax
  __int64 v197; // rcx
  __int64 v198; // rax
  const struct UnBCL::String *v199; // rax
  struct UnBCL::String *v200; // rax
  int m; // esi
  int (__fastcall ***v202)(_QWORD); // rcx
  char *v203; // rcx
  _QWORD *v204; // rax
  const struct UnBCL::String *v205; // rbx
  const struct UnBCL::String *v206; // rax
  char *v207; // r14
  void *v208; // rsi
  __int64 v209; // rbx
  __int64 v210; // rax
  __int64 v211; // rax
  DWORD v212; // edi
  __int64 v213; // rbx
  struct tagLOG_PARTIAL_MSG *v214; // rax
  int n; // edi
  int (__fastcall ***v216)(_QWORD); // rcx
  char *v217; // rcx
  __int64 v218; // rbx
  DWORD v219; // esi
  __int64 v220; // r14
  UnBCL::String *v221; // rax
  UnBCL::String *v222; // rax
  const wchar_t *v223; // rax
  struct tagLOG_PARTIAL_MSG *v224; // rax
  int (__fastcall ***v225)(_QWORD); // rcx
  bool v226; // cc
  __int64 v227; // rax
  char *v228; // rcx
  __int64 v229; // r14
  int (__fastcall ***v230)(_QWORD); // rcx
  char *v231; // rcx
  _QWORD *v232; // rax
  struct UnBCL::String *v233; // rbx
  struct UnBCL::String *v234; // rax
  char *v235; // rcx
  int (__fastcall ***v236)(_QWORD); // rcx
  DWORD v237; // edi
  __int64 v238; // rbx
  struct tagLOG_PARTIAL_MSG *v239; // rax
  unsigned int ii; // r14d
  int (__fastcall ***v241)(_QWORD); // rcx
  DWORD v242; // esi
  __int64 v243; // rdi
  __int64 v244; // rcx
  _QWORD *v245; // rax
  UnBCL::String *v246; // rax
  const char *v247; // rbx
  __int64 v248; // rcx
  _QWORD *v249; // rax
  UnBCL::String *v250; // rax
  const char *v251; // rax
  struct tagLOG_PARTIAL_MSG *v252; // rax
  _QWORD *v253; // rax
  _QWORD *v254; // rbx
  __int64 v255; // rax
  struct IExecutionContext *v256; // rdi
  const struct UnBCL::String *v257; // rax
  struct UnBCL::String *v258; // rax
  __int64 v259; // rax
  __int64 v260; // rsi
  unsigned int jj; // r14d
  int (__fastcall ***v262)(_QWORD); // rcx
  __int64 v263; // rcx
  _QWORD *v264; // rax
  __int64 v265; // rax
  const struct UnBCL::String *v266; // r13
  __int64 v267; // rax
  __int64 v268; // rdi
  UnBCL::String *v269; // rax
  UnBCL::String *v270; // rbx
  __int64 v271; // rcx
  _QWORD *v272; // rax
  __int64 v273; // rax
  __int64 v274; // r13
  struct UnBCL::String *v275; // rax
  struct UnBCL::String *v276; // rax
  __int64 v277; // rax
  __int64 v278; // rdi
  void (__fastcall *v279)(__int64, __int64); // rbx
  __int64 v280; // rax
  DWORD v281; // edi
  __int64 v282; // rbx
  UnBCL::String *v283; // rax
  const char *v284; // rax
  struct tagLOG_PARTIAL_MSG *v285; // rax
  DWORD v286; // edi
  __int64 v287; // rbx
  __int64 v288; // rcx
  __int64 v289; // rax
  __int64 v290; // rcx
  __int64 v291; // rax
  __int64 v292; // rax
  UnBCL::String *v293; // rax
  const char *v294; // rax
  struct tagLOG_PARTIAL_MSG *v295; // rax
  const struct UnBCL::String *v296; // rbx
  const struct UnBCL::String *v297; // rax
  struct UnBCL::String *v298; // rax
  __int64 v299; // rax
  __int64 v300; // rdi
  void (__fastcall *v301)(__int64, __int64); // rbx
  __int64 v302; // rax
  const struct UnBCL::String *v303; // rbx
  const struct UnBCL::String *v304; // rax
  struct UnBCL::String *v305; // rax
  __int64 v306; // rax
  __int64 v307; // rdi
  void (__fastcall *v308)(__int64, __int64); // rbx
  __int64 v309; // rax
  const struct UnBCL::String *v310; // rbx
  const struct UnBCL::String *v311; // rax
  struct UnBCL::String *v312; // rax
  __int64 v313; // rax
  __int64 v314; // rdi
  void (__fastcall *v315)(__int64, __int64); // rbx
  __int64 v316; // rax
  __int64 v317; // rax
  int (__fastcall ***v318)(_QWORD); // rcx
  DWORD v319; // edi
  __int64 v320; // rbx
  struct tagLOG_PARTIAL_MSG *v321; // rax
  unsigned int kk; // r13d
  __int64 v323; // rax
  int (__fastcall ***v324)(_QWORD); // rcx
  DWORD v325; // edi
  __int64 v326; // rbx
  __int64 v327; // rax
  __int64 v328; // rcx
  UnBCL::String **v329; // rax
  const char *v330; // rax
  struct tagLOG_PARTIAL_MSG *v331; // rax
  __int64 v332; // rax
  __int64 v333; // rcx
  UnBCL::String **v334; // rax
  const WCHAR *v335; // rax
  DWORD v336; // edi
  __int64 v337; // rbx
  struct tagLOG_PARTIAL_MSG *v338; // rax
  struct UnBCL::String *v339; // rax
  CGlobalPath *v340; // rbx
  __int64 v341; // rax
  __int64 v342; // rcx
  struct UnBCL::String **v343; // rax
  CGlobalPath *v344; // rax
  const unsigned __int16 *v345; // rbx
  struct CGlobalPath *v346; // rdi
  UnBCL::String *v347; // rax
  const unsigned __int16 *v348; // rax
  CRelocateOS *v350; // rbx
  int mm; // r13d
  int (__fastcall ***v352)(_QWORD); // rcx
  __int64 v353; // rcx
  __int64 v354; // rdi
  DWORD v355; // r14d
  __int64 v356; // rsi
  UnBCL::String *v357; // rax
  const char *v358; // rbx
  int v359; // edi
  UnBCL::String *v360; // rax
  const char *v361; // rax
  struct tagLOG_PARTIAL_MSG *v362; // rax
  LARGE_INTEGER v363; // rbx
  UnBCL::String *v364; // rax
  const WCHAR *v365; // rax
  HRESULT v366; // esi
  DWORD v367; // edi
  __int64 v368; // rbx
  struct tagLOG_PARTIAL_MSG *v369; // rax
  struct tagLOG_PARTIAL_MSG *v370; // rax
  int v371; // r14d
  UnBCL::String *v372; // rax
  const unsigned __int16 *v373; // rax
  int IsLoaded; // ebx
  DWORD v375; // eax
  DWORD v376; // ebx
  __int64 v377; // rdi
  const wchar_t *v378; // r8
  struct tagLOG_PARTIAL_MSG *v379; // rax
  struct UnBCL::String *v380; // rax
  int v381; // ebx
  const struct UnBCL::String *v382; // rdi
  _QWORD *v383; // rax
  const struct UnBCL::String *v384; // rax
  struct UnBCL::String *v385; // rax
  UnBCL::String *v386; // rax
  const WCHAR *v387; // rax
  DWORD v388; // ebx
  __int64 v389; // rdi
  UnBCL::String *v390; // rax
  const char *v391; // rax
  struct tagLOG_PARTIAL_MSG *v392; // rax
  struct UnBCL::String *v393; // rbx
  struct UnBCL::String *v394; // rax
  int v395; // ebx
  struct UnBCL::String *v396; // rax
  DWORD v397; // edi
  __int64 v398; // rsi
  UnBCL::String *v399; // rax
  const char *v400; // rax
  struct tagLOG_PARTIAL_MSG *v401; // rax
  UnBCL::String *v402; // rax
  const WCHAR *v403; // rax
  unsigned int v404; // edi
  int nn; // eax
  UnBCL::String *v406; // rax
  const unsigned __int16 *v407; // rax
  struct UnBCL::String *v408; // rax
  UnBCL::String *v409; // rax
  const WCHAR *v410; // rax
  struct UnBCL::String *v411; // rsi
  struct UnBCL::String *v412; // rax
  DWORD v413; // ebx
  __int64 v414; // rdi
  UnBCL::String *v415; // rax
  const char *v416; // rax
  struct tagLOG_PARTIAL_MSG *v417; // rax
  struct UnBCL::String *v418; // rax
  int v419; // ebx
  UnBCL::String *v420; // rax
  const WCHAR *v421; // rax
  CGlobalPath *v422; // rdi
  _QWORD *v423; // rax
  struct UnBCL::String *v424; // rax
  CGlobalPath *v425; // rax
  CGlobalPath *v426; // rdi
  struct UnBCL::String *v427; // rax
  CGlobalPath *v428; // rax
  struct UnBCL::String *v429; // rax
  struct UnBCL::String *v430; // rax
  UnBCL::String *v431; // rax
  const unsigned __int16 *v432; // rsi
  struct CGlobalPath *v433; // rdi
  UnBCL::String *v434; // rax
  const unsigned __int16 *v435; // rax
  __int64 v436; // rdi
  CGlobalPath *v437; // rsi
  struct UnBCL::String *v438; // rax
  CGlobalPath *v439; // rax
  CGlobalPath *v440; // rsi
  struct UnBCL::String *v441; // rax
  CGlobalPath *v442; // rax
  struct UnBCL::String *v443; // rax
  struct UnBCL::String *v444; // rax
  UnBCL::String *v445; // rax
  const unsigned __int16 *v446; // r14
  struct CGlobalPath *v447; // rsi
  UnBCL::String *v448; // rax
  const unsigned __int16 *v449; // rax
  __int64 v450; // r8
  unsigned int v451; // r14d
  int v452; // edi
  __int64 v453; // rax
  const struct UnBCL::String *v454; // rsi
  struct UnBCL::String *v455; // rax
  const struct UnBCL::String *v456; // rdi
  const struct UnBCL::String *v457; // rax
  struct UnBCL::String *v458; // rax
  const unsigned __int16 *v459; // rax
  const struct UnBCL::String *v460; // rdi
  const struct UnBCL::String *v461; // rax
  struct UnBCL::String *v462; // rax
  DWORD v463; // r13d
  UnBCL::String *v464; // rax
  const char *v465; // rdi
  const char *v466; // rax
  struct tagLOG_PARTIAL_MSG *v467; // rax
  int v468; // eax
  DWORD v469; // edi
  const struct UnBCL::String *v470; // rdi
  const struct UnBCL::String *v471; // rax
  struct UnBCL::String *v472; // rax
  UnBCL::String *v473; // rax
  const WCHAR *v474; // rax
  __int64 v475; // rax
  void *v476; // rax
  __int64 v477; // rax
  const struct UnBCL::String *v478; // rdi
  const struct UnBCL::String *v479; // rax
  struct UnBCL::String *v480; // rax
  const struct UnBCL::String *v481; // rax
  const struct UnBCL::String *v482; // rax
  UnBCL::Object *Dir; // rax
  UnBCL::Object *v484; // rdi
  __int64 v485; // rdi
  __int64 v486; // rsi
  __int64 v487; // rax
  DWORD v488; // edi
  __int64 v489; // rsi
  struct tagLOG_PARTIAL_MSG *v490; // rax
  unsigned int v491; // edi
  int i1; // esi
  const wchar_t *v493; // rsi
  __int64 v494; // rax
  UnBCL::String *v495; // rax
  const char *v496; // r13
  _QWORD *v497; // rax
  UnBCL::String *v498; // rax
  const char *v499; // r14
  _QWORD *v500; // rax
  _QWORD *v501; // rax
  UnBCL::String *v502; // rax
  const wchar_t *v503; // rax
  struct tagLOG_PARTIAL_MSG *v504; // rax
  DWORD v505; // edi
  __int64 v506; // rsi
  struct tagLOG_PARTIAL_MSG *v507; // rax
  struct UnBCL::String *v508; // rax
  struct UnBCL::String *v509; // rax
  struct UnBCL::String *v510; // rax
  DWORD v511; // esi
  __int64 v512; // r14
  UnBCL::String *v513; // rax
  const char *v514; // rdi
  UnBCL::String *v515; // rax
  const char *v516; // rax
  struct tagLOG_PARTIAL_MSG *v517; // rax
  UnBCL::String *v518; // rax
  const WCHAR *v519; // rax
  UnBCL::String *v520; // rax
  const WCHAR *v521; // rax
  signed int NamedSecurityInfoW; // eax
  unsigned int v523; // edi
  DWORD v524; // ebx
  __int64 v525; // rdi
  DWORD v526; // eax
  struct tagLOG_PARTIAL_MSG *v527; // rax
  DWORD v528; // edi
  __int64 v529; // rsi
  const char *v530; // rbx
  UnBCL::String *v531; // rax
  const char *v532; // rax
  struct tagLOG_PARTIAL_MSG *v533; // rax
  UnBCL::String *v534; // rax
  const unsigned __int16 *v535; // rax
  NTSTATUS v536; // eax
  DWORD v537; // edi
  __int64 v538; // rsi
  struct tagLOG_PARTIAL_MSG *v539; // rax
  SECURITY_DESCRIPTOR_CONTROL v540; // si
  SECURITY_DESCRIPTOR_CONTROL v541; // r14
  SECURITY_INFORMATION v542; // edi
  signed int v543; // eax
  bool v544; // sf
  signed int v545; // eax
  DWORD v546; // esi
  struct tagLOG_PARTIAL_MSG *v547; // rax
  NTSTATUS v548; // eax
  DWORD v549; // edi
  __int64 v550; // rsi
  struct tagLOG_PARTIAL_MSG *v551; // rax
  WCHAR *v552; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v554; // rax
  _QWORD *v555; // rdi
  __int64 v556; // rax
  void *v557; // rax
  __int64 v558; // rax
  __int64 v559; // rax
  CRelocateOS *v560; // rsi
  const struct UnBCL::String *v561; // rdi
  const struct UnBCL::String *v562; // rax
  struct UnBCL::String *v563; // rax
  _QWORD *v564; // rax
  _QWORD *v565; // rdi
  __int64 v566; // rax
  __int64 v567; // rax
  __int64 Files; // rax
  int i2; // esi
  __int64 v570; // rax
  __int64 v571; // rax
  __int64 v572; // r13
  UnBCL::String *v573; // rdi
  __int64 v574; // rax
  const struct UnBCL::String **v575; // rax
  __int64 v576; // rax
  __int64 Directories; // rax
  int i3; // esi
  __int64 v579; // rax
  __int64 v580; // rax
  __int64 v581; // r13
  UnBCL::String *v582; // rdi
  __int64 v583; // rax
  const struct UnBCL::String **v584; // rax
  _QWORD *v585; // rax
  _QWORD *v586; // rdi
  __int64 v587; // rax
  __int64 v588; // rax
  __int64 v589; // rsi
  _QWORD *v590; // rax
  _QWORD *v591; // rdi
  __int64 v592; // rax
  unsigned int v593; // r13d
  int i4; // edi
  _QWORD *v595; // rax
  __int64 v596; // rax
  UnBCL::String *v597; // rdi
  const struct UnBCL::String *v598; // rax
  int v599; // r13d
  __int64 v600; // rax
  int v601; // esi
  int i6; // eax
  wchar_t **v603; // rdi
  const unsigned __int16 *v604; // r13
  __int64 v605; // rax
  UnBCL::String **v606; // rax
  const unsigned __int16 *v607; // rax
  BOOL v608; // eax
  DWORD v609; // esi
  __int64 v610; // r13
  __int64 v611; // rax
  UnBCL::String **v612; // rax
  const char *v613; // rdi
  UnBCL::String *v614; // rax
  const char *v615; // rax
  struct tagLOG_PARTIAL_MSG *v616; // rax
  __int64 v617; // rax
  const struct UnBCL::String *v618; // rdi
  const struct UnBCL::String *v619; // rax
  struct UnBCL::String *v620; // rax
  __int64 v621; // rax
  const struct UnBCL::String *v622; // rdi
  const struct UnBCL::String *v623; // rax
  struct UnBCL::String *v624; // rax
  unsigned int i7; // esi
  __int64 v626; // rax
  __int64 v627; // rax
  __int64 v628; // rax
  CStoredPath **v629; // rax
  struct UnBCL::String *v630; // rdi
  __int64 v631; // rax
  COSPieceInfo **v632; // rax
  struct CGlobalPath *CurrentPath; // rax
  struct UnBCL::String *v634; // rax
  unsigned int i8; // esi
  __int64 v636; // rax
  __int64 v637; // rax
  __int64 v638; // rax
  CStoredPath **v639; // rax
  const struct UnBCL::String *v640; // rdi
  __int64 v641; // rax
  CStoredPath **v642; // rax
  const struct UnBCL::String *Path; // rax
  struct UnBCL::Exception *v644; // rdi
  __int64 v645; // rax
  COSPieceInfo **v646; // rax
  struct CGlobalPath *v647; // rax
  const struct UnBCL::String *v648; // rax
  struct UnBCL::String *v649; // rdi
  struct UnBCL::String *v650; // rax
  UnBCL::String *v651; // rax
  const WCHAR *v652; // rax
  int v653; // r13d
  UnBCL::String *v654; // rax
  const WCHAR *v655; // rax
  unsigned int i9; // edi
  __int64 v657; // rax
  __int64 v658; // rax
  struct UnBCL::String *v659; // rsi
  __int64 v660; // rax
  COSPieceInfo **v661; // rax
  struct CGlobalPath *v662; // rax
  struct UnBCL::String *v663; // rax
  DWORD v664; // edi
  __int64 v665; // rsi
  UnBCL::String *v666; // rax
  const char *v667; // rax
  struct tagLOG_PARTIAL_MSG *v668; // rax
  int i10; // edi
  __int64 v670; // rax
  __int64 v671; // rax
  const struct UnBCL::String *v672; // rsi
  __int64 v673; // rax
  const struct UnBCL::String **v674; // rax
  DWORD v675; // edi
  __int64 v676; // rsi
  UnBCL::String *v677; // rax
  const char *v678; // rax
  struct tagLOG_PARTIAL_MSG *v679; // rax
  __int64 v680; // rax
  const struct UnBCL::String *v681; // rdi
  const struct UnBCL::String *v682; // rax
  struct UnBCL::String *v683; // rax
  int v684; // eax
  signed int v685; // edi
  DWORD v686; // ebx
  __int64 v687; // rsi
  UnBCL::String *v688; // rax
  const char *v689; // rax
  struct tagLOG_PARTIAL_MSG *v690; // rax
  DWORD v691; // esi
  __int64 v692; // r13
  UnBCL::String *v693; // rax
  const char *v694; // rdi
  UnBCL::String *v695; // rax
  const char *v696; // rax
  struct tagLOG_PARTIAL_MSG *v697; // rax
  int v698; // r13d
  int v699; // esi
  int v700; // edi
  int v701; // eax
  DWORD v702; // eax
  int v703; // edi
  struct UnBCL::String *v704; // rax
  DWORD v705; // edi
  __int64 v706; // rsi
  UnBCL::String *v707; // rax
  const char *v708; // rax
  struct tagLOG_PARTIAL_MSG *v709; // rax
  void (__fastcall *v710)(_QWORD, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rdi
  UnBCL::String *v711; // rax
  const unsigned __int16 *v712; // rax
  DWORD v713; // edi
  __int64 v714; // rsi
  UnBCL::String *v715; // rax
  const char *v716; // rax
  struct tagLOG_PARTIAL_MSG *v717; // rax
  struct UnBCL::String *v718; // rax
  DWORD v719; // ebx
  __int64 v720; // rsi
  UnBCL::String *v721; // rax
  const char *v722; // rax
  struct tagLOG_PARTIAL_MSG *v723; // rax
  DWORD v724; // edi
  __int64 v725; // rsi
  UnBCL::String *v726; // rax
  const char *v727; // rax
  struct tagLOG_PARTIAL_MSG *v728; // rax
  struct UnBCL::String *v729; // rax
  CGlobalPath *v730; // rdi
  struct UnBCL::String *v731; // rax
  CGlobalPath *v732; // rax
  const unsigned __int16 *v733; // rsi
  struct CGlobalPath *v734; // rdi
  UnBCL::String *v735; // rax
  const unsigned __int16 *v736; // rax
  __int64 v737; // rax
  __int64 v738; // rdi
  void (__fastcall *v739)(__int64, struct UnBCL::String *); // rsi
  UnBCL::String *v740; // rax
  struct UnBCL::String *v741; // rax
  DWORD v742; // edi
  __int64 v743; // rsi
  struct tagLOG_PARTIAL_MSG *v744; // rax
  signed int v745; // eax
  bool v746; // sf
  signed int v747; // eax
  unsigned int v748; // r14d
  DWORD v749; // ebx
  __int64 v750; // rdi
  struct tagLOG_PARTIAL_MSG *v751; // rax
  DWORD v752; // edi
  __int64 v753; // rsi
  struct tagLOG_PARTIAL_MSG *v754; // rax
  DWORD v755; // edi
  __int64 v756; // rsi
  UnBCL::String *v757; // rax
  const char *v758; // rax
  struct tagLOG_PARTIAL_MSG *v759; // rax
  signed int v760; // eax
  bool v761; // sf
  signed int v762; // eax
  unsigned int v763; // r14d
  DWORD v764; // ebx
  __int64 v765; // rdi
  UnBCL::String *v766; // rax
  const char *v767; // rax
  struct tagLOG_PARTIAL_MSG *v768; // rax
  DWORD v769; // edi
  __int64 v770; // rsi
  UnBCL::String *v771; // rax
  const char *v772; // rax
  struct tagLOG_PARTIAL_MSG *v773; // rax
  signed int v774; // eax
  bool v775; // sf
  signed int v776; // eax
  unsigned int v777; // r14d
  DWORD v778; // ebx
  __int64 v779; // rdi
  UnBCL::String *v780; // rax
  const char *v781; // rax
  struct tagLOG_PARTIAL_MSG *v782; // rax
  DWORD v783; // ebx
  __int64 v784; // r14
  const char *v785; // rax
  struct tagLOG_PARTIAL_MSG *v786; // rax
  DWORD v787; // edi
  __int64 v788; // rsi
  UnBCL::String *v789; // rax
  const char *v790; // rax
  struct tagLOG_PARTIAL_MSG *v791; // rax
  DWORD v792; // ebx
  __int64 v793; // rdi
  UnBCL::String *v794; // rax
  const char *v795; // rax
  struct tagLOG_PARTIAL_MSG *v796; // rax
  DWORD v797; // ebx
  __int64 v798; // rsi
  UnBCL::String *v799; // rax
  const char *v800; // rax
  struct tagLOG_PARTIAL_MSG *v801; // rax
  DWORD v802; // edi
  __int64 v803; // rsi
  UnBCL::String *v804; // rax
  const char *v805; // rax
  struct tagLOG_PARTIAL_MSG *v806; // rax
  const struct UnBCL::String *v807; // rax
  struct UnBCL::String *v808; // rax
  const struct UnBCL::String *v809; // rdi
  const struct UnBCL::String *v810; // rax
  struct UnBCL::String *v811; // rax
  __int64 v812; // rdi
  __int64 v813; // rax
  CRelocateOS *v814; // rdi
  __int64 v815; // rax
  const struct UnBCL::String *v816; // rbx
  const struct UnBCL::String *v817; // rax
  struct UnBCL::String *v818; // rax
  __int64 v819; // rsi
  __int64 v820; // rdi
  __int64 v821; // rbx
  __int64 v822; // rax
  DWORD v823; // ebx
  __int64 v824; // rdi
  struct tagLOG_PARTIAL_MSG *v825; // rax
  __int64 v826; // rax
  const struct UnBCL::String *v827; // rdi
  const struct UnBCL::String *v828; // rax
  struct UnBCL::String *v829; // rax
  const struct UnBCL::String *v830; // rax
  const struct UnBCL::String *v831; // rbx
  const struct UnBCL::String *v832; // rax
  struct UnBCL::String *v833; // rax
  struct UnBCL::String *v834; // rbx
  struct UnBCL::String *v835; // rax
  signed int v836; // eax
  bool v837; // sf
  signed int v838; // eax
  DWORD v839; // esi
  __int64 v840; // r14
  UnBCL::String *v841; // rax
  const char *v842; // rdi
  UnBCL::String *v843; // rax
  const char *v844; // rax
  struct tagLOG_PARTIAL_MSG *v845; // rax
  __int64 Unicode; // rax
  UnBCL::StreamReader *v847; // rbx
  struct UnBCL::Encoding *v848; // rdi
  const struct UnBCL::String *v849; // rax
  _QWORD *v850; // rbx
  __int64 v851; // rax
  UnBCL::StreamWriter *v852; // rbx
  struct UnBCL::Encoding *v853; // rdi
  struct Stream *v854; // rax
  __int64 v855; // rdi
  __int64 v856; // rbx
  __int64 v857; // rax
  DWORD v858; // esi
  __int64 v859; // r14
  UnBCL::String *v860; // rax
  const char *v861; // rdi
  UnBCL::String *v862; // rax
  const char *v863; // rax
  struct tagLOG_PARTIAL_MSG *v864; // rax
  const struct UnBCL::String *v865; // rbx
  const struct UnBCL::String *v866; // rax
  struct UnBCL::String *v867; // rax
  struct UnBCL::String *v868; // rax
  int v869; // ebx
  DWORD v870; // edi
  __int64 v871; // rsi
  UnBCL::String *v872; // rax
  const char *v873; // rax
  struct tagLOG_PARTIAL_MSG *v874; // rax
  UnBCL::String *v875; // rax
  const char *v876; // rax
  struct UnBCL::Exception *v877; // rbx
  DWORD v878; // edi
  __int64 v879; // rsi
  UnBCL::String *v880; // rax
  const char *v881; // rax
  struct tagLOG_PARTIAL_MSG *v882; // rax
  __int64 v883; // rax
  DWORD v884; // ebx
  __int64 v885; // rdi
  UnBCL::String *v886; // rax
  const char *v887; // rax
  struct tagLOG_PARTIAL_MSG *v888; // rax
  UnBCL::Exception *ExceptionPtr; // rax
  DWORD v890; // edi
  __int64 v891; // rsi
  const char *MessageW; // rbx
  unsigned int Severity; // eax
  struct tagLOG_PARTIAL_MSG *v894; // rax
  int ppsidGroup; // [rsp+20h] [rbp-A68h]
  int ppsidGroupa; // [rsp+20h] [rbp-A68h]
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // [rsp+38h] [rbp-A50h]
  PSECURITY_DESCRIPTOR *ppSecurityDescriptora; // [rsp+38h] [rbp-A50h]
  ULONG CreateOptions; // [rsp+40h] [rbp-A48h]
  ULONG CreateOptionsa; // [rsp+40h] [rbp-A48h]
  int v901; // [rsp+68h] [rbp-A20h]
  const char *v902; // [rsp+70h] [rbp-A18h]
  void (__fastcall *v903)(char *, __int64); // [rsp+70h] [rbp-A18h]
  void (__fastcall *v904)(char *, __int64); // [rsp+70h] [rbp-A18h]
  const char *v905; // [rsp+70h] [rbp-A18h]
  void (__fastcall *v906)(__int64, UnBCL::String *); // [rsp+70h] [rbp-A18h]
  __int64 v907; // [rsp+70h] [rbp-A18h]
  __int64 v908; // [rsp+70h] [rbp-A18h]
  __int64 v909; // [rsp+70h] [rbp-A18h]
  __int64 v910; // [rsp+70h] [rbp-A18h]
  void (__fastcall *v911)(__int64, UnBCL::String *); // [rsp+70h] [rbp-A18h]
  void (__fastcall *v912)(__int64, UnBCL::String *); // [rsp+70h] [rbp-A18h]
  __int64 v913; // [rsp+70h] [rbp-A18h]
  DWORD FileAttributesW; // [rsp+70h] [rbp-A18h]
  CRelocateOS *v915; // [rsp+78h] [rbp-A10h]
  int v916[2]; // [rsp+80h] [rbp-A08h]
  unsigned int i5; // [rsp+88h] [rbp-A00h]
  int v918; // [rsp+8Ch] [rbp-9FCh]
  int i11; // [rsp+8Ch] [rbp-9FCh]
  UnBCL::String *v920; // [rsp+98h] [rbp-9F0h]
  struct IExecutionContext *v921; // [rsp+A0h] [rbp-9E8h]
  void (__fastcall *v922)(__int64, UnBCL::String *); // [rsp+A8h] [rbp-9E0h]
  int v923; // [rsp+A8h] [rbp-9E0h]
  DWORD v924; // [rsp+B0h] [rbp-9D8h]
  int v925; // [rsp+B0h] [rbp-9D8h]
  unsigned int v926; // [rsp+B8h] [rbp-9D0h]
  const char *v927; // [rsp+C0h] [rbp-9C8h]
  BOOL v928; // [rsp+C0h] [rbp-9C8h]
  __int64 v929; // [rsp+C8h] [rbp-9C0h]
  struct _GUID v930; // [rsp+D0h] [rbp-9B8h] BYREF
  __int64 v931; // [rsp+F0h] [rbp-998h] BYREF
  __int64 v932; // [rsp+F8h] [rbp-990h]
  int v933[2]; // [rsp+110h] [rbp-978h] BYREF
  char v934[8]; // [rsp+118h] [rbp-970h]
  int v935[2]; // [rsp+120h] [rbp-968h] BYREF
  char v936[8]; // [rsp+128h] [rbp-960h]
  int v937[2]; // [rsp+130h] [rbp-958h]
  _QWORD *v938; // [rsp+140h] [rbp-948h] BYREF
  _QWORD *v939; // [rsp+148h] [rbp-940h] BYREF
  _QWORD *v940; // [rsp+150h] [rbp-938h] BYREF
  _QWORD *v941; // [rsp+158h] [rbp-930h] BYREF
  _QWORD *v942; // [rsp+160h] [rbp-928h] BYREF
  _QWORD *v943; // [rsp+168h] [rbp-920h] BYREF
  int v944[2]; // [rsp+170h] [rbp-918h]
  _QWORD *v945; // [rsp+178h] [rbp-910h] BYREF
  _QWORD *pExceptionObject; // [rsp+180h] [rbp-908h] BYREF
  _QWORD *v947; // [rsp+188h] [rbp-900h] BYREF
  _QWORD *v948; // [rsp+190h] [rbp-8F8h] BYREF
  _QWORD *v949; // [rsp+198h] [rbp-8F0h] BYREF
  _QWORD *v950; // [rsp+1A0h] [rbp-8E8h] BYREF
  _QWORD *v951; // [rsp+1A8h] [rbp-8E0h] BYREF
  _QWORD *v952; // [rsp+1B0h] [rbp-8D8h] BYREF
  _BYTE v953[16]; // [rsp+1E0h] [rbp-8A8h] BYREF
  _BYTE v954[16]; // [rsp+1F0h] [rbp-898h] BYREF
  _BYTE v955[16]; // [rsp+200h] [rbp-888h] BYREF
  _BYTE v956[16]; // [rsp+210h] [rbp-878h] BYREF
  _BYTE v957[16]; // [rsp+220h] [rbp-868h] BYREF
  _BYTE v958[16]; // [rsp+240h] [rbp-848h] BYREF
  _BYTE v959[16]; // [rsp+250h] [rbp-838h] BYREF
  _BYTE v960[16]; // [rsp+260h] [rbp-828h] BYREF
  _BYTE v961[16]; // [rsp+270h] [rbp-818h] BYREF
  _BYTE v962[16]; // [rsp+280h] [rbp-808h] BYREF
  _BYTE v963[16]; // [rsp+290h] [rbp-7F8h] BYREF
  struct UnBCL::Exception *v964; // [rsp+2A8h] [rbp-7E0h] BYREF
  _QWORD v965[3]; // [rsp+2B0h] [rbp-7D8h] BYREF
  struct UnBCL::Exception *v966[3]; // [rsp+2C8h] [rbp-7C0h] BYREF
  _BYTE v967[16]; // [rsp+2E0h] [rbp-7A8h] BYREF
  _BYTE v968[24]; // [rsp+2F0h] [rbp-798h] BYREF
  _BYTE v969[24]; // [rsp+308h] [rbp-780h] BYREF
  _BYTE v970[24]; // [rsp+338h] [rbp-750h] BYREF
  _BYTE v971[24]; // [rsp+350h] [rbp-738h] BYREF
  _BYTE v972[24]; // [rsp+368h] [rbp-720h] BYREF
  _BYTE v973[24]; // [rsp+380h] [rbp-708h] BYREF
  _BYTE v974[24]; // [rsp+398h] [rbp-6F0h] BYREF
  _BYTE v975[24]; // [rsp+3B0h] [rbp-6D8h] BYREF
  _BYTE v976[24]; // [rsp+3C8h] [rbp-6C0h] BYREF
  _BYTE v977[24]; // [rsp+3E0h] [rbp-6A8h] BYREF
  _BYTE v978[24]; // [rsp+3F8h] [rbp-690h] BYREF
  _BYTE v979[24]; // [rsp+410h] [rbp-678h] BYREF
  _BYTE v980[24]; // [rsp+428h] [rbp-660h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+440h] [rbp-648h] BYREF
  PCWSTR SourceString; // [rsp+448h] [rbp-640h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+450h] [rbp-638h] BYREF
  void *FileHandle; // [rsp+458h] [rbp-630h] BYREF
  void *v985; // [rsp+460h] [rbp-628h] BYREF
  PSID pOwner; // [rsp+468h] [rbp-620h] BYREF
  PSID pGroup; // [rsp+470h] [rbp-618h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+478h] [rbp-610h] BYREF
  PACL pSacl; // [rsp+490h] [rbp-5F8h] BYREF
  PACL pDacl; // [rsp+498h] [rbp-5F0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+4A0h] [rbp-5E8h] BYREF
  const __int64 *v992; // [rsp+4D0h] [rbp-5B8h] BYREF
  __int64 v993; // [rsp+4D8h] [rbp-5B0h]
  const __int64 *v994; // [rsp+4E0h] [rbp-5A8h] BYREF
  int v995[2]; // [rsp+4E8h] [rbp-5A0h]
  WORD pControl; // [rsp+4F0h] [rbp-598h] BYREF
  _BYTE v997[16]; // [rsp+4F8h] [rbp-590h] BYREF
  const __int64 *v998; // [rsp+508h] [rbp-580h] BYREF
  _QWORD *v999; // [rsp+510h] [rbp-578h]
  const __int64 *v1000; // [rsp+518h] [rbp-570h] BYREF
  _QWORD *v1001; // [rsp+520h] [rbp-568h]
  _BYTE v1002[16]; // [rsp+528h] [rbp-560h] BYREF
  _BYTE v1003[16]; // [rsp+538h] [rbp-550h] BYREF
  int v1004; // [rsp+548h] [rbp-540h] BYREF
  _BYTE v1005[16]; // [rsp+550h] [rbp-538h] BYREF
  _BYTE v1006[16]; // [rsp+560h] [rbp-528h] BYREF
  WINBOOL bSaclPresent; // [rsp+570h] [rbp-518h] BYREF
  WINBOOL bDaclPresent; // [rsp+574h] [rbp-514h] BYREF
  void **v1009; // [rsp+578h] [rbp-510h] BYREF
  __int64 v1010; // [rsp+580h] [rbp-508h]
  _BYTE v1011[16]; // [rsp+588h] [rbp-500h] BYREF
  _BYTE v1012[16]; // [rsp+598h] [rbp-4F0h] BYREF
  _BYTE v1013[16]; // [rsp+5A8h] [rbp-4E0h] BYREF
  void **v1014; // [rsp+5B8h] [rbp-4D0h] BYREF
  __int64 v1015; // [rsp+5C0h] [rbp-4C8h]
  WINBOOL bGroupDefaulted; // [rsp+5C8h] [rbp-4C0h] BYREF
  DWORD dwRevision; // [rsp+5CCh] [rbp-4BCh] BYREF
  WINBOOL bSaclDefaulted; // [rsp+5D0h] [rbp-4B8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+5D4h] [rbp-4B4h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+5D8h] [rbp-4B0h] BYREF
  void **v1021; // [rsp+5E0h] [rbp-4A8h] BYREF
  struct CGlobalPath *v1022; // [rsp+5E8h] [rbp-4A0h]
  _BYTE v1023[16]; // [rsp+5F0h] [rbp-498h] BYREF
  _BYTE v1024[16]; // [rsp+600h] [rbp-488h] BYREF
  _BYTE v1025[16]; // [rsp+610h] [rbp-478h] BYREF
  _BYTE v1026[16]; // [rsp+620h] [rbp-468h] BYREF
  _QWORD v1027[2]; // [rsp+630h] [rbp-458h] BYREF
  _BYTE v1028[16]; // [rsp+640h] [rbp-448h] BYREF
  _BYTE v1029[16]; // [rsp+650h] [rbp-438h] BYREF
  _BYTE v1030[16]; // [rsp+660h] [rbp-428h] BYREF
  _QWORD v1031[7]; // [rsp+670h] [rbp-418h] BYREF
  _BYTE v1032[16]; // [rsp+6A8h] [rbp-3E0h] BYREF
  _BYTE v1033[16]; // [rsp+6B8h] [rbp-3D0h] BYREF
  const char *v1034; // [rsp+6C8h] [rbp-3C0h] BYREF
  UnBCL::Object *v1035; // [rsp+6D0h] [rbp-3B8h]
  void **v1036; // [rsp+6D8h] [rbp-3B0h] BYREF
  struct CGlobalPath *v1037; // [rsp+6E0h] [rbp-3A8h]
  _BYTE v1038[16]; // [rsp+6E8h] [rbp-3A0h] BYREF
  _QWORD v1039[2]; // [rsp+6F8h] [rbp-390h] BYREF
  _BYTE v1040[16]; // [rsp+708h] [rbp-380h] BYREF
  _BYTE v1041[16]; // [rsp+718h] [rbp-370h] BYREF
  _BYTE v1042[16]; // [rsp+728h] [rbp-360h] BYREF
  void **v1043; // [rsp+738h] [rbp-350h] BYREF
  struct CGlobalPath *v1044; // [rsp+740h] [rbp-348h]
  _BYTE v1045[16]; // [rsp+748h] [rbp-340h] BYREF
  _BYTE v1046[16]; // [rsp+758h] [rbp-330h] BYREF
  _BYTE v1047[16]; // [rsp+768h] [rbp-320h] BYREF
  _BYTE v1048[16]; // [rsp+778h] [rbp-310h] BYREF
  _BYTE v1049[16]; // [rsp+788h] [rbp-300h] BYREF
  _BYTE v1050[16]; // [rsp+798h] [rbp-2F0h] BYREF
  _BYTE v1051[16]; // [rsp+7A8h] [rbp-2E0h] BYREF
  _BYTE v1052[16]; // [rsp+7B8h] [rbp-2D0h] BYREF
  _BYTE v1053[16]; // [rsp+7C8h] [rbp-2C0h] BYREF
  _BYTE v1054[16]; // [rsp+7D8h] [rbp-2B0h] BYREF
  _BYTE v1055[16]; // [rsp+7E8h] [rbp-2A0h] BYREF
  _BYTE v1056[16]; // [rsp+7F8h] [rbp-290h] BYREF
  _BYTE v1057[16]; // [rsp+808h] [rbp-280h] BYREF
  _BYTE v1058[16]; // [rsp+818h] [rbp-270h] BYREF
  _BYTE v1059[16]; // [rsp+828h] [rbp-260h] BYREF
  _BYTE v1060[16]; // [rsp+838h] [rbp-250h] BYREF
  _BYTE v1061[16]; // [rsp+848h] [rbp-240h] BYREF
  _BYTE v1062[16]; // [rsp+858h] [rbp-230h] BYREF
  char v1063[16]; // [rsp+888h] [rbp-200h] BYREF
  _BYTE v1064[16]; // [rsp+898h] [rbp-1F0h] BYREF
  char v1065[16]; // [rsp+8A8h] [rbp-1E0h] BYREF
  _BYTE v1066[16]; // [rsp+8B8h] [rbp-1D0h] BYREF
  _BYTE v1067[16]; // [rsp+8C8h] [rbp-1C0h] BYREF
  _BYTE v1068[16]; // [rsp+8D8h] [rbp-1B0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+8E8h] [rbp-1A0h] BYREF
  _BYTE v1070[16]; // [rsp+908h] [rbp-180h] BYREF
  _BYTE v1071[16]; // [rsp+918h] [rbp-170h] BYREF
  _BYTE v1072[16]; // [rsp+928h] [rbp-160h] BYREF
  _BYTE v1073[16]; // [rsp+938h] [rbp-150h] BYREF
  _BYTE v1074[16]; // [rsp+948h] [rbp-140h] BYREF
  _BYTE v1075[16]; // [rsp+958h] [rbp-130h] BYREF
  _BYTE v1076[16]; // [rsp+968h] [rbp-120h] BYREF
  _BYTE v1077[16]; // [rsp+978h] [rbp-110h] BYREF
  _BYTE v1078[16]; // [rsp+988h] [rbp-100h] BYREF
  struct _GUID v1079; // [rsp+9B0h] [rbp-D8h] BYREF
  struct _GUID v1080; // [rsp+9C0h] [rbp-C8h] BYREF
  _BYTE v1081[16]; // [rsp+9D0h] [rbp-B8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+9E0h] [rbp-A8h] BYREF
  unsigned int v1083; // [rsp+9F0h] [rbp-98h] BYREF
  _BYTE v1084[16]; // [rsp+9F8h] [rbp-90h] BYREF
  UnBCL::Exception *v1085[3]; // [rsp+A08h] [rbp-80h] BYREF
  _BYTE v1086[48]; // [rsp+A20h] [rbp-68h] BYREF

  v965[2] = -2;
  v921 = a2;
  v915 = this;
  *(_QWORD *)v937 = this;
  *(_QWORD *)v944 = a2;
  v40 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v968, L"SetupPlatform.ini", a3, a4);
  v41 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
  v42 = UnBCL::Path::Combine(v41, v40);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1002, v42);
  UnBCL::String::~String((UnBCL::String *)v968);
  v43 = 0;
  v920 = 0;
  v44 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v969, L"FreezeProfilesFolder");
  v926 = SPGetStoredBOOL(a2, v44, 0);
  UnBCL::String::~String((UnBCL::String *)v969);
  v45 = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 72LL))(a2);
  v46 = (struct IRollback *)v45;
  if ( !v45 )
    goto LABEL_37;
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 40LL))(v45)
    && (*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v46 + 56LL))(v46) )
  {
    v43 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v46 + 56LL))(v46);
    v920 = v43;
  }
  LastError = GetLastError();
  v48 = CurrentIP();
  v49 = ConstructPartialMsgW(0x4000000u, "Attempting to set the OS switch checkpoint");
  WdsSetupLogMessageW(
    v49,
    819200,
    L"D",
    0,
    2138,
    L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
    L"CRelocateOS::DoExecute",
    v48,
    LastError,
    0,
    0);
  if ( (unsigned int)SPSetRollbackCheckpoint(v46, L"SetupPlatformOSSwitchCheckpoint", v43, 0) )
  {
    v53 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
    CString = UnBCL::String::get_CString(v53);
    v55 = SPReadConfigValue(L"BootEntries", L"NewOS", CString);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1013, v55);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v1013) )
    {
      v56 = GetLastError();
      v57 = v56 < 0;
      if ( v56 > 0 )
        v57 = 1;
      if ( v57 )
      {
        v58 = GetLastError();
        v59 = v58;
        if ( v58 > 0 )
          v59 = (unsigned __int16)v58 | 0x80070000;
      }
      else
      {
        v59 = -2147467259;
      }
      v60 = GetLastError();
      v61 = CurrentIP();
      v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
      v63 = (const char *)UnBCL::String::get_CString(v62);
      v64 = ConstructPartialMsgW(0x2000000u, "Failed to read the new OS entry GUID from %s. hr = 0x%X", v63, v59);
      WdsSetupLogMessageW(
        v64,
        819200,
        L"D",
        0,
        2156,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v61,
        v60,
        0,
        0);
      goto LABEL_15;
    }
    v1079 = 0;
    v66 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1013);
    v67 = UnBCL::String::get_CString(v66);
    v59 = SPGuidFromString(v67, &v1079);
    if ( v59 < 0 )
    {
      v68 = GetLastError();
      v69 = CurrentIP();
      v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1013);
      v71 = (const char *)UnBCL::String::get_CString(v70);
      v72 = ConstructPartialMsgW(0x2000000u, "SPGuidFromString failed for %s. hr = 0x%X", v71, v59);
      WdsSetupLogMessageW(
        v72,
        819200,
        L"D",
        0,
        2164,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v69,
        v68,
        0,
        0);
LABEL_15:
      v65 = v1013;
LABEL_141:
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v65);
      goto LABEL_142;
    }
    v73 = 1;
    v74 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
    v75 = UnBCL::String::get_CString(v74);
    v76 = SPReadConfigValue(L"BootEntries", L"ExternalRollback", v75);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1012, v76);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v1012) )
    {
      v73 = 0;
      v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
      v78 = UnBCL::String::get_CString(v77);
      v79 = SPReadConfigValue(L"BootEntries", L"SafeOS", v78);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v955, v79);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v1012, v955);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v955);
      if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v1012) )
      {
        v80 = GetLastError();
        v81 = v80 < 0;
        if ( v80 > 0 )
          v81 = 1;
        if ( v81 )
        {
          v82 = GetLastError();
          v59 = v82;
          if ( v82 > 0 )
            v59 = (unsigned __int16)v82 | 0x80070000;
        }
        else
        {
          v59 = -2147467259;
        }
        v83 = GetLastError();
        v84 = CurrentIP();
        v85 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
        v86 = (const char *)UnBCL::String::get_CString(v85);
        v87 = ConstructPartialMsgW(
                0x2000000u,
                "Failed to read rollback or safe OS entry GUIDs from %s. hr = 0x%X",
                v86,
                v59);
        CreateOptions = v83;
        ppSecurityDescriptor = (PSECURITY_DESCRIPTOR *)v84;
        ppsidGroup = 2180;
        goto LABEL_27;
      }
    }
    v1080 = 0;
    v88 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1012);
    v89 = UnBCL::String::get_CString(v88);
    v59 = SPGuidFromString(v89, &v1080);
    if ( v59 < 0 )
    {
      v90 = GetLastError();
      v91 = CurrentIP();
      v92 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1012);
      v93 = (const char *)UnBCL::String::get_CString(v92);
      v87 = ConstructPartialMsgW(0x2000000u, "SPGuidFromString failed for %s. hr = 0x%X", v93, v59);
      CreateOptions = v90;
      ppSecurityDescriptor = (PSECURITY_DESCRIPTOR *)v91;
      ppsidGroup = 2193;
LABEL_27:
      WdsSetupLogMessageW(
        v87,
        819200,
        L"D",
        0,
        ppsidGroup,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        ppSecurityDescriptor,
        CreateOptions,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1012);
      goto LABEL_15;
    }
    v930 = v1079;
    if ( !(*(unsigned int (__fastcall **)(struct IRollback *, struct _GUID *))(*(_QWORD *)v46 + 88LL))(v46, &v930) )
    {
      v94 = GetLastError();
      v95 = CurrentIP();
      v96 = ConstructPartialMsgW(0x2000000u, "%hs: Failed to save the new OS GUID", "CRelocateOS::DoExecute");
      CreateOptionsa = v94;
      ppSecurityDescriptora = (PSECURITY_DESCRIPTOR *)v95;
      ppsidGroupa = 2202;
LABEL_32:
      WdsSetupLogMessageW(
        v96,
        819200,
        L"D",
        0,
        ppsidGroupa,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        ppSecurityDescriptora,
        CreateOptionsa,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1012);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1013);
      goto LABEL_33;
    }
    v930 = v1080;
    if ( !(*(unsigned int (__fastcall **)(struct IRollback *, struct _GUID *, _QWORD))(*(_QWORD *)v46 + 80LL))(
            v46,
            &v930,
            v73) )
    {
      v97 = GetLastError();
      v98 = CurrentIP();
      v96 = ConstructPartialMsgW(0x2000000u, "%hs: Failed to save the rollback GUID", "CRelocateOS::DoExecute");
      CreateOptionsa = v97;
      ppSecurityDescriptora = (PSECURITY_DESCRIPTOR *)v98;
      ppsidGroupa = 2208;
      goto LABEL_32;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1012);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1013);
LABEL_37:
    v99 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
    v100 = UnBCL::String::get_CString(v99);
    v101 = SPReadConfigValue(L"Parameters", L"MigrationScope", v100);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1033, v101);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v1033) )
    {
      P = UnBCL::SmartPtr<UnBCL::String>::get_P(v1033);
      v918 = SPGetMigScopeFromString(P);
    }
    else
    {
      v918 = 0;
      v59 = GetLastError();
      if ( (unsigned int)(v59 - 2) > 1 )
      {
        if ( v59 > 0 )
          v59 = (unsigned __int16)v59 | 0x80070000;
        v102 = GetLastError();
        v103 = CurrentIP();
        v104 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
        v105 = (const char *)UnBCL::String::get_CString(v104);
        v106 = ConstructPartialMsgW(0x2000000u, "Failed to read the migration scope from %s. hr = 0x%08X", v105, v59);
        WdsSetupLogMessageW(
          v106,
          819200,
          L"D",
          0,
          2225,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v103,
          v102,
          0,
          0);
        v65 = v1033;
        goto LABEL_141;
      }
    }
    v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
    v109 = UnBCL::String::get_CString(v108);
    v110 = SPReadOSPiecesSection(L"OS.OLD.Pieces", v109);
    v992 = &UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
    v993 = 0;
    UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v992, v110);
    if ( v993 )
    {
      v111 = GetLastError();
      v112 = CurrentIP();
      v113 = ConstructPartialMsgW(0x4000000u, "Final list of source OS pieces:");
      WdsSetupLogMessageW(
        v113,
        819200,
        L"D",
        0,
        2238,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v112,
        v111,
        0,
        0);
      for ( i = 0; ; ++i )
      {
        v115 = (int (__fastcall ***)(_QWORD))(v993 + 8 + *(int *)(*(_QWORD *)(v993 + 8) + 12LL));
        if ( (int)i >= (**v115)(v115) )
          break;
        v116 = v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL;
        if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v116 + 24LL))(v116, i) )
        {
          v117 = GetLastError();
          v118 = CurrentIP();
          v119 = *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + v993 + 8;
          v120 = &cchOriginalDestLength;
          if ( !*(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v119 + 24LL))(v119, i)
                          + 80LL) )
            v120 = L"do not ";
          v121 = v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL;
          v122 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v121 + 24LL))(v121, i);
          v123 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v122 + 72LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v122 + 72LL));
          v902 = (const char *)UnBCL::String::get_CString(v123);
          v124 = *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + v993 + 8;
          v125 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v124 + 24LL))(v124, i);
          v126 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v125 + 32LL);
          v927 = (const char *)UnBCL::String::get_CString(v126);
          v127 = *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + v993 + 8;
          v128 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 24LL))(v127, i);
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(*v128 + 16LL) )
          {
            v129 = v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL;
            v130 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v129 + 24LL))(v129, i);
            v131 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v130 + 16LL);
            v132 = UnBCL::String::get_CString(v131);
          }
          else
          {
            v132 = L"<NULL>";
          }
          v133 = ConstructPartialMsgW(
                   0x4000000u,
                   "    Name: %s, Original path: %s, Current path: %s (%sallow relocation)",
                   (const char *)v132,
                   v927,
                   v902,
                   (const char *)v120);
          WdsSetupLogMessageW(
            v133,
            819200,
            L"D",
            0,
            2250,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v118,
            v117,
            0,
            0);
        }
      }
    }
    else
    {
      v134 = GetLastError();
      v135 = CurrentIP();
      v136 = ConstructPartialMsgW(0x4000000u, "No source OS pieces found");
      WdsSetupLogMessageW(
        v136,
        819200,
        L"D",
        0,
        2256,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v135,
        v134,
        0,
        0);
    }
    v137 = UnBCL::Object::operator new(0x80u);
    if ( v137 )
      v138 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
               v137,
               1);
    else
      v138 = 0;
    v998 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
    v999 = 0;
    UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v998, v138);
    (*(void (__fastcall **)(_QWORD *, __int64))(*v999 + 40LL))(v999, 1);
    v139 = 0;
    while ( 1 )
    {
      v140 = UnBCL::String::Format(L"Source%d", v139);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1047, v140);
      v141 = UnBCL::String::Format(L"Destination%d", v139);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1046, v141);
      v142 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
      v143 = UnBCL::String::get_CString(v142);
      v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1047);
      v145 = UnBCL::String::get_CString(v144);
      v146 = SPReadConfigGlobalPath(L"WindowsOld.Mappings", v145, v143);
      v1014 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      v1015 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v1014, v146);
      v147 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
      v148 = UnBCL::String::get_CString(v147);
      v149 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1046);
      v150 = UnBCL::String::get_CString(v149);
      v151 = SPReadConfigGlobalPath(L"WindowsOld.Mappings", v150, v148);
      v1009 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      v1010 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v1009, v151);
      if ( !v1015 )
        break;
      if ( !v1010 )
        goto LABEL_67;
      v152 = (UnBCL::String *)(*(__int64 (**)(void))(*(_QWORD *)v1015 + 16LL))();
      v153 = UnBCL::String::TrimEnd(v152, L"\\ ");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1062, v153);
      v154 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1010 + 16LL))(v1010);
      v155 = UnBCL::String::TrimEnd(v154, L"\\ ");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1078, v155);
      v156 = (char *)v999 + *(int *)(v999[1] + 16LL);
      v903 = *(void (__fastcall **)(char *, __int64))(*((_QWORD *)v156 + 1) + 40LL);
      v157 = UnBCL::Object::operator new(0x40u);
      if ( v157 )
      {
        v158 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1078);
        v159 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1062);
        v160 = UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(
                 v157,
                 v159,
                 v158,
                 1,
                 1,
                 1);
      }
      else
      {
        v160 = 0;
      }
      v903(v156 + 8, v160);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1078);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1062);
      ++v139;
      v1009 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v1009);
      v1014 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v1014);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1046);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1047);
    }
    if ( v1010 )
    {
LABEL_67:
      v161 = GetLastError();
      v162 = CurrentIP();
      v163 = ConstructPartialMsgW(
               0x2000000u,
               "Incorrect mappings detected in OS relocation phase, setup will continue but there might be errors");
      WdsSetupLogMessageW(
        v163,
        819200,
        L"D",
        0,
        2279,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v162,
        v161,
        0,
        0);
      v1009 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v1009);
      v1014 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v1014);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1046);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1047);
    }
    else
    {
      v1009 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v1009);
      v1014 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v1014);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1046);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1047);
    }
    v164 = (int (__fastcall ***)(_QWORD))((char *)v999 + *(int *)(v999[1] + 12LL) + 8);
    if ( (**v164)(v164) <= 0 )
    {
      v181 = GetLastError();
      v182 = CurrentIP();
      v183 = ConstructPartialMsgW(0x4000000u, "No source symbolic mappings found");
      WdsSetupLogMessageW(
        v183,
        819200,
        L"D",
        0,
        2300,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v182,
        v181,
        0,
        0);
    }
    else
    {
      v165 = GetLastError();
      v166 = CurrentIP();
      v167 = ConstructPartialMsgW(0x4000000u, "Initial list of source symbolic mappings:");
      WdsSetupLogMessageW(
        v167,
        819200,
        L"D",
        0,
        2292,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v166,
        v165,
        0,
        0);
      for ( j = 0; ; ++j )
      {
        v169 = (int (__fastcall ***)(_QWORD))((char *)v999 + *(int *)(v999[1] + 12LL) + 8);
        if ( (int)j >= (**v169)(v169) )
          break;
        v170 = GetLastError();
        v171 = CurrentIP();
        v172 = (__int64)v999 + *(int *)(v999[1] + 16LL) + 8;
        v173 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v172 + 24LL))(v172, j);
        v174 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v173 + 16LL))(*v173);
        v175 = (const char *)UnBCL::String::get_CString(v174);
        v176 = (__int64)v999 + *(int *)(v999[1] + 16LL) + 8;
        v177 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v176 + 24LL))(v176, j);
        v178 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v177)(*v177);
        v179 = (const char *)UnBCL::String::get_CString(v178);
        v180 = ConstructPartialMsgW(0x4000000u, "    %s => %s", v179, v175);
        WdsSetupLogMessageW(
          v180,
          819200,
          L"D",
          0,
          2295,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v171,
          v170,
          0,
          0);
      }
    }
    v184 = UnBCL::Object::operator new(0x80u);
    if ( v184 )
      v185 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
               v184,
               1);
    else
      v185 = 0;
    v1000 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
    v1001 = 0;
    UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v1000, v185);
    (*(void (__fastcall **)(_QWORD *, __int64))(*v1001 + 40LL))(v1001, 1);
    v186 = v993;
    if ( v993 )
    {
      for ( k = 0; ; ++k )
      {
        v188 = (int (__fastcall ***)(_QWORD))(v186 + 8 + *(int *)(*(_QWORD *)(v186 + 8) + 12LL));
        if ( (int)k >= (**v188)(v188) )
          break;
        v189 = v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL;
        if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v189 + 24LL))(v189, k) )
        {
          v190 = v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL;
          v191 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v190 + 24LL))(v190, k);
          v192 = UnBCL::SmartPtr<UnBCL::String>::get_P(*v191 + 48LL);
          v193 = *(int *)(*(_QWORD *)(v993 + 8) + 16LL);
          if ( v192 )
            v194 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v993 + v193 + 8) + 24LL))(
                                v993 + v193 + 8,
                                k)
                 + 48LL;
          else
            v194 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v993 + v193 + 8) + 24LL))(
                                v993 + v193 + 8,
                                k)
                 + 32LL;
          v195 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v194);
          PathRoot = UnBCL::Path::GetPathRoot(v195);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1038, PathRoot);
          v197 = v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL;
          v198 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v197 + 24LL))(v197, k);
          v199 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v198 + 72LL)
                                                                                 + 16LL))(*(_QWORD *)(*(_QWORD *)v198 + 72LL));
          v200 = UnBCL::Path::GetPathRoot(v199);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1048, v200);
          for ( m = 0; ; ++m )
          {
            v202 = (int (__fastcall ***)(_QWORD))((char *)v1001 + *(int *)(v1001[1] + 12LL) + 8);
            if ( m >= (**v202)(v202) )
              goto LABEL_88;
            v203 = (char *)v1001 + *(int *)(v1001[1] + 16LL) + 8;
            v204 = (_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v203 + 24LL))(v203, (unsigned int)m);
            v205 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v204)(*v204);
            v206 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1038);
            if ( !UnBCL::String::Compare(v206, v205, 1) )
              break;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v954, 0);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v1038, v954);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v954);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v953, 0);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v1048, v953);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v953);
LABEL_88:
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v1038) && UnBCL::SmartPtr<UnBCL::String>::get_P(v1048) )
          {
            v207 = (char *)v1001 + *(int *)(v1001[1] + 16LL);
            v904 = *(void (__fastcall **)(char *, __int64))(*((_QWORD *)v207 + 1) + 40LL);
            v208 = UnBCL::Object::operator new(0x40u);
            if ( v208 )
            {
              v209 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1048);
              v210 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1038);
              v211 = UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(
                       v208,
                       v210,
                       v209,
                       1,
                       1,
                       1);
            }
            else
            {
              v211 = 0;
            }
            v904(v207 + 8, v211);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1048);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1038);
        }
        v186 = v993;
      }
    }
    if ( v1001 )
    {
      v212 = GetLastError();
      v213 = CurrentIP();
      v214 = ConstructPartialMsgW(0x4000000u, "Final list of Windows.old roots:");
      WdsSetupLogMessageW(
        v214,
        819200,
        L"D",
        0,
        2339,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v213,
        v212,
        0,
        0);
      for ( n = 0; ; ++n )
      {
        v216 = (int (__fastcall ***)(_QWORD))((char *)v1001 + *(int *)(v1001[1] + 12LL) + 8);
        if ( n >= (**v216)(v216) )
          break;
        v217 = (char *)v1001 + *(int *)(v1001[1] + 16LL) + 8;
        v218 = *(_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v217 + 24LL))(v217, (unsigned int)n);
        v219 = GetLastError();
        v220 = CurrentIP();
        v221 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v218 + 16LL))(v218);
        v905 = (const char *)UnBCL::String::get_CString(v221);
        if ( (**(__int64 (__fastcall ***)(__int64))v218)(v218) )
        {
          v222 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v218)(v218);
          v223 = UnBCL::String::get_CString(v222);
        }
        else
        {
          v223 = L"<NULL>";
        }
        v224 = ConstructPartialMsgW(0x4000000u, "    %s = %s", (const char *)v223, v905);
        WdsSetupLogMessageW(
          v224,
          819200,
          L"D",
          0,
          2348,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v220,
          v219,
          0,
          0);
      }
    }
    while ( 1 )
    {
      v225 = (int (__fastcall ***)(_QWORD))((char *)v999 + *(int *)(v999[1] + 12LL) + 8);
      v226 = (**v225)(v225) > 0;
      v227 = v999[1];
      if ( !v226 )
        break;
      v228 = (char *)v999 + *(int *)(v227 + 16) + 8;
      v229 = *(_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v228 + 24LL))(v228, 0);
      v230 = (int (__fastcall ***)(_QWORD))((char *)v1001 + *(int *)(v1001[1] + 12LL) + 8);
      if ( (**v230)(v230) > 0 )
      {
        v231 = (char *)v1001 + *(int *)(v1001[1] + 16LL) + 8;
        v232 = (_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v231 + 24LL))(v231, 0);
        v233 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v232 + 16LL))(*v232);
        v234 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v229 + 16LL))(v229);
        SPIsPathInsideFolder(v234, v233);
      }
      v235 = (char *)v999 + *(int *)(v999[1] + 16LL) + 8;
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v235 + 88LL))(v235, 0);
    }
    v236 = (int (__fastcall ***)(_QWORD))((char *)v999 + *(int *)(v227 + 12) + 8);
    if ( (**v236)(v236) > 0 )
    {
      v237 = GetLastError();
      v238 = CurrentIP();
      v239 = ConstructPartialMsgW(0x4000000u, "Final list of source symbolic mappings:");
      WdsSetupLogMessageW(
        v239,
        819200,
        L"D",
        0,
        2392,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v238,
        v237,
        0,
        0);
      for ( ii = 0; ; ++ii )
      {
        v241 = (int (__fastcall ***)(_QWORD))((char *)v999 + *(int *)(v999[1] + 12LL) + 8);
        if ( (int)ii >= (**v241)(v241) )
          break;
        v242 = GetLastError();
        v243 = CurrentIP();
        v244 = (__int64)v999 + *(int *)(v999[1] + 16LL) + 8;
        v245 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v244 + 24LL))(v244, ii);
        v246 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v245 + 16LL))(*v245);
        v247 = (const char *)UnBCL::String::get_CString(v246);
        v248 = (__int64)v999 + *(int *)(v999[1] + 16LL) + 8;
        v249 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v248 + 24LL))(v248, ii);
        v250 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v249)(*v249);
        v251 = (const char *)UnBCL::String::get_CString(v250);
        v252 = ConstructPartialMsgW(0x4000000u, "    %s => %s", v251, v247);
        WdsSetupLogMessageW(
          v252,
          819200,
          L"D",
          0,
          2395,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v243,
          v242,
          0,
          0);
      }
    }
    v253 = UnBCL::Object::operator new(0xB0u);
    v254 = v253;
    if ( v253 )
    {
      UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v253, 1);
      v254[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
    }
    else
    {
      v254 = 0;
    }
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1005, v254);
    v255 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v255 + 40LL))(v255, 1);
    v256 = v921;
    v257 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v921)(v921);
    v258 = UnBCL::Path::GetPathRoot(v257);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1042, v258);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 272) )
    {
      v259 = UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 272);
      v260 = SPGetStoredObjectsGroup(v921, v259);
      if ( v260 )
      {
        for ( jj = 0; ; ++jj )
        {
          v262 = (int (__fastcall ***)(_QWORD))(v260 + *(int *)(*(_QWORD *)(v260 + 8) + 12LL) + 8LL);
          if ( (int)jj >= (**v262)(v262) )
            break;
          v263 = v260 + *(int *)(*(_QWORD *)(v260 + 8) + 16LL) + 8LL;
          v264 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v263 + 24LL))(v263, jj);
          v265 = _RTDynamicCast_0(
                   *v264,
                   0,
                   &UnBCL::ISerializable `RTTI Type Descriptor',
                   &CStoredPath `RTTI Type Descriptor',
                   0);
          if ( v265 )
          {
            v266 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v265 + 16LL))(v265);
            v267 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
            v268 = v267 + *(int *)(*(_QWORD *)(v267 + 8) + 16LL);
            v906 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v268 + 8) + 40LL);
            v269 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            v270 = v269;
            if ( v269 )
            {
              UnBCL::String::String(v269, v266);
              *(_QWORD *)v270 = &UnBCL::String::`local vftable';
            }
            else
            {
              v270 = 0;
            }
            v906(v268 + 8, v270);
          }
          else
          {
            v271 = v260 + *(int *)(*(_QWORD *)(v260 + 8) + 16LL) + 8LL;
            v272 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 24LL))(v271, jj);
            v273 = _RTDynamicCast_0(
                     *v272,
                     0,
                     &UnBCL::ISerializable `RTTI Type Descriptor',
                     &CStoredString `RTTI Type Descriptor',
                     0);
            v274 = v273;
            if ( v273 )
            {
              v275 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v273 + 8LL))(v273);
              v276 = SPGetStoredPath(v256, v275);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1053, v276);
              if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v1053) )
              {
                v277 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
                v278 = v277 + *(int *)(*(_QWORD *)(v277 + 8) + 16LL);
                v279 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v278 + 8) + 40LL);
                v280 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1053);
                v279(v278 + 8, v280);
              }
              else
              {
                v281 = GetLastError();
                v282 = CurrentIP();
                v283 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v274 + 8LL))(v274);
                v284 = (const char *)UnBCL::String::get_CString(v283);
                v285 = ConstructPartialMsgW(
                         0x3000000u,
                         "%hs: Cannot find stored path for exception ID %s",
                         "CRelocateOS::DoExecute",
                         v284);
                WdsSetupLogMessageW(
                  v285,
                  819200,
                  L"D",
                  0,
                  2431,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                  L"CRelocateOS::DoExecute",
                  v282,
                  v281,
                  0,
                  0);
              }
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1053);
            }
            else
            {
              v286 = GetLastError();
              v287 = CurrentIP();
              v288 = v260 + *(int *)(*(_QWORD *)(v260 + 8) + 16LL) + 8LL;
              v289 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v288 + 24LL))(v288, jj);
              v290 = *(int *)(*(_QWORD *)(*(_QWORD *)v289 + 8LL) + 4LL) + *(_QWORD *)v289 + 8LL;
              v291 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v290 + 32LL))(v290);
              v292 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v967, v291);
              v293 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v292);
              v294 = (const char *)UnBCL::String::get_CString(v293);
              v295 = ConstructPartialMsgW(
                       0x3000000u,
                       "%hs: Found unknown object in exception list. Object: %s",
                       "CRelocateOS::DoExecute",
                       v294);
              WdsSetupLogMessageW(
                v295,
                819200,
                L"D",
                0,
                2435,
                L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                L"CRelocateOS::DoExecute",
                v287,
                v286,
                0,
                0);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v967);
            }
          }
          v256 = v921;
        }
      }
    }
    v296 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v970, L"Recovery\\WindowsRE");
    v297 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1042);
    v298 = UnBCL::Path::Combine(v297, v296);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1052, v298);
    UnBCL::String::~String((UnBCL::String *)v970);
    v299 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
    v300 = v299 + *(int *)(*(_QWORD *)(v299 + 8) + 16LL);
    v301 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v300 + 8) + 40LL);
    v302 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1052);
    v301(v300 + 8, v302);
    v303 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v971, L"Recovery\\DownlevelWindowsRE");
    v304 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1042);
    v305 = UnBCL::Path::Combine(v304, v303);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1061, v305);
    UnBCL::String::~String((UnBCL::String *)v971);
    v306 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
    v307 = v306 + *(int *)(*(_QWORD *)(v306 + 8) + 16LL);
    v308 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v307 + 8) + 40LL);
    v309 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1061);
    v308(v307 + 8, v309);
    v310 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v972, L"Recovery\\ReAgentOld.xml");
    v311 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1042);
    v312 = UnBCL::Path::Combine(v311, v310);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1060, v312);
    UnBCL::String::~String((UnBCL::String *)v972);
    v313 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
    v314 = v313 + *(int *)(*(_QWORD *)(v313 + 8) + 16LL);
    v315 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v314 + 8) + 40LL);
    v316 = UnBCL::SmartPtr<UnBCL::String>::Steal(v1060);
    v315(v314 + 8, v316);
    v317 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
    v318 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v317 + 8) + 12LL) + v317 + 8);
    if ( (**v318)(v318) <= 0 )
    {
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v959, 0);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v1005, v959);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v959);
    }
    else
    {
      v319 = GetLastError();
      v320 = CurrentIP();
      v321 = ConstructPartialMsgW(0x4000000u, "Final list of source move exceptions:");
      WdsSetupLogMessageW(
        v321,
        819200,
        L"D",
        0,
        2453,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v320,
        v319,
        0,
        0);
      for ( kk = 0; ; ++kk )
      {
        v323 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
        v324 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v323 + 8) + 12LL) + v323 + 8);
        if ( (int)kk >= (**v324)(v324) )
          break;
        v325 = GetLastError();
        v326 = CurrentIP();
        v327 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
        v328 = *(int *)(*(_QWORD *)(v327 + 8) + 16LL) + v327 + 8;
        v329 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v328 + 24LL))(v328, kk);
        v330 = (const char *)UnBCL::String::get_CString(*v329);
        v331 = ConstructPartialMsgW(0x4000000u, "    %s", v330);
        WdsSetupLogMessageW(
          v331,
          819200,
          L"D",
          0,
          2456,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v326,
          v325,
          0,
          0);
        v332 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
        v333 = *(int *)(*(_QWORD *)(v332 + 8) + 16LL) + v332 + 8;
        v334 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v333 + 24LL))(v333, kk);
        v335 = UnBCL::String::get_CString(*v334);
        if ( GetFileAttributesW(v335) == -1 )
        {
          v336 = GetLastError();
          v337 = CurrentIP();
          v338 = ConstructPartialMsgW(0x4000000u, "Exception file/folder does not exist, ignoring");
          WdsSetupLogMessageW(
            v338,
            819200,
            L"D",
            0,
            2460,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v337,
            v336,
            0,
            0);
        }
        else if ( v920 )
        {
          v339 = UnBCL::String::Format(L"%d", 0);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1054, v339);
          v340 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
          if ( v340 )
          {
            v341 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1005);
            v342 = *(int *)(*(_QWORD *)(v341 + 8) + 16LL) + v341 + 8;
            v343 = (struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v342 + 24LL))(
                                              v342,
                                              kk);
            v344 = CGlobalPath::CGlobalPath(v340, *v343);
          }
          else
          {
            v344 = 0;
          }
          v1021 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
          v1022 = 0;
          UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v1021, v344);
          v345 = UnBCL::String::get_CString(v920);
          v346 = v1022;
          v347 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1054);
          v348 = UnBCL::String::get_CString(v347);
          SPWriteConfigGlobalPath(L"Paths.Exceptions", v348, v346, v345);
        }
      }
    }
    v350 = v915;
    if ( *((_QWORD *)v915 + 39) )
    {
      for ( mm = 0; ; ++mm )
      {
        v352 = (int (__fastcall ***)(_QWORD))(*((_QWORD *)v350 + 39)
                                            + 8LL
                                            + *(int *)(*(_QWORD *)(*((_QWORD *)v350 + 39) + 8LL) + 12LL));
        if ( mm >= (**v352)(v352) )
          break;
        v353 = *((_QWORD *)v350 + 39) + *(int *)(*(_QWORD *)(*((_QWORD *)v350 + 39) + 8LL) + 16LL) + 8LL;
        v354 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v353 + 24LL))(v353, (unsigned int)mm);
        v907 = v354;
        if ( v354 )
        {
          v355 = GetLastError();
          v356 = CurrentIP();
          v357 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v354 + 40) + 16LL))(*(_QWORD *)(v354 + 40));
          v358 = (const char *)UnBCL::String::get_CString(v357);
          v359 = *(_DWORD *)(v354 + 64);
          v360 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v907 + 56) + 16LL))(*(_QWORD *)(v907 + 56));
          v361 = (const char *)UnBCL::String::get_CString(v360);
          v362 = ConstructPartialMsgW(
                   0x4000000u,
                   "Suspending WIMBoot entry %I64u (%s, %d) for drive %s",
                   *(_QWORD *)(v907 + 24),
                   v361,
                   v359,
                   v358);
          WdsSetupLogMessageW(
            v362,
            819200,
            L"D",
            0,
            2501,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v356,
            v355,
            0,
            0);
          v363 = *(LARGE_INTEGER *)(v907 + 24);
          v364 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v907 + 40) + 16LL))(*(_QWORD *)(v907 + 40));
          v365 = UnBCL::String::get_CString(v364);
          v366 = WofWimSuspendEntry(v365, v363);
          v367 = GetLastError();
          v368 = CurrentIP();
          if ( v366 >= 0 )
          {
            v370 = ConstructPartialMsgW(0x4000000u, "WIMBoot entry suspended successfully.");
            WdsSetupLogMessageW(
              v370,
              819200,
              L"D",
              0,
              2511,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v368,
              v367,
              0,
              0);
          }
          else
          {
            v369 = ConstructPartialMsgW(0x3000000u, "Failed to suspend WIMBoot entry. Error: 0x%08X", v366);
            WdsSetupLogMessageW(
              v369,
              819200,
              L"D",
              0,
              2506,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v368,
              v367,
              0,
              0);
          }
          v350 = v915;
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v997);
    v371 = 0;
    v985 = 0;
    UnBCL::Exception::Exception((UnBCL::Exception *)v1031);
    v1031[0] = &`CRelocateOS::DoExecute'::`159'::CXXXXXHandledException::`vftable';
    v372 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
    v373 = UnBCL::String::get_CString(v372);
    SPWriteConfigValue(L"WindowsOld.Mappings", 0, 0, v373);
    v1004 = 0;
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1049, 0);
    IsLoaded = WsmIsLoaded(&v1004);
    v375 = GetLastError();
    if ( IsLoaded < 0 )
    {
      v742 = v375;
      v743 = CurrentIP();
      v744 = ConstructPartialMsgW(
               0x2000000u,
               "SETUPMON: Failed to assess whether the monitoring driver is active or not. Error 0x%08X",
               IsLoaded);
      WdsSetupLogMessageW(
        v744,
        819200,
        L"D",
        0,
        2532,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v743,
        v742,
        0,
        0);
      pExceptionObject = v1031;
      throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&pExceptionObject;
    }
    v376 = v375;
    v377 = CurrentIP();
    v378 = &cchOriginalDestLength;
    if ( !v1004 )
      v378 = L"not ";
    v379 = ConstructPartialMsgW(0x4000000u, "SETUPMON: Monitoring driver is %sactive", (const char *)v378);
    WdsSetupLogMessageW(
      v379,
      819200,
      L"D",
      0,
      2537,
      L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
      L"CRelocateOS::DoExecute",
      v377,
      v376,
      0,
      0);
    if ( v1004 )
    {
      v380 = SPGetClientPath();
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v960, v380);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v1049, v960);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v960);
      if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v1049) )
      {
        v745 = GetLastError();
        v746 = v745 < 0;
        if ( v745 > 0 )
          v746 = 1;
        if ( v746 )
        {
          v747 = GetLastError();
          v748 = v747;
          if ( v747 > 0 )
            v748 = (unsigned __int16)v747 | 0x80070000;
        }
        else
        {
          v748 = -2147467259;
        }
        v749 = GetLastError();
        v750 = CurrentIP();
        v751 = ConstructPartialMsgW(0x2000000u, "SETUPMON: Failed to get the client's full path. Error 0x%08X", v748);
        WdsSetupLogMessageW(
          v751,
          819200,
          L"D",
          0,
          2545,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v750,
          v749,
          0,
          0);
        v947 = v1031;
        throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v947;
      }
    }
    v381 = SPCreateSecurityDescriptor(
             L"O:BAG:BAD:P(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A;OICI;0x1200a9;;;BU)(A;OICI;0x1200a9;;;AU)",
             &v985);
    if ( v381 < 0 )
    {
      v752 = GetLastError();
      v753 = CurrentIP();
      v754 = ConstructPartialMsgW(
               0x2000000u,
               "CRelocateOS: Cannot create security descriptor for Windows.old folders. Error: 0x%08X",
               v381);
      WdsSetupLogMessageW(
        v754,
        819200,
        L"D",
        0,
        2554,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v753,
        v752,
        0,
        0);
      v948 = v1031;
      throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v948;
    }
    SecurityAttributes.nLength = 24;
    *(&SecurityAttributes.nLength + 1) = 0;
    SecurityAttributes.lpSecurityDescriptor = v985;
    SecurityAttributes.bInheritHandle = 0;
    *(&SecurityAttributes.bInheritHandle + 1) = 0;
    if ( (**(int (__fastcall ***)(__int64))((char *)v1001 + *(int *)(v1001[1] + 12LL) + 8))((__int64)v1001 + *(int *)(v1001[1] + 12LL) + 8) > 0 )
    {
      v382 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 248);
      v383 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)((char *)v1001
                                                                              + *(int *)(v1001[1] + 16LL)
                                                                              + 8)
                                                                  + 24LL))(
                         (__int64)v1001 + *(int *)(v1001[1] + 16LL) + 8,
                         0);
      v384 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v383 + 16LL))(*v383);
      v385 = UnBCL::Path::Combine(v384, v382);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v961, v385);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v997, v961);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v961);
      v386 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
      v387 = UnBCL::String::get_CString(v386);
      if ( GetFileAttributesW(v387) != -1 && *((_DWORD *)v915 + 66) )
      {
        if ( v1004 )
        {
          v388 = GetLastError();
          v389 = CurrentIP();
          v390 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
          v391 = (const char *)UnBCL::String::get_CString(v390);
          v392 = ConstructPartialMsgW(0x4000000u, "VERBOSE: SETUPMON: Suspending protection for: %s", v391);
          WdsSetupLogMessageW(
            v392,
            819200,
            L"D",
            0,
            2573,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v389,
            v388,
            0,
            0);
          v393 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1049);
          v394 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v997);
          v395 = SPSuspendMonitoringProtection(v394, v393);
          if ( v395 < 0 )
          {
            v755 = GetLastError();
            v756 = CurrentIP();
            v757 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
            v758 = (const char *)UnBCL::String::get_CString(v757);
            v759 = ConstructPartialMsgW(
                     0x2000000u,
                     "SETUPMON: Failed to suspend protection for %s. Error 0x%08X",
                     v758,
                     v395);
            WdsSetupLogMessageW(
              v759,
              819200,
              L"D",
              0,
              2577,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v756,
              v755,
              0,
              0);
            v949 = v1031;
            throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v949;
          }
          v371 = 1;
        }
        v396 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v997);
        if ( !(unsigned int)SPDeleteFolder(v396, 1, 1, 0) )
        {
          v397 = GetLastError();
          v398 = CurrentIP();
          v399 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
          v400 = (const char *)UnBCL::String::get_CString(v399);
          v401 = ConstructPartialMsgW(
                   0x3000000u,
                   "CRelocateOS: Failing to remove existing %s directory, will move out of the way",
                   v400);
          WdsSetupLogMessageW(
            v401,
            819200,
            L"D",
            0,
            2586,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v398,
            v397,
            0,
            0);
        }
      }
      v402 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
      v403 = UnBCL::String::get_CString(v402);
      if ( GetFileAttributesW(v403) != -1 )
      {
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1026);
        v404 = 1;
        for ( nn = 1; nn != 0x7FFFFFFF; nn = v404 )
        {
          v406 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
          v407 = UnBCL::String::get_CString(v406);
          v408 = UnBCL::String::Format(L"%s(%d)", v407, v404);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v962, v408);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v1026, v962);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v962);
          v409 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1026);
          v410 = UnBCL::String::get_CString(v409);
          if ( GetFileAttributesW(v410) == -1 )
          {
            v411 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1026);
            v412 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v997);
            if ( SPMoveFile(v412, v411, 0, 0) )
              break;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v963, 0);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v1026, v963);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v963);
          ++v404;
        }
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v1026) )
        {
          v760 = GetLastError();
          v761 = v760 < 0;
          if ( v760 > 0 )
            v761 = 1;
          if ( v761 )
          {
            v762 = GetLastError();
            v763 = v762;
            if ( v762 > 0 )
              v763 = (unsigned __int16)v762 | 0x80070000;
          }
          else
          {
            v763 = -2147467259;
          }
          v764 = GetLastError();
          v765 = CurrentIP();
          v766 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
          v767 = (const char *)UnBCL::String::get_CString(v766);
          v768 = ConstructPartialMsgW(
                   0x2000000u,
                   "CRelocateOS: Cannot find room to move stale %s out of the way. Error: 0x%08X",
                   v767,
                   v763);
          WdsSetupLogMessageW(
            v768,
            819200,
            L"D",
            0,
            2610,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v765,
            v764,
            0,
            0);
          v950 = v1031;
          throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v950;
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1026);
      }
      if ( !v371 )
        goto LABEL_177;
      v413 = GetLastError();
      v414 = CurrentIP();
      v415 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
      v416 = (const char *)UnBCL::String::get_CString(v415);
      v417 = ConstructPartialMsgW(0x4000000u, "VERBOSE: SETUPMON: Resuming protection for: %s", v416);
      WdsSetupLogMessageW(
        v417,
        819200,
        L"D",
        0,
        2618,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v414,
        v413,
        0,
        0);
      v418 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v997);
      v419 = SPResumeMonitoringProtection(v418);
      if ( v419 >= 0 )
      {
LABEL_177:
        v420 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
        v421 = UnBCL::String::get_CString(v420);
        if ( CreateDirectoryW(v421, &SecurityAttributes) )
        {
          v422 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
          if ( v422 )
          {
            v423 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)((char *)v1001
                                                                                    + *(int *)(v1001[1] + 16LL)
                                                                                    + 8)
                                                                        + 24LL))(
                               (__int64)v1001 + *(int *)(v1001[1] + 16LL) + 8,
                               0);
            v424 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v423 + 16LL))(*v423);
            v425 = CGlobalPath::CGlobalPath(v422, v424);
          }
          else
          {
            v425 = 0;
          }
          v1036 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
          v1037 = 0;
          UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v1036, v425);
          v426 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
          if ( v426 )
          {
            v427 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v997);
            v428 = CGlobalPath::CGlobalPath(v426, v427);
          }
          else
          {
            v428 = 0;
          }
          v1027[0] = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
          v1027[1] = 0;
          UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(v1027, v428);
          v429 = UnBCL::String::Format(L"Source%d", 0);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1064, v429);
          v430 = UnBCL::String::Format(L"Destination%d", 0);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1063, v430);
          v431 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
          v432 = UnBCL::String::get_CString(v431);
          v433 = v1037;
          v434 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1064);
          v435 = UnBCL::String::get_CString(v434);
          SPWriteConfigGlobalPath(L"WindowsOld.Mappings", v435, v433, v432);
        }
        v774 = GetLastError();
        v775 = v774 < 0;
        if ( v774 > 0 )
          v775 = 1;
        if ( v775 )
        {
          v776 = GetLastError();
          v777 = v776;
          if ( v776 > 0 )
            v777 = (unsigned __int16)v776 | 0x80070000;
        }
        else
        {
          v777 = -2147467259;
        }
        v778 = GetLastError();
        v779 = CurrentIP();
        v780 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
        v781 = (const char *)UnBCL::String::get_CString(v780);
        v782 = ConstructPartialMsgW(0x2000000u, "CRelocateOS: Cannot create %s. Error: 0x%08X", v781, v777);
        WdsSetupLogMessageW(
          v782,
          819200,
          L"D",
          0,
          2632,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v779,
          v778,
          0,
          0);
        v952 = v1031;
        throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v952;
      }
      v769 = GetLastError();
      v770 = CurrentIP();
      v771 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v997);
      v772 = (const char *)UnBCL::String::get_CString(v771);
      v773 = ConstructPartialMsgW(0x2000000u, "SETUPMON: Failed to resume protection for %s. Error 0x%08X", v772, v419);
      WdsSetupLogMessageW(
        v773,
        819200,
        L"D",
        0,
        2622,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v770,
        v769,
        0,
        0);
      v951 = v1031;
      throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v951;
    }
    if ( (**(int (__fastcall ***)(__int64))((char *)v999 + *(int *)(v999[1] + 12LL) + 8))((__int64)v999 + *(int *)(v999[1] + 12LL) + 8) > 0
      && (**(int (__fastcall ***)(__int64))((char *)v999 + *(int *)(v999[1] + 12LL) + 8))((__int64)v999 + *(int *)(v999[1] + 12LL) + 8) > 0 )
    {
      v436 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)((char *)v999
                                                                               + *(int *)(v999[1] + 16LL)
                                                                               + 8)
                                                                   + 24LL))(
                          (__int64)v999 + *(int *)(v999[1] + 16LL) + 8,
                          0);
      v437 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
      if ( v437 )
      {
        v438 = (struct UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v436)(v436);
        v439 = CGlobalPath::CGlobalPath(v437, v438);
      }
      else
      {
        v439 = 0;
      }
      v1043 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      v1044 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v1043, v439);
      v440 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
      if ( v440 )
      {
        v441 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v436 + 16LL))(v436);
        v442 = CGlobalPath::CGlobalPath(v440, v441);
      }
      else
      {
        v442 = 0;
      }
      v1039[0] = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
      v1039[1] = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(v1039, v442);
      v443 = UnBCL::String::Format(L"Source%d", 0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1066, v443);
      v444 = UnBCL::String::Format(L"Destination%d", 0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1065, v444);
      v445 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
      v446 = UnBCL::String::get_CString(v445);
      v447 = v1044;
      v448 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1066);
      v449 = UnBCL::String::get_CString(v448);
      SPWriteConfigGlobalPath(L"WindowsOld.Mappings", v449, v447, v446);
    }
    v450 = v993;
    if ( v993 )
    {
      v451 = 0;
      v452 = 0;
      while ( v452 < (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v450 + 8) + 12LL) + v450 + 8))(v450 + 8 + *(int *)(*(_QWORD *)(v450 + 8) + 12LL)) )
      {
        if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v993 + 8) + 16LL)
                                                                               + v993
                                                                               + 8)
                                                                   + 24LL))(
                          v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL,
                          v451) )
        {
          v453 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v993 + 8) + 16LL)
                                                                        + v993
                                                                        + 8)
                                                            + 24LL))(
                   v993 + *(int *)(*(_QWORD *)(v993 + 8) + 16LL) + 8LL,
                   v451);
          v454 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v453 + 72LL)
                                                                                 + 16LL))(*(_QWORD *)(*(_QWORD *)v453 + 72LL));
          v455 = UnBCL::Path::GetPathRoot(v454);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1068, v455);
          v456 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 248);
          v457 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1068);
          v458 = UnBCL::Path::Combine(v457, v456);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1067, v458);
          if ( (int)UnBCL::String::get_Length(v454) > 2
            && UnBCL::String::get_CString(v454)[1] == 58
            && UnBCL::String::get_CString(v454)[2] == 92 )
          {
            v459 = UnBCL::String::get_CString(v454);
            v460 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v973, v459 + 3);
            v461 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1067);
            v462 = UnBCL::Path::Combine(v461, v460);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1055, v462);
            UnBCL::String::~String((UnBCL::String *)v973);
            v463 = GetLastError();
            v908 = CurrentIP();
            v464 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1055);
            v465 = (const char *)UnBCL::String::get_CString(v464);
            v466 = (const char *)UnBCL::String::get_CString(v454);
            v467 = ConstructPartialMsgW(0x4000000u, "CRelocateOS: Moving previous OS piece from %s to %s", v466, v465);
            WdsSetupLogMessageW(
              v467,
              819200,
              L"D",
              0,
              2712,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v908,
              v463,
              0,
              0);
            LODWORD(v465) = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v1005);
            v468 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1055);
            if ( !(unsigned int)SPMoveFileWithShortName((_DWORD)v454, v468, 0, (_DWORD)v465, 0, 0, 0, 0) )
            {
              v469 = GetLastError();
              if ( v469 - 2 > 1 )
              {
                v783 = GetLastError();
                v784 = CurrentIP();
                v785 = (const char *)UnBCL::String::get_CString(v454);
                v786 = ConstructPartialMsgW(
                         0x2000000u,
                         "%hs: Cannot move path %s from the previos OS to Windows.old. Error: 0x%08X",
                         "CRelocateOS::DoExecute",
                         v785,
                         v469);
                WdsSetupLogMessageW(
                  v786,
                  819200,
                  L"D",
                  0,
                  2719,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                  L"CRelocateOS::DoExecute",
                  v784,
                  v783,
                  0,
                  0);
                v941 = v1031;
                throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v941;
              }
            }
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1055);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1067);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1068);
        }
        v452 = ++v451;
        v450 = v993;
      }
    }
    v470 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v974, L"WINDOWS");
    v471 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 208);
    v472 = UnBCL::Path::Combine(v471, v470);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1025, v472);
    UnBCL::String::~String((UnBCL::String *)v974);
    v994 = &UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
    *(_QWORD *)v995 = 0;
    if ( v993 )
    {
      v473 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1002);
      v474 = UnBCL::String::get_CString(v473);
      v475 = SPReadOSPiecesSection(L"OS.NEW.Pieces", v474);
      v931 = (__int64)&UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
      v932 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v931, v475);
      UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v994, v932);
      v931 = (__int64)&UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v931);
      if ( !*(_QWORD *)v995 )
      {
        v476 = UnBCL::Object::operator new(0x80u);
        if ( v476 )
          v477 = UnBCL::ArrayList<COSPieceInfo *>::ArrayList<COSPieceInfo *>(v476, 1);
        else
          v477 = 0;
        *(_QWORD *)v935 = &UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
        *(_QWORD *)v936 = 0;
        UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(v935, v477);
        UnBCL::SmartPtr<UnBCL::ArrayList<unsigned short>>::Assign(&v994, *(_QWORD *)v936);
        *(_QWORD *)v935 = &UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
        UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v935);
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v995 + 40LL))(*(_QWORD *)v995, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1028);
        try
        {
          v1034 = UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
          v1035 = 0;
          v478 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v975, L"Footprint");
          v479 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v921 + 8LL))(v921);
          v480 = UnBCL::Path::Combine(v479, v478);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v956, v480);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v1028, v956);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v956);
          UnBCL::String::~String((UnBCL::String *)v975);
          v481 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1028);
          if ( !UnBCL::Directory::Exists(v481) )
          {
            v482 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1028);
            Dir = UnBCL::Directory::CreateDir(v482);
            v484 = Dir;
            *(_QWORD *)v933 = UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
            *(_QWORD *)v934 = 0;
            if ( Dir )
              UnBCL::Object::AddRef(Dir);
            UnBCL::SmartPtr<UnBCL::DirectoryInfo>::DeAssign(v933);
            *(_QWORD *)v934 = v484;
            if ( v484 )
              UnBCL::Object::AddRef(v484);
            UnBCL::SmartPtr<UnBCL::DirectoryInfo>::DeAssign(&v1034);
            v1035 = v484;
            *(_QWORD *)v933 = UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
            UnBCL::SmartPtr<UnBCL::DirectoryInfo>::DeAssign(v933);
          }
          v1034 = UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::DeAssign(&v1034);
        }
        catch ( UnBCL::Exception *v966 )
        {
          v875 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1028);
          v876 = (const char *)UnBCL::String::get_CString(v875);
          v877 = v966[0];
          pExceptionLogFormat::pExceptionLogFormat(
            (pExceptionLogFormat *)&v1083,
            0x2000000u,
            v966[0],
            "%hs: Failed to create working directory %s",
            "CRelocateOS::DoExecute",
            v876);
          UnBCL::Exception::AddStackTrace(
            v1085[2],
            "long __cdecl CRelocateOS::DoExecute(struct IExecutionContext *,void *,struct IInternalOperationsProgress *)");
          v878 = GetLastError();
          v879 = CurrentIP();
          v880 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1084);
          v881 = (const char *)UnBCL::String::get_CString(v880);
          v882 = ConstructPartialMsgW(v1083, "%s", v881);
          WdsSetupLogMessageW(
            v882,
            819200,
            L"D",
            0,
            2759,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v879,
            v878,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1085);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1084);
          if ( v877 )
            (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v877)(v877, 1);
          SPGetHResultFromMigStatus(4);
          a39 = &STACK[0x10F8];
          throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&a39;
        }
        v485 = *(_QWORD *)v995;
        v486 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1028);
        v487 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1025);
        SPGetOSInformation(v487, v926, v486, 0, v485, 0, 0);
      }
      v488 = GetLastError();
      v489 = CurrentIP();
      v490 = ConstructPartialMsgW(0x4000000u, "Final list of destination OS pieces:");
      WdsSetupLogMessageW(
        v490,
        819200,
        L"D",
        0,
        2795,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v489,
        v488,
        0,
        0);
      v491 = 0;
      for ( i1 = 0;
            i1 < (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 12LL)
                                                  + *(_QWORD *)v995
                                                  + 8LL))(*(_QWORD *)v995 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL)
                                                                                         + 12LL));
            i1 = v491 )
      {
        if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL)
                                                                                        + 16LL)
                                                                               + *(_QWORD *)v995
                                                                               + 8LL)
                                                                   + 24LL))(
                          *(_QWORD *)v995 + *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL) + 8LL,
                          v491) )
        {
          v924 = GetLastError();
          v909 = CurrentIP();
          v493 = &cchOriginalDestLength;
          if ( !*(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL)
                                                                                              + *(_QWORD *)v995
                                                                                              + 8LL)
                                                                                  + 24LL))(
                                         *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL) + *(_QWORD *)v995 + 8LL,
                                         v491)
                          + 80LL) )
            v493 = L"do not ";
          v494 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL)
                                                                                 + 16LL)
                                                                        + *(_QWORD *)v995
                                                                        + 8LL)
                                                            + 24LL))(
                   *(_QWORD *)v995 + *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL) + 8LL,
                   v491);
          v495 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v494 + 72LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v494 + 72LL));
          v496 = (const char *)UnBCL::String::get_CString(v495);
          v497 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL)
                                                                                           + 16LL)
                                                                                  + *(_QWORD *)v995
                                                                                  + 8LL)
                                                                      + 24LL))(
                             *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL) + *(_QWORD *)v995 + 8LL,
                             v491);
          v498 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v497 + 32LL);
          v499 = (const char *)UnBCL::String::get_CString(v498);
          v500 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL)
                                                                                           + 16LL)
                                                                                  + *(_QWORD *)v995
                                                                                  + 8LL)
                                                                      + 24LL))(
                             *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL) + *(_QWORD *)v995 + 8LL,
                             v491);
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(*v500 + 16LL) )
          {
            v501 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL)
                                                                                             + 16LL)
                                                                                    + *(_QWORD *)v995
                                                                                    + 8LL)
                                                                        + 24LL))(
                               *(_QWORD *)v995 + *(int *)(*(_QWORD *)(*(_QWORD *)v995 + 8LL) + 16LL) + 8LL,
                               v491);
            v502 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v501 + 16LL);
            v503 = UnBCL::String::get_CString(v502);
          }
          else
          {
            v503 = L"<NULL>";
          }
          v504 = ConstructPartialMsgW(
                   0x4000000u,
                   "    Name: %s, Original path: %s, Current path: %s (%sallow relocation)",
                   (const char *)v503,
                   v499,
                   v496,
                   (const char *)v493);
          WdsSetupLogMessageW(
            v504,
            819200,
            L"D",
            0,
            2807,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v909,
            v924,
            0,
            0);
        }
        ++v491;
      }
    }
    else
    {
      v505 = GetLastError();
      v506 = CurrentIP();
      v507 = ConstructPartialMsgW(0x4000000u, "No source OS pieces found");
      WdsSetupLogMessageW(
        v507,
        819200,
        L"D",
        0,
        2814,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v506,
        v505,
        0,
        0);
    }
    v925 = 0;
    v508 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1025);
    if ( (unsigned int)SPIsOverlayOS(v508) )
    {
      v509 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1025);
      if ( (unsigned int)SPIsOverlayOSMounted(v509) )
      {
        v510 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1025);
        v381 = SPUnmountOverlayOS(v510);
        if ( v381 < 0 )
        {
          v787 = GetLastError();
          v788 = CurrentIP();
          v789 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1025);
          v790 = (const char *)UnBCL::String::get_CString(v789);
          v791 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Cannot unmount overlay for %s. Error: 0x%08X",
                   "CRelocateOS::DoExecute",
                   v790,
                   v381);
          WdsSetupLogMessageW(
            v791,
            819200,
            L"D",
            0,
            2832,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v788,
            v787,
            0,
            0);
          v938 = v1031;
          throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v938;
        }
        v925 = 1;
      }
    }
    v511 = GetLastError();
    v512 = CurrentIP();
    v513 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 224);
    v514 = (const char *)UnBCL::String::get_CString(v513);
    v515 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 208);
    v516 = (const char *)UnBCL::String::get_CString(v515);
    v517 = ConstructPartialMsgW(0x4000000u, "CRelocateOS: Moving new OS pieces from %s to %s", v516, v514);
    WdsSetupLogMessageW(
      v517,
      819200,
      L"D",
      0,
      2838,
      L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
      L"CRelocateOS::DoExecute",
      v512,
      v511,
      0,
      0);
    v518 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 208);
    v519 = UnBCL::String::get_CString(v518);
    if ( GetFileAttributesW(v519) == -1 )
    {
      v792 = GetLastError();
      v793 = CurrentIP();
      v794 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 208);
      v795 = (const char *)UnBCL::String::get_CString(v794);
      v796 = ConstructPartialMsgW(0x2000000u, "CRelocateOS: Can't find the new OS installation in %s", v795);
      WdsSetupLogMessageW(
        v796,
        819200,
        L"D",
        0,
        2841,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v793,
        v792,
        0,
        0);
      v939 = v1031;
      throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v939;
    }
    if ( *((_DWORD *)v915 + 60) )
    {
      SecurityDescriptor = 0;
      v520 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 208);
      v521 = UnBCL::String::get_CString(v520);
      NamedSecurityInfoW = GetNamedSecurityInfoW(v521, SE_FILE_OBJECT, 0xF000001F, 0, 0, 0, 0, &SecurityDescriptor);
      v523 = NamedSecurityInfoW;
      if ( NamedSecurityInfoW )
      {
        if ( NamedSecurityInfoW > 0 )
          v523 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
        v797 = GetLastError();
        v798 = CurrentIP();
        v799 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 208);
        v800 = (const char *)UnBCL::String::get_CString(v799);
        v801 = ConstructPartialMsgW(
                 0x2000000u,
                 "CRelocateOS: Cannot access security information for source root %s (error 0x%08X)",
                 v800,
                 v523);
        WdsSetupLogMessageW(
          v801,
          819200,
          L"D",
          0,
          2874,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v798,
          v797,
          0,
          0);
        v940 = v1031;
        throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v940;
      }
      if ( SecurityDescriptor )
      {
        DestinationString = 0;
        memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
        IoStatusBlock = 0;
        SourceString = 0;
        FileHandle = 0;
        StringSecurityDescriptor = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
               SecurityDescriptor,
               1u,
               0xF000001F,
               &StringSecurityDescriptor,
               0) )
        {
          v528 = GetLastError();
          v529 = CurrentIP();
          v530 = (const char *)StringSecurityDescriptor;
          v531 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 224);
          v532 = (const char *)UnBCL::String::get_CString(v531);
          v533 = ConstructPartialMsgW(0x4000000u, "CRelocateOS: Setting ACL on %s: %s", v532, v530);
          WdsSetupLogMessageW(
            v533,
            819200,
            L"D",
            0,
            2899,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v529,
            v528,
            0,
            0);
          LocalFree(StringSecurityDescriptor);
          StringSecurityDescriptor = 0;
        }
        else
        {
          v524 = GetLastError();
          v525 = CurrentIP();
          v526 = GetLastError();
          v527 = ConstructPartialMsgW(
                   0x3000000u,
                   "CRelocateOS: ConvertSecurityDescriptorToStringSecurityDescriptor failed. Error: 0x%08X",
                   v526);
          WdsSetupLogMessageW(
            v527,
            819200,
            L"D",
            0,
            2895,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v525,
            v524,
            0,
            0);
        }
        v534 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 224);
        v535 = UnBCL::String::get_CString(v534);
        v381 = DosPathToNt(v535, &SourceString);
        if ( v381 < 0 )
        {
          v802 = GetLastError();
          v803 = CurrentIP();
          v804 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 224);
          v805 = (const char *)UnBCL::String::get_CString(v804);
          v806 = ConstructPartialMsgW(
                   0x2000000u,
                   "CRelocateOS: Cannot convert destination path to NT path for %s (error 0x%08X)",
                   v805,
                   v381);
          WdsSetupLogMessageW(
            v806,
            819200,
            L"D",
            0,
            2907,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v803,
            v802,
            0,
            0);
          v942 = v1031;
          throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v942;
        }
        RtlInitUnicodeString(&DestinationString, SourceString);
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v536 = NtCreateFile(
                 &FileHandle,
                 0x10C0000u,
                 &ObjectAttributes,
                 &IoStatusBlock,
                 0,
                 0x80u,
                 7u,
                 1u,
                 0x204000u,
                 0,
                 0);
        if ( v536 >= 0 )
        {
          pOwner = 0;
          bOwnerDefaulted = 0;
          pGroup = 0;
          bGroupDefaulted = 0;
          bDaclPresent = 0;
          pDacl = 0;
          bDaclDefaulted = 0;
          bSaclPresent = 0;
          pSacl = 0;
          bSaclDefaulted = 0;
          pControl = 0;
          v540 = 0;
          v541 = 0;
          dwRevision = 0;
          GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted);
          GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bGroupDefaulted);
          GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
          GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted);
          GetSecurityDescriptorControl(SecurityDescriptor, &pControl, &dwRevision);
          v542 = ((pControl & 0x2000) != 0 ? 0x40000000 : 0x10000000)
               | ((pControl & 0x1000) != 0 ? 0x80000000 : 0x20000000)
               | (bSaclPresent != 0 ? 0x10018 : 0)
               | (bDaclPresent != 0 ? 4 : 0)
               | (pGroup != 0 ? 2 : 0)
               | (pOwner != 0);
          if ( (pControl & 0x400) != 0 )
          {
            v540 = 256;
            v541 = 256;
          }
          if ( (pControl & 0x800) != 0 )
          {
            v540 |= 0x200u;
            v541 |= 0x200u;
          }
          if ( v540 && !SetSecurityDescriptorControl(SecurityDescriptor, v540, v541) )
          {
            v543 = GetLastError();
            v544 = v543 < 0;
            if ( v543 > 0 )
              v544 = 1;
            if ( v544 )
            {
              v545 = GetLastError();
              v381 = v545;
              if ( v545 > 0 )
                v381 = (unsigned __int16)v545 | 0x80070000;
            }
            else
            {
              v381 = -2147467259;
            }
            v546 = GetLastError();
            v910 = CurrentIP();
            v547 = ConstructPartialMsgW(
                     0x2000000u,
                     "CRelocateOS: Failed to set security descriptor control on destination NT path %s. Error: 0x%08X",
                     (const char *)SourceString,
                     v381);
            WdsSetupLogMessageW(
              v547,
              819200,
              L"D",
              0,
              2985,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v910,
              v546,
              0,
              0);
          }
          if ( v381 >= 0 )
          {
            v548 = NtSetSecurityObject(FileHandle, v542, SecurityDescriptor);
            if ( v548 < 0 )
            {
              v381 = v548 | 0x10000000;
              v549 = GetLastError();
              v550 = CurrentIP();
              v551 = ConstructPartialMsgW(
                       0x2000000u,
                       "CRelocateOS: Failed to set security on destination NT path %s. Error: 0x%08X",
                       (const char *)SourceString,
                       v381);
              WdsSetupLogMessageW(
                v551,
                819200,
                L"D",
                0,
                2995,
                L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                L"CRelocateOS::DoExecute",
                v550,
                v549,
                0,
                0);
            }
          }
          NtClose(FileHandle);
          FileHandle = 0;
        }
        else
        {
          v381 = v536 | 0x10000000;
          v537 = GetLastError();
          v538 = CurrentIP();
          v539 = ConstructPartialMsgW(
                   0x2000000u,
                   "CRelocateOS: Failed to open the destination NT path %s (error 0x%08X)",
                   (const char *)SourceString,
                   v381);
          WdsSetupLogMessageW(
            v539,
            819200,
            L"D",
            0,
            2935,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v538,
            v537,
            0,
            0);
        }
        v552 = (WCHAR *)SourceString;
        if ( SourceString )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v552);
        }
        SourceString = 0;
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
        if ( v381 < 0 )
        {
          v943 = v1031;
          throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v943;
        }
      }
    }
    v554 = UnBCL::Object::operator new(0xB0u);
    v555 = v554;
    if ( v554 )
    {
      UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v554, 1);
      v555[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
    }
    else
    {
      v555 = 0;
    }
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1041, v555);
    v556 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1041);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v556 + 40LL))(v556, 1);
    v557 = UnBCL::Object::operator new(0x80u);
    if ( v557 )
      v558 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
               v557,
               1);
    else
      v558 = 0;
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(
      v1040,
      v558);
    v559 = RAII::CAutoCleanupBase<void *>::operator->(v1040);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v559 + 40LL))(v559, 1);
    try
    {
      v560 = v915;
      v561 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 248);
      v562 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 224);
      v563 = UnBCL::Path::Combine(v562, v561);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1073, v563);
      v564 = UnBCL::Object::operator new(0xB0u);
      v565 = v564;
      if ( v564 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v564, 1);
        v565[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v565 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1011, v565);
      v566 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v566 + 40LL))(v566, 1);
      v567 = UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 208);
      Files = UnBCL::Directory::GetFiles(v567, 0, 0);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v1050, Files);
      if ( (unsigned __int8)UnBCL::operator!=(v1050, 0) )
      {
        for ( i2 = 0; ; ++i2 )
        {
          v570 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v1050);
          if ( i2 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v570 + 8) + 12LL) + v570 + 8))(v570 + 8 + *(int *)(*(_QWORD *)(v570 + 8) + 12LL)) )
            break;
          v571 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
          v572 = v571 + *(int *)(*(_QWORD *)(v571 + 8) + 16LL);
          v911 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v572 + 8) + 40LL);
          v573 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          if ( v573 )
          {
            v574 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v1050);
            v575 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v574 + 8) + 16LL) + v574 + 8)
                                                                                             + 24LL))(
                                                    v574 + *(int *)(*(_QWORD *)(v574 + 8) + 16LL) + 8LL,
                                                    (unsigned int)i2);
            UnBCL::String::String(v573, *v575);
            *(_QWORD *)v573 = &UnBCL::String::`local vftable';
          }
          else
          {
            v573 = 0;
          }
          v911(v572 + 8, v573);
        }
        v560 = v915;
      }
      v576 = UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v560 + 208);
      Directories = UnBCL::Directory::GetDirectories(v576, 0, 0);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v1051, Directories);
      if ( (unsigned __int8)UnBCL::operator!=(v1051, 0) )
      {
        for ( i3 = 0; ; ++i3 )
        {
          v579 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v1051);
          if ( i3 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v579 + 8) + 12LL) + v579 + 8))(v579 + 8 + *(int *)(*(_QWORD *)(v579 + 8) + 12LL)) )
            break;
          v580 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
          v581 = v580 + *(int *)(*(_QWORD *)(v580 + 8) + 16LL);
          v912 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v581 + 8) + 40LL);
          v582 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          if ( v582 )
          {
            v583 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v1051);
            v584 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v583 + 8) + 16LL) + v583 + 8)
                                                                                             + 24LL))(
                                                    v583 + *(int *)(*(_QWORD *)(v583 + 8) + 16LL) + 8LL,
                                                    (unsigned int)i3);
            UnBCL::String::String(v582, *v584);
            *(_QWORD *)v582 = &UnBCL::String::`local vftable';
          }
          else
          {
            v582 = 0;
          }
          v912(v581 + 8, v582);
        }
        v560 = v915;
      }
      v928 = (unsigned int)(v918 - 3) <= 2;
      v585 = UnBCL::Object::operator new(0xB0u);
      v586 = v585;
      if ( v585 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v585, 1);
        v586[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v586 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1045, v586);
      v587 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1045);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v587 + 40LL))(v587, 1);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1024, 0);
      if ( (unsigned __int8)UnBCL::operator!=((char *)v560 + 288, 0) )
      {
        v588 = UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v560 + 288);
        v589 = SPGetStoredObjectsGroup(v921, v588);
        if ( v589 )
        {
          v590 = UnBCL::Object::operator new(0xB0u);
          v591 = v590;
          if ( v590 )
          {
            UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v590, 1);
            v591[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
          }
          else
          {
            v591 = 0;
          }
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v957, v591);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v1024, v957);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v957);
          v592 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1024);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v592 + 40LL))(v592, 1);
          v593 = 0;
          for ( i4 = 0;
                i4 < (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v589 + 8) + 12LL) + v589 + 8))(v589 + *(int *)(*(_QWORD *)(v589 + 8) + 12LL) + 8LL);
                i4 = v593 )
          {
            v595 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v589 + 8)
                                                                                             + 16LL)
                                                                                    + v589
                                                                                    + 8)
                                                                        + 24LL))(
                               v589 + *(int *)(*(_QWORD *)(v589 + 8) + 16LL) + 8LL,
                               v593);
            v913 = _RTDynamicCast_0(
                     *v595,
                     0,
                     &UnBCL::ISerializable `RTTI Type Descriptor',
                     &CStoredString `RTTI Type Descriptor',
                     0);
            if ( v913 )
            {
              v596 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1024);
              v929 = v596 + *(int *)(*(_QWORD *)(v596 + 8) + 16LL) + 8LL;
              v922 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(*(int *)(*(_QWORD *)(v596 + 8) + 16LL)
                                                                                 + v596
                                                                                 + 8)
                                                                     + 40LL);
              v597 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
              if ( v597 )
              {
                v598 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v913 + 8LL))(v913);
                UnBCL::String::String(v597, v598);
                *(_QWORD *)v597 = &UnBCL::String::`local vftable';
              }
              else
              {
                v597 = 0;
              }
              v922(v929, v597);
            }
            ++v593;
          }
        }
      }
      v599 = 0;
      for ( i5 = 0; ; ++i5 )
      {
        v600 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
        if ( v599 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v600 + 8) + 12LL) + v600 + 8))(v600 + 8 + *(int *)(*(_QWORD *)(v600 + 8) + 12LL)) )
          goto LABEL_426;
        v601 = 0;
        for ( i6 = 0; i6 < 14; i6 = v601 )
        {
          v603 = &(&off_180547E00)[2 * v601];
          v604 = *v603;
          v605 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
          v606 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v605 + 8) + 16LL)
                                                                                          + v605
                                                                                          + 8)
                                                                              + 24LL))(
                                     v605 + *(int *)(*(_QWORD *)(v605 + 8) + 16LL) + 8LL,
                                     i5);
          v607 = UnBCL::String::get_CString(*v606);
          if ( UnBCL::String::Compare(v607, v604, 1) )
            goto LABEL_319;
          switch ( *((_DWORD *)v603 + 2) )
          {
            case 0:
              goto LABEL_318;
            case 1:
              v608 = v928;
              break;
            case 2:
              v608 = v926;
              break;
            default:
              goto LABEL_319;
          }
          if ( v608 )
          {
LABEL_318:
            v609 = GetLastError();
            v610 = CurrentIP();
            v611 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
            v612 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v611 + 8) + 16LL)
                                                                                            + v611
                                                                                            + 8)
                                                                                + 24LL))(
                                       v611 + *(int *)(*(_QWORD *)(v611 + 8) + 16LL) + 8LL,
                                       i5);
            v613 = (const char *)UnBCL::String::get_CString(*v612);
            v614 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v915 + 208);
            v615 = (const char *)UnBCL::String::get_CString(v614);
            v616 = ConstructPartialMsgW(
                     0x4000000u,
                     "CRelocateOS: Path %s\\%s excluded, will not be moved in the final place.",
                     v615,
                     v613);
            WdsSetupLogMessageW(
              v616,
              819200,
              L"D",
              0,
              3107,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v610,
              v609,
              0,
              0);
            goto LABEL_392;
          }
LABEL_319:
          ++v601;
        }
        v617 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
        v618 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v617 + 8) + 16LL) + v617 + 8)
                                                                                          + 24LL))(
                                                 v617 + *(int *)(*(_QWORD *)(v617 + 8) + 16LL) + 8LL,
                                                 i5);
        v619 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 208);
        v620 = UnBCL::Path::Combine(v619, v618);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1006, v620);
        v621 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
        v622 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v621 + 8) + 16LL) + v621 + 8)
                                                                                          + 24LL))(
                                                 v621 + *(int *)(*(_QWORD *)(v621 + 8) + 16LL) + 8LL,
                                                 i5);
        v623 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 224);
        v624 = UnBCL::Path::Combine(v623, v622);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1003, v624);
        if ( (unsigned __int8)UnBCL::operator!=(&v992, 0) && (unsigned __int8)UnBCL::operator!=(&v994, 0) )
        {
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1023);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1029);
          for ( i7 = 0; ; ++i7 )
          {
            v626 = RAII::CAutoCleanupBase<void *>::operator->(&v994);
            if ( (int)i7 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v626 + 8) + 12LL) + v626 + 8))(v626 + 8 + *(int *)(*(_QWORD *)(v626 + 8) + 12LL)) )
              break;
            v627 = RAII::CAutoCleanupBase<void *>::operator->(&v994);
            if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v627 + 8)
                                                                                            + 16LL)
                                                                                   + v627
                                                                                   + 8)
                                                                       + 24LL))(
                              v627 + *(int *)(*(_QWORD *)(v627 + 8) + 16LL) + 8LL,
                              i7) )
            {
              v628 = RAII::CAutoCleanupBase<void *>::operator->(&v994);
              v629 = (CStoredPath **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v628 + 8) + 16LL)
                                                                                            + v628
                                                                                            + 8)
                                                                                + 24LL))(
                                       v628 + *(int *)(*(_QWORD *)(v628 + 8) + 16LL) + 8LL,
                                       i7);
              if ( CStoredPath::RetrievePath(*v629) )
              {
                v630 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1006);
                v631 = RAII::CAutoCleanupBase<void *>::operator->(&v994);
                v632 = (COSPieceInfo **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v631 + 8) + 16LL)
                                                                                               + v631
                                                                                               + 8)
                                                                                   + 24LL))(
                                          v631 + *(int *)(*(_QWORD *)(v631 + 8) + 16LL) + 8LL,
                                          i7);
                CurrentPath = COSPieceInfo::get_CurrentPath(*v632);
                v634 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(struct CGlobalPath *))(*(_QWORD *)CurrentPath
                                                                                               + 16LL))(CurrentPath);
                SPArePathsEqual(v634, v630);
              }
            }
          }
          if ( (unsigned __int8)UnBCL::operator!=(v1029, 0) )
          {
            for ( i8 = 0; ; ++i8 )
            {
              v636 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
              if ( (int)i8 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v636 + 8) + 12LL) + v636 + 8))(v636 + 8 + *(int *)(*(_QWORD *)(v636 + 8) + 12LL)) )
                goto LABEL_338;
              v637 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
              if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v637 + 8)
                                                                                              + 16LL)
                                                                                     + v637
                                                                                     + 8)
                                                                         + 24LL))(
                                v637 + *(int *)(*(_QWORD *)(v637 + 8) + 16LL) + 8LL,
                                i8) )
              {
                v638 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
                v639 = (CStoredPath **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v638 + 8) + 16LL)
                                                                                              + v638
                                                                                              + 8)
                                                                                  + 24LL))(
                                         v638 + *(int *)(*(_QWORD *)(v638 + 8) + 16LL) + 8LL,
                                         i8);
                if ( CStoredPath::RetrievePath(*v639) )
                {
                  v640 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1029);
                  v641 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
                  v642 = (CStoredPath **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v641 + 8) + 16LL)
                                                                                                + v641
                                                                                                + 8)
                                                                                    + 24LL))(
                                           v641 + *(int *)(*(_QWORD *)(v641 + 8) + 16LL) + 8LL,
                                           i8);
                  Path = CStoredPath::RetrievePath(*v642);
                  if ( !UnBCL::String::Compare(Path, v640, 1) )
                    break;
                }
              }
            }
            v644 = (struct UnBCL::Exception *)UnBCL::Object::operator new(0x18u);
            v966[2] = v644;
            if ( v644 )
            {
              v645 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
              v646 = (COSPieceInfo **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v645 + 8) + 16LL)
                                                                                             + v645
                                                                                             + 8)
                                                                                 + 24LL))(
                                        v645 + *(int *)(*(_QWORD *)(v645 + 8) + 16LL) + 8LL,
                                        i8);
              v647 = COSPieceInfo::get_CurrentPath(*v646);
              v648 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(struct CGlobalPath *))(*(_QWORD *)v647 + 16LL))(v647);
              UnBCL::String::String(v644, v648);
              *(_QWORD *)v644 = &UnBCL::String::`local vftable';
            }
            else
            {
              v644 = 0;
            }
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v958, v644);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v1023, v958);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v958);
          }
LABEL_338:
          if ( (unsigned __int8)UnBCL::operator!=(v1023, 0) )
          {
            v649 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1003);
            v650 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1023);
            SPArePathsEqual(v650, v649);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1029);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1023);
        }
        v651 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
        v652 = UnBCL::String::get_CString(v651);
        FileAttributesW = GetFileAttributesW(v652);
        if ( FileAttributesW == -1 )
          goto LABEL_386;
        v653 = 0;
        v901 = 0;
        v923 = 0;
        v654 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1003);
        v655 = UnBCL::String::get_CString(v654);
        if ( GetFileAttributesW(v655) == -1 )
          goto LABEL_366;
        if ( (unsigned __int8)UnBCL::operator!=(&v992, 0) )
        {
          for ( i9 = 0; ; ++i9 )
          {
            v657 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
            if ( (int)i9 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v657 + 8) + 12LL) + v657 + 8))(v657 + 8 + *(int *)(*(_QWORD *)(v657 + 8) + 12LL)) )
              break;
            v658 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
            if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v658 + 8)
                                                                                            + 16LL)
                                                                                   + v658
                                                                                   + 8)
                                                                       + 24LL))(
                              v658 + *(int *)(*(_QWORD *)(v658 + 8) + 16LL) + 8LL,
                              i9) )
            {
              v659 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1003);
              v660 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
              v661 = (COSPieceInfo **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v660 + 8) + 16LL)
                                                                                             + v660
                                                                                             + 8)
                                                                                 + 24LL))(
                                        v660 + *(int *)(*(_QWORD *)(v660 + 8) + 16LL) + 8LL,
                                        i9);
              v662 = COSPieceInfo::get_CurrentPath(*v661);
              v663 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(struct CGlobalPath *))(*(_QWORD *)v662 + 16LL))(v662);
              SPArePathsEqual(v663, v659);
            }
          }
        }
        v664 = GetLastError();
        v665 = CurrentIP();
        v666 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1003);
        v667 = (const char *)UnBCL::String::get_CString(v666);
        v668 = ConstructPartialMsgW(
                 0x4000000u,
                 "CRelocateOS_VERBOSE: Collision detected for path %s, which is not an OS piece.",
                 v667);
        WdsSetupLogMessageW(
          v668,
          819200,
          L"D",
          0,
          3242,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v665,
          v664,
          0,
          0);
        if ( !(unsigned __int8)UnBCL::operator!=(v1024, 0) )
          goto LABEL_357;
        v653 = 1;
        v901 = 1;
        for ( i10 = 0; ; ++i10 )
        {
          v670 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1024);
          if ( i10 >= (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v670 + 8) + 12LL) + v670 + 8))(v670 + 8 + *(int *)(*(_QWORD *)(v670 + 8) + 12LL)) )
          {
            v923 = 1;
LABEL_357:
            if ( !v653 )
              goto LABEL_358;
            goto LABEL_366;
          }
          v671 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1024);
          v672 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v671 + 8) + 16LL) + v671 + 8)
                                                                                            + 24LL))(
                                                   v671 + *(int *)(*(_QWORD *)(v671 + 8) + 16LL) + 8LL,
                                                   (unsigned int)i10);
          v673 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
          v674 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v673 + 8) + 16LL) + v673 + 8)
                                                                                           + 24LL))(
                                                  v673 + *(int *)(*(_QWORD *)(v673 + 8) + 16LL) + 8LL,
                                                  i5);
          if ( !UnBCL::String::Compare(*v674, v672, 1) )
            break;
        }
        v901 = 0;
LABEL_358:
        v675 = GetLastError();
        v676 = CurrentIP();
        v677 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1003);
        v678 = (const char *)UnBCL::String::get_CString(v677);
        v679 = ConstructPartialMsgW(
                 0x4000000u,
                 "CRelocateOS: Collision detected for path %s, which is not an OS piece. Moving out of the way.",
                 v678);
        WdsSetupLogMessageW(
          v679,
          819200,
          L"D",
          0,
          3269,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v676,
          v675,
          0,
          0);
        v680 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1011);
        v681 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(int *)(*(_QWORD *)(v680 + 8) + 16LL) + v680 + 8)
                                                                                          + 24LL))(
                                                 v680 + *(int *)(*(_QWORD *)(v680 + 8) + 16LL) + 8LL,
                                                 i5);
        v682 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1073);
        v683 = UnBCL::Path::Combine(v682, v681);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1056, v683);
        LODWORD(v681) = UnBCL::SmartPtr<UnBCL::String>::get_P(v1056);
        v684 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1003);
        if ( !(unsigned int)SPMoveFileWithShortName(v684, (_DWORD)v681, 0, 0, 0, 1, 0, 0) )
        {
          v685 = GetLastError();
          if ( (unsigned int)(v685 - 2) > 1 )
          {
            v686 = GetLastError();
            v687 = CurrentIP();
            v688 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1003);
            v689 = (const char *)UnBCL::String::get_CString(v688);
            v690 = ConstructPartialMsgW(
                     0x2000000u,
                     "CRelocateOS: Cannot move path %s out of the way of the new OS. Error: 0x%08X",
                     v689,
                     v685);
            WdsSetupLogMessageW(
              v690,
              819200,
              L"D",
              0,
              3280,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v687,
              v686,
              0,
              0);
            if ( v685 > 0 )
              v381 = (unsigned __int16)v685 | 0x80070000;
            else
              v381 = v685;
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1056);
            goto LABEL_364;
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1056);
LABEL_366:
        v691 = GetLastError();
        v692 = CurrentIP();
        v693 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1003);
        v694 = (const char *)UnBCL::String::get_CString(v693);
        v695 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
        v696 = (const char *)UnBCL::String::get_CString(v695);
        v697 = ConstructPartialMsgW(0x4000000u, "CRelocateOS: Moving new OS piece from %s to %s", v696, v694);
        WdsSetupLogMessageW(
          v697,
          819200,
          L"D",
          0,
          3288,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v692,
          v691,
          0,
          0);
        *(_QWORD *)v916 = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v921 + 64LL))(v921);
        v698 = 5;
        v699 = 0;
        for ( i11 = 0; ; v699 = i11 )
        {
          v700 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1003);
          v701 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1006);
          if ( (unsigned int)SPMoveFileWithShortName(v701, v700, 0, 0, 0, v901, v923, 0) )
            goto LABEL_385;
          v702 = GetLastError();
          v703 = v702;
          if ( v702 - 2 <= 1 )
          {
            v724 = GetLastError();
            v725 = CurrentIP();
            v726 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
            v727 = (const char *)UnBCL::String::get_CString(v726);
            v728 = ConstructPartialMsgW(0x3000000u, "CRelocateOS: Source path %s does not exist", v727);
            WdsSetupLogMessageW(
              v728,
              819200,
              L"D",
              0,
              3306,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v725,
              v724,
              0,
              0);
            goto LABEL_385;
          }
          if ( v702 != 5 && v702 != 32 || v698 <= 0 )
            break;
          --v698;
          if ( v699
            || (v704 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1006),
                (int)SPFindAndUnloadHive(v704, 1) < 0) )
          {
            v713 = GetLastError();
            v714 = CurrentIP();
            v715 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
            v716 = (const char *)UnBCL::String::get_CString(v715);
            v717 = ConstructPartialMsgW(
                     0x3000000u,
                     "CRelocateOS: Failed to move path %s, we'll wait for one second and retry",
                     v716);
            WdsSetupLogMessageW(
              v717,
              819200,
              L"D",
              0,
              3332,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v714,
              v713,
              0,
              0);
            Sleep(0x3E8u);
          }
          else
          {
            i11 = 1;
            v705 = GetLastError();
            v706 = CurrentIP();
            v707 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
            v708 = (const char *)UnBCL::String::get_CString(v707);
            v709 = ConstructPartialMsgW(
                     0x3000000u,
                     "CRelocateOS: Failed to move path %s, we've unloaded all hives from it and will retry",
                     v708);
            WdsSetupLogMessageW(
              v709,
              819200,
              L"D",
              0,
              3321,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v706,
              v705,
              0,
              0);
            if ( *(_QWORD *)v916 )
            {
              v710 = *(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, const unsigned __int16 *))(**(_QWORD **)v916 + 16LL);
              v711 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
              v712 = UnBCL::String::get_CString(v711);
              v710(*(_QWORD *)v916, L"SP_RETRY_INFO", L"RetryUnloadHive", v712);
            }
          }
        }
        if ( !v901 && (FileAttributesW & 0x10) != 0 )
        {
          v718 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1003);
          SPDeleteFolder(v718, 1, 1, 0);
        }
        v719 = GetLastError();
        v720 = CurrentIP();
        v721 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1006);
        v722 = (const char *)UnBCL::String::get_CString(v721);
        v723 = ConstructPartialMsgW(
                 0x2000000u,
                 "CRelocateOS: Cannot move path %s from Windows.NEW. Error: 0x%08X",
                 v722,
                 v703);
        WdsSetupLogMessageW(
          v723,
          819200,
          L"D",
          0,
          3350,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CRelocateOS::DoExecute",
          v720,
          v719,
          0,
          0);
        if ( v703 > 0 )
          v381 = (unsigned __int16)v703 | 0x80070000;
        else
          v381 = v703;
LABEL_385:
        if ( v381 < 0 )
        {
LABEL_364:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1003);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1006);
LABEL_426:
          if ( v381 >= 0 )
          {
            v807 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 224);
            v808 = UnBCL::Path::GetPathRoot(v807);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1076, v808);
            v809 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v976, L"WINDOWS");
            v810 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1076);
            v811 = UnBCL::Path::Combine(v810, v809);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1077, v811);
            UnBCL::String::~String((UnBCL::String *)v976);
            v812 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v1045);
            v813 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1077);
            SPRecordOSFootprint(v813, v812);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1077);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1076);
          }
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1024);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1045);
          UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v1051);
          UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v1050);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1011);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1073);
          v814 = v915;
          goto LABEL_476;
        }
LABEL_386:
        if ( v920 )
        {
          v729 = UnBCL::String::Format(L"%d", 0);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1058, v729);
          v730 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
          *(_QWORD *)&v930.Data1 = v730;
          if ( v730 )
          {
            v731 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1003);
            v732 = CGlobalPath::CGlobalPath(v730, v731);
          }
          else
          {
            v732 = 0;
          }
          UnBCL::SmartPtr<CGlobalPath>::SmartPtr<CGlobalPath>(v1057, v732);
          v733 = UnBCL::String::get_CString(v920);
          v734 = (struct CGlobalPath *)RAII::CAutoCleanupBase<void *>::operator->(v1057);
          v735 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1058);
          v736 = UnBCL::String::get_CString(v735);
          SPWriteConfigGlobalPath(L"Quarantine.NewPaths", v736, v734, v733);
        }
        v737 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1045);
        v738 = v737 + *(int *)(*(_QWORD *)(v737 + 8) + 16LL);
        v739 = *(void (__fastcall **)(__int64, struct UnBCL::String *))(*(_QWORD *)(v738 + 8) + 40LL);
        v740 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1003);
        v741 = UnBCL::String::Remove(v740, 0, 2);
        v739(v738 + 8, v741);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1003);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1006);
LABEL_392:
        v599 = i5 + 1;
      }
    }
    catch ( UnBCL::Exception *v965 )
    {
      v883 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v965[0] + 32LL))(v965[0]);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1075, v883);
      v884 = GetLastError();
      v885 = CurrentIP();
      v886 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1075);
      v887 = (const char *)UnBCL::String::get_CString(v886);
      v888 = ConstructPartialMsgW(0x2000000u, "CRelocateOS: Exception while moving files: %s", v887);
      WdsSetupLogMessageW(
        v888,
        819200,
        L"D",
        0,
        3396,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CRelocateOS::DoExecute",
        v885,
        v884,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1075);
      v381 = -2147024865;
      v814 = *(CRelocateOS **)v937;
      v915 = *(CRelocateOS **)v937;
      v921 = *(struct IExecutionContext **)v944;
    }
LABEL_476:
    if ( v381 >= 0 )
    {
      v815 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v1041);
      if ( (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v815 + 8) + 12LL) + v815 + 8))(v815 + 8 + *(int *)(*(_QWORD *)(v815 + 8) + 12LL)) > 0 )
      {
        if ( (unsigned __int8)UnBCL::operator==(&v992, 0) || (unsigned __int8)UnBCL::operator==(&v994, 0) )
        {
          v823 = GetLastError();
          v824 = CurrentIP();
          v825 = ConstructPartialMsgW(
                   0x2000000u,
                   "CRelocateOS: Cannot perform an OS piece relocation without the list of OS pieces from both systems.");
          WdsSetupLogMessageW(
            v825,
            819200,
            L"D",
            0,
            3407,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CRelocateOS::DoExecute",
            v824,
            v823,
            0,
            0);
          v381 = -2147024865;
        }
        else
        {
          v816 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v977, L"WINDOWS");
          v817 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v814 + 224);
          v818 = UnBCL::Path::Combine(v817, v816);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1070, v818);
          UnBCL::String::~String((UnBCL::String *)v977);
          v819 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1070);
          v820 = RAII::CAutoCleanupBase<void *>::operator->(&v994);
          v821 = RAII::CAutoCleanupBase<void *>::operator->(&v992);
          v822 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v1041);
          v381 = SPFixupRelocatedFolders(v822, v821, v820, v819);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1070);
        }
      }
      if ( v381 >= 0 )
      {
        v826 = RAII::CAutoCleanupBase<void *>::operator->(v1040);
        if ( (**(int (__fastcall ***)(__int64))(*(int *)(*(_QWORD *)(v826 + 8) + 12LL) + v826 + 8))(v826 + 8 + *(int *)(*(_QWORD *)(v826 + 8) + 12LL)) > 0 )
        {
          v827 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v978, L"FolderMoveLog.TXT");
          v828 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v921)(v921);
          v829 = UnBCL::Path::Combine(v828, v827);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1030, v829);
          UnBCL::String::~String((UnBCL::String *)v978);
          v830 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1030);
          if ( UnBCL::File::Exists(v830) )
          {
            v831 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v979, L"FolderMoveLog.TXT.BAK");
            v832 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v921)(v921);
            v833 = UnBCL::Path::Combine(v832, v831);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1032, v833);
            UnBCL::String::~String((UnBCL::String *)v979);
            v834 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1032);
            v835 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1030);
            if ( SPMoveFile(v835, v834, 0, 0) )
            {
              try
              {
                Unicode = UnBCL::Encoding::GetUnicode();
                UnBCL::SmartPtr<UnBCL::Encoding>::SmartPtr<UnBCL::Encoding>(v1074, Unicode);
                v847 = (UnBCL::StreamReader *)UnBCL::Object::operator new(0x128u);
                *(_QWORD *)&v930.Data1 = v847;
                if ( v847 )
                {
                  v848 = (struct UnBCL::Encoding *)UnBCL::SmartPtr<UnBCL::Encoding>::get_P(v1074);
                  v849 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1032);
                  UnBCL::StreamReader::StreamReader(v847, v849, v848);
                  *((_QWORD *)v847 + 30) = &UnBCL::StreamReader::`local vftable'{for `UnBCL::Object'};
                }
                else
                {
                  v847 = 0;
                }
                UnBCL::SmartPtr<UnBCL::StreamReader>::SmartPtr<UnBCL::StreamReader>(v1081, v847);
                v850 = UnBCL::Object::operator new(0x50u);
                *(_QWORD *)&v930.Data1 = v850;
                if ( v850 )
                {
                  v851 = UnBCL::SmartPtr<UnBCL::String>::get_P(v1030);
                  UnBCL::FileStream::FileStream(v850, v851, 1, 3, 2, 128, 1);
                  v850[5] = &UnBCL::FileStream::`local vftable'{for `UnBCL::Object'};
                }
                else
                {
                  v850 = 0;
                }
                UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(v1072, v850);
                v852 = (UnBCL::StreamWriter *)UnBCL::Object::operator new(0x80u);
                *(_QWORD *)&v930.Data1 = v852;
                if ( v852 )
                {
                  v853 = (struct UnBCL::Encoding *)UnBCL::Encoding::GetUnicode();
                  v854 = (struct Stream *)UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(v1072);
                  UnBCL::StreamWriter::StreamWriter(v852, v854, v853, 0, 1, 1);
                  *((_QWORD *)v852 + 4) = &UnBCL::StreamWriter::`local vftable'{for `UnBCL::Object'};
                }
                else
                {
                  v852 = 0;
                }
                UnBCL::SmartPtr<UnBCL::StreamWriter>::SmartPtr<UnBCL::StreamWriter>(v1071, v852);
                v855 = RAII::CAutoCleanupBase<void *>::operator->(v1040);
                v856 = RAII::CAutoCleanupBase<void *>::operator->(v1071);
                v857 = RAII::CAutoCleanupBase<void *>::operator->(v1081);
                v381 = CRelocateOS::ProcessJournalEntries(v915, v857, v856, v855);
                if ( v381 < 0 )
                {
                  v858 = GetLastError();
                  v859 = CurrentIP();
                  v860 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1030);
                  v861 = (const char *)UnBCL::String::get_CString(v860);
                  v862 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1032);
                  v863 = (const char *)UnBCL::String::get_CString(v862);
                  v864 = ConstructPartialMsgW(
                           0x2000000u,
                           "CRelocateOS: Failed to write converted entries from %s to %s",
                           v863,
                           v861);
                  WdsSetupLogMessageW(
                    v864,
                    819200,
                    L"D",
                    0,
                    3456,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                    L"CRelocateOS::DoExecute",
                    v859,
                    v858,
                    0,
                    0);
                }
                UnBCL::SmartPtr<UnBCL::StreamWriter>::~SmartPtr<UnBCL::StreamWriter>(v1071);
                UnBCL::SmartPtr<UnBCL::FileStream>::~SmartPtr<UnBCL::FileStream>(v1072);
                UnBCL::SmartPtr<UnBCL::StreamReader>::~SmartPtr<UnBCL::StreamReader>(v1081);
                UnBCL::SmartPtr<UnBCL::Encoding>::~SmartPtr<UnBCL::Encoding>(v1074);
              }
              catch ( UnBCL::Exception *v964 )
              {
                pExceptionLogFormat::pExceptionLogFormat(
                  (pExceptionLogFormat *)v1086,
                  0x2000000u,
                  v964,
                  "CRelocateOS: Error writing converted entries");
                ExceptionPtr = pExceptionLogFormat::GetExceptionPtr((pExceptionLogFormat *)v1086);
                UnBCL::Exception::AddStackTrace(
                  ExceptionPtr,
                  "long __cdecl CRelocateOS::DoExecute(struct IExecutionContext *,void *,struct IInternalOperationsProgress *)");
                v890 = GetLastError();
                v891 = CurrentIP();
                MessageW = (const char *)pExceptionLogFormat::GetMessageW((pExceptionLogFormat *)v1086);
                Severity = pExceptionLogFormat::GetSeverity((pExceptionLogFormat *)v1086);
                v894 = ConstructPartialMsgW(Severity, "%s", MessageW);
                WdsSetupLogMessageW(
                  v894,
                  819200,
                  L"D",
                  0,
                  3461,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                  L"CRelocateOS::DoExecute",
                  v891,
                  v890,
                  0,
                  0);
                pExceptionLogFormat::~pExceptionLogFormat((pExceptionLogFormat *)v1086);
                v381 = -2147467259;
                v915 = *(CRelocateOS **)v937;
              }
            }
            else
            {
              v836 = GetLastError();
              v837 = v836 < 0;
              if ( v836 > 0 )
                v837 = 1;
              if ( v837 )
              {
                v838 = GetLastError();
                v381 = v838;
                if ( v838 > 0 )
                  v381 = (unsigned __int16)v838 | 0x80070000;
              }
              else
              {
                v381 = -2147467259;
              }
              v839 = GetLastError();
              v840 = CurrentIP();
              v841 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1032);
              v842 = (const char *)UnBCL::String::get_CString(v841);
              v843 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1030);
              v844 = (const char *)UnBCL::String::get_CString(v843);
              v845 = ConstructPartialMsgW(
                       0x2000000u,
                       "CRelocateOS: Cannot move journal file from %s to %s. Error: 0x%08X",
                       v844,
                       v842,
                       v381);
              WdsSetupLogMessageW(
                v845,
                819200,
                L"D",
                0,
                3429,
                L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
                L"CRelocateOS::DoExecute",
                v840,
                v839,
                0,
                0);
            }
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1032);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1030);
        }
        if ( v381 >= 0 && v925 )
        {
          v865 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v980, L"WINDOWS");
          v866 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v915 + 224);
          v867 = UnBCL::Path::Combine(v866, v865);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v1059, v867);
          UnBCL::String::~String((UnBCL::String *)v980);
          v868 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v1059);
          v869 = SPMountOverlayOS(v868);
          if ( v869 < 0 )
          {
            v870 = GetLastError();
            v871 = CurrentIP();
            v872 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v1059);
            v873 = (const char *)UnBCL::String::get_CString(v872);
            v874 = ConstructPartialMsgW(
                     0x2000000u,
                     "%hs: Cannot mount overlay for %s. Error: 0x%08X",
                     "CRelocateOS::DoExecute",
                     v873,
                     v869);
            WdsSetupLogMessageW(
              v874,
              819200,
              L"D",
              0,
              3483,
              L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
              L"CRelocateOS::DoExecute",
              v871,
              v870,
              0,
              0);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1059);
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(v1040);
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v1041);
    UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::~SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>(&v994);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1025);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1049);
    v945 = v1031;
    throw (`CRelocateOS::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`159'::CXXXXXHandledException **)&v945;
  }
  v50 = GetLastError();
  v51 = CurrentIP();
  v52 = ConstructPartialMsgW(0x2000000u, "Error setting OS Switch Rollback checkpoint");
  WdsSetupLogMessageW(
    v52,
    819200,
    L"D",
    0,
    2144,
    L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
    L"CRelocateOS::DoExecute",
    v51,
    v50,
    0,
    0);
LABEL_33:
  v59 = -2147467259;
LABEL_142:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v1002);
  return (unsigned int)v59;
}

```

## disassembly

```asm
0x180167100  mov     r11, rsp
0x180167103  push    rdi
0x180167104  push    r12
0x180167106  push    r13
0x180167108  push    r14
0x18016710a  push    r15
0x18016710c  sub     rsp, 0A60h
0x180167113  mov     qword ptr [r11-7C8h], 0FFFFFFFFFFFFFFFEh
0x18016711e  mov     [r11+18h], rbx
0x180167122  mov     [r11+20h], rsi
0x180167126  mov     rax, cs:__security_cookie
0x18016712d  xor     rax, rsp
0x180167130  mov     [rsp+0A88h+var_38], rax
0x180167138  mov     rdi, rdx
0x18016713b  mov     [rsp+0A88h+var_9E8], rdx; int
0x180167143  mov     qword ptr [rsp+0A88h+var_A10], rcx; int
0x180167148  mov     qword ptr [rsp+0A88h+var_958], rcx; int
0x180167150  mov     qword ptr [rsp+0A88h+var_918], rdx; int
0x180167158  xor     r15d, r15d
0x18016715b  mov     r13d, r15d
0x18016715e  mov     dword ptr [rsp+0A88h+var_A20], r15d
0x180167163  mov     dword ptr [rsp+0A88h+var_A28], r15d
0x180167168  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x18016716f  lea     rcx, [r11-798h]
0x180167176  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18016717c  mov     rbx, rax
0x18016717f  mov     rcx, [rdi]
0x180167182  mov     rax, [rcx]
0x180167185  mov     rcx, rdi
0x180167188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016718d  mov     rdx, rbx
0x180167190  mov     rcx, rax
0x180167193  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180167199  mov     rdx, rax
0x18016719c  lea     rcx, [rsp+0A88h+var_560]
0x1801671a4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801671aa  nop
0x1801671ab  lea     rcx, [rsp+0A88h+var_798]
0x1801671b3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801671b9  mov     r14d, r15d
0x1801671bc  mov     qword ptr [rsp+0A88h+var_9F0], r15; int
0x1801671c4  lea     rdx, aFreezeprofiles; "FreezeProfilesFolder"
0x1801671cb  lea     rcx, [rsp+0A88h+var_780]
0x1801671d3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801671d9  nop
0x1801671da  xor     r8d, r8d; int
0x1801671dd  mov     rdx, rax; struct UnBCL::String *
0x1801671e0  mov     rcx, rdi; struct IExecutionContext *
0x1801671e3  call    ?SPGetStoredBOOL@@YAHPEAUIExecutionContext@@PEAVString@UnBCL@@H@Z; SPGetStoredBOOL(IExecutionContext *,UnBCL::String *,int)
0x1801671e8  mov     dword ptr [rsp+0A88h+var_9D0], eax; __int64
0x1801671ef  lea     rcx, [rsp+0A88h+var_780]
0x1801671f7  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801671fd  mov     rax, [rdi]
0x180167200  mov     rcx, rdi
0x180167203  mov     rax, [rax+48h]
0x180167207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016720c  mov     rsi, rax
0x18016720f  test    rax, rax
0x180167212  jz      loc_1801678FC
0x180167218  mov     rcx, [rax]
0x18016721b  mov     rax, [rcx+28h]
0x18016721f  mov     rcx, rsi
0x180167222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167227  test    eax, eax
0x180167229  jnz     short loc_180167259
0x18016722b  mov     rcx, [rsi]
0x18016722e  mov     rax, [rcx+38h]
0x180167232  mov     rcx, rsi
0x180167235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016723a  test    rax, rax
0x18016723d  jz      short loc_180167259
0x18016723f  mov     rax, [rsi]
0x180167242  mov     rcx, rsi
0x180167245  mov     rax, [rax+38h]
0x180167249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016724e  mov     r14, rax
0x180167251  mov     qword ptr [rsp+0A88h+var_9F0], rax
0x180167259  call    cs:__imp_GetLastError
0x18016725f  mov     edi, eax
0x180167261  call    cs:__imp_CurrentIP
0x180167267  mov     rbx, rax
0x18016726a  lea     rdx, aAttemptingToSe; "Attempting to set the OS switch checkpo"...
0x180167271  mov     ecx, 4000000h; unsigned int
0x180167276  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18016727b  mov     [rsp+0A88h+EaLength], r15d
0x180167280  mov     [rsp+0A88h+EaBuffer], r15
0x180167285  mov     [rsp+0A88h+CreateOptions], edi
0x180167289  mov     [rsp+0A88h+ppSecurityDescriptor], rbx
0x18016728e  lea     rdi, aCrelocateosDoe_0; "CRelocateOS::DoExecute"
0x180167295  mov     [rsp+0A88h+ppSacl], rdi
0x18016729a  lea     rdi, aBaseNtsetupSet_48; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801672a1  mov     [rsp+0A88h+ppDacl], rdi
0x1801672a6  mov     dword ptr [rsp+0A88h+ppsidGroup], 85Ah
0x1801672ae  xor     r9d, r9d
0x1801672b1  lea     r12, aD_0; "D"
0x1801672b8  mov     r8, r12
0x1801672bb  mov     edx, 0C8000h
0x1801672c0  mov     rcx, rax
0x1801672c3  call    cs:__imp_WdsSetupLogMessageW
0x1801672c9  xor     r9d, r9d; struct OSRollbackService::ICheckpointParameters *
0x1801672cc  mov     r8, r14; struct UnBCL::String *
0x1801672cf  lea     rdx, aSetupplatformo_0; "SetupPlatformOSSwitchCheckpoint"
0x1801672d6  mov     rcx, rsi; struct IRollback *
0x1801672d9  call    ?SPSetRollbackCheckpoint@@YAHPEAUIRollback@@PEBGPEAVString@UnBCL@@PEAUICheckpointParameters@OSRollbackService@@@Z; SPSetRollbackCheckpoint(IRollback *,ushort const *,UnBCL::String *,OSRollbackService::ICheckpointParameters *)
0x1801672de  test    eax, eax
0x1801672e0  jnz     short loc_180167350
0x1801672e2  call    cs:__imp_GetLastError
0x1801672e8  mov     edi, eax
0x1801672ea  call    cs:__imp_CurrentIP
0x1801672f0  mov     rbx, rax
0x1801672f3  lea     rdx, aErrorSettingOs; "Error setting OS Switch Rollback checkp"...
0x1801672fa  mov     ecx, 2000000h; unsigned int
0x1801672ff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180167304  mov     [rsp+0A88h+EaLength], r15d
0x180167309  mov     [rsp+0A88h+EaBuffer], r15
0x18016730e  mov     [rsp+0A88h+CreateOptions], edi
0x180167312  mov     [rsp+0A88h+ppSecurityDescriptor], rbx
0x180167317  lea     rcx, aCrelocateosDoe_0; "CRelocateOS::DoExecute"
0x18016731e  mov     [rsp+0A88h+ppSacl], rcx
0x180167323  lea     rcx, aBaseNtsetupSet_48; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18016732a  mov     [rsp+0A88h+ppDacl], rcx
0x18016732f  mov     dword ptr [rsp+0A88h+ppsidGroup], 860h
0x180167337  xor     r9d, r9d
0x18016733a  mov     r8, r12
0x18016733d  mov     edx, 0C8000h
0x180167342  mov     rcx, rax
0x180167345  call    cs:__imp_WdsSetupLogMessageW
0x18016734b  jmp     loc_180167842
0x180167350  lea     rcx, [rsp+0A88h+var_560]
0x180167358  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18016735e  mov     rcx, rax
0x180167361  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180167367  mov     r8, rax; lpFileName
0x18016736a  lea     rdx, aNewos_0; "NewOS"
0x180167371  lea     rdi, aBootentries; "BootEntries"
0x180167378  mov     rcx, rdi; lpAppName
0x18016737b  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180167380  mov     rdx, rax
0x180167383  lea     rcx, [rsp+0A88h+var_4E0]
0x18016738b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180167391  nop
0x180167392  lea     rcx, [rsp+0A88h+var_4E0]
0x18016739a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801673a0  test    rax, rax
0x1801673a3  jnz     loc_180167473
0x1801673a9  call    cs:__imp_GetLastError
0x1801673af  test    eax, eax
0x1801673b1  jle     short loc_1801673BD
0x1801673b3  movzx   eax, ax
0x1801673b6  or      eax, 80070000h
0x1801673bb  test    eax, eax
0x1801673bd  jns     short loc_1801673D9
0x1801673bf  call    cs:__imp_GetLastError
0x1801673c5  mov     r14d, eax
0x1801673c8  test    eax, eax
0x1801673ca  jle     short loc_1801673DF
0x1801673cc  movzx   r14d, ax
0x1801673d0  or      r14d, 80070000h
0x1801673d7  jmp     short loc_1801673DF
0x1801673d9  mov     r14d, 80004005h
0x1801673df  call    cs:__imp_GetLastError
0x1801673e5  mov     edi, eax
0x1801673e7  call    cs:__imp_CurrentIP
0x1801673ed  mov     rbx, rax
0x1801673f0  lea     rcx, [rsp+0A88h+var_560]
0x1801673f8  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801673fe  mov     rcx, rax
0x180167401  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180167407  mov     r8, rax
0x18016740a  mov     r9d, r14d
0x18016740d  lea     rdx, aFailedToReadTh_1; "Failed to read the new OS entry GUID fr"...
0x180167414  mov     ecx, 2000000h; unsigned int
0x180167419  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18016741e  mov     [rsp+0A88h+EaLength], r15d
0x180167423  mov     [rsp+0A88h+EaBuffer], r15
0x180167428  mov     [rsp+0A88h+CreateOptions], edi
0x18016742c  mov     [rsp+0A88h+ppSecurityDescriptor], rbx
0x180167431  lea     rcx, aCrelocateosDoe_0; "CRelocateOS::DoExecute"
0x180167438  mov     [rsp+0A88h+ppSacl], rcx
0x18016743d  lea     rcx, aBaseNtsetupSet_48; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180167444  mov     [rsp+0A88h+ppDacl], rcx
0x180167449  mov     dword ptr [rsp+0A88h+ppsidGroup], 86Ch
0x180167451  xor     r9d, r9d
0x180167454  mov     r8, r12
0x180167457  mov     edx, 0C8000h
0x18016745c  mov     rcx, rax
0x18016745f  call    cs:__imp_WdsSetupLogMessageW
0x180167465  nop
0x180167466  lea     rcx, [rsp+0A88h+var_4E0]
0x18016746e  jmp     loc_18016989C
0x180167473  xorps   xmm0, xmm0
0x180167476  movups  xmmword ptr [rsp+0A88h+var_D8.Data1], xmm0
0x18016747e  lea     rcx, [rsp+0A88h+var_4E0]
0x180167486  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18016748c  mov     rcx, rax
0x18016748f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180167495  mov     rcx, rax; unsigned __int16 *
0x180167498  lea     rdx, [rsp+0A88h+var_D8]; struct _GUID *
0x1801674a0  call    ?SPGuidFromString@@YAJPEBGPEAU_GUID@@@Z; SPGuidFromString(ushort const *,_GUID *)
0x1801674a5  mov     r14d, eax
0x1801674a8  test    eax, eax
0x1801674aa  jns     short loc_180167523
0x1801674ac  call    cs:__imp_GetLastError
0x1801674b2  mov     edi, eax
0x1801674b4  call    cs:__imp_CurrentIP
0x1801674ba  mov     rbx, rax
0x1801674bd  lea     rcx, [rsp+0A88h+var_4E0]
0x1801674c5  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801674cb  mov     rcx, rax
0x1801674ce  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801674d4  mov     r8, rax
0x1801674d7  mov     r9d, r14d
0x1801674da  lea     rdx, aSpguidfromstri; "SPGuidFromString failed for %s. hr = 0x"...
0x1801674e1  mov     ecx, 2000000h; unsigned int
0x1801674e6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801674eb  mov     [rsp+0A88h+EaLength], r15d
0x1801674f0  mov     [rsp+0A88h+EaBuffer], r15
0x1801674f5  mov     [rsp+0A88h+CreateOptions], edi
0x1801674f9  mov     [rsp+0A88h+ppSecurityDescriptor], rbx
0x1801674fe  lea     rcx, aCrelocateosDoe_0; "CRelocateOS::DoExecute"
0x180167505  mov     [rsp+0A88h+ppSacl], rcx
0x18016750a  lea     rcx, aBaseNtsetupSet_48; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180167511  mov     [rsp+0A88h+ppDacl], rcx
0x180167516  mov     dword ptr [rsp+0A88h+ppsidGroup], 874h
0x18016751e  jmp     loc_180167451
0x180167523  mov     r12d, 1
0x180167529  mov     ebx, r12d
0x18016752c  lea     rcx, [rsp+0A88h+var_560]
0x180167534  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18016753a  mov     rcx, rax
0x18016753d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180167543  mov     r8, rax; lpFileName
0x180167546  lea     rdx, aExternalrollba; "ExternalRollback"
0x18016754d  mov     rcx, rdi; lpAppName
0x180167550  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180167555  mov     rdx, rax
0x180167558  lea     rcx, [rsp+0A88h+var_4F0]
0x180167560  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180167566  nop
0x180167567  lea     rcx, [rsp+0A88h+var_4F0]
0x18016756f  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180167575  test    rax, rax
0x180167578  jnz     loc_1801676CC
0x18016757e  mov     ebx, r15d
0x180167581  lea     rcx, [rsp+0A88h+var_560]
0x180167589  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18016758f  mov     rcx, rax
0x180167592  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180167598  mov     r8, rax; lpFileName
0x18016759b  lea     rdx, aSafeos; "SafeOS"
0x1801675a2  mov     rcx, rdi; lpAppName
0x1801675a5  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x1801675aa  mov     rdx, rax
0x1801675ad  lea     rcx, [rsp+0A88h+var_888]
0x1801675b5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801675bb  nop
0x1801675bc  lea     rdx, [rsp+0A88h+var_888]
0x1801675c4  lea     rcx, [rsp+0A88h+var_4F0]
0x1801675cc  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1801675d2  nop
0x1801675d3  lea     rcx, [rsp+0A88h+var_888]
0x1801675db  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1801675e1  lea     rcx, [rsp+0A88h+var_4F0]
0x1801675e9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801675ef  test    rax, rax
0x1801675f2  jnz     loc_1801676CC
0x1801675f8  call    cs:__imp_GetLastError
0x1801675fe  test    eax, eax
0x180167600  jle     short loc_18016760C
0x180167602  movzx   eax, ax
0x180167605  or      eax, 80070000h
0x18016760a  test    eax, eax
0x18016760c  jns     short loc_180167628
0x18016760e  call    cs:__imp_GetLastError
0x180167614  mov     r14d, eax
0x180167617  test    eax, eax
0x180167619  jle     short loc_18016762E
0x18016761b  movzx   r14d, ax
0x18016761f  or      r14d, 80070000h
0x180167626  jmp     short loc_18016762E
0x180167628  mov     r14d, 80004005h
0x18016762e  call    cs:__imp_GetLastError
0x180167634  mov     edi, eax
0x180167636  call    cs:__imp_CurrentIP
0x18016763c  mov     rbx, rax
0x18016763f  lea     rcx, [rsp+0A88h+var_560]
0x180167647  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18016764d  mov     rcx, rax
0x180167650  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180167656  mov     r8, rax
0x180167659  mov     r9d, r14d
0x18016765c  lea     rdx, aFailedToReadRo; "Failed to read rollback or safe OS entr"...
0x180167663  mov     ecx, 2000000h; unsigned int
0x180167668  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18016766d  mov     [rsp+0A88h+EaLength], r15d
0x180167672  mov     [rsp+0A88h+EaBuffer], r15
0x180167677  mov     [rsp+0A88h+CreateOptions], edi
0x18016767b  mov     [rsp+0A88h+ppSecurityDescriptor], rbx
0x180167680  lea     rcx, aCrelocateosDoe_0; "CRelocateOS::DoExecute"
0x180167687  mov     [rsp+0A88h+ppSacl], rcx
  ... truncated ...
```
