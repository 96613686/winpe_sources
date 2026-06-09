# UnionFs::PreRename(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void * *,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)

- ea: `0x14002e3c8`
- end: `0x1400319b6`
- name: `?PreRename@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAPEAXAEAVStackEventTracer@1@PEBVUfsStreamHandleCtx@1@@Z`
- size: `13806`
- prototype: `int(UnionFs *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsStreamHandleCtx *)`
- caller_count: `1`
- callee_count: `59`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140034890`

## callees

- `0x140001008`
- `0x140002354`
- `0x1400029d0`
- `0x140004ff0`
- `0x1400057b0`
- `0x140005d20`
- `0x140005d5c`
- `0x140006340`
- `0x14000696c`
- `0x140008870`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140011148`
- `0x140011198`
- `0x14001124c`
- `0x1400112a8`
- `0x140027130`
- `0x140029560`
- `0x14002accc`
- `0x14002b6cc`
- `0x14002b824`
- `0x14002bb38`
- `0x14002bd24`
- `0x14002bea4`
- `0x14002e3c8`
- `0x140036180`
- `0x14003c658`
- `0x14003cd88`
- `0x140040e6c`
- `0x140041840`
- `0x140043474`
- `0x1400434c8`
- `0x1400438e4`
- `0x14004397c`
- `0x140044c04`
- `0x140055d9c`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140060ed8`
- `0x140061024`
- `0x140061090`
- `0x1400628e4`
- `0x140064370`
- `0x14006bca8`
- `0x14006e1a4`
- `0x14006efa8`
- `0x14006f8b8`
- `0x1400702e4`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14002f728`
- `ntoskrnl!IoGetSilo` at `0x140030e8a`
- `ntoskrnl!IoGetSilo` at `0x14002f728`
- `ntoskrnl!IoGetSilo` at `0x140030e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e831`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eafd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002edd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eeec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f04f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f1ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f348`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f471`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f56b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f5ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f652`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f7f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f8d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ff99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e831`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eafd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ebd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002edd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eeec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f04f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f1ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f348`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f471`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f56b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f5ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f652`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f7f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f8d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fe34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ff99`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14002f711`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14002f711`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002e580`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002e580`
- `ntoskrnl!ObfDereferenceObject` at `0x14003007e`
- `ntoskrnl!ObfDereferenceObject` at `0x14003007e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140031766`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140031766`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030100`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030223`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030405`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030662`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030100`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030223`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030405`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030662`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003010c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003022f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030411`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003066e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003010c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003022f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030411`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003066e`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14002e4e9`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14002e4e9`
- `FLTMGR!FltIsDirectory` at `0x14002e7d0`
- `FLTMGR!FltIsDirectory` at `0x140030067`
- `FLTMGR!FltIsDirectory` at `0x14002e7d0`
- `FLTMGR!FltIsDirectory` at `0x140030067`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e487`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e510`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e55a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e623`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e766`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e781`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e866`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eb32`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eca5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002ecc0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eea5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eec0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f084`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f1ff`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f61f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f955`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f970`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002faeb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002fc8b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002fd85`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002fedb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400302c4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400302e3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400304a6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400304c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400307f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030812`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400309e1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030a00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030e3e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030e59`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031875`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031890`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031961`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003197c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e487`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e510`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e55a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e623`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e766`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e781`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002e866`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eb32`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eca5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002ecc0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eea5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002eec0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f084`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f1ff`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f61f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f955`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f970`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002faeb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002fc8b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002fd85`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002fedb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400302c4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400302e3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400304a6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400304c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400307f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030812`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400309e1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030a00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030e3e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140030e59`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031875`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031890`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031961`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003197c`
- `FLTMGR!FltReleaseContext` at `0x140030729`
- `FLTMGR!FltReleaseContext` at `0x140030917`
- `FLTMGR!FltReleaseContext` at `0x140030a20`
- `FLTMGR!FltReleaseContext` at `0x140030729`
- `FLTMGR!FltReleaseContext` at `0x140030917`
- `FLTMGR!FltReleaseContext` at `0x140030a20`

## string_xrefs

- `0x1400305b4`: `PUSH: Getting relative path`
- `0x14002f0dc`: `PUSH: Cache lookup`
- `0x14002fa2d`: `PUSH: Cache lookup`
- `0x14002f7a8`: `PUSH: Allocating scratch path for layer lookup`
- `0x140031564`: `PUSH: Inserting path cache payload`
- `0x14002e462`: `UnionFs::PreRename`
- `0x14002e531`: `UnionFs::PreRename`
- `0x14002e5e2`: `UnionFs::PreRename`
- `0x14002e678`: `UnionFs::PreRename`
- `0x14002e6ff`: `UnionFs::PreRename`
- `0x14002e7fa`: `UnionFs::PreRename`
- `0x14002ea59`: `UnionFs::PreRename`
- `0x14002ebae`: `UnionFs::PreRename`
- `0x14002ed86`: `UnionFs::PreRename`
- `0x14002f0f2`: `UnionFs::PreRename`
- `0x14002f2b8`: `UnionFs::PreRename`
- `0x14002f3c3`: `UnionFs::PreRename`
- `0x14002f538`: `UnionFs::PreRename`
- `0x14002f675`: `UnionFs::PreRename`
- `0x14002f7be`: `UnionFs::PreRename`
- `0x14002f86d`: `UnionFs::PreRename`
- `0x14002fa43`: `UnionFs::PreRename`
- `0x14002fbda`: `UnionFs::PreRename`
- `0x14002fcd1`: `UnionFs::PreRename`
- `0x14002fe0b`: `UnionFs::PreRename`
- `0x1400300b1`: `UnionFs::PreRename`
- `0x1400301e6`: `UnionFs::PreRename`
- `0x140030337`: `UnionFs::PreRename`
- `0x14003056b`: `UnionFs::PreRename`
- `0x1400305ca`: `UnionFs::PreRename`
- `0x140030709`: `UnionFs::PreRename`
- `0x1400308fa`: `UnionFs::PreRename`
- `0x140030b65`: `UnionFs::PreRename`
- `0x140030caa`: `UnionFs::PreRename`
- `0x140030ede`: `UnionFs::PreRename`
- `0x140030fd0`: `UnionFs::PreRename`
- `0x140031109`: `UnionFs::PreRename`
- `0x1400311d0`: `UnionFs::PreRename`
- `0x14002e7e9`: `API: FltIsDirectory(source)`
- `0x14002edab`: `ORIGIN: Directory backed by layer descendants, cannot rename`
- `0x14002f285`: `!sourceCacheEntry || (renameFlags.SourceIsDirectory && (sourceCacheEntry->IsReplacedTombstone() || sourceCacheEntry->IsRenamedTombstone()))`
- `0x14002f507`: `sourceCacheEntry`
- `0x1400300a0`: `API: FltIsDirectory(BFO)`
- `0x140030360`: `Denying attempted superseding rename without flag.`
- `0x1400303b4`: `ORIGIN: superseding rename`
- `0x14003055f`: `ORIGIN: Rejecting COW for superseding rename with immutable destination`
- `0x140030638`: `PUSH: Converting cache entry to soft tombstone`
- `0x1400311ba`: `PUSH: Converting cache entry to soft tombstone`
- `0x140031440`: `PUSH: Converting cache entry to soft tombstone`
- `0x1400308d5`: `Path should exist`
- `0x140030cd7`: `Denying superseding POSIX rename of directory when source is a file.`
- `0x140030d2b`: `ORIGIN: POSIX superseding rename file -> directory`
- `0x140030ecd`: `PUSH: Checking POSIX superseding rename target`
- `0x140031016`: `Denying superseding POSIX rename of non-empty directory.`
- `0x14003104e`: `ORIGIN: POSIX superseding rename non-empty directory`
- `0x1400310f8`: `PUSH: Allocating path cache payload`
- `0x1400315e7`: `PUSH: Copying source name info to UfsPathName`
- `0x140031634`: `PUSH: Copying destination name info to UfsPathName`
- `0x1400317a6`: `ORIGIN: Allocating rename context`

## pseudocode

```c
__int64 __fastcall UnionFs::PreRename(
        struct _FLT_CALLBACK_DATA *this,
        struct _FLT_RELATED_OBJECTS *a2,
        struct _FILE_OBJECT *a3,
        void **a4,
        struct UnionFs::StackEventTracer *a5)
{
  struct UnionFs::StackEventTracer *v5; // r14
  UnionFs::StackEventTracer *v8; // rdi
  NTSTATUS DestinationFileNameInformation; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v10; // rcx
  PFLT_IO_PARAMETER_BLOCK FileNameLength; // rax
  struct _FILE_OBJECT *v13; // rdx
  WCHAR *EaBuffer; // rcx
  WCHAR *v15; // r9
  void *v16; // r8
  struct _FLT_INSTANCE *Instance; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v18; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  struct _FLT_FILE_NAME_INFORMATION *v22; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v23; // rcx
  ULONG_PTR v24; // rdx
  PFLT_INSTANCE v25; // rcx
  const struct _FLT_INSTANCE *v26; // rdx
  ULONG v27; // r9d
  int v28; // esi
  struct _UNICODE_STRING *v29; // rdx
  struct _UNICODE_STRING *v30; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v31; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v32; // rcx
  utl::_RefCountBase *v33; // r15
  volatile signed __int32 *v34; // rsi
  struct _UNICODE_STRING *v35; // r12
  struct _FLT_INSTANCE *v36; // rdx
  struct _FILE_OBJECT *v37; // rcx
  struct _UNICODE_STRING *v38; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v39; // rcx
  UnionFs::UfsLayerCtx *v40; // rbx
  char v41; // al
  char v42; // r13
  UnionFs::UfsLayerCtx **ScratchLayer; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v44; // rdx
  char v45; // bl
  int v46; // eax
  _QWORD *v47; // rbx
  struct FsFltWil::Details::RundownRefCacheAware *v48; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v49; // rdx
  struct _UNICODE_STRING *v50; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v51; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v52; // rcx
  PFILE_OBJECT v53; // rax
  int IsDirectoryEmpty; // eax
  const char *v55; // rcx
  __int64 v56; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v57; // rdx
  utl::_RefCountBase *v58; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v59; // rdx
  struct _UNICODE_STRING *v60; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v61; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v62; // rcx
  int v63; // r8d
  unsigned int v64; // r13d
  struct FsFltWil::Details::RundownRefCacheAware *v65; // rdx
  utl::_RefCountBase *v66; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v67; // rdx
  struct _UNICODE_STRING *v68; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v69; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v70; // rcx
  utl::_RefCountBase *v71; // rcx
  __int64 v72; // rax
  volatile signed __int32 *v73; // r15
  char v74; // r9
  __int64 v75; // r9
  __int64 v76; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v77; // rdx
  struct _UNICODE_STRING *v78; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v79; // rcx
  int v80; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v81; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v82; // rdx
  struct _UNICODE_STRING *v83; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v84; // rcx
  utl::_RefCountBase *v85; // rdx
  utl::_RefCountBase *v86; // rcx
  utl::_RefCountBase *Buffer; // rax
  _QWORD *v88; // rbx
  struct _UNICODE_STRING *v89; // rdx
  utl::_RefCountBase *v90; // rax
  int v91; // eax
  const char *v92; // rcx
  __int64 v93; // r8
  utl::_RefCountBase *v94; // rcx
  struct _UNICODE_STRING *v95; // rdx
  utl::_RefCountBase *v96; // rcx
  struct _UNICODE_STRING *v97; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v98; // rcx
  utl::_RefCountBase *v99; // rcx
  __m128i si128; // xmm6
  utl::_RefCountBase *v101; // r13
  utl::_RefCountBase *v102; // rbx
  PFILE_OBJECT v103; // rbx
  ULONG Flags; // edi
  __int64 Silo; // rax
  bool v106; // cf
  int v107; // eax
  struct _UNICODE_STRING *v108; // rdx
  struct _UNICODE_STRING *v109; // rbx
  utl::_RefCountBase *v110; // rbx
  struct UnionFs::StackEventTracer *v111; // r9
  int v112; // r8d
  struct _UNICODE_STRING *v113; // rdx
  struct _UNICODE_STRING *v114; // rbx
  struct _UNICODE_STRING *v115; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v116; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v117; // rcx
  char v118; // r9
  __int64 v119; // r9
  __int64 v120; // rcx
  int v121; // eax
  struct _FLT_FILE_NAME_INFORMATION *v122; // rcx
  utl::_RefCountBase *v123; // rax
  bool *v124; // rcx
  char v125; // dl
  struct _UNICODE_STRING *v126; // r13
  struct _FLT_FILE_NAME_INFORMATION *v127; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v128; // rcx
  struct _UNICODE_STRING v129; // xmm1
  int v130; // eax
  utl::_RefCountBase *v131; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v132; // rcx
  void *v133; // rax
  struct _UNICODE_STRING v134; // xmm1
  __int16 v135; // cx
  struct _UNICODE_STRING v136; // xmm0
  volatile signed __int32 *v137; // rax
  utl::_RefCountBase *v138; // rcx
  volatile signed __int32 *v139; // rax
  __int64 v140; // rdx
  struct _FLT_INSTANCE *v141; // rbx
  utl::_RefCountBase *v142; // rcx
  unsigned __int8 v143; // al
  int IsFileCowable; // eax
  struct _FLT_FILE_NAME_INFORMATION *v145; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v146; // rcx
  int v147; // edx
  const char *v148; // rax
  unsigned int v149; // edi
  __int64 v150; // r8
  struct _FLT_FILE_NAME_INFORMATION *v151; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v152; // rcx
  unsigned __int8 v153; // al
  int RemainingPath; // eax
  struct _UNICODE_STRING *v155; // rdx
  const char *v156; // rcx
  __int64 v157; // r8
  struct _UNICODE_STRING *v158; // rdx
  int v159; // ecx
  int v160; // r8d
  utl::_RefCountBase *v161; // rcx
  int v162; // r12d
  struct _UNICODE_STRING *v163; // rdx
  utl::_RefCountBase *v164; // rcx
  PVOID *p_Context; // rcx
  utl::_RefCountBase *v166; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v167; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v168; // rcx
  bool *v169; // r12
  UnionFs::UfsUnionCtx *v170; // r10
  __int64 v171; // rax
  const struct UnionFs::UfsLayerCtx *v172; // rcx
  int v173; // eax
  struct _UNICODE_STRING *v174; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v175; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v176; // rcx
  PFLT_INSTANCE v177; // r9
  __int64 v178; // r8
  volatile signed __int32 *v179; // rax
  unsigned int v180; // eax
  struct _UNICODE_STRING *v181; // rdx
  int v182; // r8d
  int v183; // r9d
  unsigned __int64 v184; // rcx
  struct _UNICODE_STRING *v185; // rdx
  struct _UNICODE_STRING *v186; // rdx
  utl::_RefCountBase *v187; // rcx
  utl::_RefCountBase *v188; // rcx
  struct _UNICODE_STRING *v189; // rdx
  struct _UNICODE_STRING *v190; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v191; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v192; // rcx
  UnionFs::UfsUnionCtx *v193; // rdi
  PFILE_OBJECT v194; // rcx
  bool v195; // bl
  const struct _EJOB *v196; // rax
  UnionFs::StackEventTracer *v197; // r12
  int v198; // r8d
  int v199; // r9d
  struct _UNICODE_STRING *v200; // rdx
  struct _UNICODE_STRING *v201; // rdx
  int v202; // r8d
  int v203; // eax
  utl::_RefCountBase *v204; // r13
  __int64 v205; // rcx
  struct _ERESOURCE *v206; // rdx
  int v207; // r8d
  int v208; // r9d
  UNICODE_STRING *p_Name; // rcx
  bool v210; // zf
  FsFltWil::Details *v211; // rcx
  const char *v212; // rax
  __int64 v213; // r8
  int v214; // r8d
  int v215; // eax
  __int64 v216; // r12
  __int64 v217; // rax
  __int64 v218; // rbx
  PVOID v219; // rax
  UnionFs::StackEventTracer *v220; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v221; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v222; // rcx
  const char *NameOptions; // [rsp+30h] [rbp-D8h]
  const char *NameOptionsa; // [rsp+30h] [rbp-D8h]
  UnionFs::StackEventTracer *NameOptionsb; // [rsp+30h] [rbp-D8h]
  const char *NameOptionsc; // [rsp+30h] [rbp-D8h]
  const char *NameOptionsd; // [rsp+30h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION v228; // [rsp+68h] [rbp-A0h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int8 IsDirectory[8]; // [rsp+78h] [rbp-90h] BYREF
  struct _UNICODE_STRING *v231; // [rsp+80h] [rbp-88h] BYREF
  PVOID Context; // [rsp+88h] [rbp-80h] BYREF
  PVOID v233; // [rsp+90h] [rbp-78h] BYREF
  PVOID v234; // [rsp+98h] [rbp-70h] BYREF
  UnionFs::StackEventTracer *v235; // [rsp+A0h] [rbp-68h] BYREF
  utl::_RefCountBase *v236[2]; // [rsp+A8h] [rbp-60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v238; // [rsp+C0h] [rbp-48h]
  int v239; // [rsp+C4h] [rbp-44h]
  utl::_RefCountBase *v240; // [rsp+C8h] [rbp-40h] BYREF
  utl::_RefCountBase *v241[2]; // [rsp+D0h] [rbp-38h] BYREF
  void *v242; // [rsp+E0h] [rbp-28h] BYREF
  PVOID v243; // [rsp+E8h] [rbp-20h] BYREF
  struct _FLT_CALLBACK_DATA *v244; // [rsp+F0h] [rbp-18h] BYREF
  bool *v245; // [rsp+F8h] [rbp-10h] BYREF
  struct _FLT_FILE_NAME_INFORMATION **v246; // [rsp+108h] [rbp+0h] BYREF
  PFLT_FILE_NAME_INFORMATION RetFileNameInformation; // [rsp+110h] [rbp+8h] BYREF
  __int64 v248; // [rsp+118h] [rbp+10h]
  utl::_RefCountBase *v249; // [rsp+128h] [rbp+20h]
  utl::_RefCountBase *v250[2]; // [rsp+138h] [rbp+30h] BYREF
  utl::_RefCountBase *v251[2]; // [rsp+148h] [rbp+40h] BYREF
  struct _FLT_RELATED_OBJECTS *v252; // [rsp+158h] [rbp+50h]
  PVOID v253[2]; // [rsp+160h] [rbp+58h] BYREF
  UnionFs *v254; // [rsp+170h] [rbp+68h] BYREF
  __int64 v255; // [rsp+178h] [rbp+70h] BYREF
  utl::_RefCountBase *v256[2]; // [rsp+180h] [rbp+78h]
  PVOID P; // [rsp+190h] [rbp+88h]
  struct _UNICODE_STRING UnicodeString; // [rsp+198h] [rbp+90h] BYREF
  UnionFs::UfsScratchMappingTable *v259; // [rsp+1A8h] [rbp+A0h] BYREF
  char v260[8]; // [rsp+1B0h] [rbp+A8h] BYREF
  __int128 v261; // [rsp+1B8h] [rbp+B0h] BYREF
  utl::_RefCountBase *v262[2]; // [rsp+1C8h] [rbp+C0h]
  __int64 v263; // [rsp+1D8h] [rbp+D0h]
  int v264; // [rsp+1E0h] [rbp+D8h]
  struct _FILE_OBJECT *v265; // [rsp+1E8h] [rbp+E0h]
  __int128 v266; // [rsp+1F8h] [rbp+F0h] BYREF
  utl::_RefCountBase *v267[2]; // [rsp+208h] [rbp+100h]
  __int64 v268; // [rsp+218h] [rbp+110h] BYREF
  __int64 v269; // [rsp+220h] [rbp+118h]
  struct UnionFs::UfsPathName *v270[2]; // [rsp+228h] [rbp+120h]
  struct _UNICODE_STRING v271[7]; // [rsp+238h] [rbp+130h] BYREF
  PWSTR *p_Buffer; // [rsp+2A8h] [rbp+1A0h]
  char v273[152]; // [rsp+2D8h] [rbp+1D0h] BYREF
  utl::_RefCountBase *v274[2]; // [rsp+370h] [rbp+268h] BYREF
  _QWORD v275[17]; // [rsp+380h] [rbp+278h] BYREF
  utl::_RefCountBase *v276[2]; // [rsp+408h] [rbp+300h] BYREF
  _QWORD v277[18]; // [rsp+418h] [rbp+310h] BYREF
  _DWORD v278[20]; // [rsp+4A8h] [rbp+3A0h] BYREF
  _BYTE v279[392]; // [rsp+4F8h] [rbp+3F0h] BYREF

