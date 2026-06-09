# UnionFs::HandleSetEa(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)

- ea: `0x14001d5d0`
- end: `0x14001e946`
- name: `?HandleSetEa@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@1@AEAVUfsUnionCtx@1@PEA_NAEAVStackEventTracer@1@@Z`
- size: `4982`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsUnionCtx *, bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `32`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001ed90`

## callees

- `0x1400015c4`
- `0x1400047d4`
- `0x140006064`
- `0x14000f81c`
- `0x14001014c`
- `0x140011168`
- `0x1400112c8`
- `0x14001c820`
- `0x14001c888`
- `0x14001c970`
- `0x14001d5d0`
- `0x14001f41c`
- `0x14001f49c`
- `0x140021878`
- `0x14002194c`
- `0x140021a64`
- `0x1400235a8`
- `0x140023784`
- `0x140023a10`
- `0x14002aca0`
- `0x140043a64`
- `0x140043ad8`
- `0x140043afc`
- `0x140056974`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140060494`
- `0x14006e394`
- `0x14006e54c`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001d6c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001d6c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d749`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d863`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d90f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dc56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dda1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e035`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e103`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e197`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e1d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e262`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e2d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e3d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e40f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e49d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e6d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e710`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e7a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e908`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d749`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d863`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d90f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dc56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dda1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e035`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e103`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e197`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e1d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e262`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e2d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e3d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e40f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e49d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e6d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e710`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e7a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e908`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001da6b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001daf7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001db1e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dbf5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dd44`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dfd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e205`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e50f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e5bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e743`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e8af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001da6b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001daf7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001db1e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dbf5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dd44`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dfd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e205`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e50f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e5bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e743`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e8af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001da77`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001db03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001db2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dc01`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dd50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dfe4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e211`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e51b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e5c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e74f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e8bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001da77`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001db03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001db2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dc01`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dd50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dfe4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e211`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e51b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e5c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e74f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e8bb`
- `FLTMGR!FltLockUserBuffer` at `0x14001d65a`
- `FLTMGR!FltLockUserBuffer` at `0x14001d65a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d8f9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001daae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001dc3c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001dd8b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e01f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e24c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e78a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e8f2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d8f9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001daae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001dc3c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001dd8b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e01f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e24c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e78a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001e8f2`
- `FLTMGR!FltQueryInformationFile` at `0x14001db9e`
- `FLTMGR!FltQueryInformationFile` at `0x14001de7a`
- `FLTMGR!FltQueryInformationFile` at `0x14001db9e`
- `FLTMGR!FltQueryInformationFile` at `0x14001de7a`
- `FLTMGR!FltQueryEaFile` at `0x14001dcd5`
- `FLTMGR!FltQueryEaFile` at `0x14001dcd5`

## string_xrefs

- `0x14001d7ae`: `ORIGIN: ProbeForRead`
- `0x14001de8c`: `API: Querying number of hard links`
- `0x14001df4e`: `PUSH: Getting hard link paths`
- `0x14001e614`: `ORIGIN: Setting EA on hard link`
- `0x14001e0a4`: `PUSH: Converting layer paths to scratch paths`
- `0x14001e14e`: `PUSH: Adding scratch path to EA payload`
- `0x14001e297`: `PUSH: Allocating UfsPathName`

## pseudocode

```c
__int64 __fastcall UnionFs::HandleSetEa(
        PFLT_CALLBACK_DATA CallbackData,
        WCHAR *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        struct UnionFs::UfsStreamHandleCtx *a4,
        struct UnionFs::UfsUnionCtx *a5,
        struct UnionFs::StackEventTracer *a6)
{
  void *v8; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdi
  NTSTATUS InformationFile; // ebx
  struct _MDL *MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  unsigned __int64 Length; // rax
  void **v15; // rax
  void *v16; // rbx
  int inited; // r15d
  struct _FLT_FILE_NAME_INFORMATION *v18; // rcx
  void *v19; // rcx
  UnionFs::UfsEaTable *v20; // rcx
  __int64 v21; // r9
  PVOID v22; // rdi
  struct _ERESOURCE *v23; // rbx
  struct _ERESOURCE *FsContext2; // r15
  __int64 v25; // rax
  __int64 v26; // r10
  struct _FLT_FILE_NAME_INFORMATION *v27; // rcx
  struct _ERESOURCE **v28; // rax
  struct _ERESOURCE *v29; // rcx
  __int64 v30; // r12
  struct _FILE_OBJECT *BackingFileObject; // rbx
  __int64 v32; // r12
  const char *v33; // rax
  __int64 v34; // r8
  struct _ERESOURCE *v35; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v36; // rcx
  struct _FILE_OBJECT *v37; // rbx
  gsl::details *v38; // rcx
  NTSTATUS EaFile; // r12d
  struct _FLT_FILE_NAME_INFORMATION *v40; // rcx
  bool v41; // zf
  int updated; // eax
  struct _ERESOURCE *v43; // r12
  int HardLinkPaths; // r13d
  __int64 v45; // rcx
  void *v46; // rbx
  struct _ERESOURCE *v47; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v48; // rcx
  int v49; // eax
  PVOID v50; // rbx
  _BYTE *v51; // r13
  const struct UnionFs::UfsPathName **v52; // rdi
  const struct UnionFs::UfsPathName **v53; // rbx
  int v54; // eax
  __int64 v55; // rcx
  void *v56; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v57; // rcx
  int v58; // eax
  PVOID v59; // rdi
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  PVOID v63; // rbx
  PVOID v64; // rbx
  void *v65; // rbx
  PVOID v66; // rbx
  PVOID v67; // rbx
  void *v68; // rbx
  int v69; // eax
  __int64 v70; // rcx
  int v71; // r8d
  int v72; // r9d
  PVOID v73; // rbx
  void *v74; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v75; // rcx
  __int64 v76; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v77; // rcx
  const char *Priority; // [rsp+28h] [rbp-1C0h]
  const char *Prioritya; // [rsp+28h] [rbp-1C0h]
  const char *Priorityb; // [rsp+28h] [rbp-1C0h]
  const char *Priorityc; // [rsp+28h] [rbp-1C0h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-198h] BYREF
  PVOID v83; // [rsp+58h] [rbp-190h] BYREF
  __int128 v84; // [rsp+60h] [rbp-188h] BYREF
  ULONG LengthReturned[2]; // [rsp+70h] [rbp-178h] BYREF
  PVOID P; // [rsp+78h] [rbp-170h] BYREF
  __int64 v87; // [rsp+80h] [rbp-168h] BYREF
  utl::_RefCountBase *v88; // [rsp+88h] [rbp-160h]
  __int128 v89; // [rsp+90h] [rbp-158h] BYREF
  PERESOURCE Resource; // [rsp+A0h] [rbp-148h]
  PVOID v91[2]; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v92; // [rsp+C0h] [rbp-128h]
  struct UnionFs::StackEventTracer *FileInformation; // [rsp+D0h] [rbp-118h] BYREF
  struct _FILE_OBJECT v94; // [rsp+D8h] [rbp-110h] BYREF

