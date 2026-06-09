# AllocateAndInitializeExtObject(HKEY__ *,HKEY__ *,_UNICODE_STRING *)

- ea: `0x180018470`
- end: `0x18001a801`
- name: `?AllocateAndInitializeExtObject@@YAPEAUEXT_OBJECT@@PEAUHKEY__@@0PEAU_UNICODE_STRING@@@Z`
- size: `9105`
- prototype: `struct EXT_OBJECT *__fastcall(HKEY, HKEY, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800177c0`

## callees

- `0x180015964`
- `0x180015e40`
- `0x180017554`
- `0x180018470`
- `0x180026a7c`
- `0x180027230`
- `0x18002cde0`
- `0x18002fbe0`
- `0x18003b2bc`
- `0x18003b57c`
- `0x18003b748`
- `0x18003d048`
- `0x180057b78`
- `0x180057dfc`
- `0x18005828c`
- `0x180065042`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001a428`
- `msvcrt!_ultow_s` at `0x18001a428`
- `msvcrt!wcstoul` at `0x1800192c7`
- `msvcrt!wcstoul` at `0x18001932c`
- `msvcrt!wcstoul` at `0x180019372`
- `msvcrt!wcstoul` at `0x1800192c7`
- `msvcrt!wcstoul` at `0x18001932c`
- `msvcrt!wcstoul` at `0x180019372`
- `ntdll!NtQueryValueKey` at `0x18001867c`
- `ntdll!NtQueryValueKey` at `0x180018af4`
- `ntdll!NtQueryValueKey` at `0x180018f3b`
- `ntdll!NtQueryValueKey` at `0x180019021`
- `ntdll!NtQueryValueKey` at `0x1800190fd`
- `ntdll!NtQueryValueKey` at `0x1800191ea`
- `ntdll!NtQueryValueKey` at `0x180019476`
- `ntdll!NtQueryValueKey` at `0x180019567`
- `ntdll!NtQueryValueKey` at `0x18001964d`
- `ntdll!NtQueryValueKey` at `0x1800196fe`
- `ntdll!NtQueryValueKey` at `0x180019821`
- `ntdll!NtQueryValueKey` at `0x180019a8b`
- `ntdll!NtQueryValueKey` at `0x180019bc2`
- `ntdll!NtQueryValueKey` at `0x18001867c`
- `ntdll!NtQueryValueKey` at `0x180018af4`
- `ntdll!NtQueryValueKey` at `0x180018f3b`
- `ntdll!NtQueryValueKey` at `0x180019021`
- `ntdll!NtQueryValueKey` at `0x1800190fd`
- `ntdll!NtQueryValueKey` at `0x1800191ea`
- `ntdll!NtQueryValueKey` at `0x180019476`
- `ntdll!NtQueryValueKey` at `0x180019567`
- `ntdll!NtQueryValueKey` at `0x18001964d`
- `ntdll!NtQueryValueKey` at `0x1800196fe`
- `ntdll!NtQueryValueKey` at `0x180019821`
- `ntdll!NtQueryValueKey` at `0x180019a8b`
- `ntdll!NtQueryValueKey` at `0x180019bc2`
- `ntdll!NtClose` at `0x180019e02`
- `ntdll!NtClose` at `0x180019e02`
- `ntdll!NtOpenThreadToken` at `0x18001a472`
- `ntdll!NtOpenThreadToken` at `0x18001a472`
- `ntdll!NtSetInformationThread` at `0x18001a4a7`
- `ntdll!NtSetInformationThread` at `0x18001a528`
- `ntdll!NtSetInformationThread` at `0x18001a4a7`
- `ntdll!NtSetInformationThread` at `0x18001a528`
- `ntdll!RtlInitUnicodeString` at `0x180018625`
- `ntdll!RtlInitUnicodeString` at `0x180018aa2`
- `ntdll!RtlInitUnicodeString` at `0x180018ee7`
- `ntdll!RtlInitUnicodeString` at `0x180018fc5`
- `ntdll!RtlInitUnicodeString` at `0x1800190a5`
- `ntdll!RtlInitUnicodeString` at `0x18001918a`
- `ntdll!RtlInitUnicodeString` at `0x180019421`
- `ntdll!RtlInitUnicodeString` at `0x180019512`
- `ntdll!RtlInitUnicodeString` at `0x1800195f8`
- `ntdll!RtlInitUnicodeString` at `0x1800196ac`
- `ntdll!RtlInitUnicodeString` at `0x1800197c7`
- `ntdll!RtlInitUnicodeString` at `0x180019a3e`
- `ntdll!RtlInitUnicodeString` at `0x180019b6b`
- `ntdll!RtlInitUnicodeString` at `0x180018625`
- `ntdll!RtlInitUnicodeString` at `0x180018aa2`
- `ntdll!RtlInitUnicodeString` at `0x180018ee7`
- `ntdll!RtlInitUnicodeString` at `0x180018fc5`
- `ntdll!RtlInitUnicodeString` at `0x1800190a5`
- `ntdll!RtlInitUnicodeString` at `0x18001918a`
- `ntdll!RtlInitUnicodeString` at `0x180019421`
- `ntdll!RtlInitUnicodeString` at `0x180019512`
- `ntdll!RtlInitUnicodeString` at `0x1800195f8`
- `ntdll!RtlInitUnicodeString` at `0x1800196ac`
- `ntdll!RtlInitUnicodeString` at `0x1800197c7`
- `ntdll!RtlInitUnicodeString` at `0x180019a3e`
- `ntdll!RtlInitUnicodeString` at `0x180019b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a40d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a40d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a45d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a45d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800199e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800199e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019cef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019cef`
- `KERNEL32!LocalFree` at `0x1800186bb`
- `KERNEL32!LocalFree` at `0x180018b36`
- `KERNEL32!LocalFree` at `0x180018f7c`
- `KERNEL32!LocalFree` at `0x180019063`
- `KERNEL32!LocalFree` at `0x18001913f`
- `KERNEL32!LocalFree` at `0x180019243`
- `KERNEL32!LocalFree` at `0x1800194b5`
- `KERNEL32!LocalFree` at `0x1800195a6`
- `KERNEL32!LocalFree` at `0x180019670`
- `KERNEL32!LocalFree` at `0x180019745`
- `KERNEL32!LocalFree` at `0x180019864`
- `KERNEL32!LocalFree` at `0x180019ab7`
- `KERNEL32!LocalFree` at `0x180019c17`
- `KERNEL32!LocalFree` at `0x180019c87`
- `KERNEL32!LocalFree` at `0x180019e11`
- `KERNEL32!LocalFree` at `0x18001a1ad`
- `KERNEL32!LocalFree` at `0x18001a66a`
- `KERNEL32!LocalFree` at `0x18001a68b`
- `KERNEL32!LocalFree` at `0x18001a6b0`
- `KERNEL32!LocalFree` at `0x1800186bb`
- `KERNEL32!LocalFree` at `0x180018b36`
- `KERNEL32!LocalFree` at `0x180018f7c`
- `KERNEL32!LocalFree` at `0x180019063`
- `KERNEL32!LocalFree` at `0x18001913f`
- `KERNEL32!LocalFree` at `0x180019243`
- `KERNEL32!LocalFree` at `0x1800194b5`
- `KERNEL32!LocalFree` at `0x1800195a6`
- `KERNEL32!LocalFree` at `0x180019670`
- `KERNEL32!LocalFree` at `0x180019745`
- `KERNEL32!LocalFree` at `0x180019864`
- `KERNEL32!LocalFree` at `0x180019ab7`
- `KERNEL32!LocalFree` at `0x180019c17`
- `KERNEL32!LocalFree` at `0x180019c87`
- `KERNEL32!LocalFree` at `0x180019e11`
- `KERNEL32!LocalFree` at `0x18001a1ad`
- `KERNEL32!LocalFree` at `0x18001a66a`
- `KERNEL32!LocalFree` at `0x18001a68b`
- `KERNEL32!LocalFree` at `0x18001a6b0`
- `KERNEL32!GetLastError` at `0x18001a532`
- `KERNEL32!GetLastError` at `0x18001a55f`
- `KERNEL32!GetLastError` at `0x18001a571`
- `KERNEL32!GetLastError` at `0x18001a532`
- `KERNEL32!GetLastError` at `0x18001a55f`
- `KERNEL32!GetLastError` at `0x18001a571`
- `KERNEL32!CloseHandle` at `0x18001a541`
- `KERNEL32!CloseHandle` at `0x18001a541`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180018720`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180018720`
- `KERNEL32!CompareStringOrdinal` at `0x180018527`
- `KERNEL32!CompareStringOrdinal` at `0x180019d56`
- `KERNEL32!CompareStringOrdinal` at `0x180018527`
- `KERNEL32!CompareStringOrdinal` at `0x180019d56`
- `KERNEL32!CreateMutexW` at `0x18001a504`
- `KERNEL32!CreateMutexW` at `0x18001a504`
- `KERNEL32!SetLastError` at `0x18001a613`
- `KERNEL32!SetLastError` at `0x18001a613`

## string_xrefs

- `0x1800193ff`: `Keep Library Resident`
- `0x180018a90`: `Open Timeout`
- `0x18001996d`: `\Linkage`

## pseudocode

```c
struct EXT_OBJECT *__fastcall AllocateAndInitializeExtObject(HKEY a1, HKEY a2, struct _UNICODE_STRING *a3)
{
  unsigned __int16 *v3; // r12
  LPCWCH *v5; // rbx
  WCHAR *v6; // rax
  void *v7; // r13
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
  int v29; // eax
  int v30; // esi
  unsigned __int8 *v31; // rsi
  __int64 v32; // r14
  int v33; // eax
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
  int v54; // eax
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
  unsigned int v81; // r15d
  unsigned int v82; // r15d
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
  int v98; // esi
  int v99; // r14d
  _DWORD *v100; // rax
  _DWORD *v101; // rdi
  NTSTATUS v102; // ebx
  unsigned int v103; // eax
  int v104; // r15d
  int v105; // esi
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
  unsigned __int64 v149; // rcx
  unsigned __int64 v150; // rdi
  void *v151; // rax
  HKEY v152; // r13
  int v153; // r15d
  ULONG v154; // esi
  unsigned int v155; // r14d
  _DWORD *v156; // rax
  _DWORD *v157; // rdi
  NTSTATUS ValueKey; // r14d
  unsigned int v159; // esi
  size_t v160; // r8
  void *v161; // rsi
  unsigned int v162; // eax
  unsigned __int64 v163; // rcx
  int v164; // eax
  __int64 v165; // rsi
  __int64 v166; // rsi
  char *v167; // rdi
  unsigned __int8 *v168; // rax
  __int64 v169; // r8
  int v170; // ecx
  int v171; // edx
  unsigned __int8 *v172; // rax
  char *v173; // r8
  int v174; // ecx
  int v175; // edx
  unsigned __int8 *v176; // rax
  __int64 v177; // r8
  int v178; // ecx
  int v179; // edx
  unsigned __int64 v180; // rsi
  char *v181; // rax
  unsigned __int64 v182; // r9
  _BYTE *v183; // r13
  unsigned __int8 *v184; // r11
  __int64 v185; // r8
  unsigned __int64 v186; // rcx
  _BYTE *v187; // rdx
  __int64 v188; // r10
  __int64 v189; // r11
  int v190; // r8d
  _BYTE *v191; // rax
  unsigned __int64 v192; // rsi
  _BYTE *v193; // r9
  unsigned __int64 v194; // r10
  __int64 v195; // r8
  _BYTE *v196; // rcx
  _BYTE *v197; // rdi
  _BYTE *v198; // rdx
  __int64 v199; // r11
  __int64 v200; // rdi
  _BYTE *v201; // rax
  _BYTE *v202; // r13
  unsigned __int64 v203; // rsi
  unsigned __int64 v204; // r10
  unsigned __int8 *v205; // rdi
  __int64 v206; // r8
  _BYTE *v207; // rcx
  _BYTE *v208; // rdx
  __int64 v209; // r11
  __int64 v210; // rdi
  _BYTE *v211; // rax
  _WORD *v212; // r13
  unsigned __int64 v213; // rsi
  _WORD *v214; // r10
  unsigned __int64 v215; // rdx
  LPCWCH v216; // rdi
  __int64 v217; // rcx
  unsigned __int64 v218; // r8
  _WORD *v219; // r9
  __int64 v220; // r11
  __int64 v221; // rdi
  _WORD *v222; // rcx
  int v223; // r11d
  _WORD *v224; // r14
  unsigned __int64 v225; // rsi
  unsigned int v226; // r13d
  const void *v227; // rdx
  size_t v228; // r8
  unsigned __int64 v229; // rsi
  unsigned __int16 *v230; // rcx
  __int64 v231; // rax
  __int64 v232; // r10
  unsigned __int64 v233; // rdx
  _WORD *v234; // r8
  _WORD *v235; // rcx
  unsigned int v236; // eax
  WCHAR *v237; // rax
  __int64 v238; // r11
  unsigned __int16 *v239; // r8
  __int64 v240; // rdx
  __int64 v241; // rcx
  __int64 v242; // r10
  WCHAR *v243; // rcx
  __int64 v244; // r8
  WCHAR *v245; // r8
  unsigned __int16 *v246; // rbx
  __int64 v247; // rax
  const wchar_t *v248; // rcx
  unsigned __int64 v249; // rdi
  __int64 v250; // r9
  __int64 v251; // rdx
  WCHAR *v252; // rcx
  int v253; // r9d
  __int64 v254; // rcx
  DWORD CurrentProcessId; // eax
  HANDLE CurrentThread; // rax
  NTSTATUS v257; // eax
  BOOL v258; // ebx
  unsigned int v259; // edi
  DWORD v260; // eax
  int SD; // eax
  __int64 *v262; // rax
  int v263; // ebx
  char *v265; // rdx
  __int64 v266; // rax
  __int64 v267; // r8
  __int64 v268; // r9
  _WORD *v269; // rcx
  char *v270; // rax
  char *v271; // rcx
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  char *v273; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v274; // [rsp+50h] [rbp-B0h]
  int v275; // [rsp+58h] [rbp-A8h]
  int v276; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v277; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v278; // [rsp+68h] [rbp-98h] BYREF
  ULONG v279; // [rsp+70h] [rbp-90h] BYREF
  ULONG v280; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG v281; // [rsp+78h] [rbp-88h] BYREF
  ULONG v282; // [rsp+7Ch] [rbp-84h] BYREF
  ULONG v283; // [rsp+80h] [rbp-80h]
  ULONG v284; // [rsp+84h] [rbp-7Ch]
  struct _UNICODE_STRING v285; // [rsp+88h] [rbp-78h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp-68h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp-60h]
  __int64 v288; // [rsp+A8h] [rbp-58h]
  unsigned int v289; // [rsp+B0h] [rbp-50h]
  ULONG v290; // [rsp+B4h] [rbp-4Ch]
  unsigned __int8 *v291; // [rsp+B8h] [rbp-48h]
  HKEY hKey; // [rsp+C0h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp-30h] BYREF
  ULONG v295; // [rsp+D4h] [rbp-2Ch] BYREF
  ULONG v296; // [rsp+D8h] [rbp-28h] BYREF
  ULONG v297; // [rsp+DCh] [rbp-24h] BYREF
  ULONG v298; // [rsp+E0h] [rbp-20h] BYREF
  ULONG v299; // [rsp+E4h] [rbp-1Ch] BYREF
  ULONG v300; // [rsp+E8h] [rbp-18h] BYREF
  int v301; // [rsp+ECh] [rbp-14h] BYREF
  unsigned __int8 *v302; // [rsp+F0h] [rbp-10h]
  struct _UNICODE_STRING *ThreadInformation; // [rsp+F8h] [rbp-8h] BYREF
  struct _SECURITY_ATTRIBUTES v304; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpSrc; // [rsp+118h] [rbp+18h]
  HLOCAL hMem; // [rsp+120h] [rbp+20h]
  LPCWCH *v307; // [rsp+128h] [rbp+28h]
  LPCWCH lpString2; // [rsp+130h] [rbp+30h]
  struct _UNICODE_STRING DestinationString; // [rsp+138h] [rbp+38h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+148h] [rbp+48h] BYREF
  struct _UNICODE_STRING v311; // [rsp+158h] [rbp+58h] BYREF
  struct _UNICODE_STRING v312; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING v313; // [rsp+178h] [rbp+78h] BYREF
  struct _UNICODE_STRING v314; // [rsp+188h] [rbp+88h] BYREF
  struct _UNICODE_STRING v315; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING v316; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING v317; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _UNICODE_STRING v318; // [rsp+1C8h] [rbp+C8h] BYREF
  struct _UNICODE_STRING v319; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v320; // [rsp+1E8h] [rbp+E8h] BYREF
  char v321[16]; // [rsp+1F8h] [rbp+F8h] BYREF
  const char *v322; // [rsp+208h] [rbp+108h]
  __int64 v323; // [rsp+210h] [rbp+110h]
  const wchar_t *v324; // [rsp+218h] [rbp+118h]
  int v325; // [rsp+220h] [rbp+120h]
  int v326; // [rsp+224h] [rbp+124h]
  char v327[16]; // [rsp+228h] [rbp+128h] BYREF
  const char *v328; // [rsp+238h] [rbp+138h]
  __int64 v329; // [rsp+240h] [rbp+140h]
  const wchar_t *v330; // [rsp+248h] [rbp+148h]
  int v331; // [rsp+250h] [rbp+150h]
  int v332; // [rsp+254h] [rbp+154h]
  char v333[16]; // [rsp+258h] [rbp+158h] BYREF
  const char *v334; // [rsp+268h] [rbp+168h]
  __int64 v335; // [rsp+270h] [rbp+170h]
  const wchar_t *v336; // [rsp+278h] [rbp+178h]
  int v337; // [rsp+280h] [rbp+180h]
  int v338; // [rsp+284h] [rbp+184h]
  _DWORD Src[64]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t Buffer[32]; // [rsp+390h] [rbp+290h] BYREF
  WCHAR Name[576]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v3 = a3->Buffer;
  hKey = a1;
  ThreadInformation = a3;
  v283 = 0;
  v281 = 0;
  v284 = 0;
  v282 = 0;
  KeyHandle = a2;
  phkResult = 0;
  v274 = v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v3);
  v5 = (LPCWCH *)ExtensibleObjects;
  v307 = 0;
  hMem = ExtensibleObjects;
  if ( ExtensibleObjects )
  {
    while ( CompareStringOrdinal(v5[49], -1, v3, -1, 1) != 2 )
    {
      v307 = v5;
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
    v290 = dwExtCtrOpenProcWaitMs;
    v8 = 0;
    v280 = dwExtCtrOpenProcWaitMs;
    v289 = dwExtCtrOpenProcWaitMs;
    v9 = 0;
    v276 = dwExtCtrOpenProcWaitMs;
    v10 = 0;
    v273 = 0;
    *(_QWORD *)&v285.Length = 0;
    v275 = 0;
    v11 = 1072;
    v301 = 1000;
    ResultLength = 0;
    v320 = 0;
    DestinationString = 0;
    if ( (unsigned __int64)a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = 6;
      goto LABEL_536;
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
          v302 = v25;
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
          v302 = v25;
          v23 = 8;
LABEL_28:
          LODWORD(Size) = 536;
          v27 = KeyHandle;
          v28 = 0;
          v29 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Open", v15, &v279, v25, (unsigned int *)&Size, 0);
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
                WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, (_DWORD)v274, (_DWORD)v25, (__int64)v274);
              v30 = Size + 8;
              v25[(unsigned int)Size] = 0;
              v23 = v30 & 0xFFFFFFF8;
              goto LABEL_71;
            }
            LastError = 1;
            v36 = 1;
          }
          v37 = v274;
          v275 = v36;
          if ( v274 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                (_DWORD)v274,
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
            v323 = 5;
            v322 = "Open";
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
            v325 = v40;
            v324 = v41;
            v326 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)S_Perflib_Context,
              (unsigned int)PERFLIB_PROC_NAME_NOT_FOUND,
              (_DWORD)v15,
              3,
              (__int64)v321);
          }
          if ( LastError )
            goto LABEL_42;
          v27 = KeyHandle;
