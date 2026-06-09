# UnionFs::Utils::CopyItemPriv(_FLT_CALLBACK_DATA const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathName const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::Utils::CopyItemParams const &,UnionFs::StackEventTracer &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> *)

- ea: `0x14006c3ec`
- end: `0x14006de83`
- name: `?CopyItemPriv@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@AEBVUfsPathName@2@AEBU_FLT_INSTANCE@@2AEBUCopyItemParams@12@AEAVStackEventTracer@2@PEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@Z`
- size: `6807`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING SourceString, __int64, struct _FILE_OBJECT *, __int64)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006be98`
- `0x14006de90`

## callees

- `0x140003bc0`
- `0x140006064`
- `0x14000f81c`
- `0x14001014c`
- `0x14001c888`
- `0x140022020`
- `0x140023adc`
- `0x140044334`
- `0x1400444f4`
- `0x1400448c8`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005d718`
- `0x140067d00`
- `0x140067e58`
- `0x140067ea4`
- `0x14006b694`
- `0x14006b78c`
- `0x14006c058`
- `0x14006c3ec`
- `0x14006e394`
- `0x14006fc38`
- `0x140072df8`
- `0x14007599c`
- `0x140075d30`
- `0x1400787a8`
- `0x140078dc0`
- `0x140079f68`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006c630`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c76c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c79c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c84e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c87e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ca84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cb4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cb7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cbab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cee7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d041`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d099`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d0c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d3ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d455`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d484`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d4b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d61b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d671`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d8c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d945`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d973`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006daa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc64`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dcc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dd7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ddcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ddfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006de29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c630`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c76c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c79c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c84e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c87e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ca84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cb4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cb7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cbab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cee7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d041`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d099`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d0c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d3ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d455`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d484`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d4b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d61b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d671`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d8c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d945`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d973`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006daa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc64`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dcc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dd7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ddcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ddfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006de29`
- `ntoskrnl!PsGetHostSilo` at `0x14006cd19`
- `ntoskrnl!PsGetHostSilo` at `0x14006cd19`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c468`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c52a`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c681`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c8cf`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cbfc`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cf97`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d147`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d2c5`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d3d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d503`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d5f0`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d71f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d895`
- `ntoskrnl!ObfDereferenceObject` at `0x14006da2c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006dbe7`
- `ntoskrnl!ObfDereferenceObject` at `0x14006dd4f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c468`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c52a`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c681`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c8cf`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cbfc`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cf97`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d147`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d2c5`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d3d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d503`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d5f0`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d71f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d895`
- `ntoskrnl!ObfDereferenceObject` at `0x14006da2c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006dbe7`
- `ntoskrnl!ObfDereferenceObject` at `0x14006dd4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006cdad`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ceaa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d05c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d418`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d634`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d8d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006da70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006dc2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006dd93`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006cdad`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ceaa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d05c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d418`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d634`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d8d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006da70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006dc2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006dd93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006cdb9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ceb6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d068`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d424`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d640`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d8e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006da7c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dc37`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dd9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006cdb9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ceb6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d068`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d424`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d640`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d8e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006da7c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dc37`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dd9f`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006c932`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006cc5b`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006c932`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006cc5b`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006c805`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006c805`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006c979`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cb65`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cf00`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d0b2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d46e`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d68a`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d92f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dac2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dc7d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dde5`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006c979`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cb65`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cf00`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d0b2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d46e`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d68a`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d92f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dac2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dc7d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dde5`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006cb03`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006ccc1`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006cb03`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006ccc1`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c511`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c668`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c7d4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c8b6`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cbe3`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cf7e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d12e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d4ea`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d706`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c511`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c668`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c7d4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c8b6`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cbe3`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cf7e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d12e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d4ea`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d706`

## string_xrefs

- `0x14006c4e8`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c592`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c5f8`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c74b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c82d`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c95b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006ca5e`: `UnionFs::Utils::CopyItemPriv`
- `0x14006cb30`: `UnionFs::Utils::CopyItemPriv`
- `0x14006cd8d`: `UnionFs::Utils::CopyItemPriv`
- `0x14006ce87`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d02b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d39b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d54f`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d823`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d9de`: `UnionFs::Utils::CopyItemPriv`
- `0x14006db9b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c4d7`: `PUSH: Opening source file`
- `0x14006c73a`: `PUSH: Getting source security descriptor`
- `0x14006c5e7`: `PUSH: Copying target name`
- `0x14006c945`: `API: FltAllocateExtraCreateParameterFromLookasideList`
- `0x14006cc6e`: `API: FltAllocateExtraCreateParameterFromLookasideList`
- `0x14006c81c`: `API: FltAllocateExtraCreateParameterList`
- `0x14006cab9`: `PUSH: Munging reparse data`
- `0x14006ca4d`: `PUSH: Getting layer reparse data`
- `0x14006cb24`: `API: FltInsertExtraCreateParameter`
- `0x14006d582`: `Destination already exists`
- `0x14006d015`: `PUSH: Copy EAs to buffer`
- `0x14006d812`: `PUSH: Copying compression state`
- `0x14006d38a`: `API: Creating component in target`
- `0x14006db8a`: `PUSH: Copying hard links`
- `0x14006d9cd`: `PUSH: Copying file metadata`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyItemPriv(
        const struct _UNICODE_STRING *a1,
        __int64 a2,
        __int128 *a3,
        struct _FLT_INSTANCE *a4,
        PCUNICODE_STRING SourceString,
        __int64 *a6,
        struct _FILE_OBJECT *a7,
        void **a8)
{
  void *v10; // rcx
  __int64 v11; // r9
  struct _ERESOURCE *v12; // r15
  __int128 v13; // xmm0
  int v14; // ebx
  PVOID v15; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v17; // rcx
  int Security; // edi
  struct _UNICODE_STRING *v19; // r9
  struct _UNICODE_STRING *v20; // rdx
  struct _UNICODE_STRING *v21; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v22; // rcx
  PVOID v23; // rcx
  _WORD *v24; // rbx
  unsigned __int16 v25; // ax
  struct _FILE_OBJECT *v26; // rbx
  PVOID v27; // rdi
  __int128 v28; // xmm0
  struct _UNICODE_STRING *v29; // rdx
  struct _UNICODE_STRING *v30; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v31; // rcx
  NTSTATUS ReparseData; // r14d
  struct _UNICODE_STRING *v33; // rdx
  struct _UNICODE_STRING *v34; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v35; // rcx
  PVOID v36; // rcx
  struct _ECP_LIST *v37; // r12
  NTSTATUS v38; // eax
  PVOID v39; // r14
  _DWORD *v40; // rcx
  const char *v41; // rax
  __int64 v42; // r8
  NTSTATUS Parameter; // r15d
  __int64 v44; // r8
  const char *v45; // rcx
  struct _UNICODE_STRING *v46; // rdx
  struct _UNICODE_STRING *v47; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v48; // rcx
  PVOID v49; // rcx
  _OWORD *v50; // rax
  __int64 *v51; // rax
  __int64 HostSilo; // rax
  __int64 v53; // rax
  UnionFs::UfsEaTable *v54; // rcx
  utl::_RefCountBase *v55; // r15
  utl::_RefCountBase *v56; // rdx
  __int64 EaLength; // r8
  struct _FILE_OBJECT *EaBuffer; // r13
  struct _FILE_OBJECT *v59; // rax
  struct _FILE_OBJECT **v60; // rax
  struct _ERESOURCE *v61; // rcx
  struct _UNICODE_STRING *v62; // rdx
  struct _UNICODE_STRING *v63; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v64; // rcx
  PVOID v65; // rcx
  int EAs; // eax
  struct _ERESOURCE *v67; // rcx
  struct _UNICODE_STRING *v68; // rdx
  struct _UNICODE_STRING *v69; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v70; // rcx
  PVOID v71; // rcx
  ULONG CreateOptions; // ecx
  ULONG FileAttributes; // r9d
  unsigned int v74; // edx
  int v75; // r8d
  struct UnionFs::StackEventTracer *v76; // r9
  NTSTATUS v77; // r13d
  void *v78; // rax
  PVOID v79; // rcx
  struct _ERESOURCE *v80; // rcx
  struct _UNICODE_STRING *v81; // rdx
  struct _UNICODE_STRING *v82; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v83; // rcx
  PVOID v84; // rcx
  const struct _UNICODE_STRING *v85; // rax
  PVOID v86; // rcx
  struct _ERESOURCE *v87; // rcx
  struct _UNICODE_STRING *v88; // rdx
  struct _UNICODE_STRING *v89; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v90; // rcx
  PVOID v91; // rcx
  struct UnionFs::StackEventTracer *v92; // r9
  UnionFs::Utils *v93; // r13
  __int64 v94; // rax
  PVOID v95; // rcx
  struct _ERESOURCE *v96; // rcx
  struct _UNICODE_STRING *v97; // rdx
  struct _UNICODE_STRING *v98; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v99; // rcx
  int v100; // r15d
  PVOID v101; // rcx
  struct _ERESOURCE *v102; // rcx
  struct _UNICODE_STRING *v103; // rdx
  struct _UNICODE_STRING *v104; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v105; // rcx
  PVOID v106; // rcx
  struct _ERESOURCE *v107; // rcx
  struct _UNICODE_STRING *v108; // rdx
  struct _UNICODE_STRING *v109; // rbx
  void *v110; // rcx
  PVOID v111; // rcx
  struct _ERESOURCE *v112; // rcx
  struct _UNICODE_STRING *v113; // rdx
  struct _UNICODE_STRING *v114; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v115; // rcx
  ULONG CleanupCallback; // [rsp+20h] [rbp-E0h]
  const char *LookasideList; // [rsp+28h] [rbp-D8h]
  const char *LookasideLista; // [rsp+28h] [rbp-D8h]
  const char *LookasideListb; // [rsp+28h] [rbp-D8h]
  char *LookasideListc; // [rsp+28h] [rbp-D8h]
  const char *LookasideListd; // [rsp+28h] [rbp-D8h]
  const char *LookasideListe; // [rsp+28h] [rbp-D8h]
  const char *LookasideListf; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp-80h] BYREF
  char v125; // [rsp+88h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+90h] [rbp-70h] BYREF
  PVOID EcpContext; // [rsp+A0h] [rbp-60h]
  PVOID P; // [rsp+A8h] [rbp-58h] BYREF
  char v129; // [rsp+B0h] [rbp-50h] BYREF
  char v130; // [rsp+B1h] [rbp-4Fh] BYREF
  PVOID v131; // [rsp+B8h] [rbp-48h] BYREF
  PERESOURCE v132; // [rsp+C0h] [rbp-40h] BYREF
  PVOID v133; // [rsp+C8h] [rbp-38h] BYREF
  PVOID v134; // [rsp+D0h] [rbp-30h] BYREF
  struct _ERESOURCE *FileInformation; // [rsp+D8h] [rbp-28h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v137; // [rsp+E8h] [rbp-18h] BYREF
  int v138; // [rsp+F0h] [rbp-10h] BYREF
  int v139; // [rsp+F8h] [rbp-8h] BYREF
  int v140; // [rsp+FCh] [rbp-4h] BYREF
  PFLT_INSTANCE Instance; // [rsp+100h] [rbp+0h]
  utl::_RefCountBase *v142; // [rsp+108h] [rbp+8h] BYREF
  utl::_RefCountBase *v143; // [rsp+110h] [rbp+10h]
  PFILE_OBJECT FileObject[2]; // [rsp+118h] [rbp+18h] BYREF
  char v145; // [rsp+128h] [rbp+28h]
  PVOID v146; // [rsp+130h] [rbp+30h] BYREF
  PECP_LIST EcpList; // [rsp+138h] [rbp+38h] BYREF
  utl::_RefCountBase *v148[2]; // [rsp+140h] [rbp+40h] BYREF
  PERESOURCE Resource; // [rsp+150h] [rbp+50h]
  const char *v150; // [rsp+160h] [rbp+60h] BYREF
  const struct _UNICODE_STRING *v151; // [rsp+168h] [rbp+68h] BYREF
  struct _FILE_OBJECT *v152; // [rsp+170h] [rbp+70h] BYREF
  __int64 v153; // [rsp+178h] [rbp+78h]
  __int128 v154; // [rsp+180h] [rbp+80h] BYREF
  __int64 v155; // [rsp+190h] [rbp+90h]
  void **v156; // [rsp+198h] [rbp+98h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v158; // [rsp+1C0h] [rbp+C0h]
  _QWORD v159[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v160; // [rsp+1E8h] [rbp+E8h]
  _QWORD v161[13]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v162; // [rsp+258h] [rbp+158h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+260h] [rbp+160h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+290h] [rbp+190h] BYREF
  __int128 v165; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v166; // [rsp+2B0h] [rbp+1B0h]

  Instance = a4;
  v155 = a2;
  v151 = a1;
  v153 = (__int64)a6;
  v156 = a8;
  if ( a8 )
  {
    v10 = *a8;
    *a8 = 0;
    if ( v10 )
      ObfDereferenceObject(v10);
  }
  v11 = ((_DWORD)a6[6] & 1u) + 6;
  v12 = **(struct _ERESOURCE ***)(a2 + 8);
  *(_OWORD *)Object = 0;
  v13 = *a3;
  FileInformation = v12;
  EcpContext = 0;
  *(_OWORD *)FileObject = v13;
  v14 = UnionFs::Utils::OpenAsReparsePoint(v12, FileObject, 2147614720LL, v11, Object);
  if ( v14 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v14,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x26000211ABALL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: Opening source file",
      (const char *)a7);
LABEL_6:
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v15 = Object[1];
    Object[1] = 0;
    if ( v15 )
      ObfDereferenceObject(v15);
    if ( Object[0] )
      FltClose(Object[0]);
    return (unsigned int)v14;
  }
  v148[1] = (utl::_RefCountBase *)Object[1];
  FileNameInformation = 0;
  v148[0] = 0;
  Resource = v12;
  v14 = UnionFs::Utils::GetFileNameInformation(v148, 1025, &FileNameInformation, a7);
  if ( v14 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v14,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x62D00211AC9LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: Getting source file name information",
      (const char *)a7);
    v17 = FileNameInformation;
    FileNameInformation = 0;
    if ( v17 )
      FltReleaseFileNameInformation(v17);
    goto LABEL_6;
  }
  P = 0;
  Security = UnionFs::UfsPathName::Copy(SourceString);
  if ( Security < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Security,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x63B00211AD1LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: Copying target name",
      (const char *)a7);
    v21 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v20);
      ExFreePoolWithTag(v21, 0);
    }
    v22 = FileNameInformation;
    FileNameInformation = 0;
    if ( v22 )
      FltReleaseFileNameInformation(v22);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v23 = Object[1];
    Object[1] = 0;
