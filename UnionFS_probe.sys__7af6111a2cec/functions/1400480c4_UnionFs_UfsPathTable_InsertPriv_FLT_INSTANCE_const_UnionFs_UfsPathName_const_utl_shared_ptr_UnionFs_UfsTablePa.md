# UnionFs::UfsPathTable::InsertPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,utl::pair<utl::shared_ptr<UnionFs::UfsPathTree>,ushort> *,UnionFs::InsertOptionalParams *)

- ea: `0x1400480c4`
- end: `0x14004c490`
- name: `?InsertPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAU?$pair@V?$shared_ptr@VUfsPathTree@UnionFs@@@utl@@G@6@PEAUInsertOptionalParams@2@@Z`
- size: `17356`
- prototype: ``
- caller_count: `3`
- callee_count: `55`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140047ef8`
- `0x14004c4a0`
- `0x14004dd90`

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
- `0x14000f7fc`
- `0x1400112a8`
- `0x140020078`
- `0x140035a24`
- `0x140035c68`
- `0x140035cb8`
- `0x140035df4`
- `0x1400449c0`
- `0x140044e60`
- `0x140045098`
- `0x140045178`
- `0x140045284`
- `0x1400453b4`
- `0x140045560`
- `0x1400456f8`
- `0x14004577c`
- `0x140045878`
- `0x1400458d0`
- `0x140045bc0`
- `0x140045c54`
- `0x140046014`
- `0x140046134`
- `0x140046198`
- `0x1400464c8`
- `0x140047ddc`
- `0x1400480c4`
- `0x14004e5c8`
- `0x14004e794`
- `0x14004f2d4`
- `0x14004f4ac`
- `0x14004f528`
- `0x14004f5d4`
- `0x140056ac4`
- `0x140056afc`
- `0x1400790f0`
- `0x140079214`
- `0x140079970`
- `0x140079a6c`
- `0x140079afc`
- `0x140079c48`
- `0x140079dcc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140048294`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400484e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048595`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048716`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004988c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004998c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049dcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c2d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c34d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c3cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c444`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048294`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400484e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048595`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048716`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004988c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004998c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049dcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c2d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c34d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c3cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c444`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004879b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004879b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004911f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140049140`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004b8b0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004b8d5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004911f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140049140`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004b8b0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14004b8d5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400482ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400483a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400484b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400485ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400486e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048a01`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048a7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048ac1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048aec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048cba`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048ce7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048fb9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049852`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400499d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049ab1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b06`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049bd3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049cb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049d10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049d92`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004be9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c0a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c19b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c21f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c317`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c40e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400482ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400483a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400484b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400485ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400486e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048a01`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048a7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048ac1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048aec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048cba`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048ce7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048fb9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049852`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400499d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049ab1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b06`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049bd3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049cb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049d10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049d92`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004be9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c0a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c19b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c21f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c317`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c40e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400482f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400483ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400484be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004860b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400486ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048a0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048a88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048acd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048af8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c7c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048cc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048cf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048fc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004985e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400499dd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049abd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049bdf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049cbe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049d1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049d9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004beaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c0b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c1a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c22b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c323`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c41a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400482f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400483ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400484be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004860b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400486ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048a0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048a88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048acd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048af8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c7c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048cc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048cf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048fc5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004985e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400499dd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049abd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049bdf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049cbe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049d1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049d9e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004beaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c0b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c1a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c22b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c323`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c41a`
- `FLTMGR!FltReleaseContext` at `0x14004845a`
- `FLTMGR!FltReleaseContext` at `0x14004857c`
- `FLTMGR!FltReleaseContext` at `0x14004c3b6`
- `FLTMGR!FltReleaseContext` at `0x14004845a`
- `FLTMGR!FltReleaseContext` at `0x14004857c`
- `FLTMGR!FltReleaseContext` at `0x14004c3b6`

## string_xrefs

- `0x140049fa3`: `UnionFs::UfsPathTierNode::ConvertFinalNodeToInner`
- `0x140049fdb`: `UnionFs::UfsPathTierNode::ConvertFinalNodeToInner`
- `0x140048196`: `UnionFs::UfsPathTable::InsertPriv`
- `0x140048258`: `UnionFs::UfsPathTable::InsertPriv`
- `0x140048354`: `UnionFs::UfsPathTable::InsertPriv`
- `0x14004842a`: `UnionFs::UfsPathTable::InsertPriv`
- `0x1400485a4`: `UnionFs::UfsPathTable::InsertPriv`
- `0x14004c384`: `UnionFs::UfsPathTable::InsertPriv`
- `0x140048247`: `PUSH: Could not get short names for path`
- `0x140048343`: `ORIGIN: Table already run down`
- `0x140048687`: `ORIGIN: Table already run down`
- `0x140048bf3`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140048dc0`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140048efa`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x1400497c6`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004a53c`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004a714`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004a80e`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004aea2`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b051`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b12a`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004b3b3`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004bd32`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004bf95`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x1400497d1`: `Preventing insert of metadata path into path table`
- `0x1400487eb`: `moreComponentsLeft == moreShortComponentsLeft`
- `0x14004931a`: `moreComponentsLeft == moreShortComponentsLeft`
- `0x14004bb0a`: `moreComponentsLeft == moreShortComponentsLeft`
- `0x14004990b`: `PUSH: One or more payload nodes already exist in the table.`
- `0x140049a28`: `ORIGIN: \ is already a mapping.`
- `0x140049bfd`: `PUSH: InsertCallback in PathTable.`
- `0x140049e96`: `PUSH: InsertCallback in PathTable.`
- `0x14004a13c`: `PUSH: InsertCallback in PathTable.`
- `0x14004ab8a`: `PUSH: InsertCallback in PathTable.`
- `0x140048c01`: `Inserted payload (replaced invalid volume root)`
- `0x140048dce`: `Inserted payload (replaced invalid volume root)`
- `0x140049cdb`: `ORIGIN: Root node already owned by a union`
- `0x14004902f`: `PUSH: Adding subtree to path tree node`
- `0x14004a8fc`: `PUSH: Adding subtree to path tree node`
- `0x14004b4c5`: `PUSH: Adding subtree to path tree node`
- `0x14004a9df`: `PUSH: Updating stored path length`
- `0x14004b50c`: `PUSH: Updating stored path length`
- `0x14004bc2d`: `PUSH: Updating stored path length`
- `0x14004c024`: `PUSH: Updating stored path length`
- `0x14004b750`: `ORIGIN: Incoming path has an existing short component.`
- `0x14004aaa7`: `ORIGIN: Attempted insert of root on already-owned node`
- `0x14004b5ec`: `ORIGIN: Attempted insert of root on already-owned node`
- `0x14004a54a`: `Inserted payload (replaced invalid)`
- `0x14004a722`: `Inserted payload (replaced invalid)`
- `0x14004ab54`: `ORIGIN: Path is already in table`
- `0x14004b535`: `ORIGIN: Attempted insert into union root node`
- `0x14004b215`: `ORIGIN: Node already has payload`
- `0x140049f72`: `PUSH: Payload node already exists along this path, nested paths not allowed.`
- `0x14004bb95`: `PUSH: Could not create new path node.`
- `0x14004b885`: `curInsertNode->IsFinal() || moreComponentsLeft || nextLevelTree`
- `0x14004b955`: `PUSH: Could not create new short name path node.`
- `0x14004ba51`: `!curInsertNode->IsFinal()`

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
  int ShortNameCopy; // eax
  int v21; // esi
  struct _UNICODE_STRING *v22; // rdx
  struct _UNICODE_STRING *v23; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v24; // rdx
  UnionFs::UfsInstanceTierNode *v25; // rdx
  unsigned __int16 v26; // r9
  struct FsFltWil::Details::RundownRefCacheAware *v27; // rdx
  struct _UNICODE_STRING *v28; // rdx
  struct _ERESOURCE *v29; // rcx
  bool v30; // zf
  __int64 **v31; // r15
  __int64 **i; // rax
  const struct std::nothrow_t *v33; // rdx
  int v34; // r12d
  struct FsFltWil::Details::RundownRefCacheAware *v35; // rdx
  PVOID v36; // rbx
  void *v37; // rcx
  struct _UNICODE_STRING *v38; // rdx
  struct _ERESOURCE *v39; // rcx
  bool v40; // zf
  __int64 ***v41; // rax
  _QWORD *v42; // r14
  __int64 **v43; // rcx
  __int64 **v44; // rcx
  __int64 *v45; // rcx
  const char *v46; // rcx
  void *v47; // rcx
  char v48; // r12
  const char *v49; // r12
  struct _ERESOURCE *v50; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v51; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v52; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v53; // rdx
  struct _ERESOURCE *v54; // rcx
  struct _UNICODE_STRING *v55; // r8
  int v56; // r9d
  bool v57; // r15
  BOOLEAN v58; // al
  int v59; // r8d
  struct FsFltWil::Details::RundownRefCacheAware *v60; // rdx
  int v61; // eax
  struct _UNICODE_STRING *Buffer_low; // r8
  bool v63; // r15
  struct UnionFs::UfsPathTierNode *v64; // r12
  __int64 v65; // r8
  UnionFs::UfsPathTree *v66; // rcx
  utl::_RefCountBase *v67; // r8
  unsigned int v68; // r9d
  bool IsEmpty; // r15
  int inited; // r15d
  volatile signed __int32 *v71; // r15
  struct UnionFs::UfsPathTierNode *v72; // rcx
  volatile signed __int32 *v73; // r12
  int v74; // ecx
  struct _ERESOURCE *v75; // rcx
  struct _ERESOURCE *v76; // rcx
  struct _ERESOURCE **v77; // rax
  struct _ERESOURCE *v78; // rcx
  struct _ERESOURCE *v79; // rax
  struct _ERESOURCE *v80; // rcx
  struct UnionFs::UfsPathTierNode *v81; // r8
  __int64 *v82; // r12
  __int64 v83; // rax
  int v84; // r8d
  int v85; // r9d
  const struct _UNICODE_STRING *v86; // rax
  struct _ERESOURCE *v87; // rcx
  struct _ERESOURCE **v88; // rax
  struct _ERESOURCE *v89; // rcx
  struct _ERESOURCE *v90; // rax
  struct _ERESOURCE *v91; // rcx
  __int64 *v92; // r12
  __int64 v93; // rax
  int v94; // r8d
  int v95; // r9d
  const struct _UNICODE_STRING *v96; // rax
  volatile signed __int32 *v97; // rax
  int v98; // r8d
  int v99; // r9d
  const struct _UNICODE_STRING *v100; // rax
  utl::_RefCountBase *v101; // rcx
  struct _ERESOURCE *v102; // rcx
  UnionFs::UfsInstanceTierNode *v103; // r15
  const char *v104; // r15
  __int64 OwningUnion; // rax
  volatile signed __int32 *v106; // rax
  UnionFs::UfsPathTree *v107; // r13
  int v108; // r12d
  const char *v109; // rax
  struct _UNICODE_STRING *v110; // r8
  struct UnionFs::UfsPathTierNode *Node; // r15
  struct UnionFs::UfsPathTierNode *v112; // r13
  char v113; // r15
  __int64 v114; // rcx
  int v115; // r12d
  _BYTE *v116; // r13
  volatile signed __int32 *v117; // r15
  int v118; // eax
  struct _ERESOURCE *v119; // rdx
  FsFltWil::Details *v120; // rcx
  __int64 v121; // rax
  struct _UNICODE_STRING *v122; // r8
  bool v123; // r15
  __int64 v124; // rax
  __int64 *v125; // r12
  volatile signed __int32 *v126; // rax
  UnionFs::UfsPathTree *v127; // rax
  volatile signed __int32 *v128; // rcx
  FsFltWil::Details **v129; // rcx
  _BYTE *v130; // r12
  volatile signed __int32 *v131; // r13
  struct _ERESOURCE *v132; // rdx
  int v133; // eax
  FsFltWil::Details *v134; // rcx
  bool v135; // r15
  utl::_RefCountBase **v136; // rax
  bool v137; // r15
  _BYTE *v138; // r12
  __int64 v139; // rax
  struct _ERESOURCE *v140; // rdx
  int v141; // eax
  _BYTE *v142; // r13
  int v143; // r13d
  const struct _UNICODE_STRING *v144; // rax
  struct _UNICODE_STRING *v145; // rdx
  struct _ERESOURCE *v146; // rcx
  bool v147; // zf
  UnionFs::UfsPathTierNode *m; // rbx
  struct FsFltWil::Details::RundownRefCacheAware *v149; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v150; // rdx
  UnionFs::UfsPathTierNode *k; // rbx
  PVOID v152; // r8
  _QWORD *v153; // rcx
  __int64 v154; // rax
  struct _UNICODE_STRING *v155; // rdx
  struct _ERESOURCE *v156; // rcx
  bool v157; // zf
  struct FsFltWil::Details::RundownRefCacheAware *v158; // rdx
  struct _ERESOURCE *v159; // rcx
  struct _ERESOURCE *v160; // rcx
  PERESOURCE v161; // rax
  utl::_RefCountBase *v162; // rcx
  struct _ERESOURCE *v163; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v164; // rdx
  struct _ERESOURCE *v165; // rcx
  struct _ERESOURCE *v166; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v167; // rdx
  struct _ERESOURCE *v168; // rcx
  struct _ERESOURCE *v169; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v170; // rdx
  struct _UNICODE_STRING *v171; // rdx
  struct _ERESOURCE *v172; // rcx
  _DWORD *v173; // rsi
  FsFltWil::Details **v174; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v175; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v176; // rdx
  int v177; // edx
  const char *v178; // rax
  __int64 v179; // r8
  struct UnionFs::UfsPathTierNode *v180; // rcx
  __int64 v181; // rax
  volatile signed __int32 *v182; // rax
  bool v183; // r15
  struct UnionFs::UfsPathTierNode *v184; // r15
  __int64 *v185; // r12
  struct _ERESOURCE *v186; // rdx
  FsFltWil::Details *v187; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v188; // rdx
  struct _ERESOURCE *v189; // rdx
  FsFltWil::Details *v190; // rcx
  FsFltWil::Details *v191; // rcx
  __int64 v192; // rax
  FsFltWil::Details *v193; // rcx
  _DWORD *v194; // rsi
  struct _ERESOURCE *v195; // rdx
  utl::_RefCountBase *v196; // rcx
  FsFltWil::Details *v197; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v198; // rdx
  struct _ERESOURCE *v199; // rdx
  FsFltWil::Details *v200; // rcx
  __int64 v201; // r8
  struct _ERESOURCE *v202; // rdx
  FsFltWil::Details *v203; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v204; // rdx
  struct _ERESOURCE *v205; // rdx
  FsFltWil::Details *v206; // rcx
  __int64 *v207; // rsi
  __int64 v208; // rax
  int v209; // r8d
  int v210; // r9d
  struct UnionFs::UfsPathTierNode *v211; // r13
  __int64 v212; // rax
  const struct _UNICODE_STRING *v213; // rax
  FsFltWil::Details *v214; // rcx
  __int64 v215; // rax
  struct _ERESOURCE *v216; // rdx
  int v217; // r8d
  int v218; // r9d
  FsFltWil::Details *v219; // rcx
  __int64 *v220; // rsi
  __int64 v221; // rax
  int v222; // r8d
  int v223; // r9d
  struct UnionFs::UfsPathTierNode *v224; // r13
  __int64 v225; // rax
  const struct _UNICODE_STRING *v226; // rax
  const struct _UNICODE_STRING *v227; // rax
  _DWORD *v228; // rsi
  _DWORD *v229; // rcx
  utl::_RefCountBase *v230; // rcx
  struct _ERESOURCE *v231; // rdx
  FsFltWil::Details *v232; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v233; // rdx
  struct _ERESOURCE *v234; // rdx
  FsFltWil::Details *v235; // rcx
  int v236; // eax
  struct _ERESOURCE *v237; // rdx
  FsFltWil::Details *v238; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v239; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v240; // rdx
  struct _ERESOURCE *v241; // rdx
  FsFltWil::Details *v242; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v243; // rdx
  FsFltWil::Details *v244; // rcx
  __int64 v245; // rax
  _DWORD *v246; // rsi
  __int64 v247; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v248; // rdx
  __int64 *v249; // rsi
  __int64 v250; // rax
  int v251; // r8d
  int v252; // r9d
  struct UnionFs::UfsPathTierNode *v253; // r13
  __int64 v254; // rax
  const struct _UNICODE_STRING *v255; // rax
  FsFltWil::Details *v256; // rcx
  __int64 v257; // rax
  int v258; // r8d
  int v259; // r9d
  __int64 *v260; // rsi
  __int64 v261; // rax
  int v262; // r8d
  int v263; // r9d
  struct UnionFs::UfsPathTierNode *v264; // r13
  __int64 v265; // rax
  const struct _UNICODE_STRING *v266; // rax
  const struct _UNICODE_STRING *v267; // rax
  _DWORD *v268; // rsi
  _DWORD *v269; // rcx
  __int64 *v270; // r12
  __int64 v271; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v272; // rdx
  struct UnionFs::UfsPathTierNode *v273; // r13
  __int64 v274; // rax
  int v275; // r8d
  int v276; // r9d
  const struct _UNICODE_STRING *v277; // rax
  struct UnionFs::UfsPathTierNode *v278; // r13
  const char *v279; // r12
  int v280; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v281; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v282; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v283; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v284; // rdx
  struct _ERESOURCE *v285; // rcx
  unsigned __int64 v286; // rcx
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // r8
  unsigned __int64 v290; // rcx
  __int64 v291; // rax
  struct UnionFs::UfsPathTierNode *v292; // r8
  char *v293; // rax
  volatile signed __int32 *v294; // rax
  UnionFs::Utils *v295; // r12
  struct _UNICODE_STRING *v296; // r8
  struct _UNICODE_STRING *v297; // r8
  __int64 v298; // r8
  int v299; // eax
  int v300; // r8d
  int v301; // r9d
  int v302; // eax
  const struct _UNICODE_STRING *v303; // rax
  utl::_RefCountBase *v304; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v305; // rdx
  const struct UnionFs::UfsUnionCtx **v306; // r15
  volatile signed __int32 *v307; // rsi
  __int64 v308; // rdx
  struct UnionFs::UfsPathTierNode *v309; // rcx
  const struct UnionFs::UfsUnionCtx **v310; // rdx
  int v311; // r8d
  int v312; // r9d
  const struct _UNICODE_STRING *v313; // rax
  int updated; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v315; // rdx
  struct _ERESOURCE *v316; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v317; // rdx
  struct _ERESOURCE *v318; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v319; // rdx
  struct _ERESOURCE *v320; // rcx
  UnionFs::UfsPathTierNode *j; // rbx
  PVOID v322; // rcx
  _QWORD *v323; // rdx
  __int64 v324; // rax
  struct _UNICODE_STRING *v325; // rdx
  struct _ERESOURCE *v326; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v327; // rdx
  PVOID v328; // rbx
  void *v329; // rcx
  struct _UNICODE_STRING *v330; // rdx
  struct _ERESOURCE *v331; // rcx
  char *v332; // [rsp+30h] [rbp-D8h]
  __int64 v333; // [rsp+68h] [rbp-A0h] BYREF
  PERESOURCE Resource; // [rsp+70h] [rbp-98h] BYREF
  _BOOL8 v335; // [rsp+78h] [rbp-90h]
  PVOID P; // [rsp+80h] [rbp-88h] BYREF
  bool v337; // [rsp+88h] [rbp-80h]
  struct UnionFs::UfsPathTierNode *v338; // [rsp+90h] [rbp-78h] BYREF
  struct UnionFs::UfsPathTierNode *v339; // [rsp+98h] [rbp-70h] BYREF
  FsFltWil::Details *v340; // [rsp+A0h] [rbp-68h] BYREF
  UnionFs::UfsPathTree *v341; // [rsp+A8h] [rbp-60h] BYREF
  utl::_RefCountBase *v342; // [rsp+B0h] [rbp-58h]
  unsigned int v343; // [rsp+B8h] [rbp-50h] BYREF
  utl::_RefCountBase *v344[2]; // [rsp+C0h] [rbp-48h] BYREF
  PVOID v345[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v346; // [rsp+E0h] [rbp-28h]
  PERESOURCE v347; // [rsp+E8h] [rbp-20h] BYREF
  FsFltWil::Details *v348; // [rsp+F0h] [rbp-18h] BYREF
  const char *v349; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v350[2]; // [rsp+100h] [rbp-8h] BYREF
  char v351; // [rsp+110h] [rbp+8h]
  __int64 *v352; // [rsp+118h] [rbp+10h] BYREF
  int v353; // [rsp+120h] [rbp+18h] BYREF
  struct UnionFs::UfsPathTierNode *v354; // [rsp+128h] [rbp+20h] BYREF
  UnionFs::UfsInstanceTierNode *v355; // [rsp+130h] [rbp+28h] BYREF
  __int128 v356; // [rsp+138h] [rbp+30h] BYREF
  int v357; // [rsp+148h] [rbp+40h] BYREF
  _DWORD *v358; // [rsp+150h] [rbp+48h]
  const struct UnionFs::UfsUnionCtx **v359; // [rsp+158h] [rbp+50h] BYREF
  FsFltWil::Details *v360; // [rsp+160h] [rbp+58h] BYREF
  __int64 v361; // [rsp+168h] [rbp+60h] BYREF
  const struct _UNICODE_STRING *v362; // [rsp+170h] [rbp+68h] BYREF
  UnionFs::Utils *v363; // [rsp+178h] [rbp+70h] BYREF
  int v364; // [rsp+180h] [rbp+78h] BYREF
  UNICODE_STRING String1; // [rsp+188h] [rbp+80h] BYREF
  FsFltWil::Details *v366; // [rsp+198h] [rbp+90h] BYREF
  FsFltWil::Details *v367; // [rsp+1A8h] [rbp+A0h] BYREF
  UNICODE_STRING SourceString; // [rsp+1B8h] [rbp+B0h] BYREF
  PVOID v369; // [rsp+1C8h] [rbp+C0h]
  utl::_RefCountBase *v370; // [rsp+1D0h] [rbp+C8h] BYREF
  __m128i v371; // [rsp+1D8h] [rbp+D0h] BYREF
  int v372; // [rsp+1E8h] [rbp+E0h] BYREF
  const char *v373; // [rsp+1F0h] [rbp+E8h] BYREF
  int v374; // [rsp+1F8h] [rbp+F0h] BYREF
  int v375; // [rsp+1FCh] [rbp+F4h] BYREF
  _QWORD v376[2]; // [rsp+200h] [rbp+F8h] BYREF
  int v377; // [rsp+210h] [rbp+108h] BYREF
  const char *v378; // [rsp+218h] [rbp+110h] BYREF
  struct _ERESOURCE *v379; // [rsp+220h] [rbp+118h] BYREF
  struct _ERESOURCE *v380; // [rsp+228h] [rbp+120h] BYREF
  PERESOURCE v381; // [rsp+230h] [rbp+128h] BYREF
  PERESOURCE v382; // [rsp+238h] [rbp+130h] BYREF
  _QWORD v383[3]; // [rsp+240h] [rbp+138h] BYREF
  __int128 v384; // [rsp+258h] [rbp+150h] BYREF
  PVOID *v385; // [rsp+268h] [rbp+160h] BYREF
  unsigned int v386; // [rsp+270h] [rbp+168h]
  const struct _UNICODE_STRING *v387; // [rsp+278h] [rbp+170h] BYREF
  __int64 v388; // [rsp+280h] [rbp+178h] BYREF
  struct UnionFs::UfsPathTierNode *v389; // [rsp+288h] [rbp+180h] BYREF
  const char *v390; // [rsp+290h] [rbp+188h] BYREF
  char v391[8]; // [rsp+298h] [rbp+190h] BYREF
  const char *v392; // [rsp+2A0h] [rbp+198h] BYREF
  char v393[8]; // [rsp+2A8h] [rbp+1A0h] BYREF
  char v394[8]; // [rsp+2B0h] [rbp+1A8h] BYREF
  const char *v395; // [rsp+2B8h] [rbp+1B0h] BYREF
  const struct _UNICODE_STRING *v396; // [rsp+2C0h] [rbp+1B8h] BYREF
  __int64 v397; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE *v398; // [rsp+2D0h] [rbp+1C8h] BYREF
  const char *v399; // [rsp+2D8h] [rbp+1D0h] BYREF
  const char *v400; // [rsp+2E0h] [rbp+1D8h] BYREF
  const char *v401; // [rsp+2E8h] [rbp+1E0h] BYREF
  const struct _UNICODE_STRING *v402; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int64 v403; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE *v404; // [rsp+300h] [rbp+1F8h] BYREF
  const char *v405; // [rsp+308h] [rbp+200h] BYREF
  const char *v406; // [rsp+310h] [rbp+208h] BYREF
  const char *v407; // [rsp+318h] [rbp+210h] BYREF
  const struct _UNICODE_STRING *v408; // [rsp+320h] [rbp+218h] BYREF
  __int64 v409; // [rsp+328h] [rbp+220h] BYREF
  _BYTE *v410; // [rsp+330h] [rbp+228h] BYREF
  const char *v411; // [rsp+338h] [rbp+230h] BYREF
  char v412[8]; // [rsp+340h] [rbp+238h] BYREF
  char v413[8]; // [rsp+348h] [rbp+240h] BYREF
  const struct _UNICODE_STRING *v414; // [rsp+350h] [rbp+248h] BYREF
  __int64 v415; // [rsp+358h] [rbp+250h] BYREF
  const char *v416; // [rsp+360h] [rbp+258h] BYREF
  const char *v417; // [rsp+368h] [rbp+260h] BYREF
  const char *v418; // [rsp+370h] [rbp+268h] BYREF
  char v419[8]; // [rsp+378h] [rbp+270h] BYREF
  const struct _UNICODE_STRING *v420; // [rsp+380h] [rbp+278h] BYREF
  __int64 v421; // [rsp+388h] [rbp+280h] BYREF
  const char *v422; // [rsp+390h] [rbp+288h] BYREF
  const char *v423; // [rsp+398h] [rbp+290h] BYREF
  const char *v424; // [rsp+3A0h] [rbp+298h] BYREF
  const struct _UNICODE_STRING *v425; // [rsp+3A8h] [rbp+2A0h] BYREF
  __int64 v426; // [rsp+3B0h] [rbp+2A8h] BYREF
  _BYTE *v427; // [rsp+3B8h] [rbp+2B0h] BYREF
  const char *v428; // [rsp+3C0h] [rbp+2B8h] BYREF
  const char *v429; // [rsp+3C8h] [rbp+2C0h] BYREF
  const char *v430; // [rsp+3D0h] [rbp+2C8h] BYREF
  const struct _UNICODE_STRING *v431; // [rsp+3D8h] [rbp+2D0h] BYREF
  __int64 v432; // [rsp+3E0h] [rbp+2D8h] BYREF
  const char *v433; // [rsp+3E8h] [rbp+2E0h] BYREF
  char v434[8]; // [rsp+3F0h] [rbp+2E8h] BYREF
  const char *v435; // [rsp+3F8h] [rbp+2F0h] BYREF
  const struct _UNICODE_STRING *v436; // [rsp+400h] [rbp+2F8h] BYREF
  __int64 v437; // [rsp+408h] [rbp+300h] BYREF
  const char *v438; // [rsp+410h] [rbp+308h] BYREF
  const char *v439; // [rsp+418h] [rbp+310h] BYREF
  const char *v440; // [rsp+420h] [rbp+318h] BYREF
  const struct _UNICODE_STRING *v441; // [rsp+428h] [rbp+320h] BYREF
  __int64 v442; // [rsp+430h] [rbp+328h] BYREF
  const char *v443; // [rsp+438h] [rbp+330h] BYREF
  const char *v444; // [rsp+440h] [rbp+338h] BYREF
  const char *v445; // [rsp+448h] [rbp+340h] BYREF
  const struct _UNICODE_STRING *v446; // [rsp+450h] [rbp+348h] BYREF
  __int64 v447; // [rsp+458h] [rbp+350h] BYREF
  struct UnionFs::UfsPathTierNode *v448; // [rsp+460h] [rbp+358h] BYREF
  const char *v449; // [rsp+468h] [rbp+360h] BYREF
  const char *v450; // [rsp+470h] [rbp+368h] BYREF
  const char *v451; // [rsp+478h] [rbp+370h] BYREF
  const struct _UNICODE_STRING *v452; // [rsp+480h] [rbp+378h] BYREF
  __int64 v453; // [rsp+488h] [rbp+380h] BYREF
  struct UnionFs::UfsPathTierNode *v454; // [rsp+490h] [rbp+388h] BYREF
  const char *v455; // [rsp+498h] [rbp+390h] BYREF
  __int64 v456; // [rsp+4A0h] [rbp+398h] BYREF
  utl::_RefCountBase *v457; // [rsp+4A8h] [rbp+3A0h]
  __int128 v458; // [rsp+4B8h] [rbp+3B0h] BYREF
  __int64 v459; // [rsp+4C8h] [rbp+3C0h] BYREF
  utl::_RefCountBase *v460; // [rsp+4D0h] [rbp+3C8h]
  __int128 v461; // [rsp+4D8h] [rbp+3D0h] BYREF
  __int64 v462; // [rsp+4E8h] [rbp+3E0h] BYREF
  utl::_RefCountBase *v463; // [rsp+4F0h] [rbp+3E8h]
  __int128 v464; // [rsp+4F8h] [rbp+3F0h] BYREF
  utl::_RefCountBase *v465[2]; // [rsp+508h] [rbp+400h] BYREF
  const char *v466; // [rsp+518h] [rbp+410h] BYREF
  const char *v467; // [rsp+520h] [rbp+418h] BYREF
  _QWORD v468[2]; // [rsp+528h] [rbp+420h] BYREF
  _QWORD v469[2]; // [rsp+538h] [rbp+430h] BYREF
  _QWORD v470[2]; // [rsp+548h] [rbp+440h] BYREF
  _QWORD v471[2]; // [rsp+558h] [rbp+450h] BYREF
  _QWORD v472[2]; // [rsp+568h] [rbp+460h] BYREF
  _QWORD v473[2]; // [rsp+578h] [rbp+470h] BYREF
  _QWORD v474[2]; // [rsp+588h] [rbp+480h] BYREF
  _QWORD v475[2]; // [rsp+598h] [rbp+490h] BYREF
  _QWORD v476[2]; // [rsp+5A8h] [rbp+4A0h] BYREF
  _QWORD v477[2]; // [rsp+5B8h] [rbp+4B0h] BYREF
  _QWORD v478[2]; // [rsp+5C8h] [rbp+4C0h] BYREF
  _QWORD v479[2]; // [rsp+5D8h] [rbp+4D0h] BYREF
  _QWORD v480[2]; // [rsp+5E8h] [rbp+4E0h] BYREF
  _QWORD v481[2]; // [rsp+5F8h] [rbp+4F0h] BYREF
  _QWORD v482[2]; // [rsp+608h] [rbp+500h] BYREF
  _QWORD v483[2]; // [rsp+618h] [rbp+510h] BYREF
  _QWORD v484[8]; // [rsp+628h] [rbp+520h] BYREF
  _QWORD v485[2]; // [rsp+668h] [rbp+560h] BYREF
  _QWORD v486[2]; // [rsp+678h] [rbp+570h] BYREF
  _QWORD v487[2]; // [rsp+688h] [rbp+580h] BYREF
  char v488[8]; // [rsp+698h] [rbp+590h] BYREF
  utl::_RefCountBase *v489; // [rsp+6A0h] [rbp+598h]
  char v490[8]; // [rsp+6A8h] [rbp+5A0h] BYREF
  utl::_RefCountBase *v491; // [rsp+6B0h] [rbp+5A8h]
  __int128 v492; // [rsp+6B8h] [rbp+5B0h] BYREF
  char v493[8]; // [rsp+6C8h] [rbp+5C0h] BYREF
  utl::_RefCountBase *v494; // [rsp+6D0h] [rbp+5C8h]
  char v495[8]; // [rsp+6D8h] [rbp+5D0h] BYREF
  utl::_RefCountBase *v496; // [rsp+6E0h] [rbp+5D8h]
  char v497[8]; // [rsp+6E8h] [rbp+5E0h] BYREF
  utl::_RefCountBase *v498; // [rsp+6F0h] [rbp+5E8h]
  char v499[8]; // [rsp+6F8h] [rbp+5F0h] BYREF
  utl::_RefCountBase *v500; // [rsp+700h] [rbp+5F8h]
  __int128 v501; // [rsp+708h] [rbp+600h] BYREF
  __m128i v502; // [rsp+718h] [rbp+610h] BYREF
  __m128i v503; // [rsp+728h] [rbp+620h] BYREF
  __m128i v504; // [rsp+738h] [rbp+630h] BYREF
  __int128 v505; // [rsp+748h] [rbp+640h] BYREF
  struct _UNICODE_STRING v506; // [rsp+758h] [rbp+650h] BYREF
  __int64 v507; // [rsp+7D8h] [rbp+6D0h]
  __int64 v508; // [rsp+850h] [rbp+748h]
  _QWORD v509[17]; // [rsp+858h] [rbp+750h] BYREF
  char v510[8]; // [rsp+8E0h] [rbp+7D8h] BYREF
  _QWORD v511[13]; // [rsp+8E8h] [rbp+7E0h] BYREF
  _QWORD *v512; // [rsp+950h] [rbp+848h]
  _BYTE v513[128]; // [rsp+958h] [rbp+850h] BYREF
  __int64 v514; // [rsp+9D8h] [rbp+8D0h]

  v9 = a5;
  v363 = a3;
  v349 = (const char *)a1;
  v343 = 0;
  v366 = a2;
  *a5 = 0;
  v352 = a4;
  v358 = a5;
  v362 = (const struct _UNICODE_STRING *)a8;
  v359 = 0;
  if ( a9 )
  {
    v12 = *(const struct UnionFs::UfsUnionCtx ***)a9;
    v354 = *(struct UnionFs::UfsPathTierNode **)(a9 + 8);
    v359 = v12;
  }
  else
  {
    v354 = 0;
    v12 = 0;
  }
  v357 = a7 & 4;
  if ( (a7 & 4) != 0 && !v12 || v12 && (a7 & 4) == 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC00000E5LL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x4800014005ELL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "ORIGIN: Invalid root insertion parameters",
      v332);
    return 3221225701LL;
  }
  v353 = 0;
  v14 = 0;
  v371 = 0;
  if ( a8 )
  {
    v15 = *(volatile signed __int32 **)(a8 + 8);
    v16 = *(FsFltWil::Details **)a8;
    v367 = *(FsFltWil::Details **)a8;
    if ( v15 )
      _InterlockedIncrement(v15 + 2);
    v17 = *(unsigned __int16 *)(a8 + 16);
    v371.m128i_i64[0] = (__int64)v16;
    v371.m128i_i64[1] = (__int64)v15;
    v14 = _mm_load_si128(&v371);
    v353 = v17;
  }
  else
  {
    v367 = 0;
    v15 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  }
  v18 = *a1;
  v19 = 0;
  P = 0;
  if ( (v18 & 1) != 0 )
  {
    ShortNameCopy = UnionFs::UfsPathName::MakeShortNameCopy(a3, a2, &P, a6);
    v21 = ShortNameCopy;
    if ( ShortNameCopy < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)ShortNameCopy,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xD00140070LL,
        (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
        "PUSH: Could not get short names for path",
        v332);
      v23 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v23, v22);
        ExFreePoolWithTag(v23, 0);
      }
      goto LABEL_21;
    }
    v19 = (struct _UNICODE_STRING *)P;
  }
  Resource = 0;
  if ( (a7 & 1) == 0 )
  {
    FsFltWil::AcquireResourceExclusive(&v379, a1 + 8);
    Resource = v379;
    v379 = 0;
  }
  v24 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 17);
  v507 = 0;
  FsFltWil::AcquireRundownReference(v509, v24);
  if ( !v509[0] )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED000ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x1BA00140080LL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "ORIGIN: Table already run down",
      v332);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v27);
    if ( v509[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
    v29 = Resource;
    Resource = 0;
    if ( v29 )
    {
      ExReleaseResourceLite(v29);
      KeLeaveCriticalRegion();
    }
    if ( !v19 )
      goto LABEL_77;
    v30 = LOBYTE(v19[1].Length) == 0;
LABEL_74:
    if ( v30 )
      *v19 = 0;
    FsFltWil::Details::FreeUnicodeString(v19, v28);
    ExFreePoolWithTag(v19, 0);
LABEL_77:
    if ( v15 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
    return 3236757514LL;
  }
  v31 = (__int64 **)(a1 + 2);
  for ( i = (__int64 **)*v31; i != v31; i = (__int64 **)*i )
  {
    v355 = (UnionFs::UfsInstanceTierNode *)(i + 2);
    if ( (FsFltWil::Details *)*i[3] == a2 )
      goto LABEL_61;
  }
  v369 = 0;
  v34 = UnionFs::UfsInstanceTierNode::AllocAndInit(a2);
  if ( v34 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v34,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x6A00140094LL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "PUSH: Allocating new instance tier node",
      v332);
    v36 = v369;
    if ( v369 )
    {
      v37 = (void *)*((_QWORD *)v369 + 1);
      *((_QWORD *)v369 + 1) = 0;
      if ( v37 )
        FltReleaseContext(v37);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v36);
      ExFreePoolWithTag(v36, 0);
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v35);
    if ( v509[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
    v39 = Resource;
    Resource = 0;
    if ( v39 )
    {
      ExReleaseResourceLite(v39);
      KeLeaveCriticalRegion();
    }
    if ( !v19 )
      goto LABEL_53;
    v40 = LOBYTE(v19[1].Length) == 0;
    goto LABEL_50;
  }
  v41 = (__int64 ***)operator new(0x28u, v33);
  if ( !v41 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0xCA0014009ALL,
      (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
      "ORIGIN: Saving new instance tier node",
      v332);
    v328 = v369;
    if ( v369 )
    {
      v329 = (void *)*((_QWORD *)v369 + 1);
      *((_QWORD *)v369 + 1) = 0;
      if ( v329 )
        FltReleaseContext(v329);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v328);
      ExFreePoolWithTag(v328, 0);
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v327);
    if ( v509[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
    v331 = Resource;
    Resource = 0;
    if ( v331 )
    {
      ExReleaseResourceLite(v331);
      KeLeaveCriticalRegion();
    }
    if ( v19 )
    {
      if ( !LOBYTE(v19[1].Length) )
        *v19 = 0;
      FsFltWil::Details::FreeUnicodeString(v19, v330);
      ExFreePoolWithTag(v19, 0);
    }
    if ( v15 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
    return 3221225626LL;
  }
  v42 = v369;
  v43 = *(__int64 ***)v369;
  *(_QWORD *)v369 = 0;
  v41[2] = v43;
  v44 = (__int64 **)v42[1];
  v42[1] = 0;
  v41[3] = v44;
  *((_WORD *)v41 + 16) = 0;
  v45 = v31[1];
  v41[1] = (__int64 **)v45;
  *v41 = v31;
  *v45 = (__int64)v41;
  v46 = v349;
  v31[1] = (__int64 *)v41;
  v31[2] = (__int64 *)((char *)v31[2] + 1);
  v25 = (UnionFs::UfsInstanceTierNode *)(*((_QWORD *)v46 + 2) + 16LL);
  v355 = v25;
  if ( v42 )
  {
    v47 = (void *)v42[1];
    v42[1] = 0;
    if ( v47 )
      FltReleaseContext(v47);
    utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v42);
    ExFreePoolWithTag(v42, 0);
  }
LABEL_61:
  v48 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v48 )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v25);
        memset(v509, 0, sizeof(v509));
        v49 = v349;
        FsFltWil::AcquireResourceExclusive(&v380, v349 + 32);
        v50 = Resource;
        Resource = v380;
        if ( v50 )
        {
          ExReleaseResourceLite(v50);
          KeLeaveCriticalRegion();
        }
        v51 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v49 + 17);
        v380 = 0;
        v508 = 0;
        FsFltWil::AcquireRundownReference(v513, v51);
        wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(
          (FsFltWil::Details *)v509,
          v513);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v513, v52);
        if ( v514 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v514 + 24LL))(v514);
        if ( !v509[0] )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0ED000ALL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x454001400B4LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "ORIGIN: Table already run down",
            v332);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v53);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v54 = Resource;
          Resource = 0;
          if ( v54 )
          {
            ExReleaseResourceLite(v54);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_77;
          v30 = LOBYTE(v19[1].Length) == 0;
          goto LABEL_74;
        }
      }
      else
      {
        v49 = v349;
      }
      String1 = 0;
      v55 = (struct _UNICODE_STRING *)*((unsigned __int16 *)v363 + 12);
      v505 = *(_OWORD *)v363;
      v57 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v505, &String1, v55, v26);
      LOBYTE(v335) = v57;
      v356 = *(_OWORD *)v363;
      if ( (a7 & 0x20) != 0 )
      {
        v58 = RtlEqualUnicodeString(&String1, &UnionFs::g_ExtendComponent, 1u);
        v60 = 0;
        if ( v58 )
        {
          if ( (unsigned int)dword_14009E178 > 3
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v144 = (const struct _UNICODE_STRING *)&v356;
            v357 = 196;
            if ( !*((_QWORD *)&v356 + 1) )
              v144 = &FsTlEmptyUnicodeString;
            v349 = "UnionFs::UfsPathTable::InsertPriv";
            v362 = v144;
            v355 = (UnionFs::UfsInstanceTierNode *)"onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v395 = "Preventing insert of metadata path into path table";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)qword_140097C90,
              v59,
              v56,
              (__int64)&v395,
              (__int64)&v349,
              (__int64)&v355,
              (__int64)&v357,
              (__int64)&v362);
          }
          *v9 = 4;
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v60);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v146 = Resource;
          Resource = 0;
          if ( v146 )
          {
            ExReleaseResourceLite(v146);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_839;
          v147 = LOBYTE(v19[1].Length) == 0;
          goto LABEL_291;
        }
      }
      v61 = *(_DWORD *)v49;
      SourceString = 0;
      if ( (v61 & 1) != 0 )
      {
        Buffer_low = (struct _UNICODE_STRING *)LOWORD(v19[1].Buffer);
        v506 = *v19;
        if ( v57 != UnionFs::Utils::WalkPath((UnionFs::Utils *)&v506, &SourceString, Buffer_low, v56) )
          MicrosoftTelemetryAssertTriggeredMsgKM("moreComponentsLeft == moreShortComponentsLeft");
      }
      v345[0] = v345;
      v345[1] = v345;
      LOBYTE(v333) = 0;
      v385 = v345;
      v63 = String1.Length == 0;
      v373 = v49;
      v376[0] = v345;
      v376[1] = &v359;
      v350[0] = v345;
      v350[1] = &v359;
      v511[0] = off_14007EA70;
      v511[1] = &v359;
      v512 = v511;
      v346 = 0;
      v337 = String1.Length == 0;
      v386 = a7;
      v64 = *(struct UnionFs::UfsPathTierNode **)v355;
      v339 = *(struct UnionFs::UfsPathTierNode **)v355;
      v351 = 1;
      *(_OWORD *)v344 = 0;
      if ( String1.Length )
        break;
      if ( !v357 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000E5LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x48400140152LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Accidental insertion at volume root.",
          v332);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        for ( j = (UnionFs::UfsPathTierNode *)v345[0];
              j != (UnionFs::UfsPathTierNode *)v345;
              j = *(UnionFs::UfsPathTierNode **)j )
        {
          UnionFs::UfsPathTierNode::RemoveDependentUnion(*((UnionFs::UfsPathTierNode **)j + 2), *v359);
        }
        while ( 1 )
        {
          v322 = v345[0];
          if ( v345[0] == v345 )
            break;
          v323 = (_QWORD *)*((_QWORD *)v345[0] + 1);
          v324 = *(_QWORD *)v345[0];
          *v323 = *(_QWORD *)v345[0];
          *(_QWORD *)(v324 + 8) = v323;
          ExFreePoolWithTag(v322, 0);
        }
        v346 = 0;
        goto LABEL_850;
      }
      v65 = *((_QWORD *)v64 + 7);
      v66 = (UnionFs::UfsPathTree *)*((_QWORD *)v64 + 6);
      if ( v65 )
        _InterlockedIncrement((volatile signed __int32 *)(v65 + 8));
      IsEmpty = UnionFs::UfsPathTree::IsEmpty(v66);
      if ( v67 )
      {
        utl::_RefCountBase::_DecStrong(v67);
        v68 = a7;
      }
      if ( !IsEmpty )
      {
        inited = lambda_c5291e2bd2658c1720c6c0fd9196e103_::operator()(&v373, v68, a6);
        if ( inited < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)inited,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x2100014015BLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: One or more payload nodes already exist in the table.",
            v332);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          for ( k = (UnionFs::UfsPathTierNode *)v345[0];
                k != (UnionFs::UfsPathTierNode *)v345;
                k = *(UnionFs::UfsPathTierNode **)k )
          {
            UnionFs::UfsPathTierNode::RemoveDependentUnion(*((UnionFs::UfsPathTierNode **)k + 2), *v359);
          }
          while ( 1 )
          {
            v152 = v345[0];
            if ( v345[0] == v345 )
              break;
            v153 = (_QWORD *)*((_QWORD *)v345[0] + 1);
            v154 = *(_QWORD *)v345[0];
            *v153 = *(_QWORD *)v345[0];
            *(_QWORD *)(v154 + 8) = v153;
            ExFreePoolWithTag(v152, 0);
          }
          v346 = 0;
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v150);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v156 = Resource;
          Resource = 0;
          if ( v156 )
          {
            ExReleaseResourceLite(v156);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_316;
          v157 = LOBYTE(v19[1].Length) == 0;
LABEL_313:
          if ( v157 )
            *v19 = 0;
          FsFltWil::Details::FreeUnicodeString(v19, v155);
          ExFreePoolWithTag(v19, 0);
          goto LABEL_316;
        }
        if ( !*((_QWORD *)v64 + 8) && !*((_QWORD *)v64 + 15) )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000E5LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x49200140166LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "ORIGIN: Missing volume root node with other nodes in table",
            v332);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          for ( m = (UnionFs::UfsPathTierNode *)v345[0];
                m != (UnionFs::UfsPathTierNode *)v345;
                m = *(UnionFs::UfsPathTierNode **)m )
          {
            UnionFs::UfsPathTierNode::RemoveDependentUnion(*((UnionFs::UfsPathTierNode **)m + 2), *v359);
          }
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
LABEL_850:
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v149);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v326 = Resource;
          Resource = 0;
          if ( v326 )
          {
            ExReleaseResourceLite(v326);
            KeLeaveCriticalRegion();
          }
          if ( v19 )
          {
            if ( !LOBYTE(v19[1].Length) )
              *v19 = 0;
            FsFltWil::Details::FreeUnicodeString(v19, v325);
            ExFreePoolWithTag(v19, 0);
          }
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return 3221225701LL;
        }
      }
      v63 = v337;
