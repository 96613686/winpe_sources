# pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)

- ea: `0x1802ed994`
- end: `0x1802ee59b`
- name: `?pSPCopyFile@@YAJPEAVString@UnBCL@@0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z22HH@Z`
- size: `3079`
- prototype: `void __fastcall __noreturn(struct UnBCL::String *, struct UnBCL::String *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, void *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1802cd8b0`

## callees

- `0x180013804`
- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x1802ed994`
- `0x1803f2ca0`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802edd7e`
- `KERNEL32!GetLastError` at `0x1802edd8f`
- `KERNEL32!GetLastError` at `0x1802ede05`
- `KERNEL32!GetLastError` at `0x1802ede16`
- `KERNEL32!GetLastError` at `0x1802edfa7`
- `KERNEL32!GetLastError` at `0x1802edfbd`
- `KERNEL32!GetLastError` at `0x1802edfdd`
- `KERNEL32!GetLastError` at `0x1802ee098`
- `KERNEL32!GetLastError` at `0x1802ee0ae`
- `KERNEL32!GetLastError` at `0x1802ee0ce`
- `KERNEL32!GetLastError` at `0x1802ee189`
- `KERNEL32!GetLastError` at `0x1802ee19f`
- `KERNEL32!GetLastError` at `0x1802ee1bf`
- `KERNEL32!GetLastError` at `0x1802ee27d`
- `KERNEL32!GetLastError` at `0x1802ee293`
- `KERNEL32!GetLastError` at `0x1802ee2bd`
- `KERNEL32!GetLastError` at `0x1802ee368`
- `KERNEL32!GetLastError` at `0x1802ee410`
- `KERNEL32!GetLastError` at `0x1802ee4b0`
- `KERNEL32!GetLastError` at `0x1802ee4c9`
- `KERNEL32!GetLastError` at `0x1802edd7e`
- `KERNEL32!GetLastError` at `0x1802edd8f`
- `KERNEL32!GetLastError` at `0x1802ede05`
- `KERNEL32!GetLastError` at `0x1802ede16`
- `KERNEL32!GetLastError` at `0x1802edfa7`
- `KERNEL32!GetLastError` at `0x1802edfbd`
- `KERNEL32!GetLastError` at `0x1802edfdd`
- `KERNEL32!GetLastError` at `0x1802ee098`
- `KERNEL32!GetLastError` at `0x1802ee0ae`
- `KERNEL32!GetLastError` at `0x1802ee0ce`
- `KERNEL32!GetLastError` at `0x1802ee189`
- `KERNEL32!GetLastError` at `0x1802ee19f`
- `KERNEL32!GetLastError` at `0x1802ee1bf`
- `KERNEL32!GetLastError` at `0x1802ee27d`
- `KERNEL32!GetLastError` at `0x1802ee293`
- `KERNEL32!GetLastError` at `0x1802ee2bd`
- `KERNEL32!GetLastError` at `0x1802ee368`
- `KERNEL32!GetLastError` at `0x1802ee410`
- `KERNEL32!GetLastError` at `0x1802ee4b0`
- `KERNEL32!GetLastError` at `0x1802ee4c9`
- `KERNEL32!SetFileAttributesW` at `0x1802edd70`
- `KERNEL32!SetFileAttributesW` at `0x1802edd70`
- `KERNEL32!GetFileAttributesW` at `0x1802edd43`
- `KERNEL32!GetFileAttributesW` at `0x1802edd43`
- `KERNEL32!CreateFileW` at `0x1802edb47`
- `KERNEL32!CreateFileW` at `0x1802edbbb`
- `KERNEL32!CreateFileW` at `0x1802edb47`
- `KERNEL32!CreateFileW` at `0x1802edbbb`
- `KERNEL32!WriteFile` at `0x1802edc59`
- `KERNEL32!WriteFile` at `0x1802edc59`
- `KERNEL32!GetFileSizeEx` at `0x1802edb6a`
- `KERNEL32!GetFileSizeEx` at `0x1802edb6a`
- `KERNEL32!ReadFile` at `0x1802edc28`
- `KERNEL32!ReadFile` at `0x1802edc28`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802ed9f4`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802eda5d`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802ed9f4`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802eda5d`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802edaf0`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802edaf0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802edf05`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802edf66`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802edf05`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802edf66`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802edd07`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802edd07`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802eda26`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802eda89`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802eda26`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802eda89`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802eda14`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802eda7d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802eda14`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802eda7d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802edee8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802edf49`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802edee8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802edf49`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802eda48`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802edaab`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802eda48`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802edaab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edb19`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edb90`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edd31`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edd5c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edd9f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802ede26`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edff6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802ee0e7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802ee1d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edb19`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edb90`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edd31`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edd5c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edd9f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802ede26`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802edff6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802ee0e7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802ee1d8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edb22`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edb99`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edd3a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edd65`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edda8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802ede2f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edfff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802ee0f0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802ee1e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edb22`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edb99`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edd3a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edd65`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edda8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802ede2f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802edfff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802ee0f0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802ee1e1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802eda54`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802edab7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802edea8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802edeb7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802eda54`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802edab7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802edea8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802edeb7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda05`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda34`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda6e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda97`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda05`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda34`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda6e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802eda97`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ede99`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee069`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee15a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee24b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee32e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee3d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee47e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee53a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ede99`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee069`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee15a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee24b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee32e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee3d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee47e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802ee53a`
- `WDSCORE!CurrentIP` at `0x1802edd86`
- `WDSCORE!CurrentIP` at `0x1802ede0d`
- `WDSCORE!CurrentIP` at `0x1802edfe5`
- `WDSCORE!CurrentIP` at `0x1802ee0d6`
- `WDSCORE!CurrentIP` at `0x1802ee1c7`
- `WDSCORE!CurrentIP` at `0x1802ee2c5`
- `WDSCORE!CurrentIP` at `0x1802ee370`
- `WDSCORE!CurrentIP` at `0x1802ee418`
- `WDSCORE!CurrentIP` at `0x1802ee4d1`
- `WDSCORE!CurrentIP` at `0x1802edd86`
- `WDSCORE!CurrentIP` at `0x1802ede0d`
- `WDSCORE!CurrentIP` at `0x1802edfe5`
- `WDSCORE!CurrentIP` at `0x1802ee0d6`
- `WDSCORE!CurrentIP` at `0x1802ee1c7`
- `WDSCORE!CurrentIP` at `0x1802ee2c5`
- `WDSCORE!CurrentIP` at `0x1802ee370`
- `WDSCORE!CurrentIP` at `0x1802ee418`
- `WDSCORE!CurrentIP` at `0x1802ee4d1`

## string_xrefs

- `0x1802edefb`: `SourcePath`
- `0x1802edf5c`: `DestinationPath`
- `0x1802edf1a`: `long __cdecl pSPCopyFile(class UnBCL::String *,class UnBCL::String *,unsigned long (__cdecl *)(union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,unsigned long,unsigned long,void *,void *,void *),void *,void *,int,int)`
- `0x1802edf7b`: `long __cdecl pSPCopyFile(class UnBCL::String *,class UnBCL::String *,unsigned long (__cdecl *)(union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,unsigned long,unsigned long,void *,void *,void *),void *,void *,int,int)`
- `0x1802ee4e4`: `%hs: Failed to write file. Error: 0x%08X`
- `0x1802ee428`: `%hs: Copy operation cancelled by the progress routine.`
- `0x1802ee1f5`: `%hs: Failed to open destination file %s. Error: 0x%08X`
- `0x1802ee2d8`: `%hs: Failed to allocate buffer for copy operation. Error: 0x%08X`
- `0x1802ee013`: `%hs: Failed to open source file %s. Error: 0x%08X`
- `0x1802edde0`: `pSPCopyFile`
- `0x1802ede67`: `pSPCopyFile`
- `0x1802ee037`: `pSPCopyFile`
- `0x1802ee128`: `pSPCopyFile`
- `0x1802ee219`: `pSPCopyFile`
- `0x1802ee2fc`: `pSPCopyFile`
- `0x1802ee3a4`: `pSPCopyFile`
- `0x1802ee44c`: `pSPCopyFile`
- `0x1802ee508`: `pSPCopyFile`
- `0x1802eddb5`: `pSPCopyFile`
- `0x1802ede3c`: `pSPCopyFile`
- `0x1802ee00c`: `pSPCopyFile`
- `0x1802ee0fd`: `pSPCopyFile`
- `0x1802ee1ee`: `pSPCopyFile`
- `0x1802ee2d1`: `pSPCopyFile`
- `0x1802ee379`: `pSPCopyFile`
- `0x1802ee421`: `pSPCopyFile`
- `0x1802ee4dd`: `pSPCopyFile`
- `0x1802ee380`: `%hs: Copy operation cancelled by the cancel parameter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=2
void __fastcall __noreturn pSPCopyFile(
        struct UnBCL::String *a1,
        struct UnBCL::String *a2,
        unsigned int (*a3)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        UnBCL::ArgumentNullException *a4,
        void *a5,
        int a6,
        int a7)
{
  struct UnBCL::String *FullPath; // rax
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v11; // rax
  struct UnBCL::String *v12; // rax
  const struct UnBCL::String *v13; // rax
  struct UnBCL::String *v14; // rax
  UnBCL::String *v15; // rax
  const WCHAR *CString; // rax
  HANDLE FileW; // rax
  void *v18; // rsi
  UnBCL::String *v19; // rax
  const WCHAR *v20; // rax
  HANDLE v21; // r15
  void *v22; // rdi
  __int64 v23; // rbx
  DWORD v24; // ecx
  int v25; // eax
  int v26; // eax
  UnBCL::ArgumentNullException *v27; // rax
  UnBCL::ArgumentNullException *v28; // rbx
  UnBCL::ArgumentNullException *v29; // rax
  UnBCL::ArgumentNullException *v30; // rbx
  signed int v31; // eax
  bool v32; // sf
  signed int v33; // eax
  unsigned int v34; // esi
  DWORD v35; // ebx
  __int64 v36; // rdi
  UnBCL::String *v37; // rax
  const char *v38; // rax
  struct tagLOG_PARTIAL_MSG *v39; // rax
  signed int v40; // eax
  bool v41; // sf
  signed int v42; // eax
  unsigned int v43; // esi
  DWORD v44; // ebx
  __int64 v45; // rdi
  UnBCL::String *v46; // rax
  const char *v47; // rax
  struct tagLOG_PARTIAL_MSG *v48; // rax
  signed int v49; // eax
  bool v50; // sf
  signed int v51; // eax
  unsigned int v52; // esi
  DWORD v53; // ebx
  __int64 v54; // rdi
  UnBCL::String *v55; // rax
  const char *v56; // rax
  struct tagLOG_PARTIAL_MSG *v57; // rax
  signed int v58; // eax
  bool v59; // sf
  signed int v60; // eax
  signed int v61; // esi
  DWORD v62; // edi
  __int64 v63; // rbx
  struct tagLOG_PARTIAL_MSG *v64; // rax
  DWORD v65; // edi
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  DWORD v68; // edi
  __int64 v69; // rbx
  struct tagLOG_PARTIAL_MSG *v70; // rax
  signed int LastError; // eax
  unsigned int v72; // esi
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  _QWORD v76[2]; // [rsp+68h] [rbp-130h] BYREF
  UnBCL::ArgumentNullException *v77; // [rsp+78h] [rbp-120h]
  __int64 v78; // [rsp+80h] [rbp-118h]
  void *v79; // [rsp+88h] [rbp-110h]
  __int64 v80; // [rsp+90h] [rbp-108h]
  __int64 pExceptionObject; // [rsp+98h] [rbp-100h] BYREF
  __int64 v82; // [rsp+A0h] [rbp-F8h] BYREF
  _QWORD *v83; // [rsp+A8h] [rbp-F0h] BYREF
  _QWORD *v84; // [rsp+B0h] [rbp-E8h] BYREF
  _QWORD *v85; // [rsp+B8h] [rbp-E0h] BYREF
  _QWORD *v86; // [rsp+C0h] [rbp-D8h] BYREF
  _QWORD *v87; // [rsp+C8h] [rbp-D0h] BYREF
  _QWORD *v88; // [rsp+D0h] [rbp-C8h] BYREF
  _QWORD *v89; // [rsp+D8h] [rbp-C0h] BYREF
  _QWORD v90[2]; // [rsp+E0h] [rbp-B8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+F0h] [rbp-A8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+F4h] [rbp-A4h] BYREF
  _BYTE v93[16]; // [rsp+F8h] [rbp-A0h] BYREF
  LARGE_INTEGER FileSize; // [rsp+108h] [rbp-90h] BYREF
  _BYTE v95[16]; // [rsp+110h] [rbp-88h] BYREF
  _QWORD v96[7]; // [rsp+120h] [rbp-78h] BYREF

  v90[1] = -2;
  v77 = a4;
  if ( a1 )
  {
    if ( a2 )
    {
      FullPath = UnBCL::Path::GetFullPath(a1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v93, FullPath);
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v93);
      v11 = UnBCL::Path::WithLongPrefix(P, 1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v76, v11);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v93, v76);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v76);
      v12 = UnBCL::Path::GetFullPath(a2);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v95, v12);
      v13 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v95);
      v14 = UnBCL::Path::WithLongPrefix(v13, 1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v76, v14);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v95, v76);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v76);
      FileSize.QuadPart = 0;
      v76[0] = -1;
      v80 = -1;
      v79 = 0;
      UnBCL::Exception::Exception((UnBCL::Exception *)v96);
      v96[0] = &`pSPCopyFile'::`11'::CXXXXXHandledException::`vftable';
      v15 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v93);
      CString = UnBCL::String::get_CString(v15);
      FileW = CreateFileW(CString, 0x80000000, 1u, 0, 3u, a6 != 0 ? 0x2000000 : 0, 0);
      v18 = FileW;
      v76[0] = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        if ( GetFileSizeEx(FileW, &FileSize) )
        {
          v19 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v95);
          v20 = UnBCL::String::get_CString(v19);
          v21 = CreateFileW(v20, 0x40000000u, 0, 0, 1u, a6 != 0 ? 167772160 : 0x8000000, 0);
          v80 = (__int64)v21;
          if ( v21 != (HANDLE)-1LL )
          {
            v22 = operator new[](0x400000u);
            v79 = v22;
            if ( v22 )
            {
              v78 = 0;
              NumberOfBytesRead = 0;
              NumberOfBytesWritten = 0;
              v23 = 0;
              while ( ReadFile(v18, v22, 0x400000u, &NumberOfBytesRead, 0) )
              {
                NumberOfBytesWritten = 0;
                if ( !WriteFile(v21, v22, NumberOfBytesRead, &NumberOfBytesWritten, 0)
                  || (v24 = NumberOfBytesRead, NumberOfBytesWritten != NumberOfBytesRead) )
                {
                  LastError = GetLastError();
                  v72 = LastError;
                  if ( LastError > 0 )
                    v72 = (unsigned __int16)LastError | 0x80070000;
                  v73 = GetLastError();
                  v74 = CurrentIP();
                  v75 = ConstructPartialMsgW(0x4000000u, "%hs: Failed to write file. Error: 0x%08X", "pSPCopyFile", v72);
                  WdsSetupLogMessageW(
                    v75,
                    819200,
                    L"D",
                    0,
                    5356,
                    L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
                    L"pSPCopyFile",
                    v74,
                    v73,
                    0,
                    0);
                  v89 = v96;
                  throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v89;
                }
                v23 += NumberOfBytesRead;
                if ( a3 )
                {
                  v25 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD))a3)(
                          (LARGE_INTEGER)FileSize.QuadPart,
                          v23,
                          (LARGE_INTEGER)FileSize.QuadPart,
                          v23,
                          1,
                          0,
                          v18,
                          v21,
                          v77)
                      - 1;
                  if ( !v25 || (v26 = v25 - 1) == 0 )
                  {
                    v68 = GetLastError();
                    v69 = CurrentIP();
                    v70 = ConstructPartialMsgW(
                            0x4000000u,
                            "%hs: Copy operation cancelled by the progress routine.",
                            "pSPCopyFile");
                    WdsSetupLogMessageW(
                      v70,
                      819200,
                      L"D",
                      0,
                      5378,
                      L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
                      L"pSPCopyFile",
                      v69,
                      v68,
                      0,
                      0);
                    v87 = v96;
                    throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v87;
                  }
                  v24 = NumberOfBytesRead;
                  if ( v26 == 1 )
                    a3 = 0;
                }
                if ( v24 < 0x400000 )
                  break;
                if ( (unsigned int)SPIsEventSet(a5) )
                {
                  v65 = GetLastError();
                  v66 = CurrentIP();
                  v67 = ConstructPartialMsgW(
                          0x4000000u,
                          "%hs: Copy operation cancelled by the cancel parameter.",
                          "pSPCopyFile");
                  WdsSetupLogMessageW(
                    v67,
                    819200,
                    L"D",
                    0,
                    5392,
                    L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
                    L"pSPCopyFile",
                    v66,
                    v65,
                    0,
                    0);
                  v88 = v96;
                  throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v88;
                }
              }
              v90[0] = v96;
              throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)v90;
            }
            v58 = GetLastError();
            v59 = v58 < 0;
            if ( v58 > 0 )
              v59 = 1;
            if ( v59 )
            {
              v60 = GetLastError();
              v61 = v60;
              if ( v60 > 0 )
                v61 = (unsigned __int16)v60 | 0x80070000;
              if ( v61 >= 0 )
                v61 = -2147024888;
            }
            else
            {
              v61 = -2147467259;
            }
            v62 = GetLastError();
            v63 = CurrentIP();
            v64 = ConstructPartialMsgW(
                    0x4000000u,
                    "%hs: Failed to allocate buffer for copy operation. Error: 0x%08X",
                    "pSPCopyFile",
                    v61);
            WdsSetupLogMessageW(
              v64,
              819200,
              L"D",
              0,
              5343,
              L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
              L"pSPCopyFile",
              v63,
              v62,
              0,
              0);
            v86 = v96;
            throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v86;
          }
          v49 = GetLastError();
          v50 = v49 < 0;
          if ( v49 > 0 )
            v50 = 1;
          if ( v50 )
          {
            v51 = GetLastError();
            v52 = v51;
            if ( v51 > 0 )
              v52 = (unsigned __int16)v51 | 0x80070000;
          }
          else
          {
            v52 = -2147467259;
          }
          v53 = GetLastError();
          v54 = CurrentIP();
          v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v95);
          v56 = (const char *)UnBCL::String::get_CString(v55);
          v57 = ConstructPartialMsgW(
                  0x4000000u,
                  "%hs: Failed to open destination file %s. Error: 0x%08X",
                  "pSPCopyFile",
                  v56,
                  v52);
          WdsSetupLogMessageW(
            v57,
            819200,
            L"D",
            0,
            5331,
            L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
            L"pSPCopyFile",
            v54,
            v53,
            0,
            0);
          v85 = v96;
          throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v85;
        }
        v40 = GetLastError();
        v41 = v40 < 0;
        if ( v40 > 0 )
          v41 = 1;
        if ( v41 )
        {
          v42 = GetLastError();
          v43 = v42;
          if ( v42 > 0 )
            v43 = (unsigned __int16)v42 | 0x80070000;
        }
        else
        {
          v43 = -2147467259;
        }
        v44 = GetLastError();
        v45 = CurrentIP();
        v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v93);
        v47 = (const char *)UnBCL::String::get_CString(v46);
        v48 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Failed to get the size for source file %s. Error: 0x%08X",
                "pSPCopyFile",
                v47,
                v43);
        WdsSetupLogMessageW(
          v48,
          819200,
          L"D",
          0,
          5315,
          L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
          L"pSPCopyFile",
          v45,
          v44,
          0,
          0);
        v84 = v96;
        throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v84;
      }
      v31 = GetLastError();
      v32 = v31 < 0;
      if ( v31 > 0 )
        v32 = 1;
      if ( v32 )
      {
        v33 = GetLastError();
        v34 = v33;
        if ( v33 > 0 )
          v34 = (unsigned __int16)v33 | 0x80070000;
      }
      else
      {
        v34 = -2147467259;
      }
      v35 = GetLastError();
      v36 = CurrentIP();
      v37 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v93);
      v38 = (const char *)UnBCL::String::get_CString(v37);
      v39 = ConstructPartialMsgW(
              0x4000000u,
              "%hs: Failed to open source file %s. Error: 0x%08X",
              "pSPCopyFile",
              v38,
              v34);
      WdsSetupLogMessageW(
        v39,
        819200,
        L"D",
        0,
        5308,
        L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
        L"pSPCopyFile",
        v36,
        v35,
        0,
        0);
      v83 = v96;
      throw (`pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException **)&v83;
    }
    v29 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v30 = v29;
    v77 = v29;
    if ( v29 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v29, L"DestinationPath");
      *(_QWORD *)v30 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v30 = 0;
    }
    v82 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v30,
            "long __cdecl pSPCopyFile(class UnBCL::String *,class UnBCL::String *,unsigned long (__cdecl *)(union _LARGE_"
            "INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,unsigned long,unsigned long,void *,vo"
            "id *,void *),void *,void *,int,int)");
    throw (UnBCL::ArgumentNullException **)&v82;
  }
  v27 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
  v28 = v27;
  v77 = v27;
  if ( v27 )
  {
    UnBCL::ArgumentNullException::ArgumentNullException(v27, L"SourcePath");
    *(_QWORD *)v28 = &UnBCL::ArgumentNullException::`local vftable';
  }
  else
  {
    v28 = 0;
  }
  pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                       v28,
                       "long __cdecl pSPCopyFile(class UnBCL::String *,class UnBCL::String *,unsigned long (__cdecl *)(un"
                       "ion _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,unsigned long,u"
                       "nsigned long,void *,void *,void *),void *,void *,int,int)");
  throw (UnBCL::ArgumentNullException **)&pExceptionObject;
}

