# MainHr(_GAPP *)

- ea: `0x140013894`
- end: `0x140015d53`
- name: `?MainHr@@YAJPEAU_GAPP@@@Z`
- size: `9407`
- prototype: `__int64 __fastcall(struct _GAPP *)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140021744`

## callees

- `0x140002116`
- `0x140003a78`
- `0x140003d6c`
- `0x1400043a4`
- `0x140004d54`
- `0x140005f7c`
- `0x140006e64`
- `0x140007494`
- `0x1400076c8`
- `0x140007cb0`
- `0x140008624`
- `0x140009700`
- `0x140009aa8`
- `0x140009e18`
- `0x14000a21c`
- `0x14000a564`
- `0x14000b1e4`
- `0x14000b33c`
- `0x14000ba6c`
- `0x14000bccc`
- `0x14000e2a0`
- `0x14000edc4`
- `0x14000f4a4`
- `0x14000f90c`
- `0x14000fbf0`
- `0x14000fcf0`
- `0x14000fe48`
- `0x14001011c`
- `0x140010148`
- `0x140010644`
- `0x140010a14`
- `0x140011d18`
- `0x140012124`
- `0x1400135b8`
- `0x1400136d4`
- `0x140013894`
- `0x140015d5c`
- `0x140015e10`
- `0x1400166d8`
- `0x140016bb4`
- `0x140018ccc`
- `0x14001c624`
- `0x14001d4ac`
- `0x14001dedc`
- `0x14001f300`
- `0x1400203a8`
- `0x140024510`
- `0x14002571c`
- `0x140026104`
- `0x1400276dc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140013ae9`
- `ADVAPI32!RegOpenKeyExW` at `0x140013ae9`
- `ADVAPI32!RegCloseKey` at `0x140015c50`
- `ADVAPI32!RegCloseKey` at `0x140015c50`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140013c4c`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140013c4c`
- `KERNEL32!CloseHandle` at `0x140013ea9`
- `KERNEL32!CloseHandle` at `0x1400146e0`
- `KERNEL32!CloseHandle` at `0x1400148c1`
- `KERNEL32!CloseHandle` at `0x140014fab`
- `KERNEL32!CloseHandle` at `0x140014fc4`
- `KERNEL32!CloseHandle` at `0x140015bb4`
- `KERNEL32!CloseHandle` at `0x140015bcd`
- `KERNEL32!CloseHandle` at `0x140015be3`
- `KERNEL32!CloseHandle` at `0x140015bf9`
- `KERNEL32!CloseHandle` at `0x140015c0f`
- `KERNEL32!CloseHandle` at `0x140015c25`
- `KERNEL32!CloseHandle` at `0x140015c3a`
- `KERNEL32!CloseHandle` at `0x140013ea9`
- `KERNEL32!CloseHandle` at `0x1400146e0`
- `KERNEL32!CloseHandle` at `0x1400148c1`
- `KERNEL32!CloseHandle` at `0x140014fab`
- `KERNEL32!CloseHandle` at `0x140014fc4`
- `KERNEL32!CloseHandle` at `0x140015bb4`
- `KERNEL32!CloseHandle` at `0x140015bcd`
- `KERNEL32!CloseHandle` at `0x140015be3`
- `KERNEL32!CloseHandle` at `0x140015bf9`
- `KERNEL32!CloseHandle` at `0x140015c0f`
- `KERNEL32!CloseHandle` at `0x140015c25`
- `KERNEL32!CloseHandle` at `0x140015c3a`
- `KERNEL32!GetNativeSystemInfo` at `0x14001440f`
- `KERNEL32!GetNativeSystemInfo` at `0x14001440f`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14001415d`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x14001415d`
- `KERNEL32!HeapAlloc` at `0x140013f2f`
- `KERNEL32!HeapAlloc` at `0x140013fd2`
- `KERNEL32!HeapAlloc` at `0x140014053`
- `KERNEL32!HeapAlloc` at `0x140013f2f`
- `KERNEL32!HeapAlloc` at `0x140013fd2`
- `KERNEL32!HeapAlloc` at `0x140014053`
- `KERNEL32!GetProcessHeap` at `0x140013f15`
- `KERNEL32!GetProcessHeap` at `0x140013fb8`
- `KERNEL32!GetProcessHeap` at `0x14001403e`
- `KERNEL32!GetProcessHeap` at `0x140013f15`
- `KERNEL32!GetProcessHeap` at `0x140013fb8`
- `KERNEL32!GetProcessHeap` at `0x14001403e`
- `KERNEL32!GetLastError` at `0x140013b2a`
- `KERNEL32!GetLastError` at `0x140013cb0`
- `KERNEL32!GetLastError` at `0x1400153cb`
- `KERNEL32!GetLastError` at `0x140013b2a`
- `KERNEL32!GetLastError` at `0x140013cb0`
- `KERNEL32!GetLastError` at `0x1400153cb`
- `KERNEL32!GetTickCount64` at `0x140013bb8`
- `KERNEL32!GetTickCount64` at `0x140013d02`
- `KERNEL32!GetTickCount64` at `0x140013bb8`
- `KERNEL32!GetTickCount64` at `0x140013d02`
- `KERNEL32!Sleep` at `0x140013dad`
- `KERNEL32!Sleep` at `0x140013dad`
- `KERNEL32!CreateEventW` at `0x140013b0b`
- `KERNEL32!CreateEventW` at `0x140013b0b`
- `KERNEL32!SetFileAttributesW` at `0x140014cec`
- `KERNEL32!SetFileAttributesW` at `0x140014cec`
- `KERNEL32!GetFileAttributesW` at `0x14001491f`
- `KERNEL32!GetFileAttributesW` at `0x1400150f7`
- `KERNEL32!GetFileAttributesW` at `0x14001491f`
- `KERNEL32!GetFileAttributesW` at `0x1400150f7`
- `KERNEL32!WaitForSingleObject` at `0x140013c6b`
- `KERNEL32!WaitForSingleObject` at `0x140013e2b`
- `KERNEL32!WaitForSingleObject` at `0x14001465c`
- `KERNEL32!WaitForSingleObject` at `0x140014840`
- `KERNEL32!WaitForSingleObject` at `0x140013c6b`
- `KERNEL32!WaitForSingleObject` at `0x140013e2b`
- `KERNEL32!WaitForSingleObject` at `0x14001465c`
- `KERNEL32!WaitForSingleObject` at `0x140014840`
- `KERNEL32!GetModuleFileNameW` at `0x140014119`
- `KERNEL32!GetModuleFileNameW` at `0x140014119`

## string_xrefs

- `0x1400154f9`: `ActionableCompat`
- `0x1400156db`: `ActionableCompat`
- `0x14001578f`: `ActionableCompat`
- `0x140014d29`: `Creating path: [%s]...`
- `0x14001455f`: `ProcessId`
- `0x1400145ab`: `ProcessId`
- `0x140015b3d`: `ProcessId`
- `0x140014abe`: `Removing CorrelationVector registry value...`
- `0x140014b2f`: `Removing cleanup registry value...`
- `0x140014ba0`: `Flushing MoSetup registry key...`
- `0x140013c23`: `CmdLine contains setupplatform.exe Waiting for system-context rollback to start...`
- `0x140013c97`: `Timeout reached. Will retry waiting for system-context rollback to start.`
- `0x140013cd7`: `Error while waiting for system-context rollback to start: [0x%X]`
- `0x140013d76`: `Waited [%d] seconds for system-context rollback to create RollbackOnline key.`
- `0x140013dc2`: `Global\Microsoft.Windows.Setup.Rollback`
- `0x1400145f0`: `Global\Microsoft.Windows.Setup.Rollback`
- `0x140013e11`: `Waiting for Rollback to finish...`
- `0x140014642`: `Waiting for Rollback to finish...`
- `0x140013e52`: `Wait for Rollback mutex returned: [0x%X]`
- `0x140014683`: `Wait for Rollback mutex returned: [0x%X]`
- `0x140013e8a`: `Finished waiting for Rollback!`
- `0x1400146c1`: `Finished waiting for Rollback!`
- `0x14001417b`: `System32`
- `0x14001458c`: `Removing ProcessId registry value...`
- `0x1400145d4`: `Failed to remove ProcessId value, Error: [0x%X]`
- `0x140014727`: `Error checking pending Setup Platform rollback: [0x%X]`
- `0x1400147c5`: `Detected existing cleanup task mutex... exiting.`
- `0x140014907`: `Path cleanup failed! Error = 0x%X`
- `0x1400158d3`: `Path cleanup failed! Error = 0x%X`
- `0x1400149bc`: `Preserve working path: [%s]`
- `0x1400149f6`: `Cleaning alternate storage paths...`
- `0x140014a2b`: `Failed to clean alternate storage paths, Error: [0x%X]`
- `0x140014b06`: `Failed to remove MoSetup cleanup value, Error: [0x%X]`
- `0x140014b77`: `Failed to remove MoSetup cleanup value, Error: [0x%X]`
- `0x140014be1`: `Failed to flush MoSetup registry key, Error: [0x%X]`
- `0x140014c24`: `Windows.old`
- `0x140014cba`: `Creating path (with ACL): [%s]...`
- `0x140014de0`: `Check for FU Reserve tag on directory: [%s]`
- `0x140014e33`: `Marking directory as Hard Reserve: [%s]...`
- `0x140014e73`: `Failed to Mark [%s] directory as Hard Reserve: [0x%X]...`
- `0x140014e8d`: `Directory [%s] is not in Hard Reserve. Not marking [%s] as Hard Reserve `
- `0x140014e9b`: `Failed to get [%s] directory Hard Reserve status: [0x%X]...`
- `0x140014f60`: `Populating Dynamic Update files: [%s] -> [%s]...`
- `0x140015065`: `not already`
- `0x14001505e`: `already`
- `0x1400150c0`: `Failed to read SetupDUConsumed RegKey. Assuming not consumed  - bSetupDUFromUA: [%s]`
- `0x1400151e7`: `Expanding Setup Dynamic Update files: [%s] -> [%s]...`
- `0x140015360`: `Expanding Setup Dynamic Update files: [%s] -> [%s]...`
- `0x140015429`: `Applying SetupDU from a directory: [%s]`
- `0x140015558`: `Launching process: [%s] with command-line [%s] in Session: [%d]`
- `0x14001567c`: `SetupHost process returned: [0x%X], but SetupHostResult registry key has value [0x%X]`
- `0x1400156aa`: `SetupHost process returned: [0x%X], but SetupHostResult registry key was missing.`
- `0x14001570e`: `Remapping DBG_TERMINATE_PROCESS to MOSETUP_E_COMPAT_TERMINATE...`
- `0x1400157bf`: `SetupHost result missing... remapping [0x%x] to MOSETUP_E_COMPAT_TERMINATE.`
- `0x140015891`: `Deleting ESD download directory failed! Error = 0x%X`
- `0x1400159ea`: `%s: Error flushing volatile registry key, Error = 0x%X`
- `0x140015a6b`: `%s: Error opening/creating key for Box result value, Error = 0x%X`