LABEL_99:
      if ( !UnionFs::UfsInstanceTierNode::HasVolumeRootMapping(v355) )
      {
        if ( v63 )
        {
          v306 = v359;
          v307 = (volatile signed __int32 *)v352[1];
          v308 = *v352;
          if ( v307 )
            _InterlockedIncrement(v307 + 2);
          v485[0] = v308;
          v485[1] = v307;
          v309 = *(struct UnionFs::UfsPathTierNode **)v355;
          if ( v307 )
            _InterlockedIncrement(v307 + 2);
          UnionFs::UfsPathTierNode::SetPayload(v309, v485);
          v310 = v306;
          v103 = v355;
          UnionFs::UfsPathTierNode::SetOwningUnion(*(_QWORD *)v355, v310);
          if ( v307 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v307);
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v313 = (const struct _UNICODE_STRING *)&v356;
            LODWORD(v338) = 498;
            if ( !*((_QWORD *)&v356 + 1) )
              v313 = &FsTlEmptyUnicodeString;
            v444 = "UnionFs::UfsPathTable::InsertPriv";
            v441 = v313;
            v442 = *v352;
            v443 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v445 = "Inserted payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_14009781E,
              v311,
              v312,
              (__int64)&v445,
              (__int64)&v444,
              (__int64)&v443,
              (__int64)&v338,
              (__int64)&v442,
              (__int64)&v441);
          }
          *v9 = 1;
