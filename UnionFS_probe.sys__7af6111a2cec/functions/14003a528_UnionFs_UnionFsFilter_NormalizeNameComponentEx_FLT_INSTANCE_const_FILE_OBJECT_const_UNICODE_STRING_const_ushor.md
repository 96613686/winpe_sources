# UnionFs::UnionFsFilter::NormalizeNameComponentEx(_FLT_INSTANCE const &,_FILE_OBJECT const &,_UNICODE_STRING const &,ushort,_UNICODE_STRING const &,_FILE_NAMES_INFORMATION *,ulong,ulong,void * *,UnionFs::StackEventTracer &)

- ea: `0x14003a528`
- end: `0x14003b3d5`
- name: `?NormalizeNameComponentEx@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBU_UNICODE_STRING@@G2PEAU_FILE_NAMES_INFORMATION@@KKPEAPEAXAEAVStackEventTracer@2@@Z`
- size: `3757`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, const struct _UNICODE_STRING *, unsigned __int16, const struct _UNICODE_STRING *, struct _FILE_NAMES_INFORMATION *, unsigned int, unsigned int, void **, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003b3e0`

## callees

- `0x140005574`
- `0x140005ff8`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x1400279fc`
- `0x14002ac7c`
- `0x14003a528`
- `0x1400438e4`
- `0x14004452c`
- `0x140055e68`
- `0x140056a14`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140061090`
- `0x14006efa8`
- `0x140075b30`
- `0x140077710`
- `0x140079c48`
- `0x140079d0c`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14003a8ec`
- `ntoskrnl!IoGetSilo` at `0x14003aadd`
- `ntoskrnl!IoGetSilo` at `0x14003aff1`
- `ntoskrnl!IoGetSilo` at `0x14003b0f0`
- `ntoskrnl!IoGetSilo` at `0x14003a8ec`
- `ntoskrnl!IoGetSilo` at `0x14003aadd`
- `ntoskrnl!IoGetSilo` at `0x14003aff1`
- `ntoskrnl!IoGetSilo` at `0x14003b0f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a893`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a9b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ace0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003afac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b069`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a893`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a9b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ace0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad04`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ad48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003afac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b069`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003aa54`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003aa54`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003aa72`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003aa72`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003aaca`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003b105`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003aaca`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003b105`
- `ntoskrnl!PsGetHostSilo` at `0x14003aef3`
- `ntoskrnl!PsGetHostSilo` at `0x14003aef3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003aa3d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003aa3d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b208`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b250`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b327`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b208`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b250`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b327`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003b2f2`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003b2f2`
- `FLTMGR!FltGetVolumeName` at `0x14003ae6c`
- `FLTMGR!FltGetVolumeName` at `0x14003ae6c`
- `FLTMGR!FltCreateFileEx2` at `0x14003b1e1`
- `FLTMGR!FltCreateFileEx2` at `0x14003b1e1`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003add5`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003add5`
- `FLTMGR!FltClose` at `0x14003b265`
- `FLTMGR!FltClose` at `0x14003b33c`
- `FLTMGR!FltClose` at `0x14003b265`
- `FLTMGR!FltClose` at `0x14003b33c`
- `FLTMGR!FltReleaseContext` at `0x14003a7d2`
- `FLTMGR!FltReleaseContext` at `0x14003aa22`
- `FLTMGR!FltReleaseContext` at `0x14003b0d9`
- `FLTMGR!FltReleaseContext` at `0x14003b38e`
- `FLTMGR!FltReleaseContext` at `0x14003a7d2`
- `FLTMGR!FltReleaseContext` at `0x14003aa22`
- `FLTMGR!FltReleaseContext` at `0x14003b0d9`
- `FLTMGR!FltReleaseContext` at `0x14003b38e`
- `FLTMGR!FltObjectDereference` at `0x14003adfb`
- `FLTMGR!FltObjectDereference` at `0x14003ae4d`
- `FLTMGR!FltObjectDereference` at `0x14003af0e`
- `FLTMGR!FltObjectDereference` at `0x14003adfb`
- `FLTMGR!FltObjectDereference` at `0x14003ae4d`
- `FLTMGR!FltObjectDereference` at `0x14003af0e`

## string_xrefs

- `0x14003a5f4`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a6e6`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a77b`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a85b`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a964`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003ab96`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003abe9`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003aca6`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003ad85`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003ae29`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003aeb8`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003b017`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003b22d`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a94f`: `ORIGIN: Allocating parentAndComponent`
- `0x14003b006`: `API: Constructing parentAndComponent`
- `0x14003aea7`: `PUSH: Copying full layer name`
- `0x14003b21c`: `API: Opening parent`
- `0x14003b304`: `API: Getting normalized component name`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::NormalizeNameComponentEx(
        UnionFs::UnionFsFilter *this,
        const struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _UNICODE_STRING *p_UnicodeString,
        unsigned __int16 a5,
        const struct _UNICODE_STRING *a6,
        struct _FILE_NAMES_INFORMATION *a7,
        ULONG Length,
        bool a9,
        void **a10,
        struct UnionFs::StackEventTracer *a11)
{
  struct _FILE_OBJECT *v11; // r15
  bool v14; // r8
  NTSTATUS MappingTableForFileObject; // ebx
  _DWORD *v16; // rsi
  int v17; // edi
  struct _UNICODE_STRING *v18; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v19; // rdx
  struct _UNICODE_STRING *v20; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v21; // rdx
  UnionFs::UfsScratchMappingTable *v22; // rbx
  const struct _FLT_INSTANCE *ScratchInstance; // rax
  struct _UNICODE_STRING *v24; // rdx
  struct _UNICODE_STRING *v25; // rbx
  utl::_RefCountBase *v26; // rdi
  utl::_RefCountBase *v27; // r12
  struct _UNICODE_STRING *v28; // rdx
  const struct _FLT_INSTANCE *v29; // rbx
  const UNICODE_STRING *v30; // rbx
  struct _UNICODE_STRING *v31; // rdx
  struct _UNICODE_STRING *v32; // rdx
  struct _UNICODE_STRING *v33; // rbx
  bool v34; // zf
  struct _UNICODE_STRING *v35; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v36; // rdx
  NTSTATUS appended; // r15d
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rbx
  __int64 v39; // rax
  __int16 v40; // ax
  unsigned __int16 v41; // ax
  __int64 v42; // rcx
  __int64 v43; // rdx
  struct _UNICODE_STRING *v44; // rdx
  _QWORD *v45; // rbx
  struct _UNICODE_STRING *v46; // rdx
  struct _UNICODE_STRING *v47; // rbx
  struct _UNICODE_STRING *v48; // rdx
  struct _UNICODE_STRING *v49; // r14
  utl::_RefCountBase *v50; // rcx
  struct _UNICODE_STRING *v51; // rdx
  struct _UNICODE_STRING *v52; // rbx
  bool v53; // zf
  _QWORD *v54; // r12
  PFLT_VOLUME v55; // r13
  __int64 v56; // r9
  struct _UNICODE_STRING *v57; // r9
  __int64 v58; // rdx
  __int64 v59; // rcx
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // r15
  utl::_RefCountBase *v62; // rcx
  struct _UNICODE_STRING *v63; // rbx
  struct _UNICODE_STRING *v64; // rbx
  struct _UNICODE_STRING *v65; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v66; // rdx
  PVOID v67; // rcx
  const char *v68; // rax
  __int64 v69; // r8
  struct _UNICODE_STRING *v70; // rdx
  PVOID v71; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v72; // rdx
  struct _UNICODE_STRING *v73; // rdx
  PVOID v74; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v75; // rdx
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesb; // [rsp+28h] [rbp-D8h]
  const struct _UNICODE_STRING *IoStatusBlock; // [rsp+30h] [rbp-D0h]
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  PVOID FltObject; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  ULONG BufferSizeNeeded; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v86; // [rsp+B8h] [rbp-48h] BYREF
  PFILE_OBJECT FileObject; // [rsp+C0h] [rbp-40h]
  void *FileHandle; // [rsp+C8h] [rbp-38h] BYREF
  PVOID *p_FltObject; // [rsp+D0h] [rbp-30h]
  PFLT_VOLUME RetVolume; // [rsp+D8h] [rbp-28h] BYREF
  char v91; // [rsp+E0h] [rbp-20h]
  __int64 v92; // [rsp+E8h] [rbp-18h] BYREF
  utl::_RefCountBase *v93[2]; // [rsp+F0h] [rbp-10h]
  PVOID P; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING v95; // [rsp+110h] [rbp+10h] BYREF
  char v96; // [rsp+120h] [rbp+20h]
  PCUNICODE_STRING Source; // [rsp+150h] [rbp+50h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+158h] [rbp+58h] BYREF
  __int64 Silo; // [rsp+178h] [rbp+78h]
  PVOID v100; // [rsp+180h] [rbp+80h] BYREF
  PVOID FileInformation; // [rsp+188h] [rbp+88h]
  struct _OBJECT_ATTRIBUTES v102; // [rsp+190h] [rbp+90h] BYREF
  struct _IO_STATUS_BLOCK v103; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v104[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v105[14]; // [rsp+1D8h] [rbp+D8h] BYREF
  PFLT_CONTEXT v106; // [rsp+248h] [rbp+148h]
  utl::_RefCountBase *v107; // [rsp+250h] [rbp+150h]
  __int64 v108; // [rsp+258h] [rbp+158h] BYREF
  char v109; // [rsp+260h] [rbp+160h]
  _BYTE v110[112]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v111; // [rsp+2D8h] [rbp+1D8h]
  PFLT_CONTEXT Context[3]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v113[17]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v114[80]; // [rsp+380h] [rbp+280h] BYREF
  bool v115; // [rsp+460h] [rbp+360h]

  v11 = a3;
  Source = a6;
  FileObject = a3;
  FileInformation = a7;
  memset(Context, 0, sizeof(Context));
  memset(v113, 0, sizeof(v113));
  MappingTableForFileObject = UnionFs::UfsStreamHandleCtx::FltGet(
                                a2,
                                v11,
                                v14,
                                (struct UnionFs::HandleCtxAndUnionWithRundown *)Context,
                                a11);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a11,
      (struct UnionFs::StackEventTracer *)0x176000F017CLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
      "PUSH: Getting streamhandle ctx",
      ObjectAttributes);
    goto LABEL_174;
  }
  v16 = Context[0];
  v106 = Context[1];
  v107 = (utl::_RefCountBase *)Context[2];
  v108 = v113[0];
  v109 = v113[1];
  memset(Context, 0, sizeof(Context));
  wistd::function<void (bool)>::function<void (bool)>(v110, &v113[2]);
  memset(v113, 0, sizeof(v113));
  Silo = 1;
  v115 = !a9;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  UnicodeString = 0;
  if ( !v16 || (*v16 & 1) == 0 )
  {
    Silo = IoGetSilo(v11);
    v17 = 0;
    goto LABEL_146;
  }
  if ( !v106 )
  {
    v17 = -1058209784;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0008LL,
      (int)a11,
      (struct UnionFs::StackEventTracer *)0x608000F019ALL,
      (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
      "ORIGIN: Inactive union for SFO",
      ObjectAttributes);
LABEL_7:
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v18);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v19);
    if ( v111 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
    if ( v107 )
      utl::_RefCountBase::_DecStrong(v107);
LABEL_172:
    FltReleaseContext(v16);
LABEL_173:
    MappingTableForFileObject = v17;
    goto LABEL_174;
  }
  FltObject = 0;
  MappingTableForFileObject = UnionFs::Utils::GetMappingTableForFileObject(a2, v11, &FltObject, a11, 0);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a11,
      (struct UnionFs::StackEventTracer *)0x2B5000F01A2LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
      "PUSH: Getting mapping table",
      ObjectAttributes);
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v20);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v21);
    if ( v111 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
    if ( v107 )
      utl::_RefCountBase::_DecStrong(v107);
    goto LABEL_16;
  }
  v22 = (UnionFs::UfsScratchMappingTable *)FltObject;
  if ( !FltObject )
    MicrosoftTelemetryAssertTriggeredMsgKM("Shouldn't have been called without a mapping table");
  UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&v95, p_UnicodeString, a5);
  v92 = 0;
  P = 0;
  *(_OWORD *)v93 = 0;
  ScratchInstance = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance((UnionFs::UfsStreamHandleCtx *)v16);
  v17 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
          v22,
          ScratchInstance,
          (const struct UnionFs::UfsPathName *)&v95,
          v115,
          (struct UnionFs::LookupScratchRootResults *)&v92,
          a11);
  if ( v17 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v17,
      (int)a11,
      (struct UnionFs::StackEventTracer *)0x179000F01AFLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
      "PUSH: Looking up name in mapping table",
      ObjectAttributesa);
    v25 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v25, v24);
      ExFreePoolWithTag(v25, 0);
    }
    if ( v93[1] )
      utl::_RefCountBase::_DecStrong(v93[1]);
    if ( !v96 )
      v95 = 0;
    FsFltWil::Details::FreeUnicodeString(&v95, v24);
    goto LABEL_7;
  }
  v26 = v93[1];
  v27 = v93[0];
  if ( v93[1] )
    _InterlockedIncrement((volatile signed __int32 *)v93[1] + 2);
  if ( v27 )
  {
    v29 = (const struct _FLT_INSTANCE *)**((_QWORD **)v27 + 1);
    if ( UnionFs::UfsStreamHandleCtx::TryGetScratchInstance((UnionFs::UfsStreamHandleCtx *)v16) != v29 )
      MicrosoftTelemetryAssertTriggeredMsgKM("handleCtx->TryGetScratchInstance() == scratchCtx->GetInstance()");
    v30 = Source;
    FsFltWil::MakeUniqueUnicodeString(
      &DestinationString,
      (unsigned __int16)(p_UnicodeString->MaximumLength + Source->MaximumLength + 2),
      1835943509);
    if ( !DestinationString.Buffer )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a11,
        (struct UnionFs::StackEventTracer *)0x17C000F01CBLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
        "ORIGIN: Allocating parentAndComponent",
        ObjectAttributesa);
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v31);
      if ( v26 )
        utl::_RefCountBase::_DecStrong(v26);
      v33 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v33, v32);
        ExFreePoolWithTag(v33, 0);
      }
      if ( v26 )
        utl::_RefCountBase::_DecStrong(v26);
      v34 = v96 == 0;
