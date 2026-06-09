# Microsoft.SharePoint.FileSync.CrudProcessor::ProcessChangeWithExceptionHandler

- ea: `0xaac1a0`
- end: `0xaad551`
- name: `Microsoft.SharePoint.FileSync.CrudProcessor::ProcessChangeWithExceptionHandler`
- size: `5041`
- prototype: ``
- caller_count: `6`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0xaaaaa0`
- `0xaaabb0`
- `0xaab0c0`
- `0xaaba40`
- `0xaabbb0`
- `0xaad7c0`

## callees

- `0x1b7f20`
- `0x1b7f50`
- `0x93dae0`
- `0x957d90`
- `0xa9af50`
- `0xa9afa0`
- `0xa9b3e0`
- `0xa9b440`
- `0xa9cbd0`
- `0xa9d2c0`
- `0xa9d430`
- `0xaa1850`
- `0xaa1860`
- `0xaabdf0`
- `0xaac1a0`
- `0xaad560`
- `0xaad580`
- `0xaad8d0`
- `0xaad8f0`
- `0xaad940`
- `0xaad960`
- `0xaad980`
- `0xaad9a0`
- `0xaad9e0`
- `0xaada00`

## string_xrefs

- `0xaac1d0`: `ProcessChangeWithExceptionHandler:{0}- SPBITSSessionNotFoundException: WriteStatus=[{1}] : {2}`
- `0xaac214`: `ProcessChangeWithExceptionHandler:{0}- SPBITSSessionInProgressException: WriteStatus=[{1}] : {2}`
- `0xaac258`: `ProcessChangeWithExceptionHandler:{0}- SPBITSMissingRangeException: WriteStatus=[{1}] : {2}`
- `0xaac2a2`: `ProcessChangeWithExceptionHandler:{0}- SyncResourceAlreadyExistsException: WriteStatus=[{1}] : {2}`
- `0xaac2e7`: `ProcessChangeWithExceptionHandler:{0}- SyncInvalidResourceTypeException: WriteStatus=[{1}] : {2}`
- `0xaac32c`: `ProcessChangeWithExceptionHandler:{0}- SyncParentResourceNotFoundException: WriteStatus=[{1}] : {2}`
- `0xaac371`: `ProcessChangeWithExceptionHandler:{0}- SyncResoureNotFoundException: WriteStatus=[{1}] : {2}`
- `0xaac3bc`: `ProcessChangeWithExceptionHandler:{0}- SyncBitsCommitErrorException: WriteStatus=[{1}] : {2}`
- `0xaac401`: `ProcessChangeWithExceptionHandler:{0}- SyncInvalidRootFolderOperationException: WriteStatus=[{1}] : {2}`
- `0xaac446`: `ProcessChangeWithExceptionHandler:{0}- SyncArgumentOutOfRangeException: WriteStatus=[{1}] : {2}`
- `0xaac491`: `ProcessChangeWithExceptionHandler:{0}- SyncBadRequestException: WriteStatus=[{1}] : {2}`
- `0xaac4df`: `ProcessChangeWithExceptionHandler:{0}- SyncServerException: WriteStatus=[{1}] : {2}`
- `0xaac59b`: `ProcessChangeWithExceptionHandler:{0}- (SyncErrorCode.DeleteFolderWithSubWebs) Folder has children; DeleteIfEmpty failed for {1} with {2}. Exception: {3}.`
- `0xaac678`: `ProcessChangeWithExceptionHandler:{0}- (SyncErrorCode.DocumentCheckedOut) WriteStatus[{1}] Exception[{2}]`
- `0xaac70d`: `ProcessChangeWithExceptionHandler:{0}- (SyncErrorCode.ConcurrentUpdateConflict) Exception[{1}]`
- `0xaacb4b`: `ProcessChangeWithExceptionHandler:{0}- SPException (V_REMOVE_FILE) ETagMismatch for ParentResourceID:[{1}], ResourceID:[{2}], ClientETag[{3}]`
- `0xaacc3d`: `ProcessChangeWithExceptionHandler:{0}- SPException (V_CANT_DELETE_FOLDER_WITH_SUBWEBS) Folder has children; DeleteIfEmpty failed for {1} with {2}`
- `0xaacc88`: `ProcessChangeWithExceptionHandler:{0}- SPException (TP_E_DOCALREADYEXISTS) Item Already Exists for {1} type {2}`
- `0xaaccd4`: `ProcessChangeWithExceptionHandler:{0}- SPException (V_DIR_GONE) Target directory gone, Target {1}`
- `0xaacdc3`: `ProcessChangeWithExceptionHandler:{0}- SPException (COBALT_HRESULT_FILEUNAUTHORIZEDACCESS) WriteStatus=[{1}] : {2}`
- `0xaace6b`: `ProcessChangeWithExceptionHandler:{0}- SPException (COM_MISSING_FILE_OR_INVALID_FILE_NAME): WriteStatus=[{1}] : {2}`
- `0xaacefb`: `ProcessChangeWithExceptionHandler:{0}- SPException (ERROR_NOT_ENOUGH_QUOTA) WriteStatus=[{1}] : {2}`
- `0xaacf3f`: `ProcessChangeWithExceptionHandler:{0}- SPException (V_COBALT_ERROR) WriteStatus=[{1}] : {2}`
- `0xaacf82`: `ProcessChangeWithExceptionHandler:{0}- SPException (TP_E_LISTITEMDELETED) List item {1} is deleted: WriteStatus=[{2}] : {3}`
- `0xaacfcf`: `ProcessChangeWithExceptionHandler:{0}- SPException (V_NO_RENAME_TO_THICKET_FOLDER) Exception: {1}`
- `0xaad008`: `ProcessChangeWithExceptionHandler:{0}- SPException (V_NO_THICKET_MOVE) Exception: {1}`
- `0xaad350`: `ProcessChangeWithExceptionHandler:{0}- (Exception) FileNotFoundException: WriteStatus=[{1}] : {2}`
- `0xaad396`: `ProcessChangeWithExceptionHandler:{0}- (Exception) DirectoryNotFoundException: WriteStatus=[{1}] : {2}`
- `0xaad3dc`: `ProcessChangeWithExceptionHandler:{0}- (Exception) PathTooLongException: WriteStatus=[{1}] : {2}`
- `0xaad43a`: `ProcessChangeWithExceptionHandler:{0}- (Exception) UnauthorizedAccessException: WriteStatus=[{1}] : {2}`
- `0xaad492`: `ProcessChangeWithExceptionHandler:{0}- (Exception) COMException: WriteStatus=[{1}] : {2}`
- `0xaad4cf`: `ProcessChangeWithExceptionHandler{0}- Unknown (COMException): {1}`

## pseudocode

```c

