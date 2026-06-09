# COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)

- ea: `0x18003e3e8`
- end: `0x18003f441`
- name: `?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z`
- size: `4185`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, _DWORD *, __int64, __int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003cc10`
- `0x18003d2b8`
- `0x18003d7a8`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180008f5c`
- `0x180009438`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011b44`
- `0x180011bf0`
- `0x180011ef0`
- `0x18001a930`
- `0x18003bbdc`
- `0x18003e3e8`
- `0x180042a70`
- `0x180042bb4`
- `0x180042cf8`
- `0x1800431bc`
- `0x180043248`
- `0x180043a60`
- `0x180044b90`
- `0x180051d7c`
- `0x180051f78`
- `0x180052248`
- `0x1800526f4`
- `0x180052830`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e79c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e7a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e79c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003e7a6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18003e7b0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18003e7b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003e756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003e756`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ed58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ed58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ec85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f3dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ec85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f3dd`
- `RPCRT4!UuidFromStringW` at `0x18003e5c9`
- `RPCRT4!UuidFromStringW` at `0x18003e5c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e796`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003e796`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eb17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eb17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ec6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f32e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ec6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f32e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eaa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f365`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003eaa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f365`
- `OLEAUT32!__imp_SysStringLen` at `0x18003e6f7`
- `OLEAUT32!__imp_SysStringLen` at `0x18003e6f7`

## string_xrefs

- `0x18003efff`: `WillUpdateAutoCommit`
- `0x18003f014`: `WillUpdateAutoCommit`
- `0x18003eebd`: `UpdatePriority`
- `0x18003e69c`: `Install`
- `0x18003e693`: `Commit`
- `0x18003e5dd`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003e714`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003e978`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003ea0d`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003eadb`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003ec34`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003ed6a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003edfe`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003f247`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003f305`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18003e62a`: `Skipping UUP on Prem language specific update ID: %ws`
- `0x18003e6b2`: `Preparing to %ws update ID: %ws.%d`
- `0x18003e94a`: `ParseHandlerXml`
- `0x18003ef22`: `Update agent does not support priority set capability`
- `0x18003f11e`: `Install failed for update ID: %ws.%d Error Info type is %lu`
- `0x18003f089`: `Update agent does not support autocommit query capability`
- `0x18003f154`: `Need to install the baseline update`
- `0x18003f274`: `Invalid update operation`
- `0x18003e4fe`: `OptionalSessionFlags for Commit to be passed to Update Agent = %lu`
- `0x18003e4bf`: `OptionalSessionFlags for Install to be passed to Update Agent = %lu`
- `0x18003e744`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18003e73d`: `BreakOnHandlerInstallCall`

## pseudocode