  v5 = a5;
  *(_QWORD *)&a3->Type = 0;
  v265 = a3;
  v252 = a2;
  v244 = this;
  v246 = (struct _FLT_FILE_NAME_INFORMATION **)this;
  v8 = (UnionFs::StackEventTracer *)a4;
  v235 = (UnionFs::StackEventTracer *)a4;
  v238 = 0;
  FileNameInformation = 0;
  RetFileNameInformation = 0;
  v248 = 0;
  DestinationFileNameInformation = UnionFs::Utils::GetFileNameInformation(&v246, 16778241, &FileNameInformation, a4);
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x360000B0031LL,
      (unsigned __int64)"UnionFs::PreRename",
      "PUSH: Getting source file name information",
      NameOptions);
LABEL_3:
    v10 = FileNameInformation;
    FileNameInformation = 0;
LABEL_4:
    if ( v10 )
      FltReleaseFileNameInformation(v10);
    return (unsigned int)DestinationFileNameInformation;
  }
  FileNameLength = this->Iopb;
  v13 = a2->FileObject;
  v228 = 0;
  RetFileNameInformation = 0;
  EaBuffer = (WCHAR *)FileNameLength->Parameters.Create.EaBuffer;
  v246 = &v228;
  v253[0] = EaBuffer;
  LODWORD(FileNameLength) = *((_DWORD *)EaBuffer + 4);
  v15 = EaBuffer + 10;
  v16 = (void *)*((_QWORD *)EaBuffer + 1);
  Instance = a2->Instance;
  LOBYTE(v248) = 1;
  DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                     Instance,
                                     v13,
                                     v16,
                                     v15,
                                     (ULONG)FileNameLength,
                                     0x1000101u,
                                     &RetFileNameInformation);
  if ( (_BYTE)v248 )
  {
    v18 = *v246;
    *v246 = RetFileNameInformation;
    if ( v18 )
      FltReleaseFileNameInformation(v18);
  }
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x361000B0042LL,
      (unsigned __int64)"UnionFs::PreRename",
      "API: Getting destination file name",
      NameOptionsa);
    goto LABEL_12;
  }
  if ( !RtlCompareUnicodeString(&FileNameInformation->Name, &v228->Name, 0) )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x60) != 0
      && (qword_14009E190 & 0x60) == qword_14009E190 )
    {
      LODWORD(v240) = 76;
      v253[0] = "Source and destination same";
      v243 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
      v235 = (UnionFs::StackEventTracer *)"UnionFs::PreRename";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        qword_14009E190,
        (unsigned int)byte_140096A8D,
        v20,
        v21,
        (__int64)v253,
        (__int64)&v235,
        (__int64)&v243,
        (__int64)&v240);
    }
LABEL_19:
    v22 = v228;
    v228 = 0;
    if ( v22 )
      FltReleaseFileNameInformation(v22);
    v23 = FileNameInformation;
    FileNameInformation = 0;
LABEL_753:
    if ( v23 )
      FltReleaseFileNameInformation(v23);
    return 0;
  }
  v24 = (ULONG_PTR)a2->FileObject;
  v25 = a2->Instance;
  v259 = 0;
  DestinationFileNameInformation = UnionFs::Utils::GetMappingTableForFileObject(v25, v24, &v259, v8, 0);
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x337000B0059LL,
      (unsigned __int64)"UnionFs::PreRename",
      "PUSH: Getting mapping table",
      NameOptionsa);
