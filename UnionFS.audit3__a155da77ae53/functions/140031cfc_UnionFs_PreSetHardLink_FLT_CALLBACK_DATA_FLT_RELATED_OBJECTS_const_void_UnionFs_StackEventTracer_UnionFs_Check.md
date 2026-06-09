# UnionFs::PreSetHardLink(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void * *,UnionFs::StackEventTracer &,UnionFs::CheckAndSwitchResults &,UnionFs::UfsStreamHandleCtx const *)

- ea: `0x140031cfc`
- end: `0x1400348ef`
- name: `?PreSetHardLink@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAPEAXAEAVStackEventTracer@1@AEAUCheckAndSwitchResults@1@PEBVUfsStreamHandleCtx@1@@Z`
- size: `11251`
- prototype: `int(UnionFs *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **, struct UnionFs::StackEventTracer *, struct UnionFs::CheckAndSwitchResults *, const struct UnionFs::UfsStreamHandleCtx *)`
- caller_count: `1`
- callee_count: `48`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140034900`

## callees

- `0x140001008`
- `0x140001c08`
- `0x140002354`
- `0x140005d20`
- `0x140005d5c`
- `0x140006340`
- `0x140008140`
- `0x14000883c`
- `0x14000efa0`
- `0x14000f344`
- `0x14000f81c`
- `0x140010ba8`
- `0x1400111b8`
- `0x14001126c`
- `0x1400271d0`
- `0x14002aca0`
- `0x14002ad1c`
- `0x14002ad6c`
- `0x14002b548`
- `0x14002bbec`
- `0x14002bc64`
- `0x14002bd60`
- `0x14002bf04`
- `0x14002c05c`
- `0x140031cfc`
- `0x1400362c0`
- `0x14003cea8`
- `0x1400419c8`
- `0x140043a64`
- `0x140055f1c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140061058`
- `0x1400611a4`
- `0x14006be98`
- `0x14006e394`
- `0x14006f198`
- `0x14006faa8`
- `0x1400704d4`
- `0x1400779fc`
- `0x140079f68`
- `0x14007a0ec`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x140033954`
- `ntoskrnl!IoGetSilo` at `0x140033954`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032129`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032212`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032365`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003265b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400327c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400328ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032d7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032f2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400331f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400332eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033c61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032129`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032212`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032365`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003265b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400327c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400328ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032d7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032f2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400331f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400332eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033c61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033d8c`
- `ntoskrnl!ObfDereferenceObject` at `0x140032b03`
- `ntoskrnl!ObfDereferenceObject` at `0x140032b78`
- `ntoskrnl!ObfDereferenceObject` at `0x140032cb9`
- `ntoskrnl!ObfDereferenceObject` at `0x140032e16`
- `ntoskrnl!ObfDereferenceObject` at `0x140032e6b`
- `ntoskrnl!ObfDereferenceObject` at `0x140032f6c`
- `ntoskrnl!ObfDereferenceObject` at `0x140032b03`
- `ntoskrnl!ObfDereferenceObject` at `0x140032b78`
- `ntoskrnl!ObfDereferenceObject` at `0x140032cb9`
- `ntoskrnl!ObfDereferenceObject` at `0x140032e16`
- `ntoskrnl!ObfDereferenceObject` at `0x140032e6b`
- `ntoskrnl!ObfDereferenceObject` at `0x140032f6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032586`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003273b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032872`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032944`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033570`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033623`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033876`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033b23`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033c95`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032586`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003273b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032872`
- `ntoskrnl!ExReleaseResourceLite` at `0x140032944`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033570`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033623`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033876`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033b23`
- `ntoskrnl!ExReleaseResourceLite` at `0x140033c95`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032592`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032747`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003287e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032950`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003357c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003362f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033882`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033b2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033ca1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032592`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032747`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003287e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032950`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003357c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003362f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033882`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033b2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140033ca1`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140031dad`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140031dad`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031dd7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031e1d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031f51`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032247`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400322d1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003239a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400325c7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032690`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032780`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400328bd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032bfa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032d3b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032eed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400330ec`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003315c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033225`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400332a9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003343b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400335be`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033742`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400338c4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033b71`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033bc7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033ce3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033d39`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033ef3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033f45`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034098`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400341fc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003424e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034359`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034557`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003474c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003486b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400348bd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031dd7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031e1d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031f51`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032247`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400322d1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003239a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400325c7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032690`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032780`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400328bd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032bfa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032d3b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032eed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400330ec`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003315c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033225`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400332a9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003343b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400335be`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033742`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400338c4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033b71`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033bc7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033ce3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033d39`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033ef3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140033f45`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034098`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400341fc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003424e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034359`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140034557`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003474c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003486b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400348bd`
- `FLTMGR!FltReleaseContext` at `0x1400342d7`
- `FLTMGR!FltReleaseContext` at `0x1400344d5`
- `FLTMGR!FltReleaseContext` at `0x1400346cf`
- `FLTMGR!FltReleaseContext` at `0x1400347d6`
- `FLTMGR!FltReleaseContext` at `0x1400342d7`
- `FLTMGR!FltReleaseContext` at `0x1400344d5`
- `FLTMGR!FltReleaseContext` at `0x1400346cf`
- `FLTMGR!FltReleaseContext` at `0x1400347d6`

## string_xrefs

- `0x140033f9c`: `PUSH: Getting relative path`
- `0x140032476`: `PUSH: Cache lookup`
- `0x1400333ef`: `PUSH: Cache lookup`
- `0x140034479`: `Path should exist`
- `0x140031df8`: `UnionFs::PreSetHardLink`
- `0x140031e66`: `UnionFs::PreSetHardLink`
- `0x140031ef0`: `UnionFs::PreSetHardLink`
- `0x140032171`: `UnionFs::PreSetHardLink`
- `0x1400322a9`: `UnionFs::PreSetHardLink`
- `0x14003248c`: `UnionFs::PreSetHardLink`
- `0x14003256b`: `UnionFs::PreSetHardLink`
- `0x14003271a`: `UnionFs::PreSetHardLink`
- `0x140032852`: `UnionFs::PreSetHardLink`
- `0x1400329e2`: `UnionFs::PreSetHardLink`
- `0x140032ae3`: `UnionFs::PreSetHardLink`
- `0x140032b52`: `UnionFs::PreSetHardLink`
- `0x140032c93`: `UnionFs::PreSetHardLink`
- `0x140032e45`: `UnionFs::PreSetHardLink`
- `0x140032fe6`: `UnionFs::PreSetHardLink`
- `0x14003311a`: `UnionFs::PreSetHardLink`
- `0x14003327a`: `UnionFs::PreSetHardLink`
- `0x140033405`: `UnionFs::PreSetHardLink`
- `0x14003353a`: `UnionFs::PreSetHardLink`
- `0x1400336e0`: `UnionFs::PreSetHardLink`
- `0x1400337ad`: `UnionFs::PreSetHardLink`
- `0x1400339d3`: `UnionFs::PreSetHardLink`
- `0x140033ae2`: `UnionFs::PreSetHardLink`
- `0x140033c38`: `UnionFs::PreSetHardLink`
- `0x140033ddc`: `UnionFs::PreSetHardLink`
- `0x140033fad`: `UnionFs::PreSetHardLink`
- `0x140034016`: `UnionFs::PreSetHardLink`
- `0x140034176`: `UnionFs::PreSetHardLink`
- `0x1400342b8`: `UnionFs::PreSetHardLink`
- `0x14003449b`: `UnionFs::PreSetHardLink`
- `0x14003468a`: `UnionFs::PreSetHardLink`
- `0x140033053`: `Found directory tombstone for link target`
- `0x14003309a`: `ORIGIN: Found directory tombstone for link target`
- `0x1400330fd`: `COW Race: Source not found in path cache`
- `0x140033109`: `ORIGIN: COW Race: Source not found in path cache`
- `0x140032709`: `ORIGIN: Rejecting COW of hardlink source`
- `0x140032b35`: `COW Race: Utils::CopyItem destination already existed`
- `0x140032b41`: `ORIGIN: COW Race: Utils::CopyItem destination already existed`
- `0x140032e34`: `ORIGIN: Allocating link context`
- `0x1400336cf`: `ORIGIN: Allocating link context`
- `0x1400337f7`: `Found directory tombstone for link destination`
- `0x140033831`: `ORIGIN: Found directory tombstone at link destination.`
- `0x140033e26`: `Denying attempted superseding hard link without flag.`
- `0x140033a57`: `ORIGIN: Hard link collision`
- `0x140033e60`: `ORIGIN: Hard link collision`
- `0x140034165`: `ORIGIN: Rejecting COW for immutable hardlink destination`
- `0x140033a1d`: `Attempting superseding hard link without flag.`

## pseudocode

