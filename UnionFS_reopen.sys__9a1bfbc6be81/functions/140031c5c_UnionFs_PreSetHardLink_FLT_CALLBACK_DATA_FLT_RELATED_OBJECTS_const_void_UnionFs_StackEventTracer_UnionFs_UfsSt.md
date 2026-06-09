# UnionFs::PreSetHardLink(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void * *,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)

- ea: `0x140031c5c`
- end: `0x140034880`
- name: `?PreSetHardLink@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAPEAXAEAVStackEventTracer@1@PEBVUfsStreamHandleCtx@1@@Z`
- size: `11300`
- prototype: `int(UnionFs *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsStreamHandleCtx *)`
- caller_count: `1`
- callee_count: `48`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140034890`

## callees

- `0x140001008`
- `0x140001c08`
- `0x140002354`
- `0x140005d20`
- `0x140005d5c`
- `0x140005ec4`
- `0x140006340`
- `0x140008140`
- `0x140008870`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140011198`
- `0x14001124c`
- `0x140027130`
- `0x14002ac00`
- `0x14002ac7c`
- `0x14002accc`
- `0x14002b4a8`
- `0x14002bab8`
- `0x14002bc48`
- `0x14002bcc0`
- `0x14002be64`
- `0x14002bfbc`
- `0x140031c5c`
- `0x140036180`
- `0x14003cd88`
- `0x140041840`
- `0x1400438e4`
- `0x140055d9c`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140060ed8`
- `0x140061024`
- `0x14006bca8`
- `0x14006e1a4`
- `0x14006efa8`
- `0x14006f8b8`
- `0x1400702e4`
- `0x140077710`
- `0x140079c48`
- `0x140079dcc`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x1400338e5`
- `ntoskrnl!IoGetSilo` at `0x1400338e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031e7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003207d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032166`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400325b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032719`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032857`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033155`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033271`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031e7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003207d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032166`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400325b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032719`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032857`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033155`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033271`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d1d`
- `ntoskrnl!ObfDereferenceObject` at `0x140032a5e`
- `ntoskrnl!ObfDereferenceObject` at `0x140032ad3`
- `ntoskrnl!ObfDereferenceObject` at `0x140032c14`
- `ntoskrnl!ObfDereferenceObject` at `0x140032d7b`
- `ntoskrnl!ObfDereferenceObject` at `0x140032dd0`
- `ntoskrnl!ObfDereferenceObject` at `0x140032ed1`
- `ntoskrnl!ObfDereferenceObject` at `0x140032a5e`
- `ntoskrnl!ObfDereferenceObject` at `0x140032ad3`
- `ntoskrnl!ObfDereferenceObject` at `0x140032c14`
- `ntoskrnl!ObfDereferenceObject` at `0x140032d7b`
- `ntoskrnl!ObfDereferenceObject` at `0x140032dd0`
- `ntoskrnl!ObfDereferenceObject` at `0x140032ed1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400324dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032692`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400327ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003289d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033500`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400335b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033807`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033ab4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033c26`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400324dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032692`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400327ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003289d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033500`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400335b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033807`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033ab4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033c26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400324e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003269e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400327d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400328a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003350c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400335bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033813`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033ac0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033c32`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400324e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003269e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400327d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400328a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003350c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400335bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033813`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033ac0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033c32`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140031d01`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140031d01`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031d2b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031d71`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031ea5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003219b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032225`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400322ee`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003251e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400325e7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400326d7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032815`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032b55`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032c96`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032e52`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033051`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400330c1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003318a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003322f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400333c9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003354e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400336d3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033855`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033b02`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033b58`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033c74`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033cca`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033e84`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033ed6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034029`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003418d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400341df`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400342ea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400344e8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400346dd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400347fc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003484e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031d2b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031d71`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031ea5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003219b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032225`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400322ee`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003251e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400325e7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400326d7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032815`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032b55`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032c96`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032e52`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033051`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400330c1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003318a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003322f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400333c9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003354e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400336d3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033855`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033b02`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033b58`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033c74`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033cca`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033e84`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033ed6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034029`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003418d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400341df`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400342ea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400344e8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400346dd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400347fc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003484e`
- `FLTMGR!FltReleaseContext` at `0x140034268`
- `FLTMGR!FltReleaseContext` at `0x140034466`
- `FLTMGR!FltReleaseContext` at `0x140034660`
- `FLTMGR!FltReleaseContext` at `0x140034767`
- `FLTMGR!FltReleaseContext` at `0x140034268`
- `FLTMGR!FltReleaseContext` at `0x140034466`
- `FLTMGR!FltReleaseContext` at `0x140034660`
- `FLTMGR!FltReleaseContext` at `0x140034767`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140032d1f`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140032d1f`

## string_xrefs

- `0x140033f2d`: `PUSH: Getting relative path`
- `0x1400323ca`: `PUSH: Cache lookup`
- `0x14003337d`: `PUSH: Cache lookup`
- `0x14003440a`: `Path should exist`
- `0x140031d4c`: `UnionFs::PreSetHardLink`
- `0x140031dba`: `UnionFs::PreSetHardLink`
- `0x140031e44`: `UnionFs::PreSetHardLink`
- `0x1400320c5`: `UnionFs::PreSetHardLink`
- `0x1400321fd`: `UnionFs::PreSetHardLink`
- `0x1400323e0`: `UnionFs::PreSetHardLink`
- `0x1400324c2`: `UnionFs::PreSetHardLink`
- `0x140032671`: `UnionFs::PreSetHardLink`
- `0x1400327aa`: `UnionFs::PreSetHardLink`
- `0x14003293b`: `UnionFs::PreSetHardLink`
- `0x140032a3e`: `UnionFs::PreSetHardLink`
- `0x140032aad`: `UnionFs::PreSetHardLink`
- `0x140032bee`: `UnionFs::PreSetHardLink`
- `0x140032daa`: `UnionFs::PreSetHardLink`
- `0x140032f4b`: `UnionFs::PreSetHardLink`
- `0x14003307f`: `UnionFs::PreSetHardLink`
- `0x1400331f7`: `UnionFs::PreSetHardLink`
- `0x140033393`: `UnionFs::PreSetHardLink`
- `0x1400334ca`: `UnionFs::PreSetHardLink`
- `0x140033671`: `UnionFs::PreSetHardLink`
- `0x14003373e`: `UnionFs::PreSetHardLink`
- `0x140033964`: `UnionFs::PreSetHardLink`
- `0x140033a73`: `UnionFs::PreSetHardLink`
- `0x140033bc9`: `UnionFs::PreSetHardLink`
- `0x140033d6d`: `UnionFs::PreSetHardLink`
- `0x140033f3e`: `UnionFs::PreSetHardLink`
- `0x140033fa7`: `UnionFs::PreSetHardLink`
- `0x140034107`: `UnionFs::PreSetHardLink`
- `0x140034249`: `UnionFs::PreSetHardLink`
- `0x14003442c`: `UnionFs::PreSetHardLink`
- `0x14003461b`: `UnionFs::PreSetHardLink`
- `0x140032fb8`: `Found directory tombstone for link target`
- `0x140032fff`: `ORIGIN: Found directory tombstone for link target`
- `0x140033062`: `COW Race: Source not found in path cache`
- `0x14003306e`: `ORIGIN: COW Race: Source not found in path cache`
- `0x140032660`: `ORIGIN: Rejecting COW of hardlink source`
- `0x140032a90`: `COW Race: Utils::CopyItem destination already existed`
- `0x140032a9c`: `ORIGIN: COW Race: Utils::CopyItem destination already existed`
- `0x140032d99`: `ORIGIN: Allocating link context`
- `0x140033660`: `ORIGIN: Allocating link context`
- `0x140033788`: `Found directory tombstone for link destination`
- `0x1400337c2`: `ORIGIN: Found directory tombstone at link destination.`
- `0x140033db7`: `Denying attempted superseding hard link without flag.`
- `0x1400339e8`: `ORIGIN: Hard link collision`
- `0x140033df1`: `ORIGIN: Hard link collision`
- `0x1400340f6`: `ORIGIN: Rejecting COW for immutable hardlink destination`
- `0x1400339ae`: `Attempting superseding hard link without flag.`

## pseudocode

```c
__int64 __fastcall UnionFs::PreSetHardLink(
        UnionFs *this,
        struct _FLT_RELATED_OBJECTS *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        void **a4,
        struct UnionFs::StackEventTracer *a5)
{
  FsFltWil::Details *v5; // r13
  __int64 FileNameLength; // rax
  __int64 v10; // rcx
  WCHAR *v11; // r9
  void *v12; // r8
  struct _FILE_OBJECT *FileObject; // rdx
  struct _FLT_INSTANCE *Instance; // rcx
  NTSTATUS DestinationFileNameInformation; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v16; // rax
  struct _FLT_FILE_NAME_INFORMATION *v17; // rcx
  ULONG_PTR v19; // rdx
  PFLT_INSTANCE v20; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v21; // rcx
  const struct _FLT_INSTANCE *v22; // rdx
  ULONG v23; // r9d
  int v24; // esi
  struct _UNICODE_STRING *v25; // rdx
  struct _UNICODE_STRING *v26; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v27; // rcx
  utl::_RefCountBase *v28; // rbx
  UnionFs::UfsLayerCtx *v29; // rdi
  utl::_RefCountBase *v30; // r14
  struct _UNICODE_STRING *v31; // rsi
  UnionFs::UfsLayerCtx **ScratchLayer; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v33; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v34; // rdx
  struct _UNICODE_STRING *v35; // rdx
  unsigned int v36; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v37; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v38; // rdx
  struct _UNICODE_STRING *v39; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v40; // rcx
  UnionFs::UnionFsFilter *v41; // rcx
  int v42; // r15d
  struct FsFltWil::Details::RundownRefCacheAware *v43; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v44; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v45; // rdx
  struct _UNICODE_STRING *v46; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v47; // rcx
  int v48; // eax
  ULONG v49; // r9d
  __int64 v50; // r9
  __int64 v51; // rcx
  int v52; // eax
  int v53; // r8d
  struct UnionFs::StackEventTracer *v54; // r9
  utl::_RefCountBase *v55; // rdx
  utl::_RefCountBase *v56; // rcx
  utl::_RefCountBase *v57; // rax
  utl::_RefCountBase *v58; // rdx
  struct _ERESOURCE *v59; // r15
  int IsFileCowable; // eax
  int v61; // r8d
  int v62; // r13d
  struct FsFltWil::Details::RundownRefCacheAware *v63; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v64; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v65; // rdx
  struct _UNICODE_STRING *v66; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v67; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v68; // rcx
  struct _UNICODE_STRING *v69; // rdx
  int v70; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v71; // rcx
  struct _UNICODE_STRING *v72; // rdx
  int v73; // edi
  struct _FLT_RELATED_OBJECTS *v74; // r15
  int v75; // eax
  struct _UNICODE_STRING *v76; // rdx
  utl::_RefCountBase *v77; // rcx
  utl::_RefCountBase *v78; // rax
  utl::_RefCountBase *v79; // rcx
  PFLT_INSTANCE v80; // r9
  int v81; // edx
  PFLT_CALLBACK_DATA v82; // rdi
  int v83; // eax
  PVOID v84; // rcx
  struct _UNICODE_STRING *v85; // rdx
  PVOID v86; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v87; // rcx
  struct _UNICODE_STRING *v88; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v89; // rcx
  const struct _FLT_INSTANCE *ScratchInstance; // rax
  struct _UNICODE_STRING *v91; // rdx
  PVOID v92; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v93; // rcx
  struct _UNICODE_STRING *v94; // rdx
  __int64 v95; // rax
  struct _UNICODE_STRING *v96; // rdx
  struct _UNICODE_STRING *v97; // rdx
  PVOID v98; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v99; // rcx
  struct _UNICODE_STRING *v100; // rdx
  PVOID v101; // rcx
  UNICODE_STRING *p_Name; // rcx
  bool v103; // zf
  struct _FLT_FILE_NAME_INFORMATION *v104; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v105; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v106; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v107; // rdx
  struct _UNICODE_STRING *v108; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v109; // rcx
  struct _UNICODE_STRING *v110; // rdx
  char v111; // r9
  __int64 v112; // r9
  __int64 v113; // rcx
  int v114; // eax
  int v115; // r8d
  int v116; // r9d
  struct _FLT_FILE_NAME_INFORMATION *v117; // rcx
  utl::_RefCountBase *v118; // rdi
  FsFltWil::Details *v119; // rbx
  volatile signed __int32 *v120; // r15
  bool v121; // al
  struct _ERESOURCE *v122; // r13
  int v123; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v124; // rcx
  utl::_RefCountBase *v125; // rcx
  __int64 v126; // rbx
  __int64 v127; // rax
  struct _FLT_FILE_NAME_INFORMATION *v128; // rcx
  utl::_RefCountBase *v129; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v130; // rcx
  struct UnionFs::StackEventTracer *v131; // r9
  PFILE_OBJECT v132; // rbx
  BOOL v133; // edi
  __int64 Silo; // rax
  int v135; // ebx
  int v136; // r8d
  bool v137; // dl
  _QWORD *v138; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v139; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v140; // rcx
  int v141; // eax
  utl::_RefCountBase *v142; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v143; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v144; // rcx
  volatile signed __int32 *v145; // r13
  __int16 v146; // ax
  void *v147; // rcx
  int v148; // r8d
  utl::_RefCountBase *v149; // rcx
  struct _ERESOURCE *v150; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v151; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v152; // rcx
  struct _UNICODE_STRING *v153; // rdx
  int v154; // eax
  struct _ERESOURCE *v155; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v156; // rcx
  char v157; // al
  struct _ERESOURCE *v158; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v159; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v160; // rcx
  struct _UNICODE_STRING *v161; // rdx
  struct _ERESOURCE *v162; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v163; // rcx
  UnionFs::UfsUnionCtx *v164; // r11
  volatile signed __int32 *v165; // rax
  const struct UnionFs::UfsLayerCtx *v166; // rcx
  PVOID v167; // rsi
  struct _UNICODE_STRING *v168; // rdx
  struct _UNICODE_STRING *v169; // rdx
  struct _UNICODE_STRING *v170; // rdx
  struct _ERESOURCE *v171; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v172; // rcx
  bool v173; // bl
  utl::_RefCountBase *v174; // rcx
  PFLT_INSTANCE v175; // r9
  volatile signed __int32 *v176; // rbx
  __int64 v177; // r8
  __int64 v178; // rax
  int v179; // eax
  struct _UNICODE_STRING *v180; // rdx
  struct _UNICODE_STRING *v181; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v182; // rcx
  struct _UNICODE_STRING *v183; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v184; // rcx
  const char *NameOptions; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsa; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsb; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsc; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsd; // [rsp+28h] [rbp-D8h]
  const char *NameOptionse; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsf; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsg; // [rsp+28h] [rbp-D8h]
  const char *NameOptionsh; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h] BYREF
  PFLT_FILE_NAME_INFORMATION v195; // [rsp+58h] [rbp-A8h] BYREF
  char v196; // [rsp+60h] [rbp-A0h] BYREF
  bool v197; // [rsp+61h] [rbp-9Fh]
  unsigned int v198; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v199; // [rsp+68h] [rbp-98h] BYREF
  PVOID v200; // [rsp+70h] [rbp-90h] BYREF
  utl::_RefCountBase *v201[2]; // [rsp+78h] [rbp-88h] BYREF
  utl::_RefCountBase *v202; // [rsp+88h] [rbp-78h] BYREF
  PVOID Object[2]; // [rsp+90h] [rbp-70h] BYREF
  PVOID v204; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v205; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v206; // [rsp+B0h] [rbp-50h]
  char v207[8]; // [rsp+B8h] [rbp-48h] BYREF
  utl::_RefCountBase **v208; // [rsp+C0h] [rbp-40h] BYREF
  char v209; // [rsp+C8h] [rbp-38h]
  FsFltWil::Details *v210; // [rsp+D0h] [rbp-30h] BYREF
  utl::_RefCountBase *v211; // [rsp+D8h] [rbp-28h]
  PFLT_CALLBACK_DATA Data; // [rsp+E0h] [rbp-20h] BYREF
  struct _FLT_RELATED_OBJECTS *v213; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING RetFileNameInformation[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v215; // [rsp+120h] [rbp+20h] BYREF
  utl::_RefCountBase *v216[2]; // [rsp+128h] [rbp+28h]
  PVOID P; // [rsp+138h] [rbp+38h]
  utl::_RefCountBase *v218; // [rsp+140h] [rbp+40h]
  char v219[8]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v220; // [rsp+150h] [rbp+50h]
  utl::_RefCountBase *v221[2]; // [rsp+160h] [rbp+60h]
  __int64 v222; // [rsp+170h] [rbp+70h]
  int v223; // [rsp+178h] [rbp+78h]
  __int128 v224; // [rsp+180h] [rbp+80h] BYREF
  utl::_RefCountBase *v225[2]; // [rsp+190h] [rbp+90h]
  PERESOURCE v226; // [rsp+1A0h] [rbp+A0h]
  __int64 v227; // [rsp+1A8h] [rbp+A8h]
  __int128 v228; // [rsp+1B0h] [rbp+B0h]
  __int128 v229; // [rsp+1C0h] [rbp+C0h] BYREF
  bool *v230[2]; // [rsp+1D0h] [rbp+D0h]
  PERESOURCE Resource; // [rsp+1E0h] [rbp+E0h]
  __int64 v232; // [rsp+1E8h] [rbp+E8h]
  __int128 v233; // [rsp+1F0h] [rbp+F0h]
  utl::_RefCountBase *v234[2]; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v235[17]; // [rsp+210h] [rbp+110h] BYREF
  utl::_RefCountBase *v236[2]; // [rsp+298h] [rbp+198h] BYREF
  _QWORD v237[17]; // [rsp+2A8h] [rbp+1A8h] BYREF
  struct _UNICODE_STRING UnicodeString[7]; // [rsp+330h] [rbp+230h] BYREF
  PWSTR *p_Buffer; // [rsp+3A0h] [rbp+2A0h]

  v5 = a5;
  *(_QWORD *)&a3->Size = 0;
  FileNameLength = *((_QWORD *)this + 2);
  FileNameInformation = 0;
  Data = (PFLT_CALLBACK_DATA)this;
  v218 = (utl::_RefCountBase *)a3;
  v10 = *(_QWORD *)(FileNameLength + 56);
  *(_QWORD *)&RetFileNameInformation[0].Length = &FileNameInformation;
  v213 = a2;
  LODWORD(FileNameLength) = *(_DWORD *)(v10 + 16);
  v11 = (WCHAR *)(v10 + 20);
  v12 = *(void **)(v10 + 8);
  FileObject = a2->FileObject;
  v205 = (_BYTE *)v10;
  Instance = a2->Instance;
  v210 = a5;
  v206 = 0;
  RetFileNameInformation[0].Buffer = 0;
  LOBYTE(RetFileNameInformation[1].Length) = 1;
  DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                     Instance,
                                     FileObject,
                                     v12,
                                     v11,
                                     FileNameLength,
                                     0x1000101u,
                                     (PFLT_FILE_NAME_INFORMATION *)&RetFileNameInformation[0].Buffer);
  if ( LOBYTE(RetFileNameInformation[1].Length) )
  {
    v16 = **(struct _FLT_FILE_NAME_INFORMATION ***)&RetFileNameInformation[0].Length;
    **(_QWORD **)&RetFileNameInformation[0].Length = RetFileNameInformation[0].Buffer;
    if ( v16 )
      FltReleaseFileNameInformation(v16);
  }
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39B000B04C0LL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "API: Getting destination file name information",
      NameOptions);
