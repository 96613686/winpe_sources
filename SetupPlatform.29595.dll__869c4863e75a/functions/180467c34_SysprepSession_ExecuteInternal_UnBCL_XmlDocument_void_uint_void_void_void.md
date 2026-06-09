# SysprepSession::ExecuteInternal(UnBCL::XmlDocument *,void (*)(uint,void *),void *,void *)

- ea: `0x180467c34`
- end: `0x180468d8b`
- name: `?ExecuteInternal@SysprepSession@@AEAAKPEAVXmlDocument@UnBCL@@P6AXIPEAX@Z11@Z`
- size: `4439`
- prototype: `unsigned int __fastcall(SysprepSession *__hidden this, struct UnBCL::XmlDocument *, void (*)(unsigned int, void *), void *, HANDLE hHandle)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180465c38`

## callees

- `0x180001f68`
- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x18005dd24`
- `0x18028f84c`
- `0x18028f8c0`
- `0x1802920f0`
- `0x18029214c`
- `0x180460598`
- `0x180461cc0`
- `0x1804624b0`
- `0x180462700`
- `0x180462f18`
- `0x1804654e8`
- `0x180465fc8`
- `0x180467c34`
- `0x18046926c`
- `0x18046a528`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180467d3e`
- `KERNEL32!GetLastError` at `0x180467e14`
- `KERNEL32!GetLastError` at `0x1804680bc`
- `KERNEL32!GetLastError` at `0x180468173`
- `KERNEL32!GetLastError` at `0x1804683a2`
- `KERNEL32!GetLastError` at `0x18046848c`
- `KERNEL32!GetLastError` at `0x18046867c`
- `KERNEL32!GetLastError` at `0x180468776`
- `KERNEL32!GetLastError` at `0x18046882a`
- `KERNEL32!GetLastError` at `0x1804689aa`
- `KERNEL32!GetLastError` at `0x180468a97`
- `KERNEL32!GetLastError` at `0x180468b54`
- `KERNEL32!GetLastError` at `0x180468c14`
- `KERNEL32!GetLastError` at `0x180467d3e`
- `KERNEL32!GetLastError` at `0x180467e14`
- `KERNEL32!GetLastError` at `0x1804680bc`
- `KERNEL32!GetLastError` at `0x180468173`
- `KERNEL32!GetLastError` at `0x1804683a2`
- `KERNEL32!GetLastError` at `0x18046848c`
- `KERNEL32!GetLastError` at `0x18046867c`
- `KERNEL32!GetLastError` at `0x180468776`
- `KERNEL32!GetLastError` at `0x18046882a`
- `KERNEL32!GetLastError` at `0x1804689aa`
- `KERNEL32!GetLastError` at `0x180468a97`
- `KERNEL32!GetLastError` at `0x180468b54`
- `KERNEL32!GetLastError` at `0x180468c14`
- `KERNEL32!WaitForSingleObject` at `0x180468261`
- `KERNEL32!WaitForSingleObject` at `0x180468261`
- `unbcl!?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z` at `0x180467db6`
- `unbcl!?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z` at `0x180467db6`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1804685cd`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1804685cd`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180467ce9`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180467ce9`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180467f07`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180467f2f`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180467f07`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180467f2f`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180468063`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180468063`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18046803c`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18046803c`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180467dec`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180467e29`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180467fd8`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180468000`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180467dec`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180467e29`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180467fd8`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180468000`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180467dc4`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180467dc4`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180467dd4`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180467dd4`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180467de0`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468a66`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468b28`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468be5`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468ca5`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468cf5`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180467de0`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468a66`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468b28`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468be5`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468ca5`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468cf5`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180467d0b`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180467d0b`
- `unbcl!?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z` at `0x180467f7d`
- `unbcl!?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z` at `0x180467f7d`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180467cae`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180467f69`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x18046809e`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180467cae`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x180467f69`
- `unbcl!?get_Count@XmlNodeList@UnBCL@@QEAAHXZ` at `0x18046809e`
- `unbcl!?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z` at `0x180467c8b`
- `unbcl!?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z` at `0x180467c8b`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x180468648`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@K@Z` at `0x180468648`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180467fc3`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180467fc3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180467c7f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180467d16`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046802a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046818c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804682ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804683b6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468471`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804684a0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046854f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804685b2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804685e5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804685f7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046865d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468690`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046878a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046883e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468957`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804689be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468a42`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468aab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468b68`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468c28`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180467c7f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180467d16`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046802a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046818c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804682ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804683b6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468471`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804684a0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046854f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804685b2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804685e5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804685f7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046865d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468690`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046878a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18046883e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468957`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1804689be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468a42`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468aab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468b68`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180468c28`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180467d01`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180467d01`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180467cdf`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180467cdf`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180467ec3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180467f95`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18046862d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180467ec3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180467f95`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18046862d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180467da6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180467da6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180467e4f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468195`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1804683bf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18046847a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1804684a9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468558`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468699`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468793`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468847`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468960`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1804689c7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468ab4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468b71`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468c31`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180467e4f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468195`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1804683bf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18046847a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1804684a9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468558`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468699`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468793`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468847`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468960`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1804689c7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468ab4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468b71`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180468c31`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18046861c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468a71`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468b33`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468bf0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468cb0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468cda`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468d00`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468d2a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468d42`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18046861c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468a71`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468b33`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468bf0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468cb0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468cda`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468d00`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468d2a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180468d42`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180467c74`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180467cf6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1804685da`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180467c74`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180467cf6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1804685da`
- `WDSCORE!WdsSetupLogMessageW` at `0x180467d9c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180467ea5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18046812a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1804681ff`
- `WDSCORE!WdsSetupLogMessageW` at `0x180468425`
- `WDSCORE!WdsSetupLogMessageW` at `0x18046850f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1804686ff`
- `WDSCORE!WdsSetupLogMessageW` at `0x1804687f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1804688ad`
- `WDSCORE!WdsSetupLogMessageW` at `0x180468a2d`

## string_xrefs