LABEL_45:
      if ( v34 )
        v95 = 0;
      FsFltWil::Details::FreeUnicodeString(&v95, v32);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v35);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v36);
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
      if ( v107 )
        utl::_RefCountBase::_DecStrong(v107);
      FltReleaseContext(v16);
      MappingTableForFileObject = -1073741670;
      goto LABEL_174;
    }
    RtlCopyUnicodeString(&DestinationString, p_UnicodeString);
    appended = RtlAppendUnicodeToString(&DestinationString, L"\\");
    if ( appended < 0 || (appended = RtlAppendUnicodeStringToString(&DestinationString, v30), appended < 0) )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        (int)a11,
        (struct UnionFs::StackEventTracer *)0x17D000F01D4LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
        "API: Constructing parentAndComponent",
        ObjectAttributesa);
      goto LABEL_129;
    }
    v105[0] = off_14007E740;
    v105[13] = v105;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a11, v104);
    memset(v114, 0, 0x48u);
    TransactionParameterBlock = IoGetTransactionParameterBlock(FileObject);
    v39 = IoGetSilo(FileObject);
    IoStatusBlock = (const struct _UNICODE_STRING *)TransactionParameterBlock;
    appended = UnionFs::Utils::StatItem(&DestinationString, **((_QWORD **)v27 + 1), v39, v115, v114);
    v40 = *((_WORD *)a11 + 245);
    if ( v40 )
    {
      v41 = v40 - 1;
      *((_WORD *)a11 + 245) = v41;
      v42 = 120 * (v41 + 1LL);
      v43 = *(_QWORD *)((char *)a11 + v42);
      *(_QWORD *)((char *)a11 + v42) = 0;
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
    }
    if ( appended >= 0 )
    {
      v11 = FileObject;
      a2 = (const struct _FLT_INSTANCE *)**((_QWORD **)v27 + 1);
      Silo = IoGetSilo(FileObject);
    }
    else
    {
      if ( appended != -1073741766 && appended != -1073741772 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x17E000F01EELL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "PUSH: Querying stat information",
          (const char *)a11);
LABEL_129:
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v44);
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v64 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v64, v51);
          ExFreePoolWithTag(v64, 0);
        }
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v53 = v96 == 0;
LABEL_138:
        if ( v53 )
          v95 = 0;
        FsFltWil::Details::FreeUnicodeString(&v95, v51);
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v65);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v66);
        if ( v111 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
        if ( v107 )
          utl::_RefCountBase::_DecStrong(v107);
        FltReleaseContext(v16);
        MappingTableForFileObject = appended;
        goto LABEL_174;
      }
      utl::make_unique<UnionFs::FindAndStatResults,,0>(&v100);
      v45 = v100;
      if ( !v100 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x3E5000F0201LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "ORIGIN: Allocating findAndStatResults",
          (const char *)a11);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v46);
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v47 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v47, v32);
          ExFreePoolWithTag(v47, 0);
        }
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v34 = v96 == 0;
        goto LABEL_45;
      }
      v86 = 0;
      *((_QWORD *)v100 + 12) = &v86;
      appended = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v106, &DestinationString, v16, v115, v45);
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x17F000F020DLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "PUSH: Utils::FindAndStatItemInLayers",
          (const char *)a11);
