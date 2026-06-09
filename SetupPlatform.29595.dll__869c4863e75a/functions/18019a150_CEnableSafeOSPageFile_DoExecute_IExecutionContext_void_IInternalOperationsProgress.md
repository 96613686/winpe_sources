# CEnableSafeOSPageFile::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x18019a150`
- end: `0x18019ae55`
- name: `?DoExecute@CEnableSafeOSPageFile@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `3333`
- prototype: `__int64 __fastcall(CEnableSafeOSPageFile *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180057dec`
- `0x18019a150`
- `0x18019c31c`
- `0x1802d6738`
- `0x1804339d4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18019a7f7`
- `ntdll!RtlInitUnicodeString` at `0x18019a7f7`
- `ntdll!NtCreatePagingFile` at `0x18019a80c`
- `ntdll!NtCreatePagingFile` at `0x18019a80c`
- `ntdll!NtSetSystemInformation` at `0x18019ada3`
- `ntdll!NtSetSystemInformation` at `0x18019ada3`
- `ADVAPI32!RegCloseKey` at `0x18019ab63`
- `ADVAPI32!RegCloseKey` at `0x18019ad03`
- `ADVAPI32!RegCloseKey` at `0x18019ab63`
- `ADVAPI32!RegCloseKey` at `0x18019ad03`
- `ADVAPI32!RegSetValueExW` at `0x18019ab56`
- `ADVAPI32!RegSetValueExW` at `0x18019acf6`
- `ADVAPI32!RegSetValueExW` at `0x18019ab56`
- `ADVAPI32!RegSetValueExW` at `0x18019acf6`
- `ADVAPI32!RegCreateKeyExW` at `0x18019ab27`
- `ADVAPI32!RegCreateKeyExW` at `0x18019acc9`
- `ADVAPI32!RegCreateKeyExW` at `0x18019ab27`
- `ADVAPI32!RegCreateKeyExW` at `0x18019acc9`
- `KERNEL32!GetLastError` at `0x18019a1d8`
- `KERNEL32!GetLastError` at `0x18019a2c5`
- `KERNEL32!GetLastError` at `0x18019a2dd`
- `KERNEL32!GetLastError` at `0x18019a2f5`
- `KERNEL32!GetLastError` at `0x18019a38a`
- `KERNEL32!GetLastError` at `0x18019a4e7`
- `KERNEL32!GetLastError` at `0x18019a55e`
- `KERNEL32!GetLastError` at `0x18019a63f`
- `KERNEL32!GetLastError` at `0x18019a6bb`
- `KERNEL32!GetLastError` at `0x18019a747`
- `KERNEL32!GetLastError` at `0x18019a823`
- `KERNEL32!GetLastError` at `0x18019a8e9`
- `KERNEL32!GetLastError` at `0x18019a952`
- `KERNEL32!GetLastError` at `0x18019a9ac`
- `KERNEL32!GetLastError` at `0x18019a9f4`
- `KERNEL32!GetLastError` at `0x18019aa70`
- `KERNEL32!GetLastError` at `0x18019ab71`
- `KERNEL32!GetLastError` at `0x18019ab96`
- `KERNEL32!GetLastError` at `0x18019ad19`
- `KERNEL32!GetLastError` at `0x18019ad36`
- `KERNEL32!GetLastError` at `0x18019adb7`
- `KERNEL32!GetLastError` at `0x18019a1d8`
- `KERNEL32!GetLastError` at `0x18019a2c5`
- `KERNEL32!GetLastError` at `0x18019a2dd`
- `KERNEL32!GetLastError` at `0x18019a2f5`
- `KERNEL32!GetLastError` at `0x18019a38a`
- `KERNEL32!GetLastError` at `0x18019a4e7`
- `KERNEL32!GetLastError` at `0x18019a55e`
- `KERNEL32!GetLastError` at `0x18019a63f`
- `KERNEL32!GetLastError` at `0x18019a6bb`
- `KERNEL32!GetLastError` at `0x18019a747`
- `KERNEL32!GetLastError` at `0x18019a823`
- `KERNEL32!GetLastError` at `0x18019a8e9`
- `KERNEL32!GetLastError` at `0x18019a952`
- `KERNEL32!GetLastError` at `0x18019a9ac`
- `KERNEL32!GetLastError` at `0x18019a9f4`
- `KERNEL32!GetLastError` at `0x18019aa70`
- `KERNEL32!GetLastError` at `0x18019ab71`
- `KERNEL32!GetLastError` at `0x18019ab96`
- `KERNEL32!GetLastError` at `0x18019ad19`
- `KERNEL32!GetLastError` at `0x18019ad36`
- `KERNEL32!GetLastError` at `0x18019adb7`
- `KERNEL32!SetLastError` at `0x18019ab6b`
- `KERNEL32!SetLastError` at `0x18019ad0b`
- `KERNEL32!SetLastError` at `0x18019ab6b`
- `KERNEL32!SetLastError` at `0x18019ad0b`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18019a27b`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18019a3f8`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18019a27b`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18019a3f8`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18019a733`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18019a733`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18019a455`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18019a455`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18019a42a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18019a487`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18019a42a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18019a487`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18019a41e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18019a44c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18019a47b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18019a41e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18019a44c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18019a47b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019a442`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019a4a0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019a442`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019a4a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019a411`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019a46e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019a411`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019a46e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a19e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a4ab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a5d9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a765`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a7e1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a19e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a4ab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a5d9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a765`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18019a7e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a1a7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a2ab`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a30b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a4b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a4c2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a506`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a5cb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a5e2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a655`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a723`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a76e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a7ea`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a839`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019aa0a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a1a7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a2ab`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a30b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a4b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a4c2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a506`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a5cb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a5e2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a655`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a723`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a76e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a7ea`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019a839`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18019aa0a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019a377`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019a6b3`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019a718`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019ae2e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019ae39`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019a377`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019a6b3`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019a718`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019ae2e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18019ae39`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a262`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a437`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a495`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a740`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a262`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a437`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a495`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18019a740`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a242`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a360`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a3e7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a5b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a637`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a6a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a70d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a7d0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a8d9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a943`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a9a6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019aa5f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019aad1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019ac02`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019ac72`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019ae14`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a242`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a360`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a3e7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a5b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a637`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a6a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a70d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a7d0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a8d9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a943`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019a9a6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019aa5f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019aad1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019ac02`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019ac72`
- `WDSCORE!WdsSetupLogMessageW` at `0x18019ae14`
- `WDSCORE!CurrentIP` at `0x18019a1e0`
- `WDSCORE!CurrentIP` at `0x18019a2fd`
- `WDSCORE!CurrentIP` at `0x18019a392`
- `WDSCORE!CurrentIP` at `0x18019a4f8`
- `WDSCORE!CurrentIP` at `0x18019a566`
- `WDSCORE!CurrentIP` at `0x18019a5bd`
- `WDSCORE!CurrentIP` at `0x18019a647`
- `WDSCORE!CurrentIP` at `0x18019a6c3`
- `WDSCORE!CurrentIP` at `0x18019a750`
- `WDSCORE!CurrentIP` at `0x18019a82b`
- `WDSCORE!CurrentIP` at `0x18019a8f1`
- `WDSCORE!CurrentIP` at `0x18019a95a`
- `WDSCORE!CurrentIP` at `0x18019a9b4`
- `WDSCORE!CurrentIP` at `0x18019a9fc`
- `WDSCORE!CurrentIP` at `0x18019aa78`
- `WDSCORE!CurrentIP` at `0x18019ab9e`
- `WDSCORE!CurrentIP` at `0x18019ac19`
- `WDSCORE!CurrentIP` at `0x18019ad3e`
- `WDSCORE!CurrentIP` at `0x18019adbf`
- `WDSCORE!CurrentIP` at `0x18019a1e0`
- `WDSCORE!CurrentIP` at `0x18019a2fd`
- `WDSCORE!CurrentIP` at `0x18019a392`

## string_xrefs

- `0x18019a39e`: `PAGEFILE: Existing page file is already %llu, extending maximum size`
- `0x18019a6cc`: `PAGEFILE: Could not find offline Windows directory; skipping MEMORY.DMP extraction`
- `0x18019a890`: `CEnableSafeOSPageFile::DoExecute: NtCreatePagingFile failed to create a %llu byte page file at %s: 0x%08x`
- `0x18019aa16`: `PAGEFILE: The page file at %s was already active and big enough (status: 0x%08x), no further action needed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CEnableSafeOSPageFile::DoExecute(
        CEnableSafeOSPageFile *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // rdi
  UnBCL::String *v6; // rax
  const unsigned __int16 *CString; // rax
  int v8; // esi
  DWORD LastError; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  const WCHAR *v12; // rax
  LARGE_INTEGER v13; // rax
  LARGE_INTEGER v14; // rsi
  signed int v15; // eax
  bool v16; // sf
  signed int v17; // eax
  unsigned int v18; // esi
  DWORD v19; // edi
  __int64 v20; // rbx
  const char *v21; // rax
  struct tagLOG_PARTIAL_MSG *v22; // rax
  unsigned int v23; // ebx
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  const struct UnBCL::String *v28; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v30; // rax
  const struct UnBCL::String *v31; // rax
  const struct UnBCL::String *v32; // rbx
  const struct UnBCL::String *v33; // rax
  struct UnBCL::String *v34; // rax
  UnBCL::String *v35; // rax
  const unsigned __int16 *v36; // rbx
  const unsigned __int16 *v37; // rax
  int CrashDumpFromPageFile; // esi
  DWORD v39; // eax
  DWORD v40; // edi
  __int64 v41; // rbx
  const char *v42; // rax
  struct tagLOG_PARTIAL_MSG *v43; // rax
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  DWORD v47; // esi
  __int64 v48; // rdi
  const char *v49; // rbx
  UnBCL::String *v50; // rax
  const char *v51; // rax
  struct tagLOG_PARTIAL_MSG *v52; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  const char *v55; // rax
  struct tagLOG_PARTIAL_MSG *v56; // rax
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  const unsigned __int16 *v60; // rax
  struct UnBCL::String *v61; // rax
  DWORD v62; // r14d
  __int64 v63; // rsi
  LARGE_INTEGER v64; // rbx
  LARGE_INTEGER v65; // rdi
  UnBCL::String *v66; // rax
  const char *v67; // rax
  struct tagLOG_PARTIAL_MSG *v68; // rax
  UnBCL::String *v69; // rax
  const WCHAR *v70; // rax
  NTSTATUS v71; // esi
  DWORD v72; // edi
  __int64 v73; // rbx
  const char *v74; // r9
  struct tagLOG_PARTIAL_MSG *v75; // rax
  struct tagLOG_PARTIAL_MSG *v76; // rax
  DWORD v77; // edi
  __int64 v78; // rbx
  struct tagLOG_PARTIAL_MSG *v79; // rax
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  DWORD v83; // edi
  __int64 v84; // rbx
  struct tagLOG_PARTIAL_MSG *v85; // rax
  DWORD v86; // edi
  __int64 v87; // rbx
  const char *v88; // rax
  struct tagLOG_PARTIAL_MSG *v89; // rax
  DWORD v90; // edi
  __int64 v91; // rbx
  struct tagLOG_PARTIAL_MSG *v92; // rax
  LSTATUS Key; // ebx
  signed int v94; // eax
  unsigned int v95; // esi
  DWORD v96; // edi
  __int64 v97; // rbx
  struct tagLOG_PARTIAL_MSG *v98; // rax
  bool v99; // zf
  signed int v100; // edi
  __int64 v101; // rbx
  struct tagLOG_PARTIAL_MSG *v102; // rax
  LSTATUS v103; // ebx
  signed int v104; // eax
  unsigned int v105; // esi
  DWORD v106; // edi
  __int64 v107; // rbx
  struct tagLOG_PARTIAL_MSG *v108; // rax
  NTSTATUS v109; // eax
  int v110; // esi
  DWORD v111; // edi
  __int64 v112; // rbx
  struct tagLOG_PARTIAL_MSG *v113; // rax
  int v114; // [rsp+60h] [rbp-A0h]
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER MaxiumSize; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwDisposition[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v119[16]; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER InitialSize; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v121[16]; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v123[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v124; // [rsp+D8h] [rbp-28h]
  _BYTE v125[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v126[88]; // [rsp+F8h] [rbp-8h] BYREF

  v124 = -2;
  *(_QWORD *)Data = 0;
  hKey[0] = 0;
  v4 = *((_QWORD *)this + 29);
  v5 = *((_QWORD *)this + 28);
  *(_QWORD *)dwDisposition = (char *)this + 208;
  v6 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 208);
  CString = UnBCL::String::get_CString(v6);
  v8 = pDeterminePageFileRequirements(CString, v5, v4, (struct UnBCL::String **)Data, (unsigned __int64 *)hKey);
  v114 = v8;
  if ( v8 < 0 )
  {
    LastError = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(
            0x2000000u,
            "CEnableSafeOSPageFile::DoExecute: Failed to determine page file requirements: 0x%08x",
            v8);
    WdsSetupLogMessageW(
      v11,
      819200,
      L"D",
      0,
      678,
      L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
      L"CEnableSafeOSPageFile::DoExecute",
      v10,
      LastError,
      0,
      0);
    if ( *((_DWORD *)this + 9) )
      return 0;
    return (unsigned int)v8;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v123, *(_QWORD *)Data);
  InitialSize = (LARGE_INTEGER)hKey[0];
  MaxiumSize = (LARGE_INTEGER)hKey[0];
  v8 = 0;
  if ( !UnBCL::File::Exists(*(const struct UnBCL::String **)Data) )
  {
    if ( *((_DWORD *)this + 9) )
    {
      v44 = GetLastError();
      v45 = CurrentIP();
      v46 = ConstructPartialMsgW(
              0x4000000u,
              "PAGEFILE: There is no existing pagefile, and there was no hard requirement for pagefile.");
      WdsSetupLogMessageW(
        v46,
        819200,
        L"D",
        0,
        716,
        L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
        L"CEnableSafeOSPageFile::DoExecute",
        v45,
        v44,
        0,
        0);
LABEL_56:
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v123);
      return (unsigned int)v8;
    }
LABEL_18:
    if ( UnBCL::File::Exists(*(const struct UnBCL::String **)Data) )
    {
      v28 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v125, L"WINDOWS");
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*(_QWORD *)dwDisposition);
      v30 = UnBCL::Path::Combine(P, v28);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v121, v30);
      UnBCL::String::~String((UnBCL::String *)v125);
      v31 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v121);
      if ( UnBCL::Directory::Exists(v31) )
      {
        v32 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v126, L"MEMORY.DMP");
        v33 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v121);
        v34 = UnBCL::Path::Combine(v33, v32);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(hKey, v34);
        UnBCL::String::~String((UnBCL::String *)v126);
        v35 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(hKey);
        v36 = UnBCL::String::get_CString(v35);
        v37 = UnBCL::String::get_CString(*(UnBCL::String **)Data);
        CrashDumpFromPageFile = ExtractCrashDumpFromPageFile(v37, v36, 0, 0);
        v114 = CrashDumpFromPageFile;
        if ( CrashDumpFromPageFile < 0 )
        {
          v53 = GetLastError();
          v54 = CurrentIP();
          v55 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)Data);
          v56 = ConstructPartialMsgW(
                  0x3000000u,
                  "CEnableSafeOSPageFile::DoExecute: Failed to extract crash dump from %s: 0x%08x",
                  v55,
                  CrashDumpFromPageFile);
          WdsSetupLogMessageW(
            v56,
            819200,
            L"D",
            0,
            749,
            L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
            L"CEnableSafeOSPageFile::DoExecute",
            v54,
            v53,
            0,
            0);
          v114 = 0;
        }
        else
        {
          v39 = GetLastError();
          if ( CrashDumpFromPageFile == 1 )
          {
            v40 = v39;
            v41 = CurrentIP();
            v42 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)Data);
            v43 = ConstructPartialMsgW(0x4000000u, "PAGEFILE: Did not find memory dump in %s", v42);
            WdsSetupLogMessageW(
              v43,
              819200,
              L"D",
              0,
              740,
              L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
              L"CEnableSafeOSPageFile::DoExecute",
              v41,
              v40,
              0,
              0);
          }
          else
          {
            v47 = v39;
            v48 = CurrentIP();
            v49 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)Data);
            v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(hKey);
            v51 = (const char *)UnBCL::String::get_CString(v50);
            v52 = ConstructPartialMsgW(0x4000000u, "PAGEFILE: Extracted %s from %s", v51, v49);
            WdsSetupLogMessageW(
              v52,
              819200,
              L"D",
              0,
              744,
              L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
              L"CEnableSafeOSPageFile::DoExecute",
              v48,
              v47,
              0,
              0);
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(hKey);
      }
      else
      {
        v57 = GetLastError();
        v58 = CurrentIP();
        v59 = ConstructPartialMsgW(
                0x3000000u,
                "PAGEFILE: Could not find offline Windows directory; skipping MEMORY.DMP extraction");
        WdsSetupLogMessageW(
          v59,
          819200,
          L"D",
          0,
          755,
          L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
          L"CEnableSafeOSPageFile::DoExecute",
          v58,
          v57,
          0,
          0);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v121);
    }
    v60 = UnBCL::String::get_CString(*(UnBCL::String **)Data);
    v61 = UnBCL::String::Format(L"\\??\\%s", v60);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v119, v61);
    v62 = GetLastError();
    v63 = CurrentIP();
    v64 = MaxiumSize;
    v65 = InitialSize;
    v66 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v119);
    v67 = (const char *)UnBCL::String::get_CString(v66);
    v68 = ConstructPartialMsgW(
            0x4000000u,
            "PAGEFILE: Creating page file %s, min size %llu, max size %llu",
            v67,
            v65.QuadPart,
            v64.QuadPart);
    WdsSetupLogMessageW(
      v68,
      819200,
      L"D",
      0,
      772,
      L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
      L"CEnableSafeOSPageFile::DoExecute",
      v63,
      v62,
      0,
      0);
    DestinationString = 0;
    v69 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v119);
    v70 = UnBCL::String::get_CString(v69);
    RtlInitUnicodeString(&DestinationString, v70);
    v71 = NtCreatePagingFile(&DestinationString, &InitialSize, &MaxiumSize, 0);
    if ( (unsigned int)(v71 + 1073741584) <= 1 )
    {
      v86 = GetLastError();
      v87 = CurrentIP();
      v88 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)Data);
      v89 = ConstructPartialMsgW(
              0x3000000u,
              "PAGEFILE: The page file at %s was already active and big enough (status: 0x%08x), no further action needed",
              v88,
              v71);
      WdsSetupLogMessageW(
        v89,
        819200,
        L"D",
        0,
        798,
        L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
        L"CEnableSafeOSPageFile::DoExecute",
        v87,
        v86,
        0,
        0);
    }
    else
    {
      v72 = GetLastError();
      v73 = CurrentIP();
      v74 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)Data);
      if ( v71 < 0 )
      {
        v76 = ConstructPartialMsgW(
                0x3000000u,
                "CEnableSafeOSPageFile::DoExecute: NtCreatePagingFile failed to create a %llu byte page file at %s: 0x%08x",
                MaxiumSize.QuadPart,
                v74,
                v71);
        WdsSetupLogMessageW(
          v76,
          819200,
          L"D",
          0,
          812,
          L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
          L"CEnableSafeOSPageFile::DoExecute",
          v73,
          v72,
          0,
          0);
        if ( !*((_DWORD *)this + 9) )
        {
          v77 = GetLastError();
          v78 = CurrentIP();
          v79 = ConstructPartialMsgW(
                  0x2000000u,
                  "CEnableSafeOSPageFile::DoExecute: Page file space was a hard requirement, cannot continue setup");
          WdsSetupLogMessageW(
            v79,
            819200,
            L"D",
            0,
            816,
            L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
            L"CEnableSafeOSPageFile::DoExecute",
            v78,
            v77,
            0,
            0);
          v8 = v71 | 0x10000000;
LABEL_55:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v119);
          goto LABEL_56;
        }
        v80 = GetLastError();
        v81 = CurrentIP();
        v82 = ConstructPartialMsgW(0x3000000u, "PAGEFILE: Page file space only needed to capture kernel crash dumps");
        WdsSetupLogMessageW(
          v82,
          819200,
          L"D",
          0,
          821,
          L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
          L"CEnableSafeOSPageFile::DoExecute",
          v81,
          v80,
          0,
          0);
        v83 = GetLastError();
        v84 = CurrentIP();
        v85 = ConstructPartialMsgW(
                0x3000000u,
                "PAGEFILE: Will continue, but kernel-mode crash dumps may not be captured");
        WdsSetupLogMessageW(
          v85,
          819200,
          L"D",
          0,
          822,
          L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
          L"CEnableSafeOSPageFile::DoExecute",
          v84,
          v83,
          0,
          0);
      }
      else
      {
        v75 = ConstructPartialMsgW(
                0x4000000u,
                "PAGEFILE: Initialized a %llu byte page file at %s",
                MaxiumSize.QuadPart,
                v74);
        WdsSetupLogMessageW(
          v75,
          819200,
          L"D",
          0,
          803,
          L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
          L"CEnableSafeOSPageFile::DoExecute",
          v73,
          v72,
          0,
          0);
      }
    }
    *((_DWORD *)this + 9) = 1;
    v90 = GetLastError();
    v91 = CurrentIP();
    v92 = ConstructPartialMsgW(0x4000000u, "PAGEFILE: Setting dump type to %d", *((_DWORD *)this + 60));
    WdsSetupLogMessageW(
      v92,
      819200,
      L"D",
      0,
      833,
      L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
      L"CEnableSafeOSPageFile::DoExecute",
      v91,
      v90,
      0,
      0);
    *(_DWORD *)Data = *((_DWORD *)this + 60);
    hKey[0] = 0;
    dwDisposition[0] = 0;
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
            0,
            (LPWSTR)&Class,
            0,
            0x20006u,
            0,
            hKey,
            dwDisposition);
    if ( !Key )
    {
      Key = RegSetValueExW(hKey[0], L"CrashDumpEnabled", 0, 4u, Data, 4u);
      RegCloseKey(hKey[0]);
    }
    SetLastError(Key);
    v94 = GetLastError();
    if ( Key )
    {
      v95 = v94;
      v114 = v94;
      if ( v94 > 0 )
      {
        v95 = (unsigned __int16)v94 | 0x80070000;
        v114 = v95;
      }
      v96 = GetLastError();
      v97 = CurrentIP();
      v98 = ConstructPartialMsgW(
              0x2000000u,
              "CEnableSafeOSPageFile::DoExecute: Cannot set %s [%s] value to full dump type: 0x%08x",
              (const char *)L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
              (const char *)L"CrashDumpEnabled",
              v95);
      WdsSetupLogMessageW(
        v98,
        819200,
        L"D",
        0,
        843,
        L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
        L"CEnableSafeOSPageFile::DoExecute",
        v97,
        v96,
        0,
        0);
    }
    else
    {
      v100 = v94;
      v101 = CurrentIP();
      v102 = ConstructPartialMsgW(0x4000000u, "PAGEFILE: Setting FilterPages to %d", *((_DWORD *)this + 61));
      WdsSetupLogMessageW(
        v102,
        819200,
        L"D",
        0,
        847,
        L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
        L"CEnableSafeOSPageFile::DoExecute",
        v101,
        v100,
        0,
        0);
      dwDisposition[0] = *((_DWORD *)this + 61);
      hKey[0] = 0;
      *(_DWORD *)Data = 0;
      v103 = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
               0,
               (LPWSTR)&Class,
               0,
               0x20006u,
               0,
               hKey,
               (LPDWORD)Data);
      if ( !v103 )
      {
        v103 = RegSetValueExW(hKey[0], L"FilterPages", 0, 4u, (const BYTE *)dwDisposition, 4u);
        RegCloseKey(hKey[0]);
      }
      SetLastError(v103);
      if ( !v103 )
      {
        v109 = NtSetSystemInformation(SystemCrashDumpStateInformation, 0, 0);
        if ( v109 < 0 )
        {
          v110 = v109 | 0x10000000;
          v114 = v109 | 0x10000000;
          v111 = GetLastError();
          v112 = CurrentIP();
          v113 = ConstructPartialMsgW(
                   0x2000000u,
                   "CEnableSafeOSPageFile::DoExecute: Failed to set NtSetSystemInformation for full memory dump: 0x%08x",
                   v110);
          WdsSetupLogMessageW(
            v113,
            819200,
            L"D",
            0,
            865,
            L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
            L"CEnableSafeOSPageFile::DoExecute",
            v112,
            v111,
            0,
            0);
        }
        v8 = 0;
        v99 = *((_DWORD *)this + 9) == 0;
        goto LABEL_53;
      }
      v104 = GetLastError();
      v105 = v104;
      v114 = v104;
      if ( v104 > 0 )
      {
        v105 = (unsigned __int16)v104 | 0x80070000;
        v114 = v105;
      }
      v106 = GetLastError();
      v107 = CurrentIP();
      v108 = ConstructPartialMsgW(
               0x2000000u,
               "CEnableSafeOSPageFile::DoExecute: Cannot set %s [%s] value to filterpages to 1: 0x%08x",
               (const char *)L"SYSTEM\\CurrentControlSet\\Control\\CrashControl",
               (const char *)L"CrashDumpEnabled",
               v105);
      WdsSetupLogMessageW(
        v108,
        819200,
        L"D",
        0,
        857,
        L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
        L"CEnableSafeOSPageFile::DoExecute",
        v107,
        v106,
        0,
        0);
    }
    v8 = 0;
    v99 = *((_DWORD *)this + 9) == 0;
LABEL_53:
    if ( v99 )
      v8 = v114;
    goto LABEL_55;
  }
  v12 = UnBCL::String::get_CString(*(UnBCL::String **)Data);
  v13.QuadPart = SPGetFileSize(v12);
  v14 = v13;
  if ( v13.QuadPart )
  {
    if ( v13.QuadPart >= (unsigned __int64)MaxiumSize.QuadPart )
    {
      v25 = GetLastError();
      v26 = CurrentIP();
      v27 = ConstructPartialMsgW(
              0x4000000u,
              "PAGEFILE: Existing page file is already %llu, extending maximum size",
              v14.QuadPart);
      WdsSetupLogMessageW(
        v27,
        819200,
        L"D",
        0,
        700,
        L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
        L"CEnableSafeOSPageFile::DoExecute",
        v26,
        v25,
        0,
        0);
      MaxiumSize = v14;
    }
    goto LABEL_18;
  }
  v15 = GetLastError();
  v16 = v15 < 0;
  if ( v15 > 0 )
    v16 = 1;
  if ( v16 )
  {
    v17 = GetLastError();
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    v18 = -2147467259;
  }
  v19 = GetLastError();
  v20 = CurrentIP();
  v21 = (const char *)UnBCL::String::get_CString(*(UnBCL::String **)Data);
  v22 = ConstructPartialMsgW(
          0x2000000u,
          "CEnableSafeOSPageFile::DoExecute: Failed to get size of existing page file %s: 0x%08x",
          v21,
          v18);
  WdsSetupLogMessageW(
    v22,
    819200,
    L"D",
    0,
    694,
    L"base\\ntsetup\\setupplatform\\lib\\src\\pagefile.cpp",
    L"CEnableSafeOSPageFile::DoExecute",
    v20,
    v19,
    0,
    0);
  v23 = 0;
  if ( !*((_DWORD *)this + 9) )
    v23 = v18;
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v123);
  return v23;
}

```

## disassembly

```asm
0x18019a150  mov     [rsp-8+arg_0], rcx
0x18019a155  push    rbp
0x18019a156  push    rbx
0x18019a157  push    rsi
0x18019a158  push    rdi
0x18019a159  push    r12
0x18019a15b  push    r13
0x18019a15d  push    r14
0x18019a15f  push    r15
0x18019a161  lea     rbp, [rsp-18h]
0x18019a166  sub     rsp, 118h
0x18019a16d  mov     [rbp+50h+var_78], 0FFFFFFFFFFFFFFFEh
0x18019a175  xor     r14d, r14d
0x18019a178  mov     qword ptr [rsp+150h+Data], r14
0x18019a17d  mov     [rsp+150h+hKey], r14
0x18019a182  mov     rbx, [rcx+0E8h]
0x18019a189  mov     rdi, [rcx+0E0h]
0x18019a190  lea     rax, [rcx+0D0h]
0x18019a197  mov     qword ptr [rbp+50h+dwDisposition], rax
0x18019a19b  mov     rcx, rax
0x18019a19e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18019a1a4  mov     rcx, rax
0x18019a1a7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a1ad  lea     rcx, [rsp+150h+hKey]
0x18019a1b2  mov     qword ptr [rsp+150h+dwOptions], rcx; unsigned __int64 *
0x18019a1b7  lea     r9, [rsp+150h+Data]; struct UnBCL::String **
0x18019a1bc  mov     r8, rbx; unsigned __int64
0x18019a1bf  mov     rdx, rdi; unsigned __int64
0x18019a1c2  mov     rcx, rax; unsigned __int16 *
0x18019a1c5  call    ?pDeterminePageFileRequirements@@YAJPEBG_K1PEAPEAVString@UnBCL@@PEA_K@Z; pDeterminePageFileRequirements(ushort const *,unsigned __int64,unsigned __int64,UnBCL::String * *,unsigned __int64 *)
0x18019a1ca  mov     esi, eax
0x18019a1cc  mov     [rsp+150h+var_F0], eax
0x18019a1d0  test    eax, eax
0x18019a1d2  jns     loc_18019A259
0x18019a1d8  call    cs:__imp_GetLastError
0x18019a1de  mov     edi, eax
0x18019a1e0  call    cs:__imp_CurrentIP
0x18019a1e6  mov     rbx, rax
0x18019a1e9  mov     r8d, esi
0x18019a1ec  lea     rdx, aCenablesafeosp_2; "CEnableSafeOSPageFile::DoExecute: Faile"...
0x18019a1f3  mov     ecx, 2000000h; unsigned int
0x18019a1f8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a1fd  mov     [rsp+150h+var_100], r14d
0x18019a202  mov     [rsp+150h+var_108], r14
0x18019a207  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x18019a20b  mov     [rsp+150h+phkResult], rbx
0x18019a210  lea     r13, aCenablesafeosp_4; "CEnableSafeOSPageFile::DoExecute"
0x18019a217  mov     [rsp+150h+lpSecurityAttributes], r13
0x18019a21c  lea     r14, aBaseNtsetupSet_23; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18019a223  mov     qword ptr [rsp+150h+samDesired], r14
0x18019a228  mov     [rsp+150h+dwOptions], 2A6h
0x18019a230  xor     r9d, r9d
0x18019a233  lea     r8, aD_0; "D"
0x18019a23a  mov     edx, 0C8000h
0x18019a23f  mov     rcx, rax
0x18019a242  call    cs:__imp_WdsSetupLogMessageW
0x18019a248  xor     eax, eax
0x18019a24a  mov     rcx, [rbp+50h+arg_0]
0x18019a24e  cmp     [rcx+24h], eax
0x18019a251  cmovnz  esi, eax
0x18019a254  jmp     loc_18019AE3F
0x18019a259  mov     rdx, qword ptr [rsp+150h+Data]
0x18019a25e  lea     rcx, [rbp+50h+var_88]
0x18019a262  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18019a268  nop
0x18019a269  mov     rax, [rsp+150h+hKey]
0x18019a26e  mov     qword ptr [rbp+50h+InitialSize], rax
0x18019a272  mov     qword ptr [rbp+50h+MaxiumSize], rax
0x18019a276  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a27b  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x18019a281  lea     r13, aCenablesafeosp_4; "CEnableSafeOSPageFile::DoExecute"
0x18019a288  lea     r14, aBaseNtsetupSet_23; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18019a28f  lea     r15, aD_0; "D"
0x18019a296  xor     esi, esi
0x18019a298  mov     r12d, 0C8000h
0x18019a29e  test    eax, eax
0x18019a2a0  jz      loc_18019A551
0x18019a2a6  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a2ab  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a2b1  mov     rcx, rax; lpFileName
0x18019a2b4  call    ?SPGetFileSize@@YA_KPEBG@Z; SPGetFileSize(ushort const *)
0x18019a2b9  mov     rsi, rax
0x18019a2bc  test    rax, rax
0x18019a2bf  jnz     loc_18019A384
0x18019a2c5  call    cs:__imp_GetLastError
0x18019a2cb  mov     ebx, 80070000h
0x18019a2d0  test    eax, eax
0x18019a2d2  jle     short loc_18019A2DB
0x18019a2d4  movzx   eax, ax
0x18019a2d7  or      eax, ebx
0x18019a2d9  test    eax, eax
0x18019a2db  jns     short loc_18019A2F0
0x18019a2dd  call    cs:__imp_GetLastError
0x18019a2e3  mov     esi, eax
0x18019a2e5  test    eax, eax
0x18019a2e7  jle     short loc_18019A2F5
0x18019a2e9  movzx   esi, ax
0x18019a2ec  or      esi, ebx
0x18019a2ee  jmp     short loc_18019A2F5
0x18019a2f0  mov     esi, 80004005h
0x18019a2f5  call    cs:__imp_GetLastError
0x18019a2fb  mov     edi, eax
0x18019a2fd  call    cs:__imp_CurrentIP
0x18019a303  mov     rbx, rax
0x18019a306  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a30b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a311  mov     r8, rax
0x18019a314  mov     r9d, esi
0x18019a317  lea     rdx, aCenablesafeosp_8; "CEnableSafeOSPageFile::DoExecute: Faile"...
0x18019a31e  mov     ecx, 2000000h; unsigned int
0x18019a323  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a328  mov     [rsp+150h+var_100], 0
0x18019a330  mov     [rsp+150h+var_108], 0
0x18019a339  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x18019a33d  mov     [rsp+150h+phkResult], rbx
0x18019a342  mov     [rsp+150h+lpSecurityAttributes], r13
0x18019a347  mov     qword ptr [rsp+150h+samDesired], r14
0x18019a34c  mov     [rsp+150h+dwOptions], 2B6h
0x18019a354  xor     r9d, r9d
0x18019a357  mov     r8, r15
0x18019a35a  mov     edx, r12d
0x18019a35d  mov     rcx, rax
0x18019a360  call    cs:__imp_WdsSetupLogMessageW
0x18019a366  nop
0x18019a367  xor     ebx, ebx
0x18019a369  mov     rcx, [rbp+50h+arg_0]
0x18019a36d  cmp     [rcx+24h], ebx
0x18019a370  cmovz   ebx, esi
0x18019a373  lea     rcx, [rbp+50h+var_88]
0x18019a377  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18019a37d  mov     eax, ebx
0x18019a37f  jmp     loc_18019AE41
0x18019a384  cmp     rsi, qword ptr [rbp+50h+MaxiumSize]
0x18019a388  jb      short loc_18019A3F1
0x18019a38a  call    cs:__imp_GetLastError
0x18019a390  mov     edi, eax
0x18019a392  call    cs:__imp_CurrentIP
0x18019a398  mov     rbx, rax
0x18019a39b  mov     r8, rsi
0x18019a39e  lea     rdx, aPagefileExisti; "PAGEFILE: Existing page file is already"...
0x18019a3a5  mov     ecx, 4000000h; unsigned int
0x18019a3aa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a3af  mov     [rsp+150h+var_100], 0
0x18019a3b7  mov     [rsp+150h+var_108], 0
0x18019a3c0  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x18019a3c4  mov     [rsp+150h+phkResult], rbx
0x18019a3c9  mov     [rsp+150h+lpSecurityAttributes], r13
0x18019a3ce  mov     qword ptr [rsp+150h+samDesired], r14
0x18019a3d3  mov     [rsp+150h+dwOptions], 2BCh
0x18019a3db  xor     r9d, r9d
0x18019a3de  mov     r8, r15
0x18019a3e1  mov     edx, r12d
0x18019a3e4  mov     rcx, rax
0x18019a3e7  call    cs:__imp_WdsSetupLogMessageW
0x18019a3ed  mov     qword ptr [rbp+50h+MaxiumSize], rsi
0x18019a3f1  xor     esi, esi
0x18019a3f3  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a3f8  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x18019a3fe  test    eax, eax
0x18019a400  jz      loc_18019A71E
0x18019a406  lea     rdx, aWindows_4; "WINDOWS"
0x18019a40d  lea     rcx, [rbp+50h+var_70]
0x18019a411  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18019a417  mov     rbx, rax
0x18019a41a  mov     rcx, qword ptr [rbp+50h+dwDisposition]
0x18019a41e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18019a424  mov     rdx, rbx
0x18019a427  mov     rcx, rax
0x18019a42a  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18019a430  mov     rdx, rax
0x18019a433  lea     rcx, [rbp+50h+var_A8]
0x18019a437  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18019a43d  nop
0x18019a43e  lea     rcx, [rbp+50h+var_70]
0x18019a442  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18019a448  lea     rcx, [rbp+50h+var_A8]
0x18019a44c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18019a452  mov     rcx, rax
0x18019a455  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18019a45b  test    eax, eax
0x18019a45d  jz      loc_18019A6BB
0x18019a463  lea     rdx, aMemoryDmp_0; "MEMORY.DMP"
0x18019a46a  lea     rcx, [rbp+50h+var_58]
0x18019a46e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18019a474  mov     rbx, rax
0x18019a477  lea     rcx, [rbp+50h+var_A8]
0x18019a47b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18019a481  mov     rdx, rbx
0x18019a484  mov     rcx, rax
0x18019a487  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18019a48d  mov     rdx, rax
0x18019a490  lea     rcx, [rsp+150h+hKey]
0x18019a495  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18019a49b  nop
0x18019a49c  lea     rcx, [rbp+50h+var_58]
0x18019a4a0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18019a4a6  lea     rcx, [rsp+150h+hKey]
0x18019a4ab  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18019a4b1  mov     rcx, rax
0x18019a4b4  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a4ba  mov     rbx, rax
0x18019a4bd  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a4c2  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a4c8  xor     r9d, r9d
0x18019a4cb  xor     r8d, r8d
0x18019a4ce  mov     rdx, rbx
0x18019a4d1  mov     rcx, rax
0x18019a4d4  call    ExtractCrashDumpFromPageFile
0x18019a4d9  mov     esi, eax
0x18019a4db  mov     [rsp+150h+var_F0], eax
0x18019a4df  test    eax, eax
0x18019a4e1  js      loc_18019A63F
0x18019a4e7  call    cs:__imp_GetLastError
0x18019a4ed  cmp     esi, 1
0x18019a4f0  jnz     loc_18019A5BB
0x18019a4f6  mov     edi, eax
0x18019a4f8  call    cs:__imp_CurrentIP
0x18019a4fe  mov     rbx, rax
0x18019a501  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a506  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a50c  mov     r8, rax
0x18019a50f  lea     rdx, aPagefileDidNot; "PAGEFILE: Did not find memory dump in %"...
0x18019a516  mov     ecx, 4000000h; unsigned int
0x18019a51b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a520  mov     [rsp+150h+var_100], 0
0x18019a528  mov     [rsp+150h+var_108], 0
0x18019a531  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x18019a535  mov     [rsp+150h+phkResult], rbx
0x18019a53a  mov     [rsp+150h+lpSecurityAttributes], r13
0x18019a53f  mov     qword ptr [rsp+150h+samDesired], r14
0x18019a544  mov     [rsp+150h+dwOptions], 2E4h
0x18019a54c  jmp     loc_18019A62B
0x18019a551  mov     rcx, [rbp+50h+arg_0]
0x18019a555  cmp     [rcx+24h], esi
0x18019a558  jz      loc_18019A3F3
0x18019a55e  call    cs:__imp_GetLastError
0x18019a564  mov     edi, eax
0x18019a566  call    cs:__imp_CurrentIP
0x18019a56c  mov     rbx, rax
0x18019a56f  lea     rdx, aPagefileThereI; "PAGEFILE: There is no existing pagefile"...
0x18019a576  mov     ecx, 4000000h; unsigned int
0x18019a57b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a580  mov     [rsp+150h+var_100], esi
0x18019a584  mov     [rsp+150h+var_108], rsi
0x18019a589  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x18019a58d  mov     [rsp+150h+phkResult], rbx
0x18019a592  mov     [rsp+150h+lpSecurityAttributes], r13
0x18019a597  mov     qword ptr [rsp+150h+samDesired], r14
0x18019a59c  mov     [rsp+150h+dwOptions], 2CCh
0x18019a5a4  xor     r9d, r9d
0x18019a5a7  mov     r8, r15
0x18019a5aa  mov     edx, r12d
0x18019a5ad  mov     rcx, rax
0x18019a5b0  call    cs:__imp_WdsSetupLogMessageW
0x18019a5b6  jmp     loc_18019AE35
0x18019a5bb  mov     esi, eax
0x18019a5bd  call    cs:__imp_CurrentIP
0x18019a5c3  mov     rdi, rax
0x18019a5c6  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a5cb  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a5d1  mov     rbx, rax
0x18019a5d4  lea     rcx, [rsp+150h+hKey]
0x18019a5d9  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18019a5df  mov     rcx, rax
0x18019a5e2  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a5e8  mov     r9, rbx
0x18019a5eb  mov     r8, rax
0x18019a5ee  lea     rdx, aPagefileExtrac; "PAGEFILE: Extracted %s from %s"
0x18019a5f5  mov     ecx, 4000000h; unsigned int
0x18019a5fa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a5ff  mov     [rsp+150h+var_100], 0
0x18019a607  mov     [rsp+150h+var_108], 0
0x18019a610  mov     dword ptr [rsp+150h+lpdwDisposition], esi
0x18019a614  mov     [rsp+150h+phkResult], rdi
0x18019a619  mov     [rsp+150h+lpSecurityAttributes], r13
0x18019a61e  mov     qword ptr [rsp+150h+samDesired], r14
0x18019a623  mov     [rsp+150h+dwOptions], 2E8h
0x18019a62b  xor     r9d, r9d
0x18019a62e  mov     r8, r15
0x18019a631  mov     edx, r12d
0x18019a634  mov     rcx, rax
0x18019a637  call    cs:__imp_WdsSetupLogMessageW
0x18019a63d  jmp     short loc_18019A6AE
0x18019a63f  call    cs:__imp_GetLastError
0x18019a645  mov     edi, eax
0x18019a647  call    cs:__imp_CurrentIP
0x18019a64d  mov     rbx, rax
0x18019a650  mov     rcx, qword ptr [rsp+150h+Data]
0x18019a655  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019a65b  mov     r8, rax
0x18019a65e  mov     r9d, esi
0x18019a661  lea     rdx, aCenablesafeosp_0; "CEnableSafeOSPageFile::DoExecute: Faile"...
0x18019a668  mov     ecx, 3000000h; unsigned int
0x18019a66d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18019a672  xor     esi, esi
0x18019a674  mov     [rsp+150h+var_100], esi
0x18019a678  mov     [rsp+150h+var_108], rsi
0x18019a67d  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x18019a681  mov     [rsp+150h+phkResult], rbx
0x18019a686  mov     [rsp+150h+lpSecurityAttributes], r13
  ... truncated ...
```
