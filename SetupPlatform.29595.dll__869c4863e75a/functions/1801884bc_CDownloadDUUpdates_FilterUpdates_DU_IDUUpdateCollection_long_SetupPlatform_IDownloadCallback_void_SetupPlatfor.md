# CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)

- ea: `0x1801884bc`
- end: `0x18018a2b0`
- name: `?FilterUpdates@CDownloadDUUpdates@@IEAAJPEAUIDUUpdateCollection@DU@@PEAJPEAUIDownloadCallback@SetupPlatform@@PEAXPEAUIDUDownloadProgress@5@PEAUITelemetry@@PEAUITelemetryActivity@@@Z`
- size: `7668`
- prototype: `void __fastcall __noreturn(CDownloadDUUpdates *__hidden this, struct DU::IDUUpdateCollection *, int *, struct SetupPlatform::IDownloadCallback *, void *, struct SetupPlatform::IDUDownloadProgress *, struct ITelemetry *, struct ITelemetryActivity *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180184d3c`

## callees

- `0x180013804`
- `0x18001413d`
- `0x180044820`
- `0x180057dec`
- `0x1801884bc`
- `0x18018b5e4`
- `0x1803f2ca0`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018863f`
- `KERNEL32!GetLastError` at `0x18018891a`
- `KERNEL32!GetLastError` at `0x1801889b8`
- `KERNEL32!GetLastError` at `0x180188a2c`
- `KERNEL32!GetLastError` at `0x180188aba`
- `KERNEL32!GetLastError` at `0x180188b1b`
- `KERNEL32!GetLastError` at `0x180188b8f`
- `KERNEL32!GetLastError` at `0x180188c23`
- `KERNEL32!GetLastError` at `0x180188cb7`
- `KERNEL32!GetLastError` at `0x180188d4b`
- `KERNEL32!GetLastError` at `0x180188e25`
- `KERNEL32!GetLastError` at `0x1801891a4`
- `KERNEL32!GetLastError` at `0x180189218`
- `KERNEL32!GetLastError` at `0x180189294`
- `KERNEL32!GetLastError` at `0x1801893e4`
- `KERNEL32!GetLastError` at `0x1801894a0`
- `KERNEL32!GetLastError` at `0x1801896a1`
- `KERNEL32!GetLastError` at `0x180189740`
- `KERNEL32!GetLastError` at `0x1801897e3`
- `KERNEL32!GetLastError` at `0x180189887`
- `KERNEL32!GetLastError` at `0x18018992b`
- `KERNEL32!GetLastError` at `0x1801899cf`
- `KERNEL32!GetLastError` at `0x180189a73`
- `KERNEL32!GetLastError` at `0x180189b16`
- `KERNEL32!GetLastError` at `0x180189bb9`
- `KERNEL32!GetLastError` at `0x180189c5c`
- `KERNEL32!GetLastError` at `0x180189cff`
- `KERNEL32!GetLastError` at `0x180189da2`
- `KERNEL32!GetLastError` at `0x180189e46`
- `KERNEL32!GetLastError` at `0x180189ee2`
- `KERNEL32!GetLastError` at `0x180189f82`
- `KERNEL32!GetLastError` at `0x18018a04f`
- `KERNEL32!GetLastError` at `0x18018a103`
- `KERNEL32!GetLastError` at `0x18018a1da`
- `KERNEL32!GetLastError` at `0x18018863f`
- `KERNEL32!GetLastError` at `0x18018891a`
- `KERNEL32!GetLastError` at `0x1801889b8`
- `KERNEL32!GetLastError` at `0x180188a2c`
- `KERNEL32!GetLastError` at `0x180188aba`
- `KERNEL32!GetLastError` at `0x180188b1b`
- `KERNEL32!GetLastError` at `0x180188b8f`
- `KERNEL32!GetLastError` at `0x180188c23`
- `KERNEL32!GetLastError` at `0x180188cb7`
- `KERNEL32!GetLastError` at `0x180188d4b`
- `KERNEL32!GetLastError` at `0x180188e25`
- `KERNEL32!GetLastError` at `0x1801891a4`
- `KERNEL32!GetLastError` at `0x180189218`
- `KERNEL32!GetLastError` at `0x180189294`
- `KERNEL32!GetLastError` at `0x1801893e4`
- `KERNEL32!GetLastError` at `0x1801894a0`
- `KERNEL32!GetLastError` at `0x1801896a1`
- `KERNEL32!GetLastError` at `0x180189740`
- `KERNEL32!GetLastError` at `0x1801897e3`
- `KERNEL32!GetLastError` at `0x180189887`
- `KERNEL32!GetLastError` at `0x18018992b`
- `KERNEL32!GetLastError` at `0x1801899cf`
- `KERNEL32!GetLastError` at `0x180189a73`
- `KERNEL32!GetLastError` at `0x180189b16`
- `KERNEL32!GetLastError` at `0x180189bb9`
- `KERNEL32!GetLastError` at `0x180189c5c`
- `KERNEL32!GetLastError` at `0x180189cff`
- `KERNEL32!GetLastError` at `0x180189da2`
- `KERNEL32!GetLastError` at `0x180189e46`
- `KERNEL32!GetLastError` at `0x180189ee2`
- `KERNEL32!GetLastError` at `0x180189f82`
- `KERNEL32!GetLastError` at `0x18018a04f`
- `KERNEL32!GetLastError` at `0x18018a103`
- `KERNEL32!GetLastError` at `0x18018a1da`
- `KERNEL32!CompareStringW` at `0x180189153`
- `KERNEL32!CompareStringW` at `0x180189186`
- `KERNEL32!CompareStringW` at `0x180189153`
- `KERNEL32!CompareStringW` at `0x180189186`
- `KERNEL32!SystemTimeToFileTime` at `0x1801890d4`
- `KERNEL32!SystemTimeToFileTime` at `0x1801890e7`
- `KERNEL32!SystemTimeToFileTime` at `0x1801890d4`
- `KERNEL32!SystemTimeToFileTime` at `0x1801890e7`
- `KERNEL32!CompareFileTime` at `0x1801890fa`
- `KERNEL32!CompareFileTime` at `0x1801890fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18018959c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18018959c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801895d8`
- `OLEAUT32!__imp_SysStringLen` at `0x180188ba8`
- `OLEAUT32!__imp_SysStringLen` at `0x180188c3c`
- `OLEAUT32!__imp_SysStringLen` at `0x180188cd0`
- `OLEAUT32!__imp_SysStringLen` at `0x180188d64`
- `OLEAUT32!__imp_SysStringLen` at `0x180188ba8`
- `OLEAUT32!__imp_SysStringLen` at `0x180188c3c`
- `OLEAUT32!__imp_SysStringLen` at `0x180188cd0`
- `OLEAUT32!__imp_SysStringLen` at `0x180188d64`
- `OLEAUT32!__imp_VarBstrFromDate` at `0x1801888f3`
- `OLEAUT32!__imp_VarBstrFromDate` at `0x1801888f3`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801888c9`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801888c9`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18018855e`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18018855e`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180189664`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180189664`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801892c1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180189411`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801894cd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801892c1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180189411`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801894cd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801892ca`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018941a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801894d6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801892ca`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018941a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801894d6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180189338`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018948f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180189544`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180189338`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018948f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180189544`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801892b7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180189407`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801894c3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801892b7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180189407`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801894c3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801886aa`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188993`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188a26`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188aa2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188b89`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188c1d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188cb1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188d45`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188dd9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188e8c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189212`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189280`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189329`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189480`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189535`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018970d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801897b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189854`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801898f8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018999c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189a40`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189ae4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189b87`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189c2a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189ccd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189d70`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189e13`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189eb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189f53`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189fec`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018a0c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018a174`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018a244`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801886aa`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188993`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188a26`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188aa2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188b89`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188c1d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188cb1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188d45`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188dd9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180188e8c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189212`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189280`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189329`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189480`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189535`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018970d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801897b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189854`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801898f8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018999c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189a40`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189ae4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189b87`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189c2a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189ccd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189d70`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189e13`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189eb0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189f53`
- `WDSCORE!WdsSetupLogMessageW` at `0x180189fec`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018a0c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018a174`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018a244`
- `WDSCORE!CurrentIP` at `0x180188647`
- `WDSCORE!CurrentIP` at `0x180188922`
- `WDSCORE!CurrentIP` at `0x1801889c0`
- `WDSCORE!CurrentIP` at `0x180188a34`
- `WDSCORE!CurrentIP` at `0x180188ac2`
- `WDSCORE!CurrentIP` at `0x180188b23`