LABEL_26:
    if ( v23 )
      ObfDereferenceObject(v23);
    if ( Object[0] )
      FltClose(Object[0]);
    return (unsigned int)Security;
  }
  v24 = P;
  v25 = UnionFs::Utils::RemoveFinalComponent(
          (UnionFs::Utils *)P,
          (struct _UNICODE_STRING *)*((unsigned __int16 *)P + 12),
          0,
          v19);
  v24[20] -= v25;
  v24[28] += v25;
  UnionFs::UfsPathName::AppendPath(
    (UnionFs::UfsPathName *)P,
    &FileNameInformation->FinalComponent,
    (struct _UNICODE_STRING *)a7);
  UnionFs::UfsPathName::AppendUnicodeString(
    (PCUNICODE_STRING)P,
    &FileNameInformation->Stream,
    (struct UnionFs::StackEventTracer *)a7);
  v26 = 0;
  v27 = 0;
  v134 = 0;
  v28 = *(_OWORD *)P;
  v140 = *((_DWORD *)a6 + 12) | 4;
  v154 = v28;
  if ( (v140 & 8) == 0 )
  {
    Security = UnionFs::Utils::QuerySecurity((PFLT_INSTANCE)v12, (PFILE_OBJECT)Object[1], 0x10000u);
    if ( Security < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Security,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x28300211AF0LL,
        (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
        "PUSH: Getting source security descriptor",
        (const char *)a7);
      if ( v134 )
        ExFreePoolWithTag(v134, 0);
      v30 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v30, v29);
        ExFreePoolWithTag(v30, 0);
      }
      v31 = FileNameInformation;
      FileNameInformation = 0;
      if ( v31 )
        FltReleaseFileNameInformation(v31);
      if ( EcpContext )
        FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
      v23 = Object[1];
      Object[1] = 0;
      goto LABEL_26;
    }
    v27 = v134;
  }
  EcpList = 0;
  ReparseData = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
  if ( ReparseData < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)ReparseData,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x10A00211AF7LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "API: FltAllocateExtraCreateParameterList",
      (const char *)a7);
