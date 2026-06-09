# UtcUploadTelemetryData(UnBCL::String *,int,ulong,int,UnBCL::String *,UnBCL::String *,UnBCL::String *,int,int)

- ea: `0x180382b94`
- end: `0x1803834e9`
- name: `?UtcUploadTelemetryData@@YAXPEAVString@UnBCL@@HKH000HH@Z`
- size: `2389`
- prototype: `void __fastcall(struct UnBCL::String *, int, unsigned int, int, struct UnBCL::String *, struct UnBCL::String *, struct UnBCL::String *, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1803755e8`

## callees

- `0x180057dec`
- `0x180382b94`
- `0x180383af8`
- `0x180383ce8`
- `0x18040b41c`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180382f7c`
- `ADVAPI32!OpenSCManagerW` at `0x180382f7c`
- `ADVAPI32!OpenServiceW` at `0x180382f9b`
- `ADVAPI32!OpenServiceW` at `0x180382f9b`
- `ADVAPI32!CloseServiceHandle` at `0x180382fd7`
- `ADVAPI32!CloseServiceHandle` at `0x180382fe0`
- `ADVAPI32!CloseServiceHandle` at `0x180382fd7`
- `ADVAPI32!CloseServiceHandle` at `0x180382fe0`
- `ADVAPI32!QueryServiceStatusEx` at `0x180382fc0`
- `ADVAPI32!QueryServiceStatusEx` at `0x180382fc0`
- `KERNEL32!GetLastError` at `0x180382e88`
- `KERNEL32!GetLastError` at `0x180382fee`
- `KERNEL32!GetLastError` at `0x180383070`
- `KERNEL32!GetLastError` at `0x1803830eb`
- `KERNEL32!GetLastError` at `0x180383168`
- `KERNEL32!GetLastError` at `0x1803831d9`
- `KERNEL32!GetLastError` at `0x1803831ea`
- `KERNEL32!GetLastError` at `0x180383239`
- `KERNEL32!GetLastError` at `0x1803832c7`
- `KERNEL32!GetLastError` at `0x18038331e`
- `KERNEL32!GetLastError` at `0x180383403`
- `KERNEL32!GetLastError` at `0x180383414`
- `KERNEL32!GetLastError` at `0x180382e88`
- `KERNEL32!GetLastError` at `0x180382fee`
- `KERNEL32!GetLastError` at `0x180383070`
- `KERNEL32!GetLastError` at `0x1803830eb`
- `KERNEL32!GetLastError` at `0x180383168`
- `KERNEL32!GetLastError` at `0x1803831d9`
- `KERNEL32!GetLastError` at `0x1803831ea`
- `KERNEL32!GetLastError` at `0x180383239`
- `KERNEL32!GetLastError` at `0x1803832c7`
- `KERNEL32!GetLastError` at `0x18038331e`
- `KERNEL32!GetLastError` at `0x180383403`
- `KERNEL32!GetLastError` at `0x180383414`
- `KERNEL32!DeleteFileW` at `0x1803833f5`
- `KERNEL32!DeleteFileW` at `0x1803833f5`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180382d24`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180382d24`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180382dd0`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180382dd0`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180382db9`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180382db9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180382cce`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180382d65`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180382cce`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180382d65`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180382e6e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180383398`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1803833c5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180383420`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180382e6e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180383398`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1803833c5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180383420`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382e2b`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382e2b`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180382e48`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180382e48`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180382e58`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180382e58`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382e64`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803834aa`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382e64`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803834aa`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382ca6`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382ca6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180382d59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180382db0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180382dc7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180382d59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180382db0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180382dc7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382c90`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382c9b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382c90`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180382c9b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180382d04`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180382d3d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180382d9a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180382d04`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180382d3d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180382d9a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180382cc1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180382d1a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180382d4b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180382cc1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180382d1a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180382d4b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180382e0e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180382e0e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180382cec`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180382d83`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180382cec`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180382d83`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180382dda`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180382e9d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180382dda`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180382e9d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382de3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382df5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382ea6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382eb2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382f34`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803833ec`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180383447`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382de3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382df5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382ea6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382eb2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180382f34`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803833ec`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180383447`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382cf8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382d8f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382da6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803834b5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803834c0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382cf8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382d8f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180382da6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803834b5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803834c0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180382cdc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180382d32`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180382d73`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180382cdc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180382d32`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180382d73`
- `WDSCORE!WdsSetupLogMessageW` at `0x180382f12`
- `WDSCORE!WdsSetupLogMessageW` at `0x180383052`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803830d7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180383155`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803831c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803832a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18038337e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180383498`
- `WDSCORE!WdsSetupLogMessageW` at `0x180382f12`
- `WDSCORE!WdsSetupLogMessageW` at `0x180383052`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803830d7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180383155`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803831c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803832a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18038337e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180383498`
- `WDSCORE!CurrentIP` at `0x180382e90`
- `WDSCORE!CurrentIP` at `0x180382ff6`
- `WDSCORE!CurrentIP` at `0x180383078`
- `WDSCORE!CurrentIP` at `0x1803830f3`
- `WDSCORE!CurrentIP` at `0x180383170`
- `WDSCORE!CurrentIP` at `0x1803831e1`
- `WDSCORE!CurrentIP` at `0x180383241`
- `WDSCORE!CurrentIP` at `0x1803832cf`
- `WDSCORE!CurrentIP` at `0x180383326`
- `WDSCORE!CurrentIP` at `0x18038340b`
- `WDSCORE!CurrentIP` at `0x180382e90`
- `WDSCORE!CurrentIP` at `0x180382ff6`
- `WDSCORE!CurrentIP` at `0x180383078`
- `WDSCORE!CurrentIP` at `0x1803830f3`
- `WDSCORE!CurrentIP` at `0x180383170`
- `WDSCORE!CurrentIP` at `0x1803831e1`
- `WDSCORE!CurrentIP` at `0x180383241`
- `WDSCORE!CurrentIP` at `0x1803832cf`
- `WDSCORE!CurrentIP` at `0x180383326`
- `WDSCORE!CurrentIP` at `0x18038340b`

## string_xrefs

- `0x180382ebe`: `Copy telemetry file: source folder: %s, destination folder: %s`
- `0x180383453`: `Failed to delete file: %s. Error = %d`
- `0x180382fff`: `Diagtrack service is running`
- `0x1803830ff`: `Either AlwaysRestartDiagTrack was specified, or ForceUpload failed with error code=0x%x, restarting the diagtrack service to upload the etl`
- `0x180383179`: `Restart Diagtrack service successfully`
- `0x1803831f3`: `Failed to restart Diagtrack service, error code=%d`
- `0x18038324e`: `Service %s is not available`
- `0x1803832d8`: `Delete all etl files because this is an async upload request.`
- `0x18038332f`: `Upload files successfully so we can remove all etl files.`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall UtcUploadTelemetryData(
        struct UnBCL::String *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        struct UnBCL::String *a5,
        struct UnBCL::String *a6,
        struct UnBCL::String *a7,
        int a8,
        int a9)
{
  int v11; // r14d
  int v12; // r12d
  const struct UnBCL::String *v13; // rdx
  struct UnBCL::String *v14; // rax
  const struct UnBCL::String *v15; // rcx
  struct UnBCL::String *v16; // rax
  const struct UnBCL::String *v17; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v19; // rax
  const struct UnBCL::String *v20; // rax
  const struct UnBCL::String *v21; // rax
  UnBCL::String *v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rbx
  __int64 v25; // rax
  DWORD LastError; // esi
  __int64 v27; // rdi
  UnBCL::String *v28; // rax
  const char *v29; // rbx
  const char *v30; // rax
  struct tagLOG_PARTIAL_MSG *v31; // rax
  BOOL v32; // ebx
  const WCHAR *v33; // rax
  SC_HANDLE v34; // rax
  SC_HANDLE v35; // rsi
  SC_HANDLE v36; // rdi
  DWORD v37; // edi
  __int64 v38; // rbx
  struct tagLOG_PARTIAL_MSG *v39; // rax
  int v40; // esi
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  DWORD v50; // edi
  __int64 v51; // rbx
  DWORD v52; // eax
  struct tagLOG_PARTIAL_MSG *v53; // rax
  DWORD v54; // edi
  __int64 v55; // rbx
  struct tagLOG_PARTIAL_MSG *v56; // rax
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  DWORD v60; // edi
  __int64 v61; // rbx
  struct tagLOG_PARTIAL_MSG *v62; // rax
  unsigned int i; // r14d
  __int64 v64; // rax
  unsigned int (__fastcall ***v65)(_QWORD); // rcx
  __int64 v66; // rax
  __int64 v67; // rcx
  UnBCL::String **v68; // rax
  const WCHAR *v69; // rax
  DWORD v70; // esi
  __int64 v71; // rdi
  DWORD v72; // ebx
  __int64 v73; // rax
  __int64 v74; // rcx
  UnBCL::String **v75; // rax
  const char *v76; // rax
  struct tagLOG_PARTIAL_MSG *v77; // rax
  DWORD pcbBytesNeeded[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v79[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v80[16]; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *CString; // [rsp+98h] [rbp-68h] BYREF
  const unsigned __int16 *v82; // [rsp+A0h] [rbp-60h]
  _BYTE v83[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h]
  _BYTE v85[16]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE v86[24]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Buffer[16]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v88; // [rsp+F8h] [rbp-8h]
  int v89; // [rsp+108h] [rbp+8h]
  WCHAR ServiceName[16]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v91[20]; // [rsp+130h] [rbp+30h] BYREF

  v84 = -2;
  v91[0] = 7471184;
  v91[1] = 6750319;
  v91[2] = 6357106;
  v91[3] = 4456557;
  v91[4] = 7602273;
  v91[5] = 6029409;
  v91[6] = 6881357;
  v91[7] = 7471203;
  v91[8] = 7536751;
  v91[9] = 6684783;
  v91[10] = 6029428;
  v91[11] = 6881348;
  v91[12] = 6750305;
  v91[13] = 7274606;
  v91[14] = 6881395;
  v91[15] = 6029427;
  v91[16] = 5505093;
  v91[17] = 4980812;
  v91[18] = 6750319;
  v91[19] = 115;
  wcscpy(ServiceName, L"DiagTrack");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v85);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v80);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v83);
  v11 = 0;
  v12 = 0;
  if ( a7 )
  {
    v13 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v79, (const unsigned __int16 *)v91);
    v14 = UnBCL::Path::Combine(a7, v13);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(pcbBytesNeeded, v14);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v80, pcbBytesNeeded);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(pcbBytesNeeded);
    UnBCL::String::~String((UnBCL::String *)v79);
  }
  else
  {
    v15 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v86, L"%systemdrive%");
    v16 = UnBCL::Environment::ExpandEnvironmentVariables(v15);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v79, v16);
    UnBCL::String::~String((UnBCL::String *)v86);
    v17 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)Buffer, (const unsigned __int16 *)v91);
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v79);
    v19 = UnBCL::Path::Combine(P, v17);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(pcbBytesNeeded, v19);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v80, pcbBytesNeeded);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(pcbBytesNeeded);
    UnBCL::String::~String((UnBCL::String *)Buffer);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v79);
  }
  v20 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v80);
  if ( !UnBCL::Directory::Exists(v20) )
  {
    v21 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v80);
    UnBCL::Directory::CreateDir(v21);
  }
  v22 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v80);
  CString = UnBCL::String::get_CString(v22);
  if ( a5 )
    v82 = UnBCL::String::get_CString(a5);
  else
    v82 = 0;
  v23 = UnBCL::Object::operator new(0xB0u);
  v24 = v23;
  *(_QWORD *)pcbBytesNeeded = v23;
  if ( v23 )
  {
    UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v23, 1);
    v24[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
  }
  else
  {
    v24 = 0;
  }
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v79, v24);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v83, v79);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v79);
  v25 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v83);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 40LL))(v25, 1);
  LastError = GetLastError();
  v27 = CurrentIP();
  v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v80);
  v29 = (const char *)UnBCL::String::get_CString(v28);
  v30 = (const char *)UnBCL::String::get_CString(a1);
  v31 = ConstructPartialMsgW(0x4000000u, "Copy telemetry file: source folder: %s, destination folder: %s", v30, v29);
  v32 = 0;
  WdsSetupLogMessageW(
    v31,
    0,
    L"D",
    0,
    383,
    L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
    L"UtcUploadTelemetryData",
    v27,
    LastError,
    0,
    0);
  v79[0] = 0;
  v79[1] = &CString;
  v79[2] = pCopyTelemetryFile;
  v33 = UnBCL::String::get_CString(a1);
  EnumeratePathEx(v33, 0);
  *(_OWORD *)Buffer = 0;
  v88 = 0;
  v89 = 0;
  pcbBytesNeeded[0] = 0;
  v34 = OpenSCManagerW(0, 0, 0xF003Fu);
  v35 = v34;
  if ( v34 )
  {
    v36 = OpenServiceW(v34, ServiceName, 0x80000000);
    if ( v36 )
    {
      if ( QueryServiceStatusEx(v36, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, pcbBytesNeeded) )
        v32 = *(_DWORD *)&Buffer[4] == 4;
      CloseServiceHandle(v36);
    }
    CloseServiceHandle(v35);
    if ( v32 )
    {
      v37 = GetLastError();
      v38 = CurrentIP();
      v39 = ConstructPartialMsgW(0x4000000u, "Diagtrack service is running");
      WdsSetupLogMessageW(
        v39,
        0,
        L"D",
        0,
        401,
        L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
        L"UtcUploadTelemetryData",
        v38,
        v37,
        0,
        0);
      if ( a9 )
      {
        v40 = 0;
      }
      else
      {
        v40 = pForceUpload();
        if ( v40 >= 0 )
        {
          v41 = GetLastError();
          v42 = CurrentIP();
          v43 = ConstructPartialMsgW(0x4000000u, "Successfully Forceuploaded the telemetry data.");
          WdsSetupLogMessageW(
            v43,
            0,
            L"D",
            0,
            410,
            L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
            L"UtcUploadTelemetryData",
            v42,
            v41,
            0,
            0);
          v12 = 1;
          goto LABEL_26;
        }
      }
      v44 = GetLastError();
      v45 = CurrentIP();
      v46 = ConstructPartialMsgW(
              0x3000000u,
              "Either AlwaysRestartDiagTrack was specified, or ForceUpload failed with error code=0x%x, restarting the di"
              "agtrack service to upload the etl",
              v40);
      WdsSetupLogMessageW(
        v46,
        0,
        L"D",
        0,
        421,
        L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
        L"UtcUploadTelemetryData",
        v45,
        v44,
        0,
        0);
      if ( (unsigned int)pRestartService(ServiceName) )
      {
        v47 = GetLastError();
        v48 = CurrentIP();
        v49 = ConstructPartialMsgW(0x4000000u, "Restart Diagtrack service successfully");
        WdsSetupLogMessageW(
          v49,
          0,
          L"D",
          0,
          425,
          L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
          L"UtcUploadTelemetryData",
          v48,
          v47,
          0,
          0);
        v11 = 1;
      }
      else
      {
        v50 = GetLastError();
        v51 = CurrentIP();
        v52 = GetLastError();
        v53 = ConstructPartialMsgW(0x3000000u, "Failed to restart Diagtrack service, error code=%d", v52);
        WdsSetupLogMessageW(
          v53,
          0,
          L"D",
          0,
          430,
          L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
          L"UtcUploadTelemetryData",
          v51,
          v50,
          0,
          0);
      }
      goto LABEL_26;
    }
  }
  v54 = GetLastError();
  v55 = CurrentIP();
  v56 = ConstructPartialMsgW(0x2000000u, "Service %s is not available", (const char *)ServiceName);
  WdsSetupLogMessageW(
    v56,
    0,
    L"D",
    0,
    436,
    L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
    L"UtcUploadTelemetryData",
    v55,
    v54,
    0,
    0);
LABEL_26:
  if ( a2 && v11 )
    goto LABEL_31;
  if ( !v12 )
    goto LABEL_39;
  if ( a2 && v11 )
  {
LABEL_31:
    v57 = GetLastError();
    v58 = CurrentIP();
    v59 = ConstructPartialMsgW(0x4000000u, "Delete all etl files because this is an async upload request.");
    WdsSetupLogMessageW(
      v59,
      0,
      L"D",
      0,
      443,
      L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
      L"UtcUploadTelemetryData",
      v58,
      v57,
      0,
      0);
  }
  else
  {
    v60 = GetLastError();
    v61 = CurrentIP();
    v62 = ConstructPartialMsgW(0x4000000u, "Upload files successfully so we can remove all etl files.");
    WdsSetupLogMessageW(
      v62,
      0,
      L"D",
      0,
      447,
      L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
      L"UtcUploadTelemetryData",
      v61,
      v60,
      0,
      0);
  }
  if ( !a8 )
  {
    for ( i = 0; ; ++i )
    {
      v64 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v83);
      v65 = (unsigned int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v64 + 8) + 12LL) + v64 + 8);
      if ( i >= (**v65)(v65) )
        break;
      v66 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v83);
      v67 = *(int *)(*(_QWORD *)(v66 + 8) + 16LL) + v66 + 8;
      v68 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 24LL))(v67, i);
      v69 = UnBCL::String::get_CString(*v68);
      if ( !DeleteFileW(v69) )
      {
        v70 = GetLastError();
        v71 = CurrentIP();
        v72 = GetLastError();
        v73 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v83);
        v74 = *(int *)(*(_QWORD *)(v73 + 8) + 16LL) + v73 + 8;
        v75 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v74 + 24LL))(v74, i);
        v76 = (const char *)UnBCL::String::get_CString(*v75);
        v77 = ConstructPartialMsgW(0x3000000u, "Failed to delete file: %s. Error = %d", v76, v72);
        WdsSetupLogMessageW(
          v77,
          0,
          L"D",
          0,
          456,
          L"base\\ntsetup\\setupplatform\\lib\\utcutil\\utcutil.cpp",
          L"UtcUploadTelemetryData",
          v71,
          v70,
          0,
          0);
      }
    }
  }
LABEL_39:
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v83);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v80);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v85);
}

```