```c
__int64 __fastcall COSInstaller::OrchestrateUpdate(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  char v10; // si
  OLECHAR *v12; // r13
  unsigned int v13; // ebx
  __int64 v14; // r12
  int v15; // edi
  int v16; // eax
  void *v17; // rbx
  _BYTE *v18; // rsi
  __int64 v19; // rdi
  __int64 v20; // r14
  unsigned __int16 *v21; // rcx
  unsigned int v22; // eax
  const struct std::nothrow_t *v23; // rdx
  int FilesPerPatchType; // r15d
  __int64 v25; // rax
  const wchar_t *v26; // r8
  OSDeploymentHelper *v27; // rax
  bool v28; // cl
  __int64 v29; // rcx
  int v30; // ebx
  __int64 v32; // r13
  struct tagDSUpdateMetadata *v33; // rbx
  wchar_t **v34; // r8
  int *v35; // r9
  __int64 v36; // rdx
  unsigned int v37; // eax
  char IsEnabled; // al
  unsigned int v39; // r9d
  __int64 v40; // rdx
  _BYTE *v41; // rax
  int v42; // eax
  int v43; // eax
  __int64 (__fastcall *v44)(__int64, LPVOID *); // rbx
  int v45; // eax
  unsigned __int64 v46; // r9
  __int64 v47; // rdx
  struct tagDSUpdateMetadata *v48; // rbx
  HRESULT updated; // eax
  __int64 v50; // rdx
  int v51; // eax
  int v52; // eax
  __int64 v53; // rbx
  int v54; // eax
  int v55; // eax
  int v56; // edx
  int v57; // eax
  __int64 (__fastcall *v58)(__int64, __int64 *, _DWORD *); // rbx
  int v59; // eax
  int v60; // eax
  __int64 v61; // rcx
  int v62; // eax
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvc; // [rsp+20h] [rbp-E0h]
  const wchar_t *v68; // [rsp+28h] [rbp-D8h]
  unsigned int *v69; // [rsp+30h] [rbp-D0h]
  unsigned int *v70; // [rsp+30h] [rbp-D0h]
  struct tagDSFile ***v71; // [rsp+38h] [rbp-C8h]
  int v72; // [rsp+38h] [rbp-C8h]
  __int64 v73; // [rsp+38h] [rbp-C8h]
  bool v74; // [rsp+50h] [rbp-B0h]
  char v75; // [rsp+51h] [rbp-AFh] BYREF
  struct tagDSFile **v76; // [rsp+54h] [rbp-ACh] BYREF
  int v77; // [rsp+5Ch] [rbp-A4h]
  struct tagDSUpdateMetadata *v78; // [rsp+60h] [rbp-A0h]
  int v79; // [rsp+68h] [rbp-98h]
  _QWORD *v80; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v81; // [rsp+78h] [rbp-88h] BYREF
  __int64 v82; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v83; // [rsp+88h] [rbp-78h] BYREF
  void *v84; // [rsp+90h] [rbp-70h] BYREF
  __int64 v85; // [rsp+98h] [rbp-68h]
  __int64 v86; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v87; // [rsp+A8h] [rbp-58h]
  OLECHAR *v88; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v89; // [rsp+B8h] [rbp-48h] BYREF
  OSDeploymentHelper *v90; // [rsp+C0h] [rbp-40h]
  _QWORD *v91; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v92[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v93; // [rsp+D8h] [rbp-28h]
  __int64 v94; // [rsp+E0h] [rbp-20h]
  GUID v95; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v96; // [rsp+F8h] [rbp-8h]
  __int64 v97; // [rsp+100h] [rbp+0h]
  __int64 v98; // [rsp+108h] [rbp+8h]
  __int64 v99; // [rsp+110h] [rbp+10h] BYREF
  GUID v100; // [rsp+118h] [rbp+18h]
  __int64 v101; // [rsp+128h] [rbp+28h]
  _QWORD v102[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v103[2]; // [rsp+150h] [rbp+50h] BYREF
  char v104; // [rsp+160h] [rbp+60h]
  IID rclsid; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v106[14]; // [rsp+180h] [rbp+80h] BYREF
  struct tagDSGlobalUpdateId *v107; // [rsp+1F0h] [rbp+F0h] BYREF
  int v108; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v109; // [rsp+200h] [rbp+100h] BYREF
  LPVOID v110; // [rsp+208h] [rbp+108h] BYREF
  LPVOID pv; // [rsp+210h] [rbp+110h] BYREF
  OSDeploymentHelper *v112; // [rsp+218h] [rbp+118h] BYREF
  HANDLE hObject; // [rsp+220h] [rbp+120h] BYREF
  __int128 v114; // [rsp+228h] [rbp+128h] BYREF
  UUID Uuid; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v116[112]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v10 = a3;
  v79 = a3;
  v85 = a1;
  LODWORD(v109) = a4;
  *(_QWORD *)&rclsid.Data1 = a5;
  v87 = a6;
  *(_QWORD *)&v114 = a7;
  v97 = a8;
  v98 = a9;
  v80 = a10;
  v78 = *(struct tagDSUpdateMetadata **)(a2 + 56);
  v107 = (struct tagDSGlobalUpdateId *)(a2 + 32);
  v12 = *(OLECHAR **)(a2 + 16);
  v88 = v12;
  v112 = *(OSDeploymentHelper **)(a2 + 24);
  v13 = *(_DWORD *)(a2 + 80);
  v14 = 0;
  v15 = 0;
  v77 = 0;
  if ( (a3 & 1) != 0 )
  {
    v15 = (v13 >> 6) & 4;
    v77 = v15;
    ppv = 0;
    WUTrace(0, 0, 4096, 4);
  }
  if ( (v10 & 2) != 0 )
  {
    v16 = v15 | 1;
    if ( (v13 & 0x200) == 0 )
      v16 = v15;
    v77 = v16;
    ppv = 0;
    WUTrace(0, 0, 4096, 4);
  }
  *(_QWORD *)&v95.Data1 = *(_QWORD *)(a2 + 256);
  v93 = *(_QWORD *)(a2 + 104);
  v94 = *(_QWORD *)(a2 + 248);
  v89 = (_BYTE *)(a2 + 112);
  v91 = a10;
  v83 = 0;
  v84 = 0;
  v76 = 0;
  v17 = 0;
  *(_QWORD *)v92 = 0;
  Uuid = 0;
  v18 = 0;
  v81 = 0;
  pv = 0;
  v19 = 0;
  v82 = 0;
  v20 = 0;
  v86 = 0;
  v110 = 0;
  v96 = 0;
  Trace::UpdateIdToString::UpdateIdToString(
    (Trace::UpdateIdToString *)v116,
    (struct tagDSUpdateMetadata *)((char *)v78 + 4));
  hObject = 0;
  v21 = *(unsigned __int16 **)a2;
  if ( *(_QWORD *)a2 )
  {
    if ( *v21 )
    {
      v22 = UuidFromStringW(v21, &Uuid);
      if ( v22 )
      {
        FilesPerPatchType = wil::details::in1diag3::Return_Win32(
                              retaddr,
                              (void *)0x37A,
                              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
                              (const char *)v22,
                              ppv);
        goto LABEL_158;
      }
    }
  }
  if ( IsUUPOnPremLangSpecificChildUpdate(v78, v107, &Uuid) )
  {
    Trace::UpdateIdToString::UpdateIdToString(
      (Trace::UpdateIdToString *)v106,
      (struct tagDSUpdateMetadata *)((char *)v78 + 4));
    WUTrace(0, 0, 4096, 4);
    FilesPerPatchType = 0;
    goto LABEL_158;
  }
  v25 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v106, (const struct _GUID *)((char *)v78 + 4));
  v26 = L"Unknown";
  switch ( v79 )
  {
    case 1:
      v26 = L"Install";
      break;
    case 2:
      v26 = L"Commit";
      break;
    case 4:
      v26 = L"Revert";
      break;
  }
  v71 = (struct tagDSFile ***)v25;
  v69 = (unsigned int *)v26;
  WUTrace(0, 0, 4096, 4);
  v27 = (OSDeploymentHelper *)v12;
  if ( v112 )
    v27 = v112;
  v90 = v27;
  if ( !SysStringLen(v12) )
  {
    FilesPerPatchType = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80070057LL,
      0);
    goto LABEL_158;
  }
  *v87 = 0;
  if ( (unsigned int)AreTestKeysAllowed(v28) )
  {
    v30 = RegQueryDwordValueWithDefaultAndRangeCheck(
            v29,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            L"BreakOnHandlerInstallCall",
            0,
            0,
            L"Preparing to %ws update ID: %ws.%d",
            v69);
    if ( v30 )
    {
      LODWORD(v71) = v30;
      GetCurrentProcessId();
      WUTrace(0, 0, 4096, 3);
      while ( !IsDebuggerPresent() )
      {
        if ( !v30-- )
          break;
        Sleep(0x3E8u);
      }
      if ( IsDebuggerPresent() )
        DebugBreak();
    }
  }
  v102[3] = 1;
  v102[0] = &v110;
  v102[1] = &pv;
  v32 = v85;
  v102[2] = v85;
  v33 = v78;
  FilesPerPatchType = OSDeploymentHelper::GetFilesPerPatchType(
                        (OSDeploymentHelper *)*((unsigned int *)v78 + 116),
                        *((_QWORD *)v78 + 59),
                        (struct tagDSFile *const)&v83,
                        (const struct tagDSFile **)((char *)&v76 + 4),
                        (unsigned int *)&v84,
                        &v76,
                        v92,
                        v71);
  if ( FilesPerPatchType < 0 )
  {
    ppvb = FilesPerPatchType;
    WUTrace(0, 0, 4096, 2);
    v36 = 954;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)FilesPerPatchType,
      ppvb);
    goto LABEL_157;
  }
  v74 = v83 != 0;
  if ( !v83
    || (v108 = 0,
        FilesPerPatchType = OSDeploymentHelper::EvaluateFileInSandbox(v90, v83, (const struct tagDSFile *)&v108, v35),
        FilesPerPatchType >= 0)
    && (FilesPerPatchType = v108, v108 >= 0) )
  {
    if ( !v112 )
    {
      v37 = 0;
      LODWORD(v76) = 0;
      if ( HIDWORD(v76) )
      {
        while ( 1 )
        {
          v108 = 0;
          FilesPerPatchType = OSDeploymentHelper::EvaluateFileInSandbox(
                                v90,
                                *((const wchar_t **)v84 + v37),
                                (const struct tagDSFile *)&v108,
                                v35);
          if ( FilesPerPatchType < 0 )
          {
            ppvb = FilesPerPatchType;
            WUTrace(0, 0, 4096, 2);
            v36 = 991;
            goto LABEL_49;
          }
          if ( v108 < 0 )
            break;
          v37 = (_DWORD)v76 + 1;
          LODWORD(v76) = v37;
          if ( v37 >= HIDWORD(v76) )
          {
            v32 = v85;
            v33 = v78;
            goto LABEL_44;
          }
        }
        ppvb = v108;
        WUTrace(0, 0, 4096, 2);
        FilesPerPatchType = v108;
        if ( v108 >= 0 )
          goto LABEL_157;
        v36 = 1001;
        goto LABEL_49;
      }
    }
LABEL_44:
    FilesPerPatchType = OSDeploymentHelper::ParseHandlerXml(
                          (struct tagDSUpdateMetadata *)((char *)v33 + 544),
                          (const struct tagDSDataBlob *)&v81,
                          v34);
    if ( FilesPerPatchType < 0 )
    {
      WUTrace(0, 0, 4096, 2);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F3,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)FilesPerPatchType,
        FilesPerPatchType);
LABEL_52:
      v18 = v81;
      goto LABEL_157;
    }
    if ( *(_BYTE *)(v32 + 56) )
    {
      FilesPerPatchType = -2145116152;
      goto LABEL_52;
    }
    v99 = 0;
    v100 = GUID_NULL;
    v101 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl);
    v18 = v81;
    if ( IsEnabled )
    {
      FilesPerPatchType = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(
                            (struct _GUID *)&v99,
                            (GUID *)((char *)v33 + 4),
                            (void **)0x1B7740);
      if ( FilesPerPatchType < 0 )
      {
        v40 = 1020;
LABEL_60:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
          (const char *)(unsigned int)FilesPerPatchType,
          ppva);
LABEL_156:
        OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v99);
        goto LABEL_157;
      }
    }
    else
    {
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      FilesPerPatchType = OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(
                            (GUID *)((char *)v33 + 4),
                            (const struct _GUID *)&hObject,
                            (void **)0x1B7740,
                            v39);
      if ( FilesPerPatchType < 0 )
      {
        v40 = 1027;
        goto LABEL_60;
      }
    }
    v103[0] = &hObject;
    v103[1] = v107;
    v104 = 1;
    v85 = v32 + 64;
    if ( v32 != -64 )
      EnterCriticalSection((LPCRITICAL_SECTION)(v32 + 72));
    if ( *(_QWORD *)(v32 + 112) )
    {
      FilesPerPatchType = -2145124343;
LABEL_153:
      if ( v32 != -64 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 72));
      goto LABEL_155;
    }
    memset(v106, 0, 0x68u);
    v106[1] = v116;
    v106[2] = v93;
    v106[3] = v94;
    v106[0] = *(_QWORD *)&v95.Data1;
    v106[6] = v112;
    LODWORD(v106[8]) = v77;
    if ( v89 )
    {
      v41 = (_BYTE *)v106[4];
      if ( *v89 )
        v41 = v89;
      v106[4] = v41;
    }
    if ( !v80 && v74 )
      v91 = (_QWORD *)*((_QWORD *)v83 + 9);
    v80 = v106;
    v95 = Buf1;
    v42 = 0;
    if ( !v112 )
      v42 = HIDWORD(v76);
    LODWORD(v76) = v42;
    v89 = v18;
    v43 = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,IDeploymentSession,wchar_t * const &,wchar_t const * &,wchar_t *,unsigned long,WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>> &,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
            (int)v32 + 112,
            (unsigned int)&v88,
            (unsigned int)&v91,
            (unsigned int)&v89,
            (__int64)&v76,
            (__int64)&v84,
            (__int64)&v95,
            v72,
            (__int64)&v80);
    FilesPerPatchType = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)v43,
        (int)ppvc);
      goto LABEL_153;
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v32 + 112) + 8LL))(*(_QWORD *)(v32 + 112));
    v14 = *(_QWORD *)(v32 + 112);
    v96 = v14;
    if ( v32 != -64 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 72));
    v44 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 24LL);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v45 = v44(v14, &pv);
    FilesPerPatchType = v45;
    if ( v45 < 0 )
    {
      v46 = (unsigned int)v45;
      v47 = 1106;
LABEL_150:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)v46,
        (int)ppvc);
      goto LABEL_155;
    }
    v88 = (OLECHAR *)(v32 + 144);
    v80 = (_QWORD *)(v32 + 120);
    v48 = v78;
    updated = Microsoft::WRL::Details::MakeAndInitialize<COSInstallDeploymentProgress,COSInstallDeploymentProgress,tagDSGlobalUpdateId const &,tagDSGlobalUpdateId const &,CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>> *,CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>> *,IUpdateDeploymentCallback * &>(
                (unsigned int)&v82,
                (int)v78 + 4,
                (_DWORD)v107,
                (unsigned int)&v80,
                (__int64)&v88,
                (__int64)&rclsid);
    FilesPerPatchType = updated;
    if ( updated < 0 )
    {
      v50 = 1112;
LABEL_87:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)updated,
        (int)ppvc);
      v19 = v82;
LABEL_155:
      wil::details::lambda_call__lambda_8442dda86b2b3a16dab6fbc6b475eee9___::_lambda_call__lambda_8442dda86b2b3a16dab6fbc6b475eee9___(v103);
      goto LABEL_156;
    }
    if ( v110 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v110 + 16LL))(v110);
      v110 = 0;
    }
    rclsid = Buf1;
    updated = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_c8264914_c0d2_48da_a5cd_f47d74fda7f6, &v110);
    FilesPerPatchType = updated;
    if ( updated < 0 )
    {
      v50 = 1117;
      goto LABEL_87;
    }
    v19 = v82;
    v51 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64))(*(_QWORD *)v110 + 32LL))(v110, pv, v82);
    FilesPerPatchType = v51;
    if ( v51 < 0 )
    {
      v46 = (unsigned int)v51;
      v47 = 1119;
      goto LABEL_150;
    }
    v75 = 0;
    v52 = Microsoft::WRL::Details::MakeAndInitialize<CUHOSDeploymentInformation,CUHOSDeploymentInformation,bool,unsigned long &,unsigned long const &,tagDSFile * const &>(
            (unsigned int)&v86,
            (unsigned int)&v75,
            (unsigned int)&v109,
            (int)v48 + 464,
            (__int64)v48 + 472);
    FilesPerPatchType = v52;
    v53 = 0;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x466,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)(unsigned int)v52,
        (int)ppvc);
      v20 = v86;
      goto LABEL_155;
    }
    v20 = v86;
    v54 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64))(*(_QWORD *)v110 + 24LL))(v110, pv, v86);
    FilesPerPatchType = v54;
    if ( v54 < 0 )
    {
      v46 = (unsigned int)v54;
      v47 = 1128;
      goto LABEL_150;
    }
    if ( v79 != 1 )
    {
      if ( v79 == 2 )
      {
        FilesPerPatchType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 48LL))(v14);
      }
      else if ( v79 == 4 )
      {
        v107 = 0;
        FilesPerPatchType = (**(__int64 (__fastcall ***)(__int64, GUID *, struct tagDSGlobalUpdateId **))v14)(
                              v14,
                              &GUID_347c6b31_7d10_4ada_9ede_ae9288f35f47,
                              &v107);
        if ( FilesPerPatchType >= 0 )
        {
          LODWORD(ppvc) = 0;
          WUTrace(0, 0, 4096, 4);
          FilesPerPatchType = (*(__int64 (__fastcall **)(struct tagDSGlobalUpdateId *, _DWORD *))(*(_QWORD *)v107 + 104LL))(
                                v107,
                                v87);
        }
        v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
        if ( v62 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4FC,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)v62,
            (int)ppvc);
        if ( v107 )
          (*(void (__fastcall **)(struct tagDSGlobalUpdateId *))(*(_QWORD *)v107 + 16LL))(v107);
      }
      else
      {
        LODWORD(ppvc) = 0;
        WUTrace(0, 0, 4096, 2);
        FilesPerPatchType = -2145112065;
      }
      goto LABEL_139;
    }
    v109 = 0;
    v107 = 0;
    v55 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct tagDSGlobalUpdateId **))v14)(
            v14,
            &GUID_57816c47_d685_423a_89c6_feefbd90ed47,
            &v107);
    if ( v55 >= 0 && v107 )
    {
      v56 = *(_DWORD *)(v32 + 168);
      if ( v56 )
      {
        if ( v56 == 1 )
          v53 = 2;
      }
      else
      {
        v53 = 1;
      }
      v57 = (*(__int64 (__fastcall **)(struct tagDSGlobalUpdateId *, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v107 + 168LL))(
              v107,
              0,
              L"UpdatePriority",
              v53);
      v73 = v53;
      v70 = (unsigned int *)L"UpdatePriority";
      if ( v57 < 0 )
      {
        v68 = L"Failed to set Attribute [%ws] value = %lld";
        LODWORD(ppvc) = v57;
      }
      else
      {
        v68 = L"Set attribute [%ws] value = %lld";
        ppvc = 0;
      }
      WUTrace(0, 0, 4096, 4);
    }
    else
    {
      v68 = L"Update agent does not support priority set capability";
      LODWORD(ppvc) = v55;
      WUTrace(0, 0, 4096, 3);
    }
    if ( v107 )
      (*(void (__fastcall **)(struct tagDSGlobalUpdateId *))(*(_QWORD *)v107 + 16LL))(v107);
    v58 = *(__int64 (__fastcall **)(__int64, __int64 *, _DWORD *))(*(_QWORD *)v14 + 40LL);
    if ( v109 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      v109 = 0;
    }
    FilesPerPatchType = v58(v14, &v109, v87);
    if ( FilesPerPatchType < 0 )
    {
      v114 = 0;
      v61 = v109;
      if ( v109 )
      {
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v109 + 24LL))(v109, &v114);
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v106, (const struct _GUID *)((char *)v78 + 4));
        LODWORD(ppvc) = FilesPerPatchType;
        WUTrace(0, 0, 4096, 2);
        v61 = v109;
      }
      if ( FilesPerPatchType != -2146498504 )
        goto LABEL_125;
      LODWORD(ppvc) = -2146498504;
      WUTrace(0, 0, 4096, 2);
      FilesPerPatchType = -2145116122;
    }
    else
    {
      v112 = 0;
      v59 = (**(__int64 (__fastcall ***)(__int64, GUID *, OSDeploymentHelper **))v14)(
              v14,
              &GUID_57816c47_d685_423a_89c6_feefbd90ed47,
              &v112);
      if ( v59 >= 0 && v112 )
      {
        v107 = 0;
        v60 = (*(__int64 (__fastcall **)(OSDeploymentHelper *, _QWORD, const wchar_t *, struct tagDSGlobalUpdateId **, LPVOID *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v112 + 152LL))(
                v112,
                0,
                L"WillUpdateAutoCommit",
                &v107,
                ppvc,
                v68,
                v70,
                v73);
        if ( v60 < 0 )
        {
          LODWORD(ppvc) = v60;
          WUTrace(0, 0, 4096, 4);
        }
        else
        {
          LODWORD(ppvc) = 0;
          WUTrace(0, 0, 4096, 4);
          *(_DWORD *)v114 = 2 - (v107 != 0);
        }
      }
      else
      {
        LODWORD(ppvc) = v59;
        WUTrace(0, 0, 4096, 3);
      }
      if ( v112 )
        (*(void (__fastcall **)(OSDeploymentHelper *))(*(_QWORD *)v112 + 16LL))(v112);
    }
    v61 = v109;
LABEL_125:
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
LABEL_139:
    if ( v74 && v97 )
      DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)v83 + 9), v97);
    if ( v98 )
      DuplicateOptionalString<wchar_t *,wchar_t *>(v18, v98);
    if ( FilesPerPatchType >= 0 )
    {
      FilesPerPatchType = 0;
      goto LABEL_155;
    }
    if ( FilesPerPatchType == -2145116147
      || FilesPerPatchType == -2147024894
      || FilesPerPatchType == -1047526943
      || (unsigned int)(FilesPerPatchType + 1047526898) <= 1 )
    {
      goto LABEL_155;
    }
    v46 = (unsigned int)FilesPerPatchType;
    v47 = 1307;
    goto LABEL_150;
  }
  ppvb = FilesPerPatchType;
  WUTrace(0, 0, 4096, 2);
  if ( FilesPerPatchType < 0 )
  {
    v36 = 972;
    goto LABEL_49;
  }
LABEL_157:
  wil::details::lambda_call__lambda_6b188daa3d3c97e193f917f682fa79c8___::_lambda_call__lambda_6b188daa3d3c97e193f917f682fa79c8___(v102);
  v17 = *(void **)v92;
LABEL_158:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v110 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v110 + 16LL))(v110);
    v110 = 0;
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v18 )
    SusFree(v18);
  if ( v17 )
    operator delete(v17, v23);
  if ( v84 )
    operator delete(v84, v23);
  return (unsigned int)FilesPerPatchType;
}

```

