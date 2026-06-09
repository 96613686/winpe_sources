# SPExecuteGather(int,int,int,UnBCL::String *,UnBCL::String *,SetupPlatform::SP_MIG_SCOPE,int,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,UnBCL::ArrayList<UnBCL::String *> *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,int,int,int,int,int,int,ISPTelemetryData * *,ISPMigProgress *)

- ea: `0x180325c4c`
- end: `0x18032759e`
- name: `?SPExecuteGather@@YA?AW4MIGSTATUS@@HHHPEAVString@UnBCL@@0W4SP_MIG_SCOPE@SetupPlatform@@H0PEAV?$ArrayList@PEAVString@UnBCL@@@3@2000000HHHHHHPEAPEAUISPTelemetryData@@PEAUISPMigProgress@@@Z`
- size: `6482`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801fb590`
- `0x18020f27c`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180035de8`
- `0x18003d0e8`
- `0x18004d4b4`
- `0x180057dec`
- `0x18005dd8c`
- `0x18010f64c`
- `0x1802cff64`
- `0x18030158c`
- `0x180302f18`
- `0x180325c4c`
- `0x1803330b0`
- `0x180333170`
- `0x18033e844`
- `0x18033fa34`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180325cb8`
- `KERNEL32!GetLastError` at `0x1803267f2`
- `KERNEL32!GetLastError` at `0x180326967`
- `KERNEL32!GetLastError` at `0x180326e6e`
- `KERNEL32!GetLastError` at `0x180326fed`
- `KERNEL32!GetLastError` at `0x18032725f`
- `KERNEL32!GetLastError` at `0x180327270`
- `KERNEL32!GetLastError` at `0x180327352`
- `KERNEL32!GetLastError` at `0x180325cb8`
- `KERNEL32!GetLastError` at `0x1803267f2`
- `KERNEL32!GetLastError` at `0x180326967`
- `KERNEL32!GetLastError` at `0x180326e6e`
- `KERNEL32!GetLastError` at `0x180326fed`
- `KERNEL32!GetLastError` at `0x18032725f`
- `KERNEL32!GetLastError` at `0x180327270`
- `KERNEL32!GetLastError` at `0x180327352`
- `KERNEL32!CopyFileW` at `0x1803268f7`
- `KERNEL32!CopyFileW` at `0x180326f73`
- `KERNEL32!CopyFileW` at `0x1803268f7`
- `KERNEL32!CopyFileW` at `0x180326f73`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180325eb1`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180325eb1`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1803267da`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180326e56`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1803267da`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180326e56`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180326728`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180326da4`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180326728`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180326da4`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180326a1d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18032709c`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x180326a1d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18032709c`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180325e74`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180326791`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180326e0d`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180325e74`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180326791`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180326e0d`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180327497`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1803274fb`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180327497`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1803274fb`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326043`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326141`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18032621c`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326341`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18032643f`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326512`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18032669e`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326d1a`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326043`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326141`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18032621c`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326341`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18032643f`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326512`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18032669e`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180326d1a`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180325ff4`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326028`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803260f2`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326126`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326201`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803262f2`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326326`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803263f0`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326424`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803264f7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326683`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326cff`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180325ff4`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326028`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803260f2`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326126`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326201`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803262f2`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326326`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803263f0`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326424`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1803264f7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326683`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180326cff`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180325d80`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180325f97`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326095`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1803261a4`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326295`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326393`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18032649a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18032664c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326a65`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326cc8`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1803270e4`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180325d80`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180325f97`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326095`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1803261a4`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326295`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326393`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18032649a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18032664c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326a65`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180326cc8`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1803270e4`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180326926`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180326fa2`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180326926`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180326fa2`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326613`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18032673e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326905`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326c8a`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326dba`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326f81`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326613`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18032673e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326905`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326c8a`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326dba`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180326f81`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1803265c3`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180326c41`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1803265c3`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180326c41`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1803265df`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180326c56`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1803265df`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180326c56`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1803265f6`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180326c6d`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1803265f6`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180326c6d`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180326605`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180326bbd`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180326c7c`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18032722d`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180326605`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180326bbd`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180326c7c`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18032722d`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180326588`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180326c06`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180326588`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180326c06`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x18032755e`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x18032755e`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180326adf`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180327154`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180326adf`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180327154`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180325dd0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180325feb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326006`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032601f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032603a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803260e9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326104`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032611d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326138`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803261f8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326213`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803262e9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326304`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032631d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326338`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803263e7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326402`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032641b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326436`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803264ee`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326509`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032667a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326695`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326a59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326aac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326abd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326ace`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326cf6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326d11`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803270d8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180327121`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180327132`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180327143`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180327324`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180327344`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180325dd0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180325feb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326006`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032601f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032603a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803260e9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326104`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18032611d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326138`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803261f8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326213`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1803262e9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180326304`

## string_xrefs

