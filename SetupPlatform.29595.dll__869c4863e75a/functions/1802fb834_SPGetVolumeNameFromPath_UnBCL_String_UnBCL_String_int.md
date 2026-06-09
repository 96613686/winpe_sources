# SPGetVolumeNameFromPath(UnBCL::String *,UnBCL::String * *,int *)

- ea: `0x1802fb834`
- end: `0x1802fbda5`
- name: `?SPGetVolumeNameFromPath@@YAPEAVString@UnBCL@@PEAV12@PEAPEAV12@PEAH@Z`
- size: `1393`
- prototype: `struct UnBCL::String *__fastcall(struct UnBCL::String *, struct UnBCL::String **, int *)`
- caller_count: `26`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180121620`
- `0x180138890`
- `0x18013db30`
- `0x180140640`
- `0x180187a20`
- `0x1801da230`
- `0x1801dab80`
- `0x1802078b4`
- `0x180238f90`
- `0x1802a3700`
- `0x1802aa1e0`
- `0x1802c6538`
- `0x1802c6944`
- `0x1802d1f8c`
- `0x1802d6fd8`
- `0x1802dd720`
- `0x1802ec5a8`
- `0x1802f3cc0`
- `0x1802f4fd0`
- `0x1802f5640`
- `0x1802f8478`
- `0x1802f9024`
- `0x1802fb5dc`
- `0x1802fbdac`
- `0x1802fc148`
- `0x1803aa0e0`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x1802fb834`
- `0x1802fdc0c`
- `0x1804bbfa0`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x1802fb924`
- `KERNEL32!GetVolumePathNameW` at `0x1802fbaa1`
- `KERNEL32!GetVolumePathNameW` at `0x1802fbada`
- `KERNEL32!GetVolumePathNameW` at `0x1802fb924`
- `KERNEL32!GetVolumePathNameW` at `0x1802fbaa1`
- `KERNEL32!GetVolumePathNameW` at `0x1802fbada`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1802fbaf6`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1802fbaf6`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802fb9b2`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802fb9b2`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802fb95f`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802fb95f`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802fb9e0`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x1802fb9e0`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802fb8d9`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802fb8d9`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802fbd6b`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802fbd6b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x1802fba2c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x1802fba2c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802fba0a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802fba0a`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802fbc91`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802fbc91`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x1802fbc54`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x1802fbc54`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb956`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb995`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9a9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9cc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9fe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fbb0e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fbbf0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fbc2c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb956`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb995`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9a9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9cc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fb9fe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fbb0e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fbbf0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802fbc2c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb892`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb89d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb8a9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb8f9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb892`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb89d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb8a9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802fb8f9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802fbb49`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802fbb79`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802fbb49`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802fbb79`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fb8b9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fbb1c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fbb5c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fbd4e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fb8b9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fbb1c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fbb5c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802fbd4e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fb93c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fb94b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fb97e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fba41`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fbbc9`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fbc16`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fbc73`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fb93c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fb94b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fb97e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fba41`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fbbc9`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fbc16`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802fbc73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fb905`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fba88`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbac1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbb34`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbb9a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbc3b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fb905`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fba88`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbac1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbb34`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbb9a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802fbc3b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fb90e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fba91`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fbaca`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fbb3d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fbc44`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fb90e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fba91`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fbaca`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fbb3d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802fbc44`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fb98a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fba59`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fba71`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fba7d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbab6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbbd5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbc22`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbc7f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbc9f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcaa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcb6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcc2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbccd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcd9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbce8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcf4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbd00`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbd0b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbd17`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fb98a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fba59`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fba71`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fba7d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbab6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbbd5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbc22`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbc7f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbc9f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcaa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcb6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcc2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbccd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcd9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbce8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbcf4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbd00`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbd0b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802fbd17`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fb8ee`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fb96d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fb9c0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fba17`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbb8e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbbb8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbc06`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbc62`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fb8ee`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fb96d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fb9c0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fba17`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbb8e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbbb8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbc06`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802fbc62`
- `unbcl!?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z` at `0x1802fbbaa`
- `unbcl!?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z` at `0x1802fbbaa`

## string_xrefs