LABEL_173:
          if ( v362 )
          {
            v104 = v349;
            v15 = 0;
            v504 = v14;
            v21 = UnionFs::UfsPathTable::AddOrReplaceSubtree(v349, v64, &v504, a6, 0);
            if ( v21 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v21,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x3C000140204LL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Adding subtree to path tree node",
                v332);
LABEL_813:
              if ( v512 )
                (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
              wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
              utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
              FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v315);
              if ( v509[16] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
              v316 = Resource;
              Resource = 0;
              if ( v316 )
              {
                ExReleaseResourceLite(v316);
                KeLeaveCriticalRegion();
              }
              goto LABEL_819;
            }
            updated = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v355, v353, a6);
            v21 = updated;
            if ( updated < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)updated,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x4400014020ALL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Updating stored path length",
                v332);
              goto LABEL_813;
            }
          }
          else
          {
            if ( *(_WORD *)v363 > *((_WORD *)v103 + 8) )
              *((_WORD *)v103 + 8) = *(_WORD *)v363;
            v104 = v349;
          }
          if ( *v9 != 1 || (v21 = UnionFs::UfsPathTable::Traverse(v104, v366, v510, a6, 10), v21 >= 0) )
          {
            if ( v512 )
              (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
            wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
            utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v319);
            if ( v509[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
            v320 = Resource;
            Resource = 0;
            if ( v320 )
            {
              ExReleaseResourceLite(v320);
              KeLeaveCriticalRegion();
            }
            goto LABEL_838;
          }
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v21,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x5FE0014021BLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: Applying owner to descendants of root",
            v332);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v317);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v318 = Resource;
          Resource = 0;
          if ( v318 )
          {
            ExReleaseResourceLite(v318);
            KeLeaveCriticalRegion();
          }
          goto LABEL_831;
        }
        goto LABEL_177;
      }
      if ( v63 && (*(_DWORD *)v349 & 4) == 0 )
      {
        inited = -1073741811;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000000DLL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0xE00140175LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: \\ is already a mapping.",
          v332);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v158);
        if ( v509[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
        v159 = Resource;
        Resource = 0;
        if ( v159 )
        {
          ExReleaseResourceLite(v159);
          KeLeaveCriticalRegion();
        }
        if ( !v19 )
          goto LABEL_316;
        v157 = LOBYTE(v19[1].Length) == 0;
        goto LABEL_313;
      }
      v71 = (volatile signed __int32 *)*((_QWORD *)v64 + 9);
      v72 = (struct UnionFs::UfsPathTierNode *)*((_QWORD *)v64 + 8);
      v338 = v72;
      v73 = v71 + 2;
      v361 = (__int64)(v71 + 2);
      if ( v71 )
        _InterlockedIncrement(v73);
      else
        v361 = 8;
      (*(void (__fastcall **)(struct UnionFs::UfsPathTierNode *, PERESOURCE *))(*(_QWORD *)v72 + 8LL))(v72, &v347);
      v74 = (int)v354;
      v486[0] = &v347;
      v486[1] = &Resource;
      if ( !v354 )
        goto LABEL_127;
      v487[0] = v338;
      v487[1] = v71;
      if ( v71 )
        _InterlockedIncrement(v73);
      v34 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
              v74,
              (unsigned int)v487,
              (unsigned int)&v333,
              (unsigned int)v486,
              (__int64)a6);
      if ( v34 != -1073741267 )
      {
        if ( v34 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v34,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x1000014018CLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v332);
          v166 = v347;
          v347 = 0;
          if ( v166 )
          {
            ExReleaseResourceLite(v166);
            KeLeaveCriticalRegion();
          }
          if ( v71 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v71);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v167);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v168 = Resource;
          Resource = 0;
          if ( v168 )
          {
            ExReleaseResourceLite(v168);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_53;
          v40 = LOBYTE(v19[1].Length) == 0;
LABEL_50:
          if ( v40 )
            *v19 = 0;
          FsFltWil::Details::FreeUnicodeString(v19, v38);
          ExFreePoolWithTag(v19, 0);
LABEL_53:
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return (unsigned int)v34;
        }
        if ( (_BYTE)v333 )
        {
          v76 = v347;
          v347 = 0;
          if ( v76 )
          {
            ExReleaseResourceLite(v76);
            KeLeaveCriticalRegion();
          }
          v77 = (struct _ERESOURCE **)(*(__int64 (__fastcall **)(struct UnionFs::UfsPathTierNode *, PERESOURCE *))(*(_QWORD *)v338 + 16LL))(
                                        v338,
                                        &v381);
          v78 = *v77;
          *v77 = 0;
          v79 = v347;
          v347 = v78;
          if ( v79 )
          {
            ExReleaseResourceLite(v79);
            KeLeaveCriticalRegion();
          }
          v80 = v381;
          v381 = 0;
          if ( v80 )
          {
            ExReleaseResourceLite(v80);
            KeLeaveCriticalRegion();
          }
          v81 = v338;
          if ( !*((_BYTE *)v338 + 8) )
          {
            LOBYTE(v333) = 0;
            v73 = (volatile signed __int32 *)v361;
            goto LABEL_128;
          }
          v30 = String1.Length == 0;
          *v9 = 3;
          *((_BYTE *)v9 + 32) = !v30;
          v160 = (struct _ERESOURCE *)*((_QWORD *)v9 + 1);
          v161 = v347;
          v347 = 0;
          *((_QWORD *)v9 + 1) = v161;
          if ( v160 )
          {
            ExReleaseResourceLite(v160);
            KeLeaveCriticalRegion();
            v81 = v338;
          }
          if ( v71 )
            _InterlockedIncrement((volatile signed __int32 *)v361);
          *((_QWORD *)v9 + 2) = v81;
          v162 = (utl::_RefCountBase *)*((_QWORD *)v9 + 3);
          *((_QWORD *)v9 + 3) = v71;
          if ( v162 )
            utl::_RefCountBase::_DecStrong(v162);
          v163 = v347;
          v347 = 0;
          if ( v163 )
          {
            ExReleaseResourceLite(v163);
            KeLeaveCriticalRegion();
          }
          if ( v71 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v71);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v164);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v165 = Resource;
          Resource = 0;
          if ( v165 )
          {
            ExReleaseResourceLite(v165);
            KeLeaveCriticalRegion();
          }
          if ( !v19 )
            goto LABEL_839;
          v147 = LOBYTE(v19[1].Length) == 0;
