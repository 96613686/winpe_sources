# ActivateInputProfileWorker(ushort const *)

- ea: `0x180006d90`
- end: `0x180007fac`
- name: `?ActivateInputProfileWorker@@YAHPEBG@Z`
- size: `4636`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e18c`
- `0x1800962b0`

## callees

- `0x180002dbc`
- `0x180004b70`
- `0x180006d90`
- `0x180007fc0`
- `0x180007ff0`
- `0x180008094`
- `0x1800080d0`
- `0x180008a60`
- `0x18000a6d8`
- `0x18000a72c`
- `0x18000a7d0`
- `0x18001da0c`
- `0x180032850`
- `0x1800332d0`
- `0x1800333e0`
- `0x1800342ac`
- `0x18003a1b0`
- `0x18003b860`
- `0x180047e40`
- `0x1800483e4`
- `0x18004de54`
- `0x180058dd8`
- `0x180060610`
- `0x180061470`
- `0x18006c000`
- `0x18006caa0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180007188`
- `KERNEL32!LocalAlloc` at `0x1800071ae`
- `KERNEL32!LocalAlloc` at `0x180007188`
- `KERNEL32!LocalAlloc` at `0x1800071ae`
- `KERNEL32!LocalFree` at `0x180007481`
- `KERNEL32!LocalFree` at `0x18000748b`
- `KERNEL32!LocalFree` at `0x180007784`
- `KERNEL32!LocalFree` at `0x18000778e`
- `KERNEL32!LocalFree` at `0x1800078f9`
- `KERNEL32!LocalFree` at `0x180007903`
- `KERNEL32!LocalFree` at `0x180007481`
- `KERNEL32!LocalFree` at `0x18000748b`
- `KERNEL32!LocalFree` at `0x180007784`
- `KERNEL32!LocalFree` at `0x18000778e`
- `KERNEL32!LocalFree` at `0x1800078f9`
- `KERNEL32!LocalFree` at `0x180007903`
- `KERNEL32!LoadLibraryW` at `0x180007ea4`
- `KERNEL32!LoadLibraryW` at `0x180007ea4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007c52`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007c52`
- `KERNEL32!GetProcAddress` at `0x180007eb9`
- `KERNEL32!GetProcAddress` at `0x180007eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007114`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007114`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800072cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800076ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800072cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800076ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800073c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000750e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007522`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000753d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800076fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007be1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007bfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800073c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000750e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007522`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000753d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800076fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007bd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007be1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007bfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e93`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006f2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006fd4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000706c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800079f3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007a51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007aba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007c9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007d01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007d62`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007dc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e93`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006f2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006fd4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000706c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800079f3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007a51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007aba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007c9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007d01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007d62`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007dc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180006e48`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180006ee0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180006f89`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007021`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007ad6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180006e48`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180006ee0`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180006f89`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007021`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007ad6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180007260`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180007260`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007169`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007169`
- `USER32!ActivateKeyboardLayout` at `0x1800077eb`
- `USER32!ActivateKeyboardLayout` at `0x1800077eb`

## string_xrefs

- `0x180007417`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x18000746c`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180007751`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x18000785c`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x1800078c3`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180007b36`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180007b90`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180007f28`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180007eaf`: `TF_CreateInputProcessorProfiles`
- `0x180007e9d`: `msctf.dll`

## pseudocode