  *(_QWORD *)&v94.FileName.Length = a4;
  *(_QWORD *)LengthReturned = a3;
  v94.FileName.Buffer = a2;
  v94.CurrentByteOffset.QuadPart = (LONGLONG)CallbackData;
  *(_QWORD *)&v94.Waiters = a5;
  FileInformation = a6;
  *(_BYTE *)a5 = 0;
  v8 = 0;
  v83 = 0;
  Iopb = CallbackData->Iopb;
  if ( Iopb->Parameters.Read.ByteOffset.QuadPart )
  {
    InformationFile = FltLockUserBuffer(CallbackData);
    if ( InformationFile < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)InformationFile,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x54300050190LL,
        (unsigned __int64)"UnionFs::HandleSetEa",
        "API: FltLockUserBuffer",
        Priority);
      return (unsigned int)InformationFile;
    }
    MdlAddress = Iopb->Parameters.SetEa.MdlAddress;
    if ( (MdlAddress->MdlFlags & 5) != 0 )
      MappedSystemVa = MdlAddress->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      InformationFile = -1073741801;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000017LL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x54400050199LL,
        (unsigned __int64)"UnionFs::HandleSetEa",
        "ORIGIN: MmGetSystemAddressForMdlSafe",
        Priority);
      return (unsigned int)InformationFile;
    }
    Length = Iopb->Parameters.Read.Length;
    if ( !Iopb->Parameters.Read.Length )
    {
      *(_QWORD *)&v94.Flags = 0;
LABEL_21:
      v16 = 0;
      goto LABEL_22;
    }
    goto LABEL_218;
  }
  if ( !CallbackData->RequestorMode )
  {
    Length = Iopb->Parameters.Read.Length;
    MdlAddress = Iopb->Parameters.MdlWriteComplete.MdlChain;
    if ( MdlAddress || !Iopb->Parameters.Read.Length )
    {
      *(_QWORD *)&v94.Flags = Iopb->Parameters.QueryEa.EaList;
      goto LABEL_21;
    }
LABEL_218:
    gsl::details::terminate((gsl::details *)MdlAddress);
    __debugbreak();
  }
  v15 = (void **)utl::make_unique_pool<enum gsl::byte [0],256,1634027093,0>(&P, Iopb->Parameters.Read.Length);
  v8 = *v15;
  v16 = v8;
  *v15 = 0;
  v83 = v8;
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( !v8 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x642000501AALL,
      (unsigned __int64)"UnionFs::HandleSetEa",
      "ORIGIN: Allocating double EA buffer",
      Priority);
    return 3221225626LL;
  }
  RtlCopyFromUser(v8, Iopb->Parameters.QueryEa.EaList, Iopb->Parameters.Read.Length);
  Length = Iopb->Parameters.Read.Length;
  *(_QWORD *)&v94.Flags = v8;
LABEL_22:
  *(_QWORD *)&v94.LockOperation = Length;
  if ( Length < 0xC )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000004LL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x546000501C0LL,
      (unsigned __int64)"UnionFs::HandleSetEa",
      "ORIGIN: Provided buffer too small",
      Priority);
    if ( v16 )
      ExFreePoolWithTag(v16, 0);
    return 3221225476LL;
  }
  FileNameInformation = 0;
  v91[0] = 0;
  v91[1] = *((PVOID *)a2 + 4);
  v92 = *((_QWORD *)a2 + 3);
  inited = UnionFs::Utils::GetFileNameInformation(v91, 16777473, &FileNameInformation, a6);
  if ( inited < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inited,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x562000501CDLL,
      (unsigned __int64)"UnionFs::HandleSetEa",
      "PUSH: Getting source file name information",
      Priority);
    v18 = FileNameInformation;
    FileNameInformation = 0;
LABEL_28:
    if ( v18 )
      FltReleaseFileNameInformation(v18);
    if ( !v16 )
      return (unsigned int)inited;
    v19 = v16;
