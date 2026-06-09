# UnionFs::UnionFsFilter::NormalizeNameComponentEx(_FLT_INSTANCE const &,_FILE_OBJECT const &,_UNICODE_STRING const &,ushort,_UNICODE_STRING const &,_FILE_NAMES_INFORMATION *,ulong,ulong,void * *,UnionFs::StackEventTracer &)

- ea: `0x14003a668`
- end: `0x14003b4ec`
- name: `?NormalizeNameComponentEx@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBU_UNICODE_STRING@@G2PEAU_FILE_NAMES_INFORMATION@@KKPEAPEAXAEAVStackEventTracer@2@@Z`
- size: `3716`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, const struct _UNICODE_STRING *, unsigned __int16, const struct _UNICODE_STRING *, struct _FILE_NAMES_INFORMATION *, unsigned int, unsigned int, void **, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x14003b500`

## callees

- `0x140005574`
- `0x140005ff8`
- `0x14000efa0`
- `0x14000f81c`
- `0x140010ba8`
- `0x140027a9c`
- `0x14002ad1c`
- `0x14003a668`
- `0x140043a64`
- `0x1400446ac`
- `0x140055fe8`
- `0x140056b94`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140061210`
- `0x14006f198`
- `0x140075d30`
- `0x1400779fc`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14003aa2c`
- `ntoskrnl!IoGetSilo` at `0x14003acde`
- `ntoskrnl!IoGetSilo` at `0x14003b1ef`
- `ntoskrnl!IoGetSilo` at `0x14003b207`
- `ntoskrnl!IoGetSilo` at `0x14003aa2c`
- `ntoskrnl!IoGetSilo` at `0x14003acde`
- `ntoskrnl!IoGetSilo` at `0x14003b1ef`
- `ntoskrnl!IoGetSilo` at `0x14003b207`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a9d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aaee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ae38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b140`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b164`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b1ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a9d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aaee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ac06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ae38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003aee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003af49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b140`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b164`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b1ad`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003ab8c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003ab8c`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003accb`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003b21c`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003accb`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14003b21c`
- `ntoskrnl!PsGetHostSilo` at `0x14003b0f4`
- `ntoskrnl!PsGetHostSilo` at `0x14003b0f4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003ab79`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003ab79`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b31f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b367`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b43e`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b31f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b367`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b43e`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003b409`
- `FLTMGR!FltQueryDirectoryFile` at `0x14003b409`
- `FLTMGR!FltGetVolumeName` at `0x14003b06d`
- `FLTMGR!FltGetVolumeName` at `0x14003b06d`
- `FLTMGR!FltCreateFileEx2` at `0x14003b2f8`
- `FLTMGR!FltCreateFileEx2` at `0x14003b2f8`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003afd6`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003afd6`
- `FLTMGR!FltClose` at `0x14003b37c`
- `FLTMGR!FltClose` at `0x14003b453`
- `FLTMGR!FltClose` at `0x14003b37c`
- `FLTMGR!FltClose` at `0x14003b453`
- `FLTMGR!FltReleaseContext` at `0x14003a912`
- `FLTMGR!FltReleaseContext` at `0x14003ab5e`
- `FLTMGR!FltReleaseContext` at `0x14003ac76`
- `FLTMGR!FltReleaseContext` at `0x14003b4a5`
- `FLTMGR!FltReleaseContext` at `0x14003a912`
- `FLTMGR!FltReleaseContext` at `0x14003ab5e`
- `FLTMGR!FltReleaseContext` at `0x14003ac76`
- `FLTMGR!FltReleaseContext` at `0x14003b4a5`
- `FLTMGR!FltObjectDereference` at `0x14003affc`
- `FLTMGR!FltObjectDereference` at `0x14003b04e`
- `FLTMGR!FltObjectDereference` at `0x14003b10f`
- `FLTMGR!FltObjectDereference` at `0x14003affc`
- `FLTMGR!FltObjectDereference` at `0x14003b04e`
- `FLTMGR!FltObjectDereference` at `0x14003b10f`

## string_xrefs

- `0x14003a734`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a826`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a8bb`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003a99b`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003aaa0`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003abb4`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003ad97`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003adea`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003aea7`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003af86`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003b02a`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003b0b9`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003b344`: `UnionFs::UnionFsFilter::NormalizeNameComponentEx`
- `0x14003aa8b`: `ORIGIN: Allocating parentAndComponent`
- `0x14003aba3`: `API: Constructing parentAndComponent`
- `0x14003b0a8`: `PUSH: Copying full layer name`
- `0x14003b333`: `API: Opening parent`
- `0x14003b41b`: `API: Getting normalized component name`

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
  struct _UNICODE_STRING *v38; // rdx
  struct _UNICODE_STRING *v39; // rdx
  struct _UNICODE_STRING *v40; // rbx
  bool v41; // zf
  struct _UNICODE_STRING *v42; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v43; // rdx
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rbx
  __int64 v45; // rax
  __int16 v46; // ax
  unsigned __int16 v47; // ax
  __int64 v48; // rcx
  __int64 v49; // rdx
  _QWORD *v50; // rbx
  struct _UNICODE_STRING *v51; // rdx
  struct _UNICODE_STRING *v52; // rbx
  struct _UNICODE_STRING *v53; // rdx
  struct _UNICODE_STRING *v54; // r14
  utl::_RefCountBase *v55; // rcx
  struct _UNICODE_STRING *v56; // rbx
  _QWORD *v57; // r12
  PFLT_VOLUME v58; // r13
  __int64 v59; // r9
  struct _UNICODE_STRING *v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rcx
  struct _UNICODE_STRING *v63; // rdx
  struct _UNICODE_STRING *v64; // r15
  utl::_RefCountBase *v65; // rcx
  struct _UNICODE_STRING *v66; // rbx
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
  ULONG BufferSizeNeeded; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v85; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
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
    goto LABEL_173;
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
    goto LABEL_145;
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
LABEL_171:
    FltReleaseContext(v16);
LABEL_172:
    MappingTableForFileObject = v17;
    goto LABEL_173;
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
      (unsigned __int16)(p_UnicodeString->MaximumLength + Source->MaximumLength),
      1835943509);
    if ( !DestinationString.Buffer )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a11,
        (struct UnionFs::StackEventTracer *)0x17C000F01CALL,
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
      goto LABEL_173;
    }
    RtlCopyUnicodeString(&DestinationString, p_UnicodeString);
    appended = RtlAppendUnicodeStringToString(&DestinationString, v30);
    if ( appended < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        (int)a11,
        (struct UnionFs::StackEventTracer *)0x17D000F01D5LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
        "API: Constructing parentAndComponent",
        ObjectAttributesa);
LABEL_54:
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v38);
      if ( v26 )
        utl::_RefCountBase::_DecStrong(v26);
      v40 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v40, v39);
        ExFreePoolWithTag(v40, 0);
      }
      if ( v26 )
        utl::_RefCountBase::_DecStrong(v26);
      v41 = v96 == 0;
LABEL_63:
      if ( v41 )
        v95 = 0;
      FsFltWil::Details::FreeUnicodeString(&v95, v39);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v42);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v108, v43);
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 24LL))(v111);
      if ( v107 )
        utl::_RefCountBase::_DecStrong(v107);
      FltReleaseContext(v16);
      MappingTableForFileObject = appended;
      goto LABEL_173;
    }
    v105[0] = off_14007E748;
    v105[13] = v105;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a11, v104);
    memset(v114, 0, 0x48u);
    TransactionParameterBlock = IoGetTransactionParameterBlock(FileObject);
    v45 = IoGetSilo(FileObject);
    IoStatusBlock = (const struct _UNICODE_STRING *)TransactionParameterBlock;
    appended = UnionFs::Utils::StatItem(&DestinationString, **((_QWORD **)v27 + 1), v45, v115, v114);
    v46 = *((_WORD *)a11 + 245);
    if ( v46 )
    {
      v47 = v46 - 1;
      *((_WORD *)a11 + 245) = v47;
      v48 = 120 * (v47 + 1LL);
      v49 = *(_QWORD *)((char *)a11 + v48);
      *(_QWORD *)((char *)a11 + v48) = 0;
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 24LL))(v49);
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
          (struct UnionFs::StackEventTracer *)0x17E000F01EFLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "PUSH: Querying stat information",
          (const char *)a11);
        goto LABEL_54;
      }
      utl::make_unique<UnionFs::FindAndStatResults,,0>(&v100);
      v50 = v100;
      if ( !v100 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x3E5000F0202LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "ORIGIN: Allocating findAndStatResults",
          (const char *)a11);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v51);
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v52 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v52, v32);
          ExFreePoolWithTag(v52, 0);
        }
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v34 = v96 == 0;
        goto LABEL_45;
      }
      v85 = 0;
      *((_QWORD *)v100 + 12) = &v85;
      appended = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v106, &DestinationString, v16, v115, v50);
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x17F000F020ELL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "PUSH: Utils::FindAndStatItemInLayers",
          (const char *)a11);
LABEL_89:
        v54 = (struct _UNICODE_STRING *)v85;
        if ( v85 )
        {
          if ( !*((_BYTE *)v85 + 16) )
            *(_OWORD *)v85 = 0;
          FsFltWil::Details::FreeUnicodeString(v54, v53);
          ExFreePoolWithTag(v54, 0);
        }
        if ( v50 )
        {
          v55 = (utl::_RefCountBase *)v50[11];
          if ( v55 )
            utl::_RefCountBase::_DecStrong(v55);
          ExFreePoolWithTag(v50, 0);
        }
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v53);
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v56 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v56, v39);
          ExFreePoolWithTag(v56, 0);
        }
        if ( v26 )
          utl::_RefCountBase::_DecStrong(v26);
        v41 = v96 == 0;
        goto LABEL_63;
      }
      if ( *(_WORD *)v50 != 1 )
      {
        appended = -1073741809;
        UnionFs::ProcessTraceInfoOrigin(
          (UnionFs *)0xC000000FLL,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x5F3000F0219LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "ORIGIN: Not found",
          (const char *)&DestinationString,
          IoStatusBlock);
        goto LABEL_89;
      }
      FltObject = 0;
      p_FltObject = &FltObject;
      RetVolume = 0;
      v91 = 1;
      appended = FltGetVolumeFromInstance(**(PFLT_INSTANCE **)(v50[10] + 8LL), &RetVolume);
      if ( v91 )
      {
        v57 = p_FltObject;
        v58 = RetVolume;
        if ( *p_FltObject )
          FltObjectDereference(*p_FltObject);
        *v57 = v58;
      }
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x180000F0226LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "API: Getting volume from instance",
          (const char *)a11);
        goto LABEL_114;
      }
      BufferSizeNeeded = 0;
      FltGetVolumeName((PFLT_VOLUME)FltObject, 0, &BufferSizeNeeded);
      if ( BufferSizeNeeded > 0xFFFF )
        MicrosoftTelemetryAssertTriggeredMsgKM("volumeNameSize <= MAXUSHORT");
      LOBYTE(v59) = 1;
      appended = UnionFs::UfsPathName::AsUnicodeString(v85, &UnicodeString, a11, v59);
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          (int)a11,
          (struct UnionFs::StackEventTracer *)0x1F7000F0235LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::NormalizeNameComponentEx",
          "PUSH: Copying full layer name",
          (const char *)a11);
LABEL_114:
        if ( FltObject )
          FltObjectDereference(FltObject);
        goto LABEL_89;
      }
      UnionFs::Utils::RemoveFinalComponent(
        (UnionFs::Utils *)&UnicodeString,
        (struct _UNICODE_STRING *)(unsigned __int16)BufferSizeNeeded,
        0,
        v60);
      p_UnicodeString = &UnicodeString;
      a2 = **(const struct _FLT_INSTANCE ***)(v50[10] + 8LL);
      Silo = PsGetHostSilo(v62, v61);
      if ( FltObject )
        FltObjectDereference(FltObject);
      v64 = (struct _UNICODE_STRING *)v85;
      if ( v85 )
      {
        if ( !*((_BYTE *)v85 + 16) )
          *(_OWORD *)v85 = 0;
        FsFltWil::Details::FreeUnicodeString(v64, v63);
        ExFreePoolWithTag(v64, 0);
      }
      if ( v50 )
      {
        v65 = (utl::_RefCountBase *)v50[11];
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
        ExFreePoolWithTag(v50, 0);
      }
      v11 = FileObject;
    }
    FsFltWil::Details::FreeUnicodeString(&DestinationString, v63);
    goto LABEL_132;
  }
  a2 = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance((UnionFs::UfsStreamHandleCtx *)v16);
  Silo = IoGetSilo(v11);
LABEL_132:
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  v66 = (struct _UNICODE_STRING *)P;
  if ( P )
  {
    if ( !*((_BYTE *)P + 16) )
      *(_OWORD *)P = 0;
    FsFltWil::Details::FreeUnicodeString(v66, v28);
    ExFreePoolWithTag(v66, 0);
  }
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  v17 = 0;
  if ( !v96 )
    v95 = 0;
  FsFltWil::Details::FreeUnicodeString(&v95, v28);
LABEL_145:
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
        goto LABEL_172;
      goto LABEL_171;
    }
    v68 = "API: Getting normalized component name";
    v69 = 0x178000F0270LL;
  }
  else
  {
    v68 = "API: Opening parent";
    v69 = 0x177000F0262LL;
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
LABEL_173:
  UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
  return (unsigned int)MappingTableForFileObject;
}

```