LABEL_47:
    if ( v27 )
      ExFreePoolWithTag(v27, 0);
    v34 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v34, v33);
      ExFreePoolWithTag(v34, 0);
    }
    v35 = FileNameInformation;
    FileNameInformation = 0;
    if ( v35 )
      FltReleaseFileNameInformation(v35);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v36 = Object[1];
    Object[1] = 0;
    if ( v36 )
      ObfDereferenceObject(v36);
    if ( Object[0] )
      FltClose(Object[0]);
    return (unsigned int)ReparseData;
  }
  v37 = EcpList;
  v133 = 0;
  v38 = FltAllocateExtraCreateParameterFromLookasideList(
          *(PFLT_FILTER *)UnionFs::g_FilterState,
          &GUID_ECP_ATOMIC_CREATE,
          0x58u,
          0,
          0,
          (char *)UnionFs::g_FilterState + 1984,
          &v133);
  ReparseData = v38;
  if ( v38 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v38,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x10B00211B09LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "API: FltAllocateExtraCreateParameterFromLookasideList",
      LookasideList);
LABEL_64:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
    goto LABEL_47;
  }
  memset(v133, 0, 0x58u);
  v137 = 0;
  v138 = 0;
  *(_WORD *)v133 = 88;
  v39 = 0;
  *((_WORD *)v133 + 1) |= 0x400u;
  *((_WORD *)v133 + 1) |= 0x200u;
  v40 = EcpContext;
  v165 = 0;
  v150 = (const char *)EcpContext;
  v166 = 0;
  *((_QWORD *)&v166 + 1) = *((_QWORD *)EcpContext + 6);
  v165 = *(_OWORD *)((char *)EcpContext + 24);
  *(_QWORD *)&v166 = *((_QWORD *)EcpContext + 5);
  *((_QWORD *)v133 + 4) = &v165;
  *((_WORD *)v133 + 1) |= 0x10u;
  if ( (v40[18] & 0x400) != 0 )
  {
    ReparseData = UnionFs::Utils::GetReparseData((PFLT_INSTANCE)v12, (PFILE_OBJECT)Object[1], CleanupCallback);
    if ( ReparseData < 0 )
    {
      v41 = "PUSH: Getting layer reparse data";
      v42 = 0x28400211B23LL;
      goto LABEL_68;
    }
    v39 = v137;
    if ( v137 )
    {
      ReparseData = UnionFs::Utils::VirtualizeReparseData(&v137, &v138, *a6, a7);
      if ( ReparseData < 0 )
      {
        v41 = "PUSH: Munging reparse data";
        v42 = 0x6C500211B30LL;
LABEL_68:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)ReparseData,
          (int)a7,
          (struct UnionFs::StackEventTracer *)v42,
          (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
          v41,
          LookasideList);
        if ( v137 )
          ExFreePoolWithTag(v137, 0);
        goto LABEL_64;
      }
      v39 = v137;
      *((_WORD *)v133 + 1) |= 2u;
      *((_WORD *)v133 + 3) = v138;
      *((_QWORD *)v133 + 1) = v39;
    }
  }
  Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpList, v133);
  if ( Parameter < 0 )
  {
    v44 = 0x10C00211B3BLL;
LABEL_76:
    v45 = "API: FltInsertExtraCreateParameter";
LABEL_77:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)Parameter,
      (int)a7,
      (struct UnionFs::StackEventTracer *)v44,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      v45,
      LookasideList);