LABEL_32:
    ExFreePoolWithTag(v19, 0);
    return (unsigned int)inited;
  }
  v89 = 0;
  Resource = 0;
  if ( *((_DWORD *)a4 + 7) == 2 )
    v20 = *(UnionFs::UfsEaTable **)(*((_QWORD *)a4 + 4) + 24LL);
  else
    v20 = (UnionFs::UfsEaTable *)*((_QWORD *)UnionFs::g_FilterState + 11);
  inited = UnionFs::UfsEaTable::LookupEaEntry(
             v20,
             *((const struct _FLT_INSTANCE **)a2 + 3),
             FileNameInformation,
             1,
             (struct UnionFs::LookupEaResults *)&v89,
             a6);
  if ( inited < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inited,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x55E000501D7LL,
      (unsigned __int64)"UnionFs::HandleSetEa",
      "PUSH: EA table lookup",
      Prioritya);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
    v18 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_28;
  }
  v22 = (PVOID)v89;
  v84 = v89;
  if ( *((_QWORD *)&v89 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL));
  v23 = Resource;
  Resource = 0;
  FsContext2 = v23;
  if ( !v22 )
  {
    v25 = utl::enable_shared_from_this<UnionFs::UfsUnionCtx>::shared_from_this(a4, &v87);
    inited = UnionFs::UfsEaPayload::AllocAndInitShared(v25, v26, &v84, a6);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x549000501E4LL,
        (unsigned __int64)"UnionFs::HandleSetEa",
        "PUSH: Allocating new EA payload",
        Prioritya);
      if ( v23 )
      {
        ExReleaseResourceLite(v23);
        KeLeaveCriticalRegion();
      }
      if ( *((_QWORD *)&v84 + 1) )
        utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
      v27 = FileNameInformation;
      FileNameInformation = 0;
      if ( v27 )
        FltReleaseFileNameInformation(v27);
      if ( !v8 )
        return (unsigned int)inited;
      v19 = v8;
      goto LABEL_32;
    }
    v22 = (PVOID)v84;
    P = (PVOID)v84;
    v28 = (struct _ERESOURCE **)(*(__int64 (__fastcall **)(_QWORD, PVOID *))(*(_QWORD *)v84 + 16LL))(v84, &v83);
    FsContext2 = *v28;
    *v28 = 0;
    if ( v23 )
    {
      ExReleaseResourceLite(v23);
      KeLeaveCriticalRegion();
    }
    v29 = (struct _ERESOURCE *)v83;
    v83 = 0;
    if ( v29 )
    {
      ExReleaseResourceLite(v29);
      KeLeaveCriticalRegion();
    }
    v30 = *(_QWORD *)LengthReturned;
    BackingFileObject = (struct _FILE_OBJECT *)UnionFs::UfsFsContext2::GetBackingFileObject(*(UnionFs::UfsFsContext2 **)(*(_QWORD *)(*(_QWORD *)LengthReturned + 72LL) + 32LL));
    v83 = BackingFileObject;
    UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(v30, &v87);
    LODWORD(FileInformation) = 0;
    v32 = v87;
    InformationFile = FltQueryInformationFile(
                        **(PFLT_INSTANCE **)(v87 + 8),
                        BackingFileObject,
                        &FileInformation,
                        4u,
                        FileEaInformation,
                        0);
    if ( InformationFile < 0 )
    {
      v33 = "API: Querying EA info";
      v34 = 0x531000501F9LL;
LABEL_57:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)InformationFile,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v34,
        (unsigned __int64)"UnionFs::HandleSetEa",
        v33,
        Priorityb);
LABEL_58:
      if ( v88 )
        utl::_RefCountBase::_DecStrong(v88);
      if ( !FsContext2 )
        goto LABEL_63;
      v35 = FsContext2;
LABEL_62:
      ExReleaseResourceLite(v35);
      KeLeaveCriticalRegion();
LABEL_63:
      if ( *((_QWORD *)&v84 + 1) )
        utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
LABEL_65:
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
      v36 = FileNameInformation;
      FileNameInformation = 0;
      if ( v36 )
        FltReleaseFileNameInformation(v36);
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
      return (unsigned int)InformationFile;
    }
    if ( (_DWORD)FileInformation )
    {
      utl::make_unique_pool<enum gsl::byte [0],256,1634027093,0>(&v94.FinalStatus, (unsigned int)FileInformation);
      v37 = *(struct _FILE_OBJECT **)&v94.FinalStatus;
      if ( !*(_QWORD *)&v94.FinalStatus )
      {
        InformationFile = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x53200050205LL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "ORIGIN: Allocating query EA buffer",
          Priorityb);
        goto LABEL_58;
      }
      LengthReturned[0] = 0;
      EaFile = FltQueryEaFile(
                 **(PFLT_INSTANCE **)(v32 + 8),
                 (PFILE_OBJECT)v83,
                 *(PVOID *)&v94.FinalStatus,
                 (ULONG)FileInformation,
                 0,
                 0,
                 0,
                 0,
                 1u,
                 LengthReturned);
      if ( EaFile < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)EaFile,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x53300050216LL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "API: Querying ea info",
          Priorityc);