## string_xrefs

- `0x180188684`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018896d`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188a00`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188a7c`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188b02`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188b63`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188bf7`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188c8b`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188d1f`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188db3`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188e66`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801891ec`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189303`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018945a`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018950f`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801896e7`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018978b`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018982e`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801898d2`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189976`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189a1a`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189abe`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189b61`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189c04`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189ca7`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189d4a`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189ded`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189e8a`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189f2d`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180189fc6`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018a0a2`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018a14e`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018a21e`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180188678`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188961`: `CDownloadDUUpdates::FilterUpdates`
- `0x1801889f4`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188a70`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188af6`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188b57`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188beb`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188c7f`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188d13`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188da7`: `CDownloadDUUpdates::FilterUpdates`
- `0x180188e5a`: `CDownloadDUUpdates::FilterUpdates`
- `0x1801891e0`: `CDownloadDUUpdates::FilterUpdates`
- `0x18018928d`: `CDownloadDUUpdates::FilterUpdates`
- `0x18018944e`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189499`: `CDownloadDUUpdates::FilterUpdates`
- `0x1801896db`: `CDownloadDUUpdates::FilterUpdates`
- `0x18018977f`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189822`: `CDownloadDUUpdates::FilterUpdates`
- `0x1801898c6`: `CDownloadDUUpdates::FilterUpdates`
- `0x18018996a`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189a0e`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189ab2`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189b55`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189bf8`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189c9b`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189d3e`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189de1`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189e7e`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189f21`: `CDownloadDUUpdates::FilterUpdates`
- `0x180189fba`: `CDownloadDUUpdates::FilterUpdates`
- `0x18018a096`: `CDownloadDUUpdates::FilterUpdates`
- `0x18018a142`: `CDownloadDUUpdates::FilterUpdates`
- `0x1801896b8`: `CDownloadDUUpdates::FilterUpdates: Cancelled. hr = 0x%x`
- `0x180188653`: `CDownloadDUUpdates::FilterUpdates: Skipping update at index %d; it cannot be filtered`
- `0x18018989b`: `CDownloadDUUpdates::FilterUpdates: IDUUpdate::GetWUAInterface failed. hr = 0x%x`
- `0x180189754`: `CDownloadDUUpdates::FilterUpdates: IDUUpdateCollection::GetItem failed. hr = 0x%x`
- `0x1801897f7`: `CDownloadDUUpdates::FilterUpdates: IDUUpdate::GetType failed. hr = 0x%x`
- `0x180189a87`: `CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverClass failed. hr = 0x%x`
- `0x180189b2a`: `CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverHardwareID failed. hr = 0x%x`
- `0x18018993f`: `CDownloadDUUpdates::FilterUpdates: IUpdate::get_Identity failed. hr = 0x%x`
- `0x1801899e3`: `CDownloadDUUpdates::FilterUpdates: IUpdateIdentity::get_UpdateID failed. hr = 0x%x`
- `0x180189d13`: `CDownloadDUUpdates::FilterUpdates: VariantTimeToSystemTime failed. hr = 0x%x`
- `0x180189db6`: `CDownloadDUUpdates::FilterUpdates: VarBstrFromDate failed. hr = 0x%x`
- `0x180189bcd`: `CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverManufacturer failed. hr = 0x%x`
- `0x180189c70`: `CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverVerDate failed. hr = 0x%x`
- `0x180188acb`: `    Type: Component`
- `0x180188936`: `CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate not available for update %s, will not filter. hr = 0x%x`
- `0x1801889c9`: `  Deciding dynamic update download on update:`
- `0x180188e36`: `Opening DISM session for the source system (Online)`
- `0x180189e5a`: `CDownloadDUUpdates::FilterUpdates: Failed to initialize DISM. Error: 0x%08X`
- `0x18018a117`: `CDownloadDUUpdates::FilterUpdates: Allocation of DISM driver arrays failed. hr = 0x%x`
- `0x180189efd`: `Failed to open DISM session: (%s). Error: 0x%08X`
- `0x1801892d3`: `  Initial decision for this update: %s`
- `0x1801894df`: `  Final decision for the update: %s`
- `0x18018a1ee`: `Failed to remove update item from update collection. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall __noreturn CDownloadDUUpdates::FilterUpdates(
        CDownloadDUUpdates *this,
        struct DU::IDUUpdateCollection *a2,
        int *a3,
        struct SetupPlatform::IDownloadCallback *a4,
        void *a5,
        struct SetupPlatform::IDUDownloadProgress *a6,
        struct ITelemetry *a7,
        struct ITelemetryActivity *a8)
{
  struct DU::IDUUpdateCollection *v9; // rdi
  void *v10; // rbx
  _QWORD *v11; // r13
  _DWORD *v12; // r12
  int v13; // r14d
  unsigned int v14; // r15d
  __int64 (__fastcall *v15)(struct DU::IDUUpdateCollection *, _QWORD, __int64); // rbx
  __int64 v16; // rax
  int v17; // esi
  __int64 v18; // rax
  int v19; // esi
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  __int64 v23; // rax
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // r14d
  int v28; // esi
  int v29; // esi
  int v30; // esi
  int v31; // esi
  int v32; // esi
  HRESULT v33; // esi
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  unsigned int v37; // esi
  DWORD v38; // edi
  __int64 v39; // rbx
  struct tagLOG_PARTIAL_MSG *v40; // rax
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
  UINT v52; // eax
  BSTR v53; // r8
  struct tagLOG_PARTIAL_MSG *v54; // rax
  DWORD v55; // edi
  __int64 v56; // rbx
  UINT v57; // eax
  BSTR v58; // r8
  struct tagLOG_PARTIAL_MSG *v59; // rax
  DWORD v60; // edi
  __int64 v61; // rbx
  UINT v62; // eax
  BSTR v63; // r8
  struct tagLOG_PARTIAL_MSG *v64; // rax
  DWORD v65; // edi
  __int64 v66; // rbx
  UINT v67; // eax
  BSTR v68; // r8
  int v69; // r14d
  DWORD v70; // edi
  __int64 v71; // rbx
  struct tagLOG_PARTIAL_MSG *v72; // rax
  int v73; // r14d
  int Drivers; // r14d
  _DWORD *v75; // rax
  unsigned int i; // ecx
  unsigned int v77; // ebx
  void *v78; // rdi
  __int64 v79; // rcx
  __m128i v80; // xmm2
  int v81; // r14d
  unsigned int j; // edi
  __int64 v83; // rcx
  int v84; // ebx
  __int64 v85; // rcx
  __int64 v86; // r8
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  DWORD v90; // edi
  __int64 v91; // rbx
  struct tagLOG_PARTIAL_MSG *v92; // rax
  DWORD v93; // ebx
  __int64 v94; // rdi
  __int64 AnswerString; // rax
  __int64 v96; // rax
  UnBCL::String *P; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v99; // rax
  unsigned int v100; // ebx
  BSTR v101; // r8
  BSTR v102; // r9
  BSTR v103; // rax
  _SYSTEMTIME *p_SystemTime; // rcx
  DWORD v105; // edi
  __int64 v106; // rsi
  __int64 v107; // rax
  __int64 v108; // rax
  UnBCL::String *v109; // rax
  const char *v110; // rax
  struct tagLOG_PARTIAL_MSG *v111; // rax
  DWORD v112; // ebx
  __int64 v113; // rdi
  __int64 v114; // rax
  __int64 v115; // rax
  UnBCL::String *v116; // rax
  const char *v117; // rax
  struct tagLOG_PARTIAL_MSG *v118; // rax
  int v119; // esi
  DWORD LastError; // edi
  __int64 v121; // rbx
  struct tagLOG_PARTIAL_MSG *v122; // rax
  DWORD v123; // edi
  __int64 v124; // rbx
  struct tagLOG_PARTIAL_MSG *v125; // rax
  DWORD v126; // edi
  __int64 v127; // rbx
  struct tagLOG_PARTIAL_MSG *v128; // rax
  DWORD v129; // edi
  __int64 v130; // rbx
  struct tagLOG_PARTIAL_MSG *v131; // rax
  DWORD v132; // edi
  __int64 v133; // rbx
  struct tagLOG_PARTIAL_MSG *v134; // rax
  DWORD v135; // edi
  __int64 v136; // rbx
  struct tagLOG_PARTIAL_MSG *v137; // rax
  DWORD v138; // edi
  __int64 v139; // rbx
  struct tagLOG_PARTIAL_MSG *v140; // rax
  DWORD v141; // edi
  __int64 v142; // rbx
  struct tagLOG_PARTIAL_MSG *v143; // rax
  DWORD v144; // edi
  __int64 v145; // rbx
  struct tagLOG_PARTIAL_MSG *v146; // rax
  DWORD v147; // edi
  __int64 v148; // rbx
  struct tagLOG_PARTIAL_MSG *v149; // rax
  DWORD v150; // edi
  __int64 v151; // rbx
  struct tagLOG_PARTIAL_MSG *v152; // rax
  DWORD v153; // edi
  __int64 v154; // rbx
  struct tagLOG_PARTIAL_MSG *v155; // rax
  DWORD v156; // edi
  __int64 v157; // rbx
  struct tagLOG_PARTIAL_MSG *v158; // rax
  DWORD v159; // edi
  __int64 v160; // rbx
  struct tagLOG_PARTIAL_MSG *v161; // rax
  DWORD v162; // edi
  __int64 v163; // rbx
  struct tagLOG_PARTIAL_MSG *v164; // rax
  DWORD v165; // edi
  __int64 v166; // rbx
  struct tagLOG_PARTIAL_MSG *v167; // rax
  DWORD v168; // edi
  __int64 v169; // rbx
  struct tagLOG_PARTIAL_MSG *v170; // rax
  DWORD v171; // edi
  __int64 v172; // rbx
  struct tagLOG_PARTIAL_MSG *v173; // rax
  __int64 *v174; // rbp
  _QWORD *v175; // rdi
  unsigned int v176; // ebx
  unsigned int v177; // edx
  void *v178; // rcx
  __int64 *v179; // rdx
  __int64 v180; // [rsp+0h] [rbp-318h] BYREF
  PCNZWCH lpString2; // [rsp+20h] [rbp-2F8h]
  int cchCount2[2]; // [rsp+28h] [rbp-2F0h]
  const wchar_t *v183; // [rsp+30h] [rbp-2E8h]
  __int64 v184; // [rsp+38h] [rbp-2E0h]
  DWORD v185; // [rsp+40h] [rbp-2D8h]
  __int64 v186; // [rsp+48h] [rbp-2D0h]
  int v187; // [rsp+50h] [rbp-2C8h]
  int v188; // [rsp+60h] [rbp-2B8h]
  int v189; // [rsp+64h] [rbp-2B4h]
  unsigned int v190; // [rsp+68h] [rbp-2B0h] BYREF
  int v191; // [rsp+6Ch] [rbp-2ACh] BYREF
  unsigned int v192; // [rsp+70h] [rbp-2A8h] BYREF
  FILETIME FileTime2; // [rsp+78h] [rbp-2A0h] BYREF
  int v194; // [rsp+80h] [rbp-298h]
  __int64 v195; // [rsp+88h] [rbp-290h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-288h] BYREF
  BSTR v197; // [rsp+98h] [rbp-280h] BYREF
  BSTR v198; // [rsp+A0h] [rbp-278h] BYREF
  struct _FILETIME FileTime; // [rsp+A8h] [rbp-270h] BYREF
  void **v200; // [rsp+B0h] [rbp-268h] BYREF
  void (__fastcall ***v201)(_QWORD); // [rsp+B8h] [rbp-260h]
  int v202; // [rsp+C0h] [rbp-258h]
  int v203; // [rsp+C4h] [rbp-254h]
  BSTR pbstr; // [rsp+C8h] [rbp-250h] BYREF
  BSTR pbstrOut; // [rsp+D0h] [rbp-248h] BYREF
  __int64 v206; // [rsp+D8h] [rbp-240h] BYREF
  DOUBLE vtime; // [rsp+E0h] [rbp-238h] BYREF
  __int64 v208; // [rsp+E8h] [rbp-230h] BYREF
  void *v209; // [rsp+F0h] [rbp-228h]
  _QWORD v210[7]; // [rsp+F8h] [rbp-220h] BYREF
  struct DU::IDUUpdateCollection *v211; // [rsp+130h] [rbp-1E8h]
  _QWORD *v212; // [rsp+138h] [rbp-1E0h]
  void *v213; // [rsp+140h] [rbp-1D8h]
  _QWORD *v214; // [rsp+148h] [rbp-1D0h] BYREF
  _QWORD *v215; // [rsp+150h] [rbp-1C8h] BYREF
  _QWORD *v216; // [rsp+158h] [rbp-1C0h] BYREF
  _QWORD *v217; // [rsp+160h] [rbp-1B8h] BYREF
  _QWORD *v218; // [rsp+168h] [rbp-1B0h] BYREF
  _QWORD *v219; // [rsp+170h] [rbp-1A8h] BYREF
  _QWORD *v220; // [rsp+178h] [rbp-1A0h] BYREF
  _QWORD *v221; // [rsp+180h] [rbp-198h] BYREF
  _QWORD *v222; // [rsp+188h] [rbp-190h] BYREF
  _QWORD *v223; // [rsp+190h] [rbp-188h] BYREF
  _QWORD *v224; // [rsp+198h] [rbp-180h] BYREF
  _QWORD *v225; // [rsp+1A0h] [rbp-178h] BYREF
  _QWORD *v226; // [rsp+1A8h] [rbp-170h] BYREF
  _QWORD *v227; // [rsp+1B0h] [rbp-168h] BYREF
  _QWORD *v228; // [rsp+1B8h] [rbp-160h] BYREF
  _QWORD *v229; // [rsp+1C0h] [rbp-158h] BYREF
  _QWORD *pExceptionObject; // [rsp+1C8h] [rbp-150h] BYREF
  struct SetupPlatform::IDownloadCallback *v231; // [rsp+1D0h] [rbp-148h]
  _QWORD *v232; // [rsp+1D8h] [rbp-140h] BYREF
  int *v233; // [rsp+1E0h] [rbp-138h]
  _QWORD *v234; // [rsp+1E8h] [rbp-130h] BYREF
  _QWORD *v235; // [rsp+1F0h] [rbp-128h] BYREF
  _QWORD *v236; // [rsp+1F8h] [rbp-120h] BYREF
  _BYTE v237[16]; // [rsp+200h] [rbp-118h] BYREF
  _BYTE v238[16]; // [rsp+210h] [rbp-108h] BYREF
  _BYTE v239[16]; // [rsp+220h] [rbp-F8h] BYREF
  __int64 v240; // [rsp+230h] [rbp-E8h]
  __int128 v241; // [rsp+240h] [rbp-D8h]
  __int128 v242; // [rsp+250h] [rbp-C8h]
  __int128 v243; // [rsp+260h] [rbp-B8h]
  __int128 v244; // [rsp+270h] [rbp-A8h]
  SYSTEMTIME v245; // [rsp+280h] [rbp-98h] BYREF
  __int128 v246; // [rsp+290h] [rbp-88h]
  int v247; // [rsp+2A0h] [rbp-78h]
  _SYSTEMTIME SystemTime; // [rsp+2B0h] [rbp-68h] BYREF

  v240 = -2;
  v231 = a4;
  v233 = a3;
  v9 = a2;
  v211 = a2;
  v10 = a5;
  v209 = a5;
  v189 = 0;
  v202 = 0;
  v192 = 0;
  v195 = 0;
  v190 = 0;
  v11 = 0;
  v212 = 0;
  v12 = 0;
  v213 = 0;
  v188 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v210);
  v210[0] = &`CDownloadDUUpdates::FilterUpdates'::`3'::CXXXXXHandledException::`vftable';
  v13 = *a3;
  v194 = *a3;
  v14 = 0;
  try
  {
    try
    {
      while ( 1 )
      {
        if ( (int)v14 >= v13 )
        {
          *v233 = v13;
          v188 = 1;
          v234 = v210;
          goto LABEL_123;
        }
        if ( (unsigned int)SPIsEventSet(v10) )
        {
          v189 = -2147023673;
          LastError = GetLastError();
          v121 = CurrentIP();
          v122 = ConstructPartialMsgW(
                   0x2000000u,
                   "CDownloadDUUpdates::FilterUpdates: Cancelled. hr = 0x%x",
                   -2147023673);
          WdsSetupLogMessageW(
            v122,
            819200,
            L"D",
            0,
            3029,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v121,
            LastError,
            0,
            0);
          v188 = 1;
          pExceptionObject = v210;
          throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&pExceptionObject;
        }
        v201 = 0;
        v200 = &RAII::CAutoRelease<DU::IDUUpdate *>::`vftable';
        v15 = *(__int64 (__fastcall **)(struct DU::IDUUpdateCollection *, _QWORD, __int64))(*(_QWORD *)v9 + 8LL);
        v16 = RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v200);
        v17 = v15(v9, v14, v16);
        v189 = v17;
        if ( v17 < 0 )
        {
          v123 = GetLastError();
          v124 = CurrentIP();
          v125 = ConstructPartialMsgW(
                   0x2000000u,
                   "CDownloadDUUpdates::FilterUpdates: IDUUpdateCollection::GetItem failed. hr = 0x%x",
                   v17);
          WdsSetupLogMessageW(
            v125,
            819200,
            L"D",
            0,
            3037,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v124,
            v123,
            0,
            0);
          v188 = 1;
          v236 = v210;
          throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v236;
        }
        v191 = 0;
        v18 = ((__int64 (__fastcall *)(void ***))v200[3])(&v200);
        v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 8LL))(v18, &v191);
        v189 = v19;
        if ( v19 < 0 )
        {
          v126 = GetLastError();
          v127 = CurrentIP();
          v128 = ConstructPartialMsgW(
                   0x2000000u,
                   "CDownloadDUUpdates::FilterUpdates: IDUUpdate::GetType failed. hr = 0x%x",
                   v19);
          WdsSetupLogMessageW(
            v128,
            819200,
            L"D",
            0,
            3045,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v127,
            v126,
            0,
            0);
          v188 = 1;
          v214 = v210;
          throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v214;
        }
        if ( ((v191 - 2) & 0xFFFFFFFD) != 0 )
        {
          v20 = GetLastError();
          v21 = CurrentIP();
          v22 = ConstructPartialMsgW(
                  0x4000000u,
                  "CDownloadDUUpdates::FilterUpdates: Skipping update at index %d; it cannot be filtered",
                  v14);
          WdsSetupLogMessageW(
            v22,
            819200,
            L"D",
            0,
            3053,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v21,
            v20,
            0,
            0);
          v200 = &RAII::CAutoRelease<DU::IDUUpdate *>::`vftable';
          if ( v201 )
          {
            (**v201)(v201);
            v201 = 0;
          }
          goto LABEL_82;
        }
        v206 = 0;
        v23 = ((__int64 (__fastcall *)(void ***))v200[3])(&v200);
        v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 32LL))(v23, &v206);
        v189 = v24;
        if ( v24 < 0 )
        {
          v129 = GetLastError();
          v130 = CurrentIP();
          v131 = ConstructPartialMsgW(
                   0x2000000u,
                   "CDownloadDUUpdates::FilterUpdates: IDUUpdate::GetWUAInterface failed. hr = 0x%x",
                   v24);
          WdsSetupLogMessageW(
            v131,
            819200,
            L"D",
            0,
            3061,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v130,
            v129,
            0,
            0);
          v188 = 1;
          v215 = v210;
          throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v215;
        }
        v208 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v206 + 152LL))(v206, &v208);
        v189 = v25;
        if ( v25 < 0 )
        {
          v132 = GetLastError();
          v133 = CurrentIP();
          v134 = ConstructPartialMsgW(
                   0x2000000u,
                   "CDownloadDUUpdates::FilterUpdates: IUpdate::get_Identity failed. hr = 0x%x",
                   v25);
          WdsSetupLogMessageW(
            v134,
            819200,
            L"D",
            0,
            3069,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v133,
            v132,
            0,
            0);
          v188 = 1;
          v216 = v210;
          throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v216;
        }
        v198 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v208 + 64LL))(v208, &v198);
        v189 = v26;
        if ( v26 < 0 )
        {
          v135 = GetLastError();
          v136 = CurrentIP();
          v137 = ConstructPartialMsgW(
                   0x2000000u,
                   "CDownloadDUUpdates::FilterUpdates: IUpdateIdentity::get_UpdateID failed. hr = 0x%x",
                   v26);
          WdsSetupLogMessageW(
            v137,
            819200,
            L"D",
            0,
            3077,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v136,
            v135,
            0,
            0);
          v188 = 1;
          v217 = v210;
          throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v217;
        }
        pbstr = 0;
        v197 = 0;
        bstrString = 0;
        SystemTime = 0;
        pbstrOut = 0;
        v27 = 0;
        v203 = 0;
        if ( v191 == 2 )
        {
          FileTime2 = 0;
          v28 = (**(__int64 (__fastcall ***)(__int64, GUID *, FILETIME *))v206)(
                  v206,
                  &GUID_b383cd1a_5ce9_4504_9f63_764b1236f191,
                  &FileTime2);
          v189 = v28;
          if ( v28 < 0 )
          {
            v34 = GetLastError();
            v35 = CurrentIP();
            v36 = ConstructPartialMsgW(
                    0x3000000u,
                    "CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate not available for update %s, will not filter. hr = 0x%x",
                    (const char *)v198,
                    v28);
            WdsSetupLogMessageW(
              v36,
              819200,
              L"D",
              0,
              3141,
              L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
              L"CDownloadDUUpdates::FilterUpdates",
              v35,
              v34,
              0,
              0);
            v189 = 0;
          }
          else
          {
            v29 = (*(__int64 (__fastcall **)(FILETIME, BSTR *))(**(_QWORD **)&FileTime2 + 416LL))(FileTime2, &pbstr);
            v189 = v29;
            if ( v29 < 0 )
            {
              v138 = GetLastError();
              v139 = CurrentIP();
              v140 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverClass failed. hr = 0x%x",
                       v29);
              WdsSetupLogMessageW(
                v140,
                819200,
                L"D",
                0,
                3096,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v139,
                v138,
                0,
                0);
              v188 = 1;
              v218 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v218;
            }
            v30 = (*(__int64 (__fastcall **)(FILETIME, BSTR *))(**(_QWORD **)&FileTime2 + 424LL))(FileTime2, &v197);
            v189 = v30;
            if ( v30 < 0 )
            {
              v141 = GetLastError();
              v142 = CurrentIP();
              v143 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverHardwareID failed. hr = 0x%x",
                       v30);
              WdsSetupLogMessageW(
                v143,
                819200,
                L"D",
                0,
                3103,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v142,
                v141,
                0,
                0);
              v188 = 1;
              v219 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v219;
            }
            v31 = (*(__int64 (__fastcall **)(FILETIME, BSTR *))(**(_QWORD **)&FileTime2 + 432LL))(
                    FileTime2,
                    &bstrString);
            v189 = v31;
            if ( v31 < 0 )
            {
              v144 = GetLastError();
              v145 = CurrentIP();
              v146 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverManufacturer failed. hr = 0x%x",
                       v31);
              WdsSetupLogMessageW(
                v146,
                819200,
                L"D",
                0,
                3110,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v145,
                v144,
                0,
                0);
              v188 = 1;
              v220 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v220;
            }
            vtime = 0.0;
            v32 = (*(__int64 (__fastcall **)(FILETIME, DOUBLE *))(**(_QWORD **)&FileTime2 + 456LL))(FileTime2, &vtime);
            v189 = v32;
            if ( v32 < 0 )
            {
              v147 = GetLastError();
              v148 = CurrentIP();
              v149 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: IWindowsDriverUpdate::get_DriverVerDate failed. hr = 0x%x",
                       v32);
              WdsSetupLogMessageW(
                v149,
                819200,
                L"D",
                0,
                3118,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v148,
                v147,
                0,
                0);
              v188 = 1;
              v221 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v221;
            }
            if ( !VariantTimeToSystemTime(vtime, &SystemTime) )
            {
              v150 = GetLastError();
              v151 = CurrentIP();
              v152 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: VariantTimeToSystemTime failed. hr = 0x%x",
                       v32);
              WdsSetupLogMessageW(
                v152,
                819200,
                L"D",
                0,
                3124,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v151,
                v150,
                0,
                0);
              v188 = 1;
              v222 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v222;
            }
            v33 = VarBstrFromDate(vtime, 0x409u, 0x40u, &pbstrOut);
            v189 = v33;
            if ( v33 < 0 )
            {
              v153 = GetLastError();
              v154 = CurrentIP();
              v155 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: VarBstrFromDate failed. hr = 0x%x",
                       v33);
              WdsSetupLogMessageW(
                v155,
                819200,
                L"D",
                0,
                3132,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v154,
                v153,
                0,
                0);
              v188 = 1;
              v223 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v223;
            }
            v27 = 1;
            v203 = 1;
          }
          if ( FileTime2 )
            (*(void (__fastcall **)(FILETIME))(**(_QWORD **)&FileTime2 + 16LL))(FileTime2);
        }
        v37 = 0;
        v38 = GetLastError();
        v39 = CurrentIP();
        v40 = ConstructPartialMsgW(0x4000000u, "  Deciding dynamic update download on update:");
        WdsSetupLogMessageW(
          v40,
          819200,
          L"D",
          0,
          3148,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::FilterUpdates",
          v39,
          v38,
          0,
          0);
        v41 = GetLastError();
        v42 = CurrentIP();
        v43 = ConstructPartialMsgW(0x4000000u, "    Id: %s", (const char *)v198);
        WdsSetupLogMessageW(
          v43,
          819200,
          L"D",
          0,
          3149,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::FilterUpdates",
          v42,
          v41,
          0,
          0);
        if ( v191 == 2 )
          break;
        if ( v191 == 4 )
        {
          v44 = GetLastError();
          v45 = CurrentIP();
          v46 = ConstructPartialMsgW(0x4000000u, "    Type: Component");
          v187 = 0;
          v186 = 0;
          v185 = v44;
          v184 = v45;
          v183 = L"CDownloadDUUpdates::FilterUpdates";
          *(_QWORD *)cchCount2 = L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp";
          LODWORD(lpString2) = 3153;
LABEL_37:
          WdsSetupLogMessageW(
            v46,
            819200,
            L"D",
            0,
            (_DWORD)lpString2,
            *(_QWORD *)cchCount2,
            v183,
            v184,
            v185,
            v186,
            v187);
        }
        if ( v27 )
        {
          if ( !v195 )
          {
            v69 = DismInitialize(2, 0, 0);
            v189 = v69;
            if ( v69 < 0 )
            {
              v156 = GetLastError();
              v157 = CurrentIP();
              v158 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: Failed to initialize DISM. Error: 0x%08X",
                       v69);
              WdsSetupLogMessageW(
                v158,
                819200,
                L"D",
                0,
                3185,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v157,
                v156,
                0,
                0);
              v188 = 1;
              v224 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v224;
            }
            v202 = 1;
            v70 = GetLastError();
            v71 = CurrentIP();
            v72 = ConstructPartialMsgW(0x4000000u, "Opening DISM session for the source system (Online)");
            WdsSetupLogMessageW(
              v72,
              819200,
              L"D",
              0,
              3190,
              L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
              L"CDownloadDUUpdates::FilterUpdates",
              v71,
              v70,
              0,
              0);
            v73 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v192);
            v189 = v73;
            if ( v73 < 0 )
            {
              v159 = GetLastError();
              v160 = CurrentIP();
              v161 = ConstructPartialMsgW(
                       0x2000000u,
                       "Failed to open DISM session: (%s). Error: 0x%08X",
                       (const char *)L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}",
                       v73);
              WdsSetupLogMessageW(
                v161,
                819200,
                L"D",
                0,
                3195,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v160,
                v159,
                0,
                0);
              v188 = 1;
              v225 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v225;
            }
            Drivers = DismGetDrivers(v192, 0, &v195, &v190);
            v189 = Drivers;
            if ( Drivers < 0 )
            {
              v162 = GetLastError();
              v163 = CurrentIP();
              v164 = ConstructPartialMsgW(
                       0x2000000u,
                       "Failed to get driver packages from the online system. Error: 0x%08X",
                       Drivers);
              WdsSetupLogMessageW(
                v164,
                819200,
                L"D",
                0,
                3203,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v163,
                v162,
                0,
                0);
              v188 = 1;
              v226 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v226;
            }
            v11 = operator new[](saturated_mul(v190, 8u));
            v212 = v11;
            v75 = operator new[](saturated_mul(v190, 4u));
            v12 = v75;
            v213 = v75;
            if ( !v11 || !v75 )
            {
              v189 = -2147024882;
              v168 = GetLastError();
              v169 = CurrentIP();
              v170 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::FilterUpdates: Allocation of DISM driver arrays failed. hr = 0x%x",
                       -2147024882);
              WdsSetupLogMessageW(
                v170,
                819200,
                L"D",
                0,
                3213,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::FilterUpdates",
                v169,
                v168,
                0,
                0);
              v188 = 1;
              v229 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v229;
            }
            for ( i = 0; i < v190; ++i )
              v11[i] = 0;
            v77 = 0;
            v78 = v209;
            while ( v77 < v190 )
            {
              if ( (unsigned int)SPIsEventSet(v78) )
              {
                v189 = -2147023673;
                v188 = 1;
                v227 = v210;
                throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v227;
              }
              v79 = 100LL * (int)v77;
              v80 = *(__m128i *)(v79 + v195);
              v242 = *(_OWORD *)(v79 + v195 + 16);
              v243 = *(_OWORD *)(v79 + v195 + 32);
              v244 = *(_OWORD *)(v79 + v195 + 48);
              v245 = *(SYSTEMTIME *)(v79 + v195 + 64);
              v246 = *(_OWORD *)(v79 + v195 + 80);
              v247 = *(_DWORD *)(v79 + v195 + 96);
              FileTime = (struct _FILETIME)_mm_srli_si128(v80, 8).m128i_u64[0];
              v81 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DismGetDriverInfo)(
                      v192,
                      FileTime,
                      &v11[v77],
                      &v12[v77],
                      0);
              v189 = v81;
              if ( v81 < 0 )
              {
                v165 = GetLastError();
                v166 = CurrentIP();
                v167 = ConstructPartialMsgW(
                         0x2000000u,
                         "Failed to get driver info from driver package %s. Error: 0x%08X",
                         *(const char **)&FileTime,
                         v81);
                WdsSetupLogMessageW(
                  v167,
                  819200,
                  L"D",
                  0,
                  3235,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                  L"CDownloadDUUpdates::FilterUpdates",
                  v166,
                  v165,
                  0,
                  0);
                v188 = 1;
                v228 = v210;
                throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v228;
              }
              ++v77;
            }
          }
          for ( j = 0; ; ++j )
          {
            if ( j >= v190 )
              goto LABEL_62;
            if ( (unsigned int)SPIsEventSet(v209) )
            {
              v189 = -2147023673;
              v188 = 1;
              v235 = v210;
              throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v235;
            }
            v83 = 100LL * (int)j;
            v241 = *(_OWORD *)(v83 + v195);
            v242 = *(_OWORD *)(v83 + v195 + 16);
            v243 = *(_OWORD *)(v83 + v195 + 32);
            v244 = *(_OWORD *)(v83 + v195 + 48);
            v245 = *(SYSTEMTIME *)(v83 + v195 + 64);
            v246 = *(_OWORD *)(v83 + v195 + 80);
            v247 = *(_DWORD *)(v83 + v195 + 96);
            FileTime = 0;
            FileTime2 = 0;
            SystemTimeToFileTime((const SYSTEMTIME *)&v245.wDayOfWeek, &FileTime);
            SystemTimeToFileTime(&SystemTime, &FileTime2);
            if ( !CompareFileTime(&FileTime, &FileTime2) )
            {
              v84 = 0;
              if ( v12[j] )
                break;
            }
LABEL_60:
            ;
          }
          while ( 1 )
          {
            v85 = 52LL * v84;
            v86 = v11[j];
            FileTime = *(struct _FILETIME *)(v85 + v86);
            if ( CompareStringW(0x409u, 1u, *(PCNZWCH *)(v85 + v86 + 16), -1, v197, -1) == 2
              && CompareStringW(0x409u, 1u, *(PCNZWCH *)&FileTime, -1, bstrString, -1) == 2 )
            {
              break;
            }
            if ( (unsigned int)++v84 >= v12[j] )
              goto LABEL_60;
          }
          v87 = GetLastError();
          v88 = CurrentIP();
          v89 = ConstructPartialMsgW(0x4000000u, "  Found matching driver package in the current OS");
          WdsSetupLogMessageW(
            v89,
            819200,
            L"D",
            0,
            3272,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v88,
            v87,
            0,
            0);
          v90 = GetLastError();
          v91 = CurrentIP();
          v92 = ConstructPartialMsgW(0x4000000u, "    Matching package: %s", *((const char **)&v241 + 1));
          WdsSetupLogMessageW(
            v92,
            819200,
            L"D",
            0,
            3273,
            L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
            L"CDownloadDUUpdates::FilterUpdates",
            v91,
            v90,
            0,
            0);
          v37 = 1;
        }
LABEL_62:
        v93 = GetLastError();
        v94 = CurrentIP();
        AnswerString = CDownloadDUUpdates::GetAnswerString(v37);
        v96 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v237, AnswerString);
        P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v96);
        CString = (const char *)UnBCL::String::get_CString(P);
        v99 = ConstructPartialMsgW(0x4000000u, "  Initial decision for this update: %s", CString);
        WdsSetupLogMessageW(
          v99,
          819200,
          L"D",
          0,
          3280,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::FilterUpdates",
          v94,
          v93,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v237);
        if ( v231 )
        {
          if ( v191 == 2 )
          {
            if ( v203 )
            {
              v101 = v197;
              v102 = pbstr;
              v103 = bstrString;
              p_SystemTime = &SystemTime;
            }
            else
            {
              v101 = 0;
              v102 = 0;
              v103 = 0;
              p_SystemTime = 0;
            }
            v100 = (*(__int64 (__fastcall **)(struct SetupPlatform::IDownloadCallback *, BSTR, BSTR, BSTR, BSTR, _SYSTEMTIME *, unsigned int))(*(_QWORD *)v231 + 8LL))(
                     v231,
                     v198,
                     v101,
                     v102,
                     v103,
                     p_SystemTime,
                     v37);
          }
          else
          {
            v100 = 0;
            if ( v191 == 4 )
              v100 = (**(__int64 (__fastcall ***)(struct SetupPlatform::IDownloadCallback *, BSTR, _QWORD))v231)(
                       v231,
                       v198,
                       v37);
          }
          if ( v100 != v37 )
          {
            v105 = GetLastError();
            v106 = CurrentIP();
            v107 = CDownloadDUUpdates::GetAnswerString(v100);
            v108 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v238, v107);
            v109 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v108);
            v110 = (const char *)UnBCL::String::get_CString(v109);
            v111 = ConstructPartialMsgW(0x4000000u, "  Specific callback decision: %s", v110);
            WdsSetupLogMessageW(
              v111,
              819200,
              L"D",
              0,
              3305,
              L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
              L"CDownloadDUUpdates::FilterUpdates",
              v106,
              v105,
              0,
              0);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v238);
            v37 = v100;
          }
        }
        v112 = GetLastError();
        v113 = CurrentIP();
        v114 = CDownloadDUUpdates::GetAnswerString(v37);
        v115 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v239, v114);
        v116 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v115);
        v117 = (const char *)UnBCL::String::get_CString(v116);
        v118 = ConstructPartialMsgW(0x4000000u, "  Final decision for the update: %s", v117);
        WdsSetupLogMessageW(
          v118,
          819200,
          L"D",
          0,
          3310,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::FilterUpdates",
          v113,
          v112,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v239);
        if ( v37 == 1 )
        {
          v119 = (*(__int64 (__fastcall **)(struct DU::IDUUpdateCollection *, _QWORD))(*(_QWORD *)v211 + 16LL))(
                   v211,
                   v14);
          v189 = v119;
          if ( v119 < 0 )
          {
            v171 = GetLastError();
            v172 = CurrentIP();
            v173 = ConstructPartialMsgW(
                     0x2000000u,
                     "Failed to remove update item from update collection. Error: 0x%08X",
                     v119);
            WdsSetupLogMessageW(
              v173,
              819200,
              L"D",
              0,
              3317,
              L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
              L"CDownloadDUUpdates::FilterUpdates",
              v172,
              v171,
              0,
              0);
            v188 = 1;
            v232 = v210;
            throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v232;
          }
          --v14;
          v13 = --v194;
        }
        else
        {
          v13 = v194;
        }
        SysFreeString(pbstrOut);
        SysFreeString(bstrString);
        SysFreeString(v197);
        SysFreeString(pbstr);
        SysFreeString(v198);
        if ( v208 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v208 + 16LL))(v208);
        if ( v206 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        v200 = &RAII::CAutoRelease<DU::IDUUpdate *>::`vftable';
        if ( v201 )
        {
          (**v201)(v201);
          v201 = 0;
        }
LABEL_82:
        ++v14;
        v9 = v211;
        v10 = v209;
      }
      v47 = GetLastError();
      v48 = CurrentIP();
      v49 = ConstructPartialMsgW(0x4000000u, "    Type: Driver");
      WdsSetupLogMessageW(
        v49,
        819200,
        L"D",
        0,
        3157,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::FilterUpdates",
        v48,
        v47,
        0,
        0);
      v50 = GetLastError();
      v51 = CurrentIP();
      v52 = SysStringLen(pbstr);
      v53 = L"<unknown>";
      if ( v52 )
        v53 = pbstr;
      v54 = ConstructPartialMsgW(0x4000000u, "    WU Class Name: %s", (const char *)v53);
      WdsSetupLogMessageW(
        v54,
        819200,
        L"D",
        0,
        3158,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::FilterUpdates",
        v51,
        v50,
        0,
        0);
      v55 = GetLastError();
      v56 = CurrentIP();
      v57 = SysStringLen(v197);
      v58 = L"<unknown>";
      if ( v57 )
        v58 = v197;
      v59 = ConstructPartialMsgW(0x4000000u, "    Hardware ID: %s", (const char *)v58);
      WdsSetupLogMessageW(
        v59,
        819200,
        L"D",
        0,
        3159,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::FilterUpdates",
        v56,
        v55,
        0,
        0);
      v60 = GetLastError();
      v61 = CurrentIP();
      v62 = SysStringLen(bstrString);
      v63 = L"<unknown>";
      if ( v62 )
        v63 = bstrString;
      v64 = ConstructPartialMsgW(0x4000000u, "    Manufacturer: %s", (const char *)v63);
      WdsSetupLogMessageW(
        v64,
        819200,
        L"D",
        0,
        3160,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::FilterUpdates",
        v61,
        v60,
        0,
        0);
      v65 = GetLastError();
      v66 = CurrentIP();
      v67 = SysStringLen(pbstrOut);
      v68 = L"<unknown>";
      if ( v67 )
        v68 = pbstrOut;
      v46 = ConstructPartialMsgW(0x4000000u, "    Version Date: %s", (const char *)v68);
      v187 = 0;
      v186 = 0;
      v185 = v65;
      v184 = v66;
      v183 = L"CDownloadDUUpdates::FilterUpdates";
      *(_QWORD *)cchCount2 = L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp";
      LODWORD(lpString2) = 3161;
      goto LABEL_37;
    }
    catch ( DU::IEAAJPEAUIDUUpdateCollection:: )
    {
      CDownloadDUUpdates::FilterUpdates_::_1_::catch_26();
      __eh34_caught_type(
        1,
        DU::IEAAJPEAUIDUUpdateCollection::`CDownloadDUUpdates::FilterUpdates'::`4'::CXXXXXTemp * `RTTI Type Descriptor');
    }
