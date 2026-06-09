# InstallLayoutOrTipPrivateWorker(ushort const *,ulong)

- ea: `0x180005500`
- end: `0x180006d84`
- name: `?InstallLayoutOrTipPrivateWorker@@YAHPEBGK@Z`
- size: `6276`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a584`
- `0x1800962b0`

## callees

- `0x180002344`
- `0x180002f10`
- `0x180003a80`
- `0x1800040e0`
- `0x180004b70`
- `0x180005500`
- `0x180007fc0`
- `0x180007ff0`
- `0x180008094`
- `0x1800080d0`
- `0x180008a60`
- `0x18000a6d8`
- `0x18000a72c`
- `0x18000a7d0`
- `0x18001da0c`
- `0x180032ae4`
- `0x180033180`
- `0x1800332d0`
- `0x180038170`
- `0x18003a1b0`
- `0x18003b314`
- `0x1800460fc`
- `0x180046194`
- `0x18004704c`
- `0x1800483e4`
- `0x18004b62c`
- `0x18004c210`
- `0x180061470`
- `0x180063ffc`
- `0x180064224`
- `0x1800646dc`
- `0x18006c000`
- `0x18006caa0`
- `0x18006cad0`
- `0x18006f4c0`
- `0x18009662c`
- `0x1800967bc`
- `0x1800968b8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180005dc9`
- `KERNEL32!LocalAlloc` at `0x180005dfc`
- `KERNEL32!LocalAlloc` at `0x180005dc9`
- `KERNEL32!LocalAlloc` at `0x180005dfc`
- `KERNEL32!InitializeCriticalSection` at `0x180005e21`
- `KERNEL32!InitializeCriticalSection` at `0x180005e3f`
- `KERNEL32!InitializeCriticalSection` at `0x180006256`
- `KERNEL32!InitializeCriticalSection` at `0x180005e21`
- `KERNEL32!InitializeCriticalSection` at `0x180005e3f`
- `KERNEL32!InitializeCriticalSection` at `0x180006256`
- `KERNEL32!LocalFree` at `0x180005b59`
- `KERNEL32!LocalFree` at `0x180005b63`
- `KERNEL32!LocalFree` at `0x1800066fa`
- `KERNEL32!LocalFree` at `0x180005b59`
- `KERNEL32!LocalFree` at `0x180005b63`
- `KERNEL32!LocalFree` at `0x1800066fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800062b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800063af`
- `KERNEL32!LeaveCriticalSection` at `0x18000658c`
- `KERNEL32!LeaveCriticalSection` at `0x1800062b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800063af`
- `KERNEL32!LeaveCriticalSection` at `0x18000658c`
- `KERNEL32!EnterCriticalSection` at `0x180006263`
- `KERNEL32!EnterCriticalSection` at `0x18000636b`
- `KERNEL32!EnterCriticalSection` at `0x180006548`
- `KERNEL32!EnterCriticalSection` at `0x180006263`
- `KERNEL32!EnterCriticalSection` at `0x18000636b`
- `KERNEL32!EnterCriticalSection` at `0x180006548`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800066e9`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800066e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000581f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000587a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000598f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006020`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000581f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000587a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000598f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006020`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006058`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005730`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000583b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000593c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005aa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005acc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005af5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000606b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ca7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005730`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000583b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000593c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800059a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005aa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005acc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005ae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005af5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000606b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ca7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005709`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800057b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005915`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005ce4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005d43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006a33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006af0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006b51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006c0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005709`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800057b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005915`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005ce4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005d43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006a33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006af0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006b51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006c0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800056c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000576d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800058c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800056c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000576d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800058c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005da6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005da6`

## string_xrefs

