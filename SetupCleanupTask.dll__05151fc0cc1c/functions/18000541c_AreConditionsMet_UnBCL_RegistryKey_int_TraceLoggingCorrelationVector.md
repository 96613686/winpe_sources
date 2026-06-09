# AreConditionsMet(UnBCL::RegistryKey *,int &,TraceLoggingCorrelationVector *)

- ea: `0x18000541c`
- end: `0x180005e8f`
- name: `?AreConditionsMet@@YAHPEAVRegistryKey@UnBCL@@AEAHPEAVTraceLoggingCorrelationVector@@@Z`
- size: `2675`
- prototype: `__int64 __fastcall(struct UnBCL::RegistryKey *, int *, struct TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006838`

## callees

- `0x18000113c`
- `0x180004704`
- `0x1800047a8`
- `0x180004b70`
- `0x180004c84`
- `0x18000541c`
- `0x18000638c`
- `0x180006744`
- `0x18000ae40`
- `0x18000c700`
- `0x180032310`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000555a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000589e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000555a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000589e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005afb`
- `unbcl!?get_Days@TimeSpan@UnBCL@@QEBAHXZ` at `0x1800058b7`
- `unbcl!?get_Days@TimeSpan@UnBCL@@QEBAHXZ` at `0x18000591a`
- `unbcl!?get_Days@TimeSpan@UnBCL@@QEBAHXZ` at `0x1800058b7`
- `unbcl!?get_Days@TimeSpan@UnBCL@@QEBAHXZ` at `0x18000591a`
- `unbcl!?GetNow@DateTime@UnBCL@@SA?AV12@H@Z` at `0x18000586f`
- `unbcl!?GetNow@DateTime@UnBCL@@SA?AV12@H@Z` at `0x18000586f`
- `unbcl!?Subtract@DateTime@UnBCL@@QEBA?AVTimeSpan@2@AEBV12@@Z` at `0x180005889`
- `unbcl!?Subtract@DateTime@UnBCL@@QEBA?AVTimeSpan@2@AEBV12@@Z` at `0x180005889`
- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x180005693`
- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x180005693`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x1800055fd`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180005a39`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x1800055fd`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180005a39`
- `unbcl!??0DateTime@UnBCL@@QEAA@HHHHHHH@Z` at `0x18000583c`
- `unbcl!??0DateTime@UnBCL@@QEAA@HHHHHHH@Z` at `0x18000583c`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x1800057d1`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x1800057d1`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800059b4`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180005a0f`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180005b60`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800059b4`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180005a0f`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180005b60`
- `unbcl!?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z` at `0x1800057a3`
- `unbcl!?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z` at `0x1800057a3`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x18000577b`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x1800057b4`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x18000577b`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x1800057b4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800057f2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800057f2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180005648`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800056a5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800057c3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180005a58`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180005648`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800056a5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800057c3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180005a58`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800055e8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180005686`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180005791`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180005a24`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800055e8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180005686`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180005791`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180005a24`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180005898`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180005997`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180005898`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180005997`
- `KERNEL32!OOBEComplete` at `0x1800054b0`
- `KERNEL32!OOBEComplete` at `0x1800054b0`
- `WDSCORE!CurrentIP` at `0x1800054c6`
- `WDSCORE!CurrentIP` at `0x180005562`
- `WDSCORE!CurrentIP` at `0x1800056f6`
- `WDSCORE!CurrentIP` at `0x1800058a6`
- `WDSCORE!CurrentIP` at `0x18000592e`
- `WDSCORE!CurrentIP` at `0x180005a74`
- `WDSCORE!CurrentIP` at `0x180005b03`
- `WDSCORE!CurrentIP` at `0x1800054c6`
- `WDSCORE!CurrentIP` at `0x180005562`
- `WDSCORE!CurrentIP` at `0x1800056f6`
- `WDSCORE!CurrentIP` at `0x1800058a6`
- `WDSCORE!CurrentIP` at `0x18000592e`
- `WDSCORE!CurrentIP` at `0x180005a74`
- `WDSCORE!CurrentIP` at `0x180005b03`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000552b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800055b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000575f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000590c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005981`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005ac9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005b51`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000552b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800055b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000575f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000590c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005981`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005ac9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005b51`

## string_xrefs