LABEL_6:
    v17 = FileNameInformation;
    FileNameInformation = 0;
LABEL_7:
    if ( v17 )
      FltReleaseFileNameInformation(v17);
    return (unsigned int)DestinationFileNameInformation;
  }
  v19 = (ULONG_PTR)a2->FileObject;
  v20 = a2->Instance;
  v200 = 0;
  DestinationFileNameInformation = UnionFs::Utils::GetMappingTableForFileObject(v20, v19, &v200, a4, 0);
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39C000B04C9LL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Getting mapping table",
      NameOptions);
    goto LABEL_6;
  }
  if ( !v200 )
  {
    v21 = FileNameInformation;
    FileNameInformation = 0;
LABEL_590:
    if ( v21 )
      FltReleaseFileNameInformation(v21);
    return 0;
  }
  v22 = a2->Instance;
  v23 = a2->FileObject->Flags >> 17;
  v215 = 1;
  P = 0;
  *(_OWORD *)v216 = 0;
  v24 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
          (UnionFs::UfsScratchMappingTable *)v200,
          v22,
          FileNameInformation,
          (v23 & 1) == 0,
          (struct UnionFs::LookupScratchRootResults *)&v215,
          (struct UnionFs::StackEventTracer *)a4);
  if ( v24 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v24,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39D000B04DBLL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Looking up scratch root",
      NameOptionsa);
    v26 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v26, v25);
      ExFreePoolWithTag(v26, 0);
    }
    if ( v216[1] )
      utl::_RefCountBase::_DecStrong(v216[1]);
    v27 = FileNameInformation;
    FileNameInformation = 0;
    if ( v27 )
      FltReleaseFileNameInformation(v27);
    return (unsigned int)v24;
  }
  v28 = v216[1];
  v29 = v216[0];
  v30 = v216[1];
  v202 = v216[0];
  if ( v216[1] )
    _InterlockedIncrement((volatile signed __int32 *)v216[1] + 2);
  v31 = (struct _UNICODE_STRING *)P;
  v204 = P;
  P = 0;
  *(_OWORD *)v236 = 0;
  memset(v237, 0, sizeof(v237));
  if ( a5 )
  {
    ScratchLayer = (UnionFs::UfsLayerCtx **)UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(a5, RetFileNameInformation);
    UnionFs::UfsLayerCtx::TryGetOwningUnion(
      *ScratchLayer,
      (struct UnionFs::UfsUnionCtxWithRundown *)v236,
      (struct UnionFs::StackEventTracer *)a4);
    if ( RetFileNameInformation[0].Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)RetFileNameInformation[0].Buffer);
    if ( !v236[0] )
    {
      *(_DWORD *)a4 = 0;
      v5 = 0;
      *((_WORD *)a4 + 274) = 0;
      v210 = 0;
    }
  }
  *(_OWORD *)v234 = 0;
  memset(v235, 0, sizeof(v235));
  if ( v29 )
  {
    UnionFs::UfsLayerCtx::TryGetOwningUnion(
      v29,
      (struct UnionFs::UfsUnionCtxWithRundown *)v234,
      (struct UnionFs::StackEventTracer *)a4);
    if ( !v234[0] )
    {
      *(_DWORD *)a4 = 0;
      *((_WORD *)a4 + 274) = 0;
      if ( v28 )
        utl::_RefCountBase::_DecStrong(v28);
      v29 = 0;
      v202 = 0;
      v30 = 0;
    }
  }
  if ( !v5 )
  {
    if ( !v29 )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v235, v33);
      if ( v235[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v235[16] + 24LL))(v235[16]);
      if ( v234[1] )
        utl::_RefCountBase::_DecStrong(v234[1]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v237, v34);
      if ( v237[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v237[16] + 24LL))(v237[16]);
      if ( v236[1] )
        utl::_RefCountBase::_DecStrong(v236[1]);
      if ( v31 )
      {
        if ( !LOBYTE(v31[1].Length) )
          *v31 = 0;
        FsFltWil::Details::FreeUnicodeString(v31, v35);
        ExFreePoolWithTag(v31, 0);
      }
      if ( v30 )
        utl::_RefCountBase::_DecStrong(v30);
      if ( v28 )
        utl::_RefCountBase::_DecStrong(v28);
      v21 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_590;
    }
    v36 = -1058209789;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0003LL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x5ED000B050ELL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "ORIGIN: Source not in a union, destination is",
      NameOptionsa);
    goto LABEL_56;
  }
  v195 = 0;
  *(_QWORD *)&RetFileNameInformation[0].Length = this;
  RetFileNameInformation[0].Buffer = 0;
  *(_QWORD *)&RetFileNameInformation[1].Length = 0;
  v42 = UnionFs::Utils::GetFileNameInformation(RetFileNameInformation, 16778241, &v195, a4);
  if ( v42 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v42,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39A000B051CLL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Getting source file name information",
      NameOptionsa);