LABEL_291:
          if ( v147 )
            *v19 = 0;
          FsFltWil::Details::FreeUnicodeString(v19, v145);
          ExFreePoolWithTag(v19, 0);
          goto LABEL_839;
        }
        v73 = (volatile signed __int32 *)v361;
LABEL_127:
        v81 = v338;
LABEL_128:
        if ( v337 )
        {
          if ( !*((_BYTE *)v81 + 8) )
          {
            v82 = v352;
            v468[0] = *v352;
            v83 = v352[1];
            v468[1] = v83;
            if ( v83 )
              _InterlockedIncrement((volatile signed __int32 *)(v83 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v339, v468);
            if ( (unsigned int)dword_14009E178 > 5
              && (qword_14009E188 & 0x10) != 0
              && (qword_14009E190 & 0x10) == qword_14009E190 )
            {
              v86 = (const struct _UNICODE_STRING *)&v356;
              v372 = 442;
              if ( !*((_QWORD *)&v356 + 1) )
                v86 = &FsTlEmptyUnicodeString;
              v450 = "UnionFs::UfsPathTable::InsertPriv";
              v446 = v86;
              v447 = *v82;
              v448 = v338;
              v449 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
              v451 = "Inserted payload (replaced invalid volume root)";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (unsigned int)&FsTlEmptyUnicodeString,
                (unsigned int)&byte_140097CD7,
                v84,
                v85,
                (__int64)&v451,
                (__int64)&v450,
                (__int64)&v449,
                (__int64)&v372,
                (__int64)&v448,
                (__int64)&v447,
                (__int64)&v446);
            }
            goto LABEL_153;
          }
          v87 = v347;
          v347 = 0;
          if ( v87 )
          {
            ExReleaseResourceLite(v87);
            KeLeaveCriticalRegion();
            v81 = v338;
          }
          v88 = (struct _ERESOURCE **)(*(__int64 (__fastcall **)(struct UnionFs::UfsPathTierNode *, PERESOURCE *))(*(_QWORD *)v81 + 16LL))(
                                        v81,
                                        &v382);
          v89 = *v88;
          *v88 = 0;
          v90 = v347;
          v347 = v89;
          if ( v90 )
          {
            ExReleaseResourceLite(v90);
            KeLeaveCriticalRegion();
          }
          v91 = v382;
          v382 = 0;
          if ( v91 )
          {
            ExReleaseResourceLite(v91);
            KeLeaveCriticalRegion();
          }
          if ( *((_BYTE *)v338 + 8) )
          {
            v97 = *(volatile signed __int32 **)UnionFs::UfsPathTierNode::GetOwningUnion(v339, v488);
            v361 = (__int64)v97;
            if ( v489 )
            {
              utl::_RefCountBase::_DecStrong(v489);
              v97 = (volatile signed __int32 *)v361;
            }
            if ( v97 )
            {
              UnionFs::ProcessTraceStatusOrigin(
                (UnionFs *)0xC0ED0001LL,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x486001401DALL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "ORIGIN: Root node already owned by a union",
                v332);
              v169 = v347;
              v347 = 0;
              if ( v169 )
              {
                ExReleaseResourceLite(v169);
                KeLeaveCriticalRegion();
              }
              if ( v71 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v71);
              if ( v512 )
                (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
              wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
              utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
              FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v170);
              if ( v509[16] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
              v172 = Resource;
              Resource = 0;
              if ( v172 )
              {
                ExReleaseResourceLite(v172);
                KeLeaveCriticalRegion();
              }
              if ( v19 )
              {
                if ( !LOBYTE(v19[1].Length) )
                  *v19 = 0;
                FsFltWil::Details::FreeUnicodeString(v19, v171);
                ExFreePoolWithTag(v19, 0);
              }
              goto LABEL_699;
            }
            if ( (unsigned int)dword_14009E178 > 4
              && (qword_14009E188 & 0x10) != 0
              && (qword_14009E190 & 0x10) == qword_14009E190 )
            {
              v100 = (const struct _UNICODE_STRING *)&v356;
              v375 = 480;
              if ( !*((_QWORD *)&v356 + 1) )
                v100 = &FsTlEmptyUnicodeString;
              *(_QWORD *)v391 = "UnionFs::UfsPathTable::InsertPriv";
              v387 = v100;
              v388 = *v352;
              v389 = v338;
              v390 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
              v392 = "Insert returning existing volume root payload";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (unsigned int)&FsTlEmptyUnicodeString,
                (unsigned int)word_140097642,
                v98,
                v99,
                (__int64)&v392,
                (__int64)v391,
                (__int64)&v390,
                (__int64)&v375,
                (__int64)&v389,
                (__int64)&v388,
                (__int64)&v387);
            }
            *v9 = 2;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v9 + 2,
              &v347);
            if ( v71 )
              _InterlockedIncrement(v73);
            *((_QWORD *)v9 + 2) = v338;
            v101 = (utl::_RefCountBase *)*((_QWORD *)v9 + 3);
            *((_QWORD *)v9 + 3) = v71;
            if ( v101 )
              utl::_RefCountBase::_DecStrong(v101);
          }
          else
          {
            v92 = v352;
            v469[0] = *v352;
            v93 = v352[1];
            v469[1] = v93;
            if ( v93 )
              _InterlockedIncrement((volatile signed __int32 *)(v93 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v339, v469);
            if ( (unsigned int)dword_14009E178 > 5
              && (qword_14009E188 & 0x10) != 0
              && (qword_14009E190 & 0x10) == qword_14009E190 )
            {
              v96 = (const struct _UNICODE_STRING *)&v356;
              v377 = 462;
              if ( !*((_QWORD *)&v356 + 1) )
                v96 = &FsTlEmptyUnicodeString;
              v466 = "UnionFs::UfsPathTable::InsertPriv";
              v452 = v96;
              v453 = *v92;
              v454 = v338;
              v455 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
              v467 = "Inserted payload (replaced invalid volume root)";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
                (unsigned int)&FsTlEmptyUnicodeString,
                (unsigned int)&word_140097986,
                v94,
                v95,
                (__int64)&v467,
                (__int64)&v466,
                (__int64)&v455,
                (__int64)&v377,
                (__int64)&v454,
                (__int64)&v453,
                (__int64)&v452);
            }
LABEL_153:
            *v9 = 1;
          }
        }
        v102 = v347;
        v347 = 0;
        if ( v102 )
        {
          ExReleaseResourceLite(v102);
          KeLeaveCriticalRegion();
        }
        if ( v71 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v71);
        v64 = v339;
        if ( v337 )
        {
          v103 = v355;
          goto LABEL_173;
        }
        goto LABEL_177;
      }
      v75 = v347;
      v347 = 0;
      v48 = 1;
      if ( v75 )
      {
        ExReleaseResourceLite(v75);
        KeLeaveCriticalRegion();
      }
      if ( v71 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v71);
      if ( v512 )
        (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
    }
    if ( v357 )
      goto LABEL_99;
