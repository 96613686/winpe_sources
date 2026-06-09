# CUnmountWIM::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x1801dab80`
- end: `0x1801dd11c`
- name: `?DoExecute@CUnmountWIM@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `9628`
- prototype: `void __fastcall __noreturn(CUnmountWIM *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180029c98`
- `0x1800447ec`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ae6b4`
- `0x1800b42d0`
- `0x180156370`
- `0x180157594`
- `0x1801dab80`
- `0x1802cd8b0`
- `0x1802cd980`
- `0x1802cff64`
- `0x1802d68d4`
- `0x1802fb834`
- `0x18035734c`
- `0x180404554`
- `0x18040498c`
- `0x180404b5c`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1801db1fe`
- `ADVAPI32!RegCloseKey` at `0x1801dc01e`
- `ADVAPI32!RegCloseKey` at `0x1801db1fe`
- `ADVAPI32!RegCloseKey` at `0x1801dc01e`
- `ADVAPI32!RegCreateKeyExW` at `0x1801db15b`
- `ADVAPI32!RegCreateKeyExW` at `0x1801db15b`
- `ADVAPI32!RegRestoreKeyW` at `0x1801db1e6`
- `ADVAPI32!RegRestoreKeyW` at `0x1801db1e6`
- `KERNEL32!GetLastError` at `0x1801dac7d`
- `KERNEL32!GetLastError` at `0x1801daea8`
- `KERNEL32!GetLastError` at `0x1801db270`
- `KERNEL32!GetLastError` at `0x1801db42c`
- `KERNEL32!GetLastError` at `0x1801db66b`
- `KERNEL32!GetLastError` at `0x1801db72f`
- `KERNEL32!GetLastError` at `0x1801db89d`
- `KERNEL32!GetLastError` at `0x1801dba5e`
- `KERNEL32!GetLastError` at `0x1801dbafe`
- `KERNEL32!GetLastError` at `0x1801dbb9e`
- `KERNEL32!GetLastError` at `0x1801dbc35`
- `KERNEL32!GetLastError` at `0x1801dbd0f`
- `KERNEL32!GetLastError` at `0x1801dbd25`
- `KERNEL32!GetLastError` at `0x1801dbd51`
- `KERNEL32!GetLastError` at `0x1801dbe0c`
- `KERNEL32!GetLastError` at `0x1801dbebb`
- `KERNEL32!GetLastError` at `0x1801dbf85`
- `KERNEL32!GetLastError` at `0x1801dc04d`
- `KERNEL32!GetLastError` at `0x1801dc063`
- `KERNEL32!GetLastError` at `0x1801dc095`
- `KERNEL32!GetLastError` at `0x1801dc13d`
- `KERNEL32!GetLastError` at `0x1801dc153`
- `KERNEL32!GetLastError` at `0x1801dc185`
- `KERNEL32!GetLastError` at `0x1801dc22e`
- `KERNEL32!GetLastError` at `0x1801dc244`
- `KERNEL32!GetLastError` at `0x1801dc276`
- `KERNEL32!GetLastError` at `0x1801dc31c`
- `KERNEL32!GetLastError` at `0x1801dc3d0`
- `KERNEL32!GetLastError` at `0x1801dc3e6`
- `KERNEL32!GetLastError` at `0x1801dc418`
- `KERNEL32!GetLastError` at `0x1801dc4bd`
- `KERNEL32!GetLastError` at `0x1801dc4d3`
- `KERNEL32!GetLastError` at `0x1801dc505`
- `KERNEL32!GetLastError` at `0x1801dc5ab`
- `KERNEL32!GetLastError` at `0x1801dc662`
- `KERNEL32!GetLastError` at `0x1801dc678`
- `KERNEL32!GetLastError` at `0x1801dc6aa`
- `KERNEL32!GetLastError` at `0x1801dc74e`
- `KERNEL32!GetLastError` at `0x1801dc764`
- `KERNEL32!GetLastError` at `0x1801dc796`
- `KERNEL32!GetLastError` at `0x1801dc83b`
- `KERNEL32!GetLastError` at `0x1801dc851`
- `KERNEL32!GetLastError` at `0x1801dc883`
- `KERNEL32!GetLastError` at `0x1801dc91e`
- `KERNEL32!GetLastError` at `0x1801dc934`
- `KERNEL32!GetLastError` at `0x1801dc966`
- `KERNEL32!GetLastError` at `0x1801dcba1`
- `KERNEL32!GetLastError` at `0x1801dcbb7`
- `KERNEL32!GetLastError` at `0x1801dcbdc`
- `KERNEL32!GetLastError` at `0x1801dcc8a`
- `KERNEL32!GetLastError` at `0x1801dcca0`
- `KERNEL32!GetLastError` at `0x1801dccc5`
- `KERNEL32!GetLastError` at `0x1801dcd6f`
- `KERNEL32!GetLastError` at `0x1801dcdf0`
- `KERNEL32!GetLastError` at `0x1801dce06`
- `KERNEL32!GetLastError` at `0x1801dce34`
- `KERNEL32!GetLastError` at `0x1801dceab`
- `KERNEL32!GetLastError` at `0x1801dcf2e`
- `KERNEL32!GetLastError` at `0x1801dcfb2`
- `KERNEL32!GetLastError` at `0x1801dcfc3`
- `KERNEL32!GetLastError` at `0x1801dcfd9`
- `KERNEL32!GetLastError` at `0x1801dd058`
- `KERNEL32!GetLastError` at `0x1801dd069`
- `KERNEL32!GetLastError` at `0x1801dac7d`
- `KERNEL32!GetLastError` at `0x1801daea8`
- `KERNEL32!GetLastError` at `0x1801db270`
- `KERNEL32!GetLastError` at `0x1801db42c`
- `KERNEL32!GetLastError` at `0x1801db66b`
- `KERNEL32!GetLastError` at `0x1801db72f`
- `KERNEL32!GetLastError` at `0x1801db89d`
- `KERNEL32!GetLastError` at `0x1801dba5e`
- `KERNEL32!GetLastError` at `0x1801dbafe`
- `KERNEL32!GetLastError` at `0x1801dbb9e`
- `KERNEL32!GetLastError` at `0x1801dbc35`
- `KERNEL32!GetLastError` at `0x1801dbd0f`
- `KERNEL32!GetLastError` at `0x1801dbd25`
- `KERNEL32!GetLastError` at `0x1801dbd51`
- `KERNEL32!GetLastError` at `0x1801dbe0c`
- `KERNEL32!GetLastError` at `0x1801dbebb`
- `KERNEL32!GetLastError` at `0x1801dbf85`
- `KERNEL32!GetLastError` at `0x1801dc04d`
- `KERNEL32!GetLastError` at `0x1801dc063`
- `KERNEL32!GetLastError` at `0x1801dc095`
- `KERNEL32!GetLastError` at `0x1801dc13d`
- `KERNEL32!GetLastError` at `0x1801dc153`
- `KERNEL32!GetLastError` at `0x1801dc185`
- `KERNEL32!GetLastError` at `0x1801dc22e`
- `KERNEL32!GetLastError` at `0x1801dc244`
- `KERNEL32!GetLastError` at `0x1801dc276`
- `KERNEL32!GetLastError` at `0x1801dc31c`
- `KERNEL32!GetLastError` at `0x1801dc3d0`
- `KERNEL32!GetLastError` at `0x1801dc3e6`
- `KERNEL32!GetLastError` at `0x1801dc418`
- `KERNEL32!GetLastError` at `0x1801dc4bd`
- `KERNEL32!GetLastError` at `0x1801dc4d3`
- `KERNEL32!GetLastError` at `0x1801dc505`
- `KERNEL32!GetLastError` at `0x1801dc5ab`
- `KERNEL32!GetLastError` at `0x1801dc662`
- `KERNEL32!GetLastError` at `0x1801dc678`
- `KERNEL32!GetLastError` at `0x1801dc6aa`
- `KERNEL32!GetLastError` at `0x1801dc74e`
- `KERNEL32!GetLastError` at `0x1801dc764`
- `KERNEL32!GetLastError` at `0x1801dc796`
- `KERNEL32!GetLastError` at `0x1801dc83b`
- `KERNEL32!GetLastError` at `0x1801dc851`
- `KERNEL32!GetLastError` at `0x1801dc883`
- `KERNEL32!GetLastError` at `0x1801dc91e`
- `KERNEL32!GetLastError` at `0x1801dc934`
- `KERNEL32!GetLastError` at `0x1801dc966`
- `KERNEL32!GetLastError` at `0x1801dcba1`
- `KERNEL32!GetLastError` at `0x1801dcbb7`
- `KERNEL32!GetLastError` at `0x1801dcbdc`
- `KERNEL32!GetLastError` at `0x1801dcc8a`
- `KERNEL32!GetLastError` at `0x1801dcca0`
- `KERNEL32!GetLastError` at `0x1801dccc5`
- `KERNEL32!GetLastError` at `0x1801dcd6f`
- `KERNEL32!GetLastError` at `0x1801dcdf0`
- `KERNEL32!GetLastError` at `0x1801dce06`
- `KERNEL32!GetLastError` at `0x1801dce34`
- `KERNEL32!GetLastError` at `0x1801dceab`
- `KERNEL32!GetLastError` at `0x1801dcf2e`
- `KERNEL32!GetLastError` at `0x1801dcfb2`
- `KERNEL32!GetLastError` at `0x1801dcfc3`
- `KERNEL32!GetLastError` at `0x1801dcfd9`
- `KERNEL32!GetLastError` at `0x1801dd058`
- `KERNEL32!GetLastError` at `0x1801dd069`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1801db0f1`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1801db7c9`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1801db0f1`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1801db7c9`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db358`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db41e`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db556`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db625`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db358`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db41e`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db556`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801db625`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801dabf1`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801dae7a`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801db0ae`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801dabf1`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801dae7a`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801db0ae`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1801db258`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1801db258`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801dac57`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801daf45`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801daf98`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801dafea`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801db198`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801dac57`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801daf45`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801daf98`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801dafea`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801db198`
- `unbcl!??2Object@UnBCL@@SAPEAX_KI@Z` at `0x1801dcac5`
- `unbcl!??2Object@UnBCL@@SAPEAX_KI@Z` at `0x1801dcac5`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801db884`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801dba39`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801db884`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801dba39`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dac1d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dac4b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801daf39`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dafde`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db018`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db029`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db305`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db331`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db4fa`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db52c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db6ff`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db74b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dcaf6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dd03f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dac1d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dac4b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801daf39`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dafde`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db018`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db029`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db305`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db331`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db4fa`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db52c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db6ff`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801db74b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dcaf6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801dd03f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801dac77`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801daf65`

## string_xrefs

- `0x1801dc291`: `%hs: Cannot get volume path for OS partition. Error: 0x%08X`
- `0x1801db4c0`: `UPGOsPath`
- `0x1801dc42e`: `UPGOsPath`
- `0x1801db64d`: `UPGBootVhdVolumePath`
- `0x1801dc6c0`: `UPGBootVhdVolumePath`
- `0x1801db764`: `%hs: VHD path: %s`
- `0x1801db711`: `UPGVhdPath`
- `0x1801dc7ac`: `UPGVhdPath`
- `0x1801dbc8b`: `%hs: Cannot copy filter from %s to %s. Error: 0x%08X`
- `0x1801dafbe`: `System32\Drivers\WinSetupBoot.sys`
- `0x1801db0ea`: `ControlSet%03u\Services\WinSetupBoot`
- `0x1801dbef1`: `%hs: Cannot create filter key %s. Error: 0x%08X`
- `0x1801db696`: `CUnmountWIM::DoExecute`
- `0x1801db75d`: `CUnmountWIM::DoExecute`
- `0x1801dba6f`: `CUnmountWIM::DoExecute`
- `0x1801dbb12`: `CUnmountWIM::DoExecute`
- `0x1801dbc84`: `CUnmountWIM::DoExecute`
- `0x1801dbd80`: `CUnmountWIM::DoExecute`
- `0x1801dbe20`: `CUnmountWIM::DoExecute`
- `0x1801dbeea`: `CUnmountWIM::DoExecute`
- `0x1801dbfb4`: `CUnmountWIM::DoExecute`
- `0x1801dc0b2`: `CUnmountWIM::DoExecute`
- `0x1801dc1a2`: `CUnmountWIM::DoExecute`
- `0x1801dc28a`: `CUnmountWIM::DoExecute`
- `0x1801dc349`: `CUnmountWIM::DoExecute`
- `0x1801dc435`: `CUnmountWIM::DoExecute`
- `0x1801dc519`: `CUnmountWIM::DoExecute`
- `0x1801dc5db`: `CUnmountWIM::DoExecute`
- `0x1801dc6c7`: `CUnmountWIM::DoExecute`
- `0x1801dc7b3`: `CUnmountWIM::DoExecute`
- `0x1801dc897`: `CUnmountWIM::DoExecute`
- `0x1801dc97a`: `CUnmountWIM::DoExecute`
- `0x1801dcc07`: `CUnmountWIM::DoExecute`
- `0x1801dccd9`: `CUnmountWIM::DoExecute`
- `0x1801dace5`: `CUnmountWIM::DoExecute`
- `0x1801dae67`: `CUnmountWIM::DoExecute`
- `0x1801db2be`: `CUnmountWIM::DoExecute`
- `0x1801db477`: `CUnmountWIM::DoExecute`
- `0x1801db6c0`: `CUnmountWIM::DoExecute`
- `0x1801db787`: `CUnmountWIM::DoExecute`
- `0x1801db913`: `CUnmountWIM::DoExecute`
- `0x1801dba99`: `CUnmountWIM::DoExecute`
- `0x1801dbb3c`: `CUnmountWIM::DoExecute`
- `0x1801dbcae`: `CUnmountWIM::DoExecute`
- `0x1801dbdaa`: `CUnmountWIM::DoExecute`
- `0x1801dbe4a`: `CUnmountWIM::DoExecute`
- `0x1801dbf14`: `CUnmountWIM::DoExecute`
- `0x1801dbfde`: `CUnmountWIM::DoExecute`
- `0x1801dc0dc`: `CUnmountWIM::DoExecute`
- `0x1801dc1cc`: `CUnmountWIM::DoExecute`
- `0x1801dc2b4`: `CUnmountWIM::DoExecute`
- `0x1801dc373`: `CUnmountWIM::DoExecute`
- `0x1801dc45f`: `CUnmountWIM::DoExecute`
- `0x1801dc543`: `CUnmountWIM::DoExecute`
- `0x1801dc605`: `CUnmountWIM::DoExecute`
- `0x1801dc6f1`: `CUnmountWIM::DoExecute`
- `0x1801dc7dd`: `CUnmountWIM::DoExecute`
- `0x1801dc8c1`: `CUnmountWIM::DoExecute`
- `0x1801dc9a4`: `CUnmountWIM::DoExecute`
- `0x1801dcda3`: `CUnmountWIM::DoExecute`
- `0x1801dce6b`: `CUnmountWIM::DoExecute`
- `0x1801dcefc`: `CUnmountWIM::DoExecute`
- `0x1801dcf62`: `CUnmountWIM::DoExecute`
- `0x1801dd017`: `CUnmountWIM::DoExecute`
- `0x1801dd0ad`: `CUnmountWIM::DoExecute`
- `0x1801dbbaf`: `Bad request. Asked to inject the driver but not commit the image`
- `0x1801dacc1`: `Extracting BOOT directory from %s to %s`
- `0x1801dc520`: `%hs: Cannot get volume path for VHD partition on known VHD boot. Error: 0x%08X`
- `0x1801db228`: `UPGFilterRollbackActive`
- `0x1801dc19b`: `UPGFilterRollbackActive`
- `0x1801dc981`: `%hs: Failed to enable CM_SERVICE_VIRTUAL_DISK_BOOT_LOAD on BootDriverFlags. Error: 0x%08X`
- `0x1801dc89e`: `%hs: Failed to create backup of BootDriverFlags. Error: 0x%08X`
- `0x1801dcc0e`: `%hs: Cannot get mounted image handle for %s. Error 0x%08X`
- `0x1801db8ef`: `Unmounting WIM file %s from %s`
- `0x1801dcff4`: `Failed to unmount WIM image. Error: 0x%08X`
- `0x1801dcf3f`: `WIM changes committed, proceeding to unmount.`
- `0x1801dce48`: `Failed to commit WIM changes. Error: 0x%08X`
- `0x1801dcd80`: `Committing WIM changes`
- `0x1801dd08a`: `Error removing directory %s. Error: 0x%08X`

## pseudocode

```c

```

## disassembly

```asm
0x1801dab80  mov     rax, rsp
0x1801dab83  mov     [rax+20h], r9
0x1801dab87  mov     [rax+18h], r8
0x1801dab8b  mov     [rax+10h], rdx
0x1801dab8f  mov     [rax+8], rcx
0x1801dab93  push    rbx
0x1801dab94  push    rsi
0x1801dab95  push    rdi
0x1801dab96  push    r12
0x1801dab98  push    r13
0x1801dab9a  push    r14
0x1801dab9c  push    r15
0x1801dab9e  sub     rsp, 360h
0x1801daba5  mov     qword ptr [rax-90h], 0FFFFFFFFFFFFFFFEh
0x1801dabb0  mov     r12, rdx
0x1801dabb3  mov     r14, rcx
0x1801dabb6  xor     esi, esi
0x1801dabb8  mov     [rsp+398h+var_338], esi
0x1801dabbc  mov     [rsp+398h+var_300], rsi
0x1801dabc4  mov     [rax-2D8h], rsi
0x1801dabcb  mov     [rax-2F8h], rsi
0x1801dabd2  mov     [rax-310h], esi
0x1801dabd8  mov     [rsp+398h+var_308], esi
0x1801dabdf  mov     [rsp+398h+var_30C], esi
0x1801dabe6  mov     [rsp+398h+var_330], esi
0x1801dabea  lea     rcx, [rax-100h]
0x1801dabf1  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1801dabf7  lea     rax, ??_7CXXXXXHandledException@?2??DoExecute@CUnmountWIM@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CUnmountWIM::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException::`vftable'
0x1801dabfe  mov     [rsp+398h+var_100], rax
0x1801dac06  cmp     [r14+0FCh], esi
0x1801dac0d  jz      loc_1801DAE61
0x1801dac13  lea     rbx, [r14+100h]
0x1801dac1a  mov     rcx, rbx
0x1801dac1d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801dac23  test    rax, rax
0x1801dac26  jz      loc_1801DBA56
0x1801dac2c  lea     rdx, aWindowsBoot; "WINDOWS\\Boot"
0x1801dac33  lea     rcx, [rsp+398h+var_2A8]
0x1801dac3b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801dac41  mov     rdi, rax
0x1801dac44  lea     rcx, [r14+0E8h]
0x1801dac4b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801dac51  mov     rdx, rdi
0x1801dac54  mov     rcx, rax
0x1801dac57  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1801dac5d  mov     rdx, rax
0x1801dac60  lea     rcx, [rsp+398h+var_2F0]
0x1801dac68  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801dac6e  nop
0x1801dac6f  lea     rcx, [rsp+398h+var_2A8]
0x1801dac77  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801dac7d  call    cs:__imp_GetLastError
0x1801dac83  mov     r14d, eax
0x1801dac86  call    cs:__imp_CurrentIP
0x1801dac8c  mov     r15, rax
0x1801dac8f  mov     rcx, rbx
0x1801dac92  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801dac98  mov     rcx, rax
0x1801dac9b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801daca1  mov     rdi, rax
0x1801daca4  lea     rcx, [rsp+398h+var_2F0]
0x1801dacac  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801dacb2  mov     rcx, rax
0x1801dacb5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801dacbb  mov     r9, rdi
0x1801dacbe  mov     r8, rax
0x1801dacc1  lea     rdx, aExtractingBoot; "Extracting BOOT directory from %s to %s"
0x1801dacc8  mov     ecx, 4000000h; unsigned int
0x1801daccd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801dacd2  mov     [rsp+398h+var_348], esi
0x1801dacd6  mov     qword ptr [rsp+398h+var_350], rsi
0x1801dacdb  mov     dword ptr [rsp+398h+var_358], r14d
0x1801dace0  mov     [rsp+398h+var_360], r15
0x1801dace5  lea     rcx, aCunmountwimDoe; "CUnmountWIM::DoExecute"
0x1801dacec  mov     [rsp+398h+var_368], rcx
0x1801dacf1  lea     rcx, aBaseNtsetupSet_9; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801dacf8  mov     qword ptr [rsp+398h+var_370], rcx
0x1801dacfd  mov     [rsp+398h+var_378], 0B30h
0x1801dad05  xor     r9d, r9d
0x1801dad08  lea     r8, aD_0; "D"
0x1801dad0f  mov     edx, 0C8000h
0x1801dad14  mov     rcx, rax
0x1801dad17  call    cs:__imp_WdsSetupLogMessageW
0x1801dad1d  mov     ecx, 0B0h
0x1801dad22  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1801dad28  mov     [rsp+398h+var_318], rax
0x1801dad30  test    rax, rax
0x1801dad33  jz      short loc_1801DAD3F
0x1801dad35  mov     rcx, rax
0x1801dad38  call    ??0?$ArrayList@PEAVCCopyInfo@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<CCopyInfo *>::ArrayList<CCopyInfo *>(void)
0x1801dad3d  jmp     short loc_1801DAD42
0x1801dad3f  mov     rax, rsi
0x1801dad42  mov     rdx, rax
0x1801dad45  lea     rcx, [rsp+398h+var_328]
0x1801dad4a  call    ??0?$SmartPtr@V?$ArrayList@PEAVCCopyInfo@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVCCopyInfo@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CCopyInfo *>>::SmartPtr<UnBCL::ArrayList<CCopyInfo *>>(UnBCL::ArrayList<CCopyInfo *> *)
0x1801dad4f  nop
0x1801dad50  mov     rcx, [rsp+398h+var_320]
0x1801dad55  mov     rax, [rcx]
0x1801dad58  mov     r13d, 1
0x1801dad5e  mov     edx, r13d
0x1801dad61  mov     rax, [rax+28h]
0x1801dad65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dad6a  mov     rdx, [rsp+398h+var_320]
0x1801dad6f  mov     rax, [rdx+8]
0x1801dad73  movsxd  r14, dword ptr [rax+10h]
0x1801dad77  add     r14, rdx
0x1801dad7a  mov     r15, [r14+8]
0x1801dad7e  mov     ecx, 90h
0x1801dad83  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1801dad89  mov     rdi, rax
0x1801dad8c  mov     [rsp+398h+var_318], rax
0x1801dad94  test    rax, rax
0x1801dad97  jz      short loc_1801DADF1
0x1801dad99  mov     rcx, rbx
0x1801dad9c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801dada2  mov     rcx, rax
0x1801dada5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801dadab  mov     rbx, rax
0x1801dadae  lea     rcx, [rsp+398h+var_2F0]
0x1801dadb6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801dadbc  mov     rcx, rax
0x1801dadbf  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801dadc5  mov     [rsp+398h+var_350], esi; unsigned int
0x1801dadc9  mov     dword ptr [rsp+398h+var_358], esi; int
0x1801dadcd  mov     dword ptr [rsp+398h+var_360], esi; int
0x1801dadd1  mov     dword ptr [rsp+398h+var_368], r13d; int
0x1801dadd6  mov     [rsp+398h+var_370], esi; int
0x1801dadda  mov     [rsp+398h+var_378], esi; int
0x1801dadde  mov     r9, rbx; unsigned __int16 *
0x1801dade1  mov     r8, rax; unsigned __int16 *
0x1801dade4  mov     edx, r13d; int
0x1801dade7  mov     rcx, rdi; this
0x1801dadea  call    ??0CCopyInfo@@QEAA@HPEBG0HHHHHI@Z; CCopyInfo::CCopyInfo(int,ushort const *,ushort const *,int,int,int,int,int,uint)
0x1801dadef  jmp     short loc_1801DADF4
0x1801dadf1  mov     rax, rsi
0x1801dadf4  mov     rdx, rax
0x1801dadf7  lea     rcx, [r14+8]
0x1801dadfb  mov     rax, [r15+28h]
0x1801dadff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dae04  mov     dword ptr [rsp+398h+var_368], esi
0x1801dae08  mov     [rsp+398h+var_370], r13d
0x1801dae0d  mov     [rsp+398h+var_378], esi
0x1801dae11  xor     r9d, r9d
0x1801dae14  xor     r8d, r8d
0x1801dae17  xor     edx, edx
0x1801dae19  mov     rcx, [rsp+398h+var_320]
0x1801dae1e  call    ?SPCopyFilesAndFolders@@YAJPEAV?$ArrayList@PEAVCCopyInfo@@@UnBCL@@PEAUICopyCallback@@PEAXPEAUIGenericProgress@SetupPlatform@@IHH@Z; SPCopyFilesAndFolders(UnBCL::ArrayList<CCopyInfo *> *,ICopyCallback *,void *,SetupPlatform::IGenericProgress *,uint,int,int)
0x1801dae23  mov     r14d, eax
0x1801dae26  mov     [rsp+398h+var_338], eax
0x1801dae2a  test    eax, eax
0x1801dae2c  js      loc_1801DBAFE
0x1801dae32  lea     rax, ??_7?$SmartPtr@V?$ArrayList@PEAVCCopyInfo@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CCopyInfo *>>::`vftable'
0x1801dae39  mov     [rsp+398h+var_328], rax
0x1801dae3e  lea     rcx, [rsp+398h+var_328]
0x1801dae43  call    ?DeAssign@?$SmartPtr@V?$Hashtable@KPEAUIVdsVDisk@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::Hashtable<ulong,IVdsVDisk *>>::DeAssign(void)
0x1801dae48  nop
0x1801dae49  lea     rcx, [rsp+398h+var_2F0]
0x1801dae51  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1801dae57  mov     r14, [rsp+398h+arg_0]
0x1801dae5f  jmp     short loc_1801DAE67
0x1801dae61  mov     r13d, 1
0x1801dae67  lea     r15, aCunmountwimDoe; "CUnmountWIM::DoExecute"
0x1801dae6e  mov     [rsp+398h+var_32C], esi
0x1801dae72  lea     rcx, [rsp+398h+var_C8]
0x1801dae7a  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1801dae80  lea     rax, ??_7CXXXXXHandledException@?BC@??DoExecute@CUnmountWIM@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CUnmountWIM::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`18'::CXXXXXHandledException::`vftable'
0x1801dae87  mov     [rsp+398h+var_C8], rax
0x1801dae8f  mov     rax, [r12]
0x1801dae93  mov     rcx, r12
0x1801dae96  mov     rax, [rax+28h]
0x1801dae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dae9f  cmp     eax, 4
0x1801daea2  jl      loc_1801DCB43
0x1801daea8  call    cs:__imp_GetLastError
0x1801daeae  mov     edi, eax
0x1801daeb0  call    cs:__imp_CurrentIP
0x1801daeb6  mov     rbx, rax
0x1801daeb9  lea     rdx, aInjectingSetup; "Injecting setup filter driver"
0x1801daec0  mov     ecx, 4000000h; unsigned int
0x1801daec5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801daeca  mov     [rsp+398h+var_348], esi
0x1801daece  mov     qword ptr [rsp+398h+var_350], rsi
0x1801daed3  mov     dword ptr [rsp+398h+var_358], edi
0x1801daed7  mov     [rsp+398h+var_360], rbx
0x1801daedc  mov     [rsp+398h+var_368], r15
0x1801daee1  lea     rcx, aBaseNtsetupSet_9; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801daee8  mov     qword ptr [rsp+398h+var_370], rcx
0x1801daeed  mov     [rsp+398h+var_378], 0B41h
0x1801daef5  xor     r9d, r9d
0x1801daef8  lea     r8, aD_0; "D"
0x1801daeff  mov     edx, 0C8000h
0x1801daf04  mov     rcx, rax
0x1801daf07  call    cs:__imp_WdsSetupLogMessageW
0x1801daf0d  cmp     [r14+0F8h], esi
0x1801daf14  jz      loc_1801DBB9E
0x1801daf1a  lea     rdx, aWindows_4; "WINDOWS"
0x1801daf21  lea     rcx, [rsp+398h+var_2A8]
0x1801daf29  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801daf2f  mov     rbx, rax
0x1801daf32  lea     rcx, [r14+0E8h]
0x1801daf39  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801daf3f  mov     rdx, rbx
0x1801daf42  mov     rcx, rax
0x1801daf45  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1801daf4b  mov     rdx, rax
0x1801daf4e  lea     rcx, [rsp+398h+var_2F0]
0x1801daf56  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801daf5c  nop
0x1801daf5d  lea     rcx, [rsp+398h+var_2A8]
0x1801daf65  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801daf6b  lea     rdx, aWinsetupbootSy; "WinSetupBoot.sys"
0x1801daf72  lea     rcx, [rsp+398h+var_180]
0x1801daf7a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801daf80  mov     rbx, rax
0x1801daf83  mov     rcx, [r12]
0x1801daf87  mov     rax, [rcx]
0x1801daf8a  mov     rcx, r12
0x1801daf8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801daf92  mov     rdx, rbx
0x1801daf95  mov     rcx, rax
0x1801daf98  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1801daf9e  mov     rdx, rax
0x1801dafa1  lea     rcx, [rsp+398h+var_158]
0x1801dafa9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801dafaf  nop
0x1801dafb0  lea     rcx, [rsp+398h+var_180]
0x1801dafb8  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801dafbe  lea     rdx, aSystem32Driver_1; "System32\\Drivers\\WinSetupBoot.sys"
0x1801dafc5  lea     rcx, [rsp+398h+var_58]
0x1801dafcd  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801dafd3  mov     rbx, rax
0x1801dafd6  lea     rcx, [rsp+398h+var_2F0]
0x1801dafde  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801dafe4  mov     rdx, rbx
0x1801dafe7  mov     rcx, rax
0x1801dafea  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1801daff0  mov     rdx, rax
0x1801daff3  lea     rcx, [rsp+398h+var_168]
0x1801daffb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801db001  nop
0x1801db002  lea     rcx, [rsp+398h+var_58]
0x1801db00a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801db010  lea     rcx, [rsp+398h+var_168]
0x1801db018  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801db01e  mov     rbx, rax
0x1801db021  lea     rcx, [rsp+398h+var_158]
0x1801db029  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801db02f  mov     dword ptr [rsp+398h+var_360], esi; int
0x1801db033  mov     dword ptr [rsp+398h+var_368], esi; int
0x1801db037  mov     [rsp+398h+var_370], r13d; int
0x1801db03c  mov     qword ptr [rsp+398h+var_378], rsi; void *
0x1801db041  xor     r9d, r9d; void *
0x1801db044  xor     r8d, r8d; unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *)
0x1801db047  mov     rdx, rbx; struct UnBCL::String *
0x1801db04a  mov     rcx, rax; struct UnBCL::String *
0x1801db04d  call    ?SPCopyFile@@YAJPEAVString@UnBCL@@0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z22HHH@Z; SPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int,int)
0x1801db052  mov     r14d, eax
0x1801db055  mov     [rsp+398h+var_338], eax
0x1801db059  test    eax, eax
0x1801db05b  js      loc_1801DBC35
0x1801db061  lea     rcx, [rsp+398h+var_2F0]
0x1801db069  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801db06f  mov     rcx, rax
0x1801db072  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801db078  lea     r8, aOfflineRwSyste; "$OFFLINE_RW$SYSTEM"
0x1801db07f  lea     rdx, aSystem; "SYSTEM"
0x1801db086  mov     rcx, rax; unsigned __int16 *
0x1801db089  call    ?SPMountOfflineHive@@YAPEAUHKEY__@@PEBG00@Z; SPMountOfflineHive(ushort const *,ushort const *,ushort const *)
0x1801db08e  mov     r15, rax
0x1801db091  mov     [rsp+398h+var_300], rax
0x1801db099  test    rax, rax
0x1801db09c  jz      loc_1801DBD0F
0x1801db0a2  mov     [rsp+398h+var_334], esi
0x1801db0a6  lea     rcx, [rsp+398h+var_290]
0x1801db0ae  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1801db0b4  lea     rax, ??_7CXXXXXHandledException@?CI@??DoExecute@CUnmountWIM@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CUnmountWIM::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`40'::CXXXXXHandledException::`vftable'
0x1801db0bb  mov     [rsp+398h+var_290], rax
0x1801db0c3  lea     r8, aCurrent_0; "Current"
0x1801db0ca  lea     rdx, aSelect; "Select"
0x1801db0d1  mov     rcx, r15
0x1801db0d4  call    RegGetDword
0x1801db0d9  mov     [rsp+398h+var_2E0], eax
0x1801db0e0  test    eax, eax
0x1801db0e2  jz      loc_1801DBE0C
0x1801db0e8  mov     edx, eax
0x1801db0ea  lea     rcx, aControlset03uS_1; "ControlSet%03u\\Services\\WinSetupBoot"
0x1801db0f1  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1801db0f7  mov     rdx, rax
0x1801db0fa  lea     rcx, [rsp+398h+var_180]
0x1801db102  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801db108  nop
0x1801db109  mov     [rsp+398h+var_318], rsi
0x1801db111  lea     rcx, [rsp+398h+var_180]
0x1801db119  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801db11f  mov     rcx, rax
0x1801db122  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801db128  mov     [rsp+398h+var_358], rsi; lpdwDisposition
0x1801db12d  lea     rcx, [rsp+398h+var_318]
0x1801db135  mov     [rsp+398h+var_360], rcx; phkResult
0x1801db13a  mov     [rsp+398h+var_368], rsi; lpSecurityAttributes
  ... truncated ...
```
