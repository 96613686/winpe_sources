# CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x180140640`
- end: `0x18014561b`
- name: `?DoExecute@CPrepareSafeOSBootRemoval@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `20443`
- prototype: `int(CPrepareSafeOSBootRemoval *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `44`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180035cc0`
- `0x18003d070`
- `0x180044810`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ae6b4`
- `0x1800c2e14`
- `0x1801178c0`
- `0x18011a588`
- `0x18011b9c0`
- `0x18011c424`
- `0x18012b0a0`
- `0x18012b158`
- `0x18012b26c`
- `0x180131d90`
- `0x180140640`
- `0x1802cd8b0`
- `0x1802d8bfc`
- `0x1802dacac`
- `0x1802e2078`
- `0x1802e4bb8`
- `0x1802e63d4`
- `0x1802e6604`
- `0x1802f2618`
- `0x1802f3cc0`
- `0x1802fb834`
- `0x180329870`
- `0x18032c348`
- `0x18035734c`
- `0x180404554`
- `0x1804048a0`
- `0x18040498c`
- `0x180404acc`
- `0x180404b5c`
- `0x1804791fc`
- `0x180479248`
- `0x18047994c`
- `0x1804799e4`
- `0x180479e40`
- `0x180479f70`
- `0x18047a1b4`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18014212c`
- `ADVAPI32!RegCloseKey` at `0x180144b0e`
- `ADVAPI32!RegCloseKey` at `0x18014212c`
- `ADVAPI32!RegCloseKey` at `0x180144b0e`
- `ADVAPI32!RegCreateKeyExW` at `0x18014208a`
- `ADVAPI32!RegCreateKeyExW` at `0x18014208a`
- `ADVAPI32!RegRestoreKeyW` at `0x180142114`
- `ADVAPI32!RegRestoreKeyW` at `0x180142114`
- `KERNEL32!GetLastError` at `0x18014096f`
- `KERNEL32!GetLastError` at `0x180140a82`
- `KERNEL32!GetLastError` at `0x180140b63`
- `KERNEL32!GetLastError` at `0x180140b7d`
- `KERNEL32!GetLastError` at `0x180140ba1`
- `KERNEL32!GetLastError` at `0x180140f25`
- `KERNEL32!GetLastError` at `0x1801410d6`
- `KERNEL32!GetLastError` at `0x1801413b9`
- `KERNEL32!GetLastError` at `0x180141458`
- `KERNEL32!GetLastError` at `0x1801415c8`
- `KERNEL32!GetLastError` at `0x18014178d`
- `KERNEL32!GetLastError` at `0x1801419c3`
- `KERNEL32!GetLastError` at `0x180141a8e`
- `KERNEL32!GetLastError` at `0x180141d11`
- `KERNEL32!GetLastError` at `0x180141d9d`
- `KERNEL32!GetLastError` at `0x180141e76`
- `KERNEL32!GetLastError` at `0x180142709`
- `KERNEL32!GetLastError` at `0x18014272b`
- `KERNEL32!GetLastError` at `0x180142b36`
- `KERNEL32!GetLastError` at `0x180142b4c`
- `KERNEL32!GetLastError` at `0x180142b69`
- `KERNEL32!GetLastError` at `0x180142f51`
- `KERNEL32!GetLastError` at `0x1801430e7`
- `KERNEL32!GetLastError` at `0x180143194`
- `KERNEL32!GetLastError` at `0x180143238`
- `KERNEL32!GetLastError` at `0x18014324c`
- `KERNEL32!GetLastError` at `0x180143266`
- `KERNEL32!GetLastError` at `0x180143277`
- `KERNEL32!GetLastError` at `0x180143325`
- `KERNEL32!GetLastError` at `0x1801433e6`
- `KERNEL32!GetLastError` at `0x180143493`
- `KERNEL32!GetLastError` at `0x180143540`
- `KERNEL32!GetLastError` at `0x1801435e8`
- `KERNEL32!GetLastError` at `0x180143681`
- `KERNEL32!GetLastError` at `0x180143741`
- `KERNEL32!GetLastError` at `0x1801437ee`
- `KERNEL32!GetLastError` at `0x18014389b`
- `KERNEL32!GetLastError` at `0x18014393f`
- `KERNEL32!GetLastError` at `0x1801439df`
- `KERNEL32!GetLastError` at `0x1801439f6`
- `KERNEL32!GetLastError` at `0x180143a10`
- `KERNEL32!GetLastError` at `0x180143a21`
- `KERNEL32!GetLastError` at `0x180143acb`
- `KERNEL32!GetLastError` at `0x180143b80`
- `KERNEL32!GetLastError` at `0x180143c32`
- `KERNEL32!GetLastError` at `0x180143c46`
- `KERNEL32!GetLastError` at `0x180143c5c`
- `KERNEL32!GetLastError` at `0x180143d17`
- `KERNEL32!GetLastError` at `0x180143dc9`
- `KERNEL32!GetLastError` at `0x180143ddd`
- `KERNEL32!GetLastError` at `0x180143dfc`
- `KERNEL32!GetLastError` at `0x180143ebb`
- `KERNEL32!GetLastError` at `0x180143ecf`
- `KERNEL32!GetLastError` at `0x180143ef4`
- `KERNEL32!GetLastError` at `0x180143f9e`
- `KERNEL32!GetLastError` at `0x180143fb2`
- `KERNEL32!GetLastError` at `0x180143fd7`
- `KERNEL32!GetLastError` at `0x180144082`
- `KERNEL32!GetLastError` at `0x180144096`
- `KERNEL32!GetLastError` at `0x1801440bb`
- `KERNEL32!GetLastError` at `0x180144160`
- `KERNEL32!GetLastError` at `0x180144218`
- `KERNEL32!GetLastError` at `0x18014422c`
- `KERNEL32!GetLastError` at `0x180144251`
- `KERNEL32!GetLastError` at `0x1801442fc`
- `KERNEL32!GetLastError` at `0x180144310`
- `KERNEL32!GetLastError` at `0x180144335`
- `KERNEL32!GetLastError` at `0x1801443da`
- `KERNEL32!GetLastError` at `0x18014448f`
- `KERNEL32!GetLastError` at `0x1801444a3`
- `KERNEL32!GetLastError` at `0x1801444c8`
- `KERNEL32!GetLastError` at `0x180144572`
- `KERNEL32!GetLastError` at `0x180144589`
- `KERNEL32!GetLastError` at `0x1801445ae`
- `KERNEL32!GetLastError` at `0x180144658`
- `KERNEL32!GetLastError` at `0x180144738`
- `KERNEL32!GetLastError` at `0x180144752`
- `KERNEL32!GetLastError` at `0x180144777`
- `KERNEL32!GetLastError` at `0x180144822`
- `KERNEL32!GetLastError` at `0x1801448fe`
- `KERNEL32!GetLastError` at `0x1801449ac`
- `KERNEL32!GetLastError` at `0x180144a74`
- `KERNEL32!GetLastError` at `0x180144b3e`
- `KERNEL32!GetLastError` at `0x180144b55`
- `KERNEL32!GetLastError` at `0x180144b74`
- `KERNEL32!GetLastError` at `0x180144c26`
- `KERNEL32!GetLastError` at `0x180144c3d`
- `KERNEL32!GetLastError` at `0x180144c5c`
- `KERNEL32!GetLastError` at `0x180144d0e`
- `KERNEL32!GetLastError` at `0x180144d22`
- `KERNEL32!GetLastError` at `0x180144d41`
- `KERNEL32!GetLastError` at `0x180144df8`
- `KERNEL32!GetLastError` at `0x180144e99`
- `KERNEL32!GetLastError` at `0x180144ead`
- `KERNEL32!GetLastError` at `0x180144ec3`
- `KERNEL32!GetLastError` at `0x180144f9f`
- `KERNEL32!GetLastError` at `0x180144fb3`
- `KERNEL32!GetLastError` at `0x180144fc9`
- `KERNEL32!GetLastError` at `0x18014508e`
- `KERNEL32!GetLastError` at `0x1801450a2`
- `KERNEL32!GetLastError` at `0x1801450b8`
- `KERNEL32!GetLastError` at `0x180145192`
- `KERNEL32!GetLastError` at `0x1801451a6`
- `KERNEL32!GetLastError` at `0x1801451bc`
- `KERNEL32!GetLastError` at `0x180145280`
- `KERNEL32!GetLastError` at `0x180145294`
- `KERNEL32!GetLastError` at `0x1801452b9`
- `KERNEL32!GetLastError` at `0x180145360`
- `KERNEL32!GetLastError` at `0x180145402`
- `KERNEL32!GetLastError` at `0x1801454a4`
- `KERNEL32!GetLastError` at `0x18014096f`
- `KERNEL32!GetLastError` at `0x180140a82`
- `KERNEL32!GetLastError` at `0x180140b63`
- `KERNEL32!GetLastError` at `0x180140b7d`
- `KERNEL32!GetLastError` at `0x180140ba1`
- `KERNEL32!GetLastError` at `0x180140f25`
- `KERNEL32!GetLastError` at `0x1801410d6`
- `KERNEL32!GetLastError` at `0x1801413b9`
- `KERNEL32!GetLastError` at `0x180141458`
- `KERNEL32!GetLastError` at `0x1801415c8`
- `KERNEL32!GetLastError` at `0x18014178d`
- `KERNEL32!GetLastError` at `0x1801419c3`
- `KERNEL32!GetLastError` at `0x180141a8e`
- `KERNEL32!GetLastError` at `0x180141d11`
- `KERNEL32!GetLastError` at `0x180141d9d`
- `KERNEL32!GetLastError` at `0x180141e76`
- `KERNEL32!GetLastError` at `0x180142709`
- `KERNEL32!GetLastError` at `0x18014272b`
- `KERNEL32!GetLastError` at `0x180142b36`
- `KERNEL32!GetLastError` at `0x180142b4c`
- `KERNEL32!GetLastError` at `0x180142b69`
- `KERNEL32!GetLastError` at `0x180142f51`
- `KERNEL32!GetLastError` at `0x1801430e7`
- `KERNEL32!GetLastError` at `0x180143194`
- `KERNEL32!GetLastError` at `0x180143238`
- `KERNEL32!GetLastError` at `0x18014324c`
- `KERNEL32!GetLastError` at `0x180143266`
- `KERNEL32!GetLastError` at `0x180143277`
- `KERNEL32!GetLastError` at `0x180143325`
- `KERNEL32!GetLastError` at `0x1801433e6`
- `KERNEL32!GetLastError` at `0x180143493`
- `KERNEL32!GetLastError` at `0x180143540`
- `KERNEL32!GetLastError` at `0x1801435e8`
- `KERNEL32!GetLastError` at `0x180143681`
- `KERNEL32!GetLastError` at `0x180143741`
- `KERNEL32!GetLastError` at `0x1801437ee`
- `KERNEL32!GetLastError` at `0x18014389b`
- `KERNEL32!GetLastError` at `0x18014393f`
- `KERNEL32!GetLastError` at `0x1801439df`
- `KERNEL32!GetLastError` at `0x1801439f6`
- `KERNEL32!GetLastError` at `0x180143a10`
- `KERNEL32!GetLastError` at `0x180143a21`
- `KERNEL32!GetLastError` at `0x180143acb`
- `KERNEL32!GetLastError` at `0x180143b80`
- `KERNEL32!GetLastError` at `0x180143c32`
- `KERNEL32!GetLastError` at `0x180143c46`
- `KERNEL32!GetLastError` at `0x180143c5c`
- `KERNEL32!GetLastError` at `0x180143d17`
- `KERNEL32!GetLastError` at `0x180143dc9`
- `KERNEL32!GetLastError` at `0x180143ddd`
- `KERNEL32!GetLastError` at `0x180143dfc`
- `KERNEL32!GetLastError` at `0x180143ebb`
- `KERNEL32!GetLastError` at `0x180143ecf`
- `KERNEL32!GetLastError` at `0x180143ef4`
- `KERNEL32!GetLastError` at `0x180143f9e`
- `KERNEL32!GetLastError` at `0x180143fb2`
- `KERNEL32!GetLastError` at `0x180143fd7`
- `KERNEL32!GetLastError` at `0x180144082`
- `KERNEL32!GetLastError` at `0x180144096`
- `KERNEL32!GetLastError` at `0x1801440bb`
- `KERNEL32!GetLastError` at `0x180144160`
- `KERNEL32!GetLastError` at `0x180144218`
- `KERNEL32!GetLastError` at `0x18014422c`
- `KERNEL32!GetLastError` at `0x180144251`
- `KERNEL32!GetLastError` at `0x1801442fc`
- `KERNEL32!GetLastError` at `0x180144310`
- `KERNEL32!GetLastError` at `0x180144335`
- `KERNEL32!GetLastError` at `0x1801443da`
- `KERNEL32!GetLastError` at `0x18014448f`
- `KERNEL32!GetLastError` at `0x1801444a3`
- `KERNEL32!GetLastError` at `0x1801444c8`
- `KERNEL32!GetLastError` at `0x180144572`
- `KERNEL32!GetLastError` at `0x180144589`
- `KERNEL32!GetLastError` at `0x1801445ae`
- `KERNEL32!GetLastError` at `0x180144658`
- `KERNEL32!GetLastError` at `0x180144738`
- `KERNEL32!GetLastError` at `0x180144752`
- `KERNEL32!GetLastError` at `0x180144777`
- `KERNEL32!GetLastError` at `0x180144822`
- `KERNEL32!GetLastError` at `0x1801448fe`
- `KERNEL32!GetLastError` at `0x1801449ac`
- `KERNEL32!GetLastError` at `0x180144a74`

## string_xrefs

- `0x180142207`: `Rollback`
- `0x180142172`: `ExternalRollback`
- `0x1801422bd`: `rollbackinfo.ini`
- `0x1801451fb`: `%hs: Failed to write %s to the %s config file. Error: 0x%08X`
- `0x180143c92`: `%hs: Failed to write timeout to file: %s. hr = 0x%08X`
- `0x1801431af`: `%hs: Failed to open system store. Status = 0x%08X`
- `0x18014099e`: `%hs: Command line for the safe OS: %s`
- `0x1801430ff`: `FLOWTRACK: %hs: Will not attempt the SafeOS boot removal, exiting`
- `0x1801432a4`: `%hs: Failed to read Safe OS boot entry GUID from %s. Error = 0x%08X`
- `0x180143957`: `%hs: Missing information for the SafeOS for rollback.`
- `0x180143401`: `%hs: Failed to open BCD bootmgr handle. Status = 0x%08X`
- `0x18014355b`: `%hs: Failed to open new BCD's safe OS entry. Status = 0x%08X`
- `0x180140f40`: `%hs: Failed to set rollback description for the SafeOS, ignoring error. Status = 0x%08X`
- `0x180143a4e`: `%hs: Failed to read New OS boot entry GUID from %s. Error = 0x%08X`
- `0x18014155b`: `BootPathOverride`
- `0x180143f0a`: `BootPathOverride`
- `0x1801440d6`: `%hs: Cannot get volume path for OS partition. Error: 0x%08X`
- `0x18014182b`: `UPGOsPath`
- `0x180144267`: `UPGOsPath`
- `0x180144350`: `%hs: Cannot get volume path for host partition. Error: 0x%08X`
- `0x1801419a5`: `UPGBootVhdVolumePath`
- `0x1801444de`: `UPGBootVhdVolumePath`
- `0x180141acb`: `%hs: VHD path: %s`
- `0x180141a70`: `UPGVhdPath`
- `0x1801445c4`: `UPGVhdPath`
- `0x1801446b2`: `%hs: Cannot get the subfolder for global path %s. Error: 0x%08X`
- `0x180144878`: `%hs: Cannot copy filter from %s to %s. Error: 0x%08X`
- `0x180141f4a`: `System32\Drivers\WinSetupBoot.sys`
- `0x180142016`: `ControlSet%03u\Services\WinSetupBoot`
- `0x1801449e2`: `%hs: Cannot create filter key %s. Error: 0x%08X`
- `0x180144ba1`: `%hs: Failed to write rollback boot entry GUID to %s. Error: 0x%08X`
- `0x180144c89`: `%hs: Failed to write external rollback marker to %s. Error: 0x%08X`
- `0x180142246`: `RollbackExternal`
- `0x180144e13`: `%hs: Failed to get NewOS root directory. Error: 0x%08X`
- `0x180144d6e`: `%hs: Failed to write new OS boot entry GUID to %s. Error: 0x%08X`
- `0x180142761`: `%hs: Failed to read the migration scope from %s. hr = 0x%08X`
- `0x180144f18`: `%hs: Failed to write WinOld path %s to the %s config file. Error: 0x%08X`
- `0x180142bbf`: `%hs: Failed to write new path %s to the %s config file. Error: 0x%08X`
- `0x180142b22`: `Quarantine.NewPaths`
- `0x180145009`: `%hs: Failed to write WinOld mapping source %s to the %s config file. Error: 0x%08X`
- `0x18014510d`: `%hs: ocateOS: Failed to write WinOld mapping destination %s to the %s config file. Error: 0x%08X`
- `0x180142f62`: `Attempting to set the OS switch checkpoint`
- `0x180142f28`: `KernelRename`
- `0x1801451ed`: `KernelRename`
- `0x1801452d4`: `%hs: Error setting OS Switch Rollback checkpoint. Error: 0x%08X`
- `0x18014537b`: `%hs: Failed to open BCD's new OS entry. Status = 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=82 #try_helpers=2
__int64 __fastcall CPrepareSafeOSBootRemoval::DoExecute(
        CPrepareSafeOSBootRemoval *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  __int64 v6; // rdi
  struct IRollback *v7; // rax
  struct IRollback *v8; // rbx
  struct UnBCL::String *v9; // rax
  int v10; // r8d
  UnBCL::String *v11; // rax
  const struct UnBCL::String *v12; // rbx
  const struct UnBCL::String *v13; // rax
  struct UnBCL::String *v14; // rax
  int v15; // esi
  const struct UnBCL::String *P; // rbx
  const struct UnBCL::String *v17; // rax
  struct UnBCL::String *v18; // rax
  __int64 v19; // rdi
  UnBCL::String *v20; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v22; // rax
  UnBCL::String *v23; // rax
  UnBCL::String *v24; // rax
  UnBCL::String *v25; // rax
  struct UnBCL::String *v26; // rax
  DWORD v27; // edi
  __int64 v28; // rsi
  UnBCL::String *v29; // rax
  const char *v30; // rbx
  UnBCL::String *v31; // rax
  const char *v32; // rax
  struct tagLOG_PARTIAL_MSG *v33; // rax
  UnBCL::String *v34; // rax
  const unsigned __int16 *v35; // rbx
  UnBCL::String *v36; // rax
  const unsigned __int16 *v37; // rax
  signed int v38; // eax
  bool v39; // sf
  signed int v40; // eax
  unsigned int v41; // ebx
  unsigned int v42; // esi
  DWORD v43; // edi
  __int64 v44; // r14
  UnBCL::String *v45; // rax
  const char *v46; // rax
  struct tagLOG_PARTIAL_MSG *v47; // rax
  UnBCL::String *v48; // rax
  const WCHAR *v49; // rbx
  UnBCL::String *v50; // rax
  const WCHAR *v51; // rax
  struct UnBCL::String *v52; // rax
  UnBCL::String *v53; // rax
  const unsigned __int16 *v54; // rax
  int v55; // ebx
  int v56; // r14d
  int v57; // r14d
  int v58; // r14d
  UnBCL::String *v59; // rax
  const WCHAR *v60; // rax
  struct UnBCL::String *v61; // rax
  UnBCL::String *v62; // rax
  const unsigned __int16 *v63; // rax
  int v64; // ebx
  int v65; // r14d
  int v66; // r14d
  int v67; // r14d
  char *v68; // rbx
  UnBCL::String *v69; // rax
  unsigned int v70; // edi
  UnBCL::String *v71; // rax
  const unsigned __int16 *v72; // rax
  int v73; // r14d
  DWORD v74; // edi
  __int64 v75; // rbx
  struct tagLOG_PARTIAL_MSG *v76; // rax
  UnBCL::String *v77; // rax
  const WCHAR *v78; // rbx
  UnBCL::String *v79; // rax
  const WCHAR *v80; // rax
  struct UnBCL::String *v81; // rax
  UnBCL::String *v82; // rax
  const unsigned __int16 *v83; // rax
  int v84; // ebx
  DWORD v85; // eax
  bool v86; // zf
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  int v90; // r14d
  struct UnBCL::String *v91; // rax
  int v92; // r8d
  int v93; // ebx
  unsigned int Timeout; // r14d
  struct UnBCL::String *v95; // rax
  UnBCL::String *v96; // rax
  const unsigned __int16 *v97; // rbx
  UnBCL::String *v98; // rax
  const unsigned __int16 *v99; // rax
  __int64 v100; // rbx
  struct tagLOG_PARTIAL_MSG *v101; // rax
  unsigned int v102; // r14d
  __int64 v103; // rdi
  CBool *v104; // rax
  CBool *v105; // rdx
  char *v106; // rbx
  __int64 v107; // rax
  DWORD v108; // edi
  __int64 v109; // rbx
  struct tagLOG_PARTIAL_MSG *v110; // rax
  unsigned int v111; // r14d
  DWORD v112; // edi
  __int64 v113; // rbx
  struct tagLOG_PARTIAL_MSG *v114; // rax
  UnBCL::String *v115; // rax
  const unsigned __int16 *v116; // rax
  HKEY v117; // r12
  const struct UnBCL::String *v118; // rax
  struct UnBCL::String *PathRoot; // rax
  DWORD v120; // ebx
  __int64 v121; // rdi
  UnBCL::String *v122; // rax
  const char *v123; // rax
  struct tagLOG_PARTIAL_MSG *v124; // rax
  struct UnBCL::String *v125; // rax
  struct UnBCL::String *v126; // rax
  UnBCL::String *v127; // rax
  UnBCL::String *v128; // rdi
  struct UnBCL::String *v129; // rbx
  struct UnBCL::String *v130; // rax
  struct UnBCL::String *v131; // rax
  UnBCL::String *v132; // rax
  DWORD v133; // ebx
  __int64 v134; // rdi
  UnBCL::String *v135; // rax
  const char *v136; // rax
  struct tagLOG_PARTIAL_MSG *v137; // rax
  UnBCL::String *v138; // rax
  const unsigned __int16 *v139; // rax
  unsigned int v140; // edi
  __int64 v141; // rcx
  struct UnBCL::String *v142; // rax
  struct UnBCL::String *v143; // rax
  UnBCL::String *v144; // rax
  UnBCL::String *v145; // rdi
  struct UnBCL::String *v146; // rbx
  struct UnBCL::String *v147; // rax
  struct UnBCL::String *v148; // rax
  UnBCL::String *v149; // rax
  UnBCL::String *v150; // rax
  const unsigned __int16 *v151; // rax
  DWORD v152; // ebx
  __int64 v153; // rdi
  UnBCL::String *v154; // rax
  const char *v155; // rax
  struct tagLOG_PARTIAL_MSG *v156; // rax
  UnBCL::String *v157; // rax
  const unsigned __int16 *v158; // rax
  DWORD v159; // ebx
  __int64 v160; // rdi
  UnBCL::String *v161; // rax
  const char *v162; // rax
  struct tagLOG_PARTIAL_MSG *v163; // rax
  UnBCL::String *v164; // rax
  const WCHAR *v165; // rax
  __int64 v166; // rax
  UnBCL::MultiSz *v167; // rax
  UnBCL::MultiSz *v168; // rbx
  int (__fastcall ***v169)(_QWORD); // rcx
  __int64 v170; // rcx
  __int64 v171; // rcx
  _QWORD *v172; // rax
  struct UnBCL::String *v173; // rax
  __int64 (__fastcall ***v174)(_QWORD); // rcx
  __int64 v175; // rax
  DWORD v176; // edi
  __int64 v177; // rbx
  struct tagLOG_PARTIAL_MSG *v178; // rax
  DWORD v179; // ebx
  __int64 v180; // rdi
  const char *v181; // rax
  const unsigned __int16 *Buffer; // rax
  DWORD v183; // edi
  __int64 v184; // rbx
  struct tagLOG_PARTIAL_MSG *v185; // rax
  const struct UnBCL::String *v186; // rbx
  const struct UnBCL::String *v187; // rax
  struct UnBCL::String *v188; // rax
  const struct UnBCL::String *v189; // rbx
  const struct UnBCL::String *v190; // rax
  struct UnBCL::String *v191; // rax
  struct UnBCL::String *v192; // rbx
  struct UnBCL::String *v193; // rax
  DWORD v194; // edi
  __int64 v195; // rbx
  struct tagLOG_PARTIAL_MSG *v196; // rax
  DWORD LastError; // edi
  __int64 v199; // rbx
  struct tagLOG_PARTIAL_MSG *v200; // rax
  signed int v201; // eax
  bool v202; // sf
  DWORD v203; // ebx
  __int64 v204; // rdi
  DWORD v205; // esi
  UnBCL::String *v206; // rax
  const char *v207; // rax
  struct tagLOG_PARTIAL_MSG *v208; // rax
  DWORD v209; // edi
  __int64 v210; // rsi
  UnBCL::String *v211; // rax
  const char *v212; // rax
  struct tagLOG_PARTIAL_MSG *v213; // rax
  DWORD v214; // edi
  __int64 v215; // rbx
  struct tagLOG_PARTIAL_MSG *v216; // rax
  DWORD v217; // edi
  __int64 v218; // rbx
  struct tagLOG_PARTIAL_MSG *v219; // rax
  DWORD v220; // edi
  __int64 v221; // rbx
  struct tagLOG_PARTIAL_MSG *v222; // rax
  DWORD v223; // edi
  __int64 v224; // rbx
  struct tagLOG_PARTIAL_MSG *v225; // rax
  DWORD v226; // edi
  __int64 v227; // rsi
  UnBCL::String *v228; // rax
  const char *v229; // rax
  struct tagLOG_PARTIAL_MSG *v230; // rax
  DWORD v231; // edi
  __int64 v232; // rbx
  struct tagLOG_PARTIAL_MSG *v233; // rax
  DWORD v234; // edi
  __int64 v235; // rbx
  struct tagLOG_PARTIAL_MSG *v236; // rax
  DWORD v237; // edi
  __int64 v238; // rbx
  struct tagLOG_PARTIAL_MSG *v239; // rax
  DWORD v240; // edi
  __int64 v241; // rbx
  struct tagLOG_PARTIAL_MSG *v242; // rax
  signed int v243; // eax
  bool v244; // sf
  DWORD v245; // ebx
  __int64 v246; // rdi
  DWORD v247; // esi
  UnBCL::String *v248; // rax
  const char *v249; // rax
  struct tagLOG_PARTIAL_MSG *v250; // rax
  DWORD v251; // edi
  __int64 v252; // rsi
  UnBCL::String *v253; // rax
  const char *v254; // rax
  struct tagLOG_PARTIAL_MSG *v255; // rax
  DWORD v256; // edi
  __int64 v257; // rbx
  struct tagLOG_PARTIAL_MSG *v258; // rax
  signed int v259; // eax
  bool v260; // sf
  signed int v261; // eax
  DWORD v262; // ebx
  __int64 v263; // rdi
  UnBCL::String *v264; // rax
  const char *v265; // rax
  struct tagLOG_PARTIAL_MSG *v266; // rax
  DWORD v267; // edi
  __int64 v268; // rbx
  struct tagLOG_PARTIAL_MSG *v269; // rax
  signed int v270; // eax
  bool v271; // sf
  signed int v272; // eax
  signed int v273; // ebx
  DWORD v274; // edi
  __int64 v275; // rsi
  UnBCL::String *v276; // rax
  const char *v277; // rax
  struct tagLOG_PARTIAL_MSG *v278; // rax
  signed int v279; // eax
  bool v280; // sf
  signed int v281; // eax
  signed int v282; // r14d
  DWORD v283; // edi
  __int64 v284; // rbx
  struct tagLOG_PARTIAL_MSG *v285; // rax
  signed int v286; // eax
  bool v287; // sf
  signed int v288; // eax
  signed int v289; // r14d
  DWORD v290; // edi
  __int64 v291; // rbx
  struct tagLOG_PARTIAL_MSG *v292; // rax
  signed int v293; // eax
  bool v294; // sf
  signed int v295; // eax
  signed int v296; // r14d
  DWORD v297; // edi
  __int64 v298; // rbx
  struct tagLOG_PARTIAL_MSG *v299; // rax
  DWORD v300; // ebx
  __int64 v301; // rdi
  UnBCL::String *v302; // rax
  const char *v303; // rax
  struct tagLOG_PARTIAL_MSG *v304; // rax
  signed int v305; // eax
  bool v306; // sf
  signed int v307; // eax
  signed int v308; // r14d
  DWORD v309; // edi
  __int64 v310; // rbx
  struct tagLOG_PARTIAL_MSG *v311; // rax
  signed int v312; // eax
  bool v313; // sf
  signed int v314; // eax
  signed int v315; // r14d
  DWORD v316; // edi
  __int64 v317; // rbx
  struct tagLOG_PARTIAL_MSG *v318; // rax
  DWORD v319; // ebx
  __int64 v320; // rdi
  UnBCL::String *v321; // rax
  const char *v322; // rax
  struct tagLOG_PARTIAL_MSG *v323; // rax
  signed int v324; // eax
  bool v325; // sf
  signed int v326; // eax
  signed int v327; // r14d
  DWORD v328; // edi
  __int64 v329; // rbx
  struct tagLOG_PARTIAL_MSG *v330; // rax
  signed int v331; // eax
  bool v332; // sf
  signed int v333; // eax
  signed int v334; // r14d
  DWORD v335; // edi
  __int64 v336; // rbx
  struct tagLOG_PARTIAL_MSG *v337; // rax
  signed int v338; // eax
  bool v339; // sf
  signed int v340; // eax
  signed int v341; // r14d
  DWORD v342; // edi
  __int64 v343; // rbx
  struct tagLOG_PARTIAL_MSG *v344; // rax
  int dwOptions; // [rsp+20h] [rbp-518h]
  PHKEY phkResult; // [rsp+38h] [rbp-500h]
  DWORD lpdwDisposition; // [rsp+40h] [rbp-4F8h]
  unsigned int v348; // [rsp+68h] [rbp-4D0h] BYREF
  void **v349; // [rsp+70h] [rbp-4C8h] BYREF
  UnBCL::MultiSz *v350; // [rsp+78h] [rbp-4C0h]
  CPrepareSafeOSBootRemoval *v351; // [rsp+80h] [rbp-4B8h]
  __int64 v352; // [rsp+88h] [rbp-4B0h] BYREF
  _OWORD v353[2]; // [rsp+90h] [rbp-4A8h] BYREF
  _BYTE v354[16]; // [rsp+B0h] [rbp-488h] BYREF
  struct UnBCL::String *v355; // [rsp+C0h] [rbp-478h] BYREF
  struct UnBCL::String *v356; // [rsp+C8h] [rbp-470h]
  __int64 v357; // [rsp+D0h] [rbp-468h] BYREF
  int v358; // [rsp+D8h] [rbp-460h]
  void **v359; // [rsp+E0h] [rbp-458h] BYREF
  __int64 v360; // [rsp+E8h] [rbp-450h]
  _QWORD v361[7]; // [rsp+F0h] [rbp-448h] BYREF
  __int64 v362; // [rsp+128h] [rbp-410h] BYREF
  __int64 v363; // [rsp+130h] [rbp-408h]
  _BYTE v364[16]; // [rsp+140h] [rbp-3F8h] BYREF
  __int64 v365; // [rsp+158h] [rbp-3E0h]
  __int64 v366; // [rsp+160h] [rbp-3D8h] BYREF
  struct IExecutionContext *v367; // [rsp+168h] [rbp-3D0h]
  __int64 v368; // [rsp+178h] [rbp-3C0h] BYREF
  __int64 v369; // [rsp+180h] [rbp-3B8h]
  int v370; // [rsp+188h] [rbp-3B0h]
  _BYTE v371[16]; // [rsp+190h] [rbp-3A8h] BYREF
  _BYTE v372[16]; // [rsp+1A0h] [rbp-398h] BYREF
  _BYTE v373[32]; // [rsp+1B0h] [rbp-388h] BYREF
  struct IRollback *v374; // [rsp+1D0h] [rbp-368h]
  HKEY v375; // [rsp+1D8h] [rbp-360h]
  _BYTE v376[16]; // [rsp+210h] [rbp-328h] BYREF
  _BYTE v377[16]; // [rsp+220h] [rbp-318h] BYREF
  _BYTE v378[16]; // [rsp+230h] [rbp-308h] BYREF
  char v379[8]; // [rsp+270h] [rbp-2C8h] BYREF
  _QWORD *v380; // [rsp+288h] [rbp-2B0h] BYREF
  _QWORD *pExceptionObject; // [rsp+290h] [rbp-2A8h] BYREF
  _QWORD *v382; // [rsp+298h] [rbp-2A0h] BYREF
  _QWORD *v383; // [rsp+2A0h] [rbp-298h] BYREF
  _QWORD *v384; // [rsp+2A8h] [rbp-290h] BYREF
  _QWORD *v385; // [rsp+2B0h] [rbp-288h] BYREF
  _QWORD *v386; // [rsp+2B8h] [rbp-280h] BYREF
  _QWORD *v387; // [rsp+2C0h] [rbp-278h] BYREF
  _QWORD *v388; // [rsp+2C8h] [rbp-270h] BYREF
  _QWORD *v389; // [rsp+2D0h] [rbp-268h] BYREF
  _QWORD *v390; // [rsp+2D8h] [rbp-260h] BYREF
  _QWORD *v391; // [rsp+2E0h] [rbp-258h] BYREF
  _QWORD *v392; // [rsp+2E8h] [rbp-250h] BYREF
  _QWORD *v393; // [rsp+2F0h] [rbp-248h] BYREF
  _QWORD *v394; // [rsp+360h] [rbp-1D8h] BYREF
  _QWORD *v395; // [rsp+368h] [rbp-1D0h] BYREF
  _QWORD *v396; // [rsp+370h] [rbp-1C8h] BYREF
  _QWORD *v397; // [rsp+378h] [rbp-1C0h] BYREF
  _QWORD *v398; // [rsp+380h] [rbp-1B8h] BYREF
  _QWORD *v399; // [rsp+388h] [rbp-1B0h] BYREF
  _QWORD *v400; // [rsp+390h] [rbp-1A8h] BYREF
  _QWORD *v401; // [rsp+398h] [rbp-1A0h] BYREF
  _QWORD *v402; // [rsp+3A0h] [rbp-198h] BYREF
  _QWORD *v403; // [rsp+3A8h] [rbp-190h] BYREF
  _QWORD *v404; // [rsp+3B0h] [rbp-188h] BYREF
  _QWORD *v405; // [rsp+3B8h] [rbp-180h] BYREF
  _QWORD *v406; // [rsp+3F8h] [rbp-140h] BYREF
  _QWORD v407[7]; // [rsp+400h] [rbp-138h] BYREF
  struct _GUID v408; // [rsp+438h] [rbp-100h] BYREF
  struct _GUID v409; // [rsp+450h] [rbp-E8h] BYREF
  struct _GUID v410; // [rsp+470h] [rbp-C8h] BYREF
  char v411[48]; // [rsp+480h] [rbp-B8h] BYREF
  _BYTE v412[64]; // [rsp+4B0h] [rbp-88h] BYREF
  char v413[16]; // [rsp+4F0h] [rbp-48h] BYREF
  __int16 v414; // [rsp+500h] [rbp-38h]
  int v415; // [rsp+502h] [rbp-36h]
  wchar_t v416; // [rsp+506h] [rbp-32h]

  v407[6] = -2;
  v367 = a2;
  v351 = this;
  v358 = 0;
  v362 = 0;
  v366 = 0;
  v365 = 0;
  v357 = 0;
  LODWORD(v355) = 0;
  v6 = 0;
  v363 = 0;
  v7 = (struct IRollback *)(*(__int64 (__fastcall **)(struct IExecutionContext *, struct IExecutionContext *, void *, struct IInternalOperationsProgress *))(*(_QWORD *)a2 + 72LL))(
                             a2,
                             a2,
                             a3,
                             a4);
  v8 = v7;
  v374 = v7;
  if ( v7
    && !(*(unsigned int (__fastcall **)(struct IRollback *))(*(_QWORD *)v7 + 40LL))(v7)
    && (*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v8 + 48LL))(v8) )
  {
    v6 = (*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v8 + 48LL))(v8);
    v363 = v6;
    v356 = 0;
  }
  else
  {
    v356 = 0;
    if ( !v8 )
      goto LABEL_9;
  }
  if ( !(*(unsigned int (__fastcall **)(struct IRollback *))(*(_QWORD *)v8 + 40LL))(v8)
    && (*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v8 + 56LL))(v8) )
  {
    v356 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v8 + 56LL))(v8);
  }
LABEL_9:
  if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2) >= 4 )
  {
    v375 = 0;
    v9 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v379, L"FreezeProfilesFolder");
    v370 = SPGetStoredBOOL(a2, v9, v10);
    UnBCL::String::~String((UnBCL::String *)v379);
    v414 = 63;
    v415 = *(_DWORD *)L":\\";
    v416 = asc_180557F68[3];
    v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 208);
    v414 = *UnBCL::String::get_CString(v11);
    v12 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v379, L"SetupPlatform.ini");
    v13 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
    v14 = UnBCL::Path::Combine(v13, v12);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v354, v14);
    UnBCL::String::~String((UnBCL::String *)v379);
    UnBCL::Exception::Exception((UnBCL::Exception *)v361);
    v361[0] = &`CPrepareSafeOSBootRemoval::DoExecute'::`12'::CXXXXXHandledException::`vftable';
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v371, 0);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v372, 0);
    v410 = 0;
    if ( !*((_DWORD *)this + 84) )
    {
      v15 = BcdOpenSystemStore(&v362);
      if ( v15 < 0 )
      {
        LastError = GetLastError();
        v199 = CurrentIP();
        v200 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: Failed to open system store. Status = 0x%08X",
                 "CPrepareSafeOSBootRemoval::DoExecute",
                 v15);
        WdsSetupLogMessageW(
          v200,
          819200,
          L"D",
          0,
          5532,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v199,
          LastError,
          0,
          0);
        pExceptionObject = v361;
        throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&pExceptionObject;
      }
      if ( v6 )
      {
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 224)
          || !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 240)
          || !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 272) )
        {
          v240 = GetLastError();
          v241 = CurrentIP();
          v242 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Missing information for the SafeOS for rollback.",
                   "CPrepareSafeOSBootRemoval::DoExecute");
          WdsSetupLogMessageW(
            v242,
            819200,
            L"D",
            0,
            5546,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v241,
            v240,
            0,
            0);
          v392 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v392;
        }
        P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 240);
        v17 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
        v18 = UnBCL::Path::Combine(v17, P);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v349, v18);
        LODWORD(P) = GetLastError();
        v19 = CurrentIP();
        v20 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
        CString = (const char *)UnBCL::String::get_CString(v20);
        v22 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Command line for the safe OS: %s",
                "CPrepareSafeOSBootRemoval::DoExecute",
                CString);
        WdsSetupLogMessageW(
          v22,
          819200,
          L"D",
          0,
          5560,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v19,
          (_DWORD)P,
          0,
          0);
        v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
        if ( *UnBCL::String::get_CString(v23) )
        {
          v24 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
          if ( UnBCL::String::get_CString(v24)[1] == 58 )
          {
            v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
            v26 = UnBCL::String::Remove(v25, 0, 2);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v353, v26);
            UnBCL::SmartPtr<UnBCL::String>::operator=(&v349, v353);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v353);
          }
        }
        v27 = GetLastError();
        v28 = CurrentIP();
        v29 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 224);
        v30 = (const char *)UnBCL::String::get_CString(v29);
        v31 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
        v32 = (const char *)UnBCL::String::get_CString(v31);
        v33 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Setting boot app %s for WinRe %s",
                "CPrepareSafeOSBootRemoval::DoExecute",
                v32,
                v30);
        WdsSetupLogMessageW(
          v33,
          819200,
          L"D",
          0,
          5569,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v28,
          v27,
          0,
          0);
        v34 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
        v35 = UnBCL::String::get_CString(v34);
        v36 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 224);
        v37 = UnBCL::String::get_CString(v36);
        if ( (unsigned int)WinReSetBootApp(v37, v35) )
        {
          v42 = -2147467259;
        }
        else
        {
          v38 = GetLastError();
          v39 = v38 < 0;
          if ( v38 > 0 )
            v39 = 1;
          if ( v39 )
          {
            v40 = GetLastError();
            v41 = v40;
            if ( v40 > 0 )
              v41 = (unsigned __int16)v40 | 0x80070000;
            v42 = -2147467259;
          }
          else
          {
            v42 = -2147467259;
            v41 = -2147467259;
          }
          v43 = GetLastError();
          v44 = CurrentIP();
          v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
          v46 = (const char *)UnBCL::String::get_CString(v45);
          v47 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: Failed to set the boot app %s. hr = 0x%08X",
                  "CPrepareSafeOSBootRemoval::DoExecute",
                  v46,
                  v41);
          WdsSetupLogMessageW(
            v47,
            819200,
            L"D",
            0,
            5574,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v44,
            v43,
            0,
            0);
        }
        v48 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
        v49 = UnBCL::String::get_CString(v48);
        v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 272);
        v51 = UnBCL::String::get_CString(v50);
        v52 = SPReadConfigValue(L"BootEntries", v51, v49);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v353, v52);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v371, v353);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v353);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v371) )
        {
          v201 = GetLastError();
          v202 = v201 < 0;
          if ( v201 > 0 )
            v202 = 1;
          if ( v202 )
            GetLastError();
          v203 = GetLastError();
          v204 = CurrentIP();
          v205 = GetLastError();
          v206 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
          v207 = (const char *)UnBCL::String::get_CString(v206);
          v208 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to read Safe OS boot entry GUID from %s. Error = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v207,
                   v205);
          WdsSetupLogMessageW(
            v208,
            819200,
            L"D",
            0,
            5590,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v204,
            v203,
            0,
            0);
          v382 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v382;
        }
        v408 = 0;
        v53 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v371);
        v54 = UnBCL::String::get_CString(v53);
        v55 = SPGuidFromString(v54, &v408);
        if ( v55 < 0 )
        {
          v209 = GetLastError();
          v210 = CurrentIP();
          v211 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v371);
          v212 = (const char *)UnBCL::String::get_CString(v211);
          v213 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: SPGuidFromString failed for %s. hr = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v212,
                   v55);
          WdsSetupLogMessageW(
            v213,
            819200,
            L"D",
            0,
            5598,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v210,
            v209,
            0,
            0);
          v383 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v383;
        }
        v56 = BcdOpenObject(v362, &GUID_WINDOWS_BOOTMGR, &v366);
        if ( v56 < 0 )
        {
          v214 = GetLastError();
          v215 = CurrentIP();
          v216 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to open BCD bootmgr handle. Status = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v56);
          WdsSetupLogMessageW(
            v216,
            819200,
            L"D",
            0,
            5609,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v215,
            v214,
            0,
            0);
          v384 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v384;
        }
        v57 = BcdSetElementData(v366, 587202563, &v408, 16);
        if ( v57 < 0 )
        {
          v217 = GetLastError();
          v218 = CurrentIP();
          v219 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to set Safe OS as default entry in the BCD. Status = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v57);
          WdsSetupLogMessageW(
            v219,
            819200,
            L"D",
            0,
            5621,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v218,
            v217,
            0,
            0);
          v385 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v385;
        }
        v58 = BcdOpenObject(v362, &v408, &v357);
        if ( v58 < 0 )
        {
          v220 = GetLastError();
          v221 = CurrentIP();
          v222 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to open new BCD's safe OS entry. Status = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v58);
          WdsSetupLogMessageW(
            v222,
            819200,
            L"D",
            0,
            5642,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v221,
            v220,
            0,
            0);
          v386 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v386;
        }
        v409 = 0;
        v59 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
        v60 = UnBCL::String::get_CString(v59);
        v61 = SPReadConfigValue(L"BootEntries", L"OldOS", v60);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v359, v61);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v359) )
        {
          v223 = GetLastError();
          v224 = CurrentIP();
          v225 = ConstructPartialMsgW(
                   0x2000000u,
                   "CPrepareSafeOSBootRemoval::DoExecute: Could not get old OS boot entry from param file.");
          WdsSetupLogMessageW(
            v225,
            819200,
            L"D",
            0,
            5654,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v224,
            v223,
            0,
            0);
          v380 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v380;
        }
        v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v359);
        v63 = UnBCL::String::get_CString(v62);
        v64 = SPGuidFromString(v63, &v409);
        if ( v64 < 0 )
        {
          v226 = GetLastError();
          v227 = CurrentIP();
          v228 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v359);
          v229 = (const char *)UnBCL::String::get_CString(v228);
          v230 = ConstructPartialMsgW(0x2000000u, "SPGuidFromString failed for %s. hr = 0x%X", v229, v64);
          WdsSetupLogMessageW(
            v230,
            819200,
            L"D",
            0,
            5661,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v227,
            v226,
            0,
            0);
          v388 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v388;
        }
        v65 = BcdSetElementData(v357, 335544328, &v409, 16);
        if ( v65 < 0 )
        {
          v231 = GetLastError();
          v232 = CurrentIP();
          v233 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to set the old OS as recovery sequence for SafeOS. Status = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v65);
          WdsSetupLogMessageW(
            v233,
            819200,
            L"D",
            0,
            5675,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v232,
            v231,
            0,
            0);
          v389 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v389;
        }
        LOWORD(v348) = 0;
        v66 = BcdSetElementData(v357, 369098835, &v348, 2);
        if ( v66 < 0 )
        {
          v234 = GetLastError();
          v235 = CurrentIP();
          v236 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to disable restartonfailure for SafeOS. Status = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v66);
          WdsSetupLogMessageW(
            v236,
            819200,
            L"D",
            0,
            5691,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v235,
            v234,
            0,
            0);
          v390 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v390;
        }
        v352 = 8;
        v67 = BcdSetElementData(v357, 620757216, &v352, 8);
        if ( v67 < 0 )
        {
          v237 = GetLastError();
          v238 = CurrentIP();
          v239 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Failed to disable restartonfailure for SafeOS. Status = 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v67);
          WdsSetupLogMessageW(
            v239,
            819200,
            L"D",
            0,
            5708,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v238,
            v237,
            0,
            0);
          v391 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v391;
        }
        v68 = (char *)v351 + 304;
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v351 + 304) )
        {
          v69 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v68);
          v70 = 2 * UnBCL::String::get_Length(v69) + 2;
          v71 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v68);
          v72 = UnBCL::String::get_CString(v71);
          v73 = BcdSetElementData(v357, 301989892, v72, v70);
          if ( v73 < 0 )
          {
            v74 = GetLastError();
            v75 = CurrentIP();
            v76 = ConstructPartialMsgW(
                    0x3000000u,
                    "%hs: Failed to set rollback description for the SafeOS, ignoring error. Status = 0x%08X",
                    "CPrepareSafeOSBootRemoval::DoExecute",
                    v73);
            WdsSetupLogMessageW(
              v76,
              819200,
              L"D",
              0,
              5722,
              L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
              L"CPrepareSafeOSBootRemoval::DoExecute",
              v75,
              v74,
              0,
              0);
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v359);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v349);
        v6 = v363;
      }
      else
      {
        v42 = -2147467259;
      }
      v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
      v78 = UnBCL::String::get_CString(v77);
      v79 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v351 + 256);
      v80 = UnBCL::String::get_CString(v79);
      v81 = SPReadConfigValue(L"BootEntries", v80, v78);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v353, v81);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v372, v353);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v353);
      if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v372) )
      {
        v243 = GetLastError();
        v244 = v243 < 0;
        if ( v243 > 0 )
          v244 = 1;
        if ( v244 )
          GetLastError();
        v245 = GetLastError();
        v246 = CurrentIP();
        v247 = GetLastError();
        v248 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
        v249 = (const char *)UnBCL::String::get_CString(v248);
        v250 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: Failed to read New OS boot entry GUID from %s. Error = 0x%08X",
                 "CPrepareSafeOSBootRemoval::DoExecute",
                 v249,
                 v247);
        WdsSetupLogMessageW(
          v250,
          819200,
          L"D",
          0,
          5737,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v246,
          v245,
          0,
          0);
        v393 = v361;
        throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v393;
      }
      v82 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v372);
      v83 = UnBCL::String::get_CString(v82);
      v84 = SPGuidFromString(v83, &v410);
      if ( v84 < 0 )
      {
        v251 = GetLastError();
        v252 = CurrentIP();
        v253 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v372);
        v254 = (const char *)UnBCL::String::get_CString(v253);
        v255 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: SPGuidFromString failed for %s. hr = 0x%08X",
                 "CPrepareSafeOSBootRemoval::DoExecute",
                 v254,
                 v84);
        WdsSetupLogMessageW(
          v255,
          819200,
          L"D",
          0,
          5743,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v252,
          v251,
          0,
          0);
        v387 = v361;
        throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v387;
      }
      OSRollbackUtils::CBCDManipulator::CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v373);
      OSRollbackUtils::CBCDManipulator::Open((OSRollbackUtils::CBCDManipulator *)v373, 0);
      v85 = GetLastError();
      v86 = v6 == 0;
      v87 = v85;
      if ( v86 )
      {
        v100 = CurrentIP();
        v101 = ConstructPartialMsgW(
                 0x4000000u,
                 "%hs: The new boot entry will be set as default boot entry",
                 "CPrepareSafeOSBootRemoval::DoExecute");
        WdsSetupLogMessageW(
          v101,
          819200,
          L"D",
          0,
          5769,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v100,
          v87,
          0,
          0);
        v102 = OSRollbackUtils::CBCDManipulator::SetDefaultBootEntry((OSRollbackUtils::CBCDManipulator *)v373, &v410);
        if ( v102 )
        {
          v267 = GetLastError();
          v268 = CurrentIP();
          v269 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: BCD failed to set the default boot entry. Error: 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v102);
          WdsSetupLogMessageW(
            v269,
            819200,
            L"D",
            0,
            5773,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v268,
            v267,
            0,
            0);
          v406 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v406;
        }
      }
      else
      {
        v88 = CurrentIP();
        v89 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: The new boot entry will be set as a one-time boot sequence",
                "CPrepareSafeOSBootRemoval::DoExecute");
        WdsSetupLogMessageW(
          v89,
          819200,
          L"D",
          0,
          5755,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v88,
          v87,
          0,
          0);
        UnBCL::ArrayList<_GUID>::ArrayList<_GUID>(v411);
        v353[0] = v410;
        UnBCL::ArrayList<DISK_SPACE_IMPACT>::Add(v413, v353);
        v90 = OSRollbackUtils::CBCDManipulator::SetIdentityList((OSRollbackUtils::CBCDManipulator *)v373);
        if ( v90 )
        {
          v256 = GetLastError();
          v257 = CurrentIP();
          v258 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: BCD failed to set boot sequence list. Error: 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v90);
          WdsSetupLogMessageW(
            v258,
            819200,
            L"D",
            0,
            5762,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v257,
            v256,
            0,
            0);
          v407[0] = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)v407;
        }
        UnBCL::ArrayList<_GUID>::~ArrayList<_GUID>(v412);
        UnBCL::Object::~Object((UnBCL::Object *)v412);
      }
      v91 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v353, L"BootManagerTimeoutSaved");
      v93 = SPGetStoredBOOL(a2, v91, v92);
      UnBCL::String::~String((UnBCL::String *)v353);
      if ( !v93 )
      {
        v348 = 0;
        Timeout = OSRollbackUtils::CBCDManipulator::GetTimeout((OSRollbackUtils::CBCDManipulator *)v373, &v348);
        if ( Timeout )
        {
          v108 = GetLastError();
          v109 = CurrentIP();
          v110 = ConstructPartialMsgW(
                   0x3000000u,
                   "%hs: BCD failed to get the boot manager timeout. Error: 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   Timeout);
          WdsSetupLogMessageW(
            v110,
            819200,
            L"D",
            0,
            5805,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v109,
            v108,
            0,
            0);
        }
        else
        {
          v95 = UnBCL::String::Format(L"%d", v348);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v353, v95);
          v96 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
          v97 = UnBCL::String::get_CString(v96);
          v98 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v353);
          v99 = UnBCL::String::get_CString(v98);
          if ( !SPWriteConfigValue(L"BootManager", L"Timeout", v99, v97) )
          {
            v259 = GetLastError();
            v260 = v259 < 0;
            if ( v259 > 0 )
              v260 = 1;
            if ( v260 )
            {
              v261 = GetLastError();
              v42 = v261;
              if ( v261 > 0 )
                v42 = (unsigned __int16)v261 | 0x80070000;
            }
            v262 = GetLastError();
            v263 = CurrentIP();
            v264 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
            v265 = (const char *)UnBCL::String::get_CString(v264);
            v266 = ConstructPartialMsgW(
                     0x2000000u,
                     "%hs: Failed to write timeout to file: %s. hr = 0x%08X",
                     "CPrepareSafeOSBootRemoval::DoExecute",
                     v265,
                     v42);
            WdsSetupLogMessageW(
              v266,
              819200,
              L"D",
              0,
              5795,
              L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
              L"CPrepareSafeOSBootRemoval::DoExecute",
              v263,
              v262,
              0,
              0);
            v405 = v361;
            throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v405;
          }
          v103 = *(_QWORD *)a2;
          v104 = (CBool *)UnBCL::Object::operator new(0x40u);
          v352 = (__int64)v104;
          if ( v104 )
            v105 = CBool::CBool(v104, 1);
          else
            v105 = 0;
          if ( v105 )
            v106 = (char *)v105 + *(int *)(*((_QWORD *)v105 + 1) + 8LL) + 8;
          else
            v106 = 0;
          v107 = UnBCL::String::String((UnBCL::String *)&v408, L"BootManagerTimeoutSaved");
          (*(void (__fastcall **)(struct IExecutionContext *, __int64, char *))(v103 + 96))(a2, v107, v106);
          UnBCL::String::~String((UnBCL::String *)&v408);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v353);
        }
      }
      v111 = OSRollbackUtils::CBCDManipulator::SetTimeout((OSRollbackUtils::CBCDManipulator *)v373, 0);
      if ( v111 )
      {
        v112 = GetLastError();
        v113 = CurrentIP();
        v114 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: BCD failed to set the boot manager timeout. Error: 0x%08X",
                 "CPrepareSafeOSBootRemoval::DoExecute",
                 v111);
        WdsSetupLogMessageW(
          v114,
          819200,
          L"D",
          0,
          5811,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v113,
          v112,
          0,
          0);
      }
      OSRollbackUtils::CBCDManipulator::~CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v373);
    }
    v115 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v351 + 208);
    v116 = UnBCL::String::get_CString(v115);
    v117 = SPMountOfflineHive(v116, L"SYSTEM", L"$OFFLINE_RW$SYSTEM");
    v375 = v117;
    if ( v117 )
    {
      if ( (unsigned int)RegSetBinEx(v117, L"Setup", L"BootPathOverride", 1, L"\\WINDOWS\\", 20) )
      {
        if ( (unsigned int)RegSetDword(v117, L"Setup", L"UPGFilterActive", 1) )
        {
          v118 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v367)(v367);
          PathRoot = UnBCL::Path::GetPathRoot(v118);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v378, PathRoot);
          v120 = GetLastError();
          v121 = CurrentIP();
          v122 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v378);
          v123 = (const char *)UnBCL::String::get_CString(v122);
          v124 = ConstructPartialMsgW(0x4000000u, "VERBOSE: OS part root (DOS): %s", v123);
          WdsSetupLogMessageW(
            v124,
            819200,
            L"D",
            0,
            5867,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v121,
            v120,
            0,
            0);
          v125 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v378);
          v126 = SPGetVolumeNameFromPath(v125, 0, (int *)&v355);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v364, v126);
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v364) )
          {
            v127 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
            if ( UnBCL::String::StartsWith(v127, L"\\\\?\\", 1) )
            {
              v128 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
              v129 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v409, L"\\??\\");
              v130 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v408, L"\\\\?\\");
              v131 = UnBCL::String::Replace(v128, v130, v129, 1);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v353, v131);
              UnBCL::SmartPtr<UnBCL::String>::operator=(v364, v353);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v353);
              UnBCL::String::~String((UnBCL::String *)&v408);
              UnBCL::String::~String((UnBCL::String *)&v409);
            }
            v132 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
            if ( UnBCL::String::StartsWith(v132, L"\\??\\Volume{", 1) )
            {
              v133 = GetLastError();
              v134 = CurrentIP();
              v135 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
              v136 = (const char *)UnBCL::String::get_CString(v135);
              v137 = ConstructPartialMsgW(0x4000000u, "VERBOSE: OS volume: %s", v136);
              WdsSetupLogMessageW(
                v137,
                819200,
                L"D",
                0,
                5889,
                L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                L"CPrepareSafeOSBootRemoval::DoExecute",
                v134,
                v133,
                0,
                0);
              v138 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
              v139 = UnBCL::String::get_CString(v138);
              v140 = 0;
              if ( (unsigned int)RegSetString(v117, L"Setup", L"UPGOsPath", v139) )
              {
                v141 = *((_QWORD *)v351 + 41);
                if ( v141 )
                {
                  v142 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v141 + 16);
                  v143 = SPGetVolumeNameFromPath(v142, 0, (int *)&v355);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v349, v143);
                  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v349) )
                  {
                    v312 = GetLastError();
                    v313 = v312 < 0;
                    if ( v312 > 0 )
                      v313 = 1;
                    if ( v313 )
                    {
                      v314 = GetLastError();
                      v315 = v314;
                      if ( v314 > 0 )
                        v315 = (unsigned __int16)v314 | 0x80070000;
                      if ( v315 >= 0 )
                        v315 = -2147467259;
                    }
                    else
                    {
                      v315 = -2147467259;
                    }
                    v316 = GetLastError();
                    v317 = CurrentIP();
                    v318 = ConstructPartialMsgW(
                             0x2000000u,
                             "%hs: Cannot get volume path for host partition. Error: 0x%08X",
                             "CPrepareSafeOSBootRemoval::DoExecute",
                             v315);
                    WdsSetupLogMessageW(
                      v318,
                      819200,
                      L"D",
                      0,
                      5912,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                      L"CPrepareSafeOSBootRemoval::DoExecute",
                      v317,
                      v316,
                      0,
                      0);
                    v398 = v361;
                    throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v398;
                  }
                  v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
                  if ( UnBCL::String::StartsWith(v144, L"\\\\?\\", 1) )
                  {
                    v145 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
                    v146 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v409, L"\\??\\");
                    v147 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v408, L"\\\\?\\");
                    v148 = UnBCL::String::Replace(v145, v147, v146, 1);
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v353, v148);
                    UnBCL::SmartPtr<UnBCL::String>::operator=(&v349, v353);
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v353);
                    UnBCL::String::~String((UnBCL::String *)&v408);
                    UnBCL::String::~String((UnBCL::String *)&v409);
                  }
                  v149 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
                  if ( !UnBCL::String::StartsWith(v149, L"\\??\\Volume{", 1) )
                  {
                    v319 = GetLastError();
                    v320 = CurrentIP();
                    v321 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
                    v322 = (const char *)UnBCL::String::get_CString(v321);
                    v323 = ConstructPartialMsgW(
                             0x2000000u,
                             "%hs: Unexpected host volume format: %s. Error: 0x%08X",
                             "CPrepareSafeOSBootRemoval::DoExecute",
                             v322,
                             -2147467259);
                    WdsSetupLogMessageW(
                      v323,
                      819200,
                      L"D",
                      0,
                      5922,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                      L"CPrepareSafeOSBootRemoval::DoExecute",
                      v320,
                      v319,
                      0,
                      0);
                    v397 = v361;
                    throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v397;
                  }
                  v150 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
                  v151 = UnBCL::String::get_CString(v150);
                  if ( !(unsigned int)RegSetString(v117, L"Setup", L"UPGBootVhdVolumePath", v151) )
                  {
                    v324 = GetLastError();
                    v325 = v324 < 0;
                    if ( v324 > 0 )
                      v325 = 1;
                    if ( v325 )
                    {
                      v326 = GetLastError();
                      v327 = v326;
                      if ( v326 > 0 )
                        v327 = (unsigned __int16)v326 | 0x80070000;
                      if ( v327 >= 0 )
                        v327 = -2147467259;
                    }
                    else
                    {
                      v327 = -2147467259;
                    }
                    v328 = GetLastError();
                    v329 = CurrentIP();
                    v330 = ConstructPartialMsgW(
                             0x2000000u,
                             "%hs: Cannot set %s value. Error: 0x%08X",
                             "CPrepareSafeOSBootRemoval::DoExecute",
                             (const char *)L"UPGBootVhdVolumePath",
                             v327);
                    WdsSetupLogMessageW(
                      v330,
                      819200,
                      L"D",
                      0,
                      5932,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                      L"CPrepareSafeOSBootRemoval::DoExecute",
                      v329,
                      v328,
                      0,
                      0);
                    v396 = v361;
                    throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v396;
                  }
                  v152 = GetLastError();
                  v153 = CurrentIP();
                  v154 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v349);
                  v155 = (const char *)UnBCL::String::get_CString(v154);
                  v156 = ConstructPartialMsgW(
                           0x4000000u,
                           "%hs: Host volume: %s",
                           "CPrepareSafeOSBootRemoval::DoExecute",
                           v155);
                  WdsSetupLogMessageW(
                    v156,
                    819200,
                    L"D",
                    0,
                    5935,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                    L"CPrepareSafeOSBootRemoval::DoExecute",
                    v153,
                    v152,
                    0,
                    0);
                  v157 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*((_QWORD *)v351 + 41) + 32LL);
                  v158 = UnBCL::String::get_CString(v157);
                  if ( !(unsigned int)RegSetString(v117, L"Setup", L"UPGVhdPath", v158) )
                  {
                    v331 = GetLastError();
                    v332 = v331 < 0;
                    if ( v331 > 0 )
                      v332 = 1;
                    if ( v332 )
                    {
                      v333 = GetLastError();
                      v334 = v333;
                      if ( v333 > 0 )
                        v334 = (unsigned __int16)v333 | 0x80070000;
                      if ( v334 >= 0 )
                        v334 = -2147467259;
                    }
                    else
                    {
                      v334 = -2147467259;
                    }
                    v335 = GetLastError();
                    v336 = CurrentIP();
                    v337 = ConstructPartialMsgW(
                             0x2000000u,
                             "%hs: Cannot set %s value. Error: 0x%08X",
                             "CPrepareSafeOSBootRemoval::DoExecute",
                             (const char *)L"UPGVhdPath",
                             v334);
                    WdsSetupLogMessageW(
                      v337,
                      819200,
                      L"D",
                      0,
                      5944,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                      L"CPrepareSafeOSBootRemoval::DoExecute",
                      v336,
                      v335,
                      0,
                      0);
                    v395 = v361;
                    throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v395;
                  }
                  v159 = GetLastError();
                  v160 = CurrentIP();
                  v161 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*((_QWORD *)v351 + 41) + 32LL);
                  v162 = (const char *)UnBCL::String::get_CString(v161);
                  v163 = ConstructPartialMsgW(
                           0x4000000u,
                           "%hs: VHD path: %s",
                           "CPrepareSafeOSBootRemoval::DoExecute",
                           v162);
                  WdsSetupLogMessageW(
                    v163,
                    819200,
                    L"D",
                    0,
                    5947,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                    L"CPrepareSafeOSBootRemoval::DoExecute",
                    v160,
                    v159,
                    0,
                    0);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v349);
                  v140 = 0;
                }
                v164 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
                v165 = UnBCL::String::get_CString(v164);
                v166 = SPReadOSPiecesSection(L"OS.OLD.Pieces", v165);
                UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>(
                  &v368,
                  v166);
                if ( v369 )
                {
                  v167 = (UnBCL::MultiSz *)UnBCL::Object::operator new(0x70u);
                  v168 = v167;
                  v352 = (__int64)v167;
                  if ( v167 )
                  {
                    UnBCL::MultiSz::MultiSz(v167);
                    *((_QWORD *)v168 + 5) = &UnBCL::MultiSz::`local vftable'{for `UnBCL::Object'};
                  }
                  else
                  {
                    v168 = 0;
                  }
                  UnBCL::SmartPtr<UnBCL::MultiSz>::SmartPtr<UnBCL::MultiSz>(&v349, v168);
                  while ( 1 )
                  {
                    v169 = (int (__fastcall ***)(_QWORD))(v369 + 8 + *(int *)(*(_QWORD *)(v369 + 8) + 12LL));
                    if ( (int)v140 >= (**v169)(v169) )
                      break;
                    v170 = v369 + *(int *)(*(_QWORD *)(v369 + 8) + 16LL) + 8LL;
                    if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v170 + 24LL))(v170, v140) )
                    {
                      v355 = 0;
                      v171 = v369 + *(int *)(*(_QWORD *)(v369 + 8) + 16LL) + 8LL;
                      v172 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v171 + 24LL))(v171, v140);
                      v173 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v172 + 32LL);
                      CGlobalPath::BuildDiskInfoFromPath(v173, 0, 0, 0, 0, &v355);
                    }
                    ++v140;
                  }
                  v174 = (__int64 (__fastcall ***)(_QWORD))((char *)v350 + *(int *)(*(_QWORD *)v350 + 8LL));
                  v175 = (**v174)(v174);
                  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned short const *>>::SmartPtr<UnBCL::IEnumerator<unsigned short const *>>(
                    &v359,
                    v175);
                  v176 = GetLastError();
                  v177 = CurrentIP();
                  v178 = ConstructPartialMsgW(0x4000000u, "OS pieces for WinSetupBoot (no volume):");
                  lpdwDisposition = v176;
                  phkResult = (PHKEY)v177;
                  for ( dwOptions = 5982; ; dwOptions = 5985 )
                  {
                    WdsSetupLogMessageW(
                      v178,
                      819200,
                      L"D",
                      0,
                      dwOptions,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                      L"CPrepareSafeOSBootRemoval::DoExecute",
                      phkResult,
                      lpdwDisposition,
                      0,
                      0);
                    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v360 + 8LL))(v360) )
                      break;
                    v179 = GetLastError();
                    v180 = CurrentIP();
                    v181 = (const char *)(**(__int64 (__fastcall ***)(__int64))v360)(v360);
                    v178 = ConstructPartialMsgW(0x4000000u, "    %s", v181);
                    lpdwDisposition = v179;
                    phkResult = (PHKEY)v180;
                  }
                  Buffer = UnBCL::MultiSz::get_Buffer(v350);
                  if ( !(unsigned int)RegSetMultiSz(v117, L"Setup", L"UPGOldOsPieces", Buffer) )
                  {
                    v338 = GetLastError();
                    v339 = v338 < 0;
                    if ( v338 > 0 )
                      v339 = 1;
                    if ( v339 )
                    {
                      v340 = GetLastError();
                      v341 = v340;
                      if ( v340 > 0 )
                        v341 = (unsigned __int16)v340 | 0x80070000;
                      if ( v341 >= 0 )
                        v341 = -2147467259;
                    }
                    else
                    {
                      v341 = -2147467259;
                    }
                    v342 = GetLastError();
                    v343 = CurrentIP();
                    v344 = ConstructPartialMsgW(
                             0x2000000u,
                             "%hs: Cannot set %s value. Error: 0x%08X",
                             "CPrepareSafeOSBootRemoval::DoExecute",
                             (const char *)L"UPGOldOsPieces",
                             v341);
                    WdsSetupLogMessageW(
                      v344,
                      819200,
                      L"D",
                      0,
                      5994,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                      L"CPrepareSafeOSBootRemoval::DoExecute",
                      v343,
                      v342,
                      0,
                      0);
                    v404 = v361;
                    throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v404;
                  }
                  v359 = &UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned short const *>>::`vftable';
                  UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v359);
                  v349 = &UnBCL::SmartPtr<UnBCL::MultiSz>::`vftable';
                  UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v349);
                }
                else
                {
                  v183 = GetLastError();
                  v184 = CurrentIP();
                  v185 = ConstructPartialMsgW(0x4000000u, "No source OS pieces found");
                  WdsSetupLogMessageW(
                    v185,
                    819200,
                    L"D",
                    0,
                    6000,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                    L"CPrepareSafeOSBootRemoval::DoExecute",
                    v184,
                    v183,
                    0,
                    0);
                }
                v186 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v353, L"WinSetupBoot.sys");
                v187 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v367)(v367);
                v188 = UnBCL::Path::Combine(v187, v186);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v377, v188);
                UnBCL::String::~String((UnBCL::String *)v353);
                v189 = (const struct UnBCL::String *)UnBCL::String::String(
                                                       (UnBCL::String *)&v408,
                                                       L"System32\\Drivers\\WinSetupBoot.sys");
                v190 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v351 + 208);
                v191 = UnBCL::Path::Combine(v190, v189);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v376, v191);
                UnBCL::String::~String((UnBCL::String *)&v408);
                v192 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v376);
                v193 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v377);
                SPCopyFile(v193, v192, 0, 0, 0, 1, 0, 0);
              }
              v305 = GetLastError();
              v306 = v305 < 0;
              if ( v305 > 0 )
                v306 = 1;
              if ( v306 )
              {
                v307 = GetLastError();
                v308 = v307;
                if ( v307 > 0 )
                  v308 = (unsigned __int16)v307 | 0x80070000;
                if ( v308 >= 0 )
                  v308 = -2147467259;
              }
              else
              {
                v308 = -2147467259;
              }
              v309 = GetLastError();
              v310 = CurrentIP();
              v311 = ConstructPartialMsgW(
                       0x2000000u,
                       "%hs: Cannot set %s value. Error: 0x%08X",
                       "CPrepareSafeOSBootRemoval::DoExecute",
                       (const char *)L"UPGOsPath",
                       v308);
              WdsSetupLogMessageW(
                v311,
                819200,
                L"D",
                0,
                5897,
                L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                L"CPrepareSafeOSBootRemoval::DoExecute",
                v310,
                v309,
                0,
                0);
              v399 = v361;
              throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v399;
            }
            v300 = GetLastError();
            v301 = CurrentIP();
            v302 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
            v303 = (const char *)UnBCL::String::get_CString(v302);
            v304 = ConstructPartialMsgW(
                     0x2000000u,
                     "%hs: Unexpected OS volume format: %s. Error: 0x%08X",
                     "CPrepareSafeOSBootRemoval::DoExecute",
                     v303,
                     -2147467259);
            WdsSetupLogMessageW(
              v304,
              819200,
              L"D",
              0,
              5886,
              L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
              L"CPrepareSafeOSBootRemoval::DoExecute",
              v301,
              v300,
              0,
              0);
            v400 = v361;
            throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v400;
          }
          v293 = GetLastError();
          v294 = v293 < 0;
          if ( v293 > 0 )
            v294 = 1;
          if ( v294 )
          {
            v295 = GetLastError();
            v296 = v295;
            if ( v295 > 0 )
              v296 = (unsigned __int16)v295 | 0x80070000;
            if ( v296 >= 0 )
              v296 = -2147467259;
          }
          else
          {
            v296 = -2147467259;
          }
          v297 = GetLastError();
          v298 = CurrentIP();
          v299 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: Cannot get volume path for OS partition. Error: 0x%08X",
                   "CPrepareSafeOSBootRemoval::DoExecute",
                   v296);
          WdsSetupLogMessageW(
            v299,
            819200,
            L"D",
            0,
            5876,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareSafeOSBootRemoval::DoExecute",
            v298,
            v297,
            0,
            0);
          v394 = v361;
          throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v394;
        }
        v286 = GetLastError();
        v287 = v286 < 0;
        if ( v286 > 0 )
          v287 = 1;
        if ( v287 )
        {
          v288 = GetLastError();
          v289 = v288;
          if ( v288 > 0 )
            v289 = (unsigned __int16)v288 | 0x80070000;
          if ( v289 >= 0 )
            v289 = -2147467259;
        }
        else
        {
          v289 = -2147467259;
        }
        v290 = GetLastError();
        v291 = CurrentIP();
        v292 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: Cannot set %s value. Error: 0x%08X",
                 "CPrepareSafeOSBootRemoval::DoExecute",
                 (const char *)L"UPGFilterActive",
                 v289);
        WdsSetupLogMessageW(
          v292,
          819200,
          L"D",
          0,
          5860,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CPrepareSafeOSBootRemoval::DoExecute",
          v291,
          v290,
          0,
          0);
        v401 = v361;
        throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v401;
      }
      v279 = GetLastError();
      v280 = v279 < 0;
      if ( v279 > 0 )
        v280 = 1;
      if ( v280 )
      {
        v281 = GetLastError();
        v282 = v281;
        if ( v281 > 0 )
          v282 = (unsigned __int16)v281 | 0x80070000;
        if ( v282 >= 0 )
          v282 = -2147467259;
      }
      else
      {
        v282 = -2147467259;
      }
      v283 = GetLastError();
      v284 = CurrentIP();
      v285 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Cannot set %s value. Error: 0x%08X",
               "CPrepareSafeOSBootRemoval::DoExecute",
               (const char *)L"BootPathOverride",
               v282);
      WdsSetupLogMessageW(
        v285,
        819200,
        L"D",
        0,
        5848,
        L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
        L"CPrepareSafeOSBootRemoval::DoExecute",
        v284,
        v283,
        0,
        0);
      v402 = v361;
      throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v402;
    }
    v270 = GetLastError();
    v271 = v270 < 0;
    if ( v270 > 0 )
      v271 = 1;
    if ( v271 )
    {
      v272 = GetLastError();
      v273 = v272;
      if ( v272 > 0 )
        v273 = (unsigned __int16)v272 | 0x80070000;
      if ( v273 >= 0 )
        v273 = -2147467259;
    }
    else
    {
      v273 = -2147467259;
    }
    v274 = GetLastError();
    v275 = CurrentIP();
    v276 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v351 + 208);
    v277 = (const char *)UnBCL::String::get_CString(v276);
    v278 = ConstructPartialMsgW(
             0x2000000u,
             "%hs: Cannot load the system hive for the offline OS %s. Error: 0x%08X",
             "CPrepareSafeOSBootRemoval::DoExecute",
             v277,
             v273);
    WdsSetupLogMessageW(
      v278,
      819200,
      L"D",
      0,
      5836,
      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
      L"CPrepareSafeOSBootRemoval::DoExecute",
      v275,
      v274,
      0,
      0);
    v403 = v361;
    throw (`CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v403;
  }
  v194 = GetLastError();
  v195 = CurrentIP();
  v196 = ConstructPartialMsgW(
           0x4000000u,
           "FLOWTRACK: %hs: Will not attempt the SafeOS boot removal, exiting",
           "CPrepareSafeOSBootRemoval::DoExecute");
  WdsSetupLogMessageW(
    v196,
    819200,
    L"D",
    0,
    5502,
    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
    L"CPrepareSafeOSBootRemoval::DoExecute",
    v195,
    v194,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x180140640  mov     r11, rsp
0x180140643  push    rdi
0x180140644  push    r12
0x180140646  push    r13
0x180140648  push    r14
0x18014064a  push    r15
0x18014064c  sub     rsp, 510h
0x180140653  mov     qword ptr [r11-108h], 0FFFFFFFFFFFFFFFEh
0x18014065e  mov     [r11+18h], rbx
0x180140662  mov     [r11+20h], rsi
0x180140666  mov     rax, cs:__security_cookie
0x18014066d  xor     rax, rsp
0x180140670  mov     [rsp+538h+var_30], rax
0x180140678  mov     r12, rdx
0x18014067b  mov     [rsp+538h+var_3D0], rdx
0x180140683  mov     r15, rcx
0x180140686  mov     [rsp+538h+var_4B8], rcx
0x18014068e  xor     r13d, r13d
0x180140691  mov     [r11-460h], r13d
0x180140698  mov     [r11-410h], r13
0x18014069f  mov     [r11-3D8h], r13
0x1801406a6  mov     [r11-3E0h], r13
0x1801406ad  mov     [r11-468h], r13
0x1801406b4  mov     [r11-478h], r13d
0x1801406bb  mov     edi, r13d
0x1801406be  mov     [rsp+538h+var_408], r13
0x1801406c6  mov     rax, [rdx]
0x1801406c9  mov     rcx, rdx
0x1801406cc  mov     rax, [rax+48h]
0x1801406d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801406d5  mov     rbx, rax
0x1801406d8  mov     [rsp+538h+var_368], rax
0x1801406e0  test    rax, rax
0x1801406e3  jz      short loc_180140730
0x1801406e5  mov     rcx, [rax]
0x1801406e8  mov     rax, [rcx+28h]
0x1801406ec  mov     rcx, rbx
0x1801406ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801406f4  test    eax, eax
0x1801406f6  jnz     short loc_180140730
0x1801406f8  mov     rcx, [rbx]
0x1801406fb  mov     rax, [rcx+30h]
0x1801406ff  mov     rcx, rbx
0x180140702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140707  test    rax, rax
0x18014070a  jz      short loc_180140730
0x18014070c  mov     rax, [rbx]
0x18014070f  mov     rcx, rbx
0x180140712  mov     rax, [rax+30h]
0x180140716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014071b  mov     rdi, rax
0x18014071e  mov     [rsp+538h+var_408], rax
0x180140726  mov     [rsp+538h+var_470], r13
0x18014072e  jmp     short loc_18014073D
0x180140730  mov     [rsp+538h+var_470], r13
0x180140738  test    rbx, rbx
0x18014073b  jz      short loc_18014077B
0x18014073d  mov     rax, [rbx]
0x180140740  mov     rcx, rbx
0x180140743  mov     rax, [rax+28h]
0x180140747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014074c  test    eax, eax
0x18014074e  jnz     short loc_18014077B
0x180140750  mov     rax, [rbx]
0x180140753  mov     rcx, rbx
0x180140756  mov     rax, [rax+38h]
0x18014075a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014075f  test    rax, rax
0x180140762  jz      short loc_18014077B
0x180140764  mov     rax, [rbx]
0x180140767  mov     rcx, rbx
0x18014076a  mov     rax, [rax+38h]
0x18014076e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140773  mov     [rsp+538h+var_470], rax
0x18014077b  mov     rcx, [r12]
0x18014077f  mov     rax, [rcx+28h]
0x180140783  mov     rcx, r12
0x180140786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014078b  cmp     eax, 4
0x18014078e  jl      loc_1801430E7
0x180140794  mov     [rsp+538h+var_4D8], r13d
0x180140799  mov     [rsp+538h+var_360], r13
0x1801407a1  lea     rdx, aFreezeprofiles; "FreezeProfilesFolder"
0x1801407a8  lea     rcx, [rsp+538h+var_2C8]
0x1801407b0  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801407b6  nop
0x1801407b7  mov     rdx, rax; struct UnBCL::String *
0x1801407ba  mov     rcx, r12; struct IExecutionContext *
0x1801407bd  call    ?SPGetStoredBOOL@@YAHPEAUIExecutionContext@@PEAVString@UnBCL@@H@Z; SPGetStoredBOOL(IExecutionContext *,UnBCL::String *,int)
0x1801407c2  mov     [rsp+538h+var_3B0], eax
0x1801407c9  lea     rcx, [rsp+538h+var_2C8]
0x1801407d1  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801407d7  mov     eax, 3Fh ; '?'
0x1801407dc  mov     [rsp+538h+var_38], ax
0x1801407e4  mov     ecx, dword ptr cs:asc_180557F68+2; ":\\"
0x1801407ea  mov     [rsp+538h+var_36], ecx
0x1801407f1  movzx   ecx, word ptr cs:asc_180557F68+6; ""
0x1801407f8  mov     [rsp+538h+var_32], cx
0x180140800  lea     rcx, [r15+0D0h]
0x180140807  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18014080d  mov     rcx, rax
0x180140810  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140816  movzx   ecx, word ptr [rax]
0x180140819  mov     [rsp+538h+var_38], cx
0x180140821  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x180140828  lea     rcx, [rsp+538h+var_2C8]
0x180140830  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180140836  mov     rbx, rax
0x180140839  mov     rcx, [r12]
0x18014083d  mov     rax, [rcx]
0x180140840  mov     rcx, r12
0x180140843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140848  mov     rdx, rbx
0x18014084b  mov     rcx, rax
0x18014084e  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180140854  mov     rdx, rax
0x180140857  lea     rcx, [rsp+538h+var_488]
0x18014085f  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180140865  nop
0x180140866  lea     rcx, [rsp+538h+var_2C8]
0x18014086e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180140874  mov     [rsp+538h+var_4D4], r13d
0x180140879  lea     rcx, [rsp+538h+var_448]
0x180140881  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180140887  lea     rax, ??_7CXXXXXHandledException@?M@??DoExecute@CPrepareSafeOSBootRemoval@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CPrepareSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException::`vftable'
0x18014088e  mov     [rsp+538h+var_448], rax
0x180140896  xor     edx, edx
0x180140898  lea     rcx, [rsp+538h+var_3A8]
0x1801408a0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801408a6  nop
0x1801408a7  xor     edx, edx
0x1801408a9  lea     rcx, [rsp+538h+var_398]
0x1801408b1  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801408b7  nop
0x1801408b8  xorps   xmm0, xmm0
0x1801408bb  movups  xmmword ptr [rsp+538h+var_C8.Data1], xmm0
0x1801408c3  cmp     [r15+150h], r13d
0x1801408ca  jnz     loc_1801414E4
0x1801408d0  lea     rcx, [rsp+538h+var_410]
0x1801408d8  call    cs:__imp_BcdOpenSystemStore
0x1801408de  mov     esi, eax
0x1801408e0  test    eax, eax
0x1801408e2  js      loc_18014318A
0x1801408e8  test    rdi, rdi
0x1801408eb  jz      loc_180140FD3
0x1801408f1  lea     r14, [r15+0E0h]
0x1801408f8  mov     rcx, r14
0x1801408fb  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180140901  test    rax, rax
0x180140904  jz      loc_18014393F
0x18014090a  lea     rbx, [r15+0F0h]
0x180140911  mov     rcx, rbx
0x180140914  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18014091a  test    rax, rax
0x18014091d  jz      loc_18014393F
0x180140923  lea     rcx, [r15+110h]
0x18014092a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180140930  test    rax, rax
0x180140933  jz      loc_18014393F
0x180140939  mov     rcx, rbx
0x18014093c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180140942  mov     rbx, rax
0x180140945  mov     rcx, [r12]
0x180140949  mov     rax, [rcx]
0x18014094c  mov     rcx, r12
0x18014094f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140954  mov     rdx, rbx
0x180140957  mov     rcx, rax
0x18014095a  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180140960  mov     rdx, rax
0x180140963  lea     rcx, [rsp+538h+var_4C8]
0x180140968  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18014096e  nop
0x18014096f  call    cs:__imp_GetLastError
0x180140975  mov     ebx, eax
0x180140977  call    cs:__imp_CurrentIP
0x18014097d  mov     rdi, rax
0x180140980  lea     rcx, [rsp+538h+var_4C8]
0x180140985  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18014098b  mov     rcx, rax
0x18014098e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140994  mov     r9, rax
0x180140997  lea     r8, aCpreparesafeos; "CPrepareSafeOSBootRemoval::DoExecute"
0x18014099e  lea     rdx, aHsCommandLineF; "%hs: Command line for the safe OS: %s"
0x1801409a5  mov     ecx, 4000000h; unsigned int
0x1801409aa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801409af  mov     [rsp+538h+var_4E8], r13d
0x1801409b4  mov     [rsp+538h+var_4F0], r13
0x1801409b9  mov     dword ptr [rsp+538h+lpdwDisposition], ebx
0x1801409bd  mov     [rsp+538h+phkResult], rdi
0x1801409c2  lea     rcx, aCpreparesafeos_2; "CPrepareSafeOSBootRemoval::DoExecute"
0x1801409c9  mov     [rsp+538h+lpSecurityAttributes], rcx
0x1801409ce  lea     rcx, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801409d5  mov     qword ptr [rsp+538h+samDesired], rcx
0x1801409da  mov     [rsp+538h+dwOptions], 15B8h
0x1801409e2  xor     r9d, r9d
0x1801409e5  lea     r8, aD_0; "D"
0x1801409ec  mov     r13d, 0C8000h
0x1801409f2  mov     edx, r13d
0x1801409f5  mov     rcx, rax
0x1801409f8  call    cs:__imp_WdsSetupLogMessageW
0x1801409fe  lea     rcx, [rsp+538h+var_4C8]
0x180140a03  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140a09  mov     rcx, rax
0x180140a0c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140a12  xor     edx, edx
0x180140a14  cmp     [rax], dx
0x180140a17  jz      short loc_180140A82
0x180140a19  lea     rcx, [rsp+538h+var_4C8]
0x180140a1e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140a24  mov     rcx, rax
0x180140a27  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140a2d  cmp     word ptr [rax+2], 3Ah ; ':'
0x180140a32  jnz     short loc_180140A82
0x180140a34  lea     rcx, [rsp+538h+var_4C8]
0x180140a39  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140a3f  xor     edx, edx
0x180140a41  lea     r8d, [rdx+2]
0x180140a45  mov     rcx, rax
0x180140a48  call    cs:__imp_?Remove@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Remove(int,int)
0x180140a4e  mov     rdx, rax
0x180140a51  lea     rcx, [rsp+538h+var_4A8]
0x180140a59  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180140a5f  nop
0x180140a60  lea     rdx, [rsp+538h+var_4A8]
0x180140a68  lea     rcx, [rsp+538h+var_4C8]
0x180140a6d  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180140a73  nop
0x180140a74  lea     rcx, [rsp+538h+var_4A8]
0x180140a7c  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180140a82  call    cs:__imp_GetLastError
0x180140a88  mov     edi, eax
0x180140a8a  call    cs:__imp_CurrentIP
0x180140a90  mov     rsi, rax
0x180140a93  mov     rcx, r14
0x180140a96  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140a9c  mov     rcx, rax
0x180140a9f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140aa5  mov     rbx, rax
0x180140aa8  lea     rcx, [rsp+538h+var_4C8]
0x180140aad  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140ab3  mov     rcx, rax
0x180140ab6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140abc  mov     qword ptr [rsp+538h+dwOptions], rbx
0x180140ac1  mov     r9, rax
0x180140ac4  lea     r8, aCpreparesafeos; "CPrepareSafeOSBootRemoval::DoExecute"
0x180140acb  lea     rdx, aHsSettingBootA_0; "%hs: Setting boot app %s for WinRe %s"
0x180140ad2  mov     ecx, 4000000h; unsigned int
0x180140ad7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180140adc  xor     ecx, ecx
0x180140ade  mov     [rsp+538h+var_4E8], ecx
0x180140ae2  mov     [rsp+538h+var_4F0], rcx
0x180140ae7  mov     dword ptr [rsp+538h+lpdwDisposition], edi
0x180140aeb  mov     [rsp+538h+phkResult], rsi
0x180140af0  lea     rcx, aCpreparesafeos_2; "CPrepareSafeOSBootRemoval::DoExecute"
0x180140af7  mov     [rsp+538h+lpSecurityAttributes], rcx
0x180140afc  lea     rcx, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180140b03  mov     qword ptr [rsp+538h+samDesired], rcx
0x180140b08  mov     [rsp+538h+dwOptions], 15C1h
0x180140b10  xor     r9d, r9d
0x180140b13  lea     r8, aD_0; "D"
0x180140b1a  mov     edx, r13d
0x180140b1d  mov     rcx, rax
0x180140b20  call    cs:__imp_WdsSetupLogMessageW
0x180140b26  lea     rcx, [rsp+538h+var_4C8]
0x180140b2b  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140b31  mov     rcx, rax
0x180140b34  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140b3a  mov     rbx, rax
0x180140b3d  mov     rcx, r14
0x180140b40  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140b46  mov     rcx, rax
0x180140b49  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140b4f  mov     rdx, rbx
0x180140b52  mov     rcx, rax
0x180140b55  call    cs:__imp_WinReSetBootApp
0x180140b5b  test    eax, eax
0x180140b5d  jnz     loc_180140C33
0x180140b63  call    cs:__imp_GetLastError
0x180140b69  mov     r13d, 80070000h
0x180140b6f  test    eax, eax
0x180140b71  jle     short loc_180140B7B
0x180140b73  movzx   eax, ax
0x180140b76  or      eax, r13d
0x180140b79  test    eax, eax
0x180140b7b  jns     short loc_180140B96
0x180140b7d  call    cs:__imp_GetLastError
0x180140b83  mov     ebx, eax
0x180140b85  test    eax, eax
0x180140b87  jle     short loc_180140B8F
0x180140b89  movzx   ebx, ax
0x180140b8c  or      ebx, r13d
0x180140b8f  mov     esi, 80004005h
0x180140b94  jmp     short loc_180140B9D
0x180140b96  mov     esi, 80004005h
0x180140b9b  mov     ebx, esi
0x180140b9d  mov     [rsp+538h+var_4D8], ebx
0x180140ba1  call    cs:__imp_GetLastError
0x180140ba7  mov     edi, eax
0x180140ba9  call    cs:__imp_CurrentIP
  ... truncated ...
```
