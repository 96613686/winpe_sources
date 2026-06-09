# CSetupPlatformPrivate::Initialize(ushort const *,ushort const *,int,int,int)

- ea: `0x180259cd4`
- end: `0x18025b43f`
- name: `?Initialize@CSetupPlatformPrivate@@QEAAJPEBG0HHH@Z`
- size: `5995`
- prototype: `__int64 __fastcall(CSetupPlatformPrivate *this, const unsigned __int16 *, const unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009bcc0`
- `0x18009bd60`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x18002a5d0`
- `0x180044754`
- `0x180044820`
- `0x180057dec`
- `0x18005dd24`
- `0x1800adfec`
- `0x1800af68c`
- `0x1802595e0`
- `0x180259cd4`
- `0x18025c4bc`
- `0x18029f7f8`
- `0x18029f9b0`
- `0x18029fb60`
- `0x1802d7cd8`
- `0x1802d8598`
- `0x1802e2078`
- `0x1803738b0`
- `0x18037f254`
- `0x180380204`
- `0x1803804e0`
- `0x1804bbf46`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18025a57d`
- `msvcrt!_wtoi` at `0x18025ac36`
- `msvcrt!_wtoi` at `0x18025a57d`
- `msvcrt!_wtoi` at `0x18025ac36`
- `KERNEL32!GetLastError` at `0x18025a1c8`
- `KERNEL32!GetLastError` at `0x18025a5e2`
- `KERNEL32!GetLastError` at `0x18025a656`
- `KERNEL32!GetLastError` at `0x18025a7c6`
- `KERNEL32!GetLastError` at `0x18025b216`
- `KERNEL32!GetLastError` at `0x18025b307`
- `KERNEL32!GetLastError` at `0x18025a1c8`
- `KERNEL32!GetLastError` at `0x18025a5e2`
- `KERNEL32!GetLastError` at `0x18025a656`
- `KERNEL32!GetLastError` at `0x18025a7c6`
- `KERNEL32!GetLastError` at `0x18025b216`
- `KERNEL32!GetLastError` at `0x18025b307`
- `KERNEL32!SetCurrentDirectoryW` at `0x180259d68`
- `KERNEL32!SetCurrentDirectoryW` at `0x180259d68`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025add7`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025ae30`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025ae6e`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025aecb`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025add7`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025ae30`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025ae6e`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18025aecb`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18025b16f`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18025b16f`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18025ad4c`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18025ad4c`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025ae99`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025af93`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025ae99`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025af93`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18025abaa`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18025abaa`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025a507`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025aa6b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025aacc`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025acb1`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025acdb`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025ad05`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025afef`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b01e`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b061`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b08b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b0b5`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025a507`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025aa6b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025aacc`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025acb1`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025acdb`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025ad05`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025afef`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b01e`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b061`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b08b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18025b0b5`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180259e0d`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180259e0d`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025aef7`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025af54`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025aef7`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18025af54`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18025b2cd`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18025b3a5`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18025b405`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18025b2cd`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18025b3a5`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x18025b405`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x18025ad57`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x18025ad57`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259e66`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259ec7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259f28`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259f90`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a048`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a26e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a2d9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a344`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a3b1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a3f3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a454`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259e66`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259ec7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259f28`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180259f90`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a048`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a26e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a2d9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a344`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a3b1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a3f3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18025a454`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x18025a8cf`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x18025a8ed`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x18025a8cf`
- `unbcl!??C?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEBAPEAV?$Array@E@1@XZ` at `0x18025a8ed`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x18025a893`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@E@1@@Z` at `0x18025a893`
- `unbcl!??4?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18025a8a3`
- `unbcl!??4?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18025a8a3`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18025a8af`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18025a97c`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18025a8af`
- `unbcl!??1?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18025a97c`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18025a855`
- `unbcl!??0?$SmartPtr@V?$Array@E@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18025a855`
- `unbcl!?GetASCII@Encoding@UnBCL@@SAPEAV12@XZ` at `0x18025a85c`
- `unbcl!?GetASCII@Encoding@UnBCL@@SAPEAV12@XZ` at `0x18025a85c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259e04`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259e5a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259ebb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259f1c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259f84`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a03c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a1a7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a3a5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a3e7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a448`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a4cf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a55c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a790`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025aa39`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025ab92`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025ac15`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025ac7c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025afc4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025b032`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025b0c7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025b112`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259e04`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259e5a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259ebb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259f1c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180259f84`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a03c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a1a7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a3a5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a3e7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a448`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a4cf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a55c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025a790`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025aa39`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025ab92`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025ac15`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025ac7c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025afc4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025b032`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025b0c7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18025b112`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259e9e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259eff`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259f60`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259fcb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a089`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a2a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a311`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a37f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a3c9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a42b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a48f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259e9e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259eff`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259f60`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180259fcb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a089`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a2a6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a311`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a37f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a3c9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a42b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18025a48f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259dc7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259e4e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259eaf`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259f10`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259f71`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a004`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a025`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a107`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a24c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a2b7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a322`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a399`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a3da`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a43c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259dc7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259e4e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259eaf`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259f10`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180259f71`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a004`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a025`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a107`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a24c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a2b7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a322`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18025a399`

## string_xrefs

- `0x180259f66`: `Rollback`
- `0x18025a317`: `Rollback`
- `0x18025a0a4`: `InstallationID`
- `0x18025aa14`: `InstallationType`
- `0x18025a161`: `ScratchDirectory`
- `0x18025a4aa`: `ExternalRollback`
- `0x18025afe8`: `Service`
- `0x18025a431`: `rollbackinfo.ini`
- `0x18025a5f6`: `CSetupPlatformPrivate::Initialize: IgnoreNonCriticalErrors flag was set... tolerating error from deserialize telemetry instance. Error: 0x%08X`
- `0x18025a537`: `RollbackMode`
- `0x18025a1d9`: `Scratch directory could not be found. Abandoning...`
- `0x18025b24a`: `%hs: Unknown installation type: %s. Error: 0x%08X`
- `0x18025b396`: `Failed to read installation type`
- `0x18025b3f6`: `Failed to initialize rollback`
- `0x18025b2be`: `Unknown installation type`
- `0x18025b322`: `%hs: Failed to read the installation type. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall CSetupPlatformPrivate::Initialize(
        CSetupPlatformPrivate *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5)
{
  char v8; // r15
  struct UnBCL::String *v9; // rax
  UnBCL::String *v10; // rax
  const WCHAR *CString; // rax
  UnBCL::String *v12; // rax
  UnBCL::String *v13; // rax
  UnBCL::String *v14; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *ParentPath; // rax
  const struct UnBCL::String *v17; // rbx
  const struct UnBCL::String *v18; // rax
  struct UnBCL::String *v19; // rax
  const struct UnBCL::String *v20; // rbx
  const struct UnBCL::String *v21; // rax
  struct UnBCL::String *v22; // rax
  const struct UnBCL::String *v23; // rbx
  const struct UnBCL::String *v24; // rax
  struct UnBCL::String *v25; // rax
  const struct UnBCL::String *v26; // rbx
  char *v27; // rdi
  const struct UnBCL::String *v28; // rax
  struct UnBCL::String *v29; // rax
  UnBCL::String *v30; // rax
  struct UnBCL::String *v31; // rbx
  const struct UnBCL::String *v32; // rbx
  const struct UnBCL::String *v33; // rax
  UnBCL::String *v34; // rax
  const WCHAR *v35; // rax
  struct UnBCL::String *v36; // rax
  UnBCL::String *v37; // rax
  UnBCL::String *v38; // rbx
  UnBCL::String *v39; // rax
  const WCHAR *v40; // rax
  struct UnBCL::String *v41; // rax
  int ScratchDirectory; // r15d
  DWORD LastError; // edi
  __int64 v44; // rbx
  struct tagLOG_PARTIAL_MSG *v45; // rax
  const struct UnBCL::String *v46; // rbx
  const struct UnBCL::String *v47; // rax
  struct UnBCL::String *v48; // rax
  const struct UnBCL::String *v49; // rbx
  const struct UnBCL::String *v50; // rax
  struct UnBCL::String *v51; // rax
  const struct UnBCL::String *v52; // rbx
  const struct UnBCL::String *v53; // rax
  struct UnBCL::String *v54; // rax
  char *v55; // r15
  const struct UnBCL::String *v56; // rbx
  const struct UnBCL::String *v57; // rax
  struct UnBCL::String *v58; // rax
  const struct UnBCL::String *v59; // rbx
  const struct UnBCL::String *v60; // rax
  struct UnBCL::String *v61; // rax
  const struct UnBCL::String *v62; // rbx
  const struct UnBCL::String *v63; // rax
  struct UnBCL::String *v64; // rax
  UnBCL::String *v65; // rax
  const WCHAR *v66; // rax
  struct UnBCL::String *v67; // rax
  UnBCL::String *v68; // rax
  const unsigned __int16 *v69; // rax
  UnBCL::String *v70; // rax
  const WCHAR *v71; // rax
  struct UnBCL::String *v72; // rax
  UnBCL::String *v73; // rax
  const wchar_t *v74; // rax
  struct CTelemetry **v75; // rbx
  UnBCL::String *v76; // rax
  const unsigned __int16 *v77; // rax
  int v78; // eax
  DWORD v79; // edi
  __int64 v80; // rbx
  struct tagLOG_PARTIAL_MSG *v81; // rax
  DWORD v82; // edi
  __int64 v83; // rbx
  struct tagLOG_PARTIAL_MSG *v84; // rax
  CTelemetry *v85; // rax
  CTelemetry *v86; // rdx
  char *v87; // rbx
  __int64 v88; // rdx
  __int64 v89; // rax
  struct UnBCL::String **v90; // rbx
  struct UnBCL::String *v91; // rax
  DWORD v92; // edi
  __int64 v93; // rbx
  UnBCL::String *v94; // rax
  const char *v95; // rax
  struct tagLOG_PARTIAL_MSG *v96; // rax
  __int64 ASCII; // rdi
  __int64 (__fastcall *v98)(__int64, __int64); // rbx
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rdi
  int (__fastcall ***v102)(_QWORD); // rax
  unsigned __int64 v103; // rbx
  __int64 v104; // rax
  char *v105; // rax
  unsigned __int64 v106; // rdx
  char *v107; // rcx
  char v108; // r8
  char *v109; // rax
  struct TraceLoggingCorrelationVector *v110; // rax
  CSetupPlatformRollback *v111; // rax
  CSetupPlatformRollback *v112; // rdx
  UnBCL::String *v113; // rax
  const WCHAR *v114; // rax
  struct UnBCL::String *v115; // rax
  UnBCL::String *v116; // rax
  const unsigned __int16 *v117; // rax
  CInstallCheckpointSequence *v118; // rax
  unsigned int v119; // r13d
  CInstallCheckpointSequence *v120; // r12
  UnBCL::String *v121; // rax
  const unsigned __int16 *v122; // rax
  CServicingCheckpointSequence *v123; // rax
  unsigned int (__fastcall ***v124)(_QWORD, CInstallCheckpointSequence *, const unsigned __int16 *, _QWORD); // rdi
  unsigned int (__fastcall *v125)(_QWORD, CInstallCheckpointSequence *, const unsigned __int16 *, _QWORD); // rbx
  UnBCL::String *v126; // rax
  const unsigned __int16 *v127; // rax
  UnBCL::String *v128; // rax
  const WCHAR *v129; // rax
  struct UnBCL::String *v130; // rax
  UnBCL::String *v131; // rax
  UnBCL::String *v132; // rax
  UnBCL::String *v133; // rax
  const WCHAR *v134; // rax
  struct UnBCL::String *v135; // rax
  UnBCL::String *v136; // rax
  const wchar_t *v137; // rax
  UnBCL::String *v138; // rax
  const WCHAR *v139; // rax
  struct UnBCL::String *v140; // rax
  UnBCL::String *v141; // rax
  const unsigned __int16 *v142; // rax
  UnBCL::String *v143; // rax
  const unsigned __int16 *v144; // rax
  UnBCL::String *v145; // rax
  const unsigned __int16 *v146; // rax
  BOOL v147; // eax
  UnBCL::String *v148; // rax
  const WCHAR *v149; // rax
  __int64 v150; // rax
  void *v151; // rax
  unsigned int i; // edi
  __int64 v153; // rax
  int (__fastcall ***v154)(_QWORD); // rcx
  unsigned int v155; // ebx
  unsigned int v156; // r13d
  __int64 v157; // rax
  __int64 v158; // rcx
  UnBCL::String **v159; // rax
  int v160; // r14d
  __int64 v161; // rax
  __int64 v162; // rcx
  UnBCL::String **v163; // rax
  struct UnBCL::String *v164; // rax
  __int64 v165; // rax
  __int64 v166; // rcx
  UnBCL::String **v167; // rax
  struct UnBCL::String *v168; // rax
  UnBCL::String *v169; // rax
  int v170; // r14d
  UnBCL::String *v171; // rax
  struct UnBCL::String *v172; // rax
  UnBCL::String *v173; // rax
  struct UnBCL::String *v174; // rax
  UnBCL::String *v175; // rax
  const unsigned __int16 *v176; // rax
  UnBCL::String *v177; // rax
  const unsigned __int16 *v178; // rax
  UnBCL::String *v179; // rax
  const unsigned __int16 *v180; // rax
  UnBCL::String *v181; // rax
  const unsigned __int16 *v182; // rax
  UnBCL::String *v183; // rax
  const unsigned __int16 *v184; // rax
  __int64 v185; // r12
  void *v186; // rax
  void *v187; // r14
  __int64 v188; // rax
  void (__fastcall ***v189)(_QWORD, __int64); // rcx
  DWORD v191; // edi
  __int64 v192; // rbx
  UnBCL::String *v193; // rax
  const char *v194; // rax
  struct tagLOG_PARTIAL_MSG *v195; // rax
  UnBCL::Win32Exception *v196; // rax
  UnBCL::Win32Exception *v197; // rbx
  DWORD v198; // edi
  __int64 v199; // rbx
  struct tagLOG_PARTIAL_MSG *v200; // rax
  UnBCL::Win32Exception *v201; // rax
  UnBCL::Win32Exception *v202; // rbx
  UnBCL::Win32Exception *v203; // rax
  UnBCL::Win32Exception *v204; // rbx
  _QWORD v205[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  int v207; // [rsp+78h] [rbp-88h]
  void **v208; // [rsp+80h] [rbp-80h] BYREF
  void (__fastcall ***v209)(_QWORD, __int64); // [rsp+88h] [rbp-78h]
  _BYTE v210[16]; // [rsp+90h] [rbp-70h] BYREF
  int v211[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v212[24]; // [rsp+A8h] [rbp-58h] BYREF
  void **v213; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v214; // [rsp+C8h] [rbp-38h]
  _BYTE v215[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v216[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v217[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v218[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v219[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v220[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v221[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v222[16]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v223[16]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v224[16]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v225; // [rsp+178h] [rbp+78h]
  unsigned __int16 v226; // [rsp+180h] [rbp+80h] BYREF
  int v227; // [rsp+182h] [rbp+82h]
  char Source[272]; // [rsp+190h] [rbp+90h] BYREF

  v225 = -2;
  v211[0] = a4;
  v8 = 0;
  v207 = 0;
  v9 = SPGetPlatformDir();
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v9);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 208, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 208);
  CString = UnBCL::String::get_CString(v10);
  SetCurrentDirectoryW(CString);
  v226 = 63;
  v227 = 58;
  v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 208);
  v226 = *UnBCL::String::get_CString(v12);
  v13 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v14 = v13;
  pExceptionObject = (__int64)v13;
  if ( v13 )
  {
    UnBCL::String::String(v13, &v226);
    *(_QWORD *)v14 = &UnBCL::String::`local vftable';
  }
  else
  {
    v14 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v14);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 224, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
  ParentPath = UnBCL::Path::GetParentPath(P);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, ParentPath);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 240, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  v17 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Sources");
  v18 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 240);
  v19 = UnBCL::Path::Combine(v18, v17);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v19);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 352, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  UnBCL::String::~String((UnBCL::String *)v212);
  v20 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Work");
  v21 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 240);
  v22 = UnBCL::Path::Combine(v21, v20);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v22);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 320, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  UnBCL::String::~String((UnBCL::String *)v212);
  v23 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Store");
  v24 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 240);
  v25 = UnBCL::Path::Combine(v24, v23);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v25);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 336, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  UnBCL::String::~String((UnBCL::String *)v212);
  v26 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Rollback");
  v27 = (char *)this + 352;
  v28 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 352);
  v29 = UnBCL::Path::Combine(v28, v26);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v29);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 368, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  UnBCL::String::~String((UnBCL::String *)v212);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 384, (char *)this + 368);
  if ( a2 )
  {
    v30 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v31 = v30;
    pExceptionObject = (__int64)v30;
    if ( v30 )
    {
      UnBCL::String::String(v30, a2);
      *(_QWORD *)v31 = &UnBCL::String::`local vftable';
    }
    else
    {
      v31 = 0;
    }
  }
  else
  {
    v32 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"SetupPlatform.ini");
    v8 = 1;
    v207 = 1;
    v33 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 352);
    v31 = UnBCL::Path::Combine(v33, v32);
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v31);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 24, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  if ( (v8 & 1) != 0 )
    UnBCL::String::~String((UnBCL::String *)v212);
  v34 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v35 = UnBCL::String::get_CString(v34);
  v36 = SPReadConfigValue(L"Parameters", L"InstallationID", v35);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v36);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 256, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  if ( a3 )
  {
    v37 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v38 = v37;
    pExceptionObject = (__int64)v37;
    if ( v37 )
    {
      UnBCL::String::String(v37, a3);
      *(_QWORD *)v38 = &UnBCL::String::`local vftable';
    }
    else
    {
      v38 = 0;
    }
  }
  else
  {
    v38 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v38);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 304, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v40 = UnBCL::String::get_CString(v39);
  v41 = SPReadConfigValue(L"Parameters", L"ScratchDirectory", v40);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v41);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 272, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 272) )
  {
    ScratchDirectory = CSetupPlatformPrivate::FindScratchDirectory(this, v211[0]);
    if ( ScratchDirectory < 0 )
    {
      LastError = GetLastError();
      v44 = CurrentIP();
      v45 = ConstructPartialMsgW(0x2000000u, "Scratch directory could not be found. Abandoning...");
      WdsSetupLogMessageW(
        v45,
        819200,
        L"D",
        0,
        1288,
        L"base\\ntsetup\\setupplatform\\lib\\private\\execution.cpp",
        L"CSetupPlatformPrivate::Initialize",
        v44,
        LastError,
        0,
        0);
      return (unsigned int)ScratchDirectory;
    }
    v46 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Work");
    v47 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 37) + 16LL))(*((_QWORD *)this + 37));
    v48 = UnBCL::Path::Combine(v47, v46);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v48);
    UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 320, v205);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
    UnBCL::String::~String((UnBCL::String *)v212);
    v49 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Store");
    v50 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 37) + 16LL))(
                                          *((_QWORD *)this + 37),
                                          **((_QWORD **)this + 37));
    v51 = UnBCL::Path::Combine(v50, v49);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v51);
    UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 336, v205);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
    UnBCL::String::~String((UnBCL::String *)v212);
    v52 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Rollback");
    v53 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 37) + 16LL))(
                                          *((_QWORD *)this + 37),
                                          **((_QWORD **)this + 37));
    v54 = UnBCL::Path::Combine(v53, v52);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v54);
    v55 = (char *)this + 368;
    UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 368, v205);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
    UnBCL::String::~String((UnBCL::String *)v212);
  }
  else
  {
    v55 = (char *)this + 368;
  }
  v56 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v212, L"Diagnostics");
  v57 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
  v58 = UnBCL::Path::Combine(v57, v56);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v224, v58);
  UnBCL::String::~String((UnBCL::String *)v212);
  v59 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v218, L"diagnostics.dat");
  v60 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v224);
  v61 = UnBCL::Path::Combine(v60, v59);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v61);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 160, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  UnBCL::String::~String((UnBCL::String *)v218);
  v62 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v218, L"rollbackinfo.ini");
  v63 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v55);
  v64 = UnBCL::Path::Combine(v63, v62);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, v64);
  UnBCL::SmartPtr<UnBCL::String>::operator=((char *)this + 400, v205);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
  UnBCL::String::~String((UnBCL::String *)v218);
  v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v66 = UnBCL::String::get_CString(v65);
  v67 = SPReadConfigValue(L"BootEntries", L"ExternalRollback", v66);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v221, v67);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v221) )
  {
    *((_DWORD *)this + 105) = 1;
    v68 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v221);
    v69 = UnBCL::String::get_CString(v68);
    *((_DWORD *)this + 104) = UnBCL::String::Compare(v69, L"Disabled", 1) != 0;
  }
  v207 = 0;
  v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 400);
  v71 = UnBCL::String::get_CString(v70);
  v72 = SPReadConfigValue(L"Flow", L"RollbackMode", v71);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v220, v72);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v220) )
  {
    v73 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v220);
    v74 = UnBCL::String::get_CString(v73);
    v207 = _wtoi(v74);
  }
  v214 = 0;
  v213 = &RAII::CAutoDelete<CTelemetry *>::`vftable';
  v75 = (struct CTelemetry **)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v213);
  v76 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 352);
  v77 = UnBCL::String::get_CString(v76);
  v78 = SPDeserializeTelemetry(v77, v75);
  ScratchDirectory = v78;
  if ( v78 >= 0 )
  {
    v88 = v214;
    v214 = 0;
    v87 = (char *)this + 192;
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 24) + 32LL))((char *)this + 192, v88);
  }
  else
  {
    if ( v78 != -2147023728 )
    {
      v79 = GetLastError();
      v80 = CurrentIP();
      v81 = ConstructPartialMsgW(
              0x3000000u,
              "CSetupPlatformPrivate::Initialize: IgnoreNonCriticalErrors flag was set... tolerating error from deseriali"
              "ze telemetry instance. Error: 0x%08X",
              ScratchDirectory);
      WdsSetupLogMessageW(
        v81,
        819200,
        L"D",
        0,
        1338,
        L"base\\ntsetup\\setupplatform\\lib\\private\\execution.cpp",
        L"CSetupPlatformPrivate::Initialize",
        v80,
        v79,
        0,
        0);
    }
    ScratchDirectory = 0;
    v82 = GetLastError();
    v83 = CurrentIP();
    v84 = ConstructPartialMsgW(0x4000000u, "Creating a new telemetry session.");
    WdsSetupLogMessageW(
      v84,
      819200,
      L"D",
      0,
      1348,
      L"base\\ntsetup\\setupplatform\\lib\\private\\execution.cpp",
      L"CSetupPlatformPrivate::Initialize",
      v83,
      v82,
      0,
      0);
    v85 = (CTelemetry *)UnBCL::Object::operator new(0x98u);
    pExceptionObject = (__int64)v85;
    if ( v85 )
      v86 = CTelemetry::CTelemetry(v85);
    else
      v86 = 0;
    v87 = (char *)this + 192;
    (*(void (__fastcall **)(char *, CTelemetry *))(*((_QWORD *)this + 24) + 32LL))((char *)this + 192, v86);
    v27 = (char *)this + 352;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v87 + 24LL))(v87) )
  {
    v89 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v87 + 24LL))(v87);
    pExceptionObject = _RTDynamicCast_0(
                         v89,
                         0,
                         &ITelemetry `RTTI Type Descriptor',
                         &CTelemetry `RTTI Type Descriptor',
                         0);
    v209 = 0;
    v208 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
    v90 = (struct UnBCL::String **)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v208);
    v91 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v27);
    SPDiagTrackGetCorrelationVectorOriginal(v91, v90);
    *(_QWORD *)v211 = 0;
    if ( ((unsigned __int8 (__fastcall *)(void ***, int *))v208[8])(&v208, v211) )
    {
      v92 = GetLastError();
      v93 = CurrentIP();
      v94 = (UnBCL::String *)((__int64 (__fastcall *)(void ***))v208[3])(&v208);
      v95 = (const char *)UnBCL::String::get_CString(v94);
      v96 = ConstructPartialMsgW(0x4000000u, "Setting Correlation vector: %s", v95);
      WdsSetupLogMessageW(
        v96,
        819200,
        L"D",
        0,
        1365,
        L"base\\ntsetup\\setupplatform\\lib\\private\\execution.cpp",
        L"CSetupPlatformPrivate::Initialize",
        v93,
        v92,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::SmartPtr<UnBCL::Array<unsigned char>>(v210);
      ASCII = UnBCL::Encoding::GetASCII();
      v98 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)ASCII + 48LL);
      v99 = ((__int64 (__fastcall *)(void ***))v208[4])(&v208);
      v100 = v98(ASCII, v99);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::SmartPtr<UnBCL::Array<unsigned char>>(v205, v100);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::operator=(v210, v205);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::~SmartPtr<UnBCL::Array<unsigned char>>(v205);
      v101 = 260;
      memset_0(Source, 0, 0x104u);
      v102 = (int (__fastcall ***)(_QWORD))UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::operator->(v210);
      v103 = (**v102)(v102);
      v104 = UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::operator->(v210);
      v105 = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v104 + 56LL))(v104, 0);
      v106 = v103;
      if ( v103 <= 0x7FFFFFFE )
      {
        v107 = Source;
        do
        {
          if ( !v106 )
            break;
          v108 = *v105;
          if ( !*v105 )
            break;
          ++v105;
          *v107++ = v108;
          --v106;
          --v101;
        }
        while ( v101 );
        v109 = v107 - 1;
        if ( v101 )
          v109 = v107;
        *v109 = 0;
      }
      else
      {
        Source[0] = 0;
      }
      v110 = TraceLoggingCorrelationVector::Set(Source, v106);
      (*(void (__fastcall **)(__int64, struct TraceLoggingCorrelationVector *))(*(_QWORD *)(pExceptionObject + 80) + 48LL))(
        pExceptionObject + 80,
        v110);
      UnBCL::SmartPtr<UnBCL::Array<unsigned char>>::~SmartPtr<UnBCL::Array<unsigned char>>(v210);
    }
    v208 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
    if ( v209 )
      (**v209)(v209, 1);
  }
  if ( a5 )
    CSetupPlatformPrivate::StartTelemetry(this);
  if ( *((_DWORD *)this + 104) )
  {
    v111 = (CSetupPlatformRollback *)UnBCL::Object::operator new(0x58u);
    pExceptionObject = (__int64)v111;
    if ( v111 )
      v112 = CSetupPlatformRollback::CSetupPlatformRollback(v111);
    else
      v112 = 0;
    (*(void (__fastcall **)(char *, CSetupPlatformRollback *))(*((_QWORD *)this + 22) + 32LL))((char *)this + 176, v112);
    v113 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
    v114 = UnBCL::String::get_CString(v113);
    v115 = SPReadConfigValue(L"Parameters", L"InstallationType", v114);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v210, v115);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v210) )
    {
      v198 = GetLastError();
      v199 = CurrentIP();
      v200 = ConstructPartialMsgW(
               0x2000000u,
               "%hs: Failed to read the installation type. Error: 0x%08X",
               "CSetupPlatformPrivate::Initialize",
               ScratchDirectory);
      WdsSetupLogMessageW(
        v200,
        819200,
        L"D",
        0,
        1398,
        L"base\\ntsetup\\setupplatform\\lib\\private\\execution.cpp",
        L"CSetupPlatformPrivate::Initialize",
        v199,
        v198,
        0,
        0);
      v201 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v202 = v201;
      *(_QWORD *)v211 = v201;
      if ( v201 )
      {
        UnBCL::Win32Exception::Win32Exception(v201, 0x54Fu, L"Failed to read installation type");
        *(_QWORD *)v202 = &UnBCL::Win32Exception::`local vftable';
      }
      else
      {
        v202 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v202,
                           "long __cdecl CSetupPlatformPrivate::Initialize(const unsigned short *,const unsigned short *,int,int,int)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
    v116 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v210);
    v117 = UnBCL::String::get_CString(v116);
    if ( UnBCL::String::Compare(v117, L"Deployment", 1) )
    {
      v121 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v210);
      v122 = UnBCL::String::get_CString(v121);
      if ( UnBCL::String::Compare(v122, L"Servicing", 1) )
      {
        v191 = GetLastError();
        v192 = CurrentIP();
        v193 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v210);
        v194 = (const char *)UnBCL::String::get_CString(v193);
        v195 = ConstructPartialMsgW(
                 0x2000000u,
                 "%hs: Unknown installation type: %s. Error: 0x%08X",
                 "CSetupPlatformPrivate::Initialize",
                 v194,
                 ScratchDirectory);
        WdsSetupLogMessageW(
          v195,
          819200,
          L"D",
          0,
          1414,
          L"base\\ntsetup\\setupplatform\\lib\\private\\execution.cpp",
          L"CSetupPlatformPrivate::Initialize",
          v192,
          v191,
          0,
          0);
        v196 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v197 = v196;
        *(_QWORD *)v211 = v196;
        if ( v196 )
        {
          UnBCL::Win32Exception::Win32Exception(v196, 0x54Fu, L"Unknown installation type");
          *(_QWORD *)v197 = &UnBCL::Win32Exception::`local vftable';
        }
        else
        {
          v197 = 0;
        }
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v197,
                             "long __cdecl CSetupPlatformPrivate::Initialize(const unsigned short *,const unsigned short *,int,int,int)");
        throw (UnBCL::Win32Exception **)&pExceptionObject;
      }
      v123 = (CServicingCheckpointSequence *)UnBCL::Object::operator new(0x90u);
      pExceptionObject = (__int64)v123;
      if ( v123 )
        v120 = CServicingCheckpointSequence::CServicingCheckpointSequence(v123);
      else
        v120 = 0;
      v119 = v207;
    }
    else
    {
      v118 = (CInstallCheckpointSequence *)UnBCL::Object::operator new(0x90u);
      pExceptionObject = (__int64)v118;
      v119 = v207;
      if ( v118 )
        v120 = CInstallCheckpointSequence::CInstallCheckpointSequence(v118, v207 == 0);
      else
        v120 = 0;
    }
    v124 = (unsigned int (__fastcall ***)(_QWORD, CInstallCheckpointSequence *, const unsigned __int16 *, _QWORD))(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 8LL))((char *)this + 176);
    v125 = **v124;
    v126 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 368);
    v127 = UnBCL::String::get_CString(v126);
    if ( !v125(v124, v120, v127, v119) )
    {
      v203 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v204 = v203;
      *(_QWORD *)v211 = v203;
      if ( v203 )
      {
        UnBCL::Win32Exception::Win32Exception(v203, 0x54Fu, L"Failed to initialize rollback");
        *(_QWORD *)v204 = &UnBCL::Win32Exception::`local vftable';
      }
      else
      {
        v204 = 0;
      }
      pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                           v204,
                           "long __cdecl CSetupPlatformPrivate::Initialize(const unsigned short *,const unsigned short *,int,int,int)");
      throw (UnBCL::Win32Exception **)&pExceptionObject;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v210);
  }
  v128 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v129 = UnBCL::String::get_CString(v128);
  v130 = SPReadConfigValue(L"Parameters", L"SourceDirDriveLetter", v129);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v217, v130);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v217) )
  {
    v131 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v217);
    if ( (int)UnBCL::String::get_Length(v131) > 0 )
    {
      v132 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v217);
      *((_WORD *)this + 212) = *UnBCL::String::get_CString(v132);
    }
  }
  *((_DWORD *)this + 107) = 1800;
  v133 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v134 = UnBCL::String::get_CString(v133);
  v135 = SPReadConfigValue(L"DiagDumps", L"TIMEOUT", v134);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v219, v135);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v219) )
  {
    v136 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v219);
    v137 = UnBCL::String::get_CString(v136);
    *((_DWORD *)this + 107) = _wtoi(v137);
  }
  v138 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v139 = UnBCL::String::get_CString(v138);
  v140 = SPReadConfigValue(L"DiagDumps", L"Kernel", v139);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v216, v140);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v216) )
  {
    v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v216);
    v142 = UnBCL::String::get_CString(v141);
    v147 = 1;
    if ( UnBCL::String::Compare(v142, L"Yes", 1) )
    {
      v143 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v216);
      v144 = UnBCL::String::get_CString(v143);
      if ( UnBCL::String::Compare(v144, L"TRUE", 1) )
      {
        v145 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v216);
        v146 = UnBCL::String::get_CString(v145);
        if ( UnBCL::String::Compare(v146, L"1", 1) )
          v147 = 0;
      }
    }
    *((_DWORD *)this + 108) = v147;
  }
  v148 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 24);
  v149 = UnBCL::String::get_CString(v148);
  v150 = SPGetSectionLines(v149, L"DiagDumps.Extra");
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v215, v150);
  if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(v215) )
  {
    v151 = UnBCL::Object::operator new(0xB0u);
    pExceptionObject = (__int64)v151;
    if ( v151 )
      v151 = (void *)UnBCL::ArrayList<CDiagDumpItem *>::ArrayList<CDiagDumpItem *>(v151);
    UnBCL::SmartPtr<UnBCL::ArrayList<CDiagDumpItem *>>::SmartPtr<UnBCL::ArrayList<CDiagDumpItem *>>(v205, v151);
    UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=((char *)this + 440, v205);
    v205[0] = &UnBCL::SmartPtr<UnBCL::ArrayList<CDiagDumpItem *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v205);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 56) + 40LL))(*((_QWORD *)this + 56), 1);
    for ( i = 0; ; ++i )
    {
      v153 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v215);
      v154 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v153 + 8) + 12LL) + v153 + 8);
      if ( (int)i >= (**v154)(v154) )
        break;
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v205, 0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v208, 0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v210, 0);
      v155 = 0;
      v156 = 0;
      v157 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v215);
      v158 = *(int *)(*(_QWORD *)(v157 + 8) + 16LL) + v157 + 8;
      v159 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v158 + 24LL))(v158, i);
      v160 = UnBCL::String::IndexOf(*v159, 0x3Du);
      if ( v160 >= 0 )
      {
        v161 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v215);
        v162 = *(int *)(*(_QWORD *)(v161 + 8) + 16LL) + v161 + 8;
        v163 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v162 + 24LL))(v162, i);
        v164 = UnBCL::String::Substring(*v163, 0, v160);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v222, v164);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v205, v222);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v222);
        v165 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v215);
        v166 = *(int *)(*(_QWORD *)(v165 + 8) + 16LL) + v165 + 8;
        v167 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v166 + 24LL))(v166, i);
        v168 = UnBCL::String::Remove(*v167, 0, v160 + 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v223, v168);
        UnBCL::SmartPtr<UnBCL::String>::operator=(&v208, v223);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v223);
        v169 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v208);
        v170 = UnBCL::String::IndexOf(v169, 0x7Cu);
        if ( v170 >= 0 )
        {
          v171 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v208);
          v172 = UnBCL::String::Remove(v171, 0, v170 + 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v218, v172);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v210, v218);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v218);
          v173 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v208);
          v174 = UnBCL::String::Substring(v173, 0, v170);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v212, v174);
          UnBCL::SmartPtr<UnBCL::String>::operator=(&v208, v212);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v212);
        }
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&v208) )
        {
          v175 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v208);
          v176 = UnBCL::String::get_CString(v175);
          if ( UnBCL::String::Compare(v176, L"Service", 1) )
          {
            v177 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v208);
            v178 = UnBCL::String::get_CString(v177);
            if ( !UnBCL::String::Compare(v178, L"Process", 1) )
              v155 = 2;
          }
          else
          {
            v155 = 1;
          }
        }
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v210) )
        {
          v179 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v210);
          v180 = UnBCL::String::get_CString(v179);
          if ( !UnBCL::String::Compare(v180, L"Yes", 1)
            || (v181 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v210),
                v182 = UnBCL::String::get_CString(v181),
                !UnBCL::String::Compare(v182, L"TRUE", 1))
            || (v183 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v210),
                v184 = UnBCL::String::get_CString(v183),
                !UnBCL::String::Compare(v184, L"1", 1)) )
          {
            v156 = 1;
          }
        }
      }
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v205) && v155 )
      {
        v185 = *((_QWORD *)this + 56) + *(int *)(*(_QWORD *)(*((_QWORD *)this + 56) + 8LL) + 16LL);
        pExceptionObject = *(_QWORD *)(*(_QWORD *)(v185 + 8) + 40LL);
        v186 = UnBCL::Object::operator new(0x58u);
        v187 = v186;
        *(_QWORD *)v211 = v186;
        if ( v186 )
        {
          v188 = UnBCL::SmartPtr<UnBCL::String>::get_P(v205);
          v186 = (void *)CDiagDumpItem::CDiagDumpItem(v187, v188, v155, v156);
        }
        ((void (__fastcall *)(__int64, void *))pExceptionObject)(v185 + 8, v186);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v210);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v208);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v205);
    }
  }
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v215);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v216);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v219);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v217);
  v213 = &RAII::CAutoDelete<CTelemetry *>::`vftable';
  if ( v214 )
  {
    v189 = (void (__fastcall ***)(_QWORD, __int64))(v214 + 8 + *(int *)(*(_QWORD *)(v214 + 8) + 4LL));
    (**v189)(v189, 1);
    v214 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v220);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v221);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v224);
  return (unsigned int)ScratchDirectory;
}