## pseudocode

```c
__int64 __fastcall MainHr(struct _GAPP *a1)
{
  unsigned __int64 v2; // r14
  unsigned __int64 v3; // rbx
  struct IDlpManager *v4; // rdi
  void *v5; // rsi
  int v6; // r12d
  int v7; // r15d
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ecx
  HANDLE v11; // rcx
  int v12; // eax
  __int64 v13; // r9
  const unsigned __int16 *v14; // r8
  HANDLE v15; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v18; // rcx
  int v19; // eax
  ULONGLONG TickCount64; // r12
  __int64 v21; // rcx
  HANDLE v22; // rcx
  DWORD v23; // eax
  int v24; // r15d
  HANDLE v25; // rcx
  HANDLE v26; // rcx
  bool v27; // sf
  ULONGLONG v28; // rax
  HANDLE v29; // rcx
  __int64 v30; // rcx
  int MutexWithAcl; // eax
  int ModulePath; // eax
  HANDLE ProcessHeap; // rax
  void *v34; // rax
  HANDLE v35; // rax
  void *v36; // rax
  HANDLE v37; // rax
  unsigned __int64 v38; // rax
  _OWORD *v39; // rdx
  const unsigned __int16 *v40; // r8
  HANDLE v41; // rcx
  DWORD ModuleFileNameW; // eax
  __int64 v43; // rcx
  __int64 v44; // r14
  int FolderPath; // eax
  int v46; // ecx
  HANDLE v47; // rcx
  __int64 v48; // r8
  const WCHAR *v49; // r12
  bool v50; // zf
  int v51; // eax
  int v52; // eax
  HANDLE v53; // rcx
  int v54; // eax
  __int64 SetupVolatileRegKey; // rax
  __int64 v56; // rcx
  HANDLE v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  int v60; // eax
  HANDLE v61; // rcx
  int v62; // eax
  int v63; // eax
  HANDLE v64; // rcx
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  HANDLE v69; // rcx
  DWORD FileAttributesW; // r14d
  int v71; // r14d
  const wchar_t *v72; // r9
  HANDLE v73; // rcx
  int v74; // eax
  HANDLE v75; // rcx
  int v76; // eax
  HANDLE v77; // rcx
  HANDLE v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rcx
  int v81; // eax
  HANDLE v82; // rcx
  HANDLE v83; // rcx
  __int64 SetupRegKey; // rax
  __int64 v85; // rcx
  int v86; // eax
  HANDLE v87; // rcx
  HANDLE v88; // rcx
  __int64 v89; // rax
  __int64 v90; // rcx
  int v91; // eax
  HANDLE v92; // rcx
  HANDLE v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rcx
  int v96; // eax
  HANDLE v97; // rcx
  HANDLE v98; // rcx
  HANDLE v99; // rcx
  HANDLE v100; // rcx
  unsigned __int16 *v101; // r14
  const char *v102; // rdx
  int v103; // eax
  HANDLE v104; // rcx
  HANDLE v105; // rcx
  int DirHardReserveStatus; // r8d
  char *v107; // rax
  HANDLE v108; // rcx
  int v109; // eax
  HANDLE v110; // rcx
  const unsigned __int16 *v111; // r8
  HANDLE v112; // rcx
  __int64 v113; // r12
  HANDLE v114; // rcx
  __int64 v115; // r14
  int v116; // r12d
  HANDLE v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rcx
  const wchar_t *v120; // r8
  const wchar_t *v121; // r9
  HANDLE v122; // rcx
  HANDLE v123; // rcx
  const WCHAR *v124; // rcx
  DWORD v125; // r14d
  int v126; // r14d
  const WCHAR *v127; // r14
  HANDLE v128; // rcx
  HANDLE v129; // rcx
  HANDLE v130; // rcx
  const WCHAR *v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rcx
  HANDLE v136; // rcx
  const WCHAR *v137; // r12
  HANDLE v138; // rcx
  HANDLE v139; // rcx
  HANDLE v140; // rcx
  HANDLE v141; // rcx
  signed int v142; // eax
  HANDLE v143; // rcx
  const unsigned __int16 *v144; // r12
  const unsigned __int16 *v145; // r14
  __int64 v146; // rax
  __int64 v147; // rcx
  __int64 v148; // rax
  __int64 v149; // rcx
  __int64 v150; // rax
  __int64 v151; // rcx
  HANDLE v152; // rcx
  int v153; // ecx
  unsigned int v154; // r12d
  __int64 v155; // rax
  __int64 v156; // rcx
  __int64 v157; // rax
  __int64 v158; // rcx
  const unsigned __int16 *v159; // rax
  __int64 v160; // rax
  __int64 v161; // rcx
  unsigned int v162; // r8d
  unsigned int v163; // eax
  HANDLE v164; // rcx
  HANDLE v165; // rcx
  __int64 v166; // rax
  __int64 v167; // rcx
  HANDLE v168; // r9
  HANDLE v169; // r9
  __int64 v170; // rax
  __int64 v171; // rcx
  __int64 v172; // rax
  __int64 v173; // rcx
  HANDLE v174; // rcx
  HANDLE v175; // rcx
  char *v176; // rax
  HANDLE v177; // rcx
  int v178; // eax
  HANDLE v179; // rcx
  int v180; // eax
  HANDLE v181; // rcx
  HANDLE v182; // rcx
  unsigned int v183; // r12d
  __int64 v184; // rax
  __int64 v185; // rcx
  int v186; // r8d
  __int64 v187; // rax
  __int64 v188; // rcx
  int v189; // r8d
  __int64 v190; // rax
  __int64 v191; // rcx
  int v192; // eax
  HANDLE v193; // rcx
  HANDLE v194; // rcx
  const unsigned __int16 *v195; // r8
  HANDLE v196; // rcx
  int v197; // eax
  HANDLE v198; // rcx
  HANDLE v199; // rcx
  __int64 v200; // rax
  __int64 v201; // rcx
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  unsigned int v204[2]; // [rsp+30h] [rbp-D8h]
  int v205; // [rsp+40h] [rbp-C8h]
  int v206; // [rsp+58h] [rbp-B0h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A8h] BYREF
  int v208; // [rsp+68h] [rbp-A0h] BYREF
  int v209; // [rsp+6Ch] [rbp-9Ch] BYREF
  unsigned __int16 v210[2]; // [rsp+70h] [rbp-98h] BYREF
  int v211; // [rsp+74h] [rbp-94h] BYREF
  int v212; // [rsp+78h] [rbp-90h] BYREF
  int v213; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v214; // [rsp+80h] [rbp-88h]
  HANDLE hHandle; // [rsp+88h] [rbp-80h]
  unsigned __int64 v216; // [rsp+90h] [rbp-78h]
  int v217; // [rsp+98h] [rbp-70h] BYREF
  int v218; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v219; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 *v220; // [rsp+A8h] [rbp-60h] BYREF
  struct IDlpManager *v221; // [rsp+B0h] [rbp-58h] BYREF
  LPCWSTR lpPathName; // [rsp+B8h] [rbp-50h] BYREF
  LPCWSTR v223; // [rsp+C0h] [rbp-48h] BYREF
  int v224; // [rsp+C8h] [rbp-40h] BYREF
  int v225; // [rsp+CCh] [rbp-3Ch] BYREF
  int v226; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v227; // [rsp+D8h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+E0h] [rbp-28h]
  __int64 v229; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v230; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int16 *v231; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v232; // [rsp+100h] [rbp-8h] BYREF
  HANDLE v233; // [rsp+108h] [rbp+0h]
  HANDLE v234; // [rsp+110h] [rbp+8h]
  HKEY hKey; // [rsp+118h] [rbp+10h] BYREF
  struct CMoReserveManager *v236; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int16 *v237; // [rsp+128h] [rbp+20h] BYREF
  HANDLE v238; // [rsp+130h] [rbp+28h]
  unsigned __int16 *v239; // [rsp+138h] [rbp+30h] BYREF
  __int64 v240; // [rsp+140h] [rbp+38h] BYREF
  __int64 v241; // [rsp+148h] [rbp+40h] BYREF
  LPCWSTR v242; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int16 *v243; // [rsp+158h] [rbp+50h] BYREF
  __int64 v244; // [rsp+160h] [rbp+58h] BYREF
  __int64 v245; // [rsp+168h] [rbp+60h] BYREF
  LPCWSTR v246; // [rsp+170h] [rbp+68h] BYREF
  HANDLE v247; // [rsp+178h] [rbp+70h]
  HANDLE v248; // [rsp+180h] [rbp+78h]
  __int64 v249; // [rsp+188h] [rbp+80h] BYREF
  _QWORD v250[2]; // [rsp+190h] [rbp+88h] BYREF
  _QWORD v251[2]; // [rsp+1A0h] [rbp+98h] BYREF
  _QWORD v252[2]; // [rsp+1B0h] [rbp+A8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+1C0h] [rbp+B8h] BYREF
  WCHAR Buffer[264]; // [rsp+1F8h] [rbp+F0h] BYREF
  WCHAR Filename[264]; // [rsp+408h] [rbp+300h] BYREF

  v252[1] = -2;
  v2 = 0;
  v3 = 0;
  v216 = 0;
  memset_0(Filename, 0, 0x208u);
  v224 = 0;
  v219 = 1;
  v249 = 0;
  v246 = 0;
  v229 = 0;
  v245 = 0;
  v244 = 0;
  lpFileName = 0;
  lpPathName = 0;
  v243 = 0;
  v223 = 0;
  v242 = 0;
  v241 = 0;
  v240 = 0;
  v239 = 0;
  memset_0(Buffer, 0, 0x208u);
  v4 = 0;
  v221 = 0;
  v252[0] = 0;
  v236 = 0;
  v213 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  v225 = 0;
  v210[0] = 0;
  LOWORD(v209) = 0;
  v211 = 0;
  hKey = 0;
  v5 = 0;
  v247 = 0;
  v238 = 0;
  v248 = 0;
  v234 = 0;
  v233 = 0;
  hHandle = 0;
  hObject = 0;
  v227 = 0;
  v237 = 0;
  v232 = 0;
  v231 = 0;
  v220 = 0;
  v230 = 0;
  v218 = 0;
  v226 = 0;
  v212 = 0;
  v208 = 0;
  v6 = 0;
  v217 = 0;
  v214 = 0;
  v251[0] = 0;
  v251[1] = 0;
  v250[0] = 0;
  v250[1] = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    goto LABEL_3;
  }
  if ( !*((_DWORD *)a1 + 26) )
  {
    v9 = *((_DWORD *)a1 + 29);
    if ( v9 == 5 || v9 == 6 || v9 == 9 )
    {
      v10 = *((_DWORD *)a1 + 30);
      if ( v10 != 3 )
      {
        v18 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v18 = g_shLogFile;
        OutputMsg(v18, g_shLogEvent, L"Lowering priority for WU scenario...");
        v19 = LowerPriority(&v221);
        v13 = (unsigned int)v19;
        if ( v19 >= 0 )
          goto LABEL_18;
        v14 = L"Error lowering priority for WU scenario, Error = 0x%X";
        goto LABEL_15;
      }
    }
    else
    {
      v10 = *((_DWORD *)a1 + 30);
    }
    if ( v9 == 8 && v10 != 3 )
    {
      v11 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v11 = g_shLogFile;
      OutputMsg(v11, g_shLogEvent, L"Lowering priority for Azure Host scenario...");
      v12 = LowerPriority(&v221);
      v13 = (unsigned int)v12;
      if ( v12 >= 0 )
        goto LABEL_18;
      v14 = L"Error lowering priority for Azure Host scenario, Error = 0x%X";
LABEL_15:
      v15 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v15 = g_shLogFile;
      OutputMsg(v15, g_shLogEvent, v14, v13);
LABEL_18:
      v4 = v221;
    }
  }
  if ( *((_DWORD *)a1 + 30) == 9 )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x110u, &hKey);
    if ( v7 )
    {
      if ( v7 <= 0 )
        goto LABEL_3;
      v7 = (unsigned __int16)v7;
      goto LABEL_32;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    v5 = EventW;
    if ( !EventW )
    {
      v5 = 0;
      v247 = 0;
LABEL_23:
      LastError = GetLastError();
      v7 = LastError;
      if ( !LastError )
      {
LABEL_24:
        v7 = -2147467259;
        goto LABEL_3;
      }
      if ( LastError <= 0 )
        goto LABEL_3;
      v7 = (unsigned __int16)LastError;
LABEL_32:
      v7 |= 0x80070000;
      goto LABEL_3;
    }
    v247 = EventW;
    TickCount64 = GetTickCount64();
    if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(v21, L"SYSTEM\\Setup", L"CmdLine", &v232) >= 0 )
    {
      while ( StrStrIC(v232) && v2 < 0x493E0 )
      {
        v22 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v22 = g_shLogFile;
        OutputMsg(
          v22,
          g_shLogEvent,
          L"CmdLine contains setupplatform.exe Waiting for system-context rollback to start...");
        v7 = RegNotifyChangeKeyValue(hKey, 1, 4u, v5, 1);
        if ( v7 )
        {
          if ( v7 <= 0 )
            goto LABEL_3;
          v7 = (unsigned __int16)v7;
          goto LABEL_66;
        }
        v23 = WaitForSingleObject(v5, 0xEA60u);
        v24 = 0;
        if ( v23 == 258 )
        {
          v25 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v25 = g_shLogFile;
          OutputMsg(v25, g_shLogEvent, L"Timeout reached. Will retry waiting for system-context rollback to start.");
        }
        else if ( v23 )
        {
          v7 = GetLastError();
          v26 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v26 = g_shLogFile;
          OutputMsg(
            v26,
            g_shLogEvent,
            L"Error while waiting for system-context rollback to start: [0x%X]",
            (unsigned int)v7);
          v27 = v7 < 0;
          if ( v7 > 0 )
          {
            v7 = (unsigned __int16)v7 | 0x80070000;
            v27 = v7 < 0;
          }
          if ( v27 )
            goto LABEL_63;
          v24 = 0;
        }
        v28 = GetTickCount64();
        if ( v28 - TickCount64 > v28 )
        {
          v24 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v2 = v28 - TickCount64;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v24);
        v29 = 0;
        if ( v24 < 0 )
          v2 = 300000;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v29 = g_shLogFile;
        OutputMsg(
          v29,
          g_shLogEvent,
          L"Waited [%d] seconds for system-context rollback to create RollbackOnline key.",
          v2 / 0x3E8);
        if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(v30, L"SYSTEM\\Setup", L"CmdLine", &v232) < 0 )
          break;
      }
    }
    Sleep(0x5DCu);
    MutexWithAcl = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Setup.Rollback");
    v7 = MutexWithAcl;
    if ( MutexWithAcl < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)MutexWithAcl);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
    ModulePath = CheckPendingSetupPlatformRollback();
    v7 = ModulePath;
    if ( ModulePath < 0 )
    {
LABEL_62:
      v8 = (unsigned int)ModulePath;
      goto LABEL_410;
    }
LABEL_86:
    v7 = 0;
    goto LABEL_411;
  }
  switch ( *((_DWORD *)a1 + 29) )
  {
    case 5:
      ProcessHeap = GetProcessHeap();
      v34 = HeapAlloc(ProcessHeap, 0, 0x60u);
      v3 = (unsigned __int64)v34;
      v216 = (unsigned __int64)v34;
      if ( v34 )
      {
        memset_0(v34, 0, 0x60u);
        memset_0((void *)(v3 & -(__int64)(v3 != -8)), 0, 0x60u);
        *(_QWORD *)v3 = &CUpdateScenarioCtrl::`vftable';
        *(_DWORD *)(v3 + 8) = 5;
        *(_QWORD *)(v3 + 16) = 0;
        *(_QWORD *)(v3 + 24) = 0;
        *(_QWORD *)(v3 + 32) = 0;
        *(_QWORD *)(v3 + 40) = 0;
        *(_QWORD *)(v3 + 48) = 0;
        *(_QWORD *)(v3 + 56) = 0;
        *(_QWORD *)(v3 + 80) = 0;
        break;
      }