LABEL_78:
    if ( v39 )
      ExFreePoolWithTag(v39, 0);
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
    if ( v27 )
      ExFreePoolWithTag(v27, 0);
    v47 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v47, v46);
      ExFreePoolWithTag(v47, 0);
    }
    v48 = FileNameInformation;
    FileNameInformation = 0;
    if ( v48 )
      FltReleaseFileNameInformation(v48);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v49 = Object[1];
    Object[1] = 0;
    if ( v49 )
      ObfDereferenceObject(v49);
    if ( Object[0] )
      FltClose(Object[0]);
    return (unsigned int)Parameter;
  }
  v146 = 0;
  Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                *(PFLT_FILTER *)UnionFs::g_FilterState,
                &GUID_ECP_DUAL_OPLOCK_KEY,
                0x24u,
                0,
                0,
                (char *)UnionFs::g_FilterState + 2368,
                &v146);
  if ( Parameter < 0 )
  {
    v45 = "API: FltAllocateExtraCreateParameterFromLookasideList";
    v44 = 0x62400211B49LL;
    goto LABEL_77;
  }
  v50 = v146;
  *(_OWORD *)v146 = 0;
  v50[1] = 0;
  *((_DWORD *)v50 + 8) = 0;
  *((_OWORD *)v146 + 1) = UNIONFS_GUID_ECP_OPLOCK_KEY;
  *((_BYTE *)v146 + 33) = 1;
  Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpList, v146);
  if ( Parameter < 0 )
  {
    v44 = 0x62200211B52LL;
    goto LABEL_76;
  }
  v158 = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  v51 = (__int64 *)a6[1];
  if ( v51 )
    HostSilo = *v51;
  else
    HostSilo = PsGetHostSilo();
  v158 = HostSilo;
  v53 = *a6;
  *(_OWORD *)v148 = 0;
  Resource = 0;
  if ( *(_DWORD *)(v53 + 28) == 2 )
    v54 = *(UnionFs::UfsEaTable **)(*(_QWORD *)(v53 + 32) + 24LL);
  else
    v54 = (UnionFs::UfsEaTable *)*((_QWORD *)UnionFs::g_FilterState + 11);
  Parameter = UnionFs::UfsEaTable::LookupEaEntry(
                v54,
                Instance,
                (const struct UnionFs::UfsPathName *)P,
                1,
                (struct UnionFs::LookupEaResults *)v148,
                (struct UnionFs::StackEventTracer *)a7);
  if ( Parameter < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Parameter,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x56C00211B69LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: EA table lookup",
      LookasideLista);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    if ( v148[1] )
      utl::_RefCountBase::_DecStrong(v148[1]);
    goto LABEL_78;
  }
  v55 = v148[1];
  v56 = v148[0];
  v142 = v148[0];
  v143 = v148[1];
  if ( v148[1] )
  {
    _InterlockedIncrement((volatile signed __int32 *)v148[1] + 2);
    v56 = v142;
  }
  v132 = Resource;
  Resource = 0;
  EaLength = *((unsigned int *)EcpContext + 30);
  EaBuffer = (struct _FILE_OBJECT *)*((_QWORD *)EcpContext + 16);
  HIDWORD(FileObject[0]) = 0;
  if ( !EaBuffer && EaLength )
  {
    gsl::details::terminate((gsl::details *)EcpContext);
    JUMPOUT(0x14006DE82LL);
  }
  if ( !v56 )
  {
LABEL_168:
    CreateOptions = 2162728;
    DriverContext.ExtraCreateParameter = EcpList;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityDescriptor = v27;
    ObjectAttributes.RootDirectory = *(HANDLE *)(v153 + 40);
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v154;
    ObjectAttributes.SecurityQualityOfService = 0;
    v139 = 2162728;
    if ( (*((_DWORD *)v150 + 18) & 0x10) != 0 )
    {
      CreateOptions = 2162729;
      v139 = 2162729;
    }
    FileAttributes = *((_DWORD *)v150 + 18) & 0xBFEF;
    v74 = *((_DWORD *)v150 + 18) & 0xFF7F0000;
    if ( v74 )
    {
      *((_DWORD *)v133 + 10) |= v74;
      *((_WORD *)v133 + 1) |= 0x20u;
      CreateOptions = v139;
    }
    FileObject[0] = (PFILE_OBJECT)&v131;
    v131 = 0;
    IoStatusBlock = 0;
    FileObject[1] = 0;
    v145 = 1;
    FileHandle = 0;
    v77 = FltCreateFileEx2(
            *(PFLT_FILTER *)UnionFs::g_FilterState,
            Instance,
            &FileHandle,
            &FileObject[1],
            0x40040000u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes,
            0,
            2u,
            CreateOptions,
            EaBuffer,
            EaLength,
            0,
            &DriverContext);
    if ( v145 )
    {
      v78 = *(void **)FileObject[0];
      *(_QWORD *)FileObject[0] = FileObject[1];
      if ( v78 )
        ObfDereferenceObject(v78);
    }
    v161[0] = &v130;
    v161[1] = &v125;
    v161[2] = v153;
    v161[3] = &v140;
    v161[5] = &P;
    v161[6] = v151;
    v161[8] = &v154;
    v161[9] = &v139;
    v161[10] = FileInformation;
    v161[11] = &v142;
    v161[12] = &v132;
    v130 = 0;
    v125 = 0;
    v161[4] = Instance;
    v161[7] = a7;
    if ( v77 < 0 )
    {
      if ( v77 != -1073741771 && v77 != -1073739511 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v77,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x10D00211CDELL,
          (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
          "API: Creating component in target",
          LookasideListc);
        v162 = 0;
        lambda_a388a843c4de2873654497514a81f9e8_::operator()(v161);
        v79 = v131;
        v131 = 0;
        if ( v79 )
          ObfDereferenceObject(v79);
        if ( FileHandle )
          FltClose(FileHandle);
        if ( v26 )
          ExFreePoolWithTag(v26, 0);
        v80 = v132;
        v132 = 0;
        if ( v80 )
        {
          ExReleaseResourceLite(v80);
          KeLeaveCriticalRegion();
        }
        if ( v143 )
          utl::_RefCountBase::_DecStrong(v143);
        if ( v55 )
          utl::_RefCountBase::_DecStrong(v55);
        if ( v39 )
          ExFreePoolWithTag(v39, 0);
        FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
        if ( v27 )
          ExFreePoolWithTag(v27, 0);
        v82 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v82, v81);
          ExFreePoolWithTag(v82, 0);
        }
        v83 = FileNameInformation;
        FileNameInformation = 0;
        if ( v83 )
          FltReleaseFileNameInformation(v83);
        if ( EcpContext )
          FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
        v84 = Object[1];
        Object[1] = 0;
        if ( v84 )
          ObfDereferenceObject(v84);
        if ( Object[0] )
          FltClose(Object[0]);
        return (unsigned int)v77;
      }
      if ( (unsigned int)dword_14009E178 > 4 )
      {
        LODWORD(v134) = v77;
        LODWORD(FileInformation) = 7382;
        v85 = (const struct _UNICODE_STRING *)&v154;
        v137 = (PVOID)"UnionFs::Utils::CopyItemPriv";
        if ( !*((_QWORD *)&v154 + 1) )
          v85 = &FsTlEmptyUnicodeString;
        v151 = v85;
        v150 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
        v152 = (struct _FILE_OBJECT *)"Destination already exists";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)byte_140099D39,
          v75,
          (unsigned int)"UnionFs::Utils::CopyItemPriv",
          (__int64)&v152,
          (__int64)&v137,
          (__int64)&v150,
          (__int64)&FileInformation,
          (__int64)&v134,
          (__int64)&v151);
      }
      v125 = 1;
      v162 = 0;
      lambda_a388a843c4de2873654497514a81f9e8_::operator()(v161);
      v86 = v131;
      v131 = 0;
      if ( v86 )
        ObfDereferenceObject(v86);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v26 )
        ExFreePoolWithTag(v26, 0);
      v87 = v132;
      v132 = 0;
      if ( v87 )
      {
        ExReleaseResourceLite(v87);
        KeLeaveCriticalRegion();
      }
      if ( v143 )
        utl::_RefCountBase::_DecStrong(v143);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      if ( v39 )
        ExFreePoolWithTag(v39, 0);
      FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
      if ( v27 )
        ExFreePoolWithTag(v27, 0);
      v89 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v89, v88);
        ExFreePoolWithTag(v89, 0);
      }
      v90 = FileNameInformation;
      FileNameInformation = 0;
      if ( v90 )
        FltReleaseFileNameInformation(v90);
      if ( EcpContext )
        FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
      v91 = Object[1];
      Object[1] = 0;
      if ( v91 )
        ObfDereferenceObject(v91);
      if ( Object[0] )
        FltClose(Object[0]);
      return 0;
    }
    FileObject[1] = (PFILE_OBJECT)&v131;
    FileObject[0] = (PFILE_OBJECT)Instance;
    v145 = 1;
    UnionFs::Utils::SuppressTimestampUpdates(Instance, (struct _FILE_OBJECT *)v131, a7, v76);
    v93 = (UnionFs::Utils *)FileInformation;
    LOWORD(a7[2].Busy) = 0;
    v129 = 0;
    v94 = v155;
    *(_DWORD *)&a7->Type = 0;
    if ( *(_DWORD *)(*(_QWORD *)(v94 + 8) + 24LL) != 30 )
    {
      if ( (int)UnionFs::Utils::SuppressTimestampUpdates(v93, (struct _FILE_OBJECT *)Object[1], a7, v92) >= 0 )
        v129 = 1;
      *(_DWORD *)&a7->Type = 0;
      LOWORD(a7[2].Busy) = 0;
    }
    v159[1] = v93;
    v159[0] = &v129;
    v159[2] = Object;
    v159[3] = a7;
    v160 = 1;
    if ( (*((_DWORD *)v150 + 18) & 0x800) != 0 )
    {
      v77 = UnionFs::Utils::CopyFileCompression(
              v93,
              (const struct _FLT_INSTANCE *)Object[1],
              (const struct _FILE_OBJECT *)Instance,
              (const struct _FLT_INSTANCE *)v131,
              a7,
              (struct UnionFs::StackEventTracer *)LookasideListc);
      if ( v77 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v77,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x28500211D1ALL,
          (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
          "PUSH: Copying compression state",
          LookasideListd);
        wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v159);
        LODWORD(FileInformation) = 3;
        FltSetInformationFile(Instance, (PFILE_OBJECT)v131, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
        v162 = 0;
        lambda_a388a843c4de2873654497514a81f9e8_::operator()(v161);
        v95 = v131;
        v131 = 0;
        if ( v95 )
          ObfDereferenceObject(v95);
        if ( FileHandle )
          FltClose(FileHandle);
        if ( v26 )
          ExFreePoolWithTag(v26, 0);
        v96 = v132;
        v132 = 0;
        if ( v96 )
        {
          ExReleaseResourceLite(v96);
          KeLeaveCriticalRegion();
        }
        if ( v143 )
          utl::_RefCountBase::_DecStrong(v143);
        if ( v55 )
          utl::_RefCountBase::_DecStrong(v55);
        if ( v39 )
          ExFreePoolWithTag(v39, 0);
        FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
        if ( v27 )
          ExFreePoolWithTag(v27, 0);
        v98 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v98, v97);
          ExFreePoolWithTag(v98, 0);
        }
        v99 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_310;
      }
      v93 = (UnionFs::Utils *)FileInformation;
    }
    LookasideListe = (const char *)v131;
    v100 = UnionFs::Utils::CopyItemDataStreams(v93, Object[0], Object[1], Instance, FileHandle);
    if ( v100 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v100,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x26A00211D28LL,
        (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
        "PUSH: Copying file metadata",
        LookasideListe);
      wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v159);
      wil::details::lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___::_lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___(FileObject);
      v162 = 0;
      lambda_a388a843c4de2873654497514a81f9e8_::operator()(v161);
      v101 = v131;
      v131 = 0;
      if ( v101 )
        ObfDereferenceObject(v101);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v26 )
        ExFreePoolWithTag(v26, 0);
      v102 = v132;
      v132 = 0;
      if ( v102 )
      {
        ExReleaseResourceLite(v102);
        KeLeaveCriticalRegion();
      }
      if ( v143 )
        utl::_RefCountBase::_DecStrong(v143);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v148);
      if ( v39 )
        ExFreePoolWithTag(v39, 0);
      FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
      if ( v27 )
        ExFreePoolWithTag(v27, 0);
      v104 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v104, v103);
        ExFreePoolWithTag(v104, 0);
      }
      v105 = FileNameInformation;
      FileNameInformation = 0;
      if ( v105 )
        FltReleaseFileNameInformation(v105);
      v77 = v100;
      goto LABEL_312;
    }
    if ( (v140 & 0x10) == 0
      || (LookasideListf = *(const char **)v153,
          v77 = UnionFs::Utils::CopyHardLinks(v151, v93, Object[1], Instance, v131),
          v77 >= 0) )
    {
      v130 = 1;
      v125 = 1;
      if ( v156 )
      {
        v110 = *v156;
        *v156 = v131;
        v131 = v110;
      }
      v145 = 0;
      wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v159);
      wil::details::lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___::_lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___(FileObject);
      v162 = 0;
      lambda_a388a843c4de2873654497514a81f9e8_::operator()(v161);
      v111 = v131;
      v131 = 0;
      if ( v111 )
        ObfDereferenceObject(v111);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v26 )
        ExFreePoolWithTag(v26, 0);
      v112 = v132;
      v132 = 0;
      if ( v112 )
      {
        ExReleaseResourceLite(v112);
        KeLeaveCriticalRegion();
      }
      if ( v143 )
        utl::_RefCountBase::_DecStrong(v143);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v148);
      if ( v39 )
        ExFreePoolWithTag(v39, 0);
      FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
      if ( v27 )
        ExFreePoolWithTag(v27, 0);
      v114 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v114, v113);
        ExFreePoolWithTag(v114, 0);
      }
      v115 = FileNameInformation;
      FileNameInformation = 0;
      if ( v115 )
        FltReleaseFileNameInformation(v115);
      UnionFs::Utils::OpenAsReparsePointResults::~OpenAsReparsePointResults((UnionFs::Utils::OpenAsReparsePointResults *)Object);
      return 0;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v77,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x3A600211D39LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: Copying hard links",
      LookasideListf);
    wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v159);
    wil::details::lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___::_lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___(FileObject);
    v162 = 0;
    lambda_a388a843c4de2873654497514a81f9e8_::operator()(v161);
    v106 = v131;
    v131 = 0;
    if ( v106 )
      ObfDereferenceObject(v106);
    if ( FileHandle )
      FltClose(FileHandle);
    if ( v26 )
      ExFreePoolWithTag(v26, 0);
    v107 = v132;
    v132 = 0;
    if ( v107 )
    {
      ExReleaseResourceLite(v107);
      KeLeaveCriticalRegion();
    }
    if ( v143 )
      utl::_RefCountBase::_DecStrong(v143);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v148);
    if ( v39 )
      ExFreePoolWithTag(v39, 0);
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
    if ( v27 )
      ExFreePoolWithTag(v27, 0);
    v109 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v109, v108);
      ExFreePoolWithTag(v109, 0);
    }
    v99 = FileNameInformation;
    FileNameInformation = 0;