LABEL_71:
          v295 = 0;
          v20 += v23;
          ValueName = 0;
          RtlInitUnicodeString(&ValueName, L"Open Timeout");
          v295 = 20;
          v42 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
          v43 = v42;
          if ( v42 )
          {
            *(_OWORD *)v42 = 0;
            v42[4] = 0;
            v44 = NtQueryValueKey(v27, &ValueName, KeyValuePartialInformation, v42, 0x14u, &v295);
            if ( (int)(v44 + 0x80000000) < 0 || v44 == -2147483643 )
            {
              v28 = v43[1];
              if ( v44 >= 0 )
              {
                memcpy_0(&v276, v43 + 3, (unsigned int)v43[2]);
                v44 = 0;
                v289 = v276;
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
            v291 = v31;
            v32 = 8;
            v289 = dwExtCtrOpenProcWaitMs;
LABEL_43:
            LODWORD(Size) = 536;
            v33 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Close", v15, &v279, v31, (unsigned int *)&Size, 0);
            LastError = v33;
            if ( v33 )
            {
              if ( v33 == 2 || v33 == 234 )
                v275 = 1;
            }
            else
            {
              if ( *v31 )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, (_DWORD)v15, (_DWORD)v31, (__int64)v274);
                v34 = L"NULL";
                v32 = ((_DWORD)Size + 8) & 0xFFFFFFF8;
                v35 = &v31[v32];
                goto LABEL_106;
              }
              LastError = 1;
              v275 = 1;
            }
            v46 = v274;
            if ( v274 )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                  (_DWORD)v274,
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
              v329 = 6;
              v328 = "Close";
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
              v331 = v48;
              v330 = v49;
              v332 = 0;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)S_Perflib_Context,
                (unsigned int)PERFLIB_PROC_NAME_NOT_FOUND,
                (_DWORD)v15,
                3,
                (__int64)v327);
              goto LABEL_104;
            }