LABEL_73:
        if ( v37 )
          ExFreePoolWithTag(v37, 0);
        if ( v88 )
          utl::_RefCountBase::_DecStrong(v88);
        if ( FsContext2 )
        {
          ExReleaseResourceLite(FsContext2);
          KeLeaveCriticalRegion();
        }
        if ( *((_QWORD *)&v84 + 1) )
          utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
        UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
        v40 = FileNameInformation;
        v41 = FileNameInformation == 0;
        FileNameInformation = 0;
        if ( !v41 )
          FltReleaseFileNameInformation(v40);
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
        return (unsigned int)EaFile;
      }
      *(_QWORD *)&v94.FinalStatus = LengthReturned[0];
      v94.RelatedFileObject = v37;
      if ( !v37 && LengthReturned[0] )
      {
        gsl::details::terminate(v38);
        JUMPOUT(0x14001E946LL);
      }
      updated = UnionFs::UfsEaPayload::AddOrUpdateEAs(v22, &v94.FinalStatus, a6, 0);
      EaFile = updated;
      if ( updated < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)updated,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x5510005021CLL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "PUSH: Adding EAs",
          Priorityc);
        goto LABEL_73;
      }
      if ( v37 )
        ExFreePoolWithTag(v37, 0);
    }
    v94.IrpListLock = 0;
    LODWORD(v94.IrpList.Flink) = 0;
    InformationFile = FltQueryInformationFile(
                        **(PFLT_INSTANCE **)(v87 + 8),
                        (PFILE_OBJECT)v83,
                        &v94.IrpListLock,
                        0xCu,
                        FileStandardLinkInformation,
                        0);
    if ( InformationFile < 0 )
    {
      v33 = "API: Querying number of hard links";
      v34 = 0x6320005022BLL;
      goto LABEL_57;
    }
    v43 = FsContext2;
    memset(&v94.FsContext, 0, 32);
    if ( HIDWORD(v94.IrpListLock) <= 1 )
    {
      UnionFs::UfsPathName::UfsPathName(
        (UnionFs::UfsPathName *)&v94.LastLock,
        &FileNameInformation->Name,
        FileNameInformation->Volume.Length);
      if ( *((_DWORD *)a4 + 7) == 2 )
        v76 = *(_QWORD *)(*((_QWORD *)a4 + 4) + 24LL);
      else
        v76 = *((_QWORD *)UnionFs::g_FilterState + 11);
      InformationFile = UnionFs::UfsEaTable::InsertEaEntry(
                          v76,
                          *((_QWORD *)v94.FileName.Buffer + 3),
                          (int)&v94.LastLock,
                          (int)&v84,
                          (__int64)&v94.FsContext,
                          (char *)a6,
                          0);
      if ( InformationFile < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)InformationFile,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x55F0005027DLL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "PUSH: EA Table insert",
          Prioritya);
        UnionFs::UfsPathName::~UfsPathName((UnionFs::UfsPathName *)&v94.LastLock);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)&v94.FsContext);
        if ( v88 )
          utl::_RefCountBase::_DecStrong(v88);
        if ( !FsContext2 )
          goto LABEL_63;
        v35 = FsContext2;
        goto LABEL_62;
      }
      UnionFs::UfsPathName::~UfsPathName((UnionFs::UfsPathName *)&v94.LastLock);
    }
    else
    {
      *(__m128i *)&v94.Type = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v94.Vpb = (PVPB)-1LL;
      HardLinkPaths = UnionFs::Utils::GetHardLinkPaths(**(PFLT_INSTANCE **)(v87 + 8), (PFILE_OBJECT)v83, &v94, a6);
      if ( HardLinkPaths < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)HardLinkPaths,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x5010005023BLL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "PUSH: Getting hard link paths",
          Priorityb);
        goto LABEL_98;
      }
      *(__m128i *)v91 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v92 = -1;
      v49 = UnionFs::UfsUnionCtx::ConvertLayerPathsToScratchPaths(*(_QWORD *)&v94.FileName.Length, &v94, v91, a6, 0);
      HardLinkPaths = v49;
      if ( v49 == -1073741275 || v49 == -1073741811 )
      {
        UnionFs::StackEventTracer::LogError(a6);
        *(_DWORD *)a6 = 0;
        *((_WORD *)a6 + 274) = 0;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0ED0003LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x5FA0005024ELL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "ORIGIN: Setting EA on hard link",
          Priorityb);
        if ( (unsigned int)dword_14009E178 > 2 )
        {
          LODWORD(P) = HardLinkPaths;
          LOWORD(LengthReturned[0]) = 590;
          LODWORD(v83) = 1530;
          *(_QWORD *)&v94.FinalStatus = "UnionFs::HandleSetEa";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
            v70,
            (unsigned int)byte_140096673,
            v71,
            v72,
            (__int64)&v94.FinalStatus,
            (__int64)&v83,
            (__int64)LengthReturned,
            (__int64)&P);
        }
        v73 = v91[0];
        if ( v91[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v70,
            v91[0],
            ((char *)v91[1] - (char *)v91[0]) >> 3);
          if ( v73 )
            ExFreePoolWithTag(v73, 0);
        }
        v74 = *(void **)&v94.Type;
        if ( *(_QWORD *)&v94.Type != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v70,
            *(_QWORD *)&v94.Type,
            ((__int64)v94.DeviceObject - *(_QWORD *)&v94.Type) >> 3);
          if ( v74 )
            ExFreePoolWithTag(v74, 0);
        }
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)&v94.FsContext);
        if ( v88 )
          utl::_RefCountBase::_DecStrong(v88);
        if ( FsContext2 )
        {
          ExReleaseResourceLite(FsContext2);
          KeLeaveCriticalRegion();
        }
        if ( *((_QWORD *)&v84 + 1) )
          utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
        UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
        v75 = FileNameInformation;
        FileNameInformation = 0;
        if ( v75 )
          FltReleaseFileNameInformation(v75);
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
        return 3236757507LL;
      }
      if ( v49 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v49,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x50200050254LL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "PUSH: Converting layer paths to scratch paths",
          Priorityb);
        v50 = v91[0];
        if ( v91[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v45,
            v91[0],
            ((char *)v91[1] - (char *)v91[0]) >> 3);
          if ( v50 )
            ExFreePoolWithTag(v50, 0);
        }
LABEL_98:
        v46 = *(void **)&v94.Type;
        if ( *(_QWORD *)&v94.Type != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v45,
            *(_QWORD *)&v94.Type,
            ((__int64)v94.DeviceObject - *(_QWORD *)&v94.Type) >> 3);
          if ( v46 )
            ExFreePoolWithTag(v46, 0);
        }
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)&v94.FsContext);
        if ( v88 )
          utl::_RefCountBase::_DecStrong(v88);
        if ( FsContext2 )
        {
          v47 = FsContext2;
LABEL_105:
          ExReleaseResourceLite(v47);
          KeLeaveCriticalRegion();
        }