LABEL_73:
        v49 = (struct _UNICODE_STRING *)v86;
        if ( v86 )
        {
          if ( !*((_BYTE *)v86 + 16) )
            *(_OWORD *)v86 = 0;
          FsFltWil::Details::FreeUnicodeString(v49, v48);
          ExFreePoolWithTag(v49, 0);
        }
        if ( v45 )
        {
          v50 = (utl::_RefCountBase *)v45[11];
          if ( v50 )
            utl::_RefCountBase::_DecStrong(v50);
          ExFreePoolWithTag(v45, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v48);
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v52 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v52, v51);
          ExFreePoolWithTag(v52, 0);
        }
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v53 = v96 == 0;
        goto LABEL_138;
      }
      if ( *(_WORD *)v45 != 1 )
      {
        appended = -1073741809;
        UnionFs::ProcessTraceInfoOrigin(
          (UnionFs *)0xC000000FLL,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x5F3000F0218LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "ORIGIN: Not found",
          (const char *)&DestinationString,
          IoStatusBlock);
        goto LABEL_73;
      }
      FltObject = 0;
      p_FltObject = &FltObject;
      RetVolume = 0;
      v91 = 1;
      appended = FltGetVolumeFromInstance(**(PFLT_INSTANCE **)(v45[10] + 8LL), &RetVolume);
      if ( v91 )
      {
        v54 = p_FltObject;
        v55 = RetVolume;
        if ( *p_FltObject )
          FltObjectDereference(*p_FltObject);
        *v54 = v55;
      }
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x180000F0225LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "API: Getting volume from instance",
          (const char *)a11);
        goto LABEL_98;
      }
      BufferSizeNeeded = 0;
      FltGetVolumeName((PFLT_VOLUME)FltObject, 0, &BufferSizeNeeded);
      if ( BufferSizeNeeded > 0xFFFF )
        MicrosoftTelemetryAssertTriggeredMsgKM("volumeNameSize <= MAXUSHORT");
      LOBYTE(v56) = 1;
      appended = UnionFs::UfsPathName::AsUnicodeString(v86, &UnicodeString, a11, v56);
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x1F7000F0234LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "PUSH: Copying full layer name",
          (const char *)a11);
