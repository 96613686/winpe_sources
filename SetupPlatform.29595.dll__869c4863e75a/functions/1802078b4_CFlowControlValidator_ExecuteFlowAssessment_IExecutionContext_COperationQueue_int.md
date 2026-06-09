# CFlowControlValidator::ExecuteFlowAssessment(IExecutionContext *,COperationQueue *,int)

- ea: `0x1802078b4`
- end: `0x18020a500`
- name: `?ExecuteFlowAssessment@CFlowControlValidator@@IEAAJPEAUIExecutionContext@@PEAVCOperationQueue@@H@Z`
- size: `11340`
- prototype: `int(CFlowControlValidator *__hidden this, struct IExecutionContext *, struct COperationQueue *, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180215830`
- `0x180216f50`

## callees

- `0x180035cc0`
- `0x180057dec`
- `0x18005dd24`
- `0x18012b158`
- `0x1802078b4`
- `0x18020ab54`
- `0x18020abfc`
- `0x18020dba0`
- `0x18021b564`
- `0x1802c6944`
- `0x1802d021c`
- `0x1802d0e40`
- `0x1802d8bfc`
- `0x1802d8e3c`
- `0x1802e1ef4`
- `0x1802e2078`
- `0x1802fb834`
- `0x18032c348`
- `0x18034f794`
- `0x18034f808`
- `0x180363a48`
- `0x1804bbf46`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802079be`
- `KERNEL32!GetLastError` at `0x180207a66`
- `KERNEL32!GetLastError` at `0x180207b02`
- `KERNEL32!GetLastError` at `0x180207ba7`
- `KERNEL32!GetLastError` at `0x180207c49`
- `KERNEL32!GetLastError` at `0x180207d81`
- `KERNEL32!GetLastError` at `0x180207e0f`
- `KERNEL32!GetLastError` at `0x180207e9f`
- `KERNEL32!GetLastError` at `0x180207f90`
- `KERNEL32!GetLastError` at `0x180208094`
- `KERNEL32!GetLastError` at `0x1802081af`
- `KERNEL32!GetLastError` at `0x180208277`
- `KERNEL32!GetLastError` at `0x1802084a1`
- `KERNEL32!GetLastError` at `0x1802085d4`
- `KERNEL32!GetLastError` at `0x1802085e5`
- `KERNEL32!GetLastError` at `0x180208b65`
- `KERNEL32!GetLastError` at `0x180208c7f`
- `KERNEL32!GetLastError` at `0x180208d05`
- `KERNEL32!GetLastError` at `0x180208e8f`
- `KERNEL32!GetLastError` at `0x180209074`
- `KERNEL32!GetLastError` at `0x1802091ea`
- `KERNEL32!GetLastError` at `0x180209378`
- `KERNEL32!GetLastError` at `0x1802093fa`
- `KERNEL32!GetLastError` at `0x18020940b`
- `KERNEL32!GetLastError` at `0x18020947c`
- `KERNEL32!GetLastError` at `0x18020948d`
- `KERNEL32!GetLastError` at `0x180209501`
- `KERNEL32!GetLastError` at `0x1802095aa`
- `KERNEL32!GetLastError` at `0x1802096c9`
- `KERNEL32!GetLastError` at `0x1802097c0`
- `KERNEL32!GetLastError` at `0x180209887`
- `KERNEL32!GetLastError` at `0x18020992d`
- `KERNEL32!GetLastError` at `0x1802099c5`
- `KERNEL32!GetLastError` at `0x180209a4b`
- `KERNEL32!GetLastError` at `0x180209bc7`
- `KERNEL32!GetLastError` at `0x180209c7a`
- `KERNEL32!GetLastError` at `0x180209dfb`
- `KERNEL32!GetLastError` at `0x180209e93`
- `KERNEL32!GetLastError` at `0x180209fcb`
- `KERNEL32!GetLastError` at `0x18020a058`
- `KERNEL32!GetLastError` at `0x18020a1aa`
- `KERNEL32!GetLastError` at `0x18020a237`
- `KERNEL32!GetLastError` at `0x18020a370`
- `KERNEL32!GetLastError` at `0x18020a3fd`
- `KERNEL32!GetLastError` at `0x1802079be`
- `KERNEL32!GetLastError` at `0x180207a66`
- `KERNEL32!GetLastError` at `0x180207b02`
- `KERNEL32!GetLastError` at `0x180207ba7`
- `KERNEL32!GetLastError` at `0x180207c49`
- `KERNEL32!GetLastError` at `0x180207d81`
- `KERNEL32!GetLastError` at `0x180207e0f`
- `KERNEL32!GetLastError` at `0x180207e9f`
- `KERNEL32!GetLastError` at `0x180207f90`
- `KERNEL32!GetLastError` at `0x180208094`
- `KERNEL32!GetLastError` at `0x1802081af`
- `KERNEL32!GetLastError` at `0x180208277`
- `KERNEL32!GetLastError` at `0x1802084a1`
- `KERNEL32!GetLastError` at `0x1802085d4`
- `KERNEL32!GetLastError` at `0x1802085e5`
- `KERNEL32!GetLastError` at `0x180208b65`
- `KERNEL32!GetLastError` at `0x180208c7f`
- `KERNEL32!GetLastError` at `0x180208d05`
- `KERNEL32!GetLastError` at `0x180208e8f`
- `KERNEL32!GetLastError` at `0x180209074`
- `KERNEL32!GetLastError` at `0x1802091ea`
- `KERNEL32!GetLastError` at `0x180209378`
- `KERNEL32!GetLastError` at `0x1802093fa`
- `KERNEL32!GetLastError` at `0x18020940b`
- `KERNEL32!GetLastError` at `0x18020947c`
- `KERNEL32!GetLastError` at `0x18020948d`
- `KERNEL32!GetLastError` at `0x180209501`
- `KERNEL32!GetLastError` at `0x1802095aa`
- `KERNEL32!GetLastError` at `0x1802096c9`
- `KERNEL32!GetLastError` at `0x1802097c0`
- `KERNEL32!GetLastError` at `0x180209887`
- `KERNEL32!GetLastError` at `0x18020992d`
- `KERNEL32!GetLastError` at `0x1802099c5`
- `KERNEL32!GetLastError` at `0x180209a4b`
- `KERNEL32!GetLastError` at `0x180209bc7`
- `KERNEL32!GetLastError` at `0x180209c7a`
- `KERNEL32!GetLastError` at `0x180209dfb`
- `KERNEL32!GetLastError` at `0x180209e93`
- `KERNEL32!GetLastError` at `0x180209fcb`
- `KERNEL32!GetLastError` at `0x18020a058`
- `KERNEL32!GetLastError` at `0x18020a1aa`
- `KERNEL32!GetLastError` at `0x18020a237`
- `KERNEL32!GetLastError` at `0x18020a370`
- `KERNEL32!GetLastError` at `0x18020a3fd`
- `KERNEL32!CreateFileW` at `0x1802092f9`
- `KERNEL32!CreateFileW` at `0x1802092f9`
- `KERNEL32!DeviceIoControl` at `0x18020934b`
- `KERNEL32!DeviceIoControl` at `0x18020934b`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802088d0`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180208935`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802089cc`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180208a30`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802088d0`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180208935`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802089cc`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180208a30`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c00`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c0c`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c00`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c0c`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180208899`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180208899`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802088a7`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802089a5`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802088a7`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802089a5`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802085ad`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802085ad`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x180207df9`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x180209fb5`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x180207df9`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x180209fb5`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802087fb`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18020895e`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180208a59`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802087fb`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18020895e`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180208a59`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802088b3`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802089b0`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802088b3`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802089b0`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1802091c7`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1802091c7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180207951`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18020918f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180207951`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18020918f`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180207d61`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180208b36`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180207d61`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180208b36`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208717`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802087a9`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18020886a`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802088fc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802089f8`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208a87`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208ab5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208add`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208b07`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208717`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802087a9`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18020886a`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802088fc`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802089f8`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208a87`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208ab5`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208add`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180208b07`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802086de`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18020884a`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802086de`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18020884a`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1802086a8`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1802086f3`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18020885f`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1802086a8`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1802086f3`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18020885f`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180208702`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180208702`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18020870d`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c17`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c22`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18020870d`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c17`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180208c22`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180207d52`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020842e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020846e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802084d8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802085a4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802085c5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020888b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020898a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180209047`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802091be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180209b9d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020a178`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020a34e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180207d52`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020842e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020846e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802084d8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802085a4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802085c5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020888b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020898a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180209047`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802091be`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180209b9d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020a178`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18020a34e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180207969`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180207d6d`

## string_xrefs