- `0x1803267d3`: `%s\%08d.xml`
- `0x180326e4f`: `%s\%08d.xml`
- `0x180326a28`: `MigJournal.xml`
- `0x1803270a7`: `MigJournal.xml`
- `0x180326ca7`: `MachineSpecific_XMLs`
- `0x180326630`: `MachineIndependent_XMLs`
- `0x18032684a`: `Copying extra migration XML: %s -> %s`
- `0x180326ec6`: `Copying extra migration XML: %s -> %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=64 #try_helpers=1
__int64 __fastcall SPExecuteGather(
        int a1,
        int a2,
        int a3,
        const struct UnBCL::String *a4,
        struct UnBCL::String *a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        struct UnBCL::String *a11,
        const struct UnBCL::String *a12,
        const struct UnBCL::String *a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        int a17,
        int a18,
        int a19,
        int a20,
        int a21,
        int a22,
        _QWORD *a23,
        struct ISPMigProgress *a24)
{
  int v25; // r12d
  DWORD LastError; // edi
  __int64 v27; // rbx
  const unsigned __int16 *v28; // r9
  struct tagLOG_PARTIAL_MSG *v29; // rax
  const struct UnBCL::String *v30; // rax
  struct UnBCL::String *v31; // rax
  UnBCL::String *v32; // rax
  const unsigned __int16 *CString; // rax
  const struct UnBCL::String *P; // rbx
  const struct UnBCL::String *v35; // rax
  unsigned int v36; // r13d
  CSPTelemetryData *v37; // rax
  UnBCL::String *v38; // rax
  struct UnBCL::String *v39; // rbx
  const struct UnBCL::String *v40; // rax
  int v41; // esi
  const struct UnBCL::String *v42; // rdx
  const struct UnBCL::String *v43; // rdi
  struct UnBCL::String *v44; // rax
  const struct UnBCL::String *v45; // rax
  struct UnBCL::String *v46; // rax
  int v47; // edx
  int v48; // r9d
  const struct UnBCL::String *v49; // rax
  const struct UnBCL::String *v50; // rax
  struct UnBCL::DirectoryInfo *Dir; // rax
  const struct UnBCL::String *v52; // rax
  struct UnBCL::String *v53; // rax
  const struct UnBCL::String *v54; // rax
  struct UnBCL::String *v55; // rax
  int v56; // edx
  int v57; // r9d
  const struct UnBCL::String *v58; // rax
  const struct UnBCL::String *v59; // rax
  struct UnBCL::DirectoryInfo *v60; // rax
  const struct UnBCL::String *v61; // rbx
  const struct UnBCL::String *v62; // rax
  struct UnBCL::String *v63; // rax
  const struct UnBCL::String *v64; // rax
  const struct UnBCL::String *v65; // rax
  struct UnBCL::DirectoryInfo *v66; // rax
  const struct UnBCL::String *v67; // rax
  struct UnBCL::String *v68; // rax
  const struct UnBCL::String *v69; // rax
  struct UnBCL::String *v70; // rax
  int v71; // edx
  int v72; // r9d
  const struct UnBCL::String *v73; // rax
  const struct UnBCL::String *v74; // rax
  struct UnBCL::DirectoryInfo *v75; // rax
  const struct UnBCL::String *v76; // rax
  struct UnBCL::String *v77; // rax
  const struct UnBCL::String *v78; // rax
  struct UnBCL::String *v79; // rax
  int v80; // edx
  int v81; // r9d
  const struct UnBCL::String *v82; // rax
  const struct UnBCL::String *v83; // rax
  struct UnBCL::DirectoryInfo *v84; // rax
  const struct UnBCL::String *v85; // rax
  struct UnBCL::String *v86; // rax
  const struct UnBCL::String *v87; // rax
  const struct UnBCL::String *v88; // rax
  struct UnBCL::DirectoryInfo *v89; // rax
  _QWORD *v90; // rax
  _QWORD *v91; // rbx
  __int64 v92; // rax
  const struct UnBCL::String *v93; // rax
  struct UnBCL::String *v94; // rax
  const struct UnBCL::String *v95; // rax
  const struct UnBCL::String *v96; // rax
  struct UnBCL::DirectoryInfo *v97; // rax
  unsigned int j; // edi
  int (__fastcall ***v99)(_QWORD); // rcx
  __int64 v100; // rcx
  UnBCL::String *v101; // rbx
  UnBCL::String *v102; // rax
  const unsigned __int16 *v103; // rax
  __int64 v104; // rax
  __int64 v105; // r15
  __int64 v106; // r13
  UnBCL::String *v107; // rbx
  __int64 v108; // rcx
  const struct UnBCL::String **v109; // rax
  UnBCL::String *v110; // rax
  const unsigned __int16 *v111; // rax
  struct UnBCL::String *v112; // rax
  DWORD v113; // r15d
  __int64 v114; // r12
  UnBCL::String *v115; // rax
  const char *v116; // rbx
  __int64 v117; // rcx
  UnBCL::String **v118; // rax
  const char *v119; // rax
  struct tagLOG_PARTIAL_MSG *v120; // rax
  UnBCL::String *v121; // rax
  const WCHAR *v122; // rbx
  __int64 v123; // rcx
  UnBCL::String **v124; // rax
  const WCHAR *v125; // rax
  __int64 v126; // rax
  __int64 v127; // rbx
  void (__fastcall *v128)(__int64, __int64); // r15
  __int64 v129; // rax
  DWORD v130; // edi
  __int64 v131; // rbx
  struct tagLOG_PARTIAL_MSG *v132; // rax
  BOOL v133; // r15d
  struct UnBCL::String *v134; // rax
  const struct UnBCL::String *v135; // rbx
  int v136; // edi
  const struct UnBCL::String *v137; // rax
  __int64 v138; // rsi
  __int64 v139; // rdi
  __int64 v140; // rbx
  __int64 v141; // rax
  _QWORD *v142; // rax
  _QWORD *v143; // rbx
  __int64 v144; // rax
  const struct UnBCL::String *v145; // rax
  struct UnBCL::String *v146; // rax
  const struct UnBCL::String *v147; // rax
  const struct UnBCL::String *v148; // rax
  struct UnBCL::DirectoryInfo *v149; // rax
  unsigned int i; // edi
  int (__fastcall ***v151)(_QWORD); // rcx
  __int64 v152; // rcx
  UnBCL::String *v153; // rbx
  UnBCL::String *v154; // rax
  const unsigned __int16 *v155; // rax
  __int64 v156; // rax
  __int64 v157; // r15
  __int64 v158; // r13
  UnBCL::String *v159; // rbx
  __int64 v160; // rcx
  const struct UnBCL::String **v161; // rax
  UnBCL::String *v162; // rax
  const unsigned __int16 *v163; // rax
  struct UnBCL::String *v164; // rax
  DWORD v165; // r15d
  __int64 v166; // r12
  UnBCL::String *v167; // rax
  const char *v168; // rbx
  __int64 v169; // rcx
  UnBCL::String **v170; // rax
  const char *v171; // rax
  struct tagLOG_PARTIAL_MSG *v172; // rax
  UnBCL::String *v173; // rax
  const WCHAR *v174; // rbx
  __int64 v175; // rcx
  UnBCL::String **v176; // rax
  const WCHAR *v177; // rax
  __int64 v178; // rax
  __int64 v179; // rbx
  void (__fastcall *v180)(__int64, __int64); // r15
  __int64 v181; // rax
  DWORD v182; // edi
  __int64 v183; // rbx
  struct tagLOG_PARTIAL_MSG *v184; // rax
  BOOL v185; // r15d
  struct UnBCL::String *v186; // rax
  const struct UnBCL::String *v187; // rbx
  char v188; // di
  const struct UnBCL::String *v189; // rax
  __int64 v190; // rsi
  __int64 v191; // rdi
  __int64 v192; // rbx
  __int64 v193; // rax
  DWORD v194; // edi
  __int64 v195; // rbx
  DWORD v196; // eax
  struct tagLOG_PARTIAL_MSG *v197; // rax
  struct UnBCL::String *v198; // rax
  struct UnBCL::String *v199; // rax
  DWORD v200; // edi
  __int64 v201; // rbx
  struct tagLOG_PARTIAL_MSG *v202; // rax
  __int64 result; // rax
  UnBCL::ArgumentNullException *v204; // rax
  UnBCL::ArgumentNullException *v205; // rbx
  UnBCL::ArgumentNullException *v206; // rax
  UnBCL::ArgumentNullException *v207; // rbx
  UnBCL::Win32Exception *v208; // rax
  UnBCL::Win32Exception *v209; // rbx
  struct UnBCL::Exception *v210; // rsi
  DWORD v211; // edi
  __int64 v212; // rbx
  UnBCL::String *v213; // rax
  const char *v214; // rax
  struct tagLOG_PARTIAL_MSG *v215; // rax
  DWORD v216; // edi
  __int64 v217; // rbx
  UnBCL::String *v218; // rax
  const char *v219; // rax
  struct tagLOG_PARTIAL_MSG *v220; // rax
  char v221[8]; // [rsp+A0h] [rbp-178h] BYREF
  __int64 v222; // [rsp+A8h] [rbp-170h]
  int v223; // [rsp+B8h] [rbp-160h]
  __int64 v224; // [rsp+C0h] [rbp-158h]
  __int64 v225; // [rsp+C8h] [rbp-150h] BYREF
  int v226[2]; // [rsp+D0h] [rbp-148h]
  _BYTE v227[24]; // [rsp+D8h] [rbp-140h] BYREF
  _BYTE v228[16]; // [rsp+F0h] [rbp-128h] BYREF
  _BYTE v229[16]; // [rsp+100h] [rbp-118h] BYREF
  _BYTE v230[16]; // [rsp+110h] [rbp-108h] BYREF
  unsigned int v231; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v232[16]; // [rsp+128h] [rbp-F0h] BYREF
  _BYTE v233[16]; // [rsp+138h] [rbp-E0h] BYREF
  UnBCL::Exception *v234; // [rsp+148h] [rbp-D0h]
  _BYTE v235[16]; // [rsp+150h] [rbp-C8h] BYREF
  _BYTE v236[16]; // [rsp+160h] [rbp-B8h] BYREF
  _BYTE v237[16]; // [rsp+170h] [rbp-A8h] BYREF
  _BYTE v238[16]; // [rsp+180h] [rbp-98h] BYREF
  void **v239; // [rsp+190h] [rbp-88h] BYREF
  __int64 v240; // [rsp+198h] [rbp-80h]
  __int64 pExceptionObject; // [rsp+1A8h] [rbp-70h] BYREF
  __int64 v242; // [rsp+1B0h] [rbp-68h] BYREF
  _QWORD v243[2]; // [rsp+1B8h] [rbp-60h] BYREF
  struct UnBCL::Exception *v244; // [rsp+1C8h] [rbp-50h] BYREF
  struct UnBCL::Exception *v245; // [rsp+1D8h] [rbp-40h] BYREF
  _BYTE v246[56]; // [rsp+1E0h] [rbp-38h] BYREF

  v243[1] = -2;
  v25 = 0;
  v223 = 0;
  if ( !a11 )
  {
    v204 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v205 = v204;
    if ( v204 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v204, L"StoreDir");
      *(_QWORD *)v205 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v205 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v205,
                         "enum MIGSTATUS __cdecl SPExecuteGather(int,int,int,class UnBCL::String *,class UnBCL::String *,"
                         "enum SetupPlatform::SP_MIG_SCOPE,int,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::"
                         "String *> *,class UnBCL::ArrayList<class UnBCL::String *> *,class UnBCL::String *,class UnBCL::"
                         "String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String "
                         "*,int,int,int,int,int,int,struct ISPTelemetryData **,struct ISPMigProgress *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !a12 )
  {
    v206 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v207 = v206;
    if ( v206 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v206, L"WorkDir");
      *(_QWORD *)v207 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v207 = 0;
    }
    v242 = AddStackTraceToException<UnBCL::InvalidOperationException>(
             v207,
             "enum MIGSTATUS __cdecl SPExecuteGather(int,int,int,class UnBCL::String *,class UnBCL::String *,enum SetupPl"
             "atform::SP_MIG_SCOPE,int,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,class UnBCL:"
             ":ArrayList<class UnBCL::String *> *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class"
             " UnBCL::String *,class UnBCL::String *,class UnBCL::String *,int,int,int,int,int,int,struct ISPTelemetryDat"
             "a **,struct ISPMigProgress *)");
    throw (UnBCL::ArgumentNullException **)&v242;
  }
  if ( a22 && !a21 )
  {
    v208 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v209 = v208;
    if ( v208 )
    {
      UnBCL::Win32Exception::Win32Exception(v208, 0x57u);
      *(_QWORD *)v209 = &UnBCL::Win32Exception::`local vftable';
    }
    else
    {
      v209 = 0;
    }
    v243[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v209,
                "enum MIGSTATUS __cdecl SPExecuteGather(int,int,int,class UnBCL::String *,class UnBCL::String *,enum Setu"
                "pPlatform::SP_MIG_SCOPE,int,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,class "
                "UnBCL::ArrayList<class UnBCL::String *> *,class UnBCL::String *,class UnBCL::String *,class UnBCL::Strin"
                "g *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,int,int,int,int,int,int,struct ISP"
                "TelemetryData **,struct ISPMigProgress *)");
    throw (UnBCL::Win32Exception **)v243;
  }
  LastError = GetLastError();
  v27 = CurrentIP();
  v28 = L"Offline";
  if ( !a5 )
    v28 = L"Online";
  v29 = ConstructPartialMsgW(0x4000000u, "%hs: Begin run (%s)", "SPExecuteGather", (const char *)v28);
  WdsSetupLogMessageW(
    v29,
    819200,
    L"D",
    0,
    7845,
    L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
    L"SPExecuteGather",
    v27,
    LastError,
    0,
    0);
  pSPRemoveUpgradeRegTree(a5);
  if ( a6 == 5 )
  {
    v30 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v239, L"drvfiles.dat");
    v31 = UnBCL::Path::Combine(a4, v30);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v31);
    UnBCL::String::~String((UnBCL::String *)&v239);
    v32 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v221);
    CString = UnBCL::String::get_CString(v32);
    BuildDriverFilesList(CString, 0);
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v221);
    v35 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MIG_OSDB_DRV_FILES");
    UnBCL::Environment::SetEnvironmentVar(v35, P);
    UnBCL::String::~String((UnBCL::String *)v227);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
  }
  v36 = 0;
  v37 = (CSPTelemetryData *)UnBCL::Object::operator new(0x80u);
  v224 = (__int64)v37;
  if ( v37 )
    v37 = CSPTelemetryData::CSPTelemetryData(v37);
  UnBCL::SmartPtr<CSPTelemetryData>::SmartPtr<CSPTelemetryData>(&v239, v37);
  if ( a5 )
  {
    v38 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v39 = v38;
    v224 = (__int64)v38;
    if ( v38 )
    {
      UnBCL::String::String(v38, a5);
      *(_QWORD *)v39 = &UnBCL::String::`local vftable';
    }
    else
    {
      v39 = 0;
    }
  }
  else
  {
    v40 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v221, L"%windir%");
    v25 = 1;
    v223 = 1;
    v39 = UnBCL::Environment::ExpandEnvironmentVariables(v40);
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v246, v39);
  if ( (v25 & 1) != 0 )
  {
    v223 = v25 & 0xFFFFFFFE;
    UnBCL::String::~String((UnBCL::String *)v221);
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v236);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v230);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v238);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v235);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v229);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v237);
  try
  {
    v225 = (__int64)UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
    *(_QWORD *)v226 = 0;
    v41 = a2;
    if ( a2 )
    {
      v42 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MachineIndependent");
      v43 = a11;
      v44 = UnBCL::Path::Combine(a11, v42);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v44);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v235, v221);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
      UnBCL::String::~String((UnBCL::String *)v227);
      v45 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v235);
      if ( UnBCL::Directory::Exists(v45) )
      {
        v46 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v235);
        SPDeleteFolder(v46, v47, 0, v48);
      }
      v49 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v235);
      if ( !UnBCL::Directory::Exists(v49) )
      {
        v50 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v235);
        Dir = UnBCL::Directory::CreateDir(v50);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, Dir);
        UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(&v225, v222);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
      }
      v52 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MachineIndependent");
      v53 = UnBCL::Path::Combine(a12, v52);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v53);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v229, v221);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
      UnBCL::String::~String((UnBCL::String *)v227);
      v54 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
      if ( UnBCL::Directory::Exists(v54) )
      {
        v55 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
        SPDeleteFolder(v55, v56, 0, v57);
      }
      v58 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
      if ( !UnBCL::Directory::Exists(v58) )
      {
        v59 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
        v60 = UnBCL::Directory::CreateDir(v59);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v60);
        UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(&v225, v222);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
      }
      v61 = a13;
      if ( a13 )
      {
        v62 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MachineIndependent");
        v63 = UnBCL::Path::Combine(a13, v62);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v63);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v237, v221);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
        UnBCL::String::~String((UnBCL::String *)v227);
        v64 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v237);
        if ( !UnBCL::Directory::Exists(v64) )
        {
          v65 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v237);
          v66 = UnBCL::Directory::CreateDir(v65);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v66);
          UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(&v225, v222);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
        }
      }
    }
    else
    {
      v61 = a13;
      v43 = a11;
    }
    if ( a1 )
    {
      v67 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MachineSpecific");
      v68 = UnBCL::Path::Combine(v43, v67);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v68);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v236, v221);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
      UnBCL::String::~String((UnBCL::String *)v227);
      v69 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
      if ( UnBCL::Directory::Exists(v69) )
      {
        v70 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
        SPDeleteFolder(v70, v71, 0, v72);
      }
      v73 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
      if ( !UnBCL::Directory::Exists(v73) )
      {
        v74 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
        v75 = UnBCL::Directory::CreateDir(v74);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v75);
        UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(&v225, v222);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
      }
      v76 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MachineSpecific");
      v77 = UnBCL::Path::Combine(a12, v76);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v77);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v230, v221);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
      UnBCL::String::~String((UnBCL::String *)v227);
      v78 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v230);
      if ( UnBCL::Directory::Exists(v78) )
      {
        v79 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v230);
        SPDeleteFolder(v79, v80, 0, v81);
      }
      v82 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v230);
      if ( !UnBCL::Directory::Exists(v82) )
      {
        v83 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v230);
        v84 = UnBCL::Directory::CreateDir(v83);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v84);
        UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(&v225, v222);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
      }
      if ( v61 )
      {
        v85 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v227, L"MachineSpecific");
        v86 = UnBCL::Path::Combine(v61, v85);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v86);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v238, v221);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
        UnBCL::String::~String((UnBCL::String *)v227);
        v87 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v238);
        if ( !UnBCL::Directory::Exists(v87) )
        {
          v88 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v238);
          v89 = UnBCL::Directory::CreateDir(v88);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v89);
          UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(&v225, v222);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(&v225);
  }
  catch ( UnBCL::Exception *v245 )
  {
    v210 = v245;
    pExceptionLogFormat::pExceptionLogFormat(
      (pExceptionLogFormat *)&v231,
      0x2000000u,
      v245,
      "%hs: Migration phase caught an exception creating work/store directories.",
      "SPExecuteGather");
    UnBCL::Exception::AddStackTrace(
      v234,
      "enum MIGSTATUS __cdecl SPExecuteGather(int,int,int,class UnBCL::String *,class UnBCL::String *,enum SetupPlatform:"
      ":SP_MIG_SCOPE,int,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,class UnBCL::ArrayList<cla"
      "ss UnBCL::String *> *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,clas"
      "s UnBCL::String *,class UnBCL::String *,int,int,int,int,int,int,struct ISPTelemetryData **,struct ISPMigProgress *)");
    v211 = GetLastError();
    v212 = CurrentIP();
    v213 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v232);
    v214 = (const char *)UnBCL::String::get_CString(v213);
    v215 = ConstructPartialMsgW(v231, "%s", v214);
    WdsSetupLogMessageW(
      v215,
      819200,
      L"D",
      0,
      7941,
      L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
      L"SPExecuteGather",
      v212,
      v211,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v233);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v232);
    if ( v210 )
      (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v210)(v210, 1);
    LODWORD(v224) = 4;
    v36 = 4;
    goto LABEL_105;
  }
  if ( !v41 || a6 - 3 > 2 && !a7 )
  {
    if ( a1 && a6 - 3 <= 2 )
    {
      LODWORD(v224) = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v228);
      if ( a9 )
      {
        v142 = UnBCL::Object::operator new(0xB0u);
        v143 = v142;
        v225 = (__int64)v142;
        if ( v142 )
        {
          UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v142, 1);
          v143[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
        }
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v221, v143);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v228, v221);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v221);
        v144 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v228);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v144 + 40LL))(v144, 1);
        v145 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v231, L"MachineSpecific_XMLs");
        v146 = UnBCL::Path::Combine(a11, v145);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v146);
        UnBCL::String::~String((UnBCL::String *)&v231);
        v147 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v227);
        if ( !UnBCL::Directory::Exists(v147) )
        {
          v148 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v227);
          v149 = UnBCL::Directory::CreateDir(v148);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v149);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
        }
        for ( i = 0; ; ++i )
        {
          v151 = (int (__fastcall ***)(_QWORD))(a9 + *(int *)(*(_QWORD *)(a9 + 8) + 12LL) + 8LL);
          if ( (int)i >= (**v151)(v151) )
            break;
          v152 = a9 + *(int *)(*(_QWORD *)(a9 + 8) + 16LL) + 8LL;
          v153 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v152 + 24LL))(v152, i);
          v154 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v227);
          v155 = UnBCL::String::get_CString(v154);
          if ( UnBCL::String::StartsWith(v153, v155, 1) )
          {
            v156 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v228);
            v157 = v156 + *(int *)(*(_QWORD *)(v156 + 8) + 16LL);
            v158 = *(_QWORD *)(v157 + 8);
            v159 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            v225 = (__int64)v159;
            if ( v159 )
            {
              v160 = a9 + *(int *)(*(_QWORD *)(a9 + 8) + 16LL) + 8LL;
              v161 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v160 + 24LL))(
                                                      v160,
                                                      i);
              UnBCL::String::String(v159, *v161);
              *(_QWORD *)v159 = &UnBCL::String::`local vftable';
            }
            (*(void (__fastcall **)(__int64, UnBCL::String *))(v158 + 40))(v157 + 8, v159);
          }
          else
          {
            v162 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v227);
            v163 = UnBCL::String::get_CString(v162);
            v164 = UnBCL::String::Format(L"%s\\%08d.xml", v163, i);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v164);
            v165 = GetLastError();
            v166 = CurrentIP();
            v167 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v221);
            v168 = (const char *)UnBCL::String::get_CString(v167);
            v169 = a9 + *(int *)(*(_QWORD *)(a9 + 8) + 16LL) + 8LL;
            v170 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v169 + 24LL))(v169, i);
            v171 = (const char *)UnBCL::String::get_CString(*v170);
            v172 = ConstructPartialMsgW(0x4000000u, "Copying extra migration XML: %s -> %s", v171, v168);
            WdsSetupLogMessageW(
              v172,
              819200,
              L"D",
              0,
              8051,
              L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
              L"SPExecuteGather",
              v166,
              v165,
              0,
              0);
            v173 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v221);
            v174 = UnBCL::String::get_CString(v173);
            v175 = a9 + *(int *)(*(_QWORD *)(a9 + 8) + 16LL) + 8LL;
            v176 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v175 + 24LL))(v175, i);
            v177 = UnBCL::String::get_CString(*v176);
            CopyFileW(v177, v174, 0);
            v178 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v228);
            v179 = v178 + *(int *)(*(_QWORD *)(v178 + 8) + 16LL);
            v180 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v179 + 8) + 40LL);
            v181 = UnBCL::SmartPtr<UnBCL::String>::Steal(v221);
            v180(v179 + 8, v181);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
        v36 = v224;
        if ( (_DWORD)v224 )
        {
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v228);
          goto LABEL_106;
        }
      }
      v182 = GetLastError();
      v183 = CurrentIP();
      v184 = ConstructPartialMsgW(0x4000000u, "%hs: Executing machine-specific gather", "SPExecuteGather");
      WdsSetupLogMessageW(
        v184,
        819200,
        L"D",
        0,
        8065,
        L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
        L"SPExecuteGather",
        v183,
        v182,
        0,
        0);
      v185 = !a21 && !a22;
      v186 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v238);
      if ( v186 )
      {
        v187 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v231, L"MigJournal.xml");
        v188 = v223 | 4;
        v223 |= 4u;
        v189 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v238);
        v186 = UnBCL::Path::Combine(v189, v187);
      }
      else
      {
        v188 = v223;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v186);
      if ( (v188 & 4) != 0 )
        UnBCL::String::~String((UnBCL::String *)&v231);
      v190 = UnBCL::SmartPtr<UnBCL::String>::get_P(v221);
      v191 = UnBCL::SmartPtr<UnBCL::String>::get_P(v230);
      v192 = UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
      v193 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v228);
      pSPDoMainGather(a5, a6, 0, a8, 1, v185, v193, v192, v191, v190, a14, a15, a16, a17, a18, a19, a20, v240, a24);
    }
    if ( a3 && !(unsigned int)pSPPersistEnvVars(a11) )
    {
      v194 = GetLastError();
      v195 = CurrentIP();
      v196 = GetLastError();
      v197 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Persisting control environment variables failed. Error: 0x%08X",
               "SPExecuteGather",
               v196);
      WdsSetupLogMessageW(
        v197,
        819200,
        L"D",
        0,
        8099,
        L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
        L"SPExecuteGather",
        v195,
        v194,
        0,
        0);
      v36 = 5;
      goto LABEL_105;
    }
    if ( !a23 )
      goto LABEL_105;
    *a23 = UnBCL::SmartPtr<CSPTelemetryData>::Steal(&v239);
    goto LABEL_105;
  }
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(&v225);
  try
  {
    if ( a10 )
    {
      v90 = UnBCL::Object::operator new(0xB0u);
      v91 = v90;
      v224 = (__int64)v90;
      if ( v90 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v90, 1);
        v91[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v221, v91);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(&v225, v221);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v221);
      v92 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(&v225);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 40LL))(v92, 1);
      v93 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v231, L"MachineIndependent_XMLs");
      v94 = UnBCL::Path::Combine(v43, v93);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v228, v94);
      UnBCL::String::~String((UnBCL::String *)&v231);
      v95 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v228);
      if ( !UnBCL::Directory::Exists(v95) )
      {
        v96 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v228);
        v97 = UnBCL::Directory::CreateDir(v96);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v221, v97);
        UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v221);
      }
      for ( j = 0; ; ++j )
      {
        v99 = (int (__fastcall ***)(_QWORD))(a10 + *(int *)(*(_QWORD *)(a10 + 8) + 12LL) + 8LL);
        if ( (int)j >= (**v99)(v99) )
          break;
        v100 = a10 + *(int *)(*(_QWORD *)(a10 + 8) + 16LL) + 8LL;
        v101 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v100 + 24LL))(v100, j);
        v102 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v228);
        v103 = UnBCL::String::get_CString(v102);
        if ( UnBCL::String::StartsWith(v101, v103, 1) )
        {
          v104 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(&v225);
          v105 = v104 + *(int *)(*(_QWORD *)(v104 + 8) + 16LL);
          v106 = *(_QWORD *)(v105 + 8);
          v107 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v224 = (__int64)v107;
          if ( v107 )
          {
            v108 = a10 + *(int *)(*(_QWORD *)(a10 + 8) + 16LL) + 8LL;
            v109 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v108 + 24LL))(
                                                    v108,
                                                    j);
            UnBCL::String::String(v107, *v109);
            *(_QWORD *)v107 = &UnBCL::String::`local vftable';
          }
          (*(void (__fastcall **)(__int64, UnBCL::String *))(v106 + 40))(v105 + 8, v107);
        }
        else
        {
          v110 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v228);
          v111 = UnBCL::String::get_CString(v110);
          v112 = UnBCL::String::Format(L"%s\\%08d.xml", v111, j);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v112);
          v113 = GetLastError();
          v114 = CurrentIP();
          v115 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v227);
          v116 = (const char *)UnBCL::String::get_CString(v115);
          v117 = a10 + *(int *)(*(_QWORD *)(a10 + 8) + 16LL) + 8LL;
          v118 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v117 + 24LL))(v117, j);
          v119 = (const char *)UnBCL::String::get_CString(*v118);
          v120 = ConstructPartialMsgW(0x4000000u, "Copying extra migration XML: %s -> %s", v119, v116);
          WdsSetupLogMessageW(
            v120,
            819200,
            L"D",
            0,
            7978,
            L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
            L"SPExecuteGather",
            v114,
            v113,
            0,
            0);
          v121 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v227);
          v122 = UnBCL::String::get_CString(v121);
          v123 = a10 + *(int *)(*(_QWORD *)(a10 + 8) + 16LL) + 8LL;
          v124 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v123 + 24LL))(v123, j);
          v125 = UnBCL::String::get_CString(*v124);
          CopyFileW(v125, v122, 0);
          v126 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(&v225);
          v127 = v126 + *(int *)(*(_QWORD *)(v126 + 8) + 16LL);
          v128 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v127 + 8) + 40LL);
          v129 = UnBCL::SmartPtr<UnBCL::String>::Steal(v227);
          v128(v127 + 8, v129);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
        }
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v228);
    }
    v130 = GetLastError();
    v131 = CurrentIP();
    v132 = ConstructPartialMsgW(0x4000000u, "%hs: Executing machine-independent gather", "SPExecuteGather");
    WdsSetupLogMessageW(
      v132,
      819200,
      L"D",
      0,
      7992,
      L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
      L"SPExecuteGather",
      v131,
      v130,
      0,
      0);
    v133 = a21 && !a22;
  }
  catch ( UnBCL::Exception *v244 )
  {
    pExceptionLogFormat::pExceptionLogFormat(
      (pExceptionLogFormat *)&v231,
      0x2000000u,
      v244,
      "Error while copying additional migration XMLs.");
    UnBCL::Exception::AddStackTrace(
      v234,
      "enum MIGSTATUS __cdecl SPExecuteGather(int,int,int,class UnBCL::String *,class UnBCL::String *,enum SetupPlatform:"
      ":SP_MIG_SCOPE,int,class UnBCL::String *,class UnBCL::ArrayList<class UnBCL::String *> *,class UnBCL::ArrayList<cla"
      "ss UnBCL::String *> *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *,clas"
      "s UnBCL::String *,class UnBCL::String *,int,int,int,int,int,int,struct ISPTelemetryData **,struct ISPMigProgress *)");
    v216 = GetLastError();
    v217 = CurrentIP();
    v218 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v232);
    v219 = (const char *)UnBCL::String::get_CString(v218);
    v220 = ConstructPartialMsgW(v231, "%s", v219);
    WdsSetupLogMessageW(
      v220,
      819200,
      L"D",
      0,
      7986,
      L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
      L"SPExecuteGather",
      v217,
      v216,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v233);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v232);
    LODWORD(v224) = 4;
    v36 = 4;
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(&v225);
LABEL_105:
    if ( a1 )
    {
LABEL_106:
      v198 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v230);
      pSPDeleteDirectory(v198);
    }
    if ( a2 )
    {
      v199 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
      pSPDeleteDirectory(v199);
    }
    v200 = GetLastError();
    v201 = CurrentIP();
    v202 = ConstructPartialMsgW(0x4000000u, "%hs: End run. Result: 0x%08X", "SPExecuteGather", v36);
    WdsSetupLogMessageW(
      v202,
      819200,
      L"D",
      0,
      8123,
      L"base\\ntsetup\\setupplatform\\lib\\util\\migutils.cpp",
      L"SPExecuteGather",
      v201,
      v200,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v237);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v229);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v235);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v238);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v230);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v236);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v246);
    v239 = &UnBCL::SmartPtr<CSPTelemetryData>::`vftable';
    UnBCL::SmartPtr<COperationsProgress>::DeAssign(&v239);
    result = v36;
  }
  v134 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v237);
  if ( v134 )
  {
    v135 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v231, L"MigJournal.xml");
    v136 = v223 | 2;
    v223 |= 2u;
    v137 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v237);
    v134 = UnBCL::Path::Combine(v137, v135);
  }
  else
  {
    v136 = v223;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v134);
  if ( (v136 & 2) != 0 )
  {
    v223 = v136 & 0xFFFFFFFD;
    UnBCL::String::~String((UnBCL::String *)&v231);
  }
  v138 = UnBCL::SmartPtr<UnBCL::String>::get_P(v221);
  v139 = UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
  v140 = UnBCL::SmartPtr<UnBCL::String>::get_P(v235);
  v141 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(&v225);
  pSPDoMainGather(a5, a6, a7, a8, 0, v133, v141, v140, v139, v138, a14, a15, a16, a17, a18, a19, a20, v240, a24);
}