```c
__int64 __fastcall ActivateInputProfileWorker(RTL_SRWLOCK *a1)
{
  HKEY v2; // r14
  HKEY v3; // rdi
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  HKEY v6; // rdi
  LSTATUS v7; // eax
  LSTATUS v8; // ebx
  LSTATUS v9; // eax
  HKEY v10; // rdi
  LSTATUS v11; // eax
  LSTATUS v12; // ebx
  HKEY v13; // rdi
  LSTATUS v14; // eax
  LSTATUS v15; // ebx
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  HKEY v19; // rsi
  DWORD v20; // ebx
  unsigned int v21; // r13d
  unsigned int v22; // r15d
  int v23; // ebx
  HKEY v24; // rdi
  LSTATUS v25; // eax
  HKEY v26; // rbx
  DWORD v27; // edi
  LSTATUS v28; // eax
  __int64 v29; // rdx
  LSTATUS v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // r14d
  struct InputContainer *NextEmptyEntry; // rax
  struct InputContainer *v34; // rsi
  __int64 v35; // rax
  void (__fastcall ***v36)(_QWORD, __int64); // r14
  __int64 v37; // r8
  struct InputContainer *ImeInList; // rcx
  HLOCAL v39; // rdx
  DWORD v40; // edi
  int v41; // r13d
  int v42; // r15d
  FARPROC ProcAddress; // rax
  int v44; // edi
  int v45; // eax
  __int64 v46; // rdx
  unsigned int v47; // eax
  int v48; // eax
  __int64 v49; // rbx
  int v51; // eax
  int v52; // eax
  struct InputContainer *v53; // rax
  struct InputContainer *v54; // rdi
  HMODULE LibraryW; // rax
  char v56; // bl
  int dwOptions; // [rsp+20h] [rbp-E0h]
  bool dwOptionsa; // [rsp+20h] [rbp-E0h]
  bool dwOptionsc; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v62; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  void **v64; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h]
  void **v66; // [rsp+88h] [rbp-78h] BYREF
  HKEY v67; // [rsp+90h] [rbp-70h]
  DWORD cchValueName; // [rsp+98h] [rbp-68h] BYREF
  HKEY v69; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v70; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v71; // [rsp+ACh] [rbp-54h]
  HLOCAL v72; // [rsp+B0h] [rbp-50h]
  void **v73; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v74; // [rsp+C0h] [rbp-40h]
  DWORD cValues; // [rsp+C8h] [rbp-38h] BYREF
  void **v76; // [rsp+D0h] [rbp-30h] BYREF
  HKEY v77; // [rsp+D8h] [rbp-28h]
  void **v78; // [rsp+E0h] [rbp-20h] BYREF
  HKEY v79; // [rsp+E8h] [rbp-18h]
  __int64 v80; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v81[2]; // [rsp+F8h] [rbp-8h] BYREF
  HLOCAL hMem; // [rsp+100h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+108h] [rbp+8h] BYREF
  void **v84; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v85[264]; // [rsp+118h] [rbp+18h] BYREF
  _DWORD *v86; // [rsp+220h] [rbp+120h]
  _DWORD *v87; // [rsp+228h] [rbp+128h] BYREF
  BYTE v88[48]; // [rsp+230h] [rbp+130h] BYREF
  BYTE v89[8]; // [rsp+260h] [rbp+160h] BYREF
  HKEY v90; // [rsp+268h] [rbp+168h]
  BYTE Data[2]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t String[12]; // [rsp+288h] [rbp+188h] BYREF
  unsigned __int16 v93[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v94; // [rsp+2B0h] [rbp+1B0h]
  __int128 v95; // [rsp+2C0h] [rbp+1C0h]
  __int128 v96; // [rsp+2D0h] [rbp+1D0h]
  __int128 v97; // [rsp+2E0h] [rbp+1E0h]
  _OWORD v98[2]; // [rsp+2F0h] [rbp+1F0h]
  unsigned __int16 v99[40]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v100[40]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR ValueName[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  SRWLock = a1;
  v78 = &CInputDllRegKey::`vftable';
  v2 = 0;
  v79 = 0;
  v64 = &CInputDllRegKey::`vftable';
  hKey = 0;
  v73 = &CInputDllRegKey::`vftable';
  v74 = 0;
  v66 = &CInputDllRegKey::`vftable';
  v67 = 0;
  v76 = &CInputDllRegKey::`vftable';
  v77 = 0;
  *(_QWORD *)v89 = &CInputDllRegKey::`vftable';
  v90 = 0;
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v84);
  v84 = &InputTraceLoggingTelemetry::ActivateInputProfile::`vftable';
  InputTraceLoggingTelemetry::ActivateInputProfile::StartActivity(
    (InputTraceLoggingTelemetry::ActivateInputProfile *)&v84,
    (const unsigned __int16 *)a1);
  dwDisposition = 0;
  v62 = 0;
  phkResult = 0;
  v3 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v3 = phkResult;
  v4 = RegCreateKeyExW(v3, L"Keyboard Layout\\Preload", 0, 0, 0, 0x2001Fu, 0, &v62, &dwDisposition);
  v5 = v4;
  if ( !v4 )
  {
    v5 = 0;
LABEL_5:
    v2 = v62;
    v79 = v62;
    goto LABEL_6;
  }
  if ( v4 == 5 )
  {
    v5 = RegCreateKeyExW(v3, L"Keyboard Layout\\Preload", 0, 0, 4u, 0x2001Fu, 0, &v62, &dwDisposition);
    if ( !v5 )
    {
      v5 = CInputDllRegKey::Close((CInputDllRegKey *)&v78);
      goto LABEL_5;
    }
  }
LABEL_6:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    goto LABEL_181;
  dwDisposition = 0;
  v62 = 0;
  phkResult = 0;
  v6 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v6 = phkResult;
  v7 = RegCreateKeyExW(v6, L"Keyboard Layout\\Substitutes", 0, 0, 0, 0x2001Fu, 0, &v62, &dwDisposition);
  v8 = v7;
  if ( !v7 )
  {
    v8 = 0;
    if ( !hKey )
    {
LABEL_15:
      hKey = v62;
      goto LABEL_16;
    }
    v9 = RegCloseKey(hKey);
LABEL_14:
    v8 = v9;
    goto LABEL_15;
  }
  if ( v7 == 5 )
  {
    v8 = RegCreateKeyExW(v6, L"Keyboard Layout\\Substitutes", 0, 0, 4u, 0x2001Fu, 0, &v62, &dwDisposition);
    if ( !v8 )
    {
      v9 = CInputDllRegKey::Close((CInputDllRegKey *)&v64);
      goto LABEL_14;
    }
  }
LABEL_16:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v8 )
    goto LABEL_181;
  dwDisposition = 0;
  v62 = 0;
  phkResult = 0;
  v10 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v10 = phkResult;
  v11 = RegCreateKeyExW(v10, L"Software\\Microsoft\\CTF\\TIP", 0, 0, 0, 0x2001Fu, 0, &v62, &dwDisposition);
  v12 = v11;
  if ( !v11 )
  {
    v12 = 0;
LABEL_23:
    v74 = v62;
    goto LABEL_24;
  }
  if ( v11 == 5 )
  {
    v12 = RegCreateKeyExW(v10, L"Software\\Microsoft\\CTF\\TIP", 0, 0, 4u, 0x2001Fu, 0, &v62, &dwDisposition);
    if ( !v12 )
    {
      v12 = CInputDllRegKey::Close((CInputDllRegKey *)&v73);
      goto LABEL_23;
    }
  }