LABEL_72:
      v3 = 0;
      v216 = 0;
      v8 = 2147942414LL;
LABEL_409:
      v7 = v8;
      goto LABEL_410;
    case 6:
      v35 = GetProcessHeap();
      v36 = HeapAlloc(v35, 0, 0x40u);
      v3 = (unsigned __int64)v36;
      v216 = (unsigned __int64)v36;
      if ( !v36 )
        goto LABEL_72;
      memset_0(v36, 0, 0x40u);
      memset_0((void *)(v3 & -(__int64)(v3 != -8)), 0, 0x40u);
      *(_QWORD *)v3 = &CPackageScenarioCtrl::`vftable';
      *(_DWORD *)(v3 + 8) = 6;
      *(_QWORD *)(v3 + 16) = 0;
      *(_QWORD *)(v3 + 24) = 0;
      *(_QWORD *)(v3 + 32) = 0;
      *(_QWORD *)(v3 + 48) = 0;
      break;
    case 9:
      v37 = GetProcessHeap();
      v38 = (unsigned __int64)HeapAlloc(v37, 0, 0x30u);
      v3 = v38;
      v216 = v38;
      if ( !v38 )
        goto LABEL_72;
      *(_OWORD *)v38 = 0;
      *(_OWORD *)(v38 + 16) = 0;
      *(_OWORD *)(v38 + 32) = 0;
      v39 = (_OWORD *)(v38 & ((unsigned __int128)-(__int128)(v38 + 8) >> 64));
      *v39 = 0;
      v39[1] = 0;
      v39[2] = 0;
      *(_QWORD *)v38 = &CServicingScenarioCtrl::`vftable';
      *(_DWORD *)(v38 + 8) = 9;
      *(_QWORD *)(v38 + 16) = 0;
      *(_QWORD *)(v38 + 24) = 0;
      *(_QWORD *)(v38 + 32) = 0;
      break;
    default:
      v8 = 2147549183LL;
      goto LABEL_409;
  }
  if ( !v3 )
    goto LABEL_72;
  v216 = v3;
  if ( (int)CheckEarlyExit(a1, &v224, &v219) >= 0 && v224 )
  {
    v40 = L"Exiting early!";
LABEL_83:
    v41 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v41 = g_shLogFile;
    OutputMsg(v41, g_shLogEvent, v40);
    goto LABEL_86;
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW )
    goto LABEL_23;
  if ( ModuleFileNameW >= 0x104 )
  {
    v7 = -2147024774;
    goto LABEL_3;
  }
  ModulePath = CMiscHelpersT<CEmptyType>::GetModulePath(v43, &v227);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    goto LABEL_23;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"System32", 0, &v249);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"..", 0, &v246);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::GetFullPathNameW(v246);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  if ( *((_DWORD *)a1 + 29) == 7 )
  {
    v44 = v229;
    FolderPath = CMiscHelpersT<CEmptyType>::CombinePath(v229, L"$Windows.~WS", 0, &lpFileName);
    v7 = FolderPath;
    if ( FolderPath < 0 )
    {
LABEL_97:
      v8 = (unsigned int)FolderPath;
      goto LABEL_410;
    }
    ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(v44, L"ESD\\Download", 0, &v243);
  }
  else
  {
    ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(v229, L"$WINDOWS.~BT", 0, &lpFileName);
  }
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(lpFileName, L"Sources", 0, &lpPathName);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(lpFileName, L"DUDownload", 0, &v240);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(lpFileName, L"DUDownload\\Setup", 0, &v223);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(lpFileName, L"DUDownload\\Cab", 0, &v242);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(v227, L"DUDownload", 0, &v241);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  v46 = *((_DWORD *)a1 + 32);
  if ( v46 != 2 && (((v46 - 4) & 0xFFFFFFFC) != 0 || v46 == 5) )
  {
    if ( *((_DWORD *)a1 + 29) == 1 || *((_DWORD *)a1 + 29) == 4 )
    {
      if ( (int)IsServerMediaFromConfigFile(v227, &v217) < 0 )
      {
        v47 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v47 = g_shLogFile;
        OutputMsg(v47, g_shLogEvent, L"Unable to check for server media.");
      }
      v6 = v217;
    }
  }
  else
  {
    v6 = 1;
  }
  v48 = *((_QWORD *)a1 + 6);
  if ( !v48 )
    v48 = 0;
  v205 = v6;
  v49 = lpPathName;
  ModulePath = (*(__int64 (__fastcall **)(unsigned __int64, WCHAR *, __int64, LPCWSTR, _DWORD, _DWORD, _DWORD, int))(*(_QWORD *)v3 + 8LL))(
                 v3,
                 Filename,
                 v48,
                 lpPathName,
                 *((_DWORD *)a1 + 30),
                 *((_DWORD *)a1 + 32),
                 *((_DWORD *)a1 + 20),
                 v205);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  if ( *((_DWORD *)a1 + 29) != 7 )
  {
    ModulePath = GetNativeArchitecture(&v225, v210);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    if ( v225 )
    {
      ModulePath = CDlpOSInfoT<CUnknownImpl<IUnknown>>::GetModuleMachineArchitecture(&v209);
      v7 = ModulePath;
      if ( ModulePath < 0 )
        goto LABEL_62;
      v50 = v210[0] == (unsigned __int16)v209;
    }
    else
    {
      GetNativeSystemInfo(&SystemInfo);
      ModulePath = CDlpOSInfoT<CUnknownImpl<IUnknown>>::GetModuleArchitecture(&v213);
      v7 = ModulePath;
      if ( ModulePath < 0 )
        goto LABEL_62;
      v50 = SystemInfo.wProcessorArchitecture == v213;
    }
    if ( !v50 )
    {
      v8 = 2147942616LL;
      goto LABEL_409;
    }
  }
  v51 = *((_DWORD *)a1 + 29);
  if ( v51 == 4 )
  {
    if ( (unsigned int)AutorunIsWdsMode() || *((_DWORD *)a1 + 28) )
    {
      v53 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v53 = g_shLogFile;
      OutputMsg(v53, g_shLogEvent, L"Detected wds mode... exiting.");
      v7 = -1047526923;
      goto LABEL_3;
    }
    v51 = *((_DWORD *)a1 + 29);
  }
  if ( v51 == 7 )
  {
    v52 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Websetup");
    v7 = v52;
    if ( v52 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v52);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
  }
  else
  {
    v54 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Setup.Box");
    v7 = v54;
    if ( v54 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v54);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
    SetupVolatileRegKey = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::ValueExists(v56, SetupVolatileRegKey, L"ProcessId", &v208) >= 0
      && v208 )
    {
      v57 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v57 = g_shLogFile;
      OutputMsg(v57, g_shLogEvent, L"Removing ProcessId registry value...");
      v58 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
      v60 = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v59, v58, L"ProcessId");
      if ( v60 < 0 )
      {
        v61 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v61 = g_shLogFile;
        OutputMsg(v61, g_shLogEvent, L"Failed to remove ProcessId value, Error: [0x%X]", (unsigned int)v60);
      }
    }
    v62 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Setup.Rollback");
    v7 = v62;
    if ( v62 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v62);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
    if ( hHandle )
    {
      CloseHandle(hHandle);
      hHandle = 0;
    }
    if ( *((_DWORD *)a1 + 29) == 5 || *((_DWORD *)a1 + 29) == 6 || *((_DWORD *)a1 + 29) == 9 )
    {
      v63 = CheckPendingSetupPlatformRollback();
      if ( v63 < 0 )
      {
        v64 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v64 = g_shLogFile;
        OutputMsg(v64, g_shLogEvent, L"Error checking pending Setup Platform rollback: [0x%X]", (unsigned int)v63);
      }
    }
    v65 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Setup");
    v7 = v65;
    if ( v65 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v65);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
    v66 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Setup.Cleanup");
    v7 = v66;
    if ( v66 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v66);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
    v67 = CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(L"Global\\Microsoft.Windows.Setup.SetupCln");
    v7 = v67;
    if ( v67 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v67);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_3;
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    v49 = lpPathName;
  }
  v68 = PerformCleanup(lpFileName, *((unsigned int *)a1 + 30), *((unsigned int *)a1 + 29));
  if ( v68 < 0 )
  {
    v69 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v69 = g_shLogFile;
    OutputMsg(v69, g_shLogEvent, L"Path cleanup failed! Error = 0x%X", (unsigned int)v68);
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
    v71 = 0;
  else
    v71 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v71 )
  {
    if ( *((_DWORD *)a1 + 27) )
      goto LABEL_189;
    ModulePath = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, int *))(*(_QWORD *)v3 + 16LL))(
                   v3,
                   *((unsigned int *)a1 + 20),
                   &v211);
    v7 = ModulePath;
    if ( ModulePath == -1047527129 )
    {
      v219 = 0;
      goto LABEL_62;
    }
    if ( ModulePath < 0 )
      goto LABEL_62;
    v72 = L"Yes";
    if ( !v211 )
