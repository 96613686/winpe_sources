# UnionFs::UfsPathTable::InsertPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,utl::pair<utl::shared_ptr<UnionFs::UfsPathTree>,ushort> *,UnionFs::InsertOptionalParams *)

- ea: `0x140048244`
- end: `0x14004c610`
- name: `?InsertPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAU?$pair@V?$shared_ptr@VUfsPathTree@UnionFs@@@utl@@G@6@PEAUInsertOptionalParams@2@@Z`
- size: `17356`
- prototype: ``
- caller_count: `3`
- callee_count: `55`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140048078`
- `0x14004c620`
- `0x14004df10`

## callees

- `0x140001c08`
- `0x1400029d0`
- `0x140003060`
- `0x140005d20`
- `0x140005d5c`
- `0x140005d9c`
- `0x140005e10`
- `0x14000696c`
- `0x1400069b4`
- `0x14000f81c`
- `0x1400112c8`
- `0x140020118`
- `0x140035b64`
- `0x140035da8`
- `0x140035df8`
- `0x140035f34`
- `0x140044b40`
- `0x140044fe0`
- `0x140045218`
- `0x1400452f8`
- `0x140045404`
- `0x140045534`
- `0x1400456e0`
- `0x140045878`
- `0x1400458fc`
- `0x1400459f8`
- `0x140045a50`
- `0x140045d40`
- `0x140045dd4`
- `0x140046194`
- `0x1400462b4`
- `0x140046318`
- `0x140046648`
- `0x140047f5c`
- `0x140048244`
- `0x14004e748`
- `0x14004e914`
- `0x14004f454`
- `0x14004f62c`
- `0x14004f6a8`
- `0x14004f754`
- `0x140056c44`
- `0x140056c7c`
- `0x140079404`
- `0x140079528`
- `0x140079c90`
- `0x140079d8c`
- `0x140079e1c`
- `0x140079f68`
- `0x14007a0ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140048414`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048668`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048715`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048896`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c452`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c4cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c54f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c5c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048414`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048668`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048715`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048896`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c452`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c4cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c54f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c5c4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004891b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004891b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004929f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400492c0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004ba30`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004ba55`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004929f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400492c0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004ba30`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004ba55`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004846d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048522`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048632`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004877f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048860`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048b81`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048bfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048df0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048e3a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048e67`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049139`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400499d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c31`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049cd1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049d53`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049db0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049e32`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049f12`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c01e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c224`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c31b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c39f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c497`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c58e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004846d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048522`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048632`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004877f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048860`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048b81`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048bfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c41`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048df0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048e3a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048e67`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049139`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400499d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c31`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049cd1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049d53`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049db0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049e32`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049f12`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c01e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c224`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c31b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c39f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c497`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c58e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048479`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004852e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004863e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004878b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004886c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048b8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048dfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048e46`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048e73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049145`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400499de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c92`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049cdd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049d5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049dbc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049e3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049e9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049f1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c02a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c230`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c327`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c3ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c4a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c59a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048479`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004852e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004863e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004878b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004886c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048b8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048dfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048e46`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048e73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049145`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400499de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c92`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049cdd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049d5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049dbc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049e3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049e9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049f1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c02a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c230`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c327`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c3ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c4a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c59a`
- `FLTMGR!FltReleaseContext` at `0x1400485da`
- `FLTMGR!FltReleaseContext` at `0x1400486fc`
- `FLTMGR!FltReleaseContext` at `0x14004c536`
- `FLTMGR!FltReleaseContext` at `0x1400485da`
- `FLTMGR!FltReleaseContext` at `0x1400486fc`
- `FLTMGR!FltReleaseContext` at `0x14004c536`

## string_xrefs