```c
__int64 __fastcall UnionFs::PreSetHardLink(
        UnionFs *this,
        struct _FLT_RELATED_OBJECTS *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        void **a4,
        struct UnionFs::StackEventTracer *a5,
        struct UnionFs::CheckAndSwitchResults *a6)
{
  FsFltWil::Details *v6; // r13
  __int64 v10; // rax
  __int64 v11; // rcx
  WCHAR *v12; // r9
  void *v13; // r8
  struct _FILE_OBJECT *FileObject; // rdx
  struct _FLT_INSTANCE *Instance; // rcx
  NTSTATUS DestinationFileNameInformation; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v17; // rax
  struct _FLT_FILE_NAME_INFORMATION *v18; // rcx
  ULONG_PTR v20; // rdx
  PFLT_INSTANCE v21; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v22; // rcx
  const struct _FLT_INSTANCE *v23; // rdx
  ULONG v24; // r9d
  int v25; // esi
  struct _UNICODE_STRING *v26; // rdx
  struct _UNICODE_STRING *v27; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v28; // rcx
  utl::_RefCountBase *v29; // rbx
  UnionFs::UfsLayerCtx *v30; // rdi
  utl::_RefCountBase *v31; // r14
  struct _UNICODE_STRING *v32; // rsi
  UnionFs::UfsLayerCtx **ScratchLayer; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v34; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v35; // rdx
  struct _UNICODE_STRING *v36; // rdx
  unsigned int v37; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v38; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v39; // rdx
  struct _UNICODE_STRING *v40; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v41; // rcx
  UnionFs::UnionFsFilter *v42; // rcx
  int v43; // r15d
  struct FsFltWil::Details::RundownRefCacheAware *v44; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v45; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v46; // rdx
  struct _UNICODE_STRING *v47; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v48; // rcx
  int v49; // eax
  ULONG v50; // r9d
  __int64 v51; // r9
  __int64 v52; // rcx
  int v53; // eax
  int v54; // r8d
  struct UnionFs::StackEventTracer *v55; // r9
  utl::_RefCountBase *v56; // rdx
  utl::_RefCountBase *v57; // rcx
  utl::_RefCountBase *v58; // rax
  utl::_RefCountBase *v59; // rdx
  struct _ERESOURCE *v60; // r15
  int IsFileCowable; // eax
  int v62; // r8d
  int v63; // r13d
  struct FsFltWil::Details::RundownRefCacheAware *v64; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v65; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v66; // rdx
  struct _UNICODE_STRING *v67; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v68; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v69; // rcx
  struct _UNICODE_STRING *v70; // rdx
  int v71; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v72; // rcx
  struct _UNICODE_STRING *v73; // rdx
  int v74; // edi
  struct _FLT_RELATED_OBJECTS *v75; // r15
  int v76; // eax
  struct _UNICODE_STRING *v77; // rdx
  utl::_RefCountBase *v78; // rcx
  utl::_RefCountBase *v79; // rax
  utl::_RefCountBase *v80; // rcx
  PFLT_INSTANCE v81; // r9
  int v82; // edx
  struct _FLT_CALLBACK_DATA *v83; // rdi
  int v84; // eax
  PVOID v85; // rcx
  struct _UNICODE_STRING *v86; // rdx
  PVOID v87; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v88; // rcx
  struct _UNICODE_STRING *v89; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v90; // rcx
  UnionFs::UnionFsFilter *v91; // rcx
  const struct _FLT_INSTANCE *ScratchInstance; // r8
  struct _UNICODE_STRING *v93; // rdx
  PVOID v94; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v95; // rcx
  struct _UNICODE_STRING *v96; // rdx
  __int64 v97; // rax
  struct _UNICODE_STRING *v98; // rdx
  struct _UNICODE_STRING *v99; // rdx
  PVOID v100; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v101; // rcx
  struct _UNICODE_STRING *v102; // rdx
  PVOID v103; // rcx
  UNICODE_STRING *p_Name; // rcx
  bool v105; // zf
  struct _FLT_FILE_NAME_INFORMATION *v106; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v107; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v108; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v109; // rdx
  struct _UNICODE_STRING *v110; // rdx
  struct _FLT_RELATED_OBJECTS *v111; // r8
  struct _FLT_FILE_NAME_INFORMATION *v112; // rcx
  struct _UNICODE_STRING *v113; // rdx
  char v114; // r9
  __int64 v115; // r9
  __int64 v116; // rcx
  int v117; // eax
  int v118; // r8d
  int v119; // r9d
  struct _FLT_FILE_NAME_INFORMATION *v120; // rcx
  utl::_RefCountBase *v121; // rdi
  FsFltWil::Details *v122; // rbx
  volatile signed __int32 *v123; // r15
  bool v124; // al
  struct _ERESOURCE *v125; // r13
  int v126; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v127; // rcx
  utl::_RefCountBase *v128; // rcx
  __int64 v129; // rbx
  __int64 v130; // rax
  struct _FLT_FILE_NAME_INFORMATION *v131; // rcx
  utl::_RefCountBase *v132; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v133; // rcx
  struct UnionFs::StackEventTracer *v134; // r9
  PFILE_OBJECT v135; // rbx
  BOOL v136; // edi
  __int64 Silo; // rax
  int v138; // ebx
  int v139; // r8d
  bool v140; // dl
  _QWORD *v141; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v142; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v143; // rcx
  int v144; // eax
  utl::_RefCountBase *v145; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v146; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v147; // rcx
  volatile signed __int32 *v148; // r13
  __int16 v149; // ax
  void *v150; // rcx
  int v151; // r8d
  utl::_RefCountBase *v152; // rcx
  struct _ERESOURCE *v153; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v154; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v155; // rcx
  struct _UNICODE_STRING *v156; // rdx
  int v157; // eax
  struct _ERESOURCE *v158; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v159; // rcx
  char v160; // al
  struct _ERESOURCE *v161; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v162; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v163; // rcx
  struct _UNICODE_STRING *v164; // rdx
  struct _ERESOURCE *v165; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v166; // rcx
  UnionFs::UfsUnionCtx *v167; // r11
  volatile signed __int32 *v168; // rax
  const struct UnionFs::UfsLayerCtx *v169; // rcx
  PVOID v170; // rsi
  struct _UNICODE_STRING *v171; // rdx
  struct _UNICODE_STRING *v172; // rdx
  struct _UNICODE_STRING *v173; // rdx
  struct _ERESOURCE *v174; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v175; // rcx
  bool v176; // bl
  utl::_RefCountBase *v177; // rcx
  PFLT_INSTANCE v178; // r9
  volatile signed __int32 *v179; // rbx
  __int64 v180; // r8
  __int64 v181; // rax
  int v182; // eax
  struct _UNICODE_STRING *v183; // rdx
  struct _UNICODE_STRING *v184; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v185; // rcx
  struct _UNICODE_STRING *v186; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v187; // rcx
  struct UnionFs::CheckAndSwitchResults *FileNameLength; // [rsp+20h] [rbp-E0h]
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
  PFLT_FILE_NAME_INFORMATION v199; // [rsp+58h] [rbp-A8h] BYREF
  char v200; // [rsp+60h] [rbp-A0h] BYREF
  bool v201; // [rsp+61h] [rbp-9Fh]
  __int64 v202; // [rsp+68h] [rbp-98h] BYREF
  PVOID v203; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v204; // [rsp+78h] [rbp-88h] BYREF
  utl::_RefCountBase *v205[2]; // [rsp+80h] [rbp-80h] BYREF
  utl::_RefCountBase *v206; // [rsp+90h] [rbp-70h] BYREF
  PVOID Object[2]; // [rsp+98h] [rbp-68h] BYREF
  PVOID v208; // [rsp+A8h] [rbp-58h] BYREF
  struct UnionFs::CheckAndSwitchResults *v209; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v210; // [rsp+B8h] [rbp-48h]
  char v211[8]; // [rsp+C0h] [rbp-40h] BYREF
  utl::_RefCountBase **v212; // [rsp+C8h] [rbp-38h] BYREF
  char v213; // [rsp+D0h] [rbp-30h]
  PVOID RetFileNameInformation[4]; // [rsp+E0h] [rbp-20h] BYREF
  FsFltWil::Details *v215; // [rsp+100h] [rbp+0h] BYREF
  utl::_RefCountBase *v216; // [rsp+108h] [rbp+8h]
  struct _FLT_CALLBACK_DATA *v217; // [rsp+110h] [rbp+10h] BYREF
  struct _FLT_RELATED_OBJECTS *v218; // [rsp+118h] [rbp+18h]
  __int64 v219; // [rsp+120h] [rbp+20h] BYREF
  utl::_RefCountBase *v220[2]; // [rsp+128h] [rbp+28h]
  PVOID P; // [rsp+138h] [rbp+38h]
  utl::_RefCountBase *v222; // [rsp+140h] [rbp+40h]
  char v223[8]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v224; // [rsp+150h] [rbp+50h]
  utl::_RefCountBase *v225[2]; // [rsp+160h] [rbp+60h]
  __int64 v226; // [rsp+170h] [rbp+70h]
  int v227; // [rsp+178h] [rbp+78h]
  __int128 v228; // [rsp+180h] [rbp+80h] BYREF
  utl::_RefCountBase *v229[2]; // [rsp+190h] [rbp+90h]
  PERESOURCE v230; // [rsp+1A0h] [rbp+A0h]
  __int64 v231; // [rsp+1A8h] [rbp+A8h]
  __int128 v232; // [rsp+1B0h] [rbp+B0h]
  __int128 v233; // [rsp+1C0h] [rbp+C0h] BYREF
  bool *v234[2]; // [rsp+1D0h] [rbp+D0h]
  PERESOURCE Resource; // [rsp+1E0h] [rbp+E0h]
  __int64 v236; // [rsp+1E8h] [rbp+E8h]
  __int128 v237; // [rsp+1F0h] [rbp+F0h]
  utl::_RefCountBase *v238[2]; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v239[17]; // [rsp+210h] [rbp+110h] BYREF
  utl::_RefCountBase *v240[2]; // [rsp+298h] [rbp+198h] BYREF
  _QWORD v241[17]; // [rsp+2A8h] [rbp+1A8h] BYREF
  struct _UNICODE_STRING UnicodeString[7]; // [rsp+330h] [rbp+230h] BYREF
  PWSTR *p_Buffer; // [rsp+3A0h] [rbp+2A0h]

  v6 = a6;
  *(_QWORD *)&a3->Size = 0;
  v209 = a5;
  v10 = *((_QWORD *)this + 2);
  FileNameInformation = 0;
  v217 = (struct _FLT_CALLBACK_DATA *)this;
  v222 = (utl::_RefCountBase *)a3;
  v11 = *(_QWORD *)(v10 + 56);
  RetFileNameInformation[0] = &FileNameInformation;
  v218 = a2;
  LODWORD(v10) = *(_DWORD *)(v11 + 16);
  v12 = (WCHAR *)(v11 + 20);
  v13 = *(void **)(v11 + 8);
  FileObject = a2->FileObject;
  v204 = (_BYTE *)v11;
  Instance = a2->Instance;
  v215 = a6;
  v210 = 0;
  RetFileNameInformation[1] = 0;
  LOBYTE(RetFileNameInformation[2]) = 1;
  DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                     Instance,
                                     FileObject,
                                     v13,
                                     v12,
                                     v10,
                                     0x1000101u,
                                     (PFLT_FILE_NAME_INFORMATION *)&RetFileNameInformation[1]);
  if ( LOBYTE(RetFileNameInformation[2]) )
  {
    v17 = *(struct _FLT_FILE_NAME_INFORMATION **)RetFileNameInformation[0];
    *(_QWORD *)RetFileNameInformation[0] = RetFileNameInformation[1];
    if ( v17 )
      FltReleaseFileNameInformation(v17);
  }
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39B000B04C1LL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "API: Getting destination file name information",
      NameOptions);
LABEL_6:
    v18 = FileNameInformation;
    FileNameInformation = 0;
LABEL_7:
    if ( v18 )
      FltReleaseFileNameInformation(v18);
    return (unsigned int)DestinationFileNameInformation;
  }
  v20 = (ULONG_PTR)a2->FileObject;
  v21 = a2->Instance;
  v203 = 0;
  DestinationFileNameInformation = UnionFs::Utils::GetMappingTableForFileObject(v21, v20, &v203, a4, 0);
  if ( DestinationFileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DestinationFileNameInformation,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39C000B04CALL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Getting mapping table",
      NameOptions);
    goto LABEL_6;
  }
  if ( !v203 )
  {
    v22 = FileNameInformation;
    FileNameInformation = 0;
LABEL_590:
    if ( v22 )
      FltReleaseFileNameInformation(v22);
    return 0;
  }
  v23 = a2->Instance;
  v24 = a2->FileObject->Flags >> 17;
  v219 = 1;
  P = 0;
  *(_OWORD *)v220 = 0;
  v25 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
          (UnionFs::UfsScratchMappingTable *)v203,
          v23,
          FileNameInformation,
          (v24 & 1) == 0,
          (struct UnionFs::LookupScratchRootResults *)&v219,
          (struct UnionFs::StackEventTracer *)a4);
  if ( v25 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v25,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39D000B04DCLL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Looking up scratch root",
      NameOptionsa);
    v27 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v27, v26);
      ExFreePoolWithTag(v27, 0);
    }
    if ( v220[1] )
      utl::_RefCountBase::_DecStrong(v220[1]);
    v28 = FileNameInformation;
    FileNameInformation = 0;
    if ( v28 )
      FltReleaseFileNameInformation(v28);
    return (unsigned int)v25;
  }
  v29 = v220[1];
  v30 = v220[0];
  v31 = v220[1];
  v206 = v220[0];
  if ( v220[1] )
    _InterlockedIncrement((volatile signed __int32 *)v220[1] + 2);
  v32 = (struct _UNICODE_STRING *)P;
  v208 = P;
  P = 0;
  *(_OWORD *)v240 = 0;
  memset(v241, 0, sizeof(v241));
  if ( a6 )
  {
    ScratchLayer = (UnionFs::UfsLayerCtx **)UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(a6, RetFileNameInformation);
    UnionFs::UfsLayerCtx::TryGetOwningUnion(
      *ScratchLayer,
      (struct UnionFs::UfsUnionCtxWithRundown *)v240,
      (struct UnionFs::StackEventTracer *)a4);
    if ( RetFileNameInformation[1] )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)RetFileNameInformation[1]);
    if ( !v240[0] )
    {
      *(_DWORD *)a4 = 0;
      v6 = 0;
      *((_WORD *)a4 + 274) = 0;
      v215 = 0;
    }
  }
  *(_OWORD *)v238 = 0;
  memset(v239, 0, sizeof(v239));
  if ( v30 )
  {
    UnionFs::UfsLayerCtx::TryGetOwningUnion(
      v30,
      (struct UnionFs::UfsUnionCtxWithRundown *)v238,
      (struct UnionFs::StackEventTracer *)a4);
    if ( !v238[0] )
    {
      *(_DWORD *)a4 = 0;
      *((_WORD *)a4 + 274) = 0;
      if ( v29 )
        utl::_RefCountBase::_DecStrong(v29);
      v30 = 0;
      v206 = 0;
      v31 = 0;
    }
  }
  if ( !v6 )
  {
    if ( !v30 )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v239, v34);
      if ( v239[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v239[16] + 24LL))(v239[16]);
      if ( v238[1] )
        utl::_RefCountBase::_DecStrong(v238[1]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v241, v35);
      if ( v241[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v241[16] + 24LL))(v241[16]);
      if ( v240[1] )
        utl::_RefCountBase::_DecStrong(v240[1]);
      if ( v32 )
      {
        if ( !LOBYTE(v32[1].Length) )
          *v32 = 0;
        FsFltWil::Details::FreeUnicodeString(v32, v36);
        ExFreePoolWithTag(v32, 0);
      }
      if ( v31 )
        utl::_RefCountBase::_DecStrong(v31);
      if ( v29 )
        utl::_RefCountBase::_DecStrong(v29);
      v22 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_590;
    }
    v37 = -1058209789;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0003LL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x5ED000B050FLL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "ORIGIN: Source not in a union, destination is",
      NameOptionsa);
    goto LABEL_56;
  }
  v199 = 0;
  RetFileNameInformation[0] = this;
  RetFileNameInformation[1] = 0;
  RetFileNameInformation[2] = 0;
  v43 = UnionFs::Utils::GetFileNameInformation(RetFileNameInformation, 16778241, &v199, a4);
  if ( v43 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v43,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39A000B051DLL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Getting source file name information",
      NameOptionsa);
LABEL_78:
    v45 = v199;
    v199 = 0;
    if ( v45 )
      FltReleaseFileNameInformation(v45);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v239, v44);
    if ( v239[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v239[16] + 24LL))(v239[16]);
    if ( v238[1] )
      utl::_RefCountBase::_DecStrong(v238[1]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v241, v46);
    if ( v241[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v241[16] + 24LL))(v241[16]);
    if ( v240[1] )
      utl::_RefCountBase::_DecStrong(v240[1]);
    if ( v32 )
    {
      if ( !LOBYTE(v32[1].Length) )
        *v32 = 0;
      FsFltWil::Details::FreeUnicodeString(v32, v47);
      ExFreePoolWithTag(v32, 0);
    }
    if ( v31 )
      utl::_RefCountBase::_DecStrong(v31);
    if ( v29 )
      utl::_RefCountBase::_DecStrong(v29);
    v48 = FileNameInformation;
    FileNameInformation = 0;
    if ( v48 )
      FltReleaseFileNameInformation(v48);
    return (unsigned int)v43;
  }
  v49 = *(_DWORD *)v6;
  *(_QWORD *)v211 = 0;
  v202 = 0;
  if ( (v49 & 1) != 0 )
  {
    if ( (v49 & 0x20) != 0 )
    {
      v75 = v218;
      v111 = v218;
      FileNameLength = v209;
      *(_DWORD *)v209 |= 1u;
      v83 = v217;
      DestinationFileNameInformation = UnionFs::UnionFsFilter::CheckAndSwitchTarget(
                                         v42,
                                         v217,
                                         v111,
                                         (struct UnionFs::StackEventTracer *)a4,
                                         FileNameLength);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x4CF000B05EELL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: CheckAndSwitchTarget failure on SFO",
          NameOptionsa);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v112 = v199;
        v199 = 0;
        if ( v112 )
          FltReleaseFileNameInformation(v112);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v113);
          ExFreePoolWithTag(v32, 0);
        }
        goto LABEL_307;
      }
    }
    else
    {
      v50 = ~(v218->FileObject->Flags >> 17);
      v233 = 0;
      *(_OWORD *)v234 = 0;
      v51 = v50 & 1 | 0xA;
      Resource = 0;
      v236 = 0;
      v237 = 0;
      if ( *((_DWORD *)v240[0] + 7) == 2 )
        v52 = *(_QWORD *)(*((_QWORD *)v240[0] + 4) + 16LL);
      else
        v52 = *((_QWORD *)UnionFs::g_FilterState + 10);
      NameOptionsb = (const char *)a4;
      v53 = UnionFs::UfsPathCache::LookupEntry(v52, v218->Instance, v199, v51, &v233);
      v43 = v53;
      if ( v53 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v53,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B9000B053CLL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Cache lookup",
          (const char *)a4);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        goto LABEL_78;
      }
      *(_OWORD *)v205 = 0;
      if ( !v234[0] )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("COW Race: Source not found in path cache");
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BBLL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x4CE000B0564LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: COW Race: Source not found in path cache",
          (const char *)a4);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        v108 = v199;
        v199 = 0;
        if ( v108 )
          FltReleaseFileNameInformation(v108);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v239, v107);
        if ( v239[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v239[16] + 24LL))(v239[16]);
        if ( v238[1] )
          utl::_RefCountBase::_DecStrong(v238[1]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v241, v109);
        if ( v241[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v241[16] + 24LL))(v241[16]);
        if ( v240[1] )
          utl::_RefCountBase::_DecStrong(v240[1]);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v110);
          ExFreePoolWithTag(v32, 0);
        }
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        if ( v29 )
          utl::_RefCountBase::_DecStrong(v29);
        v90 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_297;
      }
      if ( (unsigned __int16)(*((_WORD *)v234[0] + 84) - 3) <= 1u )
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x400) != 0
          && (qword_14009E190 & 0x400) == qword_14009E190 )
        {
          p_Name = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
          *(_QWORD *)v211 = "UnionFs::PreSetHardLink";
          v105 = v199->Name.Buffer == 0;
          LODWORD(v204) = 1357;
          if ( !v105 )
            p_Name = &v199->Name;
          v206 = (utl::_RefCountBase *)"onecore\\base\\fs\\unionfs\\sys\\info.cpp";
          v217 = (struct _FLT_CALLBACK_DATA *)"Found directory tombstone for link target";
          v203 = p_Name;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (_DWORD)p_Name,
            (unsigned int)byte_140096B0D,
            v54,
            (_DWORD)v55,
            (__int64)&v217,
            (__int64)v211,
            (__int64)&v206,
            (__int64)&v204,
            (__int64)&v203);
        }
        v37 = -1073741638;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x5EF000B0552LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Found directory tombstone for link target",
          NameOptionsb);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        v106 = v199;
        v199 = 0;
        if ( v106 )
          FltReleaseFileNameInformation(v106);
LABEL_56:
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v239, v38);
        if ( v239[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v239[16] + 24LL))(v239[16]);
        if ( v238[1] )
          utl::_RefCountBase::_DecStrong(v238[1]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v241, v39);
        if ( v241[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v241[16] + 24LL))(v241[16]);
        if ( v240[1] )
          utl::_RefCountBase::_DecStrong(v240[1]);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v40);
          ExFreePoolWithTag(v32, 0);
        }
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        if ( v29 )
          utl::_RefCountBase::_DecStrong(v29);
        v41 = FileNameInformation;
        FileNameInformation = 0;
LABEL_73:
        if ( v41 )
          FltReleaseFileNameInformation(v41);
        return v37;
      }
      v56 = v205[1];
      v57 = (utl::_RefCountBase *)v234[0];
      v58 = (utl::_RefCountBase *)v234[1];
      *(_OWORD *)v234 = 0;
      v205[0] = v57;
      v205[1] = v58;
      if ( v56 )
      {
        utl::_RefCountBase::_DecStrong(v56);
        v57 = v205[0];
      }
      v59 = v240[0];
      v60 = Resource;
      Resource = 0;
      if ( (*((_DWORD *)v240[0] + 6) & 0x80u) != 0 )
      {
        v200 = 0;
        IsFileCowable = UnionFs::Utils::IsFileCowable(
                          (UnionFs::Utils *)&v200,
                          (bool *)v57,
                          (struct UnionFs::UfsPathCachePayload *)a4,
                          v55);
        v63 = IsFileCowable;
        if ( IsFileCowable < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)IsFileCowable,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x78C000B056FLL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "PUSH: Checking immutability",
            (const char *)a4);
          if ( v60 )
          {
            ExReleaseResourceLite(v60);
            KeLeaveCriticalRegion();
          }
          if ( v205[1] )
            utl::_RefCountBase::_DecStrong(v205[1]);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
          v65 = v199;
          v199 = 0;
          if ( v65 )
            FltReleaseFileNameInformation(v65);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v239, v64);
          if ( v239[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v239[16] + 24LL))(v239[16]);
          if ( v238[1] )
            utl::_RefCountBase::_DecStrong(v238[1]);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v241, v66);
          if ( v241[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v241[16] + 24LL))(v241[16]);
          if ( v240[1] )
            utl::_RefCountBase::_DecStrong(v240[1]);
          if ( v32 )
          {
            if ( !LOBYTE(v32[1].Length) )
              *v32 = 0;
            FsFltWil::Details::FreeUnicodeString(v32, v67);
            ExFreePoolWithTag(v32, 0);
          }
          if ( v31 )
            utl::_RefCountBase::_DecStrong(v31);
          if ( v29 )
            utl::_RefCountBase::_DecStrong(v29);
          v68 = FileNameInformation;
          FileNameInformation = 0;
LABEL_135:
          if ( v68 )
            FltReleaseFileNameInformation(v68);
          return (unsigned int)v63;
        }
        if ( !v200 )
        {
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x400000000000LL) != 0
            && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
          {
            v203 = (PVOID)1;
            v206 = (utl::_RefCountBase *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)&byte_140096E4F,
              v62,
              (unsigned int)&v206,
              (__int64)&v203);
          }
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000022LL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x78D000B057CLL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "ORIGIN: Rejecting COW of hardlink source",
            (const char *)a4);
          if ( v60 )
          {
            ExReleaseResourceLite(v60);
            KeLeaveCriticalRegion();
          }
          if ( v205[1] )
            utl::_RefCountBase::_DecStrong(v205[1]);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
          v69 = v199;
          v199 = 0;
          if ( v69 )
            FltReleaseFileNameInformation(v69);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
          if ( v32 )
          {
            if ( !LOBYTE(v32[1].Length) )
              *v32 = 0;
            FsFltWil::Details::FreeUnicodeString(v32, v70);
            ExFreePoolWithTag(v32, 0);
          }
LABEL_153:
          if ( v31 )
            utl::_RefCountBase::_DecStrong(v31);
LABEL_490:
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
          v163 = FileNameInformation;
          FileNameInformation = 0;
          if ( v163 )
            FltReleaseFileNameInformation(v163);
          return 3221225506LL;
        }
        v59 = v240[0];
        LODWORD(v57) = v205[0];
        v6 = v215;
      }
      v71 = (int)v199;
      RetFileNameInformation[0] = v59;
      RetFileNameInformation[1] = v240[1];
      if ( v240[1] )
        _InterlockedIncrement((volatile signed __int32 *)v240[1] + 2);
      DestinationFileNameInformation = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(
                                         (_DWORD)v57,
                                         (unsigned int)RetFileNameInformation,
                                         v71,
                                         8,
                                         (_DWORD)a4);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x42A000B0589LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: ConvertToSoftTombstone for COW",
          (const char *)a4);
        if ( v60 )
        {
          ExReleaseResourceLite(v60);
          KeLeaveCriticalRegion();
        }
LABEL_162:
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v72 = v199;
        v199 = 0;
        if ( v72 )
          FltReleaseFileNameInformation(v72);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v73);
          ExFreePoolWithTag(v32, 0);
        }
LABEL_170:
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
LABEL_508:
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
        v18 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_7;
      }
      v213 = 1;
      v212 = v205;
      if ( v60 )
      {
        ExReleaseResourceLite(v60);
        KeLeaveCriticalRegion();
      }
      UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(v6, &v215);
      UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)UnicodeString, &v199->Name, v199->Volume.Length);
      v74 = (int)v215;
      v75 = v218;
      v76 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
              v238[0],
              v217,
              v218,
              v199,
              (const struct UnionFs::UfsPathName *)UnicodeString,
              v6,
              v215,
              (struct UnionFs::StackEventTracer *)a4,
              0);
      DestinationFileNameInformation = v76;
      if ( v76 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v76,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B1000B05A7LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Preparing for COW",
          NameOptionsc);
LABEL_177:
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v77);
        if ( v216 )
          utl::_RefCountBase::_DecStrong(v216);
        wil::details::lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___::_lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___(&v212);
        goto LABEL_162;
      }
      v78 = v205[0];
      *(utl::_RefCountBase **)v223 = v240[0];
      v79 = v205[1];
      v226 = 0;
      v227 = 22;
      v224 = 0;
      *(_OWORD *)v225 = 0;
      if ( v205[1] )
        _InterlockedIncrement((volatile signed __int32 *)v205[1] + 2);
      *((_QWORD *)&v224 + 1) = v78;
      v80 = v225[0];
      v225[0] = v79;
      if ( v80 )
        utl::_RefCountBase::_DecStrong(v80);
      v81 = v75->Instance;
      v82 = v74;
      v83 = v217;
      Object[0] = 0;
      v84 = UnionFs::Utils::CopyItem(
              (_DWORD)v217,
              v82,
              *((_QWORD *)v205[0] + 6),
              (_DWORD)v81,
              UnicodeString,
              (__int64)v223,
              (struct _FILE_OBJECT *)a4,
              (__int64)Object);
      DestinationFileNameInformation = v84;
      if ( v84 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v84,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B2000B05B7LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Performing COW",
          NameOptionsd);
        v85 = Object[0];
        Object[0] = 0;
        if ( v85 )
          ObfDereferenceObject(v85);
        if ( v225[0] )
          utl::_RefCountBase::_DecStrong(v225[0]);
        goto LABEL_177;
      }
      v213 = 0;
      if ( !Object[0] )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("COW Race: Utils::CopyItem destination already existed");
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BBLL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3D4000B05C8LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: COW Race: Utils::CopyItem destination already existed",
          NameOptionsd);
        v87 = Object[0];
        Object[0] = 0;
        if ( v87 )
          ObfDereferenceObject(v87);
        if ( v225[0] )
          utl::_RefCountBase::_DecStrong(v225[0]);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v86);
        if ( v216 )
          utl::_RefCountBase::_DecStrong(v216);
        wil::details::lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___::_lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v88 = v199;
        v199 = 0;
        if ( v88 )
          FltReleaseFileNameInformation(v88);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v89);
          ExFreePoolWithTag(v32, 0);
        }
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
        v90 = FileNameInformation;
        FileNameInformation = 0;
LABEL_297:
        if ( v90 )
          FltReleaseFileNameInformation(v90);
        return 3221225659LL;
      }
      ScratchInstance = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(v6);
      if ( !ScratchInstance )
      {
        v37 = -1058209784;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0008LL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x4CD000B05D1LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Scratch instance not available",
          NameOptionsd);
        v94 = Object[0];
        Object[0] = 0;
        if ( v94 )
          ObfDereferenceObject(v94);
        if ( v225[0] )
          utl::_RefCountBase::_DecStrong(v225[0]);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v93);
        if ( v216 )
          utl::_RefCountBase::_DecStrong(v216);
        wil::details::lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___::_lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v95 = v199;
        v199 = 0;
        if ( v95 )
          FltReleaseFileNameInformation(v95);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v96);
          ExFreePoolWithTag(v32, 0);
        }
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
        v41 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_73;
      }
      UnionFs::UnionFsFilter::SwitchTarget(
        v91,
        v83,
        ScratchInstance,
        (const struct _FILE_OBJECT *)Object[0],
        (struct UnionFs::CheckAndSwitchResults *)((char *)v209 + 8));
      RetFileNameInformation[0] = Object[0];
      Object[0] = 0;
      *(_OWORD *)&RetFileNameInformation[1] = 0;
      v97 = utl::make_unique<UnionFs::LinkContext,UnionFs::LinkContext,0>(&v203, RetFileNameInformation);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::operator=(&v202, v97);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v203);
      if ( RetFileNameInformation[2] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)RetFileNameInformation[2]);
      if ( RetFileNameInformation[0] )
        ObfDereferenceObject(RetFileNameInformation[0]);
      *(_QWORD *)v211 = v202;
      if ( !v202 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3C7000B05DFLL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Allocating link context",
          NameOptionsd);
        v100 = Object[0];
        Object[0] = 0;
        if ( v100 )
          ObfDereferenceObject(v100);
        if ( v225[0] )
          utl::_RefCountBase::_DecStrong(v225[0]);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v99);
        if ( v216 )
          utl::_RefCountBase::_DecStrong(v216);
        wil::details::lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___::_lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v101 = v199;
        v199 = 0;
        if ( v101 )
          FltReleaseFileNameInformation(v101);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v102);
          ExFreePoolWithTag(v32, 0);
        }
LABEL_252:
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
LABEL_399:
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
        v143 = FileNameInformation;
        FileNameInformation = 0;
        if ( v143 )
          FltReleaseFileNameInformation(v143);
        return 3221225626LL;
      }
      v103 = Object[0];
      Object[0] = 0;
      if ( v103 )
        ObfDereferenceObject(v103);
      if ( v225[0] )
        utl::_RefCountBase::_DecStrong(v225[0]);
      if ( !LOBYTE(UnicodeString[1].Length) )
        UnicodeString[0] = 0;
      FsFltWil::Details::FreeUnicodeString(UnicodeString, v98);
      if ( v216 )
        utl::_RefCountBase::_DecStrong(v216);
      wil::details::lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___::_lambda_call__lambda_b2b2b10256270a0b74a3a8cde47aab40___(&v212);
      if ( v205[1] )
        utl::_RefCountBase::_DecStrong(v205[1]);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v233);
    }
  }
  else
  {
    v75 = v218;
    v83 = v217;
  }
  if ( !v206 )
  {
LABEL_583:
    if ( *(_QWORD *)v211 )
    {
      v202 = 0;
      *(_QWORD *)v222 = *(_QWORD *)v211;
    }
    utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
    v187 = v199;
    v199 = 0;
    if ( v187 )
      FltReleaseFileNameInformation(v187);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
    if ( v31 )
      utl::_RefCountBase::_DecStrong(v31);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
    v22 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_590;
  }
  if ( v83->Iopb->Parameters.Create.Options == 72 )
    v200 = *v204 & 1;
  else
    v200 = *v204 != 0;
  v114 = ~(unsigned __int8)(v75->FileObject->Flags >> 17);
  v228 = 0;
  *(_OWORD *)v229 = 0;
  v115 = v114 & 1 | 0xAu;
  v230 = 0;
  v231 = 0;
  v232 = 0;
  if ( *((_DWORD *)v238[0] + 7) == 2 )
    v116 = *(_QWORD *)(*((_QWORD *)v238[0] + 4) + 16LL);
  else
    v116 = *((_QWORD *)UnionFs::g_FilterState + 10);
  NameOptionse = (const char *)a4;
  v117 = UnionFs::UfsPathCache::LookupEntry(v116, v75->Instance, FileNameInformation, v115, &v228);
  DestinationFileNameInformation = v117;
  if ( v117 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v117,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x3AD000B0616LL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "PUSH: Cache lookup",
      (const char *)a4);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
    utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
    v120 = v199;
    v199 = 0;
    if ( v120 )
      FltReleaseFileNameInformation(v120);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
LABEL_307:
    if ( v31 )
      utl::_RefCountBase::_DecStrong(v31);
    goto LABEL_508;
  }
  v121 = v229[0];
  v122 = (FsFltWil::Details *)v230;
  v123 = (volatile signed __int32 *)v229[1];
  v124 = v229[0] != 0;
  v212 = v205;
  v230 = 0;
  v203 = v229[0];
  v125 = (struct _ERESOURCE *)v122;
  *(_OWORD *)v229 = 0;
  v215 = v122;
  v201 = v124;
  v213 = 1;
  LOBYTE(Object[0]) = 1;
  *(_OWORD *)v205 = 0;
  if ( v124 )
  {
    LOWORD(Object[0]) = *((_WORD *)v121 + 84);
    if ( (unsigned __int16)(LOWORD(Object[0]) - 3) <= 1u )
    {
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x400) != 0
        && (qword_14009E190 & 0x400) == qword_14009E190 )
      {
        LODWORD(v204) = 1591;
        v203 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
        v206 = (utl::_RefCountBase *)"UnionFs::PreSetHardLink";
        *(_QWORD *)v211 = "Found directory tombstone for link destination";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          1024,
          (unsigned int)word_140096D0A,
          v118,
          v119,
          (__int64)v211,
          (__int64)&v206,
          (__int64)&v203,
          (__int64)&v204);
      }
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000022LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x461000B063CLL,
        (unsigned __int64)"UnionFs::PreSetHardLink",
        "ORIGIN: Found directory tombstone at link destination.",
        NameOptionse);
      wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
      if ( v205[1] )
        utl::_RefCountBase::_DecStrong(v205[1]);
      if ( v122 )
      {
        ExReleaseResourceLite((PERESOURCE)v122);
        KeLeaveCriticalRegion();
      }
      if ( v123 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
      v133 = v199;
      v199 = 0;
      if ( v133 )
        FltReleaseFileNameInformation(v133);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
      goto LABEL_153;
    }
    v126 = (int)FileNameInformation;
    RetFileNameInformation[0] = v238[0];
    RetFileNameInformation[1] = v238[1];
    if ( v238[1] )
      _InterlockedIncrement((volatile signed __int32 *)v238[1] + 2);
    v63 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(
            (_DWORD)v121,
            (unsigned int)RetFileNameInformation,
            v126,
            7,
            (_DWORD)a4);
    if ( v63 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v63,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x6AF000B064DLL,
        (unsigned __int64)"UnionFs::PreSetHardLink",
        "PUSH: Could not place soft tombstone",
        (const char *)a4);
      wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
      if ( v205[1] )
        utl::_RefCountBase::_DecStrong(v205[1]);
      if ( v122 )
      {
        ExReleaseResourceLite((PERESOURCE)v122);
        KeLeaveCriticalRegion();
      }
      if ( v123 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
      utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
      v127 = v199;
      v199 = 0;
      if ( v127 )
        FltReleaseFileNameInformation(v127);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
      if ( v31 )
        utl::_RefCountBase::_DecStrong(v31);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
      v68 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_135;
    }
    v125 = 0;
    v215 = 0;
    if ( v122 )
    {
      ExReleaseResourceLite((PERESOURCE)v122);
      KeLeaveCriticalRegion();
    }
    if ( v123 )
      _InterlockedIncrement(v123 + 2);
    v128 = v205[1];
    v205[0] = v121;
    v205[1] = (utl::_RefCountBase *)v123;
    if ( v128 )
      utl::_RefCountBase::_DecStrong(v128);
    if ( LOWORD(Object[0]) == 2 )
    {
      v129 = *(_QWORD *)v211;
      if ( *(_QWORD *)v211 )
      {
        if ( v123 )
          _InterlockedIncrement(v123 + 2);
        v132 = *(utl::_RefCountBase **)(v129 + 16);
        *(_QWORD *)(v129 + 16) = v123;
        *(_QWORD *)(v129 + 8) = v121;
        if ( v132 )
          utl::_RefCountBase::_DecStrong(v132);
      }
      else
      {
        if ( v123 )
          _InterlockedIncrement(v123 + 2);
        RetFileNameInformation[0] = 0;
        RetFileNameInformation[1] = v121;
        RetFileNameInformation[2] = (PVOID)v123;
        v130 = utl::make_unique<UnionFs::LinkContext,UnionFs::LinkContext,0>(&v203, RetFileNameInformation);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::operator=(&v202, v130);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v203);
        UnionFs::LinkContext::~LinkContext((UnionFs::LinkContext *)RetFileNameInformation);
        *(_QWORD *)v211 = v202;
        if ( !v202 )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC000009ALL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x45C000B0665LL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "ORIGIN: Allocating link context",
            (const char *)a4);
          wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
          if ( v205[1] )
            utl::_RefCountBase::_DecStrong(v205[1]);
          if ( v123 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
          utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
          v131 = v199;
          v199 = 0;
          if ( v131 )
            FltReleaseFileNameInformation(v131);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
          goto LABEL_252;
        }
      }
      goto LABEL_578;
    }
    LOBYTE(Object[0]) = 0;
  }
  UnicodeString[0].Buffer = (PWSTR)off_14007E748;
  p_Buffer = &UnicodeString[0].Buffer;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a4, UnicodeString);
  if ( LOBYTE(Object[0]) )
  {
    v135 = v218->FileObject;
    v136 = (v135->Flags & 0x20000) == 0;
    memset(UnicodeString, 0, 0x48u);
    Silo = IoGetSilo(v135);
    NameOptionse = (const char *)a4;
    v138 = UnionFs::Utils::StatItem(&FileNameInformation->Name, v218->Instance, Silo, v136, UnicodeString);
    UnionFs::StackEventTracer::ClearIgnoreStatusCallback((UnionFs::StackEventTracer *)a4);
    if ( v138 != -1073741766 && v138 != -1073741772 )
    {
      if ( !v200 )
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x400) != 0
          && (qword_14009E190 & 0x400) == qword_14009E190 )
        {
          LODWORD(v204) = 1858;
          v203 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
          v206 = (utl::_RefCountBase *)"UnionFs::PreSetHardLink";
          *(_QWORD *)v211 = "Attempting superseding hard link without flag.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            1024,
            (unsigned int)byte_140096DC3,
            v139,
            (_DWORD)v134,
            (__int64)v211,
            (__int64)&v206,
            (__int64)&v203,
            (__int64)&v204);
        }
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000035LL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x49A000B0746LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "ORIGIN: Hard link collision",
          NameOptionse);
        wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v215);
LABEL_440:
        if ( v123 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v154 = v199;
        v199 = 0;
        if ( v154 )
          FltReleaseFileNameInformation(v154);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
        v155 = FileNameInformation;
        FileNameInformation = 0;
        if ( v155 )
          FltReleaseFileNameInformation(v155);
        return 3221225525LL;
      }
LABEL_578:
      v213 = 0;
      wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
      if ( v205[1] )
        utl::_RefCountBase::_DecStrong(v205[1]);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v215);
      if ( v123 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
      goto LABEL_583;
    }
    v121 = (utl::_RefCountBase *)v203;
  }
  v140 = v201;
  v209 = 0;
  if ( v201 )
  {
    v203 = 0;
    v148 = 0;
    v149 = 0;
    LODWORD(v204) = 0;
    v151 = 0;
    goto LABEL_429;
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&v203);
  v141 = v203;
  if ( !v203 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x40C000B06AALL,
      (unsigned __int64)"UnionFs::PreSetHardLink",
      "ORIGIN: Allocating findAndStatResults",
      NameOptionse);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
    wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
    if ( v205[1] )
      utl::_RefCountBase::_DecStrong(v205[1]);
    if ( v125 )
    {
      ExReleaseResourceLite(v125);
      KeLeaveCriticalRegion();
    }
    if ( v123 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
    utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
    v142 = v199;
    v199 = 0;
    if ( v142 )
      FltReleaseFileNameInformation(v142);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
    if ( v31 )
      utl::_RefCountBase::_DecStrong(v31);
    goto LABEL_399;
  }
  NameOptionse = (const char *)a4;
  *((_QWORD *)v203 + 12) = &v209;
  *(struct _UNICODE_STRING *)RetFileNameInformation = *v32;
  v144 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(
           v238[0],
           &FileNameInformation->Name,
           RetFileNameInformation,
           1,
           v141);
  LODWORD(v204) = v144;
  if ( v144 >= 0 )
  {
    v148 = (volatile signed __int32 *)v141[11];
    v149 = *(_WORD *)v141;
    v150 = (void *)v141[10];
    LODWORD(v204) = *(unsigned __int16 *)v141;
    v203 = v150;
    if ( v148 )
      _InterlockedIncrement(v148 + 2);
    v151 = *((_DWORD *)v141 + 16);
    LODWORD(Object[0]) = v151;
    if ( v141 )
    {
      v152 = (utl::_RefCountBase *)v141[11];
      if ( v152 )
        utl::_RefCountBase::_DecStrong(v152);
      ExFreePoolWithTag(v141, 0);
      v149 = (__int16)v204;
      v151 = (int)Object[0];
    }
    if ( v149 != 1 )
      goto LABEL_451;
    v140 = v201;
LABEL_429:
    if ( !v200 )
    {
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x400) != 0
        && (qword_14009E190 & 0x400) == qword_14009E190 )
      {
        LODWORD(v204) = 1730;
        v203 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
        v206 = (utl::_RefCountBase *)"UnionFs::PreSetHardLink";
        *(_QWORD *)v211 = "Denying attempted superseding hard link without flag.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          1024,
          (unsigned int)byte_140096C75,
          v151,
          (_DWORD)v134,
          (__int64)v211,
          (__int64)&v206,
          (__int64)&v203,
          (__int64)&v204);
      }
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000035LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x462000B06C6LL,
        (unsigned __int64)"UnionFs::PreSetHardLink",
        "ORIGIN: Hard link collision",
        NameOptionse);
      if ( v148 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
      wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
      if ( v205[1] )
        utl::_RefCountBase::_DecStrong(v205[1]);
      if ( v215 )
        FsFltWil::Details::ReleaseResource(v215, v153);
      goto LABEL_440;
    }
    if ( v140 || v149 == 1 )
    {
      if ( (*((_DWORD *)v238[0] + 6) & 0x80u) != 0 )
      {
        LOBYTE(Object[0]) = 0;
        if ( v140 )
        {
          v157 = UnionFs::Utils::IsFileCowable(
                   (UnionFs::Utils *)Object,
                   (bool *)v121,
                   (struct UnionFs::UfsPathCachePayload *)a4,
                   v134);
          DestinationFileNameInformation = v157;
          if ( v157 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v157,
              (int)a4,
              (struct UnionFs::StackEventTracer *)0x78F000B06D6LL,
              (unsigned __int64)"UnionFs::PreSetHardLink",
              "PUSH: Checking immutability",
              NameOptionse);
            goto LABEL_458;
          }
          v160 = (char)Object[0];
        }
        else
        {
          v160 = (v151 & 0x800010) != 0;
        }
        if ( !v160 )
        {
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x400000000000LL) != 0
            && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
          {
            v203 = (PVOID)1;
            v206 = (utl::_RefCountBase *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)byte_140096E01,
              v151,
              (unsigned int)&v206,
              (__int64)&v203);
          }
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000022LL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x790000B06E8LL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "ORIGIN: Rejecting COW for immutable hardlink destination",
            NameOptionse);
          if ( v148 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
          wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
          if ( v205[1] )
            utl::_RefCountBase::_DecStrong(v205[1]);
          if ( v215 )
            FsFltWil::Details::ReleaseResource(v215, v161);
          if ( v123 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
          utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
          v162 = v199;
          v199 = 0;
          if ( v162 )
            FltReleaseFileNameInformation(v162);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
          if ( v31 )
            utl::_RefCountBase::_DecStrong(v31);
          goto LABEL_490;
        }
      }
LABEL_452:
      *(_OWORD *)RetFileNameInformation = 0;
      *(struct _UNICODE_STRING *)Object = *v32;
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
          (struct UnionFs::StackEventTracer *)0x3AF000B06F7LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Getting relative path",
          NameOptionse);
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)RetFileNameInformation, v156);
LABEL_458:
        if ( v148 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
        wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        if ( v215 )
          FsFltWil::Details::ReleaseResource(v215, v158);
        if ( v123 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v159 = v199;
        v199 = 0;
        if ( v159 )
          FltReleaseFileNameInformation(v159);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        goto LABEL_508;
      }
      Object[0] = 0;
      DestinationFileNameInformation = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(
                                         (_DWORD)v206,
                                         v218->FileObject,
                                         (_DWORD)v32,
                                         (unsigned int)RetFileNameInformation,
                                         (__int64)v217,
                                         (__int64)Object,
                                         (__int64)a4);
      if ( DestinationFileNameInformation < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B0000B0707LL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Creating handle context",
          NameOptionsf);
        if ( Object[0] )
          FltReleaseContext(Object[0]);
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)RetFileNameInformation, v164);
        if ( v148 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
        wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        if ( v215 )
          FsFltWil::Details::ReleaseResource(v215, v165);
        if ( v123 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v166 = v199;
        v199 = 0;
        if ( v166 )
          FltReleaseFileNameInformation(v166);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
        if ( v31 )
          utl::_RefCountBase::_DecStrong(v31);
        goto LABEL_508;
      }
      UnionFs::UfsPathName::UfsPathName(
        (UnionFs::UfsPathName *)UnicodeString,
        &FileNameInformation->Name,
        FileNameInformation->Volume.Length);
      v167 = v238[0];
      if ( v201 )
      {
        v168 = (volatile signed __int32 *)*((_QWORD *)v121 + 5);
        v169 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v121 + 4);
        v206 = (utl::_RefCountBase *)v168;
        if ( v168 )
          _InterlockedIncrement(v168 + 2);
        v210 = 1;
      }
      else
      {
        v169 = (const struct UnionFs::UfsLayerCtx *)v203;
        v206 = v222;
      }
      v170 = Object[0];
      DestinationFileNameInformation = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                                         v167,
                                         v217,
                                         v218,
                                         FileNameInformation,
                                         (const struct UnionFs::UfsPathName *)UnicodeString,
                                         (const struct UnionFs::UfsStreamHandleCtx *)Object[0],
                                         v169,
                                         (struct UnionFs::StackEventTracer *)a4,
                                         0);
      if ( (v210 & 1) != 0 )
      {
        v210 &= ~1u;
        if ( v206 )
          utl::_RefCountBase::_DecStrong(v206);
      }
      if ( DestinationFileNameInformation < 0 )
      {
        if ( DestinationFileNameInformation == -1073741766 || DestinationFileNameInformation == -1073741772 )
          MicrosoftTelemetryAssertTriggeredMsgKM("Path should exist");
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)DestinationFileNameInformation,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3E8000B071CLL,
          (unsigned __int64)"UnionFs::PreSetHardLink",
          "PUSH: Preparing for COW",
          NameOptionsg);
        if ( !LOBYTE(UnicodeString[1].Length) )
          UnicodeString[0] = 0;
        FsFltWil::Details::FreeUnicodeString(UnicodeString, v172);
        if ( v170 )
          FltReleaseContext(v170);
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)RetFileNameInformation, v173);
        if ( v148 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
        wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
        if ( v205[1] )
          utl::_RefCountBase::_DecStrong(v205[1]);
        if ( v215 )
          FsFltWil::Details::ReleaseResource(v215, v174);
        if ( v123 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
        utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
        v175 = v199;
        v199 = 0;
        if ( v175 )
          FltReleaseFileNameInformation(v175);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
        goto LABEL_170;
      }
      v176 = v201;
      if ( v201 || (_WORD)v204 == 1 )
      {
        *(utl::_RefCountBase **)v223 = v238[0];
        v226 = 0;
        v227 = 22;
        v224 = 0;
        *(_OWORD *)v225 = 0;
        if ( v201 )
        {
          if ( v123 )
            _InterlockedIncrement(v123 + 2);
          v177 = v225[0];
          *((_QWORD *)&v224 + 1) = v121;
          v225[0] = (utl::_RefCountBase *)v123;
          if ( v177 )
            utl::_RefCountBase::_DecStrong(v177);
        }
        v178 = v218->Instance;
        if ( v176 )
        {
          v210 |= 2u;
          v179 = (volatile signed __int32 *)*((_QWORD *)v121 + 5);
          v180 = *((_QWORD *)v121 + 6);
          v181 = *((_QWORD *)v121 + 4);
          if ( v179 )
            _InterlockedIncrement(v179 + 2);
        }
        else
        {
          LODWORD(v180) = (_DWORD)v209;
          v179 = (volatile signed __int32 *)v222;
          LODWORD(v181) = (_DWORD)v203;
        }
        v182 = UnionFs::Utils::CopyItem(
                 (_DWORD)v217,
                 v181,
                 v180,
                 (_DWORD)v178,
                 UnicodeString,
                 (__int64)v223,
                 (struct _FILE_OBJECT *)a4,
                 0);
        v171 = (struct _UNICODE_STRING *)v210;
        LODWORD(v204) = v182;
        if ( (v210 & 2) != 0 && v179 )
        {
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v179);
          v182 = (int)v204;
        }
        if ( v182 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v182,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x353000B073ALL,
            (unsigned __int64)"UnionFs::PreSetHardLink",
            "PUSH: Performing COW",
            NameOptionsh);
          if ( v225[0] )
            utl::_RefCountBase::_DecStrong(v225[0]);
          if ( !LOBYTE(UnicodeString[1].Length) )
            UnicodeString[0] = 0;
          FsFltWil::Details::FreeUnicodeString(UnicodeString, v183);
          if ( v170 )
            FltReleaseContext(v170);
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)RetFileNameInformation, v184);
          if ( v148 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
          wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
          if ( v205[1] )
            utl::_RefCountBase::_DecStrong(v205[1]);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v215);
          if ( v123 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
          utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
          v185 = v199;
          v199 = 0;
          if ( v185 )
            FltReleaseFileNameInformation(v185);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
          if ( v31 )
            utl::_RefCountBase::_DecStrong(v31);
          goto LABEL_417;
        }
        if ( v225[0] )
          utl::_RefCountBase::_DecStrong(v225[0]);
      }
      if ( !LOBYTE(UnicodeString[1].Length) )
        UnicodeString[0] = 0;
      FsFltWil::Details::FreeUnicodeString(UnicodeString, v171);
      if ( v170 )
        FltReleaseContext(v170);
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)RetFileNameInformation, v186);
LABEL_575:
      if ( v148 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
      goto LABEL_578;
    }
LABEL_451:
    if ( v149 != 3 )
      goto LABEL_575;
    goto LABEL_452;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v144,
    (int)a4,
    (struct UnionFs::StackEventTracer *)0x3B3000B06B6LL,
    (unsigned __int64)"UnionFs::PreSetHardLink",
    "PUSH: Failed to lookup entry",
    (const char *)a4);
  if ( v141 )
  {
    v145 = (utl::_RefCountBase *)v141[11];
    if ( v145 )
      utl::_RefCountBase::_DecStrong(v145);
    ExFreePoolWithTag(v141, 0);
  }
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v209);
  wil::details::lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___::_lambda_call__lambda_b406326ea4a6bcbc48cbf4d44d9138b0___(&v212);
  if ( v205[1] )
    utl::_RefCountBase::_DecStrong(v205[1]);
  if ( v125 )
  {
    ExReleaseResourceLite(v125);
    KeLeaveCriticalRegion();
  }
  if ( v123 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v123);
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v228);
  utl::unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>::~unique_ptr<UnionFs::LinkContext,utl::default_delete<UnionFs::LinkContext>>(&v202);
  v146 = v199;
  v199 = 0;
  if ( v146 )
    FltReleaseFileNameInformation(v146);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v238);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v240);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v208);
  if ( v31 )
    utl::_RefCountBase::_DecStrong(v31);
LABEL_417:
  UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v219);
  v147 = FileNameInformation;
  FileNameInformation = 0;
  if ( v147 )
    FltReleaseFileNameInformation(v147);
  return (unsigned int)v204;
}

```