LABEL_189:
      v72 = L"No";
    v73 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v73 = g_shLogFile;
    OutputMsg(v73, g_shLogEvent, L"Preserve working path: [%s]", v72);
  }
  v74 = v211;
  if ( !v211 )
  {
    v75 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v75 = g_shLogFile;
    OutputMsg(v75, g_shLogEvent, L"Cleaning alternate storage paths...");
    v76 = DeleteAlternateStoragePaths();
    if ( v76 < 0 )
    {
      v77 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v77 = g_shLogFile;
      OutputMsg(v77, g_shLogEvent, L"Failed to clean alternate storage paths, Error: [0x%X]", (unsigned int)v76);
    }
    v78 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v78 = g_shLogFile;
    OutputMsg(v78, g_shLogEvent, L"Cleaning MoSetup Volatile key...");
    v79 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    v81 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyIfExists(v80, v79);
    if ( v81 < 0 )
    {
      v82 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v82 = g_shLogFile;
      OutputMsg(v82, g_shLogEvent, L"Failed to clean MoSetup Volatile key, Error: [0x%X]", (unsigned int)v81);
    }
    v83 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v83 = g_shLogFile;
    OutputMsg(v83, g_shLogEvent, L"Removing CorrelationVector registry value...");
    SetupRegKey = MoSetupReg::GetSetupRegKey(*((unsigned int *)a1 + 29));
    v86 = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v85, SetupRegKey, L"CorrelationVector");
    if ( v86 < 0 )
    {
      v87 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v87 = g_shLogFile;
      OutputMsg(v87, g_shLogEvent, L"Failed to remove MoSetup cleanup value, Error: [0x%X]", (unsigned int)v86);
    }
    v88 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v88 = g_shLogFile;
    OutputMsg(v88, g_shLogEvent, L"Removing cleanup registry value...");
    v89 = MoSetupReg::GetSetupRegKey(*((unsigned int *)a1 + 29));
    v91 = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v90, v89, L"Cleanup");
    if ( v91 < 0 )
    {
      v92 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v92 = g_shLogFile;
      OutputMsg(v92, g_shLogEvent, L"Failed to remove MoSetup cleanup value, Error: [0x%X]", (unsigned int)v91);
    }
    v93 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v93 = g_shLogFile;
    OutputMsg(v93, g_shLogEvent, L"Flushing MoSetup registry key...");
    v94 = MoSetupReg::GetSetupRegKey(*((unsigned int *)a1 + 29));
    v96 = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v95, v94);
    if ( v96 < 0 )
    {
      v97 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v97 = g_shLogFile;
      OutputMsg(v97, g_shLogEvent, L"Failed to flush MoSetup registry key, Error: [0x%X]", (unsigned int)v96);
    }
    v98 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v98 = g_shLogFile;
    OutputMsg(v98, g_shLogEvent, L"Cleaning working dir...");
    ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(v229, L"Windows.old", 0, &v245);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    ModulePath = CMiscHelpersT<CEmptyType>::CombinePath(v245, L"Cleanup", 0, &v244);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    ModulePath = DeleteWorkingDir(*((unsigned int *)a1 + 29), Buffer[0], lpFileName, v244);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    v74 = v211;
  }
  if ( *((_DWORD *)a1 + 27) )
  {
    v40 = L"MoSetup Cleanup Mode finish, exit...";
    goto LABEL_83;
  }
  if ( !v74 )
  {
    v99 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v99 = g_shLogFile;
    OutputMsg(v99, g_shLogEvent, L"Creating path (with ACL): [%s]...", lpFileName);
    ModulePath = CDlpHelpersT<CEmptyType>::CreateFolderWithAcl(lpFileName);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    if ( !SetFileAttributesW(lpFileName, 0x2002u) )
      goto LABEL_23;
  }
  if ( (unsigned int)DirectoryExists(v49) )
    goto LABEL_262;
  v100 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v100 = g_shLogFile;
  OutputMsg(v100, g_shLogEvent, L"Creating path: [%s]...", v49);
  ModulePath = DirEnsureExists(v49);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  if ( *((_DWORD *)a1 + 29) != 6 )
    goto LABEL_262;
  v101 = v227;
  v7 = CMiscHelpersT<CEmptyType>::CombinePath(v227, L"Metadata", 0, &v239);
  if ( v7 < 0 )
  {
LABEL_63:
    v8 = (unsigned int)v7;
    goto LABEL_410;
  }
  v103 = CMoReserveManager::CreateInstance(v239, v102, &v236);
  if ( v103 >= 0 )
  {
    v105 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v105 = g_shLogFile;
    OutputMsg(v105, g_shLogEvent, L"Check for FU Reserve tag on directory: [%s]", v101);
    v213 = 0;
    DirHardReserveStatus = CMoReserveManagerT<CUnknownImpl<IUnknown>>::GetDirHardReserveStatus(v236, v101, &v213);
    v107 = (char *)g_shLogFile - 1;
    if ( DirHardReserveStatus < 0 )
    {
      LODWORD(phkResult) = DirHardReserveStatus;
      v111 = L"Failed to get [%s] directory Hard Reserve status: [0x%X]...";
    }
    else
    {
      if ( v213 )
      {
        v108 = 0;
        if ( (unsigned __int64)v107 <= 0xFFFFFFFFFFFFFFFDuLL )
          v108 = g_shLogFile;
        OutputMsg(v108, g_shLogEvent, L"Marking directory as Hard Reserve: [%s]...", v49);
        v109 = CMoReserveManagerT<CUnknownImpl<IUnknown>>::MarkDirAsHardReserve(v236, v49);
        if ( v109 < 0 )
        {
          v110 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v110 = g_shLogFile;
          LODWORD(phkResult) = v109;
          OutputMsg(v110, g_shLogEvent, L"Failed to Mark [%s] directory as Hard Reserve: [0x%X]...", v49, phkResult);
        }
        goto LABEL_262;
      }
      phkResult = (PHKEY)v49;
      v111 = L"Directory [%s] is not in Hard Reserve. Not marking [%s] as Hard Reserve ";
    }
    v112 = 0;
    if ( (unsigned __int64)v107 <= 0xFFFFFFFFFFFFFFFDuLL )
      v112 = g_shLogFile;
    OutputMsg(v112, g_shLogEvent, v111, v101, phkResult);
    goto LABEL_262;
  }
  v104 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v104 = g_shLogFile;
  OutputMsg(v104, g_shLogEvent, L"Storage Reserve Manager Unavailable: [0x%X]", (unsigned int)v103);