LABEL_78:
    v44 = v195;
    v195 = 0;
    if ( v44 )
      FltReleaseFileNameInformation(v44);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v235, v43);
    if ( v235[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v235[16] + 24LL))(v235[16]);
    if ( v234[1] )
      utl::_RefCountBase::_DecStrong(v234[1]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v237, v45);
    if ( v237[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v237[16] + 24LL))(v237[16]);
    if ( v236[1] )
      utl::_RefCountBase::_DecStrong(v236[1]);
    if ( v31 )
    {
      if ( !LOBYTE(v31[1].Length) )
        *v31 = 0;
      FsFltWil::Details::FreeUnicodeString(v31, v46);
      ExFreePoolWithTag(v31, 0);
    }
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    if ( v28 )
      utl::_RefCountBase::_DecStrong(v28);
    v47 = FileNameInformation;
    FileNameInformation = 0;
    if ( v47 )
      FltReleaseFileNameInformation(v47);
    return (unsigned int)v42;
  }
  v48 = *(_DWORD *)v5;
  *(_QWORD *)v207 = 0;
  v199 = 0;
  if ( (v48 & 1) != 0 )
  {
    if ( (v48 & 0x20) != 0 )
    {
      v74 = v213;
      *(_DWORD *)&RetFileNameInformation[0].Length = 1;
      v82 = Data;
      *(USHORT *)((char *)&RetFileNameInformation[0].MaximumLength + 3) = 0;
      *((_BYTE *)&RetFileNameInformation[0].MaximumLength + 5) = 0;
      *((_BYTE *)&RetFileNameInformation[0].MaximumLength + 2) = 0;
      *(_OWORD *)&RetFileNameInformation[0].Buffer = 0;
      *(_OWORD *)&RetFileNameInformation[1].Buffer = 0;
      DestinationFileNameInformation = UnionFs::UnionFsFilter::CheckAndSwitchTarget(
                                         v41,
                                         Data,
                                         v213,
                                         (struct UnionFs::StackEventTracer *)a4,
                                         (struct UnionFs::CheckAndSwitchResults *)RetFileNameInformation);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x4CF000B05EFLL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: CheckAndSwitchTarget failure on SFO",
          NameOptionsa);
        UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)RetFileNameInformation);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v109 = v195;
        v195 = 0;
        if ( v109 )
          FltReleaseFileNameInformation(v109);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v110);
          ExFreePoolWithTag(v31, 0);
        }
        goto LABEL_307;
      }
      UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)RetFileNameInformation);
    }
    else
    {
      v49 = ~(v213->FileObject->Flags >> 17);
      v229 = 0;
      *(_OWORD *)v230 = 0;
      v50 = v49 & 1 | 0xA;
      Resource = 0;
      v232 = 0;
      v233 = 0;
      if ( *((_DWORD *)v236[0] + 7) == 2 )
        v51 = *(_QWORD *)(*((_QWORD *)v236[0] + 4) + 16LL);
      else
        v51 = *((_QWORD *)UnionFs::g_FilterState + 10);
      NameOptionsb = (const char *)a4;
      v52 = UnionFs::UfsPathCache::LookupEntry(v51, v213->Instance, v195, v50, &v229);
      v42 = v52;
      if ( v52 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v52,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B9000B053BLL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Cache lookup",
          (const char *)a4);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        goto LABEL_78;
      }
      *(_OWORD *)v201 = 0;
      if ( !v230[0] )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("COW Race: Source not found in path cache");
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BBLL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x4CE000B0563LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: COW Race: Source not found in path cache",
          (const char *)a4);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        v106 = v195;
        v195 = 0;
        if ( v106 )
          FltReleaseFileNameInformation(v106);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v235, v105);
        if ( v235[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v235[16] + 24LL))(v235[16]);
        if ( v234[1] )
          utl::_RefCountBase::_DecStrong(v234[1]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v237, v107);
        if ( v237[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v237[16] + 24LL))(v237[16]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v108);
          ExFreePoolWithTag(v31, 0);
        }
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        if ( v28 )
          utl::_RefCountBase::_DecStrong(v28);
        v89 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_297;
      }
      if ( (unsigned __int16)(*((_WORD *)v230[0] + 80) - 3) <= 1u )
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x400) != 0
          && (qword_14009E190 & 0x400) == qword_14009E190 )
        {
          p_Name = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
          *(_QWORD *)v207 = "UnionFs::PreSetHardLink";
          v103 = v195->Name.Buffer == 0;
          v198 = 1356;
          if ( !v103 )
            p_Name = &v195->Name;
          v202 = (utl::_RefCountBase *)"onecore\\base\\fs\\unionfs\\sys\\info.cpp";
          Data = (PFLT_CALLBACK_DATA)"Found directory tombstone for link target";
          v200 = p_Name;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (_DWORD)p_Name,
            (unsigned int)byte_140096DCB,
            v53,
            (_DWORD)v54,
            (__int64)&Data,
            (__int64)v207,
            (__int64)&v202,
            (__int64)&v198,
            (__int64)&v200);
        }
        v36 = -1073741638;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x5EF000B0551LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Found directory tombstone for link target",
          NameOptionsb);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        v104 = v195;
        v195 = 0;
        if ( v104 )
          FltReleaseFileNameInformation(v104);