LABEL_310:
    if ( v99 )
      FltReleaseFileNameInformation(v99);
LABEL_312:
    UnionFs::Utils::OpenAsReparsePointResults::~OpenAsReparsePointResults((UnionFs::Utils::OpenAsReparsePointResults *)Object);
    return (unsigned int)v77;
  }
  v59 = (struct _FILE_OBJECT *)*((unsigned int *)v56 + 16);
  LODWORD(v134) = 0;
  v152 = v59;
  v60 = (struct _FILE_OBJECT **)utl::make_unique_pool<enum gsl::byte [0],256,1634027093,0>(&v137, v59);
  EaBuffer = *v60;
  *v60 = 0;
  if ( v137 )
    ExFreePoolWithTag(v137, 0);
  if ( !EaBuffer )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x64500211B80LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "ORIGIN: Allocating EA buffer",
      LookasideLista);
    v61 = v132;
    v132 = 0;
    if ( v61 )
    {
      ExReleaseResourceLite(v61);
      KeLeaveCriticalRegion();
    }
    if ( v143 )
      utl::_RefCountBase::_DecStrong(v143);
    if ( v55 )
      utl::_RefCountBase::_DecStrong(v55);
    if ( v39 )
      ExFreePoolWithTag(v39, 0);
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
    if ( v27 )
      ExFreePoolWithTag(v27, 0);
    v63 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v63, v62);
      ExFreePoolWithTag(v63, 0);
    }
    v64 = FileNameInformation;
    FileNameInformation = 0;
    if ( v64 )
      FltReleaseFileNameInformation(v64);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v65 = Object[1];
    Object[1] = 0;
    if ( v65 )
      ObfDereferenceObject(v65);
    if ( Object[0] )
      FltClose(Object[0]);
    return 3221225626LL;
  }
  v137 = (PVOID)(unsigned int)v152;
  FileObject[0] = v152;
  v26 = EaBuffer;
  FileObject[1] = EaBuffer;
  EAs = UnionFs::UfsEaPayload::GetEAs((__int64)v142, 0, FileObject, (unsigned int *)&v134, 0, 0, 1);
  LODWORD(v134) = EAs;
  if ( EAs == -1073741742 )
  {
    LODWORD(EaLength) = (_DWORD)v137;
    goto LABEL_168;
  }
  if ( EAs >= 0 )
  {
    LODWORD(EaLength) = (_DWORD)v137;
    goto LABEL_168;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)EAs,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x56D00211B8DLL,
    (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
    "PUSH: Copy EAs to buffer",
    LookasideListb);
  ExFreePoolWithTag(EaBuffer, 0);
  v67 = v132;
  v132 = 0;
  if ( v67 )
  {
    ExReleaseResourceLite(v67);
    KeLeaveCriticalRegion();
  }
  if ( v143 )
    utl::_RefCountBase::_DecStrong(v143);
  if ( v55 )
    utl::_RefCountBase::_DecStrong(v55);
  if ( v39 )
    ExFreePoolWithTag(v39, 0);
  FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
  if ( v27 )
    ExFreePoolWithTag(v27, 0);
  v69 = (struct _UNICODE_STRING *)P;
  if ( P )
  {
    if ( !*((_BYTE *)P + 16) )
      *(_OWORD *)P = 0;
    FsFltWil::Details::FreeUnicodeString(v69, v68);
    ExFreePoolWithTag(v69, 0);
  }
  v70 = FileNameInformation;
  FileNameInformation = 0;
  if ( v70 )
    FltReleaseFileNameInformation(v70);
  if ( EcpContext )
    FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
  v71 = Object[1];
  Object[1] = 0;
  if ( v71 )
    ObfDereferenceObject(v71);
  if ( Object[0] )
    FltClose(Object[0]);
  return (unsigned int)v134;
}