- `0x180005508`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x180005548`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000573c`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x1800058e9`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x1800059cf`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x180005aa6`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x1800054d8`: `Failed to call OOBEComplete. GLE = %d`
- `0x180005677`: `UninstallActive`
- `0x180005713`: `Uninstall is %sactive`
- `0x180005782`: `UninstallMark`
- `0x18000593c`: `Installation finished more than %d days ago. Uninstall is no longer valid.`
- `0x180005b0c`: `Block reason: Uninstall is still valid.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AreConditionsMet(struct UnBCL::RegistryKey *a1, int *a2, struct TraceLoggingCorrelationVector *a3)
{
  int v3; // r15d
  DWORD LastError; // edi
  __int64 v5; // rbx
  DWORD v6; // eax
  struct tagLOG_PARTIAL_MSG *v7; // rax
  int v8; // eax
  unsigned int v9; // r12d
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // ebx
  const struct UnBCL::String *v14; // rax
  struct UnBCL::RegistryKey *v15; // rax
  UnBCL::RegistryKey *v16; // rsi
  const struct UnBCL::String *v17; // rax
  BOOL v18; // esi
  DWORD v19; // edi
  __int64 v20; // rbx
  const wchar_t *v21; // r8
  struct tagLOG_PARTIAL_MSG *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned __int16 *v25; // rdi
  struct UnBCL::RegistryKey *v26; // rax
  struct UnBCL::RegistryKey *v27; // rsi
  __int64 Now; // rax
  DWORD v29; // edi
  __int64 v30; // rbx
  int Days; // eax
  struct tagLOG_PARTIAL_MSG *v32; // rax
  signed int v33; // eax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  int *v37; // rax
  const struct UnBCL::String *v38; // rax
  struct UnBCL::RegistryKey *v39; // rax
  DWORD v40; // edi
  __int64 v41; // rbx
  struct tagLOG_PARTIAL_MSG *v42; // rax
  DWORD v43; // edi
  __int64 v44; // rbx
  struct tagLOG_PARTIAL_MSG *v45; // rax
  __int64 v46; // rax
  void (__fastcall ***v48)(_QWORD, __int64); // rsi
  __int64 v49; // rax
  DWORD v50; // edi
  __int64 v51; // rbx
  UnBCL::String *v52; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v54; // rax
  unsigned int v55; // [rsp+60h] [rbp-248h] BYREF
  unsigned int v56; // [rsp+64h] [rbp-244h] BYREF
  unsigned int v57; // [rsp+68h] [rbp-240h] BYREF
  unsigned int v58; // [rsp+6Ch] [rbp-23Ch] BYREF
  int v59; // [rsp+70h] [rbp-238h]
  unsigned int Value; // [rsp+74h] [rbp-234h]
  int v61; // [rsp+78h] [rbp-230h] BYREF
  struct UnBCL::RegistryKey *v62; // [rsp+80h] [rbp-228h] BYREF
  TraceLoggingCorrelationVector *v63; // [rsp+88h] [rbp-220h] BYREF
  int *v64; // [rsp+90h] [rbp-218h] BYREF
  int *v65; // [rsp+98h] [rbp-210h] BYREF
  _QWORD v66[2]; // [rsp+A0h] [rbp-208h] BYREF
  void **v67; // [rsp+B0h] [rbp-1F8h] BYREF
  UnBCL::RegistryKey *v68; // [rsp+B8h] [rbp-1F0h]
  _QWORD v69[3]; // [rsp+C0h] [rbp-1E8h] BYREF
  _BYTE v70[16]; // [rsp+D8h] [rbp-1D0h] BYREF
  _BYTE v71[24]; // [rsp+E8h] [rbp-1C0h] BYREF
  _BYTE v72[16]; // [rsp+100h] [rbp-1A8h] BYREF
  _BYTE v73[24]; // [rsp+110h] [rbp-198h] BYREF
  void (__fastcall ***v74)(_QWORD, __int64); // [rsp+128h] [rbp-180h] BYREF
  void (__fastcall ***v75)(_QWORD, __int64); // [rsp+130h] [rbp-178h] BYREF
  char Destination[32]; // [rsp+140h] [rbp-168h] BYREF
  unsigned int *v77; // [rsp+160h] [rbp-148h]
  __int64 v78; // [rsp+168h] [rbp-140h]
  unsigned int *v79; // [rsp+170h] [rbp-138h]
  __int64 v80; // [rsp+178h] [rbp-130h]
  int **v81; // [rsp+180h] [rbp-128h]
  __int64 v82; // [rsp+188h] [rbp-120h]
  int **v83; // [rsp+190h] [rbp-118h]
  __int64 v84; // [rsp+198h] [rbp-110h]
  struct UnBCL::RegistryKey **v85; // [rsp+1A0h] [rbp-108h]
  __int64 v86; // [rsp+1A8h] [rbp-100h]
  TraceLoggingCorrelationVector **v87; // [rsp+1B0h] [rbp-F8h]
  __int64 v88; // [rsp+1B8h] [rbp-F0h]
  char v89[32]; // [rsp+1D0h] [rbp-D8h] BYREF
  TraceLoggingCorrelationVector **v90; // [rsp+1F0h] [rbp-B8h]
  __int64 v91; // [rsp+1F8h] [rbp-B0h]
  struct UnBCL::RegistryKey **v92; // [rsp+200h] [rbp-A8h]
  __int64 v93; // [rsp+208h] [rbp-A0h]
  int **v94; // [rsp+210h] [rbp-98h]
  __int64 v95; // [rsp+218h] [rbp-90h]
  int **v96; // [rsp+220h] [rbp-88h]
  __int64 v97; // [rsp+228h] [rbp-80h]
  unsigned int *v98; // [rsp+230h] [rbp-78h]
  __int64 v99; // [rsp+238h] [rbp-70h]
  unsigned int *v100; // [rsp+240h] [rbp-68h]
  __int64 v101; // [rsp+248h] [rbp-60h]
  char *v102; // [rsp+250h] [rbp-58h]
  int v103; // [rsp+258h] [rbp-50h]
  int v104; // [rsp+25Ch] [rbp-4Ch]

  v63 = a3;
  v65 = a2;
  v62 = a1;
  v64 = a2;
  v66[0] = a3;
  *a2 = 0;
  v61 = 0;
  v58 = 3;
  v56 = 10;
  v3 = 0;
  v59 = 0;
  Value = 0;
  v67 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  v68 = 0;
  if ( (unsigned int)OOBEComplete(&v61) )
  {
    v8 = v61;
  }
  else
  {
    LastError = GetLastError();
    v5 = CurrentIP();
    v6 = GetLastError();
    v7 = ConstructPartialMsgW(0x3000000u, "Failed to call OOBEComplete. GLE = %d", v6);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      335,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
      L"AreConditionsMet",
      v5,
      LastError,
      0,
      0);
    v8 = 0;
    v61 = 0;
  }
  if ( !v8 )
  {
    v9 = 0;
    v10 = GetLastError();
    v11 = CurrentIP();
    v12 = ConstructPartialMsgW(0x3000000u, "Block reason: OOBE hasn't finished yet.");
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      343,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
      L"AreConditionsMet",
      v11,
      v10,
      0,
      0);
    v13 = 3;
    goto LABEL_25;
  }
  v13 = 0;
  v57 = 0;
  v9 = 1;
  v55 = 1;
  v14 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v71, L"SYSTEM\\Setup");
  v15 = UnBCL::RegistryKey::OpenSubKey(v62, v14, 0);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v69, (__int64)v15);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=((__int64)&v67, (__int64)v69);
  v69[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(v69);
  UnBCL::String::~String((UnBCL::String *)v71);
  v16 = v68;
  if ( v68 )
  {
    ReadUninstallWindow(v62, &v58, &v56);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v17 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v71, L"UninstallActive");
      Value = UnBCL::RegistryKey::GetValue(v16, v17);
      UnBCL::String::~String((UnBCL::String *)v71);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &UnBCL::Exception * `RTTI Type Descriptor', (UnBCL::Exception **)&v74) )
      {
        if ( v74 )
          (**v74)(v74, 1);
        v9 = v55;
        v3 = v59;
        v65 = v64;
        v63 = (TraceLoggingCorrelationVector *)v66[0];
        __eh34_try_continuation(0, &UnBCL::Exception * `RTTI Type Descriptor', &loc_1800056AE);
      }
    }
    v18 = Value == 1;
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = &word_18003D6CC;
    if ( !v18 )
      v21 = L"not ";
    v22 = ConstructPartialMsgW(0x4000000u, "Uninstall is %sactive", (const char *)v21);
    WdsSetupLogMessageW(
      v22,
      0,
      L"D",
      0,
      362,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
      L"AreConditionsMet",
      v20,
      v19,
      0,
      0);
    if ( !v18 )
    {
LABEL_21:
      v38 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v73, L"DeploymentInProgress");
      v39 = UnBCL::RegistryKey::OpenSubKey(v68, v38, 0);
      UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v66, (__int64)v39);
      UnBCL::String::~String((UnBCL::String *)v73);
      if ( v66[1] )
      {
        v40 = GetLastError();
        v41 = CurrentIP();
        v42 = ConstructPartialMsgW(0x4000000u, "Block reason: Deployment is in progress.");
        WdsSetupLogMessageW(
          v42,
          0,
          L"D",
          0,
          417,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
          L"AreConditionsMet",
          v41,
          v40,
          0,
          0);
        v9 = 0;
        v13 = 1;
        v66[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
        UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(v66);
      }
      else
      {
        v66[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
        UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(v66);
        v13 = v57;
      }
      goto LABEL_25;
    }
    v3 = 1;
    UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::SmartPtr<UnBCL::Array<unsigned char>>(v72);
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      v23 = UnBCL::String::String((UnBCL::String *)v69, L"UninstallMark");
      UnBCL::RegistryKey::GetBinaryValue(v68, v23);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::SmartPtr<UnBCL::Array<unsigned char>>(v70);
      UnBCL::String::~String((UnBCL::String *)v69);
      v24 = UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::operator->(v70);
      v25 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 56LL))(v24, 0);
      v26 = (struct UnBCL::RegistryKey *)UnBCL::Object::operator new(0x18u);
      v27 = v26;
      v62 = v26;
      if ( v26 )
      {
        UnBCL::DateTime::DateTime(v26, *v25, v25[1], v25[3], v25[4], v25[5], v25[6], v25[7]);
        *(_QWORD *)v27 = &UnBCL::DateTime::`local vftable';
      }
      else
      {
        v27 = 0;
      }
      UnBCL::SmartPtr<UnBCL::DateTime>::SmartPtr<UnBCL::DateTime>(v69, v27);
      Now = UnBCL::DateTime::GetNow(v73, 1);
      UnBCL::DateTime::Subtract(Now, v71, v69[1]);
      UnBCL::Object::~Object((UnBCL::Object *)v73);
      v29 = GetLastError();
      v30 = CurrentIP();
      Days = UnBCL::TimeSpan::get_Days((UnBCL::TimeSpan *)v71);
      v32 = ConstructPartialMsgW(0x4000000u, "Number of days since upgrade finished: %d", Days);
      WdsSetupLogMessageW(
        v32,
        0,
        L"D",
        0,
        386,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
        L"AreConditionsMet",
        v30,
        v29,
        0,
        0);
      v33 = UnBCL::TimeSpan::get_Days((UnBCL::TimeSpan *)v71);
      if ( v33 > (int)v56 )
      {
        v34 = GetLastError();
        v35 = CurrentIP();
        v36 = ConstructPartialMsgW(
                0x4000000u,
                "Installation finished more than %d days ago. Uninstall is no longer valid.",
                v56);
        WdsSetupLogMessageW(
          v36,
          0,
          L"D",
          0,
          389,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
          L"AreConditionsMet",
          v35,
          v34,
          0,
          0);
        v3 = 0;
        v59 = 0;
      }
      UnBCL::Object::~Object((UnBCL::Object *)v71);
      UnBCL::SmartPtr<UnBCL::DateTime>::~SmartPtr<UnBCL::DateTime>(v69);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::~SmartPtr<UnBCL::Array<unsigned char>>(v70);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &UnBCL::Exception * `RTTI Type Descriptor', (UnBCL::Exception **)&v75) )
      {
        v48 = v75;
        v49 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v75)[4])(v75);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v70, v49);
        v50 = GetLastError();
        v51 = CurrentIP();
        v52 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v70);
        CString = (const char *)UnBCL::String::get_CString(v52);
        v54 = ConstructPartialMsgW(
                0x2000000u,
                "Failed to read uninstall mark time. Will consider uninstall invalid. Exception: %s",
                CString);
        WdsSetupLogMessageW(
          v54,
          0,
          L"D",
          0,
          396,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
          L"AreConditionsMet",
          v51,
          v50,
          0,
          0);
        v59 = 0;
        (**v48)(v48, 1);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v70);
        v9 = v55;
        v3 = v59;
        v37 = v64;
        v63 = (TraceLoggingCorrelationVector *)v66[0];
        __eh34_try_continuation(2, &UnBCL::Exception * `RTTI Type Descriptor', &loc_1800059C5);
        goto LABEL_19;
      }
    }
    v37 = v65;