LABEL_56:
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v235, v37);
        if ( v235[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v235[16] + 24LL))(v235[16]);
        if ( v234[1] )
          utl::_RefCountBase::_DecStrong(v234[1]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v237, v38);
        if ( v237[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v237[16] + 24LL))(v237[16]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v39);
          ExFreePoolWithTag(v31, 0);
        }
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        if ( v28 )
          utl::_RefCountBase::_DecStrong(v28);
        v40 = FileNameInformation;
        FileNameInformation = 0;
LABEL_73:
        if ( v40 )
          FltReleaseFileNameInformation(v40);
        return v36;
      }
      v55 = v201[1];
      v56 = (utl::_RefCountBase *)v230[0];
      v57 = (utl::_RefCountBase *)v230[1];
      *(_OWORD *)v230 = 0;
      v201[0] = v56;
      v201[1] = v57;
      if ( v55 )
      {
        utl::_RefCountBase::_DecStrong(v55);
        v56 = v201[0];
      }
      v58 = v236[0];
      v59 = Resource;
      Resource = 0;
      if ( (*((_DWORD *)v236[0] + 6) & 0x80u) != 0 )
      {
        v196 = 0;
        IsFileCowable = UnionFs::Utils::IsFileCowable(
                          (UnionFs::Utils *)&v196,
                          (bool *)v56,
                          (struct UnionFs::UfsPathCachePayload *)a4,
                          v54);
        v62 = IsFileCowable;
        if ( IsFileCowable < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)IsFileCowable,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x78C000B056ELL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "PUSH: Checking immutability",
            (const char *)a4);
          if ( v59 )
          {
            ExReleaseResourceLite(v59);
            KeLeaveCriticalRegion();
          }
          if ( v201[1] )
            utl::_RefCountBase::_DecStrong(v201[1]);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
          v64 = v195;
          v195 = 0;
          if ( v64 )
            FltReleaseFileNameInformation(v64);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v235, v63);
          if ( v235[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v235[16] + 24LL))(v235[16]);
          if ( v234[1] )
            utl::_RefCountBase::_DecStrong(v234[1]);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v237, v65);
          if ( v237[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v237[16] + 24LL))(v237[16]);
          if ( v236[1] )
            utl::_RefCountBase::_DecStrong(v236[1]);
          if ( v31 )
          {
            if ( !LOBYTE(v31[1].Length) )
              *v31 = 0;
            FsFltWil::Details::FreeUnicodeString(v31, v66);
            ExFreePoolWithTag(v31, 0);
          }
          if ( v30 )
            utl::_RefCountBase::_DecStrong(v30);
          if ( v28 )
            utl::_RefCountBase::_DecStrong(v28);
          v67 = FileNameInformation;
          FileNameInformation = 0;
LABEL_135:
          if ( v67 )
            FltReleaseFileNameInformation(v67);
          return (unsigned int)v62;
        }
        if ( !v196 )
        {
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x400000000000LL) != 0
            && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
          {
            v200 = (PVOID)1;
            v202 = (utl::_RefCountBase *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)byte_140096D3D,
              v61,
              (unsigned int)&v202,
              (__int64)&v200);
          }
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000022LL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x78D000B057BLL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "ORIGIN: Rejecting COW of hardlink source",
            (const char *)a4);
          if ( v59 )
          {
            ExReleaseResourceLite(v59);
            KeLeaveCriticalRegion();
          }
          if ( v201[1] )
            utl::_RefCountBase::_DecStrong(v201[1]);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
          v68 = v195;
          v195 = 0;
          if ( v68 )
            FltReleaseFileNameInformation(v68);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
          if ( v31 )
          {
            if ( !LOBYTE(v31[1].Length) )
              *v31 = 0;
            FsFltWil::Details::FreeUnicodeString(v31, v69);
            ExFreePoolWithTag(v31, 0);
          }
LABEL_153:
          if ( v30 )
            utl::_RefCountBase::_DecStrong(v30);
LABEL_490:
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
          v160 = FileNameInformation;
          FileNameInformation = 0;
          if ( v160 )
            FltReleaseFileNameInformation(v160);
          return 3221225506LL;
        }
        v58 = v236[0];
        LODWORD(v56) = v201[0];
        v5 = v210;
      }
      v70 = (int)v195;
      *(_QWORD *)&RetFileNameInformation[0].Length = v58;
      RetFileNameInformation[0].Buffer = (PWSTR)v236[1];
      if ( v236[1] )
        _InterlockedIncrement((volatile signed __int32 *)v236[1] + 2);
      DestinationFileNameInformation = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(
                                         (_DWORD)v56,
                                         (unsigned int)RetFileNameInformation,
                                         v70,
                                         8,
                                         (_DWORD)a4);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x42A000B0588LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: ConvertToSoftTombstone for COW",
          (const char *)a4);
        if ( v59 )
        {
          ExReleaseResourceLite(v59);
          KeLeaveCriticalRegion();
        }
LABEL_162:
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v71 = v195;
        v195 = 0;
        if ( v71 )
          FltReleaseFileNameInformation(v71);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v72);
          ExFreePoolWithTag(v31, 0);
        }
LABEL_170:
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
LABEL_508:
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
        v17 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_7;
      }
      v209 = 1;
      v208 = v201;
      if ( v59 )
      {
        ExReleaseResourceLite(v59);
        KeLeaveCriticalRegion();
      }
      UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(v5, &v210);
      UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)UnicodeString, &v195->Name, v195->Volume.Length);
      v73 = (int)v210;
      v74 = v213;
      v75 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
              v234[0],
              Data,
              v213,
              v195,
              (const struct UnionFs::UfsPathName *)UnicodeString,
              v5,
              v210,
              (struct UnionFs::StackEventTracer *)a4,
              0);
      DestinationFileNameInformation = v75;
      if ( v75 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v75,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B1000B05A6LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Preparing for COW",
          NameOptionsc);
LABEL_177:
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v76);
        if ( v211 )
          utl::_RefCountBase::_DecStrong(v211);
        wil::details::lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___::_lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___(&v208);
        goto LABEL_162;
      }
      v77 = v201[0];
      *(utl::_RefCountBase **)v219 = v236[0];
      v78 = v201[1];
      v222 = 0;
      v223 = 22;
      v220 = 0;
      *(_OWORD *)v221 = 0;
      if ( v201[1] )
        _InterlockedIncrement((volatile signed __int32 *)v201[1] + 2);
      *((_QWORD *)&v220 + 1) = v77;
      v79 = v221[0];
      v221[0] = v78;
      if ( v79 )
        utl::_RefCountBase::_DecStrong(v79);
      v80 = v74->Instance;
      v81 = v73;
      v82 = Data;
      Object[0] = 0;
      v83 = UnionFs::Utils::CopyItem(
              (_DWORD)Data,
              v81,
              *((_QWORD *)v201[0] + 6),
              (_DWORD)v80,
              UnicodeString,
              (__int64)v219,
              (struct _FILE_OBJECT *)a4,
              (__int64)Object);
      DestinationFileNameInformation = v83;
      if ( v83 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v83,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B2000B05B6LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Performing COW",
          NameOptionsd);
        v84 = Object[0];
        Object[0] = 0;
        if ( v84 )
          ObfDereferenceObject(v84);
        if ( v221[0] )
          utl::_RefCountBase::_DecStrong(v221[0]);
        goto LABEL_177;
      }
      v209 = 0;
      if ( !Object[0] )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("COW Race: Utils::CopyItem destination already existed");
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BBLL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3D4000B05C7LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: COW Race: Utils::CopyItem destination already existed",
          NameOptionsd);
        v86 = Object[0];
        Object[0] = 0;
        if ( v86 )
          ObfDereferenceObject(v86);
        if ( v221[0] )
          utl::_RefCountBase::_DecStrong(v221[0]);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v85);
        if ( v211 )
          utl::_RefCountBase::_DecStrong(v211);
        wil::details::lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___::_lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v87 = v195;
        v195 = 0;
        if ( v87 )
          FltReleaseFileNameInformation(v87);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v88);
          ExFreePoolWithTag(v31, 0);
        }
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
        v89 = FileNameInformation;
        FileNameInformation = 0;
LABEL_297:
        if ( v89 )
          FltReleaseFileNameInformation(v89);
        return 3221225659LL;
      }
      ScratchInstance = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(v5);
      if ( !ScratchInstance )
      {
        v36 = -1058209784;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0008LL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x4CD000B05D0LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Scratch instance not available",
          NameOptionsd);
        v92 = Object[0];
        Object[0] = 0;
        if ( v92 )
          ObfDereferenceObject(v92);
        if ( v221[0] )
          utl::_RefCountBase::_DecStrong(v221[0]);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v91);
        if ( v211 )
          utl::_RefCountBase::_DecStrong(v211);
        wil::details::lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___::_lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v93 = v195;
        v195 = 0;
        if ( v93 )
          FltReleaseFileNameInformation(v93);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v94);
          ExFreePoolWithTag(v31, 0);
        }
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
        v40 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_73;
      }
      v82->Iopb->TargetInstance = ScratchInstance;
      v82->Iopb->TargetFileObject = (PFILE_OBJECT)Object[0];
      FltSetCallbackDataDirty(v82);
      *(PVOID *)&RetFileNameInformation[0].Length = Object[0];
      Object[0] = 0;
      *(_OWORD *)&RetFileNameInformation[0].Buffer = 0;
      v95 = utl::make_unique<UnionFs::LinkContext,UnionFs::LinkContext,0>(&v200, RetFileNameInformation);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::operator=(&v199, v95);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v200);
      if ( *(_QWORD *)&RetFileNameInformation[1].Length )
        utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&RetFileNameInformation[1].Length);
      if ( *(_QWORD *)&RetFileNameInformation[0].Length )
        ObfDereferenceObject(*(PVOID *)&RetFileNameInformation[0].Length);
      *(_QWORD *)v207 = v199;
      if ( !v199 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3C7000B05E0LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Allocating link context",
          NameOptionsd);
        v98 = Object[0];
        Object[0] = 0;
        if ( v98 )
          ObfDereferenceObject(v98);
        if ( v221[0] )
          utl::_RefCountBase::_DecStrong(v221[0]);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v97);
        if ( v211 )
          utl::_RefCountBase::_DecStrong(v211);
        wil::details::lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___::_lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v99 = v195;
        v195 = 0;
        if ( v99 )
          FltReleaseFileNameInformation(v99);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v100);
          ExFreePoolWithTag(v31, 0);
        }