LABEL_262:
  ModulePath = (*(__int64 (__fastcall **)(unsigned __int64, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v3 + 24LL))(
                 v3,
                 &v231,
                 &v237);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD *, _QWORD *))(*(_QWORD *)v3 + 48LL))(v3, v251, v250);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  ModulePath = RedirectLogging(v251, v250);
  v7 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_62;
  if ( !v211 )
  {
    v113 = v241;
    if ( (unsigned int)DirectoryExists(v241) )
    {
      v114 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v114 = g_shLogFile;
      v115 = v240;
      OutputMsg(v114, g_shLogEvent, L"Populating Dynamic Update files: [%s] -> [%s]...", v113, v240);
      if ( !(unsigned int)CopyDirectory(v113, v115) )
        goto LABEL_23;
    }
  }
  if ( v4 )
  {
    (*(void (__fastcall **)(struct IDlpManager *))(*(_QWORD *)v4 + 16LL))(v4);
    v221 = 0;
  }
  if ( v234 )
  {
    CloseHandle(v234);
    v234 = 0;
  }
  if ( v233 )
  {
    CloseHandle(v233);
    v233 = 0;
  }
  v212 = 1;
  if ( *((_QWORD *)a1 + 7) )
  {
    v117 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v117 = g_shLogFile;
    OutputMsg(v117, g_shLogEvent, L"SetupDU files found in CmdLine.");
    v116 = 1;
    v206 = 1;
    v118 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v119, v118, L"SetupDUConsumed", &v226) < 0 )
    {
      v123 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v123 = g_shLogFile;
      OutputMsg(
        v123,
        g_shLogEvent,
        L"Failed to read SetupDUConsumed RegKey. Assuming not consumed  - bSetupDUFromUA: [%s]",
        L"TRUE");
    }
    else
    {
      if ( v226 )
      {
        v116 = 0;
        v120 = L"FALSE";
      }
      else
      {
        v120 = L"TRUE";
      }
      v206 = v116;
      v121 = L"not already";
      if ( !v116 )
        v121 = L"already";
      v122 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v122 = g_shLogFile;
      OutputMsg(v122, g_shLogEvent, L"From RegKey: SetupDU files [%s] consumed - bSetupDUFromUA: [%s]", v121, v120);
    }
  }
  else
  {
    v116 = 0;
    v206 = 0;
  }
  if ( !v212 )
    goto LABEL_411;
  while ( v116 )
  {
    v124 = (const WCHAR *)*((_QWORD *)a1 + 7);
    if ( !v124 )
      v124 = 0;
    v125 = GetFileAttributesW(v124);
    if ( v125 == -1 )
      v126 = 0;
    else
      v126 = (v125 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v126 )
    {
      v136 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v136 = g_shLogFile;
      OutputMsg(v136, g_shLogEvent, L"File Not Found: [%s]", *((_QWORD *)a1 + 7));
LABEL_335:
      v127 = v223;
      goto LABEL_336;
    }
    v127 = v223;
    if ( (unsigned int)DirectoryExists(v223) )
    {
      v128 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v128 = g_shLogFile;
      OutputMsg(v128, g_shLogEvent, L"Deleting folder [%s] before expansion...", v127);
      if ( !(unsigned int)DeletePathEx(v127) )
        goto LABEL_332;
    }
    v129 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v129 = g_shLogFile;
    OutputMsg(v129, g_shLogEvent, L"Creating folder [%s] for expansion...", v127);
    FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v127);
    v7 = FolderPath;
    if ( FolderPath < 0 )
      goto LABEL_97;
    v130 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v130 = g_shLogFile;
    OutputMsg(v130, g_shLogEvent, L"Expanding Setup Dynamic Update files: [%s] -> [%s]...", *((_QWORD *)a1 + 7), v127);
    v131 = (const WCHAR *)*((_QWORD *)a1 + 7);
    if ( !v131 )
      v131 = 0;
    FolderPath = OpenCABFilesInFolder(v131, v127);
    v7 = FolderPath;
    if ( FolderPath < 0 )
      goto LABEL_97;
    v132 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    FolderPath = CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v133, v132);
    v7 = FolderPath;
    if ( FolderPath < 0 )
      goto LABEL_97;
    v134 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    FolderPath = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v135, v134, L"SetupDUConsumed", 1);
    v7 = FolderPath;
    if ( FolderPath < 0 )
      goto LABEL_97;
    v206 = 0;
