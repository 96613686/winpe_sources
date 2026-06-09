# InstallBegin

- ea: `0x180003370`
- end: `0x180004774`
- name: `InstallBegin`
- size: `5124`
- prototype: `__int64 __fastcall(__int64, HKEY, CManagedAppProcessor **, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180002024`
- `0x180002310`
- `0x180002788`
- `0x180002aa0`
- `0x180002b14`
- `0x180003370`
- `0x180004e30`
- `0x180004fc0`
- `0x180005a48`
- `0x180005cec`
- `0x180005e6c`
- `0x180006c54`
- `0x180007ea4`
- `0x1800084d4`
- `0x180008724`
- `0x180008d6c`
- `0x18000a2cc`
- `0x18000d1f4`
- `0x18000df00`
- `0x18000e4f0`
- `0x18000e69c`
- `0x18000e744`
- `0x18000e834`
- `0x180010ae8`
- `0x180011e44`
- `0x1800126ec`
- `0x180012bc4`
- `0x180012edc`
- `0x180012fbc`
- `0x180013530`
- `0x18001af7c`
- `0x18001b1a0`
- `0x18001b780`
- `0x18001bbe0`
- `0x18001c0e0`
- `0x18002ad9c`
- `0x18002ada8`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180003499`
- `RPCRT4!RpcImpersonateClient` at `0x1800036c0`
- `RPCRT4!RpcImpersonateClient` at `0x180003499`
- `RPCRT4!RpcImpersonateClient` at `0x1800036c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800034a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800034a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800034bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800034bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000405d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000405d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003fc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000421a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004297`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800044a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000458a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003fc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000421a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004297`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800044a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000458a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004001`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004001`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004256`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000430d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800044d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800045c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004256`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000430d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800044d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800045c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000433c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004715`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000433c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004715`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800034e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800034e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004706`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800034f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800036ae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800036e1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003e80`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004180`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800034f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800036ae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800036e1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003e80`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004180`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180003a1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004031`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180003a1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004031`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004632`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004632`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000380c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003833`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003907`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003995`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003cd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003eee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800040d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000380c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003833`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003907`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003995`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003cd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003eee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800040d9`
- `USERENV!FreeGPOListW` at `0x180004724`
- `USERENV!FreeGPOListW` at `0x180004724`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800038af`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800046bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800038af`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800046bf`
- `ADVAPI32!RegDeleteKeyW` at `0x18000409a`
- `ADVAPI32!RegDeleteKeyW` at `0x18000409a`
- `KERNEL32!lstrcmpiW` at `0x18000371a`
- `KERNEL32!lstrcmpiW` at `0x180003add`
- `KERNEL32!lstrcmpiW` at `0x18000371a`
- `KERNEL32!lstrcmpiW` at `0x180003add`
- `ntdll!RtlLeaveCriticalSection` at `0x180003a64`
- `ntdll!RtlLeaveCriticalSection` at `0x180003a64`
- `ntdll!RtlEnterCriticalSection` at `0x1800038fa`
- `ntdll!RtlEnterCriticalSection` at `0x1800038fa`

## string_xrefs

- `0x180003fe2`: `TempClasses`
- `0x180004093`: `TempClasses`
- `0x1800042c1`: `shell\open\command`
- `0x1800042f4`: `command`
- `0x18000436c`: `CLSID\`

## pseudocode

```c
__int64 __fastcall InstallBegin(__int64 a1, HKEY a2, CManagedAppProcessor **a3, __int64 a4, _OWORD *a5)
{
  _OWORD *v5; // r12
  CManagedAppProcessor *v6; // r14
  CManagedAppProcessor **v7; // rbx
  HKEY v8; // rsi
  unsigned int LastError; // edi
  HANDLE CurrentThread; // rax
  CAppInfo *v12; // r13
  int v13; // r8d
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  bool v18; // zf
  DWORD v19; // r8d
  int v20; // ecx
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  PGROUP_POLICY_OBJECTW v24; // rbx
  struct _GROUP_POLICY_OBJECTW *pNext; // rsi
  const unsigned __int16 *lpDisplayName; // rbx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  CManagedAppProcessor *v29; // rax
  CManagedAppProcessor **v30; // r15
  CLoadMsi *v31; // rax
  CLoadMsi *v32; // rax
  HMODULE *v33; // rbx
  CManagedAppProcessor *v34; // rax
  CAppInfo *v35; // rax
  int v36; // r12d
  DWORD v37; // eax
  __int64 *v38; // rcx
  __int64 *v39; // rbx
  unsigned int v40; // r9d
  unsigned int v41; // edx
  wchar_t *v42; // rsi
  CAppInfo *v43; // rax
  CAppInfo *v44; // rax
  CAppInfo *v45; // rsi
  CAppInfo *v46; // rbx
  __int64 v47; // rax
  unsigned int *v48; // rcx
  void *v49; // rsi
  HLOCAL v50; // rax
  unsigned int *v51; // rcx
  int v52; // r15d
  HKEY v53; // r12
  _DWORD *v54; // rbx
  DWORD v55; // eax
  __int64 v56; // rbx
  __int64 v57; // rdx
  unsigned __int16 *v58; // rax
  int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // r15d
  __int64 v62; // rbx
  BYTE *v63; // rbx
  __int64 v64; // r14
  const wchar_t *v65; // rdx
  __int64 v66; // rcx
  BYTE *v67; // rax
  BYTE *v68; // rcx
  __int64 v69; // rcx
  unsigned __int16 *v70; // r8
  __int64 v71; // rdx
  char *v72; // rax
  char *v73; // rcx
  __int64 v74; // rbx
  __int64 v75; // rcx
  const wchar_t *v76; // r8
  __int64 v77; // rdx
  _WORD *v78; // rax
  _WORD *v79; // rcx
  const wchar_t *v80; // rcx
  _WORD *v81; // rax
  _WORD *v82; // rcx
  LSTATUS v83; // eax
  __int64 v84; // rax
  struct __MIDL_appmgmt_0004 *v85; // rbx
  struct __MIDL_appmgmt_0004 *v86; // rcx
  CManagedAppProcessor *v87; // rbx
  HMODULE *v88; // rbx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v91; // [rsp+58h] [rbp-A8h] BYREF
  CManagedAppProcessor *v92; // [rsp+60h] [rbp-A0h]
  HKEY v93; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v94; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  PGROUP_POLICY_OBJECTW pGPOList; // [rsp+98h] [rbp-68h] BYREF
  struct __MIDL_appmgmt_0004 *v99; // [rsp+A0h] [rbp-60h]
  CManagedAppProcessor *v100; // [rsp+A8h] [rbp-58h]
  CManagedAppProcessor *v101; // [rsp+B0h] [rbp-50h]
  CManagedAppProcessor **v102; // [rsp+B8h] [rbp-48h]
  _QWORD v103[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v104; // [rsp+D0h] [rbp-30h]
  __int128 v105; // [rsp+E0h] [rbp-20h]
  __int64 v106; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v107; // [rsp+F8h] [rbp-8h]
  __int128 v108; // [rsp+100h] [rbp+0h]
  __int128 v109; // [rsp+110h] [rbp+10h]
  int v110; // [rsp+120h] [rbp+20h]
  int v111; // [rsp+124h] [rbp+24h]
  _BYTE v112[144]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v113; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _GUID v114; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v115; // [rsp+1E0h] [rbp+E0h]
  unsigned __int16 *v116; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v117; // [rsp+1FCh] [rbp+FCh]
  unsigned __int16 *v118; // [rsp+200h] [rbp+100h]
  struct _GUID v119; // [rsp+21Ch] [rbp+11Ch] BYREF
  _QWORD Buf2[5]; // [rsp+22Ch] [rbp+12Ch] BYREF
  struct _GUID v121; // [rsp+254h] [rbp+154h] BYREF
  unsigned int v122; // [rsp+264h] [rbp+164h]
  __int64 v123; // [rsp+268h] [rbp+168h]
  struct _GUID Buf1; // [rsp+2C0h] [rbp+1C0h] BYREF
  tagCSPLATFORM v125; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v126; // [rsp+2E0h] [rbp+1E0h]
  WCHAR Data[6]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v128; // [rsp+2FCh] [rbp+1FCh] BYREF
  _BYTE v129[168]; // [rsp+348h] [rbp+248h] BYREF
  unsigned __int16 v130[40]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 v131[128]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR String2[40]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR v133[40]; // [rsp+590h] [rbp+490h] BYREF

  v5 = a5;
  v107 = &v106;
  v6 = 0;
  hKey = a2;
  v7 = a3;
  v99 = (struct __MIDL_appmgmt_0004 *)a4;
  v102 = a3;
  v106 = (__int64)&v106;
  v94 = (unsigned int *)a5;
  v103[0] = &CAppList::`vftable';
  v8 = a2;
  v108 = 0;
  v115 = 0;
  v103[1] = 0;
  v104 = 0;
  v105 = 0;
  v109 = 0;
  v110 = -2147467259;
  v111 = 0;
  v113 = 0;
  v114 = 0;
  v125 = 0;
  v126 = 0;
  memset_0(&v116, 0, 0xD0u);
  cbData = 0;
  Buf1 = 0;
  CRsopAppContext::CRsopAppContext((CRsopAppContext *)v112, 3u, 0, (struct _APPKEY *)v8);
  *v7 = 0;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  TokenHandle = 0;
  *(_OWORD *)(a4 + 32) = 0;
  *(_QWORD *)(a4 + 48) = 0;
  *a5 = 0;
  phkResult = 0;
  pGPOList = 0;
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_282;
  CurrentThread = GetCurrentThread();
  LODWORD(v91) = OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle);
  if ( !(_DWORD)v91 && (LastError = GetLastError()) != 0
    || (LastError = RegOpenCurrentUser(0x10000000u, &phkResult)) != 0 )
  {
    CloseHandle(TokenHandle);
    RevertToSelf();
    goto LABEL_282;
  }
  v100 = 0;
  v12 = 0;
  LogTime();
  v13 = *((_DWORD *)v8 + 1);
  DWORD1(v126) = 2048;
  GetDefaultPlatform((struct tagCSPLATFORM *)&v125.dwVersionHi, 1, v13);
  v14 = *(_DWORD *)v8;
  *((_QWORD *)&v126 + 1) = -1;
  v125.dwPlatformId = 23;
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 == 1 )
        {
          v18 = *((_DWORD *)v8 + 1) == 9;
          v19 = *((_DWORD *)v8 + 6);
          *((_QWORD *)&v113 + 1) = *((_QWORD *)v8 + 1);
          *(_QWORD *)&v114.Data1 = *((_QWORD *)v8 + 2);
          LODWORD(v113) = 0;
          if ( (v18 || *((_DWORD *)v8 + 1) == 6) && (v19 & 3) != 0 )
          {
            v20 = ((v19 & 1) << 28) | 0x20000000;
            if ( (v19 & 2) == 0 )
              v20 = (v19 & 1) << 28;
            v19 = v19 & 0xFFFFFFFC | v20;
          }
          v125.dwPlatformId = v19;
          GuidToString((struct _GUID *)(v8 + 2), v130);
          if ( *(_DWORD *)&gDebugLevel )
            _DebugMsg(4u, 0xBEDu, v130, v125.dwPlatformId);
        }
      }
      else
      {
        v21 = *((_QWORD *)v8 + 1);
        LODWORD(v113) = 4;
        *((_QWORD *)&v113 + 1) = v21;
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4u, 0xBECu);
      }
    }
    else
    {
      v22 = *((_QWORD *)v8 + 1);
      LODWORD(v113) = 1;
      *((_QWORD *)&v113 + 1) = v22;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xBEBu);
    }
  }
  else
  {
    v23 = *((_QWORD *)v8 + 1);
    v114 = (struct _GUID)*((_OWORD *)v8 + 1);
    LODWORD(v113) = 5;
    *((_QWORD *)&v113 + 1) = v23;
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xBEAu);
  }
  LastError = CsGetAppInfo(&v113, &v125, &v116);
  RevertToSelf();
  if ( LastError )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xBEEu, LastError);
    memset_0(&v116, 0, 0xD0u);
    LODWORD(v93) = LastError;
  }
  else
  {
    LastError = RpcImpersonateClient(0);
    if ( LastError )
      goto LABEL_84;
    LastError = GetCurrentUserGPOList(&pGPOList);
    LODWORD(v93) = LastError;
    RevertToSelf();
    if ( LastError )
      goto LABEL_259;
    v24 = pGPOList;
    GuidToString(&v121, String2);
    while ( v24 )
    {
      pNext = v24->pNext;
      if ( !lstrcmpiW(v24->szGPOName, String2) )
      {
        lpDisplayName = v24->lpDisplayName;
        if ( lpDisplayName )
          goto LABEL_34;
        break;
      }
      v24 = pNext;
    }
    lpDisplayName = &word_18002F430;
LABEL_34:
    if ( v117 != 5 )
    {
      if ( v117 == 6 )
      {
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4u, 0xC01u, v116, lpDisplayName);
        *(_QWORD *)(a4 + 8) = StringDuplicate(v116);
        v27 = StringDuplicate(lpDisplayName);
        v28 = v118;
        *(_QWORD *)(a4 + 16) = v27;
        *(_QWORD *)(a4 + 40) = StringDuplicate(v28);
        goto LABEL_83;
      }
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xC02u, v117, v116, lpDisplayName);
      LastError = -2147221148;
      goto LABEL_259;
    }
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xC00u, v116, lpDisplayName);
    v8 = hKey;
  }
  if ( LastError )
    goto LABEL_259;
  v29 = (CManagedAppProcessor *)LocalAlloc(0, 0x38u);
  v92 = v29;
  v30 = (CManagedAppProcessor **)v29;
  if ( v29 )
  {
    *(_QWORD *)v29 = 0;
    *((_QWORD *)v29 + 1) = 0;
    *((_DWORD *)v29 + 4) = 0;
    v31 = (CLoadMsi *)LocalAlloc(0, 8u);
    if ( v31 )
    {
      v32 = CLoadMsi::CLoadMsi(v31, (unsigned int *)&v93);
      LastError = (unsigned int)v93;
      v33 = (HMODULE *)v32;
    }
    else
    {
      v33 = 0;
    }
    v30[3] = (CManagedAppProcessor *)v33;
    v30[4] = 0;
    *((_BYTE *)v30 + 40) = 0;
    v30[6] = 0;
    if ( LastError )
    {
      if ( v33 )
      {
        if ( *v33 )
          FreeLibrary(*v33);
        operator delete(v33, 8u);
      }
      v30[3] = 0;
    }
    else if ( v33 )
    {
      goto LABEL_62;
    }
    operator delete(v30, 0x38u);
    v30 = 0;
  }
  LastError = 14;
  v92 = (CManagedAppProcessor *)v30;
  LODWORD(v93) = 14;
LABEL_62:
  if ( LastError )
  {
    v6 = v92;
    goto LABEL_259;
  }
  RtlEnterCriticalSection(&gAppCS);
  v34 = (CManagedAppProcessor *)LocalAlloc(0, 0x1F0u);
  if ( !v34 )
  {
    v101 = 0;
    v100 = 0;
    goto LABEL_67;
  }
  v100 = CManagedAppProcessor::CManagedAppProcessor(
           v34,
           0,
           TokenHandle,
           phkResult,
           0,
           1,
           0,
           (struct CRsopAppContext *)v112,
           (unsigned int *)&v93);
  v101 = v100;
  v6 = v100;
  if ( !v100 )
  {
LABEL_67:
    LastError = 14;
    goto LABEL_68;
  }
  LastError = (unsigned int)v93;
LABEL_68:
  if ( LastError )
    goto LABEL_81;
  LastError = CManagedAppProcessor::SetPolicyListFromGPOList(v6, pGPOList);
  if ( LastError )
    goto LABEL_81;
  v35 = (CAppInfo *)LocalAlloc(0, 0x1C8u);
  if ( !v35 || (v12 = CAppInfo::CAppInfo(v35, v6, (struct tagPACKAGEDISPINFO *)&v116, LastError + 1, (int *)&v91)) == 0 )
  {
LABEL_255:
    LastError = 14;
LABEL_81:
    v6 = v92;
    goto LABEL_82;
  }
  v36 = (int)v91;
  if ( !(_DWORD)v91 )
  {
    v5 = v94;
    goto LABEL_255;
  }
  GuidToString(&v119, v133);
  LastError = CManagedAppProcessor::GetOrderedLocalAppList(v6, (struct CAppList *)v103);
  if ( LastError )
  {
LABEL_80:
    v5 = v94;
    goto LABEL_81;
  }
  if ( *((_DWORD *)v6 + 99) == 1 || !*((_DWORD *)v6 + 74) || ImpersonateLoggedOnUser(*((HANDLE *)v6 + 33)) )
  {
    LastError = 0;
  }
  else
  {
    if ( *(_DWORD *)&gDebugLevel )
    {
      v37 = GetLastError();
      _DebugMsg(LastError + 2, 0xBC4u, v37);
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_80;
  }
  *v30 = v6;
  v30[1] = v12;
  v38 = v107;
  v39 = v107;
  *((_QWORD *)&v108 + 1) = v108;
  if ( v107 == &v106 )
    v39 = 0;
  *(_QWORD *)&v108 = v107;
  if ( !v39 )
  {
LABEL_134:
    *(_QWORD *)&v108 = *((_QWORD *)&v108 + 1);
    if ( !LastError )
    {
      if ( *(_DWORD *)hKey != 1 && (*((_BYTE *)v12 + 224) & 0x80) == 0 )
        *((_DWORD *)v12 + 53) &= ~0x2000u;
      CAppInfo::InitializePass0(v12);
      CAppInfo::SetActionPass1(v12);
      CAppInfo::SetActionPass2(v12);
      CAppInfo::SetActionPass3(v12);
      CAppInfo::SetActionPass4(v12);
      LastError = *((_DWORD *)v12 + 58);
    }
    goto LABEL_139;
  }
  while ( 1 )
  {
    if ( (v39[28] & 3) == 0 )
    {
      *(_QWORD *)&v108 = v38[1];
      goto LABEL_126;
    }
    if ( lstrcmpiW((LPCWSTR)v39[10], v133) || v39[3] == Buf2[0] && v39[4] == Buf2[1] )
      break;
    if ( *(_DWORD *)v8 != 1 )
    {
      LastError = -2147221148;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0xC16u, *((_QWORD *)v12 + 5));
      goto LABEL_134;
    }
    *(_QWORD *)&v108 = *(_QWORD *)(v108 + 8);
    *(_QWORD *)(*v39 + 8) = v39[1];
    *(_QWORD *)v39[1] = *v39;
    v39[1] = (__int64)v6 + 80;
    *v39 = *((_QWORD *)v6 + 10);
    *(_QWORD *)(*((_QWORD *)v6 + 10) + 8LL) = v39;
    *((_QWORD *)v6 + 10) = v39;
LABEL_126:
    v39 = (__int64 *)v108;
    if ( (__int64 *)v108 == &v106 || !(_QWORD)v108 )
      goto LABEL_134;
    v8 = hKey;
    v38 = (__int64 *)v108;
  }
  v40 = v122;
  v41 = 0;
  if ( !v122 )
  {
LABEL_105:
    if ( v41 >= v40 )
    {
      v42 = (wchar_t *)v39[17];
      if ( v42 )
      {
        while ( *v42 )
        {
          StringToGuid(v42, &Buf1);
          if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
          {
            if ( *(_DWORD *)hKey != 1 )
              goto LABEL_132;
            if ( CGPOInfoList::Compare(v6, (const unsigned __int16 *)v39[6], *((const unsigned __int16 **)v12 + 6)) < 0 )
            {
              memset_0(Data, 0, 0xD0u);
              LODWORD(v113) = 6;
              *((_QWORD *)&v113 + 1) = v39[3];
              *(_QWORD *)&v114.Data1 = v39[4];
              StringToGuid((wchar_t *)v39[6], (struct _GUID *)v114.Data4);
              if ( (unsigned int)CsGetAppInfo(&v113, 0, Data) )
                goto LABEL_123;
              v43 = (CAppInfo *)LocalAlloc(0, 0x1C8u);
              if ( v43 )
              {
                v44 = CAppInfo::CAppInfo(v43, v6, (struct tagPACKAGEDISPINFO *)Data, 0, (int *)&v91);
                v36 = (int)v91;
                v45 = v44;
              }
              else
              {
                v45 = 0;
              }
              if ( !v36 )
              {
                if ( v45 )
                {
                  CAppInfo::~CAppInfo(v45);
                  operator delete(v45, 0x1C8u);
                }
                v45 = 0;
              }
              ReleasePackageInfo(Data);
              if ( !v45 )
                goto LABEL_123;
              *((_QWORD *)v12 + 1) = (char *)v6 + 80;
              *(_QWORD *)v12 = *((_QWORD *)v6 + 10);
              *(_QWORD *)(*((_QWORD *)v6 + 10) + 8LL) = v12;
              *((_QWORD *)v6 + 10) = v12;
              LastError = CAppInfo::InitializePass0(v45);
              *(_QWORD *)(*(_QWORD *)v12 + 8LL) = *((_QWORD *)v12 + 1);
              **((_QWORD **)v12 + 1) = *(_QWORD *)v12;
              *((_QWORD *)v45 + 1) = (char *)v6 + 80;
              *(_QWORD *)v45 = *((_QWORD *)v6 + 10);
              *(_QWORD *)(*((_QWORD *)v6 + 10) + 8LL) = v45;
              *((_QWORD *)v6 + 10) = v45;
              if ( LastError )
LABEL_123:
                LastError = -2147221148;
            }
            break;
          }
          v42 += 39;
          if ( !v42 )
            break;
        }
      }
      if ( LastError == -2147221148 )
        goto LABEL_134;
      *(_QWORD *)&v108 = *(_QWORD *)(v108 + 8);
    }
    goto LABEL_126;
  }
  while ( (*(_BYTE *)(v123 + 48LL * v41 + 40) & 3) == 0
       || v39[3] != *(_QWORD *)(v123 + 48LL * v41 + 8)
       || v39[4] != *(_QWORD *)(v123 + 48LL * v41 + 16) )
  {
    if ( ++v41 >= v122 )
      goto LABEL_105;
  }
  if ( *(_DWORD *)v8 == 1 )
  {
    *(_QWORD *)&v108 = *(_QWORD *)(v108 + 8);
    *(_QWORD *)(*v39 + 8) = v39[1];
    *(_QWORD *)v39[1] = *v39;
    v39[1] = (__int64)v6 + 80;
    *v39 = *((_QWORD *)v6 + 10);
    *(_QWORD *)(*((_QWORD *)v6 + 10) + 8LL) = v39;
    *((_QWORD *)v6 + 10) = v39;
    v40 = v122;
    goto LABEL_105;
  }
LABEL_132:
  LastError = -2147221148;
  if ( !*(_DWORD *)&gDebugLevel )
    goto LABEL_134;
  _DebugMsg(4u, 0xC17u, *((_QWORD *)v12 + 5));
  *(_QWORD *)&v108 = *((_QWORD *)&v108 + 1);
LABEL_139:
  if ( *((_DWORD *)v6 + 99) != 1 && *((_DWORD *)v6 + 74) )
    RevertToSelf();
  if ( LastError )
    goto LABEL_145;
  if ( !(unsigned int)CAppInfo::CopyToApplicationInfo(v12, v99) )
    goto LABEL_144;
  v46 = (CAppInfo *)*((_QWORD *)v6 + 11);
  v47 = *((_QWORD *)v6 + 12);
  *((_QWORD *)v6 + 12) = v46;
  if ( v46 == (CManagedAppProcessor *)((char *)v6 + 80) )
    v46 = 0;
  *((_QWORD *)v6 + 13) = v47;
  if ( v46 )
  {
    v48 = v94;
    do
    {
      if ( (unsigned int)(*((_DWORD *)v46 + 57) - 4) <= 1 )
      {
        v49 = (void *)*((_QWORD *)v48 + 1);
        v50 = LocalAlloc(0, 56LL * (*v48 + 1));
        v51 = v94;
        v52 = 0;
        *((_QWORD *)v94 + 1) = v50;
        if ( v50 )
        {
          if ( v49 )
          {
            memcpy_0(v50, v49, 56LL * *v51);
            v51 = v94;
          }
          v52 = CAppInfo::CopyToApplicationInfo(v46, (struct __MIDL_appmgmt_0004 *)(*((_QWORD *)v51 + 1) + 56LL * *v51));
        }
        LocalFree(v49);
        if ( !v52 )
        {
          v5 = v94;
          LastError = 14;
          *v94 = 0;
          goto LABEL_81;
        }
        v48 = v94;
        ++*v94;
      }
      v46 = *(CAppInfo **)(*((_QWORD *)v6 + 12) + 8LL);
      *((_QWORD *)v6 + 12) = v46;
      if ( v46 == (CManagedAppProcessor *)((char *)v6 + 80) )
        v46 = 0;
    }
    while ( v46 );
  }
  v53 = hKey;
  *((_QWORD *)v6 + 12) = *((_QWORD *)v6 + 13);
  if ( *(_DWORD *)v53 != 1 )
  {
    *(_QWORD *)&Buf1.Data1 = 0;
    v91 = 0;
    hKey = 0;
    v93 = 0;
    v131[0] = 0;
    LastError = RegOpenKeyExW(
                  phkResult,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy",
                  0,
                  0xF003Fu,
                  &hKey);
    if ( LastError )
      goto LABEL_169;
    LastError = RegCreateKeyExW(hKey, L"TempClasses", 0, 0, 0, 0xF003Fu, 0, &v93, 0);
    if ( LastError )
      goto LABEL_169;
    if ( *((_DWORD *)v6 + 99) == 1
      || (v54 = (_DWORD *)((char *)v6 + 296), !*((_DWORD *)v6 + 74))
      || ImpersonateLoggedOnUser(*((HANDLE *)v6 + 33)) )
    {
      v54 = (_DWORD *)((char *)v101 + 296);
    }
    else
    {
      if ( *(_DWORD *)&gDebugLevel )
      {
        v55 = GetLastError();
        _DebugMsg(LastError + 2, 0xBC4u, v55);
      }
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_169:
        CEvents::Install((CManagedAppProcessor *)((char *)v6 + 344), LastError, v12);
        goto LABEL_170;
      }
    }
    v60 = CAppInfo::CopyScriptIfNeeded(v12);
    LastError = v60;
    if ( *((_DWORD *)v6 + 99) != 1 && *v54 )
    {
      RevertToSelf();
      v60 = LastError;
    }
    if ( v60 )
      goto LABEL_169;
    if ( (*(_DWORD *)v53 == 2 || (v61 = 8, *(_DWORD *)v53 == 3)) && (v61 = 264, *(_DWORD *)v53 == 3)
      || *(_DWORD *)v53 == 4 )
    {
      v62 = 128;
      v61 |= 0x80u;
    }
    else
    {
      v62 = 128;
    }
    LastError = CallMsiAdvertiseScript(*((const unsigned __int16 **)v12 + 11), v61, &v93, 0);
    if ( LastError )
      goto LABEL_169;
    if ( *(_DWORD *)v53 != 4 )
    {
      v63 = (BYTE *)*((_QWORD *)v53 + 1);
      if ( *(_DWORD *)v53 != 2 )
        goto LABEL_202;
      cbData = 256;
      LastError = RegOpenKeyExW(v93, (LPCWSTR)v63, 0, 0xF003Fu, &v91);
      if ( LastError )
        goto LABEL_210;
      LastError = RegQueryValueExW(v91, &word_18002F430, 0, 0, (LPBYTE)Data, &cbData);
      RegCloseKey(v91);
      if ( LastError )
        goto LABEL_210;
      v63 = (BYTE *)Data;
LABEL_202:
      LastError = RegOpenKeyExW(v93, (LPCWSTR)v63, 0, 0xF003Fu, (PHKEY)&Buf1);
      if ( LastError )
      {
LABEL_210:
        cbData = 256;
      }
      else
      {
        LastError = RegOpenKeyExW(*(HKEY *)&Buf1.Data1, L"shell\\open\\command", 0, 0xF003Fu, &v91);
        RegCloseKey(*(HKEY *)&Buf1.Data1);
        cbData = 256;
        if ( !LastError )
        {
          LastError = RegQueryValueExW(v91, L"command", 0, 0, (LPBYTE)v131, &cbData);
          if ( !LastError && (gDebugLevel & 2) != 0 && *(_DWORD *)&gDebugLevel )
            _DebugMsg(LastError + 4, 0xC18u, v63);
          goto LABEL_208;
        }
      }
      goto LABEL_209;
    }
    v64 = 2147483646;
    v65 = L"CLSID\\";
    v66 = 2147483646;
    v67 = (BYTE *)Data;
    do
    {
      if ( !v66 )
        break;
      if ( !*v65 )
        break;
      *(_WORD *)v67 = *v65++;
      v67 += 2;
      --v66;
      --v62;
    }
    while ( v62 );
    v68 = v67 - 2;
    if ( v62 )
      v68 = v67;
    *(_WORD *)v68 = 0;
    if ( !v62 )
      goto LABEL_218;
    v69 = 2147483646;
    v70 = v130;
    v71 = 122;
    v72 = &v128;
    do
    {
      if ( !v69 )
        break;
      if ( !*v70 )
        break;
      *(_WORD *)v72 = *v70++;
      v72 += 2;
      --v69;
      --v71;
    }
    while ( v71 );
    v73 = v72 - 2;
    if ( v71 )
      v73 = v72;
    *(_WORD *)v73 = 0;
    if ( v71 )
    {
      v74 = 84;
      if ( ((_BYTE)v53[6] & 1) != 0 )
      {
        v75 = 2147483646;
        v76 = L"\\InprocServer32";
        v77 = 84;
        v78 = v129;
        do
        {
          if ( !v75 )
            break;
          if ( !*v76 )
            break;
          *v78++ = *v76++;
          --v75;
          --v77;
        }
        while ( v77 );
        v79 = v78 - 1;
        if ( v77 )
          v79 = v78;
        *v79 = 0;
        if ( !v77 )
          goto LABEL_234;
        cbData = 256;
        LastError = RegOpenKeyExW(v93, Data, 0, 0xF003Fu, &v91);
        if ( !LastError )
        {
          LastError = RegQueryValueExW(v91, L"InprocServer32", 0, 0, (LPBYTE)v131, &cbData);
          if ( !LastError && *(_DWORD *)&gDebugLevel )
            _DebugMsg(4u, 0xC19u);
          RegCloseKey(v91);
        }
      }
      if ( v131[0] || ((_BYTE)v53[6] & 4) == 0 )
        goto LABEL_209;
      v80 = L"\\LocalServer32";
      v81 = v129;
      do
      {
        if ( !v64 )
          break;
        if ( !*v80 )
          break;
        *v81++ = *v80++;
        --v64;
        --v74;
      }
      while ( v74 );
      v82 = v81 - 1;
      if ( v74 )
        v82 = v81;
      *v82 = 0;
      if ( v74 )
      {
        v83 = RegOpenKeyExW(v93, Data, 0, 0xF003Fu, &v91);
        cbData = 256;
        LastError = v83;
        if ( !v83 )
        {
          LastError = RegQueryValueExW(v91, L"LocalServer32", 0, 0, (LPBYTE)v131, &cbData);
          if ( !LastError && *(_DWORD *)&gDebugLevel )
            _DebugMsg(4u, 0xC1Au);
LABEL_208:
          RegCloseKey(v91);
        }
LABEL_209:
        CallMsiAdvertiseScript(*((const unsigned __int16 **)v12 + 11), v61, &v93, 1);
      }
      else
      {
LABEL_234:
        LastError = 122;
      }
    }
    else
    {
LABEL_218:
      LastError = 122;
    }
LABEL_170:
    if ( v93 )
    {
      RegCloseKey(v93);
      RegDeleteKeyW(hKey, L"TempClasses");
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( !LastError )
    {
      v56 = -1;
      v57 = -1;
      do
        ++v57;
      while ( v131[v57] );
      v58 = (unsigned __int16 *)LocalAlloc(0, 2 * v57 + 2);
      *((_QWORD *)v99 + 4) = v58;
      if ( v58 )
      {
        do
          ++v56;
        while ( v131[v56] );
        v59 = StringCchCopyW(v58, v56 + 1, v131);
        if ( v59 >= 0 )
          goto LABEL_181;
        LastError = (unsigned __int16)v59;
        if ( !(_WORD)v59 )
          goto LABEL_181;
      }
      else
      {
LABEL_144:
        LastError = 14;
      }
    }
LABEL_145:
    v5 = v94;
    goto LABEL_81;
  }
LABEL_181:
  v6 = v92;
  if ( (*((_DWORD *)v12 + 56) & 0x200) != 0 )
    SetSystemRestorePoint(*((unsigned __int16 **)v12 + 5));
  v5 = v94;
LABEL_82:
  RtlLeaveCriticalSection(&gAppCS);
LABEL_83:
  v7 = v102;
LABEL_84:
  if ( !LastError )
  {
    *v7 = v6;
    goto LABEL_272;
  }
LABEL_259:
  while ( *(_DWORD *)v5 )
  {
    v84 = (unsigned int)(*(_DWORD *)v5 - 1);
    *(_DWORD *)v5 = v84;
    FreeApplicationInfo((struct __MIDL_appmgmt_0004 *)(*((_QWORD *)v5 + 1) + 56 * v84));
  }
  LocalFree(*((HLOCAL *)v5 + 1));
  v85 = v99;
  v86 = v99;
  *(_DWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = 0;
  FreeApplicationInfo(v86);
  *(_OWORD *)v85 = 0;
  *((_OWORD *)v85 + 1) = 0;
  *((_OWORD *)v85 + 2) = 0;
  *((_QWORD *)v85 + 6) = 0;
  v87 = v100;
  if ( v100 )
  {
    if ( v12 )
      LogRsopInstallData(v100, v12);
    CManagedAppProcessor::~CManagedAppProcessor(v87);
    operator delete(v87, 0x1F0u);
  }
  if ( v12 )
  {
    CAppInfo::~CAppInfo(v12);
    operator delete(v12, 0x1C8u);
  }
  if ( v6 )
  {
    v88 = (HMODULE *)*((_QWORD *)v6 + 3);
    if ( v88 )
    {
      if ( *v88 )
        FreeLibrary(*v88);
      operator delete(v88, 8u);
    }
    operator delete(v6, 0x38u);
  }
LABEL_272:
  if ( (int)LastError > 0 && *(_DWORD *)&gDebugLevel )
    _DebugMsg(4u, 0xBEFu, LastError);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( pGPOList )
    FreeGPOListW(pGPOList);
  ReleasePackageInfo(&v116);
LABEL_282:
  CRsopAppContext::~CRsopAppContext((CRsopAppContext *)v112);
  CAppList::~CAppList((CAppList *)v103);
  return LastError;
}

```

## disassembly

```asm
0x180003370  mov     [rsp-8+arg_0], rbx
0x180003375  push    rbp
0x180003376  push    rsi
0x180003377  push    rdi
0x180003378  push    r12
0x18000337a  push    r13
0x18000337c  push    r14
0x18000337e  push    r15
0x180003380  lea     rbp, [rsp-4F0h]
0x180003388  sub     rsp, 5F0h
0x18000338f  mov     rax, cs:__security_cookie
0x180003396  xor     rax, rsp
0x180003399  mov     [rbp+520h+var_40], rax
0x1800033a0  mov     r12, [rbp+520h+arg_20]
0x1800033a7  lea     rax, [rbp+520h+var_530]
0x1800033ab  xorps   xmm0, xmm0
0x1800033ae  mov     [rbp+520h+var_528], rax
0x1800033b2  xor     r14d, r14d
0x1800033b5  mov     [rsp+620h+hKey], rdx
0x1800033ba  mov     rbx, r8
0x1800033bd  mov     [rbp+520h+var_580], r9
0x1800033c1  lea     rax, [rbp+520h+var_530]
0x1800033c5  mov     [rbp+520h+var_568], rbx
0x1800033c9  mov     [rbp+520h+var_530], rax
0x1800033cd  lea     rcx, [rbp+520h+var_430]; void *
0x1800033d4  lea     rax, ??_7CAppList@@6B@; const CAppList::`vftable'
0x1800033db  mov     [rsp+620h+var_5B0], r12
0x1800033e0  mov     [rbp+520h+var_560], rax
0x1800033e4  mov     rsi, rdx
0x1800033e7  xor     eax, eax
0x1800033e9  movdqa  [rbp+520h+var_520], xmm0
0x1800033ee  xorps   xmm1, xmm1
0x1800033f1  mov     [rbp+520h+var_440], rax
0x1800033f8  xor     edx, edx; Val
0x1800033fa  mov     [rbp+520h+var_558], r14
0x1800033fe  mov     r8d, 0D0h; Size
0x180003404  movdqa  [rbp+520h+var_550], xmm0
0x180003409  mov     r15, r9
0x18000340c  movdqa  [rbp+520h+var_540], xmm1
0x180003411  movdqa  [rbp+520h+var_510], xmm0
0x180003416  mov     [rbp+520h+var_500], 80004005h
0x18000341d  mov     [rbp+520h+var_4FC], r14d
0x180003421  mov     [rbp+520h+TokenHandle], r14
0x180003425  mov     [rbp+520h+phkResult], r14
0x180003429  movups  [rbp+520h+var_460], xmm0
0x180003430  movups  xmmword ptr [rbp+520h+var_450.Data1], xmm0
0x180003437  movups  xmmword ptr [rbp+520h+var_350.dwPlatformId], xmm0
0x18000343e  movups  [rbp+520h+var_340], xmm0
0x180003445  call    memset_0
0x18000344a  xorps   xmm0, xmm0
0x18000344d  mov     [rsp+620h+cbData], r14d
0x180003452  mov     r9, rsi; struct _APPKEY *
0x180003455  lea     edx, [r14+3]; unsigned int
0x180003459  xor     r8d, r8d; void *
0x18000345c  lea     rcx, [rbp+520h+var_4F0]; this
0x180003460  movups  [rbp+520h+Buf1], xmm0
0x180003467  call    ??0CRsopAppContext@@QEAA@KPEAXPEAU_APPKEY@@@Z; CRsopAppContext::CRsopAppContext(ulong,void *,_APPKEY *)
0x18000346c  mov     [rbx], r14
0x18000346f  xorps   xmm0, xmm0
0x180003472  movups  xmmword ptr [r15], xmm0
0x180003476  xor     eax, eax
0x180003478  xor     ecx, ecx; BindingHandle
0x18000347a  movups  xmmword ptr [r15+10h], xmm0
0x18000347f  mov     [rbp+520h+TokenHandle], r14
0x180003483  movups  xmmword ptr [r15+20h], xmm0
0x180003488  mov     [r15+30h], rax
0x18000348c  movups  xmmword ptr [r12], xmm0
0x180003491  mov     [rbp+520h+phkResult], r14
0x180003495  mov     [rbp+520h+pGPOList], r14
0x180003499  call    cs:__imp_RpcImpersonateClient
0x18000349f  mov     edi, eax
0x1800034a1  test    eax, eax
0x1800034a3  jnz     loc_180004736
0x1800034a9  call    cs:__imp_GetCurrentThread
0x1800034af  lea     r9, [rbp+520h+TokenHandle]; TokenHandle
0x1800034b3  mov     edx, 2000Eh; DesiredAccess
0x1800034b8  mov     rcx, rax; ThreadHandle
0x1800034bb  lea     r8d, [r14+1]; OpenAsSelf
0x1800034bf  call    cs:__imp_OpenThreadToken
0x1800034c5  mov     dword ptr [rsp+620h+var_5C8], eax
0x1800034c9  test    eax, eax
0x1800034cb  jnz     short loc_1800034D9
0x1800034cd  call    cs:__imp_GetLastError
0x1800034d3  mov     edi, eax
0x1800034d5  test    eax, eax
0x1800034d7  jnz     short loc_1800034EE
0x1800034d9  lea     rdx, [rbp+520h+phkResult]; phkResult
0x1800034dd  mov     ecx, 10000000h; samDesired
0x1800034e2  call    cs:__imp_RegOpenCurrentUser
0x1800034e8  mov     edi, eax
0x1800034ea  test    eax, eax
0x1800034ec  jz      short loc_180003503
0x1800034ee  mov     rcx, [rbp+520h+TokenHandle]; hObject
0x1800034f2  call    cs:__imp_CloseHandle
0x1800034f8  call    cs:__imp_RevertToSelf
0x1800034fe  jmp     loc_180004736
0x180003503  mov     [rbp+520h+var_578], r14
0x180003507  mov     r13, r14
0x18000350a  call    ?LogTime@@YAXXZ; LogTime(void)
0x18000350f  mov     r8d, [rsi+4]; int
0x180003513  lea     rcx, [rbp+520h+var_350.dwVersionHi]; struct tagCSPLATFORM *
0x18000351a  mov     edx, 1; int
0x18000351f  mov     dword ptr [rbp+520h+var_340+4], 800h
0x180003529  call    ?GetDefaultPlatform@@YAXPEAUtagCSPLATFORM@@HJ@Z; GetDefaultPlatform(tagCSPLATFORM *,int,long)
0x18000352e  mov     ecx, [rsi]
0x180003530  or      eax, 0FFFFFFFFh
0x180003533  mov     dword ptr [rbp+520h+var_340+8], eax
0x180003539  mov     dword ptr [rbp+520h+var_340+0Ch], eax
0x18000353f  mov     eax, 4
0x180003544  mov     [rbp+520h+var_350.dwPlatformId], 17h
0x18000354e  sub     ecx, 1
0x180003551  jz      loc_180003659
0x180003557  sub     ecx, 1
0x18000355a  jz      loc_180003631
0x180003560  sub     ecx, 1
0x180003563  jz      loc_18000360D
0x180003569  cmp     ecx, 1
0x18000356c  jnz     loc_180003692
0x180003572  mov     rax, [rsi+8]
0x180003576  xor     edi, edi
0x180003578  cmp     dword ptr [rsi+4], 9
0x18000357c  mov     r8d, [rsi+18h]
0x180003580  mov     qword ptr [rbp+520h+var_460+8], rax
0x180003587  mov     rax, [rsi+10h]
0x18000358b  mov     qword ptr [rbp+520h+var_450.Data1], rax
0x180003592  mov     dword ptr [rbp+520h+var_460], edi
0x180003598  jz      short loc_1800035A0
0x18000359a  cmp     dword ptr [rsi+4], 6
0x18000359e  jnz     short loc_1800035C8
0x1800035a0  test    r8b, 3
0x1800035a4  jz      short loc_1800035C8
0x1800035a6  mov     edx, r8d
0x1800035a9  mov     eax, r8d
0x1800035ac  and     edx, 1
0x1800035af  shl     edx, 1Ch
0x1800035b2  mov     ecx, edx
0x1800035b4  bts     ecx, 1Dh
0x1800035b8  test    r8b, 2
0x1800035bc  cmovz   ecx, edx
0x1800035bf  and     eax, 0FFFFFFFCh
0x1800035c2  mov     r8d, ecx
0x1800035c5  or      r8d, eax
0x1800035c8  lea     rdx, [rbp+520h+var_230]; unsigned __int16 *
0x1800035cf  mov     [rbp+520h+var_350.dwPlatformId], r8d
0x1800035d6  lea     rcx, [rsi+8]; struct _GUID *
0x1800035da  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x1800035df  cmp     cs:?gDebugLevel@@3KA, edi; ulong gDebugLevel
0x1800035e5  jz      loc_180003692
0x1800035eb  mov     r9d, [rbp+520h+var_350.dwPlatformId]
0x1800035f2  lea     r8, [rbp+520h+var_230]
0x1800035f9  mov     edx, 0BEDh; unsigned int
0x1800035fe  mov     ecx, 4; unsigned int
0x180003603  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180003608  jmp     loc_180003692
0x18000360d  mov     r8, [rsi+8]
0x180003611  xor     r9d, r9d
0x180003614  cmp     cs:?gDebugLevel@@3KA, r9d; ulong gDebugLevel
0x18000361b  mov     dword ptr [rbp+520h+var_460], eax
0x180003621  mov     qword ptr [rbp+520h+var_460+8], r8
0x180003628  jz      short loc_180003692
0x18000362a  mov     edx, 0BECh
0x18000362f  jmp     short loc_18000368B
0x180003631  mov     r8, [rsi+8]
0x180003635  xor     r9d, r9d
0x180003638  cmp     cs:?gDebugLevel@@3KA, r9d; ulong gDebugLevel
0x18000363f  mov     dword ptr [rbp+520h+var_460], 1
0x180003649  mov     qword ptr [rbp+520h+var_460+8], r8
0x180003650  jz      short loc_180003692
0x180003652  mov     edx, 0BEBh
0x180003657  jmp     short loc_18000368B
0x180003659  movups  xmm0, xmmword ptr [rsi+10h]
0x18000365d  mov     r8, [rsi+8]
0x180003661  xor     r9d, r9d
0x180003664  cmp     cs:?gDebugLevel@@3KA, r9d; ulong gDebugLevel
0x18000366b  movdqu  xmmword ptr [rbp+520h+var_450.Data1], xmm0
0x180003673  mov     dword ptr [rbp+520h+var_460], 5
0x18000367d  mov     qword ptr [rbp+520h+var_460+8], r8
0x180003684  jz      short loc_180003692
0x180003686  mov     edx, 0BEAh; unsigned int
0x18000368b  mov     ecx, eax; unsigned int
0x18000368d  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180003692  lea     r8, [rbp+520h+var_430]
0x180003699  lea     rdx, [rbp+520h+var_350]
0x1800036a0  lea     rcx, [rbp+520h+var_460]
0x1800036a7  call    CsGetAppInfo
0x1800036ac  mov     edi, eax
0x1800036ae  call    cs:__imp_RevertToSelf
0x1800036b4  xor     eax, eax
0x1800036b6  test    edi, edi
0x1800036b8  jnz     loc_180003854
0x1800036be  xor     ecx, ecx; BindingHandle
0x1800036c0  call    cs:__imp_RpcImpersonateClient
0x1800036c6  xor     esi, esi
0x1800036c8  mov     edi, eax
0x1800036ca  test    eax, eax
0x1800036cc  jnz     loc_180003A6E
0x1800036d2  lea     rcx, [rbp+520h+pGPOList]; ppGPOList
0x1800036d6  call    ?GetCurrentUserGPOList@@YAKPEAPEAU_GROUP_POLICY_OBJECTW@@@Z; GetCurrentUserGPOList(_GROUP_POLICY_OBJECTW * *)
0x1800036db  mov     edi, eax
0x1800036dd  mov     dword ptr [rsp+620h+var_5B8], eax
0x1800036e1  call    cs:__imp_RevertToSelf
0x1800036e7  test    edi, edi
0x1800036e9  jnz     loc_180004625
0x1800036ef  mov     rbx, [rbp+520h+pGPOList]
0x1800036f3  lea     rdx, [rbp+520h+String2]; unsigned __int16 *
0x1800036fa  lea     rcx, [rbp+520h+var_3CC]; struct _GUID *
0x180003701  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x180003706  jmp     short loc_180003729
0x180003708  mov     rsi, [rbx+90h]
0x18000370f  lea     rcx, [rbx+20h]; lpString1
0x180003713  lea     rdx, [rbp+520h+String2]; lpString2
0x18000371a  call    cs:__imp_lstrcmpiW
0x180003720  test    eax, eax
0x180003722  jz      short loc_180003730
0x180003724  mov     rbx, rsi
0x180003727  xor     esi, esi
0x180003729  test    rbx, rbx
0x18000372c  jnz     short loc_180003708
0x18000372e  jmp     short loc_18000373B
0x180003730  mov     rbx, [rbx+18h]
0x180003734  xor     esi, esi
0x180003736  test    rbx, rbx
0x180003739  jnz     short loc_180003742
0x18000373b  lea     rbx, word_18002F430
0x180003742  mov     r8d, [rbp+520h+var_424]
0x180003749  mov     ecx, r8d
0x18000374c  sub     ecx, 5
0x18000374f  jz      loc_1800037D9
0x180003755  cmp     ecx, 1
0x180003758  jz      short loc_180003787
0x18000375a  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x180003760  jz      short loc_18000377D
0x180003762  mov     r9, [rbp+520h+var_430]
0x180003769  mov     edx, 0C02h; unsigned int
0x18000376e  mov     ecx, 4; unsigned int
0x180003773  mov     [rsp+620h+var_600], rbx
0x180003778  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000377d  mov     edi, 80040164h
0x180003782  jmp     loc_180004625
0x180003787  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x18000378d  jz      short loc_1800037A8
0x18000378f  mov     r8, [rbp+520h+var_430]
0x180003796  mov     r9, rbx
0x180003799  mov     edx, 0C01h; unsigned int
0x18000379e  mov     ecx, 4; unsigned int
0x1800037a3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800037a8  mov     rcx, [rbp+520h+var_430]; unsigned __int16 *
0x1800037af  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x1800037b4  mov     rcx, rbx; unsigned __int16 *
0x1800037b7  mov     [r15+8], rax
0x1800037bb  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x1800037c0  mov     rcx, [rbp+520h+var_420]; unsigned __int16 *
0x1800037c7  mov     [r15+10h], rax
0x1800037cb  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x1800037d0  mov     [r15+28h], rax
0x1800037d4  jmp     loc_180003A6A
0x1800037d9  cmp     cs:?gDebugLevel@@3KA, esi; ulong gDebugLevel
0x1800037df  jz      short loc_1800037FA
0x1800037e1  mov     r8, [rbp+520h+var_430]
0x1800037e8  mov     r9, rbx
0x1800037eb  mov     edx, 0C00h; unsigned int
0x1800037f0  mov     ecx, 4; unsigned int
0x1800037f5  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800037fa  mov     rsi, [rsp+620h+hKey]
0x1800037ff  test    edi, edi
0x180003801  jnz     loc_18000460D
0x180003807  lea     edx, [rdi+38h]; uBytes
0x18000380a  xor     ecx, ecx; uFlags
0x18000380c  call    cs:__imp_LocalAlloc
0x180003812  mov     [rsp+620h+var_5C0], rax
0x180003817  mov     r15, rax
0x18000381a  test    rax, rax
0x18000381d  jz      loc_1800038DD
0x180003823  lea     edx, [rdi+8]; uBytes
0x180003826  mov     [rax], r14
0x180003829  xor     ecx, ecx; uFlags
0x18000382b  mov     [rax+8], r14
0x18000382f  mov     [rax+10h], r14d
0x180003833  call    cs:__imp_LocalAlloc
0x180003839  test    rax, rax
0x18000383c  jz      short loc_18000388B
0x18000383e  lea     rdx, [rsp+620h+var_5B8]; unsigned int *
0x180003843  mov     rcx, rax; this
0x180003846  call    ??0CLoadMsi@@QEAA@AEAK@Z; CLoadMsi::CLoadMsi(ulong &)
0x18000384b  mov     edi, dword ptr [rsp+620h+var_5B8]
0x18000384f  mov     rbx, rax
0x180003852  jmp     short loc_18000388E
0x180003854  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18000385a  jz      short loc_18000386E
0x18000385c  mov     r8d, edi
0x18000385f  mov     edx, 0BEEh; unsigned int
0x180003864  mov     ecx, 4; unsigned int
0x180003869  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000386e  xor     edx, edx; Val
0x180003870  lea     rcx, [rbp+520h+var_430]; void *
0x180003877  mov     r8d, 0D0h; Size
0x18000387d  call    memset_0
0x180003882  mov     dword ptr [rsp+620h+var_5B8], edi
0x180003886  jmp     loc_1800037FF
0x18000388b  mov     rbx, r14
  ... truncated ...
```
