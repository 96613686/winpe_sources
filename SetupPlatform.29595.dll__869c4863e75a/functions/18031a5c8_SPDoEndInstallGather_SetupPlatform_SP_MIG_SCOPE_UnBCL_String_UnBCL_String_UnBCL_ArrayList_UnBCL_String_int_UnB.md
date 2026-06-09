# SPDoEndInstallGather(SetupPlatform::SP_MIG_SCOPE,UnBCL::String *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,int,UnBCL::String *,UnBCL::String *,UnBCL::String *,ISPTelemetryData * *,ISPMigProgress *)

- ea: `0x18031a5c8`
- end: `0x18031c070`
- name: `?SPDoEndInstallGather@@YA?AW4MIGSTATUS@@W4SP_MIG_SCOPE@SetupPlatform@@PEAVString@UnBCL@@1PEAV?$ArrayList@PEAVString@UnBCL@@@5@H111PEAPEAUISPTelemetryData@@PEAUISPMigProgress@@@Z`
- size: `6824`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, struct CSPTelemetryData *, int, int, int, struct ISPMigProgress *, int, char, int, int, char, int, int, __int64, __int64, char, int, int, int, __int64, __int64, int, __int64, __int64, char, CSPExecuteProgress *, __int64, int, char, int, int, int, int, int, struct CSPTelemetryData *, int, int, int, int, int, int, int, __int64, __int64, __int64, __int64, __int64, int, __int64, int, int, __int64, char, int, int, int, int, int, int, char, int, int, int, int, int, int, char, int, int, int, int, int, int, __int64, int, int, int, int, int, int, int, int, int, int, char, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, __int64, int, int, int, struct ISPMigProgress *)`
- caller_count: `1`
- callee_count: `27`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801fd6e0`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x18005dd8c`
- `0x1800b42d0`
- `0x18010f64c`
- `0x18012a5c0`
- `0x18012b0fc`
- `0x180131d68`
- `0x1801ee484`
- `0x180301454`
- `0x1803014c4`
- `0x18030158c`
- `0x180302740`
- `0x180302820`
- `0x180302f18`
- `0x180303a50`
- `0x180303c08`
- `0x180303c80`
- `0x180303cf8`
- `0x1803051c0`
- `0x1803051e8`
- `0x1803075ac`
- `0x18031a5c8`
- `0x180332e7c`
- `0x180337bbc`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18031a5ff`
- `KERNEL32!GetLastError` at `0x18031b2c4`
- `KERNEL32!GetLastError` at `0x18031b5d8`
- `KERNEL32!GetLastError` at `0x18031b806`
- `KERNEL32!GetLastError` at `0x18031b9e4`
- `KERNEL32!GetLastError` at `0x18031bb4a`
- `KERNEL32!GetLastError` at `0x18031bd77`
- `KERNEL32!GetLastError` at `0x18031be2c`
- `KERNEL32!GetLastError` at `0x18031bec8`
- `KERNEL32!GetLastError` at `0x18031bfd3`
- `KERNEL32!GetLastError` at `0x18031a5ff`
- `KERNEL32!GetLastError` at `0x18031b2c4`
- `KERNEL32!GetLastError` at `0x18031b5d8`
- `KERNEL32!GetLastError` at `0x18031b806`
- `KERNEL32!GetLastError` at `0x18031b9e4`
- `KERNEL32!GetLastError` at `0x18031bb4a`
- `KERNEL32!GetLastError` at `0x18031bd77`
- `KERNEL32!GetLastError` at `0x18031be2c`
- `KERNEL32!GetLastError` at `0x18031bec8`
- `KERNEL32!GetLastError` at `0x18031bfd3`
- `KERNEL32!SetCurrentDirectoryW` at `0x18031b264`
- `KERNEL32!SetCurrentDirectoryW` at `0x18031b264`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18031b1d5`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18031b1d5`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031ac4f`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031acf0`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031ac4f`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031acf0`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b1fc`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b3ae`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b4ae`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b53b`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b1fc`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b3ae`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b4ae`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18031b53b`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031b8da`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031b93f`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031b8da`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031b93f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18031b5b5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18031b5b5`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b4e7`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b505`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b574`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b58e`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b7a9`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b4e7`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b505`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b574`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b58e`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031b7a9`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x18031b9a3`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x18031b9a3`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031b22a`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18031b22a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031ac7a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031ad3b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031b662`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031ac7a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031ad3b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031b662`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a705`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a711`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a754`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a760`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a78a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a7b4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a7de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a808`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a832`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a85c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a886`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a8c2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a8ce`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a90a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a916`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a940`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a980`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a98c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a9b6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a9e0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aa10`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aa3a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aa64`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aaa4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aab0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aaf0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aafc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab26`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab50`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab90`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab9c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031abdf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031abeb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ac27`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ac33`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ac6c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031acc2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031acd1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ad2d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ad83`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ad92`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031add1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ade0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ae2c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ae3b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ae9c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aeab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aeee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031af55`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031af69`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031afa8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031afb7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031afff`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b00e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b04d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b05c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b08c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b0cf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b0de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b121`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b130`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b168`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b1ab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b1ba`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b247`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b5d2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a705`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a711`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a754`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a760`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a78a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a7b4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a7de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a808`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a832`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a85c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a886`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a8c2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a8ce`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a90a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a916`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a940`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a980`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a98c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a9b6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a9e0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aa10`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aa3a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aa64`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aaa4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aab0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aaf0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aafc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab26`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab50`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab90`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ab9c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031abdf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031abeb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ac27`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ac33`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ac6c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031acc2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031acd1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ad2d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ad83`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ad92`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031add1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ade0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ae2c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ae3b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031ae9c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aeab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031aeee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031af55`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031af69`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031afa8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031afb7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031afff`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b00e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b04d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b05c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b08c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b0cf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b0de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b121`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b130`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b168`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b1ab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b1ba`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b247`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031b5d2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031a6d7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031a6ec`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031a726`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031a73b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031a772`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18031a79c`

## string_xrefs

- `0x18031b211`: `SetupPlatform.dll`
- `0x18031abba`: `MIG_ALLOW_REPARSE_POINTS`
- `0x18031aa7f`: `MIG_CONTENT_COMPARE_ACLS`
- `0x18031a9e6`: `MIG_REPL_MANIFESTS_DIR`
- `0x18031a9bc`: `MIG_MANIFESTS`
- `0x18031a7ba`: `MIG_AGENT_DLL_FILTER`
- `0x18031b0fc`: `MIG_AGENT_DLL_FILTER`
- `0x18031ab6b`: `MIG_FILE_COMPARE`
- `0x18031a862`: `MIG_UPGRADE_AGENT_NO_DISCOVER`
- `0x18031a838`: `MIG_UPGRADE_CONFIG_SCRIPT`
- `0x18031bd90`: `Estimation completed. Number of events: %d`
- `0x18031aab6`: `COPYRAW`
- `0x18031b8ef`: `enum MIGSTATUS __cdecl SPDoEndInstallGather(enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x18031b954`: `enum MIGSTATUS __cdecl SPDoEndInstallGather(enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x18031b9b8`: `enum MIGSTATUS __cdecl SPDoEndInstallGather(enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x18031a63a`: `SPDoEndInstallGather`
- `0x18031b2ff`: `SPDoEndInstallGather`
- `0x18031b625`: `SPDoEndInstallGather`
- `0x18031b844`: `SPDoEndInstallGather`
- `0x18031bb3f`: `SPDoEndInstallGather`
- `0x18031bdb5`: `SPDoEndInstallGather`
- `0x18031a610`: `SPDoEndInstallGather`
- `0x18031b2d5`: `SPDoEndInstallGather`
- `0x18031b81a`: `SPDoEndInstallGather`
- `0x18031b9f8`: `SPDoEndInstallGather`
- `0x18031be40`: `SPDoEndInstallGather`
- `0x18031bedc`: `SPDoEndInstallGather`
- `0x18031bfe7`: `SPDoEndInstallGather`
- `0x18031adac`: `MIG_CONVERT_SECURITY_SID_CONSTANTS`
- `0x18031acd7`: `MIG_PLUGIN_CALL_TIMEOUT_INTERVALS`
- `0x18031ad5e`: `MIG_PLUGIN_CALL_TIMEOUT_INTERVALS`
- `0x18031ac02`: `MIG_REPORT_PLUGIN_FAILURES_NEW`
- `0x18031ac39`: `MIG_PLUGIN_CALL_TIMEOUT`
- `0x18031ac9d`: `MIG_PLUGIN_CALL_TIMEOUT`
- `0x18031a6cb`: `End Install gather`
- `0x18031b16e`: `uninstall.xml`
- `0x18031b594`: `Uninstall.IMG`
- `0x18031b0e4`: `mxeagent.dll;csiagent.dll`
- `0x18031b143`: `MIG_XML_PHASE_FILTER`
- `0x18031b092`: `uninstall`
- `0x18031ae07`: `MIG_CONFIG_ENV_0`
- `0x18031b600`: `Upgrade store full path is: %s`
- `0x18031be47`: `%hs: Cannot create the IMG store. Error: 0x%08X`

## pseudocode

```c

```

## disassembly

```asm
0x18031a5c8  mov     rax, rsp
0x18031a5cb  mov     [rax+20h], r9
0x18031a5cf  mov     [rax+18h], r8
0x18031a5d3  push    rsi
0x18031a5d4  push    rdi
0x18031a5d5  push    r12
0x18031a5d7  push    r14
0x18031a5d9  push    r15
0x18031a5db  sub     rsp, 300h
0x18031a5e2  mov     qword ptr [rax-80h], 0FFFFFFFFFFFFFFFEh
0x18031a5ea  mov     [rax+8], rbx
0x18031a5ee  mov     r12, rdx
0x18031a5f1  mov     r14d, ecx
0x18031a5f4  xor     esi, esi
0x18031a5f6  mov     r15d, esi
0x18031a5f9  mov     [rax-270h], esi
0x18031a5ff  call    cs:__imp_GetLastError
0x18031a605  mov     edi, eax
0x18031a607  call    cs:__imp_CurrentIP
0x18031a60d  mov     rbx, rax
0x18031a610  lea     r8, aSpdoendinstall_1; "SPDoEndInstallGather"
0x18031a617  lea     rdx, aHsBeginRun; "%hs: Begin run"
0x18031a61e  mov     ecx, 4000000h; unsigned int
0x18031a623  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18031a628  mov     dword ptr [rsp+328h+var_2D8], esi
0x18031a62c  mov     [rsp+328h+var_2E0], rsi
0x18031a631  mov     [rsp+328h+var_2E8], edi
0x18031a635  mov     [rsp+328h+var_2F0], rbx
0x18031a63a  lea     rcx, aSpdoendinstall; "SPDoEndInstallGather"
0x18031a641  mov     [rsp+328h+var_2F8], rcx
0x18031a646  lea     rcx, aBaseNtsetupSet_40; "base\\ntsetup\\setupplatform\\lib\\util"...
0x18031a64d  mov     [rsp+328h+var_300], rcx
0x18031a652  mov     [rsp+328h+var_308], 1744h
0x18031a65a  xor     r9d, r9d
0x18031a65d  lea     r8, aD_0; "D"
0x18031a664  mov     edx, 0C8000h
0x18031a669  mov     rcx, rax
0x18031a66c  call    cs:__imp_WdsSetupLogMessageW
0x18031a672  mov     [rsp+328h+arg_18], esi
0x18031a679  mov     ecx, 80h
0x18031a67e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18031a684  mov     [rsp+328h+var_248], rax
0x18031a68c  test    rax, rax
0x18031a68f  jz      short loc_18031A69B
0x18031a691  mov     rcx, rax; this
0x18031a694  call    ??0CSPTelemetryData@@QEAA@XZ; CSPTelemetryData::CSPTelemetryData(void)
0x18031a699  jmp     short loc_18031A69E
0x18031a69b  mov     rax, rsi
0x18031a69e  mov     rdx, rax
0x18031a6a1  lea     rcx, [rsp+328h+var_1F8]
0x18031a6a9  call    ??0?$SmartPtr@VCSPTelemetryData@@@UnBCL@@QEAA@PEAVCSPTelemetryData@@@Z; UnBCL::SmartPtr<CSPTelemetryData>::SmartPtr<CSPTelemetryData>(CSPTelemetryData *)
0x18031a6ae  nop
0x18031a6af  cmp     [rsp+328h+arg_28], rsi
0x18031a6b7  jz      loc_18031B8B5
0x18031a6bd  cmp     qword ptr [rsp+328h+arg_30], rsi
0x18031a6c5  jz      loc_18031B91A
0x18031a6cb  lea     rdx, aEndInstallGath; "End Install gather"
0x18031a6d2  lea     rcx, [rsp+328h+var_2B0]
0x18031a6d7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a6dd  mov     rbx, rax
0x18031a6e0  lea     rdx, aMigDiagSession; "MIG_DIAG_SESSION_NAME"
0x18031a6e7  lea     rcx, [rsp+328h+var_2C8]
0x18031a6ec  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a6f2  nop
0x18031a6f3  mov     rdx, rbx
0x18031a6f6  mov     rcx, rax
0x18031a6f9  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a6ff  nop
0x18031a700  lea     rcx, [rsp+328h+var_2C8]
0x18031a705  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a70b  nop
0x18031a70c  lea     rcx, [rsp+328h+var_2B0]
0x18031a711  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a717  lea     rdi, Value; "1"
0x18031a71e  mov     rdx, rdi
0x18031a721  lea     rcx, [rsp+328h+var_2B0]
0x18031a726  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a72c  mov     rbx, rax
0x18031a72f  lea     rdx, aMigDiagShellFo; "MIG_DIAG_SHELL_FOLDERS"
0x18031a736  lea     rcx, [rsp+328h+var_2C8]
0x18031a73b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a741  nop
0x18031a742  mov     rdx, rbx
0x18031a745  mov     rcx, rax
0x18031a748  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a74e  nop
0x18031a74f  lea     rcx, [rsp+328h+var_2C8]
0x18031a754  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a75a  nop
0x18031a75b  lea     rcx, [rsp+328h+var_2B0]
0x18031a760  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a766  lea     rdx, aMigCmiMachineS; "MIG_CMI_MACHINE_SPECIFIC"
0x18031a76d  lea     rcx, [rsp+328h+var_2C8]
0x18031a772  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a778  nop
0x18031a779  xor     edx, edx
0x18031a77b  mov     rcx, rax
0x18031a77e  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a784  nop
0x18031a785  lea     rcx, [rsp+328h+var_2C8]
0x18031a78a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a790  lea     rdx, aMigCmiInnerSec; "MIG_CMI_INNER_SECTION"
0x18031a797  lea     rcx, [rsp+328h+var_2C8]
0x18031a79c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a7a2  nop
0x18031a7a3  xor     edx, edx
0x18031a7a5  mov     rcx, rax
0x18031a7a8  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a7ae  nop
0x18031a7af  lea     rcx, [rsp+328h+var_2C8]
0x18031a7b4  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a7ba  lea     rdx, aMigAgentDllFil; "MIG_AGENT_DLL_FILTER"
0x18031a7c1  lea     rcx, [rsp+328h+var_2C8]
0x18031a7c6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a7cc  nop
0x18031a7cd  xor     edx, edx
0x18031a7cf  mov     rcx, rax
0x18031a7d2  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a7d8  nop
0x18031a7d9  lea     rcx, [rsp+328h+var_2C8]
0x18031a7de  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a7e4  lea     rdx, aMigrationScrip_0; "MIGRATION_SCRIPT_FILES"
0x18031a7eb  lea     rcx, [rsp+328h+var_2C8]
0x18031a7f0  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a7f6  nop
0x18031a7f7  xor     edx, edx
0x18031a7f9  mov     rcx, rax
0x18031a7fc  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a802  nop
0x18031a803  lea     rcx, [rsp+328h+var_2C8]
0x18031a808  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a80e  lea     rdx, aMigUpgradeScri; "MIG_UPGRADE_SCRIPTS"
0x18031a815  lea     rcx, [rsp+328h+var_2C8]
0x18031a81a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a820  nop
0x18031a821  xor     edx, edx
0x18031a823  mov     rcx, rax
0x18031a826  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a82c  nop
0x18031a82d  lea     rcx, [rsp+328h+var_2C8]
0x18031a832  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a838  lea     rdx, aMigUpgradeConf; "MIG_UPGRADE_CONFIG_SCRIPT"
0x18031a83f  lea     rcx, [rsp+328h+var_2C8]
0x18031a844  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a84a  nop
0x18031a84b  xor     edx, edx
0x18031a84d  mov     rcx, rax
0x18031a850  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a856  nop
0x18031a857  lea     rcx, [rsp+328h+var_2C8]
0x18031a85c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a862  lea     rdx, aMigUpgradeAgen; "MIG_UPGRADE_AGENT_NO_DISCOVER"
0x18031a869  lea     rcx, [rsp+328h+var_2C8]
0x18031a86e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a874  nop
0x18031a875  xor     edx, edx
0x18031a877  mov     rcx, rax
0x18031a87a  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a880  nop
0x18031a881  lea     rcx, [rsp+328h+var_2C8]
0x18031a886  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a88c  mov     rdx, rdi
0x18031a88f  lea     rcx, [rsp+328h+var_2B0]
0x18031a894  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a89a  mov     rbx, rax
0x18031a89d  lea     rdx, aMigUpgrade; "MIG_UPGRADE"
0x18031a8a4  lea     rcx, [rsp+328h+var_2C8]
0x18031a8a9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a8af  nop
0x18031a8b0  mov     rdx, rbx
0x18031a8b3  mov     rcx, rax
0x18031a8b6  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a8bc  nop
0x18031a8bd  lea     rcx, [rsp+328h+var_2C8]
0x18031a8c2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a8c8  nop
0x18031a8c9  lea     rcx, [rsp+328h+var_2B0]
0x18031a8ce  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a8d4  mov     rdx, rdi
0x18031a8d7  lea     rcx, [rsp+328h+var_2B0]
0x18031a8dc  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a8e2  mov     rbx, rax
0x18031a8e5  lea     rdx, aMigOsdbCheckWi; "MIG_OSDB_CHECK_WINSXS"
0x18031a8ec  lea     rcx, [rsp+328h+var_2C8]
0x18031a8f1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a8f7  nop
0x18031a8f8  mov     rdx, rbx
0x18031a8fb  mov     rcx, rax
0x18031a8fe  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a904  nop
0x18031a905  lea     rcx, [rsp+328h+var_2C8]
0x18031a90a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a910  nop
0x18031a911  lea     rcx, [rsp+328h+var_2B0]
0x18031a916  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a91c  lea     rdx, aMigUpgradeOpti; "MIG_UPGRADE_OPTIMIZE_GAC_MIGRATION"
0x18031a923  lea     rcx, [rsp+328h+var_2C8]
0x18031a928  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a92e  nop
0x18031a92f  xor     edx, edx
0x18031a931  mov     rcx, rax
0x18031a934  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a93a  nop
0x18031a93b  lea     rcx, [rsp+328h+var_2C8]
0x18031a940  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a946  lea     rdx, aNo; "No"
0x18031a94d  lea     rcx, [rsp+328h+var_2B0]
0x18031a952  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a958  mov     rbx, rax
0x18031a95b  lea     rdx, aMigUseProcessE; "MIG_USE_PROCESS_ENV"
0x18031a962  lea     rcx, [rsp+328h+var_2C8]
0x18031a967  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a96d  nop
0x18031a96e  mov     rdx, rbx
0x18031a971  mov     rcx, rax
0x18031a974  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a97a  nop
0x18031a97b  lea     rcx, [rsp+328h+var_2C8]
0x18031a980  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a986  nop
0x18031a987  lea     rcx, [rsp+328h+var_2B0]
0x18031a98c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a992  lea     rdx, aMigDisableCont; "MIG_DISABLE_CONTENT_REMAP"
0x18031a999  lea     rcx, [rsp+328h+var_2C8]
0x18031a99e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a9a4  nop
0x18031a9a5  xor     edx, edx
0x18031a9a7  mov     rcx, rax
0x18031a9aa  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a9b0  nop
0x18031a9b1  lea     rcx, [rsp+328h+var_2C8]
0x18031a9b6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a9bc  lea     rdx, aMigManifests; "MIG_MANIFESTS"
0x18031a9c3  lea     rcx, [rsp+328h+var_2C8]
0x18031a9c8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a9ce  nop
0x18031a9cf  xor     edx, edx
0x18031a9d1  mov     rcx, rax
0x18031a9d4  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031a9da  nop
0x18031a9db  lea     rcx, [rsp+328h+var_2C8]
0x18031a9e0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031a9e6  lea     rdx, aMigReplManifes; "MIG_REPL_MANIFESTS_DIR"
0x18031a9ed  lea     rcx, [rsp+328h+var_2C8]
0x18031a9f2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031a9f8  nop
0x18031a9f9  mov     rdx, qword ptr [rsp+328h+arg_38]
0x18031aa01  mov     rcx, rax
0x18031aa04  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031aa0a  nop
0x18031aa0b  lea     rcx, [rsp+328h+var_2C8]
0x18031aa10  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031aa16  lea     rdx, aMigrationScrip_0; "MIGRATION_SCRIPT_FILES"
0x18031aa1d  lea     rcx, [rsp+328h+var_2C8]
0x18031aa22  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031aa28  nop
0x18031aa29  xor     edx, edx
0x18031aa2b  mov     rcx, rax
0x18031aa2e  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031aa34  nop
0x18031aa35  lea     rcx, [rsp+328h+var_2C8]
0x18031aa3a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031aa40  lea     rdx, aMigrationScrip; "MIGRATION_SCRIPT_DIR"
0x18031aa47  lea     rcx, [rsp+328h+var_2C8]
0x18031aa4c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031aa52  nop
0x18031aa53  xor     edx, edx
0x18031aa55  mov     rcx, rax
0x18031aa58  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031aa5e  nop
0x18031aa5f  lea     rcx, [rsp+328h+var_2C8]
0x18031aa64  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031aa6a  lea     rdx, a0; "0"
0x18031aa71  lea     rcx, [rsp+328h+var_2B0]
0x18031aa76  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031aa7c  mov     rbx, rax
0x18031aa7f  lea     rdx, aMigContentComp; "MIG_CONTENT_COMPARE_ACLS"
0x18031aa86  lea     rcx, [rsp+328h+var_2C8]
0x18031aa8b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031aa91  nop
0x18031aa92  mov     rdx, rbx
0x18031aa95  mov     rcx, rax
0x18031aa98  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031aa9e  nop
0x18031aa9f  lea     rcx, [rsp+328h+var_2C8]
0x18031aaa4  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031aaaa  nop
0x18031aaab  lea     rcx, [rsp+328h+var_2B0]
0x18031aab0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031aab6  lea     rdx, aCopyraw; "COPYRAW"
0x18031aabd  lea     rcx, [rsp+328h+var_2B0]
0x18031aac2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031aac8  mov     rbx, rax
0x18031aacb  lea     rdx, aMigEfsMode; "MIG_EFS_MODE"
0x18031aad2  lea     rcx, [rsp+328h+var_2C8]
0x18031aad7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031aadd  nop
0x18031aade  mov     rdx, rbx
0x18031aae1  mov     rcx, rax
0x18031aae4  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
  ... truncated ...
```