```

## disassembly

```asm
0x180325c4c  mov     rax, rsp
0x180325c4f  mov     [rax+18h], r8d
0x180325c53  mov     [rax+10h], edx
0x180325c56  mov     [rax+8], ecx
0x180325c59  push    rsi; int
0x180325c5a  push    rdi; int
0x180325c5b  push    r12; __int64
0x180325c5d  push    r13; __int64
0x180325c5f  push    r15; __int64
0x180325c61  sub     rsp, 1F0h
0x180325c68  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x180325c70  mov     [rax+20h], rbx
0x180325c74  mov     rsi, r9
0x180325c77  xor     r12d, r12d
0x180325c7a  mov     [rax-160h], r12d
0x180325c81  cmp     [rsp+218h+arg_50], r12
0x180325c89  jz      loc_180327472
0x180325c8f  mov     r15, [rsp+218h+arg_58]
0x180325c97  test    r15, r15
0x180325c9a  jz      loc_1803274D7
0x180325ca0  cmp     [rsp+218h+arg_A8], r12d
0x180325ca8  jz      short loc_180325CB8
0x180325caa  cmp     [rsp+218h+arg_A0], r12d
0x180325cb2  jz      loc_18032753B
0x180325cb8  call    cs:__imp_GetLastError
0x180325cbe  mov     edi, eax
0x180325cc0  call    cs:__imp_CurrentIP
0x180325cc6  mov     rbx, rax
0x180325cc9  lea     rax, aOnline_0; "Online"
0x180325cd0  lea     r9, aOffline_1; "Offline"
0x180325cd7  cmp     [rsp+218h+arg_20], r12
0x180325cdf  cmovz   r9, rax
0x180325ce3  lea     r8, aSpexecutegathe; "SPExecuteGather"
0x180325cea  lea     rdx, aHsBeginRunS; "%hs: Begin run (%s)"
0x180325cf1  mov     ecx, 4000000h; unsigned int
0x180325cf6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180325cfb  mov     dword ptr [rsp+218h+var_1C8], r12d
0x180325d00  mov     [rsp+218h+var_1D0], r12
0x180325d05  mov     [rsp+218h+var_1D8], edi
0x180325d09  mov     qword ptr [rsp+218h+var_1E0], rbx
0x180325d0e  lea     rcx, aSpexecutegathe_0; "SPExecuteGather"
0x180325d15  mov     qword ptr [rsp+218h+var_1E8], rcx
0x180325d1a  lea     rcx, aBaseNtsetupSet_40; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180325d21  mov     [rsp+218h+var_1F0], rcx
0x180325d26  mov     [rsp+218h+var_1F8], 1EA5h
0x180325d2e  xor     r9d, r9d
0x180325d31  lea     r8, aD_0; "D"
0x180325d38  mov     edx, 0C8000h
0x180325d3d  mov     rcx, rax
0x180325d40  call    cs:__imp_WdsSetupLogMessageW
0x180325d46  mov     rdi, [rsp+218h+arg_20]
0x180325d4e  mov     rcx, rdi; struct UnBCL::String *
0x180325d51  call    ?pSPRemoveUpgradeRegTree@@YAHPEAVString@UnBCL@@@Z; pSPRemoveUpgradeRegTree(UnBCL::String *)
0x180325d56  cmp     [rsp+218h+arg_28], 5
0x180325d5e  jnz     loc_180325E19
0x180325d64  lea     rdx, aDrvfilesDat; "drvfiles.dat"
0x180325d6b  lea     rcx, [rsp+218h+var_88]
0x180325d73  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180325d79  nop
0x180325d7a  mov     rdx, rax
0x180325d7d  mov     rcx, rsi
0x180325d80  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180325d86  mov     rdx, rax
0x180325d89  lea     rcx, [rsp+218h+var_178]
0x180325d91  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180325d97  nop
0x180325d98  lea     rcx, [rsp+218h+var_88]
0x180325da0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180325da6  lea     rcx, [rsp+218h+var_178]
0x180325dae  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180325db4  mov     rcx, rax
0x180325db7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180325dbd  mov     rcx, rax
0x180325dc0  xor     edx, edx
0x180325dc2  call    cs:__imp_BuildDriverFilesList
0x180325dc8  lea     rcx, [rsp+218h+var_178]
0x180325dd0  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180325dd6  mov     rbx, rax
0x180325dd9  lea     rdx, aMigOsdbDrvFile; "MIG_OSDB_DRV_FILES"
0x180325de0  lea     rcx, [rsp+218h+var_140]
0x180325de8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180325dee  nop
0x180325def  mov     rdx, rbx
0x180325df2  mov     rcx, rax
0x180325df5  call    cs:__imp_?SetEnvironmentVar@Environment@UnBCL@@SAXPEBVString@2@0@Z; UnBCL::Environment::SetEnvironmentVar(UnBCL::String const *,UnBCL::String const *)
0x180325dfb  nop
0x180325dfc  lea     rcx, [rsp+218h+var_140]
0x180325e04  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180325e0a  nop
0x180325e0b  lea     rcx, [rsp+218h+var_178]
0x180325e13  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180325e19  xor     r13d, r13d
0x180325e1c  mov     ecx, 80h
0x180325e21  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180325e27  mov     [rsp+218h+var_158], rax
0x180325e2f  test    rax, rax
0x180325e32  jz      short loc_180325E3D
0x180325e34  mov     rcx, rax; this
0x180325e37  call    ??0CSPTelemetryData@@QEAA@XZ; CSPTelemetryData::CSPTelemetryData(void)
0x180325e3c  nop
0x180325e3d  mov     rdx, rax
0x180325e40  lea     rcx, [rsp+218h+var_88]
0x180325e48  call    ??0?$SmartPtr@VCSPTelemetryData@@@UnBCL@@QEAA@PEAVCSPTelemetryData@@@Z; UnBCL::SmartPtr<CSPTelemetryData>::SmartPtr<CSPTelemetryData>(CSPTelemetryData *)
0x180325e4d  nop
0x180325e4e  test    rdi, rdi
0x180325e51  jz      short loc_180325E8A
0x180325e53  mov     ecx, 18h
0x180325e58  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180325e5e  mov     rbx, rax
0x180325e61  mov     [rsp+218h+var_158], rax
0x180325e69  test    rax, rax
0x180325e6c  jz      short loc_180325E86
0x180325e6e  mov     rdx, rdi
0x180325e71  mov     rcx, rax
0x180325e74  call    cs:__imp_??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x180325e7a  lea     rdi, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180325e81  mov     [rbx], rdi
0x180325e84  jmp     short loc_180325E88
0x180325e86  xor     ebx, ebx
0x180325e88  jmp     short loc_180325EBA
0x180325e8a  lea     rdx, aWindir; "%windir%"
0x180325e91  lea     rcx, [rsp+218h+var_178]
0x180325e99  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180325e9f  nop
0x180325ea0  mov     r12d, 1
0x180325ea6  mov     [rsp+218h+var_160], r12d
0x180325eae  mov     rcx, rax
0x180325eb1  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x180325eb7  mov     rbx, rax
0x180325eba  mov     rdx, rbx
0x180325ebd  lea     rcx, [rsp+218h+var_38]
0x180325ec5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180325ecb  nop
0x180325ecc  test    r12b, 1
0x180325ed0  jz      short loc_180325EEC
0x180325ed2  and     r12d, 0FFFFFFFEh
0x180325ed6  mov     [rsp+218h+var_160], r12d; int
0x180325ede  lea     rcx, [rsp+218h+var_178]
0x180325ee6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180325eec  lea     rcx, [rsp+218h+var_B8]
0x180325ef4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180325efa  nop
0x180325efb  lea     rcx, [rsp+218h+var_108]
0x180325f03  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180325f09  nop
0x180325f0a  lea     rcx, [rsp+218h+var_98]
0x180325f12  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180325f18  nop
0x180325f19  lea     rcx, [rsp+218h+var_C8]
0x180325f21  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180325f27  nop
0x180325f28  lea     rcx, [rsp+218h+var_118]
0x180325f30  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180325f36  nop
0x180325f37  lea     rcx, [rsp+218h+var_A8]
0x180325f3f  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180325f45  nop
0x180325f46  lea     rax, ??_7?$SmartPtr@VDirectoryInfo@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable'
0x180325f4d  mov     [rsp+218h+var_150], rax; __int64
0x180325f55  mov     qword ptr [rsp+218h+var_148], 0; int
0x180325f61  mov     esi, [rsp+218h+arg_8]
0x180325f68  test    esi, esi
0x180325f6a  jz      loc_180326258
0x180325f70  lea     r12, aMachineindepen_0; "MachineIndependent"
0x180325f77  mov     rdx, r12
0x180325f7a  lea     rcx, [rsp+218h+var_140]
0x180325f82  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180325f88  nop
0x180325f89  mov     rdx, rax
0x180325f8c  mov     rdi, [rsp+218h+arg_50]
0x180325f94  mov     rcx, rdi
0x180325f97  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180325f9d  mov     rdx, rax
0x180325fa0  lea     rcx, [rsp+218h+var_178]
0x180325fa8  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180325fae  nop
0x180325faf  lea     rdx, [rsp+218h+var_178]
0x180325fb7  lea     rcx, [rsp+218h+var_C8]
0x180325fbf  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180325fc5  nop
0x180325fc6  lea     rcx, [rsp+218h+var_178]
0x180325fce  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180325fd4  nop
0x180325fd5  lea     rcx, [rsp+218h+var_140]
0x180325fdd  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180325fe3  lea     rcx, [rsp+218h+var_C8]
0x180325feb  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180325ff1  mov     rcx, rax
0x180325ff4  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180325ffa  test    eax, eax
0x180325ffc  jz      short loc_180326017
0x180325ffe  lea     rcx, [rsp+218h+var_C8]
0x180326006  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18032600c  xor     r8d, r8d; int
0x18032600f  mov     rcx, rax; struct UnBCL::String *
0x180326012  call    ?SPDeleteFolder@@YAHPEAVString@UnBCL@@HHH@Z; SPDeleteFolder(UnBCL::String *,int,int,int)
0x180326017  lea     rcx, [rsp+218h+var_C8]
0x18032601f  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180326025  mov     rcx, rax
0x180326028  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18032602e  test    eax, eax
0x180326030  jnz     short loc_18032607D
0x180326032  lea     rcx, [rsp+218h+var_C8]
0x18032603a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180326040  mov     rcx, rax
0x180326043  call    cs:__imp_?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z; UnBCL::Directory::CreateDir(UnBCL::String const *)
0x180326049  mov     rdx, rax
0x18032604c  lea     rcx, [rsp+218h+var_178]
0x180326054  call    ??0?$SmartPtr@VDirectoryInfo@UnBCL@@@UnBCL@@QEAA@PEAVDirectoryInfo@1@@Z; UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(UnBCL::DirectoryInfo *)
0x180326059  nop
0x18032605a  mov     rdx, [rsp+218h+var_170]
0x180326062  lea     rcx, [rsp+218h+var_150]
0x18032606a  call    ?Assign@?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@AEAAXPEAVXmlDocument@2@@Z; UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(UnBCL::XmlDocument *)
0x18032606f  nop
0x180326070  lea     rcx, [rsp+218h+var_178]
0x180326078  call    ??1?$SmartPtr@VDirectoryInfo@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(void)
0x18032607d  mov     rdx, r12
0x180326080  lea     rcx, [rsp+218h+var_140]
0x180326088  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18032608e  nop
0x18032608f  mov     rdx, rax
0x180326092  mov     rcx, r15
0x180326095  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18032609b  mov     rdx, rax
0x18032609e  lea     rcx, [rsp+218h+var_178]
0x1803260a6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1803260ac  nop
0x1803260ad  lea     rdx, [rsp+218h+var_178]
0x1803260b5  lea     rcx, [rsp+218h+var_118]
0x1803260bd  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1803260c3  nop
0x1803260c4  lea     rcx, [rsp+218h+var_178]
0x1803260cc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1803260d2  nop
0x1803260d3  lea     rcx, [rsp+218h+var_140]
0x1803260db  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1803260e1  lea     rcx, [rsp+218h+var_118]
0x1803260e9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1803260ef  mov     rcx, rax
0x1803260f2  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x1803260f8  test    eax, eax
0x1803260fa  jz      short loc_180326115
0x1803260fc  lea     rcx, [rsp+218h+var_118]
0x180326104  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18032610a  xor     r8d, r8d; int
0x18032610d  mov     rcx, rax; struct UnBCL::String *
0x180326110  call    ?SPDeleteFolder@@YAHPEAVString@UnBCL@@HHH@Z; SPDeleteFolder(UnBCL::String *,int,int,int)
0x180326115  lea     rcx, [rsp+218h+var_118]
0x18032611d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180326123  mov     rcx, rax
0x180326126  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18032612c  test    eax, eax
0x18032612e  jnz     short loc_18032617B
0x180326130  lea     rcx, [rsp+218h+var_118]
0x180326138  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18032613e  mov     rcx, rax
0x180326141  call    cs:__imp_?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z; UnBCL::Directory::CreateDir(UnBCL::String const *)
0x180326147  mov     rdx, rax
0x18032614a  lea     rcx, [rsp+218h+var_178]
0x180326152  call    ??0?$SmartPtr@VDirectoryInfo@UnBCL@@@UnBCL@@QEAA@PEAVDirectoryInfo@1@@Z; UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(UnBCL::DirectoryInfo *)
0x180326157  nop
0x180326158  mov     rdx, [rsp+218h+var_170]
0x180326160  lea     rcx, [rsp+218h+var_150]
0x180326168  call    ?Assign@?$SmartPtr@VXmlDocument@UnBCL@@@UnBCL@@AEAAXPEAVXmlDocument@2@@Z; UnBCL::SmartPtr<UnBCL::XmlDocument>::Assign(UnBCL::XmlDocument *)
0x18032616d  nop
0x18032616e  lea     rcx, [rsp+218h+var_178]
0x180326176  call    ??1?$SmartPtr@VDirectoryInfo@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(void)
0x18032617b  mov     rbx, [rsp+218h+arg_60]
0x180326183  test    rbx, rbx
0x180326186  jz      loc_180326268
0x18032618c  mov     rdx, r12
0x18032618f  lea     rcx, [rsp+218h+var_140]
0x180326197  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18032619d  nop
0x18032619e  mov     rdx, rax
0x1803261a1  mov     rcx, rbx
0x1803261a4  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1803261aa  mov     rdx, rax
0x1803261ad  lea     rcx, [rsp+218h+var_178]
0x1803261b5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1803261bb  nop
0x1803261bc  lea     rdx, [rsp+218h+var_178]
0x1803261c4  lea     rcx, [rsp+218h+var_A8]
0x1803261cc  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1803261d2  nop
0x1803261d3  lea     rcx, [rsp+218h+var_178]
0x1803261db  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1803261e1  nop
0x1803261e2  lea     rcx, [rsp+218h+var_140]
0x1803261ea  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1803261f0  lea     rcx, [rsp+218h+var_A8]
0x1803261f8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1803261fe  mov     rcx, rax
0x180326201  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180326207  test    eax, eax
0x180326209  jnz     short loc_180326268
0x18032620b  lea     rcx, [rsp+218h+var_A8]
0x180326213  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180326219  mov     rcx, rax
0x18032621c  call    cs:__imp_?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z; UnBCL::Directory::CreateDir(UnBCL::String const *)
  ... truncated ...
```