- `0x1800055a8`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180005a25`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180005c7e`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180006788`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x1800068de`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180005534`: `InstallLayoutOrTipPrivateWorker`

## pseudocode

```c
__int64 __fastcall InstallLayoutOrTipPrivateWorker(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v4; // eax
  __int16 v7; // r12
  const WCHAR *v8; // rsi
  int v9; // r12d
  HKEY v10; // rdi
  HKEY v11; // r15
  HKEY v12; // r14
  LSTATUS v13; // eax
  LSTATUS v14; // ebx
  const WCHAR *v15; // rsi
  HKEY v16; // r14
  LSTATUS v17; // eax
  LSTATUS v18; // ebx
  LSTATUS v19; // eax
  LSTATUS v20; // ecx
  LSTATUS v21; // eax
  LSTATUS v22; // ecx
  HKEY v23; // rsi
  LSTATUS v24; // eax
  unsigned __int16 *v25; // r9
  LSTATUS v26; // ebx
  LSTATUS v27; // eax
  unsigned __int16 *v28; // r9
  LSTATUS v29; // edx
  unsigned __int16 *v30; // r9
  HKEY v31; // r13
  char v32; // cl
  DWORD v33; // ebx
  HLOCAL v34; // rax
  DWORD v35; // edx
  unsigned int v36; // ebx
  HLOCAL v37; // rax
  unsigned int v38; // ecx
  DWORD v39; // r15d
  int v40; // r12d
  int v41; // r14d
  unsigned int v42; // r15d
  char v43; // r12
  __int128 v44; // xmm6
  __int128 v45; // xmm7
  __int128 v46; // xmm8
  __int128 v47; // xmm9
  __int128 v48; // xmm10
  __int128 v49; // xmm11
  __int128 v50; // xmm12
  int *v51; // rsi
  unsigned int v52; // ebx
  int v53; // edi
  int v54; // r8d
  unsigned int i; // r9d
  __int64 v56; // rcx
  __int64 v57; // rax
  _WORD *v58; // r10
  unsigned __int8 v59; // dl
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rcx
  int v63; // r8d
  __int64 v64; // r9
  __int64 v65; // rcx
  __int64 v66; // rax
  _WORD *v67; // r10
  unsigned __int8 v68; // dl
  __int64 v69; // rcx
  _QWORD *v70; // rbx
  __int16 v71; // di
  _WORD *v72; // rax
  char *v73; // rbx
  _WORD *v74; // rsi
  _QWORD *v75; // rcx
  _DWORD *v76; // rbx
  __int128 *v77; // rdx
  __int64 v78; // rax
  __int128 *v79; // rcx
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int128 v90; // xmm1
  _QWORD *v91; // rcx
  __int16 v92; // di
  __int64 **k; // rcx
  _DWORD *v94; // rbx
  _QWORD *v95; // rcx
  _QWORD *m; // rcx
  _WORD *v97; // rax
  _QWORD *n; // r10
  __int64 v99; // r9
  int v100; // eax
  unsigned __int16 *v101; // rax
  int v102; // ecx
  int v103; // edx
  HKEY v104; // rbx
  unsigned __int16 *v105; // rdi
  unsigned int v106; // ebx
  int v107; // eax
  unsigned __int16 *v108; // rdi
  unsigned int v109; // ebx
  __int64 v110; // r9
  int v111; // eax
  __int64 **j; // rdx
  LSTATUS v113; // eax
  LSTATUS v114; // eax
  unsigned int v115; // ebx
  unsigned __int16 *v116; // rax
  int v117; // ecx
  int v118; // edx
  __int64 v119; // rsi
  __int64 AssemblySortOrder; // rax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  bool dwOptionsc; // [rsp+20h] [rbp-E0h]
  bool dwOptionsd; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int samDesireda; // [rsp+28h] [rbp-D8h]
  unsigned int samDesiredb; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributesa; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributesb; // [rsp+30h] [rbp-D0h]
  unsigned int *v132; // [rsp+38h] [rbp-C8h]
  unsigned int *v133; // [rsp+38h] [rbp-C8h]
  unsigned int *v134; // [rsp+38h] [rbp-C8h]
  bool IsLoaded; // [rsp+60h] [rbp-A0h]
  HKEY v136; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  char v139; // [rsp+80h] [rbp-80h]
  bool v140[8]; // [rsp+88h] [rbp-78h] BYREF
  HKEY v141; // [rsp+90h] [rbp-70h]
  __int64 v142; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v143; // [rsp+A0h] [rbp-60h]
  void **v144; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v145; // [rsp+B0h] [rbp-50h]
  __int64 v146; // [rsp+B8h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-40h]
  void **v148; // [rsp+C8h] [rbp-38h] BYREF
  HKEY v149; // [rsp+D0h] [rbp-30h]
  void **v150; // [rsp+D8h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h]
  unsigned int v152; // [rsp+E8h] [rbp-18h]
  DWORD cbData; // [rsp+ECh] [rbp-14h] BYREF
  void **v154; // [rsp+F0h] [rbp-10h] BYREF
  HKEY v155; // [rsp+F8h] [rbp-8h]
  DWORD cValues; // [rsp+100h] [rbp+0h] BYREF
  int v157; // [rsp+104h] [rbp+4h]
  BOOL v158; // [rsp+108h] [rbp+8h]
  void **v159; // [rsp+110h] [rbp+10h] BYREF
  HKEY v160; // [rsp+118h] [rbp+18h]
  void **v161; // [rsp+120h] [rbp+20h] BYREF
  HKEY v162; // [rsp+128h] [rbp+28h]
  void **v163; // [rsp+130h] [rbp+30h] BYREF
  HKEY v164; // [rsp+138h] [rbp+38h]
  void **v165; // [rsp+140h] [rbp+40h] BYREF
  HKEY v166; // [rsp+148h] [rbp+48h]
  __int128 v167; // [rsp+150h] [rbp+50h] BYREF
  int v168; // [rsp+160h] [rbp+60h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+168h] [rbp+68h] BYREF
  __int128 v170; // [rsp+190h] [rbp+90h] BYREF
  int v171; // [rsp+1A0h] [rbp+A0h]
  struct _RTL_CRITICAL_SECTION v172; // [rsp+1A8h] [rbp+A8h] BYREF
  void **v173; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v174[272]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v175[8]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v176[48]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _WORD v177[2]; // [rsp+320h] [rbp+220h] BYREF
  unsigned int v178; // [rsp+324h] [rbp+224h]
  int v179; // [rsp+32Ch] [rbp+22Ch]
  _WORD v180[39]; // [rsp+334h] [rbp+234h] BYREF
  _WORD v181[303]; // [rsp+382h] [rbp+282h] BYREF
  wchar_t Data[8]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v183[8]; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int128 v184; // [rsp+600h] [rbp+500h]
  __int128 v185; // [rsp+610h] [rbp+510h]
  __int128 v186; // [rsp+620h] [rbp+520h]
  __int128 v187; // [rsp+630h] [rbp+530h]
  _OWORD v188[6]; // [rsp+640h] [rbp+540h]
  unsigned __int16 v189[40]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v190[88]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _BYTE v191[176]; // [rsp+7A0h] [rbp+6A0h] BYREF
  WCHAR SubKey[264]; // [rsp+850h] [rbp+750h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B08h] [rbp+A08h]

  v152 = a2;
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v173);
  v173 = &InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable';
  InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::StartActivity((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)&v173);
  v4 = a2 >> 5;
  LOBYTE(v4) = (a2 & 0x20) == 0;
  cbData = a2 & 0x40;
  v158 = v4;
  v157 = a2 & 0x100;
  IsLoaded = EnsureBcp47LangsLibraryIsLoaded();
  if ( (a2 & 0x40) != 0 && (a2 & 0x100) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4BD,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      dwOptions);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v173, 2147500037LL);
    v173 = &InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable';
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v173);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v176);
    wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v175);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v174);
    return 0;
  }
  v7 = a2;
  v161 = &CInputDllRegKey::`vftable';
  v150 = &CInputDllRegKey::`vftable';
  v8 = L"TextInputDrt\\Keyboard Layout\\Preload";
  *(_QWORD *)v140 = &CInputDllRegKey::`vftable';
  v144 = &CInputDllRegKey::`vftable';
  v9 = v7 & 0x200;
  v159 = &CInputDllRegKey::`vftable';
  v154 = &CInputDllRegKey::`vftable';
  v10 = 0;
  v148 = &CInputDllRegKey::`vftable';
  v11 = 0;
  v165 = &CInputDllRegKey::`vftable';
  v163 = &CInputDllRegKey::`vftable';
  if ( !v9 )
    v8 = L"Keyboard Layout\\Preload";
  v162 = 0;
  hKey = 0;
  v141 = 0;
  v145 = 0;
  v160 = 0;
  v155 = 0;
  v149 = 0;
  v166 = 0;
  v164 = 0;
  dwDisposition = 0;
  v136 = 0;
  phkResult = 0;
  v12 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v12 = phkResult;
  v13 = RegCreateKeyExW(v12, v8, 0, 0, 0, 0x2001Fu, 0, &v136, &dwDisposition);
  v14 = v13;
  if ( v13 )
  {
    if ( v13 == 5 )
    {
      v14 = RegCreateKeyExW(v12, v8, 0, 0, 4u, 0x2001Fu, 0, &v136, &dwDisposition);
      if ( !v14 )
      {
        v113 = CInputDllRegKey::Close((CInputDllRegKey *)&v161);
        v10 = v136;
        v14 = v113;
        v162 = v136;
      }
    }
  }
  else
  {
    v10 = v136;
    v14 = 0;
    v162 = v136;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v14 )
    goto LABEL_90;
  v15 = L"TextInputDrt\\Keyboard Layout\\Substitutes";
  if ( !v9 )
    v15 = L"Keyboard Layout\\Substitutes";
  dwDisposition = 0;
  v136 = 0;
  phkResult = 0;
  v16 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v16 = phkResult;
  v17 = RegCreateKeyExW(v16, v15, 0, 0, 0, 0x2001Fu, 0, &v136, &dwDisposition);
  v18 = v17;
  if ( v17 )
  {
    if ( v17 == 5 )
    {
      v18 = RegCreateKeyExW(v16, v15, 0, 0, 4u, 0x2001Fu, 0, &v136, &dwDisposition);
      if ( !v18 )
      {
        v18 = CInputDllRegKey::Close((CInputDllRegKey *)&v150);
        hKey = v136;
      }
    }
  }
  else
  {
    v18 = 0;
    if ( hKey )
      v18 = RegCloseKey(hKey);
    hKey = v136;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v18 )
    goto LABEL_90;
  v136 = 0;
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Keyboard Layouts", 0, 0x20019u, &v136);
  if ( !v19 )
    goto LABEL_26;
  if ( v19 != 5 )
  {
LABEL_233:
    if ( CInputDllRegKey::Open(
           (CInputDllRegKey *)v140,
           HKEY_LOCAL_MACHINE,
           L"System\\ControlSet001\\Control\\Keyboard Layouts",
           0x20019u) )
    {
      goto LABEL_90;
    }
    goto LABEL_30;
  }
  dwDisposition = 0;
  v20 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Keyboard Layouts",
          0,
          0,
          4u,
          0x20019u,
          0,
          &v136,
          &dwDisposition);
  if ( !v20 )
  {
LABEL_26:
    v20 = 0;
    if ( v141 )
      v20 = RegCloseKey(v141);
    v141 = v136;
  }
  if ( v20 )
    goto LABEL_233;
LABEL_30:
  v136 = 0;
  v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Nls\\Locale", 0, 0x20019u, &v136);
  if ( !v21 )
    goto LABEL_31;
  if ( v21 != 5 )
  {
LABEL_235:
    if ( CInputDllRegKey::Open(
           (CInputDllRegKey *)&v144,
           HKEY_LOCAL_MACHINE,
           L"System\\ControlSet001\\Control\\Nls\\Locale",
           0x20019u) )
    {
      goto LABEL_90;
    }
    goto LABEL_35;
  }
  dwDisposition = 0;
  v22 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Nls\\Locale",
          0,
          0,
          4u,
          0x20019u,
          0,
          &v136,
          &dwDisposition);
  if ( !v22 )
  {
LABEL_31:
    v22 = 0;
    if ( v145 )
      v22 = RegCloseKey(v145);
    v145 = v136;
  }
  if ( v22 )
    goto LABEL_235;
LABEL_35:
  dwDisposition = 0;
  v136 = 0;
  phkResult = 0;
  v23 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v23 = phkResult;
  v24 = RegCreateKeyExW(v23, L"Software\\Microsoft\\CTF\\TIP", 0, 0, 0, 0x2001Fu, 0, &v136, &dwDisposition);
  v26 = v24;
  if ( v24 )
  {
    if ( v24 == 5 )
    {
      v26 = RegCreateKeyExW(v23, L"Software\\Microsoft\\CTF\\TIP", 0, 0, 4u, 0x2001Fu, 0, &v136, &dwDisposition);
      if ( !v26 )
      {
        v114 = CInputDllRegKey::Close((CInputDllRegKey *)&v159);
        v11 = v136;
        v26 = v114;
        v160 = v136;
      }
    }
  }
  else
  {
    v11 = v136;
    v26 = 0;
    v160 = v136;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v26
    || (unsigned int)CInputDllRegKey::Create(
                       (CInputDllRegKey *)&v154,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\CTF\\HiddenDummyLayouts",
                       v25,
                       dwOptionsa,
                       samDesired,
                       lpSecurityAttributes,
                       v132) )
  {
    goto LABEL_90;
  }
  v136 = 0;
  v27 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\CTF\\TIP", 0, 0x20019u, &v136);
  if ( !v27 )
    goto LABEL_44;
  if ( v27 != 5 )
  {
LABEL_241:
    if ( v9 )
      goto LABEL_48;
LABEL_90:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      dwOptionsa);
    goto LABEL_52;
  }
  dwDisposition = 0;
  v29 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\CTF\\TIP",
          0,
          0,
          4u,
          0x20019u,
          0,
          &v136,
          &dwDisposition);
  if ( !v29 )
  {
LABEL_44:
    v29 = 0;
    if ( v149 )
      v29 = RegCloseKey(v149);
    v149 = v136;
  }
  if ( v29 )
    goto LABEL_241;
LABEL_48:
  if ( (unsigned int)CInputDllRegKey::Create(
                       (CInputDllRegKey *)&v165,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\CTF\\SortOrder\\Language",
                       v28,
                       dwOptionsa,
                       samDesireda,
                       lpSecurityAttributesa,
                       v133)
    || (unsigned int)CInputDllRegKey::Create(
                       (CInputDllRegKey *)&v163,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\CTF\\SortOrder\\AssemblyItem",
                       v30,
                       dwOptionsa,
                       samDesiredb,
                       lpSecurityAttributesb,
                       v134) )
  {
    goto LABEL_90;
  }
  v31 = (HKEY)ParseItemString(a1);
  phkResult = v31;
  if ( !v31 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D4,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      dwOptionsa);
LABEL_52:
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v173, 2147500037LL);
    if ( v164 )
      RegCloseKey(v164);
    if ( v166 )
      RegCloseKey(v166);
    v148 = &CInputDllRegKey::`vftable';
    if ( v149 )
    {
      RegCloseKey(v149);
      v149 = 0;
    }
    v154 = &CInputDllRegKey::`vftable';
    if ( v155 )
    {
      RegCloseKey(v155);
      v155 = 0;
    }
    if ( v11 )
      RegCloseKey(v11);
    v144 = &CInputDllRegKey::`vftable';
    if ( v145 )
    {
      RegCloseKey(v145);
      v145 = 0;
    }
    *(_QWORD *)v140 = &CInputDllRegKey::`vftable';
    if ( v141 )
    {
      RegCloseKey(v141);
      v141 = 0;
    }
    v150 = &CInputDllRegKey::`vftable';
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( v10 )
      RegCloseKey(v10);
    v173 = &InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable';
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v173);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v176);
    wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v175);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v174);
    return 0;
  }
  v32 = v152 & 1;
  v152 &= 0x80u;
  v139 = v32;
  cValues = 0;
  RegQueryInfoKeyW(v10, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v33 = cValues + *((_DWORD *)v31 + 4);
  v142 = 0;
  v143 = 0;
  v34 = LocalAlloc(0x40u, 700LL * v33);
  v35 = v142;
  v143 = v34;
  if ( v34 )
    v35 = v33;
  LODWORD(v142) = v35;
  v36 = *((_DWORD *)v31 + 4) + 4;
  v146 = 0;
  hMem = 0;
  v37 = LocalAlloc(0x40u, 700LL * v36);
  v38 = v146;
  hMem = v37;
  v167 = 0;
  if ( v37 )
    v38 = v36;
  v168 = 0;
  LODWORD(v146) = v38;
  InitializeCriticalSection(&CriticalSection);
  v171 = 0;
  v170 = 0;
  InitializeCriticalSection(&v172);
  InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(
    (struct CInputList *)&v142,
    (struct CInputDllRegKey *)&v161,
    (struct CInputDllRegKey *)&v150,
    (struct CInputDllRegKey *)&v154,
    (struct CInputDllRegKey *)v140);
  InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
    (struct CInputList *)&v146,
    (struct CInputDllRegKey *)&v159,
    0,
    0,
    dwOptionsc);
  InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
    (struct CInputList *)&v146,
    (struct CInputDllRegKey *)&v148,
    1,
    1,
    dwOptionsd);
  InstallLayoutOrTipPrivateHelpers::ReadSortOrder(
    (struct CInputDllRegKey *)&v165,
    (struct CInputDllRegKey *)&v163,
    (struct CSortOrder *)&v167);
  v39 = cbData;
  v40 = v157;
  if ( cbData || v157 )
  {
    if ( (_DWORD)v142 )
    {
      v105 = (unsigned __int16 *)v143;
      v106 = 0;
      if ( v143 )
      {
        do
        {
          if ( v106 >= HIDWORD(v142) )
            break;
          if ( *((_BYTE *)v105 + 16) )
          {
            *((_BYTE *)v105 + 16) = 0;
            if ( IsLoaded )
            {
              v107 = ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, __int64))pfnBcp47BufferFromLcid)(
                       *v105,
                       v183,
                       85);
              if ( v107 >= 0 )
              {
                v110 = *v105;
                v190[0] = 0;
                dwOptionsb = *((_DWORD *)v105 + 1);
                StringCchPrintfW(v190, 0x57u, L"%04X:%08X", v110);
                ((void (__fastcall *)(unsigned __int16 *, __int64, unsigned __int16 *))pfnRemoveUserLanguageInputMethods)(
                  v183,
                  59,
                  v190);
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x4FF,
                  (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
                  (const char *)(unsigned int)v107,
                  dwOptionsb);
              }
            }
          }
          if ( ++v106 >= (unsigned int)v142 )
            break;
          v105 = (unsigned __int16 *)((char *)v143 + 700 * v106);
        }
        while ( v105 );
      }
    }
    if ( (_DWORD)v146 )
    {
      v108 = (unsigned __int16 *)hMem;
      v109 = 0;
      if ( hMem )
      {
        do
        {
          if ( v109 >= HIDWORD(v146) )
            break;
          if ( v108[10] && v108[49] && *((_BYTE *)v108 + 16) && (v40 && *((_BYTE *)v108 + 19) || v39) )
          {
            *((_BYTE *)v108 + 16) = 0;
            if ( IsLoaded )
            {
              v111 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64))pfnBcp47BufferFromLcid)(*v108, v191, 85);
              if ( v111 >= 0 )
              {
                dwOptionsb = (_DWORD)v108 + 20;
                StringCchPrintfW(SubKey, 0x57u, L"%04X:%s%s", *v108);
                ((void (__fastcall *)(_BYTE *, __int64, WCHAR *))pfnRemoveUserLanguageInputMethods)(v191, 59, SubKey);
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x518,
                  (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
                  (const char *)(unsigned int)v111,
                  dwOptionsb);
              }
            }
          }
          if ( ++v109 >= (unsigned int)v146 )
            break;
          v108 = (unsigned __int16 *)((char *)hMem + 700 * v109);
        }
        while ( v108 );
        v31 = phkResult;
      }
    }
    while ( (_QWORD)v167 )
      CList<SortOrderItem *>::Pop(&v167);
    while ( (_QWORD)v170 )
      CList<CLanguageAssemblyList *>::Pop(&v170);
  }
  v41 = 0;
  if ( *((int *)v31 + 4) > 0 )
  {
    v42 = v152;
    v43 = v139;
    v44 = *(_OWORD *)L"ts\\%08x";
    v45 = *(_OWORD *)L"d Layouts\\%08x";
    v46 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
    v47 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
    v48 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
    v49 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
    v50 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
    while ( 1 )
    {
      v51 = (int *)(*((_QWORD *)v31 + 1) + *((_DWORD *)v31 + 5) * v41);
      if ( v51 )
        break;
LABEL_140:
      if ( ++v41 >= *((_DWORD *)v31 + 4) )
        goto LABEL_141;
    }
    if ( *v51 == 1 )
    {
      if ( v43 || v42 )
        InstallLayoutOrTipPrivateHelpers::DisableKeyboard(
          *((_WORD *)v51 + 2),
          v51[2],
          (struct CInputList *)&v142,
          IsLoaded);
      else
        InstallLayoutOrTipPrivateHelpers::EnableKeyboard(
          *((_WORD *)v51 + 2),
          v51[2],
          0,
          (struct CInputList *)&v142,
          IsLoaded,
          (struct CInputDllRegKey *)v140,
          (struct CInputDllRegKey *)&v144);
    }
    else
    {
      if ( *v51 != 2 )
        goto LABEL_108;
      CLSIDToStringW((const struct _GUID *)(v51 + 3), v183);
      CLSIDToStringW((const struct _GUID *)(v51 + 7), v189);
      if ( v43 || v42 )
        InstallLayoutOrTipPrivateHelpers::DisableIme(
          *((_WORD *)v51 + 2),
          v183,
          v189,
          (struct CInputList *)&v146,
          (struct CInputList *)&v142,
          IsLoaded);
      else
        InstallLayoutOrTipPrivateHelpers::EnableIme(
          *((_WORD *)v51 + 2),
          v183,
          v189,
          (struct CInputList *)&v146,
          (struct CInputList *)&v142,
          IsLoaded,
          (struct CInputDllRegKey *)&v148,
          (struct CInputDllRegKey *)v140,
          (struct CInputDllRegKey *)&v144);
    }
    v50 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
    v49 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
    v48 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
    v47 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
    v46 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
    v45 = *(_OWORD *)L"d Layouts\\%08x";
    v44 = *(_OWORD *)L"ts\\%08x";
LABEL_108:
    memset_0(v177, 0, 0x2BCu);
    v52 = v51[2];
    v53 = *((unsigned __int16 *)v51 + 2);
    v179 = *v51;
    v188[0] = v45;
    v177[0] = v53;
    v136 = 0;
    *(_OWORD *)v183 = v50;
    v184 = v49;
    v185 = v48;
    v186 = v47;
    v187 = v46;
    *(_OWORD *)((char *)v188 + 14) = v44;
    if ( (v52 & 0xF0000000) != 0xE0000000 )
    {
      StringCchPrintfW(SubKey, 0x104u, v183, v52);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v136) )
      {
        cbData = 16;
        if ( RegQueryValueExW(v136, L"Layout Id", 0, 0, (LPBYTE)Data, &cbData) )
        {
          RegCloseKey(v136);
        }
        else
        {
          v115 = o_wcstoul_0(Data, 0, 16);
          RegCloseKey(v136);
          v52 = v115 + 61440;
        }
      }
      v44 = *(_OWORD *)L"ts\\%08x";
      v45 = *(_OWORD *)L"d Layouts\\%08x";
      v52 = v53 + (v52 << 16);
      v46 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
      v47 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
      v48 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
      v49 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
      v50 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
    }
    v178 = v52;
    v180[0] = 123;
    v54 = 1;
    for ( i = 0; i < 0x14; ++i )
    {
      if ( v54 >= 36 )
        break;
      v56 = *((unsigned __int8 *)qword_1800B0EC0 + (int)i);
      v57 = v54++;
      v58 = &v180[v57];
      if ( (_BYTE)v56 == 45 )
      {
        *v58 = 45;
      }
      else
      {
        v59 = *((_BYTE *)v51 + v56 + 12);
        v60 = v54++;
        *v58 = word_1800B0E90[(unsigned __int64)v59 >> 4];
        v180[v60] = word_1800B0E90[v59 & 0xF];
      }
    }
    v61 = v54;
    v62 = v54;
    v63 = 1;
    v180[v61] = 125;
    v180[v62 + 1] = 0;
    v64 = 0;
    v181[0] = 123;
    do
    {
      if ( v63 >= 36 )
        break;
      v65 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v64);
      v66 = v63++;
      v67 = &v181[v66];
      if ( (_BYTE)v65 == 45 )
      {
        *v67 = 45;
      }
      else
      {
        v68 = *((_BYTE *)v51 + v65 + 28);
        v69 = v63++;
        *v67 = word_1800B0E90[(unsigned __int64)v68 >> 4];
        v181[v69] = word_1800B0E90[v68 & 0xF];
      }
      v64 = (unsigned int)(v64 + 1);
    }
    while ( (unsigned int)v64 < 0x14 );
    v31 = phkResult;
    v181[v63] = 125;
    v181[v63 + 1] = 0;
    if ( v43 || v42 )
    {
      v70 = (_QWORD *)v170;
      v71 = v177[0];
      while ( v70 )
      {
        v72 = (_WORD *)v70[2];
        if ( *v72 == v177[0] )
        {
          v119 = v70[2];
          AssemblySortOrder = CSortOrder::FindAssemblySortOrder(v63, v177, v72 + 4, v64);
          if ( !AssemblySortOrder )
            goto LABEL_140;
          CList<SortOrderItem *>::Delete(v119 + 8, AssemblySortOrder);
          if ( !*(_DWORD *)(v119 + 24) )
          {
            CList<SortOrderItem *>::Delete(&v170, v70);
            for ( j = (__int64 **)v167; j; j = (__int64 **)*j )
            {
              if ( *(_WORD *)j[2] == v71 )
                goto LABEL_222;
            }
            j = 0;
LABEL_222:
            CList<SortOrderItem *>::Delete(&v167, j);
            v44 = *(_OWORD *)L"ts\\%08x";
            v45 = *(_OWORD *)L"d Layouts\\%08x";
            v46 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
            v47 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
            v48 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
            v49 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
            v50 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
            goto LABEL_140;
          }
          goto LABEL_139;
        }
        v70 = (_QWORD *)*v70;
      }
    }
    else
    {
      v92 = v177[0];
      for ( k = (__int64 **)v167; k; k = (__int64 **)*k )
      {
        if ( *(_WORD *)k[2] == v177[0] )
          goto LABEL_155;
      }
      v94 = operator new(0x2C0u);
      memset_0((char *)v94 + 2, 0, 0x2BAu);
      *(_WORD *)v94 = v92;
      v94[175] = v168 + 1;
      EnterCriticalSection(&CriticalSection);
      v95 = operator new(0x18u);
      *v95 = 0;
      v95[1] = 0;
      v95[2] = v94;
      if ( v167 == 0 )
      {
        *((_QWORD *)&v167 + 1) = v95;
      }
      else
      {
        *(_QWORD *)(v167 + 8) = v95;
        *v95 = v167;
        v95[1] = 0;
      }
      ++v168;
      *(_QWORD *)&v167 = v95;
      LeaveCriticalSection(&CriticalSection);
      v44 = *(_OWORD *)L"ts\\%08x";
      v45 = *(_OWORD *)L"d Layouts\\%08x";
      v46 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
      v47 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
      v48 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
      v49 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
      v50 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
LABEL_155:
      for ( m = (_QWORD *)v170; ; m = (_QWORD *)*m )
      {
        if ( !m )
          goto LABEL_130;
        v97 = (_WORD *)m[2];
        if ( *v97 == v92 )
          break;
      }
      v74 = v97 + 4;
      if ( v97 == (_WORD *)-8LL )
      {
LABEL_130:
        v73 = (char *)operator new(0x48u);
        *(_WORD *)v73 = v92;
        v74 = v73 + 8;
        *((_QWORD *)v73 + 1) = 0;
        *((_QWORD *)v73 + 2) = 0;
        *((_DWORD *)v73 + 6) = 0;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v73 + 32));
        EnterCriticalSection(&v172);
        v75 = operator new(0x18u);
        *v75 = 0;
        v75[1] = 0;
        v75[2] = v73;
        if ( v170 == 0 )
        {
          *((_QWORD *)&v170 + 1) = v75;
        }
        else
        {
          *(_QWORD *)(v170 + 8) = v75;
          *v75 = v170;
          v75[1] = 0;
        }
        ++v171;
        *(_QWORD *)&v170 = v75;
        LeaveCriticalSection(&v172);
        goto LABEL_133;
      }
      for ( n = *(_QWORD **)v74; n; n = (_QWORD *)*n )
      {
        v99 = n[2];
        if ( *(_WORD *)v99 == v92 )
        {
          v100 = *(_DWORD *)(v99 + 12);
          if ( v100 == v179 )
          {
            if ( v100 == 1 )
            {
              if ( *(_DWORD *)(v99 + 4) == v178 )
                goto LABEL_140;
            }
            else if ( v100 == 2 )
            {
              v101 = (unsigned __int16 *)(v99 + 20);
              do
              {
                v102 = *(unsigned __int16 *)((char *)&v180[-10] + (_QWORD)v101 - v99);
                v103 = *v101 - v102;
                if ( v103 )
                  break;
                ++v101;
              }
              while ( v102 );
              if ( !v103 )
              {
                v116 = (unsigned __int16 *)(v99 + 98);
                do
                {
                  v117 = *(unsigned __int16 *)((char *)&v181[-49] + (_QWORD)v116 - v99);
                  v118 = *v116 - v117;
                  if ( v118 )
                    break;
                  ++v116;
                }
                while ( v117 );
                if ( !v118 )
                  goto LABEL_140;
              }
            }
          }
        }
      }