- `0x180209166`: `Windows.old`
- `0x180208678`: `OsPaths`
- `0x18020977b`: `SysprepComplete`
- `0x18020804c`: `FrameworkApplyComplete`
- `0x180209684`: `FirstBootApplyComplete`
- `0x180209f6d`: `OOBEBootApplyComplete`
- `0x180207a77`: `FLOWTRACK: Flow assessment: New OS image won't be applied before finalize, cannot execute the NEO installation flow.`
- `0x180207a34`: `NewOSWimApplyIncomplete`
- `0x180207bb8`: `FLOWTRACK: Flow assessment: Main offline apply won't be applied before finalize, cannot execute the NEO installation flow.`
- `0x180207b78`: `OfflineApplyIncomplete`
- `0x180207b13`: `FLOWTRACK: Flow assessment: Main offline apply has not completed, cannot execute the NEO flow.`
- `0x1802080a5`: `FLOWTRACK: Flow assessment: Framework apply is not complete, needs to run again, cannot execute the Skip SafeOS boot flow.`
- `0x180207fa1`: `FLOWTRACK: Flow assessment: Offline Sysprep is not complete, needs to run again, cannot execute the Skip SafeOS boot flow.`
- `0x18020831b`: `SymbolicMappingsFound`
- `0x1802081c0`: `FLOWTRACK: Flow assessment: Found symbolic mappings in the configuration file, cannot execute the Skip SafeOS boot flow.`
- `0x18020810a`: `FrameworkApplyIncomplete`
- `0x1802085f5`: `FLOWTRACK: Failed to get NewOS root directory. Error: 0x%08X`
- `0x18020854e`: `OSPiecesOutsideOSVolume`
- `0x1802084ea`: `FLOWTRACK: Flow assessment: Found OS pieces %s outside OS volume, cannot execute the Skip SafeOS boot flow.`
- `0x180208d16`: `FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip SafeOS boot flow.`
- `0x180209512`: `FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip SafeOS boot flow.`
- `0x180208b76`: `FLOWTRACK: Flow assessment: Found non-OS file object in New OS directory, cannot execute the Skip SafeOS boot flow.`
- `0x1802091fb`: `FLOWTRACK: Flow assessment: Found Windows.OLD folder, cannot execute the Skip SafeOS boot flow.`
- `0x18020949a`: `Flow assessment: Cannot open volume for the OS partition (%s). Error: 0x%08X`
- `0x1802097d1`: `FLOWTRACK: Flow assessment: Offline sysprep is not complete, online actions are needed, cannot execute the Skip First boot flow.`
- `0x18020973f`: `FirstBootOfflineApplyIncomplete`
- `0x1802096da`: `FLOWTRACK: Flow assessment: Machine-specific apply is not complete, online actions are needed, cannot execute the Skip First boot flow.`
- `0x1802098fd`: `ICBFirstApplyIncomplete`
- `0x180209898`: `FLOWTRACK: Flow assessment: ICB machine-specific apply exists and has not completed, cannot execute the Skip First boot flow.`
- `0x180209836`: `OfflineSysprepIncomplete`
- `0x180209c40`: `MigratedServiceValidationFailed`
- `0x180209bd8`: `FLOWTRACK: Flow assessment: Cannot validate migrated services, cannot execute the Skip First boot flow.`
- `0x180209a5c`: `FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip First boot flow.`
- `0x180209c8b`: `FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip First boot flow.`
- `0x180209f9e`: `SP_ENV_FORCE_ALL_MIG_COMPLETED`
- `0x18020a069`: `FLOWTRACK: Flow assessment: Machine-independent apply is not complete, online actions are needed, cannot execute the No Online Setup flow.`
- `0x180209fdc`: `FLOWTRACK: Flow assessment: Pretending all migration completed offline due to environment variable.`
- `0x18020a1bb`: `FLOWTRACK: Flow assessment: Cannot validate CBS online installation completion, cannot execute the No Online Setup flow.`
- `0x18020a40e`: `FLOWTRACK: Flow assessment: Respecialize online actions are not complete, cannot execute the No Online Setup flow.`
- `0x18020a381`: `FLOWTRACK: Flow assessment: Cannot validate respecialize completion, cannot execute the No Online Setup flow.`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall CFlowControlValidator::ExecuteFlowAssessment(
        CFlowControlValidator *this,
        struct IExecutionContext *a2,
        struct COperationQueue *a3,
        int a4)
{
  int v4; // esi
  struct IExecutionContext *v6; // r15
  __int64 v8; // r14
  const struct UnBCL::String *v9; // rbx
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  __int64 v12; // rcx
  int v13; // r12d
  DWORD LastError; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  const wchar_t *v17; // r9
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  __int64 v21; // rcx
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  UnBCL::String *v31; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v33; // rax
  const struct UnBCL::String *v34; // rbx
  const struct UnBCL::String *P; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  const struct UnBCL::String *v39; // rax
  int IsEnvironmentVarSetTrue; // ebx
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  struct UnBCL::String *v50; // rax
  int v51; // r8d
  int v52; // ebx
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  UnBCL::String *v56; // rax
  const WCHAR *v57; // rax
  struct CGlobalPath *v58; // rax
  UnBCL::String *v59; // rax
  const WCHAR *v60; // rax
  struct CGlobalPath *v61; // rax
  __int64 v62; // rsi
  DWORD v63; // edi
  __int64 v64; // rbx
  struct tagLOG_PARTIAL_MSG *v65; // rax
  UnBCL::String *v66; // rax
  struct UnBCL::String *v67; // rax
  UnBCL::String *v68; // rax
  struct UnBCL::String *v69; // rax
  DWORD v70; // esi
  __int64 v71; // rdi
  UnBCL::String *v72; // rax
  const char *v73; // rbx
  UnBCL::String *v74; // rax
  const char *v75; // rax
  struct tagLOG_PARTIAL_MSG *v76; // rax
  UnBCL::String *v77; // rax
  const WCHAR *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rsi
  unsigned int k; // edi
  int (__fastcall ***v82)(_QWORD); // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  _QWORD *v85; // rax
  struct UnBCL::String *v86; // rbx
  __int64 v87; // rcx
  _QWORD *v88; // rax
  struct UnBCL::String *v89; // rax
  DWORD v90; // edi
  __int64 v91; // rbx
  __int64 v92; // rcx
  _QWORD *v93; // rax
  UnBCL::String *v94; // rax
  const char *v95; // rax
  struct tagLOG_PARTIAL_MSG *v96; // rax
  const struct UnBCL::String *v97; // rax
  struct UnBCL::String *ParentPath; // rax
  DWORD v99; // edi
  __int64 v100; // rbx
  struct tagLOG_PARTIAL_MSG *v101; // rax
  __int64 v103; // rdx
  __int64 v104; // rdi
  _QWORD *v105; // rax
  _QWORD *v106; // rbx
  __int64 v107; // rax
  int m; // esi
  int (__fastcall ***v109)(_QWORD); // rcx
  __int64 v110; // rcx
  _QWORD *v111; // rax
  __int64 v112; // rax
  UnBCL::String *v113; // rbx
  const struct UnBCL::String *v114; // rax
  _QWORD *v115; // rax
  _QWORD *v116; // rbx
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 Files; // rax
  int n; // edi
  __int64 v121; // rax
  int (__fastcall ***v122)(_QWORD); // rcx
  __int64 v123; // rax
  __int64 v124; // rsi
  UnBCL::String *v125; // rbx
  __int64 v126; // rax
  __int64 v127; // rcx
  const struct UnBCL::String **v128; // rax
  __int64 v129; // rax
  __int64 Directories; // rax
  int ii; // edi
  __int64 v132; // rax
  int (__fastcall ***v133)(_QWORD); // rcx
  __int64 v134; // rax
  __int64 v135; // rsi
  UnBCL::String *v136; // rbx
  __int64 v137; // rax
  __int64 v138; // rcx
  const struct UnBCL::String **v139; // rax
  int v140; // esi
  __int64 v141; // rax
  int (__fastcall ***v142)(_QWORD); // rcx
  int jj; // edi
  __int64 v144; // rax
  int (__fastcall ***v145)(_QWORD); // rcx
  __int64 v146; // rax
  __int64 v147; // rcx
  const struct UnBCL::String *v148; // rbx
  __int64 v149; // rax
  __int64 v150; // rcx
  const struct UnBCL::String **v151; // rax
  DWORD v152; // edi
  __int64 v153; // rbx
  struct tagLOG_PARTIAL_MSG *v154; // rax
  __int64 v155; // rcx
  __int64 v156; // rbx
  unsigned int v157; // esi
  DWORD v158; // edi
  __int64 v159; // rbx
  struct tagLOG_PARTIAL_MSG *v160; // rax
  DWORD v161; // edi
  __int64 v162; // rbx
  struct tagLOG_PARTIAL_MSG *v163; // rax
  int v164; // edi
  int i; // ebx
  int (__fastcall ***v166)(_QWORD); // rcx
  char *v167; // rcx
  __int64 v168; // rax
  _DWORD *v169; // rsi
  __int64 v170; // rcx
  __int64 v171; // r8
  __int64 v172; // rcx
  DWORD v173; // edi
  __int64 v174; // rbx
  struct tagLOG_PARTIAL_MSG *v175; // rax
  __int64 v176; // rcx
  __int64 v177; // rcx
  __int64 v178; // rcx
  __int64 v179; // rcx
  __int64 v180; // rcx
  __int64 v181; // rcx
  __int64 v182; // rcx
  __int64 v183; // rcx
  __int64 v184; // rcx
  __int64 v185; // rcx
  __int64 v186; // rcx
  struct UnBCL::String *v187; // rax
  struct UnBCL::String *v188; // rax
  DWORD v189; // edi
  __int64 v190; // rbx
  struct tagLOG_PARTIAL_MSG *v191; // rax
  UnBCL::String *v192; // rax
  const struct UnBCL::String *v193; // rbx
  const struct UnBCL::String *v194; // rax
  struct UnBCL::String *v195; // rax
  const struct UnBCL::String *v196; // rax
  DWORD v197; // edi
  __int64 v198; // rbx
  struct tagLOG_PARTIAL_MSG *v199; // rax
  UnBCL::String *v200; // rax
  HANDLE FileW; // rax
  DWORD v202; // edi
  __int64 v203; // rbx
  struct tagLOG_PARTIAL_MSG *v204; // rax
  DWORD v205; // edi
  __int64 v206; // rbx
  DWORD v207; // eax
  struct tagLOG_PARTIAL_MSG *v208; // rax
  DWORD v209; // edi
  __int64 v210; // rbx
  DWORD v211; // eax
  struct tagLOG_PARTIAL_MSG *v212; // rax
  DWORD v213; // edi
  __int64 v214; // rbx
  struct tagLOG_PARTIAL_MSG *v215; // rax
  DWORD v216; // edi
  __int64 v217; // rbx
  struct tagLOG_PARTIAL_MSG *v218; // rax
  const wchar_t *v219; // r9
  struct UnBCL::String *v220; // rax
  int v221; // r8d
  int v222; // ebx
  DWORD v223; // edi
  __int64 v224; // rbx
  struct tagLOG_PARTIAL_MSG *v225; // rax
  const wchar_t *v226; // r8
  struct UnBCL::String *v227; // rax
  int v228; // r8d
  int v229; // ebx
  DWORD v230; // edi
  __int64 v231; // rbx
  struct tagLOG_PARTIAL_MSG *v232; // rax
  __int64 v233; // rcx
  DWORD v234; // edi
  __int64 v235; // rbx
  struct tagLOG_PARTIAL_MSG *v236; // rax
  DWORD v237; // edi
  __int64 v238; // rbx
  struct tagLOG_PARTIAL_MSG *v239; // rax
  __int64 v240; // rcx
  __int64 v241; // rbx
  unsigned int v242; // esi
  DWORD v243; // edi
  __int64 v244; // rbx
  struct tagLOG_PARTIAL_MSG *v245; // rax
  DWORD v246; // edi
  __int64 v247; // rbx
  struct tagLOG_PARTIAL_MSG *v248; // rax
  __int64 v249; // rcx
  __int64 v250; // rcx
  __int64 v251; // rcx
  __int64 v252; // rcx
  int v253; // esi
  struct UnBCL::String *v254; // rax
  DWORD v255; // edi
  __int64 v256; // rbx
  struct tagLOG_PARTIAL_MSG *v257; // rax
  int v258; // ebx
  int j; // r12d
  int (__fastcall ***v260)(_QWORD); // rcx
  char *v261; // rcx
  __int64 v262; // rax
  _DWORD *v263; // rsi
  __int64 v264; // rcx
  __int64 v265; // r8
  __int64 v266; // rcx
  DWORD v267; // edi
  __int64 v268; // rbx
  struct tagLOG_PARTIAL_MSG *v269; // rax
  DWORD v270; // edi
  __int64 v271; // rbx
  struct tagLOG_PARTIAL_MSG *v272; // rax
  const wchar_t *v273; // r9
  const wchar_t *v274; // r8
  struct UnBCL::String *v275; // rax
  int v276; // r8d
  int v277; // ebx
  const struct UnBCL::String *v278; // rax
  int v279; // ebx
  DWORD v280; // edi
  __int64 v281; // rbx
  struct tagLOG_PARTIAL_MSG *v282; // rax
  DWORD v283; // edi
  __int64 v284; // rbx
  struct tagLOG_PARTIAL_MSG *v285; // rax
  CFlowControlValidator *v286; // r12
  struct UnBCL::String *v287; // rbx
  struct UnBCL::String *v288; // rax
  struct UnBCL::String *v289; // rax
  struct UnBCL::String *v290; // rdx
  int v291; // [rsp+60h] [rbp-A0h] BYREF
  __int64 OutBuffer; // [rsp+68h] [rbp-98h] BYREF
  void **v293; // [rsp+70h] [rbp-90h] BYREF
  __int64 v294; // [rsp+78h] [rbp-88h]
  void (__fastcall *v295)(__int64, UnBCL::String *); // [rsp+88h] [rbp-78h]
  CFlowControlValidator *v296; // [rsp+90h] [rbp-70h]
  void **v297; // [rsp+98h] [rbp-68h] BYREF
  __int64 v298; // [rsp+A0h] [rbp-60h]
  __int64 v299; // [rsp+A8h] [rbp-58h]
  _BYTE v300[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v301[24]; // [rsp+C0h] [rbp-40h] BYREF
  struct IExecutionContext *v302; // [rsp+D8h] [rbp-28h]
  _BYTE v303[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v304[16]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v305[16]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v306; // [rsp+118h] [rbp+18h]
  _BYTE v307[24]; // [rsp+120h] [rbp+20h] BYREF
  DWORD BytesReturned[2]; // [rsp+138h] [rbp+38h] BYREF
  WCHAR FileName[8]; // [rsp+140h] [rbp+40h] BYREF

  v306 = -2;
  v4 = a4;
  v291 = a4;
  v6 = a2;
  v302 = a2;
  v296 = this;
  if ( a2 && a3 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 64LL))(a2);
    v299 = v8;
    v9 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v307, L"SetupPlatform.ini");
    v10 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v6)(v6);
    v11 = UnBCL::Path::Combine(v10, v9);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v305, v11);
    UnBCL::String::~String((UnBCL::String *)v307);
    if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v6 + 40LL))(v6) < 3 )
      goto LABEL_20;
    if ( !(unsigned int)COperationQueue::IsOperationExecuted(a3, 55) )
    {
      if ( v4 )
      {
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 3);
        LastError = GetLastError();
        v15 = CurrentIP();
        v16 = ConstructPartialMsgW(
                0x4000000u,
                "FLOWTRACK: Flow assessment: New OS image has not been applied, cannot execute the NEO flow.");
        WdsSetupLogMessageW(
          v16,
          819200,
          L"D",
          0,
          3542,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v15,
          LastError,
          0,
          0);
LABEL_7:
        if ( !v8 )
          goto LABEL_115;
        v17 = L"NewOSWimApplyIncomplete";
        goto LABEL_24;
      }
      if ( (int)CFlowControlValidator::GetOperationEarliestExecutionPhase(v12, a3, 55) >= 3 )
      {
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 3);
        v18 = GetLastError();
        v19 = CurrentIP();
        v20 = ConstructPartialMsgW(
                0x4000000u,
                "FLOWTRACK: Flow assessment: New OS image won't be applied before finalize, cannot execute the NEO installation flow.");
        WdsSetupLogMessageW(
          v20,
          819200,
          L"D",
          0,
          3558,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v19,
          v18,
          0,
          0);
        goto LABEL_7;
      }
    }
    if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 65)
      && !(unsigned int)COperationQueue::IsOperationExecuted(a3, 65) )
    {
      if ( v4 )
      {
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 3);
        v22 = GetLastError();
        v23 = CurrentIP();
        v24 = ConstructPartialMsgW(
                0x4000000u,
                "FLOWTRACK: Flow assessment: Main offline apply has not completed, cannot execute the NEO flow.");
        WdsSetupLogMessageW(
          v24,
          819200,
          L"D",
          0,
          3578,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v23,
          v22,
          0,
          0);
LABEL_15:
        if ( !v8 )
          goto LABEL_115;
        v17 = L"OfflineApplyIncomplete";
        goto LABEL_24;
      }
      if ( (int)CFlowControlValidator::GetOperationEarliestExecutionPhase(v21, a3, 65) >= 3 )
      {
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 3);
        v25 = GetLastError();
        v26 = CurrentIP();
        v27 = ConstructPartialMsgW(
                0x4000000u,
                "FLOWTRACK: Flow assessment: Main offline apply won't be applied before finalize, cannot execute the NEO "
                "installation flow.");
        WdsSetupLogMessageW(
          v27,
          819200,
          L"D",
          0,
          3594,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v26,
          v25,
          0,
          0);
        goto LABEL_15;
      }
    }
    if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v6 + 40LL))(v6) < 4 )
    {
LABEL_20:
      v13 = 0;
      goto LABEL_115;
    }
    if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 60) )
    {
      v13 = 0;
      (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
      v28 = GetLastError();
      v29 = CurrentIP();
      v30 = ConstructPartialMsgW(
              0x4000000u,
              "FLOWTRACK: Flow assessment: Data image apply detected, cannot execute the Skip SafeOS boot flow.");
      WdsSetupLogMessageW(
        v30,
        819200,
        L"D",
        0,
        3625,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CFlowControlValidator::ExecuteFlowAssessment",
        v29,
        v28,
        0,
        0);
      if ( !v8 )
        goto LABEL_115;
      v17 = L"DataImageApply";
      goto LABEL_24;
    }
    v13 = 1;
    if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 55) )
    {
      v31 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v305);
      CString = UnBCL::String::get_CString(v31);
      v33 = SPReadConfigValue(L"Actions", L"ApplyEA", CString);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v293, v33);
      v34 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v301, L"Yes");
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v293);
      LODWORD(v34) = UnBCL::String::Compare(P, v34, 1);
      UnBCL::String::~String((UnBCL::String *)v301);
      if ( !(_DWORD)v34 )
      {
        if ( *((int *)this + 22) < 4 )
        {
          v39 = (const struct UnBCL::String *)UnBCL::String::String(
                                                (UnBCL::String *)v301,
                                                L"SP_ENV_FORCE_SKIP_SAFEOS_BOOT");
          IsEnvironmentVarSetTrue = UnBCL::Environment::IsEnvironmentVarSetTrue(v39, 0);
          UnBCL::String::~String((UnBCL::String *)v301);
          if ( IsEnvironmentVarSetTrue )
          {
            v41 = GetLastError();
            v42 = CurrentIP();
            v43 = ConstructPartialMsgW(
                    0x4000000u,
                    "FLOWTRACK: Flow assessment: New OS does not have EAs applied, continuing on optimized flow due to fo"
                    "rce environment variable.");
            WdsSetupLogMessageW(
              v43,
              819200,
              L"D",
              0,
              3646,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"CFlowControlValidator::ExecuteFlowAssessment",
              v42,
              v41,
              0,
              0);
          }
          else
          {
            v13 = 0;
            (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
            v44 = GetLastError();
            v45 = CurrentIP();
            v46 = ConstructPartialMsgW(
                    0x4000000u,
                    "FLOWTRACK: Flow assessment: New OS does not have EAs applied, cannot execute the Skip SafeOS boot flow.");
            WdsSetupLogMessageW(
              v46,
              819200,
              L"D",
              0,
              3652,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"CFlowControlValidator::ExecuteFlowAssessment",
              v45,
              v44,
              0,
              0);
            if ( v8 )
              (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
                v8,
                L"SP_VALIDATOR_INFO",
                L"WinreBootReason",
                L"MissingEAsNewOS");
          }
        }
        else
        {
          v36 = GetLastError();
          v37 = CurrentIP();
          v38 = ConstructPartialMsgW(
                  0x4000000u,
                  "FLOWTRACK: Flow assessment: New OS does not have EAs applied, continuing on optimized flow due to flow"
                  " constraint request.");
          WdsSetupLogMessageW(
            v38,
            819200,
            L"D",
            0,
            3641,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CFlowControlValidator::ExecuteFlowAssessment",
            v37,
            v36,
            0,
            0);
        }
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v293);
      if ( !v13 )
        goto LABEL_115;
    }
    if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 64)
      && v4
      && !(unsigned int)COperationQueue::IsOperationExecuted(a3, 64) )
    {
      v13 = 0;
      (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
      v47 = GetLastError();
      v48 = CurrentIP();
      v49 = ConstructPartialMsgW(
              0x4000000u,
              "FLOWTRACK: Flow assessment: Offline Sysprep is not complete, needs to run again, cannot execute the Skip S"
              "afeOS boot flow.");
      WdsSetupLogMessageW(
        v49,
        819200,
        L"D",
        0,
        3671,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CFlowControlValidator::ExecuteFlowAssessment",
        v48,
        v47,
        0,
        0);
      if ( v8 )
      {
        v17 = L"OfflineSysprepNotExecuted";
LABEL_24:
        (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
          v8,
          L"SP_VALIDATOR_INFO",
          L"WinreBootReason",
          v17);
        goto LABEL_115;
      }
      goto LABEL_115;
    }
    if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 62) )
    {
      if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 62) )
      {
        if ( v4 )
        {
          v50 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v293, L"FrameworkApplyComplete");
          v52 = SPGetStoredBOOL(v6, v50, v51);
          UnBCL::String::~String((UnBCL::String *)&v293);
          if ( !v52 )
          {
            v13 = 0;
            (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
            v53 = GetLastError();
            v54 = CurrentIP();
            v55 = ConstructPartialMsgW(
                    0x4000000u,
                    "FLOWTRACK: Flow assessment: Framework apply is not complete, needs to run again, cannot execute the "
                    "Skip SafeOS boot flow.");
            WdsSetupLogMessageW(
              v55,
              819200,
              L"D",
              0,
              3690,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"CFlowControlValidator::ExecuteFlowAssessment",
              v54,
              v53,
              0,
              0);
            if ( v8 )
            {
              v17 = L"FrameworkApplyIncomplete";
              goto LABEL_24;
            }
LABEL_115:
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::GetImpl'::`2'::impl) )
            {
              if ( !v13 )
                goto LABEL_210;
              if ( v4 )
              {
                v164 = 1;
                for ( i = 0; ; ++i )
                {
                  LODWORD(OutBuffer) = i;
                  v166 = (int (__fastcall ***)(_QWORD))((char *)a3 + *(int *)(*((_QWORD *)a3 + 1) + 12LL) + 8);
                  if ( i >= (**v166)(v166) )
                    break;
                  v167 = (char *)a3 + *(int *)(*((_QWORD *)a3 + 1) + 16LL) + 8;
                  v168 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v167 + 24LL))(v167, (unsigned int)i);
                  v169 = *(_DWORD **)v168;
                  if ( !*(_DWORD *)(*(_QWORD *)v168 + 48LL) && !v169[11] && !v169[9] )
                  {
                    LODWORD(v170) = 0;
                    v171 = (unsigned int)v169[18];
                    while ( (_DWORD)v171 != dword_1805C44C0[(unsigned int)v170] )
                    {
                      v170 = (unsigned int)(v170 + 1);
                      if ( (int)v170 >= 11 )
                      {
                        if ( (unsigned int)CFlowControlValidator::GetOperationEarliestExecutionPhase(v170, a3, v171) == 4
                          && (int)CFlowControlValidator::GetOperationLatestExecutionPhase(
                                    v172,
                                    a3,
                                    (unsigned int)v169[18]) <= 4 )
                        {
                          v173 = GetLastError();
                          v174 = CurrentIP();
                          v175 = ConstructPartialMsgW(
                                   0x4000000u,
                                   "FLOWTRACK: Flow assessment: Found operation that needs to run in SafeOS phase (%d)",
                                   v169[18]);
                          WdsSetupLogMessageW(
                            v175,
                            819200,
                            L"D",
                            0,
                            4006,
                            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                            L"CFlowControlValidator::ExecuteFlowAssessment",
                            v174,
                            v173,
                            0,
                            0);
                          v164 = 0;
                          i = OutBuffer;
                        }
                        break;
                      }
                    }
                  }
                }
                v8 = v299;
                v6 = v302;
                if ( !v164 )
                {
                  v13 = 0;
                  (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v302 + 48LL))(v302, 4);
                  v216 = GetLastError();
                  v217 = CurrentIP();
                  v218 = ConstructPartialMsgW(
                           0x4000000u,
                           "FLOWTRACK: Flow assessment: Found one or more operations that need to run in SafeOS phase, ca"
                           "nnot execute the Skip SafeOS boot flow.");
                  WdsSetupLogMessageW(
                    v218,
                    819200,
                    L"D",
                    0,
                    4016,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                    L"CFlowControlValidator::ExecuteFlowAssessment",
                    v217,
                    v216,
                    0,
                    0);
                  if ( v8 )
                  {
                    v219 = L"NonEmptySafeOSQueue";
LABEL_208:
                    v226 = L"WinreBootReason";
                    goto LABEL_209;
                  }
                  goto LABEL_210;
                }
                v4 = v291;
              }
            }
            else if ( !v13 )
            {
              goto LABEL_210;
            }
            if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v6 + 40LL))(v6) < 5 )
            {
              v13 = 0;
              goto LABEL_210;
            }
            if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 65) )
            {
              if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 65) )
              {
                v220 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v303, L"FirstBootApplyComplete");
                v222 = SPGetStoredBOOL(v6, v220, v221);
                UnBCL::String::~String((UnBCL::String *)v303);
                if ( !v222 )
                {
                  v13 = 0;
                  (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 5);
                  v223 = GetLastError();
                  v224 = CurrentIP();
                  v225 = ConstructPartialMsgW(
                           0x4000000u,
                           "FLOWTRACK: Flow assessment: Machine-specific apply is not complete, online actions are needed"
                           ", cannot execute the Skip First boot flow.");
                  WdsSetupLogMessageW(
                    v225,
                    819200,
                    L"D",
                    0,
                    4047,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                    L"CFlowControlValidator::ExecuteFlowAssessment",
                    v224,
                    v223,
                    0,
                    0);
                  if ( !v8 )
                    goto LABEL_210;
                  v219 = L"FirstBootOfflineApplyIncomplete";
LABEL_174:
                  v226 = L"FirstBootReason";
LABEL_209:
                  (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
                    v8,
                    L"SP_VALIDATOR_INFO",
                    v226,
                    v219);
                  goto LABEL_210;
                }
              }
            }
            if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 64) )
            {
              if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 64) )
              {
                v227 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v303, L"SysprepComplete");
                v229 = SPGetStoredBOOL(v6, v227, v228);
                UnBCL::String::~String((UnBCL::String *)v303);
                if ( !v229 )
                {
                  v13 = 0;
                  (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 5);
                  v230 = GetLastError();
                  v231 = CurrentIP();
                  v232 = ConstructPartialMsgW(
                           0x4000000u,
                           "FLOWTRACK: Flow assessment: Offline sysprep is not complete, online actions are needed, canno"
                           "t execute the Skip First boot flow.");
                  WdsSetupLogMessageW(
                    v232,
                    819200,
                    L"D",
                    0,
                    4065,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                    L"CFlowControlValidator::ExecuteFlowAssessment",
                    v231,
                    v230,
                    0,
                    0);
                  if ( !v8 )
                    goto LABEL_210;
                  v219 = L"OfflineSysprepIncomplete";
                  goto LABEL_174;
                }
              }
            }
            if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 146)
              && !(unsigned int)COperationQueue::IsOperationExecuted(a3, 146) )
            {
              if ( v4 )
              {
                v13 = 0;
                (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 5);
                v234 = GetLastError();
                v235 = CurrentIP();
                v236 = ConstructPartialMsgW(
                         0x4000000u,
                         "FLOWTRACK: Flow assessment: ICB machine-specific apply exists and has not completed, cannot exe"
                         "cute the Skip First boot flow.");
                WdsSetupLogMessageW(
                  v236,
                  819200,
                  L"D",
                  0,
                  4083,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                  L"CFlowControlValidator::ExecuteFlowAssessment",
                  v235,
                  v234,
                  0,
                  0);
                goto LABEL_184;
              }
              if ( (int)CFlowControlValidator::GetOperationEarliestExecutionPhase(v233, a3, 146) >= 3 )
              {
                v13 = 0;
                (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 5);
                v237 = GetLastError();
                v238 = CurrentIP();
                v239 = ConstructPartialMsgW(
                         0x4000000u,
                         "FLOWTRACK: Flow assessment: ICB machine-specific apply won't be applied before finalize, cannot"
                         " execute the Skip First boot flow.");
                WdsSetupLogMessageW(
                  v239,
                  819200,
                  L"D",
                  0,
                  4099,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                  L"CFlowControlValidator::ExecuteFlowAssessment",
                  v238,
                  v237,
                  0,
                  0);
LABEL_184:
                if ( v8 )
                {
                  v219 = L"ICBFirstApplyIncomplete";
                  goto LABEL_208;
                }
LABEL_210:
                v253 = v291;
                goto LABEL_211;
              }
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::GetImpl'::`2'::impl) )
            {
              v241 = 0;
              while ( 1 )
              {
                v242 = dword_1805C44A0[v241];
                if ( !(unsigned int)CFlowControlValidator::IsOperationRemovable(&_ImageBase, a3, v242) )
                  break;
                v241 = (unsigned int)(v241 + 1);
                if ( (int)v241 >= 5 )
                  goto LABEL_195;
              }
              v243 = GetLastError();
              v244 = CurrentIP();
              v245 = ConstructPartialMsgW(
                       0x4000000u,
                       "FLOWTRACK: Flow assessment: Operation %d is not removable.",
                       v242);
              WdsSetupLogMessageW(
                v245,
                819200,
                L"D",
                0,
                4120,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"CFlowControlValidator::ExecuteFlowAssessment",
                v244,
                v243,
                0,
                0);
              v13 = 0;
              (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 5);
              v246 = GetLastError();
              v247 = CurrentIP();
              v248 = ConstructPartialMsgW(
                       0x4000000u,
                       "FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip"
                       " First boot flow.");
              WdsSetupLogMessageW(
                v248,
                819200,
                L"D",
                0,
                4129,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"CFlowControlValidator::ExecuteFlowAssessment",
                v247,
                v246,
                0,
                0);
              if ( !v8 )
                goto LABEL_210;
              (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
                v8,
                L"SP_VALIDATOR_INFO",
                L"WinreBootReason",
                L"PendingOperations");
LABEL_195:
              if ( !v13 )
                goto LABEL_210;
            }
            else if ( !(unsigned int)CFlowControlValidator::IsOperationRemovable(v240, a3, 125)
                   || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v249, a3, 139)
                   || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v250, a3, 141)
                   || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v251, a3, 155)
                   || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v252, a3, 145) )
            {
              v13 = 0;
              (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 5);
              v255 = GetLastError();
              v256 = CurrentIP();
              v257 = ConstructPartialMsgW(
                       0x4000000u,
                       "FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip"
                       " First boot flow.");
              WdsSetupLogMessageW(
                v257,
                819200,
                L"D",
                0,
                4147,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"CFlowControlValidator::ExecuteFlowAssessment",
                v256,
                v255,
                0,
                0);
              if ( v8 )
              {
                v219 = L"PendingOperations";
                goto LABEL_208;
              }
              goto LABEL_210;
            }
            if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 65) )
            {
              v253 = v291;
              if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 65) && v291 )
              {
                v254 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v296 + 72);
                SPValidateMigratedServices(v254);
              }
