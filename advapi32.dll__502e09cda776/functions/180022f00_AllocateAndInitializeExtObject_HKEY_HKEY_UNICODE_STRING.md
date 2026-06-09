# AllocateAndInitializeExtObject(HKEY__ *,HKEY__ *,_UNICODE_STRING *)

- ea: `0x180022f00`
- end: `0x180025362`
- name: `?AllocateAndInitializeExtObject@@YAPEAUEXT_OBJECT@@PEAUHKEY__@@0PEAU_UNICODE_STRING@@@Z`
- size: `9314`
- prototype: `struct EXT_OBJECT *(HKEY, HKEY, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022170`

## callees

- `0x1800019e0`
- `0x180002e84`
- `0x18000e7cc`
- `0x18000ecf0`
- `0x180022f00`
- `0x180029698`
- `0x18002a6a8`
- `0x18002f850`
- `0x18003e354`
- `0x18003fb18`
- `0x18003fd04`
- `0x18004165c`
- `0x180063c7c`
- `0x180063f10`
- `0x1800643d8`
- `0x180072042`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180024f2e`
- `msvcrt!_ultow_s` at `0x180024f2e`
- `msvcrt!wcstoul` at `0x180023de0`
- `msvcrt!wcstoul` at `0x180023e4b`
- `msvcrt!wcstoul` at `0x180023e97`
- `msvcrt!wcstoul` at `0x180023de0`
- `msvcrt!wcstoul` at `0x180023e4b`
- `msvcrt!wcstoul` at `0x180023e97`
- `ntdll!NtQueryValueKey` at `0x18002311c`
- `ntdll!NtQueryValueKey` at `0x1800235ae`
- `ntdll!NtQueryValueKey` at `0x180023a12`
- `ntdll!NtQueryValueKey` at `0x180023b0a`
- `ntdll!NtQueryValueKey` at `0x180023bf8`
- `ntdll!NtQueryValueKey` at `0x180023cf7`
- `ntdll!NtQueryValueKey` at `0x180023fb0`
- `ntdll!NtQueryValueKey` at `0x1800240b7`
- `ntdll!NtQueryValueKey` at `0x1800241af`
- `ntdll!NtQueryValueKey` at `0x180024272`
- `ntdll!NtQueryValueKey` at `0x1800243a7`
- `ntdll!NtQueryValueKey` at `0x18002462a`
- `ntdll!NtQueryValueKey` at `0x18002311c`
- `ntdll!NtQueryValueKey` at `0x1800235ae`
- `ntdll!NtQueryValueKey` at `0x180023a12`
- `ntdll!NtQueryValueKey` at `0x180023b0a`
- `ntdll!NtQueryValueKey` at `0x180023bf8`
- `ntdll!NtQueryValueKey` at `0x180023cf7`
- `ntdll!NtQueryValueKey` at `0x180023fb0`
- `ntdll!NtQueryValueKey` at `0x1800240b7`
- `ntdll!NtQueryValueKey` at `0x1800241af`
- `ntdll!NtQueryValueKey` at `0x180024272`
- `ntdll!NtQueryValueKey` at `0x1800243a7`
- `ntdll!NtQueryValueKey` at `0x18002462a`
- `ntdll!NtClose` at `0x1800248f0`
- `ntdll!NtClose` at `0x1800248f0`
- `ntdll!NtOpenThreadToken` at `0x180024f84`
- `ntdll!NtOpenThreadToken` at `0x180024f84`
- `ntdll!NtSetInformationThread` at `0x180024fbf`
- `ntdll!NtSetInformationThread` at `0x18002504c`
- `ntdll!NtSetInformationThread` at `0x180024fbf`
- `ntdll!NtSetInformationThread` at `0x18002504c`
- `ntdll!RtlInitUnicodeString` at `0x1800230bb`
- `ntdll!RtlInitUnicodeString` at `0x180023552`
- `ntdll!RtlInitUnicodeString` at `0x1800239b6`
- `ntdll!RtlInitUnicodeString` at `0x180023aa8`
- `ntdll!RtlInitUnicodeString` at `0x180023b9a`
- `ntdll!RtlInitUnicodeString` at `0x180023c91`
- `ntdll!RtlInitUnicodeString` at `0x180023f51`
- `ntdll!RtlInitUnicodeString` at `0x180024058`
- `ntdll!RtlInitUnicodeString` at `0x180024154`
- `ntdll!RtlInitUnicodeString` at `0x18002421a`
- `ntdll!RtlInitUnicodeString` at `0x180024347`
- `ntdll!RtlInitUnicodeString` at `0x1800245d5`
- `ntdll!RtlInitUnicodeString` at `0x1800230bb`
- `ntdll!RtlInitUnicodeString` at `0x180023552`
- `ntdll!RtlInitUnicodeString` at `0x1800239b6`
- `ntdll!RtlInitUnicodeString` at `0x180023aa8`
- `ntdll!RtlInitUnicodeString` at `0x180023b9a`
- `ntdll!RtlInitUnicodeString` at `0x180023c91`
- `ntdll!RtlInitUnicodeString` at `0x180023f51`
- `ntdll!RtlInitUnicodeString` at `0x180024058`
- `ntdll!RtlInitUnicodeString` at `0x180024154`
- `ntdll!RtlInitUnicodeString` at `0x18002421a`
- `ntdll!RtlInitUnicodeString` at `0x180024347`
- `ntdll!RtlInitUnicodeString` at `0x1800245d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024f0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024f0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024f69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024f69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024575`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024575`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800247cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800247cb`
- `KERNEL32!LocalFree` at `0x180023161`
- `KERNEL32!LocalFree` at `0x1800235f6`
- `KERNEL32!LocalFree` at `0x180023a59`
- `KERNEL32!LocalFree` at `0x180023b52`
- `KERNEL32!LocalFree` at `0x180023c40`
- `KERNEL32!LocalFree` at `0x180023d56`
- `KERNEL32!LocalFree` at `0x180023ff5`
- `KERNEL32!LocalFree` at `0x1800240fc`
- `KERNEL32!LocalFree` at `0x1800241d8`
- `KERNEL32!LocalFree` at `0x1800242bf`
- `KERNEL32!LocalFree` at `0x1800243f0`
- `KERNEL32!LocalFree` at `0x18002465c`
- `KERNEL32!LocalFree` at `0x18002475d`
- `KERNEL32!LocalFree` at `0x180024905`
- `KERNEL32!LocalFree` at `0x180024cad`
- `KERNEL32!LocalFree` at `0x1800251b2`
- `KERNEL32!LocalFree` at `0x1800251d9`
- `KERNEL32!LocalFree` at `0x180025204`
- `KERNEL32!LocalFree` at `0x180023161`
- `KERNEL32!LocalFree` at `0x1800235f6`
- `KERNEL32!LocalFree` at `0x180023a59`
- `KERNEL32!LocalFree` at `0x180023b52`
- `KERNEL32!LocalFree` at `0x180023c40`
- `KERNEL32!LocalFree` at `0x180023d56`
- `KERNEL32!LocalFree` at `0x180023ff5`
- `KERNEL32!LocalFree` at `0x1800240fc`
- `KERNEL32!LocalFree` at `0x1800241d8`
- `KERNEL32!LocalFree` at `0x1800242bf`
- `KERNEL32!LocalFree` at `0x1800243f0`
- `KERNEL32!LocalFree` at `0x18002465c`
- `KERNEL32!LocalFree` at `0x18002475d`
- `KERNEL32!LocalFree` at `0x180024905`
- `KERNEL32!LocalFree` at `0x180024cad`
- `KERNEL32!LocalFree` at `0x1800251b2`
- `KERNEL32!LocalFree` at `0x1800251d9`
- `KERNEL32!LocalFree` at `0x180025204`
- `KERNEL32!GetLastError` at `0x18002505c`
- `KERNEL32!GetLastError` at `0x180025095`
- `KERNEL32!GetLastError` at `0x1800250ad`
- `KERNEL32!GetLastError` at `0x18002505c`
- `KERNEL32!GetLastError` at `0x180025095`
- `KERNEL32!GetLastError` at `0x1800250ad`
- `KERNEL32!CloseHandle` at `0x180025071`
- `KERNEL32!CloseHandle` at `0x180025071`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800231cc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800231cc`
- `KERNEL32!CompareStringOrdinal` at `0x180022fb7`
- `KERNEL32!CompareStringOrdinal` at `0x180024838`
- `KERNEL32!CompareStringOrdinal` at `0x180022fb7`
- `KERNEL32!CompareStringOrdinal` at `0x180024838`
- `KERNEL32!CreateMutexW` at `0x180025022`
- `KERNEL32!CreateMutexW` at `0x180025022`
- `KERNEL32!SetLastError` at `0x180025155`
- `KERNEL32!SetLastError` at `0x180025155`

## string_xrefs

- `0x180023f2f`: `Keep Library Resident`
- `0x180023540`: `Open Timeout`
- `0x1800244fd`: `\Linkage`

## pseudocode

