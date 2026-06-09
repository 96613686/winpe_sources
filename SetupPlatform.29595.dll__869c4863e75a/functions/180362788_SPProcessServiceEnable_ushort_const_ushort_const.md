# SPProcessServiceEnable(ushort const *,ushort const *)

- ea: `0x180362788`
- end: `0x180363725`
- name: `?SPProcessServiceEnable@@YAXPEBG0@Z`
- size: `3997`
- prototype: `void(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1801708f0`
- `0x180216f50`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x1800b42d0`
- `0x18035734c`
- `0x18035fe7c`
- `0x180362788`
- `0x180363f00`
- `0x180365880`
- `0x180365a00`
- `0x180365ae8`
- `0x180365c58`
- `0x180404554`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180363022`
- `ADVAPI32!RegCloseKey` at `0x180363022`
- `ADVAPI32!OpenSCManagerW` at `0x1803629a1`
- `ADVAPI32!OpenSCManagerW` at `0x1803629a1`
- `ADVAPI32!OpenServiceW` at `0x180363263`
- `ADVAPI32!OpenServiceW` at `0x180363263`
- `ADVAPI32!CloseServiceHandle` at `0x180363559`
- `ADVAPI32!CloseServiceHandle` at `0x180363559`
- `ADVAPI32!StartServiceW` at `0x18036327d`
- `ADVAPI32!StartServiceW` at `0x18036327d`
- `KERNEL32!GetLastError` at `0x1803627b3`
- `KERNEL32!GetLastError` at `0x1803628c9`
- `KERNEL32!GetLastError` at `0x1803628da`
- `KERNEL32!GetLastError` at `0x1803629b1`
- `KERNEL32!GetLastError` at `0x1803629c2`
- `KERNEL32!GetLastError` at `0x180362a7d`
- `KERNEL32!GetLastError` at `0x180362cc5`
- `KERNEL32!GetLastError` at `0x180362de8`
- `KERNEL32!GetLastError` at `0x180362e62`
- `KERNEL32!GetLastError` at `0x180362f45`
- `KERNEL32!GetLastError` at `0x180363064`
- `KERNEL32!GetLastError` at `0x180363127`
- `KERNEL32!GetLastError` at `0x1803631ef`
- `KERNEL32!GetLastError` at `0x18036328b`
- `KERNEL32!GetLastError` at `0x180363322`
- `KERNEL32!GetLastError` at `0x180363418`
- `KERNEL32!GetLastError` at `0x180363477`
- `KERNEL32!GetLastError` at `0x180363487`
- `KERNEL32!GetLastError` at `0x1803634e0`
- `KERNEL32!GetLastError` at `0x18036356b`
- `KERNEL32!GetLastError` at `0x180363581`
- `KERNEL32!GetLastError` at `0x180363592`
- `KERNEL32!GetLastError` at `0x1803635e6`
- `KERNEL32!GetLastError` at `0x18036363f`
- `KERNEL32!GetLastError` at `0x1803627b3`
- `KERNEL32!GetLastError` at `0x1803628c9`
- `KERNEL32!GetLastError` at `0x1803628da`
- `KERNEL32!GetLastError` at `0x1803629b1`
- `KERNEL32!GetLastError` at `0x1803629c2`
- `KERNEL32!GetLastError` at `0x180362a7d`
- `KERNEL32!GetLastError` at `0x180362cc5`
- `KERNEL32!GetLastError` at `0x180362de8`
- `KERNEL32!GetLastError` at `0x180362e62`
- `KERNEL32!GetLastError` at `0x180362f45`
- `KERNEL32!GetLastError` at `0x180363064`
- `KERNEL32!GetLastError` at `0x180363127`
- `KERNEL32!GetLastError` at `0x1803631ef`
- `KERNEL32!GetLastError` at `0x18036328b`
- `KERNEL32!GetLastError` at `0x180363322`
- `KERNEL32!GetLastError` at `0x180363418`
- `KERNEL32!GetLastError` at `0x180363477`
- `KERNEL32!GetLastError` at `0x180363487`
- `KERNEL32!GetLastError` at `0x1803634e0`
- `KERNEL32!GetLastError` at `0x18036356b`
- `KERNEL32!GetLastError` at `0x180363581`
- `KERNEL32!GetLastError` at `0x180363592`
- `KERNEL32!GetLastError` at `0x1803635e6`
- `KERNEL32!GetLastError` at `0x18036363f`
- `unbcl!?Trim@String@UnBCL@@QEBAPEAV12@XZ` at `0x180362bab`
- `unbcl!?Trim@String@UnBCL@@QEBAPEAV12@XZ` at `0x180362c7c`
- `unbcl!?Trim@String@UnBCL@@QEBAPEAV12@XZ` at `0x180362bab`
- `unbcl!?Trim@String@UnBCL@@QEBAPEAV12@XZ` at `0x180362c7c`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180362c34`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180362c34`
- `unbcl!?LastIndexOf@String@UnBCL@@QEBAHG@Z` at `0x180362b5e`
- `unbcl!?LastIndexOf@String@UnBCL@@QEBAHG@Z` at `0x180362b5e`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180362c0f`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x180362c0f`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180362b82`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180362b82`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180362979`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180362979`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180362f10`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180362ff3`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180362f10`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180362ff3`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1803636bc`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1803636bc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180362876`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180362ecf`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180362fb2`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18036318e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1803631bf`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180362876`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180362ecf`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180362fb2`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18036318e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1803631bf`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180362846`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180362846`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180362867`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180362867`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18036294f`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18036294f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180362f04`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180362fe7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180362f04`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180362fe7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180362b24`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180362b24`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18036282a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180362b08`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180362ee9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180362fcc`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18036282a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180362b08`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180362ee9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180362fcc`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180362bd3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180362c59`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180362ca1`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180362bd3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180362c59`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180362ca1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362b50`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362b73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362ba2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362bf0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362c26`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362c73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362cf0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362d63`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362db8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362b50`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362b73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362ba2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362bf0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362c26`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362c73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362cf0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362d63`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180362db8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362bf9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362cf9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362d6c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362dc1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803631e6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362bf9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362cf9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362d6c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180362dc1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1803631e6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362be2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362c68`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362cb0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362cbf`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18036302e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362be2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362c68`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362cb0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180362cbf`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18036302e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362b44`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362b93`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362bbc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362c45`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362c8d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362b44`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362b93`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362bbc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362c45`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180362c8d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18036281f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362940`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362a17`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362adb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362d58`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362e4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362ec1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362fa4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803630cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x18036317d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18036324f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803632f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180363550`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803636a6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18036281f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362940`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362a17`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362adb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362d58`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362e4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362ec1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180362fa4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803630cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x18036317d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18036324f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803632f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180363550`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803636a6`
- `WDSCORE!CurrentIP` at `0x1803627bb`
- `WDSCORE!CurrentIP` at `0x1803628d1`
- `WDSCORE!CurrentIP` at `0x1803629b9`
- `WDSCORE!CurrentIP` at `0x180362a85`
- `WDSCORE!CurrentIP` at `0x180362ccd`
- `WDSCORE!CurrentIP` at `0x180362df0`
- `WDSCORE!CurrentIP` at `0x180362e6a`
- `WDSCORE!CurrentIP` at `0x180362f4d`
- `WDSCORE!CurrentIP` at `0x18036306c`
- `WDSCORE!CurrentIP` at `0x18036312f`