LABEL_24:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v12 )
    goto LABEL_181;
  dwDisposition = 0;
  v62 = 0;
  phkResult = 0;
  v13 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v13 = phkResult;
  v14 = RegCreateKeyExW(
          v13,
          L"Software\\Microsoft\\CTF\\HiddenDummyLayouts",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &v62,
          &dwDisposition);
  v15 = v14;
  if ( v14 )
  {
    if ( v14 != 5 )
      goto LABEL_34;
    v15 = RegCreateKeyExW(
            v13,
            L"Software\\Microsoft\\CTF\\HiddenDummyLayouts",
            0,
            0,
            4u,
            0x2001Fu,
            0,
            &v62,
            &dwDisposition);
    if ( v15 )
      goto LABEL_34;
    v16 = CInputDllRegKey::Close((CInputDllRegKey *)&v66);
    goto LABEL_32;
  }
  v15 = 0;
  if ( v67 )
  {
    v16 = RegCloseKey(v67);
LABEL_32:
    v15 = v16;
  }
  v67 = v62;
LABEL_34:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v15 )
    goto LABEL_181;
  v62 = 0;
  v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\CTF\\TIP", 0, 0x20019u, &v62);
  if ( !v17
    || v17 == 5
    && (dwDisposition = 0,
        !RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\CTF\\TIP",
           0,
           0,
           4u,
           0x20019u,
           0,
           &v62,
           &dwDisposition)) )
  {
    v77 = v62;
  }
  v62 = 0;
  v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Keyboard Layouts", 0, 0x20019u, &v62);
  if ( !v18 )
  {
    v19 = v62;
    v90 = v62;
    goto LABEL_41;
  }
  if ( v18 == 5 )
  {
    dwDisposition = 0;
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Keyboard Layouts",
            0,
            0,
            4u,
            0x20019u,
            0,
            &v62,
            &dwDisposition) )
    {
      v19 = v62;
      v90 = v62;
      goto LABEL_41;
    }
  }
  if ( CInputDllRegKey::Open(
         (CInputDllRegKey *)v89,
         HKEY_LOCAL_MACHINE,
         L"System\\ControlSet001\\Control\\Keyboard Layouts",
         0x20019u) )
  {
LABEL_181:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x738,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      dwOptions);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v84, 2147500037LL);
    v84 = &InputTraceLoggingTelemetry::ActivateInputProfile::`vftable';
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v84);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v84);
    *(_QWORD *)v89 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v89);
    v76 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v76);
    v66 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v66);
    v73 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v73);
    v64 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v64);
    v78 = &CInputDllRegKey::`vftable';
    goto LABEL_121;
  }
  v19 = v90;
LABEL_41:
  cValues = 0;
  RegQueryInfoKeyW(v2, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v20 = cValues;
  v21 = 0;
  v22 = 0;
  v71 = 0;
  v72 = LocalAlloc(0x40u, 700LL * cValues);
  if ( v72 )
    v21 = v20;
  v70 = v21;
  v23 = 0;
  v81[1] = 0;
  hMem = LocalAlloc(0x40u, 0xAF0u);
  if ( hMem )
    v23 = 4;
  v81[0] = v23;
  v24 = v2;
  phkResult = 0;
  v69 = 0;
  if ( v2 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &v69) )
    v24 = v69;
  v25 = RegOpenKeyExW(v24, &sourceString, 0, 0x20019u, &phkResult);
  if ( !v25
    || (v26 = 0, v25 == 5)
    && (dwDisposition = 0, !RegCreateKeyExW(v24, &sourceString, 0, 0, 4u, 0x20019u, 0, &phkResult, &dwDisposition)) )
  {
    v26 = phkResult;
  }
  if ( v69 )
    RegCloseKey(v69);
  v27 = 0;
  if ( v26 )
  {
    while ( 1 )
    {
      cchValueName = 256;
      v28 = RegEnumValueW(v26, v27, ValueName, &cchValueName, 0, 0, 0, 0);
      v29 = 255;
      if ( v28 )
        v29 = 0;
      ValueName[v29] = 0;
      if ( v28 )
        break;
      ++v27;
      if ( o_wcstoul_0(ValueName, 0, 10) )
      {
        cchValueName = 18;
        LODWORD(v62) = 0;
        v30 = RegQueryValueExW(v26, ValueName, 0, (LPDWORD)&v62, Data, &cchValueName);
        v31 = 16;
        if ( v30 )
          v31 = 0;
        *(_WORD *)&Data[v31] = 0;
        if ( !v30 )
        {
          v32 = o_wcstoul_0((const wchar_t *)Data, 0, 16);
          if ( v32 )
          {
            NextEmptyEntry = CInputList::GetNextEmptyEntry((CInputList *)&v70);
            v34 = NextEmptyEntry;
            if ( NextEmptyEntry )
            {
              *((_DWORD *)NextEmptyEntry + 3) = 1;
              *((_DWORD *)NextEmptyEntry + 1) = v32;
              *(_WORD *)NextEmptyEntry = v32;
              if ( !((unsigned int (__fastcall *)(void ***, wchar_t *, BYTE *, __int64))v64[1])(&v64, String, Data, 9) )
              {
                v47 = o_wcstoul_0(String, 0, 16);
                *((_DWORD *)v34 + 2) = *((_DWORD *)v34 + 1);
                *((_DWORD *)v34 + 1) = v47;
              }
              *((_DWORD *)v34 + 3) = 1;
              *((_BYTE *)v34 + 16) = 1;
              *((_BYTE *)v34 + 18) = InstallLayoutOrTipPrivateHelpers::IsKeyboardHiddenDummyLayout(
                                       *(_WORD *)v34,
                                       *((_DWORD *)v34 + 1),
                                       (struct CInputDllRegKey *)&v66);
              *((_BYTE *)v34 + 17) = InstallLayoutOrTipPrivateHelpers::IsValidKeyboard(
                                       *((_DWORD *)v34 + 1),
                                       (struct CInputDllRegKey *)v89);
              CLSIDToStringW(&GUID_NULL, (unsigned __int16 *)v34 + 10);
              CLSIDToStringW(&GUID_NULL, (unsigned __int16 *)v34 + 49);
            }
          }
        }
      }
    }
    v19 = v90;
    v22 = v71;
    v21 = v70;
  }
  if ( !v22 )
  {
    v53 = CInputList::GetNextEmptyEntry((CInputList *)&v70);
    v54 = v53;
    if ( v53 )
    {
      *((_DWORD *)v53 + 3) = 1;
      *((_DWORD *)v53 + 1) = 1033;
      *(_WORD *)v53 = 1033;
      *((_WORD *)v53 + 8) = 257;
      CLSIDToStringW(&GUID_NULL, (unsigned __int16 *)v53 + 10);
      CLSIDToStringW(&GUID_NULL, (unsigned __int16 *)v54 + 49);
    }
    v21 = v70;
    v22 = v71;
  }
  if ( v26 )
    RegCloseKey(v26);
  InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
    (struct CInputList *)v81,
    (struct CInputDllRegKey *)&v73,
    0,
    0,
    dwOptionsa);
  InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
    (struct CInputList *)v81,
    (struct CInputDllRegKey *)&v76,
    1,
    1,
    dwOptionsc);
  v35 = ParseItemString(SRWLock);
  v36 = (void (__fastcall ***)(_QWORD, __int64))v35;
  if ( !v35 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x754,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x8007000ELL,
      dwOptionsb);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v84, 2147942414LL);
