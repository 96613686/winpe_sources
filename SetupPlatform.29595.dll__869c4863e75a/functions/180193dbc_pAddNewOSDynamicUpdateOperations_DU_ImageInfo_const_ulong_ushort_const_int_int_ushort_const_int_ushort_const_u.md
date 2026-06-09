# pAddNewOSDynamicUpdateOperations(DU::ImageInfo const *,ulong,ushort const *,int,int,ushort const *,int,ushort const *,ushort const *,ushort const *,int,COperationQueue *,CBaseInternalProgress *)

- ea: `0x180193dbc`
- end: `0x1801954ad`
- name: `?pAddNewOSDynamicUpdateOperations@@YAJPEBUImageInfo@DU@@KPEBGHH1H111HPEAVCOperationQueue@@PEAVCBaseInternalProgress@@@Z`
- size: `5873`
- prototype: `__int64 __fastcall(const struct DU::ImageInfo *, unsigned int, const unsigned __int16 *, int, int, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, struct COperationQueue *, struct CBaseInternalProgress *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180186e6c`
- `0x18018f1c0`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x18017d6c4`
- `0x18017e230`
- `0x180193dbc`
- `0x1802dd204`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180193e98`
- `KERNEL32!GetLastError` at `0x180193f1d`
- `KERNEL32!GetLastError` at `0x180193e98`
- `KERNEL32!GetLastError` at `0x180193f1d`
- `KERNEL32!CompareStringW` at `0x180194363`
- `KERNEL32!CompareStringW` at `0x1801943bb`
- `KERNEL32!CompareStringW` at `0x180194419`
- `KERNEL32!CompareStringW` at `0x180194363`
- `KERNEL32!CompareStringW` at `0x1801943bb`
- `KERNEL32!CompareStringW` at `0x180194419`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1801952b8`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180195311`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18019536a`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1801953c3`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18019541c`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180195475`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1801952b8`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180195311`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18019536a`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1801953c3`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18019541c`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180195475`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194024`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801940f2`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18019455c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194631`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801948cb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801949a1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194c25`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194cfb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194f8f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180195066`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194024`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801940f2`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18019455c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194631`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801948cb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801949a1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194c25`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194cfb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180194f8f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180195066`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194154`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194693`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194a03`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194d5d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801950c8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194154`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194693`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194a03`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180194d5d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801950c8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180193fec`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801940be`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194524`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801945fd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194892`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18019496d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194bec`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194cc7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194f55`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180195032`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180193fec`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801940be`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194524`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801945fd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194892`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18019496d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194bec`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194cc7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180194f55`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180195032`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194056`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194061`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194124`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019412f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019458e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194599`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194663`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019466e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801948fd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194908`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801949d3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801949de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194c57`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194c62`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194d2d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194d38`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194fc1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194fcc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180195098`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801950a3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194056`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194061`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194124`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019412f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019458e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194599`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194663`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18019466e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801948fd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194908`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801949d3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801949de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194c57`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194c62`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194d2d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194d38`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194fc1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180194fcc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180195098`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801950a3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194007`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194017`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194086`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801940d5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801940e5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019453f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019454f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801945be`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194614`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194624`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801948ad`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801948be`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019492e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194984`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194994`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194c07`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194c18`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194c88`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194cde`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194cee`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194f71`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194f82`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194ff2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180195049`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180195059`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194007`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194017`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194086`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801940d5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801940e5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019453f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019454f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801945be`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194614`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194624`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801948ad`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801948be`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18019492e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194984`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194994`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194c07`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194c18`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194c88`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194cde`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194cee`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194f71`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194f82`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180194ff2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180195049`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180195059`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019406e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019413a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194261`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801945a6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194679`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801947a7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194915`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801949e9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194b10`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194c6f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194d43`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194e6a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194fd9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801950ae`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801951d2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019529c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801952f5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019534e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801953a7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180195400`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180195459`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019406e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019413a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194261`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801945a6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194679`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801947a7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194915`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801949e9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194b10`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194c6f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194d43`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194e6a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180194fd9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801950ae`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801951d2`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18019529c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801952f5`

## string_xrefs