LABEL_98:
        if ( FltObject )
          FltObjectDereference(FltObject);
        goto LABEL_73;
      }
      UnionFs::Utils::RemoveFinalComponent(
        (UnionFs::Utils *)&UnicodeString,
        (struct _UNICODE_STRING *)(unsigned __int16)BufferSizeNeeded,
        0,
        v57);
      p_UnicodeString = &UnicodeString;
      a2 = **(const struct _FLT_INSTANCE ***)(v45[10] + 8LL);
      Silo = PsGetHostSilo(v59, v58);
      if ( FltObject )
        FltObjectDereference(FltObject);
      v61 = (struct _UNICODE_STRING *)v86;
      if ( v86 )
      {
        if ( !*((_BYTE *)v86 + 16) )
          *(_OWORD *)v86 = 0;
        FsFltWil::Details::FreeUnicodeString(v61, v60);
        ExFreePoolWithTag(v61, 0);
      }
      if ( v45 )
      {
        v62 = (utl::_RefCountBase *)v45[11];
        if ( v62 )
          utl::_RefCountBase::_DecStrong(v62);
        ExFreePoolWithTag(v45, 0);
      }
      v11 = FileObject;
    }
    FsFltWil::Details::FreeUnicodeString(&DestinationString, v60);
    goto LABEL_116;
  }
  a2 = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance((UnionFs::UfsStreamHandleCtx *)v16);
  Silo = IoGetSilo(v11);