LABEL_72:
    LocalFree(hMem);
    LocalFree(v72);
    v84 = &InputTraceLoggingTelemetry::ActivateInputProfile::`vftable';
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v84);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v88);
    wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v87);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v85);
    if ( v19 )
      RegCloseKey(v19);
    if ( v77 )
      RegCloseKey(v77);
    v66 = &CInputDllRegKey::`vftable';
    if ( v67 )
    {
      RegCloseKey(v67);
      v67 = 0;
    }
    if ( v74 )
      RegCloseKey(v74);
    v64 = &CInputDllRegKey::`vftable';
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( v79 )
      RegCloseKey(v79);
    return 0;
  }
  v49 = *(_QWORD *)(v35 + 8);
  if ( !v49 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x75C,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x8007000ELL,
      dwOptionsb);
    (**v36)(v36, 1);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v84, 2147942414LL);
    LocalFree(hMem);
    LocalFree(v72);
    v84 = &InputTraceLoggingTelemetry::ActivateInputProfile::`vftable';
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v84);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v84);
    *(_QWORD *)v89 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v89);
    v76 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v76);
    v66 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v66);
    v73 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v73);
    v64 = &CInputDllRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v64);
    v78 = &CInputDllRegKey::`vftable';
LABEL_121:
    CInputDllRegKey::Close((CInputDllRegKey *)&v78);
    return 0;
  }
  if ( *(_DWORD *)v49 == 1 )
  {
    v37 = 0;
    ImeInList = 0;
    v39 = v72;
    if ( v21 )
      ImeInList = (struct InputContainer *)v72;
    while ( ImeInList && (unsigned int)v37 < v22 )
    {
      if ( *(_WORD *)ImeInList == *(_WORD *)(v49 + 4) && *((_DWORD *)ImeInList + 1) == *(_DWORD *)(v49 + 8) )
        goto LABEL_93;
      v37 = (unsigned int)(v37 + 1);
      if ( (unsigned int)v37 >= v21 )
        ImeInList = 0;
      else
        ImeInList = (struct InputContainer *)((char *)v72 + 700 * (unsigned int)v37);
    }
    goto LABEL_71;
  }
  if ( *(_DWORD *)v49 != 2
    || (CLSIDToStringW((const struct _GUID *)(v49 + 12), v100),
        CLSIDToStringW((const struct _GUID *)(v49 + 28), v99),
        (ImeInList = InstallLayoutOrTipPrivateHelpers::FindImeInList(
                       (struct CInputList *)v81,
                       *(_WORD *)(v49 + 4),
                       v100,
                       v99)) == 0) )
  {
LABEL_71:
    (**v36)(v36, 1);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x783,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      dwOptionsb);
    goto LABEL_72;
  }
LABEL_93:
  if ( !*((_BYTE *)ImeInList + 17) )
    goto LABEL_71;
  v80 = 0;
  v40 = *((_DWORD *)ImeInList + 1);
  v69 = 0;
  *(_OWORD *)v93 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Control\\Keyboard Layouts\\%08x";
  v94 = *(_OWORD *)L"urrentControlSet\\Control\\Keyboard Layouts\\%08x";
  v95 = *(_OWORD *)L"ntrolSet\\Control\\Keyboard Layouts\\%08x";
  v96 = *(_OWORD *)L"\\Control\\Keyboard Layouts\\%08x";
  v97 = *(_OWORD *)L"\\Keyboard Layouts\\%08x";
  v98[0] = *(_OWORD *)L"d Layouts\\%08x";
  *(_OWORD *)((char *)v98 + 14) = *(_OWORD *)L"ts\\%08x";
  if ( (v40 & 0xF0000000) != 0xE0000000 )
  {
    v41 = *(unsigned __int16 *)ImeInList;
    dwDisposition = 0;
    v42 = 0;
    StringCchPrintfW(ValueName, 0x104u, v93, v40);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, ValueName, 0, 0x20019u, &v69) )
    {
      LODWORD(v62) = 16;
      if ( !RegQueryValueExW(v69, L"Layout Id", 0, 0, v89, (LPDWORD)&v62) )
      {
        dwDisposition = o_wcstoul_0((const wchar_t *)v89, 0, 16);
        v42 = 1;
      }
      RegCloseKey(v69);
    }
    if ( v42 )
      v40 = dwDisposition + 61440;
    v40 = v41 + (v40 << 16);
  }
  if ( *(_DWORD *)v49 == 1 )
    ActivateKeyboardLayout((HKL)(int)v40, 0);
  ProcAddress = (FARPROC)g_pfnTF_CreateInputProcessorProfiles;
  if ( g_pfnTF_CreateInputProcessorProfiles
    || ((LibraryW = LoadLibraryW(L"msctf.dll")) == 0
      ? (ProcAddress = (FARPROC)g_pfnTF_CreateInputProcessorProfiles)
      : (FARPROC)(ProcAddress = GetProcAddress(LibraryW, "TF_CreateInputProcessorProfiles"),
                  g_pfnTF_CreateInputProcessorProfiles = (__int64)ProcAddress),
        ProcAddress) )
  {
    v44 = ((__int64 (__fastcall *)(__int64 *, HLOCAL, __int64))ProcAddress)(&v80, v39, v37);
  }
  else
  {
    v44 = -2147467259;
  }
  if ( v44 >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v80 + 112LL))(v80, *(unsigned __int16 *)(v49 + 4));
    phkResult = 0;
    v48 = (**(__int64 (__fastcall ***)(__int64, GUID *, HKEY *))v80)(v80, &IID_ITfInputProcessorProfileMgr, &phkResult);
    v44 = v48;
    if ( v48 >= 0 )
    {
      if ( *(_DWORD *)v49 == 1 )
      {
        v52 = (*(__int64 (__fastcall **)(HKEY, __int64, _QWORD, GUID *))(*(_QWORD *)phkResult + 24LL))(
                phkResult,
                2,
                *(unsigned __int16 *)(v49 + 4),
                &GUID_NULL);
        v44 = v52;
        if ( v52 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7A2,
            (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
            (const char *)(unsigned int)v52,
            (int)&GUID_NULL);
      }
      else if ( *(_DWORD *)v49 == 2 )
      {
        v51 = (*(__int64 (__fastcall **)(HKEY, __int64, _QWORD, __int64))(*(_QWORD *)phkResult + 24LL))(
                phkResult,
                1,
                *(unsigned __int16 *)(v49 + 4),
                v49 + 12);
        v44 = v51;
        if ( v51 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7AC,
            (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
            (const char *)(unsigned int)v51,
            v49 + 28);
      }
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 16LL))(phkResult);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x798,
        (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
        (const char *)(unsigned int)v48,
        dwOptionsb);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)(unsigned int)v44,
      dwOptionsb);
  }
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v84, (unsigned int)v44);
  (**v36)(v36, 1);
  LocalFree(hMem);
  LocalFree(v72);
  v84 = &InputTraceLoggingTelemetry::ActivateInputProfile::`vftable';
  if ( !v87 )
    goto LABEL_109;
  wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v84,
    &SRWLock);
  if ( !v87 || (v56 = 1, *v87 != 1) )
  {
    v56 = 0;
    wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v87);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v56 )
  {
LABEL_109:
    if ( *v86 == 1 )
    {
      v45 = v86[22];
      LODWORD(v62) = v45;
      v46 = 2147942974LL;
      if ( v45 < 0 )
        v46 = (unsigned int)v45;
      wil::ActivityBase<WinLogonLogonUIRPCServerLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WinLogonLogonUIRPCServerLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v86,
        v46,
        &v62);
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v84);
    }
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v88);
  wil::details::shared_object<wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v87);
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<InputTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v85);
  if ( v19 )
    RegCloseKey(v19);
  if ( v77 )
    RegCloseKey(v77);
  v66 = &CInputDllRegKey::`vftable';
  if ( v67 )
  {
    RegCloseKey(v67);
    v67 = 0;
  }
  if ( v74 )
    RegCloseKey(v74);
  v64 = &CInputDllRegKey::`vftable';
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v79 )
    RegCloseKey(v79);
  return 1;
}