LABEL_103:
            v34 = L"NULL";
LABEL_104:
            if ( LastError )
              goto LABEL_522;
            v35 = v31 + 8;
LABEL_106:
            v50 = 0;
            TokenHandle = v35;
            v51 = v32 + v20;
            v52 = (HKEY)KeyHandle;
            v276 = 0;
            v277 = 0;
            v288 = v51;
            LODWORD(Size) = 536;
            if ( PrivateRegQueryValueExT((HKEY)KeyHandle, L"Query", v15, &v279, v35, (unsigned int *)&Size, 0)
              && (LODWORD(Size) = 536,
                  v54 = PrivateRegQueryValueExT(v52, L"Collect", v53, &v279, v35, (unsigned int *)&Size, 0),
                  (v55 = v54) != 0) )
            {
              v56 = 8;
              if ( v54 == 2 || v54 == 234 )
                v275 = 1;
            }
            else
            {
              v56 = ((_DWORD)Size + 8) & 0xFFFFFFF8;
              v288 = v56 + v51;
              if ( *v35 )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, (_DWORD)v53, (_DWORD)v35, (__int64)v274);
                goto LABEL_132;
              }
              v55 = 1;
              v275 = 1;
            }
            v57 = v274;
            if ( v274 )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                  (_DWORD)v274,
                  v55);
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v55);
            }
            if ( PerfpThrottleError(0xBBBu, 0, &PerfpErrorLog) && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
            {
              v335 = 8;
              v334 = "Collect";
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
              v337 = v60;
              v336 = v34;
              v338 = 0;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)S_Perflib_Context,
                (unsigned int)PERFLIB_PROC_NAME_NOT_FOUND,
                v58,
                3,
                (__int64)v333);
            }
            if ( v55 )
            {
LABEL_144:
              v280 = 0;
              v65 = 0;
              v312 = 0;
              RtlInitUnicodeString(&v312, L"First Counter");
              v280 = 20;
              v66 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
              v67 = KeyHandle;
              v68 = v66;
              if ( v66 )
              {
                *(_OWORD *)v66 = 0;
                v66[4] = 0;
                v69 = NtQueryValueKey(v67, &v312, KeyValuePartialInformation, v66, 0x14u, &v280);
                if ( (int)(v69 + 0x80000000) < 0 || v69 == -2147483643 )
                {
                  v65 = v68[1];
                  if ( v69 >= 0 )
                  {
                    memcpy_0(&v281, v68 + 3, (unsigned int)v68[2]);
                    v69 = 0;
                    v283 = v281;
                  }
                }
                LocalFree(v68);
                if ( v69 >= 0 )
                {
                  v70 = 0;
LABEL_153:
                  if ( v70 || v65 != 4 )
                    v283 = 0;
                  v281 = 0;
                  v71 = 0;
                  v313 = 0;
                  RtlInitUnicodeString(&v313, L"Last Counter");
                  v281 = 20;
                  v72 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                  v73 = v72;
                  if ( v72 )
                  {
                    *(_OWORD *)v72 = 0;
                    v72[4] = 0;
                    v74 = NtQueryValueKey(v67, &v313, KeyValuePartialInformation, v72, 0x14u, &v281);
                    if ( (int)(v74 + 0x80000000) < 0 || v74 == -2147483643 )
                    {
                      v71 = v73[1];
                      if ( v74 >= 0 )
                      {
                        memcpy_0(&v282, v73 + 3, (unsigned int)v73[2]);
                        v74 = 0;
                        v284 = v282;
                      }
                    }
                    LocalFree(v73);
                    if ( v74 >= 0 )
                    {
                      v75 = 0;
LABEL_165:
                      if ( v75 || v71 != 4 )
                        v284 = 0;
                      v282 = 0;
                      v76 = (WCHAR *)&v35[v56];
                      v77 = 0;
                      v319 = 0;
                      RtlInitUnicodeString(&v319, L"Object List");
                      v282 = 1088;
                      v78 = operator new(0x440u, (const struct std::nothrow_t *)&std::nothrow);
                      v79 = v78;
                      if ( v78 )
                      {
                        memset_0(v78, 0, 0x440u);
                        v80 = NtQueryValueKey(v67, &v319, KeyValuePartialInformation, v79, 0x440u, &v282);
                        if ( (int)(v80 + 0x80000000) < 0 || v80 == -2147483643 )
                        {
                          v81 = v79[2];
                          v77 = v79[1];
                          LODWORD(Size) = v81;
                          if ( v80 >= 0 && v76 )
                          {
                            memcpy_0(v76, v79 + 3, v81);
                            v82 = v79[2];
                            v80 = 0;
                          }
                          else
                          {
                            v82 = Size;
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
                        LODWORD(Size) = 0;
                        v296 = 0;
                        v314 = 0;
                        v99 = 0;
                        RtlInitUnicodeString(&v314, L"Keep Library Resident");
                        v296 = 20;
                        v100 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                        v101 = v100;
                        if ( v100 )
                        {
                          *(_OWORD *)v100 = 0;
                          v100[4] = 0;
                          v102 = NtQueryValueKey(v67, &v314, KeyValuePartialInformation, v100, 0x14u, &v296);
                          if ( (int)(v102 + 0x80000000) < 0 || v102 == -2147483643 )
                          {
                            v99 = v101[1];
                            if ( v102 >= 0 )
                            {
                              memcpy_0(&Size, v101 + 3, (unsigned int)v101[2]);
                              v98 = Size;
                              v102 = 0;
                            }
                          }
                          LocalFree(v101);
                          if ( v102 >= 0 )
                          {
                            v103 = 0;
LABEL_218:
                            v104 = v276;
                            if ( !v103 && v99 == 4 )
                            {
                              if ( v98 == 1 )
                                v104 = 4;
                              v276 = v104;
                            }
                            v105 = 0;
                            LODWORD(Size) = 0;
                            v297 = 0;
                            v315 = 0;
                            v106 = 0;
                            RtlInitUnicodeString(&v315, L"Collect Supports Metadata");
                            v297 = 20;
                            v107 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                            v108 = v107;
                            if ( v107 )
                            {
                              *(_OWORD *)v107 = 0;
                              v107[4] = 0;
                              v109 = NtQueryValueKey(v67, &v315, KeyValuePartialInformation, v107, 0x14u, &v297);
                              if ( (int)(v109 + 0x80000000) < 0 || v109 == -2147483643 )
                              {
                                v106 = v108[1];
                                if ( v109 >= 0 )
                                {
                                  memcpy_0(&Size, v108 + 3, (unsigned int)v108[2]);
                                  v105 = Size;
                                  v109 = 0;
                                }
                              }
                              LocalFree(v108);
                              if ( v109 >= 0 )
                              {
                                v110 = 0;
LABEL_232:
                                if ( !v110 && v106 == 4 && v105 == 1 )
                                  v276 = v104 | 0x80;
                                v111 = 0;
                                v316 = 0;
                                v298 = 0;
                                RtlInitUnicodeString(&v316, L"Error Count Limit");
                                v298 = 20;
                                v112 = (unsigned int *)operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
                                v113 = v112;
                                if ( v112 )
                                {
                                  *(_OWORD *)v112 = 0;
                                  v112[4] = 0;
                                  v114 = NtQueryValueKey(v67, &v316, KeyValuePartialInformation, v112, 0x14u, &v298);
                                  if ( v114 >= 0 )
                                  {
                                    memcpy_0(&v301, v113 + 3, v113[2]);
                                    v114 = 0;
                                  }
                                  LocalFree(v113);
                                  if ( v114 >= 0 )
                                  {
LABEL_243:
                                    v299 = 0;
                                    v115 = 0;
                                    v116 = 16;
                                    v317 = 0;
                                    RtlInitUnicodeString(&v317, L"Library Validation Code");
                                    v299 = 32;
                                    v117 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
                                    v118 = v117;
                                    if ( v117 )
                                    {
                                      *v117 = 0;
                                      v117[1] = 0;
                                      v119 = NtQueryValueKey(v67, &v317, KeyValuePartialInformation, v117, 0x20u, &v299);
                                      if ( (int)(v119 + 0x80000000) < 0 || v119 == -2147483643 )
                                      {
                                        v115 = v118[1];
                                        v116 = v118[2];
                                        if ( v119 >= 0 )
                                        {
                                          memcpy_0(&v320, v118 + 3, v116);
                                          v8 = v320;
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
                                              v274);
                                          }
                                          v8 = 0;
                                        }
                                        v121 = 0;
                                        v278 = 0;
                                        v300 = 0;
                                        v318 = 0;
                                        v122 = 8;
                                        RtlInitUnicodeString(&v318, L"Successful File Date");
                                        v300 = 24;
                                        v123 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                                        v124 = v123;
                                        if ( v123 )
                                        {
                                          *(_OWORD *)v123 = 0;
                                          *((_QWORD *)v123 + 2) = 0;
                                          v125 = NtQueryValueKey(
                                                   v67,
                                                   &v318,
                                                   KeyValuePartialInformation,
                                                   v123,
                                                   0x18u,
                                                   &v300);
                                          if ( (int)(v125 + 0x80000000) < 0 || v125 == -2147483643 )
                                          {
                                            v111 = v124[1];
                                            v122 = v124[2];
                                            if ( v125 >= 0 )
                                            {
                                              memcpy_0(&v278, v124 + 3, v122);
                                              v121 = v278;
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
                                        v127 = v274;
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
                                          v278 = v135;
                                          goto LABEL_301;
                                        }
                                        if ( v135 )
                                        {
                                          if ( v135 <= 0x7FFFFFFF )
                                          {
                                            v139 = 2147483646;
                                            v278 = v135;
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
                                              v142 = RegOpenKeyExW(hKey, v93, 0, 0x20019u, &phkResult);
LABEL_302:
                                              if ( v142 || (v143 = phkResult) == 0 )
                                              {
                                                v166 = v288;
                                                v7 = 0;
                                                *(_QWORD *)&v285.Length = 0;
                                                LODWORD(Size) = 0;
                                                goto LABEL_345;
                                              }
                                              v7 = 0;
                                              LODWORD(Size) = 0;
                                              LODWORD(hKey) = 0;
                                              v144 = 0;
                                              v285 = 0;
                                              if ( (unsigned __int64)phkResult - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                                                goto LABEL_340;
                                              RtlInitUnicodeString(&v285, L"Export");
                                              LODWORD(hKey) = 16;
                                              v145 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                                              v146 = v145;
                                              if ( v145 )
                                              {
                                                *v145 = 0;
                                                v147 = NtQueryValueKey(
                                                         v143,
                                                         &v285,
                                                         KeyValuePartialInformation,
                                                         v145,
                                                         0x10u,
                                                         (PULONG)&hKey);
                                                if ( (int)(v147 + 0x80000000) < 0 || v147 == -2147483643 )
                                                {
                                                  v144 = v146[2];
                                                  v128 = v146[1];
                                                  LODWORD(Size) = v144;
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
                                                v149 = ((unsigned __int64)(v144 + 1) >> 1) + 1;
                                                v150 = 2 * v149;
                                                if ( !is_mul_ok(v149, 2u) )
                                                  v150 = -1;
                                                v151 = operator new(v150, (const struct std::nothrow_t *)&std::nothrow);
                                                *(_QWORD *)&v285.Length = v151;
                                                v7 = v151;
                                                if ( !v151 )
                                                {
                                                  *(_QWORD *)&v285.Length = 0;
                                                  LastError = 14;
                                                  LODWORD(Size) = 0;
                                                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                  {
                                                    WPP_SF_d(
                                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                      28,
                                                      WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                                      v144);
                                                  }
                                                  goto LABEL_341;
                                                }
                                                memset_0(v151, 0, v150);
                                                v152 = phkResult;
                                                LODWORD(hKey) = 0;
                                                v153 = 0;
                                                *(_OWORD *)&v304.nLength = 0;
                                                if ( (unsigned __int64)phkResult - 1 > 0xFFFFFFFFFFFFFFFDuLL )
                                                {
                                                  v161 = *(void **)&v285.Length;
LABEL_336:
                                                  LocalFree(v161);
                                                  v7 = 0;
                                                  *(_QWORD *)&v285.Length = 0;
                                                  LODWORD(Size) = 0;
                                                  LastError = 0;
LABEL_341:
                                                  v166 = v288;
LABEL_342:
                                                  RegCloseKey(phkResult);
                                                  if ( !LastError )
                                                  {
LABEL_345:
                                                    v167 = (char *)hMem;
                                                    if ( hMem )
                                                    {
                                                      if ( *((_DWORD *)hMem + 93) == v283
                                                        && *((_DWORD *)hMem + 94) == v284
                                                        && CompareStringOrdinal(
                                                             *((LPCWCH *)hMem + 12),
                                                             -1,
                                                             lpString2,
                                                             -1,
                                                             1) == 2 )
                                                      {
                                                        v168 = (unsigned __int8 *)*((_QWORD *)v167 + 3);
                                                        v169 = v302 - v168;
                                                        do
                                                        {
                                                          v170 = v168[v169];
                                                          v171 = *v168 - v170;
                                                          if ( v171 )
                                                            break;
                                                          ++v168;
                                                        }
                                                        while ( v170 );
                                                        if ( !v171 )
                                                        {
                                                          v172 = (unsigned __int8 *)*((_QWORD *)v167 + 6);
                                                          v173 = (char *)((_BYTE *)TokenHandle - v172);
                                                          do
                                                          {
                                                            v174 = (unsigned __int8)v173[(_QWORD)v172];
                                                            v175 = *v172 - v174;
                                                            if ( v175 )
                                                              break;
                                                            ++v172;
                                                          }
                                                          while ( v174 );
                                                          if ( !v175 )
                                                          {
                                                            v176 = (unsigned __int8 *)*((_QWORD *)v167 + 9);
                                                            v177 = v291 - v176;
                                                            do
                                                            {
                                                              v178 = v176[v177];
                                                              v179 = *v176 - v178;
                                                              if ( v179 )
                                                                break;
                                                              ++v176;
                                                            }
                                                            while ( v178 );
                                                            if ( !v179 )
                                                            {
                                                              v9 = v167;
                                                              v167[524] = 0;
                                                              goto LABEL_525;
                                                            }
                                                          }
                                                        }
                                                      }
                                                      if ( v307 )
                                                        *v307 = *(LPCWCH *)v167;
                                                      else
                                                        ExtensibleObjects = *(HLOCAL *)v167;
                                                      CloseExtObjectLibrary((struct EXT_OBJECT *)v167, 1);
                                                      NtClose(*((HANDLE *)v167 + 13));
                                                      --NumExtensibleObjects;
                                                      LocalFree(v167);
                                                    }
                                                    v180 = ((ThreadInformation->MaximumLength + 7LL) & 0xFFFFFFF8LL)
                                                         + v166;
                                                    v181 = (char *)operator new(
                                                                     v180,
                                                                     (const struct std::nothrow_t *)&std::nothrow);
                                                    v9 = v181;
                                                    if ( !v181 )
                                                    {
                                                      LastError = 14;
                                                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                      {
                                                        WPP_SF_d(
                                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                          29,
                                                          WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                                          (unsigned int)v180);
                                                      }
                                                      v3 = v274;
                                                      goto LABEL_508;
                                                    }
                                                    memset_0(v181, 0, v180);
                                                    v182 = v180 - 528;
                                                    v273 = v9;
                                                    v183 = v9 + 528;
                                                    *((_QWORD *)v9 + 3) = v9 + 528;
                                                    if ( v180 == 528 )
                                                      goto LABEL_496;
                                                    if ( v182 > 0x7FFFFFFF )
                                                    {
                                                      *v183 = 0;
                                                      goto LABEL_521;
                                                    }
                                                    v184 = v302;
                                                    v185 = 2147483646;
                                                    v273 = v9;
                                                    v186 = v180 - 528;
                                                    v187 = v9 + 528;
                                                    v188 = 0;
                                                    do
                                                    {
                                                      if ( !v185 )
                                                        break;
                                                      if ( !*v184 )
                                                        break;
                                                      *v187++ = *v184++;
                                                      --v185;
                                                      ++v188;
                                                      --v186;
                                                    }
                                                    while ( v186 );
                                                    v189 = v188 - 1;
                                                    v190 = -2147024774;
                                                    if ( v186 )
                                                    {
                                                      v189 = v188;
                                                      v190 = 0;
                                                    }
                                                    v191 = v187 - 1;
                                                    if ( v186 )
                                                      v191 = v187;
                                                    *v191 = 0;
                                                    if ( v190 >= 0 )
                                                    {
                                                      v183 += v189;
                                                      v182 -= v189;
                                                      v273 = v9;
                                                    }
                                                    else
                                                    {
                                                      *v183 = 0;
                                                    }
                                                    v192 = v182;
                                                    if ( v190 < 0 )
                                                      goto LABEL_520;
                                                    v193 = (_BYTE *)((unsigned __int64)(v183 + 8) & 0xFFFFFFFFFFFFFFF8uLL);
                                                    v273 = v9;
                                                    *((_DWORD *)v9 + 15) = v289;
                                                    *((_QWORD *)v9 + 6) = v193;
                                                    v194 = (unsigned __int64)&v183[v192 - (_QWORD)v193];
                                                    if ( v194 )
                                                    {
                                                      if ( v194 > 0x7FFFFFFF )
                                                      {
LABEL_501:
                                                        *v193 = 0;
                                                        goto LABEL_502;
                                                      }
                                                      v195 = 2147483646;
                                                      v196 = &v183[v192 - (_QWORD)v193];
                                                      v197 = TokenHandle;
                                                      v198 = (_BYTE *)((unsigned __int64)(v183 + 8)
                                                                     & 0xFFFFFFFFFFFFFFF8uLL);
                                                      v199 = 0;
                                                      do
                                                      {
                                                        if ( !v195 )
                                                          break;
                                                        if ( !*v197 )
                                                          break;
                                                        *v198++ = *v197++;
                                                        --v195;
                                                        ++v199;
                                                        --v196;
                                                      }
                                                      while ( v196 );
                                                      v200 = v199 - 1;
                                                      v190 = -2147024774;
                                                      if ( v196 )
                                                      {
                                                        v200 = v199;
                                                        v190 = 0;
                                                      }
                                                      v201 = v198 - 1;
                                                      if ( v196 )
                                                        v201 = v198;
                                                      *v201 = 0;
                                                      if ( v190 >= 0 )
                                                      {
                                                        v193 += v200;
                                                        v194 -= v200;
                                                        v273 = v9;
                                                      }
                                                      else
                                                      {
                                                        *v193 = 0;
                                                      }
                                                      v202 = v193;
                                                      v203 = v194;
                                                      if ( v190 < 0 )
                                                        goto LABEL_520;
                                                      v193 = (_BYTE *)((unsigned __int64)(v193 + 8)
                                                                     & 0xFFFFFFFFFFFFFFF8uLL);
                                                      v273 = v9;
                                                      *((_DWORD *)v9 + 14) = v290;
                                                      *((_QWORD *)v9 + 9) = v193;
                                                      v204 = (unsigned __int64)&v202[v194 - (_QWORD)v193];
                                                      if ( v204 )
                                                      {
                                                        if ( v204 <= 0x7FFFFFFF )
                                                        {
                                                          v205 = v291;
                                                          v206 = 2147483646;
                                                          v207 = &v202[v203 - (_QWORD)v193];
                                                          v208 = (_BYTE *)((unsigned __int64)(v202 + 8)
                                                                         & 0xFFFFFFFFFFFFFFF8uLL);
                                                          v209 = 0;
                                                          do
                                                          {
                                                            if ( !v206 )
                                                              break;
                                                            if ( !*v205 )
                                                              break;
                                                            *v208++ = *v205++;
                                                            --v206;
                                                            ++v209;
                                                            --v207;
                                                          }
                                                          while ( v207 );
                                                          v210 = v209 - 1;
                                                          v190 = -2147024774;
                                                          if ( v207 )
                                                          {
                                                            v210 = v209;
                                                            v190 = 0;
                                                          }
                                                          v211 = v208 - 1;
                                                          if ( v207 )
                                                            v211 = v208;
                                                          *v211 = 0;
                                                          if ( v190 >= 0 )
                                                          {
                                                            v193 += v210;
                                                            v273 = v9;
                                                            v204 -= v210;
                                                          }
                                                          else
                                                          {
                                                            *v193 = 0;
                                                          }
                                                          v212 = v193;
                                                          v213 = v204;
                                                          if ( v190 >= 0 )
                                                          {
                                                            v273 = v9;
                                                            v214 = (_WORD *)((unsigned __int64)(v193 + 8)
                                                                           & 0xFFFFFFFFFFFFFFF8uLL);
                                                            *((_QWORD *)v9 + 12) = v214;
                                                            v215 = (unsigned __int64)&v193[v213 - (_QWORD)v214] >> 1;
                                                            if ( v215 )
                                                            {
                                                              if ( v215 <= 0x7FFFFFFF )
                                                              {
                                                                v216 = lpString2;
                                                                v217 = 2147483646;
                                                                v218 = (unsigned __int64)&v193[v213 - (_QWORD)v214] >> 1;
                                                                v219 = (_WORD *)((unsigned __int64)(v193 + 8)
                                                                               & 0xFFFFFFFFFFFFFFF8uLL);
                                                                v220 = 0;
                                                                do
                                                                {
                                                                  if ( !v217 )
                                                                    break;
                                                                  if ( !*v216 )
                                                                    break;
                                                                  *v219++ = *v216++;
                                                                  --v217;
                                                                  ++v220;
                                                                  --v218;
                                                                }
                                                                while ( v218 );
                                                                v221 = v220 - 1;
                                                                v222 = v219 - 1;
                                                                if ( v218 )
                                                                  v221 = v220;
                                                                v223 = -2147024774;
                                                                if ( v218 )
                                                                {
                                                                  v222 = v219;
                                                                  v223 = 0;
                                                                }
                                                                *v222 = 0;
                                                                if ( v218 )
                                                                {
                                                                  v214 += v221;
                                                                  v215 -= v221;
                                                                }
                                                                else
                                                                {
                                                                  *v214 = 0;
                                                                  v273 = v9;
                                                                  if ( v223 != -2147024774 )
                                                                  {
LABEL_424:
                                                                    if ( v223 < 0 )
                                                                    {
                                                                      LOWORD(v138) = v223;
LABEL_521:
                                                                      LastError = (unsigned __int16)v138;
                                                                      goto LABEL_522;
                                                                    }
                                                                    v273 = v9;
                                                                    v224 = (_WORD *)(((unsigned __int64)v212 + 23)
                                                                                   & 0xFFFFFFFFFFFFFFF8uLL);
                                                                    v225 = (unsigned __int64)v212
                                                                         + 2 * v213
                                                                         - (_QWORD)v224;
                                                                    if ( *(_QWORD *)&v285.Length )
                                                                    {
                                                                      v226 = Size;
                                                                      v227 = *(const void **)&v285.Length;
                                                                      v228 = (unsigned int)Size;
                                                                      *((_QWORD *)v9 + 4) = v224;
                                                                      memcpy_0(v224, v227, v228);
                                                                      v224 = (_WORD *)(((unsigned __int64)&v224[((unsigned __int64)v226 >> 1) + 3]
                                                                                      + 1)
                                                                                     & 0xFFFFFFFFFFFFFFF8uLL);
                                                                      LocalFree(*(HLOCAL *)&v285.Length);
                                                                      *(_QWORD *)&v285.Length = 0;
                                                                      v225 -= (v226 + 7) & 0xFFFFFFF8;
                                                                    }
                                                                    v229 = v225 >> 1;
                                                                    *((_QWORD *)v9 + 49) = v224;
                                                                    if ( v229 )
                                                                    {
                                                                      if ( v229 <= 0x7FFFFFFF )
                                                                      {
                                                                        v230 = v274;
                                                                        v231 = 2147483646;
                                                                        v232 = 0;
                                                                        v233 = v229;
                                                                        v234 = v224;
                                                                        do
                                                                        {
                                                                          if ( !v231 )
                                                                            break;
                                                                          if ( !*v230 )
                                                                            break;
                                                                          *v234++ = *v230++;
                                                                          --v231;
                                                                          ++v232;
                                                                          --v233;
                                                                        }
                                                                        while ( v233 );
                                                                        v235 = v234 - 1;
                                                                        v138 = -2147024774;
                                                                        if ( v233 )
                                                                        {
                                                                          v235 = v234;
                                                                          v138 = 0;
                                                                        }
                                                                        *v235 = 0;
                                                                        if ( !v233 )
                                                                        {
                                                                          *v224 = 0;
                                                                          v273 = v9;
                                                                        }
                                                                        if ( v138 < 0 )
                                                                          goto LABEL_521;
                                                                        *((_DWORD *)v9 + 95) = v276;
                                                                        *((_QWORD *)v9 + 13) = KeyHandle;
                                                                        *((_DWORD *)v9 + 93) = v283;
                                                                        *((_DWORD *)v9 + 94) = v284;
                                                                        v236 = v277;
                                                                        *((_QWORD *)v9 + 53) = v121;
                                                                        *((_DWORD *)v9 + 96) = 1;
                                                                        *(_OWORD *)(v9 + 408) = v8;
                                                                        if ( v236 )
                                                                        {
                                                                          *((_DWORD *)v9 + 28) = v236;
                                                                          memcpy_0(v9 + 116, Src, 4LL * v236);
                                                                        }
                                                                        v3 = v274;
                                                                        v237 = Name;
                                                                        v238 = 536;
                                                                        *((_QWORD *)v9 + 50) = 0;
                                                                        v239 = v3;
                                                                        v240 = 536;
                                                                        v241 = 2147483646;
                                                                        v242 = 0;
                                                                        do
                                                                        {
                                                                          if ( !v241 )
                                                                            break;
                                                                          if ( !*v239 )
                                                                            break;
                                                                          *v237++ = *v239++;
                                                                          --v241;
                                                                          ++v242;
                                                                          --v240;
                                                                        }
                                                                        while ( v240 );
                                                                        v243 = v237 - 1;
                                                                        v244 = v242 - 1;
                                                                        if ( v240 )
                                                                        {
                                                                          v243 = v237;
                                                                          v244 = v242;
                                                                        }
                                                                        *v243 = 0;
                                                                        if ( v240 )
                                                                        {
                                                                          v238 = 536 - v244;
                                                                          v245 = &Name[v244];
                                                                        }
                                                                        else
                                                                        {
                                                                          v245 = Name;
                                                                          Name[0] = 0;
                                                                        }
                                                                        if ( !v240 )
                                                                        {
                                                                          v249 = v238;
                                                                          goto LABEL_470;
                                                                        }
                                                                        v273 = v9;
                                                                        v246 = v245;
                                                                        if ( (unsigned __int64)(v238 - 1) > 0x7FFFFFFE )
                                                                        {
                                                                          v249 = v238;
                                                                          if ( v238 )
                                                                            *v245 = 0;
                                                                        }
                                                                        else
                                                                        {
                                                                          v247 = 2147483646;
                                                                          v248 = L"_Perf_Library_Lock_PID_";
                                                                          v249 = v238;
                                                                          v250 = 0;
                                                                          do
                                                                          {
                                                                            if ( !v247 )
                                                                              break;
                                                                            if ( !*v248 )
                                                                              break;
                                                                            *v245++ = *v248++;
                                                                            --v247;
                                                                            ++v250;
                                                                            --v238;
                                                                          }
                                                                          while ( v238 );
                                                                          v251 = v250 - 1;
                                                                          v252 = v245 - 1;
                                                                          if ( v238 )
                                                                          {
                                                                            v251 = v250;
                                                                            v252 = v245;
                                                                          }
                                                                          v253 = -2147024774;
                                                                          if ( v238 )
                                                                            v253 = 0;
                                                                          *v252 = 0;
                                                                          v245 = &v246[v251];
                                                                          if ( v238 )
                                                                          {
                                                                            v249 -= v251;
                                                                            goto LABEL_470;
                                                                          }
                                                                          v254 = v249 & 0x7FFFFFFFFFFFFFFFLL;
                                                                          if ( (v249 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
                                                                          {
                                                                            v245 = v246;
                                                                            *v246 = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            v254 = v249 - v251;
                                                                          }
                                                                          if ( v253 == -2147024774 )
                                                                          {
                                                                            v249 = v254;
LABEL_470:
                                                                            v246 = v245;
                                                                          }
                                                                        }
                                                                        CurrentProcessId = GetCurrentProcessId();
                                                                        _ultow_s(CurrentProcessId, Buffer, 0x20u, 16);
                                                                        if ( (int)StringCchCopyW(v246, v249, Buffer) < 0 )
                                                                          Buffer[0] = 0;
                                                                        TokenHandle = 0;
                                                                        memset(&v304, 0, sizeof(v304));
                                                                        CurrentThread = GetCurrentThread();
                                                                        v257 = NtOpenThreadToken(
                                                                                 CurrentThread,
                                                                                 4u,
                                                                                 1u,
                                                                                 &TokenHandle);
                                                                        if ( v257 >= 0 )
                                                                        {
                                                                          ThreadInformation = 0;
                                                                          v259 = 0;
                                                                          v258 = NtSetInformationThread(
                                                                                   (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                                                                   ThreadImpersonationToken,
                                                                                   &ThreadInformation,
                                                                                   8u) >= 0;
                                                                        }
                                                                        else
                                                                        {
                                                                          v258 = 0;
                                                                          v259 = PerfpDosError(v257);
                                                                        }
                                                                        v260 = g_SizeSD;
                                                                        if ( g_SizeSD )
                                                                        {
                                                                          v304.bInheritHandle = 0;
                                                                        }
                                                                        else
                                                                        {
                                                                          SD = PerflibCreateSD(v259);
                                                                          v304.bInheritHandle = 0;
                                                                          if ( !SD )
                                                                          {
                                                                            v304.nLength = 92;
                                                                            v262 = qword_180083120;
LABEL_482:
                                                                            v304.lpSecurityDescriptor = v262;
                                                                            *((_QWORD *)v9 + 1) = CreateMutexW(
                                                                                                    &v304,
                                                                                                    0,
                                                                                                    Name);
                                                                            if ( v258
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
                                                                            *((_DWORD *)v9 + 120) = v301;
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
LABEL_539:
                                                                                v9 = v273;
                                                                                v7 = *(void **)&v285.Length;
LABEL_508:
                                                                                SetLastError(LastError);
                                                                                v263 = v275;
                                                                                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28)
                                                                                    & 4) != 0
                                                                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                                                {
                                                                                  WPP_SF_Sd(
                                                                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                                                    30,
                                                                                    (unsigned int)WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids,
                                                                                    (_DWORD)v3,
                                                                                    v275);
                                                                                }
                                                                                if ( v263 )
                                                                                  DisableLibrary(
                                                                                    (HKEY)KeyHandle,
                                                                                    v3,
                                                                                    1u);
                                                                                if ( v9 )
                                                                                {
                                                                                  LocalFree(v9);
                                                                                  v9 = 0;
                                                                                }
                                                                                goto LABEL_515;
                                                                              }
                                                                              LastError = 14;
                                                                            }
LABEL_523:
                                                                            if ( !LastError )
                                                                            {
                                                                              v9 = v273;
                                                                              v7 = *(void **)&v285.Length;
LABEL_525:
                                                                              v265 = (char *)lpPerflibSectionAddr;
                                                                              if ( lpPerflibSectionAddr )
                                                                              {
                                                                                if ( *(_DWORD *)lpPerflibSectionAddr >= *((_DWORD *)lpPerflibSectionAddr + 1) )
                                                                                {
                                                                                  ++*((_DWORD *)lpPerflibSectionAddr + 2);
                                                                                  *((_QWORD *)v9 + 54) = 0;
                                                                                }
                                                                                else
                                                                                {
                                                                                  v266 = (unsigned int)(*(_DWORD *)lpPerflibSectionAddr + 1);
                                                                                  v267 = 2147483646;
                                                                                  *(_DWORD *)lpPerflibSectionAddr = v266;
                                                                                  v268 = 32;
                                                                                  v269 = (_WORD *)*((_QWORD *)v9 + 49);
                                                                                  v270 = &v265[128 * v266];
                                                                                  *((_QWORD *)v9 + 54) = v270;
                                                                                  do
                                                                                  {
                                                                                    if ( !v267 )
                                                                                      break;
                                                                                    if ( !*v269 )
                                                                                      break;
                                                                                    *(_WORD *)v270 = *v269++;
                                                                                    v270 += 2;
                                                                                    --v267;
                                                                                    --v268;
                                                                                  }
                                                                                  while ( v268 );
                                                                                  v271 = v270 - 2;
                                                                                  if ( v268 )
                                                                                    v271 = v270;
                                                                                  *(_WORD *)v271 = 0;
                                                                                }
                                                                              }
LABEL_515:
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
                                                                            goto LABEL_539;
                                                                          }
                                                                          v260 = g_SizeSD;
                                                                        }
                                                                        v304.nLength = v260;
                                                                        v262 = (__int64 *)&g_RuntimeSD;
                                                                        goto LABEL_482;
                                                                      }
                                                                      *v224 = 0;
                                                                    }
LABEL_496:
                                                                    v273 = v9;
                                                                    goto LABEL_521;
                                                                  }
                                                                }
                                                                v212 = v214;
                                                                v213 = v215;
                                                                goto LABEL_424;
                                                              }
                                                              *v214 = 0;
                                                            }
                                                            v273 = v9;
                                                            goto LABEL_521;
                                                          }
LABEL_520:
                                                          LOWORD(v138) = v190;
                                                          goto LABEL_521;
                                                        }
                                                        goto LABEL_501;
                                                      }
                                                    }
LABEL_502:
                                                    v273 = v9;
                                                    goto LABEL_521;
                                                  }
LABEL_522:
                                                  v3 = v274;
                                                  goto LABEL_523;
                                                }
                                                RtlInitUnicodeString((PUNICODE_STRING)&v304, L"Export");
                                                v154 = Size + 16;
                                                LODWORD(hKey) = Size + 16;
                                                v155 = Size + 16;
                                                v156 = operator new(
                                                         (unsigned int)(Size + 16),
                                                         (const struct std::nothrow_t *)&std::nothrow);
                                                v157 = v156;
                                                if ( v156 )
                                                {
                                                  memset_0(v156, 0, v155);
                                                  ValueKey = NtQueryValueKey(
                                                               v152,
                                                               (PUNICODE_STRING)&v304,
                                                               KeyValuePartialInformation,
                                                               v157,
                                                               v154,
                                                               (PULONG)&hKey);
                                                  if ( ((int)(ValueKey + 0x80000000) < 0 || ValueKey == -2147483643)
                                                    && (v159 = v157[2],
                                                        v153 = v157[1],
                                                        LODWORD(Size) = v159,
                                                        ValueKey >= 0) )
                                                  {
                                                    v160 = v159;
                                                    v161 = *(void **)&v285.Length;
                                                    memcpy_0(*(void **)&v285.Length, v157 + 3, v160);
                                                    ValueKey = 0;
                                                    LODWORD(Size) = v157[2];
                                                  }
                                                  else
                                                  {
                                                    v161 = *(void **)&v285.Length;
                                                  }
                                                  LocalFree(v157);
                                                  if ( ValueKey >= 0 )
                                                  {
                                                    v162 = 0;
LABEL_331:
                                                    if ( !v162 && (v153 == 1 || v153 == 7) )
                                                    {
                                                      LastError = 0;
                                                      v7 = *(void **)&v285.Length;
                                                      v163 = (unsigned __int64)(unsigned int)Size >> 1;
                                                      v164 = Size + 9;
                                                      LODWORD(Size) = Size + 2;
                                                      v165 = v288;
                                                      *(_WORD *)(*(_QWORD *)&v285.Length + 2 * v163) = 0;
                                                      v166 = (v164 & 0xFFFFFFF8) + v165;
                                                      goto LABEL_342;
                                                    }
                                                    goto LABEL_336;
                                                  }
                                                }
                                                else
                                                {
                                                  v161 = *(void **)&v285.Length;
                                                  ValueKey = -1073741801;
                                                }
                                                v162 = PerfpDosError(ValueKey);
                                                goto LABEL_331;
                                              }
LABEL_340:
                                              LODWORD(Size) = 0;
                                              LastError = 0;
                                              *(_QWORD *)&v285.Length = 0;
                                              goto LABEL_341;
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
                                        v278 = v135;
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
                      v278 = v85;
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
                              Src[v91] = v90;
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
                        v277 = v89;
                        v85 = v278;
                        if ( !v87 )
                          goto LABEL_207;
                        v92 = v277;
                        if ( v277 < 0x40 && v87 != v88 )
                        {
                          Src[v92] = wcstoul(v87, 0, 10);
                          v93 = (WCHAR *)((char *)v76 + v85);
                          v277 = v92 + 1;
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
                        v277 = 0;
                        if ( *v76 )
                        {
                          do
                          {
                            if ( v94 >= 0x40 )
                              break;
                            v95 = wcstoul(v87, 0, 10);
                            v96 = v94++;
                            Src[v96] = v95;
                            v97 = -1;
                            do
                              v39 = v87[++v97] == 0;
                            while ( !v39 );
                            v87 += v97 + 1;
                          }
                          while ( *v87 );
                          v277 = v94;
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
            v279 = 0;
            v311 = 0;
            RtlInitUnicodeString(&v311, L"Collect Timeout");
            v279 = 20;
            v61 = operator new(0x14u, (const struct std::nothrow_t *)&std::nothrow);
            v62 = v61;
            if ( v61 )
            {
              *(_OWORD *)v61 = 0;
              v61[4] = 0;
              v63 = NtQueryValueKey(v52, &v311, KeyValuePartialInformation, v61, 0x14u, &v279);
              if ( (int)(v63 + 0x80000000) < 0 || v63 == -2147483643 )
              {
                v50 = v62[1];
                if ( v63 >= 0 )
                {
                  memcpy_0(&v280, v62 + 3, (unsigned int)v62[2]);
                  v63 = 0;
                  v290 = v280;
                }
              }
              LocalFree(v62);
              if ( v63 >= 0 )
              {
                v64 = 0;
LABEL_141:
                if ( v64 || v50 != 4 )
                  v290 = dwExtCtrOpenProcWaitMs;
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
          v291 = v31;
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
          v302 = v25;
          v23 = 8;
          goto LABEL_39;
        }
      }
      v23 = 8;
      v25 = (unsigned __int8 *)(v21 + 8);
      v302 = v25;
LABEL_39:
      if ( (*((_BYTE *)v26 + 28) & 4) != 0 && *((_BYTE *)v26 + 25) >= 2u )
        WPP_SF_S(v26[2], 17, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v3);
      goto LABEL_42;
    }
LABEL_536:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, v3);
    goto LABEL_508;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids, 5896);
  return 0;
}

```

## disassembly

```asm
0x180018470  push    rbp
0x180018472  push    rbx
0x180018473  push    rsi
0x180018474  push    rdi
0x180018475  push    r12
0x180018477  lea     rbp, [rsp-780h]
0x18001847f  sub     rsp, 880h
0x180018486  mov     rax, cs:__security_cookie
0x18001848d  xor     rax, rsp
0x180018490  mov     [rbp+7A0h+var_50], rax
0x180018497  mov     r12, [r8+8]
0x18001849b  xor     esi, esi
0x18001849d  mov     [rbp+7A0h+hKey], rcx
0x1800184a1  mov     rdi, rdx
0x1800184a4  mov     ecx, esi
0x1800184a6  mov     [rbp+7A0h+ThreadInformation], r8
0x1800184aa  mov     [rbp+7A0h+var_820], ecx
0x1800184ad  mov     [rsp+8A0h+var_828], ecx
0x1800184b1  mov     [rbp+7A0h+var_81C], ecx
0x1800184b4  mov     [rsp+8A0h+var_824], ecx
0x1800184b8  mov     [rbp+7A0h+KeyHandle], rdx
0x1800184bc  mov     [rbp+7A0h+phkResult], rsi
0x1800184c0  mov     [rsp+8A0h+var_850], r12
0x1800184c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184cc  test    byte ptr [rcx+1Ch], 4
0x1800184d0  jz      short loc_1800184F0
0x1800184d2  cmp     byte ptr [rcx+19h], 4
0x1800184d6  jb      short loc_1800184F0
0x1800184d8  mov     rcx, [rcx+10h]
0x1800184dc  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x1800184e3  mov     edx, 0Ah
0x1800184e8  mov     r9, r12
0x1800184eb  call    WPP_SF_S
0x1800184f0  mov     rbx, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x1800184f7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800184fe  mov     [rbp+7A0h+var_778], rsi
0x180018502  mov     [rbp+7A0h+hMem], rbx
0x180018506  test    rbx, rbx
0x180018509  jz      short loc_180018573
0x18001850b  nop     dword ptr [rax+rax+00h]
0x180018510  mov     rcx, [rbx+188h]; lpString1
0x180018517  mov     r9d, eax; cchCount2
0x18001851a  mov     r8, r12; lpString2
0x18001851d  mov     [rsp+8A0h+bIgnoreCase], 1; bIgnoreCase
0x180018525  mov     edx, eax; cchCount1
0x180018527  call    cs:__imp_CompareStringOrdinal
0x18001852d  cmp     eax, 2
0x180018530  jz      short loc_18001854B
0x180018532  mov     [rbp+7A0h+var_778], rbx
0x180018536  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001853d  mov     rbx, [rbx]
0x180018540  mov     [rbp+7A0h+hMem], rbx
0x180018544  test    rbx, rbx
0x180018547  jnz     short loc_180018510
0x180018549  jmp     short loc_180018573
0x18001854b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018552  test    byte ptr [rcx+1Ch], 4
0x180018556  jz      short loc_180018573
0x180018558  cmp     byte ptr [rcx+19h], 4
0x18001855c  jb      short loc_180018573
0x18001855e  mov     rcx, [rcx+10h]
0x180018562  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x180018569  mov     edx, 0Bh
0x18001856e  call    WPP_SF_
0x180018573  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001857a  mov     ecx, 1708h; unsigned __int64
0x18001857f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018584  mov     [rbp+7A0h+lpSrc], rax
0x180018588  test    rax, rax
0x18001858b  jz      loc_18001A7B4
0x180018591  mov     [rsp+8A0h+arg_18], r13
0x180018599  xor     edx, edx; Val
0x18001859b  mov     [rsp+8A0h+var_28], r14
0x1800185a3  mov     r8d, 1708h; Size
0x1800185a9  mov     [rsp+8A0h+var_30], r15
0x1800185b1  mov     rcx, rax; void *
0x1800185b4  movaps  [rsp+8A0h+var_40], xmm6
0x1800185bc  call    memset_0
0x1800185c1  mov     eax, cs:?dwExtCtrOpenProcWaitMs@@3KA; ulong dwExtCtrOpenProcWaitMs
0x1800185c7  mov     r13, rsi
0x1800185ca  mov     [rbp+7A0h+var_7EC], eax
0x1800185cd  xorps   xmm6, xmm6
0x1800185d0  mov     [rsp+8A0h+var_82C], eax
0x1800185d4  xorps   xmm0, xmm0
0x1800185d7  mov     [rbp+7A0h+var_7F0], eax
0x1800185da  mov     r15, rsi
0x1800185dd  mov     [rsp+8A0h+var_844], eax
0x1800185e1  mov     r14d, esi
0x1800185e4  lea     rax, [rdi-1]
0x1800185e8  mov     [rsp+8A0h+var_858], rsi
0x1800185ed  mov     qword ptr [rbp+7A0h+var_818.Length], rsi
0x1800185f1  mov     [rsp+8A0h+var_848], esi
0x1800185f5  mov     esi, 430h
0x1800185fa  mov     [rbp+7A0h+var_7B4], 3E8h
0x180018601  mov     [rbp+7A0h+var_7D0], r13d
0x180018605  movups  [rbp+7A0h+var_6B8], xmm6
0x18001860c  movups  xmmword ptr [rbp+7A0h+DestinationString.Length], xmm0
0x180018610  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018614  ja      loc_18001A769
0x18001861a  lea     rdx, ?DLLValue@@3QBGB; "Library"
0x180018621  lea     rcx, [rbp+7A0h+DestinationString]; DestinationString
0x180018625  call    cs:__imp_RtlInitUnicodeString
0x18001862b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018632  mov     [rbp+7A0h+var_7D0], 440h
0x180018639  mov     ecx, 440h; unsigned __int64
0x18001863e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018643  mov     rbx, rax
0x180018646  test    rax, rax
0x180018649  jz      short loc_1800186C9
0x18001864b  xor     edx, edx; Val
0x18001864d  mov     r8d, 440h; Size
0x180018653  mov     rcx, rax; void *
0x180018656  call    memset_0
0x18001865b  lea     rax, [rbp+7A0h+var_7D0]
0x18001865f  mov     r9, rbx; KeyValueInformation
0x180018662  mov     [rsp+8A0h+ResultLength], rax; ResultLength
0x180018667  lea     rdx, [rbp+7A0h+DestinationString]; ValueName
0x18001866b  mov     r8d, 2; KeyValueInformationClass
0x180018671  mov     [rsp+8A0h+bIgnoreCase], 440h; Length
0x180018679  mov     rcx, rdi; KeyHandle
0x18001867c  call    cs:__imp_NtQueryValueKey
0x180018682  mov     edi, eax
0x180018684  mov     eax, 80000000h
0x180018689  lea     ecx, [rdi+rax]
0x18001868c  test    eax, ecx
0x18001868e  jnz     short loc_180018698
0x180018690  cmp     edi, 80000005h
0x180018696  jnz     short loc_1800186B8
0x180018698  mov     r14d, [rbx+4]
0x18001869c  mov     esi, [rbx+8]
0x18001869f  test    edi, edi
0x1800186a1  js      short loc_1800186B8
0x1800186a3  mov     rcx, [rbp+7A0h+lpSrc]; void *
0x1800186a7  lea     rdx, [rbx+0Ch]; Src
0x1800186ab  mov     r8d, esi; Size
0x1800186ae  call    memcpy_0
0x1800186b3  mov     esi, [rbx+8]
0x1800186b6  xor     edi, edi
0x1800186b8  mov     rcx, rbx; hMem
0x1800186bb  call    cs:__imp_LocalFree
0x1800186c1  test    edi, edi
0x1800186c3  js      short loc_1800186CE
0x1800186c5  xor     edi, edi
0x1800186c7  jmp     short loc_1800186D7
0x1800186c9  mov     edi, 0C0000017h
0x1800186ce  mov     ecx, edi; int
0x1800186d0  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x1800186d5  mov     edi, eax
0x1800186d7  test    edi, edi
0x1800186d9  jnz     loc_18001A76E
0x1800186df  mov     r9, [rbp+7A0h+lpSrc]
0x1800186e3  xor     eax, eax
0x1800186e5  mov     ecx, esi
0x1800186e7  mov     edi, 0FFFFFFF8h
0x1800186ec  add     esi, 8
0x1800186ef  shr     rcx, 1
0x1800186f2  and     rsi, rdi
0x1800186f5  mov     r13d, 210h
0x1800186fb  mov     ebx, 218h
0x180018700  mov     [r9+rcx*2], ax
0x180018705  lea     r15, [r9+rsi]
0x180018709  mov     [rbp+7A0h+lpString2], r15
0x18001870d  cmp     r14d, 2
0x180018711  jnz     loc_1800187FF
0x180018717  mov     r8d, ebx; nSize
0x18001871a  mov     rdx, r15; lpDst
0x18001871d  mov     rcx, r9; lpSrc
0x180018720  call    cs:__imp_ExpandEnvironmentStringsW
0x180018726  lea     ecx, [rax-1]
0x180018729  cmp     ecx, 217h
0x18001872f  ja      short loc_180018750
0x180018731  lea     eax, ds:9[rax*2]
0x180018738  mov     esi, 8
0x18001873d  and     rax, rdi
0x180018740  add     r15, rax
0x180018743  mov     [rbp+7A0h+var_7B0], r15
0x180018747  lea     r13, [rax+210h]
0x18001874e  jmp     short loc_180018770
0x180018750  mov     rcx, cs:WPP_GLOBAL_Control
0x180018757  mov     edi, 482h
0x18001875c  mov     esi, 8
0x180018761  add     r15, rsi
0x180018764  mov     [rbp+7A0h+var_7B0], r15
0x180018768  test    edi, edi
0x18001876a  jnz     loc_180018877
0x180018770  mov     dword ptr [rsp+8A0h+Size], ebx
0x180018774  lea     rax, [rsp+8A0h+Size]
0x180018779  mov     rbx, [rbp+7A0h+KeyHandle]
0x18001877d  lea     r9, [rsp+8A0h+var_830]; unsigned int *
0x180018782  xor     r14d, r14d
0x180018785  lea     rdx, ?OpenValue@@3QBGB; "Open"
0x18001878c  mov     [rsp+8A0h+var_870], r14d; int
0x180018791  mov     rcx, rbx; KeyHandle
0x180018794  mov     [rsp+8A0h+ResultLength], rax; unsigned int *
0x180018799  mov     r12, r15
0x18001879c  mov     qword ptr [rsp+8A0h+bIgnoreCase], r15; unsigned __int8 *
0x1800187a1  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x1800187a6  mov     edi, eax
0x1800187a8  test    eax, eax
0x1800187aa  jnz     loc_180018951
0x1800187b0  cmp     [r15], r14b
0x1800187b3  jz      loc_180018948
0x1800187b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187c0  test    byte ptr [rcx+1Ch], 4
0x1800187c4  jz      short loc_1800187E7
0x1800187c6  cmp     byte ptr [rcx+19h], 4
0x1800187ca  jb      short loc_1800187E7
0x1800187cc  mov     r8, [rsp+8A0h+var_850]
0x1800187d1  mov     edx, 10h
0x1800187d6  mov     rcx, [rcx+10h]
0x1800187da  mov     r9, r15
0x1800187dd  mov     qword ptr [rsp+8A0h+bIgnoreCase], r8
0x1800187e2  call    WPP_SF_sS
0x1800187e7  mov     eax, dword ptr [rsp+8A0h+Size]
0x1800187eb  mov     ecx, 0FFFFFFF8h
0x1800187f0  lea     esi, [rax+8]
0x1800187f3  mov     [rax+r15], r14b
0x1800187f7  and     rsi, rcx
0x1800187fa  jmp     loc_180018A89
0x1800187ff  cmp     r14d, 1
0x180018803  jnz     short loc_18001882B
0x180018805  mov     r8, rsi; Size
0x180018808  mov     rdx, r9; Src
0x18001880b  mov     rcx, r15; void *
0x18001880e  call    memcpy_0
0x180018813  add     r15, rsi
0x180018816  lea     r13, [rsi+210h]
0x18001881d  mov     [rbp+7A0h+var_7B0], r15
0x180018821  mov     esi, 8
0x180018826  jmp     loc_180018770
0x18001882b  mov     edi, 482h
0x180018830  mov     rcx, cs:WPP_GLOBAL_Control
0x180018837  test    byte ptr [rcx+1Ch], 4
0x18001883b  jz      loc_18001875C
0x180018841  cmp     byte ptr [rcx+19h], 2
0x180018845  jb      loc_18001875C
0x18001884b  mov     rcx, [rcx+10h]
0x18001884f  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x180018856  mov     edx, 0Dh
0x18001885b  mov     r9d, edi
0x18001885e  call    WPP_SF_d
0x180018863  mov     rcx, cs:WPP_GLOBAL_Control
0x18001886a  add     r15, 8
0x18001886e  mov     [rbp+7A0h+var_7B0], r15
0x180018872  mov     esi, 8
0x180018877  test    byte ptr [rcx+1Ch], 4
0x18001887b  jz      short loc_18001889B
0x18001887d  cmp     byte ptr [rcx+19h], 2
0x180018881  jb      short loc_18001889B
0x180018883  mov     rcx, [rcx+10h]
0x180018887  lea     r8, WPP_0fec710e7ed83f9f7c16dab251b4958d_Traceguids
0x18001888e  mov     edx, 11h
0x180018893  mov     r9, r12
0x180018896  call    WPP_SF_S
0x18001889b  add     rsi, r15
0x18001889e  mov     r14d, 8
0x1800188a4  mov     [rbp+7A0h+var_7E8], rsi
0x1800188a8  test    edi, edi
0x1800188aa  jnz     loc_180018CB7
0x1800188b0  mov     rcx, [rbp+7A0h+KeyHandle]; KeyHandle
0x1800188b4  lea     rax, [rsp+8A0h+Size]
0x1800188b9  mov     [rsp+8A0h+var_870], 0; int
0x1800188c1  lea     r9, [rsp+8A0h+var_830]; unsigned int *
0x1800188c6  mov     [rsp+8A0h+ResultLength], rax; unsigned int *
0x1800188cb  lea     rdx, ?CloseValue@@3QBGB; "Close"
0x1800188d2  mov     qword ptr [rsp+8A0h+bIgnoreCase], rsi; unsigned __int8 *
0x1800188d7  mov     rbx, rsi
0x1800188da  mov     dword ptr [rsp+8A0h+Size], 218h
0x1800188e2  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x1800188e7  mov     edi, eax
0x1800188e9  test    eax, eax
0x1800188eb  jnz     loc_180018B87
0x1800188f1  cmp     [rsi], al
0x1800188f3  jz      loc_180018B7C
0x1800188f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018900  test    byte ptr [rcx+1Ch], 4
0x180018904  jz      short loc_180018927
0x180018906  cmp     byte ptr [rcx+19h], 4
0x18001890a  jb      short loc_180018927
0x18001890c  mov     rax, [rsp+8A0h+var_850]
0x180018911  mov     edx, 14h
0x180018916  mov     rcx, [rcx+10h]
0x18001891a  mov     r9, rsi
0x18001891d  mov     qword ptr [rsp+8A0h+bIgnoreCase], rax
0x180018922  call    WPP_SF_sS
0x180018927  mov     r14d, dword ptr [rsp+8A0h+Size]
0x18001892c  lea     r12, aNull_0; "NULL"
0x180018933  add     r14d, 8
0x180018937  mov     eax, 0FFFFFFF8h
0x18001893c  and     r14, rax
0x18001893f  lea     r15, [r14+rbx]
0x180018943  jmp     loc_180018CCA
0x180018948  mov     edi, 1
0x18001894d  mov     eax, edi
0x18001894f  jmp     short loc_180018967
0x180018951  cmp     eax, 2
0x180018954  jz      short loc_18001895D
0x180018956  cmp     eax, 0EAh
0x18001895b  jnz     short loc_180018964
0x18001895d  mov     eax, 1
  ... truncated ...
```