LABEL_336:
    if ( (unsigned int)DirectoryExists(v127) )
    {
      v143 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v143 = g_shLogFile;
      v144 = lpPathName;
      OutputMsg(v143, g_shLogEvent, L"Applying SetupDU from a directory: [%s]", v127, lpPathName);
      ModulePath = MergeAndApplySetupDU(v127, v144);
      v7 = ModulePath;
      v145 = 0;
      if ( ModulePath < 0 )
        goto LABEL_62;
    }
    else
    {
      v144 = lpPathName;
      v145 = 0;
    }
    v212 = 0;
    SH_SSTRING::operator=(&v220);
    ModulePath = CreateCommandLine(a1, v237, &v220);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    SH_SSTRING::operator=(&v230);
    ModulePath = (*(__int64 (__fastcall **)(unsigned __int64, __int64 *))(*(_QWORD *)v3 + 32LL))(v3, &v230);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    ModulePath = STRAPI_Format(&v220, L"%s %s", v220, v230);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    v146 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    ModulePath = CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v147, v146);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    v148 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    ModulePath = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v149, v148, L"ActionableCompat");
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    v150 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    ModulePath = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v151, v150);
    v7 = ModulePath;
    if ( ModulePath < 0 )
      goto LABEL_62;
    v152 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v152 = g_shLogFile;
    v204[0] = *((_DWORD *)a1 + 16);
    OutputMsg(
      v152,
      g_shLogEvent,
      L"Launching process: [%s] with command-line [%s] in Session: [%d]",
      v231,
      v220,
      *(_QWORD *)v204);
    v153 = *((_DWORD *)a1 + 29);
    if ( v153 == 4 || (unsigned int)(v153 - 1) <= 1 || v153 == 8 )
    {
      v154 = -1;
    }
    else
    {
      v145 = v144;
      v154 = 54000000;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    v155 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    v7 = CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v156, v155, L"SetupHostResult");
    if ( v7 < 0 )
      goto LABEL_63;
    v157 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    FolderPath = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v158, v157);
    v7 = FolderPath;
    if ( FolderPath < 0 )
      goto LABEL_97;
    v214 = 1;
    v159 = (const unsigned __int16 *)*((_QWORD *)a1 + 4);
    if ( !v159 )
      v159 = 0;
    v7 = LaunchProcessInSession(v231, v220, v145, *((_DWORD *)a1 + 16), v159, v154, &v212);
    v160 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v161, v160, L"SetupHostResult", &v218) < 0 )
    {
      v165 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v165 = g_shLogFile;
      OutputMsg(
        v165,
        g_shLogEvent,
        L"SetupHost process returned: [0x%X], but SetupHostResult registry key was missing.",
        (unsigned int)v7);
    }
    else
    {
      v162 = v218;
      if ( v218 > 0 )
        v163 = (unsigned __int16)v218 | 0x80070000;
      else
        v163 = v218;
      if ( v163 != v7 )
      {
        if ( v218 > 0 )
          v162 = (unsigned __int16)v218 | 0x80070000;
        v164 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v164 = g_shLogFile;
        LODWORD(phkResult) = v162;
        OutputMsg(
          v164,
          g_shLogEvent,
          L"SetupHost process returned: [0x%X], but SetupHostResult registry key has value [0x%X]",
          (unsigned int)v7,
          phkResult);
      }
    }
    if ( v7 == 1073807364 )
    {
      v166 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
      if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::ValueExists(v167, v166, L"ActionableCompat", &v208) >= 0
        && v208 )
      {
        v168 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v168 = g_shLogFile;
        v7 = -1047527159;
        OutputMsg(v168, g_shLogEvent, L"Remapping DBG_TERMINATE_PROCESS to MOSETUP_E_COMPAT_TERMINATE...");
      }
      else
      {
        v169 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v169 = g_shLogFile;
        v7 = -1047527162;
        OutputMsg(v169, g_shLogEvent, L"Remapping DBG_TERMINATE_PROCESS to MOSETUP_E_TERMINATE_PROCESS...");
      }
    }
    else if ( v7 >= 0 )
    {
      v170 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
      if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v171, v170, L"SetupHostResult", &v218) < 0 )
      {
        v172 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
        if ( (int)CRegUtilT<unsigned short *,CRegType,0,1>::ValueExists(v173, v172, L"ActionableCompat", &v208) >= 0
          && v208 )
        {
          v174 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v174 = g_shLogFile;
          OutputMsg(
            v174,
            g_shLogEvent,
            L"SetupHost result missing... remapping [0x%x] to MOSETUP_E_COMPAT_TERMINATE.",
            (unsigned int)v7);
          v7 = -1047527159;
        }
        else
        {
          v175 = 0;
          v176 = (char *)g_shLogFile - 1;
          if ( v7 == 1 )
          {
            if ( (unsigned __int64)v176 <= 0xFFFFFFFFFFFFFFFDuLL )
              v175 = g_shLogFile;
            OutputMsg(
              v175,
              g_shLogEvent,
              L"SetupHost result missing... remapping [0x%x] to MOSETUP_E_TERMINATE_PROCESS.",
              1);
            v7 = -1047527162;
          }
          else
          {
            if ( (unsigned __int64)v176 <= 0xFFFFFFFFFFFFFFFDuLL )
              v175 = g_shLogFile;
            OutputMsg(
              v175,
              g_shLogEvent,
              L"SetupHost result missing... remapping [0x%x] to MOSETUP_E_PROCESS_CRASHED.",
              (unsigned int)v7);
            v7 = -1047527137;
          }
        }
      }
    }
    v177 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v177 = g_shLogFile;
    OutputMsg(v177, g_shLogEvent, L"LaunchProcessInSession returned: [0x%X]", (unsigned int)v7);
    if ( *((_DWORD *)a1 + 29) == 7 )
    {
      v178 = BoxDeletePath(v243);
      if ( v178 < 0 )
      {
        v179 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v179 = g_shLogFile;
        OutputMsg(v179, g_shLogEvent, L"Deleting ESD download directory failed! Error = 0x%X", (unsigned int)v178);
      }
    }
    v180 = PerformCleanup(lpFileName, *((unsigned int *)a1 + 30), *((unsigned int *)a1 + 29));
    if ( v180 < 0 )
    {
      v181 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v181 = g_shLogFile;
      OutputMsg(v181, g_shLogEvent, L"Path cleanup failed! Error = 0x%X", (unsigned int)v180);
    }
    if ( !v212 )
      goto LABEL_411;
    v116 = v206;
  }
  v137 = v242;
  if ( !(unsigned int)DirectoryExists(v242) )
    goto LABEL_335;
  v127 = v223;
  if ( !(unsigned int)DirectoryExists(v223) )
    goto LABEL_467;
  v138 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v138 = g_shLogFile;
  OutputMsg(v138, g_shLogEvent, L"Deleting folder [%s] before expansion...", v127);
  if ( (unsigned int)DeletePathEx(v127) )
  {
LABEL_467:
    v139 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v139 = g_shLogFile;
    OutputMsg(v139, g_shLogEvent, L"Creating folder [%s] for expansion...", v127);
    FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v127);
    v7 = FolderPath;
    v140 = 0;
    if ( FolderPath < 0 )
      goto LABEL_97;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v140 = g_shLogFile;
    OutputMsg(v140, g_shLogEvent, L"Expanding Setup Dynamic Update files: [%s] -> [%s]...", v137, v127);
    FolderPath = OpenCABFilesInFolder(v137, v127);
    v7 = FolderPath;
    v141 = 0;
    if ( FolderPath < 0 )
      goto LABEL_97;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v141 = g_shLogFile;
    OutputMsg(v141, g_shLogEvent, L"Deleting folder [%s] after successful expansion...", v137);
    if ( (unsigned int)DeletePathEx(v137) )
      goto LABEL_336;
  }
LABEL_332:
  v142 = GetLastError();
  v7 = v142;
  if ( !v142 )
    goto LABEL_24;
  if ( v142 > 0 )
  {
    v7 = (unsigned __int16)v142;
LABEL_66:
    v7 |= 0x80070000;
  }
LABEL_3:
  v8 = (unsigned int)v7;
LABEL_410:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_411:
  if ( *((_DWORD *)a1 + 29) == 6 || *((_DWORD *)a1 + 29) == 9 )
  {
    v183 = v214;
    if ( !v214 && v7 == -2147024891 )
    {
      v194 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v194 = g_shLogFile;
      v204[0] = -1047526935;
      LODWORD(phkResult) = -2147024891;
      OutputMsg(
        v194,
        g_shLogEvent,
        L"%s: Remapping [0x%X] to [0x%X] to facilitate retries",
        L"MainHr",
        phkResult,
        *(_QWORD *)v204);
      v7 = -1047526935;
    }
  }
  else
  {
    if ( v7 == -1047526935 )
    {
      v182 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v182 = g_shLogFile;
      v204[0] = -2147024891;
      LODWORD(phkResult) = -1047526935;
      OutputMsg(
        v182,
        g_shLogEvent,
        L"%s: Remapping [0x%X] to [0x%X] in a non-UUP scenario",
        L"MainHr",
        phkResult,
        *(_QWORD *)v204);
      v7 = -2147024891;
    }
    v183 = v214;
  }
  if ( v219 )
  {
    v184 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    v186 = CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v185, v184);
    if ( v186 < 0 )
    {
      LODWORD(phkResult) = v186;
      v195 = L"%s: Error opening/creating key for Box result value, Error = 0x%X";
    }
    else
    {
      v187 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
      v189 = CRegUtilT<unsigned long,CRegType,0,1>::SetValue(v188, v187, L"BoxResult", (unsigned int)v7);
      if ( v189 >= 0 )
      {
        v190 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
        v192 = CDlpHelpersT<CEmptyType>::FlushRegistryKey(v191, v190);
        if ( v192 < 0 )
        {
          v193 = 0;
          if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            v193 = g_shLogFile;
          LODWORD(phkResult) = v192;
          OutputMsg(v193, g_shLogEvent, L"%s: Error flushing volatile registry key, Error = 0x%X", L"MainHr", phkResult);
        }
        goto LABEL_435;
      }
      LODWORD(phkResult) = v189;
      v195 = L"%s: Error storing Box result value, Error = 0x%X";
    }
    v196 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v196 = g_shLogFile;
    OutputMsg(v196, g_shLogEvent, v195, L"MainHr", phkResult);
  }
