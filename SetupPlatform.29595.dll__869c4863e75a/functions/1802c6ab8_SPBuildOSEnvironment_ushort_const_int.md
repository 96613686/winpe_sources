# SPBuildOSEnvironment(ushort const *,int)

- ea: `0x1802c6ab8`
- end: `0x1802c7f7c`
- name: `?SPBuildOSEnvironment@@YAPEAVCBasicEnv@Mig@@PEBGH@Z`
- size: `5316`
- prototype: `struct Mig::CBasicEnv *__fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d4cc0`

## callees

- `0x180057dec`
- `0x1800ae2cc`
- `0x1800c2e14`
- `0x1802c6ab8`
- `0x1802ea590`
- `0x18035734c`
- `0x180357748`
- `0x1803fd0a0`
- `0x1803fd7a8`
- `0x180404554`
- `0x18040466c`
- `0x1804bbfa0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1802c7e9d`
- `ADVAPI32!RegCloseKey` at `0x1802c7e9d`
- `ADVAPI32!RegCreateKeyExW` at `0x1802c72aa`
- `ADVAPI32!RegCreateKeyExW` at `0x1802c72aa`
- `KERNEL32!GetProcessHeap` at `0x1802c6e09`
- `KERNEL32!GetProcessHeap` at `0x1802c6eb4`
- `KERNEL32!GetProcessHeap` at `0x1802c6f58`
- `KERNEL32!GetProcessHeap` at `0x1802c6ffc`
- `KERNEL32!GetProcessHeap` at `0x1802c70a0`
- `KERNEL32!GetProcessHeap` at `0x1802c7144`
- `KERNEL32!GetProcessHeap` at `0x1802c71e8`
- `KERNEL32!GetProcessHeap` at `0x1802c7259`
- `KERNEL32!GetProcessHeap` at `0x1802c7c9e`
- `KERNEL32!GetProcessHeap` at `0x1802c7db8`
- `KERNEL32!GetProcessHeap` at `0x1802c7e4e`
- `KERNEL32!GetProcessHeap` at `0x1802c6e09`
- `KERNEL32!GetProcessHeap` at `0x1802c6eb4`
- `KERNEL32!GetProcessHeap` at `0x1802c6f58`
- `KERNEL32!GetProcessHeap` at `0x1802c6ffc`
- `KERNEL32!GetProcessHeap` at `0x1802c70a0`
- `KERNEL32!GetProcessHeap` at `0x1802c7144`
- `KERNEL32!GetProcessHeap` at `0x1802c71e8`
- `KERNEL32!GetProcessHeap` at `0x1802c7259`
- `KERNEL32!GetProcessHeap` at `0x1802c7c9e`
- `KERNEL32!GetProcessHeap` at `0x1802c7db8`
- `KERNEL32!GetProcessHeap` at `0x1802c7e4e`
- `KERNEL32!HeapFree` at `0x1802c6e17`
- `KERNEL32!HeapFree` at `0x1802c6ec2`
- `KERNEL32!HeapFree` at `0x1802c6f66`
- `KERNEL32!HeapFree` at `0x1802c700a`
- `KERNEL32!HeapFree` at `0x1802c70ae`
- `KERNEL32!HeapFree` at `0x1802c7152`
- `KERNEL32!HeapFree` at `0x1802c71f6`
- `KERNEL32!HeapFree` at `0x1802c7267`
- `KERNEL32!HeapFree` at `0x1802c7cac`
- `KERNEL32!HeapFree` at `0x1802c7dc6`
- `KERNEL32!HeapFree` at `0x1802c7e5c`
- `KERNEL32!HeapFree` at `0x1802c6e17`
- `KERNEL32!HeapFree` at `0x1802c6ec2`
- `KERNEL32!HeapFree` at `0x1802c6f66`
- `KERNEL32!HeapFree` at `0x1802c700a`
- `KERNEL32!HeapFree` at `0x1802c70ae`
- `KERNEL32!HeapFree` at `0x1802c7152`
- `KERNEL32!HeapFree` at `0x1802c71f6`
- `KERNEL32!HeapFree` at `0x1802c7267`
- `KERNEL32!HeapFree` at `0x1802c7cac`
- `KERNEL32!HeapFree` at `0x1802c7dc6`
- `KERNEL32!HeapFree` at `0x1802c7e5c`
- `KERNEL32!GetLastError` at `0x1802c6b9f`
- `KERNEL32!GetLastError` at `0x1802c6bb0`
- `KERNEL32!GetLastError` at `0x1802c72ba`
- `KERNEL32!GetLastError` at `0x1802c6b9f`
- `KERNEL32!GetLastError` at `0x1802c6bb0`
- `KERNEL32!GetLastError` at `0x1802c72ba`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c737e`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7463`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7579`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7653`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c772d`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7807`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c78e1`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c79bb`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7a95`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c737e`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7463`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7579`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7653`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c772d`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7807`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c78e1`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c79bb`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c7a95`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c6b3b`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c6c90`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c6b3b`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802c6c90`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802c7d8b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802c7de8`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802c7e21`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802c7d8b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802c7de8`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802c7e21`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c73d0`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c74ae`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c75c4`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c769e`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7778`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7852`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c792c`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7a06`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7ae0`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c73d0`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c74ae`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c75c4`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c769e`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7778`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7852`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c792c`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7a06`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802c7ae0`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6d17`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6d68`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6d9f`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6dd6`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6e4a`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6e81`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6eee`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6f25`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6f92`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6fc9`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7036`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c706d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c70da`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7111`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c717e`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c71b5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7226`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7c6b`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6d17`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6d68`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6d9f`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6dd6`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6e4a`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6e81`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6eee`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6f25`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6f92`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c6fc9`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7036`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c706d`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c70da`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7111`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c717e`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c71b5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7226`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802c7c6b`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1802c7f0d`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1802c7f0d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c6ccc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c6cdf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c73e2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c741a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c74c0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c74f8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7530`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c75d2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c760a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c76ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c76e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7786`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c77be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7860`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7898`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c793a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7972`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7a14`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7a4c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7aee`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7e66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c6ccc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c6cdf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c73e2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c741a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c74c0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c74f8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7530`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c75d2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c760a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c76ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c76e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7786`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c77be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7860`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7898`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c793a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7972`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7a14`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7a4c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7aee`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802c7e66`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802c6b5d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802c7cb6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802c6b5d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802c7cb6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c6b53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c6cc2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c6d0d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c73b0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7410`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7448`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7495`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c74ee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7526`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c755e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c75ab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7600`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7638`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7685`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c76da`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802c7712`

