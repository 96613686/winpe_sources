# CUpgradeSecurity::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x180172a20`
- end: `0x1801734f0`
- name: `?DoExecute@CUpgradeSecurity@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `2768`
- prototype: `__int64 __fastcall(CUpgradeSecurity *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180044820`
- `0x180057dec`
- `0x180172a20`
- `0x1802e2078`
- `0x1802e4bb8`
- `0x180329870`
- `0x180404f78`
- `0x1804058b0`
- `0x180406640`
- `0x18045d5a8`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180172fe1`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180172fe1`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180173096`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180173096`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180173156`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180173156`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180172f28`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180172f28`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180173246`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180173246`
- `KERNEL32!GetLastError` at `0x180172a6c`
- `KERNEL32!GetLastError` at `0x180172b7a`
- `KERNEL32!GetLastError` at `0x180172b9f`
- `KERNEL32!GetLastError` at `0x180172c41`
- `KERNEL32!GetLastError` at `0x180172cf9`
- `KERNEL32!GetLastError` at `0x180172d7c`
- `KERNEL32!GetLastError` at `0x180172d91`
- `KERNEL32!GetLastError` at `0x180172e26`
- `KERNEL32!GetLastError` at `0x180172e3b`
- `KERNEL32!GetLastError` at `0x180172f32`
- `KERNEL32!GetLastError` at `0x180172f47`
- `KERNEL32!GetLastError` at `0x180172feb`
- `KERNEL32!GetLastError` at `0x180173000`
- `KERNEL32!GetLastError` at `0x1801730a0`
- `KERNEL32!GetLastError` at `0x1801730b5`
- `KERNEL32!GetLastError` at `0x180173164`
- `KERNEL32!GetLastError` at `0x180173179`
- `KERNEL32!GetLastError` at `0x18017325f`
- `KERNEL32!GetLastError` at `0x180173324`
- `KERNEL32!GetLastError` at `0x180173419`
- `KERNEL32!GetLastError` at `0x180172a6c`
- `KERNEL32!GetLastError` at `0x180172b7a`
- `KERNEL32!GetLastError` at `0x180172b9f`
- `KERNEL32!GetLastError` at `0x180172c41`
- `KERNEL32!GetLastError` at `0x180172cf9`
- `KERNEL32!GetLastError` at `0x180172d7c`
- `KERNEL32!GetLastError` at `0x180172d91`
- `KERNEL32!GetLastError` at `0x180172e26`
- `KERNEL32!GetLastError` at `0x180172e3b`
- `KERNEL32!GetLastError` at `0x180172f32`
- `KERNEL32!GetLastError` at `0x180172f47`
- `KERNEL32!GetLastError` at `0x180172feb`
- `KERNEL32!GetLastError` at `0x180173000`
- `KERNEL32!GetLastError` at `0x1801730a0`
- `KERNEL32!GetLastError` at `0x1801730b5`
- `KERNEL32!GetLastError` at `0x180173164`
- `KERNEL32!GetLastError` at `0x180173179`
- `KERNEL32!GetLastError` at `0x18017325f`
- `KERNEL32!GetLastError` at `0x180173324`
- `KERNEL32!GetLastError` at `0x180173419`
- `KERNEL32!SetFileAttributesW` at `0x180172e18`
- `KERNEL32!SetFileAttributesW` at `0x180172e18`
- `KERNEL32!LocalFree` at `0x18017330a`
- `KERNEL32!LocalFree` at `0x18017330a`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180172cb7`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180172cb7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180172b12`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180172b12`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180172b6b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180172c28`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180172b6b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180172c28`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180172b2a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180172cd0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180172b2a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180172cd0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180172af3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180172cad`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180172af3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180172cad`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172b34`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172bb4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172cda`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172d5d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172da6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172e01`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172e50`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180173213`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180173274`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172b34`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172bb4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172cda`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172d5d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172da6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172e01`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180172e50`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180173213`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180173274`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172b3d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172bbd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172ce3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172d66`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172daf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172e0a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172e59`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18017321c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18017327d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172b3d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172bbd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172ce3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172d66`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172daf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172e0a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180172e59`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18017321c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18017327d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18017331c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180173389`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180173394`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18017331c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180173389`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180173394`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180172b1f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180172b60`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180172cc4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180172b1f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180172b60`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180172cc4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172ae2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172c12`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172c9b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172d53`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172eae`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172fa8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18017305d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180173112`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801731d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801732d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18017337e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801734c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172ae2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172c12`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172c9b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172d53`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172eae`
- `WDSCORE!WdsSetupLogMessageW` at `0x180172fa8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18017305d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180173112`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801731d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801732d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18017337e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801734c8`
- `WDSCORE!CurrentIP` at `0x180172a74`
- `WDSCORE!CurrentIP` at `0x180172ba7`
- `WDSCORE!CurrentIP` at `0x180172c49`
- `WDSCORE!CurrentIP` at `0x180172d01`
- `WDSCORE!CurrentIP` at `0x180172d99`
- `WDSCORE!CurrentIP` at `0x180172e43`
- `WDSCORE!CurrentIP` at `0x180172f4f`
- `WDSCORE!CurrentIP` at `0x180173008`
- `WDSCORE!CurrentIP` at `0x1801730bd`
- `WDSCORE!CurrentIP` at `0x180173181`
- `WDSCORE!CurrentIP` at `0x180173267`
- `WDSCORE!CurrentIP` at `0x18017332c`
- `WDSCORE!CurrentIP` at `0x180173421`
- `WDSCORE!CurrentIP` at `0x180172a74`
- `WDSCORE!CurrentIP` at `0x180172ba7`
- `WDSCORE!CurrentIP` at `0x180172c49`
- `WDSCORE!CurrentIP` at `0x180172d01`
- `WDSCORE!CurrentIP` at `0x180172d99`
- `WDSCORE!CurrentIP` at `0x180172e43`
- `WDSCORE!CurrentIP` at `0x180172f4f`
- `WDSCORE!CurrentIP` at `0x180173008`
- `WDSCORE!CurrentIP` at `0x1801730bd`
- `WDSCORE!CurrentIP` at `0x180173181`
- `WDSCORE!CurrentIP` at `0x180173267`
- `WDSCORE!CurrentIP` at `0x18017332c`
- `WDSCORE!CurrentIP` at `0x180173421`

## string_xrefs

- `0x1801731f4`: `SeSecurityPrivilege`
- `0x1801732e9`: `SeSecurityPrivilege`
- `0x180172bc9`: `Failed to read the migration scope from %s. hr = 0x%08X`
- `0x180172aa9`: `CUpgradeSecurity::DoExecute`
- `0x180173496`: `CUpgradeSecurity::DoExecute`
- `0x180172c52`: `Full upgrade detected; will set Recovery directory security`
- `0x180172a85`: `Upgrade security completed`
- `0x180173472`: `Cannot apply the security template for the new OS. Error: 0x%08X`
- `0x180172e65`: `Failed to hide directory %s. hr = 0x%08X`
- `0x180172d0a`: `Recovery directory does not exist; creating it`
- `0x180172dbb`: `Failed to create the directory %s. hr = 0x%08X`
- `0x1801730c9`: `Failed to get group from security descriptor. hr = 0x%08X`
- `0x18017318d`: `Failed to get DACL from security descriptor. hr = 0x%08X`
- `0x180172f5f`: `Failed to create security descriptor from SDDL %s. hr = 0x%08X`
- `0x180173014`: `Failed to get owner from security descriptor. hr = 0x%08X`
- `0x18017342a`: `Failed to set the Online Apply rollback checkpoint`
- `0x180173289`: `Failed to set security on %s. hr = 0x%08X`
- `0x180173335`: `Full upgrade not detected; will not set Recovery directory security`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CUpgradeSecurity::DoExecute(
        CUpgradeSecurity *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  int v4; // eax
  signed int v5; // esi
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  const struct UnBCL::String *v9; // rbx
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v14; // rax
  signed int v15; // ecx
  DWORD v16; // edi
  __int64 v17; // rbx
  UnBCL::String *v18; // rax
  const char *v19; // rax
  struct tagLOG_PARTIAL_MSG *v20; // rax
  int v21; // ecx
  __int64 P; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  const struct UnBCL::String *v26; // rax
  struct UnBCL::String *v27; // rax
  UnBCL::String *v28; // rax
  const unsigned __int16 *v29; // rax
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  UnBCL::String *v33; // rax
  const unsigned __int16 *v34; // rax
  signed int v35; // eax
  DWORD v36; // edi
  __int64 v37; // rbx
  UnBCL::String *v38; // rax
  const char *v39; // rax
  struct tagLOG_PARTIAL_MSG *v40; // rax
  UnBCL::String *v41; // rax
  const WCHAR *v42; // rax
  signed int v43; // eax
  DWORD v44; // edi
  __int64 v45; // rbx
  UnBCL::String *v46; // rax
  const char *v47; // rax
  struct tagLOG_PARTIAL_MSG *v48; // rax
  PSECURITY_DESCRIPTOR *v49; // rax
  signed int v50; // eax
  DWORD v51; // edi
  __int64 v52; // rbx
  struct tagLOG_PARTIAL_MSG *v53; // rax
  void *v54; // rax
  signed int v55; // eax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  void *v59; // rax
  signed int v60; // eax
  DWORD v61; // edi
  __int64 v62; // rbx
  struct tagLOG_PARTIAL_MSG *v63; // rax
  void *v64; // rax
  signed int v65; // eax
  DWORD v66; // edi
  __int64 v67; // rbx
  struct tagLOG_PARTIAL_MSG *v68; // rax
  struct _ACL *v69; // rbx
  PSID psidGroup; // rdi
  PSID v71; // rsi
  UnBCL::String *v72; // rax
  WCHAR *v73; // rax
  signed int v74; // eax
  DWORD v75; // edi
  __int64 v76; // rbx
  UnBCL::String *v77; // rax
  const char *v78; // rax
  struct tagLOG_PARTIAL_MSG *v79; // rax
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  __int64 v83; // rax
  struct IRollback *v84; // rbx
  struct UnBCL::String *v85; // rdi
  struct OSRollbackService::ICheckpointParameters *v86; // r9
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  struct tagLOG_PARTIAL_MSG *v90; // rax
  _BYTE v93[24]; // [rsp+70h] [rbp-90h] BYREF
  void **v94; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h]
  PACL pDacl; // [rsp+98h] [rbp-68h] BYREF
  PSID pGroup; // [rsp+A0h] [rbp-60h] BYREF
  PSID pOwner; // [rsp+A8h] [rbp-58h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+B0h] [rbp-50h] BYREF
  WINBOOL bDaclPresent; // [rsp+B4h] [rbp-4Ch] BYREF
  _BYTE v101[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v102[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v103[16]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR StringSecurityDescriptor[48]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = InstallSecurityTemplate((int)this);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  LastError = GetLastError();
  v7 = CurrentIP();
  if ( v5 < 0 )
  {
    v90 = ConstructPartialMsgW(0x2000000u, "Cannot apply the security template for the new OS. Error: 0x%08X", v5);
    WdsSetupLogMessageW(
      v90,
      819200,
      L"D",
      0,
      5022,
      L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
      L"CUpgradeSecurity::DoExecute",
      v7,
      LastError,
      0,
      0);
    return (unsigned int)v5;
  }
  v8 = ConstructPartialMsgW(0x4000000u, "Upgrade security completed");
  WdsSetupLogMessageW(
    v8,
    819200,
    L"D",
    0,
    5018,
    L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
    L"CUpgradeSecurity::DoExecute",
    v7,
    LastError,
    0,
    0);
  v9 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v101, L"SetupPlatform.ini");
  v10 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
  v11 = UnBCL::Path::Combine(v10, v9);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v103, v11);
  UnBCL::String::~String((UnBCL::String *)v101);
  v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v103);
  CString = UnBCL::String::get_CString(v12);
  v14 = SPReadConfigValue(L"Parameters", L"MigrationScope", CString);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v102, v14);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v102) )
  {
    P = UnBCL::SmartPtr<UnBCL::String>::get_P(v102);
    v21 = SPGetMigScopeFromString(P);
  }
  else
  {
    v15 = GetLastError();
    if ( (unsigned int)(v15 - 2) > 1 )
    {
      if ( v15 > 0 )
        v5 = (unsigned __int16)v15 | 0x80070000;
      else
        v5 = v15;
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v103);
      v19 = (const char *)UnBCL::String::get_CString(v18);
      v20 = ConstructPartialMsgW(0x2000000u, "Failed to read the migration scope from %s. hr = 0x%08X", v19, v5);
      WdsSetupLogMessageW(
        v20,
        819200,
        L"D",
        0,
        5043,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CUpgradeSecurity::DoExecute",
        v17,
        v16,
        0,
        0);
    }
    v21 = 0;
    if ( v5 < 0 )
      goto LABEL_54;
  }
  if ( v21 == 5 )
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(0x4000000u, "Full upgrade detected; will set Recovery directory security");
    WdsSetupLogMessageW(
      v25,
      819200,
      L"D",
      0,
      5055,
      L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
      L"CUpgradeSecurity::DoExecute",
      v24,
      v23,
      0,
      0);
    v26 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v93, L"%SystemDrive%\\Recovery");
    v27 = UnBCL::Environment::ExpandEnvironmentVariables(v26);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v101, v27);
    UnBCL::String::~String((UnBCL::String *)v93);
    v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
    v29 = UnBCL::String::get_CString(v28);
    if ( !(unsigned int)DirectoryExists(v29) )
    {
      v30 = GetLastError();
      v31 = CurrentIP();
      v32 = ConstructPartialMsgW(0x4000000u, "Recovery directory does not exist; creating it");
      WdsSetupLogMessageW(
        v32,
        819200,
        L"D",
        0,
        5060,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CUpgradeSecurity::DoExecute",
        v31,
        v30,
        0,
        0);
      v33 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
      v34 = UnBCL::String::get_CString(v33);
      if ( (unsigned int)CreatePath(v34) )
      {
        v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
        v42 = UnBCL::String::get_CString(v41);
        if ( !SetFileAttributesW(v42, 2u) )
        {
          v43 = GetLastError();
          v5 = v43;
          if ( v43 > 0 )
            v5 = (unsigned __int16)v43 | 0x80070000;
          v44 = GetLastError();
          v45 = CurrentIP();
          v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
          v47 = (const char *)UnBCL::String::get_CString(v46);
          v48 = ConstructPartialMsgW(0x2000000u, "Failed to hide directory %s. hr = 0x%08X", v47, v5);
          WdsSetupLogMessageW(
            v48,
            819200,
            L"D",
            0,
            5071,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CUpgradeSecurity::DoExecute",
            v45,
            v44,
            0,
            0);
        }
      }
      else
      {
        v35 = GetLastError();
        v5 = v35;
        if ( v35 > 0 )
          v5 = (unsigned __int16)v35 | 0x80070000;
        v36 = GetLastError();
        v37 = CurrentIP();
        v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
        v39 = (const char *)UnBCL::String::get_CString(v38);
        v40 = ConstructPartialMsgW(0x2000000u, "Failed to create the directory %s. hr = 0x%08X", v39, v5);
        WdsSetupLogMessageW(
          v40,
          819200,
          L"D",
          0,
          5064,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CUpgradeSecurity::DoExecute",
          v37,
          v36,
          0,
          0);
      }
    }
    hMem = 0;
    v94 = &RAII::CAutoLocalFree<void *>::`vftable';
    if ( v5 >= 0 )
    {
      wcscpy(StringSecurityDescriptor, L"O:BAG:BAD:PAI(A;OICI;GA;;;SY)(A;OICIA;;;BA)");
      v49 = (PSECURITY_DESCRIPTOR *)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v94);
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, v49, 0) )
      {
        v50 = GetLastError();
        v5 = v50;
        if ( v50 > 0 )
          v5 = (unsigned __int16)v50 | 0x80070000;
        v51 = GetLastError();
        v52 = CurrentIP();
        v53 = ConstructPartialMsgW(
                0x2000000u,
                "Failed to create security descriptor from SDDL %s. hr = 0x%08X",
                (const char *)StringSecurityDescriptor,
                v5);
        WdsSetupLogMessageW(
          v53,
          819200,
          L"D",
          0,
          5083,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CUpgradeSecurity::DoExecute",
          v52,
          v51,
          0,
          0);
      }
    }
    pOwner = 0;
    if ( v5 >= 0 )
    {
      bOwnerDefaulted = 0;
      v54 = (void *)((__int64 (__fastcall *)(void ***))v94[4])(&v94);
      if ( !GetSecurityDescriptorOwner(v54, &pOwner, &bOwnerDefaulted) )
      {
        v55 = GetLastError();
        v5 = v55;
        if ( v55 > 0 )
          v5 = (unsigned __int16)v55 | 0x80070000;
        v56 = GetLastError();
        v57 = CurrentIP();
        v58 = ConstructPartialMsgW(0x2000000u, "Failed to get owner from security descriptor. hr = 0x%08X", v5);
        WdsSetupLogMessageW(
          v58,
          819200,
          L"D",
          0,
          5094,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CUpgradeSecurity::DoExecute",
          v57,
          v56,
          0,
          0);
      }
    }
    pGroup = 0;
    if ( v5 >= 0 )
    {
      bOwnerDefaulted = 0;
      v59 = (void *)((__int64 (__fastcall *)(void ***))v94[4])(&v94);
      if ( !GetSecurityDescriptorGroup(v59, &pGroup, &bOwnerDefaulted) )
      {
        v60 = GetLastError();
        v5 = v60;
        if ( v60 > 0 )
          v5 = (unsigned __int16)v60 | 0x80070000;
        v61 = GetLastError();
        v62 = CurrentIP();
        v63 = ConstructPartialMsgW(0x2000000u, "Failed to get group from security descriptor. hr = 0x%08X", v5);
        WdsSetupLogMessageW(
          v63,
          819200,
          L"D",
          0,
          5105,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CUpgradeSecurity::DoExecute",
          v62,
          v61,
          0,
          0);
      }
    }
    pDacl = 0;
    if ( v5 >= 0 )
    {
      bDaclPresent = 0;
      bOwnerDefaulted = 0;
      v64 = (void *)((__int64 (__fastcall *)(void ***))v94[4])(&v94);
      if ( GetSecurityDescriptorDacl(v64, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
        goto LABEL_43;
      v65 = GetLastError();
      v5 = v65;
      if ( v65 > 0 )
        v5 = (unsigned __int16)v65 | 0x80070000;
      v66 = GetLastError();
      v67 = CurrentIP();
      v68 = ConstructPartialMsgW(0x2000000u, "Failed to get DACL from security descriptor. hr = 0x%08X", v5);
      WdsSetupLogMessageW(
        v68,
        819200,
        L"D",
        0,
        5117,
        L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
        L"CUpgradeSecurity::DoExecute",
        v67,
        v66,
        0,
        0);
      if ( v5 >= 0 )
      {
LABEL_43:
        bOwnerDefaulted = 0;
        bDaclPresent = EnablePrivilegeEx(L"SeSecurityPrivilege");
        v69 = pDacl;
        psidGroup = pGroup;
        v71 = pOwner;
        v72 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
        v73 = (WCHAR *)UnBCL::String::get_CString(v72);
        v74 = SetNamedSecurityInfoW(v73, SE_FILE_OBJECT, 0x80000007, v71, psidGroup, v69, 0);
        v5 = v74;
        if ( v74 > 0 )
          v5 = (unsigned __int16)v74 | 0x80070000;
        if ( v5 < 0 )
        {
          v75 = GetLastError();
          v76 = CurrentIP();
          v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
          v78 = (const char *)UnBCL::String::get_CString(v77);
          v79 = ConstructPartialMsgW(0x2000000u, "Failed to set security on %s. hr = 0x%08X", v78, v5);
          WdsSetupLogMessageW(
            v79,
            819200,
            L"D",
            0,
            5139,
            L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
            L"CUpgradeSecurity::DoExecute",
            v76,
            v75,
            0,
            0);
        }
        if ( bDaclPresent && !bOwnerDefaulted )
          EnablePrivilegeEx(L"SeSecurityPrivilege");
      }
    }
    v94 = &RAII::CAutoLocalFree<void *>::`vftable';
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v101);
  }
  else
  {
    v80 = GetLastError();
    v81 = CurrentIP();
    v82 = ConstructPartialMsgW(0x4000000u, "Full upgrade not detected; will not set Recovery directory security");
    WdsSetupLogMessageW(
      v82,
      819200,
      L"D",
      0,
      5150,
      L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
      L"CUpgradeSecurity::DoExecute",
      v81,
      v80,
      0,
      0);
  }