LABEL_12:
    v19 = v228;
    v228 = 0;
    if ( v19 )
      FltReleaseFileNameInformation(v19);
    goto LABEL_3;
  }
  if ( !v259 )
    goto LABEL_19;
  v26 = a2->Instance;
  v27 = a2->FileObject->Flags >> 17;
  v255 = 1;
  P = 0;
  *(_OWORD *)v256 = 0;
  v28 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
          v259,
          v26,
          v228,
          (v27 & 1) == 0,
          (struct UnionFs::LookupScratchRootResults *)&v255,
          v8);
  if ( v28 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v28,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x345000B006BLL,
      (unsigned __int64)"UnionFs::PreRename",
      "PUSH: Looking up scratch root",
      (const char *)NameOptionsb);
    v30 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v30, v29);
      ExFreePoolWithTag(v30, 0);
    }
    if ( v256[1] )
      utl::_RefCountBase::_DecStrong(v256[1]);
    v31 = v228;
    v228 = 0;
    if ( v31 )
      FltReleaseFileNameInformation(v31);
    v32 = FileNameInformation;
    FileNameInformation = 0;
    if ( v32 )
      FltReleaseFileNameInformation(v32);
    return (unsigned int)v28;
  }
  v33 = v256[1];
  v34 = (volatile signed __int32 *)v256[1];
  if ( v256[1] )
    _InterlockedIncrement((volatile signed __int32 *)v256[1] + 2);
  v35 = (struct _UNICODE_STRING *)P;
  v36 = a2->Instance;
  v37 = a2->FileObject;
  v233 = P;
  P = 0;
  IsDirectory[3] = 0;
  DestinationFileNameInformation = FltIsDirectory(v37, v36, &IsDirectory[3]);
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0xEB000B0075LL,
      (unsigned __int64)"UnionFs::PreRename",
      "API: FltIsDirectory(source)",
      (const char *)NameOptionsb);
    if ( v35 )
    {
      if ( !LOBYTE(v35[1].Length) )
        *v35 = 0;
      FsFltWil::Details::FreeUnicodeString(v35, v38);
      ExFreePoolWithTag(v35, 0);
    }
    if ( v33 )
    {
      utl::_RefCountBase::_DecStrong(v33);
      utl::_RefCountBase::_DecStrong(v33);
    }
    v39 = v228;
    v228 = 0;
    if ( v39 )
      FltReleaseFileNameInformation(v39);
    v10 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_4;
  }
  v40 = v256[0];
  v239 = 0;
  v259 = v256[0];
  if ( v244->Iopb->Parameters.Create.Options == 65 && (*(_DWORD *)v253[0] & 2) != 0 )
    v41 = 8;
  else
    v41 = 0;
  v42 = v41 | (IsDirectory[3] != 0 ? 2 : 0);
  LOBYTE(v239) = v42;
  *(_OWORD *)v276 = 0;
  memset(v277, 0, 0x88u);
  if ( a5 )
  {
    ScratchLayer = (UnionFs::UfsLayerCtx **)UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(a5, v251);
    UnionFs::UfsLayerCtx::TryGetOwningUnion(*ScratchLayer, (struct UnionFs::UfsUnionCtxWithRundown *)v276, v8);
    if ( v251[1] )
      utl::_RefCountBase::_DecStrong(v251[1]);
    if ( !v276[0] )
    {
      *(_DWORD *)v8 = 0;
      v5 = 0;
      *((_WORD *)v8 + 274) = 0;
    }
  }
  *(_OWORD *)v274 = 0;
  memset(v275, 0, sizeof(v275));
  if ( v40 )
  {
    UnionFs::UfsLayerCtx::TryGetOwningUnion(v40, (struct UnionFs::UfsUnionCtxWithRundown *)v274, v8);
    if ( !v274[0] )
    {
      *(_DWORD *)v8 = 0;
      *((_WORD *)v8 + 274) = 0;
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
      v40 = 0;
      v259 = 0;
      v34 = 0;
    }
  }
  if ( !v5 )
  {
    if ( !v40 )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v275, v44);
      if ( v275[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v275[16] + 24LL))(v275[16]);
      if ( v274[1] )
        utl::_RefCountBase::_DecStrong(v274[1]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v277, v77);
      if ( v277[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v277[16] + 24LL))(v277[16]);
      if ( v276[1] )
        utl::_RefCountBase::_DecStrong(v276[1]);
      if ( v35 )
      {
        if ( !LOBYTE(v35[1].Length) )
          *v35 = 0;
        FsFltWil::Details::FreeUnicodeString(v35, v78);
        ExFreePoolWithTag(v35, 0);
      }
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
      v79 = v228;
      v228 = 0;
      if ( v79 )
        FltReleaseFileNameInformation(v79);
      v23 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_753;
    }
    goto LABEL_159;
  }
  if ( (v42 & 2) == 0 )
    goto LABEL_159;
  if ( v40 )
  {
    v238 = 1;
    if ( *(UnionFs::UfsLayerCtx **)UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(v5, v251) == v40 )
    {
      v45 = 0;
      v46 = 1;
      goto LABEL_70;
    }
  }
  v45 = 1;
  if ( (v238 & 1) != 0 )
  {
    v46 = v238;
LABEL_70:
    v238 = v46 & 0xFFFFFFFE;
    if ( v251[1] )
      utl::_RefCountBase::_DecStrong(v251[1]);
    if ( !v45 )
      goto LABEL_159;
  }
  if ( (*(_DWORD *)v5 & 8) == 0 )
  {
    utl::make_unique<UnionFs::FindAndStatResults,,0>(&v243);
    v47 = v243;
    if ( !v243 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x63E000B00AFLL,
        (unsigned __int64)"UnionFs::PreRename",
        "ORIGIN: Allocating findAndStatResults",
        (const char *)NameOptionsb);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v275, v48);
      if ( v275[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v275[16] + 24LL))(v275[16]);
      if ( v274[1] )
        utl::_RefCountBase::_DecStrong(v274[1]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v277, v49);
      if ( v277[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v277[16] + 24LL))(v277[16]);
      if ( v276[1] )
        utl::_RefCountBase::_DecStrong(v276[1]);
      if ( v35 )
      {
        if ( !LOBYTE(v35[1].Length) )
          *v35 = 0;
        FsFltWil::Details::FreeUnicodeString(v35, v50);
        ExFreePoolWithTag(v35, 0);
      }
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
LABEL_91:
      v51 = v228;
      v228 = 0;
      if ( v51 )
        FltReleaseFileNameInformation(v51);
      v52 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_737;
    }
    NameOptionsb = v8;
    v53 = v252->FileObject;
    *(_OWORD *)v251 = *(_OWORD *)*((_QWORD *)v5 + 8);
    IsDirectoryEmpty = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(
                         v276[0],
                         v251,
                         v5,
                         (v53->Flags & 0x20000) == 0,
                         v243);
    LODWORD(v240) = IsDirectoryEmpty;
    if ( IsDirectoryEmpty < 0 )
    {
      v55 = "PUSH: Checking for item in layers";
      v56 = 0x63F000B00BELL;
LABEL_96:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)IsDirectoryEmpty,
        (int)v8,
        (struct UnionFs::StackEventTracer *)v56,
        (unsigned __int64)"UnionFs::PreRename",
        v55,
        (const char *)v8);
      if ( v47 )
      {
        v58 = (utl::_RefCountBase *)v47[11];
        if ( v58 )
          utl::_RefCountBase::_DecStrong(v58);
        ExFreePoolWithTag(v47, 0);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v275, v57);
      if ( v275[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v275[16] + 24LL))(v275[16]);
      if ( v274[1] )
        utl::_RefCountBase::_DecStrong(v274[1]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v277, v59);
      if ( v277[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v277[16] + 24LL))(v277[16]);
      if ( v276[1] )
        utl::_RefCountBase::_DecStrong(v276[1]);
      if ( v35 )
      {
        if ( !LOBYTE(v35[1].Length) )
          *v35 = 0;
        FsFltWil::Details::FreeUnicodeString(v35, v60);
        ExFreePoolWithTag(v35, 0);
      }
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
LABEL_116:
      v61 = v228;
      v228 = 0;
      if ( v61 )
        FltReleaseFileNameInformation(v61);
      v62 = FileNameInformation;
      FileNameInformation = 0;
      if ( v62 )
        FltReleaseFileNameInformation(v62);
      return (unsigned int)v240;
    }
    if ( *(_WORD *)v47 == 1 )
    {
      IsDirectory[1] = 0;
      IsDirectoryEmpty = UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty(v5, v244, (bool *)&IsDirectory[1], v8, 0);
      LODWORD(v240) = IsDirectoryEmpty;
      if ( IsDirectoryEmpty < 0 )
      {
        v55 = "PUSH: Check if source dir empty";
        v56 = 0x644000B00CBLL;
        goto LABEL_96;
      }
      if ( !IsDirectory[1] )
      {
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x400000000000LL) != 0
          && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
        {
          v243 = (PVOID)1;
          v235 = (UnionFs::StackEventTracer *)0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)&unk_140096B58,
            v63,
            (unsigned int)&v235,
            (__int64)&v243);
        }
        v64 = (v259 == 0) - 1058209791;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)v64,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x640000B00D9LL,
          (unsigned __int64)"UnionFs::PreRename",
          "ORIGIN: Directory backed by layer descendants, cannot rename",
          (const char *)v8);
        if ( v47 )
        {
          v66 = (utl::_RefCountBase *)v47[11];
          if ( v66 )
            utl::_RefCountBase::_DecStrong(v66);
          ExFreePoolWithTag(v47, 0);
        }
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v275, v65);
        if ( v275[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v275[16] + 24LL))(v275[16]);
        if ( v274[1] )
          utl::_RefCountBase::_DecStrong(v274[1]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v277, v67);
        if ( v277[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v277[16] + 24LL))(v277[16]);
        if ( v276[1] )
          utl::_RefCountBase::_DecStrong(v276[1]);
        if ( v35 )
        {
          if ( !LOBYTE(v35[1].Length) )
            *v35 = 0;
          FsFltWil::Details::FreeUnicodeString(v35, v68);
          ExFreePoolWithTag(v35, 0);
        }
        if ( v34 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
        if ( v33 )
          utl::_RefCountBase::_DecStrong(v33);
        v69 = v228;
        v228 = 0;
        if ( v69 )
          FltReleaseFileNameInformation(v69);
        v70 = FileNameInformation;
        FileNameInformation = 0;
LABEL_152:
        if ( v70 )
          FltReleaseFileNameInformation(v70);
        return v64;
      }
    }
    if ( v47 )
    {
      v71 = (utl::_RefCountBase *)v47[11];
      if ( v71 )
        utl::_RefCountBase::_DecStrong(v71);
      ExFreePoolWithTag(v47, 0);
    }
  }