LABEL_123:
    throw (`CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException **)&v234;
  }
  catch ( UnBCL::Exception * )
  {
    v179 = &v180;
    v174 = v179;
    v175 = (_QWORD *)v179[39];
    if ( v175 )
    {
      v176 = 0;
      v177 = *((_DWORD *)v174 + 26);
      if ( v177 )
      {
        do
        {
          if ( v175[v176] )
          {
            DismDelete();
            v175[v176] = 0;
            v177 = *((_DWORD *)v174 + 26);
          }
          ++v176;
        }
        while ( v176 < v177 );
      }
      operator delete[](v175);
    }
    v178 = (void *)v174[40];
    if ( v178 )
      operator delete[](v178);
    if ( v174[17] )
    {
      DismDelete();
      v174[17] = 0;
    }
    if ( *((_DWORD *)v174 + 28) )
    {
      DismCloseSession();
      *((_DWORD *)v174 + 28) = 0;
    }
    if ( *((_DWORD *)v174 + 48) )
      DismShutdown();
    if ( !*((_DWORD *)v174 + 24) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v210);
  }
}

```

## disassembly

```asm
0x1801884bc  mov     r11, rsp
0x1801884bf  push    rbx
0x1801884c0  push    rsi
0x1801884c1  push    rdi
0x1801884c2  push    r12
0x1801884c4  push    r13
0x1801884c6  push    r14
0x1801884c8  push    r15
0x1801884ca  sub     rsp, 2E0h
0x1801884d1  mov     qword ptr [r11-0E8h], 0FFFFFFFFFFFFFFFEh
0x1801884dc  movaps  xmmword ptr [r11-48h], xmm6
0x1801884e1  mov     rax, cs:__security_cookie
0x1801884e8  xor     rax, rsp
0x1801884eb  mov     [rsp+318h+var_58], rax
0x1801884f3  mov     [rsp+318h+var_148], r9
0x1801884fb  mov     rsi, r8
0x1801884fe  mov     [rsp+318h+var_138], r8
0x180188506  mov     rdi, rdx
0x180188509  mov     [rsp+318h+var_1E8], rdx
0x180188511  mov     rbx, [rsp+318h+arg_20]
0x180188519  mov     [rsp+318h+var_228], rbx
0x180188521  xor     eax, eax
0x180188523  mov     [rsp+318h+var_2B4], eax
0x180188527  mov     [rsp+318h+var_258], eax
0x18018852e  mov     [rsp+318h+var_2A8], eax
0x180188532  mov     [r11-290h], rax
0x180188539  mov     [rsp+318h+var_2B0], eax
0x18018853d  mov     r13d, eax
0x180188540  mov     [rsp+318h+var_1E0], rax
0x180188548  mov     r12d, eax
0x18018854b  mov     [rsp+318h+var_1D8], rax
0x180188553  mov     [rsp+318h+var_2B8], eax
0x180188557  lea     rcx, [r11-220h]
0x18018855e  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180188564  lea     rax, ??_7CXXXXXHandledException@?2??FilterUpdates@CDownloadDUUpdates@@IEAAJPEAUIDUUpdateCollection@DU@@PEAJPEAUIDownloadCallback@SetupPlatform@@PEAXPEAUIDUDownloadProgress@6@PEAUITelemetry@@PEAUITelemetryActivity@@@Z@6B@; const `CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)'::`3'::CXXXXXHandledException::`vftable'
0x18018856b  mov     [rsp+318h+var_220], rax
0x180188573  mov     r14d, [rsi]
0x180188576  mov     [rsp+318h+var_298], r14d
0x18018857e  xor     esi, esi
0x180188580  mov     r15d, esi
0x180188583  xorps   xmm6, xmm6
0x180188586  cmp     r15d, r14d
0x180188589  jge     loc_18018A277
0x18018858f  mov     rcx, rbx; void *
0x180188592  call    ?SPIsEventSet@@YAHPEAX@Z; SPIsEventSet(void *)
0x180188597  test    eax, eax
0x180188599  jnz     loc_180189699
0x18018859f  mov     [rsp+318h+var_260], rsi
0x1801885a7  lea     rax, ??_7?$CAutoRelease@PEAUIDUUpdate@DU@@@RAII@@6B@; const RAII::CAutoRelease<DU::IDUUpdate *>::`vftable'
0x1801885ae  mov     [rsp+318h+var_268], rax
0x1801885b6  mov     rax, [rdi]
0x1801885b9  mov     rbx, [rax+8]
0x1801885bd  lea     rcx, [rsp+318h+var_268]
0x1801885c5  call    ??I?$CAutoCleanupBase@PEAVVdsVolumePathEnumerator@@@RAII@@UEBAPEBQEAVVdsVolumePathEnumerator@@XZ; RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(void)
0x1801885ca  mov     r8, rax
0x1801885cd  mov     edx, r15d
0x1801885d0  mov     rcx, rdi
0x1801885d3  mov     rax, rbx
0x1801885d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801885db  mov     esi, eax
0x1801885dd  mov     [rsp+318h+var_2B4], eax
0x1801885e1  xor     ebx, ebx
0x1801885e3  test    eax, eax
0x1801885e5  js      loc_180189740
0x1801885eb  mov     [rsp+318h+var_2AC], ebx
0x1801885ef  mov     rax, [rsp+318h+var_268]
0x1801885f7  lea     rcx, [rsp+318h+var_268]
0x1801885ff  mov     rax, [rax+18h]
0x180188603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188608  mov     r8, rax
0x18018860b  mov     rcx, [rax]
0x18018860e  mov     rax, [rcx+8]
0x180188612  lea     rdx, [rsp+318h+var_2AC]
0x180188617  mov     rcx, r8
0x18018861a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018861f  mov     esi, eax
0x180188621  mov     [rsp+318h+var_2B4], eax
0x180188625  test    eax, eax
0x180188627  js      loc_1801897E3
0x18018862d  mov     eax, [rsp+318h+var_2AC]
0x180188631  add     eax, 0FFFFFFFEh
0x180188634  test    eax, 0FFFFFFFDh
0x180188639  jz      loc_1801886E5
0x18018863f  call    cs:__imp_GetLastError
0x180188645  mov     edi, eax
0x180188647  call    cs:__imp_CurrentIP
0x18018864d  mov     rbx, rax
0x180188650  mov     r8d, r15d
0x180188653  lea     rdx, aCdownloadduupd_58; "CDownloadDUUpdates::FilterUpdates: Skip"...
0x18018865a  mov     ecx, 4000000h; unsigned int
0x18018865f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180188664  xor     esi, esi
0x180188666  mov     [rsp+318h+var_2C8], esi
0x18018866a  mov     [rsp+318h+var_2D0], rsi
0x18018866f  mov     [rsp+318h+var_2D8], edi
0x180188673  mov     [rsp+318h+var_2E0], rbx
0x180188678  lea     rcx, aCdownloadduupd_11; "CDownloadDUUpdates::FilterUpdates"
0x18018867f  mov     [rsp+318h+var_2E8], rcx
0x180188684  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18018868b  mov     qword ptr [rsp+318h+cchCount2], rcx
0x180188690  mov     dword ptr [rsp+318h+lpString2], 0BEDh
0x180188698  xor     r9d, r9d
0x18018869b  lea     r8, aD_0; "D"
0x1801886a2  mov     edx, 0C8000h
0x1801886a7  mov     rcx, rax
0x1801886aa  call    cs:__imp_WdsSetupLogMessageW
0x1801886b0  nop
0x1801886b1  lea     rax, ??_7?$CAutoRelease@PEAUIDUUpdate@DU@@@RAII@@6B@; const RAII::CAutoRelease<DU::IDUUpdate *>::`vftable'
0x1801886b8  mov     [rsp+318h+var_268], rax
0x1801886c0  mov     rcx, [rsp+318h+var_260]
0x1801886c8  test    rcx, rcx
0x1801886cb  jz      short loc_1801886E0
0x1801886cd  mov     rax, [rcx]
0x1801886d0  mov     rax, [rax]
0x1801886d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801886d8  mov     [rsp+318h+var_260], rsi
0x1801886e0  jmp     loc_180189644
0x1801886e5  mov     [rsp+318h+var_240], rbx
0x1801886ed  mov     rax, [rsp+318h+var_268]
0x1801886f5  lea     rcx, [rsp+318h+var_268]
0x1801886fd  mov     rax, [rax+18h]
0x180188701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188706  mov     r8, rax
0x180188709  mov     rcx, [rax]
0x18018870c  mov     rax, [rcx+20h]
0x180188710  lea     rdx, [rsp+318h+var_240]
0x180188718  mov     rcx, r8
0x18018871b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188720  mov     esi, eax
0x180188722  mov     [rsp+318h+var_2B4], eax
0x180188726  test    eax, eax
0x180188728  js      loc_180189887
0x18018872e  mov     [rsp+318h+var_230], rbx
0x180188736  mov     rcx, [rsp+318h+var_240]
0x18018873e  mov     rax, [rcx]
0x180188741  lea     rdx, [rsp+318h+var_230]
0x180188749  mov     rax, [rax+98h]
0x180188750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188755  mov     esi, eax
0x180188757  mov     [rsp+318h+var_2B4], eax
0x18018875b  test    eax, eax
0x18018875d  js      loc_18018992B
0x180188763  mov     [rsp+318h+var_278], rbx
0x18018876b  mov     rcx, [rsp+318h+var_230]
0x180188773  mov     rax, [rcx]
0x180188776  lea     rdx, [rsp+318h+var_278]
0x18018877e  mov     rax, [rax+40h]
0x180188782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188787  mov     esi, eax
0x180188789  mov     [rsp+318h+var_2B4], eax
0x18018878d  test    eax, eax
0x18018878f  js      loc_1801899CF
0x180188795  mov     [rsp+318h+pbstr], rbx
0x18018879d  mov     [rsp+318h+var_280], rbx
0x1801887a5  mov     [rsp+318h+bstrString], rbx
0x1801887ad  xorps   xmm0, xmm0
0x1801887b0  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x1801887b8  mov     [rsp+318h+pbstrOut], rbx
0x1801887c0  mov     r14d, ebx
0x1801887c3  mov     [rsp+318h+var_254], ebx
0x1801887ca  cmp     [rsp+318h+var_2AC], 2
0x1801887cf  jnz     loc_1801889B6
0x1801887d5  mov     qword ptr [rsp+318h+FileTime2.dwLowDateTime], rbx
0x1801887da  mov     rcx, [rsp+318h+var_240]
0x1801887e2  mov     rax, [rcx]
0x1801887e5  lea     r8, [rsp+318h+FileTime2]
0x1801887ea  lea     rdx, _GUID_b383cd1a_5ce9_4504_9f63_764b1236f191
0x1801887f1  mov     rax, [rax]
0x1801887f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801887f9  mov     esi, eax
0x1801887fb  mov     [rsp+318h+var_2B4], eax
0x1801887ff  test    eax, eax
0x180188801  js      loc_18018891A
0x180188807  mov     rcx, qword ptr [rsp+318h+FileTime2.dwLowDateTime]
0x18018880c  mov     rax, [rcx]
0x18018880f  lea     rdx, [rsp+318h+pbstr]
0x180188817  mov     rax, [rax+1A0h]
0x18018881e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188823  mov     esi, eax
0x180188825  mov     [rsp+318h+var_2B4], eax
0x180188829  test    eax, eax
0x18018882b  js      loc_180189A73
0x180188831  mov     rcx, qword ptr [rsp+318h+FileTime2.dwLowDateTime]
0x180188836  mov     rax, [rcx]
0x180188839  lea     rdx, [rsp+318h+var_280]
0x180188841  mov     rax, [rax+1A8h]
0x180188848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018884d  mov     esi, eax
0x18018884f  mov     [rsp+318h+var_2B4], eax
0x180188853  test    eax, eax
0x180188855  js      loc_180189B16
0x18018885b  mov     rcx, qword ptr [rsp+318h+FileTime2.dwLowDateTime]
0x180188860  mov     rax, [rcx]
0x180188863  lea     rdx, [rsp+318h+bstrString]
0x18018886b  mov     rax, [rax+1B0h]
0x180188872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188877  mov     esi, eax
0x180188879  mov     [rsp+318h+var_2B4], eax
0x18018887d  test    eax, eax
0x18018887f  js      loc_180189BB9
0x180188885  movsd   [rsp+318h+vtime], xmm6
0x18018888e  mov     rcx, qword ptr [rsp+318h+FileTime2.dwLowDateTime]
0x180188893  mov     rax, [rcx]
0x180188896  lea     rdx, [rsp+318h+vtime]
0x18018889e  mov     rax, [rax+1C8h]
0x1801888a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801888aa  mov     esi, eax
0x1801888ac  mov     [rsp+318h+var_2B4], eax
0x1801888b0  test    eax, eax
0x1801888b2  js      loc_180189C5C
0x1801888b8  lea     rdx, [rsp+318h+SystemTime]; lpSystemTime
0x1801888c0  movsd   xmm0, [rsp+318h+vtime]; vtime
0x1801888c9  call    cs:__imp_VariantTimeToSystemTime
0x1801888cf  test    eax, eax
0x1801888d1  jz      loc_180189CFF
0x1801888d7  lea     r9, [rsp+318h+pbstrOut]; pbstrOut
0x1801888df  mov     edx, 409h; lcid
0x1801888e4  mov     r8d, 40h ; '@'; dwFlags
0x1801888ea  movsd   xmm0, [rsp+318h+vtime]; dateIn
0x1801888f3  call    cs:__imp_VarBstrFromDate
0x1801888f9  mov     esi, eax
0x1801888fb  mov     [rsp+318h+var_2B4], eax
0x1801888ff  test    eax, eax
0x180188901  js      loc_180189DA2
0x180188907  mov     r14d, 1
0x18018890d  mov     [rsp+318h+var_254], r14d
0x180188915  jmp     loc_18018899F
0x18018891a  call    cs:__imp_GetLastError
0x180188920  mov     edi, eax
0x180188922  call    cs:__imp_CurrentIP
0x180188928  mov     rbx, rax
0x18018892b  mov     r9d, esi
0x18018892e  mov     r8, [rsp+318h+var_278]
0x180188936  lea     rdx, aCdownloadduupd_37; "CDownloadDUUpdates::FilterUpdates: IWin"...
0x18018893d  mov     ecx, 3000000h; unsigned int
0x180188942  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180188947  mov     [rsp+318h+var_2C8], 0
0x18018894f  mov     [rsp+318h+var_2D0], 0
0x180188958  mov     [rsp+318h+var_2D8], edi
0x18018895c  mov     [rsp+318h+var_2E0], rbx
0x180188961  lea     rcx, aCdownloadduupd_11; "CDownloadDUUpdates::FilterUpdates"
0x180188968  mov     [rsp+318h+var_2E8], rcx
0x18018896d  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180188974  mov     qword ptr [rsp+318h+cchCount2], rcx
0x180188979  mov     dword ptr [rsp+318h+lpString2], 0C45h
0x180188981  xor     r9d, r9d
0x180188984  lea     r8, aD_0; "D"
0x18018898b  mov     edx, 0C8000h
0x180188990  mov     rcx, rax
0x180188993  call    cs:__imp_WdsSetupLogMessageW
0x180188999  xor     ebx, ebx
0x18018899b  mov     [rsp+318h+var_2B4], ebx
0x18018899f  mov     rcx, qword ptr [rsp+318h+FileTime2.dwLowDateTime]
0x1801889a4  test    rcx, rcx
0x1801889a7  jz      short loc_1801889B6
0x1801889a9  mov     rax, [rcx]
0x1801889ac  mov     rax, [rax+10h]
0x1801889b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801889b5  nop
0x1801889b6  mov     esi, ebx
0x1801889b8  call    cs:__imp_GetLastError
0x1801889be  mov     edi, eax
0x1801889c0  call    cs:__imp_CurrentIP
0x1801889c6  mov     rbx, rax
0x1801889c9  lea     rdx, aDecidingDynami; "  Deciding dynamic update download on u"...
0x1801889d0  mov     ecx, 4000000h; unsigned int
0x1801889d5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801889da  mov     [rsp+318h+var_2C8], 0
0x1801889e2  mov     [rsp+318h+var_2D0], 0
0x1801889eb  mov     [rsp+318h+var_2D8], edi
0x1801889ef  mov     [rsp+318h+var_2E0], rbx
0x1801889f4  lea     rcx, aCdownloadduupd_11; "CDownloadDUUpdates::FilterUpdates"
0x1801889fb  mov     [rsp+318h+var_2E8], rcx
0x180188a00  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180188a07  mov     qword ptr [rsp+318h+cchCount2], rcx
0x180188a0c  mov     dword ptr [rsp+318h+lpString2], 0C4Ch
0x180188a14  xor     r9d, r9d
0x180188a17  lea     r8, aD_0; "D"
0x180188a1e  mov     edx, 0C8000h
0x180188a23  mov     rcx, rax
0x180188a26  call    cs:__imp_WdsSetupLogMessageW
0x180188a2c  call    cs:__imp_GetLastError
0x180188a32  mov     edi, eax
0x180188a34  call    cs:__imp_CurrentIP
0x180188a3a  mov     rbx, rax
0x180188a3d  mov     r8, [rsp+318h+var_278]
0x180188a45  lea     rdx, aIdS; "    Id: %s"
0x180188a4c  mov     ecx, 4000000h; unsigned int
0x180188a51  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180188a56  mov     [rsp+318h+var_2C8], 0
0x180188a5e  mov     [rsp+318h+var_2D0], 0
0x180188a67  mov     [rsp+318h+var_2D8], edi
0x180188a6b  mov     [rsp+318h+var_2E0], rbx
0x180188a70  lea     rcx, aCdownloadduupd_11; "CDownloadDUUpdates::FilterUpdates"
0x180188a77  mov     [rsp+318h+var_2E8], rcx
0x180188a7c  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180188a83  mov     qword ptr [rsp+318h+cchCount2], rcx
0x180188a88  mov     dword ptr [rsp+318h+lpString2], 0C4Dh
0x180188a90  xor     r9d, r9d
0x180188a93  lea     r8, aD_0; "D"
  ... truncated ...
```