## string_xrefs

- `0x18036359e`: `Failed to open service %s. Error: 0x%08X`
- `0x1803627f5`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x18036291c`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803629f3`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180362a1f`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180362d34`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180362e28`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180362e9b`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180362f7e`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180363018`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803630a7`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x18036310f`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x18036322b`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803632ce`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x18036336b`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803633b9`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803633ff`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x18036345e`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803634ca`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180363526`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x1803635cd`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180363629`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180363682`: `base\ntsetup\setupplatform\lib\util\serviceutils.cpp`
- `0x180362d05`: `Processing service "%s"%s`
- `0x1803628f4`: `Cannot open/load system hive from %s. Error: 0x%08X`
- `0x180362e73`: `Service is AUTO_START, will start it after all processing is done`
- `0x180362df9`: `Service start type restored`
- `0x1803629cb`: `Failed to open service manager, won't be able to refresh/start restored services. Error: 0x%08X`
- `0x1803627c4`: `Enabling (and potentially starting) deferred services`
- `0x1803627e9`: `SPProcessServiceEnable`
- `0x180362d28`: `SPProcessServiceEnable`
- `0x180362e1c`: `SPProcessServiceEnable`
- `0x180362f35`: `SPProcessServiceEnable`
- `0x18036309b`: `SPProcessServiceEnable`
- `0x1803630e7`: `SPProcessServiceEnable`
- `0x180363108`: `SPProcessServiceEnable`
- `0x1803632c2`: `SPProcessServiceEnable`
- `0x18036335f`: `SPProcessServiceEnable`
- `0x1803633ad`: `SPProcessServiceEnable`
- `0x1803633f3`: `SPProcessServiceEnable`
- `0x180363452`: `SPProcessServiceEnable`
- `0x1803634be`: `SPProcessServiceEnable`
- `0x18036351a`: `SPProcessServiceEnable`
- `0x18036355f`: `SPProcessServiceEnable`
- `0x1803635c1`: `SPProcessServiceEnable`
- `0x18036361d`: `SPProcessServiceEnable`
- `0x180363676`: `SPProcessServiceEnable`
- `0x1803633d5`: `Service %s state is %u`
- `0x18036338f`: `Service %s is still stopped, probably stopped automatically`
- `0x18036333c`: `Service %s is now running`
- `0x18036329f`: `Service %s is starting`
- `0x180363203`: `Starting service %s`
- `0x180363138`: `Starting the AUTO_START services`
- `0x180363078`: `Failed to restore the start type for service. Error: 0x%08X`
- `0x180362f56`: `Service is marked for forced start, will start it after all processing is done`
- `0x180363653`: `Service %s is already running`
- `0x1803635fa`: `Service %s does not exist, skipping`
- `0x1803634f7`: `Could not start service %s. Error: 0x%08X`
- `0x18036349b`: `Service %s was already running.`
- `0x18036342f`: `An error occurred waiting for service %s to start. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall SPProcessServiceEnable(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rax
  HKEY v9; // rax
  HKEY v10; // r13
  DWORD v11; // edi
  __int64 v12; // rbx
  DWORD v13; // eax
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  DWORD v17; // eax
  struct tagLOG_PARTIAL_MSG *v18; // rax
  int ControlSet; // eax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  const unsigned __int16 *i; // rdi
  UnBCL::String *v24; // rax
  UnBCL::String *v25; // rbx
  int v26; // r12d
  UnBCL::String *v27; // rax
  int IndexOf; // ebx
  UnBCL::String *v29; // rax
  struct UnBCL::String *v30; // rax
  UnBCL::String *v31; // rax
  struct UnBCL::String *v32; // rax
  UnBCL::String *v33; // rax
  const unsigned __int16 *CString; // rax
  UnBCL::String *v35; // rax
  struct UnBCL::String *v36; // rax
  UnBCL::String *v37; // rax
  struct UnBCL::String *v38; // rax
  DWORD v39; // edi
  __int64 v40; // r14
  const wchar_t *v41; // rbx
  UnBCL::String *v42; // rax
  const char *v43; // rax
  struct tagLOG_PARTIAL_MSG *v44; // rax
  UnBCL::String *v45; // rax
  const unsigned __int16 *v46; // rax
  HKEY v47; // r15
  SC_HANDLE v48; // rbx
  UnBCL::String *v49; // rax
  const WCHAR *v50; // rax
  unsigned int started; // eax
  unsigned int v52; // r14d
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rdi
  __int64 v61; // r14
  UnBCL::String *v62; // rbx
  const struct UnBCL::String *P; // rax
  DWORD v64; // edi
  __int64 v65; // rbx
  struct tagLOG_PARTIAL_MSG *v66; // rax
  __int64 v67; // rax
  __int64 v68; // rdi
  __int64 v69; // r14
  UnBCL::String *v70; // rbx
  const struct UnBCL::String *v71; // rax
  __int64 v72; // rax
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  DWORD v76; // edi
  __int64 v77; // rbx
  struct tagLOG_PARTIAL_MSG *v78; // rax
  int j; // r13d
  __int64 v80; // rax
  int (__fastcall ***v81)(_QWORD); // rcx
  __int64 v82; // rax
  __int64 v83; // rcx
  UnBCL::String **v84; // rax
  const char *v85; // r14
  DWORD v86; // edi
  __int64 v87; // rbx
  struct tagLOG_PARTIAL_MSG *v88; // rax
  SC_HANDLE v89; // rax
  SC_HANDLE v90; // r12
  DWORD v91; // edi
  __int64 v92; // rbx
  struct tagLOG_PARTIAL_MSG *v93; // rax
  unsigned int v94; // edx
  unsigned int v95; // r8d
  unsigned int v96; // r15d
  int v97; // r15d
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  DWORD v103; // r15d
  DWORD v104; // edi
  __int64 v105; // rbx
  DWORD v106; // eax
  DWORD v107; // edi
  __int64 v108; // rbx
  DWORD v109; // eax
  struct tagLOG_PARTIAL_MSG *v110; // rax
  DWORD v111; // edi
  __int64 v112; // rbx
  DWORD v113; // edi
  __int64 v114; // rbx
  HKEY *v115; // rbp
  SC_HANDLE v116; // rcx
  HKEY v117; // rcx
  _BYTE *v118; // rdx
  _BYTE *v119; // rdx
  _BYTE v120[32]; // [rsp+0h] [rbp-1B8h] BYREF
  int v121; // [rsp+20h] [rbp-198h]
  const wchar_t *v122; // [rsp+28h] [rbp-190h]
  const wchar_t *v123; // [rsp+30h] [rbp-188h]
  __int64 v124; // [rsp+38h] [rbp-180h]
  DWORD v125; // [rsp+40h] [rbp-178h]
  __int64 v126; // [rsp+48h] [rbp-170h]
  int v127; // [rsp+50h] [rbp-168h]
  _BYTE v128[16]; // [rsp+60h] [rbp-158h] BYREF
  int v129; // [rsp+70h] [rbp-148h]
  SC_HANDLE hSCManager; // [rsp+78h] [rbp-140h]
  int Dword; // [rsp+80h] [rbp-138h]
  HKEY v132; // [rsp+88h] [rbp-130h]
  _BYTE v133[16]; // [rsp+90h] [rbp-128h] BYREF
  HKEY v134; // [rsp+A0h] [rbp-118h] BYREF
  unsigned int v135[2]; // [rsp+A8h] [rbp-110h]
  const unsigned __int16 *v136; // [rsp+B0h] [rbp-108h]
  _BYTE v137[16]; // [rsp+B8h] [rbp-100h] BYREF
  _BYTE *pExceptionObject; // [rsp+C8h] [rbp-F0h] BYREF
  _QWORD *v139; // [rsp+D0h] [rbp-E8h] BYREF
  _BYTE v140[16]; // [rsp+D8h] [rbp-E0h] BYREF
  _BYTE v141[16]; // [rsp+E8h] [rbp-D0h] BYREF
  _BYTE v142[16]; // [rsp+F8h] [rbp-C0h] BYREF
  __int64 v143; // [rsp+108h] [rbp-B0h]
  _QWORD v144[7]; // [rsp+110h] [rbp-A8h] BYREF
  _BYTE v145[112]; // [rsp+148h] [rbp-70h] BYREF
  UnBCL::String *v147; // [rsp+1D0h] [rbp+18h] BYREF
  int v148; // [rsp+1D8h] [rbp+20h]

  v143 = -2;
  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(0x4000000u, "Enabling (and potentially starting) deferred services");
  WdsSetupLogMessageW(
    v5,
    819200,
    L"D",
    0,
    608,
    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
    L"SPProcessServiceEnable",
    v4,
    LastError,
    0,
    0);
  v6 = UnBCL::Object::operator new(0xB0u);
  v7 = v6;
  v147 = (UnBCL::String *)v6;
  if ( v6 )
  {
    UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v6, 1);
    v7[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
  }
  else
  {
    v7 = 0;
  }
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v133, v7);
  v8 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  if ( a2 )
    v9 = SPMountOfflineHive(a2, L"SYSTEM", L"$OFFLINE_RW$SYSTEM");
  else
    v9 = pSPOpenOnlineSystemHive();
  v10 = v9;
  v132 = v9;
  if ( !v9 )
  {
    v11 = GetLastError();
    v12 = CurrentIP();
    v13 = GetLastError();
    if ( !a2 )
      a2 = L"online system";
    v14 = ConstructPartialMsgW(0x2000000u, "Cannot open/load system hive from %s. Error: 0x%08X", (const char *)a2, v13);
    WdsSetupLogMessageW(
      v14,
      819200,
      L"D",
      0,
      616,
      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
      L"SPProcessServiceEnable",
      v12,
      v11,
      0,
      0);
    goto LABEL_11;
  }
  hSCManager = 0;
  v129 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v144);
  v144[0] = &`SPProcessServiceEnable'::`6'::CXXXXXHandledException::`vftable';
  if ( !a2 )
  {
    hSCManager = OpenSCManagerW(0, 0, 0xA0000000);
    if ( !hSCManager )
    {
      v15 = GetLastError();
      v16 = CurrentIP();
      v17 = GetLastError();
      v18 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to open service manager, won't be able to refresh/start restored services. Error: 0x%08X",
              v17);
      WdsSetupLogMessageW(
        v18,
        819200,
        L"D",
        0,
        629,
        L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
        L"SPProcessServiceEnable",
        v16,
        v15,
        0,
        0);
    }
  }
  Dword = RegGetDword(v10, L"Select", L"Current");
  *(_QWORD *)v135 = 0;
  v134 = v10;
  ControlSet = pSPEnumNextControlSet((struct CONTROLSET_ENUM *)&v134);
  try
  {
    try
    {
      if ( !ControlSet )
        goto LABEL_52;
      v148 = 0;
      SPProcessServiceEnable_::_19_::CXXXXXHandledException::CXXXXXHandledException(v145);
      try
      {
        try
        {
          do
          {
            v20 = GetLastError();
            v21 = CurrentIP();
            v22 = ConstructPartialMsgW(0x4000000u, "Processing ControlSet%03u", v135[1]);
            WdsSetupLogMessageW(
              v22,
              819200,
              L"D",
              0,
              645,
              L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
              L"SPProcessServiceEnable",
              v21,
              v20,
              0,
              0);
            for ( i = a1; ; i = &v136[v72 + 1] )
            {
              v136 = i;
              if ( !i || !*i )
                break;
              v24 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
              v25 = v24;
              v147 = v24;
              if ( v24 )
              {
                UnBCL::String::String(v24, i);
                *(_QWORD *)v25 = &UnBCL::String::`local vftable';
              }
              else
              {
                v25 = 0;
              }
              v26 = 0;
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v128, v25);
              v27 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
              IndexOf = UnBCL::String::LastIndexOf(v27, 0x2Cu);
              if ( IndexOf > 0 )
              {
                v29 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
                v30 = UnBCL::String::Remove(v29, 0, IndexOf + 1);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v137, v30);
                v31 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v137);
                v32 = UnBCL::String::Trim(v31);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v140, v32);
                UnBCL::SmartPtr<UnBCL::String>::operator=(v137, v140);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v140);
                v33 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v137);
                CString = UnBCL::String::get_CString(v33);
                if ( !UnBCL::String::Compare(CString, L"ForceRestart", 1) )
                {
                  v26 = 1;
                  v35 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
                  v36 = UnBCL::String::Substring(v35, 0, IndexOf);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v141, v36);
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v128, v141);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v141);
                  v37 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
                  v38 = UnBCL::String::Trim(v37);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v142, v38);
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v128, v142);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v142);
                }
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v137);
              }
              v39 = GetLastError();
              v40 = CurrentIP();
              v41 = L" (Force start)";
              if ( !v26 )
                v41 = &cchOriginalDestLength;
              v42 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
              v43 = (const char *)UnBCL::String::get_CString(v42);
              v44 = ConstructPartialMsgW(0x4000000u, "Processing service \"%s\"%s", v43, (const char *)v41);
              WdsSetupLogMessageW(
                v44,
                819200,
                L"D",
                0,
                665,
                L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                L"SPProcessServiceEnable",
                v40,
                v39,
                0,
                0);
              v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
              v46 = UnBCL::String::get_CString(v45);
              v47 = pSPOpenServiceKey(v10, v46, v135[1]);
              if ( v47 )
              {
                LODWORD(v147) = -1;
                v48 = 0;
                if ( v135[1] == Dword )
                  v48 = hSCManager;
                v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
                v50 = UnBCL::String::get_CString(v49);
                started = pSPRestoreServiceStartType(v47, v50, v48, (unsigned int *)&v147);
                v52 = started;
                if ( started )
                {
                  if ( started - 2 > 1 )
                  {
                    v73 = GetLastError();
                    v74 = CurrentIP();
                    v75 = ConstructPartialMsgW(
                            0x2000000u,
                            "Failed to restore the start type for service. Error: 0x%08X",
                            v52);
                    WdsSetupLogMessageW(
                      v75,
                      819200,
                      L"D",
                      0,
                      691,
                      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                      L"SPProcessServiceEnable",
                      v74,
                      v73,
                      0,
                      0);
                  }
                }
                else
                {
                  v53 = GetLastError();
                  v54 = CurrentIP();
                  v55 = ConstructPartialMsgW(0x4000000u, "Service start type restored");
                  WdsSetupLogMessageW(
                    v55,
                    819200,
                    L"D",
                    0,
                    673,
                    L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                    L"SPProcessServiceEnable",
                    v54,
                    v53,
                    0,
                    0);
                  if ( (_DWORD)v147 == 2 )
                  {
                    v56 = GetLastError();
                    v57 = CurrentIP();
                    v58 = ConstructPartialMsgW(
                            0x4000000u,
                            "Service is AUTO_START, will start it after all processing is done");
                    WdsSetupLogMessageW(
                      v58,
                      819200,
                      L"D",
                      0,
                      678,
                      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                      L"SPProcessServiceEnable",
                      v57,
                      v56,
                      0,
                      0);
                    v59 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
                    v60 = v59 + *(int *)(*(_QWORD *)(v59 + 8) + 16LL);
                    v61 = *(_QWORD *)(v60 + 8);
                    v62 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                    v147 = v62;
                    if ( v62 )
                    {
                      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v128);
                      UnBCL::String::String(v62, P);
                      *(_QWORD *)v62 = &UnBCL::String::`local vftable';
                    }
                    else
                    {
                      v62 = 0;
                    }
                    (*(void (__fastcall **)(__int64, UnBCL::String *))(v61 + 40))(v60 + 8, v62);
                  }
                  if ( v26 )
                  {
                    v64 = GetLastError();
                    v65 = CurrentIP();
                    v66 = ConstructPartialMsgW(
                            0x4000000u,
                            "Service is marked for forced start, will start it after all processing is done");
                    WdsSetupLogMessageW(
                      v66,
                      819200,
                      L"D",
                      0,
                      683,
                      L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                      L"SPProcessServiceEnable",
                      v65,
                      v64,
                      0,
                      0);
                    v67 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
                    v68 = v67 + *(int *)(*(_QWORD *)(v67 + 8) + 16LL);
                    v69 = *(_QWORD *)(v68 + 8);
                    v70 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                    v147 = v70;
                    if ( v70 )
                    {
                      v71 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v128);
                      UnBCL::String::String(v70, v71);
                      *(_QWORD *)v70 = &UnBCL::String::`local vftable';
                    }
                    else
                    {
                      v70 = 0;
                    }
                    (*(void (__fastcall **)(__int64, UnBCL::String *))(v69 + 40))(v68 + 8, v70);
                  }
                }
                RegCloseKey(v47);
              }
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v128);
              v72 = -1;
              do
                ++v72;
              while ( v136[v72] );
            }
          }
          while ( (unsigned int)pSPEnumNextControlSet((struct CONTROLSET_ENUM *)&v134) );
        }
        catch ( Z::YAXPEBG0:: )
        {
          SPProcessServiceEnable_::_1_::catch_14();
          __eh34_caught_type(3, Z::YAXPEBG0::`SPProcessServiceEnable'::`20'::CXXXXXTemp * `RTTI Type Descriptor');
        }
        v148 = 1;
        pExceptionObject = v145;
        throw (`SPProcessServiceEnable(ushort const *,ushort const *)'::`19'::CXXXXXHandledException **)&pExceptionObject;
      }
      catch ( UnBCL::Exception * )
      {
        v119 = v120;
        if ( !*((_DWORD *)v119 + 118) )
          throw;
        `COperation::Execute'::`12'::CXXXXXHandledException::~CXXXXXHandledException(v145);
LABEL_52:
        if ( hSCManager )
        {
          v76 = GetLastError();
          v77 = CurrentIP();
          v78 = ConstructPartialMsgW(0x4000000u, "Starting the AUTO_START services");
          WdsSetupLogMessageW(
            v78,
            819200,
            L"D",
            0,
            712,
            L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
            L"SPProcessServiceEnable",
            v77,
            v76,
            0,
            0);
          for ( j = 0; ; ++j )
          {
            v80 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
            v81 = (int (__fastcall ***)(_QWORD))(v80 + 8 + *(int *)(*(_QWORD *)(v80 + 8) + 12LL));
            if ( j >= (**v81)(v81) )
              break;
            v82 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
            v83 = v82 + 8 + *(int *)(*(_QWORD *)(v82 + 8) + 16LL);
            v84 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 24LL))(
                                      v83,
                                      (unsigned int)j);
            v85 = (const char *)UnBCL::String::get_CString(*v84);
            v86 = GetLastError();
            v87 = CurrentIP();
            v88 = ConstructPartialMsgW(0x4000000u, "Starting service %s", v85);
            WdsSetupLogMessageW(
              v88,
              819200,
              L"D",
              0,
              716,
              L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
              L"SPProcessServiceEnable",
              v87,
              v86,
              0,
              0);
            v89 = OpenServiceW(hSCManager, (LPCWSTR)v85, 0xA0000000);
            v90 = v89;
            if ( v89 )
            {
              if ( StartServiceW(v89, 0, 0) )
              {
                v91 = GetLastError();
                v92 = CurrentIP();
                v93 = ConstructPartialMsgW(0x4000000u, "Service %s is starting", v85);
                WdsSetupLogMessageW(
                  v93,
                  819200,
                  L"D",
                  0,
                  722,
                  L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp",
                  L"SPProcessServiceEnable",
                  v92,
                  v91,
                  0,
                  0);
                LODWORD(v147) = 0;
                v96 = SPWaitForServiceState(v90, v94, v95, (unsigned int *)&v147);
                if ( v96 )
                {
                  v101 = GetLastError();
                  v102 = CurrentIP();
                  v100 = ConstructPartialMsgW(
                           0x3000000u,
                           "An error occurred waiting for service %s to start. Error: 0x%08X",
                           v85,
                           v96);
                  v127 = 0;
                  v126 = 0;
                  v125 = v101;
                  v124 = v102;
                  v123 = L"SPProcessServiceEnable";
                  v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                  v121 = 744;
                }
                else
                {
                  v97 = (int)v147;
                  v98 = GetLastError();
                  v99 = CurrentIP();
                  if ( v97 == 4 )
                  {
                    v100 = ConstructPartialMsgW(0x4000000u, "Service %s is now running", v85);
                    v127 = 0;
                    v126 = 0;
                    v125 = v98;
                    v124 = v99;
                    v123 = L"SPProcessServiceEnable";
                    v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                    v121 = 731;
                  }
                  else if ( v97 == 1 )
                  {
                    v100 = ConstructPartialMsgW(
                             0x3000000u,
                             "Service %s is still stopped, probably stopped automatically",
                             v85);
                    v127 = 0;
                    v126 = 0;
                    v125 = v98;
                    v124 = v99;
                    v123 = L"SPProcessServiceEnable";
                    v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                    v121 = 735;
                  }
                  else
                  {
                    v100 = ConstructPartialMsgW(0x3000000u, "Service %s state is %u", v85, v97);
                    v127 = 0;
                    v126 = 0;
                    v125 = v98;
                    v124 = v99;
                    v123 = L"SPProcessServiceEnable";
                    v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                    v121 = 739;
                  }
                }
              }
              else
              {
                v103 = GetLastError();
                v104 = GetLastError();
                v105 = CurrentIP();
                if ( v103 == 1056 )
                {
                  v100 = ConstructPartialMsgW(0x4000000u, "Service %s was already running.", v85);
                  v127 = 0;
                  v126 = 0;
                  v125 = v104;
                  v124 = v105;
                  v123 = L"SPProcessServiceEnable";
                  v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                  v121 = 752;
                }
                else
                {
                  v100 = ConstructPartialMsgW(0x3000000u, "Could not start service %s. Error: 0x%08X", v85, v103);
                  v127 = 0;
                  v126 = 0;
                  v125 = v104;
                  v124 = v105;
                  v123 = L"SPProcessServiceEnable";
                  v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                  v121 = 756;
                }
              }
              WdsSetupLogMessageW(v100, 819200, L"D", 0, v121, v122, v123, v124, v125, v126, v127);
              CloseServiceHandle(v90);
            }
            else
            {
              v106 = GetLastError() - 1056;
              if ( v106 )
              {
                if ( v106 == 4 )
                {
                  v111 = GetLastError();
                  v112 = CurrentIP();
                  v110 = ConstructPartialMsgW(0x4000000u, "Service %s does not exist, skipping", v85);
                  v127 = 0;
                  v126 = 0;
                  v125 = v111;
                  v124 = v112;
                  v123 = L"SPProcessServiceEnable";
                  v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                  v121 = 767;
                }
                else
                {
                  v107 = GetLastError();
                  v108 = CurrentIP();
                  v109 = GetLastError();
                  v110 = ConstructPartialMsgW(0x2000000u, "Failed to open service %s. Error: 0x%08X", v85, v109);
                  v127 = 0;
                  v126 = 0;
                  v125 = v107;
                  v124 = v108;
                  v123 = L"SPProcessServiceEnable";
                  v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                  v121 = 773;
                }
              }
              else
              {
                v113 = GetLastError();
                v114 = CurrentIP();
                v110 = ConstructPartialMsgW(0x4000000u, "Service %s is already running", v85);
                v127 = 0;
                v126 = 0;
                v125 = v113;
                v124 = v114;
                v123 = L"SPProcessServiceEnable";
                v122 = L"base\\ntsetup\\setupplatform\\lib\\util\\serviceutils.cpp";
                v121 = 770;
              }
              WdsSetupLogMessageW(v110, 819200, L"D", 0, v121, v122, v123, v124, v125, v126, v127);
            }
          }
        }
      }
    }
    catch ( Z::YAXPEBG0:: )
    {
      SPProcessServiceEnable_::_1_::catch_16();
      __eh34_caught_type(1, Z::YAXPEBG0::`SPProcessServiceEnable'::`7'::CXXXXXTemp * `RTTI Type Descriptor');
    }
    v129 = 1;
    v139 = v144;
    throw (`SPProcessServiceEnable(ushort const *,ushort const *)'::`6'::CXXXXXHandledException **)&v139;
  }
  catch ( UnBCL::Exception * )
  {
    v118 = v120;
    v115 = (HKEY *)v118;
    v116 = (SC_HANDLE)*((_QWORD *)v118 + 15);
    if ( v116 )
      CloseServiceHandle(v116);
    RegCloseKey(v115[17]);
    if ( v115[57] )
      SPUnloadKey(v117, L"$OFFLINE_RW$SYSTEM");
    if ( !*((_DWORD *)v115 + 28) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v144);
LABEL_11:
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v133);
  }
}

