# UnionFs::Utils::CopyItemPriv(_FLT_CALLBACK_DATA const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathName const &,_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::Utils::CopyItemParams const &,UnionFs::StackEventTracer &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> *)

- ea: `0x14006c1fc`
- end: `0x14006dc93`
- name: `?CopyItemPriv@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@AEBVUfsPathName@2@AEBU_FLT_INSTANCE@@2AEBUCopyItemParams@12@AEAVStackEventTracer@2@PEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@Z`
- size: `6807`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING SourceString, __int64, struct _FILE_OBJECT *, __int64)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006bca8`
- `0x14006dca0`

## callees

- `0x140003bc0`
- `0x140006064`
- `0x14000f7fc`
- `0x14001012c`
- `0x14001c7e8`
- `0x140021f80`
- `0x140023a3c`
- `0x1400441b4`
- `0x140044374`
- `0x140044748`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005d598`
- `0x140067b88`
- `0x140067c68`
- `0x140067cb4`
- `0x14006b4a4`
- `0x14006b59c`
- `0x14006be68`
- `0x14006c1fc`
- `0x14006e1a4`
- `0x14006fa48`
- `0x140072c08`
- `0x14007579c`
- `0x140075b30`
- `0x140078480`
- `0x140078a98`
- `0x140079c48`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006c440`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c57c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c5ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c65e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c894`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c95c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c98b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c9bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cc6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ccf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ced8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d20f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d265`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d294`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d2c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d42b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d481`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d4b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d4de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d726`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d755`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d783`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d8b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d8e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006daa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dbdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c440`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c57c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c5ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c65e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c894`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c95c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c98b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c9bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cc6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ccf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ce51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ced8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d20f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d265`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d294`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d2c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d42b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d481`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d4b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d4de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d6d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d726`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d755`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d783`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d8b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d8e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006d916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006daa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dbdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc39`
- `ntoskrnl!PsGetHostSilo` at `0x14006cb29`
- `ntoskrnl!PsGetHostSilo` at `0x14006cb29`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c278`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c33a`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c491`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c6df`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ca0c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cda7`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cf57`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d0d5`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d1e4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d313`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d400`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d52f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d6a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d83c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d9f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14006db5f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c278`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c33a`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c491`
- `ntoskrnl!ObfDereferenceObject` at `0x14006c6df`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ca0c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cda7`
- `ntoskrnl!ObfDereferenceObject` at `0x14006cf57`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d0d5`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d1e4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d313`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d400`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d52f`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d6a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d83c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006d9f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14006db5f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006cbbd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ccba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ce6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d228`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d444`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d6e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d880`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006da3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006dba3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006cbbd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ccba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006ce6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d228`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d444`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d6e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006d880`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006da3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006dba3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006cbc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ccc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ce78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d234`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d450`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d6f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d88c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006da47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dbaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006cbc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ccc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ce78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d234`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d450`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d6f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d88c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006da47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006dbaf`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006c742`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006ca6b`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006c742`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14006ca6b`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006c615`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14006c615`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006c789`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006c975`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cd10`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cec2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d27e`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d49a`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d73f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d8d2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006da8d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dbf5`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006c789`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006c975`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cd10`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006cec2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d27e`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d49a`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d73f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006d8d2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006da8d`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14006dbf5`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006c913`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006cad1`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006c913`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14006cad1`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c321`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c478`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c5e4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c6c6`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c9f3`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cd8e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cf3e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d2fa`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d516`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c321`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c478`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c5e4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c6c6`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006c9f3`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cd8e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006cf3e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d2fa`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14006d516`

## string_xrefs