- `0x180193ee4`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x180193f65`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x1801952cc`: `long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,unsigned long,const unsigned short *,int,int,const unsigned short *,int,const unsigned short *,const unsigned short *,const unsigned short *,int,class COperationQueue *,class CBaseInternalProgress *)`
- `0x180195325`: `long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,unsigned long,const unsigned short *,int,int,const unsigned short *,int,const unsigned short *,const unsigned short *,const unsigned short *,int,class COperationQueue *,class CBaseInternalProgress *)`
- `0x18019537e`: `long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,unsigned long,const unsigned short *,int,int,const unsigned short *,int,const unsigned short *,const unsigned short *,const unsigned short *,int,class COperationQueue *,class CBaseInternalProgress *)`
- `0x1801953d7`: `long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,unsigned long,const unsigned short *,int,int,const unsigned short *,int,const unsigned short *,const unsigned short *,const unsigned short *,int,class COperationQueue *,class CBaseInternalProgress *)`
- `0x180195430`: `long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,unsigned long,const unsigned short *,int,int,const unsigned short *,int,const unsigned short *,const unsigned short *,const unsigned short *,int,class COperationQueue *,class CBaseInternalProgress *)`
- `0x180195489`: `long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,unsigned long,const unsigned short *,int,int,const unsigned short *,int,const unsigned short *,const unsigned short *,const unsigned short *,int,class COperationQueue *,class CBaseInternalProgress *)`
- `0x1801953b9`: `UpdatesFolder`
- `0x180193ed8`: `pAddNewOSDynamicUpdateOperations`
- `0x180193f59`: `pAddNewOSDynamicUpdateOperations`
- `0x1801940ca`: `Reserved.DynamicUpdate.Critical`
- `0x180194201`: `Download Critical Dynamic Updates`
- `0x1801942d0`: `Install Critical Dynamic Updates`
- `0x180194747`: `Download Driver Dynamic Updates`
- `0x180194609`: `Reserved.DynamicUpdate.Driver`
- `0x180194816`: `Install Driver Dynamic Updates`
- `0x180194ab0`: `Download OS Updates (DU) to keep installation up-to-date`
- `0x180194b7f`: `Install OS updates (DU) to keep installation up-to-date`
- `0x180194979`: `Reserved.DynamicUpdate.GDR`
- `0x180194cd3`: `Reserved.DynamicUpdate.Langpack`
- `0x180194e0a`: `Download Language Pack Dynamic Updates`
- `0x180194ed9`: `Install Language Pack Dynamic Updates`
- `0x180195172`: `Download Feature-On-Demand Dynamic Updates`
- `0x18019503e`: `Reserved.DynamicUpdate.FeaturesOnDemand`
- `0x180195241`: `Install Feature-On-Demand Dynamic Updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=66
__int64 __fastcall pAddNewOSDynamicUpdateOperations(
        const struct DU::ImageInfo *a1,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        const unsigned __int16 *a6,
        int a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        int a11,
        struct COperationQueue *a12,
        struct CBaseInternalProgress *a13)
{
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *v15; // r14
  DWORD LastError; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  char v23; // al
  _DWORD *v24; // rax
  int v25; // ecx
  const wchar_t *v26; // rax
  const struct UnBCL::String *v27; // rbx
  const struct UnBCL::String *v28; // rax
  struct UnBCL::String *v29; // rax
  UnBCL::String *v30; // rax
  UnBCL::String *v31; // rbx
  const struct UnBCL::String *v32; // rbx
  const struct UnBCL::String *v33; // rax
  struct UnBCL::String *v34; // rax
  void *v35; // rbx
  UnBCL::String *v36; // rax
  const unsigned __int16 *CString; // rdi
  UnBCL::String *v38; // rax
  const unsigned __int16 *v39; // rax
  __int64 v40; // rdx
  char *v41; // rcx
  __int64 v42; // rsi
  void (__fastcall *v43)(char *, void *); // r14
  void *v44; // rax
  void *v45; // rdi
  UnBCL::String *v46; // rax
  UnBCL::String *v47; // rax
  _DWORD *v48; // rax
  int v49; // eax
  const wchar_t *v50; // rcx
  __int64 v51; // rdi
  const wchar_t *v52; // rax
  int v53; // eax
  unsigned int v54; // edx
  const wchar_t *v55; // rax
  const wchar_t *v56; // rax
  const struct UnBCL::String *v57; // rbx
  const struct UnBCL::String *v58; // rax
  struct UnBCL::String *v59; // rax
  UnBCL::String *v60; // rax
  UnBCL::String *v61; // rbx
  const struct UnBCL::String *v62; // rbx
  const struct UnBCL::String *v63; // rax
  struct UnBCL::String *v64; // rax
  void *v65; // rbx
  UnBCL::String *v66; // rax
  const unsigned __int16 *v67; // rsi
  UnBCL::String *v68; // rax
  const unsigned __int16 *v69; // rax
  __int64 v70; // rdx
  char *v71; // rcx
  __int64 v72; // rsi
  void (__fastcall *v73)(char *, void *); // r14
  void *v74; // rax
  void *v75; // rdi
  UnBCL::String *v76; // rax
  UnBCL::String *v77; // rax
  char v78; // si
  _DWORD *v79; // rax
  bool v80; // zf
  const wchar_t *v81; // rax
  const struct UnBCL::String *v82; // rbx
  const struct UnBCL::String *v83; // rax
  struct UnBCL::String *v84; // rax
  UnBCL::String *v85; // rax
  UnBCL::String *v86; // rbx
  const struct UnBCL::String *v87; // rbx
  const struct UnBCL::String *v88; // rax
  struct UnBCL::String *v89; // rax
  void *v90; // rbx
  UnBCL::String *v91; // rax
  const unsigned __int16 *v92; // rdi
  UnBCL::String *v93; // rax
  const unsigned __int16 *v94; // rax
  __int64 v95; // rdx
  char *v96; // rcx
  __int64 v97; // rsi
  void (__fastcall *v98)(char *, void *); // r14
  void *v99; // rax
  void *v100; // rdi
  UnBCL::String *v101; // rax
  UnBCL::String *v102; // rax
  const struct UnBCL::String *v103; // rbx
  const struct UnBCL::String *v104; // rax
  struct UnBCL::String *v105; // rax
  UnBCL::String *v106; // rax
  UnBCL::String *v107; // rbx
  const struct UnBCL::String *v108; // rbx
  const struct UnBCL::String *v109; // rax
  struct UnBCL::String *v110; // rax
  void *v111; // rbx
  UnBCL::String *v112; // rax
  const unsigned __int16 *v113; // rdi
  UnBCL::String *v114; // rax
  const unsigned __int16 *v115; // rax
  __int64 v116; // rdx
  char *v117; // rcx
  __int64 v118; // rsi
  void (__fastcall *v119)(char *, void *); // r14
  void *v120; // rax
  void *v121; // rdi
  UnBCL::String *v122; // rax
  UnBCL::String *v123; // rax
  const wchar_t *v124; // rcx
  const struct UnBCL::String *v125; // rbx
  const struct UnBCL::String *v126; // rax
  struct UnBCL::String *v127; // rax
  UnBCL::String *v128; // rax
  UnBCL::String *v129; // rbx
  const struct UnBCL::String *v130; // rbx
  const struct UnBCL::String *v131; // rax
  struct UnBCL::String *v132; // rax
  void *v133; // rbx
  UnBCL::String *v134; // rax
  const unsigned __int16 *v135; // rdi
  UnBCL::String *v136; // rax
  const unsigned __int16 *v137; // rax
  __int64 v138; // rdx
  char *v139; // rcx
  __int64 v140; // rsi
  void (__fastcall *v141)(char *, void *); // r14
  void *v142; // rax
  void *v143; // rdi
  UnBCL::String *v144; // rax
  UnBCL::String *v145; // rax
  UnBCL::ArgumentNullException *v146; // rax
  UnBCL::ArgumentNullException *v147; // rbx
  UnBCL::ArgumentNullException *v148; // rax
  UnBCL::ArgumentNullException *v149; // rbx
  UnBCL::ArgumentNullException *v150; // rax
  UnBCL::ArgumentNullException *v151; // rbx
  UnBCL::ArgumentNullException *v152; // rax
  UnBCL::ArgumentNullException *v153; // rbx
  UnBCL::ArgumentNullException *v154; // rax
  UnBCL::ArgumentNullException *v155; // rbx
  UnBCL::ArgumentNullException *v156; // rax
  UnBCL::ArgumentNullException *v157; // rbx
  const unsigned __int16 *pExceptionObject; // [rsp+B8h] [rbp-80h] BYREF
  int v159; // [rsp+C0h] [rbp-78h] BYREF
  int v160; // [rsp+C4h] [rbp-74h] BYREF
  int v161; // [rsp+C8h] [rbp-70h] BYREF
  _BYTE v162[16]; // [rsp+D0h] [rbp-68h] BYREF
  _BYTE v163[16]; // [rsp+E0h] [rbp-58h] BYREF
  _BYTE v164[24]; // [rsp+F0h] [rbp-48h] BYREF
  int v165; // [rsp+108h] [rbp-30h]
  int v166; // [rsp+10Ch] [rbp-2Ch]
  int v167; // [rsp+110h] [rbp-28h]
  __int64 v168; // [rsp+118h] [rbp-20h] BYREF
  int v169; // [rsp+120h] [rbp-18h]
  _QWORD v170[3]; // [rsp+128h] [rbp-10h] BYREF
  __int64 v171; // [rsp+140h] [rbp+8h] BYREF
  __int64 v172; // [rsp+148h] [rbp+10h]
  int v173; // [rsp+158h] [rbp+20h]
  const unsigned __int16 *v174; // [rsp+160h] [rbp+28h]
  const unsigned __int16 *v175; // [rsp+168h] [rbp+30h]
  _BYTE v176[24]; // [rsp+170h] [rbp+38h] BYREF
  __int128 v177; // [rsp+188h] [rbp+50h] BYREF
  __int128 v178; // [rsp+198h] [rbp+60h]
  __int128 v179; // [rsp+1A8h] [rbp+70h]
  __int64 v180; // [rsp+1B8h] [rbp+80h]

  v180 = -2;
  v166 = a4;
  v13 = a3;
  v174 = a3;
  v165 = a2;
  v15 = a6;
  pExceptionObject = a6;
  v175 = a8;
  v167 = a11;
  if ( !a1 )
  {
    v148 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v149 = v148;
    v168 = (__int64)v148;
    if ( v148 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v148, L"DUImageInfo");
      *(_QWORD *)v149 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v149 = 0;
    }
    pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                   v149,
                                                   "long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,u"
                                                   "nsigned long,const unsigned short *,int,int,const unsigned short *,in"
                                                   "t,const unsigned short *,const unsigned short *,const unsigned short "
                                                   "*,int,class COperationQueue *,class CBaseInternalProgress *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !*((_QWORD *)a1 + 4) )
  {
    v150 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v151 = v150;
    v168 = (__int64)v150;
    if ( v150 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v150, L"DUImageInfo->Version");
      *(_QWORD *)v151 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v151 = 0;
    }
    pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                   v151,
                                                   "long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,u"
                                                   "nsigned long,const unsigned short *,int,int,const unsigned short *,in"
                                                   "t,const unsigned short *,const unsigned short *,const unsigned short "
                                                   "*,int,class COperationQueue *,class CBaseInternalProgress *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( (a2 & 0x1F) == 0 )
    return 2147942487LL;
  if ( !a3 )
  {
    v152 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v153 = v152;
    v168 = (__int64)v152;
    if ( v152 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v152, L"UpdatesFolder");
      *(_QWORD *)v153 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v153 = 0;
    }
    pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                   v153,
                                                   "long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *,u"
                                                   "nsigned long,const unsigned short *,int,int,const unsigned short *,in"
                                                   "t,const unsigned short *,const unsigned short *,const unsigned short "
                                                   "*,int,class COperationQueue *,class CBaseInternalProgress *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a7 )
  {
    if ( !a8 )
    {
      v154 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
      v155 = v154;
      v168 = (__int64)v154;
      if ( v154 )
      {
        UnBCL::ArgumentNullException::ArgumentNullException(v154, L"NewOSDir");
        *(_QWORD *)v155 = &UnBCL::ArgumentNullException::`local vftable';
      }
      else
      {
        v155 = 0;
      }
      pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                     v155,
                                                     "long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *"
                                                     ",unsigned long,const unsigned short *,int,int,const unsigned short "
                                                     "*,int,const unsigned short *,const unsigned short *,const unsigned "
                                                     "short *,int,class COperationQueue *,class CBaseInternalProgress *)");
      throw (UnBCL::ArgumentNullException **)&pExceptionObject;
    }
    if ( !a9 )
    {
      v156 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
      v157 = v156;
      v168 = (__int64)v156;
      if ( v156 )
      {
        UnBCL::ArgumentNullException::ArgumentNullException(v156, L"LogDir");
        *(_QWORD *)v157 = &UnBCL::ArgumentNullException::`local vftable';
      }
      else
      {
        v157 = 0;
      }
      pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                     v157,
                                                     "long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *"
                                                     ",unsigned long,const unsigned short *,int,int,const unsigned short "
                                                     "*,int,const unsigned short *,const unsigned short *,const unsigned "
                                                     "short *,int,class COperationQueue *,class CBaseInternalProgress *)");
      throw (UnBCL::ArgumentNullException **)&pExceptionObject;
    }
    if ( !a10 )
    {
      v146 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
      v147 = v146;
      v168 = (__int64)v146;
      if ( v146 )
      {
        UnBCL::ArgumentNullException::ArgumentNullException(v146, L"WorkDir");
        *(_QWORD *)v147 = &UnBCL::ArgumentNullException::`local vftable';
      }
      else
      {
        v147 = 0;
      }
      pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                     v147,
                                                     "long __cdecl pAddNewOSDynamicUpdateOperations(const DU::ImageInfo *"
                                                     ",unsigned long,const unsigned short *,int,int,const unsigned short "
                                                     "*,int,const unsigned short *,const unsigned short *,const unsigned "
                                                     "short *,int,class COperationQueue *,class CBaseInternalProgress *)");
      throw (UnBCL::ArgumentNullException **)&pExceptionObject;
    }
  }
  v159 = 0;
  v173 = SPIsConnectedStandbyDevice(&v159);
  if ( v173 < 0 )
  {
    LastError = GetLastError();
    v18 = CurrentIP();
    v19 = ConstructPartialMsgW(
            0x2000000u,
            "Failed to test whether this device is connected standby. Error: 0x%08X",
            v173);
    WdsSetupLogMessageW(
      v19,
      819200,
      L"D",
      0,
      941,
      L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
      L"pAddNewOSDynamicUpdateOperations",
      v18,
      LastError,
      0,
      0);
    v173 = 0;
  }
  if ( v159 )
  {
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = ConstructPartialMsgW(0x4000000u, "Connected-Standby device detected.");
    WdsSetupLogMessageW(
      v22,
      819200,
      L"D",
      0,
      946,
      L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
      L"pAddNewOSDynamicUpdateOperations",
      v21,
      v20,
      0,
      0);
  }
  v23 = v165;
  if ( (v165 & 1) != 0 )
  {
    v24 = (_DWORD *)*((_QWORD *)a1 + 4);
    if ( *v24 == 6 )
    {
      v25 = v24[1];
      if ( v25 == 2 )
      {
        v26 = L"393789f5-61c1-4881-b5e7-c47bcca90f94";
LABEL_20:
        v168 = (__int64)v26;
        v161 = 0;
        v160 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v163);
        if ( a5 )
        {
          v27 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v170, L"CriticalDU");
          v28 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v164, v13);
          v29 = UnBCL::Path::Combine(v28, v27);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v171, v29);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v163, &v171);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v171);
          UnBCL::String::~String((UnBCL::String *)v164);
          UnBCL::String::~String((UnBCL::String *)v170);
        }
        else
        {
          v30 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v31 = v30;
          v170[0] = v30;
          if ( v30 )
          {
            UnBCL::String::String(v30, v13);
            *(_QWORD *)v31 = &UnBCL::String::`local vftable';
          }
          else
          {
            v31 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v171, v31);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v163, &v171);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v171);
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v162);
        if ( a6 )
        {
          v32 = (const struct UnBCL::String *)UnBCL::String::String(
                                                (UnBCL::String *)v170,
                                                L"Reserved.DynamicUpdate.Critical");
          v33 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v164, a6);
          v34 = UnBCL::Path::Combine(v33, v32);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v171, v34);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v162, &v171);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v171);
          UnBCL::String::~String((UnBCL::String *)v164);
          UnBCL::String::~String((UnBCL::String *)v170);
        }
        v35 = UnBCL::Object::operator new(0x1A0u);
        v170[0] = v35;
        if ( v35 )
        {
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v162) )
          {
            v36 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
            CString = UnBCL::String::get_CString(v36);
          }
          else
          {
            CString = 0;
          }
          v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
          v39 = UnBCL::String::get_CString(v38);
          v40 = CDownloadDUUpdates::CDownloadDUUpdates(
                  v35,
                  L"Download Critical Dynamic Updates",
                  &v168,
                  1,
                  6,
                  &v161,
                  1,
                  &v160,
                  1,
                  v39,
                  v166,
                  1,
                  0,
                  CString,
                  a1);
        }
        else
        {
          v40 = 0;
        }
        if ( a13 )
          *((_DWORD *)a13 + 2) += *(_DWORD *)(v40 + 32);
        v41 = (char *)a12 + *(int *)(*((_QWORD *)a12 + 1) + 16LL) + 8;
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v41 + 40LL))(v41, v40);
        if ( a7 )
        {
          v42 = *(int *)(*((_QWORD *)a12 + 1) + 16LL);
          v43 = *(void (__fastcall **)(char *, void *))(*(_QWORD *)((char *)a12 + v42 + 8) + 40LL);
          v44 = UnBCL::Object::operator new(0x178u);
          v45 = v44;
          v170[0] = v44;
          if ( v44 )
          {
            v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
            UnBCL::String::get_CString(v46);
            v47 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
            UnBCL::String::get_CString(v47);
            v44 = (void *)CInstallDUUpdatesOffline::CInstallDUUpdatesOffline(
                            v45,
                            L"Install Critical Dynamic Updates",
                            a1);
          }
          v43((char *)a12 + v42 + 8, v44);
          v13 = v174;
          v15 = pExceptionObject;
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v162);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v163);
        v23 = v165;
        goto LABEL_41;
      }
      v26 = L"18e5ea77-e3d1-43b6-a0a8-fa3dbcd42e93";
      if ( v25 == 3 )
        goto LABEL_20;
    }
    v26 = L"e4b04398-adbd-4b69-93b9-477322331cd3";
    goto LABEL_20;
  }
LABEL_41:
  if ( (v23 & 4) != 0 )
  {
    v177 = 0;
    v178 = 0;
    v179 = 0;
    v48 = (_DWORD *)*((_QWORD *)a1 + 4);
    if ( *v48 != 6 )
      goto LABEL_51;
    if ( v48[1] == 2 )
    {
      v49 = CompareStringW(0x409u, 1u, *((PCNZWCH *)a1 + 2), -1, L"Server", -1);
      v50 = L"f3c2263d-b256-4c49-a246-973c0e366449";
      if ( v49 != 2 )
        v50 = L"405706ed-f1d7-47ea-91e1-eb8860039715";
      *(_QWORD *)&v177 = v50;
      LODWORD(v51) = 1;
      goto LABEL_63;
    }
    if ( v48[1] == 3 )
    {
      *(_QWORD *)&v177 = L"8c27cdba-6a1c-455e-af20-46b7771bbb96";
      if ( CompareStringW(0x409u, 1u, *((PCNZWCH *)a1 + 2), -1, L"Server", -1) == 2 )
      {
        *((_QWORD *)&v177 + 1) = L"bfd3e48c-c96b-43fd-8b09-98cdc89dc77e";
        *(_QWORD *)&v178 = L"f3c2263d-b256-4c49-a246-973c0e366449";
LABEL_58:
        LODWORD(v51) = 3;
LABEL_63:
        v171 = 0x20000000ALL;
        v172 = 1;
        v168 = 0x100000001LL;
        v169 = 1;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v162);
        if ( a5 )
        {
          v57 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, L"DriverDU");
          v58 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v164, v13);
          v59 = UnBCL::Path::Combine(v58, v57);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v170, v59);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v170);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v170);
          UnBCL::String::~String((UnBCL::String *)v164);
          UnBCL::String::~String((UnBCL::String *)v176);
        }
        else
        {
          v60 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v61 = v60;
          v170[0] = v60;
          if ( v60 )
          {
            UnBCL::String::String(v60, v13);
            *(_QWORD *)v61 = &UnBCL::String::`local vftable';
          }
          else
          {
            v61 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v61);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v163);
        if ( v15 )
        {
          v62 = (const struct UnBCL::String *)UnBCL::String::String(
                                                (UnBCL::String *)v170,
                                                L"Reserved.DynamicUpdate.Driver");
          v63 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v15);
          v64 = UnBCL::Path::Combine(v63, v62);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v64);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v163, v164);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
          UnBCL::String::~String((UnBCL::String *)v176);
          UnBCL::String::~String((UnBCL::String *)v170);
        }
        v65 = UnBCL::Object::operator new(0x1A0u);
        v170[0] = v65;
        if ( v65 )
        {
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v163) )
          {
            v66 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
            v67 = UnBCL::String::get_CString(v66);
          }
          else
          {
            v67 = 0;
          }
          v68 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
          v69 = UnBCL::String::get_CString(v68);
          v70 = CDownloadDUUpdates::CDownloadDUUpdates(
                  v65,
                  L"Download Driver Dynamic Updates",
                  &v177,
                  (unsigned int)v51,
                  2,
                  &v171,
                  4,
                  &v168,
                  3,
                  v69,
                  v166,
                  1,
                  0,
                  v67,
                  a1);
        }
        else
        {
          v70 = 0;
        }
        if ( a13 )
          *((_DWORD *)a13 + 2) += *(_DWORD *)(v70 + 32);
        v71 = (char *)a12 + *(int *)(*((_QWORD *)a12 + 1) + 16LL) + 8;
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v71 + 40LL))(v71, v70);
        if ( a7 )
        {
          v72 = *(int *)(*((_QWORD *)a12 + 1) + 16LL);
          v73 = *(void (__fastcall **)(char *, void *))(*(_QWORD *)((char *)a12 + v72 + 8) + 40LL);
          v74 = UnBCL::Object::operator new(0x178u);
          v75 = v74;
          v170[0] = v74;
          if ( v74 )
          {
            v76 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
            UnBCL::String::get_CString(v76);
            v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
            UnBCL::String::get_CString(v77);
            v74 = (void *)CInstallDUUpdatesOffline::CInstallDUUpdatesOffline(v75, L"Install Driver Dynamic Updates", a1);
          }
          v73((char *)a12 + v72 + 8, v74);
          v15 = pExceptionObject;
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v163);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v162);
        goto LABEL_84;
      }
      *((_QWORD *)&v177 + 1) = L"f7b29b7a-086b-43f9-9cc8-e1a2f8a31e08";
      v52 = L"405706ed-f1d7-47ea-91e1-eb8860039715";
    }
    else
    {
LABEL_51:
      v53 = CompareStringW(0x409u, 1u, *((PCNZWCH *)a1 + 2), -1, L"Server", -1);
      v54 = *(_DWORD *)(*((_QWORD *)a1 + 4) + 8LL);
      if ( v53 == 2 )
      {
        *(_QWORD *)&v177 = L"f3c2263d-b256-4c49-a246-973c0e366449";
        *((_QWORD *)&v177 + 1) = L"dcc3e261-03ff-448b-994f-7216a61203a5";
        *(_QWORD *)&v178 = L"323cceaf-b60b-4a0d-8a8a-3069efde76bf";
        v55 = L"687f5e48-d5bb-4d0d-ac8a-26ea828ae85a";
        if ( v54 <= 0x3AD7 )
          v55 = (const wchar_t *)*((_QWORD *)&v178 + 1);
        *((_QWORD *)&v178 + 1) = v55;
        LODWORD(v51) = (v54 > 0x3AD7) + 3;
        goto LABEL_63;
      }
      *(_QWORD *)&v177 = L"405706ed-f1d7-47ea-91e1-eb8860039715";
      if ( v54 >= 0x3839 )
      {
        *((_QWORD *)&v177 + 1) = L"34f268b4-7e2d-40e1-8966-8bb6ea3dad27";
        *(_QWORD *)&v178 = L"0ba562e6-a6ba-490d-bdce-93a770ba8d21";
        v56 = L"06da2f0c-7937-4e28-b46c-a37317eade73";
        if ( v54 <= 0x3839 )
          v56 = (const wchar_t *)*((_QWORD *)&v178 + 1);
        *((_QWORD *)&v178 + 1) = v56;
        v51 = (unsigned int)(v54 > 0x3839) + 3;
        if ( v54 > 0x3AD7 )
        {
          *((_QWORD *)&v177 + v51) = L"c70f1038-66ac-443d-9e58-ac22e891e4fb";
          *((_QWORD *)&v177 + (unsigned int)(v54 > 0x3839) + 4) = L"b7f52cfb-c9e9-4481-9bc0-c8b4e208ba39";
          LODWORD(v51) = (v54 > 0x3839) + 5;
        }
        goto LABEL_63;
      }
      *((_QWORD *)&v177 + 1) = L"0ba562e6-a6ba-490d-bdce-93a770ba8d21";
      v52 = L"34f268b4-7e2d-40e1-8966-8bb6ea3dad27";
    }
    *(_QWORD *)&v178 = v52;
    goto LABEL_58;
  }