LABEL_211:
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::GetImpl'::`2'::impl) )
              {
                if ( !v13 )
                  goto LABEL_254;
                if ( v253 )
                {
                  v258 = 1;
                  for ( j = 0; ; ++j )
                  {
                    v260 = (int (__fastcall ***)(_QWORD))((char *)a3 + *(int *)(*((_QWORD *)a3 + 1) + 12LL) + 8);
                    if ( j >= (**v260)(v260) )
                      break;
                    v261 = (char *)a3 + *(int *)(*((_QWORD *)a3 + 1) + 16LL) + 8;
                    v262 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v261 + 24LL))(v261, (unsigned int)j);
                    v263 = *(_DWORD **)v262;
                    if ( !*(_DWORD *)(*(_QWORD *)v262 + 48LL) && !v263[11] && !v263[9] )
                    {
                      v264 = 0;
                      v265 = (unsigned int)v263[18];
                      while ( (_DWORD)v265 != dword_1805C44A0[v264] )
                      {
                        v264 = (unsigned int)(v264 + 1);
                        if ( (int)v264 >= 5 )
                        {
                          if ( (unsigned int)CFlowControlValidator::GetOperationEarliestExecutionPhase(v264, a3, v265)
                             - 5 <= 3
                            && (unsigned int)CFlowControlValidator::GetOperationLatestExecutionPhase(
                                               v266,
                                               a3,
                                               (unsigned int)v263[18])
                             - 5 <= 3 )
                          {
                            v267 = GetLastError();
                            v268 = CurrentIP();
                            v269 = ConstructPartialMsgW(
                                     0x4000000u,
                                     "FLOWTRACK: Flow assessment: Found operation that needs to run in First boot phase (%d)",
                                     v263[18]);
                            WdsSetupLogMessageW(
                              v269,
                              819200,
                              L"D",
                              0,
                              4223,
                              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                              L"CFlowControlValidator::ExecuteFlowAssessment",
                              v268,
                              v267,
                              0,
                              0);
                            v258 = 0;
                          }
                          break;
                        }
                      }
                    }
                  }
                  v8 = v299;
                  v6 = v302;
                  if ( !v258 )
                  {
                    (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v302 + 48LL))(v302, 5);
                    v270 = GetLastError();
                    v271 = CurrentIP();
                    v272 = ConstructPartialMsgW(
                             0x4000000u,
                             "FLOWTRACK: Flow assessment: Found one or more operations that need to run in First boot pha"
                             "se, cannot execute the Skip First boot flow.");
                    WdsSetupLogMessageW(
                      v272,
                      819200,
                      L"D",
                      0,
                      4233,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                      L"CFlowControlValidator::ExecuteFlowAssessment",
                      v271,
                      v270,
                      0,
                      0);
                    if ( v8 )
                    {
                      v273 = L"NonEmptyFirstBootQueue";
                      v274 = L"FirstBootReason";
LABEL_238:
                      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
                        v8,
                        L"SP_VALIDATOR_INFO",
                        v274,
                        v273);
                      goto LABEL_254;
                    }
                    goto LABEL_254;
                  }
                }
              }
              else if ( !v13 )
              {
                goto LABEL_254;
              }
              if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v6 + 40LL))(v6) < 6 )
                goto LABEL_254;
              if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 65) )
              {
                if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 65) )
                {
                  v275 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v303, L"OOBEBootApplyComplete");
                  v277 = SPGetStoredBOOL(v6, v275, v276);
                  UnBCL::String::~String((UnBCL::String *)v303);
                  if ( !v277 )
                  {
                    v278 = (const struct UnBCL::String *)UnBCL::String::String(
                                                           (UnBCL::String *)v303,
                                                           L"SP_ENV_FORCE_ALL_MIG_COMPLETED");
                    v279 = UnBCL::Environment::IsEnvironmentVarSetTrue(v278, 0);
                    UnBCL::String::~String((UnBCL::String *)v303);
                    if ( !v279 )
                    {
                      (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 6);
                      v283 = GetLastError();
                      v284 = CurrentIP();
                      v285 = ConstructPartialMsgW(
                               0x4000000u,
                               "FLOWTRACK: Flow assessment: Machine-independent apply is not complete, online actions are"
                               " needed, cannot execute the No Online Setup flow.");
                      WdsSetupLogMessageW(
                        v285,
                        819200,
                        L"D",
                        0,
                        4270,
                        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                        L"CFlowControlValidator::ExecuteFlowAssessment",
                        v284,
                        v283,
                        0,
                        0);
                      if ( v8 )
                      {
                        v273 = L"OOBEBootApplyActive";
                        v274 = L"FlowConstraintReason";
                        goto LABEL_238;
                      }
LABEL_254:
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v305);
                      return 0;
                    }
                    v280 = GetLastError();
                    v281 = CurrentIP();
                    v282 = ConstructPartialMsgW(
                             0x4000000u,
                             "FLOWTRACK: Flow assessment: Pretending all migration completed offline due to environment variable.");
                    WdsSetupLogMessageW(
                      v282,
                      819200,
                      L"D",
                      0,
                      4264,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                      L"CFlowControlValidator::ExecuteFlowAssessment",
                      v281,
                      v280,
                      0,
                      0);
                  }
                }
              }
              if ( (unsigned int)COperationQueue::IsOperationExecuted(a3, 55)
                && (!(unsigned int)COperationQueue::IsOperationPresent(a3, 37)
                 || (unsigned int)COperationQueue::IsOperationExecuted(a3, 37)) )
              {
                v291 = 0;
                v286 = v296;
                if ( !*((_DWORD *)v296 + 23) )
                {
                  v287 = (struct UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v6 + 24LL))(v6);
                  v288 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v286 + 72);
                  SPEvaluateCBSCompletionStatus(v288, v287, 0, &v291, 0);
                }
                v291 = *((_DWORD *)v296 + 24);
                if ( !v291 )
                {
LABEL_253:
                  (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 6);
                  goto LABEL_254;
                }
              }
              else
              {
                v286 = v296;
              }
              if ( !(unsigned int)COperationQueue::IsOperationPresent(a3, 64)
                || !(unsigned int)COperationQueue::IsOperationExecuted(a3, 64) )
              {
                goto LABEL_254;
              }
              LODWORD(OutBuffer) = 0;
              if ( !*((_DWORD *)v286 + 25) )
              {
                v291 = 0;
                (*(void (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)v6 + 24LL))(v6);
                v289 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v286 + 72);
                SPEvaluateRespecializeCompletionStatus(v289, v290, (int *)&OutBuffer, &v291);
              }
              if ( *((_DWORD *)v286 + 26) )
                goto LABEL_254;
              goto LABEL_253;
            }
            goto LABEL_210;
          }
        }
      }
    }
    v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v305);
    v57 = UnBCL::String::get_CString(v56);
    v58 = SPReadConfigGlobalPath(L"WindowsOld.Mappings", L"Source0", v57);
    UnBCL::SmartPtr<CGlobalPath>::SmartPtr<CGlobalPath>(&v297, v58);
    v59 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v305);
    v60 = UnBCL::String::get_CString(v59);
    v61 = SPReadConfigGlobalPath(L"WindowsOld.Mappings", L"Destination0", v60);
    UnBCL::SmartPtr<CGlobalPath>::SmartPtr<CGlobalPath>(&v293, v61);
    v62 = v294;
    if ( v298 || v294 )
    {
      v13 = 0;
      (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
      v63 = GetLastError();
      v64 = CurrentIP();
      v65 = ConstructPartialMsgW(
              0x4000000u,
              "FLOWTRACK: Flow assessment: Found symbolic mappings in the configuration file, cannot execute the Skip SafeOS boot flow.");
      WdsSetupLogMessageW(
        v65,
        819200,
        L"D",
        0,
        3712,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CFlowControlValidator::ExecuteFlowAssessment",
        v64,
        v63,
        0,
        0);
      v66 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v298 + 16LL))(v298);
      v67 = UnBCL::String::TrimEnd(v66, L"\\ ");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v300, v67);
      v68 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v69 = UnBCL::String::TrimEnd(v68, L"\\ ");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v301, v69);
      v70 = GetLastError();
      v71 = CurrentIP();
      v72 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v301);
      v73 = (const char *)UnBCL::String::get_CString(v72);
      v74 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v300);
      v75 = (const char *)UnBCL::String::get_CString(v74);
      v76 = ConstructPartialMsgW(0x4000000u, "Flow assessment: Mapping found: %s -> %s", v75, v73);
      WdsSetupLogMessageW(
        v76,
        819200,
        L"D",
        0,
        3715,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CFlowControlValidator::ExecuteFlowAssessment",
        v71,
        v70,
        0,
        0);
      if ( v8 )
        (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
          v8,
          L"SP_VALIDATOR_INFO",
          L"WinreBootReason",
          L"SymbolicMappingsFound");
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v301);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v300);
    }
    v293 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v293);
    v297 = &UnBCL::SmartPtr<CGlobalPath>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v297);
    if ( v13 )
    {
      v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v305);
      v78 = UnBCL::String::get_CString(v77);
      v79 = SPReadOSPiecesSection(L"OS.OLD.Pieces", v78);
      UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>(&v293, v79);
      v80 = v294;
      if ( v294 )
      {
        for ( k = 0; ; ++k )
        {
          LODWORD(OutBuffer) = k;
          v82 = (int (__fastcall ***)(_QWORD))(v80 + *(int *)(*(_QWORD *)(v80 + 8) + 12LL) + 8LL);
          if ( (int)k >= (**v82)(v82) )
            break;
          v83 = v80 + *(int *)(*(_QWORD *)(v80 + 8) + 16LL) + 8LL;
          if ( *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 24LL))(v83, k) )
          {
            v84 = v80 + *(int *)(*(_QWORD *)(v80 + 8) + 16LL) + 8LL;
            v85 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v84 + 24LL))(v84, k);
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P(*v85 + 32LL) )
            {
              v86 = (struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v6)(v6);
              v87 = v80 + *(int *)(*(_QWORD *)(v80 + 8) + 16LL) + 8LL;
              v88 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 24LL))(v87, k);
              v89 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v88 + 32LL);
              if ( !SPArePathsOnSameVolume(v89, v86) )
              {
                v13 = 0;
                (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
                v90 = GetLastError();
                v91 = CurrentIP();
                v92 = v80 + *(int *)(*(_QWORD *)(v80 + 8) + 16LL) + 8LL;
                v93 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v92 + 24LL))(
                                  v92,
                                  (unsigned int)OutBuffer);
                v94 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v93 + 32LL);
                v95 = (const char *)UnBCL::String::get_CString(v94);
                v96 = ConstructPartialMsgW(
                        0x4000000u,
                        "FLOWTRACK: Flow assessment: Found OS pieces %s outside OS volume, cannot execute the Skip SafeOS boot flow.",
                        v95);
                WdsSetupLogMessageW(
                  v96,
                  819200,
                  L"D",
                  0,
                  3742,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                  L"CFlowControlValidator::ExecuteFlowAssessment",
                  v91,
                  v90,
                  0,
                  0);
                if ( v8 )
                  (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
                    v8,
                    L"SP_VALIDATOR_INFO",
                    L"WinreBootReason",
                    L"OSPiecesOutsideOSVolume");
                break;
              }
            }
          }
        }
      }
      v293 = (void **)&UnBCL::SmartPtr<UnBCL::ArrayList<COSPieceInfo *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v293);
      v4 = v291;
      if ( !v13 )
        goto LABEL_115;
      if ( v291 )
      {
        v97 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v296 + 72);
        ParentPath = UnBCL::Path::GetParentPath(v97);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, ParentPath);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v297) )
        {
          v99 = GetLastError();
          v100 = CurrentIP();
          GetLastError();
          v101 = ConstructPartialMsgW(
                   0x2000000u,
                   "FLOWTRACK: Failed to get NewOS root directory. Error: 0x%08X",
                   (unsigned int)"CFlowControlValidator::ExecuteFlowAssessment");
          WdsSetupLogMessageW(
            v101,
            819200,
            L"D",
            0,
            3763,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CFlowControlValidator::ExecuteFlowAssessment",
            v100,
            v99,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v305);
          return 2147500037LL;
        }
        v103 = UnBCL::String::String((UnBCL::String *)v303, L"OsPaths");
        v104 = SPGetStoredObjectsGroup(v6, v103);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v300, 0);
        if ( v104 )
        {
          v105 = UnBCL::Object::operator new(0xB0u);
          v106 = v105;
          v295 = (void (__fastcall *)(__int64, UnBCL::String *))v105;
          if ( v105 )
          {
            UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v105, 1);
            v106[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
          }
          else
          {
            v106 = 0;
          }
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(
            FileName,
            v106);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v300, FileName);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(FileName);
          v107 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v300);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v107 + 40LL))(v107, 1);
          for ( m = 0; ; ++m )
          {
            v109 = (int (__fastcall ***)(_QWORD))(v104 + *(int *)(*(_QWORD *)(v104 + 8) + 12LL) + 8LL);
            if ( m >= (**v109)(v109) )
              break;
            v110 = v104 + *(int *)(*(_QWORD *)(v104 + 8) + 16LL) + 8LL;
            v111 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v110 + 24LL))(
                               v110,
                               (unsigned int)m);
            *(_QWORD *)BytesReturned = _RTDynamicCast_0(
                                         *v111,
                                         0,
                                         &UnBCL::ISerializable `RTTI Type Descriptor',
                                         &CStoredString `RTTI Type Descriptor',
                                         0);
            if ( *(_QWORD *)BytesReturned )
            {
              v112 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v300);
              OutBuffer = *(int *)(*(_QWORD *)(v112 + 8) + 16LL) + 8LL + v112;
              v295 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)OutBuffer + 40LL);
              v113 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
              *(_QWORD *)FileName = v113;
              if ( v113 )
              {
                v114 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)BytesReturned + 8LL))(*(_QWORD *)BytesReturned);
                UnBCL::String::String(v113, v114);
                *(_QWORD *)v113 = &UnBCL::String::`local vftable';
              }
              else
              {
                v113 = 0;
              }
              v295(OutBuffer, v113);
            }
          }
          v8 = v299;
        }
        v115 = UnBCL::Object::operator new(0xB0u);
        v116 = v115;
        *(_QWORD *)FileName = v115;
        if ( v115 )
        {
          UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v115, 1);
          v116[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
        }
        else
        {
          v116 = 0;
        }
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v304, v116);
        v117 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v304);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v117 + 40LL))(v117, 1);
        v118 = UnBCL::SmartPtr<UnBCL::String>::get_P(&v297);
        Files = UnBCL::Directory::GetFiles(v118, 0, 0);
        UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(&v293, Files);
        if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(&v293) )
        {
          for ( n = 0; ; ++n )
          {
            v121 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(&v293);
            v122 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v121 + 8) + 12LL) + v121 + 8);
            if ( n >= (**v122)(v122) )
              break;
            v123 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v304);
            v124 = v123 + *(int *)(*(_QWORD *)(v123 + 8) + 16LL);
            v295 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v124 + 8) + 40LL);
            v125 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            *(_QWORD *)FileName = v125;
            if ( v125 )
            {
              v126 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(&v293);
              v127 = *(int *)(*(_QWORD *)(v126 + 8) + 16LL) + v126 + 8;
              v128 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 24LL))(
                                                      v127,
                                                      (unsigned int)n);
              UnBCL::String::String(v125, *v128);
              *(_QWORD *)v125 = &UnBCL::String::`local vftable';
            }
            else
            {
              v125 = 0;
            }
            v295(v124 + 8, v125);
          }
          v6 = v302;
        }
        v129 = UnBCL::SmartPtr<UnBCL::String>::get_P(&v297);
        Directories = UnBCL::Directory::GetDirectories(v129, 0, 0);
        UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v301, Directories);
        if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(v301) )
        {
          for ( ii = 0; ; ++ii )
          {
            v132 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v301);
            v133 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v132 + 8) + 12LL) + v132 + 8);
            if ( ii >= (**v133)(v133) )
              break;
            v134 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v304);
            v135 = v134 + *(int *)(*(_QWORD *)(v134 + 8) + 16LL);
            v295 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v135 + 8) + 40LL);
            v136 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            *(_QWORD *)FileName = v136;
            if ( v136 )
            {
              v137 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v301);
              v138 = *(int *)(*(_QWORD *)(v137 + 8) + 16LL) + v137 + 8;
              v139 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v138 + 24LL))(
                                                      v138,
                                                      (unsigned int)ii);
              UnBCL::String::String(v136, *v139);
              *(_QWORD *)v136 = &UnBCL::String::`local vftable';
            }
            else
            {
              v136 = 0;
            }
            v295(v135 + 8, v136);
          }
          v8 = v299;
        }
        v140 = 0;
LABEL_97:
        v141 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v304);
        v142 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v141 + 8) + 12LL) + v141 + 8);
        if ( v140 < (**v142)(v142) )
        {
          for ( jj = 0; ; ++jj )
          {
            v144 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v300);
            v145 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v144 + 8) + 12LL) + v144 + 8);
            if ( jj >= (**v145)(v145) )
              break;
            v146 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v300);
            v147 = *(int *)(*(_QWORD *)(v146 + 8) + 16LL) + v146 + 8;
            v148 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v147 + 24LL))(
                                                     v147,
                                                     (unsigned int)jj);
            v149 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v304);
            v150 = *(int *)(*(_QWORD *)(v149 + 8) + 16LL) + v149 + 8;
            v151 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v150 + 24LL))(
                                                    v150,
                                                    (unsigned int)v140);
            if ( !UnBCL::String::Compare(*v151, v148, 1) )
            {
              ++v140;
              goto LABEL_97;
            }
          }
          v13 = 0;
          (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
          v152 = GetLastError();
          v153 = CurrentIP();
          v154 = ConstructPartialMsgW(
                   0x4000000u,
                   "FLOWTRACK: Flow assessment: Found non-OS file object in New OS directory, cannot execute the Skip SafeOS boot flow.");
          WdsSetupLogMessageW(
            v154,
            819200,
            L"D",
            0,
            3819,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CFlowControlValidator::ExecuteFlowAssessment",
            v153,
            v152,
            0,
            0);
          if ( v8 )
            (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
              v8,
              L"SP_VALIDATOR_INFO",
              L"WinreBootReason",
              L"NonOSFileObjects");
        }
        UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v301);
        UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(&v293);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v304);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v300);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
        v4 = v291;
        if ( !v13 )
          goto LABEL_115;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::GetImpl'::`2'::impl) )
      {
        v156 = 0;
        while ( 1 )
        {
          v157 = dword_1805C44C0[v156];
          if ( !(unsigned int)CFlowControlValidator::IsOperationRemovable(&_ImageBase, a3, v157) )
            break;
          v156 = (unsigned int)(v156 + 1);
          if ( (int)v156 >= 11 )
            goto LABEL_113;
        }
        v158 = GetLastError();
        v159 = CurrentIP();
        v160 = ConstructPartialMsgW(0x4000000u, "FLOWTRACK: Flow assessment: Operation %d is not removable.", v157);
        WdsSetupLogMessageW(
          v160,
          819200,
          L"D",
          0,
          3840,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v159,
          v158,
          0,
          0);
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
        v161 = GetLastError();
        v162 = CurrentIP();
        v163 = ConstructPartialMsgW(
                 0x4000000u,
                 "FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip SafeOS boot flow.");
        WdsSetupLogMessageW(
          v163,
          819200,
          L"D",
          0,
          3849,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v162,
          v161,
          0,
          0);
        if ( !v8 )
          goto LABEL_114;
        (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
          v8,
          L"SP_VALIDATOR_INFO",
          L"WinreBootReason",
          L"PendingSafeOsOperations");
LABEL_113:
        if ( !v13 )
          goto LABEL_114;
      }
      else if ( !(unsigned int)CFlowControlValidator::IsOperationRemovable(v155, a3, 75)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v176, a3, 76)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v177, a3, 77)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v178, a3, 78)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v179, a3, 136)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v180, a3, 83)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v181, a3, 56)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v182, a3, 95)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v183, a3, 96)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v184, a3, 108)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v185, a3, 115)
             || !(unsigned int)CFlowControlValidator::IsOperationRemovable(v186, a3, 138) )
      {
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
        v213 = GetLastError();
        v214 = CurrentIP();
        v215 = ConstructPartialMsgW(
                 0x4000000u,
                 "FLOWTRACK: Flow assessment: Cannot remove one or more safe OS operations, cannot execute the Skip SafeOS boot flow.");
        WdsSetupLogMessageW(
          v215,
          819200,
          L"D",
          0,
          3874,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v214,
          v213,
          0,
          0);
        if ( v8 )
        {
          v17 = L"PendingSafeOsOperations";
          goto LABEL_24;
        }
        goto LABEL_115;
      }
      LODWORD(OutBuffer) = 0;
      v187 = (struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v6)(v6);
      v188 = SPGetVolumeNameFromPath(v187, 0, (int *)&OutBuffer);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v293, v188);
      if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v293) || !(_DWORD)OutBuffer )
      {
        v13 = 0;
        (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
        v189 = GetLastError();
        v190 = CurrentIP();
        v191 = ConstructPartialMsgW(
                 0x3000000u,
                 "FLOWTRACK: Flow assessment: Failed to get the stable volume name, cannot execute the Skip SafeOS boot flow.");
        WdsSetupLogMessageW(
          v191,
          819200,
          L"D",
          0,
          3892,
          L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
          L"CFlowControlValidator::ExecuteFlowAssessment",
          v190,
          v189,
          0,
          0);
        if ( v8 )
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
            v8,
            L"SP_VALIDATOR_INFO",
            L"WinreBootReason",
            L"FailedGetStableVolumeName");
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v293);
      v4 = v291;
      if ( v13 && v291 )
      {
        LOWORD(BytesReturned[0]) = 63;
        *(DWORD *)((char *)BytesReturned + 2) = *(_DWORD *)L":\\";
        HIWORD(BytesReturned[1]) = asc_180557F68[3];
        v192 = (UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v6)(v6);
        LOWORD(BytesReturned[0]) = *UnBCL::String::get_CString(v192);
        v193 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v301, L"Windows.old");
        v194 = (const struct UnBCL::String *)UnBCL::String::String(
                                               (UnBCL::String *)v303,
                                               (const unsigned __int16 *)BytesReturned);
        v195 = UnBCL::Path::Combine(v194, v193);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v293, v195);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::String::~String((UnBCL::String *)v301);
        v196 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v293);
        if ( UnBCL::Directory::Exists(v196) )
        {
          v13 = 0;
          (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
          v197 = GetLastError();
          v198 = CurrentIP();
          v199 = ConstructPartialMsgW(
                   0x4000000u,
                   "FLOWTRACK: Flow assessment: Found Windows.OLD folder, cannot execute the Skip SafeOS boot flow.");
          WdsSetupLogMessageW(
            v199,
            819200,
            L"D",
            0,
            3910,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CFlowControlValidator::ExecuteFlowAssessment",
            v198,
            v197,
            0,
            0);
          if ( v8 )
            (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 16LL))(
              v8,
              L"SP_VALIDATOR_INFO",
              L"WinreBootReason",
              L"WindowsOldPresent");
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v293);
        if ( v13 )
        {
          wcscpy(FileName, L"\\\\.\\?:");
          v200 = (UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))v6)(v6);
          FileName[4] = *UnBCL::String::get_CString(v200);
          FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            v209 = GetLastError();
            v210 = CurrentIP();
            v211 = GetLastError();
            v212 = ConstructPartialMsgW(
                     0x3000000u,
                     "Flow assessment: Cannot open volume for the OS partition (%s). Error: 0x%08X",
                     (const char *)FileName,
                     v211);
            WdsSetupLogMessageW(
              v212,
              819200,
              L"D",
              0,
              3966,
              L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
              L"CFlowControlValidator::ExecuteFlowAssessment",
              v210,
              v209,
              0,
              0);
          }
          else
          {
            BytesReturned[0] = 0;
            LODWORD(OutBuffer) = 0;
            if ( DeviceIoControl(FileW, 0x90078u, 0, 0, &OutBuffer, 4u, BytesReturned, 0) )
            {
              if ( (OutBuffer & 1) != 0 )
              {
                v13 = 0;
                (*(void (__fastcall **)(struct IExecutionContext *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 4);
                v202 = GetLastError();
                v203 = CurrentIP();
                v204 = ConstructPartialMsgW(
                         0x4000000u,
                         "FLOWTRACK: Flow assessment: OS partition's file system has the dirty bit set, cannot execute th"
                         "e Skip SafeOS boot flow.");
                WdsSetupLogMessageW(
                  v204,
                  819200,
                  L"D",
                  0,
                  3952,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                  L"CFlowControlValidator::ExecuteFlowAssessment",
                  v203,
                  v202,
                  0,
                  0);
                if ( v8 )
                {
                  v17 = L"FileSystemDirtyBitSet";
                  goto LABEL_24;
                }
              }
            }
            else
            {
              v205 = GetLastError();
              v206 = CurrentIP();
              v207 = GetLastError();
              v208 = ConstructPartialMsgW(
                       0x3000000u,
                       "Flow assessment: Failed to query for the dirty bit for the OS partition. Error: 0x%08X",
                       v207);
              WdsSetupLogMessageW(
                v208,
                819200,
                L"D",
                0,
                3961,
                L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
                L"CFlowControlValidator::ExecuteFlowAssessment",
                v206,
                v205,
                0,
                0);
            }
          }
        }
      }
      goto LABEL_115;
    }