LABEL_252:
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
LABEL_399:
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
        v140 = FileNameInformation;
        FileNameInformation = 0;
        if ( v140 )
          FltReleaseFileNameInformation(v140);
        return 3221225626LL;
      }
      v101 = Object[0];
      Object[0] = 0;
      if ( v101 )
        ObfDereferenceObject(v101);
      if ( v221[0] )
        utl::_RefCountBase::_DecStrong(v221[0]);
      if ( !LOBYTE(UnicodeString[1].Length) )
        UnicodeString[0] = 0;
      FsFltWil::Details::FreeUnicodeString(UnicodeString, v96);
      if ( v211 )
        utl::_RefCountBase::_DecStrong(v211);
      wil::details::lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___::_lambda_call__lambda_ee502692914eb34d1dc27acc5817f587___(&v208);
      if ( v201[1] )
        utl::_RefCountBase::_DecStrong(v201[1]);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v229);
    }
  }
  else
  {
    v74 = v213;
    v82 = Data;
  }
  if ( !v202 )
  {
LABEL_583:
    if ( *(_QWORD *)v207 )
    {
      v199 = 0;
      *(_QWORD *)v218 = *(_QWORD *)v207;
    }
    utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
    v184 = v195;
    v195 = 0;
    if ( v184 )
      FltReleaseFileNameInformation(v184);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
    v21 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_590;
  }
  if ( v82->Iopb->Parameters.Create.Options == 72 )
    v196 = *v205 & 1;
  else
    v196 = *v205 != 0;
  v111 = ~(unsigned __int8)(v74->FileObject->Flags >> 17);
  v224 = 0;
  *(_OWORD *)v225 = 0;
  v112 = v111 & 1 | 0xAu;
  v226 = 0;
  v227 = 0;
  v228 = 0;
  if ( *((_DWORD *)v234[0] + 7) == 2 )
    v113 = *(_QWORD *)(*((_QWORD *)v234[0] + 4) + 16LL);
  else
    v113 = *((_QWORD *)UnionFs::g_FilterState + 10);
  NameOptionse = (const char *)a4;
  v114 = UnionFs::UfsPathCache::LookupEntry(v113, v74->Instance, FileNameInformation, v112, &v224);
  DestinationFileNameInformation = v114;
  if ( v114 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v114,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x3AD000B0617LL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Cache lookup",
      (const char *)a4);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
    utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
    v117 = v195;
    v195 = 0;
    if ( v117 )
      FltReleaseFileNameInformation(v117);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
LABEL_307:
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    goto LABEL_508;
  }
  v118 = v225[0];
  v119 = (FsFltWil::Details *)v226;
  v120 = (volatile signed __int32 *)v225[1];
  v121 = v225[0] != 0;
  v208 = v201;
  v226 = 0;
  v200 = v225[0];
  v122 = (struct _ERESOURCE *)v119;
  *(_OWORD *)v225 = 0;
  v210 = v119;
  v197 = v121;
  v209 = 1;
  LOBYTE(Object[0]) = 1;
  *(_OWORD *)v201 = 0;
  if ( v121 )
  {
    LOWORD(Object[0]) = *((_WORD *)v118 + 80);
    if ( (unsigned __int16)(LOWORD(Object[0]) - 3) <= 1u )
    {
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x400) != 0
        && (qword_14009E190 & 0x400) == qword_14009E190 )
      {
        v198 = 1592;
        v200 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
        v202 = (utl::_RefCountBase *)"UnionFs::PreSetHardLink";
        *(_QWORD *)v207 = "Found directory tombstone for link destination";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          1024,
          (unsigned int)&dword_140096C84,
          v115,
          v116,
          (__int64)v207,
          (__int64)&v202,
          (__int64)&v200,
          (__int64)&v198);
      }
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000022LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x461000B063DLL,
        (unsigned __int64)"UnionFs::PreSetHardLink",
        "ORIGIN: Found directory tombstone at link destination.",
        NameOptionse);
      wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
      if ( v201[1] )
        utl::_RefCountBase::_DecStrong(v201[1]);
      if ( v119 )
      {
        ExReleaseResourceLite((PERESOURCE)v119);
        KeLeaveCriticalRegion();
      }
      if ( v120 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
      v130 = v195;
      v195 = 0;
      if ( v130 )
        FltReleaseFileNameInformation(v130);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
      goto LABEL_153;
    }
    v123 = (int)FileNameInformation;
    RetFileNameInformation[0] = *(struct _UNICODE_STRING *)v234;
    if ( v234[1] )
      _InterlockedIncrement((volatile signed __int32 *)v234[1] + 2);
    v62 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(
            (_DWORD)v118,
            (unsigned int)RetFileNameInformation,
            v123,
            7,
            (_DWORD)a4);
    if ( v62 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v62,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6AF000B064ELL,
        (unsigned __int64)"UnionFs::PreSetHardLink",
        "PUSH: Could not place soft tombstone",
        (const char *)a4);
      wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
      if ( v201[1] )
        utl::_RefCountBase::_DecStrong(v201[1]);
      if ( v119 )
      {
        ExReleaseResourceLite((PERESOURCE)v119);
        KeLeaveCriticalRegion();
      }
      if ( v120 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
      v124 = v195;
      v195 = 0;
      if ( v124 )
        FltReleaseFileNameInformation(v124);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
      if ( v30 )
        utl::_RefCountBase::_DecStrong(v30);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
      v67 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_135;
    }
    v122 = 0;
    v210 = 0;
    if ( v119 )
    {
      ExReleaseResourceLite((PERESOURCE)v119);
      KeLeaveCriticalRegion();
    }
    if ( v120 )
      _InterlockedIncrement(v120 + 2);
    v125 = v201[1];
    v201[0] = v118;
    v201[1] = (utl::_RefCountBase *)v120;
    if ( v125 )
      utl::_RefCountBase::_DecStrong(v125);
    if ( LOWORD(Object[0]) == 2 )
    {
      v126 = *(_QWORD *)v207;
      if ( *(_QWORD *)v207 )
      {
        if ( v120 )
          _InterlockedIncrement(v120 + 2);
        v129 = *(utl::_RefCountBase **)(v126 + 16);
        *(_QWORD *)(v126 + 16) = v120;
        *(_QWORD *)(v126 + 8) = v118;
        if ( v129 )
          utl::_RefCountBase::_DecStrong(v129);
      }
      else
      {
        if ( v120 )
          _InterlockedIncrement(v120 + 2);
        *(_QWORD *)&RetFileNameInformation[0].Length = 0;
        RetFileNameInformation[0].Buffer = (PWSTR)v118;
        *(_QWORD *)&RetFileNameInformation[1].Length = v120;
        v127 = utl::make_unique<UnionFs::LinkContext,UnionFs::LinkContext,0>(&v200, RetFileNameInformation);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::operator=(&v199, v127);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v200);
        UnionFs::LinkContext::~LinkContext((UnionFs::LinkContext *)RetFileNameInformation);
        *(_QWORD *)v207 = v199;
        if ( !v199 )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC000009ALL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x45C000B0666LL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "ORIGIN: Allocating link context",
            (const char *)a4);
          wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
          if ( v201[1] )
            utl::_RefCountBase::_DecStrong(v201[1]);
          if ( v120 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
          utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
          v128 = v195;
          v195 = 0;
          if ( v128 )
            FltReleaseFileNameInformation(v128);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
          goto LABEL_252;
        }
      }
      goto LABEL_578;
    }
    LOBYTE(Object[0]) = 0;
  }
  UnicodeString[0].Buffer = (PWSTR)off_14007E740;
  p_Buffer = &UnicodeString[0].Buffer;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a4, UnicodeString);
  if ( LOBYTE(Object[0]) )
  {
    v132 = v213->FileObject;
    v133 = (v132->Flags & 0x20000) == 0;
    memset(UnicodeString, 0, 0x48u);
    Silo = IoGetSilo(v132);
    NameOptionse = (const char *)a4;
    v135 = UnionFs::Utils::StatItem(&FileNameInformation->Name, v213->Instance, Silo, v133, UnicodeString);
    UnionFs::StackEventTracer::ClearIgnoreStatusCallback((UnionFs::StackEventTracer *)a4);
    if ( v135 != -1073741766 && v135 != -1073741772 )
    {
      if ( !v196 )
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x400) != 0
          && (qword_14009E190 & 0x400) == qword_14009E190 )
        {
          v198 = 1859;
          v200 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
          v202 = (utl::_RefCountBase *)"UnionFs::PreSetHardLink";
          *(_QWORD *)v207 = "Attempting superseding hard link without flag.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            1024,
            (unsigned int)byte_140096D8D,
            v136,
            (_DWORD)v131,
            (__int64)v207,
            (__int64)&v202,
            (__int64)&v200,
            (__int64)&v198);
        }
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000035LL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x49A000B0747LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Hard link collision",
          NameOptionse);
        wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v210);