## disassembly

```asm
0x140031cfc  push    rbp
0x140031cfe  push    rbx
0x140031cff  push    rsi
0x140031d00  push    rdi
0x140031d01  push    r12
0x140031d03  push    r13
0x140031d05  push    r14
0x140031d07  push    r15
0x140031d09  lea     rbp, [rsp-2C8h]
0x140031d11  sub     rsp, 3C8h
0x140031d18  mov     rax, cs:__security_cookie
0x140031d1f  xor     rax, rsp
0x140031d22  mov     [rbp+300h+var_50], rax
0x140031d29  mov     rax, [rbp+300h+arg_20]
0x140031d30  xor     r14d, r14d
0x140031d33  mov     r13, [rbp+300h+arg_28]
0x140031d3a  mov     r15, rcx
0x140031d3d  mov     [r8], r14
0x140031d40  mov     rdi, rdx
0x140031d43  mov     [rbp+300h+var_350], rax
0x140031d47  mov     r12, r9
0x140031d4a  mov     rax, [rcx+10h]
0x140031d4e  lea     esi, [r14+1]
0x140031d52  mov     [rsp+400h+FileNameInformation], r14
0x140031d57  mov     [rbp+300h+var_2F0], rcx
0x140031d5b  mov     [rbp+300h+var_2C0], r8
0x140031d5f  mov     rcx, [rax+38h]
0x140031d63  lea     rax, [rsp+400h+FileNameInformation]
0x140031d68  mov     [rbp+300h+var_320], rax
0x140031d6c  lea     rax, [rbp+300h+var_320+8]
0x140031d70  mov     [rsp+400h+RetFileNameInformation], rax; RetFileNameInformation
0x140031d75  mov     [rbp+300h+var_2E8], rdx
0x140031d79  mov     eax, [rcx+10h]
0x140031d7c  lea     r9, [rcx+14h]; FileName
0x140031d80  mov     r8, [rcx+8]; RootDirectory
0x140031d84  mov     rdx, [rdx+20h]; FileObject
0x140031d88  mov     [rsp+400h+var_388], rcx
0x140031d8d  mov     rcx, [rdi+18h]; Instance
0x140031d91  mov     [rsp+400h+NameOptions], 1000101h; char *
0x140031d99  mov     [rbp+300h+var_300], r13
0x140031d9d  mov     [rbp+300h+var_348], r14d
0x140031da1  mov     [rbp+300h+var_320+8], r14
0x140031da5  mov     byte ptr [rbp+300h+var_320+10h], sil
0x140031da9  mov     [rsp+400h+FileNameLength], eax; FileNameLength
0x140031dad  call    cs:__imp_FltGetDestinationFileNameInformation
0x140031db4  nop     dword ptr [rax+rax+00h]
0x140031db9  mov     ebx, eax
0x140031dbb  cmp     byte ptr [rbp+300h+var_320+10h], r14b
0x140031dbf  jz      short loc_140031DE3
0x140031dc1  mov     rdx, [rbp+300h+var_320]
0x140031dc5  mov     rcx, [rbp+300h+var_320+8]
0x140031dc9  mov     rax, [rdx]
0x140031dcc  mov     [rdx], rcx
0x140031dcf  test    rax, rax
0x140031dd2  jz      short loc_140031DE3
0x140031dd4  mov     rcx, rax; FileNameInformation
0x140031dd7  call    cs:__imp_FltReleaseFileNameInformation
0x140031dde  nop     dword ptr [rax+rax+00h]
0x140031de3  test    ebx, ebx
0x140031de5  jns     short loc_140031E30
0x140031de7  lea     rax, aApiGettingDest_0; "API: Getting destination file name info"...
0x140031dee  mov     r8, 39B000B04C1h; struct UnionFs::StackEventTracer *
0x140031df8  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140031dff  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140031e04  mov     rdx, r12; int
0x140031e07  mov     ecx, ebx; this
0x140031e09  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140031e0e  mov     rcx, [rsp+400h+FileNameInformation]; FileNameInformation
0x140031e13  mov     [rsp+400h+FileNameInformation], r14
0x140031e18  test    rcx, rcx
0x140031e1b  jz      short loc_140031E29
0x140031e1d  call    cs:__imp_FltReleaseFileNameInformation
0x140031e24  nop     dword ptr [rax+rax+00h]
0x140031e29  mov     eax, ebx
0x140031e2b  jmp     loc_1400348CB
0x140031e30  mov     rdx, [rdi+20h]
0x140031e34  lea     r8, [rsp+400h+var_390]
0x140031e39  mov     rcx, [rdi+18h]
0x140031e3d  mov     r9, r12
0x140031e40  mov     [rsp+400h+var_390], r14
0x140031e45  mov     qword ptr [rsp+400h+FileNameLength], r14
0x140031e4a  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x140031e4f  mov     ebx, eax
0x140031e51  test    eax, eax
0x140031e53  jns     short loc_140031E7E
0x140031e55  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x140031e5c  mov     r8, 39C000B04CAh; struct UnionFs::StackEventTracer *
0x140031e66  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140031e6d  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140031e72  mov     rdx, r12; int
0x140031e75  mov     ecx, ebx; this
0x140031e77  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140031e7c  jmp     short loc_140031E0E
0x140031e7e  mov     rcx, [rsp+400h+var_390]; this
0x140031e83  test    rcx, rcx
0x140031e86  jnz     short loc_140031E97
0x140031e88  mov     rcx, [rsp+400h+FileNameInformation]
0x140031e8d  mov     [rsp+400h+FileNameInformation], r14
0x140031e92  jmp     loc_1400348B8
0x140031e97  mov     rax, [rdi+20h]
0x140031e9b  xorps   xmm0, xmm0
0x140031e9e  mov     r8, [rsp+400h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x140031ea3  mov     rdx, [rdi+18h]; struct _FLT_INSTANCE *
0x140031ea7  mov     qword ptr [rsp+400h+NameOptions], r12; char *
0x140031eac  mov     r9d, [rax+50h]
0x140031eb0  lea     rax, [rbp+300h+var_2E0]
0x140031eb4  shr     r9d, 11h
0x140031eb8  not     r9b
0x140031ebb  mov     [rbp+300h+var_2E0], rsi
0x140031ebf  and     r9b, sil; bool
0x140031ec2  mov     [rbp+300h+P], r14
0x140031ec6  movdqu  xmmword ptr [rbp+300h+var_2D8], xmm0
0x140031ecb  mov     qword ptr [rsp+400h+FileNameLength], rax; struct UnionFs::LookupScratchRootResults *
0x140031ed0  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x140031ed5  mov     esi, eax
0x140031ed7  test    eax, eax
0x140031ed9  jns     loc_140031F64
0x140031edf  lea     rax, aPushLookingUpS; "PUSH: Looking up scratch root"
0x140031ee6  mov     r8, 39D000B04DCh; struct UnionFs::StackEventTracer *
0x140031ef0  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140031ef7  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140031efc  mov     rdx, r12; int
0x140031eff  mov     ecx, esi; this
0x140031f01  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140031f06  mov     rbx, [rbp+300h+P]
0x140031f0a  test    rbx, rbx
0x140031f0d  jz      short loc_140031F34
0x140031f0f  cmp     [rbx+10h], r14b
0x140031f13  jnz     short loc_140031F1B
0x140031f15  xorps   xmm0, xmm0
0x140031f18  movups  xmmword ptr [rbx], xmm0
0x140031f1b  mov     rcx, rbx; UnicodeString
0x140031f1e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140031f23  xor     edx, edx; Tag
0x140031f25  mov     rcx, rbx; P
0x140031f28  call    cs:__imp_ExFreePoolWithTag
0x140031f2f  nop     dword ptr [rax+rax+00h]
0x140031f34  mov     rcx, [rbp+300h+var_2D8+8]; this
0x140031f38  test    rcx, rcx
0x140031f3b  jz      short loc_140031F42
0x140031f3d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140031f42  mov     rcx, [rsp+400h+FileNameInformation]; FileNameInformation
0x140031f47  mov     [rsp+400h+FileNameInformation], r14
0x140031f4c  test    rcx, rcx
0x140031f4f  jz      short loc_140031F5D
0x140031f51  call    cs:__imp_FltReleaseFileNameInformation
0x140031f58  nop     dword ptr [rax+rax+00h]
0x140031f5d  mov     eax, esi
0x140031f5f  jmp     loc_1400348CB
0x140031f64  mov     rbx, [rbp+300h+var_2D8+8]
0x140031f68  xor     eax, eax
0x140031f6a  mov     rdi, [rbp+300h+var_2D8]
0x140031f6e  mov     r14, rbx
0x140031f71  mov     [rbp+300h+var_370], rdi
0x140031f75  test    rbx, rbx
0x140031f78  jz      short loc_140031F7E
0x140031f7a  lock inc dword ptr [rbx+8]
0x140031f7e  mov     rsi, [rbp+300h+P]
0x140031f82  lea     rcx, [rbp+300h+var_158]; void *
0x140031f89  xorps   xmm0, xmm0
0x140031f8c  mov     [rbp+300h+var_358], rsi
0x140031f90  xor     edx, edx; Val
0x140031f92  mov     [rbp+300h+P], rax
0x140031f96  mov     r8d, 88h; Size
0x140031f9c  mov     [rbp+300h+var_158], rax
0x140031fa3  movdqu  xmmword ptr [rbp+300h+var_168], xmm0
0x140031fab  mov     [rbp+300h+var_150], al
0x140031fb1  mov     [rbp+300h+var_D8], rax
0x140031fb8  call    memset
0x140031fbd  xor     ecx, ecx
0x140031fbf  test    r13, r13
0x140031fc2  jz      short loc_14003200F
0x140031fc4  lea     rdx, [rbp+300h+var_320]
0x140031fc8  mov     rcx, r13
0x140031fcb  call    ?TryGetScratchLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@$$CBVUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(void)
0x140031fd0  mov     r8, r12; struct UnionFs::StackEventTracer *
0x140031fd3  lea     rdx, [rbp+300h+var_168]; struct UnionFs::UfsUnionCtxWithRundown *
0x140031fda  mov     rcx, [rax]; this
0x140031fdd  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140031fe2  mov     rcx, [rbp+300h+var_320+8]; this
0x140031fe6  test    rcx, rcx
0x140031fe9  jz      short loc_140031FF0
0x140031feb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140031ff0  xor     ecx, ecx
0x140031ff2  cmp     [rbp+300h+var_168], rcx
0x140031ff9  jnz     short loc_14003200F
0x140031ffb  mov     [r12], ecx
0x140031fff  mov     r13d, ecx
0x140032002  mov     [r12+224h], cx
0x14003200b  mov     [rbp+300h+var_300], rcx
0x14003200f  xorps   xmm0, xmm0
0x140032012  mov     [rbp+300h+var_1F0], rcx
0x140032019  mov     [rbp+300h+var_1E8], cl
0x14003201f  xor     edx, edx; Val
0x140032021  mov     [rbp+300h+var_170], rcx
0x140032028  mov     r8d, 88h; Size
0x14003202e  lea     rcx, [rbp+300h+var_1F0]; void *
0x140032035  movdqu  xmmword ptr [rbp+300h+var_200], xmm0
0x14003203d  call    memset
0x140032042  test    rdi, rdi
0x140032045  jz      short loc_14003208C
0x140032047  mov     r8, r12; struct UnionFs::StackEventTracer *
0x14003204a  lea     rdx, [rbp+300h+var_200]; struct UnionFs::UfsUnionCtxWithRundown *
0x140032051  mov     rcx, rdi; this
0x140032054  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140032059  cmp     [rbp+300h+var_200], 0
0x140032061  jnz     short loc_14003208C
0x140032063  xor     eax, eax
0x140032065  mov     dword ptr [r12], 0
0x14003206d  mov     [r12+224h], ax
0x140032076  test    rbx, rbx
0x140032079  jz      short loc_140032083
0x14003207b  mov     rcx, rbx; this
0x14003207e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032083  xor     edi, edi
0x140032085  mov     [rbp+300h+var_370], rdi
0x140032089  xor     r14d, r14d
0x14003208c  test    r13, r13
0x14003208f  jnz     loc_14003225A
0x140032095  xor     r15d, r15d
0x140032098  test    rdi, rdi
0x14003209b  jnz     loc_14003215E
0x1400320a1  lea     rcx, [rbp+300h+var_1F0]; this
0x1400320a8  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400320ad  mov     rcx, [rbp+300h+var_170]
0x1400320b4  test    rcx, rcx
0x1400320b7  jz      short loc_1400320C5
0x1400320b9  mov     rax, [rcx]
0x1400320bc  mov     rax, [rax+18h]
0x1400320c0  call    _guard_dispatch_icall
0x1400320c5  mov     rcx, [rbp+300h+var_200+8]; this
0x1400320cc  test    rcx, rcx
0x1400320cf  jz      short loc_1400320D6
0x1400320d1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400320d6  lea     rcx, [rbp+300h+var_158]; this
0x1400320dd  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400320e2  mov     rcx, [rbp+300h+var_D8]
0x1400320e9  test    rcx, rcx
0x1400320ec  jz      short loc_1400320FA
0x1400320ee  mov     rax, [rcx]
0x1400320f1  mov     rax, [rax+18h]
0x1400320f5  call    _guard_dispatch_icall
0x1400320fa  mov     rcx, [rbp+300h+var_168+8]; this
0x140032101  test    rcx, rcx
0x140032104  jz      short loc_14003210B
0x140032106  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003210b  test    rsi, rsi
0x14003210e  jz      short loc_140032135
0x140032110  cmp     [rsi+10h], r15b
0x140032114  jnz     short loc_14003211C
0x140032116  xorps   xmm0, xmm0
0x140032119  movups  xmmword ptr [rsi], xmm0
0x14003211c  mov     rcx, rsi; UnicodeString
0x14003211f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140032124  xor     edx, edx; Tag
0x140032126  mov     rcx, rsi; P
0x140032129  call    cs:__imp_ExFreePoolWithTag
0x140032130  nop     dword ptr [rax+rax+00h]
0x140032135  test    r14, r14
0x140032138  jz      short loc_140032142
0x14003213a  mov     rcx, r14; this
0x14003213d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140032142  test    rbx, rbx
0x140032145  jz      short loc_14003214F
0x140032147  mov     rcx, rbx; this
0x14003214a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003214f  mov     rcx, [rsp+400h+FileNameInformation]
0x140032154  mov     [rsp+400h+FileNameInformation], r15
0x140032159  jmp     loc_1400348B8
0x14003215e  lea     rax, aOriginSourceNo; "ORIGIN: Source not in a union, destinat"...
0x140032165  mov     edi, 0C0ED0003h
0x14003216a  mov     ecx, edi; this
0x14003216c  mov     qword ptr [rsp+400h+FileNameLength], rax; char *
0x140032171  lea     r9, aUnionfsPreseth; "UnionFs::PreSetHardLink"
0x140032178  mov     r8, 5ED000B050Fh; struct UnionFs::StackEventTracer *
0x140032182  mov     rdx, r12; int
0x140032185  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003218a  lea     rcx, [rbp+300h+var_1F0]; this
0x140032191  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140032196  mov     rcx, [rbp+300h+var_170]
0x14003219d  test    rcx, rcx
0x1400321a0  jz      short loc_1400321AE
0x1400321a2  mov     rax, [rcx]
0x1400321a5  mov     rax, [rax+18h]
0x1400321a9  call    _guard_dispatch_icall
0x1400321ae  mov     rcx, [rbp+300h+var_200+8]; this
0x1400321b5  test    rcx, rcx
0x1400321b8  jz      short loc_1400321BF
0x1400321ba  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400321bf  lea     rcx, [rbp+300h+var_158]; this
0x1400321c6  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400321cb  mov     rcx, [rbp+300h+var_D8]
0x1400321d2  test    rcx, rcx
0x1400321d5  jz      short loc_1400321E3
0x1400321d7  mov     rax, [rcx]
0x1400321da  mov     rax, [rax+18h]
0x1400321de  call    _guard_dispatch_icall
0x1400321e3  mov     rcx, [rbp+300h+var_168+8]; this
0x1400321ea  test    rcx, rcx
0x1400321ed  jz      short loc_1400321F4
  ... truncated ...
```