LABEL_114:
    v4 = v291;
    goto LABEL_115;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1802078b4  mov     rax, rsp
0x1802078b7  push    rbp
0x1802078b8  push    rsi
0x1802078b9  push    rdi
0x1802078ba  push    r12
0x1802078bc  push    r13
0x1802078be  push    r14
0x1802078c0  push    r15
0x1802078c2  lea     rbp, [rsp-60h]
0x1802078c7  sub     rsp, 160h
0x1802078ce  mov     [rbp+90h+var_78], 0FFFFFFFFFFFFFFFEh
0x1802078d6  mov     [rax+20h], rbx
0x1802078da  mov     rax, cs:__security_cookie
0x1802078e1  xor     rax, rsp
0x1802078e4  mov     [rbp+90h+var_40], rax
0x1802078e8  mov     esi, r9d
0x1802078eb  mov     [rsp+190h+var_130], r9d
0x1802078f0  mov     r13, r8
0x1802078f3  mov     r15, rdx
0x1802078f6  mov     [rbp+90h+var_B8], rdx
0x1802078fa  mov     rdi, rcx
0x1802078fd  mov     [rbp+90h+var_100], rcx
0x180207901  test    rdx, rdx
0x180207904  jz      loc_18020A4D4
0x18020790a  test    r8, r8
0x18020790d  jz      loc_18020A4D4
0x180207913  mov     rax, [rdx]
0x180207916  mov     rcx, rdx
0x180207919  mov     rax, [rax+40h]
0x18020791d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207922  mov     r14, rax
0x180207925  mov     [rbp+90h+var_E8], rax
0x180207929  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x180207930  lea     rcx, [rbp+90h+var_70]
0x180207934  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18020793a  mov     rbx, rax
0x18020793d  mov     rcx, [r15]
0x180207940  mov     rax, [rcx]
0x180207943  mov     rcx, r15
0x180207946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020794b  mov     rdx, rbx
0x18020794e  mov     rcx, rax
0x180207951  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180207957  mov     rdx, rax
0x18020795a  lea     rcx, [rbp+90h+var_88]
0x18020795e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180207964  nop
0x180207965  lea     rcx, [rbp+90h+var_70]
0x180207969  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18020796f  mov     rax, [r15]
0x180207972  mov     rcx, r15
0x180207975  mov     rax, [rax+28h]
0x180207979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020797e  mov     ebx, 3
0x180207983  lea     r12d, [rbx+3Eh]
0x180207987  cmp     eax, ebx
0x180207989  jl      loc_180207C15
0x18020798f  lea     edx, [rbx+34h]
0x180207992  mov     rcx, r13
0x180207995  call    ?IsOperationExecuted@COperationQueue@@QEAAHW4OP_OPERATION_ID@@PEBG@Z; COperationQueue::IsOperationExecuted(OP_OPERATION_ID,ushort const *)
0x18020799a  test    eax, eax
0x18020799c  jnz     loc_180207AC0
0x1802079a2  test    esi, esi
0x1802079a4  jz      loc_180207A40
0x1802079aa  xor     r12d, r12d
0x1802079ad  mov     rax, [r15]
0x1802079b0  mov     edx, ebx
0x1802079b2  mov     rcx, r15
0x1802079b5  mov     rax, [rax+30h]
0x1802079b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802079be  call    cs:__imp_GetLastError
0x1802079c4  mov     edi, eax
0x1802079c6  call    cs:__imp_CurrentIP
0x1802079cc  mov     rbx, rax
0x1802079cf  lea     rdx, aFlowtrackFlowA; "FLOWTRACK: Flow assessment: New OS imag"...
0x1802079d6  mov     ecx, 4000000h; unsigned int
0x1802079db  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802079e0  mov     [rsp+190h+var_140], r12d
0x1802079e5  mov     [rsp+190h+var_148], r12
0x1802079ea  mov     [rsp+190h+var_150], edi
0x1802079ee  mov     [rsp+190h+lpOverlapped], rbx
0x1802079f3  lea     rcx, aCflowcontrolva_0; "CFlowControlValidator::ExecuteFlowAsses"...
0x1802079fa  mov     [rsp+190h+hTemplateFile], rcx
0x1802079ff  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180207a06  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rcx
0x180207a0b  mov     [rsp+190h+dwCreationDisposition], 0DD6h
0x180207a13  xor     r9d, r9d
0x180207a16  lea     r8, aD_0; "D"
0x180207a1d  mov     edx, 0C8000h
0x180207a22  mov     rcx, rax
0x180207a25  call    cs:__imp_WdsSetupLogMessageW
0x180207a2b  test    r14, r14
0x180207a2e  jz      loc_180208DA7
0x180207a34  lea     r9, aNewoswimapplyi; "NewOSWimApplyIncomplete"
0x180207a3b  jmp     loc_180207CC6
0x180207a40  mov     r8d, 37h ; '7'
0x180207a46  mov     rdx, r13
0x180207a49  call    ?GetOperationEarliestExecutionPhase@CFlowControlValidator@@IEAA?AW4OP_EXECUTION_PHASE@@PEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::GetOperationEarliestExecutionPhase(COperationQueue *,OP_OPERATION_ID)
0x180207a4e  cmp     eax, ebx
0x180207a50  jl      short loc_180207AC0
0x180207a52  xor     r12d, r12d
0x180207a55  mov     rax, [r15]
0x180207a58  mov     edx, ebx
0x180207a5a  mov     rcx, r15
0x180207a5d  mov     rax, [rax+30h]
0x180207a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207a66  call    cs:__imp_GetLastError
0x180207a6c  mov     edi, eax
0x180207a6e  call    cs:__imp_CurrentIP
0x180207a74  mov     rbx, rax
0x180207a77  lea     rdx, aFlowtrackFlowA_12; "FLOWTRACK: Flow assessment: New OS imag"...
0x180207a7e  mov     ecx, 4000000h; unsigned int
0x180207a83  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180207a88  mov     [rsp+190h+var_140], r12d
0x180207a8d  mov     [rsp+190h+var_148], r12
0x180207a92  mov     [rsp+190h+var_150], edi
0x180207a96  mov     [rsp+190h+lpOverlapped], rbx
0x180207a9b  lea     rcx, aCflowcontrolva_0; "CFlowControlValidator::ExecuteFlowAsses"...
0x180207aa2  mov     [rsp+190h+hTemplateFile], rcx
0x180207aa7  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180207aae  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rcx
0x180207ab3  mov     [rsp+190h+dwCreationDisposition], 0DE6h
0x180207abb  jmp     loc_180207A13
0x180207ac0  mov     edx, r12d
0x180207ac3  mov     rcx, r13
0x180207ac6  call    ?IsOperationPresent@COperationQueue@@QEAAHW4OP_OPERATION_ID@@PEBG@Z; COperationQueue::IsOperationPresent(OP_OPERATION_ID,ushort const *)
0x180207acb  test    eax, eax
0x180207acd  jz      loc_180207C01
0x180207ad3  mov     edx, r12d
0x180207ad6  mov     rcx, r13
0x180207ad9  call    ?IsOperationExecuted@COperationQueue@@QEAAHW4OP_OPERATION_ID@@PEBG@Z; COperationQueue::IsOperationExecuted(OP_OPERATION_ID,ushort const *)
0x180207ade  test    eax, eax
0x180207ae0  jnz     loc_180207C01
0x180207ae6  test    esi, esi
0x180207ae8  jz      loc_180207B84
0x180207aee  xor     r12d, r12d
0x180207af1  mov     rax, [r15]
0x180207af4  mov     edx, ebx
0x180207af6  mov     rcx, r15
0x180207af9  mov     rax, [rax+30h]
0x180207afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207b02  call    cs:__imp_GetLastError
0x180207b08  mov     edi, eax
0x180207b0a  call    cs:__imp_CurrentIP
0x180207b10  mov     rbx, rax
0x180207b13  lea     rdx, aFlowtrackFlowA_31; "FLOWTRACK: Flow assessment: Main offlin"...
0x180207b1a  mov     ecx, 4000000h; unsigned int
0x180207b1f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180207b24  mov     [rsp+190h+var_140], r12d
0x180207b29  mov     [rsp+190h+var_148], r12
0x180207b2e  mov     [rsp+190h+var_150], edi
0x180207b32  mov     [rsp+190h+lpOverlapped], rbx
0x180207b37  lea     rcx, aCflowcontrolva_0; "CFlowControlValidator::ExecuteFlowAsses"...
0x180207b3e  mov     [rsp+190h+hTemplateFile], rcx
0x180207b43  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180207b4a  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rcx
0x180207b4f  mov     [rsp+190h+dwCreationDisposition], 0DFAh
0x180207b57  xor     r9d, r9d
0x180207b5a  lea     r8, aD_0; "D"
0x180207b61  mov     edx, 0C8000h
0x180207b66  mov     rcx, rax
0x180207b69  call    cs:__imp_WdsSetupLogMessageW
0x180207b6f  test    r14, r14
0x180207b72  jz      loc_180208DA7
0x180207b78  lea     r9, aOfflineapplyin; "OfflineApplyIncomplete"
0x180207b7f  jmp     loc_180207CC6
0x180207b84  mov     r8d, r12d
0x180207b87  mov     rdx, r13
0x180207b8a  call    ?GetOperationEarliestExecutionPhase@CFlowControlValidator@@IEAA?AW4OP_EXECUTION_PHASE@@PEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::GetOperationEarliestExecutionPhase(COperationQueue *,OP_OPERATION_ID)
0x180207b8f  cmp     eax, ebx
0x180207b91  jl      short loc_180207C01
0x180207b93  xor     r12d, r12d
0x180207b96  mov     rax, [r15]
0x180207b99  mov     edx, ebx
0x180207b9b  mov     rcx, r15
0x180207b9e  mov     rax, [rax+30h]
0x180207ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207ba7  call    cs:__imp_GetLastError
0x180207bad  mov     edi, eax
0x180207baf  call    cs:__imp_CurrentIP
0x180207bb5  mov     rbx, rax
0x180207bb8  lea     rdx, aFlowtrackFlowA_6; "FLOWTRACK: Flow assessment: Main offlin"...
0x180207bbf  mov     ecx, 4000000h; unsigned int
0x180207bc4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180207bc9  mov     [rsp+190h+var_140], r12d
0x180207bce  mov     [rsp+190h+var_148], r12
0x180207bd3  mov     [rsp+190h+var_150], edi
0x180207bd7  mov     [rsp+190h+lpOverlapped], rbx
0x180207bdc  lea     rcx, aCflowcontrolva_0; "CFlowControlValidator::ExecuteFlowAsses"...
0x180207be3  mov     [rsp+190h+hTemplateFile], rcx
0x180207be8  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180207bef  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rcx
0x180207bf4  mov     [rsp+190h+dwCreationDisposition], 0E0Ah
0x180207bfc  jmp     loc_180207B57
0x180207c01  mov     rax, [r15]
0x180207c04  mov     rcx, r15
0x180207c07  mov     rax, [rax+28h]
0x180207c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207c10  cmp     eax, 4
0x180207c13  jge     short loc_180207C1D
0x180207c15  xor     r12d, r12d
0x180207c18  jmp     loc_180208DA7
0x180207c1d  mov     edx, 3Ch ; '<'
0x180207c22  mov     rcx, r13
0x180207c25  call    ?IsOperationPresent@COperationQueue@@QEAAHW4OP_OPERATION_ID@@PEBG@Z; COperationQueue::IsOperationPresent(OP_OPERATION_ID,ushort const *)
0x180207c2a  test    eax, eax
0x180207c2c  jz      loc_180207CE8
0x180207c32  xor     r12d, r12d
0x180207c35  mov     rax, [r15]
0x180207c38  lea     edx, [r12+4]
0x180207c3d  mov     rcx, r15
0x180207c40  mov     rax, [rax+30h]
0x180207c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207c49  call    cs:__imp_GetLastError
0x180207c4f  mov     edi, eax
0x180207c51  call    cs:__imp_CurrentIP
0x180207c57  mov     rbx, rax
0x180207c5a  lea     rdx, aFlowtrackFlowA_9; "FLOWTRACK: Flow assessment: Data image "...
0x180207c61  mov     ecx, 4000000h; unsigned int
0x180207c66  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180207c6b  mov     [rsp+190h+var_140], r12d
0x180207c70  mov     [rsp+190h+var_148], r12
0x180207c75  mov     [rsp+190h+var_150], edi
0x180207c79  mov     [rsp+190h+lpOverlapped], rbx
0x180207c7e  lea     rcx, aCflowcontrolva_0; "CFlowControlValidator::ExecuteFlowAsses"...
0x180207c85  mov     [rsp+190h+hTemplateFile], rcx
0x180207c8a  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180207c91  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rcx
0x180207c96  mov     [rsp+190h+dwCreationDisposition], 0E29h
0x180207c9e  xor     r9d, r9d
0x180207ca1  lea     r8, aD_0; "D"
0x180207ca8  mov     edx, 0C8000h
0x180207cad  mov     rcx, rax
0x180207cb0  call    cs:__imp_WdsSetupLogMessageW
0x180207cb6  test    r14, r14
0x180207cb9  jz      loc_180208DA7
0x180207cbf  lea     r9, aDataimageapply; "DataImageApply"
0x180207cc6  mov     rax, [r14]
0x180207cc9  lea     r8, aWinrebootreaso; "WinreBootReason"
0x180207cd0  lea     rdx, aSpValidatorInf; "SP_VALIDATOR_INFO"
0x180207cd7  mov     rcx, r14
0x180207cda  mov     rax, [rax+10h]
0x180207cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207ce3  jmp     loc_180208DA7
0x180207ce8  mov     edx, 37h ; '7'
0x180207ced  lea     r12d, [rdx-36h]
0x180207cf1  mov     rcx, r13
0x180207cf4  call    ?IsOperationExecuted@COperationQueue@@QEAAHW4OP_OPERATION_ID@@PEBG@Z; COperationQueue::IsOperationExecuted(OP_OPERATION_ID,ushort const *)
0x180207cf9  test    eax, eax
0x180207cfb  jz      loc_180207F4A
0x180207d01  lea     rcx, [rbp+90h+var_88]
0x180207d05  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180207d0b  mov     rcx, rax
0x180207d0e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180207d14  mov     r8, rax; lpFileName
0x180207d17  lea     rdx, aApplyea; "ApplyEA"
0x180207d1e  lea     rcx, aActions; "Actions"
0x180207d25  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180207d2a  mov     rdx, rax
0x180207d2d  lea     rcx, [rsp+190h+var_120]
0x180207d32  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180207d38  nop
0x180207d39  lea     rdx, aYes_1; "Yes"
0x180207d40  lea     rcx, [rbp+90h+var_D0]
0x180207d44  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180207d4a  mov     rbx, rax
0x180207d4d  lea     rcx, [rsp+190h+var_120]
0x180207d52  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180207d58  mov     r8d, r12d
0x180207d5b  mov     rdx, rbx
0x180207d5e  mov     rcx, rax
0x180207d61  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x180207d67  mov     ebx, eax
0x180207d69  lea     rcx, [rbp+90h+var_D0]
0x180207d6d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180207d73  test    ebx, ebx
0x180207d75  jnz     loc_180207F36
0x180207d7b  cmp     dword ptr [rdi+58h], 4
0x180207d7f  jl      short loc_180207DE2
0x180207d81  call    cs:__imp_GetLastError
0x180207d87  mov     edi, eax
0x180207d89  call    cs:__imp_CurrentIP
0x180207d8f  mov     rbx, rax
0x180207d92  lea     rdx, aFlowtrackFlowA_5; "FLOWTRACK: Flow assessment: New OS does"...
0x180207d99  mov     ecx, 4000000h; unsigned int
0x180207d9e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180207da3  mov     [rsp+190h+var_140], 0
0x180207dab  mov     [rsp+190h+var_148], 0
0x180207db4  mov     [rsp+190h+var_150], edi
0x180207db8  mov     [rsp+190h+lpOverlapped], rbx
0x180207dbd  lea     rcx, aCflowcontrolva_0; "CFlowControlValidator::ExecuteFlowAsses"...
0x180207dc4  mov     [rsp+190h+hTemplateFile], rcx
0x180207dc9  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180207dd0  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rcx
0x180207dd5  mov     [rsp+190h+dwCreationDisposition], 0E39h
0x180207ddd  jmp     loc_180207E6B
0x180207de2  lea     rdx, aSpEnvForceSkip; "SP_ENV_FORCE_SKIP_SAFEOS_BOOT"
0x180207de9  lea     rcx, [rbp+90h+var_D0]
0x180207ded  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180207df3  nop
  ... truncated ...
```