LABEL_440:
        if ( v120 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v151 = v195;
        v195 = 0;
        if ( v151 )
          FltReleaseFileNameInformation(v151);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
        v152 = FileNameInformation;
        FileNameInformation = 0;
        if ( v152 )
          FltReleaseFileNameInformation(v152);
        return 3221225525LL;
      }
LABEL_578:
      v209 = 0;
      wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
      if ( v201[1] )
        utl::_RefCountBase::_DecStrong(v201[1]);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v210);
      if ( v120 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
      goto LABEL_583;
    }
    v118 = (utl::_RefCountBase *)v200;
  }
  v137 = v197;
  v205 = 0;
  if ( v197 )
  {
    v200 = 0;
    v145 = 0;
    v146 = 0;
    v198 = 0;
    v148 = 0;
    goto LABEL_429;
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&v200);
  v138 = v200;
  if ( !v200 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x40C000B06ABLL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "ORIGIN: Allocating findAndStatResults",
      NameOptionse);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
    wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
    if ( v201[1] )
      utl::_RefCountBase::_DecStrong(v201[1]);
    if ( v122 )
    {
      ExReleaseResourceLite(v122);
      KeLeaveCriticalRegion();
    }
    if ( v120 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
    utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
    v139 = v195;
    v195 = 0;
    if ( v139 )
      FltReleaseFileNameInformation(v139);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    goto LABEL_399;
  }
  NameOptionse = (const char *)a4;
  *((_QWORD *)v200 + 12) = &v205;
  RetFileNameInformation[0] = *v31;
  v141 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(
           v234[0],
           &FileNameInformation->Name,
           RetFileNameInformation,
           1,
           v138);
  v198 = v141;
  if ( v141 >= 0 )
  {
    v145 = (volatile signed __int32 *)v138[11];
    v146 = *(_WORD *)v138;
    v147 = (void *)v138[10];
    v198 = *(unsigned __int16 *)v138;
    v200 = v147;
    if ( v145 )
      _InterlockedIncrement(v145 + 2);
    v148 = *((_DWORD *)v138 + 16);
    LODWORD(Object[0]) = v148;
    if ( v138 )
    {
      v149 = (utl::_RefCountBase *)v138[11];
      if ( v149 )
        utl::_RefCountBase::_DecStrong(v149);
      ExFreePoolWithTag(v138, 0);
      v146 = v198;
      v148 = (int)Object[0];
    }
    if ( v146 != 1 )
      goto LABEL_451;
    v137 = v197;
LABEL_429:
    if ( !v196 )
    {
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x400) != 0
        && (qword_14009E190 & 0x400) == qword_14009E190 )
      {
        v198 = 1731;
        v200 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
        v202 = (utl::_RefCountBase *)"UnionFs::PreSetHardLink";
        *(_QWORD *)v207 = "Denying attempted superseding hard link without flag.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          1024,
          (unsigned int)&word_140096C46,
          v148,
          (_DWORD)v131,
          (__int64)v207,
          (__int64)&v202,
          (__int64)&v200,
          (__int64)&v198);
      }
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000035LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x462000B06C7LL,
        (unsigned __int64)"UnionFs::PreSetHardLink",
        "ORIGIN: Hard link collision",
        NameOptionse);
      if ( v145 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
      wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
      if ( v201[1] )
        utl::_RefCountBase::_DecStrong(v201[1]);
      if ( v210 )
        FsFltWil::Details::ReleaseResource(v210, v150);
      goto LABEL_440;
    }
    if ( v137 || v146 == 1 )
    {
      if ( (*((_DWORD *)v234[0] + 6) & 0x80u) != 0 )
      {
        LOBYTE(Object[0]) = 0;
        if ( v137 )
        {
          v154 = UnionFs::Utils::IsFileCowable(
                   (UnionFs::Utils *)Object,
                   (bool *)v118,
                   (struct UnionFs::UfsPathCachePayload *)a4,
                   v131);
          DestinationFileNameInformation = v154;
          if ( v154 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v154,
              (int)a4,
              (struct UnionFs::StackEventTracer *)0x78F000B06D7LL,
              (unsigned __int64)"UnionFs::PreSetHardLink",
              "PUSH: Checking immutability",
              NameOptionse);
            goto LABEL_458;
          }
          v157 = (char)Object[0];
        }
        else
        {
          v157 = (v148 & 0x800010) != 0;
        }
        if ( !v157 )
        {
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x400000000000LL) != 0
            && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
          {
            v200 = (PVOID)1;
            v202 = (utl::_RefCountBase *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)byte_140096BA1,
              v148,
              (unsigned int)&v202,
              (__int64)&v200);
          }
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000022LL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x790000B06E9LL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "ORIGIN: Rejecting COW for immutable hardlink destination",
            NameOptionse);
          if ( v145 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
          wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
          if ( v201[1] )
            utl::_RefCountBase::_DecStrong(v201[1]);
          if ( v210 )
            FsFltWil::Details::ReleaseResource(v210, v158);
          if ( v120 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
          utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
          v159 = v195;
          v195 = 0;
          if ( v159 )
            FltReleaseFileNameInformation(v159);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
          if ( v30 )
            utl::_RefCountBase::_DecStrong(v30);
          goto LABEL_490;
        }
      }
LABEL_452:
      RetFileNameInformation[0] = 0;
      *(struct _UNICODE_STRING *)Object = *v31;
      DestinationFileNameInformation = UnionFs::Utils::GetRemainingPath(
                                         FileNameInformation,
                                         Object,
                                         RetFileNameInformation,
                                         a4);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3AF000B06F8LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Getting relative path",
          NameOptionse);
        FsFltWil::Details::FreeUnicodeString(RetFileNameInformation, v153);
LABEL_458:
        if ( v145 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
        wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        if ( v210 )
          FsFltWil::Details::ReleaseResource(v210, v155);
        if ( v120 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v156 = v195;
        v195 = 0;
        if ( v156 )
          FltReleaseFileNameInformation(v156);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        goto LABEL_508;
      }
      Object[0] = 0;
      DestinationFileNameInformation = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(
                                         (_DWORD)v202,
                                         v213->FileObject,
                                         (_DWORD)v31,
                                         (unsigned int)RetFileNameInformation,
                                         (__int64)Data,
                                         (__int64)Object,
                                         (__int64)a4);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B0000B0708LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Creating handle context",
          NameOptionsf);
        if ( Object[0] )
          FltReleaseContext(Object[0]);
        FsFltWil::Details::FreeUnicodeString(RetFileNameInformation, v161);
        if ( v145 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
        wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        if ( v210 )
          FsFltWil::Details::ReleaseResource(v210, v162);
        if ( v120 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v163 = v195;
        v195 = 0;
        if ( v163 )
          FltReleaseFileNameInformation(v163);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        goto LABEL_508;
      }
      UnionFs::UfsPathName::UfsPathName(
        (UnionFs::UfsPathName *)UnicodeString,
        &FileNameInformation->Name,
        FileNameInformation->Volume.Length);
      v164 = v234[0];
      if ( v197 )
      {
        v165 = (volatile signed __int32 *)*((_QWORD *)v118 + 5);
        v166 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v118 + 4);
        v202 = (utl::_RefCountBase *)v165;
        if ( v165 )
          _InterlockedIncrement(v165 + 2);
        v206 = 1;
      }
      else
      {
        v166 = (const struct UnionFs::UfsLayerCtx *)v200;
        v202 = v218;
      }
      v167 = Object[0];
      DestinationFileNameInformation = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                                         v164,
                                         Data,
                                         v213,
                                         FileNameInformation,
                                         (const struct UnionFs::UfsPathName *)UnicodeString,
                                         (const struct UnionFs::UfsStreamHandleCtx *)Object[0],
                                         v166,
                                         (struct UnionFs::StackEventTracer *)a4,
                                         0);
      if ( (v206 & 1) != 0 )
      {
        v206 &= ~1u;
        if ( v202 )
          utl::_RefCountBase::_DecStrong(v202);
      }
      if ( DestinationFileNameInformation < 0 )
      {
        if ( DestinationFileNameInformation == -1073741766 || DestinationFileNameInformation == -1073741772 )
          MicrosoftTelemetryAssertTriggeredMsgKM("Path should exist");
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3E8000B071DLL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Preparing for COW",
          NameOptionsg);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v169);
        if ( v167 )
          FltReleaseContext(v167);
        FsFltWil::Details::FreeUnicodeString(RetFileNameInformation, v170);
        if ( v145 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
        wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
        if ( v201[1] )
          utl::_RefCountBase::_DecStrong(v201[1]);
        if ( v210 )
          FsFltWil::Details::ReleaseResource(v210, v171);
        if ( v120 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
        v172 = v195;
        v195 = 0;
        if ( v172 )
          FltReleaseFileNameInformation(v172);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
        goto LABEL_170;
      }
      v173 = v197;
      if ( v197 || (_WORD)v198 == 1 )
      {
        *(utl::_RefCountBase **)v219 = v234[0];
        v222 = 0;
        v223 = 22;
        v220 = 0;
        *(_OWORD *)v221 = 0;
        if ( v197 )
        {
          if ( v120 )
            _InterlockedIncrement(v120 + 2);
          v174 = v221[0];
          *((_QWORD *)&v220 + 1) = v118;
          v221[0] = (utl::_RefCountBase *)v120;
          if ( v174 )
            utl::_RefCountBase::_DecStrong(v174);
        }
        v175 = v213->Instance;
        if ( v173 )
        {
          v206 |= 2u;
          v176 = (volatile signed __int32 *)*((_QWORD *)v118 + 5);
          v177 = *((_QWORD *)v118 + 6);
          v178 = *((_QWORD *)v118 + 4);
          if ( v176 )
            _InterlockedIncrement(v176 + 2);
        }
        else
        {
          LODWORD(v177) = (_DWORD)v205;
          v176 = (volatile signed __int32 *)v218;
          LODWORD(v178) = (_DWORD)v200;
        }
        v179 = UnionFs::Utils::CopyItem(
                 (_DWORD)Data,
                 v178,
                 v177,
                 (_DWORD)v175,
                 UnicodeString,
                 (__int64)v219,
                 (struct _FILE_OBJECT *)a4,
                 0);
        v168 = (struct _UNICODE_STRING *)v206;
        v198 = v179;
        if ( (v206 & 2) != 0 && v176 )
        {
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v176);
          v179 = v198;
        }
        if ( v179 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v179,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x353000B073BLL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "PUSH: Performing COW",
            NameOptionsh);
          if ( v221[0] )
            utl::_RefCountBase::_DecStrong(v221[0]);
          if ( !LOBYTE(UnicodeString[1].Length) )
            UnicodeString[0] = 0;
          FsFltWil::Details::FreeUnicodeString(UnicodeString, v180);
          if ( v167 )
            FltReleaseContext(v167);
          FsFltWil::Details::FreeUnicodeString(RetFileNameInformation, v181);
          if ( v145 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
          wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
          if ( v201[1] )
            utl::_RefCountBase::_DecStrong(v201[1]);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v210);
          if ( v120 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
          utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
          v182 = v195;
          v195 = 0;
          if ( v182 )
            FltReleaseFileNameInformation(v182);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
          if ( v30 )
            utl::_RefCountBase::_DecStrong(v30);
          goto LABEL_417;
        }
        if ( v221[0] )
          utl::_RefCountBase::_DecStrong(v221[0]);
      }
      if ( !LOBYTE(UnicodeString[1].Length) )
        UnicodeString[0] = 0;
      FsFltWil::Details::FreeUnicodeString(UnicodeString, v168);
      if ( v167 )
        FltReleaseContext(v167);
      FsFltWil::Details::FreeUnicodeString(RetFileNameInformation, v183);