```c
struct EXT_OBJECT *__fastcall AllocateAndInitializeExtObject(HKEY a1, HKEY a2, struct _UNICODE_STRING *a3)
{
  unsigned __int16 *v3; // r12
  LPCWCH *v5; // rbx
  WCHAR *v6; // rax
  unsigned __int8 *v7; // r13
  __int128 v8; // xmm6
  char *v9; // r15
  int v10; // r14d
  unsigned int v11; // esi
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  NTSTATUS v14; // edi
  unsigned int *v15; // r8
  unsigned int LastError; // edi
  const WCHAR *v17; // r9
  unsigned __int64 v18; // rcx
  size_t v19; // rsi
  __int64 v20; // r13
  char *v21; // r15
  DWORD v22; // eax
  __int64 v23; // rsi
  __int64 v24; // rax
  unsigned __int8 *v25; // r15
  _QWORD *v26; // rcx
  HANDLE v27; // rbx
  int v28; // r14d
  unsigned int v29; // eax
  unsigned int v30; // esi
  unsigned __int8 *v31; // rsi
  __int64 v32; // r14
  unsigned int v33; // eax
  const wchar_t *v34; // r12
  unsigned __int8 *v35; // r15
  BOOL v36; // eax
  unsigned __int16 *v37; // rbx
  __int64 v38; // rax
  bool v39; // zf
  int v40; // eax
  const wchar_t *v41; // rcx
  _DWORD *v42; // rax
  _DWORD *v43; // rdi
  NTSTATUS v44; // ebx
  unsigned int v45; // eax
  unsigned __int16 *v46; // rbx
  __int64 v47; // rax
  int v48; // eax
  const wchar_t *v49; // rcx
  int v50; // esi
  __int64 v51; // rdi
  HKEY v52; // r13
  unsigned int *v53; // r8
  unsigned int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // r14
  unsigned __int16 *v57; // rdi
  int v58; // r8d
  __int64 v59; // rax
  int v60; // eax
  _DWORD *v61; // rax
  _DWORD *v62; // rdi
  NTSTATUS v63; // ebx
  unsigned int v64; // eax
  int v65; // esi
  _DWORD *v66; // rax
  HANDLE v67; // r12
  _DWORD *v68; // rdi
  NTSTATUS v69; // ebx
  unsigned int v70; // eax
  int v71; // esi
  _DWORD *v72; // rax
  _DWORD *v73; // rdi
  NTSTATUS v74; // ebx
  unsigned int v75; // eax
  WCHAR *v76; // r14
  int v77; // esi
  _DWORD *v78; // rax
  _DWORD *v79; // rdi
  NTSTATUS v80; // ebx
  ULONG v81; // r15d
  ULONG v82; // r15d
  unsigned int v83; // eax
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // r15
  WCHAR v86; // ax
  const wchar_t *v87; // rbx
  wchar_t *v88; // rdi
  unsigned int v89; // r15d
  unsigned int v90; // eax
  __int64 v91; // rcx
  __int64 v92; // rsi
  const WCHAR *v93; // r13
  unsigned int v94; // esi
  unsigned int v95; // eax
  __int64 v96; // rcx
  __int64 v97; // rax
  ULONG v98; // esi
  int v99; // r14d
  _DWORD *v100; // rax
  _DWORD *v101; // rdi
  NTSTATUS v102; // ebx
  unsigned int v103; // eax
  int v104; // r15d
  ULONG v105; // esi
  int v106; // r14d
  _DWORD *v107; // rax
  _DWORD *v108; // rdi
  NTSTATUS v109; // ebx
  unsigned int v110; // eax
  int v111; // r15d
  unsigned int *v112; // rax
  unsigned int *v113; // rbx
  NTSTATUS v114; // edi
  int v115; // r14d
  unsigned int v116; // esi
  _OWORD *v117; // rax
  _DWORD *v118; // rdi
  NTSTATUS v119; // ebx
  unsigned int v120; // eax
  __int64 v121; // rbx
  unsigned int v122; // r14d
  _DWORD *v123; // rax
  _DWORD *v124; // rsi
  NTSTATUS v125; // edi
  unsigned int v126; // eax
  unsigned __int16 *v127; // rdx
  int v128; // r14d
  __int64 v129; // rcx
  __int64 v130; // r8
  __int64 v131; // r10
  WCHAR *v132; // r9
  __int64 v133; // r11
  WCHAR *v134; // rcx
  unsigned __int64 v135; // rdx
  int v136; // r10d
  WCHAR *v137; // r9
  int v138; // r12d
  __int64 v139; // rcx
  const unsigned __int16 *v140; // r8
  WCHAR *v141; // rcx
  LSTATUS v142; // eax
  HKEY v143; // rsi
  unsigned int v144; // r15d
  _OWORD *v145; // rax
  _DWORD *v146; // rdi
  NTSTATUS v147; // esi
  unsigned int v148; // eax
  unsigned __int64 v149; // rdi
  void *v150; // rax
  unsigned int *v151; // r8
  unsigned int v152; // eax
  __int64 v153; // rsi
  __int64 v154; // rsi
  char *v155; // rdi
  unsigned __int8 *v156; // rax
  __int64 v157; // r8
  int v158; // ecx
  int v159; // edx
  unsigned __int8 *v160; // rax
  char *v161; // r8
  int v162; // ecx
  int v163; // edx
  unsigned __int8 *v164; // rax
  __int64 v165; // r8
  int v166; // ecx
  int v167; // edx
  unsigned __int64 v168; // rsi
  char *v169; // rax
  unsigned __int64 v170; // r9
  _BYTE *v171; // r13
  unsigned __int8 *v172; // r11
  __int64 v173; // r8
  unsigned __int64 v174; // rcx
  _BYTE *v175; // rdx
  __int64 v176; // r10
  __int64 v177; // r11
  int v178; // r8d
  _BYTE *v179; // rax
  unsigned __int64 v180; // rsi
  _BYTE *v181; // r9
  unsigned __int64 v182; // r10
  __int64 v183; // r8
  _BYTE *v184; // rcx
  _BYTE *v185; // rdi
  _BYTE *v186; // rdx
  __int64 v187; // r11
  __int64 v188; // rdi
  _BYTE *v189; // rax
  _BYTE *v190; // r13
  unsigned __int64 v191; // rsi
  unsigned __int64 v192; // r10
  unsigned __int8 *v193; // rdi
  __int64 v194; // r8
  _BYTE *v195; // rcx
  _BYTE *v196; // rdx
  __int64 v197; // r11
  __int64 v198; // rdi
  _BYTE *v199; // rax
  _WORD *v200; // r13
  unsigned __int64 v201; // rsi
  _WORD *v202; // r10
  unsigned __int64 v203; // rdx
  LPCWCH v204; // rdi
  __int64 v205; // rcx
  unsigned __int64 v206; // r8
  _WORD *v207; // r9
  __int64 v208; // r11
  __int64 v209; // rdi
  _WORD *v210; // rcx
  int v211; // r11d
  _WORD *v212; // r14
  unsigned __int64 v213; // rsi
  ULONG v214; // r13d
  void *v215; // rdx
  size_t v216; // r8
  unsigned __int64 v217; // rsi
  unsigned __int16 *v218; // rcx
  __int64 v219; // rax
  __int64 v220; // r10
  unsigned __int64 v221; // rdx
  _WORD *v222; // r8
  _WORD *v223; // rcx
  unsigned int v224; // eax
  WCHAR *v225; // rax
  __int64 v226; // r11
  unsigned __int16 *v227; // r8
  __int64 v228; // rdx
  __int64 v229; // rcx
  __int64 v230; // r10
  WCHAR *v231; // rcx
  __int64 v232; // r8
  WCHAR *v233; // r8
  unsigned __int16 *v234; // rbx
  __int64 v235; // rax
  const wchar_t *v236; // rcx
  unsigned __int64 v237; // rdi
  __int64 v238; // r9
  __int64 v239; // rdx
  WCHAR *v240; // rcx
  int v241; // r9d
  __int64 v242; // rcx
  DWORD CurrentProcessId; // eax
  HANDLE CurrentThread; // rax
  NTSTATUS v245; // eax
  BOOL v246; // ebx
  unsigned int v247; // edi
  DWORD v248; // eax
  int SD; // eax
  __int64 *v250; // rax
  int v251; // ebx
  char *v253; // rdx
  __int64 v254; // rax
  __int64 v255; // r8
  __int64 v256; // r9
  _WORD *v257; // rcx
  char *v258; // rax
  char *v259; // rcx
  ULONG v260; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v261; // [rsp+44h] [rbp-BCh] BYREF
  char *v262; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v263; // [rsp+50h] [rbp-B0h]
  int v264; // [rsp+58h] [rbp-A8h]
  int v265; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v266; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v267; // [rsp+68h] [rbp-98h] BYREF
  ULONG v268; // [rsp+70h] [rbp-90h] BYREF
  ULONG v269; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG v270; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h]
  ULONG v272; // [rsp+88h] [rbp-78h]
  HANDLE TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  ULONG v274; // [rsp+98h] [rbp-68h]
  HANDLE KeyHandle; // [rsp+A0h] [rbp-60h]
  __int64 v276; // [rsp+A8h] [rbp-58h]
  unsigned int v277; // [rsp+B0h] [rbp-50h]
  ULONG v278; // [rsp+B4h] [rbp-4Ch]
  unsigned __int8 *v279; // [rsp+B8h] [rbp-48h]
  HKEY phkResult; // [rsp+C0h] [rbp-40h] BYREF
  ULONG ResultLength; // [rsp+C8h] [rbp-38h] BYREF
  ULONG v282; // [rsp+CCh] [rbp-34h] BYREF
  ULONG v283; // [rsp+D0h] [rbp-30h] BYREF
  ULONG v284; // [rsp+D4h] [rbp-2Ch] BYREF
  ULONG v285; // [rsp+D8h] [rbp-28h] BYREF
  ULONG v286; // [rsp+DCh] [rbp-24h] BYREF
  ULONG v287; // [rsp+E0h] [rbp-20h] BYREF
  ULONG v288; // [rsp+E4h] [rbp-1Ch] BYREF
  int v289; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int8 *v290; // [rsp+F0h] [rbp-10h]
  struct _UNICODE_STRING *ThreadInformation; // [rsp+F8h] [rbp-8h] BYREF
  struct _SECURITY_ATTRIBUTES hKey; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpSrc; // [rsp+118h] [rbp+18h]
  HLOCAL hMem; // [rsp+120h] [rbp+20h]
  LPCWCH *v295; // [rsp+128h] [rbp+28h]
  LPCWCH lpString2; // [rsp+130h] [rbp+30h]
  struct _UNICODE_STRING DestinationString; // [rsp+138h] [rbp+38h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+148h] [rbp+48h] BYREF
  struct _UNICODE_STRING v299; // [rsp+158h] [rbp+58h] BYREF
  struct _UNICODE_STRING v300; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING v301; // [rsp+178h] [rbp+78h] BYREF
  struct _UNICODE_STRING v302; // [rsp+188h] [rbp+88h] BYREF
  struct _UNICODE_STRING v303; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING v304; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING v305; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _UNICODE_STRING v306; // [rsp+1C8h] [rbp+C8h] BYREF
  struct _UNICODE_STRING v307; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v308; // [rsp+1E8h] [rbp+E8h] BYREF
  char v309[16]; // [rsp+1F8h] [rbp+F8h] BYREF
  const char *v310; // [rsp+208h] [rbp+108h]
  __int64 v311; // [rsp+210h] [rbp+110h]
  const wchar_t *v312; // [rsp+218h] [rbp+118h]
  int v313; // [rsp+220h] [rbp+120h]
  int v314; // [rsp+224h] [rbp+124h]
  char v315[16]; // [rsp+228h] [rbp+128h] BYREF
  const char *v316; // [rsp+238h] [rbp+138h]
  __int64 v317; // [rsp+240h] [rbp+140h]
  const wchar_t *v318; // [rsp+248h] [rbp+148h]
  int v319; // [rsp+250h] [rbp+150h]
  int v320; // [rsp+254h] [rbp+154h]
  char v321[16]; // [rsp+258h] [rbp+158h] BYREF
  const char *v322; // [rsp+268h] [rbp+168h]
  __int64 v323; // [rsp+270h] [rbp+170h]
  const wchar_t *v324; // [rsp+278h] [rbp+178h]
  int v325; // [rsp+280h] [rbp+180h]
  int v326; // [rsp+284h] [rbp+184h]
  _DWORD v327[64]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t Buffer[32]; // [rsp+390h] [rbp+290h] BYREF
  WCHAR Name[576]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v3 = a3->Buffer;
  *(_QWORD *)&hKey.nLength = a1;
  ThreadInformation = a3;
  v272 = 0;
  v269 = 0;
  v274 = 0;
  v270 = 0;
  KeyHandle = a2;
  phkResult = 0;
  v263 = v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v3);
  v5 = (LPCWCH *)ExtensibleObjects;
  v295 = 0;
  hMem = ExtensibleObjects;
  if ( ExtensibleObjects )
  {
    while ( CompareStringOrdinal(v5[49], -1, v3, -1, 1) != 2 )
    {
      v295 = v5;
      v5 = (LPCWCH *)*v5;
      hMem = v5;
      if ( !v5 )
        goto LABEL_11;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids);
  }
LABEL_11:
  v6 = (WCHAR *)operator new(0x1708u, (const struct std::nothrow_t *)&std::nothrow);
  lpSrc = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x1708u);
    v7 = 0;
    v278 = dwExtCtrOpenProcWaitMs;
    v8 = 0;
    v268 = dwExtCtrOpenProcWaitMs;
    v277 = dwExtCtrOpenProcWaitMs;
    v9 = 0;
    v265 = dwExtCtrOpenProcWaitMs;
    v10 = 0;
    v262 = 0;
    Src = 0;
    v264 = 0;
    v11 = 1072;
    v289 = 1000;
    ResultLength = 0;
    v308 = 0;
    DestinationString = 0;
    if ( (unsigned __int64)a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = 6;
      goto LABEL_524;
    }
    RtlInitUnicodeString(&DestinationString, L"Library");
    ResultLength = 1088;
    v12 = operator new(0x440u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( v12 )
    {
      memset_0(v12, 0, 0x440u);
      v14 = NtQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, v13, 0x440u, &ResultLength);
      if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147483643 )
      {
        v10 = v13[1];
        v11 = v13[2];
        if ( v14 >= 0 )
        {
          memcpy_0((void *)lpSrc, v13 + 3, v11);
          v11 = v13[2];
          v14 = 0;
        }
      }
      LocalFree(v13);
      if ( v14 >= 0 )
      {
        LastError = 0;
        goto LABEL_22;
      }
    }
    else
    {
      v14 = -1073741801;
    }
    LastError = PerfpDosError(v14);
LABEL_22:
    if ( !LastError )
    {
      v17 = lpSrc;
      v18 = (unsigned __int64)v11 >> 1;
      v19 = (v11 + 8) & 0xFFFFFFF8;
      v20 = 528;
      lpSrc[v18] = 0;
      v21 = (char *)v17 + v19;
      lpString2 = (const WCHAR *)((char *)v17 + v19);
      if ( v10 == 2 )
      {
        v22 = ExpandEnvironmentStringsW(v17, (LPWSTR)((char *)v17 + v19), 0x218u);
        if ( v22 - 1 <= 0x217 )
        {
          v23 = 8;
          v24 = (2 * v22 + 9) & 0xFFFFFFF8;
          v25 = (unsigned __int8 *)&v21[v24];
          v290 = v25;
          v20 = v24 + 528;
          goto LABEL_28;
        }
        v26 = WPP_GLOBAL_Control;
        LastError = 1154;
      }
      else
      {
        if ( v10 == 1 )
        {
          memcpy_0((char *)v17 + v19, v17, v19);
          v25 = (unsigned __int8 *)&v21[v19];
          v20 = v19 + 528;
          v290 = v25;
          v23 = 8;
LABEL_28:
          v261 = 536;
          v27 = KeyHandle;
          v28 = 0;
          v29 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Open", v15, &v260, v25, &v261, 0);
          LastError = v29;
          if ( v29 )
          {
            v36 = v29 == 2 || v29 == 234;
          }
          else
          {
            if ( *v25 )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, (_DWORD)v263, (_DWORD)v25, (__int64)v263);
              v30 = v261 + 8;
              v25[v261] = 0;
              v23 = v30 & 0xFFFFFFF8;
              goto LABEL_71;
            }
            LastError = 1;
            v36 = 1;
          }
          v37 = v263;
          v264 = v36;
          if ( v263 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                (_DWORD)v263,
                LastError);
          }
          else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
              LastError);
          }
          if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
          {
            v311 = 5;
            v310 = "Open";
            if ( v37 )
            {
              v38 = -1;
              do
                v39 = v37[++v38] == 0;
              while ( !v39 );
              v40 = 2 * v38 + 2;
              v41 = v37;
            }
            else
            {
              v40 = 10;
              v41 = L"NULL";
            }
            v313 = v40;
            v312 = v41;
            v314 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)S_Perflib_Context,
              (unsigned int)PERFLIB_PROC_NAME_NOT_FOUND,
              (_DWORD)v15,
              3,
              (__int64)v309);
          }
          if ( LastError )
            goto LABEL_42;
          v27 = KeyHandle;
LABEL_71:
          v282 = 0;
          v20 += v23;
          ValueName = 0;
          RtlInitUnicodeString(&ValueName, L"Open Timeout");
          v282 = 20;
          v42 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
          v43 = v42;
          if ( v42 )
          {
            *(_OWORD *)v42 = 0;
            v42[4] = 0;
            v44 = NtQueryValueKey(v27, &ValueName, KeyValuePartialInformation, v42, 0x14u, &v282);
            if ( (int)(v44 + 0x80000000) < 0 || v44 == -2147483643 )
            {
              v28 = v43[1];
              if ( v44 >= 0 )
              {
                memcpy_0(&v265, v43 + 3, (unsigned int)v43[2]);
                v44 = 0;
                v277 = v265;
              }
            }
            LocalFree(v43);
            if ( v44 >= 0 )
            {
              v45 = 0;
              goto LABEL_80;
            }
          }
          else
          {
            v44 = -1073741801;
          }
          v45 = PerfpDosError(v44);
LABEL_80:
          if ( v45 || v28 != 4 )
          {
            v31 = &v25[v23];
            v279 = v31;
            v32 = 8;
            v277 = dwExtCtrOpenProcWaitMs;
LABEL_43:
            v261 = 536;
            v33 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Close", v15, &v260, v31, &v261, 0);
            LastError = v33;
            if ( v33 )
            {
              if ( v33 == 2 || v33 == 234 )
                v264 = 1;
            }
            else
            {
              if ( *v31 )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, (_DWORD)v15, (_DWORD)v31, (__int64)v263);
                v34 = L"NULL";
                v32 = (v261 + 8) & 0xFFFFFFF8;
                v35 = &v31[v32];
                goto LABEL_106;
              }
              LastError = 1;
              v264 = 1;
            }
            v46 = v263;
            if ( v263 )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                  (_DWORD)v263,
                  LastError);
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                LastError);
            }
            if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
            {
              v317 = 6;
              v316 = "Close";
              if ( v46 )
              {
                v47 = -1;
                do
                  v39 = v46[++v47] == 0;
                while ( !v39 );
                v48 = 2 * v47 + 2;
                v49 = v46;
                v34 = L"NULL";
              }
              else
              {
                v34 = L"NULL";
                v48 = 10;
                v49 = L"NULL";
              }
              v319 = v48;
              v318 = v49;
              v320 = 0;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)S_Perflib_Context,
                (unsigned int)PERFLIB_PROC_NAME_NOT_FOUND,
                (_DWORD)v15,
                3,
                (__int64)v315);
              goto LABEL_104;
            }
LABEL_103:
            v34 = L"NULL";
LABEL_104:
            if ( LastError )
              goto LABEL_510;
            v35 = v31 + 8;
LABEL_106:
            v50 = 0;
            TokenHandle = v35;
            v51 = v32 + v20;
            v52 = (HKEY)KeyHandle;
            v265 = 0;
            v266 = 0;
            v276 = v51;
            v261 = 536;
            if ( (unsigned int)PrivateRegQueryValueExT((HKEY)KeyHandle, L"Query", v15, &v260, v35, &v261, 0)
              && (v261 = 536, v54 = PrivateRegQueryValueExT(v52, L"Collect", v53, &v260, v35, &v261, 0),
                              (v55 = v54) != 0) )
            {
              v56 = 8;
              if ( v54 == 2 || v54 == 234 )
                v264 = 1;
            }
            else
            {
              v56 = (v261 + 8) & 0xFFFFFFF8;
              v276 = v56 + v51;
              if ( *v35 )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, (_DWORD)v53, (_DWORD)v35, (__int64)v263);
                goto LABEL_132;
              }
              v55 = 1;
              v264 = 1;
            }
            v57 = v263;
            if ( v263 )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                  (_DWORD)v263,
                  v55);
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v55);
            }
            if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
            {
              v323 = 8;
              v322 = "Collect";
              if ( v57 )
              {
                v59 = -1;
                do
                  v39 = v57[++v59] == 0;
                while ( !v39 );
                v60 = 2 * v59 + 2;
                v34 = v57;
              }
              else
              {
                v60 = 10;
              }
              v325 = v60;
              v324 = v34;
              v326 = 0;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)S_Perflib_Context,
                (unsigned int)PERFLIB_PROC_NAME_NOT_FOUND,
                v58,
                3,
                (__int64)v321);
            }
            if ( v55 )
            {
LABEL_144:
              v268 = 0;
              v65 = 0;
              v300 = 0;
              RtlInitUnicodeString(&v300, L"First Counter");
              v268 = 20;
              v66 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
              v67 = KeyHandle;
              v68 = v66;
              if ( v66 )
              {
                *(_OWORD *)v66 = 0;
                v66[4] = 0;
                v69 = NtQueryValueKey(v67, &v300, KeyValuePartialInformation, v66, 0x14u, &v268);
                if ( (int)(v69 + 0x80000000) < 0 || v69 == -2147483643 )
                {
                  v65 = v68[1];
                  if ( v69 >= 0 )
                  {
                    memcpy_0(&v269, v68 + 3, (unsigned int)v68[2]);
                    v69 = 0;
                    v272 = v269;
                  }
                }
                LocalFree(v68);
                if ( v69 >= 0 )
                {
                  v70 = 0;
LABEL_153:
                  if ( v70 || v65 != 4 )
                    v272 = 0;
                  v269 = 0;
                  v71 = 0;
                  v301 = 0;
                  RtlInitUnicodeString(&v301, L"Last Counter");
                  v269 = 20;
                  v72 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                  v73 = v72;
                  if ( v72 )
                  {
                    *(_OWORD *)v72 = 0;
                    v72[4] = 0;
                    v74 = NtQueryValueKey(v67, &v301, KeyValuePartialInformation, v72, 0x14u, &v269);
                    if ( (int)(v74 + 0x80000000) < 0 || v74 == -2147483643 )
                    {
                      v71 = v73[1];
                      if ( v74 >= 0 )
                      {
                        memcpy_0(&v270, v73 + 3, (unsigned int)v73[2]);
                        v74 = 0;
                        v274 = v270;
                      }
                    }
                    LocalFree(v73);
                    if ( v74 >= 0 )
                    {
                      v75 = 0;
LABEL_165:
                      if ( v75 || v71 != 4 )
                        v274 = 0;
                      v270 = 0;
                      v76 = (WCHAR *)&v35[v56];
                      v77 = 0;
                      v302 = 0;
                      RtlInitUnicodeString(&v302, L"Object List");
                      v270 = 1088;
                      v78 = operator new(0x440u, (const struct std::nothrow_t *)&std::nothrow);
                      v79 = v78;
                      if ( v78 )
                      {
                        memset_0(v78, 0, 0x440u);
                        v80 = NtQueryValueKey(v67, &v302, KeyValuePartialInformation, v79, 0x440u, &v270);
                        if ( (int)(v80 + 0x80000000) < 0 || v80 == -2147483643 )
                        {
                          v81 = v79[2];
                          v77 = v79[1];
                          v260 = v81;
                          if ( v80 >= 0 && v76 )
                          {
                            memcpy_0(v76, v79 + 3, v81);
                            v82 = v79[2];
                            v80 = 0;
                          }
                          else
                          {
                            v82 = v260;
                          }
                        }
                        else
                        {
                          v82 = 1072;
                        }
                        LocalFree(v79);
                        if ( v80 >= 0 )
                        {
                          v83 = 0;
                          goto LABEL_180;
                        }
                      }
                      else
                      {
                        v80 = -1073741801;
                        v82 = 1072;
                      }
                      v83 = PerfpDosError(v80);
LABEL_180:
                      if ( v83 )
                      {
                        *v76 = 0;
                        v93 = v76 + 4;
LABEL_209:
                        v98 = 0;
                        v260 = 0;
                        v284 = 0;
                        v303 = 0;
                        v99 = 0;
                        RtlInitUnicodeString(&v303, L"Keep Library Resident");
                        v284 = 20;
                        v100 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                        v101 = v100;
                        if ( v100 )
                        {
                          *(_OWORD *)v100 = 0;
                          v100[4] = 0;
                          v102 = NtQueryValueKey(v67, &v303, KeyValuePartialInformation, v100, 0x14u, &v284);
                          if ( (int)(v102 + 0x80000000) < 0 || v102 == -2147483643 )
                          {
                            v99 = v101[1];
                            if ( v102 >= 0 )
                            {
                              memcpy_0(&v260, v101 + 3, (unsigned int)v101[2]);
                              v98 = v260;
                              v102 = 0;
                            }
                          }
                          LocalFree(v101);
                          if ( v102 >= 0 )
                          {
                            v103 = 0;
LABEL_218:
                            v104 = v265;
                            if ( !v103 && v99 == 4 )
                            {
                              if ( v98 == 1 )
                                v104 = 4;
                              v265 = v104;
                            }
                            v105 = 0;
                            v260 = 0;
                            v285 = 0;
                            v304 = 0;
                            v106 = 0;
                            RtlInitUnicodeString(&v304, L"Collect Supports Metadata");
                            v285 = 20;
                            v107 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                            v108 = v107;
                            if ( v107 )
                            {
                              *(_OWORD *)v107 = 0;
                              v107[4] = 0;
                              v109 = NtQueryValueKey(v67, &v304, KeyValuePartialInformation, v107, 0x14u, &v285);
                              if ( (int)(v109 + 0x80000000) < 0 || v109 == -2147483643 )
                              {
                                v106 = v108[1];
                                if ( v109 >= 0 )
                                {
                                  memcpy_0(&v260, v108 + 3, (unsigned int)v108[2]);
                                  v105 = v260;
                                  v109 = 0;
                                }
                              }
                              LocalFree(v108);
                              if ( v109 >= 0 )
                              {
                                v110 = 0;
LABEL_232:
                                if ( !v110 && v106 == 4 && v105 == 1 )
                                  v265 = v104 | 0x80;
                                v111 = 0;
                                v305 = 0;
                                v286 = 0;
                                RtlInitUnicodeString(&v305, L"Error Count Limit");
                                v286 = 20;
                                v112 = (unsigned int *)operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                                v113 = v112;
                                if ( v112 )
                                {
                                  *(_OWORD *)v112 = 0;
                                  v112[4] = 0;
                                  v114 = NtQueryValueKey(v67, &v305, KeyValuePartialInformation, v112, 0x14u, &v286);
                                  if ( v114 >= 0 )
                                  {
                                    memcpy_0(&v289, v113 + 3, v113[2]);
                                    v114 = 0;
                                  }
                                  LocalFree(v113);
                                  if ( v114 >= 0 )
                                  {
LABEL_243:
                                    v287 = 0;
                                    v115 = 0;
                                    v116 = 16;
                                    v306 = 0;
                                    RtlInitUnicodeString(&v306, L"Library Validation Code");
                                    v287 = 32;
                                    v117 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
                                    v118 = v117;
                                    if ( v117 )
                                    {
                                      *v117 = 0;
                                      v117[1] = 0;
                                      v119 = NtQueryValueKey(v67, &v306, KeyValuePartialInformation, v117, 0x20u, &v287);
                                      if ( (int)(v119 + 0x80000000) < 0 || v119 == -2147483643 )
                                      {
                                        v115 = v118[1];
                                        v116 = v118[2];
                                        if ( v119 >= 0 )
                                        {
                                          memcpy_0(&v308, v118 + 3, v116);
                                          v8 = v308;
                                          v119 = 0;
                                        }
                                      }
                                      LocalFree(v118);
                                      if ( v119 >= 0 )
                                      {
                                        v120 = 0;
LABEL_252:
                                        if ( v120 || v115 != 3 || v116 != 16 )
                                        {
                                          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                                          {
                                            WPP_SF_S(
                                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                                              26,
                                              WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                              v263);
                                          }
                                          v8 = 0;
                                        }
                                        v121 = 0;
                                        v267 = 0;
                                        v288 = 0;
                                        v307 = 0;
                                        v122 = 8;
                                        RtlInitUnicodeString(&v307, L"Successful File Date");
                                        v288 = 24;
                                        v123 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                                        v124 = v123;
                                        if ( v123 )
                                        {
                                          *(_OWORD *)v123 = 0;
                                          *((_QWORD *)v123 + 2) = 0;
                                          v125 = NtQueryValueKey(
                                                   v67,
                                                   &v307,
                                                   KeyValuePartialInformation,
                                                   v123,
                                                   0x18u,
                                                   &v288);
                                          if ( (int)(v125 + 0x80000000) < 0 || v125 == -2147483643 )
                                          {
                                            v111 = v124[1];
                                            v122 = v124[2];
                                            if ( v125 >= 0 )
                                            {
                                              memcpy_0(&v267, v124 + 3, v122);
                                              v121 = v267;
                                              v125 = 0;
                                            }
                                          }
                                          LocalFree(v124);
                                          if ( v125 >= 0 )
                                          {
                                            v126 = 0;
                                            goto LABEL_268;
                                          }
                                        }
                                        else
                                        {
                                          v125 = -1073741801;
                                        }
                                        v126 = PerfpDosError(v125);
LABEL_268:
                                        if ( v126 || v111 != 3 || v122 != 8 )
                                        {
                                          v121 = -1;
                                          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                                          {
                                            WPP_SF_(
                                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                                              27,
                                              WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids);
                                          }
                                        }
                                        v127 = v263;
                                        v128 = 0;
                                        v129 = 2147483646;
                                        v130 = 536;
                                        v131 = 0;
                                        v132 = (WCHAR *)v93;
                                        do
                                        {
                                          if ( !v129 )
                                            break;
                                          if ( !*v127 )
                                            break;
                                          *v132++ = *v127++;
                                          --v129;
                                          ++v131;
                                          --v130;
                                        }
                                        while ( v130 );
                                        v133 = v131 - 1;
                                        v134 = v132 - 1;
                                        v135 = 536;
                                        if ( v130 )
                                        {
                                          v133 = v131;
                                          v134 = v132;
                                        }
                                        LOWORD(v136) = 122;
                                        if ( v130 )
                                          LOWORD(v136) = 0;
                                        *v134 = 0;
                                        if ( v130 )
                                        {
                                          v135 = 536 - v133;
                                          v137 = (WCHAR *)&v93[v133];
                                        }
                                        else
                                        {
                                          v137 = (WCHAR *)v93;
                                          *v93 = 0;
                                        }
                                        LOWORD(v138) = 87;
                                        if ( !v130 )
                                        {
                                          phkResult = 0;
                                          v267 = v135;
                                          goto LABEL_301;
                                        }
                                        if ( v135 )
                                        {
                                          if ( v135 <= 0x7FFFFFFF )
                                          {
                                            v139 = 2147483646;
                                            v267 = v135;
                                            v140 = L"\\Linkage";
                                            do
                                            {
                                              if ( !v139 )
                                                break;
                                              if ( !*v140 )
                                                break;
                                              *v137++ = *v140++;
                                              --v139;
                                              --v135;
                                            }
                                            while ( v135 );
                                            v141 = v137 - 1;
                                            v136 = -2147024774;
                                            if ( v135 )
                                            {
                                              v141 = v137;
                                              v136 = 0;
                                            }
                                            *v141 = 0;
LABEL_298:
                                            phkResult = 0;
                                            if ( v136 >= 0 )
                                            {
                                              v142 = RegOpenKeyExW(*(HKEY *)&hKey.nLength, v93, 0, 0x20019u, &phkResult);
LABEL_302:
                                              if ( v142 || (v143 = phkResult) == 0 )
                                              {
                                                v154 = v276;
                                                v7 = 0;
                                                Src = 0;
                                                v260 = 0;
                                                goto LABEL_333;
                                              }
                                              v7 = 0;
                                              v261 = 0;
                                              v260 = 0;
                                              v144 = 0;
                                              *(_OWORD *)&hKey.nLength = 0;
                                              if ( (unsigned __int64)phkResult - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                                                goto LABEL_328;
                                              RtlInitUnicodeString((PUNICODE_STRING)&hKey, L"Export");
                                              v260 = 16;
                                              v145 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                                              v146 = v145;
                                              if ( v145 )
                                              {
                                                *v145 = 0;
                                                v147 = NtQueryValueKey(
                                                         v143,
                                                         (PUNICODE_STRING)&hKey,
                                                         KeyValuePartialInformation,
                                                         v145,
                                                         0x10u,
                                                         &v260);
                                                if ( (int)(v147 + 0x80000000) < 0 || v147 == -2147483643 )
                                                {
                                                  v144 = v146[2];
                                                  v128 = v146[1];
                                                  v261 = v144;
                                                }
                                                LocalFree(v146);
                                                if ( v147 >= 0 )
                                                {
                                                  v148 = 0;
                                                  goto LABEL_313;
                                                }
                                              }
                                              else
                                              {
                                                v147 = -1073741801;
                                              }
                                              v148 = PerfpDosError(v147);
LABEL_313:
                                              if ( (!v148 || v148 == 234) && (v128 == 1 || v128 == 7) )
                                              {
                                                v149 = 2 * (((unsigned __int64)(v144 + 1) >> 1) + 1);
                                                if ( !is_mul_ok(((unsigned __int64)(v144 + 1) >> 1) + 1, 2u) )
                                                  v149 = -1;
                                                v150 = operator new(v149, (const struct std::nothrow_t *)&std::nothrow);
                                                Src = v150;
                                                v7 = (unsigned __int8 *)v150;
                                                if ( v150 )
                                                {
                                                  memset_0(v150, 0, v149);
                                                  v260 = 0;
                                                  LastError = PrivateRegQueryValueExT(
                                                                phkResult,
                                                                L"Export",
                                                                v151,
                                                                &v260,
                                                                v7,
                                                                &v261,
                                                                1);
                                                  if ( !LastError && (v260 == 1 || v260 == 7) )
                                                  {
                                                    v152 = v261 + 9;
                                                    v260 = v261 + 2;
                                                    v153 = v276;
                                                    *(_WORD *)&v7[2 * ((unsigned __int64)v261 >> 1)] = 0;
                                                    v154 = (v152 & 0xFFFFFFF8) + v153;
                                                    goto LABEL_330;
                                                  }
                                                  LocalFree(v7);
                                                  v7 = 0;
                                                  Src = 0;
                                                  v260 = 0;
                                                  LastError = 0;
                                                }
                                                else
                                                {
                                                  Src = 0;
                                                  LastError = 14;
                                                  v260 = 0;
                                                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                  {
                                                    WPP_SF_d(
                                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                      28,
                                                      WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                                      v144);
                                                  }
                                                }
LABEL_329:
                                                v154 = v276;
LABEL_330:
                                                RegCloseKey(phkResult);
                                                if ( !LastError )
                                                {
LABEL_333:
                                                  v155 = (char *)hMem;
                                                  if ( hMem )
                                                  {
                                                    if ( *((_DWORD *)hMem + 93) == v272
                                                      && *((_DWORD *)hMem + 94) == v274
                                                      && CompareStringOrdinal(
                                                           *((LPCWCH *)hMem + 12),
                                                           -1,
                                                           lpString2,
                                                           -1,
                                                           1) == 2 )
                                                    {
                                                      v156 = (unsigned __int8 *)*((_QWORD *)v155 + 3);
                                                      v157 = v290 - v156;
                                                      do
                                                      {
                                                        v158 = v156[v157];
                                                        v159 = *v156 - v158;
                                                        if ( v159 )
                                                          break;
                                                        ++v156;
                                                      }
                                                      while ( v158 );
                                                      if ( !v159 )
                                                      {
                                                        v160 = (unsigned __int8 *)*((_QWORD *)v155 + 6);
                                                        v161 = (char *)((_BYTE *)TokenHandle - v160);
                                                        do
                                                        {
                                                          v162 = (unsigned __int8)v161[(_QWORD)v160];
                                                          v163 = *v160 - v162;
                                                          if ( v163 )
                                                            break;
                                                          ++v160;
                                                        }
                                                        while ( v162 );
                                                        if ( !v163 )
                                                        {
                                                          v164 = (unsigned __int8 *)*((_QWORD *)v155 + 9);
                                                          v165 = v279 - v164;
                                                          do
                                                          {
                                                            v166 = v164[v165];
                                                            v167 = *v164 - v166;
                                                            if ( v167 )
                                                              break;
                                                            ++v164;
                                                          }
                                                          while ( v166 );
                                                          if ( !v167 )
                                                          {
                                                            v9 = v155;
                                                            v155[524] = 0;
                                                            goto LABEL_513;
                                                          }
                                                        }
                                                      }
                                                    }
                                                    if ( v295 )
                                                      *v295 = *(LPCWCH *)v155;
                                                    else
                                                      ExtensibleObjects = *(HLOCAL *)v155;
                                                    CloseExtObjectLibrary((struct EXT_OBJECT *)v155, 1);
                                                    NtClose(*((HANDLE *)v155 + 13));
                                                    --NumExtensibleObjects;
                                                    LocalFree(v155);
                                                  }
                                                  v168 = ((ThreadInformation->MaximumLength + 7LL) & 0xFFFFFFF8LL)
                                                       + v154;
                                                  v169 = (char *)operator new(
                                                                   v168,
                                                                   (const struct std::nothrow_t *)&std::nothrow);
                                                  v9 = v169;
                                                  if ( !v169 )
                                                  {
                                                    LastError = 14;
                                                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                    {
                                                      WPP_SF_d(
                                                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                        29,
                                                        WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                                        (unsigned int)v168);
                                                    }
                                                    v3 = v263;
                                                    goto LABEL_496;
                                                  }
                                                  memset_0(v169, 0, v168);
                                                  v170 = v168 - 528;
                                                  v262 = v9;
                                                  v171 = v9 + 528;
                                                  *((_QWORD *)v9 + 3) = v9 + 528;
                                                  if ( v168 == 528 )
                                                    goto LABEL_484;
                                                  if ( v170 > 0x7FFFFFFF )
                                                  {
                                                    *v171 = 0;
                                                    goto LABEL_509;
                                                  }
                                                  v172 = v290;
                                                  v173 = 2147483646;
                                                  v262 = v9;
                                                  v174 = v168 - 528;
                                                  v175 = v9 + 528;
                                                  v176 = 0;
                                                  do
                                                  {
                                                    if ( !v173 )
                                                      break;
                                                    if ( !*v172 )
                                                      break;
                                                    *v175++ = *v172++;
                                                    --v173;
                                                    ++v176;
                                                    --v174;
                                                  }
                                                  while ( v174 );
                                                  v177 = v176 - 1;
                                                  v178 = -2147024774;
                                                  if ( v174 )
                                                  {
                                                    v177 = v176;
                                                    v178 = 0;
                                                  }
                                                  v179 = v175 - 1;
                                                  if ( v174 )
                                                    v179 = v175;
                                                  *v179 = 0;
                                                  if ( v178 >= 0 )
                                                  {
                                                    v171 += v177;
                                                    v170 -= v177;
                                                    v262 = v9;
                                                  }
                                                  else
                                                  {
                                                    *v171 = 0;
                                                  }
                                                  v180 = v170;
                                                  if ( v178 < 0 )
                                                    goto LABEL_508;
                                                  v181 = (_BYTE *)((unsigned __int64)(v171 + 8) & 0xFFFFFFFFFFFFFFF8uLL);
                                                  v262 = v9;
                                                  *((_DWORD *)v9 + 15) = v277;
                                                  *((_QWORD *)v9 + 6) = v181;
                                                  v182 = (unsigned __int64)&v171[v180 - (_QWORD)v181];
                                                  if ( v182 )
                                                  {
                                                    if ( v182 > 0x7FFFFFFF )
                                                    {
LABEL_489:
                                                      *v181 = 0;
                                                      goto LABEL_490;
                                                    }
                                                    v183 = 2147483646;
                                                    v184 = &v171[v180 - (_QWORD)v181];
                                                    v185 = TokenHandle;
                                                    v186 = (_BYTE *)((unsigned __int64)(v171 + 8) & 0xFFFFFFFFFFFFFFF8uLL);
                                                    v187 = 0;
                                                    do
                                                    {
                                                      if ( !v183 )
                                                        break;
                                                      if ( !*v185 )
                                                        break;
                                                      *v186++ = *v185++;
                                                      --v183;
                                                      ++v187;
                                                      --v184;
                                                    }
                                                    while ( v184 );
                                                    v188 = v187 - 1;
                                                    v178 = -2147024774;
                                                    if ( v184 )
                                                    {
                                                      v188 = v187;
                                                      v178 = 0;
                                                    }
                                                    v189 = v186 - 1;
                                                    if ( v184 )
                                                      v189 = v186;
                                                    *v189 = 0;
                                                    if ( v178 >= 0 )
                                                    {
                                                      v181 += v188;
                                                      v182 -= v188;
                                                      v262 = v9;
                                                    }
                                                    else
                                                    {
                                                      *v181 = 0;
                                                    }
                                                    v190 = v181;
                                                    v191 = v182;
                                                    if ( v178 < 0 )
                                                      goto LABEL_508;
                                                    v181 = (_BYTE *)((unsigned __int64)(v181 + 8) & 0xFFFFFFFFFFFFFFF8uLL);
                                                    v262 = v9;
                                                    *((_DWORD *)v9 + 14) = v278;
                                                    *((_QWORD *)v9 + 9) = v181;
                                                    v192 = (unsigned __int64)&v190[v182 - (_QWORD)v181];
                                                    if ( v192 )
                                                    {
                                                      if ( v192 <= 0x7FFFFFFF )
                                                      {
                                                        v193 = v279;
                                                        v194 = 2147483646;
                                                        v195 = &v190[v191 - (_QWORD)v181];
                                                        v196 = (_BYTE *)((unsigned __int64)(v190 + 8)
                                                                       & 0xFFFFFFFFFFFFFFF8uLL);
                                                        v197 = 0;
                                                        do
                                                        {
                                                          if ( !v194 )
                                                            break;
                                                          if ( !*v193 )
                                                            break;
                                                          *v196++ = *v193++;
                                                          --v194;
                                                          ++v197;
                                                          --v195;
                                                        }
                                                        while ( v195 );
                                                        v198 = v197 - 1;
                                                        v178 = -2147024774;
                                                        if ( v195 )
                                                        {
                                                          v198 = v197;
                                                          v178 = 0;
                                                        }
                                                        v199 = v196 - 1;
                                                        if ( v195 )
                                                          v199 = v196;
                                                        *v199 = 0;
                                                        if ( v178 >= 0 )
                                                        {
                                                          v181 += v198;
                                                          v262 = v9;
                                                          v192 -= v198;
                                                        }
                                                        else
                                                        {
                                                          *v181 = 0;
                                                        }
                                                        v200 = v181;
                                                        v201 = v192;
                                                        if ( v178 >= 0 )
                                                        {
                                                          v262 = v9;
                                                          v202 = (_WORD *)((unsigned __int64)(v181 + 8)
                                                                         & 0xFFFFFFFFFFFFFFF8uLL);
                                                          *((_QWORD *)v9 + 12) = v202;
                                                          v203 = (unsigned __int64)&v181[v201 - (_QWORD)v202] >> 1;
                                                          if ( v203 )
                                                          {
                                                            if ( v203 <= 0x7FFFFFFF )
                                                            {
                                                              v204 = lpString2;
                                                              v205 = 2147483646;
                                                              v206 = (unsigned __int64)&v181[v201 - (_QWORD)v202] >> 1;
                                                              v207 = (_WORD *)((unsigned __int64)(v181 + 8)
                                                                             & 0xFFFFFFFFFFFFFFF8uLL);
                                                              v208 = 0;
                                                              do
                                                              {
                                                                if ( !v205 )
                                                                  break;
                                                                if ( !*v204 )
                                                                  break;
                                                                *v207++ = *v204++;
                                                                --v205;
                                                                ++v208;
                                                                --v206;
                                                              }
                                                              while ( v206 );
                                                              v209 = v208 - 1;
                                                              v210 = v207 - 1;
                                                              if ( v206 )
                                                                v209 = v208;
                                                              v211 = -2147024774;
                                                              if ( v206 )
                                                              {
                                                                v210 = v207;
                                                                v211 = 0;
                                                              }
                                                              *v210 = 0;
                                                              if ( v206 )
                                                              {
                                                                v202 += v209;
                                                                v203 -= v209;
                                                              }
                                                              else
                                                              {
                                                                *v202 = 0;
                                                                v262 = v9;
                                                                if ( v211 != -2147024774 )
                                                                {
LABEL_412:
                                                                  if ( v211 < 0 )
                                                                  {
                                                                    LOWORD(v138) = v211;
LABEL_509:
                                                                    LastError = (unsigned __int16)v138;
                                                                    goto LABEL_510;
                                                                  }
                                                                  v262 = v9;
                                                                  v212 = (_WORD *)(((unsigned __int64)v200 + 23)
                                                                                 & 0xFFFFFFFFFFFFFFF8uLL);
                                                                  v213 = (unsigned __int64)v200
                                                                       + 2 * v201
                                                                       - (_QWORD)v212;
                                                                  if ( Src )
                                                                  {
                                                                    v214 = v260;
                                                                    v215 = Src;
                                                                    v216 = v260;
                                                                    *((_QWORD *)v9 + 4) = v212;
                                                                    memcpy_0(v212, v215, v216);
                                                                    v212 = (_WORD *)(((unsigned __int64)&v212[((unsigned __int64)v214 >> 1) + 3]
                                                                                    + 1)
                                                                                   & 0xFFFFFFFFFFFFFFF8uLL);
                                                                    LocalFree(Src);
                                                                    Src = 0;
                                                                    v213 -= (v214 + 7) & 0xFFFFFFF8;
                                                                  }
                                                                  v217 = v213 >> 1;
                                                                  *((_QWORD *)v9 + 49) = v212;
                                                                  if ( v217 )
                                                                  {
                                                                    if ( v217 <= 0x7FFFFFFF )
                                                                    {
                                                                      v218 = v263;
                                                                      v219 = 2147483646;
                                                                      v220 = 0;
                                                                      v221 = v217;
                                                                      v222 = v212;
                                                                      do
                                                                      {
                                                                        if ( !v219 )
                                                                          break;
                                                                        if ( !*v218 )
                                                                          break;
                                                                        *v222++ = *v218++;
                                                                        --v219;
                                                                        ++v220;
                                                                        --v221;
                                                                      }
                                                                      while ( v221 );
                                                                      v223 = v222 - 1;
                                                                      v138 = -2147024774;
                                                                      if ( v221 )
                                                                      {
                                                                        v223 = v222;
                                                                        v138 = 0;
                                                                      }
                                                                      *v223 = 0;
                                                                      if ( !v221 )
                                                                      {
                                                                        *v212 = 0;
                                                                        v262 = v9;
                                                                      }
                                                                      if ( v138 < 0 )
                                                                        goto LABEL_509;
                                                                      *((_DWORD *)v9 + 95) = v265;
                                                                      *((_QWORD *)v9 + 13) = KeyHandle;
                                                                      *((_DWORD *)v9 + 93) = v272;
                                                                      *((_DWORD *)v9 + 94) = v274;
                                                                      v224 = v266;
                                                                      *((_QWORD *)v9 + 53) = v121;
                                                                      *((_DWORD *)v9 + 96) = 1;
                                                                      *(_OWORD *)(v9 + 408) = v8;
                                                                      if ( v224 )
                                                                      {
                                                                        *((_DWORD *)v9 + 28) = v224;
                                                                        memcpy_0(v9 + 116, v327, 4LL * v224);
                                                                      }
                                                                      v3 = v263;
                                                                      v225 = Name;
                                                                      v226 = 536;
                                                                      *((_QWORD *)v9 + 50) = 0;
                                                                      v227 = v3;
                                                                      v228 = 536;
                                                                      v229 = 2147483646;
                                                                      v230 = 0;
                                                                      do
                                                                      {
                                                                        if ( !v229 )
                                                                          break;
                                                                        if ( !*v227 )
                                                                          break;
                                                                        *v225++ = *v227++;
                                                                        --v229;
                                                                        ++v230;
                                                                        --v228;
                                                                      }
                                                                      while ( v228 );
                                                                      v231 = v225 - 1;
                                                                      v232 = v230 - 1;
                                                                      if ( v228 )
                                                                      {
                                                                        v231 = v225;
                                                                        v232 = v230;
                                                                      }
                                                                      *v231 = 0;
                                                                      if ( v228 )
                                                                      {
                                                                        v226 = 536 - v232;
                                                                        v233 = &Name[v232];
                                                                      }
                                                                      else
                                                                      {
                                                                        v233 = Name;
                                                                        Name[0] = 0;
                                                                      }
                                                                      if ( !v228 )
                                                                      {
                                                                        v237 = v226;
                                                                        goto LABEL_458;
                                                                      }
                                                                      v262 = v9;
                                                                      v234 = v233;
                                                                      if ( (unsigned __int64)(v226 - 1) > 0x7FFFFFFE )
                                                                      {
                                                                        v237 = v226;
                                                                        if ( v226 )
                                                                          *v233 = 0;
                                                                      }
                                                                      else
                                                                      {
                                                                        v235 = 2147483646;
                                                                        v236 = L"_Perf_Library_Lock_PID_";
                                                                        v237 = v226;
                                                                        v238 = 0;
                                                                        do
                                                                        {
                                                                          if ( !v235 )
                                                                            break;
                                                                          if ( !*v236 )
                                                                            break;
                                                                          *v233++ = *v236++;
                                                                          --v235;
                                                                          ++v238;
                                                                          --v226;
                                                                        }
                                                                        while ( v226 );
                                                                        v239 = v238 - 1;
                                                                        v240 = v233 - 1;
                                                                        if ( v226 )
                                                                        {
                                                                          v239 = v238;
                                                                          v240 = v233;
                                                                        }
                                                                        v241 = -2147024774;
                                                                        if ( v226 )
                                                                          v241 = 0;
                                                                        *v240 = 0;
                                                                        v233 = &v234[v239];
                                                                        if ( v226 )
                                                                        {
                                                                          v237 -= v239;
                                                                          goto LABEL_458;
                                                                        }
                                                                        v242 = v237 & 0x7FFFFFFFFFFFFFFFLL;
                                                                        if ( (v237 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
                                                                        {
                                                                          v233 = v234;
                                                                          *v234 = 0;
                                                                        }
                                                                        else
                                                                        {
                                                                          v242 = v237 - v239;
                                                                        }
                                                                        if ( v241 == -2147024774 )
                                                                        {
                                                                          v237 = v242;
LABEL_458:
                                                                          v234 = v233;
                                                                        }
                                                                      }
                                                                      CurrentProcessId = GetCurrentProcessId();
                                                                      _ultow_s(CurrentProcessId, Buffer, 0x20u, 16);
                                                                      if ( (int)StringCchCopyW(v234, v237, Buffer) < 0 )
                                                                        Buffer[0] = 0;
                                                                      TokenHandle = 0;
                                                                      memset(&hKey, 0, sizeof(hKey));
                                                                      CurrentThread = GetCurrentThread();
                                                                      v245 = NtOpenThreadToken(
                                                                               CurrentThread,
                                                                               4u,
                                                                               1u,
                                                                               &TokenHandle);
                                                                      if ( v245 >= 0 )
                                                                      {
                                                                        ThreadInformation = 0;
                                                                        v247 = 0;
                                                                        v246 = NtSetInformationThread(
                                                                                 (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                                                                 ThreadImpersonationToken,
                                                                                 &ThreadInformation,
                                                                                 8u) >= 0;
                                                                      }
                                                                      else
                                                                      {
                                                                        v246 = 0;
                                                                        v247 = PerfpDosError(v245);
                                                                      }
                                                                      v248 = g_SizeSD;
                                                                      if ( g_SizeSD )
                                                                      {
                                                                        hKey.bInheritHandle = 0;
                                                                      }
                                                                      else
                                                                      {
                                                                        SD = PerflibCreateSD(v247);
                                                                        hKey.bInheritHandle = 0;
                                                                        if ( !SD )
                                                                        {
                                                                          hKey.nLength = 92;
                                                                          v250 = qword_180091290;
LABEL_470:
                                                                          hKey.lpSecurityDescriptor = v250;
                                                                          *((_QWORD *)v9 + 1) = CreateMutexW(
                                                                                                  &hKey,
                                                                                                  0,
                                                                                                  Name);
                                                                          if ( v246
                                                                            && NtSetInformationThread(
                                                                                 (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                                                                 ThreadImpersonationToken,
                                                                                 &TokenHandle,
                                                                                 8u) < 0 )
                                                                          {
                                                                            GetLastError();
                                                                          }
                                                                          if ( TokenHandle )
                                                                            CloseHandle(TokenHandle);
                                                                          *((_DWORD *)v9 + 120) = v289;
                                                                          v9[524] = 1;
                                                                          if ( *((_QWORD *)v9 + 1)
                                                                            && GetLastError() == 183 )
                                                                          {
                                                                            LastError = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            LastError = GetLastError();
                                                                          }
                                                                          if ( !*((_QWORD *)v9 + 1) )
                                                                          {
                                                                            if ( LastError )
                                                                            {
LABEL_527:
                                                                              v9 = v262;
                                                                              v7 = (unsigned __int8 *)Src;
LABEL_496:
                                                                              SetLastError(LastError);
                                                                              v251 = v264;
                                                                              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28)
                                                                                  & 4) != 0
                                                                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                                              {
                                                                                WPP_SF_Sd(
                                                                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                                                  30,
                                                                                  (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                                                                  (_DWORD)v3,
                                                                                  v264);
                                                                              }
                                                                              if ( v251 )
                                                                                DisableLibrary((HKEY)KeyHandle, v3, 1u);
                                                                              if ( v9 )
                                                                              {
                                                                                LocalFree(v9);
                                                                                v9 = 0;
                                                                              }
                                                                              goto LABEL_503;
                                                                            }
                                                                            LastError = 14;
                                                                          }
LABEL_511:
                                                                          if ( !LastError )
                                                                          {
                                                                            v9 = v262;
                                                                            v7 = (unsigned __int8 *)Src;
LABEL_513:
                                                                            v253 = (char *)lpPerflibSectionAddr;
                                                                            if ( lpPerflibSectionAddr )
                                                                            {
                                                                              if ( *(_DWORD *)lpPerflibSectionAddr >= *((_DWORD *)lpPerflibSectionAddr + 1) )
                                                                              {
                                                                                ++*((_DWORD *)lpPerflibSectionAddr + 2);
                                                                                *((_QWORD *)v9 + 54) = 0;
                                                                              }
                                                                              else
                                                                              {
                                                                                v254 = (unsigned int)(*(_DWORD *)lpPerflibSectionAddr + 1);
                                                                                v255 = 2147483646;
                                                                                *(_DWORD *)lpPerflibSectionAddr = v254;
                                                                                v256 = 32;
                                                                                v257 = (_WORD *)*((_QWORD *)v9 + 49);
                                                                                v258 = &v253[128 * v254];
                                                                                *((_QWORD *)v9 + 54) = v258;
                                                                                do
                                                                                {
                                                                                  if ( !v255 )
                                                                                    break;
                                                                                  if ( !*v257 )
                                                                                    break;
                                                                                  *(_WORD *)v258 = *v257++;
                                                                                  v258 += 2;
                                                                                  --v255;
                                                                                  --v256;
                                                                                }
                                                                                while ( v256 );
                                                                                v259 = v258 - 2;
                                                                                if ( v256 )
                                                                                  v259 = v258;
                                                                                *(_WORD *)v259 = 0;
                                                                              }
                                                                            }
LABEL_503:
                                                                            if ( v7 )
                                                                              LocalFree(v7);
                                                                            if ( v9 )
                                                                            {
                                                                              *((_QWORD *)v9 + 62) = v9 + 488;
                                                                              *((_QWORD *)v9 + 61) = v9 + 488;
                                                                            }
                                                                            LocalFree((HLOCAL)lpSrc);
                                                                            return (struct EXT_OBJECT *)v9;
                                                                          }
                                                                          goto LABEL_527;
                                                                        }
                                                                        v248 = g_SizeSD;
                                                                      }
                                                                      hKey.nLength = v248;
                                                                      v250 = (__int64 *)&g_RuntimeSD;
                                                                      goto LABEL_470;
                                                                    }
                                                                    *v212 = 0;
                                                                  }
LABEL_484:
                                                                  v262 = v9;
                                                                  goto LABEL_509;
                                                                }
                                                              }
                                                              v200 = v202;
                                                              v201 = v203;
                                                              goto LABEL_412;
                                                            }
                                                            *v202 = 0;
                                                          }
                                                          v262 = v9;
                                                          goto LABEL_509;
                                                        }
LABEL_508:
                                                        LOWORD(v138) = v178;
                                                        goto LABEL_509;
                                                      }
                                                      goto LABEL_489;
                                                    }
                                                  }
LABEL_490:
                                                  v262 = v9;
                                                  goto LABEL_509;
                                                }
LABEL_510:
                                                v3 = v263;
                                                goto LABEL_511;
                                              }
LABEL_328:
                                              v260 = 0;
                                              LastError = 0;
                                              Src = 0;
                                              goto LABEL_329;
                                            }
LABEL_301:
                                            v142 = (unsigned __int16)v136;
                                            goto LABEL_302;
                                          }
                                          v136 = -2147024809;
                                          *v137 = 0;
                                        }
                                        else
                                        {
                                          v136 = -2147024809;
                                        }
                                        v267 = v135;
                                        goto LABEL_298;
                                      }
                                    }
                                    else
                                    {
                                      v119 = -1073741801;
                                    }
                                    v120 = PerfpDosError(v119);
                                    goto LABEL_252;
                                  }
                                }
                                else
                                {
                                  v114 = -1073741801;
                                }
                                PerfpDosError(v114);
                                goto LABEL_243;
                              }
                            }
                            else
                            {
                              v109 = -1073741801;
                            }
                            v110 = PerfpDosError(v109);
                            goto LABEL_232;
                          }
                        }
                        else
                        {
                          v102 = -1073741801;
                        }
                        v103 = PerfpDosError(v102);
                        goto LABEL_218;
                      }
                      v84 = (unsigned __int64)v82 >> 1;
                      v85 = (v82 + 8) & 0xFFFFFFF8;
                      v267 = v85;
                      v76[v84] = 0;
                      if ( v77 == 1 )
                      {
                        v86 = *v76;
                        if ( !*v76 )
                          goto LABEL_207;
                        v87 = 0;
                        v88 = v76;
                        v89 = 0;
                        do
                        {
                          if ( v86 == 32 )
                          {
                            if ( v87 && v89 < 0x40 )
                            {
                              *v88 = 0;
                              v90 = wcstoul(v87, 0, 10);
                              v91 = v89;
                              v87 = 0;
                              ++v89;
                              *v88 = 32;
                              v327[v91] = v90;
                            }
                          }
                          else if ( !v87 )
                          {
                            v87 = v88;
                          }
                          v86 = v88[1];
                          ++v88;
                        }
                        while ( v86 );
                        v266 = v89;
                        v85 = v267;
                        if ( !v87 )
                          goto LABEL_207;
                        v92 = v266;
                        if ( v266 < 0x40 && v87 != v88 )
                        {
                          v327[v92] = wcstoul(v87, 0, 10);
                          v93 = (WCHAR *)((char *)v76 + v85);
                          v266 = v92 + 1;
                          goto LABEL_209;
                        }
                      }
                      else
                      {
                        if ( v77 != 7 )
                        {
LABEL_207:
                          v93 = (WCHAR *)((char *)v76 + v85);
                          goto LABEL_209;
                        }
                        v87 = v76;
                        v94 = 0;
                        v266 = 0;
                        if ( *v76 )
                        {
                          do
                          {
                            if ( v94 >= 0x40 )
                              break;
                            v95 = wcstoul(v87, 0, 10);
                            v96 = v94++;
                            v327[v96] = v95;
                            v97 = -1;
                            do
                              v39 = v87[++v97] == 0;
                            while ( !v39 );
                            v87 += v97 + 1;
                          }
                          while ( *v87 );
                          v266 = v94;
                        }
                      }
                      if ( *v87 )
                      {
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            24,
                            WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids);
                        PerfpThrottleError(0xBBAu, 0, &PerfpErrorLog);
                      }
                      goto LABEL_207;
                    }
                  }
                  else
                  {
                    v74 = -1073741801;
                  }
                  v75 = PerfpDosError(v74);
                  goto LABEL_165;
                }
              }
              else
              {
                v69 = -1073741801;
              }
              v70 = PerfpDosError(v69);
              goto LABEL_153;
            }
LABEL_132:
            v283 = 0;
            v299 = 0;
            RtlInitUnicodeString(&v299, L"Collect Timeout");
            v283 = 20;
            v61 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
            v62 = v61;
            if ( v61 )
            {
              *(_OWORD *)v61 = 0;
              v61[4] = 0;
              v63 = NtQueryValueKey(v52, &v299, KeyValuePartialInformation, v61, 0x14u, &v283);
              if ( (int)(v63 + 0x80000000) < 0 || v63 == -2147483643 )
              {
                v50 = v62[1];
                if ( v63 >= 0 )
                {
                  memcpy_0(&v268, v62 + 3, (unsigned int)v62[2]);
                  v63 = 0;
                  v278 = v268;
                }
              }
              LocalFree(v62);
              if ( v63 >= 0 )
              {
                v64 = 0;
LABEL_141:
                if ( v64 || v50 != 4 )
                  v278 = dwExtCtrOpenProcWaitMs;
                goto LABEL_144;
              }
            }
            else
            {
              v63 = -1073741801;
            }
            v64 = PerfpDosError(v63);
            goto LABEL_141;
          }
          LastError = 0;
LABEL_42:
          v31 = &v25[v23];
          v32 = 8;
          v279 = v31;
          if ( LastError )
            goto LABEL_103;
          goto LABEL_43;
        }
        LastError = 1154;
        v26 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, 1154);
          v26 = WPP_GLOBAL_Control;
          v25 = (unsigned __int8 *)(v21 + 8);
          v290 = v25;
          v23 = 8;
          goto LABEL_39;
        }
      }
      v23 = 8;
      v25 = (unsigned __int8 *)(v21 + 8);
      v290 = v25;
LABEL_39:
      if ( (*((_BYTE *)v26 + 28) & 4) != 0 && *((_BYTE *)v26 + 25) >= 2u )
        WPP_SF_S(v26[2], 17, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v3);
      goto LABEL_42;
    }
LABEL_524:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v3);
    goto LABEL_496;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, 5896);
  return 0;
}

```