```

## disassembly

```asm
0x1802ed994  push    rbx
0x1802ed996  push    rsi
0x1802ed997  push    rdi
0x1802ed998  push    r12
0x1802ed99a  push    r13
0x1802ed99c  push    r14
0x1802ed99e  push    r15
0x1802ed9a0  sub     rsp, 160h
0x1802ed9a7  mov     [rsp+198h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1802ed9b3  mov     rax, cs:__security_cookie
0x1802ed9ba  xor     rax, rsp
0x1802ed9bd  mov     [rsp+198h+var_40], rax
0x1802ed9c5  mov     [rsp+198h+var_120], r9
0x1802ed9ca  mov     r12, r8
0x1802ed9cd  mov     rbx, rdx
0x1802ed9d0  mov     r13, [rsp+198h+arg_20]
0x1802ed9d8  xor     r14d, r14d
0x1802ed9db  test    rcx, rcx
0x1802ed9de  jz      loc_1802EDEE4
0x1802ed9e4  mov     edi, [rsp+198h+arg_28]
0x1802ed9eb  test    rbx, rbx
0x1802ed9ee  jz      loc_1802EDF46
0x1802ed9f4  call    cs:__imp_?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1802ed9fa  mov     rdx, rax
0x1802ed9fd  lea     rcx, [rsp+198h+var_A0]
0x1802eda05  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802eda0b  nop
0x1802eda0c  lea     rcx, [rsp+198h+var_A0]
0x1802eda14  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802eda1a  mov     rcx, rax
0x1802eda1d  mov     r15d, 1
0x1802eda23  mov     edx, r15d
0x1802eda26  call    cs:__imp_?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x1802eda2c  mov     rdx, rax
0x1802eda2f  lea     rcx, [rsp+198h+var_130]
0x1802eda34  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802eda3a  nop
0x1802eda3b  lea     rdx, [rsp+198h+var_130]
0x1802eda40  lea     rcx, [rsp+198h+var_A0]
0x1802eda48  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802eda4e  nop
0x1802eda4f  lea     rcx, [rsp+198h+var_130]
0x1802eda54  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802eda5a  mov     rcx, rbx
0x1802eda5d  call    cs:__imp_?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1802eda63  mov     rdx, rax
0x1802eda66  lea     rcx, [rsp+198h+var_88]
0x1802eda6e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802eda74  nop
0x1802eda75  lea     rcx, [rsp+198h+var_88]
0x1802eda7d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802eda83  mov     rcx, rax
0x1802eda86  mov     edx, r15d
0x1802eda89  call    cs:__imp_?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x1802eda8f  mov     rdx, rax
0x1802eda92  lea     rcx, [rsp+198h+var_130]
0x1802eda97  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802eda9d  nop
0x1802eda9e  lea     rdx, [rsp+198h+var_130]
0x1802edaa3  lea     rcx, [rsp+198h+var_88]
0x1802edaab  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802edab1  nop
0x1802edab2  lea     rcx, [rsp+198h+var_130]
0x1802edab7  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802edabd  mov     [rsp+198h+var_138], r14d
0x1802edac2  mov     qword ptr [rsp+198h+FileSize], r14
0x1802edaca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802edace  mov     [rsp+198h+var_130], rax
0x1802edad3  mov     [rsp+198h+var_108], rax
0x1802edadb  mov     [rsp+198h+var_110], r14
0x1802edae3  mov     [rsp+198h+var_134], r14d
0x1802edae8  lea     rcx, [rsp+198h+var_78]
0x1802edaf0  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1802edaf6  lea     rax, ??_7CXXXXXHandledException@?L@??pSPCopyFile@@YAJPEAVString@UnBCL@@0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z22HH@Z@6B@; const `pSPCopyFile(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int,int)'::`11'::CXXXXXHandledException::`vftable'
0x1802edafd  mov     [rsp+198h+var_78], rax
0x1802edb05  mov     eax, edi
0x1802edb07  neg     eax
0x1802edb09  sbb     ebx, ebx
0x1802edb0b  and     ebx, 2000000h
0x1802edb11  lea     rcx, [rsp+198h+var_A0]
0x1802edb19  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802edb1f  mov     rcx, rax
0x1802edb22  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802edb28  mov     [rsp+198h+hTemplateFile], r14; hTemplateFile
0x1802edb2d  mov     [rsp+198h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1802edb31  mov     [rsp+198h+dwCreationDisposition], 3; dwCreationDisposition
0x1802edb39  xor     r9d, r9d; lpSecurityAttributes
0x1802edb3c  mov     r8d, r15d; dwShareMode
0x1802edb3f  mov     edx, 80000000h; dwDesiredAccess
0x1802edb44  mov     rcx, rax; lpFileName
0x1802edb47  call    cs:__imp_CreateFileW
0x1802edb4d  mov     rsi, rax
0x1802edb50  mov     [rsp+198h+var_130], rax
0x1802edb55  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802edb59  jz      loc_1802EDFA7
0x1802edb5f  lea     rdx, [rsp+198h+FileSize]; lpFileSize
0x1802edb67  mov     rcx, rsi; hFile
0x1802edb6a  call    cs:__imp_GetFileSizeEx
0x1802edb70  test    eax, eax
0x1802edb72  jz      loc_1802EE098
0x1802edb78  neg     edi
0x1802edb7a  sbb     ebx, ebx
0x1802edb7c  and     ebx, 2000000h
0x1802edb82  add     ebx, 8000000h
0x1802edb88  lea     rcx, [rsp+198h+var_88]
0x1802edb90  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802edb96  mov     rcx, rax
0x1802edb99  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802edb9f  mov     [rsp+198h+hTemplateFile], r14; hTemplateFile
0x1802edba4  mov     [rsp+198h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1802edba8  mov     [rsp+198h+dwCreationDisposition], r15d; dwCreationDisposition
0x1802edbad  xor     r9d, r9d; lpSecurityAttributes
0x1802edbb0  xor     r8d, r8d; dwShareMode
0x1802edbb3  mov     edx, 40000000h; dwDesiredAccess
0x1802edbb8  mov     rcx, rax; lpFileName
0x1802edbbb  call    cs:__imp_CreateFileW
0x1802edbc1  mov     r15, rax
0x1802edbc4  mov     [rsp+198h+var_108], rax
0x1802edbcc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802edbd0  jz      loc_1802EE189
0x1802edbd6  mov     ecx, 400000h; unsigned __int64
0x1802edbdb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1802edbe0  mov     rdi, rax
0x1802edbe3  mov     [rsp+198h+var_110], rax
0x1802edbeb  test    rax, rax
0x1802edbee  jz      loc_1802EE27D
0x1802edbf4  mov     [rsp+198h+var_118], r14
0x1802edbfc  mov     [rsp+198h+NumberOfBytesRead], r14d
0x1802edc04  mov     [rsp+198h+NumberOfBytesWritten], r14d
0x1802edc0c  mov     rbx, r14
0x1802edc0f  mov     qword ptr [rsp+198h+dwCreationDisposition], r14; lpOverlapped
0x1802edc14  lea     r9, [rsp+198h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1802edc1c  mov     r8d, 400000h; nNumberOfBytesToRead
0x1802edc22  mov     rdx, rdi; lpBuffer
0x1802edc25  mov     rcx, rsi; hFile
0x1802edc28  call    cs:__imp_ReadFile
0x1802edc2e  test    eax, eax
0x1802edc30  jz      loc_1802EE56D
0x1802edc36  mov     [rsp+198h+NumberOfBytesWritten], r14d
0x1802edc3e  mov     qword ptr [rsp+198h+dwCreationDisposition], r14; lpOverlapped
0x1802edc43  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802edc4b  mov     r8d, [rsp+198h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x1802edc53  mov     rdx, rdi; lpBuffer
0x1802edc56  mov     rcx, r15; hFile
0x1802edc59  call    cs:__imp_WriteFile
0x1802edc5f  test    eax, eax
0x1802edc61  jz      loc_1802EE4B0
0x1802edc67  mov     ecx, [rsp+198h+NumberOfBytesRead]
0x1802edc6e  cmp     [rsp+198h+NumberOfBytesWritten], ecx
0x1802edc75  jnz     loc_1802EE4B0
0x1802edc7b  add     rbx, rcx
0x1802edc7e  test    r12, r12
0x1802edc81  jz      short loc_1802EDCDE
0x1802edc83  mov     rax, [rsp+198h+var_120]
0x1802edc88  mov     [rsp+198h+var_158], rax
0x1802edc8d  mov     [rsp+198h+var_160], r15
0x1802edc92  mov     [rsp+198h+hTemplateFile], rsi
0x1802edc97  mov     [rsp+198h+dwFlagsAndAttributes], r14d
0x1802edc9c  mov     [rsp+198h+dwCreationDisposition], 1
0x1802edca4  mov     r9, rbx
0x1802edca7  mov     rcx, qword ptr [rsp+198h+FileSize]
0x1802edcaf  mov     r8, rcx
0x1802edcb2  mov     rdx, rbx
0x1802edcb5  mov     rax, r12
0x1802edcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802edcbd  sub     eax, 1
0x1802edcc0  jz      loc_1802EE408
0x1802edcc6  sub     eax, 1
0x1802edcc9  jz      loc_1802EE408
0x1802edccf  mov     ecx, [rsp+198h+NumberOfBytesRead]
0x1802edcd6  cmp     eax, 1
0x1802edcd9  jnz     short loc_1802EDCDE
0x1802edcdb  mov     r12, r14
0x1802edcde  cmp     ecx, 400000h
0x1802edce4  jb      loc_1802EE56D
0x1802edcea  mov     rcx, r13; void *
0x1802edced  call    ?SPIsEventSet@@YAHPEAX@Z; SPIsEventSet(void *)
0x1802edcf2  test    eax, eax
0x1802edcf4  jnz     loc_1802EE360
0x1802edcfa  jmp     loc_1802EDC0F
0x1802edcff  lea     rcx, [rsp+198h+var_78]
0x1802edd07  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x1802edd0d  xor     r14d, r14d
0x1802edd10  cmp     [rsp+198h+var_138], r14d
0x1802edd15  jl      loc_1802EDEA0
0x1802edd1b  cmp     [rsp+198h+arg_30], r14d
0x1802edd23  jz      loc_1802EDEA0
0x1802edd29  lea     rcx, [rsp+198h+var_A0]
0x1802edd31  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802edd37  mov     rcx, rax
0x1802edd3a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802edd40  mov     rcx, rax; lpFileName
0x1802edd43  call    cs:__imp_GetFileAttributesW
0x1802edd49  mov     ebx, eax
0x1802edd4b  cmp     eax, 0FFFFFFFFh
0x1802edd4e  jz      loc_1802EDE05
0x1802edd54  lea     rcx, [rsp+198h+var_88]
0x1802edd5c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802edd62  mov     rcx, rax
0x1802edd65  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802edd6b  mov     rcx, rax; lpFileName
0x1802edd6e  mov     edx, ebx; dwFileAttributes
0x1802edd70  call    cs:__imp_SetFileAttributesW
0x1802edd76  test    eax, eax
0x1802edd78  jnz     loc_1802EDEA0
0x1802edd7e  call    cs:__imp_GetLastError
0x1802edd84  mov     esi, eax
0x1802edd86  call    cs:__imp_CurrentIP
0x1802edd8c  mov     rdi, rax
0x1802edd8f  call    cs:__imp_GetLastError
0x1802edd95  mov     ebx, eax
0x1802edd97  lea     rcx, [rsp+198h+var_88]
0x1802edd9f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802edda5  mov     rcx, rax
0x1802edda8  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802eddae  mov     [rsp+198h+dwCreationDisposition], ebx
0x1802eddb2  mov     r9, rax
0x1802eddb5  lea     r8, aPspcopyfile_0; "pSPCopyFile"
0x1802eddbc  lea     rdx, aHsFailedToSetA; "%hs: Failed to set attributes for %s. E"...
0x1802eddc3  mov     ecx, 4000000h; unsigned int
0x1802eddc8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802eddcd  mov     [rsp+198h+var_148], r14d
0x1802eddd2  mov     [rsp+198h+var_150], r14
0x1802eddd7  mov     dword ptr [rsp+198h+var_158], esi
0x1802edddb  mov     [rsp+198h+var_160], rdi
0x1802edde0  lea     rcx, aPspcopyfile; "pSPCopyFile"
0x1802edde7  mov     [rsp+198h+hTemplateFile], rcx
0x1802eddec  lea     rcx, aBaseNtsetupSet_29; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1802eddf3  mov     qword ptr [rsp+198h+dwFlagsAndAttributes], rcx
0x1802eddf8  mov     [rsp+198h+dwCreationDisposition], 1531h
0x1802ede00  jmp     loc_1802EDE87
0x1802ede05  call    cs:__imp_GetLastError
0x1802ede0b  mov     esi, eax
0x1802ede0d  call    cs:__imp_CurrentIP
0x1802ede13  mov     rdi, rax
0x1802ede16  call    cs:__imp_GetLastError
0x1802ede1c  mov     ebx, eax
0x1802ede1e  lea     rcx, [rsp+198h+var_A0]
0x1802ede26  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802ede2c  mov     rcx, rax
0x1802ede2f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802ede35  mov     [rsp+198h+dwCreationDisposition], ebx
0x1802ede39  mov     r9, rax
0x1802ede3c  lea     r8, aPspcopyfile_0; "pSPCopyFile"
0x1802ede43  lea     rdx, aHsFailedToGetA_0; "%hs: Failed to get attributes for %s. E"...
0x1802ede4a  mov     ecx, 4000000h; unsigned int
0x1802ede4f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802ede54  mov     [rsp+198h+var_148], r14d
0x1802ede59  mov     [rsp+198h+var_150], r14
0x1802ede5e  mov     dword ptr [rsp+198h+var_158], esi
0x1802ede62  mov     [rsp+198h+var_160], rdi
0x1802ede67  lea     rcx, aPspcopyfile; "pSPCopyFile"
0x1802ede6e  mov     [rsp+198h+hTemplateFile], rcx
0x1802ede73  lea     rcx, aBaseNtsetupSet_29; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1802ede7a  mov     qword ptr [rsp+198h+dwFlagsAndAttributes], rcx
0x1802ede7f  mov     [rsp+198h+dwCreationDisposition], 1536h
0x1802ede87  xor     r9d, r9d
0x1802ede8a  lea     r8, aD_0; "D"
0x1802ede91  mov     edx, 0C8000h
0x1802ede96  mov     rcx, rax
0x1802ede99  call    cs:__imp_WdsSetupLogMessageW
0x1802ede9f  nop
0x1802edea0  lea     rcx, [rsp+198h+var_88]
0x1802edea8  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802edeae  nop
0x1802edeaf  lea     rcx, [rsp+198h+var_A0]
0x1802edeb7  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802edebd  mov     eax, [rsp+198h+var_138]
0x1802edec1  mov     rcx, [rsp+198h+var_40]
0x1802edec9  xor     rcx, rsp; StackCookie
0x1802edecc  call    __security_check_cookie
0x1802eded1  add     rsp, 160h
0x1802eded8  pop     r15
0x1802ededa  pop     r14
0x1802ededc  pop     r13
0x1802edede  pop     r12
0x1802edee0  pop     rdi
0x1802edee1  pop     rsi
0x1802edee2  pop     rbx
0x1802edee3  retn
0x1802edee4  lea     ecx, [r14+38h]
0x1802edee8  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802edeee  mov     rbx, rax
0x1802edef1  mov     [rsp+198h+var_120], rax
0x1802edef6  test    rax, rax
0x1802edef9  jz      short loc_1802EDF17
0x1802edefb  lea     rdx, aSourcepath; "SourcePath"
0x1802edf02  mov     rcx, rax
0x1802edf05  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x1802edf0b  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x1802edf12  mov     [rbx], rax
0x1802edf15  jmp     short loc_1802EDF1A
0x1802edf17  mov     rbx, r14
0x1802edf1a  lea     rdx, aLongCdeclPspco_0; "long __cdecl pSPCopyFile(class UnBCL::S"...
0x1802edf21  mov     rcx, rbx
0x1802edf24  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1802edf29  mov     [rsp+198h+pExceptionObject], rax
0x1802edf31  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x1802edf38  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x1802edf40  call    _CxxThrowException_0
  ... truncated ...
```
