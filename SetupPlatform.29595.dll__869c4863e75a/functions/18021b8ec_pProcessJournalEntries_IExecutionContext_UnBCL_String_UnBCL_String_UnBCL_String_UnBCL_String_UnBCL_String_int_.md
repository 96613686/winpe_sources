# pProcessJournalEntries(IExecutionContext *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::String *,int,int *)

- ea: `0x18021b8ec`
- end: `0x18021de19`
- name: `?pProcessJournalEntries@@YAJPEAUIExecutionContext@@PEAVString@UnBCL@@1111HPEAH@Z`
- size: `9517`
- prototype: `__int64 __fastcall(struct IExecutionContext *, struct UnBCL::String *, struct UnBCL::String *, struct UnBCL::String *, struct UnBCL::String *, struct UnBCL::String *, int, int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1801efeb0`
- `0x18020f27c`

## callees

- `0x180057dec`
- `0x18005dd24`
- `0x1800c2e14`
- `0x18010f584`
- `0x18012a5c0`
- `0x18012b0fc`
- `0x18012b158`
- `0x1801556c4`
- `0x180156428`
- `0x180156484`
- `0x1801564dc`
- `0x18021b8ec`
- `0x1802e2e20`
- `0x18032c348`
- `0x180405298`
- `0x18040af48`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `msvcrt!towlower` at `0x18021c99f`
- `msvcrt!towlower` at `0x18021c9ab`
- `msvcrt!towlower` at `0x18021ccdc`
- `msvcrt!towlower` at `0x18021cce8`
- `msvcrt!towlower` at `0x18021d004`
- `msvcrt!towlower` at `0x18021c99f`
- `msvcrt!towlower` at `0x18021c9ab`
- `msvcrt!towlower` at `0x18021ccdc`
- `msvcrt!towlower` at `0x18021cce8`
- `msvcrt!towlower` at `0x18021d004`
- `msvcrt!iswalpha` at `0x18021c6e2`
- `msvcrt!iswalpha` at `0x18021c790`
- `msvcrt!iswalpha` at `0x18021c6e2`
- `msvcrt!iswalpha` at `0x18021c790`
- `KERNEL32!GetLastError` at `0x18021ba1d`
- `KERNEL32!GetLastError` at `0x18021baf0`
- `KERNEL32!GetLastError` at `0x18021c1f3`
- `KERNEL32!GetLastError` at `0x18021c2bc`
- `KERNEL32!GetLastError` at `0x18021c427`
- `KERNEL32!GetLastError` at `0x18021c49d`
- `KERNEL32!GetLastError` at `0x18021c510`
- `KERNEL32!GetLastError` at `0x18021c8db`
- `KERNEL32!GetLastError` at `0x18021d132`
- `KERNEL32!GetLastError` at `0x18021d1f0`
- `KERNEL32!GetLastError` at `0x18021d201`
- `KERNEL32!GetLastError` at `0x18021d266`
- `KERNEL32!GetLastError` at `0x18021d277`
- `KERNEL32!GetLastError` at `0x18021d2cc`
- `KERNEL32!GetLastError` at `0x18021d36f`
- `KERNEL32!GetLastError` at `0x18021d380`
- `KERNEL32!GetLastError` at `0x18021d6c3`
- `KERNEL32!GetLastError` at `0x18021da8d`
- `KERNEL32!GetLastError` at `0x18021dba6`
- `KERNEL32!GetLastError` at `0x18021dd58`
- `KERNEL32!GetLastError` at `0x18021ba1d`
- `KERNEL32!GetLastError` at `0x18021baf0`
- `KERNEL32!GetLastError` at `0x18021c1f3`
- `KERNEL32!GetLastError` at `0x18021c2bc`
- `KERNEL32!GetLastError` at `0x18021c427`
- `KERNEL32!GetLastError` at `0x18021c49d`
- `KERNEL32!GetLastError` at `0x18021c510`
- `KERNEL32!GetLastError` at `0x18021c8db`
- `KERNEL32!GetLastError` at `0x18021d132`
- `KERNEL32!GetLastError` at `0x18021d1f0`
- `KERNEL32!GetLastError` at `0x18021d201`
- `KERNEL32!GetLastError` at `0x18021d266`
- `KERNEL32!GetLastError` at `0x18021d277`
- `KERNEL32!GetLastError` at `0x18021d2cc`
- `KERNEL32!GetLastError` at `0x18021d36f`
- `KERNEL32!GetLastError` at `0x18021d380`
- `KERNEL32!GetLastError` at `0x18021d6c3`
- `KERNEL32!GetLastError` at `0x18021da8d`
- `KERNEL32!GetLastError` at `0x18021dba6`
- `KERNEL32!GetLastError` at `0x18021dd58`
- `KERNEL32!GetFileAttributesW` at `0x18021d118`
- `KERNEL32!GetFileAttributesW` at `0x18021d118`
- `KERNEL32!RemoveDirectoryW` at `0x18021d1e2`
- `KERNEL32!RemoveDirectoryW` at `0x18021d1e2`
- `unbcl!?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ` at `0x18021daa6`
- `unbcl!?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ` at `0x18021db18`
- `unbcl!?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ` at `0x18021daa6`
- `unbcl!?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ` at `0x18021db18`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d96f`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d984`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d9ac`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d9f3`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021da3c`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021da80`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d96f`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d984`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d9ac`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021d9f3`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021da3c`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18021da80`
- `unbcl!??1StringBuilder@UnBCL@@UEAA@XZ` at `0x18021db35`
- `unbcl!??1StringBuilder@UnBCL@@UEAA@XZ` at `0x18021db35`
- `unbcl!??0StringBuilder@UnBCL@@QEAA@XZ` at `0x18021d946`
- `unbcl!??0StringBuilder@UnBCL@@QEAA@XZ` at `0x18021d946`
- `unbcl!?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z` at `0x18021c626`
- `unbcl!?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z` at `0x18021c626`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021d5bf`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021d603`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021d5bf`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021d603`
- `unbcl!??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z` at `0x18021bcef`
- `unbcl!??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z` at `0x18021bdcd`
- `unbcl!??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z` at `0x18021bcef`
- `unbcl!??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z` at `0x18021bdcd`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18021d6d9`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18021d7d5`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18021d6d9`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18021d7d5`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18021d551`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18021d551`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021bfdd`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021c025`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021bfdd`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18021c025`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c88f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c8a6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c8bd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c8d4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c88f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c8a6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c8bd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18021c8d4`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18021b9aa`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18021c401`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18021d079`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18021b9aa`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18021c401`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18021d079`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18021c0b4`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18021d643`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18021c0b4`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18021d643`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18021c18f`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18021c19d`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18021c18f`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18021c19d`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c654`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c682`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c6b3`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c6f5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c730`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c761`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c7a3`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c7de`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c812`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c849`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c953`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021ca23`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cbbf`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cc90`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cd5b`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cef5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d017`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d469`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d49d`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d4d0`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d527`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d599`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d5dc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d842`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d86c`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d9bc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021da49`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c654`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c682`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c6b3`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c6f5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c730`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c761`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c7a3`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c7de`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c812`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c849`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021c953`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021ca23`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cbbf`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cc90`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cd5b`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021cef5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d017`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d469`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d49d`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d4d0`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d527`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d599`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d5dc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d842`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d86c`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021d9bc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18021da49`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18021c634`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18021c634`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18021dc1f`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18021dc1f`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x18021d0c1`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x18021d0c1`
- `unbcl!?get_P@?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEBAPEAVEncoding@2@XZ` at `0x18021be93`
- `unbcl!?get_P@?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEBAPEAVEncoding@2@XZ` at `0x18021be93`
- `unbcl!??0StreamReader@UnBCL@@QEAA@PEBVString@1@PEAVEncoding@1@@Z` at `0x18021beaa`
- `unbcl!??0StreamReader@UnBCL@@QEAA@PEBVString@1@PEAVEncoding@1@@Z` at `0x18021beaa`
- `unbcl!??1?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18021dcad`
- `unbcl!??1?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18021dcad`
- `unbcl!??0?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEAA@PEAVEncoding@1@@Z` at `0x18021be69`
- `unbcl!??0?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEAA@PEAVEncoding@1@@Z` at `0x18021be69`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18021d6ab`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18021d6ab`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18021c640`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18021c640`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021bb96`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021bbd1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021bc00`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021bf8e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021bfbd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021bfd1`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021c0a5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18021c133`

## string_xrefs

- `0x18021c3d5`: `Windows.old`
- `0x18021bc35`: `    Name: %s, Original path: %s, Current path: %s (%sallow relocation)`
- `0x18021c204`: `Final list of Windows.old roots:`
- `0x18021d173`: `Attempting to remove target folder%s: %s`
- `0x18021d15e`: ` (reparse)`
- `0x18021d389`: `VERBOSE: MOVETRACK: File symbolic link could not be removed. Error: 0x%08X`
- `0x18021d2f7`: `Attempting to remove target file (reparse): %s`
- `0x18021d280`: `VERBOSE: MOVETRACK: Folder could not be removed. Error: 0x%08X`
- `0x18021d20a`: `VERBOSE: MOVETRACK: Folder symbolic link could not be removed. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=74
__int64 __fastcall pProcessJournalEntries(
        struct IExecutionContext *a1,
        struct UnBCL::String *a2,
        struct UnBCL::String *a3,
        struct UnBCL::String *a4,
        struct UnBCL::String *a5,
        struct UnBCL::String *a6,
        int a7,
        int *a8)
{
  const struct UnBCL::String *v9; // rbx
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const WCHAR *CString; // rax
  __int64 v14; // rax
  __int64 v15; // rsi
  DWORD LastError; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  unsigned int v19; // ebx
  const wchar_t *v20; // rdi
  int (__fastcall ***v21)(_QWORD); // rcx
  __int64 v22; // rcx
  DWORD v23; // r15d
  __int64 v24; // r13
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  UnBCL::String *v28; // rax
  __int64 v29; // rcx
  _QWORD *v30; // rax
  UnBCL::String *P; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  _QWORD *v35; // rax
  UnBCL::String *v36; // rax
  const wchar_t *v37; // rax
  struct tagLOG_PARTIAL_MSG *v38; // rax
  const char *v39; // rax
  const char *v40; // rbx
  struct UnBCL::String *v41; // r12
  char *v42; // rbx
  struct UnBCL::Encoding *Unicode; // r14
  struct Stream *v44; // rax
  const char *v45; // rax
  const char *v46; // rbx
  char *v47; // rbx
  struct UnBCL::Encoding *v48; // r15
  struct Stream *v49; // rax
  __int64 v50; // rax
  char *v51; // rbx
  struct UnBCL::Encoding *v52; // rax
  const char *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rax
  unsigned int i; // ebx
  int (__fastcall ***v57)(_QWORD); // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  _QWORD *v60; // rax
  __int64 v61; // rax
  __int64 v62; // rcx
  bool v63; // zf
  __int64 (__fastcall *v64)(__int64, _QWORD); // rax
  _QWORD *v65; // rax
  const struct UnBCL::String *v66; // rax
  _QWORD *v67; // rax
  struct UnBCL::String *PathRoot; // rax
  __int64 v69; // rcx
  __int64 v70; // rax
  const struct UnBCL::String *v71; // rax
  struct UnBCL::String *v72; // rax
  int j; // edi
  int (__fastcall ***v74)(_QWORD); // rcx
  char *v75; // rcx
  _QWORD *v76; // rax
  const struct UnBCL::String *v77; // r14
  const struct UnBCL::String *v78; // rax
  char *v79; // r14
  __int64 v80; // r13
  const char *v81; // rax
  const char *v82; // rdi
  __int64 v83; // r15
  __int64 v84; // rax
  __int64 v85; // r9
  DWORD v86; // edi
  __int64 v87; // rbx
  struct tagLOG_PARTIAL_MSG *v88; // rax
  int k; // edi
  int (__fastcall ***v90)(_QWORD); // rcx
  char *v91; // rcx
  __int64 v92; // rbx
  DWORD v93; // r14d
  __int64 v94; // r15
  UnBCL::String *v95; // rax
  const char *v96; // rsi
  UnBCL::String *v97; // rax
  const wchar_t *v98; // rax
  struct tagLOG_PARTIAL_MSG *v99; // rax
  struct UnBCL::String *v100; // rax
  struct UnBCL::String *v101; // rax
  const struct UnBCL::String *v102; // rbx
  const struct UnBCL::String *v103; // rax
  struct UnBCL::String *v104; // rax
  __int64 v105; // rdi
  UnBCL::String *v106; // rax
  const char *v107; // rax
  struct tagLOG_PARTIAL_MSG *v108; // rax
  __int64 v109; // rdi
  UnBCL::String *v110; // rax
  const char *v111; // rax
  struct tagLOG_PARTIAL_MSG *v112; // rax
  __int64 v113; // rdi
  UnBCL::String *v114; // rax
  const char *v115; // rax
  struct tagLOG_PARTIAL_MSG *v116; // rax
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  int (__fastcall ***v122)(_QWORD); // rcx
  __int64 v123; // rax
  __int64 v124; // rcx
  __int64 v125; // rax
  __int64 v126; // rcx
  UnBCL::String **v127; // rax
  wint_t *v128; // rax
  __int64 v129; // rax
  __int64 v130; // rcx
  UnBCL::String **v131; // rax
  __int64 v132; // rax
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rcx
  UnBCL::String **v136; // rax
  wint_t *v137; // rax
  __int64 v138; // rax
  __int64 v139; // rcx
  UnBCL::String **v140; // rax
  __int64 v141; // rax
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 v144; // rcx
  UnBCL::String **v145; // rax
  __int64 v146; // rax
  __int64 v147; // rcx
  UnBCL::String **v148; // rax
  DWORD v149; // ebx
  __int64 v150; // rdi
  UnBCL::String *v151; // rax
  const char *v152; // rax
  struct tagLOG_PARTIAL_MSG *v153; // rax
  __int64 v154; // rax
  __int64 v155; // rcx
  UnBCL::String **v156; // rax
  wint_t *v157; // rdi
  UnBCL::String *v158; // rax
  int *v159; // r14
  UnBCL::String *v160; // rax
  __int64 v161; // rax
  __int64 v162; // rcx
  UnBCL::String **v163; // rax
  UnBCL::String *v164; // rdi
  struct UnBCL::String *v165; // rbx
  struct UnBCL::String *v166; // rax
  struct UnBCL::String *v167; // rax
  UnBCL::String *v168; // rdi
  struct UnBCL::String *v169; // rbx
  struct UnBCL::String *v170; // rax
  struct UnBCL::String *v171; // rax
  __int64 v172; // rax
  __int64 v173; // rcx
  UnBCL::String *v174; // rbx
  struct UnBCL::String *v175; // rdi
  struct UnBCL::String *v176; // rax
  struct UnBCL::String *v177; // rax
  _QWORD *v178; // rbx
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rcx
  UnBCL::String **v183; // rax
  const unsigned __int16 *v184; // rdi
  UnBCL::String *v185; // rax
  wint_t *v186; // rax
  UnBCL::String *v187; // rax
  __int64 v188; // rax
  __int64 v189; // rcx
  UnBCL::String **v190; // rax
  UnBCL::String *v191; // rdi
  struct UnBCL::String *v192; // rbx
  struct UnBCL::String *v193; // rax
  struct UnBCL::String *v194; // rax
  UnBCL::String *v195; // rdi
  struct UnBCL::String *v196; // rbx
  struct UnBCL::String *v197; // rax
  struct UnBCL::String *v198; // rax
  __int64 v199; // rax
  __int64 v200; // rcx
  UnBCL::String *v201; // rbx
  struct UnBCL::String *v202; // rdi
  struct UnBCL::String *v203; // rax
  struct UnBCL::String *v204; // rax
  _QWORD *v205; // rbx
  __int64 v206; // rax
  __int64 v207; // rax
  int v208; // r14d
  UnBCL::String *v209; // rax
  wint_t *v210; // rax
  __int64 v211; // rax
  __int64 v212; // rcx
  UnBCL::String **v213; // rax
  const unsigned __int16 *v214; // rax
  const struct UnBCL::String *v215; // rbx
  const struct UnBCL::String *v216; // rax
  struct UnBCL::String *v217; // rax
  const struct UnBCL::String *v218; // rax
  struct UnBCL::String *v219; // rax
  UnBCL::String *v220; // rax
  const WCHAR *v221; // rax
  DWORD FileAttributesW; // eax
  __int16 v223; // bx
  DWORD v224; // edi
  __int64 v225; // rsi
  UnBCL::String *v226; // rax
  const char *v227; // rax
  const wchar_t *v228; // r8
  struct tagLOG_PARTIAL_MSG *v229; // rax
  UnBCL::String *v230; // rax
  const WCHAR *v231; // rax
  DWORD v232; // edi
  __int64 v233; // rbx
  DWORD v234; // eax
  struct tagLOG_PARTIAL_MSG *v235; // rax
  const WCHAR *v236; // rax
  DWORD v237; // edi
  __int64 v238; // rbx
  DWORD v239; // eax
  DWORD v240; // ebx
  __int64 v241; // rdi
  UnBCL::String *v242; // rax
  const char *v243; // rax
  struct tagLOG_PARTIAL_MSG *v244; // rax
  UnBCL::String *v245; // rax
  const unsigned __int16 *v246; // rax
  DWORD v247; // edi
  __int64 v248; // rbx
  DWORD v249; // eax
  UnBCL::String *v250; // rax
  const unsigned __int16 *v251; // rdi
  UnBCL::String *v252; // rax
  const unsigned __int16 *v253; // rsi
  __int64 v254; // rax
  int (__fastcall ***v255)(_QWORD); // rcx
  __int64 v256; // rax
  __int64 v257; // rcx
  __int64 v258; // rax
  __int64 v259; // rcx
  UnBCL::String **v260; // rax
  UnBCL::String *v261; // rbx
  __int64 v262; // rax
  __int64 v263; // rcx
  const struct UnBCL::String **v264; // rax
  _BYTE *v265; // rcx
  __int64 v266; // rax
  __int64 v267; // rcx
  const struct UnBCL::String **v268; // rax
  struct UnBCL::String *FileName; // rax
  __int64 v270; // rax
  __int64 v271; // rcx
  const struct UnBCL::String **v272; // rax
  struct UnBCL::String *v273; // rax
  const struct UnBCL::String *v274; // rbx
  const struct UnBCL::String *v275; // rax
  __int64 v276; // rcx
  struct UnBCL::String *v277; // rax
  DWORD v278; // esi
  __int64 v279; // r14
  UnBCL::String *v280; // rax
  const wchar_t *v281; // rbx
  UnBCL::String *v282; // rax
  const char *v283; // rax
  struct tagLOG_PARTIAL_MSG *v284; // rax
  __int64 v285; // rbx
  void (__fastcall *v286)(__int64, const unsigned __int16 *); // rdi
  UnBCL::String *v287; // rax
  const unsigned __int16 *v288; // rax
  __int64 *v289; // rbx
  __int64 v290; // rdi
  UnBCL::String *v291; // rax
  const wchar_t *v292; // rax
  __int64 v293; // rax
  int (__fastcall ***v294)(_QWORD); // rcx
  __int64 v295; // rax
  __int64 v296; // rcx
  UnBCL::String *v297; // rbx
  struct UnBCL::String *v298; // rdi
  struct UnBCL::String *v299; // rax
  struct UnBCL::String *v300; // rax
  _QWORD *v301; // rbx
  __int64 v302; // rax
  __int64 v303; // rax
  UnBCL::String *v304; // rax
  const unsigned __int16 *v305; // rax
  UnBCL::String *v306; // rax
  const unsigned __int16 *v307; // rax
  int m; // ebx
  __int64 v309; // rax
  int (__fastcall ***v310)(_QWORD); // rcx
  UnBCL::String *v311; // rax
  const unsigned __int16 *v312; // rax
  __int64 v313; // rax
  __int64 v314; // rcx
  UnBCL::String **v315; // rax
  const unsigned __int16 *v316; // rax
  DWORD v317; // ebx
  __int64 v318; // rdi
  const char *v319; // rax
  struct tagLOG_PARTIAL_MSG *v320; // rax
  __int64 v321; // rbx
  void (__fastcall *v322)(__int64, const unsigned __int16 *); // rdi
  const unsigned __int16 *v323; // rax
  DWORD v324; // ebx
  __int64 v325; // rdi
  UnBCL::String *v326; // rax
  const char *v327; // rax
  struct tagLOG_PARTIAL_MSG *v328; // rax
  DWORD v330; // edi
  __int64 v331; // rbx
  struct tagLOG_PARTIAL_MSG *v332; // rax
  DWORD v333; // edi
  __int64 v334; // rbx
  UnBCL::String *v335; // rax
  const char *v336; // rax
  struct tagLOG_PARTIAL_MSG *v337; // rax
  int v338; // [rsp+20h] [rbp-388h]
  int v339; // [rsp+20h] [rbp-388h]
  int v340; // [rsp+28h] [rbp-380h]
  __int64 v341; // [rsp+38h] [rbp-370h]
  DWORD v342; // [rsp+40h] [rbp-368h]
  _BYTE v343[16]; // [rsp+60h] [rbp-348h] BYREF
  unsigned int v344; // [rsp+70h] [rbp-338h]
  _BYTE v345[16]; // [rsp+78h] [rbp-330h] BYREF
  const __int64 *v346; // [rsp+88h] [rbp-320h] BYREF
  _QWORD *v347; // [rsp+90h] [rbp-318h]
  UnBCL::String *v348; // [rsp+98h] [rbp-310h]
  _BYTE v349[16]; // [rsp+A0h] [rbp-308h] BYREF
  _BYTE v350[16]; // [rsp+B0h] [rbp-2F8h] BYREF
  _BYTE v351[16]; // [rsp+C0h] [rbp-2E8h] BYREF
  _BYTE v352[24]; // [rsp+D0h] [rbp-2D8h] BYREF
  int *v353; // [rsp+E8h] [rbp-2C0h]
  _BYTE v354[16]; // [rsp+F0h] [rbp-2B8h] BYREF
  void **v355; // [rsp+100h] [rbp-2A8h] BYREF
  __int64 v356; // [rsp+108h] [rbp-2A0h]
  _BYTE v357[16]; // [rsp+110h] [rbp-298h] BYREF
  _BYTE v358[16]; // [rsp+120h] [rbp-288h] BYREF
  _BYTE v359[16]; // [rsp+130h] [rbp-278h] BYREF
  _BYTE v360[24]; // [rsp+140h] [rbp-268h] BYREF
  UnBCL::String *v361; // [rsp+158h] [rbp-250h]
  _BYTE v362[16]; // [rsp+160h] [rbp-248h] BYREF
  _BYTE v363[16]; // [rsp+170h] [rbp-238h] BYREF
  const __int64 *v364; // [rsp+180h] [rbp-228h] BYREF
  __int64 v365; // [rsp+188h] [rbp-220h]
  unsigned int v366; // [rsp+190h] [rbp-218h] BYREF
  _BYTE v367[16]; // [rsp+198h] [rbp-210h] BYREF
  UnBCL::Exception *v368[3]; // [rsp+1A8h] [rbp-200h] BYREF
  _BYTE v369[16]; // [rsp+1C0h] [rbp-1E8h] BYREF
  void **v370; // [rsp+1D0h] [rbp-1D8h] BYREF
  __int64 v371; // [rsp+1D8h] [rbp-1D0h]
  _BYTE v372[16]; // [rsp+1E0h] [rbp-1C8h] BYREF
  _BYTE v373[16]; // [rsp+1F0h] [rbp-1B8h] BYREF
  _QWORD v374[2]; // [rsp+200h] [rbp-1A8h] BYREF
  void **v375; // [rsp+210h] [rbp-198h] BYREF
  __int64 v376; // [rsp+218h] [rbp-190h]
  struct IExecutionContext *v377; // [rsp+220h] [rbp-188h]
  _BYTE v378[16]; // [rsp+228h] [rbp-180h] BYREF
  _QWORD v379[2]; // [rsp+238h] [rbp-170h] BYREF
  _BYTE v380[16]; // [rsp+248h] [rbp-160h] BYREF
  _BYTE v381[16]; // [rsp+258h] [rbp-150h] BYREF
  _BYTE v382[16]; // [rsp+268h] [rbp-140h] BYREF
  _BYTE v383[16]; // [rsp+278h] [rbp-130h] BYREF
  _BYTE v384[16]; // [rsp+288h] [rbp-120h] BYREF
  _BYTE v385[16]; // [rsp+298h] [rbp-110h] BYREF
  _BYTE v386[16]; // [rsp+2A8h] [rbp-100h] BYREF
  _BYTE v387[16]; // [rsp+2B8h] [rbp-F0h] BYREF
  _BYTE v388[16]; // [rsp+2C8h] [rbp-E0h] BYREF
  _BYTE v389[16]; // [rsp+2D8h] [rbp-D0h] BYREF
  _BYTE v390[16]; // [rsp+2E8h] [rbp-C0h] BYREF
  _BYTE v391[16]; // [rsp+2F8h] [rbp-B0h] BYREF
  _BYTE v392[16]; // [rsp+308h] [rbp-A0h] BYREF
  _BYTE v393[16]; // [rsp+318h] [rbp-90h] BYREF
  struct UnBCL::Exception *v394[2]; // [rsp+328h] [rbp-80h] BYREF
  const char *v395; // [rsp+338h] [rbp-70h] BYREF
  struct UnBCL::String *v396; // [rsp+340h] [rbp-68h] BYREF
  const char *v397; // [rsp+348h] [rbp-60h] BYREF
  struct UnBCL::String *v398; // [rsp+350h] [rbp-58h] BYREF
  const struct UnBCL::String *v399; // [rsp+358h] [rbp-50h] BYREF

  v394[1] = (struct UnBCL::Exception *)-2LL;
  v399 = a4;
  v361 = a3;
  v348 = a2;
  v377 = a1;
  v398 = a5;
  v396 = a6;
  v353 = a8;
  if ( a8 && !a5 )
    *a8 = 0;
  v9 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v352, L"SetupPlatform.ini");
  v10 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a1)(a1);
  v11 = UnBCL::Path::Combine(v10, v9);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v378, v11);
  UnBCL::String::~String((UnBCL::String *)v352);
  v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v378);
  CString = UnBCL::String::get_CString(v12);
  v14 = SPReadOSPiecesSection(L"OS.OLD.Pieces", CString);
  UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>(&v364, v14);
  v15 = v365;
  if ( v365 )
  {
    v344 = 0;
    LastError = GetLastError();
    v17 = CurrentIP();
    v18 = ConstructPartialMsgW(0x4000000u, "Final list of source OS pieces:");
    WdsSetupLogMessageW(
      v18,
      819200,
      L"D",
      0,
      251,
      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
      L"pProcessJournalEntries",
      v17,
      LastError,
      0,
      0);
    v19 = 0;
    v20 = &cchOriginalDestLength;
    while ( 1 )
    {
      v21 = (int (__fastcall ***)(_QWORD))(v15 + *(int *)(*(_QWORD *)(v15 + 8) + 12LL) + 8LL);
      if ( (int)v19 >= (**v21)(v21) )
        break;
      v22 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
      if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, v19) )
      {
        v23 = GetLastError();
        v24 = CurrentIP();
        v25 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
        if ( !*(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, v19)
                        + 80LL) )
          v20 = L"do not ";
        v26 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 24LL))(v26, v19);
        v28 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v27 + 72LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v27 + 72LL));
        v395 = (const char *)UnBCL::String::get_CString(v28);
        v29 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
        v30 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 24LL))(v29, v19);
        P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v30 + 32LL);
        v397 = (const char *)UnBCL::String::get_CString(P);
        v32 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
        v33 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 24LL))(v32, v19);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(*v33 + 16LL) )
        {
          v34 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
          v35 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 24LL))(v34, v19);
          v36 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v35 + 16LL);
          v37 = UnBCL::String::get_CString(v36);
        }
        else
        {
          v37 = L"<NULL>";
        }
        v38 = ConstructPartialMsgW(
                0x4000000u,
                "    Name: %s, Original path: %s, Current path: %s (%sallow relocation)",
                (const char *)v37,
                v397,
                v395,
                (const char *)v20);
        WdsSetupLogMessageW(
          v38,
          819200,
          L"D",
          0,
          263,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"pProcessJournalEntries",
          v24,
          v23,
          0,
          0);
        v20 = &cchOriginalDestLength;
      }
      ++v19;
    }
    try
    {
      v39 = (const char *)UnBCL::Object::operator new(0x50u);
      v40 = v39;
      v41 = v396;
      v395 = v39;
      if ( v39 )
      {
        UnBCL::FileStream::FileStream(v39, v398, 1, 3, 2, 128, 1);
        *((_QWORD *)v40 + 5) = &UnBCL::FileStream::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v40 = 0;
      }
      UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(v379, v40);
      v42 = (char *)UnBCL::Object::operator new(0x80u);
      v395 = v42;
      if ( v42 )
      {
        Unicode = (struct UnBCL::Encoding *)UnBCL::Encoding::GetUnicode();
        v44 = (struct Stream *)UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(v379);
        UnBCL::StreamWriter::StreamWriter((UnBCL::StreamWriter *)v42, v44, Unicode, 0, 1, 1);
        *((_QWORD *)v42 + 4) = &UnBCL::StreamWriter::`local vftable'{for `UnBCL::Object'};
      }
      UnBCL::SmartPtr<UnBCL::StreamWriter>::SmartPtr<UnBCL::StreamWriter>(&v355, v42);
      v45 = (const char *)UnBCL::Object::operator new(0x50u);
      v46 = v45;
      v395 = v45;
      if ( v45 )
      {
        UnBCL::FileStream::FileStream(v45, v41, 1, 3, 2, 128, 1);
        *((_QWORD *)v46 + 5) = &UnBCL::FileStream::`local vftable'{for `UnBCL::Object'};
      }
      UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(v374, v46);
      v47 = (char *)UnBCL::Object::operator new(0x80u);
      v395 = v47;
      if ( v47 )
      {
        v48 = (struct UnBCL::Encoding *)UnBCL::Encoding::GetUnicode();
        v49 = (struct Stream *)UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(v374);
        UnBCL::StreamWriter::StreamWriter((UnBCL::StreamWriter *)v47, v49, v48, 0, 1, 1);
        *((_QWORD *)v47 + 4) = &UnBCL::StreamWriter::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v47 = 0;
      }
      UnBCL::SmartPtr<UnBCL::StreamWriter>::SmartPtr<UnBCL::StreamWriter>(&v370, v47);
      v50 = UnBCL::Encoding::GetUnicode();
      UnBCL::SmartPtr<UnBCL::Encoding>::SmartPtr<UnBCL::Encoding>(v382, v50);
      v51 = (char *)UnBCL::Object::operator new(0x128u);
      v395 = v51;
      if ( v51 )
      {
        v52 = (struct UnBCL::Encoding *)UnBCL::SmartPtr<UnBCL::Encoding>::get_P(v382);
        UnBCL::StreamReader::StreamReader((UnBCL::StreamReader *)v51, v399, v52);
        *((_QWORD *)v51 + 30) = &UnBCL::StreamReader::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v51 = 0;
      }
      UnBCL::SmartPtr<UnBCL::StreamReader>::SmartPtr<UnBCL::StreamReader>(&v375, v51);
      v53 = (const char *)UnBCL::Object::operator new(0x80u);
      v395 = v53;
      if ( v53 )
        v55 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
                v53,
                v54);
      else
        v55 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(
        &v346,
        v55);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v347 + 40LL))(v347, 1);
      for ( i = 0; ; ++i )
      {
        v57 = (int (__fastcall ***)(_QWORD))(v15 + *(int *)(*(_QWORD *)(v15 + 8) + 12LL) + 8LL);
        if ( (int)i >= (**v57)(v57) )
          break;
        v58 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
        if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 24LL))(v58, i) )
        {
          v59 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
          v60 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v59 + 24LL))(v59, i);
          v61 = UnBCL::SmartPtr<UnBCL::String>::get_P(*v60 + 48LL);
          v62 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
          v63 = v61 == 0;
          v64 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 24LL);
          if ( v63 )
          {
            v67 = (_QWORD *)v64(v62, i);
            v66 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v67 + 32LL);
          }
          else
          {
            v65 = (_QWORD *)v64(v62, i);
            v66 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v65 + 48LL);
          }
          PathRoot = UnBCL::Path::GetPathRoot(v66);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v345, PathRoot);
          v69 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 16LL) + 8LL;
          v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v69 + 24LL))(v69, i);
          v71 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v70 + 72LL)
                                                                                + 16LL))(*(_QWORD *)(*(_QWORD *)v70 + 72LL));
          v72 = UnBCL::Path::GetPathRoot(v71);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v349, v72);
          for ( j = 0; ; ++j )
          {
            v74 = (int (__fastcall ***)(_QWORD))((char *)v347 + *(int *)(v347[1] + 12LL) + 8);
            if ( j >= (**v74)(v74) )
              break;
            v75 = (char *)v347 + *(int *)(v347[1] + 16LL) + 8;
            v76 = (_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v75 + 24LL))(v75, (unsigned int)j);
            v77 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v76)(*v76);
            v78 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v345);
            if ( !UnBCL::String::Compare(v78, v77, 1) )
            {
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v358, 0);
              UnBCL::SmartPtr<UnBCL::String>::operator=(v345, v358);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v358);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v357, 0);
              UnBCL::SmartPtr<UnBCL::String>::operator=(v349, v357);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v357);
              break;
            }
          }
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v345) && UnBCL::SmartPtr<UnBCL::String>::get_P(v349) )
          {
            v79 = (char *)v347 + *(int *)(v347[1] + 16LL);
            v80 = *((_QWORD *)v79 + 1);
            v81 = (const char *)UnBCL::Object::operator new(0x40u);
            v82 = v81;
            v395 = v81;
            if ( v81 )
            {
              v83 = UnBCL::SmartPtr<UnBCL::String>::Steal(v349);
              v84 = UnBCL::SmartPtr<UnBCL::String>::Steal(v345);
              v81 = (const char *)UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(
                                    v82,
                                    v84,
                                    v83,
                                    v85,
                                    v338,
                                    v340);
            }
            (*(void (__fastcall **)(char *, const char *))(v80 + 40))(v79 + 8, v81);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v349);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v345);
        }
      }
      v86 = GetLastError();
      v87 = CurrentIP();
      v88 = ConstructPartialMsgW(0x4000000u, "Final list of Windows.old roots:");
      WdsSetupLogMessageW(
        v88,
        819200,
        L"D",
        0,
        340,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"pProcessJournalEntries",
        v87,
        v86,
        0,
        0);
      for ( k = 0; ; ++k )
      {
        v90 = (int (__fastcall ***)(_QWORD))((char *)v347 + *(int *)(v347[1] + 12LL) + 8);
        if ( k >= (**v90)(v90) )
          break;
        v91 = (char *)v347 + *(int *)(v347[1] + 16LL) + 8;
        v92 = *(_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v91 + 24LL))(v91, (unsigned int)k);
        v93 = GetLastError();
        v94 = CurrentIP();
        v95 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        v96 = (const char *)UnBCL::String::get_CString(v95);
        if ( (**(__int64 (__fastcall ***)(__int64))v92)(v92) )
        {
          v97 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v92)(v92);
          v98 = UnBCL::String::get_CString(v97);
        }
        else
        {
          v98 = L"<NULL>";
        }
        v99 = ConstructPartialMsgW(0x4000000u, "    %s = %s", (const char *)v98, v96);
        WdsSetupLogMessageW(
          v99,
          819200,
          L"D",
          0,
          349,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"pProcessJournalEntries",
          v94,
          v93,
          0,
          0);
      }
      v100 = UnBCL::String::TrimEnd(v348, L"\\");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v354, v100);
      v101 = UnBCL::String::TrimEnd(v361, L"\\");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v351, v101);
      v102 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v352, L"Windows.old");
      v103 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v351);
      v104 = UnBCL::Path::Combine(v103, v102);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v372, v104);
      UnBCL::String::~String((UnBCL::String *)v352);
      LODWORD(v102) = GetLastError();
      v105 = CurrentIP();
      v106 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v351);
      v107 = (const char *)UnBCL::String::get_CString(v106);
      v108 = ConstructPartialMsgW(0x4000000u, "ProcessJournalEntries: Old OS: %s", v107);
      WdsSetupLogMessageW(
        v108,
        819200,
        L"D",
        0,
        356,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"pProcessJournalEntries",
        v105,
        (_DWORD)v102,
        0,
        0);
      LODWORD(v102) = GetLastError();
      v109 = CurrentIP();
      v110 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
      v111 = (const char *)UnBCL::String::get_CString(v110);
      v112 = ConstructPartialMsgW(0x4000000u, "ProcessJournalEntries: New OS: %s", v111);
      WdsSetupLogMessageW(
        v112,
        819200,
        L"D",
        0,
        357,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"pProcessJournalEntries",
        v109,
        (_DWORD)v102,
        0,
        0);
      LODWORD(v102) = GetLastError();
      v113 = CurrentIP();
      v114 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v372);
      v115 = (const char *)UnBCL::String::get_CString(v114);
      v116 = ConstructPartialMsgW(0x4000000u, "ProcessJournalEntries: WinOLD: %s", v115);
      WdsSetupLogMessageW(
        v116,
        819200,
        L"D",
        0,
        358,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"pProcessJournalEntries",
        v113,
        (_DWORD)v102,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v359);
      LODWORD(v348) = 1;
      while ( 1 )
      {
        v117 = v376 + *(int *)(*(_QWORD *)v376 + 12LL);
        v118 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v384, v118);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v359, v384);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v384);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v359) )
        {
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v359);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v372);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v351);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v354);
          v346 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v346);
          v375 = &UnBCL::SmartPtr<UnBCL::StreamReader>::`vftable';
          UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v375);
          UnBCL::SmartPtr<UnBCL::Encoding>::~SmartPtr<UnBCL::Encoding>(v382);
          v370 = &UnBCL::SmartPtr<UnBCL::StreamWriter>::`vftable';
          UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v370);
          v374[0] = &UnBCL::SmartPtr<UnBCL::FileStream>::`vftable';
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v374);
          v355 = &UnBCL::SmartPtr<UnBCL::StreamWriter>::`vftable';
          UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v355);
          v379[0] = &UnBCL::SmartPtr<UnBCL::FileStream>::`vftable';
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v379);
          goto LABEL_134;
        }
        v119 = UnBCL::SmartPtr<UnBCL::String>::operator->(v359);
        v120 = UnBCL::String::Split(v119, L"|");
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v343, v120);
        if ( !UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v343) )
          goto LABEL_127;
        v121 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v122 = (int (__fastcall ***)(_QWORD))(v121 + 8 + *(int *)(*(_QWORD *)(v121 + 8) + 12LL));
        if ( (**v122)(v122) < 3 )
          goto LABEL_127;
        v123 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v124 = v123 + 8 + *(int *)(*(_QWORD *)(v123 + 8) + 16LL);
        if ( !*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v124 + 24LL))(v124, 0) )
          goto LABEL_127;
        v125 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v126 = v125 + 8 + *(int *)(*(_QWORD *)(v125 + 8) + 16LL);
        v127 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v126 + 24LL))(v126, 0);
        v128 = (wint_t *)UnBCL::String::get_CString(*v127);
        if ( !iswalpha(*v128) )
          goto LABEL_127;
        v129 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v130 = v129 + 8 + *(int *)(*(_QWORD *)(v129 + 8) + 16LL);
        v131 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v130 + 24LL))(v130, 0);
        if ( UnBCL::String::get_CString(*v131)[1] != 58 )
          goto LABEL_127;
        v132 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v133 = v132 + 8 + *(int *)(*(_QWORD *)(v132 + 8) + 16LL);
        if ( !*(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v133 + 24LL))(v133, 1) )
          goto LABEL_127;
        v134 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v135 = v134 + 8 + *(int *)(*(_QWORD *)(v134 + 8) + 16LL);
        v136 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v135 + 24LL))(v135, 1);
        v137 = (wint_t *)UnBCL::String::get_CString(*v136);
        if ( !iswalpha(*v137) )
          goto LABEL_127;
        v138 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v139 = v138 + 8 + *(int *)(*(_QWORD *)(v138 + 8) + 16LL);
        v140 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v139 + 24LL))(v139, 1);
        if ( UnBCL::String::get_CString(*v140)[1] != 58 )
          goto LABEL_127;
        v141 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v142 = v141 + 8 + *(int *)(*(_QWORD *)(v141 + 8) + 16LL);
        if ( !*(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v142 + 24LL))(v142, 2)
          || (v143 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343),
              v144 = v143 + 8 + *(int *)(*(_QWORD *)(v143 + 8) + 16LL),
              v145 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v144 + 24LL))(v144, 2),
              *UnBCL::String::get_CString(*v145) != 70)
          && (v146 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343),
              v147 = v146 + 8 + *(int *)(*(_QWORD *)(v146 + 8) + 16LL),
              v148 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v147 + 24LL))(v147, 2),
              *UnBCL::String::get_CString(*v148) != 72) )
        {
LABEL_127:
          v324 = GetLastError();
          v325 = CurrentIP();
          v326 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v359);
          v327 = (const char *)UnBCL::String::get_CString(v326);
          v328 = ConstructPartialMsgW(0x2000000u, "ProcessJournalEntries: Malformed entry ignored: %s", v327);
          WdsSetupLogMessageW(
            v328,
            819200,
            L"D",
            0,
            381,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"pProcessJournalEntries",
            v325,
            v324,
            0,
            0);
          goto LABEL_128;
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v373, v351);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v369, v372);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v358, v351);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v357, v354);
        v149 = GetLastError();
        v150 = CurrentIP();
        v151 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v359);
        v152 = (const char *)UnBCL::String::get_CString(v151);
        v153 = ConstructPartialMsgW(0x4000000u, "VERBOSE: Converting: %s", v152);
        WdsSetupLogMessageW(
          v153,
          819200,
          L"D",
          0,
          397,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"pProcessJournalEntries",
          v150,
          v149,
          0,
          0);
        v154 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v155 = v154 + 8 + *(int *)(*(_QWORD *)(v154 + 8) + 16LL);
        v156 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v155 + 24LL))(v155, 0);
        v157 = (wint_t *)UnBCL::String::get_CString(*v156);
        v158 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v351);
        LOWORD(v149) = *UnBCL::String::get_CString(v158);
        LOWORD(v157) = towlower(*v157);
        if ( (_WORD)v157 == towlower(v149) )
        {
          v159 = v353;
        }
        else
        {
          LODWORD(v348) = 0;
          v159 = v353;
          if ( v353 )
            *v353 = 0;
          LOWORD(v396) = 63;
          *(_DWORD *)((char *)&v396 + 2) = 58;
          LOWORD(v399) = 63;
          *(_DWORD *)((char *)&v399 + 2) = 58;
          v160 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v351);
          LOWORD(v396) = *UnBCL::String::get_CString(v160);
          v161 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
          v162 = v161 + 8 + *(int *)(*(_QWORD *)(v161 + 8) + 16LL);
          v163 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v162 + 24LL))(v162, 0);
          LOWORD(v399) = *UnBCL::String::get_CString(*v163);
          v164 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v351);
          v165 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v366, (const unsigned __int16 *)&v399);
          v166 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v360, (const unsigned __int16 *)&v396);
          v167 = UnBCL::String::Replace(v164, v166, v165, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v385, v167);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v373, v385);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v385);
          UnBCL::String::~String((UnBCL::String *)v360);
          UnBCL::String::~String((UnBCL::String *)&v366);
          v168 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v372);
          v169 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v360, (const unsigned __int16 *)&v399);
          v170 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v366, (const unsigned __int16 *)&v396);
          v171 = UnBCL::String::Replace(v168, v170, v169, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v391, v171);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v369, v391);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v391);
          UnBCL::String::~String((UnBCL::String *)&v366);
          UnBCL::String::~String((UnBCL::String *)v360);
        }
        v172 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v173 = v172 + 8 + *(int *)(*(_QWORD *)(v172 + 8) + 16LL);
        v174 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v173 + 24LL))(v173, 0);
        v175 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v369);
        v176 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v373);
        v177 = UnBCL::String::Replace(v174, v176, v175, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v349, v177);
        v178 = v347;
        v179 = UnBCL::SmartPtr<UnBCL::String>::get_P(v349);
        v180 = SPRemapPath(v179, v178, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v386, v180);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v349, v386);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v386);
        v181 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v182 = v181 + 8 + *(int *)(*(_QWORD *)(v181 + 8) + 16LL);
        v183 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v182 + 24LL))(v182, 1);
        v184 = UnBCL::String::get_CString(*v183);
        v185 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
        v186 = (wint_t *)UnBCL::String::get_CString(v185);
        LOWORD(v184) = *v184;
        LOWORD(v178) = towlower(*v186);
        if ( towlower((wint_t)v184) != (_WORD)v178 )
        {
          LODWORD(v348) = 0;
          if ( v159 )
            *v159 = 0;
          LOWORD(v397) = 63;
          *(_DWORD *)((char *)&v397 + 2) = 58;
          LOWORD(v398) = 63;
          *(_DWORD *)((char *)&v398 + 2) = 58;
          v187 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
          LOWORD(v397) = *UnBCL::String::get_CString(v187);
          v188 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
          v189 = v188 + 8 + *(int *)(*(_QWORD *)(v188 + 8) + 16LL);
          v190 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v189 + 24LL))(v189, 0);
          LOWORD(v398) = *UnBCL::String::get_CString(*v190);
          v191 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v351);
          v192 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v360, (const unsigned __int16 *)&v398);
          v193 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v366, (const unsigned __int16 *)&v397);
          v194 = UnBCL::String::Replace(v191, v193, v192, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v387, v194);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v358, v387);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v387);
          UnBCL::String::~String((UnBCL::String *)&v366);
          UnBCL::String::~String((UnBCL::String *)v360);
          v195 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v354);
          v196 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v360, (const unsigned __int16 *)&v398);
          v197 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v366, (const unsigned __int16 *)&v397);
          v198 = UnBCL::String::Replace(v195, v197, v196, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v388, v198);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v357, v388);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v388);
          UnBCL::String::~String((UnBCL::String *)&v366);
          UnBCL::String::~String((UnBCL::String *)v360);
        }
        v199 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v200 = v199 + 8 + *(int *)(*(_QWORD *)(v199 + 8) + 16LL);
        v201 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v200 + 24LL))(v200, 1);
        v202 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v358);
        v203 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v357);
        v204 = UnBCL::String::Replace(v201, v203, v202, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v363, v204);
        v205 = v347;
        v206 = UnBCL::SmartPtr<UnBCL::String>::get_P(v363);
        v207 = SPRemapPath(v206, v205, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v389, v207);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v363, v389);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v389);
        v208 = 0;
        LOWORD(v395) = 63;
        *(_DWORD *)((char *)&v395 + 2) = *(_DWORD *)L":\\";
        HIWORD(v395) = asc_180557F68[3];
        v209 = (UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v377)(v377);
        v210 = (wint_t *)UnBCL::String::get_CString(v209);
        LOWORD(v395) = towlower(*v210);
        v211 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
        v212 = v211 + 8 + *(int *)(*(_QWORD *)(v211 + 8) + 16LL);
        v213 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v212 + 24LL))(v212, 1);
        v214 = UnBCL::String::get_CString(*v213);
        v215 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v360, v214 + 3);
        v216 = (const struct UnBCL::String *)UnBCL::String::String(
                                               (UnBCL::String *)&v366,
                                               (const unsigned __int16 *)&v395);
        v217 = UnBCL::Path::Combine(v216, v215);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v350, v217);
        UnBCL::String::~String((UnBCL::String *)&v366);
        UnBCL::String::~String((UnBCL::String *)v360);
        v218 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v350);
        v219 = UnBCL::Path::WithLongPrefix(v218, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v390, v219);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v350, v390);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v390);
        v220 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v350);
        v221 = UnBCL::String::get_CString(v220);
        FileAttributesW = GetFileAttributesW(v221);
        v223 = FileAttributesW;
        if ( FileAttributesW != -1 )
        {
          if ( (FileAttributesW & 0x10) != 0 )
          {
            v224 = GetLastError();
            v225 = CurrentIP();
            v226 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v350);
            v227 = (const char *)UnBCL::String::get_CString(v226);
            v228 = L" (reparse)";
            if ( (v223 & 0x400) == 0 )
              v228 = &cchOriginalDestLength;
            v229 = ConstructPartialMsgW(
                     0x4000000u,
                     "Attempting to remove target folder%s: %s",
                     (const char *)v228,
                     v227);
            WdsSetupLogMessageW(
              v229,
              819200,
              L"D",
              0,
              464,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"pProcessJournalEntries",
              v225,
              v224,
              0,
              0);
            v230 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v350);
            if ( (v223 & 0x400) != 0 )
            {
              v231 = UnBCL::String::get_CString(v230);
              if ( !RemoveDirectoryW(v231) )
              {
                v232 = GetLastError();
                v233 = CurrentIP();
                v234 = GetLastError();
                v235 = ConstructPartialMsgW(
                         0x2000000u,
                         "VERBOSE: MOVETRACK: Folder symbolic link could not be removed. Error: 0x%08X",
                         v234);
                v342 = v232;
                v341 = v233;
                v339 = 471;
                goto LABEL_89;
              }
            }
            else
            {
              v236 = UnBCL::String::get_CString(v230);
              if ( !(unsigned int)DeletePathEx(v236) )
              {
                v237 = GetLastError();
                v238 = CurrentIP();
                v239 = GetLastError();
                v235 = ConstructPartialMsgW(
                         0x2000000u,
                         "VERBOSE: MOVETRACK: Folder could not be removed. Error: 0x%08X",
                         v239);
                v342 = v237;
                v341 = v238;
                v339 = 480;
                goto LABEL_89;
              }
            }
          }
          else if ( (FileAttributesW & 0x400) != 0 )
          {
            v240 = GetLastError();
            v241 = CurrentIP();
            v242 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v350);
            v243 = (const char *)UnBCL::String::get_CString(v242);
            v244 = ConstructPartialMsgW(0x4000000u, "Attempting to remove target file (reparse): %s", v243);
            WdsSetupLogMessageW(
              v244,
              819200,
              L"D",
              0,
              495,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"pProcessJournalEntries",
              v241,
              v240,
              0,
              0);
            v245 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v350);
            v246 = UnBCL::String::get_CString(v245);
            if ( !(unsigned int)DeleteFileEx2(v246, 0) )
            {
              v247 = GetLastError();
              v248 = CurrentIP();
              v249 = GetLastError();
              v235 = ConstructPartialMsgW(
                       0x2000000u,
                       "VERBOSE: MOVETRACK: File symbolic link could not be removed. Error: 0x%08X",
                       v249);
              v342 = v247;
              v341 = v248;
              v339 = 499;
LABEL_89:
              WdsSetupLogMessageW(
                v235,
                819200,
                L"D",
                0,
                v339,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"pProcessJournalEntries",
                v341,
                v342,
                0,
                0);
              if ( v353 )
                *v353 = 0;
            }
          }
          else
          {
            v208 = 1;
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v350);
        if ( (_DWORD)v348 && v356 && !v208 )
        {
          v250 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v349);
          v251 = UnBCL::String::get_CString(v250);
          v252 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v363);
          v253 = UnBCL::String::get_CString(v252);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v345);
          v254 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
          v255 = (int (__fastcall ***)(_QWORD))(v254 + 8 + *(int *)(*(_QWORD *)(v254 + 8) + 12LL));
          if ( (**v255)(v255) > 3 )
          {
            v256 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
            v257 = v256 + 8 + *(int *)(*(_QWORD *)(v256 + 8) + 16LL);
            if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v257 + 24LL))(v257, 3) )
            {
              v258 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
              v259 = v258 + 8 + *(int *)(*(_QWORD *)(v258 + 8) + 16LL);
              v260 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v259 + 24LL))(v259, 2);
              if ( *UnBCL::String::get_CString(*v260) == 72 )
              {
                v261 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                v361 = v261;
                if ( v261 )
                {
                  v262 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
                  v263 = v262 + 8 + *(int *)(*(_QWORD *)(v262 + 8) + 16LL);
                  v264 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v263 + 24LL))(
                                                          v263,
                                                          3);
                  UnBCL::String::String(v261, *v264);
                  *(_QWORD *)v261 = &UnBCL::String::`local vftable';
                }
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v383, v261);
                UnBCL::SmartPtr<UnBCL::String>::operator=(v345, v383);
                v265 = v383;
              }
              else
              {
                v266 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
                v267 = v266 + 8 + *(int *)(*(_QWORD *)(v266 + 8) + 16LL);
                v268 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v267 + 24LL))(
                                                        v267,
                                                        0);
                FileName = UnBCL::Path::GetFileName(*v268);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v392, FileName);
                v270 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
                v271 = v270 + 8 + *(int *)(*(_QWORD *)(v270 + 8) + 16LL);
                v272 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v271
                                                                                                  + 24LL))(
                                                        v271,
                                                        3);
                v273 = UnBCL::Path::GetFileName(*v272);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v380, v273);
                v274 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v380);
                v275 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v392);
                if ( UnBCL::String::Compare(v275, v274, 0) )
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v345, v380);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v380);
                v265 = v392;
              }
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v265);
            }
          }
          v276 = v356 + *(int *)(*(_QWORD *)v356 + 12LL);
          (*(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v276 + 48LL))(v276, v251 + 2);
          v277 = UnBCL::String::Concat(L"-", v253 + 2);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v381, v277);
          v278 = GetLastError();
          v279 = CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v345) )
          {
            v280 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v345);
            v281 = UnBCL::String::get_CString(v280);
          }
          else
          {
            v281 = L"no short name";
          }
          v282 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v381);
          v283 = (const char *)UnBCL::String::get_CString(v282);
          v284 = ConstructPartialMsgW(
                   0x4000000u,
                   "VERBOSE: Result (KRNL) : %s -> %s (%s)",
                   (const char *)v251 + 4,
                   v283,
                   (const char *)v281);
          WdsSetupLogMessageW(
            v284,
            819200,
            L"D",
            0,
            552,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"pProcessJournalEntries",
            v279,
            v278,
            0,
            0);
          v285 = v356 + *(int *)(*(_QWORD *)v356 + 12LL);
          v286 = *(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v285 + 48LL);
          v287 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v381);
          v288 = UnBCL::String::get_CString(v287);
          v286(v285, v288);
          v289 = (__int64 *)(v356 + *(int *)(*(_QWORD *)v356 + 12LL));
          v290 = *v289;
          if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v345) )
          {
            v291 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v345);
            v292 = UnBCL::String::get_CString(v291);
          }
          else
          {
            v292 = L"|none|";
          }
          (*(void (__fastcall **)(__int64 *, const wchar_t *))(v290 + 48))(v289, v292);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v381);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v345);
        }
        if ( v371 )
        {
          v293 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
          v294 = (int (__fastcall ***)(_QWORD))(v293 + 8 + *(int *)(*(_QWORD *)(v293 + 8) + 12LL));
          if ( (**v294)(v294) <= 3 )
          {
            v300 = 0;
          }
          else
          {
            v295 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
            v296 = v295 + 8 + *(int *)(*(_QWORD *)(v295 + 8) + 16LL);
            v297 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v296 + 24LL))(v296, 3);
            v298 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v369);
            v299 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v373);
            v300 = UnBCL::String::Replace(v297, v299, v298, 1);
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v362, v300);
          v301 = v347;
          v302 = UnBCL::SmartPtr<UnBCL::String>::get_P(v362);
          v303 = SPRemapPath(v302, v301, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v393, v303);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v362, v393);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v393);
          UnBCL::StringBuilder::StringBuilder((UnBCL::StringBuilder *)v352);
          v304 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v349);
          v305 = UnBCL::String::get_CString(v304);
          UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v352, v305);
          UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v352, L"|");
          v306 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v363);
          v307 = UnBCL::String::get_CString(v306);
          UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v352, v307);
          for ( m = 2; ; ++m )
          {
            v309 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
            v310 = (int (__fastcall ***)(_QWORD))(v309 + 8 + *(int *)(*(_QWORD *)(v309 + 8) + 12LL));
            if ( m >= (**v310)(v310) )
              break;
            UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v352, L"|");
            if ( m == 3 )
            {
              if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v362) )
              {
                v311 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v362);
                v312 = UnBCL::String::get_CString(v311);
              }
              else
              {
                v312 = &cchOriginalDestLength;
              }
              UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v352, v312);
            }
            else
            {
              v313 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v343);
              v314 = v313 + 8 + *(int *)(*(_QWORD *)(v313 + 8) + 16LL);
              v315 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v314 + 24LL))(
                                         v314,
                                         (unsigned int)m);
              v316 = UnBCL::String::get_CString(*v315);
              UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v352, v316);
            }
          }
          v317 = GetLastError();
          v318 = CurrentIP();
          v319 = (const char *)UnBCL::StringBuilder::get_CString((UnBCL::StringBuilder *)v352);
          v320 = ConstructPartialMsgW(0x4000000u, "VERBOSE: Result (RLBK) : %s", v319);
          WdsSetupLogMessageW(
            v320,
            819200,
            L"D",
            0,
            579,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"pProcessJournalEntries",
            v318,
            v317,
            0,
            0);
          v321 = v371 + *(int *)(*(_QWORD *)v371 + 12LL);
          v322 = *(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v321 + 48LL);
          v323 = UnBCL::StringBuilder::get_CString((UnBCL::StringBuilder *)v352);
          v322(v321, v323);
          UnBCL::StringBuilder::~StringBuilder((UnBCL::StringBuilder *)v352);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v362);
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v363);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v349);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v357);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v358);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v369);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v373);
LABEL_128:
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v343);
      }
    }
    catch ( UnBCL::Exception *v394 )
    {
      pExceptionLogFormat::pExceptionLogFormat(
        (pExceptionLogFormat *)&v366,
        0x2000000u,
        v394[0],
        "Error processing journal entries: ");
      UnBCL::Exception::AddStackTrace(
        v368[2],
        "long __cdecl pProcessJournalEntries(struct IExecutionContext *,class UnBCL::String *,class UnBCL::String *,class"
        " UnBCL::String *,class UnBCL::String *,class UnBCL::String *,int,int *)");
      v333 = GetLastError();
      v334 = CurrentIP();
      v335 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v367);
      v336 = (const char *)UnBCL::String::get_CString(v335);
      v337 = ConstructPartialMsgW(v366, "%s", v336);
      WdsSetupLogMessageW(
        v337,
        819200,
        L"D",
        0,
        592,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"pProcessJournalEntries",
        v334,
        v333,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v368);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v367);
      v344 = -2147467259;
    }