LABEL_19:
    if ( v3 )
    {
      v9 = 0;
      v43 = GetLastError();
      v44 = CurrentIP();
      v45 = ConstructPartialMsgW(0x4000000u, "Block reason: Uninstall is still valid.");
      WdsSetupLogMessageW(
        v45,
        0,
        L"D",
        0,
        409,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
        L"AreConditionsMet",
        v44,
        v43,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::~SmartPtr<UnBCL::Array<unsigned char>>(v72);
      v13 = 2;
      goto LABEL_25;
    }
    *v37 = 1;
    UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::~SmartPtr<UnBCL::Array<unsigned char>>(v72);
    goto LABEL_21;
  }
LABEL_25:
  if ( v63 )
  {
    if ( (unsigned int)dword_180051018 > 5
      && (qword_180051028 & 0x400000000000LL) != 0
      && (qword_180051030 & 0x400000000000LL) == qword_180051030 )
    {
      TraceLoggingCorrelationVector::ToString(v63, Destination);
      v55 = v13;
      v57 = v9;
      LODWORD(v64) = v3;
      LODWORD(v65) = Value;
      LODWORD(v62) = v58;
      LODWORD(v63) = v56;
      v46 = -1;
      do
        ++v46;
      while ( Destination[v46] );
      v102 = Destination;
      v103 = v46 + 1;
      v104 = 0;
      v100 = &v55;
      v101 = 4;
      v98 = &v57;
      v99 = 4;
      v96 = &v64;
      v97 = 4;
      v94 = &v65;
      v95 = 4;
      v92 = &v62;
      v93 = 4;
      v90 = &v63;
      v91 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180051018, word_180046E32, 0, 0, 9, v89);
    }
  }
  else if ( (unsigned int)dword_180051018 > 5
         && (qword_180051028 & 0x400000000000LL) != 0
         && (qword_180051030 & 0x400000000000LL) == qword_180051030 )
  {
    LODWORD(v63) = v13;
    LODWORD(v62) = v9;
    LODWORD(v65) = v3;
    LODWORD(v64) = Value;
    v55 = v58;
    v58 = v56;
    v87 = &v63;
    v88 = 4;
    v85 = &v62;
    v86 = 4;
    v83 = &v65;
    v84 = 4;
    v81 = &v64;
    v82 = 4;
    v79 = &v55;
    v80 = 4;
    v77 = &v58;
    v78 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180051018, &dword_180046D8C, 0, 0, 8, Destination);
  }
  v67 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(&v67);
  return v9;
}

