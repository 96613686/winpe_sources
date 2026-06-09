# CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)

- ea: `0x180184d3c`
- end: `0x180186e63`
- name: `?DoExecuteInternal@CDownloadDUUpdates@@IEAAJHHPEAUIDownloadCallback@SetupPlatform@@PEAUIExecutionContext@@PEAUITelemetry@@PEAXPEAUIDUDownloadProgress@3@PEAPEAVCDUPackageCollection@@@Z`
- size: `8487`
- prototype: `void __noreturn(CDownloadDUUpdates *__hidden this, __int64, __int64, struct SetupPlatform::IDownloadCallback *, struct IExecutionContext *, struct ITelemetry *, void *, struct SetupPlatform::IDUDownloadProgress *, struct CDUPackageCollection **)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180183580`
- `0x180186e6c`

## callees

- `0x18001413d`
- `0x180044754`
- `0x180044820`
- `0x180057dec`
- `0x18005dd24`
- `0x18017c524`
- `0x18017cac4`
- `0x18017cb20`
- `0x18017d428`
- `0x18017f1a8`
- `0x180180a88`
- `0x180181570`
- `0x180182230`
- `0x180184d3c`
- `0x180187a20`
- `0x1801884bc`
- `0x18018de08`
- `0x18018e378`
- `0x1801913e8`
- `0x180297e4c`
- `0x1802d68d4`
- `0x1802db214`
- `0x1802e3cbc`
- `0x1804058b0`
- `0x180406640`
- `0x18040b41c`
- `0x1804bbf46`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801850f5`
- `KERNEL32!GetLastError` at `0x180185155`
- `KERNEL32!GetLastError` at `0x1801851de`
- `KERNEL32!GetLastError` at `0x180185495`
- `KERNEL32!GetLastError` at `0x1801854fb`
- `KERNEL32!GetLastError` at `0x180185569`
- `KERNEL32!GetLastError` at `0x1801855d4`
- `KERNEL32!GetLastError` at `0x18018575d`
- `KERNEL32!GetLastError` at `0x180185975`
- `KERNEL32!GetLastError` at `0x180185a46`
- `KERNEL32!GetLastError` at `0x180185aac`
- `KERNEL32!GetLastError` at `0x180185b1a`
- `KERNEL32!GetLastError` at `0x180185b85`
- `KERNEL32!GetLastError` at `0x180185c23`
- `KERNEL32!GetLastError` at `0x180185e42`
- `KERNEL32!GetLastError` at `0x180185edf`
- `KERNEL32!GetLastError` at `0x180185f90`
- `KERNEL32!GetLastError` at `0x180186050`
- `KERNEL32!GetLastError` at `0x18018612a`
- `KERNEL32!GetLastError` at `0x1801861c3`
- `KERNEL32!GetLastError` at `0x180186297`
- `KERNEL32!GetLastError` at `0x180186333`
- `KERNEL32!GetLastError` at `0x18018640a`
- `KERNEL32!GetLastError` at `0x1801864a9`
- `KERNEL32!GetLastError` at `0x180186580`
- `KERNEL32!GetLastError` at `0x18018665c`
- `KERNEL32!GetLastError` at `0x18018673f`
- `KERNEL32!GetLastError` at `0x180186824`
- `KERNEL32!GetLastError` at `0x180186903`
- `KERNEL32!GetLastError` at `0x1801869db`
- `KERNEL32!GetLastError` at `0x1801869f1`
- `KERNEL32!GetLastError` at `0x180186a16`
- `KERNEL32!GetLastError` at `0x180186b0e`
- `KERNEL32!GetLastError` at `0x180186c09`
- `KERNEL32!GetLastError` at `0x180186d4d`
- `KERNEL32!GetLastError` at `0x180186d63`
- `KERNEL32!GetLastError` at `0x180186d88`
- `KERNEL32!GetLastError` at `0x1801850f5`
- `KERNEL32!GetLastError` at `0x180185155`
- `KERNEL32!GetLastError` at `0x1801851de`
- `KERNEL32!GetLastError` at `0x180185495`
- `KERNEL32!GetLastError` at `0x1801854fb`
- `KERNEL32!GetLastError` at `0x180185569`
- `KERNEL32!GetLastError` at `0x1801855d4`
- `KERNEL32!GetLastError` at `0x18018575d`
- `KERNEL32!GetLastError` at `0x180185975`
- `KERNEL32!GetLastError` at `0x180185a46`
- `KERNEL32!GetLastError` at `0x180185aac`
- `KERNEL32!GetLastError` at `0x180185b1a`
- `KERNEL32!GetLastError` at `0x180185b85`
- `KERNEL32!GetLastError` at `0x180185c23`
- `KERNEL32!GetLastError` at `0x180185e42`
- `KERNEL32!GetLastError` at `0x180185edf`
- `KERNEL32!GetLastError` at `0x180185f90`
- `KERNEL32!GetLastError` at `0x180186050`
- `KERNEL32!GetLastError` at `0x18018612a`
- `KERNEL32!GetLastError` at `0x1801861c3`
- `KERNEL32!GetLastError` at `0x180186297`
- `KERNEL32!GetLastError` at `0x180186333`
- `KERNEL32!GetLastError` at `0x18018640a`
- `KERNEL32!GetLastError` at `0x1801864a9`
- `KERNEL32!GetLastError` at `0x180186580`
- `KERNEL32!GetLastError` at `0x18018665c`
- `KERNEL32!GetLastError` at `0x18018673f`
- `KERNEL32!GetLastError` at `0x180186824`
- `KERNEL32!GetLastError` at `0x180186903`
- `KERNEL32!GetLastError` at `0x1801869db`
- `KERNEL32!GetLastError` at `0x1801869f1`
- `KERNEL32!GetLastError` at `0x180186a16`
- `KERNEL32!GetLastError` at `0x180186b0e`
- `KERNEL32!GetLastError` at `0x180186c09`
- `KERNEL32!GetLastError` at `0x180186d4d`
- `KERNEL32!GetLastError` at `0x180186d63`
- `KERNEL32!GetLastError` at `0x180186d88`
- `KERNEL32!SetLastError` at `0x180186d47`
- `KERNEL32!SetLastError` at `0x180186d47`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180185ce3`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180185ce3`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180184e84`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180184e84`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x18018582e`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x18018582e`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180185dba`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180185dba`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180184ea3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180185cc3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180185cda`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180184ea3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180185cc3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180185cda`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180184e0b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180184f94`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801857d0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180184e0b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180184f94`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801857d0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180184ebd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180184f65`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185434`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801858a1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185d03`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185d26`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185d4d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185ef3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180186a36`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180186b2e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180184ebd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180184f65`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185434`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801858a1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185d03`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185d26`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185d4d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180185ef3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180186a36`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180186b2e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180184ec6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180184f6e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018543d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801858aa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185d0c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185d2f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185d56`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185efc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180186a3f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180186b37`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180184ec6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180184f6e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018543d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801858aa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185d0c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185d2f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185d56`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180185efc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180186a3f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180186b37`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180185d7d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180185d7d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180185cf4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180185cf4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801851c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018524b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801854f5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185563`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801855ce`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018563c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801857bd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801859e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185aa6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185b14`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185b7f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185bed`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185c88`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185eac`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185f5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185ff9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801860b6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018618f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186223`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801862fc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186393`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018646a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186509`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801865e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801866c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801867a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186884`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186963`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186a9a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186b92`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186c6e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186ded`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801851c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018524b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801854f5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185563`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801855ce`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018563c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801857bd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801859e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185aa6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185b14`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185b7f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185bed`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185c88`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185eac`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185f5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180185ff9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801860b6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018618f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186223`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801862fc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186393`
- `WDSCORE!WdsSetupLogMessageW` at `0x18018646a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186509`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801865e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801866c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801867a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186884`
- `WDSCORE!WdsSetupLogMessageW` at `0x180186963`

## string_xrefs

- `0x180185135`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185195`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018521e`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801854d5`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185543`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801855ae`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018561c`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018579d`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801859c5`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185a86`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185af4`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185b5f`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185bcd`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185c68`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185e86`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185f37`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180185fd3`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186090`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018616f`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186203`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801862dc`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186373`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018644a`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801864e9`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801865c5`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801866a1`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186785`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186864`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186943`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186c4e`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180186dcb`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801860e7`: `No Updates To Download`
- `0x180185f08`: `CDownloadDUUpdates::DoExecuteInternal: Failed to get info set for image %s. hr = 0x%x`
- `0x180185fa4`: `CDownloadDUUpdates::DoExecuteInternal: Failed to search for updates. hr = 0x%x`
- `0x180185129`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185189`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185212`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801854c9`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185537`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801855a2`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185610`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185791`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801859b9`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185a7a`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185ae8`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185b53`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185bc1`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185c5c`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185e7a`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185f2b`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185fc7`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186084`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186163`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801861f7`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801862d0`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186367`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x18018643e`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801864dd`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x1801865b9`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186695`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186779`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186858`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186937`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186c42`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180186dbf`: `CDownloadDUUpdates::DoExecuteInternal`
- `0x180185e57`: `CDownloadDUUpdates::DoExecuteInternal: DU initialization failed. hr = 0x%x`
- `0x180185106`: `Only TestHook update available.`
- `0x180186061`: `No updates to download. Leaving...`
- `0x1801861d4`: `No updates to download after filtering. Leaving...`
- `0x180186254`: `No Updates To Download After Filtering`
- `0x1801851ef`: `Attempting to filter the update collection to optimize download`
- `0x180186140`: `CDownloadDUUpdates::DoExecuteInternal: Failed to filter updates. hr = 0x%x`
- `0x1801862ad`: `CDownloadDUUpdates::DoExecuteInternal: Failed to determine space needed by updates; skipping download. hr = 0x%x`
- `0x180186344`: `CDownloadDUUpdates::DoExecuteInternal: Insufficient space to download and install updates; will skip download.`
- `0x18018557f`: `  Needed by download of updates: %I64d`
- `0x1801864ba`: `CDownloadDUUpdates::DoExecuteInternal: Required update unpack capability is not present; this scenario is not supported`
- `0x18018653d`: `Required update unpack capability is not present`
- `0x1801863c7`: `Insufficient space to download and install updates`
- `0x18018641b`: `CDownloadDUUpdates::DoExecuteInternal: Fail to get CDUPackage`
- `0x180186596`: `CDownloadDUUpdates::DoExecuteInternal: Failed to download updates. hr = 0x%x`
- `0x180186618`: `Failed during download operation`
- `0x1801866f4`: `Failed to move/copy updates`
- `0x1801866fb`: `DUInstallSkippedReason`
- `0x1801867e0`: `DUInstallSkippedReason`
- `0x1801868bf`: `DUInstallSkippedReason`
- `0x18018699e`: `DUInstallSkippedReason`
- `0x180186ad2`: `DUInstallSkippedReason`
- `0x180186bcc`: `DUInstallSkippedReason`
- `0x180186ca8`: `DUInstallSkippedReason`
- `0x180186e25`: `DUInstallSkippedReason`
- `0x180186672`: `CDownloadDUUpdates::DoExecuteInternal: Failed to move/copy updates. hr = 0x%x`
- `0x1801866d9`: `DUInstallSkippedHR`
- `0x1801867be`: `DUInstallSkippedHR`
- `0x18018689d`: `DUInstallSkippedHR`
- `0x18018697c`: `DUInstallSkippedHR`
- `0x180186ab0`: `DUInstallSkippedHR`
- `0x180186baa`: `DUInstallSkippedHR`
- `0x180186c86`: `DUInstallSkippedHR`
- `0x180186e03`: `DUInstallSkippedHR`
- `0x180185996`: `Hard disk space needed: %I64d, space taken by copy: %I64d`
- `0x180186756`: `CDownloadDUUpdates::DoExecuteInternal: Did not find hard disk space needed, when update cab files will not be extracted. This is unexpected! hr = 0x%x`
- `0x180186d9c`: `CDownloadDUUpdates::DoExecuteInternal: Failed to calculate space taken up by copy of updates. hr = 0x%x`
- `0x180186e1e`: `Failed to calculate space taken up by copy of updates`
- `0x180185b30`: `  Needed by install of updates: %I64d`
- `0x180186835`: `CDownloadDUUpdates::DoExecuteInternal: Insufficient space to install updates; will skip installation.`
- `0x180186914`: `CDownloadDUUpdates::DoExecuteInternal: Total space estimate leaves low free space; skipping installation.`
- `0x1801868b8`: `Insufficient space to install updates`
- `0x180186b45`: `CDownloadDUUpdates::DoExecuteInternal: Failed to create reserved space file %s. hr = 0x%x`
- `0x180186bc5`: `Failed to create reserved space file`
- `0x180186a4b`: `CDownloadDUUpdates::DoExecuteInternal: Failed to create reserved file's parent path %s. hr = 0x%x`
- `0x180186acb`: `Failed to create reserved file's parent path`
- `0x180186c1f`: `CDownloadDUUpdates::DoExecuteInternal: Failed to store updates info. hr = 0x%x`
- `0x180186ca1`: `Failed to store updates info`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=2
void __fastcall __noreturn CDownloadDUUpdates::DoExecuteInternal(
        CDownloadDUUpdates *this,
        int a2,
        int a3,
        struct SetupPlatform::IDownloadCallback *a4,
        struct IExecutionContext *a5,
        struct ITelemetry *a6,
        void *a7,
        struct SetupPlatform::IDUDownloadProgress *a8,
        struct CDUPackageCollection **a9)
{
  CDownloadDUUpdates *v11; // rbx
  struct ITelemetry *v12; // rdi
  CDUPackageCollection *v13; // rax
  CDUPackageCollection *v14; // rax
  void (__fastcall *v15)(struct ITelemetry *, const unsigned __int16 *, struct ITelemetryActivity **); // r15
  UnBCL::String *v16; // rax
  const unsigned __int16 *CString; // rax
  int v18; // r14d
  struct CImageInfoSet **v19; // rdi
  char *v20; // r14
  UnBCL::String *v21; // rax
  const unsigned __int16 *v22; // rax
  int v23; // edi
  CDUImageInfo *v24; // rdi
  __int64 v25; // rax
  struct SetupPlatform::IImageInfo *v26; // rax
  CDUImageInfo *v27; // rax
  void (__fastcall ***v28)(_QWORD, __int64); // rcx
  struct CDUPackageCollection *v29; // rax
  int v30; // edi
  struct DU::IDUUpdateCollection **v31; // rax
  int v32; // r12d
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  DWORD v38; // edi
  __int64 v39; // rbx
  struct tagLOG_PARTIAL_MSG *v40; // rax
  struct ITelemetryActivity *v41; // rbx
  struct DU::IDUUpdateCollection *v42; // rax
  struct DU::IDUUpdateCollection *v43; // rdi
  CDUPackageCollection *v44; // rax
  struct CDUPackageCollection *v45; // rax
  __int64 v46; // rcx
  UnBCL::String *v47; // rax
  DWORD v48; // edi
  __int64 v49; // rbx
  struct tagLOG_PARTIAL_MSG *v50; // rax
  DWORD v51; // edi
  __int64 v52; // rbx
  struct tagLOG_PARTIAL_MSG *v53; // rax
  DWORD v54; // edi
  __int64 v55; // rbx
  struct tagLOG_PARTIAL_MSG *v56; // rax
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  int v60; // edi
  unsigned int *v61; // rbx
  int (__fastcall ***v62)(_QWORD); // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  DWORD v66; // edi
  __int64 v67; // rbx
  struct tagLOG_PARTIAL_MSG *v68; // rax
  struct IExecutionContext *v69; // rax
  __int64 v70; // rdi
  __int64 v71; // rax
  DWORD LastError; // edi
  __int64 v73; // rbx
  struct tagLOG_PARTIAL_MSG *v74; // rax
  DWORD v75; // ebx
  __int64 v76; // r15
  UnBCL::String *v77; // rax
  const char *v78; // rax
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
  DWORD v89; // edi
  __int64 v90; // rbx
  struct tagLOG_PARTIAL_MSG *v91; // rax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  DWORD v95; // edi
  __int64 v96; // rbx
  struct tagLOG_PARTIAL_MSG *v97; // rax
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  int v101; // [rsp+20h] [rbp-258h]
  struct ITelemetry *v102; // [rsp+20h] [rbp-258h]
  struct ITelemetryActivity *v103; // [rsp+38h] [rbp-240h]
  DWORD v104; // [rsp+40h] [rbp-238h]
  struct ITelemetryActivity *v105; // [rsp+68h] [rbp-210h] BYREF
  unsigned __int64 v106; // [rsp+70h] [rbp-208h] BYREF
  int v107; // [rsp+78h] [rbp-200h] BYREF
  void *v108; // [rsp+80h] [rbp-1F8h]
  struct IExecutionContext *v109; // [rsp+88h] [rbp-1F0h]
  _QWORD v110[2]; // [rsp+90h] [rbp-1E8h] BYREF
  struct ITelemetry *v111; // [rsp+A0h] [rbp-1D8h]
  int v112; // [rsp+A8h] [rbp-1D0h] BYREF
  CDownloadDUUpdates *v113; // [rsp+B0h] [rbp-1C8h]
  __int64 v114; // [rsp+B8h] [rbp-1C0h] BYREF
  int v115; // [rsp+C0h] [rbp-1B8h] BYREF
  struct SetupPlatform::IDUDownloadProgress *v116; // [rsp+C8h] [rbp-1B0h]
  struct DU::IDUUpdateCollection *v117; // [rsp+D0h] [rbp-1A8h]
  __int64 v118; // [rsp+D8h] [rbp-1A0h] BYREF
  struct SetupPlatform::IDownloadCallback *v119; // [rsp+E0h] [rbp-198h] BYREF
  __int64 v120; // [rsp+E8h] [rbp-190h]
  void **v121; // [rsp+F0h] [rbp-188h] BYREF
  struct DU::IDUUpdateCollection *v122; // [rsp+F8h] [rbp-180h]
  void **v123; // [rsp+100h] [rbp-178h] BYREF
  __int64 v124; // [rsp+108h] [rbp-170h]
  _QWORD v125[7]; // [rsp+120h] [rbp-158h] BYREF
  void **v126; // [rsp+158h] [rbp-120h] BYREF
  _QWORD *v127; // [rsp+178h] [rbp-100h] BYREF
  _QWORD *v128; // [rsp+180h] [rbp-F8h] BYREF
  _QWORD *v129; // [rsp+188h] [rbp-F0h] BYREF
  _QWORD *v130; // [rsp+190h] [rbp-E8h] BYREF
  _QWORD *v131; // [rsp+198h] [rbp-E0h] BYREF
  _QWORD pExceptionObject[5]; // [rsp+1D0h] [rbp-A8h] BYREF
  _QWORD *v133; // [rsp+200h] [rbp-78h] BYREF
  _QWORD *v134; // [rsp+208h] [rbp-70h] BYREF
  _QWORD v135[3]; // [rsp+210h] [rbp-68h] BYREF
  unsigned __int16 v136; // [rsp+228h] [rbp-50h] BYREF
  int v137; // [rsp+22Ah] [rbp-4Eh]
  wchar_t v138; // [rsp+22Eh] [rbp-4Ah]