## disassembly

```asm
0x180022f00  push    rbp
0x180022f02  push    rbx
0x180022f03  push    rsi
0x180022f04  push    rdi
0x180022f05  push    r12
0x180022f07  lea     rbp, [rsp-780h]
0x180022f0f  sub     rsp, 880h
0x180022f16  mov     rax, cs:__security_cookie
0x180022f1d  xor     rax, rsp
0x180022f20  mov     [rbp+7A0h+var_50], rax
0x180022f27  mov     r12, [r8+8]
0x180022f2b  xor     esi, esi
0x180022f2d  mov     [rbp+7A0h+hKey], rcx
0x180022f31  mov     rdi, rdx
0x180022f34  mov     ecx, esi
0x180022f36  mov     [rbp+7A0h+ThreadInformation], r8
0x180022f3a  mov     [rbp+7A0h+var_818], ecx
0x180022f3d  mov     [rsp+8A0h+var_82C], ecx
0x180022f41  mov     [rbp+7A0h+var_808], ecx
0x180022f44  mov     [rsp+8A0h+var_828], ecx
0x180022f48  mov     [rbp+7A0h+KeyHandle], rdx
0x180022f4c  mov     [rbp+7A0h+phkResult], rsi
0x180022f50  mov     [rsp+8A0h+var_850], r12
0x180022f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f5c  test    byte ptr [rcx+1Ch], 4
0x180022f60  jz      short loc_180022F80
0x180022f62  cmp     byte ptr [rcx+19h], 4
0x180022f66  jb      short loc_180022F80
0x180022f68  mov     rcx, [rcx+10h]
0x180022f6c  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x180022f73  mov     edx, 0Ah
0x180022f78  mov     r9, r12
0x180022f7b  call    WPP_SF_S
0x180022f80  mov     rbx, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x180022f87  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180022f8e  mov     [rbp+7A0h+var_778], rsi
0x180022f92  mov     [rbp+7A0h+hMem], rbx
0x180022f96  test    rbx, rbx
0x180022f99  jz      short loc_180023009
0x180022f9b  nop     dword ptr [rax+rax+00h]
0x180022fa0  mov     rcx, [rbx+188h]; lpString1
0x180022fa7  mov     r9d, eax; cchCount2
0x180022faa  mov     r8, r12; lpString2
0x180022fad  mov     [rsp+8A0h+bIgnoreCase], 1; bIgnoreCase
0x180022fb5  mov     edx, eax; cchCount1
0x180022fb7  call    cs:__imp_CompareStringOrdinal
0x180022fbe  nop     dword ptr [rax+rax+00h]
0x180022fc3  cmp     eax, 2
0x180022fc6  jz      short loc_180022FE1
0x180022fc8  mov     [rbp+7A0h+var_778], rbx
0x180022fcc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180022fd3  mov     rbx, [rbx]
0x180022fd6  mov     [rbp+7A0h+hMem], rbx
0x180022fda  test    rbx, rbx
0x180022fdd  jnz     short loc_180022FA0
0x180022fdf  jmp     short loc_180023009
0x180022fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fe8  test    byte ptr [rcx+1Ch], 4
0x180022fec  jz      short loc_180023009
0x180022fee  cmp     byte ptr [rcx+19h], 4
0x180022ff2  jb      short loc_180023009
0x180022ff4  mov     rcx, [rcx+10h]
0x180022ff8  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x180022fff  mov     edx, 0Bh
0x180023004  call    WPP_SF_
0x180023009  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023010  mov     ecx, 1708h; unsigned __int64
0x180023015  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002301a  mov     [rbp+7A0h+lpSrc], rax
0x18002301e  test    rax, rax
0x180023021  jz      loc_180025314
0x180023027  mov     [rsp+8A0h+arg_18], r13
0x18002302f  xor     edx, edx; Val
0x180023031  mov     [rsp+8A0h+var_28], r14
0x180023039  mov     r8d, 1708h; Size
0x18002303f  mov     [rsp+8A0h+var_30], r15
0x180023047  mov     rcx, rax; void *
0x18002304a  movaps  [rsp+8A0h+var_40], xmm6
0x180023052  call    memset_0
0x180023057  mov     eax, cs:?dwExtCtrOpenProcWaitMs@@3KA; ulong dwExtCtrOpenProcWaitMs
0x18002305d  mov     r13, rsi
0x180023060  mov     [rbp+7A0h+var_7EC], eax
0x180023063  xorps   xmm6, xmm6
0x180023066  mov     [rsp+8A0h+var_830], eax
0x18002306a  xorps   xmm0, xmm0
0x18002306d  mov     [rbp+7A0h+var_7F0], eax
0x180023070  mov     r15, rsi
0x180023073  mov     [rsp+8A0h+var_844], eax
0x180023077  mov     r14d, esi
0x18002307a  lea     rax, [rdi-1]
0x18002307e  mov     [rsp+8A0h+var_858], rsi
0x180023083  mov     [rbp+7A0h+Src], rsi
0x180023087  mov     [rsp+8A0h+var_848], esi
0x18002308b  mov     esi, 430h
0x180023090  mov     [rbp+7A0h+var_7B8], 3E8h
0x180023097  mov     [rbp+7A0h+var_7D8], r13d
0x18002309b  movups  [rbp+7A0h+var_6B8], xmm6
0x1800230a2  movups  xmmword ptr [rbp+7A0h+DestinationString.Length], xmm0
0x1800230a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800230aa  ja      loc_1800252C9
0x1800230b0  lea     rdx, ?DLLValue@@3QBGB; "Library"
0x1800230b7  lea     rcx, [rbp+7A0h+DestinationString]; DestinationString
0x1800230bb  call    cs:__imp_RtlInitUnicodeString
0x1800230c2  nop     dword ptr [rax+rax+00h]
0x1800230c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800230ce  mov     [rbp+7A0h+var_7D8], 440h
0x1800230d5  mov     ecx, 440h; unsigned __int64
0x1800230da  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800230df  mov     rbx, rax
0x1800230e2  test    rax, rax
0x1800230e5  jz      loc_180023175
0x1800230eb  xor     edx, edx; Val
0x1800230ed  mov     r8d, 440h; Size
0x1800230f3  mov     rcx, rax; void *
0x1800230f6  call    memset_0
0x1800230fb  lea     rax, [rbp+7A0h+var_7D8]
0x1800230ff  mov     r9, rbx; KeyValueInformation
0x180023102  mov     [rsp+8A0h+ResultLength], rax; ResultLength
0x180023107  lea     rdx, [rbp+7A0h+DestinationString]; ValueName
0x18002310b  mov     r8d, 2; KeyValueInformationClass
0x180023111  mov     [rsp+8A0h+bIgnoreCase], 440h; Length
0x180023119  mov     rcx, rdi; KeyHandle
0x18002311c  call    cs:__imp_NtQueryValueKey
0x180023123  nop     dword ptr [rax+rax+00h]
0x180023128  mov     edi, eax
0x18002312a  mov     eax, 80000000h
0x18002312f  lea     ecx, [rdi+rax]
0x180023132  test    eax, ecx
0x180023134  jnz     short loc_18002313E
0x180023136  cmp     edi, 80000005h
0x18002313c  jnz     short loc_18002315E
0x18002313e  mov     r14d, [rbx+4]
0x180023142  mov     esi, [rbx+8]
0x180023145  test    edi, edi
0x180023147  js      short loc_18002315E
0x180023149  mov     rcx, [rbp+7A0h+lpSrc]; void *
0x18002314d  lea     rdx, [rbx+0Ch]; Src
0x180023151  mov     r8d, esi; Size
0x180023154  call    memcpy_0
0x180023159  mov     esi, [rbx+8]
0x18002315c  xor     edi, edi
0x18002315e  mov     rcx, rbx; hMem
0x180023161  call    cs:__imp_LocalFree
0x180023168  nop     dword ptr [rax+rax+00h]
0x18002316d  test    edi, edi
0x18002316f  js      short loc_18002317A
0x180023171  xor     edi, edi
0x180023173  jmp     short loc_180023183
0x180023175  mov     edi, 0C0000017h
0x18002317a  mov     ecx, edi; int
0x18002317c  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180023181  mov     edi, eax
0x180023183  test    edi, edi
0x180023185  jnz     loc_1800252CE
0x18002318b  mov     r9, [rbp+7A0h+lpSrc]
0x18002318f  xor     eax, eax
0x180023191  mov     ecx, esi
0x180023193  mov     edi, 0FFFFFFF8h
0x180023198  add     esi, 8
0x18002319b  shr     rcx, 1
0x18002319e  and     rsi, rdi
0x1800231a1  mov     r13d, 210h
0x1800231a7  mov     ebx, 218h
0x1800231ac  mov     [r9+rcx*2], ax
0x1800231b1  lea     r15, [r9+rsi]
0x1800231b5  mov     [rbp+7A0h+lpString2], r15
0x1800231b9  cmp     r14d, 2
0x1800231bd  jnz     loc_1800232B1
0x1800231c3  mov     r8d, ebx; nSize
0x1800231c6  mov     rdx, r15; lpDst
0x1800231c9  mov     rcx, r9; lpSrc
0x1800231cc  call    cs:__imp_ExpandEnvironmentStringsW
0x1800231d3  nop     dword ptr [rax+rax+00h]
0x1800231d8  lea     ecx, [rax-1]
0x1800231db  cmp     ecx, 217h
0x1800231e1  ja      short loc_180023202
0x1800231e3  lea     eax, ds:9[rax*2]
0x1800231ea  mov     esi, 8
0x1800231ef  and     rax, rdi
0x1800231f2  add     r15, rax
0x1800231f5  mov     [rbp+7A0h+var_7B0], r15
0x1800231f9  lea     r13, [rax+210h]
0x180023200  jmp     short loc_180023222
0x180023202  mov     rcx, cs:WPP_GLOBAL_Control
0x180023209  mov     edi, 482h
0x18002320e  mov     esi, 8
0x180023213  add     r15, rsi
0x180023216  mov     [rbp+7A0h+var_7B0], r15
0x18002321a  test    edi, edi
0x18002321c  jnz     loc_180023329
0x180023222  mov     [rsp+8A0h+var_85C], ebx
0x180023226  lea     rax, [rsp+8A0h+var_85C]
0x18002322b  mov     rbx, [rbp+7A0h+KeyHandle]
0x18002322f  lea     r9, [rsp+8A0h+var_860]; unsigned int *
0x180023234  xor     r14d, r14d
0x180023237  lea     rdx, ?OpenValue@@3QBGB; "Open"
0x18002323e  mov     [rsp+8A0h+var_870], r14d; int
0x180023243  mov     rcx, rbx; KeyHandle
0x180023246  mov     [rsp+8A0h+ResultLength], rax; unsigned int *
0x18002324b  mov     r12, r15
0x18002324e  mov     qword ptr [rsp+8A0h+bIgnoreCase], r15; unsigned __int8 *
0x180023253  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180023258  mov     edi, eax
0x18002325a  test    eax, eax
0x18002325c  jnz     loc_180023403
0x180023262  cmp     [r15], r14b
0x180023265  jz      loc_1800233FA
0x18002326b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023272  test    byte ptr [rcx+1Ch], 4
0x180023276  jz      short loc_180023299
0x180023278  cmp     byte ptr [rcx+19h], 4
0x18002327c  jb      short loc_180023299
0x18002327e  mov     r8, [rsp+8A0h+var_850]
0x180023283  mov     edx, 10h
0x180023288  mov     rcx, [rcx+10h]
0x18002328c  mov     r9, r15
0x18002328f  mov     qword ptr [rsp+8A0h+bIgnoreCase], r8
0x180023294  call    WPP_SF_sS
0x180023299  mov     eax, [rsp+8A0h+var_85C]
0x18002329d  mov     ecx, 0FFFFFFF8h
0x1800232a2  lea     esi, [rax+8]
0x1800232a5  mov     [rax+r15], r14b
0x1800232a9  and     rsi, rcx
0x1800232ac  jmp     loc_180023539
0x1800232b1  cmp     r14d, 1
0x1800232b5  jnz     short loc_1800232DD
0x1800232b7  mov     r8, rsi; Size
0x1800232ba  mov     rdx, r9; Src
0x1800232bd  mov     rcx, r15; void *
0x1800232c0  call    memcpy_0
0x1800232c5  add     r15, rsi
0x1800232c8  lea     r13, [rsi+210h]
0x1800232cf  mov     [rbp+7A0h+var_7B0], r15
0x1800232d3  mov     esi, 8
0x1800232d8  jmp     loc_180023222
0x1800232dd  mov     edi, 482h
0x1800232e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232e9  test    byte ptr [rcx+1Ch], 4
0x1800232ed  jz      loc_18002320E
0x1800232f3  cmp     byte ptr [rcx+19h], 2
0x1800232f7  jb      loc_18002320E
0x1800232fd  mov     rcx, [rcx+10h]
0x180023301  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x180023308  mov     edx, 0Dh
0x18002330d  mov     r9d, edi
0x180023310  call    WPP_SF_d
0x180023315  mov     rcx, cs:WPP_GLOBAL_Control
0x18002331c  add     r15, 8
0x180023320  mov     [rbp+7A0h+var_7B0], r15
0x180023324  mov     esi, 8
0x180023329  test    byte ptr [rcx+1Ch], 4
0x18002332d  jz      short loc_18002334D
0x18002332f  cmp     byte ptr [rcx+19h], 2
0x180023333  jb      short loc_18002334D
0x180023335  mov     rcx, [rcx+10h]
0x180023339  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x180023340  mov     edx, 11h
0x180023345  mov     r9, r12
0x180023348  call    WPP_SF_S
0x18002334d  add     rsi, r15
0x180023350  mov     r14d, 8
0x180023356  mov     [rbp+7A0h+var_7E8], rsi
0x18002335a  test    edi, edi
0x18002335c  jnz     loc_180023787
0x180023362  mov     rcx, [rbp+7A0h+KeyHandle]; KeyHandle
0x180023366  lea     rax, [rsp+8A0h+var_85C]
0x18002336b  mov     [rsp+8A0h+var_870], 0; int
0x180023373  lea     r9, [rsp+8A0h+var_860]; unsigned int *
0x180023378  mov     [rsp+8A0h+ResultLength], rax; unsigned int *
0x18002337d  lea     rdx, ?CloseValue@@3QBGB; "Close"
0x180023384  mov     qword ptr [rsp+8A0h+bIgnoreCase], rsi; unsigned __int8 *
0x180023389  mov     rbx, rsi
0x18002338c  mov     [rsp+8A0h+var_85C], 218h
0x180023394  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180023399  mov     edi, eax
0x18002339b  test    eax, eax
0x18002339d  jnz     loc_18002364D
0x1800233a3  cmp     [rsi], al
0x1800233a5  jz      loc_180023642
0x1800233ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233b2  test    byte ptr [rcx+1Ch], 4
0x1800233b6  jz      short loc_1800233D9
0x1800233b8  cmp     byte ptr [rcx+19h], 4
0x1800233bc  jb      short loc_1800233D9
0x1800233be  mov     rax, [rsp+8A0h+var_850]
0x1800233c3  mov     edx, 14h
0x1800233c8  mov     rcx, [rcx+10h]
0x1800233cc  mov     r9, rsi
0x1800233cf  mov     qword ptr [rsp+8A0h+bIgnoreCase], rax
0x1800233d4  call    WPP_SF_sS
0x1800233d9  mov     r14d, [rsp+8A0h+var_85C]
0x1800233de  lea     r12, aNull_0; "NULL"
0x1800233e5  add     r14d, 8
0x1800233e9  mov     eax, 0FFFFFFF8h
0x1800233ee  and     r14, rax
0x1800233f1  lea     r15, [r14+rbx]
0x1800233f5  jmp     loc_18002379A
0x1800233fa  mov     edi, 1
0x1800233ff  mov     eax, edi
0x180023401  jmp     short loc_180023419
  ... truncated ...
```