LABEL_159:
  LOBYTE(v248) = 1;
  v246 = (struct _FLT_FILE_NAME_INFORMATION **)v236;
  RetFileNameInformation = (PFLT_FILE_NAME_INFORMATION)v241;
  *(_OWORD *)v236 = 0;
  *(_OWORD *)v241 = 0;
  if ( !v5 )
  {
    v73 = 0;
    v243 = 0;
    goto LABEL_286;
  }
  v72 = UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(v5, v251);
  v73 = *(volatile signed __int32 **)(v72 + 8);
  v243 = *(PVOID *)v72;
  *(_QWORD *)v72 = 0;
  *(_QWORD *)(v72 + 8) = 0;
  if ( v251[1] )
    utl::_RefCountBase::_DecStrong(v251[1]);
  v74 = ~(unsigned __int8)(v252->FileObject->Flags >> 17);
  memset(v271, 0, 64);
  v75 = v74 & 1 | 2u;
  if ( *((_DWORD *)v276[0] + 7) == 2 )
    v76 = *(_QWORD *)(*((_QWORD *)v276[0] + 4) + 16LL);
  else
    v76 = *((_QWORD *)UnionFs::g_FilterState + 10);
  NameOptionsb = v8;
  v80 = UnionFs::UfsPathCache::LookupEntry(v76, v252->Instance, FileNameInformation, v75, v271);
  DestinationFileNameInformation = v80;
  if ( v80 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v80,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x349000B0111LL,
      (unsigned __int64)"UnionFs::PreRename",
      "PUSH: Cache lookup",
      (const char *)v8);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v271);
    if ( v73 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
    wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
    if ( v241[1] )
      utl::_RefCountBase::_DecStrong(v241[1]);
    if ( v236[1] )
      utl::_RefCountBase::_DecStrong(v236[1]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v275, v81);
    if ( v275[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v275[16] + 24LL))(v275[16]);
    if ( v274[1] )
      utl::_RefCountBase::_DecStrong(v274[1]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v277, v82);
    if ( v277[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v277[16] + 24LL))(v277[16]);
    if ( v276[1] )
      utl::_RefCountBase::_DecStrong(v276[1]);
    if ( v35 )
    {
      if ( !LOBYTE(v35[1].Length) )
        *v35 = 0;
      FsFltWil::Details::FreeUnicodeString(v35, v83);
      ExFreePoolWithTag(v35, 0);
    }
LABEL_204:
    if ( v34 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
    v84 = v228;
    v228 = 0;
    if ( v84 )
      FltReleaseFileNameInformation(v84);
    v10 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_4;
  }
  v85 = *(utl::_RefCountBase **)&v271[1].Length;
  if ( *(_QWORD *)&v271[1].Length )
  {
    v86 = v236[1];
    Buffer = (utl::_RefCountBase *)v271[1].Buffer;
    v271[1] = 0;
    v236[0] = v85;
    v236[1] = Buffer;
    if ( !v86 )
      goto LABEL_213;
    utl::_RefCountBase::_DecStrong(v86);
  }
  v85 = v236[0];
LABEL_213:
  if ( v85 && ((v42 & 2) == 0 || *((_WORD *)v85 + 80) != 3 && *((_WORD *)v236[0] + 80) != 4) )
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "!sourceCacheEntry || (renameFlags.SourceIsDirectory && (sourceCacheEntry->IsReplacedTombstone() || sourceCacheEntr"
      "y->IsRenamedTombstone()))");
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&Context);
  v88 = Context;
  if ( !Context )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x40A000B0126LL,
      (unsigned __int64)"UnionFs::PreRename",
      "ORIGIN: Allocating findAndStatResults",
      (const char *)v8);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v271);
    if ( v73 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
    wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
    if ( v241[1] )
      utl::_RefCountBase::_DecStrong(v241[1]);
    if ( v236[1] )
      utl::_RefCountBase::_DecStrong(v236[1]);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
    if ( v35 )
    {
      if ( !LOBYTE(v35[1].Length) )
        *v35 = 0;
      FsFltWil::Details::FreeUnicodeString(v35, v89);
      ExFreePoolWithTag(v35, 0);
    }
    if ( v34 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
    goto LABEL_91;
  }
  v90 = v236[0];
  if ( !v236[0] )
  {
    NameOptionsb = v8;
    v91 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v276[0], &FileNameInformation->Name, v5, 1, Context);
    LODWORD(v240) = v91;
    if ( v91 < 0 )
    {
      v92 = "PUSH: Failed to lookup entry";
      v93 = 0x342000B0132LL;
LABEL_235:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v91,
        (int)v8,
        (struct UnionFs::StackEventTracer *)v93,
        (unsigned __int64)"UnionFs::PreRename",
        v92,
        (const char *)NameOptionsb);
      if ( v88 )
      {
        v94 = (utl::_RefCountBase *)v88[11];
        if ( v94 )
          utl::_RefCountBase::_DecStrong(v94);
        ExFreePoolWithTag(v88, 0);
      }
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v271);
LABEL_240:
      if ( v73 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
      wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
      if ( v241[1] )
        utl::_RefCountBase::_DecStrong(v241[1]);
      if ( v236[1] )
        utl::_RefCountBase::_DecStrong(v236[1]);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
      if ( v35 )
      {
        if ( !LOBYTE(v35[1].Length) )
          *v35 = 0;
        FsFltWil::Details::FreeUnicodeString(v35, v95);
        ExFreePoolWithTag(v35, 0);
      }
LABEL_250:
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
      goto LABEL_116;
    }
    v90 = v236[0];
  }
  if ( *(_WORD *)v88 == 1 || v90 )
  {
    v42 |= 1u;
    LOBYTE(v239) = v42;
    v91 = UnionFs::Utils::MarkFileAsSoftTombstone(
            (int)v252->Instance,
            (int)v276[0],
            (int)FileNameInformation,
            2,
            (__int64)v236,
            (char *)v8);
    LODWORD(v240) = v91;
    if ( v91 < 0 )
    {
      v92 = "PUSH: Could not place soft tombstone";
      v93 = 0x150000B0146LL;
      goto LABEL_235;
    }
    if ( !v236[0] )
      MicrosoftTelemetryAssertTriggeredMsgKM("sourceCacheEntry");
    if ( !UnionFs::UfsUnionCtx::ReserveSpaceForTombstone(v276[0]) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x3FF000B0151LL,
        (unsigned __int64)"UnionFs::PreRename",
        "ORIGIN: Reserving tombstone space",
        (const char *)NameOptionsb);
      if ( v88 )
      {
        v96 = (utl::_RefCountBase *)v88[11];
        if ( v96 )
          utl::_RefCountBase::_DecStrong(v96);
        ExFreePoolWithTag(v88, 0);
      }
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v271);
      if ( v73 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
      wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
      if ( v241[1] )
        utl::_RefCountBase::_DecStrong(v241[1]);
      if ( v236[1] )
        utl::_RefCountBase::_DecStrong(v236[1]);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
      if ( v35 )
      {
        if ( !LOBYTE(v35[1].Length) )
          *v35 = 0;
        FsFltWil::Details::FreeUnicodeString(v35, v97);
        ExFreePoolWithTag(v35, 0);
      }
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
      v98 = v228;
      v228 = 0;
      if ( v98 )
        FltReleaseFileNameInformation(v98);
      v52 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_737;
    }
  }
  if ( v88 )
  {
    v99 = (utl::_RefCountBase *)v88[11];
    if ( v99 )
      utl::_RefCountBase::_DecStrong(v99);
    ExFreePoolWithTag(v88, 0);
  }
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v271);
LABEL_286:
  si128 = 0;
  Context = 0;
  *(_OWORD *)v250 = 0;
  v242 = 0;
  if ( !v259 )
  {
    v101 = v250[1];
    v102 = v250[0];
LABEL_707:
    Context = 0;
    v162 = UnionFs::UfsPathName::AllocAndInit(FileNameInformation, &Context, v8);
    if ( v162 >= 0 )
    {
      v244 = 0;
      v162 = UnionFs::UfsPathName::AllocAndInit(v228, &v244, v8);
      if ( v162 >= 0 )
      {
        v216 = UnionFs::UfsUnionCtxWithRundown::UfsUnionCtxWithRundown(v271, v274);
        v217 = UnionFs::UfsUnionCtxWithRundown::UfsUnionCtxWithRundown(v273, v276);
        v251[1] = (utl::_RefCountBase *)v34;
        v251[0] = v259;
        if ( v34 )
          _InterlockedIncrement(v34 + 2);
        *(_QWORD *)&UnicodeString.Length = v243;
        UnicodeString.Buffer = (PWSTR)v73;
        if ( v73 )
          _InterlockedIncrement(v73 + 2);
        v243 = v244;
        v235 = (UnionFs::StackEventTracer *)Context;
        v244 = 0;
        Context = 0;
        v250[0] = v102;
        v250[1] = v101;
        if ( v101 )
          _InterlockedIncrement((volatile signed __int32 *)v101 + 2);
        v253[0] = v236[0];
        v253[1] = v236[1];
        if ( v236[1] )
          _InterlockedIncrement((volatile signed __int32 *)v236[1] + 2);
        v218 = UnionFs::RenameContext::RenameContext(
                 (unsigned int)v279,
                 (unsigned int)v253,
                 (unsigned int)v250,
                 (unsigned int)&v235,
                 (__int64)&v243,
                 (__int64)&UnicodeString,
                 (__int64)v251,
                 v217,
                 v216,
                 v239);
        v219 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 320));
        if ( v219 )
          v220 = (UnionFs::StackEventTracer *)UnionFs::RenameContext::RenameContext(v219, v218);
        else
          v220 = 0;
        v235 = v220;
        UnionFs::RenameContext::~RenameContext((UnionFs::RenameContext *)v279);
        if ( v220 )
        {
          v235 = 0;
          LOBYTE(v248) = 0;
          *(_QWORD *)&v265->Type = v220;
          utl::unique_ptr<UnionFs::RenameContext,utl::default_delete<UnionFs::RenameContext>>::~unique_ptr<UnionFs::RenameContext,utl::default_delete<UnionFs::RenameContext>>(&v235);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v244);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
          if ( v101 )
            utl::_RefCountBase::_DecStrong(v101);
          if ( v73 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
          wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
          if ( v241[1] )
            utl::_RefCountBase::_DecStrong(v241[1]);
          if ( v236[1] )
            utl::_RefCountBase::_DecStrong(v236[1]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
          if ( v34 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
          v222 = v228;
          v228 = 0;
          if ( v222 )
            FltReleaseFileNameInformation(v222);
          v23 = FileNameInformation;
          FileNameInformation = 0;
          goto LABEL_753;
        }
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x338000B03ABLL,
          (unsigned __int64)"UnionFs::PreRename",
          "ORIGIN: Allocating rename context",
          NameOptionsd);
        utl::unique_ptr<UnionFs::RenameContext,utl::default_delete<UnionFs::RenameContext>>::~unique_ptr<UnionFs::RenameContext,utl::default_delete<UnionFs::RenameContext>>(&v235);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v244);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
        if ( v101 )
          utl::_RefCountBase::_DecStrong(v101);
        if ( v73 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
        wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
        if ( v241[1] )
          utl::_RefCountBase::_DecStrong(v241[1]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
        if ( v34 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
        v221 = v228;
        v228 = 0;
        if ( v221 )
          FltReleaseFileNameInformation(v221);
        v52 = FileNameInformation;
        FileNameInformation = 0;
LABEL_737:
        if ( v52 )
          FltReleaseFileNameInformation(v52);
        return 3221225626LL;
      }
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v162,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x3C4000B0397LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Copying destination name info to UfsPathName",
        (const char *)NameOptionsb);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v244);
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v162,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x3C3000B0391LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Copying source name info to UfsPathName",
        (const char *)NameOptionsb);
    }
    p_Context = &Context;
LABEL_503:
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(p_Context);
    wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
    if ( v101 )
    {
      v166 = v101;
      goto LABEL_505;
    }
    goto LABEL_506;
  }
  if ( v244->Iopb->Parameters.Create.Options == 65 )
    IsDirectory[1] = *(_BYTE *)v253[0] & 1;
  else
    IsDirectory[1] = *(_BYTE *)v253[0] != 0;
  v271[0].Buffer = (PWSTR)off_14007E740;
  p_Buffer = &v271[0].Buffer;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(v8, v271);
  v103 = v252->FileObject;
  Flags = v103->Flags;
  memset(v278, 0, 0x48u);
  IoGetTransactionParameterBlock(v103);
  Silo = IoGetSilo(v252->FileObject);
  v106 = (Flags & 0x20000) != 0;
  v8 = v235;
  NameOptionsb = v235;
  LODWORD(v254) = UnionFs::Utils::StatItem(&v228->Name, v252->Instance, Silo, !v106, v278);
  UnionFs::StackEventTracer::ClearIgnoreStatusCallback(v8);
  v231 = 0;
  v107 = UnionFs::UfsPathName::AllocAndInit(v228, &v231, v8);
  LODWORD(v240) = v107;
  if ( v107 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v107,
      (int)v8,
      (struct UnionFs::StackEventTracer *)0x60E000B018CLL,
      (unsigned __int64)"UnionFs::PreRename",
      "PUSH: Allocating scratch path for layer lookup",
      (const char *)NameOptionsb);
    v109 = v231;
    if ( v231 )
    {
      if ( !LOBYTE(v231[1].Length) )
        *v231 = 0;
      FsFltWil::Details::FreeUnicodeString(v109, v108);
      ExFreePoolWithTag(v109, 0);
    }
    goto LABEL_240;
  }
  v110 = 0;
  v253[0] = 0;
  v249 = 0;
  IsDirectory[0] = 0;
  v234 = 0;
  memset(v271, 0, 0x48u);
  v112 = 0;
  if ( (int)v254 < 0 )
  {
    if ( (_DWORD)v254 != -1073741766 && (_DWORD)v254 != -1073741772 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v254,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x34F000B01A1LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Querying stat information",
        (const char *)NameOptionsb);
      v114 = (struct _UNICODE_STRING *)v234;
      if ( v234 )
      {
        if ( !*((_BYTE *)v234 + 16) )
          *(_OWORD *)v234 = 0;
        FsFltWil::Details::FreeUnicodeString(v114, v113);
        ExFreePoolWithTag(v114, 0);
      }
      v115 = v231;
      if ( v231 )
      {
        if ( !LOBYTE(v231[1].Length) )
          *v231 = 0;
        FsFltWil::Details::FreeUnicodeString(v115, v113);
        ExFreePoolWithTag(v115, 0);
      }
      if ( v73 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
      wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
      if ( v241[1] )
        utl::_RefCountBase::_DecStrong(v241[1]);
      if ( v236[1] )
        utl::_RefCountBase::_DecStrong(v236[1]);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
      v116 = v228;
      v228 = 0;
      if ( v116 )
        FltReleaseFileNameInformation(v116);
      v117 = FileNameInformation;
      FileNameInformation = 0;
      if ( v117 )
        FltReleaseFileNameInformation(v117);
      return (unsigned int)v254;
    }
    v118 = ~(unsigned __int8)(v252->FileObject->Flags >> 17);
    v266 = 0;
    v119 = v118 & 1 | 0xAu;
    *(_OWORD *)v267 = 0;
    v268 = 0;
    LODWORD(v266) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
    v269 = 0;
    *(_OWORD *)v270 = 0;
    if ( *((_DWORD *)v274[0] + 7) == 2 )
      v120 = *(_QWORD *)(*((_QWORD *)v274[0] + 4) + 16LL);
    else
      v120 = *((_QWORD *)UnionFs::g_FilterState + 10);
    NameOptionsb = v8;
    v121 = UnionFs::UfsPathCache::LookupEntry(v120, v252->Instance, v228, v119, &v266);
    v64 = v121;
    if ( v121 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v121,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x34D000B01C3LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Cache lookup",
        (const char *)v8);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v266);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
      if ( v73 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
      wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
      if ( v241[1] )
        utl::_RefCountBase::_DecStrong(v241[1]);
      if ( v236[1] )
        utl::_RefCountBase::_DecStrong(v236[1]);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
      v122 = v228;
      v228 = 0;
      if ( v122 )
        FltReleaseFileNameInformation(v122);
      v70 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_152;
    }
    v123 = v267[0];
    IsDirectory[2] = 1;
    v245 = (bool *)v267[0];
    if ( v267[0] )
    {
      v101 = v267[1];
      v250[1] = v267[1];
      *(_OWORD *)v267 = 0;
      v250[0] = v123;
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
        &v242,
        &v268);
      si128 = _mm_load_si128((const __m128i *)v250);
      v124 = v245;
      v125 = (BYTE8(v266) & 4) != 0;
      Context = v242;
    }
    else
    {
      if ( (_DWORD)v269 == 1 )
      {
        IsDirectory[2] = 0;
        v101 = (utl::_RefCountBase *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v245 = 0;
        goto LABEL_418;
      }
      v126 = v231;
      if ( (_DWORD)v269 == 2 )
      {
        DestinationFileNameInformation = UnionFs::UfsPathName::ReplacePathPrefix(
                                           (UnionFs::UfsPathName *)v231,
                                           v270[0],
                                           v270[1],
                                           v8);
        if ( DestinationFileNameInformation < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)DestinationFileNameInformation,
            (int)v8,
            (struct UnionFs::StackEventTracer *)0x60D000B01E3LL,
            (unsigned __int64)"UnionFs::PreRename",
            "PUSH: Replacing substring",
            (const char *)v8);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v266);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
LABEL_342:
          if ( v73 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
          wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
          if ( v241[1] )
            utl::_RefCountBase::_DecStrong(v241[1]);
          if ( v236[1] )
            utl::_RefCountBase::_DecStrong(v236[1]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
          if ( v34 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
          v127 = v228;
          v228 = 0;
          if ( v127 )
            FltReleaseFileNameInformation(v127);
          v10 = FileNameInformation;
          FileNameInformation = 0;
          goto LABEL_4;
        }
      }
      utl::make_unique<UnionFs::FindAndStatResults,,0>(v253);
      v110 = (utl::_RefCountBase *)v253[0];
      if ( !v253[0] )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x40B000B01EDLL,
          (unsigned __int64)"UnionFs::PreRename",
          "ORIGIN: Allocating findAndStatResults",
          (const char *)v8);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v266);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