## disassembly

```asm
0x180382b94  push    rbp
0x180382b96  push    rbx
0x180382b97  push    rsi
0x180382b98  push    rdi
0x180382b99  push    r12
0x180382b9b  push    r13
0x180382b9d  push    r14
0x180382b9f  push    r15
0x180382ba1  lea     rbp, [rsp-98h]
0x180382ba9  sub     rsp, 198h
0x180382bb0  mov     [rbp+0D0h+var_118], 0FFFFFFFFFFFFFFFEh
0x180382bb8  mov     rax, cs:__security_cookie
0x180382bbf  xor     rax, rsp
0x180382bc2  mov     [rbp+0D0h+var_50], rax
0x180382bc9  mov     r15d, edx
0x180382bcc  mov     r13, rcx
0x180382bcf  mov     rdi, [rbp+0D0h+arg_20]
0x180382bd6  mov     rbx, [rbp+0D0h+arg_30]
0x180382bdd  mov     [rbp+0D0h+var_A0], 720050h
0x180382be4  mov     [rbp+0D0h+var_9C], 67006Fh
0x180382beb  mov     [rbp+0D0h+var_98], 610072h
0x180382bf2  mov     [rbp+0D0h+var_94], 44006Dh
0x180382bf9  mov     [rbp+0D0h+var_90], 740061h
0x180382c00  mov     [rbp+0D0h+var_8C], 5C0061h
0x180382c07  mov     [rbp+0D0h+var_88], 69004Dh
0x180382c0e  mov     [rbp+0D0h+var_84], 720063h
0x180382c15  mov     [rbp+0D0h+var_80], 73006Fh
0x180382c1c  mov     [rbp+0D0h+var_7C], 66006Fh
0x180382c23  mov     [rbp+0D0h+var_78], 5C0074h
0x180382c2a  mov     [rbp+0D0h+var_74], 690044h
0x180382c31  mov     [rbp+0D0h+var_70], 670061h
0x180382c38  mov     [rbp+0D0h+var_6C], 6F006Eh
0x180382c3f  mov     [rbp+0D0h+var_68], 690073h
0x180382c46  mov     [rbp+0D0h+var_64], 5C0073h
0x180382c4d  mov     [rbp+0D0h+var_60], 540045h
0x180382c54  mov     [rbp+0D0h+var_5C], 4C004Ch
0x180382c5b  mov     [rbp+0D0h+var_58], 67006Fh
0x180382c62  mov     [rbp+0D0h+var_54], 73h ; 's'
0x180382c69  mov     dword ptr [rbp+0D0h+ServiceName], 690044h
0x180382c70  mov     [rbp+0D0h+var_BC], 670061h
0x180382c77  mov     [rbp+0D0h+var_B8], 720054h
0x180382c7e  mov     [rbp+0D0h+var_B4], 630061h
0x180382c85  mov     [rbp+0D0h+var_B0], 6Bh ; 'k'
0x180382c8c  lea     rcx, [rbp+0D0h+var_110]
0x180382c90  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180382c96  nop
0x180382c97  lea     rcx, [rbp+0D0h+var_148]
0x180382c9b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180382ca1  nop
0x180382ca2  lea     rcx, [rbp+0D0h+var_128]
0x180382ca6  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180382cac  nop
0x180382cad  xor     r14d, r14d
0x180382cb0  xor     r12d, r12d
0x180382cb3  test    rbx, rbx
0x180382cb6  jz      short loc_180382D0F
0x180382cb8  lea     rdx, [rbp+0D0h+var_A0]
0x180382cbc  lea     rcx, [rsp+1D0h+var_160]
0x180382cc1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180382cc7  nop
0x180382cc8  mov     rdx, rax
0x180382ccb  mov     rcx, rbx
0x180382cce  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180382cd4  mov     rdx, rax
0x180382cd7  lea     rcx, [rsp+1D0h+var_170]
0x180382cdc  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180382ce2  nop
0x180382ce3  lea     rdx, [rsp+1D0h+var_170]
0x180382ce8  lea     rcx, [rbp+0D0h+var_148]
0x180382cec  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180382cf2  nop
0x180382cf3  lea     rcx, [rsp+1D0h+var_170]
0x180382cf8  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180382cfe  nop
0x180382cff  lea     rcx, [rsp+1D0h+var_160]
0x180382d04  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180382d0a  jmp     loc_180382DAC
0x180382d0f  lea     rdx, aSystemdrive_0; "%systemdrive%"
0x180382d16  lea     rcx, [rbp+0D0h+var_100]
0x180382d1a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180382d20  nop
0x180382d21  mov     rcx, rax
0x180382d24  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x180382d2a  mov     rdx, rax
0x180382d2d  lea     rcx, [rsp+1D0h+var_160]
0x180382d32  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180382d38  nop
0x180382d39  lea     rcx, [rbp+0D0h+var_100]
0x180382d3d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180382d43  lea     rdx, [rbp+0D0h+var_A0]
0x180382d47  lea     rcx, [rbp+0D0h+Buffer]
0x180382d4b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180382d51  mov     rbx, rax
0x180382d54  lea     rcx, [rsp+1D0h+var_160]
0x180382d59  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180382d5f  mov     rdx, rbx
0x180382d62  mov     rcx, rax
0x180382d65  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180382d6b  mov     rdx, rax
0x180382d6e  lea     rcx, [rsp+1D0h+var_170]
0x180382d73  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180382d79  nop
0x180382d7a  lea     rdx, [rsp+1D0h+var_170]
0x180382d7f  lea     rcx, [rbp+0D0h+var_148]
0x180382d83  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180382d89  nop
0x180382d8a  lea     rcx, [rsp+1D0h+var_170]
0x180382d8f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180382d95  nop
0x180382d96  lea     rcx, [rbp+0D0h+Buffer]
0x180382d9a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180382da0  nop
0x180382da1  lea     rcx, [rsp+1D0h+var_160]
0x180382da6  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180382dac  lea     rcx, [rbp+0D0h+var_148]
0x180382db0  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180382db6  mov     rcx, rax
0x180382db9  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180382dbf  test    eax, eax
0x180382dc1  jnz     short loc_180382DD6
0x180382dc3  lea     rcx, [rbp+0D0h+var_148]
0x180382dc7  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180382dcd  mov     rcx, rax
0x180382dd0  call    cs:__imp_?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z; UnBCL::Directory::CreateDir(UnBCL::String const *)
0x180382dd6  lea     rcx, [rbp+0D0h+var_148]
0x180382dda  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180382de0  mov     rcx, rax
0x180382de3  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180382de9  mov     [rbp+0D0h+var_138], rax
0x180382ded  test    rdi, rdi
0x180382df0  jz      short loc_180382E01
0x180382df2  mov     rcx, rdi
0x180382df5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180382dfb  mov     [rbp+0D0h+var_130], rax
0x180382dff  jmp     short loc_180382E09
0x180382e01  mov     [rbp+0D0h+var_130], 0
0x180382e09  mov     ecx, 0B0h
0x180382e0e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180382e14  mov     rbx, rax
0x180382e17  mov     qword ptr [rsp+1D0h+var_170], rax
0x180382e1c  mov     edi, 1
0x180382e21  test    rax, rax
0x180382e24  jz      short loc_180382E3E
0x180382e26  mov     edx, edi
0x180382e28  mov     rcx, rax
0x180382e2b  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x180382e31  lea     rax, ??_S?$ArrayList@PEAVString@UnBCL@@@UnBCL@@6BObject@1@@; const UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'}
0x180382e38  mov     [rbx+30h], rax
0x180382e3c  jmp     short loc_180382E40
0x180382e3e  xor     ebx, ebx
0x180382e40  mov     rdx, rbx
0x180382e43  lea     rcx, [rsp+1D0h+var_160]
0x180382e48  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x180382e4e  nop
0x180382e4f  lea     rdx, [rsp+1D0h+var_160]
0x180382e54  lea     rcx, [rbp+0D0h+var_128]
0x180382e58  call    cs:__imp_??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> const &)
0x180382e5e  nop
0x180382e5f  lea     rcx, [rsp+1D0h+var_160]
0x180382e64  call    cs:__imp_??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180382e6a  lea     rcx, [rbp+0D0h+var_128]
0x180382e6e  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180382e74  mov     r8, rax
0x180382e77  mov     rcx, [rax]
0x180382e7a  mov     rax, [rcx+28h]
0x180382e7e  mov     edx, edi
0x180382e80  mov     rcx, r8
0x180382e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180382e88  call    cs:__imp_GetLastError
0x180382e8e  mov     esi, eax
0x180382e90  call    cs:__imp_CurrentIP
0x180382e96  mov     rdi, rax
0x180382e99  lea     rcx, [rbp+0D0h+var_148]
0x180382e9d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180382ea3  mov     rcx, rax
0x180382ea6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180382eac  mov     rbx, rax
0x180382eaf  mov     rcx, r13
0x180382eb2  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180382eb8  mov     r9, rbx
0x180382ebb  mov     r8, rax
0x180382ebe  lea     rdx, aCopyTelemetryF; "Copy telemetry file: source folder: %s,"...
0x180382ec5  mov     ecx, 4000000h; unsigned int
0x180382eca  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180382ecf  xor     ebx, ebx
0x180382ed1  mov     [rsp+1D0h+var_180], ebx
0x180382ed5  mov     [rsp+1D0h+var_188], rbx
0x180382eda  mov     [rsp+1D0h+var_190], esi
0x180382ede  mov     [rsp+1D0h+var_198], rdi
0x180382ee3  lea     rcx, aUtcuploadtelem; "UtcUploadTelemetryData"
0x180382eea  mov     [rsp+1D0h+var_1A0], rcx
0x180382eef  lea     rcx, aBaseNtsetupSet_47; "base\\ntsetup\\setupplatform\\lib\\utcu"...
0x180382ef6  mov     [rsp+1D0h+var_1A8], rcx
0x180382efb  mov     dword ptr [rsp+1D0h+pcbBytesNeeded], 17Fh
0x180382f03  xor     r9d, r9d
0x180382f06  lea     r8, aD_0; "D"
0x180382f0d  xor     edx, edx
0x180382f0f  mov     rcx, rax
0x180382f12  call    cs:__imp_WdsSetupLogMessageW
0x180382f18  mov     [rsp+1D0h+var_160], rbx
0x180382f1d  lea     rax, [rbp+0D0h+var_138]
0x180382f21  mov     [rsp+1D0h+var_158], rax
0x180382f26  lea     rax, ?pCopyTelemetryFile@@YAHPEAU_WDSLIB_FIND_DATA@@PEAX@Z; pCopyTelemetryFile(_WDSLIB_FIND_DATA *,void *)
0x180382f2d  mov     [rbp+0D0h+var_150], rax
0x180382f31  mov     rcx, r13
0x180382f34  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180382f3a  mov     rcx, rax; lpFileName
0x180382f3d  xor     r13d, r13d
0x180382f40  mov     dword ptr [rsp+1D0h+pcbBytesNeeded], r13d; int
0x180382f45  lea     r9, [rsp+1D0h+var_160]
0x180382f4a  lea     r8, EnumeratePathFileCallback
0x180382f51  lea     rdx, EnumeratePathDirCallback
0x180382f58  call    EnumeratePathEx
0x180382f5d  xorps   xmm0, xmm0
0x180382f60  xor     eax, eax
0x180382f62  movups  xmmword ptr [rbp+0D0h+Buffer], xmm0
0x180382f66  movups  [rbp+0D0h+var_D8], xmm0
0x180382f6a  mov     [rbp+0D0h+var_C8], eax
0x180382f6d  mov     [rsp+1D0h+var_170], r13d
0x180382f72  xor     edx, edx; lpDatabaseName
0x180382f74  xor     ecx, ecx; lpMachineName
0x180382f76  mov     r8d, 0F003Fh; dwDesiredAccess
0x180382f7c  call    cs:__imp_OpenSCManagerW
0x180382f82  mov     rsi, rax
0x180382f85  test    rax, rax
0x180382f88  jz      loc_180383239
0x180382f8e  mov     r8d, 80000000h; dwDesiredAccess
0x180382f94  lea     rdx, [rbp+0D0h+ServiceName]; lpServiceName
0x180382f98  mov     rcx, rax; hSCManager
0x180382f9b  call    cs:__imp_OpenServiceW
0x180382fa1  mov     rdi, rax
0x180382fa4  test    rax, rax
0x180382fa7  jz      short loc_180382FDD
0x180382fa9  lea     rax, [rsp+1D0h+var_170]
0x180382fae  mov     [rsp+1D0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180382fb3  lea     r9d, [rbx+24h]; cbBufSize
0x180382fb7  lea     r8, [rbp+0D0h+Buffer]; lpBuffer
0x180382fbb  xor     edx, edx; InfoLevel
0x180382fbd  mov     rcx, rdi; hService
0x180382fc0  call    cs:__imp_QueryServiceStatusEx
0x180382fc6  test    eax, eax
0x180382fc8  jz      short loc_180382FD4
0x180382fca  cmp     dword ptr [rbp+0D0h+Buffer+4], 4
0x180382fce  lea     eax, [rbx+1]
0x180382fd1  cmovz   ebx, eax
0x180382fd4  mov     rcx, rdi; hSCObject
0x180382fd7  call    cs:__imp_CloseServiceHandle
0x180382fdd  mov     rcx, rsi; hSCObject
0x180382fe0  call    cs:__imp_CloseServiceHandle
0x180382fe6  test    ebx, ebx
0x180382fe8  jz      loc_180383239
0x180382fee  call    cs:__imp_GetLastError
0x180382ff4  mov     edi, eax
0x180382ff6  call    cs:__imp_CurrentIP
0x180382ffc  mov     rbx, rax
0x180382fff  lea     rdx, aDiagtrackServi; "Diagtrack service is running"
0x180383006  mov     ecx, 4000000h; unsigned int
0x18038300b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180383010  mov     [rsp+1D0h+var_180], r13d
0x180383015  mov     [rsp+1D0h+var_188], r13
0x18038301a  mov     [rsp+1D0h+var_190], edi
0x18038301e  mov     [rsp+1D0h+var_198], rbx
0x180383023  lea     rcx, aUtcuploadtelem; "UtcUploadTelemetryData"
0x18038302a  mov     [rsp+1D0h+var_1A0], rcx
0x18038302f  lea     rcx, aBaseNtsetupSet_47; "base\\ntsetup\\setupplatform\\lib\\utcu"...
0x180383036  mov     [rsp+1D0h+var_1A8], rcx
0x18038303b  mov     dword ptr [rsp+1D0h+pcbBytesNeeded], 191h
0x180383043  xor     r9d, r9d
0x180383046  lea     r8, aD_0; "D"
0x18038304d  xor     edx, edx
0x18038304f  mov     rcx, rax
0x180383052  call    cs:__imp_WdsSetupLogMessageW
0x180383058  cmp     [rbp+0D0h+arg_40], r13d
0x18038305f  jnz     loc_1803830E8
0x180383065  call    ?pForceUpload@@YAJXZ; pForceUpload(void)
0x18038306a  mov     esi, eax
0x18038306c  test    eax, eax
0x18038306e  js      short loc_1803830EB
0x180383070  call    cs:__imp_GetLastError
0x180383076  mov     edi, eax
0x180383078  call    cs:__imp_CurrentIP
0x18038307e  mov     rbx, rax
0x180383081  lea     rdx, aSuccessfullyFo; "Successfully Forceuploaded the telemetr"...
0x180383088  mov     ecx, 4000000h; unsigned int
0x18038308d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180383092  mov     [rsp+1D0h+var_180], r13d
0x180383097  mov     [rsp+1D0h+var_188], r13
0x18038309c  mov     [rsp+1D0h+var_190], edi
0x1803830a0  mov     [rsp+1D0h+var_198], rbx
0x1803830a5  lea     rcx, aUtcuploadtelem; "UtcUploadTelemetryData"
0x1803830ac  mov     [rsp+1D0h+var_1A0], rcx
0x1803830b1  lea     rcx, aBaseNtsetupSet_47; "base\\ntsetup\\setupplatform\\lib\\utcu"...
0x1803830b8  mov     [rsp+1D0h+var_1A8], rcx
0x1803830bd  mov     dword ptr [rsp+1D0h+pcbBytesNeeded], 19Ah
0x1803830c5  xor     r9d, r9d
0x1803830c8  lea     rsi, aD_0; "D"
0x1803830cf  mov     r8, rsi
0x1803830d2  xor     edx, edx
0x1803830d4  mov     rcx, rax
0x1803830d7  call    cs:__imp_WdsSetupLogMessageW
  ... truncated ...
```