LABEL_84:
  v78 = v165;
  if ( (v165 & 2) != 0 )
  {
    v79 = (_DWORD *)*((_QWORD *)a1 + 4);
    if ( *v79 != 6 || (v80 = v79[1] == 3, v81 = L"470bd53a-c36a-448f-b620-91feede01946", !v80) )
      v81 = L"abc45868-0c9c-4bc0-a36d-03d54113baf4";
    v168 = (__int64)v81;
    v160 = 0;
    v161 = 1;
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v162);
    if ( a5 )
    {
      v82 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v171, L"GDRDU");
      v83 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v174);
      v84 = UnBCL::Path::Combine(v83, v82);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v84);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
      UnBCL::String::~String((UnBCL::String *)v176);
      UnBCL::String::~String((UnBCL::String *)&v171);
    }
    else
    {
      v85 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v86 = v85;
      v170[0] = v85;
      if ( v85 )
      {
        UnBCL::String::String(v85, v174);
        *(_QWORD *)v86 = &UnBCL::String::`local vftable';
      }
      else
      {
        v86 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v86);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v163);
    if ( v15 )
    {
      v87 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v171, L"Reserved.DynamicUpdate.GDR");
      v88 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v15);
      v89 = UnBCL::Path::Combine(v88, v87);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v89);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v163, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
      UnBCL::String::~String((UnBCL::String *)v176);
      UnBCL::String::~String((UnBCL::String *)&v171);
    }
    v90 = UnBCL::Object::operator new(0x1A0u);
    v170[0] = v90;
    if ( v90 )
    {
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v163) )
      {
        v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
        v92 = UnBCL::String::get_CString(v91);
      }
      else
      {
        v92 = 0;
      }
      v93 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
      v94 = UnBCL::String::get_CString(v93);
      v95 = CDownloadDUUpdates::CDownloadDUUpdates(
              v90,
              L"Download OS Updates (DU) to keep installation up-to-date",
              &v168,
              1,
              4,
              &v160,
              1,
              &v161,
              1,
              v94,
              v166,
              0,
              1,
              v92,
              a1);
    }
    else
    {
      v95 = 0;
    }
    if ( a13 )
      *((_DWORD *)a13 + 2) += *(_DWORD *)(v95 + 32);
    v96 = (char *)a12 + *(int *)(*((_QWORD *)a12 + 1) + 16LL) + 8;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v96 + 40LL))(v96, v95);
    if ( a7 )
    {
      v97 = *(int *)(*((_QWORD *)a12 + 1) + 16LL);
      v98 = *(void (__fastcall **)(char *, void *))(*(_QWORD *)((char *)a12 + v97 + 8) + 40LL);
      v99 = UnBCL::Object::operator new(0x178u);
      v100 = v99;
      v170[0] = v99;
      if ( v99 )
      {
        v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
        UnBCL::String::get_CString(v101);
        v102 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
        UnBCL::String::get_CString(v102);
        v99 = (void *)CInstallDUUpdatesOffline::CInstallDUUpdatesOffline(
                        v100,
                        L"Install OS updates (DU) to keep installation up-to-date",
                        a1);
      }
      v98((char *)a12 + v97 + 8, v99);
      v15 = pExceptionObject;
      v78 = v165;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v163);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v162);
  }
  if ( (v78 & 8) != 0 )
  {
    v172 = 0;
    v171 = (__int64)L"6111a83d-7a6b-4a2c-a7c2-f222eebcabf4";
    v160 = 2;
    v161 = 1;
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v162);
    if ( a5 )
    {
      v103 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v170, L"LangpackDU");
      v104 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v174);
      v105 = UnBCL::Path::Combine(v104, v103);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v105);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
      UnBCL::String::~String((UnBCL::String *)v176);
      UnBCL::String::~String((UnBCL::String *)v170);
    }
    else
    {
      v106 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v107 = v106;
      v170[0] = v106;
      if ( v106 )
      {
        UnBCL::String::String(v106, v174);
        *(_QWORD *)v107 = &UnBCL::String::`local vftable';
      }
      else
      {
        v107 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v107);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v163);
    if ( v15 )
    {
      v108 = (const struct UnBCL::String *)UnBCL::String::String(
                                             (UnBCL::String *)v170,
                                             L"Reserved.DynamicUpdate.Langpack");
      v109 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v15);
      v110 = UnBCL::Path::Combine(v109, v108);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v110);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v163, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
      UnBCL::String::~String((UnBCL::String *)v176);
      UnBCL::String::~String((UnBCL::String *)v170);
    }
    v111 = UnBCL::Object::operator new(0x1A0u);
    v170[0] = v111;
    if ( v111 )
    {
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v163) )
      {
        v112 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
        v113 = UnBCL::String::get_CString(v112);
      }
      else
      {
        v113 = 0;
      }
      v114 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
      v115 = UnBCL::String::get_CString(v114);
      v116 = CDownloadDUUpdates::CDownloadDUUpdates(
               v111,
               L"Download Language Pack Dynamic Updates",
               &v171,
               1,
               4,
               &v160,
               1,
               &v161,
               1,
               v115,
               v166,
               0,
               1,
               v113,
               a1);
    }
    else
    {
      v116 = 0;
    }
    if ( a13 )
      *((_DWORD *)a13 + 2) += *(_DWORD *)(v116 + 32);
    v117 = (char *)a12 + *(int *)(*((_QWORD *)a12 + 1) + 16LL) + 8;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v117 + 40LL))(v117, v116);
    if ( a7 )
    {
      v118 = *(int *)(*((_QWORD *)a12 + 1) + 16LL);
      v119 = *(void (__fastcall **)(char *, void *))(*(_QWORD *)((char *)a12 + v118 + 8) + 40LL);
      v120 = UnBCL::Object::operator new(0x178u);
      v121 = v120;
      v170[0] = v120;
      if ( v120 )
      {
        v122 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
        UnBCL::String::get_CString(v122);
        v123 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
        UnBCL::String::get_CString(v123);
        v120 = (void *)CInstallDUUpdatesOffline::CInstallDUUpdatesOffline(
                         v121,
                         L"Install Language Pack Dynamic Updates",
                         a1);
      }
      v119((char *)a12 + v118 + 8, v120);
      v15 = pExceptionObject;
      v78 = v165;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v163);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v162);
  }
  if ( (v78 & 0x10) != 0 )
  {
    v124 = L"e104dd76-2895-41c4-9eb5-c483a61e9427";
    if ( *(_DWORD *)(*((_QWORD *)a1 + 4) + 8LL) > 0x3AD7u )
      v124 = L"3efabf46-3037-4c85-a752-3189e574b621";
    v168 = (__int64)v124;
    v160 = 2;
    v161 = 1;
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v162);
    if ( a5 )
    {
      v125 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v171, L"FeatureOnDemandDU");
      v126 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v174);
      v127 = UnBCL::Path::Combine(v126, v125);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v127);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
      UnBCL::String::~String((UnBCL::String *)v176);
      UnBCL::String::~String((UnBCL::String *)&v171);
    }
    else
    {
      v128 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v129 = v128;
      v170[0] = v128;
      if ( v128 )
      {
        UnBCL::String::String(v128, v174);
        *(_QWORD *)v129 = &UnBCL::String::`local vftable';
      }
      else
      {
        v129 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v129);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v162, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v163);
    if ( v15 )
    {
      v130 = (const struct UnBCL::String *)UnBCL::String::String(
                                             (UnBCL::String *)&v171,
                                             L"Reserved.DynamicUpdate.FeaturesOnDemand");
      v131 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v176, v15);
      v132 = UnBCL::Path::Combine(v131, v130);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v132);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v163, v164);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
      UnBCL::String::~String((UnBCL::String *)v176);
      UnBCL::String::~String((UnBCL::String *)&v171);
    }
    v133 = UnBCL::Object::operator new(0x1A0u);
    v170[0] = v133;
    if ( v133 )
    {
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v163) )
      {
        v134 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
        v135 = UnBCL::String::get_CString(v134);
      }
      else
      {
        v135 = 0;
      }
      v136 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
      v137 = UnBCL::String::get_CString(v136);
      v138 = CDownloadDUUpdates::CDownloadDUUpdates(
               v133,
               L"Download Feature-On-Demand Dynamic Updates",
               &v168,
               1,
               4,
               &v160,
               1,
               &v161,
               1,
               v137,
               v166,
               0,
               1,
               v135,
               a1);
    }
    else
    {
      v138 = 0;
    }
    if ( a13 )
      *((_DWORD *)a13 + 2) += *(_DWORD *)(v138 + 32);
    v139 = (char *)a12 + *(int *)(*((_QWORD *)a12 + 1) + 16LL) + 8;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v139 + 40LL))(v139, v138);
    if ( a7 )
    {
      v140 = *(int *)(*((_QWORD *)a12 + 1) + 16LL);
      v141 = *(void (__fastcall **)(char *, void *))(*(_QWORD *)((char *)a12 + v140 + 8) + 40LL);
      v142 = UnBCL::Object::operator new(0x178u);
      v143 = v142;
      v170[0] = v142;
      if ( v142 )
      {
        v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
        UnBCL::String::get_CString(v144);
        v145 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
        UnBCL::String::get_CString(v145);
        v142 = (void *)CInstallDUUpdatesOffline::CInstallDUUpdatesOffline(
                         v143,
                         L"Install Feature-On-Demand Dynamic Updates",
                         a1);
      }
      v141((char *)a12 + v140 + 8, v142);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v163);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v162);
  }
  return (unsigned int)v173;
}

```

## disassembly

```asm
0x180193dbc  mov     rax, rsp
0x180193dbf  push    rbp
0x180193dc0  push    rsi
0x180193dc1  push    rdi
0x180193dc2  push    r12
0x180193dc4  push    r13
0x180193dc6  push    r14
0x180193dc8  push    r15
0x180193dca  lea     rbp, [rax-0C8h]
0x180193dd1  sub     rsp, 1C0h
0x180193dd8  mov     [rbp+0C0h+var_40], 0FFFFFFFFFFFFFFFEh
0x180193de3  mov     [rax+10h], rbx
0x180193de7  mov     [rbp+0C0h+var_EC], r9d
0x180193deb  mov     rsi, r8
0x180193dee  mov     [rbp+0C0h+var_98], r8
0x180193df2  mov     eax, edx
0x180193df4  mov     [rbp+0C0h+var_F0], edx
0x180193df7  mov     r12, rcx
0x180193dfa  mov     r14, [rbp+0C0h+arg_28]
0x180193e01  mov     [rbp+0C0h+pExceptionObject], r14
0x180193e05  mov     rcx, [rbp+0C0h+arg_38]
0x180193e0c  mov     [rbp+0C0h+var_90], rcx
0x180193e10  mov     edx, [rbp+0C0h+arg_50]
0x180193e16  mov     [rbp+0C0h+var_E8], edx
0x180193e19  mov     r13, [rbp+0C0h+arg_58]
0x180193e20  mov     r15, [rbp+0C0h+arg_60]
0x180193e27  test    r12, r12
0x180193e2a  jz      loc_1801952F0
0x180193e30  cmp     qword ptr [r12+20h], 0
0x180193e36  jz      loc_180195349
0x180193e3c  test    al, 1Fh
0x180193e3e  jnz     short loc_180193E4A
0x180193e40  mov     eax, 80070057h
0x180193e45  jmp     loc_18019527C
0x180193e4a  test    rsi, rsi
0x180193e4d  jz      loc_1801953A2
0x180193e53  cmp     [rbp+0C0h+arg_30], 0
0x180193e5a  jz      short loc_180193E81
0x180193e5c  test    rcx, rcx
0x180193e5f  jz      loc_1801953FB
0x180193e65  cmp     [rbp+0C0h+arg_40], 0
0x180193e6d  jz      loc_180195454
0x180193e73  cmp     [rbp+0C0h+arg_48], 0
0x180193e7b  jz      loc_180195297
0x180193e81  mov     [rbp+0C0h+var_138], 0
0x180193e88  lea     rcx, [rbp+0C0h+var_138]; int *
0x180193e8c  call    ?SPIsConnectedStandbyDevice@@YAJAEAH@Z; SPIsConnectedStandbyDevice(int &)
0x180193e91  mov     [rbp+0C0h+var_A0], eax
0x180193e94  test    eax, eax
0x180193e96  jns     short loc_180193F17
0x180193e98  call    cs:__imp_GetLastError
0x180193e9e  mov     edi, eax
0x180193ea0  call    cs:__imp_CurrentIP
0x180193ea6  mov     rbx, rax
0x180193ea9  mov     r8d, [rbp+0C0h+var_A0]
0x180193ead  lea     rdx, aFailedToTestWh; "Failed to test whether this device is c"...
0x180193eb4  mov     ecx, 2000000h; unsigned int
0x180193eb9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180193ebe  mov     [rsp+1F0h+var_1A0], 0
0x180193ec6  mov     qword ptr [rsp+1F0h+var_1A8], 0
0x180193ecf  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180193ed3  mov     qword ptr [rsp+1F0h+var_1B8], rbx
0x180193ed8  lea     rcx, aPaddnewosdynam; "pAddNewOSDynamicUpdateOperations"
0x180193edf  mov     [rsp+1F0h+var_1C0], rcx
0x180193ee4  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180193eeb  mov     qword ptr [rsp+1F0h+cchCount2], rcx
0x180193ef0  mov     dword ptr [rsp+1F0h+lpString2], 3ADh
0x180193ef8  xor     r9d, r9d
0x180193efb  lea     r8, aD_0; "D"
0x180193f02  mov     edx, 0C8000h
0x180193f07  mov     rcx, rax
0x180193f0a  call    cs:__imp_WdsSetupLogMessageW
0x180193f10  mov     [rbp+0C0h+var_A0], 0
0x180193f17  cmp     [rbp+0C0h+var_138], 0
0x180193f1b  jz      short loc_180193F91
0x180193f1d  call    cs:__imp_GetLastError
0x180193f23  mov     edi, eax
0x180193f25  call    cs:__imp_CurrentIP
0x180193f2b  mov     rbx, rax
0x180193f2e  lea     rdx, aConnectedStand_0; "Connected-Standby device detected."
0x180193f35  mov     ecx, 4000000h; unsigned int
0x180193f3a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180193f3f  mov     [rsp+1F0h+var_1A0], 0
0x180193f47  mov     qword ptr [rsp+1F0h+var_1A8], 0
0x180193f50  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180193f54  mov     qword ptr [rsp+1F0h+var_1B8], rbx
0x180193f59  lea     rcx, aPaddnewosdynam; "pAddNewOSDynamicUpdateOperations"
0x180193f60  mov     [rsp+1F0h+var_1C0], rcx
0x180193f65  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180193f6c  mov     qword ptr [rsp+1F0h+cchCount2], rcx
0x180193f71  mov     dword ptr [rsp+1F0h+lpString2], 3B2h
0x180193f79  xor     r9d, r9d
0x180193f7c  lea     r8, aD_0; "D"
0x180193f83  mov     edx, 0C8000h
0x180193f88  mov     rcx, rax
0x180193f8b  call    cs:__imp_WdsSetupLogMessageW
0x180193f91  lea     rdi, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180193f98  mov     ebx, 1
0x180193f9d  mov     eax, [rbp+0C0h+var_F0]
0x180193fa0  test    bl, al
0x180193fa2  jz      loc_180194317
0x180193fa8  mov     rax, [r12+20h]
0x180193fad  cmp     dword ptr [rax], 6
0x180193fb0  jnz     short loc_180193FCF
0x180193fb2  mov     ecx, [rax+4]
0x180193fb5  cmp     ecx, 2
0x180193fb8  jnz     short loc_180193FC3
0x180193fba  lea     rax, a393789f561c148; "393789f5-61c1-4881-b5e7-c47bcca90f94"
0x180193fc1  jmp     short loc_180193FD6
0x180193fc3  cmp     ecx, 3
0x180193fc6  lea     rax, a18e5ea77E3d143; "18e5ea77-e3d1-43b6-a0a8-fa3dbcd42e93"
0x180193fcd  jz      short loc_180193FD6
0x180193fcf  lea     rax, aE4b04398Adbd4b; "e4b04398-adbd-4b69-93b9-477322331cd3"
0x180193fd6  mov     [rbp+0C0h+var_E0], rax
0x180193fda  mov     [rbp+0C0h+var_130], 0
0x180193fe1  mov     [rbp+0C0h+var_134], 0
0x180193fe8  lea     rcx, [rbp+0C0h+var_118]
0x180193fec  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180193ff2  nop
0x180193ff3  cmp     [rbp+0C0h+arg_20], 0
0x180193ffa  jz      short loc_180194069
0x180193ffc  lea     rdx, aCriticaldu; "CriticalDU"
0x180194003  lea     rcx, [rbp+0C0h+var_D0]
0x180194007  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18019400d  mov     rbx, rax
0x180194010  mov     rdx, rsi
0x180194013  lea     rcx, [rbp+0C0h+var_108]
0x180194017  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18019401d  nop
0x18019401e  mov     rdx, rbx
0x180194021  mov     rcx, rax
0x180194024  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18019402a  mov     rdx, rax
0x18019402d  lea     rcx, [rbp+0C0h+var_B8]
0x180194031  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180194037  nop
0x180194038  lea     rdx, [rbp+0C0h+var_B8]
0x18019403c  lea     rcx, [rbp+0C0h+var_118]
0x180194040  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180194046  nop
0x180194047  lea     rcx, [rbp+0C0h+var_B8]
0x18019404b  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180194051  nop
0x180194052  lea     rcx, [rbp+0C0h+var_108]
0x180194056  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18019405c  nop
0x18019405d  lea     rcx, [rbp+0C0h+var_D0]
0x180194061  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180194067  jmp     short loc_1801940BA
0x180194069  mov     ecx, 18h
0x18019406e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180194074  mov     rbx, rax
0x180194077  mov     [rbp+0C0h+var_D0], rax
0x18019407b  test    rax, rax
0x18019407e  jz      short loc_180194091
0x180194080  mov     rdx, rsi
0x180194083  mov     rcx, rax
0x180194086  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18019408c  mov     [rbx], rdi
0x18019408f  jmp     short loc_180194093
0x180194091  xor     ebx, ebx
0x180194093  mov     rdx, rbx
0x180194096  lea     rcx, [rbp+0C0h+var_B8]
0x18019409a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801940a0  nop
0x1801940a1  lea     rdx, [rbp+0C0h+var_B8]
0x1801940a5  lea     rcx, [rbp+0C0h+var_118]
0x1801940a9  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1801940af  nop
0x1801940b0  lea     rcx, [rbp+0C0h+var_B8]
0x1801940b4  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1801940ba  lea     rcx, [rbp+0C0h+var_128]
0x1801940be  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1801940c4  nop
0x1801940c5  test    r14, r14
0x1801940c8  jz      short loc_180194135
0x1801940ca  lea     rdx, aReservedDynami; "Reserved.DynamicUpdate.Critical"
0x1801940d1  lea     rcx, [rbp+0C0h+var_D0]
0x1801940d5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801940db  mov     rbx, rax
0x1801940de  mov     rdx, r14
0x1801940e1  lea     rcx, [rbp+0C0h+var_108]
0x1801940e5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801940eb  nop
0x1801940ec  mov     rdx, rbx
0x1801940ef  mov     rcx, rax
0x1801940f2  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1801940f8  mov     rdx, rax
0x1801940fb  lea     rcx, [rbp+0C0h+var_B8]
0x1801940ff  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180194105  nop
0x180194106  lea     rdx, [rbp+0C0h+var_B8]
0x18019410a  lea     rcx, [rbp+0C0h+var_128]
0x18019410e  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180194114  nop
0x180194115  lea     rcx, [rbp+0C0h+var_B8]
0x180194119  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18019411f  nop
0x180194120  lea     rcx, [rbp+0C0h+var_108]
0x180194124  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18019412a  nop
0x18019412b  lea     rcx, [rbp+0C0h+var_D0]
0x18019412f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180194135  mov     ecx, 1A0h
0x18019413a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180194140  mov     rbx, rax
0x180194143  mov     [rbp+0C0h+var_D0], rax
0x180194147  test    rax, rax
0x18019414a  jz      loc_180194215
0x180194150  lea     rcx, [rbp+0C0h+var_128]
0x180194154  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18019415a  test    rax, rax
0x18019415d  jz      short loc_180194177
0x18019415f  lea     rcx, [rbp+0C0h+var_128]
0x180194163  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180194169  mov     rcx, rax
0x18019416c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180194172  mov     rdi, rax
0x180194175  jmp     short loc_180194179
0x180194177  xor     edi, edi
0x180194179  lea     rcx, [rbp+0C0h+var_118]
0x18019417d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180194183  mov     rcx, rax
0x180194186  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019418c  mov     dword ptr [rsp+98h], 0Fh
0x180194197  mov     [rsp+1F0h+var_160], 10h
0x1801941a2  lea     rcx, aCritical; "Critical"
0x1801941a9  mov     qword ptr [rsp+1F0h+var_168], rcx
0x1801941b1  mov     [rsp+70h], r12
0x1801941b6  mov     [rsp+1F0h+var_188], rdi
0x1801941bb  mov     dword ptr [rsp+1F0h+var_190], 0
0x1801941c3  mov     edx, 1
0x1801941c8  mov     [rsp+1F0h+var_198], edx
0x1801941cc  mov     ecx, [rbp+0C0h+var_EC]
0x1801941cf  mov     [rsp+1F0h+var_1A0], ecx
0x1801941d3  mov     qword ptr [rsp+1F0h+var_1A8], rax
0x1801941d8  mov     dword ptr [rsp+1F0h+var_1B0], edx
0x1801941dc  lea     rax, [rbp+0C0h+var_134]
0x1801941e0  mov     qword ptr [rsp+1F0h+var_1B8], rax
0x1801941e5  mov     dword ptr [rsp+1F0h+var_1C0], edx
0x1801941e9  lea     rax, [rbp+0C0h+var_130]
0x1801941ed  mov     qword ptr [rsp+1F0h+cchCount2], rax
0x1801941f2  mov     dword ptr [rsp+1F0h+lpString2], 6
0x1801941fa  mov     r9d, edx
0x1801941fd  lea     r8, [rbp+0C0h+var_E0]
0x180194201  lea     rdx, aDownloadCritic; "Download Critical Dynamic Updates"
0x180194208  mov     rcx, rbx
0x18019420b  call    ??0CDownloadDUUpdates@@QEAA@PEBGPEAPEBGIHQEAKI2I0HHH0PEBUImageInfo@DU@@0H0HW4OP_OPERATION_ID@@@Z; CDownloadDUUpdates::CDownloadDUUpdates(ushort const *,ushort const * *,uint,int,ulong * const,uint,ulong * const,uint,ushort const *,int,int,int,ushort const *,DU::ImageInfo const *,ushort const *,int,ushort const *,int,OP_OPERATION_ID)
0x180194210  mov     rdx, rax
0x180194213  jmp     short loc_180194217
0x180194215  xor     edx, edx
0x180194217  test    r15, r15
0x18019421a  jz      short loc_180194223
0x18019421c  mov     eax, [rdx+20h]
0x18019421f  add     [r15+8], eax
0x180194223  mov     rax, [r13+8]
0x180194227  movsxd  rcx, dword ptr [rax+10h]
0x18019422b  add     rcx, 8
0x18019422f  add     rcx, r13
0x180194232  mov     rax, [rcx]
0x180194235  mov     rax, [rax+28h]
0x180194239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019423e  cmp     [rbp+0C0h+arg_30], 0
0x180194245  jz      loc_1801942FA
0x18019424b  mov     rax, [r13+8]
0x18019424f  movsxd  rsi, dword ptr [rax+10h]
0x180194253  mov     rax, [rsi+r13+8]
0x180194258  mov     r14, [rax+28h]
0x18019425c  mov     ecx, 178h
0x180194261  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180194267  mov     rdi, rax
0x18019426a  mov     [rbp+0C0h+var_D0], rax
0x18019426e  test    rax, rax
0x180194271  jz      short loc_1801942E0
0x180194273  lea     rcx, [rbp+0C0h+var_128]
0x180194277  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18019427d  mov     rcx, rax
0x180194280  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180194286  mov     rbx, rax
0x180194289  lea     rcx, [rbp+0C0h+var_118]
0x18019428d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180194293  mov     rcx, rax
0x180194296  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18019429c  mov     dword ptr [rsp+1F0h+var_188], 1Ah
0x1801942a4  mov     dword ptr [rsp+1F0h+var_190], 3Eh ; '>'
0x1801942ac  mov     ecx, [rbp+0C0h+var_138]
0x1801942af  mov     [rsp+1F0h+var_1A8], ecx
0x1801942b3  mov     ecx, [rbp+0C0h+var_E8]
0x1801942b6  mov     dword ptr [rsp+1F0h+var_1B0], ecx
0x1801942ba  mov     rcx, [rbp+0C0h+var_90]
0x1801942be  mov     qword ptr [rsp+1F0h+var_1B8], rcx
0x1801942c3  mov     [rsp+1F0h+var_1C0], rbx
0x1801942c8  mov     qword ptr [rsp+1F0h+cchCount2], rax
0x1801942cd  mov     r8, r12
0x1801942d0  lea     rdx, aInstallCritica_0; "Install Critical Dynamic Updates"
0x1801942d7  mov     rcx, rdi
0x1801942da  call    ??0CInstallDUUpdatesOffline@@QEAA@PEBGPEBUImageInfo@DU@@0H000HHH_JHW4OP_OPERATION_ID@@@Z; CInstallDUUpdatesOffline::CInstallDUUpdatesOffline(ushort const *,DU::ImageInfo const *,ushort const *,int,ushort const *,ushort const *,ushort const *,int,int,int,__int64,int,OP_OPERATION_ID)
0x1801942df  nop
0x1801942e0  mov     rdx, rax
0x1801942e3  lea     rcx, [r13+8]
  ... truncated ...
```