```

## disassembly

```asm
0x180362788  mov     [rsp+arg_8], rdx
0x18036278d  mov     [rsp+arg_0], rcx
0x180362792  push    rbx
0x180362793  push    rsi
0x180362794  push    rdi
0x180362795  push    r12
0x180362797  push    r13
0x180362799  push    r14
0x18036279b  push    r15
0x18036279d  sub     rsp, 180h
0x1803627a4  mov     [rsp+1B8h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1803627b0  mov     r14, rdx
0x1803627b3  call    cs:__imp_GetLastError
0x1803627b9  mov     edi, eax
0x1803627bb  call    cs:__imp_CurrentIP
0x1803627c1  mov     rbx, rax
0x1803627c4  lea     rdx, aEnablingAndPot; "Enabling (and potentially starting) def"...
0x1803627cb  mov     ecx, 4000000h; unsigned int
0x1803627d0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803627d5  xor     esi, esi
0x1803627d7  mov     [rsp+1B8h+var_168], esi
0x1803627db  mov     [rsp+1B8h+var_170], rsi
0x1803627e0  mov     [rsp+1B8h+var_178], edi
0x1803627e4  mov     [rsp+1B8h+var_180], rbx
0x1803627e9  lea     r12, aSpprocessservi; "SPProcessServiceEnable"
0x1803627f0  mov     [rsp+1B8h+var_188], r12
0x1803627f5  lea     rdi, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1803627fc  mov     [rsp+1B8h+var_190], rdi
0x180362801  mov     [rsp+1B8h+var_198], 260h
0x180362809  xor     r9d, r9d
0x18036280c  lea     r8, aD_0; "D"
0x180362813  mov     r15d, 0C8000h
0x180362819  mov     edx, r15d
0x18036281c  mov     rcx, rax
0x18036281f  call    cs:__imp_WdsSetupLogMessageW
0x180362825  mov     ecx, 0B0h
0x18036282a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180362830  mov     rbx, rax
0x180362833  mov     [rsp+1B8h+arg_10], rax
0x18036283b  test    rax, rax
0x18036283e  jz      short loc_180362859
0x180362840  lea     edx, [rsi+1]
0x180362843  mov     rcx, rax
0x180362846  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x18036284c  lea     rax, ??_S?$ArrayList@PEAVString@UnBCL@@@UnBCL@@6BObject@1@@; const UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'}
0x180362853  mov     [rbx+30h], rax
0x180362857  jmp     short loc_18036285C
0x180362859  mov     rbx, rsi
0x18036285c  mov     rdx, rbx
0x18036285f  lea     rcx, [rsp+1B8h+var_128]
0x180362867  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18036286d  nop
0x18036286e  lea     rcx, [rsp+1B8h+var_128]
0x180362876  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18036287c  mov     r8, rax
0x18036287f  mov     rcx, [rax]
0x180362882  mov     rax, [rcx+28h]
0x180362886  mov     edx, 1
0x18036288b  mov     rcx, r8
0x18036288e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180362893  test    r14, r14
0x180362896  jz      short loc_1803628B0
0x180362898  lea     r8, aOfflineRwSyste; "$OFFLINE_RW$SYSTEM"
0x18036289f  lea     rdx, aSystem; "SYSTEM"
0x1803628a6  mov     rcx, r14; unsigned __int16 *
0x1803628a9  call    ?SPMountOfflineHive@@YAPEAUHKEY__@@PEBG00@Z; SPMountOfflineHive(ushort const *,ushort const *,ushort const *)
0x1803628ae  jmp     short loc_1803628B5
0x1803628b0  call    ?pSPOpenOnlineSystemHive@@YAPEAUHKEY__@@XZ; pSPOpenOnlineSystemHive(void)
0x1803628b5  mov     r13, rax
0x1803628b8  mov     [rsp+1B8h+var_130], rax
0x1803628c0  test    rax, rax
0x1803628c3  jnz     loc_180362968
0x1803628c9  call    cs:__imp_GetLastError
0x1803628cf  mov     edi, eax
0x1803628d1  call    cs:__imp_CurrentIP
0x1803628d7  mov     rbx, rax
0x1803628da  call    cs:__imp_GetLastError
0x1803628e0  lea     rcx, aOnlineSystem; "online system"
0x1803628e7  test    r14, r14
0x1803628ea  cmovz   r14, rcx
0x1803628ee  mov     r9d, eax
0x1803628f1  mov     r8, r14
0x1803628f4  lea     rdx, aCannotOpenLoad; "Cannot open/load system hive from %s. E"...
0x1803628fb  mov     ecx, 2000000h; unsigned int
0x180362900  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180362905  mov     [rsp+1B8h+var_168], esi
0x180362909  mov     [rsp+1B8h+var_170], rsi
0x18036290e  mov     [rsp+1B8h+var_178], edi
0x180362912  mov     [rsp+1B8h+var_180], rbx
0x180362917  mov     [rsp+1B8h+var_188], r12
0x18036291c  lea     rcx, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180362923  mov     [rsp+1B8h+var_190], rcx
0x180362928  mov     [rsp+1B8h+var_198], 268h
0x180362930  xor     r9d, r9d
0x180362933  lea     r8, aD_0; "D"
0x18036293a  mov     edx, r15d
0x18036293d  mov     rcx, rax
0x180362940  call    cs:__imp_WdsSetupLogMessageW
0x180362946  nop
0x180362947  lea     rcx, [rsp+1B8h+var_128]
0x18036294f  call    cs:__imp_??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180362955  add     rsp, 180h
0x18036295c  pop     r15
0x18036295e  pop     r14
0x180362960  pop     r13
0x180362962  pop     r12
0x180362964  pop     rdi
0x180362965  pop     rsi
0x180362966  pop     rbx
0x180362967  retn
0x180362968  mov     [rsp+1B8h+hSCManager], rsi
0x18036296d  mov     [rsp+1B8h+var_148], esi
0x180362971  lea     rcx, [rsp+1B8h+var_A8]
0x180362979  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x18036297f  lea     rax, ??_7CXXXXXHandledException@?5??SPProcessServiceEnable@@YAXPEBG0@Z@6B@; const `SPProcessServiceEnable(ushort const *,ushort const *)'::`6'::CXXXXXHandledException::`vftable'
0x180362986  mov     [rsp+1B8h+var_A8], rax
0x18036298e  test    r14, r14
0x180362991  jnz     loc_180362A1F
0x180362997  xor     edx, edx; lpDatabaseName
0x180362999  xor     ecx, ecx; lpMachineName
0x18036299b  mov     r8d, 0A0000000h; dwDesiredAccess
0x1803629a1  call    cs:__imp_OpenSCManagerW
0x1803629a7  mov     [rsp+1B8h+hSCManager], rax
0x1803629ac  test    rax, rax
0x1803629af  jnz     short loc_180362A1F
0x1803629b1  call    cs:__imp_GetLastError
0x1803629b7  mov     edi, eax
0x1803629b9  call    cs:__imp_CurrentIP
0x1803629bf  mov     rbx, rax
0x1803629c2  call    cs:__imp_GetLastError
0x1803629c8  mov     r8d, eax
0x1803629cb  lea     rdx, aFailedToOpenSe_1; "Failed to open service manager, won't b"...
0x1803629d2  mov     ecx, 2000000h; unsigned int
0x1803629d7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803629dc  mov     [rsp+1B8h+var_168], esi
0x1803629e0  mov     [rsp+1B8h+var_170], rsi
0x1803629e5  mov     [rsp+1B8h+var_178], edi
0x1803629e9  mov     [rsp+1B8h+var_180], rbx
0x1803629ee  mov     [rsp+1B8h+var_188], r12
0x1803629f3  lea     r14, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1803629fa  mov     [rsp+1B8h+var_190], r14
0x1803629ff  mov     [rsp+1B8h+var_198], 275h
0x180362a07  xor     r9d, r9d
0x180362a0a  lea     r8, aD_0; "D"
0x180362a11  mov     edx, r15d
0x180362a14  mov     rcx, rax
0x180362a17  call    cs:__imp_WdsSetupLogMessageW
0x180362a1d  jmp     short loc_180362A26
0x180362a1f  lea     r14, aBaseNtsetupSet_53; "base\\ntsetup\\setupplatform\\lib\\util"...
0x180362a26  lea     r8, aCurrent_0; "Current"
0x180362a2d  lea     rdx, aSelect; "Select"
0x180362a34  mov     rcx, r13
0x180362a37  call    RegGetDword
0x180362a3c  mov     [rsp+1B8h+var_138], eax
0x180362a43  mov     qword ptr [rsp+1B8h+var_110], rsi
0x180362a4b  mov     [rsp+1B8h+var_118], r13
0x180362a53  lea     rcx, [rsp+1B8h+var_118]; struct CONTROLSET_ENUM *
0x180362a5b  call    ?pSPEnumNextControlSet@@YAHPEAUCONTROLSET_ENUM@@@Z; pSPEnumNextControlSet(CONTROLSET_ENUM *)
0x180362a60  test    eax, eax
0x180362a62  jz      loc_18036311C
0x180362a68  mov     [rsp+1B8h+arg_18], esi
0x180362a6f  lea     rcx, [rsp+1B8h+var_70]
0x180362a77  call    _SPProcessServiceEnable____19___CXXXXXHandledException__CXXXXXHandledException
0x180362a7c  nop
0x180362a7d  call    cs:__imp_GetLastError
0x180362a83  mov     edi, eax
0x180362a85  call    cs:__imp_CurrentIP
0x180362a8b  mov     rbx, rax
0x180362a8e  mov     r8d, [rsp+1B8h+var_110+4]
0x180362a96  lea     rdx, aProcessingCont; "Processing ControlSet%03u"
0x180362a9d  mov     ecx, 4000000h; unsigned int
0x180362aa2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180362aa7  mov     [rsp+1B8h+var_168], esi
0x180362aab  mov     [rsp+1B8h+var_170], rsi
0x180362ab0  mov     [rsp+1B8h+var_178], edi
0x180362ab4  mov     [rsp+1B8h+var_180], rbx
0x180362ab9  mov     [rsp+1B8h+var_188], r12
0x180362abe  mov     [rsp+1B8h+var_190], r14
0x180362ac3  mov     [rsp+1B8h+var_198], 285h
0x180362acb  xor     r9d, r9d
0x180362ace  lea     r8, aD_0; "D"
0x180362ad5  mov     edx, r15d
0x180362ad8  mov     rcx, rax
0x180362adb  call    cs:__imp_WdsSetupLogMessageW
0x180362ae1  mov     rdi, [rsp+1B8h+arg_0]
0x180362ae9  mov     [rsp+1B8h+var_108], rdi
0x180362af1  test    rdi, rdi
0x180362af4  jz      loc_1803630D8
0x180362afa  cmp     [rdi], si
0x180362afd  jz      loc_1803630D8
0x180362b03  mov     ecx, 18h
0x180362b08  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180362b0e  mov     rbx, rax
0x180362b11  mov     [rsp+1B8h+arg_10], rax
0x180362b19  test    rax, rax
0x180362b1c  jz      short loc_180362B36
0x180362b1e  mov     rdx, rdi
0x180362b21  mov     rcx, rax
0x180362b24  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180362b2a  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180362b31  mov     [rbx], rax
0x180362b34  jmp     short loc_180362B39
0x180362b36  mov     rbx, rsi
0x180362b39  mov     r12d, esi
0x180362b3c  mov     rdx, rbx
0x180362b3f  lea     rcx, [rsp+1B8h+var_158]
0x180362b44  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180362b4a  nop
0x180362b4b  lea     rcx, [rsp+1B8h+var_158]
0x180362b50  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362b56  mov     edx, 2Ch ; ','
0x180362b5b  mov     rcx, rax
0x180362b5e  call    cs:__imp_?LastIndexOf@String@UnBCL@@QEBAHG@Z; UnBCL::String::LastIndexOf(ushort)
0x180362b64  mov     ebx, eax
0x180362b66  test    eax, eax
0x180362b68  jle     loc_180362CC5
0x180362b6e  lea     rcx, [rsp+1B8h+var_158]
0x180362b73  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362b79  lea     r8d, [rbx+1]
0x180362b7d  xor     edx, edx
0x180362b7f  mov     rcx, rax
0x180362b82  call    cs:__imp_?Remove@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Remove(int,int)
0x180362b88  mov     rdx, rax
0x180362b8b  lea     rcx, [rsp+1B8h+var_100]
0x180362b93  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180362b99  nop
0x180362b9a  lea     rcx, [rsp+1B8h+var_100]
0x180362ba2  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362ba8  mov     rcx, rax
0x180362bab  call    cs:__imp_?Trim@String@UnBCL@@QEBAPEAV12@XZ; UnBCL::String::Trim(void)
0x180362bb1  mov     rdx, rax
0x180362bb4  lea     rcx, [rsp+1B8h+var_E0]
0x180362bbc  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180362bc2  nop
0x180362bc3  lea     rdx, [rsp+1B8h+var_E0]
0x180362bcb  lea     rcx, [rsp+1B8h+var_100]
0x180362bd3  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180362bd9  nop
0x180362bda  lea     rcx, [rsp+1B8h+var_E0]
0x180362be2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180362be8  lea     rcx, [rsp+1B8h+var_100]
0x180362bf0  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362bf6  mov     rcx, rax
0x180362bf9  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180362bff  mov     r8d, 1
0x180362c05  lea     rdx, aForcerestart; "ForceRestart"
0x180362c0c  mov     rcx, rax
0x180362c0f  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x180362c15  test    eax, eax
0x180362c17  jnz     loc_180362CB7
0x180362c1d  lea     r12d, [rax+1]
0x180362c21  lea     rcx, [rsp+1B8h+var_158]
0x180362c26  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362c2c  mov     r8d, ebx
0x180362c2f  xor     edx, edx
0x180362c31  mov     rcx, rax
0x180362c34  call    cs:__imp_?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x180362c3a  mov     rdx, rax
0x180362c3d  lea     rcx, [rsp+1B8h+var_D0]
0x180362c45  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180362c4b  nop
0x180362c4c  lea     rdx, [rsp+1B8h+var_D0]
0x180362c54  lea     rcx, [rsp+1B8h+var_158]
0x180362c59  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180362c5f  nop
0x180362c60  lea     rcx, [rsp+1B8h+var_D0]
0x180362c68  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180362c6e  lea     rcx, [rsp+1B8h+var_158]
0x180362c73  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362c79  mov     rcx, rax
0x180362c7c  call    cs:__imp_?Trim@String@UnBCL@@QEBAPEAV12@XZ; UnBCL::String::Trim(void)
0x180362c82  mov     rdx, rax
0x180362c85  lea     rcx, [rsp+1B8h+var_C0]
0x180362c8d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180362c93  nop
0x180362c94  lea     rdx, [rsp+1B8h+var_C0]
0x180362c9c  lea     rcx, [rsp+1B8h+var_158]
0x180362ca1  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180362ca7  nop
0x180362ca8  lea     rcx, [rsp+1B8h+var_C0]
0x180362cb0  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180362cb6  nop
0x180362cb7  lea     rcx, [rsp+1B8h+var_100]
0x180362cbf  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180362cc5  call    cs:__imp_GetLastError
0x180362ccb  mov     edi, eax
0x180362ccd  call    cs:__imp_CurrentIP
0x180362cd3  mov     r14, rax
0x180362cd6  lea     rax, cchOriginalDestLength
0x180362cdd  lea     rbx, aForceStart; " (Force start)"
0x180362ce4  test    r12d, r12d
0x180362ce7  cmovz   rbx, rax
0x180362ceb  lea     rcx, [rsp+1B8h+var_158]
0x180362cf0  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180362cf6  mov     rcx, rax
0x180362cf9  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180362cff  mov     r9, rbx
0x180362d02  mov     r8, rax
0x180362d05  lea     rdx, aProcessingServ; "Processing service \"%s\"%s"
0x180362d0c  mov     ecx, 4000000h; unsigned int
  ... truncated ...
```