```

## disassembly

```asm
0x180006d90  push    rbp
0x180006d92  push    rbx
0x180006d93  push    rsi
0x180006d94  push    rdi
0x180006d95  push    r12
0x180006d97  push    r13
0x180006d99  push    r14
0x180006d9b  push    r15
0x180006d9d  lea     rbp, [rsp-4D8h]
0x180006da5  sub     rsp, 5D8h
0x180006dac  mov     rax, cs:__security_cookie
0x180006db3  xor     rax, rsp
0x180006db6  mov     [rbp+510h+var_50], rax
0x180006dbd  mov     rbx, rcx
0x180006dc0  mov     [rbp+510h+SRWLock], rcx
0x180006dc4  lea     rsi, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x180006dcb  mov     [rbp+510h+var_530], rsi
0x180006dcf  xor     r12d, r12d
0x180006dd2  mov     r14d, r12d
0x180006dd5  mov     [rbp+510h+var_528], r12
0x180006dd9  mov     [rsp+610h+var_598], rsi
0x180006dde  mov     [rbp+510h+hKey], r12
0x180006de2  mov     [rbp+510h+var_558], rsi
0x180006de6  mov     [rbp+510h+var_550], r12
0x180006dea  mov     [rbp+510h+var_588], rsi
0x180006dee  mov     [rbp+510h+var_580], r12
0x180006df2  mov     [rbp+510h+var_540], rsi
0x180006df6  mov     [rbp+510h+var_538], r12
0x180006dfa  mov     qword ptr [rbp+510h+var_3B0], rsi
0x180006e01  mov     [rbp+510h+var_3A8], r12
0x180006e08  lea     rdx, aActivateinputp; "ActivateInputProfile"
0x180006e0f  lea     rcx, [rbp+510h+var_500]; struct wil::details::IFailureCallback *
0x180006e13  call    ??0?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180006e18  lea     r15, ??_7ActivateInputProfile@InputTraceLoggingTelemetry@@6B@; const InputTraceLoggingTelemetry::ActivateInputProfile::`vftable'
0x180006e1f  mov     [rbp+510h+var_500], r15
0x180006e23  mov     rdx, rbx; unsigned __int16 *
0x180006e26  lea     rcx, [rbp+510h+var_500]; this
0x180006e2a  call    ?StartActivity@ActivateInputProfile@InputTraceLoggingTelemetry@@QEAAXPEBG@Z; InputTraceLoggingTelemetry::ActivateInputProfile::StartActivity(ushort const *)
0x180006e2f  mov     [rsp+610h+dwDisposition], r12d
0x180006e34  mov     [rsp+610h+var_5A8], r12
0x180006e39  mov     [rsp+610h+phkResult], r12
0x180006e3e  lea     rdx, [rsp+610h+phkResult]; phkResult
0x180006e43  mov     ecx, 2001Fh; samDesired
0x180006e48  call    cs:__imp_RegOpenCurrentUser
0x180006e4e  mov     rdi, 0FFFFFFFF80000001h
0x180006e55  test    eax, eax
0x180006e57  cmovz   rdi, [rsp+610h+phkResult]
0x180006e5d  lea     rax, [rsp+610h+dwDisposition]
0x180006e62  mov     [rsp+610h+lpdwDisposition], rax; lpdwDisposition
0x180006e67  lea     rax, [rsp+610h+var_5A8]
0x180006e6c  mov     [rsp+610h+var_5D8], rax; phkResult
0x180006e71  mov     [rsp+610h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180006e76  mov     [rsp+610h+samDesired], 2001Fh; samDesired
0x180006e7e  mov     [rsp+610h+dwOptions], r12d; int
0x180006e83  xor     r9d, r9d; lpClass
0x180006e86  xor     r8d, r8d; Reserved
0x180006e89  lea     rdx, ?c_szPreload@@3QBGB; "Keyboard Layout\\Preload"
0x180006e90  mov     rcx, rdi; hKey
0x180006e93  call    cs:__imp_RegCreateKeyExW
0x180006e99  mov     ebx, eax
0x180006e9b  test    eax, eax
0x180006e9d  jnz     loc_180007C5D
0x180006ea3  mov     ebx, r12d
0x180006ea6  mov     r14, [rsp+610h+var_5A8]
0x180006eab  mov     [rbp+510h+var_528], r14
0x180006eaf  mov     rcx, [rsp+610h+phkResult]; hKey
0x180006eb4  test    rcx, rcx
0x180006eb7  jz      short loc_180006EBF
0x180006eb9  call    cs:__imp_RegCloseKey
0x180006ebf  test    ebx, ebx
0x180006ec1  jnz     loc_180007F19
0x180006ec7  mov     [rsp+610h+dwDisposition], r12d
0x180006ecc  mov     [rsp+610h+var_5A8], r12
0x180006ed1  mov     [rsp+610h+phkResult], r12
0x180006ed6  lea     rdx, [rsp+610h+phkResult]; phkResult
0x180006edb  mov     ecx, 2001Fh; samDesired
0x180006ee0  call    cs:__imp_RegOpenCurrentUser
0x180006ee6  mov     rdi, 0FFFFFFFF80000001h
0x180006eed  test    eax, eax
0x180006eef  cmovz   rdi, [rsp+610h+phkResult]
0x180006ef5  lea     rax, [rsp+610h+dwDisposition]
0x180006efa  mov     [rsp+610h+lpdwDisposition], rax; lpdwDisposition
0x180006eff  lea     rax, [rsp+610h+var_5A8]
0x180006f04  mov     [rsp+610h+var_5D8], rax; phkResult
0x180006f09  mov     [rsp+610h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180006f0e  mov     [rsp+610h+samDesired], 2001Fh; samDesired
0x180006f16  mov     [rsp+610h+dwOptions], r12d; dwOptions
0x180006f1b  xor     r9d, r9d; lpClass
0x180006f1e  xor     r8d, r8d; Reserved
0x180006f21  lea     rdx, ?c_szSubstitutes@@3QBGB; "Keyboard Layout\\Substitutes"
0x180006f28  mov     rcx, rdi; hKey
0x180006f2b  call    cs:__imp_RegCreateKeyExW
0x180006f31  mov     ebx, eax
0x180006f33  test    eax, eax
0x180006f35  jnz     loc_180007CBF
0x180006f3b  mov     ebx, r12d
0x180006f3e  mov     rcx, [rbp+510h+hKey]; hKey
0x180006f42  test    rcx, rcx
0x180006f45  jz      short loc_180006F4F
0x180006f47  call    cs:__imp_RegCloseKey
0x180006f4d  mov     ebx, eax
0x180006f4f  mov     rax, [rsp+610h+var_5A8]
0x180006f54  mov     [rbp+510h+hKey], rax
0x180006f58  mov     rcx, [rsp+610h+phkResult]; hKey
0x180006f5d  test    rcx, rcx
0x180006f60  jz      short loc_180006F68
0x180006f62  call    cs:__imp_RegCloseKey
0x180006f68  test    ebx, ebx
0x180006f6a  jnz     loc_180007F19
0x180006f70  mov     [rsp+610h+dwDisposition], r12d
0x180006f75  mov     [rsp+610h+var_5A8], r12
0x180006f7a  mov     [rsp+610h+phkResult], r12
0x180006f7f  lea     rdx, [rsp+610h+phkResult]; phkResult
0x180006f84  mov     ecx, 2001Fh; samDesired
0x180006f89  call    cs:__imp_RegOpenCurrentUser
0x180006f8f  mov     rdi, 0FFFFFFFF80000001h
0x180006f96  test    eax, eax
0x180006f98  cmovz   rdi, [rsp+610h+phkResult]
0x180006f9e  lea     rax, [rsp+610h+dwDisposition]
0x180006fa3  mov     [rsp+610h+lpdwDisposition], rax; lpdwDisposition
0x180006fa8  lea     rax, [rsp+610h+var_5A8]
0x180006fad  mov     [rsp+610h+var_5D8], rax; phkResult
0x180006fb2  mov     [rsp+610h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180006fb7  mov     [rsp+610h+samDesired], 2001Fh; samDesired
0x180006fbf  mov     [rsp+610h+dwOptions], r12d; dwOptions
0x180006fc4  xor     r9d, r9d; lpClass
0x180006fc7  xor     r8d, r8d; Reserved
0x180006fca  lea     rdx, ?c_szCtfTip@@3QBGB; "Software\\Microsoft\\CTF\\TIP"
0x180006fd1  mov     rcx, rdi; hKey
0x180006fd4  call    cs:__imp_RegCreateKeyExW
0x180006fda  mov     ebx, eax
0x180006fdc  test    eax, eax
0x180006fde  jnz     loc_180007D20
0x180006fe4  mov     ebx, r12d
0x180006fe7  mov     rax, [rsp+610h+var_5A8]
0x180006fec  mov     [rbp+510h+var_550], rax
0x180006ff0  mov     rcx, [rsp+610h+phkResult]; hKey
0x180006ff5  test    rcx, rcx
0x180006ff8  jz      short loc_180007000
0x180006ffa  call    cs:__imp_RegCloseKey
0x180007000  test    ebx, ebx
0x180007002  jnz     loc_180007F19
0x180007008  mov     [rsp+610h+dwDisposition], r12d
0x18000700d  mov     [rsp+610h+var_5A8], r12
0x180007012  mov     [rsp+610h+phkResult], r12
0x180007017  lea     rdx, [rsp+610h+phkResult]; phkResult
0x18000701c  mov     ecx, 2001Fh; samDesired
0x180007021  call    cs:__imp_RegOpenCurrentUser
0x180007027  mov     rdi, 0FFFFFFFF80000001h
0x18000702e  test    eax, eax
0x180007030  cmovz   rdi, [rsp+610h+phkResult]
0x180007036  lea     rax, [rsp+610h+dwDisposition]
0x18000703b  mov     [rsp+610h+lpdwDisposition], rax; lpdwDisposition
0x180007040  lea     rax, [rsp+610h+var_5A8]
0x180007045  mov     [rsp+610h+var_5D8], rax; phkResult
0x18000704a  mov     [rsp+610h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000704f  mov     [rsp+610h+samDesired], 2001Fh; samDesired
0x180007057  mov     [rsp+610h+dwOptions], r12d; dwOptions
0x18000705c  xor     r9d, r9d; lpClass
0x18000705f  xor     r8d, r8d; Reserved
0x180007062  lea     rdx, ?c_szHiddenDummyLayoutsKey@@3QBGB; "Software\\Microsoft\\CTF\\HiddenDummyLa"...
0x180007069  mov     rcx, rdi; hKey
0x18000706c  call    cs:__imp_RegCreateKeyExW
0x180007072  mov     ebx, eax
0x180007074  test    eax, eax
0x180007076  jnz     loc_180007D82
0x18000707c  mov     ebx, r12d
0x18000707f  mov     rcx, [rbp+510h+var_580]; hKey
0x180007083  test    rcx, rcx
0x180007086  jz      short loc_180007090
0x180007088  call    cs:__imp_RegCloseKey
0x18000708e  mov     ebx, eax
0x180007090  mov     rax, [rsp+610h+var_5A8]
0x180007095  mov     [rbp+510h+var_580], rax
0x180007099  mov     rcx, [rsp+610h+phkResult]; hKey
0x18000709e  test    rcx, rcx
0x1800070a1  jz      short loc_1800070A9
0x1800070a3  call    cs:__imp_RegCloseKey
0x1800070a9  test    ebx, ebx
0x1800070ab  jnz     loc_180007F19
0x1800070b1  mov     [rsp+610h+var_5A8], r12
0x1800070b6  lea     rax, [rsp+610h+var_5A8]
0x1800070bb  mov     qword ptr [rsp+610h+dwOptions], rax; phkResult
0x1800070c0  mov     r9d, 20019h; samDesired
0x1800070c6  xor     r8d, r8d; ulOptions
0x1800070c9  lea     rdx, ?c_szCtfTip@@3QBGB; "Software\\Microsoft\\CTF\\TIP"
0x1800070d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800070d7  call    cs:__imp_RegOpenKeyExW
0x1800070dd  test    eax, eax
0x1800070df  jnz     loc_1800079A8
0x1800070e5  mov     rax, [rsp+610h+var_5A8]
0x1800070ea  mov     [rbp+510h+var_538], rax
0x1800070ee  mov     [rsp+610h+var_5A8], r12
0x1800070f3  lea     rax, [rsp+610h+var_5A8]
0x1800070f8  mov     qword ptr [rsp+610h+dwOptions], rax; phkResult
0x1800070fd  mov     r9d, 20019h; samDesired
0x180007103  xor     r8d, r8d; ulOptions
0x180007106  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Key"...
0x18000710d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007114  call    cs:__imp_RegOpenKeyExW
0x18000711a  test    eax, eax
0x18000711c  jnz     loc_180007A06
0x180007122  mov     rsi, [rsp+610h+var_5A8]
0x180007127  mov     [rbp+510h+var_3A8], rsi
0x18000712e  mov     [rbp+510h+cValues], r12d
0x180007132  mov     [rsp+610h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180007137  mov     [rsp+610h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000713c  mov     [rsp+610h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180007141  mov     [rsp+610h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x180007146  lea     rax, [rbp+510h+cValues]
0x18000714a  mov     [rsp+610h+var_5D8], rax; lpcValues
0x18000714f  mov     [rsp+610h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x180007154  mov     qword ptr [rsp+610h+samDesired], r12; lpcbMaxSubKeyLen
0x180007159  mov     qword ptr [rsp+610h+dwOptions], r12; lpcSubKeys
0x18000715e  xor     r9d, r9d; lpReserved
0x180007161  xor     r8d, r8d; lpcchClass
0x180007164  xor     edx, edx; lpClass
0x180007166  mov     rcx, r14; hKey
0x180007169  call    cs:__imp_RegQueryInfoKeyW
0x18000716f  mov     ebx, [rbp+510h+cValues]
0x180007172  mov     r13d, r12d
0x180007175  mov     r15d, r12d
0x180007178  mov     [rbp+510h+var_564], r12d
0x18000717c  imul    rdx, rbx, 2BCh; uBytes
0x180007183  mov     ecx, 40h ; '@'; uFlags
0x180007188  call    cs:__imp_LocalAlloc
0x18000718e  mov     [rbp+510h+var_560], rax
0x180007192  test    rax, rax
0x180007195  cmovnz  r13d, ebx
0x180007199  mov     [rbp+510h+var_568], r13d
0x18000719d  mov     ebx, r12d
0x1800071a0  mov     [rbp+510h+var_514], r12d
0x1800071a4  mov     edx, 0AF0h; uBytes
0x1800071a9  mov     ecx, 40h ; '@'; uFlags
0x1800071ae  call    cs:__imp_LocalAlloc
0x1800071b4  mov     [rbp+510h+hMem], rax
0x1800071b8  test    rax, rax
0x1800071bb  mov     eax, 4
0x1800071c0  cmovnz  ebx, eax
0x1800071c3  mov     [rbp+510h+var_518], ebx
0x1800071c6  mov     rdi, r14
0x1800071c9  mov     [rsp+610h+phkResult], r12
0x1800071ce  mov     [rbp+510h+var_570], r12
0x1800071d2  cmp     r14, 0FFFFFFFF80000001h
0x1800071d9  jz      loc_180007ACD
0x1800071df  lea     rax, [rsp+610h+phkResult]
0x1800071e4  mov     qword ptr [rsp+610h+dwOptions], rax; phkResult
0x1800071e9  mov     r9d, 20019h; samDesired
0x1800071ef  xor     r8d, r8d; ulOptions
0x1800071f2  lea     rdx, sourceString; lpSubKey
0x1800071f9  mov     rcx, rdi; hKey
0x1800071fc  call    cs:__imp_RegOpenKeyExW
0x180007202  test    eax, eax
0x180007204  jnz     loc_180007A70
0x18000720a  mov     rbx, [rsp+610h+phkResult]
0x18000720f  mov     rcx, [rbp+510h+var_570]; hKey
0x180007213  test    rcx, rcx
0x180007216  jz      short loc_180007220
0x180007218  call    cs:__imp_RegCloseKey
0x18000721e  xchg    ax, ax
0x180007220  mov     edi, r12d
0x180007223  lea     r12, GUID_NULL
0x18000722a  test    rbx, rbx
0x18000722d  jz      loc_1800073B7
0x180007233  xor     esi, esi
0x180007235  mov     [rbp+510h+cchValueName], 100h
0x18000723c  mov     [rsp+610h+var_5D8], rsi; lpcbData
0x180007241  mov     [rsp+610h+lpSecurityAttributes], rsi; lpData
0x180007246  mov     qword ptr [rsp+610h+samDesired], rsi; lpType
0x18000724b  mov     qword ptr [rsp+610h+dwOptions], rsi; int
0x180007250  lea     r9, [rbp+510h+cchValueName]; lpcchValueName
0x180007254  lea     r8, [rbp+510h+ValueName]; lpValueName
0x18000725b  mov     edx, edi; dwIndex
0x18000725d  mov     rcx, rbx; hKey
0x180007260  call    cs:__imp_RegEnumValueW
0x180007266  mov     edx, 1FEh
0x18000726b  test    eax, eax
0x18000726d  cmovnz  rdx, rsi
0x180007271  mov     [rbp+rdx+510h+ValueName], si
0x180007279  jnz     loc_1800073A8
0x18000727f  inc     edi
0x180007281  xor     edx, edx; EndPtr
0x180007283  mov     r8d, 0Ah; Radix
0x180007289  lea     rcx, [rbp+510h+ValueName]; String
0x180007290  call    _o_wcstoul_0
0x180007295  test    eax, eax
0x180007297  jz      short loc_180007235
0x180007299  mov     [rbp+510h+cchValueName], 12h
0x1800072a0  mov     dword ptr [rsp+610h+var_5A8], esi
0x1800072a4  lea     rax, [rbp+510h+cchValueName]
0x1800072a8  mov     qword ptr [rsp+610h+samDesired], rax; lpcbData
0x1800072ad  lea     rax, [rbp+510h+Data]
0x1800072b4  mov     qword ptr [rsp+610h+dwOptions], rax; lpData
0x1800072b9  lea     r9, [rsp+610h+var_5A8]; lpType
0x1800072be  xor     r8d, r8d; lpReserved
0x1800072c1  lea     rdx, [rbp+510h+ValueName]; lpValueName
0x1800072c8  mov     rcx, rbx; hKey
0x1800072cb  call    cs:__imp_RegQueryValueExW
0x1800072d1  mov     edx, 10h
0x1800072d6  test    eax, eax
  ... truncated ...
```