LABEL_133:
      v76 = operator new(0x2C0u);
      memset_0(v76, 0, 0x2C0u);
      v77 = (__int128 *)v177;
      v78 = 5;
      v76[175] = *((_DWORD *)v74 + 4) + 1;
      v79 = (__int128 *)v76;
      do
      {
        v79 += 8;
        v80 = *v77;
        v81 = v77[1];
        v77 += 8;
        *(v79 - 8) = v80;
        v82 = *(v77 - 6);
        *(v79 - 7) = v81;
        v83 = *(v77 - 5);
        *(v79 - 6) = v82;
        v84 = *(v77 - 4);
        *(v79 - 5) = v83;
        v85 = *(v77 - 3);
        *(v79 - 4) = v84;
        v86 = *(v77 - 2);
        *(v79 - 3) = v85;
        v87 = *(v77 - 1);
        *(v79 - 2) = v86;
        *(v79 - 1) = v87;
        --v78;
      }
      while ( v78 );
      v88 = v77[1];
      *v79 = *v77;
      v89 = v77[2];
      v79[1] = v88;
      v90 = *(__int128 *)((char *)v77 + 44);
      v79[2] = v89;
      *(__int128 *)((char *)v79 + 44) = v90;
      EnterCriticalSection((LPCRITICAL_SECTION)(v74 + 12));
      v91 = operator new(0x18u);
      *v91 = 0;
      v91[1] = 0;
      v91[2] = v76;
      if ( *(_QWORD *)v74 || *((_QWORD *)v74 + 1) )
      {
        *(_QWORD *)(*(_QWORD *)v74 + 8LL) = v91;
        *v91 = *(_QWORD *)v74;
        v91[1] = 0;
      }
      else
      {
        *((_QWORD *)v74 + 1) = v91;
      }
      *(_QWORD *)v74 = v91;
      ++*((_DWORD *)v74 + 4);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v74 + 12));