## string_xrefs

- `0x1802c7ec8`: `ProgramData`
- `0x1802c72d5`: `%hs: Cannot open the software key for the online OS. Error: 0x%08X`
- `0x1802c6ea5`: `CSIDL_PROGRAM_FILES`
- `0x1802c7613`: `CSIDL_PROGRAM_FILES`
- `0x1802c6dfa`: `CSIDL_WINDOWS`
- `0x1802c7539`: `CSIDL_WINDOWS`
- `0x1802c705a`: `CommonProgramFiles`
- `0x1802c7869`: `CommonProgramFiles`
- `0x1802c7091`: `CSIDL_PROGRAM_FILES_COMMON`
- `0x1802c78a1`: `CSIDL_PROGRAM_FILES_COMMON`
- `0x1802c6fed`: `CSIDL_PROGRAM_FILESARM`
- `0x1802c77c7`: `CSIDL_PROGRAM_FILESARM`
- `0x1802c7013`: `CommonFilesDir`
- `0x1802c6f49`: `CSIDL_PROGRAM_FILESX86`
- `0x1802c76ed`: `CSIDL_PROGRAM_FILESX86`
- `0x1802c71a2`: `CommonProgramFiles(Arm)`
- `0x1802c7a1d`: `CommonProgramFiles(Arm)`
- `0x1802c71d9`: `CSIDL_PROGRAM_FILES_COMMONARM`
- `0x1802c7a55`: `CSIDL_PROGRAM_FILES_COMMONARM`
- `0x1802c7135`: `CSIDL_PROGRAM_FILES_COMMONX86`
- `0x1802c797b`: `CSIDL_PROGRAM_FILES_COMMONX86`
- `0x1802c715b`: `CommonFilesDir (Arm)`
- `0x1802c70b7`: `CommonFilesDir (x86)`
- `0x1802c70fe`: `CommonProgramFiles(x86)`
- `0x1802c7943`: `CommonProgramFiles(x86)`
- `0x1802c79a6`: `%CommonProgramFiles(Arm)%`
- `0x1802c77f2`: `%CommonProgramFiles%`
- `0x1802c78cc`: `%CommonProgramFiles(x86)%`
- `0x1802c7c0f`: `CSIDL_SYSTEM`
- `0x1802c7c48`: `ProfilesDirectory`
- `0x1802c7b6c`: `%WINDIR%\system32`
- `0x1802c7bc9`: `SYSTEM32`
- `0x1802c7eb4`: `%SystemDrive%\ProgramData`

## pseudocode