- `0x180468d67`: `void __cdecl SysprepSession::SetOfflineStateInRegistry(class UnBCL::String *,unsigned long)`
- `0x1804680cd`: `After sorting, components will be excuted in the following order:`
- `0x180467d4f`: `Test mode enabled, following components will be skipped:`
- `0x1804683c8`: `SysprepSession::ExecuteInternal: Component %s does not have offline-capable module, will run it online`
- `0x180468850`: `Component %s ran offline, but required reboot; running pending parts`
- `0x1804686a2`: `Component %s successfully ran offline; skipping it online`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall SysprepSession::ExecuteInternal(
        SysprepSession *this,
        struct UnBCL::XmlDocument *a2,
        void (*a3)(unsigned int, void *),
        SysprepComponent *a4,
        HANDLE hHandle)
{
  struct UnBCL::String *XPathForSelection; // rax
  struct UnBCL::String *P; // rax
  struct UnBCL::XmlNodeList *v8; // rax
  UnBCL::XmlNodeList *v9; // r14
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *EnvironmentVar; // rax
  DWORD LastError; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int i; // esi
  __int64 v18; // rax
  int (__fastcall ***v19)(_QWORD); // rcx
  DWORD v20; // edi
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  UnBCL::String **v24; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v26; // rax
  SysprepComponent *v27; // rax
  __int64 v28; // r15
  __int64 v29; // r13
  int j; // r12d
  struct UnBCL::XmlNode *Item; // rax
  SysprepComponent *v32; // rax
  __int64 v33; // rax
  UnBCL::Object *v34; // rdi
  int k; // esi
  __int64 v36; // rax
  int (__fastcall ***v37)(_QWORD); // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  const struct UnBCL::String *v40; // rbx
  const struct UnBCL::String *v41; // rax
  __int64 v42; // rbx
  void (__fastcall *v43)(__int64, UnBCL::Object *); // rsi
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  int m; // r12d
  int (__fastcall ***v48)(_QWORD); // rcx
  __int64 v49; // rcx
  __int64 v50; // rbx
  DWORD v51; // r14d
  __int64 v52; // rsi
  int v53; // edi
  UnBCL::String *v54; // rax
  const char *v55; // rax
  struct tagLOG_PARTIAL_MSG *v56; // rax
  int v57; // ebx
  int (__fastcall ***v58)(_QWORD); // rcx
  __int64 v59; // rcx
  __int64 v60; // rsi
  char v61; // di
  int n; // ebx
  int (__fastcall ***v63)(_QWORD); // rcx
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r14
  SysprepSession *v67; // r12
  __int64 v68; // rcx
  struct UnBCL::String *v69; // rax
  unsigned int v70; // r12d
  int v71; // ebx
  int (__fastcall ***v72)(_QWORD); // rcx
  __int64 v73; // rcx
  struct SysprepAction **v74; // rax
  struct SysprepAction *v75; // rbx
  unsigned int v76; // eax
  unsigned int v77; // esi
  DWORD v78; // edi
  __int64 v79; // rbx
  UnBCL::String *v80; // rax
  const char *v81; // rax
  struct tagLOG_PARTIAL_MSG *v82; // rax
  UnBCL::String *v83; // rax
  const unsigned __int16 *v84; // rax
  int v85; // ecx
  int v86; // r8d
  int v87; // r9d
  __int16 *v88; // rdx
  DWORD v89; // edi
  __int64 v90; // rbx
  UnBCL::String *v91; // rax
  const unsigned __int16 *v92; // rax
  struct tagLOG_PARTIAL_MSG *v93; // rax
  UnBCL::String *v94; // rax
  char v95; // cl
  unsigned int v96; // ebx
  struct UnBCL::String *v97; // rdi
  struct UnBCL::String *v98; // rax
  struct UnBCL::String *v99; // rbx
  struct UnBCL::String *v100; // rax
  unsigned int v101; // edi
  UnBCL::Win32Exception *v102; // rax
  UnBCL::Win32Exception *v103; // rbx
  struct UnBCL::String *v104; // rax
  unsigned int OfflineStateFromRegistry; // eax
  char v106; // si
  DWORD v107; // edi
  __int64 v108; // rbx
  UnBCL::String *v109; // rax
  const char *v110; // rax
  struct tagLOG_PARTIAL_MSG *v111; // rax
  int v112; // esi
  __int64 v113; // rbx
  int (__fastcall ***v114)(_QWORD); // rcx
  __int64 v115; // rcx
  __int64 v116; // rax
  struct SysprepAction *v117; // rdx
  DWORD v118; // edi
  __int64 v119; // rbx
  UnBCL::String *v120; // rax
  const char *v121; // rax
  struct tagLOG_PARTIAL_MSG *v122; // rax
  unsigned int v123; // r12d
  DWORD v124; // edi
  __int64 v125; // rbx
  UnBCL::String *v126; // rax
  const char *v127; // rax
  struct tagLOG_PARTIAL_MSG *v128; // rax
  int v129; // r12d
  __int64 v130; // rbx
  int (__fastcall ***v131)(_QWORD); // rcx
  __int64 v132; // rcx
  __int64 v133; // rax
  struct SysprepAction *v134; // rdi
  int v135; // ebx
  UnBCL::String *v136; // rax
  int v137; // ecx
  int v138; // r8d
  int v139; // r9d
  DWORD v140; // edi
  __int64 v141; // rbx
  UnBCL::String *v142; // rax
  const char *v143; // rax
  struct tagLOG_PARTIAL_MSG *v144; // rax
  struct UnBCL::String *v145; // rax
  DWORD v146; // edi
  __int64 v147; // rbx
  UnBCL::String *v148; // rax
  const char *v149; // rax
  struct tagLOG_PARTIAL_MSG *v150; // rax
  DWORD v151; // edi
  __int64 v152; // rbx
  UnBCL::String *v153; // rax
  const char *v154; // rax
  struct tagLOG_PARTIAL_MSG *v155; // rax
  DWORD v156; // edi
  __int64 v157; // rbx
  UnBCL::String *v158; // rax
  const char *v159; // rax
  struct tagLOG_PARTIAL_MSG *v160; // rax
  void **v162; // [rsp+68h] [rbp-81h] BYREF
  UnBCL::Object *v163; // [rsp+70h] [rbp-79h]
  void **v164; // [rsp+78h] [rbp-71h] BYREF
  __int64 v165; // [rsp+80h] [rbp-69h]
  int v166; // [rsp+88h] [rbp-61h]
  int v167; // [rsp+8Ch] [rbp-5Dh]
  _BYTE v168[16]; // [rsp+90h] [rbp-59h] BYREF
  _QWORD v169[2]; // [rsp+A0h] [rbp-49h] BYREF
  _BYTE v170[16]; // [rsp+B0h] [rbp-39h] BYREF
  char v171[8]; // [rsp+C0h] [rbp-29h] BYREF
  UnBCL::XmlNodeList *v172; // [rsp+C8h] [rbp-21h]
  _BYTE v173[16]; // [rsp+D0h] [rbp-19h] BYREF
  _BYTE v174[24]; // [rsp+E0h] [rbp-9h] BYREF
  __int64 v175; // [rsp+F8h] [rbp+Fh]
  char v177; // [rsp+158h] [rbp+6Fh]
  SysprepComponent *pExceptionObject; // [rsp+160h] [rbp+77h] BYREF

  pExceptionObject = a4;
  v175 = -2;
  XPathForSelection = SysprepSession::CreateXPathForSelection(this);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v173, XPathForSelection);
  P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v173);
  v8 = UnBCL::XmlNode::SelectNodes(a2, P);
  UnBCL::SmartPtr<UnBCL::XmlNodeList>::SmartPtr<UnBCL::XmlNodeList>(v171, v8);
  v9 = v172;
  if ( !v172 || !UnBCL::XmlNodeList::get_Count(v172) )
  {
    UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(v171);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v173);
    return 0;
  }
  v177 = 0;
  v164 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
  v165 = 0;
  v10 = (const struct UnBCL::String *)UnBCL::String::String(
                                        (UnBCL::String *)v174,
                                        L"SYSPREP_PLATFORM_SESSION_TEST_SKIPLIST");
  EnvironmentVar = UnBCL::Environment::GetEnvironmentVar(v10);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v170, EnvironmentVar);
  UnBCL::String::~String((UnBCL::String *)v174);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v168);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v170) )
  {
    LastError = GetLastError();
    v13 = CurrentIP();
    v14 = ConstructPartialMsgW(0x4000000u, "Test mode enabled, following components will be skipped:");
    WdsSetupLogMessageW(
      v14,
      983040,
      L"D",
      0,
      561,
      L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
      L"SysprepSession::ExecuteInternal",
      v13,
      LastError,
      0,
      0);
    v15 = UnBCL::SmartPtr<UnBCL::String>::operator->(v170);
    v16 = UnBCL::String::Split(v15, L";");
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(&v162, v16);
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v168, &v162);
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(&v162);
    for ( i = 0; ; ++i )
    {
      v18 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v168);
      v19 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v18 + 8) + 12LL) + v18 + 8);
      if ( i >= (**v19)(v19) )
        break;
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v168);
      v23 = *(int *)(*(_QWORD *)(v22 + 8) + 16LL) + v22 + 8;
      v24 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 24LL))(v23, (unsigned int)i);
      CString = (const char *)UnBCL::String::get_CString(*v24);
      v26 = ConstructPartialMsgW(0x4000000u, "  Name: %s", CString);
      WdsSetupLogMessageW(
        v26,
        983040,
        L"D",
        0,
        565,
        L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
        L"SysprepSession::ExecuteInternal",
        v21,
        v20,
        0,
        0);
    }
  }
  v27 = (SysprepComponent *)UnBCL::Object::operator new(0x80u);
  pExceptionObject = v27;
  if ( v27 )
    v28 = UnBCL::ArrayList<SysprepComponent *>::ArrayList<SysprepComponent *>(v27);
  else
    v28 = 0;
  v162 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
  v163 = 0;
  v29 = v28 + 8;
  if ( v28 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v28 + *(int *)(*(_QWORD *)v29 + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v162);
  v163 = (UnBCL::Object *)v28;
  if ( v28 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v28 + *(int *)(*(_QWORD *)v29 + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v164);
  v165 = v28;
  v162 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v162);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 40LL))(v28, 1);
  for ( j = 0; j < UnBCL::XmlNodeList::get_Count(v9); ++j )
  {
    Item = UnBCL::XmlNodeList::get_Item(v9, j);
    UnBCL::SmartPtr<UnBCL::XmlNode>::SmartPtr<UnBCL::XmlNode>(v169, Item);
    v32 = (SysprepComponent *)UnBCL::Object::operator new(0x38u);
    pExceptionObject = v32;
    if ( v32 )
      v32 = SysprepComponent::SysprepComponent(v32, (struct UnBCL::XmlNode *)v169[1]);
    UnBCL::SmartPtr<SysprepComponent>::SmartPtr<SysprepComponent>(&v162, v32);
    v33 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v168);
    v34 = v163;
    if ( v33 )
    {
      for ( k = 0; ; ++k )
      {
        v36 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v168);
        v37 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v36 + 8) + 12LL) + v36 + 8);
        if ( k >= (**v37)(v37) )
          break;
        v38 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v168);
        v39 = *(int *)(*(_QWORD *)(v38 + 8) + 16LL) + v38 + 8;
        v40 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 24LL))(
                                                v39,
                                                (unsigned int)k);
        v41 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v34 + 16);
        if ( !UnBCL::String::Compare(v41, v40, 1) )
          goto LABEL_25;
      }
    }
    v42 = *(int *)(*(_QWORD *)v29 + 16LL);
    v43 = *(void (__fastcall **)(__int64, UnBCL::Object *))(*(_QWORD *)(v42 + v28 + 8) + 40LL);
    if ( v34 )
    {
      UnBCL::Object::DecRef(v34);
      v163 = 0;
    }
    v43(v42 + v28 + 8, v34);