LABEL_116:
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  v63 = (struct _UNICODE_STRING *)P;
  if ( P )
  {
    if ( !*((_BYTE *)P + 16) )
      *(_OWORD *)P = 0;
    FsFltWil::Details::FreeUnicodeString(v63, v28);
    ExFreePoolWithTag(v63, 0);
  }
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  v17 = 0;
  if ( !v96 )
    v95 = 0;
  FsFltWil::Details::FreeUnicodeString(&v95, v28);
LABEL_146:
  DriverContext.TxnParameters = IoGetTransactionParameterBlock(v11);
  *(_QWORD *)&v102.Length = 48;
  v102.Attributes = (v115 << 6) | 0x200;
  memset(&v102.Attributes + 1, 0, 20);
  p_FltObject = &Object;
  v102.RootDirectory = 0;
  v102.ObjectName = p_UnicodeString;
  Object = 0;
  v103 = 0;
  RetVolume = 0;
  v91 = 1;
  FileHandle = 0;
  MappingTableForFileObject = FltCreateFileEx2(
                                *(PFLT_FILTER *)UnionFs::g_FilterState,
                                a2,
                                &FileHandle,
                                (PFILE_OBJECT *)&RetVolume,
                                0x80u,
                                &v102,
                                &v103,
                                0,
                                0,
                                7u,
                                1u,
                                0x20u,
                                0,
                                0,
                                0,
                                &DriverContext);
  if ( v91 )
  {
    v67 = *p_FltObject;
    *p_FltObject = RetVolume;
    if ( v67 )
      ObfDereferenceObject(v67);
  }
  if ( MappingTableForFileObject >= 0 )
  {
    MappingTableForFileObject = FltQueryDirectoryFile(
                                  a2,
                                  (PFILE_OBJECT)Object,
                                  FileInformation,
                                  Length,
                                  FileNamesInformation,
                                  1u,
                                  (PUNICODE_STRING)Source,
                                  1u,
                                  0);
    if ( MappingTableForFileObject >= 0 )
    {
      v74 = Object;
      Object = 0;
      if ( v74 )
        ObfDereferenceObject(v74);
      if ( FileHandle )
        FltClose(FileHandle);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v73);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v75);
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
      if ( v107 )
        utl::_RefCountBase::_DecStrong(v107);
      if ( !v16 )
        goto LABEL_173;
      goto LABEL_172;
    }
    v68 = "API: Getting normalized component name";
    v69 = 0x178000F026FLL;
  }
  else
  {
    v68 = "API: Opening parent";
    v69 = 0x177000F0261LL;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)MappingTableForFileObject,
    (int)a11,
    (struct UnionFs::StackEventTracer *)v69,
    (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
    v68,
    ObjectAttributesb);
  v71 = Object;
  Object = 0;
  if ( v71 )
    ObfDereferenceObject(v71);
  if ( FileHandle )
    FltClose(FileHandle);
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v70);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v72);
  if ( v111 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
  if ( v107 )
    utl::_RefCountBase::_DecStrong(v107);
  if ( v16 )
LABEL_16:
    FltReleaseContext(v16);
LABEL_174:
  UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
  return (unsigned int)MappingTableForFileObject;
}