LABEL_106:
        if ( *((_QWORD *)&v84 + 1) )
          utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
        UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
        v48 = FileNameInformation;
        v41 = FileNameInformation == 0;
        FileNameInformation = 0;
        if ( !v41 )
          FltReleaseFileNameInformation(v48);
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
        return (unsigned int)HardLinkPaths;
      }
      v51 = v91[0];
      v52 = (const struct UnionFs::UfsPathName **)v91[0];
      v53 = (const struct UnionFs::UfsPathName **)v91[1];
      while ( v52 != v53 )
      {
        v54 = UnionFs::UfsEaPayload::AddScratchPath((UnionFs::UfsEaPayload *)P, *v52, a6);
        LengthReturned[0] = v54;
        if ( v54 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v54,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x25C0005025CLL,
            (unsigned __int64)"UnionFs::HandleSetEa",
            "PUSH: Adding scratch path to EA payload",
            Priorityb);
LABEL_124:
          if ( v51 != (_BYTE *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
              v55,
              v51,
              ((char *)v53 - v51) >> 3);
            if ( v51 )
              ExFreePoolWithTag(v51, 0);
          }
          v56 = *(void **)&v94.Type;
          if ( *(_QWORD *)&v94.Type != -1 )
          {
            utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
              v55,
              *(_QWORD *)&v94.Type,
              ((__int64)v94.DeviceObject - *(_QWORD *)&v94.Type) >> 3);
            if ( v56 )
              ExFreePoolWithTag(v56, 0);
          }
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)&v94.FsContext);
          if ( v88 )
            utl::_RefCountBase::_DecStrong(v88);
          if ( FsContext2 )
          {
            ExReleaseResourceLite(FsContext2);
            KeLeaveCriticalRegion();
          }
          if ( *((_QWORD *)&v84 + 1) )
            utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
          UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
          v57 = FileNameInformation;
          v41 = FileNameInformation == 0;
          FileNameInformation = 0;
          if ( !v41 )
            FltReleaseFileNameInformation(v57);
          if ( v8 )
            ExFreePoolWithTag(v8, 0);
          return LengthReturned[0];
        }
        ++v52;
      }
      v83 = 0;
      v58 = UnionFs::UfsPathName::AllocAndInit(FileNameInformation, &v83, a6);
      LengthReturned[0] = v58;
      if ( v58 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v58,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x5A300050264LL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "PUSH: Allocating UfsPathName",
          Priorityb);
        v59 = v83;
        if ( v83 )
        {
          UnionFs::UfsPathName::~UfsPathName((UnionFs::UfsPathName *)v83);
          ExFreePoolWithTag(v59, 0);
        }
        goto LABEL_124;
      }
      utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>::push_back(
        v91,
        &v83);
      if ( *(_DWORD *)(*(_QWORD *)&v94.FileName.Length + 28LL) == 2 )
        v60 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v94.FileName.Length + 32LL) + 24LL);
      else
        v60 = *((_QWORD *)UnionFs::g_FilterState + 11);
      HardLinkPaths = UnionFs::UfsEaTable::InsertEaEntryWithMultipleNames(
                        v60,
                        *((_QWORD *)v94.FileName.Buffer + 3),
                        (int)v91,
                        (int)&v84,
                        (__int64)&v94.FsContext,
                        (char *)a6);
      if ( HardLinkPaths < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)HardLinkPaths,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x77E00050271LL,
          (unsigned __int64)"UnionFs::HandleSetEa",
          "PUSH: EA Table multi-name insert",
          Prioritya);
        v63 = v83;
        if ( v83 )
        {
          UnionFs::UfsPathName::~UfsPathName((UnionFs::UfsPathName *)v83);
          ExFreePoolWithTag(v63, 0);
        }
        v64 = v91[0];
        if ( v91[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v62,
            v91[0],
            ((char *)v91[1] - (char *)v91[0]) >> 3);
          if ( v64 )
            ExFreePoolWithTag(v64, 0);
        }
        v65 = *(void **)&v94.Type;
        if ( *(_QWORD *)&v94.Type != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v62,
            *(_QWORD *)&v94.Type,
            ((__int64)v94.DeviceObject - *(_QWORD *)&v94.Type) >> 3);
          if ( v65 )
            ExFreePoolWithTag(v65, 0);
        }
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)&v94.FsContext);
        if ( v88 )
          utl::_RefCountBase::_DecStrong(v88);
        if ( FsContext2 )
        {
          v47 = FsContext2;
          goto LABEL_105;
        }
        goto LABEL_106;
      }
      v66 = v83;
      if ( v83 )
      {
        UnionFs::UfsPathName::~UfsPathName((UnionFs::UfsPathName *)v83);
        ExFreePoolWithTag(v66, 0);
      }
      v67 = v91[0];
      if ( v91[0] != (PVOID)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
          v61,
          v91[0],
          ((char *)v91[1] - (char *)v91[0]) >> 3);
        if ( v67 )
          ExFreePoolWithTag(v67, 0);
      }
      v68 = *(void **)&v94.Type;
      if ( *(_QWORD *)&v94.Type != -1 )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
          v61,
          *(_QWORD *)&v94.Type,
          ((__int64)v94.DeviceObject - *(_QWORD *)&v94.Type) >> 3);
        if ( v68 )
          ExFreePoolWithTag(v68, 0);
      }
      v22 = P;
    }
    if ( LODWORD(v94.FsContext) == 2 )
    {
      FsContext2 = (struct _ERESOURCE *)v94.FsContext2;
      v94.FsContext2 = 0;
      if ( v43 )
      {
        ExReleaseResourceLite(v43);
        KeLeaveCriticalRegion();
      }
      utl::shared_ptr<UnionFs::UfsPathTree>::operator=(&v84, &v94.SectionObjectPointer);
      v22 = (PVOID)v84;
    }
    UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)&v94.FsContext);
    if ( v88 )
      utl::_RefCountBase::_DecStrong(v88);
  }
  LOBYTE(v21) = *(_BYTE *)(v94.CurrentByteOffset.QuadPart + 80) != 0;
  v69 = UnionFs::UfsEaPayload::AddOrUpdateEAs(v22, &v94.LockOperation, a6, v21);
  InformationFile = v69;
  if ( v69 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v69,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x54A00050292LL,
      (unsigned __int64)"UnionFs::HandleSetEa",
      "PUSH: Adding EAs",
      Prioritya);
    if ( FsContext2 )
    {
      ExReleaseResourceLite(FsContext2);
      KeLeaveCriticalRegion();
    }
    if ( *((_QWORD *)&v84 + 1) )
      utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
    goto LABEL_65;
  }
  **(_BYTE **)&v94.Waiters = 1;
  if ( FsContext2 )
  {
    ExReleaseResourceLite(FsContext2);
    KeLeaveCriticalRegion();
  }
  if ( *((_QWORD *)&v84 + 1) )
    utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v84 + 1));
  UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)&v89);
  v77 = FileNameInformation;
  FileNameInformation = 0;
  if ( v77 )
    FltReleaseFileNameInformation(v77);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return 0;
}