LABEL_25:
    UnBCL::SmartPtr<SysprepComponent>::~SmartPtr<SysprepComponent>(&v162);
    UnBCL::SmartPtr<UnBCL::XmlNode>::~SmartPtr<UnBCL::XmlNode>(v169);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 88LL))(v28);
  v44 = GetLastError();
  v45 = CurrentIP();
  v46 = ConstructPartialMsgW(0x4000000u, "After sorting, components will be excuted in the following order:");
  WdsSetupLogMessageW(
    v46,
    983040,
    L"D",
    0,
    597,
    L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
    L"SysprepSession::ExecuteInternal",
    v45,
    v44,
    0,
    0);
  for ( m = 0; ; ++m )
  {
    v48 = (int (__fastcall ***)(_QWORD))(v29 + *(int *)(*(_QWORD *)v29 + 12LL));
    if ( m >= (**v48)(v48) )
      break;
    v49 = v28 + *(int *)(*(_QWORD *)v29 + 16LL) + 8LL;
    v50 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 24LL))(v49, (unsigned int)m);
    v51 = GetLastError();
    v52 = CurrentIP();
    v53 = *(_DWORD *)(v50 + 32);
    v54 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v50 + 16);
    v55 = (const char *)UnBCL::String::get_CString(v54);
    v56 = ConstructPartialMsgW(0x4000000u, "  Name: %s, Order: %d", v55, v53);
    WdsSetupLogMessageW(
      v56,
      983040,
      L"D",
      0,
      601,
      L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
      L"SysprepSession::ExecuteInternal",
      v52,
      v51,
      0,
      0);
  }
  v57 = 0;