LABEL_355:
        if ( v73 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
        wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
        if ( v241[1] )
          utl::_RefCountBase::_DecStrong(v241[1]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
        if ( v34 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
        v128 = v228;
        v228 = 0;
        if ( v128 )
          FltReleaseFileNameInformation(v128);
        v52 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_737;
      }
      NameOptionsb = v8;
      *((_QWORD *)v253[0] + 12) = &v234;
      v129 = *v126;
      *(struct _UNICODE_STRING *)v251 = *v35;
      UnicodeString = v129;
      v130 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v274[0], &UnicodeString, v251, 1, v110);
      v64 = v130;
      if ( v130 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v130,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x354000B01FALL,
          (unsigned __int64)"UnionFs::PreRename",
          "PUSH: Failed to lookup entry",
          (const char *)v8);
        if ( v110 )
        {
          v131 = (utl::_RefCountBase *)*((_QWORD *)v110 + 11);
          if ( v131 )
            utl::_RefCountBase::_DecStrong(v131);
          ExFreePoolWithTag(v110, 0);
        }
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v266);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
        if ( v73 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
        wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
        if ( v241[1] )
          utl::_RefCountBase::_DecStrong(v241[1]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
        if ( v34 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
        v132 = v228;
        v228 = 0;
        if ( v132 )
          FltReleaseFileNameInformation(v132);
        v70 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_152;
      }
      v133 = (void *)*((_QWORD *)v110 + 10);
      v134 = *(struct _UNICODE_STRING *)((char *)v110 + 24);
      v135 = *(_WORD *)v110;
      v271[0] = *(struct _UNICODE_STRING *)((char *)v110 + 8);
      v136 = *(struct _UNICODE_STRING *)((char *)v110 + 40);
      v253[0] = v133;
      v137 = (volatile signed __int32 *)*((_QWORD *)v110 + 11);
      v271[1] = v134;
      v271[2] = v136;
      *(_QWORD *)&v271[4].Length = *((_QWORD *)v110 + 9);
      LOWORD(v240) = v135;
      v249 = (utl::_RefCountBase *)v137;
      v271[3] = *(struct _UNICODE_STRING *)((char *)v110 + 56);
      if ( v137 )
        _InterlockedIncrement(v137 + 2);
      if ( (_DWORD)v254 == -1073741766 && v135 == 2 || (_DWORD)v254 == -1073741772 && v135 != 1 )
        IsDirectory[2] = 0;
      if ( !v110 )
      {
        LOWORD(v110) = (_WORD)v240;
        v124 = 0;
        v101 = (utl::_RefCountBase *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v245 = 0;
LABEL_399:
        if ( (_WORD)v110 != 1 )
        {
LABEL_417:
          v110 = v249;
LABEL_418:
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v266);
          v143 = IsDirectory[0];
          v112 = 0;
          if ( !IsDirectory[0] )
            goto LABEL_419;
          goto LABEL_445;
        }
LABEL_400:
        IsDirectory[0] = 1;
        if ( v124 )
        {
          v139 = (volatile signed __int32 *)*((_QWORD *)v124 + 5);
          v140 = *((_QWORD *)v124 + 4);
          v240 = (utl::_RefCountBase *)v139;
          if ( v139 )
            _InterlockedIncrement(v139 + 2);
          v141 = **(struct _FLT_INSTANCE ***)(v140 + 8);
          FsFltWil::ReferenceObObject<_FILE_OBJECT>(&FileObject, v124 + 64);
          DestinationFileNameInformation = FltIsDirectory(FileObject, v141, &IsDirectory[3]);
          if ( FileObject )
            ObfDereferenceObject(FileObject);
          if ( v240 )
            utl::_RefCountBase::_DecStrong(v240);
          if ( DestinationFileNameInformation < 0 )
          {
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)(unsigned int)DestinationFileNameInformation,
              (int)v8,
              (struct UnionFs::StackEventTracer *)0xEC000B0220LL,
              (unsigned __int64)"UnionFs::PreRename",
              "API: FltIsDirectory(BFO)",
              (const char *)NameOptionsb);
            UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v266);
            utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
            if ( v249 )
              utl::_RefCountBase::_DecStrong(v249);
            utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
            if ( Context )
            {
              ExReleaseResourceLite((PERESOURCE)Context);
              KeLeaveCriticalRegion();
            }
            if ( !v101 )
              goto LABEL_342;
            v142 = v101;
            goto LABEL_414;
          }
          LOBYTE(v239) = (IsDirectory[3] != 0 ? 4 : 0) | v239 & 0xFB;
        }
        else
        {
          LOBYTE(v239) = v239 & 0xFB | (LODWORD(v271[3].Buffer) >> 2) & 4;
        }
        goto LABEL_417;
      }
      v138 = (utl::_RefCountBase *)*((_QWORD *)v110 + 11);
      LOBYTE(FileObject) = 0;
      if ( v138 )
        utl::_RefCountBase::_DecStrong(v138);
      ExFreePoolWithTag(v110, 0);
      v125 = (char)FileObject;
      LOWORD(v110) = (_WORD)v240;
      v124 = 0;
      v101 = (utl::_RefCountBase *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v245 = 0;
    }
    if ( v124 && !v125 && *((_WORD *)v124 + 80) != 3 && *((_WORD *)v124 + 80) != 4 )
      goto LABEL_400;
    goto LABEL_399;
  }
  IsDirectory[2] = 0;
  v245 = 0;
  LOBYTE(v239) = v42 & 0xFB | (v278[14] >> 2) & 4;
  v143 = 0;
  v101 = (utl::_RefCountBase *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
LABEL_445:
  if ( !IsDirectory[1] )
  {
    if ( (unsigned int)dword_14009E178 > 4
      && (qword_14009E188 & 0x20) != 0
      && (qword_14009E190 & 0x20) == qword_14009E190 )
    {
      LODWORD(FileObject) = 565;
      v253[0] = "Denying attempted superseding rename without flag.";
      v243 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
      v235 = (UnionFs::StackEventTracer *)"UnionFs::PreRename";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        qword_14009E190,
        (unsigned int)byte_140096A11,
        0,
        (_DWORD)v111,
        (__int64)v253,
        (__int64)&v235,
        (__int64)&v243,
        (__int64)&FileObject);
    }
    v147 = (int)v8;
    v148 = "ORIGIN: superseding rename";
    v149 = -1073741771;
    v150 = 0x463000B0239LL;
    goto LABEL_451;
  }
LABEL_419:
  IsDirectory[1] = 0;
  if ( IsDirectory[2] )
  {
    if ( v143 && (*((_DWORD *)v274[0] + 6) & 0x80u) != 0 )
    {
      IsDirectory[2] = 0;
      if ( v245 )
      {
        IsFileCowable = UnionFs::Utils::IsFileCowable((UnionFs::Utils *)&IsDirectory[2], v245, v8, v111);
        LODWORD(FileObject) = IsFileCowable;
        if ( IsFileCowable < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)IsFileCowable,
            (int)v8,
            (struct UnionFs::StackEventTracer *)0x78A000B0249LL,
            (unsigned __int64)"UnionFs::PreRename",
            "PUSH: Checking immutability",
            (const char *)NameOptionsb);
LABEL_425:
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
          if ( v110 )
            utl::_RefCountBase::_DecStrong(v110);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
          if ( Context )
          {
            ExReleaseResourceLite((PERESOURCE)Context);
            KeLeaveCriticalRegion();
          }
          if ( v101 )
            utl::_RefCountBase::_DecStrong(v101);
          if ( v73 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
          wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
          if ( v241[1] )
            utl::_RefCountBase::_DecStrong(v241[1]);
          if ( v236[1] )
            utl::_RefCountBase::_DecStrong(v236[1]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
          if ( v34 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
          v145 = v228;
          v228 = 0;
          if ( v145 )
            FltReleaseFileNameInformation(v145);
          v146 = FileNameInformation;
          FileNameInformation = 0;
          if ( v146 )
            FltReleaseFileNameInformation(v146);
          return (unsigned int)FileObject;
        }
        v153 = IsDirectory[2];
      }
      else if ( ((__int64)v271[3].Buffer & 0x800000) != 0 || (v153 = 0, ((__int64)v271[3].Buffer & 0x10) != 0) )
      {
        v153 = 1;
      }
      if ( !v153 )
      {
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x400000000000LL) != 0
          && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
        {
          v243 = (PVOID)1;
          v235 = (UnionFs::StackEventTracer *)0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)&word_140096ACE,
            v112,
            (unsigned int)&v235,
            (__int64)&v243);
        }
        v147 = (int)v8;
        v148 = "ORIGIN: Rejecting COW for superseding rename with immutable destination";
        v149 = -1073741790;
        v150 = 0x78B000B025BLL;
LABEL_451:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)v149,
          v147,
          (struct UnionFs::StackEventTracer *)v150,
          (unsigned __int64)"UnionFs::PreRename",
          v148,
          (const char *)NameOptionsb);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
        if ( v110 )
          utl::_RefCountBase::_DecStrong(v110);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
        if ( Context )
        {
          ExReleaseResourceLite((PERESOURCE)Context);
          KeLeaveCriticalRegion();
        }
        if ( v101 )
          utl::_RefCountBase::_DecStrong(v101);
        if ( v73 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
        wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
        if ( v241[1] )
          utl::_RefCountBase::_DecStrong(v241[1]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
        if ( v34 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
        v151 = v228;
        v228 = 0;
        if ( v151 )
          FltReleaseFileNameInformation(v151);
        v152 = FileNameInformation;
        FileNameInformation = 0;
        if ( v152 )
          FltReleaseFileNameInformation(v152);
        return v149;
      }
    }
    UnicodeString = 0;
    *(struct _UNICODE_STRING *)v251 = *v35;
    RemainingPath = UnionFs::Utils::GetRemainingPath(v228, v251, &UnicodeString, v8);
    LODWORD(FileObject) = RemainingPath;
    if ( RemainingPath < 0 )
    {
      v156 = "PUSH: Getting relative path";
      v157 = 0x350000B0267LL;
LABEL_482:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)RemainingPath,
        (int)v8,
        (struct UnionFs::StackEventTracer *)v157,
        (unsigned __int64)"UnionFs::PreRename",
        v156,
        (const char *)NameOptionsb);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v158);
      goto LABEL_425;
    }
    v159 = (int)v245;
    if ( v245 )
    {
      v160 = (int)v228;
      v251[0] = v274[0];
      v251[1] = v274[1];
      if ( v274[1] )
        _InterlockedIncrement((volatile signed __int32 *)v274[1] + 2);
      RemainingPath = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(
                        v159,
                        (unsigned int)v251,
                        v160,
                        3,
                        (_DWORD)v8);
      LODWORD(FileObject) = RemainingPath;
      if ( RemainingPath < 0 )
      {
        v156 = "PUSH: Converting cache entry to soft tombstone";
        v157 = 0x46E000B0274LL;
        goto LABEL_482;
      }
      v242 = 0;
      if ( Context )
      {
        ExReleaseResourceLite((PERESOURCE)Context);
        KeLeaveCriticalRegion();
      }
      if ( v101 )
        _InterlockedIncrement((volatile signed __int32 *)v101 + 2);
      v161 = v241[1];
      v241[0] = (utl::_RefCountBase *)v245;
      v241[1] = v101;
      if ( v161 )
        utl::_RefCountBase::_DecStrong(v161);
      IsDirectory[1] = 1;
    }
    if ( (_DWORD)v254 == -1073741766 )
    {
      Context = 0;
      v162 = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(
               (_DWORD)v259,
               v252->FileObject,
               (_DWORD)v35,
               (unsigned int)&UnicodeString,
               (__int64)v244,
               (__int64)&Context,
               (__int64)v8);
      if ( v162 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v162,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x351000B028ELL,
          (unsigned __int64)"UnionFs::PreRename",
          "PUSH: Creating handle context",
          NameOptionsc);
        if ( Context )
          FltReleaseContext(Context);
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v163);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
        if ( !v110 )
          goto LABEL_502;
        v164 = v110;