LABEL_435:
  if ( v7 < 0 )
  {
    if ( v3 )
    {
      v197 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 40LL))(
               v3,
               v183,
               (unsigned int)v7);
      if ( v197 < 0 )
      {
        v198 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v198 = g_shLogFile;
        LODWORD(phkResult) = v197;
        OutputMsg(v198, g_shLogEvent, L"%s: spScenarioCtrl->OnFailure returned Error = 0x%X", L"MainHr", phkResult);
      }
    }
    v199 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v199 = g_shLogFile;
    LODWORD(phkResult) = v7;
    OutputMsg(v199, g_shLogEvent, L"%s: Error = 0x%X", L"MainHr", phkResult);
  }
  if ( v238 )
  {
    v200 = MoSetupReg::GetSetupVolatileRegKey(*((unsigned int *)a1 + 29));
    CRegUtilT<unsigned long,CRegType,0,1>::DeleteValueIfExists(v201, v200, L"ProcessId");
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(v250);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(v251);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v230);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v220);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v231);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v232);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v237);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v227);
  if ( hObject )
    CloseHandle(hObject);
  if ( hHandle )
    CloseHandle(hHandle);
  if ( v233 )
    CloseHandle(v233);
  if ( v234 )
    CloseHandle(v234);
  if ( v248 )
    CloseHandle(v248);
  if ( v238 )
    CloseHandle(v238);
  if ( v5 )
    CloseHandle(v5);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  SP_COM<CMoReserveManager>::~SP_COM<CMoReserveManager>(&v236);
  SP_COM<CMoReserveManager>::~SP_COM<CMoReserveManager>(v252);
  SP_COM<CMoReserveManager>::~SP_COM<CMoReserveManager>(&v221);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v239);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v240);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v241);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v223);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v243);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpPathName);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v244);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v245);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v229);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v246);
  DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v249);
  if ( v3 )
    (**(void (__fastcall ***)(unsigned __int64, __int64))v3)(v3, 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140013894  mov     rax, rsp
0x140013897  push    rbp
0x140013898  push    r12
0x14001389a  push    r13
0x14001389c  push    r14
0x14001389e  push    r15
0x1400138a0  lea     rbp, [rax-548h]
0x1400138a7  sub     rsp, 620h
0x1400138ae  mov     [rbp+540h+var_490], 0FFFFFFFFFFFFFFFEh
0x1400138b9  mov     [rax+10h], rbx
0x1400138bd  mov     [rax+18h], rsi
0x1400138c1  mov     [rax+20h], rdi
0x1400138c5  mov     rax, cs:__security_cookie
0x1400138cc  xor     rax, rsp
0x1400138cf  mov     [rbp+540h+var_30], rax
0x1400138d6  mov     r13, rcx
0x1400138d9  xor     r14d, r14d
0x1400138dc  mov     ebx, r14d
0x1400138df  mov     [rbp+540h+var_5B8], rbx
0x1400138e3  mov     edi, 208h
0x1400138e8  mov     r8d, edi; Size
0x1400138eb  xor     edx, edx; Val
0x1400138ed  lea     rcx, [rbp+540h+Filename]; void *
0x1400138f4  call    memset_0
0x1400138f9  mov     [rbp+540h+var_580], r14d
0x1400138fd  mov     [rbp+540h+var_5A8], 1
0x140013904  mov     [rbp+540h+var_4C0], r14
0x14001390b  mov     [rbp+540h+var_4D8], r14
0x14001390f  mov     [rbp+540h+var_560], r14
0x140013913  mov     [rbp+540h+var_4E0], r14
0x140013917  mov     [rbp+540h+var_4E8], r14
0x14001391b  mov     [rsp+640h+lpFileName], r14
0x140013920  mov     [rbp+540h+lpPathName], r14
0x140013924  mov     [rbp+540h+var_4F0], r14
0x140013928  mov     [rbp+540h+var_588], r14
0x14001392c  mov     [rbp+540h+var_4F8], r14
0x140013930  mov     [rbp+540h+var_500], r14
0x140013934  mov     [rbp+540h+var_508], r14
0x140013938  mov     [rbp+540h+var_510], r14
0x14001393c  mov     r8d, edi; Size
0x14001393f  xor     edx, edx; Val
0x140013941  lea     rcx, [rbp+540h+Buffer]; void *
0x140013948  call    memset_0
0x14001394d  mov     edi, r14d
0x140013950  mov     [rbp+540h+var_598], r14
0x140013954  mov     [rbp+540h+var_498], r14
0x14001395b  mov     [rbp+540h+var_528], r14
0x14001395f  mov     [rsp+640h+var_5CC], r14d
0x140013964  xorps   xmm0, xmm0
0x140013967  movups  xmmword ptr [rbp+540h+SystemInfo], xmm0
0x14001396e  movups  xmmword ptr [rbp+540h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140013975  movups  xmmword ptr [rbp+540h+SystemInfo.dwNumberOfProcessors], xmm0
0x14001397c  mov     [rbp+540h+var_57C], r14d
0x140013980  mov     [rsp+640h+var_5D8], r14w
0x140013986  mov     word ptr [rsp+640h+var_5DC], r14w
0x14001398c  mov     [rsp+640h+var_5D4], r14d
0x140013991  mov     [rbp+540h+hKey], r14
0x140013995  mov     esi, r14d
0x140013998  mov     [rbp+540h+var_4D0], r14
0x14001399c  mov     [rbp+540h+var_518], r14
0x1400139a0  mov     [rbp+540h+var_4C8], r14
0x1400139a4  mov     [rbp+540h+var_538], r14
0x1400139a8  mov     [rbp+540h+var_540], r14
0x1400139ac  mov     [rbp+540h+hHandle], r14
0x1400139b0  mov     [rbp+540h+hObject], r14
0x1400139b4  mov     [rbp+540h+var_570], r14
0x1400139b8  mov     [rbp+540h+var_520], r14
0x1400139bc  mov     [rbp+540h+var_548], r14
0x1400139c0  mov     [rbp+540h+var_550], r14
0x1400139c4  mov     [rbp+540h+var_5A0], r14
0x1400139c8  mov     [rbp+540h+var_558], r14
0x1400139cc  mov     [rbp+540h+var_5AC], r14d
0x1400139d0  mov     [rbp+540h+var_578], r14d
0x1400139d4  mov     [rsp+640h+var_5D0], r14d
0x1400139d9  mov     [rsp+640h+var_5E0], r14d
0x1400139de  mov     dword ptr [rsp+640h+var_5F0], r14d
0x1400139e3  mov     r12d, r14d
0x1400139e6  mov     [rbp+540h+var_5B0], r14d
0x1400139ea  mov     [rsp+640h+var_5C8], r14d
0x1400139ef  mov     [rbp+540h+var_4A8], r14
0x1400139f6  mov     [rbp+540h+var_4A0], r14
0x1400139fd  mov     [rbp+540h+var_4B8], r14
0x140013a04  mov     [rbp+540h+var_4B0], r14
0x140013a0b  lea     r15d, [r14+9]
0x140013a0f  test    r13, r13
0x140013a12  jnz     short loc_140013A22
0x140013a14  mov     r15d, 80070057h
0x140013a1a  mov     ecx, r15d
0x140013a1d  jmp     loc_1400158FF
0x140013a22  cmp     [r13+68h], r14d
0x140013a26  jnz     loc_140013ABF
0x140013a2c  mov     eax, [r13+74h]
0x140013a30  cmp     eax, 5
0x140013a33  jz      loc_140013B48
0x140013a39  cmp     eax, 6
0x140013a3c  jz      loc_140013B48
0x140013a42  cmp     eax, r15d
0x140013a45  jz      loc_140013B48
0x140013a4b  mov     ecx, [r13+78h]
0x140013a4f  cmp     eax, 8
0x140013a52  jnz     short loc_140013ABF
0x140013a54  cmp     ecx, 3
0x140013a57  jz      short loc_140013ABF
0x140013a59  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013a60  lea     rax, [rdx-1]
0x140013a64  mov     rcx, r14
0x140013a67  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013a6b  cmovbe  rcx, rdx; hFile
0x140013a6f  lea     r8, aLoweringPriori_0; "Lowering priority for Azure Host scenar"...
0x140013a76  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013a7d  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013a82  lea     rcx, [rbp+540h+var_598]; struct IDlpManager **
0x140013a86  call    ?LowerPriority@@YAJPEAPEAVIDlpManager@@@Z; LowerPriority(IDlpManager * *)
0x140013a8b  mov     r9d, eax
0x140013a8e  test    eax, eax
0x140013a90  jns     short loc_140013ABB
0x140013a92  lea     r8, aErrorLoweringP_0; "Error lowering priority for Azure Host "...
0x140013a99  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013aa0  lea     rax, [rdx-1]
0x140013aa4  mov     rcx, r14
0x140013aa7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013aab  cmovbe  rcx, rdx; hFile
0x140013aaf  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013ab6  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013abb  mov     rdi, [rbp+540h+var_598]
0x140013abf  cmp     [r13+78h], r15d
0x140013ac3  jnz     loc_140013F0A
0x140013ac9  lea     rax, [rbp+540h+hKey]
0x140013acd  mov     [rsp+640h+phkResult], rax; phkResult
0x140013ad2  mov     r9d, 110h; samDesired
0x140013ad8  xor     r8d, r8d; ulOptions
0x140013adb  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x140013ae2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140013ae9  call    cs:__imp_RegOpenKeyExW
0x140013af0  nop     dword ptr [rax+rax+00h]
0x140013af5  mov     r15d, eax
0x140013af8  test    eax, eax
0x140013afa  jnz     loc_140013EF8
0x140013b00  xor     r9d, r9d; lpName
0x140013b03  xor     r8d, r8d; bInitialState
0x140013b06  lea     edx, [rax+1]; bManualReset
0x140013b09  xor     ecx, ecx; lpEventAttributes
0x140013b0b  call    cs:__imp_CreateEventW
0x140013b12  nop     dword ptr [rax+rax+00h]
0x140013b17  mov     rsi, rax
0x140013b1a  test    rax, rax
0x140013b1d  jnz     loc_140013BB4
0x140013b23  mov     rsi, r14
0x140013b26  mov     [rbp+540h+var_4D0], r14
0x140013b2a  call    cs:__imp_GetLastError
0x140013b31  nop     dword ptr [rax+rax+00h]
0x140013b36  test    eax, eax
0x140013b38  mov     r15d, eax
0x140013b3b  jnz     short loc_140013B9E
0x140013b3d  mov     r15d, 80004005h
0x140013b43  jmp     loc_140013A1A
0x140013b48  mov     ecx, [r13+78h]
0x140013b4c  cmp     ecx, 3
0x140013b4f  jz      loc_140013A4F
0x140013b55  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013b5c  lea     rax, [rdx-1]
0x140013b60  mov     rcx, r14
0x140013b63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013b67  cmovbe  rcx, rdx; hFile
0x140013b6b  lea     r8, aLoweringPriori; "Lowering priority for WU scenario..."
0x140013b72  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013b79  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013b7e  lea     rcx, [rbp+540h+var_598]; struct IDlpManager **
0x140013b82  call    ?LowerPriority@@YAJPEAPEAVIDlpManager@@@Z; LowerPriority(IDlpManager * *)
0x140013b87  mov     r9d, eax
0x140013b8a  test    eax, eax
0x140013b8c  jns     loc_140013ABB
0x140013b92  lea     r8, aErrorLoweringP; "Error lowering priority for WU scenario"...
0x140013b99  jmp     loc_140013A99
0x140013b9e  jle     loc_140013A1A
0x140013ba4  movzx   r15d, ax
0x140013ba8  or      r15d, 80070000h
0x140013baf  jmp     loc_140013A1A
0x140013bb4  mov     [rbp+540h+var_4D0], rsi
0x140013bb8  call    cs:__imp_GetTickCount64
0x140013bbf  nop     dword ptr [rax+rax+00h]
0x140013bc4  mov     r12, rax
0x140013bc7  lea     r9, [rbp+540h+var_548]
0x140013bcb  lea     r8, aCmdline; "CmdLine"
0x140013bd2  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x140013bd9  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x140013bde  xor     r15d, r15d
0x140013be1  test    eax, eax
0x140013be3  js      loc_140013DA8
0x140013be9  mov     edi, 80070000h
0x140013bee  mov     rcx, [rbp+540h+var_548]
0x140013bf2  call    StrStrIC
0x140013bf7  test    rax, rax
0x140013bfa  jz      loc_140013DA8
0x140013c00  cmp     r14, 493E0h
0x140013c07  jnb     loc_140013DA8
0x140013c0d  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013c14  lea     rax, [rdx-1]
0x140013c18  mov     rcx, r15
0x140013c1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013c1f  cmovbe  rcx, rdx; hFile
0x140013c23  lea     r8, aCmdlineContain; "CmdLine contains setupplatform.exe Wait"...
0x140013c2a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013c31  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013c36  mov     eax, 1
0x140013c3b  mov     dword ptr [rsp+640h+phkResult], eax; fAsynchronous
0x140013c3f  mov     r9, rsi; hEvent
0x140013c42  lea     r8d, [rax+3]; dwNotifyFilter
0x140013c46  mov     edx, eax; bWatchSubtree
0x140013c48  mov     rcx, [rbp+540h+hKey]; hKey
0x140013c4c  call    cs:__imp_RegNotifyChangeKeyValue
0x140013c53  nop     dword ptr [rax+rax+00h]
0x140013c58  mov     r15d, eax
0x140013c5b  test    eax, eax
0x140013c5d  jnz     loc_140013EE0
0x140013c63  mov     edx, 0EA60h; dwMilliseconds
0x140013c68  mov     rcx, rsi; hHandle
0x140013c6b  call    cs:__imp_WaitForSingleObject
0x140013c72  nop     dword ptr [rax+rax+00h]
0x140013c77  xor     r15d, r15d
0x140013c7a  cmp     eax, 102h
0x140013c7f  jnz     short loc_140013CAC
0x140013c81  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013c88  lea     rax, [rdx-1]
0x140013c8c  mov     ecx, r15d
0x140013c8f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013c93  cmovbe  rcx, rdx; hFile
0x140013c97  lea     r8, aTimeoutReached; "Timeout reached. Will retry waiting for"...
0x140013c9e  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013ca5  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013caa  jmp     short loc_140013D02
0x140013cac  test    eax, eax
0x140013cae  jz      short loc_140013D02
0x140013cb0  call    cs:__imp_GetLastError
0x140013cb7  nop     dword ptr [rax+rax+00h]
0x140013cbc  mov     r15d, eax
0x140013cbf  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013cc6  lea     rax, [rdx-1]
0x140013cca  xor     ecx, ecx
0x140013ccc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013cd0  cmovbe  rcx, rdx; hFile
0x140013cd4  mov     r9d, r15d
0x140013cd7  lea     r8, aErrorWhileWait; "Error while waiting for system-context "...
0x140013cde  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013ce5  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013cea  test    r15d, r15d
0x140013ced  jle     short loc_140013CF9
0x140013cef  movzx   r15d, r15w
0x140013cf3  or      r15d, edi
0x140013cf6  test    r15d, r15d
0x140013cf9  js      loc_140013ED0
0x140013cff  xor     r15d, r15d
0x140013d02  call    cs:__imp_GetTickCount64
0x140013d09  nop     dword ptr [rax+rax+00h]
0x140013d0e  mov     rcx, rax
0x140013d11  sub     rcx, r12
0x140013d14  cmp     rcx, rax
0x140013d17  ja      short loc_140013D1E
0x140013d19  mov     r14, rcx
0x140013d1c  jmp     short loc_140013D2D
0x140013d1e  mov     eax, 80070216h
0x140013d23  mov     r15d, eax
0x140013d26  mov     ecx, eax
0x140013d28  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140013d2d  mov     ecx, r15d
0x140013d30  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140013d35  xor     ecx, ecx
0x140013d37  test    r15d, r15d
0x140013d3a  mov     eax, 493E0h
0x140013d3f  cmovs   r14, rax
0x140013d43  mov     rax, 624DD2F1A9FBE77h
0x140013d4d  mul     r14
0x140013d50  mov     r9, r14
0x140013d53  sub     r9, rdx
0x140013d56  shr     r9, 1
0x140013d59  add     r9, rdx
0x140013d5c  shr     r9, 9
0x140013d60  mov     rdx, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140013d67  lea     rax, [rdx-1]
0x140013d6b  xor     r15d, r15d
0x140013d6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013d72  cmovbe  rcx, rdx; hFile
0x140013d76  lea     r8, aWaitedDSeconds; "Waited [%d] seconds for system-context "...
0x140013d7d  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140013d84  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140013d89  lea     r9, [rbp+540h+var_548]
0x140013d8d  lea     r8, aCmdline; "CmdLine"
0x140013d94  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x140013d9b  call    ?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x140013da0  test    eax, eax
0x140013da2  jns     loc_140013BEE
0x140013da8  mov     ecx, 5DCh; dwMilliseconds
0x140013dad  call    cs:__imp_Sleep
0x140013db4  nop     dword ptr [rax+rax+00h]
0x140013db9  lea     r9, [rsp+640h+var_5F0]
0x140013dbe  lea     r8, [rbp+540h+hHandle]
0x140013dc2  lea     rcx, aGlobalMicrosof_4; "Global\\Microsoft.Windows.Setup.Rollbac"...
0x140013dc9  call    ?CreateMutexWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGHPEAPEAXPEAH@Z; CDlpHelpersT<CEmptyType>::CreateMutexWithAcl(ushort const *,int,void * *,int *)
0x140013dce  mov     r15d, eax
0x140013dd1  xor     r14d, r14d
  ... truncated ...
```