- `0x1802fbd7f`: `class UnBCL::String *__cdecl SPGetVolumeNameFromPath(class UnBCL::String *,class UnBCL::String **,int *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
struct UnBCL::String *__fastcall SPGetVolumeNameFromPath(struct UnBCL::String *a1, struct UnBCL::String **a2, int *a3)
{
  int v6; // edi
  UnBCL::String *v7; // rax
  UnBCL::String *v8; // rbx
  UnBCL::String *v9; // rax
  const WCHAR *CString; // rax
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *ParentPath; // rax
  const struct UnBCL::String *v13; // rax
  struct UnBCL::String *FileName; // rax
  const struct UnBCL::String *v15; // rbx
  const struct UnBCL::String *v16; // rax
  struct UnBCL::String *v17; // rax
  __int64 v18; // rax
  UnBCL::String *v19; // rax
  const WCHAR *v20; // rax
  UnBCL::String *v21; // rax
  const WCHAR *v22; // rax
  UnBCL::String *v23; // rbx
  UnBCL::String *v24; // rax
  const unsigned __int16 *v25; // rax
  UnBCL::String *v26; // rax
  UnBCL::String *v27; // rbx
  UnBCL::String *v28; // rax
  struct UnBCL::String *v29; // rax
  __int64 v30; // rax
  __int64 VolumeStableGuidStringFromVolumeName; // rax
  UnBCL::String *v32; // rax
  const unsigned __int16 *v33; // rax
  struct UnBCL::String *v34; // rax
  __int64 v35; // rbx
  UnBCL::ArgumentNullException *v37; // rax
  UnBCL::ArgumentNullException *v38; // rbx
  __int64 pExceptionObject; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v40; // [rsp+30h] [rbp-D8h] BYREF
  UnBCL::ArgumentNullException *v41; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v45[16]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v46[16]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v47[16]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-58h]
  _BYTE v49[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v50[16]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2E8h] [rbp+1E0h] BYREF

  v48 = -2;
  v6 = 0;
  LODWORD(pExceptionObject) = 0;
  if ( !a1 )
  {
    v37 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v38 = v37;
    v41 = v37;
    if ( v37 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v37, L"Path");
      *(_QWORD *)v38 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v38 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v38,
                         "class UnBCL::String *__cdecl SPGetVolumeNameFromPath(class UnBCL::String *,class UnBCL::String **,int *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( a2 )
    *a2 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v45);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v46);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43);
  v7 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v8 = v7;
  v41 = v7;
  if ( v7 )
  {
    UnBCL::String::String(v7, a1);
    *(_QWORD *)v8 = &UnBCL::String::`local vftable';
  }
  else
  {
    v8 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v42, v8);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v47);
  v9 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v42);
  CString = UnBCL::String::get_CString(v9);
  if ( !GetVolumePathNameW(CString, szVolumePathName, 0x104u) )
    goto LABEL_35;
  do
  {
    UnBCL::SmartPtr<UnBCL::String>::operator=(v45, &v42);
    UnBCL::SmartPtr<UnBCL::String>::operator=(&v43, v47);
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v45);
    ParentPath = UnBCL::Path::GetParentPath(P);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v40, ParentPath);
    UnBCL::SmartPtr<UnBCL::String>::operator=(&v42, &v40);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v40);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v42) )
      break;
    v13 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v45);
    FileName = UnBCL::Path::GetFileName(v13);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v41, FileName);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v41) )
    {
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v41);
      break;
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(&v43) )
    {
      v15 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v43);
      v16 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v41);
      v17 = UnBCL::Path::Combine(v16, v15);
      v18 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v50, v17);
      v6 |= 1u;
    }
    else
    {
      v18 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v49, &v41);
      v6 |= 2u;
    }
    LODWORD(pExceptionObject) = v6;
    UnBCL::SmartPtr<UnBCL::String>::operator=(v47, v18);
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      LODWORD(pExceptionObject) = v6;
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v49);
    }
    if ( (v6 & 1) != 0 )
    {
      v6 &= ~1u;
      LODWORD(pExceptionObject) = v6;
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v50);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v41);
    v19 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v42);
    v20 = UnBCL::String::get_CString(v19);
  }
  while ( GetVolumePathNameW(v20, szVolumePathName, 0x104u) );
  v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v45);
  v22 = UnBCL::String::get_CString(v21);
  if ( GetVolumePathNameW(v22, szVolumePathName, 0x104u)
    && GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    if ( a2 && UnBCL::SmartPtr<UnBCL::String>::get_P(&v43) )
    {
      v23 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v41 = v23;
      if ( v23 )
      {
        v24 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v43);
        v25 = UnBCL::String::get_CString(v24);
        UnBCL::String::String(v23, v25);
        *(_QWORD *)v23 = &UnBCL::String::`local vftable';
      }
      else
      {
        v23 = 0;
      }
      *a2 = v23;
    }
    v26 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v27 = v26;
    v41 = v26;
    if ( v26 )
    {
      UnBCL::String::String(v26, szVolumeName);
      *(_QWORD *)v27 = &UnBCL::String::`local vftable';
    }
    else
    {
      v27 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v44, v27);
    v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v44);
    v29 = UnBCL::String::TrimEnd(v28, L"\\");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v40, v29);
    UnBCL::SmartPtr<UnBCL::String>::operator=(&v44, &v40);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v40);
    if ( a3 )
    {
      *a3 = 0;
      v30 = UnBCL::SmartPtr<UnBCL::String>::get_P(&v44);
      VolumeStableGuidStringFromVolumeName = pGetVolumeStableGuidStringFromVolumeName(v30);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v40, VolumeStableGuidStringFromVolumeName);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v46, &v40);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v40);
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v46) )
      {
        v32 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v46);
        v33 = UnBCL::String::get_CString(v32);
        v34 = UnBCL::String::Concat(L"\\\\?\\Volume", v33);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v40, v34);
        UnBCL::SmartPtr<UnBCL::String>::operator=(&v44, &v40);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v40);
        *a3 = 1;
      }
    }
    v35 = UnBCL::SmartPtr<UnBCL::String>::Steal(&v44);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v44);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v47);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v42);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v43);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v46);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v45);
    return (struct UnBCL::String *)v35;
  }
  else
  {
LABEL_35:
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v47);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v42);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v43);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v46);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v45);
    return 0;
  }
}

