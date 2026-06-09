# CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)

- ea: `0x1800c6274`
- end: `0x1800c7df6`
- name: `?Finalize@CDeploymentBase@@QEAA?AW4SYSTEM_STATE@SetupPlatform@@PEAUIOperationsProgress@3@H@Z`
- size: `7042`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c7e10`
- `0x1800c8be0`

## callees

- `0x18001413d`
- `0x180044810`
- `0x180057dec`
- `0x1800a2e40`
- `0x1800c6158`
- `0x1800c6274`
- `0x180114ff8`
- `0x1802d6738`
- `0x1802d68d4`
- `0x1802e6604`
- `0x18034e330`
- `0x180352b00`
- `0x180354338`
- `0x180371248`
- `0x180372ba4`
- `0x180380350`
- `0x1804bbf46`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800c6ca6`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6cb5`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6ca6`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6cb5`
- `KERNEL32!GetLastError` at `0x1800c62e5`
- `KERNEL32!GetLastError` at `0x1800c6380`
- `KERNEL32!GetLastError` at `0x1800c6507`
- `KERNEL32!GetLastError` at `0x1800c65a4`
- `KERNEL32!GetLastError` at `0x1800c6761`
- `KERNEL32!GetLastError` at `0x1800c6857`
- `KERNEL32!GetLastError` at `0x1800c695a`
- `KERNEL32!GetLastError` at `0x1800c6a53`
- `KERNEL32!GetLastError` at `0x1800c6b29`
- `KERNEL32!GetLastError` at `0x1800c6b3f`
- `KERNEL32!GetLastError` at `0x1800c6b64`
- `KERNEL32!GetLastError` at `0x1800c6d5b`
- `KERNEL32!GetLastError` at `0x1800c6def`
- `KERNEL32!GetLastError` at `0x1800c6e55`
- `KERNEL32!GetLastError` at `0x1800c6ec0`
- `KERNEL32!GetLastError` at `0x1800c6f60`
- `KERNEL32!GetLastError` at `0x1800c7007`
- `KERNEL32!GetLastError` at `0x1800c70ae`
- `KERNEL32!GetLastError` at `0x1800c7161`
- `KERNEL32!GetLastError` at `0x1800c7219`
- `KERNEL32!GetLastError` at `0x1800c72d1`
- `KERNEL32!GetLastError` at `0x1800c737e`
- `KERNEL32!GetLastError` at `0x1800c7424`
- `KERNEL32!GetLastError` at `0x1800c7578`
- `KERNEL32!GetLastError` at `0x1800c7589`
- `KERNEL32!GetLastError` at `0x1800c7684`
- `KERNEL32!GetLastError` at `0x1800c7695`
- `KERNEL32!GetLastError` at `0x1800c7817`
- `KERNEL32!GetLastError` at `0x1800c7969`
- `KERNEL32!GetLastError` at `0x1800c7981`
- `KERNEL32!GetLastError` at `0x1800c7a29`
- `KERNEL32!GetLastError` at `0x1800c7a41`
- `KERNEL32!GetLastError` at `0x1800c7c86`
- `KERNEL32!GetLastError` at `0x1800c7d07`
- `KERNEL32!GetLastError` at `0x1800c7d18`
- `KERNEL32!GetLastError` at `0x1800c62e5`
- `KERNEL32!GetLastError` at `0x1800c6380`
- `KERNEL32!GetLastError` at `0x1800c6507`
- `KERNEL32!GetLastError` at `0x1800c65a4`
- `KERNEL32!GetLastError` at `0x1800c6761`
- `KERNEL32!GetLastError` at `0x1800c6857`
- `KERNEL32!GetLastError` at `0x1800c695a`
- `KERNEL32!GetLastError` at `0x1800c6a53`
- `KERNEL32!GetLastError` at `0x1800c6b29`
- `KERNEL32!GetLastError` at `0x1800c6b3f`
- `KERNEL32!GetLastError` at `0x1800c6b64`
- `KERNEL32!GetLastError` at `0x1800c6d5b`
- `KERNEL32!GetLastError` at `0x1800c6def`
- `KERNEL32!GetLastError` at `0x1800c6e55`
- `KERNEL32!GetLastError` at `0x1800c6ec0`
- `KERNEL32!GetLastError` at `0x1800c6f60`
- `KERNEL32!GetLastError` at `0x1800c7007`
- `KERNEL32!GetLastError` at `0x1800c70ae`
- `KERNEL32!GetLastError` at `0x1800c7161`
- `KERNEL32!GetLastError` at `0x1800c7219`
- `KERNEL32!GetLastError` at `0x1800c72d1`
- `KERNEL32!GetLastError` at `0x1800c737e`
- `KERNEL32!GetLastError` at `0x1800c7424`
- `KERNEL32!GetLastError` at `0x1800c7578`
- `KERNEL32!GetLastError` at `0x1800c7589`
- `KERNEL32!GetLastError` at `0x1800c7684`
- `KERNEL32!GetLastError` at `0x1800c7695`
- `KERNEL32!GetLastError` at `0x1800c7817`
- `KERNEL32!GetLastError` at `0x1800c7969`
- `KERNEL32!GetLastError` at `0x1800c7981`
- `KERNEL32!GetLastError` at `0x1800c7a29`
- `KERNEL32!GetLastError` at `0x1800c7a41`
- `KERNEL32!GetLastError` at `0x1800c7c86`
- `KERNEL32!GetLastError` at `0x1800c7d07`
- `KERNEL32!GetLastError` at `0x1800c7d18`
- `KERNEL32!SetLastError` at `0x1800c6cd2`
- `KERNEL32!SetLastError` at `0x1800c6cd2`
- `KERNEL32!EnterCriticalSection` at `0x1800c64ad`
- `KERNEL32!EnterCriticalSection` at `0x1800c64ad`
- `KERNEL32!GetSystemPowerStatus` at `0x1800c7bdd`
- `KERNEL32!GetSystemPowerStatus` at `0x1800c7bdd`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800c772c`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800c78f5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800c772c`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800c78f5`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800c6410`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800c645b`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800c6410`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800c645b`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1800c64c3`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1800c64c3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800c6a2d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800c751a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800c78c0`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800c6a2d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800c751a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800c78c0`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800c6c8d`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800c6c8d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800c6a21`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800c7509`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800c78af`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800c6a21`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800c7509`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800c78af`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c6420`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c646b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c6a4d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c753a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c78e0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c6420`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c646b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c6a4d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c753a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800c78e0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c6404`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c644f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c6a11`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c74f4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c789a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c6404`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c644f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c6a11`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c74f4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800c789a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6619`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6ad2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6af4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6c0d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6c48`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7548`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c775d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c77a9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c77d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7915`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7934`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7996`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7a55`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7da1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6619`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6ad2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6af4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6c0d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c6c48`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7548`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c775d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c77a9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c77d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7915`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7934`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7996`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7a55`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800c7da1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6622`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6adb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6afd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6c16`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6c51`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7551`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c765d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7766`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c77b2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c77e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c791e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c793d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c799f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7a5e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7b3a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7b60`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7b82`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7daa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6622`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6adb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6afd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6c16`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c6c51`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7551`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c765d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7766`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c77b2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c77e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c791e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c793d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c799f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7a5e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7b3a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7b60`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7b82`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800c7daa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c771d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7a0f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7a1e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7baa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7dc4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c771d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7a0f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7a1e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7baa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800c7dc4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800c6a3e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800c752b`

## string_xrefs

- `0x1800c6335`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c63c2`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6547`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c65ec`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c67a9`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c68a1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c69a4`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6a9a`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6bb0`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6da0`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6e2f`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6e9a`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6f01`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c6fa5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c704c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c70f3`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c71a1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c7259`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c7311`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c73ca`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c7470`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c75c1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c76cd`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c785c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c7cf1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c7d50`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800c7704`: `SP_INSTALL_INFO`
- `0x1800c7792`: `SP_INSTALL_INFO`
- `0x1800c7592`: `Failed to save shutdown requirement to setplatform config file. Error = %d`
- `0x1800c7561`: `ShutdownAfterInstallation`
- `0x1800c766d`: `PostRollbackShutdown`
- `0x1800c769e`: `Failed to save shutdown requirement to rollback config file. Error = %d`
- `0x1800c782d`: `Failed to add working directory size and free space; SQM data will not be reliable. hr = 0x%08X`
- `0x1800c7a6f`: `Failed to get size of working directory %s; SQM data will not be reliable. Error = %d`
- `0x1800c7cc2`: `Battery Information - LifePercent: %d, LifeTime: %d, ACLineStatus: %d, BatteryFlag: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=2
__int64 __fastcall CDeploymentBase::Finalize(unsigned __int64 a1, __int64 a2, int a3)
{
  unsigned int v4; // eax
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD LastError; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  const struct UnBCL::String *v12; // rax
  const struct UnBCL::String *v13; // rax
  int IsEnvironmentVarSetTrue; // ebx
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  UnBCL::String *v21; // rax
  const unsigned __int16 *CString; // rax
  unsigned __int64 v23; // rax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  const struct UnBCL::String *v33; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v35; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  UnBCL::String *v39; // rax
  UnBCL::String *v40; // rax
  const unsigned __int16 *v41; // rax
  signed int v42; // eax
  bool v43; // sf
  signed int v44; // eax
  unsigned int v45; // eax
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  UnBCL::String *v49; // rax
  const unsigned __int16 *v50; // rax
  UnBCL::String *v51; // rax
  const unsigned __int16 *v52; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  DWORD v59; // edi
  __int64 v60; // rbx
  struct tagLOG_PARTIAL_MSG *v61; // rax
  DWORD v62; // edi
  __int64 v63; // rbx
  struct tagLOG_PARTIAL_MSG *v64; // rax
  DWORD v65; // edi
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  DWORD v68; // edi
  __int64 v69; // rbx
  struct tagLOG_PARTIAL_MSG *v70; // rax
  DWORD v71; // edi
  __int64 v72; // rbx
  struct tagLOG_PARTIAL_MSG *v73; // rax
  DWORD v74; // edi
  __int64 v75; // rbx
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
  struct tagLOG_PARTIAL_MSG *v88; // rax
  const struct UnBCL::String *v89; // rax
  struct UnBCL::String *v90; // rax
  UnBCL::String *v91; // rax
  const unsigned __int16 *v92; // rax
  DWORD v93; // edi
  __int64 v94; // rbx
  DWORD v95; // eax
  struct tagLOG_PARTIAL_MSG *v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  UnBCL::String *v99; // rax
  const unsigned __int16 *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  DWORD v103; // eax
  struct tagLOG_PARTIAL_MSG *v104; // rax
  struct UnBCL::String *v105; // rax
  UnBCL::String *v106; // rax
  const unsigned __int16 *v107; // rax
  UnBCL::String *v108; // rax
  const WCHAR *v109; // rax
  UnBCL::String *v110; // rax
  const unsigned __int16 *v111; // rax
  DWORD v112; // edi
  __int64 v113; // rbx
  struct tagLOG_PARTIAL_MSG *v114; // rax
  const struct UnBCL::String *v115; // rax
  struct UnBCL::String *v116; // rax
  struct UnBCL::String *v117; // rax
  UnBCL::String *v118; // rax
  UnBCL::String *v119; // rax
  const unsigned __int16 *v120; // rax
  UnBCL::String *v121; // rax
  const char *v122; // rax
  struct tagLOG_PARTIAL_MSG *v123; // rax
  UnBCL::String *v124; // rax
  const char *v125; // rax
  struct tagLOG_PARTIAL_MSG *v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  UnBCL::String *v129; // rbx
  const unsigned __int16 *v130; // rax
  const unsigned __int16 *v131; // rax
  const unsigned __int16 *v132; // rax
  __int64 v133; // rcx
  DWORD v134; // edi
  __int64 v135; // rbx
  struct tagLOG_PARTIAL_MSG *v136; // rax
  DWORD v137; // edi
  __int64 v138; // rbx
  DWORD v139; // eax
  struct tagLOG_PARTIAL_MSG *v140; // rax
  __int64 v141; // rax
  CDiagnosticsHelper *v142; // rbx
  UnBCL::String *v143; // rax
  const unsigned __int16 *v144; // rax
  NTSTATUS Status; // [rsp+60h] [rbp-1A8h]
  unsigned int v146; // [rsp+6Ch] [rbp-19Ch]
  unsigned int v147; // [rsp+6Ch] [rbp-19Ch]
  __int64 v148; // [rsp+70h] [rbp-198h] BYREF
  unsigned int v149; // [rsp+78h] [rbp-190h] BYREF
  unsigned int v150; // [rsp+7Ch] [rbp-18Ch]
  int v151; // [rsp+80h] [rbp-188h]
  int v152; // [rsp+84h] [rbp-184h]
  unsigned __int16 v153[4]; // [rsp+88h] [rbp-180h] BYREF
  __int64 v154[2]; // [rsp+90h] [rbp-178h] BYREF
  unsigned __int64 v155[3]; // [rsp+A0h] [rbp-168h] BYREF
  _BYTE v156[24]; // [rsp+B8h] [rbp-150h] BYREF
  _QWORD v157[7]; // [rsp+D0h] [rbp-138h] BYREF
  _QWORD *pExceptionObject; // [rsp+108h] [rbp-100h] BYREF
  _QWORD *v159; // [rsp+110h] [rbp-F8h] BYREF
  _QWORD *v160; // [rsp+118h] [rbp-F0h] BYREF
  _QWORD *v161; // [rsp+120h] [rbp-E8h] BYREF
  _QWORD *v162; // [rsp+128h] [rbp-E0h] BYREF
  _QWORD *v163; // [rsp+130h] [rbp-D8h] BYREF
  _QWORD *v164; // [rsp+138h] [rbp-D0h] BYREF
  _QWORD *v165; // [rsp+140h] [rbp-C8h] BYREF
  _QWORD *v166; // [rsp+148h] [rbp-C0h] BYREF
  _QWORD *v167; // [rsp+150h] [rbp-B8h] BYREF
  _QWORD *v168; // [rsp+158h] [rbp-B0h] BYREF
  _QWORD *v169; // [rsp+160h] [rbp-A8h] BYREF
  _BYTE v170[24]; // [rsp+168h] [rbp-A0h] BYREF
  _BYTE v171[16]; // [rsp+180h] [rbp-88h] BYREF
  __int64 v172; // [rsp+190h] [rbp-78h]
  _BYTE v173[24]; // [rsp+198h] [rbp-70h] BYREF
  _BYTE v174[24]; // [rsp+1B0h] [rbp-58h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+1C8h] [rbp-40h] BYREF

  v172 = -2;
  LODWORD(v155[0]) = a3;
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = a2;
  v155[2] = a1;
  v4 = *(_DWORD *)(a1 + 460);
  if ( v4 <= 1 || v4 - 6 <= 1 )
  {
    CDeploymentBase::ExitReadOnlyMode((CDeploymentBase *)a1);
    if ( *(_DWORD *)(a1 + 460) != 7 )
    {
      LastError = GetLastError();
      v10 = CurrentIP();
      v11 = ConstructPartialMsgW(0x4000000u, "Last execute detected, Will check for simulated operations");
      WdsSetupLogMessageW(
        v11,
        819200,
        L"D",
        0,
        2547,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::Finalize",
        v10,
        LastError,
        0,
        0);
      v12 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v156, L"SP_ENV_ADD_SIMULATED_OPS_UPG");
      LODWORD(v10) = UnBCL::Environment::IsEnvironmentVarSetTrue(v12, 0);
      UnBCL::String::~String((UnBCL::String *)v156);
      if ( (_DWORD)v10 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 496) + 24LL))(*(_QWORD *)(a1 + 496), 1);
      v13 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v156, L"SP_ENV_ADD_SIMULATED_OPS_PBR");
      IsEnvironmentVarSetTrue = UnBCL::Environment::IsEnvironmentVarSetTrue(v13, 0);
      UnBCL::String::~String((UnBCL::String *)v156);
      if ( IsEnvironmentVarSetTrue )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 496) + 24LL))(*(_QWORD *)(a1 + 496), 2);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    UnBCL::Exception::Exception((UnBCL::Exception *)v157);
    v157[0] = &`CDeploymentBase::Finalize'::`15'::CXXXXXHandledException::`vftable';
    if ( !*(_DWORD *)(a1 + 452) && (*(int (__fastcall **)(unsigned __int64))(*(_QWORD *)a1 + 152LL))(a1) < 0 )
    {
      *(_DWORD *)(a1 + 460) = 4;
      pExceptionObject = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&pExceptionObject;
    }
    v154[0] = 0;
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(0x4000000u, "DISKSPACEQUERY: Calculating disk space needed:");
    WdsSetupLogMessageW(
      v17,
      819200,
      L"D",
      0,
      2581,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::Finalize",
      v16,
      v15,
      0,
      0);
    LODWORD(v148) = COperationQueue::GetDiskSpaceNeeded(
                      *(COperationQueue **)(a1 + 496),
                      (struct IExecutionContext *)a1,
                      v154,
                      &v148,
                      *(_DWORD *)(a1 + 528));
    if ( (int)v148 < 0 )
    {
      v53 = GetLastError();
      v54 = CurrentIP();
      v55 = ConstructPartialMsgW(0x2000000u, "DISKSPACEQUERY: Calculating disk space failed. Error: 0x%08X", v148);
      WdsSetupLogMessageW(
        v55,
        819200,
        L"D",
        0,
        2590,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::Finalize",
        v54,
        v53,
        0,
        0);
      v168 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v168;
    }
    v18 = GetLastError();
    v19 = CurrentIP();
    v20 = ConstructPartialMsgW(0x4000000u, "DISKSPACEQUERY: Final disk space needed estimate: %I64d", v154[0]);
    WdsSetupLogMessageW(
      v20,
      819200,
      L"D",
      0,
      2593,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::Finalize",
      v19,
      v18,
      0,
      0);
    v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 152);
    CString = UnBCL::String::get_CString(v21);
    v23 = SPGetFreeDiskSpace(CString);
    if ( v23 < v154[0] )
    {
      v148 = v23 + 104857600;
      if ( v23 + 104857600 < v154[0] )
      {
        v56 = GetLastError();
        v57 = CurrentIP();
        v58 = ConstructPartialMsgW(0x3000000u, "Not enough disk space for the next set of operations.");
        WdsSetupLogMessageW(
          v58,
          819200,
          L"D",
          0,
          2606,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v57,
          v56,
          0,
          0);
        v59 = GetLastError();
        v60 = CurrentIP();
        v61 = ConstructPartialMsgW(0x3000000u, "Disk space available: %I64u", v148 - 104857600);
        WdsSetupLogMessageW(
          v61,
          819200,
          L"D",
          0,
          2607,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v60,
          v59,
          0,
          0);
        v62 = GetLastError();
        v63 = CurrentIP();
        v64 = ConstructPartialMsgW(0x3000000u, "Disk space needed   : %I64d", v154[0]);
        WdsSetupLogMessageW(
          v64,
          819200,
          L"D",
          0,
          2608,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v63,
          v62,
          0,
          0);
        v169 = v157;
        throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v169;
      }
    }
    *(_DWORD *)(a1 + 460) = 1;
    v149 = 0;
    v152 = 0;
    LODWORD(v154[0]) = 0;
    v151 = 0;
    LODWORD(v148) = COperationQueue::ValidateOperationsForPhase(
                      *(_QWORD *)(a1 + 496),
                      1,
                      a1,
                      *(unsigned int *)(a1 + 528),
                      &v149);
    if ( (int)v148 < 0 )
    {
      v65 = GetLastError();
      v66 = CurrentIP();
      v67 = ConstructPartialMsgW(0x2000000u, "Downlevel operations are not valid. Error: 0x%08X", v148);
      WdsSetupLogMessageW(
        v67,
        819200,
        L"D",
        0,
        2625,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::Finalize",
        v66,
        v65,
        0,
        0);
      *(_DWORD *)(a1 + 460) = 4;
      v159 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v159;
    }
    LODWORD(v148) = COperationQueue::ValidateOperationsForPhase(
                      *(_QWORD *)(a1 + 496),
                      2,
                      a1,
                      *(unsigned int *)(a1 + 528),
                      v154);
    if ( (int)v148 < 0 )
    {
      v68 = GetLastError();
      v69 = CurrentIP();
      v70 = ConstructPartialMsgW(0x2000000u, "Pre-finalize operations are not valid. Error: 0x%08X", v148);
      WdsSetupLogMessageW(
        v70,
        819200,
        L"D",
        0,
        2633,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::Finalize",
        v69,
        v68,
        0,
        0);
      *(_DWORD *)(a1 + 460) = 4;
      v160 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v160;
    }
    LODWORD(v148) = COperationQueue::ValidateOperationsForPhase(
                      *(_QWORD *)(a1 + 496),
                      3,
                      a1,
                      *(unsigned int *)(a1 + 528),
                      0);
    if ( (int)v148 < 0 )
    {
      v71 = GetLastError();
      v72 = CurrentIP();
      v73 = ConstructPartialMsgW(0x2000000u, "Finalize operations are not valid. Error: 0x%08X", v148);
      WdsSetupLogMessageW(
        v73,
        819200,
        L"D",
        0,
        2641,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::Finalize",
        v72,
        v71,
        0,
        0);
      *(_DWORD *)(a1 + 460) = 4;
      v161 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v161;
    }
    LODWORD(v148) = v152 + v151;
    if ( v152 + v151 )
      v150 = 100 * v152 / (unsigned int)(v152 + v151);
    else
      v150 = 0;
    v24 = GetLastError();
    v25 = CurrentIP();
    v26 = ConstructPartialMsgW(0x4000000u, "VERBOSE: Percents for downlevel: %d%% -> %d%%", 0, v150);
    WdsSetupLogMessageW(
      v26,
      819200,
      L"D",
      0,
      2652,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::Finalize",
      v25,
      v24,
      0,
      0);
    if ( v149 )
    {
      if ( *(_QWORD *)&SystemPowerStatus.ACLineStatus )
        (***(void (__fastcall ****)(_QWORD, __int64, _QWORD, _QWORD))&SystemPowerStatus.ACLineStatus)(
          *(_QWORD *)&SystemPowerStatus.ACLineStatus,
          1,
          0,
          v150);
    }
    else if ( (*(int (__fastcall **)(unsigned __int64, __int64, _QWORD, _QWORD, unsigned int))(*(_QWORD *)a1 + 160LL))(
                a1,
                1,
                *(_QWORD *)&SystemPowerStatus.ACLineStatus,
                0,
                v150) < 0 )
    {
      if ( *(_DWORD *)(a1 + 460) == 5 )
      {
        v74 = GetLastError();
        v75 = CurrentIP();
        v76 = ConstructPartialMsgW(0x3000000u, "Out of disk space while executing operations.");
        WdsSetupLogMessageW(
          v76,
          819200,
          L"D",
          0,
          2660,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v75,
          v74,
          0,
          0);
        *(_DWORD *)(a1 + 460) = 1;
      }
      v162 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v162;
    }
    if ( (_DWORD)v148 )
      v149 = 100 * (v151 + v152) / (unsigned int)v148;
    else
      v149 = 0;
    v27 = GetLastError();
    v28 = CurrentIP();
    v29 = ConstructPartialMsgW(0x4000000u, "VERBOSE: Percents for pre-finalize: %d%% -> %d%%", v150, v149);
    WdsSetupLogMessageW(
      v29,
      819200,
      L"D",
      0,
      2683,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::Finalize",
      v28,
      v27,
      0,
      0);
    if ( LODWORD(v154[0]) )
    {
      if ( *(_QWORD *)&SystemPowerStatus.ACLineStatus )
        (***(void (__fastcall ****)(_QWORD, __int64, _QWORD, _QWORD))&SystemPowerStatus.ACLineStatus)(
          *(_QWORD *)&SystemPowerStatus.ACLineStatus,
          1,
          0,
          v149);
    }
    else if ( (*(int (__fastcall **)(unsigned __int64, __int64, _QWORD, _QWORD, unsigned int))(*(_QWORD *)a1 + 160LL))(
                a1,
                2,
                *(_QWORD *)&SystemPowerStatus.ACLineStatus,
                v150,
                v149) < 0 )
    {
      if ( *(_DWORD *)(a1 + 460) == 5 )
      {
        v77 = GetLastError();
        v78 = CurrentIP();
        v79 = ConstructPartialMsgW(0x3000000u, "Out of disk space while executing operations.");
        WdsSetupLogMessageW(
          v79,
          819200,
          L"D",
          0,
          2691,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v78,
          v77,
          0,
          0);
        *(_DWORD *)(a1 + 460) = 1;
      }
      v163 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v163;
    }
    if ( (_DWORD)v148 )
      v146 = 100 * (v152 + v151) / (unsigned int)v148;
    else
      v146 = 0;
    v30 = GetLastError();
    v31 = CurrentIP();
    v32 = ConstructPartialMsgW(0x4000000u, "VERBOSE: Percents for finalize: %d%% -> %d%%", v149, v146);
    WdsSetupLogMessageW(
      v32,
      819200,
      L"D",
      0,
      2714,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::Finalize",
      v31,
      v30,
      0,
      0);
    if ( (*(int (__fastcall **)(unsigned __int64, __int64, _QWORD, _QWORD, unsigned int))(*(_QWORD *)a1 + 160LL))(
           a1,
           3,
           *(_QWORD *)&SystemPowerStatus.ACLineStatus,
           v149,
           v146) < 0 )
    {
      if ( *(_DWORD *)(a1 + 460) == 5 )
      {
        v80 = GetLastError();
        v81 = CurrentIP();
        v82 = ConstructPartialMsgW(0x3000000u, "Out of disk space while executing operations.");
        WdsSetupLogMessageW(
          v82,
          819200,
          L"D",
          0,
          2720,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v81,
          v80,
          0,
          0);
        *(_DWORD *)(a1 + 460) = 1;
      }
      v164 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v164;
    }
    v33 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v173, L"SetupPlatform.ini");
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(a1 + 152);
    v35 = UnBCL::Path::Combine(P, v33);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v156, v35);
    UnBCL::String::~String((UnBCL::String *)v173);
    v36 = GetLastError();
    v37 = CurrentIP();
    v38 = ConstructPartialMsgW(0x4000000u, "%hs: Serializing operations queue...", "CDeploymentBase::Finalize");
    WdsSetupLogMessageW(
      v38,
      819200,
      L"D",
      0,
      2739,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::Finalize",
      v37,
      v36,
      0,
      0);
    *(_DWORD *)v153 = 63;
    v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 152);
    v153[0] = *UnBCL::String::get_CString(v39);
    v40 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v156);
    v41 = UnBCL::String::get_CString(v40);
    if ( SPWriteConfigValue(L"Parameters", L"SourceDirDriveLetter", v153, v41) )
    {
      v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 152);
      v52 = UnBCL::String::get_CString(v51);
      LODWORD(v148) = SPSerializeOperations(*(_QWORD *)(a1 + 496), *(_QWORD *)(a1 + 480), v52, 0);
      if ( (int)v148 < 0 )
      {
        v86 = GetLastError();
        v87 = CurrentIP();
        v88 = ConstructPartialMsgW(
                0x2000000u,
                "%hs: Failed to serialize operations queue. Error: 0x%08X",
                "CDeploymentBase::Finalize",
                v148);
        WdsSetupLogMessageW(
          v88,
          819200,
          L"D",
          0,
          2753,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v87,
          v86,
          0,
          0);
        *(_DWORD *)(a1 + 460) = 4;
        v165 = v157;
        throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v165;
      }
LABEL_46:
      *(_QWORD *)&SystemPowerStatus.ACLineStatus = _RTDynamicCast_0(
                                                     *(_QWORD *)(a1 + 96),
                                                     0,
                                                     &ITelemetry `RTTI Type Descriptor',
                                                     &CTelemetry `RTTI Type Descriptor',
                                                     0);
      v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 152);
      v50 = UnBCL::String::get_CString(v49);
      LODWORD(v148) = SPSerializeTelemetry(*(struct CTelemetry **)&SystemPowerStatus.ACLineStatus, v50);
      if ( (int)v148 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 460) == 8 )
        {
          if ( LODWORD(v155[0]) )
          {
            *(_QWORD *)&SystemPowerStatus.ACLineStatus = UnBCL::String::String(
                                                           (UnBCL::String *)v170,
                                                           L"SetupPlatform.ini");
            v89 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(a1 + 152);
            v90 = UnBCL::Path::Combine(v89, *(const struct UnBCL::String **)&SystemPowerStatus.ACLineStatus);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v155, v90);
            UnBCL::String::~String((UnBCL::String *)v170);
            v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v155);
            v92 = UnBCL::String::get_CString(v91);
            if ( !SPWriteConfigValue(L"Parameters", L"ShutdownAfterInstallation", L"TRUE", v92) )
            {
              v93 = GetLastError();
              v94 = CurrentIP();
              v95 = GetLastError();
              v96 = ConstructPartialMsgW(
                      0x3000000u,
                      "Failed to save shutdown requirement to setplatform config file. Error = %d",
                      v95);
              WdsSetupLogMessageW(
                v96,
                819200,
                L"D",
                0,
                2779,
                L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                L"CDeploymentBase::Finalize",
                v94,
                v93,
                0,
                0);
            }
            if ( (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(a1 + 296) + 24LL))(a1 + 296) )
            {
              v97 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(a1 + 296) + 8LL))(a1 + 296);
              if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 56LL))(v97) )
              {
                v98 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(a1 + 296) + 8LL))(a1 + 296);
                v99 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v98 + 56LL))(v98);
                v100 = UnBCL::String::get_CString(v99);
                if ( !SPWriteConfigValue(L"Flow", L"PostRollbackShutdown", L"TRUE", v100) )
                {
                  v101 = GetLastError();
                  v102 = CurrentIP();
                  v103 = GetLastError();
                  v104 = ConstructPartialMsgW(
                           0x3000000u,
                           "Failed to save shutdown requirement to rollback config file. Error = %d",
                           v103);
                  WdsSetupLogMessageW(
                    v104,
                    819200,
                    L"D",
                    0,
                    2787,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                    L"CDeploymentBase::Finalize",
                    v102,
                    v101,
                    0,
                    0);
                }
              }
            }
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**(_QWORD **)(a1 + 96) + 24LL))(
              *(_QWORD *)(a1 + 96),
              L"SP_INSTALL_INFO",
              L"ShutdownRequested",
              1);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v155);
          }
          v105 = UnBCL::String::Format(L"%d", 0);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v171, v105);
          *(_QWORD *)&SystemPowerStatus.ACLineStatus = RAII::CAutoCleanupBase<void *>::operator->(a1 + 104);
          v106 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v171);
          v107 = UnBCL::String::get_CString(v106);
          CDiagnosticsHelper::SetWatsonBucketingParam(*(CDiagnosticsHelper **)&SystemPowerStatus.ACLineStatus, 3u, v107);
          (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(**(_QWORD **)(a1 + 96) + 24LL))(
            *(_QWORD *)(a1 + 96),
            L"SP_INSTALL_INFO",
            L"OverallResult",
            0);
          v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 168);
          v109 = UnBCL::String::get_CString(v108);
          v155[0] = SPGetFileSize(v109);
          if ( v155[0] )
          {
            v110 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 152);
            v111 = UnBCL::String::get_CString(v110);
            *(_QWORD *)&SystemPowerStatus.ACLineStatus = SPGetFreeDiskSpace(v111);
            Status = ULongLongAdd(
                       *(unsigned __int64 *)&SystemPowerStatus.ACLineStatus,
                       v155[0],
                       (unsigned __int64 *)&SystemPowerStatus.ACLineStatus);
            if ( Status >= 0 )
            {
              v155[0] = UnBCL::String::String((UnBCL::String *)v174, L"SetupPlatform.ini");
              v115 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(a1 + 152);
              v116 = UnBCL::Path::Combine(v115, (const struct UnBCL::String *)v155[0]);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v170, v116);
              UnBCL::String::~String((UnBCL::String *)v174);
              v117 = UnBCL::String::Format(L"%I64u", *(_QWORD *)&SystemPowerStatus.ACLineStatus);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v154, v117);
              v118 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v170);
              *(_QWORD *)&SystemPowerStatus.ACLineStatus = UnBCL::String::get_CString(v118);
              v119 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v154);
              v120 = UnBCL::String::get_CString(v119);
              if ( !SPWriteConfigValue(
                      L"Diagnostics",
                      L"AvailableFreeSpace",
                      v120,
                      *(const unsigned __int16 **)&SystemPowerStatus.ACLineStatus) )
              {
                LODWORD(v148) = GetLastError();
                *(_QWORD *)&SystemPowerStatus.ACLineStatus = CurrentIP();
                LODWORD(v155[0]) = GetLastError();
                v121 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v154);
                v122 = (const char *)UnBCL::String::get_CString(v121);
                v123 = ConstructPartialMsgW(
                         0x3000000u,
                         "Failed to save available free space info to file: %s. Error = %d",
                         v122,
                         LODWORD(v155[0]));
                WdsSetupLogMessageW(
                  v123,
                  819200,
                  L"D",
                  0,
                  2821,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                  L"CDeploymentBase::Finalize",
                  *(_QWORD *)&SystemPowerStatus.ACLineStatus,
                  v148,
                  0,
                  0);
              }
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v154);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
            }
            else
            {
              v112 = GetLastError();
              v113 = CurrentIP();
              v114 = ConstructPartialMsgW(
                       0x3000000u,
                       "Failed to add working directory size and free space; SQM data will not be reliable. hr = 0x%08X",
                       Status);
              WdsSetupLogMessageW(
                v114,
                819200,
                L"D",
                0,
                2810,
                L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                L"CDeploymentBase::Finalize",
                v113,
                v112,
                0,
                0);
            }
          }
          else
          {
            LODWORD(v148) = GetLastError();
            *(_QWORD *)&SystemPowerStatus.ACLineStatus = CurrentIP();
            LODWORD(v155[0]) = GetLastError();
            v124 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 184);
            v125 = (const char *)UnBCL::String::get_CString(v124);
            v126 = ConstructPartialMsgW(
                     0x3000000u,
                     "Failed to get size of working directory %s; SQM data will not be reliable. Error = %d",
                     v125,
                     LODWORD(v155[0]));
            WdsSetupLogMessageW(
              v126,
              819200,
              L"D",
              0,
              2829,
              L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
              L"CDeploymentBase::Finalize",
              *(_QWORD *)&SystemPowerStatus.ACLineStatus,
              v148,
              0,
              0);
          }
          if ( (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(a1 + 296) + 24LL))(a1 + 296) )
          {
            v127 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(a1 + 296) + 8LL))(a1 + 296);
            if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v127 + 56LL))(v127) )
            {
              v128 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(a1 + 296) + 8LL))(a1 + 296);
              v129 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v128 + 56LL))(v128);
              v130 = UnBCL::String::get_CString(v129);
              SPWriteConfigValue(L"Flow", L"CurrentPhase", L"Downlevel,End", v130);
              v131 = UnBCL::String::get_CString(v129);
              SPWriteConfigValue(L"Flow", L"CurrentOperation", 0, v131);
              v132 = UnBCL::String::get_CString(v129);
              SPWriteConfigValue(L"Flow", L"OperationResult", 0, v132);
            }
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v171);
        }
        if ( *(_DWORD *)(a1 + 460) == 8 )
        {
          *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
          SystemPowerStatus.BatteryFullLifeTime = 0;
          if ( GetSystemPowerStatus(&SystemPowerStatus) )
          {
            v133 = *(_QWORD *)(a1 + 96);
            if ( v133 )
            {
              (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v133 + 24LL))(
                v133,
                L"SP_BATTERY_INFO",
                L"BatteryChargePercent",
                SystemPowerStatus.BatteryLifePercent);
              (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(**(_QWORD **)(a1 + 96) + 24LL))(
                *(_QWORD *)(a1 + 96),
                L"SP_BATTERY_INFO",
                L"BatteryTimeRemaining",
                SystemPowerStatus.BatteryLifeTime);
              (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(**(_QWORD **)(a1 + 96) + 24LL))(
                *(_QWORD *)(a1 + 96),
                L"SP_BATTERY_INFO",
                L"BatteryIsOnAC",
                SystemPowerStatus.ACLineStatus);
              (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(**(_QWORD **)(a1 + 96) + 24LL))(
                *(_QWORD *)(a1 + 96),
                L"SP_BATTERY_INFO",
                L"BatteryIsCritical",
                SystemPowerStatus.BatteryFlag);
            }
            v134 = GetLastError();
            v135 = CurrentIP();
            v136 = ConstructPartialMsgW(
                     0x4000000u,
                     "Battery Information - LifePercent: %d, LifeTime: %d, ACLineStatus: %d, BatteryFlag: %d",
                     SystemPowerStatus.BatteryLifePercent,
                     SystemPowerStatus.BatteryLifeTime,
                     SystemPowerStatus.ACLineStatus,
                     SystemPowerStatus.BatteryFlag);
            WdsSetupLogMessageW(
              v136,
              819200,
              L"D",
              0,
              2878,
              L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
              L"CDeploymentBase::Finalize",
              v135,
              v134,
              0,
              0);
          }
          else
          {
            v137 = GetLastError();
            v138 = CurrentIP();
            v139 = GetLastError();
            v140 = ConstructPartialMsgW(0x3000000u, "Failed to get battery information. Error = %d", v139);
            WdsSetupLogMessageW(
              v140,
              819200,
              L"D",
              0,
              2882,
              L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
              L"CDeploymentBase::Finalize",
              v138,
              v137,
              0,
              0);
          }
        }
        v141 = RAII::CAutoCleanupBase<void *>::operator->(a1 + 104);
        UnBCL::Hashtable<CWIMBootHelper::CWIMEntryIndex *,UnBCL::DictionaryEntry<void *,void *> *>::set_AutoDeleteKey(
          v141,
          *(unsigned int *)(a1 + 448));
        v142 = (CDiagnosticsHelper *)RAII::CAutoCleanupBase<void *>::operator->(a1 + 104);
        v143 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 232);
        v144 = UnBCL::String::get_CString(v143);
        CDiagnosticsHelper::PersistDiagnosticsData(v142, v144);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v156);
        v167 = v157;
        throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v167;
      }
      v83 = GetLastError();
      v84 = CurrentIP();
      v85 = ConstructPartialMsgW(
              0x2000000u,
              "%hs: Failed to serialize Telemetry instance. Error: 0x%08X",
              "CDeploymentBase::Finalize",
              v148);
      WdsSetupLogMessageW(
        v85,
        819200,
        L"D",
        0,
        2765,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::Finalize",
        v84,
        v83,
        0,
        0);
      *(_DWORD *)(a1 + 460) = 4;
      v166 = v157;
      throw (`CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException **)&v166;
    }
    v42 = GetLastError();
    v43 = v42 < 0;
    if ( v42 > 0 )
      v43 = 1;
    if ( v43 )
    {
      v44 = GetLastError();
      v147 = v44;
      if ( v44 <= 0 )
      {
LABEL_45:
        v46 = GetLastError();
        v47 = CurrentIP();
        v48 = ConstructPartialMsgW(
                0x2000000u,
                "%hs: Failed to save source drive letter. Error: 0x%08X",
                "CDeploymentBase::Finalize",
                v147);
        WdsSetupLogMessageW(
          v48,
          819200,
          L"D",
          0,
          2745,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::Finalize",
          v47,
          v46,
          0,
          0);
        *(_DWORD *)(a1 + 460) = 4;
        goto LABEL_46;
      }
      v45 = (unsigned __int16)v44 | 0x80070000;
    }
    else
    {
      v45 = -2147467259;
    }
    v147 = v45;
    goto LABEL_45;
  }
  v5 = GetLastError();
  v6 = CurrentIP();
  v7 = ConstructPartialMsgW(
         0x3000000u,
         "%hs: System state does not allow for finalize operations to be executed. Current state is %d",
         "CDeploymentBase::Finalize",
         *(_DWORD *)(a1 + 460));
  WdsSetupLogMessageW(
    v7,
    819200,
    L"D",
    0,
    2536,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CDeploymentBase::Finalize",
    v6,
    v5,
    0,
    0);
  return *(unsigned int *)(a1 + 460);
}