```

## disassembly

```asm
0xaac1a0  ldloca.s 0
0xaac1a2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xaac1a8  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.SharePoint.FileSync.SyncUtils::GetErrorHandlingHint()
0xaac1ad  stloc.0
0xaac1ae  ldc.i4.1
0xaac1af  call     void Microsoft.SharePoint.FileSync.SyncUtils::SetErrorHandlingHint(int32 hint)
0xaac1b4  ldarg.2
0xaac1b5  callvirt instance void [mscorlib]System.Action::Invoke()
0xaac1ba  leave    loc_AAD52F
0xaac1bf  stloc.1
0xaac1c0  ldarg.1
0xaac1c1  ldc.i4.s 0x18
0xaac1c3  stind.i4
0xaac1c4  ldc.i4   0x4470CE
0xaac1c9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac1ce  ldc.i4.s 0xF
0xaac1d0  ldstr    aProcesschangew// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac1d5  ldc.i4.3
0xaac1d6  newarr   [mscorlib]System.Object
0xaac1db  stloc.s  0x16
0xaac1dd  ldloc.s  0x16
0xaac1df  ldc.i4.0
0xaac1e0  ldarg.0
0xaac1e1  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac1e6  stelem.ref
0xaac1e7  ldloc.s  0x16
0xaac1e9  ldc.i4.1
0xaac1ea  ldarg.1
0xaac1eb  ldind.i4
0xaac1ec  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac1f1  stelem.ref
0xaac1f2  ldloc.s  0x16
0xaac1f4  ldc.i4.2
0xaac1f5  ldloc.1
0xaac1f6  stelem.ref
0xaac1f7  ldloc.s  0x16
0xaac1f9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac1fe  leave    loc_AAD52F
0xaac203  stloc.2
0xaac204  ldarg.1
0xaac205  ldc.i4.s 0x1A
0xaac207  stind.i4
0xaac208  ldc.i4   0x4470CF
0xaac20d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac212  ldc.i4.s 0xF
0xaac214  ldstr    aProcesschangew_0// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac219  ldc.i4.3
0xaac21a  newarr   [mscorlib]System.Object
0xaac21f  stloc.s  0x17
0xaac221  ldloc.s  0x17
0xaac223  ldc.i4.0
0xaac224  ldarg.0
0xaac225  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac22a  stelem.ref
0xaac22b  ldloc.s  0x17
0xaac22d  ldc.i4.1
0xaac22e  ldarg.1
0xaac22f  ldind.i4
0xaac230  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac235  stelem.ref
0xaac236  ldloc.s  0x17
0xaac238  ldc.i4.2
0xaac239  ldloc.2
0xaac23a  stelem.ref
0xaac23b  ldloc.s  0x17
0xaac23d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac242  leave    loc_AAD52F
0xaac247  stloc.3
0xaac248  ldarg.1
0xaac249  ldc.i4.s 0x14
0xaac24b  stind.i4
0xaac24c  ldc.i4   0x4470D0
0xaac251  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac256  ldc.i4.s 0xF
0xaac258  ldstr    aProcesschangew_1// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac25d  ldc.i4.3
0xaac25e  newarr   [mscorlib]System.Object
0xaac263  stloc.s  0x18
0xaac265  ldloc.s  0x18
0xaac267  ldc.i4.0
0xaac268  ldarg.0
0xaac269  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac26e  stelem.ref
0xaac26f  ldloc.s  0x18
0xaac271  ldc.i4.1
0xaac272  ldarg.1
0xaac273  ldind.i4
0xaac274  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac279  stelem.ref
0xaac27a  ldloc.s  0x18
0xaac27c  ldc.i4.2
0xaac27d  ldloc.3
0xaac27e  stelem.ref
0xaac27f  ldloc.s  0x18
0xaac281  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac286  leave    loc_AAD52F
0xaac28b  stloc.s  4
0xaac28d  ldarg.1
0xaac28e  ldloc.s  4
0xaac290  callvirt instance valuetype Microsoft.SharePoint.FileSync.WriteStatus Microsoft.SharePoint.FileSync.SyncResourceAlreadyExistsException::get_ItemExistsStatus()
0xaac295  stind.i4
0xaac296  ldc.i4   0x4470C4
0xaac29b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac2a0  ldc.i4.s 0xF
0xaac2a2  ldstr    aProcesschangew_2// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac2a7  ldc.i4.3
0xaac2a8  newarr   [mscorlib]System.Object
0xaac2ad  stloc.s  0x19
0xaac2af  ldloc.s  0x19
0xaac2b1  ldc.i4.0
0xaac2b2  ldarg.0
0xaac2b3  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac2b8  stelem.ref
0xaac2b9  ldloc.s  0x19
0xaac2bb  ldc.i4.1
0xaac2bc  ldarg.1
0xaac2bd  ldind.i4
0xaac2be  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac2c3  stelem.ref
0xaac2c4  ldloc.s  0x19
0xaac2c6  ldc.i4.2
0xaac2c7  ldloc.s  4
0xaac2c9  stelem.ref
0xaac2ca  ldloc.s  0x19
0xaac2cc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac2d1  leave    loc_AAD52F
0xaac2d6  stloc.s  5
0xaac2d8  ldarg.1
0xaac2d9  ldc.i4.2
0xaac2da  stind.i4
0xaac2db  ldc.i4   0x4470C5
0xaac2e0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac2e5  ldc.i4.s 0xF
0xaac2e7  ldstr    aProcesschangew_3// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac2ec  ldc.i4.3
0xaac2ed  newarr   [mscorlib]System.Object
0xaac2f2  stloc.s  0x1A
0xaac2f4  ldloc.s  0x1A
0xaac2f6  ldc.i4.0
0xaac2f7  ldarg.0
0xaac2f8  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac2fd  stelem.ref
0xaac2fe  ldloc.s  0x1A
0xaac300  ldc.i4.1
0xaac301  ldarg.1
0xaac302  ldind.i4
0xaac303  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac308  stelem.ref
0xaac309  ldloc.s  0x1A
0xaac30b  ldc.i4.2
0xaac30c  ldloc.s  5
0xaac30e  stelem.ref
0xaac30f  ldloc.s  0x1A
0xaac311  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac316  leave    loc_AAD52F
0xaac31b  stloc.s  6
0xaac31d  ldarg.1
0xaac31e  ldc.i4.7
0xaac31f  stind.i4
0xaac320  ldc.i4   0x4470C6
0xaac325  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac32a  ldc.i4.s 0xF
0xaac32c  ldstr    aProcesschangew_4// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac331  ldc.i4.3
0xaac332  newarr   [mscorlib]System.Object
0xaac337  stloc.s  0x1B
0xaac339  ldloc.s  0x1B
0xaac33b  ldc.i4.0
0xaac33c  ldarg.0
0xaac33d  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac342  stelem.ref
0xaac343  ldloc.s  0x1B
0xaac345  ldc.i4.1
0xaac346  ldarg.1
0xaac347  ldind.i4
0xaac348  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac34d  stelem.ref
0xaac34e  ldloc.s  0x1B
0xaac350  ldc.i4.2
0xaac351  ldloc.s  6
0xaac353  stelem.ref
0xaac354  ldloc.s  0x1B
0xaac356  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac35b  leave    loc_AAD52F
0xaac360  stloc.s  7
0xaac362  ldarg.1
0xaac363  ldc.i4.7
0xaac364  stind.i4
0xaac365  ldc.i4   0x4470C7
0xaac36a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac36f  ldc.i4.s 0xF
0xaac371  ldstr    aProcesschangew_5// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac376  ldc.i4.3
0xaac377  newarr   [mscorlib]System.Object
0xaac37c  stloc.s  0x1C
0xaac37e  ldloc.s  0x1C
0xaac380  ldc.i4.0
0xaac381  ldarg.0
0xaac382  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac387  stelem.ref
0xaac388  ldloc.s  0x1C
0xaac38a  ldc.i4.1
0xaac38b  ldarg.1
0xaac38c  ldind.i4
0xaac38d  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac392  stelem.ref
0xaac393  ldloc.s  0x1C
0xaac395  ldc.i4.2
0xaac396  ldloc.s  7
0xaac398  stelem.ref
0xaac399  ldloc.s  0x1C
0xaac39b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac3a0  leave    loc_AAD52F
0xaac3a5  stloc.s  8
0xaac3a7  ldarg.1
0xaac3a8  ldloc.s  8
0xaac3aa  callvirt instance valuetype Microsoft.SharePoint.FileSync.WriteStatus Microsoft.SharePoint.FileSync.SyncBitsCommitErrorException::get_WriteStatus()
0xaac3af  stind.i4
0xaac3b0  ldc.i4   0x5C61D5
0xaac3b5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac3ba  ldc.i4.s 0xF
0xaac3bc  ldstr    aProcesschangew_6// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac3c1  ldc.i4.3
0xaac3c2  newarr   [mscorlib]System.Object
0xaac3c7  stloc.s  0x1D
0xaac3c9  ldloc.s  0x1D
0xaac3cb  ldc.i4.0
0xaac3cc  ldarg.0
0xaac3cd  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac3d2  stelem.ref
0xaac3d3  ldloc.s  0x1D
0xaac3d5  ldc.i4.1
0xaac3d6  ldarg.1
0xaac3d7  ldind.i4
0xaac3d8  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac3dd  stelem.ref
0xaac3de  ldloc.s  0x1D
0xaac3e0  ldc.i4.2
0xaac3e1  ldloc.s  8
0xaac3e3  stelem.ref
0xaac3e4  ldloc.s  0x1D
0xaac3e6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac3eb  leave    loc_AAD52F
0xaac3f0  stloc.s  9
0xaac3f2  ldarg.1
0xaac3f3  ldc.i4.1
0xaac3f4  stind.i4
0xaac3f5  ldc.i4   0x494419
0xaac3fa  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac3ff  ldc.i4.s 0xF
0xaac401  ldstr    aProcesschangew_7// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac406  ldc.i4.3
0xaac407  newarr   [mscorlib]System.Object
0xaac40c  stloc.s  0x1E
0xaac40e  ldloc.s  0x1E
0xaac410  ldc.i4.0
0xaac411  ldarg.0
0xaac412  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac417  stelem.ref
0xaac418  ldloc.s  0x1E
0xaac41a  ldc.i4.1
0xaac41b  ldarg.1
0xaac41c  ldind.i4
0xaac41d  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac422  stelem.ref
0xaac423  ldloc.s  0x1E
0xaac425  ldc.i4.2
0xaac426  ldloc.s  9
0xaac428  stelem.ref
0xaac429  ldloc.s  0x1E
0xaac42b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xaac430  leave    loc_AAD52F
0xaac435  stloc.s  0xA
0xaac437  ldarg.1
0xaac438  ldc.i4.7
0xaac439  stind.i4
0xaac43a  ldc.i4   0x4470C8
0xaac43f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xaac444  ldc.i4.s 0xA
0xaac446  ldstr    aProcesschangew_8// "ProcessChangeWithExceptionHandler:{0}- "...
0xaac44b  ldc.i4.3
0xaac44c  newarr   [mscorlib]System.Object
0xaac451  stloc.s  0x1F
0xaac453  ldloc.s  0x1F
0xaac455  ldc.i4.0
0xaac456  ldarg.0
0xaac457  callvirt instance string RequestContext::get_CallingMethodOrCommand()
0xaac45c  stelem.ref
0xaac45d  ldloc.s  0x1F
0xaac45f  ldc.i4.1
0xaac460  ldarg.1
0xaac461  ldind.i4
0xaac462  box      Microsoft.SharePoint.FileSync.WriteStatus
0xaac467  stelem.ref
0xaac468  ldloc.s  0x1F
0xaac46a  ldc.i4.2
0xaac46b  ldloc.s  0xA
0xaac46d  stelem.ref
0xaac46e  ldloc.s  0x1F
0xaac470  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
  ... truncated ...
```