LABEL_501:
        utl::_RefCountBase::_DecStrong(v164);
LABEL_502:
        p_Context = (PVOID *)&v231;
        goto LABEL_503;
      }
      v169 = v245;
      v170 = v274[0];
      if ( v245 )
      {
        v171 = *((_QWORD *)v245 + 5);
        v238 |= 2u;
        v172 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v245 + 4);
        FileObject = (PFILE_OBJECT)v171;
        if ( v171 )
          _InterlockedIncrement((volatile signed __int32 *)(v171 + 8));
      }
      else
      {
        v172 = (const struct UnionFs::UfsLayerCtx *)v253[0];
        FileObject = v265;
      }
      v173 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
               v170,
               v244,
               v252,
               v228,
               (const struct UnionFs::UfsPathName *)v231,
               (const struct UnionFs::UfsStreamHandleCtx *)Context,
               v172,
               v8,
               0);
      LODWORD(v254) = v173;
      if ( (v238 & 2) != 0 )
      {
        v238 &= ~2u;
        if ( FileObject )
        {
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)FileObject);
          v173 = (int)v254;
        }
      }
      if ( v173 < 0 )
      {
        if ( v173 == -1073741766 || v173 == -1073741772 )
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("Path should exist");
          v173 = (int)v254;
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v173,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x3E7000B029DLL,
          (unsigned __int64)"UnionFs::PreRename",
          "PUSH: Preparing for COW",
          (const char *)NameOptionsb);
        if ( Context )
          FltReleaseContext(Context);
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v174);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
        if ( v110 )
          utl::_RefCountBase::_DecStrong(v110);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
        if ( v101 )
          utl::_RefCountBase::_DecStrong(v101);
        if ( v73 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
        wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
        if ( v241[1] )
          utl::_RefCountBase::_DecStrong(v241[1]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
        if ( v34 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
        v175 = v228;
        v228 = 0;
        if ( v175 )
          FltReleaseFileNameInformation(v175);
        v176 = FileNameInformation;
        FileNameInformation = 0;
        if ( v176 )
          FltReleaseFileNameInformation(v176);
        return (unsigned int)v254;
      }
      if ( Context )
        FltReleaseContext(Context);
    }
    else
    {
      v169 = v245;
    }
    if ( IsDirectory[0] )
    {
      *(utl::_RefCountBase **)v260 = v274[0];
      v263 = 0;
      v264 = 22;
      v261 = 0;
      *(_OWORD *)v262 = 0;
      utl::shared_ptr<UnionFs::UfsPathTree>::operator=((char *)&v261 + 8, v250);
      if ( IsDirectory[1] )
        v264 |= 0x20u;
      UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)v271, &v228->Name, v228->Volume.Length);
      v177 = v252->Instance;
      if ( v169 )
        v178 = *((_QWORD *)v169 + 6);
      else
        LODWORD(v178) = (_DWORD)v234;
      if ( v169 )
      {
        v253[0] = *((PVOID *)v169 + 4);
        v179 = (volatile signed __int32 *)*((_QWORD *)v169 + 5);
        v238 = 4;
        Context = (PVOID)v179;
        if ( v179 )
          _InterlockedIncrement(v179 + 2);
      }
      else
      {
        Context = v265;
      }
      v180 = UnionFs::Utils::CopyItem(
               (_DWORD)v244,
               v253[0],
               v178,
               (_DWORD)v177,
               v271,
               (__int64)v260,
               (struct _FILE_OBJECT *)v8,
               0);
      v184 = v180;
      LODWORD(v240) = v180;
      if ( (v238 & 4) != 0 && Context )
      {
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context);
        v184 = (unsigned int)v240;
      }
      if ( (v184 & 0x80000000) != 0LL )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)v184,
          (int)v8,
          (struct UnionFs::StackEventTracer *)0x3DB000B02C0LL,
          (unsigned __int64)"UnionFs::PreRename",
          "PUSH: Performing COW",
          (const char *)NameOptionsb);
        if ( !LOBYTE(v271[1].Length) )
          v271[0] = 0;
        FsFltWil::Details::FreeUnicodeString(v271, v185);
        if ( v262[0] )
          utl::_RefCountBase::_DecStrong(v262[0]);
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v186);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
        if ( v110 )
          utl::_RefCountBase::_DecStrong(v110);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
        if ( v101 )
          utl::_RefCountBase::_DecStrong(v101);
        if ( v73 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
        wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
        if ( v241[1] )
          utl::_RefCountBase::_DecStrong(v241[1]);
        if ( v236[1] )
          utl::_RefCountBase::_DecStrong(v236[1]);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
        goto LABEL_250;
      }
      if ( v169 && (v264 & 0x20) == 0 )
      {
        v187 = v101;
        v101 = 0;
        v245 = 0;
        v250[0] = 0;
        v250[1] = 0;
        if ( v187 )
          utl::_RefCountBase::_DecStrong(v187);
        v188 = v241[1];
        v241[0] = 0;
        v241[1] = 0;
        if ( v188 )
          utl::_RefCountBase::_DecStrong(v188);
        si128 = _mm_load_si128((const __m128i *)v250);
      }
      LOBYTE(v181) = v239;
      if ( (v239 & 0xC) == 0xC )
      {
        if ( (v239 & 2) == 0 )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x20) != 0
            && (qword_14009E190 & 0x20) == qword_14009E190 )
          {
            LODWORD(FileObject) = 726;
            v253[0] = "Denying superseding POSIX rename of directory when source is a file.";
            v243 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
            v235 = (UnionFs::StackEventTracer *)"UnionFs::PreRename";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              qword_14009E190,
              (unsigned int)word_140096B1A,
              v182,
              v183,
              (__int64)v253,
              (__int64)&v235,
              (__int64)&v243,
              (__int64)&FileObject);
          }
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000BALL,
            (int)v8,
            (struct UnionFs::StackEventTracer *)0x4DC000B02DALL,
            (unsigned __int64)"UnionFs::PreRename",
            "ORIGIN: POSIX superseding rename file -> directory",
            (const char *)NameOptionsb);
          if ( !LOBYTE(v271[1].Length) )
            v271[0] = 0;
          FsFltWil::Details::FreeUnicodeString(v271, v189);
          if ( v262[0] )
            utl::_RefCountBase::_DecStrong(v262[0]);
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v190);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
          if ( v110 )
            utl::_RefCountBase::_DecStrong(v110);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
          if ( v101 )
            utl::_RefCountBase::_DecStrong(v101);
          if ( v73 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
          wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
          if ( v241[1] )
            utl::_RefCountBase::_DecStrong(v241[1]);
          if ( v236[1] )
            utl::_RefCountBase::_DecStrong(v236[1]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
          if ( v34 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
          v191 = v228;
          v228 = 0;
          if ( v191 )
            FltReleaseFileNameInformation(v191);
          v192 = FileNameInformation;
          FileNameInformation = 0;
          if ( v192 )
            FltReleaseFileNameInformation(v192);
          return 3221225658LL;
        }
        v193 = v274[0];
        IsDirectory[0] = 0;
        v194 = v252->FileObject;
        v195 = (v194->Flags & 0x20000) != 0;
        v196 = (const struct _EJOB *)IoGetSilo(v194);
        v197 = v235;
        DestinationFileNameInformation = UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory(
                                           v193,
                                           v244,
                                           v228,
                                           v196,
                                           v195,
                                           (bool *)IsDirectory,
                                           v235);
        if ( DestinationFileNameInformation < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)DestinationFileNameInformation,
            (int)v197,
            (struct UnionFs::StackEventTracer *)0x54000B02EBLL,
            (unsigned __int64)"UnionFs::PreRename",
            "PUSH: Checking POSIX superseding rename target",
            (const char *)NameOptionsb);
LABEL_617:
          if ( !LOBYTE(v271[1].Length) )
            v271[0] = 0;
          FsFltWil::Details::FreeUnicodeString(v271, v200);
          if ( v262[0] )
            utl::_RefCountBase::_DecStrong(v262[0]);
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v201);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
          if ( v249 )
            utl::_RefCountBase::_DecStrong(v249);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
          if ( v101 )
            utl::_RefCountBase::_DecStrong(v101);
          if ( v73 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
          wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
          if ( v241[1] )
            utl::_RefCountBase::_DecStrong(v241[1]);
          if ( v236[1] )
            utl::_RefCountBase::_DecStrong(v236[1]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
          goto LABEL_204;
        }
        if ( !IsDirectory[0] )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x20) != 0
            && (qword_14009E190 & 0x20) == qword_14009E190 )
          {
            LODWORD(FileObject) = 752;
            v243 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
            v235 = (UnionFs::StackEventTracer *)"UnionFs::PreRename";
            v253[0] = "Denying superseding POSIX rename of non-empty directory.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              qword_14009E190,
              (unsigned int)&byte_140096A4F,
              v198,
              v199,
              (__int64)v253,
              (__int64)&v235,
              (__int64)&v243,
              (__int64)&FileObject);
          }
          DestinationFileNameInformation = -1073741567;
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000101LL,
            (int)v197,
            (struct UnionFs::StackEventTracer *)0x4DD000B02F4LL,
            (unsigned __int64)"UnionFs::PreRename",
            "ORIGIN: POSIX superseding rename non-empty directory",
            (const char *)NameOptionsb);
          goto LABEL_617;
        }
        v8 = v197;
      }
      if ( !LOBYTE(v271[1].Length) )
        v271[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v271, v181);
      if ( v262[0] )
        utl::_RefCountBase::_DecStrong(v262[0]);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v155);
  }
  v102 = (utl::_RefCountBase *)v245;
  if ( (v239 & 2) == 0 || (v239 & 1) == 0 )
    goto LABEL_704;
  IsDirectory[0] = 1;
  if ( !v245 )
  {
    DestinationFileNameInformation = UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(v250, v8, 0);
    if ( DestinationFileNameInformation < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)DestinationFileNameInformation,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x364000B0309LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Allocating path cache payload",
        (const char *)NameOptionsb);
LABEL_649:
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
      if ( v249 )
        utl::_RefCountBase::_DecStrong(v249);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
      v142 = v250[1];
      if ( !v250[1] )
        goto LABEL_342;