LABEL_177:
    inited = lambda_499e3257b266ccbef4f29b33c513cd89_::operator()(&v385, v64, a6);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x49500140227LL,
        (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
        "PUSH: Adding volume root to intermediate nodes",
        v332);
      if ( v512 )
        (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v305);
      if ( v509[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
      v285 = Resource;
      Resource = 0;
      goto LABEL_795;
    }
    OwningUnion = UnionFs::UfsPathTierNode::GetOwningUnion(v64, v490);
    utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(v344, OwningUnion);
    if ( v491 )
      utl::_RefCountBase::_DecStrong(v491);
    v106 = (volatile signed __int32 *)*((_QWORD *)v64 + 7);
    v107 = (UnionFs::UfsPathTree *)*((_QWORD *)v64 + 6);
    v341 = v107;
    v342 = (utl::_RefCountBase *)v106;
    if ( v106 )
      _InterlockedIncrement(v106 + 2);
    v108 = v343;
    v109 = 0;
LABEL_183:
    v378 = v109;
    v383[1] = 0;
    v383[0] = &String1;
    Node = UnionFs::UfsPathTree::FindNode(v107, (const struct UnionFs::UFS_COMPARE_KEY *)v383);
    v338 = Node;
    if ( (*v349 & 3) == 3
      && RtlCompareUnicodeString(&SourceString, &UnionFs::g_NoShortComponent, 0)
      && RtlCompareUnicodeString(&SourceString, &String1, 0) )
    {
      v383[0] = &SourceString;
      v339 = UnionFs::UfsPathTree::FindNode(v107, (const struct UnionFs::UFS_COMPARE_KEY *)v383);
    }
    else
    {
      v339 = 0;
    }
    if ( !Node )
      goto LABEL_411;
    v112 = Node;
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
        v332);
      if ( v342 )
        utl::_RefCountBase::_DecStrong(v342);
      if ( v344[1] )
        utl::_RefCountBase::_DecStrong(v344[1]);
      if ( v512 )
        (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v284);
      if ( v509[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
      v285 = Resource;
      Resource = 0;
LABEL_795:
      if ( v285 )
      {
        ExReleaseResourceLite(v285);
        KeLeaveCriticalRegion();
      }
      goto LABEL_797;
    }
    v113 = 0;
    if ( v335 )
      break;
    if ( *((_QWORD *)v112 + 6) )
    {
      inited = lambda_c5291e2bd2658c1720c6c0fd9196e103_::operator()(&v373, a7, a6);
      if ( inited < 0 )
      {
        v178 = "PUSH: Current node has descendants";
        v179 = 0x21100140344LL;
LABEL_703:
        v177 = (int)a6;
LABEL_704:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          v177,
          (struct UnionFs::StackEventTracer *)v179,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          v178,
          v332);
        goto LABEL_705;
      }
      v135 = 0;
      if ( (a7 & 4) != 0 )
      {
        v108 |= 2u;
        v343 = v108;
        if ( *(_QWORD *)UnionFs::UfsPathTierNode::GetOwningUnion(v112, v497) )
          v135 = 1;
      }
      if ( (v108 & 2) != 0 )
      {
        v343 = v108 & 0xFFFFFFFD;
        if ( v498 )
          utl::_RefCountBase::_DecStrong(v498);
      }
      if ( v135 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0001LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x4870014034FLL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Attempted insert of root on already-owned node",
          v332);
        if ( v342 )
          utl::_RefCountBase::_DecStrong(v342);
        if ( v344[1] )
          utl::_RefCountBase::_DecStrong(v344[1]);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v282);
        if ( v509[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
LABEL_698:
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
LABEL_699:
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return 3236757505LL;
      }
      v136 = (utl::_RefCountBase **)UnionFs::UfsPathTierNode::GetOwningUnion(v112, v499);
      v137 = v344[0] != *v136;
      if ( v500 )
        utl::_RefCountBase::_DecStrong(v500);
      if ( v137 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED000BLL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x2A90014035ALL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Attempted insert into union root node",
          v332);
        if ( v342 )
          utl::_RefCountBase::_DecStrong(v342);
        if ( v344[1] )
          utl::_RefCountBase::_DecStrong(v344[1]);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v281);
        if ( v509[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return 3236757515LL;
      }
      v117 = (volatile signed __int32 *)*((_QWORD *)v112 + 9);
      v138 = (_BYTE *)*((_QWORD *)v112 + 8);
      *(_QWORD *)&v384 = v138;
      *((_QWORD *)&v384 + 1) = v117;
      if ( v117 )
        _InterlockedIncrement(v117 + 2);
      v348 = 0;
      if ( !v138 )
        goto LABEL_638;
      v139 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v138 + 8LL))(v138, v394);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
        &v348,
        v139);
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v394);
      if ( (*(_DWORD *)v349 & 4) == 0 )
      {
        if ( !v138[8] )
          UnionFs::UfsPathTierNode::ClearPayload(v112);
LABEL_638:
        v270 = v352;
        v483[0] = *v352;
        v271 = v352[1];
        v483[1] = v271;
        if ( v271 )
          _InterlockedIncrement((volatile signed __int32 *)(v271 + 8));
        if ( !(unsigned __int8)UnionFs::UfsPathTierNode::AddPayloadToInnerNode(v112, v483) )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000035LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x21400140408LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "ORIGIN: Node already has payload",
            v332);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v348);
          if ( v117 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
          goto LABEL_643;
        }
        v273 = v339;
        if ( v339 )
        {
          v484[0] = *v270;
          v274 = v270[1];
          v484[1] = v274;
          if ( v274 )
            _InterlockedIncrement((volatile signed __int32 *)(v274 + 8));
          UnionFs::UfsPathTierNode::AddPayloadToInnerNode(v273, v484);
        }
        v21 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v376, a6);
        if ( v21 < 0 )
        {
          v247 = 0x47C00140418LL;
LABEL_588:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v21,
            (int)a6,
            (struct UnionFs::StackEventTracer *)v247,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: Adding dependent union to intermediates",
            v332);
LABEL_589:
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v348);
          if ( v117 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
LABEL_591:
          if ( v342 )
            utl::_RefCountBase::_DecStrong(v342);
          if ( v344[1] )
            utl::_RefCountBase::_DecStrong(v344[1]);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v248);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
LABEL_599:
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
          goto LABEL_831;
        }
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x10) != 0
          && (qword_14009E190 & 0x10) == qword_14009E190 )
        {
          v277 = (const struct _UNICODE_STRING *)&v356;
          LODWORD(v352) = 1053;
          if ( !*((_QWORD *)&v356 + 1) )
            v277 = &FsTlEmptyUnicodeString;
          *(_QWORD *)v434 = "UnionFs::UfsPathTable::InsertPriv";
          v431 = v277;
          v432 = *v270;
          v433 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
          v435 = "Inserted payload";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (unsigned int)&FsTlEmptyUnicodeString,
            (unsigned int)&word_1400978C6,
            v275,
            v276,
            (__int64)&v435,
            (__int64)v434,
            (__int64)&v433,
            (__int64)&v352,
            (__int64)&v432,
            (__int64)&v431);
        }
LABEL_666:
        v268 = v358;
        *v358 = 1;
        goto LABEL_667;
      }
      v141 = (int)v354;
      v142 = v138;
      if ( !v354 )
        goto LABEL_585;
      v473[0] = &v348;
      v473[1] = &Resource;
      v501 = v384;
      if ( v117 )
        _InterlockedIncrement(v117 + 2);
      v143 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
               v141,
               (unsigned int)&v501,
               (unsigned int)&v333,
               (unsigned int)v473,
               (__int64)a6);
      if ( v143 != -1073741267 )
      {
        if ( v143 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v143,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x12600140387LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v332);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v348);
          if ( v117 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
          if ( v342 )
            utl::_RefCountBase::_DecStrong(v342);
          if ( v344[1] )
            utl::_RefCountBase::_DecStrong(v344[1]);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v243);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return (unsigned int)v143;
        }
        if ( (_BYTE)v333 )
        {
          v244 = v348;
          v348 = 0;
          if ( v244 )
            FsFltWil::Details::ReleaseResource(v244, v140);
          v245 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v138 + 16LL))(v138, v413);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            &v348,
            v245);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v413);
          if ( v138[8] )
          {
            v246 = v358;
            *v358 = 3;
            *((_BYTE *)v246 + 32) = 0;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v246 + 2,
              &v348);
            utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v246 + 4, &v384);
LABEL_582:
            v174 = &v348;
            goto LABEL_372;
          }
          LOBYTE(v333) = 0;
        }
        v142 = v138;
LABEL_585:
        if ( !v138[8] )
        {
          v21 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v376, a6);
          if ( v21 < 0 )
          {
            v247 = 0x47A001403AELL;
            goto LABEL_588;
          }
          v249 = v352;
          v479[0] = *v352;
          v250 = v352[1];
          v479[1] = v250;
          if ( v250 )
            _InterlockedIncrement((volatile signed __int32 *)(v250 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v338, v479);
          v253 = v339;
          if ( v339 )
          {
            v480[0] = *v249;
            v254 = v249[1];
            v480[1] = v254;
            if ( v254 )
              _InterlockedIncrement((volatile signed __int32 *)(v254 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v253, v480);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v255 = (const struct _UNICODE_STRING *)&v356;
            LODWORD(v370) = 955;
            if ( !*((_QWORD *)&v356 + 1) )
              v255 = &FsTlEmptyUnicodeString;
            v417 = "UnionFs::UfsPathTable::InsertPriv";
            v414 = v255;
            v415 = *v249;
            v416 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v418 = "Inserted payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&byte_140097D47,
              v251,
              v252,
              (__int64)&v418,
              (__int64)&v417,
              (__int64)&v416,
              (__int64)&v370,
              (__int64)&v415,
              (__int64)&v414);
          }
          goto LABEL_666;
        }
        v256 = v348;
        v348 = 0;
        if ( v256 )
          FsFltWil::Details::ReleaseResource(v256, v140);
        v257 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v142 + 16LL))(v142, v419);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
          &v348,
          v257);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v419);
        if ( !v138[8] )
        {
          v21 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v376, a6);
          if ( v21 < 0 )
          {
            v247 = 0x47B001403D2LL;
            goto LABEL_588;
          }
          v260 = v352;
          v481[0] = *v352;
          v261 = v352[1];
          v481[1] = v261;
          if ( v261 )
            _InterlockedIncrement((volatile signed __int32 *)(v261 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v338, v481);
          v264 = v339;
          if ( v339 )
          {
            v482[0] = *v260;
            v265 = v260[1];
            v482[1] = v265;
            if ( v265 )
              _InterlockedIncrement((volatile signed __int32 *)(v265 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v264, v482);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v266 = (const struct _UNICODE_STRING *)&v356;
            LODWORD(v361) = 991;
            if ( !*((_QWORD *)&v356 + 1) )
              v266 = &FsTlEmptyUnicodeString;
            v423 = "UnionFs::UfsPathTable::InsertPriv";
            v420 = v266;
            v421 = *v260;
            v422 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v424 = "Inserted payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)byte_140097D9B,
              v262,
              v263,
              (__int64)&v424,
              (__int64)&v423,
              (__int64)&v422,
              (__int64)&v361,
              (__int64)&v421,
              (__int64)&v420);
          }
          goto LABEL_666;
        }
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x10) != 0
          && (qword_14009E190 & 0x10) == qword_14009E190 )
        {
          v267 = (const struct _UNICODE_STRING *)&v356;
          v427 = v138;
          if ( !*((_QWORD *)&v356 + 1) )
            v267 = &FsTlEmptyUnicodeString;
          LODWORD(v363) = 1002;
          v425 = v267;
          v429 = "UnionFs::UfsPathTable::InsertPriv";
          v426 = *v352;
          v428 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
          v430 = "Insert returning existing payload";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
            (unsigned int)&FsTlEmptyUnicodeString,
            (unsigned int)word_14009791A,
            v258,
            v259,
            (__int64)&v430,
            (__int64)&v429,
            (__int64)&v428,
            (__int64)&v363,
            (__int64)&v427,
            (__int64)&v426,
            (__int64)&v425);
        }
        v268 = v358;
        v269 = v358 + 2;
        *v358 = 2;
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
          v269,
          &v348);
        utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v268 + 4, &v384);