```c
// Hidden C++ exception states: #wind=62
struct Mig::CBasicEnv *__fastcall SPBuildOSEnvironment(const unsigned __int16 *a1)
{
  Mig::CBasicEnv *v2; // rax
  const struct UnBCL::String *v3; // rax
  struct UnBCL::String *ParentPath; // rax
  HKEY v5; // rax
  DWORD LastError; // edi
  __int64 v7; // rbx
  DWORD v8; // eax
  struct tagLOG_PARTIAL_MSG *v9; // rax
  const unsigned __int16 *String; // rax
  unsigned __int16 *v12; // rsi
  Mig::CBasicEnv *v13; // rdi
  const struct UnBCL::String *v14; // rax
  struct UnBCL::String *v15; // rax
  const struct UnBCL::String *P; // rbx
  const struct UnBCL::String *v17; // rax
  UnBCL::String *v18; // rax
  const unsigned __int16 *CString; // rbx
  UnBCL::String *v20; // rax
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // rax
  UnBCL::String *v23; // rax
  const unsigned __int16 *v24; // rax
  UnBCL::String *v25; // rax
  const unsigned __int16 *v26; // rax
  UnBCL::String *v27; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v29; // rbx
  const unsigned __int16 *v30; // rax
  UnBCL::String *v31; // rax
  const unsigned __int16 *v32; // rax
  UnBCL::String *v33; // rax
  HANDLE v34; // rax
  unsigned __int16 *v35; // rbx
  const unsigned __int16 *v36; // rax
  UnBCL::String *v37; // rax
  const unsigned __int16 *v38; // rax
  UnBCL::String *v39; // rax
  HANDLE v40; // rax
  unsigned __int16 *v41; // rbx
  const unsigned __int16 *v42; // rax
  UnBCL::String *v43; // rax
  const unsigned __int16 *v44; // rax
  UnBCL::String *v45; // rax
  HANDLE v46; // rax
  unsigned __int16 *v47; // rbx
  const unsigned __int16 *v48; // rax
  UnBCL::String *v49; // rax
  const unsigned __int16 *v50; // rax
  UnBCL::String *v51; // rax
  HANDLE v52; // rax
  unsigned __int16 *v53; // rbx
  const unsigned __int16 *v54; // rax
  UnBCL::String *v55; // rax
  const unsigned __int16 *v56; // rax
  UnBCL::String *v57; // rax
  HANDLE v58; // rax
  unsigned __int16 *v59; // rbx
  const unsigned __int16 *v60; // rax
  UnBCL::String *v61; // rax
  const unsigned __int16 *v62; // rax
  UnBCL::String *v63; // rax
  HANDLE v64; // rax
  unsigned __int16 *v65; // rbx
  const unsigned __int16 *v66; // rax
  UnBCL::String *v67; // rax
  HANDLE v68; // rax
  LSTATUS v69; // esi
  DWORD v70; // edi
  __int64 v71; // rbx
  struct tagLOG_PARTIAL_MSG *v72; // rax
  const struct UnBCL::String *v73; // rcx
  struct UnBCL::String *v74; // rax
  UnBCL::String *v75; // rax
  int v76; // eax
  const struct UnBCL::String *v77; // rbx
  const struct UnBCL::String *v78; // rax
  const struct UnBCL::String *v79; // rbx
  const struct UnBCL::String *v80; // rax
  const struct UnBCL::String *v81; // rax
  struct UnBCL::String *v82; // rax
  UnBCL::String *v83; // rax
  const struct UnBCL::String *v84; // rbx
  const struct UnBCL::String *v85; // rax
  const struct UnBCL::String *v86; // rbx
  const struct UnBCL::String *v87; // rax
  const struct UnBCL::String *v88; // rbx
  const struct UnBCL::String *v89; // rax
  const struct UnBCL::String *v90; // rax
  struct UnBCL::String *v91; // rax
  UnBCL::String *v92; // rax
  const struct UnBCL::String *v93; // rbx
  const struct UnBCL::String *v94; // rax
  const struct UnBCL::String *v95; // rbx
  const struct UnBCL::String *v96; // rax
  const struct UnBCL::String *v97; // rax
  struct UnBCL::String *v98; // rax
  UnBCL::String *v99; // rax
  const struct UnBCL::String *v100; // rbx
  const struct UnBCL::String *v101; // rax
  const struct UnBCL::String *v102; // rbx
  const struct UnBCL::String *v103; // rax
  const struct UnBCL::String *v104; // rax
  struct UnBCL::String *v105; // rax
  UnBCL::String *v106; // rax
  const struct UnBCL::String *v107; // rbx
  const struct UnBCL::String *v108; // rax
  const struct UnBCL::String *v109; // rbx
  const struct UnBCL::String *v110; // rax
  const struct UnBCL::String *v111; // rax
  struct UnBCL::String *v112; // rax
  UnBCL::String *v113; // rax
  const struct UnBCL::String *v114; // rbx
  const struct UnBCL::String *v115; // rax
  const struct UnBCL::String *v116; // rbx
  const struct UnBCL::String *v117; // rax
  const struct UnBCL::String *v118; // rax
  struct UnBCL::String *v119; // rax
  UnBCL::String *v120; // rax
  const struct UnBCL::String *v121; // rbx
  const struct UnBCL::String *v122; // rax
  const struct UnBCL::String *v123; // rbx
  const struct UnBCL::String *v124; // rax
  const struct UnBCL::String *v125; // rax
  struct UnBCL::String *v126; // rax
  UnBCL::String *v127; // rax
  const struct UnBCL::String *v128; // rbx
  const struct UnBCL::String *v129; // rax
  const struct UnBCL::String *v130; // rbx
  const struct UnBCL::String *v131; // rax
  const struct UnBCL::String *v132; // rax
  struct UnBCL::String *v133; // rax
  UnBCL::String *v134; // rax
  const struct UnBCL::String *v135; // rbx
  const struct UnBCL::String *v136; // rax
  const struct UnBCL::String *v137; // rbx
  const struct UnBCL::String *v138; // rax
  const struct UnBCL::String *v139; // rbx
  const struct UnBCL::String *v140; // rax
  const struct UnBCL::String *v141; // rbx
  const struct UnBCL::String *v142; // rax
  const struct UnBCL::String *v143; // rbx
  const struct UnBCL::String *v144; // rax
  unsigned __int16 *v145; // rbx
  const unsigned __int16 *v146; // rax
  UnBCL::String *v147; // rax
  HANDLE v148; // rax
  unsigned int Dword; // ebx
  unsigned int v150; // r14d
  __int64 v151; // rax
  void *v152; // rsi
  __int64 v153; // rax
  unsigned __int16 *v154; // r14
  UnBCL::String *v155; // rax
  UnBCL::String *v156; // rbx
  struct UnBCL::String *v157; // rax
  HANDLE v158; // rax
  struct UnBCL::String *v159; // rax
  struct UnBCL::String *v160; // rax
  HANDLE v161; // rax
  UnBCL::String *v162; // rax
  const unsigned __int16 *v163; // rax
  HKEY v164; // rcx
  const struct UnBCL::String *v165; // rbx
  const struct UnBCL::String *v166; // rax
  _BYTE v167[24]; // [rsp+68h] [rbp-59h] BYREF
  _QWORD v168[3]; // [rsp+80h] [rbp-41h] BYREF
  void **v169; // [rsp+98h] [rbp-29h] BYREF
  Mig::CBasicEnv *v170; // [rsp+A0h] [rbp-21h]
  __int64 v171; // [rsp+A8h] [rbp-19h]
  HKEY hKey; // [rsp+B0h] [rbp-11h] BYREF
  _BYTE v173[16]; // [rsp+B8h] [rbp-9h] BYREF
  _BYTE v174[16]; // [rsp+C8h] [rbp+7h] BYREF
  _BYTE v175[16]; // [rsp+D8h] [rbp+17h] BYREF

  v171 = -2;
  v2 = (Mig::CBasicEnv *)UnBCL::Object::operator new(0x50u);
  v168[0] = v2;
  if ( v2 )
    v2 = (Mig::CBasicEnv *)Mig::CBasicEnv::CBasicEnv(v2);
  UnBCL::SmartPtr<Mig::CBasicEnv>::SmartPtr<Mig::CBasicEnv>(&v169, v2);
  v3 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, a1);
  LODWORD(v168[0]) = 1;
  ParentPath = UnBCL::Path::GetParentPath(v3);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v174, ParentPath);
  UnBCL::String::~String((UnBCL::String *)v167);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v173);
  hKey = 0;
  if ( a1 )
  {
    v5 = SPMountOfflineHive(a1, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
    hKey = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      v7 = CurrentIP();
      v8 = GetLastError();
      v9 = ConstructPartialMsgW(
             0x2000000u,
             "%hs: Cannot load the software hive for the offline OS %s. Error: 0x%08X",
             "SPBuildOSEnvironment",
             (const char *)a1,
             v8);
      WdsSetupLogMessageW(
        v9,
        819200,
        L"D",
        0,
        336,
        L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
        L"SPBuildOSEnvironment",
        v7,
        LastError,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v173);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v174);
      v169 = &UnBCL::SmartPtr<Mig::CBasicEnv>::`vftable';
      UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v169);
      return 0;
    }
    String = (const unsigned __int16 *)RegGetStringEx(v5, L"Microsoft\\Windows NT\\CurrentVersion", L"SystemRoot", 0);
    v12 = (unsigned __int16 *)String;
    v13 = v170;
    if ( String )
    {
      v14 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, String);
      v15 = UnBCL::Path::GetParentPath(v14);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v15);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
      UnBCL::String::~String((UnBCL::String *)v167);
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v173) )
      {
        P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
        v17 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SystemDriveNative");
        Mig::CBasicEnv::Add(v13, v17, P);
        UnBCL::String::~String((UnBCL::String *)v167);
        if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174) )
        {
          v18 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
          CString = UnBCL::String::get_CString(v18);
        }
        else
        {
          CString = 0;
        }
        v20 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
        v21 = UnBCL::String::get_CString(v20);
        pAddToEnv(v13, L"SystemDrive", v21, CString);
      }
      v22 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v22 )
      {
        v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v22 = UnBCL::String::get_CString(v23);
      }
      pAddToEnv(v13, L"WinDir", v12, v22);
      v24 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v24 )
      {
        v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v24 = UnBCL::String::get_CString(v25);
      }
      pAddToEnv(v13, L"SystemRoot", v12, v24);
      v26 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v26 )
      {
        v27 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v26 = UnBCL::String::get_CString(v27);
      }
      pAddToEnv(v13, L"CSIDL_WINDOWS", v12, v26);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    v29 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows\\CurrentVersion", L"ProgramFilesDir", 0);
    if ( v29 )
    {
      v30 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v30 )
      {
        v31 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v30 = UnBCL::String::get_CString(v31);
      }
      pAddToEnv(v13, L"ProgramFiles", v29, v30);
      v32 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v32 )
      {
        v33 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v32 = UnBCL::String::get_CString(v33);
      }
      pAddToEnv(v13, L"CSIDL_PROGRAM_FILES", v29, v32);
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v29);
    }
    v35 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows\\CurrentVersion", L"ProgramFilesDir (x86)", 0);
    if ( v35 )
    {
      v36 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v36 )
      {
        v37 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v36 = UnBCL::String::get_CString(v37);
      }
      pAddToEnv(v13, L"ProgramFiles(x86)", v35, v36);
      v38 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v38 )
      {
        v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v38 = UnBCL::String::get_CString(v39);
      }
      pAddToEnv(v13, L"CSIDL_PROGRAM_FILESX86", v35, v38);
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v35);
    }
    v41 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows\\CurrentVersion", L"ProgramFilesDir (Arm)", 0);
    if ( v41 )
    {
      v42 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v42 )
      {
        v43 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v42 = UnBCL::String::get_CString(v43);
      }
      pAddToEnv(v13, L"ProgramFiles(Arm)", v41, v42);
      v44 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v44 )
      {
        v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v44 = UnBCL::String::get_CString(v45);
      }
      pAddToEnv(v13, L"CSIDL_PROGRAM_FILESARM", v41, v44);
      v46 = GetProcessHeap();
      HeapFree(v46, 0, v41);
    }
    v47 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows\\CurrentVersion", L"CommonFilesDir", 0);
    if ( v47 )
    {
      v48 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v48 )
      {
        v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v48 = UnBCL::String::get_CString(v49);
      }
      pAddToEnv(v13, L"CommonProgramFiles", v47, v48);
      v50 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v50 )
      {
        v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v50 = UnBCL::String::get_CString(v51);
      }
      pAddToEnv(v13, L"CSIDL_PROGRAM_FILES_COMMON", v47, v50);
      v52 = GetProcessHeap();
      HeapFree(v52, 0, v47);
    }
    v53 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows\\CurrentVersion", L"CommonFilesDir (x86)", 0);
    if ( v53 )
    {
      v54 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v54 )
      {
        v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v54 = UnBCL::String::get_CString(v55);
      }
      pAddToEnv(v13, L"CommonProgramFiles(x86)", v53, v54);
      v56 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v56 )
      {
        v57 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v56 = UnBCL::String::get_CString(v57);
      }
      pAddToEnv(v13, L"CSIDL_PROGRAM_FILES_COMMONX86", v53, v56);
      v58 = GetProcessHeap();
      HeapFree(v58, 0, v53);
    }
    v59 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows\\CurrentVersion", L"CommonFilesDir (Arm)", 0);
    if ( v59 )
    {
      v60 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v60 )
      {
        v61 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v60 = UnBCL::String::get_CString(v61);
      }
      pAddToEnv(v13, L"CommonProgramFiles(Arm)", v59, v60);
      v62 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v62 )
      {
        v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v62 = UnBCL::String::get_CString(v63);
      }
      pAddToEnv(v13, L"CSIDL_PROGRAM_FILES_COMMONARM", v59, v62);
      v64 = GetProcessHeap();
      HeapFree(v64, 0, v59);
    }
    v65 = (unsigned __int16 *)RegGetStringEx(hKey, L"Microsoft\\Windows NT\\CurrentVersion\\ProfileList", L"Public", 0);
    if ( v65 )
    {
      v66 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
      if ( v66 )
      {
        v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
        v66 = UnBCL::String::get_CString(v67);
      }
      pAddToEnv(v13, L"public", v65, v66);
      v68 = GetProcessHeap();
      HeapFree(v68, 0, v65);
    }
  }
  else
  {
    v69 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE", 0, 0, 0, 0x20019u, 0, &hKey, 0);
    if ( v69 )
    {
      v70 = GetLastError();
      v71 = CurrentIP();
      v72 = ConstructPartialMsgW(
              0x2000000u,
              "%hs: Cannot open the software key for the online OS. Error: 0x%08X",
              "SPBuildOSEnvironment",
              v69);
      WdsSetupLogMessageW(
        v72,
        819200,
        L"D",
        0,
        407,
        L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
        L"SPBuildOSEnvironment",
        v71,
        v70,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v173);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v174);
      v169 = &UnBCL::SmartPtr<Mig::CBasicEnv>::`vftable';
      UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v169);
      return 0;
    }
    v73 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%SystemDrive%");
    v74 = UnBCL::Environment::ExpandEnvironmentVariables(v73);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v74);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v75 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    v76 = UnBCL::String::StartsWith(v75, L"%", 1);
    v13 = v170;
    if ( !v76 )
    {
      v77 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v78 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SystemDriveNative");
      Mig::CBasicEnv::Add(v13, v78, v77);
      UnBCL::String::~String((UnBCL::String *)v167);
      v79 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v80 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SystemDrive");
      Mig::CBasicEnv::Add(v13, v80, v79);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v81 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%WinDir%");
    v82 = UnBCL::Environment::ExpandEnvironmentVariables(v81);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v82);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v83 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v83, L"%", 1) )
    {
      v84 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v85 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"WinDir");
      Mig::CBasicEnv::Add(v13, v85, v84);
      UnBCL::String::~String((UnBCL::String *)v167);
      v86 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v87 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SystemRoot");
      Mig::CBasicEnv::Add(v13, v87, v86);
      UnBCL::String::~String((UnBCL::String *)v167);
      v88 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v89 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CSIDL_WINDOWS");
      Mig::CBasicEnv::Add(v13, v89, v88);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v90 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%ProgramFiles%");
    v91 = UnBCL::Environment::ExpandEnvironmentVariables(v90);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v91);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v92 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v92, L"%", 1) )
    {
      v93 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v94 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"ProgramFiles");
      Mig::CBasicEnv::Add(v13, v94, v93);
      UnBCL::String::~String((UnBCL::String *)v167);
      v95 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v96 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CSIDL_PROGRAM_FILES");
      Mig::CBasicEnv::Add(v13, v96, v95);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v97 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%ProgramFiles(x86)%");
    v98 = UnBCL::Environment::ExpandEnvironmentVariables(v97);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v98);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v99 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v99, L"%", 1) )
    {
      v100 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v101 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"ProgramFiles(x86)");
      Mig::CBasicEnv::Add(v13, v101, v100);
      UnBCL::String::~String((UnBCL::String *)v167);
      v102 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v103 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CSIDL_PROGRAM_FILESX86");
      Mig::CBasicEnv::Add(v13, v103, v102);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v104 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%ProgramFiles(Arm)%");
    v105 = UnBCL::Environment::ExpandEnvironmentVariables(v104);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v105);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v106 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v106, L"%", 1) )
    {
      v107 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v108 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"ProgramFiles(Arm)");
      Mig::CBasicEnv::Add(v13, v108, v107);
      UnBCL::String::~String((UnBCL::String *)v167);
      v109 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v110 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CSIDL_PROGRAM_FILESARM");
      Mig::CBasicEnv::Add(v13, v110, v109);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v111 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%CommonProgramFiles%");
    v112 = UnBCL::Environment::ExpandEnvironmentVariables(v111);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v112);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v113 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v113, L"%", 1) )
    {
      v114 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v115 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CommonProgramFiles");
      Mig::CBasicEnv::Add(v13, v115, v114);
      UnBCL::String::~String((UnBCL::String *)v167);
      v116 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v117 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CSIDL_PROGRAM_FILES_COMMON");
      Mig::CBasicEnv::Add(v13, v117, v116);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v118 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%CommonProgramFiles(x86)%");
    v119 = UnBCL::Environment::ExpandEnvironmentVariables(v118);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v119);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v120 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v120, L"%", 1) )
    {
      v121 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v122 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CommonProgramFiles(x86)");
      Mig::CBasicEnv::Add(v13, v122, v121);
      UnBCL::String::~String((UnBCL::String *)v167);
      v123 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v124 = (const struct UnBCL::String *)UnBCL::String::String(
                                             (UnBCL::String *)v167,
                                             L"CSIDL_PROGRAM_FILES_COMMONX86");
      Mig::CBasicEnv::Add(v13, v124, v123);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v125 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%CommonProgramFiles(Arm)%");
    v126 = UnBCL::Environment::ExpandEnvironmentVariables(v125);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v126);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v127 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v127, L"%", 1) )
    {
      v128 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v129 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CommonProgramFiles(Arm)");
      Mig::CBasicEnv::Add(v13, v129, v128);
      UnBCL::String::~String((UnBCL::String *)v167);
      v130 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v131 = (const struct UnBCL::String *)UnBCL::String::String(
                                             (UnBCL::String *)v167,
                                             L"CSIDL_PROGRAM_FILES_COMMONARM");
      Mig::CBasicEnv::Add(v13, v131, v130);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
    v132 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"%public%");
    v133 = UnBCL::Environment::ExpandEnvironmentVariables(v132);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168, v133);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v173, v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
    UnBCL::String::~String((UnBCL::String *)v167);
    v134 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v173);
    if ( !UnBCL::String::StartsWith(v134, L"%", 1) )
    {
      v135 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
      v136 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"public");
      Mig::CBasicEnv::Add(v13, v136, v135);
      UnBCL::String::~String((UnBCL::String *)v167);
    }
  }
  v137 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v168, L"%WINDIR%\\system");
  v138 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SYSTEM16");
  Mig::CBasicEnv::Add(v13, v138, v137);
  UnBCL::String::~String((UnBCL::String *)v167);
  UnBCL::String::~String((UnBCL::String *)v168);
  v139 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v168, L"%WINDIR%\\system32");
  v140 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SYSTEM");
  Mig::CBasicEnv::Add(v13, v140, v139);
  UnBCL::String::~String((UnBCL::String *)v167);
  UnBCL::String::~String((UnBCL::String *)v168);
  v141 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v168, L"%WINDIR%\\system32");
  v142 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"SYSTEM32");
  Mig::CBasicEnv::Add(v13, v142, v141);
  UnBCL::String::~String((UnBCL::String *)v167);
  UnBCL::String::~String((UnBCL::String *)v168);
  v143 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v168, L"%WINDIR%\\system32");
  v144 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"CSIDL_SYSTEM");
  Mig::CBasicEnv::Add(v13, v144, v143);
  UnBCL::String::~String((UnBCL::String *)v167);
  UnBCL::String::~String((UnBCL::String *)v168);
  v145 = (unsigned __int16 *)RegGetStringEx(
                               hKey,
                               L"Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                               L"ProfilesDirectory",
                               0);
  if ( v145 )
  {
    v146 = (const unsigned __int16 *)UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v174);
    if ( v146 )
    {
      v147 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v174);
      v146 = UnBCL::String::get_CString(v147);
    }
    pAddToEnv(v13, L"ProfilesFolder", v145, v146);
    v148 = GetProcessHeap();
    HeapFree(v148, 0, v145);
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v175);
  Dword = RegGetDword(hKey, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentMajorVersionNumber");
  v150 = RegGetDword(hKey, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentMinorVersionNumber");
  v151 = RegGetStringEx(hKey, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentBuild", 0);
  v152 = (void *)v151;
  if ( !Dword )
  {
    v153 = RegGetStringEx(hKey, L"Microsoft\\Windows NT\\CurrentVersion", L"CurrentVersion", 0);
    v154 = (unsigned __int16 *)v153;
    if ( v153 )
    {
      if ( v152 )
      {
        v157 = UnBCL::String::Format(L"%s.%s", v153, v152);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, v157);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v175, v167);
      }
      else
      {
        v155 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v156 = v155;
        v168[0] = v155;
        if ( v155 )
        {
          UnBCL::String::String(v155, v154);
          *(_QWORD *)v156 = &UnBCL::String::`local vftable';
        }
        else
        {
          v156 = 0;
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, v156);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v175, v167);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v167);
      v158 = GetProcessHeap();
      HeapFree(v158, 0, v154);
    }
    if ( !v152 )
      goto LABEL_99;
    goto LABEL_98;
  }
  if ( v151 )
  {
    v160 = UnBCL::String::Format(L"%u.%u.%s", Dword, v150, v151);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, v160);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v175, v167);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v167);