```

## disassembly

```asm
0x14001d5d0  push    rbx
0x14001d5d2  push    rsi
0x14001d5d3  push    rdi
0x14001d5d4  push    r12
0x14001d5d6  push    r13
0x14001d5d8  push    r14
0x14001d5da  push    r15
0x14001d5dc  sub     rsp, 1B0h
0x14001d5e3  mov     rax, cs:__security_cookie
0x14001d5ea  xor     rax, rsp
0x14001d5ed  mov     [rsp+1E8h+var_48], rax
0x14001d5f5  mov     r13, r9
0x14001d5f8  mov     [rsp+1E8h+var_B8], r9
0x14001d600  mov     qword ptr [rsp+1E8h+var_178], r8
0x14001d605  mov     r12, rdx
0x14001d608  mov     [rsp+1E8h+var_B0], rdx
0x14001d610  mov     rax, rcx
0x14001d613  mov     [rsp+1E8h+var_A8], rcx
0x14001d61b  mov     r14, [rsp+1E8h+arg_28]
0x14001d623  mov     rcx, [rsp+1E8h+arg_20]
0x14001d62b  mov     [rsp+1E8h+var_A0], rcx
0x14001d633  mov     [rsp+1E8h+FileInformation], r14
0x14001d63b  xor     r15d, r15d
0x14001d63e  mov     [rcx], r15b
0x14001d641  mov     esi, r15d
0x14001d644  mov     [rsp+1E8h+var_190], r15
0x14001d649  mov     rdi, [rax+10h]
0x14001d64d  cmp     [rdi+28h], r15
0x14001d651  jz      loc_14001D718
0x14001d657  mov     rcx, rax; CallbackData
0x14001d65a  call    cs:__imp_FltLockUserBuffer
0x14001d661  nop     dword ptr [rax+rax+00h]
0x14001d666  mov     ebx, eax
0x14001d668  test    eax, eax
0x14001d66a  jns     short loc_14001D69A
0x14001d66c  lea     rax, aApiFltlockuser; "API: FltLockUserBuffer"
0x14001d673  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d678  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d67f  mov     r8, 54300050190h; struct UnionFs::StackEventTracer *
0x14001d689  mov     rdx, r14; int
0x14001d68c  mov     ecx, ebx; this
0x14001d68e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d693  mov     eax, ebx
0x14001d695  jmp     loc_14001E916
0x14001d69a  mov     rcx, [rdi+28h]; MemoryDescriptorList
0x14001d69e  test    byte ptr [rcx+0Ah], 5
0x14001d6a2  jz      short loc_14001D6AA
0x14001d6a4  mov     rax, [rcx+18h]
0x14001d6a8  jmp     short loc_14001D6CC
0x14001d6aa  mov     [rsp+1E8h+Priority], 40000010h; char *
0x14001d6b2  mov     [rsp+1E8h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14001d6b7  xor     r9d, r9d; RequestedAddress
0x14001d6ba  xor     edx, edx; AccessMode
0x14001d6bc  lea     r8d, [r9+1]; CacheType
0x14001d6c0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001d6c7  nop     dword ptr [rax+rax+00h]
0x14001d6cc  test    rax, rax
0x14001d6cf  jz      short loc_14001D6FF
0x14001d6d1  lea     rax, aOriginMmgetsys; "ORIGIN: MmGetSystemAddressForMdlSafe"
0x14001d6d8  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d6dd  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d6e4  mov     r8, 54400050199h; struct UnionFs::StackEventTracer *
0x14001d6ee  mov     rdx, r14; int
0x14001d6f1  mov     ebx, 0C0000017h
0x14001d6f6  mov     ecx, ebx; this
0x14001d6f8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d6fd  jmp     short loc_14001D693
0x14001d6ff  mov     eax, [rdi+18h]
0x14001d702  test    rax, rax
0x14001d705  jnz     loc_14001E93A
0x14001d70b  mov     [rsp+1E8h+var_C0], r15
0x14001d713  jmp     loc_14001D81C
0x14001d718  cmp     [rax+50h], r15b
0x14001d71c  jz      loc_14001D7FF
0x14001d722  mov     edx, [rdi+18h]
0x14001d725  lea     rcx, [rsp+1E8h+P]
0x14001d72a  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GBGFEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1634027093,0>(unsigned __int64)
0x14001d72f  mov     rsi, [rax]
0x14001d732  mov     rbx, rsi
0x14001d735  mov     [rax], r15
0x14001d738  mov     [rsp+1E8h+var_190], rsi
0x14001d73d  mov     rcx, [rsp+1E8h+P]; P
0x14001d742  test    rcx, rcx
0x14001d745  jz      short loc_14001D755
0x14001d747  xor     edx, edx; Tag
0x14001d749  call    cs:__imp_ExFreePoolWithTag
0x14001d750  nop     dword ptr [rax+rax+00h]
0x14001d755  test    rsi, rsi
0x14001d758  jz      short loc_14001D77B
0x14001d75a  mov     r8d, [rdi+18h]; Size
0x14001d75e  mov     rdx, [rdi+20h]; Src
0x14001d762  mov     rcx, rsi; void *
0x14001d765  call    RtlCopyFromUser
0x14001d76a  nop
0x14001d76b  mov     eax, [rdi+18h]
0x14001d76e  mov     [rsp+1E8h+var_C0], rbx
0x14001d776  jmp     loc_14001D81F
0x14001d77b  lea     rax, aOriginAllocati_50; "ORIGIN: Allocating double EA buffer"
0x14001d782  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d787  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d78e  mov     r8, 642000501AAh; struct UnionFs::StackEventTracer *
0x14001d798  mov     rdx, r14; int
0x14001d79b  mov     ebx, 0C000009Ah
0x14001d7a0  mov     ecx, ebx; this
0x14001d7a2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d7a7  mov     eax, ebx
0x14001d7a9  jmp     loc_14001E916
0x14001d7ae  lea     rax, aOriginProbefor; "ORIGIN: ProbeForRead"
0x14001d7b5  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d7ba  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d7c1  mov     r8, 626000501B0h; struct UnionFs::StackEventTracer *
0x14001d7cb  mov     rdx, [rsp+1E8h+FileInformation]; int
0x14001d7d3  mov     ecx, 0C00000E8h; this
0x14001d7d8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d7dd  mov     rcx, [rsp+1E8h+var_190]; P
0x14001d7e2  test    rcx, rcx
0x14001d7e5  jz      short loc_14001D7F5
0x14001d7e7  xor     edx, edx; Tag
0x14001d7e9  call    cs:__imp_ExFreePoolWithTag
0x14001d7f0  nop     dword ptr [rax+rax+00h]
0x14001d7f5  mov     eax, 0C00000E8h
0x14001d7fa  jmp     loc_14001E916
0x14001d7ff  mov     eax, [rdi+18h]
0x14001d802  mov     rcx, [rdi+20h]
0x14001d806  test    rcx, rcx
0x14001d809  jnz     short loc_14001D814
0x14001d80b  test    rax, rax
0x14001d80e  jnz     loc_14001E93A
0x14001d814  mov     [rsp+1E8h+var_C0], rcx
0x14001d81c  mov     rbx, r15
0x14001d81f  mov     [rsp+1E8h+var_C8], rax
0x14001d827  cmp     rax, 0Ch
0x14001d82b  jnb     short loc_14001D876
0x14001d82d  lea     rax, aOriginProvided; "ORIGIN: Provided buffer too small"
0x14001d834  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d839  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d840  mov     r8, 546000501C0h; struct UnionFs::StackEventTracer *
0x14001d84a  mov     rdx, r14; int
0x14001d84d  mov     edi, 0C0000004h
0x14001d852  mov     ecx, edi; this
0x14001d854  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d859  test    rbx, rbx
0x14001d85c  jz      short loc_14001D86F
0x14001d85e  xor     edx, edx; Tag
0x14001d860  mov     rcx, rbx; P
0x14001d863  call    cs:__imp_ExFreePoolWithTag
0x14001d86a  nop     dword ptr [rax+rax+00h]
0x14001d86f  mov     eax, edi
0x14001d871  jmp     loc_14001E916
0x14001d876  mov     [rsp+1E8h+FileNameInformation], r15
0x14001d87b  mov     [rsp+1E8h+var_138], r15
0x14001d883  mov     rax, [r12+20h]
0x14001d888  mov     [rsp+1E8h+var_138+8], rax
0x14001d890  mov     rax, [r12+18h]
0x14001d895  mov     [rsp+1E8h+var_128], rax
0x14001d89d  mov     r9, r14
0x14001d8a0  lea     r8, [rsp+1E8h+FileNameInformation]
0x14001d8a5  mov     edx, 1000101h
0x14001d8aa  lea     rcx, [rsp+1E8h+var_138]
0x14001d8b2  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14001d8b7  mov     r15d, eax
0x14001d8ba  test    eax, eax
0x14001d8bc  jns     short loc_14001D923
0x14001d8be  lea     rax, aPushGettingSou_0; "PUSH: Getting source file name informat"...
0x14001d8c5  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d8ca  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d8d1  mov     r8, 562000501CDh; struct UnionFs::StackEventTracer *
0x14001d8db  mov     rdx, r14; int
0x14001d8de  mov     ecx, r15d; this
0x14001d8e1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d8e6  mov     rcx, [rsp+1E8h+FileNameInformation]; FileNameInformation
0x14001d8eb  mov     [rsp+1E8h+FileNameInformation], 0
0x14001d8f4  test    rcx, rcx
0x14001d8f7  jz      short loc_14001D905
0x14001d8f9  call    cs:__imp_FltReleaseFileNameInformation
0x14001d900  nop     dword ptr [rax+rax+00h]
0x14001d905  test    rbx, rbx
0x14001d908  jz      short loc_14001D91B
0x14001d90a  mov     rcx, rbx; P
0x14001d90d  xor     edx, edx; Tag
0x14001d90f  call    cs:__imp_ExFreePoolWithTag
0x14001d916  nop     dword ptr [rax+rax+00h]
0x14001d91b  mov     eax, r15d
0x14001d91e  jmp     loc_14001E916
0x14001d923  xorps   xmm0, xmm0
0x14001d926  movdqu  [rsp+1E8h+var_158], xmm0
0x14001d92f  mov     [rsp+1E8h+Resource], 0
0x14001d93b  cmp     dword ptr [r13+1Ch], 2
0x14001d940  jnz     short loc_14001D94C
0x14001d942  mov     rax, [r13+20h]
0x14001d946  mov     rcx, [rax+18h]
0x14001d94a  jmp     short loc_14001D957
0x14001d94c  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001d953  mov     rcx, [rax+58h]; this
0x14001d957  mov     qword ptr [rsp+1E8h+Priority], r14; char *
0x14001d95c  lea     rax, [rsp+1E8h+var_158]
0x14001d964  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; struct UnionFs::LookupEaResults *
0x14001d969  mov     r9b, 1; bool
0x14001d96c  mov     r8, [rsp+1E8h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x14001d971  mov     rdx, [r12+18h]; struct _FLT_INSTANCE *
0x14001d976  call    ?LookupEaEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupEaResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::LookupEaEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupEaResults &,UnionFs::StackEventTracer &)
0x14001d97b  mov     r15d, eax
0x14001d97e  xor     r12d, r12d
0x14001d981  test    eax, eax
0x14001d983  jns     short loc_14001D9C9
0x14001d985  lea     rax, aPushEaTableLoo; "PUSH: EA table lookup"
0x14001d98c  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001d991  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001d998  mov     r8, 55E000501D7h; struct UnionFs::StackEventTracer *
0x14001d9a2  mov     rdx, r14; int
0x14001d9a5  mov     ecx, r15d; this
0x14001d9a8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d9ad  lea     rcx, [rsp+1E8h+var_158]; this
0x14001d9b5  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001d9ba  mov     rcx, [rsp+1E8h+FileNameInformation]
0x14001d9bf  mov     [rsp+1E8h+FileNameInformation], r12
0x14001d9c4  jmp     loc_14001D8F4
0x14001d9c9  mov     rdi, qword ptr [rsp+1E8h+var_158]
0x14001d9d1  mov     qword ptr [rsp+1E8h+var_188], rdi
0x14001d9d6  mov     rax, qword ptr [rsp+1E8h+var_158+8]
0x14001d9de  mov     qword ptr [rsp+1E8h+var_188+8], rax
0x14001d9e3  test    rax, rax
0x14001d9e6  jz      short loc_14001D9EC
0x14001d9e8  lock inc dword ptr [rax+8]
0x14001d9ec  mov     rbx, [rsp+1E8h+Resource]
0x14001d9f4  mov     [rsp+1E8h+Resource], r12
0x14001d9fc  mov     r15, rbx
0x14001d9ff  test    rdi, rdi
0x14001da02  jnz     loc_14001E560
0x14001da08  mov     r10, [rsp+1E8h+FileNameInformation]
0x14001da0d  lea     rdx, [rsp+1E8h+var_168]
0x14001da15  mov     rcx, r13
0x14001da18  call    ?shared_from_this@?$enable_shared_from_this@VUfsUnionCtx@UnionFs@@@utl@@QEAA?AV?$shared_ptr@VUfsUnionCtx@UnionFs@@@2@XZ; utl::enable_shared_from_this<UnionFs::UfsUnionCtx>::shared_from_this(void)
0x14001da1d  mov     r9, r14
0x14001da20  lea     r8, [rsp+1E8h+var_188]
0x14001da25  mov     rdx, r10
0x14001da28  mov     rcx, rax
0x14001da2b  call    ?AllocAndInitShared@UfsEaPayload@UnionFs@@SAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$shared_ptr@VUfsEaPayload@UnionFs@@@4@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsEaPayload::AllocAndInitShared(utl::shared_ptr<UnionFs::UfsUnionCtx>,_FLT_FILE_NAME_INFORMATION const &,utl::shared_ptr<UnionFs::UfsEaPayload> &,UnionFs::StackEventTracer &,bool)
0x14001da30  mov     r15d, eax
0x14001da33  test    eax, eax
0x14001da35  jns     loc_14001DACB
0x14001da3b  lea     rax, aPushAllocating_0; "PUSH: Allocating new EA payload"
0x14001da42  mov     qword ptr [rsp+1E8h+BugCheckOnFailure], rax; char *
0x14001da47  lea     r9, aUnionfsHandles; "UnionFs::HandleSetEa"
0x14001da4e  mov     r8, 549000501E4h; struct UnionFs::StackEventTracer *
0x14001da58  mov     rdx, r14; int
0x14001da5b  mov     ecx, r15d; this
0x14001da5e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001da63  test    rbx, rbx
0x14001da66  jz      short loc_14001DA83
0x14001da68  mov     rcx, rbx; Resource
0x14001da6b  call    cs:__imp_ExReleaseResourceLite
0x14001da72  nop     dword ptr [rax+rax+00h]
0x14001da77  call    cs:__imp_KeLeaveCriticalRegion
0x14001da7e  nop     dword ptr [rax+rax+00h]
0x14001da83  mov     rcx, qword ptr [rsp+1E8h+var_188+8]; this
0x14001da88  test    rcx, rcx
0x14001da8b  jz      short loc_14001DA92
0x14001da8d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001da92  lea     rcx, [rsp+1E8h+var_158]; this
0x14001da9a  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001da9f  mov     rcx, [rsp+1E8h+FileNameInformation]; FileNameInformation
0x14001daa4  mov     [rsp+1E8h+FileNameInformation], r12
0x14001daa9  test    rcx, rcx
0x14001daac  jz      short loc_14001DABA
0x14001daae  call    cs:__imp_FltReleaseFileNameInformation
0x14001dab5  nop     dword ptr [rax+rax+00h]
0x14001daba  test    rsi, rsi
0x14001dabd  jz      loc_14001D91B
0x14001dac3  mov     rcx, rsi
0x14001dac6  jmp     loc_14001D90D
0x14001dacb  mov     rdi, qword ptr [rsp+1E8h+var_188]
0x14001dad0  mov     [rsp+1E8h+P], rdi
0x14001dad5  mov     rax, [rdi]
0x14001dad8  mov     rax, [rax+10h]
0x14001dadc  lea     rdx, [rsp+1E8h+var_190]
0x14001dae1  mov     rcx, rdi
0x14001dae4  call    _guard_dispatch_icall
0x14001dae9  mov     r15, [rax]
0x14001daec  mov     [rax], r12
0x14001daef  test    rbx, rbx
0x14001daf2  jz      short loc_14001DB0F
0x14001daf4  mov     rcx, rbx; Resource
0x14001daf7  call    cs:__imp_ExReleaseResourceLite
0x14001dafe  nop     dword ptr [rax+rax+00h]
0x14001db03  call    cs:__imp_KeLeaveCriticalRegion
0x14001db0a  nop     dword ptr [rax+rax+00h]
0x14001db0f  mov     rcx, [rsp+1E8h+var_190]; Resource
0x14001db14  mov     [rsp+1E8h+var_190], r12
0x14001db19  test    rcx, rcx
0x14001db1c  jz      short loc_14001DB36
0x14001db1e  call    cs:__imp_ExReleaseResourceLite
0x14001db25  nop     dword ptr [rax+rax+00h]
0x14001db2a  call    cs:__imp_KeLeaveCriticalRegion
0x14001db31  nop     dword ptr [rax+rax+00h]
0x14001db36  mov     r12, qword ptr [rsp+1E8h+var_178]
0x14001db3b  mov     rcx, [r12+48h]
0x14001db40  mov     rcx, [rcx+20h]; this
0x14001db44  call    ?GetBackingFileObject@UfsFsContext2@UnionFs@@QEBAPEBU_FILE_OBJECT@@XZ; UnionFs::UfsFsContext2::GetBackingFileObject(void)
0x14001db49  mov     rbx, rax
  ... truncated ...
```