```

## disassembly

```asm
0x1802fb834  mov     rax, rsp
0x1802fb837  push    rbp
0x1802fb838  push    rsi
0x1802fb839  push    rdi
0x1802fb83a  push    r12
0x1802fb83c  push    r13
0x1802fb83e  push    r14
0x1802fb840  push    r15
0x1802fb842  lea     rbp, [rax-438h]
0x1802fb849  sub     rsp, 500h
0x1802fb850  mov     [rbp+430h+var_488], 0FFFFFFFFFFFFFFFEh
0x1802fb858  mov     [rax+20h], rbx
0x1802fb85c  mov     rax, cs:__security_cookie
0x1802fb863  xor     rax, rsp
0x1802fb866  mov     [rbp+430h+var_40], rax
0x1802fb86d  mov     r15, r8
0x1802fb870  mov     rsi, rdx
0x1802fb873  mov     r14, rcx
0x1802fb876  xor     edi, edi
0x1802fb878  mov     dword ptr [rsp+530h+pExceptionObject], edi
0x1802fb87c  test    rcx, rcx
0x1802fb87f  jz      loc_1802FBD49
0x1802fb885  test    rdx, rdx
0x1802fb888  jz      short loc_1802FB88D
0x1802fb88a  mov     [rdx], rdi
0x1802fb88d  lea     rcx, [rsp+78h]
0x1802fb892  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802fb898  nop
0x1802fb899  lea     rcx, [rbp+430h+var_4A8]
0x1802fb89d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802fb8a3  nop
0x1802fb8a4  lea     rcx, [rsp+58h]
0x1802fb8a9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802fb8af  nop
0x1802fb8b0  mov     r12d, 18h
0x1802fb8b6  mov     ecx, r12d
0x1802fb8b9  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802fb8bf  mov     rbx, rax
0x1802fb8c2  mov     [rsp+530h+var_4F8], rax
0x1802fb8c7  lea     r13, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x1802fb8ce  test    rax, rax
0x1802fb8d1  jz      short loc_1802FB8E4
0x1802fb8d3  mov     rdx, r14
0x1802fb8d6  mov     rcx, rax
0x1802fb8d9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x1802fb8df  mov     [rbx], r13
0x1802fb8e2  jmp     short loc_1802FB8E6
0x1802fb8e4  xor     ebx, ebx
0x1802fb8e6  mov     rdx, rbx
0x1802fb8e9  lea     rcx, [rsp+48h]
0x1802fb8ee  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fb8f4  nop
0x1802fb8f5  lea     rcx, [rbp+430h+var_498]
0x1802fb8f9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802fb8ff  nop
0x1802fb900  lea     rcx, [rsp+48h]
0x1802fb905  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802fb90b  mov     rcx, rax
0x1802fb90e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802fb914  mov     rcx, rax; lpszFileName
0x1802fb917  mov     r14d, 104h
0x1802fb91d  mov     r8d, r14d; cchBufferLength
0x1802fb920  lea     rdx, [rbp+430h+szVolumePathName]; lpszVolumePathName
0x1802fb924  call    cs:__imp_GetVolumePathNameW
0x1802fb92a  test    eax, eax
0x1802fb92c  jz      loc_1802FBCE4
0x1802fb932  lea     rdx, [rsp+48h]
0x1802fb937  lea     rcx, [rsp+78h]
0x1802fb93c  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fb942  lea     rdx, [rbp+430h+var_498]
0x1802fb946  lea     rcx, [rsp+58h]
0x1802fb94b  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fb951  lea     rcx, [rsp+78h]
0x1802fb956  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fb95c  mov     rcx, rax
0x1802fb95f  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x1802fb965  mov     rdx, rax
0x1802fb968  lea     rcx, [rsp+28h]
0x1802fb96d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fb973  nop
0x1802fb974  lea     rdx, [rsp+28h]
0x1802fb979  lea     rcx, [rsp+48h]
0x1802fb97e  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fb984  nop
0x1802fb985  lea     rcx, [rsp+28h]
0x1802fb98a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fb990  lea     rcx, [rsp+48h]
0x1802fb995  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fb99b  test    rax, rax
0x1802fb99e  jz      loc_1802FBABC
0x1802fb9a4  lea     rcx, [rsp+78h]
0x1802fb9a9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fb9af  mov     rcx, rax
0x1802fb9b2  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x1802fb9b8  mov     rdx, rax
0x1802fb9bb  lea     rcx, [rsp+530h+var_4F8]
0x1802fb9c0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fb9c6  nop
0x1802fb9c7  lea     rcx, [rsp+530h+var_4F8]
0x1802fb9cc  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fb9d2  test    rax, rax
0x1802fb9d5  jz      loc_1802FBAB1
0x1802fb9db  lea     rcx, [rsp+58h]
0x1802fb9e0  call    cs:__imp_??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ; UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(void)
0x1802fb9e6  test    rax, rax
0x1802fb9e9  jz      short loc_1802FBA23
0x1802fb9eb  lea     rcx, [rsp+58h]
0x1802fb9f0  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fb9f6  mov     rbx, rax
0x1802fb9f9  lea     rcx, [rsp+530h+var_4F8]
0x1802fb9fe  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fba04  mov     rdx, rbx
0x1802fba07  mov     rcx, rax
0x1802fba0a  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802fba10  mov     rdx, rax
0x1802fba13  lea     rcx, [rbp+430h+var_470]
0x1802fba17  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fba1d  nop
0x1802fba1e  or      edi, 1
0x1802fba21  jmp     short loc_1802FBA36
0x1802fba23  lea     rdx, [rsp+530h+var_4F8]
0x1802fba28  lea     rcx, [rbp+430h+var_480]
0x1802fba2c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fba32  nop
0x1802fba33  or      edi, 2
0x1802fba36  mov     dword ptr [rsp+530h+pExceptionObject], edi
0x1802fba3a  mov     rdx, rax
0x1802fba3d  lea     rcx, [rbp+430h+var_498]
0x1802fba41  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fba47  nop
0x1802fba48  test    dil, 2
0x1802fba4c  jz      short loc_1802FBA60
0x1802fba4e  and     edi, 0FFFFFFFDh
0x1802fba51  mov     dword ptr [rsp+530h+pExceptionObject], edi
0x1802fba55  lea     rcx, [rbp+430h+var_480]
0x1802fba59  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fba5f  nop
0x1802fba60  test    dil, 1
0x1802fba64  jz      short loc_1802FBA78
0x1802fba66  and     edi, 0FFFFFFFEh
0x1802fba69  mov     dword ptr [rsp+530h+pExceptionObject], edi
0x1802fba6d  lea     rcx, [rbp+430h+var_470]
0x1802fba71  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fba77  nop
0x1802fba78  lea     rcx, [rsp+530h+var_4F8]
0x1802fba7d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fba83  lea     rcx, [rsp+48h]
0x1802fba88  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802fba8e  mov     rcx, rax
0x1802fba91  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802fba97  mov     rcx, rax; lpszFileName
0x1802fba9a  mov     r8d, r14d; cchBufferLength
0x1802fba9d  lea     rdx, [rbp+430h+szVolumePathName]; lpszVolumePathName
0x1802fbaa1  call    cs:__imp_GetVolumePathNameW
0x1802fbaa7  test    eax, eax
0x1802fbaa9  jnz     loc_1802FB932
0x1802fbaaf  jmp     short loc_1802FBABC
0x1802fbab1  lea     rcx, [rsp+530h+var_4F8]
0x1802fbab6  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbabc  lea     rcx, [rsp+78h]
0x1802fbac1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802fbac7  mov     rcx, rax
0x1802fbaca  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802fbad0  mov     rcx, rax; lpszFileName
0x1802fbad3  mov     r8d, r14d; cchBufferLength
0x1802fbad6  lea     rdx, [rbp+430h+szVolumePathName]; lpszVolumePathName
0x1802fbada  call    cs:__imp_GetVolumePathNameW
0x1802fbae0  test    eax, eax
0x1802fbae2  jz      loc_1802FBCE4
0x1802fbae8  mov     r8d, r14d; cchBufferLength
0x1802fbaeb  lea     rdx, [rbp+430h+szVolumeName]; lpszVolumeName
0x1802fbaf2  lea     rcx, [rbp+430h+szVolumePathName]; lpszVolumeMountPoint
0x1802fbaf6  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1802fbafc  test    eax, eax
0x1802fbafe  jz      loc_1802FBCE4
0x1802fbb04  test    rsi, rsi
0x1802fbb07  jz      short loc_1802FBB59
0x1802fbb09  lea     rcx, [rsp+58h]
0x1802fbb0e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fbb14  test    rax, rax
0x1802fbb17  jz      short loc_1802FBB59
0x1802fbb19  mov     rcx, r12
0x1802fbb1c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802fbb22  mov     rbx, rax
0x1802fbb25  mov     [rsp+530h+var_4F8], rax
0x1802fbb2a  test    rax, rax
0x1802fbb2d  jz      short loc_1802FBB54
0x1802fbb2f  lea     rcx, [rsp+58h]
0x1802fbb34  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802fbb3a  mov     rcx, rax
0x1802fbb3d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802fbb43  mov     rdx, rax
0x1802fbb46  mov     rcx, rbx
0x1802fbb49  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802fbb4f  mov     [rbx], r13
0x1802fbb52  jmp     short loc_1802FBB56
0x1802fbb54  xor     ebx, ebx
0x1802fbb56  mov     [rsi], rbx
0x1802fbb59  mov     rcx, r12
0x1802fbb5c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802fbb62  mov     rbx, rax
0x1802fbb65  mov     [rsp+530h+var_4F8], rax
0x1802fbb6a  test    rax, rax
0x1802fbb6d  jz      short loc_1802FBB84
0x1802fbb6f  lea     rdx, [rbp+430h+szVolumeName]
0x1802fbb76  mov     rcx, rax
0x1802fbb79  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802fbb7f  mov     [rbx], r13
0x1802fbb82  jmp     short loc_1802FBB86
0x1802fbb84  xor     ebx, ebx
0x1802fbb86  mov     rdx, rbx
0x1802fbb89  lea     rcx, [rsp+68h]
0x1802fbb8e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fbb94  nop
0x1802fbb95  lea     rcx, [rsp+68h]
0x1802fbb9a  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802fbba0  lea     rdx, pszSrc; "\\"
0x1802fbba7  mov     rcx, rax
0x1802fbbaa  call    cs:__imp_?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z; UnBCL::String::TrimEnd(ushort const *)
0x1802fbbb0  mov     rdx, rax
0x1802fbbb3  lea     rcx, [rsp+28h]
0x1802fbbb8  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fbbbe  nop
0x1802fbbbf  lea     rdx, [rsp+28h]
0x1802fbbc4  lea     rcx, [rsp+68h]
0x1802fbbc9  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fbbcf  nop
0x1802fbbd0  lea     rcx, [rsp+28h]
0x1802fbbd5  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbbdb  test    r15, r15
0x1802fbbde  jz      loc_1802FBC8C
0x1802fbbe4  mov     dword ptr [r15], 0
0x1802fbbeb  lea     rcx, [rsp+68h]
0x1802fbbf0  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fbbf6  mov     rcx, rax
0x1802fbbf9  call    pGetVolumeStableGuidStringFromVolumeName
0x1802fbbfe  mov     rdx, rax
0x1802fbc01  lea     rcx, [rsp+28h]
0x1802fbc06  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fbc0c  nop
0x1802fbc0d  lea     rdx, [rsp+28h]
0x1802fbc12  lea     rcx, [rbp+430h+var_4A8]
0x1802fbc16  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fbc1c  nop
0x1802fbc1d  lea     rcx, [rsp+28h]
0x1802fbc22  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbc28  lea     rcx, [rbp+430h+var_4A8]
0x1802fbc2c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802fbc32  test    rax, rax
0x1802fbc35  jz      short loc_1802FBC8C
0x1802fbc37  lea     rcx, [rbp+430h+var_4A8]
0x1802fbc3b  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802fbc41  mov     rcx, rax
0x1802fbc44  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802fbc4a  mov     rdx, rax
0x1802fbc4d  lea     rcx, aVolume_0; "\\\\?\\Volume"
0x1802fbc54  call    cs:__imp_?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x1802fbc5a  mov     rdx, rax
0x1802fbc5d  lea     rcx, [rsp+28h]
0x1802fbc62  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802fbc68  nop
0x1802fbc69  lea     rdx, [rsp+28h]
0x1802fbc6e  lea     rcx, [rsp+68h]
0x1802fbc73  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802fbc79  nop
0x1802fbc7a  lea     rcx, [rsp+28h]
0x1802fbc7f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbc85  mov     dword ptr [r15], 1
0x1802fbc8c  lea     rcx, [rsp+68h]
0x1802fbc91  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x1802fbc97  mov     rbx, rax
0x1802fbc9a  lea     rcx, [rsp+68h]
0x1802fbc9f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbca5  nop
0x1802fbca6  lea     rcx, [rbp+430h+var_498]
0x1802fbcaa  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcb0  nop
0x1802fbcb1  lea     rcx, [rsp+48h]
0x1802fbcb6  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcbc  nop
0x1802fbcbd  lea     rcx, [rsp+58h]
0x1802fbcc2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcc8  nop
0x1802fbcc9  lea     rcx, [rbp+430h+var_4A8]
0x1802fbccd  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcd3  nop
0x1802fbcd4  lea     rcx, [rsp+78h]
0x1802fbcd9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcdf  mov     rax, rbx
0x1802fbce2  jmp     short loc_1802FBD1F
0x1802fbce4  lea     rcx, [rbp+430h+var_498]
0x1802fbce8  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcee  nop
0x1802fbcef  lea     rcx, [rsp+48h]
0x1802fbcf4  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbcfa  nop
0x1802fbcfb  lea     rcx, [rsp+58h]
0x1802fbd00  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802fbd06  nop
0x1802fbd07  lea     rcx, [rbp+430h+var_4A8]
  ... truncated ...
```