```

## disassembly

```asm
0x180259cd4  push    rbp
0x180259cd6  push    rbx
0x180259cd7  push    rsi
0x180259cd8  push    rdi
0x180259cd9  push    r12
0x180259cdb  push    r13
0x180259cdd  push    r14
0x180259cdf  push    r15
0x180259ce1  lea     rbp, [rsp-1B8h]
0x180259ce9  sub     rsp, 2B8h
0x180259cf0  mov     [rbp+1F0h+var_178], 0FFFFFFFFFFFFFFFEh
0x180259cf8  mov     rax, cs:__security_cookie
0x180259cff  xor     rax, rsp
0x180259d02  mov     [rbp+1F0h+var_50], rax
0x180259d09  mov     [rbp+1F0h+var_250], r9d
0x180259d0d  mov     r13, r8
0x180259d10  mov     r14, rdx
0x180259d13  mov     rsi, rcx
0x180259d16  xor     r15d, r15d
0x180259d19  mov     [rsp+2F0h+var_278], r15d
0x180259d1e  call    ?SPGetPlatformDir@@YAPEAVString@UnBCL@@XZ; SPGetPlatformDir(void)
0x180259d23  mov     rdx, rax
0x180259d26  lea     rcx, [rsp+2F0h+var_290]
0x180259d2b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259d31  nop
0x180259d32  lea     r12, [rsi+0D0h]
0x180259d39  lea     rdx, [rsp+2F0h+var_290]
0x180259d3e  mov     rcx, r12
0x180259d41  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259d47  nop
0x180259d48  lea     rcx, [rsp+2F0h+var_290]
0x180259d4d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259d53  mov     rcx, r12
0x180259d56  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180259d5c  mov     rcx, rax
0x180259d5f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180259d65  mov     rcx, rax; lpPathName
0x180259d68  call    cs:__imp_SetCurrentDirectoryW
0x180259d6e  lea     eax, [r15+3Fh]
0x180259d72  mov     [rbp+1F0h+var_170], ax
0x180259d79  mov     [rbp+1F0h+var_16E], 3Ah ; ':'
0x180259d83  mov     rcx, r12
0x180259d86  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180259d8c  mov     rcx, rax
0x180259d8f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180259d95  movzx   ecx, word ptr [rax]
0x180259d98  mov     [rbp+1F0h+var_170], cx
0x180259d9f  lea     ecx, [r15+18h]
0x180259da3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180259da9  mov     rbx, rax
0x180259dac  mov     [rsp+2F0h+pExceptionObject], rax
0x180259db1  lea     rdi, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180259db8  test    rax, rax
0x180259dbb  jz      short loc_180259DD2
0x180259dbd  lea     rdx, [rbp+1F0h+var_170]
0x180259dc4  mov     rcx, rax
0x180259dc7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180259dcd  mov     [rbx], rdi
0x180259dd0  jmp     short loc_180259DD4
0x180259dd2  xor     ebx, ebx
0x180259dd4  mov     rdx, rbx
0x180259dd7  lea     rcx, [rsp+2F0h+var_290]
0x180259ddc  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259de2  nop
0x180259de3  lea     rcx, [rsi+0E0h]
0x180259dea  lea     rdx, [rsp+2F0h+var_290]
0x180259def  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259df5  nop
0x180259df6  lea     rcx, [rsp+2F0h+var_290]
0x180259dfb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259e01  mov     rcx, r12
0x180259e04  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180259e0a  mov     rcx, rax
0x180259e0d  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x180259e13  mov     rdx, rax
0x180259e16  lea     rcx, [rsp+2F0h+var_290]
0x180259e1b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259e21  nop
0x180259e22  lea     rdi, [rsi+0F0h]
0x180259e29  lea     rdx, [rsp+2F0h+var_290]
0x180259e2e  mov     rcx, rdi
0x180259e31  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259e37  nop
0x180259e38  lea     rcx, [rsp+2F0h+var_290]
0x180259e3d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259e43  lea     rdx, aSources_1; "Sources"
0x180259e4a  lea     rcx, [rbp+1F0h+var_248]
0x180259e4e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180259e54  mov     rbx, rax
0x180259e57  mov     rcx, rdi
0x180259e5a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180259e60  mov     rdx, rbx
0x180259e63  mov     rcx, rax
0x180259e66  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180259e6c  mov     rdx, rax
0x180259e6f  lea     rcx, [rsp+2F0h+var_290]
0x180259e74  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259e7a  nop
0x180259e7b  lea     rcx, [rsi+160h]
0x180259e82  lea     rdx, [rsp+2F0h+var_290]
0x180259e87  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259e8d  nop
0x180259e8e  lea     rcx, [rsp+2F0h+var_290]
0x180259e93  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259e99  nop
0x180259e9a  lea     rcx, [rbp+1F0h+var_248]
0x180259e9e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180259ea4  lea     rdx, aWork; "Work"
0x180259eab  lea     rcx, [rbp+1F0h+var_248]
0x180259eaf  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180259eb5  mov     rbx, rax
0x180259eb8  mov     rcx, rdi
0x180259ebb  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180259ec1  mov     rdx, rbx
0x180259ec4  mov     rcx, rax
0x180259ec7  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180259ecd  mov     rdx, rax
0x180259ed0  lea     rcx, [rsp+2F0h+var_290]
0x180259ed5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259edb  nop
0x180259edc  lea     rcx, [rsi+140h]
0x180259ee3  lea     rdx, [rsp+2F0h+var_290]
0x180259ee8  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259eee  nop
0x180259eef  lea     rcx, [rsp+2F0h+var_290]
0x180259ef4  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259efa  nop
0x180259efb  lea     rcx, [rbp+1F0h+var_248]
0x180259eff  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180259f05  lea     rdx, aStore; "Store"
0x180259f0c  lea     rcx, [rbp+1F0h+var_248]
0x180259f10  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180259f16  mov     rbx, rax
0x180259f19  mov     rcx, rdi
0x180259f1c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180259f22  mov     rdx, rbx
0x180259f25  mov     rcx, rax
0x180259f28  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180259f2e  mov     rdx, rax
0x180259f31  lea     rcx, [rsp+2F0h+var_290]
0x180259f36  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259f3c  nop
0x180259f3d  lea     rcx, [rsi+150h]
0x180259f44  lea     rdx, [rsp+2F0h+var_290]
0x180259f49  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259f4f  nop
0x180259f50  lea     rcx, [rsp+2F0h+var_290]
0x180259f55  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259f5b  nop
0x180259f5c  lea     rcx, [rbp+1F0h+var_248]
0x180259f60  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180259f66  lea     rdx, aRollback; "Rollback"
0x180259f6d  lea     rcx, [rbp+1F0h+var_248]
0x180259f71  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180259f77  mov     rbx, rax
0x180259f7a  lea     rdi, [rsi+160h]
0x180259f81  mov     rcx, rdi
0x180259f84  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180259f8a  mov     rdx, rbx
0x180259f8d  mov     rcx, rax
0x180259f90  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180259f96  mov     rdx, rax
0x180259f99  lea     rcx, [rsp+2F0h+var_290]
0x180259f9e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180259fa4  nop
0x180259fa5  lea     rbx, [rsi+170h]
0x180259fac  lea     rdx, [rsp+2F0h+var_290]
0x180259fb1  mov     rcx, rbx
0x180259fb4  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259fba  nop
0x180259fbb  lea     rcx, [rsp+2F0h+var_290]
0x180259fc0  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180259fc6  nop
0x180259fc7  lea     rcx, [rbp+1F0h+var_248]
0x180259fcb  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180259fd1  lea     rcx, [rsi+180h]
0x180259fd8  mov     rdx, rbx
0x180259fdb  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180259fe1  test    r14, r14
0x180259fe4  jz      short loc_18025A01A
0x180259fe6  mov     ecx, 18h
0x180259feb  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180259ff1  mov     rbx, rax
0x180259ff4  mov     [rsp+2F0h+pExceptionObject], rax
0x180259ff9  test    rax, rax
0x180259ffc  jz      short loc_18025A016
0x180259ffe  mov     rdx, r14
0x18025a001  mov     rcx, rax
0x18025a004  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18025a00a  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18025a011  mov     [rbx], rax
0x18025a014  jmp     short loc_18025A018
0x18025a016  xor     ebx, ebx
0x18025a018  jmp     short loc_18025A051
0x18025a01a  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x18025a021  lea     rcx, [rbp+1F0h+var_248]
0x18025a025  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18025a02b  mov     rbx, rax
0x18025a02e  mov     r15d, 1
0x18025a034  mov     [rsp+2F0h+var_278], r15d
0x18025a039  mov     rcx, rdi
0x18025a03c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18025a042  mov     rdx, rbx
0x18025a045  mov     rcx, rax
0x18025a048  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18025a04e  mov     rbx, rax
0x18025a051  mov     rdx, rbx
0x18025a054  lea     rcx, [rsp+2F0h+var_290]
0x18025a059  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18025a05f  nop
0x18025a060  lea     r14, [rsi+18h]
0x18025a064  lea     rdx, [rsp+2F0h+var_290]
0x18025a069  mov     rcx, r14
0x18025a06c  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18025a072  nop
0x18025a073  lea     rcx, [rsp+2F0h+var_290]
0x18025a078  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18025a07e  nop
0x18025a07f  test    r15b, 1
0x18025a083  jz      short loc_18025A08F
0x18025a085  lea     rcx, [rbp+1F0h+var_248]
0x18025a089  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18025a08f  mov     rcx, r14
0x18025a092  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18025a098  mov     rcx, rax
0x18025a09b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18025a0a1  mov     r8, rax; lpFileName
0x18025a0a4  lea     rdx, aInstallationid; "InstallationID"
0x18025a0ab  lea     rcx, szSection; "Parameters"
0x18025a0b2  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x18025a0b7  mov     rdx, rax
0x18025a0ba  lea     rcx, [rsp+2F0h+var_290]
0x18025a0bf  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18025a0c5  nop
0x18025a0c6  lea     rcx, [rsi+100h]
0x18025a0cd  lea     rdx, [rsp+2F0h+var_290]
0x18025a0d2  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18025a0d8  nop
0x18025a0d9  lea     rcx, [rsp+2F0h+var_290]
0x18025a0de  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18025a0e4  test    r13, r13
0x18025a0e7  jz      short loc_18025A11D
0x18025a0e9  mov     ecx, 18h
0x18025a0ee  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18025a0f4  mov     rbx, rax
0x18025a0f7  mov     [rsp+2F0h+pExceptionObject], rax
0x18025a0fc  test    rax, rax
0x18025a0ff  jz      short loc_18025A119
0x18025a101  mov     rdx, r13
0x18025a104  mov     rcx, rax
0x18025a107  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18025a10d  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18025a114  mov     [rbx], rax
0x18025a117  jmp     short loc_18025A11B
0x18025a119  xor     ebx, ebx
0x18025a11b  jmp     short loc_18025A11F
0x18025a11d  xor     ebx, ebx
0x18025a11f  mov     rdx, rbx
0x18025a122  lea     rcx, [rsp+2F0h+var_290]
0x18025a127  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18025a12d  nop
0x18025a12e  lea     rcx, [rsi+130h]
0x18025a135  lea     rdx, [rsp+2F0h+var_290]
0x18025a13a  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18025a140  nop
0x18025a141  lea     rcx, [rsp+2F0h+var_290]
0x18025a146  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18025a14c  mov     rcx, r14
0x18025a14f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18025a155  mov     rcx, rax
0x18025a158  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18025a15e  mov     r8, rax; lpFileName
0x18025a161  lea     rdx, aScratchdirecto_0; "ScratchDirectory"
0x18025a168  lea     rcx, szSection; "Parameters"
0x18025a16f  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x18025a174  mov     rdx, rax
0x18025a177  lea     rcx, [rsp+2F0h+var_290]
0x18025a17c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18025a182  nop
0x18025a183  lea     rbx, [rsi+110h]
0x18025a18a  lea     rdx, [rsp+2F0h+var_290]
0x18025a18f  mov     rcx, rbx
0x18025a192  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18025a198  nop
0x18025a199  lea     rcx, [rsp+2F0h+var_290]
0x18025a19e  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18025a1a4  mov     rcx, rbx
0x18025a1a7  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18025a1ad  test    rax, rax
0x18025a1b0  jz      loc_18025A387
0x18025a1b6  mov     edx, [rbp+1F0h+var_250]; int
0x18025a1b9  mov     rcx, rsi; this
0x18025a1bc  call    ?FindScratchDirectory@CSetupPlatformPrivate@@IEAAJH@Z; CSetupPlatformPrivate::FindScratchDirectory(int)
0x18025a1c1  mov     r15d, eax
0x18025a1c4  test    eax, eax
0x18025a1c6  jns     short loc_18025A241
0x18025a1c8  call    cs:__imp_GetLastError
0x18025a1ce  mov     edi, eax
0x18025a1d0  call    cs:__imp_CurrentIP
0x18025a1d6  mov     rbx, rax
  ... truncated ...
```
