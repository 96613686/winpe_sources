# CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x18013c5f0`
- end: `0x18013d4cf`
- name: `?DoExecute@CFinalizeSafeOSBootRemoval@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `3807`
- prototype: `__int64 __fastcall(CFinalizeSafeOSBootRemoval *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x18013c5f0`
- `0x1802dacac`
- `0x1802e2078`
- `0x1802e6604`
- `0x180405298`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x18013c9d3`
- `ADVAPI32!OpenSCManagerW` at `0x18013c9d3`
- `ADVAPI32!OpenServiceW` at `0x18013ca5d`
- `ADVAPI32!OpenServiceW` at `0x18013ca5d`
- `ADVAPI32!ControlService` at `0x18013cb1b`
- `ADVAPI32!ControlService` at `0x18013cb1b`
- `ADVAPI32!DeleteService` at `0x18013cbe7`
- `ADVAPI32!DeleteService` at `0x18013cbe7`
- `ADVAPI32!CloseServiceHandle` at `0x18013ceaa`
- `ADVAPI32!CloseServiceHandle` at `0x18013ceb5`
- `ADVAPI32!CloseServiceHandle` at `0x18013ceaa`
- `ADVAPI32!CloseServiceHandle` at `0x18013ceb5`
- `KERNEL32!GetLastError` at `0x18013c91c`
- `KERNEL32!GetLastError` at `0x18013c92d`
- `KERNEL32!GetLastError` at `0x18013c9e3`
- `KERNEL32!GetLastError` at `0x18013c9f4`
- `KERNEL32!GetLastError` at `0x18013ca77`
- `KERNEL32!GetLastError` at `0x18013ca8a`
- `KERNEL32!GetLastError` at `0x18013cb25`
- `KERNEL32!GetLastError` at `0x18013cb75`
- `KERNEL32!GetLastError` at `0x18013cb86`
- `KERNEL32!GetLastError` at `0x18013cbf5`
- `KERNEL32!GetLastError` at `0x18013cccd`
- `KERNEL32!GetLastError` at `0x18013cd30`
- `KERNEL32!GetLastError` at `0x18013cd41`
- `KERNEL32!GetLastError` at `0x18013cdbb`
- `KERNEL32!GetLastError` at `0x18013cdcc`
- `KERNEL32!GetLastError` at `0x18013ce38`
- `KERNEL32!GetLastError` at `0x18013ce49`
- `KERNEL32!GetLastError` at `0x18013cec0`
- `KERNEL32!GetLastError` at `0x18013cf63`
- `KERNEL32!GetLastError` at `0x18013d00e`
- `KERNEL32!GetLastError` at `0x18013d0b2`
- `KERNEL32!GetLastError` at `0x18013d0c8`
- `KERNEL32!GetLastError` at `0x18013d0e8`
- `KERNEL32!GetLastError` at `0x18013d1c2`
- `KERNEL32!GetLastError` at `0x18013d287`
- `KERNEL32!GetLastError` at `0x18013d34a`
- `KERNEL32!GetLastError` at `0x18013d403`
- `KERNEL32!GetLastError` at `0x18013c91c`
- `KERNEL32!GetLastError` at `0x18013c92d`
- `KERNEL32!GetLastError` at `0x18013c9e3`
- `KERNEL32!GetLastError` at `0x18013c9f4`
- `KERNEL32!GetLastError` at `0x18013ca77`
- `KERNEL32!GetLastError` at `0x18013ca8a`
- `KERNEL32!GetLastError` at `0x18013cb25`
- `KERNEL32!GetLastError` at `0x18013cb75`
- `KERNEL32!GetLastError` at `0x18013cb86`
- `KERNEL32!GetLastError` at `0x18013cbf5`
- `KERNEL32!GetLastError` at `0x18013cccd`
- `KERNEL32!GetLastError` at `0x18013cd30`
- `KERNEL32!GetLastError` at `0x18013cd41`
- `KERNEL32!GetLastError` at `0x18013cdbb`
- `KERNEL32!GetLastError` at `0x18013cdcc`
- `KERNEL32!GetLastError` at `0x18013ce38`
- `KERNEL32!GetLastError` at `0x18013ce49`
- `KERNEL32!GetLastError` at `0x18013cec0`
- `KERNEL32!GetLastError` at `0x18013cf63`
- `KERNEL32!GetLastError` at `0x18013d00e`
- `KERNEL32!GetLastError` at `0x18013d0b2`
- `KERNEL32!GetLastError` at `0x18013d0c8`
- `KERNEL32!GetLastError` at `0x18013d0e8`
- `KERNEL32!GetLastError` at `0x18013d1c2`
- `KERNEL32!GetLastError` at `0x18013d287`
- `KERNEL32!GetLastError` at `0x18013d34a`
- `KERNEL32!GetLastError` at `0x18013d403`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18013cc74`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18013cc74`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18013c6d4`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18013c6d4`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013c750`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013c8be`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013c750`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013c8be`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18013c888`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18013c888`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013c6f3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013c7ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013cc9c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013c6f3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013c7ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013cc9c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18013c71d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18013c71d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013c770`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013c8de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013cc91`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013c770`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013c8de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013cc91`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013c733`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013c8ac`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013cc6a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013c733`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013c8ac`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013cc6a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18013c7d3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18013c7d3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c77e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c793`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c80c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c8ec`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013ccb0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013cce3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013cd4e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d102`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d117`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d1d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d29b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d35e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d417`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c77e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c793`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c80c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013c8ec`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013ccb0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013cce3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013cd4e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d102`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d117`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d1d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d29b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d35e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013d417`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c787`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c79c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c815`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c8f5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013ccb9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013ccec`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013cd57`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d10b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d120`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d1e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d2a4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d367`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d420`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c787`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c79c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c815`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013c8f5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013ccb9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013ccec`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013cd57`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d10b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d120`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d1e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d2a4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d367`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013d420`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013c7e2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013c9b1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013ce30`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013d48e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013d49a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013c7e2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013c9b1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013ce30`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013d48e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18013d49a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013c761`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013c7bf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013c8cf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013cc82`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013c761`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013c7bf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013c8cf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013cc82`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013c993`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013ca45`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013caed`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cbde`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cc55`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cdab`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013ce24`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cea1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cf2e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cfd2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d07f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d190`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d24b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d30e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d3d1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d47f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013c993`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013ca45`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013caed`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cbde`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cc55`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cdab`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013ce24`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cea1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cf2e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013cfd2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d07f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d190`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d24b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d30e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d3d1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013d47f`

## string_xrefs

- `0x18013d029`: `%hs: Failed to open system store. Status = 0x%08X`
- `0x18013cf7c`: `%hs: Missing information for the SafeOS for rollback.`
- `0x18013d2b8`: `%hs: Failed to open BCD's %s entry. Status = 0x%08X`
- `0x18013d139`: `%hs: Failed to read %s boot entry GUID from %s. hr = 0x%08X`
- `0x18013d429`: `Recovery sequence for %s boot entry deleted successfully.`
- `0x18013d37b`: `%hs: Failed to remove recovery sequence for %s. Status = 0x%08X`
- `0x18013c9fd`: `Failed to open service control manager. Error: 0x%08X`
- `0x18013c93d`: `Failed to write the %s marker. Error: 0x%08X`
- `0x18013caa5`: `Failed to open service %s. Error: 0x%08X`
- `0x18013cb96`: `Failed to stop service %s. Error: 0x%08X`
- `0x18013cb3d`: `Service %s stopped successfully.`
- `0x18013cc5b`: `%windir%\System32\drivers\WinSetupBoot.sys`
- `0x18013cc0d`: `Service %s deleted successfully.`
- `0x18013cd63`: `Failed to delete %s. Error: 0x%08X`
- `0x18013ccf5`: `Service binary %s deleted successfully.`
- `0x18013ce59`: `Failed to delete service %s. Error: 0x%08X`
- `0x18013cddc`: `Failed to determine service binary file path for %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=2
__int64 __fastcall CFinalizeSafeOSBootRemoval::DoExecute(
        CFinalizeSafeOSBootRemoval *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  SC_HANDLE v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rbx
  char *v9; // rdi
  int v10; // r15d
  const struct UnBCL::String *v11; // rbx
  const struct UnBCL::String *v12; // rax
  struct UnBCL::String *v13; // rax
  UnBCL::String *v14; // rax
  const WCHAR *CString; // rbx
  UnBCL::String *v16; // rax
  const WCHAR *v17; // rax
  struct UnBCL::String *v18; // rax
  UnBCL::String *v19; // rax
  const unsigned __int16 *v20; // rax
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  SC_HANDLE v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  DWORD v27; // eax
  struct tagLOG_PARTIAL_MSG *v28; // rax
  SC_HANDLE v29; // rax
  SC_HANDLE v30; // rsi
  DWORD v31; // esi
  DWORD v32; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  DWORD v38; // edi
  __int64 v39; // rbx
  DWORD v40; // eax
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  const struct UnBCL::String *v44; // rax
  struct UnBCL::String *v45; // rax
  UnBCL::String *v46; // rax
  const unsigned __int16 *v47; // rax
  DWORD v48; // edi
  __int64 v49; // rbx
  UnBCL::String *v50; // rax
  const char *v51; // rax
  struct tagLOG_PARTIAL_MSG *v52; // rax
  DWORD v53; // esi
  __int64 v54; // rdi
  DWORD v55; // ebx
  UnBCL::String *v56; // rax
  const char *v57; // rax
  struct tagLOG_PARTIAL_MSG *v58; // rax
  DWORD v59; // edi
  __int64 v60; // rbx
  DWORD v61; // eax
  DWORD v62; // edi
  __int64 v63; // rbx
  DWORD v64; // eax
  struct tagLOG_PARTIAL_MSG *v65; // rax
  DWORD v67; // edi
  __int64 v68; // rbx
  struct tagLOG_PARTIAL_MSG *v69; // rax
  DWORD v70; // edi
  __int64 v71; // rbx
  struct tagLOG_PARTIAL_MSG *v72; // rax
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  signed int v76; // eax
  bool v77; // sf
  signed int v78; // eax
  unsigned int v79; // ebx
  DWORD v80; // r15d
  __int64 v81; // r12
  UnBCL::String *v82; // rax
  const char *v83; // rsi
  UnBCL::String *v84; // rax
  const char *v85; // rax
  struct tagLOG_PARTIAL_MSG *v86; // rax
  DWORD v87; // edi
  __int64 v88; // rsi
  UnBCL::String *v89; // rax
  const char *v90; // rax
  struct tagLOG_PARTIAL_MSG *v91; // rax
  DWORD v92; // esi
  __int64 v93; // r15
  UnBCL::String *v94; // rax
  const char *v95; // rax
  struct tagLOG_PARTIAL_MSG *v96; // rax
  DWORD LastError; // esi
  __int64 v98; // r15
  UnBCL::String *v99; // rax
  const char *v100; // rax
  struct tagLOG_PARTIAL_MSG *v101; // rax
  DWORD v102; // ebx
  __int64 v103; // rsi
  UnBCL::String *v104; // rax
  const char *v105; // rax
  struct tagLOG_PARTIAL_MSG *v106; // rax
  int v107; // [rsp+20h] [rbp-178h]
  int v108; // [rsp+20h] [rbp-178h]
  __int64 v109; // [rsp+38h] [rbp-160h]
  __int64 v110; // [rsp+38h] [rbp-160h]
  DWORD v111; // [rsp+40h] [rbp-158h]
  DWORD v112; // [rsp+40h] [rbp-158h]
  SC_HANDLE v113; // [rsp+68h] [rbp-130h] BYREF
  _BYTE v114[16]; // [rsp+70h] [rbp-128h] BYREF
  __int64 v115; // [rsp+80h] [rbp-118h] BYREF
  SC_HANDLE hSCObject; // [rsp+88h] [rbp-110h]
  _QWORD *pExceptionObject; // [rsp+90h] [rbp-108h] BYREF
  _QWORD *v118; // [rsp+98h] [rbp-100h] BYREF
  _QWORD *v119; // [rsp+A0h] [rbp-F8h] BYREF
  _QWORD *v120; // [rsp+A8h] [rbp-F0h] BYREF
  _QWORD *v121; // [rsp+B0h] [rbp-E8h] BYREF
  _QWORD *v122; // [rsp+B8h] [rbp-E0h] BYREF
  _QWORD *v123; // [rsp+C0h] [rbp-D8h] BYREF
  _BYTE v124[16]; // [rsp+C8h] [rbp-D0h] BYREF
  _BYTE v125[24]; // [rsp+D8h] [rbp-C0h] BYREF
  _BYTE v126[16]; // [rsp+F0h] [rbp-A8h] BYREF
  _QWORD v127[8]; // [rsp+100h] [rbp-98h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+140h] [rbp-58h] BYREF

  v127[7] = -2;
  v6 = 0;
  hSCObject = 0;
  v7 = (*(__int64 (__fastcall **)(struct IExecutionContext *, struct IExecutionContext *, void *, struct IInternalOperationsProgress *))(*(_QWORD *)a2 + 72LL))(
         a2,
         a2,
         a3,
         a4);
  v8 = v7;
  if ( v7
    && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7)
    && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8) )
  {
    v6 = (SC_HANDLE)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
    hSCObject = v6;
  }
  if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2) >= 4 )
  {
    if ( v6 )
    {
      v113 = 0;
      v115 = 0;
      UnBCL::Exception::Exception((UnBCL::Exception *)v127);
      v127[0] = &`CFinalizeSafeOSBootRemoval::DoExecute'::`12'::CXXXXXHandledException::`vftable';
      v9 = (char *)this + 208;
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208) )
      {
        v10 = BcdOpenSystemStore(&v113);
        if ( v10 >= 0 )
        {
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v114);
          v11 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v125, L"SetupPlatform.ini");
          v12 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
          v13 = UnBCL::Path::Combine(v12, v11);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v124, v13);
          UnBCL::String::~String((UnBCL::String *)v125);
          v14 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v124);
          CString = UnBCL::String::get_CString(v14);
          v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v9);
          v17 = UnBCL::String::get_CString(v16);
          v18 = SPReadConfigValue(L"BootEntries", v17, CString);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v126, v18);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v114, v126);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v126);
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v114) )
          {
            *(_OWORD *)&ServiceStatus.dwServiceType = 0;
            v19 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
            v20 = UnBCL::String::get_CString(v19);
            v21 = SPGuidFromString(v20, (struct _GUID *)&ServiceStatus);
            if ( v21 >= 0 )
            {
              v22 = BcdOpenObject(v113, &ServiceStatus, &v115);
              if ( v22 >= 0 )
              {
                v23 = BcdDeleteElement(v115, 335544328);
                if ( v23 < 0 )
                {
                  LastError = GetLastError();
                  v98 = CurrentIP();
                  v99 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v9);
                  v100 = (const char *)UnBCL::String::get_CString(v99);
                  v101 = ConstructPartialMsgW(
                           0x2000000u,
                           "%hs: Failed to remove recovery sequence for %s. Status = 0x%08X",
                           "CFinalizeSafeOSBootRemoval::DoExecute",
                           v100,
                           v23);
                  WdsSetupLogMessageW(
                    v101,
                    819200,
                    L"D",
                    0,
                    6572,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                    L"CFinalizeSafeOSBootRemoval::DoExecute",
                    v98,
                    LastError,
                    0,
                    0);
                  v122 = v127;
                  throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v122;
                }
                v102 = GetLastError();
                v103 = CurrentIP();
                v104 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v9);
                v105 = (const char *)UnBCL::String::get_CString(v104);
                v106 = ConstructPartialMsgW(
                         0x4000000u,
                         "Recovery sequence for %s boot entry deleted successfully.",
                         v105);
                WdsSetupLogMessageW(
                  v106,
                  819200,
                  L"D",
                  0,
                  6576,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                  L"CFinalizeSafeOSBootRemoval::DoExecute",
                  v103,
                  v102,
                  0,
                  0);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v124);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v114);
                v123 = v127;
                throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v123;
              }
              v92 = GetLastError();
              v93 = CurrentIP();
              v94 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v9);
              v95 = (const char *)UnBCL::String::get_CString(v94);
              v96 = ConstructPartialMsgW(
                      0x2000000u,
                      "%hs: Failed to open BCD's %s entry. Status = 0x%08X",
                      "CFinalizeSafeOSBootRemoval::DoExecute",
                      v95,
                      v22);
              WdsSetupLogMessageW(
                v96,
                819200,
                L"D",
                0,
                6560,
                L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
                L"CFinalizeSafeOSBootRemoval::DoExecute",
                v93,
                v92,
                0,
                0);
              v121 = v127;
              throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v121;
            }
            v87 = GetLastError();
            v88 = CurrentIP();
            v89 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
            v90 = (const char *)UnBCL::String::get_CString(v89);
            v91 = ConstructPartialMsgW(
                    0x2000000u,
                    "%hs: SPGuidFromString failed for %s. hr = 0x%08X",
                    "CFinalizeSafeOSBootRemoval::DoExecute",
                    v90,
                    v21);
            WdsSetupLogMessageW(
              v91,
              819200,
              L"D",
              0,
              6547,
              L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
              L"CFinalizeSafeOSBootRemoval::DoExecute",
              v88,
              v87,
              0,
              0);
            v120 = v127;
            throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v120;
          }
          v76 = GetLastError();
          v77 = v76 < 0;
          if ( v76 > 0 )
            v77 = 1;
          if ( v77 )
          {
            v78 = GetLastError();
            v79 = v78;
            if ( v78 > 0 )
              v79 = (unsigned __int16)v78 | 0x80070000;
          }
          else
          {
            v79 = -2147467259;
          }
          v80 = GetLastError();
          v81 = CurrentIP();
          v82 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v124);
          v83 = (const char *)UnBCL::String::get_CString(v82);
          v84 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v9);
          v85 = (const char *)UnBCL::String::get_CString(v84);
          v86 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: Failed to read %s boot entry GUID from %s. hr = 0x%08X",
                  "CFinalizeSafeOSBootRemoval::DoExecute",
                  v85,
                  v83,
                  v79);
          WdsSetupLogMessageW(
            v86,
            819200,
            L"D",
            0,
            6539,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CFinalizeSafeOSBootRemoval::DoExecute",
            v81,
            v80,
            0,
            0);
          v119 = v127;
          throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v119;
        }
        v73 = GetLastError();
        v74 = CurrentIP();
        v75 = ConstructPartialMsgW(
                0x2000000u,
                "%hs: Failed to open system store. Status = 0x%08X",
                "CFinalizeSafeOSBootRemoval::DoExecute",
                v10);
        WdsSetupLogMessageW(
          v75,
          819200,
          L"D",
          0,
          6528,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CFinalizeSafeOSBootRemoval::DoExecute",
          v74,
          v73,
          0,
          0);
        v118 = v127;
        throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&v118;
      }
      v70 = GetLastError();
      v71 = CurrentIP();
      v72 = ConstructPartialMsgW(
              0x3000000u,
              "%hs: Missing information for the SafeOS for rollback.",
              "CFinalizeSafeOSBootRemoval::DoExecute");
      WdsSetupLogMessageW(
        v72,
        819200,
        L"D",
        0,
        6519,
        L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
        L"CFinalizeSafeOSBootRemoval::DoExecute",
        v71,
        v70,
        0,
        0);
      pExceptionObject = v127;
      throw (`CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException **)&pExceptionObject;
    }
    v24 = OpenSCManagerW(0, 0, 0x10020u);
    v113 = v24;
    if ( !v24 )
    {
      v25 = GetLastError();
      v26 = CurrentIP();
      v27 = GetLastError();
      v28 = ConstructPartialMsgW(0x2000000u, "Failed to open service control manager. Error: 0x%08X", v27);
      WdsSetupLogMessageW(
        v28,
        819200,
        L"D",
        0,
        6619,
        L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
        L"CFinalizeSafeOSBootRemoval::DoExecute",
        v26,
        v25,
        0,
        0);
      return 0;
    }
    v29 = OpenServiceW(v24, L"WinSetupBoot", 0x10020u);
    v30 = v29;
    hSCObject = v29;
    if ( !v29 )
    {
      v31 = GetLastError();
      if ( v31 != 1060 )
      {
        v32 = GetLastError();
        v33 = CurrentIP();
        v34 = ConstructPartialMsgW(
                0x2000000u,
                "Failed to open service %s. Error: 0x%08X",
                (const char *)L"WinSetupBoot",
                v31);
        WdsSetupLogMessageW(
          v34,
          819200,
          L"D",
          0,
          6631,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CFinalizeSafeOSBootRemoval::DoExecute",
          v33,
          v32,
          0,
          0);
      }
      goto LABEL_32;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( ControlService(v29, 1u, &ServiceStatus) )
    {
      v35 = GetLastError();
      v36 = CurrentIP();
      v37 = ConstructPartialMsgW(0x4000000u, "Service %s stopped successfully.", (const char *)L"WinSetupBoot");
      v111 = v35;
      v109 = v36;
      v107 = 6639;
    }
    else
    {
      v38 = GetLastError();
      v39 = CurrentIP();
      v40 = GetLastError();
      v37 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to stop service %s. Error: 0x%08X",
              (const char *)L"WinSetupBoot",
              v40);
      v111 = v38;
      v109 = v39;
      v107 = 6643;
    }
    WdsSetupLogMessageW(
      v37,
      819200,
      L"D",
      0,
      v107,
      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
      L"CFinalizeSafeOSBootRemoval::DoExecute",
      v109,
      v111,
      0,
      0);
    if ( !DeleteService(v30) )
    {
      v62 = GetLastError();
      v63 = CurrentIP();
      v64 = GetLastError();
      v65 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to delete service %s. Error: 0x%08X",
              (const char *)L"WinSetupBoot",
              v64);
      WdsSetupLogMessageW(
        v65,
        819200,
        L"D",
        0,
        6669,
        L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
        L"CFinalizeSafeOSBootRemoval::DoExecute",
        v63,
        v62,
        0,
        0);
      goto LABEL_31;
    }
    v41 = GetLastError();
    v42 = CurrentIP();
    v43 = ConstructPartialMsgW(0x4000000u, "Service %s deleted successfully.", (const char *)L"WinSetupBoot");
    WdsSetupLogMessageW(
      v43,
      819200,
      L"D",
      0,
      6648,
      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
      L"CFinalizeSafeOSBootRemoval::DoExecute",
      v42,
      v41,
      0,
      0);
    v44 = (const struct UnBCL::String *)UnBCL::String::String(
                                          (UnBCL::String *)v125,
                                          L"%windir%\\System32\\drivers\\WinSetupBoot.sys");
    v45 = UnBCL::Environment::ExpandEnvironmentVariables(v44);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v114, v45);
    UnBCL::String::~String((UnBCL::String *)v125);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v114) )
    {
      v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
      v47 = UnBCL::String::get_CString(v46);
      if ( !(unsigned int)DeleteFileEx2(v47, 0) )
      {
        v53 = GetLastError();
        v54 = CurrentIP();
        v55 = GetLastError();
        v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
        v57 = (const char *)UnBCL::String::get_CString(v56);
        v58 = ConstructPartialMsgW(0x2000000u, "Failed to delete %s. Error: 0x%08X", v57, v55);
        WdsSetupLogMessageW(
          v58,
          819200,
          L"D",
          0,
          6659,
          L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
          L"CFinalizeSafeOSBootRemoval::DoExecute",
          v54,
          v53,
          0,
          0);
        v30 = hSCObject;
LABEL_29:
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v114);
LABEL_31:
        CloseServiceHandle(v30);
LABEL_32:
        CloseServiceHandle(v113);
        return 0;
      }
      v48 = GetLastError();
      v49 = CurrentIP();
      v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
      v51 = (const char *)UnBCL::String::get_CString(v50);
      v52 = ConstructPartialMsgW(0x4000000u, "Service binary %s deleted successfully.", v51);
      v112 = v48;
      v110 = v49;
      v108 = 6655;
    }
    else
    {
      v59 = GetLastError();
      v60 = CurrentIP();
      v61 = GetLastError();
      v52 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to determine service binary file path for %s. Error: 0x%08X",
              (const char *)L"WinSetupBoot",
              v61);
      v112 = v59;
      v110 = v60;
      v108 = 6664;
    }
    WdsSetupLogMessageW(
      v52,
      819200,
      L"D",
      0,
      v108,
      L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
      L"CFinalizeSafeOSBootRemoval::DoExecute",
      v110,
      v112,
      0,
      0);
    goto LABEL_29;
  }
  v67 = GetLastError();
  v68 = CurrentIP();
  v69 = ConstructPartialMsgW(
          0x4000000u,
          "FLOWTRACK: %hs: SafeOS boot removal was not executed, exiting",
          "CFinalizeSafeOSBootRemoval::DoExecute");
  WdsSetupLogMessageW(
    v69,
    819200,
    L"D",
    0,
    6488,
    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
    L"CFinalizeSafeOSBootRemoval::DoExecute",
    v68,
    v67,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x18013c5f0  mov     rax, rsp
0x18013c5f3  push    rdi
0x18013c5f4  push    r12
0x18013c5f6  push    r13
0x18013c5f8  push    r14
0x18013c5fa  push    r15
0x18013c5fc  sub     rsp, 170h
0x18013c603  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x18013c60b  mov     [rax+18h], rbx
0x18013c60f  mov     [rax+20h], rsi
0x18013c613  mov     rax, cs:__security_cookie
0x18013c61a  xor     rax, rsp
0x18013c61d  mov     [rsp+198h+var_38], rax
0x18013c625  mov     rsi, rdx
0x18013c628  mov     r15, rcx
0x18013c62b  xor     r14d, r14d
0x18013c62e  mov     edi, r14d
0x18013c631  mov     [rsp+198h+hSCObject], r14
0x18013c639  mov     rax, [rdx]
0x18013c63c  mov     rcx, rdx
0x18013c63f  mov     rax, [rax+48h]
0x18013c643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c648  mov     rbx, rax
0x18013c64b  test    rax, rax
0x18013c64e  jz      short loc_18013C691
0x18013c650  mov     rax, [rax]
0x18013c653  mov     rcx, rbx
0x18013c656  mov     rax, [rax+28h]
0x18013c65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c65f  test    eax, eax
0x18013c661  jnz     short loc_18013C691
0x18013c663  mov     rax, [rbx]
0x18013c666  mov     rcx, rbx
0x18013c669  mov     rax, [rax+30h]
0x18013c66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c672  test    rax, rax
0x18013c675  jz      short loc_18013C691
0x18013c677  mov     rax, [rbx]
0x18013c67a  mov     rcx, rbx
0x18013c67d  mov     rax, [rax+30h]
0x18013c681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c686  mov     rdi, rax
0x18013c689  mov     [rsp+198h+hSCObject], rax
0x18013c691  mov     rcx, [rsi]
0x18013c694  mov     rax, [rcx+28h]
0x18013c698  mov     rcx, rsi
0x18013c69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c6a0  cmp     eax, 4
0x18013c6a3  jl      loc_18013CEC0
0x18013c6a9  mov     r13d, r14d
0x18013c6ac  mov     [rsp+198h+var_134], r14d
0x18013c6b1  test    rdi, rdi
0x18013c6b4  jz      loc_18013C9B9
0x18013c6ba  mov     [rsp+198h+var_130], r14
0x18013c6bf  mov     [rsp+198h+var_118], r14
0x18013c6c7  mov     [rsp+198h+var_138], r14d
0x18013c6cc  lea     rcx, [rsp+198h+var_98]
0x18013c6d4  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x18013c6da  lea     rax, ??_7CXXXXXHandledException@?M@??DoExecute@CFinalizeSafeOSBootRemoval@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CFinalizeSafeOSBootRemoval::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`12'::CXXXXXHandledException::`vftable'
0x18013c6e1  mov     [rsp+198h+var_98], rax
0x18013c6e9  lea     rdi, [r15+0D0h]
0x18013c6f0  mov     rcx, rdi
0x18013c6f3  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013c6f9  test    rax, rax
0x18013c6fc  jz      loc_18013CF63
0x18013c702  lea     rcx, [rsp+198h+var_130]
0x18013c707  call    cs:__imp_BcdOpenSystemStore
0x18013c70d  mov     r15d, eax
0x18013c710  test    eax, eax
0x18013c712  js      loc_18013D004
0x18013c718  lea     rcx, [rsp+198h+var_128]
0x18013c71d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18013c723  nop
0x18013c724  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x18013c72b  lea     rcx, [rsp+198h+var_C0]
0x18013c733  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013c739  mov     rbx, rax
0x18013c73c  mov     rdx, [rsi]
0x18013c73f  mov     rcx, rsi
0x18013c742  mov     rax, [rdx]
0x18013c745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c74a  mov     rdx, rbx
0x18013c74d  mov     rcx, rax
0x18013c750  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18013c756  mov     rdx, rax
0x18013c759  lea     rcx, [rsp+198h+var_D0]
0x18013c761  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013c767  nop
0x18013c768  lea     rcx, [rsp+198h+var_C0]
0x18013c770  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013c776  lea     rcx, [rsp+198h+var_D0]
0x18013c77e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013c784  mov     rcx, rax
0x18013c787  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013c78d  mov     rbx, rax
0x18013c790  mov     rcx, rdi
0x18013c793  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013c799  mov     rcx, rax
0x18013c79c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013c7a2  mov     r8, rbx; lpFileName
0x18013c7a5  mov     rdx, rax; lpKeyName
0x18013c7a8  lea     rcx, aBootentries; "BootEntries"
0x18013c7af  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x18013c7b4  mov     rdx, rax
0x18013c7b7  lea     rcx, [rsp+198h+var_A8]
0x18013c7bf  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013c7c5  nop
0x18013c7c6  lea     rdx, [rsp+198h+var_A8]
0x18013c7ce  lea     rcx, [rsp+198h+var_128]
0x18013c7d3  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18013c7d9  nop
0x18013c7da  lea     rcx, [rsp+198h+var_A8]
0x18013c7e2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18013c7e8  lea     rcx, [rsp+198h+var_128]
0x18013c7ed  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013c7f3  test    rax, rax
0x18013c7f6  jz      loc_18013D0B2
0x18013c7fc  xorps   xmm0, xmm0
0x18013c7ff  movups  xmmword ptr [rsp+198h+ServiceStatus.dwServiceType], xmm0
0x18013c807  lea     rcx, [rsp+198h+var_128]
0x18013c80c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013c812  mov     rcx, rax
0x18013c815  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013c81b  lea     rdx, [rsp+198h+ServiceStatus]; struct _GUID *
0x18013c823  mov     rcx, rax; unsigned __int16 *
0x18013c826  call    ?SPGuidFromString@@YAJPEBGPEAU_GUID@@@Z; SPGuidFromString(ushort const *,_GUID *)
0x18013c82b  mov     ebx, eax
0x18013c82d  mov     [rsp+198h+var_134], eax
0x18013c831  test    eax, eax
0x18013c833  js      loc_18013D1C2
0x18013c839  lea     r8, [rsp+198h+var_118]
0x18013c841  lea     rdx, [rsp+198h+ServiceStatus]
0x18013c849  mov     rcx, [rsp+198h+var_130]
0x18013c84e  call    cs:__imp_BcdOpenObject
0x18013c854  mov     ebx, eax
0x18013c856  test    eax, eax
0x18013c858  js      loc_18013D27D
0x18013c85e  mov     edx, 14000008h
0x18013c863  mov     rcx, [rsp+198h+var_118]
0x18013c86b  call    cs:__imp_BcdDeleteElement
0x18013c871  mov     ebx, eax
0x18013c873  test    eax, eax
0x18013c875  jns     loc_18013D403
0x18013c87b  jmp     loc_18013D340
0x18013c880  lea     rcx, [rsp+198h+var_98]
0x18013c888  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x18013c88e  mov     r13d, [rsp+198h+var_134]
0x18013c893  xor     r14d, r14d
0x18013c896  test    r13d, r13d
0x18013c899  cmovs   r13d, r14d
0x18013c89d  lea     rdx, aMarkerSetup; "$MARKER.SETUP"
0x18013c8a4  lea     rcx, [rsp+198h+var_C0]
0x18013c8ac  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013c8b2  nop
0x18013c8b3  mov     rdx, rax
0x18013c8b6  mov     rcx, [rsp+198h+hSCObject]
0x18013c8be  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18013c8c4  mov     rdx, rax
0x18013c8c7  lea     rcx, [rsp+198h+ServiceStatus]
0x18013c8cf  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013c8d5  nop
0x18013c8d6  lea     rcx, [rsp+198h+var_C0]
0x18013c8de  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013c8e4  lea     rcx, [rsp+198h+ServiceStatus]
0x18013c8ec  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013c8f2  mov     rcx, rax
0x18013c8f5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013c8fb  mov     r9, rax; unsigned __int16 *
0x18013c8fe  lea     r8, aYes_1; "Yes"
0x18013c905  lea     rdx, aAlive; "Alive"
0x18013c90c  lea     rcx, aSetup; "Setup"
0x18013c913  call    ?SPWriteConfigValue@@YAHPEBG000@Z; SPWriteConfigValue(ushort const *,ushort const *,ushort const *,ushort const *)
0x18013c918  test    eax, eax
0x18013c91a  jnz     short loc_18013C99B
0x18013c91c  call    cs:__imp_GetLastError
0x18013c922  mov     edi, eax
0x18013c924  call    cs:__imp_CurrentIP
0x18013c92a  mov     rbx, rax
0x18013c92d  call    cs:__imp_GetLastError
0x18013c933  mov     r9d, eax
0x18013c936  lea     r8, aMarkerSetup; "$MARKER.SETUP"
0x18013c93d  lea     rdx, aFailedToWriteT_0; "Failed to write the %s marker. Error: 0"...
0x18013c944  mov     ecx, 3000000h; unsigned int
0x18013c949  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18013c94e  mov     [rsp+198h+var_148], r14d
0x18013c953  mov     [rsp+198h+var_150], r14
0x18013c958  mov     [rsp+198h+var_158], edi
0x18013c95c  mov     [rsp+198h+var_160], rbx
0x18013c961  lea     r15, aCfinalizesafeo; "CFinalizeSafeOSBootRemoval::DoExecute"
0x18013c968  mov     [rsp+198h+var_168], r15
0x18013c96d  lea     r12, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18013c974  mov     [rsp+198h+var_170], r12
0x18013c979  mov     dword ptr [rsp+198h+var_178], 19D2h
0x18013c981  xor     r9d, r9d
0x18013c984  lea     r8, aD_0; "D"
0x18013c98b  mov     edx, 0C8000h
0x18013c990  mov     rcx, rax
0x18013c993  call    cs:__imp_WdsSetupLogMessageW
0x18013c999  jmp     short loc_18013C9A9
0x18013c99b  lea     r15, aCfinalizesafeo; "CFinalizeSafeOSBootRemoval::DoExecute"
0x18013c9a2  lea     r12, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18013c9a9  lea     rcx, [rsp+198h+ServiceStatus]
0x18013c9b1  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18013c9b7  jmp     short loc_18013C9C7
0x18013c9b9  lea     r15, aCfinalizesafeo; "CFinalizeSafeOSBootRemoval::DoExecute"
0x18013c9c0  lea     r12, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18013c9c7  mov     ebx, 10020h
0x18013c9cc  mov     r8d, ebx; dwDesiredAccess
0x18013c9cf  xor     edx, edx; lpDatabaseName
0x18013c9d1  xor     ecx, ecx; lpMachineName
0x18013c9d3  call    cs:__imp_OpenSCManagerW
0x18013c9d9  mov     [rsp+198h+var_130], rax
0x18013c9de  test    rax, rax
0x18013c9e1  jnz     short loc_18013CA50
0x18013c9e3  call    cs:__imp_GetLastError
0x18013c9e9  mov     edi, eax
0x18013c9eb  call    cs:__imp_CurrentIP
0x18013c9f1  mov     rbx, rax
0x18013c9f4  call    cs:__imp_GetLastError
0x18013c9fa  mov     r8d, eax
0x18013c9fd  lea     rdx, aFailedToOpenSe; "Failed to open service control manager."...
0x18013ca04  mov     ecx, 2000000h; unsigned int
0x18013ca09  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18013ca0e  mov     [rsp+198h+var_148], r14d
0x18013ca13  mov     [rsp+198h+var_150], r14
0x18013ca18  mov     [rsp+198h+var_158], edi
0x18013ca1c  mov     [rsp+198h+var_160], rbx
0x18013ca21  mov     [rsp+198h+var_168], r15
0x18013ca26  mov     [rsp+198h+var_170], r12
0x18013ca2b  mov     dword ptr [rsp+198h+var_178], 19DBh
0x18013ca33  xor     r9d, r9d
0x18013ca36  lea     r8, aD_0; "D"
0x18013ca3d  mov     edx, 0C8000h
0x18013ca42  mov     rcx, rax
0x18013ca45  call    cs:__imp_WdsSetupLogMessageW
0x18013ca4b  jmp     loc_18013CEBB
0x18013ca50  mov     r8d, ebx; dwDesiredAccess
0x18013ca53  lea     rdx, ServiceName; "WinSetupBoot"
0x18013ca5a  mov     rcx, rax; hSCManager
0x18013ca5d  call    cs:__imp_OpenServiceW
0x18013ca63  mov     rsi, rax
0x18013ca66  mov     [rsp+198h+hSCObject], rax
0x18013ca6e  test    rax, rax
0x18013ca71  jnz     loc_18013CAF8
0x18013ca77  call    cs:__imp_GetLastError
0x18013ca7d  mov     esi, eax
0x18013ca7f  cmp     eax, 424h
0x18013ca84  jz      loc_18013CEB0
0x18013ca8a  call    cs:__imp_GetLastError
0x18013ca90  mov     edi, eax
0x18013ca92  call    cs:__imp_CurrentIP
0x18013ca98  mov     rbx, rax
0x18013ca9b  mov     r9d, esi
0x18013ca9e  lea     r8, ServiceName; "WinSetupBoot"
0x18013caa5  lea     rdx, aFailedToOpenSe_0; "Failed to open service %s. Error: 0x%08"...
0x18013caac  mov     ecx, 2000000h; unsigned int
0x18013cab1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18013cab6  mov     [rsp+198h+var_148], r14d
0x18013cabb  mov     [rsp+198h+var_150], r14
0x18013cac0  mov     [rsp+198h+var_158], edi
0x18013cac4  mov     [rsp+198h+var_160], rbx
0x18013cac9  mov     [rsp+198h+var_168], r15
0x18013cace  mov     [rsp+198h+var_170], r12
0x18013cad3  mov     dword ptr [rsp+198h+var_178], 19E7h
0x18013cadb  xor     r9d, r9d
0x18013cade  lea     r8, aD_0; "D"
0x18013cae5  mov     edx, 0C8000h
0x18013caea  mov     rcx, rax
0x18013caed  call    cs:__imp_WdsSetupLogMessageW
0x18013caf3  jmp     loc_18013CEB0
0x18013caf8  xorps   xmm0, xmm0
0x18013cafb  movups  xmmword ptr [rsp+198h+ServiceStatus.dwServiceType], xmm0
0x18013cb03  movups  xmmword ptr [rsp+198h+ServiceStatus.dwWin32ExitCode], xmm0
0x18013cb0b  lea     r8, [rsp+198h+ServiceStatus]; lpServiceStatus
0x18013cb13  mov     edx, 1; dwControl
0x18013cb18  mov     rcx, rsi; hService
0x18013cb1b  call    cs:__imp_ControlService
0x18013cb21  test    eax, eax
0x18013cb23  jz      short loc_18013CB75
0x18013cb25  call    cs:__imp_GetLastError
0x18013cb2b  mov     edi, eax
0x18013cb2d  call    cs:__imp_CurrentIP
0x18013cb33  mov     rbx, rax
0x18013cb36  lea     r8, ServiceName; "WinSetupBoot"
0x18013cb3d  lea     rdx, aServiceSStoppe; "Service %s stopped successfully."
0x18013cb44  mov     ecx, 4000000h; unsigned int
0x18013cb49  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18013cb4e  mov     [rsp+198h+var_148], r14d
0x18013cb53  mov     [rsp+198h+var_150], r14
0x18013cb58  mov     [rsp+198h+var_158], edi
0x18013cb5c  mov     [rsp+198h+var_160], rbx
0x18013cb61  mov     [rsp+198h+var_168], r15
0x18013cb66  mov     [rsp+198h+var_170], r12
0x18013cb6b  mov     dword ptr [rsp+198h+var_178], 19EFh
0x18013cb73  jmp     short loc_18013CBCC
0x18013cb75  call    cs:__imp_GetLastError
0x18013cb7b  mov     edi, eax
0x18013cb7d  call    cs:__imp_CurrentIP
0x18013cb83  mov     rbx, rax
0x18013cb86  call    cs:__imp_GetLastError
  ... truncated ...
```