LABEL_414:
      utl::_RefCountBase::_DecStrong(v142);
      goto LABEL_342;
    }
    v101 = v250[1];
    v102 = v250[0];
    si128 = _mm_load_si128((const __m128i *)v250);
    IsDirectory[0] = 0;
  }
  if ( !IsDirectory[1] )
  {
    v202 = (int)v228;
    v251[0] = v274[0];
    v251[1] = v274[1];
    if ( v274[1] )
      _InterlockedIncrement((volatile signed __int32 *)v274[1] + 2);
    v203 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone((_DWORD)v102, (unsigned int)v251, v202, 4, (_DWORD)v8);
    v162 = v203;
    if ( v203 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v203,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x3C6000B0318LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Converting cache entry to soft tombstone",
        (const char *)NameOptionsb);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
      v164 = v249;
      if ( !v249 )
        goto LABEL_502;
      goto LABEL_501;
    }
    utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v241, v250);
  }
  if ( IsDirectory[0] )
  {
LABEL_695:
    if ( !UnionFs::UfsUnionCtx::ReserveSpaceForTombstone(v274[0]) )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)0xC000009ALL,
        (int)v8,
        (struct UnionFs::StackEventTracer *)0x3FE000B0387LL,
        (unsigned __int64)"UnionFs::PreRename",
        "PUSH: Reserving tombstone space",
        (const char *)NameOptionsb);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
      if ( v249 )
        utl::_RefCountBase::_DecStrong(v249);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
      if ( v101 )
        utl::_RefCountBase::_DecStrong(v101);
      goto LABEL_355;
    }
LABEL_704:
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
    if ( v249 )
      utl::_RefCountBase::_DecStrong(v249);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
    goto LABEL_707;
  }
  *(_QWORD *)v260 = 0;
  v262[0] = 0;
  v262[1] = 0;
  *(__m128i *)v251 = si128;
  v261 = 0;
  if ( v101 )
    _InterlockedIncrement((volatile signed __int32 *)v101 + 2);
  v204 = v251[0];
  while ( 1 )
  {
    if ( *((_DWORD *)v274[0] + 7) == 2 )
      v205 = *(_QWORD *)(*((_QWORD *)v274[0] + 4) + 16LL);
    else
      v205 = *((_QWORD *)UnionFs::g_FilterState + 10);
    DestinationFileNameInformation = UnionFs::UfsPathCache::InsertEntry(
                                       v205,
                                       (int)v252->Instance,
                                       (int)v228,
                                       (int)v111,
                                       (__int64)v250,
                                       v260,
                                       (int)v8);
    if ( DestinationFileNameInformation < 0 )
    {
      v212 = "PUSH: Inserting path cache payload";
      v213 = 0x365000B0340LL;
      goto LABEL_701;
    }
    v102 = v250[0];
    if ( *(_DWORD *)v260 != 2 )
      goto LABEL_692;
    if ( *((_WORD *)v250[0] + 80) != 1 )
      break;
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x60) != 0
      && (qword_14009E190 & 0x60) == qword_14009E190 )
    {
      p_Name = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
      v245 = (bool *)"onecore\\base\\fs\\unionfs\\sys\\info.cpp";
      v240 = (utl::_RefCountBase *)"UnionFs::PreRename";
      v210 = v228->Name.Buffer == 0;
      v253[0] = v204;
      if ( !v210 )
        p_Name = &v228->Name;
      Context = v250[0];
      v235 = (UnionFs::StackEventTracer *)p_Name;
      v254 = (UnionFs *)"Found existing Soft tombstone";
      LODWORD(FileObject) = 844;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (_DWORD)p_Name,
        (unsigned int)word_140096CC2,
        v207,
        v208,
        (__int64)&v254,
        (__int64)&v240,
        (__int64)&v245,
        (__int64)&FileObject,
        (__int64)&Context,
        (__int64)v253,
        (__int64)&v235);
    }
    v211 = (FsFltWil::Details *)v261;
    *(_QWORD *)&v261 = 0;
    if ( v211 )
      FsFltWil::Details::ReleaseResource(v211, v206);
    DestinationFileNameInformation = UnionFs::UfsPathCachePayload::WaitForSoftTombstone(v102, 1, v8, v244);
    if ( DestinationFileNameInformation < 0 )
    {
      v212 = "PUSH: WaitForSoftTombstone";
      v213 = 0x38B000B0357LL;
LABEL_701:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)DestinationFileNameInformation,
        (int)v8,
        (struct UnionFs::StackEventTracer *)v213,
        (unsigned __int64)"UnionFs::PreRename",
        v212,
        (const char *)NameOptionsb);
      if ( v251[1] )
        utl::_RefCountBase::_DecStrong(v251[1]);
      UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v260);
      goto LABEL_649;
    }
    utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v250, v251);
  }
  v214 = (int)v228;
  UnicodeString = *(struct _UNICODE_STRING *)v274;
  if ( v274[1] )
    _InterlockedIncrement((volatile signed __int32 *)v274[1] + 2);
  v215 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(
           (_DWORD)v102,
           (unsigned int)&UnicodeString,
           v214,
           5,
           (_DWORD)v8);
  v162 = v215;
  if ( v215 >= 0 )
  {
    UnionFs::UfsPathCachePayload::RevertSoftTombstone(v241[0], v8);
    utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v241, v250);
LABEL_692:
    if ( v251[1] )
      utl::_RefCountBase::_DecStrong(v251[1]);
    UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v260);
    v101 = v250[1];
    goto LABEL_695;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v215,
    (int)v8,
    (struct UnionFs::StackEventTracer *)0x12B000B037ALL,
    (unsigned __int64)"UnionFs::PreRename",
    "PUSH: Converting cache entry to soft tombstone",
    (const char *)NameOptionsb);
  if ( v251[1] )
    utl::_RefCountBase::_DecStrong(v251[1]);
  UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v260);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v234);
  if ( v249 )
    utl::_RefCountBase::_DecStrong(v249);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v231);
  wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v242);
  v166 = v250[1];
  if ( v250[1] )
LABEL_505:
    utl::_RefCountBase::_DecStrong(v166);
LABEL_506:
  if ( v73 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v73);
  wil::details::lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___::_lambda_call__lambda_4b0464f5f93cb108c7aa51a4c81814fb___(&v246);
  if ( v241[1] )
    utl::_RefCountBase::_DecStrong(v241[1]);
  if ( v236[1] )
    utl::_RefCountBase::_DecStrong(v236[1]);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v274);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v276);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v233);
  if ( v34 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
  UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v255);
  v167 = v228;
  v228 = 0;
  if ( v167 )
    FltReleaseFileNameInformation(v167);
  v168 = FileNameInformation;
  FileNameInformation = 0;
  if ( v168 )
    FltReleaseFileNameInformation(v168);
  return (unsigned int)v162;
}

