# SPDoEndInstallApply(UnBCL::String *,SetupPlatform::SP_MIG_SCOPE,UnBCL::String *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,int,UnBCL::String *,UnBCL::String *,UnBCL::String *,ISPTelemetryData * *,ISPMigProgress *)

- ea: `0x180317c20`
- end: `0x18031a5c2`
- name: `?SPDoEndInstallApply@@YA?AW4MIGSTATUS@@PEAVString@UnBCL@@W4SP_MIG_SCOPE@SetupPlatform@@00PEAV?$ArrayList@PEAVString@UnBCL@@@3@H000PEAPEAUISPTelemetryData@@PEAUISPMigProgress@@@Z`
- size: `10658`
- prototype: `void __fastcall __noreturn(int, int, int, int, bool, struct CSPTelemetryData *, int, int, int, struct UnBCL::String *, int, int, char, int, int, char, __int64, int, __int64, int, __int64, __int64, __int64, __int64, __int64, char, int, int, int, int, int, __int64, int, int, __int64, int, __int64, __int64, __int64, char, int, char, int, int, int, char, struct CSPTelemetryData *, int, int, int, int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int, __int64, int, int, int, int, int, int, __int64, __int64, __int64, __int64, int, int, int, int, int, int, char, int, int, int, int, int, int, __int64, int, int, int, int, int, int, __int64, int, int, int, int, int, int, char, int, int, int, int, int, int, int, int, int, int, int, __int64, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `32`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802a6aa0`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180044754`
- `0x180044810`
- `0x180044820`
- `0x180057dec`
- `0x18005dd8c`
- `0x1800b42d0`
- `0x18011bc64`
- `0x18012a5c0`
- `0x18012b0fc`
- `0x180131d68`
- `0x1801556c4`
- `0x18015dc78`
- `0x1802c7f84`
- `0x1803014c4`
- `0x18030158c`
- `0x180302820`
- `0x180302f18`
- `0x180303b90`
- `0x180303d98`
- `0x180303de8`
- `0x180303e60`
- `0x180303ed8`
- `0x180303f28`
- `0x1803051c0`
- `0x1803051e8`
- `0x180317914`
- `0x180317c20`
- `0x180332e7c`
- `0x18033e4f4`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180317c54`
- `KERNEL32!GetLastError` at `0x180318a4f`
- `KERNEL32!GetLastError` at `0x180318af2`
- `KERNEL32!GetLastError` at `0x180318b64`
- `KERNEL32!GetLastError` at `0x180318c72`
- `KERNEL32!GetLastError` at `0x1803190b2`
- `KERNEL32!GetLastError` at `0x180319340`
- `KERNEL32!GetLastError` at `0x180319624`
- `KERNEL32!GetLastError` at `0x1803196bd`
- `KERNEL32!GetLastError` at `0x1803199d1`
- `KERNEL32!GetLastError` at `0x180319c0a`
- `KERNEL32!GetLastError` at `0x180319ea8`
- `KERNEL32!GetLastError` at `0x180319f5b`
- `KERNEL32!GetLastError` at `0x18031a031`
- `KERNEL32!GetLastError` at `0x18031a0d6`
- `KERNEL32!GetLastError` at `0x18031a149`
- `KERNEL32!GetLastError` at `0x18031a201`
- `KERNEL32!GetLastError` at `0x18031a2ac`
- `KERNEL32!GetLastError` at `0x18031a354`
- `KERNEL32!GetLastError` at `0x18031a3fc`
- `KERNEL32!GetLastError` at `0x18031a528`
- `KERNEL32!GetLastError` at `0x180317c54`
- `KERNEL32!GetLastError` at `0x180318a4f`
- `KERNEL32!GetLastError` at `0x180318af2`
- `KERNEL32!GetLastError` at `0x180318b64`
- `KERNEL32!GetLastError` at `0x180318c72`
- `KERNEL32!GetLastError` at `0x1803190b2`
- `KERNEL32!GetLastError` at `0x180319340`
- `KERNEL32!GetLastError` at `0x180319624`
- `KERNEL32!GetLastError` at `0x1803196bd`
- `KERNEL32!GetLastError` at `0x1803199d1`
- `KERNEL32!GetLastError` at `0x180319c0a`
- `KERNEL32!GetLastError` at `0x180319ea8`
- `KERNEL32!GetLastError` at `0x180319f5b`
- `KERNEL32!GetLastError` at `0x18031a031`
- `KERNEL32!GetLastError` at `0x18031a0d6`
- `KERNEL32!GetLastError` at `0x18031a149`
- `KERNEL32!GetLastError` at `0x18031a201`
- `KERNEL32!GetLastError` at `0x18031a2ac`
- `KERNEL32!GetLastError` at `0x18031a354`
- `KERNEL32!GetLastError` at `0x18031a3fc`
- `KERNEL32!GetLastError` at `0x18031a528`
- `KERNEL32!SetCurrentDirectoryW` at `0x180318a14`
- `KERNEL32!SetCurrentDirectoryW` at `0x180318a14`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x180318985`
- `unbcl!?GetCurrentDir@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x180318985`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1803183e2`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180318489`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1803183e2`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180318489`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1803189ac`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318d66`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318de3`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318e74`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318f2b`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318f7f`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318fed`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1803189ac`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318d66`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318de3`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318e74`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318f2b`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318f7f`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180318fed`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180319d89`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180319dc4`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180319d89`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180319dc4`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180319418`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031947d`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1803194e2`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180319418`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18031947d`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1803194e2`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180318c4c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180318c4c`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180318e1c`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180318e36`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180318ef5`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180319029`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1803191db`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180319223`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180319240`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031931b`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180318e1c`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180318e36`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180318ef5`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180319029`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1803191db`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180319223`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180319240`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18031931b`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x180319546`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x180319546`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1803189da`
- `unbcl!?GetLoadedModuleDir@Directory@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1803189da`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180318386`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031840d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803184dd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180318cf3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180318386`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18031840d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803184dd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180318cf3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317d7d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317d8c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317db6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317de0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e0a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e34`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e5e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e88`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317eb2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317ef5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f04`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f47`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f56`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f80`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317fc3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317fd2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317ffc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318026`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318050`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318080`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803180aa`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803180d4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318117`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318126`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318169`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318178`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803181bb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803181ca`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803181f4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031821e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318261`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318270`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803182b3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803182c2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318305`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318314`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318357`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318366`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803183ba`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803183ff`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031845b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031846a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803184cf`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031852b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031853a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031858c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031859b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318602`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318611`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031865a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803186cb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803186df`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318728`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318737`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031878d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031879c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803187e5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803187f4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318824`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031886d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031887c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803188c5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803188d4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318912`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031895b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031896a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803189f7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318c6c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a1fb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a2a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a34e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a3f6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18031a49e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317d7d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317d8c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317db6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317de0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e0a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e34`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e5e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317e88`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317eb2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317ef5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f04`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f47`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f56`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317f80`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317fc3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317fd2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180317ffc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318026`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318050`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318080`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803180aa`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1803180d4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180318117`

## string_xrefs

- `0x1803189c1`: `SetupPlatform.dll`
- `0x18031a2c5`: `registry`
- `0x18031a2ef`: `   Registry: %d`
- `0x1803182e0`: `MIG_ALLOW_REPARSE_POINTS`
- `0x1803180f2`: `MIG_CONTENT_COMPARE_ACLS`
- `0x180318056`: `MIG_REPL_MANIFESTS_DIR`
- `0x180318002`: `MIG_MANIFESTS`
- `0x18031802c`: `MIG_MANIFESTS_DIR`
- `0x180317de6`: `MIG_AGENT_DLL_FILTER`
- `0x18031889a`: `MIG_AGENT_DLL_FILTER`
- `0x18031828e`: `MIG_FILE_COMPARE`
- `0x180317e8e`: `MIG_UPGRADE_AGENT_NO_DISCOVER`
- `0x180317e64`: `MIG_UPGRADE_CONFIG_SCRIPT`
- `0x18031817e`: `COPYRAW`
- `0x180318470`: `MIG_PLUGIN_CALL_TIMEOUT_INTERVALS`
- `0x180318500`: `MIG_PLUGIN_CALL_TIMEOUT_INTERVALS`
- `0x180318332`: `MIG_REPORT_PLUGIN_FAILURES_NEW`
- `0x1803183cc`: `MIG_PLUGIN_CALL_TIMEOUT`
- `0x180318430`: `MIG_PLUGIN_CALL_TIMEOUT`
- `0x180318918`: `uninstall.xml`
- `0x180318c2b`: `Uninstall.IMG`
- `0x180318882`: `mxeagent.dll;csiagent.dll`
- `0x1803188e7`: `MIG_XML_PHASE_FILTER`
- `0x18031882a`: `uninstall`
- `0x180318561`: `MIG_CONFIG_ENV_0`
- `0x180317d40`: `End Install apply`
- `0x180318144`: `MIG_COMPARE_LOGICAL_CONTENT`
- `0x180317c65`: `SPDoEndInstallApply`
- `0x180318a7d`: `SPDoEndInstallApply`
- `0x180318b06`: `SPDoEndInstallApply`
- `0x180318b86`: `SPDoEndInstallApply`
- `0x180319359`: `SPDoEndInstallApply`
- `0x180319595`: `SPDoEndInstallApply`
- `0x180319638`: `SPDoEndInstallApply`
- `0x1803196d1`: `SPDoEndInstallApply`
- `0x180319ebc`: `SPDoEndInstallApply`
- `0x180319f6f`: `SPDoEndInstallApply`
- `0x18031a045`: `SPDoEndInstallApply`
- `0x18031a53c`: `SPDoEndInstallApply`
- `0x18031942d`: `enum MIGSTATUS __cdecl SPDoEndInstallApply(class UnBCL::String *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x180319492`: `enum MIGSTATUS __cdecl SPDoEndInstallApply(class UnBCL::String *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x1803194f7`: `enum MIGSTATUS __cdecl SPDoEndInstallApply(class UnBCL::String *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x18031955b`: `enum MIGSTATUS __cdecl SPDoEndInstallApply(class UnBCL::String *,enum SetupPlatform::SP_MIG_SCOPE,class UnBCL::String *,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,int,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,struct ISPTelemetryData **,struct ISPMigProgress *)`
- `0x180317c8f`: `SPDoEndInstallApply`
- `0x180319199`: `SPDoEndInstallApply`
- `0x180319385`: `SPDoEndInstallApply`
- `0x180319ab2`: `SPDoEndInstallApply`
- `0x180319c61`: `SPDoEndInstallApply`
- `0x180319ee6`: `SPDoEndInstallApply`
- `0x180319f99`: `SPDoEndInstallApply`
- `0x18031a06f`: `SPDoEndInstallApply`
- `0x18031a10a`: `SPDoEndInstallApply`
- `0x18031a1c0`: `SPDoEndInstallApply`
- `0x18031a26b`: `SPDoEndInstallApply`
- `0x18031a313`: `SPDoEndInstallApply`
- `0x18031a3bb`: `SPDoEndInstallApply`
- `0x18031a463`: `SPDoEndInstallApply`
- `0x180318c9d`: `Upgrade store full path is: %s`
- `0x18031a0e7`: `Apply statistics: end install`
- `0x180319167`: `%hs: User %s%s%s%s from the new system does not have an equivalent on the old OS. Will not be restored.SPDoEndInstallApply`
- `0x180319a83`: `%hs: User %s%s%s%s from the new system does not have a profile on the old OS. Will not be restored.SPDoEndInstallApply`
- `0x1803196d8`: `%hs: Cannot open the UNC store. Error: 0x%08X`

## pseudocode

```c

```

## disassembly

```asm
0x180317c20  mov     rax, rsp
0x180317c23  mov     [rax+20h], r9
0x180317c27  mov     [rax+18h], r8
0x180317c2b  mov     [rax+8], rcx
0x180317c2f  push    rbx
0x180317c30  push    rsi
0x180317c31  push    rdi
0x180317c32  push    r12
0x180317c34  push    r13
0x180317c36  push    r14
0x180317c38  push    r15
0x180317c3a  sub     rsp, 3D0h
0x180317c41  mov     qword ptr [rax-90h], 0FFFFFFFFFFFFFFFEh
0x180317c4c  mov     r14d, edx
0x180317c4f  xor     esi, esi
0x180317c51  mov     [rax+58h], esi
0x180317c54  call    cs:__imp_GetLastError
0x180317c5a  mov     edi, eax
0x180317c5c  call    cs:__imp_CurrentIP
0x180317c62  mov     rbx, rax
0x180317c65  lea     r8, aSpdoendinstall_2; "SPDoEndInstallApply"
0x180317c6c  lea     rdx, aHsBeginRun; "%hs: Begin run"
0x180317c73  mov     ecx, 4000000h; unsigned int
0x180317c78  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180317c7d  mov     dword ptr [rsp+408h+var_3B8], esi
0x180317c81  mov     [rsp+408h+var_3C0], rsi
0x180317c86  mov     [rsp+408h+var_3C8], edi
0x180317c8a  mov     [rsp+408h+var_3D0], rbx
0x180317c8f  lea     r15, aSpdoendinstall_0; "SPDoEndInstallApply"
0x180317c96  mov     [rsp+408h+var_3D8], r15
0x180317c9b  lea     rcx, aBaseNtsetupSet_40; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180317ca2  mov     [rsp+408h+var_3E0], rcx
0x180317ca7  mov     dword ptr [rsp+408h+var_3E8], 1901h
0x180317caf  xor     r9d, r9d
0x180317cb2  lea     r12, aD_0; "D"
0x180317cb9  mov     r8, r12
0x180317cbc  mov     r13d, 0C8000h
0x180317cc2  mov     edx, r13d
0x180317cc5  mov     rcx, rax
0x180317cc8  call    cs:__imp_WdsSetupLogMessageW
0x180317cce  mov     [rsp+408h+arg_20], sil
0x180317cd6  mov     dword ptr [rsp+408h+arg_48], esi
0x180317cdd  mov     ecx, 80h
0x180317ce2  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180317ce8  mov     [rsp+408h+var_340], rax
0x180317cf0  test    rax, rax
0x180317cf3  jz      short loc_180317CFF
0x180317cf5  mov     rcx, rax; this
0x180317cf8  call    ??0CSPTelemetryData@@QEAA@XZ; CSPTelemetryData::CSPTelemetryData(void)
0x180317cfd  jmp     short loc_180317D02
0x180317cff  mov     rax, rsi
0x180317d02  mov     rdx, rax
0x180317d05  lea     rcx, [rsp+408h+var_298]
0x180317d0d  call    ??0?$SmartPtr@VCSPTelemetryData@@@UnBCL@@QEAA@PEAVCSPTelemetryData@@@Z; UnBCL::SmartPtr<CSPTelemetryData>::SmartPtr<CSPTelemetryData>(CSPTelemetryData *)
0x180317d12  nop
0x180317d13  mov     rdi, [rsp+408h+arg_0]
0x180317d1b  test    rdi, rdi
0x180317d1e  jz      loc_1803193F5
0x180317d24  cmp     qword ptr [rsp+408h+arg_30], rsi
0x180317d2c  jz      loc_180319458
0x180317d32  cmp     qword ptr [rsp+408h+arg_38], rsi
0x180317d3a  jz      loc_1803194BD
0x180317d40  lea     rdx, aEndInstallAppl; "End Install apply"
0x180317d47  lea     rcx, [rsp+408h+var_388]
0x180317d4f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317d55  mov     rbx, rax
0x180317d58  lea     rdx, aMigDiagSession; "MIG_DIAG_SESSION_NAME"
0x180317d5f  lea     rcx, [rsp+408h+var_3A0]
0x180317d64  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317d6a  nop
0x180317d6b  mov     rdx, rbx
0x180317d6e  mov     rcx, rax
0x180317d71  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317d77  nop
0x180317d78  lea     rcx, [rsp+408h+var_3A0]
0x180317d7d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317d83  nop
0x180317d84  lea     rcx, [rsp+408h+var_388]
0x180317d8c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317d92  lea     rdx, aMigCmiMachineS; "MIG_CMI_MACHINE_SPECIFIC"
0x180317d99  lea     rcx, [rsp+408h+var_3A0]
0x180317d9e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317da4  nop
0x180317da5  xor     edx, edx
0x180317da7  mov     rcx, rax
0x180317daa  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317db0  nop
0x180317db1  lea     rcx, [rsp+408h+var_3A0]
0x180317db6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317dbc  lea     rdx, aMigCmiInnerSec; "MIG_CMI_INNER_SECTION"
0x180317dc3  lea     rcx, [rsp+408h+var_3A0]
0x180317dc8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317dce  nop
0x180317dcf  xor     edx, edx
0x180317dd1  mov     rcx, rax
0x180317dd4  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317dda  nop
0x180317ddb  lea     rcx, [rsp+408h+var_3A0]
0x180317de0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317de6  lea     rdx, aMigAgentDllFil; "MIG_AGENT_DLL_FILTER"
0x180317ded  lea     rcx, [rsp+408h+var_3A0]
0x180317df2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317df8  nop
0x180317df9  xor     edx, edx
0x180317dfb  mov     rcx, rax
0x180317dfe  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317e04  nop
0x180317e05  lea     rcx, [rsp+408h+var_3A0]
0x180317e0a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317e10  lea     rdx, aMigrationScrip_0; "MIGRATION_SCRIPT_FILES"
0x180317e17  lea     rcx, [rsp+408h+var_3A0]
0x180317e1c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317e22  nop
0x180317e23  xor     edx, edx
0x180317e25  mov     rcx, rax
0x180317e28  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317e2e  nop
0x180317e2f  lea     rcx, [rsp+408h+var_3A0]
0x180317e34  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317e3a  lea     rdx, aMigUpgradeScri; "MIG_UPGRADE_SCRIPTS"
0x180317e41  lea     rcx, [rsp+408h+var_3A0]
0x180317e46  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317e4c  nop
0x180317e4d  xor     edx, edx
0x180317e4f  mov     rcx, rax
0x180317e52  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317e58  nop
0x180317e59  lea     rcx, [rsp+408h+var_3A0]
0x180317e5e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317e64  lea     rdx, aMigUpgradeConf; "MIG_UPGRADE_CONFIG_SCRIPT"
0x180317e6b  lea     rcx, [rsp+408h+var_3A0]
0x180317e70  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317e76  nop
0x180317e77  xor     edx, edx
0x180317e79  mov     rcx, rax
0x180317e7c  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317e82  nop
0x180317e83  lea     rcx, [rsp+408h+var_3A0]
0x180317e88  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317e8e  lea     rdx, aMigUpgradeAgen; "MIG_UPGRADE_AGENT_NO_DISCOVER"
0x180317e95  lea     rcx, [rsp+408h+var_3A0]
0x180317e9a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317ea0  nop
0x180317ea1  xor     edx, edx
0x180317ea3  mov     rcx, rax
0x180317ea6  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317eac  nop
0x180317ead  lea     rcx, [rsp+408h+var_3A0]
0x180317eb2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317eb8  lea     rdx, Value; "1"
0x180317ebf  lea     rcx, [rsp+408h+var_388]
0x180317ec7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317ecd  mov     rbx, rax
0x180317ed0  lea     rdx, aMigUpgrade; "MIG_UPGRADE"
0x180317ed7  lea     rcx, [rsp+408h+var_3A0]
0x180317edc  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317ee2  nop
0x180317ee3  mov     rdx, rbx
0x180317ee6  mov     rcx, rax
0x180317ee9  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317eef  nop
0x180317ef0  lea     rcx, [rsp+408h+var_3A0]
0x180317ef5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317efb  nop
0x180317efc  lea     rcx, [rsp+408h+var_388]
0x180317f04  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317f0a  lea     rdx, Value; "1"
0x180317f11  lea     rcx, [rsp+408h+var_388]
0x180317f19  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317f1f  mov     rbx, rax
0x180317f22  lea     rdx, aMigOsdbCheckWi; "MIG_OSDB_CHECK_WINSXS"
0x180317f29  lea     rcx, [rsp+408h+var_3A0]
0x180317f2e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317f34  nop
0x180317f35  mov     rdx, rbx
0x180317f38  mov     rcx, rax
0x180317f3b  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317f41  nop
0x180317f42  lea     rcx, [rsp+408h+var_3A0]
0x180317f47  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317f4d  nop
0x180317f4e  lea     rcx, [rsp+408h+var_388]
0x180317f56  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317f5c  lea     rdx, aMigUpgradeOpti; "MIG_UPGRADE_OPTIMIZE_GAC_MIGRATION"
0x180317f63  lea     rcx, [rsp+408h+var_3A0]
0x180317f68  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317f6e  nop
0x180317f6f  xor     edx, edx
0x180317f71  mov     rcx, rax
0x180317f74  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317f7a  nop
0x180317f7b  lea     rcx, [rsp+408h+var_3A0]
0x180317f80  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317f86  lea     rdx, aNo; "No"
0x180317f8d  lea     rcx, [rsp+408h+var_388]
0x180317f95  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317f9b  mov     rbx, rax
0x180317f9e  lea     rdx, aMigUseProcessE; "MIG_USE_PROCESS_ENV"
0x180317fa5  lea     rcx, [rsp+408h+var_3A0]
0x180317faa  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317fb0  nop
0x180317fb1  mov     rdx, rbx
0x180317fb4  mov     rcx, rax
0x180317fb7  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317fbd  nop
0x180317fbe  lea     rcx, [rsp+408h+var_3A0]
0x180317fc3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317fc9  nop
0x180317fca  lea     rcx, [rsp+408h+var_388]
0x180317fd2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180317fd8  lea     rdx, aMigDisableCont; "MIG_DISABLE_CONTENT_REMAP"
0x180317fdf  lea     rcx, [rsp+408h+var_3A0]
0x180317fe4  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180317fea  nop
0x180317feb  xor     edx, edx
0x180317fed  mov     rcx, rax
0x180317ff0  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180317ff6  nop
0x180317ff7  lea     rcx, [rsp+408h+var_3A0]
0x180317ffc  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180318002  lea     rdx, aMigManifests; "MIG_MANIFESTS"
0x180318009  lea     rcx, [rsp+408h+var_3A0]
0x18031800e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180318014  nop
0x180318015  xor     edx, edx
0x180318017  mov     rcx, rax
0x18031801a  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180318020  nop
0x180318021  lea     rcx, [rsp+408h+var_3A0]
0x180318026  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031802c  lea     rdx, aMigManifestsDi; "MIG_MANIFESTS_DIR"
0x180318033  lea     rcx, [rsp+408h+var_3A0]
0x180318038  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18031803e  nop
0x18031803f  xor     edx, edx
0x180318041  mov     rcx, rax
0x180318044  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031804a  nop
0x18031804b  lea     rcx, [rsp+408h+var_3A0]
0x180318050  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180318056  lea     rdx, aMigReplManifes; "MIG_REPL_MANIFESTS_DIR"
0x18031805d  lea     rcx, [rsp+408h+var_3A0]
0x180318062  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180318068  nop
0x180318069  mov     rdx, qword ptr [rsp+408h+arg_40]
0x180318071  mov     rcx, rax
0x180318074  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x18031807a  nop
0x18031807b  lea     rcx, [rsp+408h+var_3A0]
0x180318080  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180318086  lea     rdx, aMigrationScrip_0; "MIGRATION_SCRIPT_FILES"
0x18031808d  lea     rcx, [rsp+408h+var_3A0]
0x180318092  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180318098  nop
0x180318099  xor     edx, edx
0x18031809b  mov     rcx, rax
0x18031809e  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x1803180a4  nop
0x1803180a5  lea     rcx, [rsp+408h+var_3A0]
0x1803180aa  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1803180b0  lea     rdx, aMigrationScrip; "MIGRATION_SCRIPT_DIR"
0x1803180b7  lea     rcx, [rsp+408h+var_3A0]
0x1803180bc  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1803180c2  nop
0x1803180c3  xor     edx, edx
0x1803180c5  mov     rcx, rax
0x1803180c8  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x1803180ce  nop
0x1803180cf  lea     rcx, [rsp+408h+var_3A0]
0x1803180d4  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1803180da  lea     rdx, a0; "0"
0x1803180e1  lea     rcx, [rsp+408h+var_388]
0x1803180e9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1803180ef  mov     rbx, rax
0x1803180f2  lea     rdx, aMigContentComp; "MIG_CONTENT_COMPARE_ACLS"
0x1803180f9  lea     rcx, [rsp+408h+var_3A0]
0x1803180fe  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180318104  nop
0x180318105  mov     rdx, rbx
0x180318108  mov     rcx, rax
0x18031810b  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180318111  nop
0x180318112  lea     rcx, [rsp+408h+var_3A0]
0x180318117  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031811d  nop
0x18031811e  lea     rcx, [rsp+408h+var_388]
0x180318126  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18031812c  lea     rdx, aNo; "No"
0x180318133  lea     rcx, [rsp+408h+var_388]
0x18031813b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180318141  mov     rbx, rax
0x180318144  lea     rdx, aMigCompareLogi; "MIG_COMPARE_LOGICAL_CONTENT"
0x18031814b  lea     rcx, [rsp+408h+var_3A0]
0x180318150  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180318156  nop
0x180318157  mov     rdx, rbx
0x18031815a  mov     rcx, rax
0x18031815d  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180318163  nop
0x180318164  lea     rcx, [rsp+408h+var_3A0]
  ... truncated ...
```