LABEL_575:
      if ( v145 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v145);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
      goto LABEL_578;
    }
LABEL_451:
    if ( v146 != 3 )
      goto LABEL_575;
    goto LABEL_452;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v141,
    (int)a4,
    (struct UnionFs::StackEventTracer *)0x3B3000B06B7LL,
    (unsigned __int64)"UnionFs::PreSetHardLink",
    "PUSH: Failed to lookup entry",
    (const char *)a4);
  if ( v138 )
  {
    v142 = (utl::_RefCountBase *)v138[11];
    if ( v142 )
      utl::_RefCountBase::_DecStrong(v142);
    ExFreePoolWithTag(v138, 0);
  }
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v205);
  wil::details::lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___::_lambda_call__lambda_0c23d7b3fd30ebdb2054d6e6c278aecf___(&v208);
  if ( v201[1] )
    utl::_RefCountBase::_DecStrong(v201[1]);
  if ( v122 )
  {
    ExReleaseResourceLite(v122);
    KeLeaveCriticalRegion();
  }
  if ( v120 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v120);
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v224);
  utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v199);
  v143 = v195;
  v195 = 0;
  if ( v143 )
    FltReleaseFileNameInformation(v143);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v234);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v236);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v204);
  if ( v30 )
    utl::_RefCountBase::_DecStrong(v30);
LABEL_417:
  UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v215);
  v144 = FileNameInformation;
  FileNameInformation = 0;
  if ( v144 )
    FltReleaseFileNameInformation(v144);
  return v198;
}