LABEL_54:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v102);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v103);
  if ( v5 >= 0 )
  {
    v83 = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 72LL))(a2);
    v84 = (struct IRollback *)v83;
    if ( v83 )
    {
      v85 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v83 + 40LL))(v83)
        && (*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v84 + 56LL))(v84) )
      {
        v85 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IRollback *))(*(_QWORD *)v84 + 56LL))(v84);
      }
      if ( !(unsigned int)SPSetRollbackCheckpoint(v84, L"SetupPlatformOnlineApplyCheckpoint", v85, v86) )
      {
        v5 = -2147023537;
        v87 = GetLastError();
        v88 = CurrentIP();
        v89 = ConstructPartialMsgW(0x2000000u, "Failed to set the Online Apply rollback checkpoint");
        WdsSetupLogMessageW(
          v89,
          819200,
          L"D",
          0,
          5182,
          L"base\\ntsetup\\setupplatform\\lib\\src\\miscoperations.cpp",
          L"CUpgradeSecurity::DoExecute",
          v88,
          v87,
          0,
          0);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180172a20  push    rbp
0x180172a22  push    rbx
0x180172a23  push    rsi
0x180172a24  push    rdi
0x180172a25  push    r12
0x180172a27  push    r13
0x180172a29  push    r14
0x180172a2b  push    r15
0x180172a2d  lea     rbp, [rsp-68h]
0x180172a32  sub     rsp, 168h
0x180172a39  mov     [rsp+1A0h+var_138], 0FFFFFFFFFFFFFFFEh
0x180172a42  mov     rax, cs:__security_cookie
0x180172a49  xor     rax, rsp
0x180172a4c  mov     [rbp+0A0h+var_50], rax
0x180172a50  mov     [rsp+1A0h+var_140], rdx
0x180172a55  call    ?InstallSecurityTemplate@@YAKH@Z; InstallSecurityTemplate(int)
0x180172a5a  mov     esi, eax
0x180172a5c  xor     r14d, r14d
0x180172a5f  test    eax, eax
0x180172a61  jle     short loc_180172A6C
0x180172a63  movzx   esi, ax
0x180172a66  or      esi, 80070000h
0x180172a6c  call    cs:__imp_GetLastError
0x180172a72  mov     edi, eax
0x180172a74  call    cs:__imp_CurrentIP
0x180172a7a  mov     rbx, rax
0x180172a7d  test    esi, esi
0x180172a7f  js      loc_18017346F
0x180172a85  lea     rdx, aUpgradeSecurit_0; "Upgrade security completed"
0x180172a8c  mov     ecx, 4000000h; unsigned int
0x180172a91  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180172a96  mov     [rsp+1A0h+var_150], r14d
0x180172a9b  mov     [rsp+1A0h+var_158], r14
0x180172aa0  mov     [rsp+1A0h+var_160], edi
0x180172aa4  mov     [rsp+1A0h+var_168], rbx
0x180172aa9  lea     r12, aCupgradesecuri; "CUpgradeSecurity::DoExecute"
0x180172ab0  mov     [rsp+1A0h+pSacl], r12
0x180172ab5  lea     r13, aBaseNtsetupSet_48; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180172abc  mov     [rsp+1A0h+var_178], r13
0x180172ac1  mov     dword ptr [rsp+1A0h+psidGroup], 139Ah
0x180172ac9  xor     r9d, r9d
0x180172acc  lea     r14, aD_0; "D"
0x180172ad3  mov     r8, r14
0x180172ad6  mov     r15d, 0C8000h
0x180172adc  mov     edx, r15d
0x180172adf  mov     rcx, rax
0x180172ae2  call    cs:__imp_WdsSetupLogMessageW
0x180172ae8  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x180172aef  lea     rcx, [rbp+0A0h+var_E8]
0x180172af3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180172af9  mov     rbx, rax
0x180172afc  mov     rcx, [rsp+1A0h+var_140]
0x180172b01  mov     rax, [rcx]
0x180172b04  mov     rax, [rax]
0x180172b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180172b0c  mov     rdx, rbx
0x180172b0f  mov     rcx, rax
0x180172b12  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180172b18  mov     rdx, rax
0x180172b1b  lea     rcx, [rbp+0A0h+var_C0]
0x180172b1f  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180172b25  nop
0x180172b26  lea     rcx, [rbp+0A0h+var_E8]
0x180172b2a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180172b30  lea     rcx, [rbp+0A0h+var_C0]
0x180172b34  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172b3a  mov     rcx, rax
0x180172b3d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172b43  mov     r8, rax; lpFileName
0x180172b46  lea     rdx, aMigrationscope; "MigrationScope"
0x180172b4d  lea     rcx, szSection; "Parameters"
0x180172b54  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180172b59  mov     rdx, rax
0x180172b5c  lea     rcx, [rbp+0A0h+var_D0]
0x180172b60  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180172b66  nop
0x180172b67  lea     rcx, [rbp+0A0h+var_D0]
0x180172b6b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180172b71  test    rax, rax
0x180172b74  jnz     loc_180172C24
0x180172b7a  call    cs:__imp_GetLastError
0x180172b80  mov     ecx, eax
0x180172b82  add     eax, 0FFFFFFFEh
0x180172b85  cmp     eax, 1
0x180172b88  jbe     loc_180172C18
0x180172b8e  test    ecx, ecx
0x180172b90  jg      short loc_180172B96
0x180172b92  mov     esi, ecx
0x180172b94  jmp     short loc_180172B9F
0x180172b96  movzx   esi, cx
0x180172b99  or      esi, 80070000h
0x180172b9f  call    cs:__imp_GetLastError
0x180172ba5  mov     edi, eax
0x180172ba7  call    cs:__imp_CurrentIP
0x180172bad  mov     rbx, rax
0x180172bb0  lea     rcx, [rbp+0A0h+var_C0]
0x180172bb4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172bba  mov     rcx, rax
0x180172bbd  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172bc3  mov     r8, rax
0x180172bc6  mov     r9d, esi
0x180172bc9  lea     rdx, aFailedToReadTh_0; "Failed to read the migration scope from"...
0x180172bd0  mov     ecx, 2000000h; unsigned int
0x180172bd5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180172bda  mov     [rsp+1A0h+var_150], 0
0x180172be2  mov     [rsp+1A0h+var_158], 0
0x180172beb  mov     [rsp+1A0h+var_160], edi
0x180172bef  mov     [rsp+1A0h+var_168], rbx
0x180172bf4  mov     [rsp+1A0h+pSacl], r12
0x180172bf9  mov     [rsp+1A0h+var_178], r13
0x180172bfe  mov     dword ptr [rsp+1A0h+psidGroup], 13B3h
0x180172c06  xor     r9d, r9d
0x180172c09  mov     r8, r14
0x180172c0c  mov     edx, r15d
0x180172c0f  mov     rcx, rax
0x180172c12  call    cs:__imp_WdsSetupLogMessageW
0x180172c18  xor     ecx, ecx
0x180172c1a  test    esi, esi
0x180172c1c  js      loc_180173385
0x180172c22  jmp     short loc_180172C38
0x180172c24  lea     rcx, [rbp+0A0h+var_D0]
0x180172c28  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180172c2e  mov     rcx, rax
0x180172c31  call    ?SPGetMigScopeFromString@@YA?AW4SP_MIG_SCOPE@SetupPlatform@@PEAVString@UnBCL@@@Z; SPGetMigScopeFromString(UnBCL::String *)
0x180172c36  mov     ecx, eax
0x180172c38  cmp     ecx, 5
0x180172c3b  jnz     loc_180173324
0x180172c41  call    cs:__imp_GetLastError
0x180172c47  mov     edi, eax
0x180172c49  call    cs:__imp_CurrentIP
0x180172c4f  mov     rbx, rax
0x180172c52  lea     rdx, aFullUpgradeDet; "Full upgrade detected; will set Recover"...
0x180172c59  mov     ecx, 4000000h; unsigned int
0x180172c5e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180172c63  mov     [rsp+1A0h+var_150], 0
0x180172c6b  mov     [rsp+1A0h+var_158], 0
0x180172c74  mov     [rsp+1A0h+var_160], edi
0x180172c78  mov     [rsp+1A0h+var_168], rbx
0x180172c7d  mov     [rsp+1A0h+pSacl], r12
0x180172c82  mov     [rsp+1A0h+var_178], r13
0x180172c87  mov     dword ptr [rsp+1A0h+psidGroup], 13BFh
0x180172c8f  xor     r9d, r9d
0x180172c92  mov     r8, r14
0x180172c95  mov     edx, r15d
0x180172c98  mov     rcx, rax
0x180172c9b  call    cs:__imp_WdsSetupLogMessageW
0x180172ca1  lea     rdx, aSystemdriveRec; "%SystemDrive%\\Recovery"
0x180172ca8  lea     rcx, [rsp+1A0h+var_130]
0x180172cad  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180172cb3  nop
0x180172cb4  mov     rcx, rax
0x180172cb7  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x180172cbd  mov     rdx, rax
0x180172cc0  lea     rcx, [rbp+0A0h+var_E8]
0x180172cc4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180172cca  nop
0x180172ccb  lea     rcx, [rsp+1A0h+var_130]
0x180172cd0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180172cd6  lea     rcx, [rbp+0A0h+var_E8]
0x180172cda  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172ce0  mov     rcx, rax
0x180172ce3  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172ce9  mov     rcx, rax
0x180172cec  call    DirectoryExists
0x180172cf1  test    eax, eax
0x180172cf3  jnz     loc_180172EB4
0x180172cf9  call    cs:__imp_GetLastError
0x180172cff  mov     edi, eax
0x180172d01  call    cs:__imp_CurrentIP
0x180172d07  mov     rbx, rax
0x180172d0a  lea     rdx, aRecoveryDirect; "Recovery directory does not exist; crea"...
0x180172d11  mov     ecx, 4000000h; unsigned int
0x180172d16  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180172d1b  mov     [rsp+1A0h+var_150], 0
0x180172d23  mov     [rsp+1A0h+var_158], 0
0x180172d2c  mov     [rsp+1A0h+var_160], edi
0x180172d30  mov     [rsp+1A0h+var_168], rbx
0x180172d35  mov     [rsp+1A0h+pSacl], r12
0x180172d3a  mov     [rsp+1A0h+var_178], r13
0x180172d3f  mov     dword ptr [rsp+1A0h+psidGroup], 13C4h
0x180172d47  xor     r9d, r9d
0x180172d4a  mov     r8, r14
0x180172d4d  mov     edx, r15d
0x180172d50  mov     rcx, rax
0x180172d53  call    cs:__imp_WdsSetupLogMessageW
0x180172d59  lea     rcx, [rbp+0A0h+var_E8]
0x180172d5d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172d63  mov     rcx, rax
0x180172d66  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172d6c  mov     rcx, rax
0x180172d6f  call    CreatePath
0x180172d74  test    eax, eax
0x180172d76  jnz     loc_180172DFD
0x180172d7c  call    cs:__imp_GetLastError
0x180172d82  mov     esi, eax
0x180172d84  test    eax, eax
0x180172d86  jle     short loc_180172D91
0x180172d88  movzx   esi, ax
0x180172d8b  or      esi, 80070000h
0x180172d91  call    cs:__imp_GetLastError
0x180172d97  mov     edi, eax
0x180172d99  call    cs:__imp_CurrentIP
0x180172d9f  mov     rbx, rax
0x180172da2  lea     rcx, [rbp+0A0h+var_E8]
0x180172da6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172dac  mov     rcx, rax
0x180172daf  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172db5  mov     r8, rax
0x180172db8  mov     r9d, esi
0x180172dbb  lea     rdx, aFailedToCreate_42; "Failed to create the directory %s. hr ="...
0x180172dc2  mov     ecx, 2000000h; unsigned int
0x180172dc7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180172dcc  mov     [rsp+1A0h+var_150], 0
0x180172dd4  mov     [rsp+1A0h+var_158], 0
0x180172ddd  mov     [rsp+1A0h+var_160], edi
0x180172de1  mov     [rsp+1A0h+var_168], rbx
0x180172de6  mov     [rsp+1A0h+pSacl], r12
0x180172deb  mov     [rsp+1A0h+var_178], r13
0x180172df0  mov     dword ptr [rsp+1A0h+psidGroup], 13C8h
0x180172df8  jmp     loc_180172EA2
0x180172dfd  lea     rcx, [rbp+0A0h+var_E8]
0x180172e01  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172e07  mov     rcx, rax
0x180172e0a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172e10  mov     rcx, rax; lpFileName
0x180172e13  mov     edx, 2; dwFileAttributes
0x180172e18  call    cs:__imp_SetFileAttributesW
0x180172e1e  test    eax, eax
0x180172e20  jnz     loc_180172EB4
0x180172e26  call    cs:__imp_GetLastError
0x180172e2c  mov     esi, eax
0x180172e2e  test    eax, eax
0x180172e30  jle     short loc_180172E3B
0x180172e32  movzx   esi, ax
0x180172e35  or      esi, 80070000h
0x180172e3b  call    cs:__imp_GetLastError
0x180172e41  mov     edi, eax
0x180172e43  call    cs:__imp_CurrentIP
0x180172e49  mov     rbx, rax
0x180172e4c  lea     rcx, [rbp+0A0h+var_E8]
0x180172e50  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180172e56  mov     rcx, rax
0x180172e59  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180172e5f  mov     r8, rax
0x180172e62  mov     r9d, esi
0x180172e65  lea     rdx, aFailedToHideDi; "Failed to hide directory %s. hr = 0x%08"...
0x180172e6c  mov     ecx, 2000000h; unsigned int
0x180172e71  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180172e76  mov     [rsp+1A0h+var_150], 0
0x180172e7e  mov     [rsp+1A0h+var_158], 0
0x180172e87  mov     [rsp+1A0h+var_160], edi
0x180172e8b  mov     [rsp+1A0h+var_168], rbx
0x180172e90  mov     [rsp+1A0h+pSacl], r12
0x180172e95  mov     [rsp+1A0h+var_178], r13
0x180172e9a  mov     dword ptr [rsp+1A0h+psidGroup], 13CFh
0x180172ea2  xor     r9d, r9d
0x180172ea5  mov     r8, r14
0x180172ea8  mov     edx, r15d
0x180172eab  mov     rcx, rax
0x180172eae  call    cs:__imp_WdsSetupLogMessageW
0x180172eb4  mov     [rbp+0A0h+hMem], 0
0x180172ebc  lea     rax, ??_7?$CAutoLocalFree@PEAX@RAII@@6B@; const RAII::CAutoLocalFree<void *>::`vftable'
0x180172ec3  mov     [rbp+0A0h+var_118], rax
0x180172ec7  test    esi, esi
0x180172ec9  js      loc_180172FAE
0x180172ecf  movaps  xmm0, xmmword ptr cs:aOBagBadPaiAOic; "O:BAG:BAD:PAI(A;OICI;GA;;;SY)(A;OICI;GA"...
0x180172ed6  movaps  xmmword ptr [rbp+0A0h+StringSecurityDescriptor], xmm0
0x180172eda  movaps  xmm1, xmmword ptr cs:aOBagBadPaiAOic+10h; "D:PAI(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)"
0x180172ee1  movaps  [rbp+0A0h+var_A0], xmm1
0x180172ee5  movaps  xmm0, xmmword ptr cs:aOBagBadPaiAOic+20h; "OICI;GA;;;SY)(A;OICI;GA;;;BA)"
0x180172eec  movaps  [rbp+0A0h+var_90], xmm0
0x180172ef0  movaps  xmm1, xmmword ptr cs:aOBagBadPaiAOic+30h; ";;SY)(A;OICI;GA;;;BA)"
0x180172ef7  movaps  [rbp+0A0h+var_80], xmm1
0x180172efb  movaps  xmm0, xmmword ptr cs:aOBagBadPaiAOic+40h; "OICI;GA;;;BA)"
0x180172f02  movaps  [rbp+0A0h+var_70], xmm0
0x180172f06  movups  xmm1, xmmword ptr cs:aOBagBadPaiAOic+4Ch; "A;;;BA)"
0x180172f0d  movups  [rbp+0A0h+var_70+0Ch], xmm1
0x180172f11  lea     rcx, [rbp+0A0h+var_118]
0x180172f15  call    ??I?$CAutoCleanupBase@PEAVVdsVolumePathEnumerator@@@RAII@@UEBAPEBQEAVVdsVolumePathEnumerator@@XZ; RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(void)
0x180172f1a  mov     r8, rax; SecurityDescriptor
0x180172f1d  xor     r9d, r9d; SecurityDescriptorSize
0x180172f20  lea     edx, [r9+1]; StringSDRevision
0x180172f24  lea     rcx, [rbp+0A0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180172f28  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180172f2e  test    eax, eax
0x180172f30  jnz     short loc_180172FAE
0x180172f32  call    cs:__imp_GetLastError
0x180172f38  mov     esi, eax
0x180172f3a  test    eax, eax
0x180172f3c  jle     short loc_180172F47
0x180172f3e  movzx   esi, ax
0x180172f41  or      esi, 80070000h
0x180172f47  call    cs:__imp_GetLastError
0x180172f4d  mov     edi, eax
0x180172f4f  call    cs:__imp_CurrentIP
0x180172f55  mov     rbx, rax
0x180172f58  mov     r9d, esi
0x180172f5b  lea     r8, [rbp+0A0h+StringSecurityDescriptor]
0x180172f5f  lea     rdx, aFailedToCreate_27; "Failed to create security descriptor fr"...
0x180172f66  mov     ecx, 2000000h; unsigned int
  ... truncated ...
```