  v135[2] = -2;
  v119 = a4;
  v11 = this;
  v113 = this;
  pExceptionObject[3] = this;
  v109 = a5;
  v12 = a6;
  v111 = a6;
  v108 = a7;
  v116 = a8;
  pExceptionObject[4] = a9;
  v115 = 0;
  v122 = 0;
  v121 = &RAII::CAutoRelease<DU::IDUUpdateCollection *>::`vftable';
  v117 = 0;
  v13 = (CDUPackageCollection *)UnBCL::Object::operator new(0x118u);
  v118 = (__int64)v13;
  if ( v13 )
    v14 = CDUPackageCollection::CDUPackageCollection(v13);
  else
    v14 = 0;
  v110[1] = v14;
  v110[0] = &RAII::CAutoRelease<CDUPackageCollection *>::`vftable';
  if ( !a6 )
  {
    if ( a5 )
    {
      v12 = (struct ITelemetry *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a5 + 64LL))(a5);
      v111 = v12;
    }
    else
    {
      v12 = 0;
      v111 = 0;
    }
  }
  v105 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v125);
  v125[0] = &`CDownloadDUUpdates::DoExecuteInternal'::`3'::CXXXXXHandledException::`vftable';
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v11 + 352) && v12 )
  {
    v15 = *(void (__fastcall **)(struct ITelemetry *, const unsigned __int16 *, struct ITelemetryActivity **))(*(_QWORD *)v12 + 48LL);
    v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v11 + 352);
    CString = UnBCL::String::get_CString(v16);
    v15(v12, CString, &v105);
  }
  if ( v105 )
    (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *))(*(_QWORD *)v105 + 32LL))(
      v105,
      L"SP_DU_INFO",
      L"DUSearchAndDownloadStartTime");
  if ( !a2 )
  {
    v18 = SPInitializeDU(&v115);
    if ( v18 < 0 )
    {
      LastError = GetLastError();
      v73 = CurrentIP();
      v74 = ConstructPartialMsgW(
              0x2000000u,
              "CDownloadDUUpdates::DoExecuteInternal: DU initialization failed. hr = 0x%x",
              v18);
      WdsSetupLogMessageW(
        v74,
        819200,
        L"D",
        0,
        3774,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::DoExecuteInternal",
        v73,
        LastError,
        0,
        0);
      pExceptionObject[0] = v125;
      throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)pExceptionObject;
    }
  }
  if ( !*((_QWORD *)v11 + 40) )
  {
    v124 = 0;
    v123 = &RAII::CAutoDelete<CImageInfoSet *>::`vftable';
    v19 = (struct CImageInfoSet **)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v123);
    v20 = (char *)v11 + 328;
    v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v11 + 328);
    v22 = UnBCL::String::get_CString(v21);
    v23 = CImageInfoSet::CreateFromWIM(v22, 0, v19);
    if ( v23 < 0 )
    {
      v75 = GetLastError();
      v76 = CurrentIP();
      v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v20);
      v78 = (const char *)UnBCL::String::get_CString(v77);
      v79 = ConstructPartialMsgW(
              0x2000000u,
              "CDownloadDUUpdates::DoExecuteInternal: Failed to get info set for image %s. hr = 0x%x",
              v78,
              v23);
      WdsSetupLogMessageW(
        v79,
        819200,
        L"D",
        0,
        3786,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::DoExecuteInternal",
        v76,
        v75,
        0,
        0);
      v133 = v125;
      throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v133;
    }
    v24 = (CDUImageInfo *)UnBCL::Object::operator new(0xC8u);
    v106 = (unsigned __int64)v24;
    if ( v24 )
    {
      v25 = ((__int64 (__fastcall *)(void ***))v123[3])(&v123);
      v26 = (struct SetupPlatform::IImageInfo *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 8LL))(
                                                  v25,
                                                  (unsigned int)(*((_DWORD *)v11 + 86) - 1));
      v27 = CDUImageInfo::CDUImageInfo(v24, v26);
    }
    else
    {
      v27 = 0;
    }
    UnBCL::SmartPtr<CDUImageInfo>::SmartPtr<CDUImageInfo>(&v126, v27);
    UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=((char *)v11 + 312, &v126);
    v126 = &UnBCL::SmartPtr<CDUImageInfo>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v126);
    v123 = &RAII::CAutoDelete<CImageInfoSet *>::`vftable';
    if ( v124 )
    {
      v28 = (void (__fastcall ***)(_QWORD, __int64))(v124 + *(int *)(*(_QWORD *)(v124 + 16) + 4LL) + 16LL);
      (**v28)(v28, 1);
    }
  }
  v29 = (struct CDUPackageCollection *)(*(__int64 (__fastcall **)(_QWORD *))(v110[0] + 32LL))(v110);
  v30 = CDownloadDUUpdates::CheckTestHook(v11, v29);
  v107 = 0;
  LODWORD(v106) = 0;
  v31 = (struct DU::IDUUpdateCollection **)((__int64 (__fastcall *)(void ***))v121[1])(&v121);
  v32 = CDownloadDUUpdates::SearchUpdates(v11, a3, v31, &v107, (int *)&v106);
  if ( v32 < 0 )
  {
    v80 = GetLastError();
    v81 = CurrentIP();
    v82 = ConstructPartialMsgW(
            0x2000000u,
            "CDownloadDUUpdates::DoExecuteInternal: Failed to search for updates. hr = 0x%x",
            v32);
    WdsSetupLogMessageW(
      v82,
      819200,
      L"D",
      0,
      3806,
      L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
      L"CDownloadDUUpdates::DoExecuteInternal",
      v81,
      v80,
      0,
      0);
    if ( v105 )
      (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v105 + 24LL))(
        v105,
        L"SP_DU_INFO",
        L"DUSearchFailedHR",
        (unsigned int)v32);
    v134 = v125;
    throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v134;
  }
  if ( v107 )
  {
    if ( !(_DWORD)v106 )
    {
      if ( a3 )
      {
        v38 = GetLastError();
        v39 = CurrentIP();
        v40 = ConstructPartialMsgW(0x4000000u, "Attempting to filter the update collection to optimize download");
        WdsSetupLogMessageW(
          v40,
          819200,
          L"D",
          0,
          3843,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::DoExecuteInternal",
          v39,
          v38,
          0,
          0);
        v41 = v105;
        v42 = (struct DU::IDUUpdateCollection *)((__int64 (__fastcall *)(void ***))v121[4])(&v121);
        CDownloadDUUpdates::FilterUpdates(v113, v42, &v107, v119, v108, v116, v111, v41);
      }
LABEL_31:
      if ( v107 > 0 )
      {
        v43 = v122;
        v117 = v122;
        v122 = 0;
        v44 = (CDUPackageCollection *)(*(__int64 (__fastcall **)(_QWORD *))(v110[0] + 24LL))(v110);
        CDUPackageCollection::Append(v44, v43);
      }
      v118 = 0;
      v114 = 0;
      v112 = 1;
      v45 = (struct CDUPackageCollection *)(*(__int64 (__fastcall **)(_QWORD *))(v110[0] + 32LL))(v110);
      LODWORD(v106) = CDownloadDUUpdates::CalculateSpaceNeeded(v11, v45, &v118, &v114, &v112);
      if ( (v106 & 0x80000000) == 0LL )
      {
        if ( v105 )
        {
          (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v105 + 8LL))(
            v105,
            L"SP_DU_INFO",
            L"DUDownloadPackageSize",
            v118);
          (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v105 + 8LL))(
            v105,
            L"SP_DU_INFO",
            L"DUDownloadPackageSizeOnDisk",
            v114);
        }
        v46 = v118;
        if ( *((_DWORD *)v11 + 71) )
          v46 = v114;
        v106 = v118 + v46 + v114;
        v136 = 63;
        v137 = *(_DWORD *)L":\\";
        v138 = asc_180557F68[3];
        v47 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v11 + 264);
        v136 = *UnBCL::String::get_CString(v47);
        v119 = (struct SetupPlatform::IDownloadCallback *)SPGetFreeDiskSpace(&v136);
        if ( v109 )
          v111 = (struct ITelemetry *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v109 + 120LL))(v109);
        else
          v111 = (struct ITelemetry *)597688320;
        v48 = GetLastError();
        v49 = CurrentIP();
        v50 = ConstructPartialMsgW(0x4000000u, "DU disk space checkpoint before download:");
        WdsSetupLogMessageW(
          v50,
          819200,
          L"D",
          0,
          3923,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::DoExecuteInternal",
          v49,
          v48,
          0,
          0);
        v51 = GetLastError();
        v52 = CurrentIP();
        v53 = ConstructPartialMsgW(0x4000000u, "  Available: %I64d", v119);
        WdsSetupLogMessageW(
          v53,
          819200,
          L"D",
          0,
          3924,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::DoExecuteInternal",
          v52,
          v51,
          0,
          0);
        v54 = GetLastError();
        v55 = CurrentIP();
        v56 = ConstructPartialMsgW(0x4000000u, "  Needed by download of updates: %I64d", v106);
        WdsSetupLogMessageW(
          v56,
          819200,
          L"D",
          0,
          3925,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::DoExecuteInternal",
          v55,
          v54,
          0,
          0);
        v57 = GetLastError();
        v58 = CurrentIP();
        v59 = ConstructPartialMsgW(0x4000000u, "  Needed by setup: %I64d", v111);
        WdsSetupLogMessageW(
          v59,
          819200,
          L"D",
          0,
          3926,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::DoExecuteInternal",
          v58,
          v57,
          0,
          0);
        if ( (__int64)v119 >= (__int64)((char *)v111 + v106) )
        {
          v60 = 0;
          v61 = (unsigned int *)v113;
          while ( 1 )
          {
            v62 = (int (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(_QWORD *))(v110[0] + 24LL))(v110);
            if ( v60 >= (**v62)(v62) )
              break;
            v63 = (*(__int64 (__fastcall **)(_QWORD *))(v110[0] + 24LL))(v110);
            v64 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63 + 8LL))(v63, (unsigned int)v60);
            v65 = _RTDynamicCast_0(
                    v64,
                    0,
                    &SetupPlatform::IDUPackage `RTTI Type Descriptor',
                    &CDUPackage `RTTI Type Descriptor',
                    0);
            if ( !v65 )
            {
              v92 = GetLastError();
              v93 = CurrentIP();
              v94 = ConstructPartialMsgW(0x2000000u, "CDownloadDUUpdates::DoExecuteInternal: Fail to get CDUPackage");
              WdsSetupLogMessageW(
                v94,
                819200,
                L"D",
                0,
                3960,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::DoExecuteInternal",
                v93,
                v92,
                0,
                0);
              v129 = v125;
              throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v129;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v65 + 24) + 40LL))(
                    *(_QWORD *)(v65 + 24),
                    0,
                    v61[72],
                    v61[71]) )
            {
              v95 = GetLastError();
              v96 = CurrentIP();
              v97 = ConstructPartialMsgW(
                      0x2000000u,
                      "CDownloadDUUpdates::DoExecuteInternal: Required update unpack capability is not present; this scen"
                      "ario is not supported");
              WdsSetupLogMessageW(
                v97,
                819200,
                L"D",
                0,
                3969,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::DoExecuteInternal",
                v96,
                v95,
                0,
                0);
              if ( v105 )
              {
                (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v105 + 24LL))(
                  v105,
                  L"SP_DU_INFO",
                  L"DUDownloadSkippedHR",
                  2147942450LL);
                (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v105 + 16LL))(
                  v105,
                  L"SP_DU_INFO",
                  L"DUDownloadSkippedReason",
                  L"Required update unpack capability is not present");
              }
              v130 = v125;
              throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v130;
            }
            ++v60;
          }
          if ( v107 <= 0 )
          {
            v66 = GetLastError();
            v67 = CurrentIP();
            v68 = ConstructPartialMsgW(0x4000000u, "Only test hook available, skip download.");
            WdsSetupLogMessageW(
              v68,
              819200,
              L"D",
              0,
              4002,
              L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
              L"CDownloadDUUpdates::DoExecuteInternal",
              v67,
              v66,
              0,
              0);
            v61 = (unsigned int *)v113;
          }
          else
          {
            LODWORD(v106) = CDownloadDUUpdates::DownloadUpdates((CDownloadDUUpdates *)v61, v117, v108, v116, v102, v105);
            if ( (v106 & 0x80000000) != 0LL )
            {
              v98 = GetLastError();
              v99 = CurrentIP();
              v100 = ConstructPartialMsgW(
                       0x2000000u,
                       "CDownloadDUUpdates::DoExecuteInternal: Failed to download updates. hr = 0x%x",
                       v106);
              WdsSetupLogMessageW(
                v100,
                819200,
                L"D",
                0,
                3991,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CDownloadDUUpdates::DoExecuteInternal",
                v99,
                v98,
                0,
                0);
              if ( v105 )
              {
                (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v105 + 24LL))(
                  v105,
                  L"SP_DU_INFO",
                  L"DUDownloadFailedHR",
                  (unsigned int)v106);
                (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v105 + 16LL))(
                  v105,
                  L"SP_DU_INFO",
                  L"DUDownloadFailedReason",
                  L"Failed during download operation");
              }
              v131 = v125;
              throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v131;
            }
          }
          v69 = (struct IExecutionContext *)UnBCL::Object::operator new(0x80u);
          v109 = v69;
          if ( v69 )
          {
            v70 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned long> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned long> *>(v69);
            v116 = (struct SetupPlatform::IDUDownloadProgress *)v70;
          }
          else
          {
            v70 = 0;
            v116 = 0;
          }
          v119 = (struct SetupPlatform::IDownloadCallback *)&UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned long> *>>::`vftable';
          v120 = 0;
          if ( v70 )
            UnBCL::Object::AddRef((UnBCL::Object *)(v70 + *(int *)(*(_QWORD *)(v70 + 8) + 4LL) + 8LL));
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v119);
          v120 = v70;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 40LL))(v70, 1);
          v71 = (*(__int64 (__fastcall **)(_QWORD *))(v110[0] + 32LL))(v110);
          CDownloadDUUpdates::MoveOrCopyUpdates(v61, v71, v70, v108);
        }
        v89 = GetLastError();
        v90 = CurrentIP();
        v91 = ConstructPartialMsgW(
                0x3000000u,
                "CDownloadDUUpdates::DoExecuteInternal: Insufficient space to download and install updates; will skip download.");
        WdsSetupLogMessageW(
          v91,
          819200,
          L"D",
          0,
          3935,
          L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
          L"CDownloadDUUpdates::DoExecuteInternal",
          v90,
          v89,
          0,
          0);
        if ( v105 )
        {
          (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v105 + 24LL))(
            v105,
            L"SP_DU_INFO",
            L"DUDownloadSkippedHR",
            2147942512LL);
          (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v105 + 16LL))(
            v105,
            L"SP_DU_INFO",
            L"DUDownloadSkippedReason",
            L"Insufficient space to download and install updates");
        }
        v128 = v125;
        throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v128;
      }
      v86 = GetLastError();
      v87 = CurrentIP();
      v88 = ConstructPartialMsgW(
              0x2000000u,
              "CDownloadDUUpdates::DoExecuteInternal: Failed to determine space needed by updates; skipping download. hr = 0x%x",
              v106);
      WdsSetupLogMessageW(
        v88,
        819200,
        L"D",
        0,
        3888,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::DoExecuteInternal",
        v87,
        v86,
        0,
        0);
      v127 = v125;
      throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)&v127;
    }
    v36 = GetLastError();
    v37 = CurrentIP();
    v35 = ConstructPartialMsgW(
            0x4000000u,
            "Search was successfully optimized; will skip further filtering for download optimization");
    v104 = v36;
    v103 = (struct ITelemetryActivity *)v37;
    v101 = 3839;
  }
  else
  {
    if ( !v30 )
    {
      v83 = GetLastError();
      v84 = CurrentIP();
      v85 = ConstructPartialMsgW(0x4000000u, "No updates to download. Leaving...");
      WdsSetupLogMessageW(
        v85,
        819200,
        L"D",
        0,
        3819,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CDownloadDUUpdates::DoExecuteInternal",
        v84,
        v83,
        0,
        0);
      if ( v105 )
      {
        (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v105 + 24LL))(
          v105,
          L"SP_DU_INFO",
          L"DUDownloadSkippedHR",
          1);
        (*(void (__fastcall **)(struct ITelemetryActivity *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v105 + 16LL))(
          v105,
          L"SP_DU_INFO",
          L"DUDownloadSkippedReason",
          L"No Updates To Download");
      }
      v135[0] = v125;
      throw (`CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException **)v135;
    }
    v33 = GetLastError();
    v34 = CurrentIP();
    v35 = ConstructPartialMsgW(0x4000000u, "Only TestHook update available.");
    v104 = v33;
    v103 = (struct ITelemetryActivity *)v34;
    v101 = 3829;
  }
  WdsSetupLogMessageW(
    v35,
    819200,
    L"D",
    0,
    v101,
    L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
    L"CDownloadDUUpdates::DoExecuteInternal",
    v103,
    v104,
    0,
    0);
  v11 = v113;
  goto LABEL_31;
}