```

## disassembly

```asm
0x140031c5c  push    rbp
0x140031c5e  push    rbx
0x140031c5f  push    rsi
0x140031c60  push    rdi
0x140031c61  push    r12
0x140031c63  push    r13
0x140031c65  push    r14
0x140031c67  push    r15
0x140031c69  lea     rbp, [rsp-2C8h]
0x140031c71  sub     rsp, 3C8h
0x140031c78  mov     rax, cs:__security_cookie
0x140031c7f  xor     rax, rsp
0x140031c82  mov     [rbp+300h+var_50], rax
0x140031c89  mov     r13, [rbp+300h+arg_20]
0x140031c90  xor     r14d, r14d
0x140031c93  mov     [r8], r14
0x140031c96  mov     r15, rcx
0x140031c99  mov     rax, [rcx+10h]
0x140031c9d  mov     rdi, rdx
0x140031ca0  mov     [rsp+400h+FileNameInformation], r14
0x140031ca5  mov     r12, r9
0x140031ca8  mov     [rbp+300h+Data], rcx
0x140031cac  lea     esi, [r14+1]
0x140031cb0  mov     [rbp+300h+var_2C0], r8
0x140031cb4  mov     rcx, [rax+38h]
0x140031cb8  lea     rax, [rsp+400h+FileNameInformation]
0x140031cbd  mov     qword ptr [rbp+300h+var_310], rax
0x140031cc1  lea     rax, [rbp+300h+var_310+8]
0x140031cc5  mov     [rsp+400h+RetFileNameInformation], rax; RetFileNameInformation
0x140031cca  mov     [rbp+300h+var_318], rdx
0x140031cce  mov     eax, [rcx+10h]
0x140031cd1  lea     r9, [rcx+14h]; FileName
0x140031cd5  mov     r8, [rcx+8]; RootDirectory
0x140031cd9  mov     rdx, [rdx+20h]; FileObject
0x140031cdd  mov     [rbp+300h+var_358], rcx
0x140031ce1  mov     rcx, [rdi+18h]; Instance
0x140031ce5  mov     [rsp+400h+NameOptions], 1000101h; char *
0x140031ced  mov     [rbp+300h+var_330], r13
0x140031cf1  mov     [rbp+300h+var_350], r14d
0x140031cf5  mov     qword ptr [rbp+300h+var_310+8], r14
0x140031cf9  mov     [rbp+300h+var_310+10h], sil
0x140031cfd  mov     [rsp+400h+FileNameLength], eax; FileNameLength
0x140031d01  call    cs:__imp_FltGetDestinationFileNameInformation
0x140031d08  nop     dword ptr [rax+rax+00h]
0x140031d0d  mov     ebx, eax
0x140031d0f  cmp     [rbp+300h+var_310+10h], r14b
0x140031d13  jz      short loc_140031D37
0x140031d15  mov     rdx, qword ptr [rbp+300h+var_310]
0x140031d19  mov     rcx, qword ptr [rbp+300h+var_310+8]
0x140031d1d  mov     rax, [rdx]
0x140031d20  mov     [rdx], rcx
0x140031d23  test    rax, rax
0x140031d26  jz      short loc_140031D37
0x140031d28  mov     rcx, rax; FileNameInformation
0x140031d2b  call    cs:__imp_FltReleaseFileNameInformation
0x140031d32  nop     dword ptr [rax+rax+00h]
0x140031d37  test    ebx, ebx
0x140031d39  jns     short loc_140031D84
0x140031d3b  lea     rax, aApiGettingDest_0; "API: Getting destination file name info"...
0x140031d42  mov     r8, 39B000B04C0h; struct UnionFs::StackEventTracer *
0x140031d4c  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140031d53  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140031d58  mov     rdx, r12; int
0x140031d5b  mov     ecx, ebx; this
0x140031d5d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140031d62  mov     rcx, [rsp+400h+FileNameInformation]; FileNameInformation
0x140031d67  mov     [rsp+400h+FileNameInformation], r14
0x140031d6c  test    rcx, rcx
0x140031d6f  jz      short loc_140031D7D
0x140031d71  call    cs:__imp_FltReleaseFileNameInformation
0x140031d78  nop     dword ptr [rax+rax+00h]
0x140031d7d  mov     eax, ebx
0x140031d7f  jmp     loc_14003485C
0x140031d84  mov     rdx, [rdi+20h]
0x140031d88  lea     r8, [rsp+400h+var_390]
0x140031d8d  mov     rcx, [rdi+18h]
0x140031d91  mov     r9, r12
0x140031d94  mov     [rsp+400h+var_390], r14
0x140031d99  mov     qword ptr [rsp+400h+FileNameLength], r14
0x140031d9e  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x140031da3  mov     ebx, eax
0x140031da5  test    eax, eax
0x140031da7  jns     short loc_140031DD2
0x140031da9  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x140031db0  mov     r8, 39C000B04C9h; struct UnionFs::StackEventTracer *
0x140031dba  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140031dc1  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140031dc6  mov     rdx, r12; int
0x140031dc9  mov     ecx, ebx; this
0x140031dcb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140031dd0  jmp     short loc_140031D62
0x140031dd2  mov     rcx, [rsp+400h+var_390]; this
0x140031dd7  test    rcx, rcx
0x140031dda  jnz     short loc_140031DEB
0x140031ddc  mov     rcx, [rsp+400h+FileNameInformation]
0x140031de1  mov     [rsp+400h+FileNameInformation], r14
0x140031de6  jmp     loc_140034849
0x140031deb  mov     rax, [rdi+20h]
0x140031def  xorps   xmm0, xmm0
0x140031df2  mov     r8, [rsp+400h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x140031df7  mov     rdx, [rdi+18h]; struct _FLT_INSTANCE *
0x140031dfb  mov     qword ptr [rsp+400h+NameOptions], r12; char *
0x140031e00  mov     r9d, [rax+50h]
0x140031e04  lea     rax, [rbp+300h+var_2E0]
0x140031e08  shr     r9d, 11h
0x140031e0c  not     r9b
0x140031e0f  mov     [rbp+300h+var_2E0], rsi
0x140031e13  and     r9b, sil; bool
0x140031e16  mov     [rbp+300h+P], r14
0x140031e1a  movdqu  xmmword ptr [rbp+300h+var_2D8], xmm0
0x140031e1f  mov     qword ptr [rsp+400h+FileNameLength], rax; struct UnionFs::LookupScratchRootResults *
0x140031e24  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x140031e29  mov     esi, eax
0x140031e2b  test    eax, eax
0x140031e2d  jns     loc_140031EB8
0x140031e33  lea     rax, aPushLookingUpS; "PUSH: Looking up scratch root"
0x140031e3a  mov     r8, 39D000B04DBh; struct UnionFs::StackEventTracer *
0x140031e44  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140031e4b  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140031e50  mov     rdx, r12; int
0x140031e53  mov     ecx, esi; this
0x140031e55  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140031e5a  mov     rbx, [rbp+300h+P]
0x140031e5e  test    rbx, rbx
0x140031e61  jz      short loc_140031E88
0x140031e63  cmp     [rbx+10h], r14b
0x140031e67  jnz     short loc_140031E6F
0x140031e69  xorps   xmm0, xmm0
0x140031e6c  movups  xmmword ptr [rbx], xmm0
0x140031e6f  mov     rcx, rbx; UnicodeString
0x140031e72  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140031e77  xor     edx, edx; Tag
0x140031e79  mov     rcx, rbx; P
0x140031e7c  call    cs:__imp_ExFreePoolWithTag
0x140031e83  nop     dword ptr [rax+rax+00h]
0x140031e88  mov     rcx, [rbp+300h+var_2D8+8]; this
0x140031e8c  test    rcx, rcx
0x140031e8f  jz      short loc_140031E96
0x140031e91  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140031e96  mov     rcx, [rsp+400h+FileNameInformation]; FileNameInformation
0x140031e9b  mov     [rsp+400h+FileNameInformation], r14
0x140031ea0  test    rcx, rcx
0x140031ea3  jz      short loc_140031EB1
0x140031ea5  call    cs:__imp_FltReleaseFileNameInformation
0x140031eac  nop     dword ptr [rax+rax+00h]
0x140031eb1  mov     eax, esi
0x140031eb3  jmp     loc_14003485C
0x140031eb8  mov     rbx, [rbp+300h+var_2D8+8]
0x140031ebc  xor     eax, eax
0x140031ebe  mov     rdi, [rbp+300h+var_2D8]
0x140031ec2  mov     r14, rbx
0x140031ec5  mov     [rbp+300h+var_378], rdi
0x140031ec9  test    rbx, rbx
0x140031ecc  jz      short loc_140031ED2
0x140031ece  lock inc dword ptr [rbx+8]
0x140031ed2  mov     rsi, [rbp+300h+P]
0x140031ed6  lea     rcx, [rbp+300h+var_158]; void *
0x140031edd  xorps   xmm0, xmm0
0x140031ee0  mov     [rbp+300h+var_360], rsi
0x140031ee4  xor     edx, edx; Val
0x140031ee6  mov     [rbp+300h+P], rax
0x140031eea  mov     r8d, 88h; Size
0x140031ef0  mov     [rbp+300h+var_158], rax
0x140031ef7  movdqu  xmmword ptr [rbp+300h+var_168], xmm0
0x140031eff  mov     [rbp+300h+var_150], al
0x140031f05  mov     [rbp+300h+var_D8], rax
0x140031f0c  call    memset
0x140031f11  xor     ecx, ecx
0x140031f13  test    r13, r13
0x140031f16  jz      short loc_140031F63
0x140031f18  lea     rdx, [rbp+300h+var_310]
0x140031f1c  mov     rcx, r13
0x140031f1f  call    ?TryGetScratchLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@$$CBVUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(void)
0x140031f24  mov     r8, r12; struct UnionFs::StackEventTracer *
0x140031f27  lea     rdx, [rbp+300h+var_168]; struct UnionFs::UfsUnionCtxWithRundown *
0x140031f2e  mov     rcx, [rax]; this
0x140031f31  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140031f36  mov     rcx, qword ptr [rbp+300h+var_310+8]; this
0x140031f3a  test    rcx, rcx
0x140031f3d  jz      short loc_140031F44
0x140031f3f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140031f44  xor     ecx, ecx
0x140031f46  cmp     [rbp+300h+var_168], rcx
0x140031f4d  jnz     short loc_140031F63
0x140031f4f  mov     [r12], ecx
0x140031f53  mov     r13d, ecx
0x140031f56  mov     [r12+224h], cx
0x140031f5f  mov     [rbp+300h+var_330], rcx
0x140031f63  xorps   xmm0, xmm0
0x140031f66  mov     [rbp+300h+var_1F0], rcx
0x140031f6d  mov     [rbp+300h+var_1E8], cl
0x140031f73  xor     edx, edx; Val
0x140031f75  mov     [rbp+300h+var_170], rcx
0x140031f7c  mov     r8d, 88h; Size
0x140031f82  lea     rcx, [rbp+300h+var_1F0]; void *
0x140031f89  movdqu  xmmword ptr [rbp+300h+var_200], xmm0
0x140031f91  call    memset
0x140031f96  test    rdi, rdi
0x140031f99  jz      short loc_140031FE0
0x140031f9b  mov     r8, r12; struct UnionFs::StackEventTracer *
0x140031f9e  lea     rdx, [rbp+300h+var_200]; struct UnionFs::UfsUnionCtxWithRundown *
0x140031fa5  mov     rcx, rdi; this
0x140031fa8  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140031fad  cmp     [rbp+300h+var_200], 0
0x140031fb5  jnz     short loc_140031FE0
0x140031fb7  xor     eax, eax
0x140031fb9  mov     dword ptr [r12], 0
0x140031fc1  mov     [r12+224h], ax
0x140031fca  test    rbx, rbx
0x140031fcd  jz      short loc_140031FD7
0x140031fcf  mov     rcx, rbx; this
0x140031fd2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140031fd7  xor     edi, edi
0x140031fd9  mov     [rbp+300h+var_378], rdi
0x140031fdd  xor     r14d, r14d
0x140031fe0  test    r13, r13
0x140031fe3  jnz     loc_1400321AE
0x140031fe9  xor     r15d, r15d
0x140031fec  test    rdi, rdi
0x140031fef  jnz     loc_1400320B2
0x140031ff5  lea     rcx, [rbp+300h+var_1F0]; this
0x140031ffc  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140032001  mov     rcx, [rbp+300h+var_170]
0x140032008  test    rcx, rcx
0x14003200b  jz      short loc_140032019
0x14003200d  mov     rax, [rcx]
0x140032010  mov     rax, [rax+18h]
0x140032014  call    _guard_dispatch_icall
0x140032019  mov     rcx, [rbp+300h+var_200+8]; this
0x140032020  test    rcx, rcx
0x140032023  jz      short loc_14003202A
0x140032025  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003202a  lea     rcx, [rbp+300h+var_158]; this
0x140032031  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140032036  mov     rcx, [rbp+300h+var_D8]
0x14003203d  test    rcx, rcx
0x140032040  jz      short loc_14003204E
0x140032042  mov     rax, [rcx]
0x140032045  mov     rax, [rax+18h]
0x140032049  call    _guard_dispatch_icall
0x14003204e  mov     rcx, [rbp+300h+var_168+8]; this
0x140032055  test    rcx, rcx
0x140032058  jz      short loc_14003205F
0x14003205a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003205f  test    rsi, rsi
0x140032062  jz      short loc_140032089
0x140032064  cmp     [rsi+10h], r15b
0x140032068  jnz     short loc_140032070
0x14003206a  xorps   xmm0, xmm0
0x14003206d  movups  xmmword ptr [rsi], xmm0
0x140032070  mov     rcx, rsi; UnicodeString
0x140032073  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140032078  xor     edx, edx; Tag
0x14003207a  mov     rcx, rsi; P
0x14003207d  call    cs:__imp_ExFreePoolWithTag
0x140032084  nop     dword ptr [rax+rax+00h]
0x140032089  test    r14, r14
0x14003208c  jz      short loc_140032096
0x14003208e  mov     rcx, r14; this
0x140032091  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032096  test    rbx, rbx
0x140032099  jz      short loc_1400320A3
0x14003209b  mov     rcx, rbx; this
0x14003209e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400320a3  mov     rcx, [rsp+400h+FileNameInformation]
0x1400320a8  mov     [rsp+400h+FileNameInformation], r15
0x1400320ad  jmp     loc_140034849
0x1400320b2  lea     rax, aOriginSourceNo; "ORIGIN: Source not in a union, destinat"...
0x1400320b9  mov     edi, 0C0ED0003h
0x1400320be  mov     ecx, edi; this
0x1400320c0  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x1400320c5  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x1400320cc  mov     r8, 5ED000B050Eh; struct UnionFs::StackEventTracer *
0x1400320d6  mov     rdx, r12; int
0x1400320d9  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400320de  lea     rcx, [rbp+300h+var_1F0]; this
0x1400320e5  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400320ea  mov     rcx, [rbp+300h+var_170]
0x1400320f1  test    rcx, rcx
0x1400320f4  jz      short loc_140032102
0x1400320f6  mov     rax, [rcx]
0x1400320f9  mov     rax, [rax+18h]
0x1400320fd  call    _guard_dispatch_icall
0x140032102  mov     rcx, [rbp+300h+var_200+8]; this
0x140032109  test    rcx, rcx
0x14003210c  jz      short loc_140032113
0x14003210e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032113  lea     rcx, [rbp+300h+var_158]; this
0x14003211a  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003211f  mov     rcx, [rbp+300h+var_D8]
0x140032126  test    rcx, rcx
0x140032129  jz      short loc_140032137
0x14003212b  mov     rax, [rcx]
0x14003212e  mov     rax, [rax+18h]
0x140032132  call    _guard_dispatch_icall
0x140032137  mov     rcx, [rbp+300h+var_168+8]; this
0x14003213e  test    rcx, rcx
0x140032141  jz      short loc_140032148
0x140032143  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032148  test    rsi, rsi
  ... truncated ...
```