LABEL_667:
        v278 = v338;
        v279 = v349;
        if ( v357 )
        {
          if ( *v268 == 1 )
          {
            v332 = (char *)a6;
            v21 = UnionFs::UfsPathTable::Traverse(v349, v366, v338);
            if ( v21 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v21,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x48A00140430LL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Applying owning union to inner node and descendants",
                (const char *)a6);
              goto LABEL_589;
            }
          }
        }
        if ( v362 )
        {
          v503 = v14;
          v15 = 0;
          v21 = UnionFs::UfsPathTable::AddOrReplaceSubtree(v279, v278, &v503, a6, v339);
          if ( v21 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v21,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x3BD0014043BLL,
              (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
              "PUSH: Adding subtree to path tree node",
              v332);
            goto LABEL_674;
          }
          v280 = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v355, v353, a6);
          v21 = v280;
          if ( v280 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v280,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x44200140441LL,
              (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
              "PUSH: Updating stored path length",
              v332);
LABEL_674:
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v348);
LABEL_540:
            if ( v117 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
            if ( v342 )
              utl::_RefCountBase::_DecStrong(v342);
            if ( v344[1] )
              utl::_RefCountBase::_DecStrong(v344[1]);
            if ( v512 )
              (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
            wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
            utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v239);
            if ( v509[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
LABEL_819:
            utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
            return (unsigned int)v21;
          }
        }
        v351 = 0;
        goto LABEL_582;
      }
      v129 = &v348;
LABEL_269:
      v48 = 1;
      wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v129);
    }
    else
    {
      if ( !*((_QWORD *)v112 + 8) )
        MicrosoftTelemetryAssertTriggeredMsgKM("Final nodes should have payloads");
      if ( (*(_DWORD *)v349 & 4) == 0 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000035LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x2120014033BLL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Path is already in table",
          v332);
LABEL_643:
        if ( v342 )
          utl::_RefCountBase::_DecStrong(v342);
        if ( v344[1] )
          utl::_RefCountBase::_DecStrong(v344[1]);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v272);
        if ( v509[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return 3221225525LL;
      }
      if ( (a7 & 4) != 0 )
      {
        v108 |= 1u;
        v343 = v108;
        if ( *(_QWORD *)UnionFs::UfsPathTierNode::GetOwningUnion(v112, v495) )
          v113 = 1;
      }
      if ( (v108 & 1) != 0 )
      {
        v343 = v108 & 0xFFFFFFFE;
        if ( v496 )
          utl::_RefCountBase::_DecStrong(v496);
      }
      if ( v113 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0001LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x47600140285LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "ORIGIN: Attempted insert of root on already-owned node",
          v332);
        if ( v342 )
          utl::_RefCountBase::_DecStrong(v342);
        if ( v344[1] )
          utl::_RefCountBase::_DecStrong(v344[1]);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v240);
        if ( v509[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
        v242 = (FsFltWil::Details *)Resource;
        Resource = 0;
        if ( v242 )
          FsFltWil::Details::ReleaseResource(v242, v241);
        goto LABEL_698;
      }
      v117 = (volatile signed __int32 *)*((_QWORD *)v112 + 9);
      v130 = (_BYTE *)*((_QWORD *)v112 + 8);
      v131 = v117 + 2;
      if ( v117 )
        _InterlockedIncrement(v131);
      (*(void (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v130 + 8LL))(v130, &v340);
      v133 = (int)v354;
      if ( !v354 )
        goto LABEL_462;
      v472[0] = v130;
      v471[0] = &v340;
      v471[1] = &Resource;
      v472[1] = v117;
      if ( v117 )
        _InterlockedIncrement(v131);
      v364 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
               v133,
               (unsigned int)v472,
               (unsigned int)&v333,
               (unsigned int)v471,
               (__int64)a6);
      if ( v364 != -1073741267 )
      {
        if ( v364 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v364,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x101001402A7LL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v332);
          v187 = v340;
          v340 = 0;
          if ( v187 )
            FsFltWil::Details::ReleaseResource(v187, v186);
          if ( v117 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
          if ( v342 )
            utl::_RefCountBase::_DecStrong(v342);
          if ( v344[1] )
            utl::_RefCountBase::_DecStrong(v344[1]);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v188);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          v190 = (FsFltWil::Details *)Resource;
          Resource = 0;
          if ( v190 )
            FsFltWil::Details::ReleaseResource(v190, v189);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          if ( v15 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
          return (unsigned int)v364;
        }
        if ( (_BYTE)v333 )
        {
          v191 = v340;
          v340 = 0;
          if ( v191 )
            FsFltWil::Details::ReleaseResource(v191, v132);
          v192 = (*(__int64 (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v130 + 16LL))(v130, &v366);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            &v340,
            v192);
          v193 = v366;
          v366 = 0;
          if ( v193 )
            FsFltWil::Details::ReleaseResource(v193, v132);
          if ( v130[8] )
          {
            v194 = v358;
            *v358 = 3;
            *((_BYTE *)v194 + 32) = 0;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v194 + 2,
              &v340);
            if ( v117 )
              _InterlockedIncrement(v131);
            *((_QWORD *)v194 + 2) = v130;
            v196 = (utl::_RefCountBase *)*((_QWORD *)v194 + 3);
            *((_QWORD *)v194 + 3) = v117;
            if ( v196 )
              utl::_RefCountBase::_DecStrong(v196);
            v197 = v340;
            v340 = 0;
            if ( v197 )
              FsFltWil::Details::ReleaseResource(v197, v195);
            if ( v117 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
            if ( v342 )
              utl::_RefCountBase::_DecStrong(v342);
            if ( v344[1] )
              utl::_RefCountBase::_DecStrong(v344[1]);
            if ( v512 )
              (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
            wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
            utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v198);
            if ( v509[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
            v200 = (FsFltWil::Details *)Resource;
            Resource = 0;
            if ( v200 )
              FsFltWil::Details::ReleaseResource(v200, v199);
            goto LABEL_838;
          }
          LOBYTE(v333) = 0;
        }
LABEL_462:
        if ( !v130[8] )
        {
          v21 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v376, a6);
          if ( v21 < 0 )
          {
            v201 = 0x478001402D7LL;
            goto LABEL_465;
          }
          v207 = v352;
          v475[0] = *v352;
          v208 = v352[1];
          v475[1] = v208;
          if ( v208 )
            _InterlockedIncrement((volatile signed __int32 *)(v208 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v338, v475);
          v211 = v339;
          if ( v339 )
          {
            v476[0] = *v207;
            v212 = v207[1];
            v476[1] = v212;
            if ( v212 )
              _InterlockedIncrement((volatile signed __int32 *)(v212 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v211, v476);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v398 = v130;
            v213 = (const struct _UNICODE_STRING *)&v356;
            v364 = 742;
            if ( !*((_QWORD *)&v356 + 1) )
              v213 = &FsTlEmptyUnicodeString;
            v400 = "UnionFs::UfsPathTable::InsertPriv";
            v396 = v213;
            v397 = *v207;
            v399 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v401 = "Inserted payload (replaced invalid)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&unk_140097C20,
              v209,
              v210,
              (__int64)&v401,
              (__int64)&v400,
              (__int64)&v399,
              (__int64)&v364,
              (__int64)&v398,
              (__int64)&v397,
              (__int64)&v396);
          }
LABEL_510:
          *v358 = 1;
LABEL_521:
          if ( v362 )
          {
            v15 = 0;
            v502 = v14;
            v21 = UnionFs::UfsPathTable::AddOrReplaceSubtree(v349, v338, &v502, a6, v339);
            if ( v21 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v21,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x3C900140328LL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Adding subtree to path tree node",
                v332);
              v232 = v340;
              v340 = 0;
              if ( v232 )
                FsFltWil::Details::ReleaseResource(v232, v231);
              if ( v117 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
              if ( v342 )
                utl::_RefCountBase::_DecStrong(v342);
              if ( v344[1] )
                utl::_RefCountBase::_DecStrong(v344[1]);
              if ( v512 )
                (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
              wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
              utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
              FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v233);
              if ( v509[16] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
              v235 = (FsFltWil::Details *)Resource;
              Resource = 0;
              if ( v235 )
                FsFltWil::Details::ReleaseResource(v235, v234);
              goto LABEL_819;
            }
            v236 = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v355, v353, a6);
            v21 = v236;
            if ( v236 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v236,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x4410014032ELL,
                (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
                "PUSH: Updating stored path length",
                v332);
              v238 = v340;
              v340 = 0;
              if ( v238 )
                FsFltWil::Details::ReleaseResource(v238, v237);
              goto LABEL_540;
            }
          }
          v351 = 0;
          v174 = &v340;
LABEL_372:
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v174);
          if ( v117 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
          if ( v342 )
            utl::_RefCountBase::_DecStrong(v342);
          if ( v344[1] )
            utl::_RefCountBase::_DecStrong(v344[1]);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v175);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          goto LABEL_382;
        }
        v214 = v340;
        v340 = 0;
        if ( v214 )
          FsFltWil::Details::ReleaseResource(v214, v132);
        v215 = (*(__int64 (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v130 + 16LL))(v130, &v367);
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
          &v340,
          v215);
        v219 = v367;
        v367 = 0;
        if ( v219 )
          FsFltWil::Details::ReleaseResource(v219, v216);
        if ( v130[8] )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v227 = (const struct _UNICODE_STRING *)&v356;
            v410 = v130;
            if ( !*((_QWORD *)&v356 + 1) )
              v227 = &FsTlEmptyUnicodeString;
            v374 = 791;
            v408 = v227;
            *(_QWORD *)v412 = "UnionFs::UfsPathTable::InsertPriv";
            v409 = *v352;
            v411 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v378 = "Insert returning existing payload";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_140097A66,
              v217,
              v218,
              (__int64)&v378,
              (__int64)v412,
              (__int64)&v411,
              (__int64)&v374,
              (__int64)&v410,
              (__int64)&v409,
              (__int64)&v408);
          }
          v228 = v358;
          v229 = v358 + 2;
          *v358 = 2;
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            v229,
            &v340);
          if ( v117 )
            _InterlockedIncrement(v131);
          *((_QWORD *)v228 + 2) = v130;
          v230 = (utl::_RefCountBase *)*((_QWORD *)v228 + 3);
          *((_QWORD *)v228 + 3) = v117;
          if ( v230 )
            utl::_RefCountBase::_DecStrong(v230);
          goto LABEL_521;
        }
        v21 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v376, a6);
        if ( v21 >= 0 )
        {
          v220 = v352;
          v477[0] = *v352;
          v221 = v352[1];
          v477[1] = v221;
          if ( v221 )
            _InterlockedIncrement((volatile signed __int32 *)(v221 + 8));
          UnionFs::UfsPathTierNode::SetPayload(v338, v477);
          v224 = v339;
          if ( v339 )
          {
            v478[0] = *v220;
            v225 = v220[1];
            v478[1] = v225;
            if ( v225 )
              _InterlockedIncrement((volatile signed __int32 *)(v225 + 8));
            UnionFs::UfsPathTierNode::SetPayload(v224, v478);
          }
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v404 = v130;
            v226 = (const struct _UNICODE_STRING *)&v356;
            v343 = 780;
            if ( !*((_QWORD *)&v356 + 1) )
              v226 = &FsTlEmptyUnicodeString;
            v406 = "UnionFs::UfsPathTable::InsertPriv";
            v402 = v226;
            v403 = *v220;
            v405 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v407 = "Inserted payload (replaced invalid)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_1400979F6,
              v222,
              v223,
              (__int64)&v407,
              (__int64)&v406,
              (__int64)&v405,
              (__int64)&v343,
              (__int64)&v404,
              (__int64)&v403,
              (__int64)&v402);
          }
          goto LABEL_510;
        }
        v201 = 0x479001402FDLL;