LABEL_98:
    v161 = GetProcessHeap();
    HeapFree(v161, 0, v152);
    goto LABEL_99;
  }
  v159 = UnBCL::String::Format(L"%u.%u", Dword, v150);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, v159);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v175, v167);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v167);
LABEL_99:
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v175) )
  {
    v162 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v175);
    v163 = UnBCL::String::get_CString(v162);
    pAddToEnv(v13, L"OSVersion", v163, 0);
  }
  RegCloseKey(hKey);
  if ( a1 )
    SPUnloadKey(v164, L"$OFFLINE_RW$SOFTWARE");
  v165 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v168, L"%SystemDrive%\\ProgramData");
  v166 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v167, L"ProgramData");
  Mig::CBasicEnv::Add(v13, v166, v165);
  UnBCL::String::~String((UnBCL::String *)v167);
  UnBCL::String::~String((UnBCL::String *)v168);
  if ( v13 )
  {
    UnBCL::Object::DecRef((Mig::CBasicEnv *)((char *)v13 + *(int *)(*(_QWORD *)v13 + 4LL)));
    v170 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v175);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v173);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v174);
  v169 = &UnBCL::SmartPtr<Mig::CBasicEnv>::`vftable';
  UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v169);
  return v13;
}

```

## disassembly

```asm
0x1802c6ab8  mov     rax, rsp
0x1802c6abb  push    rbp
0x1802c6abc  push    rdi
0x1802c6abd  push    r13
0x1802c6abf  push    r14
0x1802c6ac1  push    r15
0x1802c6ac3  lea     rbp, [rax-5Fh]
0x1802c6ac7  sub     rsp, 0F0h
0x1802c6ace  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x1802c6ad6  mov     [rax+10h], rbx
0x1802c6ada  mov     [rax+18h], rsi
0x1802c6ade  mov     rax, cs:__security_cookie
0x1802c6ae5  xor     rax, rsp
0x1802c6ae8  mov     [rbp+57h+var_30], rax
0x1802c6aec  mov     r15, rcx
0x1802c6aef  mov     dword ptr [rbp+57h+var_98], 0
0x1802c6af6  mov     ecx, 50h ; 'P'
0x1802c6afb  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802c6b01  mov     [rbp+57h+var_98], rax
0x1802c6b05  test    rax, rax
0x1802c6b08  jz      short loc_1802C6B13
0x1802c6b0a  mov     rcx, rax; this
0x1802c6b0d  call    ??0CBasicEnv@Mig@@QEAA@XZ; Mig::CBasicEnv::CBasicEnv(void)
0x1802c6b12  nop
0x1802c6b13  mov     rdx, rax
0x1802c6b16  lea     rcx, [rbp+57h+var_80]
0x1802c6b1a  call    ??0?$SmartPtr@VCBasicEnv@Mig@@@UnBCL@@QEAA@PEAVCBasicEnv@Mig@@@Z; UnBCL::SmartPtr<Mig::CBasicEnv>::SmartPtr<Mig::CBasicEnv>(Mig::CBasicEnv *)
0x1802c6b1f  nop
0x1802c6b20  mov     rdx, r15
0x1802c6b23  lea     rcx, [rbp+57h+var_B0]
0x1802c6b27  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802c6b2d  nop
0x1802c6b2e  mov     r14d, 1
0x1802c6b34  mov     dword ptr [rbp+57h+var_98], r14d
0x1802c6b38  mov     rcx, rax
0x1802c6b3b  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x1802c6b41  mov     rdx, rax
0x1802c6b44  lea     rcx, [rbp+57h+var_50]
0x1802c6b48  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802c6b4e  nop
0x1802c6b4f  lea     rcx, [rbp+57h+var_B0]
0x1802c6b53  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802c6b59  lea     rcx, [rbp+57h+var_60]
0x1802c6b5d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802c6b63  nop
0x1802c6b64  mov     [rbp+57h+hKey], 0
0x1802c6b6c  lea     r13, aMicrosoftWindo_9; "Microsoft\\Windows NT\\CurrentVersion"
0x1802c6b73  lea     rdx, aSoftware; "SOFTWARE"
0x1802c6b7a  test    r15, r15
0x1802c6b7d  jz      loc_1802C7272
0x1802c6b83  lea     r8, aOfflineRwSoftw; "$OFFLINE_RW$SOFTWARE"
0x1802c6b8a  mov     rcx, r15; unsigned __int16 *
0x1802c6b8d  call    ?SPMountOfflineHive@@YAPEAUHKEY__@@PEBG00@Z; SPMountOfflineHive(ushort const *,ushort const *,ushort const *)
0x1802c6b92  mov     [rbp+57h+hKey], rax
0x1802c6b96  test    rax, rax
0x1802c6b99  jnz     loc_1802C6C5A
0x1802c6b9f  call    cs:__imp_GetLastError
0x1802c6ba5  mov     edi, eax
0x1802c6ba7  call    cs:__imp_CurrentIP
0x1802c6bad  mov     rbx, rax
0x1802c6bb0  call    cs:__imp_GetLastError
0x1802c6bb6  mov     [rsp+110h+dwOptions], eax
0x1802c6bba  mov     r9, r15
0x1802c6bbd  lea     r8, aSpbuildosenvir_0; "SPBuildOSEnvironment"
0x1802c6bc4  lea     rdx, aHsCannotLoadTh; "%hs: Cannot load the software hive for "...
0x1802c6bcb  mov     ecx, 2000000h; unsigned int
0x1802c6bd0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802c6bd5  mov     [rsp+110h+var_C0], 0
0x1802c6bdd  mov     qword ptr [rsp+110h+var_C8], 0
0x1802c6be6  mov     dword ptr [rsp+110h+lpdwDisposition], edi
0x1802c6bea  mov     [rsp+110h+phkResult], rbx
0x1802c6bef  lea     rcx, aSpbuildosenvir; "SPBuildOSEnvironment"
0x1802c6bf6  mov     [rsp+110h+lpSecurityAttributes], rcx
0x1802c6bfb  lea     rcx, aBaseNtsetupSet_29; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1802c6c02  mov     qword ptr [rsp+110h+samDesired], rcx
0x1802c6c07  mov     [rsp+110h+dwOptions], 150h
0x1802c6c0f  xor     r9d, r9d
0x1802c6c12  lea     r8, aD_0; "D"
0x1802c6c19  mov     edx, 0C8000h
0x1802c6c1e  mov     rcx, rax
0x1802c6c21  call    cs:__imp_WdsSetupLogMessageW
0x1802c6c27  nop
0x1802c6c28  lea     rcx, [rbp+57h+var_60]
0x1802c6c2c  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802c6c32  nop
0x1802c6c33  lea     rcx, [rbp+57h+var_50]
0x1802c6c37  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802c6c3d  nop
0x1802c6c3e  lea     rax, ??_7?$SmartPtr@VCBasicEnv@Mig@@@UnBCL@@6B@; const UnBCL::SmartPtr<Mig::CBasicEnv>::`vftable'
0x1802c6c45  mov     [rbp+57h+var_80], rax
0x1802c6c49  lea     rcx, [rbp+57h+var_80]
0x1802c6c4d  call    ?DeAssign@?$SmartPtr@VCOptionalComponent@OC@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(void)
0x1802c6c52  nop
0x1802c6c53  xor     eax, eax
0x1802c6c55  jmp     loc_1802C7F54
0x1802c6c5a  xor     r9d, r9d
0x1802c6c5d  lea     r8, aSystemroot; "SystemRoot"
0x1802c6c64  mov     rdx, r13
0x1802c6c67  mov     rcx, rax
0x1802c6c6a  call    RegGetStringEx
0x1802c6c6f  mov     rsi, rax
0x1802c6c72  mov     rdi, [rbp+57h+var_78]
0x1802c6c76  test    rax, rax
0x1802c6c79  jz      loc_1802C6E1D
0x1802c6c7f  mov     rdx, rax
0x1802c6c82  lea     rcx, [rbp+57h+var_B0]
0x1802c6c86  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802c6c8c  nop
0x1802c6c8d  mov     rcx, rax
0x1802c6c90  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x1802c6c96  mov     rdx, rax
0x1802c6c99  lea     rcx, [rbp+57h+var_98]
0x1802c6c9d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802c6ca3  nop
0x1802c6ca4  lea     rdx, [rbp+57h+var_98]
0x1802c6ca8  lea     rcx, [rbp+57h+var_60]
0x1802c6cac  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802c6cb2  nop
0x1802c6cb3  lea     rcx, [rbp+57h+var_98]
0x1802c6cb7  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802c6cbd  nop
0x1802c6cbe  lea     rcx, [rbp+57h+var_B0]
0x1802c6cc2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802c6cc8  lea     rcx, [rbp+57h+var_60]
0x1802c6ccc  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802c6cd2  test    rax, rax
0x1802c6cd5  jz      loc_1802C6D64
0x1802c6cdb  lea     rcx, [rbp+57h+var_60]
0x1802c6cdf  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802c6ce5  mov     rbx, rax
0x1802c6ce8  lea     rdx, aSystemdrivenat_0; "SystemDriveNative"
0x1802c6cef  lea     rcx, [rbp+57h+var_B0]
0x1802c6cf3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802c6cf9  nop
0x1802c6cfa  mov     r8, rbx; struct UnBCL::String *
0x1802c6cfd  mov     rdx, rax; struct UnBCL::String *
0x1802c6d00  mov     rcx, rdi; this
0x1802c6d03  call    ?Add@CBasicEnv@Mig@@QEAAXPEBVString@UnBCL@@0@Z; Mig::CBasicEnv::Add(UnBCL::String const *,UnBCL::String const *)
0x1802c6d08  nop
0x1802c6d09  lea     rcx, [rbp+57h+var_B0]
0x1802c6d0d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802c6d13  lea     rcx, [rbp+57h+var_50]
0x1802c6d17  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6d1d  test    rax, rax
0x1802c6d20  jz      short loc_1802C6D3A
0x1802c6d22  lea     rcx, [rbp+57h+var_50]
0x1802c6d26  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6d2c  mov     rcx, rax
0x1802c6d2f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6d35  mov     rbx, rax
0x1802c6d38  jmp     short loc_1802C6D3C
0x1802c6d3a  xor     ebx, ebx
0x1802c6d3c  lea     rcx, [rbp+57h+var_60]
0x1802c6d40  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6d46  mov     rcx, rax
0x1802c6d49  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6d4f  mov     r9, rbx; unsigned __int16 *
0x1802c6d52  mov     r8, rax; unsigned __int16 *
0x1802c6d55  lea     rdx, aSystemdrive; "SystemDrive"
0x1802c6d5c  mov     rcx, rdi; this
0x1802c6d5f  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6d64  lea     rcx, [rbp+57h+var_50]
0x1802c6d68  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6d6e  test    rax, rax
0x1802c6d71  jz      short loc_1802C6D86
0x1802c6d73  lea     rcx, [rbp+57h+var_50]
0x1802c6d77  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6d7d  mov     rcx, rax
0x1802c6d80  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6d86  mov     r9, rax; unsigned __int16 *
0x1802c6d89  mov     r8, rsi; unsigned __int16 *
0x1802c6d8c  lea     rdx, aWindir_2; "WinDir"
0x1802c6d93  mov     rcx, rdi; this
0x1802c6d96  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6d9b  lea     rcx, [rbp+57h+var_50]
0x1802c6d9f  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6da5  test    rax, rax
0x1802c6da8  jz      short loc_1802C6DBD
0x1802c6daa  lea     rcx, [rbp+57h+var_50]
0x1802c6dae  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6db4  mov     rcx, rax
0x1802c6db7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6dbd  mov     r9, rax; unsigned __int16 *
0x1802c6dc0  mov     r8, rsi; unsigned __int16 *
0x1802c6dc3  lea     rdx, aSystemroot; "SystemRoot"
0x1802c6dca  mov     rcx, rdi; this
0x1802c6dcd  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6dd2  lea     rcx, [rbp+57h+var_50]
0x1802c6dd6  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6ddc  test    rax, rax
0x1802c6ddf  jz      short loc_1802C6DF4
0x1802c6de1  lea     rcx, [rbp+57h+var_50]
0x1802c6de5  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6deb  mov     rcx, rax
0x1802c6dee  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6df4  mov     r9, rax; unsigned __int16 *
0x1802c6df7  mov     r8, rsi; unsigned __int16 *
0x1802c6dfa  lea     rdx, aCsidlWindows; "CSIDL_WINDOWS"
0x1802c6e01  mov     rcx, rdi; this
0x1802c6e04  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6e09  call    cs:__imp_GetProcessHeap
0x1802c6e0f  mov     rcx, rax; hHeap
0x1802c6e12  mov     r8, rsi; lpMem
0x1802c6e15  xor     edx, edx; dwFlags
0x1802c6e17  call    cs:__imp_HeapFree
0x1802c6e1d  xor     r9d, r9d
0x1802c6e20  lea     r8, aProgramfilesdi_1; "ProgramFilesDir"
0x1802c6e27  lea     rsi, aMicrosoftWindo_7; "Microsoft\\Windows\\CurrentVersion"
0x1802c6e2e  mov     rdx, rsi
0x1802c6e31  mov     rcx, [rbp+57h+hKey]
0x1802c6e35  call    RegGetStringEx
0x1802c6e3a  mov     rbx, rax
0x1802c6e3d  test    rax, rax
0x1802c6e40  jz      loc_1802C6EC8
0x1802c6e46  lea     rcx, [rbp+57h+var_50]
0x1802c6e4a  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6e50  test    rax, rax
0x1802c6e53  jz      short loc_1802C6E68
0x1802c6e55  lea     rcx, [rbp+57h+var_50]
0x1802c6e59  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6e5f  mov     rcx, rax
0x1802c6e62  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6e68  mov     r9, rax; unsigned __int16 *
0x1802c6e6b  mov     r8, rbx; unsigned __int16 *
0x1802c6e6e  lea     rdx, aProgramfiles_1; "ProgramFiles"
0x1802c6e75  mov     rcx, rdi; this
0x1802c6e78  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6e7d  lea     rcx, [rbp+57h+var_50]
0x1802c6e81  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6e87  test    rax, rax
0x1802c6e8a  jz      short loc_1802C6E9F
0x1802c6e8c  lea     rcx, [rbp+57h+var_50]
0x1802c6e90  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6e96  mov     rcx, rax
0x1802c6e99  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6e9f  mov     r9, rax; unsigned __int16 *
0x1802c6ea2  mov     r8, rbx; unsigned __int16 *
0x1802c6ea5  lea     rdx, aCsidlProgramFi_3; "CSIDL_PROGRAM_FILES"
0x1802c6eac  mov     rcx, rdi; this
0x1802c6eaf  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6eb4  call    cs:__imp_GetProcessHeap
0x1802c6eba  mov     rcx, rax; hHeap
0x1802c6ebd  mov     r8, rbx; lpMem
0x1802c6ec0  xor     edx, edx; dwFlags
0x1802c6ec2  call    cs:__imp_HeapFree
0x1802c6ec8  xor     r9d, r9d
0x1802c6ecb  lea     r8, aProgramfilesdi_0; "ProgramFilesDir (x86)"
0x1802c6ed2  mov     rdx, rsi
0x1802c6ed5  mov     rcx, [rbp+57h+hKey]
0x1802c6ed9  call    RegGetStringEx
0x1802c6ede  mov     rbx, rax
0x1802c6ee1  test    rax, rax
0x1802c6ee4  jz      loc_1802C6F6C
0x1802c6eea  lea     rcx, [rbp+57h+var_50]
0x1802c6eee  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6ef4  test    rax, rax
0x1802c6ef7  jz      short loc_1802C6F0C
0x1802c6ef9  lea     rcx, [rbp+57h+var_50]
0x1802c6efd  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6f03  mov     rcx, rax
0x1802c6f06  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6f0c  mov     r9, rax; unsigned __int16 *
0x1802c6f0f  mov     r8, rbx; unsigned __int16 *
0x1802c6f12  lea     rdx, aProgramfilesX8_1; "ProgramFiles(x86)"
0x1802c6f19  mov     rcx, rdi; this
0x1802c6f1c  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6f21  lea     rcx, [rbp+57h+var_50]
0x1802c6f25  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6f2b  test    rax, rax
0x1802c6f2e  jz      short loc_1802C6F43
0x1802c6f30  lea     rcx, [rbp+57h+var_50]
0x1802c6f34  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6f3a  mov     rcx, rax
0x1802c6f3d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802c6f43  mov     r9, rax; unsigned __int16 *
0x1802c6f46  mov     r8, rbx; unsigned __int16 *
0x1802c6f49  lea     rdx, aCsidlProgramFi_1; "CSIDL_PROGRAM_FILESX86"
0x1802c6f50  mov     rcx, rdi; this
0x1802c6f53  call    ?pAddToEnv@@YAXPEAVCBasicEnv@Mig@@PEBG11@Z; pAddToEnv(Mig::CBasicEnv *,ushort const *,ushort const *,ushort const *)
0x1802c6f58  call    cs:__imp_GetProcessHeap
0x1802c6f5e  mov     rcx, rax; hHeap
0x1802c6f61  mov     r8, rbx; lpMem
0x1802c6f64  xor     edx, edx; dwFlags
0x1802c6f66  call    cs:__imp_HeapFree
0x1802c6f6c  xor     r9d, r9d
0x1802c6f6f  lea     r8, aProgramfilesdi; "ProgramFilesDir (Arm)"
0x1802c6f76  mov     rdx, rsi
0x1802c6f79  mov     rcx, [rbp+57h+hKey]
0x1802c6f7d  call    RegGetStringEx
0x1802c6f82  mov     rbx, rax
0x1802c6f85  test    rax, rax
0x1802c6f88  jz      loc_1802C7010
0x1802c6f8e  lea     rcx, [rbp+57h+var_50]
0x1802c6f92  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802c6f98  test    rax, rax
0x1802c6f9b  jz      short loc_1802C6FB0
0x1802c6f9d  lea     rcx, [rbp+57h+var_50]
0x1802c6fa1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802c6fa7  mov     rcx, rax
0x1802c6faa  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
  ... truncated ...
```