```

## disassembly

```asm
0x180184d3c  mov     r11, rsp
0x180184d3f  push    rbx
0x180184d40  push    rsi
0x180184d41  push    rdi
0x180184d42  push    r12
0x180184d44  push    r13
0x180184d46  push    r14
0x180184d48  push    r15
0x180184d4a  sub     rsp, 240h
0x180184d51  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x180184d59  mov     rax, cs:__security_cookie
0x180184d60  xor     rax, rsp
0x180184d63  mov     [rsp+278h+var_48], rax
0x180184d6b  mov     [rsp+278h+var_198], r9
0x180184d73  mov     r13d, r8d
0x180184d76  mov     r12d, edx
0x180184d79  mov     rbx, rcx
0x180184d7c  mov     [rsp+278h+var_1C8], rcx
0x180184d84  mov     [rsp+278h+var_90], rcx
0x180184d8c  mov     r14, [rsp+278h+arg_20]
0x180184d94  mov     [rsp+278h+var_1F0], r14
0x180184d9c  mov     rdi, [rsp+278h+arg_28]
0x180184da4  mov     [rsp+278h+var_1D8], rdi
0x180184dac  mov     rax, [rsp+278h+arg_30]
0x180184db4  mov     [rsp+278h+var_1F8], rax
0x180184dbc  mov     rax, [rsp+278h+arg_38]
0x180184dc4  mov     [rsp+278h+var_1B0], rax
0x180184dcc  mov     rax, [rsp+278h+arg_40]
0x180184dd4  mov     [rsp+278h+var_88], rax
0x180184ddc  xor     esi, esi
0x180184dde  mov     [rsp+278h+var_218], esi
0x180184de2  mov     [rsp+278h+var_1B8], esi
0x180184de9  mov     [r11-180h], rsi
0x180184df0  lea     rax, ??_7?$CAutoRelease@PEAUIDUUpdateCollection@DU@@@RAII@@6B@; const RAII::CAutoRelease<DU::IDUUpdateCollection *>::`vftable'
0x180184df7  mov     [r11-188h], rax
0x180184dfe  mov     [rsp+278h+var_1A8], rsi
0x180184e06  mov     ecx, 118h
0x180184e0b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180184e11  mov     [rsp+278h+var_1A0], rax
0x180184e19  test    rax, rax
0x180184e1c  jz      short loc_180184E28
0x180184e1e  mov     rcx, rax; this
0x180184e21  call    ??0CDUPackageCollection@@QEAA@XZ; CDUPackageCollection::CDUPackageCollection(void)
0x180184e26  jmp     short loc_180184E2B
0x180184e28  mov     rax, rsi
0x180184e2b  mov     [rsp+278h+var_1E0], rax
0x180184e33  lea     rax, ??_7?$CAutoRelease@PEAVCDUPackageCollection@@@RAII@@6B@; const RAII::CAutoRelease<CDUPackageCollection *>::`vftable'
0x180184e3a  mov     [rsp+278h+var_1E8], rax
0x180184e42  test    rdi, rdi
0x180184e45  jnz     short loc_180184E73
0x180184e47  test    r14, r14
0x180184e4a  jz      short loc_180184E68
0x180184e4c  mov     rax, [r14]
0x180184e4f  mov     rcx, r14
0x180184e52  mov     rax, [rax+40h]
0x180184e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184e5b  mov     rdi, rax
0x180184e5e  mov     [rsp+278h+var_1D8], rax
0x180184e66  jmp     short loc_180184E73
0x180184e68  mov     rdi, rsi
0x180184e6b  mov     [rsp+278h+var_1D8], rsi
0x180184e73  mov     [rsp+278h+var_210], rsi
0x180184e78  mov     [rsp+278h+var_214], esi
0x180184e7c  lea     rcx, [rsp+278h+var_158]
0x180184e84  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180184e8a  lea     rax, ??_7CXXXXXHandledException@?2??DoExecuteInternal@CDownloadDUUpdates@@IEAAJHHPEAUIDownloadCallback@SetupPlatform@@PEAUIExecutionContext@@PEAUITelemetry@@PEAXPEAUIDUDownloadProgress@4@PEAPEAVCDUPackageCollection@@@Z@6B@; const `CDownloadDUUpdates::DoExecuteInternal(int,int,SetupPlatform::IDownloadCallback *,IExecutionContext *,ITelemetry *,void *,SetupPlatform::IDUDownloadProgress *,CDUPackageCollection * *)'::`3'::CXXXXXHandledException::`vftable'
0x180184e91  mov     [rsp+278h+var_158], rax
0x180184e99  lea     r14, [rbx+160h]
0x180184ea0  mov     rcx, r14
0x180184ea3  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180184ea9  test    rax, rax
0x180184eac  jz      short loc_180184EDF
0x180184eae  test    rdi, rdi
0x180184eb1  jz      short loc_180184EDF
0x180184eb3  mov     rax, [rdi]
0x180184eb6  mov     r15, [rax+30h]
0x180184eba  mov     rcx, r14
0x180184ebd  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180184ec3  mov     rcx, rax
0x180184ec6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180184ecc  lea     r8, [rsp+278h+var_210]
0x180184ed1  mov     rdx, rax
0x180184ed4  mov     rcx, rdi
0x180184ed7  mov     rax, r15
0x180184eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184edf  mov     rcx, [rsp+278h+var_210]
0x180184ee4  lea     r15, aSpDuInfo; "SP_DU_INFO"
0x180184eeb  test    rcx, rcx
0x180184eee  jz      short loc_180184F06
0x180184ef0  mov     rax, [rcx]
0x180184ef3  lea     r8, aDusearchanddow_0; "DUSearchAndDownloadStartTime"
0x180184efa  mov     rdx, r15
0x180184efd  mov     rax, [rax+20h]
0x180184f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184f06  test    r12d, r12d
0x180184f09  jnz     short loc_180184F27
0x180184f0b  lea     rcx, [rsp+278h+var_1B8]; int *
0x180184f13  call    ?SPInitializeDU@@YAJAEAH@Z; SPInitializeDU(int &)
0x180184f18  mov     r14d, eax
0x180184f1b  mov     [rsp+278h+var_218], eax
0x180184f1f  test    eax, eax
0x180184f21  js      loc_180185E42
0x180184f27  cmp     [rbx+140h], rsi
0x180184f2e  jnz     loc_18018506E
0x180184f34  mov     [rsp+278h+var_170], rsi
0x180184f3c  lea     r12, ??_7?$CAutoDelete@PEAVCImageInfoSet@@@RAII@@6B@; const RAII::CAutoDelete<CImageInfoSet *>::`vftable'
0x180184f43  mov     [rsp+278h+var_178], r12
0x180184f4b  lea     rcx, [rsp+278h+var_178]
0x180184f53  call    ??I?$CAutoCleanupBase@PEAVVdsVolumePathEnumerator@@@RAII@@UEBAPEBQEAVVdsVolumePathEnumerator@@XZ; RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(void)
0x180184f58  mov     rdi, rax
0x180184f5b  lea     r14, [rbx+148h]
0x180184f62  mov     rcx, r14
0x180184f65  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180184f6b  mov     rcx, rax
0x180184f6e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180184f74  mov     r8, rdi; struct CImageInfoSet **
0x180184f77  xor     edx, edx; struct SetupPlatform::WIM_IMAGE_OPTIONS *
0x180184f79  mov     rcx, rax; unsigned __int16 *
0x180184f7c  call    ?CreateFromWIM@CImageInfoSet@@SAJPEBGPEAUWIM_IMAGE_OPTIONS@SetupPlatform@@PEAPEAV1@@Z; CImageInfoSet::CreateFromWIM(ushort const *,SetupPlatform::WIM_IMAGE_OPTIONS *,CImageInfoSet * *)
0x180184f81  mov     edi, eax
0x180184f83  mov     [rsp+278h+var_218], eax
0x180184f87  test    eax, eax
0x180184f89  js      loc_180185EDF
0x180184f8f  mov     ecx, 0C8h
0x180184f94  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180184f9a  mov     rdi, rax
0x180184f9d  mov     [rsp+278h+var_208], rax
0x180184fa2  test    rax, rax
0x180184fa5  jz      short loc_180184FEE
0x180184fa7  mov     rcx, [rsp+278h+var_178]
0x180184faf  mov     rax, [rcx+18h]
0x180184fb3  lea     rcx, [rsp+278h+var_178]
0x180184fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184fc0  mov     r8, rax
0x180184fc3  mov     rcx, [rax]
0x180184fc6  mov     edx, [rbx+158h]
0x180184fcc  mov     r14d, 1
0x180184fd2  sub     edx, r14d
0x180184fd5  mov     rax, [rcx+8]
0x180184fd9  mov     rcx, r8
0x180184fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184fe1  mov     rdx, rax; struct SetupPlatform::IImageInfo *
0x180184fe4  mov     rcx, rdi; this
0x180184fe7  call    ??0CDUImageInfo@@QEAA@PEAUIImageInfo@SetupPlatform@@@Z; CDUImageInfo::CDUImageInfo(SetupPlatform::IImageInfo *)
0x180184fec  jmp     short loc_180184FF7
0x180184fee  mov     rax, rsi
0x180184ff1  mov     r14d, 1
0x180184ff7  mov     rdx, rax
0x180184ffa  lea     rcx, [rsp+278h+var_120]
0x180185002  call    ??0?$SmartPtr@VCDUImageInfo@@@UnBCL@@QEAA@PEAVCDUImageInfo@@@Z; UnBCL::SmartPtr<CDUImageInfo>::SmartPtr<CDUImageInfo>(CDUImageInfo *)
0x180185007  nop
0x180185008  lea     rcx, [rbx+138h]
0x18018500f  lea     rdx, [rsp+278h+var_120]
0x180185017  call    ??4?$SmartPtr@V?$ArrayList@PEAVCRegCreationData@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>> const &)
0x18018501c  nop
0x18018501d  lea     rax, ??_7?$SmartPtr@VCDUImageInfo@@@UnBCL@@6B@; const UnBCL::SmartPtr<CDUImageInfo>::`vftable'
0x180185024  mov     [rsp+278h+var_120], rax
0x18018502c  lea     rcx, [rsp+278h+var_120]
0x180185034  call    ?DeAssign@?$SmartPtr@V?$Hashtable@KPEAUIVdsVDisk@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::Hashtable<ulong,IVdsVDisk *>>::DeAssign(void)
0x180185039  nop
0x18018503a  mov     [rsp+278h+var_178], r12
0x180185042  mov     rdx, [rsp+278h+var_170]
0x18018504a  test    rdx, rdx
0x18018504d  jz      short loc_180185074
0x18018504f  mov     rax, [rdx+10h]
0x180185053  movsxd  rcx, dword ptr [rax+4]
0x180185057  add     rcx, 10h
0x18018505b  add     rcx, rdx
0x18018505e  mov     rax, [rcx]
0x180185061  mov     edx, r14d
0x180185064  mov     rax, [rax]
0x180185067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018506c  jmp     short loc_180185074
0x18018506e  mov     r14d, 1
0x180185074  mov     rax, [rsp+278h+var_1E8]
0x18018507c  lea     rcx, [rsp+278h+var_1E8]
0x180185084  mov     rax, [rax+20h]
0x180185088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018508d  mov     rdx, rax; struct CDUPackageCollection *
0x180185090  mov     rcx, rbx; this
0x180185093  call    ?CheckTestHook@CDownloadDUUpdates@@IEAAHPEAVCDUPackageCollection@@@Z; CDownloadDUUpdates::CheckTestHook(CDUPackageCollection *)
0x180185098  mov     edi, eax
0x18018509a  mov     [rsp+278h+var_200], esi
0x18018509e  mov     dword ptr [rsp+278h+var_208], esi
0x1801850a2  mov     rcx, [rsp+278h+var_188]
0x1801850aa  mov     rax, [rcx+8]
0x1801850ae  lea     rcx, [rsp+278h+var_188]
0x1801850b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801850bb  lea     rcx, [rsp+278h+var_208]
0x1801850c0  mov     [rsp+278h+var_258], rcx; int *
0x1801850c5  lea     r9, [rsp+278h+var_200]; int *
0x1801850ca  mov     r8, rax; struct DU::IDUUpdateCollection **
0x1801850cd  mov     edx, r13d; int
0x1801850d0  mov     rcx, rbx; this
0x1801850d3  call    ?SearchUpdates@CDownloadDUUpdates@@IEAAJHPEAPEAUIDUUpdateCollection@DU@@PEAJPEAH@Z; CDownloadDUUpdates::SearchUpdates(int,DU::IDUUpdateCollection * *,long *,int *)
0x1801850d8  mov     r12d, eax
0x1801850db  mov     [rsp+278h+var_218], eax
0x1801850df  test    eax, eax
0x1801850e1  js      loc_180185F90
0x1801850e7  cmp     [rsp+278h+var_200], esi
0x1801850eb  jnz     short loc_18018514B
0x1801850ed  test    edi, edi
0x1801850ef  jz      loc_18018604B
0x1801850f5  call    cs:__imp_GetLastError
0x1801850fb  mov     edi, eax
0x1801850fd  call    cs:__imp_CurrentIP
0x180185103  mov     rbx, rax
0x180185106  lea     rdx, aOnlyTesthookUp; "Only TestHook update available."
0x18018510d  mov     ecx, 4000000h; unsigned int
0x180185112  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180185117  mov     [rsp+278h+var_228], esi
0x18018511b  mov     [rsp+278h+var_230], rsi
0x180185120  mov     [rsp+278h+var_238], edi
0x180185124  mov     [rsp+278h+var_240], rbx
0x180185129  lea     rbx, aCdownloadduupd_13; "CDownloadDUUpdates::DoExecuteInternal"
0x180185130  mov     [rsp+278h+var_248], rbx
0x180185135  lea     rbx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18018513c  mov     [rsp+278h+var_250], rbx
0x180185141  mov     dword ptr [rsp+278h+var_258], 0EF5h
0x180185149  jmp     short loc_1801851A9
0x18018514b  cmp     dword ptr [rsp+278h+var_208], esi
0x18018514f  jz      loc_1801851D5
0x180185155  call    cs:__imp_GetLastError
0x18018515b  mov     edi, eax
0x18018515d  call    cs:__imp_CurrentIP
0x180185163  mov     rbx, rax
0x180185166  lea     rdx, aSearchWasSucce; "Search was successfully optimized; will"...
0x18018516d  mov     ecx, 4000000h; unsigned int
0x180185172  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180185177  mov     [rsp+278h+var_228], esi
0x18018517b  mov     [rsp+278h+var_230], rsi
0x180185180  mov     [rsp+278h+var_238], edi
0x180185184  mov     [rsp+278h+var_240], rbx
0x180185189  lea     rbx, aCdownloadduupd_13; "CDownloadDUUpdates::DoExecuteInternal"
0x180185190  mov     [rsp+278h+var_248], rbx
0x180185195  lea     rbx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18018519c  mov     [rsp+278h+var_250], rbx
0x1801851a1  mov     dword ptr [rsp+278h+var_258], 0EFFh
0x1801851a9  xor     r9d, r9d
0x1801851ac  lea     r13, aD_0; "D"
0x1801851b3  mov     r8, r13
0x1801851b6  mov     r12d, 0C8000h
0x1801851bc  mov     edx, r12d
0x1801851bf  mov     rcx, rax
0x1801851c2  call    cs:__imp_WdsSetupLogMessageW
0x1801851c8  mov     rbx, [rsp+278h+var_1C8]
0x1801851d0  jmp     loc_1801852E4
0x1801851d5  test    r13d, r13d
0x1801851d8  jz      loc_1801852D7
0x1801851de  call    cs:__imp_GetLastError
0x1801851e4  mov     edi, eax
0x1801851e6  call    cs:__imp_CurrentIP
0x1801851ec  mov     rbx, rax
0x1801851ef  lea     rdx, aAttemptingToFi_0; "Attempting to filter the update collect"...
0x1801851f6  mov     ecx, 4000000h; unsigned int
0x1801851fb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180185200  mov     [rsp+278h+var_228], esi
0x180185204  mov     [rsp+278h+var_230], rsi
0x180185209  mov     [rsp+278h+var_238], edi
0x18018520d  mov     [rsp+278h+var_240], rbx
0x180185212  lea     rbx, aCdownloadduupd_13; "CDownloadDUUpdates::DoExecuteInternal"
0x180185219  mov     [rsp+278h+var_248], rbx
0x18018521e  lea     rbx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180185225  mov     [rsp+278h+var_250], rbx
0x18018522a  mov     dword ptr [rsp+278h+var_258], 0F03h
0x180185232  xor     r9d, r9d
0x180185235  lea     r13, aD_0; "D"
0x18018523c  mov     r8, r13
0x18018523f  mov     r12d, 0C8000h
0x180185245  mov     edx, r12d
0x180185248  mov     rcx, rax
0x18018524b  call    cs:__imp_WdsSetupLogMessageW
0x180185251  mov     rbx, [rsp+278h+var_210]
0x180185256  mov     rax, [rsp+278h+var_188]
0x18018525e  lea     rcx, [rsp+278h+var_188]
0x180185266  mov     rax, [rax+20h]
0x18018526a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018526f  mov     rdx, rax; struct DU::IDUUpdateCollection *
0x180185272  mov     [rsp+278h+var_240], rbx; struct ITelemetryActivity *
0x180185277  mov     rax, [rsp+278h+var_1D8]
0x18018527f  mov     [rsp+278h+var_248], rax; struct ITelemetry *
0x180185284  mov     r9, [rsp+278h+var_1B0]
0x18018528c  mov     [rsp+278h+var_250], r9; struct SetupPlatform::IDUDownloadProgress *
0x180185291  mov     r9, [rsp+278h+var_1F8]
0x180185299  mov     [rsp+278h+var_258], r9; void *
0x18018529e  mov     r9, [rsp+278h+var_198]; struct SetupPlatform::IDownloadCallback *
0x1801852a6  lea     r8, [rsp+278h+var_200]; int *
0x1801852ab  mov     rbx, [rsp+278h+var_1C8]
0x1801852b3  mov     rcx, rbx; this
0x1801852b6  call    ?FilterUpdates@CDownloadDUUpdates@@IEAAJPEAUIDUUpdateCollection@DU@@PEAJPEAUIDownloadCallback@SetupPlatform@@PEAXPEAUIDUDownloadProgress@5@PEAUITelemetry@@PEAUITelemetryActivity@@@Z; CDownloadDUUpdates::FilterUpdates(DU::IDUUpdateCollection *,long *,SetupPlatform::IDownloadCallback *,void *,SetupPlatform::IDUDownloadProgress *,ITelemetry *,ITelemetryActivity *)
0x1801852bb  mov     dword ptr [rsp+278h+var_208], eax
0x1801852bf  mov     [rsp+278h+var_218], eax
0x1801852c3  test    eax, eax
0x1801852c5  js      loc_18018612A
0x1801852cb  cmp     [rsp+278h+var_200], esi
0x1801852cf  jz      loc_1801861BE
0x1801852d5  jmp     short loc_1801852E8
0x1801852d7  lea     r13, aD_0; "D"
0x1801852de  mov     r12d, 0C8000h
0x1801852e4  cmp     [rsp+278h+var_200], esi
  ... truncated ...
```