```

## disassembly

```asm
0x14006c3ec  push    rbp
0x14006c3ee  push    rbx
0x14006c3ef  push    rsi
0x14006c3f0  push    rdi
0x14006c3f1  push    r12
0x14006c3f3  push    r13
0x14006c3f5  push    r14
0x14006c3f7  push    r15
0x14006c3f9  lea     rbp, [rsp-1D8h]
0x14006c401  sub     rsp, 2D8h
0x14006c408  mov     rax, cs:__security_cookie
0x14006c40f  xor     rax, rsp
0x14006c412  mov     [rbp+210h+var_50], rax
0x14006c419  mov     rax, [rbp+210h+arg_38]
0x14006c420  xor     r12d, r12d
0x14006c423  mov     r13, [rbp+210h+arg_28]
0x14006c42a  mov     rbx, r8
0x14006c42d  mov     rsi, [rbp+210h+arg_30]
0x14006c434  mov     r14, rdx
0x14006c437  mov     rdi, [rbp+210h+SourceString]
0x14006c43e  mov     [rbp+210h+Instance], r9
0x14006c442  mov     [rbp+210h+var_180], rdx
0x14006c449  mov     [rbp+210h+var_1A8], rcx
0x14006c44d  mov     [rbp+210h+var_198], r13
0x14006c451  mov     [rbp+210h+var_178], rax
0x14006c458  test    rax, rax
0x14006c45b  jz      short loc_14006C474
0x14006c45d  mov     rcx, [rax]; Object
0x14006c460  mov     [rax], r12
0x14006c463  test    rcx, rcx
0x14006c466  jz      short loc_14006C474
0x14006c468  call    cs:__imp_ObfDereferenceObject
0x14006c46f  nop     dword ptr [rax+rax+00h]
0x14006c474  mov     rax, [r14+8]
0x14006c478  lea     rdx, [rbp+210h+FileObject]
0x14006c47c  mov     r9d, [r13+30h]
0x14006c480  xorps   xmm0, xmm0
0x14006c483  and     r9d, 1
0x14006c487  mov     r8d, 80020000h
0x14006c48d  add     r9d, 6
0x14006c491  mov     r15, [rax]
0x14006c494  mov     rax, [r13+20h]
0x14006c498  mov     rcx, r15
0x14006c49b  mov     [rsp+310h+AllocationSize], rax
0x14006c4a0  mov     rax, [r13+8]
0x14006c4a4  mov     [rsp+310h+IoStatusBlock], rax
0x14006c4a9  lea     rax, [rbp+210h+Object]
0x14006c4ad  movdqu  xmmword ptr [rbp+210h+Object], xmm0
0x14006c4b2  mov     [rsp+310h+LookasideList], rsi; char *
0x14006c4b7  movups  xmm0, xmmword ptr [rbx]
0x14006c4ba  mov     [rsp+310h+CleanupCallback], rax
0x14006c4bf  mov     [rbp+210h+FileInformation], r15
0x14006c4c3  mov     [rbp+210h+EcpContext], r12
0x14006c4c7  movdqu  xmmword ptr [rbp+210h+FileObject], xmm0
0x14006c4cc  call    ?OpenAsReparsePoint@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KW4OpenAsReparsePointFlags@12@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@PEAX@Z; UnionFs::Utils::OpenAsReparsePoint(_FLT_INSTANCE const &,_UNICODE_STRING const &,ulong,UnionFs::Utils::OpenAsReparsePointFlags,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,void *)
0x14006c4d1  mov     ebx, eax
0x14006c4d3  test    eax, eax
0x14006c4d5  jns     short loc_14006C552
0x14006c4d7  lea     rax, aPushOpeningSou; "PUSH: Opening source file"
0x14006c4de  mov     r8, 26000211ABAh; struct UnionFs::StackEventTracer *
0x14006c4e8  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CopyItemPriv"
0x14006c4ef  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c4f4  mov     rdx, rsi; int
0x14006c4f7  mov     ecx, ebx; this
0x14006c4f9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c4fe  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c502  test    rdx, rdx
0x14006c505  jz      short loc_14006C51D
0x14006c507  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c50e  mov     rcx, [rcx]; Filter
0x14006c511  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c518  nop     dword ptr [rax+rax+00h]
0x14006c51d  mov     rcx, [rbp+210h+Object+8]; Object
0x14006c521  mov     [rbp+210h+Object+8], r12
0x14006c525  test    rcx, rcx
0x14006c528  jz      short loc_14006C536
0x14006c52a  call    cs:__imp_ObfDereferenceObject
0x14006c531  nop     dword ptr [rax+rax+00h]
0x14006c536  mov     rcx, [rbp+210h+Object]; FileHandle
0x14006c53a  test    rcx, rcx
0x14006c53d  jz      short loc_14006C54B
0x14006c53f  call    cs:__imp_FltClose
0x14006c546  nop     dword ptr [rax+rax+00h]
0x14006c54b  mov     eax, ebx
0x14006c54d  jmp     loc_14006DE59
0x14006c552  mov     rax, [rbp+210h+Object+8]
0x14006c556  lea     r8, [rbp+210h+FileNameInformation]
0x14006c55a  mov     r9, rsi
0x14006c55d  mov     [rbp+210h+var_1D0+8], rax
0x14006c561  mov     edx, 401h
0x14006c566  mov     [rbp+210h+FileNameInformation], r12
0x14006c56a  lea     rcx, [rbp+210h+var_1D0]
0x14006c56e  mov     [rbp+210h+var_1D0], r12
0x14006c572  mov     [rbp+210h+Resource], r15
0x14006c576  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14006c57b  mov     ebx, eax
0x14006c57d  test    eax, eax
0x14006c57f  jns     short loc_14006C5CA
0x14006c581  lea     rax, aPushGettingSou_0; "PUSH: Getting source file name informat"...
0x14006c588  mov     r8, 62D00211AC9h; struct UnionFs::StackEventTracer *
0x14006c592  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CopyItemPriv"
0x14006c599  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c59e  mov     rdx, rsi; int
0x14006c5a1  mov     ecx, ebx; this
0x14006c5a3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c5a8  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c5ac  mov     [rbp+210h+FileNameInformation], r12
0x14006c5b0  test    rcx, rcx
0x14006c5b3  jz      loc_14006C4FE
0x14006c5b9  call    cs:__imp_FltReleaseFileNameInformation
0x14006c5c0  nop     dword ptr [rax+rax+00h]
0x14006c5c5  jmp     loc_14006C4FE
0x14006c5ca  mov     r8, rsi
0x14006c5cd  mov     [rbp+210h+P], r12
0x14006c5d1  lea     rdx, [rbp+210h+P]
0x14006c5d5  mov     rcx, rdi; SourceString
0x14006c5d8  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14006c5dd  mov     edi, eax
0x14006c5df  test    eax, eax
0x14006c5e1  jns     loc_14006C6A9
0x14006c5e7  lea     rax, aPushCopyingTar; "PUSH: Copying target name"
0x14006c5ee  mov     r8, 63B00211AD1h; struct UnionFs::StackEventTracer *
0x14006c5f8  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CopyItemPriv"
0x14006c5ff  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c604  mov     rdx, rsi; int
0x14006c607  mov     ecx, edi; this
0x14006c609  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c60e  mov     rbx, [rbp+210h+P]
0x14006c612  test    rbx, rbx
0x14006c615  jz      short loc_14006C63C
0x14006c617  cmp     [rbx+10h], r12b
0x14006c61b  jnz     short loc_14006C623
0x14006c61d  xorps   xmm0, xmm0
0x14006c620  movups  xmmword ptr [rbx], xmm0
0x14006c623  mov     rcx, rbx; UnicodeString
0x14006c626  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006c62b  xor     edx, edx; Tag
0x14006c62d  mov     rcx, rbx; P
0x14006c630  call    cs:__imp_ExFreePoolWithTag
0x14006c637  nop     dword ptr [rax+rax+00h]
0x14006c63c  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c640  mov     [rbp+210h+FileNameInformation], r12
0x14006c644  test    rcx, rcx
0x14006c647  jz      short loc_14006C655
0x14006c649  call    cs:__imp_FltReleaseFileNameInformation
0x14006c650  nop     dword ptr [rax+rax+00h]
0x14006c655  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c659  test    rdx, rdx
0x14006c65c  jz      short loc_14006C674
0x14006c65e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c665  mov     rcx, [rcx]; Filter
0x14006c668  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c66f  nop     dword ptr [rax+rax+00h]
0x14006c674  mov     rcx, [rbp+210h+Object+8]; Object
0x14006c678  mov     [rbp+210h+Object+8], r12
0x14006c67c  test    rcx, rcx
0x14006c67f  jz      short loc_14006C68D
0x14006c681  call    cs:__imp_ObfDereferenceObject
0x14006c688  nop     dword ptr [rax+rax+00h]
0x14006c68d  mov     rcx, [rbp+210h+Object]; FileHandle
0x14006c691  test    rcx, rcx
0x14006c694  jz      short loc_14006C6A2
0x14006c696  call    cs:__imp_FltClose
0x14006c69d  nop     dword ptr [rax+rax+00h]
0x14006c6a2  mov     eax, edi
0x14006c6a4  jmp     loc_14006DE59
0x14006c6a9  mov     rbx, [rbp+210h+P]
0x14006c6ad  xor     r8d, r8d; unsigned __int16
0x14006c6b0  mov     rcx, rbx; this
0x14006c6b3  movzx   edx, word ptr [rbx+18h]; struct _UNICODE_STRING *
0x14006c6b7  call    ?RemoveFinalComponent@Utils@UnionFs@@YAGAEAU_UNICODE_STRING@@GPEAU3@@Z; UnionFs::Utils::RemoveFinalComponent(_UNICODE_STRING &,ushort,_UNICODE_STRING *)
0x14006c6bc  sub     [rbx+28h], ax
0x14006c6c0  mov     r8, rsi; struct _UNICODE_STRING *
0x14006c6c3  add     [rbx+38h], ax
0x14006c6c7  mov     rdx, [rbp+210h+FileNameInformation]
0x14006c6cb  mov     rcx, [rbp+210h+P]; this
0x14006c6cf  add     rdx, 58h ; 'X'; Source
0x14006c6d3  call    ?AppendPath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AppendPath(_UNICODE_STRING const &,UnionFs::StackEventTracer &)
0x14006c6d8  mov     rdx, [rbp+210h+FileNameInformation]
0x14006c6dc  mov     r8, rsi; struct UnionFs::StackEventTracer *
0x14006c6df  mov     rcx, [rbp+210h+P]; SourceString
0x14006c6e3  add     rdx, 48h ; 'H'; Source
0x14006c6e7  call    ?AppendUnicodeString@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AppendUnicodeString(_UNICODE_STRING const &,UnionFs::StackEventTracer &)
0x14006c6ec  mov     rax, [rbp+210h+P]
0x14006c6f0  xor     ebx, ebx
0x14006c6f2  mov     edi, ebx
0x14006c6f4  mov     [rbp+210h+var_240], rbx
0x14006c6f8  movups  xmm0, xmmword ptr [rax]
0x14006c6fb  mov     eax, [r13+30h]
0x14006c6ff  or      eax, 4
0x14006c702  mov     [rbp+210h+var_214], eax
0x14006c705  movdqu  [rbp+210h+var_190], xmm0
0x14006c70d  test    al, 8
0x14006c70f  jnz     loc_14006C7F1
0x14006c715  mov     rdx, [rbp+210h+Object+8]; FileObject
0x14006c719  lea     r8, [rbp+210h+var_240]
0x14006c71d  mov     r9, rsi
0x14006c720  mov     dword ptr [rsp+310h+CleanupCallback], 10000h; SecurityInformation
0x14006c728  mov     rcx, r15; Instance
0x14006c72b  call    ?QuerySecurity@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::QuerySecurity(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &,UnionFs::StackEventTracer &,ulong)
0x14006c730  mov     edi, eax
0x14006c732  test    eax, eax
0x14006c734  jns     loc_14006C7ED
0x14006c73a  lea     rax, aPushGettingSou; "PUSH: Getting source security descripto"...
0x14006c741  mov     r8, 28300211AF0h; struct UnionFs::StackEventTracer *
0x14006c74b  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CopyItemPriv"
0x14006c752  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c757  mov     rdx, rsi; int
0x14006c75a  mov     ecx, edi; this
0x14006c75c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c761  mov     rcx, [rbp+210h+var_240]; P
0x14006c765  test    rcx, rcx
0x14006c768  jz      short loc_14006C778
0x14006c76a  xor     edx, edx; Tag
0x14006c76c  call    cs:__imp_ExFreePoolWithTag
0x14006c773  nop     dword ptr [rax+rax+00h]
0x14006c778  mov     rbx, [rbp+210h+P]
0x14006c77c  xor     esi, esi
0x14006c77e  test    rbx, rbx
0x14006c781  jz      short loc_14006C7A8
0x14006c783  cmp     [rbx+10h], sil
0x14006c787  jnz     short loc_14006C78F
0x14006c789  xorps   xmm0, xmm0
0x14006c78c  movups  xmmword ptr [rbx], xmm0
0x14006c78f  mov     rcx, rbx; UnicodeString
0x14006c792  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006c797  xor     edx, edx; Tag
0x14006c799  mov     rcx, rbx; P
0x14006c79c  call    cs:__imp_ExFreePoolWithTag
0x14006c7a3  nop     dword ptr [rax+rax+00h]
0x14006c7a8  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c7ac  mov     [rbp+210h+FileNameInformation], rsi
0x14006c7b0  test    rcx, rcx
0x14006c7b3  jz      short loc_14006C7C1
0x14006c7b5  call    cs:__imp_FltReleaseFileNameInformation
0x14006c7bc  nop     dword ptr [rax+rax+00h]
0x14006c7c1  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c7c5  test    rdx, rdx
0x14006c7c8  jz      short loc_14006C7E0
0x14006c7ca  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c7d1  mov     rcx, [rcx]; Filter
0x14006c7d4  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c7db  nop     dword ptr [rax+rax+00h]
0x14006c7e0  mov     rcx, [rbp+210h+Object+8]
0x14006c7e4  mov     [rbp+210h+Object+8], rsi
0x14006c7e8  jmp     loc_14006C67C
0x14006c7ed  mov     rdi, [rbp+210h+var_240]
0x14006c7f1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c7f8  lea     r8, [rbp+210h+EcpList]; EcpList
0x14006c7fc  mov     [rbp+210h+EcpList], rbx
0x14006c800  xor     edx, edx; Flags
0x14006c802  mov     rcx, [rcx]; Filter
0x14006c805  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14006c80c  nop     dword ptr [rax+rax+00h]
0x14006c811  mov     r14d, eax
0x14006c814  test    eax, eax
0x14006c816  jns     loc_14006C8F8
0x14006c81c  lea     rax, aApiFltallocate; "API: FltAllocateExtraCreateParameterLis"...
0x14006c823  mov     r8, 10A00211AF7h; struct UnionFs::StackEventTracer *
0x14006c82d  lea     r9, aUnionfsUtilsCo_1; "UnionFs::Utils::CopyItemPriv"
0x14006c834  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c839  mov     rdx, rsi; int
0x14006c83c  mov     ecx, r14d; this
0x14006c83f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c844  test    rdi, rdi
0x14006c847  jz      short loc_14006C85A
0x14006c849  xor     edx, edx; Tag
0x14006c84b  mov     rcx, rdi; P
0x14006c84e  call    cs:__imp_ExFreePoolWithTag
0x14006c855  nop     dword ptr [rax+rax+00h]
0x14006c85a  mov     rbx, [rbp+210h+P]
0x14006c85e  xor     edi, edi
0x14006c860  test    rbx, rbx
0x14006c863  jz      short loc_14006C88A
0x14006c865  cmp     [rbx+10h], dil
0x14006c869  jnz     short loc_14006C871
0x14006c86b  xorps   xmm0, xmm0
0x14006c86e  movups  xmmword ptr [rbx], xmm0
0x14006c871  mov     rcx, rbx; UnicodeString
0x14006c874  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006c879  xor     edx, edx; Tag
0x14006c87b  mov     rcx, rbx; P
0x14006c87e  call    cs:__imp_ExFreePoolWithTag
0x14006c885  nop     dword ptr [rax+rax+00h]
0x14006c88a  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c88e  mov     [rbp+210h+FileNameInformation], rdi
0x14006c892  test    rcx, rcx
0x14006c895  jz      short loc_14006C8A3
0x14006c897  call    cs:__imp_FltReleaseFileNameInformation
0x14006c89e  nop     dword ptr [rax+rax+00h]
0x14006c8a3  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c8a7  test    rdx, rdx
0x14006c8aa  jz      short loc_14006C8C2
0x14006c8ac  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c8b3  mov     rcx, [rcx]; Filter
0x14006c8b6  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c8bd  nop     dword ptr [rax+rax+00h]
0x14006c8c2  mov     rcx, [rbp+210h+Object+8]; Object
0x14006c8c6  mov     [rbp+210h+Object+8], rdi
0x14006c8ca  test    rcx, rcx
  ... truncated ...
```