- `0x14006c2f8`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c3a2`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c408`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c55b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c63d`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c76b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c86e`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c940`: `UnionFs::Utils::CopyItemPriv`
- `0x14006cb9d`: `UnionFs::Utils::CopyItemPriv`
- `0x14006cc97`: `UnionFs::Utils::CopyItemPriv`
- `0x14006ce3b`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d1ab`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d35f`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d633`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d7ee`: `UnionFs::Utils::CopyItemPriv`
- `0x14006d9ab`: `UnionFs::Utils::CopyItemPriv`
- `0x14006c2e7`: `PUSH: Opening source file`
- `0x14006c54a`: `PUSH: Getting source security descriptor`
- `0x14006c3f7`: `PUSH: Copying target name`
- `0x14006c755`: `API: FltAllocateExtraCreateParameterFromLookasideList`
- `0x14006ca7e`: `API: FltAllocateExtraCreateParameterFromLookasideList`
- `0x14006c62c`: `API: FltAllocateExtraCreateParameterList`
- `0x14006c8c9`: `PUSH: Munging reparse data`
- `0x14006c85d`: `PUSH: Getting layer reparse data`
- `0x14006c934`: `API: FltInsertExtraCreateParameter`
- `0x14006d392`: `Destination already exists`
- `0x14006ce25`: `PUSH: Copy EAs to buffer`
- `0x14006d622`: `PUSH: Copying compression state`
- `0x14006d19a`: `API: Creating component in target`
- `0x14006d99a`: `PUSH: Copying hard links`
- `0x14006d7dd`: `PUSH: Copying file metadata`

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
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp-80h] BYREF
  char v126; // [rsp+88h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+90h] [rbp-70h] BYREF
  PVOID EcpContext; // [rsp+A0h] [rbp-60h]
  PVOID P; // [rsp+A8h] [rbp-58h] BYREF
  char v130; // [rsp+B0h] [rbp-50h] BYREF
  char v131; // [rsp+B1h] [rbp-4Fh] BYREF
  PVOID v132; // [rsp+B8h] [rbp-48h] BYREF
  PERESOURCE v133; // [rsp+C0h] [rbp-40h] BYREF
  PVOID v134; // [rsp+C8h] [rbp-38h] BYREF
  PVOID v135; // [rsp+D0h] [rbp-30h] BYREF
  struct _ERESOURCE *FileInformation; // [rsp+D8h] [rbp-28h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v138; // [rsp+E8h] [rbp-18h] BYREF
  int v139; // [rsp+F0h] [rbp-10h] BYREF
  int v140; // [rsp+F8h] [rbp-8h] BYREF
  int v141; // [rsp+FCh] [rbp-4h] BYREF
  PFLT_INSTANCE Instance; // [rsp+100h] [rbp+0h]
  utl::_RefCountBase *v143; // [rsp+108h] [rbp+8h] BYREF
  utl::_RefCountBase *v144; // [rsp+110h] [rbp+10h]
  PFILE_OBJECT FileObject[2]; // [rsp+118h] [rbp+18h] BYREF
  char v146; // [rsp+128h] [rbp+28h]
  PVOID v147; // [rsp+130h] [rbp+30h] BYREF
  PECP_LIST EcpList; // [rsp+138h] [rbp+38h] BYREF
  utl::_RefCountBase *v149[2]; // [rsp+140h] [rbp+40h] BYREF
  PERESOURCE Resource; // [rsp+150h] [rbp+50h]
  const char *v151; // [rsp+160h] [rbp+60h] BYREF
  const struct _UNICODE_STRING *v152; // [rsp+168h] [rbp+68h] BYREF
  struct _FILE_OBJECT *v153; // [rsp+170h] [rbp+70h] BYREF
  __int64 v154; // [rsp+178h] [rbp+78h]
  __int128 v155; // [rsp+180h] [rbp+80h] BYREF
  __int64 v156; // [rsp+190h] [rbp+90h]
  void **v157; // [rsp+198h] [rbp+98h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v159; // [rsp+1C0h] [rbp+C0h]
  _QWORD v160[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v161; // [rsp+1E8h] [rbp+E8h]
  _QWORD v162[13]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v163; // [rsp+258h] [rbp+158h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+260h] [rbp+160h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+290h] [rbp+190h] BYREF
  __int128 v166; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v167; // [rsp+2B0h] [rbp+1B0h]

  Instance = a4;
  v156 = a2;
  v152 = a1;
  v154 = (__int64)a6;
  v157 = a8;
  if ( a8 )
  {
    v10 = *a8;
    *a8 = 0;
    if ( v10 )
      ObfDereferenceObject(v10);
  }
  v11 = ((_DWORD)a6[6] & 1u) + 6;
  v12 = **(struct _ERESOURCE ***)(a2 + 8);
  AllocationSize = (PLARGE_INTEGER)a6[4];
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
      (struct UnionFs::StackEventTracer *)0x26000211A84LL,
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
  v149[1] = (utl::_RefCountBase *)Object[1];
  FileNameInformation = 0;
  v149[0] = 0;
  Resource = v12;
  v14 = UnionFs::Utils::GetFileNameInformation(v149, 1025, &FileNameInformation, a7);
  if ( v14 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v14,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x62D00211A93LL,
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
      (struct UnionFs::StackEventTracer *)0x63B00211A9BLL,
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
  v135 = 0;
  v28 = *(_OWORD *)P;
  v141 = *((_DWORD *)a6 + 12) | 4;
  v155 = v28;
  if ( (v141 & 8) == 0 )
  {
    Security = UnionFs::Utils::QuerySecurity((PFLT_INSTANCE)v12, (PFILE_OBJECT)Object[1], 0x10000u);
    if ( Security < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Security,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x28300211ABALL,
        (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
        "PUSH: Getting source security descriptor",
        (const char *)a7);
      if ( v135 )
        ExFreePoolWithTag(v135, 0);
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
    v27 = v135;
  }
  EcpList = 0;
  ReparseData = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
  if ( ReparseData < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)ReparseData,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x10A00211AC1LL,
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
  v134 = 0;
  v38 = FltAllocateExtraCreateParameterFromLookasideList(
          *(PFLT_FILTER *)UnionFs::g_FilterState,
          &GUID_ECP_ATOMIC_CREATE,
          0x58u,
          0,
          0,
          (char *)UnionFs::g_FilterState + 1984,
          &v134);
  ReparseData = v38;
  if ( v38 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v38,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x10B00211AD3LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "API: FltAllocateExtraCreateParameterFromLookasideList",
      LookasideList);
LABEL_64:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v37);
    goto LABEL_47;
  }
  memset(v134, 0, 0x58u);
  v138 = 0;
  v139 = 0;
  *(_WORD *)v134 = 88;
  v39 = 0;
  *((_WORD *)v134 + 1) |= 0x400u;
  *((_WORD *)v134 + 1) |= 0x200u;
  v40 = EcpContext;
  v166 = 0;
  v151 = (const char *)EcpContext;
  v167 = 0;
  *((_QWORD *)&v167 + 1) = *((_QWORD *)EcpContext + 6);
  v166 = *(_OWORD *)((char *)EcpContext + 24);
  *(_QWORD *)&v167 = *((_QWORD *)EcpContext + 5);
  *((_QWORD *)v134 + 4) = &v166;
  *((_WORD *)v134 + 1) |= 0x10u;
  if ( (v40[18] & 0x400) != 0 )
  {
    ReparseData = UnionFs::Utils::GetReparseData((PFLT_INSTANCE)v12, (PFILE_OBJECT)Object[1], CleanupCallback);
    if ( ReparseData < 0 )
    {
      v41 = "PUSH: Getting layer reparse data";
      v42 = 0x28400211AEDLL;
      goto LABEL_68;
    }
    v39 = v138;
    if ( v138 )
    {
      ReparseData = UnionFs::Utils::VirtualizeReparseData(&v138, &v139, *a6, a7);
      if ( ReparseData < 0 )
      {
        v41 = "PUSH: Munging reparse data";
        v42 = 0x6C500211AFALL;
LABEL_68:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)ReparseData,
          (int)a7,
          (struct UnionFs::StackEventTracer *)v42,
          (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
          v41,
          LookasideList);
        if ( v138 )
          ExFreePoolWithTag(v138, 0);
        goto LABEL_64;
      }
      v39 = v138;
      *((_WORD *)v134 + 1) |= 2u;
      *((_WORD *)v134 + 3) = v139;
      *((_QWORD *)v134 + 1) = v39;
    }
  }
  Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpList, v134);
  if ( Parameter < 0 )
  {
    v44 = 0x10C00211B05LL;
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
  v147 = 0;
  Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                *(PFLT_FILTER *)UnionFs::g_FilterState,
                &GUID_ECP_DUAL_OPLOCK_KEY,
                0x24u,
                0,
                0,
                (char *)UnionFs::g_FilterState + 2368,
                &v147);
  if ( Parameter < 0 )
  {
    v45 = "API: FltAllocateExtraCreateParameterFromLookasideList";
    v44 = 0x62400211B13LL;
    goto LABEL_77;
  }
  v50 = v147;
  *(_OWORD *)v147 = 0;
  v50[1] = 0;
  *((_DWORD *)v50 + 8) = 0;
  *((_OWORD *)v147 + 1) = UNIONFS_GUID_ECP_OPLOCK_KEY;
  *((_BYTE *)v147 + 33) = 1;
  Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpList, v147);
  if ( Parameter < 0 )
  {
    v44 = 0x62200211B1CLL;
    goto LABEL_76;
  }
  v159 = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  v51 = (__int64 *)a6[1];
  if ( v51 )
    HostSilo = *v51;
  else
    HostSilo = PsGetHostSilo();
  v159 = HostSilo;
  v53 = *a6;
  *(_OWORD *)v149 = 0;
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
                (struct UnionFs::LookupEaResults *)v149,
                (struct UnionFs::StackEventTracer *)a7);
  if ( Parameter < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Parameter,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x56C00211B33LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: EA table lookup",
      LookasideLista);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    if ( v149[1] )
      utl::_RefCountBase::_DecStrong(v149[1]);
    goto LABEL_78;
  }
  v55 = v149[1];
  v56 = v149[0];
  v143 = v149[0];
  v144 = v149[1];
  if ( v149[1] )
  {
    _InterlockedIncrement((volatile signed __int32 *)v149[1] + 2);
    v56 = v143;
  }
  v133 = Resource;
  Resource = 0;
  EaLength = *((unsigned int *)EcpContext + 30);
  EaBuffer = (struct _FILE_OBJECT *)*((_QWORD *)EcpContext + 16);
  HIDWORD(FileObject[0]) = 0;
  if ( !EaBuffer && EaLength )
  {
    gsl::details::terminate((gsl::details *)EcpContext);
    JUMPOUT(0x14006DC92LL);
  }
  if ( !v56 )
  {
LABEL_168:
    CreateOptions = 2162728;
    DriverContext.ExtraCreateParameter = EcpList;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityDescriptor = v27;
    ObjectAttributes.RootDirectory = *(HANDLE *)(v154 + 40);
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v155;
    ObjectAttributes.SecurityQualityOfService = 0;
    v140 = 2162728;
    if ( (*((_DWORD *)v151 + 18) & 0x10) != 0 )
    {
      CreateOptions = 2162729;
      v140 = 2162729;
    }
    FileAttributes = *((_DWORD *)v151 + 18) & 0xBFEF;
    v74 = *((_DWORD *)v151 + 18) & 0xFF7F0000;
    if ( v74 )
    {
      *((_DWORD *)v134 + 10) |= v74;
      *((_WORD *)v134 + 1) |= 0x20u;
      CreateOptions = v140;
    }
    FileObject[0] = (PFILE_OBJECT)&v132;
    v132 = 0;
    IoStatusBlock = 0;
    FileObject[1] = 0;
    v146 = 1;
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
    if ( v146 )
    {
      v78 = *(void **)FileObject[0];
      *(_QWORD *)FileObject[0] = FileObject[1];
      if ( v78 )
        ObfDereferenceObject(v78);
    }
    v162[0] = &v131;
    v162[1] = &v126;
    v162[2] = v154;
    v162[3] = &v141;
    v162[5] = &P;
    v162[6] = v152;
    v162[8] = &v155;
    v162[9] = &v140;
    v162[10] = FileInformation;
    v162[11] = &v143;
    v162[12] = &v133;
    v131 = 0;
    v126 = 0;
    v162[4] = Instance;
    v162[7] = a7;
    if ( v77 < 0 )
    {
      if ( v77 != -1073741771 && v77 != -1073739511 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v77,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x10D00211CA8LL,
          (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
          "API: Creating component in target",
          LookasideListc);
        v163 = 0;
        lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(v162);
        v79 = v132;
        v132 = 0;
        if ( v79 )
          ObfDereferenceObject(v79);
        if ( FileHandle )
          FltClose(FileHandle);
        if ( v26 )
          ExFreePoolWithTag(v26, 0);
        v80 = v133;
        v133 = 0;
        if ( v80 )
        {
          ExReleaseResourceLite(v80);
          KeLeaveCriticalRegion();
        }
        if ( v144 )
          utl::_RefCountBase::_DecStrong(v144);
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
        LODWORD(v135) = v77;
        LODWORD(FileInformation) = 7328;
        v85 = (const struct _UNICODE_STRING *)&v155;
        v138 = (PVOID)"UnionFs::Utils::CopyItemPriv";
        if ( !*((_QWORD *)&v155 + 1) )
          v85 = &FsTlEmptyUnicodeString;
        v152 = v85;
        v151 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
        v153 = (struct _FILE_OBJECT *)"Destination already exists";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)byte_140099CB9,
          v75,
          (unsigned int)"UnionFs::Utils::CopyItemPriv",
          (__int64)&v153,
          (__int64)&v138,
          (__int64)&v151,
          (__int64)&FileInformation,
          (__int64)&v135,
          (__int64)&v152);
      }
      v126 = 1;
      v163 = 0;
      lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(v162);
      v86 = v132;
      v132 = 0;
      if ( v86 )
        ObfDereferenceObject(v86);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v26 )
        ExFreePoolWithTag(v26, 0);
      v87 = v133;
      v133 = 0;
      if ( v87 )
      {
        ExReleaseResourceLite(v87);
        KeLeaveCriticalRegion();
      }
      if ( v144 )
        utl::_RefCountBase::_DecStrong(v144);
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
    FileObject[1] = (PFILE_OBJECT)&v132;
    FileObject[0] = (PFILE_OBJECT)Instance;
    v146 = 1;
    UnionFs::Utils::SuppressTimestampUpdates(Instance, (const struct _FLT_INSTANCE *)v132, a7, v76);
    v93 = (UnionFs::Utils *)FileInformation;
    LOWORD(a7[2].Busy) = 0;
    v130 = 0;
    v94 = v156;
    *(_DWORD *)&a7->Type = 0;
    if ( *(_DWORD *)(*(_QWORD *)(v94 + 8) + 24LL) != 30 )
    {
      if ( UnionFs::Utils::SuppressTimestampUpdates(v93, (const struct _FLT_INSTANCE *)Object[1], a7, v92) >= 0 )
        v130 = 1;
      *(_DWORD *)&a7->Type = 0;
      LOWORD(a7[2].Busy) = 0;
    }
    v160[1] = v93;
    v160[0] = &v130;
    v160[2] = Object;
    v160[3] = a7;
    v161 = 1;
    if ( (*((_DWORD *)v151 + 18) & 0x800) != 0 )
    {
      v77 = UnionFs::Utils::CopyFileCompression(
              v93,
              (const struct _FLT_INSTANCE *)Object[1],
              (const struct _FILE_OBJECT *)Instance,
              (const struct _FLT_INSTANCE *)v132,
              a7,
              (struct UnionFs::StackEventTracer *)LookasideListc);
      if ( v77 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v77,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x28500211CE4LL,
          (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
          "PUSH: Copying compression state",
          LookasideListd);
        wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v160);
        LODWORD(FileInformation) = 3;
        FltSetInformationFile(Instance, (PFILE_OBJECT)v132, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
        v163 = 0;
        lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(v162);
        v95 = v132;
        v132 = 0;
        if ( v95 )
          ObfDereferenceObject(v95);
        if ( FileHandle )
          FltClose(FileHandle);
        if ( v26 )
          ExFreePoolWithTag(v26, 0);
        v96 = v133;
        v133 = 0;
        if ( v96 )
        {
          ExReleaseResourceLite(v96);
          KeLeaveCriticalRegion();
        }
        if ( v144 )
          utl::_RefCountBase::_DecStrong(v144);
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
    LookasideListe = (const char *)v132;
    v100 = UnionFs::Utils::CopyItemDataStreams(v93, Object[0], Object[1], Instance, FileHandle);
    if ( v100 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v100,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x26A00211CF2LL,
        (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
        "PUSH: Copying file metadata",
        LookasideListe);
      wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v160);
      wil::details::lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___::_lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___(FileObject);
      v163 = 0;
      lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(v162);
      v101 = v132;
      v132 = 0;
      if ( v101 )
        ObfDereferenceObject(v101);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v26 )
        ExFreePoolWithTag(v26, 0);
      v102 = v133;
      v133 = 0;
      if ( v102 )
      {
        ExReleaseResourceLite(v102);
        KeLeaveCriticalRegion();
      }
      if ( v144 )
        utl::_RefCountBase::_DecStrong(v144);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v149);
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
    if ( (v141 & 0x10) == 0
      || (LookasideListf = *(const char **)v154,
          v77 = UnionFs::Utils::CopyHardLinks(v152, v93, Object[1], Instance, v132),
          v77 >= 0) )
    {
      v131 = 1;
      v126 = 1;
      if ( v157 )
      {
        v110 = *v157;
        *v157 = v132;
        v132 = v110;
      }
      v146 = 0;
      wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v160);
      wil::details::lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___::_lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___(FileObject);
      v163 = 0;
      lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(v162);
      v111 = v132;
      v132 = 0;
      if ( v111 )
        ObfDereferenceObject(v111);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v26 )
        ExFreePoolWithTag(v26, 0);
      v112 = v133;
      v133 = 0;
      if ( v112 )
      {
        ExReleaseResourceLite(v112);
        KeLeaveCriticalRegion();
      }
      if ( v144 )
        utl::_RefCountBase::_DecStrong(v144);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v149);
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
      (struct UnionFs::StackEventTracer *)0x3A600211D03LL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "PUSH: Copying hard links",
      LookasideListf);
    wil::details::lambda_call__lambda_2776654e44483e89c3842b1c456b577f___::_lambda_call__lambda_2776654e44483e89c3842b1c456b577f___(v160);
    wil::details::lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___::_lambda_call__lambda_ee6b4cad7daed117185eb4b8c92f43a2___(FileObject);
    v163 = 0;
    lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(v162);
    v106 = v132;
    v132 = 0;
    if ( v106 )
      ObfDereferenceObject(v106);
    if ( FileHandle )
      FltClose(FileHandle);
    if ( v26 )
      ExFreePoolWithTag(v26, 0);
    v107 = v133;
    v133 = 0;
    if ( v107 )
    {
      ExReleaseResourceLite(v107);
      KeLeaveCriticalRegion();
    }
    if ( v144 )
      utl::_RefCountBase::_DecStrong(v144);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v149);
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
  LODWORD(v135) = 0;
  v153 = v59;
  v60 = (struct _FILE_OBJECT **)utl::make_unique_pool<enum gsl::byte [0],256,1634027093,0>(&v138, v59);
  EaBuffer = *v60;
  *v60 = 0;
  if ( v138 )
    ExFreePoolWithTag(v138, 0);
  if ( !EaBuffer )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x64500211B4ALL,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
      "ORIGIN: Allocating EA buffer",
      LookasideLista);
    v61 = v133;
    v133 = 0;
    if ( v61 )
    {
      ExReleaseResourceLite(v61);
      KeLeaveCriticalRegion();
    }
    if ( v144 )
      utl::_RefCountBase::_DecStrong(v144);
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
  v138 = (PVOID)(unsigned int)v153;
  FileObject[0] = v153;
  v26 = EaBuffer;
  FileObject[1] = EaBuffer;
  EAs = UnionFs::UfsEaPayload::GetEAs(
          (_DWORD)v143,
          0,
          (unsigned int)FileObject,
          (unsigned int)&v135,
          0,
          0,
          1,
          (_DWORD)AllocationSize);
  LODWORD(v135) = EAs;
  if ( EAs == -1073741742 )
  {
    LODWORD(EaLength) = (_DWORD)v138;
    goto LABEL_168;
  }
  if ( EAs >= 0 )
  {
    LODWORD(EaLength) = (_DWORD)v138;
    goto LABEL_168;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)EAs,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x56D00211B57LL,
    (unsigned __int64)"UnionFs::Utils::CopyItemPriv",
    "PUSH: Copy EAs to buffer",
    LookasideListb);
  ExFreePoolWithTag(EaBuffer, 0);
  v67 = v133;
  v133 = 0;
  if ( v67 )
  {
    ExReleaseResourceLite(v67);
    KeLeaveCriticalRegion();
  }
  if ( v144 )
    utl::_RefCountBase::_DecStrong(v144);
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
  return (unsigned int)v135;
}

```