```

## disassembly

```asm
0x1800c6274  mov     rax, rsp
0x1800c6277  push    rdi
0x1800c6278  push    r12
0x1800c627a  push    r13
0x1800c627c  push    r14
0x1800c627e  push    r15
0x1800c6280  sub     rsp, 1E0h
0x1800c6287  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x1800c628f  mov     [rax+18h], rbx
0x1800c6293  mov     [rax+20h], rsi
0x1800c6297  mov     rax, cs:__security_cookie
0x1800c629e  xor     rax, rsp
0x1800c62a1  mov     [rsp+208h+var_30], rax
0x1800c62a9  mov     dword ptr [rsp+208h+var_168], r8d
0x1800c62b1  mov     qword ptr [rsp+208h+SystemPowerStatus.ACLineStatus], rdx
0x1800c62b9  mov     r14, rcx
0x1800c62bc  mov     [rsp+208h+var_158], rcx
0x1800c62c4  mov     eax, [rcx+1CCh]
0x1800c62ca  mov     r15d, 1
0x1800c62d0  cmp     eax, r15d
0x1800c62d3  jbe     loc_1800C636D
0x1800c62d9  add     eax, 0FFFFFFFAh
0x1800c62dc  cmp     eax, r15d
0x1800c62df  jbe     loc_1800C636D
0x1800c62e5  call    cs:__imp_GetLastError
0x1800c62eb  mov     edi, eax
0x1800c62ed  call    cs:__imp_CurrentIP
0x1800c62f3  mov     rbx, rax
0x1800c62f6  mov     r9d, [r14+1CCh]
0x1800c62fd  lea     r8, aCdeploymentbas_20; "CDeploymentBase::Finalize"
0x1800c6304  lea     rdx, aHsSystemStateD_3; "%hs: System state does not allow for fi"...
0x1800c630b  mov     ecx, 3000000h; unsigned int
0x1800c6310  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800c6315  xor     esi, esi
0x1800c6317  mov     [rsp+208h+var_1B8], esi
0x1800c631b  mov     [rsp+208h+var_1C0], rsi
0x1800c6320  mov     [rsp+208h+var_1C8], edi
0x1800c6324  mov     [rsp+208h+var_1D0], rbx
0x1800c6329  lea     rcx, aCdeploymentbas_30; "CDeploymentBase::Finalize"
0x1800c6330  mov     [rsp+208h+var_1D8], rcx
0x1800c6335  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800c633c  mov     [rsp+208h+var_1E0], rcx
0x1800c6341  mov     [rsp+208h+var_1E8], 9E8h
0x1800c6349  xor     r9d, r9d
0x1800c634c  lea     r8, aD_0; "D"
0x1800c6353  mov     edx, 0C8000h
0x1800c6358  mov     rcx, rax
0x1800c635b  call    cs:__imp_WdsSetupLogMessageW
0x1800c6361  mov     eax, [r14+1CCh]
0x1800c6368  jmp     loc_1800C6CF2
0x1800c636d  call    ?ExitReadOnlyMode@CDeploymentBase@@QEAAXXZ; CDeploymentBase::ExitReadOnlyMode(void)
0x1800c6372  cmp     dword ptr [r14+1CCh], 7
0x1800c637a  jz      loc_1800C648F
0x1800c6380  call    cs:__imp_GetLastError
0x1800c6386  mov     edi, eax
0x1800c6388  call    cs:__imp_CurrentIP
0x1800c638e  mov     rbx, rax
0x1800c6391  lea     rdx, aLastExecuteDet; "Last execute detected, Will check for s"...
0x1800c6398  mov     ecx, 4000000h; unsigned int
0x1800c639d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800c63a2  xor     esi, esi
0x1800c63a4  mov     [rsp+208h+var_1B8], esi
0x1800c63a8  mov     [rsp+208h+var_1C0], rsi
0x1800c63ad  mov     [rsp+208h+var_1C8], edi
0x1800c63b1  mov     [rsp+208h+var_1D0], rbx
0x1800c63b6  lea     rdi, aCdeploymentbas_30; "CDeploymentBase::Finalize"
0x1800c63bd  mov     [rsp+208h+var_1D8], rdi
0x1800c63c2  lea     rdi, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800c63c9  mov     [rsp+208h+var_1E0], rdi
0x1800c63ce  mov     [rsp+208h+var_1E8], 9F3h
0x1800c63d6  xor     r9d, r9d
0x1800c63d9  lea     r12, aD_0; "D"
0x1800c63e0  mov     r8, r12
0x1800c63e3  mov     r13d, 0C8000h
0x1800c63e9  mov     edx, r13d
0x1800c63ec  mov     rcx, rax
0x1800c63ef  call    cs:__imp_WdsSetupLogMessageW
0x1800c63f5  lea     rdx, aSpEnvAddSimula_0; "SP_ENV_ADD_SIMULATED_OPS_UPG"
0x1800c63fc  lea     rcx, [rsp+208h+var_150]
0x1800c6404  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800c640a  nop
0x1800c640b  xor     edx, edx
0x1800c640d  mov     rcx, rax
0x1800c6410  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x1800c6416  mov     ebx, eax
0x1800c6418  lea     rcx, [rsp+208h+var_150]
0x1800c6420  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800c6426  test    ebx, ebx
0x1800c6428  jz      short loc_1800C6440
0x1800c642a  mov     rcx, [r14+1F0h]
0x1800c6431  mov     rax, [rcx]
0x1800c6434  mov     edx, r15d
0x1800c6437  mov     rax, [rax+18h]
0x1800c643b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6440  lea     rdx, aSpEnvAddSimula; "SP_ENV_ADD_SIMULATED_OPS_PBR"
0x1800c6447  lea     rcx, [rsp+208h+var_150]
0x1800c644f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800c6455  nop
0x1800c6456  xor     edx, edx
0x1800c6458  mov     rcx, rax
0x1800c645b  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x1800c6461  mov     ebx, eax
0x1800c6463  lea     rcx, [rsp+208h+var_150]
0x1800c646b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800c6471  test    ebx, ebx
0x1800c6473  jz      short loc_1800C649E
0x1800c6475  mov     rcx, [r14+1F0h]
0x1800c647c  mov     rax, [rcx]
0x1800c647f  mov     edx, 2
0x1800c6484  mov     rax, [rax+18h]
0x1800c6488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c648d  jmp     short loc_1800C649E
0x1800c648f  xor     esi, esi
0x1800c6491  lea     r12, aD_0; "D"
0x1800c6498  mov     r13d, 0C8000h
0x1800c649e  mov     eax, [r14+1CCh]
0x1800c64a5  mov     [rsp+208h+var_1A4], eax
0x1800c64a9  lea     rcx, [r14+10h]; lpCriticalSection
0x1800c64ad  call    cs:__imp_EnterCriticalSection
0x1800c64b3  mov     [rsp+208h+Status], esi
0x1800c64b7  mov     [rsp+208h+var_1A0], esi
0x1800c64bb  lea     rcx, [rsp+208h+var_138]
0x1800c64c3  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1800c64c9  lea     rax, ??_7CXXXXXHandledException@?P@??Finalize@CDeploymentBase@@QEAA?AW4SYSTEM_STATE@SetupPlatform@@PEAUIOperationsProgress@4@H@Z@6B@; const `CDeploymentBase::Finalize(SetupPlatform::IOperationsProgress *,int)'::`15'::CXXXXXHandledException::`vftable'
0x1800c64d0  mov     [rsp+208h+var_138], rax
0x1800c64d8  cmp     [r14+1C4h], esi
0x1800c64df  jnz     short loc_1800C64FF
0x1800c64e1  mov     rax, [r14]
0x1800c64e4  mov     rcx, r14
0x1800c64e7  mov     rax, [rax+98h]
0x1800c64ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c64f3  mov     [rsp+208h+Status], eax
0x1800c64f7  test    eax, eax
0x1800c64f9  js      loc_1800C6D1F
0x1800c64ff  mov     [rsp+208h+var_178], rsi
0x1800c6507  call    cs:__imp_GetLastError
0x1800c650d  mov     edi, eax
0x1800c650f  call    cs:__imp_CurrentIP
0x1800c6515  mov     rbx, rax
0x1800c6518  lea     rdx, aDiskspacequery_0; "DISKSPACEQUERY: Calculating disk space "...
0x1800c651f  mov     ecx, 4000000h; unsigned int
0x1800c6524  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800c6529  mov     [rsp+208h+var_1B8], esi
0x1800c652d  mov     [rsp+208h+var_1C0], rsi
0x1800c6532  mov     [rsp+208h+var_1C8], edi
0x1800c6536  mov     [rsp+208h+var_1D0], rbx
0x1800c653b  lea     rcx, aCdeploymentbas_30; "CDeploymentBase::Finalize"
0x1800c6542  mov     [rsp+208h+var_1D8], rcx
0x1800c6547  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800c654e  mov     [rsp+208h+var_1E0], rcx
0x1800c6553  mov     [rsp+208h+var_1E8], 0A15h
0x1800c655b  xor     r9d, r9d
0x1800c655e  mov     r8, r12
0x1800c6561  mov     edx, r13d
0x1800c6564  mov     rcx, rax
0x1800c6567  call    cs:__imp_WdsSetupLogMessageW
0x1800c656d  mov     eax, [r14+210h]
0x1800c6574  mov     [rsp+208h+var_1E8], eax; int
0x1800c6578  lea     r9, [rsp+208h+var_198]; __int64 *
0x1800c657d  lea     r8, [rsp+208h+var_178]; __int64 *
0x1800c6585  mov     rdx, r14; struct IExecutionContext *
0x1800c6588  mov     rcx, [r14+1F0h]; this
0x1800c658f  call    ?GetDiskSpaceNeeded@COperationQueue@@QEAAJPEAUIExecutionContext@@AEA_J1H@Z; COperationQueue::GetDiskSpaceNeeded(IExecutionContext *,__int64 &,__int64 &,int)
0x1800c6594  mov     dword ptr [rsp+208h+var_198], eax
0x1800c6598  mov     [rsp+208h+Status], eax
0x1800c659c  test    eax, eax
0x1800c659e  js      loc_1800C6D5B
0x1800c65a4  call    cs:__imp_GetLastError
0x1800c65aa  mov     edi, eax
0x1800c65ac  call    cs:__imp_CurrentIP
0x1800c65b2  mov     rbx, rax
0x1800c65b5  mov     r8, [rsp+208h+var_178]
0x1800c65bd  lea     rdx, aDiskspacequery_4; "DISKSPACEQUERY: Final disk space needed"...
0x1800c65c4  mov     ecx, 4000000h; unsigned int
0x1800c65c9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800c65ce  mov     [rsp+208h+var_1B8], esi
0x1800c65d2  mov     [rsp+208h+var_1C0], rsi
0x1800c65d7  mov     [rsp+208h+var_1C8], edi
0x1800c65db  mov     [rsp+208h+var_1D0], rbx
0x1800c65e0  lea     rcx, aCdeploymentbas_30; "CDeploymentBase::Finalize"
0x1800c65e7  mov     [rsp+208h+var_1D8], rcx
0x1800c65ec  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800c65f3  mov     [rsp+208h+var_1E0], rcx
0x1800c65f8  mov     [rsp+208h+var_1E8], 0A21h
0x1800c6600  xor     r9d, r9d
0x1800c6603  mov     r8, r12
0x1800c6606  mov     edx, r13d
0x1800c6609  mov     rcx, rax
0x1800c660c  call    cs:__imp_WdsSetupLogMessageW
0x1800c6612  lea     rcx, [r14+98h]
0x1800c6619  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800c661f  mov     rcx, rax
0x1800c6622  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800c6628  mov     rcx, rax; unsigned __int16 *
0x1800c662b  call    ?SPGetFreeDiskSpace@@YA_KPEBG@Z; SPGetFreeDiskSpace(ushort const *)
0x1800c6630  cmp     rax, [rsp+208h+var_178]
0x1800c6638  jnb     short loc_1800C6653
0x1800c663a  add     rax, 6400000h
0x1800c6640  mov     [rsp+208h+var_198], rax
0x1800c6645  cmp     rax, [rsp+208h+var_178]
0x1800c664d  jb      loc_1800C6DEF
0x1800c6653  mov     [r14+1CCh], r15d
0x1800c665a  mov     [rsp+208h+var_190], esi
0x1800c665e  mov     [rsp+208h+var_184], esi
0x1800c6665  mov     dword ptr [rsp+208h+var_178], esi
0x1800c666c  mov     [rsp+208h+var_188], esi
0x1800c6673  mov     [rsp+208h+var_19C], esi
0x1800c6677  lea     rax, [rsp+208h+var_184]
0x1800c667f  mov     [rsp+208h+var_1D8], rax
0x1800c6684  lea     rax, [rsp+208h+var_190]
0x1800c6689  mov     qword ptr [rsp+208h+var_1E8], rax
0x1800c668e  mov     r9d, [r14+210h]
0x1800c6695  mov     r8, r14
0x1800c6698  mov     edx, r15d
0x1800c669b  mov     rcx, [r14+1F0h]
0x1800c66a2  call    ?ValidateOperationsForPhase@COperationQueue@@QEAAJW4OP_EXECUTION_PHASE@@PEAUIExecutionContext@@HPEAHPEAI3@Z; COperationQueue::ValidateOperationsForPhase(OP_EXECUTION_PHASE,IExecutionContext *,int,int *,uint *,uint *)
0x1800c66a7  mov     dword ptr [rsp+208h+var_198], eax
0x1800c66ab  mov     [rsp+208h+Status], eax
0x1800c66af  test    eax, eax
0x1800c66b1  js      loc_1800C6F60
0x1800c66b7  lea     rax, [rsp+208h+var_188]
0x1800c66bf  mov     [rsp+208h+var_1D8], rax
0x1800c66c4  lea     rax, [rsp+208h+var_178]
0x1800c66cc  mov     qword ptr [rsp+208h+var_1E8], rax
0x1800c66d1  mov     r9d, [r14+210h]
0x1800c66d8  mov     r8, r14
0x1800c66db  mov     edx, 2
0x1800c66e0  mov     rcx, [r14+1F0h]
0x1800c66e7  call    ?ValidateOperationsForPhase@COperationQueue@@QEAAJW4OP_EXECUTION_PHASE@@PEAUIExecutionContext@@HPEAHPEAI3@Z; COperationQueue::ValidateOperationsForPhase(OP_EXECUTION_PHASE,IExecutionContext *,int,int *,uint *,uint *)
0x1800c66ec  mov     dword ptr [rsp+208h+var_198], eax
0x1800c66f0  mov     [rsp+208h+Status], eax
0x1800c66f4  test    eax, eax
0x1800c66f6  js      loc_1800C7007
0x1800c66fc  lea     rax, [rsp+208h+var_19C]
0x1800c6701  mov     [rsp+208h+var_1D8], rax
0x1800c6706  mov     qword ptr [rsp+208h+var_1E8], rsi
0x1800c670b  mov     r9d, [r14+210h]
0x1800c6712  mov     r8, r14
0x1800c6715  mov     edx, 3
0x1800c671a  mov     rcx, [r14+1F0h]
0x1800c6721  call    ?ValidateOperationsForPhase@COperationQueue@@QEAAJW4OP_EXECUTION_PHASE@@PEAUIExecutionContext@@HPEAHPEAI3@Z; COperationQueue::ValidateOperationsForPhase(OP_EXECUTION_PHASE,IExecutionContext *,int,int *,uint *,uint *)
0x1800c6726  mov     dword ptr [rsp+208h+var_198], eax
0x1800c672a  mov     [rsp+208h+Status], eax
0x1800c672e  test    eax, eax
0x1800c6730  js      loc_1800C70AE
0x1800c6736  mov     ecx, [rsp+208h+var_19C]
0x1800c673a  add     ecx, [rsp+208h+var_188]
0x1800c6741  mov     edx, [rsp+208h+var_184]
0x1800c6748  add     ecx, edx
0x1800c674a  mov     dword ptr [rsp+208h+var_198], ecx
0x1800c674e  jz      short loc_1800C675D
0x1800c6750  imul    eax, edx, 64h ; 'd'
0x1800c6753  xor     edx, edx
0x1800c6755  div     ecx
0x1800c6757  mov     [rsp+208h+var_18C], eax
0x1800c675b  jmp     short loc_1800C6761
0x1800c675d  mov     [rsp+208h+var_18C], esi
0x1800c6761  call    cs:__imp_GetLastError
0x1800c6767  mov     edi, eax
0x1800c6769  call    cs:__imp_CurrentIP
0x1800c676f  mov     rbx, rax
0x1800c6772  mov     r9d, [rsp+208h+var_18C]
0x1800c6777  xor     r8d, r8d
0x1800c677a  lea     rdx, aVerbosePercent; "VERBOSE: Percents for downlevel: %d%% -"...
0x1800c6781  mov     ecx, 4000000h; unsigned int
0x1800c6786  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800c678b  mov     [rsp+208h+var_1B8], esi
0x1800c678f  mov     [rsp+208h+var_1C0], rsi
0x1800c6794  mov     [rsp+208h+var_1C8], edi
0x1800c6798  mov     [rsp+208h+var_1D0], rbx
0x1800c679d  lea     rcx, aCdeploymentbas_30; "CDeploymentBase::Finalize"
0x1800c67a4  mov     [rsp+208h+var_1D8], rcx
0x1800c67a9  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800c67b0  mov     [rsp+208h+var_1E0], rcx
0x1800c67b5  mov     [rsp+208h+var_1E8], 0A5Ch
0x1800c67bd  xor     r9d, r9d
0x1800c67c0  mov     r8, r12
0x1800c67c3  mov     edx, r13d
0x1800c67c6  mov     rcx, rax
0x1800c67c9  call    cs:__imp_WdsSetupLogMessageW
0x1800c67cf  cmp     [rsp+208h+var_190], esi
0x1800c67d3  jnz     short loc_1800C680D
0x1800c67d5  mov     rax, [r14]
0x1800c67d8  mov     r9d, [rsp+208h+var_18C]
0x1800c67dd  mov     [rsp+208h+var_1E8], r9d
0x1800c67e2  xor     r9d, r9d
0x1800c67e5  mov     r8, qword ptr [rsp+208h+SystemPowerStatus.ACLineStatus]
0x1800c67ed  mov     edx, r15d
0x1800c67f0  mov     rcx, r14
0x1800c67f3  mov     rax, [rax+0A0h]
0x1800c67fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c67ff  mov     [rsp+208h+Status], eax
0x1800c6803  test    eax, eax
0x1800c6805  js      loc_1800C7155
0x1800c680b  jmp     short loc_1800C6830
0x1800c680d  mov     rcx, qword ptr [rsp+208h+SystemPowerStatus.ACLineStatus]
0x1800c6815  test    rcx, rcx
0x1800c6818  jz      short loc_1800C6830
0x1800c681a  mov     rax, [rcx]
0x1800c681d  mov     r9d, [rsp+208h+var_18C]
  ... truncated ...
```