```

## disassembly

```asm
0x18000541c  push    rbx
0x18000541e  push    rsi
0x18000541f  push    rdi
0x180005420  push    r12
0x180005422  push    r13
0x180005424  push    r14
0x180005426  push    r15
0x180005428  sub     rsp, 270h
0x18000542f  mov     rax, cs:__security_cookie
0x180005436  xor     rax, rsp
0x180005439  mov     [rsp+2A8h+var_48], rax
0x180005441  mov     [rsp+2A8h+var_220], r8
0x180005449  mov     rax, rdx
0x18000544c  mov     [rsp+2A8h+var_210], rdx
0x180005454  mov     [rsp+2A8h+var_228], rcx
0x18000545c  mov     [rsp+2A8h+var_218], rdx
0x180005464  mov     [rsp+2A8h+var_208], r8
0x18000546c  xor     r14d, r14d
0x18000546f  mov     [rdx], r14d
0x180005472  mov     [rsp+2A8h+var_230], r14d
0x180005477  lea     eax, [r14+3]
0x18000547b  mov     [rsp+2A8h+var_23C], eax
0x18000547f  mov     [rsp+2A8h+var_244], 0Ah
0x180005487  mov     r15d, r14d
0x18000548a  mov     [rsp+2A8h+var_238], r14d
0x18000548f  mov     [rsp+2A8h+var_234], r14d
0x180005494  lea     rdi, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000549b  mov     [rsp+2A8h+var_1F8], rdi
0x1800054a3  mov     [rsp+2A8h+var_1F0], r14
0x1800054ab  lea     rcx, [rsp+2A8h+var_230]
0x1800054b0  call    cs:__imp_OOBEComplete
0x1800054b6  test    eax, eax
0x1800054b8  jnz     loc_180005541
0x1800054be  call    cs:__imp_GetLastError
0x1800054c4  mov     edi, eax
0x1800054c6  call    cs:__imp_CurrentIP
0x1800054cc  mov     rbx, rax
0x1800054cf  call    cs:__imp_GetLastError
0x1800054d5  mov     r8d, eax
0x1800054d8  lea     rdx, aFailedToCallOo; "Failed to call OOBEComplete. GLE = %d"
0x1800054df  mov     ecx, 3000000h; unsigned int
0x1800054e4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800054e9  mov     [rsp+2A8h+var_258], r14d
0x1800054ee  mov     [rsp+2A8h+var_260], r14
0x1800054f3  mov     [rsp+2A8h+var_268], edi
0x1800054f7  mov     [rsp+2A8h+var_270], rbx
0x1800054fc  lea     r13, aAreconditionsm; "AreConditionsMet"
0x180005503  mov     [rsp+2A8h+var_278], r13
0x180005508  lea     rsi, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000550f  mov     [rsp+2A8h+var_280], rsi
0x180005514  mov     [rsp+2A8h+var_288], 14Fh
0x18000551c  xor     r9d, r9d
0x18000551f  lea     r8, aD_0; "D"
0x180005526  xor     edx, edx
0x180005528  mov     rcx, rax
0x18000552b  call    cs:__imp_WdsSetupLogMessageW
0x180005531  mov     eax, r14d
0x180005534  mov     [rsp+2A8h+var_230], eax
0x180005538  lea     rdi, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000553f  jmp     short loc_180005553
0x180005541  lea     r13, aAreconditionsm; "AreConditionsMet"
0x180005548  lea     rsi, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000554f  mov     eax, [rsp+2A8h+var_230]
0x180005553  test    eax, eax
0x180005555  jnz     short loc_1800055C7
0x180005557  mov     r12d, r14d
0x18000555a  call    cs:__imp_GetLastError
0x180005560  mov     edi, eax
0x180005562  call    cs:__imp_CurrentIP
0x180005568  mov     rbx, rax
0x18000556b  lea     rdx, aBlockReasonOob; "Block reason: OOBE hasn't finished yet."
0x180005572  mov     ecx, 3000000h; unsigned int
0x180005577  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000557c  mov     [rsp+2A8h+var_258], r14d
0x180005581  mov     [rsp+2A8h+var_260], r14
0x180005586  mov     [rsp+2A8h+var_268], edi
0x18000558a  mov     [rsp+2A8h+var_270], rbx
0x18000558f  mov     [rsp+2A8h+var_278], r13
0x180005594  mov     [rsp+2A8h+var_280], rsi
0x180005599  mov     [rsp+2A8h+var_288], 157h
0x1800055a1  xor     r9d, r9d
0x1800055a4  lea     r8, aD_0; "D"
0x1800055ab  xor     edx, edx
0x1800055ad  mov     rcx, rax
0x1800055b0  call    cs:__imp_WdsSetupLogMessageW
0x1800055b6  mov     ebx, 3
0x1800055bb  lea     rdi, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x1800055c2  jmp     loc_180005B90
0x1800055c7  mov     ebx, r14d
0x1800055ca  mov     [rsp+2A8h+var_240], ebx
0x1800055ce  mov     r12d, 1
0x1800055d4  mov     [rsp+2A8h+var_248], r12d
0x1800055d9  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1800055e0  lea     rcx, [rsp+2A8h+var_1C0]
0x1800055e8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800055ee  nop
0x1800055ef  xor     r8d, r8d
0x1800055f2  mov     rdx, rax
0x1800055f5  mov     rcx, [rsp+2A8h+var_228]
0x1800055fd  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x180005603  mov     rdx, rax
0x180005606  lea     rcx, [rsp+2A8h+var_1E8]
0x18000560e  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x180005613  nop
0x180005614  lea     rdx, [rsp+2A8h+var_1E8]
0x18000561c  lea     rcx, [rsp+2A8h+var_1F8]
0x180005624  call    ??4?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(UnBCL::SmartPtr<UnBCL::RegistryKey> const &)
0x180005629  nop
0x18000562a  mov     [rsp+2A8h+var_1E8], rdi
0x180005632  lea     rcx, [rsp+2A8h+var_1E8]
0x18000563a  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000563f  nop
0x180005640  lea     rcx, [rsp+2A8h+var_1C0]
0x180005648  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000564e  mov     rsi, [rsp+2A8h+var_1F0]
0x180005656  test    rsi, rsi
0x180005659  jz      loc_180005B90
0x18000565f  lea     r8, [rsp+2A8h+var_244]; unsigned int *
0x180005664  lea     rdx, [rsp+2A8h+var_23C]; unsigned int *
0x180005669  mov     rcx, [rsp+2A8h+var_228]; struct UnBCL::RegistryKey *
0x180005671  call    ?ReadUninstallWindow@@YAXPEAVRegistryKey@UnBCL@@AEAK1@Z; ReadUninstallWindow(UnBCL::RegistryKey *,ulong &,ulong &)
0x180005676  nop
0x180005677  lea     rdx, aUninstallactiv; "UninstallActive"
0x18000567e  lea     rcx, [rsp+2A8h+var_1C0]
0x180005686  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000568c  nop
0x18000568d  mov     rdx, rax
0x180005690  mov     rcx, rsi
0x180005693  call    cs:__imp_?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z; UnBCL::RegistryKey::GetValue(UnBCL::String const *)
0x180005699  mov     [rsp+2A8h+var_234], eax
0x18000569d  lea     rcx, [rsp+2A8h+var_1C0]
0x1800056a5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800056ab  nop
0x1800056ac  jmp     short loc_1800056E2
0x1800056ae  xor     r14d, r14d
0x1800056b1  lea     r13, aAreconditionsm; "AreConditionsMet"
0x1800056b8  mov     r12d, [rsp+2A8h+var_248]
0x1800056bd  mov     r15d, [rsp+2A8h+var_238]
0x1800056c2  mov     rax, [rsp+2A8h+var_218]
0x1800056ca  mov     [rsp+2A8h+var_210], rax
0x1800056d2  mov     rax, [rsp+2A8h+var_208]
0x1800056da  mov     [rsp+2A8h+var_220], rax
0x1800056e2  mov     esi, r14d
0x1800056e5  cmp     [rsp+2A8h+var_234], 1
0x1800056ea  setz    sil
0x1800056ee  call    cs:__imp_GetLastError
0x1800056f4  mov     edi, eax
0x1800056f6  call    cs:__imp_CurrentIP
0x1800056fc  mov     rbx, rax
0x1800056ff  lea     rax, aNot; "not "
0x180005706  lea     r8, word_18003D6CC
0x18000570d  test    esi, esi
0x18000570f  cmovz   r8, rax
0x180005713  lea     rdx, aUninstallIsSac; "Uninstall is %sactive"
0x18000571a  mov     ecx, 4000000h; unsigned int
0x18000571f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005724  mov     [rsp+2A8h+var_258], r14d
0x180005729  mov     [rsp+2A8h+var_260], r14
0x18000572e  mov     [rsp+2A8h+var_268], edi
0x180005732  mov     [rsp+2A8h+var_270], rbx
0x180005737  mov     [rsp+2A8h+var_278], r13
0x18000573c  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180005743  mov     [rsp+2A8h+var_280], rcx
0x180005748  mov     [rsp+2A8h+var_288], 16Ah
0x180005750  xor     r9d, r9d
0x180005753  lea     r8, aD_0; "D"
0x18000575a  xor     edx, edx
0x18000575c  mov     rcx, rax
0x18000575f  call    cs:__imp_WdsSetupLogMessageW
0x180005765  test    esi, esi
0x180005767  jz      loc_180005A15
0x18000576d  xor     edx, edx
0x18000576f  lea     r15d, [rdx+1]
0x180005773  lea     rcx, [rsp+2A8h+var_1A8]
0x18000577b  call    cs:__imp_??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z; UnBCL::SmartPtr<UnBCL::Array<uchar>>::SmartPtr<UnBCL::Array<uchar>>(UnBCL::Array<uchar> *)
0x180005781  nop
0x180005782  lea     rdx, aUninstallmark; "UninstallMark"
0x180005789  lea     rcx, [rsp+2A8h+var_1E8]
0x180005791  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180005797  nop
0x180005798  mov     rdx, rax
0x18000579b  mov     rcx, [rsp+2A8h+var_1F0]
0x1800057a3  call    cs:__imp_?GetBinaryValue@RegistryKey@UnBCL@@QEAAPEAV?$Array@E@2@PEBVString@2@@Z; UnBCL::RegistryKey::GetBinaryValue(UnBCL::String const *)
0x1800057a9  mov     rdx, rax
0x1800057ac  lea     rcx, [rsp+2A8h+var_1D0]
0x1800057b4  call    cs:__imp_??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z; UnBCL::SmartPtr<UnBCL::Array<uchar>>::SmartPtr<UnBCL::Array<uchar>>(UnBCL::Array<uchar> *)
0x1800057ba  nop
0x1800057bb  lea     rcx, [rsp+2A8h+var_1E8]
0x1800057c3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800057c9  lea     rcx, [rsp+2A8h+var_1D0]
0x1800057d1  call    cs:__imp_??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ; UnBCL::SmartPtr<UnBCL::Array<uchar>>::operator->(void)
0x1800057d7  mov     r8, rax
0x1800057da  mov     rcx, [rax]
0x1800057dd  mov     rax, [rcx+38h]
0x1800057e1  xor     edx, edx
0x1800057e3  mov     rcx, r8
0x1800057e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057eb  mov     rdi, rax
0x1800057ee  lea     ecx, [r15+17h]
0x1800057f2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800057f8  mov     rsi, rax
0x1800057fb  mov     [rsp+2A8h+var_228], rax
0x180005803  test    rax, rax
0x180005806  jz      short loc_18000584E
0x180005808  movzx   ecx, word ptr [rdi+0Eh]
0x18000580c  movzx   r10d, word ptr [rdi+0Ch]
0x180005811  movzx   r11d, word ptr [rdi+0Ah]
0x180005816  movzx   ebx, word ptr [rdi+8]
0x18000581a  movzx   r9d, word ptr [rdi+6]
0x18000581f  movzx   r8d, word ptr [rdi+2]
0x180005824  movzx   edx, word ptr [rdi]
0x180005827  mov     dword ptr [rsp+2A8h+var_270], ecx
0x18000582b  mov     dword ptr [rsp+2A8h+var_278], r10d
0x180005830  mov     dword ptr [rsp+2A8h+var_280], r11d
0x180005835  mov     [rsp+2A8h+var_288], ebx
0x180005839  mov     rcx, rax
0x18000583c  call    cs:__imp_??0DateTime@UnBCL@@QEAA@HHHHHHH@Z; UnBCL::DateTime::DateTime(int,int,int,int,int,int,int)
0x180005842  lea     rax, ??_SDateTime@UnBCL@@6B@; const UnBCL::DateTime::`local vftable'
0x180005849  mov     [rsi], rax
0x18000584c  jmp     short loc_180005851
0x18000584e  mov     rsi, r14
0x180005851  mov     rdx, rsi
0x180005854  lea     rcx, [rsp+2A8h+var_1E8]
0x18000585c  call    ??0?$SmartPtr@VDateTime@UnBCL@@@UnBCL@@QEAA@PEAVDateTime@1@@Z; UnBCL::SmartPtr<UnBCL::DateTime>::SmartPtr<UnBCL::DateTime>(UnBCL::DateTime *)
0x180005861  nop
0x180005862  mov     edx, 1
0x180005867  lea     rcx, [rsp+2A8h+var_198]
0x18000586f  call    cs:__imp_?GetNow@DateTime@UnBCL@@SA?AV12@H@Z; UnBCL::DateTime::GetNow(int)
0x180005875  nop
0x180005876  mov     r8, [rsp+2A8h+var_1E0]
0x18000587e  lea     rdx, [rsp+2A8h+var_1C0]
0x180005886  mov     rcx, rax
0x180005889  call    cs:__imp_?Subtract@DateTime@UnBCL@@QEBA?AVTimeSpan@2@AEBV12@@Z; UnBCL::DateTime::Subtract(UnBCL::DateTime const &)
0x18000588f  nop
0x180005890  lea     rcx, [rsp+2A8h+var_198]
0x180005898  call    cs:__imp_??1Object@UnBCL@@UEAA@XZ; UnBCL::Object::~Object(void)
0x18000589e  call    cs:__imp_GetLastError
0x1800058a4  mov     edi, eax
0x1800058a6  call    cs:__imp_CurrentIP
0x1800058ac  mov     rbx, rax
0x1800058af  lea     rcx, [rsp+2A8h+var_1C0]
0x1800058b7  call    cs:__imp_?get_Days@TimeSpan@UnBCL@@QEBAHXZ; UnBCL::TimeSpan::get_Days(void)
0x1800058bd  mov     r8d, eax
0x1800058c0  lea     rdx, aNumberOfDaysSi_0; "Number of days since upgrade finished: "...
0x1800058c7  mov     ecx, 4000000h; unsigned int
0x1800058cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800058d1  mov     [rsp+2A8h+var_258], r14d
0x1800058d6  mov     [rsp+2A8h+var_260], r14
0x1800058db  mov     [rsp+2A8h+var_268], edi
0x1800058df  mov     [rsp+2A8h+var_270], rbx
0x1800058e4  mov     [rsp+2A8h+var_278], r13
0x1800058e9  lea     rsi, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800058f0  mov     [rsp+2A8h+var_280], rsi
0x1800058f5  mov     [rsp+2A8h+var_288], 182h
0x1800058fd  xor     r9d, r9d
0x180005900  lea     r8, aD_0; "D"
0x180005907  xor     edx, edx
0x180005909  mov     rcx, rax
0x18000590c  call    cs:__imp_WdsSetupLogMessageW
0x180005912  lea     rcx, [rsp+2A8h+var_1C0]
0x18000591a  call    cs:__imp_?get_Days@TimeSpan@UnBCL@@QEBAHXZ; UnBCL::TimeSpan::get_Days(void)
0x180005920  cmp     eax, [rsp+2A8h+var_244]
0x180005924  jle     short loc_18000598F
0x180005926  call    cs:__imp_GetLastError
0x18000592c  mov     edi, eax
0x18000592e  call    cs:__imp_CurrentIP
0x180005934  mov     rbx, rax
0x180005937  mov     r8d, [rsp+2A8h+var_244]
0x18000593c  lea     rdx, aInstallationFi; "Installation finished more than %d days"...
0x180005943  mov     ecx, 4000000h; unsigned int
0x180005948  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000594d  mov     [rsp+2A8h+var_258], r14d
0x180005952  mov     [rsp+2A8h+var_260], r14
0x180005957  mov     [rsp+2A8h+var_268], edi
0x18000595b  mov     [rsp+2A8h+var_270], rbx
0x180005960  mov     [rsp+2A8h+var_278], r13
0x180005965  mov     [rsp+2A8h+var_280], rsi
0x18000596a  mov     [rsp+2A8h+var_288], 185h
0x180005972  xor     r9d, r9d
0x180005975  lea     r8, aD_0; "D"
0x18000597c  xor     edx, edx
0x18000597e  mov     rcx, rax
0x180005981  call    cs:__imp_WdsSetupLogMessageW
0x180005987  mov     r15d, r14d
0x18000598a  mov     [rsp+2A8h+var_238], r14d
0x18000598f  lea     rcx, [rsp+2A8h+var_1C0]
0x180005997  call    cs:__imp_??1Object@UnBCL@@UEAA@XZ; UnBCL::Object::~Object(void)
0x18000599d  nop
0x18000599e  lea     rcx, [rsp+2A8h+var_1E8]
0x1800059a6  call    ??1?$SmartPtr@VDateTime@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::DateTime>::~SmartPtr<UnBCL::DateTime>(void)
0x1800059ab  nop
0x1800059ac  lea     rcx, [rsp+2A8h+var_1D0]
0x1800059b4  call    cs:__imp_??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::Array<uchar>>::~SmartPtr<UnBCL::Array<uchar>>(void)
0x1800059ba  nop
0x1800059bb  mov     rax, [rsp+2A8h+var_210]
0x1800059c3  jmp     short loc_1800059F8
0x1800059c5  xor     r14d, r14d
0x1800059c8  lea     r13, aAreconditionsm; "AreConditionsMet"
0x1800059cf  lea     rsi, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800059d6  mov     r12d, [rsp+2A8h+var_248]
  ... truncated ...
```