## disassembly

```asm
0x14003a668  mov     [rsp-8+arg_0], rbx
0x14003a66d  push    rbp
0x14003a66e  push    rsi
0x14003a66f  push    rdi
0x14003a670  push    r12
0x14003a672  push    r13
0x14003a674  push    r14
0x14003a676  push    r15
0x14003a678  lea     rbp, [rsp-2E0h]
0x14003a680  sub     rsp, 3E0h
0x14003a687  mov     rax, cs:__security_cookie
0x14003a68e  xor     rax, rsp
0x14003a691  mov     [rbp+310h+var_40], rax
0x14003a698  mov     rax, [rbp+310h+arg_28]
0x14003a69f  lea     rcx, [rbp+310h+var_118]; void *
0x14003a6a6  movzx   edi, [rbp+310h+arg_20]
0x14003a6ad  mov     r15, r8
0x14003a6b0  mov     r14, [rbp+310h+arg_50]
0x14003a6b7  mov     r12, rdx
0x14003a6ba  mov     [rbp+310h+Source], rax
0x14003a6be  xorps   xmm0, xmm0
0x14003a6c1  mov     rax, [rbp+310h+arg_30]
0x14003a6c8  xorps   xmm1, xmm1
0x14003a6cb  mov     [rbp+310h+FileObject], r8
0x14003a6cf  xor     esi, esi
0x14003a6d1  xor     edx, edx; Val
0x14003a6d3  mov     [rbp+310h+FileInformation], rax
0x14003a6da  mov     r8d, 88h; Size
0x14003a6e0  mov     [rbp+310h+var_110], sil
0x14003a6e7  mov     r13, r9
0x14003a6ea  mov     [rbp+310h+var_98], rsi
0x14003a6f1  movdqu  xmmword ptr [rbp+310h+Context], xmm0
0x14003a6f9  movdqu  xmmword ptr [rbp+1F0h], xmm1
0x14003a701  call    memset
0x14003a706  lea     r9, [rbp+310h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14003a70d  mov     qword ptr [rsp+410h+DesiredAccess], r14; struct UnionFs::StackEventTracer *
0x14003a712  mov     rdx, r15; FileObject
0x14003a715  mov     rcx, r12; Instance
0x14003a718  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14003a71d  mov     ebx, eax
0x14003a71f  test    eax, eax
0x14003a721  jns     short loc_14003A74F
0x14003a723  lea     rax, aPushGettingStr_0; "PUSH: Getting streamhandle ctx"
0x14003a72a  mov     r8, 176000F017Ch; struct UnionFs::StackEventTracer *
0x14003a734  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a73b  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a740  mov     rdx, r14; int
0x14003a743  mov     ecx, ebx; this
0x14003a745  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a74a  jmp     loc_14003B4B3
0x14003a74f  mov     rax, [rbp+310h+Context+8]
0x14003a756  lea     rdx, [rbp+310h+var_108]
0x14003a75d  mov     rsi, [rbp+310h+Context]
0x14003a764  lea     rcx, [rbp+310h+var_1A8]
0x14003a76b  mov     [rbp+310h+var_1C8], rax
0x14003a772  xorps   xmm0, xmm0
0x14003a775  mov     rax, [rbp+310h+var_120]
0x14003a77c  xor     ebx, ebx
0x14003a77e  mov     [rbp+310h+var_1C0], rax
0x14003a785  mov     rax, [rbp+310h+var_118]
0x14003a78c  mov     [rbp+310h+var_1B8], rax
0x14003a793  mov     al, [rbp+310h+var_110]
0x14003a799  mov     [rbp+310h+var_1B0], al
0x14003a79f  mov     [rbp+310h+Context], rbx
0x14003a7a6  movdqu  xmmword ptr [rbp+310h+Context+8], xmm0
0x14003a7ae  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14003a7b3  xor     edx, edx; Val
0x14003a7b5  lea     rcx, [rbp+310h+var_118]; void *
0x14003a7bc  mov     r8d, 88h; Size
0x14003a7c2  call    memset
0x14003a7c7  mov     al, [rbp+310h+arg_40]
0x14003a7cd  lea     ecx, [rbx+1]
0x14003a7d0  not     al
0x14003a7d2  mov     [rbp+310h+var_298], rcx
0x14003a7d6  and     al, cl
0x14003a7d8  xorps   xmm1, xmm1
0x14003a7db  mov     [rbp+310h+arg_40], al
0x14003a7e1  lea     eax, [rbx+28h]
0x14003a7e4  xorps   xmm0, xmm0
0x14003a7e7  movups  xmmword ptr [rbp+310h+var_2B8.Size], xmm1
0x14003a7eb  mov     [rbp+310h+var_2B8.Size], ax
0x14003a7ef  movups  xmmword ptr [rbp+310h+UnicodeString.Length], xmm0
0x14003a7f3  movups  xmmword ptr [rbp+310h+var_2B8.DeviceObjectHint], xmm1
0x14003a7f7  test    rsi, rsi
0x14003a7fa  jz      loc_14003B204
0x14003a800  mov     eax, [rsi]
0x14003a802  test    cl, al
0x14003a804  jz      loc_14003B204
0x14003a80a  cmp     [rbp+310h+var_1C8], rbx
0x14003a811  jnz     short loc_14003A886
0x14003a813  lea     rax, aOriginInactive; "ORIGIN: Inactive union for SFO"
0x14003a81a  mov     edi, 0C0ED0008h
0x14003a81f  mov     ecx, edi; this
0x14003a821  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a826  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a82d  mov     r8, 608000F019Ah; struct UnionFs::StackEventTracer *
0x14003a837  mov     rdx, r14; int
0x14003a83a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a83f  lea     rcx, [rbp+310h+UnicodeString]; UnicodeString
0x14003a843  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a848  lea     rcx, [rbp+310h+var_1B8]; this
0x14003a84f  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003a854  mov     rcx, [rbp+310h+var_138]
0x14003a85b  test    rcx, rcx
0x14003a85e  jz      short loc_14003A86C
0x14003a860  mov     rax, [rcx]
0x14003a863  mov     rax, [rax+18h]
0x14003a867  call    _guard_dispatch_icall
0x14003a86c  mov     rcx, [rbp+310h+var_1C0]; this
0x14003a873  test    rcx, rcx
0x14003a876  jz      loc_14003B4A2
0x14003a87c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a881  jmp     loc_14003B4A2
0x14003a886  mov     r9, r14
0x14003a889  mov     [rbp+310h+FltObject], rbx
0x14003a88d  lea     r8, [rbp+310h+FltObject]
0x14003a891  mov     qword ptr [rsp+410h+DesiredAccess], rbx
0x14003a896  mov     rdx, r15
0x14003a899  mov     rcx, r12
0x14003a89c  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x14003a8a1  xor     r12d, r12d
0x14003a8a4  mov     ebx, eax
0x14003a8a6  test    eax, eax
0x14003a8a8  jns     short loc_14003A923
0x14003a8aa  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x14003a8b1  mov     r8, 2B5000F01A2h; struct UnionFs::StackEventTracer *
0x14003a8bb  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a8c2  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a8c7  mov     rdx, r14; int
0x14003a8ca  mov     ecx, ebx; this
0x14003a8cc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a8d1  lea     rcx, [rbp+310h+UnicodeString]; UnicodeString
0x14003a8d5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a8da  lea     rcx, [rbp+310h+var_1B8]; this
0x14003a8e1  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003a8e6  mov     rcx, [rbp+310h+var_138]
0x14003a8ed  test    rcx, rcx
0x14003a8f0  jz      short loc_14003A8FE
0x14003a8f2  mov     rax, [rcx]
0x14003a8f5  mov     rax, [rax+18h]
0x14003a8f9  call    _guard_dispatch_icall
0x14003a8fe  mov     rcx, [rbp+310h+var_1C0]; this
0x14003a905  test    rcx, rcx
0x14003a908  jz      short loc_14003A90F
0x14003a90a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a90f  mov     rcx, rsi; Context
0x14003a912  call    cs:__imp_FltReleaseContext
0x14003a919  nop     dword ptr [rax+rax+00h]
0x14003a91e  jmp     loc_14003B4B3
0x14003a923  mov     rbx, [rbp+310h+FltObject]
0x14003a927  test    rbx, rbx
0x14003a92a  jnz     short loc_14003A938
0x14003a92c  lea     rcx, aShouldnTHaveBe; "Shouldn't have been called without a ma"...
0x14003a933  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003a938  movzx   r8d, di; unsigned __int16
0x14003a93c  lea     rcx, [rbp+310h+var_300]; this
0x14003a940  mov     rdx, r13; struct _UNICODE_STRING *
0x14003a943  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x14003a948  xorps   xmm2, xmm2
0x14003a94b  mov     [rbp+310h+var_328], r12
0x14003a94f  mov     rcx, rsi; this
0x14003a952  mov     [rbp+310h+P], r12
0x14003a956  movdqu  xmmword ptr [rbp+310h+var_320], xmm2
0x14003a95b  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14003a960  mov     r9b, [rbp+310h+arg_40]; bool
0x14003a967  lea     rcx, [rbp+310h+var_328]
0x14003a96b  mov     [rsp+410h+ObjectAttributes], r14; char *
0x14003a970  lea     r8, [rbp+310h+var_300]; struct UnionFs::UfsPathName *
0x14003a974  mov     qword ptr [rsp+410h+DesiredAccess], rcx; struct UnionFs::LookupScratchRootResults *
0x14003a979  mov     rdx, rax; struct _FLT_INSTANCE *
0x14003a97c  mov     rcx, rbx; this
0x14003a97f  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x14003a984  mov     edi, eax
0x14003a986  test    eax, eax
0x14003a988  jns     short loc_14003AA08
0x14003a98a  lea     rax, aPushLookingUpN_0; "PUSH: Looking up name in mapping table"
0x14003a991  mov     r8, 179000F01AFh; struct UnionFs::StackEventTracer *
0x14003a99b  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003a9a2  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003a9a7  mov     rdx, r14; int
0x14003a9aa  mov     ecx, edi; this
0x14003a9ac  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a9b1  mov     rbx, [rbp+310h+P]
0x14003a9b5  test    rbx, rbx
0x14003a9b8  jz      short loc_14003A9DF
0x14003a9ba  cmp     [rbx+10h], r12b
0x14003a9be  jnz     short loc_14003A9C6
0x14003a9c0  xorps   xmm0, xmm0
0x14003a9c3  movups  xmmword ptr [rbx], xmm0
0x14003a9c6  mov     rcx, rbx; UnicodeString
0x14003a9c9  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003a9ce  xor     edx, edx; Tag
0x14003a9d0  mov     rcx, rbx; P
0x14003a9d3  call    cs:__imp_ExFreePoolWithTag
0x14003a9da  nop     dword ptr [rax+rax+00h]
0x14003a9df  mov     rcx, [rbp+310h+var_320+8]; this
0x14003a9e3  test    rcx, rcx
0x14003a9e6  jz      short loc_14003A9ED
0x14003a9e8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003a9ed  cmp     [rbp+310h+var_2F0], r12b
0x14003a9f1  jnz     short loc_14003A9FA
0x14003a9f3  xorps   xmm0, xmm0
0x14003a9f6  movups  xmmword ptr [rbp+310h+var_300.Length], xmm0
0x14003a9fa  lea     rcx, [rbp+310h+var_300]; UnicodeString
0x14003a9fe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003aa03  jmp     loc_14003A83F
0x14003aa08  mov     rdi, [rbp+310h+var_320+8]
0x14003aa0c  mov     r12, [rbp+310h+var_320]
0x14003aa10  test    rdi, rdi
0x14003aa13  jz      short loc_14003AA19
0x14003aa15  lock inc dword ptr [rdi+8]
0x14003aa19  mov     rcx, rsi; this
0x14003aa1c  test    r12, r12
0x14003aa1f  jnz     short loc_14003AA41
0x14003aa21  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14003aa26  mov     rcx, r15
0x14003aa29  mov     r12, rax
0x14003aa2c  call    cs:__imp_IoGetSilo
0x14003aa33  nop     dword ptr [rax+rax+00h]
0x14003aa38  mov     [rbp+310h+var_298], rax
0x14003aa3c  jmp     loc_14003B17D
0x14003aa41  mov     rax, [r12+8]
0x14003aa46  mov     rbx, [rax]
0x14003aa49  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14003aa4e  cmp     rax, rbx
0x14003aa51  jz      short loc_14003AA5F
0x14003aa53  lea     rcx, aHandlectxTryge; "handleCtx->TryGetScratchInstance() == s"...
0x14003aa5a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003aa5f  mov     rbx, [rbp+310h+Source]
0x14003aa63  lea     rcx, [rbp+310h+DestinationString]
0x14003aa67  mov     r8d, 6D6E4655h
0x14003aa6d  movzx   edx, word ptr [rbx+2]
0x14003aa71  add     dx, [r13+2]
0x14003aa76  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14003aa7b  xor     r15d, r15d
0x14003aa7e  cmp     [rbp+310h+DestinationString.Buffer], r15
0x14003aa82  jnz     loc_14003AB72
0x14003aa88  mov     rdx, r14; int
0x14003aa8b  lea     rax, aOriginAllocati_15; "ORIGIN: Allocating parentAndComponent"
0x14003aa92  mov     r14d, 0C000009Ah
0x14003aa98  mov     qword ptr [rsp+410h+DesiredAccess], rax; char *
0x14003aa9d  mov     ecx, r14d; this
0x14003aaa0  lea     r9, aUnionfsUnionfs_5; "UnionFs::UnionFsFilter::NormalizeNameCo"...
0x14003aaa7  mov     r8, 17C000F01CAh; struct UnionFs::StackEventTracer *
0x14003aab1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003aab6  lea     rcx, [rbp+310h+DestinationString]; UnicodeString
0x14003aaba  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003aabf  test    rdi, rdi
0x14003aac2  jz      short loc_14003AACC
0x14003aac4  mov     rcx, rdi; this
0x14003aac7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003aacc  mov     rbx, [rbp+310h+P]
0x14003aad0  test    rbx, rbx
0x14003aad3  jz      short loc_14003AAFA
0x14003aad5  cmp     [rbx+10h], r15b
0x14003aad9  jnz     short loc_14003AAE1
0x14003aadb  xorps   xmm0, xmm0
0x14003aade  movups  xmmword ptr [rbx], xmm0
0x14003aae1  mov     rcx, rbx; UnicodeString
0x14003aae4  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003aae9  xor     edx, edx; Tag
0x14003aaeb  mov     rcx, rbx; P
0x14003aaee  call    cs:__imp_ExFreePoolWithTag
0x14003aaf5  nop     dword ptr [rax+rax+00h]
0x14003aafa  test    rdi, rdi
0x14003aafd  jz      short loc_14003AB07
0x14003aaff  mov     rcx, rdi; this
0x14003ab02  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003ab07  cmp     [rbp+310h+var_2F0], r15b
0x14003ab0b  jnz     short loc_14003AB14
0x14003ab0d  xorps   xmm0, xmm0
0x14003ab10  movups  xmmword ptr [rbp+310h+var_300.Length], xmm0
0x14003ab14  lea     rcx, [rbp+310h+var_300]; UnicodeString
0x14003ab18  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003ab1d  lea     rcx, [rbp+310h+UnicodeString]; UnicodeString
0x14003ab21  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003ab26  lea     rcx, [rbp+310h+var_1B8]; this
0x14003ab2d  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14003ab32  mov     rcx, [rbp+310h+var_138]
0x14003ab39  test    rcx, rcx
0x14003ab3c  jz      short loc_14003AB4A
0x14003ab3e  mov     rax, [rcx]
0x14003ab41  mov     rax, [rax+18h]
0x14003ab45  call    _guard_dispatch_icall
0x14003ab4a  mov     rcx, [rbp+310h+var_1C0]; this
0x14003ab51  test    rcx, rcx
0x14003ab54  jz      short loc_14003AB5B
0x14003ab56  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003ab5b  mov     rcx, rsi; Context
0x14003ab5e  call    cs:__imp_FltReleaseContext
0x14003ab65  nop     dword ptr [rax+rax+00h]
0x14003ab6a  mov     ebx, r14d
0x14003ab6d  jmp     loc_14003B4B3
0x14003ab72  mov     rdx, r13; SourceString
0x14003ab75  lea     rcx, [rbp+310h+DestinationString]; DestinationString
0x14003ab79  call    cs:__imp_RtlCopyUnicodeString
0x14003ab80  nop     dword ptr [rax+rax+00h]
0x14003ab85  mov     rdx, rbx; Source
0x14003ab88  lea     rcx, [rbp+310h+DestinationString]; Destination
0x14003ab8c  call    cs:__imp_RtlAppendUnicodeStringToString
  ... truncated ...
```