LABEL_139:
      v50 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
      v49 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
      v48 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
      v47 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
      v46 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
      v45 = *(_OWORD *)L"d Layouts\\%08x";
      v44 = *(_OWORD *)L"ts\\%08x";
    }
    goto LABEL_140;
  }
LABEL_141:
  InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(
    (struct CInputList *)&v142,
    v158,
    (struct CInputDllRegKey *)&v161,
    (struct CInputDllRegKey *)&v150,
    (struct CInputDllRegKey *)&v154);
  InstallLayoutOrTipPrivateHelpers::WriteImeRegistry((struct CInputList *)&v146, (struct CInputDllRegKey *)&v159);
  InstallLayoutOrTipPrivateHelpers::WriteSortOrder(
    (struct CInputDllRegKey *)&v165,
    (struct CInputDllRegKey *)&v163,
    (struct CSortOrder *)&v167);
  phkResult = 0;
  if ( GetCurrentUserSid((void **)&phkResult) )
  {
    v104 = phkResult;
    if ( !IsWellKnownSid(phkResult, WinLocalSystemSid)
      && EnsureBcp47LangsLibraryIsLoaded()
      && EnsureKernel32LibraryIsLoaded() )
    {
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))pfnNotifyUiLanguageChange)(32, 0, 0, 0, 0);
    }
    LocalFree(v104);
  }
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v173, 0);
  (**(void (__fastcall ***)(HKEY, __int64))v31)(v31, 1);
  while ( (_QWORD)v167 )
    CList<SortOrderItem *>::Pop(&v167);
  while ( (_QWORD)v170 )
    CList<CLanguageAssemblyList *>::Pop(&v170);
  CList<CLanguageAssemblyList *>::~CList<CLanguageAssemblyList *>(&v170);
  CList<CLanguageAssemblyList *>::~CList<CLanguageAssemblyList *>(&v167);
  LocalFree(hMem);
  LocalFree(v143);
  if ( v164 )
    RegCloseKey(v164);
  if ( v166 )
    RegCloseKey(v166);
  v148 = &CInputDllRegKey::`vftable';
  if ( v149 )
  {
    RegCloseKey(v149);
    v149 = 0;
  }
  v154 = &CInputDllRegKey::`vftable';
  if ( v155 )
  {
    RegCloseKey(v155);
    v155 = 0;
  }
  if ( v160 )
    RegCloseKey(v160);
  v144 = &CInputDllRegKey::`vftable';
  if ( v145 )
  {
    RegCloseKey(v145);
    v145 = 0;
  }
  *(_QWORD *)v140 = &CInputDllRegKey::`vftable';
  if ( v141 )
  {
    RegCloseKey(v141);
    v141 = 0;
  }
  v150 = &CInputDllRegKey::`vftable';
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v162 )
    RegCloseKey(v162);
  v173 = &InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable';
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v173);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v176);
  wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v175);
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v174);
  return 1;
}

```