LABEL_134:
    v364 = &UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v364);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v378);
    return v344;
  }
  else
  {
    v330 = GetLastError();
    v331 = CurrentIP();
    v332 = ConstructPartialMsgW(0x2000000u, "No source OS pieces found");
    WdsSetupLogMessageW(
      v332,
      819200,
      L"D",
      0,
      269,
      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
      L"pProcessJournalEntries",
      v331,
      v330,
      0,
      0);
    v364 = &UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v364);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v378);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x18021b8ec  mov     rax, rsp
0x18021b8ef  push    rbx
0x18021b8f0  push    rsi
0x18021b8f1  push    rdi
0x18021b8f2  push    r12
0x18021b8f4  push    r13
0x18021b8f6  push    r14
0x18021b8f8  push    r15
0x18021b8fa  sub     rsp, 370h
0x18021b901  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x18021b909  mov     rax, cs:__security_cookie
0x18021b910  xor     rax, rsp
0x18021b913  mov     [rsp+3A8h+var_48], rax
0x18021b91b  mov     [rsp+3A8h+var_50], r9
0x18021b923  mov     [rsp+3A8h+var_250], r8
0x18021b92b  mov     [rsp+3A8h+var_310], rdx
0x18021b933  mov     rdi, rcx
0x18021b936  mov     [rsp+3A8h+var_188], rcx
0x18021b93e  mov     r14, [rsp+3A8h+arg_20]
0x18021b946  mov     [rsp+3A8h+var_58], r14
0x18021b94e  mov     r12, [rsp+3A8h+arg_28]
0x18021b956  mov     [rsp+3A8h+var_68], r12
0x18021b95e  mov     rax, [rsp+3A8h+arg_38]
0x18021b966  mov     [rsp+3A8h+var_2C0], rax
0x18021b96e  xor     r15d, r15d
0x18021b971  test    rax, rax
0x18021b974  jz      short loc_18021B97E
0x18021b976  test    r14, r14
0x18021b979  jnz     short loc_18021B97E
0x18021b97b  mov     [rax], r15d
0x18021b97e  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x18021b985  lea     rcx, [rsp+3A8h+var_2D8]
0x18021b98d  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18021b993  mov     rbx, rax
0x18021b996  mov     rcx, [rdi]
0x18021b999  mov     rax, [rcx]
0x18021b99c  mov     rcx, rdi
0x18021b99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021b9a4  mov     rdx, rbx
0x18021b9a7  mov     rcx, rax
0x18021b9aa  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18021b9b0  mov     rdx, rax
0x18021b9b3  lea     rcx, [rsp+3A8h+var_180]
0x18021b9bb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18021b9c1  nop
0x18021b9c2  lea     rcx, [rsp+3A8h+var_2D8]
0x18021b9ca  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18021b9d0  lea     rcx, [rsp+3A8h+var_180]
0x18021b9d8  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18021b9de  mov     rcx, rax
0x18021b9e1  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18021b9e7  mov     rdx, rax; lpFileName
0x18021b9ea  lea     rcx, aOsOldPieces; "OS.OLD.Pieces"
0x18021b9f1  call    ?SPReadOSPiecesSection@@YAPEAV?$ArrayList@PEAVCOSPieceInfo@@@UnBCL@@PEBG0@Z; SPReadOSPiecesSection(ushort const *,ushort const *)
0x18021b9f6  mov     rdx, rax
0x18021b9f9  lea     rcx, [rsp+3A8h+var_228]
0x18021ba01  call    ??0?$SmartPtr@V?$ArrayList@PEAVCOSPieceInfo@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVCOSPieceInfo@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>(UnBCL::ArrayList<COSPieceInfo *> *)
0x18021ba06  nop
0x18021ba07  mov     rsi, [rsp+3A8h+var_220]
0x18021ba0f  test    rsi, rsi
0x18021ba12  jz      loc_18021DD58
0x18021ba18  mov     [rsp+3A8h+var_338], r15d
0x18021ba1d  call    cs:__imp_GetLastError
0x18021ba23  mov     edi, eax
0x18021ba25  call    cs:__imp_CurrentIP
0x18021ba2b  mov     rbx, rax
0x18021ba2e  lea     rdx, aFinalListOfSou_0; "Final list of source OS pieces:"
0x18021ba35  mov     ecx, 4000000h; unsigned int
0x18021ba3a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18021ba3f  mov     [rsp+3A8h+var_358], r15d
0x18021ba44  mov     [rsp+3A8h+var_360], r15
0x18021ba49  mov     [rsp+3A8h+var_368], edi
0x18021ba4d  mov     [rsp+3A8h+var_370], rbx
0x18021ba52  lea     rcx, aPprocessjourna; "pProcessJournalEntries"
0x18021ba59  mov     [rsp+3A8h+var_378], rcx
0x18021ba5e  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18021ba65  mov     [rsp+3A8h+var_380], rcx
0x18021ba6a  mov     dword ptr [rsp+3A8h+var_388], 0FBh
0x18021ba72  xor     r9d, r9d
0x18021ba75  lea     r8, aD_0; "D"
0x18021ba7c  mov     edx, 0C8000h
0x18021ba81  mov     rcx, rax
0x18021ba84  call    cs:__imp_WdsSetupLogMessageW
0x18021ba8a  mov     ebx, r15d
0x18021ba8d  lea     rdi, cchOriginalDestLength
0x18021ba94  mov     r13d, 1
0x18021ba9a  lea     r12, aPprocessjourna; "pProcessJournalEntries"
0x18021baa1  lea     r14, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18021baa8  mov     rax, [rsi+8]
0x18021baac  movsxd  rcx, dword ptr [rax+0Ch]
0x18021bab0  add     rcx, 8
0x18021bab4  add     rcx, rsi
0x18021bab7  mov     rax, [rcx]
0x18021baba  mov     rax, [rax]
0x18021babd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bac2  cmp     ebx, eax
0x18021bac4  jge     loc_18021BCA1
0x18021baca  mov     rax, [rsi+8]
0x18021bace  movsxd  rcx, dword ptr [rax+10h]
0x18021bad2  add     rcx, 8
0x18021bad6  add     rcx, rsi
0x18021bad9  mov     rax, [rcx]
0x18021badc  mov     edx, ebx
0x18021bade  mov     rax, [rax+18h]
0x18021bae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bae7  cmp     [rax], r15
0x18021baea  jz      loc_18021BC99
0x18021baf0  call    cs:__imp_GetLastError
0x18021baf6  mov     r15d, eax
0x18021baf9  call    cs:__imp_CurrentIP
0x18021baff  mov     r13, rax
0x18021bb02  mov     rcx, [rsi+8]
0x18021bb06  movsxd  rcx, dword ptr [rcx+10h]
0x18021bb0a  add     rcx, 8
0x18021bb0e  add     rcx, rsi
0x18021bb11  mov     rdx, [rcx]
0x18021bb14  mov     rax, [rdx+18h]
0x18021bb18  mov     edx, ebx
0x18021bb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bb1f  mov     rcx, [rax]
0x18021bb22  lea     rax, aDoNot; "do not "
0x18021bb29  cmp     dword ptr [rcx+50h], 0
0x18021bb2d  cmovz   rdi, rax
0x18021bb31  mov     rax, [rsi+8]
0x18021bb35  movsxd  rcx, dword ptr [rax+10h]
0x18021bb39  add     rcx, 8
0x18021bb3d  add     rcx, rsi
0x18021bb40  mov     rax, [rcx]
0x18021bb43  mov     edx, ebx
0x18021bb45  mov     rax, [rax+18h]
0x18021bb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bb4e  mov     rcx, [rax]
0x18021bb51  mov     rcx, [rcx+48h]
0x18021bb55  mov     rax, [rcx]
0x18021bb58  mov     rax, [rax+10h]
0x18021bb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bb61  mov     rcx, rax
0x18021bb64  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18021bb6a  mov     [rsp+3A8h+var_70], rax
0x18021bb72  mov     rcx, [rsi+8]
0x18021bb76  movsxd  rcx, dword ptr [rcx+10h]
0x18021bb7a  add     rcx, 8
0x18021bb7e  add     rcx, rsi
0x18021bb81  mov     rdx, [rcx]
0x18021bb84  mov     rax, [rdx+18h]
0x18021bb88  mov     edx, ebx
0x18021bb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bb8f  mov     rcx, [rax]
0x18021bb92  add     rcx, 20h ; ' '
0x18021bb96  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18021bb9c  mov     rcx, rax
0x18021bb9f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18021bba5  mov     [rsp+3A8h+var_60], rax
0x18021bbad  mov     rcx, [rsi+8]
0x18021bbb1  movsxd  rcx, dword ptr [rcx+10h]
0x18021bbb5  add     rcx, 8
0x18021bbb9  add     rcx, rsi
0x18021bbbc  mov     rdx, [rcx]
0x18021bbbf  mov     rax, [rdx+18h]
0x18021bbc3  mov     edx, ebx
0x18021bbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bbca  mov     rcx, [rax]
0x18021bbcd  add     rcx, 10h
0x18021bbd1  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18021bbd7  test    rax, rax
0x18021bbda  jz      short loc_18021BC11
0x18021bbdc  mov     rax, [rsi+8]
0x18021bbe0  movsxd  rcx, dword ptr [rax+10h]
0x18021bbe4  add     rcx, 8
0x18021bbe8  add     rcx, rsi
0x18021bbeb  mov     rax, [rcx]
0x18021bbee  mov     edx, ebx
0x18021bbf0  mov     rax, [rax+18h]
0x18021bbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021bbf9  mov     rcx, [rax]
0x18021bbfc  add     rcx, 10h
0x18021bc00  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18021bc06  mov     rcx, rax
0x18021bc09  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18021bc0f  jmp     short loc_18021BC18
0x18021bc11  lea     rax, aNull_6; "<NULL>"
0x18021bc18  mov     [rsp+3A8h+var_380], rdi
0x18021bc1d  mov     rcx, [rsp+3A8h+var_70]
0x18021bc25  mov     [rsp+3A8h+var_388], rcx
0x18021bc2a  mov     r9, [rsp+3A8h+var_60]
0x18021bc32  mov     r8, rax
0x18021bc35  lea     rdx, aNameSOriginalP; "    Name: %s, Original path: %s, Curren"...
0x18021bc3c  mov     ecx, 4000000h; unsigned int
0x18021bc41  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18021bc46  mov     [rsp+3A8h+var_358], 0
0x18021bc4e  mov     [rsp+3A8h+var_360], 0
0x18021bc57  mov     [rsp+3A8h+var_368], r15d
0x18021bc5c  mov     [rsp+3A8h+var_370], r13
0x18021bc61  mov     [rsp+3A8h+var_378], r12
0x18021bc66  mov     [rsp+3A8h+var_380], r14
0x18021bc6b  mov     dword ptr [rsp+3A8h+var_388], 107h
0x18021bc73  xor     r9d, r9d
0x18021bc76  lea     r8, aD_0; "D"
0x18021bc7d  mov     edx, 0C8000h
0x18021bc82  mov     rcx, rax
0x18021bc85  call    cs:__imp_WdsSetupLogMessageW
0x18021bc8b  xor     r15d, r15d
0x18021bc8e  lea     r13d, [r15+1]
0x18021bc92  lea     rdi, cchOriginalDestLength
0x18021bc99  add     ebx, r13d
0x18021bc9c  jmp     loc_18021BAA8
0x18021bca1  mov     ecx, 50h ; 'P'
0x18021bca6  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18021bcac  mov     rbx, rax
0x18021bcaf  mov     r14, [rsp+3A8h+var_58]
0x18021bcb7  mov     r12, [rsp+3A8h+var_68]
0x18021bcbf  mov     [rsp+3A8h+var_70], rax
0x18021bcc7  mov     edi, 80h
0x18021bccc  test    rax, rax
0x18021bccf  jz      short loc_18021BD02
0x18021bcd1  mov     dword ptr [rsp+3A8h+var_378], r13d
0x18021bcd6  mov     dword ptr [rsp+3A8h+var_380], edi
0x18021bcda  mov     dword ptr [rsp+3A8h+var_388], 2
0x18021bce2  lea     r9d, [rdi-7Dh]
0x18021bce6  mov     r8d, r13d
0x18021bce9  mov     rdx, r14
0x18021bcec  mov     rcx, rax
0x18021bcef  call    cs:__imp_??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z; UnBCL::FileStream::FileStream(UnBCL::String const *,UnBCL::FileMode,UnBCL::FileAccess,UnBCL::FileShare,ulong)
0x18021bcf5  lea     r15, ??_SFileStream@UnBCL@@6BObject@1@@; const UnBCL::FileStream::`local vftable'{for `UnBCL::Object'}
0x18021bcfc  mov     [rbx+28h], r15
0x18021bd00  jmp     short loc_18021BD0C
0x18021bd02  mov     rbx, r15
0x18021bd05  lea     r15, ??_SFileStream@UnBCL@@6BObject@1@@; const UnBCL::FileStream::`local vftable'{for `UnBCL::Object'}
0x18021bd0c  mov     rdx, rbx
0x18021bd0f  lea     rcx, [rsp+3A8h+var_170]
0x18021bd17  call    ??0?$SmartPtr@VFileStream@UnBCL@@@UnBCL@@QEAA@PEAVFileStream@1@@Z; UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(UnBCL::FileStream *)
0x18021bd1c  nop
0x18021bd1d  mov     rcx, rdi
0x18021bd20  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18021bd26  mov     rbx, rax
0x18021bd29  mov     [rsp+3A8h+var_70], rax
0x18021bd31  test    rbx, rbx
0x18021bd34  jz      short loc_18021BD7A
0x18021bd36  call    cs:__imp_?GetUnicode@Encoding@UnBCL@@SAPEAV12@XZ; UnBCL::Encoding::GetUnicode(void)
0x18021bd3c  mov     r14, rax
0x18021bd3f  lea     rcx, [rsp+3A8h+var_170]
0x18021bd47  call    ?Steal@?$SmartPtr@V?$Hashtable@PEAVString@UnBCL@@PEAVCDriverInstallInfo@@@UnBCL@@@UnBCL@@QEAAPEAV?$Hashtable@PEAVString@UnBCL@@PEAVCDriverInstallInfo@@@2@XZ; UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(void)
0x18021bd4c  mov     dword ptr [rsp+3A8h+var_378], r13d
0x18021bd51  mov     dword ptr [rsp+3A8h+var_380], r13d
0x18021bd56  mov     dword ptr [rsp+3A8h+var_388], r13d
0x18021bd5b  xor     r9d, r9d
0x18021bd5e  mov     r8, r14
0x18021bd61  mov     rdx, rax
0x18021bd64  mov     rcx, rbx
0x18021bd67  call    cs:__imp_??0StreamWriter@UnBCL@@QEAA@PEAVStream@1@PEAVEncoding@1@HHH@Z; UnBCL::StreamWriter::StreamWriter(UnBCL::Stream *,UnBCL::Encoding *,int,int,int)
0x18021bd6d  lea     r14, ??_SStreamWriter@UnBCL@@6BObject@1@@; const UnBCL::StreamWriter::`local vftable'{for `UnBCL::Object'}
0x18021bd74  mov     [rbx+20h], r14
0x18021bd78  jmp     short loc_18021BD81
0x18021bd7a  lea     r14, ??_SStreamWriter@UnBCL@@6BObject@1@@; const UnBCL::StreamWriter::`local vftable'{for `UnBCL::Object'}
0x18021bd81  mov     rdx, rbx
0x18021bd84  lea     rcx, [rsp+3A8h+var_2A8]
0x18021bd8c  call    ??0?$SmartPtr@VStreamWriter@UnBCL@@@UnBCL@@QEAA@PEAVStreamWriter@1@@Z; UnBCL::SmartPtr<UnBCL::StreamWriter>::SmartPtr<UnBCL::StreamWriter>(UnBCL::StreamWriter *)
0x18021bd91  nop
0x18021bd92  mov     ecx, 50h ; 'P'
0x18021bd97  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18021bd9d  mov     rbx, rax
0x18021bda0  mov     [rsp+3A8h+var_70], rax
0x18021bda8  test    rbx, rbx
0x18021bdab  jz      short loc_18021BDD7
0x18021bdad  mov     dword ptr [rsp+3A8h+var_378], r13d
0x18021bdb2  mov     dword ptr [rsp+3A8h+var_380], edi
0x18021bdb6  mov     dword ptr [rsp+3A8h+var_388], 2
0x18021bdbe  mov     r9d, 3
0x18021bdc4  mov     r8d, r13d
0x18021bdc7  mov     rdx, r12
0x18021bdca  mov     rcx, rax
0x18021bdcd  call    cs:__imp_??0FileStream@UnBCL@@QEAA@PEBVString@1@W4FileMode@1@W4FileAccess@1@W4FileShare@1@K@Z; UnBCL::FileStream::FileStream(UnBCL::String const *,UnBCL::FileMode,UnBCL::FileAccess,UnBCL::FileShare,ulong)
0x18021bdd3  mov     [rbx+28h], r15
0x18021bdd7  mov     rdx, rbx
0x18021bdda  lea     rcx, [rsp+3A8h+var_1A8]
0x18021bde2  call    ??0?$SmartPtr@VFileStream@UnBCL@@@UnBCL@@QEAA@PEAVFileStream@1@@Z; UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(UnBCL::FileStream *)
0x18021bde7  nop
0x18021bde8  mov     rcx, rdi
0x18021bdeb  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18021bdf1  mov     rbx, rax
0x18021bdf4  mov     [rsp+3A8h+var_70], rax
0x18021bdfc  test    rax, rax
0x18021bdff  jz      short loc_18021BE41
0x18021be01  call    cs:__imp_?GetUnicode@Encoding@UnBCL@@SAPEAV12@XZ; UnBCL::Encoding::GetUnicode(void)
0x18021be07  mov     r15, rax
0x18021be0a  lea     rcx, [rsp+3A8h+var_1A8]
0x18021be12  call    ?Steal@?$SmartPtr@V?$Hashtable@PEAVString@UnBCL@@PEAVCDriverInstallInfo@@@UnBCL@@@UnBCL@@QEAAPEAV?$Hashtable@PEAVString@UnBCL@@PEAVCDriverInstallInfo@@@2@XZ; UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(void)
0x18021be17  mov     dword ptr [rsp+3A8h+var_378], r13d
0x18021be1c  mov     dword ptr [rsp+3A8h+var_380], r13d
0x18021be21  mov     dword ptr [rsp+3A8h+var_388], r13d
0x18021be26  xor     r9d, r9d
0x18021be29  mov     r8, r15
0x18021be2c  mov     rdx, rax
0x18021be2f  mov     rcx, rbx
0x18021be32  call    cs:__imp_??0StreamWriter@UnBCL@@QEAA@PEAVStream@1@PEAVEncoding@1@HHH@Z; UnBCL::StreamWriter::StreamWriter(UnBCL::Stream *,UnBCL::Encoding *,int,int,int)
0x18021be38  mov     [rbx+20h], r14
0x18021be3c  xor     r14d, r14d
0x18021be3f  jmp     short loc_18021BE47
0x18021be41  xor     r14d, r14d
0x18021be44  mov     ebx, r14d
  ... truncated ...
```