LABEL_465:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v21,
          (int)a6,
          (struct UnionFs::StackEventTracer *)v201,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "PUSH: Adding dependent union to intermediates",
          v332);
        v203 = v340;
        v340 = 0;
        if ( v203 )
          FsFltWil::Details::ReleaseResource(v203, v202);
        if ( v117 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
        if ( v342 )
          utl::_RefCountBase::_DecStrong(v342);
        if ( v344[1] )
          utl::_RefCountBase::_DecStrong(v344[1]);
        if ( v512 )
          (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
        wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v204);
        if ( v509[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
        v206 = (FsFltWil::Details *)Resource;
        Resource = 0;
        if ( v206 )
          FsFltWil::Details::ReleaseResource(v206, v205);
LABEL_831:
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
LABEL_21:
        if ( v15 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
        return (unsigned int)v21;
      }
      v134 = v340;
      v340 = 0;
      v48 = 1;
      if ( v134 )
        FsFltWil::Details::ReleaseResource(v134, v132);
    }
    if ( v117 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
    if ( v342 )
      utl::_RefCountBase::_DecStrong(v342);
    if ( v344[1] )
      utl::_RefCountBase::_DecStrong(v344[1]);
    if ( v512 )
      (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
    wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
    utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
    v9 = v358;
  }
  v114 = *((_QWORD *)v112 + 8);
  if ( v114 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v114 + 48LL))(v114) )
    {
      v115 = (int)v354;
      if ( v354 )
      {
        v116 = (_BYTE *)*((_QWORD *)v112 + 8);
        *(_QWORD *)&v458 = v116;
        v117 = (volatile signed __int32 *)*((_QWORD *)v338 + 9);
        *((_QWORD *)&v458 + 1) = v117;
        if ( v117 )
          _InterlockedIncrement(v117 + 2);
        (*(void (__fastcall **)(_BYTE *, FsFltWil::Details **))(*(_QWORD *)v116 + 8LL))(v116, &v360);
        v470[0] = &v360;
        v470[1] = &Resource;
        v492 = v458;
        if ( v117 )
          _InterlockedIncrement(v117 + 2);
        v118 = wistd::function<long (utl::shared_ptr<UnionFs::UfsTablePayload>,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)>::operator()(
                 v115,
                 (unsigned int)&v492,
                 (unsigned int)&v333,
                 (unsigned int)v470,
                 (__int64)a6);
        v34 = v118;
        if ( v118 == -1073741267 )
        {
          v129 = &v360;
          goto LABEL_269;
        }
        if ( v118 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v118,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x2080014045DLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: InsertCallback in PathTable.",
            v332);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v360);
          if ( v117 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
LABEL_385:
          if ( v342 )
            utl::_RefCountBase::_DecStrong(v342);
          if ( v344[1] )
            utl::_RefCountBase::_DecStrong(v344[1]);
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v176);
          if ( v509[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&Resource);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          goto LABEL_53;
        }
        if ( (_BYTE)v333 )
        {
          v120 = v360;
          v360 = 0;
          if ( v120 )
            FsFltWil::Details::ReleaseResource(v120, v119);
          v121 = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v116 + 16LL))(v116, v393);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
            &v360,
            v121);
          wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(v393);
          if ( v116[8] )
          {
            v173 = v358;
            *v358 = 3;
            *((_BYTE *)v173 + 32) = 1;
            wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::operator=(
              v173 + 2,
              &v360);
            utl::shared_ptr<UnionFs::UfsPathTree>::operator=(v173 + 4, &v458);
            v174 = &v360;
            goto LABEL_372;
          }
          LOBYTE(v333) = 0;
        }
        wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>::~unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&void FsFltWil::Details::ReleaseResource(_ERESOURCE *)>>(&v360);
        if ( v117 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
        v112 = v338;
      }
    }
  }
  v123 = UnionFs::Utils::WalkPathName(v363, (const struct UnionFs::UfsPathName *)&String1, v110);
  LOBYTE(v335) = v123;
  if ( (*(_DWORD *)v349 & 1) != 0
    && v123 != UnionFs::Utils::WalkPathName(
                 (UnionFs::Utils *)v19,
                 (const struct UnionFs::UfsPathName *)&SourceString,
                 v122) )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("moreComponentsLeft == moreShortComponentsLeft");
  }
  inited = lambda_499e3257b266ccbef4f29b33c513cd89_::operator()(&v385, v112, a6);
  if ( inited < 0 )
  {
    v178 = "PUSH: Updating intermediateNodes";
    v179 = 0x48200140486LL;
    goto LABEL_703;
  }
  v124 = UnionFs::UfsPathTierNode::GetOwningUnion(v112, v493);
  utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(v344, v124);
  if ( v494 )
    utl::_RefCountBase::_DecStrong(v494);
  v125 = (__int64 *)((char *)v112 + 48);
  if ( *((_QWORD *)v112 + 6) )
  {
    v456 = *v125;
    v126 = (volatile signed __int32 *)*((_QWORD *)v112 + 7);
    v457 = (utl::_RefCountBase *)v126;
    if ( v126 )
      _InterlockedIncrement(v126 + 2);
    utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(&v341, &v456);
    if ( v457 )
      utl::_RefCountBase::_DecStrong(v457);
    v107 = v341;
    v108 = v343;
    if ( !v339 )
      goto LABEL_224;
    v108 = v343 | 4;
    v343 |= 4u;
    v127 = (UnionFs::UfsPathTree *)*((_QWORD *)v339 + 6);
    v128 = (volatile signed __int32 *)*((_QWORD *)v339 + 7);
    v370 = (utl::_RefCountBase *)v128;
    if ( v128 )
      _InterlockedIncrement(v128 + 2);
    if ( v127 != v107 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Short name node should have same descendant tree.");
LABEL_224:
      v128 = (volatile signed __int32 *)v370;
    }
    v109 = (const char *)v338;
    if ( (v108 & 4) != 0 )
    {
      v108 &= ~4u;
      v343 = v108;
      if ( v128 )
      {
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v128);
        v109 = (const char *)v338;
      }
    }
    goto LABEL_183;
  }
  inited = lambda_c5291e2bd2658c1720c6c0fd9196e103_::operator()(&v373, a7, a6);
  v177 = (int)a6;
  if ( inited < 0 )
  {
    v178 = "PUSH: Payload node already exists along this path, nested paths not allowed.";
    v179 = 0x11001404A0LL;
    goto LABEL_704;
  }
  if ( *v125 )
  {
    inited = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x21600150144LL,
      (unsigned __int64)"UnionFs::UfsPathTierNode::ConvertFinalNodeToInner",
      "ORIGIN: Node is not final",
      v332);
LABEL_400:
    v178 = "PUSH: Converting final node to inner.";
    v179 = 0x218001404A8LL;
    goto LABEL_703;
  }
  inited = UnionFs::UfsPathTree::AllocAndInitShared(v125, a6);
  if ( inited < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inited,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x21700150149LL,
      (unsigned __int64)"UnionFs::UfsPathTierNode::ConvertFinalNodeToInner",
      "PUSH: Allocating m_NextLevelTree",
      v332);
    goto LABEL_400;
  }
  v180 = v339;
  if ( v339 )
  {
    v474[0] = *v125;
    v181 = *((_QWORD *)v112 + 7);
    v474[1] = v181;
    if ( v181 )
      _InterlockedIncrement((volatile signed __int32 *)(v181 + 8));
    inited = UnionFs::UfsPathTierNode::ConvertFinalNodeToInner(v180, v474, a6);
    if ( inited < 0 )
    {
      v178 = "PUSH: Adding descendant tree to short name node.";
      v179 = 0x21A001404B2LL;
      goto LABEL_703;
    }
  }
  v459 = *v125;
  v182 = (volatile signed __int32 *)*((_QWORD *)v112 + 7);
  v460 = (utl::_RefCountBase *)v182;
  if ( v182 )
    _InterlockedIncrement(v182 + 2);
  utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(&v341, &v459);
  if ( v460 )
    utl::_RefCountBase::_DecStrong(v460);
  v107 = v341;
LABEL_411:
  if ( !v107 )
    MicrosoftTelemetryAssertTriggeredMsgKM("We must have a parent to insert under");
  v183 = v335;
  while ( 2 )
  {
    v339 = 0;
    if ( v183 )
    {
      inited = UnionFs::UfsPathTierNode::AllocAndInitInnerNode(&String1, 0);
      if ( inited < 0 )
      {
        v298 = 0x12001404D0LL;
        goto LABEL_761;
      }
      v184 = v339;
      v34 = lambda_499e3257b266ccbef4f29b33c513cd89_::operator()(&v385, v339, a6);
      if ( v34 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v34,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x483001404D7LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "PUSH: Updating intermediateNodes",
          v332);
        goto LABEL_759;
      }
      v185 = v352;
LABEL_727:
      if ( *((_QWORD *)v184 + 6) && !v335 && !v367 )
        MicrosoftTelemetryAssertTriggeredMsgKM("curInsertNode->IsFinal() || moreComponentsLeft || nextLevelTree");
      if ( (*(_DWORD *)v349 & 1) != 0
        && RtlCompareUnicodeString(&SourceString, &UnionFs::g_NoShortComponent, 0)
        && RtlCompareUnicodeString(&SourceString, &String1, 0) )
      {
        v354 = 0;
        if ( v335 )
        {
          v484[4] = *((_QWORD *)v184 + 6);
          v288 = *((_QWORD *)v184 + 7);
          v484[5] = v288;
          if ( v288 )
            _InterlockedIncrement((volatile signed __int32 *)(v288 + 8));
          v34 = UnionFs::UfsPathTierNode::AllocAndInitInnerShortNameNode(&SourceString, (__int64)&v354, (int)a6);
          if ( v34 < 0 )
          {
            v289 = 0x1300140502LL;
LABEL_739:
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v34,
              (int)a6,
              (struct UnionFs::StackEventTracer *)v289,
              (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
              "PUSH: Could not create new short name path node.",
              v332);
            utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v354);
LABEL_759:
            utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v339);
            goto LABEL_385;
          }
        }
        else
        {
          v290 = (unsigned __int64)&v371 & -(__int64)(v362 != 0);
          v484[6] = *v185;
          v291 = v185[1];
          v484[7] = v291;
          if ( v291 )
            _InterlockedIncrement((volatile signed __int32 *)(v291 + 8));
          v34 = UnionFs::UfsPathTierNode::AllocAndInitPayloadShortNameNode(&SourceString, (__int64)&v354, (int)a6, v290);
          if ( v34 < 0 )
          {
            v289 = 0x11C00140517LL;
            goto LABEL_739;
          }
        }
        v292 = v354;
        v293 = (char *)v354 + 32;
        v354 = 0;
        v461 = (unsigned __int64)v293;
        UnionFs::UfsPathTree::InsertNode(v107, (const struct UnionFs::UFS_COMPARE_KEY *)&v461, v292);
        utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v354);
      }
      *(_OWORD *)v465 = 0;
      if ( v335 )
      {
        if ( !*((_QWORD *)v184 + 6) )
          MicrosoftTelemetryAssertTriggeredMsgKM("!curInsertNode->IsFinal()");
        v462 = *((_QWORD *)v184 + 6);
        v294 = (volatile signed __int32 *)*((_QWORD *)v184 + 7);
        v463 = (utl::_RefCountBase *)v294;
        if ( v294 )
          _InterlockedIncrement(v294 + 2);
        utl::shared_ptr<UnionFs::UfsUnionCtx>::operator=(v465, &v462);
        if ( v463 )
          utl::_RefCountBase::_DecStrong(v463);
      }
      v339 = 0;
      v464 = (unsigned __int64)v184 + 32;
      UnionFs::UfsPathTree::InsertNode(v107, (const struct UnionFs::UFS_COMPARE_KEY *)&v464, v184);
      v295 = v363;
      v183 = UnionFs::Utils::WalkPathName(v363, (const struct UnionFs::UfsPathName *)&String1, v296);
      LOBYTE(v335) = v183;
      if ( (*(_DWORD *)v349 & 1) != 0
        && v183 != UnionFs::Utils::WalkPathName(
                     (UnionFs::Utils *)v19,
                     (const struct UnionFs::UfsPathName *)&SourceString,
                     v297) )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("moreComponentsLeft == moreShortComponentsLeft");
      }
      utl::shared_ptr<UnionFs::UfsPathTree>::operator=(&v341, v465);
      if ( v465[1] )
        utl::_RefCountBase::_DecStrong(v465[1]);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v339);
      if ( String1.Length )
      {
        v107 = v341;
        continue;
      }
      v299 = lambda_699009e3499d304af7d2f76f0343fe81_::operator()(v376, a6);
      v21 = v299;
      if ( v299 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v299,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x48500140552LL,
          (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
          "PUSH: Adding dependent union to intermediates",
          v332);
        goto LABEL_591;
      }
      if ( v362 )
      {
        v302 = UnionFs::UfsInstanceTierNode::UpdateMaxStoredPathLengthDiff(v355, v353, a6);
        v21 = v302;
        if ( v302 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v302,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x4430014055BLL,
            (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
            "PUSH: Updating stored path length",
            v332);
          if ( v342 )
            utl::_RefCountBase::_DecStrong(v342);
          if ( v344[1] )
          {
            utl::_RefCountBase::_DecStrong(v344[1]);
            v15 = (volatile signed __int32 *)v371.m128i_i64[1];
          }
          if ( v512 )
            (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
          wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
          utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
          wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::~unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>(v509);
          goto LABEL_599;
        }
      }
      else if ( *(_WORD *)v295 > *((_WORD *)v355 + 8) )
      {
        *((_WORD *)v355 + 8) = *(_WORD *)v295;
      }
      v351 = 0;
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x10) != 0
        && (qword_14009E190 & 0x10) == qword_14009E190 )
      {
        v303 = (const struct _UNICODE_STRING *)&v356;
        v353 = 1383;
        if ( !*((_QWORD *)&v356 + 1) )
          v303 = &FsTlEmptyUnicodeString;
        v439 = "UnionFs::UfsPathTable::InsertPriv";
        v436 = v303;
        v437 = *v352;
        v438 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
        v440 = "Inserted payload";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)word_140097872,
          v300,
          v301,
          (__int64)&v440,
          (__int64)&v439,
          (__int64)&v438,
          (__int64)&v353,
          (__int64)&v437,
          (__int64)&v436);
        v15 = (volatile signed __int32 *)v371.m128i_i64[1];
      }
      v304 = v342;
      *v358 = 1;
      if ( v304 )
      {
        utl::_RefCountBase::_DecStrong(v304);
        v15 = (volatile signed __int32 *)v371.m128i_i64[1];
      }
      if ( v344[1] )
      {
        utl::_RefCountBase::_DecStrong(v344[1]);
        v15 = (volatile signed __int32 *)v371.m128i_i64[1];
      }
      if ( v512 )
        (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
      wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
      wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::~unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>(v509);
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
  v185 = v352;
  v286 = (unsigned __int64)&v371 & -(__int64)(v362 != 0);
  v484[2] = *v352;
  v287 = v352[1];
  v484[3] = v287;
  if ( v287 )
    _InterlockedIncrement((volatile signed __int32 *)(v287 + 8));
  inited = UnionFs::UfsPathTierNode::AllocAndInitPayloadNode(&String1, (int)a6, v286);
  if ( inited >= 0 )
  {
    v184 = v339;
    goto LABEL_727;
  }
  v298 = 0x110001404EALL;
LABEL_761:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)inited,
    (int)a6,
    (struct UnionFs::StackEventTracer *)v298,
    (unsigned __int64)"UnionFs::UfsPathTable::InsertPriv",
    "PUSH: Could not create new path node.",
    v332);
  utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(&v339);