## disassembly

```asm
0x14006c1fc  push    rbp
0x14006c1fe  push    rbx
0x14006c1ff  push    rsi
0x14006c200  push    rdi
0x14006c201  push    r12
0x14006c203  push    r13
0x14006c205  push    r14
0x14006c207  push    r15
0x14006c209  lea     rbp, [rsp-1D8h]
0x14006c211  sub     rsp, 2D8h
0x14006c218  mov     rax, cs:__security_cookie
0x14006c21f  xor     rax, rsp
0x14006c222  mov     [rbp+210h+var_50], rax
0x14006c229  mov     rax, [rbp+210h+arg_38]
0x14006c230  xor     r12d, r12d
0x14006c233  mov     r13, [rbp+210h+arg_28]
0x14006c23a  mov     rbx, r8
0x14006c23d  mov     rsi, [rbp+210h+arg_30]
0x14006c244  mov     r14, rdx
0x14006c247  mov     rdi, [rbp+210h+SourceString]
0x14006c24e  mov     [rbp+210h+Instance], r9
0x14006c252  mov     [rbp+210h+var_180], rdx
0x14006c259  mov     [rbp+210h+var_1A8], rcx
0x14006c25d  mov     [rbp+210h+var_198], r13
0x14006c261  mov     [rbp+210h+var_178], rax
0x14006c268  test    rax, rax
0x14006c26b  jz      short loc_14006C284
0x14006c26d  mov     rcx, [rax]; Object
0x14006c270  mov     [rax], r12
0x14006c273  test    rcx, rcx
0x14006c276  jz      short loc_14006C284
0x14006c278  call    cs:__imp_ObfDereferenceObject
0x14006c27f  nop     dword ptr [rax+rax+00h]
0x14006c284  mov     rax, [r14+8]
0x14006c288  lea     rdx, [rbp+210h+FileObject]
0x14006c28c  mov     r9d, [r13+30h]
0x14006c290  xorps   xmm0, xmm0
0x14006c293  and     r9d, 1
0x14006c297  mov     r8d, 80020000h
0x14006c29d  add     r9d, 6
0x14006c2a1  mov     r15, [rax]
0x14006c2a4  mov     rax, [r13+20h]
0x14006c2a8  mov     rcx, r15
0x14006c2ab  mov     [rsp+310h+AllocationSize], rax
0x14006c2b0  mov     rax, [r13+8]
0x14006c2b4  mov     [rsp+310h+IoStatusBlock], rax
0x14006c2b9  lea     rax, [rbp+210h+Object]
0x14006c2bd  movdqu  xmmword ptr [rbp+210h+Object], xmm0
0x14006c2c2  mov     [rsp+310h+LookasideList], rsi; char *
0x14006c2c7  movups  xmm0, xmmword ptr [rbx]
0x14006c2ca  mov     [rsp+310h+CleanupCallback], rax
0x14006c2cf  mov     [rbp+210h+FileInformation], r15
0x14006c2d3  mov     [rbp+210h+EcpContext], r12
0x14006c2d7  movdqu  xmmword ptr [rbp+210h+FileObject], xmm0
0x14006c2dc  call    ?OpenAsReparsePoint@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KW4OpenAsReparsePointFlags@12@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@PEAX@Z; UnionFs::Utils::OpenAsReparsePoint(_FLT_INSTANCE const &,_UNICODE_STRING const &,ulong,UnionFs::Utils::OpenAsReparsePointFlags,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,void *)
0x14006c2e1  mov     ebx, eax
0x14006c2e3  test    eax, eax
0x14006c2e5  jns     short loc_14006C362
0x14006c2e7  lea     rax, aPushOpeningSou; "PUSH: Opening source file"
0x14006c2ee  mov     r8, 26000211A84h; struct UnionFs::StackEventTracer *
0x14006c2f8  lea     r9, aUnionfsUtilsCo_2; "UnionFs::Utils::CopyItemPriv"
0x14006c2ff  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c304  mov     rdx, rsi; int
0x14006c307  mov     ecx, ebx; this
0x14006c309  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c30e  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c312  test    rdx, rdx
0x14006c315  jz      short loc_14006C32D
0x14006c317  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c31e  mov     rcx, [rcx]; Filter
0x14006c321  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c328  nop     dword ptr [rax+rax+00h]
0x14006c32d  mov     rcx, [rbp+210h+Object+8]; Object
0x14006c331  mov     [rbp+210h+Object+8], r12
0x14006c335  test    rcx, rcx
0x14006c338  jz      short loc_14006C346
0x14006c33a  call    cs:__imp_ObfDereferenceObject
0x14006c341  nop     dword ptr [rax+rax+00h]
0x14006c346  mov     rcx, [rbp+210h+Object]; FileHandle
0x14006c34a  test    rcx, rcx
0x14006c34d  jz      short loc_14006C35B
0x14006c34f  call    cs:__imp_FltClose
0x14006c356  nop     dword ptr [rax+rax+00h]
0x14006c35b  mov     eax, ebx
0x14006c35d  jmp     loc_14006DC69
0x14006c362  mov     rax, [rbp+210h+Object+8]
0x14006c366  lea     r8, [rbp+210h+FileNameInformation]
0x14006c36a  mov     r9, rsi
0x14006c36d  mov     [rbp+210h+var_1D0+8], rax
0x14006c371  mov     edx, 401h
0x14006c376  mov     [rbp+210h+FileNameInformation], r12
0x14006c37a  lea     rcx, [rbp+210h+var_1D0]
0x14006c37e  mov     [rbp+210h+var_1D0], r12
0x14006c382  mov     [rbp+210h+Resource], r15
0x14006c386  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14006c38b  mov     ebx, eax
0x14006c38d  test    eax, eax
0x14006c38f  jns     short loc_14006C3DA
0x14006c391  lea     rax, aPushGettingSou_0; "PUSH: Getting source file name informat"...
0x14006c398  mov     r8, 62D00211A93h; struct UnionFs::StackEventTracer *
0x14006c3a2  lea     r9, aUnionfsUtilsCo_2; "UnionFs::Utils::CopyItemPriv"
0x14006c3a9  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c3ae  mov     rdx, rsi; int
0x14006c3b1  mov     ecx, ebx; this
0x14006c3b3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c3b8  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c3bc  mov     [rbp+210h+FileNameInformation], r12
0x14006c3c0  test    rcx, rcx
0x14006c3c3  jz      loc_14006C30E
0x14006c3c9  call    cs:__imp_FltReleaseFileNameInformation
0x14006c3d0  nop     dword ptr [rax+rax+00h]
0x14006c3d5  jmp     loc_14006C30E
0x14006c3da  mov     r8, rsi
0x14006c3dd  mov     [rbp+210h+P], r12
0x14006c3e1  lea     rdx, [rbp+210h+P]
0x14006c3e5  mov     rcx, rdi; SourceString
0x14006c3e8  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14006c3ed  mov     edi, eax
0x14006c3ef  test    eax, eax
0x14006c3f1  jns     loc_14006C4B9
0x14006c3f7  lea     rax, aPushCopyingTar; "PUSH: Copying target name"
0x14006c3fe  mov     r8, 63B00211A9Bh; struct UnionFs::StackEventTracer *
0x14006c408  lea     r9, aUnionfsUtilsCo_2; "UnionFs::Utils::CopyItemPriv"
0x14006c40f  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c414  mov     rdx, rsi; int
0x14006c417  mov     ecx, edi; this
0x14006c419  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c41e  mov     rbx, [rbp+210h+P]
0x14006c422  test    rbx, rbx
0x14006c425  jz      short loc_14006C44C
0x14006c427  cmp     [rbx+10h], r12b
0x14006c42b  jnz     short loc_14006C433
0x14006c42d  xorps   xmm0, xmm0
0x14006c430  movups  xmmword ptr [rbx], xmm0
0x14006c433  mov     rcx, rbx; UnicodeString
0x14006c436  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006c43b  xor     edx, edx; Tag
0x14006c43d  mov     rcx, rbx; P
0x14006c440  call    cs:__imp_ExFreePoolWithTag
0x14006c447  nop     dword ptr [rax+rax+00h]
0x14006c44c  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c450  mov     [rbp+210h+FileNameInformation], r12
0x14006c454  test    rcx, rcx
0x14006c457  jz      short loc_14006C465
0x14006c459  call    cs:__imp_FltReleaseFileNameInformation
0x14006c460  nop     dword ptr [rax+rax+00h]
0x14006c465  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c469  test    rdx, rdx
0x14006c46c  jz      short loc_14006C484
0x14006c46e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c475  mov     rcx, [rcx]; Filter
0x14006c478  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c47f  nop     dword ptr [rax+rax+00h]
0x14006c484  mov     rcx, [rbp+210h+Object+8]; Object
0x14006c488  mov     [rbp+210h+Object+8], r12
0x14006c48c  test    rcx, rcx
0x14006c48f  jz      short loc_14006C49D
0x14006c491  call    cs:__imp_ObfDereferenceObject
0x14006c498  nop     dword ptr [rax+rax+00h]
0x14006c49d  mov     rcx, [rbp+210h+Object]; FileHandle
0x14006c4a1  test    rcx, rcx
0x14006c4a4  jz      short loc_14006C4B2
0x14006c4a6  call    cs:__imp_FltClose
0x14006c4ad  nop     dword ptr [rax+rax+00h]
0x14006c4b2  mov     eax, edi
0x14006c4b4  jmp     loc_14006DC69
0x14006c4b9  mov     rbx, [rbp+210h+P]
0x14006c4bd  xor     r8d, r8d; unsigned __int16
0x14006c4c0  mov     rcx, rbx; this
0x14006c4c3  movzx   edx, word ptr [rbx+18h]; struct _UNICODE_STRING *
0x14006c4c7  call    ?RemoveFinalComponent@Utils@UnionFs@@YAGAEAU_UNICODE_STRING@@GPEAU3@@Z; UnionFs::Utils::RemoveFinalComponent(_UNICODE_STRING &,ushort,_UNICODE_STRING *)
0x14006c4cc  sub     [rbx+28h], ax
0x14006c4d0  mov     r8, rsi; struct _UNICODE_STRING *
0x14006c4d3  add     [rbx+38h], ax
0x14006c4d7  mov     rdx, [rbp+210h+FileNameInformation]
0x14006c4db  mov     rcx, [rbp+210h+P]; this
0x14006c4df  add     rdx, 58h ; 'X'; Source
0x14006c4e3  call    ?AppendPath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AppendPath(_UNICODE_STRING const &,UnionFs::StackEventTracer &)
0x14006c4e8  mov     rdx, [rbp+210h+FileNameInformation]
0x14006c4ec  mov     r8, rsi; struct UnionFs::StackEventTracer *
0x14006c4ef  mov     rcx, [rbp+210h+P]; SourceString
0x14006c4f3  add     rdx, 48h ; 'H'; Source
0x14006c4f7  call    ?AppendUnicodeString@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AppendUnicodeString(_UNICODE_STRING const &,UnionFs::StackEventTracer &)
0x14006c4fc  mov     rax, [rbp+210h+P]
0x14006c500  xor     ebx, ebx
0x14006c502  mov     edi, ebx
0x14006c504  mov     [rbp+210h+var_240], rbx
0x14006c508  movups  xmm0, xmmword ptr [rax]
0x14006c50b  mov     eax, [r13+30h]
0x14006c50f  or      eax, 4
0x14006c512  mov     [rbp+210h+var_214], eax
0x14006c515  movdqu  [rbp+210h+var_190], xmm0
0x14006c51d  test    al, 8
0x14006c51f  jnz     loc_14006C601
0x14006c525  mov     rdx, [rbp+210h+Object+8]; FileObject
0x14006c529  lea     r8, [rbp+210h+var_240]
0x14006c52d  mov     r9, rsi
0x14006c530  mov     dword ptr [rsp+310h+CleanupCallback], 10000h; SecurityInformation
0x14006c538  mov     rcx, r15; Instance
0x14006c53b  call    ?QuerySecurity@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::QuerySecurity(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &,UnionFs::StackEventTracer &,ulong)
0x14006c540  mov     edi, eax
0x14006c542  test    eax, eax
0x14006c544  jns     loc_14006C5FD
0x14006c54a  lea     rax, aPushGettingSou; "PUSH: Getting source security descripto"...
0x14006c551  mov     r8, 28300211ABAh; struct UnionFs::StackEventTracer *
0x14006c55b  lea     r9, aUnionfsUtilsCo_2; "UnionFs::Utils::CopyItemPriv"
0x14006c562  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c567  mov     rdx, rsi; int
0x14006c56a  mov     ecx, edi; this
0x14006c56c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c571  mov     rcx, [rbp+210h+var_240]; P
0x14006c575  test    rcx, rcx
0x14006c578  jz      short loc_14006C588
0x14006c57a  xor     edx, edx; Tag
0x14006c57c  call    cs:__imp_ExFreePoolWithTag
0x14006c583  nop     dword ptr [rax+rax+00h]
0x14006c588  mov     rbx, [rbp+210h+P]
0x14006c58c  xor     esi, esi
0x14006c58e  test    rbx, rbx
0x14006c591  jz      short loc_14006C5B8
0x14006c593  cmp     [rbx+10h], sil
0x14006c597  jnz     short loc_14006C59F
0x14006c599  xorps   xmm0, xmm0
0x14006c59c  movups  xmmword ptr [rbx], xmm0
0x14006c59f  mov     rcx, rbx; UnicodeString
0x14006c5a2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006c5a7  xor     edx, edx; Tag
0x14006c5a9  mov     rcx, rbx; P
0x14006c5ac  call    cs:__imp_ExFreePoolWithTag
0x14006c5b3  nop     dword ptr [rax+rax+00h]
0x14006c5b8  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c5bc  mov     [rbp+210h+FileNameInformation], rsi
0x14006c5c0  test    rcx, rcx
0x14006c5c3  jz      short loc_14006C5D1
0x14006c5c5  call    cs:__imp_FltReleaseFileNameInformation
0x14006c5cc  nop     dword ptr [rax+rax+00h]
0x14006c5d1  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c5d5  test    rdx, rdx
0x14006c5d8  jz      short loc_14006C5F0
0x14006c5da  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c5e1  mov     rcx, [rcx]; Filter
0x14006c5e4  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c5eb  nop     dword ptr [rax+rax+00h]
0x14006c5f0  mov     rcx, [rbp+210h+Object+8]
0x14006c5f4  mov     [rbp+210h+Object+8], rsi
0x14006c5f8  jmp     loc_14006C48C
0x14006c5fd  mov     rdi, [rbp+210h+var_240]
0x14006c601  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c608  lea     r8, [rbp+210h+EcpList]; EcpList
0x14006c60c  mov     [rbp+210h+EcpList], rbx
0x14006c610  xor     edx, edx; Flags
0x14006c612  mov     rcx, [rcx]; Filter
0x14006c615  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14006c61c  nop     dword ptr [rax+rax+00h]
0x14006c621  mov     r14d, eax
0x14006c624  test    eax, eax
0x14006c626  jns     loc_14006C708
0x14006c62c  lea     rax, aApiFltallocate; "API: FltAllocateExtraCreateParameterLis"...
0x14006c633  mov     r8, 10A00211AC1h; struct UnionFs::StackEventTracer *
0x14006c63d  lea     r9, aUnionfsUtilsCo_2; "UnionFs::Utils::CopyItemPriv"
0x14006c644  mov     [rsp+310h+CleanupCallback], rax; char *
0x14006c649  mov     rdx, rsi; int
0x14006c64c  mov     ecx, r14d; this
0x14006c64f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c654  test    rdi, rdi
0x14006c657  jz      short loc_14006C66A
0x14006c659  xor     edx, edx; Tag
0x14006c65b  mov     rcx, rdi; P
0x14006c65e  call    cs:__imp_ExFreePoolWithTag
0x14006c665  nop     dword ptr [rax+rax+00h]
0x14006c66a  mov     rbx, [rbp+210h+P]
0x14006c66e  xor     edi, edi
0x14006c670  test    rbx, rbx
0x14006c673  jz      short loc_14006C69A
0x14006c675  cmp     [rbx+10h], dil
0x14006c679  jnz     short loc_14006C681
0x14006c67b  xorps   xmm0, xmm0
0x14006c67e  movups  xmmword ptr [rbx], xmm0
0x14006c681  mov     rcx, rbx; UnicodeString
0x14006c684  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006c689  xor     edx, edx; Tag
0x14006c68b  mov     rcx, rbx; P
0x14006c68e  call    cs:__imp_ExFreePoolWithTag
0x14006c695  nop     dword ptr [rax+rax+00h]
0x14006c69a  mov     rcx, [rbp+210h+FileNameInformation]; FileNameInformation
0x14006c69e  mov     [rbp+210h+FileNameInformation], rdi
0x14006c6a2  test    rcx, rcx
0x14006c6a5  jz      short loc_14006C6B3
0x14006c6a7  call    cs:__imp_FltReleaseFileNameInformation
0x14006c6ae  nop     dword ptr [rax+rax+00h]
0x14006c6b3  mov     rdx, [rbp+210h+EcpContext]; EcpContext
0x14006c6b7  test    rdx, rdx
0x14006c6ba  jz      short loc_14006C6D2
0x14006c6bc  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006c6c3  mov     rcx, [rcx]; Filter
0x14006c6c6  call    cs:__imp_FltFreeExtraCreateParameter
0x14006c6cd  nop     dword ptr [rax+rax+00h]
0x14006c6d2  mov     rcx, [rbp+210h+Object+8]; Object
0x14006c6d6  mov     [rbp+210h+Object+8], rdi
0x14006c6da  test    rcx, rcx
  ... truncated ...
```