- `0x14004a123`: `UnionFs::UfsPathTierNode::ConvertFinalNodeToInner`
- `0x14004a15b`: `UnionFs::UfsPathTierNode::ConvertFinalNodeToInner`
- `0x140048316`: `UnionFs::UfsPathTable::InsertPriv`
- `0x1400483d8`: `UnionFs::UfsPathTable::InsertPriv`
- `0x1400484d4`: `UnionFs::UfsPathTable::InsertPriv`
- `0x1400485aa`: `UnionFs::UfsPathTable::InsertPriv`
- `0x140048724`: `UnionFs::UfsPathTable::InsertPriv`
- `0x14004c504`: `UnionFs::UfsPathTable::InsertPriv`
- `0x1400483c7`: `PUSH: Could not get short names for path`
- `0x1400484c3`: `ORIGIN: Table already run down`
- `0x140048807`: `ORIGIN: Table already run down`
- `0x140048d73`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140048f40`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004907a`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140049946`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004a6bc`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004a894`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004a98e`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b022`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b1d1`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b2aa`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b533`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004beb2`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004c115`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140049951`: `Preventing insert of metadata path into path table`
- `0x14004896b`: `moreComponentsLeft == moreShortComponentsLeft`
- `0x14004949a`: `moreComponentsLeft == moreShortComponentsLeft`
- `0x14004bc8a`: `moreComponentsLeft == moreShortComponentsLeft`
- `0x140049a8b`: `PUSH: One or more payload nodes already exist in the table.`
- `0x140049ba8`: `ORIGIN: \ is already a mapping.`
- `0x140049d7d`: `PUSH: InsertCallback in PathTable.`
- `0x14004a016`: `PUSH: InsertCallback in PathTable.`
- `0x14004a2bc`: `PUSH: InsertCallback in PathTable.`
- `0x14004ad0a`: `PUSH: InsertCallback in PathTable.`
- `0x140048d81`: `Inserted payload (replaced invalid volume root)`
- `0x140048f4e`: `Inserted payload (replaced invalid volume root)`
- `0x140049e5b`: `ORIGIN: Root node already owned by a union`
- `0x1400491af`: `PUSH: Adding subtree to path tree node`
- `0x14004aa7c`: `PUSH: Adding subtree to path tree node`
- `0x14004b645`: `PUSH: Adding subtree to path tree node`
- `0x14004ab5f`: `PUSH: Updating stored path length`
- `0x14004b68c`: `PUSH: Updating stored path length`
- `0x14004bdad`: `PUSH: Updating stored path length`
- `0x14004c1a4`: `PUSH: Updating stored path length`
- `0x14004b8d0`: `ORIGIN: Incoming path has an existing short component.`
- `0x14004ac27`: `ORIGIN: Attempted insert of root on already-owned node`
- `0x14004b76c`: `ORIGIN: Attempted insert of root on already-owned node`
- `0x14004a6ca`: `Inserted payload (replaced invalid)`
- `0x14004a8a2`: `Inserted payload (replaced invalid)`
- `0x14004acd4`: `ORIGIN: Path is already in table`
- `0x14004b6b5`: `ORIGIN: Attempted insert into union root node`
- `0x14004b395`: `ORIGIN: Node already has payload`
- `0x14004a0f2`: `PUSH: Payload node already exists along this path, nested paths not allowed.`
- `0x14004bd15`: `PUSH: Could not create new path node.`
- `0x14004ba05`: `curInsertNode->IsFinal() || moreComponentsLeft || nextLevelTree`
- `0x14004bad5`: `PUSH: Could not create new short name path node.`
- `0x14004bbd1`: `!curInsertNode->IsFinal()`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::InsertPriv(
        int *a1,
        FsFltWil::Details *a2,
        UnionFs::Utils *a3,
        __int64 *a4,
        _DWORD *a5,
        struct UnionFs::StackEventTracer *a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9)
{
  _DWORD *v9; // r13
  const struct UnionFs::UfsUnionCtx **v12; // rax
  __m128i v14; // xmm6
  volatile signed __int32 *v15; // rdi
  FsFltWil::Details *v16; // rcx
  int v17; // eax
  int v18; // eax
  struct _UNICODE_STRING *v19; // rsi
  int ShortNameCopy; // esi
  struct _UNICODE_STRING *v21; // rdx
  struct _UNICODE_STRING *v22; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v23; // rdx
  UnionFs::UfsInstanceTierNode *v24; // rdx
  unsigned __int16 v25; // r9
  struct FsFltWil::Details::RundownRefCacheAware *v26; // rdx
  struct _UNICODE_STRING *v27; // rdx
  struct _ERESOURCE *v28; // rcx
  bool v29; // zf
  __int64 **v30; // r15
  __int64 **i; // rax
  const struct std::nothrow_t *v32; // rdx
  int v33; // r12d
  struct FsFltWil::Details::RundownRefCacheAware *v34; // rdx
  PVOID v35; // rbx
  void *v36; // rcx
  struct _UNICODE_STRING *v37; // rdx
  struct _ERESOURCE *v38; // rcx
  bool v39; // zf
  __int64 ***v40; // rax
  _QWORD *v41; // r14
  __int64 **v42; // rcx
  __int64 **v43; // rcx
  __int64 *v44; // rcx
  const char *v45; // rcx
  void *v46; // rcx
  char v47; // r12
  const char *v48; // r12
  struct _ERESOURCE *v49; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v50; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v51; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v52; // rdx
  struct _ERESOURCE *v53; // rcx
  struct _UNICODE_STRING *v54; // r8
  int v55; // r9d
  bool v56; // r15
  BOOLEAN v57; // al
  int v58; // r8d
  struct FsFltWil::Details::RundownRefCacheAware *v59; // rdx
  int v60; // eax
  struct _UNICODE_STRING *Buffer_low; // r8
  bool v62; // r15
  struct UnionFs::UfsPathTierNode *v63; // r12
  __int64 v64; // r8
  UnionFs::UfsPathTree *v65; // rcx
  utl::_RefCountBase *v66; // r8
  unsigned int v67; // r9d
  bool IsEmpty; // r15
  int inited; // r15d
  volatile signed __int32 *v70; // r15
  struct UnionFs::UfsPathTierNode *v71; // rcx
  volatile signed __int32 *v72; // r12
  int v73; // ecx
  struct _ERESOURCE *v74; // rcx
  struct _ERESOURCE *v75; // rcx
  struct _ERESOURCE **v76; // rax
  struct _ERESOURCE *v77; // rcx
  struct _ERESOURCE *v78; // rax
  struct _ERESOURCE *v79; // rcx
  struct UnionFs::UfsPathTierNode *v80; // r8
  __int64 *v81; // r12
  __int64 v82; // rax
  int v83; // r8d
  int v84; // r9d
  const struct _UNICODE_STRING *v85; // rax
  struct _ERESOURCE *v86; // rcx
  struct _ERESOURCE **v87; // rax
  struct _ERESOURCE *v88; // rcx
  struct _ERESOURCE *v89; // rax
  struct _ERESOURCE *v90; // rcx
  __int64 *v91; // r12
  __int64 v92; // rax
  int v93; // r8d
  int v94; // r9d
  const struct _UNICODE_STRING *v95; // rax
  volatile signed __int32 *v96; // rax
  int v97; // r8d
  int v98; // r9d
  const struct _UNICODE_STRING *v99; // rax
  utl::_RefCountBase *v100; // rcx
  struct _ERESOURCE *v101; // rcx
  UnionFs::UfsInstanceTierNode *v102; // r15
  const char *v103; // r15
  __int64 OwningUnion; // rax
  volatile signed __int32 *v105; // rax
  UnionFs::UfsPathTree *v106; // r13
  int v107; // r12d
  const char *v108; // rax
  struct _UNICODE_STRING *v109; // r8
  struct UnionFs::UfsPathTierNode *Node; // r15
  struct UnionFs::UfsPathTierNode *v111; // r13
  char v112; // r15
  __int64 v113; // rcx
  int v114; // r12d
  _BYTE *v115; // r13
  volatile signed __int32 *v116; // r15
  int v117; // eax
  struct _ERESOURCE *v118; // rdx
  FsFltWil::Details *v119; // rcx
  __int64 v120; // rax
  struct _UNICODE_STRING *v121; // r8
  bool v122; // r15
  __int64 v123; // rax
  __int64 *v124; // r12
  volatile signed __int32 *v125; // rax
  UnionFs::UfsPathTree *v126; // rax
  volatile signed __int32 *v127; // rcx
  FsFltWil::Details **v128; // rcx
  _BYTE *v129; // r12
  volatile signed __int32 *v130; // r13
  struct _ERESOURCE *v131; // rdx
  int v132; // eax
  FsFltWil::Details *v133; // rcx
  bool v134; // r15
  utl::_RefCountBase **v135; // rax
  bool v136; // r15
  _BYTE *v137; // r12
  __int64 v138; // rax
  struct _ERESOURCE *v139; // rdx
  int v140; // eax
  _BYTE *v141; // r13
  int v142; // r13d
  const struct _UNICODE_STRING *v143; // rax
  struct _UNICODE_STRING *v144; // rdx
  struct _ERESOURCE *v145; // rcx
  bool v146; // zf
  UnionFs::UfsPathTierNode *m; // rbx
  struct FsFltWil::Details::RundownRefCacheAware *v148; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v149; // rdx
  UnionFs::UfsPathTierNode *k; // rbx
  PVOID v151; // r8
  _QWORD *v152; // rcx
  __int64 v153; // rax
  struct _UNICODE_STRING *v154; // rdx
  struct _ERESOURCE *v155; // rcx
  bool v156; // zf
  struct FsFltWil::Details::RundownRefCacheAware *v157; // rdx
  struct _ERESOURCE *v158; // rcx
  struct _ERESOURCE *v159; // rcx
  PERESOURCE v160; // rax
  utl::_RefCountBase *v161; // rcx
  struct _ERESOURCE *v162; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v163; // rdx
  struct _ERESOURCE *v164; // rcx
  struct _ERESOURCE *v165; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v166; // rdx
  struct _ERESOURCE *v167; // rcx
  struct _ERESOURCE *v168; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v169; // rdx
  struct _UNICODE_STRING *v170; // rdx
  struct _ERESOURCE *v171; // rcx
  _DWORD *v172; // rsi
  FsFltWil::Details **v173; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v174; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v175; // rdx
  int v176; // edx
  const char *v177; // rax
  __int64 v178; // r8
  struct UnionFs::UfsPathTierNode *v179; // rcx
  __int64 v180; // rax
  volatile signed __int32 *v181; // rax
  bool v182; // r15
  struct UnionFs::UfsPathTierNode *v183; // r15
  __int64 *v184; // r12
  struct _ERESOURCE *v185; // rdx
  FsFltWil::Details *v186; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v187; // rdx
  struct _ERESOURCE *v188; // rdx
  FsFltWil::Details *v189; // rcx
  FsFltWil::Details *v190; // rcx
  __int64 v191; // rax
  FsFltWil::Details *v192; // rcx
  _DWORD *v193; // rsi
  struct _ERESOURCE *v194; // rdx
  utl::_RefCountBase *v195; // rcx
  FsFltWil::Details *v196; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v197; // rdx
  struct _ERESOURCE *v198; // rdx
  FsFltWil::Details *v199; // rcx
  __int64 v200; // r8
  struct _ERESOURCE *v201; // rdx
  FsFltWil::Details *v202; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v203; // rdx
  struct _ERESOURCE *v204; // rdx
  FsFltWil::Details *v205; // rcx
  __int64 *v206; // rsi
  __int64 v207; // rax
  int v208; // r8d
  int v209; // r9d
  struct UnionFs::UfsPathTierNode *v210; // r13
  __int64 v211; // rax
  const struct _UNICODE_STRING *v212; // rax
  FsFltWil::Details *v213; // rcx
  __int64 v214; // rax
  struct _ERESOURCE *v215; // rdx
  int v216; // r8d
  int v217; // r9d
  FsFltWil::Details *v218; // rcx
  __int64 *v219; // rsi
  __int64 v220; // rax
  int v221; // r8d
  int v222; // r9d
  struct UnionFs::UfsPathTierNode *v223; // r13
  __int64 v224; // rax
  const struct _UNICODE_STRING *v225; // rax
  const struct _UNICODE_STRING *v226; // rax
  _DWORD *v227; // rsi
  _DWORD *v228; // rcx
  utl::_RefCountBase *v229; // rcx
  struct _ERESOURCE *v230; // rdx
  FsFltWil::Details *v231; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v232; // rdx
  struct _ERESOURCE *v233; // rdx
  FsFltWil::Details *v234; // rcx
  int v235; // eax
  struct _ERESOURCE *v236; // rdx
  FsFltWil::Details *v237; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v238; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v239; // rdx
  struct _ERESOURCE *v240; // rdx
  FsFltWil::Details *v241; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v242; // rdx
  FsFltWil::Details *v243; // rcx
  __int64 v244; // rax
  _DWORD *v245; // rsi
  __int64 v246; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v247; // rdx
  __int64 *v248; // rsi
  __int64 v249; // rax
  int v250; // r8d
  int v251; // r9d
  struct UnionFs::UfsPathTierNode *v252; // r13
  __int64 v253; // rax
  const struct _UNICODE_STRING *v254; // rax
  FsFltWil::Details *v255; // rcx
  __int64 v256; // rax
  int v257; // r8d
  int v258; // r9d
  __int64 *v259; // rsi
  __int64 v260; // rax
  int v261; // r8d
  int v262; // r9d
  struct UnionFs::UfsPathTierNode *v263; // r13
  __int64 v264; // rax
  const struct _UNICODE_STRING *v265; // rax
  const struct _UNICODE_STRING *v266; // rax
  _DWORD *v267; // rsi
  _DWORD *v268; // rcx
  __int64 *v269; // r12
  __int64 v270; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v271; // rdx
  struct UnionFs::UfsPathTierNode *v272; // r13
  __int64 v273; // rax
  int v274; // r8d
  int v275; // r9d
  const struct _UNICODE_STRING *v276; // rax
  struct UnionFs::UfsPathTierNode *v277; // r13
  const char *v278; // r12
  int v279; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v280; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v281; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v282; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v283; // rdx
  struct _ERESOURCE *v284; // rcx
  unsigned __int64 v285; // rcx
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // r8
  unsigned __int64 v289; // rcx
  __int64 v290; // rax
  struct UnionFs::UfsPathTierNode *v291; // r8
  char *v292; // rax
  volatile signed __int32 *v293; // rax
  UnionFs::Utils *v294; // r12
  struct _UNICODE_STRING *v295; // r8
  struct _UNICODE_STRING *v296; // r8
  __int64 v297; // r8
  int v298; // eax
  int v299; // r8d
  int v300; // r9d
  int v301; // eax
  const struct _UNICODE_STRING *v302; // rax
  utl::_RefCountBase *v303; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v304; // rdx
  const struct UnionFs::UfsUnionCtx **v305; // r15
  volatile signed __int32 *v306; // rsi
  __int64 v307; // rdx
  struct UnionFs::UfsPathTierNode *v308; // rcx
  const struct UnionFs::UfsUnionCtx **v309; // rdx
  int v310; // r8d
  int v311; // r9d
  const struct _UNICODE_STRING *v312; // rax
  int updated; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v314; // rdx
  struct _ERESOURCE *v315; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v316; // rdx
  struct _ERESOURCE *v317; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v318; // rdx
  struct _ERESOURCE *v319; // rcx
  UnionFs::UfsPathTierNode *j; // rbx
  PVOID v321; // rcx
  _QWORD *v322; // rdx
  __int64 v323; // rax
  struct _UNICODE_STRING *v324; // rdx
  struct _ERESOURCE *v325; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v326; // rdx
  PVOID v327; // rbx
  void *v328; // rcx
  struct _UNICODE_STRING *v329; // rdx
  struct _ERESOURCE *v330; // rcx
  char *v331; // [rsp+30h] [rbp-D8h]
  __int64 v332; // [rsp+68h] [rbp-A0h] BYREF
  PERESOURCE Resource; // [rsp+70h] [rbp-98h] BYREF
  _BOOL8 v334; // [rsp+78h] [rbp-90h]
  PVOID P; // [rsp+80h] [rbp-88h] BYREF
  bool v336; // [rsp+88h] [rbp-80h]
  struct UnionFs::UfsPathTierNode *v337; // [rsp+90h] [rbp-78h] BYREF
  struct UnionFs::UfsPathTierNode *v338; // [rsp+98h] [rbp-70h] BYREF
  FsFltWil::Details *v339; // [rsp+A0h] [rbp-68h] BYREF
  UnionFs::UfsPathTree *v340; // [rsp+A8h] [rbp-60h] BYREF
  utl::_RefCountBase *v341; // [rsp+B0h] [rbp-58h]
  unsigned int v342; // [rsp+B8h] [rbp-50h] BYREF
  utl::_RefCountBase *v343[2]; // [rsp+C0h] [rbp-48h] BYREF
  PVOID v344[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v345; // [rsp+E0h] [rbp-28h]
  PERESOURCE v346; // [rsp+E8h] [rbp-20h] BYREF
  FsFltWil::Details *v347; // [rsp+F0h] [rbp-18h] BYREF
  const char *v348; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v349[2]; // [rsp+100h] [rbp-8h] BYREF
  char v350; // [rsp+110h] [rbp+8h]
  __int64 *v351; // [rsp+118h] [rbp+10h] BYREF
  int v352; // [rsp+120h] [rbp+18h] BYREF
  struct UnionFs::UfsPathTierNode *v353; // [rsp+128h] [rbp+20h] BYREF
  UnionFs::UfsInstanceTierNode *v354; // [rsp+130h] [rbp+28h] BYREF
  __int128 v355; // [rsp+138h] [rbp+30h] BYREF
  int v356; // [rsp+148h] [rbp+40h] BYREF
  _DWORD *v357; // [rsp+150h] [rbp+48h]
  const struct UnionFs::UfsUnionCtx **v358; // [rsp+158h] [rbp+50h] BYREF
  FsFltWil::Details *v359; // [rsp+160h] [rbp+58h] BYREF
  __int64 v360; // [rsp+168h] [rbp+60h] BYREF
  const struct _UNICODE_STRING *v361; // [rsp+170h] [rbp+68h] BYREF
  UnionFs::Utils *v362; // [rsp+178h] [rbp+70h] BYREF
  int v363; // [rsp+180h] [rbp+78h] BYREF
  UNICODE_STRING String1; // [rsp+188h] [rbp+80h] BYREF
  FsFltWil::Details *v365; // [rsp+198h] [rbp+90h] BYREF
  FsFltWil::Details *v366; // [rsp+1A8h] [rbp+A0h] BYREF
  UNICODE_STRING SourceString; // [rsp+1B8h] [rbp+B0h] BYREF
  PVOID v368; // [rsp+1C8h] [rbp+C0h]
  utl::_RefCountBase *v369; // [rsp+1D0h] [rbp+C8h] BYREF
  __m128i v370; // [rsp+1D8h] [rbp+D0h] BYREF
  int v371; // [rsp+1E8h] [rbp+E0h] BYREF
  const char *v372; // [rsp+1F0h] [rbp+E8h] BYREF
  int v373; // [rsp+1F8h] [rbp+F0h] BYREF
  int v374; // [rsp+1FCh] [rbp+F4h] BYREF
  _QWORD v375[2]; // [rsp+200h] [rbp+F8h] BYREF
  int v376; // [rsp+210h] [rbp+108h] BYREF
  const char *v377; // [rsp+218h] [rbp+110h] BYREF
  struct _ERESOURCE *v378; // [rsp+220h] [rbp+118h] BYREF
  struct _ERESOURCE *v379; // [rsp+228h] [rbp+120h] BYREF
  PERESOURCE v380; // [rsp+230h] [rbp+128h] BYREF
  PERESOURCE v381; // [rsp+238h] [rbp+130h] BYREF
  _QWORD v382[3]; // [rsp+240h] [rbp+138h] BYREF
  __int128 v383; // [rsp+258h] [rbp+150h] BYREF
  PVOID *v384; // [rsp+268h] [rbp+160h] BYREF
  unsigned int v385; // [rsp+270h] [rbp+168h]
  const struct _UNICODE_STRING *v386; // [rsp+278h] [rbp+170h] BYREF
  __int64 v387; // [rsp+280h] [rbp+178h] BYREF
  struct UnionFs::UfsPathTierNode *v388; // [rsp+288h] [rbp+180h] BYREF
  const char *v389; // [rsp+290h] [rbp+188h] BYREF
  char v390[8]; // [rsp+298h] [rbp+190h] BYREF
  const char *v391; // [rsp+2A0h] [rbp+198h] BYREF
  char v392[8]; // [rsp+2A8h] [rbp+1A0h] BYREF
  char v393[8]; // [rsp+2B0h] [rbp+1A8h] BYREF
  const char *v394; // [rsp+2B8h] [rbp+1B0h] BYREF
  const struct _UNICODE_STRING *v395; // [rsp+2C0h] [rbp+1B8h] BYREF
  __int64 v396; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE *v397; // [rsp+2D0h] [rbp+1C8h] BYREF
  const char *v398; // [rsp+2D8h] [rbp+1D0h] BYREF
  const char *v399; // [rsp+2E0h] [rbp+1D8h] BYREF
  const char *v400; // [rsp+2E8h] [rbp+1E0h] BYREF
  const struct _UNICODE_STRING *v401; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int64 v402; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE *v403; // [rsp+300h] [rbp+1F8h] BYREF
  const char *v404; // [rsp+308h] [rbp+200h] BYREF
  const char *v405; // [rsp+310h] [rbp+208h] BYREF
  const char *v406; // [rsp+318h] [rbp+210h] BYREF
  const struct _UNICODE_STRING *v407; // [rsp+320h] [rbp+218h] BYREF
  __int64 v408; // [rsp+328h] [rbp+220h] BYREF
  _BYTE *v409; // [rsp+330h] [rbp+228h] BYREF
  const char *v410; // [rsp+338h] [rbp+230h] BYREF
  char v411[8]; // [rsp+340h] [rbp+238h] BYREF
  char v412[8]; // [rsp+348h] [rbp+240h] BYREF
  const struct _UNICODE_STRING *v413; // [rsp+350h] [rbp+248h] BYREF
  __int64 v414; // [rsp+358h] [rbp+250h] BYREF
  const char *v415; // [rsp+360h] [rbp+258h] BYREF
  const char *v416; // [rsp+368h] [rbp+260h] BYREF
  const char *v417; // [rsp+370h] [rbp+268h] BYREF
  char v418[8]; // [rsp+378h] [rbp+270h] BYREF
  const struct _UNICODE_STRING *v419; // [rsp+380h] [rbp+278h] BYREF
  __int64 v420; // [rsp+388h] [rbp+280h] BYREF
  const char *v421; // [rsp+390h] [rbp+288h] BYREF
  const char *v422; // [rsp+398h] [rbp+290h] BYREF
  const char *v423; // [rsp+3A0h] [rbp+298h] BYREF
  const struct _UNICODE_STRING *v424; // [rsp+3A8h] [rbp+2A0h] BYREF
  __int64 v425; // [rsp+3B0h] [rbp+2A8h] BYREF
  _BYTE *v426; // [rsp+3B8h] [rbp+2B0h] BYREF
  const char *v427; // [rsp+3C0h] [rbp+2B8h] BYREF
  const char *v428; // [rsp+3C8h] [rbp+2C0h] BYREF
  const char *v429; // [rsp+3D0h] [rbp+2C8h] BYREF
  const struct _UNICODE_STRING *v430; // [rsp+3D8h] [rbp+2D0h] BYREF
  __int64 v431; // [rsp+3E0h] [rbp+2D8h] BYREF
  const char *v432; // [rsp+3E8h] [rbp+2E0h] BYREF
  char v433[8]; // [rsp+3F0h] [rbp+2E8h] BYREF
  const char *v434; // [rsp+3F8h] [rbp+2F0h] BYREF
  const struct _UNICODE_STRING *v435; // [rsp+400h] [rbp+2F8h] BYREF
  __int64 v436; // [rsp+408h] [rbp+300h] BYREF
  const char *v437; // [rsp+410h] [rbp+308h] BYREF
  const char *v438; // [rsp+418h] [rbp+310h] BYREF
  const char *v439; // [rsp+420h] [rbp+318h] BYREF
  const struct _UNICODE_STRING *v440; // [rsp+428h] [rbp+320h] BYREF
  __int64 v441; // [rsp+430h] [rbp+328h] BYREF
  const char *v442; // [rsp+438h] [rbp+330h] BYREF
  const char *v443; // [rsp+440h] [rbp+338h] BYREF
  const char *v444; // [rsp+448h] [rbp+340h] BYREF
  const struct _UNICODE_STRING *v445; // [rsp+450h] [rbp+348h] BYREF
  __int64 v446; // [rsp+458h] [rbp+350h] BYREF
  struct UnionFs::UfsPathTierNode *v447; // [rsp+460h] [rbp+358h] BYREF
  const char *v448; // [rsp+468h] [rbp+360h] BYREF
  const char *v449; // [rsp+470h] [rbp+368h] BYREF
  const char *v450; // [rsp+478h] [rbp+370h] BYREF
  const struct _UNICODE_STRING *v451; // [rsp+480h] [rbp+378h] BYREF
  __int64 v452; // [rsp+488h] [rbp+380h] BYREF
  struct UnionFs::UfsPathTierNode *v453; // [rsp+490h] [rbp+388h] BYREF
  const char *v454; // [rsp+498h] [rbp+390h] BYREF
  __int64 v455; // [rsp+4A0h] [rbp+398h] BYREF
  utl::_RefCountBase *v456; // [rsp+4A8h] [rbp+3A0h]
  __int128 v457; // [rsp+4B8h] [rbp+3B0h] BYREF
  __int64 v458; // [rsp+4C8h] [rbp+3C0h] BYREF
  utl::_RefCountBase *v459; // [rsp+4D0h] [rbp+3C8h]
  __int128 v460; // [rsp+4D8h] [rbp+3D0h] BYREF
  __int64 v461; // [rsp+4E8h] [rbp+3E0h] BYREF
  utl::_RefCountBase *v462; // [rsp+4F0h] [rbp+3E8h]
  __int128 v463; // [rsp+4F8h] [rbp+3F0h] BYREF
  utl::_RefCountBase *v464[2]; // [rsp+508h] [rbp+400h] BYREF
  const char *v465; // [rsp+518h] [rbp+410h] BYREF
  const char *v466; // [rsp+520h] [rbp+418h] BYREF
  _QWORD v467[2]; // [rsp+528h] [rbp+420h] BYREF
  _QWORD v468[2]; // [rsp+538h] [rbp+430h] BYREF
  _QWORD v469[2]; // [rsp+548h] [rbp+440h] BYREF
  _QWORD v470[2]; // [rsp+558h] [rbp+450h] BYREF
  _QWORD v471[2]; // [rsp+568h] [rbp+460h] BYREF
  _QWORD v472[2]; // [rsp+578h] [rbp+470h] BYREF
  _QWORD v473[2]; // [rsp+588h] [rbp+480h] BYREF
  _QWORD v474[2]; // [rsp+598h] [rbp+490h] BYREF
  _QWORD v475[2]; // [rsp+5A8h] [rbp+4A0h] BYREF
  _QWORD v476[2]; // [rsp+5B8h] [rbp+4B0h] BYREF
  _QWORD v477[2]; // [rsp+5C8h] [rbp+4C0h] BYREF
  _QWORD v478[2]; // [rsp+5D8h] [rbp+4D0h] BYREF
  _QWORD v479[2]; // [rsp+5E8h] [rbp+4E0h] BYREF
  _QWORD v480[2]; // [rsp+5F8h] [rbp+4F0h] BYREF
  _QWORD v481[2]; // [rsp+608h] [rbp+500h] BYREF
  _QWORD v482[2]; // [rsp+618h] [rbp+510h] BYREF
  _QWORD v483[8]; // [rsp+628h] [rbp+520h] BYREF
  _QWORD v484[2]; // [rsp+668h] [rbp+560h] BYREF
  _QWORD v485[2]; // [rsp+678h] [rbp+570h] BYREF
  _QWORD v486[2]; // [rsp+688h] [rbp+580h] BYREF
  char v487[8]; // [rsp+698h] [rbp+590h] BYREF
  utl::_RefCountBase *v488; // [rsp+6A0h] [rbp+598h]
  char v489[8]; // [rsp+6A8h] [rbp+5A0h] BYREF
  utl::_RefCountBase *v490; // [rsp+6B0h] [rbp+5A8h]
  __int128 v491; // [rsp+6B8h] [rbp+5B0h] BYREF
  char v492[8]; // [rsp+6C8h] [rbp+5C0h] BYREF
  utl::_RefCountBase *v493; // [rsp+6D0h] [rbp+5C8h]
  char v494[8]; // [rsp+6D8h] [rbp+5D0h] BYREF
  utl::_RefCountBase *v495; // [rsp+6E0h] [rbp+5D8h]
  char v496[8]; // [rsp+6E8h] [rbp+5E0h] BYREF
  utl::_RefCountBase *v497; // [rsp+6F0h] [rbp+5E8h]
  char v498[8]; // [rsp+6F8h] [rbp+5F0h] BYREF
  utl::_RefCountBase *v499; // [rsp+700h] [rbp+5F8h]
  __int128 v500; // [rsp+708h] [rbp+600h] BYREF
  __m128i v501; // [rsp+718h] [rbp+610h] BYREF
  __m128i v502; // [rsp+728h] [rbp+620h] BYREF
  __m128i v503; // [rsp+738h] [rbp+630h] BYREF
  __int128 v504; // [rsp+748h] [rbp+640h] BYREF
  struct _UNICODE_STRING v505; // [rsp+758h] [rbp+650h] BYREF
  __int64 v506; // [rsp+7D8h] [rbp+6D0h]
  __int64 v507; // [rsp+850h] [rbp+748h]
  _QWORD v508[17]; // [rsp+858h] [rbp+750h] BYREF
  char v509[8]; // [rsp+8E0h] [rbp+7D8h] BYREF
  _QWORD v510[13]; // [rsp+8E8h] [rbp+7E0h] BYREF
  _QWORD *v511; // [rsp+950h] [rbp+848h]
  _BYTE v512[128]; // [rsp+958h] [rbp+850h] BYREF
  __int64 v513; // [rsp+9D8h] [rbp+8D0h]

  v9 = a5;
  v362 = a3;
  v348 = (const char *)a1;
  v342 = 0;
  v365 = a2;
  *a5 = 0;
  v351 = a4;
  v357 = a5;
  v361 = (const struct _UNICODE_STRING *)a8;
  v358 = 0;
  if ( a9 )
  {
    v12 = *(const struct UnionFs::UfsUnionCtx ***)a9;
    v353 = *(struct UnionFs::UfsPathTierNode **)(a9 + 8);
    v358 = v12;
  }
  else
  {
    v353 = 0;
    v12 = 0;
  }
  v356 = a7 & 4;
  if ( (a7 & 4) != 0 && !v12 || v12 && (a7 & 4) == 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC00000E5LL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x4800014005ELL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "ORIGIN: Invalid root insertion parameters",
      v331);
    return 3221225701LL;
  }
  v352 = 0;
  v14 = 0;
  v370 = 0;
  if ( a8 )
  {
    v15 = *(volatile signed __int32 **)(a8 + 8);
    v16 = *(FsFltWil::Details **)a8;
    v366 = *(FsFltWil::Details **)a8;
    if ( v15 )
      _InterlockedIncrement(v15 + 2);
    v17 = *(unsigned __int16 *)(a8 + 16);
    v370.m128i_i64[0] = (__int64)v16;
    v370.m128i_i64[1] = (__int64)v15;
    v14 = _mm_load_si128(&v370);
    v352 = v17;
  }
  else
  {
    v366 = 0;
    v15 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  }
  v18 = *a1;
  v19 = 0;
  P = 0;
  if ( (v18 & 1) != 0 )
  {
    ShortNameCopy = UnionFs::UfsPathName::MakeShortNameCopy(a3, a2, &P, a6);
    if ( ShortNameCopy < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)ShortNameCopy,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xD00140070LL,
        (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
        "PUSH: Could not get short names for path",
        v331);
      v22 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v22, v21);
        ExFreePoolWithTag(v22, 0);
      }
      goto LABEL_21;
    }
    v19 = (struct _UNICODE_STRING *)P;
  }
  Resource = 0;
  if ( (a7 & 1) == 0 )
  {
    FsFltWil::AcquireResourceExclusive(&v378, a1 + 8);
    Resource = v378;
    v378 = 0;
  }
  v23 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 17);
  v506 = 0;
  FsFltWil::AcquireRundownReference(v508, v23);
  if ( !v508[0] )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED000ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x1BA00140080LL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "ORIGIN: Table already run down",
      v331);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v26);
    if ( v508[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
    v28 = Resource;
    Resource = 0;
    if ( v28 )
    {
      ExReleaseResourceLite(v28);
      KeLeaveCriticalRegion();
    }
    if ( !v19 )
      goto LABEL_77;
    v29 = LOBYTE(v19[1].Length) == 0;
LABEL_74:
    if ( v29 )
      *v19 = 0;
    FsFltWil::Details::FreeUnicodeString(v19, v27);
    ExFreePoolWithTag(v19, 0);
LABEL_77:
    if ( v15 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
    return 3236757514LL;
  }
  v30 = (__int64 **)(a1 + 2);
  for ( i = (__int64 **)*v30; i != v30; i = (__int64 **)*i )
  {
    v354 = (UnionFs::UfsInstanceTierNode *)(i + 2);
    if ( (FsFltWil::Details *)*i[3] == a2 )
      goto LABEL_61;
  }
  v368 = 0;
  v33 = UnionFs::UfsInstanceTierNode::AllocAndInit(a2);
  if ( v33 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v33,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x6A00140094LL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "PUSH: Allocating new instance tier node",
      v331);
    v35 = v368;
    if ( v368 )
    {
      v36 = (void *)*((_QWORD *)v368 + 1);
      *((_QWORD *)v368 + 1) = 0;
      if ( v36 )
        FltReleaseContext(v36);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v35);
      ExFreePoolWithTag(v35, 0);
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v34);
    if ( v508[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
    v38 = Resource;
    Resource = 0;
    if ( v38 )
    {
      ExReleaseResourceLite(v38);
      KeLeaveCriticalRegion();
    }
    if ( !v19 )
      goto LABEL_53;
    v39 = LOBYTE(v19[1].Length) == 0;
    goto LABEL_50;
  }
  v40 = (__int64 ***)operator new(0x28u, v32);
  if ( !v40 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0xCA0014009ALL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "ORIGIN: Saving new instance tier node",
      v331);
    v327 = v368;
    if ( v368 )
    {
      v328 = (void *)*((_QWORD *)v368 + 1);
      *((_QWORD *)v368 + 1) = 0;
      if ( v328 )
        FltReleaseContext(v328);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v327);
      ExFreePoolWithTag(v327, 0);
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v326);
    if ( v508[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
    v330 = Resource;
    Resource = 0;
    if ( v330 )
    {
      ExReleaseResourceLite(v330);
      KeLeaveCriticalRegion();
    }
    if ( v19 )
    {
      if ( !LOBYTE(v19[1].Length) )
        *v19 = 0;
      FsFltWil::Details::FreeUnicodeString(v19, v329);
      ExFreePoolWithTag(v19, 0);
    }
    if ( v15 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
    return 3221225626LL;
  }
  v41 = v368;
  v42 = *(__int64 ***)v368;
  *(_QWORD *)v368 = 0;
  v40[2] = v42;
  v43 = (__int64 **)v41[1];
  v41[1] = 0;
  v40[3] = v43;
  *((_WORD *)v40 + 16) = 0;
  v44 = v30[1];
  v40[1] = (__int64 **)v44;
  *v40 = v30;
  *v44 = (__int64)v40;
  v45 = v348;
  v30[1] = (__int64 *)v40;
  v30[2] = (__int64 *)((char *)v30[2] + 1);
  v24 = (UnionFs::UfsInstanceTierNode *)(*((_QWORD *)v45 + 2) + 16LL);
  v354 = v24;
  if ( v41 )
  {
    v46 = (void *)v41[1];
    v41[1] = 0;
    if ( v46 )
      FltReleaseContext(v46);
    utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v41);
    ExFreePoolWithTag(v41, 0);
  }
LABEL_61:
  v47 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v47 )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v24);
        memset(v508, 0, sizeof(v508));
        v48 = v348;
        FsFltWil::AcquireResourceExclusive(&v379, v348 + 32);
        v49 = Resource;
        Resource = v379;
        if ( v49 )
        {
          ExReleaseResourceLite(v49);
          KeLeaveCriticalRegion();
        }
        v50 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v48 + 17);
        v379 = 0;
        v507 = 0;
        FsFltWil::AcquireRundownReference(v512, v50);
        wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(
          (FsFltWil::Details *)v508,
          v512);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v512, v51);
        if ( v513 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v513 + 24LL))(v513);
        if ( !v508[0] )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0ED000ALL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x454001400B4LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "ORIGIN: Table already run down",
            v331);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v52);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v53 = Resource;
          Resource = 0;
          if ( v53 )
          {
            ExReleaseResourceLite(v53);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_77;
          v29 = LOBYTE(v19[1].Length) == 0;
          goto LABEL_74;
        }
      }
      else
      {
        v48 = v348;
      }
      String1 = 0;
      v54 = (struct _UNICODE_STRING *)*((unsigned __int16 *)v362 + 12);
      v504 = *(_OWORD *)v362;
      v56 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v504, &String1, v54, v25);
      LOBYTE(v334) = v56;
      v355 = *(_OWORD *)v362;
      if ( (a7 & 0x20) != 0 )
      {
        v57 = RtlEqualUnicodeString(&String1, &UnionFs::g_ExtendComponent, 1u);
        v59 = 0;
        if ( v57 )
        {
          if ( (unsigned int)dword_14009E178 > 3
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v143 = (const struct _UNICODE_STRING *)&v355;
            v356 = 196;
            if ( !*((_QWORD *)&v355 + 1) )
              v143 = &FsTlEmptyUnicodeString;
            v348 = "UnionFs::UfsPathTable::InsertPriv";
            v361 = v143;
            v354 = (UnionFs::UfsInstanceTierNode *)"onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v394 = "Preventing insert of metadata path into path table";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)qword_140097D10,
              v58,
              v55,
              (__int64)&v394,
              (__int64)&v348,
              (__int64)&v354,
              (__int64)&v356,
              (__int64)&v361);
          }
          *v9 = 4;
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v59);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v145 = Resource;
          Resource = 0;
          if ( v145 )
          {
            ExReleaseResourceLite(v145);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_839;
          v146 = LOBYTE(v19[1].Length) == 0;
          goto LABEL_291;
        }
      }
      v60 = *(_DWORD *)v48;
      SourceString = 0;
      if ( (v60 & 1) != 0 )
      {
        Buffer_low = (struct _UNICODE_STRING *)LOWORD(v19[1].Buffer);
        v505 = *v19;
        if ( v56 != UnionFs::Utils::WalkPath((UnionFs::Utils *)&v505, &SourceString, Buffer_low, v55) )
          MicrosoftTelemetryAssertTriggeredMsgKM("moreComponentsLeft == moreShortComponentsLeft");
      }
      v344[0] = v344;
      v344[1] = v344;
      LOBYTE(v332) = 0;
      v384 = v344;
      v62 = String1.Length == 0;
      v372 = v48;
      v375[0] = v344;
      v375[1] = &v358;
      v349[0] = v344;
      v349[1] = &v358;
      v510[0] = off_14007EA78;
      v510[1] = &v358;
      v511 = v510;
      v345 = 0;
      v336 = String1.Length == 0;
      v385 = a7;
      v63 = *(struct UnionFs::UfsPathTierNode **)v354;
      v338 = *(struct UnionFs::UfsPathTierNode **)v354;
      v350 = 1;
      *(_OWORD *)v343 = 0;
      if ( String1.Length )
        break;
      if ( !v356 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000E5LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x48400140152LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Accidental insertion at volume root.",
          v331);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        for ( j = (UnionFs::UfsPathTierNode *)v344[0];
              j != (UnionFs::UfsPathTierNode *)v344;
              j = *(UnionFs::UfsPathTierNode **)j )
        {
          UnionFs::UfsPathTierNode::RemoveDependentUnion(*((UnionFs::UfsPathTierNode **)j + 2), *v358);
        }
        while ( 1 )
        {
          v321 = v344[0];
          if ( v344[0] == v344 )
            break;
          v322 = (_QWORD *)*((_QWORD *)v344[0] + 1);
          v323 = *(_QWORD *)v344[0];
          *v322 = *(_QWORD *)v344[0];
          *(_QWORD *)(v323 + 8) = v322;
          ExFreePoolWithTag(v321, 0);
        }
        v345 = 0;
        goto LABEL_850;
      }
      v64 = *((_QWORD *)v63 + 7);
      v65 = (UnionFs::UfsPathTree *)*((_QWORD *)v63 + 6);
      if ( v64 )
        _InterlockedIncrement((volatile signed __int32 *)(v64 + 8));
      IsEmpty = UnionFs::UfsPathTree::IsEmpty(v65);
      if ( v66 )
      {
        utl::_RefCountBase::_DecStrong(v66);
        v67 = a7;
      }
      if ( !IsEmpty )
      {
        inited = lambda_c5291e2bd2658c1720c6c0fd9196e103_::operator()(&v372, v67, a6);
        if ( inited < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)inited,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x2100014015BLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: One or more payload nodes already exist in the table.",
            v331);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          for ( k = (UnionFs::UfsPathTierNode *)v344[0];
                k != (UnionFs::UfsPathTierNode *)v344;
                k = *(UnionFs::UfsPathTierNode **)k )
          {
            UnionFs::UfsPathTierNode::RemoveDependentUnion(*((UnionFs::UfsPathTierNode **)k + 2), *v358);
          }
          while ( 1 )
          {
            v151 = v344[0];
            if ( v344[0] == v344 )
              break;
            v152 = (_QWORD *)*((_QWORD *)v344[0] + 1);
            v153 = *(_QWORD *)v344[0];
            *v152 = *(_QWORD *)v344[0];
            *(_QWORD *)(v153 + 8) = v152;
            ExFreePoolWithTag(v151, 0);
          }
          v345 = 0;
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v149);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v155 = Resource;
          Resource = 0;
          if ( v155 )
          {
            ExReleaseResourceLite(v155);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_316;
          v156 = LOBYTE(v19[1].Length) == 0;
LABEL_313:
          if ( v156 )
            *v19 = 0;
          FsFltWil::Details::FreeUnicodeString(v19, v154);
          ExFreePoolWithTag(v19, 0);
          goto LABEL_316;
        }
        if ( !*((_QWORD *)v63 + 8) && !*((_QWORD *)v63 + 15) )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000E5LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x49200140166LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "ORIGIN: Missing volume root node with other nodes in table",
            v331);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          for ( m = (UnionFs::UfsPathTierNode *)v344[0];
                m != (UnionFs::UfsPathTierNode *)v344;
                m = *(UnionFs::UfsPathTierNode **)m )
          {
            UnionFs::UfsPathTierNode::RemoveDependentUnion(*((UnionFs::UfsPathTierNode **)m + 2), *v358);
          }
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
LABEL_850:
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v148);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v325 = Resource;
          Resource = 0;
          if ( v325 )
          {
            ExReleaseResourceLite(v325);
            KeLeaveCriticalRegion();
          }
          if ( v19 )
          {
            if ( !LOBYTE(v19[1].Length) )
              *v19 = 0;
            FsFltWil::Details::FreeUnicodeString(v19, v324);
            ExFreePoolWithTag(v19, 0);
          }
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return 3221225701LL;
        }
      }
      v62 = v336;
LABEL_99:
      if ( !UnionFs::UfsInstanceTierNode::HasVolumeRootMapping(v354) )
      {
        if ( v62 )
        {
          v305 = v358;
          v306 = (volatile signed __int32 *)v351[1];
          v307 = *v351;
          if ( v306 )
            _InterlockedIncrement(v306 + 2);
          v484[0] = v307;
          v484[1] = v306;
          v308 = *(struct UnionFs::UfsPathTierNode **)v354;
          if ( v306 )
            _InterlockedIncrement(v306 + 2);
          UnionFs::UfsPathTierNode::SetPayload(v308, v484);
          v309 = v305;
          v102 = v354;
          UnionFs::UfsPathTierNode::SetOwningUnion(*(_QWORD *)v354, v309);
          if ( v306 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v306);
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v312 = (const struct _UNICODE_STRING *)&v355;
            LODWORD(v337) = 498;
            if ( !*((_QWORD *)&v355 + 1) )
              v312 = &FsTlEmptyUnicodeString;
            v443 = "UnionFs::UfsPathTable::InsertPriv";
            v440 = v312;
            v441 = *v351;
            v442 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v444 = "Inserted payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_14009789E,
              v310,
              v311,
              (__int64)&v444,
              (__int64)&v443,
              (__int64)&v442,
              (__int64)&v337,
              (__int64)&v441,
              (__int64)&v440);
          }
          *v9 = 1;
LABEL_173:
          if ( v361 )
          {
            v103 = v348;
            v15 = 0;
            v503 = v14;
            ShortNameCopy = UnionFs::UfsPathTable::AddOrReplaceSubtree(v348, v63, &v503, a6, 0);
            if ( ShortNameCopy < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)ShortNameCopy,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x3C000140204LL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Adding subtree to path tree node",
                v331);
LABEL_813:
              if ( v511 )
                (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
              wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
              utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
              FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v314);
              if ( v508[16] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
              v315 = Resource;
              Resource = 0;
              if ( v315 )
              {
                ExReleaseResourceLite(v315);
                KeLeaveCriticalRegion();
              }
              goto LABEL_819;
            }
            updated = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v354, v352, a6);
            ShortNameCopy = updated;
            if ( updated < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)updated,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x4400014020ALL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Updating stored path length",
                v331);
              goto LABEL_813;
            }
          }
          else
          {
            if ( *(_WORD *)v362 > *((_WORD *)v102 + 8) )
              *((_WORD *)v102 + 8) = *(_WORD *)v362;
            v103 = v348;
          }
          if ( *v9 != 1
            || (ShortNameCopy = UnionFs::UfsPathTable::Traverse(v103, v365, v509, a6, 10), ShortNameCopy >= 0) )
          {
            if ( v511 )
              (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
            wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
            utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v318);
            if ( v508[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
            v319 = Resource;
            Resource = 0;
            if ( v319 )
            {
              ExReleaseResourceLite(v319);
              KeLeaveCriticalRegion();
            }
            goto LABEL_838;
          }
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)ShortNameCopy,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x5FE0014021BLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: Applying owner to descendants of root",
            v331);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v316);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v317 = Resource;
          Resource = 0;
          if ( v317 )
          {
            ExReleaseResourceLite(v317);
            KeLeaveCriticalRegion();
          }
          goto LABEL_831;
        }
        goto LABEL_177;
      }
      if ( v62 && (*(_DWORD *)v348 & 4) == 0 )
      {
        inited = -1073741811;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000000DLL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0xE00140175LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: \\ is already a mapping.",
          v331);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v157);
        if ( v508[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
        v158 = Resource;
        Resource = 0;
        if ( v158 )
        {
          ExReleaseResourceLite(v158);
          KeLeaveCriticalRegion();
        }
        if ( !v19 )
          goto LABEL_316;
        v156 = LOBYTE(v19[1].Length) == 0;
        goto LABEL_313;
      }
      v70 = (volatile signed __int32 *)*((_QWORD *)v63 + 9);
      v71 = (struct UnionFs::UfsPathTierNode *)*((_QWORD *)v63 + 8);
      v337 = v71;
      v72 = v70 + 2;
      v360 = (__int64)(v70 + 2);
      if ( v70 )
        _InterlockedIncrement(v72);
      else
        v360 = 8;
      (*(void (__fastcall **)(struct UnionFs::UfsPathTierNode *, PERESOURCE *))(*(_QWORD *)v71 + 8LL))(v71, &v346);
      v73 = (int)v353;
      v485[0] = &v346;
      v485[1] = &Resource;
      if ( !v353 )
        goto LABEL_127;
      v486[0] = v337;
      v486[1] = v70;
      if ( v70 )
        _InterlockedIncrement(v72);
      v33 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
              v73,
              (unsigned int)v486,
              (unsigned int)&v332,
              (unsigned int)v485,
              (__int64)a6);
      if ( v33 != -1073741267 )
      {
        if ( v33 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v33,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x1000014018CLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v331);
          v165 = v346;
          v346 = 0;
          if ( v165 )
          {
            ExReleaseResourceLite(v165);
            KeLeaveCriticalRegion();
          }
          if ( v70 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v70);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v166);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v167 = Resource;
          Resource = 0;
          if ( v167 )
          {
            ExReleaseResourceLite(v167);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_53;
          v39 = LOBYTE(v19[1].Length) == 0;
LABEL_50:
          if ( v39 )
            *v19 = 0;
          FsFltWil::Details::FreeUnicodeString(v19, v37);
          ExFreePoolWithTag(v19, 0);
LABEL_53:
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return (unsigned int)v33;
        }
        if ( (_BYTE)v332 )
        {
          v75 = v346;
          v346 = 0;
          if ( v75 )
          {
            ExReleaseResourceLite(v75);
            KeLeaveCriticalRegion();
          }
          v76 = (struct _ERESOURCE **)(*(__int64 (__fastcall **)(struct UnionFs::UfsPathTierNode *, PERESOURCE *))(*(_QWORD *)v337 + 16LL))(
                                        v337,
                                        &v380);
          v77 = *v76;
          *v76 = 0;
          v78 = v346;
          v346 = v77;
          if ( v78 )
          {
            ExReleaseResourceLite(v78);
            KeLeaveCriticalRegion();
          }
          v79 = v380;
          v380 = 0;
          if ( v79 )
          {
            ExReleaseResourceLite(v79);
            KeLeaveCriticalRegion();
          }
          v80 = v337;
          if ( !*((_BYTE *)v337 + 8) )
          {
            LOBYTE(v332) = 0;
            v72 = (volatile signed __int32 *)v360;
            goto LABEL_128;
          }
          v29 = String1.Length == 0;
          *v9 = 3;
          *((_BYTE *)v9 + 32) = !v29;
          v159 = (struct _ERESOURCE *)*((_QWORD *)v9 + 1);
          v160 = v346;
          v346 = 0;
          *((_QWORD *)v9 + 1) = v160;
          if ( v159 )
          {
            ExReleaseResourceLite(v159);
            KeLeaveCriticalRegion();
            v80 = v337;
          }
          if ( v70 )
            _InterlockedIncrement((volatile signed __int32 *)v360);
          *((_QWORD *)v9 + 2) = v80;
          v161 = (utl::_RefCountBase *)*((_QWORD *)v9 + 3);
          *((_QWORD *)v9 + 3) = v70;
          if ( v161 )
            utl::_RefCountBase::_DecStrong(v161);
          v162 = v346;
          v346 = 0;
          if ( v162 )
          {
            ExReleaseResourceLite(v162);
            KeLeaveCriticalRegion();
          }
          if ( v70 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v70);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v163);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v164 = Resource;
          Resource = 0;
          if ( v164 )
          {
            ExReleaseResourceLite(v164);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_839;
          v146 = LOBYTE(v19[1].Length) == 0;
LABEL_291:
          if ( v146 )
            *v19 = 0;
          FsFltWil::Details::FreeUnicodeString(v19, v144);
          ExFreePoolWithTag(v19, 0);
          goto LABEL_839;
        }
        v72 = (volatile signed __int32 *)v360;
LABEL_127:
        v80 = v337;
LABEL_128:
        if ( v336 )
        {
          if ( !*((_BYTE *)v80 + 8) )
          {
            v81 = v351;
            v467[0] = *v351;
            v82 = v351[1];
            v467[1] = v82;
            if ( v82 )
              _InterlockedIncrement((volatile signed __int32 *)(v82 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v338, v467);
            if ( (unsigned int)dword_14009E178 > 5
              && (qword_14009E188 & 0x10) != 0
              && (qword_14009E190 & 0x10) == qword_14009E190 )
            {
              v85 = (const struct _UNICODE_STRING *)&v355;
              v371 = 442;
              if ( !*((_QWORD *)&v355 + 1) )
                v85 = &FsTlEmptyUnicodeString;
              v449 = "UnionFs::UfsPathTable::InsertPriv";
              v445 = v85;
              v446 = *v81;
              v447 = v337;
              v448 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
              v450 = "Inserted payload (replaced invalid volume root)";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (unsigned int)&FsTlEmptyUnicodeString,
                (unsigned int)&byte_140097D57,
                v83,
                v84,
                (__int64)&v450,
                (__int64)&v449,
                (__int64)&v448,
                (__int64)&v371,
                (__int64)&v447,
                (__int64)&v446,
                (__int64)&v445);
            }
            goto LABEL_153;
          }
          v86 = v346;
          v346 = 0;
          if ( v86 )
          {
            ExReleaseResourceLite(v86);
            KeLeaveCriticalRegion();
            v80 = v337;
          }
          v87 = (struct _ERESOURCE **)(*(__int64 (__fastcall **)(struct UnionFs::UfsPathTierNode *, PERESOURCE *))(*(_QWORD *)v80 + 16LL))(
                                        v80,
                                        &v381);
          v88 = *v87;
          *v87 = 0;
          v89 = v346;
          v346 = v88;
          if ( v89 )
          {
            ExReleaseResourceLite(v89);
            KeLeaveCriticalRegion();
          }
          v90 = v381;
          v381 = 0;
          if ( v90 )
          {
            ExReleaseResourceLite(v90);
            KeLeaveCriticalRegion();
          }
          if ( *((_BYTE *)v337 + 8) )
          {
            v96 = *(volatile signed __int32 **)UnionFs::UfsPathTierNode::GetOwningUnion(v338, v487);
            v360 = (__int64)v96;
            if ( v488 )
            {
              utl::_RefCountBase::_DecStrong(v488);
              v96 = (volatile signed __int32 *)v360;
            }
            if ( v96 )
            {
              UnionFs::ProcessTraceStatusOrigin(
                (UnionFs *)0xC0ED0001LL,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x486001401DALL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "ORIGIN: Root node already owned by a union",
                v331);
              v168 = v346;
              v346 = 0;
              if ( v168 )
              {
                ExReleaseResourceLite(v168);
                KeLeaveCriticalRegion();
              }
              if ( v70 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v70);
              if ( v511 )
                (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
              wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
              utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
              FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v169);
              if ( v508[16] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
              v171 = Resource;
              Resource = 0;
              if ( v171 )
              {
                ExReleaseResourceLite(v171);
                KeLeaveCriticalRegion();
              }
              if ( v19 )
              {
                if ( !LOBYTE(v19[1].Length) )
                  *v19 = 0;
                FsFltWil::Details::FreeUnicodeString(v19, v170);
                ExFreePoolWithTag(v19, 0);
              }
              goto LABEL_699;
            }
            if ( (unsigned int)dword_14009E178 > 4
              && (qword_14009E188 & 0x10) != 0
              && (qword_14009E190 & 0x10) == qword_14009E190 )
            {
              v99 = (const struct _UNICODE_STRING *)&v355;
              v374 = 480;
              if ( !*((_QWORD *)&v355 + 1) )
                v99 = &FsTlEmptyUnicodeString;
              *(_QWORD *)v390 = "UnionFs::UfsPathTable::InsertPriv";
              v386 = v99;
              v387 = *v351;
              v388 = v337;
              v389 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
              v391 = "Insert returning existing volume root payload";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (unsigned int)&FsTlEmptyUnicodeString,
                (unsigned int)word_1400976C2,
                v97,
                v98,
                (__int64)&v391,
                (__int64)v390,
                (__int64)&v389,
                (__int64)&v374,
                (__int64)&v388,
                (__int64)&v387,
                (__int64)&v386);
            }
            *v9 = 2;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v9 + 2,
              &v346);
            if ( v70 )
              _InterlockedIncrement(v72);
            *((_QWORD *)v9 + 2) = v337;
            v100 = (utl::_RefCountBase *)*((_QWORD *)v9 + 3);
            *((_QWORD *)v9 + 3) = v70;
            if ( v100 )
              utl::_RefCountBase::_DecStrong(v100);
          }
          else
          {
            v91 = v351;
            v468[0] = *v351;
            v92 = v351[1];
            v468[1] = v92;
            if ( v92 )
              _InterlockedIncrement((volatile signed __int32 *)(v92 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v338, v468);
            if ( (unsigned int)dword_14009E178 > 5
              && (qword_14009E188 & 0x10) != 0
              && (qword_14009E190 & 0x10) == qword_14009E190 )
            {
              v95 = (const struct _UNICODE_STRING *)&v355;
              v376 = 462;
              if ( !*((_QWORD *)&v355 + 1) )
                v95 = &FsTlEmptyUnicodeString;
              v465 = "UnionFs::UfsPathTable::InsertPriv";
              v451 = v95;
              v452 = *v91;
              v453 = v337;
              v454 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
              v466 = "Inserted payload (replaced invalid volume root)";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (unsigned int)&FsTlEmptyUnicodeString,
                (unsigned int)&word_140097A06,
                v93,
                v94,
                (__int64)&v466,
                (__int64)&v465,
                (__int64)&v454,
                (__int64)&v376,
                (__int64)&v453,
                (__int64)&v452,
                (__int64)&v451);
            }
LABEL_153:
            *v9 = 1;
          }
        }
        v101 = v346;
        v346 = 0;
        if ( v101 )
        {
          ExReleaseResourceLite(v101);
          KeLeaveCriticalRegion();
        }
        if ( v70 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v70);
        v63 = v338;
        if ( v336 )
        {
          v102 = v354;
          goto LABEL_173;
        }
        goto LABEL_177;
      }
      v74 = v346;
      v346 = 0;
      v47 = 1;
      if ( v74 )
      {
        ExReleaseResourceLite(v74);
        KeLeaveCriticalRegion();
      }
      if ( v70 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v70);
      if ( v511 )
        (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
    }
    if ( v356 )
      goto LABEL_99;
LABEL_177:
    inited = lambda_499e3257b266ccbef4f29b33c513cd89_::operator()(&v384, v63, a6);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x49500140227LL,
        (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
        "PUSH: Adding volume root to intermediate nodes",
        v331);
      if ( v511 )
        (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v304);
      if ( v508[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
      v284 = Resource;
      Resource = 0;
      goto LABEL_795;
    }
    OwningUnion = UnionFs::UfsPathTierNode::GetOwningUnion(v63, v489);
    utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(v343, OwningUnion);
    if ( v490 )
      utl::_RefCountBase::_DecStrong(v490);
    v105 = (volatile signed __int32 *)*((_QWORD *)v63 + 7);
    v106 = (UnionFs::UfsPathTree *)*((_QWORD *)v63 + 6);
    v340 = v106;
    v341 = (utl::_RefCountBase *)v105;
    if ( v105 )
      _InterlockedIncrement(v105 + 2);
    v107 = v342;
    v108 = 0;
LABEL_183:
    v377 = v108;
    v382[1] = 0;
    v382[0] = &String1;
    Node = UnionFs::UfsPathTree::FindNode(v106, (const struct UnionFs::UFS_COMPARE_KEY *)v382);
    v337 = Node;
    if ( (*v348 & 3) == 3
      && RtlCompareUnicodeString(&SourceString, &UnionFs::g_NoShortComponent, 0)
      && RtlCompareUnicodeString(&SourceString, &String1, 0) )
    {
      v382[0] = &SourceString;
      v338 = UnionFs::UfsPathTree::FindNode(v106, (const struct UnionFs::UFS_COMPARE_KEY *)v382);
    }
    else
    {
      v338 = 0;
    }
    if ( !Node )
      goto LABEL_411;
    v111 = Node;
    if ( (*((_DWORD *)Node + 6) & 1) != 0 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Don't expect to find short names in table on insert");
      inited = -1073741811;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xF00140267LL,
        (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
        "ORIGIN: Incoming path has an existing short component.",
        v331);
      if ( v341 )
        utl::_RefCountBase::_DecStrong(v341);
      if ( v343[1] )
        utl::_RefCountBase::_DecStrong(v343[1]);
      if ( v511 )
        (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v283);
      if ( v508[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
      v284 = Resource;
      Resource = 0;
LABEL_795:
      if ( v284 )
      {
        ExReleaseResourceLite(v284);
        KeLeaveCriticalRegion();
      }
      goto LABEL_797;
    }
    v112 = 0;
    if ( v334 )
      break;
    if ( *((_QWORD *)v111 + 6) )
    {
      inited = lambda_c5291e2bd2658c1720c6c0fd9196e103_::operator()(&v372, a7, a6);
      if ( inited < 0 )
      {
        v177 = "PUSH: Current node has descendants";
        v178 = 0x21100140344LL;
LABEL_703:
        v176 = (int)a6;
LABEL_704:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          v176,
          (struct UnionFs::StackEventTracer *)v178,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          v177,
          v331);
        goto LABEL_705;
      }
      v134 = 0;
      if ( (a7 & 4) != 0 )
      {
        v107 |= 2u;
        v342 = v107;
        if ( *(_QWORD *)UnionFs::UfsPathTierNode::GetOwningUnion(v111, v496) )
          v134 = 1;
      }
      if ( (v107 & 2) != 0 )
      {
        v342 = v107 & 0xFFFFFFFD;
        if ( v497 )
          utl::_RefCountBase::_DecStrong(v497);
      }
      if ( v134 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0001LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x4870014034FLL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Attempted insert of root on already-owned node",
          v331);
        if ( v341 )
          utl::_RefCountBase::_DecStrong(v341);
        if ( v343[1] )
          utl::_RefCountBase::_DecStrong(v343[1]);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v281);
        if ( v508[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
LABEL_698:
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
LABEL_699:
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return 3236757505LL;
      }
      v135 = (utl::_RefCountBase **)UnionFs::UfsPathTierNode::GetOwningUnion(v111, v498);
      v136 = v343[0] != *v135;
      if ( v499 )
        utl::_RefCountBase::_DecStrong(v499);
      if ( v136 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED000BLL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x2A90014035ALL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Attempted insert into union root node",
          v331);
        if ( v341 )
          utl::_RefCountBase::_DecStrong(v341);
        if ( v343[1] )
          utl::_RefCountBase::_DecStrong(v343[1]);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v280);
        if ( v508[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return 3236757515LL;
      }
      v116 = (volatile signed __int32 *)*((_QWORD *)v111 + 9);
      v137 = (_BYTE *)*((_QWORD *)v111 + 8);
      *(_QWORD *)&v383 = v137;
      *((_QWORD *)&v383 + 1) = v116;
      if ( v116 )
        _InterlockedIncrement(v116 + 2);
      v347 = 0;
      if ( !v137 )
        goto LABEL_638;
      v138 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v137 + 8LL))(v137, v393);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
        &v347,
        v138);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v393);
      if ( (*(_DWORD *)v348 & 4) == 0 )
      {
        if ( !v137[8] )
          UnionFs::UfsPathTierNode::ClearPayload(v111);
LABEL_638:
        v269 = v351;
        v482[0] = *v351;
        v270 = v351[1];
        v482[1] = v270;
        if ( v270 )
          _InterlockedIncrement((volatile signed __int32 *)(v270 + 8));
        if ( !(unsigned __int8)UnionFs::UfsPathTierNode::AddPayloadToInnerNode(v111, v482) )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000035LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x21400140408LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "ORIGIN: Node already has payload",
            v331);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v347);
          if ( v116 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
          goto LABEL_643;
        }
        v272 = v338;
        if ( v338 )
        {
          v483[0] = *v269;
          v273 = v269[1];
          v483[1] = v273;
          if ( v273 )
            _InterlockedIncrement((volatile signed __int32 *)(v273 + 8));
          UnionFs::UfsPathTierNode::AddPayloadToInnerNode(v272, v483);
        }
        ShortNameCopy = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v375, a6);
        if ( ShortNameCopy < 0 )
        {
          v246 = 0x47C00140418LL;
LABEL_588:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)ShortNameCopy,
            (int)a6,
            (struct UnionFs::StackEventTracer *)v246,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: Adding dependent union to intermediates",
            v331);
LABEL_589:
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v347);
          if ( v116 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
LABEL_591:
          if ( v341 )
            utl::_RefCountBase::_DecStrong(v341);
          if ( v343[1] )
            utl::_RefCountBase::_DecStrong(v343[1]);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v247);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
LABEL_599:
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
          goto LABEL_831;
        }
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x10) != 0
          && (qword_14009E190 & 0x10) == qword_14009E190 )
        {
          v276 = (const struct _UNICODE_STRING *)&v355;
          LODWORD(v351) = 1053;
          if ( !*((_QWORD *)&v355 + 1) )
            v276 = &FsTlEmptyUnicodeString;
          *(_QWORD *)v433 = "UnionFs::UfsPathTable::InsertPriv";
          v430 = v276;
          v431 = *v269;
          v432 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
          v434 = "Inserted payload";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (unsigned int)&FsTlEmptyUnicodeString,
            (unsigned int)&word_140097946,
            v274,
            v275,
            (__int64)&v434,
            (__int64)v433,
            (__int64)&v432,
            (__int64)&v351,
            (__int64)&v431,
            (__int64)&v430);
        }
LABEL_666:
        v267 = v357;
        *v357 = 1;
        goto LABEL_667;
      }
      v140 = (int)v353;
      v141 = v137;
      if ( !v353 )
        goto LABEL_585;
      v472[0] = &v347;
      v472[1] = &Resource;
      v500 = v383;
      if ( v116 )
        _InterlockedIncrement(v116 + 2);
      v142 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
               v140,
               (unsigned int)&v500,
               (unsigned int)&v332,
               (unsigned int)v472,
               (__int64)a6);
      if ( v142 != -1073741267 )
      {
        if ( v142 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v142,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x12600140387LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v331);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v347);
          if ( v116 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
          if ( v341 )
            utl::_RefCountBase::_DecStrong(v341);
          if ( v343[1] )
            utl::_RefCountBase::_DecStrong(v343[1]);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v242);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return (unsigned int)v142;
        }
        if ( (_BYTE)v332 )
        {
          v243 = v347;
          v347 = 0;
          if ( v243 )
            FsFltWil::Details::ReleaseResource(v243, v139);
          v244 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v137 + 16LL))(v137, v412);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            &v347,
            v244);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v412);
          if ( v137[8] )
          {
            v245 = v357;
            *v357 = 3;
            *((_BYTE *)v245 + 32) = 0;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v245 + 2,
              &v347);
            utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v245 + 4, &v383);
LABEL_582:
            v173 = &v347;
            goto LABEL_372;
          }
          LOBYTE(v332) = 0;
        }
        v141 = v137;
LABEL_585:
        if ( !v137[8] )
        {
          ShortNameCopy = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v375, a6);
          if ( ShortNameCopy < 0 )
          {
            v246 = 0x47A001403AELL;
            goto LABEL_588;
          }
          v248 = v351;
          v478[0] = *v351;
          v249 = v351[1];
          v478[1] = v249;
          if ( v249 )
            _InterlockedIncrement((volatile signed __int32 *)(v249 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v337, v478);
          v252 = v338;
          if ( v338 )
          {
            v479[0] = *v248;
            v253 = v248[1];
            v479[1] = v253;
            if ( v253 )
              _InterlockedIncrement((volatile signed __int32 *)(v253 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v252, v479);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v254 = (const struct _UNICODE_STRING *)&v355;
            LODWORD(v369) = 955;
            if ( !*((_QWORD *)&v355 + 1) )
              v254 = &FsTlEmptyUnicodeString;
            v416 = "UnionFs::UfsPathTable::InsertPriv";
            v413 = v254;
            v414 = *v248;
            v415 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v417 = "Inserted payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&byte_140097DC7,
              v250,
              v251,
              (__int64)&v417,
              (__int64)&v416,
              (__int64)&v415,
              (__int64)&v369,
              (__int64)&v414,
              (__int64)&v413);
          }
          goto LABEL_666;
        }
        v255 = v347;
        v347 = 0;
        if ( v255 )
          FsFltWil::Details::ReleaseResource(v255, v139);
        v256 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v141 + 16LL))(v141, v418);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
          &v347,
          v256);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v418);
        if ( !v137[8] )
        {
          ShortNameCopy = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v375, a6);
          if ( ShortNameCopy < 0 )
          {
            v246 = 0x47B001403D2LL;
            goto LABEL_588;
          }
          v259 = v351;
          v480[0] = *v351;
          v260 = v351[1];
          v480[1] = v260;
          if ( v260 )
            _InterlockedIncrement((volatile signed __int32 *)(v260 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v337, v480);
          v263 = v338;
          if ( v338 )
          {
            v481[0] = *v259;
            v264 = v259[1];
            v481[1] = v264;
            if ( v264 )
              _InterlockedIncrement((volatile signed __int32 *)(v264 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v263, v481);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v265 = (const struct _UNICODE_STRING *)&v355;
            LODWORD(v360) = 991;
            if ( !*((_QWORD *)&v355 + 1) )
              v265 = &FsTlEmptyUnicodeString;
            v422 = "UnionFs::UfsPathTable::InsertPriv";
            v419 = v265;
            v420 = *v259;
            v421 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v423 = "Inserted payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)byte_140097E1B,
              v261,
              v262,
              (__int64)&v423,
              (__int64)&v422,
              (__int64)&v421,
              (__int64)&v360,
              (__int64)&v420,
              (__int64)&v419);
          }
          goto LABEL_666;
        }
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x10) != 0
          && (qword_14009E190 & 0x10) == qword_14009E190 )
        {
          v266 = (const struct _UNICODE_STRING *)&v355;
          v426 = v137;
          if ( !*((_QWORD *)&v355 + 1) )
            v266 = &FsTlEmptyUnicodeString;
          LODWORD(v362) = 1002;
          v424 = v266;
          v428 = "UnionFs::UfsPathTable::InsertPriv";
          v425 = *v351;
          v427 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
          v429 = "Insert returning existing payload";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (unsigned int)&FsTlEmptyUnicodeString,
            (unsigned int)word_14009799A,
            v257,
            v258,
            (__int64)&v429,
            (__int64)&v428,
            (__int64)&v427,
            (__int64)&v362,
            (__int64)&v426,
            (__int64)&v425,
            (__int64)&v424);
        }
        v267 = v357;
        v268 = v357 + 2;
        *v357 = 2;
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
          v268,
          &v347);
        utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v267 + 4, &v383);
LABEL_667:
        v277 = v337;
        v278 = v348;
        if ( v356 )
        {
          if ( *v267 == 1 )
          {
            v331 = (char *)a6;
            ShortNameCopy = UnionFs::UfsPathTable::Traverse(v348, v365, v337);
            if ( ShortNameCopy < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)ShortNameCopy,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x48A00140430LL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Applying owning union to inner node and descendants",
                (const char *)a6);
              goto LABEL_589;
            }
          }
        }
        if ( v361 )
        {
          v502 = v14;
          v15 = 0;
          ShortNameCopy = UnionFs::UfsPathTable::AddOrReplaceSubtree(v278, v277, &v502, a6, v338);
          if ( ShortNameCopy < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)ShortNameCopy,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x3BD0014043BLL,
              (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
              "PUSH: Adding subtree to path tree node",
              v331);
            goto LABEL_674;
          }
          v279 = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v354, v352, a6);
          ShortNameCopy = v279;
          if ( v279 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v279,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x44200140441LL,
              (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
              "PUSH: Updating stored path length",
              v331);
LABEL_674:
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v347);
LABEL_540:
            if ( v116 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
            if ( v341 )
              utl::_RefCountBase::_DecStrong(v341);
            if ( v343[1] )
              utl::_RefCountBase::_DecStrong(v343[1]);
            if ( v511 )
              (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
            wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
            utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v238);
            if ( v508[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
LABEL_819:
            utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
            return (unsigned int)ShortNameCopy;
          }
        }
        v350 = 0;
        goto LABEL_582;
      }
      v128 = &v347;
LABEL_269:
      v47 = 1;
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v128);
    }
    else
    {
      if ( !*((_QWORD *)v111 + 8) )
        MicrosoftTelemetryAssertTriggeredMsgKM("Final nodes should have payloads");
      if ( (*(_DWORD *)v348 & 4) == 0 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000035LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x2120014033BLL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Path is already in table",
          v331);
LABEL_643:
        if ( v341 )
          utl::_RefCountBase::_DecStrong(v341);
        if ( v343[1] )
          utl::_RefCountBase::_DecStrong(v343[1]);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v271);
        if ( v508[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return 3221225525LL;
      }
      if ( (a7 & 4) != 0 )
      {
        v107 |= 1u;
        v342 = v107;
        if ( *(_QWORD *)UnionFs::UfsPathTierNode::GetOwningUnion(v111, v494) )
          v112 = 1;
      }
      if ( (v107 & 1) != 0 )
      {
        v342 = v107 & 0xFFFFFFFE;
        if ( v495 )
          utl::_RefCountBase::_DecStrong(v495);
      }
      if ( v112 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0001LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x47600140285LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Attempted insert of root on already-owned node",
          v331);
        if ( v341 )
          utl::_RefCountBase::_DecStrong(v341);
        if ( v343[1] )
          utl::_RefCountBase::_DecStrong(v343[1]);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v239);
        if ( v508[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
        v241 = (FsFltWil::Details *)Resource;
        Resource = 0;
        if ( v241 )
          FsFltWil::Details::ReleaseResource(v241, v240);
        goto LABEL_698;
      }
      v116 = (volatile signed __int32 *)*((_QWORD *)v111 + 9);
      v129 = (_BYTE *)*((_QWORD *)v111 + 8);
      v130 = v116 + 2;
      if ( v116 )
        _InterlockedIncrement(v130);
      (*(void (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v129 + 8LL))(v129, &v339);
      v132 = (int)v353;
      if ( !v353 )
        goto LABEL_462;
      v471[0] = v129;
      v470[0] = &v339;
      v470[1] = &Resource;
      v471[1] = v116;
      if ( v116 )
        _InterlockedIncrement(v130);
      v363 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
               v132,
               (unsigned int)v471,
               (unsigned int)&v332,
               (unsigned int)v470,
               (__int64)a6);
      if ( v363 != -1073741267 )
      {
        if ( v363 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v363,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x101001402A7LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v331);
          v186 = v339;
          v339 = 0;
          if ( v186 )
            FsFltWil::Details::ReleaseResource(v186, v185);
          if ( v116 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
          if ( v341 )
            utl::_RefCountBase::_DecStrong(v341);
          if ( v343[1] )
            utl::_RefCountBase::_DecStrong(v343[1]);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v187);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          v189 = (FsFltWil::Details *)Resource;
          Resource = 0;
          if ( v189 )
            FsFltWil::Details::ReleaseResource(v189, v188);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return (unsigned int)v363;
        }
        if ( (_BYTE)v332 )
        {
          v190 = v339;
          v339 = 0;
          if ( v190 )
            FsFltWil::Details::ReleaseResource(v190, v131);
          v191 = (*(__int64 (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v129 + 16LL))(v129, &v365);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            &v339,
            v191);
          v192 = v365;
          v365 = 0;
          if ( v192 )
            FsFltWil::Details::ReleaseResource(v192, v131);
          if ( v129[8] )
          {
            v193 = v357;
            *v357 = 3;
            *((_BYTE *)v193 + 32) = 0;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v193 + 2,
              &v339);
            if ( v116 )
              _InterlockedIncrement(v130);
            *((_QWORD *)v193 + 2) = v129;
            v195 = (utl::_RefCountBase *)*((_QWORD *)v193 + 3);
            *((_QWORD *)v193 + 3) = v116;
            if ( v195 )
              utl::_RefCountBase::_DecStrong(v195);
            v196 = v339;
            v339 = 0;
            if ( v196 )
              FsFltWil::Details::ReleaseResource(v196, v194);
            if ( v116 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
            if ( v341 )
              utl::_RefCountBase::_DecStrong(v341);
            if ( v343[1] )
              utl::_RefCountBase::_DecStrong(v343[1]);
            if ( v511 )
              (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
            wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
            utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v197);
            if ( v508[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
            v199 = (FsFltWil::Details *)Resource;
            Resource = 0;
            if ( v199 )
              FsFltWil::Details::ReleaseResource(v199, v198);
            goto LABEL_838;
          }
          LOBYTE(v332) = 0;
        }
LABEL_462:
        if ( !v129[8] )
        {
          ShortNameCopy = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v375, a6);
          if ( ShortNameCopy < 0 )
          {
            v200 = 0x478001402D7LL;
            goto LABEL_465;
          }
          v206 = v351;
          v474[0] = *v351;
          v207 = v351[1];
          v474[1] = v207;
          if ( v207 )
            _InterlockedIncrement((volatile signed __int32 *)(v207 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v337, v474);
          v210 = v338;
          if ( v338 )
          {
            v475[0] = *v206;
            v211 = v206[1];
            v475[1] = v211;
            if ( v211 )
              _InterlockedIncrement((volatile signed __int32 *)(v211 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v210, v475);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v397 = v129;
            v212 = (const struct _UNICODE_STRING *)&v355;
            v363 = 742;
            if ( !*((_QWORD *)&v355 + 1) )
              v212 = &FsTlEmptyUnicodeString;
            v399 = "UnionFs::UfsPathTable::InsertPriv";
            v395 = v212;
            v396 = *v206;
            v398 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v400 = "Inserted payload (replaced invalid)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&unk_140097CA0,
              v208,
              v209,
              (__int64)&v400,
              (__int64)&v399,
              (__int64)&v398,
              (__int64)&v363,
              (__int64)&v397,
              (__int64)&v396,
              (__int64)&v395);
          }
LABEL_510:
          *v357 = 1;
LABEL_521:
          if ( v361 )
          {
            v15 = 0;
            v501 = v14;
            ShortNameCopy = UnionFs::UfsPathTable::AddOrReplaceSubtree(v348, v337, &v501, a6, v338);
            if ( ShortNameCopy < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)ShortNameCopy,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x3C900140328LL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Adding subtree to path tree node",
                v331);
              v231 = v339;
              v339 = 0;
              if ( v231 )
                FsFltWil::Details::ReleaseResource(v231, v230);
              if ( v116 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
              if ( v341 )
                utl::_RefCountBase::_DecStrong(v341);
              if ( v343[1] )
                utl::_RefCountBase::_DecStrong(v343[1]);
              if ( v511 )
                (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
              wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
              utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
              FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v232);
              if ( v508[16] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
              v234 = (FsFltWil::Details *)Resource;
              Resource = 0;
              if ( v234 )
                FsFltWil::Details::ReleaseResource(v234, v233);
              goto LABEL_819;
            }
            v235 = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v354, v352, a6);
            ShortNameCopy = v235;
            if ( v235 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v235,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x4410014032ELL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Updating stored path length",
                v331);
              v237 = v339;
              v339 = 0;
              if ( v237 )
                FsFltWil::Details::ReleaseResource(v237, v236);
              goto LABEL_540;
            }
          }
          v350 = 0;
          v173 = &v339;
LABEL_372:
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v173);
          if ( v116 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
          if ( v341 )
            utl::_RefCountBase::_DecStrong(v341);
          if ( v343[1] )
            utl::_RefCountBase::_DecStrong(v343[1]);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v174);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          goto LABEL_382;
        }
        v213 = v339;
        v339 = 0;
        if ( v213 )
          FsFltWil::Details::ReleaseResource(v213, v131);
        v214 = (*(__int64 (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v129 + 16LL))(v129, &v366);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
          &v339,
          v214);
        v218 = v366;
        v366 = 0;
        if ( v218 )
          FsFltWil::Details::ReleaseResource(v218, v215);
        if ( v129[8] )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v226 = (const struct _UNICODE_STRING *)&v355;
            v409 = v129;
            if ( !*((_QWORD *)&v355 + 1) )
              v226 = &FsTlEmptyUnicodeString;
            v373 = 791;
            v407 = v226;
            *(_QWORD *)v411 = "UnionFs::UfsPathTable::InsertPriv";
            v408 = *v351;
            v410 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v377 = "Insert returning existing payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_140097AE6,
              v216,
              v217,
              (__int64)&v377,
              (__int64)v411,
              (__int64)&v410,
              (__int64)&v373,
              (__int64)&v409,
              (__int64)&v408,
              (__int64)&v407);
          }
          v227 = v357;
          v228 = v357 + 2;
          *v357 = 2;
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            v228,
            &v339);
          if ( v116 )
            _InterlockedIncrement(v130);
          *((_QWORD *)v227 + 2) = v129;
          v229 = (utl::_RefCountBase *)*((_QWORD *)v227 + 3);
          *((_QWORD *)v227 + 3) = v116;
          if ( v229 )
            utl::_RefCountBase::_DecStrong(v229);
          goto LABEL_521;
        }
        ShortNameCopy = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v375, a6);
        if ( ShortNameCopy >= 0 )
        {
          v219 = v351;
          v476[0] = *v351;
          v220 = v351[1];
          v476[1] = v220;
          if ( v220 )
            _InterlockedIncrement((volatile signed __int32 *)(v220 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v337, v476);
          v223 = v338;
          if ( v338 )
          {
            v477[0] = *v219;
            v224 = v219[1];
            v477[1] = v224;
            if ( v224 )
              _InterlockedIncrement((volatile signed __int32 *)(v224 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v223, v477);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v403 = v129;
            v225 = (const struct _UNICODE_STRING *)&v355;
            v342 = 780;
            if ( !*((_QWORD *)&v355 + 1) )
              v225 = &FsTlEmptyUnicodeString;
            v405 = "UnionFs::UfsPathTable::InsertPriv";
            v401 = v225;
            v402 = *v219;
            v404 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v406 = "Inserted payload (replaced invalid)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_140097A76,
              v221,
              v222,
              (__int64)&v406,
              (__int64)&v405,
              (__int64)&v404,
              (__int64)&v342,
              (__int64)&v403,
              (__int64)&v402,
              (__int64)&v401);
          }
          goto LABEL_510;
        }
        v200 = 0x479001402FDLL;
LABEL_465:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)ShortNameCopy,
          (int)a6,
          (struct UnionFs::StackEventTracer *)v200,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "PUSH: Adding dependent union to intermediates",
          v331);
        v202 = v339;
        v339 = 0;
        if ( v202 )
          FsFltWil::Details::ReleaseResource(v202, v201);
        if ( v116 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
        if ( v341 )
          utl::_RefCountBase::_DecStrong(v341);
        if ( v343[1] )
          utl::_RefCountBase::_DecStrong(v343[1]);
        if ( v511 )
          (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v203);
        if ( v508[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
        v205 = (FsFltWil::Details *)Resource;
        Resource = 0;
        if ( v205 )
          FsFltWil::Details::ReleaseResource(v205, v204);
LABEL_831:
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
LABEL_21:
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return (unsigned int)ShortNameCopy;
      }
      v133 = v339;
      v339 = 0;
      v47 = 1;
      if ( v133 )
        FsFltWil::Details::ReleaseResource(v133, v131);
    }
    if ( v116 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
    if ( v341 )
      utl::_RefCountBase::_DecStrong(v341);
    if ( v343[1] )
      utl::_RefCountBase::_DecStrong(v343[1]);
    if ( v511 )
      (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
    wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
    utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
    v9 = v357;
  }
  v113 = *((_QWORD *)v111 + 8);
  if ( v113 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v113 + 48LL))(v113) )
    {
      v114 = (int)v353;
      if ( v353 )
      {
        v115 = (_BYTE *)*((_QWORD *)v111 + 8);
        *(_QWORD *)&v457 = v115;
        v116 = (volatile signed __int32 *)*((_QWORD *)v337 + 9);
        *((_QWORD *)&v457 + 1) = v116;
        if ( v116 )
          _InterlockedIncrement(v116 + 2);
        (*(void (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v115 + 8LL))(v115, &v359);
        v469[0] = &v359;
        v469[1] = &Resource;
        v491 = v457;
        if ( v116 )
          _InterlockedIncrement(v116 + 2);
        v117 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
                 v114,
                 (unsigned int)&v491,
                 (unsigned int)&v332,
                 (unsigned int)v469,
                 (__int64)a6);
        v33 = v117;
        if ( v117 == -1073741267 )
        {
          v128 = &v359;
          goto LABEL_269;
        }
        if ( v117 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v117,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x2080014045DLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v331);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v359);
          if ( v116 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
LABEL_385:
          if ( v341 )
            utl::_RefCountBase::_DecStrong(v341);
          if ( v343[1] )
            utl::_RefCountBase::_DecStrong(v343[1]);
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v175);
          if ( v508[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          goto LABEL_53;
        }
        if ( (_BYTE)v332 )
        {
          v119 = v359;
          v359 = 0;
          if ( v119 )
            FsFltWil::Details::ReleaseResource(v119, v118);
          v120 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v115 + 16LL))(v115, v392);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            &v359,
            v120);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v392);
          if ( v115[8] )
          {
            v172 = v357;
            *v357 = 3;
            *((_BYTE *)v172 + 32) = 1;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v172 + 2,
              &v359);
            utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v172 + 4, &v457);
            v173 = &v359;
            goto LABEL_372;
          }
          LOBYTE(v332) = 0;
        }
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v359);
        if ( v116 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v116);
        v111 = v337;
      }
    }
  }
  v122 = UnionFs::Utils::WalkPathName(v362, (const struct UnionFs::UfsPathName *)&String1, v109);
  LOBYTE(v334) = v122;
  if ( (*(_DWORD *)v348 & 1) != 0
    && v122 != UnionFs::Utils::WalkPathName(
                 (UnionFs::Utils *)v19,
                 (const struct UnionFs::UfsPathName *)&SourceString,
                 v121) )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("moreComponentsLeft == moreShortComponentsLeft");
  }
  inited = lambda_499e3257b266ccbef4f29b33c513cd89_::operator()(&v384, v111, a6);
  if ( inited < 0 )
  {
    v177 = "PUSH: Updating intermediateNodes";
    v178 = 0x48200140486LL;
    goto LABEL_703;
  }
  v123 = UnionFs::UfsPathTierNode::GetOwningUnion(v111, v492);
  utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(v343, v123);
  if ( v493 )
    utl::_RefCountBase::_DecStrong(v493);
  v124 = (__int64 *)((char *)v111 + 48);
  if ( *((_QWORD *)v111 + 6) )
  {
    v455 = *v124;
    v125 = (volatile signed __int32 *)*((_QWORD *)v111 + 7);
    v456 = (utl::_RefCountBase *)v125;
    if ( v125 )
      _InterlockedIncrement(v125 + 2);
    utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(&v340, &v455);
    if ( v456 )
      utl::_RefCountBase::_DecStrong(v456);
    v106 = v340;
    v107 = v342;
    if ( !v338 )
      goto LABEL_224;
    v107 = v342 | 4;
    v342 |= 4u;
    v126 = (UnionFs::UfsPathTree *)*((_QWORD *)v338 + 6);
    v127 = (volatile signed __int32 *)*((_QWORD *)v338 + 7);
    v369 = (utl::_RefCountBase *)v127;
    if ( v127 )
      _InterlockedIncrement(v127 + 2);
    if ( v126 != v106 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Short name node should have same descendant tree.");
LABEL_224:
      v127 = (volatile signed __int32 *)v369;
    }
    v108 = (const char *)v337;
    if ( (v107 & 4) != 0 )
    {
      v107 &= ~4u;
      v342 = v107;
      if ( v127 )
      {
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v127);
        v108 = (const char *)v337;
      }
    }
    goto LABEL_183;
  }
  inited = lambda_c5291e2bd2658c1720c6c0fd9196e103_::operator()(&v372, a7, a6);
  v176 = (int)a6;
  if ( inited < 0 )
  {
    v177 = "PUSH: Payload node already exists along this path, nested paths not allowed.";
    v178 = 0x11001404A0LL;
    goto LABEL_704;
  }
  if ( *v124 )
  {
    inited = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x21600150144LL,
      (unsigned __int64)"UnionFs::UfsPathTierNode::ConvertFinalNodeToInner",
      "ORIGIN: Node is not final",
      v331);
LABEL_400:
    v177 = "PUSH: Converting final node to inner.";
    v178 = 0x218001404A8LL;
    goto LABEL_703;
  }
  inited = UnionFs::UfsPathTree::AllocAndInitShared(v124, a6);
  if ( inited < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inited,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x21700150149LL,
      (unsigned __int64)"UnionFs::UfsPathTierNode::ConvertFinalNodeToInner",
      "PUSH: Allocating m_NextLevelTree",
      v331);
    goto LABEL_400;
  }
  v179 = v338;
  if ( v338 )
  {
    v473[0] = *v124;
    v180 = *((_QWORD *)v111 + 7);
    v473[1] = v180;
    if ( v180 )
      _InterlockedIncrement((volatile signed __int32 *)(v180 + 8));
    inited = UnionFs::UfsPathTierNode::ConvertFinalNodeToInner(v179, v473, a6);
    if ( inited < 0 )
    {
      v177 = "PUSH: Adding descendant tree to short name node.";
      v178 = 0x21A001404B2LL;
      goto LABEL_703;
    }
  }
  v458 = *v124;
  v181 = (volatile signed __int32 *)*((_QWORD *)v111 + 7);
  v459 = (utl::_RefCountBase *)v181;
  if ( v181 )
    _InterlockedIncrement(v181 + 2);
  utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(&v340, &v458);
  if ( v459 )
    utl::_RefCountBase::_DecStrong(v459);
  v106 = v340;
LABEL_411:
  if ( !v106 )
    MicrosoftTelemetryAssertTriggeredMsgKM("We must have a parent to insert under");
  v182 = v334;
  while ( 2 )
  {
    v338 = 0;
    if ( v182 )
    {
      inited = UnionFs::UfsPathTierNode::AllocAndInitInnerNode(&String1, 0);
      if ( inited < 0 )
      {
        v297 = 0x12001404D0LL;
        goto LABEL_761;
      }
      v183 = v338;
      v33 = lambda_499e3257b266ccbef4f29b33c513cd89_::operator()(&v384, v338, a6);
      if ( v33 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v33,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x483001404D7LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "PUSH: Updating intermediateNodes",
          v331);
        goto LABEL_759;
      }
      v184 = v351;
LABEL_727:
      if ( *((_QWORD *)v183 + 6) && !v334 && !v366 )
        MicrosoftTelemetryAssertTriggeredMsgKM("curInsertNode->IsFinal() || moreComponentsLeft || nextLevelTree");
      if ( (*(_DWORD *)v348 & 1) != 0
        && RtlCompareUnicodeString(&SourceString, &UnionFs::g_NoShortComponent, 0)
        && RtlCompareUnicodeString(&SourceString, &String1, 0) )
      {
        v353 = 0;
        if ( v334 )
        {
          v483[4] = *((_QWORD *)v183 + 6);
          v287 = *((_QWORD *)v183 + 7);
          v483[5] = v287;
          if ( v287 )
            _InterlockedIncrement((volatile signed __int32 *)(v287 + 8));
          v33 = UnionFs::UfsPathTierNode::AllocAndInitInnerShortNameNode(&SourceString, (__int64)&v353, (int)a6);
          if ( v33 < 0 )
          {
            v288 = 0x1300140502LL;
LABEL_739:
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v33,
              (int)a6,
              (struct UnionFs::StackEventTracer *)v288,
              (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
              "PUSH: Could not create new short name path node.",
              v331);
            utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v353);
LABEL_759:
            utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v338);
            goto LABEL_385;
          }
        }
        else
        {
          v289 = (unsigned __int64)&v370 & -(__int64)(v361 != 0);
          v483[6] = *v184;
          v290 = v184[1];
          v483[7] = v290;
          if ( v290 )
            _InterlockedIncrement((volatile signed __int32 *)(v290 + 8));
          v33 = UnionFs::UfsPathTierNode::AllocAndInitPayloadShortNameNode(&SourceString, (__int64)&v353, (int)a6, v289);
          if ( v33 < 0 )
          {
            v288 = 0x11C00140517LL;
            goto LABEL_739;
          }
        }
        v291 = v353;
        v292 = (char *)v353 + 32;
        v353 = 0;
        v460 = (unsigned __int64)v292;
        UnionFs::UfsPathTree::InsertNode(v106, (const struct UnionFs::UFS_COMPARE_KEY *)&v460, v291);
        utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v353);
      }
      *(_OWORD *)v464 = 0;
      if ( v334 )
      {
        if ( !*((_QWORD *)v183 + 6) )
          MicrosoftTelemetryAssertTriggeredMsgKM("!curInsertNode->IsFinal()");
        v461 = *((_QWORD *)v183 + 6);
        v293 = (volatile signed __int32 *)*((_QWORD *)v183 + 7);
        v462 = (utl::_RefCountBase *)v293;
        if ( v293 )
          _InterlockedIncrement(v293 + 2);
        utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(v464, &v461);
        if ( v462 )
          utl::_RefCountBase::_DecStrong(v462);
      }
      v338 = 0;
      v463 = (unsigned __int64)v183 + 32;
      UnionFs::UfsPathTree::InsertNode(v106, (const struct UnionFs::UFS_COMPARE_KEY *)&v463, v183);
      v294 = v362;
      v182 = UnionFs::Utils::WalkPathName(v362, (const struct UnionFs::UfsPathName *)&String1, v295);
      LOBYTE(v334) = v182;
      if ( (*(_DWORD *)v348 & 1) != 0
        && v182 != UnionFs::Utils::WalkPathName(
                     (UnionFs::Utils *)v19,
                     (const struct UnionFs::UfsPathName *)&SourceString,
                     v296) )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("moreComponentsLeft == moreShortComponentsLeft");
      }
      utl::shared_ptr<UnionFs::UfsPathTree>::operator=(&v340, v464);
      if ( v464[1] )
        utl::_RefCountBase::_DecStrong(v464[1]);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v338);
      if ( String1.Length )
      {
        v106 = v340;
        continue;
      }
      v298 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v375, a6);
      ShortNameCopy = v298;
      if ( v298 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v298,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x48500140552LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "PUSH: Adding dependent union to intermediates",
          v331);
        goto LABEL_591;
      }
      if ( v361 )
      {
        v301 = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v354, v352, a6);
        ShortNameCopy = v301;
        if ( v301 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v301,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x4430014055BLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: Updating stored path length",
            v331);
          if ( v341 )
            utl::_RefCountBase::_DecStrong(v341);
          if ( v343[1] )
          {
            utl::_RefCountBase::_DecStrong(v343[1]);
            v15 = (volatile signed __int32 *)v370.m128i_i64[1];
          }
          if ( v511 )
            (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
          wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::~unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>(v508);
          goto LABEL_599;
        }
      }
      else if ( *(_WORD *)v294 > *((_WORD *)v354 + 8) )
      {
        *((_WORD *)v354 + 8) = *(_WORD *)v294;
      }
      v350 = 0;
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x10) != 0
        && (qword_14009E190 & 0x10) == qword_14009E190 )
      {
        v302 = (const struct _UNICODE_STRING *)&v355;
        v352 = 1383;
        if ( !*((_QWORD *)&v355 + 1) )
          v302 = &FsTlEmptyUnicodeString;
        v438 = "UnionFs::UfsPathTable::InsertPriv";
        v435 = v302;
        v436 = *v351;
        v437 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
        v439 = "Inserted payload";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)word_1400978F2,
          v299,
          v300,
          (__int64)&v439,
          (__int64)&v438,
          (__int64)&v437,
          (__int64)&v352,
          (__int64)&v436,
          (__int64)&v435);
        v15 = (volatile signed __int32 *)v370.m128i_i64[1];
      }
      v303 = v341;
      *v357 = 1;
      if ( v303 )
      {
        utl::_RefCountBase::_DecStrong(v303);
        v15 = (volatile signed __int32 *)v370.m128i_i64[1];
      }
      if ( v343[1] )
      {
        utl::_RefCountBase::_DecStrong(v343[1]);
        v15 = (volatile signed __int32 *)v370.m128i_i64[1];
      }
      if ( v511 )
        (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
      wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::~unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>(v508);
LABEL_382:
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
LABEL_838:
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
LABEL_839:
      if ( v15 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
      return 0;
    }
    break;
  }
  v184 = v351;
  v285 = (unsigned __int64)&v370 & -(__int64)(v361 != 0);
  v483[2] = *v351;
  v286 = v351[1];
  v483[3] = v286;
  if ( v286 )
    _InterlockedIncrement((volatile signed __int32 *)(v286 + 8));
  inited = UnionFs::UfsPathTierNode::AllocAndInitPayloadNode(&String1, (int)a6, v285);
  if ( inited >= 0 )
  {
    v183 = v338;
    goto LABEL_727;
  }
  v297 = 0x110001404EALL;
LABEL_761:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)inited,
    (int)a6,
    (struct UnionFs::StackEventTracer *)v297,
    (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
    "PUSH: Could not create new path node.",
    v331);
  utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v338);
LABEL_705:
  if ( v341 )
    utl::_RefCountBase::_DecStrong(v341);
  if ( v343[1] )
    utl::_RefCountBase::_DecStrong(v343[1]);
  if ( v511 )
    (*(void (__fastcall **)(_QWORD *))(*v511 + 24LL))(v511);
  wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v349);
  utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v344);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v508, v282);
  if ( v508[16] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v508[16] + 24LL))(v508[16]);
  wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
LABEL_797:
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
LABEL_316:
  if ( v15 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140048244  mov     rax, rsp
0x140048247  mov     [rax+20h], rbx
0x14004824b  push    rbp
0x14004824c  push    rsi
0x14004824d  push    rdi
0x14004824e  push    r12
0x140048250  push    r13
0x140048252  push    r14
0x140048254  push    r15
0x140048256  lea     rbp, [rax-928h]
0x14004825d  sub     rsp, 9F0h
0x140048264  movaps  xmmword ptr [rax-48h], xmm6
0x140048268  mov     rax, cs:__security_cookie
0x14004826f  xor     rax, rsp
0x140048272  mov     [rbp+920h+var_48], rax
0x140048279  mov     r13, [rbp+920h+arg_20]
0x140048280  mov     r10, r8
0x140048283  mov     rbx, [rbp+920h+arg_28]
0x14004828a  mov     r15, rcx
0x14004828d  mov     [rbp+920h+var_8B0], r8
0x140048291  mov     r12, rdx
0x140048294  xor     r8d, r8d
0x140048297  mov     [rbp+920h+var_930], rcx
0x14004829b  mov     rcx, [rbp+920h+arg_40]
0x1400482a2  mov     [rbp+920h+var_970], r8d
0x1400482a6  mov     [rbp+920h+var_890], rdx
0x1400482ad  mov     rdx, [rbp+920h+arg_38]
0x1400482b4  mov     [r13+0], r8d
0x1400482b8  mov     [rbp+920h+var_910], r9
0x1400482bc  mov     [rbp+920h+var_8D8], r13
0x1400482c0  mov     [rbp+920h+var_8B8], rdx
0x1400482c4  mov     [rbp+920h+var_8D0], r8
0x1400482c8  test    rcx, rcx
0x1400482cb  jz      short loc_1400482DE
0x1400482cd  mov     rax, [rcx]
0x1400482d0  mov     rcx, [rcx+8]
0x1400482d4  mov     [rbp+920h+var_900], rcx
0x1400482d8  mov     [rbp+920h+var_8D0], rax
0x1400482dc  jmp     short loc_1400482E5
0x1400482de  mov     [rbp+920h+var_900], r8
0x1400482e2  mov     rax, r8
0x1400482e5  mov     r14d, [rbp+920h+arg_30]
0x1400482ec  mov     ecx, r14d
0x1400482ef  and     ecx, 4
0x1400482f2  mov     [rbp+920h+var_8E0], ecx
0x1400482f5  jz      short loc_1400482FC
0x1400482f7  test    rax, rax
0x1400482fa  jz      short loc_140048305
0x1400482fc  test    rax, rax
0x1400482ff  jz      short loc_140048339
0x140048301  test    ecx, ecx
0x140048303  jnz     short loc_140048339
0x140048305  lea     rax, aOriginInvalidR; "ORIGIN: Invalid root insertion paramete"...
0x14004830c  mov     r8, 4800014005Eh; struct UnionFs::StackEventTracer *
0x140048316  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x14004831d  mov     [rsp+0A20h+var_A00], rax; char *
0x140048322  mov     rdx, rbx; int
0x140048325  mov     ecx, 0C00000E5h; this
0x14004832a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004832f  mov     eax, 0C00000E5h
0x140048334  jmp     loc_14004C5E0
0x140048339  mov     [rbp+920h+var_908], r8d
0x14004833d  xorps   xmm6, xmm6
0x140048340  movdqa  [rbp+920h+var_850], xmm6
0x140048348  test    rdx, rdx
0x14004834b  jz      short loc_140048383
0x14004834d  mov     rdi, [rdx+8]
0x140048351  mov     rcx, [rdx]
0x140048354  mov     [rbp+920h+var_880], rcx
0x14004835b  test    rdi, rdi
0x14004835e  jz      short loc_140048364
0x140048360  lock inc dword ptr [rdi+8]
0x140048364  movzx   eax, word ptr [rdx+10h]
0x140048368  mov     qword ptr [rbp+920h+var_850], rcx
0x14004836f  mov     qword ptr [rbp+920h+var_850+8], rdi
0x140048376  movdqa  xmm6, [rbp+920h+var_850]
0x14004837e  mov     [rbp+920h+var_908], eax
0x140048381  jmp     short loc_140048398
0x140048383  xorps   xmm0, xmm0
0x140048386  movq    [rbp+920h+var_880], xmm6
0x14004838e  psrldq  xmm0, 8
0x140048393  movq    rdi, xmm0
0x140048398  mov     eax, [r15]
0x14004839b  mov     rsi, r8
0x14004839e  mov     [rsp+0A20h+P], r8
0x1400483a3  test    al, 1
0x1400483a5  jz      loc_140048439
0x1400483ab  mov     r9, rbx
0x1400483ae  lea     r8, [rsp+0A20h+P]
0x1400483b3  mov     rdx, r12
0x1400483b6  mov     rcx, r10
0x1400483b9  call    ?MakeShortNameCopy@UfsPathName@UnionFs@@QEBAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::MakeShortNameCopy(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400483be  xor     r8d, r8d
0x1400483c1  mov     esi, eax
0x1400483c3  test    eax, eax
0x1400483c5  jns     short loc_140048434
0x1400483c7  lea     rax, aPushCouldNotGe_1; "PUSH: Could not get short names for pat"...
0x1400483ce  mov     r8, 0D00140070h; struct UnionFs::StackEventTracer *
0x1400483d8  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x1400483df  mov     [rsp+0A20h+var_A00], rax; char *
0x1400483e4  mov     rdx, rbx; int
0x1400483e7  mov     ecx, esi; this
0x1400483e9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400483ee  mov     rbx, [rsp+0A20h+P]
0x1400483f3  xor     r14d, r14d
0x1400483f6  test    rbx, rbx
0x1400483f9  jz      short loc_140048420
0x1400483fb  cmp     [rbx+10h], r14b
0x1400483ff  jnz     short loc_140048407
0x140048401  xorps   xmm0, xmm0
0x140048404  movups  xmmword ptr [rbx], xmm0
0x140048407  mov     rcx, rbx; UnicodeString
0x14004840a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004840f  xor     edx, edx; Tag
0x140048411  mov     rcx, rbx; P
0x140048414  call    cs:__imp_ExFreePoolWithTag
0x14004841b  nop     dword ptr [rax+rax+00h]
0x140048420  test    rdi, rdi
0x140048423  jz      short loc_14004842D
0x140048425  mov     rcx, rdi; this
0x140048428  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004842d  mov     eax, esi
0x14004842f  jmp     loc_14004C5E0
0x140048434  mov     rsi, [rsp+0A20h+P]
0x140048439  mov     [rsp+0A20h+Resource], r8
0x14004843e  test    r14b, 1
0x140048442  jnz     short loc_14004848F
0x140048444  lea     rdx, [r15+20h]
0x140048448  lea     rcx, [rbp+920h+var_808]
0x14004844f  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140048454  mov     rcx, [rsp+0A20h+Resource]; Resource
0x140048459  xor     r8d, r8d
0x14004845c  mov     rax, [rbp+920h+var_808]
0x140048463  mov     [rsp+0A20h+Resource], rax
0x140048468  test    rcx, rcx
0x14004846b  jz      short loc_140048488
0x14004846d  call    cs:__imp_ExReleaseResourceLite
0x140048474  nop     dword ptr [rax+rax+00h]
0x140048479  call    cs:__imp_KeLeaveCriticalRegion
0x140048480  nop     dword ptr [rax+rax+00h]
0x140048485  xor     r8d, r8d
0x140048488  mov     [rbp+920h+var_808], r8
0x14004848f  mov     rdx, [r15+88h]; RunRefCacheAware
0x140048496  lea     r9, [rbp+920h+var_2C0]
0x14004849d  mov     [rbp+920h+var_250], r8
0x1400484a4  lea     rcx, [rbp+920h+var_1D0]; void *
0x1400484ab  mov     r8b, 1
0x1400484ae  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x1400484b3  xor     r14d, r14d
0x1400484b6  cmp     [rbp+920h+var_1D0], r14
0x1400484bd  jnz     loc_14004854B
0x1400484c3  lea     rax, aOriginTableAlr; "ORIGIN: Table already run down"
0x1400484ca  mov     r8, 1BA00140080h; struct UnionFs::StackEventTracer *
0x1400484d4  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x1400484db  mov     [rsp+0A20h+var_A00], rax; char *
0x1400484e0  mov     rdx, rbx; int
0x1400484e3  mov     ecx, 0C0ED000Ah; this
0x1400484e8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400484ed  lea     rcx, [rbp+920h+var_1D0]; this
0x1400484f4  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400484f9  mov     rcx, [rbp+920h+var_150]
0x140048500  xor     ebx, ebx
0x140048502  test    rcx, rcx
0x140048505  jz      short loc_140048513
0x140048507  mov     rax, [rcx]
0x14004850a  mov     rax, [rax+18h]
0x14004850e  call    _guard_dispatch_icall
0x140048513  mov     rcx, [rsp+0A20h+Resource]; Resource
0x140048518  mov     [rsp+0A20h+Resource], rbx
0x14004851d  test    rcx, rcx
0x140048520  jz      short loc_14004853A
0x140048522  call    cs:__imp_ExReleaseResourceLite
0x140048529  nop     dword ptr [rax+rax+00h]
0x14004852e  call    cs:__imp_KeLeaveCriticalRegion
0x140048535  nop     dword ptr [rax+rax+00h]
0x14004853a  test    rsi, rsi
0x14004853d  jz      loc_1400488A2
0x140048543  cmp     [rsi+10h], bl
0x140048546  jmp     loc_140048881
0x14004854b  add     r15, 8
0x14004854f  mov     rax, [r15]
0x140048552  cmp     rax, r15
0x140048555  jz      short loc_140048575
0x140048557  lea     rcx, [rax+10h]
0x14004855b  mov     [rbp+920h+var_8F8], rcx
0x14004855f  mov     rcx, [rcx+8]
0x140048563  cmp     [rcx], r12
0x140048566  jz      short loc_14004856D
0x140048568  mov     rax, [rax]
0x14004856b  jmp     short loc_140048552
0x14004856d  xor     r15d, r15d
0x140048570  jmp     loc_140048721
0x140048575  mov     r8, rbx
0x140048578  mov     [rbp+920h+var_860], r14
0x14004857f  lea     rdx, [rbp+920h+var_860]
0x140048586  mov     rcx, r12; Instance
0x140048589  call    ?AllocAndInit@UfsInstanceTierNode@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsInstanceTierNode@UnionFs@@U?$default_delete@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceTierNode::AllocAndInit(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsInstanceTierNode,utl::default_delete<UnionFs::UfsInstanceTierNode>> &,UnionFs::StackEventTracer &)
0x14004858e  mov     r12d, eax
0x140048591  test    eax, eax
0x140048593  jns     loc_140048689
0x140048599  lea     rax, aPushAllocating_12; "PUSH: Allocating new instance tier node"
0x1400485a0  mov     r8, 6A00140094h; struct UnionFs::StackEventTracer *
0x1400485aa  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x1400485b1  mov     [rsp+0A20h+var_A00], rax; char *
0x1400485b6  mov     rdx, rbx; int
0x1400485b9  mov     ecx, r12d; this
0x1400485bc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400485c1  mov     rbx, [rbp+920h+var_860]
0x1400485c8  test    rbx, rbx
0x1400485cb  jz      short loc_1400485FF
0x1400485cd  mov     rcx, [rbx+8]; Context
0x1400485d1  mov     [rbx+8], r14
0x1400485d5  test    rcx, rcx
0x1400485d8  jz      short loc_1400485E6
0x1400485da  call    cs:__imp_FltReleaseContext
0x1400485e1  nop     dword ptr [rax+rax+00h]
0x1400485e6  mov     rcx, rbx
0x1400485e9  call    ??1?$unique_ptr@VUfsPathTierNode@UnionFs@@U?$default_delete@VUfsPathTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(void)
0x1400485ee  xor     edx, edx; Tag
0x1400485f0  mov     rcx, rbx; P
0x1400485f3  call    cs:__imp_ExFreePoolWithTag
0x1400485fa  nop     dword ptr [rax+rax+00h]
0x1400485ff  lea     rcx, [rbp+920h+var_1D0]; this
0x140048606  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004860b  mov     rcx, [rbp+920h+var_150]
0x140048612  test    rcx, rcx
0x140048615  jz      short loc_140048623
0x140048617  mov     rax, [rcx]
0x14004861a  mov     rax, [rax+18h]
0x14004861e  call    _guard_dispatch_icall
0x140048623  mov     rcx, [rsp+0A20h+Resource]; Resource
0x140048628  mov     [rsp+0A20h+Resource], r14
0x14004862d  test    rcx, rcx
0x140048630  jz      short loc_14004864A
0x140048632  call    cs:__imp_ExReleaseResourceLite
0x140048639  nop     dword ptr [rax+rax+00h]
0x14004863e  call    cs:__imp_KeLeaveCriticalRegion
0x140048645  nop     dword ptr [rax+rax+00h]
0x14004864a  test    rsi, rsi
0x14004864d  jz      short loc_140048674
0x14004864f  cmp     [rsi+10h], r14b
0x140048653  jnz     short loc_14004865B
0x140048655  xorps   xmm0, xmm0
0x140048658  movups  xmmword ptr [rsi], xmm0
0x14004865b  mov     rcx, rsi; UnicodeString
0x14004865e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140048663  xor     edx, edx; Tag
0x140048665  mov     rcx, rsi; P
0x140048668  call    cs:__imp_ExFreePoolWithTag
0x14004866f  nop     dword ptr [rax+rax+00h]
0x140048674  test    rdi, rdi
0x140048677  jz      short loc_140048681
0x140048679  mov     rcx, rdi; this
0x14004867c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140048681  mov     eax, r12d
0x140048684  jmp     loc_14004C5E0
0x140048689  mov     ecx, 28h ; '('; unsigned __int64
0x14004868e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140048693  xor     r12d, r12d
0x140048696  test    rax, rax
0x140048699  jz      loc_14004C4EF
0x14004869f  mov     r14, [rbp+920h+var_860]
0x1400486a6  mov     rcx, [r14]
0x1400486a9  mov     [r14], r12
0x1400486ac  mov     [rax+10h], rcx
0x1400486b0  mov     rcx, [r14+8]
0x1400486b4  mov     [r14+8], r12
0x1400486b8  mov     [rax+18h], rcx
0x1400486bc  mov     [rax+20h], r12w
0x1400486c1  mov     rcx, [r15+8]
0x1400486c5  mov     [rax+8], rcx
0x1400486c9  mov     [rax], r15
0x1400486cc  mov     [rcx], rax
0x1400486cf  mov     rcx, [rbp+920h+var_930]
0x1400486d3  mov     [r15+8], rax
0x1400486d7  inc     qword ptr [r15+10h]
0x1400486db  xor     r15d, r15d
0x1400486de  mov     rdx, [rcx+10h]
0x1400486e2  add     rdx, 10h
0x1400486e6  mov     [rbp+920h+var_8F8], rdx
0x1400486ea  test    r14, r14
0x1400486ed  jz      short loc_140048721
0x1400486ef  mov     rcx, [r14+8]; Context
0x1400486f3  mov     [r14+8], r15
0x1400486f7  test    rcx, rcx
0x1400486fa  jz      short loc_140048708
0x1400486fc  call    cs:__imp_FltReleaseContext
0x140048703  nop     dword ptr [rax+rax+00h]
0x140048708  mov     rcx, r14
0x14004870b  call    ??1?$unique_ptr@VUfsPathTierNode@UnionFs@@U?$default_delete@VUfsPathTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(void)
0x140048710  xor     edx, edx; Tag
0x140048712  mov     rcx, r14; P
0x140048715  call    cs:__imp_ExFreePoolWithTag
0x14004871c  nop     dword ptr [rax+rax+00h]
0x140048721  mov     r12b, r15b
0x140048724  lea     r14, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x14004872b  test    r12b, r12b
0x14004872e  jz      loc_1400488B9
0x140048734  lea     rcx, [rbp+920h+var_1D0]; this
0x14004873b  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
  ... truncated ...
```