LABEL_705:
  if ( v342 )
    utl::_RefCountBase::_DecStrong(v342);
  if ( v344[1] )
    utl::_RefCountBase::_DecStrong(v344[1]);
  if ( v512 )
    (*(void (__fastcall **)(_QWORD *))(*v512 + 24LL))(v512);
  wil::details::lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___::_lambda_call__lambda_bd8239b2c70f4fd43776e748499db2b0___(v350);
  utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(v345);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v509, v283);
  if ( v509[16] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v509[16] + 24LL))(v509[16]);
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
0x1400480c4  mov     rax, rsp
0x1400480c7  mov     [rax+20h], rbx
0x1400480cb  push    rbp
0x1400480cc  push    rsi
0x1400480cd  push    rdi
0x1400480ce  push    r12
0x1400480d0  push    r13
0x1400480d2  push    r14
0x1400480d4  push    r15
0x1400480d6  lea     rbp, [rax-928h]
0x1400480dd  sub     rsp, 9F0h
0x1400480e4  movaps  xmmword ptr [rax-48h], xmm6
0x1400480e8  mov     rax, cs:__security_cookie
0x1400480ef  xor     rax, rsp
0x1400480f2  mov     [rbp+920h+var_48], rax
0x1400480f9  mov     r13, [rbp+920h+arg_20]
0x140048100  mov     r10, r8
0x140048103  mov     rbx, [rbp+920h+arg_28]
0x14004810a  mov     r15, rcx
0x14004810d  mov     [rbp+920h+var_8B0], r8
0x140048111  mov     r12, rdx
0x140048114  xor     r8d, r8d
0x140048117  mov     [rbp+920h+var_930], rcx
0x14004811b  mov     rcx, [rbp+920h+arg_40]
0x140048122  mov     [rbp+920h+var_970], r8d
0x140048126  mov     [rbp+920h+var_890], rdx
0x14004812d  mov     rdx, [rbp+920h+arg_38]
0x140048134  mov     [r13+0], r8d
0x140048138  mov     [rbp+920h+var_910], r9
0x14004813c  mov     [rbp+920h+var_8D8], r13
0x140048140  mov     [rbp+920h+var_8B8], rdx
0x140048144  mov     [rbp+920h+var_8D0], r8
0x140048148  test    rcx, rcx
0x14004814b  jz      short loc_14004815E
0x14004814d  mov     rax, [rcx]
0x140048150  mov     rcx, [rcx+8]
0x140048154  mov     [rbp+920h+var_900], rcx
0x140048158  mov     [rbp+920h+var_8D0], rax
0x14004815c  jmp     short loc_140048165
0x14004815e  mov     [rbp+920h+var_900], r8
0x140048162  mov     rax, r8
0x140048165  mov     r14d, [rbp+920h+arg_30]
0x14004816c  mov     ecx, r14d
0x14004816f  and     ecx, 4
0x140048172  mov     [rbp+920h+var_8E0], ecx
0x140048175  jz      short loc_14004817C
0x140048177  test    rax, rax
0x14004817a  jz      short loc_140048185
0x14004817c  test    rax, rax
0x14004817f  jz      short loc_1400481B9
0x140048181  test    ecx, ecx
0x140048183  jnz     short loc_1400481B9
0x140048185  lea     rax, aOriginInvalidR; "ORIGIN: Invalid root insertion paramete"...
0x14004818c  mov     r8, 4800014005Eh; struct UnionFs::StackEventTracer *
0x140048196  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x14004819d  mov     [rsp+0A20h+var_A00], rax; char *
0x1400481a2  mov     rdx, rbx; int
0x1400481a5  mov     ecx, 0C00000E5h; this
0x1400481aa  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400481af  mov     eax, 0C00000E5h
0x1400481b4  jmp     loc_14004C460
0x1400481b9  mov     [rbp+920h+var_908], r8d
0x1400481bd  xorps   xmm6, xmm6
0x1400481c0  movdqa  [rbp+920h+var_850], xmm6
0x1400481c8  test    rdx, rdx
0x1400481cb  jz      short loc_140048203
0x1400481cd  mov     rdi, [rdx+8]
0x1400481d1  mov     rcx, [rdx]
0x1400481d4  mov     [rbp+920h+var_880], rcx
0x1400481db  test    rdi, rdi
0x1400481de  jz      short loc_1400481E4
0x1400481e0  lock inc dword ptr [rdi+8]
0x1400481e4  movzx   eax, word ptr [rdx+10h]
0x1400481e8  mov     qword ptr [rbp+920h+var_850], rcx
0x1400481ef  mov     qword ptr [rbp+920h+var_850+8], rdi
0x1400481f6  movdqa  xmm6, [rbp+920h+var_850]
0x1400481fe  mov     [rbp+920h+var_908], eax
0x140048201  jmp     short loc_140048218
0x140048203  xorps   xmm0, xmm0
0x140048206  movq    [rbp+920h+var_880], xmm6
0x14004820e  psrldq  xmm0, 8
0x140048213  movq    rdi, xmm0
0x140048218  mov     eax, [r15]
0x14004821b  mov     rsi, r8
0x14004821e  mov     [rsp+0A20h+P], r8
0x140048223  test    al, 1
0x140048225  jz      loc_1400482B9
0x14004822b  mov     r9, rbx
0x14004822e  lea     r8, [rsp+0A20h+P]
0x140048233  mov     rdx, r12
0x140048236  mov     rcx, r10
0x140048239  call    ?MakeShortNameCopy@UfsPathName@UnionFs@@QEBAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::MakeShortNameCopy(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14004823e  xor     r8d, r8d
0x140048241  mov     esi, eax
0x140048243  test    eax, eax
0x140048245  jns     short loc_1400482B4
0x140048247  lea     rax, aPushCouldNotGe_1; "PUSH: Could not get short names for pat"...
0x14004824e  mov     r8, 0D00140070h; struct UnionFs::StackEventTracer *
0x140048258  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x14004825f  mov     [rsp+0A20h+var_A00], rax; char *
0x140048264  mov     rdx, rbx; int
0x140048267  mov     ecx, esi; this
0x140048269  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004826e  mov     rbx, [rsp+0A20h+P]
0x140048273  xor     r14d, r14d
0x140048276  test    rbx, rbx
0x140048279  jz      short loc_1400482A0
0x14004827b  cmp     [rbx+10h], r14b
0x14004827f  jnz     short loc_140048287
0x140048281  xorps   xmm0, xmm0
0x140048284  movups  xmmword ptr [rbx], xmm0
0x140048287  mov     rcx, rbx; UnicodeString
0x14004828a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004828f  xor     edx, edx; Tag
0x140048291  mov     rcx, rbx; P
0x140048294  call    cs:__imp_ExFreePoolWithTag
0x14004829b  nop     dword ptr [rax+rax+00h]
0x1400482a0  test    rdi, rdi
0x1400482a3  jz      short loc_1400482AD
0x1400482a5  mov     rcx, rdi; this
0x1400482a8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400482ad  mov     eax, esi
0x1400482af  jmp     loc_14004C460
0x1400482b4  mov     rsi, [rsp+0A20h+P]
0x1400482b9  mov     [rsp+0A20h+Resource], r8
0x1400482be  test    r14b, 1
0x1400482c2  jnz     short loc_14004830F
0x1400482c4  lea     rdx, [r15+20h]
0x1400482c8  lea     rcx, [rbp+920h+var_808]
0x1400482cf  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400482d4  mov     rcx, [rsp+0A20h+Resource]; Resource
0x1400482d9  xor     r8d, r8d
0x1400482dc  mov     rax, [rbp+920h+var_808]
0x1400482e3  mov     [rsp+0A20h+Resource], rax
0x1400482e8  test    rcx, rcx
0x1400482eb  jz      short loc_140048308
0x1400482ed  call    cs:__imp_ExReleaseResourceLite
0x1400482f4  nop     dword ptr [rax+rax+00h]
0x1400482f9  call    cs:__imp_KeLeaveCriticalRegion
0x140048300  nop     dword ptr [rax+rax+00h]
0x140048305  xor     r8d, r8d
0x140048308  mov     [rbp+920h+var_808], r8
0x14004830f  mov     rdx, [r15+88h]; RunRefCacheAware
0x140048316  lea     r9, [rbp+920h+var_2C0]
0x14004831d  mov     [rbp+920h+var_250], r8
0x140048324  lea     rcx, [rbp+920h+var_1D0]; void *
0x14004832b  mov     r8b, 1
0x14004832e  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x140048333  xor     r14d, r14d
0x140048336  cmp     [rbp+920h+var_1D0], r14
0x14004833d  jnz     loc_1400483CB
0x140048343  lea     rax, aOriginTableAlr; "ORIGIN: Table already run down"
0x14004834a  mov     r8, 1BA00140080h; struct UnionFs::StackEventTracer *
0x140048354  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x14004835b  mov     [rsp+0A20h+var_A00], rax; char *
0x140048360  mov     rdx, rbx; int
0x140048363  mov     ecx, 0C0ED000Ah; this
0x140048368  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004836d  lea     rcx, [rbp+920h+var_1D0]; this
0x140048374  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140048379  mov     rcx, [rbp+920h+var_150]
0x140048380  xor     ebx, ebx
0x140048382  test    rcx, rcx
0x140048385  jz      short loc_140048393
0x140048387  mov     rax, [rcx]
0x14004838a  mov     rax, [rax+18h]
0x14004838e  call    _guard_dispatch_icall
0x140048393  mov     rcx, [rsp+0A20h+Resource]; Resource
0x140048398  mov     [rsp+0A20h+Resource], rbx
0x14004839d  test    rcx, rcx
0x1400483a0  jz      short loc_1400483BA
0x1400483a2  call    cs:__imp_ExReleaseResourceLite
0x1400483a9  nop     dword ptr [rax+rax+00h]
0x1400483ae  call    cs:__imp_KeLeaveCriticalRegion
0x1400483b5  nop     dword ptr [rax+rax+00h]
0x1400483ba  test    rsi, rsi
0x1400483bd  jz      loc_140048722
0x1400483c3  cmp     [rsi+10h], bl
0x1400483c6  jmp     loc_140048701
0x1400483cb  add     r15, 8
0x1400483cf  mov     rax, [r15]
0x1400483d2  cmp     rax, r15
0x1400483d5  jz      short loc_1400483F5
0x1400483d7  lea     rcx, [rax+10h]
0x1400483db  mov     [rbp+920h+var_8F8], rcx
0x1400483df  mov     rcx, [rcx+8]
0x1400483e3  cmp     [rcx], r12
0x1400483e6  jz      short loc_1400483ED
0x1400483e8  mov     rax, [rax]
0x1400483eb  jmp     short loc_1400483D2
0x1400483ed  xor     r15d, r15d
0x1400483f0  jmp     loc_1400485A1
0x1400483f5  mov     r8, rbx
0x1400483f8  mov     [rbp+920h+var_860], r14
0x1400483ff  lea     rdx, [rbp+920h+var_860]
0x140048406  mov     rcx, r12; Instance
0x140048409  call    ?AllocAndInit@UfsInstanceTierNode@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsInstanceTierNode@UnionFs@@U?$default_delete@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceTierNode::AllocAndInit(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsInstanceTierNode,utl::default_delete<UnionFs::UfsInstanceTierNode>> &,UnionFs::StackEventTracer &)
0x14004840e  mov     r12d, eax
0x140048411  test    eax, eax
0x140048413  jns     loc_140048509
0x140048419  lea     rax, aPushAllocating_12; "PUSH: Allocating new instance tier node"
0x140048420  mov     r8, 6A00140094h; struct UnionFs::StackEventTracer *
0x14004842a  lea     r9, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x140048431  mov     [rsp+0A20h+var_A00], rax; char *
0x140048436  mov     rdx, rbx; int
0x140048439  mov     ecx, r12d; this
0x14004843c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140048441  mov     rbx, [rbp+920h+var_860]
0x140048448  test    rbx, rbx
0x14004844b  jz      short loc_14004847F
0x14004844d  mov     rcx, [rbx+8]; Context
0x140048451  mov     [rbx+8], r14
0x140048455  test    rcx, rcx
0x140048458  jz      short loc_140048466
0x14004845a  call    cs:__imp_FltReleaseContext
0x140048461  nop     dword ptr [rax+rax+00h]
0x140048466  mov     rcx, rbx
0x140048469  call    ??1?$unique_ptr@VUfsPathTierNode@UnionFs@@U?$default_delete@VUfsPathTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(void)
0x14004846e  xor     edx, edx; Tag
0x140048470  mov     rcx, rbx; P
0x140048473  call    cs:__imp_ExFreePoolWithTag
0x14004847a  nop     dword ptr [rax+rax+00h]
0x14004847f  lea     rcx, [rbp+920h+var_1D0]; this
0x140048486  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004848b  mov     rcx, [rbp+920h+var_150]
0x140048492  test    rcx, rcx
0x140048495  jz      short loc_1400484A3
0x140048497  mov     rax, [rcx]
0x14004849a  mov     rax, [rax+18h]
0x14004849e  call    _guard_dispatch_icall
0x1400484a3  mov     rcx, [rsp+0A20h+Resource]; Resource
0x1400484a8  mov     [rsp+0A20h+Resource], r14
0x1400484ad  test    rcx, rcx
0x1400484b0  jz      short loc_1400484CA
0x1400484b2  call    cs:__imp_ExReleaseResourceLite
0x1400484b9  nop     dword ptr [rax+rax+00h]
0x1400484be  call    cs:__imp_KeLeaveCriticalRegion
0x1400484c5  nop     dword ptr [rax+rax+00h]
0x1400484ca  test    rsi, rsi
0x1400484cd  jz      short loc_1400484F4
0x1400484cf  cmp     [rsi+10h], r14b
0x1400484d3  jnz     short loc_1400484DB
0x1400484d5  xorps   xmm0, xmm0
0x1400484d8  movups  xmmword ptr [rsi], xmm0
0x1400484db  mov     rcx, rsi; UnicodeString
0x1400484de  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400484e3  xor     edx, edx; Tag
0x1400484e5  mov     rcx, rsi; P
0x1400484e8  call    cs:__imp_ExFreePoolWithTag
0x1400484ef  nop     dword ptr [rax+rax+00h]
0x1400484f4  test    rdi, rdi
0x1400484f7  jz      short loc_140048501
0x1400484f9  mov     rcx, rdi; this
0x1400484fc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140048501  mov     eax, r12d
0x140048504  jmp     loc_14004C460
0x140048509  mov     ecx, 28h ; '('; unsigned __int64
0x14004850e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140048513  xor     r12d, r12d
0x140048516  test    rax, rax
0x140048519  jz      loc_14004C36F
0x14004851f  mov     r14, [rbp+920h+var_860]
0x140048526  mov     rcx, [r14]
0x140048529  mov     [r14], r12
0x14004852c  mov     [rax+10h], rcx
0x140048530  mov     rcx, [r14+8]
0x140048534  mov     [r14+8], r12
0x140048538  mov     [rax+18h], rcx
0x14004853c  mov     [rax+20h], r12w
0x140048541  mov     rcx, [r15+8]
0x140048545  mov     [rax+8], rcx
0x140048549  mov     [rax], r15
0x14004854c  mov     [rcx], rax
0x14004854f  mov     rcx, [rbp+920h+var_930]
0x140048553  mov     [r15+8], rax
0x140048557  inc     qword ptr [r15+10h]
0x14004855b  xor     r15d, r15d
0x14004855e  mov     rdx, [rcx+10h]
0x140048562  add     rdx, 10h
0x140048566  mov     [rbp+920h+var_8F8], rdx
0x14004856a  test    r14, r14
0x14004856d  jz      short loc_1400485A1
0x14004856f  mov     rcx, [r14+8]; Context
0x140048573  mov     [r14+8], r15
0x140048577  test    rcx, rcx
0x14004857a  jz      short loc_140048588
0x14004857c  call    cs:__imp_FltReleaseContext
0x140048583  nop     dword ptr [rax+rax+00h]
0x140048588  mov     rcx, r14
0x14004858b  call    ??1?$unique_ptr@VUfsPathTierNode@UnionFs@@U?$default_delete@VUfsPathTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(void)
0x140048590  xor     edx, edx; Tag
0x140048592  mov     rcx, r14; P
0x140048595  call    cs:__imp_ExFreePoolWithTag
0x14004859c  nop     dword ptr [rax+rax+00h]
0x1400485a1  mov     r12b, r15b
0x1400485a4  lea     r14, aUnionfsUfspath; "UnionFs::UfsPathTable::InsertPriv"
0x1400485ab  test    r12b, r12b
0x1400485ae  jz      loc_140048739
0x1400485b4  lea     rcx, [rbp+920h+var_1D0]; this
0x1400485bb  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
  ... truncated ...
```