## disassembly

```asm
0x18003e3e8  mov     [rsp-8+arg_10], rbx
0x18003e3ed  push    rbp
0x18003e3ee  push    rsi
0x18003e3ef  push    rdi
0x18003e3f0  push    r12
0x18003e3f2  push    r13
0x18003e3f4  push    r14
0x18003e3f6  push    r15
0x18003e3f8  lea     rbp, [rsp-1D0h]
0x18003e400  sub     rsp, 2D0h
0x18003e407  mov     rax, cs:__security_cookie
0x18003e40e  xor     rax, rsp
0x18003e411  mov     [rbp+200h+var_40], rax
0x18003e418  mov     esi, r8d
0x18003e41b  mov     [rsp+300h+var_298], r8d
0x18003e420  mov     r15, rdx
0x18003e423  mov     [rbp+200h+var_268], rcx
0x18003e427  mov     dword ptr [rbp+200h+var_100], r9d
0x18003e42e  mov     rax, [rbp+200h+arg_20]
0x18003e435  mov     qword ptr [rbp+200h+rclsid.Data1], rax
0x18003e439  mov     rax, [rbp+200h+arg_28]
0x18003e440  mov     [rbp+200h+var_258], rax
0x18003e444  mov     rax, [rbp+200h+arg_30]
0x18003e44b  mov     qword ptr [rbp+200h+var_D8], rax
0x18003e452  mov     rcx, [rbp+200h+arg_38]
0x18003e459  mov     [rbp+200h+var_200], rcx
0x18003e45d  mov     rax, [rbp+200h+arg_40]
0x18003e464  mov     [rbp+200h+var_1F8], rax
0x18003e468  mov     r14, [rbp+200h+arg_48]
0x18003e46f  mov     [rsp+300h+var_290], r14
0x18003e474  mov     rax, [rdx+38h]
0x18003e478  mov     [rsp+300h+var_2A0], rax
0x18003e47d  lea     rax, [rdx+20h]
0x18003e481  mov     [rbp+200h+var_110], rax
0x18003e488  mov     r13, [rdx+10h]
0x18003e48c  mov     [rbp+200h+var_250], r13
0x18003e490  mov     rax, [rdx+18h]
0x18003e494  mov     [rbp+200h+var_E8], rax
0x18003e49b  mov     ebx, [rdx+50h]
0x18003e49e  xor     r12d, r12d
0x18003e4a1  mov     edi, r12d
0x18003e4a4  mov     [rsp+300h+var_2A4], r12d
0x18003e4a9  test    r8b, 1
0x18003e4ad  jz      short loc_18003E4E4
0x18003e4af  mov     edi, ebx
0x18003e4b1  shr     edi, 6
0x18003e4b4  and     edi, 4
0x18003e4b7  mov     [rsp+300h+var_2A4], edi
0x18003e4bb  mov     dword ptr [rsp+300h+var_2D0], edi
0x18003e4bf  lea     rax, aOptionalsessio_0; "OptionalSessionFlags for Install to be "...
0x18003e4c6  mov     [rsp+300h+var_2D8], rax
0x18003e4cb  mov     [rsp+300h+ppv], r12
0x18003e4d0  xor     edx, edx
0x18003e4d2  xor     ecx, ecx
0x18003e4d4  lea     r9d, [r12+4]
0x18003e4d9  mov     r8d, 1000h
0x18003e4df  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e4e4  test    sil, 2
0x18003e4e8  jz      short loc_18003E522
0x18003e4ea  mov     eax, edi
0x18003e4ec  or      eax, 1
0x18003e4ef  bt      ebx, 9
0x18003e4f3  cmovnb  eax, edi
0x18003e4f6  mov     [rsp+300h+var_2A4], eax
0x18003e4fa  mov     dword ptr [rsp+300h+var_2D0], eax
0x18003e4fe  lea     rax, aOptionalsessio; "OptionalSessionFlags for Commit to be p"...
0x18003e505  mov     [rsp+300h+var_2D8], rax
0x18003e50a  mov     [rsp+300h+ppv], r12; unsigned int
0x18003e50f  xor     edx, edx
0x18003e511  xor     ecx, ecx
0x18003e513  lea     r9d, [rdx+4]
0x18003e517  mov     r8d, 1000h
0x18003e51d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e522  mov     rax, [r15+100h]
0x18003e529  mov     qword ptr [rbp+200h+var_218], rax
0x18003e52d  mov     rax, [r15+68h]
0x18003e531  mov     [rbp+200h+var_228], rax
0x18003e535  mov     rax, [r15+0F8h]
0x18003e53c  mov     [rbp+200h+var_220], rax
0x18003e540  lea     rax, [r15+70h]
0x18003e544  mov     [rbp+200h+var_248], rax
0x18003e548  mov     [rbp+200h+var_238], r14
0x18003e54c  mov     [rbp+200h+var_278], r12
0x18003e550  mov     dword ptr [rsp+300h+var_2AC+4], r12d
0x18003e555  mov     [rbp+200h+var_270], r12
0x18003e559  mov     dword ptr [rsp+300h+var_2AC], r12d
0x18003e55e  mov     rbx, r12
0x18003e561  mov     qword ptr [rbp+200h+var_230], rbx
0x18003e565  xorps   xmm0, xmm0
0x18003e568  movups  xmmword ptr [rbp+200h+Uuid.Data1], xmm0
0x18003e56f  mov     rsi, r12
0x18003e572  mov     [rsp+300h+var_288], r12
0x18003e577  mov     [rbp+200h+pv], r12
0x18003e57e  mov     rdi, r12
0x18003e581  mov     [rbp+200h+var_280], r12
0x18003e585  mov     r14, r12
0x18003e588  mov     [rbp+200h+var_260], r12
0x18003e58c  mov     [rbp+200h+var_F8], r12
0x18003e593  mov     [rbp+200h+var_208], r12
0x18003e597  mov     rdx, [rsp+300h+var_2A0]
0x18003e59c  add     rdx, 4; struct tagDSGlobalUpdateId *
0x18003e5a0  lea     rcx, [rbp+200h+var_B0]; this
0x18003e5a7  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18003e5ac  xor     eax, eax
0x18003e5ae  mov     [rbp+200h+hObject], rax
0x18003e5b5  mov     rcx, [r15]; StringUuid
0x18003e5b8  test    rcx, rcx
0x18003e5bb  jz      short loc_18003E5F6
0x18003e5bd  cmp     [rcx], ax
0x18003e5c0  jz      short loc_18003E5F6
0x18003e5c2  lea     rdx, [rbp+200h+Uuid]; Uuid
0x18003e5c9  call    cs:__imp_UuidFromStringW
0x18003e5cf  test    eax, eax
0x18003e5d1  jz      short loc_18003E5F6
0x18003e5d3  mov     rcx, [rbp+208h]; this
0x18003e5da  mov     r9d, eax; char *
0x18003e5dd  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003e5e4  mov     edx, 37Ah; void *
0x18003e5e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e5ee  mov     r15d, eax
0x18003e5f1  jmp     loc_18003F356
0x18003e5f6  lea     r8, [rbp+200h+Uuid]; struct _GUID *
0x18003e5fd  mov     rdx, [rbp+200h+var_110]; struct tagDSGlobalUpdateId *
0x18003e604  mov     r15, [rsp+300h+var_2A0]
0x18003e609  mov     rcx, r15; struct tagDSUpdateMetadata *
0x18003e60c  call    ?IsUUPOnPremLangSpecificChildUpdate@@YA_NAEBUtagDSUpdateMetadata@@AEBUtagDSGlobalUpdateId@@AEBU_GUID@@@Z; IsUUPOnPremLangSpecificChildUpdate(tagDSUpdateMetadata const &,tagDSGlobalUpdateId const &,_GUID const &)
0x18003e611  test    al, al
0x18003e613  jz      short loc_18003E659
0x18003e615  lea     rdx, [r15+4]; struct tagDSGlobalUpdateId *
0x18003e619  lea     rcx, [rbp+200h+var_180]; this
0x18003e620  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18003e625  mov     [rsp+300h+var_2D0], rax
0x18003e62a  lea     rax, aSkippingUupOnP; "Skipping UUP on Prem language specific "...
0x18003e631  mov     [rsp+300h+var_2D8], rax
0x18003e636  xor     r13d, r13d
0x18003e639  mov     [rsp+300h+ppv], r13
0x18003e63e  xor     edx, edx
0x18003e640  xor     ecx, ecx
0x18003e642  lea     r9d, [r13+4]
0x18003e646  mov     r8d, 1000h
0x18003e64c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e651  mov     r15d, r13d
0x18003e654  jmp     loc_18003F359
0x18003e659  lea     rax, [r15+4]
0x18003e65d  mov     r15d, [rax+10h]
0x18003e661  mov     rdx, rax; struct _GUID *
0x18003e664  lea     rcx, [rbp+200h+var_180]; this
0x18003e66b  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003e670  lea     r8, aUnknown_0; "Unknown"
0x18003e677  mov     edx, [rsp+300h+var_298]
0x18003e67b  sub     edx, 1
0x18003e67e  jz      short loc_18003E69C
0x18003e680  sub     edx, 1
0x18003e683  jz      short loc_18003E693
0x18003e685  cmp     edx, 2
0x18003e688  jnz     short loc_18003E6A3
0x18003e68a  lea     r8, aRevert_0; "Revert"
0x18003e691  jmp     short loc_18003E6A3
0x18003e693  lea     r8, aCommit; "Commit"
0x18003e69a  jmp     short loc_18003E6A3
0x18003e69c  lea     r8, aInstall; "Install"
0x18003e6a3  mov     dword ptr [rsp+300h+var_2C0], r15d
0x18003e6a8  mov     [rsp+300h+var_2C8], rax
0x18003e6ad  mov     [rsp+300h+var_2D0], r8
0x18003e6b2  lea     rax, aPreparingToWsU; "Preparing to %ws update ID: %ws.%d"
0x18003e6b9  mov     [rsp+300h+var_2D8], rax
0x18003e6be  mov     [rsp+300h+ppv], 0; int
0x18003e6c7  mov     r9d, 4
0x18003e6cd  mov     r15d, 1000h
0x18003e6d3  mov     r8d, r15d
0x18003e6d6  xor     edx, edx
0x18003e6d8  xor     ecx, ecx
0x18003e6da  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e6df  mov     rax, r13
0x18003e6e2  mov     rcx, [rbp+200h+var_E8]
0x18003e6e9  test    rcx, rcx
0x18003e6ec  cmovnz  rax, rcx
0x18003e6f0  mov     [rbp+200h+var_240], rax
0x18003e6f4  mov     rcx, r13; pbstr
0x18003e6f7  call    cs:__imp_SysStringLen
0x18003e6fd  xor     r13d, r13d
0x18003e700  test    eax, eax
0x18003e702  jnz     short loc_18003E72A
0x18003e704  mov     rcx, [rbp+208h]; this
0x18003e70b  mov     r15d, 80070057h
0x18003e711  mov     r9d, r15d; char *
0x18003e714  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003e71b  mov     edx, 394h; void *
0x18003e720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e725  jmp     loc_18003F359
0x18003e72a  mov     rax, [rbp+200h+var_258]
0x18003e72e  mov     [rax], r13d
0x18003e731  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18003e736  test    eax, eax
0x18003e738  jz      short loc_18003E7B6
0x18003e73a  xor     r9d, r9d
0x18003e73d  lea     r8, aBreakonhandler; "BreakOnHandlerInstallCall"
0x18003e744  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e74b  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x18003e750  mov     ebx, eax
0x18003e752  test    eax, eax
0x18003e754  jz      short loc_18003E7B6
0x18003e756  call    cs:__imp_GetCurrentProcessId
0x18003e75c  mov     dword ptr [rsp+300h+var_2C8], ebx
0x18003e760  mov     dword ptr [rsp+300h+var_2D0], eax
0x18003e764  lea     rax, aPidLuWaitingLu; "PID:%lu - waiting %lu seconds for debug"...
0x18003e76b  mov     [rsp+300h+var_2D8], rax
0x18003e770  mov     [rsp+300h+ppv], r13
0x18003e775  mov     r9d, 3
0x18003e77b  mov     r8d, r15d
0x18003e77e  xor     edx, edx
0x18003e780  xor     ecx, ecx
0x18003e782  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e787  jmp     short loc_18003E79C
0x18003e789  mov     eax, ebx
0x18003e78b  dec     ebx
0x18003e78d  test    eax, eax
0x18003e78f  jz      short loc_18003E7A6
0x18003e791  mov     ecx, 3E8h; dwMilliseconds
0x18003e796  call    cs:__imp_Sleep
0x18003e79c  call    cs:__imp_IsDebuggerPresent
0x18003e7a2  test    eax, eax
0x18003e7a4  jz      short loc_18003E789
0x18003e7a6  call    cs:__imp_IsDebuggerPresent
0x18003e7ac  test    eax, eax
0x18003e7ae  jz      short loc_18003E7B6
0x18003e7b0  call    cs:__imp_DebugBreak
0x18003e7b6  xorps   xmm0, xmm0
0x18003e7b9  movups  [rbp+200h+var_1D0], xmm0
0x18003e7bd  movups  [rbp+200h+var_1C0], xmm0
0x18003e7c1  lea     rax, [rbp+200h+var_F8]
0x18003e7c8  mov     qword ptr [rbp+200h+var_1D0], rax
0x18003e7cc  lea     rax, [rbp+200h+pv]
0x18003e7d3  mov     qword ptr [rbp+200h+var_1D0+8], rax
0x18003e7d7  mov     r13, [rbp+200h+var_268]
0x18003e7db  mov     qword ptr [rbp+200h+var_1C0], r13
0x18003e7df  mov     byte ptr [rbp+200h+var_1C0+8], 1
0x18003e7e3  lea     rax, [rbp+200h+var_230]
0x18003e7e7  mov     [rsp+300h+var_2D0], rax; unsigned int *
0x18003e7ec  lea     rax, [rsp+300h+var_2AC]
0x18003e7f1  mov     [rsp+300h+var_2D8], rax; struct tagDSFile ***
0x18003e7f6  lea     rax, [rbp+200h+var_270]
0x18003e7fa  mov     [rsp+300h+ppv], rax; int
0x18003e7ff  lea     r9, [rsp+300h+var_2AC+4]; struct tagDSFile **
0x18003e804  lea     r8, [rbp+200h+var_278]; struct tagDSFile *
0x18003e808  mov     rbx, [rsp+300h+var_2A0]
0x18003e80d  mov     rdx, [rbx+1D8h]; unsigned int
0x18003e814  mov     ecx, [rbx+1D0h]; this
0x18003e81a  call    ?GetFilesPerPatchType@OSDeploymentHelper@@YAJKQEAUtagDSFile@@PEAPEBU2@PEAKPEAPEAPEAU2@23@Z; OSDeploymentHelper::GetFilesPerPatchType(ulong,tagDSFile * const,tagDSFile const * *,ulong *,tagDSFile * * *,ulong *,tagDSFile * * *)
0x18003e81f  mov     r15d, eax
0x18003e822  xor     ecx, ecx
0x18003e824  test    eax, eax
0x18003e826  jns     short loc_18003E854
0x18003e828  lea     rax, aFailedToDeterm; "Failed to determine the servicing stack"...
0x18003e82f  mov     [rsp+300h+var_2D8], rax
0x18003e834  mov     dword ptr [rsp+300h+ppv], r15d
0x18003e839  xor     edx, edx
0x18003e83b  lea     r9d, [rcx+2]
0x18003e83f  mov     r8d, 1000h
0x18003e845  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e84a  mov     edx, 3BAh
0x18003e84f  jmp     loc_18003EA0D
0x18003e854  mov     rax, [rbp+200h+var_278]
0x18003e858  test    rax, rax
0x18003e85b  setnz   [rsp+300h+var_2B0]
0x18003e860  test    rax, rax
0x18003e863  jz      short loc_18003E8C8
0x18003e865  mov     [rbp+200h+var_108], ecx
0x18003e86b  lea     r8, [rbp+200h+var_108]; struct tagDSFile *
0x18003e872  mov     rdx, rax; wchar_t *
0x18003e875  mov     rcx, [rbp+200h+var_240]; this
0x18003e879  call    ?EvaluateFileInSandbox@OSDeploymentHelper@@YAJPEB_WAEBUtagDSFile@@PEAJ@Z; OSDeploymentHelper::EvaluateFileInSandbox(wchar_t const *,tagDSFile const &,long *)
0x18003e87e  mov     r15d, eax
0x18003e881  xor     ecx, ecx
0x18003e883  test    eax, eax
0x18003e885  js      short loc_18003E893
0x18003e887  mov     r15d, [rbp+200h+var_108]
0x18003e88e  test    r15d, r15d
0x18003e891  jns     short loc_18003E8C8
0x18003e893  lea     rax, aServicingStack; "Servicing stack cab validation failed"
0x18003e89a  mov     [rsp+300h+var_2D8], rax
0x18003e89f  mov     dword ptr [rsp+300h+ppv], r15d
0x18003e8a4  xor     edx, edx
0x18003e8a6  lea     r9d, [rdx+2]
0x18003e8aa  mov     r8d, 1000h
0x18003e8b0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003e8b5  test    r15d, r15d
0x18003e8b8  jns     loc_18003F349
0x18003e8be  mov     edx, 3CCh
0x18003e8c3  jmp     loc_18003EA0D
0x18003e8c8  cmp     [rbp+200h+var_E8], rcx
0x18003e8cf  jnz     short loc_18003E92E
0x18003e8d1  mov     eax, ecx
0x18003e8d3  mov     dword ptr [rsp+300h+var_2AC], ecx
0x18003e8d7  cmp     dword ptr [rsp+300h+var_2AC+4], ecx
0x18003e8db  jbe     short loc_18003E92E
0x18003e8dd  mov     [rbp+200h+var_108], ecx
0x18003e8e3  mov     ebx, eax
0x18003e8e5  mov     r13, [rbp+200h+var_270]
0x18003e8e9  lea     r8, [rbp+200h+var_108]; struct tagDSFile *
  ... truncated ...
```