```

## disassembly

```asm
0x14003a528  mov     [rsp-8+arg_0], rbx
0x14003a52d  push    rbp
0x14003a52e  push    rsi
0x14003a52f  push    rdi
0x14003a530  push    r12
0x14003a532  push    r13
0x14003a534  push    r14
0x14003a536  push    r15
0x14003a538  lea     rbp, [rsp-2E0h]
0x14003a540  sub     rsp, 3E0h
0x14003a547  mov     rax, cs:__security_cookie
0x14003a54e  xor     rax, rsp
0x14003a551  mov     [rbp+310h+var_40], rax
0x14003a558  mov     rax, [rbp+310h+arg_28]
0x14003a55f  lea     rcx, [rbp+310h+var_118]; void *
0x14003a566  movzx   edi, [rbp+310h+arg_20]
0x14003a56d  mov     r15, r8
0x14003a570  mov     r14, [rbp+310h+arg_50]
0x14003a577  mov     r12, rdx
0x14003a57a  mov     [rbp+310h+Source], rax
0x14003a57e  xorps   xmm0, xmm0
0x14003a581  mov     rax, [rbp+310h+arg_30]
0x14003a588  xorps   xmm1, xmm1
0x14003a58b  mov     [rbp+310h+FileObject], r8
0x14003a58f  xor     esi, esi
0x14003a591  xor     edx, edx; Val
0x14003a593  mov     [rbp+310h+FileInformation], rax
0x14003a59a  mov     r8d, 88h; Size
0x14003a5a0  mov     [rbp+310h+var_110], sil
0x14003a5a7  mov     r13, r9
0x14003a5aa  mov     [rbp+310h+var_98], rsi
0x14003a5b1  movdqu  xmmword ptr [rbp+310h+Context], xmm0
0x14003a5b9  movdqu  xmmword ptr [rbp+1F0h], xmm1
0x14003a5c1  call    memset
0x14003a5c6  lea     r9, [rbp+310h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14003a5cd  mov     qword ptr [rsp+410h+DesiredAccess], r14; struct UnionFs::StackEventTracer *
0x14003a5d2  mov     rdx, r15; FileObject
0x14003a5d5  mov     rcx, r12; Instance
0x14003a5d8  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14003a5dd  mov     ebx, eax
0x14003a5df  test    eax, eax
0x14003a5e1  jns     short loc_14003A60F
0x14003a5e3  lea     rax, aPushGettingStr_0; "PUSH: Getting streamhandle ctx"
0x14003a5ea  mov     r8, 176000F017Ch; struct UnionFs::StackEventTracer *
0x14003a5f4  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a5fb  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a600  mov     rdx, r14; int
0x14003a603  mov     ecx, ebx; this
0x14003a605  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a60a  jmp     loc_14003B39C
0x14003a60f  mov     rax, [rbp+310h+Context+8]
0x14003a616  lea     rdx, [rbp+310h+var_108]
0x14003a61d  mov     rsi, [rbp+310h+Context]
0x14003a624  lea     rcx, [rbp+310h+var_1A8]
0x14003a62b  mov     [rbp+310h+var_1C8], rax
0x14003a632  xorps   xmm0, xmm0
0x14003a635  mov     rax, [rbp+310h+var_120]
0x14003a63c  xor     ebx, ebx
0x14003a63e  mov     [rbp+310h+var_1C0], rax
0x14003a645  mov     rax, [rbp+310h+var_118]
0x14003a64c  mov     [rbp+310h+var_1B8], rax
0x14003a653  mov     al, [rbp+310h+var_110]
0x14003a659  mov     [rbp+310h+var_1B0], al
0x14003a65f  mov     [rbp+310h+Context], rbx
0x14003a666  movdqu  xmmword ptr [rbp+310h+Context+8], xmm0
0x14003a66e  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14003a673  xor     edx, edx; Val
0x14003a675  lea     rcx, [rbp+310h+var_118]; void *
0x14003a67c  mov     r8d, 88h; Size
0x14003a682  call    memset
0x14003a687  mov     al, [rbp+310h+arg_40]
0x14003a68d  lea     ecx, [rbx+1]
0x14003a690  not     al
0x14003a692  mov     [rbp+310h+var_298], rcx
0x14003a696  and     al, cl
0x14003a698  xorps   xmm1, xmm1
0x14003a69b  mov     [rbp+310h+arg_40], al
0x14003a6a1  lea     eax, [rbx+28h]
0x14003a6a4  xorps   xmm0, xmm0
0x14003a6a7  movups  xmmword ptr [rbp+310h+var_2B8.Size], xmm1
0x14003a6ab  mov     [rbp+310h+var_2B8.Size], ax
0x14003a6af  movups  xmmword ptr [rbp+310h+UnicodeString.Length], xmm0
0x14003a6b3  movups  xmmword ptr [rbp+310h+var_2B8.DeviceObjectHint], xmm1
0x14003a6b7  test    rsi, rsi
0x14003a6ba  jz      loc_14003B0ED
0x14003a6c0  mov     eax, [rsi]
0x14003a6c2  test    cl, al
0x14003a6c4  jz      loc_14003B0ED
0x14003a6ca  cmp     [rbp+310h+var_1C8], rbx
0x14003a6d1  jnz     short loc_14003A746
0x14003a6d3  lea     rax, aOriginInactive; "ORIGIN: Inactive union for SFO"
0x14003a6da  mov     edi, 0C0ED0008h
0x14003a6df  mov     ecx, edi; this
0x14003a6e1  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a6e6  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a6ed  mov     r8, 608000F019Ah; struct UnionFs::StackEventTracer *
0x14003a6f7  mov     rdx, r14; int
0x14003a6fa  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a6ff  lea     rcx, [rbp+310h+UnicodeString]; UnicodeString
0x14003a703  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a708  lea     rcx, [rbp+310h+var_1B8]; this
0x14003a70f  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003a714  mov     rcx, [rbp+310h+var_138]
0x14003a71b  test    rcx, rcx
0x14003a71e  jz      short loc_14003A72C
0x14003a720  mov     rax, [rcx]
0x14003a723  mov     rax, [rax+18h]
0x14003a727  call    _guard_dispatch_icall
0x14003a72c  mov     rcx, [rbp+310h+var_1C0]; this
0x14003a733  test    rcx, rcx
0x14003a736  jz      loc_14003B38B
0x14003a73c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a741  jmp     loc_14003B38B
0x14003a746  mov     r9, r14
0x14003a749  mov     [rbp+310h+FltObject], rbx
0x14003a74d  lea     r8, [rbp+310h+FltObject]
0x14003a751  mov     qword ptr [rsp+410h+DesiredAccess], rbx
0x14003a756  mov     rdx, r15
0x14003a759  mov     rcx, r12
0x14003a75c  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x14003a761  xor     r12d, r12d
0x14003a764  mov     ebx, eax
0x14003a766  test    eax, eax
0x14003a768  jns     short loc_14003A7E3
0x14003a76a  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x14003a771  mov     r8, 2B5000F01A2h; struct UnionFs::StackEventTracer *
0x14003a77b  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a782  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a787  mov     rdx, r14; int
0x14003a78a  mov     ecx, ebx; this
0x14003a78c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a791  lea     rcx, [rbp+310h+UnicodeString]; UnicodeString
0x14003a795  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a79a  lea     rcx, [rbp+310h+var_1B8]; this
0x14003a7a1  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003a7a6  mov     rcx, [rbp+310h+var_138]
0x14003a7ad  test    rcx, rcx
0x14003a7b0  jz      short loc_14003A7BE
0x14003a7b2  mov     rax, [rcx]
0x14003a7b5  mov     rax, [rax+18h]
0x14003a7b9  call    _guard_dispatch_icall
0x14003a7be  mov     rcx, [rbp+310h+var_1C0]; this
0x14003a7c5  test    rcx, rcx
0x14003a7c8  jz      short loc_14003A7CF
0x14003a7ca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a7cf  mov     rcx, rsi; Context
0x14003a7d2  call    cs:__imp_FltReleaseContext
0x14003a7d9  nop     dword ptr [rax+rax+00h]
0x14003a7de  jmp     loc_14003B39C
0x14003a7e3  mov     rbx, [rbp+310h+FltObject]
0x14003a7e7  test    rbx, rbx
0x14003a7ea  jnz     short loc_14003A7F8
0x14003a7ec  lea     rcx, aShouldnTHaveBe; "Shouldn't have been called without a ma"...
0x14003a7f3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003a7f8  movzx   r8d, di; unsigned __int16
0x14003a7fc  lea     rcx, [rbp+310h+var_300]; this
0x14003a800  mov     rdx, r13; struct _UNICODE_STRING *
0x14003a803  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x14003a808  xorps   xmm2, xmm2
0x14003a80b  mov     [rbp+310h+var_328], r12
0x14003a80f  mov     rcx, rsi; this
0x14003a812  mov     [rbp+310h+P], r12
0x14003a816  movdqu  xmmword ptr [rbp+310h+var_320], xmm2
0x14003a81b  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14003a820  mov     r9b, [rbp+310h+arg_40]; bool
0x14003a827  lea     rcx, [rbp+310h+var_328]
0x14003a82b  mov     [rsp+410h+ObjectAttributes], r14; char *
0x14003a830  lea     r8, [rbp+310h+var_300]; struct UnionFs::UfsPathName *
0x14003a834  mov     qword ptr [rsp+410h+DesiredAccess], rcx; struct UnionFs::LookupScratchRootResults *
0x14003a839  mov     rdx, rax; struct _FLT_INSTANCE *
0x14003a83c  mov     rcx, rbx; this
0x14003a83f  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x14003a844  mov     edi, eax
0x14003a846  test    eax, eax
0x14003a848  jns     short loc_14003A8C8
0x14003a84a  lea     rax, aPushLookingUpN_0; "PUSH: Looking up name in mapping table"
0x14003a851  mov     r8, 179000F01AFh; struct UnionFs::StackEventTracer *
0x14003a85b  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a862  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a867  mov     rdx, r14; int
0x14003a86a  mov     ecx, edi; this
0x14003a86c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a871  mov     rbx, [rbp+310h+P]
0x14003a875  test    rbx, rbx
0x14003a878  jz      short loc_14003A89F
0x14003a87a  cmp     [rbx+10h], r12b
0x14003a87e  jnz     short loc_14003A886
0x14003a880  xorps   xmm0, xmm0
0x14003a883  movups  xmmword ptr [rbx], xmm0
0x14003a886  mov     rcx, rbx; UnicodeString
0x14003a889  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a88e  xor     edx, edx; Tag
0x14003a890  mov     rcx, rbx; P
0x14003a893  call    cs:__imp_ExFreePoolWithTag
0x14003a89a  nop     dword ptr [rax+rax+00h]
0x14003a89f  mov     rcx, [rbp+310h+var_320+8]; this
0x14003a8a3  test    rcx, rcx
0x14003a8a6  jz      short loc_14003A8AD
0x14003a8a8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a8ad  cmp     [rbp+310h+var_2F0], r12b
0x14003a8b1  jnz     short loc_14003A8BA
0x14003a8b3  xorps   xmm0, xmm0
0x14003a8b6  movups  xmmword ptr [rbp+310h+var_300.Length], xmm0
0x14003a8ba  lea     rcx, [rbp+310h+var_300]; UnicodeString
0x14003a8be  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a8c3  jmp     loc_14003A6FF
0x14003a8c8  mov     rdi, [rbp+310h+var_320+8]
0x14003a8cc  mov     r12, [rbp+310h+var_320]
0x14003a8d0  test    rdi, rdi
0x14003a8d3  jz      short loc_14003A8D9
0x14003a8d5  lock inc dword ptr [rdi+8]
0x14003a8d9  mov     rcx, rsi; this
0x14003a8dc  test    r12, r12
0x14003a8df  jnz     short loc_14003A901
0x14003a8e1  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14003a8e6  mov     rcx, r15
0x14003a8e9  mov     r12, rax
0x14003a8ec  call    cs:__imp_IoGetSilo
0x14003a8f3  nop     dword ptr [rax+rax+00h]
0x14003a8f8  mov     [rbp+310h+var_298], rax
0x14003a8fc  jmp     loc_14003AF7C
0x14003a901  mov     rax, [r12+8]
0x14003a906  mov     rbx, [rax]
0x14003a909  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14003a90e  cmp     rax, rbx
0x14003a911  jz      short loc_14003A91F
0x14003a913  lea     rcx, aHandlectxTryge; "handleCtx->TryGetScratchInstance() == s"...
0x14003a91a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003a91f  mov     rbx, [rbp+310h+Source]
0x14003a923  lea     rcx, [rbp+310h+DestinationString]
0x14003a927  mov     r8d, 6D6E4655h
0x14003a92d  movzx   edx, word ptr [rbx+2]
0x14003a931  add     dx, 2
0x14003a935  add     dx, [r13+2]
0x14003a93a  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14003a93f  xor     r15d, r15d
0x14003a942  cmp     [rbp+310h+DestinationString.Buffer], r15
0x14003a946  jnz     loc_14003AA36
0x14003a94c  mov     rdx, r14; int
0x14003a94f  lea     rax, aOriginAllocati_15; "ORIGIN: Allocating parentAndComponent"
0x14003a956  mov     r14d, 0C000009Ah
0x14003a95c  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a961  mov     ecx, r14d; this
0x14003a964  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a96b  mov     r8, 17C000F01CBh; struct UnionFs::StackEventTracer *
0x14003a975  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a97a  lea     rcx, [rbp+310h+DestinationString]; UnicodeString
0x14003a97e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a983  test    rdi, rdi
0x14003a986  jz      short loc_14003A990
0x14003a988  mov     rcx, rdi; this
0x14003a98b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a990  mov     rbx, [rbp+310h+P]
0x14003a994  test    rbx, rbx
0x14003a997  jz      short loc_14003A9BE
0x14003a999  cmp     [rbx+10h], r15b
0x14003a99d  jnz     short loc_14003A9A5
0x14003a99f  xorps   xmm0, xmm0
0x14003a9a2  movups  xmmword ptr [rbx], xmm0
0x14003a9a5  mov     rcx, rbx; UnicodeString
0x14003a9a8  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a9ad  xor     edx, edx; Tag
0x14003a9af  mov     rcx, rbx; P
0x14003a9b2  call    cs:__imp_ExFreePoolWithTag
0x14003a9b9  nop     dword ptr [rax+rax+00h]
0x14003a9be  test    rdi, rdi
0x14003a9c1  jz      short loc_14003A9CB
0x14003a9c3  mov     rcx, rdi; this
0x14003a9c6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a9cb  cmp     [rbp+310h+var_2F0], r15b
0x14003a9cf  jnz     short loc_14003A9D8
0x14003a9d1  xorps   xmm0, xmm0
0x14003a9d4  movups  xmmword ptr [rbp+310h+var_300.Length], xmm0
0x14003a9d8  lea     rcx, [rbp+310h+var_300]; UnicodeString
0x14003a9dc  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a9e1  lea     rcx, [rbp+310h+UnicodeString]; UnicodeString
0x14003a9e5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a9ea  lea     rcx, [rbp+310h+var_1B8]; this
0x14003a9f1  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003a9f6  mov     rcx, [rbp+310h+var_138]
0x14003a9fd  test    rcx, rcx
0x14003aa00  jz      short loc_14003AA0E
0x14003aa02  mov     rax, [rcx]
0x14003aa05  mov     rax, [rax+18h]
0x14003aa09  call    _guard_dispatch_icall
0x14003aa0e  mov     rcx, [rbp+310h+var_1C0]; this
0x14003aa15  test    rcx, rcx
0x14003aa18  jz      short loc_14003AA1F
0x14003aa1a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003aa1f  mov     rcx, rsi; Context
0x14003aa22  call    cs:__imp_FltReleaseContext
0x14003aa29  nop     dword ptr [rax+rax+00h]
0x14003aa2e  mov     ebx, r14d
0x14003aa31  jmp     loc_14003B39C
0x14003aa36  mov     rdx, r13; SourceString
0x14003aa39  lea     rcx, [rbp+310h+DestinationString]; DestinationString
0x14003aa3d  call    cs:__imp_RtlCopyUnicodeString
0x14003aa44  nop     dword ptr [rax+rax+00h]
0x14003aa49  lea     rdx, Source; "\\"
0x14003aa50  lea     rcx, [rbp+310h+DestinationString]; Destination
  ... truncated ...
```