```

## disassembly

```asm
0x14002e3c8  mov     rax, rsp
0x14002e3cb  push    rbp
0x14002e3cc  push    rbx
0x14002e3cd  push    rsi
0x14002e3ce  push    rdi
0x14002e3cf  push    r12
0x14002e3d1  push    r13
0x14002e3d3  push    r14
0x14002e3d5  push    r15
0x14002e3d7  lea     rbp, [rax-5D8h]
0x14002e3de  sub     rsp, 698h
0x14002e3e5  movaps  xmmword ptr [rax-58h], xmm6
0x14002e3e9  mov     rax, cs:__security_cookie
0x14002e3f0  xor     rax, rsp
0x14002e3f3  mov     qword ptr [rbp+5D0h+var_58], rax
0x14002e3fa  mov     r14, [rbp+5D0h+arg_20]
0x14002e401  xor     r15d, r15d
0x14002e404  mov     [r8], r15
0x14002e407  mov     r13, rdx
0x14002e40a  mov     [rbp+5D0h+var_4F0], r8
0x14002e411  mov     rsi, rcx
0x14002e414  mov     [rbp+5D0h+var_580], rdx
0x14002e418  lea     r8, [rsp+6D0h+FileNameInformation]
0x14002e41d  mov     [rbp+5D0h+var_5E8], rcx
0x14002e421  mov     edx, 1000401h
0x14002e426  mov     [rbp+5D0h+var_5D0], rcx
0x14002e42a  mov     rdi, r9
0x14002e42d  lea     rcx, [rbp+5D0h+var_5D0]
0x14002e431  mov     [rbp+5D0h+var_638], r9
0x14002e435  mov     [rbp+5D0h+var_618], r15d
0x14002e439  mov     [rsp+6D0h+FileNameInformation], r15
0x14002e43e  mov     [rbp+5D0h+var_5C8], r15
0x14002e442  mov     [rbp+5D0h+var_5C0], r15
0x14002e446  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14002e44b  mov     ebx, eax
0x14002e44d  test    eax, eax
0x14002e44f  jns     short loc_14002E49A
0x14002e451  lea     rax, aPushGettingSou_0; "PUSH: Getting source file name informat"...
0x14002e458  mov     r8, 360000B0031h; struct UnionFs::StackEventTracer *
0x14002e462  lea     r9, aUnionfsPrerena; "UnionFs::PreRename"
0x14002e469  mov     qword ptr [rsp+6D0h+FileNameLength], rax; char *
0x14002e46e  mov     rdx, rdi; int
0x14002e471  mov     ecx, ebx; this
0x14002e473  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002e478  mov     rcx, [rsp+6D0h+FileNameInformation]; FileNameInformation
0x14002e47d  mov     [rsp+6D0h+FileNameInformation], r15
0x14002e482  test    rcx, rcx
0x14002e485  jz      short loc_14002E493
0x14002e487  call    cs:__imp_FltReleaseFileNameInformation
0x14002e48e  nop     dword ptr [rax+rax+00h]
0x14002e493  mov     eax, ebx
0x14002e495  jmp     loc_14003198A
0x14002e49a  mov     rax, [rsi+10h]
0x14002e49e  mov     esi, 1
0x14002e4a3  mov     rdx, [r13+20h]; FileObject
0x14002e4a7  mov     [rsp+6D0h+var_670], r15
0x14002e4ac  mov     [rbp+5D0h+var_5C8], r15
0x14002e4b0  mov     rcx, [rax+38h]
0x14002e4b4  lea     rax, [rsp+6D0h+var_670]
0x14002e4b9  mov     [rbp+5D0h+var_5D0], rax
0x14002e4bd  lea     rax, [rbp+5D0h+var_5C8]
0x14002e4c1  mov     [rsp+6D0h+RetFileNameInformation], rax; RetFileNameInformation
0x14002e4c6  mov     [rbp+5D0h+var_578], rcx
0x14002e4ca  mov     eax, [rcx+10h]
0x14002e4cd  lea     r9, [rcx+14h]; FileName
0x14002e4d1  mov     r8, [rcx+8]; RootDirectory
0x14002e4d5  mov     rcx, [r13+18h]; Instance
0x14002e4d9  mov     [rsp+6D0h+NameOptions], 1000101h; char *
0x14002e4e1  mov     byte ptr [rbp+5D0h+var_5C0], sil
0x14002e4e5  mov     [rsp+6D0h+FileNameLength], eax; FileNameLength
0x14002e4e9  call    cs:__imp_FltGetDestinationFileNameInformation
0x14002e4f0  nop     dword ptr [rax+rax+00h]
0x14002e4f5  mov     ebx, eax
0x14002e4f7  cmp     byte ptr [rbp+5D0h+var_5C0], r15b
0x14002e4fb  jz      short loc_14002E51C
0x14002e4fd  mov     r8, [rbp+5D0h+var_5D0]
0x14002e501  mov     rdx, [rbp+5D0h+var_5C8]
0x14002e505  mov     rcx, [r8]; FileNameInformation
0x14002e508  mov     [r8], rdx
0x14002e50b  test    rcx, rcx
0x14002e50e  jz      short loc_14002E51C
0x14002e510  call    cs:__imp_FltReleaseFileNameInformation
0x14002e517  nop     dword ptr [rax+rax+00h]
0x14002e51c  test    ebx, ebx
0x14002e51e  jns     short loc_14002E56B
0x14002e520  lea     rax, aApiGettingDest; "API: Getting destination file name"
0x14002e527  mov     r8, 361000B0042h; struct UnionFs::StackEventTracer *
0x14002e531  lea     r9, aUnionfsPrerena; "UnionFs::PreRename"
0x14002e538  mov     qword ptr [rsp+6D0h+FileNameLength], rax; char *
0x14002e53d  mov     rdx, rdi; int
0x14002e540  mov     ecx, ebx; this
0x14002e542  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002e547  mov     rcx, [rsp+6D0h+var_670]; FileNameInformation
0x14002e54c  mov     [rsp+6D0h+var_670], r15
0x14002e551  test    rcx, rcx
0x14002e554  jz      loc_14002E478
0x14002e55a  call    cs:__imp_FltReleaseFileNameInformation
0x14002e561  nop     dword ptr [rax+rax+00h]
0x14002e566  jmp     loc_14002E478
0x14002e56b  mov     rdx, [rsp+6D0h+var_670]
0x14002e570  xor     r8d, r8d; CaseInSensitive
0x14002e573  mov     rcx, [rsp+6D0h+FileNameInformation]
0x14002e578  add     rdx, 8; String2
0x14002e57c  add     rcx, 8; String1
0x14002e580  call    cs:__imp_RtlCompareUnicodeString
0x14002e587  nop     dword ptr [rax+rax+00h]
0x14002e58c  test    eax, eax
0x14002e58e  jnz     loc_14002E63E
0x14002e594  mov     eax, cs:dword_14009E178
0x14002e59a  cmp     eax, 5
0x14002e59d  jbe     short loc_14002E614
0x14002e59f  mov     rcx, cs:qword_14009E190
0x14002e5a6  mov     rax, cs:qword_14009E188
0x14002e5ad  test    al, 60h
0x14002e5af  jz      short loc_14002E614
0x14002e5b1  mov     rax, rcx
0x14002e5b4  and     eax, 60h
0x14002e5b7  cmp     rax, rcx
0x14002e5ba  jnz     short loc_14002E614
0x14002e5bc  lea     rax, aSourceAndDesti; "Source and destination same"
0x14002e5c3  mov     dword ptr [rbp+5D0h+var_610], 4Ch ; 'L'
0x14002e5ca  mov     [rbp+5D0h+var_578], rax
0x14002e5ce  lea     r12, aOnecoreBaseFsU_13; "onecore\\base\\fs\\unionfs\\sys\\info.c"...
0x14002e5d5  lea     rax, [rbp+5D0h+var_610]
0x14002e5d9  mov     [rbp+5D0h+var_5F0], r12
0x14002e5dd  mov     [rsp+6D0h+var_698], rax
0x14002e5e2  lea     r14, aUnionfsPrerena; "UnionFs::PreRename"
0x14002e5e9  lea     rax, [rbp+5D0h+var_5F0]
0x14002e5ed  mov     [rbp+5D0h+var_638], r14
0x14002e5f1  mov     [rsp+6D0h+RetFileNameInformation], rax
0x14002e5f6  lea     rdx, byte_140096A8D
0x14002e5fd  lea     rax, [rbp+5D0h+var_638]
0x14002e601  mov     qword ptr [rsp+6D0h+NameOptions], rax
0x14002e606  lea     rax, [rbp+5D0h+var_578]
0x14002e60a  mov     qword ptr [rsp+6D0h+FileNameLength], rax
0x14002e60f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14002e614  mov     rcx, [rsp+6D0h+var_670]; FileNameInformation
0x14002e619  mov     [rsp+6D0h+var_670], r15
0x14002e61e  test    rcx, rcx
0x14002e621  jz      short loc_14002E62F
0x14002e623  call    cs:__imp_FltReleaseFileNameInformation
0x14002e62a  nop     dword ptr [rax+rax+00h]
0x14002e62f  mov     rcx, [rsp+6D0h+FileNameInformation]
0x14002e634  mov     [rsp+6D0h+FileNameInformation], r15
0x14002e639  jmp     loc_140031977
0x14002e63e  mov     rdx, [r13+20h]
0x14002e642  lea     r8, [rbp+5D0h+var_530]
0x14002e649  mov     rcx, [r13+18h]
0x14002e64d  mov     r9, rdi
0x14002e650  mov     [rbp+5D0h+var_530], r15
0x14002e657  mov     qword ptr [rsp+6D0h+FileNameLength], r15
0x14002e65c  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x14002e661  mov     ebx, eax
0x14002e663  test    eax, eax
0x14002e665  jns     short loc_14002E693
0x14002e667  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x14002e66e  mov     r8, 337000B0059h; struct UnionFs::StackEventTracer *
0x14002e678  lea     r9, aUnionfsPrerena; "UnionFs::PreRename"
0x14002e67f  mov     qword ptr [rsp+6D0h+FileNameLength], rax; char *
0x14002e684  mov     rdx, rdi; int
0x14002e687  mov     ecx, ebx; this
0x14002e689  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002e68e  jmp     loc_14002E547
0x14002e693  mov     rcx, [rbp+5D0h+var_530]; this
0x14002e69a  test    rcx, rcx
0x14002e69d  jz      loc_14002E614
0x14002e6a3  mov     rax, [r13+20h]
0x14002e6a7  xorps   xmm0, xmm0
0x14002e6aa  mov     r8, [rsp+6D0h+var_670]; struct _FLT_FILE_NAME_INFORMATION *
0x14002e6af  mov     rdx, [r13+18h]; struct _FLT_INSTANCE *
0x14002e6b3  mov     qword ptr [rsp+6D0h+NameOptions], rdi; char *
0x14002e6b8  mov     r9d, [rax+50h]
0x14002e6bc  lea     rax, [rbp+5D0h+var_560]
0x14002e6c0  shr     r9d, 11h
0x14002e6c4  not     r9b
0x14002e6c7  mov     [rbp+5D0h+var_560], rsi
0x14002e6cb  and     r9b, sil; bool
0x14002e6ce  mov     [rbp+5D0h+P], r15
0x14002e6d5  movdqu  xmmword ptr [rbp+5D0h+var_558], xmm0
0x14002e6da  mov     qword ptr [rsp+6D0h+FileNameLength], rax; struct UnionFs::LookupScratchRootResults *
0x14002e6df  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x14002e6e4  mov     esi, eax
0x14002e6e6  test    eax, eax
0x14002e6e8  jns     loc_14002E794
0x14002e6ee  lea     rax, aPushLookingUpS; "PUSH: Looking up scratch root"
0x14002e6f5  mov     r8, 345000B006Bh; struct UnionFs::StackEventTracer *
0x14002e6ff  lea     r9, aUnionfsPrerena; "UnionFs::PreRename"
0x14002e706  mov     qword ptr [rsp+6D0h+FileNameLength], rax; char *
0x14002e70b  mov     rdx, rdi; int
0x14002e70e  mov     ecx, esi; this
0x14002e710  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002e715  mov     rbx, [rbp+5D0h+P]
0x14002e71c  test    rbx, rbx
0x14002e71f  jz      short loc_14002E746
0x14002e721  cmp     [rbx+10h], r15b
0x14002e725  jnz     short loc_14002E72D
0x14002e727  xorps   xmm0, xmm0
0x14002e72a  movups  xmmword ptr [rbx], xmm0
0x14002e72d  mov     rcx, rbx; UnicodeString
0x14002e730  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14002e735  xor     edx, edx; Tag
0x14002e737  mov     rcx, rbx; P
0x14002e73a  call    cs:__imp_ExFreePoolWithTag
0x14002e741  nop     dword ptr [rax+rax+00h]
0x14002e746  mov     rcx, [rbp+5D0h+var_558+8]; this
0x14002e74d  test    rcx, rcx
0x14002e750  jz      short loc_14002E757
0x14002e752  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002e757  mov     rcx, [rsp+6D0h+var_670]; FileNameInformation
0x14002e75c  mov     [rsp+6D0h+var_670], r15
0x14002e761  test    rcx, rcx
0x14002e764  jz      short loc_14002E772
0x14002e766  call    cs:__imp_FltReleaseFileNameInformation
0x14002e76d  nop     dword ptr [rax+rax+00h]
0x14002e772  mov     rcx, [rsp+6D0h+FileNameInformation]; FileNameInformation
0x14002e777  mov     [rsp+6D0h+FileNameInformation], r15
0x14002e77c  test    rcx, rcx
0x14002e77f  jz      short loc_14002E78D
0x14002e781  call    cs:__imp_FltReleaseFileNameInformation
0x14002e788  nop     dword ptr [rax+rax+00h]
0x14002e78d  mov     eax, esi
0x14002e78f  jmp     loc_14003198A
0x14002e794  mov     r15, [rbp+5D0h+var_558+8]
0x14002e79b  mov     rsi, r15
0x14002e79e  test    r15, r15
0x14002e7a1  jz      short loc_14002E7A8
0x14002e7a3  lock inc dword ptr [r15+8]
0x14002e7a8  mov     r12, [rbp+5D0h+P]
0x14002e7af  lea     r8, [rsp+6D0h+IsDirectory+3]; IsDirectory
0x14002e7b4  mov     rdx, [r13+18h]; Instance
0x14002e7b8  mov     rcx, [r13+20h]; FileObject
0x14002e7bc  mov     [rbp+5D0h+var_648], r12
0x14002e7c0  mov     [rbp+5D0h+P], 0
0x14002e7cb  mov     [rsp+6D0h+IsDirectory+3], 0
0x14002e7d0  call    cs:__imp_FltIsDirectory
0x14002e7d7  nop     dword ptr [rax+rax+00h]
0x14002e7dc  xor     r13d, r13d
0x14002e7df  mov     ebx, eax
0x14002e7e1  test    eax, eax
0x14002e7e3  jns     loc_14002E881
0x14002e7e9  lea     rax, aApiFltisdirect_3; "API: FltIsDirectory(source)"
0x14002e7f0  mov     r8, 0EB000B0075h; struct UnionFs::StackEventTracer *
0x14002e7fa  lea     r9, aUnionfsPrerena; "UnionFs::PreRename"
0x14002e801  mov     qword ptr [rsp+6D0h+FileNameLength], rax; char *
0x14002e806  mov     rdx, rdi; int
0x14002e809  mov     ecx, ebx; this
0x14002e80b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002e810  test    r12, r12
0x14002e813  jz      short loc_14002E83D
0x14002e815  cmp     [r12+10h], r13b
0x14002e81a  jnz     short loc_14002E824
0x14002e81c  xorps   xmm0, xmm0
0x14002e81f  movups  xmmword ptr [r12], xmm0
0x14002e824  mov     rcx, r12; UnicodeString
0x14002e827  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14002e82c  xor     edx, edx; Tag
0x14002e82e  mov     rcx, r12; P
0x14002e831  call    cs:__imp_ExFreePoolWithTag
0x14002e838  nop     dword ptr [rax+rax+00h]
0x14002e83d  test    r15, r15
0x14002e840  jz      short loc_14002E857
0x14002e842  mov     rcx, r15; this
0x14002e845  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002e84a  test    r15, r15
0x14002e84d  jz      short loc_14002E857
0x14002e84f  mov     rcx, r15; this
0x14002e852  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002e857  mov     rcx, [rsp+6D0h+var_670]; FileNameInformation
0x14002e85c  mov     [rsp+6D0h+var_670], r13
0x14002e861  test    rcx, rcx
0x14002e864  jz      short loc_14002E872
0x14002e866  call    cs:__imp_FltReleaseFileNameInformation
0x14002e86d  nop     dword ptr [rax+rax+00h]
0x14002e872  mov     rcx, [rsp+6D0h+FileNameInformation]
0x14002e877  mov     [rsp+6D0h+FileNameInformation], r13
0x14002e87c  jmp     loc_14002E482
0x14002e881  mov     al, [rsp+6D0h+IsDirectory+3]
0x14002e885  mov     ecx, 2
0x14002e88a  mov     rbx, [rbp+5D0h+var_558]
0x14002e88e  neg     al
0x14002e890  mov     rax, [rbp+5D0h+var_5E8]
0x14002e894  mov     [rbp+5D0h+var_614], r13d
0x14002e898  sbb     r13b, r13b
0x14002e89b  and     r13b, cl
0x14002e89e  mov     [rbp+5D0h+var_530], rbx
0x14002e8a5  mov     rax, [rax+10h]
0x14002e8a9  cmp     dword ptr [rax+20h], 41h ; 'A'
0x14002e8ad  jnz     short loc_14002E8BD
0x14002e8af  mov     rax, [rbp+5D0h+var_578]
0x14002e8b3  mov     eax, [rax]
0x14002e8b5  test    cl, al
0x14002e8b7  jz      short loc_14002E8BD
0x14002e8b9  mov     al, 8
0x14002e8bb  jmp     short loc_14002E8BF
0x14002e8bd  xor     al, al
0x14002e8bf  or      r13b, al
0x14002e8c2  lea     rcx, [rbp+5D0h+var_2C0]; void *
0x14002e8c9  xor     eax, eax
0x14002e8cb  mov     byte ptr [rbp+5D0h+var_614], r13b
0x14002e8cf  xorps   xmm0, xmm0
  ... truncated ...
```