## disassembly

```asm
0x180005500  mov     [rsp-8+arg_18], rbx
0x180005505  push    rbp
0x180005506  push    rsi
0x180005507  push    rdi
0x180005508  push    r13
0x18000550a  push    r14
0x18000550c  lea     rbp, [rsp-9E0h]
0x180005514  sub     rsp, 0AE0h
0x18000551b  mov     rax, cs:__security_cookie
0x180005522  xor     rax, rsp
0x180005525  mov     [rbp+0A00h+var_A0], rax
0x18000552c  mov     esi, edx
0x18000552e  mov     [rbp+0A00h+var_A18], edx
0x180005531  mov     r13, rcx
0x180005534  lea     rdx, aInstalllayouto; "InstallLayoutOrTipPrivateWorker"
0x18000553b  lea     rcx, [rbp+0A00h+var_930]; struct wil::details::IFailureCallback *
0x180005542  call    ??0?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180005547  lea     r14, ??_7InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@6B@; const InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable'
0x18000554e  lea     rcx, [rbp+0A00h+var_930]; this
0x180005555  mov     [rbp+0A00h+var_930], r14
0x18000555c  call    ?StartActivity@InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@QEAAXXZ; InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::StartActivity(void)
0x180005561  mov     eax, esi
0x180005563  mov     ebx, esi
0x180005565  shr     eax, 5
0x180005568  mov     edi, esi
0x18000556a  not     al
0x18000556c  and     ebx, 40h
0x18000556f  and     al, 1
0x180005571  mov     [rbp+0A00h+cbData], ebx
0x180005574  and     edi, 100h
0x18000557a  mov     [rbp+0A00h+var_9F8], eax
0x18000557d  mov     [rbp+0A00h+var_9FC], edi
0x180005580  call    ?EnsureBcp47LangsLibraryIsLoaded@@YA_NXZ; EnsureBcp47LangsLibraryIsLoaded(void)
0x180005585  mov     [rsp+0B00h+var_AA0], al
0x180005589  test    ebx, ebx
0x18000558b  jnz     loc_180006AA7
0x180005591  xor     al, al
0x180005593  mov     rcx, [rbp+0A08h]; this
0x18000559a  test    al, al
0x18000559c  jz      loc_180005629
0x1800055a2  mov     r9d, 80004005h; char *
0x1800055a8  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x1800055af  mov     edx, 4BDh; void *
0x1800055b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800055b9  mov     edx, 80004005h
0x1800055be  lea     rcx, [rbp+0A00h+var_930]
0x1800055c5  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800055ca  lea     rcx, [rbp+0A00h+var_930]
0x1800055d1  mov     [rbp+0A00h+var_930], r14
0x1800055d8  call    ?Destroy@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800055dd  lea     rcx, [rbp+0A00h+var_810]; this
0x1800055e4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800055e9  lea     rcx, [rbp+0A00h+var_818]
0x1800055f0  call    ?reset@?$shared_object@V?$ActivityData@VInputTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800055f5  lea     rcx, [rbp+0A00h+var_928]
0x1800055fc  call    ??1?$ActivityData@VInputTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180005601  xor     eax, eax
0x180005603  mov     rcx, [rbp+0A00h+var_A0]
0x18000560a  xor     rcx, rsp; StackCookie
0x18000560d  call    __security_check_cookie
0x180005612  mov     rbx, [rsp+0B00h+arg_18]
0x18000561a  add     rsp, 0AE0h
0x180005621  pop     r14
0x180005623  pop     r13
0x180005625  pop     rdi
0x180005626  pop     rsi
0x180005627  pop     rbp
0x180005628  retn
0x180005629  xor     ebx, ebx
0x18000562b  mov     [rsp+0B00h+arg_8], r12
0x180005633  lea     rax, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x18000563a  mov     [rsp+0B00h+arg_10], r15
0x180005642  mov     r12d, esi
0x180005645  mov     [rbp+0A00h+var_9E0], rax
0x180005649  mov     [rbp+0A00h+var_A28], rax
0x18000564d  lea     rsi, ?c_szPreloadTest@@3QBGB; "TextInputDrt\\Keyboard Layout\\Preload"
0x180005654  mov     qword ptr [rbp+0A00h+var_A78], rax
0x180005658  lea     rdx, [rsp+0B00h+phkResult]; phkResult
0x18000565d  mov     [rbp+0A00h+var_A58], rax
0x180005661  and     r12d, 200h
0x180005668  mov     [rbp+0A00h+var_9F0], rax
0x18000566c  mov     ecx, 2001Fh; samDesired
0x180005671  mov     [rbp+0A00h+var_A10], rax
0x180005675  mov     edi, ebx
0x180005677  mov     [rbp+0A00h+var_A38], rax
0x18000567b  mov     r15d, ebx
0x18000567e  mov     [rbp+0A00h+var_9C0], rax
0x180005682  mov     [rbp+0A00h+var_9D0], rax
0x180005686  lea     rax, ?c_szPreload@@3QBGB; "Keyboard Layout\\Preload"
0x18000568d  cmovz   rsi, rax
0x180005691  mov     [rbp+0A00h+var_9D8], rbx
0x180005695  mov     [rbp+0A00h+hKey], rbx
0x180005699  mov     [rbp+0A00h+var_A70], rbx
0x18000569d  mov     [rbp+0A00h+var_A50], rbx
0x1800056a1  mov     [rbp+0A00h+var_9E8], rbx
0x1800056a5  mov     [rbp+0A00h+var_A08], rbx
0x1800056a9  mov     [rbp+0A00h+var_A30], rbx
0x1800056ad  mov     [rbp+0A00h+var_9B8], rbx
0x1800056b1  mov     [rbp+0A00h+var_9C8], rbx
0x1800056b5  mov     [rsp+0B00h+dwDisposition], ebx
0x1800056b9  mov     [rsp+0B00h+var_A98], rbx
0x1800056be  mov     [rsp+0B00h+phkResult], rbx
0x1800056c3  call    cs:__imp_RegOpenCurrentUser
0x1800056c9  mov     r14, 0FFFFFFFF80000001h
0x1800056d0  mov     rdx, rsi; lpSubKey
0x1800056d3  test    eax, eax
0x1800056d5  lea     rax, [rsp+0B00h+dwDisposition]
0x1800056da  mov     [rsp+0B00h+lpdwDisposition], rax; lpdwDisposition
0x1800056df  lea     rax, [rsp+0B00h+var_A98]
0x1800056e4  cmovz   r14, [rsp+0B00h+phkResult]
0x1800056ea  xor     r9d, r9d; lpClass
0x1800056ed  mov     [rsp+0B00h+var_AC8], rax; phkResult
0x1800056f2  xor     r8d, r8d; Reserved
0x1800056f5  mov     [rsp+0B00h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800056fa  mov     rcx, r14; hKey
0x1800056fd  mov     [rsp+0B00h+samDesired], 2001Fh; samDesired
0x180005705  mov     [rsp+0B00h+dwOptions], ebx; int
0x180005709  call    cs:__imp_RegCreateKeyExW
0x18000570f  mov     ebx, eax
0x180005711  test    eax, eax
0x180005713  jnz     loc_180006AB6
0x180005719  mov     rdi, [rsp+0B00h+var_A98]
0x18000571e  xor     esi, esi
0x180005720  mov     ebx, esi
0x180005722  mov     [rbp+0A00h+var_9D8], rdi
0x180005726  mov     rcx, [rsp+0B00h+phkResult]; hKey
0x18000572b  test    rcx, rcx
0x18000572e  jz      short loc_180005736
0x180005730  call    cs:__imp_RegCloseKey
0x180005736  test    ebx, ebx
0x180005738  jnz     loc_180005C77
0x18000573e  lea     rax, ?c_szSubstitutes@@3QBGB; "Keyboard Layout\\Substitutes"
0x180005745  test    r12d, r12d
0x180005748  lea     rsi, ?c_szSubstitutesTest@@3QBGB; "TextInputDrt\\Keyboard Layout\\Substitu"...
0x18000574f  mov     ecx, 2001Fh; samDesired
0x180005754  cmovz   rsi, rax
0x180005758  lea     rdx, [rsp+0B00h+phkResult]; phkResult
0x18000575d  xor     ebx, ebx
0x18000575f  mov     [rsp+0B00h+dwDisposition], ebx
0x180005763  mov     [rsp+0B00h+var_A98], rbx
0x180005768  mov     [rsp+0B00h+phkResult], rbx
0x18000576d  call    cs:__imp_RegOpenCurrentUser
0x180005773  mov     r14, 0FFFFFFFF80000001h
0x18000577a  mov     rdx, rsi; lpSubKey
0x18000577d  test    eax, eax
0x18000577f  lea     rax, [rsp+0B00h+dwDisposition]
0x180005784  mov     [rsp+0B00h+lpdwDisposition], rax; lpdwDisposition
0x180005789  lea     rax, [rsp+0B00h+var_A98]
0x18000578e  cmovz   r14, [rsp+0B00h+phkResult]
0x180005794  xor     r9d, r9d; lpClass
0x180005797  mov     [rsp+0B00h+var_AC8], rax; phkResult
0x18000579c  xor     r8d, r8d; Reserved
0x18000579f  mov     [rsp+0B00h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800057a4  mov     rcx, r14; hKey
0x1800057a7  mov     [rsp+0B00h+samDesired], 2001Fh; samDesired
0x1800057af  mov     [rsp+0B00h+dwOptions], ebx; dwOptions
0x1800057b3  call    cs:__imp_RegCreateKeyExW
0x1800057b9  mov     ebx, eax
0x1800057bb  test    eax, eax
0x1800057bd  jnz     loc_180006B17
0x1800057c3  mov     rcx, [rbp+0A00h+hKey]; hKey
0x1800057c7  xor     esi, esi
0x1800057c9  mov     ebx, esi
0x1800057cb  test    rcx, rcx
0x1800057ce  jz      short loc_1800057D8
0x1800057d0  call    cs:__imp_RegCloseKey
0x1800057d6  mov     ebx, eax
0x1800057d8  mov     rax, [rsp+0B00h+var_A98]
0x1800057dd  mov     [rbp+0A00h+hKey], rax
0x1800057e1  mov     rcx, [rsp+0B00h+phkResult]; hKey
0x1800057e6  test    rcx, rcx
0x1800057e9  jz      short loc_1800057F1
0x1800057eb  call    cs:__imp_RegCloseKey
0x1800057f1  test    ebx, ebx
0x1800057f3  jnz     loc_180005C77
0x1800057f9  lea     rax, [rsp+0B00h+var_A98]
0x1800057fe  mov     [rsp+0B00h+var_A98], rsi
0x180005803  mov     r9d, 20019h; samDesired
0x180005809  mov     qword ptr [rsp+0B00h+dwOptions], rax; phkResult
0x18000580e  xor     r8d, r8d; ulOptions
0x180005811  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Key"...
0x180005818  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000581f  call    cs:__imp_RegOpenKeyExW
0x180005825  test    eax, eax
0x180005827  jnz     loc_180005C9A
0x18000582d  mov     rax, [rbp+0A00h+var_A70]
0x180005831  mov     ecx, esi
0x180005833  test    rax, rax
0x180005836  jz      short loc_180005843
0x180005838  mov     rcx, rax; hKey
0x18000583b  call    cs:__imp_RegCloseKey
0x180005841  mov     ecx, eax
0x180005843  mov     rax, [rsp+0B00h+var_A98]
0x180005848  mov     [rbp+0A00h+var_A70], rax
0x18000584c  test    ecx, ecx
0x18000584e  jnz     loc_180006B78
0x180005854  lea     rax, [rsp+0B00h+var_A98]
0x180005859  mov     [rsp+0B00h+var_A98], rsi
0x18000585e  mov     r9d, 20019h; samDesired
0x180005864  mov     qword ptr [rsp+0B00h+dwOptions], rax; phkResult
0x180005869  xor     r8d, r8d; ulOptions
0x18000586c  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Nls"...
0x180005873  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000587a  call    cs:__imp_RegOpenKeyExW
0x180005880  test    eax, eax
0x180005882  jnz     loc_180005CF9
0x180005888  mov     rax, [rbp+0A00h+var_A50]
0x18000588c  mov     ecx, esi
0x18000588e  test    rax, rax
0x180005891  jz      short loc_18000589E
0x180005893  mov     rcx, rax; hKey
0x180005896  call    cs:__imp_RegCloseKey
0x18000589c  mov     ecx, eax
0x18000589e  mov     rax, [rsp+0B00h+var_A98]
0x1800058a3  mov     [rbp+0A00h+var_A50], rax
0x1800058a7  test    ecx, ecx
0x1800058a9  jnz     loc_180006BA2
0x1800058af  lea     rdx, [rsp+0B00h+phkResult]; phkResult
0x1800058b4  mov     [rsp+0B00h+dwDisposition], esi
0x1800058b8  mov     ecx, 2001Fh; samDesired
0x1800058bd  mov     [rsp+0B00h+var_A98], rsi
0x1800058c2  mov     [rsp+0B00h+phkResult], rsi
0x1800058c7  call    cs:__imp_RegOpenCurrentUser
0x1800058cd  mov     rsi, 0FFFFFFFF80000001h
0x1800058d4  lea     rdx, ?c_szCtfTip@@3QBGB; "Software\\Microsoft\\CTF\\TIP"
0x1800058db  test    eax, eax
0x1800058dd  lea     rax, [rsp+0B00h+dwDisposition]
0x1800058e2  mov     [rsp+0B00h+lpdwDisposition], rax; lpdwDisposition
0x1800058e7  lea     rax, [rsp+0B00h+var_A98]
0x1800058ec  cmovz   rsi, [rsp+0B00h+phkResult]
0x1800058f2  xor     r14d, r14d
0x1800058f5  mov     [rsp+0B00h+var_AC8], rax; unsigned int *
0x1800058fa  xor     r9d, r9d; lpClass
0x1800058fd  mov     [rsp+0B00h+lpSecurityAttributes], r14; struct _SECURITY_ATTRIBUTES *
0x180005902  xor     r8d, r8d; Reserved
0x180005905  mov     [rsp+0B00h+samDesired], 2001Fh; unsigned int
0x18000590d  mov     rcx, rsi; hKey
0x180005910  mov     [rsp+0B00h+dwOptions], r14d; unsigned int
0x180005915  call    cs:__imp_RegCreateKeyExW
0x18000591b  mov     ebx, eax
0x18000591d  test    eax, eax
0x18000591f  jnz     loc_180006BCC
0x180005925  mov     r15, [rsp+0B00h+var_A98]
0x18000592a  xor     esi, esi
0x18000592c  mov     ebx, esi
0x18000592e  mov     [rbp+0A00h+var_9E8], r15
0x180005932  mov     rcx, [rsp+0B00h+phkResult]; hKey
0x180005937  test    rcx, rcx
0x18000593a  jz      short loc_180005942
0x18000593c  call    cs:__imp_RegCloseKey
0x180005942  test    ebx, ebx
0x180005944  jnz     loc_180005C77
0x18000594a  lea     r8, ?c_szHiddenDummyLayoutsKey@@3QBGB; "Software\\Microsoft\\CTF\\HiddenDummyLa"...
0x180005951  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180005958  lea     rcx, [rbp+0A00h+var_A10]; this
0x18000595c  call    ?Create@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CInputDllRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180005961  test    eax, eax
0x180005963  jnz     loc_180005C77
0x180005969  lea     rax, [rsp+0B00h+var_A98]
0x18000596e  mov     [rsp+0B00h+var_A98], rsi
0x180005973  mov     r9d, 20019h; samDesired
0x180005979  mov     qword ptr [rsp+0B00h+dwOptions], rax; int
0x18000597e  xor     r8d, r8d; ulOptions
0x180005981  lea     rdx, ?c_szCtfTip@@3QBGB; "Software\\Microsoft\\CTF\\TIP"
0x180005988  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000598f  call    cs:__imp_RegOpenKeyExW
0x180005995  test    eax, eax
0x180005997  jnz     loc_1800069E9
0x18000599d  mov     rcx, [rbp+0A00h+var_A30]; hKey
0x1800059a1  mov     edx, esi
0x1800059a3  test    rcx, rcx
0x1800059a6  jz      short loc_1800059B0
0x1800059a8  call    cs:__imp_RegCloseKey
0x1800059ae  mov     edx, eax
0x1800059b0  mov     rax, [rsp+0B00h+var_A98]
0x1800059b5  mov     [rbp+0A00h+var_A30], rax
0x1800059b9  test    edx, edx
0x1800059bb  jnz     loc_180006C31
0x1800059c1  lea     r8, ?c_szSortOrderLanguage@@3QBGB; "Software\\Microsoft\\CTF\\SortOrder\\La"...
0x1800059c8  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1800059cf  lea     rcx, [rbp+0A00h+var_9C0]; this
0x1800059d3  call    ?Create@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CInputDllRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800059d8  test    eax, eax
0x1800059da  jnz     loc_180005C77
0x1800059e0  lea     r8, ?c_szSortOrderAssemblyItem@@3QBGB; "Software\\Microsoft\\CTF\\SortOrder\\As"...
0x1800059e7  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1800059ee  lea     rcx, [rbp+0A00h+var_9D0]; this
0x1800059f2  call    ?Create@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CInputDllRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800059f7  test    eax, eax
0x1800059f9  jnz     loc_180005C77
0x1800059ff  mov     rcx, r13
0x180005a02  call    ?ParseItemString@@YAPEAV?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@PEBG@Z; ParseItemString(ushort const *)
0x180005a07  mov     rcx, [rbp+0A08h]; this
0x180005a0e  mov     r13, rax
0x180005a11  mov     [rsp+0B00h+phkResult], rax
0x180005a16  test    rax, rax
0x180005a19  jnz     loc_180005D58
0x180005a1f  mov     r9d, 80004005h; char *
0x180005a25  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x180005a2c  mov     edx, 4D4h; void *
  ... truncated ...
```