LABEL_30:
  v167 = v57;
  v58 = (int (__fastcall ***)(_QWORD))(v29 + *(int *)(*(_QWORD *)v29 + 12LL));
  if ( v57 >= (**v58)(v58) )
  {
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
    v164 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v164);
    UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(v171);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v173);
    return v177 != 0 ? 0xBC2 : 0;
  }
  v59 = v28 + *(int *)(*(_QWORD *)v29 + 16LL) + 8LL;
  v60 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v59 + 24LL))(v59, (unsigned int)v57);
  v169[0] = v60;
  if ( hHandle && !WaitForSingleObject(hHandle, 0) )
  {
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v168);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
    v164 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v164);
    v77 = 1223;
    goto LABEL_99;
  }
  v61 = 0;
  for ( n = 0; ; ++n )
  {
    v63 = (int (__fastcall ***)(_QWORD))(*(_QWORD *)(v60 + 48)
                                       + 8LL
                                       + *(int *)(*(_QWORD *)(*(_QWORD *)(v60 + 48) + 8LL) + 12LL));
    if ( n >= (**v63)(v63) )
      break;
    v64 = *(_QWORD *)(v60 + 48) + *(int *)(*(_QWORD *)(*(_QWORD *)(v60 + 48) + 8LL) + 16LL) + 8LL;
    v65 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v64 + 24LL))(v64, (unsigned int)n);
    if ( *(_DWORD *)(*(_QWORD *)v65 + 32LL) == 9 )
    {
      v61 = *(_BYTE *)(*(_QWORD *)v65 + 36LL);
      if ( v61 )
        break;
    }
  }
  LOBYTE(pExceptionObject) = v61;
  v66 = v60 + 16;
  v67 = this;
  v68 = v60 + 16;
  if ( *((_BYTE *)this + 120) )
  {
    v69 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v68);
    SysprepSession::RemoveOfflineStateFromRegistry(this, v69);
    v70 = 0;
    v71 = 0;
    while ( 1 )
    {
      v166 = v71;
      v72 = (int (__fastcall ***)(_QWORD))(*(_QWORD *)(v60 + 48)
                                         + 8LL
                                         + *(int *)(*(_QWORD *)(*(_QWORD *)(v60 + 48) + 8LL) + 12LL));
      if ( v71 >= (**v72)(v72) )
      {
        v95 = v177;
        if ( (v70 & 6) != 0 )
          v95 = 1;
        v177 = v95;
        v96 = v70 | 1;
        if ( (v70 & 6) != 0 )
          v96 = v70;
        v97 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
        if ( v97 )
        {
          v98 = UnBCL::String::Format(L"%d", v96);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v174, v98);
          v99 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v174);
          v100 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 16);
          v101 = ActionPlatform::SetValue((SysprepSession *)((char *)this + 64), v100, v97, 4u, v99);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v174);
          if ( v101 )
          {
            v102 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
            v103 = v102;
            if ( v102 )
            {
              UnBCL::Win32Exception::Win32Exception(v102, v101);
              *(_QWORD *)v103 = &UnBCL::Win32Exception::`local vftable';
            }
            else
            {
              v103 = 0;
            }
            pExceptionObject = (SysprepComponent *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                     v103,
                                                     "void __cdecl SysprepSession::SetOfflineStateInRegistry(class UnBCL:"
                                                     ":String *,unsigned long)");
            throw (UnBCL::Win32Exception **)&pExceptionObject;
          }
        }
LABEL_94:
        v57 = v167 + 1;
        goto LABEL_30;
      }
      v73 = *(_QWORD *)(v60 + 48) + *(int *)(*(_QWORD *)(*(_QWORD *)(v60 + 48) + 8LL) + 16LL) + 8LL;
      v74 = (struct SysprepAction **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 24LL))(
                                       v73,
                                       (unsigned int)v71);
      v75 = *v74;
      if ( *((_BYTE *)*v74 + 36) )
      {
        v76 = SysprepSession::ExecuteAction(this, *v74, 0, hHandle);
        v77 = v76;
        if ( *((_DWORD *)v75 + 8) == 9 && v76 == 3010 )
        {
          v70 |= 2u;
        }
        else if ( v76 )
        {
          v146 = GetLastError();
          v147 = CurrentIP();
          v148 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
          v149 = (const char *)UnBCL::String::get_CString(v148);
          v150 = ConstructPartialMsgW(
                   0x2000000u,
                   "SysprepSession::ExecuteInternal: Error in executing action for %s; dwRet = 0x%x",
                   v149,
                   v77);
          WdsSetupLogMessageW(
            v150,
            983040,
            L"D",
            0,
            661,
            L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
            L"SysprepSession::ExecuteInternal",
            v147,
            v146,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v168);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
          v164 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v164);
          goto LABEL_99;
        }
        v60 = v169[0];
      }
      else if ( *((_DWORD *)v75 + 8) == 9 )
      {
        if ( !v61 )
        {
          v78 = GetLastError();
          v79 = CurrentIP();
          v80 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
          v81 = (const char *)UnBCL::String::get_CString(v80);
          v82 = ConstructPartialMsgW(
                  0x4000000u,
                  "SysprepSession::ExecuteInternal: Component %s does not have offline-capable module, will run it online",
                  v81);
          WdsSetupLogMessageW(
            v82,
            983040,
            L"D",
            0,
            672,
            L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
            L"SysprepSession::ExecuteInternal",
            v79,
            v78,
            0,
            0);
          v70 |= 4u;
          if ( (unsigned int)dword_1808293B8 > 5
            && (qword_1808293C8 & 0x400000000000LL) != 0
            && (qword_1808293D0 & 0x400000000000LL) == qword_1808293D0 )
          {
            v83 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
            v84 = UnBCL::String::get_CString(v83);
            v88 = (__int16 *)byte_180749669;
LABEL_57:
            v162 = (void **)v84;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v85,
              (_DWORD)v88,
              v86,
              v87,
              (__int64)&v162);
          }
        }
      }
      else
      {
        v89 = GetLastError();
        v90 = CurrentIP();
        v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
        v92 = UnBCL::String::get_CString(v91);
        v93 = ConstructPartialMsgW(
                0x4000000u,
                "SysprepSession::ExecuteInternal: Found non-offline-capable action to run offline; will need to run it online",
                v92);
        WdsSetupLogMessageW(
          v93,
          983040,
          L"D",
          0,
          683,
          L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
          L"SysprepSession::ExecuteInternal",
          v90,
          v89,
          0,
          0);
        v70 |= 4u;
        if ( (unsigned int)dword_1808293B8 > 5
          && (qword_1808293C8 & 0x400000000000LL) != 0
          && (qword_1808293D0 & 0x400000000000LL) == qword_1808293D0 )
        {
          v94 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
          v84 = UnBCL::String::get_CString(v94);
          v88 = &word_1807496EE;
          goto LABEL_57;
        }
      }
      v71 = v166 + 1;
      v61 = (char)pExceptionObject;
    }
  }
  v104 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v68);
  OfflineStateFromRegistry = SysprepSession::GetOfflineStateFromRegistry(this, v104);
  v106 = OfflineStateFromRegistry;
  LODWORD(pExceptionObject) = OfflineStateFromRegistry;
  if ( OfflineStateFromRegistry == 1 )
  {
    v107 = GetLastError();
    v108 = CurrentIP();
    v109 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
    v110 = (const char *)UnBCL::String::get_CString(v109);
    v111 = ConstructPartialMsgW(0x4000000u, "Component %s successfully ran offline; skipping it online", v110);
    WdsSetupLogMessageW(
      v111,
      983040,
      L"D",
      0,
      718,
      L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
      L"SysprepSession::ExecuteInternal",
      v108,
      v107,
      0,
      0);
LABEL_93:
    v145 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
    SysprepSession::RemoveOfflineStateFromRegistry(v67, v145);
    goto LABEL_94;
  }
  if ( !OfflineStateFromRegistry )
  {
    v112 = 0;
    v113 = v169[0];
    while ( 1 )
    {
      v114 = (int (__fastcall ***)(_QWORD))(*(_QWORD *)(v113 + 48)
                                          + 8LL
                                          + *(int *)(*(_QWORD *)(*(_QWORD *)(v113 + 48) + 8LL) + 12LL));
      if ( v112 >= (**v114)(v114) )
        goto LABEL_93;
      v115 = *(_QWORD *)(v113 + 48) + *(int *)(*(_QWORD *)(*(_QWORD *)(v113 + 48) + 8LL) + 16LL) + 8LL;
      v116 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v115 + 24LL))(v115, (unsigned int)v112);
      v117 = *(struct SysprepAction **)v116;
      if ( *(_DWORD *)(*(_QWORD *)v116 + 32LL) == 9 && *((_BYTE *)v117 + 36) )
      {
        v118 = GetLastError();
        v119 = CurrentIP();
        v120 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
        v121 = (const char *)UnBCL::String::get_CString(v120);
        v122 = ConstructPartialMsgW(
                 0x4000000u,
                 "SysprepSession::ExecuteInternal: Skipping offline-capable module of %s when running online",
                 v121);
        WdsSetupLogMessageW(
          v122,
          983040,
          L"D",
          0,
          740,
          L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
          L"SysprepSession::ExecuteInternal",
          v119,
          v118,
          0,
          0);
        v113 = v169[0];
      }
      else
      {
        v123 = SysprepSession::ExecuteAction(v67, v117, 0, hHandle);
        if ( v123 )
        {
          v151 = GetLastError();
          v152 = CurrentIP();
          v153 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
          v154 = (const char *)UnBCL::String::get_CString(v153);
          v155 = ConstructPartialMsgW(
                   0x2000000u,
                   "SysprepSession::ExecuteInternal: Error in executing action for %s; dwRet = 0x%x",
                   v154,
                   v123);
          WdsSetupLogMessageW(
            v155,
            983040,
            L"D",
            0,
            734,
            L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
            L"SysprepSession::ExecuteInternal",
            v152,
            v151,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v168);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
          v164 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v164);
          v77 = v123;
          goto LABEL_99;
        }
        v67 = this;
      }
      ++v112;
    }
  }
  v124 = GetLastError();
  v125 = CurrentIP();
  v126 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
  v127 = (const char *)UnBCL::String::get_CString(v126);
  v128 = ConstructPartialMsgW(0x4000000u, "Component %s ran offline, but required reboot; running pending parts", v127);
  WdsSetupLogMessageW(
    v128,
    983040,
    L"D",
    0,
    750,
    L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
    L"SysprepSession::ExecuteInternal",
    v125,
    v124,
    0,
    0);
  v129 = 0;
  while ( 2 )
  {
    v130 = v169[0];
    v131 = (int (__fastcall ***)(_QWORD))(*(_QWORD *)(v169[0] + 48LL)
                                        + 8LL
                                        + *(int *)(*(_QWORD *)(*(_QWORD *)(v169[0] + 48LL) + 8LL) + 12LL));
    if ( v129 >= (**v131)(v131) )
    {
      v67 = this;
      goto LABEL_93;
    }
    v132 = *(_QWORD *)(v130 + 48) + *(int *)(*(_QWORD *)(*(_QWORD *)(v130 + 48) + 8LL) + 16LL) + 8LL;
    v133 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v132 + 24LL))(v132, (unsigned int)v129);
    v134 = *(struct SysprepAction **)v133;
    if ( *(_BYTE *)(*(_QWORD *)v133 + 36LL) )
    {
      v140 = GetLastError();
      v141 = CurrentIP();
      v142 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
      v143 = (const char *)UnBCL::String::get_CString(v142);
      v144 = ConstructPartialMsgW(
               0x4000000u,
               "SysprepSession::ExecuteInternal: Ran offline-capable action of %s offline; skipping it online",
               v143);
      WdsSetupLogMessageW(
        v144,
        983040,
        L"D",
        0,
        776,
        L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
        L"SysprepSession::ExecuteInternal",
        v141,
        v140,
        0,
        0);
      goto LABEL_91;
    }
    if ( *((_DWORD *)v134 + 8) == 9 && (v106 & 2) != 0 )
    {
      v135 = 1;
      if ( (unsigned int)dword_1808293B8 > 5
        && (qword_1808293C8 & 0x400000000000LL) != 0
        && (qword_1808293D0 & 0x400000000000LL) == qword_1808293D0 )
      {
        v136 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
        v162 = (void **)UnBCL::String::get_CString(v136);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v137,
          (unsigned int)&unk_1807496A8,
          v138,
          v139,
          (__int64)&v162);
      }
    }
    else
    {
      v135 = 0;
    }
    v77 = SysprepSession::ExecuteAction(this, v134, v135, hHandle);
    if ( !v77 )
    {
      v106 = (char)pExceptionObject;
LABEL_91:
      ++v129;
      continue;
    }
    break;
  }
  v156 = GetLastError();
  v157 = CurrentIP();
  v158 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v66);
  v159 = (const char *)UnBCL::String::get_CString(v158);
  v160 = ConstructPartialMsgW(
           0x2000000u,
           "SysprepSession::ExecuteInternal: Error in execute actions for %s; dwRet = 0x%x",
           v159,
           v77);
  WdsSetupLogMessageW(
    v160,
    983040,
    L"D",
    0,
    769,
    L"base\\ntsetup\\opktools\\sysprep\\platform\\sysprepsession.cpp",
    L"SysprepSession::ExecuteInternal",
    v157,
    v156,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v168);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
  v164 = &UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v164);
LABEL_99:
  UnBCL::SmartPtr<UnBCL::XmlNodeList>::~SmartPtr<UnBCL::XmlNodeList>(v171);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v173);
  return v77;
}

```

## disassembly

```asm
0x180467c34  mov     rax, rsp
0x180467c37  mov     [rax+20h], r9
0x180467c3b  mov     [rax+18h], r8
0x180467c3f  mov     [rax+8], rcx
0x180467c43  push    rbp
0x180467c44  push    rsi
0x180467c45  push    rdi
0x180467c46  push    r12
0x180467c48  push    r13
0x180467c4a  push    r14
0x180467c4c  push    r15
0x180467c4e  lea     rbp, [rax-57h]
0x180467c52  sub     rsp, 100h
0x180467c59  mov     [rbp+4Fh+var_40], 0FFFFFFFFFFFFFFFEh
0x180467c61  mov     [rax+10h], rbx
0x180467c65  mov     rbx, rdx
0x180467c68  call    ?CreateXPathForSelection@SysprepSession@@AEAAPEAVString@UnBCL@@XZ; SysprepSession::CreateXPathForSelection(void)
0x180467c6d  mov     rdx, rax
0x180467c70  lea     rcx, [rbp+4Fh+var_68]
0x180467c74  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180467c7a  nop
0x180467c7b  lea     rcx, [rbp+4Fh+var_68]
0x180467c7f  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180467c85  mov     rdx, rax
0x180467c88  mov     rcx, rbx
0x180467c8b  call    cs:__imp_?SelectNodes@XmlNode@UnBCL@@QEAAPEAVXmlNodeList@2@PEAVString@2@@Z; UnBCL::XmlNode::SelectNodes(UnBCL::String *)
0x180467c91  mov     rdx, rax
0x180467c94  lea     rcx, [rbp+4Fh+var_78]
0x180467c98  call    ??0?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@QEAA@PEAVXmlNodeList@1@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::SmartPtr<UnBCL::XmlNodeList>(UnBCL::XmlNodeList *)
0x180467c9d  nop
0x180467c9e  mov     r14, [rbp+4Fh+var_70]
0x180467ca2  test    r14, r14
0x180467ca5  jz      loc_180468D34
0x180467cab  mov     rcx, r14
0x180467cae  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x180467cb4  test    eax, eax
0x180467cb6  jz      loc_180468D34
0x180467cbc  xor     al, al
0x180467cbe  mov     dword ptr [rbp+4Fh+arg_10], eax
0x180467cc1  lea     rbx, ??_7?$SmartPtr@V?$ArrayList@PEAVSysprepComponent@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable'
0x180467cc8  mov     [rbp+4Fh+var_C0], rbx
0x180467ccc  mov     [rbp+4Fh+var_B8], 0
0x180467cd4  lea     rdx, aSysprepPlatfor_0; "SYSPREP_PLATFORM_SESSION_TEST_SKIPLIST"
0x180467cdb  lea     rcx, [rbp+4Fh+var_58]
0x180467cdf  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180467ce5  nop
0x180467ce6  mov     rcx, rax
0x180467ce9  call    cs:__imp_?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::GetEnvironmentVar(UnBCL::String const *)
0x180467cef  mov     rdx, rax
0x180467cf2  lea     rcx, [rbp+4Fh+var_88]
0x180467cf6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180467cfc  nop
0x180467cfd  lea     rcx, [rbp+4Fh+var_58]
0x180467d01  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180467d07  lea     rcx, [rbp+4Fh+var_A8]
0x180467d0b  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180467d11  nop
0x180467d12  lea     rcx, [rbp+4Fh+var_88]
0x180467d16  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180467d1c  lea     r12, aSysprepsession_16; "SysprepSession::ExecuteInternal"
0x180467d23  lea     r13, aBaseNtsetupOpk_1; "base\\ntsetup\\opktools\\sysprep\\platf"...
0x180467d2a  mov     esi, 1
0x180467d2f  mov     r15d, 0F0000h
0x180467d35  test    rax, rax
0x180467d38  jz      loc_180467EBE
0x180467d3e  call    cs:__imp_GetLastError
0x180467d44  mov     edi, eax
0x180467d46  call    cs:__imp_CurrentIP
0x180467d4c  mov     rbx, rax
0x180467d4f  lea     rdx, aTestModeEnable; "Test mode enabled, following components"...
0x180467d56  mov     ecx, 4000000h; unsigned int
0x180467d5b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180467d60  mov     dword ptr [rsp+50h], 0
0x180467d68  mov     qword ptr [rsp+130h+var_E8], 0
0x180467d71  mov     dword ptr [rsp+130h+var_F0], edi
0x180467d75  mov     qword ptr [rsp+130h+var_F8], rbx
0x180467d7a  mov     [rsp+130h+var_100], r12
0x180467d7f  mov     [rsp+130h+var_108], r13
0x180467d84  mov     dword ptr [rsp+130h+var_110], 231h
0x180467d8c  xor     r9d, r9d
0x180467d8f  lea     r8, aD_0; "D"
0x180467d96  mov     edx, r15d
0x180467d99  mov     rcx, rax
0x180467d9c  call    cs:__imp_WdsSetupLogMessageW
0x180467da2  lea     rcx, [rbp+4Fh+var_88]
0x180467da6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180467dac  lea     rdx, asc_180578F60; ";"
0x180467db3  mov     rcx, rax
0x180467db6  call    cs:__imp_?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z; UnBCL::String::Split(ushort const *)
0x180467dbc  mov     rdx, rax
0x180467dbf  lea     rcx, [rsp+130h+var_D0]
0x180467dc4  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x180467dca  nop
0x180467dcb  lea     rdx, [rsp+130h+var_D0]
0x180467dd0  lea     rcx, [rbp+4Fh+var_A8]
0x180467dd4  call    cs:__imp_??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> const &)
0x180467dda  nop
0x180467ddb  lea     rcx, [rsp+130h+var_D0]
0x180467de0  call    cs:__imp_??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x180467de6  xor     esi, esi
0x180467de8  lea     rcx, [rbp+4Fh+var_A8]
0x180467dec  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180467df2  mov     rcx, [rax+8]
0x180467df6  movsxd  rdx, dword ptr [rcx+0Ch]
0x180467dfa  lea     rcx, [rax+8]
0x180467dfe  add     rcx, rdx
0x180467e01  mov     rax, [rcx]
0x180467e04  mov     rax, [rax]
0x180467e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180467e0c  cmp     esi, eax
0x180467e0e  jge     loc_180467EB2
0x180467e14  call    cs:__imp_GetLastError
0x180467e1a  mov     edi, eax
0x180467e1c  call    cs:__imp_CurrentIP
0x180467e22  mov     rbx, rax
0x180467e25  lea     rcx, [rbp+4Fh+var_A8]
0x180467e29  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180467e2f  mov     rcx, [rax+8]
0x180467e33  movsxd  rdx, dword ptr [rcx+10h]
0x180467e37  lea     rcx, [rax+8]
0x180467e3b  add     rcx, rdx
0x180467e3e  mov     rdx, [rcx]
0x180467e41  mov     rax, [rdx+18h]
0x180467e45  mov     edx, esi
0x180467e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180467e4c  mov     rcx, [rax]
0x180467e4f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180467e55  mov     r8, rax
0x180467e58  lea     rdx, aNameS_1; "  Name: %s"
0x180467e5f  mov     ecx, 4000000h; unsigned int
0x180467e64  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180467e69  mov     dword ptr [rsp+50h], 0
0x180467e71  mov     qword ptr [rsp+130h+var_E8], 0
0x180467e7a  mov     dword ptr [rsp+130h+var_F0], edi
0x180467e7e  mov     qword ptr [rsp+130h+var_F8], rbx
0x180467e83  mov     [rsp+130h+var_100], r12
0x180467e88  mov     [rsp+130h+var_108], r13
0x180467e8d  mov     dword ptr [rsp+130h+var_110], 235h
0x180467e95  xor     r9d, r9d
0x180467e98  lea     r8, aD_0; "D"
0x180467e9f  mov     edx, r15d
0x180467ea2  mov     rcx, rax
0x180467ea5  call    cs:__imp_WdsSetupLogMessageW
0x180467eab  inc     esi
0x180467ead  jmp     loc_180467DE8
0x180467eb2  mov     esi, 1
0x180467eb7  lea     rbx, ??_7?$SmartPtr@V?$ArrayList@PEAVSysprepComponent@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<SysprepComponent *>>::`vftable'
0x180467ebe  mov     ecx, 80h
0x180467ec3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180467ec9  mov     [rbp+4Fh+pExceptionObject], rax
0x180467ecd  test    rax, rax
0x180467ed0  jz      short loc_180467EDF
0x180467ed2  mov     rcx, rax
0x180467ed5  call    ??0?$ArrayList@PEAVSysprepComponent@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<SysprepComponent *>::ArrayList<SysprepComponent *>(void)
0x180467eda  mov     r15, rax
0x180467edd  jmp     short loc_180467EE2
0x180467edf  xor     r15d, r15d
0x180467ee2  mov     [rsp+130h+var_D0], rbx
0x180467ee7  mov     [rbp+4Fh+var_C8], 0
0x180467eef  lea     r13, [r15+8]
0x180467ef3  test    r15, r15
0x180467ef6  jz      short loc_180467F0D
0x180467ef8  mov     rax, [r13+0]
0x180467efc  movsxd  rcx, dword ptr [rax+4]
0x180467f00  add     rcx, 8
0x180467f04  add     rcx, r15
0x180467f07  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180467f0d  lea     rcx, [rsp+130h+var_D0]
0x180467f12  call    ?DeAssign@?$SmartPtr@V?$Hashtable@KPEAUIVdsVDisk@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::Hashtable<ulong,IVdsVDisk *>>::DeAssign(void)
0x180467f17  mov     [rbp+4Fh+var_C8], r15
0x180467f1b  test    r15, r15
0x180467f1e  jz      short loc_180467F35
0x180467f20  mov     rax, [r13+0]
0x180467f24  movsxd  rcx, dword ptr [rax+4]
0x180467f28  add     rcx, 8
0x180467f2c  add     rcx, r15
0x180467f2f  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x180467f35  lea     rcx, [rbp+4Fh+var_C0]
0x180467f39  call    ?DeAssign@?$SmartPtr@V?$Hashtable@KPEAUIVdsVDisk@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::Hashtable<ulong,IVdsVDisk *>>::DeAssign(void)
0x180467f3e  mov     [rbp+4Fh+var_B8], r15
0x180467f42  mov     [rsp+130h+var_D0], rbx
0x180467f47  lea     rcx, [rsp+130h+var_D0]
0x180467f4c  call    ?DeAssign@?$SmartPtr@V?$Hashtable@KPEAUIVdsVDisk@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::Hashtable<ulong,IVdsVDisk *>>::DeAssign(void)
0x180467f51  nop
0x180467f52  mov     rax, [r15]
0x180467f55  mov     edx, esi
0x180467f57  mov     rcx, r15
0x180467f5a  mov     rax, [rax+28h]
0x180467f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180467f63  xor     r12d, r12d
0x180467f66  mov     rcx, r14
0x180467f69  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x180467f6f  test    eax, eax
0x180467f71  jle     loc_1804680AD
0x180467f77  mov     edx, r12d
0x180467f7a  mov     rcx, r14
0x180467f7d  call    cs:__imp_?get_Item@XmlNodeList@UnBCL@@QEAAPEAVXmlNode@2@H@Z; UnBCL::XmlNodeList::get_Item(int)
0x180467f83  mov     rdx, rax
0x180467f86  lea     rcx, [rbp+4Fh+var_98]
0x180467f8a  call    ??0?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@QEAA@PEAVXmlNode@1@@Z; UnBCL::SmartPtr<UnBCL::XmlNode>::SmartPtr<UnBCL::XmlNode>(UnBCL::XmlNode *)
0x180467f8f  nop
0x180467f90  mov     ecx, 38h ; '8'
0x180467f95  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180467f9b  mov     [rbp+4Fh+pExceptionObject], rax
0x180467f9f  test    rax, rax
0x180467fa2  jz      short loc_180467FB1
0x180467fa4  mov     rdx, [rbp+4Fh+var_90]; struct UnBCL::XmlNode *
0x180467fa8  mov     rcx, rax; this
0x180467fab  call    ??0SysprepComponent@@QEAA@PEAVXmlNode@UnBCL@@@Z; SysprepComponent::SysprepComponent(UnBCL::XmlNode *)
0x180467fb0  nop
0x180467fb1  mov     rdx, rax
0x180467fb4  lea     rcx, [rsp+130h+var_D0]
0x180467fb9  call    ??0?$SmartPtr@VSysprepComponent@@@UnBCL@@QEAA@PEAVSysprepComponent@@@Z; UnBCL::SmartPtr<SysprepComponent>::SmartPtr<SysprepComponent>(SysprepComponent *)
0x180467fbe  nop
0x180467fbf  lea     rcx, [rbp+4Fh+var_A8]
0x180467fc3  call    cs:__imp_?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(void)
0x180467fc9  mov     rdi, [rbp+4Fh+var_C8]
0x180467fcd  test    rax, rax
0x180467fd0  jz      short loc_18046804A
0x180467fd2  xor     esi, esi
0x180467fd4  lea     rcx, [rbp+4Fh+var_A8]
0x180467fd8  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180467fde  mov     rcx, [rax+8]
0x180467fe2  movsxd  rdx, dword ptr [rcx+0Ch]
0x180467fe6  lea     rcx, [rax+8]
0x180467fea  add     rcx, rdx
0x180467fed  mov     rax, [rcx]
0x180467ff0  mov     rax, [rax]
0x180467ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180467ff8  cmp     esi, eax
0x180467ffa  jge     short loc_18046804A
0x180467ffc  lea     rcx, [rbp+4Fh+var_A8]
0x180468000  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180468006  mov     rcx, [rax+8]
0x18046800a  movsxd  rdx, dword ptr [rcx+10h]
0x18046800e  lea     rcx, [rax+8]
0x180468012  add     rcx, rdx
0x180468015  mov     rax, [rcx]
0x180468018  mov     edx, esi
0x18046801a  mov     rax, [rax+18h]
0x18046801e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180468023  mov     rbx, [rax]
0x180468026  lea     rcx, [rdi+10h]
0x18046802a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180468030  mov     r8d, 1
0x180468036  mov     rdx, rbx
0x180468039  mov     rcx, rax
0x18046803c  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x180468042  test    eax, eax
0x180468044  jz      short loc_180468084
0x180468046  inc     esi
0x180468048  jmp     short loc_180467FD4
0x18046804a  mov     rax, [r13+0]
0x18046804e  movsxd  rbx, dword ptr [rax+10h]
0x180468052  mov     rax, [rbx+r15+8]
0x180468057  mov     rsi, [rax+28h]
0x18046805b  test    rdi, rdi
0x18046805e  jz      short loc_180468071
0x180468060  mov     rcx, rdi
0x180468063  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x180468069  mov     [rbp+4Fh+var_C8], 0
0x180468071  mov     rdx, rdi
0x180468074  lea     rcx, [r15+8]
0x180468078  add     rcx, rbx
0x18046807b  mov     rax, rsi
0x18046807e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180468083  nop
0x180468084  lea     rcx, [rsp+130h+var_D0]
0x180468089  call    ??1?$SmartPtr@VSysprepComponent@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<SysprepComponent>::~SmartPtr<SysprepComponent>(void)
0x18046808e  nop
0x18046808f  lea     rcx, [rbp+4Fh+var_98]
0x180468093  call    ??1?$SmartPtr@VXmlNode@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::XmlNode>::~SmartPtr<UnBCL::XmlNode>(void)
0x180468098  inc     r12d
0x18046809b  mov     rcx, r14
0x18046809e  call    cs:__imp_?get_Count@XmlNodeList@UnBCL@@QEAAHXZ; UnBCL::XmlNodeList::get_Count(void)
0x1804680a4  cmp     r12d, eax
0x1804680a7  jl      loc_180467F77
0x1804680ad  mov     rax, [r15]
0x1804680b0  mov     rcx, r15
0x1804680b3  mov     rax, [rax+58h]
0x1804680b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804680bc  call    cs:__imp_GetLastError
0x1804680c2  mov     edi, eax
0x1804680c4  call    cs:__imp_CurrentIP
0x1804680ca  mov     rbx, rax
0x1804680cd  lea     rdx, aAfterSortingCo; "After sorting, components will be excut"...
0x1804680d4  mov     ecx, 4000000h; unsigned int
0x1804680d9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1804680de  mov     dword ptr [rsp+50h], 0
0x1804680e6  mov     qword ptr [rsp+130h+var_E8], 0
0x1804680ef  mov     dword ptr [rsp+130h+var_F0], edi
0x1804680f3  mov     qword ptr [rsp+130h+var_F8], rbx
0x1804680f8  lea     rcx, aSysprepsession_16; "SysprepSession::ExecuteInternal"
0x1804680ff  mov     [rsp+130h+var_100], rcx
0x180468104  lea     rcx, aBaseNtsetupOpk_1; "base\\ntsetup\\opktools\\sysprep\\platf"...
0x18046810b  mov     [rsp+130h+var_108], rcx
0x180468110  mov     dword ptr [rsp+130h+var_110], 255h
0x180468118  xor     r9d, r9d
0x18046811b  lea     r8, aD_0; "D"
0x180468122  mov     edx, 0F0000h
  ... truncated ...
```
